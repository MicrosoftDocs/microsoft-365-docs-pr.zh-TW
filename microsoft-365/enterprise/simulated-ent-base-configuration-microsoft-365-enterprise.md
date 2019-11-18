---
title: Microsoft 365 模擬企業基本設定
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 使用此「測試實驗室指南」建立 Microsoft 365 企業版的模擬企業測試環境。
ms.openlocfilehash: cf69be53f6c0687aba90b57ab4e272ea68c66c3e
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673299"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="7dfd7-103">模擬企業基本設定</span><span class="sxs-lookup"><span data-stu-id="7dfd7-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="7dfd7-104">*這個測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版兩種測試環境。*</span><span class="sxs-lookup"><span data-stu-id="7dfd7-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="7dfd7-105">本文提供逐步指示來為 Microsoft 365 企業版建立簡化的環境，其中包含：</span><span class="sxs-lookup"><span data-stu-id="7dfd7-105">This article provides you with step-by-step instructions to create a simplified environment for Microsoft 365 Enterprise that includes:</span></span>

- <span data-ttu-id="7dfd7-106">Microsoft 365 E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="7dfd7-107">簡化的組織內部網域與網際網路的連線，由 Azure 虛擬網路上的三部虛擬機器 (DC1、APP1 及 CLIENT1) 組成。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-107">A simplified organization intranet connected to the Internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![模擬企業基本設定](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="7dfd7-109">您可以利用額外的[測試實驗室指南](m365-enterprise-test-lab-guides.md)或靠您自己，使用所產生的環境來測試 [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise)的功能。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-109">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="7dfd7-111">按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="7dfd7-112">階段 1：建立模擬的內部網路</span><span class="sxs-lookup"><span data-stu-id="7dfd7-112">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="7dfd7-113">在這個階段，您可以在 Azure 基礎結構服務中建立模擬內部網路，其中包含 Active Directory Domain Services (AD DS) 網域控制站、應用程式伺服器和用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-113">In this phase, you build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span> 

<span data-ttu-id="7dfd7-114">您可以在其他 [Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)中使用這些電腦，以設定並示範混合式身分識別及其他功能。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-114">You'll use these computers in additional [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="7dfd7-115">方法 1：使用 Azure Resource Manager 範本建立模擬內部網路</span><span class="sxs-lookup"><span data-stu-id="7dfd7-115">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="7dfd7-p101">在這個方法中，您可以使用 Azure Resource Manager (ARM) 範本來建立模擬內部網路。ARM 範本包含建立 Azure 網路基礎結構、虛擬機器及其設定的所有指示。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p101">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet. ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="7dfd7-118">部署範本之前，請先閱讀[範本讀我檔案頁面](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)並準備好下列資訊：</span><span class="sxs-lookup"><span data-stu-id="7dfd7-118">Prior to deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="7dfd7-p102">測試環境的公用 DNS 網域名稱 (testlab.\<您的公用網域>)。您必須在 [自訂部署]\*\*\*\* 面的 [網域名稱]\*\*\*\* 欄位中輸入此名稱。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p102">The public DNS domain name of your test environment (testlab.\<your public domain>). You’ll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span></span>
- <span data-ttu-id="7dfd7-p103">虛擬機器公用 IP 位址 URL 上的 DNS 標籤前置詞。您必須在 [自訂部署]\*\*\*\* 頁面的 [DNS 標籤前置詞]\*\*\*\* 欄位中輸入此標籤。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You’ll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="7dfd7-123">閱讀指示之後，請在[範本讀我檔案頁面](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)上按一下 [部署至 Azure]\*\*\*\* 以開始使用。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-123">After reading through the instructions, click **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="7dfd7-124">ARM 範本所建立的模擬內部網路需要 Azure 付費訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-124">The simulated intranet built by the ARM template requires a paid Azure subscription.</span></span>
>

<span data-ttu-id="7dfd7-125">範本完成後，您的設定如下。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-125">Here is your configuration after the template is complete.</span></span>

