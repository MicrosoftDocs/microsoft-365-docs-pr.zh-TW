---
title: Microsoft 365 安全性入口網站中的裝置設定檔
description: 查看組織中裝置的風險與暴露層級。 分析過去並呈現威脅，並以最新的更新保護裝置。
keywords: 安全性，惡意程式碼，Microsoft 365，M365，Microsoft 威脅防護，MTP，安全性中心，Microsoft Defender ATP，Office 365 ATP，Azure ATP，裝置頁面，裝置設定檔，機器頁面，電腦設定檔
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
ms.openlocfilehash: f6b79d3252084b298f94e01b18ebe3505f83b480
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196854"
---
# <a name="device-profile-page"></a>裝置設定檔頁面面

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 安全性入口網站為您提供裝置設定檔頁面面，因此您可以快速評估網路上裝置的健康情況和狀態。

> [!IMPORTANT]
> 裝置設定檔頁面面的顯示可能會稍有不同，這取決於裝置是否已在 Microsoft Defender ATP、Azure ATP 或兩者中註冊。

如果裝置已在 Microsoft Defender ATP 中註冊，您也可以使用 [裝置設定檔] 頁面執行某些常見的安全性工作。

## <a name="navigating-the-device-profile-page"></a>流覽裝置設定檔頁面面

設定檔頁面面會分成數個較寬的區段。

![具有 (1) 索引標籤區域 (2) 邊欄及 (3) 動作的裝置設定檔頁面面的圖像以紅色醒目顯示](../../media/mtp-device-profile/hybrid-device-overall.png)

邊欄 (1) 會列出裝置的基本詳細資料。

主要內容區域 (2) 包含的索引標籤可供您切換以查看裝置的不同資訊類型。

如果裝置註冊于 Microsoft Defender ATP，您也會看到 (3) 回應動作清單。 回應動作可讓您執行常見的安全性相關工作。

## <a name="sidebar"></a>側 欄

在裝置設定檔頁面面的主要內容區域旁是側邊。

