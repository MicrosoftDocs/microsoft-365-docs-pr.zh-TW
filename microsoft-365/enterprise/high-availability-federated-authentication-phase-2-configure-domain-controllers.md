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
description: 摘要：設定 Microsoft Azure 中 Microsoft 365 的高可用性同盟驗證的網域控制站及目錄同步處理伺服器。
ms.openlocfilehash: 751d332ce5f5606fe5f833182f002a1f4b6f29ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909807"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a><span data-ttu-id="40094-103">高可用性同盟驗證階段 2：設定網域控制站</span><span class="sxs-lookup"><span data-stu-id="40094-103">High availability federated authentication Phase 2: Configure domain controllers</span></span>

<span data-ttu-id="40094-104">在此階段，針對 azure 基礎結構服務中 Microsoft 365 同盟驗證部署高可用性時，您會在 azure 虛擬網路中設定兩個網域控制站與目錄同步處理伺服器。</span><span class="sxs-lookup"><span data-stu-id="40094-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you configure two domain controllers and the directory synchronization server in the Azure virtual network.</span></span> <span data-ttu-id="40094-105">然後用戶端 Web 驗證要求即可在 Azure 虛擬網路中驗證，而非透過站台對站台的 VPN 連線來傳送驗證流量至內部部署網路。</span><span class="sxs-lookup"><span data-stu-id="40094-105">Client web requests for authentication can then be authenticated in the Azure virtual network, rather than sending that authentication traffic across the site-to-site VPN connection to your on-premises network.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40094-106">active directory Federation Services (ad FS) 無法使用 Azure Active Directory (Azure AD) 取代 Active Directory 網域服務 (AD DS) 網域控制站。</span><span class="sxs-lookup"><span data-stu-id="40094-106">Active Directory Federation Services (AD FS) cannot use Azure Active Directory (Azure AD) as a substitute for Active Directory Domain Services (AD DS) domain controllers.</span></span> 
  
