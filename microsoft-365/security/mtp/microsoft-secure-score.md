---
title: Microsoft 安全分數
description: 說明 microsoft 365 security center 中的 Microsoft 安全分數、如何改善安全性狀態，以及安全性管理員可以預期的狀況。
keywords: 安全性、惡意程式碼、Microsoft 365、M365、安全分數、安全性中心、改進動作
ms.prod: microsoft-365-enterprise
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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 57e18d68f6f33482fec3880b56ccad52c719a6d9
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023400"
---
# <a name="microsoft-secure-score"></a>Microsoft 安全分數

Microsoft Secure 得分是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。 可在 https://security.microsoft.com/securescore [Microsoft 365 的安全性中心](overview-security-center.md)找到該網址。

遵循安全分數建議可保護您的組織免受威脅。 透過 Microsoft 365 security center 中的集中式儀表板，組織可以監視及處理其 Microsoft 365 身分識別、資料、應用程式、裝置和基礎結構的安全性。

安全分數可協助組織：  

* 報告組織安全狀況的目前狀態。
* 提供探索性、可見度、指導方針和控制，以提升安全性狀況。  
* 與基準進行比較，並建立關鍵效能指標（KPIs）。

組織可以存取穩定的衡量方式和趨勢、與其他 Microsoft 產品的整合、與類似組織的分數比較，以及更多。 分數也可以反映協力廠商的解決方案如何解決建議的動作。

## <a name="how-it-works"></a>運作方式

您可以在設定推薦的安全性功能、執行安全性相關工作，或使用協力廠商應用程式或軟體來解決改進動作中的點數，也可以指定其他的緩解。 有些改進動作只會在完全完成時給予點，有些的動作會在某些裝置或使用者完成時提供部分分數。 如果您無法或不想要制定其中一個 [改進] 動作，您可以選擇接受風險或剩餘風險。

不管授權為何，我們都會向您顯示一組完整的可能改進功能，讓您瞭解安全性的最佳作法，並提升您的分數。 您的絕對安全性狀態是以安全分數表示，不論貴組織擁有的產品授權為何都會保持不變。 請記住，安全性應該與可用性進行平衡，而不是每個建議都適用于您的環境。

您的分數會即時更新，以反映 [視覺化效果] 和 [改進動作] 頁面中顯示的資訊。 安全分數也會每天同步處理每個動作的取得點數的系統資料。

### <a name="how-improvement-actions-are-scored"></a>如何計分改進動作

每個改進動作都值得10點或更少。 大多數會以二進位方式計分：若您執行改進動作（如建立新原則或開啟特定設定），您會收到100% 的點數。 在其他改進動作中，點會指定為總設定的百分比。 例如，如果改進的動作指出您使用多重要素驗證來保護所有使用者時取得10點，而且您只會保護 50 100 的使用者，則會得到部分分數5點（50 protected/100 總計 * 10 最大值 = 5 pt 部分分數）。

### <a name="products-included-in-secure-score"></a>安全分數中包含的產品

目前有 Microsoft 365 （包括 Exchange Online）、Azure AD、Microsoft Defender ATP、Azure ATP 和 Cloud App Security 的建議。 即將推出其他安全性產品的建議。 建議不會涵蓋與各項產品相關聯的所有攻擊面，但也是一個很好的基準。 您也可以將改進動作標示為協力廠商或替代範圍的緩解。

### <a name="security-defaults"></a>安全性預設

Microsoft 安全分數已更新改進動作，以支援[Azure Active Directory 中的安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)，如此可讓您的組織使用預先設定的安全性設定進行常見的攻擊，以協助保護您的組織。

如果您開啟安全性預設值，您會獲得下列改進動作的完整得分：

- 確定所有使用者均可完成安全存取的多重要素驗證（9點）
- 需要對管理角色進行 MFA （10點）
- 啟用原則以封鎖舊版驗證（7點）

>[!IMPORTANT]
>安全性預設值包括可提供類似安全性的安全性功能，以「登入風險原則」和「使用者風險原則」改進動作。 我們建議您將這些原則的安全性設定更新為「透過替代的緩解」來解決，而不是在安全性預設的上方進行。

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

## <a name="gain-visibility-into-your-security-posture"></a>深入瞭解您的安全性狀況

為了協助您更快速地取得所需資訊，Microsoft 改進的動作會組織成群組：

* Identity （Azure AD 帳戶 & 角色）
* 資料（Microsoft 資訊保護）
* 裝置（Microsoft Defender ATP，稱為設定[分數](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score)）
* 應用程式（電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security）
* 基礎結構（現在沒有任何改進動作）

