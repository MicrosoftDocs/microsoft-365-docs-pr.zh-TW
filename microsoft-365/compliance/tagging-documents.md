---
title: 標記檢閱集中的文件
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在審閱集中標記檔，可協助移除不必要的內容，並識別 Advanced eDiscovery 案例中的相關內容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736250"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="3c575-103">在 Advanced eDiscovery 中的審閱集中標記檔</span><span class="sxs-lookup"><span data-stu-id="3c575-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="3c575-104">在「檢查」集中組織內容對於在 eDiscovery 程式中完成各種工作流程很重要。</span><span class="sxs-lookup"><span data-stu-id="3c575-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="3c575-105">這包括：</span><span class="sxs-lookup"><span data-stu-id="3c575-105">This includes:</span></span>

- <span data-ttu-id="3c575-106">挑選不必要的內容</span><span class="sxs-lookup"><span data-stu-id="3c575-106">Culling unnecessary content</span></span>

- <span data-ttu-id="3c575-107">識別相關的內容</span><span class="sxs-lookup"><span data-stu-id="3c575-107">Identifying relevant content</span></span>

- <span data-ttu-id="3c575-108">識別專家或律師必須查看的內容</span><span class="sxs-lookup"><span data-stu-id="3c575-108">Identifying content that must be reviewed by an expert or attorney</span></span>

<span data-ttu-id="3c575-109">當專家、律師或其他使用者查看審閱集中的內容時，可以使用標記來捕獲其與內容相關的觀點。</span><span class="sxs-lookup"><span data-stu-id="3c575-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="3c575-110">例如，若要挑選不必要的內容，使用者可以使用標記（如「沒有回應」）來標記檔。</span><span class="sxs-lookup"><span data-stu-id="3c575-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="3c575-111">在審閱及標記內容之後，您可以建立審閱集搜尋，以排除標記為「無回應」的任何內容。</span><span class="sxs-lookup"><span data-stu-id="3c575-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive".</span></span> <span data-ttu-id="3c575-112">此程式會從 eDiscovery 工作流程的後續步驟中消除未回應的內容。</span><span class="sxs-lookup"><span data-stu-id="3c575-112">This process eliminates the non-responsive content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="3c575-113">您可以針對每個案例自訂審閱集中的 [標籤] 面板，使標記支援案例的預定的審閱工作流程。</span><span class="sxs-lookup"><span data-stu-id="3c575-113">The tagging panel in a review set can be customized for every case so that the tags support the intended review workflow for the case.</span></span>

> [!NOTE]
> <span data-ttu-id="3c575-114">標記的範圍是 Advanced eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="3c575-114">The scope of tags is an Advanced eDiscovery case.</span></span> <span data-ttu-id="3c575-115">這表示案例只能有一組標記可供檢閱者用來標記審閱集檔。</span><span class="sxs-lookup"><span data-stu-id="3c575-115">That means a case can only have one set of tags that reviewers can use to tag review set documents.</span></span> <span data-ttu-id="3c575-116">您無法設定一組不同的標記，以在相同的情況下用於不同的審閱集。</span><span class="sxs-lookup"><span data-stu-id="3c575-116">You can't set up a different set of tags for use in different review sets in the same case.</span></span>

## <a name="tag-types"></a><span data-ttu-id="3c575-117">標記類型</span><span class="sxs-lookup"><span data-stu-id="3c575-117">Tag types</span></span>

<span data-ttu-id="3c575-118">Advanced eDiscovery 提供兩種標記類型：</span><span class="sxs-lookup"><span data-stu-id="3c575-118">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="3c575-119">**單一選項標記**：限制檢閱者選取群組內的單一標記。</span><span class="sxs-lookup"><span data-stu-id="3c575-119">**Single choice tags**: Restricts reviewers to selecting a single tag within a group.</span></span> <span data-ttu-id="3c575-120">這些類型的標記是很有用的，可確保檢閱者沒有選取「已回應」及「無回應」等衝突標記。</span><span class="sxs-lookup"><span data-stu-id="3c575-120">These types of tags can be useful to ensure that reviewers don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="3c575-121">單一選項標記顯示為選項按鈕。</span><span class="sxs-lookup"><span data-stu-id="3c575-121">Single choice tags appear as radio buttons.</span></span>

