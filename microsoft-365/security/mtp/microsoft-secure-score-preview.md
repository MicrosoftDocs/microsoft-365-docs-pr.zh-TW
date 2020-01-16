---
title: Microsoft 安全分數 （預覽）
description: 說明 Microsoft 安全分數 Microsoft 365 安全性中心、 詳細資料的計算方式，以及哪些安全性系統管理員可以預期使用它。
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365，安全分數資訊安全中心、 改進動作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: 284efd5224f3e48ab718c0de0c877f68fc0bdecc
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210475"
---
# <a name="microsoft-secure-score-preview"></a>Microsoft 安全分數 （預覽）

>[!IMPORTANT]
>一些資訊和有關搶鮮產品，可能會在正式發行之前大幅修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 安全分數是具有較高的數字，表示所採取的多個改進動作的組織的安全性狀態，度量單位。 下列建議的安全分數可以防止潛在威脅組織。 從 Microsoft 365 安全性中心集中式儀表板，組織可以監視，並在其 Microsoft 365 身分識別、 資料、 app、 裝置和基礎結構的安全性上運作。

安全分數可幫助組織：  

* 在組織的安全性狀態的目前狀態報告。
* 提供可測知性、 可見性、 指導以及控制項，以提高其安全性狀態。  
* 比較基準，並建立關鍵效能指標 (Kpi)。

組織存取的評量和趨勢，與其他 Microsoft 產品整合、 分數比較與類似的組織，以及執行更多功能強大的視覺效果。 分數也可反映協力廠商解決方案時解決建議的動作。

此外，您可以存取您的建議，以及分數透過[Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api)。 了解[安全分數資源類型](https://go.microsoft.com/fwlink/?linkid=2092996)。

## <a name="how-it-works"></a>運作方式

您所設定的特定點建議的安全性功能，執行與安全性相關的工作，或解決與協力廠商應用程式或軟體的改進巨集指令。 一些改進動作只提供點完全完成時，和某些授與部分點為單位，如果他們使用某些裝置或使用者完成。 如果您無法或不想要達成其中一個改進動作，您可以選擇接受風險或其餘的風險。

我們示範整組可能的改進功能，無論授權，因此您可以了解安全性最佳做法，並改善您的分數。 安全分數，無論哪項產品授權您的組織相同擁有哪些保持代表您的絕對的安全性狀態。 請記住，應取得平衡安全性與可用性，並不是每個建議才能為您的環境。

您的分數會更新以反映視覺效果和改進動作頁面中所呈現的資訊的即時。 安全分數也每天同步處理以接收關於每個動作您達成點為單位的系統資料。

### <a name="how-improvement-actions-are-scored"></a>如何改進動作，就會獲得

每個改進動作是值得 10 點或更少。 二進位的方式，就會獲得最-如果您實作的改進巨集指令，如建立新的原則，或開啟的特定設定，您會收到的資料點的 100%。 其他改進的動作，點都指定的百分比的總組態。 例如，如果改進巨集指令會指出您取得 30 點保護您的所有使用者以多重要素驗證和您只需要 100 個受保護的總使用者 5，會提供您大約 2 點的部分分數 (受保護的 5 / 100 總 * 30 的最大點數 = 2 點數部分分數)。

### <a name="products-included-in-secure-score"></a>安全分數中包含的產品

目前有 Office 365 （包括 SharePoint Online、 Exchange Online、 OneDrive for Business、 Microsoft 資訊保護和更多），建議 Azure AD，Microsoft Defender ATP 與 Cloud App Security。 建議的其他安全性產品即將推出。 建議將涵蓋每個產品相關聯的所有受攻擊面，但它們是不錯的比較基準。 您也可以將標示改進動作為所涵蓋的協力廠商。

## <a name="required-permissions"></a>必要的權限

若要存取 Microsoft 安全分數的權限，您必須獲指派其中一個 Azure Active Directory 中的下列角色。

### <a name="read-and-write-roles"></a>讀取和寫入角色

讀取與寫入權限，您可以進行的變更，並直接互動安全分數。 您也可以指派給其他使用者的唯讀權限。

* 全域管理員
* 安全性系統管理員
* Exchange 管理員
* SharePoint 系統管理員

### <a name="read-only-roles"></a>唯讀的角色

具有唯讀存取權，您不能編輯狀態] 或 [備忘稿改進巨集指令、 編輯分數區域，或編輯自訂比較。

* 服務台管理員
* 使用者系統管理員
* 服務管理員
* 安全性讀取者
* 安全性操作員
* 全域的讀取者

### <a name="graph-api"></a>Graph API

若要存取 Graph API，您需要有下列其中一個角色除了下列範圍：

* SecurityEvents.Read.All （適用於唯讀角色）
* SecurityEvents.ReadWrite.All (針對讀取和寫入角色)

## <a name="gain-visibility-into-your-security-posture"></a>取得您的安全性狀態的可視性

為了協助您更快速地需要的資訊，Microsoft 改進動作會組織成群組：

* 身分識別 （Azure AD 帳戶 & 角色與 Azure ATP 即將推出）
* 資料 (Microsoft Information Protection)
* 裝置 （Microsoft Defender ATP 裝置）
* 應用程式 （電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security）
* 基礎結構 （Azure 的資源）

在 [Microsoft 安全分數概觀] 頁面中，您可以看到點分割的方式這些群組與何種點可用之間。 [概觀] 頁面上也是以取得總分基準比較，與您安全分數的歷史趨勢的全面檢視的位置，並可以採取來改善您的分數的改進動作的優先順序。

![安全分數首頁](../media/secure-score/secure-score-homepage.png)
*圖 1: Microsoft 安全分數概觀] 頁面上*

