---
title: SharePoint Server 2007 終止支援藍圖
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/28/2019
audience: ITPro
ms.topic: conceptual
f1.keywords:
- CSH
ms.custom:
- vsemail
- MS_WSS_DirectoryManagement
- MS_WSS_ConfigEmail
- globalemailconfig
- configssc
- AppDefToBDC
- seo-marvel-apr2020
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- OFU120
- SPS150
- OSU140
- WSU120
- OSR120
- SPO160
- PJW120
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: ba124775-d5c0-4d68-b88d-8458ad4c3717
description: 在2017年10月10日，SharePoint Server 2007 已結束支援。 在本文中，瞭解升級、遷移和支援選項。
ms.openlocfilehash: c89f150618150e352de476e0a0982fd2d98348e2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688810"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a><span data-ttu-id="73897-104">SharePoint Server 2007 終止支援藍圖</span><span class="sxs-lookup"><span data-stu-id="73897-104">SharePoint Server 2007 end of support roadmap</span></span>

<span data-ttu-id="73897-105">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="73897-105">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="73897-106">在 **2017 年10月 10**日，Microsoft Office SharePoint Server 2007 已到達支援終止。</span><span class="sxs-lookup"><span data-stu-id="73897-106">On **October 10, 2017**, Microsoft Office SharePoint Server 2007 reached end of support.</span></span> <span data-ttu-id="73897-107">若尚未開始從 SharePoint Server 2007 遷移至 Microsoft 365 或更新版本的 SharePoint 伺服器內部部署，現在是開始規劃的時間。</span><span class="sxs-lookup"><span data-stu-id="73897-107">If you haven't begun your migration from SharePoint Server 2007 to Microsoft 365 or a newer version of SharePoint Server on-premises, now's the time to start planning.</span></span> <span data-ttu-id="73897-108">本文將詳細說明如何將資料移轉至 SharePoint 線上，或升級 SharePoint 伺服器內部部署的資源。</span><span class="sxs-lookup"><span data-stu-id="73897-108">This article details resources to help people migrate data to SharePoint Online, or upgrade your SharePoint Server on-premises.</span></span> 
  
## <a name="what-does-end-of-support-mean"></a><span data-ttu-id="73897-109">終止支援是什麼意思？</span><span class="sxs-lookup"><span data-stu-id="73897-109">What does end of support mean?</span></span>

<span data-ttu-id="73897-110">SharePoint Server （幾乎所有的 Microsoft 產品）都具有支援週期，Microsoft 提供了新功能、bug 修正、安全性修正等等。</span><span class="sxs-lookup"><span data-stu-id="73897-110">SharePoint Server, like almost all Microsoft products, has a support lifecycle during which Microsoft provides new features, bug fixes, security fixes, and so on.</span></span> <span data-ttu-id="73897-111">產品的生命週期從首次發行日期算起，通常會持續 10 年，而這個生命週期的結束就稱為產品支援結束。</span><span class="sxs-lookup"><span data-stu-id="73897-111">This lifecycle typically lasts for 10 years from the date of the product's initial release, and the end of this lifecycle is known as the product's end of support.</span></span> <span data-ttu-id="73897-112">在支援終止時，Microsoft 不再提供：</span><span class="sxs-lookup"><span data-stu-id="73897-112">At end of support, Microsoft no longer provides:</span></span>
  
- <span data-ttu-id="73897-113">可能發生之任何問題的技術支援；</span><span class="sxs-lookup"><span data-stu-id="73897-113">Technical support for problems that may occur;</span></span>
    
- <span data-ttu-id="73897-114">所發現且可能會影響伺服器穩定性及可用性之問題的錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="73897-114">Bug fixes for issues that are discovered and that may impact the stability and usability of the server;</span></span>
    
- <span data-ttu-id="73897-115">已發現並可能導致伺服器遭受安全性破壞之弱點的安全性修正程式。和</span><span class="sxs-lookup"><span data-stu-id="73897-115">Security fixes for vulnerabilities that are discovered and that may make the server vulnerable to security breaches; and</span></span> 
    
- <span data-ttu-id="73897-116">時區更新。</span><span class="sxs-lookup"><span data-stu-id="73897-116">Time zone updates.</span></span>
    
<span data-ttu-id="73897-117">雖然您的 SharePoint Server 2007 伺服器陣列在10月 10 2017 日之後仍會運作，但不會為產品 (（包括安全性修補程式/) 修復程式）提供進一步的更新、修補程式或修復程式，而 Microsoft 支援人員會將其支援工作完全移至較新版本的產品。</span><span class="sxs-lookup"><span data-stu-id="73897-117">Though your SharePoint Server 2007 farm will still be operational after October 10, 2017, no further updates, patches, or fixes will be shipped for the product (including security patches/fixes), and Microsoft Support will have fully shifted its support efforts to more recent versions of the product.</span></span> <span data-ttu-id="73897-118">因為您的安裝將不再受支援或修補，所以由於支援方法的終止，您應該升級產品或遷移重要資料。</span><span class="sxs-lookup"><span data-stu-id="73897-118">Because your installation will no longer supported or patched, as end of support approaches you should upgrade the product, or migrate important data.</span></span>
  
> [!TIP]
> <span data-ttu-id="73897-119">若尚未計畫升級或遷移，請參閱： [SharePoint 2007 遷移選項](sharepoint-2007-migration-options.md)，如需一些開始位置的範例。</span><span class="sxs-lookup"><span data-stu-id="73897-119">If you haven't already planned for upgrade or migration, please see: [SharePoint 2007 migration options to consider](sharepoint-2007-migration-options.md), for some examples of where to begin.</span></span> <span data-ttu-id="73897-120">您也可以搜尋可協助升級或 Microsoft 365 遷移 (或兩者) 的 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=841249) 。</span><span class="sxs-lookup"><span data-stu-id="73897-120">You can also search for [Microsoft Partners](https://go.microsoft.com/fwlink/?linkid=841249) who can help with upgrade or Microsoft 365 migration (or both).</span></span> 
  
<span data-ttu-id="73897-121">如需 Office 2007 伺服器達到支援終止的詳細資訊，請參閱 [協助您從 Office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)。</span><span class="sxs-lookup"><span data-stu-id="73897-121">For more information about Office 2007 servers reaching the end of support, see [Resources to help you upgrade from Office 2007 servers and clients](upgrade-from-office-2007-servers-and-products.md).</span></span>
  
## <a name="what-are-my-options"></a><span data-ttu-id="73897-122">我有哪些選擇？</span><span class="sxs-lookup"><span data-stu-id="73897-122">What are my options?</span></span>

