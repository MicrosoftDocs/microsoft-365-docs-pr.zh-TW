---
title: 高可用性同盟驗證階段2設定網域控制站
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
ms.assetid: 6b0eff4c-2c5e-4581-8393-a36f7b36a72f
description: 摘要：在 Microsoft Azure 中設定 Microsoft 365 高可用性同盟驗證的網域控制站與目錄同步處理伺服器。
ms.openlocfilehash: 1c3fd686ee553a57d66dcfd51a6045167a12de8a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688643"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a>高可用性同盟驗證階段 2：設定網域控制站

在此階段，在 Azure 基礎結構服務中為 Microsoft 365 同盟驗證部署高可用性時，您會在 Azure 虛擬網路中設定兩個網域控制站與目錄同步處理伺服器。 然後用戶端 Web 驗證要求即可在 Azure 虛擬網路中驗證，而非透過站台對站台的 VPN 連線來傳送驗證流量至內部部署網路。
  
> [!NOTE]
> Active Directory Federation Services (AD FS) 無法使用 Azure Active Directory (Azure AD) 取代 Active Directory 網域服務 (AD DS) 網域控制站。 
  
您必須先完成此階段，再移至 [階段3：設定 AD FS 伺服器](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)。 請參閱 [在 Azure 中部署 Microsoft 365 的高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) ，以瞭解所有階段。
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a>在 Azure 中建立網域控制站虛擬機器

首先，您必須填寫表格 M 的 **虛擬機器名稱** 欄，然後依需求在 **大小下限** 欄中修改虛擬機器大小。
  