- <span data-ttu-id="3c575-122">**多重選取標記**：允許評論選取群組中的多個標記。</span><span class="sxs-lookup"><span data-stu-id="3c575-122">**Multiple choice tags**: Allow reviews to select multiple tags within a group.</span></span> <span data-ttu-id="3c575-123">這些類型的標記會顯示為核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3c575-123">These types of tags appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="3c575-124">標記結構</span><span class="sxs-lookup"><span data-stu-id="3c575-124">Tag structure</span></span>

<span data-ttu-id="3c575-125">除了標記類型之外，標記在標記面板中的組織方式也可以用來讓標記檔更直觀。</span><span class="sxs-lookup"><span data-stu-id="3c575-125">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="3c575-126">標記是依區段群組。</span><span class="sxs-lookup"><span data-stu-id="3c575-126">Tags are grouped by sections.</span></span> <span data-ttu-id="3c575-127">「複查設定搜尋」支援依標籤及依標籤進行搜尋的功能] 區段。</span><span class="sxs-lookup"><span data-stu-id="3c575-127">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="3c575-128">這表示您可以建立「複查集搜尋」，以檢索標記為區段中任何標記的檔。</span><span class="sxs-lookup"><span data-stu-id="3c575-128">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![標記面板中的標記區段](../media/TagTypes.png)

<span data-ttu-id="3c575-130">您可以在區段中嵌套標記以進一步組織標籤。</span><span class="sxs-lookup"><span data-stu-id="3c575-130">You can further organize tags by nesting them within a section.</span></span> <span data-ttu-id="3c575-131">例如，如果要識別及標記特權內容，可以使用嵌套來明確檢閱者可以將檔標記為「特權」，並檢查適當的嵌套標記，以選取特權類型。</span><span class="sxs-lookup"><span data-stu-id="3c575-131">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a reviewer can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![標記區段中的嵌套標記](../media/NestingTags.png)

## <a name="create-tags"></a><span data-ttu-id="3c575-133">建立標記</span><span class="sxs-lookup"><span data-stu-id="3c575-133">Create tags</span></span>

<span data-ttu-id="3c575-134">將標籤套用至審閱集內的檔之前，您必須建立標記結構。</span><span class="sxs-lookup"><span data-stu-id="3c575-134">Before applying tags to documents in the review set, you need to create a tag structure.</span></span>

1. <span data-ttu-id="3c575-135">開啟審閱集，並流覽至命令列，然後選取 [ **依查詢選取標記**]。</span><span class="sxs-lookup"><span data-stu-id="3c575-135">Open a review set and navigate to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="3c575-136">在 [標記] 面板中，選取 [**管理標記選項**]。</span><span class="sxs-lookup"><span data-stu-id="3c575-136">In the tagging panel, select **Manage tag options**</span></span>

3. <span data-ttu-id="3c575-137">選取 [ **新增標記] 區段**。</span><span class="sxs-lookup"><span data-stu-id="3c575-137">Select **Add tag section**.</span></span>

4. <span data-ttu-id="3c575-138">輸入標記群組標題和選用的描述，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="3c575-138">Type a tag group title and an optional description, and then click **Save**.</span></span>

5. <span data-ttu-id="3c575-139">選取標記群組標題旁的三個點下拉式功能表，然後按一下 [ **新增] 核取方塊** 或 [ **新增選項] 按鈕**。</span><span class="sxs-lookup"><span data-stu-id="3c575-139">Select the triple dot dropdown menu next to the tag group title and click **Add check box** or **Add option button**.</span></span>

6. <span data-ttu-id="3c575-140">輸入核取方塊或選項按鈕的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="3c575-140">Type a name and description for the checkbox or option button.</span></span>

