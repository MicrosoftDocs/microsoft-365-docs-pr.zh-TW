---
title: Microsoft 安全評分（預覽）
description: 說明 microsoft 365 security center 中的 Microsoft Secure 得分、如何計算詳細資料，以及安全管理員可以使用的方式。
keywords: 安全性、惡意程式碼、Microsoft 365、M365、安全分數、安全性中心、改進動作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 8767174fa17aceab7d83adb96f938efad5074356
ms.sourcegitcommit: 1e9ce51efa583c33625299d17e37f58048a4169c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/24/2020
ms.locfileid: "43804770"
---
# <a name="microsoft-secure-score-preview"></a>Microsoft 安全評分（預覽）

>[!IMPORTANT]
>一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft Secure 得分是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。 可在 Microsoft 365 的https://security.microsoft.com/securescore安全性中心找到該網址。

遵循安全性分數建議可保護您的組織免受威脅。 透過 Microsoft 365 security center 中的集中式儀表板，組織可以監視及處理其 Microsoft 365 身分識別、資料、應用程式、裝置和基礎結構的安全性。

安全分數可協助組織：  

* 報告組織安全狀況的目前狀態。
* 提供探索性、可見度、指導方針和控制，以提升安全性狀況。  
* 與基準進行比較，並建立關鍵效能指標（KPIs）。

組織可以存取穩定的衡量方式和趨勢、與其他 Microsoft 產品的整合、與類似組織的分數比較，以及更多。 分數也可以反映協力廠商的解決方案如何解決建議的動作。

