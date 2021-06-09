---
title: 將非 custodial 資料來源新增至 Advanced eDiscovery 案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 您可以將非 custodial 資料來源新增至 Advanced eDiscovery 案例，並在資料來源上保留。 非 custodial 的資料來源是重新編制索引的，所以標示為已部分索引的任何內容都會重新處理，使其完全和快速可供搜尋。
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740350"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="b78b8-104">將非 custodial 資料來源新增至 Advanced eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="b78b8-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="b78b8-105">在 Advanced eDiscovery 案例中，它不一定會符合您在案例中將 Microsoft 365 資料來源與系統管理員相關聯的需求。</span><span class="sxs-lookup"><span data-stu-id="b78b8-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="b78b8-106">不過，您可能還需要將該資料與案例產生關聯，以便進行搜尋、將其新增至審閱集合，以及加以分析和審閱。</span><span class="sxs-lookup"><span data-stu-id="b78b8-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="b78b8-107">Advanced eDiscovery 中的功能稱為「*非 custodial 資料來源*」，可讓您將資料新增至案例，而不需將其關聯至保管人。</span><span class="sxs-lookup"><span data-stu-id="b78b8-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="b78b8-108">它也會將相同的 Advanced eDiscovery 功能套用至可用於與保管人相關聯之資料的非 custodial 資料。</span><span class="sxs-lookup"><span data-stu-id="b78b8-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="b78b8-109">您可以套用至非 custodial 資料的兩個最實用專案是保留，並使用 [高級索引](indexing-custodian-data.md)進行處理。</span><span class="sxs-lookup"><span data-stu-id="b78b8-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="b78b8-110">新增非 custodial 的資料來源</span><span class="sxs-lookup"><span data-stu-id="b78b8-110">Add a non-custodial data source</span></span>

<span data-ttu-id="b78b8-111">請遵循下列步驟，在 Advanced eDiscovery 案例中新增及管理非 custodial 的資料來源。</span><span class="sxs-lookup"><span data-stu-id="b78b8-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="b78b8-112">在 [ **Advanced eDiscovery** ] 首頁上，按一下您要新增資料的案例。</span><span class="sxs-lookup"><span data-stu-id="b78b8-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="b78b8-113">按一下 [**資料來源**] 索引標籤，然後按一下 [**新增資料來源**  >  **新增資料位置**]。</span><span class="sxs-lookup"><span data-stu-id="b78b8-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="b78b8-114">在 [ **新增非 custodial 資料位置** ] 飛入頁面上，選擇您想要新增至案例的資料來源。</span><span class="sxs-lookup"><span data-stu-id="b78b8-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="b78b8-115">您可以展開 **SharePoint** 或 **Exchange** 區段，然後按一下 [**編輯**]，以新增多個信箱和網站。</span><span class="sxs-lookup"><span data-stu-id="b78b8-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![將 SharePoint 網站和 Exchange 信箱新增為非 custodial 資料來源](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="b78b8-117">**SharePoint** -按一下 [**編輯**] 以新增網站。</span><span class="sxs-lookup"><span data-stu-id="b78b8-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="b78b8-118">選取清單中的網站，或在搜尋列中輸入網站的 URL，即可搜尋網站。</span><span class="sxs-lookup"><span data-stu-id="b78b8-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="b78b8-119">選取您要新增為非保管人資料來源的網站，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b78b8-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="b78b8-120">**Exchange** -按一下 [**編輯**] 以新增信箱。</span><span class="sxs-lookup"><span data-stu-id="b78b8-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="b78b8-121">在信箱或通訊群組的搜尋方塊中，輸入名稱或別名 (至少三個字元) 。</span><span class="sxs-lookup"><span data-stu-id="b78b8-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="b78b8-122">選取您要新增為非保管人資料來源的信箱，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b78b8-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b78b8-123">您可以使用 **SharePoint** 和 **Exchange** 區段，將與小組或 Yammer 群組相關聯的網站和信箱新增為非 custodial 資料來源。</span><span class="sxs-lookup"><span data-stu-id="b78b8-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="b78b8-124">您必須另外新增與小組或 Yammer 群組相關聯的信箱與網站。</span><span class="sxs-lookup"><span data-stu-id="b78b8-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="b78b8-125">在您新增非 custodial 資料來源之後，您可以選擇將這些位置置於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="b78b8-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="b78b8-126">選取或取消選取資料來源旁的 [ **保留** ] 核取方塊，以置於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="b78b8-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="b78b8-127">在 [**新增非 custodial 資料位置**] 彈出頁面的底部 **，按一下 [** 新增]，將資料來源新增至案例。</span><span class="sxs-lookup"><span data-stu-id="b78b8-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="b78b8-128">您新增的每個非 custodial 資料來源都會列在 [ **資料來源** ] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="b78b8-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="b78b8-129">非 custodial 資料來源是由 [**來源類型**] 欄中的 [**資料位置**] 值所識別。</span><span class="sxs-lookup"><span data-stu-id="b78b8-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![[資料來源] 索引標籤上的非 custodial 資料來源](../media/NonCustodialDataSources2.png)

<span data-ttu-id="b78b8-131">在將非 custodial 資料來源新增至案例之後，會建立名為 *索引標籤非 custodial 資料* 的作業，並顯示在案例的 [ **工作** ] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="b78b8-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="b78b8-132">在建立工作之後，起始的高級索引處理常式和資料來源都會重新編制索引。</span><span class="sxs-lookup"><span data-stu-id="b78b8-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="b78b8-133">管理非 custodial 資料來源的保留</span><span class="sxs-lookup"><span data-stu-id="b78b8-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="b78b8-134">在非 custodial 資料來源上進行保留後，會自動建立包含案例的非 custodial 資料來源的保留原則。</span><span class="sxs-lookup"><span data-stu-id="b78b8-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="b78b8-135">當您將其他非 custodial 資料來源置於保留狀態時，會將它們新增至此保留原則。</span><span class="sxs-lookup"><span data-stu-id="b78b8-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="b78b8-136">開啟 Advanced eDiscovery 案例，然後選取 [**保留**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b78b8-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="b78b8-137">按一下 [ **NCDSHold \<GUID\>**]，其中 GUID 值是唯一的案例。</span><span class="sxs-lookup"><span data-stu-id="b78b8-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="b78b8-138">飛入頁面顯示暫止的非 custodial 資料來源的資訊和統計資料。</span><span class="sxs-lookup"><span data-stu-id="b78b8-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![[非 custodial 資料來源保留] 的飛出頁面會顯示 [統計資料]](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="b78b8-140">按一下 [ **編輯保留** ]，以查看置於保留狀態的非 custodial 資料來源，並執行下列管理工作：</span><span class="sxs-lookup"><span data-stu-id="b78b8-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="b78b8-141">在 [ **位置** ] 頁面上，您可以從保留中移除非 custodial 資料來源，將其解除。</span><span class="sxs-lookup"><span data-stu-id="b78b8-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="b78b8-142">釋放資料來源並不會從案例中移除非 custodial 資料來源。</span><span class="sxs-lookup"><span data-stu-id="b78b8-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="b78b8-143">它只會移除放在資料來源上的保留。</span><span class="sxs-lookup"><span data-stu-id="b78b8-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="b78b8-144">在 [ **查詢** ] 頁面上，您可以編輯 [保留]，以在案例中建立套用至所有 tha 非 custodial 資料來源的查詢型保留。</span><span class="sxs-lookup"><span data-stu-id="b78b8-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