![Azure 基礎結構服務中的模擬內部網路](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="7dfd7-127">方法 2：使用 Azure PowerShell 建立模擬內部網路</span><span class="sxs-lookup"><span data-stu-id="7dfd7-127">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="7dfd7-128">在這個方法中，您使用 Windows PowerShell 和 Azure PowerShell 模組建置網路基礎結構、虛擬機器及其設定。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-128">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="7dfd7-p104">如果您想要使用 PowerShell 獲得一次一個步驟建立 Azure 基礎結構元素的體驗，則使用此方法。然後，您可以自行定義 PowerShell 命令區塊，以便在 Azure 中部署其他虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="7dfd7-131">步驟 1：建立 DC1</span><span class="sxs-lookup"><span data-stu-id="7dfd7-131">Step 1: Create DC1</span></span>

<span data-ttu-id="7dfd7-132">在這個步驟，我們會建立 Azure 虛擬網路並新增 DC1 (這部虛擬機器是 AD DS 網域的網域控制站)。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-132">In this step, we create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="7dfd7-133">首先，在本機電腦上啟動 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-133">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7dfd7-p105">下列命令集會使用最新版的 Azure PowerShell。請參閱[開始使用 Azure PowerShell Cmdlet](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="7dfd7-136">使用下列命令登入您的 Azure 帳戶。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-136">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="7dfd7-137">使用下列命令取得訂用帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-137">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="7dfd7-p106">設定 Azure 訂用帳戶。以正確的名稱取代括號中的所有項目 (包括 < 和 > 字元)。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p106">Set your Azure subscription. Replace everything within the quotes, including the < and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="7dfd7-p107">接著，為您的模擬企業測試實驗室建立新的資源群組。若要判斷資源群組名稱是否是唯一的，可使用此命令來列出現有的資源群組。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="7dfd7-p108">使用這些命令建立新的資源群組。以正確的名稱取代引號內的所有項目 (包括 < 和 > 字元)。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p108">Create your new resource group with these commands. Replace everything within the quotes, including the < and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="7dfd7-p109">接下來，您會建立 TestLab 虛擬網路，該虛擬網路會裝載模擬企業環境的 Corpnet 子網路以及利用網路安全性群組來保護它。填入您的資源群組名稱，並且在本機電腦上的 PowerShell 命令提示字元執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p109">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group. Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="7dfd7-146">接下來，建立 DC1 虛擬機器，然後將它設定為 \*\* 測試實驗室的網域控制站。測試實驗室虛擬網路的虛擬機器的\*\*\<公用網域 > AD DS 網域及 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-146">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain> AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="7dfd7-147">例如，若您的公用網域名稱為 **<span>contoso</span>.com**，則 DC1 虛擬機器會是 **<span>testlab</span>.contoso.com** 網域的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-147">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="7dfd7-148">若要建立 DC1 的 Azure 虛擬機器，請填入您的資源群組，並在本機電腦上的 PowerShell 命令提示字元執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-148">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A1
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

<span data-ttu-id="7dfd7-p111">系統會提示您輸入 DC1 上本機系統管理員帳戶的使用者名稱和密碼。使用強式密碼，並將名稱和密碼記錄於安全的位置。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="7dfd7-151">接下來，連線到 DC1 虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-151">Next, connect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="7dfd7-152">在 [Azure 入口網站](https://portal.azure.com)中，按一下 **[資源群組] >** [新的資源群組名稱] **> [DC1] > [連線]**。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-152">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [the name of your new resource group] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="7dfd7-p112">在開啟的窗格中，按一下 [下載 RDP 檔案]\*\*\*\*。開啟所下載的 DC1.rdp 檔案，然後按一下 [連線]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p112">In the open pane, click **Download RDP file**. Open the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="7dfd7-155">指定 DC1 本機系統管理員帳戶名稱：</span><span class="sxs-lookup"><span data-stu-id="7dfd7-155">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="7dfd7-156">對於 Windows 7：</span><span class="sxs-lookup"><span data-stu-id="7dfd7-156">For Windows 7:</span></span>
    
     <span data-ttu-id="7dfd7-p113">在 [Windows 安全性]\*\*\*\* 對話方塊中，按一下 [使用其他帳戶]\*\*\*\*。在 [使用者名稱]\*\*\*\* 中，輸入 **DC1\\**[本機系統管理員帳戶名稱]。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p113">In the **Windows Security** dialog box, click **Use another account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
   - <span data-ttu-id="7dfd7-159">對於 Windows 8 或 Windows 10：</span><span class="sxs-lookup"><span data-stu-id="7dfd7-159">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="7dfd7-p114">在 [Windows 安全性]\*\*\*\* 對話方塊中，按一下 [更多選項]\*\*\*\*，然後按 [使用不同帳戶]\*\*\*\*。在 [使用者名稱]\*\*\*\* 中，輸入 **DC1\\**[本機系統管理員帳戶名稱]。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p114">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="7dfd7-162">在 [密碼]\*\*\*\* 中，輸入本機系統管理員帳戶的密碼，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-162">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="7dfd7-163">出現提示時，按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-163">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="7dfd7-164">接著，使用此命令在 DC1 上系統管理員層級 Windows PowerShell 命令提示字元將額外的資料磁碟新增為新的磁碟區 (磁碟機代號 F:)。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-164">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="7dfd7-p115">接著，將 DC1 設定為 **testlab.**\<您的公用網域> 網域的網域控制站和 DNS 伺服器。指定您的公用網域名稱，移除 \< 和 > 字元，然後在 DC1 上的系統管理員層級 Windows PowerShell 命令提示字元執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p115">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<your public domain> domain. Specify your public domain name, remove the \< and > characters, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="7dfd7-p116">您必須指定安全模式的系統管理員密碼。將此密碼儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="7dfd7-169">請注意，這些命令可能需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-169">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="7dfd7-170">DC1 重新啟動後，重新連線到 DC1 虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-170">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="7dfd7-171">在 [Azure 入口網站](https://portal.azure.com)中，按一下 **[資源群組] >** [您的資源群組名稱] **> [DC1] > [連線]**。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-171">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [your resource group name] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="7dfd7-172">執行所下載的 DC1.rdp 檔案，然後按一下 [連線]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-172">Run the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="7dfd7-p117">在 [Windows 安全性]\*\*\*\* 中，按一下 [使用其他帳戶]\*\*\*\*。在 [使用者名稱]\*\*\*\* 中，輸入 **TESTLAB\\**[本機系統管理員帳戶名稱]。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p117">In **Windows Security**, click **Use another account**. In **User name**, type **TESTLAB\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="7dfd7-175">在 [密碼]\*\*\*\* 中，輸入本機系統管理員帳戶的密碼，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-175">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="7dfd7-176">出現提示時，按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-176">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="7dfd7-p118">接下來，建立 Active Directory 中的使用者帳戶，可在登入 TESTLAB 網域成員電腦時使用。在系統管理員層級 Windows PowerShell 命令提示字元執行此命令。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p118">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers. Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="7dfd7-p119">請注意，此命令會提示您提供 User1 帳戶密碼。由於這個帳戶將會用於所有 TESTLAB 網域成員電腦的遠端桌面連線，請選擇強式密碼。記錄 User1 帳戶密碼，並將它儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p119">Note that this command prompts you to supply the User1 account password. Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password. Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="7dfd7-p120">接下來，將新的 User1 帳戶設定為網域、企業和結構描述管理員。在系統管理員層級 Windows PowerShell 命令提示字元執行此命令。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab"+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="7dfd7-184">關閉 DC1 的遠端桌面工作階段，然後使用 TESTLAB\\User1 帳戶重新連線。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-184">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="7dfd7-185">接下來，若要允許 Ping 工具的流量，請在系統管理員層級 Windows PowerShell 命令提示字元執行此命令。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-185">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="7dfd7-186">這是您目前的設定。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-186">This is your current configuration.</span></span>
  
![模擬企業基本設定步驟 1](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="7dfd7-188">步驟 2：設定 APP1</span><span class="sxs-lookup"><span data-stu-id="7dfd7-188">Step 2: Configure APP1</span></span>

<span data-ttu-id="7dfd7-189">在這個步驟，您會建立及設定 APP1，這是一開始提供 Web 和檔案共用服務的應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-189">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="7dfd7-190">若要建立 APP1 的 Azure 虛擬機器，請填入您的資源群組，並在本機電腦上的命令提示字元執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-190">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="7dfd7-191">接下來，使用 APP1 本機系統管理員帳戶名稱和密碼連線到 APP1 虛擬機器，然後開啟 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-191">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="7dfd7-192">若要檢查 APP1 和 DC1 之間的名稱解析和網路通訊，請執行 **ping dc1.testlab.**\<您的公用網域名稱> 命令，並確認有四個回覆。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-192">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command and verify that there are four replies.</span></span>
  
<span data-ttu-id="7dfd7-193">接下來在 Windows PowerShell 命令提示字元使用以下命令將 APP1 虛擬機器加入 TESTLAB 網域。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-193">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

<span data-ttu-id="7dfd7-194">請注意，您必須在執行 **Add-Computer** 命令之後，提供 TESTLAB\\User1 網域帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-194">Note that you must supply the TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="7dfd7-195">APP1 重新啟動之後，使用 TESTLAB\\User1 帳戶連線至 APP1，然後開啟系統管理員層級 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-195">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="7dfd7-196">接下來，在 APP1 上的系統管理員層級 Windows PowerShell 命令提示字元中使用此命令讓 APP1 成為 Web 伺服器。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-196">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="7dfd7-197">接下來，使用這些 PowerShell 命令在 APP1 上的資料夾內建立共用資料夾及文字檔。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-197">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="7dfd7-198">這是您目前的設定。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-198">This is your current configuration.</span></span>
  
![模擬企業基本設定步驟 2](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="7dfd7-200">步驟 3：設定 CLIENT1</span><span class="sxs-lookup"><span data-stu-id="7dfd7-200">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="7dfd7-201">在這個步驟中，建立及設定 CLIENT1，其可在內部網路上作為一般的膝上型電腦、平板電腦或桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-201">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="7dfd7-p121">下列命令集可建立執行 Windows Server 2016 資料中心的 CLIENT1，其適用於所有類型的 Azure 訂閱。如果您有以 Visual Studio 為基礎的 Azure 訂閱，則可以使用 [Azure 入口網站](https://portal.azure.com)建立執行 Windows 10 的 CLIENT1。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p121">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have an Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span> 
  
<span data-ttu-id="7dfd7-204">若要建立 CLIENT1 的 Azure 虛擬機器，請填入您的資源群組，並在本機電腦上的命令提示字元執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-204">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="7dfd7-205">接下來，使用 CLIENT1 本機系統管理員帳戶名稱和密碼連線到 CLIENT1 虛擬機器，然後開啟系統管理員層級 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-205">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="7dfd7-206">若要檢查 CLIENT1 和 DC1 之間的名稱解析和網路通訊，請在 Windows PowerShell 命令提示字元執行 **ping dc1.testlab.**\<您的公用網域名稱> 命令，並確認有四個回覆。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-206">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="7dfd7-207">接下來在 Windows PowerShell 命令提示字元使用以下命令將 CLIENT1 虛擬機器加入 TESTLAB 網域。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-207">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

<span data-ttu-id="7dfd7-208">請注意，您必須在執行 **Add-Computer** 命令之後，提供 TESTLAB\\User1 網域帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-208">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="7dfd7-209">CLIENT1 重新啟動之後，使用 TESTLAB\\User1 帳戶名稱和密碼連線至 CLIENT1，然後開啟系統管理員層級 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-209">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="7dfd7-210">接下來，確認您可以從 CLIENT1 存取 APP1 上的 Web 及檔案共用資源。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-210">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="7dfd7-211">在 [伺服器管理員] 的樹狀窗格中，按一下 [本機伺服器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-211">In Server Manager, in the tree pane, click **Local Server**.</span></span>
    
2. <span data-ttu-id="7dfd7-212">在 [CLIENT1 的屬性]\*\*\*\* 中，按一下 [IE 增強式安全性設定]\*\*\*\* 旁邊的 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-212">In **Properties for CLIENT1**, click **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="7dfd7-213">在 [Internet Explorer 增強式安全性設定]\*\*\*\* 中，為 [管理員]\*\*\*\* 和 [使用者]\*\*\*\* 按一下 [關閉]\*\*\*\*，然後按 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-213">In **Internet Explorer Enhanced Security Configuration**, click **Off** for **Administrators** and **Users**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="7dfd7-214">從 [開始] 畫面，按一下 [Internet Explorer]\*\*\*\*，然後按 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-214">From the Start screen, click **Internet Explorer**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="7dfd7-p122">在網址列中，輸入 **http<span>://</span>app1.testab.**\<您的公用網域名稱>**/**，然後按 ENTER 鍵。您應該會看到 APP1 的預設網際網路資訊服務網頁。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p122">In the Address bar, type **http<span>://</span>app1.testab.**\<your public domain name>**/**, and then press ENTER. You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="7dfd7-217">在桌面工作列中，按一下 [檔案總管] 圖示。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-217">From the desktop taskbar, click the File Explorer icon.</span></span>
    
7. <span data-ttu-id="7dfd7-p123">在網址列中，輸入 **\\\\app1\\檔案**，然後按 ENTER 鍵。您應該會看到資料夾視窗中的檔案共用資料夾內容。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p123">In the address bar, type **\\\\app1\\Files**, and then press ENTER. You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="7dfd7-p124">在 [檔案]\*\*\*\* 共用資料夾視窗中，按兩下 **Example.txt** 檔案。您應該會看到 Example.txt 檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p124">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="7dfd7-222">關閉 **example.txt - 記事本**以及 [檔案]\*\*\*\* 共用資料夾視窗。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-222">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="7dfd7-223">這是您目前的設定。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-223">This is your current configuration.</span></span>
  
![模擬企業基本設定步驟 3](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="7dfd7-225">階段 2：建立您的 Microsoft 365 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="7dfd7-225">Phase 2: Create your Microsoft 365 E5 subscriptions</span></span>

<span data-ttu-id="7dfd7-226">您可以在這個階段建立新的 Microsoft 365 E5 訂閱，其使用全新的 Azure AD 租用戶，亦即與您生產訂閱不同。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-226">In this phase, you create a new Microsoft 365 E5 subscription that use a new Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span> <span data-ttu-id="7dfd7-227">您可以使用兩種方式執行此動作：</span><span class="sxs-lookup"><span data-stu-id="7dfd7-227">You can do this in two primary ways:</span></span>

- <span data-ttu-id="7dfd7-228">使用 Microsoft 365 E5 的試用版訂閱。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-228">Use a trial subscription of Microsoft 365 E5.</span></span> 

  <span data-ttu-id="7dfd7-p126">Microsoft 365 E5 試用版訂閱期限是 30 天，也可以輕鬆地延長到 60 天。試用版訂閱到期時，您必須將它轉換為付費訂閱，或建立新的試用版訂閱。建立新的試用版訂閱表示您將失去之前的設定，這可能會留下複雜的情況。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p126">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. When the trial subscription expires, you must either convert it to a paid subscriptions or create a new trial subscription. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="7dfd7-232">使用具少數授權數的不同 Microsoft 365 E5 生產訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-232">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="7dfd7-p127">這會產生額外的成本，但可確保您有運作中的測試環境可嘗試不會過期的功能、組態和案例。您可以長期使用相同的測試環境進行概念性驗證、同儕示範和管理，以及應用程式開發和測試。這是建議的方法。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p127">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire. You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing. This is the recommended method.</span></span>

<span data-ttu-id="7dfd7-236">若要開始 Microsoft 365 E5 試用版訂閱，您需要虛構的公司名稱和新 Microsoft 帳戶。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-236">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="7dfd7-p128">我們建議您使用公司名稱 Contoso 的變種作為公司名稱，也就是 Microsoft 範例內容中使用的虛構公司，但此為非必要的動作。在此處記錄您虛構公司名稱：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p128">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here: ![](./media/Common-Images/TableLine.png)</span></span>
    
2. <span data-ttu-id="7dfd7-p129">若要註冊新 Microsoft 帳戶，請移至 [https://outlook.com ](https://outlook.com)，並使用新電子郵件帳戶以及地址建立帳戶。您會使用這個帳戶來登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p129">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="7dfd7-241">在此處記錄您新帳戶的名字和姓氏：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="7dfd7-241">Record the first and last name of your new account here: ![](./media/Common-Images/TableLine.png)</span></span>
    
  - <span data-ttu-id="7dfd7-242">在此處記錄新電子郵件帳戶地址：![](./media/Common-Images/TableLine.png)@outlook.com</span><span class="sxs-lookup"><span data-stu-id="7dfd7-242">Record the new email account address here: ![](./media/Common-Images/TableLine.png)@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="7dfd7-243">註冊 Office 365 E5 試用訂閱</span><span class="sxs-lookup"><span data-stu-id="7dfd7-243">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="7dfd7-244">我們首先使用 Office 365 E5 試用版訂閱，然後再新增 Microsoft 365 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-244">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

1. <span data-ttu-id="7dfd7-245">針對模擬的企業 Office 365 開發/測試環境，使用來自 Azure 入口網站的 CORP\User1 帳戶連接至 CLIENT1。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-245">For the simulated enterprise Office 365 dev/test environment, connect to CLIENT1 with the CORP\User1 account from the Azure portal.</span></span>  <span data-ttu-id="7dfd7-246">從 [開始] 畫面中，執行 Microsoft Edge，然後移至 [https://aka.ms/e5trial](https://aka.ms/e5trial)。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-246">From the Start screen, run Microsoft Edge and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="7dfd7-247">在 [歡迎，讓我們認識您]\*\*\*\* 頁面上，指定：</span><span class="sxs-lookup"><span data-stu-id="7dfd7-247">On the **Welcome, let's get to know you** page, specify:</span></span>
    
  - <span data-ttu-id="7dfd7-248">您的實際位置</span><span class="sxs-lookup"><span data-stu-id="7dfd7-248">Your physical location</span></span>
    
  - <span data-ttu-id="7dfd7-249">新 Microsoft 帳戶的名字和姓氏</span><span class="sxs-lookup"><span data-stu-id="7dfd7-249">The first and last name of your new Microsoft account</span></span>
    
  - <span data-ttu-id="7dfd7-250">新電子郵件帳戶地址</span><span class="sxs-lookup"><span data-stu-id="7dfd7-250">Your new email account address</span></span>
    
  - <span data-ttu-id="7dfd7-251">公司電話號碼</span><span class="sxs-lookup"><span data-stu-id="7dfd7-251">A business phone number</span></span>
    
  - <span data-ttu-id="7dfd7-252">虛構公司名稱</span><span class="sxs-lookup"><span data-stu-id="7dfd7-252">Your fictional company name</span></span>
    
  - <span data-ttu-id="7dfd7-253">250-999 名人員的組織規模</span><span class="sxs-lookup"><span data-stu-id="7dfd7-253">An organization size of 250-999 people</span></span>
    
3. <span data-ttu-id="7dfd7-254">按一下 [再多一個步驟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-254">Click **Just one more step**.</span></span>
    
4. <span data-ttu-id="7dfd7-255">在 [建立使用者識別碼]\*\*\*\* 頁面上，根據新電子郵件地址輸入使用者名稱、在 @ 符號之後接上虛構公司 (移除名稱中的所有空格)，接著是此新 Office 365 帳戶的密碼 (兩次)。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-255">On the **Create your user ID** page, type a user name based on your new email address, your fictional company after the @ sign (remove all spaces in the name), then a password (twice) for this new Office 365 account.</span></span>
    
    <span data-ttu-id="7dfd7-256">在安全位置中記錄您輸入的密碼。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-256">Record the password that you typed in a secure location.</span></span>
    
    <span data-ttu-id="7dfd7-257">在這裡輸入虛構公司的名稱：![](./media/Common-Images/TableLine.png) (此將稱為**組織名稱**)</span><span class="sxs-lookup"><span data-stu-id="7dfd7-257">Record your fictional company name, to be referred to as the **organization name**, here: ![](./media/Common-Images/TableLine.png)</span></span>
    
5. <span data-ttu-id="7dfd7-258">按一下 [建立我的帳戶] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-258">Click **Create my account**.</span></span>
    
6. <span data-ttu-id="7dfd7-p131">在 [證明您不是機器人。]\*\*\*\* 頁面中，輸入能夠傳送簡訊的手機號碼，然後按一下 [傳送簡訊給我]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-p131">On the **Prove. You're. Not. A. Robot.** page, type the phone number of your text-capable phone, and then click **Text me**.</span></span>
    
7. <span data-ttu-id="7dfd7-261">輸入已接收簡訊訊息中的驗證代碼，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-261">Type the verification code from the received text message, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7dfd7-262">在此記錄登入頁面 URL (選取並複製)：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="7dfd7-262">Record the sign-in page URL here (select and copy): ![](./media/Common-Images/TableLine.png)</span></span>
    
9. <span data-ttu-id="7dfd7-263">在此記錄使用者識別碼 (選取與複製)：![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7dfd7-263">Record the user ID here (select and copy): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="7dfd7-264">此值將被稱為 **Office 365 全域系統管理員名稱**。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-264">This value will be referred to as the **Office 365 global administrator name**.</span></span>
    
10. <span data-ttu-id="7dfd7-265">當您看到 [您已準備就緒]\*\*\*\*，對其按一下。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-265">When you see **You're ready to go**, click it.</span></span>
    
11. <span data-ttu-id="7dfd7-266">在下一頁中，請稍候直到 Office 365 完成設定且所有的圖標皆可供使用。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-266">On the next page, wait until Office 365 completes setting up and all the tiles are available.</span></span>
    
<span data-ttu-id="7dfd7-267">您應會看到主要 Office 365 入口網站頁面，您可以從其中存取 Office 服務和 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-267">You should see main Office 365 portal page from which you can access Office services and the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="7dfd7-268">我們提供您建立 Office 365 試用版訂閱，以便開發/測試環境中能有不同於您目前已有之付費訂閱的單獨 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-268">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="7dfd7-269">此區隔表示您可以在測試租用戶中新增和移除使用者，而不會影響到生產訂閱。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-269">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
### <a name="configure-your-office-365-e5-trial-subscription"></a><span data-ttu-id="7dfd7-270">設定 Office 365 E5 試用版訂閱</span><span class="sxs-lookup"><span data-stu-id="7dfd7-270">Phase 3: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="7dfd7-271">接下來，您可以設定其他使用者使用您的 Office 365 E5 訂閱，並指派他們 Office 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-271">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="7dfd7-272">使用[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) 中的指示，將 Azure Active Directory PowerShell for Graph 模組 CLIENT1 虛擬機器連線到您的 Office 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-272">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from:</span></span>
    
<span data-ttu-id="7dfd7-273">在 [Windows PowerShell 認證要求] 對話方塊中，輸入 Office 365 全域管理員帳戶的使用者名稱 (例如：jdoe@contosotoycompany.onmicrosoft.com) 和密碼。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-273">In the Windows PowerShell Credential Request dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="7dfd7-274">填入您的組織名稱 (範例︰contosotoycompany)，代表位置的兩個字元國家/地區代碼、常用帳戶密碼，再從 PowerShell 命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7dfd7-274">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="7dfd7-275">這裡會使用常見密碼，以便在開發/測試環境中能自動化並輕鬆進行設定。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-275">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="7dfd7-276">當然，對於生產訂閱，這是非常不鼓勵的。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-276">Obviously, this is highly discouraged for production subscriptions.</span></span> 

#### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="7dfd7-277">記錄鑰匙資訊供日後參考</span><span class="sxs-lookup"><span data-stu-id="7dfd7-277">Record key information for future reference</span></span>

<span data-ttu-id="7dfd7-278">您可能會想要列印本文，以記錄您在 Office 365 試用版訂閱的 30 天內所需的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-278">You might want to print this article to record the specific values that you will need for this environment over the 30 days of the Office 365 trial subscription. You can easily extend the trail subscription for another 30 days. For a permanent dev/test environment, create a new paid subscription with a small number of licenses.</span></span> <span data-ttu-id="7dfd7-279">您可以輕鬆再延長 30 天的試用訂閱。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-279">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="7dfd7-280">針對永久開發/測試環境，建立具有單獨 Azure AD 租用戶及少數授權的新付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-280">For a permanent dev/test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

<span data-ttu-id="7dfd7-281">記錄這些值︰</span><span class="sxs-lookup"><span data-stu-id="7dfd7-281">Record these values:</span></span>
  
- <span data-ttu-id="7dfd7-282">Office 365 全域系統管理員名稱：![](./media/Common-Images/TableLine.png).onmicrosoft.com (在階段 2 的步驟 9)</span><span class="sxs-lookup"><span data-stu-id="7dfd7-282">Office 365 global administrator name: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (from step 9 of Phase 2)</span></span>
    
    <span data-ttu-id="7dfd7-283">將此帳戶的密碼記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-283">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="7dfd7-284">您的試用訂閱組織名稱：![](./media/Common-Images/TableLine.png) (從階段 2 的步驟 4)</span><span class="sxs-lookup"><span data-stu-id="7dfd7-284">Your trial subscription organization name: ![](./media/Common-Images/TableLine.png) (from step 4 of Phase 2)</span></span>
    
- <span data-ttu-id="7dfd7-285">若要列出使用者 2、使用者 3、使用者 4 和使用者 5 的帳戶，從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰</span><span class="sxs-lookup"><span data-stu-id="7dfd7-285">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="7dfd7-286">在此記錄帳戶名稱：</span><span class="sxs-lookup"><span data-stu-id="7dfd7-286">Record the account names here:</span></span>
    
  - <span data-ttu-id="7dfd7-287">使用者 2 的帳戶名稱：user2 @![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7dfd7-287">User 2 account name: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="7dfd7-288">使用者 3 的帳戶名稱：user3 @![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7dfd7-288">User 3 account name: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="7dfd7-289">使用者 4 的帳戶名稱：user4 @![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7dfd7-289">User 4 account name: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="7dfd7-290">使用者 5 的帳戶名稱：user5 @![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7dfd7-290">User 5 account name: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="7dfd7-291">將這些帳戶的常見密碼記錄於安全的位置。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-291">Also record the passwords for these accounts in a secure location.</span></span>
   

#### <a name="using-an-office-365-e5-devtest-environment"></a><span data-ttu-id="7dfd7-292">使用 Office 365 E5 開發/測試環境</span><span class="sxs-lookup"><span data-stu-id="7dfd7-292">Using an Office 365 E5 dev/test environment</span></span>

<span data-ttu-id="7dfd7-293">如果您只需要 Office 365 開發/測試環境，您可以在這裡停止。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-293">If all you need is an Office 365 dev/test environment, you can stop here.</span></span> 

<span data-ttu-id="7dfd7-294">如需適用於 Office 365 和 Microsoft 365 的其他測試實驗室指南，請參閱 [Microsoft 365 企業版測試實驗室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-294">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="7dfd7-295">新增 Microsoft 365 E5 試用版訂閱</span><span class="sxs-lookup"><span data-stu-id="7dfd7-295">Phase 2: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="7dfd7-296">接下來，您可以註冊 Microsoft 365 E5 試用版訂閱，並將它新增至與 Office 365 E5 試用版訂閱相同的組織。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-296">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="7dfd7-297">首先，新增 Microsoft 365 E5 試用版訂閱，並將 Microsoft 365 授權指派給您的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-297">First, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="7dfd7-298">使用網際網路瀏覽器的私用執行個體，以全域系統管理員帳戶憑證登入位於 [https://admin.microsoft.com](https://admin.microsoft.com) 的 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-298">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="7dfd7-299">在 [Microsoft 365 系統管理中心] \*\*\*\* 頁面的左側導覽中，按一下 [帳單 > 購買服務]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-299">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="7dfd7-300">在 [購買服務]\*\*\*\* 頁面上，找到 [Microsoft 365 E5]\*\*\*\* 項目。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-300">On the **Purchase services** page, find the **Microsoft 365 E5** item.</span></span> <span data-ttu-id="7dfd7-301">將滑鼠指標停留在上面，並且按一下 [開始免費試用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-301">Hover your mouse pointer over it and click **Start free trial**.</span></span>

4. <span data-ttu-id="7dfd7-302">在 [Microsoft 365 E5 試用版]\*\*\*\* 頁面上，選擇要收到簡訊或電話、輸入您的電話號碼，然後按一下 [傳送簡訊給我]\*\*\*\* 或 [打電話給我]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-302">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span>

5. <span data-ttu-id="7dfd7-303">在 [確認訂單]\*\*\*\* 頁面上，按一下 [立即試用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-303">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="7dfd7-304">在 [訂單收據]\*\*\*\* 頁面上，按一下 [繼續]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-304">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="7dfd7-305">在 Microsoft 365 系統管理中心，按一下 [作用中使用者]\*\*\*\*，然後您的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-305">In the Microsoft 365 admin center, click **Active users**, and then your administrator account.</span></span>

8. <span data-ttu-id="7dfd7-306">按一下 [產品授權]\*\*\*\* 的 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-306">Click **Edit** for **Product licenses**.</span></span>

9. <span data-ttu-id="7dfd7-307">關閉 Office 365 企業版 E5 授權，然後開啟 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-307">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

10. <span data-ttu-id="7dfd7-308">按一下 [儲存 > 關閉 > 關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-308">Click **Save > Close > Close**.</span></span>

<span data-ttu-id="7dfd7-309">接下來，請為所有其他帳戶 (使用者 2、使用者 3、使用者 4 和使用者 5) 重複先前程序的步驟 8 至 11。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-309">Next, repeat steps 8 and 9 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7dfd7-310">Microsoft 365 E5 試用版訂閱的期限是 30 天。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-310">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="7dfd7-311">在永久測試環境中，將此試用訂閱轉換為具少數授權數的付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-311">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span> 
  
### <a name="results"></a><span data-ttu-id="7dfd7-312">結果</span><span class="sxs-lookup"><span data-stu-id="7dfd7-312">Results</span></span>

<span data-ttu-id="7dfd7-313">測試環境現在擁有：</span><span class="sxs-lookup"><span data-stu-id="7dfd7-313">Your test environment now has:</span></span>
  
- <span data-ttu-id="7dfd7-314">Microsoft 365 E5 試用版訂閱。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-314">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="7dfd7-315">您的所有適用使用者帳戶皆可使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-315">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="7dfd7-316">模擬且簡化的內部網路。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-316">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="7dfd7-317">這是您的最終設定。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-317">This is your final configuration.</span></span>
  
![模擬企業基本設定階段 2](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="7dfd7-319">您現在已準備好嘗試 [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="7dfd7-319">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="7dfd7-320">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7dfd7-320">Next steps</span></span>

<span data-ttu-id="7dfd7-321">探索這些額外的測試實驗室指南集合：</span><span class="sxs-lookup"><span data-stu-id="7dfd7-321">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="7dfd7-322">身分識別</span><span class="sxs-lookup"><span data-stu-id="7dfd7-322">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="7dfd7-323">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="7dfd7-323">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="7dfd7-324">資訊保護</span><span class="sxs-lookup"><span data-stu-id="7dfd7-324">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="7dfd7-325">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7dfd7-325">See also</span></span>

[<span data-ttu-id="7dfd7-326">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="7dfd7-326">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7dfd7-327">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="7dfd7-327">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7dfd7-328">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="7dfd7-328">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