此外，您可以透過[Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)來存取您的建議和評分。 深入瞭解[安全分數資源類型](https://go.microsoft.com/fwlink/?linkid=2092996)。

## <a name="how-it-works"></a>運作方式

您可以在設定建議的安全性功能、執行安全性相關工作，或使用協力廠商應用程式或軟體來解決改進動作時，獲得相關的點數。 有些改進動作只會在完全完成時給予點，有些的動作會在某些裝置或使用者完成時提供部分分數。 如果您無法或不想要制定其中一個 [改進] 動作，您可以選擇接受風險或剩餘風險。

不管授權為何，我們都會向您顯示一組完整的可能改進功能，讓您瞭解安全性的最佳作法，並提升您的分數。 您的絕對安全性狀態是以安全分數表示，不論貴組織擁有的產品授權為何都會保持不變。 請記住，安全性應該與可用性進行平衡，而不是每個建議都適用于您的環境。

您的分數會即時更新，以反映 [視覺化效果] 和 [改進動作] 頁面中顯示的資訊。 安全分數也會每天同步處理每個動作的取得點數的系統資料。

### <a name="how-improvement-actions-are-scored"></a>如何計分改進動作

每個改進動作都值得10點或更少。 大多數會以二進位方式計分：若您執行改進動作（如建立新原則或開啟特定設定），您會收到100% 的點數。 在其他改進動作中，點會指定為總設定的百分比。 例如，如果改進的動作指出您使用多重要素驗證來保護所有使用者時取得30點，而且您只會保護 100 5% 以上的使用者，則會得到大約2點的部分分數（5個 protected/100 總計 * 30 最大值 = 2 pt 部分分數）。

### <a name="products-included-in-secure-score"></a>安全分數中包含的產品

目前有 Microsoft 365 的建議（包括 SharePoint Online、Exchange Online、商務 OneDrive、Microsoft 資訊保護等等）、Azure AD、Microsoft Defender ATP 和 Cloud App Security。 即將推出其他安全性產品的建議。 建議不會涵蓋與各項產品相關聯的所有攻擊面，但也是一個很好的基準。 您也可以將改進動作標示為協力廠商所涵蓋的範圍。

## <a name="required-permissions"></a>必要的權限

若要具有存取 Microsoft Secure 得分的許可權，您必須在 Azure Active Directory 中為下列其中一個角色指派。

### <a name="read-and-write-roles"></a>讀取和寫入角色

透過讀取和寫入權限，您可以進行變更，並直接與安全分數互動。 您也可以將唯讀許可權指派給其他使用者。

* 全域管理員
* 安全性系統管理員
* Exchange 系統管理員
* SharePoint 系統管理員
* 帳戶管理員

### <a name="read-only-roles"></a>唯讀角色

若具有唯讀許可權，您就無法編輯 [改進動作]、[編輯計分區域] 或 [編輯自訂比較] 的狀態或附注。

* 説明台管理員
* 使用者管理員
* 服務管理員
* 安全性讀取者
* 安全性操作員
* 全域讀取者

### <a name="graph-api"></a>圖形 API

若要存取 Graph API，除了 role 之外，您還必須具有下列其中一個範圍：

* SecurityEvents Read。 All （適用于唯讀角色）
* ReadWrite SecurityEvents （適用于讀取和寫入角色）

## <a name="gain-visibility-into-your-security-posture"></a>深入瞭解您的安全性狀況

為了協助您更快速地取得所需資訊，Microsoft 改進的動作會組織成群組：

* Identity （Azure AD 帳戶 & 角色）
* 資料（Microsoft 資訊保護）
* 裝置（現在沒有任何改進動作）
* 應用程式（電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security）
* 基礎結構（現在沒有任何改進動作）

在 [Microsoft Secure 得分一覽] 頁面中，您可以看到各群組之間的點數如何分割，以及哪些點可供使用。 [一覽表] 頁面也是取得整體總分、您的安全分數與基準比較之歷史趨勢的完整視圖，以及可以採取以改善評分的優先改進動作的位置。

![安全分數主頁](../../media/secure-score/secure-score-homepage.png)
*圖1： Microsoft Secure 得分一覽頁面*

## <a name="take-action-to-improve-your-score"></a>採取動作以提升您的分數

[改進動作] 索引標籤會列出解決可能攻擊面的安全性建議，及其狀態（已完成、已計畫、已接受的風險、協力廠商和 to address）。 您可以搜尋、篩選和群組所有的「改進」動作。  

### <a name="ranking"></a>排名

排名是根據剩下的剩餘點數、實施難度、使用者影響和複雜性而定。 最高排名的「改進」動作具有很大的分數，但有低難度、使用者影響和複雜性。

### <a name="actions"></a>動作

當您選取特定的 [提升] 動作時，會出現完整的頁面快顯視窗。  

![改進動作飛出](../../media/secure-score/secure-score-improvement-action.png)
範例*圖2：改進動作飛出範例*

若要完成此動作，您有幾個選項：

* 選取 [**管理**] 以進入設定畫面並進行變更。 接著，您將會在飛出的位置看到必要的動作。點通常需要24小時才能更新。

* 選取 [**共用**]，將直接連結複製到 [改進] 動作，或選擇用來共用連結的平臺，例如電子郵件、microsoft 小組、microsoft Planner 或 ServiceNow。 選取 [ServiceNow 將可讓您建立 ServiceNow 和 Microsoft 365 的安全性中心首頁會顯示的變更票證。 若要深入瞭解，請參閱[Microsoft 365 Security Center 和 ServiceNow integration](tickets.md)。

* 選取 [**編輯狀態和附注**] 編輯任何手動狀態，或記錄 [改進] 動作特有的附注。 您可以根據 [改進動作] 索引標籤中的狀態來篩選或群組。您可以選取下列 statues：

    * **若要解決**此事項，您可以辨識改進動作是必要的，並計畫于未來某一點進行處理。 這種狀態也適用于已偵測到部分但未完全完成的動作。
    * 已**計畫**-完成改進動作有一些具體的計畫。
    * 已**接受風險**-安全性應該一定要與可用性進行平衡，而不是每個建議都適用于您的環境。 在這種情況下，您可以選擇接受風險或餘下的風險，而不會制定改進動作。 您不會獲得任何點數，但是動作將不再顯示在 [改進動作] 清單中。 您可以在歷史記錄中查看此動作，也可以隨時復原。
    * **透過協力廠商解決**--改進動作已經由協力廠商應用程式或軟體所提出。 您將會獲得值得行動的點數，所以您的分數會更好反映整體的安全性狀況。 如果協力廠商不再涵蓋該控制項，您可以選擇其他狀態。 請記住，如果改進動作標示為透過協力廠商解決，Microsoft 將無法深入瞭解實施的完整性。

### <a name="prerequisites"></a>必要條件

「實施」區段中的必要條件會列出所有需要取得的授權，或在解決改進動作之前必須完成的動作。 請確定您的授權有足夠的座位，可完成 [改進] 動作，並將這些授權套用至必要的使用者。  

## <a name="track-your-score-history-and-meet-goals"></a>追蹤您的分數記錄並符合目標

您可以在 [**記錄**] 索引標籤中，在一段時間內，查看組織的分數圖表。在圖形下方會列出所選取時間範圍內所執行的所有動作，以及其屬性，例如結果點和類別。 您可以自訂日期範圍及依類別篩選。

在 [**度量 & 趨勢**] 索引標籤中，有數個圖形可讓您更深入的趨勢及設定目標。 您可以設定整個視覺效果頁面的日期範圍。 視覺化效果包括：

* **您的安全分數區域**-自訂取決於組織的目標和「良好」、「好」和「不良分數」範圍的定義。
* **回歸趨勢**-因設定、使用者或裝置變更而 regressed 之點的時程表。  
* **比較趨勢**-組織的安全分數與其他時間的比較方式。 此視圖可以包含表示具有類似座位元數目之組織之分數平均的行，以及您可以設定的自訂比較視圖。
* **風險接受趨勢**-標示為「風險已接受」的「改進」動作時程表。
* **得分變更**-在指定的日期範圍內，已增加的點數、點數 regressed 或新的動作，以及後續的分數變更。

## <a name="risk-awareness"></a>風險認知

Microsoft Secure 得分是根據系統設定、使用者行為和其他安全性相關度量的安全性狀況的數位摘要;這不是系統或資料被破壞的可能性的絕對度量。 相反地，它代表您已在 Microsoft 環境中採用安全性控制的程度，可協助抵消遭破壞的風險。 沒有任何線上服務完全避免安全缺口，安全分數不得以任何方式轉譯為保證安全性破壞。

## <a name="whats-new"></a>新功能 

若要讓 Microsoft 安全評分為您安全性狀況的更佳代表，我們進行了一些變更。 若要深入瞭解規劃的變更，請參閱[Microsoft Secure 得分中的內容？](microsoft-secure-score-whats-coming.md)。

### <a name="april-21st-2020"></a>2020年4月21日

#### <a name="added-azure-active-directory-improvement-action"></a>新增 Azure Active Directory 改進動作

- 不允許使用者將同意授與未受管理的應用程式（目前已發行版本本中提供）

#### <a name="added-azure-advanced-threat-protection-improvement-actions"></a>新增 Azure 高級威脅防護改進動作

- 停用網域控制站上的幕後列印程式服務
- 修改不安全的 Kerberos 委派以防止模仿
- 使用 Microsoft LAPS 保護和管理本機系統管理員密碼
- 降低橫向移動路徑對機密實體的風險
- 移除敏感群組中的睡眠帳戶
- 從實體中移除不安全的 SID 歷程記錄屬性
- 解決不安全的帳戶屬性
- 停止清除文字認證曝光
- 停止舊版通訊協定通訊
- 停止弱密碼使用

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a>支援 Microsoft Defender ATP 威脅 & 漏洞管理（TVM）安全性建議

現在提供 TVM 提供的所有發佈安全性建議。

### <a name="january---march-2020"></a>一月份-2020 年3月

#### <a name="updated-interface-and-functionality"></a>更新的介面及功能

* CISO 和潛在客戶層級討論的所有新的計量和趨勢視圖
* 追蹤和基準成績的新方法
* 更好地追蹤和瞭解分數回歸
* 篩選、標記、搜尋及群組您的改善動作
* 使用分數預測和規劃的動作來管理您的未來目標
* 還有更多！

#### <a name="removed-not-scored-and-review-improvement-actions"></a>移除「未評分」和「複查」改進動作

安全分數的原則之一是，分數應該是標準化的，且與的功能非常輕鬆。 具有不具可度量或具可操作性的改進動作已導致混淆。 只有在每個建議都會對分數有明確影響時，其中一個 Microsoft 安全評分才有意義。 不計分的改善動作不是可測量的，而且與其他改進動作相比，檢查改進動作不會以相同的標準進行度量。

基於這些原因，所有未計分或要求的改善動作都會暫時移除。 您的元件不需要任何動作。

#### <a name="simplification-of-the-point-system"></a>簡化了點系統

若要在多個經驗上標準化點，每個安全分數改進動作點總數已更新為10點以內。 在目前我們所做的安全性控制的廣泛 breather，以及未來將新增的安全性控制措施，都有一定的一致性。 雖然這是一項重大的變更，但您會看到點上有一個下沉，但是安全性狀況不會有任何變更。

## <a name="we-want-to-hear-from-you"></a>我們想要聽到您的來信

如果您有任何問題，請在[安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社區中公佈，以告知我們。 我們正在監視社區，並會提供協助。
