---
title: Microsoft 安全分數的新功能
description: 說明 microsoft 365 security center 中的 Microsoft Secure 得分發生了哪些新的變更。
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
ms.openlocfilehash: e31389705ddd8de4854a3477012d7fa90b78c7ee
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866892"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft 安全分數的新功能

若要讓 Microsoft 安全評分為您安全性狀況的更佳代表，我們進行了一些變更。 若要深入瞭解規劃的變更，請參閱 [Microsoft Secure 得分中的內容？](microsoft-secure-score-whats-coming.md)。

## <a name="july-2020"></a>2020 年 7 月

### <a name="adding-improvement-actions-for-azure-advanced-threat-protection"></a>新增 Azure 高級威脅防護的改進動作

- 有風險的側面移動路徑
- 不安全的帳戶屬性
- 在 Active Directory 信任上啟用安全性功能
- 從實體中移除不安全的 SID 歷程記錄屬性

## <a name="june-2020"></a>2020 年 6 月

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>已移除 Microsoft Defender 高級威脅防護的改進動作

* 開啟攻擊面減少規則

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>新增 Microsoft Defender 高級威脅防護的改進動作

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

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>不相容身分識別安全分數與圖形 API

在最近發行的 Microsoft Secure 得分中，已發佈一個已改進的計分模型。 這些變更可讓您更靈活且準確的安全性狀況的觀點。 不過，這些更新已讓 Microsoft 安全分數暫時不相容身分識別安全分數和圖形 API。

在時間內，身分識別安全分數和圖形 API 將採用新的計分模型。 在此之前，客戶會看到 Microsoft 安全評分、身分識別安全分數及圖形 API 所報告的分數差異。 我們對這項不便的任何不便深表歉意，而且正在運作，以確保未來的體驗更具相容性。

## <a name="updated-improvement-actions"></a>更新的改進動作

- 新增 Azure Active Directory 改進動作
- 新增 Azure 高級威脅防護改進動作
- 支援 Microsoft Defender ATP [威脅 & 弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 安全性建議
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
