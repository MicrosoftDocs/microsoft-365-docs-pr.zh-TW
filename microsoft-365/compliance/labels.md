---
title: 保留標籤概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Office 365 中的保留標籤可以幫助您對正確的內容採取正確的動作。使用保留標籤，您可以分類整個組織中的資料以利控管，並根據該分類強制執行保留規則。您也可以使用保留標籤在 Office 365 中實作記錄管理。
ms.openlocfilehash: 71630812e75ef8b4af2f172f73e51d0084fb0df1
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076248"
---
# <a name="overview-of-retention-labels"></a>保留標籤概觀

您的整個組織可能擁有不同類型的內容，需要採取不同的動作才能符合產業規範和內部原則。例如，您可能有：
  
- 至少必須**保留**一小段時間的稅務表單。 
    
- 到達特定年限之後需要**永久刪除**的新聞材料。 
    
- 需要先**保留**之然後再**永久刪除**的競爭力研究。 
    
- 必須**標示為記錄**使之無法編輯或刪除的工作簽證。 
    
在這些案例中，Office 365 中的保留標籤可以幫助您對正確的內容採取正確的動作。使用保留標籤，您可以分類整個組織中的資料以利管理，並根據該分類強制執行保留規則。
  
使用保留標籤，您可以：
  
- **讓組織的人員可以手動套用保留標籤**至 Outlook 網頁版、Outlook 2010 及更新版本、OneDrive、SharePoint、Office 365 群組中的內容。使用者通常最清楚自己使用的內容類型，因此可以對其分類並套用適當的原則。 
    
- 在當內容符合特定條件時**自動將保留標籤套用到內容**，例如內容包含： 
    
  - 特定類型的敏感資訊。
    
  - 特定關鍵字符合您建立的查詢。
    
  自動將保留標籤套用到內容很重要，因為：
    
     - 您不需要訓練您的使用者記下所有分類。
    
     - 您不需要仰賴使用者正確地將所有內容分類。
    
   - 使用者不再需要了解資料控管原則，就可以專心工作。

  > [!NOTE]
  > 自動套用標籤的功能需要每位使用者均擁有 Office 365 Enterprise E5 授權，這些使用者有權編輯網站或信箱中已自動標籤的內容。
      
- **在 Office 365 中實作記錄管理**，包括電子郵件和文件。您可以使用保留標籤將內容分類成記錄。在這種情況下，無法變更或移除標籤，且不能編輯或刪除內容。 

- **將預設保留標籤套用至 SharePoint 中的文件庫、資料夾或文件集**，以便該位置中的所有文件都繼承預設保留標籤。  
    
您可以在 Microsoft 365 合規性中心、Microsoft 365 安全性中心或 Office 365 安全性與合規性中心建立保留標籤。 在左側導覽中，選擇 **[分類] ** > ** [保留標籤] ** > ** [建立標籤]**。

## <a name="how-retention-labels-work-with-retention-label-policies"></a>保留標籤如何與保留標籤原則一起使用

為貴組織中的人員提供保留標籤，將內容分類只需完成兩個步驟：首先，您必須建立保留標籤，接著將標籤發佈到您指定的位置。 當您發佈保留標籤時，系統會建立保留標籤原則。
  
