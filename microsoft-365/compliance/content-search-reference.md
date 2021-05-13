---
title: 內容搜尋的功能參考
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
description: 本文包含 Microsoft 365 合規性中心中內容搜尋電子文件探索工具的參考資訊，可協助了解內容搜尋的許多詳細資料。
ms.openlocfilehash: f3545cc4644ca8b0a96ee37713d8fe62be7466e5
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332891"
---
# <a name="feature-reference-for-content-search"></a><span data-ttu-id="38d1a-103">內容搜尋的功能參考</span><span class="sxs-lookup"><span data-stu-id="38d1a-103">Feature reference for Content search</span></span>

<span data-ttu-id="38d1a-104">本文說明內容搜尋的功能。</span><span class="sxs-lookup"><span data-stu-id="38d1a-104">This article describes features and functionality of Content search.</span></span>

## <a name="content-search-limits"></a><span data-ttu-id="38d1a-105">內容搜尋限制</span><span class="sxs-lookup"><span data-stu-id="38d1a-105">Content search limits</span></span>

- <span data-ttu-id="38d1a-106">如需 [內容搜尋] 適用限制的說明，請參閱[內容搜尋的限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-106">For a description of the limits that are applied to content searches, see [Limits for Content search](limits-for-content-search.md).</span></span>
  
- <span data-ttu-id="38d1a-107">Microsoft 會收集服務中所有組織執行的內容搜尋的效能資訊。</span><span class="sxs-lookup"><span data-stu-id="38d1a-107">Microsoft collects performance information for Content searches run by all organizations in the service.</span></span> <span data-ttu-id="38d1a-108">雖然搜尋查詢的複雜性可能會影響搜尋時間，會影響搜尋所需時間的最大因素是搜尋的信箱數量。</span><span class="sxs-lookup"><span data-stu-id="38d1a-108">While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched.</span></span> <span data-ttu-id="38d1a-109">雖然 Microsoft 不對搜尋時間提供服務等級協定，下表根據搜尋中包含的信箱數量列出內容搜尋的平均搜尋時間。</span><span class="sxs-lookup"><span data-stu-id="38d1a-109">Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for a Content Search based on the number of mailboxes included in the search.</span></span>
  
  |<span data-ttu-id="38d1a-110">**信箱數目**</span><span class="sxs-lookup"><span data-stu-id="38d1a-110">**Number of mailboxes**</span></span>|<span data-ttu-id="38d1a-111">**平均搜尋時間**</span><span class="sxs-lookup"><span data-stu-id="38d1a-111">**Average search time**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="38d1a-112">100</span><span class="sxs-lookup"><span data-stu-id="38d1a-112">100</span></span>  <br/> |<span data-ttu-id="38d1a-113">30 秒</span><span class="sxs-lookup"><span data-stu-id="38d1a-113">30 seconds</span></span>  <br/> |
  |<span data-ttu-id="38d1a-114">1,000</span><span class="sxs-lookup"><span data-stu-id="38d1a-114">1,000</span></span>  <br/> |<span data-ttu-id="38d1a-115">45 秒</span><span class="sxs-lookup"><span data-stu-id="38d1a-115">45 seconds</span></span>  <br/> |
  |<span data-ttu-id="38d1a-116">10,000</span><span class="sxs-lookup"><span data-stu-id="38d1a-116">10,000</span></span>  <br/> |<span data-ttu-id="38d1a-117">4 分鐘</span><span class="sxs-lookup"><span data-stu-id="38d1a-117">4 minutes</span></span>  <br/> |
  |<span data-ttu-id="38d1a-118">25,000</span><span class="sxs-lookup"><span data-stu-id="38d1a-118">25,000</span></span>  <br/> |<span data-ttu-id="38d1a-119">10 分鐘</span><span class="sxs-lookup"><span data-stu-id="38d1a-119">10 minutes</span></span>  <br/> |
  |<span data-ttu-id="38d1a-120">50,000</span><span class="sxs-lookup"><span data-stu-id="38d1a-120">50,000</span></span>  <br/> |<span data-ttu-id="38d1a-121">20 分鐘</span><span class="sxs-lookup"><span data-stu-id="38d1a-121">20 minutes</span></span>  <br/> |
  |<span data-ttu-id="38d1a-122">100,000</span><span class="sxs-lookup"><span data-stu-id="38d1a-122">100,000</span></span>  <br/> |<span data-ttu-id="38d1a-123">25 分鐘</span><span class="sxs-lookup"><span data-stu-id="38d1a-123">25 minutes</span></span>  <br/> |
  |||
  
## <a name="building-a-search-query"></a><span data-ttu-id="38d1a-124">建立搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="38d1a-124">Building a search query</span></span>

<span data-ttu-id="38d1a-125">如需建立搜尋查詢、使用布林搜尋運算子和搜尋條件，以及搜尋與組織外部使用者共用的機密資訊類型和內容的詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-125">For detailed information about creating a search query, using Boolean search operators and search conditions, and searching for sensitive information types and content shared with users outside your organization, see [Keyword queries and search conditions for Content Search ](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="38d1a-126">使用關鍵字清單建立搜尋查詢時，請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="38d1a-126">Keep the following things in mind when using the keyword list to create a search query.</span></span>
  
- <span data-ttu-id="38d1a-127">您必須選取 **[顯示關鍵字清單]** 核取方塊，然後在不同的列輸入每個關鍵字來建立搜尋查詢，其中每個列的關鍵字 (或關鍵字字詞) 是用 **OR** 運算子連接。</span><span class="sxs-lookup"><span data-stu-id="38d1a-127">You have to select the **Show keyword list** checkbox and then type each keyword in a separate row to create a search query where the keywords (or keyword phrases) in each row are connected by the **OR** operator.</span></span> <span data-ttu-id="38d1a-128">如果您在輸入關鍵字之後，於關鍵字方塊中貼上關鍵字清單或按下 **Enter** 鍵，就不會使用 **OR** 運算子將其連接。</span><span class="sxs-lookup"><span data-stu-id="38d1a-128">If you paste a list of keywords in the keyword box or press the **Enter** key after typing a keyword, they won't be connected by the **OR** operator.</span></span> <span data-ttu-id="38d1a-129">以下是如何新增關鍵字清單的不正確和正確範例。</span><span class="sxs-lookup"><span data-stu-id="38d1a-129">Here are incorrect and correct examples of how to add a list of keywords.</span></span>
    
    <span data-ttu-id="38d1a-130">**不正確**</span><span class="sxs-lookup"><span data-stu-id="38d1a-130">**Incorrect**</span></span>
    
    ![設定關鍵字清單格式的方式不正確 (在關鍵字方塊中貼上清單)](../media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    <span data-ttu-id="38d1a-132">**正確**</span><span class="sxs-lookup"><span data-stu-id="38d1a-132">**Correct**</span></span>
    
    ![設定關鍵字清單格式的方式正確 (選取核取方塊，然後貼上清單)](../media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- <span data-ttu-id="38d1a-134">您也可以在 Excel 檔案或純文字檔案中準備關鍵字或關鍵字片語的清單，然後將您的清單複製並貼入關鍵字清單中。</span><span class="sxs-lookup"><span data-stu-id="38d1a-134">You can also prepare a list of keywords or keyword phrases in an Excel file or a plain text file, and then copy and paste your list into the keyword list.</span></span> <span data-ttu-id="38d1a-135">若要這麼做，您必須選取 **[顯示關鍵字清單]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="38d1a-135">To do this, you have to select the **Show keyword list** check box.</span></span> <span data-ttu-id="38d1a-136">然後在關鍵字清單的第一列按一下，並貼上您的清單。</span><span class="sxs-lookup"><span data-stu-id="38d1a-136">Then, click the first row in the keyword list and paste your list.</span></span> <span data-ttu-id="38d1a-137">來自 Excel 或文字檔案的每一行都會貼到關鍵字清單中的不同列。</span><span class="sxs-lookup"><span data-stu-id="38d1a-137">Each line from the Excel or text file is pasted into separate row in the keyword list.</span></span> 
    
- <span data-ttu-id="38d1a-138">使用關鍵字清單建立查詢之後，最好先驗證搜尋查詢語法，以讓該搜尋查詢成為您想要的查詢。</span><span class="sxs-lookup"><span data-stu-id="38d1a-138">After you create a query using the keyword list, it's a good idea to verify the search query syntax to make the search query is what you intended.</span></span> <span data-ttu-id="38d1a-139">在詳細資料窗格的 **[查詢]** 下顯示的搜尋查詢中，關鍵字使用文字 **(c:s)** 分隔。</span><span class="sxs-lookup"><span data-stu-id="38d1a-139">In the search query that's displayed under **Query** in the details pane, the keywords are separated by the text **(c:s)**.</span></span> <span data-ttu-id="38d1a-140">這表示關鍵字是使用與 **OR** 運算子類似功能的邏輯運算子連接。</span><span class="sxs-lookup"><span data-stu-id="38d1a-140">This indicates that the keywords are connected by a logical operator similar in functionality to the **OR** operator.</span></span> <span data-ttu-id="38d1a-141">同樣地，如果您的搜尋查詢中包含條件，關鍵字與條件以文字 **(c:c)** 分隔。</span><span class="sxs-lookup"><span data-stu-id="38d1a-141">Similarly, if your search query includes conditions, the keywords and the conditions are separated by the text **(c:c)**.</span></span> <span data-ttu-id="38d1a-142">這表示關鍵字是使用與 **AND** 運算子類似功能的邏輯運算子與條件連接。</span><span class="sxs-lookup"><span data-stu-id="38d1a-142">This indicates that the keywords are connected to the conditions with a logical operator similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="38d1a-143">以下是使用關鍵字清單與條件時產生的搜尋查詢的範例 (顯示在 [詳細資料] 窗格中)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-143">Here's an example of the search query (displayed in the Details pane) that results when using the keyword list and a condition.</span></span> 
    
    ![使用關鍵字清單與條件時建立的查詢範例](../media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- <span data-ttu-id="38d1a-145">執行內容搜尋時，Microsoft 365 會自動檢查您的搜尋查詢中是否有不受支援的字元，以及可能未大寫的布林值運算子。</span><span class="sxs-lookup"><span data-stu-id="38d1a-145">When you run a content search, Microsoft 365 automatically checks your search query for unsupported characters and for Boolean operators that may not be capitalized.</span></span> <span data-ttu-id="38d1a-146">不支援的字元通常會隱藏起來，且通常會導致搜尋錯誤或傳回非預期的結果。</span><span class="sxs-lookup"><span data-stu-id="38d1a-146">Unsupported characters are often hidden and typically cause a search error or return unintended results.</span></span> <span data-ttu-id="38d1a-147">如需所檢查不受支援字元的詳細資訊，請參閱[檢查您的內容搜尋查詢是否有錯誤](check-your-content-search-query-for-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-147">For more information about the unsupported characters that are checked, see [Check your Content Search query for errors](check-your-content-search-query-for-errors.md).</span></span>
    
- <span data-ttu-id="38d1a-148">如果您有包含非英文字元 (例如中文字元) 關鍵字的搜尋查詢時，您可以按一下 **[查詢語言-國家/地區]**![內容搜尋中的 [查詢語言-國家/地區] 圖示](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png)，然後選取搜尋的語言-國家/地區文化特性代碼值。</span><span class="sxs-lookup"><span data-stu-id="38d1a-148">If you have a search query that contains keywords for non-English characters (such as Chinese characters), you can click **Query language-country/region**![Query language-country/region icon in Content search](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) and select a language-country culture code value for the search.</span></span> <span data-ttu-id="38d1a-149">預設的語言-國家/地區為中性。</span><span class="sxs-lookup"><span data-stu-id="38d1a-149">The default language/region is neutral.</span></span> <span data-ttu-id="38d1a-150">如何判斷您是否需要變更內容搜尋的語言設定？</span><span class="sxs-lookup"><span data-stu-id="38d1a-150">How can you tell if you need to change the language setting for a content search?</span></span> <span data-ttu-id="38d1a-151">如果您確定您要搜尋的內容位置包含非英文字元，但搜尋卻未傳回任何結果，這可能是語言設定所造成。</span><span class="sxs-lookup"><span data-stu-id="38d1a-151">If you're certain content locations contain the non-English characters you're searching for, but the search returns no results, the language setting may be the cause.</span></span> 
  
## <a name="partially-indexed-items"></a><span data-ttu-id="38d1a-152">部分編製索引的項目</span><span class="sxs-lookup"><span data-stu-id="38d1a-152">Partially indexed items</span></span>

- <span data-ttu-id="38d1a-153">估計的搜尋結果中會包含信箱中部分編製索引的項目。</span><span class="sxs-lookup"><span data-stu-id="38d1a-153">Partially indexed items in mailboxes are included in the estimated search results.</span></span> <span data-ttu-id="38d1a-154">估計的搜尋結果中不會包括來自 SharePoint 和 OneDrive 的部分編製索引項目。</span><span class="sxs-lookup"><span data-stu-id="38d1a-154">Partially indexed items from SharePoint and OneDrive aren't included in the estimated search results.</span></span> <span data-ttu-id="38d1a-155">如需詳細資訊，請參閱[電子文件探索中部分編製索引的項目](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-155">For more information, see [Partially indexed items in eDiscovery](partially-indexed-items-in-content-search.md).</span></span>

## <a name="searching-onedrive-accounts"></a><span data-ttu-id="38d1a-156">搜尋 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="38d1a-156">Searching OneDrive accounts</span></span>

- <span data-ttu-id="38d1a-157">若要收集組織中 OneDrive 網站的 URL 清單，請參閱[建立組織中所有 OneDrive 位置的清單](/onedrive/list-onedrive-urls)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-157">To collect a list of the URLs for the OneDrive sites in your organization, see [Create a list of all OneDrive locations in your organization](/onedrive/list-onedrive-urls).</span></span> <span data-ttu-id="38d1a-158">本文章中的這個指令碼會建立文字檔案，其中包含所有 OneDrive 網站的清單。</span><span class="sxs-lookup"><span data-stu-id="38d1a-158">This script in this article creates a text file that contains a list of all OneDrive sites.</span></span> <span data-ttu-id="38d1a-159">若要執行此指令碼，您必須安裝並使用 SharePoint Online 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="38d1a-159">To run this script, you have to install and use the SharePoint Online Management Shell.</span></span> <span data-ttu-id="38d1a-160">請務必將您組織 MySite 網域的 URL 附加至您要搜尋的每個 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="38d1a-160">Be sure to append the URL for your organization's MySite domain to each OneDrive site that you want to search.</span></span> <span data-ttu-id="38d1a-161">這是包含您所有 OneDrive 的網域；例如，`https://contoso-my.sharepoint.com`。</span><span class="sxs-lookup"><span data-stu-id="38d1a-161">This is the domain that contains all your OneDrive; for example,  `https://contoso-my.sharepoint.com`.</span></span> <span data-ttu-id="38d1a-162">以下是使用者 OneDrive 網站的 URL 範例：`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。</span><span class="sxs-lookup"><span data-stu-id="38d1a-162">Here's an example of a URL for a user's OneDrive site:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.</span></span>
    
    <span data-ttu-id="38d1a-163">在人員的使用者主體名稱 (UPN) 變更的少數情況下，其 OneDrive 位置的 URL 將會變更以納入新的 UPN。</span><span class="sxs-lookup"><span data-stu-id="38d1a-163">In the rare case of a person's user principal name (UPN) being changed, the URL for their OneDrive location is changed to incorporate the new UPN.</span></span> <span data-ttu-id="38d1a-164">如果發生這種情況，您必須透過新增使用者的新 OneDrive URL 並移除舊 URL 來修改內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="38d1a-164">If this happens, you have to modify a content search by adding the user's new OneDrive URL and removing the old one.</span></span> <span data-ttu-id="38d1a-165">如需詳細資訊，請參閱 [UPN 變更將如何影響 OneDrive URL](/onedrive/upn-changes)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-165">For more information, see [How UPN changes affect the OneDrive URL](/onedrive/upn-changes).</span></span>
  
## <a name="searching-microsoft-teams-and-microsoft-365-groups"></a><span data-ttu-id="38d1a-166">搜尋 Microsoft Teams 和 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="38d1a-166">Searching Microsoft Teams and Microsoft 365 Groups</span></span>

<span data-ttu-id="38d1a-167">您可以搜尋與 Microsoft Teams 或 Microsoft 365 相關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-167">You can search the mailbox that's associated with a Microsoft Team or Microsoft 365 Group.</span></span> <span data-ttu-id="38d1a-168">因為 Microsoft Teams 建置於 Microsoft 365 群組上，搜尋它們的方式很類似。</span><span class="sxs-lookup"><span data-stu-id="38d1a-168">Because Microsoft Teams is built on Microsoft 365 Groups, searching them is similar.</span></span> <span data-ttu-id="38d1a-169">在這兩個情況下，只會搜尋群組或團隊信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-169">In both cases, only the group or team mailbox is searched.</span></span> <span data-ttu-id="38d1a-170">不會搜尋群組或團隊成員的信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-170">The mailboxes of the group or team members aren't searched.</span></span> <span data-ttu-id="38d1a-171">若要進行搜尋，您必須特別將它們新增至搜尋。</span><span class="sxs-lookup"><span data-stu-id="38d1a-171">To search them, you have to specifically add them to the search.</span></span>
  
<span data-ttu-id="38d1a-172">搜尋 Microsoft Teams 和 Microsoft 365 群組中的內容時，請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="38d1a-172">Keep the following things in mind when searching for content in Microsoft Teams and Microsoft 365 Groups.</span></span>
  
- <span data-ttu-id="38d1a-173">若要搜尋位於 Teams 和 Microsoft 365 群組中的內容，您必須指定與團隊或群組相關聯的信箱和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="38d1a-173">To search for content located in Teams and Microsoft 365 Groups, you have to specify the mailbox and SharePoint site that are associated with a team or group.</span></span>

- <span data-ttu-id="38d1a-174">來自私人頻道的內容會儲存在每位使用者的信箱，而不會儲存在小組信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-174">Content from private channels is stored in each user's mailbox, not the team mailbox.</span></span> <span data-ttu-id="38d1a-175">若要搜尋私人頻道中的內容，請參閱[私人頻道進階電子文件探索](/microsoftteams/ediscovery-investigation#ediscovery-of-private-channels) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-175">To search for content in private channels, see [eDiscovery of private channels](/microsoftteams/ediscovery-investigation#ediscovery-of-private-channels).</span></span>
    
- <span data-ttu-id="38d1a-176">在 Exchange Online 中執行 **Get-UnifiedGroup** Cmdlet，以檢視團隊或 Microsoft 365 群組的內容。</span><span class="sxs-lookup"><span data-stu-id="38d1a-176">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for a team or a Microsoft 365 Group.</span></span> <span data-ttu-id="38d1a-177">這是取得與團隊或群組相關聯的網站 URL 的絕佳方法。</span><span class="sxs-lookup"><span data-stu-id="38d1a-177">This is a good way to get the URL for the site that's associated with a team or a group.</span></span> <span data-ttu-id="38d1a-178">例如，下列命令會顯示名為「資深領導團隊」的 Microsoft 365 群組的所選屬性：</span><span class="sxs-lookup"><span data-stu-id="38d1a-178">For example, the following command displays selected properties for a Microsoft 365 Group named Senior Leadership Team:</span></span> 
    
  ```text
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  ```

    > [!NOTE]
    > <span data-ttu-id="38d1a-179">若要執行 **Get-UnifiedGroup** Cmdlet，您必須獲指派 Exchange Online 中的「僅檢視收件者」角色或者為獲指派「僅檢視收件者」角色之角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="38d1a-179">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="38d1a-180">搜尋使用者的信箱時，不會搜尋使用者所隸屬的任何團隊或 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="38d1a-180">When a user's mailbox is searched, any team or Microsoft 365 Group that the user is a member of won't be searched.</span></span> <span data-ttu-id="38d1a-181">同樣地，當您搜尋團隊或 Microsoft 365 群組時，只會搜尋您指定的群組信箱及群組網站。</span><span class="sxs-lookup"><span data-stu-id="38d1a-181">Similarly, when you search a team or a Microsoft 365 Group, only the group mailbox and group site that you specify is searched.</span></span> <span data-ttu-id="38d1a-182">不會搜尋群組成員的信箱和商務用 OneDrive 帳戶，除非您明確地將它們新增至搜尋。</span><span class="sxs-lookup"><span data-stu-id="38d1a-182">The mailboxes and OneDrive for Business accounts of group members aren't searched unless you explicitly add them to the search.</span></span>

- <span data-ttu-id="38d1a-183">若要取得團隊或 Microsoft 365 群組的成員清單，您可以在 Microsoft 365 系統管理中心的 **[常用] \> [群組]** 頁面上檢視內容。</span><span class="sxs-lookup"><span data-stu-id="38d1a-183">To get a list of the members of a team or a Microsoft 365 Group, you can view the properties on the **Home \> Groups** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="38d1a-184">或者，您可以在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="38d1a-184">Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 

  ```powershell
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
  ```

    > [!NOTE]
    > <span data-ttu-id="38d1a-185">若要執行 **Get-UnifiedGroupLinks** Cmdlet，您必須獲指派 Exchange Online 中的「僅檢視收件者」角色或者為獲指派「僅檢視收件者」角色之角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="38d1a-185">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="38d1a-186">屬於 Teams 頻道一部分的交談會儲存在與團隊相關聯的信箱中。</span><span class="sxs-lookup"><span data-stu-id="38d1a-186">Conversations that are part of a Teams channel are stored in the mailbox that's associated with the team.</span></span> <span data-ttu-id="38d1a-187">同樣地，團隊成員在頻道中共用的檔案會儲存在團隊的 SharePoint 網站上。</span><span class="sxs-lookup"><span data-stu-id="38d1a-187">Similarly, files that team members share in a channel are stored on the team's SharePoint site.</span></span> <span data-ttu-id="38d1a-188">因此，您必須將團隊信箱和 SharePoint 網站新增為內容位置，才能搜尋頻道中的交談和檔案。</span><span class="sxs-lookup"><span data-stu-id="38d1a-188">Therefore, you have to add the team mailbox and SharePoint site as a content location to search conversations and files in a channel.</span></span>
    
- <span data-ttu-id="38d1a-189">或者，屬於 Teams 中聊天清單的交談會儲存在參與聊天的使用者的 Exchange Online 信箱中。</span><span class="sxs-lookup"><span data-stu-id="38d1a-189">Alternatively, conversations that are part of the Chat list in Teams are stored in the Exchange Online mailbox of the users who participate in the chat.</span></span> <span data-ttu-id="38d1a-190">而使用者在聊天交談中共用的檔案會儲存在共用檔案的使用者的商務用 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="38d1a-190">And files that a user shares in Chat conversations are stored in the OneDrive for Business account of the user who shares the file.</span></span> <span data-ttu-id="38d1a-191">因此，您必須將個別使用者信箱和商務用 OneDrive 帳戶新增為內容位置，才能搜尋聊天清單中的交談和檔案。</span><span class="sxs-lookup"><span data-stu-id="38d1a-191">Therefore, you have to add the individual user mailboxes and OneDrive for Business accounts as content locations to search conversations and files in the Chat list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38d1a-192">在 Exchange 混合式部署中，具有內部部署信箱的使用者可能會參與屬於 Teams 中聊天清單的交談。</span><span class="sxs-lookup"><span data-stu-id="38d1a-192">In an Exchange hybrid deployment, users with an on-premises mailbox might participate in conversations that are part of the Chat list in Teams.</span></span> <span data-ttu-id="38d1a-193">在此情況下，來自這些交談的內容也可供搜尋，因為針對具有內部部署信箱的使用者，這些內容會儲存到雲端式存放區域 (稱為 *內部部署使用者的雲端式信箱*)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-193">In this case, content from these conversations is also searchable because it's saved to a cloud-based storage area (called a *cloud-based mailbox for on-premises users*) for users who have an on-premises mailbox.</span></span> <span data-ttu-id="38d1a-194">如需詳細資訊，請參閱[搜尋內部部署使用者的 Teams 聊天資料](search-cloud-based-mailboxes-for-on-premises-users.md)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-194">For more information, see [Search for Teams chat data for on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
  
- <span data-ttu-id="38d1a-195">每個團隊或團隊頻道包含一個 Wiki，用於記筆記和進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="38d1a-195">Every team or team channel contains a Wiki for note-taking and collaboration.</span></span> <span data-ttu-id="38d1a-196">Wiki 的內容會自動儲存至 .mht 格式的檔案中。</span><span class="sxs-lookup"><span data-stu-id="38d1a-196">The Wiki content is automatically saved to a file with a .mht format.</span></span> <span data-ttu-id="38d1a-197">此檔案會儲存在團隊 SharePoint 網站上的 Teams Wiki 資料文件庫中。</span><span class="sxs-lookup"><span data-stu-id="38d1a-197">This file is stored in the Teams Wiki Data document library on the team's SharePoint site.</span></span> <span data-ttu-id="38d1a-198">您可以使用「內容搜尋」工具來搜尋 Wiki，方法是將團隊的 SharePoint 網站指定為要搜尋的內容位置。</span><span class="sxs-lookup"><span data-stu-id="38d1a-198">You can use the Content Search tool to search the Wiki by specifying the team's SharePoint site as the content location to search.</span></span>

    > [!NOTE]
    > <span data-ttu-id="38d1a-199">搜尋團隊或頻道的 Wiki 功能 (搜尋團隊的 SharePoint 網站時) 是在 2017 年 6 月 22 日推出。</span><span class="sxs-lookup"><span data-stu-id="38d1a-199">The capability to search the Wiki for a team or channel (when you search the team's SharePoint site) was released on June 22, 2017.</span></span> <span data-ttu-id="38d1a-200">在該日期當日或之後儲存或更新的 Wiki 頁面可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="38d1a-200">Wiki pages that were saved or updated on that date or after are available to be searched.</span></span> <span data-ttu-id="38d1a-201">在該日期之前儲存或更新的 Wiki 頁面無法供搜尋。</span><span class="sxs-lookup"><span data-stu-id="38d1a-201">Wiki pages last saved or updated before that date aren't available for search.</span></span>

- <span data-ttu-id="38d1a-202">Teams 頻道中的會議及電話的摘要資訊也會儲存在撥入會議或電話使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="38d1a-202">Summary information for meetings and calls in a Teams channel are also stored in the mailboxes of users who dialed into the meeting or call.</span></span> <span data-ttu-id="38d1a-203">這表示您可以使用內容搜尋來搜尋這些摘要記錄。</span><span class="sxs-lookup"><span data-stu-id="38d1a-203">This means you can use Content Search to search these summary records.</span></span> <span data-ttu-id="38d1a-204">摘要資訊包含：</span><span class="sxs-lookup"><span data-stu-id="38d1a-204">Summary information includes:</span></span>
  
  - <span data-ttu-id="38d1a-205">會議或通話的日期、開始時間、結束時間和持續期間</span><span class="sxs-lookup"><span data-stu-id="38d1a-205">Date, start time, end time, and duration of a meeting or call</span></span>

  - <span data-ttu-id="38d1a-206">每個參與者加入或離開會議或通話的日期及時間</span><span class="sxs-lookup"><span data-stu-id="38d1a-206">The date and time when each participant joined or left the meeting or call</span></span>

  - <span data-ttu-id="38d1a-207">傳送到語音信箱的通話</span><span class="sxs-lookup"><span data-stu-id="38d1a-207">Calls sent to voice mail</span></span>

  - <span data-ttu-id="38d1a-208">未接來電或無人接聽的來電</span><span class="sxs-lookup"><span data-stu-id="38d1a-208">Missed or unanswered calls</span></span>

  - <span data-ttu-id="38d1a-209">來電轉接，以兩個不同通話的形式呈現</span><span class="sxs-lookup"><span data-stu-id="38d1a-209">Call transfers, which are represented as two separate calls</span></span>

  <span data-ttu-id="38d1a-210">可能需要最長達 8 小時的時間，會議和通話摘要記錄才可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="38d1a-210">It can take up to 8 hours for meeting and call summary records to be available to be searched.</span></span>

  <span data-ttu-id="38d1a-211">在搜尋結果中，會在 **[類型]** 欄位中將會議摘要識別為 **[會議]**，以及將通話摘要識別為 **[通話]**。</span><span class="sxs-lookup"><span data-stu-id="38d1a-211">In the search results, meeting summaries are identified as **Meeting** in the **Type field**, and call summaries are identified as **Call**.</span></span> <span data-ttu-id="38d1a-212">此外，屬於 Teams 頻道和 1xN 聊天的交談，會在 **[類型]** 欄位中識別為 **IM**。</span><span class="sxs-lookup"><span data-stu-id="38d1a-212">Also, conversations that are part of a Teams channel and 1xN chats are identified as **IM** in the **Type** field.</span></span>
  
  ![Teams 會議、通話和 1xN 聊天都可在 [類型] 欄位中識別](../media/O365-ContentSearch-Teams-MessageKind.png)

   <span data-ttu-id="38d1a-214">如需詳細資訊，請參閱 [Microsoft Teams 啟動通話跟會議的電子文件探索](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-launches-ediscovery-for-calling-and-meetings/ba-p/210947)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-214">For more information, see [Microsoft Teams launches eDiscovery for calls and meetings](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-launches-ediscovery-for-calling-and-meetings/ba-p/210947).</span></span>

- <span data-ttu-id="38d1a-215">Teams 頻道、1:1 聊天和 1xN 聊天中的應用程式產生的卡片內容儲存在信箱中，可以進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="38d1a-215">Card content generated by apps in Teams channels, 1:1 chats, and 1xN chats is stored in mailboxes and can be searched.</span></span> <span data-ttu-id="38d1a-216">*卡片* 是一個 UI 容器，用於儲存簡短的內容片段。</span><span class="sxs-lookup"><span data-stu-id="38d1a-216">A *card* is a UI container for short pieces of content.</span></span> <span data-ttu-id="38d1a-217">卡片可以有多個内容和附件，還可以包含可以觸發卡片動作的按鈕。</span><span class="sxs-lookup"><span data-stu-id="38d1a-217">Cards can have multiple properties and attachments, and can include buttons that can trigger card actions.</span></span> <span data-ttu-id="38d1a-218">如需詳細資訊，請參閱 [卡片](/microsoftteams/platform/task-modules-and-cards/what-are-cards)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-218">For more information, see [Cards](/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span></span>

  <span data-ttu-id="38d1a-219">與其他 Teams 內容一樣，儲存卡片內容的位置取決於卡片的使用位置。</span><span class="sxs-lookup"><span data-stu-id="38d1a-219">Like other Teams content, where card content is stored is based on where the card was used.</span></span> <span data-ttu-id="38d1a-220">Teams 頻道中使用的卡片之內容儲存在 Teams 群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="38d1a-220">Content for cards used in a Teams channel is stored in the Teams group mailbox.</span></span> <span data-ttu-id="38d1a-221">1:1 和 1xN 聊天的卡片內容儲存在聊天參與者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="38d1a-221">Card content for 1:1 and 1xN chats are stored in the mailboxes of the chat participants.</span></span>

  <span data-ttu-id="38d1a-222">要搜尋卡片內容，可以使用 `kind:microsoftteams` 或 `itemclass:IPM.SkypeTeams.Message` 搜尋條件。</span><span class="sxs-lookup"><span data-stu-id="38d1a-222">To search for card content, you can use the `kind:microsoftteams` or `itemclass:IPM.SkypeTeams.Message` search conditions.</span></span> <span data-ttu-id="38d1a-223">檢閲搜尋結果時，Teams 頻道中機器人程式產生之卡片內容的 **寄件者/作者** 電子郵件屬性為 `<appname>@teams.microsoft.com` ，其中 `appname` 是產生卡片內容的應用程式之名稱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-223">When reviewing search results, card content generated by bots in a Teams channel have the **Sender/Author** email property as `<appname>@teams.microsoft.com`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="38d1a-224">如果卡片內容是由使用者生成的，則 **寄件者/作者** 的值識別使用者。</span><span class="sxs-lookup"><span data-stu-id="38d1a-224">If card content was generated by a user, the value of **Sender/Author** identifies the user.</span></span>

  <span data-ttu-id="38d1a-225">在內容搜尋結果中檢視卡片內容時，內容顯示為訊息的附件。</span><span class="sxs-lookup"><span data-stu-id="38d1a-225">When viewing card content in Content search results, the content appears as an attachment to the message.</span></span> <span data-ttu-id="38d1a-226">附件名為 `appname.html`，其中 `appname` 是產生卡片內容之應用程式的名稱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-226">The attachment is named `appname.html`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="38d1a-227">下方的螢幕擷取畫面顯示了卡片內容 (對於名為 Asana 的應用程式) 在Teams 和搜尋結果中的顯示方式。</span><span class="sxs-lookup"><span data-stu-id="38d1a-227">The following screenshots show how card content (for an app named Asana) appears in Teams and in the results of a search.</span></span>

  <span data-ttu-id="38d1a-228">**Teams 中的卡片内容**</span><span class="sxs-lookup"><span data-stu-id="38d1a-228">**Card content in Teams**</span></span>

  ![Teams 頻道訊息中的卡片内容](../media/CardContentTeams.png)

  <span data-ttu-id="38d1a-230">**搜尋結果中的卡片内容**</span><span class="sxs-lookup"><span data-stu-id="38d1a-230">**Card content in search results**</span></span>
  
  ![內容搜尋結果中的相同卡片內容](../media/CardContentEdiscoverySearchResults.png)

  > [!NOTE]
  > <span data-ttu-id="38d1a-232">要在此時顯示搜尋結果中卡片內容中之影像 (如上一螢幕擷取畫面中的核取記號)，您必須登入 Teams (在用於檢視搜尋結果的同一瀏覽器工作階段中之不同索引標籤中的 https://teams.microsoft.com) 處)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-232">To display images from card content in search results at this time (such as the checkmarks in the previous screenshot), you have to be signed into Teams (at https://teams.microsoft.com) in a different tab in the same browser session that you use to view the search results.</span></span> <span data-ttu-id="38d1a-233">否則，將顯示影像預留位置。</span><span class="sxs-lookup"><span data-stu-id="38d1a-233">Otherwise, image placeholders are displayed.</span></span>

- <span data-ttu-id="38d1a-234">您可以使用 **Kind** 電子郵件屬性或 **[郵件類型]** 搜尋條件來搜尋 Teams 中的專屬內容。</span><span class="sxs-lookup"><span data-stu-id="38d1a-234">You can use the **Kind** email property or the **Message kind** search condition to search specifically for content in Teams.</span></span>
  
  - <span data-ttu-id="38d1a-235">若要在關鍵字搜尋查詢中使用 **Kind** 屬性，請在搜尋查詢的 **[關鍵字]** 方塊中輸入 `kind:microsoftteams`。</span><span class="sxs-lookup"><span data-stu-id="38d1a-235">To use the **Kind** property as part of the keyword search query, in the **Keywords** box of a search query, type `kind:microsoftteams`.</span></span>

    ![在關鍵字方塊中使用 kind:microsoftteams](../media/O365-ContentSearch-Teams-Keywords.png)
  
  - <span data-ttu-id="38d1a-237">若要使用搜尋條件，請新增 **[郵件類型]** 條件，然後使用 `microsoftteams` 值。</span><span class="sxs-lookup"><span data-stu-id="38d1a-237">To use a search condition, add the **Message kind** condition and use the value `microsoftteams`.</span></span>

    ![使用郵件類型條件搭配 microsoftteams 值。](../media/O365-ContentSearch-Teams-MessageKindCondition.png)

   <span data-ttu-id="38d1a-239">條件會使用 **AND** 運算子以邏輯方式連接至關鍵字查詢。</span><span class="sxs-lookup"><span data-stu-id="38d1a-239">Conditions are logically connected to the keyword query by the **AND** operator.</span></span> <span data-ttu-id="38d1a-240">這表示項目必須同時符合關鍵字查詢和搜尋條件，才能在搜尋結果中傳回。</span><span class="sxs-lookup"><span data-stu-id="38d1a-240">That means an item must match both the keyword query and the search condition to be returned in the search results.</span></span> <span data-ttu-id="38d1a-241">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)中的「使用條件的指導方針」小節。</span><span class="sxs-lookup"><span data-stu-id="38d1a-241">For more information, see the "Guidelines for using conditions" section in [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)</span></span>
  
## <a name="searching-yammer-groups"></a><span data-ttu-id="38d1a-242">搜尋 Yammer 群組</span><span class="sxs-lookup"><span data-stu-id="38d1a-242">Searching Yammer Groups</span></span>

<span data-ttu-id="38d1a-243">您可以使用 **ItemClass** 電子郵件屬性或 **類型** 搜尋條件來搜尋 Yammer 群組中的特定交談項目。</span><span class="sxs-lookup"><span data-stu-id="38d1a-243">You can use the **ItemClass** email property or the **Type** search condition to search specifically for conversation items in Yammer Groups.</span></span>

  - <span data-ttu-id="38d1a-244">若要使用 **ItemClass** 屬性做為關鍵字搜尋查詢的一部分，請在搜尋查詢的 **[關鍵字]** 方塊中，輸入下列其中一種 (或所有)「屬性：值組」：</span><span class="sxs-lookup"><span data-stu-id="38d1a-244">To use the **ItemClass** property as part of the keyword search query, in the **Keywords** box of a search query, you can type one (or all) of the following property:value pairs:</span></span>

     - <span data-ttu-id="38d1a-245">ItemClass:IPM.Yammer.message</span><span class="sxs-lookup"><span data-stu-id="38d1a-245">ItemClass:IPM.Yammer.message</span></span>
     - <span data-ttu-id="38d1a-246">ItemClass:IPM.Yammer.poll</span><span class="sxs-lookup"><span data-stu-id="38d1a-246">ItemClass:IPM.Yammer.poll</span></span>
     - <span data-ttu-id="38d1a-247">ItemClass:IPM.Yammer.praise</span><span class="sxs-lookup"><span data-stu-id="38d1a-247">ItemClass:IPM.Yammer.praise</span></span>
     - <span data-ttu-id="38d1a-248">ItemClass:IPM.Yammer.question</span><span class="sxs-lookup"><span data-stu-id="38d1a-248">ItemClass:IPM.Yammer.question</span></span>
  
    <span data-ttu-id="38d1a-249">例如，您可以使用下列搜尋查詢來傳回 Yammer 訊息和 Yammer 稱讚項目：</span><span class="sxs-lookup"><span data-stu-id="38d1a-249">For example, you can use the following search query to return Yammer messages and Yammer praise items:</span></span>

    ![使用 ItemClass 屬性來搜尋 Yammer 項目](../media/YammerContentSearch1.png)
  
  - <span data-ttu-id="38d1a-251">您也可以使用 **類型** 電子郵件條件，然後選取 **[Yammer 訊息]** 以傳回 Yammer 項目。</span><span class="sxs-lookup"><span data-stu-id="38d1a-251">Alternatively, you can use the **Type** email condition and select **Yammer messages** to return Yammer items.</span></span> <span data-ttu-id="38d1a-252">例如，下列搜尋查詢會傳回所有包含關鍵字「保密」的 Yammer 交談項目。</span><span class="sxs-lookup"><span data-stu-id="38d1a-252">For example, the following search query will return all Yammer conversation items that contain the keyword "confidential".</span></span> 

    ![使用「類型」條件卡片來搜尋 Yammer 交談項目](../media/YammerContentSearch2.png)

## <a name="searching-inactive-mailboxes"></a><span data-ttu-id="38d1a-254">搜尋非作用中信箱</span><span class="sxs-lookup"><span data-stu-id="38d1a-254">Searching inactive mailboxes</span></span>

<span data-ttu-id="38d1a-255">您可以在內容搜尋中搜尋非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-255">You can search inactive mailboxes in a content search.</span></span> <span data-ttu-id="38d1a-256">若要取得組織中非作用中信箱的清單，請在 Exchange Online PowerShell 中執行命令 `Get-Mailbox -InactiveMailboxOnly`。</span><span class="sxs-lookup"><span data-stu-id="38d1a-256">To get a list of the inactive mailboxes in your organization, run the command  `Get-Mailbox -InactiveMailboxOnly` in Exchange Online PowerShell.</span></span> <span data-ttu-id="38d1a-257">或者，您可以移至安全性與合規性中心中的 **[資訊控管]** \> **[保留]**，然後按一下 **[更多]** ![[瀏覽列省略符號]](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **[非作用中信箱]**。</span><span class="sxs-lookup"><span data-stu-id="38d1a-257">Alternatively, you can go to **Information governance** \> **Retention** in the Security & Compliance Center, and then click **More**![Navigation Bar ellipses](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inactive mailboxes**.</span></span>
  
<span data-ttu-id="38d1a-258">搜尋非作用中信箱時，請注意以下幾點。</span><span class="sxs-lookup"><span data-stu-id="38d1a-258">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>

- <span data-ttu-id="38d1a-259">如果現有內容搜尋包含使用者信箱，且該信箱設定為非作用中，在信箱成為非作用中之後，當您重新執行搜尋時，內容搜尋會繼續搜尋非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-259">If an existing content search includes a user mailbox and that mailbox is made inactive, the content search will continue to search the inactive mailbox when you rerun the search after it becomes inactive.</span></span>

- <span data-ttu-id="38d1a-260">有時候，使用者的作用中信箱及非作用中信箱可能擁有相同的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="38d1a-260">Sometimes a user may have an active mailbox and an inactive mailbox that have the same SMTP address.</span></span> <span data-ttu-id="38d1a-261">在此情況下，僅會搜尋您選取做為內容搜尋位置的特定信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-261">In this case, only the specific mailbox that you select as a location for a content search is searched.</span></span> <span data-ttu-id="38d1a-262">換句話說，如果您將使用者的信箱新增至搜尋，您無法假設會同時搜尋其作用中和非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-262">In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes are searched.</span></span> <span data-ttu-id="38d1a-263">只會搜尋您明確地新增至搜尋的信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-263">Only the mailbox that you explicitly add to the search is searched.</span></span>

- <span data-ttu-id="38d1a-264">您可以使用安全性與合規性中心 PowerShell 來建立內容搜尋，以搜尋非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-264">You can use Security & Compliance Center PowerShell to create a content search to search an inactive mailbox.</span></span> <span data-ttu-id="38d1a-265">若要這麼做，您必須將一個句點 (.</span><span class="sxs-lookup"><span data-stu-id="38d1a-265">To do this, you have to pre-append a period ( .</span></span> <span data-ttu-id="38d1a-266">) 附加至非作用中信箱的電子郵件地址前端。</span><span class="sxs-lookup"><span data-stu-id="38d1a-266">) to the email address of the inactive mailbox.</span></span> <span data-ttu-id="38d1a-267">例如，下列命令會建立內容搜尋，搜尋電子郵件地址為 pavelb@contoso.onmicrosoft.com 的非作用中信箱：</span><span class="sxs-lookup"><span data-stu-id="38d1a-267">For example, the following command creates a content search that searches an inactive mailbox with the email address pavelb@contoso.onmicrosoft.com:</span></span>

   ```powershell
   New-ComplianceSearch -Name InactiveMailboxSearch -ExchangeLocation .pavelb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
   ```

- <span data-ttu-id="38d1a-268">我們強烈建議您避免使用具有相同 SMTP 地址的作用中信箱及非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-268">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address.</span></span> <span data-ttu-id="38d1a-269">如果您需要重複使用已指派給非作用中信箱的 SMTP 地址，建議您復原非作用中信箱，或將非作用中信箱的內容還原為作用中信箱 (或者作用中信箱的封存)，然後刪除非作用中信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-269">If you need to reuse the SMTP address that is assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox.</span></span> <span data-ttu-id="38d1a-270">如需詳細資訊，請參閱下列其中一個主題：</span><span class="sxs-lookup"><span data-stu-id="38d1a-270">For more information, see one of the following topics:</span></span>

  - [<span data-ttu-id="38d1a-271">在 Office 365 中復原非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="38d1a-271">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)

  - [<span data-ttu-id="38d1a-272">在 Office 365 中還原非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="38d1a-272">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)

  - [<span data-ttu-id="38d1a-273">在 Office 365 中刪除非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="38d1a-273">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

## <a name="searching-disconnected-or-de-licensed-mailboxes"></a><span data-ttu-id="38d1a-274">搜尋連線中斷或取消授權的信箱</span><span class="sxs-lookup"><span data-stu-id="38d1a-274">Searching disconnected or de-licensed mailboxes</span></span>

<span data-ttu-id="38d1a-275">如果您從使用者帳戶或 Azure Active Directory 中移除 Exchange Online 授權 (或整個 Microsoft 365 授權)，該使用者的信箱就會變成「連線中斷」的信箱。</span><span class="sxs-lookup"><span data-stu-id="38d1a-275">If the Exchange Online license (or the entire Microsoft 365 license) is removed from a user account or in Azure Active Directory, the user's mailbox becomes a *disconnected* mailbox.</span></span> <span data-ttu-id="38d1a-276">這表示信箱已不再與使用者帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="38d1a-276">This means that the mailbox is no longer associated with the user account.</span></span> <span data-ttu-id="38d1a-277">搜尋中斷連線的信箱時，會發生以下狀況：</span><span class="sxs-lookup"><span data-stu-id="38d1a-277">Here's what happens when searching disconnected mailboxes:</span></span>

- <span data-ttu-id="38d1a-278">如果從信箱移除授權，信箱即不再可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="38d1a-278">If the license is removed from a mailbox, the mailbox is no longer searchable.</span></span> 

- <span data-ttu-id="38d1a-279">如果現有的內容搜尋包含已移除授權的信箱，如果您重新執行內容搜尋，則不會從已中斷連線的信箱傳回任何搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="38d1a-279">If an existing content search includes a mailbox in which the license is removed, no search results from the disconnected mailbox will be returned if you rerun the content search.</span></span>

- <span data-ttu-id="38d1a-280">如果您使用 **New-ComplianceSearch** Cmdlet 來建立內容搜尋，並將中斷連線的信箱指定為要搜尋的 Exchange 內容位置，內容搜尋將不會從已中斷連線的信箱傳回任何搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="38d1a-280">If you use the **New-ComplianceSearch** cmdlet to create a content search and specify a disconnected mailbox as the Exchange content location to search, the content search won't return any search results from the disconnected mailbox.</span></span>

<span data-ttu-id="38d1a-281">如果您要保留已中斷連線信箱中的資料，使其可供搜尋，您必須在移除授權之前，先在信箱上放置保留。</span><span class="sxs-lookup"><span data-stu-id="38d1a-281">If you need to preserve the data in a disconnected mailbox so that it's searchable, you must place a hold on the mailbox before removing the license.</span></span> <span data-ttu-id="38d1a-282">這麼做會保留資料，並在移除保留之前讓中斷連線的信箱可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="38d1a-282">This preserves the data and keeps the disconnected mailbox searchable until the hold is removed.</span></span> <span data-ttu-id="38d1a-283">如需保留的詳細資訊，請參閱[如何找出位於 Exchange Online 信箱的保留類型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="38d1a-283">For more information about holds, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="searching-for-content-in-a-sharepoint-multi-geo-environment"></a><span data-ttu-id="38d1a-284">在 SharePoint 多地理位置環境中搜尋內容</span><span class="sxs-lookup"><span data-stu-id="38d1a-284">Searching for content in a SharePoint Multi-Geo environment</span></span>

<span data-ttu-id="38d1a-285">如果電子文件探索管理員需要在 [SharePoint 多地理位置環境](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)中的不同區域中搜尋 SharePoint 和 OneDrive 中的內容，則需要執行以下操作才能進行：</span><span class="sxs-lookup"><span data-stu-id="38d1a-285">If it's necessary for an eDiscovery manager to search for content in SharePoint and OneDrive in different regions in a [SharePoint multi-geo environment](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md), then you need to do the following things to make that happen:</span></span>

1. <span data-ttu-id="38d1a-286">為電子文件探索管理員需要搜尋的每個衛星地理位置建立個別的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="38d1a-286">Create a separate user account for each satellite geo location that the eDiscovery manager needs to search.</span></span> <span data-ttu-id="38d1a-287">若要在該地理位置中的網站搜尋內容，電子文件探索管理員必須登入您為該位置建立的帳戶，然後再執行內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="38d1a-287">To search for content in sites in that geo location, the eDiscovery manager must sign in to the account you created for that location and then run a content search.</span></span>

2. <span data-ttu-id="38d1a-288">為電子文件探索管理員需要搜尋的每個衛星地理位置 (以及相應的使用者帳戶) 建立搜尋權限篩選條件。</span><span class="sxs-lookup"><span data-stu-id="38d1a-288">Create a search permissions filter for each satellite geo location (and corresponding user account) the eDiscovery manager needs to search.</span></span> <span data-ttu-id="38d1a-289">當電子文件探索管理員登入與該位置關聯的使用者帳戶時，每一個搜尋權限篩選條件都會將內容搜尋的範圍限制為特定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="38d1a-289">Each of these search permissions filters limits the scope of the content search to a specific geo location when the eDiscovery manager is signed in to the user account associated with that location.</span></span>

> [!TIP]
> <span data-ttu-id="38d1a-290">在 [[進階電子文件探索]](overview-ediscovery-20.md) 中使用搜尋工具時，您不必使用此策略。</span><span class="sxs-lookup"><span data-stu-id="38d1a-290">You don't have to use this strategy when using the search tool in [Advanced eDiscovery](overview-ediscovery-20.md).</span></span> <span data-ttu-id="38d1a-291">這是因為在進階電子文件探索中搜尋 SharePoint 網站和OneDrive 帳戶時，會搜尋所有資料中心。</span><span class="sxs-lookup"><span data-stu-id="38d1a-291">That's because all datacenters are searched when you search SharePoint sites and OneDrive accounts in Advanced eDiscovery.</span></span> <span data-ttu-id="38d1a-292">只有在使用內容搜尋工具並執行與[電子文件探索案例](./get-started-core-ediscovery.md)相關聯的搜尋時，才必須使用這個特定區域使用者帳戶和搜尋權限篩選器的策略。</span><span class="sxs-lookup"><span data-stu-id="38d1a-292">You have to use this strategy of region-specific user accounts and search permissions filters only when using the Content Search tool and running searches associated with [eDiscovery cases](./get-started-core-ediscovery.md).</span></span>

<span data-ttu-id="38d1a-293">例如，假設電子文件探索管理員需要在北美、歐洲和亞太地區的衛星位置搜尋 SharePoint 和 OneDrive 內容。</span><span class="sxs-lookup"><span data-stu-id="38d1a-293">For example, let's say that an eDiscovery manager needs to search for SharePoint and OneDrive content in satellite locations in North American, Europe, and Asia Pacific.</span></span> <span data-ttu-id="38d1a-294">第一個步驟是建立三個使用者帳戶，每個位置一個。</span><span class="sxs-lookup"><span data-stu-id="38d1a-294">The first step is to create three users accounts, one for each location.</span></span> <span data-ttu-id="38d1a-295">下一步是建立三個搜尋權限篩選條件，每個位置及相應的使用者帳戶一個。</span><span class="sxs-lookup"><span data-stu-id="38d1a-295">The next step is to create three search permissions filters, one for each location *and* corresponding user account.</span></span> <span data-ttu-id="38d1a-296">以下是此案例的三個搜尋權限篩選條件的範例。</span><span class="sxs-lookup"><span data-stu-id="38d1a-296">Here are examples of the three search permissions filters for this scenario.</span></span> <span data-ttu-id="38d1a-297">在每個範例中，**[區域]** 指定該地理位置的 SharePoint 資料中心位置，**[使用者]** 參數指定相應的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="38d1a-297">In each of these examples, the **Region** specifies the SharePoint datacenter location for that geo and the **Users** parameter specifies the corresponding user account.</span></span>

<span data-ttu-id="38d1a-298">**北美**</span><span class="sxs-lookup"><span data-stu-id="38d1a-298">**North America**</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-NAM" -Users ediscovery-nam@contoso.com -Region NAM -Action ALL
```

<span data-ttu-id="38d1a-299">**歐洲**</span><span class="sxs-lookup"><span data-stu-id="38d1a-299">**Europe**</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-EUR" -Users ediscovery-eur@contoso.com -Region EUR -Action ALL
```

<span data-ttu-id="38d1a-300">**亞太地區**</span><span class="sxs-lookup"><span data-stu-id="38d1a-300">**Asia Pacific**</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-APC" -Users ediscovery-apc@contoso.com -Region APC -Action ALL
```

<span data-ttu-id="38d1a-301">使用搜尋權限篩選條件在多地理位置環境中搜尋內容時，請記住以下事項：</span><span class="sxs-lookup"><span data-stu-id="38d1a-301">Keep the following things in mind when using search permissions filters to search for content in multi-geo environments:</span></span>

- <span data-ttu-id="38d1a-302">**[地區]** 參數會指示搜尋特定的衛星位置。</span><span class="sxs-lookup"><span data-stu-id="38d1a-302">The **Region** parameter directs searches to the specified satellite location.</span></span> <span data-ttu-id="38d1a-303">如果電子文件探索管理員只搜尋搜尋權限篩選器指定之區域以外的 SharePoint 和 OneDrive 網站，則不會傳回搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="38d1a-303">If an eDiscovery manager only searches SharePoint and OneDrive sites outside of the region specified in the search permissions filter, no search results are returned.</span></span> 

- <span data-ttu-id="38d1a-304">**[地區]** 參數不會控制 Exchange 信箱的搜尋。</span><span class="sxs-lookup"><span data-stu-id="38d1a-304">The **Region** parameter doesn't control searches of Exchange mailboxes.</span></span> <span data-ttu-id="38d1a-305">搜尋信箱時，也會搜尋所有資料中心。</span><span class="sxs-lookup"><span data-stu-id="38d1a-305">All datacenters are searched when you search mailboxes.</span></span>

<span data-ttu-id="38d1a-306">如需在多地理位置環境中使用搜尋權限篩選條件的詳細資訊，請參閱[設定電子文件探索調查的合規性界限](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments)中的「搜尋和匯出在多地理位置環境中的內容」這一節。</span><span class="sxs-lookup"><span data-stu-id="38d1a-306">For more information about using search permissions filters in a multi-geo environment, see the "Searching and exporting content in Multi-Geo environments" section in [Set up compliance boundaries for eDiscovery investigations](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).</span></span>
