---
title: SharePoint 2007 要考慮的遷移選項
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 本文包含使用 SharePoint Server 2007 之使用者的資訊，以協助他們規劃升級。
ms.openlocfilehash: 3e37a01f1a2d387cda6723a8df1f73734fa3ba9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694951"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a><span data-ttu-id="a6121-103">SharePoint 2007 要考慮的遷移選項</span><span class="sxs-lookup"><span data-stu-id="a6121-103">SharePoint 2007 migration options to consider</span></span>

<span data-ttu-id="a6121-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="a6121-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a6121-105">Microsoft SharePoint 2007 和 SharePoint Server 2007 已到達支援的結尾。</span><span class="sxs-lookup"><span data-stu-id="a6121-105">Microsoft SharePoint 2007 and SharePoint Server 2007 have reached end of support.</span></span> <span data-ttu-id="a6121-106">是時候升級！</span><span class="sxs-lookup"><span data-stu-id="a6121-106">It's time to upgrade!</span></span> <span data-ttu-id="a6121-107">本文提供遷移選項的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a6121-107">This article provides information about your migration options.</span></span>
  
## <a name="common-upgrade-strategies-for-sharepoint"></a><span data-ttu-id="a6121-108">SharePoint 的常見升級策略</span><span class="sxs-lookup"><span data-stu-id="a6121-108">Common upgrade strategies for SharePoint</span></span>

<span data-ttu-id="a6121-109">有多種方法可升級 SharePoint 伺服器環境。</span><span class="sxs-lookup"><span data-stu-id="a6121-109">There are multiple methods to upgrade a SharePoint Server environment.</span></span> <span data-ttu-id="a6121-110">如果您有 Microsoft Office SharePoint Server 2007 伺服器陣列，以下是升級方法的一些範例：</span><span class="sxs-lookup"><span data-stu-id="a6121-110">If you have a Microsoft Office SharePoint Server 2007 farm, here are some examples of the upgrade methods:</span></span>
  
- <span data-ttu-id="a6121-111">資料庫附加</span><span class="sxs-lookup"><span data-stu-id="a6121-111">Database attach</span></span>
    
- <span data-ttu-id="a6121-112">並列升級</span><span class="sxs-lookup"><span data-stu-id="a6121-112">Side-by-side upgrade</span></span>
    
- <span data-ttu-id="a6121-113">就地升級 </span><span class="sxs-lookup"><span data-stu-id="a6121-113">In-place upgrade</span></span>
    
- <span data-ttu-id="a6121-114">混合式升級 (就地搭配已拆離資料庫/個別資料庫附加) </span><span class="sxs-lookup"><span data-stu-id="a6121-114">Hybrid upgrade (in-place with detached databases / separate database attach)</span></span>
    
- <span data-ttu-id="a6121-115">SharePoint 混合 (連線至內部部署 SharePoint) </span><span class="sxs-lookup"><span data-stu-id="a6121-115">SharePoint hybrids (connect online to on-premises SharePoint)</span></span>
    
- <span data-ttu-id="a6121-116">在網站集合或文件庫之間手動移動資料</span><span class="sxs-lookup"><span data-stu-id="a6121-116">Manually move data between site collections or libraries</span></span>
    
