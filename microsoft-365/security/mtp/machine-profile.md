---
title: Microsoft 365 安全性入口網站中的電腦設定檔
description: 查看組織中裝置的風險與暴露層級。 分析過去並呈現威脅，並以最新的更新保護電腦。
keywords: 安全性，惡意程式碼，Microsoft 365，M365，Microsoft 威脅防護，MTP，安全性中心，Microsoft Defender ATP，Office 365 ATP，Azure ATP，機器頁面，機器清單，電腦設定檔
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 7ab3f63008c65fca1a99128cc6f11f83bc86b2b4
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857550"
---
# <a name="machine-profile-page"></a>電腦設定檔頁面面

Microsoft 365 安全性入口網站為您提供電腦設定檔頁面面，因此您可以評估網路上裝置的健康情況和狀態。 每個機器設定檔頁面麵包含有關裝置的大量資訊。

您可以查看有關其執行的軟體、任何過去及呈現安全性事件或警示的深入資訊，並尋找相關軟體修補程式的連結。

您也可以使用電腦設定檔執行常見的安全性相關工作，並快速查看裝置的基本詳細資料。

## <a name="navigating-the-machine-profile-page"></a>流覽 [機器設定檔] 頁面

您可以直接選取 [機器] 清單上的裝置名稱，或選擇 [電腦清單] 浮出控制項上的 [**開啟機器] 頁面**，即可存取 [機器設定檔] 頁面。

當您開啟頁面後，就會發現它會分成三個區段。

![具有（1）索引標籤區域（2）邊欄及（3）個動作以紅色反白顯示的機器設定檔頁面面的圖像](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

主要內容區域（1）包含7個索引標籤，您可以切換以查看有關機器的不同類型的資訊。

側邊（2）列出機器的基本詳細資料。

「側邊」和「主要內容」區段的頁首（3）中也有可用的回應動作。 您可以使用此標頭中的動作來執行常見的安全性相關工作。

## <a name="tabs-section"></a>Tabs 區段

[機器設定檔] 索引標籤可讓您透過電腦的安全性詳細資料、包含警示清單的表、時程表、安全性建議清單、軟體清查、發現之弱點清單及遺失的方式來切換Kb （安全性更新）。

### <a name="overview-tab"></a>概覽] 索引標籤

預設索引標籤為 **[一覽表**]。 它可快速查看有關裝置的最重要安全性事實。

![電腦設定檔之 [簡介] 索引標籤的影像](../../media/mtp-machine-profile/overview.png)

您可以在這裡尋找裝置風險層級和作用中警示的圖表、任何目前登入的使用者、大部分最少使用者的簡短清單及安全性評估，以詳述裝置的暴露層級、安全性建議、受影響的軟體，以及發現的漏洞。

### <a name="alerts-tab"></a>[通知] 索引標籤

[**警示**] 索引標籤包含已在裝置上報告的警示清單。

![電腦設定檔的 [警示] 索引標籤](../../media/mtp-machine-profile/alerts.png)

您可以自訂所顯示的專案數，以及顯示每個專案的欄數。 預設行為是每頁列出30個專案，且已開啟11欄來顯示。

此索引標籤中的欄包含觸發警示之威脅之嚴重性的資訊，以及狀態、調查狀態，以及已指派警示的人員。

「*受影響的實體*」欄位是指的是目前正在查看其設定檔的電腦（實體），再加上受影響之網路中的任何其他電腦。

選取此清單中的專案將會開啟指向選取之警示的連結。

此清單可按嚴重性、狀態或受託人篩選。

### <a name="timeline-tab"></a>時程表] 索引標籤

[**時程表**] 索引標籤包含在裝置上所引發之事件的互動式、有時間圖表。 透過移動圖表的醒目提示區域，您可以在不同的時間範圍中查看事件。 您也可以輸入自訂的日期範圍。

圖表下方是所選取日期範圍的事件清單。

![電腦設定檔的 [時程表] 索引標籤的影像](../../media/mtp-machine-profile/timeline.png)

可自訂顯示的專案數和清單中的欄數。 預設值欄會列出事件時間、作用中使用者、動作類型、實體（處理常式）及事件的其他相關資訊。

從清單中選取一個專案，就會開啟一個顯示事件實體圖表的飛出視窗，顯示觸發事件的父項和子進程。

此清單可依特定類型的事件篩選;例如，登錄事件或 Smart Screen 事件。

### <a name="security-recommendations-tab"></a>安全性建議] 索引標籤

[**安全性建議**] 索引標籤會列出您可以採取以保護裝置的動作。 選取此清單上的專案會開啟快顯視窗，您可以在其中取得如何套用建議的指示。

![電腦設定檔的安全性建議的映射] 索引標籤](../../media/mtp-machine-profile/security-recs.png)