## <a name="take-action-to-improve-your-score"></a>採取動作來改善您的分數

改進動作] 索引標籤列出解決可能受攻擊面，以及其狀態的安全性建議 （已完成且計劃，風險接受，第三廠商，與地址）。 您可以搜尋、 篩選和群組改進的所有動作。  

### <a name="ranking"></a>排名

排名根據由左到達成，實作困難，使用者的影響和複雜性的其餘點的數目。 最高排名的改進動作有大量的剩餘低困難、 使用者的影響，與複雜性的點。

### <a name="actions"></a>動作

當您選取特定的改進巨集指令時，整頁彈出式視窗隨即出現。  

![改進巨集指令彈出式範例](../media/secure-score/secure-score-improvement-action.png)
*圖 2： 改進巨集指令彈出式範例*

若要完成此動作，您有幾個選項：

* 選取 [**管理**回到 [設定] 畫面，並進行變更。 然後，您將取得巨集指令，值得中為可見的飛出視窗中的點。點通常需要大約 24 小時更新。

* 選取 [**共用**複製直接連結到的改進巨集指令，或選擇要共用的連結，例如電子郵件、 Microsoft Teams、 Microsoft Planner 或 ServiceNow 的平台。 選取 ServiceNow 可讓您建立變更票證也就是顯示在 ServiceNow 和 Microsoft 365 安全性中心首頁。 若要深入了解，請參閱[Microsoft 365 安全中心和 ServiceNow 整合](tickets.md)。

* 選取 [**編輯狀態和記事**] 以編輯任何手動狀態或錄製備忘稿特有的改進巨集指令。 您可以篩選或群組所改進動作] 索引標籤中狀態。您可以選取雕像如下所示

    * **地址**-您辨識改進巨集指令是必要的而且打算在未來解決在某個時間點。 此狀態下也適用於部分，但未完全完成時會偵測的動作。
    * **計劃**— 中準備就緒可以完成的改進巨集指令沒有具體計劃。
    * **風險接受**— 安全性應該一律平衡與可用性，並不是每個建議適用於您的環境。 時，這種情況，您可以選擇要接受風險; 或是其餘的風險，並不制訂的改進巨集指令。 您不會提供任何點，但巨集指令不再是可見的改進動作清單中。 您可以檢視歷程記錄中的此巨集指令或復原在任何時間。
    * **透過協力廠商解決**— 由協力廠商應用程式或軟體已處理過的改進巨集指令。 讓您的成績更妥善地反映您的整體安全性狀態，您將能夠值得了巨集指令的點。 如果協力廠商不再涵蓋控制項，您可以選擇另一個狀態。 請記住，Microsoft 就會有任何可見性實作的完整性，如果改進巨集指令會標示為透過協力廠商解決

### <a name="prerequisites"></a>必要條件

任何需要可獲得授權或需要解決的改進巨集指令先完成的動作，將會列出實作] 區段中的必要條件。 請確定您在您完成的改進巨集指令的授權中有足夠的基座，而且這些授權可套用至所需的使用者。  

## <a name="track-your-score-history-and-meet-goals"></a>追蹤您的分數歷程記錄，以及達成目標

