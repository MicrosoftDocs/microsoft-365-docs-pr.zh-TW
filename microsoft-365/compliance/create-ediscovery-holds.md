---
title: 在核心 eDiscovery 案例中建立 eDiscovery 存放
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
description: 您可以建立與核心 eDiscovery 案例相關聯的保留，以保留可能與調查相關的內容。
ms.openlocfilehash: b3a213e499a71356999367deff930ea9a04945df
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127520"
---
# <a name="create-an-ediscovery-hold"></a>建立電子文件探索保留

您可以使用核心 eDiscovery 案例來建立保留，以保留可能與案例相關的內容。 您可以針對在案例中所調查之人員的商務客戶，保留 Exchange 信箱和 OneDrive。 您也可以在與 Microsoft 小組、Office 365 群組和 Yammer 群組相關聯的信箱和網站上放置保留。 當您將內容位置置於保留狀態時，會保留內容，直到您從內容位置移除保留，或刪除保留為止。

在您建立 eDiscovery 保留後，可能需要長達24小時，保留才會生效。 

當您建立保留時，您可以使用下列選項來限定保留在指定內容位置的內容：
  
- 您可以建立無限保留，其中指定位置的所有內容都會處於暫止狀態。 或者，您可以建立以查詢為基礎的保留，其中只有符合搜尋查詢之指定位置的內容處於暫止狀態。

- 您可以指定日期範圍，只保留在該日期範圍內傳送、接收或建立的內容。 或者，您也可以保留指定位置的所有內容，不論它是在何時傳送、接收或建立。
  
## <a name="how-to-create-an-ediscovery-hold"></a>如何建立電子檔保留

若要建立與核心 eDiscovery 案例相關聯的 eDiscovery 保留：
  
1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並登入使用已獲指派適當 eDiscovery 許可權之使用者帳戶的認證。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [**全部顯示**]，然後按一下 [ **eDiscovery > Core**]。

3. 在 [**核心電子**檔探索] 頁面上，選取您要在其中建立保留的案例，然後按一下 [**開啟案例**]。

4. 在案例的**首頁**上，按一下 [**保留**] 索引標籤。
  
5. 在 [**保留**] 頁面上，按一下 [**建立**]。

6. 在 [**命名您的保留**嚮導] 頁面上，提供 [保留名稱] 並新增選用描述，然後按 **[下一步]**。 [保留] 的名稱在您的組織中必須是唯一的。

