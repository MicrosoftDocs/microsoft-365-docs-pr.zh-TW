---
title: 準備用於識別碼清單內容搜尋的 CSV 檔案
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
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: 使用來自現有內容搜尋的 CSV 檔案，以建立會傳回特定電子郵件專案的 ID 清單搜尋。
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311533"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="af09a-103">準備用於識別碼清單內容搜尋的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="af09a-103">Prepare a CSV file for an ID list Content search</span></span>

<span data-ttu-id="af09a-104">您可以使用 Exchange IDs 清單來搜尋特定的信箱電子郵件訊息和其他信箱專案。</span><span class="sxs-lookup"><span data-stu-id="af09a-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="af09a-105">若要建立識別碼清單搜尋，您可以提交逗點分隔值 (CSV) 檔案，以識別要搜尋的特定信箱項目。</span><span class="sxs-lookup"><span data-stu-id="af09a-105">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="af09a-106">針對此 CSV 檔案，您可以使用當您匯出內容搜尋結果時所包含的 **Results.csv** 檔或未 **編制索引的 Items.csv** 檔案，或從現有的內容搜尋中匯出內容搜尋報告時所包含的檔。</span><span class="sxs-lookup"><span data-stu-id="af09a-106">For this CSV file, you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content search results or export a Content search report from an existing Content search.</span></span> <span data-ttu-id="af09a-107">然後，編輯這些檔案中的其中一個，以指出要搜尋的特定專案、建立新的識別碼清單搜尋，然後提交 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="af09a-107">Then you edit one of these files to indicate the specific items to search for, create a new ID list search, and submit the CSV file.</span></span>

<span data-ttu-id="af09a-108">**為何要建立識別碼清單搜尋？**</span><span class="sxs-lookup"><span data-stu-id="af09a-108">**Why create an ID list search?**</span></span> <span data-ttu-id="af09a-109">如果您無法根據 **Results.csv** 或非 **索引的 Items.csv** 檔案中的中繼資料來判斷某個專案是否回應 eDiscovery 要求，您可以使用識別碼清單搜尋來尋找、預覽及匯出該專案，以判斷其是否回應您正在調查的案例。</span><span class="sxs-lookup"><span data-stu-id="af09a-109">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="af09a-110">識別碼清單搜尋通常是用來搜尋並傳回一組特定的未編制索引的專案。</span><span class="sxs-lookup"><span data-stu-id="af09a-110">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

<span data-ttu-id="af09a-111">以下是建立識別碼清單搜尋之程式的快速概覽。</span><span class="sxs-lookup"><span data-stu-id="af09a-111">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="af09a-112">在 Microsoft 365 規範中心建立並執行新的搜尋。</span><span class="sxs-lookup"><span data-stu-id="af09a-112">Create and run a new search in the Microsoft 365 compliance center.</span></span>

