---
title: 在 Microsoft 365 合規性中心，建立並執行內容搜尋。
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 使用合規性中心中的內容搜尋電子文件探索工具，在不同的 Microsoft 365 服務中搜尋內容。
ms.openlocfilehash: a058c07d080962723e9f6bc7a150cbfb5074e7db
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311654"
---
# <a name="create-a-content-search"></a><span data-ttu-id="5095d-103">建立內容搜尋</span><span class="sxs-lookup"><span data-stu-id="5095d-103">Create a content search</span></span>

<span data-ttu-id="5095d-104">您可以使用 Microsoft 365 合規性中心中的內容搜尋電子文件探索工具搜尋就地內容，例如組織中的電子郵件、文件和立即訊息交談。</span><span class="sxs-lookup"><span data-stu-id="5095d-104">You can use the Content search eDiscovery tool in the Microsoft 365 compliance center to search for in-place content such as email, documents, and instant messaging conversations in your organization.</span></span> <span data-ttu-id="5095d-105">使用此工具在這些 Microsoft 365 資料來源中搜尋內容：</span><span class="sxs-lookup"><span data-stu-id="5095d-105">Use this tool to search for content in these Microsoft 365 data sources:</span></span>
  
- <span data-ttu-id="5095d-106">Exchange Online 信箱</span><span class="sxs-lookup"><span data-stu-id="5095d-106">Exchange Online mailboxes</span></span>

- <span data-ttu-id="5095d-107">SharePoint Online 網站和商務用 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="5095d-107">SharePoint Online sites and OneDrive for Business accounts</span></span>

- <span data-ttu-id="5095d-108">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5095d-108">Microsoft Teams</span></span>

- <span data-ttu-id="5095d-109">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="5095d-109">Microsoft 365 Groups</span></span>

- <span data-ttu-id="5095d-110">Yammer 群組</span><span class="sxs-lookup"><span data-stu-id="5095d-110">Yammer Groups</span></span>

<span data-ttu-id="5095d-111">執行搜尋之後，搜尋飛出頁面中會顯示內容位置數目及預估的搜尋結果數目。</span><span class="sxs-lookup"><span data-stu-id="5095d-111">After you run a search, the number of content locations and an estimated number of search results are displayed on the search flyout page.</span></span> <span data-ttu-id="5095d-112">您可以快速檢視統計資料，例如最多項目符合搜尋查詢的內容位置。</span><span class="sxs-lookup"><span data-stu-id="5095d-112">You can quickly view statistics, such as the content locations that have the most items that match the search query.</span></span> <span data-ttu-id="5095d-113">執行搜尋後，您可以預覽結果或將結果匯出到本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="5095d-113">After you run a search, you can preview the results or export them to a local computer.</span></span>

## <a name="create-and-run-a-search"></a><span data-ttu-id="5095d-114">建立並執行搜尋</span><span class="sxs-lookup"><span data-stu-id="5095d-114">Create and run a search</span></span>

<span data-ttu-id="5095d-115">若要存取 Microsoft 365 合規性中心中的 [內容搜尋] 頁面以執行搜尋和預覽並匯出搜尋結果，系統管理員、法務人員或電子文件探索管理員必須是 [安全性與合規性中心] 中的電子文件探索管理員角色群組成員。</span><span class="sxs-lookup"><span data-stu-id="5095d-115">To access to the **Content search** page in the Microsoft 365 compliance center (to run searches and preview results and export results), an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in Security & Compliance Center.</span></span> <span data-ttu-id="5095d-116">如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="5095d-116">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
  
1. <span data-ttu-id="5095d-117">前往 <https://compliance.microsoft.com>，然後使用已指派適當權限的帳號認證登入。</span><span class="sxs-lookup"><span data-stu-id="5095d-117">Go to <https://compliance.microsoft.com> and sign in using the credentials of an account that's been assigned the appropriate permissions.</span></span>

