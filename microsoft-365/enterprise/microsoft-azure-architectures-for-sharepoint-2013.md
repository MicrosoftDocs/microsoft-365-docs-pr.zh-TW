---
title: Microsoft Azure SharePoint 2013 架構
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
- seo-marvel-apr2020
ms.assetid: 98fc1006-9399-4ff0-a216-c7c05820d822
description: 瞭解可在 Microsoft Azure 虛擬機器中主控哪些類型的 SharePoint 2013 解決方案，以及如何將 Azure 設定為主機1。
ms.openlocfilehash: 37d7eb2a746e30ad560949a933783beb6b971a08
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695647"
---
# <a name="microsoft-azure-architectures-for-sharepoint-2013"></a><span data-ttu-id="55d75-103">Microsoft Azure SharePoint 2013 架構</span><span class="sxs-lookup"><span data-stu-id="55d75-103">Microsoft Azure Architectures for SharePoint 2013</span></span>

<span data-ttu-id="55d75-104">Azure 是一種主控 SharePoint Server 2013 解決方案的良好環境。</span><span class="sxs-lookup"><span data-stu-id="55d75-104">Azure is a good environment for hosting a SharePoint Server 2013 solution.</span></span> <span data-ttu-id="55d75-105">在大多數情況下，建議使用 Microsoft 365，但是在 Azure 主控的 SharePoint 伺服器陣列可以是特定解決方案的一個不錯選項。</span><span class="sxs-lookup"><span data-stu-id="55d75-105">In most cases, we recommend Microsoft 365, but a SharePoint Server farm hosted in Azure can be a good option for specific solutions.</span></span> <span data-ttu-id="55d75-106">本文說明如何設計 SharePoint 方案，使其符合 Azure 平臺的完美程度。</span><span class="sxs-lookup"><span data-stu-id="55d75-106">This article describes how to architect SharePoint solutions so they are a good fit in the Azure platform.</span></span> <span data-ttu-id="55d75-107">下列兩個特定解決方案用作範例：</span><span class="sxs-lookup"><span data-stu-id="55d75-107">The following two specific solutions are used as examples:</span></span>
  
- [<span data-ttu-id="55d75-108">Microsoft Azure 中的 SharePoint Server 2013 災害復原</span><span class="sxs-lookup"><span data-stu-id="55d75-108">SharePoint Server 2013 Disaster Recovery in Microsoft Azure</span></span>](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)
    