- <span data-ttu-id="a6121-117">FastTrack 嚮導升級至 Microsoft 365 ([SharePoint 線上部署顧問](https://aka.ms/spoguidance)) </span><span class="sxs-lookup"><span data-stu-id="a6121-117">FastTrack Wizard upgrade to Microsoft 365 ([SharePoint Online deployment advisor](https://aka.ms/spoguidance))</span></span>
    
- <span data-ttu-id="a6121-118">在 Microsoft 365 中 SharePoint Online (SPO) 的遷移 API</span><span class="sxs-lookup"><span data-stu-id="a6121-118">Migration API to SharePoint Online (SPO) in Microsoft 365</span></span>
    
<span data-ttu-id="a6121-119">哪種方法最適合您？</span><span class="sxs-lookup"><span data-stu-id="a6121-119">What works best for you?</span></span>
  
<span data-ttu-id="a6121-120">在升級時，您對伺服器陣列的作用和用途的知識是戰術性的實力。</span><span class="sxs-lookup"><span data-stu-id="a6121-120">Your knowledge of what your farm does and is used for is a tactical strength when it comes to upgrade.</span></span> <span data-ttu-id="a6121-121">人們使用 SharePoint 伺服器陣列的方式，可協助您選擇您的選項。</span><span class="sxs-lookup"><span data-stu-id="a6121-121">The way people use the SharePoint Farm will help you choose from your options.</span></span>
  
> [!TIP]
> <span data-ttu-id="a6121-122">Microsoft Office SharePoint Server 2007 也有一個逐步升級，但這裡並未涵蓋此部分。</span><span class="sxs-lookup"><span data-stu-id="a6121-122">Microsoft Office SharePoint Server 2007 also has a gradual upgrade not covered here.</span></span> <span data-ttu-id="a6121-123">若要查看步驟特定升級文章的清單，請參閱 [SharePoint Server 2007 結束支援藍圖](sharepoint-2007-end-of-support.md)。</span><span class="sxs-lookup"><span data-stu-id="a6121-123">To see a list of step-specific upgrade articles see the [SharePoint Server 2007 end of support Roadmap](sharepoint-2007-end-of-support.md).</span></span> 
  
<span data-ttu-id="a6121-124">請記得檢查 [產品生命週期](https://support.microsoft.com/lifecycle/search) 和系統需求，以瞭解升級所用 SharePoint 的任何版本。</span><span class="sxs-lookup"><span data-stu-id="a6121-124">Remember to check the [Product Lifecycle](https://support.microsoft.com/lifecycle/search) and System Requirements for whatever version of SharePoint you're upgrading to.</span></span> <span data-ttu-id="a6121-125">如此一來，您就會知道下一次升級是必要的 (例如，如果您在傳統產品（如 SharePoint Server 2010）上暫停以規劃更多升級，請確定您知道其支援日期的結束日期) ，並確定您有支援方案的硬體。</span><span class="sxs-lookup"><span data-stu-id="a6121-125">This is so you'll be aware when the next upgrade will be necessary (for example, if you pause at a legacy product like SharePoint Server 2010 to plan for more upgrades, be sure you know its end of support date), and to be certain you have hardware that supports your plan.</span></span> 
  
<span data-ttu-id="a6121-126">如果您打算將部分（或全部）的 SharePoint 網站轉換為雲端中的 Microsoft 365，這是一段時間，可將 [microsoft 365 和 Office 365 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)的連結做成書簽。</span><span class="sxs-lookup"><span data-stu-id="a6121-126">If you're planning to transition some, or all, of your SharePoint sites to Microsoft 365 in the Cloud, this is a time to bookmark a link to the [Microsoft 365 and Office 365 service descriptions](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library).</span></span> <span data-ttu-id="a6121-127">您將需要服務說明，以瞭解 SharePoint 線上功能，以及它們與內部部署 SharePoint 伺服器的差異。</span><span class="sxs-lookup"><span data-stu-id="a6121-127">You'll need the Service Descriptions to learn about SharePoint Online features and how they might differ from on-premises SharePoint Server.</span></span> <span data-ttu-id="a6121-128">升級功能 Microsoft Office SharePoint Server 2007 伺服器陣列。</span><span class="sxs-lookup"><span data-stu-id="a6121-128">Upgrade functional Microsoft Office SharePoint Server 2007 farms.</span></span> <span data-ttu-id="a6121-129">如果您的安裝中有中斷的網站，請在升級之前加以修正。</span><span class="sxs-lookup"><span data-stu-id="a6121-129">If your installation has sites that are broken, fix them prior to upgrade.</span></span>
  
## <a name="a-note-about-managing-risk"></a><span data-ttu-id="a6121-130">有關管理風險的附注</span><span class="sxs-lookup"><span data-stu-id="a6121-130">A note about managing risk</span></span>

<span data-ttu-id="a6121-131">例如「並列」的方法對於升級邏輯的配置很重要。</span><span class="sxs-lookup"><span data-stu-id="a6121-131">Methods like 'side-by-side' are important in the scheme of upgrade logic.</span></span> <span data-ttu-id="a6121-132">當您同時升級時，您會維護 Microsoft Office SharePoint Server 2007 伺服器陣列，但建立伺服器陣列下一個版本的下一個版本 (SharePoint 伺服器 2010) 新的硬體上。</span><span class="sxs-lookup"><span data-stu-id="a6121-132">When you upgrade side-by-side, you maintain your Microsoft Office SharePoint Server 2007 farm, but build a farm the next version up from it (SharePoint Server 2010) on new hardware.</span></span> <span data-ttu-id="a6121-133">這可透過三種方式進行：</span><span class="sxs-lookup"><span data-stu-id="a6121-133">This helps in three ways:</span></span>
  
1. <span data-ttu-id="a6121-134">您有一個地方，您可以使用資料庫附加，將 Microsoft Office SharePoint Server 2007 資料庫備份，以分開升級。</span><span class="sxs-lookup"><span data-stu-id="a6121-134">You have a place to take backups of your Microsoft Office SharePoint Server 2007 databases to upgrade them separately, by using database attach.</span></span>
    
2. <span data-ttu-id="a6121-135">如果您找出的 Microsoft Office SharePoint Server 2007 伺服器陣列上只包含少量重要的文件庫和其他資訊，您可以選擇從 Microsoft Office SharePoint Server 2007 手動移動資料，以 SharePoint 伺服器2010，或是只將特定網站和網站帶至下一個版本 (這樣可讓您的工作更容易) 。</span><span class="sxs-lookup"><span data-stu-id="a6121-135">If you figure out that only a small number of critical document libraries and other information are in use on your Microsoft Office SharePoint Server 2007 farm, you can choose to manually move data from Microsoft Office SharePoint Server 2007 to SharePoint Server 2010, or take only specific sites and webs to the next version (which can make your job easier).</span></span>
    
3. <span data-ttu-id="a6121-136">您對 Microsoft Office SharePoint Server 2007 伺服器陣列所做的較少，就像您升級時，伺服器陣列包含的資料更安全。</span><span class="sxs-lookup"><span data-stu-id="a6121-136">The less you do to the Microsoft Office SharePoint Server 2007 server farm, directly, the safer the data that farm contains as you upgrade.</span></span>
    
<span data-ttu-id="a6121-137">In-Place 升級等方法將直接作用於您的 Microsoft Office SharePoint Server 2007 伺服器陣列，讓您更少的選項可放棄路徑，然後再從 pristine 環境重新開始。</span><span class="sxs-lookup"><span data-stu-id="a6121-137">Methods like In-Place upgrade will act directly on your Microsoft Office SharePoint Server 2007 farm, giving you fewer easy options to abandon a path and begin again with your pristine environment.</span></span> <span data-ttu-id="a6121-138">您可以盡可能組建一些安全措施， (例如進行原始環境的備份或測試) 。</span><span class="sxs-lookup"><span data-stu-id="a6121-138">As much as possible, build in some safety measures (like taking and testing backups of the original environment).</span></span> <span data-ttu-id="a6121-139">例如，如果您的 Microsoft Office SharePoint Server 2007 伺服器陣列是虛擬的，且是重複備份及還原的目的，請在升級服務時段之前備份及還原最新的資料庫。</span><span class="sxs-lookup"><span data-stu-id="a6121-139">For example, if your Microsoft Office SharePoint Server 2007 farm is virtual, and is duplicated for the purposes of backup and restore, then back-up and restore the most current databases prior to your service window for the upgrade.</span></span> <span data-ttu-id="a6121-140">知道您可以還原資料庫備份的選項，並不會使您成為安全保護，但可讓您高枕無憂。</span><span class="sxs-lookup"><span data-stu-id="a6121-140">Knowing that you have the option to restore database backups will not only give you a failsafe, it can give you peace of mind.</span></span>
  
> [!TIP]
> <span data-ttu-id="a6121-141">[Microsoft Office SharePoint Server 2007](https://technet.microsoft.com/library/cc261992%28v=office.12%29.aspx)、 [SharePoint Server 2010](https://technet.microsoft.com/library/cc261992%28v=office.14%29.aspx)、 [SharePoint Server 2013](https://technet.microsoft.com/library/cc261992%28v=office.15%29.aspx)及[SharePoint 伺服器 2016](https://technet.microsoft.com/library/cc261992%28v=office.16%29.aspx)的最佳作法檔都存在於升級中。</span><span class="sxs-lookup"><span data-stu-id="a6121-141">Best practices documents for upgrade exist for [Microsoft Office SharePoint Server 2007](https://technet.microsoft.com/library/cc261992%28v=office.12%29.aspx), [SharePoint Server 2010](https://technet.microsoft.com/library/cc261992%28v=office.14%29.aspx), [SharePoint Server 2013](https://technet.microsoft.com/library/cc261992%28v=office.15%29.aspx), and [SharePoint Server 2016](https://technet.microsoft.com/library/cc261992%28v=office.16%29.aspx).</span></span> <span data-ttu-id="a6121-142">您也可以搜尋使用升級或 Microsoft 365 遷移經驗的 [Microsoft 合作夥伴](https://partnercenter.microsoft.com/pcv/search) 。</span><span class="sxs-lookup"><span data-stu-id="a6121-142">You can also search for [Microsoft Partners](https://partnercenter.microsoft.com/pcv/search) who have experience with upgrades or Microsoft 365 migrations.</span></span> 
  
## <a name="make-your-plan"></a><span data-ttu-id="a6121-143">制定計畫</span><span class="sxs-lookup"><span data-stu-id="a6121-143">Make your plan</span></span>

<span data-ttu-id="a6121-144">如果您需要升級，您需要一個計畫，而且在這些情況下，一個大小不會全部容納。</span><span class="sxs-lookup"><span data-stu-id="a6121-144">If you need to upgrade, you need a plan, and one-size doesn't fit all in these cases.</span></span> <span data-ttu-id="a6121-145">您的計畫可能非常簡單，只是「使用 SharePoint Online 建立 Microsoft 365 訂閱，註冊網域，然後重新導向人員，將檔案儲存在這裡」。</span><span class="sxs-lookup"><span data-stu-id="a6121-145">Your plan may be as simple as 'Create a Microsoft 365 subscription with SharePoint Online, register a domain, and redirect people to save their files there'.</span></span> <span data-ttu-id="a6121-146">它可能不是。</span><span class="sxs-lookup"><span data-stu-id="a6121-146">And it may not be.</span></span> <span data-ttu-id="a6121-147">這是您所決定的，而是由您和您的使用者實際需要。</span><span class="sxs-lookup"><span data-stu-id="a6121-147">That decision is yours, and it's down to what you and your users really need.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6121-148">在已結束生命週期的軟體上執行時，會有很大的危險。</span><span class="sxs-lookup"><span data-stu-id="a6121-148">It's risky to run on software whose lifecycle has ended.</span></span> <span data-ttu-id="a6121-149">當發現問題時，已不支援的產品不再有修補。</span><span class="sxs-lookup"><span data-stu-id="a6121-149">Products that are out of support are no longer patched when issues are found.</span></span> <span data-ttu-id="a6121-150">這也表示如果發生新的安全性威脅，將不會有安全性修補程式或修復程式，因為已不再支援生命週期結束產品。</span><span class="sxs-lookup"><span data-stu-id="a6121-150">This also means that if new security threats arise, there will be no security patches or fixes because the end-of-lifecycle products are no longer supported.</span></span> <span data-ttu-id="a6121-151">請避免這種狀況！</span><span class="sxs-lookup"><span data-stu-id="a6121-151">Please avoid that situation!</span></span> 
  
### <a name="first-know-your-farm"></a><span data-ttu-id="a6121-152">首先，知道您的伺服器陣列</span><span class="sxs-lookup"><span data-stu-id="a6121-152">First, know your farm</span></span>

<span data-ttu-id="a6121-153">升級時，您的決策應根據伺服器陣列對您的組織所執行的動作而定。</span><span class="sxs-lookup"><span data-stu-id="a6121-153">When upgrading, your decision-making should be based on what your farm does for your organization.</span></span> <span data-ttu-id="a6121-154">它會滿足什麼需求？</span><span class="sxs-lookup"><span data-stu-id="a6121-154">What need does it satisfy?</span></span> <span data-ttu-id="a6121-155">其角色為何？</span><span class="sxs-lookup"><span data-stu-id="a6121-155">What's its role?</span></span> <span data-ttu-id="a6121-156">您公司中的每個伺服器陣列都有不同的角色。</span><span class="sxs-lookup"><span data-stu-id="a6121-156">Each farm in your company may have a different role.</span></span> <span data-ttu-id="a6121-157">您的部分 SharePoint 伺服器陣列可能很  *重要*  ，有些則可能是檔案封存--在安全維護中。</span><span class="sxs-lookup"><span data-stu-id="a6121-157">Some of your SharePoint farms may be  *critical*  , some may be file archives -- there for safe-keeping.</span></span> <span data-ttu-id="a6121-158">或者，如果您的伺服器陣列同時填滿許多角色，您可能需要知道哪些網站集合、網站或文件庫皆有，任何自訂專案，以及其重要性。</span><span class="sxs-lookup"><span data-stu-id="a6121-158">Or, if your farm fills many roles at once, then you may need to know what site collections, webs, or even document libraries do, any customizations, and how important they are.</span></span> <span data-ttu-id="a6121-159">在此層級分析您的資料似乎很多，但在升級或遷移之前，它會節約您的網域的時間和精力。</span><span class="sxs-lookup"><span data-stu-id="a6121-159">Analyzing your data at this level may seem like a lot of work, but it saves time and effort to master your domain before you upgrade, or migrate, it.</span></span> <span data-ttu-id="a6121-160">一旦您知道所有移動的部分，以及最重要的位數之後，您也會知道您已 outgrown 及可以留下什麼。</span><span class="sxs-lookup"><span data-stu-id="a6121-160">Once you know all the moving parts, and the most important bits, you'll also know what you've outgrown and can leave behind.</span></span> <span data-ttu-id="a6121-161">這項知識只會對您的未來帶來益處。</span><span class="sxs-lookup"><span data-stu-id="a6121-161">That knowledge will only benefit you going forward.</span></span> 
  
<span data-ttu-id="a6121-162">那麼，使用者怎麼說對您的 SharePoint 伺服器陣列而言最為重要？</span><span class="sxs-lookup"><span data-stu-id="a6121-162">So, what are users saying is most important about your SharePoint Server farm?</span></span>
  
- <span data-ttu-id="a6121-163">內建的 SharePoint 功能</span><span class="sxs-lookup"><span data-stu-id="a6121-163">Built-in SharePoint features</span></span>
    
- <span data-ttu-id="a6121-164">大型資料主體 (例如檔案的封存) </span><span class="sxs-lookup"><span data-stu-id="a6121-164">The large data corpus (such as an archive of files)</span></span>
    
- <span data-ttu-id="a6121-165">可用性</span><span class="sxs-lookup"><span data-stu-id="a6121-165">Availability</span></span>
    
- <span data-ttu-id="a6121-166">伺服器陣列中的重要應用程式、網頁元件或檔 (任務重要的伺服器陣列) </span><span class="sxs-lookup"><span data-stu-id="a6121-166">Critical apps, web parts, or docs in the farm (Mission critical farm)</span></span>
    
- <span data-ttu-id="a6121-167">符合規範標準</span><span class="sxs-lookup"><span data-stu-id="a6121-167">The Compliance standards met</span></span>
    
- <span data-ttu-id="a6121-168">自訂</span><span class="sxs-lookup"><span data-stu-id="a6121-168">Customizations</span></span>
    
<span data-ttu-id="a6121-169">如果您對您的 SharePoint 伺服器陣列執行一些重要的動作，請說其作用像是有關用戶端服務需求重要資料的大型目錄，您可以在「重要應用程式」旁進行勾選標記，也可以將它放在「可用性」旁，但如果您無法使用 SharePoint 一段時間，您的業務就會受到影響。</span><span class="sxs-lookup"><span data-stu-id="a6121-169">If you run something essential to your business from your SharePoint farm, say it acts like a large catalog of critical data about client service requirements, you may put a tick beside 'Critical apps', but also 'Availability' -- that is, your business would be impacted if you couldn't use SharePoint for a while.</span></span> <span data-ttu-id="a6121-170">同樣地，您也可以檢查「自訂」，因為您伺服器陣列所提供的重要服務是以自訂程式碼、網站定義或多個共同作業的自訂專案為基礎。</span><span class="sxs-lookup"><span data-stu-id="a6121-170">Likewise, you might check 'Customizations' because the critical services your farm offers are based on custom code, site definitions, or a number of customizations that work together.</span></span>
  
<span data-ttu-id="a6121-171">如果 SharePoint 符合這些需求，而不需要在使用軟體的內建功能之外的任何地方執行任何作業，而且您一般會更新它並執行正常的管理與維護 SharePoint，也就是您在舊版本的 SharePoint 中所做的原因。</span><span class="sxs-lookup"><span data-stu-id="a6121-171">If SharePoint met those needs without your having to do anything outside of using what's built-in to the software, and you generally update it and carry out normal administration and maintenance, you may have chosen 'Built-in SharePoint' -- this may also be your reason for sitting on an older version of SharePoint.</span></span> <span data-ttu-id="a6121-172">換句話說，它已經做了您所需的動作，而且您現在還沒有必要升級，Microsoft Office SharePoint Server 2007 已結束支援。</span><span class="sxs-lookup"><span data-stu-id="a6121-172">In other words, it already does what you need it to and you haven't needed to upgrade until now, at Microsoft Office SharePoint Server 2007 end of support.</span></span>
  
<span data-ttu-id="a6121-173">當您在專案中列出這些專案時，您會建立升級的準則。</span><span class="sxs-lookup"><span data-stu-id="a6121-173">When you bullet-list these things, you create criteria for your upgrade.</span></span> <span data-ttu-id="a6121-174">換句話說，任何升級都會必須符合此條碼才能考慮。</span><span class="sxs-lookup"><span data-stu-id="a6121-174">In other words, any upgrade would have to meet this bar to be considered.</span></span> <span data-ttu-id="a6121-175">這為您提供一種方法，讓您可以排除目前不符合您需求的方法。</span><span class="sxs-lookup"><span data-stu-id="a6121-175">This gives you a way to rule out methods that don't currently fit your needs.</span></span>
  
### <a name="a-simple-sample-plan"></a><span data-ttu-id="a6121-176">簡單的範例計畫</span><span class="sxs-lookup"><span data-stu-id="a6121-176">A simple sample plan</span></span>

<span data-ttu-id="a6121-177">您可能需要在您的 SharePoint 升級所需的路徑上，與領導和其他系統管理員達成共識。</span><span class="sxs-lookup"><span data-stu-id="a6121-177">There may need to be wider consensus with leadership and other admins on the path your SharePoint Upgrade will take.</span></span> <span data-ttu-id="a6121-178">SharePoint 伺服器管理員通常會與 Microsoft SQL Server 系統管理員合作、與網路及安全性小組合作等等。</span><span class="sxs-lookup"><span data-stu-id="a6121-178">SharePoint Server Administrators often cooperate with Microsoft SQL Server admins, work with Networking and Security teams, and more.</span></span> <span data-ttu-id="a6121-179">在有許多專案關係人的情況下，您可能需要建立或調整升級和遷移計畫的合約。</span><span class="sxs-lookup"><span data-stu-id="a6121-179">Where there are a lot of stakeholders, you may need to build agreement for, or adjust, your upgrade and migration plan.</span></span> <span data-ttu-id="a6121-180">例如，如果您遷移資料，讓部分公司在 Microsoft 365 中使用 SharePoint 線上，則在您的網路內可能需要進行效能調整或測試。</span><span class="sxs-lookup"><span data-stu-id="a6121-180">For example, if you migrate data so that part of your company uses SharePoint Online in Microsoft 365, there will likely need to be performance tuning or testing inside your network.</span></span> <span data-ttu-id="a6121-181">受影響的小組應提前通知。</span><span class="sxs-lookup"><span data-stu-id="a6121-181">Affected teams should be informed ahead of time.</span></span>
  
<span data-ttu-id="a6121-182">在我的簡易範例中，我會顯示 SharePoint 管理員的提案，然後列出所有已商定的利益關係人的計畫。</span><span class="sxs-lookup"><span data-stu-id="a6121-182">In my simple sample, I show a SharePoint administrator's proposal and then list out the plan that all the stakeholders agreed upon.</span></span> <span data-ttu-id="a6121-183">為了清楚起見，請記錄您的協定和決策。</span><span class="sxs-lookup"><span data-stu-id="a6121-183">For clarity, document your agreements and decisions.</span></span>
  
<span data-ttu-id="a6121-184">方案會在深入分析伺服器陣列後開始，並嘗試識別伺服器陣列的角色、痛點及其他重要資訊，這些資訊會導致縮小某些升級選項。</span><span class="sxs-lookup"><span data-stu-id="a6121-184">The plan starts after an in-depth analysis of a farm, and tries to identify the role of the farm, pain points, and other important information that will lead to narrowing down some upgrade options.</span></span> <span data-ttu-id="a6121-185">之後，SharePoint 系統管理員所進行的升級提案，以及專案關係人同意行動計畫。</span><span class="sxs-lookup"><span data-stu-id="a6121-185">Afterward, an upgrade proposal is made by SharePoint administrator, and stakeholders agree on an action plan.</span></span>
  
<span data-ttu-id="a6121-186">我的 ' 最重要」專案符號清單：</span><span class="sxs-lookup"><span data-stu-id="a6121-186">My 'most important' bullet list:</span></span>
  
- <span data-ttu-id="a6121-187">可供 SharePoint 內建的可用性、功能，以及符合性標準。</span><span class="sxs-lookup"><span data-stu-id="a6121-187">Availability, features built-in to SharePoint, and Compliance standards.</span></span>
    
- <span data-ttu-id="a6121-188">大部分的資料都是在三個網站集合上，開發人員小組使用一種會議工作區尤為重要，且在全球範圍內大量使用。</span><span class="sxs-lookup"><span data-stu-id="a6121-188">Most of the data is on three site collections, with one Meeting Workspace used by a Dev team particularly important and in heavy use in multiple time-zones worldwide.</span></span>
    
- <span data-ttu-id="a6121-189">有17個其他廣泛使用的網站。</span><span class="sxs-lookup"><span data-stu-id="a6121-189">There are seventeen other sites that are widely used.</span></span>
    
- <span data-ttu-id="a6121-190">兩個文件庫 (根網站集合上的會議工作區和檔，) 每個) 的 (超過8000個檔的最大。</span><span class="sxs-lookup"><span data-stu-id="a6121-190">Two document libraries (Meeting Workspace and Documents on the root site collection) are largest (over 8000 docs each).</span></span> <span data-ttu-id="a6121-191">我們有大量的封存檔和清單包含試算表附件。</span><span class="sxs-lookup"><span data-stu-id="a6121-191">We have a large number of archived docs and list with spreadsheet attachments.</span></span>
    
- <span data-ttu-id="a6121-192">有十四個文件庫的清單，其具有必須符合規範的敏感性資料。</span><span class="sxs-lookup"><span data-stu-id="a6121-192">There are fourteen lists of libraries that have sensitive data that MUST stay in Compliance.</span></span>
    
- <span data-ttu-id="a6121-193">我們必須能夠在任何位置執行保留和電子探索。</span><span class="sxs-lookup"><span data-stu-id="a6121-193">We MUST have the ability to do holds and e-discovery wherever we go.</span></span>
    
- <span data-ttu-id="a6121-194">由於 InfoSec 規則，此資料中的部分資料必須保持內部部署。</span><span class="sxs-lookup"><span data-stu-id="a6121-194">Some of this data MUST stay on-premises, due to InfoSec rules.</span></span>
    
 <span data-ttu-id="a6121-195">**我的升級和遷移選擇：**</span><span class="sxs-lookup"><span data-stu-id="a6121-195">**My upgrade and migration choices:**</span></span>
  
| <span data-ttu-id="a6121-196">是</span><span class="sxs-lookup"><span data-stu-id="a6121-196">Yes</span></span> | <span data-ttu-id="a6121-197">否</span><span class="sxs-lookup"><span data-stu-id="a6121-197">No</span></span> |
|:-----|:-----|
|<span data-ttu-id="a6121-198">使用資料庫附加升級資料庫</span><span class="sxs-lookup"><span data-stu-id="a6121-198">Upgrade databases with database attach</span></span>  <br/> |<span data-ttu-id="a6121-199">就地升級 </span><span class="sxs-lookup"><span data-stu-id="a6121-199">In-place upgrade</span></span>  <br/> |
|<span data-ttu-id="a6121-200">以並行方式升級伺服器陣列</span><span class="sxs-lookup"><span data-stu-id="a6121-200">Upgrade with farms side-by-side</span></span>  <br/> |<span data-ttu-id="a6121-201">混合式升級</span><span class="sxs-lookup"><span data-stu-id="a6121-201">Hybrid Upgrade</span></span>  <br/> |
|<span data-ttu-id="a6121-202">用於個人網站資料) Microsoft 365 (中的遷移 API SPO</span><span class="sxs-lookup"><span data-stu-id="a6121-202">Migration API to SPO in Microsoft 365 (for personal site data)</span></span>  <br/> |<span data-ttu-id="a6121-203">尚不需要 SharePoint 混合 () </span><span class="sxs-lookup"><span data-stu-id="a6121-203">SharePoint Hybrid (not needed yet)</span></span>  <br/> |
|<span data-ttu-id="a6121-204">某些手動資料移轉至 SharePoint 線上以進行重要資料</span><span class="sxs-lookup"><span data-stu-id="a6121-204">Some manual data migrations to SharePoint Online for critical data</span></span>  <br/> |<span data-ttu-id="a6121-205">升級至 Microsoft 365 的 FastTrack 嚮導</span><span class="sxs-lookup"><span data-stu-id="a6121-205">FastTrack wizard upgrade to Microsoft 365</span></span>  <br/> |
   
 <span data-ttu-id="a6121-206">**建議的計畫：**</span><span class="sxs-lookup"><span data-stu-id="a6121-206">**My proposed plan:**</span></span>
  
<span data-ttu-id="a6121-207">在內部部署環境中，使用 SharePoint 並行的版本，以進行虛擬化，讓我們能夠先升級資料庫。</span><span class="sxs-lookup"><span data-stu-id="a6121-207">Upgrade on-premises, with versions of SharePoint side-by-side, some virtualized, so that we can upgrade the databases first.</span></span> <span data-ttu-id="a6121-208">從 SharePoint 2007 至 SharePoint 2010。</span><span class="sxs-lookup"><span data-stu-id="a6121-208">Go from SharePoint 2007 to SharePoint 2010.</span></span> <span data-ttu-id="a6121-209">系統管理員和 Devs 測試所產生的伺服器陣列。</span><span class="sxs-lookup"><span data-stu-id="a6121-209">Admins and Devs test the resulting farm.</span></span> <span data-ttu-id="a6121-210">使用者測試產生的伺服器陣列。</span><span class="sxs-lookup"><span data-stu-id="a6121-210">Users test the resulting farm.</span></span> <span data-ttu-id="a6121-211">修正這段時間內的任何顯示-停止問題。</span><span class="sxs-lookup"><span data-stu-id="a6121-211">Fix any show-stopping issues during this time.</span></span> <span data-ttu-id="a6121-212">再一次，並排將 SharePoint 2010 資料庫升級為 SharePoint 2013。</span><span class="sxs-lookup"><span data-stu-id="a6121-212">Again, side-by-side, upgrade SharePoint 2010 databases to SharePoint 2013.</span></span> <span data-ttu-id="a6121-213">測試。</span><span class="sxs-lookup"><span data-stu-id="a6121-213">Test.</span></span> <span data-ttu-id="a6121-214">使用者測試/試驗。</span><span class="sxs-lookup"><span data-stu-id="a6121-214">User test/pilot.</span></span> <span data-ttu-id="a6121-215">修正這段時間內的任何顯示-停止問題。</span><span class="sxs-lookup"><span data-stu-id="a6121-215">Fix any show-stopping issues during this time.</span></span>
  
- <span data-ttu-id="a6121-216">如果與 SPO 混合使用的搜尋同盟符合您的需求，請考慮。</span><span class="sxs-lookup"><span data-stu-id="a6121-216">Consider if a Search Federated Hybrid with SPO meets your needs.</span></span>
    
- <span data-ttu-id="a6121-217">如果您想要從這裡升級至 SharePoint 線上，請考慮 [FastTrack 協助](https://fasttrack.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="a6121-217">Consider [FastTrack assistance](https://fasttrack.microsoft.com) if you would like to upgrade to SharePoint Online from here.</span></span> 
    
- <span data-ttu-id="a6121-218">決定是否可將任何網站集合卸載至 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="a6121-218">Determine if any site collections can be offloaded to a Microsoft 365 Subscription.</span></span> <span data-ttu-id="a6121-219"> (Microsoft 365 符合許多 [規範標準](https://technet.microsoft.com/library/office-365-compliance.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a6121-219">(Microsoft 365 meets many [Compliance standards](https://technet.microsoft.com/library/office-365-compliance.aspx).</span></span> <span data-ttu-id="a6121-220">Microsoft 365 具有 [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) ，可透過規範中心進行 [封存](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) 。 ) </span><span class="sxs-lookup"><span data-stu-id="a6121-220">Microsoft 365 has [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) and can do [Holds](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) through the Compliance Centre.)</span></span> 
    
<span data-ttu-id="a6121-221">否則，繼續執行 SharePoint Server 2016 的並列升級。</span><span class="sxs-lookup"><span data-stu-id="a6121-221">Otherwise, continue with a side-by-side upgrade to SharePoint Server 2016.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6121-222">在規劃升級的系統管理員和實際的程式之間的建議各項間，是由升級所依賴的其他專案關係人所進行的交談。</span><span class="sxs-lookup"><span data-stu-id="a6121-222">In between recommendations made by the administrators planning the upgrade and the actual process are the conversations that happen with other stakeholders on which the upgrade relies.</span></span> <span data-ttu-id="a6121-223">例如，有時候，經濟效益會強制管理員變更其計畫。</span><span class="sxs-lookup"><span data-stu-id="a6121-223">For example, sometimes economics force administrators to change their plans.</span></span> <span data-ttu-id="a6121-224">不論是哪一種最終決定，您都應該記錄商定的計畫是什麼。</span><span class="sxs-lookup"><span data-stu-id="a6121-224">Whatever the final decision is, you should document what the agreed-upon plan is, going forward.</span></span> <span data-ttu-id="a6121-225">其外觀可能類似如下：</span><span class="sxs-lookup"><span data-stu-id="a6121-225">It might look something like this:</span></span> 
  
 <span data-ttu-id="a6121-226">**我的行動方案：**</span><span class="sxs-lookup"><span data-stu-id="a6121-226">**My action plan:**</span></span>
  
<span data-ttu-id="a6121-227">在內部部署中，我們使用虛擬環境建立預設的 SharePoint Server 2010 和2013。</span><span class="sxs-lookup"><span data-stu-id="a6121-227">On-premises, we use a virtual environment to build default SharePoint Server 2010, and 2013.</span></span> <span data-ttu-id="a6121-228">SharePoint Server 2016 將建立在符合2016系統需求的新硬體上。</span><span class="sxs-lookup"><span data-stu-id="a6121-228">SharePoint Server 2016 will be built on new hardware that meets system requirements for 2016.</span></span> <span data-ttu-id="a6121-229">若要將資料庫附加到從 SharePoint 2007 到其所有版本之間的更新，並 SharePoint 伺服器2016，我們將執行資料庫。</span><span class="sxs-lookup"><span data-stu-id="a6121-229">We will do database attaches to upgrade databases from SharePoint 2007 through all versions between it and SharePoint Server 2016.</span></span> <span data-ttu-id="a6121-230">若原生功能尚未符合我們的需求，請在 SharePoint Server 2016 環境中重新建立及測試核心自訂。</span><span class="sxs-lookup"><span data-stu-id="a6121-230">Core customizations are being recreated for and tested in the SharePoint Server 2016 environment at this time, if native features don't already meet our needs.</span></span> <span data-ttu-id="a6121-231">如果取得成功，我們會在新的硬體上使用已升級的資料庫和較少的自訂專案，進行內部部署伺服器陣列。</span><span class="sxs-lookup"><span data-stu-id="a6121-231">If we are successful, we will have an on-premises farm on new hardware with upgraded databases, and fewer customizations.</span></span> <span data-ttu-id="a6121-232">我們會將已升級的內容資料庫附加至新的網站集合，SharePoint Server 2013、test、user test/試驗，然後再將 DNS 切回到新的 SharePoint 伺服器2016環境以供即時使用。</span><span class="sxs-lookup"><span data-stu-id="a6121-232">We'll attach the upgraded content databases to new site collections in SharePoint Server 2013, test, user test/pilot, and then do a DNS cut-over to the new SharePoint Server 2016 environment for live use.</span></span>
  
- <span data-ttu-id="a6121-233">我們不會考慮 SharePoint Server 2016 之間的同盟混合，也不會立即 SharePoint 線上。</span><span class="sxs-lookup"><span data-stu-id="a6121-233">We will not consider Federated Hybrid between SharePoint Server 2016 and SharePoint Online right now.</span></span>
    
- <span data-ttu-id="a6121-234">我們的網站預估35% 可使用虛名網域轉變為新的 SPO 網站，或最終成為商務儲存的 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="a6121-234">An estimated 35% of our sites can be turned into new SPO sites with vanity domains, or, ultimately, become OneDrive for Business storage.</span></span> <span data-ttu-id="a6121-235">尋找其他機會來轉換網站，或將新網站路由傳送至 SPO。</span><span class="sxs-lookup"><span data-stu-id="a6121-235">Looking for other opportunities to convert sites, or route new sites to SPO.</span></span>
    
- <span data-ttu-id="a6121-236">這部分的部分遷移是手動進行的，將其拖曳至商務個人網站的 OneDrive，有些則是透過遷移 API。</span><span class="sxs-lookup"><span data-stu-id="a6121-236">Some of this part of the migration will be manual, by drag-and-drop to OneDrive for Business personal sites, and some by migration API.</span></span>
    
<span data-ttu-id="a6121-237">更詳細的步驟，或特定升級方向的連結數目應遵循計畫。</span><span class="sxs-lookup"><span data-stu-id="a6121-237">More detailed steps, or a number of links to specific upgrade directions should follow a plan.</span></span> <span data-ttu-id="a6121-238">MOSS 2007 電腦不應解除委任，為了進行比較，應維護虛擬環境;不過，當使用者重新導向至 SharePoint Server 2016 時，將會完成升級。</span><span class="sxs-lookup"><span data-stu-id="a6121-238">The MOSS 2007 computer should not be decommissioned, and virtual environments should be maintained for the sake of comparison; however, the upgrade will be complete when users are redirected to SharePoint Server 2016.</span></span>
  
<span data-ttu-id="a6121-239">選擇方法的主要因素是升級的總成本和時間成本 (您會在 SharePoint 遷移藍圖文章) 中深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="a6121-239">Often major factors in choosing a method are the total cost of the upgrade and the cost in time (you'll see more on this in the SharePoint Migration Roadmap article).</span></span> <span data-ttu-id="a6121-240">不過，事先規劃可讓您極大的好處是設定期望、明智的選擇，以及將成功的方式呈現成一組幀。</span><span class="sxs-lookup"><span data-stu-id="a6121-240">However, planning ahead will benefit you greatly in setting expectations, choosing wisely, and framing what success will look like.</span></span>
  
## <a name="related-links"></a><span data-ttu-id="a6121-241">相關連結</span><span class="sxs-lookup"><span data-stu-id="a6121-241">Related links</span></span>

[<span data-ttu-id="a6121-242">協助您從 Office 2007 伺服器及用戶端升級的資源</span><span class="sxs-lookup"><span data-stu-id="a6121-242">Resources to help you upgrade from Office 2007 servers and clients</span></span>](upgrade-from-office-2007-servers-and-products.md)
  
[<span data-ttu-id="a6121-243">Microsoft 生命週期原則及生命週期搜尋</span><span class="sxs-lookup"><span data-stu-id="a6121-243">Microsoft Lifecycle Policy and Lifecycle search</span></span>](https://support.microsoft.com/lifecycle)
  
[<span data-ttu-id="a6121-244">搜尋可協助升級或遷移的 Microsoft 合作夥伴</span><span class="sxs-lookup"><span data-stu-id="a6121-244">Search for Microsoft Partners who can help with upgrade or migration</span></span>](https://partnercenter.microsoft.com/pcv/search)
  