2. <span data-ttu-id="5095d-118">在 Microsoft 365 合規性中心的左瀏覽窗格中，按一下 **[顯示全部]**，然後按一下 **[內容搜尋]**。</span><span class="sxs-lookup"><span data-stu-id="5095d-118">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="5095d-119">在 **[内容搜尋]** 頁面上，按一下 **[新增搜尋]**。</span><span class="sxs-lookup"><span data-stu-id="5095d-119">On the **Content search** page, click **New search**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5095d-120">[依識別碼清單搜尋] 選項可讓您使用 Exchange 識別碼的清單來搜尋特定的電子郵件訊息和其他信箱項目。</span><span class="sxs-lookup"><span data-stu-id="5095d-120">The **Search by ID list** option lets you search for specific email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="5095d-121">若要建立識別碼清單搜尋，您可以提交逗點分隔值 (CSV) 檔案，以識別要搜尋的特定信箱項目。</span><span class="sxs-lookup"><span data-stu-id="5095d-121">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="5095d-122">如需相關指示，請參閱[為備識別碼清單搜尋準備 CSV 檔案](csv-file-for-an-id-list-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="5095d-122">For instructions, see [Prepare a CSV file for an ID list search](csv-file-for-an-id-list-content-search.md).</span></span>

4. <span data-ttu-id="5095d-123">輸入搜尋的名稱，以及可協助識別搜尋的選擇性描述。</span><span class="sxs-lookup"><span data-stu-id="5095d-123">Type a name for the search, an optional description that helps identify the search.</span></span> <span data-ttu-id="5095d-124">搜尋的名稱在組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="5095d-124">The name of the search must be unique in your organization.</span></span>

