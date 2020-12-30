---
title: Microsoft 安全分數
description: 說明 microsoft 365 security center 中的 Microsoft 安全分數、如何改善安全性狀態，以及安全性管理員可以預期的狀況。
keywords: microsoft 安全分數、安全分數、office 365 安全分數、microsoft security 得分、microsoft 365 安全性中心、改進動作
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
ms.openlocfilehash: 6e9dd214e53e3fdd601fe51e5522a3a24a7fd3d0
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/29/2020
ms.locfileid: "49737996"
---
# <a name="microsoft-secure-score"></a>Microsoft 安全分數

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure 得分是組織的安全性狀況度量，具有較高的數目，表示執行的改善動作越多。 可在 https://security.microsoft.com/securescore [Microsoft 365 的安全性中心](overview-security-center.md)找到該網址。

遵循安全分數建議可保護您的組織免受威脅。 在 Microsoft 365 安全中心的中央儀表板中，組織可以監視及處理其 Microsoft 365 身分識別、應用程式和裝置的安全性。

安全分數可協助組織：  

* 報告組織安全狀況的目前狀態。
* 提供探索性、可見度、指導方針和控制，以提升安全性狀況。  
* 請與基準進行比較，並建立 (KPIs) 的重要效能指標。

組織可以存取穩定的衡量方式和趨勢、與其他 Microsoft 產品的整合、與類似組織的分數比較，以及更多。 分數也可以反映協力廠商的解決方案如何解決建議的動作。

![安全分數首頁](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>運作方式

您會在下列動作中取得重點：

- 設定推薦的安全性功能
- 進行安全性相關工作
- 使用協力廠商應用程式或軟體解決改進動作，或以替代的方式緩解

有些改進動作只會在完全完成時提供積分。 有些是在某些裝置或使用者已完成時，有些點會產生部分點。 如果您無法或不想要制定其中一個 [改進] 動作，您可以選擇接受風險或剩餘風險。

如果您有其中一個支援的 Microsoft 產品的授權，您會看到這些產品的建議。 不管授權版、訂閱或計畫為何，我們都會向您展示產品的完整一組可能改進。 如此一來，您就可以瞭解安全性最佳作法，並改善您的分數。 不管您的組織擁有的特定產品授權為何，您的絕對安全性狀態（以安全分數表示）都會保持不變。 請記住，安全性應該與可用性進行平衡，而不是每個建議都適用于您的環境。

您的分數會即時更新，以反映 [視覺化效果] 和 [改進動作] 頁面中顯示的資訊。 安全分數也會每天同步處理每個動作的取得點數的系統資料。

### <a name="key-scenarios"></a>主要案例

- [檢查您目前的分數](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [比較您的分數與您的組織](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [查看改進動作和決定行動計畫](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [啟動工作流程以進行調查或實施](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>如何計分改進動作

每個改進動作都值得10點或更少，且最多會以二進位方式計分。 如果您執行改進動作（如建立新原則或開啟特定設定），您會收到100% 的點數。 在其他改進動作中，點會指定為總設定的百分比。

例如，「改進」動作表明您可以使用多重要素驗證來保護所有使用者，以取得10點。 您只會保護50的100使用者總數，因此您可以取得5點的部分分數 (50 protected/100 總計 * 10 最大值 = 5 pt) 。

### <a name="products-included-in-secure-score"></a>安全分數中包含的產品

目前，下列產品的建議如下：

- Microsoft 365 (包括 Exchange Online) 
- Azure Active Directory
- 適用於端點的 Microsoft Defender
- 適用於身分識別的 Microsoft Defender
- Cloud App Security

即將推出其他安全性產品的建議。 建議不涵蓋每項產品相關聯的所有攻擊面，但也是一個很好的基準。 您也可以將改進動作標示為協力廠商或替代範圍的緩解。

### <a name="security-defaults"></a>安全性預設

Microsoft Secure 得分已更新改進動作，以支援 [Azure Active Directory 中的安全性預設值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)，如此可讓您的組織使用預先設定的常見攻擊安全性設定，以協助保護您的組織。

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

* 技術支援管理員
* 使用者系統管理員
* 服務管理員
* 安全性讀取者
* 安全性操作員
* 全域讀取者

## <a name="risk-awareness"></a>風險認知

Microsoft Secure 得分是根據系統設定、使用者行為及其他安全性相關度量，以數位摘要的安全性狀況。 這不是系統或資料遭到破壞的可能性的絕對度量。 相反地，它代表您已在 Microsoft 環境中採用安全性控制的程度，可協助抵消遭破壞的風險。 任何線上服務都不會受到安全性違例的攻擊，安全分數不得以任何方式轉譯為保證安全性破壞。

## <a name="we-want-to-hear-from-you"></a>我們想知道您的想法

如果您有任何問題，請在 [安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社區中發佈以告知我們。 我們正在監視社區，並會提供協助。

## <a name="related-resources"></a>相關資源

- [評估您的安全性狀態](microsoft-secure-score-improvement-actions.md)
- [追蹤您的 Microsoft 安全分數記錄並符合目標](microsoft-secure-score-history-metrics-trends.md)
- [即將推出的功能](microsoft-secure-score-whats-coming.md)
- [新功能](microsoft-secure-score-whats-new.md)
