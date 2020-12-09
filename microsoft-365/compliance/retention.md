---
title: 了解保留原則和標籤，以自動保留或刪除內容
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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 了解保留原則和保留標籤，可協助您保留所需的內容，並刪除您不想要的內容。
ms.openlocfilehash: e2833d966fb8a1fcc15cbeb02b781d9c0325b9c1
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519374"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a>了解保留原則和保留標籤

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

對大多數組織來說，其資料 (電子郵件、文件、即時訊息等) 的數量和複雜性日益增加。有效管理或控管此資訊至關重要，因為您需要：
  
- **主動遵守產業規範和內部原則**，因此您需要將某些內容至少保留一段時間，例如，Sarbanes-Oxley 法案可能會要求您將某些類型的內容保留七年。 

- **降低發生訴訟或安全性漏洞的風險**，方法為永久刪除您不再需要保留的舊內容。 
    
- **協助貴組織有效分享知識並提高靈活度**，方法為確保使用者只使用目前和相關的內容。 
    
您設定的保留設定可協助您實現所有目標。 管理內容通常需要以下兩個動作：
  
- **保留** 內容，以便無法在保留期間結束之前將其永久刪除。 
    
- 在保留期間結束之前，永久 **刪除** 內容。 
    

使用這兩個保留動作，您可以設定以下結果的保留設定：

- 僅保留：永久持續保留內容或保留指定的一段時間。
- 僅刪除：指定一段時間後刪除內容。
- 保留並刪除：將內容保留指定的時間，然後將其刪除。

這些保留設定可以使用就地內容，從而在您基於合規性原因而必須保留內容時，節省建立和設定額外儲存體的額外負荷。 此外，您不必執行自訂的程序來複製及同步處理這項資料。

## <a name="how-retention-settings-work-with-content-in-place"></a>保留設定如何與就地內容搭配使用

當內容有指派保留設定時，該內容會保留在其原始位置。 若未發生任何變更，人員可以繼續使用其文件或郵件。 但如果人員編輯或刪除保留原則中包含的內容，則會自動保留內容複本。
  
- 對於 SharePoint 和 OneDrive 網站：複本會保留在 **文件保留庫** 中。

- 針對 Exchange 信箱：複本會保留在 **[可復原的項目]** 資料夾中。 

- 針對 Teams 和 Yammer 訊息：複本會保留在名為 **SubstrateHolds** 的隱藏資料夾中，以作為 Exchange [可復原的項目 **]** 資料夾中的子資料夾。

> [!NOTE]
> [文件保留庫] 會佔用不受網站儲存空間配額限制的儲存空間。 當您對 SharePoint 和 Microsoft 365 群組使用保留設定時，可能需要增加您的儲存空間。
> 
大部分的人員無法檢視這些安全的位置和保留的內容。 在大部分的情況下，使用者甚至不需要知道其內容受保留設定的限制。

如需有關保留設定如何配合不同工作負載使用的詳細資訊，請參閱下列文章：

