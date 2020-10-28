---
title: Microsoft 安全分數
description: 說明 Microsoft 365 security center 中的 Microsoft 安全評分的新變更。
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
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779245"
---
# <a name="whats-coming-to-microsoft-secure-score"></a>Microsoft 安全分數

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

我們在近期進行一些變更，讓 [Microsoft 安全評分](microsoft-secure-score.md) 成為安全狀況的更好代表，並提高可用性。 您的分數和可能的最大分數可能會有所變更。

## <a name="proposed-changes"></a>建議變更

### <a name="november-2020"></a>2020年11月

移到 **> ServiceNow** 中，移除透過安全分數建立 ServiceNow 入場券的功能。

- ServiceNow 連接器的預覽期間結束。 2020的結尾將不再提供這項功能。 感謝您的意見反應，並在我們決定接下來的步驟時繼續支援。

在先前的 Microsoft Defender ATP) 中，新增與 Microsoft Defender for Endpoint (相關的18個改進動作：

攻擊面減少 (ASR) 相關建議：
- 從電子郵件客戶程式和 web 郵件封鎖可執行檔內容
- 封鎖所有 Office 應用程式以建立子流程
- 封鎖 Office 應用程式建立可執行檔內容
- 封鎖 Office 應用程式將程式碼注入其他程式
- 從啟動下載的可執行內容封鎖 JavaScript 或 VBScript
- 封鎖可能混淆的腳本執行
- 封鎖 Office 宏的 WIN32 API 呼叫
- 封鎖可執行檔，除非符合流行、age 或受信任的清單準則
- 使用勒索軟體的高級防護
- 封鎖從 Windows local security 機關子系統進行的認證竊取 ( # A0) 
- 封鎖來自 PSExec 和 WMI 命令的進程建立
- 封鎖從 USB 執行的不受信任和未簽署程式
- 封鎖 Office communication application 建立子流程
- 封鎖 Adobe Reader，以建立子流程
- 透過 WMI 事件訂閱封鎖持久性

服務相關建議：
- 修正 Windows 服務的未加引號服務路徑
- 將服務可執行路徑變更為一般受保護的位置
- 變更服務帳戶以避免在 windows 登錄中快取密碼

## <a name="related-resources"></a>相關資源

- [Microsoft 安全評分概述](microsoft-secure-score.md)
- [評估您的安全性狀態](microsoft-secure-score-improvement-actions.md)
- [追蹤您的 Microsoft 安全分數記錄並符合目標](microsoft-secure-score-history-metrics-trends.md)
- [新功能](microsoft-secure-score-whats-new.md)
