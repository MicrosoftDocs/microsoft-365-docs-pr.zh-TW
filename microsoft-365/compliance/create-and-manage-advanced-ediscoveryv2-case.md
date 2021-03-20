---
title: 在 Microsoft 365 中建立及管理高級 eDiscovery 案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 本文說明如何建立及管理高級 eDiscovery 案例。 第一步是建立案例，並開始使用 Advanced eDiscovery 的功能和功能。
ms.openlocfilehash: d0f63bca90945c3dfe13b08fa0f1d139da8a9189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908359"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a><span data-ttu-id="7a07a-104">建立及管理高級 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="7a07a-104">Create and manage an Advanced eDiscovery case</span></span>

<span data-ttu-id="7a07a-105">在將管理案例的組織中設定高級 eDiscovery 並 [指派對 ediscovery 管理員的許可權](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) 之後，下一步是建立並管理案例。</span><span class="sxs-lookup"><span data-stu-id="7a07a-105">After setting up Advanced eDiscovery and [assigning permissions to eDiscovery managers](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) in your organization that will manage cases, the next step is to create and manage a case.</span></span>

<span data-ttu-id="7a07a-106">本文也提供使用案例來管理法律案例或其他調查類型的高級 eDiscovery 工作流程的高層次概述。</span><span class="sxs-lookup"><span data-stu-id="7a07a-106">This article also provides a high-level overview of using cases to manage the Advanced eDiscovery workflow for a legal case or other types of investigations.</span></span>

## <a name="create-a-case"></a><span data-ttu-id="7a07a-107">建立案例</span><span class="sxs-lookup"><span data-stu-id="7a07a-107">Create a case</span></span>

<span data-ttu-id="7a07a-108">完成下列步驟以建立案例並新增成員。</span><span class="sxs-lookup"><span data-stu-id="7a07a-108">Complete the following steps to create a case and add members.</span></span> <span data-ttu-id="7a07a-109">建立案例的使用者會自動新增為成員。</span><span class="sxs-lookup"><span data-stu-id="7a07a-109">The user who creates the case is automatically added as a member.</span></span> <span data-ttu-id="7a07a-110">案例的成員可以存取 Microsoft 365 規範中心內的案例，以及執行高級 eDiscovery 任務。</span><span class="sxs-lookup"><span data-stu-id="7a07a-110">Members of the case can access the case in the Microsoft 365 compliance center and perform Advanced eDiscovery tasks.</span></span>

1. <span data-ttu-id="7a07a-111">移至 <https://compliance.microsoft.com> 並使用已獲指派 eDiscovery 許可權之使用者帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="7a07a-111">Go to <https://compliance.microsoft.com> and sign in using the credentials for user account that has been assigned eDiscovery permissions.</span></span> <span data-ttu-id="7a07a-112">組織管理角色群組的成員也可以建立高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="7a07a-112">Members of the Organization Management role group can also create Advanced eDiscovery cases.</span></span>

2. <span data-ttu-id="7a07a-113">在 Microsoft 365 規範中心的左功能窗格中，按一下 [ **全部顯示**]，然後按一下 [ **eDiscovery > Advanced**]。</span><span class="sxs-lookup"><span data-stu-id="7a07a-113">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

3. <span data-ttu-id="7a07a-114">在 [ **高級 eDiscovery** ] 頁面上，按一下 [ **案例** ] 索引標籤，然後按一下 [ **建立案例**]。</span><span class="sxs-lookup"><span data-stu-id="7a07a-114">On the **Advanced eDiscovery** page, click the **Cases** tab, and then click **Create a case**.</span></span>

4. <span data-ttu-id="7a07a-115">在 [ **新 eDiscovery 案例** 飛出] 頁面上，為案例輸入 (必要) 的名稱，然後輸入選用的案例編號及描述。</span><span class="sxs-lookup"><span data-stu-id="7a07a-115">On the **New eDiscovery case** flyout page, give the case a name (required), and then type an optional case number and description.</span></span> <span data-ttu-id="7a07a-116">案例名稱在您的組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7a07a-116">The case name must be unique in your organization.</span></span>

