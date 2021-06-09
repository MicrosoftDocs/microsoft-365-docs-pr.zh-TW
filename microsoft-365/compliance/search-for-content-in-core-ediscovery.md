---
title: 在核心 eDiscovery 案例中搜尋內容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 搜尋可能與核心 eDiscovery 案例相關的內容。
ms.openlocfilehash: 8d2e2a20135312a8f111a071abbe77b03b8e8363
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311771"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>在核心 eDiscovery 案例中搜尋內容

在建立核心 eDiscovery 案例，並將案例中的相關人員設定為暫止狀態之後，您可以建立並執行一或多個搜尋與案例相關的內容。 與核心 eDiscovery 案例相關聯的搜尋並未列在「Microsoft 365 規範中心」的 [**內容搜尋**] 頁面上。 這些搜尋會列在核心 eDiscover 案例的 [ **搜尋** ] 頁面上，與搜尋產生關聯。 這也表示只有案例成員才能存取與案例相關聯的搜尋。

若要建立核心 eDiscovery 搜尋：
  
1. 移至 <https://compliance.microsoft.com> 並登入使用已獲指派適當 eDiscovery 許可權之使用者帳戶的認證，而且是案例的成員。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [**全部顯示**]，然後按一下 [ **eDiscovery > Core**]。

3. 在 [ **核心電子** 檔探索] 頁面上，選取您要建立相關聯搜尋的案例，然後按一下 [ **開啟案例**]。

4. 在案例的 **首頁** 上，按一下 [ **搜尋** ] 索引標籤，然後按一下 [ **新增搜尋**]。

   ![按一下 [新增搜尋] 以建立核心 eDiscovery 搜尋搜尋](../media/CoreeDiscoverySearch1.png)

   > [!NOTE]
   > [依識別碼清單搜尋] 選項可讓您使用 Exchange 識別碼的清單來搜尋特定的電子郵件訊息和其他信箱項目。 若要建立識別碼清單搜尋，您可以提交逗點分隔值 (CSV) 檔案，以識別要搜尋的特定信箱項目。 如需相關指示，請參閱[為備識別碼清單搜尋準備 CSV 檔案](csv-file-for-an-id-list-content-search.md)。

5. 在 [ **新增搜尋** 嚮導] 中，輸入搜尋的名稱，以及可協助識別搜尋的選擇性描述。 搜尋的名稱在組織中必須是唯一的。

6. 在 [位置] 頁面上，選擇您想要搜尋的內容位置。 您可以搜尋信箱、網站與公用資料夾。

    ![選擇要設定保存措施的內容位置](../media/ContentSearchLocations.png)
  
   1. **Exchange 信箱**：將開關設定為 [開啟] ，然後按一下 [選擇使用者、群組或團隊] 以指定要設定保存措施的信箱。 使用搜尋方塊來尋找使用者信箱及通訊群組 (以在群組成員的信箱上設定保存措施) 以設定保存措施。 您也可以搜尋與 Microsoft Teams （頻道訊息）、Office 365 群組和 Yammer 群組相關聯的信箱。 如需儲存在信箱中的應用程式資料詳細資訊，請參閱[儲存在電子文件探索信箱中的內容](what-is-stored-in-exo-mailbox.md) (部分機器翻譯)。

   2. **SharePoint 網站**：將開關設定為 [開啟] 然後按一下 [選擇網站] 以指定要設定保存措施的 SharePoint 網站和 OneDrive 帳戶。 針對您想要設定保存措施的每個網站，輸入其 URL。 您也可以新增 Microsoft Teams、Office 365 群組或 Yammer 群組的 SharePoint 網站的 URL。
  
   3. **Exchange 公用資料夾**：將開關設定為 [開啟] 以保存 Exchange Online 組織的所有公用資料夾。 無法選擇保存特定公用資料夾。 如果您不想保存公用資料夾，請讓切換開關保持關閉。
  
   4. 保留選取此核取方塊以搜尋內部部署使用者的 Teams 內容。 例如，如果您要搜尋組織中的所有 Exchange 信箱並選取此核取方塊，用於儲存內部部署使用者的 Teams 聊天資料的雲端式儲存空間將會包含在搜尋範圍中。 如需詳細資訊，請參閱[搜尋內部部署使用者的 Teams 聊天資料](search-cloud-based-mailboxes-for-on-premises-users.md)。

