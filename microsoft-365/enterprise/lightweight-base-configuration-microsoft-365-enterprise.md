---
title: 輕量型基本組態
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 使用這個「測試實驗室指南」建立輕量型測試環境，以測試 Microsoft 365 企業版。
ms.openlocfilehash: e162f1dbdb79b17c5ba6fa4fd88f4b2be3c53863
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866691"
---
# <a name="the-lightweight-base-configuration"></a>輕量型基本組態

本文提供逐步指示，以便建立簡化環境，其中包含 Office 365 E5、Enterprise Mobility + Security (EMS) E5 與執行 Windows 10 企業版的電腦。 

![輕量級 Microsoft 3656 企業版測試環境](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

使用產生的環境來測試 [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise)的功能。

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 按一下[這裡](https://aka.ms/m365etlgstack)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中文件的所有視覺對應。

## <a name="phase-1-create-your-office-365-e5-subscription"></a>階段 1：建立您的 Office 365 E5 訂閱

請依照 [Office 365 開發/測試環境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)中階段 2 和階段 3 的步驟，建立簡易的 Office 365 開發/測試環境，如圖 1 所示。
  
**圖 1：Office 365 E5 訂閱及其 Azure Active Directory (AD) 租用戶和使用者帳戶**

![Microsoft 365 企業版測試環境的階段 1](media/lightweight-base-configuration-microsoft-365-enterprise/Phase1.png)

> [!NOTE]
> Office 365 E5 試用訂閱為 30 天，也可以輕鬆擴充到 60 天。如需永久測試環境，請建立具有一些授權的新付費訂閱。 
  
## <a name="phase-2-add-ems"></a>階段 2：新增 EMS

在這個階段中，您可以註冊 EMS E5 試用訂閱，並將它新增至與 Office 365 E5 試用訂閱相同的組織。
  
首先，請新增 EMS E5 試用訂閱，並指派 EMS 授權給您的全域管理員帳戶。
  
1. 請使用網際網路瀏覽器的私用執行個體，並使用全域管理員帳戶認證登入 Office 365 入口網站。如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 按一下 [管理]**** 磚。
    
3. 在瀏覽器的 [Office 系統管理中心]**** 索引標籤上，按一下左導覽中的 [計費] > [購買服務]****。
    
4. 在 [購買服務]**** 頁面上，尋找 **Enterprise Mobility + Security E5** 項目。將滑鼠指標停留在上面，並且按一下 [開始免費試用]****。
    
5. 在 [確認訂單]**** 頁面上，按一下 [立即試用]****。
    
6. 在 [訂單收據]**** 頁面上，按一下 [繼續]****。
    
7. 在瀏覽器的 [Office 365 系統管理中心]**** 索引標籤上，按一下左導覽中的 [使用者] > [作用中使用者]****。
    
8. 按一下您的全域系統管理員帳戶，然後按一下 [產品授權]**** 的 [編輯]****。
    
9. 在 [產品授權]**** 窗格中，將 [**Enterprise Mobility + Security E5**] 的產品授權設為 [開啟]****，按一下 [儲存]****，然後按兩次 [關閉]****。
    
> [!NOTE]
> Enterprise Mobility + Security E5 試用訂閱為 90 天。針對永久測試環境，建立具有少數授權的新付費訂閱。 
  
 ***如果您已完成 [Office 365 開發/測試環境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)的階段 3***，請為所有其他帳戶 (使用者 2、使用者 3、使用者 4 和使用者 5) 重複先前程序的步驟 8 和 9。
  
測試環境現在擁有：
  
- Office 365 E5 Enterprise 和 EMS E5 試用訂閱會與您的使用者帳戶清單共用相同的 Azure AD 租用戶。
- 已啟用所有適用的使用者帳戶 (僅全域管理員或全部五個使用者帳戶) 以使用 Office 365 E5 和 EMS E5。
    
圖 2 顯示產生的組態，其中會新增 EMS。
  
**圖 2：新增 EMS 試用訂閱**

![Microsoft 365 企業版測試環境的階段 2](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-3-create-a-windows-10-enterprise-computer"></a>階段 3：建立 Windows 10 企業版的電腦

在這個階段中，您會建立執行 Windows 10 企業版的獨立電腦，作為實體電腦、虛擬機器或是 Azure 虛擬機器。
  
### <a name="physical-computer"></a>實體電腦

取得個人電腦並在其上安裝 Windows 10 企業版。您可以在[這裡](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下載 Windows 10 企業版試用版。
  
### <a name="virtual-machine"></a>虛擬機器

使用您所選的 Hypervisor 建立虛擬機器並在其上安裝 Windows 10 企業版。您可以在[這裡](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下載 Windows 10 企業版試用版。
  
### <a name="virtual-machine-in-azure"></a>Azure 中的虛擬機器

若要在 Microsoft Azure 中建立 Windows 10 虛擬機器，***您必須擁有以 Visual Studio 為基礎的訂閱***，其具有 Windows 10 企業版的影像存取權。其他類型的 Azure 訂閱，例如試用版與付費訂閱，沒有此影像的存取權。如需最新資訊，請參閱[在 Azure 中使用 Windows 用戶端進行開發/測試案例](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)。
  
> [!NOTE]
> 下列命令集會使用最新版的 Azure PowerShell。請參閱[開始使用 Azure PowerShell Cmdlet](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)。這些命令集會建置名為 WIN10 的 Windows 10 企業版虛擬機器，以及所有必要的基礎結構，包括資源群組、儲存體帳戶及虛擬網路。如果您已熟悉 Azure 基礎結構服務，請調整這些指示以符合您目前所部署的基礎結構。 
  
首先，啟動 Microsoft PowerShell 提示字元。
  
使用下列命令登入您的 Azure 帳戶。
  
```
Login-AzureRMAccount
```

使用下列命令取得訂用帳戶名稱。
  
```
Get-AzureRMSubscription | Sort Name | Select Name
```

設定 Azure 訂用帳戶。以正確的名稱取代括號中的所有項目 (包括 \< 和 > 字元)。
  
```
$subscr="<subscription name>"
Get-AzureRmSubscription -SubscriptionName $subscr | Select-AzureRmSubscription
```

接著，建立新的資源群組。若要判斷資源群組名稱是否是唯一的，可使用此命令來列出現有的資源群組。
  
```
Get-AzureRMResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

使用這些命令建立新的資源群組。以正確的名稱取代引號內的所有項目 (包括 \< 和 > 字元)。
  
```
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzureRMResourceGroup -Name $rgName -Location $locName
```

接下來，您可以使用這些命令建立新的虛擬網路和 WIN10 虛擬機器。出現提示時，請提供 WIN10 本機系統管理員帳戶的名稱和密碼，並將其存放在安全的位置。
  
```
$corpnetSubnet=New-AzureRMVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzureRMVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzureRMNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzureRMNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzureRMVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzureRMNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzureRMVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$pip=New-AzureRMPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzureRMNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzureRMVMConfig -VMName WIN10 -VMSize Standard_D1_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzureRMVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzureRMVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzureRMVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzureRmVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzureRMVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-4-join-your-windows-10-computer-to-azure-ad"></a>階段 4：將 Windows 10 電腦加入 Azure AD

建立實體或虛擬機器的 Windows 10 企業版之後，使用本機系統管理員帳戶登入。
  
> [!NOTE]
> 針對 Azure 中的虛擬機器，使用[這些指示](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)來與它連線。
  
接下來，將 WIN10 電腦加入 Office 365 和 EMS 訂閱的 Azure AD 租用戶。
  
1. 在 WIN10 電腦桌面，按一下 [開始] > [設定] > [帳戶] > [存取公司或學校] > [連線]****。
    
2. 在 [設定公司或學校帳戶]**** 對話方塊中，按一下 [將此裝置加入 Azure Active Directory]****。
    
3. 在 [公司或學校帳戶]**** 中，輸入 Office 365 訂閱的全域管理員帳戶名稱，然後按一下 [下一步]****。
    
4. 在 [輸入密碼]**** 中，輸入全域管理員帳戶的密碼，然後按一下 [登入]****。
    
5. 系統提示您確認這是您的組織時，按一下 [加入]****，然後按一下 [完成]****。
    
6. 關閉設定視窗。
    
接下來，在 WIN10 電腦上安裝 Office 365 專業增強版。
  
1. 開啟 Microsoft Edge 瀏覽器，並使用全域管理員帳戶認證登入 Office 365 入口網站。如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 在 [Microsoft Office 首頁]**** 索引標籤上，按一下 [安裝 Office 2016]****。
    
3. 系統提示您要執行的動作時，按一下 [執行]****，然後為 [使用者帳戶控制]**** 按一下 [是]****。
    
4. 等待 Office 完成安裝。當您看到 **「一切就緒！」** 時，按兩次 [關閉]****。
    
圖 3 顯示產生的環境，其中包括以下的 WIN10 電腦：

- 已加入 Office 365 和 EMS 訂閱的 Azure AD 租用戶
- 已在 Intune 中註冊為 Azure AD 裝置 (EMS)
- 已安裝 Office 365 專業增強版
  
**圖3：Microsoft 365 測試環境的最終組態**


![Microsoft 365 企業版測試環境的階段 4](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
  
您現在已準備好嘗試 [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。
  
## <a name="next-steps"></a>後續步驟

探索這些額外的測試實驗室指南集合：
  
- [身分識別](m365-enterprise-test-lab-guides.md#identity)
- [行動裝置管理](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [資訊保護](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企業版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365-enterprise/)
