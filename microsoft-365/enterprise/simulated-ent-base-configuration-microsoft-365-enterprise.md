---
title: Microsoft 365 模擬企業基本設定
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 使用此「測試實驗室指南」建立 Microsoft 365 企業版的模擬企業測試環境。
ms.openlocfilehash: 486429bf9e1c0a88c9beb01a092f968256c1fa77
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818492"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="5b812-103">模擬企業基本設定</span><span class="sxs-lookup"><span data-stu-id="5b812-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="5b812-104">*這個測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版兩種測試環境。*</span><span class="sxs-lookup"><span data-stu-id="5b812-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="5b812-105">本文提供逐步指示來為 Microsoft 365 企業版建立簡化的環境，其中包含：</span><span class="sxs-lookup"><span data-stu-id="5b812-105">This article provides you with step-by-step instructions to create a simplified environment for Microsoft 365 Enterprise that includes:</span></span>

- <span data-ttu-id="5b812-106">Microsoft 365 E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="5b812-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="5b812-107">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路上的三部虛擬機器 (DC1、APP1 及 CLIENT1) 組成。</span><span class="sxs-lookup"><span data-stu-id="5b812-107">A simplified organization intranet connected to the Internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![模擬企業基本設定](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="5b812-109">您可以利用額外的[測試實驗室指南](m365-enterprise-test-lab-guides.md)或靠您自己，使用所產生的環境來測試 [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise)的功能。</span><span class="sxs-lookup"><span data-stu-id="5b812-109">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="5b812-111">如需 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應，請移至 [Microsoft 365 企業測試實驗室指南堆疊](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="5b812-111">Go to [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="5b812-112">階段 1：建立模擬的內部網路</span><span class="sxs-lookup"><span data-stu-id="5b812-112">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="5b812-113">在這個階段，您可以在 Azure 基礎結構服務中建立模擬內部網路，其中包含 Active Directory Domain Services (AD DS) 網域控制站、應用程式伺服器和用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="5b812-113">In this phase, you build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span> 

<span data-ttu-id="5b812-114">您可以在其他 [Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)中使用這些電腦，以設定並示範混合式身分識別及其他功能。</span><span class="sxs-lookup"><span data-stu-id="5b812-114">You'll use these computers in additional [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="5b812-115">方法 1：使用 Azure Resource Manager 範本建立模擬內部網路</span><span class="sxs-lookup"><span data-stu-id="5b812-115">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="5b812-116">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet.</span><span class="sxs-lookup"><span data-stu-id="5b812-116">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet.</span></span> <span data-ttu-id="5b812-117">ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span><span class="sxs-lookup"><span data-stu-id="5b812-117">ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="5b812-118">部署範本之前，請先閱讀[範本讀我檔案頁面](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)並準備好下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5b812-118">Prior to deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="5b812-119">The public DNS domain name of your test environment (testlab.\<your public domain>).</span><span class="sxs-lookup"><span data-stu-id="5b812-119">The public DNS domain name of your test environment (testlab.\<your public domain>).</span></span> <span data-ttu-id="5b812-120">You'll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span><span class="sxs-lookup"><span data-stu-id="5b812-120">You'll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span></span>
- <span data-ttu-id="5b812-121">A DNS label prefix for the URLs of the public IP addresses of your virtual machines.</span><span class="sxs-lookup"><span data-stu-id="5b812-121">A DNS label prefix for the URLs of the public IP addresses of your virtual machines.</span></span> <span data-ttu-id="5b812-122">You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span><span class="sxs-lookup"><span data-stu-id="5b812-122">You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="5b812-123">閱讀指示之後，請在[範本讀我檔案頁面](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)上按一下 [部署至 Azure]\*\*\*\* 以開始使用。</span><span class="sxs-lookup"><span data-stu-id="5b812-123">After reading through the instructions, click **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="5b812-124">ARM 範本所建立的模擬內部網路需要 Azure 付費訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="5b812-124">The simulated intranet built by the ARM template requires a paid Azure subscription.</span></span>
>

<span data-ttu-id="5b812-125">範本完成後，您的設定如下。</span><span class="sxs-lookup"><span data-stu-id="5b812-125">Here is your configuration after the template is complete.</span></span>

