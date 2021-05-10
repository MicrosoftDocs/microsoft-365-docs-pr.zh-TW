---
title: Microsoft Defender for Office 365 威脅瀏覽器中的威脅搜尋
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 使用安全規範中心中的威脅瀏覽器或即時偵測 &amp; ，以有效地調查和回應威脅。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65fe67103d9a380c63a0362594c23290457ea3aa
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52295229"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 威脅瀏覽器中的威脅搜尋

本文內容：

- [威脅瀏覽器逐步流覽](#threat-explorer-walk-through)
- [電子郵件調查](#email-investigation)
- [電子郵件修復](#email-remediation)
- [威脅搜尋體驗的增強功能](#improvements-to-threat-hunting-experience)

> [!NOTE]
> 這是 **威脅 Explorer (Explorer)**、**電子郵件安全性** 及 **Explorer 和即時** 偵測 (基礎的 **3 篇文章** 中的一部分，例如工具間的差異，以及操作) 所需的許可權。 此系列中的其他兩篇文章是 [使用威脅瀏覽器的電子郵件安全性](email-security-in-microsoft-defender.md) 和 [威脅瀏覽器，以及即時的偵測基礎知識](real-time-detections.md)。


**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

如果您的組織有 [Office 365 的 Microsoft Defender](defender-for-office-365.md)，而且您具有 [許可權](#required-licenses-and-permissions)，您可以使用 **Explorer** 或 **即時** 偵測來偵測和修正威脅。 

在 [ **安全性 & 規範中心**] 中，移至 [ **威脅管理**]，然後選擇 [ **Explorer** ] _或_[ **即時** 偵測]。

<br>

****

|使用 Microsoft Defender Office 365 方案2，您會看到：|使用 Microsoft Defender Office 365 方案1，您會看到：|
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

使用這些工具，您可以：

- 查看 Microsoft 365 安全性功能偵測到的惡意程式碼
- 查看網路釣魚 URL，然後按一下 [已判定資料]
- 從瀏覽器中的視圖開始自動調查和回應程式
- 調查惡意電子郵件及其他

如需詳細資訊，請參閱 [使用威脅瀏覽器的電子郵件安全性](email-security-in-microsoft-defender.md)。 

## <a name="threat-explorer-walk-through"></a>威脅瀏覽器逐步流覽

在 Microsoft Defender for Office 365 中，有兩個訂閱者案（方案1和方案2）。 手動運作的威脅搜尋工具，都存在於兩個計畫中的不同名稱和不同功能。

Office 365 方案1的 Defender 使用 *即時* 偵測，也就是 *威脅瀏覽器* 的子集 (也稱為計畫2中的 *Explorer*) 搜尋工具。 在此系列文章中，大部分的範例是使用完整威脅瀏覽器建立的。 管理員應該在即時偵測中測試任何步驟，以查看其適用的位置。

若要開啟 Explorer 工具，請移至 **Security & 合規性中心**  >  **威脅管理**  >  **瀏覽器** (或 **即時** 偵測) 。 依預設，您會到達 **惡意軟體** 頁面，但使用 [View] （ **查看** ）下拉式功能表以熟悉您的選項。 如果您要搜尋網路釣魚網路，或鑽研至威脅活動，請選擇這些視圖。

> [!div class="mx-imgBorder"]
> ![威脅瀏覽器中的 View 下拉式清單](../../media/threat-explorer-view-drop-down.png)

一旦安全性作業 (Sec Op) 人員會選取他們想要查看的資料、範圍是否如使用者 **報送** 或更大的查看（如 **所有電子郵件**），他們可以使用 [ **寄件者** ] 按鈕進一步篩選。 請記得選取 [重新整理]，以完成篩選動作。

> [!div class="mx-imgBorder"]
> ![威脅瀏覽器中的寄件者按鈕](../../media/threat-explorer-sender-button.png)

若要在瀏覽器中精煉焦點或即時偵測，您可以在層中想到。 第一個是 **View**。 第二個可以視為 *篩選的焦點*。 例如，您可以透過記錄決策來回溯您在尋找威脅時所採取的步驟：若要在瀏覽器中找出問題， **我選擇具有收件者篩選器焦點的惡意程式碼視圖**。 這可讓您更輕鬆 retracing 步驟。

> [!TIP]
> 如果 Sec Ops 使用標籤來標示其考慮高值 **目標的帳戶** ，他們可以像網路釣魚視圖一樣，進行選擇 *篩選焦點 (包括使用) 的日期範圍*。 這會在時間範圍 (等時間範圍內，向使用者顯示其高價值的使用者目標，例如，當某些網路釣魚攻擊針對其行業) 所發生的情況。 

您可以使用日期範圍控制項，對日期範圍進行改進。 在這裡，您可以在 **惡意** 代碼視圖中查看瀏覽器，並使用 **偵測技術** 篩選焦點。 但它是可讓 Sec Ops 小組深入瞭解的「 **高級篩選** 」按鈕。 

> [!div class="mx-imgBorder"]
> ![威脅瀏覽器中的高級篩選](../../media/threat-explorer-advanced-filter.png)

按一下 [ **高級] 篩選器** 會彈出面板，讓每個 hunters 建立查詢本身，讓它們包含或排除所需查看的資訊。 瀏覽器頁面上的圖表和表格都會反映其結果。 

> [!div class="mx-imgBorder"]
> ![查詢的結果](../../media/threat-explorer-chart-table.png)

使用 [ **欄選項** ] 按鈕，以取得表格中最有説明的資訊類型： 

> [!div class="mx-imgBorder"]
> ![高亮顯示欄選項按鈕](../../media/threat-explorer-column-options.png)

> [!div class="mx-imgBorder"]
> ![欄中可用的選項](../../media/threat-explorer-column-options-details.png)

在同一個 mien 中，請務必測試顯示選項。 不同的物件會對相同資料的不同簡報有很好的反應。 針對有些檢視器， **電子郵件來源** 地圖可顯示威脅的普及或更快，比其旁邊的 [ **市場活動顯示** ] 選項更快。 每秒 Op 可以利用這些顯示效果，使底線成為安全性和保護的必要點，或用於進行後續比較，以示範其動作的效能。 

> [!div class="mx-imgBorder"]
> ![電子郵件來源地圖](../../media/threat-explorer-email-origin-map.png)

> [!div class="mx-imgBorder"]
> ![市場活動顯示選項](../../media/threat-explorer-campaign-display.png)

### <a name="email-investigation"></a>電子郵件調查

當您看到可疑的電子郵件時，按一下名稱以展開右側的飛出視窗。 在這裡，允許 Sec Ops 的橫幅會看到 [ [電子郵件實體] 頁面](mdo-email-entity-page.md) 可供使用。

[電子郵件實體] 頁面會將可在 [ **詳細** 資料]、[ **附件**]、[ **裝置**] 底下找到的內容，包含更多組織的資料。 這包括 DMARC 結果、純文字顯示（含副本選項的電子郵件標題）、判定已安全引爆之附件的資訊，以及 detonations 丟棄的檔案， (可以包含已連接的 IP 位址，以及) 的頁面或檔案的螢幕擷取畫面。 URLs 及其 verdicts 也會以報告的類似詳細資料列出。 

當您到達此階段時，[電子郵件實體] 頁面將對最後一個步驟（*修正*）很重要。 

> [!div class="mx-imgBorder"]
> ![電子郵件實體頁面](../../media/threat-explorer-email-entity-page.png)

> [!TIP]
> 若要深入瞭解 [ **分析** ] 索引標籤上的 [豐富的電子郵件實體) ] 頁面 (，包括引爆附件的結果、包含 URLs 的結果，以及安全的電子郵件預覽，請按一下 [這裡](mdo-email-entity-page.md)。

> [!div class="mx-imgBorder"]
> ![電子郵件實體頁面的 [分析] 索引標籤](../../media/threat-explorer-analysis-tab.png)

### <a name="email-remediation"></a>電子郵件修復

當 Sec Op 人員判斷電子郵件成為威脅之後，下一個瀏覽器或即時偵測步驟便會處理威脅並修正該威脅。 若要執行此動作，可以傳回威脅瀏覽器，選取問題電子郵件的核取方塊，然後使用 [ **動作** ] 按鈕。

> [!div class="mx-imgBorder"]
> ![威脅瀏覽器中的 [動作] 按鈕](../../media/threat-explorer-email-actions-button.png)

在這裡，分析員可以採取類似于垃圾郵件、網路釣魚或惡意程式碼等動作來報告郵件，也就是在您有計劃 2) 的情況下，可以包含觸發自動調查和回應 (或 AIR) 行動手冊 (的其他調查。 或者，也可以將郵件報告為乾淨。

> [!div class="mx-imgBorder"]
> ![[動作] 下拉式清單](../../media/threat-explorer-email-actions-drop-down.png)

## <a name="improvements-to-threat-hunting-experience"></a>威脅搜尋體驗的增強功能

### <a name="alert-id"></a>警示識別碼

從警示流覽至威脅瀏覽器時，會依照 **警示識別碼** 篩選該 **視圖**。 這也適用于即時偵測。 會顯示與特定警示相關的郵件，以及 (計數) 的電子郵件總數。 您將能夠查看郵件是否屬於警示的一部分，以及從該郵件流覽至相關的警示。

最後，警示識別碼會包含在 URL 中，例如： `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`

> [!div class="mx-imgBorder"]
> ![警示識別碼的篩選](../../media/AlertID-Filter.png)

> [!div class="mx-imgBorder"]
> ![詳細資料快顯視窗中的警示識別碼](../../media/AlertID-DetailsFlyout.png)

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a>延伸 Explorer (和即時偵測) 資料保留與試用承租人的搜尋限制 

在此變更中，分析者將可以搜尋並篩選超過30天的電子郵件資料 (會在威脅瀏覽器中增加7天) ，在威脅瀏覽器中增加，針對 Office P1 和 P2 試用租使用者的 Defender 進行即時偵測。 這不會影響 P1 和 P2 E5 客戶的任何實際執行承租人，保留預設值為已30天。

### <a name="updated-export-limit"></a>更新的匯出限制 

可以從威脅瀏覽器匯出的電子郵件記錄數目現在是 200000 (為 9990) 。 可以匯出的一組資料行不會變更。 

### <a name="tags-in-threat-explorer"></a>威脅瀏覽器中的標記

> [!NOTE]
> [使用者標記] 功能是在預覽中，並非所有人都可以使用。 此外，預覽可能也會變更。 如需發行排程的相關資訊，請參閱 Microsoft 365 藍圖。

使用者標記識別 Microsoft Defender 中 Office 365 的特定使用者群組。 如需標記的相關資訊（包括授權和設定），請參閱 [User tags](user-tags.md)。

在威脅瀏覽器中，您可以在下列體驗中看到使用者標記的相關資訊。

#### <a name="email-grid-view"></a>電子郵件格線視圖

當分析員查看 [ **標記** ] 欄的電子郵件格線時，他們會看到所有已套用到寄件者或收件者信箱的標記。 依預設，會先顯示「 *優先順序」帳戶* 之類的系統標記。

> [!div class="mx-imgBorder"]
> ![在電子郵件格線視圖中篩選標記](../../media/tags-grid.png)

#### <a name="filtering"></a>篩選

標記可用作篩選。 以這種方式，只在優先順序帳戶中加以搜尋，或使用特定的使用者標記案例。 您也可以排除包含某些標記的結果。 結合標記與其他篩選和日期範圍，以縮小您的調查範圍。 

[![篩選標記](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![不篩選標記](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>電子郵件詳細資料快顯視窗

若要查看寄件者和收件者的個別標記，請選取電子郵件以開啟 [郵件詳細資料] 浮出。 在 [ **摘要** ] 索引標籤上，會分別顯示寄件者和收件者標記。 寄件者和收件者個別標記的相關資訊可匯出為 CSV 資料。 

> [!div class="mx-imgBorder"]
> ![電子郵件詳細資料標記](../../media/tags-flyout.png)

標記資訊也會顯示在 URL 中按一下 [飛入]。 若要查看，請移至網路釣魚或所有電子郵件 view > **URLs** 或 **URL 按一下** ] 索引標籤。選取個別的 [URL] 飛出，以查看有關該 URL 之按一下的其他詳細資料，包括任何與該按一下相關聯的標記。

### <a name="updated-timeline-view"></a>更新時程表視圖

> [!div class="mx-imgBorder"]
> ![URL 標記](../../media/tags-urls.png)
>
觀看[此影片](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)瞭解更多資訊。

## <a name="extended-capabilities"></a>延伸功能

### <a name="top-targeted-users"></a>主要目標使用者

主要惡意程式碼系列會顯示惡意程式碼區段中 **主要的目標使用者** 。 主要的目標使用者將透過網路釣魚和所有電子郵件視圖延伸。 分析員將可以查看前5位目標使用者，以及每個視圖中每位使用者的嘗試次數。 

安全性作業使用者可以匯出目標使用者的清單，最多可匯出3000的限制，以及嘗試的次數，以供每個電子郵件 view 之離線分析使用。 此外，選取 [嘗試次數] (例如，13在下列的圖像中嘗試) 會在威脅瀏覽器中開啟篩選的視圖，這樣您就能看到有關電子郵件的詳細資料，以及該使用者的威脅。  

> [!div class="mx-imgBorder"]
> ![主要目標使用者](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>傳輸規則 Exchange

安全性作業小組能夠在電子郵件格線視圖中查看所有 Exchange 的傳輸規則 (或郵件流程規則) 套用至郵件。 選取格線中的 [**欄選項**]，然後從 [欄] 選項 **新增 Exchange 傳輸規則**。 在電子郵件中的 [**詳細資料**] 快顯視窗中也會顯示 Exchange 傳輸規則] 選項。 

會出現套用至郵件的傳輸規則名稱及 Guid。 分析員將可以使用傳輸規則的名稱來搜尋郵件。 這是包含搜尋，也就是您也可以進行部分搜尋。 

> [!IMPORTANT]
> Exchange 傳輸規則搜尋與名稱可用性取決於指派給您的特定角色。 您必須具有下列其中一個角色或許可權，才能查看傳輸規則名稱和搜尋。 不過，即使沒有下列角色或許可權，分析員還是可以在電子郵件詳細資料中看到傳輸規則標籤及 GUID 資訊。 其他記錄流覽的電子郵件格線、電子郵件 flyouts、篩選和匯出不會受到影響。
>
> - Exchange Online僅資料遺失防護：全部
> - Exchange Online僅 O365SupportViewConfig： All
> - Microsoft Azure Active Directory 或 Exchange Online 安全性管理員： All
> - Azure Active Directory 或 Exchange Online 安全性讀者： All
> - Exchange Online僅傳輸規則：全部
> - Exchange Online僅 View-Only 設定：全部
>
> 在電子郵件格線、詳細資料浮出和匯出的 CSV 中，ETRs 會以如下所示的名稱/GUID 呈現。
>
> > [!div class="mx-imgBorder"]
> > ![Exchange傳輸規則](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>輸入連接器

連接器是一組指示，可自訂您的電子郵件進出 Microsoft 365 或 Office 365 組織的方式。 它們可讓您套用任何安全性限制或控制項。 在 [威脅瀏覽器] 中，您可以查看與電子郵件相關的連接器，並搜尋使用連接器名稱的電子郵件。 

連接器的搜尋是包含查詢，這表示部分關鍵字搜尋可以運作： 

> [!div class="mx-imgBorder"]
> ![連接器詳細資料](../../media/Connector_Details.png)

## <a name="required-licenses-and-permissions"></a>必要的授權和權限

您必須具有[Microsoft Defender Office 365](defender-for-office-365.md) ，才能使用 Explorer 或即時偵測。

- Explorer 會包含在 Office 365 方案2的 Defender 中。
- 在 Office 365 方案1的 Defender 中包含即時偵測報告。
- 規劃為所有應受 Office 365 Defender 保護的使用者指派授權。 瀏覽器和即時偵測顯示已授權使用者的偵測資料。

若要查看和使用 Explorer 或即時偵測，您必須具備下列各項：

- 針對安全性 & 規範中心：

  - 組織管理
  - 安全性管理員 (可以在 Azure Active Directory 系統管理中心 (中指派 <https://aad.portal.azure.com>) 
  - 安全性讀取者

- Exchange Online：

  - 組織管理
  - 僅限檢視組織管理
  - 僅限檢視收件者
  - 合規性管理

若要深入了解角色和權限，請參閱下列資源：

- [安全性與合規性中心的權限](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online 中的功能權限](/exchange/permissions-exo/feature-permissions)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>其他資訊

- [尋找並調查傳送的惡意電子郵件](investigate-malicious-email-that-was-delivered.md) 
- [檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案](mdo-for-spo-odb-and-teams.md) 
- [取得威脅瀏覽器中的視圖 (和即時偵測的概覽) ](threat-explorer-views.md) 
- [威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report) 
- [Microsoft 威脅防護的自動化調查及回應](automated-investigation-response-office.md) 
- [使用電子郵件實體頁面調查電子郵件](mdo-email-entity-page.md)