7. <span data-ttu-id="3c575-141">重複此程式以建立新的標記區段、標記選項及核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3c575-141">Repeat this process to create new tag sections, tag options, and checkboxes.</span></span>

   ![設定標記結構](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a><span data-ttu-id="3c575-143">套用標記</span><span class="sxs-lookup"><span data-stu-id="3c575-143">Applying tags</span></span>

<span data-ttu-id="3c575-144">使用標記結構時，檢閱者可以在審閱集中對檔套用標記。</span><span class="sxs-lookup"><span data-stu-id="3c575-144">With the tag structure in place, reviewers can apply tags to documents in a review set.</span></span> <span data-ttu-id="3c575-145">有兩種不同的套用標記方式：</span><span class="sxs-lookup"><span data-stu-id="3c575-145">There are two different ways to apply tags:</span></span>

- <span data-ttu-id="3c575-146">標記檔</span><span class="sxs-lookup"><span data-stu-id="3c575-146">Tag files</span></span>

- <span data-ttu-id="3c575-147">標記依據查詢</span><span class="sxs-lookup"><span data-stu-id="3c575-147">Tag by query</span></span>

### <a name="tag-files"></a><span data-ttu-id="3c575-148">標記檔</span><span class="sxs-lookup"><span data-stu-id="3c575-148">Tag files</span></span>

<span data-ttu-id="3c575-149">不論您是選取審閱集中的單一專案或多個專案，您可以按一下命令列中的 [標籤檔]， **將標記套用** 至選取範圍。</span><span class="sxs-lookup"><span data-stu-id="3c575-149">Whether you select a single item or several items in a review set, you can apply tags to their selection by clicking **Tag files** in the command bar.</span></span> <span data-ttu-id="3c575-150">在 [標記] 面板中，您可以選取標記，它會自動套用至選取的檔。</span><span class="sxs-lookup"><span data-stu-id="3c575-150">In the tagging panel, you can select a tag and it is automatically applied to the selected documents.</span></span>

![標記選取的檔案](../media/TagFile2.png)

> [!NOTE]
> <span data-ttu-id="3c575-152">標記只會套用至專案清單中的選取專案。</span><span class="sxs-lookup"><span data-stu-id="3c575-152">Tags will be applied only to selected items in the list of items.</span></span>

### <a name="tag-by-query"></a><span data-ttu-id="3c575-153">標記依據查詢</span><span class="sxs-lookup"><span data-stu-id="3c575-153">Tag by query</span></span>

<span data-ttu-id="3c575-154">[依查詢進行標記] 可讓您將標記套用至目前套用於審閱集之篩選查詢所顯示的所有專案。</span><span class="sxs-lookup"><span data-stu-id="3c575-154">Tagging by query lets you apply tags to all items displayed by a filter query that's currently applied in the review set.</span></span>

1. <span data-ttu-id="3c575-155">取消選取審閱集中的所有專案，然後移至命令列，然後選取 [ **依查詢選取標記**]。</span><span class="sxs-lookup"><span data-stu-id="3c575-155">Unselect all items in the review set and go to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="3c575-156">在 [標記] 面板中，選取您要套用的標記。</span><span class="sxs-lookup"><span data-stu-id="3c575-156">In the tagging panel, select the tag that you want to apply.</span></span>

3. <span data-ttu-id="3c575-157">在 [ **標記選取範圍** ] 下拉式清單中，有三個選項可以規定要套用標記的專案。</span><span class="sxs-lookup"><span data-stu-id="3c575-157">Under the **Tag selection** dropdown, there are three options that dictate which items to apply the tag to.</span></span>

   - <span data-ttu-id="3c575-158">**符合套用查詢的專案**：會將標記套用至符合篩選器查詢準則的特定專案。</span><span class="sxs-lookup"><span data-stu-id="3c575-158">**Items that match applied query**: Applies tags to specific items that match the filter query conditions.</span></span>

   - <span data-ttu-id="3c575-159">**包含相關聯的系列專案**：將標記套用至符合篩選器查詢準則的特定專案，以及其相關聯的族專案。</span><span class="sxs-lookup"><span data-stu-id="3c575-159">**Include associated family items**: Applies tags to specific items that match the filter query conditions and their associated family items.</span></span> <span data-ttu-id="3c575-160">*系列專案* 是指共用相同 FamilyId 中繼資料值的專案。</span><span class="sxs-lookup"><span data-stu-id="3c575-160">*Family items* are items that share the same FamilyId metadata value.</span></span>  

   - <span data-ttu-id="3c575-161">**包含相關聯的交談專案**：將標記套用至符合篩選器查詢準則的專案，以及其相關聯的交談專案。</span><span class="sxs-lookup"><span data-stu-id="3c575-161">**Include associated conversation items**: Applies tags to items that match the filter query conditions and their associated conversation items.</span></span> <span data-ttu-id="3c575-162">*交談專案* 是指共用相同 ConversationId 中繼資料值的專案。</span><span class="sxs-lookup"><span data-stu-id="3c575-162">*Conversation items* are items that share the same ConversationId metadata values.</span></span>

   ![標記選取](../media/TagByQuery2.png)

4. <span data-ttu-id="3c575-164">按一下 [ **開始標記] 工作** 以觸發標記工作。</span><span class="sxs-lookup"><span data-stu-id="3c575-164">Click **Start tagging job** to trigger the tagging job.</span></span>

## <a name="tag-filter"></a><span data-ttu-id="3c575-165">標記篩選</span><span class="sxs-lookup"><span data-stu-id="3c575-165">Tag filter</span></span>

<span data-ttu-id="3c575-166">使用 [檢查] 中的標籤篩選，可根據專案的標記方式，快速尋找或排除查詢結果中的專案。</span><span class="sxs-lookup"><span data-stu-id="3c575-166">Use the tag filter in review set to quickly find or exclude items from the query results based on how an item is tagged.</span></span> 

1. <span data-ttu-id="3c575-167">選取 [ **篩選** ] 以展開 [篩選] 面板。</span><span class="sxs-lookup"><span data-stu-id="3c575-167">Select **Filters** to expand the filter panel.</span></span>

2. <span data-ttu-id="3c575-168">選取並展開 [ **專案屬性**]。</span><span class="sxs-lookup"><span data-stu-id="3c575-168">Select and expand **Item properties**.</span></span>

3. <span data-ttu-id="3c575-169">向下流覽以找出 [篩選名稱] **標記**，選取核取方塊，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="3c575-169">Scroll down to find the filter named **Tag**, select the checkbox, and then click **Done**.</span></span>

4. <span data-ttu-id="3c575-170">若要在查詢中包含或排除具有特定標記的專案，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="3c575-170">To include or exclude items with a specific tag from a query, do one of the following:</span></span>

   - <span data-ttu-id="3c575-171">**包含專案**：選取標記值，然後在下拉式功能表中選取 [ **等於** ]。</span><span class="sxs-lookup"><span data-stu-id="3c575-171">**Include items**: Select the tag value and select **Equal any of** in the dropdown menu.</span></span>

      <span data-ttu-id="3c575-172">或者</span><span class="sxs-lookup"><span data-stu-id="3c575-172">Or</span></span>

   - <span data-ttu-id="3c575-173">**排除專案**：選取標記值，然後在下拉式功能表中選取 [ **等於無** ]。</span><span class="sxs-lookup"><span data-stu-id="3c575-173">**Exclude items**: Select the tag value and select **Equals none of** in dropdown menu.</span></span>

     ![標記篩選排除專案](../media/TagFilterExclude.png)

> [!NOTE]
> <span data-ttu-id="3c575-175">請務必重新整理頁面，以確保標記篩選顯示標籤結構的最新變更。</span><span class="sxs-lookup"><span data-stu-id="3c575-175">Be sure to refresh the page to ensure that the tag filter displays the latest changes to the tag structure.</span></span>
