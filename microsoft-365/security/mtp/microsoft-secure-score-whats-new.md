---
title: Microsoft 安全分數的新增功能
description: 說明 Microsoft 365 安全性中心中的 Microsoft 安全分數發生的新變更。
keywords: Microsoft 安全分數， 安全分數， Office 365 安全分數， Microsoft 安全性分數， microsoft 365 資訊安全中心
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
ms.openlocfilehash: 039ec1c3f9b0ba233f950d11b9d58be341b28121
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930591"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft 安全分數的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

為了讓 Microsoft Secure Score 更代表您的安全性工作，我們做了一些變更。 若要瞭解已規劃的變更，請參閱 [Microsoft 安全分數將提供哪些專案？](microsoft-secure-score-whats-coming.md)

您可以在 Microsoft https://security.microsoft.com/securescore [365](overview-security-center.md)資訊安全中心找到 Microsoft 安全分數。

## <a name="january-2021"></a>2021 年 1 月

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>新增我們針對 Microsoft Teams 的第一個安全性建議

Microsoft Teams 客戶會看到「限制匿名使用者加入會議」，做為安全分數中的新改進動作。

## <a name="december-2020"></a>2020 年 12 月

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>針對 Microsoft Defender for Endpoint 新增六個帳戶相關改進動作 (Microsoft Defender ATP) ：

- 將密碼長度最小為 14 個字元以上
- 將強制密碼歷程記錄設定為 (24) >
- 將密碼年齡上限設定為 60 天以下，但不要設定為 0
- 將 '最低密碼年齡' 設定為 '1 天或 (天) '
- 停用內建的系統管理員帳戶
- 停用內建的來賓帳戶

## <a name="november-2020"></a>2020 年 11 月

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>已透過安全分數移除建立 ServiceNow 票證的能力 

不再提供透過安全分數建立 ServiceNow 票證的能力> **共用服務視窗** 。 感謝您的意見和持續支援，我們決定接下來的步驟。

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>針對 Microsoft Defender for Endpoint (先前是 Microsoft Defender ATP 的三個服務相關改進) ：

- 修正未標出之 Windows 服務的服務路徑
- 將服務可執行路徑變更為一般受保護的位置
- 變更服務帳戶以避免 Windows 登錄中的緩存密碼

## <a name="october-2020"></a>2020 年 10 月

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>移除與 Microsoft Defender for Endpoint 相關的改進動作

- 將 Microsoft Defender SmartScreen Windows 市集應用程式內容檢查設為警告

## <a name="august-2020"></a>2020年 8月

### <a name="updated-improvement-action-for-azure-active-directory"></a>Azure Active Directory 的更新改進動作

- 啟用封鎖舊版驗證的策略

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>與身分識別安全分數和圖形 API 不相容

在最新發佈的 Microsoft 安全分數中，已推出改良的計分模型。 這些變更允許您以更有彈性且更精確的方式查看安全性工作。 不過，這些更新已讓 Microsoft 安全分數暫時與身分識別安全分數和圖形 API 不相容。

身分識別安全分數和圖形 API 會一同採用新的計分模型。 在此之前，客戶會看到 Microsoft 安全分數、身分識別安全分數和圖形 API 報告的成績有差異。 對於造成不便，我們深感抱歉，並且正努力確保未來這些體驗能更相容。

## <a name="updated-improvement-actions"></a>已更新改進動作

- 已新增 Azure Active Directory 改進動作
- 已針對身分識別改進動作新增 Microsoft Defender
- 支援 Microsoft Defender 的端點 [威脅&管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 安全性建議
    - 現在提供由 TVM 提供的所有已發行安全性建議

## <a name="updated-interface-and-functionality"></a>更新的介面和功能

* C們所有新的計量和趨勢視圖，以及潛在客戶層級討論
* 追蹤和基準分數的新功能
* 針對分數回歸進行更好的追蹤及理解
* 篩選、標記、搜尋和分組您的改進動作
* 使用分數預測和計畫的行動來達成您的未來目標
* 以及更多功能！

## <a name="we-want-to-hear-from-you"></a>我們想知道您的想法

如有任何問題，請張貼在安全性、隱私權和合規性& [告訴我們](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。 我們正在監控社群，並且會為您提供協助。

## <a name="related-resources"></a>相關資源

- [評估您的安全性狀態](microsoft-secure-score-improvement-actions.md)
- [追蹤您的 Microsoft 安全分數記錄並達成目標](microsoft-secure-score-history-metrics-trends.md)
- [即將推出的功能](microsoft-secure-score-whats-coming.md)
