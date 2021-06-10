---
title: 高可用性同盟驗證階段3設定 AD FS 伺服器
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 202b76ff-74a6-4486-ada1-a9bf099dab8f
description: 瞭解如何在 Microsoft Azure 中為 Microsoft 365 的高可用性同盟驗證建立及設定 AD FS 伺服器。
ms.openlocfilehash: 388a99aa496c4ecd9145759d4dfb1b9441b4fb2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909795"
---
# <a name="high-availability-federated-authentication-phase-3-configure-ad-fs-servers"></a>高可用性同盟驗證階段 3：設定 AD FS 伺服器

在此階段的針對 Azure 基礎結構服務中 Microsoft 365 同盟驗證部署高可用性時，您會建立內部負載平衡器和兩個 AD FS 伺服器。
  
您必須先完成此階段，再移至 [階段4：設定 web 應用程式](high-availability-federated-authentication-phase-4-configure-web-application-pro.md)proxy。 如需所有階段，請參閱[在 Azure 中部署 Microsoft 365 的高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)。
  
## <a name="create-the-ad-fs-server-virtual-machines-in-azure"></a>在 Azure 中建立 AD FS 伺服器虛擬機器

使用下列 PowerShell 命令區塊來建立兩個 AD FS 伺服器的虛擬機器。 此 PowerShell 命令集會使用下清單格中的值：
  
- 表格 M，適用於虛擬機器
    
- 表格 R，適用於資源群組
    
- 表格 V，適用於虛擬網路設定
    
- 表格 S，適用於子網路
    
- 表格 I，適用於靜態 IP 位址
    
- 表格 A，適用於可用性設定組
    
請記得您在 [階段2：設定網域控制站](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) 和表格 R、V、S、I 及 A [階段1： configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md)中定義的表 M。
  
> [!NOTE]
> [!附註] 下列命令集會使用最新版的 Azure PowerShell。 請參閱[開始使用 Azure PowerShell](/powershell/azure/get-started-azureps)。 
  
首先，您會為兩個 AD FS 伺服器建立 Azure 內部負載平衡器。 指定變數的值，並移除 \< and > 字元。 當您已提供所有適當的值時，在 Azure PowerShell 命令提示字元上或 PowerShell ISE 中執行結果區塊。
  
> [!TIP]
> 若要根據您的自訂設定產生現成 PowerShell 命令區塊，請使用此 Microsoft Excel 設定活頁[簿](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)。 

```powershell
# Set up key variables
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$privIP="<Table I - Item 4 - Value column>"
$rgName=<Table R - Item 4 - Resource group name column>"

$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "ADFSServers-LBFE" -PrivateIPAddress $privIP -Subnet $subnet
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "ADFSServers-LBBE"

$healthProbe=New-AzLoadBalancerProbeConfig -Name WebServersProbe -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "HTTPSTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

接下來，建立 AD FS 伺服器虛擬機器。
  
當您已提供所有適當的值時，在 Azure PowerShell 命令提示字元上或 PowerShell ISE 中執行結果區塊。
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$avName="<Table A - Item 2 - Availability set name column>"
$rgNameTier="<Table R - Item 2 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first ADFS server virtual machine
$vmName="<Table M - Item 4 - Virtual machine name column>"
$vmSize="<Table M - Item 4 - Minimum size column>"
$staticIP="<Table I - Item 5 - Value column>"
$diskStorageType="<Table M - Item 4 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second AD FS virtual machine
$vmName="<Table M - Item 5 - Virtual machine name column>"
$vmSize="<Table M - Item 5 - Minimum size column>"
$staticIP="<Table I - Item 6 - Value column>"
$diskStorageType="<Table M - Item 5 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

```

> [!NOTE]
> 由於這些虛擬機器是用於內部網路應用程式，並不會指派公用 IP 位址或 DNS 網域名稱標籤，也不會曝露在網際網路上。不過，這也表示您無法透過 Azure 入口網站與虛擬機器連線。當您檢視虛擬機器的屬性時，無法使用 **連線** 選項。請使用遠端桌面連線附屬應用程式或另一個遠端桌面工具，透過使用其私人 IP 位址或內部網路 DNS 名稱來與虛擬機器連線。
  
針對每個虛擬機器，使用您選擇的遠端桌面用戶端，並建立遠端桌面連線。 請使用其內部網路 DNS 或本機管理員帳戶的電腦名稱和認證。
  
針對每一部虛擬機器，在 Windows PowerShell 提示中，使用下列命令將其加入適當的 Active Directory 網域服務 (AD DS) 網域。
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

以下是成功完成此階段的設定結果 (包含電腦名稱的預留位置)。
  
**階段3： Azure 中高可用性同盟驗證基礎結構的 AD FS 伺服器和內部負載平衡器**

![Azure 中具有 AD FS 伺服器的高可用性 Microsoft 365 同盟驗證基礎結構的階段3](../media/f39b2d2f-8a5b-44da-b763-e1f943fcdbc4.png)
  
## <a name="next-step"></a>下一步

使用 [階段4：設定 web 應用程式](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) proxy 以繼續設定此工作負載。
  
## <a name="see-also"></a>另請參閱

[Azure 中的 Microsoft 365 高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Microsoft 365 開發/測試環境的同盟身分識別](federated-identity-for-your-microsoft-365-dev-test-environment.md)