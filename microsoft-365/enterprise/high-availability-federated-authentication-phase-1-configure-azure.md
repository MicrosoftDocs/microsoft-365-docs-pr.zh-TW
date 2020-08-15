---
title: 高可用性同盟驗證階段1設定 Azure
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
ms.assetid: 91266aac-4d00-4b5f-b424-86a1a837792c
description: 摘要：設定 Microsoft Azure 基礎結構，以裝載 Microsoft 365 的高可用性同盟驗證。
ms.openlocfilehash: a99259e8c60346665f76aeba3a8a440e0f9061f0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688768"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a><span data-ttu-id="7aca9-103">高可用性同盟驗證階段 1：設定 Azure</span><span class="sxs-lookup"><span data-stu-id="7aca9-103">High availability federated authentication Phase 1: Configure Azure</span></span>

<span data-ttu-id="7aca9-104">在此階段中，您會在 Azure 中建立資源群組、虛擬網路 (VNet) 和可用性設定，以在階段2、3和4中主控虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="7aca9-104">In this phase, you create the resource groups, virtual network (VNet), and availability sets in Azure that will host the virtual machines in phases 2, 3, and 4.</span></span> <span data-ttu-id="7aca9-105">您必須先完成此階段，再移至 [階段2：設定網域控制站](high-availability-federated-authentication-phase-2-configure-domain-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="7aca9-105">You must complete this phase before moving on to [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="7aca9-106">請參閱 [在 Azure 中部署 Microsoft 365 的高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) ，以瞭解所有階段。</span><span class="sxs-lookup"><span data-stu-id="7aca9-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
<span data-ttu-id="7aca9-107">Azure 必須布建下列基本元件：</span><span class="sxs-lookup"><span data-stu-id="7aca9-107">Azure must be provisioned with these basic components:</span></span>
  
- <span data-ttu-id="7aca9-108">資源群組</span><span class="sxs-lookup"><span data-stu-id="7aca9-108">Resource groups</span></span>
    
- <span data-ttu-id="7aca9-109">跨部署 Azure 虛擬網路 (VNet) 搭配用於主控 Azure 虛擬機器的子網</span><span class="sxs-lookup"><span data-stu-id="7aca9-109">A cross-premises Azure virtual network (VNet) with subnets for hosting the Azure virtual machines</span></span>
    
- <span data-ttu-id="7aca9-110">用於執行子網路隔離的網路安全性群組</span><span class="sxs-lookup"><span data-stu-id="7aca9-110">Network security groups for performing subnet isolation</span></span>
    
- <span data-ttu-id="7aca9-111">可用性設定組</span><span class="sxs-lookup"><span data-stu-id="7aca9-111">Availability sets</span></span>
    
## <a name="configure-azure-components"></a><span data-ttu-id="7aca9-112">設定 Azure 元件</span><span class="sxs-lookup"><span data-stu-id="7aca9-112">Configure Azure components</span></span>

<span data-ttu-id="7aca9-113">在開始設定 Azure 元件之前，填寫下列表格。</span><span class="sxs-lookup"><span data-stu-id="7aca9-113">Before you begin configuring Azure components, fill in the following tables.</span></span> <span data-ttu-id="7aca9-114">為了可在設定 Azure 的程序中協助您，請列印此節並記下所需資訊，或將此節複製到一份文件並加以填寫。</span><span class="sxs-lookup"><span data-stu-id="7aca9-114">To assist you in the procedures for configuring Azure, print this section and write down the needed information or copy this section to a document and fill it in.</span></span> <span data-ttu-id="7aca9-115">若為 VNet 的設定，請填寫表格 V。</span><span class="sxs-lookup"><span data-stu-id="7aca9-115">For the settings of the VNet, fill in Table V.</span></span>
  
|<span data-ttu-id="7aca9-116">**項目**</span><span class="sxs-lookup"><span data-stu-id="7aca9-116">**Item**</span></span>|<span data-ttu-id="7aca9-117">**組態設定**</span><span class="sxs-lookup"><span data-stu-id="7aca9-117">**Configuration setting**</span></span>|<span data-ttu-id="7aca9-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="7aca9-118">**Description**</span></span>|<span data-ttu-id="7aca9-119">**值**</span><span class="sxs-lookup"><span data-stu-id="7aca9-119">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7aca9-120">1.</span><span class="sxs-lookup"><span data-stu-id="7aca9-120">1.</span></span>  <br/> |<span data-ttu-id="7aca9-121">VNet 名稱</span><span class="sxs-lookup"><span data-stu-id="7aca9-121">VNet name</span></span>  <br/> |<span data-ttu-id="7aca9-122">要指派給 VNet (範例 FedAuthNet) 的名稱。</span><span class="sxs-lookup"><span data-stu-id="7aca9-122">A name to assign to the VNet (example FedAuthNet).</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-124">2.</span><span class="sxs-lookup"><span data-stu-id="7aca9-124">2.</span></span>  <br/> |<span data-ttu-id="7aca9-125">VNet 位置</span><span class="sxs-lookup"><span data-stu-id="7aca9-125">VNet location</span></span>  <br/> |<span data-ttu-id="7aca9-126">將包含虛擬網路的地區性 Azure 資料中心。</span><span class="sxs-lookup"><span data-stu-id="7aca9-126">The regional Azure datacenter that will contain the virtual network.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-128">3.</span><span class="sxs-lookup"><span data-stu-id="7aca9-128">3.</span></span>  <br/> |<span data-ttu-id="7aca9-129">VPN 裝置 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7aca9-129">VPN device IP address</span></span>  <br/> |<span data-ttu-id="7aca9-130">網際網路上 VPN 裝置介面的公用 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="7aca9-130">The public IPv4 address of your VPN device's interface on the Internet.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-132">4.</span><span class="sxs-lookup"><span data-stu-id="7aca9-132">4.</span></span>  <br/> |<span data-ttu-id="7aca9-133">VNet 位址空間</span><span class="sxs-lookup"><span data-stu-id="7aca9-133">VNet address space</span></span>  <br/> |<span data-ttu-id="7aca9-p103">虛擬網路的位址空間。請與您的 IT 部門合作以決定此位址空間。</span><span class="sxs-lookup"><span data-stu-id="7aca9-p103">The address space for the virtual network. Work with your IT department to determine this address space.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-137">5.</span><span class="sxs-lookup"><span data-stu-id="7aca9-137">5.</span></span>  <br/> |<span data-ttu-id="7aca9-138">IPsec 共用金鑰</span><span class="sxs-lookup"><span data-stu-id="7aca9-138">IPsec shared key</span></span>  <br/> |<span data-ttu-id="7aca9-p104">32 個字元的隨機英數字元字串，用以驗證站台對站台 VPN 連線的兩端站台。請與您的 IT 或安全性部門合作，以決定此金鑰值。或者，請參閱[建立隨機字串以作為 IPsec 的預先共用金鑰](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx)。  </span><span class="sxs-lookup"><span data-stu-id="7aca9-p104">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection. Work with your IT or security department to determine this key value. Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  </span></span><br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="7aca9-143">**表格 V：跨單位虛擬網路設定**</span><span class="sxs-lookup"><span data-stu-id="7aca9-143">**Table V: Cross-premises virtual network configuration**</span></span>
  
<span data-ttu-id="7aca9-p105">下一步，針對此解決方案的子網路填寫表格 S。所有位址空間應是無類別網域間路由選擇 (CIDR) 格式 (也稱為網路前置詞格式)。例如 10.24.64.0/20。</span><span class="sxs-lookup"><span data-stu-id="7aca9-p105">Next, fill in Table S for the subnets of this solution. All address spaces should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format. An example is 10.24.64.0/20.</span></span>
  
<span data-ttu-id="7aca9-147">針對前三個子網，根據虛擬網路位址空間，指定名稱和單一 IP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="7aca9-147">For the first three subnets, specify a name and a single IP address space based on the virtual network address space.</span></span> <span data-ttu-id="7aca9-148">針對閘道子網，使用下列各項來判斷具有 a/27 前置詞長度) 的27位位址空間 (：</span><span class="sxs-lookup"><span data-stu-id="7aca9-148">For the gateway subnet, determine the 27-bit address space (with a /27 prefix length) for the Azure gateway subnet with the following:</span></span>
  
1. <span data-ttu-id="7aca9-149">將 VNet 位址空間中的變數位元數設為 1 (閘道子網路正在使用的位元數)，其餘位元數設為 0。</span><span class="sxs-lookup"><span data-stu-id="7aca9-149">Set the variable bits in the address space of the VNet to 1, up to the bits being used by the gateway subnet, then set the remaining bits to 0.</span></span>
    
2. <span data-ttu-id="7aca9-150">將結果位元數轉換為小數，使用設定為閘道子網路大小的前置長度將其表示為位址空間。</span><span class="sxs-lookup"><span data-stu-id="7aca9-150">Convert the resulting bits to decimal and express it as an address space with the prefix length set to the size of the gateway subnet.</span></span>
    
<span data-ttu-id="7aca9-151">請參閱 [Azure 閘道子網的位址空間計算機](https://gallery.technet.microsoft.com/scriptcenter/Address-prefix-calculator-a94b6eed) ，以取得 PowerShell 命令區塊和 c # 或 Python 主控台應用程式，為您執行這種計算。</span><span class="sxs-lookup"><span data-stu-id="7aca9-151">See [Address space calculator for Azure gateway subnets](https://gallery.technet.microsoft.com/scriptcenter/Address-prefix-calculator-a94b6eed) for a PowerShell command block and C# or Python console application that performs this calculation for you.</span></span>
  
<span data-ttu-id="7aca9-152">請與您的 IT 部門合作，以從虛擬網路位址空間判斷這些位址空間。</span><span class="sxs-lookup"><span data-stu-id="7aca9-152">Work with your IT department to determine these address spaces from the virtual network address space.</span></span>
  
|<span data-ttu-id="7aca9-153">**項目**</span><span class="sxs-lookup"><span data-stu-id="7aca9-153">**Item**</span></span>|<span data-ttu-id="7aca9-154">**子網路名稱**</span><span class="sxs-lookup"><span data-stu-id="7aca9-154">**Subnet name**</span></span>|<span data-ttu-id="7aca9-155">**子網路位址空間**</span><span class="sxs-lookup"><span data-stu-id="7aca9-155">**Subnet address space**</span></span>|<span data-ttu-id="7aca9-156">**用途**</span><span class="sxs-lookup"><span data-stu-id="7aca9-156">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7aca9-157">1.</span><span class="sxs-lookup"><span data-stu-id="7aca9-157">1.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="7aca9-160">Active Directory 網域服務所使用的子網 (AD DS) 網域控制站及目錄同步處理伺服器虛擬機器 (Vm) 。</span><span class="sxs-lookup"><span data-stu-id="7aca9-160">The subnet used by the Active Directory Domain Services (AD DS) domain controller and directory synchronization server virtual machines (VMs).</span></span>  <br/> |
|<span data-ttu-id="7aca9-161">2.</span><span class="sxs-lookup"><span data-stu-id="7aca9-161">2.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="7aca9-164">AD FS Vm 所使用的子網。</span><span class="sxs-lookup"><span data-stu-id="7aca9-164">The subnet used by the AD FS VMs.</span></span>  <br/> |
|<span data-ttu-id="7aca9-165">3.</span><span class="sxs-lookup"><span data-stu-id="7aca9-165">3.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="7aca9-168">Web 應用程式 proxy Vm 所使用的子網。</span><span class="sxs-lookup"><span data-stu-id="7aca9-168">The subnet used by the web application proxy VMs.</span></span>  <br/> |
|<span data-ttu-id="7aca9-169">4.</span><span class="sxs-lookup"><span data-stu-id="7aca9-169">4.</span></span>  <br/> |<span data-ttu-id="7aca9-170">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="7aca9-170">GatewaySubnet</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="7aca9-172">Azure 閘道 Vm 所使用的子網。</span><span class="sxs-lookup"><span data-stu-id="7aca9-172">The subnet used by the Azure gateway VMs.</span></span>  <br/> |
   
 <span data-ttu-id="7aca9-173">**表格 S：虛擬網路中的子網路**</span><span class="sxs-lookup"><span data-stu-id="7aca9-173">**Table S: Subnets in the virtual network**</span></span>
  
<span data-ttu-id="7aca9-174">下一步，針對指派至虛擬機器和負載平衡器執行個體的靜態 IP 位址填寫表格 I。</span><span class="sxs-lookup"><span data-stu-id="7aca9-174">Next, fill in Table I for the static IP addresses assigned to virtual machines and load balancer instances.</span></span>
  
|<span data-ttu-id="7aca9-175">**項目**</span><span class="sxs-lookup"><span data-stu-id="7aca9-175">**Item**</span></span>|<span data-ttu-id="7aca9-176">**用途**</span><span class="sxs-lookup"><span data-stu-id="7aca9-176">**Purpose**</span></span>|<span data-ttu-id="7aca9-177">**子網路上的 IP 位址**</span><span class="sxs-lookup"><span data-stu-id="7aca9-177">**IP address on the subnet**</span></span>|<span data-ttu-id="7aca9-178">**值**</span><span class="sxs-lookup"><span data-stu-id="7aca9-178">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7aca9-179">1.</span><span class="sxs-lookup"><span data-stu-id="7aca9-179">1.</span></span>  <br/> |<span data-ttu-id="7aca9-180">第一個網域控制站的靜態 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7aca9-180">Static IP address of the first domain controller</span></span>  <br/> |<span data-ttu-id="7aca9-181">定義於表格 S 的項目 1 中，子網路位址空間的第四個可能 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7aca9-181">The fourth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-183">2.</span><span class="sxs-lookup"><span data-stu-id="7aca9-183">2.</span></span>  <br/> |<span data-ttu-id="7aca9-184">第二個網域控制站的靜態 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7aca9-184">Static IP address of the second domain controller</span></span>  <br/> |<span data-ttu-id="7aca9-185">定義於表格 S 的項目 1 中，子網路位址空間的第五個可能 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7aca9-185">The fifth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-187">3.</span><span class="sxs-lookup"><span data-stu-id="7aca9-187">3.</span></span>  <br/> |<span data-ttu-id="7aca9-188">目錄同步處理伺服器的靜態 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7aca9-188">Static IP address of the directory synchronization server</span></span>  <br/> |<span data-ttu-id="7aca9-189">定義于表格 S 的專案1中，子網位址空間的第六個可能 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7aca9-189">The sixth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-191">4.</span><span class="sxs-lookup"><span data-stu-id="7aca9-191">4.</span></span>  <br/> |<span data-ttu-id="7aca9-192">AD FS 伺服器內部負載平衡器的靜態 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7aca9-192">Static IP address of the internal load balancer for the AD FS servers</span></span>  <br/> |<span data-ttu-id="7aca9-193">定義於表格 S 的項目 2 中，子網路位址空間的第四個可能 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7aca9-193">The fourth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-195">5.</span><span class="sxs-lookup"><span data-stu-id="7aca9-195">5.</span></span>  <br/> |<span data-ttu-id="7aca9-196">第一個 AD FS 伺服器的靜態 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7aca9-196">Static IP address of the first AD FS server</span></span>  <br/> |<span data-ttu-id="7aca9-197">定義於表格 S 的項目 2 中，子網路位址空間的第五個可能 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7aca9-197">The fifth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-199">6.</span><span class="sxs-lookup"><span data-stu-id="7aca9-199">6.</span></span>  <br/> |<span data-ttu-id="7aca9-200">第二個 AD FS 伺服器的靜態 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7aca9-200">Static IP address of the second AD FS server</span></span>  <br/> |<span data-ttu-id="7aca9-201">定義於表格 S 的項目 2 中，子網路位址空間的第六個可能 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7aca9-201">The sixth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-203">7.</span><span class="sxs-lookup"><span data-stu-id="7aca9-203">7.</span></span>  <br/> |<span data-ttu-id="7aca9-204">第一個 web 應用程式 proxy 伺服器的靜態 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7aca9-204">Static IP address of the first web application proxy server</span></span>  <br/> |<span data-ttu-id="7aca9-205">定義於表格 S 的項目 3 中，子網路位址空間的第四個可能 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7aca9-205">The fourth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-207">8.</span><span class="sxs-lookup"><span data-stu-id="7aca9-207">8.</span></span>  <br/> |<span data-ttu-id="7aca9-208">第二個 web 應用程式 proxy 伺服器的靜態 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7aca9-208">Static IP address of the second web application proxy server</span></span>  <br/> |<span data-ttu-id="7aca9-209">定義於表格 S 的項目 3 中，子網路位址空間的第五個可能 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7aca9-209">The fifth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="7aca9-211">**表格 I：虛擬網路中的靜態 IP 位址**</span><span class="sxs-lookup"><span data-stu-id="7aca9-211">**Table I: Static IP addresses in the virtual network**</span></span>
  
<span data-ttu-id="7aca9-212">若要在您初次設定虛擬網路的網域控制站時，在內部部署網路中 (DNS) 伺服器的兩個網域名稱系統，請填入 Table D。請與您的 IT 部門合作以決定此清單。</span><span class="sxs-lookup"><span data-stu-id="7aca9-212">For two Domain Name System (DNS) servers in your on-premises network that you want to use when initially setting up the domain controllers in your virtual network, fill in Table D. Work with your IT department to determine this list.</span></span>
  
|<span data-ttu-id="7aca9-213">**項目**</span><span class="sxs-lookup"><span data-stu-id="7aca9-213">**Item**</span></span>|<span data-ttu-id="7aca9-214">**DNS 伺服器的易記名稱**</span><span class="sxs-lookup"><span data-stu-id="7aca9-214">**DNS server friendly name**</span></span>|<span data-ttu-id="7aca9-215">**DNS 伺服器 IP 位址**</span><span class="sxs-lookup"><span data-stu-id="7aca9-215">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7aca9-216">1.</span><span class="sxs-lookup"><span data-stu-id="7aca9-216">1.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-219">2.</span><span class="sxs-lookup"><span data-stu-id="7aca9-219">2.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="7aca9-222">**表格 D：內部部署 DNS 伺服器**</span><span class="sxs-lookup"><span data-stu-id="7aca9-222">**Table D: On-premises DNS servers**</span></span>
  
<span data-ttu-id="7aca9-223">若要將跨單位網路的封包路由傳送至組織網路跨越整個點對點 VPN 連線，您必須設定具有本機網路的虛擬網路，該網路的位址空間清單 (于組織內部部署網路上的所有可訪問位置的 CIDR 標記法) 中。</span><span class="sxs-lookup"><span data-stu-id="7aca9-223">To route packets from the cross-premises network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network that has a list of the address spaces (in CIDR notation) for all of the reachable locations on your organization's on-premises network.</span></span> <span data-ttu-id="7aca9-224">定義區域網路的位址空間清單必須是唯一的，且不可與其他虛擬網路或其他區域網路使用的位址空間重疊。</span><span class="sxs-lookup"><span data-stu-id="7aca9-224">The list of address spaces that define your local network must be unique and must not overlap with the address space used for other virtual networks or other local networks.</span></span>
  
<span data-ttu-id="7aca9-p108">針對區域網路位址空間集，請填寫表格 L。請注意，雖已列出三個空白項，但一般來說您會需要更多。請與您的 IT 部門合作以決定此位址空間清單。</span><span class="sxs-lookup"><span data-stu-id="7aca9-p108">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more. Work with your IT department to determine this list of address spaces.</span></span>
  
|<span data-ttu-id="7aca9-227">**項目**</span><span class="sxs-lookup"><span data-stu-id="7aca9-227">**Item**</span></span>|<span data-ttu-id="7aca9-228">**區域網路位址空間**</span><span class="sxs-lookup"><span data-stu-id="7aca9-228">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7aca9-229">1.</span><span class="sxs-lookup"><span data-stu-id="7aca9-229">1.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-231">2.</span><span class="sxs-lookup"><span data-stu-id="7aca9-231">2.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-233">3.</span><span class="sxs-lookup"><span data-stu-id="7aca9-233">3.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="7aca9-235">**表格 L：區域網路的網址前置詞**</span><span class="sxs-lookup"><span data-stu-id="7aca9-235">**Table L: Address prefixes for the local network**</span></span>
  
<span data-ttu-id="7aca9-236">現在，讓我們開始組建 Azure 基礎結構，以裝載 Microsoft 365 的同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="7aca9-236">Now let's begin building the Azure infrastructure to host your federated authentication for Microsoft 365.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7aca9-237">[!附註] 下列命令集會使用最新版的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7aca9-237">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="7aca9-238">請參閱 [Azure PowerShell 入門](https://docs.microsoft.com/powershell/azure/get-started-azureps)。</span><span class="sxs-lookup"><span data-stu-id="7aca9-238">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="7aca9-239">首先，啟動 Azure PowerShell 提示並登入您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7aca9-239">First, start an Azure PowerShell prompt and login to your account.</span></span>
  
```powershell
Connect-AzAccount
```

> [!TIP]
> <span data-ttu-id="7aca9-240">若要根據您的自訂設定來產生現成 PowerShell 命令區塊，請使用此 [Microsoft Excel 配置活頁簿](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="7aca9-240">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

<span data-ttu-id="7aca9-241">使用下列命令取得訂用帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="7aca9-241">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="7aca9-242">若為舊版的 Azure PowerShell，請改為使用此命令。</span><span class="sxs-lookup"><span data-stu-id="7aca9-242">For older versions of Azure PowerShell, use this command instead.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

<span data-ttu-id="7aca9-243">設定 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="7aca9-243">Set your Azure subscription.</span></span> <span data-ttu-id="7aca9-244">以正確的名稱取代引號內的所有專案（包括 \< and > 字元）。</span><span class="sxs-lookup"><span data-stu-id="7aca9-244">Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="7aca9-245">接下來，建立新的資源群組。</span><span class="sxs-lookup"><span data-stu-id="7aca9-245">Next, create the new resource groups.</span></span> <span data-ttu-id="7aca9-246">若要判斷資源群組名稱是否是唯一一組，可使用此命令來列出現有的資源群組。</span><span class="sxs-lookup"><span data-stu-id="7aca9-246">To determine a unique set of resource group names, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="7aca9-247">針對這唯一的一組資源群組名稱，填寫下列表格。</span><span class="sxs-lookup"><span data-stu-id="7aca9-247">Fill in the following table for the set of unique resource group names.</span></span>
  
|<span data-ttu-id="7aca9-248">**項目**</span><span class="sxs-lookup"><span data-stu-id="7aca9-248">**Item**</span></span>|<span data-ttu-id="7aca9-249">**資源群組名稱**</span><span class="sxs-lookup"><span data-stu-id="7aca9-249">**Resource group name**</span></span>|<span data-ttu-id="7aca9-250">**用途**</span><span class="sxs-lookup"><span data-stu-id="7aca9-250">**Purpose**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7aca9-251">1.</span><span class="sxs-lookup"><span data-stu-id="7aca9-251">1.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="7aca9-253">網域控制站</span><span class="sxs-lookup"><span data-stu-id="7aca9-253">Domain controllers</span></span>  <br/> |
|<span data-ttu-id="7aca9-254">2.</span><span class="sxs-lookup"><span data-stu-id="7aca9-254">2.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="7aca9-256">AD FS 伺服器</span><span class="sxs-lookup"><span data-stu-id="7aca9-256">AD FS servers</span></span>  <br/> |
|<span data-ttu-id="7aca9-257">3.</span><span class="sxs-lookup"><span data-stu-id="7aca9-257">3.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="7aca9-259">Web 應用程式 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="7aca9-259">Web application proxy servers</span></span>  <br/> |
|<span data-ttu-id="7aca9-260">4.</span><span class="sxs-lookup"><span data-stu-id="7aca9-260">4.</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="7aca9-262">基礎結構元素</span><span class="sxs-lookup"><span data-stu-id="7aca9-262">Infrastructure elements</span></span>  <br/> |
   
 <span data-ttu-id="7aca9-263">**表格 R：資源群組**</span><span class="sxs-lookup"><span data-stu-id="7aca9-263">**Table R: Resource groups**</span></span>
  
<span data-ttu-id="7aca9-264">使用這些命令建立新的資源群組。</span><span class="sxs-lookup"><span data-stu-id="7aca9-264">Create your new resource groups with these commands.</span></span>
  
```powershell
$locName="<an Azure location, such as West US>"
$rgName="<Table R - Item 1 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 2 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 3 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 4 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="7aca9-265">接下來，您要建立 Azure 虛擬網路及其子網。</span><span class="sxs-lookup"><span data-stu-id="7aca9-265">Next, you create the Azure virtual network and its subnets.</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
# Get the shortened version of the location
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the subnets
$subnet1Name="<Table S - Item 1 - Subnet name column>"
$subnet1Prefix="<Table S - Item 1 - Subnet address space column>"
$subnet1=New-AzVirtualNetworkSubnetConfig -Name $subnet1Name -AddressPrefix $subnet1Prefix
$subnet2Name="<Table S - Item 2 - Subnet name column>"
$subnet2Prefix="<Table S - Item 2 - Subnet address space column>"
$subnet2=New-AzVirtualNetworkSubnetConfig -Name $subnet2Name -AddressPrefix $subnet2Prefix
$subnet3Name="<Table S - Item 3 - Subnet name column>"
$subnet3Prefix="<Table S - Item 3 - Subnet address space column>"
$subnet3=New-AzVirtualNetworkSubnetConfig -Name $subnet3Name -AddressPrefix $subnet3Prefix
$gwSubnet4Prefix="<Table S - Item 4 - Subnet address space column>"
$gwSubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnet4Prefix

# Create the virtual network
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gwSubnet,$subnet1,$subnet2,$subnet3 -DNSServer $dnsServers

```

<span data-ttu-id="7aca9-266">接下來，為每個具有虛擬機器的子網建立網路安全性群組。</span><span class="sxs-lookup"><span data-stu-id="7aca9-266">Next, you create network security groups for each subnet that has virtual machines.</span></span> <span data-ttu-id="7aca9-267">若要執行子網路隔離，您可以針對允許或拒絕子網路安全小組流量的特定類型新增規則。</span><span class="sxs-lookup"><span data-stu-id="7aca9-267">To perform subnet isolation, you can add rules for the specific types of traffic allowed or denied to the network security group of a subnet.</span></span>
  
```powershell
# Create network security groups
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName

New-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet1Name -AddressPrefix $subnet1Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet2Name -AddressPrefix $subnet2Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet3Name -AddressPrefix $subnet3Prefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="7aca9-268">接著，使用以下命令來建立站台對站台 VPN 連線的閘道。</span><span class="sxs-lookup"><span data-stu-id="7aca9-268">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "GatewaySubnet"

# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -Subnet $subnet

# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig

# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix

# Define the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway

```

> [!NOTE]
> <span data-ttu-id="7aca9-269">個別使用者的聯盟驗證不會仰賴任何內部部署資源。</span><span class="sxs-lookup"><span data-stu-id="7aca9-269">Federated authentication of individual users does not rely on any on-premises resources.</span></span> <span data-ttu-id="7aca9-270">不過，如果這種點對點 VPN 連線無法使用，VNet 中的網域控制站將不會收到內部部署 Active Directory 網域服務中所進行之使用者帳戶和群組的更新。</span><span class="sxs-lookup"><span data-stu-id="7aca9-270">However, if this site-to-site VPN connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services.</span></span> <span data-ttu-id="7aca9-271">為了確保不會發生這種情況，您可以為網站對網站 VPN 連線設定高可用性。</span><span class="sxs-lookup"><span data-stu-id="7aca9-271">To ensure this does not happen, you can configure high availability for your site-to-site VPN connection.</span></span> <span data-ttu-id="7aca9-272">如需詳細資訊，請參閱[高度可用的跨單位和 VNet-VNet 連線](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span><span class="sxs-lookup"><span data-stu-id="7aca9-272">For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="7aca9-273">接著，從顯示的以下命令中，記錄虛擬網路 Azure VPN 閘道的公用 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="7aca9-273">Next, record the public IPv4 address of the Azure VPN gateway for your virtual network from the display of this command:</span></span>
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

<span data-ttu-id="7aca9-p114">接著，設定內部部署 VPN 裝置與 Azure VPN 閘道連線。如需詳細資訊，請參閱[設定您的 VPN 裝置](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices)。</span><span class="sxs-lookup"><span data-stu-id="7aca9-p114">Next, configure your on-premises VPN device to connect to the Azure VPN gateway. For more information, see [Configure your VPN device](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="7aca9-276">若要設定您的內部部署 VPN 裝置，您需要下列項目︰</span><span class="sxs-lookup"><span data-stu-id="7aca9-276">To configure your on-premises VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="7aca9-277">Azure VPN 閘道的公用 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="7aca9-277">The public IPv4 address of the Azure VPN gateway.</span></span>
    
- <span data-ttu-id="7aca9-278">站台對站台 VPN 連線的 IPsec 預先共用金鑰 (表格 V - 項目 5 - 值欄)。</span><span class="sxs-lookup"><span data-stu-id="7aca9-278">The IPsec pre-shared key for the site-to-site VPN connection (Table V - Item 5 - Value column).</span></span>
    
<span data-ttu-id="7aca9-p115">下一步，確認從內部部署網路可觸及虛擬網路的位址空間。一般來說，完成方式是新增路由以將虛擬網路位址空間對應至 VPN 裝置，然後將此路由傳達給其餘組織網路的路由基礎結構。請與您的 IT 部門合作以決定如何執行此動作。</span><span class="sxs-lookup"><span data-stu-id="7aca9-p115">Next, ensure that the address space of the virtual network is reachable from your on-premises network. This is usually done by adding a route corresponding to the virtual network address space to your VPN device and then advertising that route to the rest of the routing infrastructure of your organization network. Work with your IT department to determine how to do this.</span></span>
  
<span data-ttu-id="7aca9-282">接下來，定義三個可用性設定集的名稱。</span><span class="sxs-lookup"><span data-stu-id="7aca9-282">Next, define the names of three availability sets.</span></span> <span data-ttu-id="7aca9-283">填寫表格 A。</span><span class="sxs-lookup"><span data-stu-id="7aca9-283">Fill out Table A.</span></span> 
  
|<span data-ttu-id="7aca9-284">**項目**</span><span class="sxs-lookup"><span data-stu-id="7aca9-284">**Item**</span></span>|<span data-ttu-id="7aca9-285">**用途**</span><span class="sxs-lookup"><span data-stu-id="7aca9-285">**Purpose**</span></span>|<span data-ttu-id="7aca9-286">**可用性設定組名稱**</span><span class="sxs-lookup"><span data-stu-id="7aca9-286">**Availability set name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7aca9-287">1.</span><span class="sxs-lookup"><span data-stu-id="7aca9-287">1.</span></span>  <br/> |<span data-ttu-id="7aca9-288">網域控制站</span><span class="sxs-lookup"><span data-stu-id="7aca9-288">Domain controllers</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-290">2.</span><span class="sxs-lookup"><span data-stu-id="7aca9-290">2.</span></span>  <br/> |<span data-ttu-id="7aca9-291">AD FS 伺服器</span><span class="sxs-lookup"><span data-stu-id="7aca9-291">AD FS servers</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="7aca9-293">3.</span><span class="sxs-lookup"><span data-stu-id="7aca9-293">3.</span></span>  <br/> |<span data-ttu-id="7aca9-294">Web 應用程式 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="7aca9-294">Web application proxy servers</span></span>  <br/> |![線條](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="7aca9-296">**表格 A：可用性設定組**</span><span class="sxs-lookup"><span data-stu-id="7aca9-296">**Table A: Availability sets**</span></span>
  
<span data-ttu-id="7aca9-297">當您在階段 2、3 和 4 中建立虛擬機器時，將會需要這些名稱。</span><span class="sxs-lookup"><span data-stu-id="7aca9-297">You will need these names when you create the virtual machines in phases 2, 3, and 4.</span></span>
  
<span data-ttu-id="7aca9-298">使用這些 Azure PowerShell 命令，建立新的可用性設定集。</span><span class="sxs-lookup"><span data-stu-id="7aca9-298">Create the new availability sets with these Azure PowerShell commands.</span></span>
  
```powershell
$locName="<the Azure location for your new resource group>"
$rgName="<Table R - Item 1 - Resource group name column>"
$avName="<Table A - Item 1 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 2 - Resource group name column>"
$avName="<Table A - Item 2 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 3 - Resource group name column>"
$avName="<Table A - Item 3 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
```

<span data-ttu-id="7aca9-299">以下是成功完成此階段的設定結果。</span><span class="sxs-lookup"><span data-stu-id="7aca9-299">This is the configuration resulting from the successful completion of this phase.</span></span>
  
<span data-ttu-id="7aca9-300">**階段1：適用于 Microsoft 365 的高可用性同盟驗證的 Azure 基礎結構**</span><span class="sxs-lookup"><span data-stu-id="7aca9-300">**Phase 1: The Azure infrastructure for high availability federated authentication for Microsoft 365**</span></span>

![Azure 中使用 Azure 基礎結構之高可用性 Microsoft 365 同盟驗證的階段1](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a><span data-ttu-id="7aca9-302">下一步</span><span class="sxs-lookup"><span data-stu-id="7aca9-302">Next step</span></span>

<span data-ttu-id="7aca9-303">使用 [階段2：設定網域控制站](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) 以繼續設定此工作負載。</span><span class="sxs-lookup"><span data-stu-id="7aca9-303">Use [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) to continue with the configuration of this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7aca9-304">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7aca9-304">See Also</span></span>

[<span data-ttu-id="7aca9-305">Azure 中的 Microsoft 365 高可用性同盟驗證</span><span class="sxs-lookup"><span data-stu-id="7aca9-305">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="7aca9-306">Microsoft 365 開發/測試環境的同盟身分識別</span><span class="sxs-lookup"><span data-stu-id="7aca9-306">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="7aca9-307">Microsoft 365 解決方案與架構中心</span><span class="sxs-lookup"><span data-stu-id="7aca9-307">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

[<span data-ttu-id="7aca9-308">瞭解 Microsoft 365 身分識別和 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7aca9-308">Understanding Microsoft 365 identity and Azure Active Directory</span></span>](about-microsoft-365-identity.md)