<span data-ttu-id="40094-107">您必須先完成此階段，再移至 [階段3：設定 AD FS 伺服器](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="40094-107">You must complete this phase before moving on to [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="40094-108">如需所有階段，請參閱[在 Azure 中部署 Microsoft 365 的高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)。</span><span class="sxs-lookup"><span data-stu-id="40094-108">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a><span data-ttu-id="40094-109">在 Azure 中建立網域控制站虛擬機器</span><span class="sxs-lookup"><span data-stu-id="40094-109">Create the domain controller virtual machines in Azure</span></span>

<span data-ttu-id="40094-110">首先，您必須填寫表格 M 的 **虛擬機器名稱** 欄，然後依需求在 **大小下限** 欄中修改虛擬機器大小。</span><span class="sxs-lookup"><span data-stu-id="40094-110">First, you need to fill out the **Virtual machine name** column of Table M and modify virtual machine sizes as needed in the **Minimum size** column.</span></span>
  
|<span data-ttu-id="40094-111">**項目**</span><span class="sxs-lookup"><span data-stu-id="40094-111">**Item**</span></span>|<span data-ttu-id="40094-112">**虛擬機器名稱**</span><span class="sxs-lookup"><span data-stu-id="40094-112">**Virtual machine name**</span></span>|<span data-ttu-id="40094-113">**圖庫影像**</span><span class="sxs-lookup"><span data-stu-id="40094-113">**Gallery image**</span></span>|<span data-ttu-id="40094-114">**儲存類型**</span><span class="sxs-lookup"><span data-stu-id="40094-114">**Storage type**</span></span>|<span data-ttu-id="40094-115">**大小下限**</span><span class="sxs-lookup"><span data-stu-id="40094-115">**Minimum size**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="40094-116">1.</span><span class="sxs-lookup"><span data-stu-id="40094-116">1.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png) <span data-ttu-id="40094-118"> (第一個網域控制站，範例 DC1)</span><span class="sxs-lookup"><span data-stu-id="40094-118">(first domain controller, example DC1)</span></span>  <br/> |<span data-ttu-id="40094-119">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="40094-119">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="40094-120">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="40094-120">Standard_LRS</span></span>  <br/> |<span data-ttu-id="40094-121">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="40094-121">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="40094-122">2.</span><span class="sxs-lookup"><span data-stu-id="40094-122">2.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png) <span data-ttu-id="40094-124"> (第二個網域控制站，範例 DC2)</span><span class="sxs-lookup"><span data-stu-id="40094-124">(second domain controller, example DC2)</span></span>  <br/> |<span data-ttu-id="40094-125">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="40094-125">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="40094-126">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="40094-126">Standard_LRS</span></span>  <br/> |<span data-ttu-id="40094-127">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="40094-127">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="40094-128">3.</span><span class="sxs-lookup"><span data-stu-id="40094-128">3.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png) <span data-ttu-id="40094-130"> (目錄同步處理伺服器，範例 DS1) </span><span class="sxs-lookup"><span data-stu-id="40094-130">(directory synchronization server, example DS1)</span></span>  <br/> |<span data-ttu-id="40094-131">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="40094-131">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="40094-132">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="40094-132">Standard_LRS</span></span>  <br/> |<span data-ttu-id="40094-133">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="40094-133">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="40094-134">4.</span><span class="sxs-lookup"><span data-stu-id="40094-134">4.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png) <span data-ttu-id="40094-136"> (第一個 AD FS 伺服器，範例 ADFS1) </span><span class="sxs-lookup"><span data-stu-id="40094-136">(first AD FS server, example ADFS1)</span></span>  <br/> |<span data-ttu-id="40094-137">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="40094-137">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="40094-138">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="40094-138">Standard_LRS</span></span>  <br/> |<span data-ttu-id="40094-139">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="40094-139">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="40094-140">5.</span><span class="sxs-lookup"><span data-stu-id="40094-140">5.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png) <span data-ttu-id="40094-142"> (第二個 AD FS 伺服器，範例 ADFS2) </span><span class="sxs-lookup"><span data-stu-id="40094-142">(second AD FS server, example ADFS2)</span></span>  <br/> |<span data-ttu-id="40094-143">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="40094-143">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="40094-144">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="40094-144">Standard_LRS</span></span>  <br/> |<span data-ttu-id="40094-145">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="40094-145">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="40094-146">6.</span><span class="sxs-lookup"><span data-stu-id="40094-146">6.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png) <span data-ttu-id="40094-148"> (第一個 web 應用程式 proxy 伺服器，範例 WEB1) </span><span class="sxs-lookup"><span data-stu-id="40094-148">(first web application proxy server, example WEB1)</span></span>  <br/> |<span data-ttu-id="40094-149">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="40094-149">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="40094-150">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="40094-150">Standard_LRS</span></span>  <br/> |<span data-ttu-id="40094-151">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="40094-151">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="40094-152">7.</span><span class="sxs-lookup"><span data-stu-id="40094-152">7.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png) <span data-ttu-id="40094-154"> (第二個 web 應用程式 proxy 伺服器，範例 WEB2) </span><span class="sxs-lookup"><span data-stu-id="40094-154">(second web application proxy server, example WEB2)</span></span>  <br/> |<span data-ttu-id="40094-155">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="40094-155">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="40094-156">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="40094-156">Standard_LRS</span></span>  <br/> |<span data-ttu-id="40094-157">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="40094-157">Standard_D2</span></span>  <br/> |
   
 <span data-ttu-id="40094-158">**表格 M-Azure 中 Microsoft 365 高可用性同盟驗證的虛擬機器**</span><span class="sxs-lookup"><span data-stu-id="40094-158">**Table M - Virtual machines for the high availability federated authentication for Microsoft 365 in Azure**</span></span>
  