![裝置設定檔的邊欄索引標籤影像](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

提要欄會列出裝置的完整名稱和暴露層級。 它也會在小型子小節中提供一些重要的基本資訊，這些資訊可切換為開啟或關閉，例如：

* **標記** -任何與裝置相關聯的 MICROSOFT Defender ATP、Azure atp 或自訂標記。 來自 Azure ATP 的標記不可編輯。
* **安全性資訊** -開啟的事件和主動警示。 在 Microsoft Defender ATP 中註冊的裝置也會顯示公開層級和風險層級。

> [!TIP]
> 暴露層級與裝置遵循安全性建議的程度有關，而風險等級是根據因素的數目計算，包括作用中警示的類型和嚴重性。

* **裝置詳細資料** -網域、OS、在第一次看到裝置時的時間戳記、IP 位址、資源。 在 Microsoft Defender ATP 中註冊的裝置也會顯示健康狀態。 在 Azure ATP 中註冊的裝置會顯示 SAM 名稱，以及在第一次建立裝置時的時間戳記。
* **網路活動** -在網路上第一次或最近一次看到裝置的時間戳記。
* *僅適用于 AZURE ATP*) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview)旗標、 [spn](https://docs.microsoft.com/windows/win32/ad/service-principal-names)和群組成員資格中所註冊的裝置的**目錄資料** (。

## <a name="response-actions"></a>回應動作

回應動作提供一種快速防護和分析威脅的方式。

![裝置設定檔的動作欄圖像](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * 只有在裝置註冊于 Microsoft Defender ATP 時，才可使用[回應動作](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)。
> * 在 Microsoft Defender ATP 中註冊的裝置，視裝置的作業系統和版本編號而定，可能會顯示不同數目的回應動作。

在裝置設定檔頁面面上可用的動作包括：

* **Manage tags** -更新您已套用至此裝置的自訂標記。
* **隔離裝置** -從組織網路隔離裝置，並使其連線至 Microsoft Defender 高級威脅防護。 您可以選擇在隔離裝置時，允許 Outlook、小組和商務用 Skype 執行，以進行通訊的目的。
* **行動中心** -查看已提交動作的狀態。 只有在已選取另一個動作時才可用。
* **限制應用程式執行** -防止未由 Microsoft 簽署的應用程式執行。
* **執行防病毒掃描** -更新 Windows Defender 防病毒定義，並立即執行防病毒掃描。 選擇 [快速掃描] 或 [完全掃描]。
* 收集有關裝置的**調查套件**收集資訊。 完成調查後，您可以下載。
* **Initiate Live Response Session** -在裝置上載入遠端命令介面，以進行 [深入的安全性調查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)。
* **啟動自動化調查** -自動 [調查和 remediates 威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。 雖然您可以手動觸發從這個頁面執行的自動調查，但 [某些警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) 會自行觸發自動調查。
* **動作中心** -顯示目前正在執行之回應動作的相關資訊。

## <a name="tabs-section"></a>Tabs 區段

[裝置設定檔] 索引標籤可讓您切換有關裝置安全性詳細資訊，以及包含警示清單的表格。

在 Microsoft Defender ATP 中註冊的裝置也會顯示功能標籤，該功能標籤會顯示時程表、安全性建議的清單、軟體清查、發現之弱點的清單，以及遺漏的 Kb (安全性更新) 。

### <a name="overview-tab"></a>概覽] 索引標籤

預設索引標籤為 **[一覽表**]。 它可快速查看有關裝置的最重要安全性事實。

![裝置設定檔之 [簡介] 索引標籤的影像](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

在這裡，您可以快速查看裝置的使用中警示及任何目前登入的使用者。

如果裝置已在 Microsoft Defender ATP 中註冊，您也會看到裝置的風險等級及安全性評估上任何可用的資料。 安全性評估會說明裝置的暴露層級、提供安全性建議，並列出受影響的軟體及發現的弱點。

### <a name="alerts-tab"></a>[通知] 索引標籤

[ **警示** ] 索引標籤包含從 Azure ATP 和 MICROSOFT Defender atp 產生于裝置上的警示清單。

![裝置設定檔的 [警示] 索引標籤](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

您可以自訂所顯示的專案數，以及顯示每個專案的欄數。 預設行為是每頁列出30個專案。

此索引標籤中的欄包含觸發警示之威脅之嚴重性的資訊，以及已指派警示的狀態、調查狀態。

「 *受影響的實體* 」欄位是指裝置 (實體) 目前正在查看其設定檔，以及受影響的網路中的任何其他裝置。

選取此清單中的專案，就會開啟一個快顯視窗，其中包含關於選取之警示的詳細資訊。

您可以根據嚴重性、狀態或指派警示的人員來篩選此清單。

### <a name="timeline-tab"></a>時程表] 索引標籤

[ **時程表** ] 索引標籤包括裝置上所引發之所有事件的互動式、依序圖表。 將圖表的醒目區域向左或向右移動，您可以在不同的時段上查看事件。 您也可以在互動式圖表和事件清單之間的下拉式功能表中，選擇自訂的日期範圍。

圖表下方是所選取日期範圍的事件清單。

![裝置設定檔的 [時程表] 索引標籤的影像](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

可自訂顯示的專案數和清單中的欄數。 預設欄會列出事件時間、作用中使用者、動作類型、實體 (處理常式) ，以及事件的其他相關資訊。

選取此清單中的專案時，會開啟一個顯示事件實體圖表的飛出視窗，顯示事件中所涉及的父項和子處理常式。

可依特定類型的事件篩選清單;例如，登錄事件或 Smart Screen 事件。

您也可以將清單匯出至 CSV 檔案，以供下載。 雖然此檔案不受限於事件數目的限制，但您可以選擇匯出的最長時間範圍為7天。

### <a name="security-recommendations-tab"></a>安全性建議] 索引標籤

[ **安全性建議** ] 索引標籤會列出您可以採取以保護裝置的動作。 選取此清單上的專案會開啟快顯視窗，您可以在其中取得如何套用建議的指示。

![裝置設定檔的安全性建議的映射] 索引標籤](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

就像先前的索引標籤一樣，可以自訂每頁顯示的專案數，以及哪些欄是可見的。

預設的視圖包含詳細說明解決安全弱點、相關威脅、相關元件或受威脅影響的軟體等等的各欄。 專案可以以建議的狀態加以篩選。

### <a name="software-inventory"></a>軟體清查

[ **軟體清查** ] 索引標籤會列出裝置上已安裝的軟體。

![裝置設定檔之軟體清查標籤的影像](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

預設的查看會顯示軟體廠商、已安裝的版本號碼、已知軟體弱點的數目、威脅深入資訊、產品碼及標記。 可自訂顯示的專案數和顯示的欄數。

選取此清單中的專案會開啟快顯視窗，其中包含選取之軟體的詳細資料，以及上次找到該軟體的路徑和時間戳記。

可依照產品程式碼篩選此清單。

### <a name="discovered-vulnerabilities-tab"></a>發現的漏洞] 索引標籤

[已 **發現的漏洞** ] 索引標籤會列出可能會影響裝置的任何常見漏洞及 (cve) 。

![裝置設定檔的 [已發現之弱點] 索引標籤影像](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

預設的視圖會列出 CVE 的嚴重性、常見弱點分數 (CVS) 、發行 cve 時的軟體、發行 cve 的時間、最後更新 CVE 的時間，以及與 CVE 相關的威脅。

就像先前的索引標籤一樣，您可以自訂顯示的專案數和可見的欄。

選取此清單中的專案將會開啟描述 CVE 的浮出控制項。

### <a name="missing-kbs"></a>遺失 Kb

[ **遺失的 kb** ] 索引標籤會列出所有尚未套用到裝置的 Microsoft 更新。 Kb 中的「」是描述這些更新的 [知識文庫文章](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) 。例如， [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)。

![裝置設定檔遺失 kb] 索引標籤的影像](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

預設的視圖會列出公告欄，其中包含更新、作業系統版本、受影響的產品、Cve 定址、KB 編號及標記。

每頁顯示的專案數，可以自訂顯示哪些欄。

選取專案會開啟連結至更新的浮出控制項。

## <a name="related-topics"></a>相關主題

* [Microsoft 威脅防護概觀](microsoft-threat-protection.md)
* [開啟 Microsoft 威脅防護](mtp-enable.md)
* [使用即時回應調查裝置上的實體](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Office 365 中的自動調查和回應 (AIR) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
