---
title: 威脅瀏覽器和即時偵測
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 在 Microsoft 365 Defender 入口網站中使用 Explorer 和即時偵測，以有效地調查威脅並作出回應。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d3dc8c205d5edfe455884d64030c7a6070762adb
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108544"
---
# <a name="threat-explorer-and-real-time-detections"></a>威脅瀏覽器和即時偵測

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

如果您的組織有 [Office 365 的 Microsoft Defender](defender-for-office-365.md)，而且您具有 [必要的許可權](#required-licenses-and-permissions)，您就會有 **瀏覽器** 或 **即時** 偵測 (以前的 *即時報告*-[請參閱「新增功能](#new-features-in-threat-explorer-and-real-time-detections)！ ) 」。 在 [安全性 & 規範中心] 中，移至 [ **威脅管理**]，然後選擇 [ **Explorer** ] _或_[ **即時** 偵測]。

<br>

****

|使用 Microsoft Defender Office 365 方案2，您會看到：|使用 Microsoft Defender Office 365 方案1，您會看到：|
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

瀏覽器或即時偵測可協助您的安全性作業小組調查並有效地回應威脅。 報告類似下列影像：

![移至威脅管理 \> 總管](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

您可以使用此報告：

- [查看 Microsoft 365 安全性功能偵測到的惡意程式碼](#see-malware-detected-in-email-by-technology)
- [查看網路釣魚 URL，然後按一下 [已判定資料]](#view-phishing-url-and-click-verdict-data)
- [從瀏覽器的視圖中啟動自動調查和回應](#start-automated-investigation-and-response)程式 (Office 365 僅限方案 2) 
- [調查惡意電子郵件及其他](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-hunting-experience"></a>威脅搜尋體驗的增強功能

### <a name="introduction-of-alert-id-for-mdo-alerts-within-explorerreal-time-detections-preview"></a>Explorer/即時偵測內 MDO 警示的警示識別碼簡介 (預覽) 

現在，如果您從警示流覽至威脅瀏覽器，它就會在瀏覽器中開啟篩選的視圖，並以警示原則識別碼篩選 (原則識別碼為警示原則) 的唯一識別碼。
在威脅瀏覽器和即時偵測中引入警示識別碼，使這項整合更為相關 (在威脅瀏覽器和即時偵測中看到警示) 識別碼的範例，這樣您就能看到與特定警示相關的訊息，以及電子郵件的計數。 您也可以查看郵件是否為警示的一部分，以及從該郵件流覽至特定警示。

當您查看個別的警示時，URL 內可使用警示識別碼;範例為 `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1` 。

> [!div class="mx-imgBorder"]
> ![警示識別碼的篩選](../../media/AlertID-Filter.png)

> [!div class="mx-imgBorder"]
> ![詳細資料快顯視窗中的警示識別碼](../../media/AlertID-DetailsFlyout.png)

### <a name="extending-the-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants-from-7-to-30-days-preview"></a>將瀏覽器的 (和即時的偵測功能延伸) 從7天到30天 (預覽的試用承租人的資料保留和搜尋限制) 

在這項變更中，您將可以搜尋和篩選超過30天的電子郵件資料 (在威脅瀏覽器/即時偵測中，針對 Office P1 和 P2 試用租使用者的 Defender，進行過去7天) 中的增加。
這不會影響 P1 和 P2/E5 客戶的任何實際執行承租人，其已有30天的資料保留和搜尋功能。

### <a name="updated-limits-for-export-of-records-for-threat-explorer-preview"></a>更新威脅瀏覽器的記錄匯出 (預覽的限制) 

做為此更新的一部分，可從威脅瀏覽器匯出的電子郵件記錄的列數會從9990增加為200000記錄。 目前可匯出的一組資料行將保持不變，但是列數會從目前的限制增加。

### <a name="tags-in-threat-explorer"></a>威脅瀏覽器中的標記

> [!NOTE]
> 使用者標記功能是在 *預覽* 中，並非所有人都可以使用，而且可能會變更。 如需發行排程的相關資訊，請參閱 Microsoft 365 藍圖。

使用者標記識別 Microsoft Defender 中 Office 365 的特定使用者群組。 如需標記的相關資訊（包括授權和設定），請參閱 [User tags](user-tags.md)。

在威脅瀏覽器中，您可以在下列體驗中看到使用者標記的相關資訊。

#### <a name="email-grid-view"></a>電子郵件格線視圖

電子郵件窗格中的 [ **標記** ] 欄包含已套用至寄件者或收件者信箱的所有標記。 依預設，會先顯示「優先順序」帳戶之類的系統標記。

> [!div class="mx-imgBorder"]
> ![在電子郵件格線視圖中篩選標記](../../media/tags-grid.png)

#### <a name="filtering"></a>篩選

您可以使用標記做為篩選。 只需在優先順序帳戶或特定使用者標記案例中尋找。 您也可以排除包含某些標記的結果。 將此功能與其他篩選器結合，以縮小您的調查範圍。

[![篩選標記](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![不篩選標記](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>電子郵件詳細資料快顯視窗

若要查看寄件者和收件者的個別標記，請選取 [主旨] 以開啟 [郵件詳細資料] 浮出。 在 [ **摘要** ] 索引標籤上，[寄件者] 和 [收件者] 標記會分開顯示（如果它們是針對電子郵件）
寄件者和收件者個別標記的相關資訊也會延伸至匯出的 CSV 資料，您可以在兩個不同的欄中查看這些詳細資料。

> [!div class="mx-imgBorder"]
> ![電子郵件詳細資料標記](../../media/tags-flyout.png)

標記資訊也會顯示在 URL 中按一下 [飛入]。 若要查看，請移至 [網路釣魚] 或 [所有電子郵件] 視圖，然後按一下 [ **URLs** ] 或 [URL] [ **按一下** ]選取個別的 [URL] 浮出視窗，以查看有關該 URL 之按一下的其他詳細資料，包括與該按一下關聯的標記。

### <a name="updated-timeline-view"></a>更新時程表視圖

> [!div class="mx-imgBorder"]
> ![URL 標記](../../media/tags-urls.png)
>
觀看[此影片](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)瞭解更多資訊。

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>對即將推出之威脅搜尋體驗的增強 () 

### <a name="updated-threat-information-for-emails"></a>更新的電子郵件威脅資訊

我們已著重于平臺和資料品質改進，以提升電子郵件記錄的資料準確性和一致性。 增強功能包括將預先傳遞和交付後資訊的整合，例如，將電子郵件上執行的動作當做處理成單一記錄。 其他詳細資料，例如垃圾郵件決定、實體層級威脅 (例如，哪些 URL 為惡意) ，以及最近的傳遞位置也包含在內。

在這些更新後，不論會影響郵件的不同傳遞事件為何，您都會看到每一封郵件的單一專案。 動作可包含 ZAP、手動修正 (，這表示系統管理動作) 、動態傳遞等等。

除了顯示惡意程式碼和網路釣魚威脅之外，您還會看到與電子郵件相關聯的垃圾郵件結論。 在電子郵件內，查看與電子郵件相關的所有威脅，以及對應的偵測技術。 電子郵件可以有零個、一或多個威脅。 您會在 [電子郵件] 浮出控制項的 [ **詳細資料** ] 區段中看到目前的威脅。 針對多種威脅 (例如惡意程式碼和網路釣魚) ，「 **偵測技術** 」欄位會顯示威脅偵測對應，也就是識別威脅的偵測技術。

一組偵測技術現在包含新的偵測方法，也包含垃圾郵件偵測技術。 您可以使用相同的偵測技術集合，在不同的電子郵件視圖中篩選結果， (惡意程式碼、網路釣魚程式、所有電子郵件) 。

> [!NOTE]
> 判定分析可能不一定要與實體關聯。 舉例來說，電子郵件可能會分類為網路釣魚或垃圾郵件，但沒有以網路釣魚/垃圾郵件判定的 URLs。 這是因為篩選器也會在指派判定之前，評估電子郵件的內容和其他詳細資料。

#### <a name="threats-in-urls"></a>URLs 中的威脅

您現在可以在 [電子郵件彈出 **詳細資料** ] 索引標籤上看到 URL 的特定威脅。威脅可能是 *惡意* 代碼、 *網路釣魚*、 *垃圾郵件* 或 *無*。 ) 

> [!div class="mx-imgBorder"]
> ![URL 威脅](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a> (即將開始的時程表視圖更新) 

> [!div class="mx-imgBorder"]
> ![更新時程表視圖](../../media/Email_Timeline.png)

時程表視圖會識別所有傳遞和傳遞投遞事件。 它包含針對這些事件子集在該時間點所識別之威脅的相關資訊。 時程表視圖也提供有關 (執行的任何其他動作（如 ZAP 或手動修正) ）的相關資訊，以及該動作的結果。 時程表視圖資訊包含：

- **來源：** 事件的來源。 可以是 admin/system/user。
- **事件：** 包含最上層的事件，例如原始傳遞、手動修復、ZAP、報送及動態傳遞。
- **動作：** 做為 ZAP 或 admin 動作一部分所採取的特定動作 (例如，soft delete) 。
- **威脅：** 涵蓋該時間點所識別的威脅 (惡意程式碼、網路釣魚和垃圾郵件) 。
- **結果/詳細資料：** 有關動作結果的詳細資訊，例如是否以 ZAP/系統管理動作的一部分執行。

### <a name="original-and-latest-delivery-location"></a>原始及最近的傳遞位置

目前，我們在電子郵件格線和電子郵件飛入位置中呈現的方式。 [**傳遞位置**] 欄位取得 [重新命名 **_原始傳遞位置_]*。我們正在引進另一個欄位，_*_最新的傳遞位置_**。

**原始傳遞位置** 將會提供有關電子郵件最初傳遞位置的詳細資訊。 **最新的傳遞位置** 會在系統動作（如 *ZAP* 或系統動作）之後的電子郵件進入，例如 *移至 [刪除的專案*]。 最新的傳遞位置是用來告訴系統管理員郵件的最後一個已知位置後置或任何系統/系統管理員動作。 它不會包含電子郵件上的任何使用者動作。 例如，如果使用者刪除郵件或將郵件移至封存/pst，則不會更新郵件的 [傳遞] 位置。 不過，如果系統動作更新了位置 (例如，ZAP 產生的電子郵件移至隔離) 中，則 **最新的傳遞位置** 會顯示為「隔離」。

> [!div class="mx-imgBorder"]
> ![更新的傳遞位置](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> 在某些情況下， **傳送位置** 和 **傳遞動作** 可能會顯示為「未知」：
>
> - 如果郵件已傳遞，您可能 **會看到 [** 已傳遞] 和 [送達] **位置** 為 "Unknown"，但是收件匣規則會將郵件移至預設資料夾 (例如草稿或封存) ，而不是 [收件匣] 或 [垃圾郵件] 資料夾。
>
> - 如果已嘗試使用系統管理員/系統動作 (（例如 ZAP) ），但找不到該郵件，則 **最新的傳遞位置** 可能是未知的。 通常動作會在使用者移動或刪除郵件之後發生。 在這種情況下，請在時程表視圖中驗證 [ **結果/詳細資料** ] 欄位。 尋找 [使用者已移動或刪除的郵件] 語句。

> [!div class="mx-imgBorder"]
> ![時程表的傳遞位置](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>其他動作

在傳送電子郵件之後套用 *其他動作*。 它們可以包含由系統管理員採取的 *ZAP*、 *手動修正* (動作（如虛刪除) 、 *動態傳遞*） *，以及重新處理 (（* 已偵測為良好) 的電子郵件）。

> [!NOTE]
> 在擱置中的變更中，目前出現在 [傳遞動作篩選] 中的「已移除的 ZAP」值將會不復存在。 您可以使用此方法，透過 **其他動作** 來搜尋所有 ZAP 嘗試的電子郵件。

> [!div class="mx-imgBorder"]
> ![瀏覽器中的其他動作](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>系統覆寫

*系統覆寫* 可讓您對郵件的預定送達位置產生例外狀況。 您可以根據威脅及篩選堆疊所識別的其他偵測，覆寫系統所提供的傳遞位置。 系統覆寫可透過租使用者或使用者原則加以設定，以依照原則所建議的方式傳遞郵件。 覆寫可識別因設定缺口而無意間傳遞的惡意郵件，例如使用者設定的過於廣泛的保管庫寄件者原則。 這些覆寫值可以是：

- 使用者原則允許：使用者在信箱層級建立原則，以允許網域或寄件者。

- 使用者原則封鎖：使用者會在信箱層級建立原則，以封鎖網域或寄件者。

- 組織原則所允許：組織的安全小組設定原則或 Exchange 郵件流程規則 (也稱為傳輸) 規則，可讓其組織中的使用者能夠使用寄件者和網域。 這可供一組使用者或整個組織使用。

- 由組織原則封鎖：組織的安全小組會設定原則或郵件流程規則，以封鎖組織中使用者的寄件者、網域、郵件語言或來源 Ip。 這可以套用到一組使用者或整個組織。

- 組織原則封鎖的檔案副檔名：組織的安全性小組會透過反惡意程式碼原則設定封鎖副檔名。 這些值現在會顯示在電子郵件詳細資料中，以協助調查。 Secops 小組也可以使用 rtf 篩選功能來篩選封鎖的副檔名。

[![瀏覽器中的系統覆寫](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![瀏覽器中的系統覆寫格線](../../media/System_Overrides_Grid.png)

### <a name="improvements-for-the-url-and-clicks-experience"></a>URL 及點擊體驗的增強功能

改進功能包括：

- 顯示已完全按一下的 URL (包括 url 任何部分之 URL 的任何查詢參數) 在 URL 快顯視窗的 [ **點擊** ] 區段中。 目前，URL 網域和路徑會出現在標題列中。 我們正在擴充該資訊以顯示完整的 URL。

- 跨 URL 篩選器的修正 (*url* 與 *url 網域* *，以及 url 網域和路徑*) ：更新會影響包含 URL/按一下判定之郵件的搜尋。 我們為通訊協定不可知的搜尋啟用支援，因此您可以在不使用的情況下搜尋 URL `http` 。 根據預設，URL 搜尋會對應至 HTTP，除非明確指定另一個值。 例如：
  - `http://`在 [ **url**]、[ **url 網域**] 及 [ **url 網域] 和 [路徑** 篩選] 欄位中，使用或不使用前置詞進行搜尋。 搜尋應該會顯示相同的結果。
  - `https://`在 **URL** 中搜尋前置詞。 若未指定任何值，則 `http://` 會假設首碼。
  - `/` 會在 **url 路徑**、 **url 網域**、 **URL 網域及路徑** 欄位的開頭和結尾略過。 `/` 在 [ **URL** ] 欄位的結尾會被忽略。

### <a name="phish-confidence-level"></a>網路釣魚信賴等級

網路釣魚信賴等級可協助識別將電子郵件分類為 "網路釣魚" 的置信度。 這兩個可能的值為 *High* 和 *Normal*。 在初始階段中，此篩選器只會在威脅瀏覽器的網路釣魚視圖中使用。

[![瀏覽器中的網路釣魚信賴等級](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>ZAP URL 信號

ZAP URL 信號通常用於 ZAP 網路釣魚警示案例，其中的電子郵件已識別為網路釣魚並在傳遞後移除。 此信號會在瀏覽器中使用對應的結果來連接警示。 這是警示的其中一個 IOCs。

為了改進搜尋程式，我們已更新威脅瀏覽器和即時偵測，使搜尋體驗更為一致。 這些變更如下所述：

- [時區改進](#timezone-improvements)
- [重新整理程式中的更新](#update-in-the-refresh-process)
- [新增至篩選的圖表深入分析](#chart-drilldown-to-add-to-filters)
- [在產品資訊更新](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>依使用者標記篩選

您現在可以排序和篩選系統或自訂使用者標記，以快速抓住威脅的範圍。 若要深入瞭解，請參閱 [使用者標記](user-tags.md)。

> [!IMPORTANT]
> 依使用者標記篩選和排序目前是公開預覽。 在正式發行之前，您可能會充分修改此功能。 Microsoft 對本所提供的資訊不提供任何明示或默示的保證。

> [!div class="mx-imgBorder"]
> ![瀏覽器中的標記欄](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>時區改進

您會看到入口網站中的電子郵件記錄以及匯出資料的時區。 透過電子郵件格線、[詳細資料] 飛出、電子郵件時程表及類似的電子郵件，它會在體驗上看到，所以結果集的時區也是清除的。

> [!div class="mx-imgBorder"]
> ![在瀏覽器中查看時區](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>重新整理程式中的更新

有些使用者對自動重新整理的混淆有批註 (例如，當您變更日期時，此頁面會立即重新整理) 和手動重新整理 (其他篩選) 。 同樣地，移除篩選器也會導致自動重新整理。 修改查詢時變更篩選可能會造成不一致的搜尋體驗。 若要解決這些問題，我們會移至手動篩選機制。

從經驗的觀點來看，使用者可以從 [篩選器集和日期) 中，套用及移除不同的篩選範圍 (，然後選取 [重新整理] 按鈕，以在定義查詢之後篩選結果。 [重新整理] 按鈕現在也會在螢幕上強調。 我們也更新相關的工具提示及產品內檔。

> [!div class="mx-imgBorder"]
> ![選取 [重新整理] 以篩選結果](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>新增至篩選的圖表深入分析

您現在可以圖表圖例值新增為篩選器。 選取 [重新整理 **] 按鈕以** 篩選結果。

> [!div class="mx-imgBorder"]
> ![深入查看圖表以進行篩選](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>產品內資訊更新

產品內現在已提供其他詳細資料，例如格線內的搜尋結果總數 (請參閱) 。 我們已改進標籤、錯誤訊息及工具提示，以提供有關篩選、搜尋經驗及結果集的詳細資訊。

> [!div class="mx-imgBorder"]
> ![View in 產品資訊](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>威脅瀏覽器中的延伸功能

### <a name="top-targeted-users"></a>主要目標使用者

如今，我們會在惡意程式碼的 [ **主要惡意程式碼系列** ] 區段中，公開電子郵件的惡意程式碼視圖中主要目標使用者的清單。 我們也會在網路釣魚和所有電子郵件視圖中擴充此視圖。 您將可以查看前5位目標使用者，以及每位使用者對對應視圖的嘗試次數。 例如，針對網路釣魚視圖，您會看到網路釣魚嘗試次數。

您可以將目標使用者的清單匯出至3000的限制，以及每個電子郵件 view 的離線分析嘗試次數。 此外，選取 [嘗試次數] (例如，13在下一個影像嘗試) 會在威脅瀏覽器中開啟篩選的視圖，這樣您就能看到該使用者的電子郵件和威脅的詳細資料。

> [!div class="mx-imgBorder"]
> ![主要目標使用者](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>傳輸規則 Exchange

在 [資料豐富] 的一部分中，您將可以查看套用至郵件的所有不同 Exchange 傳輸規則 (ETR) 。 此資訊將會出現在 [電子郵件格線] 視圖中。 若要進行查看，請選取格線中的 [**欄選項**]，然後從 [欄] 選項 **新增 Exchange 傳輸規則**。 它也會顯示在電子郵件中的 [ **詳細資料** ] 快顯視窗中。

您將能看到 GUID 及已套用至郵件的傳輸規則名稱。 您將能夠使用傳輸規則的名稱來搜尋郵件。 這是「包含」搜尋，也就是您也可以進行部分搜尋。

> [!IMPORTANT]
> ETR 搜尋和名稱可用性取決於指派給您的特定角色。 您必須具有下列其中一個角色/許可權，才能查看 ETR 名稱和搜尋。 如果您未指派任何這些角色，您就無法看到傳輸規則的名稱，或使用 ETR 名稱來搜尋郵件。 不過，您可以在電子郵件詳細資料中看到 ETR 標籤及 GUID 資訊。 其他記錄流覽的電子郵件格線、電子郵件 flyouts、篩選和匯出不會受到影響。
>
> - 僅限 EXO-資料遺失防護：全部
> - 僅限 EXO-O365SupportViewConfig： All
> - Microsoft Azure Active Directory 或 EXO-安全性系統管理員： All
> - AAD 或 EXO-Security Reader： All
> - 僅限 EXO-Transport Rules： All
> - 僅限 EXO-View-Only 設定： All
>
> 在電子郵件格線、詳細資料浮出和匯出的 CSV 中，ETRs 會以如下所示的名稱/GUID 呈現。
>
> > [!div class="mx-imgBorder"]
> > ![Exchange傳輸規則](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>輸入連接器

連接器是一組指示，可自訂您的電子郵件進出 Microsoft 365 或 Office 365 組織的方式。 它們可讓您套用任何安全性限制或控制項。 在威脅瀏覽器內，您現在可以查看與電子郵件相關的連接器，並使用連接器名稱搜尋電子郵件。

在 [自然] 中，連接器的搜尋是「包含」，這表示部分關鍵字搜尋也應該可以運作。 在主格線視圖中，[詳細資料] 飛入和匯出的 CSV，連接器會以如下所示的名稱/GUID 格式顯示：

> [!div class="mx-imgBorder"]
> ![連接器詳細資料](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>威脅瀏覽器和即時偵測中的新功能

- [查看傳送給類比使用者和網域的網路釣魚電子郵件](#view-phishing-emails-sent-to-impersonated-users-and-domains)
- [預覽電子郵件標頭和下載電子郵件內文](#preview-email-header-and-download-email-body)
- [電子郵件時間表](#email-timeline)
- [匯出 URL 點擊資料](#export-url-click-data)

### <a name="view-phishing-emails-sent-to-impersonated-users-and-domains"></a>查看傳送給類比使用者和網域的網路釣魚電子郵件

若要識別對類比使用者的使用者和網域的網頁網路嘗試，必須新增至 *要保護的使用者* 清單中。 對於網域，系統管理員必須啟用 *組織網域*，或將功能變數名稱新增至 *要保護的網域*。 您 *可以在模擬區段的*[*反網路釣魚原則] 頁面* 上找到要保護的網域。

若要查看網路釣魚郵件和搜尋模擬的使用者或網域，請使用瀏覽器的 [電子郵件 > 網路釣魚視圖](threat-explorer-views.md) 。

本範例會使用威脅瀏覽器。

1. 在 [ [安全性 & 規範中心](https://protection.office.com) ] (中 https://protection.office.com) ，選擇 [威脅管理] > Explorer (或即時偵測) 。

2. 在 [View] 功能表中，選擇 [電子郵件 > 網路釣魚。

   您可以在這裡選擇模擬的 **網域** 或 **模仿的使用者**。

3. **請選取 [** 模擬 **網域**]，然後在 textbox 中輸入受保護的網域。

   例如，搜尋受保護的功能變數名稱（如 *contoso*、 *contoso.com* 或 *contoso.com.au*）。

4. 在 [電子郵件] 索引標籤 > 詳細資料] 索引標籤下，選取任何郵件的主旨，以查看類比網域/偵測到的位置等其他類比

    **OR**

    選取 [模擬 **使用者** ]，然後在 textbox 中輸入受保護使用者的電子郵件地址。

    > [!TIP]
    > **為了獲得最佳結果**，請使用 *完整電子郵件地址* 來搜尋受保護的使用者。 當您搜尋 *firstname.lastname@contoso.com* 時（例如，調查使用者模擬時），您可以更快速且更順利地找到您的受保護的使用者。 搜尋受保護的網域時，搜尋會以根域 (contoso.com，例如) ，以及功能變數名稱 (*contoso*) 。 搜尋根網域 *contoso.com* 將同時傳回 *contoso.com* 和功能變數名稱 *contoso* 的 impersonations。

5. 在 [**電子郵件** 索引標籤詳細資料] 索引標籤中選取任何 **郵件的主旨**  >   ，以查看有關使用者或網域的其他模擬資訊和偵測 *到的位置*。

    :::image type="content" source="../../media/threat-ex-views-impersonated-user-image.png" alt-text="顯示偵測位置之受保護使用者的威脅瀏覽器詳細資料窗格，以及偵測到使用者) 的網路釣魚模擬 (所偵測到的威脅。":::

> [!NOTE]
> 在步驟3或5中，如果您選擇 [**偵測技術**]，並分別選取 [**類比網域**] 或 [模擬 **使用者**]，則使用者或網域的 [**電子郵件]** 索引標籤詳細資料] 索引標籤中的資訊，  >  只會顯示在 [*反網路釣魚原則***]** 頁面上所列之使用者或網域相關聯的訊息。 

### <a name="preview-email-header-and-download-email-body"></a>預覽電子郵件標頭和下載電子郵件內文

您現在可以預覽電子郵件頭，並下載威脅瀏覽器中的電子郵件內文。 系統管理員可以分析已下載的郵件頭/電子郵件，以取得威脅。 因為下載電子郵件可能會危及資訊的危險性，所以此程式是由以角色為基礎的存取控制 (RBAC) 所控制。 新的角色、 *預覽*，必須新增至其他角色群組 (例如安全作業或安全性系統管理員) ，以授與透過所有電子郵件消息查看下載郵件的能力。 不過，若要在威脅瀏覽器) 中查看郵件所需的 (以外，查看電子郵件標頭並不需要任何其他角色。

瀏覽器和即時偵測也會取得新的欄位，可提供您的電子郵件所在位置更完整的畫面。 這些變更可使搜尋更輕鬆進行安全性 Op。 不過，主要結果是您可以快速知道問題電子郵件訊息的位置。

這是如何達成？ 傳遞狀態現在會分解成兩個欄：

- **傳遞動作** -電子郵件的狀態。
- **傳遞位置** -傳送電子郵件的位置。

*傳遞動作* 是由於現有的原則或偵測，而對電子郵件採取的動作。 電子郵件可能的動作如下：

<br>

****

|已傳遞|已標示為垃圾郵件|已封鎖|已取代|
|---|---|---|---|
|電子郵件已傳遞至使用者的收件匣或資料夾，而且使用者可以存取。|電子郵件已傳送至使用者的 [垃圾郵件] 或 [已刪除] 資料夾，使用者可以存取它。|隔離、失敗或丟棄的電子郵件。 使用者無法存取這些郵件。|電子郵件具有惡意附件，其 .txt 的檔會以附件為惡意。|
|

以下是使用者可及無法看到的專案：

<br>

****

|使用者可以存取|使用者無法存取 |
|---|---|
|已傳遞|已封鎖|
|已標示為垃圾郵件|已取代|
|

**傳遞位置** 顯示執行後續傳遞的原則及偵測結果。 它會連結至 **_傳遞動作_**。 可能的值如下：

- *收件匣或資料夾*：電子郵件的收件匣或資料夾 (會根據您的電子郵件規則) 。
- *部署或外部*：信箱不存在於雲端上，但為內部部署。
- [垃圾郵件]*資料夾*：電子郵件位於使用者的 [垃圾郵件] 資料夾中。
- 「*刪除的郵件」資料夾*：在使用者的 [刪除的郵件] 資料夾中的電子郵件。
- *隔離*：電子郵件是隔離的，而不是在使用者的信箱中。
- *失敗*；電子郵件無法傳遞至信箱。
- *丟斷*：電子郵件在郵件流程中遺失。

### <a name="email-timeline"></a>電子郵件時間表

**電子郵件時程表** 是新的瀏覽器功能，可改善系統管理員的搜尋體驗。 它會削減檢查不同位置所花費的時間，以嘗試瞭解該事件。 當電子郵件到達時，發生多個事件或接近該郵件時，這些事件會顯示在時程表視圖中。 您的電子郵件投遞之後所發生的某些事件會在 [ **特殊動作** ] 欄中捕獲。 系統管理員可以合併時程表中的資訊，並在郵件投遞後採取特殊的動作，以深入瞭解其原則的運作方式（即最後一次路由傳送郵件的位置），而且在某些情況下，最後評估是什麼。

如需詳細資訊，請參閱[調查並修正 Office 365 中傳遞的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)。

### <a name="export-url-click-data"></a>匯出 URL 點擊資料

您現在可以將 url 按一下的報告匯出至 Microsoft Excel 以查看其 **網路消息識別碼**，並 **按一下 [判定**]，以協助說明您的 URL 按一下流量的來源。 其運作方式如下：在威脅管理的 Office 365 快速啟動列上，請遵循下列連結：

**瀏覽器** \>**查看網路釣魚** \>**按一下** \>**Top URLs** Or **URL 上擊** \> 選取 [任何記錄] 以開啟 [URL] 浮出控制項。

當您在清單中選取 URL 時，您會在飛出面板上看到新的 [ **匯出** ] 按鈕。 使用此按鈕將資料移至 Excel 試算表，以便更輕鬆地進行報告。

請遵循此路徑，以取得即時偵測報告中的相同位置：

**瀏覽器** \>**即時偵測** \>**查看網路釣魚** \>**URLs** \>**Top URLs** 或 **top 按一下** \> 選取 [任何記錄] 以開啟 [URL] 浮出 \> ] 流覽至 [**點擊**] 索引標籤。

> [!TIP]
> 當您使用瀏覽器或關聯的協力廠商工具來搜尋識別碼時，網路郵件識別碼會對應按一下 [回復至特定郵件]。 這類搜尋會識別與按一下結果關聯的電子郵件。 讓相關網路郵件識別碼能夠更快速且更強大的分析。

> [!div class="mx-imgBorder"]
> ![瀏覽器中的按一下 tab 鍵](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>查看透過技術在電子郵件中偵測到的惡意程式碼

假設您想要查看以 Microsoft 365 技術排序的電子郵件中偵測到惡意程式碼。 若要這麼做，請使用瀏覽器的 [電子郵件 > 惡意](threat-explorer-views.md#email--malware) 代碼視圖 (或即時偵測) 。

1. 在 [安全性 & 規範中心] (<https://protection.office.com>) 中，選擇 [ **威脅管理** \> **瀏覽器** (] 或 [ **即時** 偵測]) 。 (此範例使用總管。)

2. 在 [ **視圖** ] 功能表中，選擇 [ **電子郵件** \> **惡意** 代碼]。

   > [!div class="mx-imgBorder"]
   > ![總管的檢視功能表](../../media/ExplorerViewEmailMalwareMenu.png)

3. 按一下 [ **寄件者**]，然後選擇 [ **基本** \> **偵測技術**]。

   您的偵測技術現在可做為報告的篩選器。

   > [!div class="mx-imgBorder"]
   > ![惡意程式碼偵測技術](../../media/ExplorerEmailMalwareDetectionTech.png)

4. 選擇 [選項]。 然後選取 [重新整理] **按鈕，套用** 該篩選。

   > [!div class="mx-imgBorder"]
   > ![選取的偵測技術](../../media/ExplorerEmailMalwareDetectionTechATP.png)

報告會進行重新整理，以顯示惡意程式碼在電子郵件中偵測到的結果，並使用您選取的技術選項。 您可以從這裡進行進一步分析。

## <a name="view-phishing-url-and-click-verdict-data"></a>查看網路釣魚 URL，然後按一下 [已判定資料]

假設您想要查看透過電子郵件中的 URL 進行的網路釣魚攻擊，包括允許、封鎖及覆寫的 URL 清單。 若要識別所按一下的 URLs，必須設定[保管庫連結](safe-links.md)。 請務必設定[保管庫連結原則](set-up-safe-links-policies.md)，以在按保管庫連結的情況時，按一下 [保護] 和 [記錄]。

若要查看郵件中的網路釣魚 URLs，並按一下網路釣魚郵件中 URLs，請使用瀏覽器或即時偵測的 [**電子郵件**  >  **網路釣魚**](threat-explorer-views.md#email--phish)視圖。

1. 在 [安全性 & 規範中心] (<https://protection.office.com>) 中，選擇 [ **威脅管理** \> **瀏覽器** (] 或 [ **即時** 偵測]) 。 (此範例使用總管。)

2. 在 [ **視圖** ] 功能表中，選擇 [ **電子郵件** \> **釣魚網絡**]。

   > [!div class="mx-imgBorder"]
   > ![網路釣魚內容中瀏覽器的視圖功能表](../../media/ExplorerViewEmailPhishMenu.png)

3. 按一下 [ **寄件者**]，然後選擇 **URLs** \> **按一下 [判定**]。

4. 選取一個或多個選項（例如 **封鎖** 和 **封鎖**），然後在與套用該篩選的選項相同的列上選取 [重新整理 **] 按鈕。** (請勿重新整理瀏覽器視窗。)

   > [!div class="mx-imgBorder"]
   > ![URL 和按一下結果](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   報告會重新整理以在報告下的 [URL] 索引標籤上顯示兩個不同的 URL 表格：

   - **Top URLs** 是您篩選的郵件中 URLs，以及每個 URL 的電子郵件傳遞動作計數。 在網路釣魚電子郵件視圖中，此清單通常包含合法的 URLs。 攻擊者會在其郵件中混合使用良好和不良的 URLs，以嘗試傳遞，但它們會使惡意連結看起來更有趣。 URLs 的表格依總的電子郵件總數排序，但是此欄位是隱藏的，以簡化視圖。

   - **上** 指按一下的保管庫連結包裝 URLs，依總按一下計數排序。 此欄位也不會顯示，以簡化視圖。 依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。 在網路釣魚電子郵件視圖中，這些通常是可疑或惡意的 URLs。 不過，此視圖可以包含不是威脅的 URLs，但位於網路釣魚郵件中。 在這裡未顯示 URL 按一下已開啟的連結。

   這兩個 URL 表格會依照傳送動作和位置，顯示網路釣魚電子郵件中的最上層 URLs。 [！注意] 表格會顯示因警告而封鎖或訪問的 URL 按一下，因此您可以看到使用者的潛在不良連結，以及使用者已按一下的連結。 您可以從這裡進行進一步分析。 例如，在圖表下方，您可以在組織環境中所封鎖的電子郵件訊息中看到最上層 URLs。

   > [!div class="mx-imgBorder"]
   > ![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)

   選取 URL 以檢視更多詳細資訊。

   > [!NOTE]
   > 在 [URL 飛入] 對話方塊中，會移除電子郵件上的篩選，以顯示您環境中 URL 公開的完整視圖。 這可讓您在瀏覽器中篩選您關心的電子郵件訊息，找出潛在威脅的特定 URLs，然後透過 [URL 詳細資料] 對話方塊，展開您環境中的 URL 公開知識 () 而不必將 URL 篩選器新增至瀏覽器視圖本身。

### <a name="interpretation-of-click-verdicts"></a>按一下 verdicts 的轉譯

在電子郵件或 URL flyouts 中，按一下上方和篩選體驗內，您會看到不同的按一下判定值：

- **無：** 無法捕獲 URL 的判定。 使用者可能已按一下透過 URL。
- **允許：** 允許使用者流覽至 URL。
- **封鎖：** 已封鎖使用者流覽至 URL。
- **擱置的判定：** 使用者呈現在引爆擱置的頁面上。
- **封鎖已被取代：** 封鎖使用者直接流覽至 URL。 但使用者 overrode 區塊以流覽至 URL。
- **擱置的判定略過：** 使用者呈現的是 [引爆] 頁面。 但使用者 overrode 郵件以存取 URL。
- **錯誤：** 使用者呈現錯誤頁面，或捕獲判定結果時發生錯誤。
- **失敗：** 捕獲判定時，發生未知的例外狀況。 使用者可能已按一下透過 URL。

## <a name="review-email-messages-reported-by-users"></a>檢閱使用者回報的電子郵件訊息

假設您想要查看組織中的使用者已透過 [報告郵件增益集](enable-the-report-message-add-in.md)或 [報告網路釣魚增益集](enable-the-report-phish-add-in.md)舉報為 *垃圾* 郵件、*非垃圾* 郵件或 *網路釣魚* 的電子郵件訊息。 若要查看，請使用瀏覽器的 [**電子郵件**  >  **提交**](threat-explorer-views.md#email--submissions)視圖 (或即時偵測) 。

1. 在 [安全性 & 規範中心] (<https://protection.office.com>) 中，選擇 [ **威脅管理** \> **瀏覽器** (] 或 [ **即時** 偵測]) 。 (此範例使用總管。)

2. 在 [ **View** ] 功能表中，選擇 [ **電子郵件** \> **提交**]。

   > [!div class="mx-imgBorder"]
   > ![電子郵件瀏覽器的視圖功能表](../../media/explorer-view-menu-email-user-reported.png)

3. 按一下 [ **寄件者**]，然後選擇 [ **基本** \> **報表類型**]。

4. 選取選項，**例如 [** **網路釣魚**]，然後選取 [重新整理] 按鈕。

   > [!div class="mx-imgBorder"]
   > ![使用者回報的網路釣魚](../../media/EmailUserReportedReportType.png)

報告會重新整理以顯示組織中的人員報告為網路釣魚企圖的電子郵件相關資料。 您可以使用這項資訊進行進一步的分析，並在必要時，調整[Microsoft Defender 中 Office 365 的反網路釣魚原則](configure-mdo-anti-phishing-policies.md)。

## <a name="start-automated-investigation-and-response"></a>啟動自動調查及回應

> [!NOTE]
> Microsoft Defender 的「自動化調查和回應」功能可在 *Office 365 方案 2* 和 *Office 365 E5* 中取得。

[自動化調查和回應](automated-investigation-response-office.md) 可儲存您的安全性運作小組時間和精力，以調查及緩解 cyberattacks。 除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。 如需詳細資訊，請參閱 [範例：安全性管理員會從瀏覽器觸發調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>更多使用 Explorer 和即時偵測的方式

除了本文所述的案例之外，您還可以使用更多報表選項，以供 Explorer (或即時偵測) 。 請參閱下列文章：

- [尋找並調查傳送的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)
- [檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案](./mdo-for-spo-odb-and-teams.md)
- [取得威脅瀏覽器中的視圖 (和即時偵測的概覽) ](threat-explorer-views.md)
- [威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft 365 Defender 中的自動化調查和回應](../defender/m365d-autoir.md)

## <a name="required-licenses-and-permissions"></a>必要的授權和權限

您必須具有[Microsoft Defender Office 365](defender-for-office-365.md) ，才能使用 Explorer 或即時偵測。

- Explorer 會包含在 Office 365 方案2的 Defender 中。
- 在 Office 365 方案1的 Defender 中包含即時偵測報告。
- 規劃為所有應受 Office 365 Defender 保護的使用者指派授權。 瀏覽器和即時偵測顯示已授權使用者的偵測資料。

若要查看和使用 Explorer 或即時偵測，您必須具有適當的許可權，例如授與安全性管理員或安全性讀者的許可權。

- 針對安全性 & 合規性中心，您必須已指派下列角色之一：

  - 組織管理
  - 安全性管理員 (可以在 Azure Active Directory 系統管理中心 (中指派 <https://aad.portal.azure.com>) 
  - 安全性讀取者

- 針對 Exchange Online，您必須在 Exchange 系統管理中心中指派下列角色之一 (<https://admin.protection.outlook.com/ecp/>) 或[Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)：

  - 組織管理
  - 僅限檢視組織管理
  - 僅限檢視收件者
  - 合規性管理

若要深入了解角色和權限，請參閱下列資源：

- [Microsoft 365 Defender 入口網站中的權限](permissions-microsoft-365-security-center.md)
- [Exchange Online 中的功能權限](/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>威脅瀏覽器與即時偵測的差異

- 您可以在 Office 365 方案1的 Defender 中取得 *即時* 偵測報告。 您可以在 Office 365 方案2的 Defender 中取得 *威脅瀏覽器*。
- 即時偵測報告可讓您即時查看偵測。 威脅瀏覽器也會這麼做，但也會提供特定攻擊的其他詳細資料。
- *所有的電子郵件* view 都可用於威脅瀏覽器，但不會出現在即時偵測報告中。
- 威脅瀏覽器中包含更多篩選功能和可用的動作。 如需詳細資訊，請參閱[Microsoft defender for Office 365 Service Description：每個 defender 的功能可用性以取得 Office 365 計畫](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

## <a name="other-articles"></a>其他文章

[使用電子郵件實體頁面調查電子郵件](mdo-email-entity-page.md)
