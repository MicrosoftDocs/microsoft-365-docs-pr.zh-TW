---
title: Office 365 的效能疑難排解規劃
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 5/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c
ms.collection:
- M365-security-compliance
- Ent_O365
description: 本文可協助您疑難排解 Office 365 效能問題，甚至修正一些最常見的問題。
ms.openlocfilehash: 588a19e86d903a7ab709a7f0d0131da6e2a77f47
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928233"
---
# <a name="performance-troubleshooting-plan-for-office-365"></a>Office 365 的效能疑難排解規劃

您需要知道採取哪些步驟來識別及修正 SharePoint 線上、商務用 Skype、Exchange Online 或商務用 Skype Online 及用戶端電腦之間的效能、懸掛及緩慢效能 OneDrive？ 在致電支援之前，本文可協助您疑難排解 Office 365 效能問題，甚至修正一些最常見的問題。

本文實際上是一個範例行動計畫，您可以用來在發生問題時，捕獲有關效能問題的重要資料。 本文也包含一些最主要的問題。

如果您是網路效能的新功能，而且想要制定長期計畫，以監視用戶端電腦與 Office 365 之間的效能，請參閱 [Office 365 效能調整和疑難排解-系統管理員和 IT 專業人員](performance-tuning-using-baselines-and-history.md)。

## <a name="sample-performance-troubleshooting-action-plan"></a>效能疑難排解的範例行動方案

此項行動計畫包含兩個部分;準備階段和記錄階段。 如果您現在有效能問題，而且需要進行資料收集，您可以立即開始使用此計畫。

### <a name="prepare-the-client-computer"></a>準備用戶端電腦

