---
title: 高可用性同盟驗證階段4設定 web 應用程式 proxy
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
ms.custom: Ent_Solutions
ms.assetid: 1c903173-67cd-47da-86d9-d333972dda80
description: 摘要：針對 Microsoft Azure 中的 Microsoft 365 設定高可用性同盟驗證的 web 應用程式 proxy 伺服器。
ms.openlocfilehash: 95d73d05f2eef087e606df14db180b24c69d5932
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929069"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a>高可用性同盟驗證階段 4：設定 Web 應用程式 Proxy

在此階段的針對 Azure 基礎結構服務中 Microsoft 365 同盟驗證部署高可用性時，您會建立內部負載平衡器和兩個 AD FS 伺服器。
  
您必須先完成此階段，再移至[階段5：設定 Microsoft 365 的同盟驗證](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)。 如需所有階段，請參閱[在 Azure 中部署 Microsoft 365 的高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)。
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a>在 Azure 中建立網際網路對應負載平衡器

您必須先建立網際網路對應負載平衡器，讓 Azure 將從網際網路傳入的用戶端驗證流量分散到兩個 Web 應用程式 Proxy 伺服器。
  
> [!NOTE]
> [!附註] 下列命令集會使用最新版的 Azure PowerShell。 請參閱[開始使用 Azure PowerShell](/powershell/azure/get-started-azureps)。 
  
當您已提供位置和資源群組的值時，在 Azure PowerShell 命令提示字元上或 PowerShell ISE 中執行結果區塊。
  
> [!TIP]
> 若要根據您的自訂設定產生現成 PowerShell 命令區塊，請使用此 Microsoft Excel 設定活頁[簿](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)。 

```powershell
# Set up key variables
$locName="<your Azure location>"
$rgName="<Table R - Item 4 - Resource group name column>"

$publicIP=New-AzPublicIpAddress -ResourceGroupName $rgName -Name "WebProxyPublicIP" -Location $LocName -AllocationMethod "Static"
$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "WebAppProxyServers-LBFE" -PublicIpAddress $publicIP
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "WebAppProxyServers-LBBE"
$healthProbe=New-AzLoadBalancerProbeConfig -Name "WebServersProbe" -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "WebTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

若要顯示指派到您網際網路對應負載平衡器的公用 IP 位址，請在本機電腦上的 Azure PowerShell 命令提示字元上執行以下命令：
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a>決定您的同盟服務 FQDN 並建立 DNS 記錄

您需要決定 DNS 名稱以在網際網路上識別您的同盟伺服器名稱。 Azure AD 連線會以此名稱在階段5中設定 Microsoft 365，這會成為 URL 的一部分，Microsoft 365 會傳送至連線用戶端以取得安全性權杖。 例如 fs.contoso.com (fs 表示同盟服務)。
  
一旦您有了同盟服務 FQDN，請針對同盟服務 FDQN 建立公用 DNS 網域 A 記錄，這會解析為 Azure 網際網路對應負載平衡器的公用 IP 位址。
  
|**名稱**|**類型**|**TTL**|**值**|
|:-----|:-----|:-----|:-----|
|同盟服務 FDQN  <br/> |A  <br/> |3600  <br/> |Azure 網際網路對應負載平衡器的公用 IP 位址 (透過上一節中的 **Write-Host** 命令顯示) <br/> |
   
範例如下：
  
|**名稱**|**類型**|**TTL**|**值**|
|:-----|:-----|:-----|:-----|
|fs.contoso.com  <br/> |A  <br/> |3600  <br/> |131.107.249.117  <br/> |
   
下一步，將 DNS 位址記錄新增至您的組織私人 DNS 命名空間，此命名空間會將您的同盟服務 FQDN 解析為 AD FS 伺服器內部負載平衡器的私人 IP 位址 (表格 I、項目 4、值欄)。
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a>在 Azure 中建立 Web 應用程式 Proxy 伺服器虛擬機器

您可以使用下列 Azure PowerShell 命令的區塊，建立兩部 Web 應用程式 Proxy 伺服器的虛擬機器。  
  
請注意，下列 Azure PowerShell 命令集會使用下表中的值︰
  
- 表格 M，適用於虛擬機器
    
- 表格 R，適用於資源群組
    
- 表格 V，適用於虛擬網路設定
    
- 表格 S，適用於子網路
    
- 表格 I，適用於靜態 IP 位址
    
- 表格 A，適用於可用性設定組
    
請記得您在 [階段2：設定網域控制站](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) 和表格 R、V、S、I 及 A [階段1： configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md)中定義的表 M。
  
當您已提供所有適當的值時，在 Azure PowerShell 命令提示字元上或 PowerShell ISE 中執行結果區塊。
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 3 - Subnet name column>"
$avName="<Table A - Item 3 - Availability set name column>"
$rgNameTier="<Table R - Item 3 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first web application proxy server virtual machine
$vmName="<Table M - Item 6 - Virtual machine name column>"
$vmSize="<Table M - Item 6 - Minimum size column>"
$staticIP="<Table I - Item 7 - Value column>"
$diskStorageType="<Table M - Item 6 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second web application proxy virtual machine
$vmName="<Table M - Item 7 - Virtual machine name column>"
$vmSize="<Table M - Item 7 - Minimum size column>"
$staticIP="<Table I - Item 8 - Value column>"
$diskStorageType="<Table M - Item 7 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> 由於這些虛擬機器是用於內部網路應用程式，系統並不會指派公用 IP 位址或 DNS 網域名稱標籤給它們，它們也不會公開在網際網路上。不過，這也表示您無法從 Azure 入口網站連線到這些虛擬機器。當您檢視虛擬機器的屬性時，無法使用 **連線** 選項。請使用遠端桌面連線附屬應用程式或另一個遠端桌面工具，透過使用虛擬機器的私人 IP 位址或內部網路 DNS 名稱，以及本機管理員帳戶的認證來與其連線。
  
以下是成功完成此階段的設定結果 (包含電腦名稱的預留位置)。
  
**階段 4：Azure 中高可用性同盟驗證基礎結構的網際網路對應負載平衡器和 Web 應用程式 Proxy 伺服器**

![使用 web 應用程式 proxy 伺服器的 Azure 中之高可用性 Microsoft 365 同盟驗證基礎結構的階段4](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a>下一步

使用[階段5：設定 Microsoft 365 的同盟驗證](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)，以繼續設定此工作負載。
  
## <a name="see-also"></a>另請參閱

[Azure 中的 Microsoft 365 高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Microsoft 365 開發/測試環境的同盟身分識別](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365 解決方案與架構中心](../solutions/index.yml)