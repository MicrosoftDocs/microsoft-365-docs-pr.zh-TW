---
title: Microsoft 安全分數
description: 說明 microsoft 365 security center 中的 Microsoft Secure 得分、如何計算詳細資料，以及安全性管理員可以預期的情況。
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
ms.openlocfilehash: f70d2f601dfb697d8affa8bb47148f6e454c5d8e
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541092"
---
# <a name="microsoft-secure-score"></a>Microsoft 安全分數

Microsoft Secure 得分是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。 遵循安全性分數建議可保護您的組織免受威脅。 透過 Microsoft 365 security center 中的集中式儀表板，組織可以監視及處理其 Microsoft 365 身分識別、資料、應用程式、裝置和基礎結構的安全性。

安全分數可協助組織：

* 報告組織安全狀況的目前狀態。
* 提供探索性、可見度、指導方針和控制，以提升安全性狀況。  
* 與基準進行比較，並建立關鍵效能指標（KPIs）。

組織可以存取穩定的衡量方式和趨勢、與其他 Microsoft 產品的整合、與類似組織的分數比較，以及更多。 分數也可以反映協力廠商的解決方案如何解決建議的動作。

此外，您可以透過[Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)來存取您的建議和評分。 深入瞭解[安全分數資源類型](https://go.microsoft.com/fwlink/?linkid=2092996)。

## <a name="how-it-works"></a>運作方式

您可以在設定建議的安全性功能、執行安全性相關工作（如查看報告），或使用協力廠商應用程式或軟體解決改進動作的情況下，取得點數。 有些改進動作只會在完全完成時給予點，有些的動作會在某些裝置或使用者完成時提供部分分數。

不管授權為何，我們都會向您顯示一組完整的可能改進功能，讓您瞭解安全性的最佳作法，並提升您的分數。 您的絕對安全性狀態是以安全分數表示，不論貴組織擁有的產品授權為何都會保持不變。 請記住，安全性應該與可用性進行平衡，而不是每個建議都適用于您的環境。

您的分數會即時更新，以反映 [視覺化效果] 和 [改進動作] 頁面中顯示的資訊。 安全分數也會每天同步處理每個動作的取得點數的系統資料。

### <a name="how-improvement-actions-are-scored"></a>如何計分改進動作

大多數會以二進位方式計分：若您執行改進動作（如建立新原則或開啟特定設定），您會收到100% 的點數。 在其他改進動作中，點會指定為總設定的百分比。 例如，如果改進的動作指出您使用多重要素驗證來保護所有使用者時取得30點，而且您只會保護 100 5% 以上的使用者，則會得到大約2點的部分分數（5個 protected/100 總計 * 30 最大值 = 2 pt 部分分數）。

### <a name="products-included-in-secure-score"></a>安全分數中包含的產品

目前有 Office 365 的建議（包括 SharePoint Online、Exchange Online、商務 OneDrive、Microsoft 資訊保護等等）、Azure AD 和 Cloud App Security。 即將推出其他安全性產品（如 Azure ATP 和 Microsoft Defender ATP）的建議。 建議不會涵蓋與各項產品相關聯的所有攻擊面，但也是一個很好的基準。 您也可以將改進動作標示為協力廠商所涵蓋的範圍。

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

* SecurityEvents Read。 All （唯讀角色）
* ReadWrite SecurityEvents （適用于讀取和寫入角色）

## <a name="gain-visibility-into-your-security-posture"></a>深入瞭解您的安全性狀況

為了協助您更快速地取得所需資訊，Microsoft 改進的動作會組織成群組：

* Identity （Azure AD 帳戶 & 角色）
* 資料（Microsoft 資訊保護）
* 裝置（現在沒有任何改進動作）
* 應用程式（電子郵件和雲端應用程式，包括 Office 365 和 Microsoft Cloud App Security）
* 基礎結構（現在沒有任何改進動作）

在 [Microsoft Secure 得分一覽] 頁面中，您可以看到各群組之間的點數如何分割，以及哪些點可供使用。 [一覽表] 頁面也是取得整體總分、您的安全分數與基準比較之歷史趨勢的完整視圖，以及可以採取以改善評分的優先改進動作的位置。

![安全分數主頁](../../media/secure-score/homepage-original.png)
*圖1： Microsoft Secure 得分一覽頁面*

## <a name="take-action-to-improve-your-score"></a>採取動作以提升您的分數

[改進動作] 索引標籤會列出解決可能攻擊面的安全性建議，及其狀態（已完成，尚未完成，已透過協力廠商解決，且被忽略）。 您可以搜尋、篩選和群組所有的「改進」動作。

### <a name="ranking"></a>排名

排名是根據剩下的剩餘點數、實施難度、使用者影響和複雜性而定。 最高排名的「改進」動作具有很大的分數，但有低難度、使用者影響和複雜性。

### <a name="actions"></a>動作

標為 [未評分] 的動作不會由 Microsoft 安全分數追蹤。 您仍然可以採取動作，但完成這些動作不會影響您的分數。 如果您未來的動作成為 Microsoft 安全得分，而且您已完成，您的安全分數會自動反映變更。

當您選取特定的 [改進] 動作時，會出現 [飛出]。 若要完成此動作，您有幾個選項：

1. 選取 [**查看設定**] 以進入設定畫面，然後進行變更。 然後，您可以在飛出的最上方看到所要採取動作的點。最多可能需要24小時才能更新點數。

2. 選取 [**透過協力廠商解決**]，因為改進動作已經由協力廠商應用程式或軟體所定址。 您可以取得行動的價值，讓您的安全分數更好地反映整體的安全性狀況。 如果協力廠商不再涵蓋該控制項，您可以將 [改進] 動作標示為 [未完成]。 請記住，如果改進動作標示為透過協力廠商解決，則 Microsoft 無法查看是否符合評分需求。

3. 選取 [**略**過]，因為您已決定接受風險，而不會制定「改進」動作。 一旦您忽略 [改進] 動作，您可以達到的安全分數點總數即會減少。 您可以在歷史記錄中查看此動作，也可以隨時復原。

4. 選取 [**檢查**]，因為改進動作需要您定期檢查環境的一部分，以取得及保留點數。 例如，應每週複查信箱轉寄規則，以確保資料未從您的網路挾帶。 您不需要進行任何變更，但必須執行動作。 如果您定期檢查規則，您會收到點數。 如果不是，則會降低分數。

![安全分數改進動作範例](../../media/secure-score/secure-score1x450.png) ![安全分數評審改進動作範例](../../media/secure-score/secure-score2x450.png)

*圖 2 & 3：改善動作 flyouts*

## <a name="monitor-improvements-over-time"></a>監視隨時間的改進

您可以在 [**記錄**] 索引標籤中，在一段時間內，查看組織的分數圖表。在圖形下方會列出所選取時間範圍內所執行的所有動作，以及其屬性，例如結果點和類別。 您可以自訂日期範圍及依類別篩選。

## <a name="risk-awareness"></a>風險認知

Microsoft Secure 得分是根據系統設定、使用者行為和其他安全性相關度量的安全性狀態的數值摘要;這不是系統或資料被破壞的可能性的絕對度量。 相反地，它代表您已在 Microsoft 環境中採用安全性控制的程度，可協助抵消遭破壞的風險。 沒有任何線上服務完全避免安全缺口，安全分數不得以任何方式轉譯為保證安全性破壞。

## <a name="whats-new"></a>新功能

若要讓 Microsoft 安全評分為您安全性狀況的更好代表，我們進行了一些變更。

若要深入瞭解規劃的變更，請參閱[Microsoft Secure 得分中的內容？](microsoft-secure-score-whats-coming.md)

### <a name="march-2020"></a>2020 年 3 月

#### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>支援 Azure AD 改進動作的安全性預設值

Microsoft Secure 得分會更新改進動作，以支援[AZURE AD 中的安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)，如此可讓您的組織使用預先設定的常見攻擊安全性設定，以協助保護您的組織。

這會影響下列改進動作：

- 確定所有使用者均可完成安全存取的多重要素驗證
- 需要對管理角色進行 MFA
- 啟用原則以封鎖舊版驗證

#### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>移除不符合可靠度量期望的改進動作，或沒有提供安全狀況的有用標記法

為了確保 Microsoft 安全分數有意義，且每個改進動作都有意義且可靠，我們正在移除下列改進動作。

- 將使用者檔儲存在商務 OneDrive 中
- 設定 Office 365 ATP 安全附件原則
- 設定 Office 365 安全連結以驗證 URLs
- 不允許信箱委派
- 允許網站和檔的匿名來賓共用連結
- 開啟 Cloud App Security 主控台
- 設定外部共用連結的到期時間
- 開啟審計資料記錄
- 探索危險且不相容的陰影 IT 應用程式
- 檢查許可權 & 會封鎖連接至您環境的危險 OAuth 應用程式
- 設定 SharePoint 線上文件庫的版本設定
- 刪除/封鎖過去30天內未使用的帳戶
- 指定少於5個全域系統管理員

#### <a name="removed-not-scored-improvement-actions"></a>移除「未計分」的改進動作

安全分數的原則之一是，分數應該是標準化的，且與的功能非常輕鬆。 具有不具可度量或具可操作性的改進動作已導致混淆。 只有在每個建議都會對分數有明確影響時，Microsoft 安全評分才有意義。 不計分的改善動作不可度量。  

基於這些原因，已移除所有未計分的改善動作。 您的元件不需要任何動作。

#### <a name="removed-device-improvement-actions"></a>移除裝置改進動作

評估 [改進動作] 的 Microsoft Secure 得分裝置類別之後，它決定這些動作目前評估原則狀態，而不是裝置的設定狀態。 因為設定會直接與安全性狀況相關聯，所以現有的裝置動作決定不完全代表組織狀況。  當我們運作時，將會移除裝置類別中目前的動作，以提供一組建議，以直接使用診斷資料，以更完整地代表裝置安全狀況。

已移除下列改進動作：

- 啟用 Microsoft Intune 行動裝置管理
- 建立適用于 Android 的 Microsoft Intune 符合性原則
- 建立適用于 Android 的 Microsoft Intune 符合性原則
- 建立適用于 Android 的 Microsoft Intune 應用程式保護原則
- 為 iOS 建立 Microsoft Intune 應用程式保護原則
- 標示未指派為不相容的 Microsoft Intune 符合性原則的裝置
- 為 iOS 建立 Microsoft Intune 符合性原則
- 為 macOS 建立 Microsoft Intune 符合性原則
- 建立適用于 Windows 的 Microsoft Intune 符合性原則
- 建立適用于 Android 的 Microsoft Intune 設定檔
- 建立適用于 Android 的 Microsoft Intune 設定檔
- 為 macOS 建立 Microsoft Intune 設定檔
- 為 iOS 建立 Microsoft Intune 設定檔
- 建立 Windows 的 Microsoft Intune 設定檔
- 在 Microsoft Intune 中啟用增強型 jailbreak 偵測
- 需要修補所有裝置，並已啟用防病毒及防火牆
- 啟用 Windows Defender ATP 整合至 Microsoft Intune
- 建立 Microsoft Intune Windows 資訊保護原則
- 要求所有裝置都具有高級安全性設定
- 每週複查封鎖的裝置報告

#### <a name="mfa-improvement-action-updates"></a>MFA 改進動作更新

為了反映公司在套用與業務搭配運作的原則時，是否需要確保 upmost 安全性，Microsoft 安全分數已移除三個改進動作（圍繞多重要素驗證），並新增兩個動作。

已移除改進動作：

- 為多重要素驗證註冊所有使用者
- 需要對所有使用者進行 MFA
- Azure AD 特權角色需要 MFA

新增改進動作：

- 確定所有使用者均可完成安全存取的多重要素驗證
- 需要對管理角色進行 MFA

 這些新的改進動作需要在您的目錄上登錄使用者或系統管理員以進行多重要素驗證（MFA），並建立符合組織需求的適當原則集合。 主要目標具有彈性，可確保所有使用者和系統管理員都能使用多個因素或以風險為基礎的身分識別驗證提示進行驗證。 這可以採取多種原則套用範圍決策，或設定安全性預設值（即將推出3月16日），讓 Microsoft 決定何時對使用者進行 MFA 的質詢。

#### <a name="removed-review-improvement-actions"></a>已移除「複查」改進動作

安全分數的原則之一是，分數應該是標準化的，且與的功能非常輕鬆。 具有不具可度量或具可操作性的改進動作已導致混淆。 只有在每個建議都會對分數有明確影響時，其中一個 Microsoft 安全評分才有意義。 「審閱改進」動作與其他 [改進動作] 的標準不是度量。  

基於這些原因，所有需要審閱節奏的改進動作都會暫時移除。 您的元件不需要任何動作。

### <a name="preview-features"></a>預覽功能

[預覽版本](microsoft-secure-score-preview.md)中會包含下列功能：

* CISO 和潛在客戶層級討論的所有新的計量和趨勢視圖
* 追蹤和基準成績的新方法
* 更好地追蹤和監控分數回歸
* 篩選、標記、搜尋及群組您的改善動作
* 使用分數預測和規劃的動作來管理您的未來目標
* 簡化點數系統
* 還有更多！

## <a name="we-want-to-hear-from-you"></a>我們想要聽到您的來信

如果您有任何問題，請在[安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社區中公佈，以告知我們。 我們正在監視社區，並會提供協助。
