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
description: 摘要：在 Microsoft Azure 中為 Microsoft 365 的高可用性同盟驗證設定 web 應用程式 proxy 伺服器。
ms.openlocfilehash: 95d73d05f2eef087e606df14db180b24c69d5932
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929069"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a><span data-ttu-id="a10a8-103">高可用性同盟驗證階段 4：設定 Web 應用程式 Proxy</span><span class="sxs-lookup"><span data-stu-id="a10a8-103">High availability federated authentication Phase 4: Configure web application proxies</span></span>

<span data-ttu-id="a10a8-104">在此階段中，在 Azure 基礎結構服務中部署 Microsoft 365 同盟驗證的高可用性時，您會建立內部負載平衡器和兩部 AD FS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a10a8-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="a10a8-105">您必須先完成此階段，再移至 [階段5：設定 Microsoft 365 的同盟驗證](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)。</span><span class="sxs-lookup"><span data-stu-id="a10a8-105">You must complete this phase before moving on to [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="a10a8-106">請參閱 [在 Azure 中部署 Microsoft 365 的高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) ，以瞭解所有階段。</span><span class="sxs-lookup"><span data-stu-id="a10a8-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a><span data-ttu-id="a10a8-107">在 Azure 中建立網際網路對應負載平衡器</span><span class="sxs-lookup"><span data-stu-id="a10a8-107">Create the Internet-facing load balancer in Azure</span></span>

<span data-ttu-id="a10a8-108">您必須先建立網際網路對應負載平衡器，讓 Azure 將從網際網路傳入的用戶端驗證流量分散到兩個 Web 應用程式 Proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a10a8-108">You must create an Internet-facing load balancer so that Azure distributes the incoming client authentication traffic from the Internet evenly among the two web application proxy servers.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a10a8-109">[!附註] 下列命令集會使用最新版的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a10a8-109">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="a10a8-110">請參閱 [Azure PowerShell 入門](/powershell/azure/get-started-azureps)。</span><span class="sxs-lookup"><span data-stu-id="a10a8-110">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="a10a8-111">當您已提供位置和資源群組的值時，在 Azure PowerShell 命令提示字元上或 PowerShell ISE 中執行結果區塊。</span><span class="sxs-lookup"><span data-stu-id="a10a8-111">When you have supplied location and resource group values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="a10a8-112">若要根據您的自訂設定來產生現成 PowerShell 命令區塊，請使用此 [Microsoft Excel 配置活頁簿](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="a10a8-112">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

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

<span data-ttu-id="a10a8-113">若要顯示指派到您網際網路對應負載平衡器的公用 IP 位址，請在本機電腦上的 Azure PowerShell 命令提示字元上執行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a10a8-113">To display the public IP address assigned to your Internet-facing load balancer, run these commands at the Azure PowerShell command prompt on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a><span data-ttu-id="a10a8-114">決定您的同盟服務 FQDN 並建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="a10a8-114">Determine your federation service FQDN and create DNS records</span></span>

<span data-ttu-id="a10a8-115">您需要決定 DNS 名稱以在網際網路上識別您的同盟伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="a10a8-115">You need to determine the DNS name to identify your federation service name on the Internet.</span></span> <span data-ttu-id="a10a8-116">Azure AD Connect 會以此名稱在階段5中設定 Microsoft 365，這會成為 Microsoft 365 傳送至連線用戶端以取得安全性權杖之 URL 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a10a8-116">Azure AD Connect will configure Microsoft 365 with this name in Phase 5, which will become part of the URL that Microsoft 365 sends to connecting clients to get a security token.</span></span> <span data-ttu-id="a10a8-117">例如 fs.contoso.com (fs 表示同盟服務)。</span><span class="sxs-lookup"><span data-stu-id="a10a8-117">An example is fs.contoso.com (fs stands for federation service).</span></span>
  
<span data-ttu-id="a10a8-118">一旦您有了同盟服務 FQDN，請針對同盟服務 FDQN 建立公用 DNS 網域 A 記錄，這會解析為 Azure 網際網路對應負載平衡器的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a10a8-118">Once you have your federation service FDQN, create a public DNS domain A record for the federation service FDQN that resolves to the public IP address of the Azure Internet-facing load balancer.</span></span>
  
|<span data-ttu-id="a10a8-119">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a10a8-119">**Name**</span></span>|<span data-ttu-id="a10a8-120">**類型**</span><span class="sxs-lookup"><span data-stu-id="a10a8-120">**Type**</span></span>|<span data-ttu-id="a10a8-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a10a8-121">**TTL**</span></span>|<span data-ttu-id="a10a8-122">**值**</span><span class="sxs-lookup"><span data-stu-id="a10a8-122">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a10a8-123">同盟服務 FDQN</span><span class="sxs-lookup"><span data-stu-id="a10a8-123">federation service FDQN</span></span>  <br/> |<span data-ttu-id="a10a8-124">A</span><span class="sxs-lookup"><span data-stu-id="a10a8-124">A</span></span>  <br/> |<span data-ttu-id="a10a8-125">3600</span><span class="sxs-lookup"><span data-stu-id="a10a8-125">3600</span></span>  <br/> |<span data-ttu-id="a10a8-126">Azure 網際網路對應負載平衡器的公用 IP 位址 (透過上一節中的 **Write-Host** 命令顯示)</span><span class="sxs-lookup"><span data-stu-id="a10a8-126">public IP address of the Azure Internet-facing load balancer (displayed by the **Write-Host** command in the previous section)</span></span> <br/> |
   
<span data-ttu-id="a10a8-127">範例如下：</span><span class="sxs-lookup"><span data-stu-id="a10a8-127">Here is an example:</span></span>
  
|<span data-ttu-id="a10a8-128">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a10a8-128">**Name**</span></span>|<span data-ttu-id="a10a8-129">**類型**</span><span class="sxs-lookup"><span data-stu-id="a10a8-129">**Type**</span></span>|<span data-ttu-id="a10a8-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a10a8-130">**TTL**</span></span>|<span data-ttu-id="a10a8-131">**值**</span><span class="sxs-lookup"><span data-stu-id="a10a8-131">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a10a8-132">fs.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a10a8-132">fs.contoso.com</span></span>  <br/> |<span data-ttu-id="a10a8-133">A</span><span class="sxs-lookup"><span data-stu-id="a10a8-133">A</span></span>  <br/> |<span data-ttu-id="a10a8-134">3600</span><span class="sxs-lookup"><span data-stu-id="a10a8-134">3600</span></span>  <br/> |<span data-ttu-id="a10a8-135">131.107.249.117</span><span class="sxs-lookup"><span data-stu-id="a10a8-135">131.107.249.117</span></span>  <br/> |
   
<span data-ttu-id="a10a8-136">下一步，將 DNS 位址記錄新增至您的組織私人 DNS 命名空間，此命名空間會將您的同盟服務 FQDN 解析為 AD FS 伺服器內部負載平衡器的私人 IP 位址 (表格 I、項目 4、值欄)。</span><span class="sxs-lookup"><span data-stu-id="a10a8-136">Next, add a DNS address record to your organization's private DNS namespace that resolves your federation service FQDN to the private IP address assigned to the internal load balancer for the AD FS servers (Table I, item 4, Value column).</span></span>
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a><span data-ttu-id="a10a8-137">在 Azure 中建立 Web 應用程式 Proxy 伺服器虛擬機器</span><span class="sxs-lookup"><span data-stu-id="a10a8-137">Create the web application proxy server virtual machines in Azure</span></span>

<span data-ttu-id="a10a8-138">您可以使用下列 Azure PowerShell 命令的區塊，建立兩部 Web 應用程式 Proxy 伺服器的虛擬機器。 </span><span class="sxs-lookup"><span data-stu-id="a10a8-138">Use the following block of Azure PowerShell commands to create the virtual machines for the two web application proxy servers.</span></span> 
  
<span data-ttu-id="a10a8-139">請注意，下列 Azure PowerShell 命令集會使用下表中的值︰</span><span class="sxs-lookup"><span data-stu-id="a10a8-139">Note that the following Azure PowerShell command sets use values from the following tables:</span></span>
  
- <span data-ttu-id="a10a8-140">表格 M，適用於虛擬機器</span><span class="sxs-lookup"><span data-stu-id="a10a8-140">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="a10a8-141">表格 R，適用於資源群組</span><span class="sxs-lookup"><span data-stu-id="a10a8-141">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="a10a8-142">表格 V，適用於虛擬網路設定</span><span class="sxs-lookup"><span data-stu-id="a10a8-142">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="a10a8-143">表格 S，適用於子網路</span><span class="sxs-lookup"><span data-stu-id="a10a8-143">Table S, for your subnets</span></span>
    
- <span data-ttu-id="a10a8-144">表格 I，適用於靜態 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a10a8-144">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="a10a8-145">表格 A，適用於可用性設定組</span><span class="sxs-lookup"><span data-stu-id="a10a8-145">Table A, for your availability sets</span></span>
    
<span data-ttu-id="a10a8-146">請記得您在 [階段2：設定網域控制站](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) 和表格 R、V、S、I 及 A [階段1： configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md)中定義的表 M。</span><span class="sxs-lookup"><span data-stu-id="a10a8-146">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
<span data-ttu-id="a10a8-147">當您已提供所有適當的值時，在 Azure PowerShell 命令提示字元上或 PowerShell ISE 中執行結果區塊。</span><span class="sxs-lookup"><span data-stu-id="a10a8-147">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
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
> <span data-ttu-id="a10a8-p104">由於這些虛擬機器是用於內部網路應用程式，系統並不會指派公用 IP 位址或 DNS 網域名稱標籤給它們，它們也不會公開在網際網路上。不過，這也表示您無法從 Azure 入口網站連線到這些虛擬機器。當您檢視虛擬機器的屬性時，無法使用 **連線** 選項。請使用遠端桌面連線附屬應用程式或另一個遠端桌面工具，透過使用虛擬機器的私人 IP 位址或內部網路 DNS 名稱，以及本機管理員帳戶的認證來與其連線。</span><span class="sxs-lookup"><span data-stu-id="a10a8-p104">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet. However, this also means that you cannot connect to them from the Azure portal. The **Connect** option is unavailable when you view the properties of the virtual machine. Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="a10a8-152">以下是成功完成此階段的設定結果 (包含電腦名稱的預留位置)。</span><span class="sxs-lookup"><span data-stu-id="a10a8-152">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="a10a8-153">**階段 4：Azure 中高可用性同盟驗證基礎結構的網際網路對應負載平衡器和 Web 應用程式 Proxy 伺服器**</span><span class="sxs-lookup"><span data-stu-id="a10a8-153">**Phase 4: The Internet-facing load balancer and web application proxy servers for your high availability federated authentication infrastructure in Azure**</span></span>

![Azure 中具有 web 應用程式 proxy 伺服器之高可用性 Microsoft 365 同盟驗證基礎結構的階段4](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a><span data-ttu-id="a10a8-155">後續步驟</span><span class="sxs-lookup"><span data-stu-id="a10a8-155">Next step</span></span>

<span data-ttu-id="a10a8-156">使用 [階段5：設定 Microsoft 365 的同盟驗證](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) ，以繼續設定此工作負載。</span><span class="sxs-lookup"><span data-stu-id="a10a8-156">Use [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a10a8-157">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a10a8-157">See Also</span></span>

[<span data-ttu-id="a10a8-158">Azure 中的 Microsoft 365 高可用性同盟驗證</span><span class="sxs-lookup"><span data-stu-id="a10a8-158">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="a10a8-159">Microsoft 365 開發/測試環境的同盟身分識別</span><span class="sxs-lookup"><span data-stu-id="a10a8-159">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="a10a8-160">Microsoft 365 解決方案與架構中心</span><span class="sxs-lookup"><span data-stu-id="a10a8-160">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)