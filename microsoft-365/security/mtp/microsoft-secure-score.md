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
ms.openlocfilehash: 212cefebfa3b4954f30d114419f82a5862e98a4f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094795"
---
# <a name="microsoft-secure-score"></a>Microsoft 安全分數

Microsoft Secure 得分是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。 可在 https://security.microsoft.com/securescore [Microsoft 365 的安全性中心](overview-security-center.md)找到該網址。

遵循安全分數建議可保護您的組織免受威脅。 透過 Microsoft 365 security center 中的集中式儀表板，組織可以監視及處理其 Microsoft 365 身分識別、資料、應用程式、裝置和基礎結構的安全性。

安全分數可協助組織：  

* 報告組織安全狀況的目前狀態。
* 提供探索性、可見度、指導方針和控制，以提升安全性狀況。  
* 請與基準進行比較，並建立 (KPIs) 的重要效能指標。

組織可以存取穩定的衡量方式和趨勢、與其他 Microsoft 產品的整合、與類似組織的分數比較，以及更多。 分數也可以反映協力廠商的解決方案如何解決建議的動作。

![安全分數首頁](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>運作方式

您可以在設定推薦的安全性功能、執行安全性相關工作，或使用協力廠商應用程式或軟體來解決改進動作中的點數，也可以指定其他的緩解。 有些改進動作只會在完全完成時給予點，有些的動作會在某些裝置或使用者完成時提供部分分數。 如果您無法或不想要制定其中一個 [改進] 動作，您可以選擇接受風險或剩餘風險。

不管授權為何，我們都會向您顯示一組完整的可能改進功能，讓您瞭解安全性的最佳作法，並提升您的分數。 您的絕對安全性狀態是以安全分數表示，不論貴組織擁有的產品授權為何都會保持不變。 請記住，安全性應該與可用性進行平衡，而不是每個建議都適用于您的環境。

您的分數會即時更新，以反映 [視覺化效果] 和 [改進動作] 頁面中顯示的資訊。 安全分數也會每天同步處理每個動作的取得點數的系統資料。

### <a name="key-scenarios"></a>主要案例

- [檢查您目前的分數](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [比較您的分數與您的組織](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [查看改進動作和決定行動計畫](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [啟動工作流程以進行調查或實施](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365 的安全性中心和 ServiceNow 整合](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>如何計分改進動作

每個改進動作都值得10點或更少。 大多數會以二進位方式計分：若您執行改進動作（如建立新原則或開啟特定設定），您會收到100% 的點數。 在其他改進動作中，點會指定為總設定的百分比。 例如，如果改進動作表明您透過多重要素驗證來保護您的所有使用者，而且您只會保護 50 100 的使用者，則會得到部分分數為5點 (50 protected/100 總計 * 10 最大值 = 5 pt 部分分數) 。

### <a name="products-included-in-secure-score"></a>安全分數中包含的產品

目前有 Microsoft 365 (的建議，包括 Exchange Online) 、Azure AD、Microsoft Defender ATP、Azure ATP 和 Cloud App Security。 即將推出其他安全性產品的建議。 建議不會涵蓋與各項產品相關聯的所有攻擊面，但也是一個很好的基準。 您也可以將改進動作標示為協力廠商或替代範圍的緩解。

### <a name="security-defaults"></a>安全性預設

Microsoft 安全分數已更新改進動作，以支援[Azure Active Directory 中的安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)，如此可讓您的組織使用預先設定的安全性設定進行常見的攻擊，以協助保護您的組織。

如果您開啟安全性預設值，您會獲得下列改進動作的完整得分：

- 確定所有使用者均可完成 (9 點之安全訪問的多重要素驗證) 
- 需要對管理角色進行 MFA (10 點) 
- 啟用原則以封鎖舊版驗證 (7 點) 

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
* 使用者系統管理員
* 服務管理員
* 安全性讀取者
* 安全性操作員
* 全域讀取者

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
* 封鎖從 Windows local security 機關子系統進行的認證竊取 ( # A0) 
* 封鎖 Office 宏的 WIN32 API 呼叫

## <a name="we-want-to-hear-from-you"></a>我們想要聽到您的來信

如果您有任何問題，請在[安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社區中公佈，以告知我們。 我們正在監視社區，並會提供協助。

## <a name="related-resources"></a>相關資源

- [深入瞭解您的安全性狀況](microsoft-secure-score-improvement-actions.md)
- [追蹤您的 Microsoft 安全分數記錄並符合目標](microsoft-secure-score-history-metrics-trends.md)
- [即將推出的功能](microsoft-secure-score-whats-coming.md)