5. <span data-ttu-id="5095d-125">在 [位置] 頁面上，選擇您想要搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="5095d-125">On the **Locations** page, choose the content locations that you want to search.</span></span> <span data-ttu-id="5095d-126">您可以搜尋信箱、網站與公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="5095d-126">You can search mailboxes, sites, and public folders.</span></span>

    ![選擇要設定保存措施的內容位置](../media/ContentSearchLocations.png)
  
   1. <span data-ttu-id="5095d-128">**Exchange 信箱**：將開關設定為 [開啟] ，然後按一下 [選擇使用者、群組或團隊] 以指定要設定保存措施的信箱。</span><span class="sxs-lookup"><span data-stu-id="5095d-128">**Exchange mailboxes**: Set the toggle to **On** and then click **Choose users, groups, or teams** to specify the mailboxes to place on hold.</span></span> <span data-ttu-id="5095d-129">使用搜尋方塊來尋找使用者信箱及通訊群組 (以在群組成員的信箱上設定保存措施) 以設定保存措施。</span><span class="sxs-lookup"><span data-stu-id="5095d-129">Use the search box to find user mailboxes and distribution groups (to place a hold on the mailboxes of group members) to place on hold.</span></span> <span data-ttu-id="5095d-130">您也可以搜尋與 Microsoft Teams （頻道訊息）、Office 365 群組和 Yammer 群組相關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="5095d-130">You can also search the mailbox associated with a Microsoft Team (for channel messages), Office 365 Group, and Yammer Group.</span></span> <span data-ttu-id="5095d-131">如需儲存在信箱中的應用程式資料詳細資訊，請參閱[儲存在電子文件探索信箱中的內容](what-is-stored-in-exo-mailbox.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="5095d-131">For more information about the application data stored in mailboxes, see [Content stored in mailboxes for eDiscovery](what-is-stored-in-exo-mailbox.md).</span></span>

   2. <span data-ttu-id="5095d-132">**SharePoint 網站**：將開關設定為 [開啟] 然後按一下 [選擇網站] 以指定要設定保存措施的 SharePoint 網站和 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="5095d-132">**SharePoint sites**: Set the toggle to **On** and then click **Choose sites** to specify SharePoint sites and OneDrive accounts to place on hold.</span></span> <span data-ttu-id="5095d-133">針對您想要設定保存措施的每個網站，輸入其 URL。</span><span class="sxs-lookup"><span data-stu-id="5095d-133">Type the URL for each site that you want to place on hold.</span></span> <span data-ttu-id="5095d-134">您也可以新增 Microsoft Teams、Office 365 群組或 Yammer 群組的 SharePoint 網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="5095d-134">You can also add the URL for the SharePoint site for a Microsoft Team, Office 365 Group, or Yammer Group.</span></span>
  
   3. <span data-ttu-id="5095d-135">**Exchange 公用資料夾**：將開關設定為 [開啟] 以保存 Exchange Online 組織的所有公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="5095d-135">**Exchange public folders**: Set the toggle to **On** to put all public folders in your Exchange Online organization on hold.</span></span> <span data-ttu-id="5095d-136">無法選擇保存特定公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="5095d-136">You can't choose specific public folders to put on hold.</span></span> <span data-ttu-id="5095d-137">如果您不想保存公用資料夾，請讓切換開關保持關閉。</span><span class="sxs-lookup"><span data-stu-id="5095d-137">Leave the toggle switch off if you don't want to put a hold on public folders.</span></span>
  
   4. <span data-ttu-id="5095d-138">保留選取此核取方塊以搜尋內部部署使用者的 Teams 內容。</span><span class="sxs-lookup"><span data-stu-id="5095d-138">Keep this checkbox selected to search for Teams content for on-premises users.</span></span> <span data-ttu-id="5095d-139">例如，如果您要搜尋組織中的所有 Exchange 信箱並選取此核取方塊，用於儲存內部部署使用者的 Teams 聊天資料的雲端式儲存空間將會包含在搜尋範圍中。</span><span class="sxs-lookup"><span data-stu-id="5095d-139">For example, if you search all Exchange mailboxes in the organization and this checkbox is selected, the cloud-based storage used to store Teams chat data for on-premises users will be included in the scope of the search.</span></span> <span data-ttu-id="5095d-140">如需詳細資訊，請參閱[搜尋內部部署使用者的 Teams 聊天資料](search-cloud-based-mailboxes-for-on-premises-users.md)。</span><span class="sxs-lookup"><span data-stu-id="5095d-140">For more information, see [Search for Teams chat data for on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>

6. <span data-ttu-id="5095d-141">在 [定義搜尋條件] 頁面上，輸入關鍵字查詢，並在必要時將條件新增到搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="5095d-141">On the **Define your search conditions** page, type a keyword query and add conditions to the search query if necessary.</span></span>

   ![設定搜尋查詢](../media/ContentSearchQuery.png)

   1. <span data-ttu-id="5095d-143">指定關鍵字、例如傳送和接收日期的郵件內容，或者例如檔案名稱或文件上次變更日期的文件內容。</span><span class="sxs-lookup"><span data-stu-id="5095d-143">Specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="5095d-144">您可以使用內含布林運算子，較為複雜的查詢，例如 **AND**、**OR**、**NOT** 和 **NEAR**。</span><span class="sxs-lookup"><span data-stu-id="5095d-144">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="5095d-145">如果將關鍵字方塊保留空白，則位於指定內容位置的所有內容都會包含在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="5095d-145">If you leave the keyword box empty, all content located in the specified content locations is included in the search results.</span></span> <span data-ttu-id="5095d-146">如需詳細資訊，請參閱[電子文件探索的的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="5095d-146">For more information, see [Keyword queries and search conditions for eDiscovery](keyword-queries-and-search-conditions.md).</span></span>

   2. <span data-ttu-id="5095d-147">或者，您可以按一下 **[顯示關鍵字清單]** 核取方塊，然後在每一列中輸入關鍵字。</span><span class="sxs-lookup"><span data-stu-id="5095d-147">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row.</span></span> <span data-ttu-id="5095d-148">如果您這麼做，每一列的關鍵字會以邏輯運算子 (**c:s**) 連接，其功能與建立的搜尋查詢中的 **OR** 運算子類似。</span><span class="sxs-lookup"><span data-stu-id="5095d-148">If you do this, the keywords on each row are connected by a logical operator (**c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span>

      <span data-ttu-id="5095d-149">為什麼要使用關鍵字清單？</span><span class="sxs-lookup"><span data-stu-id="5095d-149">Why use the keyword list?</span></span> <span data-ttu-id="5095d-150">您可以取得會顯示有多少個項目符合每個關鍵字的統計資料。</span><span class="sxs-lookup"><span data-stu-id="5095d-150">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="5095d-151">這可協助您快速找出哪些關鍵字最有效(和最不有效)。</span><span class="sxs-lookup"><span data-stu-id="5095d-151">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="5095d-152">您也可以在一列中使用關鍵字片語 (以括號括住)。</span><span class="sxs-lookup"><span data-stu-id="5095d-152">You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="5095d-153">如需關鍵字清單和搜尋統計資料的詳細資訊，請參閱[取得搜尋的關鍵字統計資料](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)。</span><span class="sxs-lookup"><span data-stu-id="5095d-153">For more information about the keyword list and search statistics, see [Get keyword statistics for searches](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span></span>

      > [!NOTE]
      > <span data-ttu-id="5095d-154">為了協助降低大量關鍵字清單造成的問題，關鍵字清單中最多只能有 20 列。</span><span class="sxs-lookup"><span data-stu-id="5095d-154">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

   3. <span data-ttu-id="5095d-155">您可以新增搜尋條件來縮小搜尋範圍，並傳回更精簡的結果集。</span><span class="sxs-lookup"><span data-stu-id="5095d-155">You can add search conditions to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="5095d-156">每個條件會將一個子句新增至在啟動搜尋時便會建立並執行的搜尋查詢中。</span><span class="sxs-lookup"><span data-stu-id="5095d-156">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="5095d-157">條件會在邏輯上使用功能上與 **AND** 運算子類似的邏輯運算子 (**c:c**) 與關鍵字查詢連結 (在關鍵字方塊中指定)。</span><span class="sxs-lookup"><span data-stu-id="5095d-157">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="5095d-158">這表示結果中包含的項目必須同時滿足關鍵字查詢與一或多個條件。</span><span class="sxs-lookup"><span data-stu-id="5095d-158">That means that items have to satisfy both the keyword query and one or more conditions to be included in the results.</span></span> <span data-ttu-id="5095d-159">這是條件協助縮小搜尋結果的方式。</span><span class="sxs-lookup"><span data-stu-id="5095d-159">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="5095d-160">有關可在搜尋查詢中使用的條件清單和描述，請參閱[搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="5095d-160">For a list and description of conditions that you can use in a search query, see [Search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>

7. <span data-ttu-id="5095d-161">檢閱搜尋設定 (並在必要時編輯)，然後提交搜尋以啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="5095d-161">Review the search settings (and edit if necessary), and then submit the search to start it.</span></span>
  
<span data-ttu-id="5095d-162">若要再次存取此內容搜尋，或存取 **[內容搜尋]** 頁面上所列的其他內容搜尋，請選取搜尋，然後按一下 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="5095d-162">To access this content search again or access other content searches listed on the **Content search** page, select the search and then click **Open**.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="5095d-163">後續步驟</span><span class="sxs-lookup"><span data-stu-id="5095d-163">Next steps</span></span>

<span data-ttu-id="5095d-164">以下是建立和執行內容搜尋之後要執行的後續步驟清單。</span><span class="sxs-lookup"><span data-stu-id="5095d-164">Here's a list of next steps to perform after you create and run a Content search.</span></span>

- [<span data-ttu-id="5095d-165">預覽搜尋結果</span><span class="sxs-lookup"><span data-stu-id="5095d-165">Preview search results</span></span>](preview-ediscovery-search-results.md)

- [<span data-ttu-id="5095d-166">檢視搜尋結果的統計資料</span><span class="sxs-lookup"><span data-stu-id="5095d-166">View statistics for search results</span></span>](view-keyword-statistics-for-content-search.md)

- [<span data-ttu-id="5095d-167">匯出搜尋結果</span><span class="sxs-lookup"><span data-stu-id="5095d-167">Export search results</span></span>](export-search-results.md)

- [<span data-ttu-id="5095d-168">匯出搜尋報告</span><span class="sxs-lookup"><span data-stu-id="5095d-168">Export a search report</span></span>](export-a-content-search-report.md)