|**項目**|**虛擬機器名稱**|**圖庫影像**|**儲存類型**|**大小下限**|
|:-----|:-----|:-----|:-----|:-----|
|1.  <br/> |![線條](../media/Common-Images/TableLine.png)  (第一個網域控制站，範例 DC1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|2.  <br/> |![線條](../media/Common-Images/TableLine.png)  (第二個網域控制站，範例 DC2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|3.  <br/> |![線條](../media/Common-Images/TableLine.png)  (目錄同步處理伺服器，範例 DS1)   <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|4.  <br/> |![線條](../media/Common-Images/TableLine.png)  (第一個 AD FS 伺服器，範例 ADFS1)   <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|5.  <br/> |![線條](../media/Common-Images/TableLine.png)  (第二個 AD FS 伺服器，範例 ADFS2)   <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|6.  <br/> |![線條](../media/Common-Images/TableLine.png)  (第一個 web 應用程式 proxy 伺服器，範例 WEB1)   <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|7.  <br/> |![線條](../media/Common-Images/TableLine.png)  (第二個 web 應用程式 proxy 伺服器，範例 WEB2)   <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
   
 **表格 M-Azure 中 Microsoft 365 高可用性同盟驗證的虛擬機器**
  
如需虛擬機器大小的完整清單，請參閱[虛擬機器大小](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-sizes)。
  
下列 Azure PowerShell 命令區塊可建立兩個網域控制站的虛擬機器。 指定變數的值，並移除 \< and > 字元。 請注意，此 Azure PowerShell 命令區塊會使用下表中的值︰
  
- 表格 M，適用於虛擬機器
    
- 表格 R，適用於資源群組
    
- 表格 V，適用於虛擬網路設定
    
- 表格 S，適用於子網路
    
- 表格 I，適用於靜態 IP 位址
    
- 表格 A，適用於可用性設定組
    
請記得您在 [階段1： Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md)中定義的表格 R、V、S、I 和 A。
  
> [!NOTE]
> [!附註] 下列命令集會使用最新版的 Azure PowerShell。 請參閱 [Azure PowerShell 入門](https://docs.microsoft.com/powershell/azure/get-started-azureps)。 
  
當您已經提供所有正確的值時，在 Azure PowerShell 提示中或本機電腦的 PowerShell 整合式指令碼環境 (ISE) 中執行結果區塊。
  
> [!TIP]
> 若要根據您的自訂設定來產生現成 PowerShell 命令區塊，請使用此 [Microsoft Excel 配置活頁簿](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)。 

```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table S - Item 1 - Value column>"
$avName="<Table A - Item 1 - Availability set name column>"
$rgNameTier="<Table R - Item 1 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName 

# Create the first domain controller
$vmName="<Table M - Item 1 - Virtual machine name column>"
$vmSize="<Table M - Item 1 - Minimum size column>"
$staticIP="<Table I - Item 1 - Value column>"
$diskStorageType="<Table M - Item 1 - Storage type column>"
$diskSize=<size of the extra disk for Active Directory Domain Services (AD DS) data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second domain controller
$vmName="<Table M - Item 2 - Virtual machine name column>"
$vmSize="<Table M - Item 2 - Minimum size column>"
$staticIP="<Table I - Item 2 - Value column>"
$diskStorageType="<Table M - Item 2 - Storage type column>"
$diskSize=<size of the extra disk for AD DS data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the directory synchronization server
$vmName="<Table M - Item 3 - Virtual machine name column>"
$vmSize="<Table M - Item 3 - Minimum size column>"
$staticIP="<Table I - Item 3 - Value column>"
$diskStorageType="<Table M - Item 3 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the directory synchronization server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> 由於這些虛擬機器是用於內部網路應用程式，並不會指派公用 IP 位址或 DNS 網域名稱標籤，也不會曝露在網際網路上。不過，這也表示您無法透過 Azure 入口網站與虛擬機器連線。當您檢視虛擬機器的屬性時，無法使用**連線**選項。請使用遠端桌面連線附屬應用程式或另一個遠端桌面工具，透過使用其私人 IP 位址或內部網路 DNS 名稱來與虛擬機器連線。
  
## <a name="configure-the-first-domain-controller"></a>設定第一個網域控制站

使用您所選的遠端桌面用戶端，建立第一個網域控制站虛擬機器的遠端桌面連線。請使用其內部網路 DNS 或本機管理員帳戶的電腦名稱和認證。
  
接下來， **在第一個網域控制站虛擬機器**的 Windows PowerShell 命令提示字元中，使用此命令將額外的資料磁片新增至第一個網域控制站：
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

下一步，使用 **ping** 命令來對組織網路上的資源名稱和 IP 位址執行 Ping，以測試第一個網域控制站對組織網路上位置的連線狀況。
  
此程序可確保 DNS 名稱解析運作正常 (虛擬機器已透過內部部署 DNS 伺服器正確設定)，而且封包可在跨單位虛擬網路間傳送。如果此基本測試失敗，請連絡您的 IT 部門，以針對 DNS 名稱解析和封包傳遞問題進行移難排解。
  
下一步，從第一個網域控制站上的 Windows PowerShell 命令提示字元，執行下列命令：
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

系統會提示您提供網域管理員帳戶的認證。電腦將會重新啟動。
  
## <a name="configure-the-second-domain-controller"></a>設定第二個網域控制站

使用您所選的遠端桌面用戶端，建立第二個網域控制站虛擬機器的遠端桌面連線。請使用其內部網路 DNS 或本機管理員帳戶的電腦名稱和認證。
  
接下來，您必須使用 **第二個網域控制站虛擬機器上**的 Windows PowerShell 命令提示字元，將額外的資料磁片新增至第二個網域控制站。
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

接著，執行下列命令：
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

系統會提示您提供網域管理員帳戶的認證。電腦將會重新啟動。
  
下一步，您需要更新虛擬網路的 DNS 伺服器，如此一來，此 Azure 會指派兩個新的網域控制站 IP 位址給虛擬機器，以便使用虛擬機器的 DNS 伺服器。 填寫變數，然後在本機電腦上的 Windows PowerShell 命令提示字元中執行下列命令：
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$adrgName="<Table R - Item 1 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$onpremDNSIP1="<Table D - Item 1 - DNS server IP address column>"
$onpremDNSIP2="<Table D - Item 2 - DNS server IP address column>"
$staticIP1="<Table I - Item 1 - Value column>"
$staticIP2="<Table I - Item 2 - Value column>"
$firstDCName="<Table M - Item 1 - Virtual machine name column>"
$secondDCName="<Table M - Item 2 - Virtual machine name column>"

$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$vnet.DhcpOptions.DnsServers.Add($staticIP1)
$vnet.DhcpOptions.DnsServers.Add($staticIP2) 
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP1)
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP2) 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $adrgName -Name $firstDCName
Restart-AzVM -ResourceGroupName $adrgName -Name $secondDCName
```

請注意，我們會重新啟動兩個網域控制站，所以這兩個控制站不會像 DNS 伺服器一樣，透過內部部署 DNS 伺服器來設定。因為這兩個控制站本身就是 DNS 伺服器，當系統提示其作為網域控制站時，這些控制站會自動透過內部部署 DNS 伺服器設定為 DNS 轉寄站。
  
下一步，我們需要建立一個 Active Directory 複寫站台，以確保 Azure 的虛擬網路中的伺服器會使用本機網域控制站。請使用網域管理員帳戶與其中一個網域控制站連線，並從管理員層級的 Windows PowerShell 提示執行下列命令：
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a>設定目錄同步處理伺服器

使用您選擇的遠端桌面用戶端，建立與目錄同步處理伺服器虛擬機器的遠端桌面連線。 請使用其內部網路 DNS 或本機管理員帳戶的電腦名稱和認證。
  
接下來，在 Windows PowerShell 提示字元，使用下列命令將其加入適當的 AD DS 網域。
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

以下是成功完成此階段的設定結果 (包含電腦名稱的預留位置)。
  
**階段2： Azure 中高可用性同盟驗證基礎結構的網域控制站及目錄同步處理伺服器**

![Azure 中具有網域控制站之高可用性 Microsoft 365 同盟驗證基礎結構的階段2](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a>下一步

使用 [階段3：設定 AD FS 伺服器](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) 以繼續設定此工作負載。
  
## <a name="see-also"></a>另請參閱

[Azure 中的 Microsoft 365 高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Microsoft 365 開發/測試環境的同盟身分識別](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365 解決方案與架構中心](../solutions/solution-architecture-center.md)