- 尋找可能再現效能問題的用戶端電腦。 在疑難排解過程中，會使用此電腦。
- 記下來引發效能問題的步驟，讓您在測試時做好準備。
- 安裝用來收集及錄製資訊的工具：
  - 安裝 [Netmon 3.4](https://www.microsoft.com/download/details.aspx?id=4865) (或使用對等網路追蹤工具) 。
  - 安裝 [HTTPWatch](https://www.httpwatch.com/download/) 的免費基本版本 (或使用對等網路追蹤工具) 。
  - 使用螢幕錄製器或執行步驟記錄器 (PSR.exe Windows Vista 和更新版本隨附的) ，以便記錄測試期間所採取的步驟。

### <a name="log-the-performance-issue"></a>記錄效能問題

- 關閉所有多餘的網際網路瀏覽器。
- 啟動步驟記錄器或另一個螢幕錄製器。
- 啟動 Netmon 捕獲 (或網路追蹤工具) 。
- 在用戶端電腦上輸入 ipconfig/flushdns.，從命令列清除您的 DNS 快取
- 啟動新的瀏覽器會話，並開啟 HTTPWatch。
- 選用：如果您要測試 Exchange Online，請從 Office 365 管理主控台執行 Exchange Client Performance Analyzer 工具。
- 重現導致效能問題的確切步驟。
- 停止 Netmon 或其他工具的追蹤。
- 在命令列中輸入下列命令，然後按 ENTER，以執行 Office 365 訂閱的追蹤路由：

  ``` cmd
  tracert <subscriptionname>.onmicrosoft.com
  ```

- 停止步驟錄製器並儲存影片。 務必要包含捕獲的日期和時間，以及它是正確或不良的效能。
- 儲存追蹤檔案。 同樣地，一定要包含捕獲的日期和時間，以及它是正確或不良的效能。

如果您不熟悉如何執行本文所述的工具，請不要擔心，因為我們會在下一步提供這些步驟。 如果您習慣執行這種網路捕獲，您可以略過 [收集基準](performance-tuning-using-baselines-and-history.md#how-to-collect-baselines)，以說明篩選和讀取記錄檔。

### <a name="flush-the-dns-cache-first"></a>先清除 DNS 快取

為什麼？ 透過使用全新的石板來開始測試，將會啟動您的測試。 清除快取後，您會將 DNS 解析程式內容重設為最新的專案。 請記住，清除不會移除主機檔專案。 如果您大量使用主機檔專案，則應該將這些專案複製到另一個目錄中的檔案，然後清空主機檔。

#### <a name="flush-your-dns-resolver-cache"></a>清除您的 DNS 解析程式快取

1. 開啟命令提示字元， (**Start** \> **Run** \> **cmd** 或 **Windows key** \> **cmd**) 。
2. 輸入下列命令，然後按 ENTER：

    ``` cmd
    ipconfig /flushdns
    ```

## <a name="netmon"></a>監視器

Microsoft 的網路監控工具 ([Netmon](https://www.microsoft.com/download/details.aspx?id=4865)) 會分析網路上的電腦之間傳送的封包（即流量）。 透過使用 Netmon 來追蹤使用 Office 365 的流量，您可以捕獲、查看和讀取封包標頭、識別介入的裝置、檢查網路硬體上的重要設定、尋找丟棄的封包，以及遵循公司網路與 Office 365 電腦之間的流量流程。 由於流量的實際主體是加密的，也就是說，它 (透過 SSL/TLS 在埠443上傳輸，所以您無法讀取正在傳送的檔案。 相反地，您會取得封包所採取之路徑的未篩選追蹤，以協助您追蹤問題行為。

現在請確定您沒有套用篩選器。 請改為執行步驟並示範問題，再停止追蹤和儲存。

安裝 Netmon 3.4 之後，請開啟工具並執行下列步驟：

### <a name="take-a-netmon-trace-and-reproduce-the-issue"></a>進行 Netmon 追蹤並重現問題

1. 啟動 Netmon 3.4。
**「開始」** 頁面上有三個窗格：「**最近的捕獲**」、「**網路**」和「 **Microsoft 網路監視器3.4 快速入門」。請注意**。 [選取網路] 面板也會提供您可以捕獲的預設網路清單。 請確定這裡已選取網卡。

2. 在 [**開始**] 頁面的頂端，按一下 [**新增捕獲**]。 這會在 [ **開始** 頁面] 索引標籤（稱為 **Capture 1**）旁新增一個索引標籤。
![Netmon 的使用者介面，並反白顯示 [新增捕獲]、[啟動] 和 [停止] 按鈕。](../media/d4527d84-62ec-4301-82d5-e0166ff71f20.PNG)

3. 若要採取簡易捕獲，請按一下工具列上的 [ **啟動** ]。

4. 再現呈現效能問題的步驟。

5. 按一下 [**停止** 檔案 \>  \> **另存** 新檔]。 請記得為日期和時間提供時區，並提及其是否有不良或良好的效能。

## <a name="httpwatch"></a>HTTPWatch

[HTTPWatch](https://www.httpwatch.com/download/) 會收費，也就是免費的 edition。 免費 Basic Edition 涵蓋此測試所需的一切。 HTTPWatch 會從瀏覽器視窗直接監視網路流量和頁面載入時間。 HTTPWatch 是以圖形方式描述效能的 Internet Explorer 外掛程式。 分析可以儲存並在 HTTPWatch Studio 中查看。

> [!NOTE]
> 如果您使用另一個瀏覽器（例如 Firefox、Google Chrome），或是您無法在 Internet Explorer 中安裝 HTTPWatch，請開啟新的瀏覽器視窗，然後按鍵盤上的 F12 鍵。 您應該會看到位於瀏覽器底部的開發人員工具快顯功能表。 如果您使用 Opera，請按 CTRL + SHIFT + I 做為 Web Inspector，然後按一下 [ **網路** ] 索引標籤，完成下列所述的測試。 此資訊會稍有不同，但是載入時間仍會以毫秒為單位顯示。 > HTTPWatch 也對 SharePoint 線上頁面載入時間的問題非常有用。

### <a name="run-httpwatch-and-reproduce-the-issue"></a>執行 HTTPWatch 並重現問題

HTTPWatch 為瀏覽器外掛程式，所以在瀏覽器中公開工具，每個版本的 Internet Explorer 會稍有不同。 一般來說，您可以在 Internet Explorer 瀏覽器的命令列下找到 HTTPWatch。 如果您在瀏覽器視窗中看不到 HTTPWatch 外掛程式， **請按一下 [** 說明] \> ，或在 internet explorer 的較新版本中檢查您的瀏覽器 **版本，** 按一下齒輪符號及 [ **關於 internet explorer**]。 若要啟動 **命令** 行，請在 Internet Explorer 中的功能表列上按一下滑鼠右鍵，然後按一下 [ **命令列**]。

過去，HTTPWatch 已與命令和瀏覽器列產生關聯，請在安裝之後，如果您在重新開機) 檢查 **工具**，以及圖示的工具列上，您未立即看到圖示 (。 請記住，可以自訂工具列，也可以新增選項。

![顯示 HTTPWatch 圖示的 Internet Explorer 命令工具列。](../media/198590b0-d7b1-4bff-a6ad-e4ec3a1e83df.png)

1. 在 Internet Explorer 瀏覽器視窗中啟動 HTTPWatch。 它會顯示在該視窗底部的瀏覽器上。 按一下 [ **記錄**]。

2. 重現效能問題中的確切步驟。 在 HTTPWatch 中按一下 [ **停止** ] 按鈕。

3. **儲存** HTTPWatch 或透過 **電子郵件傳送**。 請記得命名該檔案，使其包含日期及時間資訊，以及您的觀賞是否包含良好或不良效能的示範。

![HTTPWatch，顯示 Office 365 首頁的頁面載入之 [網路] 索引標籤。](../media/021a2c64-d581-49fd-adf4-4c364f589d75.PNG)

這個螢幕擷取畫面來自 HTTPWatch 的專業版。 您可以在具有專業版本的電腦上，開啟基本版本中所進行的追蹤，並閱讀該電腦上的追蹤。 透過該方法，可在追蹤中取得額外資訊。

## <a name="problem-steps-recorder"></a>問題步驟記錄器

步驟記錄器或 PSR.exe 可讓您記錄發生的問題。 這是非常實用的工具，而且非常易於執行。

### <a name="run-problem-steps-recorder-psrexe-to-record-your-work"></a>執行問題步驟錄影機 (PSR.exe) 錄製您的工作

1. 使用 **開始** \> **執行** \> 類型 **PSR.exe** \> **確定**，或按一下 **Windows 鍵** \> 類型 **PSR.exe** \> 然後按 ENTER 鍵。

2. 當 [小型 PSR.exe] 視窗出現時，請按一下 [ **開始記錄** ] 並重現再現效能問題的步驟。 您可以視需要新增批註（按一下 [ **新增批註**]）。

3. 完成步驟後，按一下 [ **停止錄製** ]。 如果效能問題是頁面轉譯，請等到頁面轉譯後，再停止錄製。

4. 按一下 **[儲存]**。

![步驟記錄器或 PSR.exe 的螢幕擷取畫面。](../media/8542b0aa-a3ff-4718-8dc4-43f5521c6c34.PNG)

會為您記錄日期和時間。 這會將您的 PSR 連結到 Netmon 追蹤和 HTTPWatch 時間，並協助精確度疑難排解。 PSR 記錄中的日期和時間會顯示一分鐘，可在 URL 的登入與流覽及管理網站的部分轉譯（例如）之間傳遞。

## <a name="read-your-traces"></a>閱讀追蹤

您無法講授網路和效能疑難排解的所有事項，因為有人必須透過文章瞭解。 取得良好效能的經驗，以及您的網路運作方式及一般執行方式的知識。 不過，您可以將首要問題的清單加以舍入，並示範工具如何更輕鬆地消除最常見的問題。

如果您想要為您的 Office 365 網站挑選技能讀取網路追蹤，就不會有更好的教師定期建立頁面載入追蹤，並取得閱讀經驗。 例如，當您有機會時，請載入 Office 365 服務並追蹤處理常式。 篩選追蹤的 DNS 流量，或在 FrameData 中搜尋您所流覽之服務的名稱。 掃描追蹤以瞭解服務載入時所發生的步驟。 這將協助您瞭解一般的頁面負載應類似的情況，而且在疑難排解的情況下，尤其是在效能中，比較好的追蹤不良追蹤可能會非常教您。

Netmon 會在顯示篩選欄位中使用 Microsoft Intellisense。 Intellisense 或智慧程式碼完成，是指您在期間內輸入的秘訣和所有可用選項會顯示在下拉式選取範圍中。 例如，如果您擔心 TCP 視窗縮放，您可以尋找篩選 (例如  `.protocol.tcp.window < 100` 此方式) 。

![Netmon 的螢幕擷取畫面，顯示 [顯示篩選] 欄位使用 intellisense。](../media/75a56c11-9a60-47ee-a100-aabdfb1ba10f.PNG)

Netmon 追蹤可能會有許多流量。 如果您沒有閱讀過的經驗，您可能會在第一次開啟追蹤時淹沒。 您要做的第一件事是在追蹤時，將背景雜音的信號分開。 您可以對照 Office 365 進行測試，這就是您想要看到的流量。 如果您使用流覽追蹤，您可能不需要此清單。

您的用戶端和 Office 365 之間的流量透過 TLS 進行，這表示流量的主體會加密，而且在一般 Netmon 追蹤中不可讀取。 您的性能分析不需要知道資料包中的資訊細節。 不過，它非常關心封包標頭及其所包含的資訊。

### <a name="tips-to-get-a-good-trace"></a>取得好追蹤的秘訣

- 知道用戶端電腦 IPv4 或 IPv6 位址的值。 您可以在命令提示字元中輸入 **IPConfig** ，然後按 enter 鍵來取得。 知道此位址可讓您快速瞭解追蹤中的流量是否直接包含用戶端電腦。 如果有已知 proxy，請 ping 它，並同時取得其 IP 位址。

- 請清除您的 DNS 解析程式快取，並在可能的情況下，關閉所有執行測試的瀏覽器以外的瀏覽器。 例如，如果支援使用某些瀏覽器型工具來查看用戶端電腦的桌面，請先準備好篩選追蹤。

- 在 [繁忙追蹤] 中，找出您所使用的 Office 365 服務。 如果您以前從未或很少看到您的流量，這是將效能問題與其他網路噪音分開的有用步驟。 有幾種方式可以做到這一點。 在測試之前，您可以對特定服務 (的 URL 使用 _ping_ 或 _PsPing_ `ping outlook.office365.com` `psping -4 microsoft-my.sharepoint.com:443` ，例如) 。 您也可以在 Netmon 追蹤 (中輕鬆找到該 ping 或 PsPing，其進程名稱) 。 這將提供您開始查看的位置。

如果發生問題時，您只是使用 Netmon 追蹤，也沒關係。 若要自行確定方向，請使用類似或的篩選 `ContainsBin(FrameData, ASCII, "office")` `ContainsBin(FrameData, ASCII, "outlook")` 。 您可以從追蹤檔案錄製您的框架編號。 您也可以將 [ _框架摘要_ ] 窗格向右移動，並尋找 [交談識別碼] 欄。 您也可以在此顯示特定交談的識別碼，以日後進行記錄和查看。 請記得先移除此篩選器，再套用其他任何篩選。

> [!TIP]
> Netmon 具有許多有用的內建篩選。 嘗試 [_顯示_ 篩選] 窗格頂端的 [**負載篩選**] 按鈕。

![在用戶端電腦上的命令列中使用 PSPing，尋找您的 IP。](../media/4c43ac67-e28e-4536-842d-7add7aa28847.PNG)

![來自用戶端的 Netmon 追蹤會透過篩選 TCP 顯示相同的 PSPing 命令。旗標。 Syn = = 1。](../media/0ae7ef7d-e003-4d01-a006-dc49bd1fcef2.PNG)

熟悉您的流量，並瞭解如何找到您需要的資訊。 例如，瞭解如何使用 (例如 "Outlook" ) ，判斷追蹤中的哪個封包具有您所使用的 Office 365 服務的第一個參考。

採用 Office 365 Outlook Online 範例，流量的開始如下：

- 具有相符 QueryIDs 之 outlook.office365.com 的 DNS 標準查詢和 DNS 回應。 請務必記下此轉彎的時間偏移量，以及 Office 365 全域 DNS 會傳送名稱解析要求的位置。 最理想的方式是從本機，而不是世界的一半。

- 其狀態報表已永久移動的 HTTP GET 要求 (301) 

- RWS 流量包括 RWS Connect requests 和 Connect 回復。  (此為您建立連線的遠端 Winsock。 ) 

- TCP SYN 和 TCP SYN/ACK 交談。 此對話中的許多設定會影響您的效能。

- 然後是一系列的 TLS： tls 握手和 TLS 憑證交談所在的 tls 流量。  (記得資料是透過 SSL/TLS 加密。 ) 

流量的所有部分都很重要且已連接，但是部分追蹤的小部分包含有關效能疑難排解的資訊，因此我們將重點放在這些區域。 另外，由於我們已完成 Microsoft 的 Office 365 效能疑難排解，所以若要編譯前10個常見問題清單，我們將著重討論這些問題，以及如何使用我們所需的工具，讓您在下一個位置找到。

如果尚未安裝所有的現有工具，請使用下列矩陣進行數項工具。 盡可能。 在安裝點中提供連結。 此清單包含常見網路追蹤工具（例如 [Netmon](https://www.microsoft.com/download/details.aspx?id=4865) 和 [Wireshark](https://www.wireshark.org/)），但使用您熟悉的任何追蹤工具，而且您習慣于篩選網路流量。 當您進行測試時，請記得：

- *關閉您的瀏覽器，並僅在執行一個瀏覽器的情況下進行測試*  -這會降低所捕獲的整體流量。 它會進行較少的繁忙追蹤。
- *在用戶端電腦上清除您的 DNS 解析程式*  快取-這可在您開始進行捕獲時，提供全新的蓋板，以供清除追蹤。

## <a name="common-issues"></a>常見問題

您可能面臨的一些常見問題，以及如何在網路追蹤中尋找這些問題。

### <a name="tcp-windows-scaling"></a>TCP 視窗擴充

在 SYN-SYN/ACK 中找到。 傳統或計齡硬體可能不會利用 TCP windows 擴充功能。  若沒有適當的 TCP 視窗擴充設定，TCP 標頭中的預設16位緩衝區會填滿毫秒。  流量無法繼續傳送，直到用戶端收到已接收到原始資料的確認，從而導致延遲。

#### <a name="tools"></a>工具

- 監視器
- Wireshark

#### <a name="what-to-look-for"></a>要尋找的專案

在網路追蹤中尋找 SYN-SYN/ACK 流量。  在 Netmon 中，使用類似的篩選器  `tcp.flags.syn == 1` 。 在 Wireshark 中此篩選器是相同的。

![篩選 Netmon 或 Wireshark 中的兩個工具： TCP 的 Syn 封包。旗標。 Syn = = 1。](../media/4b9a12a1-c915-43c8-ac2f-a679d0435a29.PNG)

請注意，每個 SYN 都有一個來源埠 (SrcPort) 編號會在目的地埠 (DstPort) （如相關的認可 (SYN/ACK) ）。

若要查看網路連線所使用的 Windows 縮放值，請先展開 SYN，然後再展開相關的 SYN/ACK。

![顯示如何在追蹤中將 SrcPort 與 DstPort 相符的圖形，以取得時間差。](../media/6a4ca573-0253-4fbd-93e8-92821ee1c351.png)

### <a name="tcp-idle-time-settings"></a>TCP 閒置時間設定

在過去，大部分周邊網路都是針對暫時性的連線進行設定，這表示一般會終止閒置連線。 閒置的 TCP 會話可由 proxy 和防火牆終止超過100到300秒。 這對 Outlook Online 是有問題的，因為它會建立及使用長期連線，不論是否閒置。

當 proxy 或防火牆裝置終止連線時，系統不會通知用戶端，而且嘗試使用 Outlook Online 會表示用戶端電腦會嘗試重複，以 revive 連線，然後再進行新的連接。 頁面載入時，您可能會看到產品中的懸掛、提示或降低效能。

#### <a name="tools"></a>工具

- 監視器
- Wireshark

#### <a name="what-to-look-for"></a>要尋找的專案

在 Netmon 中，查看往返行程的 [時間偏移] 欄位。 來回行程是用戶端將要求傳送至伺服器及接收回應的時間。 檢查用戶端與出局點之間 (ex。 用戶端-- \> Proxy) ，或用戶端至 office 365 (client-- \> office 365) 。 您可以在多種類型的封包中看到這種情況。

舉例來說，Netmon 中的篩選器看起來可能像是 Wireshark 中的篩選器  `.Protocol.IPv4.Address == 10.102.14.112 AND .Protocol.IPv4.Address == 10.201.114.12`  `ip.addr == 10.102.14.112 &amp;&amp; ip.addr == 10.201.114.12` 。

> [!TIP]
> 不知道追蹤中的 IP 位址是否屬於您的 DNS 伺服器？ 請嘗試在命令列上查看。 按一下 [ **開始** \> **執行**]， \> 輸入 **cmd**，或按 **Windows 鍵** \> 並輸入 **cmd**。 在提示字元下輸入  `nslookup <the IP address from the network trace>` 。 若要測試，對您自己的電腦 IP 位址使用 nslookup。 > 若要查看 Microsoft 的 IP 範圍清單，請參閱 [Office 365 URLs 和 IP 位址範圍](./urls-and-ip-address-ranges.md)。

如果發生問題，預期會出現長時間偏移，在此情況下 (Outlook Online) ，尤其是在 TLS：顯示應用程式資料之 (的 TLS 封包例如，在 Netmon 中，您可以透過) 尋找應用程式資料封包  `.Protocol.TLS AND Description == "TLS:TLS Rec Layer-1 SSL Application Data"` 。 您應該會在會話間看到一段時間的順利進展。 如果您在重新整理 Outlook Online 時看到長時間延遲，這可能是因為傳送高重設。

### <a name="latencyround-trip-time"></a>延遲/來回行程時間

延遲是一種可根據許多因素變更大量的量值，例如升級老化裝置、將大量使用者新增至網路，以及網路連線上其他工作消耗的整體頻寬百分比。

[Office 365 的頻寬計算機] 可以從這種 [網路規劃和效能調整 office 365](network-planning-and-performance.md) 頁面取得。

需要衡量連線速度或您的 ISP 連線的頻寬？ 請嘗試此網站 (或網站（如它）) ： [Speedtest 官方網站](https://www.speedtest.net/)，或查詢您最愛的搜尋引擎以進行片語 **速度測試**。

#### <a name="tools"></a>工具

- 坪
- PsPing
- 監視器
- Wireshark

#### <a name="what-to-look-for"></a>要尋找的專案

為了追蹤追蹤中的延遲，您會受益于記錄用戶端電腦的 IP 位址和 Office 365 中 DNS 伺服器的 IP 位址。 這是為了簡化追蹤篩選的目的。 如果您透過 proxy 進行連線，您將需要用戶端電腦的 IP 位址、proxy/出局 IP 位址，以及 Office 365 DNS IP 位址，以簡化工作。

傳送至 outlook.office365.com 的 ping 要求會告訴您接收要求的資料中心名稱，即使 ping  *可能*  無法連線以傳送商標連續 ICMP 封包。 如果您使用 PsPing (免費的下載) 工具，並指定埠 (443) ，而且可能使用 IPv4 (-4) 您會獲得傳送之封包的平均往返時間。 這會針對 Office 365 服務中的其他 URLs 執行這項作業，例如 `psping -4 yourSite.sharepoint.com:443` 。 實際上，您可以指定 ping 以取得您平均平均的範例，嘗試使用一些類似的範例 `psping -4 -n 20 yourSite-my.sharepoint.com:443` 。

> [!NOTE]
> PsPing 不會傳送 ICMP 封包。 它會 ping 透過特定埠的 TCP 封包，讓您可以使用任何一種您知道的開啟。 在 Office 365 中使用 SSL/TLS，嘗試將埠：443附加到您的 PsPing。

![螢幕擷取畫面顯示的 ping 解析 outlook.office365.com，以及443執行相同的 PSPing，但同時又報告6.5 毫秒平均 RTT。](../media/c64339f2-2c96-45b8-b168-c2a060430266.PNG)

如果在進行網路追蹤時，載入 [執行 Office 365 的速度變慢] 頁面，則應該篩選 Netmon 或 Wireshark 追蹤 `DNS` 。 這是我們要尋找的其中一個 Ip。

以下是用來篩選 Netmon 以取得 IP 位址 (，並查看 DNS 延遲) 的步驟。 本範例會使用 outlook.office365.com，但也可以使用 SharePoint Online 租使用者 (hithere.sharepoint.com 的 URL，例如) 。

1. Ping URL， `ping outlook.office365.com` 然後在結果中記錄已傳送 ping 要求之 DNS 伺服器的名稱和 IP 位址。
2. 網路追蹤開啟頁面，或執行使您產生效能問題的動作，或者，如果您在 ping 上看到過高的延遲，它本身就是網路追蹤。
3. 在 Netmon 中開啟追蹤並篩選 DNS (此篩選也可在 Wireshark 中運作，但對) 大小寫敏感 `-- dns` 。 由於您知道從您的 ping 知道 DNS 伺服器的名稱，因此您也可以在 Netmon 中篩選更多 speedily，如下所示： `DNS AND ContainsBin(FrameData, ASCII, "namnorthwest")` 在 Wireshark DNS 及 frame 包含 "namnorthwest" 的情況下，它看起來就像這樣。<br/>開啟回應封包，然後在 [Netmon **框架詳細資料** ] 視窗中，按一下 [ **DNS** ] 以展開詳細資訊。 在 [DNS 資訊] 中，您會找到要求在 Office 365 中進入之 DNS 伺服器的 IP 位址。 您將需要此 IP 位址進行下一個步驟 (PsPing 工具) 。 移除篩選，以滑鼠右鍵按一下 Netmon 中的 DNS 回應 (**框架摘要** \> **尋找交談** \> **dns**) 以並排查看 dns 查詢和回應。
4. 在 Netmon 中，也請記下 DNS 要求和回應之間的時間位移欄。 在下一個步驟中，易於安裝和使用的 [PsPing](/sysinternals/downloads/psping) 工具會非常方便，因為這兩者是因為 ICMP 通常會封鎖在防火牆上，而且因為 PsPing elegantly 追蹤延遲（以毫秒為單位）。 PsPing 會在我們的案例開啟埠 443) 中完成 TCP 連線到位址及埠 (。
5. 安裝 PsPing。
6. \> \> 在您安裝 PsPing 以執行 PsPing 命令的目錄上，開啟命令提示字元 (Start Run type Cmd 或 Windows Key \> type cmd) 並將目錄變更為您安裝的目錄。 在 [我的範例] 中，您可以看到 I 是 C 的根的「Perf」資料夾。您可以使用相同的快速存取。
7. 輸入命令，讓您從舊版的 Netmon 追蹤（包括埠號碼） PsPing Office 365 DNS 伺服器的 IP 位址 `psping -n 20 132.245.24.82:445` 。 這可讓您在 PsPing 停止時，為您提供20個 ping 的抽樣，並平均延遲時間。

如果您是透過 proxy 伺服器前往 Office 365，步驟會不同。 您會先 PsPing 至 proxy 伺服器，以毫秒為單位取得 proxy/出局及回復的平均延遲值，然後在 proxy 上執行 PsPing，或是在具有直接網際網路連線的電腦上執行) ，以取得遺失的值 (一至 Office 365 及後。

如果您選擇從 proxy 執行 PsPing，則會有兩個毫秒值：用戶端電腦到 proxy 伺服器或出局點，以及 proxy 伺服器到 Office 365。 您已經完成！ 哦，還是要記錄的值。

如果您在另一部用戶端電腦上執行 PsPing，但該電腦上有直接連線至網際網路，也就是沒有 proxy，您會有兩個毫秒值：用戶端電腦到 proxy 伺服器或出局點，以及用戶端電腦到 Office 365。 在此情況下，將用戶端電腦的值減去為 proxy 伺服器或出局點從用戶端電腦的值，到 Office 365，而您的用戶端電腦上的 RTT 編號則為 proxy 伺服器或出局點，而來自 proxy 伺服器或出局點至 Office 365。

不過，如果您可以在受影響的位置上找到直接連線的用戶端電腦，或略過此 proxy，您可以選擇查看問題是否會在開頭產生，並在此後進行測試。

延遲（如 Netmon 追蹤中所示），在任何指定的會話中，只要有足夠的時間，這些額外的毫秒數便可增加。

![Netmon 中的一般延遲，並將 Netmon 預設時間差異欄位新增至框架摘要。](../media/7ad17380-8527-4bc2-9b9b-6310cf19ba6b.PNG)

> [!NOTE]
> 您的 IP 位址可能不同于這裡顯示的 ip 位址，例如，您的 ping 可能會傳回如 157.56.0.0/16 或類似範圍的內容。 如需 Office 365 所用範圍的清單，請參閱 [office 365 URLs 和 IP 位址範圍](./urls-and-ip-address-ranges.md)。

請記得展開所有節點，如果您想要搜尋，請在此) 的上方 (按鈕（例如，132.245）。

### <a name="proxy-authentication"></a>Proxy 驗證

如果您是透過 proxy 伺服器，這只適用于您。 如果不是，您可以略過這些步驟。 當正常運作時，proxy 驗證應以毫秒為單位進行一致。 您不應該看到峰值使用時段的效能不良， (例如) 。

若已開啟 Proxy 驗證，每當您建立 Office 365 的新 TCP 連線以取得資訊時，您必須透過幕後的驗證程式來進行傳遞。 例如，在 Outlook Online 中從行事曆切換到郵件時，您會進行驗證。 在 [SharePoint 線上] 中，如果頁面顯示多個網站或位置的媒體或資料，您將會驗證每個不同的 TCP 連線，以便呈現資料。

在 Outlook Online 中，每當您在 [行事曆] 和 [信箱] 之間切換時，或在 SharePoint Online 中載入慢速網頁時，可能會遇到載入速度緩慢的情況 不過，這裡還有其他一些問題未列出。

Proxy 驗證是您的出口 proxy 伺服器上的設定。 如果是導致 Office 365 出現效能問題，您必須諮詢網路小組。

#### <a name="tools"></a>工具

- 監視器
- Wireshark

#### <a name="what-to-look-for"></a>要尋找的專案

每當新的 TCP 會話都必須旋轉時，通常會從伺服器要求檔案或資訊，或提供資訊，便會進行 Proxy 驗證。 例如，您可能會在 HTTP GET 或 HTTP POST 要求周圍看到 proxy 驗證。 如果您想要查看在追蹤中驗證要求的框架，請將「NTLMSSP 摘要」欄新增至 Netmon，然後篩選  `.property.NTLMSSPSummary` 。 若要查看驗證所花費的時間，請新增 [時間增量] 欄位。

若要將欄新增至 Netmon：

1. 以滑鼠右鍵按一下欄（如 [ **描述**]）。
2. 按一下 **[選擇欄**]。
3. 在清單中找出 _NTLMSSP 摘要_ 和 _時間 Delta_ ，然後按一下 [ **新增**]。
4. 將新的欄移至 [ _描述_ ] 欄之前或之後的位置，以便您可以並列閱讀。
5. 點擊 **[確定]**。

即使您沒有新增欄，Netmon 篩選也會運作。 不過，如果您可以看到您在哪個驗證階段，您的疑難排解會變得更容易。

在尋找 Proxy 驗證的實例時，請務必在所有出現 NTLM 質詢的幀上進行探索，否則會顯示驗證郵件。 如有必要，請以滑鼠右鍵按一下特定的流量，並尋找 [交談 \> TCP]。 請注意這些交談中的時間差值。

![顯示透過交談篩選之 proxy 驗證的 Netmon 追蹤。](../media/b640f176-0a52-4bbb-972e-60fb3d6aece2.PNG)

Proxy 驗證中的4秒延遲（如 Wireshark 所示）。 在 [框架詳細資料] 中，以滑鼠右鍵按一下具有相同名稱的欄位，然後選取 [新增為欄]，即可進行 **先前所顯示之框架** 欄的時間差。  <br/> ![在 Wireshark 中，您可以透過以滑鼠右鍵按一下 [框架詳細資料] 中的相同名稱欄位，然後選取 [新增為欄]，來進行「先前顯示的 frame 的時間差」欄。](../media/f5b7bde4-8067-4ee0-bc7f-e9062ce1ba6f.PNG)

### <a name="dns-performance"></a>DNS 效能

當盡可能接近客戶的國家/地區時，名稱解析的運作方式最佳，速度會很快。

若要在國外進行 DNS 名稱解析，則可以在頁面負載中增加秒數。 理想狀況下，名稱解析會出現在100ms 之下。 如果不是，您應該進行進一步的調查。

> [!TIP]
> 不確定 Client Connectivity in Office 365 的運作方式？ 請參閱下列的用戶端連線[參考檔。](/previous-versions//dn741250(v=technet.10))

#### <a name="tools"></a>工具

- 監視器
- Wireshark
- PsPing

#### <a name="what-to-look-for"></a>要尋找的專案

分析 DNS 效能通常是網路追蹤的另一個工作。 不過，PsPing 對於可能的原因或可能的原因，也很有説明。

DNS 流量是以 TCP 及 UDP 要求和回應明確標示，其識別碼會協助您以特定的回應來符合特定的要求。 例如，當線上 SharePoint 線上使用網路名稱或 URL 網頁時，您會看到 DNS 流量。 一般來說，在傳輸區域時，除了透過 UDP 執行這種流量以外，其他的流量都是如此。

在 Netmon 和 Wireshark 中，可讓您查看 DNS 流量的最基本篩選只是 `dns` 。 指定篩選時，請務必使用低的大小寫。 在您開始在用戶端電腦上再現問題之前，請記得先清除您的 DNS 解析程式快取。 例如，如果您有慢速 SharePoint 線上頁面負載的首頁，您應該關閉所有的瀏覽器、開啟新的瀏覽器、啟動追蹤、清除 DNS 解析程式快取，然後流覽至您的 SharePoint Online 網站。 整個頁面解析完畢後，您應該停止並儲存追蹤。

![在 Netmon 中，DNS 的基本篩選器是 DNS。](../media/1bebc118-ca13-45f3-803f-ab73e7af401d.png)

您想要查看此處的時間位移。 您可以完成下列步驟，將 **Time Delta** 欄新增至 Netmon，這樣做可能會有所説明：

1. 以滑鼠右鍵按一下欄（如 [ **描述**]）。
2. 按一下 **[選擇欄**]。
3. 找到清單中的 _時間差_ ，然後按一下 [ **新增**]。
4. 將新欄移至 [ _描述_ ] 欄前面或後面的位置，以便您可以並列閱讀。
5. 點擊 **[確定]**。

如果您找到感興趣的查詢，請考慮在 [框架詳細資料] 面板中以滑鼠右鍵按一下該查詢以隔離它，然後選擇 [ **尋找交談** \> **DNS**]。 請注意，網路交談面板會直接跳至其 UDP 流量記錄中的特定交談。

![透過 DNS 篩選的 Outlook Online 負載的 Netmon 追蹤，然後使用 [尋找交談]，然後使用 DNS 來縮小結果。](../media/763cf20e-7b48-4a37-9449-c9978cfe118b.PNG)

在 Wireshark 中，您可以建立 DNS 時間欄。 使用追蹤 (或開啟追蹤) 在 Wireshark 中，或在 [篩選依據] `dns` 或 [更多 helpfully] 中開啟  `dns.time` 。 按一下任何 DNS 查詢，然後在顯示詳細資料的窗格中，展開  `Domain Name System (response)` 詳細資料。 例如，您會看到一個用於 time (的欄位 `[Time: 0.001111100 seconds]` 。 在此時間按一下滑鼠右鍵，然後選取 [套用 **成] 欄**。 這可讓您快速排序追蹤的 **時間** 欄。 按一下 [新增] 欄，依遞減的數值排序，以查看哪個 DNS 通話所用的時間最長。

[在 Wireshark 中由 (小寫) dns.time 篩選的 SharePoint Online 瀏覽，時間起點為將詳細資料納入欄位和遞增排序起。](../media/1439dcc2-12ff-4ee2-9ef3-1484cf79c384.PNG)

如果您想要進一步調查 DNS 解析時間，請嘗試針對 TCP (所使用的 DNS 埠 PsPing，例如  `psping <IP address of DNS server>:53`) 。 您是否仍會看到效能問題？ 如果您這麼做，則問題可能會比特定的網路問題更廣泛，而不是特定的 DNS 應用程式在解決時所遇到的問題。 另外也值得一提的是，ping 至 outlook.office365.com，會告訴您 Outlook Online 的 DNS 名稱解析在採取的地方 (例如，outlook-namnorthwest.office365.com) 。

如果問題似乎是以 DNS 為依據，則可能需要聯繫您的 IT 部門，以查看 DNS 設定和 DNS 轉寄站，以進一步調查此問題。

### <a name="proxy-scalability"></a>Proxy 擴充性

Office 365 中的 Outlook Online 服務會授與用戶端多項長期連線。 因此，每一位使用者可能會使用更多需要較長壽命的連線。

#### <a name="tools"></a>工具

數學

#### <a name="what-to-look-for"></a>要尋找的專案

這個功能沒有專門的網路追蹤或疑難排解工具。 相反地，它是以頻寬計算限制和其他變數為基礎。

### <a name="tcp-max-segment-size"></a>TCP 最大區段大小

在 SYN-SYN/ACK 中找到。  請在您採取的任何效能網路追蹤中檢查，以確保 TCP 封包已設定為盡可能具有最大的資料量。

目標是要查看1460位元組的 MSS，以傳輸資料。 如果您正在使用 proxy，或您使用的是 NAT，請記得從用戶端到 proxy/出局/NAT，以及從 proxy/出局/NAT 對 Office 365 執行這種測試，以取得最佳結果！ 這些是不同的 TCP 會話。

#### <a name="tools"></a>工具

監視器

#### <a name="what-to-look-for"></a>要尋找的專案

TCP 最大區段大小 (MSS) 為網路追蹤中的三向握手的另一個參數，這表示您會在 SYN-SYN/ACK 封包中找到您需要的資料。 MSS 實際上很容易看到。

開啟您所擁有的任何效能網路追蹤，並尋找您想要的連線，或展示效能問題。

> [!NOTE]
> 如果您正在尋找追蹤，且需要找出與交談相關的流量，請依用戶端的 IP 篩選，或 proxy 伺服器或出局點的 IP 進行篩選，或是兩者皆有。 直接前往，您必須在追蹤時，ping 您要測試的 URL，以取得 Office 365 的 IP 位址，並加以篩選。

要尋找追蹤第二筆？ 請嘗試使用篩選器來調整您的方向。 在 Netmon 中，根據 URL 執行搜尋，例如 `Containsbin(framedata, ascii, "sphybridExample")` ，記下 [框架編號]。

在 Wireshark 中使用類似  `frame contains "sphybridExample"` 的專案。 如果您發現) 流量中發現遠端 Winsock (RWS， (其可能會在) Wireshark 中顯示為 [PSH，ACK]，請記住，在相關的 SYN-SYN/Ack 之前，如前文所述，可以立即看到 RWS 連線。

此時，您可以記錄該幀編號、放下篩選器、按一下 Netmon 中 [網路交談] 視窗中的 [ **所有流量** ]，以查看最接近的 SYN。

重要的是，如果您在追蹤時未收到任何 IP 位址資訊，請在追蹤 (一部分找到您的 URL `sphybridExample-my.sharepoint.com` ，例如) ，將會為您提供篩選的 ip 位址。

在您想要查看的追蹤中找出連接。 若要這麼做，您可以掃描追蹤、透過 IP 位址進行篩選，或是使用 Netmon 中的 [網路交談] 視窗來選取特定交談 IDs。 找到 SYN 資料包之後，請展開 [框架詳細資料] 面板中的 [Wireshark) 中的 [在 Netmon) 中的 TCP (] 或 [傳輸控制通訊協定 (]。 展開 [TCP 選項和 MaxSegmentSize]。 找到相關的 SYN-ACK frame，並展開 TCP 選項及 MaxSegmentSize。 這兩個值中較小的值將是最大的區段大小。 在此圖中，我在稱為 TCP 疑難排解的 Netmon 中使用內建的資料行。

![使用內建欄在 Netmon 中篩選的網路追蹤。](../media/e073df13-71f8-497a-83b4-bb9f70bd9833.PNG)

內建欄位於 [ **框架詳細資料** ] 面板的頂端。  (若要切換回普通模式，請再次按一下 [ **欄** ]，然後選擇 [ **時區**]。 ) 

![在欄位下拉式清單中尋找 TCP 疑難排解選項 (在框架摘要的頂端)。](../media/64fd4baa-a872-4f07-b959-752d7d37fd62.PNG)

以下是 Wireshark 中的篩選追蹤。  () 的 MSS 值都有特定的篩選準則 `tcp.options.mss` 。 SYN、SYN/ACK 和 ACK 握手的框架都是在 Wireshark 的底層，連結在對等方的詳細資料 (so 47 ACK，連結至 46 SYN/ACK，其連結至 43 SYN) ，以簡化這類工作。

![Wireshark 依 tcp 篩選的追蹤。 options。 mss 為最大區段大小 (MSS) 。](../media/51e278db-801b-48bc-9b68-87cf92f03fd6.PNG)

如果您需要在此矩陣) 中檢查 **選擇性的認可** (下一個主題，請勿關閉追蹤！

### <a name="selective-acknowledgment"></a>選擇性認可

在 SYN-SYN/ACK 中找到。 必須在 SYN 和 SYN/ACK 中以允許的方式報告。 選擇性認可 (SACK) 允許資料包或封包遺失時，傳輸資料的順利。 裝置可以停用此功能，這可能會導致效能問題。

如果您正在使用 proxy，或您使用的是 NAT，請記得從用戶端到 proxy/出局/NAT，以及從 proxy/出局/NAT 對 Office 365 執行這種測試，以取得最佳結果！ 這些是不同的 TCP 會話。

#### <a name="tools"></a>工具

監視器

#### <a name="what-to-look-for"></a>要尋找的專案

選擇性認可 (SACK) 是 SYN-SYN/ACK 握手中的另一個參數。 您可以透過許多方式，篩選追蹤以取得 SYN/ACK。

使用 Netmon 中的 [網路交談] 視窗，在要查看的追蹤中找出您想要查看的連線，方法是掃描追蹤、依 IP 位址篩選，或按一下交談識別碼。 當您找到 SYN 資料包、展開 Netmon 中的 TCP 或「框架詳細資料」區段中的 Wireshark 傳輸控制通訊協定。 展開 [TCP 選項]，然後按 [SACK]。 找到相關的 SYN-ACK frame，並展開 [TCP 選項] 和 [SACK] 欄位。 在 SYN 和 SYN/ACK 中皆允許某些 SACK。 以下是 Netmon 和 Wireshark 中所看到的 SACK 值。

![選擇性認可 (Netmon 中的 SACK) （tcp）。 flags = = 1。](../media/216f556f-5031-4ed2-b066-a0d9b3251fa2.PNG)

![Wireshark 中所示的 SACK 及篩選器 tcp.flags.syn == 1。](../media/0a6e26e5-43dc-403b-adc9-3349a55f4e4b.PNG)

### <a name="dns-geolocation"></a>DNS 地理位置

在世界上 Office 365 的何處，嘗試解決您的 DNS 通話影響您的連線速度。

在 Outlook Online 中，在第一個 DNS 查找完成之後，該 DNS 的位置將用來連線至最接近的資料中心。 您將會連線至 Outlook Online CAS 伺服器，此伺服器會使用主幹網路連接至儲存資料的資料中心 (dC) 。 速度較快。

當存取 SharePoint 線上時，向國外進行的使用者將會定向到其作用中的資料中心，也就是說，其位置是以 SPO 租使用者的家用基底 (成為基礎，因此，如果使用者是美國（) 美國），則為 USA 中的 dC。

Lync online 一次有一個以上的 dC 中有主動節點。 當您傳送 Lync online 實例的要求時，Microsoft 的 DNS 會判斷要求在世界上的位置，並傳回最近使用 Lync online 之地區 dC 中的 IP 位址。

> [!TIP]
> 需要進一步瞭解用戶端如何連接至 Office 365？ 請參閱 [Client Connectivity](/previous-versions//dn741250(v=technet.10)) reference 文章 (及其有説明的圖形) 。

#### <a name="tools"></a>工具

- 坪
- PsPing

#### <a name="what-to-look-for"></a>要尋找的專案

從用戶端的 DNS 伺服器對 Microsoft DNS 伺服器進行名稱解析的要求，在大部分情況下，會導致 Microsoft DNS 傳回地區性資料中心的 IP 位址 (dC) 。 這對您有何意義？ 如果您的總部是在 Bangalore、印度，但您是在美國舉行，當您的瀏覽器要求 Outlook Online 時，Microsoft 的 DNS 伺服器應該會將您的 IP 位址傳送至美國的資料中心（地區性資料中心）。 若 Outlook 需要郵件，該資料將會透過整個 Microsoft 的快速骨幹絡傳送到資料中心。

當以盡可能接近的使用者位置進行名稱解析時，DNS 的運作速度最快。 如果您是在歐洲，您想要移至歐洲的 Microsoft DNS，並 (理想的) 與歐洲的資料中心打交道。 從歐洲客戶前往 DNS 和北美的資料中心的效能將會變慢。

針對 outlook.office365.com 執行 Ping 工具，以判斷您的 DNS 要求在世界上的路由。 如果您在歐洲，您應該會看到類似 outlook-emeawest.office365.com 的回復。 在美洲，預期的類似 outlook-namnorthwest.office365.com。

透過 [開始 \> 執行 \> cmd] 或 [Windows key type cmd) ]，在用戶端 (電腦上開啟命令提示字元 \> 。 輸入 ping outlook.office365.com，然後按 ENTER 鍵。 請記住，若要透過 IPv4 指定 ping，請指定-4。 您可能無法從 ICMP 封包取得回復，但您應該會看到路由傳送要求的 DNS 名稱。 如果您想要查看此連線的延遲號碼，請嘗試 PsPing 至 ping 傳回之伺服器的 IP 位址。

![outlook.office365.com 的 Ping，顯示 outlook-namnorthwest 中的解析。](../media/06c944d5-6159-43ec-aa31-757770695e8b.PNG)

![PSPing 至 ping 至 outlook.office365.com 所傳回的 IP 位址，顯示平均28毫秒延遲。](../media/f2b25a75-1a87-4479-b8a7-fa4375683507.PNG)

### <a name="office-365-application-troubleshooting"></a>Office 365 應用程式疑難排解

#### <a name="tools"></a>工具

- 監視器
- HTTPWatch
- 瀏覽器中的 F12 主控台

在此網路特有的文章中，我們並未涵蓋應用程式特定疑難排解中所用的工具。 不過，您會找到您 *可以*[在此頁面上使用的](https://support.office.com/article/Network-planning-and-performance-tuning-for-Office-365-e5f1228c-da3c-4654-bf16-d163daee8848)資源。

## <a name="related-topics"></a>相關主題

[管理 Office 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Office 365 端點常見問題集](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) (機器翻譯)