>[!NOTE]
>在最近發行的 Microsoft Secure 得分中，已發行的評分模型已發佈，使 Microsoft 安全分數暫時不相容身分識別安全分數和圖形 API。 [檢視詳細資料](microsoft-secure-score.md#incompatibility-with-identity-secure-score-and-graph-api)

在 [Microsoft Secure 得分一覽] 頁面中，您可以看到各群組之間的點數如何分割，以及哪些點可供使用。 [一覽表] 頁面也是取得整體總分、您的安全分數與基準比較之歷史趨勢的完整視圖，以及可以採取以改善評分的優先改進動作的位置。

![安全分數首頁](../../media/secure-score/secure-score-homepage-new.png)

## <a name="take-action-to-improve-your-score"></a>採取動作以提升您的分數

[**改進動作**] 索引標籤會列出解決可能的攻擊面的安全性建議，及其狀態（to address、已計畫、已被認可的風險、透過協力廠商解決的問題，以及透過取代的緩解，以及已完成）。 您可以搜尋、篩選和群組所有的「改進」動作。  

### <a name="ranking"></a>排名

排名是根據剩下的剩餘點數、實施難度、使用者影響和複雜性而定。 最高排名的「改進」動作具有很大的分數，但有低難度、使用者影響和複雜性。

### <a name="view-improvement-action-details"></a>查看改進動作詳細資料

當您選取特定的 [提升] 動作時，會出現完整的頁面快顯視窗。  

![改進動作飛出範例 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *圖2：改進動作飛出範例*

若要完成此動作，您有幾個選項：

* 選取 [**管理**] 以進入設定畫面並進行變更。 接著，您將會在飛出的位置看到必要的動作。點通常需要24小時才能更新。

* 選取 [**共用**]，將直接連結複製到 [改進] 動作，或選擇用來共用連結的平臺，例如電子郵件、microsoft 小組、microsoft Planner 或 ServiceNow。 選取 [ServiceNow 將可讓您建立 ServiceNow 和 Microsoft 365 的安全性中心首頁會顯示的變更票證。 若要深入瞭解，請參閱[Microsoft 365 Security Center 和 ServiceNow integration](tickets.md)。

### <a name="choose-an-improvement-action-status"></a>選擇改進動作狀態

選擇 [改進] 動作特有的任何狀態和記錄附注。 您可以選取下列 statues：

* **若要解決**此事項，您可以辨識改進動作是必要的，並計畫于未來某一點進行處理。 這種狀態也適用于已偵測到部分但未完全完成的動作。
* 已**計畫**-完成改進動作有一些具體的計畫。
* 已**接受風險**-安全性應該一定要與可用性進行平衡，而不是每個建議都適用于您的環境。 在這種情況下，您可以選擇接受風險或餘下的風險，而不會制定改進動作。 您不會獲得任何點數，但是動作將不再顯示在 [改進動作] 清單中。 您可以在歷史記錄中查看此動作，也可以隨時復原。
* **透過協力廠商解決**，並**透過替代的緩解**措施加以解決--改進動作已經由協力廠商應用程式或軟體或內部工具所解決。 您將會獲得值得行動的點數，所以您的分數會更好反映整體的安全性狀況。 如果協力廠商或內部工具不再涵蓋該控制項，您可以選擇其他狀態。 請記住，如果改進動作標示為這兩種狀態，Microsoft 將不會深入瞭解實施的完整性。

#### <a name="threat--vulnerability-management-improvement-actions"></a>威脅 & 弱點管理的改進動作

在 "Device" 類別中的改進動作，您將無法選擇狀態。 相反地，您會將[Microsoft Defender 安全中心](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)的相關[威脅 & 漏洞管理（TVM）安全性建議](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)，以採取行動。 您選擇的例外狀況和您所撰寫的理由將會特定于該入口網站，而且不會出現在 Microsoft Secure 得分入口網站中。

#### <a name="completed-improvement-actions"></a>已完成的改進動作

在完成改進動作的所有可能點之後，[改進動作] 的狀態為「已完成」。 已完成的改善動作會透過 Microsoft data 加以確認，而且您將無法變更狀態。

### <a name="assess-information-and-review-user-impact"></a>評估資訊並複查使用者影響

**在 [一覽**] 區段中，將會告訴您您的類別、可以防禦的攻擊，以及產品。

[**使用者影響**] 顯示使用者在已頒佈改進動作時的體驗，以及**受影響的使用者**會顯示誰會體驗。

### <a name="implement-the-improvement-action"></a>實施改進動作

「**實施**」區段會顯示所有必要條件、逐步後續步驟以完成 [改進] 動作、[改進動作] 的目前實施狀態，以及任何 [深入瞭解] 連結。

必要條件會是任何需要取得的授權，或是在解決改進動作之前必須完成的動作。 請確定您的授權有足夠的座位，可完成 [改進] 動作，並將這些授權套用至必要的使用者。  

## <a name="track-your-score-history-and-meet-goals"></a>追蹤您的分數記錄並符合目標

您可以在 [**記錄**] 索引標籤中，在一段時間內，查看組織的分數圖表。在圖形下方會列出所選取時間範圍內所執行的所有動作，以及其屬性，例如結果點和類別。 您可以自訂日期範圍及依類別篩選。

在 [**度量 & 趨勢**] 索引標籤中，有數個圖形可讓您更深入的趨勢及設定目標。 您可以設定整個視覺效果頁面的日期範圍。 視覺化效果包括：

* **您的安全分數區域**-自訂取決於組織的目標和「良好」、「好」和「不良分數」範圍的定義。
* **回歸趨勢**-因設定、使用者或裝置變更而 regressed 之點的時程表。  
* **比較趨勢**-組織的安全分數與其他時間的比較方式。 此視圖可以包含表示具有類似座位元數目之組織之分數平均的行，以及您可以設定的自訂比較視圖。
* **風險接受趨勢**-標示為「風險已接受」的「改進」動作時程表。
* **得分變更**-已取得的點數，點 regressed，以及後續得分變更，在指定的日期範圍內。

## <a name="risk-awareness"></a>風險認知

Microsoft Secure 得分是根據系統設定、使用者行為和其他安全性相關度量的安全性狀況的數位摘要;這不是系統或資料被破壞的可能性的絕對度量。 相反地，它代表您已在 Microsoft 環境中採用安全性控制的程度，可協助抵消遭破壞的風險。 沒有任何線上服務完全避免安全缺口，安全分數不得以任何方式轉譯為保證安全性破壞。

## <a name="whats-new"></a>新功能 

若要讓 Microsoft 安全評分為您安全性狀況的更佳代表，我們進行了一些變更。 若要深入瞭解規劃的變更，請參閱[Microsoft Secure 得分中的內容？](microsoft-secure-score-whats-coming.md)。

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>不相容身分識別安全分數與圖形 API

在最近發行的 Microsoft Secure 得分中，已發佈一個已改進的計分模型。 這些變更可讓您更靈活且準確的安全性狀況的觀點。 不過，這些更新已讓 Microsoft 安全分數暫時不相容身分識別安全分數和圖形 API。

在時間內，身分識別安全分數和圖形 API 將採用新的計分模型。 在此之前，客戶會看到 Microsoft 安全評分、身分識別安全分數及圖形 API 所報告的分數差異。 我們對這項不便的任何不便深表歉意，而且正在運作，以確保未來的體驗更具相容性。

### <a name="updated-improvement-actions"></a>更新的改進動作

- 新增 Azure Active Directory 改進動作
- 新增 Azure 高級威脅防護改進動作
- 支援 Microsoft Defender ATP[威脅 & 弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)安全性建議
    - 現在提供 TVM 提供的所有發行安全性建議

### <a name="updated-interface-and-functionality"></a>更新的介面及功能

* CISO 和潛在客戶層級討論的所有新的計量和趨勢視圖
* 追蹤和基準成績的新方法
* 更好地追蹤和瞭解分數回歸
* 篩選、標記、搜尋及群組您的改善動作
* 使用分數預測和規劃的動作來管理您的未來目標
* 還有更多！

### <a name="june-2020"></a>2020 年 6 月

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>已移除 Microsoft Defender 高級威脅防護的改進動作

* 開啟攻擊面減少規則

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>新增 Microsoft Defender 高級威脅防護的改進動作

* 封鎖 Adobe Reader，以建立子流程
* 使用勒索軟體的高級防護
* 封鎖所有 Office 應用程式以建立子流程
* 封鎖 Office 應用程式建立可執行檔內容
* 從啟動下載的可執行內容封鎖 JavaScript 或 VBScript
* 封鎖可能混淆的腳本執行
* 從電子郵件客戶程式和 web 郵件封鎖可執行檔內容
* 封鎖 Office communication application 建立子流程
* 封鎖從 USB 執行的不受信任和未簽署程式
* 透過 WMI 事件訂閱封鎖持久性
* 封鎖 Office 應用程式將程式碼注入其他程式
* 封鎖可執行檔，除非符合流行、age 或受信任的清單準則
* 封鎖來自 PSExec 和 WMI 命令的進程建立
* 從 Windows local security 機關子系統封鎖認證竊取（lsass.exe）
* 封鎖 Office 宏的 WIN32 API 呼叫


## <a name="we-want-to-hear-from-you"></a>我們想要聽到您的來信

如果您有任何問題，請在[安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社區中公佈，以告知我們。 我們正在監視社區，並會提供協助。

