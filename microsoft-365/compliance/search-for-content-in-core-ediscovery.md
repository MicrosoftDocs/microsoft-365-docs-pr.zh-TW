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
   > [**依識別碼搜尋] 清單** 選項可讓您使用 Exchange IDs 清單來搜尋特定的電子郵件及其他信箱專案。 若要建立識別碼清單搜尋，您可以提交逗點分隔值 (CSV) 檔案，以識別要搜尋的特定信箱項目。 如需相關指示，請參閱[為備識別碼清單搜尋準備 CSV 檔案](csv-file-for-an-id-list-content-search.md)。

5. 在 [ **新增搜尋** 嚮導] 中，輸入搜尋的名稱，以及可協助識別搜尋的選擇性描述。 搜尋的名稱在您的組織中必須是唯一的。

6. 在 [ **位置** ] 頁面上，選擇您要搜尋的內容位置。 您可以搜尋信箱、網站和公用資料夾。

    ![選擇要保留的內容位置](../media/ContentSearchLocations.png)
  
   1. **Exchange 信箱**：將切換設定為 [**開啟**]，然後按一下 **[選擇使用者、群組或小組**]，以指定要置於保留狀態的信箱。 使用 [搜尋] 方塊來尋找使用者信箱和通訊群組 (將保留在群組成員的信箱上) 進行暫止。 您也可以在與 Microsoft Team (相關聯的信箱中搜尋) 、Office 365 群組及 Yammer 群組相關聯的信箱。 如需信箱中所儲存之應用程式資料的詳細資訊，請參閱 [儲存在信箱中的內容，以取得 eDiscovery](what-is-stored-in-exo-mailbox.md)。

   2. **SharePoint 網站**：將切換設定為 [**開啟**]，然後按一下 **[選擇網站**]，以指定要保留 SharePoint 網站和 OneDrive 帳戶。 輸入您要保留之每個網站的 URL。 您也可以為 Microsoft 團隊、Office 365 群組或 Yammer 群組新增 SharePoint 網站的 URL。
  
   3. **Exchange 公用資料夾**：設定 **開啟開啟 Exchange Online** 組織中的所有公用資料夾保留。 您無法選擇要保留的特定公用資料夾。 如果您不想要保留公用資料夾，請停用切換參數。
  
   4. 選取此核取方塊可搜尋內部部署使用者的 Teams 內容。 例如，如果您搜尋組織中的所有 Exchange 信箱，並選取此核取方塊，則用來儲存內部部署使用者 Teams 聊天資料的雲端式儲存裝置將會包含在搜尋範圍內。 如需詳細資訊，請參閱[搜尋內部部署使用者的 Teams 聊天資料](search-cloud-based-mailboxes-for-on-premises-users.md)。

7. 在 [ **定義搜尋條件** ] 頁面上，輸入關鍵字查詢，並視需要將條件新增至搜尋查詢。

   ![設定搜尋查詢](../media/ContentSearchQuery.png)

   1. 指定關鍵字、郵件內容（如已傳送和接收的日期）或檔案屬性（如檔案名或檔最後變更的日期）。 您可以使用內含布林運算子的更複雜的查詢，例如 **AND**、**OR**、**NOT** 和 **NEAR**。 如果將關鍵字方塊保留空白，則位於指定內容位置的所有內容都會包含在搜尋結果中。 如需詳細資訊，請參閱 [eDiscovery 的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。

   2. 或者，您可以按一下 **[顯示關鍵字清單]** 核取方塊，然後在每一列中輸入關鍵字。 如果您這麼做，每一列的關鍵字會以邏輯運算子 (**c:s**) 連接，其功能與建立的搜尋查詢中的 **OR** 運算子類似。

      為什麼要使用關鍵字清單？ 您可以取得會顯示有多少個項目符合每個關鍵字的統計資料。 這可協助您快速找出哪些關鍵字最有效(和最不有效)。 您也可以在一列中使用關鍵字片語 (以括號括住)。 如需關鍵字清單和搜尋統計資料的詳細資訊，請參閱 [取得搜尋的關鍵字統計資料](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)。

      > [!NOTE]
      > 為了避免大型關鍵字清單所造成的問題，您最多隻能有20列的關鍵字清單。

   3. 您可以新增搜尋條件以縮小搜尋範圍，並傳回更精簡的結果集。 每個條件會將一個子句新增至在啟動搜尋時便會建立並執行的搜尋查詢中。 條件會在邏輯上使用功能上與 **AND** 運算子類似的邏輯運算子 (**c:c**) 與關鍵字查詢連結 (在關鍵字方塊中指定)。 這表示結果中包含的項目必須同時滿足關鍵字查詢與一或多個條件。 這是條件協助縮小搜尋結果的方式。 有關可在搜尋查詢中使用的條件清單和描述，請參閱[搜尋條件](keyword-queries-and-search-conditions.md#search-conditions)。

8. 複查搜尋設定 (並在必要時進行編輯) ，然後提交搜尋加以啟動。

在搜尋完成之後，您可以預覽搜尋結果。 如有必要， **請按一下** [ **搜尋** ] 頁面上的 [重新整理]，以顯示您建立的搜尋。

## <a name="more-information-about-searching-content-locations"></a>搜尋內容位置的詳細資訊

- 當您按一下 **[選擇使用者、群組或小組** 以指定要搜尋的信箱] 時，顯示的信箱選擇器會是空的。 這項設計的目的是提升效能。 若要將收件者新增至此清單，請按一下 **[選擇使用者、群組或小組**]，然後在搜尋方塊中輸入 (至少三個字元的名稱) 中，選取名稱旁邊的核取方塊，然後按一下 [ **選擇**]。

- 您可以將非使用中的信箱、Microsoft Teams、Yammer 群組、Office 365 群組和通訊群組新增至要搜尋的信箱清單。 不支援動態通訊群組。 如果您新增 Microsoft Teams、Yammer 群組或 Office 365 群組，則會搜尋群組或小組信箱;不會搜尋群組成員的信箱。

- 若要將網站新增至搜尋，請開啟切換，然後按一下 **[選擇網站**]。 輸入每個要搜尋之網站的 URL。 您也可以為 Microsoft 團隊、Yammer 群組或 Office 365 群組新增 SharePoint 網站的 URL。
