---
title: Office 365 中的內容搜尋
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: 使用 Office 365 或 Microsoft 365 合規性中心中的「內容搜尋」工具，來搜尋信箱中的內容、SharePoint Online 網站，OneDrive 帳戶、Microsoft Teams、Office 365 群組和商務用 Skype 交談。 您可以使用關鍵字搜尋查詢和搜尋條件來縮小搜尋結果。 然後您可以預覽和匯出搜尋結果。 內容搜尋也是用來搜尋與 GDPR 資料主體要求相關內容的有效工具。
ms.openlocfilehash: d27bce246cabfafd343286fc40ea670bfe560b9e
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967516"
---
# <a name="content-search-in-office-365"></a><span data-ttu-id="43114-106">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="43114-106">Content Search in Office 365</span></span>

<span data-ttu-id="43114-107">您可以使用 Office 365 或 Microsoft 365 合規性中心中的內容搜尋電子文件探索工具，來搜尋 Office 365 組織中的就地項目，例如電子郵件、文件和立即訊息交談。</span><span class="sxs-lookup"><span data-stu-id="43114-107">You can use the Content Search eDiscovery tool in the compliance center in Office 365 or Microsoft 365 to search for in-place items such as email, documents, and instant messaging conversations in your Office 365 organization.</span></span> <span data-ttu-id="43114-108">使用此工具來搜尋這些 Office 365 服務中的項目：</span><span class="sxs-lookup"><span data-stu-id="43114-108">Use this tool to search for items in these Office 365 services:</span></span>
  
- <span data-ttu-id="43114-109">Exchange Online 信箱和公用資料夾</span><span class="sxs-lookup"><span data-stu-id="43114-109">Exchange Online mailboxes and public folders</span></span>
    
- <span data-ttu-id="43114-110">SharePoint Online 網站和商務用 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="43114-110">SharePoint Online sites and OneDrive for Business accounts</span></span>
    
- <span data-ttu-id="43114-111">商務用 Skype 交談</span><span class="sxs-lookup"><span data-stu-id="43114-111">Skype for Business conversations</span></span>
    
- <span data-ttu-id="43114-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43114-112">Microsoft Teams</span></span> 
    
- <span data-ttu-id="43114-113">Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="43114-113">Office 365 Groups</span></span>
    
<span data-ttu-id="43114-114">執行內容搜尋之後，內容位置數目及預估的搜尋結果數目會顯示在搜尋統計資料中。</span><span class="sxs-lookup"><span data-stu-id="43114-114">After you run a Content Search, the number of content locations and an estimated number of search results are displayed in the search statistics.</span></span> <span data-ttu-id="43114-115">您也可以快速檢視統計資料，例如多數項目符合搜尋查詢的內容位置。</span><span class="sxs-lookup"><span data-stu-id="43114-115">You can also quickly view statistics, such as the content locations that have the most items that match the search query.</span></span> <span data-ttu-id="43114-116">執行搜尋後，您可以預覽結果或將結果匯出到本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="43114-116">After you run a search, you can preview the results or export them to a local computer.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="43114-117">建立搜尋</span><span class="sxs-lookup"><span data-stu-id="43114-117">Create a search</span></span>

<span data-ttu-id="43114-118">若要有權存取**內容搜尋**頁面以執行搜尋和預覽並匯出搜尋結果，系統管理員、法務人員或電子文件探索管理員必須是安全性與合規性中心中電子文件探索管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="43114-118">To have access to the **Content search** page to run searches and preview and export search results, an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="43114-119">如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="43114-119">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
  
