---
title: Microsoft 安全分數的新功能
description: 說明 microsoft 365 security center 中的 Microsoft Secure 得分發生了哪些新的變更。
keywords: microsoft 安全分數，安全分數，office 365 安全分數，microsoft security 得分，microsoft 365 security center
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
ms.openlocfilehash: 0ba3d7a5e46f7e0f8677ce2844c5551bf70739e3
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367105"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft 安全分數的新功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

若要讓 Microsoft 安全評分為您安全性狀況的更佳代表，我們進行了一些變更。 若要深入瞭解規劃的變更，請參閱 [Microsoft Secure 得分中的內容？](microsoft-secure-score-whats-coming.md)。

## <a name="november-2020"></a>2020年11月

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>在先前的 Microsoft Defender ATP) 中，為 Microsoft Defender for Endpoint (新增3個與服務相關的改進動作：

- 修正 Windows 服務的未加引號服務路徑
- 將服務可執行路徑變更為一般受保護的位置
- 變更服務帳戶以避免在 windows 登錄中快取密碼

## <a name="october-2020"></a>2020 年 10 月

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>移除與 Microsoft Defender for Endpoint 相關的改進動作

- 設定 Microsoft Defender SmartScreen Windows 應用程式 web 內容檢查以警告

## <a name="august-2020"></a>2020年 8月

### <a name="updated-improvement-action-for-azure-active-directory"></a>Azure Active Directory 的更新改進動作

- 啟用原則以封鎖舊版驗證

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>不相容身分識別安全分數與圖形 API

在最近發行的 Microsoft Secure 得分中，已發佈一個已改進的計分模型。 這些變更可讓您更靈活且準確的安全性狀況的觀點。 不過，這些更新已讓 Microsoft 安全分數暫時不相容身分識別安全分數和圖形 API。

在時間內，身分識別安全分數和圖形 API 將採用新的計分模型。 在此之前，客戶會看到 Microsoft 安全評分、身分識別安全分數及圖形 API 所報告的分數差異。 我們對這項不便的任何不便深表歉意，而且正在運作，以確保未來的體驗更具相容性。

## <a name="updated-improvement-actions"></a>更新的改進動作

- 新增 Azure Active Directory 改進動作
- 新增 Microsoft Defender 以進行身分識別改進動作
- 支援 Microsoft Defender for Endpoint [威脅 & 弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 安全性建議
    - 現在提供 TVM 提供的所有發行安全性建議

## <a name="updated-interface-and-functionality"></a>更新的介面及功能

* CISO 和潛在客戶層級討論的所有新的計量和趨勢視圖
* 追蹤和基準成績的新方法
* 更好地追蹤和瞭解分數回歸
* 篩選、標記、搜尋及群組您的改善動作
* 使用分數預測和規劃的動作來管理您的未來目標
* 還有更多！

## <a name="we-want-to-hear-from-you"></a>我們想要聽到您的來信

如果您有任何問題，請在 [安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社區中發佈以告知我們。 我們正在監視社區，並會提供協助。

## <a name="related-resources"></a>相關資源

- [評估您的安全性狀態](microsoft-secure-score-improvement-actions.md)
- [追蹤您的 Microsoft 安全分數記錄並符合目標](microsoft-secure-score-history-metrics-trends.md)
- [即將推出的功能](microsoft-secure-score-whats-coming.md)
