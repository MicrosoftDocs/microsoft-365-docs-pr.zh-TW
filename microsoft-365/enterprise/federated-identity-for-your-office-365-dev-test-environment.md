---
title: Microsoft 365 測試環境的同盟身分識別
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: 摘要：設定適用於 Microsoft 365 測試環境的同盟驗證。
ms.openlocfilehash: 4796f8f2a7dc6757ccbcb3d608d72ad789d34e40
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067616"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>Microsoft 365 測試環境的同盟身分識別

*這個測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版兩種測試環境。*

Office 365 支援同盟身分識別。這表示 Office 365 的連線使用者指的是 Office 365 信任的同盟驗證伺服器，而不是執行認證本身的驗證。如果使用者的認證正確，同盟驗證伺服器會發出安全性權杖，用戶端再傳送到 Office 365 做為驗證證明。同盟身分識別可進行 Office 365 訂閱驗證的卸載與擴展，以及進階驗證及安全性案例。
  
本文說明如何設定 Microsoft 365 或 Office 365 測試環境中的同盟驗證，如下：

![適用於 Microsoft 365 測試環境的同盟驗證](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase3.png)
  
此組態包含： 
  
- Microsoft 365 E5 或 Office 365 E5 試用版或正式版本訂閱。
    
- 簡化的組織內部網路連線到網際網路，包含 Azure 虛擬網路子網路上的五部虛擬機器 (DC1、APP1、CLIENT1、ADFS1 和 PROXY1)。Azure AD Connect 在 APP1 上執行，將 Active Directory Domain Services 網域中的帳戶清單同步處理到 Office 365。PROXY1 接收輸入的驗證要求。ADFS1 使用 DC1 驗證認證和發行安全性權杖。
    
設定此測試環境有五個階段︰
  
1. 使用密碼雜湊同步處理建立模擬企業測試環境。
    
2. 建立 AD FS 伺服器 (ADFS1)。
    
3. 建立 Web Proxy 伺服器 (PROXY1)。
    
4. 建立自我簽署的憑證並設定 ADFS1 及 PROXY1。
    
5. 設定 Office 365 的同盟身分識別。
    
> [!NOTE]
> 您無法使用 Azure 試用訂閱設定此測試環境。 
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理

請遵循[適用於 Microsoft 365 的密碼雜湊同步處理](password-hash-sync-m365-ent-test-environment.md)中的指示。以下是您產生的組態。
  
![使用密碼雜湊同步處理測試環境的模擬企業](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase1.png)
  
此組態包含： 
  
- Microsoft 365 E5 或 Office 365 E5 試用版或付費訂閱。
- 簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路的子網路上的 DC1、APP1 及 CLIENT1 虛擬機器組成 Azure AD Connect 在 APP1 上執行，以定期將 TESTLAB AD DS 網域同步至 Microsoft 365 或 Office 365 訂閱的 Azure AD 租用戶。

## <a name="phase-2-create-the-ad-fs-server"></a>階段 2：建立 AD FS 伺服器

AD FS 伺服器提供 Office 365 和 DC1 上裝載 corp.contoso.com 網域中的帳戶之間的同盟驗證。
  
若要為 ADFS1 建立 Azure 虛擬機器，請為基本設定填入訂閱和資源群組的名稱和 Azure 位置，然後在本機電腦上的 Azure PowerShell 命令提示字元執行這些命令。
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