<span data-ttu-id="73897-123">您的第一個終止應該是 [產品生命週期網站](https://go.microsoft.com/fwlink/?linkid=843148)。</span><span class="sxs-lookup"><span data-stu-id="73897-123">Your first stop should be the [Product Lifecycle site](https://go.microsoft.com/fwlink/?linkid=843148).</span></span> <span data-ttu-id="73897-124">如果您有內部部署的 Microsoft 產品為老化，您應該檢查其支援日期是否結束，如果您的遷移一般需要，則為一年或一個年或後的時間，您可以排程升級或遷移。</span><span class="sxs-lookup"><span data-stu-id="73897-124">If you have an on-premises Microsoft product that is aging, you should check for its end of support date so that, a year or so out - or as long as your migrations generally require - you can schedule upgrade or migrations.</span></span> <span data-ttu-id="73897-125">當您選擇下一個步驟時，它可能會在產品功能方面有助您瞭解，其品質會變得更好、更好及最適合的考慮。</span><span class="sxs-lookup"><span data-stu-id="73897-125">When choosing the next step, it might help to think in terms of what would be good enough, better, and best when it comes to product features.</span></span> <span data-ttu-id="73897-126">以下為範例：</span><span class="sxs-lookup"><span data-stu-id="73897-126">Here's an example:</span></span>
  
|<span data-ttu-id="73897-127">**良好**</span><span class="sxs-lookup"><span data-stu-id="73897-127">**Good**</span></span>|<span data-ttu-id="73897-128">**更好**</span><span class="sxs-lookup"><span data-stu-id="73897-128">**Better**</span></span>|<span data-ttu-id="73897-129">**最佳**</span><span class="sxs-lookup"><span data-stu-id="73897-129">**Best**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73897-130">SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="73897-130">SharePoint Server 2010</span></span>  <br/> |<span data-ttu-id="73897-131">SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="73897-131">SharePoint Server 2013</span></span>  <br/> |<span data-ttu-id="73897-132">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="73897-132">SharePoint Online</span></span>  <br/> |
||<span data-ttu-id="73897-133">SharePoint 混合式</span><span class="sxs-lookup"><span data-stu-id="73897-133">SharePoint Hybrid</span></span>  <br/> |<span data-ttu-id="73897-134">SharePoint Server 2016</span><span class="sxs-lookup"><span data-stu-id="73897-134">SharePoint Server 2016</span></span>  <br/> |
| | |<span data-ttu-id="73897-135">SharePoint 混合式</span><span class="sxs-lookup"><span data-stu-id="73897-135">SharePoint Hybrid</span></span>  <br/> |
   
<span data-ttu-id="73897-136">如果您選擇規模低端的選項 (足夠好) ，請記住在完成從 SharePoint Server 2007 遷移後，您必須立即開始規劃升級。</span><span class="sxs-lookup"><span data-stu-id="73897-136">If you choose options on the low end of the scale (good enough), remember you will need to begin planning for upgrade very soon after migration from SharePoint Server 2007 is complete.</span></span> <span data-ttu-id="73897-137">SharePoint Server 2007 的支援 (終止于2017年10月10日。</span><span class="sxs-lookup"><span data-stu-id="73897-137">(end of support for SharePoint Server 2007 is October 10, 2017.</span></span> <span data-ttu-id="73897-138">請注意，這些日期可能會變更，並會檢查 [產品生命週期網站](https://support.microsoft.com/lifecycle)。 ) </span><span class="sxs-lookup"><span data-stu-id="73897-138">Please note that these dates are subject to change and check the [Product Lifecycle site](https://support.microsoft.com/lifecycle).)</span></span>
  
## <a name="where-can-i-go-next"></a><span data-ttu-id="73897-139">下一步可以做什麼？</span><span class="sxs-lookup"><span data-stu-id="73897-139">Where can I go next?</span></span>

<span data-ttu-id="73897-140">SharePoint Server 可以在您自己的伺服器上安裝內部部署，也可以使用 SharePoint 線上，也就是 Microsoft 365 的一部分線上服務。</span><span class="sxs-lookup"><span data-stu-id="73897-140">SharePoint Server can be installed on-premises on your own servers, or you can use SharePoint Online, which is an online service that is part of Microsoft 365.</span></span> <span data-ttu-id="73897-141">您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="73897-141">You can choose to:</span></span>
  
- <span data-ttu-id="73897-142">移轉至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="73897-142">Migrate to SharePoint Online</span></span>
    
- <span data-ttu-id="73897-143">升級 SharePoint 伺服器內部部署</span><span class="sxs-lookup"><span data-stu-id="73897-143">Upgrade SharePoint Server on-premises</span></span>
    
- <span data-ttu-id="73897-144">進行上述兩種操作</span><span class="sxs-lookup"><span data-stu-id="73897-144">Do both of the above</span></span>
    
- <span data-ttu-id="73897-145">實施 [SharePoint 的混合](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx) 式解決方案</span><span class="sxs-lookup"><span data-stu-id="73897-145">Implement a [SharePoint hybrid](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx) solution</span></span> 
    
<span data-ttu-id="73897-146">請留意相關的隱藏成本，以維護伺服器陣列繼續進行、維護或遷移自訂專案，以及升級 SharePoint Server 所依賴的硬體。</span><span class="sxs-lookup"><span data-stu-id="73897-146">Be aware of hidden costs associated with maintaining a server farm going forward, maintaining or migrating customizations, and upgrading the hardware upon which SharePoint Server depends.</span></span> <span data-ttu-id="73897-147">如果是必要，請務必使用內部部署 SharePoint 伺服器陣列，否則會帶來必要的回報。否則，如果您在舊版的 SharePoint 伺服器上執行伺服器陣列，但沒有大量自訂，您可以從規劃的遷移受益到線上 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="73897-147">Having an on-premises SharePoint Server farm is rewarding if it is a necessity; otherwise, if you run your farm on legacy SharePoint Servers, without heavy customization, you can benefit from a planned migration to SharePoint Online.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="73897-148">如果不經常使用 SharePoint 2007 中的內容，則會有另一個選項。</span><span class="sxs-lookup"><span data-stu-id="73897-148">There is another option if the content in SharePoint 2007 is infrequently used.</span></span> <span data-ttu-id="73897-149">有些 SharePoint 管理員可以選擇建立 Microsoft 365 訂閱、設定全新的全新 SharePoint Online 網站，然後從 SharePoint 2007 中完全移除，只需將最基本的檔放至全新的 SharePoint 線上網站。</span><span class="sxs-lookup"><span data-stu-id="73897-149">Some SharePoint Administrators may choose to create a Microsoft 365 Subscription, set up a brand new SharePoint Online site, and then cut away from SharePoint 2007, cleanly, taking only the most essential documents to the fresh SharePoint Online sites.</span></span> <span data-ttu-id="73897-150">從該來源，資料可能會從 SharePoint 2007 網站耗盡成封存。</span><span class="sxs-lookup"><span data-stu-id="73897-150">From there, data may be drained from the SharePoint 2007 site into archives.</span></span> <span data-ttu-id="73897-151">讓考慮使用者如何使用 SharePoint 2007 安裝的資料。</span><span class="sxs-lookup"><span data-stu-id="73897-151">Give thought to how users work with data your SharePoint 2007 installation.</span></span> <span data-ttu-id="73897-152">可以採用創造性的方式來解決此問題！</span><span class="sxs-lookup"><span data-stu-id="73897-152">There may be creative ways to resolve this problem!</span></span> 
  
|<span data-ttu-id="73897-153">\*\*SharePoint 線上 (SPO) \*\*</span><span class="sxs-lookup"><span data-stu-id="73897-153">**SharePoint Online (SPO)**</span></span>|<span data-ttu-id="73897-154">**SharePoint Server 內部部署**</span><span class="sxs-lookup"><span data-stu-id="73897-154">**SharePoint Server on-premises**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73897-155">高成本的時間 (規劃/執行/驗證) </span><span class="sxs-lookup"><span data-stu-id="73897-155">High cost in time (plan / execution / verification)</span></span>  <br/> |<span data-ttu-id="73897-156">高成本的時間 (規劃/執行/驗證) </span><span class="sxs-lookup"><span data-stu-id="73897-156">High cost in time (plan / execution / verification)</span></span>  <br/> |
|<span data-ttu-id="73897-157">降低基金成本 (未購買硬體) </span><span class="sxs-lookup"><span data-stu-id="73897-157">Lower cost in funds (no hardware purchases)</span></span>  <br/> |<span data-ttu-id="73897-158">基金 (硬體 + devs/系統管理員的成本較高) </span><span class="sxs-lookup"><span data-stu-id="73897-158">Higher cost in funds (hardware + devs / admins)</span></span>  <br/> |
|<span data-ttu-id="73897-159">遷移時成本為一次</span><span class="sxs-lookup"><span data-stu-id="73897-159">One-time cost in migration</span></span>  <br/> |<span data-ttu-id="73897-160">每個未來遷移重複的單一時間成本</span><span class="sxs-lookup"><span data-stu-id="73897-160">One-time cost repeated per future migration</span></span>  <br/> |
|<span data-ttu-id="73897-161">低擁有權總成本/維護</span><span class="sxs-lookup"><span data-stu-id="73897-161">Low total cost of ownership / maintenance</span></span>  <br/> |<span data-ttu-id="73897-162">高擁有權總成本/維護</span><span class="sxs-lookup"><span data-stu-id="73897-162">High total cost of ownership / maintenance</span></span>  <br/> |
   
<span data-ttu-id="73897-163">當您遷移至 Microsoft 365 時，一次性移動會有較低的成本，而您正在組織資料，並決定要對雲端採取的功能和留下的功能。</span><span class="sxs-lookup"><span data-stu-id="73897-163">When you migrate to Microsoft 365, the one-time move will have a heavier cost up-front, while you're organizing data and deciding what to take to the cloud and what to leave behind.</span></span> <span data-ttu-id="73897-164">不過，將會自動從該點進行升級，您不再需要管理硬體和軟體更新，而且伺服器陣列的時間將由 Microsoft 服務等級協定 ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)) 所備份。</span><span class="sxs-lookup"><span data-stu-id="73897-164">However, upgrades will be automatic from that point, you will no longer need to manage hardware and software updates, and the up-time of your farm will be backed by a Microsoft Service Level Agreement ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)).</span></span>
  
### <a name="migrate-to-sharepoint-online"></a><span data-ttu-id="73897-165">移轉至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="73897-165">Migrate to SharePoint Online</span></span>

<span data-ttu-id="73897-166">請務必查閱相關聯的服務說明，以確定 SharePoint 線上具有您所需的所有功能。</span><span class="sxs-lookup"><span data-stu-id="73897-166">Make sure that SharePoint Online has all the features you need by reviewing the associated service description.</span></span> <span data-ttu-id="73897-167">請參閱 [Microsoft 365 和 Office 365 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)。</span><span class="sxs-lookup"><span data-stu-id="73897-167">See [Microsoft 365 and Office 365 service descriptions](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library).</span></span>
  
<span data-ttu-id="73897-168">沒有直接的方法可以從 SharePoint 2007 遷移至 SharePoint 線上;您的移動至 SharePoint 線上將會手動執行。</span><span class="sxs-lookup"><span data-stu-id="73897-168">There is no direct way to migrate from SharePoint 2007 to SharePoint Online; your move to SharePoint Online would be done manually.</span></span> <span data-ttu-id="73897-169">如果您升級為 SharePoint Server 2013 或 SharePoint Server 2016，您的移動可能也會涉及使用 SharePoint 遷移 API (將資訊遷移至商務 OneDrive （例如) ）。</span><span class="sxs-lookup"><span data-stu-id="73897-169">If you upgrade to SharePoint Server 2013 or SharePoint Server 2016, your move might also involve using the SharePoint Migration API (to migrate information into OneDrive for Business, for example).</span></span>
  
|<span data-ttu-id="73897-170">**線上專業人員**</span><span class="sxs-lookup"><span data-stu-id="73897-170">**Online Pro**</span></span>|<span data-ttu-id="73897-171">**線上 Con**</span><span class="sxs-lookup"><span data-stu-id="73897-171">**Online Con**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73897-172">Microsoft 提供 SPO 硬體和所有硬體管理。</span><span class="sxs-lookup"><span data-stu-id="73897-172">Microsoft supplies SPO hardware and all hardware administration.</span></span>  <br/> |<span data-ttu-id="73897-173">SharePoint Server 內部部署和 SPO 之間可用的功能可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="73897-173">Available features may be different between SharePoint Server on-premises and SPO.</span></span>  <br/> |
|<span data-ttu-id="73897-174">您是訂閱的全域系統管理員，而且可以指派系統管理員 SPO 網站。</span><span class="sxs-lookup"><span data-stu-id="73897-174">You are the global administrator of your subscription, and may assign administrators to SPO sites.</span></span>  <br/> |<span data-ttu-id="73897-175">SharePoint Server 內部部署中的伺服器陣列管理員可使用的部分動作不存在 (或不是必要) 包含在 Microsoft 365 的 SharePoint 系統管理員角色中。</span><span class="sxs-lookup"><span data-stu-id="73897-175">Some actions available to a Farm Administrator in SharePoint Server on-premises do not exist (or are not necessary) included in the SharePoint Administrator role in Microsoft 365.</span></span>  <br/> |
|<span data-ttu-id="73897-176">Microsoft 會對底層的硬體和軟體套用修補程式、修正及更新。</span><span class="sxs-lookup"><span data-stu-id="73897-176">Microsoft applies patches, fixes and updates to underlying hardware and software.</span></span>  <br/> |<span data-ttu-id="73897-177">由於服務沒有存取基礎檔案系統，因此某些自訂專案有限。</span><span class="sxs-lookup"><span data-stu-id="73897-177">Because there is no access to the underlying file system in the service, some customizations are limited.</span></span>  <br/> |
|<span data-ttu-id="73897-178">Microsoft 發佈 [服務等級協定](https://go.microsoft.com/fwlink/?linkid=843153) ，並快速移動以解決服務等級事件。</span><span class="sxs-lookup"><span data-stu-id="73897-178">Microsoft publishes [Service Level Agreements](https://go.microsoft.com/fwlink/?linkid=843153) and moves quickly to resolve service level incidents.</span></span>  <br/> |<span data-ttu-id="73897-179">備份與還原和其他修復選項會透過服務自動覆寫 SharePoint 線上備份會覆寫（如果不使用）。</span><span class="sxs-lookup"><span data-stu-id="73897-179">Backup and restore and other recovery options are automated by the service in SharePoint Online - backups are overwritten if not used.</span></span>  <br/> |
|<span data-ttu-id="73897-180">安全性測試和伺服器效能調整是由 Microsoft 在服務中持續執行。</span><span class="sxs-lookup"><span data-stu-id="73897-180">Security testing and server performance tuning are carried out on an ongoing basis in the service by Microsoft.</span></span>  <br/> |<span data-ttu-id="73897-181">變更使用者介面及其他 SharePoint 功能會由服務安裝，而且可能需要切換開啟或關閉。</span><span class="sxs-lookup"><span data-stu-id="73897-181">Changes to the user interface and other SharePoint features are installed by the service and may need to be toggled on or off.</span></span>  <br/> |
|<span data-ttu-id="73897-182">Microsoft 365 符合許多行業標準： [microsoft 規範服務](https://go.microsoft.com/fwlink/?linkid=843165)。</span><span class="sxs-lookup"><span data-stu-id="73897-182">Microsoft 365 meets many industry standards: [Microsoft compliance offerings](https://go.microsoft.com/fwlink/?linkid=843165).</span></span>  <br/> |<span data-ttu-id="73897-183">遷移的[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)協助是有限的。</span><span class="sxs-lookup"><span data-stu-id="73897-183">[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) assistance for migration is limited.</span></span>  <br/> <span data-ttu-id="73897-184">大部分的升級是手動或透過 [SharePoint 線上和 OneDrive 遷移內容藍圖](https://go.microsoft.com/fwlink/?linkid=843184)中所述的 SPO 遷移 API。</span><span class="sxs-lookup"><span data-stu-id="73897-184">Much of the upgrade will be manual, or via the SPO Migration API described in the [SharePoint Online and OneDrive Migration Content Roadmap](https://go.microsoft.com/fwlink/?linkid=843184).</span></span>  <br/> |
|<span data-ttu-id="73897-185">Microsoft 支援工程師和資料中心內的員工都沒有無限制的系統管理員存取您的訂閱。</span><span class="sxs-lookup"><span data-stu-id="73897-185">Neither Microsoft Support Engineers nor employees in the datacenter have unrestricted admin access to your subscription.</span></span>  <br/> |<span data-ttu-id="73897-186">若需要升級硬體基礎結構以支援較新版本的 SharePoint，或若升級需要次要伺服器陣列，可能會有額外的成本。</span><span class="sxs-lookup"><span data-stu-id="73897-186">There can be additional costs if hardware infrastructure needs to be upgraded to support the newer version of SharePoint, or if a secondary farm is required for upgrade.</span></span>  <br/> |
|<span data-ttu-id="73897-187">合作夥伴可協助您將資料移轉到線上 SharePoint 的單一時間工作。</span><span class="sxs-lookup"><span data-stu-id="73897-187">Partners can assist with the one-time job of migrating your data to SharePoint Online.</span></span>  <br/> ||
|<span data-ttu-id="73897-188">線上產品會自動更新整個服務的意義，但功能可能會取代，而且不會有真正的支援端點。</span><span class="sxs-lookup"><span data-stu-id="73897-188">Online products are updated automatically across the service meaning that though features may deprecate, there is no true end of support.</span></span>  <br/> ||
   
<span data-ttu-id="73897-189">如果您決定建立新的 Microsoft 365 網站，並在需要時手動將資料移轉到它，您可以查看您的 [Microsoft 365 選項](https://www.microsoft.com/microsoft-365/)。</span><span class="sxs-lookup"><span data-stu-id="73897-189">If you've decided to create a new Microsoft 365 site, and will manually migrate data to it as is needed, you can look at your [Microsoft 365 options](https://www.microsoft.com/microsoft-365/).</span></span>
  
### <a name="upgrade-sharepoint-server-on-premises"></a><span data-ttu-id="73897-190">升級 SharePoint 伺服器內部部署</span><span class="sxs-lookup"><span data-stu-id="73897-190">Upgrade SharePoint Server on-premises</span></span>

<span data-ttu-id="73897-191">過去沒有任何方法可以略過 SharePoint 升級的版本，至少不會在發行 SharePoint Server 2016。</span><span class="sxs-lookup"><span data-stu-id="73897-191">There is historically no way to skip versions in SharePoint Upgrades, at least not as of the release of SharePoint Server 2016.</span></span> <span data-ttu-id="73897-192">這表示升級順序如下：</span><span class="sxs-lookup"><span data-stu-id="73897-192">That means upgrades go serially:</span></span>
  
- <span data-ttu-id="73897-193">SharePoint 2007 \> SharePoint server 2010 \> SharePoint server 2013 \> SharePoint server 2016</span><span class="sxs-lookup"><span data-stu-id="73897-193">SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016</span></span>
   
<span data-ttu-id="73897-194">若要從 SharePoint 2007 到 SharePoint Server 2016 的完整途徑，將會帶來大量的時間，而且在升級的硬體方面需要成本 (請注意，SQL server 也必須升級) 、軟體和管理。</span><span class="sxs-lookup"><span data-stu-id="73897-194">To take the entire path from SharePoint 2007 to SharePoint Server 2016 will mean a significant investment of time and will involve a cost in terms of upgraded hardware (be aware that SQL servers must also be upgraded), software, and administration.</span></span> <span data-ttu-id="73897-195">根據功能的重要性，必須升級或放棄自訂專案。</span><span class="sxs-lookup"><span data-stu-id="73897-195">Customizations will need to be upgraded or abandoned, according to the criticality of the feature.</span></span>
  
> [!NOTE]
> <span data-ttu-id="73897-196">您可以維持生命週期的 SharePoint 2007 伺服器陣列，在新的硬體 (上安裝 SharePoint 伺服器2016伺服器陣列，讓個別的伺服器陣列執行並列) ，然後規劃並執行手動遷移內容 (，以下載及重新上傳內容，例如) 。</span><span class="sxs-lookup"><span data-stu-id="73897-196">It's possible to maintain your end-of-life SharePoint 2007 farm, install a SharePoint Server 2016 farm on new hardware (so the separate farms run side-by-side), and then plan and execute a manual migration of content (for downloading and re-uploading content, for example).</span></span> <span data-ttu-id="73897-197">請注意，手動移動的部分陷阱 (例如，移動檔會以執行手動移動) 之帳戶的別名取代最後一個修改的帳戶，而必須在 (時間之前完成的工作，例如重新建立網站、子網站、許可權和清單結構) 。</span><span class="sxs-lookup"><span data-stu-id="73897-197">Be aware of some of the gotchas of manual moves (such as moves of documents replacing the last modified account with the alias of the account doing the manual move), and the work that must be done ahead of time (such as recreating sites, sub-sites, permissions and list structures).</span></span> <span data-ttu-id="73897-198">同樣地，這是考慮您可以移至儲存體或不再需要的資料，可降低遷移影響的動作。</span><span class="sxs-lookup"><span data-stu-id="73897-198">Again, this is the time to consider what data you can move into storage, or no longer need, an action that can reduce the impact of migration.</span></span>
  
<span data-ttu-id="73897-199">無論是哪種方式，在升級之前先清理您的環境。</span><span class="sxs-lookup"><span data-stu-id="73897-199">Either way, clean your environment prior to upgrade.</span></span> <span data-ttu-id="73897-200">請確定您的現有伺服器陣列在升級之前是否運作正常，並在您解除委任之前 (以確認) ！</span><span class="sxs-lookup"><span data-stu-id="73897-200">Be certain your existing farm is functional before you upgrade, and (for sure) before you decommission!</span></span> 
  
<span data-ttu-id="73897-201">請記得查看 **支援和不支援的升級路徑**：</span><span class="sxs-lookup"><span data-stu-id="73897-201">Remember to review the **supported and unsupported upgrade paths**:</span></span> 
  
- [<span data-ttu-id="73897-202">SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="73897-202">SharePoint Server 2007</span></span>](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [<span data-ttu-id="73897-203">SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="73897-203">SharePoint Server 2010</span></span>](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [<span data-ttu-id="73897-204">SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="73897-204">SharePoint Server 2013</span></span>](https://go.microsoft.com/fwlink/?linkid=843157)
    
<span data-ttu-id="73897-205">如果您有 **自訂**，請務必為遷移路徑中的每個步驟規劃升級：</span><span class="sxs-lookup"><span data-stu-id="73897-205">If you have **customizations**, it's critical you have a plan your upgrade for each step in the migration path:</span></span> 
  
- [<span data-ttu-id="73897-206">SharePoint 2007</span><span class="sxs-lookup"><span data-stu-id="73897-206">SharePoint 2007</span></span>](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [<span data-ttu-id="73897-207">SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="73897-207">SharePoint Server 2010</span></span>](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [<span data-ttu-id="73897-208">SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="73897-208">SharePoint Server 2013</span></span>](https://go.microsoft.com/fwlink/?linkid=843162)
    
|<span data-ttu-id="73897-209">**內部部署 Pro**</span><span class="sxs-lookup"><span data-stu-id="73897-209">**On-premises Pro**</span></span>|<span data-ttu-id="73897-210">**內部部署 Con**</span><span class="sxs-lookup"><span data-stu-id="73897-210">**On-premises Con**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73897-211">完全控制 SharePoint 伺服器陣列的所有層面，從伺服器硬體向上。</span><span class="sxs-lookup"><span data-stu-id="73897-211">Full control of all aspects of your SharePoint Farm, from the server hardware up.</span></span>  <br/> |<span data-ttu-id="73897-212">所有中斷和修正都是貴公司 (若您的產品並非支援服務，請與付費的 Microsoft 支援人員接洽) ：</span><span class="sxs-lookup"><span data-stu-id="73897-212">All breaks and fixes are the responsibility of your company (can engage paid Microsoft Support if your product is not at end of support):</span></span>  <br/> |
|<span data-ttu-id="73897-213">SharePoint Server 內部部署的完整功能集合，具有透過混合方式將內部部署伺服器陣列連線至 SharePoint Online 訂閱的選項。</span><span class="sxs-lookup"><span data-stu-id="73897-213">Full feature set of SharePoint Server on-premises with the option to connect your on-premises farm to a SharePoint Online subscription via hybrid.</span></span>  <br/> |<span data-ttu-id="73897-214">升級、修補程式、安全性修正程式，以及 SharePoint 伺服器的所有維護都受內部部署管理。</span><span class="sxs-lookup"><span data-stu-id="73897-214">Upgrade, patches, security fixes, and all maintenance of SharePoint Server managed on-premises.</span></span>  <br/> |
|<span data-ttu-id="73897-215">取得更佳自訂的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="73897-215">Full access for greater customization.</span></span>  <br/> |<span data-ttu-id="73897-216">[Microsoft 規範服務](https://go.microsoft.com/fwlink/?linkid=843165) 必須手動設定內部部署。</span><span class="sxs-lookup"><span data-stu-id="73897-216">[Microsoft compliance offerings](https://go.microsoft.com/fwlink/?linkid=843165) must be manually configured on-premises.</span></span>  <br/> |
|<span data-ttu-id="73897-217">在您的內部部署 (所執行的安全性測試和伺服器效能調整，都是由您的控制) 。</span><span class="sxs-lookup"><span data-stu-id="73897-217">Security testing, and server performance tuning, carried out on your premises (is under your control).</span></span>  <br/> |<span data-ttu-id="73897-218">Microsoft 365 可能使 SharePoint 線上使用的功能無法與內部部署 SharePoint 伺服器互動</span><span class="sxs-lookup"><span data-stu-id="73897-218">Microsoft 365 may make features available to SharePoint Online that do not interoperate with SharePoint Server on-premises</span></span>  <br/> |
|<span data-ttu-id="73897-219">合作夥伴可協助您將資料移轉至下一版的 SharePoint Server (且超過) 。</span><span class="sxs-lookup"><span data-stu-id="73897-219">Partners can assist with migrating data to the next version of SharePoint Server (and beyond).</span></span>  <br/> |<span data-ttu-id="73897-220">您的 SharePoint 伺服器網站不會自動使用 SharePoint Online 中所看到 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 憑證。</span><span class="sxs-lookup"><span data-stu-id="73897-220">Your SharePoint Server sites will not automatically use [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) certificates as is seen in SharePoint Online.</span></span>  <br/> |
|<span data-ttu-id="73897-221">在內部部署中 SharePoint Server 內部部署命名慣例、備份與還原及其他復原選項的完整控制權。</span><span class="sxs-lookup"><span data-stu-id="73897-221">Full control of naming conventions, backup and restore and other recovery options in SharePoint Server on-premises.</span></span>  <br/> |<span data-ttu-id="73897-222">SharePoint Server 內部部署對產品生命週期保密。</span><span class="sxs-lookup"><span data-stu-id="73897-222">SharePoint Server on-premises is sensitive to product lifecycles.</span></span>  <br/> |
   
### <a name="upgrade-resources"></a><span data-ttu-id="73897-223">升級資源</span><span class="sxs-lookup"><span data-stu-id="73897-223">Upgrade Resources</span></span>

<span data-ttu-id="73897-224">請先知道您符合硬體和軟體需求，然後再遵循支援的升級方法。</span><span class="sxs-lookup"><span data-stu-id="73897-224">Begin by knowing that you meet hardware and software requirements, then follow supported upgrade methods.</span></span>
  
- <span data-ttu-id="73897-225">**硬體/軟體需求**：</span><span class="sxs-lookup"><span data-stu-id="73897-225">**Hardware/software requirements for**:</span></span> 
    
    <span data-ttu-id="73897-226">[SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)</span><span class="sxs-lookup"><span data-stu-id="73897-226">[SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204) | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204) | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206) | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)</span></span>
    
- <span data-ttu-id="73897-227">**軟體界限和限制**：</span><span class="sxs-lookup"><span data-stu-id="73897-227">**Software boundaries and limits for**:</span></span> 
    
    <span data-ttu-id="73897-228">[SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)</span><span class="sxs-lookup"><span data-stu-id="73897-228">[SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245) | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247) | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248) | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)</span></span>
    
- <span data-ttu-id="73897-229">下列專案**的升級程式概述**：</span><span class="sxs-lookup"><span data-stu-id="73897-229">**The upgrade process overview for**:</span></span> 
    
    <span data-ttu-id="73897-230">[SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)</span><span class="sxs-lookup"><span data-stu-id="73897-230">[SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250) | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251) | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252) | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)</span></span>
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a><span data-ttu-id="73897-231">在 SharePoint Online 與內部部署之間建立 SharePoint 的混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="73897-231">Create a SharePoint hybrid solution between SharePoint Online and on-premises</span></span>

<span data-ttu-id="73897-232">如果您對遷移的答案是在內部部署所提供的自我控制之間的某個地方，而且 SharePoint Online 提供的擁有成本較低，您可以透過混合方式，將 SharePoint Server 2013 或2016伺服器陣列連線至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="73897-232">If the answer to your migration needs is somewhere between the self-control offered by on-premises, and the lower cost of ownership offered by SharePoint Online, you can connect SharePoint Server 2013 or 2016 farms to SharePoint Online, through hybrids.</span></span> [<span data-ttu-id="73897-233">深入瞭解 SharePoint 混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="73897-233">Learn about SharePoint hybrid solutions</span></span>](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
<span data-ttu-id="73897-234">如果您決定混合式 SharePoint 伺服器陣列將會對您的業務帶來好處，請熟悉現有的混合式類型，以及如何設定內部部署 SharePoint 伺服器陣列與 Microsoft 365 訂閱之間的連線。</span><span class="sxs-lookup"><span data-stu-id="73897-234">If you decide that a hybrid SharePoint Server farm will benefit your business, familiarize yourself with the existing types of hybrid and how to configure the connection between your on-premises SharePoint farm and your Microsoft 365 subscription.</span></span>
  
| <span data-ttu-id="73897-235">選項</span><span class="sxs-lookup"><span data-stu-id="73897-235">Option</span></span> | <span data-ttu-id="73897-236">描述</span><span class="sxs-lookup"><span data-stu-id="73897-236">Description</span></span> |
|:-----|:-----|
<span data-ttu-id="73897-237">[Microsoft 規範服務](https://go.microsoft.com/fwlink/?linkid=843165)。</span><span class="sxs-lookup"><span data-stu-id="73897-237">[Microsoft compliance offerings](https://go.microsoft.com/fwlink/?linkid=843165).</span></span>  <br/> |<span data-ttu-id="73897-238">遷移的[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)協助是有限的。</span><span class="sxs-lookup"><span data-stu-id="73897-238">[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) assistance for migration is limited.</span></span>  <br/> <span data-ttu-id="73897-239">大部分的升級是手動或透過 [SharePoint 線上和 OneDrive 遷移內容藍圖](https://go.microsoft.com/fwlink/?linkid=843184)中所述的 SPO 遷移 API。</span><span class="sxs-lookup"><span data-stu-id="73897-239">Much of the upgrade will be manual, or via the SPO Migration API described in the [SharePoint Online and OneDrive Migration Content Roadmap](https://go.microsoft.com/fwlink/?linkid=843184).</span></span>  <br/> |
|<span data-ttu-id="73897-240">Microsoft 支援工程師和資料中心內的員工都沒有無限制的系統管理員存取您的訂閱。</span><span class="sxs-lookup"><span data-stu-id="73897-240">Neither Microsoft Support Engineers nor employees in the datacenter have unrestricted admin access to your subscription.</span></span>  <br/> |<span data-ttu-id="73897-241">若需要升級硬體基礎結構以支援較新版本的 SharePoint，或若升級需要次要伺服器陣列，可能會有額外的成本。</span><span class="sxs-lookup"><span data-stu-id="73897-241">There can be additional costs if hardware infrastructure needs to be upgraded to support the newer version of SharePoint, or if a secondary farm is required for upgrade.</span></span>  <br/> |
|<span data-ttu-id="73897-242">合作夥伴可協助您將資料移轉到線上 SharePoint 的單一時間工作。</span><span class="sxs-lookup"><span data-stu-id="73897-242">Partners can assist with the one-time job of migrating your data to SharePoint Online.</span></span>  <br/> ||
|<span data-ttu-id="73897-243">線上產品會自動更新整個服務的意義，但功能可能會取代，而且不會有真正的支援端點。</span><span class="sxs-lookup"><span data-stu-id="73897-243">Online products are updated automatically across the service meaning that though features may deprecate, there is no true end of support.</span></span>  <br/> ||
   
<span data-ttu-id="73897-244">如果您決定建立新的 Microsoft 365 網站，並在需要時手動將資料移轉到它，您可以查看您的 [Microsoft 365 選項](https://www.microsoft.com/microsoft-365/)。</span><span class="sxs-lookup"><span data-stu-id="73897-244">If you've decided to create a new Microsoft 365 site, and will manually migrate data to it as is needed, you can look at your [Microsoft 365 options](https://www.microsoft.com/microsoft-365/).</span></span>
  
### <a name="upgrade-sharepoint-server-on-premises"></a><span data-ttu-id="73897-245">升級 SharePoint 伺服器內部部署</span><span class="sxs-lookup"><span data-stu-id="73897-245">Upgrade SharePoint Server on-premises</span></span>

<span data-ttu-id="73897-246">過去沒有任何方法可以略過 SharePoint 升級的版本，至少不會在發行 SharePoint Server 2016。</span><span class="sxs-lookup"><span data-stu-id="73897-246">There is historically no way to skip versions in SharePoint Upgrades, at least not as of the release of SharePoint Server 2016.</span></span> <span data-ttu-id="73897-247">這表示升級順序如下：</span><span class="sxs-lookup"><span data-stu-id="73897-247">That means upgrades go serially:</span></span>
  
- <span data-ttu-id="73897-248">SharePoint 2007 \> SharePoint server 2010 \> SharePoint server 2013 \> SharePoint server 2016</span><span class="sxs-lookup"><span data-stu-id="73897-248">SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016</span></span>
   
<span data-ttu-id="73897-249">若要從 SharePoint 2007 到 SharePoint Server 2016 的完整途徑，將會帶來大量的時間，而且在升級的硬體方面需要成本 (請注意，SQL server 也必須升級) 、軟體和管理。</span><span class="sxs-lookup"><span data-stu-id="73897-249">To take the entire path from SharePoint 2007 to SharePoint Server 2016 will mean a significant investment of time and will involve a cost in terms of upgraded hardware (be aware that SQL servers must also be upgraded), software, and administration.</span></span> <span data-ttu-id="73897-250">根據功能的重要性，必須升級或放棄自訂專案。</span><span class="sxs-lookup"><span data-stu-id="73897-250">Customizations will need to be upgraded or abandoned, according to the criticality of the feature.</span></span>
  
> [!NOTE]
> <span data-ttu-id="73897-251">您可以維持生命週期的 SharePoint 2007 伺服器陣列，在新的硬體 (上安裝 SharePoint 伺服器2016伺服器陣列，讓個別的伺服器陣列執行並列) ，然後規劃並執行手動遷移內容 (，以下載及重新上傳內容，例如) 。</span><span class="sxs-lookup"><span data-stu-id="73897-251">It's possible to maintain your end-of-life SharePoint 2007 farm, install a SharePoint Server 2016 farm on new hardware (so the separate farms run side-by-side), and then plan and execute a manual migration of content (for downloading and re-uploading content, for example).</span></span> <span data-ttu-id="73897-252">請注意，手動移動的部分陷阱 (例如，移動檔會以執行手動移動) 之帳戶的別名取代最後一個修改的帳戶，而必須在 (時間之前完成的工作，例如重新建立網站、子網站、許可權和清單結構) 。</span><span class="sxs-lookup"><span data-stu-id="73897-252">Be aware of some of the gotchas of manual moves (such as moves of documents replacing the last modified account with the alias of the account doing the manual move), and the work that must be done ahead of time (such as recreating sites, sub-sites, permissions and list structures).</span></span> <span data-ttu-id="73897-253">同樣地，這是考慮您可以移至儲存體或不再需要的資料，可降低遷移影響的動作。</span><span class="sxs-lookup"><span data-stu-id="73897-253">Again, this is the time to consider what data you can move into storage, or no longer need, an action that can reduce the impact of migration.</span></span>
  
<span data-ttu-id="73897-254">無論是哪種方式，在升級之前先清理您的環境。</span><span class="sxs-lookup"><span data-stu-id="73897-254">Either way, clean your environment prior to upgrade.</span></span> <span data-ttu-id="73897-255">請確定您的現有伺服器陣列在升級之前是否運作正常，並在您解除委任之前 (以確認) ！</span><span class="sxs-lookup"><span data-stu-id="73897-255">Be certain your existing farm is functional before you upgrade, and (for sure) before you decommission!</span></span> 
  
<span data-ttu-id="73897-256">請記得查看 **支援和不支援的升級路徑**：</span><span class="sxs-lookup"><span data-stu-id="73897-256">Remember to review the **supported and unsupported upgrade paths**:</span></span> 
  
- [<span data-ttu-id="73897-257">SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="73897-257">SharePoint Server 2007</span></span>](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [<span data-ttu-id="73897-258">SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="73897-258">SharePoint Server 2010</span></span>](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [<span data-ttu-id="73897-259">SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="73897-259">SharePoint Server 2013</span></span>](https://go.microsoft.com/fwlink/?linkid=843157)
    
<span data-ttu-id="73897-260">如果您有 **自訂**，請務必為遷移路徑中的每個步驟規劃升級：</span><span class="sxs-lookup"><span data-stu-id="73897-260">If you have **customizations**, it's critical you have a plan your upgrade for each step in the migration path:</span></span> 
  
- [<span data-ttu-id="73897-261">SharePoint 2007</span><span class="sxs-lookup"><span data-stu-id="73897-261">SharePoint 2007</span></span>](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [<span data-ttu-id="73897-262">SharePoint Server 2010</span><span class="sxs-lookup"><span data-stu-id="73897-262">SharePoint Server 2010</span></span>](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [<span data-ttu-id="73897-263">SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="73897-263">SharePoint Server 2013</span></span>](https://go.microsoft.com/fwlink/?linkid=843162)
    
|<span data-ttu-id="73897-264">**內部部署 Pro**</span><span class="sxs-lookup"><span data-stu-id="73897-264">**On-premises Pro**</span></span>|<span data-ttu-id="73897-265">**內部部署 Con**</span><span class="sxs-lookup"><span data-stu-id="73897-265">**On-premises Con**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73897-266">完全控制 SharePoint 伺服器陣列的所有層面，從伺服器硬體向上。</span><span class="sxs-lookup"><span data-stu-id="73897-266">Full control of all aspects of your SharePoint Farm, from the server hardware up.</span></span>  <br/> |<span data-ttu-id="73897-267">所有中斷和修正都是貴公司 (若您的產品並非支援服務，請與付費的 Microsoft 支援人員接洽) ：</span><span class="sxs-lookup"><span data-stu-id="73897-267">All breaks and fixes are the responsibility of your company (can engage paid Microsoft Support if your product is not at end of support):</span></span>  <br/> |
|<span data-ttu-id="73897-268">SharePoint Server 內部部署的完整功能集合，具有透過混合方式將內部部署伺服器陣列連線至 SharePoint Online 訂閱的選項。</span><span class="sxs-lookup"><span data-stu-id="73897-268">Full feature set of SharePoint Server on-premises with the option to connect your on-premises farm to a SharePoint Online subscription via hybrid.</span></span>  <br/> |<span data-ttu-id="73897-269">升級、修補程式、安全性修正程式，以及 SharePoint 伺服器的所有維護都受內部部署管理。</span><span class="sxs-lookup"><span data-stu-id="73897-269">Upgrade, patches, security fixes, and all maintenance of SharePoint Server managed on-premises.</span></span>  <br/> |
|<span data-ttu-id="73897-270">取得更佳自訂的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="73897-270">Full access for greater customization.</span></span>  <br/> |<span data-ttu-id="73897-271">[Microsoft 規範服務](https://go.microsoft.com/fwlink/?linkid=843165) 必須手動設定內部部署。</span><span class="sxs-lookup"><span data-stu-id="73897-271">[Microsoft compliance offerings](https://go.microsoft.com/fwlink/?linkid=843165) must be manually configured on-premises.</span></span>  <br/> |
|<span data-ttu-id="73897-272">在您的內部部署 (所執行的安全性測試和伺服器效能調整，都是由您的控制) 。</span><span class="sxs-lookup"><span data-stu-id="73897-272">Security testing, and server performance tuning, carried out on your premises (is under your control).</span></span>  <br/> |<span data-ttu-id="73897-273">Microsoft 365 可能使 SharePoint 線上使用的功能無法與內部部署 SharePoint 伺服器互動</span><span class="sxs-lookup"><span data-stu-id="73897-273">Microsoft 365 may make features available to SharePoint Online that do not interoperate with SharePoint Server on-premises</span></span>  <br/> |
|<span data-ttu-id="73897-274">合作夥伴可協助您將資料移轉至下一版的 SharePoint Server (且超過) 。</span><span class="sxs-lookup"><span data-stu-id="73897-274">Partners can assist with migrating data to the next version of SharePoint Server (and beyond).</span></span>  <br/> |<span data-ttu-id="73897-275">您的 SharePoint 伺服器網站不會自動使用 SharePoint Online 中所看到 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 憑證。</span><span class="sxs-lookup"><span data-stu-id="73897-275">Your SharePoint Server sites will not automatically use [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) certificates as is seen in SharePoint Online.</span></span>  <br/> |
|<span data-ttu-id="73897-276">在內部部署中 SharePoint Server 內部部署命名慣例、備份與還原及其他復原選項的完整控制權。</span><span class="sxs-lookup"><span data-stu-id="73897-276">Full control of naming conventions, backup and restore and other recovery options in SharePoint Server on-premises.</span></span>  <br/> |<span data-ttu-id="73897-277">SharePoint Server 內部部署對產品生命週期保密。</span><span class="sxs-lookup"><span data-stu-id="73897-277">SharePoint Server on-premises is sensitive to product lifecycles.</span></span>  <br/> |
   
### <a name="upgrade-resources"></a><span data-ttu-id="73897-278">升級資源</span><span class="sxs-lookup"><span data-stu-id="73897-278">Upgrade Resources</span></span>

<span data-ttu-id="73897-279">請先知道您符合硬體和軟體需求，然後再遵循支援的升級方法。</span><span class="sxs-lookup"><span data-stu-id="73897-279">Begin by knowing that you meet hardware and software requirements, then follow supported upgrade methods.</span></span>
  
- <span data-ttu-id="73897-280">**硬體/軟體需求**：</span><span class="sxs-lookup"><span data-stu-id="73897-280">**Hardware/software requirements for**:</span></span> 
    
    <span data-ttu-id="73897-281">[SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)</span><span class="sxs-lookup"><span data-stu-id="73897-281">[SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204) | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204) | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206) | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)</span></span>
    
- <span data-ttu-id="73897-282">**軟體界限和限制**：</span><span class="sxs-lookup"><span data-stu-id="73897-282">**Software boundaries and limits for**:</span></span> 
    
    <span data-ttu-id="73897-283">[SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)</span><span class="sxs-lookup"><span data-stu-id="73897-283">[SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245) | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247) | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248) | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)</span></span>
    
- <span data-ttu-id="73897-284">下列專案**的升級程式概述**：</span><span class="sxs-lookup"><span data-stu-id="73897-284">**The upgrade process overview for**:</span></span> 
    
    <span data-ttu-id="73897-285">[SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)</span><span class="sxs-lookup"><span data-stu-id="73897-285">[SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250) | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251) | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252) | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)</span></span>
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a><span data-ttu-id="73897-286">在 SharePoint Online 與內部部署之間建立 SharePoint 的混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="73897-286">Create a SharePoint hybrid solution between SharePoint Online and on-premises</span></span>

<span data-ttu-id="73897-287">如果您對遷移的答案是在內部部署所提供的自我控制之間的某個地方，而且 SharePoint Online 提供的擁有成本較低，您可以透過混合方式，將 SharePoint Server 2013 或2016伺服器陣列連線至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="73897-287">If the answer to your migration needs is somewhere between the self-control offered by on-premises, and the lower cost of ownership offered by SharePoint Online, you can connect SharePoint Server 2013 or 2016 farms to SharePoint Online, through hybrids.</span></span> [<span data-ttu-id="73897-288">深入瞭解 SharePoint 混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="73897-288">Learn about SharePoint hybrid solutions</span></span>](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
<span data-ttu-id="73897-289">如果您決定混合式 SharePoint 伺服器陣列將會對您的業務帶來好處，請熟悉現有的混合式類型，以及如何設定內部部署 SharePoint 伺服器陣列與 Microsoft 365 訂閱之間的連線。</span><span class="sxs-lookup"><span data-stu-id="73897-289">If you decide that a hybrid SharePoint Server farm will benefit your business, familiarize yourself with the existing types of hybrid and how to configure the connection between your on-premises SharePoint farm and your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="73897-290">若要瞭解其運作方式的一個好方法是建立 Microsoft 365 開發/測試環境，您可以使用 [測試實驗室指南](m365-enterprise-test-lab-guides.md)加以設定。</span><span class="sxs-lookup"><span data-stu-id="73897-290">One good way to see how this works is by creating a Microsoft 365 dev/test environment, which you can set up with [Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span> <span data-ttu-id="73897-291">當您擁有試用版或購買的 Microsoft 365 訂閱後，您就可以在 SharePoint Online 中建立網站集合、網站及文件庫，以透過使用遷移 API 的方式手動遷移資料 (或-如果您想要透過混合式的嚮導) 將「我的網站」內容遷移至 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="73897-291">Once you have a trial or purchased Microsoft 365 subscription, you'll be on your way to creating the site collections, webs, and document libraries in SharePoint Online to which you can migrate data (either manually, by use of the Migration API, or - if you want to migrate My Site content to OneDrive for Business - through the hybrid wizard).</span></span>
  
> [!NOTE]
> <span data-ttu-id="73897-292">請記住，您的 SharePoint 2007 伺服器陣列將需要升級為 SharePoint Server 2013 或 SharePoint Server 2016，以使用混合選項</span><span class="sxs-lookup"><span data-stu-id="73897-292">Remember that your SharePoint 2007 farm will need to be upgraded, on-premises, to either SharePoint Server 2013 or SharePoint Server 2016 to use the hybrid option</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="73897-293">相關主題</span><span class="sxs-lookup"><span data-stu-id="73897-293">Related topics</span></span>

[<span data-ttu-id="73897-294">疑難排解並繼續升級 (Office SharePoint Server 2007) </span><span class="sxs-lookup"><span data-stu-id="73897-294">Troubleshoot and resume upgrade (Office SharePoint Server 2007)</span></span>](https://go.microsoft.com/fwlink/?linkid=843192)
  
[<span data-ttu-id="73897-295"> (SharePoint Server 2010 的升級問題疑難排解) </span><span class="sxs-lookup"><span data-stu-id="73897-295">Troubleshoot upgrade issues (SharePoint Server 2010)</span></span>](https://go.microsoft.com/fwlink/?linkid=843194)
  
[<span data-ttu-id="73897-296">在 SharePoint 2013 中針對資料庫的升級問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="73897-296">Troubleshoot database upgrade issues in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/?linkid=843195)
  
[<span data-ttu-id="73897-297">搜尋 Microsoft 合作夥伴以協助升級</span><span class="sxs-lookup"><span data-stu-id="73897-297">Search for Microsoft Partners to help with Upgrade</span></span>](https://go.microsoft.com/fwlink/?linkid=841249)
  
[<span data-ttu-id="73897-298">協助您從 Office 2007 伺服器及用戶端升級的資源</span><span class="sxs-lookup"><span data-stu-id="73897-298">Resources to help you upgrade from Office 2007 servers and clients</span></span>](upgrade-from-office-2007-servers-and-products.md)
  