7. 在 [**內容位置**] 頁面上，選擇您要保留的內容位置。 您可以將信箱、網站和公用資料夾放入暫止狀態。

    ![選擇要保留的內容位置](../media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   a. **信箱位置**-按一下 **[選擇使用者、群組或小組**]，然後按一下 **[選擇使用者、群組或小組**]，以指定要置於保留狀態的信箱。 使用搜尋方塊來尋找使用者信箱和通訊群組（保留信箱的群組成員）以保留。 您也可以在 Microsoft 小組、Office 365 群組或 Yammer 群組的相關信箱上放置保留。 選取 [使用者、群組、小組] 核取方塊，按一下 **[選擇**]，然後按一下 [**完成**]。

   b. **網站位置**-按一下 **[選擇網站**]，然後按一下 **[選擇網站**]，以指定要保留的 SharePoint 和 OneDrive 帳戶。 輸入您要保留之每個網站的 URL。 您也可以為 Microsoft 團隊、Office 365 群組或 Yammer 群組新增 SharePoint 網站的 URL。 按一下 **[選擇**]，然後按一下 [**完成**]。
  
   c. **Exchange 公用資料夾。** 將切換切換切換 ![ 控制項移 ](../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 至 [**全部**] 位置，將 Exchange Online 組織中的所有公用資料夾保留。 您無法選擇要保留的特定公用資料夾。 如果您不想要保留公用資料夾，請將切換參數設為 [**無**]。

   > [!NOTE]
   > 您必須將至少一個內容位置新增至保留。 否則，eDiscovery 保留靜態會顯示沒有任何專案處於保留狀態。

8. 當您完成將內容位置新增至保留狀態時，按 **[下一步]**。

9. 若要建立查詢式保留與條件，請完成下列。 否則，若要保留指定內容位置中的所有內容，請按 **[下一步]**。

    ![使用條件建立以查詢為基礎的保留](../media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    a. 在 [**關鍵字**] 下方的方塊中，輸入搜尋查詢，只保留符合搜尋準則的內容。 您可以指定關鍵字、電子郵件訊息屬性或檔案屬性，例如檔案名。 您也可以使用更複雜的查詢，使用布林運算子，例如**AND**、 **or**或**NOT**。

    b. 按一下 [**新增條件**] 以新增一或多個條件，以縮小保留的搜尋查詢。 每個條件都會將子句新增至您建立保留時所建立並執行的 KQL 搜尋查詢。 例如，您可以指定日期範圍，讓在日期範圍內建立的電子郵件或網站檔處於暫止狀態。 **And**運算子會以邏輯方式連線至關鍵字查詢（在 [**關鍵字**] 方塊中指定）。 這表示專案必須同時滿足關鍵字查詢和要保留的條件。

    如需建立搜尋查詢和使用條件的詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。

10. 設定查詢型保留後，請按 **[下一步]**。

11. 請複查您的設定（必要時進行編輯），然後按一下 [**建立此保留**]。

## <a name="query-based-holds-placed-on-site-documents"></a>放在網站檔上的查詢式保留

當您為位於 SharePoint 網站中的檔放置以查詢為基礎的 eDiscovery 保留時，請記住下列事項：

- 以查詢為基礎的保留會在刪除網站時，一小段時間內保留所有檔。 這表示當檔遭到刪除時，它會移至 [保留] 存放庫，即使它不符合查詢型保留的準則也是一樣。 不過，已刪除但不符合查詢型保留的檔，會被處理保留的保留庫的計時器工作移除。 計時器工作會定期執行，並將保留保留文件庫中的所有檔，與您查詢的 eDiscovery 保留（以及其他類型的保留和保留原則）進行比較。 計時器工作會刪除不符合查詢型保留的檔，並保留所做的檔。

- 查詢型保留不能用來執行目標保留，例如保留特定資料夾或網站中的檔，或使用其他以位置為基礎的保留準則。 這樣做可能會產生非預期的結果。 我們建議使用非位置的保留準則（如關鍵字、日期範圍或其他檔案屬性）來保留網站檔。

## <a name="ediscovery-hold-statistics"></a>eDiscovery 保留統計資料

在您建立 eDiscovery 暫止功能之後，有關新保留的資訊會顯示在所選保留的飛入頁面上。 此資訊包含保留的信箱和網站數量，以及有關保留之內容的統計資料，例如，保留的專案總數和大小，以及計算保留統計資料的最後時間。 這些保留統計資料可協助您識別要保留與案例相關的內容數量。
  
![保留統計資料](../media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
請記住有關 eDiscovery 保留統計資料的下列事項：
  
- [保留中的專案總數] 表示來自保留之所有內容來源的專案數目。 如果您已建立以查詢為基礎的保留，則此統計資料會指出符合查詢的專案數。

- 保留專案數也包含在內容位置找到的未編制索引的專案。 如果您建立以查詢為基礎的保留，則內容位置中的所有未編制索引的專案都會處於保留狀態。 這包括未編制索引的專案，但不符合查詢型保留的搜尋準則，以及可能超出日期範圍條件的未編制索引項目目。 這與執行搜尋時所發生的情形不同，在此搜尋中，搜尋結果中不會包含未符合搜尋查詢或由日期範圍條件排除的非索引項目目。 如需未編制索引之專案的詳細資訊，請參閱[部分編制索引的專案](partially-indexed-items-in-content-search.md)。

- 您可以按一下 [**更新統計資料]** 以重新執行搜尋預估，以計算目前保留的專案數，以取得最新的保留統計資料。

- 保留的專案數是正常的，因為信箱或網站處於保留狀態的使用者通常是在 SharePoint 和 OneDrive 中傳送或接收新的電子郵件，並建立新的檔。

- 如果 Exchange 信箱、SharePoint 網站或 OneDrive 帳戶移至多地理位置環境中的其他區域，該網站的統計資料將不會包含在 [保留統計資料] 中。 但這些位置的內容仍會保留。 此外，如果信箱或網站移至不同的地區，保留中所顯示的 SMTP 位址或 URL 不會自動更新。 您必須編輯保留並更新 URL 或 SMTP 位址，以便內容位置再次包含在保留統計資料中

## <a name="search-locations-on-ediscovery-hold"></a>EDiscovery 保留上的搜尋位置

當您在核心 eDiscovery 案例中[搜尋內容](search-for-content-in-core-ediscovery.md)時，您可以快速設定搜尋，只搜尋與案例相關聯之保留的內容位置。

![位置，保留位置](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)

選取 [**保留的位置**] 選項，可搜尋已設定保留狀態的所有內容位置。 若案例中包含多個 eDiscovery 保留，當您選取這個選項時，將會搜尋所有保留的內容位置。 此外，如果內容位置是放在查詢型保留中，當您執行搜尋時，只會搜尋符合保留查詢的專案。 換句話說，只有符合保留準則和搜尋準則的內容會隨搜尋結果一起傳回。 例如，如果使用者已設定為以查詢為基礎的案例保留，可保留在特定日期之前已傳送或建立的專案，則只會搜尋這些專案。 這是透過以**and**運算子連接案例保留查詢和搜尋查詢來完成。

以下是搜尋 eDiscovery 暫止位置時需要記住的一些其他事項：

- 在相同的情況下，如果內容位置是多個保留的一部分，當您使用 [全部案例內容] 選項來搜尋該內容位置時，保留查詢會由**OR**運算子組合。 同樣地，如果內容位置是兩個不同保留的一部分，其中一個是以查詢為基礎，另一個是無限期保留（所有內容都處於保留狀態），則所有內容都會因無限期保留而進行搜尋。

- 如果搜尋將其設定為保留搜尋位置，然後在案例中變更 eDiscovery 保留（透過新增或移除位置或變更保留查詢），則搜尋設定會以這些變更進行更新。 不過，您必須在變更保留以更新搜尋結果之後重新執行搜尋。

- 如果在 eDiscovery 案例中將多個 eDiscovery 保留置於單一位置，且您選擇搜尋保留的位置，則該搜尋查詢的關鍵字數目上限為500。 這是因為搜尋會結合使用**OR**運算子的所有查詢型保留。 如果合併保留查詢和搜尋查詢中的關鍵字超過500個，則會搜尋信箱中的所有內容，而不只是符合查詢架構案例的內容。

- 如果 eDiscovery 保留狀態為 [**開啟**]，則您仍然可以在保持開啟狀態時，搜尋保留的位置。

## <a name="preserve-content-in-microsoft-teams"></a>保留 Microsoft 小組中的內容

屬於 Microsoft 團隊通道一部分的對話會儲存在與 Microsoft 小組相關聯的信箱中。 同樣地，團隊成員在頻道中共用的檔案會儲存在團隊的 SharePoint 網站上。 因此，您必須將「小組信箱」和「SharePoint 網站」置於 eDiscovery 暫止狀態，才能保留通道中的交談和檔案。

或者，「小組」中 [交談] 清單一部分的交談（稱為*1:1 聊天*或*1： N 群組聊天*）會儲存在參與聊天的使用者信箱中。 與在聊天交談中的使用者共用的檔案，會儲存在共用該檔案之使用者的 OneDrive 帳戶中。 因此，您必須將個別的使用者信箱和 OneDrive 帳戶新增至 eDiscovery 暫止，以保留聊天清單中的交談和檔案。 除了放置小組信箱和網站保留狀態之外，還建議您保留 Microsoft 小組成員的信箱。

從2020年2月開始，我們開啟的功能可保留私人通道中的內容。 因為私人通道聊天是儲存在聊天參與者的信箱中，所以在 eDiscovery 保留中放置使用者信箱將會保留私人通道聊天。 此外，如果使用者信箱位於2月2020日前的 eDiscovery 暫止狀態，則保留現在會自動套用至該信箱中儲存的私人通道郵件。 也支援保留私人通道中共用的檔案。

如需有關保留小組內容的詳細資訊，請參閱[將 Microsoft 團隊使用者或小組設為法定保留](https://docs.microsoft.com/MicrosoftTeams/legal-hold)。
    
> [!IMPORTANT]
> 在雲端式組織中，參與交談（屬於小組中的聊天室清單）的使用者必須具有 Exchange Online 信箱，才能在信箱置於 eDiscovery 暫止時保留聊天交談。 這是因為 [聊天室] 清單中的交談是儲存在聊天參與者的雲端架構信箱中。 如果聊天參與者沒有 Exchange Online 信箱，您將無法保留這些聊天會話。 例如，在 Exchange 混合式部署中，具有內部部署信箱的使用者可能會 ght 能夠加入屬於小組之聊天室清單一部分的交談。 不過，在此情況下，無法保留這些交談的內容，因為這些使用者沒有可以保留的雲端式信箱。
  
每個小組或小組頻道也包含 Wiki 進行記事與共同作業。 Wiki 的內容會自動儲存至 .mht 格式的檔案中。 此檔案會儲存在團隊 SharePoint 網站上的 Teams Wiki 資料文件庫中。 您可以將小組的 SharePoint 網站新增至 eDiscovery 保留，以保留 wiki 內容。

> [!NOTE]
> 在2017年6月發行時，可保留團隊或小組管道的 Wiki 內容（即當您放置小組的 SharePoint 網站時）的功能。 如果小組網站處於保留狀態，Wiki 內容將會從該日期開始保留。 不過，如果小組網站處於保留狀態，且 Wiki 內容已在2017年6月22日之前刪除，則 Wiki 內容尚未保留。

### <a name="office-365-groups"></a>Office 365 群組

小組是以 Office 365 群組為基礎。 因此，將 Office 365 群組放在 eDiscovery 暫止的情況類似于讓小組內容保持保留狀態。

將兩個小組和 Office 365 群組置於 eDiscovery 保留狀態時，請牢記下列事項：

- 如先前所述，若要將位於小組和 Office 365 群組的內容保留，您必須指定與群組或小組相關聯的信箱和 SharePoint 網站。

- 在[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中執行**set-unifiedgroup 指令程式**，以查看小組和 Office 365 群組的屬性。 若要取得與小組或 Office 365 群組相關聯之網站的 URL，這是一種很好的方式。 例如，下列命令會顯示名為「資深領導團隊」的 Office 365 群組的所選屬性：

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > 若要執行 **Get-UnifiedGroup** Cmdlet，您必須獲指派 Exchange Online 中的「僅檢視收件者」角色或者為獲指派「僅檢視收件者」角色之角色群組的成員。 
  
- 當使用者的信箱進行搜尋時，不會搜尋使用者所屬的任何小組或 Office 365 群組。 同樣地，當您在 eDiscovery 暫止時放置小組或 Office 365 群組時，只有群組信箱和群組網站處於保留狀態。 除非您明確地將其新增至 eDiscovery 保留，否則不會保留群組成員之商務網站的信箱和 OneDrive。 因此，如果您出於法律原因而必須將小組或 Office 365 群組保留，請考慮在相同的保留中加入小組成員或群組成員的信箱和 OneDrive 帳戶。

- 若要取得小組或 Office 365 群組的成員清單，您可以在 Microsoft 365 系統管理中心的 [**群組**] 頁面上查看屬性。 或者，您可以在 Exchange Online PowerShell 中執行下列命令：

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > 若要執行 **Get-UnifiedGroupLinks** Cmdlet，您必須獲指派 Exchange Online 中的「僅檢視收件者」角色或者為獲指派「僅檢視收件者」角色之角色群組的成員。

## <a name="onedrive-accounts"></a>OneDrive 帳戶

若要收集組織中商務網站 OneDrive 的 URLs 清單，以便將其新增至與 eDiscovery 案例相關聯的保留或搜尋，請參閱[建立組織中所有 OneDrive 位置的清單](https://docs.microsoft.com/onedrive/list-onedrive-urls)。 本文中的腳本會建立一個文字檔，其中包含組織中所有 OneDrive 網站的清單。 若要執行此指令碼，您必須安裝並使用 SharePoint Online 管理命令介面。 請務必將您組織 MySite 網域的 URL 附加至您要搜尋的每個 OneDrive 網站。 這是包含您所有 OneDrive 的網域；例如，`https://contoso-my.sharepoint.com`。 以下是使用者 OneDrive 網站的 URL 範例：`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。

> [!IMPORTANT]
> 使用者 OneDrive 帳戶的 URL 包含使用者主要名稱（UPN）（例如 `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ）。 在極少數的情況下，使用者的 UPN 變更時，其 OneDrive URL 也會變更，以加入新的 UPN。 如果使用者的 OneDrive 帳戶是 eDiscovery 保留的一部分，舊的，且其 UPN 已變更，您必須更新保留，而且必須更新保留，並新增使用者的新 OneDrive URL，並移除舊的。 如需詳細資訊，請參閱 [UPN 變更將如何影響 OneDrive URL](https://docs.microsoft.com/onedrive/upn-changes) (英文)。

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>移除 eDiscovery 保留中的內容位置

將信箱、SharePoint 網站或 OneDrive 帳戶從 eDiscovery 保留中移除之後，會套用*延遲保留*。 這表示實際刪除保留的時間延遲30天，以防止資料被永久刪除（清除）從內容位置。 這可讓系統管理員搜尋或復原在移除 eDiscovery 保留後將會清除的內容。 信箱和網站的延遲保留運作方式的詳細資料會有所不同。

- **信箱：**[延遲保留] 會在下次受管理的資料夾助理處理信箱及偵測移除 eDiscovery 暫止時，放在信箱上。 具體說來，當受管理的資料夾助理將下列其中一個信箱屬性設定為**True**時，會將延遲保留套用至信箱：

   - **DelayHoldApplied：** 此屬性適用于儲存在使用者信箱中的電子郵件相關內容（由使用 Outlook 和 Outlook 網頁版的人員所產生）。

   - **DelayReleaseHoldApplied：** 此屬性適用于以雲端為基礎的內容（由非 Outlook 應用程式（如 Microsoft 團隊、Microsoft Forms 及 Microsoft Yammer）所產生，該內容儲存在使用者的信箱中。 Microsoft app 所產生的雲端資料通常會儲存在使用者信箱中的隱藏資料夾中。

   將延遲保留放在信箱上時（如果上述任一屬性設定為**True**），信箱仍會被視為無限期保留期間（如同信箱處於訴訟暫止狀態時）。 30天后，延遲保留會到期，而且 Microsoft 365 會自動嘗試移除延遲保留（透過將 DelayHoldApplied 或 DelayReleaseHoldApplied 屬性設為**False**），以移除 [保留]。 在上述任一屬性設定為**False**之後，在下一次受管理的資料夾助理處理信箱時，會清除標示為待移除的對應專案。

   如需詳細資訊，請參閱[管理延遲保留信箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。

- **SharePoint 和 OneDrive 網站：** 從 eDiscovery 保留中移除網站後的30天延遲保留期間內，將不會刪除保留在保留文件庫中的任何 SharePoint 或 OneDrive 內容。 這與從保留原則發行網站時會發生什麼情況。 此外，您無法在30天的延遲保留期間內，以手動方式刪除保留文件庫中的內容。 

   如需詳細資訊，請參閱[發行保留原則](retention.md#releasing-a-retention-policy)。

當您關閉核心 eDiscovery 案例時，延遲保留也會套用至保留狀態，因為關閉案例時會關閉保留。 如需關閉案例的詳細資訊，請參閱[關閉、重新開啟和刪除核心 eDiscovery 案例](close-reopen-delete-core-ediscovery-cases.md)。

## <a name="ediscovery-hold-limits"></a>eDiscovery 保留限制

下表列出 eDiscovery 案例及案例保留的限制。

  |**限制的描述**|**限制**|
  |:-----|:-----|
  |組織的案例數目上限  <br/> |無限制  <br/> |
  |組織的 eDiscovery 保留數目上限  <br/> |10,000  <br/> |
  |單一電子檔保留中的信箱數目上限  <br/> |1,000  <br/> |
  |單一 eDiscovery 保留中商務網站的 SharePoint 數目上限及 OneDrive  <br/> |100  <br/> |
  |在 eDiscovery 首頁顯示的案例數目上限，以及在案例中的 [保留]、[搜尋] 和 [匯出] 索引標籤上顯示的專案數上限。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup>若要查看超過1000案例、保留、搜尋或匯出的清單，您可以使用對應的 Office 365 安全性 & 合規性 PowerShell Cmdlet：<br/> [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