![標籤的角色和工作圖](media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
保留標籤是由一或多個保留標籤原則所包含之可重複使用的獨立建構元素。 保留標籤原則的主要目的是將一組保留標籤分組，以及指定您想讓這些標籤出現的目標位置。
  
![標籤、標籤原則和位置圖表](media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. 當您發佈保留標籤時，會將它們納入保留標籤原則。 請注意，保留標籤的名稱是固定的，且建立後即無法進行編輯。


2. 單一保留標籤可納入多個保留標籤原則。

3. 單一位置也可納入多個保留標籤原則。    
    
3. 保留標籤原則會指定要發佈保留標籤的位置。
    
## <a name="only-one-retention-label-at-a-time"></a>一次只能有一個保留標籤

請務必了解，電子郵件或文件等內容一次只能指派一個保留標籤：
  
- 針對使用者手動指派的保留標籤，使用者可以移除或變更獲指派的保留標籤。
    
- 如果內容有指派自動套用的標籤，使用者可以手動指派保留標籤來取代自動套用的標籤。
    
- 如果內容有使用者手動指派的保留標籤，則自動套用標籤無法取代手動指派的保留標籤。
    
- 如果有多項規則會指派自動套用標籤，且內容符合多項規則的條件，則會指派最舊規則的保留標籤。
    
手動指派標籤為明確指派，自動套用標籤為隱含指派。明確保留標籤的優先順序高於隱含標籤。如需詳細資訊，請參閱之後的[保留原則，哪一個優先？](#the-principles-of-retention-or-what-takes-precedence)小節。

本節中所有的資訊僅適用於保留標籤。請注意，除了一個保留標籤之外，也可以將一個區分大小寫的標籤套用至內容的項目。
  
## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>保留標籤要多久才會生效

當您發佈或自動套用保留標籤時，標籤不會立即生效：
  
1. 首先，標籤原則必須先將系統管理中心與原則中的位置同步。
    
2. 接著，位置可能會需要一些時間，將已發佈的保留標籤提供給使用者，或是將標籤自動套用到內容。 實際所需的時間取決於保留標籤的位置和類型。
    
### <a name="published-retention-labels"></a>已發佈的保留標籤

如果您將保留標籤發佈到 SharePoint 或 OneDrive，需要一天的時間讓這些保留標籤向使用者顯示。此外，如果您將保留標籤發佈到 Exchange，可能需要 7 天來向使用者顯示這些保留標籤，且信箱至少必須包含 10 MB 的資料。
  
![手動標籤生效的圖](media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a>自動套用保留標籤

如果您將保留標籤自動套用至符合特定條件的內容，保留標籤套用至符合條件的所有現有內容可能需要 7 天。 但請注意，部署保留標籤之後套用至新的內容很快，通常在 15 分鐘之內。
  
![自動標籤生效的圖](media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a>如何檢查發佈至 Exchange 之保留標籤的狀態

在 Exchange Online 中，是透過每 7 天執行一次的程序，將保留標籤提供給使用者。您可以使用 Powershell 查看此程序上次執行的時間，依此判斷下一次執行時間。
  
1. [連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773)。
    
2. 執行下列命令。
    
  ```
  $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
  ```

  ```
  $xmlprops = [xml]($logProps.MailboxLog)
  ```

  ```
  $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
  ```

結果：`ELCLastSuccessTimeStamp` (UTC) 屬性會顯示系統上次處理您信箱的時間。 如果系統在您建立原則後都還未處理信箱，標籤就無法顯示。 若要強制處理信箱，請執行 `Start-ManagedFolderAssistant -Identity <user>`。
    
如果標籤沒有出現在 Outlook 網頁版中，而您認為應該要出現，請務必清除瀏覽器中的快取 (CTRL + F5)。
    
## <a name="retention-label-policies-and-locations"></a>保留標籤原則與位置

可以將不同類型的保留標籤發佈到不同的位置，視保留標籤的功能而定。
  
|**如果保留標籤是...**|**則標籤原則可套用至...**|
|:-----|:-----|
|發佈給使用者  <br/> |Exchange、SharePoint、OneDrive、Office 365 群組  <br/> |
|根據敏感資訊類型而自動套用  <br/> |Exchange (僅限所有信箱)、SharePoint、OneDrive  <br/> |
|根據查詢而自動套用  <br/> |Exchange、SharePoint、OneDrive、Office 365 群組  <br/> |
   
請注意，在 Exchange 中自動套用保留標籤 (查詢和敏感資訊類型) 只會套用到新傳送的郵件 (傳送中的資料)，不會套用到目前信箱中的所有項目 (靜止的資料)。此外，用於敏感資訊類型的自動套用保留標籤只能套用到所有信箱，無法指定特定的信箱。
  
請注意，Exchange 公用資料夾和 Skype 不支援標籤。
  
## <a name="how-retention-labels-enforce-retention"></a>保留標籤如何強制保留

保留標籤可以強制執行與保留原則完全相同的保留動作。您可以使用保留標籤來實作複雜的內容規劃 (或檔案規劃)。如需保留運作方式的詳細資訊，請參閱[保留原則概觀](retention-policies.md)。
  
除此之外，保留標籤有兩個只能用於保留標籤，但不能用於保留原則的保留選項。使用保留標籤，您可以：
  
- 在保留期間結束時觸發處置檢閱，這樣能在刪除 SharePoint 和 OneDrive 文件之前，必須先檢閱它們。如需詳細資訊，請參閱[處置檢閱概觀](disposition-reviews.md)。
    
- 保留期間是從內容套用標籤時開始計算，而不是內容的壽命或上次修改時間。 請注意，此選項僅適用 SharePoint 網站和 OneDrive 帳戶中的內容。 針對 Exchange 電子郵件，保留期間一律會取決於傳送或接收訊息的日期，無論在這裡選擇的選項為何。
    
![保留設定與標籤專用的選項](media/c49118c9-6279-4661-94db-deffa76e27ac.png)
  
## <a name="where-published-retention-labels-can-appear-to-end-users"></a>可以向使用者顯示已發佈保留標籤的位置

如果保留標籤將由使用者指派給內容，您可以將它發佈到：
  
- Outlook 網頁版
    
- Outlook 2010 及更新版本
    
- OneDrive
    
- SharePoint
    
- Office 365 群組 (群組網站和Outlook 網頁版中的群組信箱)
    
以下各節說明標籤在不同應用程式中向組織內人員顯示的方式。
  
### <a name="outlook-on-the-web"></a>Outlook 網頁版

若要在 Outlook 網頁版中的項目加上標籤，以滑鼠右鍵按一下該項目 \>[指派原則]**** \> 選擇保留標籤。 
  
![Outlook 網頁版中的指派原則功能表](media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
套用保留標籤後，您可以在項目頂端檢視該保留標籤以及它採取的動作。如果電子郵件已分類，且有相關聯的保留期間，您可以一目了然電子郵件的到期日。
  
![指派給 Outlook 網頁版電子郵件的標籤](media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
您也可以將保留標籤套用到資料夾，在此情況下：
  
- 資料夾中的所有項目會自動套用相同的保留標籤，**除了**已明確套用保留標籤的項目。已明確套用標籤的項目會保留現有的保留標籤。如需詳細資訊，請參閱之後的保留原則小節。 
    
- 如果您變更或移除資料夾的預設保留標籤，資料夾中的所有項目也會變更或移除該保留標籤，**除了**明確套用保留標籤的項目。 
    
- 如果您將有預設保留標籤的項目從某個資料夾移到另一個具有不同預設保留標籤的資料夾，該項目就會套用新的預設保留標籤。
    
- 如果您將有預設保留標籤的項目從某個資料夾移到另一個沒有不同預設保留標籤的資料夾，就會移除舊的預設保留標籤。
    
### <a name="outlook-2010-and-later"></a>Outlook 2010 及更新版本

若要在 Outlook 網頁版中的項目加上標籤，以滑鼠右鍵按一下該項目 \> 在 [功能區]**** 中 \> [指派原則]**** \> 選擇保留標籤。 
  
![指派原則按鈕](media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
套用保留標籤後，您可以在項目頂端檢視該保留標籤以及所採取的動作。 如果電子郵件已套用具有相關聯保留期間的保留標籤，您可以快速查看電子郵件的到期日。
  
您也可以將保留標籤套用到資料夾。這在 Outlook 2010 及更新版本中和在 Outlook 網頁版中的作用一樣。詳細資訊請參閱前一節。
  
### <a name="onedrive-and-sharepoint"></a>OneDrive 和 SharePoint

若要為 OneDrive 或 SharePoint 中的文件 (包括 OneNote 檔案) 加上標籤，請選取右上角的項目 \>、選擇 [開啟詳細資料窗格]****![[資訊窗格] 圖示](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \>[套用保留標籤]**** \>，然後選擇保留標籤。 
  
請注意，您也可以將保留標籤套用至資料夾或數個文件，可以為文件庫設定預設保留標籤；詳細資訊請參閱下一小節。
  
![SharePoint 中項目的套用標籤清單](media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
將保留標籤套用到項目之後，您可以選取項目，並在詳細資料窗格中檢視標籤。
  
![詳細資料窗格中顯示已套用的標籤](media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
您也可以建立包含**標籤**資料行或**項目是記錄**資料行的文件庫檢視，以便快速查看指派給所有項目的保留標籤以及哪些項目是記錄。不過請注意，您無法以**項目是記錄**資料行篩選檢視。 
  
![自訂檢視中顯示的標籤資料行文件庫](media/e3392627-c0a3-405e-bb57-55f27c34cfdd.png)
  
### <a name="office-365-groups"></a>Office 365 群組

當您將保留標籤發佈到 Office 365 群組時，保留標籤會顯示在群組網站和 Outlook 網頁版中的群組信箱。將保留標籤套用至內容和上述的套用至電子郵件和文件完全相同。

若要保留 Office 365 群組的內容，您必須使用 Office 365 群組位置。雖然 Office 365 群組擁有 Exchange 信箱，包含整個 Exchange 位置的保留原則並不會包含 Office 365 群組信箱中的內容。

此外，無法使用 Exchange 位置來包含或排除特定群組信箱。雖然 Exchange 位置最初允許選取群組信箱，但是當您嘗試儲存保留原則時，您會收到「RemoteGroupMailbox 不是Exchange 位置的有效選取項目」錯誤。
  
## <a name="applying-a-retention-label-automatically-based-on-conditions"></a>根據條件自動套用保留標籤

保留標籤最強大的功能之一，是能夠自動套用至符合特定條件的內容。在此情況下，貴組織中的人員不需要套用保留標籤，Office 365 會替他們做這些事。
  
![自動套用標籤的角色和工作圖](media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
自動套用保留標籤很強大是因為：
  
- 您不需要訓練您的使用者記下所有分類。
    
- 您不需要仰賴使用者正確地將所有內容分類。
    
- 使用者不再需要了解資料控管原則，他們可以專心工作。
    
您可以選擇當內容包含以下資訊時，自動將保留標籤套用到內容：
  
- 特定類型的敏感資訊。
    
- 特定關鍵字符合您建立的查詢。
    
![自動套用標籤的條件選擇頁面](media/c0b7a3ef-bda0-494c-941d-f1f93753ecdd.png)
  
請注意，自動套用保留標籤需要 Office 365 企業版 E5 訂用帳戶，且如前文所述，可能需要 7 天讓自動套用保留標籤套用至符合條件的所有內容。
  
### <a name="auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information"></a>自動將保留標籤套用至包含特定類型敏感資訊的內容

當您為敏感資訊建立自動套用保留標籤時，會看到和建立資料外洩防護 (DLP) 原則相同的原則範本清單。每個原則範本皆預先設定為尋找特定類型的敏感資訊，例如，此處顯示的範本會尋找美國 ITIN、SSN 和護照號碼。若要深入了解 DLP，請參閱[資料外洩防護原則概觀](data-loss-prevention-policies.md)。
  
![敏感資訊類型的原則範本](media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
選取原則範本後，可以新增或移除任何類型的敏感資訊，且可以變更例項計數和比對精確度。此處所示的範例中，只有符合以下條件時，才會自動套用保留標籤：
  
- 內容包含 1 到 9 個下列三種敏感資訊類型。您可以刪除 **max ** (上限) 值，條件就會變成 **any** (任何)。
    
- 偵測到的敏感資訊類型的比對精確度 (或信賴等級) 下限為 75。許多敏感資訊類型會定義多個模式，模式的比對精確度愈高，便需要尋找愈多證據 (例如關鍵字、日期、地址)，而較低比對精確度的模式則需要較少的證據。簡單來說，比對精確度的 **min** (下限) 愈低，就越容易找到與條件相符的內容。 
    
如需這些選項的詳細資訊，請參閱[調整規則，讓規則更容易或更難相符](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。
    
![用於識別機密資訊類型的選項](media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>自動將標籤套用至包含關鍵字或可搜尋屬性的內容

您可以自動將標籤套用至符合特定條件的內容。現在可用的條件支援將標籤套用至包含特定字詞、片語或可搜尋屬性的值。您可以使用 AND、OR、NOT 等搜尋運算子來精簡查詢。

如需查詢語法的詳細資訊，請參閱：

- [關鍵字查詢語言 (KQL) 語法參考](https://docs.microsoft.com/zh-TW/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

查詢式標籤使用搜尋索引來識別內容。如需有效可搜尋屬性的詳細資訊，請參閱：

- [內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
- [SharePoint 伺服器中的編目及受控屬性概觀](https://docs.microsoft.com/zh-TW/SharePoint/technical-reference/crawled-and-managed-properties-overview)

範例查詢：

- Exchange
    - subject:"Quarterly Financials"
    - recipients:garthf<!--nolink-->@contoso.com
- SharePoint 和商務用 OneDrive
    - contenttype:contract
    - site:https<!--nolink-->://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract

![查詢編輯器](media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)

## <a name="applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a>將預設保留標籤套用至 SharePoint 文件庫、資料夾或文件集中的所有內容

除了讓使用者將保留標籤套用至個別文件，您也可以將預設保留標籤套用到 SharePoint 文件庫、資料夾或文件集，讓該位置的所有文件套用預設保留標籤。
  
以文件庫來說，這是在文件庫的 [文件庫設定]**** 頁面完成。當您選擇預設保留標籤時，也可以選擇將其套用至文件庫中的任何現有項目。 
  
例如，如果您有一個行銷資料的標籤，而且您知道某個文件庫只包含這個類型的內容，就能將「行銷資料」標籤設為該文件庫中所有文件的預設標籤。
  
![文件庫設定頁面上的套用標籤選項](media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
如果將預設保留標籤套用到文件庫、資料夾或文件集中的現有項目：
  
- 文件庫、資料夾或文件集中的所有項目會自動套用相同的標籤，**除了**已明確套用保留標籤的項目。已明確套用標籤的項目會保留現有的標籤。如需詳細資訊，請參閱之後的[保留原則，哪一個優先？](#the-principles-of-retention-or-what-takes-precedence)小節。
    
- 如果您變更或移除文件庫、資料夾或文件集的預設保留標籤時，文件庫、資料夾或文件集中的所有項目也會變更或移除該保留標籤，**除了**明確套用保留標籤的項目。 
    
- 如果將有預設保留標籤的項目從其文件庫、資料夾或文件集移到另一個文件庫、資料夾或文件集，該項目會保留現有的保留標籤，即使新位置有不同的預設保留標籤。
    
## <a name="applying-a-retention-label-to-email-by-using-rules"></a>使用規則將保留標籤套用至電子郵件

在 Outlook 2010 及更新版本中，您可以建立規則來套用保留標籤或保留原則。
  
例如，您可以建立規則來將特定保留標籤套用到傳送至或接收自特定通訊群組的所有郵件。
  
若要建立規則，以滑鼠右鍵按一下項目\> [規則]**** \> [建立規則]**** \> [進階選項]**** \> [規則精靈]**** \> [套用保留原則]****。
  
![規則精靈與套用保留原則的選項](media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a>將內容分類而不套用任何動作

當您建立保留標籤時，可以只建立標籤而不開啟任何保留或進行其他動作，如下所示。在此情況下，您可以單純使用保留標籤作為文字標籤，不強制執行任何動作。
  
例如，您可以建立不帶任何動作、名為「稍後檢閱」的保留標籤，然後將此保留標籤自動套用到包含敏感資訊類型或查詢內容的內容。
  
![標籤設定頁面中關閉保留](media/17ce863b-a823-426e-aaad-83718465f762.png)
  
## <a name="using-retention-labels-for-records-management"></a>將保留標籤用於記錄管理

從高層次來看，記錄管理意味著：
  
- 重要內容由使用者分類為記錄。
    
- 不能修改或刪除記錄。
    
- 記錄在其規定的壽命結束後終將丟棄。
    
您可以使用保留標籤在 Office 365 中實作單一、一致的記錄管理策略，其他記錄管理功能 (如記錄中心) 則僅能套用至 SharePoint 內容。您可以對記錄強制執行保留動作，然後在記錄生命週期結束時，自動丟棄這些記錄。
  
當您建立保留標籤時，可以選擇使用保留標籤將內容分類為記錄。
  
![將內容分類為記錄核取方塊](media/9c300739-d5d0-41d2-88dd-137f1cfc9cb6.png)
  
如果將項目標示為記錄，會發生四件事：
  
- 無法永久刪除此項目。
    
- 無法編輯此項目。
    
- 無法變更此標籤。
    
- 無法移除此標籤。
    
### <a name="who-can-classify-content-as-a-record"></a>誰可以將內容分類為記錄

針對 SharePoint 內容，預設成員群組 (「參與」權限等級) 中的任何使用者皆可以將記錄標籤套用至內容。只有網站集合管理員可以移除或變更已套用的保留標籤。此外，可以將內容分類為記錄的保留標籤[自動套用至內容](#auto-apply-retention-labels)。
  
### <a name="records-and-folders"></a>記錄和資料夾

您可以將保留標籤套用至 Exchange、SharePoint 或 OneDrive 中的資料夾。如果資料夾已標示為記錄，而您將項目移至該資料夾，該項目會標示為記錄。將項目移出資料夾，該項目仍會標示為記錄。
  
### <a name="records-cant-be-deleted"></a>無法刪除記錄

如果您嘗試刪除 Exchange 中的一筆記錄，該項目會移到「可復原的項目」資料夾中，如[保留原則如何就地處理內容](retention-policies.md#how-a-retention-policy-works-with-content-in-place) 中所述。
  
如果您嘗試刪除 SharePoint 中的記錄，您會看到無法刪除該項目的錯誤，該項目仍會保留在文件庫中。
  
![無法從 SharePoint 中刪除項目的訊息](media/d0020726-1593-4a96-b07c-89b275e75c49.png)
  
如果您嘗試刪除 OneDrive 中的一筆記錄，該項目會移到「文件保留庫」中，如[保留原則如何就地處理內容](retention-policies.md#how-a-retention-policy-works-with-content-in-place) 中所述。
  
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>使用保留標籤作為 DLP 原則的條件

保留標籤可強制執行保留內容的動作。此外，您也可以使用保留標籤作為資料外洩防護 (DLP) 原則的條件。DLP 原則可以對包含特定標籤的內容強制執行其他動作，例如限制存取。 
  
如需詳細資訊，請參閱[使用標籤做為條件的 DLP 原則](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)。
  
## <a name="monitor-retention-labels"></a>監控保留標籤

發佈或自動套用保留標籤後，您會想要確認它們如您的預期套用到內容。若要監控您的保留標籤，可以使用：
  
- **標籤活動總管**。使用標籤活動總管 (如下所示)，可以快速搜尋和檢視過去 30 天在 SharePoint 和商務用 OneDrive 上所有內容的保留標籤活動。如需詳細資訊，請參閱[檢視文件的標籤活動](view-label-activity-for-documents.md)。

- [標籤分析]**** 頁面。 在 Microsoft 365 合規性中心和 Microsoft 365 安全性中心中，您可以快速檢視最常使用的標籤和套用標籤的位置。 您也可以檢視具有特定標籤的所有內容。 如需詳細資訊，請參閱[利用標籤分析檢視標籤使用量](label-analytics.md)。
    
- **資料控管報告**。使用資料控管報告，可以快速檢視過去 90 天在 Exchange、SharePoint、商務用 OneDrive 上所有內容的保留標籤趨勢和活動。如需詳細資訊，請參閱[資料控管報告](view-the-data-governance-reports.md)。
    
![標籤活動總管](media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a>使用內容搜尋來尋找套用特定保留標籤的所有內容

將保留標籤指派至內容後 (無論是由使用者指派或自動套用)，您可以使用「內容搜尋」，尋找以特定保留標籤分類的所有內容。
  
當您建立內容搜尋時，請選擇 [合規性標籤]**** 條件，然後輸入完整的標籤名稱或是部分標籤名稱加上萬用字元。如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。
  
![合規性標籤條件](media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="the-principles-of-retention-or-what-takes-precedence"></a>原則保留，哪一個優先？

很有可能內容會套用多個保留原則，這些原則各有不同的動作 (保留、刪除或兩者) 和保留期間。哪一個優先？請放心，最低限度，由一個原則保留的內容不會被另一個原則永久刪除。
  
![原則保留圖](media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
若要了解不同標籤的保留動作如何套用至內容，請記住以下保留原則：
  
1. **保留優先於刪除。** 假設一個保留原則要在 3 年後刪除 Exchange 電子郵件，但另一個保留原則要保留 Exchange 電子郵件 5 年再刪除。任何達到 3 年的內容會遭到刪除，在使用者檢視中看不到它們，但仍會保留在 [可復原的項目] 資料夾，直到內容達到 5 年，便會永久刪除。 
    
2. **最長保留期間優先。** 如果內容套用多個保留內容的原則，則會一直保留到最長保留期間結束為止。 
    
3. **明確包含優先於隱含包含。** 意思是： 
    
    1. 如果包含保留設定的保留標籤是由使用者手動指派給項目 (例如 Exchange 電子郵件或 OneDrive 文件)，則此保留標籤優先於在網站或信箱層級指派的原則，並優先於文件庫指派的預設保留標籤。例如，如果明確保留標籤要保留 10 年，但指派給網站的保留原則只要保留 5 年，則保留標籤優先。請注意，自動套用的保留標籤會被視為隱含而不是明確，因為它們是由 Office 365 自動套用。
    
    2. 如果保留原則包含特定位置 (例如特定使用者的信箱或商務用 OneDrive 帳戶)，則此原則優先於其他套用至所有使用者信箱或商務用 OneDrive 帳戶但未特地包含該使用者信箱的保留原則。
    
4. **最短刪除期間優先。** 同樣地，如果內容套用多個刪除內容的原則 (無保留)，則會在最短保留期間結束時刪除。 
    
了解保留原則從上到下的仲裁流程：如果所有原則或標籤套用的規則都在同一個層級，則流程會移到下一個層級來決定套用規則的優先順序。
  
最後，保留原則或標籤無法永久刪除 eDiscovery 保留的任何內容。保留解除時，這些內容便再度符合上述的清理程序。
  
## <a name="use-retention-labels-instead-of-these-features"></a>使用保留標籤而非這些功能

您可以輕鬆將保留標籤運用在整個組織及其 Office 365 內容，包括 Exchange、SharePoint、OneDrive、Office 365 群組。若您需要在 Office 365 任何地方分類內容或管理記錄，建議您使用保留標籤。
  
Office 365 先前提供數種用於將內容分類以及管理記錄的功能， 如下所示。 這些功能會繼續支援保留標籤。 請注意，雖然有保留標籤實作與先前功能不同的實例，但是保留標籤的演進會促進 Office 365 記錄管理的未來發展。 因此，我們建議您向前邁進，使用保留標籤而非這些功能來進行資料控管。
  
### <a name="exchange-online"></a>Exchange Online

- [保留標記和保留原則](https://go.microsoft.com/fwlink/?linkid=846125)，又稱為[郵件記錄管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (僅限刪除) 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 和商務用 OneDrive

- [設定就地記錄管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保留) 
    
- [記錄中心簡介](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (保留) 
    
- [資料管理原則](intro-to-info-mgmt-policies.md) (僅限刪除) 
    
## <a name="permissions"></a>權限

您的合規性小組中將建立保留標籤的成員必須具備安全性與合規性中心的權限。根據預設，租用戶管理員將可存取此位置，並且可直接讓法務人員與其他人存取安全性與合規性中心，而不需要為其提供租用戶管理員的所有權限。若要這麼做，我們建議您：移至安全性與合規性中心的 [權限]**** 頁面，編輯 [合規性管理員]**** 角色群組，將該成員加入此角色群組。 
  
如需詳細資訊，請參閱[授與使用者存取 Office 365 安全性與合規性中心的權限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。
  
需要這些權限才能建立及套用保留標籤和標籤原則。原則強制執行不需要內容的存取權。  
## <a name="find-the-powershell-cmdlets-for-labels"></a>尋找標籤的 PowerShell Cmdlet

若要使用標籤 Cmdlet，您必須：
  
1. [連接到 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. 使用這些 Office 365 安全性與合規性中心 Cmdlet：

  - [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetag)

  - [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-compliancetag)

  - [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-compliancetag)

  - [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-compliancetag)

  - [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/enable-compliancetagstorage)

  - [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetagstorage)

  - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)

  - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)

  - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)

  - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)

  - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)

  - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)

  - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)

  - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)