您可以檢視圖表，貴組織的分數經過一段時間**歷程記錄**中的圖形下方] 索引標籤所採取的所選的時間範圍和其屬性，例如產生點及類別中的所有動作的清單。 您可以依類別自訂日期範圍與篩選器。

在 [**度量資訊 & 趨勢**] 索引標籤中，有數個圖形與圖表提供更多的可見性趨勢，並設定目標。 您可以設定整頁的視覺效果的日期範圍。 視覺效果包括：

* **您的安全分數區域**— 自訂根據貴組織的目標和良好、 沒問題，以及不正確的分數的定義範圍。
* **迴歸分析趨勢**— 時間表，因為組態、 使用者或裝置變更有迴歸去的點數。  
* **比較趨勢**— 如何貴組織的安全分數會比較給其他人的一段時間。 此檢視可包含行代表分數的組織具有類似的基座計數和平均您可以設定自訂比較檢視。
* **風險驗收趨勢**— 時間表的改進動作標示為 「 公認的風險 」。
* **分數變更**— 點數目可達到、 points 迴歸，] 或 [新動作新增，以及後續分數變更，在指定的日期範圍。

## <a name="risk-awareness"></a>風險認知

Microsoft 安全分數是您的安全性狀態的數字摘要根據系統設定、 使用者行為及其他安全性相關的度量值;它不是絕對的度量單位的方式可能會破壞您的系統或資料。 相反地，它表示要採用的安全性控制 Microsoft 環境中可協助位移正在外洩的風險的程度。 沒有線上服務已完全免於安全性弱點，以及安全分數不應該解譯成保證郵件可以針對任何方式的安全性漏洞。

## <a name="whats-coming"></a>下來什麼？

### <a name="mfa-improvement-action-updates"></a>MFA 改進動作更新

若要反映適用於企業以確保 upmost 安全性時，套用原則可搭配其業務需求，Microsoft 安全分數會移除三個改進動作圍繞多重要素驗證，並新增兩個。

會移除三個：
- 登錄所有使用者的多重要素驗證
- 需要 MFA 的所有使用者
- 需要 MFA 的 Azure AD 特殊權限角色

新的改進動作：
- 確定所有的使用者可以完成的安全存取多重要素驗證
- 需要 MFA 的系統管理角色

 這些新的改進動作將會需要透過您的目錄中註冊您的使用者或系統管理員針對多重要素驗證 (MFA)，以及建立正確的一組原則符合貴組織的需求。 主要目標是有彈性，同時確保所有使用者和系統管理員可以驗證與多重因素或風險式身分識別驗證提示。 可能需要的設定，可讓 Microsoft 決定何時挑戰使用者的 mfa 功能、 安全性預設表單，或具有多個原則套用的範圍決策。

## <a name="whats-new"></a>新功能？ 

讓 Microsoft 安全分數更好您的安全性狀態的人，以及改善可用性，我們已進行一些變更。 已變更您的成績和最大可能分數。 不過，這並不表示您的安全性狀態變更。

### <a name="updated-interface-and-functionality"></a>更新的介面和功能

* 首席資訊安全長的所有新評量和趨勢檢視，而且會導致層級的討論區
* 追蹤及基準測試您的分數的新方法
* 更好的追蹤，以及了解適用於分數衰退
* 篩選、 標記、 搜尋及群組改進動作
* 管理向您未來的目標，使用分數估算和計劃的動作
* 還有更多 ！

### <a name="removed-not-scored-and-review-improvement-actions"></a>移除 「 不計分 」 和 「 檢閱 」 改進動作

之一的安全分數原則是分數應依照標準化預定且更容易與相關。 具有不是可以測量或可採取行動的改進動作具有已造成混淆。 一個 Microsoft 安全分數僅合理時的每個建議有清除影響分數。 不計分的改進動作不是可以測量的並檢閱動作不會測量為其他改進動作的同一個標準的改進。

基於這些理由，已被暫時移除所有已不會被記錄或需要檢閱頻率的改進動作。 在您的組件上不需要採取任何動作。

### <a name="simplification-of-the-point-system"></a>簡化的點系統

若要跨多個體驗標準化點，每個安全分數改進巨集指令點總計已經更新為 10 點值得或更少。 視需要在我們今天有的安全性控制和我們將在未來新增的探索寬口氣是更一致。 雖然這是重大變更，您會看到以點合計放置會有不會變更您的安全性狀態。

## <a name="we-want-to-hear-from-you"></a>我們想要從您聽到

如果您有任何問題，請讓我們知道[安全性、 隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社群中的張貼。 我們正在監視社群，並將提供的說明。