2. <span data-ttu-id="af09a-113">匯出內容搜尋結果或內容搜尋報告。</span><span class="sxs-lookup"><span data-stu-id="af09a-113">Export the content search results or the content search report.</span></span> <span data-ttu-id="af09a-114">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="af09a-114">For more information, see:</span></span>

    - [<span data-ttu-id="af09a-115">匯出內容搜尋結果</span><span class="sxs-lookup"><span data-stu-id="af09a-115">Export Content search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="af09a-116">匯出內容搜尋報告</span><span class="sxs-lookup"><span data-stu-id="af09a-116">Export a Content search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="af09a-117">編輯 **Results.csv** 檔或未 **編制索引的 Items.csv** 檔案，並識別要包含在識別碼清單搜尋中的特定信箱專案。</span><span class="sxs-lookup"><span data-stu-id="af09a-117">Edit the **Results.csv** file or **Unindexed Items.csv** file and identify the specific mailbox items to include in the ID list search.</span></span> <span data-ttu-id="af09a-118">請參閱針對識別碼清單搜尋準備 CSV 檔案的 [指示](#prepare-the-csv-file-for-an-id-list-search) 。</span><span class="sxs-lookup"><span data-stu-id="af09a-118">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="af09a-119">建立新的識別碼清單搜尋 (請參閱 [指示](#create-an-id-list-search)) 並提交您準備的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="af09a-119">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="af09a-120">所建立的搜尋查詢只會搜尋 CSV 檔案中選取的專案。</span><span class="sxs-lookup"><span data-stu-id="af09a-120">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="af09a-121">僅支援信箱專案的 ID 清單搜尋。</span><span class="sxs-lookup"><span data-stu-id="af09a-121">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="af09a-122">您無法在識別碼清單搜尋中搜尋 SharePoint 和 OneDrive 檔。</span><span class="sxs-lookup"><span data-stu-id="af09a-122">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="af09a-123">準備用於識別碼清單搜尋的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="af09a-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="af09a-124">匯出搜尋結果或報表進行搜尋之後，請執行下列步驟，以準備用於識別碼清單搜尋的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="af09a-124">After you export the search results or report for a search, perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="af09a-125">此 CSV 檔案識別識別碼清單搜尋中的每個專案。</span><span class="sxs-lookup"><span data-stu-id="af09a-125">This CSV file identifies every item in the ID list search.</span></span>

<span data-ttu-id="af09a-126">您可以從包含 SharePoint 網站和 OneDrive 帳戶的搜尋使用 CSV 檔案，但您只能選取識別碼清單搜尋的信箱專案。</span><span class="sxs-lookup"><span data-stu-id="af09a-126">You can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can only select mailbox items for an ID list search.</span></span> <span data-ttu-id="af09a-127">如果您選取 SharePoint 或 OneDrive 中的檔，當您建立識別碼清單搜尋時，CSV 檔案會失敗驗證。</span><span class="sxs-lookup"><span data-stu-id="af09a-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="af09a-128">在 Excel 中開啟 **Results.csv** 或未 **編制索引的 Items.csv** 檔案。</span><span class="sxs-lookup"><span data-stu-id="af09a-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="af09a-129">在 [ **選取** ] 欄的儲存格中輸入 **[是]** ，對應至您要搜尋的專案。</span><span class="sxs-lookup"><span data-stu-id="af09a-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="af09a-130">針對您要搜尋的每個專案重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="af09a-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="af09a-131">當您在 Excel 中開啟 CSV 檔案時，檔 **識別碼** 欄的資料格式可能已變更為 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="af09a-131">When you open the CSV file in Excel, the data format for the **Document ID** column may have been changed to **General**.</span></span> <span data-ttu-id="af09a-132">這會導致顯示以科學記數法表示的專案檔案識別碼。</span><span class="sxs-lookup"><span data-stu-id="af09a-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="af09a-133">例如，[481037338205] 的檔識別碼會顯示為 "4.81037 E + 11"。</span><span class="sxs-lookup"><span data-stu-id="af09a-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11".</span></span> <span data-ttu-id="af09a-134">如果發生這種情況，您必須執行後續步驟，將 [ **檔識別碼** ] 欄的資料格式變更為 [ **數位** ]，以還原檔識別碼的正確格式。</span><span class="sxs-lookup"><span data-stu-id="af09a-134">If this happens, you have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="af09a-135">否則，使用 CSV 檔案的 ID 清單搜尋會失敗。</span><span class="sxs-lookup"><span data-stu-id="af09a-135">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="af09a-136">以滑鼠右鍵按一下 [整個 **檔識別碼** ] 欄，然後選取 [ **設定儲存格格式**]。</span><span class="sxs-lookup"><span data-stu-id="af09a-136">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="af09a-137">在 [ **類別** ] 方塊中，按一下 [ **數位**]。</span><span class="sxs-lookup"><span data-stu-id="af09a-137">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="af09a-138">將小數位位數變更為 **0**，然後按一下 **[確定]** 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="af09a-138">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="af09a-139">請注意，[檔識別碼] 欄中的值會變更為 [數位]。</span><span class="sxs-lookup"><span data-stu-id="af09a-139">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="af09a-140">以下是可提交識別碼清單內容搜尋之 CSV 檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="af09a-140">Here's an example of a CSV file that's ready to be submitted for an ID list content search.</span></span>

    ![目標內容搜尋的 CSV 檔案範例](../media/SearchIDListCSVFile.png)

6. <span data-ttu-id="af09a-142">儲存 CSV 檔案，或使用另 **存** 新檔案名儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="af09a-142">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="af09a-143">在這兩種情況下，請務必以 CSV 格式儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="af09a-143">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="af09a-144">建立識別碼清單搜尋</span><span class="sxs-lookup"><span data-stu-id="af09a-144">Create an ID list search</span></span>

<span data-ttu-id="af09a-145">下一步是建立新的識別碼清單搜尋，並提交您在上一個步驟中準備的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="af09a-145">The next step is to create a new ID list search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af09a-146">在匯出搜尋結果或報告之後，您應建立至少2天的 ID 清單搜尋。</span><span class="sxs-lookup"><span data-stu-id="af09a-146">You should create an ID list search no more than 2 days after exporting the search results or report.</span></span> <span data-ttu-id="af09a-147">如果搜尋結果或報告的輸出超過2天，您應該重新匯出搜尋結果或報表，以產生更新的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="af09a-147">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="af09a-148">然後您可以準備其中一個更新的 CSV 檔案，並使用它來建立識別碼清單搜尋。</span><span class="sxs-lookup"><span data-stu-id="af09a-148">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="af09a-149">移至 <https://compliance.microsoft.com> 並登入。</span><span class="sxs-lookup"><span data-stu-id="af09a-149">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="af09a-150">在 Microsoft 365 合規性中心的左瀏覽窗格中，按一下 **[顯示全部]**，然後按一下 **[內容搜尋]**。</span><span class="sxs-lookup"><span data-stu-id="af09a-150">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="af09a-151">在 [ **內容搜尋** ] 頁面上，按一下 [ **依識別碼搜尋] 清單**。</span><span class="sxs-lookup"><span data-stu-id="af09a-151">On the **Content search** page, click **Search by ID List**.</span></span>

4. <span data-ttu-id="af09a-152">在 [ **依識別碼搜尋] 清單** 快顯視窗中，命名搜尋 (並選擇性地描述它) 然後按一下 **[流覽]** ，然後選取您在上一個步驟中準備好的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="af09a-152">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="af09a-153">Microsoft 365 會嘗試驗證 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="af09a-153">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="af09a-154">如果驗證失敗，則會顯示錯誤訊息，以協助您疑難排解驗證錯誤。</span><span class="sxs-lookup"><span data-stu-id="af09a-154">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="af09a-155">CSV 檔案必須成功驗證，才能建立識別碼清單搜尋。</span><span class="sxs-lookup"><span data-stu-id="af09a-155">The CSV file has to be successfully validated to create an ID list search.</span></span>

5. <span data-ttu-id="af09a-156">在成功驗證 CSV 檔案之後，按一下 [ **搜尋** ] 以建立識別碼清單搜尋。</span><span class="sxs-lookup"><span data-stu-id="af09a-156">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="af09a-157">以下是識別碼清單搜尋中的飛出頁面範例，顯示產生的查詢及估計的搜尋結果數目。</span><span class="sxs-lookup"><span data-stu-id="af09a-157">Here's an example of the flyout page from an ID list search that shows the query that's generated and the estimated number of search results.</span></span>

    ![識別碼清單搜尋的搜尋查詢](../media/SearchIDListFlyout.png)

    <span data-ttu-id="af09a-159">在識別碼搜尋的統計資料中顯示的預估專案數目，應符合您在 CSV 檔案中選取的專案數。</span><span class="sxs-lookup"><span data-stu-id="af09a-159">The number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

6. <span data-ttu-id="af09a-160">預覽或匯出識別碼清單搜尋傳回的專案。</span><span class="sxs-lookup"><span data-stu-id="af09a-160">Preview or export the items returned by the ID list search.</span></span>

## <a name="more-information"></a><span data-ttu-id="af09a-161">其他資訊</span><span class="sxs-lookup"><span data-stu-id="af09a-161">More information</span></span>

<span data-ttu-id="af09a-162">如果您在建立 ID 清單搜尋之後移動信箱，則搜尋查詢不會傳回指定的專案。</span><span class="sxs-lookup"><span data-stu-id="af09a-162">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="af09a-163">這是因為在移動信箱時，信箱專案的 **DocumentId** 屬性會變更。</span><span class="sxs-lookup"><span data-stu-id="af09a-163">That's because the **DocumentId** property for mailbox items is changed when a mailbox is moved.</span></span> <span data-ttu-id="af09a-164">在您建立識別碼清單搜尋之後移動信箱的少數情況下，您應該建立新的內容搜尋 (或更新現有搜尋) 的搜尋結果，然後匯出搜尋結果或報告，以產生可用來建立新的 ID 清單搜尋的更新 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="af09a-164">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new Content search (or update the search results for an existing search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