- [了解 SharePoint 和 OneDrive 的保留功能](retention-policies-sharepoint.md)
- [了解 Microsoft Teams 保留](retention-policies-teams.md)
- [了解 Yammer 的保留](retention-policies-yammer.md)
- [了解 Exchange 的保留](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a>保留原則和保留標籤

您可以透過標籤原則同時使用保留原則和保留標籤，以將保留設定指派給內容。 

使用保留原則為網站或信箱層級的內容指派相同的保留設定，並使用保留標籤來指派項目層級 (資料夾、文件、電子郵件) 的保留設定。

例如，如果 SharePoint 網站中的所有文件都應該保留 5 年，使用保留原則比將相同的保留標籤套用至該網站中所有文件的方法更有效率。 不過，如果該網站中的部分文件應保留 5 年，而其他文件保留 10 年，一個保留原則就不夠用。 當您必須在項目層級指定保留設定時，請使用保留標籤。 

不同於保留原則，保留標籤的保留設定會隨著內容移至您 Microsoft 365 租用戶中不同的位置。 此外，保留標籤具有以下保留原則不支援的功能： 
 
- 除了內容的年限或上次修改時間以外，還可選擇從為內容加上標籤的時間或根據事件來開始保留期間的選項。

- 使用[可訓練分類器](classifier-learn-about.md)來識別要加上標籤的內容。

- 為 SharePoint 文件套用預設標籤。

- 支援[處置檢閱](disposition-reviews.md) 以在內容永久刪除之前檢閱。

- 將內容標示為做為標籤設定一部分的[記錄](records-management.md#records)，並且在保留期間結束而刪除內容時，永遠都有 [處置證明](disposition.md#disposition-of-records) 。

### <a name="retention-policies"></a>保留原則

保留原則可以套用到以下位置：
- Exchange 電子郵件
- SharePoint 網站
- OneDrive 帳戶
- Microsoft 365 群組
- 商務用 Skype
- Exchange 公用資料夾
- Teams 通道訊息
- Teams 聊天
- Yammer 社群訊息
- Yammer 私人訊息

您可以輕鬆地將單一原則套用到多個位置，或特定位置或使用者。

保留期間開始時，您可以選擇建立內容的時間，或者只支援檔案和 SharePoint、OneDrive 和 Microsoft 365 群組位置 (上次修改內容的時間) 的時間。

專案會從保留原則指定的容器繼承保留設定。 如果在爲了保留内容而設定原則時將專案移至容器外，則會在工作負荷的安全位置保留該專案的複本。 不過，保留設定不會隨著內容移至新的位置。 如有需要，請使用保留標籤，而非保留原則。

### <a name="retention-labels"></a>保留標籤

請針對需要不同保留設定的不同類型的內容，使用保留標籤。 例如：
  
- 至少必須保留一小段時間的稅務表單。 
    
- 到達特定年限之後需要永久刪除的新聞材料。 
    
- 需要先保留一段期間之然後再永久刪除的競爭力研究。 
    
- 必須標示為記錄使之無法編輯或刪除的工作簽證。 
    
在這些情況下，保留標籤可讓您在項目層級 (文件或電子郵件) 套用治理控制的保留設定。
  
使用保留標籤，您可以：
  
- **讓貴組織中的人員手動將保留標籤套用** 至網頁上的 Outlook 和 Outlook、OneDrive、SharePoint 和 Microsoft 365 群組中的內容。 使用者通常都清楚知道自己處理的內容類型，因此可將內容分類並套用適當的保留設定。 
    
- 在當內容符合特定條件時 **自動將保留標籤套用到內容**，例如內容包含： 
    - 特定類型的敏感資訊。
    - 特定關鍵字符合您建立的查詢。
    - 可訓練分類器的模式比對。

- 針對 SharePoint 網站和 OneDrive 帳戶中的文件和電子郵件項目 (行事曆項除外)，**從內容加上標籤起就開始保留期間**。 如果您將具有此設定的保留標籤套用於行事曆項目，則保留期間從其傳送日期開始。

- **當事件發生時 (例如員工離開組織或合約到期)，開始保留期間**。

- **將預設保留標籤套用至 SharePoint 中的文件庫、資料夾或文件集**，以便儲存在該位置中的所有文件都繼承預設保留標籤。

此外，保留標籤支援跨 Microsoft 365 應用程式和服務的電子郵件和文件[記錄管理](records-management.md)。 您可以使用保留標籤將內容標記為記錄。 發生此情況且內容仍保留在 Microsoft 365 中時，標籤會針對法規原因可能所需的內容施加進一步的限制。 如需詳細資訊，請參閱 [比較允許或封鎖動作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。

與[敏感度標籤](sensitivity-labels.md)不同，如果內容是移至 Microsoft 365 以外的位置，保留標籤不會保留。

針對租用戶支援的保留標籤數量沒有任何限制。 不過，10,000 個是針對租用戶支援的原則數目上限，其中包括會套用標籤 (保留標籤原則和自動套用保留原則) 的原則，以及保留原則。

#### <a name="classifying-content-without-applying-any-actions"></a>將內容分類而不套用任何動作

雖然保留標籤的主要目的是要保留或刪除內容，但您也可以在不開啟任何保留或其他動作的情況下使用保留標籤。 在此情況下，您可以使用保留標籤當做文字標籤，而不強制執行任何動作。
  
例如，您可以建立並套用名為「稍後檢閱」的保留標籤，而不執行任何動作，然後使用該標籤於稍後尋找該內容。
  
![僅限分類的標籤設定](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>使用保留標籤作為 DLP 原則的條件

您可以將保留標籤做為 SharePoint 文件的資料外洩防護 (DLP) 原則中的條件。 例如，設定 DLP 原則以防止文件在組織外共用 (如果已套用指定的保留標籤)。

如需詳細資訊，請參閱[使用保留標籤做為 DLP 原則中的條件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。

#### <a name="retention-labels-and-policies-that-apply-them"></a>保留標籤和套用其標籤的原則

保留標籤是獨立、可重複使用的建置組塊。 保留標籤原則的主要目的是將一組保留標籤分組，以及指定您想讓這些標籤出現的目標位置。 然後，系統管理員和使用者可以將這些標籤套用至這些位置中的內容。
  
![標籤、標籤原則和位置圖表](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
當您發佈保留標籤時，會將這些標籤包含在保留標籤原則中，好讓系統管理員和使用者選擇：

- 單一保留標籤可納入多個保留標籤原則。

- 保留標籤原則會指定要發佈保留標籤的位置。

- 單一位置也可納入多個保留標籤原則。

除了保留標籤原則以外，您也可以建立一或多個自動套用原則，每一個都有單一保留標籤。 使用此原則，當您在原則中指定的條件滿足時，將自動套用保留標籤。 

#### <a name="retention-label-policies-and-locations"></a>保留標籤原則與位置

可以將不同類型的保留標籤發佈到不同的位置，視保留標籤的功能而定。
  
| 如果保留標籤是... | 標籤原則可套用至… |
|:-----|:-----|
|已發佈給系統管理員和使用者  <br/> |Exchange、SharePoint、OneDrive、Microsoft 365 群組  <br/> |
|根據敏感資訊類型或可訓練分類器而自動套用  <br/> |Exchange (僅限所有信箱)、SharePoint、OneDrive  <br/> |
|根據查詢而自動套用  <br/> |Exchange、SharePoint、OneDrive、Microsoft 365 群組  <br/> |
   
在 Exchange 中，您只能在新傳送的郵件 (傳輸中的資料) 上自動套用保留標籤功能，而非目前在信箱中的所有郵件 (待用資料)。 此外，您只能在所有信箱中為敏感性資訊類型和可訓練分類器來自動套用保留標籤功能，但無法選取特定信箱。
  
Exchange 公用資料夾、Skype、Teams 和 Yammer 訊息不支援保留標籤。 若要保留或刪除這些位置中的內容，請改用保留原則。

#### <a name="only-one-retention-label-at-a-time"></a>一次只能有一個保留標籤

電子郵件或文件等內容一次只能套用一個保留標籤。 保留標籤可以由使用者或管理員[手動](create-apply-retention-labels.md#manually-apply-retention-labels)套用，也可以使用以下任一方法自動套用：

- [自動套用標籤原則](apply-retention-labels-automatically.md)
- [SharePoint Syntex 中的文件瞭解模型](https://docs.microsoft.com/microsoft-365/contentunderstanding/apply-a-retention-label-to-a-model)
- [SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) 或 [Outlook 的預設標籤](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)
- [Outlook 規則](create-apply-retention-labels.md#automatically-applying-a-retention-label-to-email-by-using-rules)

對於標準保留標籤 (它們不會將項目標記為[記錄或監管記錄](records-management.md#records))：

- 系統管理員和使用者可以手動變更或移除套用於內容的現有保留標籤。 

- 當內容已套用保留標籤時，現有標籤不會自動移除或替換為另一個保留標籤，但有一個可能的例外：現有標籤已作為預設標籤套用。
    
    有關使用預設標籤套用標籤行為的詳細資訊，請執行以下操作：
    - SharePoint 的預設標籤：[對 SharePoint 使用預設標籤時的標籤行為](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)
    - Outlook 的預設標籤：[將預設保留標籤套用於 Outlook 資料夾](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)

- 如果有多個自動套用標籤原則可以套用保留標籤，並且內容滿足多個原則的條件，則套用最舊的自動套用標籤原則 (按建立日期) 的保留標籤。

當保留標籤將項目標記為記錄或監管記錄時，這些標籤不會自動變更。 只有容器的管理員才能手動變更或移除將項目標記為記錄而不是監管記錄的保留標籤。 如需詳細資訊，請參閱 [比較允許或封鎖動作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。

#### <a name="monitoring-retention-labels"></a>監視保留標籤

在 Microsoft 365 合規性中心中，使用 **資料分類** > **概觀** 來監視保留標籤在租用戶中的使用方式，並識別標籤項目的位置。 如需詳細資訊 (包括重要先決條件)，請參閱[了解您的資料 - 資料分類概觀](data-classification-overview.md)。

然後您可以使用[內容總管](data-classification-content-explorer.md)和[活動總管](data-classification-activity-explorer.md)深入探討詳細資料。

> [!TIP]
>請考慮使用一些其他的資料分類深入解析 (例如可訓練分類器和敏感性資訊類型)，協助您識別可能需要保留或刪除的內容，或管理記錄。

Office 365 安全性與合規性中心具有來自 **資訊控管** > **儀表板** 的保留標籤同等概觀資訊，以及來自 **資訊控管** > **標籤活動總管** 的詳細資訊。 如需從此舊版系統管理中心監視保留標籤的詳細資訊，請參閱下列文件：
- [檢視資料控管報告](view-the-data-governance-reports.md)
- [利用標籤分析檢視標籤使用量](label-analytics.md)
- [檢視文件的標籤活動](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a>使用內容搜尋來尋找具有特定保留標籤的所有內容

將保留標籤套用至內容後 (無論是由使用者套用或自動套用)，您可以使用內容搜尋來尋找已套用特定保留標籤的所有項目。

當您建立內容搜尋時，請選擇 **[保留標籤]** 條件，然後輸入完整的保留標籤名稱或是部分標籤名稱，再使用萬用字元。 如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。
  
![保留標籤條件](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a>比較保留原則和保留標籤的功能

使用下列表格來協助您判斷是否要根據功能來使用保留原則或保留標籤。

|功能|保留原則 |保留標籤|
|:-----|:-----|:-----|:-----|
|可以保留然後刪除、僅保留或僅刪除的保留設定 |是 |是 |
|支援的工作負載： <br />- Exchange <br />- SharePoint <br />- OneDrive <br />- Microsoft 365 群組 <br />- 商務用 Skype <br />- Teams<br />- Yammer|<br /> 是 <br /> 是 <br /> 是 <br /> 是 <br /> 是 <br /> 是 <br /> 是 | <br /> 是，除了公用資料夾 <br /> 是 <br /> 是 <br /> 是 <br /> 否 <br /> 否 <br /> 否 |
|自動套用的保留 | 是 | 是 |
|根據條件套用保留 <br /> - 敏感資訊類型、KQL 查詢、可訓練分類器| 否 | 是 |
|手動套用的保留 | 否 | 是 |
|使用者的 UI 目前狀態 | 否 | 是 |
|如果內容已移動，則會持續存在 | 否 | 是，在您的 Microsoft 365 租用戶中 |
|將項目宣告為記錄| 否 | 是 |
|在加上標籤起或根據事件來開始保留期間 | 否 | 是 |
|處置檢閱 | 否| 是 |
|最高 7 年的處置證明 | 否 |是，當物料宣告為記錄時|
|稽核系統管理員活動| 是 | 是|
|識別要保留的項目： <br /> - 內容搜尋 <br /> - 資料分類頁面、內容總管，活動總管 | <br /> 否 <br /> 否 | <br /> 是 <br /> 是|

請注意，您可以使用保留原則和保留標籤做為補充保留方法。 例如：

1. 您建立並設定將在內容上次修改後五年自動刪除內容的保留原則，並將該原則套用於所有 OneDrive 帳戶。

2. 您建立並設定永久保留內容的保留標籤，並將其新增至您發佈到所有 OneDrive 帳戶的標籤原則。 您向使用者說明如何手動將此標籤套用於五年後未修改應從自動刪除排除的特定文件。

有關保留原則和保留標籤如何搭配，以及如何判斷其合併結果的更多資訊，請參閱下一節解釋保留的原則和其優先順序。

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>原則保留或何者優先

內容有可能套用多個會進行不同動作 (保留、刪除或保留然後刪除) 且保留期間不同的保留原則和保留標籤。 哪個的優先順序較高？ 

在高層級中，您可以確保保留永遠優先於刪除，然後才是最長的保留期間勝出。 

但還有其他一些因素需要考慮，因此請使用以下流程來了解每個層級從上到下扮演決勝局的結果：如果結果由第一層級決定，則無需前進到下一個層級，依此類推。 只有當結果無法由層級規則決定時，流程才會移至下一個層級，以決定保留設定優先權的結果。

![原則保留圖](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
四個不同層級的說明：
  
1. **保留優先於刪除。** 假設某個保留原則設定在 3 年後刪除 Exchange 電子郵件，但另一個保留原則設定將 Exchange 電子郵件保留 5 年再刪除。 任何到達 3 年的內容會遭到刪除，並從使用者的檢視畫面隱藏，但仍會保留再 [可復原的項目] 資料夾中，直到內容到達 5 年，才會遭永久刪除。 
2. **最長保留期間優先。** 如果內容受制於在不同的期間保留內容的多個保留設定，則該內容將一直保留到最長保留期間結束為止。
    
3. **明確包含優先於隱含包含。** 也就是說： 
    
    1. 如果包含保留設定的保留標籤是由使用者手動指派至項目 (例如 Exchange 電子郵件或 OneDrive 文件)，則該保留標籤會優先於在網站或信箱層級指派的保留原則，以及指派給文件庫的預設保留標籤。 例如，如果明確保留標籤設定要保留內容十年，但對網站指派的保留原則設定為保留內容五年，則保留標籤會優先於原則。
    
    2. 如果保留原則包含特定位置 (例如特定使用者的信箱或 OneDrive 帳戶)，則該保留原則會優先於其他套用至所有使用者信箱或 OneDrive 帳戶但未特地包含該使用者信箱的保留原則。
    
4. **最短刪除期間優先。** 同樣地，如果內容受限於會刪除內容但不帶保留期間的多個保留設定，則會在最短刪除期間結束時刪除該內容。 

最終，保留原則或保留標籤無法永久刪除任何電子文件探索保留的內容。 將保留釋出時，該內容會再次符合上述的清理程序資格，並在工作負載的受保護位置中進行。

## <a name="use-preservation-lock-to-restrict-changes-to-policies"></a>使用「保留鎖定」來限制原則變更

有些組織可能需要遵守由控管機構定義的規則，例如證券交易委員會 (SEC) 規定 17a-4，要求在保留原則開啟之後，不能關閉或執行較不嚴格的限制。 

「保留鎖定」可確保您的組織能夠符合這類法規需求，因為它會鎖定保留原則或保留標籤原則，使得沒有任何人 (包括系統管理員) 可以關閉原則、刪除原則或降低限制。
  
建立保留原則或保留標籤原則之後，您可以套用「保留鎖定」。 如需更多資訊和指示，請參閲[使用保留鎖定來限制變更保留原則和保留標籤原則](retention-preservation-lock.md)。

## <a name="releasing-a-policy-for-retention"></a>發佈保留原則

如果您的保留原則沒有保留鎖定，您可以隨時刪除您的原則，以便有效地關閉先前套用的保留設定。 您也可以維持原有的保留原則，但將位置狀態變更為 [關閉]。
 
當您這麼做時，保留在文件保留庫中的任何 SharePoint 或 OneDrive 的內容不會立即永久被刪除。 相反地，為了防止意外的資料遺失，我們有 30 天的寬限期，在這期間，保留文件庫中不會發生該原則的內容到期，因此，如有需要，您可以在這裡還原任何內容。 此外，您無法在寬限期期間手動刪除此內容。

您可以在寬限期期間將位置狀態變更為 [開啟]，這麼一來，該原則的內容將不會被刪除。

SharePoint 和 OneDrive 中的此 30 天寬限期與 Exchange 中的 30 天延遲保留對應。 如需詳細資訊，請參閱[管理延遲保留信箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。

## <a name="auditing-retention-configuration"></a>稽核保留設定

[啟用稽核功能](turn-audit-log-search-on-or-off.md)後，系統會將保留原則和保留標籤的系統管理員動作儲存至稽核記錄。 例如，建立、設定或刪除保留原則或標籤後，系統會建立稽核事件。 如需完整清單，請參閱[保留原則和保留標籤活動](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)。

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a>保留原則和保留標籤的 PowerShell Cmdlet

若要使用保留 Cmdlet，您必須先[連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。 然後使用以下任一 Cmdlet：

- [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a>何時使用保留原則和保留標籤或電子文件探索保留？

雖然您使用保留設定和[電子文件探索案例所建立的保留](create-ediscovery-holds.md)都可以防止資料永久刪除，但它們是為不同情況而設計的。 若要協助您了解差異及決定使用哪個，請使用下列指南：

- 您在 [保留原則] 和 [保留標籤] 中指定的保留設定，是專為長期資訊控管而設計，以保留或刪除符合法規需求的資料。 範圍通常很廣，主要重點是位置和內容，而不是個別使用者。 保留期間的開始和結束是可設定的，可選擇自動刪除內容，而不需要其他系統管理員介入。

- 電子文件探索的保留 (核心電子文件探索或進階電子文件探索案例) 是專為保留資料以供法律調查所設計。 該範圍是特定的，且重點是已識別使用者所擁有的內容。 保留期間的開始和結束不會進行設定，但與個別系統管理員的動作相關，沒有選項可在保留解除時自動刪除內容。

比較保留與電子文件探索保留的摘要：

|考量事項|保留 |電子文件探索保留|
|:-----|:-----|:-----|:-----|
|商務需求： |合規性 |法律資訊 |
|時間範圍： |長期 |短期 |
|焦點： |廣泛的、內容型 |特定的、使用者型 |
|開始和結束日期可設定： |是 |否 |
|內容刪除： |是 (選用) |否 |
|系統管理開銷： |低 |高 |

如果內容同時受制於保留設定和電子文件探索保留，則電子文件探索保留的內容保留永遠優先。 如此一來，[保留的原則](#the-principles-of-retention-or-what-takes-precedence)會擴充至電子文件探索保留，因為系統會在管理員手動解除保留之前，將資料保留。 不過，儘管這個優先順序，請不要將電子文件探索保留用於長期資訊控管。 如果您擔心自動刪除資料，您可以設定保留設定以永遠保留項目，或對保留標籤使用[處置評審](disposition.md#disposition-reviews)。

如果您使用舊版電子文件探索工具來保留資料，請參閱下列資源：

- Exchange： 
    - [就地保留與訴訟資料暫留](https://go.microsoft.com/fwlink/?linkid=846124)
    - [如何找出位於 Exchange Online 信箱的保留類型](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox) (英文)

- SharePoint 和 OneDrive： 
    - [在電子文件探索中心將內容新增至案例及保留來源](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (英文)

- [舊版電子文件探索工具淘汰](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a>請使用保留原則和保留標籤，而非舊版的功能

如果您必要在 Microsoft 365 中預先主動保留或刪除內容，我們建議您使用保留原則和保留標籤，而非以下較舊的功能。

如果您目前使用這些較舊的功能，這些功能會隨著保留原則和保留標籤繼續運作。 不過，建議您今後改為使用保留原則和保留標籤。 它們提供單一機制來集中管理 Microsoft 365 內容的保留與刪除。

**來自 Exchange Online 的舊版功能：**

- [保留標記和保留原則](https://go.microsoft.com/fwlink/?linkid=846125)，又稱為[通訊記錄管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (僅刪除)

**來自 SharePoint 和 OneDrive 的舊版功能：**

- [文件刪除原則](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (僅刪除)
    
- [設定就地記錄管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (僅保留) 
    
- [網站關閉及刪除的使用原則](https://support.microsoft.com/zh-TW/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (僅刪除) 
    
- [資訊管理原則](intro-to-info-mgmt-policies.md) (僅刪除)
     
如果您已設定 SharePoint 網站的內容類型原則或資訊管理原則，以保留清單或文件庫的內容，當保留原則生效時，會忽略這些原則。 

## <a name="related-information"></a>相關資訊

- [SharePoint Online 限制](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Microsoft Teams 的限制和規格](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [協助您符合資訊管理與記錄管理法規需求的資源](retention-regulatory-requirements.md)

## <a name="next-steps"></a>後續步驟

如果您已準備好建立保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。

若要建立及套用保留標籤：
- [建立保留標籤，並在應用程式中使用這些標籤](create-apply-retention-labels.md)
- [自動將保留標籤套用到內容](apply-retention-labels-automatically.md)