<span data-ttu-id="40094-159">如需虛擬機器大小的完整清單，請參閱[虛擬機器大小](/azure/virtual-machines/virtual-machines-windows-sizes)。</span><span class="sxs-lookup"><span data-stu-id="40094-159">For the complete list of virtual machine sizes, see [Sizes for virtual machines](/azure/virtual-machines/virtual-machines-windows-sizes).</span></span>
  
<span data-ttu-id="40094-160">下列 Azure PowerShell 命令區塊可建立兩個網域控制站的虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="40094-160">The following Azure PowerShell command block creates the virtual machines for the two domain controllers.</span></span> <span data-ttu-id="40094-161">指定變數的值，並移除 \< and > 字元。</span><span class="sxs-lookup"><span data-stu-id="40094-161">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="40094-162">請注意，此 Azure PowerShell 命令區塊會使用下表中的值︰</span><span class="sxs-lookup"><span data-stu-id="40094-162">Note that this Azure PowerShell command block uses values from the following tables:</span></span>
  
- <span data-ttu-id="40094-163">表格 M，適用於虛擬機器</span><span class="sxs-lookup"><span data-stu-id="40094-163">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="40094-164">表格 R，適用於資源群組</span><span class="sxs-lookup"><span data-stu-id="40094-164">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="40094-165">表格 V，適用於虛擬網路設定</span><span class="sxs-lookup"><span data-stu-id="40094-165">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="40094-166">表格 S，適用於子網路</span><span class="sxs-lookup"><span data-stu-id="40094-166">Table S, for your subnets</span></span>
    
- <span data-ttu-id="40094-167">表格 I，適用於靜態 IP 位址</span><span class="sxs-lookup"><span data-stu-id="40094-167">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="40094-168">表格 A，適用於可用性設定組</span><span class="sxs-lookup"><span data-stu-id="40094-168">Table A, for your availability sets</span></span>
    