7. 在 [定義搜尋條件] 頁面上，輸入關鍵字查詢，並在必要時將條件新增到搜尋查詢。

   ![設定搜尋查詢](../media/ContentSearchQuery.png)

   1. 指定關鍵字、例如傳送和接收日期的郵件內容，或者例如檔案名稱或文件上次變更日期的文件內容。 您可以使用內含布林運算子，較為複雜的查詢，例如 **AND**、**OR**、**NOT** 和 **NEAR**。 如果將關鍵字方塊保留空白，則位於指定內容位置的所有內容都會包含在搜尋結果中。 如需詳細資訊，請參閱[電子文件探索的的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md) (部分機器翻譯)。

   2. 或者，您可以按一下 **[顯示關鍵字清單]** 核取方塊，然後在每一列中輸入關鍵字。 如果您這麼做，每一列的關鍵字會以邏輯運算子 (**c:s**) 連接，其功能與建立的搜尋查詢中的 **OR** 運算子類似。

      為什麼要使用關鍵字清單？ 您可以取得會顯示有多少個項目符合每個關鍵字的統計資料。 這可協助您快速找出哪些關鍵字最有效(和最不有效)。 您也可以在一列中使用關鍵字片語 (以括號括住)。 如需關鍵字清單和搜尋統計資料的詳細資訊，請參閱[取得搜尋的關鍵字統計資料](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)。

      > [!NOTE]
      > 為了協助降低大量關鍵字清單造成的問題，關鍵字清單中最多只能有 20 列。

   3. 您可以新增搜尋條件來縮小搜尋範圍，並傳回更精簡的結果集。 每個條件會將一個子句新增至在啟動搜尋時便會建立並執行的搜尋查詢中。 條件會在邏輯上使用功能上與 **AND** 運算子類似的邏輯運算子 (**c:c**) 與關鍵字查詢連結 (在關鍵字方塊中指定)。 這表示結果中包含的項目必須同時滿足關鍵字查詢與一或多個條件。 這是條件協助縮小搜尋結果的方式。 有關可在搜尋查詢中使用的條件清單和描述，請參閱[搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)。

8. 檢閱搜尋設定 (並在必要時編輯)，然後提交搜尋以啟動搜尋。

在搜尋完成之後，您可以預覽搜尋結果。 如有必要， **請按一下** [ **搜尋** ] 頁面上的 [重新整理]，以顯示您建立的搜尋。

## <a name="more-information-about-searching-content-locations"></a>搜尋內容位置的詳細資訊

- 當您按一下 **[選擇使用者、群組或小組** 以指定要搜尋的信箱] 時，顯示的信箱選擇器會是空的。 這項設計的目的是提升效能。 若要將收件者新增至此清單，請按一下 **[選擇使用者、群組或小組**]，然後在搜尋方塊中輸入 (至少三個字元的名稱) 中，選取名稱旁邊的核取方塊，然後按一下 [ **選擇**]。

- 您可以將非使用中的信箱、Microsoft Teams、Yammer 群組、Office 365 群組和通訊群組新增至要搜尋的信箱清單。 不支援動態通訊群組。 如果您新增 Microsoft Teams、Yammer 群組或 Office 365 群組，則會搜尋群組或小組信箱;不會搜尋群組成員的信箱。

- 若要將網站新增至搜尋，請開啟切換，然後按一下 **[選擇網站**]。 輸入每個要搜尋之網站的 URL。 您也可以為 Microsoft 團隊、Yammer 群組或 Office 365 群組新增 SharePoint 網站的 URL。
