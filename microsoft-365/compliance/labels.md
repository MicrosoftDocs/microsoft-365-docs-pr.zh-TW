---
title: 了解保留標籤
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解保留標籤如何分類整個組織中的資料以利控管，並根據該分類強制執行保留規則。您也可以使用保留標籤為 Microsoft 365 實作記錄管理解決方案。
ms.openlocfilehash: ab2e1baf553a386009d55e43efdf75b796cc1ffd
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545965"
---
# <a name="learn-about-retention-labels"></a>了解保留標籤

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

您的整個組織可能擁有不同類型的內容，需要採取不同的動作才能符合產業規範和內部原則。例如，您可能有：
  
- 至少必須**保留**一小段時間的稅務表單。 
    
- 到達特定年限之後需要**永久刪除**的新聞材料。 
    
- 需要先**保留**之然後再**永久刪除**的競爭力研究。 
    
- 必須**標示為記錄**使之無法編輯或刪除的工作簽證。 
    
在所有這些案例中，保留標籤可以幫助您對正確的內容採取正確的動作。使用保留標籤，您可以分類整個組織中的資料以利管理，並根據該分類強制執行保留規則。
  
使用保留標籤，您可以：
  
- **讓組織的人員可以手動套用保留標籤**至 Outlook 網頁版、Outlook 2010 及更新版本、OneDrive、SharePoint 和 Microsoft 365 群組中的內容。使用者通常最清楚自己使用的內容類型，因此可以對其分類並套用適當的原則。 
    
- 在當內容符合特定條件時**自動將保留標籤套用到內容**，例如內容包含： 
    
    - 特定類型的敏感資訊。
    
    - 特定關鍵字符合您建立的查詢。
    
    - 可訓練分類器的模式比對。
    
  自動將保留標籤套用到內容很重要，因為：
    
     - 您不需要訓練您的使用者記下所有分類。
    
     - 您不需要仰賴使用者正確地將所有內容分類。
    
   - 使用者不再需要了解資料控管原則，就可以專心工作。

- **將預設保留標籤套用至 SharePoint 中的文件庫、資料夾或文件集**，以便儲存在該位置中的所有文件都繼承預設保留標籤。

此外，保留標籤支援跨 Microsoft 365 應用程式和服務的電子郵件和文件[記錄管理](records-management.md)。 您可以使用保留標籤將內容分類為記錄。 如果您這麼做，任何人都無法變更或移除標籤，相關內容也無法編輯或刪除。 

針對租用戶支援的保留標籤數量沒有任何限制。 不過，10,000 個是針對租用戶支援的原則數目上限，其中包括會套用標籤 (保留標籤原則和自動套用保留原則) 的原則，以及保留原則。

## <a name="how-retention-labels-work-with-retention-label-policies"></a>保留標籤如何搭配保留標籤原則使用

讓保留標籤可供您組織中的人員使用，使得他們能夠分類內容，需要完成兩個步驟的程序： 

1. 建立保留標籤

2. 使用保留標籤原則來發佈保留標籤
  
