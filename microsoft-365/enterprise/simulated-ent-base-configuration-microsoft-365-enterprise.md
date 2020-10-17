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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 使用此測試實驗室指南來建立適用于企業的 Microsoft 365 模擬企業測試環境。
ms.openlocfilehash: e66ec8c48e309daeb15aad5fcc475edcb2b8bb35
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487651"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="8a7b6-103">模擬企業基本設定</span><span class="sxs-lookup"><span data-stu-id="8a7b6-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="8a7b6-104">*此測試實驗室指南可用於 enterprise 和 Office 365 企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="8a7b6-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="8a7b6-105">本文說明如何為適用于企業的 Microsoft 365 建立簡化的環境，其中包括：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-105">This article describes how to create a simplified environment for Microsoft 365 for enterprise that includes:</span></span>

- <span data-ttu-id="8a7b6-106">Microsoft 365 E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="8a7b6-107">簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路上的三個虛擬機器所組成 (DC1、APP1 和 CLIENT1) 。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-107">A simplified organization intranet connected to the internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![模擬企業基本設定](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="8a7b6-109">建立簡化的測試環境包括兩個階段：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-109">Creating a simplified test environment involves two phases:</span></span>
- [<span data-ttu-id="8a7b6-110">階段 1：建立模擬的內部網路</span><span class="sxs-lookup"><span data-stu-id="8a7b6-110">Phase 1: Create a simulated intranet</span></span>](#phase-1-create-a-simulated-intranet)
- [<span data-ttu-id="8a7b6-111">階段 2：建立您的 Microsoft 365 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="8a7b6-111">Phase 2: Create your Microsoft 365 E5 subscription</span></span>](#phase-2-create-your-microsoft-365-e5-subscription)

<span data-ttu-id="8a7b6-112">您可以使用所產生的環境，利用其他[測試實驗室指南](m365-enterprise-test-lab-guides.md)或您自己的方式，測試[適用于 enterprise 的 Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise)的功能。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-112">You can use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="8a7b6-114">如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="8a7b6-115">階段 1：建立模擬的內部網路</span><span class="sxs-lookup"><span data-stu-id="8a7b6-115">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="8a7b6-116">在此階段中，請在 Azure 基礎結構服務中建立模擬的內部網路，其中包含 Active Directory 網域服務 (AD DS) 網域控制站、應用程式伺服器及用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-116">In this phase, build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span>

<span data-ttu-id="8a7b6-117">您將在其他 [Microsoft 365 for Enterprise 測試實驗室指南](m365-enterprise-test-lab-guides.md) 中使用這些電腦，以設定並示範混合式身分識別和其他功能。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-117">You'll use these computers in additional [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="8a7b6-118">方法 1：使用 Azure Resource Manager 範本建立模擬內部網路</span><span class="sxs-lookup"><span data-stu-id="8a7b6-118">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="8a7b6-119">在此方法中，您可以使用 Azure 資源管理員範本來組建模擬的內部網路。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-119">In this method, you use an Azure Resource Manager template to build out the simulated intranet.</span></span> <span data-ttu-id="8a7b6-120">Azure 資源管理員範本包含建立 Azure 網路基礎結構、虛擬機器及其設定的所有指示。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-120">Azure Resource Manager templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="8a7b6-121">部署範本之前，請先閱讀 [範本的自述頁面](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) ，並準備好下列資訊：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-121">Before deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="8a7b6-122">測試環境的公用 DNS 功能變數名稱 (testlab。 \<*your public domain*>) 。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-122">The public DNS domain name of your test environment (testlab.\<*your public domain*>).</span></span> <span data-ttu-id="8a7b6-123">您會在 [**自訂部署**] 頁面的 [**功能變數名稱**] 欄位中輸入此名稱。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-123">You'll enter this name in the **Domain Name** field of the **Custom deployment** page.</span></span>
- <span data-ttu-id="8a7b6-p103">虛擬機器公用 IP 位址 URL 上的 DNS 標籤前置詞。您必須在 **[自訂部署]** 頁面的 **[Dns 標籤前置詞]** 欄位中輸入此標籤。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="8a7b6-126">在您閱讀指示之後，請選取 [[範本 README] 頁面](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)上的 [**部署到 Azure** ] 以開始使用。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-126">After you read through the instructions, select **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="8a7b6-127">Azure 資源管理員範本所建立的模擬內部網路需要付費的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-127">The simulated intranet built by the Azure Resource Manager template requires a paid Azure subscription.</span></span>

<span data-ttu-id="8a7b6-128">範本完成後，您的設定會如下所示：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-128">After the template is complete, your configuration looks like this:</span></span>

![Azure 基礎結構服務中的模擬內部網路](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="8a7b6-130">方法 2：使用 Azure PowerShell 建立模擬內部網路</span><span class="sxs-lookup"><span data-stu-id="8a7b6-130">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="8a7b6-131">在這個方法中，您使用 Windows PowerShell 和 Azure PowerShell 模組建置網路基礎結構、虛擬機器及其設定。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-131">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="8a7b6-p104">如果您想要使用 PowerShell 獲得一次一個步驟建立 Azure 基礎結構元素的體驗，則使用此方法。然後，您可以自行定義 PowerShell 命令區塊，以便在 Azure 中部署其他虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="8a7b6-134">步驟 1：建立 DC1</span><span class="sxs-lookup"><span data-stu-id="8a7b6-134">Step 1: Create DC1</span></span>

<span data-ttu-id="8a7b6-135">在這個步驟中，您會建立 Azure 虛擬網路並新增 DC1，這是 AD DS 網域的網域控制站的虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-135">In this step, you create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="8a7b6-136">首先，在本機電腦上啟動 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-136">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a7b6-p105">下列命令集會使用最新版的 Azure PowerShell。請參閱[開始使用 Azure PowerShell Cmdlet](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="8a7b6-139">使用下列命令登入您的 Azure 帳戶。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-139">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="8a7b6-140">使用下列命令取得訂用帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-140">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="8a7b6-141">設定 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-141">Set your Azure subscription.</span></span> <span data-ttu-id="8a7b6-142">以正確的名稱取代引號內的所有專案，包括角括弧 ( "<" 和 ">" ) 。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-142">Replace everything within the quotation marks, including the angle brackets ("<" and ">"), with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="8a7b6-p107">接著，為您的模擬企業測試實驗室建立新的資源群組。若要判斷資源群組名稱是否是唯一的，可使用此命令來列出現有的資源群組。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="8a7b6-145">使用這些命令建立新的資源群組。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-145">Create your new resource group with these commands.</span></span> <span data-ttu-id="8a7b6-146">以正確的名稱取代引號內的所有專案（包括角括弧）。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-146">Replace everything within the quotation marks, including the angle brackets, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="8a7b6-147">接下來，建立會主控模擬企業環境之公司網路子網的 TestLab 虛擬網路，並以網路安全性群組來保護它。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-147">Next, create the TestLab virtual network that will host the corporate network subnet of the simulated enterprise environment and protect it with a network security group.</span></span> <span data-ttu-id="8a7b6-148">填入您的資源群組名稱，並在本機電腦的 PowerShell 命令提示字元執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-148">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="8a7b6-149">接下來，您要建立 DC1 虛擬機器，並將它設定為 **testlab**\<your public domain>的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-149">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain></span></span> <span data-ttu-id="8a7b6-150">AD DS 網域和 TestLab 虛擬網路虛擬機器的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-150">AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="8a7b6-151">例如，若您的公用網域名稱為 **<span>contoso</span>.com**，則 DC1 虛擬機器會是 **<span>testlab</span>.contoso.com** 網域的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-151">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="8a7b6-152">若要建立 DC1 的 Azure 虛擬機器，請填入您的資源群組，並在本機電腦上的 PowerShell 命令提示字元執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-152">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="8a7b6-p111">系統會提示您輸入 DC1 上本機系統管理員帳戶的使用者名稱和密碼。使用強式密碼，並將名稱和密碼記錄於安全的位置。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="8a7b6-155">接下來，連接至 DC1 虛擬機器：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-155">Next, connect to the DC1 virtual machine:</span></span>
  
1. <span data-ttu-id="8a7b6-156">在[Azure 入口網站](https://portal.azure.com)中，選取 [**資源群組** > <***新資源群組的名稱***> > **DC1**  >  **Connect]**。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-156">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <***the name of your new resource group***> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="8a7b6-157">在 [開啟] 窗格中，選取 [ **下載 RDP 檔**]。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-157">In the open pane, select **Download RDP file**.</span></span> <span data-ttu-id="8a7b6-158">開啟所下載的 DC1.rdp 檔案，然後選取 [連線 **]**。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-158">Open the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="8a7b6-159">指定 DC1 本機系統管理員帳戶名稱：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-159">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="8a7b6-160">對於 Windows 7：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-160">For Windows 7:</span></span>
    
     <span data-ttu-id="8a7b6-161">在 [ **Windows 安全性** ] 對話方塊中，選取 [ **使用另一個帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-161">In the **Windows Security** dialog box, select **Use another account**.</span></span> <span data-ttu-id="8a7b6-162">在 [**使用者名稱**] 中，輸入\*\*DC1 \\ \*\* < *本機系統管理員帳戶名稱*>。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-162">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
   - <span data-ttu-id="8a7b6-163">對於 Windows 8 或 Windows 10：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-163">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="8a7b6-164">在 [ **Windows 安全性** ] 對話方塊中，選取 [ **更多選項**]，然後選取 [ **使用另一個帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-164">In the **Windows Security** dialog box, select **More choices**, and then select **Use a different account**.</span></span> <span data-ttu-id="8a7b6-165">在 [**使用者名稱**] 中，輸入\*\*DC1 \\ \*\* < *本機系統管理員帳戶名稱*>。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-165">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="8a7b6-166">在 [ **密碼**] 中，輸入本機系統管理員帳戶的密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-166">In **Password**, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="8a7b6-167">出現提示時，請選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-167">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="8a7b6-168">接著，使用此命令在 DC1 上系統管理員層級 Windows PowerShell 命令提示字元將額外的資料磁碟新增為新的磁碟區 (磁碟機代號 F:)。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-168">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="8a7b6-169">接下來，將 DC1 設定為網域控制站，並將 DNS 伺服器設定為 **testlab。**\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="8a7b6-169">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<*your public domain*></span></span> <span data-ttu-id="8a7b6-170">網域。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-170">domain.</span></span> <span data-ttu-id="8a7b6-171">指定您的公用功能變數名稱、移除角括弧，然後在系統管理員層級的 Windows 上執行這些命令。 DC1 上 PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-171">Specify your public domain name, remove the angle brackets, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="8a7b6-p116">您必須指定安全模式的系統管理員密碼。將此密碼儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="8a7b6-174">請注意，這些命令可能需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-174">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="8a7b6-175">DC1 重新啟動後，重新連線到 DC1 虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-175">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="8a7b6-176">在[Azure 入口網站](https://portal.azure.com)中，選取 [**資源群組** > <*您的資源群組名稱*> > **DC1**  >  **Connect]**。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-176">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <*your resource group name*> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="8a7b6-177">執行已下載的 DC1.rdp 檔案，然後選取 [連線 **]**。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-177">Run the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="8a7b6-178">在 [ **Windows 安全性**] 中，選取 [ **使用另一個帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-178">In **Windows Security**, select **Use another account**.</span></span> <span data-ttu-id="8a7b6-179">在 [**使用者名稱**] 中，輸入\**TESTLAB \\ \*\* < 的*本機系統管理員帳戶名稱\*>。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-179">In **User name**, enter **TESTLAB\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="8a7b6-180">在 [ **密碼** ] 方塊中，輸入本機系統管理員帳戶的密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-180">In the **Password** box, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="8a7b6-181">出現提示時，請選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-181">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="8a7b6-182">接下來，在 Active Directory 中建立登入 TESTLAB 網域成員電腦時所使用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-182">Next, create a user account in Active Directory that will be used when signing in to TESTLAB domain member computers.</span></span> <span data-ttu-id="8a7b6-183">在系統管理員層級的 Windows PowerShell 命令提示字元中執行此命令。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-183">Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="8a7b6-184">請注意，此命令會提示您提供 User1 帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-184">Note that this command prompts you to supply the User1 account password.</span></span> <span data-ttu-id="8a7b6-185">此帳戶將用於所有 TESTLAB 網域成員電腦的遠端桌面連線，因此請選擇強式密碼。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-185">This account will be used for remote desktop connections for all TESTLAB domain member computers, so choose a strong password.</span></span> <span data-ttu-id="8a7b6-186">記錄 User1 帳戶密碼，並將其儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-186">Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="8a7b6-p120">接下來，將新的 User1 帳戶設定為網域、企業和結構描述管理員。在系統管理員層級 Windows PowerShell 命令提示字元執行此命令。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="8a7b6-189">關閉 DC1 的遠端桌面工作階段，然後使用 TESTLAB\\User1 帳戶重新連線。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-189">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="8a7b6-190">接下來，若要允許 Ping 工具的流量，請在系統管理員層級 Windows PowerShell 命令提示字元執行此命令。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-190">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="8a7b6-191">您目前的設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-191">Your current configuration looks like this:</span></span>
  
![模擬企業基本設定步驟 1](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="8a7b6-193">步驟 2：設定 APP1</span><span class="sxs-lookup"><span data-stu-id="8a7b6-193">Step 2: Configure APP1</span></span>

<span data-ttu-id="8a7b6-194">在這個步驟，您會建立及設定 APP1，這是一開始提供 Web 和檔案共用服務的應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-194">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="8a7b6-195">若要建立 APP1 的 Azure 虛擬機器，請填入您的資源群組，並在本機電腦上的命令提示字元執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-195">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="8a7b6-196">接下來，使用 APP1 本機系統管理員帳戶名稱和密碼連線到 APP1 虛擬機器，然後開啟 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-196">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="8a7b6-197">若要檢查 APP1 和 DC1 之間的名稱解析和網路通訊，請執行 **ping DC1.testlab。**\<*your public domain name*></span><span class="sxs-lookup"><span data-stu-id="8a7b6-197">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="8a7b6-198">命令，並確認有四個回復。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-198">command and verify that there are four replies.</span></span>
  
<span data-ttu-id="8a7b6-199">接下來在 Windows PowerShell 命令提示字元使用以下命令將 APP1 虛擬機器加入 TESTLAB 網域。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-199">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="8a7b6-200">請注意，在您執行 **Add-Computer** 命令之後，您必須提供 TESTLAB \\ User1 網域帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-200">Note that you after you run the **Add-Computer** command, you must supply the TESTLAB\\User1 domain account credentials.</span></span>
  
<span data-ttu-id="8a7b6-201">APP1 重新啟動之後，使用 TESTLAB\\User1 帳戶連線至 APP1，然後開啟系統管理員層級 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-201">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="8a7b6-202">接下來，在 APP1 上的系統管理員層級 Windows PowerShell 命令提示字元中使用此命令讓 APP1 成為 Web 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-202">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="8a7b6-203">接下來，使用這些 PowerShell 命令在 APP1 上的資料夾內建立共用資料夾及文字檔。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-203">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="8a7b6-204">您目前的設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-204">Your current configuration looks like this:</span></span>
  
![模擬企業基本設定步驟 2](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="8a7b6-206">步驟 3：設定 CLIENT1</span><span class="sxs-lookup"><span data-stu-id="8a7b6-206">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="8a7b6-207">在這個步驟中，建立及設定 CLIENT1，其可在內部網路上作為一般的膝上型電腦、平板電腦或桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-207">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="8a7b6-p122">下列命令集可建立執行 Windows Server 2016 資料中心的 CLIENT1，其適用於所有類型的 Azure 訂閱。如果您有以 Visual Studio 為基礎的 Azure 訂閱，則可以使用 [Azure 入口網站](https://portal.azure.com)建立執行 Windows 10 的 CLIENT1。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-p122">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span>
  
<span data-ttu-id="8a7b6-210">若要建立 CLIENT1 的 Azure 虛擬機器，請填入您的資源群組的名稱，並在本機電腦上的命令提示字元中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-210">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="8a7b6-211">接下來，使用 CLIENT1 本機系統管理員帳戶名稱和密碼連線到 CLIENT1 虛擬機器，然後開啟系統管理員層級 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-211">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="8a7b6-212">若要檢 CLIENT1 和 DC1 之間的名稱解析和網路通訊，請執行 **ping DC1.testlab。**\<*your public domain name*></span><span class="sxs-lookup"><span data-stu-id="8a7b6-212">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="8a7b6-213">命令 Windows PowerShell 命令提示字元，並確認有四個回復。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-213">command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="8a7b6-214">接下來在 Windows PowerShell 命令提示字元使用以下命令將 CLIENT1 虛擬機器加入 TESTLAB 網域。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-214">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="8a7b6-215">請注意，您必須在執行 **Add-Computer** 命令之後，提供 TESTLAB\\User1 網域帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-215">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="8a7b6-216">CLIENT1 重新啟動之後，使用 TESTLAB\\User1 帳戶名稱和密碼連線至 CLIENT1，然後開啟系統管理員層級 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-216">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="8a7b6-217">接下來，確認您可以從 CLIENT1 存取 APP1 上的 Web 及檔案共用資源。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-217">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="8a7b6-218">在 [伺服器管理員] 的樹狀窗格中，選取 [ **本機伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-218">In Server Manager, in the tree pane, select **Local Server**.</span></span>
    
2. <span data-ttu-id="8a7b6-219">在 [ **CLIENT1 的屬性**] 中，選取 [ **IE 增強式安全性**設定] 旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-219">In **Properties for CLIENT1**, select **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="8a7b6-220">在**Internet Explorer 增強式安全性**設定中，為系統**管理員**和**使用者**選取 [**關閉**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-220">In **Internet Explorer Enhanced Security Configuration**, select **Off** for **Administrators** and **Users**, and then select **OK**.</span></span>
    
4. <span data-ttu-id="8a7b6-221">從 [開始] 畫面中，選取 [ **Internet Explorer**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-221">From the Start screen, select **Internet Explorer**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="8a7b6-222">在 [位址] 列中，輸入 [ **HTTP：<span>//</span>app1] testab。** \<*your public domain name*> **/** ，然後按**enter**。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-222">In the address bar, enter **http<span>://</span>app1.testab.**\<*your public domain name*>**/**, and then press **Enter**.</span></span> <span data-ttu-id="8a7b6-223">您應該會看到 APP1 的預設網際網路資訊服務網頁。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-223">You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="8a7b6-224">在桌面工作列上，選取 [檔案瀏覽器] 圖示。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-224">On the desktop taskbar, select the File Explorer icon.</span></span>
    
7. <span data-ttu-id="8a7b6-225">在位址列中，輸入\*\* \\ \\ app1 \\ Files**，然後按**enter\*\*鍵。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-225">In the address bar, enter **\\\\app1\\Files**, and then press **Enter**.</span></span> <span data-ttu-id="8a7b6-226">您應該會看到資料夾視窗中的 [檔案] 共用資料夾的內容。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-226">You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="8a7b6-p126">在 [檔案]\*\*\*\* 共用資料夾視窗中，按兩下 **Example.txt** 檔案。您應該會看到 Example.txt 檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-p126">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="8a7b6-229">關閉 **example.txt - 記事本**以及 [檔案]\*\*\*\* 共用資料夾視窗。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-229">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="8a7b6-230">您目前的設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-230">Your current configuration looks like this:</span></span>
  
![模擬企業基本設定步驟 3](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="8a7b6-232">階段 2：建立您的 Microsoft 365 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="8a7b6-232">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="8a7b6-p127">您可以在這個階段建立新的 Microsoft 365 E5 訂閱，其使用全新的 Azure AD 租用戶，亦即與您生產訂用帳戶不同。有兩種方法可完成：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-p127">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="8a7b6-235">使用 Microsoft 365 E5 的試用版訂閱。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-235">Use a trial subscription of Microsoft 365 E5.</span></span>

  <span data-ttu-id="8a7b6-p128">Microsoft 365 E5 試用版訂閱期限是 30 天，也可以輕鬆地延長到 60 天。試用版訂閱到期時，您必須將它轉換為付費訂閱，或建立新的試用版訂閱。建立新的試用版訂閱表示您將失去之前的設定，這可能會留下複雜的情況。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-p128">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="8a7b6-239">使用具少數授權數的不同 Microsoft 365 E5 生產訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-239">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="8a7b6-240">這是額外成本，但可確保您的測試環境未到期;在此情況下，您可以嘗試功能、設定及案例。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-240">This is an additional cost, but ensures that you have a working test environment that doesn't expire; in it, you can try features, configurations, and scenarios.</span></span> <span data-ttu-id="8a7b6-241">您可以針對概念證明、對等與管理的示範，以及應用程式開發和測試，使用長期的相同測試環境。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-241">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span></span> <span data-ttu-id="8a7b6-242">這是建議的方法。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-242">This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="8a7b6-243">註冊 Office 365 E5 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="8a7b6-243">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="8a7b6-244">從 Azure 入口網站，使用 CORP\User1 帳戶連接至 CLIENT1。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-244">From the Azure portal, connect to CLIENT1 with the CORP\User1 account.</span></span>

<span data-ttu-id="8a7b6-245">若要建立新的 Office 365 E5 試用訂閱，請執行輕量型基本組態測試實驗室指南的[階段 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-245">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="8a7b6-246">若要設定您的新 Office 365 E5 試用訂閱，請執行輕量型基本組態測試實驗室指南的[階段 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-246">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="8a7b6-247">使用 Office 365 E5 測試環境</span><span class="sxs-lookup"><span data-stu-id="8a7b6-247">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="8a7b6-248">如果您只需要 Office 365 測試環境，您不需要閱讀本文的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-248">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="8a7b6-249">如需同時適用于 Microsoft 365 和 Office 365 的其他測試實驗室指南，請參閱 [Microsoft 365 for Enterprise Test Lab 指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-249">For additional Test Lab Guides that apply to both Microsoft 365 and Office 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="8a7b6-250">新增 Microsoft 365 E5 試用版訂閱</span><span class="sxs-lookup"><span data-stu-id="8a7b6-250">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="8a7b6-251">若要新增 Microsoft 365 E5 試用訂閱，並為您的使用者帳戶設定授權，請執行「輕量基本設定測試實驗室指南」的 [階段 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) 中的指示。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-251">To add a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="8a7b6-252">結果</span><span class="sxs-lookup"><span data-stu-id="8a7b6-252">Results</span></span>

<span data-ttu-id="8a7b6-253">測試環境現在擁有：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-253">Your test environment now has:</span></span>
  
- <span data-ttu-id="8a7b6-254">Microsoft 365 E5 試用版訂閱。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-254">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="8a7b6-255">您的所有適用使用者帳戶皆可使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-255">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="8a7b6-256">模擬且簡化的內部網路。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-256">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="8a7b6-257">您的最後設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-257">Your final configuration looks like this:</span></span>
  
![模擬企業基本設定階段 2](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="8a7b6-259">您現在已準備好嘗試使用 [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="8a7b6-259">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="8a7b6-260">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8a7b6-260">Next steps</span></span>

<span data-ttu-id="8a7b6-261">探索這些額外的測試實驗室指南集合：</span><span class="sxs-lookup"><span data-stu-id="8a7b6-261">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="8a7b6-262">身分識別</span><span class="sxs-lookup"><span data-stu-id="8a7b6-262">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="8a7b6-263">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="8a7b6-263">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="8a7b6-264">資訊保護</span><span class="sxs-lookup"><span data-stu-id="8a7b6-264">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="8a7b6-265">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8a7b6-265">See also</span></span>

[<span data-ttu-id="8a7b6-266">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="8a7b6-266">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8a7b6-267">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="8a7b6-267">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8a7b6-268">適用于企業的 Microsoft 365 檔</span><span class="sxs-lookup"><span data-stu-id="8a7b6-268">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
