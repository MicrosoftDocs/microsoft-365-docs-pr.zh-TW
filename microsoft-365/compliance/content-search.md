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
ms.openlocfilehash: 5f48418882d5d4c7589b3ef394a0a306c0675f34
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332843"
---
# <a name="create-a-content-search"></a>建立內容搜尋

您可以使用 Microsoft 365 合規性中心中的內容搜尋電子文件探索工具搜尋就地內容，例如組織中的電子郵件、文件和立即訊息交談。 使用此工具在這些 Microsoft 365 資料來源中搜尋內容：
  
- Exchange Online 信箱

- SharePoint Online 網站和商務用 OneDrive 帳戶

- Microsoft Teams

- Microsoft 365 群組

- Yammer 群組

執行搜尋之後，搜尋飛出頁面中會顯示內容位置數目及預估的搜尋結果數目。 您可以快速檢視統計資料，例如最多項目符合搜尋查詢的內容位置。 執行搜尋後，您可以預覽結果或將結果匯出到本機電腦上。

## <a name="create-and-run-a-search"></a>建立並執行搜尋

若要存取 Microsoft 365 合規性中心中的 [內容搜尋] 頁面以執行搜尋和預覽並匯出搜尋結果，系統管理員、法務人員或電子文件探索管理員必須是 [安全性與合規性中心] 中的電子文件探索管理員角色群組成員。 如需詳細資訊，請參閱[指派電子文件探索權限](assign-ediscovery-permissions.md)。
  
1. 前往 <https://compliance.microsoft.com>，然後使用已指派適當權限的帳號認證登入。

2. 在 Microsoft 365 合規性中心的左瀏覽窗格中，按一下 **[顯示全部]**，然後按一下 **[內容搜尋]**。

3. 在 **[内容搜尋]** 頁面上，按一下 **[新增搜尋]**。

   > [!NOTE]
   > [依識別碼清單搜尋] 選項可讓您使用 Exchange 識別碼的清單來搜尋特定的電子郵件訊息和其他信箱項目。 若要建立識別碼清單搜尋，您可以提交逗點分隔值 (CSV) 檔案，以識別要搜尋的特定信箱項目。 如需相關指示，請參閱[為備識別碼清單搜尋準備 CSV 檔案](csv-file-for-an-id-list-content-search.md)。

4. 輸入搜尋的名稱，以及可協助識別搜尋的選擇性描述。 搜尋的名稱在組織中必須是唯一的。

5. 在 [位置] 頁面上，選擇您想要搜尋的內容位置。 您可以搜尋信箱、網站與公用資料夾。

    ![選擇要設定保存措施的內容位置](../media/ContentSearchLocations.png)
  
   1. **Exchange 信箱**：將開關設定為 [開啟] ，然後按一下 [選擇使用者、群組或團隊] 以指定要設定保存措施的信箱。 使用搜尋方塊來尋找使用者信箱及通訊群組 (以在群組成員的信箱上設定保存措施) 以設定保存措施。 您也可以搜尋與 Microsoft Teams （頻道訊息）、Office 365 群組和 Yammer 群組相關聯的信箱。 如需儲存在信箱中的應用程式資料詳細資訊，請參閱[儲存在電子文件探索信箱中的內容](what-is-stored-in-exo-mailbox.md) (部分機器翻譯)。

   2. **SharePoint 網站**：將開關設定為 [開啟] 然後按一下 [選擇網站] 以指定要設定保存措施的 SharePoint 網站和 OneDrive 帳戶。 針對您想要設定保存措施的每個網站，輸入其 URL。 您也可以新增 Microsoft Teams、Office 365 群組或 Yammer 群組的 SharePoint 網站的 URL。
  
   3. **Exchange 公用資料夾**：將開關設定為 [開啟] 以保存 Exchange Online 組織的所有公用資料夾。 無法選擇保存特定公用資料夾。 如果您不想保存公用資料夾，請讓切換開關保持關閉。
  
   4. 保留選取此核取方塊以搜尋內部部署使用者的 Teams 內容。 例如，如果您要搜尋組織中的所有 Exchange 信箱並選取此核取方塊，用於儲存內部部署使用者的 Teams 聊天資料的雲端式儲存空間將會包含在搜尋範圍中。 如需詳細資訊，請參閱[搜尋內部部署使用者的 Teams 聊天資料](search-cloud-based-mailboxes-for-on-premises-users.md)。

6. 在 [定義搜尋條件] 頁面上，輸入關鍵字查詢，並在必要時將條件新增到搜尋查詢。

   ![設定搜尋查詢](../media/ContentSearchQuery.png)

   1. 指定關鍵字、例如傳送和接收日期的郵件內容，或者例如檔案名稱或文件上次變更日期的文件內容。 您可以使用內含布林運算子，較為複雜的查詢，例如 **AND**、**OR**、**NOT** 和 **NEAR**。 如果將關鍵字方塊保留空白，則位於指定內容位置的所有內容都會包含在搜尋結果中。 如需詳細資訊，請參閱[電子文件探索的的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md) (部分機器翻譯)。

   2. 或者，您可以按一下 **[顯示關鍵字清單]** 核取方塊，然後在每一列中輸入關鍵字。 如果您這麼做，每一列的關鍵字會以邏輯運算子 (**c:s**) 連接，其功能與建立的搜尋查詢中的 **OR** 運算子類似。

      為什麼要使用關鍵字清單？ 您可以取得會顯示有多少個項目符合每個關鍵字的統計資料。 這可協助您快速找出哪些關鍵字最有效(和最不有效)。 您也可以在一列中使用關鍵字片語 (以括號括住)。 如需關鍵字清單和搜尋統計資料的詳細資訊，請參閱[取得搜尋的關鍵字統計資料](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)。

      > [!NOTE]
      > 為了協助降低大量關鍵字清單造成的問題，關鍵字清單中最多只能有 20 列。

   3. 您可以新增搜尋條件來縮小搜尋範圍，並傳回更精簡的結果集。 每個條件會將一個子句新增至在啟動搜尋時便會建立並執行的搜尋查詢中。 條件會在邏輯上使用功能上與 **AND** 運算子類似的邏輯運算子 (**c:c**) 與關鍵字查詢連結 (在關鍵字方塊中指定)。 這表示結果中包含的項目必須同時滿足關鍵字查詢與一或多個條件。 這是條件協助縮小搜尋結果的方式。 有關可在搜尋查詢中使用的條件清單和描述，請參閱[搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)。

7. 檢閱搜尋設定 (並在必要時編輯)，然後提交搜尋以啟動搜尋。
  
若要再次存取此內容搜尋，或存取 **[內容搜尋]** 頁面上所列的其他內容搜尋，請選取搜尋，然後按一下 **[開啟]**。

## <a name="next-steps"></a>後續步驟

以下是建立和執行內容搜尋之後要執行的後續步驟清單。

- [預覽搜尋結果](preview-ediscovery-search-results.md)

- [檢視搜尋結果的統計資料](view-keyword-statistics-for-content-search.md)

- [匯出搜尋結果](export-search-results.md)

- [匯出搜尋報告](export-a-content-search-report.md)

## <a name="more-information"></a>其他資訊

如需內容搜尋 (例如在不同 Microsoft 365 服務中搜尋內容) 的詳細資訊，請參閱[內容搜尋的功能參考](content-search-reference.md)。
