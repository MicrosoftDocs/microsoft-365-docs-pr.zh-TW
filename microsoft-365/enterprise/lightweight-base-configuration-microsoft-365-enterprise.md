---
title: 輕量型基本組態
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 使用此測試實驗室指南來建立輕量測試環境，以測試 Microsoft 365 for enterprise。
ms.openlocfilehash: 2de0760cef7339f62229575b1e0a54b3c67a4e9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909703"
---
# <a name="the-lightweight-base-configuration"></a>輕量型基本組態

*此測試實驗室指南可用於 enterprise 和 Office 365 企業測試環境的 Microsoft 365。*

本文說明如何使用 Microsoft 365 E5 訂閱與執行 Windows 10 企業版的電腦建立簡化的環境。

![輕量型 Microsoft 365 企業版測試環境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

建立輕量測試環境包含五個階段：
- [階段1：建立您的 Microsoft 365 E5 訂閱](#phase-1-create-your-microsoft-365-e5-subscription)
- [階段 2：設定 Office 365 試用訂閱](#phase-2-configure-your-office-365-trial-subscription)
- [階段 3：新增 Microsoft 365 E5 試用版訂閱](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [階段 4：建立 Windows 10 企業版電腦](#phase-4-create-a-windows-10-enterprise-computer)
- [階段 5：將 Windows 10 電腦加入 Azure AD](#phase-5-join-your-windows-10-computer-to-azure-ad)

使用所產生的環境來測試 [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise)的功能。

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請參閱 [適用于企業測試實驗室指南堆疊的 microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

>[!NOTE]
>您可能會想要列印本文章，以記錄 在Office 365 試用版訂閱的 30 天中此環境所需的特定資訊。 您可以輕鬆將試用訂閱延長 30 天。 若為永久測試環境，請建立具有個別 Azure AD 租用戶及少量授權的新付費訂閱。

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>階段1：建立您的 Microsoft 365 E5 訂閱

我們從 Microsoft 365 E5 試用訂閱開始，然後新增 Microsoft 365 E5 訂閱給它。

>[!NOTE]
>我們建議您建立 Office 365 的試用訂閱，使測試環境具有您目前所擁有的任何付費訂閱中的個別 Azure AD 租使用者。 這種分隔意味著您可以新增及移除測試承租人中的使用者和群組，而不會影響您的實際執行訂閱。

若要開始 Microsoft 365 E5 試用版訂閱，您需要虛構的公司名稱和新 Microsoft 帳戶。
  
1. 我們建議您使用公司名稱 Contoso 的變種作為公司名稱，也就是 Microsoft 範例內容中使用的虛構公司，但此為非必要的動作。在此處記錄您虛構公司名稱： ![線](../media/Common-Images/TableLine.png)
    
2. 若要註冊新 Microsoft 帳戶，請移至 [https://outlook.com ](https://outlook.com)，並使用新電子郵件帳戶以及地址建立帳戶。您會使用這個帳戶來登入 Office 365。
    
    - 在此處記錄您新帳戶的名字和姓氏： ![線](../media/Common-Images/TableLine.png)
    
    - 在此處記錄新電子郵件帳戶地址： ![線](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>註冊 Office 365 E5 試用訂閱

1. 在您的瀏覽器中，移至 [https://aka.ms/e5trial](https://aka.ms/e5trial) 。
    
2. 在 **感謝您選擇 Office 365 E5** 頁面的步驟1中，輸入新的電子郵件帳戶位址。
3. 在追蹤訂閱處理常式的步驟2中，輸入要求的資訊，然後執行驗證。
4. 在 [步驟 3] 中，輸入組織名稱，然後輸入將成為訂閱全域管理員的帳戶名稱。
5. 針對步驟 4，在此記錄登入頁面 (選取並複製)： ![線](../media/Common-Images/TableLine.png)
6. 在此記錄使用者識別碼：![線](../media/Common-Images/TableLine.png).onmicrosoft.com  
   記錄您在安全位置輸入的密碼。
   此值將被稱為 **「全域系統管理員名稱」**。
7. 選取 [ **移至設定**]。
8. 在 Office 365 E5 設定中，選取 [ **繼續使用 *您的組織* onmicrosoft.com 電子郵件] 和**[登入]，然後選取 [結束]，然後再依序 **繼續**。

您應該會看到 Microsoft 365 系統管理中心。
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>階段 2：設定 Office 365 試用訂閱

在這個階段中，您可以設定其他使用者使用您的訂閱，並指派他們 Office 365 E5 授權。
  
若要使用電腦的 [Azure Active Directory PowerShell 的圖形模組連線到您的訂閱，請使用 [[連線至 Microsoft 365 與 PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)的指示]。
    
在 [ **Windows PowerShell 憑證要求** ] 對話方塊中，輸入全域管理員名稱 (例如，[ *Jdoe@contosotoycompany.onmicrosoft.com*) ] 和 [密碼]。
  
填寫您的組織名稱 (例如， *contosotoycompany*) 、兩個字元的國家/地區代碼、通用帳戶密碼，然後從 PowerShell 提示中執行下列命令：

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> 這裡會使用常見密碼，以便在測試環境中能自動化並輕鬆進行設定。 當然，對於生產訂閱，這是非常不鼓勵的。 

### <a name="record-key-information-for-future-reference"></a>記錄重要資訊供日後參考

若尚未記錄這些值，請立即進行記錄：
  
- 全域系統管理員名稱： ![線](../media/Common-Images/TableLine.png).onmicrosoft.com (來自階段 1 的步驟 6)
    
    也將此帳戶的密碼記錄在安全的位置。
    
- 您的試用訂閱組織名稱： ![線](../media/Common-Images/TableLine.png) (來自階段 1 的步驟 4)
    
- 若要列出使用者 2、使用者 3、使用者 4 和使用者 5 的帳戶，從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    在此記錄帳戶名稱：
    
  - 使用者 2 的帳戶名稱：user2@![線](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - 使用者 3 的帳戶名稱：user3@![線](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - 使用者 4 的帳戶名稱：user4@![線](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - 使用者 5 的帳戶名稱：user5@![線](../media/Common-Images/TableLine.png).onmicrosoft.com
    
    一併將這些帳戶的常見密碼記錄於安全的位置。
   
### <a name="using-an-office-365-test-environment"></a>使用 Office 365 測試環境

如果您只需要 Office 365 測試環境，您不需要閱讀本文的其餘部分。

如需同時適用于 Office 365 和 Microsoft 365 的其他測試實驗室指南，請參閱 [Microsoft 365 for Enterprise Test Lab 指南](m365-enterprise-test-lab-guides.md)。
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>階段 3：新增 Microsoft 365 E5 試用版訂閱

在此階段中，您可以註冊 Microsoft 365 E5 試用版訂閱，並將它新增至與 Office 365 E5 試用版訂閱相同的組織。
  
首先，新增 Microsoft 365 E5 試用版訂閱，並將新的 Microsoft 365 授權指派給您的全域系統管理員帳戶。
  
1. 在網際網路瀏覽器私人視窗中，使用您的全域系統管理員帳號憑證，登入 Microsoft 365 系統管理中心 [https://admin.microsoft.com](https://admin.microsoft.com) 。
    
2. 在 [ **Microsoft 365 系統管理中心** ] 頁面上，于左側導覽中，選取 [ **帳單 > 購買服務**]。
    
3. 在 [ **購買服務** ] 頁面上，選取 [ **Microsoft 365 E5**]，然後選取 [ **取得免費試用版**]。

4. 在 [ **Microsoft 365 E5 試用** ] 頁面上，決定接收短信或電話、輸入您的電話號碼，然後選取 [ **文字 me** ] 或 [ **呼叫我**]。 執行驗證。

5. 在 [ **確認您的訂單** ] 頁面上，選取 [ **立即試用**]。

6. 在 [ **訂單接收** ] 頁面上，選取 [ **繼續**]。

7. 在 Microsoft 365 系統管理中心中，選取 [ **使用者] >**[作用中的使用者]。

8. 在 [作用中的 **使用者**] 中，選取您的系統管理員帳戶。

9. 選取 [ **授權和應用程式**]。

10. 停用 Office 365 企業版 E5 授權，然後啟用 Microsoft 365 E5 授權。

11. 選取 [ **儲存變更**]，然後關閉 [使用者帳戶資訊] 窗格。

接下來，請為所有其他帳戶 (使用者 2、使用者 3、使用者 4 和使用者 5) 重複先前程序的步驟 8 至 11。
  
> [!NOTE]
> Microsoft 365 E5 試用訂閱的長度為30天。 若為永久測試環境，請將此試用訂閱轉換為具少量授權的付費訂閱。
  
測試環境現在擁有：
  
- Microsoft 365 E5 試用版訂閱。
- 所有適當的使用者帳戶 (全域系統管理員或所有五個使用者帳戶) 皆已可使用 Microsoft 365 E5。
    
您產生的設定會新增 Microsoft 365 E5，如下所示：
  
![Microsoft 365 企業版測試環境的階段 3](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>階段 4：建立 Windows 10 企業版電腦

在這個階段中，您會建立執行 Windows 10 企業版的獨立電腦，作為實體電腦、虛擬機器或是 Azure 虛擬機器。
  
### <a name="physical-computer"></a>實體電腦

在個人電腦上，安裝 Windows 10 企業版。 您可以在 [這裡](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下載 Windows 10 企業版試用版。
  
### <a name="virtual-machine"></a>虛擬機器

使用您選擇的虛擬機器監控程式建立虛擬機器，然後在其上安裝 Windows 10 企業版。 您可以在 [這裡](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下載 Windows 10 企業版試用版。
  
### <a name="virtual-machine-in-azure"></a>Azure 中的虛擬機器

若要在 Microsoft Azure 中建立 Windows 10 虛擬機器，***您必須擁有以 Visual Studio 為基礎的訂閱***，其具有 Windows 10 企業版的影像存取權。其他類型的 Azure 訂閱，例如試用版與付費訂閱，沒有此影像的存取權。如需最新資訊，請參閱 [在 Azure 中使用 Windows 用戶端進行開發/測試案例](/azure/virtual-machines/windows/client-images)。
  
> [!NOTE]
> [!附註] 下列命令集會使用最新版的 Azure PowerShell。 請參閱[開始使用 Azure PowerShell Cmdlet](/powershell/azureps-cmdlets-docs/)。 這些命令會將建立一個名為 WIN10 的 Windows 10 企業版虛擬機器，以及其所有必要基礎結構，包括資源群組、儲存體帳戶和虛擬網路。 如果您已熟悉 Azure 基礎結構服務，請將這些指示加以修改，以符合您目前部署的基礎結構。
  
首先，啟動 Microsoft PowerShell 提示字元。
  
使用此命令登入您的 Azure 帳戶。
  
```powershell
Connect-AzAccount
```

使用此命令取得您的訂閱名稱。
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

設定 Azure 訂用帳戶。 以正確的名稱取代引號內的所有專案（包括 \< and > 字元）。
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

接著，建立新的資源群組。 若要判斷資源群組名稱是否是唯一的，可使用此命令來列出現有的資源群組。
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

使用這些命令建立新的資源群組。 以正確的名稱取代引號內的所有專案（包括 \< and > 字元）。
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

接下來，使用下列命令建立新的虛擬網路和 WIN10 虛擬機器。 出現提示時，請提供 WIN10 本機系統管理員帳戶的名稱和密碼，並將它們儲存在安全的位置。
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a>階段 5：將 Windows 10 電腦加入 Azure AD

建立實體或虛擬機器的 Windows 10 企業版之後，使用本機系統管理員帳戶登入。
  
> [!NOTE]
> 針對 Azure 中的虛擬機器，使用  [這些指示](/azure/virtual-machines/windows/connect-logon) 來連線至該虛擬機器。
  
接下來，將 WIN10 電腦加入 Microsoft 365 E5 訂閱的 Azure AD 租用戶。
  
1. 在 WIN10 電腦的桌面上，選取 [ **啟動 > 設定] > 帳戶 > 存取工作或學校 > Connect**。
    
2. 在 [ **設定公司或學校帳戶** ] 對話方塊中，選取 [將 **此裝置加入 Azure Active Directory**]。
    
3. 在 [ **工作或學校帳戶**] 中，輸入您 Microsoft 365 E5 訂閱的全域系統管理員帳戶名稱，然後選取 **[下一步]**。
    
4. 在 [ **輸入密碼**] 中，輸入全域管理員帳戶的密碼，然後選取 [登 **入**]。
    
5. 當系統提示您確認這是您的組織時，請選取 [ **加入**]，然後選取 [ **完成**]。
    
6. 關閉設定視窗。
    
接下來，在 WIN10 電腦上安裝適用于 enterprise 的 Microsoft 365 應用程式：
  
1. 開啟 Microsoft Edge 瀏覽器，並使用您的全域系統管理員帳號憑證登入 [microsoft 365 系統管理中心](https://admin.microsoft.com) 。
    
2. 在 [ **Microsoft Office 首頁** ] 索引標籤上，選取 [ **安裝 Office**]。
    
3. 當系統提示您執行的動作時，請選取 [**執行**]，然後為 [**使用者帳戶控制** **] 選取 [是]** 。
    
4. 等候 Office 完成其安裝。 當您看到 **全部設定！**，請選取 [ **關閉** ] 兩次。
    
您產生的環境如下所示：

![Microsoft 365 企業版測試環境的階段 5](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

這包括已完成下列項目的 WIN10 電腦：

- 已加入您的 Microsoft 365 E5 訂閱的 Azure AD 租用戶。
- 已在 Microsoft Intune (EMS) 中註冊為 Azure AD 裝置。
- 已安裝適用于企業的 Microsoft 365 應用程式。
  
您現在已準備好嘗試使用 [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。
  
## <a name="next-steps"></a>後續步驟

探索這些額外的測試實驗室指南集合：
  
- [身分識別](m365-enterprise-test-lab-guides.md#identity)
- [行動裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [資訊保護](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[Microsoft 365 企業版文件](/microsoft-365-enterprise/)