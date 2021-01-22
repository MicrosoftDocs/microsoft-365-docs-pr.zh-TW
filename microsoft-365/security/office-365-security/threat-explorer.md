---
title: 威脅管和即時偵測
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
description: 使用安全性合規性中心的 Explorer 和即時偵測來調查 &amp; 並有效回應威脅。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: caf795b421ac8e1e6785abff2fc49f0e49c391ca
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931707"
---
# <a name="threat-explorer-and-real-time-detections"></a>威脅管和即時偵測

如果貴組織擁有 [Office 365](office-365-atp.md)的 Microsoft Defender，而且您擁有必要許可權，就有權存取 Explorer 或即時偵測功能，這些前稱是 *即時報告*。 [](#required-licenses-and-permissions)  (新功能。) [](#new-features-in-threat-explorer-and-real-time-detections)安全性&，請前往威脅管理，然後選取 Explorer 或 **即時偵測**。 

|使用 Microsoft Defender for Office 365 方案 2，您會看到：|使用適用于 Office 365 方案 1 的 Microsoft Defender，您會看到：|
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

Explorer 或即時偵測可協助您的安全性作業小組有效率地調查及回應威脅。 報告類似下列影像：

![移至威脅管理 \> 總管](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

您可以使用此報告：

- [查看 Microsoft 365 安全性功能偵測到的惡意攻擊](#see-malware-detected-in-email-by-technology)
- [查看網路釣魚 URL 並按一下 [網路釣魚資料](#view-phishing-url-and-click-verdict-data)
- [從適用于](#start-automated-investigation-and-response) Office 365 方案 2 的 Explorer (Defender 的一個) 
- [調查惡意電子郵件等](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a>改善威脅管和即時偵測

### <a name="tags-in-threat-explorer"></a>威脅管中的標記

> [!NOTE]
> 使用者標記功能為預覽 *版*，不適用於所有人，且可能會有所變更。 有關發行排程的資訊，請參閱 Microsoft 365 藍圖。

使用者標記可識別 Microsoft Defender for Office 365 中的特定使用者群組。 有關標記的資訊，包括授權和組組，請參閱使用者 [標記](user-tags.md)。

在威脅管中，您可以在下列體驗中查看使用者標記相關資訊。

#### <a name="email-grid-view"></a>電子郵件格線視圖

電子郵件 **網格** 線中的標記欄包含所有已適用于寄件者或收件者信箱的標記。 根據預設，優先顯示優先順序帳戶等系統標記。

> [!div class="mx-imgBorder"]
> ![在電子郵件格線視圖中篩選標記](../../media/tags-grid.png)

#### <a name="filtering"></a>篩選

您可以使用標記做為篩選。 只搜尋優先順序帳戶或特定使用者標記案例。 您也可以排除具有特定標記的結果。 將此功能與其他篩選結合以縮小您的調查範圍。

[![篩選標記](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![未篩選標記](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>電子郵件詳細資料飛出
若要查看寄件者和收件者的個別標記，請選取要開啟郵件詳細資料飛出區的主題。 如果寄件者 **和收** 件者有顯示電子郵件，則這些寄件者和收件者標記會分開顯示。
寄件者和收件者個別標記的資訊也會延伸至匯出的 CSV 資料，您可以在兩個個別的欄看到這些詳細資料。

> [!div class="mx-imgBorder"]
> ![電子郵件詳細資料標記](../../media/tags-flyout.png)

URL 按一下飛出區也會顯示標記資訊。 若要進行查看，請前往網路釣魚或所有電子郵件的視圖，然後前往 **URL** 或 URL 的 **按一下** 按鈕。選取個別的 URL 飛出，以查看該 URL 的按一下相關詳細資料，包括與該按一下相關的標記。

> [!div class="mx-imgBorder"]
> ![URL 標記](../../media/tags-urls.png)

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>在近期新推出的威脅搜尋體驗 (改善) 

### <a name="updated-threat-information-for-emails"></a>已更新電子郵件的威脅資訊

我們著重于改善平臺和資料品質，提高電子郵件記錄的資料正確性與一致性。 改進包括將傳遞前和傳遞後的資訊合併成單一記錄，例如，在電子郵件上執行的動作是 ZAP 程式一部分。 包含其他詳細資料，例如垃圾郵件垃圾郵件 (，例如哪些 URL 是惡意) ，以及最新的傳遞位置。

這些更新之後，無論影響郵件的不同傳遞後事件，您都會看到每封郵件的單一專案。 動作可能包括 ZAP、手動修復 (，這表示系統管理員) 行動、動態傳遞等等。

除了顯示惡意攻擊和網路釣魚威脅，您看到與電子郵件相關聯的垃圾郵件。 在電子郵件內，查看與電子郵件相關聯的所有威脅，以及對應的偵測技術。 電子郵件可能擁有零、一或多個威脅。 您將在電子郵件飛出區之詳細 **資料區** 段看到目前的威脅。 針對惡意 (網路釣魚) 等多種威脅，偵測技術欄位會顯示威脅偵測地圖，這是識別威脅的偵測技術。

這組偵測技術現在包含新的偵測方法，以及垃圾郵件偵測技術。 您可以使用同一組偵測技術，在不同的電子郵件視圖中篩選結果，例如惡意 (、網路釣魚、所有電子郵件) 。

> [!NOTE]
> 分析不一定與實體綁定。 例如，電子郵件可能分類為網路釣魚或垃圾郵件，但沒有標記網路釣魚/垃圾郵件垃圾郵件的 URL。 這是因為篩選也會先評估電子郵件的內容和其他詳細資料，然後再指派電子郵件的篩選準則。

#### <a name="threats-in-urls"></a>URL 中的威脅

現在，您可以在電子郵件飛出視窗的飛出詳細資料標籤上看到 URL **的特定** 威脅。威脅可能是惡意 *攻擊*、 *網路釣魚*、 *垃圾郵件*，或 *無*.) 

> [!div class="mx-imgBorder"]
> ![URL 威脅](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>已更新時程表 (近期) 

> [!div class="mx-imgBorder"]
> ![已更新的時程表視圖](../../media/Email_Timeline.png)

時程表視圖可識別所有傳遞和傳遞後的事件。 其中會包含此時所識別威脅的資訊，以用於這些事件的子集。 時程表視圖也會提供對所採取之任何額外動作的資訊 (例如 ZAP 或手動補救) ，以及該動作的結果。 時程表的視圖資訊包括：

- **來源：** 事件的來源。 它可以是系統管理員/系統/使用者。
- **活動：** 包括原始傳遞、手動修復、ZAP、提交和動態傳遞等頂層事件。
- **動作：** 做為 ZAP 或系統管理動作之一部分 (執行的特定動作，例如，) 。
- **威脅：** 涵蓋此時 (識別的惡意) 、網路釣魚、垃圾郵件等威脅。
- **結果/詳細資料：** 有關動作結果詳細資訊，例如該動作是否做為 ZAP/系統管理員動作的一部分執行。

### <a name="original-and-latest-delivery-location"></a>原始且最新的送貨位置

目前，我們已在電子郵件格線和電子郵件飛出區中顯示傳遞位置。 正在 **重新命名傳送** 位置欄位 **_原始的送貨位置_* _。 此外，我們引進了另一個欄位： _*_最新送貨位置_*_。

_ *原始的傳遞位置** 會提供有關電子郵件一開始遞送位置的更多資訊。 **最新的傳遞位置** 會指出電子郵件在像 *ZAP* 這樣的系統動作或系統管理動作後送達的位置，例如移至 *已刪除的專案*。 最新的傳遞位置旨在通知系統管理員郵件在傳遞後的最後已知位置或任何系統/系統管理員動作。 這不包含電子郵件上的任何使用者動作。 例如，如果使用者刪除郵件或將郵件移至 archive/pst，郵件的「傳遞」位置將不會更新。 但如果系統動作更新郵件的位置，例如，ZAP (電子郵件移往隔離區) ，最新傳遞位置會顯示為「隔離」。 

> [!div class="mx-imgBorder"]
> ![更新的送貨位置](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> 在某些情況下，傳遞位置和 **傳遞** 動作可能會顯示成「未知」： 
>
> - 如果郵件已送達，您可能會將傳遞位置視為「送達」和「未知」，但郵件已移至預設資料夾 (例如「草稿」或「封存」) ，而不是移至 「信箱」或「垃圾郵件」資料夾。
>
> - **如果系統管理員** /系統執行例如 ZAP (，) 傳送位置不明，但找不到訊息。 一般來說，動作會發生在使用者移動或刪除郵件之後。 在這種情況下，請驗證時程表 **視圖中的結果/** 詳細資料欄。 尋找「使用者移動或刪除訊息」的陳述。

> [!div class="mx-imgBorder"]
> ![時程表的傳遞位置](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>其他動作

*傳送電子郵件* 之後，已執行其他動作。 他們可以包括 *ZAP、* 手動修復 *(* 系統管理員採取的動作，例如，對經回溯偵測為良好電子郵件的) 、動態傳遞和 () 。

> [!NOTE]
> - 在擱置變更中，目前顯示于傳遞動作篩選中的 「由 ZAP 移除」值會消失。 在 ZAP 嘗試執行其他動作時，您將可以搜尋所有 **電子郵件**。
>
> - 偵測技術將會有新的欄位和值，以及其他動作 (尤其是 ZAP 案例和) 。 您必須評估現有的已儲存查詢和追蹤查詢，以確保它們能使用新的值。

> [!div class="mx-imgBorder"]

> ![在 Explorer 中執行其他動作](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>系統覆蓋

*系統替代* 功能可讓您將郵件的預定傳遞位置做為例外。 您根據篩選堆疊所識別的威脅與其他偵測，來取代系統提供的傳遞位置。 您可以透過租使用者或使用者政策設定系統覆蓋，以根據該政策的建議傳遞郵件。 因設定間有差異 ，例如使用者設定過於廣泛的安全寄件者政策，所以您能夠識別不小心傳送的惡意郵件。 這些替代值可以是：

- 使用者策略允許：使用者會以信箱層級建立策略，以允許網域或寄件者。
- 被使用者策略封鎖：使用者以郵件方塊層級建立策略來封鎖網域或寄件者。
- 組織原則允許：組織的安全性小組會設定原則或 Exchange 郵件流程規則 (也稱為傳輸規則) ，為組織中的使用者允許寄件者和網域。 這適用于一組使用者或整個組織。
- 被組織原則封鎖：組織的安全性小組會設定原則或郵件流程規則，以封鎖寄件者、網域、郵件語言或組織中使用者的來源 IP。 這可套用至一組使用者或整個組織。
- 組織政策封鎖的副檔名：組織的安全性小組會透過反惡意程式碼政策設定封鎖副檔名。 這些值現在會顯示在電子郵件詳細資料中，協助調查。 Secops 團隊也可使用豐富的篩選功能來篩選封鎖的副檔名。

[![在 Explorer 中的系統覆蓋](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![在 Explorer 中的系統覆蓋格線](../../media/System_Overrides_Grid.png)

### <a name="improvements-for-the-url-and-clicks-experience"></a>改善 URL 和點擊體驗

這些改良專案包括：

- 在 URL 飛出區段 (包含屬於 URL 連結一部分的任何查詢參數) 按一下的 URL連結。 目前，URL 網域和路徑會顯示在標題列中。 我們正在延伸該資訊以顯示完整的 URL。

- URL 篩選的修正 (*URL* 與 *URL* 網域 *、URL* 網域和路徑的修正) ：更新會影響搜尋包含 URL/click) 的郵件。 我們已啟用通訊協定診斷搜尋的支援，因此您可以搜尋 URL 而不使用 `http` 。 根據預設，除非明確指定其他值，否則 URL 搜尋會連結至 HTTP。 例如：

   -  搜尋 URL、URL 網域和 URL 網域和路徑篩選欄位中包含或 `http://` **不含** 首碼。   搜尋應該會顯示相同的結果。

   -  在 `https://` **URL** 中搜尋首碼。 未指定值時，會 `http://` 假設首碼。

   - `/` URL 路徑 **、URL** 網域 **、URL** 網域和 **路徑欄位的開頭和** 結尾將被忽略。 `/` URL 欄位的 **結尾** 會被忽略。

### <a name="phish-confidence-level"></a>網路釣魚信賴等級

網路釣魚信賴等級可協助識別將電子郵件分類為「網路釣魚」的信賴度。 這兩個可能的值為 *High 和* *Normal。* 在初始階段，只有威脅防護工具的網路釣魚視圖中才能使用此篩選器。

[![Explorer 中的網路釣魚信賴等級](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>ZAP URL 訊號

ZAP URL 訊號通常是用於 ZAP 網路釣魚警示案例，當電子郵件被識別為網路釣魚，且在傳遞後即移除。 這個訊號將警示與 Explorer 中的對應結果連接。 它是警示的其中一個 IOC。

為了改善尋找流程，我們已更新威脅搜尋和即時偵測，讓尋找體驗更加一致。 變更概述如下：

- [時區的改良功能](#timezone-improvements)
- [重新更新程式中的更新](#update-in-the-refresh-process)
- [要新進到篩選的圖表向下切入](#chart-drilldown-to-add-to-filters)
- [在產品資訊更新中](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>根據使用者標記篩選

現在，您可以排序及篩選系統或自訂使用者標記，以快速掌握威脅的範圍。 若要深入瞭解，請參閱使用者 [標記](user-tags.md)。

> [!IMPORTANT]
> 篩選及排序使用者標記目前處於公開預覽。 這項功能可能在正式發行前大幅修改。 Microsoft 對所提供的資訊，不提供明確或隱含的擔保。

![在 Explorer 中的標記欄](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>時區的改良功能

您將在入口網站中查看電子郵件記錄以及匯出資料的時區。 它會在電子郵件格線、詳細資料飛出視窗、電子郵件時程表和類似電子郵件等體驗中顯示，因此結果集的時區是明確的。

> [!div class="mx-imgBorder"]
> ![在 Explorer 中查看時區](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>重新更新程式中的更新

有些使用者針對自動重新 (工作造成混淆，例如，一旦變更日期，頁面就會重新) ，針對其他篩選或 (重新) 。 同樣地，移除篩選會導致自動重新組織。 在修改查詢時變更篩選可能會導致不一致的搜尋體驗。 為解決這些問題，我們正在移往手動篩選機制。

從體驗中，使用者可以從篩選集和日期 (套用並移除不同的篩選範圍) 並選取重新更新按鈕，以在定義查詢後篩選結果。 現在在螢幕上也會強調重新管理按鈕。 我們也更新了相關的工具提示和產品內檔。

> [!div class="mx-imgBorder"]
> ![選取重新更新以篩選結果](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>要新進到篩選的圖表向下切入

您現在可以使用圖表圖例值，將其新增為篩選。 選取重新 **更新** 按鈕以篩選結果。

> [!div class="mx-imgBorder"]
> ![向下切入圖表以篩選](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>產品內資訊更新

產品現在提供其他詳細資料，例如格線中的搜尋結果 (如下所示) 。 我們改善了標籤、錯誤訊息和工具提示，以提供篩選、搜尋體驗和結果集的詳細資訊。

> [!div class="mx-imgBorder"]
> ![查看產品內資訊](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>威脅管中的擴充功能

### <a name="top-targeted-users"></a>主要目標使用者

今天，我們已在電子郵件的惡意攻擊系列區段的惡意惡意攻擊視圖中公開最主要目標 **使用者** 的清單。 我們也會在網路釣魚和所有電子郵件的視圖中延伸此視圖。 您將可查看前五名的目標使用者，以及對應視圖每個使用者的嘗試次數。 例如，如果是網路釣魚視圖，則會看到網路釣魚嘗試次數。

您可以匯出目標使用者清單 ，最多 3，000 個，以及每個電子郵件視圖的離線分析嘗試次數。 此外，選取嘗試次數 (例如，在下方影像中嘗試 13 次) 就會在威脅管理器中開啟篩選的畫面，好讓您可以查看該使用者的電子郵件和威脅的更多詳細資料。

> [!div class="mx-imgBorder"]
> ![主要目標使用者](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Exchange 傳輸規則

在資料擴充作業中，您將能看到所有不同的 Exchange 傳輸規則 (ETR) 已適用于郵件。 此資訊將在電子郵件格線中提供。 若要進行查看，請選取網格 **線中的欄** 選項，然後從資料行選項新增 **Exchange** 傳輸規則。 它也會顯示在電子郵件 **的詳細資料** 飛出區上。

您將能看到 GUID 以及已適用于郵件的傳輸規則名稱。 您可以使用傳輸規則的名稱搜尋郵件。 這是「包含」搜尋，這表示您也可以執行部分搜尋。

#### <a name="important-note"></a>重要注意事項：

ETR 搜尋和名稱可用性取決於指派給您的特定角色。 您需要有下列其中一個角色/許可權才能查看 ETR 名稱和搜尋。 如果您沒有指派任何這些角色給您，則看不到傳輸規則的名稱，或是使用 ETR 名稱搜尋郵件。 不過，您可以在電子郵件詳細資料中查看 ETR 標籤和 GUID 資訊。 電子郵件格線、電子郵件飛出視窗、篩選和匯出中其他記錄檢視體驗則不受影響。

- 僅適用于 EXO - 資料外泄防護：全部
- 僅 EXO - O365SupportViewConfig：全部
- Microsoft Azure Active Directory 或 EXO - 安全性系統管理員：全部
- AAD 或 EXO - 安全性讀取程式：全部
- 僅適用于 EXO - 傳輸規則：全部
- 僅 EXO - View-Only組式：全部

在電子郵件方格、詳細資料飛出和匯出 CSV 內，ETRs 會以名稱/GUID 呈現，如下所示。

> [!div class="mx-imgBorder"]
> ![Exchange 傳輸規則](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>輸入連接器

連接器是一組指示集合，可自訂電子郵件往來于 Microsoft 365 或 Office 365 組織之間的流程。 它們可啟用任何安全性限制或控制項。 在威脅管中，您現在能查看與電子郵件相關的連接器，以及使用連接器名稱搜尋電子郵件。

連接器的搜尋在本質上是「包含」的，這表示部分關鍵字搜尋應該也一樣。 在主格線視圖、詳細資料飛出區以及匯出的 CSV 中，連接器會以名稱/GUID 格式顯示，如下所示：

> [!div class="mx-imgBorder"]
> ![連接器詳細資料](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>威脅管和即時偵測中的新功能

威脅管和即時偵測有三個新功能可用：

- [預覽電子郵件標頭和下載電子郵件內文](#preview-email-header-and-download-email-body)
- [電子郵件時間表](#email-timeline)
- [匯出 URL 點擊資料](#export-url-click-data)

新功能如下所列。

### <a name="preview-email-header-and-download-email-body"></a>預覽電子郵件標頭和下載電子郵件內文

現在，您可以預覽電子郵件標題，並下載威脅中心系統管理員的電子郵件內文，以分析下載的標題/電子郵件訊息以尋找威脅。 由於下載電子郵件訊息可能會風險曝光資訊，因此此程式是由角色型存取控制 (RBAC) 。 您必須將新角色預覽新增到另一個角色群組 (例如安全性作業或安全性系統管理員) ，才能在全電子郵件訊息視圖中下載郵件及預覽標題。

Explorer 和即時偵測也會取得新欄位，提供您電子郵件訊息位置的完整畫面。 這些變更讓尋找安全性活動變得更容易。 但主要結果還是您可以一目了然地知道問題電子郵件訊息的位置。

這是如何達成？ 傳遞狀態現在分成兩欄：

- **傳遞動作** - 電子郵件的狀態。
- **傳遞位置** - 電子郵件的路由位置。

*傳遞動作* 是因現有政策或偵測對電子郵件採取的動作。 以下是電子郵件的可能動作：

|已傳遞|已標示為垃圾郵件|已封鎖|已取代|
|---|---|---|---|
|電子郵件已傳送到使用者的信箱或資料夾，使用者可以存取。|電子郵件已送到使用者的垃圾郵件或已刪除資料夾，使用者可以存取。|受到隔離、失敗或已中斷的電子郵件。 使用者無法使用這些郵件。|電子郵件已由 .txt 檔案取代為惡意附件，而該檔案會指出附件為惡意。|

以下是使用者無法及無法看到哪些專案：

|使用者可以存取|使用者無法存取 |
|---|---|
|已傳遞|已封鎖|
|已標示為垃圾郵件|已取代|

**傳遞位置** 會顯示在傳遞後執行之策略和偵測的結果。 它連結至 **_傳遞動作_* _。 這些可能是值：

- _Inbox資料夾*：電子郵件會依據您的電子郵件規則或資料夾 (在郵件) 。
- *內部部署或外部*：信箱不存在於雲端，但位於內部部署。
- *垃圾郵件資料夾*：電子郵件位於使用者的垃圾郵件資料夾中。
- *刪除的郵件資料夾*：使用者的刪除專案資料夾中的電子郵件。
- *隔離*：電子郵件是在隔離中，而不是在使用者的信箱中。
- *失敗*；電子郵件無法傳遞至信箱。
- *已* 刪除：電子郵件在郵件流程的某處遺失。

### <a name="email-timeline"></a>電子郵件時間表

電子郵件 **時程表** 是新的 Explorer 功能，可改善系統管理員的搜尋體驗。 它會減少檢查不同位置以嘗試瞭解活動所花費的時間。 當多個事件在電子郵件送達的同一時間發生或接近時，這些事件會顯示在時程表視圖中。 傳送電子郵件後會發生一些事件，會記錄在特殊動作 **欄中** 。 系統管理員可以將時程表的資訊與郵件傳遞後採取的特殊動作結合，以深入瞭解其政策如何執行、郵件最後路由在哪裡，以及在某些情況下，最後評定的內容。

詳細資訊請參閱調查 [並修復 Office 365 中傳遞的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)。

### <a name="export-url-click-data"></a>匯出 URL 點擊資料

現在，您可以將 URL 點擊的報告匯出至 Microsoft Excel，以查看其網路訊息 **識別碼**，然後按一下位址，這有助於說明 URL 按一下流量的起始位置。 運作方式如下：在 Office 365 快速啟動工具列上的威脅管理中，遵循此鏈：

**Explorer** \>**查看網路釣魚** \>**按一下** \>**熱門 URL 或** **URL Top Clicks 會** 選取 \> 任何記錄以開啟 URL 飛出。

當您在清單中選取 URL 時，就會在飛出面板上看到新的匯出按鈕。 使用此按鈕將資料移至 Excel 試算表，以便更輕鬆地進行報告。

請遵循此路徑，在即時偵測報告中找到相同的位置：

**Explorer** \>**即時偵測** \>**查看網路釣魚** \>**URL** \>**熱門 URL** 或 **熱門滑鼠按鍵選取** \> 任何記錄以開啟 URL 飛出視窗 \> ，流覽至按一下 **按鈕。**

> [!TIP]
> 當您透過 Explorer 或相關聯的協力廠商工具搜尋識別碼時，網路訊息識別碼會將您按一下的內容重新連結至特定郵件。 這類搜尋會識別與按一下結果相關聯的電子郵件。 擁有相關的網路訊息識別碼，可更快速且更功能強大的分析。

> [!div class="mx-imgBorder"]
> ![在 Explorer 中按滑鼠按鍵](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>查看透過技術在電子郵件中偵測到的惡意程式碼

假設您想要在 Microsoft 365 技術排序的電子郵件中查看偵測到的惡意攻擊。 若要這麼做，請使用 Explorer [>](threat-explorer-views.md#email--malware) 的電子郵件和惡意 (或即時偵測) 。

1. 在安全性與合規性中心 (<https://protection.office.com>) 選擇 **[威脅管理]** \> **[總管]** (或 **[即時偵測]**)。 (此範例使用總管。)

2. 在視圖 **功能表中**，選擇電子郵件 \> **惡意攻擊**。

   > [!div class="mx-imgBorder"]
   > ![總管的檢視功能表](../../media/ExplorerViewEmailMalwareMenu.png)

3. 按一下 **[寄件者**，然後選擇基本 \> **偵測技術**。

   您的偵測技術現在可做為報告的篩選器。

   > [!div class="mx-imgBorder"]
   > ![惡意程式碼偵測技術](../../media/ExplorerEmailMalwareDetectionTech.png)

4. 選擇一個選項。 然後選取重新 **更新** 按鈕來申請該篩選。

   > [!div class="mx-imgBorder"]
   > ![選取的偵測技術](../../media/ExplorerEmailMalwareDetectionTechATP.png)

報告會重新顯示您選取的技術選項，顯示電子郵件中偵測到的惡意攻擊結果。 您可以從這裡進行進一步分析。

## <a name="view-phishing-url-and-click-verdict-data"></a>查看網路釣魚 URL 並按一下 [網路釣魚資料

假設您想要查看透過電子郵件中的 URL 進行的網路釣魚攻擊，包括允許、封鎖及覆寫的 URL 清單。 若要識別按一下的 URL， [必須](atp-safe-links.md) 安裝 [安全連結。 請務必針對安全連結 [的](set-up-atp-safe-links-policies.md) 按一下時間保護及記錄按一下的裝置設定安全連結政策。

若要檢閱郵件中的網路釣魚 URL，並按一下網路釣魚郵件中的 URL，請使用 [****  >  ****](threat-explorer-views.md#email--phish)Explorer 的電子郵件網路釣魚視圖或即時偵測。

1. 在安全性與合規性中心 (<https://protection.office.com>) 選擇 **[威脅管理]** \> **[總管]** (或 **[即時偵測]**)。 (此範例使用總管。)

2. 在視圖 **功能表中**，選擇電子郵件 \> **網路釣魚**。

   > [!div class="mx-imgBorder"]
   > ![網路釣魚內容中的 Explorer 的查看功能表](../../media/ExplorerViewEmailPhishMenu.png)

3. 按一下 **[寄件者**，然後選擇 **URL** \> **Click 寄件人**。

4. 選取一或多個選項 ，例如已封鎖和已封鎖，然後選取與要申請該篩選之選項位於同一行的重新更新按鈕。  (請勿重新整理瀏覽器視窗。)

   > [!div class="mx-imgBorder"]
   > ![URL 和按一下結果](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   報告會重新整理以在報告下的 [URL] 索引標籤上顯示兩個不同的 URL 表格：

   - **最上方 URL** 是篩選到郵件中的 URL，以及每個 URL 的電子郵件傳遞動作計數。 在網路釣魚電子郵件的視圖中，此清單通常包含合法的 URL。 攻擊者在郵件中混合了良好和錯誤的 URL 以嘗試傳遞，但會使惡意連結看起來更有趣。 URL 表格是按照電子郵件總數排序，但此欄為隱藏狀態以簡化顯示方式。

   - **熱門點擊** 數是已按過的安全連結換行 URL，按總點擊數排序。 系統不會顯示此欄，以簡化您的視圖。 依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。 在網路釣魚電子郵件的視圖中，這些通常是可疑或惡意的 URL。 但該視圖可能包含不是威脅，而是網路釣魚郵件中的 URL。 URL 按一下未顯示的連結不會顯示在這裡。

   這兩個 URL 表格會根據傳遞動作和位置，顯示網路釣魚電子郵件訊息中的熱門 URL。 表格顯示儘管警告仍封鎖或流覽的 URL 點擊次數，因此您可以查看使用者看到哪些潛在錯誤連結，以及使用者按一下了哪些連結。 您可以從這裡進行進一步分析。 例如，在圖表下方，您可以看見電子郵件訊息中，在貴組織環境中封鎖的熱門 URL。

   > [!div class="mx-imgBorder"]
   > ![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)

   選取 URL 以檢視更多詳細資訊。

   > [!NOTE]
   > 在 URL 彈出對話方塊中，電子郵件訊息的篩選會移除，以顯示您環境中 URL 曝光的完整視圖。 這可讓您在 [Explorer> 中篩選您關心的電子郵件訊息、尋找潛在威脅的特定 URL，然後透過 URL 詳細資料對話方塊 (擴展您對於您環境中 URL 公開的理解程度) 而不需要將 URL 篩選新到 [Explorer 視圖本身。

### <a name="interpretation-of-click-verdicts"></a>滑鼠按鍵的解譯

在電子郵件或 URL 飛出區、[按前點擊數時， 以及在我們的篩選體驗中，您看到不同的按一下結果值：

- **無：** 無法捕捉 URL 的當做資訊。 使用者可能已經按一下 URL。
- **已允許：** 已允許使用者流覽至 URL。
- **已封鎖：** 使用者已封鎖，因此沒有流覽到 URL。
- **擱置中：** 使用者被呈現在擱置中頁面。
- **已封鎖：** 使用者已被封鎖，因此不能直接流覽到 URL。 但使用者超過封鎖，流覽至 URL。
- **擱置中已跳過：** 使用者隨即被呈現在查看頁面。 但使用者過度控制訊息以存取 URL。
- **錯誤：** 使用者收到錯誤頁面，或是在拍攝結果時發生錯誤。
- **失敗：** 捕捉事件時，發生未知的例外。 使用者可能已經按一下 URL。

## <a name="review-email-messages-reported-by-users"></a>檢閱使用者回報的電子郵件訊息

假設您想查看貴組織使用者透過報告郵件附加元件或報告網路釣魚附加元件，被系統報告為垃圾郵件、非垃圾郵件[](enable-the-report-message-add-in.md)或網路釣魚[的電子郵件訊息](enable-the-report-phish-add-in.md)。 若要查看它們，請使用 Explorer [ ****  >  **的**](threat-explorer-views.md#email--submissions)電子郵件提交 (或即時偵測) 。

1. 在安全性與合規性中心 (<https://protection.office.com>) 選擇 **[威脅管理]** \> **[總管]** (或 **[即時偵測]**)。 (此範例使用總管。)

2. 在視圖 **功能表中****，選擇電子郵件** \> **提交**。

   > [!div class="mx-imgBorder"]
   > ![電子郵件的 Explorer 的查看功能表](../../media/explorer-view-menu-email-user-reported.png)

3. 按一下 **[寄件者**，然後選擇基本 \> **報表類型**。

4. 選取某個選項 ，例如 **網路釣魚，** 然後選取重新 **組織按鈕** 。

   > [!div class="mx-imgBorder"]
   > ![使用者回報的網路釣魚](../../media/EmailUserReportedReportType.png)

報表會重新顯示貴組織中人員報告為網路釣魚之電子郵件訊息的資料類型。 您可以使用此資訊進行進一步分析，並視需要調整 Microsoft Defender [for Office 365](configure-atp-anti-phishing-policies.md)中的防網路釣魚政策。

## <a name="start-automated-investigation-and-response"></a>啟動自動調查及回應

> [!NOTE]
> Microsoft Defender for *Office 365 方案 2* 和 Office *365 E5* 提供自動化調查與回應功能。

[自動化調查與回應](automated-investigation-response-office.md) 可節省安全性作業小組花費在調查與減少網路攻擊上的時間與精力。 除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。 詳情請參閱 [範例：安全性系統管理員會觸發](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)來自 Explorer 進行調查。

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>更多使用 Explorer 和即時偵測的方式

除了本文所述的案例之外，您還可以使用更多適用于 Explorer 的報告選項 (或即時偵測) 。 請參閱下列文章：

- [尋找並調查傳送的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)
- [檢視在 SharePoint Online、OneDrive 和 Microsoft Teams 中偵測到的惡意檔案](malicious-files-detected-in-spo-odb-or-teams.md)
- [概觀威脅總管中的 (和即時偵測) ](threat-explorer-views.md)
- [威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft 威脅防護的自動化調查及回應](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>必要的授權和權限

您必須擁有 [適用于 Office 365](office-365-atp.md) 的 Microsoft Defender，以使用 Explorer 或即時偵測。

- 總管包含在 Office 365 方案 2 的 Defender 中。
- 即時偵測報告包含在 Office 365 方案 1 的 Defender 中。
- 規劃指派授權給應該受 Office 365 Defender 保護的所有使用者。 Explorer 和即時偵測會顯示授權使用者的偵測資料。

若要查看及使用 Explorer 或即時偵測，您必須擁有適當的許可權，例如授予安全性系統管理員或安全性讀取者的許可權。

- 針對安全性&規範中心，您必須有指派下列其中一個角色：

  - 組織管理
  - 安全性系統管理員 (可以在 Azure Active Directory 系統管理中心 <https://aad.portal.azure.com> () 
  - 安全性讀取者

- 對於 Exchange Online，您必須在 Exchange 系統管理中心或 Exchange Online PowerShell 中指派下列其中一 <https://admin.protection.outlook.com/ecp/> () 角色： [](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)

  - 組織管理
  - 僅限檢視組織管理
  - 僅限檢視收件者
  - 合規性管理

若要深入了解角色和權限，請參閱下列資源：

- [安全性與合規性中心的權限](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>威脅管理與即時偵測之間的差異

- 即時 *偵測報告可在* Office 365 方案 1 的 Defender 中提供。 *威脅總* 管位於 Office 365 方案 2 的 Defender 中。
- 即時偵測報告可讓您即時查看偵測。 威脅管也會執行這項功能，但也提供特定攻擊的額外詳細資料。
- 在 *威脅管* 中提供所有電子郵件的查看，但即時偵測報告則沒有提供。
- 威脅管中包含更多篩選功能和可用的動作。 詳細資訊請參閱 Office [365 服務描述的 Microsoft Defender：Office 365 方案之 Defender 的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。
