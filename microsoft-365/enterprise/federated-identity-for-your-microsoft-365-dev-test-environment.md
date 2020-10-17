---
title: Microsoft 365 測試環境的同盟身分識別
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: 摘要：設定適用於 Microsoft 365 測試環境的同盟驗證。
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487681"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="bfb67-103">Microsoft 365 測試環境的同盟身分識別</span><span class="sxs-lookup"><span data-stu-id="bfb67-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="bfb67-104">*此測試實驗室指南可用於 enterprise 和 Office 365 企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="bfb67-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="bfb67-p101">Microsoft 365 支援同盟身分識別。這表示 Microsoft 365 的連線使用者指的是 Microsoft 365 信任的同盟驗證伺服器，而不是執行認證本身的驗證。如果使用者的認證正確，同盟驗證伺服器會發出安全性權杖，用戶端再傳送到 Microsoft 365 做為驗證證明。同盟身分識別可進行 Microsoft 365 訂閱驗證的卸載與擴展，以及進階驗證及安全性案例。</span><span class="sxs-lookup"><span data-stu-id="bfb67-p101">Microsoft 365 supports federated identity. This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="bfb67-109">本文說明如何設定您的 Microsoft 365 測試環境的同盟驗證，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bfb67-109">This article describes how to configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![適用於 Microsoft 365 測試環境的同盟驗證](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="bfb67-111">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="bfb67-111">This configuration consists of:</span></span>
  
- <span data-ttu-id="bfb67-112">Microsoft 365 E5 試用版或實際執行訂閱。</span><span class="sxs-lookup"><span data-stu-id="bfb67-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="bfb67-113">簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路之子網上的五台虛擬機器所組成 (DC1、APP1、CLIENT1、ADFS1 和 PROXY1) 。</span><span class="sxs-lookup"><span data-stu-id="bfb67-113">A simplified organization intranet connected to the internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="bfb67-114">Azure AD Connect 會在 APP1 上執行，將 Active Directory 網域服務網域中的帳戶清單同步處理至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="bfb67-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="bfb67-115">PROXY1 會接收傳入的驗證要求。</span><span class="sxs-lookup"><span data-stu-id="bfb67-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="bfb67-116">ADFS1 會使用 DC1 驗證憑證，併發出安全性權杖。</span><span class="sxs-lookup"><span data-stu-id="bfb67-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="bfb67-117">設定此測試環境包含五個階段：</span><span class="sxs-lookup"><span data-stu-id="bfb67-117">Setting up this test environment involves five phases:</span></span>
- [<span data-ttu-id="bfb67-118">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="bfb67-118">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="bfb67-119">階段 2：建立 AD FS 伺服器</span><span class="sxs-lookup"><span data-stu-id="bfb67-119">Phase 2: Create the AD FS server</span></span>](#phase-2-create-the-ad-fs-server)
- [<span data-ttu-id="bfb67-120">階段 3：建立 Web Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="bfb67-120">Phase 3: Create the web proxy server</span></span>](#phase-3-create-the-web-proxy-server)
- [<span data-ttu-id="bfb67-121">階段 4：建立自我簽署的憑證並設定 ADFS1 及 PROXY1</span><span class="sxs-lookup"><span data-stu-id="bfb67-121">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [<span data-ttu-id="bfb67-122">階段5：設定 Microsoft 365 的同盟身分識別</span><span class="sxs-lookup"><span data-stu-id="bfb67-122">Phase 5: Configure Microsoft 365 for federated identity</span></span>](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> <span data-ttu-id="bfb67-123">您無法使用 Azure 試用訂閱來設定此測試環境。</span><span class="sxs-lookup"><span data-stu-id="bfb67-123">You can't configure this test environment with an Azure Trial subscription.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="bfb67-124">階段 1：設定適用於 Microsoft 365 測試環境的密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="bfb67-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="bfb67-125">依照 [Microsoft 365 的密碼雜湊同步](password-hash-sync-m365-ent-test-environment.md)處理中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="bfb67-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="bfb67-126">您產生的設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="bfb67-126">Your resulting configuration looks like this:</span></span>
  
![使用密碼雜湊同步處理測試環境的模擬企業](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="bfb67-128">此組態包含：</span><span class="sxs-lookup"><span data-stu-id="bfb67-128">This configuration consists of:</span></span>
  
- <span data-ttu-id="bfb67-129">Microsoft 365 E5 試用版或付費訂閱。</span><span class="sxs-lookup"><span data-stu-id="bfb67-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="bfb67-130">簡化的組織內部網路連接至網際網路，由 Azure 虛擬網路子網上的 DC1、APP1 和 CLIENT1 虛擬機器所組成。</span><span class="sxs-lookup"><span data-stu-id="bfb67-130">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="bfb67-131">Azure AD Connect 會在 APP1 執行，以便定期將 TESTLAB Active Directory 網域服務 (AD DS) 網域同步處理至您的 Microsoft 365 訂閱的 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="bfb67-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="bfb67-132">階段 2：建立 AD FS 伺服器</span><span class="sxs-lookup"><span data-stu-id="bfb67-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="bfb67-133">AD FS 伺服器在 Microsoft 365 和 DC1 上裝載 corp.contoso.com 網域中的帳戶之間提供同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="bfb67-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="bfb67-134">若要為 ADFS1 建立 Azure 虛擬機器，請為基本設定填入訂閱和資源群組的名稱和 Azure 位置，然後在本機電腦上的 Azure PowerShell 命令提示字元執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="bfb67-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="bfb67-135">接下來，使用 ADFS1 本機系統管理員帳戶名稱和密碼，以使用 [Azure 入口網站](https://portal.azure.com)連線到 ADFS1 虛擬機器，然後開啟 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="bfb67-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="bfb67-136">若要檢查 ADFS1 和 DC1 之間的名稱解析和網路通訊，請執行 **ping dc1.corp.contoso.com** 命令，並檢查有四個回覆。</span><span class="sxs-lookup"><span data-stu-id="bfb67-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="bfb67-137">接下來在 ADFS1 上的 Windows PowerShell 命令提示字元使用以下命令將 ADFS1 虛擬機器加入 CORP 網域。</span><span class="sxs-lookup"><span data-stu-id="bfb67-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="bfb67-138">您產生的設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="bfb67-138">Your resulting configuration looks like this:</span></span>
  
![將 AD FS 伺服器新增至 Microsoft 365 測試環境的 DirSync](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="bfb67-140">階段 3：建立 Web Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="bfb67-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="bfb67-141">PROXY1 提供嘗試驗證 ADFS1 的使用者之間驗證訊息的 Proxy。</span><span class="sxs-lookup"><span data-stu-id="bfb67-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="bfb67-142">若要為 PROXY1 建立 Azure 虛擬機器，請填入資源群組的名稱和 Azure 位置，然後在本機電腦上的 Azure PowerShell 命令提示字元執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="bfb67-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="bfb67-143">PROXY1 指派了靜態公用 IP 位址，因為您將建立指向它的公開 DNS 記錄，且當您重新啟動 PROXY1 虛擬機器時它不得變更。</span><span class="sxs-lookup"><span data-stu-id="bfb67-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span>
  
<span data-ttu-id="bfb67-144">接下來，新增規則至網路安全性群組的 CorpNet 子網，以允許來自網際網路的未經許可輸入流量，以 PROXY1's 私人 IP 位址和 TCP 埠443。</span><span class="sxs-lookup"><span data-stu-id="bfb67-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="bfb67-145">在本機電腦的 Azure PowerShell 命令提示字元中執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="bfb67-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="bfb67-146">接下來，使用 PROXY1 本機系統管理員帳戶名稱和密碼，以使用 [Azure 入口網站](https://portal.azure.com)連線到 PROXY1 虛擬機器，然後在 PROXY1 上開啟 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="bfb67-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="bfb67-147">若要檢查 PROXY1 和 DC1 之間的名稱解析和網路通訊，請執行 **ping dc1.corp.contoso.com** 命令，並檢查有四個回覆。</span><span class="sxs-lookup"><span data-stu-id="bfb67-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="bfb67-148">接下來在 PROXY1 上的 Windows PowerShell 命令提示字元使用以下命令將 PROXY1 虛擬機器加入 CORP 網域。</span><span class="sxs-lookup"><span data-stu-id="bfb67-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="bfb67-149">使用本機電腦上的下列 Azure PowerShell 命令，顯示 PROXY1 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="bfb67-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer.</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="bfb67-p106">接下來，與公用 DNS 提供者合作，建立 **fs.testlab.**\<*your DNS domain name*> 的新公用 DNS A 記錄，其會解析到 **Write-Host** 命令所顯示的 IP 位址。**fs.testlab.**\<*your DNS domain name*> 也稱為*同盟服務 FQDN*。</span><span class="sxs-lookup"><span data-stu-id="bfb67-p106">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<*your DNS domain name*> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<*your DNS domain name*> is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="bfb67-154">接下來，使用 CORP\\User1 認證，以使用 [Azure 入口網站](https://portal.azure.com)連線到 DC1 虛擬機器，然後在系統管理員層級 Windows PowerShell 命令提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bfb67-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="bfb67-155">這些命令會建立內部 DNS A 記錄，讓 Azure 虛擬網路上的虛擬機器能夠解析內部同盟服務 FQDN，以 ADFS1's 私人 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="bfb67-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation service FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="bfb67-156">您產生的設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="bfb67-156">Your resulting configuration looks like this:</span></span>
  
![將 Web 應用程式 Proxy 伺服器新增至 Microsoft 365 測試環境的 DirSync](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="bfb67-158">階段 4：建立自我簽署的憑證並設定 ADFS1 及 PROXY1</span><span class="sxs-lookup"><span data-stu-id="bfb67-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="bfb67-159">在這個階段，您可以為同盟服務 FQDN 建立自我簽署的數位憑證，並將 ADFS1 和 PROXY1 設定為 AD FS 伺服器陣列。</span><span class="sxs-lookup"><span data-stu-id="bfb67-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="bfb67-160">首先，使用 CORP\\User1 認證，以使用 [Azure 入口網站](https://portal.azure.com)連線到 DC1 虛擬機器，然後開啟系統管理員層級 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="bfb67-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="bfb67-161">接下來，在 DC1 上的 Windows PowerShell 命令提示字元處，使用此命令建立 AD FS 服務帳戶：</span><span class="sxs-lookup"><span data-stu-id="bfb67-161">Next, create an AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="bfb67-162">請注意，此命令會提示您提供帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="bfb67-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="bfb67-163">選擇強式密碼，並將其記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="bfb67-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="bfb67-164">您將需要此階段和階段5。</span><span class="sxs-lookup"><span data-stu-id="bfb67-164">You will need it for this phase and for Phase 5.</span></span>
  
<span data-ttu-id="bfb67-p108">使用 CORP\\User1 認證以使用 [Azure 入口網站](https://portal.azure.com)連線到 ADFS1 虛擬機器。開啟 ADFS1 上的系統管理員層級 Windows PowerShell 命令提示字元，填入您的同盟服務 FQDN，然後執行這些命令以建立自我簽署的憑證：</span><span class="sxs-lookup"><span data-stu-id="bfb67-p108">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="bfb67-167">接下來，使用這些步驟，將新的自我簽署憑證儲存為檔案。</span><span class="sxs-lookup"><span data-stu-id="bfb67-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="bfb67-168">選取 [ **開始**]，輸入 **mmc.exe**，然後按 **enter**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-168">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="bfb67-169">選取 **[** 檔案] [  >  **新增/移除嵌入式管理單元**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-169">Select **File** > **Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="bfb67-170">在 [ **新增或移除嵌入式管理單元**] 中，按兩下可用之嵌入式管理單元清單中的 [ **證書** ]，選取 [ **電腦帳戶**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="bfb67-171">在 [ **選取電腦**] 中，選取 **[完成]**，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-171">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="bfb67-172">在樹狀窗格中，開啟 **[憑證 (本機電腦)] > [個人] > [憑證]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="bfb67-173">選取並按住 (或以滑鼠右鍵按一下您的同盟服務 FQDN) 憑證，選取 [ **所有**工作]，然後選取 [ **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-173">Select and hold (or right-click) the certificate with your federation service FQDN, select **All tasks**, and then select **Export**.</span></span>
    
7. <span data-ttu-id="bfb67-174">在 [ **歡迎** ] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-174">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="bfb67-175">在 [ **匯出私密金鑰** ] 頁面上，選取 **[是]**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-175">On the **Export Private Key** page, select **Yes**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="bfb67-176">在 [ **匯出檔案格式** ] 頁面上，選取 [ **匯出所有擴充屬性**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-176">On the **Export File Format** page, select **Export all extended properties**, and then select **Next**.</span></span>
    
10. <span data-ttu-id="bfb67-177">在 [**安全性**] 頁面上，選取 [**密碼**]，然後在 [**密碼**] 和 [**確認密碼**] 中輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="bfb67-177">On the **Security** page, select **Password** and enter a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="bfb67-178">在 [ **要匯出的** 檔案] 頁面上，選取 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-178">On the **File to Export** page, select **Browse**.</span></span>
    
12. <span data-ttu-id="bfb67-179">流覽至 [ **C： \\ 證書**] 資料夾，在 [**檔案名**] 中輸入**SSL** ，然後選取 [**儲存]。**</span><span class="sxs-lookup"><span data-stu-id="bfb67-179">Browse to the **C:\\Certs** folder, enter **SSL** in **File name**, and then select **Save.**</span></span>
    
13. <span data-ttu-id="bfb67-180">在 [ **要匯出的** 檔案] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-180">On the **File to Export** page, select **Next**.</span></span>
    
14. <span data-ttu-id="bfb67-181">在 [ **完成憑證匯出] 嚮導** 頁面上，選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-181">On the **Completing the Certificate Export Wizard** page, select **Finish**.</span></span> <span data-ttu-id="bfb67-182">出現提示時，請選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-182">When prompted, select **OK**.</span></span>
    
<span data-ttu-id="bfb67-183">接下來，在 ADFS1 上的 Windows PowerShell 命令提示字元中使用此命令安裝 AD FS 服務：</span><span class="sxs-lookup"><span data-stu-id="bfb67-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="bfb67-184">等待安裝完成。</span><span class="sxs-lookup"><span data-stu-id="bfb67-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="bfb67-185">接下來，使用下列步驟設定 AD FS 服務：</span><span class="sxs-lookup"><span data-stu-id="bfb67-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="bfb67-186">選取 [ **開始**]，然後選取 [ **伺服器管理員** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="bfb67-186">Select **Start**, and then select the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="bfb67-187">在 [伺服器管理員] 的樹狀窗格中，選取 [ **AD FS**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-187">In the tree pane of Server Manager, select **AD FS**.</span></span>
    
3. <span data-ttu-id="bfb67-188">在頂端的工具列中，選取橙色的警告符號，然後選取 [在 **此伺服器上設定同盟服務**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-188">In the tool bar at the top, select the orange caution symbol, and then select **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="bfb67-189">在 [Active Directory Federation Services 設定向導] 的 [ **歡迎** ] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="bfb67-190">在 [連線 **到 AD DS]** 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-190">On the **Connect to AD DS** page, select **Next**.</span></span>
    
6. <span data-ttu-id="bfb67-191">在 [指定服務內容]\*\*\*\* 頁面上：</span><span class="sxs-lookup"><span data-stu-id="bfb67-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="bfb67-192">在 [ **SSL 憑證**] 中，選取向下箭號，然後選取具有同盟服務 FQDN 名稱的憑證。</span><span class="sxs-lookup"><span data-stu-id="bfb67-192">For **SSL Certificate**, select the down arrow, and then select the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="bfb67-193">在 [ **同盟服務顯示名稱**] 中，輸入您虛擬組織的名稱。</span><span class="sxs-lookup"><span data-stu-id="bfb67-193">In **Federation Service Display Name**, enter the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="bfb67-194">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bfb67-194">Select **Next**.</span></span>
    
7. <span data-ttu-id="bfb67-195">在 [**指定服務帳戶**] 頁面上，選取 [**選取\*\*\*\*帳戶名稱**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-195">On the **Specify Service Account** page, select **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="bfb67-196">在 [ **選取使用者或服務帳戶**] 中，輸入 **ADFS-服務**]，選取 [ **檢查名稱**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-196">In **Select User or Service Account**, enter **ADFS-Service**, select **Check Names**, and then select **OK**.</span></span>
    
9. <span data-ttu-id="bfb67-197">在 [ **帳戶密碼**] 中輸入 ADFS-Service 帳戶的密碼，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-197">In **Account Password**, enter the password for the ADFS-Service account, and then select **Next**.</span></span>
    
10. <span data-ttu-id="bfb67-198">在 [ **指定設定資料庫** ] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-198">On the **Specify Configuration Database** page, select **Next**.</span></span>
    
11. <span data-ttu-id="bfb67-199">在 [ **複查選項** ] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-199">On the **Review Options** page, select **Next**.</span></span>
    
12. <span data-ttu-id="bfb67-200">在 [ **先決條件檢查** ] 頁面上，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-200">On the **Pre-requisite Checks** page, select **Configure**.</span></span>

13. <span data-ttu-id="bfb67-201">在 [ **結果** ] 頁面上，選取 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-201">On the **Results** page, select **Close**.</span></span>
    
14. <span data-ttu-id="bfb67-202">選取 [ **開始**]，選取 power 圖示，選取 [ **重新開機**]，然後選取 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-202">Select **Start**, select the power icon, select **Restart**, and then select **Continue**.</span></span>
    
<span data-ttu-id="bfb67-203">使用 CORP\\User1 帳戶認證，從 [Azure 入口網站](https://portal.azure.com)連線到 PROXY1。</span><span class="sxs-lookup"><span data-stu-id="bfb67-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="bfb67-204">接下來，使用這些步驟在 **PROXY1 和 APP1** 上安裝自我簽署的憑證。</span><span class="sxs-lookup"><span data-stu-id="bfb67-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="bfb67-205">選取 [ **開始**]，輸入 **mmc.exe**，然後按 **enter**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-205">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="bfb67-206">選取 [檔案] **> [新增/移除嵌入式管理單元**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-206">Select **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="bfb67-207">在 [ **新增或移除嵌入式管理單元**] 中，按兩下可用之嵌入式管理單元清單中的 [ **證書** ]，選取 [ **電腦帳戶**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="bfb67-208">在 [ **選取電腦**] 中，選取 **[完成]**，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-208">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="bfb67-209">在樹狀窗格中，) 個人憑證中，開啟\*\* (本機電腦的憑證\*\*  >  **Personal**  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="bfb67-209">In the tree pane, open **Certificates (Local Computer)** > **Personal** > **Certificates**.</span></span>
    
6. <span data-ttu-id="bfb67-210">選取並按住 (，或以滑鼠右鍵按一下 [) **個人**]，選取 [ **所有**工作]，然後選取 [匯 **入**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-210">Select and hold (or right-click) **Personal**, select **All tasks**, and then select **Import**.</span></span>
    
7. <span data-ttu-id="bfb67-211">在 [ **歡迎** ] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-211">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="bfb67-212">在 [**要匯入**的檔案] 頁面上，輸入\*\* \\ \\ adfs1 \\ 證書的 \\ ssl .pfx\*\*]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-212">On the **File to Import** page, enter **\\\\adfs1\\certs\\ssl.pfx**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="bfb67-213">在 [ **私密金鑰保護** ] 頁面上，于 [ **密碼**] 中輸入憑證密碼，然後選取 **[下一步]。**</span><span class="sxs-lookup"><span data-stu-id="bfb67-213">On the **Private key protection** page, enter the certificate password in **Password**, and then select **Next.**</span></span>
    
10. <span data-ttu-id="bfb67-214">在 [ **憑證存放區** ] 頁面上，選取 **[下一步]。**</span><span class="sxs-lookup"><span data-stu-id="bfb67-214">On the **Certificate store** page, select **Next.**</span></span>
    
11. <span data-ttu-id="bfb67-215">在 [ **完成** ] 頁面上，選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-215">On the **Completing** page, select **Finish**.</span></span>
    
12. <span data-ttu-id="bfb67-216">在 [ **憑證存放區** ] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-216">On the **Certificate Store** page, select **Next**.</span></span>
    
13. <span data-ttu-id="bfb67-217">出現提示時，請選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-217">When prompted, select **OK**.</span></span>
    
14. <span data-ttu-id="bfb67-218">在樹狀窗格中，選取 [ **憑證**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-218">In the tree pane, select **Certificates**.</span></span>
    
15. <span data-ttu-id="bfb67-219">選取並按住 (，或以滑鼠右鍵按一下憑證) ，然後選取 [ **複製**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-219">Select and hold (or right-click) the certificate, and then select **Copy**.</span></span>
    
16. <span data-ttu-id="bfb67-220">在樹狀窗格中，開啟 [**信任的憑證授權單位**單位]  >  **憑證**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-220">In the tree pane, open **Trusted Root Certification Authorities** > **Certificates**.</span></span>
    
17. <span data-ttu-id="bfb67-221">將滑鼠指標移至已安裝憑證的清單下，選取並按住 (或以滑鼠右鍵按一下 [) ]，然後選取 [ **貼**上]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-221">Move your mouse pointer below the list of installed certificates, select and hold (or right-click), and then select **Paste**.</span></span>
    
<span data-ttu-id="bfb67-222">開啟系統管理員層級 PowerShell 命令提示字元，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bfb67-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="bfb67-223">等待安裝完成。</span><span class="sxs-lookup"><span data-stu-id="bfb67-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="bfb67-224">使用下列步驟設定 Web 應用程式 Proxy 服務以使用 ADFS1 作為其同盟伺服器：</span><span class="sxs-lookup"><span data-stu-id="bfb67-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="bfb67-225">選取 [ **開始**]，然後選取 [ **伺服器管理員**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-225">Select **Start**, and then select **Server Manager**.</span></span>
    
2. <span data-ttu-id="bfb67-226">在樹狀窗格中，選取 [ **遠端存取**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-226">In the tree pane, select **Remote Access**.</span></span>
    
3. <span data-ttu-id="bfb67-227">在頂端的工具列中，選取橙色的警告符號，然後選取 [ **開啟 Web 應用程式 Proxy]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-227">In the tool bar at the top, select the orange caution symbol, and then select **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="bfb67-228">在 [Web 應用程式 Proxy 設定向導] 的 [ **歡迎** ] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="bfb67-229">在 [同盟伺服器]\*\*\*\* 頁面上：</span><span class="sxs-lookup"><span data-stu-id="bfb67-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="bfb67-230">在 [ **同盟服務名稱** ] 方塊中，輸入您的同盟服務 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bfb67-230">In the **Federation service name** box, enter your federation service FQDN.</span></span>
    
  - <span data-ttu-id="bfb67-231">在 [ **使用者名稱** ] 方塊中，輸入 **CORP \\ User1**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-231">In the **User name** box, enter **CORP\\User1**.</span></span>
    
  - <span data-ttu-id="bfb67-232">在 [ **密碼** ] 方塊中，輸入 User1 帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="bfb67-232">In the **Password** box, enter the password for the User1 account.</span></span>
    
  - <span data-ttu-id="bfb67-233">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bfb67-233">Select **Next**.</span></span>
    
6. <span data-ttu-id="bfb67-234">在 [ **AD FS Proxy 憑證** ] 頁面上，選取向下箭號，選取具有您同盟服務 FQDN 的憑證，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-234">On the **AD FS Proxy Certificate** page, select the down arrow, select the certificate with your federation service FQDN, and then select **Next**.</span></span>
    
7. <span data-ttu-id="bfb67-235">在 [ **確認** ] 頁面上，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-235">On the **Confirmation** page, select **Configure**.</span></span>
    
8. <span data-ttu-id="bfb67-236">在 [ **結果** ] 頁面上，選取 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-236">On the **Results** page, select **Close**.</span></span>
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="bfb67-237">階段5：設定 Microsoft 365 的同盟身分識別</span><span class="sxs-lookup"><span data-stu-id="bfb67-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="bfb67-238">以 CORP\\User1 帳戶認證使用 [Azure 入口網站](https://portal.azure.com)連線到 APP1 虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="bfb67-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="bfb67-239">使用下列步驟為同盟驗證設定 Azure AD Connect 與 Microsoft 365 訂閱：</span><span class="sxs-lookup"><span data-stu-id="bfb67-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="bfb67-240">從桌面，按兩下 [Azure AD Connect]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bfb67-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="bfb67-241">在 [ **歡迎使用 AZURE AD Connect]** 頁面上，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-241">On the **Welcome to Azure AD Connect** page, select **Configure**.</span></span>
    
3. <span data-ttu-id="bfb67-242">在 [ **其他** 工作] 頁面上，選取 [ **變更使用者登入**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-242">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="bfb67-243">在 [連線 **到 AZURE AD]** 頁面上，輸入您的全域系統管理員帳戶名稱和密碼，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-243">On the **Connect to Azure AD** page, enter your global administrator account name and password, and then select **Next**.</span></span>
    
5. <span data-ttu-id="bfb67-244">在 [ **使用者登入** ] 頁面上，選取 [ **同盟與 AD FS**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-244">On the **User sign-in** page, select **Federation with AD FS**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="bfb67-245">在 [ **AD fs 伺服器**陣列] 頁面上，選取 [**使用現有的 AD FS 伺服器陣列**]，在 [**伺服器名稱**] 方塊中輸入**ADFS1** ，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-245">On the **AD FS farm** page, select **Use an existing AD FS farm**, enter **ADFS1** in the **Server Name** box, and then select **Next**.</span></span>
    
7. <span data-ttu-id="bfb67-246">當系統提示您輸入伺服器認證時，請輸入 CORP \\ User1 帳戶的認證，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then select **OK**.</span></span>
    
8. <span data-ttu-id="bfb67-247">在 [**網域管理員**認證] 頁面上，于 [使用者**名稱**] 方塊中輸入**CORP \\ User1** ，然後在 [**密碼**] 方塊中輸入帳戶密碼，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-247">On the **Domain Administrator** credentials page, enter **CORP\\User1** in the **Username** box, enter the account password in the **Password** box, and then select **Next**.</span></span>
    
9. <span data-ttu-id="bfb67-248">在 [ **AD FS 服務帳戶**] 頁面上，于 [**網域使用者名稱**] 方塊中輸入**CORP \\ ADFS 服務**，在 [**網域使用者密碼**] 方塊中輸入帳戶密碼，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-248">On the **AD FS service account** page, enter **CORP\\ADFS-Service** in the **Domain Username** box, enter the account password in the **Domain User Password** box, and then select **Next**.</span></span>
    
10. <span data-ttu-id="bfb67-249">在 [ **AZURE AD 網域** ] 頁面的 [ **網域**] 中，選取您先前在階段1中建立並新增至您訂閱的功能變數名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bfb67-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain that you previously created and added to your subscription in Phase 1, and then select **Next**.</span></span>
    
11. <span data-ttu-id="bfb67-250">在 [ **準備設定** ] 頁面上，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-250">On the **Ready to configure** page, select **Configure**.</span></span>
    
12. <span data-ttu-id="bfb67-251">在 [ **安裝完成** ] 頁面上，選取 [ **驗證**]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-251">On the **Installation complete** page, select **Verify**.</span></span>
    
    <span data-ttu-id="bfb67-252">您應該會看到訊息，指出內部網路和網際網路設定皆已驗證。</span><span class="sxs-lookup"><span data-stu-id="bfb67-252">You should see messages indicating that both the intranet and internet configuration was verified.</span></span>
    
13. <span data-ttu-id="bfb67-253">在 [ **安裝完成** ] 頁面上 **，選取 [** 結束]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-253">On the **Installation complete** page, select **Exit**.</span></span>
    
<span data-ttu-id="bfb67-254">若要證明同盟驗證為正常運作：</span><span class="sxs-lookup"><span data-stu-id="bfb67-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="bfb67-255">在本機電腦上開啟瀏覽器的新私人執行個體，然後移至 [https://admin.microsoft.com](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="bfb67-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="bfb67-256">若為登入認證，請輸入**user1@** \<*the domain created in Phase 1*> 。</span><span class="sxs-lookup"><span data-stu-id="bfb67-256">For the sign-in credentials, enter **user1@**\<*the domain created in Phase 1*>.</span></span>
    
    <span data-ttu-id="bfb67-257">例如，如果您的測試網域是 **testlab.contoso.com**，您可以輸入 "user1@testlab.contoso.com"。</span><span class="sxs-lookup"><span data-stu-id="bfb67-257">For example, if your test domain is **testlab.contoso.com**, you would enter "user1@testlab.contoso.com".</span></span> <span data-ttu-id="bfb67-258">按 **tab** 鍵或允許 Microsoft 365 自動重新導向您。</span><span class="sxs-lookup"><span data-stu-id="bfb67-258">Press the **Tab** key or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="bfb67-259">您現在應該會看到 [連線 **不是私人** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="bfb67-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="bfb67-260">因為您已在桌上型電腦無法驗證的 ADFS1 上安裝自我簽署憑證，所以您會看到這種情況。</span><span class="sxs-lookup"><span data-stu-id="bfb67-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer can't validate.</span></span> <span data-ttu-id="bfb67-261">在同盟驗證的實際執行部署中，您可以使用受信任的憑證授權單位單位的憑證，而您的使用者將不會看到此頁面。</span><span class="sxs-lookup"><span data-stu-id="bfb67-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="bfb67-262">在 [**您的連線不是私人**] 頁面上，選取 [**高級**]，然後\*\* \<*your federation service FQDN*> \*\*選取 [繼續]。</span><span class="sxs-lookup"><span data-stu-id="bfb67-262">On the **Your connection is not private** page, select **Advanced**, and then select **Proceed to \<*your federation service FQDN*>**.</span></span> 
    
4. <span data-ttu-id="bfb67-263">在具有虛構組織名稱的頁面上，以下列動作登入：</span><span class="sxs-lookup"><span data-stu-id="bfb67-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="bfb67-264">名稱的 **CORP\\User1**</span><span class="sxs-lookup"><span data-stu-id="bfb67-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="bfb67-265">User1 帳戶的密碼</span><span class="sxs-lookup"><span data-stu-id="bfb67-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="bfb67-266">您應該會看到 [Microsoft Office 首頁]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="bfb67-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="bfb67-p112">此程序會示範試用訂閱與 DC1 上裝載的 AD DS corp.contoso.com 網域的同盟。以下是驗證程序的基本概念：</span><span class="sxs-lookup"><span data-stu-id="bfb67-p112">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="bfb67-269">當您使用登入帳戶名稱內在階段 1 建立的同盟網域時，Microsoft 365 會將您的瀏覽器重新導向至同盟服務 FQDN 和 PROXY1。</span><span class="sxs-lookup"><span data-stu-id="bfb67-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="bfb67-270">PROXY1 會向您的本機電腦傳送虛構公司登入頁面。</span><span class="sxs-lookup"><span data-stu-id="bfb67-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="bfb67-271">當您將 CORP\\User1 和密碼傳送給 PROXY1，PROXY1 會轉寄給 ADFS1。</span><span class="sxs-lookup"><span data-stu-id="bfb67-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="bfb67-272">ADFS1 會使用 DC1 驗證 CORP\\User1 和密碼，並向您的本機電腦傳送安全性權杖。</span><span class="sxs-lookup"><span data-stu-id="bfb67-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="bfb67-273">本機電腦會將安全性權杖傳送到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="bfb67-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="bfb67-274">Microsoft 365 會驗證安全性權杖是由 ADFS1 所建立，並允許存取。</span><span class="sxs-lookup"><span data-stu-id="bfb67-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="bfb67-p113">您的試用訂閱現在設定使用同盟驗證。您可以將此開發/測試環境用於進階驗證案例。</span><span class="sxs-lookup"><span data-stu-id="bfb67-p113">Your trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="bfb67-277">下一步</span><span class="sxs-lookup"><span data-stu-id="bfb67-277">Next step</span></span>

<span data-ttu-id="bfb67-278">當您準備好在 Azure 中部署 Microsoft 365 的實際執行、高可用性同盟驗證時，請參閱在 [azure 中部署 microsoft 365 的高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)。</span><span class="sxs-lookup"><span data-stu-id="bfb67-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