接下來，使用 ADFS1 本機系統管理員帳戶名稱和密碼，以使用 [Azure 入口網站](https://portal.azure.com)連線到 ADFS1 虛擬機器，然後開啟 Windows PowerShell 命令提示字元。
  
若要檢查 ADFS1 和 DC1 之間的名稱解析和網路通訊，請執行 **ping dc1.corp.contoso.com** 命令，並檢查有四個回覆。
  
接下來在 ADFS1 上的 Windows PowerShell 命令提示字元使用以下命令將 ADFS1 虛擬機器加入 CORP 網域。
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

以下是產生的組態。
  
![將 AD FS 伺服器新增至 Microsoft 365 測試環境的 DirSync](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a>階段 3：建立 Web Proxy 伺服器

PROXY1 提供嘗試驗證 ADFS1 的使用者之間驗證訊息的 Proxy。
  
若要為 PROXY1 建立 Azure 虛擬機器，請填入資源群組的名稱和 Azure 位置，然後在本機電腦上的 Azure PowerShell 命令提示字元執行這些命令。
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> PROXY1 指派了靜態公用 IP 位址，因為您將建立指向它的公開 DNS 記錄，且當您重新啟動 PROXY1 虛擬機器時它不得變更。 
  
接著，針對 CorpNet 子網路將規則新增到網路安全性群組，以允許從網際網路到 PROXY1 私人 IP 位址和 TCP 連接埠 443 之未經要求的輸入流量。在本機電腦上的 Azure PowerShell 命令提示字元執行這些命令。
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

接下來，使用 PROXY1 本機系統管理員帳戶名稱和密碼，以使用 [Azure 入口網站](https://portal.azure.com)連線到 PROXY1 虛擬機器，然後在 PROXY1 上開啟 Windows PowerShell 命令提示字元。
  
若要檢查 PROXY1 和 DC1 之間的名稱解析和網路通訊，請執行 **ping dc1.corp.contoso.com** 命令，並檢查有四個回覆。
  
接下來在 PROXY1 上的 Windows PowerShell 命令提示字元使用以下命令將 PROXY1 虛擬機器加入 CORP 網域。
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

使用這些 Azure PowerShell 命令在本機電腦上顯示 PROXY1 的公用 IP 位址：
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

接下來，與公用 DNS 提供者合作，建立 **fs.testlab.**\<您的 DNS 網域名稱> 的新公用 DNS A 記錄，其會解析到**寫入主機**命令所顯示之 IP 位址。**fs.testlab.**\<您的 DNS 網域名稱> 以下稱為*同盟服務 FQDN*。
  
接下來，使用 CORP\\User1 認證，以使用 [Azure 入口網站](https://portal.azure.com)連線到 DC1 虛擬機器，然後在系統管理員層級 Windows PowerShell 命令提示字元執行下列命令：
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
這些命令會建立內部 DNS A 記錄，使得 Azure 虛擬網路上的虛擬機器可將內部同盟 FQDN 解析為 ADFS1 的私人 IP 位址。
  
以下是產生的組態。
  
![將 Web 應用程式 Proxy 伺服器新增至 Microsoft 365 測試環境的 DirSync](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>階段 4：建立自我簽署的憑證並設定 ADFS1 及 PROXY1

在這個階段，您可以為同盟服務 FQDN 建立自我簽署的數位憑證，並將 ADFS1 和 PROXY1 設定為 AD FS 伺服器陣列。
  
首先，使用 CORP\\User1 認證，以使用 [Azure 入口網站](https://portal.azure.com)連線到 DC1 虛擬機器，然後開啟系統管理員層級 Windows PowerShell 命令提示字元。
  
接下來，在 DC1 上的 Windows PowerShell 命令提示字元中使用此命令建立 AD FS 服務帳戶：
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
請注意，此命令會提示您提供帳戶密碼。請選擇強式密碼，並將其記錄在安全的位置。您在此階段和階段 5 會需要該密碼。
  
使用 CORP\\User1 認證以使用 [Azure 入口網站](https://portal.azure.com)連線到 ADFS1 虛擬機器。開啟 ADFS1 上的系統管理員層級 Windows PowerShell 命令提示字元，填入您的同盟服務 FQDN，然後執行這些命令以建立自我簽署的憑證：
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

接下來，使用這些步驟，將新的自我簽署憑證儲存為檔案。
  
1. 按一下 [開始]****，輸入 **mmc.exe**，然後按 **Enter**。
    
2. 按一下 **[檔案] > [新增/移除嵌入式管理單元]**。
    
3. 在 [新增或移除嵌入式管理單元]**** 中可用的嵌入式管理單元清單中按兩下 [憑證]****，按一下 [電腦帳戶]****，然後按一下 [下一步]****。
    
4. 在 [選取電腦]**** 中，按一下 [完成]****，然後按一下 [確定]****。
    
5. 在樹狀窗格中，開啟 **[憑證 (本機電腦)] > [個人] > [憑證]**。
    
6. 以滑鼠右鍵按一下具同盟服務 FQDN 的憑證，按一下 [所有工作]****，然後按一下 [匯出]****。
    
7. 在 [歡迎]**** 頁面上，按 [下一步]****。
    
8. 在 [匯出私密金鑰]**** 頁面上，按一下 [是]****，然後按 [下一步]****。
    
9. 在 [匯出檔案格式]**** 頁面上，按一下 [匯出所有延伸內容]****，然後按 [下一步]****。
    
10. 在 [安全性]**** 頁面上，按一下 [密碼]****，然後在 [密碼]**** 和 [確認密碼]**** 中輸入密碼。
    
11. 在 [要匯出的檔案]**** 頁面上，按一下 [瀏覽]****。
    
12. 瀏覽至 [C:\\Certs]**** 資料夾中，在 [檔案名稱]**** 中輸入 **SSL**，然後按一下 [儲存]****。
    
13. 在 [要匯出的檔案]**** 頁面上，按一下 [下一步]****。
    
14. 在 [完成憑證匯出精靈]**** 頁面上，按一下 [完成]****。出現提示時，按一下 [確定]****。
    
接下來，在 ADFS1 上的 Windows PowerShell 命令提示字元中使用此命令安裝 AD FS 服務：
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

等待安裝完成。
  
接下來，使用下列步驟設定 AD FS 服務：
  
1. 按一下 [開始]****，然後按一下 [伺服器管理員]**** 圖示。
    
2. 在 [伺服器管理員] 的樹狀窗格中，按一下 [AD FS]****。
    
3. 在頂端的工具列，按一下橘色警告符號，然後按一下 [在此伺服器上設定同盟服務]****。
    
4. 在 Active Directory 同盟服務設定精靈的 [歡迎]**** 頁面上，按一下 [下一步]****。
    
5. 在 [連線到 AD DS]**** 頁面上，按一下 [下一步]****。
    
6. 在 [指定服務內容]**** 頁面上：
    
  - 針對 **SSL 憑證**，按一下向下箭號，然後按一下具有同盟服務 FQDN 名稱的憑證。
    
  - 在 [同盟服務顯示名稱]**** 中，輸入您虛構組織的名稱。
    
  - 按 [下一步]****。
    
7. 在 [指定服務帳戶]**** 頁面上，為**帳戶名稱**按一下 [選取]****。
    
8. 在 [選取使用者或服務帳戶]**** 中，輸入 **ADFS 服務**，按一下 [檢查名稱]****，然後按一下 [確定]****。
    
9. 在 [帳戶密碼]**** 中輸入 ADFS 服務帳戶的密碼，然後按一下 [下一步]****。
    
10. 在 [指定設定資料庫]**** 頁面上，按一下 [下一步]****。
    
11. 在 [校閱選項]**** 頁面上，按一下 [下一步]****。
    
12. 在 [必要條件檢查]**** 頁面上，按一下 [設定]****。
    
13. 在 [結果]**** 頁面上，按一下 [關閉]****。
    
14. 依序按一下 [開始]****、電源圖示、[重新啟動]**** 和 [繼續]****。
    
使用 CORP\\User1 帳戶認證，從 [Azure 入口網站](https://portal.azure.com)連線到 PROXY1。
  
接下來，使用這些步驟安裝自我簽署的憑證及設定 PROXY1。
  
1. 按一下 [開始]****，輸入 **mmc.exe**，然後按 **Enter**。
    
2. 按一下 **[檔案] > [新增/移除嵌入式管理單元]**。
    
3. 在 [新增或移除嵌入式管理單元]**** 中可用的嵌入式管理單元清單中按兩下 [憑證]****，按一下 [電腦帳戶]****，然後按一下 [下一步]****。
    
4. 在 [選取電腦]**** 中，按一下 [完成]****，然後按一下 [確定]****。
    
5. 在樹狀窗格中，開啟 **[憑證 (本機電腦)] > [個人] > [憑證]**。
    
6. 在 [個人]**** 上按一下滑鼠右鍵，按一下 [所有工作]**** 然後按一下 [匯入]****。
    
7. 在 [歡迎]**** 頁面上，按 [下一步]****。
    
8. 在 [要匯入的檔案]**** 頁面上，輸入 **\\\\adfs1\\certs\\ssl.pfx**，然後按一下 [下一步]****。
    
9. 在 [私密金鑰保護]**** 頁面上，在 [密碼]**** 中輸入憑證密碼，然後按一下 [下一步]****。
    
10. 在 [憑證存放區]**** 頁面上，按 [下一步]****。
    
11. 在 [完成]**** 頁面上，按一下 [完成]****。
    
12. 在 [憑證存放區]**** 頁面上，按 [下一步]****。
    
13. 出現提示時，按一下 [確定]****。
    
14. 在樹狀窗格中按一下 [憑證]****。
    
15. 以滑鼠右鍵按一下憑證，然後按一下 [複製]****。
    
16. 在樹狀窗格中，開啟 **[信任的根憑證授權] > [憑證]**。
    
17. 將滑鼠指標移動到已安裝的憑證清單下方，以滑鼠右鍵按一下，然後按一下 [貼上]****。
    
開啟系統管理員層級 PowerShell 命令提示字元，執行下列命令：
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

等待安裝完成。
  
使用下列步驟設定 Web 應用程式 Proxy 服務以使用 ADFS1 作為其同盟伺服器：
  
1. 按一下 [開始]****，然後按一下 [伺服器管理員]****。
    
2. 在樹狀窗格中，按一下 [遠端存取]****。
    
3. 在頂端的工具列中，按一下橘色警告符號，然後按一下 [開啟 Web 應用程式 Proxy 精靈]****。
    
4. 在 Web 應用程式 Proxy 設定精靈的 [歡迎]**** 頁面上，按一下 [下一步]****。
    
5. 在 [同盟伺服器]**** 頁面上：
    
  - 在**同盟服務名稱**中輸入您的同盟服務 FQDN。
    
  - 在**使用者名稱**中輸入 **CORP\\User1**。
    
  - 在 [密碼]**** 中，輸入 User1 帳戶的密碼。
    
  - 按 [下一步]****。
    
6. 在 [AD FS Proxy 憑證]**** 頁面上，按一下向下箭號，按一下具有同盟服務 FQDN 的憑證，然後按一下 [下一步]****。
    
7. 在 [確認]**** 頁面上，按 [設定]****。
    
8. 在 [結果]**** 頁面上，按一下 [關閉]****。

    
## <a name="phase-5-configure-office-365-for-federated-identity"></a>階段 5：設定 Office 365 的同盟身分識別

以 CORP\\User1 帳戶認證使用 [Azure 入口網站](https://portal.azure.com)連線到 APP1 虛擬機器。
  
使用下列步驟為同盟驗證設定 Azure AD Connect 與 Office 365 訂閱：
  
1. 從桌面，按兩下 [Azure AD Connect]****。
    
2. 在 [歡迎使用 Azure AD Connect]**** 頁面上，按一下 [設定]****。
    
3. 在 [其他工作]**** 頁面上，按一下 [變更使用者登入]****，然後按一下 [下一步]****。
    
4. 在 [連線到 Azure AD]**** 頁面上，輸入您的 Office 365 全域系統管理員帳戶名稱和密碼，然後按 [下一步]****。
    
5. 在 [使用者登入]**** 頁面上，按一下 [和 AD FS 的同盟]****，然後按 [下一步]****。
    
6. 在 [AD FS 伺服器陣列]**** 頁面上，按一下 [使用現有的 AD FS 伺服器陣列]****，在 [伺服器名稱]**** 中輸入 **ADFS1**，然後按一下 [下一步]****。
    
7. 出現伺服器認證提示時，輸入 CORP\\User1 帳戶認證，然後按一下 [確定]****。
    
8. 在 [網域系統管理員]**** 認證頁面中，在 [使用者名稱]**** 中輸入 **CORP\\User1**，並在 [密碼]**** 中輸入帳戶密碼，然後按一下 [下一步]****。
    
9. 在 [AD FS 服務帳戶]**** 頁面上，在 [網域使用者名稱]**** 中輸入 **CORP\\ADFS 服務**，並在 [網域使用者密碼]**** 中輸入帳戶密碼，然後按一下 [下一步]****。
    
10. 在 [Azure AD 網域]**** 頁面上，於 [網域]**** 中選取您先前在階段 1 建立並新增至 Office 365 訂閱的網域名稱，然後按一下 [下一步]****。
    
11. 在 [準備設定]**** 頁面上，按一下 [設定]****。
    
12. 在 [安裝完成]**** 頁面上，按一下 [驗證]****。
    
    您應該會看到訊息，表示內部網路和網際網路設定皆已驗證。
    
13. 在 [安裝完成]**** 頁面上，按一下 [結束]****。
    
若要證明同盟驗證為正常運作：
  
1. 在本機電腦上開啟瀏覽器的新私人執行個體，然後移至 [https://admin.microsoft.com](https://admin.microsoft.com)。
    
2. 在登入認證中輸入 **user1@**\< (在階段 1> 建立的網域)。 
    
    比方說，如果您的測試網域是 **testlab.contoso.com**，則輸入 "user1@testlab.contoso.com"。按 TAB 鍵或讓 Office 365 為您自動重新導向。
    
    您現在應該會看到**您的連線非私人連線**頁面。因為您在 ADFS1 上安裝了自我簽署的憑證，您的桌上型電腦無法加以驗證，才會出現此頁面。在同盟驗證的生產部署中，您可以使用來自受信任憑證授權單位的憑證，使用者即不會看到此頁面。
    
3. 在**您的連線非私人連線**頁面上，按一下 [進階]****，然後按一下 [繼續前往\<同盟服務 FQDN>]****。 
    
4. 在具有虛構組織名稱的頁面上，以下列動作登入：
    
  - 名稱的 **CORP\\User1**
    
  - User1 帳戶的密碼
    
    您應該會看到 **Microsoft Office 首頁**頁面。
    
此程序會示範 Office 365 試用訂閱與 DC1 上裝載的 AD DS corp.contoso.com 網域的同盟。以下是驗證程序的基本概念：
  
1. 當您使用登入帳戶名稱內在階段 1 建立的同盟網域時，Office 365 會將您的瀏覽器重新導向至同盟服務 FQDN 和 PROXY1。
    
2. PROXY1 會向您的本機電腦傳送虛構公司登入頁面。
    
3. 當您將 CORP\\User1 和密碼傳送給 PROXY1，PROXY1 會轉寄給 ADFS1。
    
4. ADFS1 會使用 DC1 驗證 CORP\\User1 和密碼，並向您的本機電腦傳送安全性權杖。
    
5. 本機電腦會將安全性權杖傳送到 Office 365。
    
6. Office 365 會驗證安全性權杖是由 ADFS1 所建立，並允許存取。
    
您的 Office 365 試用訂閱現在設定使用同盟驗證。您可以將此開發/測試環境用於進階驗證案例。
  
## <a name="next-step"></a>下一步

當您準備好在 Azure 中部署 Office 365 的生產就緒、高可用性同盟驗證，請參閱＜[在 Azure 中部署 Microsoft 365 或 Office 365 的高可用性同盟驗證](https://docs.microsoft.com/office365/enterprise/deploy-high-availability-federated-authentication-for-office-365-in-azure)＞。
  