- [<span data-ttu-id="55d75-109">Microsoft Azure 中使用 SharePoint Server 2013 的網際網路網站</span><span class="sxs-lookup"><span data-stu-id="55d75-109">Internet Sites in Microsoft Azure using SharePoint Server 2013</span></span>](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
    
## <a name="recommended-sharepoint-solutions-for-azure-infrastructure-services"></a><span data-ttu-id="55d75-110">Azure 基礎結構服務的建議 SharePoint 解決方案</span><span class="sxs-lookup"><span data-stu-id="55d75-110">Recommended SharePoint solutions for Azure Infrastructure Services</span></span>

<span data-ttu-id="55d75-111">Azure 基礎結構服務是主控 SharePoint 解決方案的極具說服力的選項。</span><span class="sxs-lookup"><span data-stu-id="55d75-111">Azure infrastructure services is a compelling option for hosting SharePoint solutions.</span></span> <span data-ttu-id="55d75-112">有些方案比其他解決方案更適合使用此平臺。</span><span class="sxs-lookup"><span data-stu-id="55d75-112">Some solutions are a better fit for this platform than others.</span></span> <span data-ttu-id="55d75-113">下表顯示建議的解決方案。</span><span class="sxs-lookup"><span data-stu-id="55d75-113">The following table shows recommended solutions.</span></span>
  
|<span data-ttu-id="55d75-114">**解決方案**</span><span class="sxs-lookup"><span data-stu-id="55d75-114">**Solution**</span></span>|<span data-ttu-id="55d75-115">**為何建議使用此解決方案進行 Azure**</span><span class="sxs-lookup"><span data-stu-id="55d75-115">**Why this solution is recommended for Azure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="55d75-116">開發和測試環境</span><span class="sxs-lookup"><span data-stu-id="55d75-116">Development and test environments</span></span>  <br/> |<span data-ttu-id="55d75-117">這很容易建立及管理這些環境。</span><span class="sxs-lookup"><span data-stu-id="55d75-117">It's easy to create and manage these environments.</span></span>  <br/> |
|<span data-ttu-id="55d75-118">內部部署 SharePoint 伺服器陣列至 Azure 的災難修復</span><span class="sxs-lookup"><span data-stu-id="55d75-118">Disaster recovery of on-premises SharePoint farms to Azure</span></span>  <br/> |<span data-ttu-id="55d75-119">**主控次要資料中心** 使用 Azure，而不是在不同地區的次要資料中心中投資。</span><span class="sxs-lookup"><span data-stu-id="55d75-119">**Hosted secondary datacenter** Use Azure instead of investing in a secondary datacenter in a different region.</span></span> <br/> <span data-ttu-id="55d75-120">**低成本的災害復原環境** 維護和支付的資源少於內部部署的嚴重損壞修復環境。</span><span class="sxs-lookup"><span data-stu-id="55d75-120">**Lower-cost disaster-recovery environments** Maintain and pay for fewer resources than an on-premises disaster recovery environment.</span></span> <span data-ttu-id="55d75-121">資源數目取決於您所選擇的嚴重損壞復原環境：冷待命、溫待命或熱待機。</span><span class="sxs-lookup"><span data-stu-id="55d75-121">The number of resources depends on the disaster recovery environment you choose: cold standby, warm standby, or hot standby.</span></span> <br/> <span data-ttu-id="55d75-122">**更多彈性平臺** 萬一發生嚴重損壞，請輕鬆向外延展您的修復 SharePoint 伺服器陣列，以滿足負載需求。</span><span class="sxs-lookup"><span data-stu-id="55d75-122">**More elastic platform** In the event of a disaster, easily scale-out your recovery SharePoint farm to meet load requirements.</span></span> <span data-ttu-id="55d75-123">當您不再需要資源時放大。</span><span class="sxs-lookup"><span data-stu-id="55d75-123">Scale in when you no longer need the resources.</span></span> <br/> <span data-ttu-id="55d75-124">請參閱 [在 Microsoft Azure 中 SharePoint Server 2013 災難修復](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)。</span><span class="sxs-lookup"><span data-stu-id="55d75-124">See [SharePoint Server 2013 Disaster Recovery in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md).</span></span>  <br/> |
|<span data-ttu-id="55d75-125">使用 Microsoft 365 無法使用之功能和縮放功能的網際網路對向網站</span><span class="sxs-lookup"><span data-stu-id="55d75-125">Internet-facing sites that use features and scale not available in Microsoft 365</span></span>  <br/> |<span data-ttu-id="55d75-126">**致力於您的努力** 專注于建立卓越的網站，而不是建立基礎結構。</span><span class="sxs-lookup"><span data-stu-id="55d75-126">**Focus your efforts** Concentrate on building a great site rather than building infrastructure.</span></span> <br/> <span data-ttu-id="55d75-127">**在 Azure 中利用彈性** 新增新的伺服器，並只支付您需要的資源，以調整需求的伺服器陣列大小。</span><span class="sxs-lookup"><span data-stu-id="55d75-127">**Take advantage of elasticity in Azure** Size the farm for the demand by adding new servers, and pay only for resources you need.</span></span> <span data-ttu-id="55d75-128"> (自動縮放) 不支援動態電腦分配。</span><span class="sxs-lookup"><span data-stu-id="55d75-128">Dynamic machine allocation is not supported (auto scale).</span></span> <br/> <span data-ttu-id="55d75-129">\*\*使用 Azure Active Directory (AD) \*\* 請利用 Azure AD 取得客戶帳戶。</span><span class="sxs-lookup"><span data-stu-id="55d75-129">**Use Azure Active Directory (AD)** Take advantage of Azure AD for customer accounts.</span></span> <br/> <span data-ttu-id="55d75-130">**新增 Microsoft 365 中無法使用的 SharePoint 功能** 新增深入報告和 web analytics。</span><span class="sxs-lookup"><span data-stu-id="55d75-130">**Add SharePoint functionality not available in Microsoft 365** Add deep reporting and web analytics.</span></span> <br/> <span data-ttu-id="55d75-131">請參閱 [使用 SharePoint Server 2013 的 Microsoft Azure 中的網際網路網站](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="55d75-131">See [Internet Sites in Microsoft Azure using SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md).</span></span>  <br/> |
|<span data-ttu-id="55d75-132">支援 Microsoft 365 或內部部署環境的應用程式伺服器陣列</span><span class="sxs-lookup"><span data-stu-id="55d75-132">App farms to support Microsoft 365 or on-premises environments</span></span>  <br/> |<span data-ttu-id="55d75-133">在 Azure 中**建立、測試和主控應用程式**，以同時支援內部部署和雲端環境。</span><span class="sxs-lookup"><span data-stu-id="55d75-133">**Build, test, and host apps** in Azure to support both on-premises and cloud environments.</span></span> <br/> <span data-ttu-id="55d75-134">在 Azure 中**主控此角色**，而不是購買內部部署環境的新硬體。</span><span class="sxs-lookup"><span data-stu-id="55d75-134">**Host this role** in Azure instead of buying new hardware for on-premises environments.</span></span> <br/> |
   
<span data-ttu-id="55d75-135">針對內部網路和共同作業解決方案及工作量，請考慮下列選項：</span><span class="sxs-lookup"><span data-stu-id="55d75-135">For intranet and collaboration solutions and workloads, consider the following options:</span></span>
  
- <span data-ttu-id="55d75-136">判斷 Microsoft 365 是否符合您的業務需求，或是否可以成為解決方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="55d75-136">Determine if Microsoft 365 meets your business requirements or can be part of the solution.</span></span> <span data-ttu-id="55d75-137">Microsoft 365 提供一個功能齊全的功能集，永遠都是最新的。</span><span class="sxs-lookup"><span data-stu-id="55d75-137">Microsoft 365 provides a rich feature set that is always up to date.</span></span>
    
- <span data-ttu-id="55d75-138">如果 Microsoft 365 不符合您的所有業務需求，請考慮從 Microsoft 諮詢服務 (MCS) 的標準實施 SharePoint 2013。</span><span class="sxs-lookup"><span data-stu-id="55d75-138">If Microsoft 365 does not meet all your business requirements, consider a standard implementation of SharePoint 2013 on premises from Microsoft Consulting Services (MCS).</span></span> <span data-ttu-id="55d75-139">標準架構可以是比自訂更快速、成本低且更容易的解決方案。</span><span class="sxs-lookup"><span data-stu-id="55d75-139">A standard architecture can be a quicker, cheaper, and easier solution for you to support than a customized one.</span></span> 
    
- <span data-ttu-id="55d75-140">如果標準執行不符合您的業務需求，請考慮使用自訂的內部部署解決方案。</span><span class="sxs-lookup"><span data-stu-id="55d75-140">If a standard implementation doesn't meet your business requirements, consider a customized on-premises solution.</span></span>
    
- <span data-ttu-id="55d75-141">如果使用雲端平臺對您的業務需求很重要，請考慮使用 Azure 基礎結構服務中所主控的 SharePoint 2013 標準或自訂的實施。</span><span class="sxs-lookup"><span data-stu-id="55d75-141">If using a cloud platform is important for your business requirements, consider a standard or customized implementation of SharePoint 2013 hosted in Azure infrastructure services.</span></span> <span data-ttu-id="55d75-142">與其他非原生 Microsoft public 雲端平臺相比，在 Azure 中支援的 SharePoint 解決方案更輕鬆。</span><span class="sxs-lookup"><span data-stu-id="55d75-142">SharePoint solutions are much easier to support in Azure than other non-native Microsoft public cloud platforms.</span></span>
    
## <a name="before-you-design-the-azure-environment"></a><span data-ttu-id="55d75-143">設計 Azure 環境之前</span><span class="sxs-lookup"><span data-stu-id="55d75-143">Before you design the Azure environment</span></span>

<span data-ttu-id="55d75-144">雖然本文使用 SharePoint 拓朴的範例，但您可以將這些設計概念與任何 SharePoint 伺服器陣列拓撲搭配使用。</span><span class="sxs-lookup"><span data-stu-id="55d75-144">While this article uses example SharePoint topologies, you can use these design concepts with any SharePoint farm topology.</span></span> <span data-ttu-id="55d75-145">在您設計 Azure 環境之前，請使用下列拓撲、架構、容量和效能指導來設計 SharePoint 伺服器陣列：</span><span class="sxs-lookup"><span data-stu-id="55d75-145">Before you design the Azure environment, use the following topology, architecture, capacity, and performance guidance to design the SharePoint farm:</span></span>
  
- [<span data-ttu-id="55d75-146">SharePoint 2013 IT 專業人員的架構設計</span><span class="sxs-lookup"><span data-stu-id="55d75-146">Architecture design for SharePoint 2013 IT pros</span></span>](https://technet.microsoft.com/sharepoint/fp123594.aspx)
    
- [<span data-ttu-id="55d75-147">規劃 SharePoint Server 2013 中的效能與容量管理</span><span class="sxs-lookup"><span data-stu-id="55d75-147">Plan for performance and capacity management in SharePoint Server 2013</span></span>](https://technet.microsoft.com/library/8dd52916-f77d-4444-b593-1f7d6f330e5f.aspx)
    
## <a name="determine-the-active-directory-domain-type"></a><span data-ttu-id="55d75-148">決定 Active Directory 網欄位型別</span><span class="sxs-lookup"><span data-stu-id="55d75-148">Determine the Active Directory domain type</span></span>

<span data-ttu-id="55d75-149">每個 SharePoint 伺服器陣列都依賴 Active Directory 來提供伺服器陣列設定的管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="55d75-149">Each SharePoint Server farm relies on Active Directory to provide administrative accounts for farm setup.</span></span> <span data-ttu-id="55d75-150">目前，Azure 的 SharePoint 解決方案有兩個選項。</span><span class="sxs-lookup"><span data-stu-id="55d75-150">At this time, there are two options for SharePoint solutions in Azure.</span></span> <span data-ttu-id="55d75-151">如下表所述。</span><span class="sxs-lookup"><span data-stu-id="55d75-151">These are described in the following table.</span></span>
  
|<span data-ttu-id="55d75-152">**選項**</span><span class="sxs-lookup"><span data-stu-id="55d75-152">**Option**</span></span>|<span data-ttu-id="55d75-153">**描述**</span><span class="sxs-lookup"><span data-stu-id="55d75-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="55d75-154">私人網路域</span><span class="sxs-lookup"><span data-stu-id="55d75-154">Dedicated domain</span></span>  <br/> |<span data-ttu-id="55d75-155">您可以將專用且隔離的 Active Directory 網域部署至 Azure，以支援您的 SharePoint 伺服器陣列。</span><span class="sxs-lookup"><span data-stu-id="55d75-155">You can deploy a dedicated and isolated Active Directory domain to Azure to support your SharePoint farm.</span></span> <span data-ttu-id="55d75-156">這對於上市公司的網際網路網站是很好的選擇。</span><span class="sxs-lookup"><span data-stu-id="55d75-156">This is a good choice for public-facing Internet sites.</span></span>  <br/> |
|<span data-ttu-id="55d75-157">透過跨單位連線擴充內部部署網域</span><span class="sxs-lookup"><span data-stu-id="55d75-157">Extend the on-premises domain through a cross-premises connection</span></span>  <br/> |<span data-ttu-id="55d75-158">當您透過跨單位連線擴充內部部署網域時，使用者會透過您的內部網路存取該 SharePoint 伺服器陣列，就像它是在內部部署中主控。</span><span class="sxs-lookup"><span data-stu-id="55d75-158">When you extend the on-premises domain through a cross-premises connection, users access the SharePoint farm via your intranet as if it were hosted on-premises.</span></span> <span data-ttu-id="55d75-159">您可以充分運用內部部署的 Active Directory 和 DNS 實施。</span><span class="sxs-lookup"><span data-stu-id="55d75-159">You can take advantage of your on-premises Active Directory and DNS implementation.</span></span>  <br/> <span data-ttu-id="55d75-160">在 Azure 中建立會從您的內部部署伺服器陣列容錯移轉至內部的嚴重損壞修復環境時，需要進行跨單位連線。</span><span class="sxs-lookup"><span data-stu-id="55d75-160">A cross-premises connection is required for building a disaster-recovery environment in Azure to fail over to from your on-premises farm.</span></span>  <br/> |
   
<span data-ttu-id="55d75-161">本文包含透過跨單位連線擴充內部部署網域的設計概念。</span><span class="sxs-lookup"><span data-stu-id="55d75-161">This article includes design concepts for extending the on-premises domain through a cross-premises connection.</span></span> <span data-ttu-id="55d75-162">如果您的解決方案使用專用的網域，您就不需要跨部署連線。</span><span class="sxs-lookup"><span data-stu-id="55d75-162">If your solution uses a dedicated domain, you don't need a cross-premises connection.</span></span>
  
## <a name="design-the-virtual-network"></a><span data-ttu-id="55d75-163">設計虛擬網路</span><span class="sxs-lookup"><span data-stu-id="55d75-163">Design the virtual network</span></span>

<span data-ttu-id="55d75-164">首先，您需要 Azure 中的虛擬網路，包含您要用來存放虛擬機器的子網。</span><span class="sxs-lookup"><span data-stu-id="55d75-164">First you need a virtual network in Azure, which includes subnets on which you will place your virtual machines.</span></span> <span data-ttu-id="55d75-165">虛擬網路必須有私人 IP 位址空間，也就是您指派給子網的部分。</span><span class="sxs-lookup"><span data-stu-id="55d75-165">The virtual network needs a private IP address space, portions of which you assign to the subnets.</span></span>
  
<span data-ttu-id="55d75-166">如果您要將內部部署網路擴充至 Azure，並透過執行災難修復) 環境所需的 (跨單位連線，則必須選擇尚未在組織網路中的其他地方使用的私人位址空間，其中可能包含您的內部部署環境和其他 Azure 虛擬網路。</span><span class="sxs-lookup"><span data-stu-id="55d75-166">If you are extending your on-premises network to Azure through a cross-premises connection (required for a disaster recovery environment), you must choose a private address space that is not already in use elsewhere in your organization network, which can include your on-premises environment and other Azure virtual networks.</span></span> 
  
<span data-ttu-id="55d75-167">**圖1：在 Azure 中具有虛擬網路的內部部署環境**</span><span class="sxs-lookup"><span data-stu-id="55d75-167">**Figure 1: On-premises environment with a virtual network in Azure**</span></span>

![為 SharePoint 解決方案設計的 Microsoft Azure 虛擬網路。](../media/OPrrasconWA-AZarch.png)
  
<span data-ttu-id="55d75-171">在此圖表中：</span><span class="sxs-lookup"><span data-stu-id="55d75-171">In this diagram:</span></span>
  
- <span data-ttu-id="55d75-172">Azure 中的虛擬網路是內部部署環境的並列說明。</span><span class="sxs-lookup"><span data-stu-id="55d75-172">A virtual network in Azure is illustrated side-by-side to the on-premises environment.</span></span> <span data-ttu-id="55d75-173">這兩種環境尚未透過跨單位連線相連，其可以是網站對網站 VPN 連線或 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="55d75-173">The two environments are not yet connected by a cross-premises connection, which can be a site-to-site VPN connection or ExpressRoute.</span></span>
    
- <span data-ttu-id="55d75-174">此時，虛擬網路只會包含子網，而不會包含其他架構元素。</span><span class="sxs-lookup"><span data-stu-id="55d75-174">At this point, the virtual network just includes the subnets and no other architectural elements.</span></span> <span data-ttu-id="55d75-175">一個子網會主控 Azure 閘道，其他子網會主控 SharePoint 伺服器陣列的層級，另外一個用於 Active Directory 和 DNS。</span><span class="sxs-lookup"><span data-stu-id="55d75-175">One subnet will host the Azure gateway and other subnets host the tiers of the SharePoint farm, with an additional one for Active Directory and DNS.</span></span>
    
## <a name="add-cross-premises-connectivity"></a><span data-ttu-id="55d75-176">新增跨部署連線能力</span><span class="sxs-lookup"><span data-stu-id="55d75-176">Add cross-premises connectivity</span></span>

<span data-ttu-id="55d75-177">下一個部署步驟是建立跨單位的連線 (如果此連接適用于您的解決方案) 。</span><span class="sxs-lookup"><span data-stu-id="55d75-177">The next deployment step is to create the cross-premises connection (if this applies to your solution).</span></span> <span data-ttu-id="55d75-178">若為跨單位連線，Azure 閘道位於個別的閘道子網，您必須建立並指派位址空間。</span><span class="sxs-lookup"><span data-stu-id="55d75-178">For cross-premises connections, a Azure gateway resides in a separate gateway subnet, which you must create and assign an address space.</span></span> 
  
<span data-ttu-id="55d75-179">當您規劃跨單位連線時，您可以定義及建立 Azure 閘道和內部部署閘道裝置的連線。</span><span class="sxs-lookup"><span data-stu-id="55d75-179">When you plan for a cross-premises connection, you define and create an Azure gateway and connection to an on-premises gateway device.</span></span>
  
<span data-ttu-id="55d75-180">**圖2：使用 Azure 閘道和內部部署閘道裝置，在內部部署環境和 Azure 之間提供網站對網站的連線能力**</span><span class="sxs-lookup"><span data-stu-id="55d75-180">**Figure 2: Using an Azure gateway and an on-premises gateway device to provide site-to-site connectivity between the on-premises environment and Azure**</span></span>

![內部部署環境已透過跨單位連線連接至 Azure 虛擬網路，其可以是網站對網站 VPN 連線或是 ExpressRoute](../media/AZarch-VPNgtwyconnct.png)
  
<span data-ttu-id="55d75-182">在此圖表中：</span><span class="sxs-lookup"><span data-stu-id="55d75-182">In this diagram:</span></span>
  
- <span data-ttu-id="55d75-183">新增至上圖：內部部署環境會透過跨單位連線（可以是網站對網站 VPN 連線或 ExpressRoute）連線至 Azure 虛擬網路。</span><span class="sxs-lookup"><span data-stu-id="55d75-183">Adding to the previous diagram, the on-premises environment is connected to the Azure virtual network by a cross-premise connection, which can be a site-to-site VPN connection or ExpressRoute.</span></span>
    
- <span data-ttu-id="55d75-184">Azure 閘道位於閘道子網上。</span><span class="sxs-lookup"><span data-stu-id="55d75-184">An Azure gateway is on a gateway subnet.</span></span>
    
- <span data-ttu-id="55d75-185">內部部署環境包括閘道裝置（例如路由器或 VPN 伺服器）。</span><span class="sxs-lookup"><span data-stu-id="55d75-185">The on-premises environment includes a gateway device, such as a router or VPN server.</span></span>
    
<span data-ttu-id="55d75-186">如需規劃及建立跨單位虛擬網路的其他資訊，請參閱 [將內部部署網路連線至 Microsoft Azure 虛擬網路](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)。</span><span class="sxs-lookup"><span data-stu-id="55d75-186">For additional information to plan for and create a cross-premises virtual network, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
  
## <a name="add-active-directory-domain-services-ad-ds-and-dns"></a><span data-ttu-id="55d75-187">將 Active Directory 網域服務新增 (AD DS) 和 DNS</span><span class="sxs-lookup"><span data-stu-id="55d75-187">Add Active Directory Domain Services (AD DS) and DNS</span></span>

<span data-ttu-id="55d75-188">針對 Azure 中的嚴重損壞修復，您可以在混合案例中部署 Windows Server AD 和 DNS，其中 Windows Server AD 同時部署在內部部署和 Azure 虛擬機器上。</span><span class="sxs-lookup"><span data-stu-id="55d75-188">For disaster recovery in Azure, you deploy Windows Server AD and DNS in a hybrid scenario where Windows Server AD is deployed both on-premises and on Azure virtual machines.</span></span>
  
<span data-ttu-id="55d75-189">**圖3：混合式 Active Directory 網域設定**</span><span class="sxs-lookup"><span data-stu-id="55d75-189">**Figure 3: Hybrid Active Directory domain configuration**</span></span>

![STwo 虛擬機器部署到 Azure 虛擬網路和 SharePoint 伺服器陣列子網路是複本網域控制站和 DNS 伺服器](../media/AZarch-HyADdomainConfig.png)
  
<span data-ttu-id="55d75-191">這個圖表是透過將兩部虛擬機器加入 Windows Server AD 和 DNS 子網，在先前的圖表上建立。</span><span class="sxs-lookup"><span data-stu-id="55d75-191">This diagram builds on the previous diagrams by adding two virtual machines to a Windows Server AD and DNS subnet.</span></span> <span data-ttu-id="55d75-192">這些虛擬機器為複本網域控制站和 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="55d75-192">These virtual machines are replica domain controllers and DNS servers.</span></span> <span data-ttu-id="55d75-193">它們是內部部署 Windows Server AD 環境的分機。</span><span class="sxs-lookup"><span data-stu-id="55d75-193">They are an extension of the on-premises Windows Server AD environment.</span></span> 
  
<span data-ttu-id="55d75-194">下表提供 Azure 中這些虛擬機器的設定建議。</span><span class="sxs-lookup"><span data-stu-id="55d75-194">The following table provides configuration recommendations for these virtual machines in Azure.</span></span> <span data-ttu-id="55d75-195">使用這些功能做為設計您自己的環境的起點，即使針對 Azure 環境不會與您的內部部署環境進行通訊的私人網路域也是一樣。</span><span class="sxs-lookup"><span data-stu-id="55d75-195">Use these as a starting point for designing your own environment—even for a dedicated domain where your Azure environment doesn't communicate with your on-premises environment.</span></span>
  
|<span data-ttu-id="55d75-196">**項目**</span><span class="sxs-lookup"><span data-stu-id="55d75-196">**Item**</span></span>|<span data-ttu-id="55d75-197">**設定**</span><span class="sxs-lookup"><span data-stu-id="55d75-197">**Configuration**</span></span>|
|:-----|:-----|
|<span data-ttu-id="55d75-198">Azure 中的虛擬機器大小</span><span class="sxs-lookup"><span data-stu-id="55d75-198">Virtual machine size in Azure</span></span>  <br/> |<span data-ttu-id="55d75-199">標準層級的 A1 或 A2 大小</span><span class="sxs-lookup"><span data-stu-id="55d75-199">A1 or A2 size in the Standard tier</span></span>  <br/> |
|<span data-ttu-id="55d75-200">作業系統</span><span class="sxs-lookup"><span data-stu-id="55d75-200">Operating system</span></span>  <br/> |<span data-ttu-id="55d75-201">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="55d75-201">Windows Server 2012 R2</span></span>  <br/> |
|<span data-ttu-id="55d75-202">Active Directory 角色</span><span class="sxs-lookup"><span data-stu-id="55d75-202">Active Directory role</span></span>  <br/> |<span data-ttu-id="55d75-203">指定為通用類別目錄伺服器的 AD DS 網域控制站。</span><span class="sxs-lookup"><span data-stu-id="55d75-203">AD DS domain controller designated as a global catalog server.</span></span> <span data-ttu-id="55d75-204">這種設定可減少跨跨單位連線的傳出流量。</span><span class="sxs-lookup"><span data-stu-id="55d75-204">This configuration reduces egress traffic across the cross-premises connection.</span></span>  <br/> <span data-ttu-id="55d75-205">在具有高變更率的多網域環境中 (此) 不常見，請將內部部署的網域控制站設定為不要與 Azure 中的通用類別目錄伺服器進行同步處理，以減少複寫流量。</span><span class="sxs-lookup"><span data-stu-id="55d75-205">In a multidomain environment with high rates of change (this is not common), configure domain controllers on premises not to sync with the global catalog servers in Azure, to reduce replication traffic.</span></span>  <br/> |
|<span data-ttu-id="55d75-206">DNS 角色</span><span class="sxs-lookup"><span data-stu-id="55d75-206">DNS role</span></span>  <br/> |<span data-ttu-id="55d75-207">在網域控制站上安裝及設定 DNS 伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="55d75-207">Install and configure the DNS Server service on the domain controllers.</span></span>  <br/> |
|<span data-ttu-id="55d75-208">資料磁片</span><span class="sxs-lookup"><span data-stu-id="55d75-208">Data disks</span></span>  <br/> |<span data-ttu-id="55d75-209">將 Active Directory 資料庫、記錄檔和 SYSVOL 放在其他 Azure 資料磁片上。</span><span class="sxs-lookup"><span data-stu-id="55d75-209">Place the Active Directory database, logs, and SYSVOL on additional Azure data disks.</span></span> <span data-ttu-id="55d75-210">請勿將它們置於 Azure 所提供的作業系統磁片或臨時磁片上。</span><span class="sxs-lookup"><span data-stu-id="55d75-210">Do not place these on the operating system disk or the temporary disks provided by Azure.</span></span>  <br/> |
|<span data-ttu-id="55d75-211">IP 位址</span><span class="sxs-lookup"><span data-stu-id="55d75-211">IP addresses</span></span>  <br/> |<span data-ttu-id="55d75-212">在設定網域控制站之後，使用靜態 IP 位址和設定虛擬網路以將這些位址指派給虛擬網路中的虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="55d75-212">Use static IP addresses and configure the virtual network to assign these addresses to the virtual machines in the virtual network after the domain controllers have been configured.</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="55d75-213">在 Azure 中部署 Active Directory 之前，請閱讀在 [Azure 虛擬機器上部署 Windows Server Active Directory 的指導方針](https://go.microsoft.com/fwlink/p/?linkid=392681)。</span><span class="sxs-lookup"><span data-stu-id="55d75-213">Before you deploy Active Directory in Azure, read [Guidelines for Deploying Windows Server Active Directory on Azure Virtual Machines](https://go.microsoft.com/fwlink/p/?linkid=392681).</span></span> <span data-ttu-id="55d75-214">這些會協助您判斷方案是否需要不同的架構或不同的設定。</span><span class="sxs-lookup"><span data-stu-id="55d75-214">These help you determine if a different architecture or different configuration settings are needed for your solution.</span></span> 
  
## <a name="add-the-sharepoint-farm"></a><span data-ttu-id="55d75-215">新增 SharePoint 伺服器陣列</span><span class="sxs-lookup"><span data-stu-id="55d75-215">Add the SharePoint farm</span></span>

<span data-ttu-id="55d75-216">將 SharePoint 伺服器陣列的虛擬機器放在適當子網上的層級。</span><span class="sxs-lookup"><span data-stu-id="55d75-216">Place the virtual machines of the SharePoint farm in tiers on the appropriate subnets.</span></span>
  
<span data-ttu-id="55d75-217">**圖4： SharePoint 虛擬機器的位置**</span><span class="sxs-lookup"><span data-stu-id="55d75-217">**Figure 4: Placement of SharePoint virtual machines**</span></span>

![資料庫伺服器和 SharePoint 伺服器角色加入 SharePoint 伺服器陣列子網路內的 Azure 虛擬網路](../media/AZarch-SPVMsinCloudSer.png)
  
<span data-ttu-id="55d75-219">這個圖表是透過在各自的層級新增 SharePoint 伺服器陣列伺服器角色，在先前的圖表上建立。</span><span class="sxs-lookup"><span data-stu-id="55d75-219">This diagram builds on the previous diagrams by adding the SharePoint farm server roles in their respective tiers.</span></span>
  
- <span data-ttu-id="55d75-220">兩部執行 SQL Server 的資料庫虛擬機器建立資料庫層。</span><span class="sxs-lookup"><span data-stu-id="55d75-220">Two database virtual machines running SQL Server create the database tier.</span></span>
    
- <span data-ttu-id="55d75-221">針對下列各層執行 SharePoint Server 2013 的兩部虛擬機器：前端伺服器、分散式快取伺服器及後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="55d75-221">Two virtual machines running SharePoint Server 2013 for each of the following tiers: front end servers, distributed cache servers, and back end servers.</span></span>
    
## <a name="design-and-fine-tune-server-roles-for-availability-sets-and-fault-domains"></a><span data-ttu-id="55d75-222">設計及微調可用性集和容錯網域的伺服器角色</span><span class="sxs-lookup"><span data-stu-id="55d75-222">Design and fine tune server roles for availability sets and fault domains</span></span>

<span data-ttu-id="55d75-223">容錯網域是執行角色實例之硬體的群組。</span><span class="sxs-lookup"><span data-stu-id="55d75-223">A fault domain is a grouping of hardware in which role instances run.</span></span> <span data-ttu-id="55d75-224">相同容錯網域內的虛擬機器可以同時由 Azure 基礎結構更新。</span><span class="sxs-lookup"><span data-stu-id="55d75-224">Virtual machines within the same fault domain can be updated by the Azure infrastructure at the same time.</span></span> <span data-ttu-id="55d75-225">或者，因為它們共用相同的機架，所以它們可能會同時失敗。</span><span class="sxs-lookup"><span data-stu-id="55d75-225">Or, they can fail at the same time because they share the same rack.</span></span> <span data-ttu-id="55d75-226">為了避免在相同容錯網域上有兩個虛擬機器的風險，您可以將虛擬機器設定為可用性設定，以確保每個虛擬機器都位於不同的容錯網域中。</span><span class="sxs-lookup"><span data-stu-id="55d75-226">To avoid the risk of having two virtual machines on the same fault domain, you can configure your virtual machines as an availability set, which ensures that each virtual machine is in a different fault domain.</span></span> <span data-ttu-id="55d75-227">如果有三個虛擬機器設定為可用性集，Azure 就會保證兩個以上的虛擬機器都位於相同的容錯網域中。</span><span class="sxs-lookup"><span data-stu-id="55d75-227">If three virtual machines are configured as an availability set, Azure guarantees that no more than two of the virtual machines are located in the same fault domain.</span></span>
  
<span data-ttu-id="55d75-228">當您為 SharePoint 伺服器陣列設計 Azure 架構時，請將相同的伺服器角色設定為可用性設定的一部分。</span><span class="sxs-lookup"><span data-stu-id="55d75-228">When you design the Azure architecture for a SharePoint farm, configure identical server roles to be part of an availability set.</span></span> <span data-ttu-id="55d75-229">這可確保您的虛擬機器分散在多個容錯網域。</span><span class="sxs-lookup"><span data-stu-id="55d75-229">This ensures that your virtual machines are spread across multiple fault domains.</span></span>
  
<span data-ttu-id="55d75-230">**圖5：使用 Azure 可用性設定可為 SharePoint 伺服器陣列層級提供高可用性**</span><span class="sxs-lookup"><span data-stu-id="55d75-230">**Figure 5: Use Azure Availability Sets to provide high availability for the SharePoint farm tiers**</span></span>

![Azure 基礎結構中針對 SharePoint 2013 解決方案的可用性設定組設定](../media/AZenv-WinAzureAvailSetsHA.png)
  
<span data-ttu-id="55d75-232">此圖表會呼叫 Azure 基礎結構內可用性集的設定。</span><span class="sxs-lookup"><span data-stu-id="55d75-232">This diagram calls out the configuration of availability sets within the Azure infrastructure.</span></span> <span data-ttu-id="55d75-233">下列每個角色共用個別的可用性集：</span><span class="sxs-lookup"><span data-stu-id="55d75-233">Each of the following roles share a separate availability set:</span></span>
  
- <span data-ttu-id="55d75-234">Active Directory 和 DNS</span><span class="sxs-lookup"><span data-stu-id="55d75-234">Active Directory and DNS</span></span>
    
- <span data-ttu-id="55d75-235">Database</span><span class="sxs-lookup"><span data-stu-id="55d75-235">Database</span></span>
    
- <span data-ttu-id="55d75-236">後端</span><span class="sxs-lookup"><span data-stu-id="55d75-236">Back end</span></span>
    
- <span data-ttu-id="55d75-237">散佈快取</span><span class="sxs-lookup"><span data-stu-id="55d75-237">Distribute cache</span></span>
    
- <span data-ttu-id="55d75-238">前端</span><span class="sxs-lookup"><span data-stu-id="55d75-238">Front end</span></span>
    
<span data-ttu-id="55d75-239">在 Azure 平臺中，可能需要精細調整 SharePoint 伺服器陣列。</span><span class="sxs-lookup"><span data-stu-id="55d75-239">The SharePoint farm might need to be fine tuned in the Azure platform.</span></span> <span data-ttu-id="55d75-240">為了確保所有元件的高可用性，請確定伺服器角色的設定都相同。</span><span class="sxs-lookup"><span data-stu-id="55d75-240">To ensure high availability of all components, ensure that the server roles are all configured identically.</span></span>
  
<span data-ttu-id="55d75-241">以下是一個範例，顯示符合特定容量和效能目標的標準網際網路網站架構。</span><span class="sxs-lookup"><span data-stu-id="55d75-241">Here is an example that shows a standard Internet Sites architecture that meets specific capacity and performance goals.</span></span> <span data-ttu-id="55d75-242">這個範例會依下列架構模型所述： [SharePoint Server 2013 的網際網路網站搜尋架構](https://go.microsoft.com/fwlink/p/?LinkId=261519)。</span><span class="sxs-lookup"><span data-stu-id="55d75-242">This example is featured in the following architecture model: [Internet Sites Search Architectures for SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=261519).</span></span>
  
<span data-ttu-id="55d75-243">**圖6：三層式伺服器陣列中的容量和效能目標規劃範例**</span><span class="sxs-lookup"><span data-stu-id="55d75-243">**Figure 6: Planning example for capacity and performance goals in a three-tier farm**</span></span>

![標準 SharePoint 2013 Internet Sites 架構具有符合特定容量和效能目標的元件配置](../media/AZarch-CapPerfexmpArch.png)
  
<span data-ttu-id="55d75-245">在此圖表中：</span><span class="sxs-lookup"><span data-stu-id="55d75-245">In this diagram:</span></span>
  
- <span data-ttu-id="55d75-246">代表三層式伺服器陣列：網頁伺服器、應用程式伺服器及資料庫伺服器。</span><span class="sxs-lookup"><span data-stu-id="55d75-246">A three-tier farm is represented: web servers, application servers, and database servers.</span></span>
    
- <span data-ttu-id="55d75-247">三台網頁伺服器的設定與多個元件相同。</span><span class="sxs-lookup"><span data-stu-id="55d75-247">The three web servers are configured identically with multiple components.</span></span>
    
- <span data-ttu-id="55d75-248">這兩個資料庫伺服器設定相同。</span><span class="sxs-lookup"><span data-stu-id="55d75-248">The two database servers are configured identically.</span></span>
    
- <span data-ttu-id="55d75-249">這三個應用程式伺服器的設定不相同。</span><span class="sxs-lookup"><span data-stu-id="55d75-249">The three application servers are not configured identically.</span></span> <span data-ttu-id="55d75-250">這些伺服器角色需要針對 Azure 中的可用性集進行微調微調。</span><span class="sxs-lookup"><span data-stu-id="55d75-250">These server roles require fine tuning for availability sets in Azure.</span></span>
    
<span data-ttu-id="55d75-251">讓我們更深入瞭解應用程式伺服器層。</span><span class="sxs-lookup"><span data-stu-id="55d75-251">Let's look closer at the application server tier.</span></span>
  
<span data-ttu-id="55d75-252">**圖7：精細調整之前的應用程式伺服器層**</span><span class="sxs-lookup"><span data-stu-id="55d75-252">**Figure 7: Application server tier before fine tuning**</span></span>

![調整為 Microsoft Azure 可用性設定組之前的 SharePoint Server 2013 應用程式伺服器層範例](../media/AZarch-AppServtierBefore.png)
  
<span data-ttu-id="55d75-254">在此圖表中：</span><span class="sxs-lookup"><span data-stu-id="55d75-254">In this diagram:</span></span>
  
- <span data-ttu-id="55d75-255">應用層中包含三部伺服器。</span><span class="sxs-lookup"><span data-stu-id="55d75-255">Three servers are included in the application tier.</span></span>
    
- <span data-ttu-id="55d75-256">第一部伺服器包含四個元件。</span><span class="sxs-lookup"><span data-stu-id="55d75-256">The first server includes four components.</span></span>
    
- <span data-ttu-id="55d75-257">第二部伺服器包含三個元件。</span><span class="sxs-lookup"><span data-stu-id="55d75-257">The second server includes three components.</span></span>
    
- <span data-ttu-id="55d75-258">第三部伺服器包含兩個元件。</span><span class="sxs-lookup"><span data-stu-id="55d75-258">The third server includes two components.</span></span>
    
<span data-ttu-id="55d75-259">您可以根據伺服器陣列的效能與容量目標，判斷元件數目。</span><span class="sxs-lookup"><span data-stu-id="55d75-259">You determine the number of components by the performance and capacity targets for the farm.</span></span> <span data-ttu-id="55d75-260">若要調整此 Azure 的架構，我們會在所有三個伺服器上複寫四個元件。</span><span class="sxs-lookup"><span data-stu-id="55d75-260">To adapt this architecture for Azure, we'll replicate the four components across all three servers.</span></span> <span data-ttu-id="55d75-261">這會增加超出效能與容量所需的元件數目。</span><span class="sxs-lookup"><span data-stu-id="55d75-261">This increases the number of components beyond what is necessary for performance and capacity.</span></span> <span data-ttu-id="55d75-262">其缺點是，此設計可確保將三個虛擬機器指派給可用性集時，Azure 平臺中所有四個元件的高可用性。</span><span class="sxs-lookup"><span data-stu-id="55d75-262">The tradeoff is that this design ensures high availability of all four components in the Azure platform when these three virtual machines are assigned to an availability set.</span></span>
  
<span data-ttu-id="55d75-263">**圖8：微調微調後的應用程式伺服器層**</span><span class="sxs-lookup"><span data-stu-id="55d75-263">**Figure 8: Application server tier after fine tuning**</span></span>

![調整為 Microsoft Azure 可用性設定組之後的 SharePoint Server 2013 應用程式伺服器層範例](../media/AZarch-AppServtierAfter.png)
  
<span data-ttu-id="55d75-265">此圖顯示所有三個應用程式伺服器設定相同的四個元件。</span><span class="sxs-lookup"><span data-stu-id="55d75-265">This diagram shows all three application servers configured identically with the same four components.</span></span>
  
<span data-ttu-id="55d75-266">當我們將可用性設定集新增至 SharePoint 伺服器陣列的層級時，會完成執行。</span><span class="sxs-lookup"><span data-stu-id="55d75-266">When we add availability sets to the tiers of the SharePoint farm, the implementation is complete.</span></span>
  
<span data-ttu-id="55d75-267">**圖9： Azure 基礎結構服務中已完成的 SharePoint 伺服器陣列**</span><span class="sxs-lookup"><span data-stu-id="55d75-267">**Figure 9: The completed SharePoint farm in Azure infrastructure services**</span></span>

![Azure Infrastructure Services 中的 SharePoint 2013 伺服器陣列以及虛擬網路、跨單位連線能力、子網路、VM 以及可用性設定組的範例 ](../media/7256292f-bf11-485b-8917-41ba206153ee.png)
  
<span data-ttu-id="55d75-269">此圖顯示在 Azure 基礎結構服務中所執行的 SharePoint 伺服器陣列，其可用性設定可提供每一層中的伺服器的容錯網域。</span><span class="sxs-lookup"><span data-stu-id="55d75-269">This diagram shows the SharePoint farm implemented in Azure infrastructure services, with availability sets to provide fault domains for the servers in each tier.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="55d75-270">另請參閱</span><span class="sxs-lookup"><span data-stu-id="55d75-270">See Also</span></span>

[<span data-ttu-id="55d75-271">Microsoft 365 解決方案與架構中心</span><span class="sxs-lookup"><span data-stu-id="55d75-271">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)
  
[<span data-ttu-id="55d75-272">Microsoft Azure 中使用 SharePoint Server 2013 的網際網路網站</span><span class="sxs-lookup"><span data-stu-id="55d75-272">Internet Sites in Microsoft Azure using SharePoint Server 2013</span></span>](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
  
[<span data-ttu-id="55d75-273">Microsoft Azure 中的 SharePoint Server 2013 災害復原</span><span class="sxs-lookup"><span data-stu-id="55d75-273">SharePoint Server 2013 Disaster Recovery in Microsoft Azure</span></span>](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)