5. <span data-ttu-id="7a07a-117">按一下 [ **儲存** ] 以建立案例。</span><span class="sxs-lookup"><span data-stu-id="7a07a-117">Click **Save** to create the case.</span></span>

   <span data-ttu-id="7a07a-118">會建立新案例，並顯示新案例中的 [ **設定** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7a07a-118">The new case is created and the **Settings** tab in the new case is displayed.</span></span>

6. <span data-ttu-id="7a07a-119">在 [**設定**] 索引標籤上的 [ **Access & 許可權**] 方塊中，按一下 [**選取**]，然後按一下 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="7a07a-119">In the **Access & permissions** tile on the **Settings** tab, click **Select**, and then click **Update**.</span></span>

7. <span data-ttu-id="7a07a-120">按一下 [更新]。</span><span class="sxs-lookup"><span data-stu-id="7a07a-120">Click **Update**.</span></span>

8. <span data-ttu-id="7a07a-121">在 [ **管理此案例** 飛入] 頁面上的 [ **管理成員**] 底下，按一下 [ **新增** ] 以將成員新增至案例。</span><span class="sxs-lookup"><span data-stu-id="7a07a-121">On the **Manage this case** flyout page, under **Manage members**, click **Add** to add members to the case.</span></span>

9. <span data-ttu-id="7a07a-122">在 [人員] 清單中，選取您要新增至案例之人員名稱旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7a07a-122">In the list of people, select the check box next to the names of the people that you want to add to the case.</span></span> <span data-ttu-id="7a07a-123">如先前所述，請確定您加入案例的人員已獲指派適當的 eDiscovery 許可權。</span><span class="sxs-lookup"><span data-stu-id="7a07a-123">As previously explained, be sure that the people you add to the case have been assigned the appropriate eDiscovery permissions.</span></span>

10. <span data-ttu-id="7a07a-124">在您選取要新增為案例成員的人員之後，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="7a07a-124">After you've selected the people to add as members of the case, click **Add**.</span></span>

11. <span data-ttu-id="7a07a-125">在 [ **管理此案例** 飛入] 頁面中，按一下 [ **儲存** ] 儲存新的案例成員清單。</span><span class="sxs-lookup"><span data-stu-id="7a07a-125">In the **Manage this case** flyout page, click **Save** to save the new list of case members.</span></span>

12. <span data-ttu-id="7a07a-126">按一下 [ **首頁** ] 索引標籤，移至案例首頁。</span><span class="sxs-lookup"><span data-stu-id="7a07a-126">Click the **Home** tab to go to the case home page.</span></span>

## <a name="manage-the-workflow"></a><span data-ttu-id="7a07a-127">管理工作流程</span><span class="sxs-lookup"><span data-stu-id="7a07a-127">Manage the workflow</span></span>

<span data-ttu-id="7a07a-128">為了讓您開始使用高級 eDiscovery，這裡是一個與 [一般 ediscovery 作法](advanced-ediscovery-edrm.md)對齊的基本工作流程。</span><span class="sxs-lookup"><span data-stu-id="7a07a-128">To get you started using Advanced eDiscovery, here's a basic workflow that aligns with [common eDiscovery practices](advanced-ediscovery-edrm.md).</span></span> <span data-ttu-id="7a07a-129">在上述每個步驟中，我們也會強調您可以探索的一些擴充的高級 eDiscovery 功能。</span><span class="sxs-lookup"><span data-stu-id="7a07a-129">In each of these steps, we'll also highlight some extended Advanced eDiscovery functionality that you can explore.</span></span>

![高級 eDiscovery 工作流程](../media/AeDWorkflow.png)

1. <span data-ttu-id="7a07a-131">**[將保管人](add-custodians-to-case.md) 和 [非 custodial 資料來源](non-custodial-data-sources.md) 新增至案例**。</span><span class="sxs-lookup"><span data-stu-id="7a07a-131">**[Add custodians](add-custodians-to-case.md) and [non-custodial data sources](non-custodial-data-sources.md) to the case**.</span></span> <span data-ttu-id="7a07a-132">建立案例之後的第一個步驟是新增保管人。</span><span class="sxs-lookup"><span data-stu-id="7a07a-132">The first step after creating a case is to add custodians.</span></span> <span data-ttu-id="7a07a-133">*管理員* 是指具有可能與案例相關之檔或電子檔的系統管理控制權的人員。</span><span class="sxs-lookup"><span data-stu-id="7a07a-133">A *custodian* is a person having administrative control of a document or electronic file that may be relevant to the case.</span></span> <span data-ttu-id="7a07a-134">此外，您也可以新增與特定使用者沒有關聯但可能與案例相關的資料來源。</span><span class="sxs-lookup"><span data-stu-id="7a07a-134">Additionally, you can add data sources that aren't associated with a specific user but may be relevant to the case.</span></span>

   <span data-ttu-id="7a07a-135">以下是一些 (，也就是在您將保管人新增至案例時) 的情況：</span><span class="sxs-lookup"><span data-stu-id="7a07a-135">Here are some things that happen (or that you can do) when you add custodians to a case:</span></span>

   - <span data-ttu-id="7a07a-136">保管人的 Exchange 信箱、OneDrive 帳戶，以及保管人隸屬的任何 Microsoft 團隊或 Yammer 群組中的資料，都可以 "標示" 為案例中的 custodial 資料。</span><span class="sxs-lookup"><span data-stu-id="7a07a-136">Data in the custodian's Exchange mailbox, OneDrive account, and any Microsoft Teams or Yammer groups that the custodian is a member of can be "marked" as custodial data in the case.</span></span>
  
   - <span data-ttu-id="7a07a-137">保管人資料是由稱為「 *高級索引*) 」的程式 (重新編制索引。</span><span class="sxs-lookup"><span data-stu-id="7a07a-137">Custodian data is reindexed (by a process called *Advanced indexing*).</span></span> <span data-ttu-id="7a07a-138">這可協助您在下一個步驟中優化搜尋。</span><span class="sxs-lookup"><span data-stu-id="7a07a-138">This helps optimize searching for it in the next step.</span></span>
  
   - <span data-ttu-id="7a07a-139">您可以對保管人資料進行保留。</span><span class="sxs-lookup"><span data-stu-id="7a07a-139">You can place a hold on custodian data.</span></span> <span data-ttu-id="7a07a-140">這會在調查期間保留與案例相關的資料。</span><span class="sxs-lookup"><span data-stu-id="7a07a-140">This preserves data that may be relevant to the case during the investigation.</span></span>
  
   - <span data-ttu-id="7a07a-141">您可以將其他資料來源與保管人 (產生關聯。例如，您可以將 SharePoint 網站或 Microsoft 365 群組與保管人) 產生關聯，這樣就可以重新編制索引、保留及搜尋此資料，就像是保管人的信箱或 OneDrive 帳戶中的資料一樣。</span><span class="sxs-lookup"><span data-stu-id="7a07a-141">You can associate other data sources with a custodian (for example, you can associate a SharePoint site or Microsoft 365 Group with a custodian) so this data can be reindexed, placed on hold, and searched, just like the data in the custodian's mailbox or OneDrive account.</span></span>

   - <span data-ttu-id="7a07a-142">您可以使用高級 eDiscovery 中的 [通訊工作流程](managing-custodian-communications.md) ，將合法保留通知傳送給保管人。</span><span class="sxs-lookup"><span data-stu-id="7a07a-142">You can use the [communications workflow](managing-custodian-communications.md) in Advanced eDiscovery to send a legal hold notification to custodians.</span></span>

2. <span data-ttu-id="7a07a-143">**[從資料來源收集相關的內容](create-draft-collection.md)**。</span><span class="sxs-lookup"><span data-stu-id="7a07a-143">**[Collect relevant content from data sources](create-draft-collection.md)**.</span></span> <span data-ttu-id="7a07a-144">在您將保管人和非 custodial 資料來源新增至案例後，請使用內建的集合工具，針對可能與案例相關的內容，搜尋這些資料來源。</span><span class="sxs-lookup"><span data-stu-id="7a07a-144">After you add custodians and non-custodial data sources to a case, use the built-in collections tool to search these data sources for content that may be relevant to the case.</span></span> <span data-ttu-id="7a07a-145">您可以使用關鍵字、屬性和條件來 [建立搜尋查詢](building-search-queries.md) ，以利用最可能與案例相關的資料傳回搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="7a07a-145">You use keywords, properties, and conditions to [build search queries](building-search-queries.md) that return search results with the data that's most likely relevant to the case.</span></span> <span data-ttu-id="7a07a-146">您也可以：</span><span class="sxs-lookup"><span data-stu-id="7a07a-146">You can also:</span></span>

   - <span data-ttu-id="7a07a-147">查看 [集合統計資料](collection-statistics-reports.md) ，可協助您精煉集合以縮小結果。</span><span class="sxs-lookup"><span data-stu-id="7a07a-147">View [collection statistics](collection-statistics-reports.md) that may help you refine a collection to narrow the results.</span></span>

   - <span data-ttu-id="7a07a-148">預覽集合的範例，以快速確認是否找到相關資料。</span><span class="sxs-lookup"><span data-stu-id="7a07a-148">Preview a sample of the collection to quickly verify whether the relevant data is being found.</span></span>

   - <span data-ttu-id="7a07a-149">修改查詢，然後重新執行集合。</span><span class="sxs-lookup"><span data-stu-id="7a07a-149">Revise a query and rerun the collection.</span></span>

3. <span data-ttu-id="7a07a-150">**[認可集合的審閱集](commit-draft-collection.md)**。</span><span class="sxs-lookup"><span data-stu-id="7a07a-150">**[Commit collection to a review set](commit-draft-collection.md)**.</span></span> <span data-ttu-id="7a07a-151">當您設定並確認搜尋傳回所需的資料之後，下一步是將搜尋結果新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="7a07a-151">Once you've configured and verified that a search returns the desired data, the next step is to add the search results to a review set.</span></span> <span data-ttu-id="7a07a-152">當您將資料新增至審閱集時，專案會從其原始位置複製到安全的 Azure 存放位置。</span><span class="sxs-lookup"><span data-stu-id="7a07a-152">When you add data to a review set, items are copied from their original location to a secure Azure Storage location.</span></span> <span data-ttu-id="7a07a-153">當審閱及分析審閱集中的專案時，會再次重新編制索引資料，以優化完整和快速的搜尋。</span><span class="sxs-lookup"><span data-stu-id="7a07a-153">The data is reindexed again to optimize it for thorough and fast searches when reviewing and analyzing items in the review set.</span></span> <span data-ttu-id="7a07a-154">此外，您也可以 [將非 Office 365 資料新增至審閱集](load-non-office-365-data-into-a-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="7a07a-154">Additionally, you can also [add non-Office 365 data into a review set](load-non-office-365-data-into-a-review-set.md).</span></span>

   <span data-ttu-id="7a07a-155">此外還有一種特殊的審閱集，您可以將資料新增至（稱為「 *交談複查集*」）。</span><span class="sxs-lookup"><span data-stu-id="7a07a-155">There's also a special kind of review set that you can add data to, called a *conversation review set*.</span></span> <span data-ttu-id="7a07a-156">這兩種審閱集可提供交談重新構建功能，以重新構建、審閱及匯出像是 Microsoft 小組中的對話交談。</span><span class="sxs-lookup"><span data-stu-id="7a07a-156">These types of reviews sets provide conversation reconstruction capabilities to reconstruct, review, and export threaded conversations like those in Microsoft Teams.</span></span> <span data-ttu-id="7a07a-157">如需詳細資訊，請參閱 [在高級 eDiscovery 中查看交談](conversation-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="7a07a-157">For more information, see [Review conversations in Advanced eDiscovery](conversation-review-sets.md).</span></span>

4. <span data-ttu-id="7a07a-158">**檢查及分析審閱集中的資料**。</span><span class="sxs-lookup"><span data-stu-id="7a07a-158">**Review and analyze data in a review set**.</span></span> <span data-ttu-id="7a07a-159">現在，資料是在審校集中，您可以使用各種各樣的工具和功能來查看及分析案例資料，將資料集減至最適合您所調查之案例的目標。</span><span class="sxs-lookup"><span data-stu-id="7a07a-159">Now that data is in a review set, you can use a wide-variety of tools and capabilities to view and analyze the case data with the goal of reducing the data set to what is most relevant to the case you're investigating.</span></span> <span data-ttu-id="7a07a-160">以下是您可以在此程式中使用之部分工具和功能的清單。</span><span class="sxs-lookup"><span data-stu-id="7a07a-160">Here's a list of some tools and capabilities that you can use during this process.</span></span>

   - <span data-ttu-id="7a07a-161">[View documents](view-documents-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="7a07a-161">[View documents](view-documents-in-review-set.md).</span></span> <span data-ttu-id="7a07a-162">這包括針對審閱集中的每一份檔，查看其中繼資料，並以原生版本或文字版本查看該檔。</span><span class="sxs-lookup"><span data-stu-id="7a07a-162">This includes viewing the metadata for each document in a review set, and viewing the document in its native version or text version.</span></span>

   - <span data-ttu-id="7a07a-163">[建立查詢和篩選](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="7a07a-163">[Create queries and filters](review-set-search.md).</span></span> <span data-ttu-id="7a07a-164">您可以使用各種搜尋準則來建立搜尋查詢 (包括可搜尋所有檔案 [中繼資料屬性](document-metadata-fields-in-advanced-ediscovery.md) 的功能) 以進一步精煉及挑選案例資料至與案例最為相關的專案。</span><span class="sxs-lookup"><span data-stu-id="7a07a-164">You create search queries using various search criteria (including the ability to search all [file metadata properties](document-metadata-fields-in-advanced-ediscovery.md)) to further refine and cull the case data to what is most relevant to the case.</span></span> <span data-ttu-id="7a07a-165">您也可以使用 [審閱集合篩選]，將其他條件快速套用至搜尋查詢的結果，以進一步精煉這些結果。</span><span class="sxs-lookup"><span data-stu-id="7a07a-165">You can also use review set filters to quickly apply other conditions to the results of a search query to further refine those results.</span></span> 

   - <span data-ttu-id="7a07a-166">[建立及使用標記](tagging-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="7a07a-166">[Create and use tags](tagging-documents.md).</span></span> <span data-ttu-id="7a07a-167">您可以將標記套用至審閱集合中的檔，以識別哪些回應 (或沒有回應案例) ，然後在建立搜尋查詢以包含或排除已標記的檔時，使用這些標記。</span><span class="sxs-lookup"><span data-stu-id="7a07a-167">You can apply tags to documents in a review set to identify which are responsive (or non-responsive to the case) and then use those tags when creating search queries to include or exclude the tagged documents.</span></span> <span data-ttu-id="7a07a-168">您也可以進行標記，以決定要匯出的檔。</span><span class="sxs-lookup"><span data-stu-id="7a07a-168">You can also tagging to determine which documents to export.</span></span>

   - <span data-ttu-id="7a07a-169">[批註和密文檔](view-documents-in-review-set.md#annotate-view)。</span><span class="sxs-lookup"><span data-stu-id="7a07a-169">[Annotate and redact documents](view-documents-in-review-set.md#annotate-view).</span></span> <span data-ttu-id="7a07a-170">您可以使用審閱中的批註工具，註釋檔，並在檔中以工作產品標記密文內容。</span><span class="sxs-lookup"><span data-stu-id="7a07a-170">You can use the annotation tool in a review to annotate documents and redact content in documents as work product.</span></span> <span data-ttu-id="7a07a-171">我們會在評審時產生 PDF 版本的批註或 redacted 檔，以降低匯出檔的 unredacted 原生版本的風險。</span><span class="sxs-lookup"><span data-stu-id="7a07a-171">We generate a PDF version of an annotated or redacted document during review to reduce the risk of exporting the unredacted native version of the document.</span></span>

   - <span data-ttu-id="7a07a-172">[分析案例資料](analyzing-data-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="7a07a-172">[Analyze case data](analyzing-data-in-review-set.md).</span></span> <span data-ttu-id="7a07a-173">高級 eDiscovery 的分析功能非常強大。</span><span class="sxs-lookup"><span data-stu-id="7a07a-173">The analytics functionality in Advanced eDiscovery is powerful.</span></span> <span data-ttu-id="7a07a-174">在複查集中的資料執行分析之後，我們會執行分析，例如接近重複偵測、電子郵件執行緒和主題，可協助減少您必須查看的檔數量。</span><span class="sxs-lookup"><span data-stu-id="7a07a-174">After you run analytics on the data in review set, we perform analysis such as near duplicate detection, email threading, and themes that can help reduce the volume of documents that you have to review.</span></span> <span data-ttu-id="7a07a-175">我們也會產生分析報告，以匯總執行分析的結果。</span><span class="sxs-lookup"><span data-stu-id="7a07a-175">We also generate an Analytics reports that summarize the result of running analytics.</span></span> <span data-ttu-id="7a07a-176">如先前所述，執行分析也會執行 [律師-用戶端許可權偵測模型](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)。</span><span class="sxs-lookup"><span data-stu-id="7a07a-176">As previously explained, running analytics also runs [the attorney-client privilege detection model](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model).</span></span>

5. <span data-ttu-id="7a07a-177">**匯出及下載案例資料**。</span><span class="sxs-lookup"><span data-stu-id="7a07a-177">**Export and download case data**.</span></span> <span data-ttu-id="7a07a-178">收集、複查及分析案例資料的最後一個步驟是，將其匯出至「高級 eDiscovery」以供外部檢查，或由調查小組以外的人員進行審閱。</span><span class="sxs-lookup"><span data-stu-id="7a07a-178">A final step after collecting, reviewing, and analyzing case data is to export it out of Advanced eDiscovery for external review or for review by people outside of the investigation team.</span></span> <span data-ttu-id="7a07a-179">匯出資料的過程分為兩個步驟。</span><span class="sxs-lookup"><span data-stu-id="7a07a-179">Exporting data is a two-step process.</span></span> <span data-ttu-id="7a07a-180">第一步是將資料 [匯出](export-documents-from-review-set.md) 至審閱集，並將它複製到不同的 Azure 存放位置， (由 Microsoft 提供，或是由組織) 所管理。</span><span class="sxs-lookup"><span data-stu-id="7a07a-180">The first step is to [export](export-documents-from-review-set.md) data out of the review set and copy it to a different Azure Storage location (one provided by Microsoft or one managed by your organization).</span></span> <span data-ttu-id="7a07a-181">然後，您使用 Azure Storage Explorer 將資料 [下載](download-export-jobs.md) 到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="7a07a-181">Then you use Azure Storage Explorer to [download](download-export-jobs.md) the data to a local computer.</span></span> <span data-ttu-id="7a07a-182">除了匯出的資料檔案之外，匯出套件也包含匯出報告、摘要報告及錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="7a07a-182">In addition to the exported data files, the contains of the export package also contains an export report, a summary report, and an error report.</span></span>

## <a name="advanced-ediscovery-architecture"></a><span data-ttu-id="7a07a-183">高級 eDiscovery 架構</span><span class="sxs-lookup"><span data-stu-id="7a07a-183">Advanced eDiscovery architecture</span></span>

<span data-ttu-id="7a07a-184">以下是一個架構示意圖，顯示單一地理位置環境和多地理位置環境中的高級 eDiscovery 端對端工作流程，以及與 [電子探索參考模型](overview-ediscovery-20.md#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)對齊的端對端資料流程。</span><span class="sxs-lookup"><span data-stu-id="7a07a-184">Here's an architecture diagram that shows the Advanced eDiscovery end-to-end workflow in a single-geo environment and in a multi-geo environment, and the end-to-end data flow that's aligned with the [Electronic Discovery Reference Model](overview-ediscovery-20.md#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model).</span></span>

<span data-ttu-id="7a07a-185">[![模型海報： Microsoft 365 中的高級 eDiscovery 架構](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="7a07a-185">[![Model poster: Advanced eDiscovery Architecture in Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)</span></span>

[<span data-ttu-id="7a07a-186">以影像形式查看</span><span class="sxs-lookup"><span data-stu-id="7a07a-186">View as an image</span></span>](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[<span data-ttu-id="7a07a-187">下載為 PDF 檔案</span><span class="sxs-lookup"><span data-stu-id="7a07a-187">Download as a PDF file</span></span>](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[<span data-ttu-id="7a07a-188">下載為 Visio 檔案</span><span class="sxs-lookup"><span data-stu-id="7a07a-188">Download as a Visio file</span></span>](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
