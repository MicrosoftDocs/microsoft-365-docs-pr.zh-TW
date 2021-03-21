---
title: 在高級 eDiscovery 中管理保留
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
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 瞭解如何在保管人及其資料來源中放置保留，以保留您的高級 eDiscovery 案例中的相關內容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 07edcb2707d1dffecfa5a2aac6c4340ac6cbe53f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926371"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>在高級 eDiscovery 中管理保留

您可以使用 Advanced eDiscovery 案例來建立保留，以保留可能與案例相關的內容。 使用「高級 eDiscovery 保留」功能，您可以將保留置於保管人及其資料來源。 此外，您可以在信箱和 OneDrive 商務網站上放置非 custodial 保留。 您也可以針對 Microsoft 365 群組，在群組信箱、SharePoint 網站和商務用 OneDrive 上放置保留。 同樣地，您可以在與 Microsoft 小組相關聯的信箱和網站上進行保留。 當您將內容位置置於保留狀態時，會保留內容，直到您放開保管人、移除特定資料位置或徹底刪除保留原則為止。

## <a name="manage-custodian-based-holds"></a>管理以保管人為基礎的封存

在某些情況下，您可能會已識別一組保管人，並決定在案例期間保留其資料。 在 [Advanced eDiscovery] 中，當這些保管人保留時，使用者及其選取的資料來源都會自動新增至保管人保留原則。

若要查看保管人保留原則：