如同先前的索引標籤，每頁顯示的專案數，可以自訂哪些欄是可見的。

預設的視圖包含詳細說明解決安全弱點、相關威脅、相關元件或受威脅影響的軟體等等的各欄。 專案可以以建議的狀態加以篩選。

### <a name="software-inventory"></a>軟體清查

[**軟體清查**] 索引標籤會列出裝置上已安裝的軟體。

![電腦設定檔之軟體庫存索引標籤的影像](../../media/mtp-machine-profile/software-inventory.png)

預設的查看會顯示軟體廠商、已安裝的版本號碼、已知軟體弱點的數目、威脅深入資訊、產品碼及標記。 可自訂顯示的專案數和顯示的欄數。

選取此清單中的專案會開啟快顯視窗，其中包含選取之軟體的詳細資料，以及上次找到該軟體的路徑和時間戳記。

可依照產品程式碼篩選此清單。

### <a name="discovered-vulnerabilities-tab"></a>發現的漏洞] 索引標籤

[已**發現的漏洞**] 索引標籤會列出任何可能會影響裝置的常見漏洞和手段（cve）。

![電腦設定檔的 [已發現之弱點] 索引標籤影像](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

預設的視圖會列出 CVE 的嚴重性、一般弱點得分（CVS）、發行 cve 時、發行 cve 的時間、最後更新 CVE 的時間，以及與 CVE 相關的威脅。

就像先前的索引標籤一樣，您可以自訂顯示的專案數和可見的欄。

選取此清單中的專案將會開啟描述 CVE 的浮出控制項。

### <a name="missing-kbs"></a>遺失 Kb

[**遺失的 kb** ] 索引標籤會列出所有尚未套用到機器的 Microsoft 更新。 Kb 中的「」是描述這些更新的[知識文庫文章](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query)。例如， [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)。

![電腦設定檔遺失 kb 索引標籤的影像](../../media/mtp-machine-profile/missing-kbs.PNG)

預設的視圖會列出公告欄，其中包含更新、作業系統版本、受影響的產品、Cve 定址、KB 編號及標記。

每頁顯示的專案數，可以自訂顯示哪些欄。

選取專案會開啟連結至更新的浮出控制項。

## <a name="sidebar"></a>側 欄

在 [機器設定檔] 頁面的主要內容區域旁是側邊。

![電腦設定檔的邊欄索引標籤影像](../../media/mtp-machine-profile/sidebar.png)

側邊條會在小型子小節中提供一些重要的基本資訊，這些資訊可切換為開啟或關閉：

* **標記**-任何與裝置相關聯的標記
* **安全性資訊**-開啟中的事件、作用中的警示、暴露層級和風險層級
* **裝置詳細資料**-網域、OS、資產群組、健康狀態、資料敏感度及 IP 位址
* **網路活動**-在網路上第一次或最近一次看到裝置的時間戳記

本節也包含裝置的名稱和暴露層級，以及指出網路上目前是否使用的圖示。

## <a name="response-actions"></a>回應動作

回應動作提供一種快速防護和分析威脅的方式。

![電腦設定檔的邊欄索引標籤影像](../../media/mtp-machine-profile/actions.PNG)

您可以在這裡使用的回應動作包括：

* **Manage tags** -更新您已套用至此裝置的自訂標記。
* **隔離機器**-從組織網路隔離機器，同時保持其連線至 Microsoft Defender 高級威脅防護。 您可以選擇在隔離機器時，允許 Outlook、小組和商務用 Skype 執行，以進行通訊的目的。
* **限制應用程式執行**-防止未由 Microsoft 簽署的應用程式執行
* **執行防病毒掃描**-更新 Windows Defender 防病毒定義，並立即執行防病毒掃描。 選擇 [快速掃描] 或 [完全掃描]。
* 收集有關機器的**調查套件**收集資訊。 完成調查後，您可以下載。
* **啟動 Live Response session** -在機器上載入遠端命令介面，以進行[深入的安全性調查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)。
* **啟動自動化調查**-自動[調查和 remediates 威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。 雖然您可以手動觸發從這個頁面執行的自動調查，但[某些警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies)會自行觸發自動調查。
* **行動中心**-查看已提交動作的狀態。 只有在已選取另一個動作時才可用。

## <a name="related-topics"></a>相關主題

* [Microsoft 威脅防護概觀](microsoft-threat-protection.md)
* [開啟 Microsoft 威脅防護](mtp-enable.md)
* [使用即時回應調查機器上的實體](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Office 365 中的自動化調查和回應（AIR）](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
