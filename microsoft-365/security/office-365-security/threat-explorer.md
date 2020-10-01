---
title: 威脅總管和即時偵測
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 瞭解如何在安全性與合規性中心使用 Explorer 和即時偵測， &amp; 以有效且有效地調查威脅並加以回應。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32ff9f2c8d009b4c9b05c12ba4e785e59cb182e7
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328080"
---
# <a name="threat-explorer-and-real-time-detections"></a>威脅總管和即時偵測

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


如果貴組織具有 [Office 365 進階威脅防護](office-365-atp.md) (Office 365 ATP)，而且您具有[必要的權限](#required-licenses-and-permissions)，您具有**總管**或**即時偵測** (先前的*即時報告* — [查看新增功能](#new-features-in-threat-explorer-and-real-time-detections)！)。 在 [安全性 & 規範中心] 中，移至 [ **威脅管理**]，然後選擇 [ **Explorer** ] _或_[ **即時**偵測]。

|在 ATP 方案 2，您會看到：|在 ATP 方案 1，您會看到：|
|---|---|
|![威脅總管](../../media/threatmgmt-explorer.png)|![即時偵測](../../media/threatmgmt-realtimedetections.png)|
|

總管 (或即時偵測) 提供您強大的報告，讓您的安全性作業小組以有效的方式調查及回應威脅。 報告類似下列影像：

![移至威脅管理 \> 總管](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

您可以使用此報告：

- [查看 Microsoft 365 的安全性功能偵測到的惡意程式碼](#see-malware-detected-in-email-by-technology)
- [檢視網路釣魚 URL 並按一下結果](#view-data-about-phishing-urls-and-click-verdict)
- [從總管中的檢視啟動自動化的調查和回應程序](#start-automated-investigation-and-response) (僅限 ATP 方案 2)
- ... [調查惡意電子郵件等功能](#more-ways-to-use-explorer-or-real-time-detections)！

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a>豐富威脅瀏覽器和即時偵測的增強功能

在改進搜尋程式的過程中，我們對威脅瀏覽器和即時偵測進行一些更新。 這些是「經驗」的改善，其重點是讓搜尋體驗更為一致。 這些變更如下所示：

- [時區改進](#timezone-improvements)
- [重新整理程式中的更新](#update-in-the-refresh-process)
- [新增至篩選的圖表深入分析](#chart-drilldown-to-add-to-filters)
- [在產品資訊更新](#in-product-information-updates)

### <a name="timezone-improvements"></a>時區改進

我們會顯示入口網站中的電子郵件記錄以及匯出資料的時區。 您可以透過電子郵件格線、詳細資料行中的電子郵件時程表及類似的電子郵件，在體驗上看到時區，這樣就不會為使用者提供明確的結果集時區。

![在瀏覽器中查看時區](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>重新整理程式中的更新

我們已聽說過與自動重新整理有關之混淆的回饋 (例如，當您變更日期時，此頁面會重新整理) 和手動重新整理 (其他篩選) 。 同樣地，移除篩選器會導致自動重新整理，這會導致在修改查詢時變更不同篩選的情況可能會造成不一致的搜尋體驗。 若要解決此情況，我們會移至手動篩選機制。
從經驗的觀點來看，使用者可以從 filter set 和 date) 套用及移除不同的篩選範圍 (，然後按下 [重新整理] 按鈕，以在完成定義查詢之後篩選結果。 重新整理按鈕也已更新，可在螢幕上清晰地呼叫。 我們也針對這項變更，更新工具提示及產品中的檔。

![按一下 [重新整理] 以篩選結果](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>新增至篩選的圖表深入分析

您現在可以按一下圖表圖例值，將該值新增為篩選。 請注意，您仍然需要按一下 [重新整理] 按鈕，以在上述變更中篩選結果。

![透過圖表深入篩選](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>在產品資訊更新

您也應該會看到產品中的其他詳細資料。 例如，在 [格線] 中的搜尋結果總數 (請參閱下列) ，以及標籤、錯誤訊息及工具提示等方面的增強功能，以提供有關篩選、搜尋經驗及結果集的詳細資訊。

![View In 產品資訊](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>威脅瀏覽器中的延伸功能

### <a name="top-targeted-users"></a>主要目標使用者

如今，我們會在惡意程式碼系列 (內的主要惡意程式碼) 區段中，公開主要目標使用者的清單。 我們也會在網路釣魚和所有電子郵件視圖中擴充此視圖，您可以在其中看到前五個目標使用者，以及每位使用者對對應 (view 的嘗試次數。例如，針對 [網路釣魚視圖]，您將能夠看到) 的網路釣魚嘗試次數。
您也可以將目標使用者的清單匯出為3000的限制，以及每個電子郵件 view 的離線分析嘗試次數。 除此之外，選取 [否]。 嘗試 (例如，下列 13) 會在威脅瀏覽器中開啟篩選的視圖，這樣您就可以深入瞭解該使用者的電子郵件和威脅。

![主要目標使用者](../../media/Top_Targeted_Users.png)


### <a name="exchange-transport-rules"></a>Exchange 傳輸規則
在資料豐富中，您也應該可以查看已套用至郵件的所有不同傳輸規則。 此資訊將會出現在 [電子郵件格線] 視圖中 (以進行查看，請選取 [格線] 中的 [欄選項]，然後在 [格線] 的 [欄] 選項中新增 Exchange Transport Rule) 以及電子郵件中的詳細資訊。
您可以同時看到 GUID，以及已套用至郵件的傳輸規則名稱。 此外，您也可以使用傳輸規則的名稱來搜尋郵件。 這會是「包含」搜尋，這表示您也可以使用部分搜尋進行搜尋。

#### <a name="important-note"></a>重要注意事項：
ETR 搜尋和名稱可用性取決於指派給您的特定角色。 您必須具有下列其中一個角色/許可權，才能查看 ETR 名稱和搜尋。  如果您未指派任何下列角色，您將無法看到傳輸規則的名稱，並使用 ETR 名稱來搜尋郵件。。 不過，您將可以在電子郵件詳細資料中看到 ETR 標籤及 GUID 資訊。 在電子郵件網格、電子郵件 flyouts、篩選和匯出等中查看記錄的其他體驗不會受到影響。

- 僅限 EXO-資料遺失防護：全部
- 僅限 EXO-O365SupportViewConfig： All
- AAD 或 EXO-安全性系統管理員： All
- AAD 或 EXO-Security Reader： All
- 僅限 EXO-Transport Rules： All
- 僅限 EXO-View-Only 設定： All

在電子郵件格線、詳細資料浮出和匯出的 CSV 中，ETRs 會以如下所示的名稱/GUID 呈現。

![Exchange 傳輸規則](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>輸入連接器

連接器是一組指示，可自訂您的電子郵件流向和來源於您的 Microsoft 365 或 Office 365 組織的方式，以及套用任何安全性限制或控制措施的功能。 在威脅瀏覽器內，您現在可以查看與電子郵件相關的連接器，也能使用連接器名稱搜尋電子郵件。
連接器的搜尋是「包含」，其性質表示部分關鍵字搜尋應該也會運作。
在主格線視圖中，[詳細資料] 飛入和匯出的 CSV，連接器會以如下所示的名稱/GUID 格式顯示：

![連接器詳細資料](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>威脅總管和即時偵測的新功能

威脅總管和即時偵測新增了三個新功能：

- [預覽電子郵件標頭和下載電子郵件內文](#preview-email-header-and-download-email-body)
- [電子郵件時間表](#email-timeline)
- [匯出 URL 點擊資料](#export-url-click-data)

新功能如下所列。

### <a name="preview-email-header-and-download-email-body"></a>預覽電子郵件標頭和下載電子郵件內文

預覽電子郵件標頭和下載電子郵件內文能力為威脅總管提供的新功能。 系統管理員將能分析下載的標頭/電子郵件訊息是否存在威脅。 由於下載電子郵件訊息可能有資訊暴露的風險，此程序是由角色型存取控制 (RBAC) 來控制。 新的角色， *預覽*必須新增至另一個角色群組 (例如安全作業或安全性系統管理員) ，授與可在 [所有電子郵件] 視圖中下載郵件和預覽標頭的能力。

但總管 (和即時偵測) 也會新增新欄位，設計用於提供您更完整的電子郵件訊息目標位置資訊。 這項變更的部分目標是讓安全性作業人員更容易搜捕，但最後的結果在於對問題電子郵件訊息的位置一目了然。

這是如何達成？ 傳遞狀態現在劃分為兩個資料行：

- **傳遞動作** - 這封電子郵件的狀態為何？
- **傳遞位置** - 結果這封電子郵件是如何路由傳送？

「傳遞動作」是基於現有原則或偵測對電子郵件所採取的動作。 以下是電子郵件可能採取的動作：

|已傳遞|已標示為垃圾郵件|已封鎖|已取代|
|---|---|---|---|
|電子郵件已傳送至使用者的收件匣或資料夾，而且使用者可以直接存取。|電子郵件會傳送至使用者的垃圾郵件資料夾或已刪除的資料夾，而且使用者可以存取這些資料夾中的電子郵件。|任何隔離、失敗或丟棄的電子郵件。 這完全無法由使用者存取！|任何電子郵件，惡意附件會以表示附件惡意的 .txt 檔取代。|

|已傳遞|已標示為垃圾郵件|已封鎖|已取代|
|---|---|---|---|
|電子郵件已傳遞至使用者的收件匣或其他資料夾，使用者可以直接存取。|電子郵件會傳送至使用者的垃圾郵件資料夾或已刪除的資料夾，而且使用者可以存取這些資料夾中的電子郵件。|任何已隔離、傳遞失敗或已捨棄的電子郵件，使用者均無法存取。|以 .txt 檔案替換為惡意附件的任何電子郵件訊息，均指出附件是惡意的。|
|

以下是使用者可以查看及無法查看的內容：

|使用者可以存取|使用者無法存取 |
|---|---|
|已傳遞|已封鎖|
|已標示為垃圾郵件|已取代|

傳遞位置顯示原則和執行傳遞後偵測的結果。 其連結到「傳遞動作」。 已新增此欄位，以深入了解找到問題電子郵件時所採取的動作。 以下是傳遞位置可能的值：

- **收件匣或資料夾**：電子郵件位於收件匣或資料夾中 (根據您的電子郵件規則)。
- **部署或外部**：信箱不存在於雲端上，但為內部部署。
- **垃圾郵件資料夾**：電子郵件位於使用者的 [垃圾郵件] 資料夾中。
- **刪除的郵件資料夾**：電子郵件位於使用者的 [刪除的郵件] 資料夾中。
- **隔離**：隔離中的電子郵件，而不是使用者信箱中的電子郵件。
- **失敗**；電子郵件無法傳遞至信箱。
- **已捨棄**：電子郵件在郵件流程的某處遺失。

### <a name="email-timeline"></a>電子郵件時間表

**電子郵件時間表**是總管的另一個新功能，目標是提升系統管理員的搜捕體驗。 這可減少不規則性，因為花較少的時間檢查不同位置以嘗試了解事件。 當多個事件同時或接近同時發生在某電子郵件時，這些事件會出現在時刻表檢視。 事實上，某些在傳遞郵件後發生的事件會由「特殊動作」欄擷取。 透過結合該郵件在時間表的資訊和傳遞郵件後採取的特殊動作，能讓系統管理員深入了解其原則的運作方式、郵件最後路由傳送的位置，以及在某些情況下最終評估的內容。

如需有關調查惡意電子郵件訊息的詳細討論，請參閱 [調查並修復 Office 365 中傳遞的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)。

### <a name="export-url-click-data"></a>匯出 URL 點擊資料

此外，您現在可以將 URL 點選的報告匯出到 Microsoft Excel 中，以便檢視其 [網路郵件識別碼] 以及 [按一下結果]，從而更容易了解 URL 點擊流量的來源。 以下說明運作方式。 在 Office 365 的威脅管理快速啟動中開啟，按一下此鏈結：

**瀏覽器** \>**查看網路釣魚** \>**按一下** \>Top **URLs 或 URL 上擊** \>**按一下任一筆記錄開啟 URL 彈出**視窗

當您按一下清單中的 URL 時，將會在飛出面版上看到新的 [匯出] 按鈕。 使用此按鈕將資料移至 Excel 試算表，以便更輕鬆地進行報告。

您可以在即時偵測報告中取得相同的位置，如下所示：

**瀏覽器** \>**即時偵測** \>**查看網路釣魚** \>**URLs** \>**上 URLs 或上按一下** \>**按一下任一筆記錄開啟 URL 彈出** \> 視窗**流覽至 [點擊]** 索引標籤。

> [!TIP]
> 當您透過網路郵件識別碼在總管或關聯的協力廠商工具中進行搜尋時，網路郵件識別碼會將點擊返回對應到特定的郵件。 搜尋網路郵件識別碼時，系統會提供系統管理員與點擊結果相關聯的特定電子郵件。 匯出時，網路郵件識別碼的關聯識別可提供更快且更強大的分析。

![瀏覽器中的按一下 tab 鍵](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>查看透過技術在電子郵件中偵測到的惡意程式碼

假設您想要查看 Microsoft 365 技術在電子郵件中偵測到惡意程式碼。 若要這麼做，請使用總管 (或即時偵測) 的 [[電子郵件] > [惡意程式碼]](threat-explorer-views.md#email--malware) 檢視。

1. 在安全性與合規性中心 ([https://protection.office.com](https://protection.office.com)) 選擇 **[威脅管理]** > **[總管]** (或 **[即時偵測]**)。 (此範例使用總管。)

2. 在 **[檢視]** 功能表中，選擇 **[電子郵件]** > **[惡意程式碼 ]**。

   ![總管的檢視功能表](../../media/ExplorerViewEmailMalwareMenu.png)

3. 按一下 **[寄件者]**，然後選擇 **[基本]** > **[偵測技術]**。

   您的偵測技術現在可做為報告的篩選器。

   ![惡意程式碼偵測技術](../../media/ExplorerEmailMalwareDetectionTech.png)

4. 選取一個選項，然後按一下 **[重新整理]** 按鈕來套用該篩選器。

   ![選取的偵測技術](../../media/ExplorerEmailMalwareDetectionTechATP.png)

報告會使用您所選取的技術選項重新整理，以顯示在電子郵件中偵測到的惡意程式碼。 您可以從這裡進行進一步分析。

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>檢視網路釣魚 URL 並按一下結果

假設您想要查看透過電子郵件中的 URL 進行的網路釣魚攻擊，包括允許、封鎖及覆寫的 URL 清單。 識別所按一下的 URLs 需要設定 [安全連結](atp-safe-links.md) 。 確定您已設定 [安全連結原則](set-up-atp-safe-links-policies.md) ，以供按一下時的保護和記錄按一下 [安全連結] 的 [verdicts]。

若要檢閱郵件中的網路釣魚 URL 和網路釣魚郵件中的 URL 點擊，請使用總管 (或即時偵測) 的 [[電子郵件] > [網路釣魚]](threat-explorer-views.md#email--phish) 檢視。

1. 在安全性與合規性中心 ([https://protection.office.com](https://protection.office.com)) 選擇 **[威脅管理]** > **[總管]** (或 **[即時偵測]**)。 (此範例使用總管。)

2. 在 **[檢視]** 功能表中，選擇 **[電子郵件]** > **[網路釣魚]**。

   ![總管的檢視功能表](../../media/ExplorerViewEmailPhishMenu.png)

3. 按一下 **[寄件者]**，然後選擇 **[URL]** > **按一下結果**。

4. 選取一或多個選項，例如 **[已封鎖]** 和 **[封鎖覆寫]**，然後按一下要套用該篩選器的選項同一行上的 **[重新整理]** 按鈕。 (請勿重新整理瀏覽器視窗。)

   ![URL 和按一下結果](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    報告會重新整理以在報告下的 [URL] 索引標籤上顯示兩個不同的 URL 表格：

   - **[熱門 URL]** 為已篩選的郵件中的 URL，而電子郵件傳送動作會計算每個 URL。 在網路釣魚電子郵件檢視中，此清單通常會包含合法的 URL。 攻擊者會在這些郵件中混雜善意和惡意的 URL，以試圖傳遞這些郵件，但他們會讓惡意連結看起來更加有趣，以誘使使用者點擊。 URLs 的表格依電子郵件總數 (排序，但是請注意，此欄位是隱藏的，可簡化 view) 。

   - **[熱門點擊]** 為點擊過的包含在安全連結中的 URL，並依總點擊數排序 (為了簡化檢視，此欄也不會顯示)。 依資料行的總計數表示每個點擊過的 URL 的安全連結按一下結果計數。 在網路釣魚電子郵件視圖中，這些都很經常是可疑或惡意的 URLs，但可能包含不具威脅但位於網路釣魚郵件中的 URLs。 已開啟的連結 URL 點擊不會顯示在這裡。

   兩個 URL 表格依傳遞動作和位置顯示網路釣魚電子郵件訊息熱門 URL，並顯示已封鎖的 URL 點擊 (或儘管已警告卻仍造訪的 URL)，讓您了解使用者接收到及互動的潛在惡意連結。 您可以從這裡進行進一步分析。 例如，在圖表的下方，您可以查看貴組織環境中封鎖的電子郵件訊息熱門 URL。

   ![已封鎖的總管 URL](../../media/ExplorerPhishClickVerdictURLs.png)

   選取 URL 以檢視更多詳細資訊。

   > [!NOTE]
   > 在 [URL 飛入] 對話方塊中，會移除電子郵件上的篩選，以顯示您環境中 URL 公開的完整視圖。 這能讓您在總管中篩選出擔心的電子郵件訊息，找出具有潛在威脅的特定 URL，然後了解暴露於環境 (經由 URL 詳細資料對話方塊) 中的 URL，而不需要將 URL 篩選新增至總管檢視本身。

### <a name="interpretation-of-different-click-verdicts"></a>不同按一下 verdicts 的轉譯

在電子郵件或 URL flyouts 中，按一下上方和篩選體驗內，您會在搜尋體驗的一部分看到不同的按一下值。 以下是按一下 Verdicts 及其轉譯的可能值：

- **無**：我們無法捕獲 URL 的判定。 使用者可能已按一下透過 URL。
- **允許**：允許使用者流覽至 URL。
- 已**封鎖**：已封鎖使用者流覽至 URL。
- **擱置的判定**：使用者已呈現「引爆擱置」頁面。
- **封鎖已封鎖**：已封鎖使用者流覽至 URL;不過，使用者 overrode 區塊以流覽至 URL。
- **擱置的判定略過**：使用者呈現的是引爆頁面;不過，使用者 overrode 頁面以流覽至 URL。
- **錯誤**：使用者已呈現錯誤頁面。 這也可能表示在捕獲判定時發生錯誤。
- **失敗**：捕獲判定時，發生未知的例外狀況。 使用者可能已按一下透過 URL。

## <a name="review-email-messages-reported-by-users"></a>檢閱使用者回報的電子郵件訊息

假設您想透過使用 [Outlook 和 Outlook 網頁版的回報郵件增益集](enable-the-report-message-add-in.md)來查看貴組織使用者回報為「垃圾郵件」、「非垃圾郵件」或「網路釣魚」的電子郵件。 若要這麼做，請使用總管 (或即時偵測) 的 [[電子郵件] > [提交]](threat-explorer-views.md#email--submissions) 檢視。

1. 在安全性與合規性中心 ([https://protection.office.com](https://protection.office.com)) 選擇 **[威脅管理]** > **[總管]** (或 **[即時偵測]**)。 (此範例使用總管。)

2. 在 **[檢視]** 功能表中，選擇 **[電子郵件]** > **[提交]**。

   ![總管的檢視功能表](../../media/explorer-view-menu-email-user-reported.png)

3. 按一下 **[寄件者]**，然後選擇 **[基本]** > **[回報類型]**。

4. 選取一個選項，例如 **[網路釣魚]**，然後按一下 **[重新整理]** 按鈕。

   ![使用者回報的網路釣魚](../../media/EmailUserReportedReportType.png)

報告會重新整理，顯示貴組織中的人員回報為網路釣魚攻擊的電子郵件相關資料。 您可以使用此資訊來進行進一步分析，並視需要調整 [ATP 防網路釣魚原則](configure-atp-anti-phishing-policies.md)。

## <a name="start-automated-investigation-and-response"></a>啟動自動調查及回應

> [!NOTE]
> **Office 365 ATP 方案 2** 和 **Office 365 E5** 提供自動化調查及回應功能。

(新增！) [自動化調查及回應](automated-investigation-response-office.md)能為您的安全性作業小組節省許多時間和精力來調查及降低網路攻擊。 除了設定會觸發安全性劇本的警示，您可以在總管中的檢視啟動自動化調查及回應程序。

如需這方面的詳細資訊，請參閱[範例：安全性系統管理員從總管觸發調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>更多使用總管 (或即時偵測) 的方法

除了這篇文章所述的案例，總管 (或即時偵測) 還有更多回報選項。

- [尋找並調查傳送的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)
- [威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)
- [取得威脅總管 (和即時偵測) 檢視的概觀](threat-explorer-views.md)
- [Microsoft 威脅防護的自動化調查及回應](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>必要的授權和權限

您必須具備 [Office 365 ATP](office-365-atp.md) 才能取得總管或即時偵測。

- 總管會包含在 Office 365 ATP 方案 2。
- 即時偵測報告會包含在 Office 365 ATP 方案 1。
- 請計劃指派授權給所有應受 Office 365 ATP 保護的使用者。 (總管或即時偵測會為經過授權的使用者顯示偵測資料。)

若要檢視及使用總管或即時偵測，您必須具有適當的權限，例如授與安全性系統管理員或安全性讀取者的權限。

- 針對「安全性與合規性中心」，您必須受指派下列其中一個角色：

  - 組織管理
  - 安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))
  - 安全性讀取者

- 針對 Exchange Online，您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) 受指派下列其中一個角色：

  - 組織管理
  - 僅檢視組織管理
  - 僅檢視收件者角色
  - 合規性管理

若要深入了解角色和權限，請參閱下列資源：

- [安全性與 &amp; 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>威脅瀏覽器與即時偵測的某些差異

- Office 365 ATP 方案 1 提供**即時偵測**報告，而 Office 365 ATP 方案 2 提供**威脅總管**。
- **即時偵測**報告可讓您即時檢視偵測。 **威脅總管**也有這個功能，但也能讓您檢視特定攻擊的其他詳細資料。
- **所有的電子郵件**view 均可在**威脅瀏覽器**中 (，而不會在**即時**偵測報告) 中。
- **威脅瀏覽器**中包含更多篩選功能和可用的動作。

如需詳細資訊，請參閱 [Office 365 ATP 服務說明：各高級威脅防護的功能可用性 (ATP) 方案](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。