![Azure 基礎結構服務中的模擬內部網路](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="5b812-127">方法 2：使用 Azure PowerShell 建立模擬內部網路</span><span class="sxs-lookup"><span data-stu-id="5b812-127">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="5b812-128">在這個方法中，您使用 Windows PowerShell 和 Azure PowerShell 模組建置網路基礎結構、虛擬機器及其設定。</span><span class="sxs-lookup"><span data-stu-id="5b812-128">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="5b812-129">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b812-129">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell.</span></span> <span data-ttu-id="5b812-130">You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span><span class="sxs-lookup"><span data-stu-id="5b812-130">You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="5b812-131">步驟 1：建立 DC1</span><span class="sxs-lookup"><span data-stu-id="5b812-131">Step 1: Create DC1</span></span>

<span data-ttu-id="5b812-132">在這個步驟，我們會建立 Azure 虛擬網路並新增 DC1 (這部虛擬機器是 AD DS 網域的網域控制站)。</span><span class="sxs-lookup"><span data-stu-id="5b812-132">In this step, we create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="5b812-133">首先，在本機電腦上啟動 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="5b812-133">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b812-134">The following command sets use the latest version of Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b812-134">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="5b812-135">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="5b812-135">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="5b812-136">使用下列命令登入您的 Azure 帳戶。</span><span class="sxs-lookup"><span data-stu-id="5b812-136">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="5b812-137">使用下列命令取得訂用帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="5b812-137">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="5b812-138">Set your Azure subscription.</span><span class="sxs-lookup"><span data-stu-id="5b812-138">Set your Azure subscription.</span></span> <span data-ttu-id="5b812-139">Replace everything within the quotes, including the < and > characters, with the correct name.</span><span class="sxs-lookup"><span data-stu-id="5b812-139">Replace everything within the quotes, including the < and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="5b812-140">Next, create a new resource group for your simulated enterprise test lab.</span><span class="sxs-lookup"><span data-stu-id="5b812-140">Next, create a new resource group for your simulated enterprise test lab.</span></span> <span data-ttu-id="5b812-141">To determine a unique resource group name, use this command to list your existing resource groups.</span><span class="sxs-lookup"><span data-stu-id="5b812-141">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="5b812-142">Create your new resource group with these commands.</span><span class="sxs-lookup"><span data-stu-id="5b812-142">Create your new resource group with these commands.</span></span> <span data-ttu-id="5b812-143">Replace everything within the quotes, including the < and > characters, with the correct names.</span><span class="sxs-lookup"><span data-stu-id="5b812-143">Replace everything within the quotes, including the < and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="5b812-144">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group.</span><span class="sxs-lookup"><span data-stu-id="5b812-144">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group.</span></span> <span data-ttu-id="5b812-145">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span><span class="sxs-lookup"><span data-stu-id="5b812-145">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="5b812-146">接下來，您要建立 DC1 虛擬機器，並將它設定為 **testlab**\<your public domain>的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="5b812-146">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain></span></span> <span data-ttu-id="5b812-147">AD DS 網域和 TestLab 虛擬網路虛擬機器的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="5b812-147">AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="5b812-148">例如，若您的公用網域名稱為 **<span>contoso</span>.com**，則 DC1 虛擬機器會是 **<span>testlab</span>.contoso.com** 網域的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="5b812-148">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="5b812-149">若要建立 DC1 的 Azure 虛擬機器，請填入您的資源群組，並在本機電腦上的 PowerShell 命令提示字元執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="5b812-149">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="5b812-150">You will be prompted for a user name and password for the local administrator account on DC1.</span><span class="sxs-lookup"><span data-stu-id="5b812-150">You will be prompted for a user name and password for the local administrator account on DC1.</span></span> <span data-ttu-id="5b812-151">Use a strong password and record both the name and password in a secure location.</span><span class="sxs-lookup"><span data-stu-id="5b812-151">Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="5b812-152">接下來，連線到 DC1 虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="5b812-152">Next, connect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="5b812-153">在 [Azure 入口網站](https://portal.azure.com)中，按一下 **[資源群組] >** [新的資源群組名稱] **> [DC1] > [連線]**。</span><span class="sxs-lookup"><span data-stu-id="5b812-153">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [the name of your new resource group] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="5b812-154">In the open pane, click **Download RDP file**.</span><span class="sxs-lookup"><span data-stu-id="5b812-154">In the open pane, click **Download RDP file**.</span></span> <span data-ttu-id="5b812-155">Open the DC1.rdp file that is downloaded, and then click **Connect**.</span><span class="sxs-lookup"><span data-stu-id="5b812-155">Open the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="5b812-156">指定 DC1 本機系統管理員帳戶名稱：</span><span class="sxs-lookup"><span data-stu-id="5b812-156">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="5b812-157">對於 Windows 7：</span><span class="sxs-lookup"><span data-stu-id="5b812-157">For Windows 7:</span></span>
    
     <span data-ttu-id="5b812-158">In the **Windows Security** dialog box, click **Use another account**.</span><span class="sxs-lookup"><span data-stu-id="5b812-158">In the **Windows Security** dialog box, click **Use another account**.</span></span> <span data-ttu-id="5b812-159">In **User name**, type **DC1\\**[Local administrator account name].</span><span class="sxs-lookup"><span data-stu-id="5b812-159">In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
   - <span data-ttu-id="5b812-160">對於 Windows 8 或 Windows 10：</span><span class="sxs-lookup"><span data-stu-id="5b812-160">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="5b812-161">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**.</span><span class="sxs-lookup"><span data-stu-id="5b812-161">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**.</span></span> <span data-ttu-id="5b812-162">In **User name**, type **DC1\\**[Local administrator account name].</span><span class="sxs-lookup"><span data-stu-id="5b812-162">In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="5b812-163">在 [密碼]\*\*\*\* 中，輸入本機系統管理員帳戶的密碼，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b812-163">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="5b812-164">出現提示時，按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b812-164">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="5b812-165">接著，使用此命令在 DC1 上系統管理員層級 Windows PowerShell 命令提示字元將額外的資料磁碟新增為新的磁碟區 (磁碟機代號 F:)。</span><span class="sxs-lookup"><span data-stu-id="5b812-165">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="5b812-166">接下來，將 DC1 設定為網域控制站，並將 DNS 伺服器設定為 **testlab。**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="5b812-166">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<your public domain></span></span> <span data-ttu-id="5b812-167">網域。</span><span class="sxs-lookup"><span data-stu-id="5b812-167">domain.</span></span> <span data-ttu-id="5b812-168">指定您的公用功能變數名稱、移除 \< and > 字元，然後在 DC1 的系統管理員層級 Windows PowerShell 命令提示字元中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="5b812-168">Specify your public domain name, remove the \< and > characters, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="5b812-169">You will need to specify a safe mode administrator password.</span><span class="sxs-lookup"><span data-stu-id="5b812-169">You will need to specify a safe mode administrator password.</span></span> <span data-ttu-id="5b812-170">Store this password in a secure location.</span><span class="sxs-lookup"><span data-stu-id="5b812-170">Store this password in a secure location.</span></span>
  
<span data-ttu-id="5b812-171">請注意，這些命令可能需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="5b812-171">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="5b812-172">DC1 重新啟動後，重新連線到 DC1 虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="5b812-172">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="5b812-173">在 [Azure 入口網站](https://portal.azure.com)中，按一下 **[資源群組] >** [您的資源群組名稱] **> [DC1] > [連線]**。</span><span class="sxs-lookup"><span data-stu-id="5b812-173">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [your resource group name] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="5b812-174">執行所下載的 DC1.rdp 檔案，然後按一下 [連線]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b812-174">Run the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="5b812-175">In **Windows Security**, click **Use another account**.</span><span class="sxs-lookup"><span data-stu-id="5b812-175">In **Windows Security**, click **Use another account**.</span></span> <span data-ttu-id="5b812-176">In **User name**, type **TESTLAB\\**[Local administrator account name].</span><span class="sxs-lookup"><span data-stu-id="5b812-176">In **User name**, type **TESTLAB\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="5b812-177">在 [密碼]\*\*\*\* 中，輸入本機系統管理員帳戶的密碼，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b812-177">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="5b812-178">出現提示時，按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b812-178">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="5b812-179">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers.</span><span class="sxs-lookup"><span data-stu-id="5b812-179">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers.</span></span> <span data-ttu-id="5b812-180">Run this command at an administrator-level Windows PowerShell command prompt.</span><span class="sxs-lookup"><span data-stu-id="5b812-180">Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="5b812-181">Note that this command prompts you to supply the User1 account password.</span><span class="sxs-lookup"><span data-stu-id="5b812-181">Note that this command prompts you to supply the User1 account password.</span></span> <span data-ttu-id="5b812-182">Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password.</span><span class="sxs-lookup"><span data-stu-id="5b812-182">Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password.</span></span> <span data-ttu-id="5b812-183">Record the User1 account password and store it in a secured location.</span><span class="sxs-lookup"><span data-stu-id="5b812-183">Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="5b812-184">Next, configure the new User1 account as a domain, enterprise, and schema administrator.</span><span class="sxs-lookup"><span data-stu-id="5b812-184">Next, configure the new User1 account as a domain, enterprise, and schema administrator.</span></span> <span data-ttu-id="5b812-185">Run this command at the administrator-level Windows PowerShell command prompt.</span><span class="sxs-lookup"><span data-stu-id="5b812-185">Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="5b812-186">關閉 DC1 的遠端桌面工作階段，然後使用 TESTLAB\\User1 帳戶重新連線。</span><span class="sxs-lookup"><span data-stu-id="5b812-186">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="5b812-187">接下來，若要允許 Ping 工具的流量，請在系統管理員層級 Windows PowerShell 命令提示字元執行此命令。</span><span class="sxs-lookup"><span data-stu-id="5b812-187">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="5b812-188">這是您目前的設定。</span><span class="sxs-lookup"><span data-stu-id="5b812-188">This is your current configuration.</span></span>
  
![模擬企業基本設定步驟 1](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="5b812-190">步驟 2：設定 APP1</span><span class="sxs-lookup"><span data-stu-id="5b812-190">Step 2: Configure APP1</span></span>

<span data-ttu-id="5b812-191">在這個步驟，您會建立及設定 APP1，這是一開始提供 Web 和檔案共用服務的應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="5b812-191">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="5b812-192">若要建立 APP1 的 Azure 虛擬機器，請填入您的資源群組，並在本機電腦上的命令提示字元執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="5b812-192">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="5b812-193">接下來，使用 APP1 本機系統管理員帳戶名稱和密碼連線到 APP1 虛擬機器，然後開啟 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="5b812-193">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="5b812-194">若要檢查 APP1 和 DC1 之間的名稱解析和網路通訊，請執行 **ping DC1.testlab。**\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="5b812-194">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<your public domain name></span></span> <span data-ttu-id="5b812-195">命令，並確認有四個回復。</span><span class="sxs-lookup"><span data-stu-id="5b812-195">command and verify that there are four replies.</span></span>
  
<span data-ttu-id="5b812-196">接下來在 Windows PowerShell 命令提示字元使用以下命令將 APP1 虛擬機器加入 TESTLAB 網域。</span><span class="sxs-lookup"><span data-stu-id="5b812-196">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="5b812-197">請注意，您必須在執行 **Add-Computer** 命令之後，提供 TESTLAB\\User1 網域帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="5b812-197">Note that you must supply the TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="5b812-198">APP1 重新啟動之後，使用 TESTLAB\\User1 帳戶連線至 APP1，然後開啟系統管理員層級 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="5b812-198">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="5b812-199">接下來，在 APP1 上的系統管理員層級 Windows PowerShell 命令提示字元中使用此命令讓 APP1 成為 Web 伺服器。</span><span class="sxs-lookup"><span data-stu-id="5b812-199">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="5b812-200">接下來，使用這些 PowerShell 命令在 APP1 上的資料夾內建立共用資料夾及文字檔。</span><span class="sxs-lookup"><span data-stu-id="5b812-200">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="5b812-201">這是您目前的設定。</span><span class="sxs-lookup"><span data-stu-id="5b812-201">This is your current configuration.</span></span>
  
![模擬企業基本設定步驟 2](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="5b812-203">步驟 3：設定 CLIENT1</span><span class="sxs-lookup"><span data-stu-id="5b812-203">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="5b812-204">在這個步驟中，建立及設定 CLIENT1，其可在內部網路上作為一般的膝上型電腦、平板電腦或桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="5b812-204">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="5b812-205">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions.</span><span class="sxs-lookup"><span data-stu-id="5b812-205">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions.</span></span> <span data-ttu-id="5b812-206">If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="5b812-206">If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span> 
  
<span data-ttu-id="5b812-207">若要建立 CLIENT1 的 Azure 虛擬機器，請填入您的資源群組，並在本機電腦上的命令提示字元執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="5b812-207">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="5b812-208">接下來，使用 CLIENT1 本機系統管理員帳戶名稱和密碼連線到 CLIENT1 虛擬機器，然後開啟系統管理員層級 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="5b812-208">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="5b812-209">若要檢 CLIENT1 和 DC1 之間的名稱解析和網路通訊，請執行 **ping DC1.testlab。**\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="5b812-209">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<your public domain name></span></span> <span data-ttu-id="5b812-210">命令 Windows PowerShell 命令提示字元，並確認有四個回復。</span><span class="sxs-lookup"><span data-stu-id="5b812-210">command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="5b812-211">接下來在 Windows PowerShell 命令提示字元使用以下命令將 CLIENT1 虛擬機器加入 TESTLAB 網域。</span><span class="sxs-lookup"><span data-stu-id="5b812-211">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="5b812-212">請注意，您必須在執行 **Add-Computer** 命令之後，提供 TESTLAB\\User1 網域帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="5b812-212">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="5b812-213">CLIENT1 重新啟動之後，使用 TESTLAB\\User1 帳戶名稱和密碼連線至 CLIENT1，然後開啟系統管理員層級 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="5b812-213">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="5b812-214">接下來，確認您可以從 CLIENT1 存取 APP1 上的 Web 及檔案共用資源。</span><span class="sxs-lookup"><span data-stu-id="5b812-214">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="5b812-215">在 [伺服器管理員] 的樹狀窗格中，按一下 [本機伺服器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b812-215">In Server Manager, in the tree pane, click **Local Server**.</span></span>
    
2. <span data-ttu-id="5b812-216">在 [CLIENT1 的屬性]\*\*\*\* 中，按一下 [IE 增強式安全性設定]\*\*\*\* 旁邊的 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b812-216">In **Properties for CLIENT1**, click **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="5b812-217">在 [Internet Explorer 增強式安全性設定]\*\*\*\* 中，為 [管理員]\*\*\*\* 和 [使用者]\*\*\*\* 按一下 [關閉]\*\*\*\*，然後按 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b812-217">In **Internet Explorer Enhanced Security Configuration**, click **Off** for **Administrators** and **Users**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="5b812-218">從 [開始] 畫面，按一下 [Internet Explorer]\*\*\*\*，然後按 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b812-218">From the Start screen, click **Internet Explorer**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="5b812-219">在網址列中，輸入 **http<span>://</span>app1.testab**\<your public domain name>**/**，然後按 [ENTER] 鍵。</span><span class="sxs-lookup"><span data-stu-id="5b812-219">In the Address bar, type **http<span>://</span>app1.testab.**\<your public domain name>**/**, and then press ENTER.</span></span> <span data-ttu-id="5b812-220">您應該會看到 APP1 的預設網際網路資訊服務網頁。</span><span class="sxs-lookup"><span data-stu-id="5b812-220">You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="5b812-221">在桌面工作列中，按一下 [檔案總管] 圖示。</span><span class="sxs-lookup"><span data-stu-id="5b812-221">From the desktop taskbar, click the File Explorer icon.</span></span>
    
7. <span data-ttu-id="5b812-222">In the address bar, type **\\\\app1\\Files**, and then press ENTER.</span><span class="sxs-lookup"><span data-stu-id="5b812-222">In the address bar, type **\\\\app1\\Files**, and then press ENTER.</span></span> <span data-ttu-id="5b812-223">You should see a folder window with the contents of the Files shared folder.</span><span class="sxs-lookup"><span data-stu-id="5b812-223">You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="5b812-224">In the **Files** shared folder window, double-click the **Example.txt** file.</span><span class="sxs-lookup"><span data-stu-id="5b812-224">In the **Files** shared folder window, double-click the **Example.txt** file.</span></span> <span data-ttu-id="5b812-225">You should see the contents of the Example.txt file.</span><span class="sxs-lookup"><span data-stu-id="5b812-225">You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="5b812-226">關閉 **example.txt - 記事本**以及 [檔案]\*\*\*\* 共用資料夾視窗。</span><span class="sxs-lookup"><span data-stu-id="5b812-226">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="5b812-227">這是您目前的設定。</span><span class="sxs-lookup"><span data-stu-id="5b812-227">This is your current configuration.</span></span>
  
![模擬企業基本設定步驟 3](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="5b812-229">階段 2：建立您的 Microsoft 365 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="5b812-229">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="5b812-230">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription.</span><span class="sxs-lookup"><span data-stu-id="5b812-230">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription.</span></span> <span data-ttu-id="5b812-231">You can do this in two ways:</span><span class="sxs-lookup"><span data-stu-id="5b812-231">You can do this in two ways:</span></span>

- <span data-ttu-id="5b812-232">使用 Microsoft 365 E5 的試用版訂閱。</span><span class="sxs-lookup"><span data-stu-id="5b812-232">Use a trial subscription of Microsoft 365 E5.</span></span> 

  <span data-ttu-id="5b812-233">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days.</span><span class="sxs-lookup"><span data-stu-id="5b812-233">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days.</span></span> <span data-ttu-id="5b812-234">When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription.</span><span class="sxs-lookup"><span data-stu-id="5b812-234">When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription.</span></span> <span data-ttu-id="5b812-235">Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span><span class="sxs-lookup"><span data-stu-id="5b812-235">Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="5b812-236">使用具少數授權數的不同 Microsoft 365 E5 生產訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="5b812-236">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="5b812-237">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire.</span><span class="sxs-lookup"><span data-stu-id="5b812-237">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire.</span></span> <span data-ttu-id="5b812-238">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span><span class="sxs-lookup"><span data-stu-id="5b812-238">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span></span> <span data-ttu-id="5b812-239">This is the recommended method.</span><span class="sxs-lookup"><span data-stu-id="5b812-239">This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="5b812-240">註冊 Office 365 E5 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="5b812-240">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="5b812-241">使用 CORP\User1 帳戶透過 Azure 入口網站連線至 CLIENT1。</span><span class="sxs-lookup"><span data-stu-id="5b812-241">Connect to CLIENT1 with the CORP\User1 account from the Azure portal.</span></span>

<span data-ttu-id="5b812-242">若要建立新的 Office 365 E5 試用訂閱，請執行輕量型基本組態測試實驗室指南的[階段 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-office-365-e5-subscription) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="5b812-242">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-office-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="5b812-243">若要設定您的新 Office 365 E5 試用訂閱，請執行輕量型基本組態測試實驗室指南的[階段 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="5b812-243">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="5b812-244">使用 Office 365 E5 測試環境</span><span class="sxs-lookup"><span data-stu-id="5b812-244">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="5b812-245">如果您只需要 Office 365 測試環境，您可以在這裡停止。</span><span class="sxs-lookup"><span data-stu-id="5b812-245">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="5b812-246">如需適用於 Office 365 和 Microsoft 365 的其他測試實驗室指南，請參閱 [Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="5b812-246">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="5b812-247">新增 Microsoft 365 E5 試用版訂閱</span><span class="sxs-lookup"><span data-stu-id="5b812-247">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="5b812-248">若要取得 Microsoft 365 E5 試用訂閱，並設定您的使用者帳戶使用授權，請執行輕量型基本組態測試實驗室指南的[階段 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="5b812-248">To a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="5b812-249">結果</span><span class="sxs-lookup"><span data-stu-id="5b812-249">Results</span></span>

<span data-ttu-id="5b812-250">測試環境現在擁有：</span><span class="sxs-lookup"><span data-stu-id="5b812-250">Your test environment now has:</span></span>
  
- <span data-ttu-id="5b812-251">Microsoft 365 E5 試用版訂閱。</span><span class="sxs-lookup"><span data-stu-id="5b812-251">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="5b812-252">您的所有適用使用者帳戶皆可使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="5b812-252">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="5b812-253">模擬且簡化的內部網路。</span><span class="sxs-lookup"><span data-stu-id="5b812-253">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="5b812-254">這是您的最終設定。</span><span class="sxs-lookup"><span data-stu-id="5b812-254">This is your final configuration.</span></span>
  
![模擬企業基本設定階段 2](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="5b812-256">您現在已準備好嘗試 [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="5b812-256">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="5b812-257">後續步驟</span><span class="sxs-lookup"><span data-stu-id="5b812-257">Next steps</span></span>

<span data-ttu-id="5b812-258">探索這些額外的測試實驗室指南集合：</span><span class="sxs-lookup"><span data-stu-id="5b812-258">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="5b812-259">身分識別</span><span class="sxs-lookup"><span data-stu-id="5b812-259">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="5b812-260">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="5b812-260">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="5b812-261">資訊保護</span><span class="sxs-lookup"><span data-stu-id="5b812-261">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="5b812-262">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5b812-262">See also</span></span>

[<span data-ttu-id="5b812-263">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="5b812-263">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5b812-264">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="5b812-264">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="5b812-265">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="5b812-265">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