<span data-ttu-id="40094-169">請記得您在 [階段1： Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md)中定義的表格 R、V、S、I 和 A。</span><span class="sxs-lookup"><span data-stu-id="40094-169">Recall that you defined Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="40094-170">[!附註] 下列命令集會使用最新版的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="40094-170">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="40094-171">請參閱[開始使用 Azure PowerShell](/powershell/azure/get-started-azureps)。</span><span class="sxs-lookup"><span data-stu-id="40094-171">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="40094-172">當您已經提供所有正確的值時，在 Azure PowerShell 提示中或本機電腦的 PowerShell 整合式指令碼環境 (ISE) 中執行結果區塊。</span><span class="sxs-lookup"><span data-stu-id="40094-172">When you have supplied all the correct values, run the resulting block at the Azure PowerShell prompt or in the PowerShell Integrated Script Environment (ISE) on your local computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="40094-173">若要根據您的自訂設定產生現成 PowerShell 命令區塊，請使用此 Microsoft Excel 設定活頁[簿](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="40094-173">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

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
> <span data-ttu-id="40094-p105">由於這些虛擬機器是用於內部網路應用程式，並不會指派公用 IP 位址或 DNS 網域名稱標籤，也不會曝露在網際網路上。不過，這也表示您無法透過 Azure 入口網站與虛擬機器連線。當您檢視虛擬機器的屬性時，無法使用 **連線** 選項。請使用遠端桌面連線附屬應用程式或另一個遠端桌面工具，透過使用其私人 IP 位址或內部網路 DNS 名稱來與虛擬機器連線。</span><span class="sxs-lookup"><span data-stu-id="40094-p105">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet. However, this also means that you cannot connect to them from the Azure portal. The **Connect** option is unavailable when you view the properties of the virtual machine. Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
## <a name="configure-the-first-domain-controller"></a><span data-ttu-id="40094-178">設定第一個網域控制站</span><span class="sxs-lookup"><span data-stu-id="40094-178">Configure the first domain controller</span></span>

<span data-ttu-id="40094-p106">使用您所選的遠端桌面用戶端，建立第一個網域控制站虛擬機器的遠端桌面連線。請使用其內部網路 DNS 或本機管理員帳戶的電腦名稱和認證。</span><span class="sxs-lookup"><span data-stu-id="40094-p106">Use the remote desktop client of your choice and create a remote desktop connection to the first domain controller virtual machine. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="40094-181">接下來，使用 **第一個網域控制站虛擬機器上** 的 Windows PowerShell 命令提示字元將額外的資料磁片新增至第一個網域控制站：</span><span class="sxs-lookup"><span data-stu-id="40094-181">Next, add the extra data disk to the first domain controller with this command from a Windows PowerShell command prompt **on the first domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="40094-182">下一步，使用 **ping** 命令來對組織網路上的資源名稱和 IP 位址執行 Ping，以測試第一個網域控制站對組織網路上位置的連線狀況。</span><span class="sxs-lookup"><span data-stu-id="40094-182">Next, test the first domain controller's connectivity to locations on your organization network by using the **ping** command to ping names and IP addresses of resources on your organization network.</span></span>
  
<span data-ttu-id="40094-p107">此程序可確保 DNS 名稱解析運作正常 (虛擬機器已透過內部部署 DNS 伺服器正確設定)，而且封包可在跨單位虛擬網路間傳送。如果此基本測試失敗，請連絡您的 IT 部門，以針對 DNS 名稱解析和封包傳遞問題進行移難排解。</span><span class="sxs-lookup"><span data-stu-id="40094-p107">This procedure ensures that DNS name resolution is working correctly (that the virtual machine is correctly configured with on-premises DNS servers) and that packets can be sent to and from the cross-premises virtual network. If this basic test fails, contact your IT department to troubleshoot the DNS name resolution and packet delivery issues.</span></span>
  
<span data-ttu-id="40094-185">下一步，從第一個網域控制站上的 Windows PowerShell 命令提示字元，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="40094-185">Next, from the Windows PowerShell command prompt on the first domain controller, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

<span data-ttu-id="40094-p108">系統會提示您提供網域管理員帳戶的認證。電腦將會重新啟動。</span><span class="sxs-lookup"><span data-stu-id="40094-p108">You will be prompted to supply the credentials of a domain administrator account. The computer will restart.</span></span>
  
## <a name="configure-the-second-domain-controller"></a><span data-ttu-id="40094-188">設定第二個網域控制站</span><span class="sxs-lookup"><span data-stu-id="40094-188">Configure the second domain controller</span></span>

<span data-ttu-id="40094-p109">使用您所選的遠端桌面用戶端，建立第二個網域控制站虛擬機器的遠端桌面連線。請使用其內部網路 DNS 或本機管理員帳戶的電腦名稱和認證。</span><span class="sxs-lookup"><span data-stu-id="40094-p109">Use the remote desktop client of your choice and create a remote desktop connection to the second domain controller virtual machine. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="40094-191">接下來，您需要 **在第二個網域控制站虛擬機器上** 的 Windows PowerShell 命令提示字元中，使用此命令將額外的資料磁片新增至第二個網域控制站：</span><span class="sxs-lookup"><span data-stu-id="40094-191">Next, you need to add the extra data disk to the second domain controller with this command from a Windows PowerShell command prompt **on the second domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="40094-192">接著，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="40094-192">Next, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

<span data-ttu-id="40094-p110">系統會提示您提供網域管理員帳戶的認證。電腦將會重新啟動。</span><span class="sxs-lookup"><span data-stu-id="40094-p110">You will be prompted to supply the credentials of a domain administrator account. The computer will restart.</span></span>
  
<span data-ttu-id="40094-195">下一步，您需要更新虛擬網路的 DNS 伺服器，如此一來，此 Azure 會指派兩個新的網域控制站 IP 位址給虛擬機器，以便使用虛擬機器的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="40094-195">Next, you need to update the DNS servers for your virtual network so that Azure assigns virtual machines the IP addresses of the two new domain controllers to use as their DNS servers.</span></span> <span data-ttu-id="40094-196">填寫變數，然後從本機電腦上的 Windows PowerShell 命令提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="40094-196">Fill in the variables and then run these commands from a Windows PowerShell command prompt on your local computer:</span></span>
  
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

<span data-ttu-id="40094-p112">請注意，我們會重新啟動兩個網域控制站，所以這兩個控制站不會像 DNS 伺服器一樣，透過內部部署 DNS 伺服器來設定。因為這兩個控制站本身就是 DNS 伺服器，當系統提示其作為網域控制站時，這些控制站會自動透過內部部署 DNS 伺服器設定為 DNS 轉寄站。</span><span class="sxs-lookup"><span data-stu-id="40094-p112">Note that we restart the two domain controllers so that they are not configured with the on-premises DNS servers as DNS servers. Because they are both DNS servers themselves, they were automatically configured with the on-premises DNS servers as DNS forwarders when they were promoted to domain controllers.</span></span>
  
<span data-ttu-id="40094-p113">下一步，我們需要建立一個 Active Directory 複寫站台，以確保 Azure 的虛擬網路中的伺服器會使用本機網域控制站。請使用網域管理員帳戶與其中一個網域控制站連線，並從管理員層級的 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="40094-p113">Next, we need to create an Active Directory replication site to ensure that servers in the Azure virtual network use the local domain controllers. Connect to either domain controller with a domain administrator account and run the following commands from an administrator-level Windows PowerShell prompt:</span></span>
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a><span data-ttu-id="40094-201">設定目錄同步處理伺服器</span><span class="sxs-lookup"><span data-stu-id="40094-201">Configure the directory synchronization server</span></span>

<span data-ttu-id="40094-202">使用您選擇的遠端桌面用戶端，建立與目錄同步處理伺服器虛擬機器的遠端桌面連線。</span><span class="sxs-lookup"><span data-stu-id="40094-202">Use the remote desktop client of your choice and create a remote desktop connection to the directory synchronization server virtual machine.</span></span> <span data-ttu-id="40094-203">請使用其內部網路 DNS 或本機管理員帳戶的電腦名稱和認證。</span><span class="sxs-lookup"><span data-stu-id="40094-203">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="40094-204">接下來，在 Windows PowerShell 提示字元處，使用下列命令將其加入適當的 AD DS 網域。</span><span class="sxs-lookup"><span data-stu-id="40094-204">Next, join it to the appropriate AD DS domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="40094-205">以下是成功完成此階段的設定結果 (包含電腦名稱的預留位置)。</span><span class="sxs-lookup"><span data-stu-id="40094-205">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="40094-206">**階段2： Azure 中高可用性同盟驗證基礎結構的網域控制站及目錄同步處理伺服器**</span><span class="sxs-lookup"><span data-stu-id="40094-206">**Phase 2: The domain controllers and directory synchronization server for your high availability federated authentication infrastructure in Azure**</span></span>

![Azure 中具有網域控制站的高可用性 Microsoft 365 同盟驗證基礎結構的階段2](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a><span data-ttu-id="40094-208">下一步</span><span class="sxs-lookup"><span data-stu-id="40094-208">Next step</span></span>

<span data-ttu-id="40094-209">使用 [階段3：設定 AD FS 伺服器](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) 以繼續設定此工作負載。</span><span class="sxs-lookup"><span data-stu-id="40094-209">Use [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="40094-210">另請參閱</span><span class="sxs-lookup"><span data-stu-id="40094-210">See Also</span></span>

[<span data-ttu-id="40094-211">Azure 中的 Microsoft 365 高可用性同盟驗證</span><span class="sxs-lookup"><span data-stu-id="40094-211">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="40094-212">Microsoft 365 開發/測試環境的同盟身分識別</span><span class="sxs-lookup"><span data-stu-id="40094-212">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="40094-213">Microsoft 365 解決方案與架構中心</span><span class="sxs-lookup"><span data-stu-id="40094-213">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)