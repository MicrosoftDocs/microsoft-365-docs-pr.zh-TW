---
title: Microsoft 安全分數
description: 說明 Microsoft 365 資訊安全中心的 Microsoft 安全分數、如何改善安全性工作，以及安全性系統管理員可預期的結果。
keywords: Microsoft 安全分數， 安全分數， Office 365 安全分數， Microsoft 安全性分數， Microsoft 365 安全性中心， 改進動作
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: a0f4307cc0ed42a8ed53cdeefdb0a7b32eb36d35
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930579"
---
# <a name="microsoft-secure-score"></a>Microsoft 安全分數

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 安全分數是組織安全性措施的度量，數位越高，表示已採取更多改進動作。 您可以在 https://security.microsoft.com/securescore [Microsoft 365 資訊安全中心找到。](overview-security-center.md)

遵循安全分數建議可保護貴組織不受威脅。 組織可以從 Microsoft 365 資訊安全中心的集中式儀表板監控及處理其 Microsoft 365 身分驗證、應用程式和裝置的安全性。

安全分數可協助組織：  

* 報告組織安全性措施的目前狀態。
* 提供可探索性、可見度、指引及控制，以改善其安全性工作。  
* 與 kpi 比較並建立 KPI (關鍵) 。

組織可存取強大的計量和趨勢視覺效果、與其他 Microsoft 產品整合、比對類似組織分數，以及更多功能。 分數也會反映在協力廠商解決方案已解決建議動作時。

![安全分數首頁](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>運作方式

您獲得下列動作的點數：

- 正在安裝建議的安全性功能
- 執行安全性相關工作
- 使用協力廠商應用程式或軟體或替代的降低風險解決改進動作

部分改進動作只會在完全完成時提供點數。 如果部分裝置或使用者已完成部分點數，系統會提供部分點數。 如果您無法或不想執行其中一個改進動作，可以選擇接受風險或剩餘風險。

如果您擁有其中一個支援的 Microsoft 產品授權，則會看到這些產品的建議。 不論授權版本、訂閱或方案如何，我們都會顯示完整的產品改良功能。 如此一來，您可以瞭解安全性最佳作法並改善您的分數。 無論貴組織擁有特定產品哪些授權，絕對的安全性絕對值會保持相同，以安全分數表示。 請記住，安全性應該與可用性保持平衡，而並非每個建議都適用于您的環境。

您的分數會即時更新，以反映視覺效果和改良動作頁面中呈現的資訊。 安全分數也會每天同步處理，以接收有關您每項動作的已達成分數的系統資料。

### <a name="key-scenarios"></a>主要案例

- [檢查您目前的分數](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [比較您的分數與像您這樣的組織](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [查看改進動作並決定行動計畫](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [啟動要調查或實施的資料流程](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>如何評分改進動作

每個改進動作都值 10 分以下，且大部分都是以二進位方式打分數。 如果您執行改進動作 ，例如建立新政策或開啟特定設定，則 100% 的分數會獲得。 針對其他改進動作，點數會以在總組數的百分比中提供。

例如，改進動作會指出，使用多重要素驗證來保護所有使用者，可得到 10 個點數。 您只有 100 名使用者中的 50 位受到保護，因此您只得到 5 分的部分分數 (50 個受保護的 / 100 個總分 * 10 個最大 pts = 5 個 pts) 。

### <a name="products-included-in-secure-score"></a>安全分數中包含的產品

目前提供下列產品的建議：

- Microsoft 365 (包括 Exchange Online) 
- Azure Active Directory
- 適用於端點的 Microsoft Defender
- 適用於身分識別的 Microsoft Defender
- Cloud App Security

我們即將推出其他安全性產品的建議。 建議不會涵蓋所有與每個產品相關的攻擊面，但它們是不錯的比較基準。 您也可以將改進動作標記為協力廠商涵蓋或替代的風險降低。

### <a name="security-defaults"></a>安全性預設

Microsoft 安全分數已更新為支援 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)中安全性預設值的改進動作，這可協助貴組織使用預先設定的安全性設定來保護常見的攻擊。

如果您開啟安全性預設值，下列改進動作會獲得完整分數：

- 確保所有使用者都可以完成多重要素驗證，以安全存取 (9 點) 
- 系統管理角色需要 MFA (10 點) 
- 啟用封鎖舊有 7 點驗證 (驗證) 

>[!IMPORTANT]
>安全性預設值包含的安全性功能，可提供類似「登錄風險策略」和「使用者風險政策」改進動作的安全性。 建議您將原則狀態更新為「透過替代的安全降低解決方案解決」，而不是在安全性預設值上設定這些原則。

## <a name="required-permissions"></a>必要的權限

若要擁有存取 Microsoft 安全分數的許可權，您必須在 Azure Active Directory 中指派下列其中一個角色。

### <a name="read-and-write-roles"></a>讀取和寫入角色

您可以變更內容，並直接與安全分數互動。 您也可以指派唯讀存取權給其他使用者。

* 全域管理員
* 安全性系統管理員
* Exchange 系統管理員
* SharePoint 系統管理員
* 帳戶管理員

### <a name="read-only-roles"></a>唯讀角色

使用唯讀存取時，您無法編輯狀態或改進動作的備註、編輯分數區域或編輯自訂比較。

* 技術支援管理員
* 使用者系統管理員
* 服務管理員
* 安全性讀取者
* 安全性操作員
* 全域讀取者

## <a name="risk-awareness"></a>風險認知

Microsoft 安全分數是安全性工作的數位摘要，是以系統組態、使用者行為及其他安全性相關度量為基礎。 並非絕對能測量系統或資料可能會外泄的可能性。 相反地，這代表您于 Microsoft 環境中採用安全性控制項的程度，可協助位移遭到入侵的風險。 任何線上服務都不受安全性威脅，安全分數不應視為以任何方式防範安全性漏洞的保證。

## <a name="we-want-to-hear-from-you"></a>我們想知道您的想法

如有任何問題，請張貼在安全性、隱私權和合規性& [告訴我們](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。 我們正在監控社群，並且會為您提供協助。

## <a name="related-resources"></a>相關資源

- [評估您的安全性狀態](microsoft-secure-score-improvement-actions.md)
- [追蹤您的 Microsoft 安全分數記錄並達成目標](microsoft-secure-score-history-metrics-trends.md)
- [即將推出的功能](microsoft-secure-score-whats-coming.md)
- [新功能](microsoft-secure-score-whats-new.md)