1. 在 [Microsoft 365 規範中心] 中，按一下 [ **eDiscovery > Advanced** 以顯示您組織中的案例清單。

2. 移至 [ **來源** ] 索引標籤，以在您的案例中新增保管人。 若要瞭解如何在高級 eDiscovery 案例中新增及放置保管人，請參閱 [Add 保管人 to a case](add-custodians-to-case.md)。 如果您已新增保管人並將其置於保留狀態，請移至步驟3。

3. 移至 [**保留**] 索引標籤，然後按一下 [ **CustodianHold \<HoldId>**]。

4. 在飛入頁面上，您可以看到原則的 [保留統計資料]。 您也可以執行將查詢套用至保管人型保留等動作。 如需建立保留查詢及使用條件的詳細資訊，請參閱 [內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。

## <a name="manage-non-custodial-holds"></a>管理非 custodial 保留

當您建立保留時，您可以使用下列選項來限定保留在指定內容位置的內容：

- 您可以在保留所有內容的位置建立無限保留。 或者，您也可以建立以查詢為基礎的保留，只保留符合搜尋查詢的內容。
  
- 您可以指定日期範圍，只保留在該日期範圍內傳送、接收或建立的內容。 或者，您可以保留所有內容，不論它是在何時傳送、接收或建立。

若要為高級 eDiscovery 案例建立非 custodial 保留：

1. 在 [Microsoft 365 規範中心] 中，按一下 [ **eDiscovery > Advanced** 以顯示您組織中的案例清單。
  
2. 按一下您要建立保留之案例旁邊的 [ **開啟** ]。
  
3. 從案例的首頁，按一下 [ **保留** ] 索引標籤。
  
4. 在 [ **保留** ] 索引標籤上，按一下 [ **建立**]。
  
5. 在 [ **命名您的保留** ] 頁面上，指定保留名稱。 [保留] 的名稱在您的組織中必須是唯一的。
 
6.  (選用) 在 [ **描述** ] 方塊中，新增保留的描述。
  
7. 按 [下一步 **]**。
  
8. 選擇您要保留的內容位置。 您可以將信箱、網站和公用資料夾放入暫止狀態。

   1. **Exchange 電子郵件** -按一下 **[選擇使用者、群組或小組** ]，然後按一下 **[選擇使用者、群組或小組** ]，以指定要保留的信箱。 使用 [搜尋] 方塊來尋找使用者信箱和通訊群組 (將保留在群組成員的信箱上) 進行暫止。 您也可以在 Microsoft 365 群組或 Microsoft 小組的相關信箱上放置保留。 選取 [使用者、群組、小組] 核取方塊，按一下 **[選擇**]，然後按一下 [ **完成**]。
 
      > [!NOTE]
      > 當您按一下 **[選擇使用者、群組或小組** 以指定要保留的信箱] 時，顯示的信箱選擇器會是空的。 這項設計的目的是提升效能。 若要將人員新增至此清單，請在搜尋方塊中輸入 (至少3個字元) 名稱。

   1. **SharePoint 網站** -按一下 **[選擇網站** ]，然後按一下 **[選擇網站** ]，以指定要保留之商務網站的 SharePoint 和 OneDrive。 輸入您要保留之每個網站的 URL。 您也可以為 Microsoft 365 群組或 Microsoft 團隊新增 SharePoint 網站的 URL。 按一下 **[選擇**]，然後按一下 [ **完成**]。
    
      請參閱 **FAQ** 一節，以取得放置 Microsoft 365 群組和 microsoft 團隊保留的秘訣。

      > [!NOTE]
      > 使用者 OneDrive 帳戶的 URL 包含使用者主要名稱 (UPN)  (例如 `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com`) 。 在極少數的情況下，使用者的 UPN 變更時，其 OneDrive URL 也會變更，以加入新的 UPN。 如果使用者的 OneDrive 帳戶是非 custodial 保留的一部分，且其 UPN 已變更，您必須更新 [保留] 並指向新的 OneDrive URL。 如需詳細資訊，請參閱 [UPN 變更將如何影響 OneDrive URL](/onedrive/upn-changes) (英文)。

   1. **Exchange 公用資料夾** -將切換開關移至 [全部] 位置，將 Exchange Online 組織中的所有公用資料夾保留。 請注意，您無法選擇要保留的特定公用資料夾。 如果您不想要保留公用資料夾，請將切換參數設為 [ **無** ]。

9. 當您完成將內容位置新增至保留狀態時，按 **[下一步]**。
  
10. 若要建立查詢式保留與條件，請完成下列。 否則，只要按 **[下一步]**。
    
    - 在 [ **關鍵字**] 底下的方塊中輸入搜尋查詢，以便只保留符合搜尋準則的內容。 您可以指定關鍵字、郵件屬性或檔案屬性，例如檔案名稱。 您也可以使用更複雜的查詢，使用布林運算子，例如 AND、OR 或 NOT。 如果 [關鍵字] 方塊是空白的，則位於指定內容位置的所有內容都會處於保留狀態。

    - 按一下 [  **新增** 條件] 以新增一或多個條件，以縮小保留的搜尋查詢。 每個條件都會將子句新增至您建立保留時所建立並執行的 KQL 搜尋查詢。 例如，您可以指定日期範圍，讓在日期範圍內建立的電子郵件或網站檔處於暫止狀態。 條件會以 AND 運算子的邏輯方式連接至關鍵字查詢 (在關鍵字方塊中指定)。 這表示專案必須同時滿足關鍵字查詢和要置於保留狀態的條件。

     如需建立搜尋查詢和使用條件的詳細資訊，請參閱 [內容搜尋的關鍵字查詢和搜尋條件](/office365/SecurityCompliance/keyword-queries-and-search-conditions)。

11. 設定查詢型保留後，請按 **[下一步]**。

12. 請複查您的設定，然後按一下 [ **建立此保留**]。

## <a name="view-hold-statistics"></a>查看保留統計資料

經過一段時間後，就會在選取之保留標籤的 [ **保留** ] 索引標籤上的詳細資料窗格中顯示新保留的相關資訊。 此資訊包含保留的信箱和網站數量，以及有關保留之內容的統計資料，例如，保留的專案總數和大小，以及計算保留統計資料的最後時間。 這些保留統計資料可協助您找出與 eDiscovery 案例相關的內容數量。

請記住保留統計資料的下列事項：

- [保留中的專案總數] 表示來自保留之所有內容來源的專案數目。 如果您已建立以查詢為基礎的保留，則此統計資料會指出符合查詢的專案數。
  
- 保留專案數也包含在內容位置找到的未編制索引的專案。 請注意，如果您建立以查詢為基礎的保留，則內容位置中的所有未編制索引的專案都會處於暫止狀態。 這包括未編制索引的專案，但不符合查詢型保留的搜尋準則，以及可能超出日期範圍條件的未編制索引項目目。 這與執行內容搜尋時所發生的情形不同，在這種情況下，在搜尋結果中不會包含未符合搜尋查詢的非索引項目目，或由日期範圍條件排除。 如需有關未編制索引之專案的詳細資訊，請參閱 [在 Office 365 的內容搜尋中部分索引的專案](partially-indexed-items-in-content-search.md)。 

- 您可以按一下 [更新統計資料] 以重新執行搜尋評估，以計算目前保留的專案數，以取得最新的保留統計資料。

- 如有需要，按一下工具列中的 [重新整理]，以在詳細資料窗格中更新 [保留統計資料]。

- 保留的專案數一般會隨著時間增加，因為信箱或網站處於保留狀態的使用者通常會傳送或接收新的電子郵件，並為商務檔建立新的 SharePoint 和 OneDrive。

- 如果 SharePoint 網站或 OneDrive 帳戶移至多地理位置環境中的其他區域，該網站的統計資料將不會包含在 [保留統計資料] 中。 不過，網站中的內容仍會保留。 此外，如果網站移至不同的區域，保留中所顯示的 URL 將不會更新。 您必須編輯保留並更新 URL。

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>在 Microsoft 團隊和 Office 365 群組上進行保留

Microsoft 團隊是以 Office 365 群組為基礎。 因此，在「高級 eDiscovery」中放置它們是非常類似的。 

- **如何將其他 Microsoft 365 群組或 Microsoft 小組網站對應至保管人？如何在 Microsoft 365 群組和 Microsoft 團隊上放置非 Custodial 保留？** Microsoft 團隊是以 Microsoft 365 群組為基礎。 因此，將其保留在 eDiscovery 案例中非常類似。 將 Microsoft 365 群組和 Microsoft 小組置於暫止狀態時，請記住下列事項。
  - 若要將 Microsoft 365 群組和 Microsoft 小組中的內容設為暫止狀態，您必須指定與群組或小組相關聯的信箱和 SharePoint 網站。
  
  - 在 Exchange Online 中執行 **set-unifiedgroup 指令程式** ，以查看 Microsoft 365 群組或 microsoft 小組的屬性。 若要取得與 Microsoft 365 群組或 Microsoft 小組相關聯之網站的 URL，這是一種很好的方式。 例如，下列命令會顯示名為「資深領導團隊」的 Microsoft 365 群組的所選屬性：


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > 若要執行 Get-UnifiedGroup Cmdlet，您必須獲指派 Exchange Online 中的「僅檢視收件者」角色或者為獲指派「僅檢視收件者」角色之角色群組的成員。

 - 搜尋使用者的信箱時，不會搜尋使用者所屬的任何 Microsoft 365 群組或 Microsoft 團隊。 同樣地，當您放置 Microsoft 365 群組或 Microsoft 小組時，只有群組信箱和群組網站處於保留狀態;除非您明確地將其新增為保管人或將其資料來源保留，否則不會保留群組成員之商務網站的信箱和 OneDrive。 因此，如果您需要將 Microsoft 365 群組或 Microsoft 團隊保留給特定的保管人，請考慮將群組網站和群組信箱對應至保管人 (請參閱在高級 eDiscovery) 中管理保管人。 如果 Microsoft 365 群組或 Microsoft 團隊不是由單一管理員所歸屬，請考慮將來源新增至非 custodial 保留。 
 
 - 若要取得 Microsoft 365 群組或 Microsoft 小組成員的清單，您可以在 Microsoft 365 系統管理中心的 [家庭 > 群組] 頁面上，查看其屬性。 或者，您可以在 Exchange Online PowerShell 中執行下列命令：

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > 若要執行 **Get-UnifiedGroupLinks** Cmdlet，您必須獲指派 Exchange Online 中的「僅檢視收件者」角色或者為獲指派「僅檢視收件者」角色之角色群組的成員。

- 屬於 Microsoft 團隊通道一部分的通道交談儲存在與小組相關聯的信箱中。 同樣地，團隊成員在頻道中共用的檔案會儲存在團隊的 SharePoint 網站上。 因此，您必須將 Microsoft 小組信箱和 SharePoint 網站置於保留狀態，以在通道中保留交談和檔案。
  
- 或者，在 Microsoft 小組中屬於聊天清單一部分的交談，會儲存在使用者參與聊天的信箱中。  使用者在聊天交談中共用的檔案會儲存在共用該檔案之使用者的 OneDrive 商務網站中。 因此，您必須將個別的使用者信箱和 OneDrive 用於商務網站保留，以便在聊天清單中保留交談和檔案。 
  
- 每個 Microsoft 團隊或小組管道都包含一個 Wiki 進行記事與共同作業。 Wiki 的內容會自動儲存至 .mht 格式的檔案中。 此檔案會儲存在團隊 SharePoint 網站上的 Teams Wiki 資料文件庫中。 您可以將內容放入 Wiki 的保留狀態，方法是將該小組的 SharePoint 網站保留。

  > [!NOTE]
  > 當您將小組 SharePoint 網站保留) 發佈于2017年6月22日時，可保留 Microsoft 小組或小組頻道 (的 Wiki 內容。 如果小組網站處於保留狀態，Wiki 內容將會從該日期開始保留。 不過，如果小組網站處於保留狀態，且 Wiki 內容已在2017年6月22日之前刪除，則 Wiki 內容尚未保留。