1. <span data-ttu-id="43114-120">移至 [https://protection.office.com](https://protection.office.com) 並使用您的 Office 365 電子郵件地址和密碼登入。</span><span class="sxs-lookup"><span data-stu-id="43114-120">Go to [https://protection.office.com](https://protection.office.com) and sign in using your Office 365 email address and password.</span></span>
    
2. <span data-ttu-id="43114-121">按一下 **[搜尋]** \> **[內容搜尋]**。</span><span class="sxs-lookup"><span data-stu-id="43114-121">Click **Search** \> **Content search**.</span></span>
    
3. <span data-ttu-id="43114-122">在 **[搜尋]** 頁面上，按一下 [![加號圖示](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) 新增搜尋]\*\*\*\* 旁邊的箭號。</span><span class="sxs-lookup"><span data-stu-id="43114-122">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span> 
    
    ![[新增搜尋] 下拉式清單](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    <span data-ttu-id="43114-124">您可以選擇下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="43114-124">You can choose one of the following options:</span></span>
    
    - <span data-ttu-id="43114-125">**引導式搜尋：** 此選項會啟動精靈，引導您建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-125">**Guided search:** This option starts a wizard that guides you through the creating the search.</span></span> <span data-ttu-id="43114-126">用來選取內容位置和建置搜尋查詢的使用者介面與 **[新增搜尋]** 選項完全相同。</span><span class="sxs-lookup"><span data-stu-id="43114-126">The user interface to select content locations and build the search query are the same as the **New search** option.</span></span> 
    
    - <span data-ttu-id="43114-127">**新增搜尋：** 此選項會顯示更新的使用者介面以建立搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-127">**New search:** This option displays an updated user interface to create a search.</span></span> <span data-ttu-id="43114-128">如果您按一下 **[新增搜尋]**，這會是預設選項。</span><span class="sxs-lookup"><span data-stu-id="43114-128">This is the default option if you click **New search**.</span></span>
    
    - <span data-ttu-id="43114-129">**依識別碼清單搜尋：** 此選項可讓您使用 Exchange 識別碼的清單來搜尋特定的電子郵件訊息和其他信箱項目。</span><span class="sxs-lookup"><span data-stu-id="43114-129">**Search by ID List:** This option lets you search for specific email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="43114-130">若要建立識別碼清單搜尋 (正式名稱為目標搜尋)，您可以提交逗點分隔值 (CSV) 檔案，以識別要搜尋的特定信箱項目。</span><span class="sxs-lookup"><span data-stu-id="43114-130">To create an ID list search (formally called a targeted search), you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="43114-131">如需相關指示，請參閱[在 Office 365 中準備識別碼清單內容搜尋的 CSV 檔案](csv-file-for-an-id-list-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="43114-131">For instructions, see [Prepare a CSV file for an ID list Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
    
    <span data-ttu-id="43114-132">此程序中的其餘步驟會遵循預設的新增搜尋工作流程。</span><span class="sxs-lookup"><span data-stu-id="43114-132">The remainder of the steps in this procedure follows the default new search workflow.</span></span>
    
4. <span data-ttu-id="43114-133">在下拉式清單中按一下 **[新增搜尋]**。</span><span class="sxs-lookup"><span data-stu-id="43114-133">Click **New search** in the drop-down list.</span></span> 
    
5. <span data-ttu-id="43114-134">在 **[搜尋查詢]** 下，指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="43114-134">Under **Search query**, specify the following things:</span></span>
    
    ![指定要搜尋的關鍵字、條件和位置](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
   - <span data-ttu-id="43114-136">**要搜尋的關鍵字：** 在 **[關鍵字]** 方塊中輸入搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="43114-136">**Keywords to search for:** Type a search query in **Keywords** box.</span></span> <span data-ttu-id="43114-137">您可以指定關鍵字、例如傳送和接收日期的郵件屬性，或者例如檔案名稱或文件上次變更的日期的文件屬性。</span><span class="sxs-lookup"><span data-stu-id="43114-137">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="43114-138">您可以使用內含布林運算子的更複雜的查詢，例如 **AND**、**OR**、**NOT** 和 **NEAR**。</span><span class="sxs-lookup"><span data-stu-id="43114-138">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="43114-139">您也可以搜尋文件中的機密資訊 (如身分證號碼) 或搜尋曾在外部共用的文件。</span><span class="sxs-lookup"><span data-stu-id="43114-139">You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally.</span></span> <span data-ttu-id="43114-140">如果將關鍵字方塊保留空白，則位於指定內容位置的所有內容都會包含在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="43114-140">If you leave the keyword box empty, all content located in the specified content locations is included in the search results.</span></span>
    
      <span data-ttu-id="43114-141">或者，您可以按一下 **[顯示關鍵字清單]** 核取方塊，然後在每一列中輸入關鍵字。</span><span class="sxs-lookup"><span data-stu-id="43114-141">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row.</span></span> <span data-ttu-id="43114-142">如果您這麼做，每一列的關鍵字會以邏輯運算子 (**c:s**) 連接，其功能與建立的搜尋查詢中的 **OR** 運算子類似。</span><span class="sxs-lookup"><span data-stu-id="43114-142">If you do this, the keywords on each row are connected by a logical operator (**c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
      <span data-ttu-id="43114-143">為什麼要使用關鍵字清單？</span><span class="sxs-lookup"><span data-stu-id="43114-143">Why use the keyword list?</span></span> <span data-ttu-id="43114-144">您可以取得會顯示有多少個項目符合每個關鍵字的統計資料。</span><span class="sxs-lookup"><span data-stu-id="43114-144">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="43114-145">這可協助您快速找出哪些關鍵字最有效(和最不有效)。</span><span class="sxs-lookup"><span data-stu-id="43114-145">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="43114-146">您也可以在一列中使用關鍵字片語 (以括號括住)。</span><span class="sxs-lookup"><span data-stu-id="43114-146">You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="43114-147">如需搜尋統計資料的詳細資訊，請參閱[檢視內容搜尋結果的關鍵字統計資料](view-keyword-statistics-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="43114-147">For more information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="43114-148">為了協助降低大量關鍵字清單造成的問題，現在關鍵字清單中最多只能有 20 列。</span><span class="sxs-lookup"><span data-stu-id="43114-148">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list.</span></span>
    
    - <span data-ttu-id="43114-149">**條件：** 您可以新增搜尋條件來縮小搜尋範圍，並傳回更精簡的結果集。</span><span class="sxs-lookup"><span data-stu-id="43114-149">**Conditions:** You can add search conditions to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="43114-150">每個條件會將一個子句新增至在啟動搜尋時便會建立並執行的搜尋查詢中。</span><span class="sxs-lookup"><span data-stu-id="43114-150">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="43114-151">條件會在邏輯上使用功能上與 **AND** 運算子類似的邏輯運算子 (**c:c**) 與關鍵字查詢連結 (在關鍵字方塊中指定)。</span><span class="sxs-lookup"><span data-stu-id="43114-151">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="43114-152">這表示結果中包含的項目必須同時滿足關鍵字查詢與一或多個條件。</span><span class="sxs-lookup"><span data-stu-id="43114-152">That means that items have to satisfy both the keyword query and one or more conditions to be included in the results.</span></span> <span data-ttu-id="43114-153">這是條件協助縮小搜尋結果的方式。</span><span class="sxs-lookup"><span data-stu-id="43114-153">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="43114-154">如需您可以在搜尋查詢中使用的條件清單和描述，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)中的「搜尋條件」一節。</span><span class="sxs-lookup"><span data-stu-id="43114-154">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
    
       - <span data-ttu-id="43114-155">**位置：** 選擇要搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="43114-155">**Locations:** Choose the content locations to search.</span></span>
    
      - <span data-ttu-id="43114-156">**所有位置：** 使用此選項來搜尋組織中的所有內容位置。</span><span class="sxs-lookup"><span data-stu-id="43114-156">**All locations:** Use this option to search all content locations in your organization.</span></span> <span data-ttu-id="43114-157">這包括所有 Exchange 信箱 (包括所有非作用中信箱、所有 Office 365 群組的信箱、所有的 Microsoft Teams 信箱) 中的電子郵件、所有商務用 Skype 交談、所有 SharePoint 和商務用 OneDrive 網站 (包括適用於所有 Office 365 群組和 Microsoft Teams 的網站)，以及所有 Exchange 公用資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="43114-157">This includes email in all Exchange mailboxes (including all inactive mailboxes, mailboxes for all Office 365 Groups, mailboxes for all Microsoft Teams), all Skype for Business conversations, all SharePoint and OneDrive for Business sites (including the sites for all Office 365 Groups and Microsoft Teams), and items in all Exchange public folders.</span></span>
    
      - <span data-ttu-id="43114-158">**特定位置：** 使用此選項來搜尋特定內容位置。</span><span class="sxs-lookup"><span data-stu-id="43114-158">**Specific locations:** Use this option to search specific content locations.</span></span> <span data-ttu-id="43114-159">您可以搜尋特定 Office 365 服務的所有內容位置 (例如搜尋所有 Exchange 信箱或搜尋所有 SharePoint 網站)，或者您可以搜尋所顯示的任何 Office 365 服務中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="43114-159">You can search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or search all SharePoint sites) or you can search specific locations in any of the Office 365 services that are displayed.</span></span> 
    
        ![用來選擇要搜尋的內容位置的使用者介面](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
         <span data-ttu-id="43114-161">您也可以將通訊群組新增到要搜尋的 Exchange 信箱清單。</span><span class="sxs-lookup"><span data-stu-id="43114-161">You can also add distribution groups to the list of Exchange mailboxes to search.</span></span> <span data-ttu-id="43114-162">針對通訊群組，會搜尋群組成員的信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-162">For distribution groups, the mailboxes of group members are searched.</span></span> <span data-ttu-id="43114-163">不支援動態通訊群組。</span><span class="sxs-lookup"><span data-stu-id="43114-163">Dynamic distribution groups aren't supported.</span></span>
    
       > [!NOTE]
       > <span data-ttu-id="43114-164">當您搜尋所有信箱位置或只是特定信箱時，匯出內容搜尋的結果時，會包含儲存在使用者信箱、來自其他 Office 365 應用程式的資料。</span><span class="sxs-lookup"><span data-stu-id="43114-164">When you search all mailbox locations or just specific mailboxes, data from other Office 365 applications that's saved to user mailboxes is included when you export the results of a Content Search.</span></span> <span data-ttu-id="43114-165">此資料不會包含在估計的搜尋結果中，並且無法提供預覽。</span><span class="sxs-lookup"><span data-stu-id="43114-165">This data won't be included in the estimated search results and isn't available for preview.</span></span> <span data-ttu-id="43114-166">當您匯出並下載搜尋結果時會包含在內。</span><span class="sxs-lookup"><span data-stu-id="43114-166">It is included when you export and download the search results.</span></span> <span data-ttu-id="43114-167">如需詳細資訊，請參閱[儲存在 Exchange Online 信箱中的內容](what-is-stored-in-exo-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="43114-167">For more information, see [Content stored in Exchange Online mailboxes](what-is-stored-in-exo-mailbox.md).</span></span>

    
6. <span data-ttu-id="43114-168">設定您的搜尋查詢之後，請按一下 **[儲存並執行]**。</span><span class="sxs-lookup"><span data-stu-id="43114-168">After you've set up your search query, click **Save & run**.</span></span>
    
7. <span data-ttu-id="43114-169">在 **[儲存搜尋]** 頁面上，輸入搜尋的名稱，以及可協助識別搜尋的選擇性描述。</span><span class="sxs-lookup"><span data-stu-id="43114-169">On the **Save search** page, type a name for the search, and an optional description that helps identify the search.</span></span> <span data-ttu-id="43114-170">搜尋的名稱在組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="43114-170">The name of the search has to be unique in your organization.</span></span> 
    
8. <span data-ttu-id="43114-171">按一下 **[儲存]** 開始搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-171">Click **Save** to start the search.</span></span> 
    
    <span data-ttu-id="43114-172">儲存並執行搜尋之後，搜尋所傳回的任何結果會顯示在結果窗格中。</span><span class="sxs-lookup"><span data-stu-id="43114-172">After you save and run the search, any results returned by the search are displayed in the results pane.</span></span> <span data-ttu-id="43114-173">根據您設定預覽設定的方式，搜尋結果會顯示或者您可以按一下 **[預覽結果]** 來加以檢視。</span><span class="sxs-lookup"><span data-stu-id="43114-173">Depending on how you have the preview setting configured, the search results are display or you have to click **Preview results** to view them.</span></span> <span data-ttu-id="43114-174">如需詳細資料，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="43114-174">See the next section for details.</span></span> 
    
<span data-ttu-id="43114-175">若要再次存取此內容搜尋，或存取 **[內容搜尋]** 頁面上所列的其他內容搜尋，請選取搜尋，然後按一下 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="43114-175">To access this content search again or access other content searches listed on the **Content search** page, select the search and then click **Open**.</span></span> 
  
<span data-ttu-id="43114-176">若要清除結果，或建立另一個搜尋，請按一下 [![加號圖示](media/O365-MDM-CreatePolicy-AddIcon.gif) 新增搜尋]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="43114-176">To clear the results or create another search, click ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif) **New search**.</span></span> 
  
## <a name="preview-search-results"></a><span data-ttu-id="43114-177">預覽搜尋結果</span><span class="sxs-lookup"><span data-stu-id="43114-177">Preview search results</span></span>

<span data-ttu-id="43114-178">預覽搜尋結果有兩個組態設定。</span><span class="sxs-lookup"><span data-stu-id="43114-178">There are two configuration settings for previewing search results.</span></span> <span data-ttu-id="43114-179">執行新搜尋或開啟現有的搜尋之後，請按一下 **[個別結果]** 來檢視下列預覽設定：</span><span class="sxs-lookup"><span data-stu-id="43114-179">After you run a new search or open an existing search, click **Individual results** to view the following preview settings:</span></span> 
  
![預覽搜尋結果設定](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. <span data-ttu-id="43114-181">**自動預覽結果：** 此設定會在您執行搜尋後顯示搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="43114-181">**Preview results automatically:** This setting displays the search results after you a run a search.</span></span>
    
2. <span data-ttu-id="43114-182">**手動預覽結果：** 此設定會在搜尋結果窗格中顯示預留位置，並顯示 **[預覽結果]** 按鈕，您必須按一下該按鈕才能顯示搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="43114-182">**Preview results manually:** This setting displays placeholders in the search results pane, and displays the **Preview results** button that you have to click to display the search results.</span></span> <span data-ttu-id="43114-183">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="43114-183">This is the default setting.</span></span> <span data-ttu-id="43114-184">透過不要在開啟現有搜尋時自動顯示搜尋結果，這有助於增強搜尋效能。</span><span class="sxs-lookup"><span data-stu-id="43114-184">It helps enhance search performance by not automatically displaying the search results when you open an existing search.</span></span> 
    
<span data-ttu-id="43114-185">可供預覽的項目數有相關的限制。</span><span class="sxs-lookup"><span data-stu-id="43114-185">There are limits related to how many items are available to be previewed.</span></span> <span data-ttu-id="43114-186">如需詳細資訊，請參閱[內容搜尋的限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="43114-186">For more information, see [Limits for Content Search](limits-for-content-search.md).</span></span> 
  
<span data-ttu-id="43114-187">如需可預覽的受支援檔案類型清單，請參閱「有關內容搜尋的詳細資訊」小節中的[預覽搜尋結果](#previewing-search-results)。</span><span class="sxs-lookup"><span data-stu-id="43114-187">For a list of supported file types that can be previewed, see [Previewing search results](#previewing-search-results) in the "More information about content search" section.</span></span> <span data-ttu-id="43114-188">如果某個檔案類型不支援預覽，或者若要下載文件的副本，您可以按一下 **[下載原始檔案]** 來將它下載至本機電腦。</span><span class="sxs-lookup"><span data-stu-id="43114-188">If a file type isn't supported for preview or to download a copy of a document, you can click **Download original file** to download it to your local computer.</span></span> <span data-ttu-id="43114-189">針對 .aspx 網頁，將會包含網頁的 URL，不過您可能沒有存取該頁面的權限。</span><span class="sxs-lookup"><span data-stu-id="43114-189">For .aspx Web pages, the URL for the page is included though you might not have permissions to access the page.</span></span> 
  
<span data-ttu-id="43114-190">也請注意，未建立索引的項目無法提供預覽。</span><span class="sxs-lookup"><span data-stu-id="43114-190">Also note that unindexed items aren't available for previewing.</span></span>
  
## <a name="view-information-and-statistics-about-a-search"></a><span data-ttu-id="43114-191">檢視有關搜尋的資訊和統計資料</span><span class="sxs-lookup"><span data-stu-id="43114-191">View information and statistics about a search</span></span>

<span data-ttu-id="43114-192">建立並執行內容搜尋後，您可以檢視估計的搜尋結果的相關統計資料。</span><span class="sxs-lookup"><span data-stu-id="43114-192">After you create and run a content search, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="43114-193">這包括搜尋結果的摘要、查詢統計資料，例如具有的項目符合搜尋查詢的內容位置數量，以及具有最符合項目的內容位置名稱。</span><span class="sxs-lookup"><span data-stu-id="43114-193">This includes a summary of the search results, the query statistics such as the number of content locations with items that match the search query, and the name of content locations that have the most matching items.</span></span> <span data-ttu-id="43114-194">您可以顯示一或多個內容搜尋的統計資料。</span><span class="sxs-lookup"><span data-stu-id="43114-194">You can display statistics for one or more content searches.</span></span> <span data-ttu-id="43114-195">如此可讓您快速比較多個搜尋的結果，並對您的搜尋查詢的有效性進行相關決策。</span><span class="sxs-lookup"><span data-stu-id="43114-195">This lets you quickly compare the results for multiple searches and make decisions about the effectiveness of your search queries.</span></span>
  
<span data-ttu-id="43114-196">您也可以將搜尋統計資料和關鍵字統計資料下載至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="43114-196">You can also download the search statistics and keyword statistics to a CSV file.</span></span> <span data-ttu-id="43114-197">如此可讓您使用 Excel 中的篩選和排序功能來比較結果，並為您的搜尋結果準備報告。</span><span class="sxs-lookup"><span data-stu-id="43114-197">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
<span data-ttu-id="43114-198">若要檢視搜尋統計資料：</span><span class="sxs-lookup"><span data-stu-id="43114-198">To view search statistics:</span></span>
  
1. <span data-ttu-id="43114-199">在 **[內容搜尋]** 頁面上，按一下 **[開啟]**，然後按一下您想要檢視其統計資料的搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-199">On the **Content search** page, click **Open** and then click the search that you want to view the statistic for.</span></span> 
    
2. <span data-ttu-id="43114-200">在飛出視窗頁面上，按一下 **[開啟查詢]**。</span><span class="sxs-lookup"><span data-stu-id="43114-200">On the flyout page, click **Open query**.</span></span> 
    
3. <span data-ttu-id="43114-201">在 **[個別結果]** 下拉式清單中，按一下 **[搜尋統計資料]**。</span><span class="sxs-lookup"><span data-stu-id="43114-201">In the **Individual results** drop down list, click **Search statistics**.</span></span>
    
4. <span data-ttu-id="43114-202">在 **[類型]** 下拉式清單中，視您想要檢視的搜尋統計資料而定，按一下下列其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="43114-202">In the **Type** drop down list, click one of the following options depending on the search statistics you want to view.</span></span> 
    
  - <span data-ttu-id="43114-203">**摘要：** 針對所搜尋的每個內容位置類型，顯示其統計資料。</span><span class="sxs-lookup"><span data-stu-id="43114-203">**Summary:** Displays statistics for each type of content locations searched.</span></span> <span data-ttu-id="43114-204">這包括包含的項目符合搜尋查詢的內容位置的數量，以及搜尋結果項目的總數量和大小。</span><span class="sxs-lookup"><span data-stu-id="43114-204">This contents the number of content locations that contained items that matched the search query, and the total number and size of search result items.</span></span> <span data-ttu-id="43114-205">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="43114-205">This is the default setting.</span></span>
    
  - <span data-ttu-id="43114-206">**查詢：** 顯示搜尋查詢的相關統計資料。</span><span class="sxs-lookup"><span data-stu-id="43114-206">**Queries:** Displays statistics about the search query.</span></span> <span data-ttu-id="43114-207">這包括查詢統計資料所適用的內容位置類型、適用的搜尋查詢統計資料部分 (請注意，**主要**代表整個搜尋查詢)、包含符合搜尋查詢項目的內容位置的數量，以及所找到符合搜尋查詢項目的總數量和大小 (在指定的內容位置中)。</span><span class="sxs-lookup"><span data-stu-id="43114-207">This includes the type of content location the query statistics are applicable to, part of the search query the statistics are applicable to (note that **Primary** indicates the entire search query), the number of the content locations that contain items that match the search query, and the total number and size and items that were found (in the specified content location) that match the search query.</span></span> <span data-ttu-id="43114-208">未編製索引項目的統計資料 (也稱為*部分編製索引的項目*) 也會顯示。</span><span class="sxs-lookup"><span data-stu-id="43114-208">Statistics for unindexed items (also called *partially indexed items*) are also displayed.</span></span> <span data-ttu-id="43114-209">不過，統計資料中只會包含來自信箱的部分編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="43114-209">However, only partially indexed items from mailboxes are included in the statistics.</span></span> <span data-ttu-id="43114-210">統計資料中不會包括來自 SharePoint 和 OneDrive 的部分編製索引項目。</span><span class="sxs-lookup"><span data-stu-id="43114-210">Partially indexed items from SharePoint and OneDrive are not included in the statistics.</span></span>
    
  - <span data-ttu-id="43114-211">**熱門位置：** 顯示每個內容位置中符合搜尋查詢的項目數量的相關統計資料。</span><span class="sxs-lookup"><span data-stu-id="43114-211">**Top locations:** Displays statistics about the number of items that match the search query in each content location.</span></span> <span data-ttu-id="43114-212">會顯示前 1,000 個位置。</span><span class="sxs-lookup"><span data-stu-id="43114-212">The top 1,000 locations are displayed.</span></span>
    
<span data-ttu-id="43114-213">如需搜尋統計資料的更詳細資訊，請參閱[檢視內容搜尋結果的關鍵字統計資料](view-keyword-statistics-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="43114-213">For more detailed information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>
  
  
## <a name="export-search-results"></a><span data-ttu-id="43114-214">匯出搜尋結果</span><span class="sxs-lookup"><span data-stu-id="43114-214">Export search results</span></span>

<span data-ttu-id="43114-215">搜尋執行成功之後，您可以將搜尋結果匯出到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="43114-215">After a search is successfully run, you can export the search results to a local computer.</span></span> <span data-ttu-id="43114-216">當您匯出電子郵件結果時，其會以 PST 檔案或以個別郵件 (.msg files) 形式下載到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="43114-216">When you export email results, they can be downloaded to your computer as PST files or as individual messages (.msg files).</span></span> <span data-ttu-id="43114-217">從 SharePoint 和 OneDrive 網站匯出內容時，會匯出原生 Office 文件的副本。</span><span class="sxs-lookup"><span data-stu-id="43114-217">When you export content from SharePoint and OneDrive sites, copies of native Office documents are exported.</span></span> <span data-ttu-id="43114-218">匯出的搜尋結果中還有其他文件和報告。</span><span class="sxs-lookup"><span data-stu-id="43114-218">There are also other documents and reports that are included with the exported search results.</span></span> <span data-ttu-id="43114-219">您也可以匯出搜尋結果報告，而非實際的項目。</span><span class="sxs-lookup"><span data-stu-id="43114-219">You can also export the search results report and not the actual items.</span></span>
  
<span data-ttu-id="43114-220">若要匯出搜尋結果：</span><span class="sxs-lookup"><span data-stu-id="43114-220">To export search results:</span></span>
  
1. <span data-ttu-id="43114-221">在 **[內容搜尋]** 頁面上，按一下您想要匯出其結果的搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-221">On the **Content search** page, click the search that you want to export the search results for.</span></span> 
    
2. <span data-ttu-id="43114-222">在飛出視窗頁面上，按一下 [![匯出搜尋結果圖示](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) 其他]\*\*\*\*，然後按一下 **[匯出結果]**。</span><span class="sxs-lookup"><span data-stu-id="43114-222">On the flyout page, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then click **Export results**.</span></span> <span data-ttu-id="43114-223">您也可以匯出搜尋結果報告。</span><span class="sxs-lookup"><span data-stu-id="43114-223">You can also export a search results report.</span></span>
    
3. <span data-ttu-id="43114-224">完成 **[匯出結果]** 飛出視窗頁面上的區段。</span><span class="sxs-lookup"><span data-stu-id="43114-224">Complete the sections on the **Export results** fly out page.</span></span> <span data-ttu-id="43114-225">務必使用捲軸來檢視所有的匯出選項。</span><span class="sxs-lookup"><span data-stu-id="43114-225">Be sure to use the scroll bar to view all export options.</span></span> 
    
<span data-ttu-id="43114-226">如需詳細指示和疑難排解提示，請參閱：</span><span class="sxs-lookup"><span data-stu-id="43114-226">For more detailed instructions and troubleshooting tips, see:</span></span>
  
- [<span data-ttu-id="43114-227">匯出內容搜尋結果</span><span class="sxs-lookup"><span data-stu-id="43114-227">Export Content Search results</span></span>](export-search-results.md)
    
- [<span data-ttu-id="43114-228">匯出內容搜尋報告</span><span class="sxs-lookup"><span data-stu-id="43114-228">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
  
## <a name="more-information-about-content-search"></a><span data-ttu-id="43114-229">有關內容搜尋的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="43114-229">More information about content search</span></span>

<span data-ttu-id="43114-230">如需有關內容搜尋的詳細資訊，請參閱以下小節。</span><span class="sxs-lookup"><span data-stu-id="43114-230">See the following sections for more information about content searches.</span></span>
  
[<span data-ttu-id="43114-231">內容搜尋限制</span><span class="sxs-lookup"><span data-stu-id="43114-231">Content search limits</span></span>](#content-search-limits)
  
[<span data-ttu-id="43114-232">建立搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="43114-232">Building a search query</span></span>](#building-a-search-query)
  
[<span data-ttu-id="43114-233">搜尋 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="43114-233">Searching OneDrive accounts</span></span>](#searching-onedrive-accounts)
  
[<span data-ttu-id="43114-234">搜尋 Microsoft Teams 和 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="43114-234">Searching Microsoft Teams and Office 365 Groups</span></span>](#searching-microsoft-teams-and-office-365-groups)
  
[<span data-ttu-id="43114-235">搜尋非作用中信箱</span><span class="sxs-lookup"><span data-stu-id="43114-235">Searching inactive mailboxes</span></span>](#searching-inactive-mailboxes)
  
[<span data-ttu-id="43114-236">搜尋連線中斷或取消授權的信箱</span><span class="sxs-lookup"><span data-stu-id="43114-236">Searching disconnected or de-licensed mailboxes</span></span>](#searching-disconnected-or-de-licensed-mailboxes)

[<span data-ttu-id="43114-237">預覽搜尋結果</span><span class="sxs-lookup"><span data-stu-id="43114-237">Previewing search results</span></span>](#previewing-search-results)
  
[<span data-ttu-id="43114-238">部分編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="43114-238">Partially indexed items</span></span>](#partially-indexed-items)

[<span data-ttu-id="43114-239">在 SharePoint 多地理位置環境中搜尋內容</span><span class="sxs-lookup"><span data-stu-id="43114-239">Searching for content in a SharePoint Multi-Geo environment</span></span>](#searching-for-content-in-a-sharepoint-multi-geo-environment)
  
### <a name="content-search-limits"></a><span data-ttu-id="43114-240">內容搜尋限制</span><span class="sxs-lookup"><span data-stu-id="43114-240">Content search limits</span></span>

- <span data-ttu-id="43114-241">如需內容搜尋功能適用限制的說明，請參閱[內容搜尋的限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="43114-241">For a description of the limits that are applied to the Content Search feature, see [Limits for Content Search](limits-for-content-search.md).</span></span>
    
- <span data-ttu-id="43114-242">Microsoft 會收集所有 Office 365 組織執行的內容搜尋的效能資訊。</span><span class="sxs-lookup"><span data-stu-id="43114-242">Microsoft collects performance information for Content Searches run by all Office 365 organizations.</span></span> <span data-ttu-id="43114-243">雖然搜尋查詢的複雜性可能會影響搜尋時間，會影響搜尋所需時間的最大因素是搜尋的信箱數量。</span><span class="sxs-lookup"><span data-stu-id="43114-243">While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched.</span></span> <span data-ttu-id="43114-244">雖然 Microsoft 不對搜尋時間提供服務等級協定，下表根據搜尋中包含的信箱數量列出內容搜尋的平均搜尋時間。</span><span class="sxs-lookup"><span data-stu-id="43114-244">Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for a Content Search based on the number of mailboxes included in the search.</span></span>
    
|<span data-ttu-id="43114-245">**信箱數目**</span><span class="sxs-lookup"><span data-stu-id="43114-245">**Number of mailboxes**</span></span>|<span data-ttu-id="43114-246">**平均搜尋時間**</span><span class="sxs-lookup"><span data-stu-id="43114-246">**Average search time**</span></span>|
|:-----|:-----|
|<span data-ttu-id="43114-247">100</span><span class="sxs-lookup"><span data-stu-id="43114-247">100</span></span>  <br/> |<span data-ttu-id="43114-248">30 秒</span><span class="sxs-lookup"><span data-stu-id="43114-248">30 seconds</span></span>  <br/> |
|<span data-ttu-id="43114-249">1,000</span><span class="sxs-lookup"><span data-stu-id="43114-249">1,000</span></span>  <br/> |<span data-ttu-id="43114-250">45 秒</span><span class="sxs-lookup"><span data-stu-id="43114-250">45 seconds</span></span>  <br/> |
|<span data-ttu-id="43114-251">10,000</span><span class="sxs-lookup"><span data-stu-id="43114-251">10,000</span></span>  <br/> |<span data-ttu-id="43114-252">4 分鐘</span><span class="sxs-lookup"><span data-stu-id="43114-252">4 minutes</span></span>  <br/> |
|<span data-ttu-id="43114-253">25,000</span><span class="sxs-lookup"><span data-stu-id="43114-253">25,000</span></span>  <br/> |<span data-ttu-id="43114-254">10 分鐘</span><span class="sxs-lookup"><span data-stu-id="43114-254">10 minutes</span></span>  <br/> |
|<span data-ttu-id="43114-255">50,000</span><span class="sxs-lookup"><span data-stu-id="43114-255">50,000</span></span>  <br/> |<span data-ttu-id="43114-256">20 分鐘</span><span class="sxs-lookup"><span data-stu-id="43114-256">20 minutes</span></span>  <br/> |
|<span data-ttu-id="43114-257">100,000</span><span class="sxs-lookup"><span data-stu-id="43114-257">100,000</span></span>  <br/> |<span data-ttu-id="43114-258">25 分鐘</span><span class="sxs-lookup"><span data-stu-id="43114-258">25 minutes</span></span>  <br/> |
  
### <a name="building-a-search-query"></a><span data-ttu-id="43114-259">建立搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="43114-259">Building a search query</span></span>

<span data-ttu-id="43114-260">如需建立搜尋查詢、使用布林搜尋運算子和搜尋條件，以及搜尋與組織外部使用者共用的機密資訊類型和內容的詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="43114-260">For detailed information about creating a search query, using Boolean search operators and search conditions, and searching for sensitive information types and content shared with users outside your organization, see [Keyword queries and search conditions for Content Search ](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="43114-261">使用關鍵字清單建立搜尋查詢時，請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="43114-261">Keep the following things in mind when using the keyword list to create a search query.</span></span>
  
- <span data-ttu-id="43114-262">您必須選取 **[顯示關鍵字清單]** 核取方塊，然後在不同的列輸入每個關鍵字來建立搜尋查詢，其中每個列的關鍵字 (或關鍵字字詞) 是用 **OR** 運算子連接。</span><span class="sxs-lookup"><span data-stu-id="43114-262">You have to select the **Show keyword list** checkbox and then type each keyword in a separate row to create a search query where the keywords (or keyword phrases) in each row are connected by the **OR** operator.</span></span> <span data-ttu-id="43114-263">如果您在輸入關鍵字之後，於關鍵字方塊中貼上關鍵字清單或按下 **Enter** 鍵，就不會使用 **OR** 運算子將其連接。</span><span class="sxs-lookup"><span data-stu-id="43114-263">If you paste a list of keywords in the keyword box or press the **Enter** key after typing a keyword, they won't be connected by the **OR** operator.</span></span> <span data-ttu-id="43114-264">以下是如何新增關鍵字清單的不正確和正確範例。</span><span class="sxs-lookup"><span data-stu-id="43114-264">Here are incorrect and correct examples of how to add a list of keywords.</span></span> 
    
    <span data-ttu-id="43114-265">**不正確**</span><span class="sxs-lookup"><span data-stu-id="43114-265">**Incorrect**</span></span>
    
    ![設定關鍵字清單格式的方式不正確 (在關鍵字方塊中貼上清單)](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    <span data-ttu-id="43114-267">**正確**</span><span class="sxs-lookup"><span data-stu-id="43114-267">**Correct**</span></span>
    
    ![設定關鍵字清單格式的方式正確 (選取核取方塊，然後貼上清單)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- <span data-ttu-id="43114-269">您也可以在 Excel 檔案或純文字檔案中準備關鍵字或關鍵字片語的清單，然後將您的清單複製並貼入關鍵字清單中。</span><span class="sxs-lookup"><span data-stu-id="43114-269">You can also prepare a list of keywords or keyword phrases in an Excel file or a plain text file, and then copy and paste your list into the keyword list.</span></span> <span data-ttu-id="43114-270">若要這麼做，您必須選取 **[顯示關鍵字清單]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="43114-270">To do this, you have to select the **Show keyword list** check box.</span></span> <span data-ttu-id="43114-271">然後在關鍵字清單的第一列按一下，並貼上您的清單。</span><span class="sxs-lookup"><span data-stu-id="43114-271">Then, click the first row in the keyword list and paste your list.</span></span> <span data-ttu-id="43114-272">來自 Excel 或文字檔案的每一行都會貼到關鍵字清單中的不同列。</span><span class="sxs-lookup"><span data-stu-id="43114-272">Each line from the Excel or text file is pasted into separate row in the keyword list.</span></span> 
    
- <span data-ttu-id="43114-273">使用關鍵字清單建立查詢之後，最好先驗證搜尋查詢語法，以讓該搜尋查詢成為您想要的查詢。</span><span class="sxs-lookup"><span data-stu-id="43114-273">After you create a query using the keyword list, it's a good idea to verify the search query syntax to make the search query is what you intended.</span></span> <span data-ttu-id="43114-274">在詳細資料窗格的 **[查詢]** 下顯示的搜尋查詢中，關鍵字使用文字 **(c:s)** 分隔。</span><span class="sxs-lookup"><span data-stu-id="43114-274">In the search query that's displayed under **Query** in the details pane, the keywords are separated by the text **(c:s)**.</span></span> <span data-ttu-id="43114-275">這表示關鍵字是使用與 **OR** 運算子類似功能的邏輯運算子連接。</span><span class="sxs-lookup"><span data-stu-id="43114-275">This indicates that the keywords are connected by a logical operator similar in functionality to the **OR** operator.</span></span> <span data-ttu-id="43114-276">同樣地，如果您的搜尋查詢中包含條件，關鍵字與條件以文字 **(c:c)** 分隔。</span><span class="sxs-lookup"><span data-stu-id="43114-276">Similarly, if your search query includes conditions, the keywords and the conditions are separated by the text **(c:c)**.</span></span> <span data-ttu-id="43114-277">這表示關鍵字是使用與 **AND** 運算子類似功能的邏輯運算子與條件連接。</span><span class="sxs-lookup"><span data-stu-id="43114-277">This indicates that the keywords are connected to the conditions with a logical operator similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="43114-278">以下是使用關鍵字清單與條件時產生的搜尋查詢的範例 (顯示在 [詳細資料] 窗格中)。</span><span class="sxs-lookup"><span data-stu-id="43114-278">Here's an example of the search query (displayed in the Details pane) that results when using the keyword list and a condition.</span></span> 
    
    ![使用關鍵字清單與條件時建立的查詢範例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- <span data-ttu-id="43114-280">執行內容搜尋時，Office 365 會自動檢查您的搜尋查詢中是否有不受支援的字元，以及可能未大寫的布林值運算子。</span><span class="sxs-lookup"><span data-stu-id="43114-280">When you run a content search, Office 365 automatically checks your search query for unsupported characters and for Boolean operators that may not be capitalized.</span></span> <span data-ttu-id="43114-281">不支援的字元通常會隱藏起來，且通常會導致搜尋錯誤或傳回非預期的結果。</span><span class="sxs-lookup"><span data-stu-id="43114-281">Unsupported characters are often hidden and typically cause a search error or return unintended results.</span></span> <span data-ttu-id="43114-282">如需所檢查不受支援字元的詳細資訊，請參閱[檢查您的內容搜尋查詢是否有錯誤](check-your-content-search-query-for-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="43114-282">For more information about the unsupported characters that are checked, see [Check your Content Search query for errors](check-your-content-search-query-for-errors.md).</span></span>
    
- <span data-ttu-id="43114-283">如果您有包含非英文字元 (例如中文字元) 關鍵字的搜尋查詢時，您可以按一下 **[查詢語言-國家/地區]**![內容搜尋中的 [查詢語言-國家/地區] 圖示](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png)，然後選取搜尋的語言-國家/地區文化特性代碼值。</span><span class="sxs-lookup"><span data-stu-id="43114-283">If you have a search query that contains keywords for non-English characters (such as Chinese characters), you can click **Query language-country/region**![Query language-country/region icon in Content search](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) and select a language-country culture code value for the search.</span></span> <span data-ttu-id="43114-284">預設的語言-國家/地區為中性。</span><span class="sxs-lookup"><span data-stu-id="43114-284">The default language/region is neutral.</span></span> <span data-ttu-id="43114-285">如何判斷您是否需要變更內容搜尋的語言設定？</span><span class="sxs-lookup"><span data-stu-id="43114-285">How can you tell if you need to change the language setting for a content search?</span></span> <span data-ttu-id="43114-286">如果您確定您要搜尋的內容位置包含非英文字元，但搜尋卻未傳回任何結果，這可能是語言設定所造成。</span><span class="sxs-lookup"><span data-stu-id="43114-286">If you're certain content locations contain the non-English characters you're searching for, but the search returns no results, the language setting may be the cause.</span></span> 
  
### <a name="searching-onedrive-accounts"></a><span data-ttu-id="43114-287">搜尋 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="43114-287">Searching OneDrive accounts</span></span>

- <span data-ttu-id="43114-288">若要收集組織中 OneDrive 網站的 URL 清單，請參閱[建立組織中所有 OneDrive 位置的清單](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。</span><span class="sxs-lookup"><span data-stu-id="43114-288">To collect a list of the URLs for the OneDrive sites in your organization, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a).</span></span> <span data-ttu-id="43114-289">本文章中的這個指令碼會建立文字檔案，其中包含所有 OneDrive 網站的清單。</span><span class="sxs-lookup"><span data-stu-id="43114-289">This script in this article creates a text file that contains a list of all OneDrive sites.</span></span> <span data-ttu-id="43114-290">若要執行此指令碼，您必須安裝並使用 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="43114-290">To run this script, you have to install and use the SharePoint Online Management Shell.</span></span> <span data-ttu-id="43114-291">請務必將您組織 MySite 網域的 URL 附加至您要搜尋的每個 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="43114-291">Be sure to append the URL for your organization's MySite domain to each OneDrive site that you want to search.</span></span> <span data-ttu-id="43114-292">這是包含您所有 OneDrive 的網域；例如，`https://contoso-my.sharepoint.com`。</span><span class="sxs-lookup"><span data-stu-id="43114-292">This is the domain that contains all your OneDrive; for example,  `https://contoso-my.sharepoint.com`.</span></span> <span data-ttu-id="43114-293">以下是使用者 OneDrive 網站的 URL 範例：`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。</span><span class="sxs-lookup"><span data-stu-id="43114-293">Here's an example of a URL for a user's OneDrive site:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.</span></span>
    
    <span data-ttu-id="43114-294">在人員的使用者主體名稱 (UPN) 變更的少數情況下，其 OneDrive 位置的 URL 將會變更以納入新的 UPN。</span><span class="sxs-lookup"><span data-stu-id="43114-294">In the rare case of a person's user principal name (UPN) being changed, the URL for their OneDrive location is changed to incorporate the new UPN.</span></span> <span data-ttu-id="43114-295">如果發生這種情況，您必須透過新增使用者的新 OneDrive URL 並移除舊 URL 來修改內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-295">If this happens, you have to modify a content search by adding the user's new OneDrive URL and removing the old one.</span></span>
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a><span data-ttu-id="43114-296">搜尋 Microsoft Teams 和 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="43114-296">Searching Microsoft Teams and Office 365 Groups</span></span>

<span data-ttu-id="43114-297">您可以搜尋與 Office 365 群組或 Microsoft Teams 相關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-297">You can search the mailbox that's associated with an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="43114-298">因為 Office 365 群組上建置於 Microsoft Teams 上，搜尋它們的方式很類似。</span><span class="sxs-lookup"><span data-stu-id="43114-298">Because Microsoft Teams is built on Office 365 Groups, searching them is similar.</span></span> <span data-ttu-id="43114-299">在這兩個情況下，只會搜尋群組或團隊信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-299">In both cases, only the group or team mailbox is searched.</span></span> <span data-ttu-id="43114-300">不會搜尋群組或團隊成員的信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-300">The mailboxes of the group or team members aren't searched.</span></span> <span data-ttu-id="43114-301">若要進行搜尋，您必須特別將它們新增至搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-301">To search them, you have to specifically add them to the search.</span></span>
  
<span data-ttu-id="43114-302">搜尋 Microsoft Teams 和 Office 365 群組中的內容時，請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="43114-302">Keep the following things in mind when searching for content in Microsoft Teams and Office 365 Groups.</span></span>
  
- <span data-ttu-id="43114-303">若要搜尋位於 Teams 和 Office 365 群組中的內容，您必須指定與團隊或群組相關聯的信箱和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="43114-303">To search for content located in Teams and Office 365 Groups, you have to specify the mailbox and SharePoint site that are associated with a team or group.</span></span>
    
- <span data-ttu-id="43114-304">在 Exchange Online 中執行 **Get-UnifiedGroup** Cmdlet，以檢視團隊或 Office 365 群組的內容。</span><span class="sxs-lookup"><span data-stu-id="43114-304">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for a team or an Office 365 Group.</span></span> <span data-ttu-id="43114-305">這是取得與團隊或群組相關聯的網站 URL 的絕佳方法。</span><span class="sxs-lookup"><span data-stu-id="43114-305">This is a good way to get the URL for the site that's associated with a team or a group.</span></span> <span data-ttu-id="43114-306">例如，下列命令會顯示名為「資深領導團隊」的 Office 365 群組的所選屬性：</span><span class="sxs-lookup"><span data-stu-id="43114-306">For example, the following command displays selected properties for an Office 365 Group named Senior Leadership Team:</span></span> 
    
  ```text
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  ```

    > [!NOTE]
    > <span data-ttu-id="43114-307">若要執行 **Get-UnifiedGroup** Cmdlet，您必須獲指派 Exchange Online 中的「僅檢視收件者」角色或者為獲指派「僅檢視收件者」角色之角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="43114-307">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="43114-308">搜尋使用者的信箱時，不會搜尋使用者所隸屬的任何團隊或 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="43114-308">When a user's mailbox is searched, any team or Office 365 Group that the user is a member of won't be searched.</span></span> <span data-ttu-id="43114-309">同樣地，當您搜尋團隊或 Office 365 群組時，只會搜尋您指定的群組信箱及群組網站。</span><span class="sxs-lookup"><span data-stu-id="43114-309">Similarly, when you search a team or an Office 365 Group, only the group mailbox and group site that you specify is searched.</span></span> <span data-ttu-id="43114-310">不會搜尋群組成員的信箱和商務用 OneDrive 帳戶，除非您明確地將它們新增至搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-310">The mailboxes and OneDrive for Business accounts of group members aren't searched unless you explicitly add them to the search.</span></span>
    
- <span data-ttu-id="43114-311">若要取得團隊或 Office 365 群組的成員清單，您可以在 Microsoft 365 系統管理中心的 **[常用] \> [群組]** 頁面上檢視內容。</span><span class="sxs-lookup"><span data-stu-id="43114-311">To get a list of the members of a team or an Office 365 Group, you can view the properties on the **Home \> Groups** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="43114-312">或者，您可以在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="43114-312">Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 
    
  ```powershell
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > <span data-ttu-id="43114-313">若要執行 **Get-UnifiedGroupLinks** Cmdlet，您必須獲指派 Exchange Online 中的「僅檢視收件者」角色或者為獲指派「僅檢視收件者」角色之角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="43114-313">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="43114-314">屬於 Teams 頻道一部分的交談會儲存在與團隊相關聯的信箱中。</span><span class="sxs-lookup"><span data-stu-id="43114-314">Conversations that are part of a Teams channel are stored in the mailbox that's associated with the team.</span></span> <span data-ttu-id="43114-315">同樣地，團隊成員在頻道中共用的檔案會儲存在團隊的 SharePoint 網站上。</span><span class="sxs-lookup"><span data-stu-id="43114-315">Similarly, files that team members share in a channel are stored on the team's SharePoint site.</span></span> <span data-ttu-id="43114-316">因此，您必須將團隊信箱和 SharePoint 網站新增為內容位置，才能搜尋頻道中的交談和檔案。</span><span class="sxs-lookup"><span data-stu-id="43114-316">Therefore, you have to add the team mailbox and SharePoint site as a content location to search conversations and files in a channel.</span></span>
    
- <span data-ttu-id="43114-317">或者，屬於 Teams 中聊天清單的交談會儲存在參與聊天的使用者的 Exchange Online 信箱中。</span><span class="sxs-lookup"><span data-stu-id="43114-317">Alternatively, conversations that are part of the Chat list in Teams are stored in the Exchange Online mailbox of the users who participate in the chat.</span></span> <span data-ttu-id="43114-318">而使用者在聊天交談中共用的檔案會儲存在共用檔案的使用者的商務用 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="43114-318">And files that a user shares in Chat conversations are stored in the OneDrive for Business account of the user who shares the file.</span></span> <span data-ttu-id="43114-319">因此，您必須將個別使用者信箱和商務用 OneDrive 帳戶新增為內容位置，才能搜尋聊天清單中的交談和檔案。</span><span class="sxs-lookup"><span data-stu-id="43114-319">Therefore, you have to add the individual user mailboxes and OneDrive for Business accounts as content locations to search conversations and files in the Chat list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="43114-320">在 Exchange 混合式部署中，具有內部部署信箱的使用者可能會參與屬於 Teams 中聊天清單的交談。</span><span class="sxs-lookup"><span data-stu-id="43114-320">In an Exchange hybrid deployment, users with an on-premises mailbox might participate in conversations that are part of the Chat list in Teams.</span></span> <span data-ttu-id="43114-321">在此情況下，來自這些交談的內容也可供搜尋，因為針對具有內部部署信箱的使用者，這些內容會儲存到雲端式存放區域 (稱為*內部部署使用者的雲端式信箱*)。</span><span class="sxs-lookup"><span data-stu-id="43114-321">In this case, content from these conversations is also searchable because it's saved to a cloud-based storage area (called a *cloud-based mailbox for on-premises users*) for users who have an on-premises mailbox.</span></span> <span data-ttu-id="43114-322">如需詳細資訊，請參閱[在 Office 365 中搜尋內部部署使用者的雲端式信箱](search-cloud-based-mailboxes-for-on-premises-users.md)。</span><span class="sxs-lookup"><span data-stu-id="43114-322">For more information, see [Searching cloud-based mailboxes for on-premises users in Office 365](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
  
- <span data-ttu-id="43114-323">每個團隊或團隊頻道包含一個 Wiki，用於記筆記和進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="43114-323">Every team or team channel contains a Wiki for note-taking and collaboration.</span></span> <span data-ttu-id="43114-324">Wiki 的內容會自動儲存至 .mht 格式的檔案中。</span><span class="sxs-lookup"><span data-stu-id="43114-324">The Wiki content is automatically saved to a file with a .mht format.</span></span> <span data-ttu-id="43114-325">此檔案會儲存在團隊 SharePoint 網站上的 Teams Wiki 資料文件庫中。</span><span class="sxs-lookup"><span data-stu-id="43114-325">This file is stored in the Teams Wiki Data document library on the team's SharePoint site.</span></span> <span data-ttu-id="43114-326">您可以使用「內容搜尋」工具來搜尋 Wiki，方法是將團隊的 SharePoint 網站指定為要搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="43114-326">You can use the Content Search tool to search the Wiki by specifying the team's SharePoint site as the content location to search.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="43114-327">搜尋團隊或頻道的 Wiki 功能 (搜尋團隊的 SharePoint 網站時) 是在 2017 年 6 月 22 日推出。</span><span class="sxs-lookup"><span data-stu-id="43114-327">The capability to search the Wiki for a team or channel (when you search the team's SharePoint site) was released on June 22, 2017.</span></span> <span data-ttu-id="43114-328">在該日期當日或之後儲存或更新的 Wiki 頁面可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-328">Wiki pages that were saved or updated on that date or after are available to be searched.</span></span> <span data-ttu-id="43114-329">在該日期之前儲存或更新的 Wiki 頁面無法供搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-329">Wiki pages last saved or updated before that date aren't available for search.</span></span> 
 
- <span data-ttu-id="43114-330">Teams 頻道中的會議及電話的摘要資訊也會儲存在撥入會議或電話使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="43114-330">Summary information for meetings and calls in a Teams channel are also stored in the mailboxes of users who dialed into the meeting or call.</span></span> <span data-ttu-id="43114-331">這表示您可以使用內容搜尋來搜尋這些摘要記錄。</span><span class="sxs-lookup"><span data-stu-id="43114-331">This means you can use Content Search to search these summary records.</span></span> <span data-ttu-id="43114-332">摘要資訊包含：</span><span class="sxs-lookup"><span data-stu-id="43114-332">Summary information includes:</span></span> 
  
  - <span data-ttu-id="43114-333">會議或通話的日期、開始時間、結束時間和持續期間</span><span class="sxs-lookup"><span data-stu-id="43114-333">Date, start time, end time, and duration of a meeting or call</span></span>

  - <span data-ttu-id="43114-334">每個參與者加入或離開會議或通話的日期及時間</span><span class="sxs-lookup"><span data-stu-id="43114-334">The date and time when each participant joined or left the meeting or call</span></span>

  - <span data-ttu-id="43114-335">傳送到語音信箱的通話</span><span class="sxs-lookup"><span data-stu-id="43114-335">Calls sent to voice mail</span></span>

  - <span data-ttu-id="43114-336">未接來電或無人接聽的來電</span><span class="sxs-lookup"><span data-stu-id="43114-336">Missed or unanswered calls</span></span>

  - <span data-ttu-id="43114-337">來電轉接，以兩個不同通話的形式呈現</span><span class="sxs-lookup"><span data-stu-id="43114-337">Call transfers, which are represented as two separate calls</span></span>

  <span data-ttu-id="43114-338">可能需要最長達 8 小時的時間，會議和通話摘要記錄才可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-338">It can take up to 8 hours for meeting and call summary records to be available to be searched.</span></span>

  <span data-ttu-id="43114-339">在搜尋結果中，會在 **[類型]** 欄位中將會議摘要識別為 **[會議]**，以及將通話摘要識別為 **[通話]**。</span><span class="sxs-lookup"><span data-stu-id="43114-339">In the search results, meeting summaries are identified as **Meeting** in the **Type field**, and call summaries are identified as **Call**.</span></span> <span data-ttu-id="43114-340">此外，屬於 Teams 頻道和 1xN 聊天的交談，會在 **[類型]** 欄位中識別為 **IM**。</span><span class="sxs-lookup"><span data-stu-id="43114-340">Also, conversations that are part of a Teams channel and 1xN chats are identified as **IM** in the **Type** field.</span></span>
  
  ![Teams 會議、通話和 1xN 聊天都可在 [類型] 欄位中識別](media/O365-ContentSearch-Teams-MessageKind.png)

- <span data-ttu-id="43114-342">您可以使用 **Kind** 電子郵件屬性或 **[郵件類型]** 搜尋條件來搜尋 Teams 中的專屬內容。</span><span class="sxs-lookup"><span data-stu-id="43114-342">You can use the **Kind** email property or the **Message kind** search condition to search specifically for content in Teams.</span></span> 
  
  - <span data-ttu-id="43114-343">若要在關鍵字搜尋查詢中使用 **Kind** 屬性，請在搜尋查詢的 **[關鍵字]** 方塊中輸入 `kind:microsoftteams`。</span><span class="sxs-lookup"><span data-stu-id="43114-343">To use the **Kind** property as part of the keyword search query, in the **Keywords** box of a search query, type `kind:microsoftteams`.</span></span>

    ![在關鍵字方塊中使用 kind:microsoftteams](media/O365-ContentSearch-Teams-Keywords.png)
  
  - <span data-ttu-id="43114-345">若要使用搜尋條件，請新增 **[郵件類型]** 條件，然後使用 `microsoftteams` 值。</span><span class="sxs-lookup"><span data-stu-id="43114-345">To use a search condition, add the **Message kind** condition and use the value `microsoftteams`.</span></span> 

    ![使用郵件類型條件搭配 microsoftteams 值。](media/O365-ContentSearch-Teams-MessageKindCondition.png)

<span data-ttu-id="43114-347">條件會使用 **AND** 運算子以邏輯方式連接至關鍵字查詢。</span><span class="sxs-lookup"><span data-stu-id="43114-347">Conditions are logically connected to the keyword query by the **AND** operator.</span></span> <span data-ttu-id="43114-348">這表示項目必須同時符合關鍵字查詢和搜尋條件，才能在搜尋結果中傳回。</span><span class="sxs-lookup"><span data-stu-id="43114-348">That means an item must match both the keyword query and the search condition to be returned in the search results.</span></span> <span data-ttu-id="43114-349">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)中的「使用條件的指導方針」小節。</span><span class="sxs-lookup"><span data-stu-id="43114-349">For more information, see the "Guidelines for using conditions" section in [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)</span></span>
  
### <a name="searching-inactive-mailboxes"></a><span data-ttu-id="43114-350">搜尋非作用中信箱</span><span class="sxs-lookup"><span data-stu-id="43114-350">Searching inactive mailboxes</span></span>

<span data-ttu-id="43114-351">您可以在內容搜尋中搜尋非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-351">You can search inactive mailboxes in a content search.</span></span> <span data-ttu-id="43114-352">若要取得組織中非作用中信箱的清單，請在 Exchange Online PowerShell 中執行命令 `Get-Mailbox -InactiveMailboxOnly`。</span><span class="sxs-lookup"><span data-stu-id="43114-352">To get a list of the inactive mailboxes in your organization, run the command  `Get-Mailbox -InactiveMailboxOnly` in Exchange Online PowerShell.</span></span> <span data-ttu-id="43114-353">或者，您可以移至安全性與合規性中心中的 **[資訊控管]** \> **[保留]**，然後按一下 **[更多]** ![[瀏覽列省略符號]](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **[非作用中信箱]**。</span><span class="sxs-lookup"><span data-stu-id="43114-353">Alternatively, you can go to **Data governance** \> **Retention** in the Security & Compliance Center, and then click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inactive mailboxes**.</span></span>
  
<span data-ttu-id="43114-354">搜尋非作用中信箱時，請注意以下幾點。</span><span class="sxs-lookup"><span data-stu-id="43114-354">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>

- <span data-ttu-id="43114-355">如果現有內容搜尋包含使用者信箱，且該信箱設定為非作用中，在信箱成為非作用中之後，當您重新執行搜尋時，內容搜尋會繼續搜尋非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-355">If an existing content search includes a user mailbox and that mailbox is made inactive, the content search will continue to search the inactive mailbox when you rerun the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="43114-356">有時候，使用者的作用中信箱及非作用中信箱可能擁有相同的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="43114-356">Sometimes a user may have an active mailbox and an inactive mailbox that have the same SMTP address.</span></span> <span data-ttu-id="43114-357">在此情況下，僅會搜尋您選取做為內容搜尋位置的特定信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-357">In this case, only the specific mailbox that you select as a location for a content search is searched.</span></span> <span data-ttu-id="43114-358">換句話說，如果您將使用者的信箱新增至搜尋，您無法假設會同時搜尋其作用中和非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-358">In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes are searched.</span></span> <span data-ttu-id="43114-359">只會搜尋您明確地新增至搜尋的信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-359">Only the mailbox that you explicitly add to the search is searched.</span></span>
    
- <span data-ttu-id="43114-360">您可以使用安全性與合規性中心 PowerShell 來建立內容搜尋，以搜尋非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-360">You can use Security & Compliance Center PowerShell to create a content search to search an inactive mailbox.</span></span> <span data-ttu-id="43114-361">若要這麼做，您必須將一個句點 (.</span><span class="sxs-lookup"><span data-stu-id="43114-361">To do this, you have to pre-append a period ( .</span></span> <span data-ttu-id="43114-362">) 附加至非作用中信箱的電子郵件地址前端。</span><span class="sxs-lookup"><span data-stu-id="43114-362">) to the email address of the inactive mailbox.</span></span> <span data-ttu-id="43114-363">例如，下列命令會建立內容搜尋，搜尋電子郵件地址為 pavelb@contoso.onmicrosoft.com 的非作用中信箱：</span><span class="sxs-lookup"><span data-stu-id="43114-363">For example, the following command creates a content search that searches an inactive mailbox with the email address pavelb@contoso.onmicrosoft.com:</span></span>

   ``` 
   New-ComplianceSearch -name InactiveMailboxSearch -ExchangeLocation .pavelb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
   ```

- <span data-ttu-id="43114-364">我們強烈建議您避免使用具有相同 SMTP 地址的作用中信箱及非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-364">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address.</span></span> <span data-ttu-id="43114-365">如果您需要重複使用已指派給非作用中信箱的 SMTP 地址，建議您復原非作用中信箱，或將非作用中信箱的內容還原為作用中信箱 (或者作用中信箱的封存)，然後刪除非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-365">If you need to reuse the SMTP address that is assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox.</span></span> <span data-ttu-id="43114-366">如需詳細資訊，請參閱下列其中一個主題：</span><span class="sxs-lookup"><span data-stu-id="43114-366">For more information, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="43114-367">在 Office 365 中復原非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="43114-367">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="43114-368">在 Office 365 中還原非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="43114-368">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="43114-369">在 Office 365 中刪除非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="43114-369">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

### <a name="searching-disconnected-or-de-licensed-mailboxes"></a><span data-ttu-id="43114-370">搜尋連線中斷或取消授權的信箱</span><span class="sxs-lookup"><span data-stu-id="43114-370">Searching disconnected or de-licensed mailboxes</span></span>

<span data-ttu-id="43114-371">如果您從 Office 365 或 Azure Active Directory 中的使用者帳戶移除 Exchange Online 授權 (或整個 Office 365 授權)，該使用者的信箱就會變成 *「連線中斷」* 的信箱。</span><span class="sxs-lookup"><span data-stu-id="43114-371">If the Exchange Online license (or the entire Office 365 license) is removed from a user account in Office 365 or in Azure Active Directory, the user's mailbox becomes a *disconnected* mailbox.</span></span> <span data-ttu-id="43114-372">這表示信箱已不再與使用者帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="43114-372">This means that the mailbox is no longer associated with the user account.</span></span> <span data-ttu-id="43114-373">搜尋中斷連線的信箱時，會發生以下狀況：</span><span class="sxs-lookup"><span data-stu-id="43114-373">Here's what happens when searching disconnected mailboxes:</span></span>

- <span data-ttu-id="43114-374">如果從信箱移除授權，信箱即不再可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-374">If the license is removed from a mailbox, the mailbox is no longer searchable.</span></span> 

- <span data-ttu-id="43114-375">如果現有的內容搜尋包含已移除授權的信箱，如果您重新執行內容搜尋，則不會從已中斷連線的信箱傳回任何搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="43114-375">If an existing content search includes a mailbox in which the license is removed, no search results from the disconnected mailbox will be returned if you rerun the content search.</span></span>

- <span data-ttu-id="43114-376">如果您使用 **New-ComplianceSearch** Cmdlet 來建立內容搜尋，並將中斷連線的信箱指定為要搜尋的 Exchange 內容位置，內容搜尋將不會從已中斷連線的信箱傳回任何搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="43114-376">If you use the **New-ComplianceSearch** cmdlet to create a content search and specify a disconnected mailbox as the Exchange content location to search, the content search won't return any search results from the disconnected mailbox.</span></span>

<span data-ttu-id="43114-377">如果您要保留已中斷連線信箱中的資料，使其可供搜尋，您必須在移除授權之前，先在信箱上放置保留。</span><span class="sxs-lookup"><span data-stu-id="43114-377">If you need to preserve the data in a disconnected mailbox so that it's searchable, you must place a hold on the mailbox before removing the license.</span></span> <span data-ttu-id="43114-378">這麼做會保留資料，並在移除保留之前讓中斷連線的信箱可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-378">This preserves the data and keeps the disconnected mailbox searchable until the hold is removed.</span></span> <span data-ttu-id="43114-379">如需保留的詳細資訊，請參閱[如何找出位於 Exchange Online 信箱的保留類型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="43114-379">For more information about holds, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

### <a name="previewing-search-results"></a><span data-ttu-id="43114-380">預覽搜尋結果</span><span class="sxs-lookup"><span data-stu-id="43114-380">Previewing search results</span></span>

<span data-ttu-id="43114-381">您可以在預覽窗格中預覽支援的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="43114-381">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="43114-382">如果某個檔案類型不受支援，您必須下載檔案的副本到您的本機電腦以便檢視。</span><span class="sxs-lookup"><span data-stu-id="43114-382">If a file type isn't supported, you have to download a copy of the file to your local computer to view it.</span></span> <span data-ttu-id="43114-383">支援下列檔案類型，並且可在搜尋結果窗格中預覽。</span><span class="sxs-lookup"><span data-stu-id="43114-383">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="43114-384">.txt、.html、.mhtml</span><span class="sxs-lookup"><span data-stu-id="43114-384">.txt, .html, .mhtml</span></span>
    
- <span data-ttu-id="43114-385">.eml</span><span class="sxs-lookup"><span data-stu-id="43114-385">.eml</span></span>
    
- <span data-ttu-id="43114-386">.doc、.docx、.docm</span><span class="sxs-lookup"><span data-stu-id="43114-386">.doc, .docx, .docm</span></span>
    
- <span data-ttu-id="43114-387">.pptm、.pptx</span><span class="sxs-lookup"><span data-stu-id="43114-387">.pptm, .pptx</span></span>
    
- <span data-ttu-id="43114-388">.pdf</span><span class="sxs-lookup"><span data-stu-id="43114-388">.pdf</span></span>
    
<span data-ttu-id="43114-389">還支援下列檔案容器類型。</span><span class="sxs-lookup"><span data-stu-id="43114-389">Also, the following file container types are supported.</span></span> <span data-ttu-id="43114-390">您可以在預覽窗格的容器中檢視檔案的清單。</span><span class="sxs-lookup"><span data-stu-id="43114-390">You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="43114-391">.zip</span><span class="sxs-lookup"><span data-stu-id="43114-391">.zip</span></span>
    
- <span data-ttu-id="43114-392">.gzip</span><span class="sxs-lookup"><span data-stu-id="43114-392">.gzip</span></span>
    
### <a name="partially-indexed-items"></a><span data-ttu-id="43114-393">部分編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="43114-393">Partially indexed items</span></span>

- <span data-ttu-id="43114-394">如先前所解說，估計的搜尋結果中會包含信箱中部分編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="43114-394">As previously explained, partially indexed items in mailboxes are included in the estimated search results.</span></span> <span data-ttu-id="43114-395">估計的搜尋結果中不會包括來自 SharePoint 和 OneDrive 的部分編製索引項目。</span><span class="sxs-lookup"><span data-stu-id="43114-395">Partially indexed items from SharePoint and OneDrive aren't included in the estimated search results.</span></span> 
    
- <span data-ttu-id="43114-396">若部分編製索引的項目符合搜尋查詢 (因為其他郵件或文件屬性符合搜尋準則)，則不會將它包含在未編製索引項目的估計數量中。</span><span class="sxs-lookup"><span data-stu-id="43114-396">If a partially indexed item matches the search query (because other message or document properties meet the search criteria), it isn't included in the estimated number of unindexed items.</span></span> <span data-ttu-id="43114-397">若搜尋準則排除了部分編製索引的項目，則不會將它包含在未編製索引項目的估計數量中。</span><span class="sxs-lookup"><span data-stu-id="43114-397">If a partially indexed item is excluded by the search criteria, it isn't included in the estimated number of unindexed items.</span></span> <span data-ttu-id="43114-398">如需詳細資訊，請參閱 [Office 365 的內容搜尋中部分編製索引的項目](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="43114-398">For more information, see [Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md).</span></span>

### <a name="searching-for-content-in-a-sharepoint-multi-geo-environment"></a><span data-ttu-id="43114-399">在 SharePoint 多地理位置環境中搜尋內容</span><span class="sxs-lookup"><span data-stu-id="43114-399">Searching for content in a SharePoint Multi-Geo environment</span></span>

<span data-ttu-id="43114-400">如果電子文件探索管理員需要在 [SharePoint 多地理位置環境](https://go.microsoft.com/fwlink/?linkid=860840)中的不同區域中搜尋 SharePoint 和 OneDrive 中的內容，則需要執行以下操作才能進行：</span><span class="sxs-lookup"><span data-stu-id="43114-400">If it's necessary for an eDiscovery manager to search for content in SharePoint and OneDrive in different regions in a [SharePoint multi-geo environment](https://go.microsoft.com/fwlink/?linkid=860840), then you need to do the following things to make that happen:</span></span>
   
1. <span data-ttu-id="43114-401">為電子文件探索管理員需要搜尋的每個衛星地理位置建立個別的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="43114-401">Create a separate user account for each satellite geo location that the eDiscovery manager needs to search.</span></span> <span data-ttu-id="43114-402">若要在該地理位置中的網站搜尋內容，電子文件探索管理員必須登入您為該位置建立的帳戶，然後再執行內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-402">To search for content in sites in that geo location, the eDiscovery manager must sign in to the account you created for that location and then run a content search.</span></span>

2. <span data-ttu-id="43114-403">為電子文件探索管理員需要搜尋的每個衛星地理位置 (以及相應的使用者帳戶) 建立搜尋權限篩選條件。</span><span class="sxs-lookup"><span data-stu-id="43114-403">Create a search permissions filter for each satellite geo location (and corresponding user account) the eDiscovery manager needs to search.</span></span> <span data-ttu-id="43114-404">當電子文件探索管理員登入與該位置關聯的使用者帳戶時，每一個搜尋權限篩選條件都會將內容搜尋的範圍限制為特定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="43114-404">Each of these search permissions filters limits the scope of the content search to a specific geo location when the eDiscovery manager is signed in to the user account associated with that location.</span></span>
 
> [!TIP]
> <span data-ttu-id="43114-405">在 [[進階電子文件探索]](overview-ediscovery-20.md) 中使用搜尋工具時，您不必使用此策略。</span><span class="sxs-lookup"><span data-stu-id="43114-405">You don't have to use this strategy when using the search tool in [Advanced eDiscovery](overview-ediscovery-20.md).</span></span> <span data-ttu-id="43114-406">這是因為在進階電子文件探索中搜尋 SharePoint 網站和OneDrive 帳戶時，會搜尋所有資料中心。</span><span class="sxs-lookup"><span data-stu-id="43114-406">That's because all datacenters are searched when you search SharePoint sites and OneDrive accounts in Advanced eDiscovery.</span></span> <span data-ttu-id="43114-407">只有在使用內容搜尋工具並執行與[電子文件探索案例](ediscovery-cases.md)相關聯的搜尋時，才必須使用這個特定區域使用者帳戶和搜尋權限篩選器的策略。</span><span class="sxs-lookup"><span data-stu-id="43114-407">You have to use this strategy of region-specific user accounts and search permissions filters only when using the Content Search tool and running searches associated with [eDiscovery cases](ediscovery-cases.md).</span></span> 


<span data-ttu-id="43114-408">例如，假設電子文件探索管理員需要在北美、歐洲和亞太地區的衛星位置搜尋 SharePoint 和 OneDrive 內容。</span><span class="sxs-lookup"><span data-stu-id="43114-408">For example, let's say that an eDiscovery manager needs to search for SharePoint and OneDrive content in satellite locations in North American, Europe, and Asia Pacific.</span></span> <span data-ttu-id="43114-409">第一個步驟是建立三個使用者帳戶，每個位置一個。</span><span class="sxs-lookup"><span data-stu-id="43114-409">The first step is to create three users accounts, one for each location.</span></span> <span data-ttu-id="43114-410">下一步是建立三個搜尋權限篩選條件，每個位置及\*\* 相應的使用者帳戶一個。</span><span class="sxs-lookup"><span data-stu-id="43114-410">The next step is to create three search permissions filters, one for each location *and* corresponding user account.</span></span> <span data-ttu-id="43114-411">以下是此案例的三個搜尋權限篩選條件的範例。</span><span class="sxs-lookup"><span data-stu-id="43114-411">Here are examples of the three search permissions filters for this scenario.</span></span> <span data-ttu-id="43114-412">在每個範例中，**[區域]** 指定該地理位置的 SharePoint 資料中心位置，**[使用者]** 參數指定相應的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="43114-412">In each of these examples, the **Region** specifies the SharePoint datacenter location for that geo and the **Users** parameter specifies the corresponding user account.</span></span> 

<span data-ttu-id="43114-413">**北美**</span><span class="sxs-lookup"><span data-stu-id="43114-413">**North America**</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-NAM" -Users ediscovery-nam@contoso.com -Region NAM -Action ALL
```

<span data-ttu-id="43114-414">**歐洲**</span><span class="sxs-lookup"><span data-stu-id="43114-414">**Europe**</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-EUR" -Users ediscovery-eur@contoso.com -Region EUR -Action ALL
```

<span data-ttu-id="43114-415">**亞太地區**</span><span class="sxs-lookup"><span data-stu-id="43114-415">**Asia Pacific**</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-APC" -Users ediscovery-apc@contoso.com -Region APC -Action ALL
```

<span data-ttu-id="43114-416">使用搜尋權限篩選條件在多地理位置環境中搜尋內容時，請記住以下事項：</span><span class="sxs-lookup"><span data-stu-id="43114-416">Keep the following things in mind when using search permissions filters to search for content in multi-geo environments:</span></span>

- <span data-ttu-id="43114-417">**[地區]** 參數會指示搜尋特定的衛星位置。</span><span class="sxs-lookup"><span data-stu-id="43114-417">The **Region** parameter directs searches to the specified satellite location.</span></span> <span data-ttu-id="43114-418">如果電子文件探索管理員只搜尋搜尋權限篩選器指定之區域以外的 SharePoint 和 OneDrive 網站，則不會傳回搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="43114-418">If an eDiscovery manager only searches SharePoint and OneDrive sites outside of the region specified in the search permissions filter, no search results are returned.</span></span> 

- <span data-ttu-id="43114-419">**[地區]** 參數不會控制 Exchange 信箱的搜尋。</span><span class="sxs-lookup"><span data-stu-id="43114-419">The **Region** parameter doesn't control searches of Exchange mailboxes.</span></span> <span data-ttu-id="43114-420">搜尋信箱時，也會搜尋所有資料中心。</span><span class="sxs-lookup"><span data-stu-id="43114-420">All datacenters are searched when you search mailboxes.</span></span> 
    
<span data-ttu-id="43114-421">如需在多地理位置環境中使用搜尋權限篩選條件的詳細資訊，請參閱[設定電子文件探索調查的合規性界限](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments)中的「搜尋和匯出在多地理位置環境中的內容」這一節。</span><span class="sxs-lookup"><span data-stu-id="43114-421">For more information about using search permissions filters in a multi-geo environment, see the "Searching and exporting content in Multi-Geo environments" section in [Set up compliance boundaries for eDiscovery investigations](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).</span></span>