![標籤的角色和工作圖](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
保留標籤是由一或多個保留標籤原則所包含之可重複使用的獨立建構元素。 保留標籤原則的主要目的是將一組保留標籤分組，以及指定您想讓這些標籤出現的目標位置。
  
![標籤、標籤原則和位置圖表](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. 當您發佈保留標籤時，會將它們納入保留標籤原則。 保留標籤名稱是不可改變的，表示在建立之後無法編輯它們。

2. 單一保留標籤可納入多個保留標籤原則。

3. 單一位置也可納入多個保留標籤原則。
    
3. 保留標籤原則會指定要發佈保留標籤的位置。
    
## <a name="only-one-retention-label-at-a-time"></a>一次只能有一個保留標籤

請務必了解，電子郵件或文件等內容一次只能指派一個保留標籤：
  
- 針對使用者手動指派的保留標籤，使用者可以移除或變更獲指派的保留標籤。
    
- 如果內容有指派自動套用的標籤，使用者可以手動指派保留標籤來取代自動套用的標籤。
    
- 如果內容有使用者手動指派的保留標籤，則自動套用標籤無法取代手動指派的保留標籤。
    
- 如果有多項規則會指派自動套用標籤，且內容符合多項規則的條件，則會指派最舊規則的保留標籤。
    
若要了解如何以及為何套用某個保留標籤 (而非其他標籤)，請務必了解明確指派標籤與隱含指派標籤之間的差異：

- 手動指派的標籤為明確指派
- 自動套用的標籤為隱含指派

明確指派的保留標籤會優先於隱式指派的保留標籤。 如需詳細資訊，請參閱此頁面上的[原則保留或何者優先？](#the-principles-of-retention-or-what-takes-precedence)一節。

## <a name="retention-label-policies-and-locations"></a>保留標籤原則與位置

可以將不同類型的保留標籤發佈到不同的位置，視保留標籤的功能而定。
  
|**如果保留標籤是...**|**則標籤原則可套用至...**|
|:-----|:-----|
|發佈給使用者  <br/> |Exchange、SharePoint、OneDrive、Microsoft 365 群組  <br/> |
|根據敏感資訊類型而自動套用  <br/> |Exchange (僅限所有信箱)、SharePoint、OneDrive  <br/> |
|根據查詢而自動套用  <br/> |Exchange、SharePoint、OneDrive、Microsoft 365 群組  <br/> |
   
在 Exchange 中，您只能在新傳送的郵件 (傳輸中的資料) 上自動套用保留標籤功能 (適用於查詢和敏感性資訊類型)，而非目前在信箱中的所有郵件 (待用資料)。 此外，您只能在所有信箱中為敏感性資訊類型自動套用保留標籤功能，但無法選取特定信箱。
  
Exchange 公用資料夾、Skype 和 Teams 頻道訊息和聊天不支援保留標籤。

## <a name="how-retention-labels-enforce-retention"></a>保留標籤如何強制保留

保留標籤可強制執行與保留原則可執行的相同動作，即保留然後刪除、僅保留或僅刪除。 您可以使用保留標籤來執行複雜的檔案規劃，以識別具有不同保留設定的特定檔案。 如需保留運作方式的詳細資訊，請參閱[了解保留原則](retention-policies.md)。

除此之外，保留標籤有兩個只能用於保留標籤，但不能用於保留原則的保留選項。使用保留標籤，您可以：
  
- 在保留期間結束時觸發處置檢閱，如此一來，必須先檢閱 SharePoint 和 OneDrive 文件，才能將它們刪除。 如需詳細資訊，請參閱[處置檢閱](disposition.md#disposition-reviews)。
    
- 保留期間是從內容套用標籤時開始計算，而不是內容的壽命或上次修改時間。 當您使用這個選項時：
    - 它僅會套用到 SharePoint 網站和 OneDrive 帳戶中的內容。 針對 Exchange 電子郵件，保留期間一律會取決於傳送或接收郵件的日期。
    - 儲存標籤後，無法變更保留期間。
    
![保留設定與標籤專用的選項](../media/c49118c9-6279-4661-94db-deffa76e27ac.png)

另一個重要的差異是，當您在 SharePoint 中將保留標籤而非保留原則套用至檔案，且標籤設定為保留內容時，使用者將無法在強制執行保留期間時刪除檔案。 當您將相同標籤套用至 OneDrive 中的檔案和電子郵件時，使用者可以刪除內容，除非標籤將內容標示為記錄。

## <a name="where-published-retention-labels-can-appear-to-end-users"></a>可以向使用者顯示已發佈保留標籤的位置

如果保留標籤將由使用者指派給內容，您可以將它發佈到：
  
- Outlook 和 Outlook 網頁版
    
- OneDrive
    
- SharePoint
    
- Microsoft 365 群組 (Outlook 網頁版中的群組網站和群組信箱)
    
以下各節說明標籤在不同應用程式中向組織內人員顯示的方式。
  

### <a name="outlook"></a>Outlook

若要在 Outlook 電腦版用戶端套用標籤到項目，請選取該項目。 在功能區的 [常用]**** 索引標籤上，按一下 [指派原則]****，然後選擇保留標籤。 
  
![指派原則按鈕](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
您也能夠以滑鼠右鍵按一下該項目，按一下操作功能表中的 [指派原則]****，然後選擇保留標籤。 

套用保留標籤後，您可以在項目頂端檢視該保留標籤以及所採取的動作。 如果電子郵件已套用具有相關聯保留期間的保留標籤，您可以快速查看電子郵件的到期日。
  
您也可以將保留標籤套用到資料夾，在此情況下：
  
- 資料夾中的所有項目會自動套用相同的保留標籤，但先前已明確套用保留標籤的項目**除外**。 明確套用標籤的項目會保有現有的保留標籤。 如需詳細資訊，請參閱此頁面上的[原則保留或何者優先？](#the-principles-of-retention-or-what-takes-precedence)一節。 
    
- 如果您變更或移除資料夾的預設保留標籤，資料夾中的所有項目也會變更或移除該保留標籤，明確指派保留標籤的項目**除外**。 
    
- 如果您將有預設保留標籤的項目從某個資料夾移到另一個具有不同預設保留標籤的資料夾，該項目就會套用新的預設保留標籤。
    
- 如果您將有預設保留標籤的項目從某個資料夾移到另一個沒有不同預設保留標籤的資料夾，就會移除舊的預設保留標籤。

### <a name="outlook-on-the-web"></a>Outlook 網頁版

若要在 Outlook 網頁版中的項目加上標籤，以滑鼠右鍵按一下該項目 \>[指派原則]**** \> 選擇保留標籤。 
  
![Outlook 網頁版中的指派原則功能表](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
套用保留標籤後，您可以在項目頂端檢視該保留標籤以及它採取的動作。如果電子郵件已分類，且有相關聯的保留期間，您可以一目了然電子郵件的到期日。
  
![指派給 Outlook 網頁版電子郵件的標籤](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
使用 Outlook 網頁版時，您也可以將保留標籤套用至資料夾。 

### <a name="onedrive-and-sharepoint"></a>OneDrive 和 SharePoint

若要為 OneDrive 或 SharePoint 中的文件 (包括 OneNote 檔案) 加上標籤，請選取右上角的項目 \>、選擇 [開啟詳細資料窗格]****![[資訊窗格] 圖示](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \>[套用保留標籤]**** \>，然後選擇保留標籤。 
  
您也可以將保留標籤套用至資料夾或數個文件，且可以[為文件庫設定預設保留標籤](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)。
  
![SharePoint 中項目的套用標籤清單](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
將保留標籤套用到項目之後，您可以選取項目，並在詳細資料窗格中檢視標籤。
  
![詳細資料窗格中顯示已套用的標籤](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
針對 SharePoint (而不是 OneDrive)，您可以建立包含 [標籤]**** 欄或 [項目為記錄]**** 欄的文件庫檢視。 此檢視可讓您快速查看指派給所有項目的保留標籤，以及記錄的項目。 不過，請注意，您無法依 [項目為記錄]**** 欄來篩選檢視。 如需如何新增欄的相關指示，請參閱[顯示或隱藏清單或文件庫中的欄](https://support.microsoft.com/zh-TW/office/show-or-hide-columns-in-a-list-or-library-b820db0d-9e3e-4ff9-8b8b-0b2dbefa87e2)。


### <a name="microsoft-365-groups"></a>Microsoft 365 群組

將保留標籤發佈到 Microsoft 365 群組 ([先前稱為 Office 365 群組](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) 時，保留標籤會同時顯示在群組網站和 Outlook 網頁版的群組信箱中。 將保留標籤套用至內容的程序，與套用至電子郵件和文件的程序相同。

若要保留 Microsoft 365 群組的內容，請使用 **Office 365 群組**位置。 即使 Microsoft 365 群組有 Exchange 信箱，包含整個 Exchange 位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。

此外，無法使用 Exchange 位置來包含或排除特定群組信箱。 雖然 Exchange 位置最初允許選取群組信箱，但是當您嘗試儲存保留原則時，您會收到 "RemoteGroupMailbox" 不是Exchange 位置的有效選項錯誤訊息。
  
首先，建立並設定您要提供應用程式和其他服務使用的敏感度標籤。 例如，您希望使用者從 Office 應用程式看到和套用的標籤。 

然後，建立一或多個包含您所設定的標籤和原則設定的標籤原則。 這是為您所選的使用者和位置發佈標籤和設定的標籤原則。

## <a name="applying-a-retention-label-automatically-based-on-conditions"></a>根據條件自動套用保留標籤

保留標籤最實用的功能之一，是將標籤自動套用至符合特定條件的內容。 在此情況下，貴組織中的人員不必親自套用保留標籤。 Microsoft 365 會執行這些動作。
  
![自動套用標籤的角色和工作圖](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
自動套用保留標籤很強大是因為：
  
- 您不需要訓練您的使用者記下所有分類。
    
- 您不需要仰賴使用者正確地將所有內容分類。
    
- 使用者不再需要了解資料控管原則，他們可以專心工作。
    
您可以選擇當內容包含以下資訊時，自動將保留標籤套用到內容：
  
- [特定敏感資訊類型](create-retention-labels.md#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [符合您所建立查詢的特定關鍵字](create-retention-labels.md#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [可訓練分類器的符合項目](create-retention-labels.md#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![自動套用標籤的選擇條件頁面](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

> [!TIP]
> 請參閱[管理具有保留標籤之 SharePoint 文件的生命週期](auto-apply-retention-labels-scenario.md)，以了解使用 SharePoint 中受管理屬性來自動套用保留標籤和實作事件導向保留的詳細案例。

## <a name="applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a>將預設保留標籤套用至 SharePoint 文件庫、資料夾或文件集中的所有內容

除了讓使用者將保留標籤套用至個別文件，您也可以將預設保留標籤套用到 SharePoint 文件庫、資料夾或文件集，讓該位置的所有文件套用預設保留標籤。
  
若為文件庫，您可以在文件庫的 **[文件庫設定]** 頁面中進行這個動作。 當您選擇預設保留標籤時，也可以選擇將該標籤套用至文件庫中的現有項目。 
  
例如，如果您有一個行銷資料的標籤，而且您知道某個文件庫只包含這個類型的內容，就能將「行銷資料」標籤設為該文件庫中所有文件的預設標籤。
  
![文件庫設定頁面上的套用標籤選項](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
如果將預設保留標籤套用到文件庫、資料夾或文件集中的現有項目：
  
- 文件庫、資料夾或文件集中的所有項目會自動套用相同的保留標籤，但先前已明確套用保留標籤的項目「除外」**** (例如記錄)。 已明確套用標籤的項目會保留現有的標籤。 如需詳細資訊，請參閱下節的[原則保留或何者優先](#the-principles-of-retention-or-what-takes-precedence)。
    
- 如果您變更或移除文件庫、資料夾或文件集的預設保留標籤，文件庫、資料夾或文件集中的所有項目也會變更或移除該保留標籤，「除了」明確套用保留標籤的項目**** (例如記錄)。
    
- 如果將有預設保留標籤的項目從一個網站集合、文件庫、資料夾或文件集移到另一個具有不同標籤的網站集合、文件庫、資料夾或文件集，該項目會保留現有的保留標籤，即使新位置有不同的預設保留標籤。 如果項目在移動前沒有標籤，則會使用新位置的預設保留標籤。

**記錄：** 如果您將預設記錄標籤套用至文件庫、資料夾或文件集，則會將記錄標籤套用到這些位置中的所有個別項目。 當您將新項目移至含有記錄標籤的位置時，該項目會標籤為記錄。 不過，如果您將預設保留標籤變更為不將內容宣告為記錄的標籤，該動作「不會」移除個別項目的記錄標籤；這些項目會保留自己的記錄標籤。 只有網站集合系統管理員能明確移除或變更記錄項目的保留標籤。

如需將內容宣告為記錄之保留標籤的詳細資訊，請參閱[了解記錄](records.md)。

## <a name="applying-a-retention-label-to-email-by-using-rules"></a>使用規則將保留標籤套用至電子郵件

在 Outlook 中，您可以建立規則來套用保留標籤或保留原則。
  
例如，您可以建立規則來將特定保留標籤套用到傳送至或接收自特定通訊群組的所有郵件。
  
若要建立規則，以滑鼠右鍵按一下項目\> [規則]**** \> [建立規則]**** \> [進階選項]**** \> [規則精靈]**** \> [套用保留原則]****。
  
![規則精靈與套用保留原則的選項](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a>將內容分類而不套用任何動作

您可以在建立保留標籤時將內容分類，而不關閉任何保留或進行其他動作。 在此情況下，您可以使用保留標籤當做文字標籤，而不強制執行任何動作。
  
例如，您可以建立不帶任何動作、名為「稍後檢閱」的保留標籤，然後將此保留標籤自動套用到包含敏感資訊類型或查詢內容的內容。
  
![標籤設定頁面中關閉保留](../media/retention-label-retentionoff.png)

  
## <a name="using-retention-labels-for-records-management"></a>將保留標籤用於記錄管理
    
您可以使用保留標籤將內容宣告為記錄。 這可以讓您在 Microsoft 365 中實作單一、一致的記錄管理策略。 如需詳細資訊，請參閱[了解記錄](records.md)。
  
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>使用保留標籤作為 DLP 原則的條件

保留標籤可強制執行保留內容的動作。此外，您也可以使用保留標籤作為資料外洩防護 (DLP) 原則的條件。DLP 原則可以對包含特定標籤的內容強制執行其他動作，例如限制存取。 
  
如需詳細資訊，請參閱[使用保留標籤做為 DLP 原則中的條件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。
  

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>原則保留或何者優先

很有可能內容會套用多個保留原則，這些原則各有不同的動作 (保留、刪除或兩者) 和保留期間。哪一個優先？請放心，最低限度，由一個原則保留的內容不會被另一個原則永久刪除。
  
![原則保留圖](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
若要了解不同標籤的保留動作如何套用至內容，請記住以下保留原則：
  
1. **保留優先於刪除。** 假設一個保留原則要在 3 年後刪除 Exchange 電子郵件，但另一個保留原則要保留 Exchange 電子郵件 5 年再刪除。任何達到 3 年的內容會遭到刪除，在使用者檢視中看不到它們，但仍會保留在 [可復原的項目] 資料夾，直到內容達到 5 年，便會永久刪除。 
    
2. **最長保留期間優先。** 如果內容套用多個保留內容的原則，則會一直保留到最長保留期間結束為止。 
    
3. **明確包含優先於隱含包含。** 意思是： 
    
    1. 如果包含保留設定的保留標籤是由使用者手動指派至項目 (例如 Exchange 電子郵件或 OneDrive 文件)，則該保留標籤會優先於在網站或信箱層級指派的原則，以及文件庫指派的預設保留標籤。 例如，如果明確保留標籤會保留 10 年，但網站指派的保留原則只會保留 5 年，則保留標籤會優先於原則。 自動套用保留標籤會被視為隱含，而不是明確，因為這類標籤是由 Microsoft 365 自動套用。
    
    2. 如果保留原則包含特定位置 (例如特定使用者的信箱或 OneDrive 帳戶)，則該原則會優先於其他套用至所有使用者信箱或 OneDrive 帳戶但未特地包含該使用者信箱的保留原則。
    
4. **最短刪除期間優先。** 同樣地，如果內容套用多個刪除內容的原則 (無保留)，則會在最短保留期間結束時刪除。 
    
了解保留原則從上到下的仲裁流程：如果所有原則或標籤套用的規則都在同一個層級，則流程會移到下一個層級來決定套用規則的優先順序。
  
最終，保留原則或保留標籤無法永久刪除任何電子文件探索保留的內容。 將保留釋出時，該內容會再次符合上述的清理程序資格。

### <a name="precedence-for-auto-labeling-with-trainable-classifiers"></a>使用可訓練分類器自動加上標籤的優先順序

系統會同時評估所有針對可訓練分類器設定的保留標籤。 如果有多個可訓練分類器偵測到某個項目，則會使用下列準則來決定要套用哪個保留標籤：

1. 設定為僅限保留或保留後刪除的保留標籤，優先順序高於設定為僅限刪除的保留標籤。

2. 針對設定為僅限保留或保留後刪除的保留標籤，保留標籤設定為最長保留期間的優先。

3. 針對設定為僅限刪除的保留標籤，設定為最短期間的保留標籤優先。

4. 相同動作和相同期間的保留標籤會導致保留標籤的選取不具有決定性。

## <a name="monitor-retention-labels"></a>監控保留標籤

您發佈或自動套用保留標籤之後，您將要驗證它們是否如預期般套用至內容。 若要監控保留標籤：
  
- **標籤活動總管**。 您可以使用總管 (如下圖中的範例所示) 來快速搜尋和檢視在過去 30 天內，SharePoint 和 OneDrive 所有內容的保留標籤活動。 如需詳細資訊，請參閱[檢視文件的標籤活動](view-label-activity-for-documents.md)。

- [標籤分析]**** 頁面。 在 Microsoft 365 合規性中心和 Microsoft 365 安全性中心中，您可以快速檢視最常使用的保留標籤和套用標籤的位置。 您也可以檢視具有特定保留標籤的所有內容。 如需詳細資訊，請參閱[利用標籤分析檢視標籤使用量](label-analytics.md)。
    
- **資料控管報告**。 您可以使用這些報告來快速檢視 Exchange、SharePoint 和 OneDrive 在過去 90 天內所有內容的保留標籤趨勢和活動。 如需詳細資訊，請參閱[檢視資料控管報告](view-the-data-governance-reports.md)。
    
![標籤活動總管](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)

## <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a>使用內容搜尋來尋找套用特定保留標籤的所有內容

將保留標籤指派至內容後 (無論是由使用者指派或自動套用)，您可以使用「內容搜尋」，尋找以特定保留標籤分類的所有內容。
  
當您建立內容搜尋時，請選擇 [合規性標籤]**** 條件，然後輸入完整的保留標籤名稱或是部分標籤名稱，再使用萬用字元。 如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。
  
![合規性標籤條件](../media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="use-retention-labels-instead-of-older-features"></a>使用保留標籤，而非較舊的功能

您可以輕鬆設定保留標籤供整個組織和其在 Microsoft 365 (包括 Exchange、SharePoint、OneDrive 和 Microsoft 365 群組) 中的內容使用。 如果您需要保留或刪除內容，或管理 Microsoft 365 任何位置中的記錄，建議您使用保留標籤。
  
有一些之前用來保留或刪除內容或管理 Microsoft 365 中記錄的其他功能。 這些功能會隨著保留標籤繼續運作。 雖然有保留標籤實作與先前功能不同的實例，但是保留標籤的演進會促進 Microsoft 365 記錄管理的未來發展。 因此，針對資料控管，我們建議您之後使用保留標籤而非下列較舊的功能。
  
### <a name="exchange-online"></a>Exchange Online

- [保留標記和保留原則](https://go.microsoft.com/fwlink/?linkid=846125)，又稱為[通訊記錄管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (僅刪除) 
    
### <a name="sharepoint-and-onedrive"></a>SharePoint 和 OneDrive

- [設定就地記錄管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保留) 
    
- [記錄中心簡介](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (保留) 
    
- [資訊管理原則](intro-to-info-mgmt-policies.md) (僅刪除) 
    
## <a name="next-steps"></a>後續步驟

如果您已準備好建立及發佈保留標籤，請參閱[建立、發佈和自動套用保留標籤](create-retention-labels.md)。
