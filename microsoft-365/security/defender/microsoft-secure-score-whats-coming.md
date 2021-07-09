---
title: Microsoft 安全分數
description: 說明 Microsoft 365 security center 中的 Microsoft 安全評分的新變更。
keywords: microsoft 安全分數、安全分數、office 365 安全分數、microsoft security 得分、microsoft 365 安全性中心、改進動作
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 910eb16ad33555ca61875a346b50cea7e63b2220
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338550"
---
# <a name="whats-coming-to-microsoft-secure-score"></a>Microsoft 安全分數

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

您可以 https://security.microsoft.com/securescore 在「 [Microsoft 365 安全性中心](overview-security-center.md)」找到 Microsoft Secure 得分。

## <a name="proposed-changes"></a>建議變更

我們在近期進行一些變更，讓 [Microsoft 安全評分](microsoft-secure-score.md) 成為安全狀況的更好代表，並提高可用性。 您的分數和可能的最大分數可能會有所變更。

### <a name="july-2021"></a>2021年7月

#### <a name="add-improvement-action-related-to-microsoft-teams"></a>新增與 Microsoft Teams 相關的改進動作

- 限制撥入使用者繞過會議會議廳。
- 限制外部參與者在 Teams 會議中擁有控制權。
- 限制匿名使用者開始 Teams 會議。
- 需要 Teams 會議中設定大廳。
- 設定允許在 Teams 會議中出現的使用者。

#### <a name="add-improvement-action-related-to-microsoft-defender-for-endpoint"></a>新增與 Microsoft Defender for Endpoint 相關的改進動作
- 修正 Microsoft Defender for macOS 的端點感應器資料收集
- 修正 Microsoft Defender 對 macOS 的 Endpoint 受損通訊
- 設定 macOS 中的最小密碼長度為15或以上的字元
- 在 macOS 中將「強制密碼史 ' 設定為「24或以上的密碼 (s) 」
- 將「密碼最長存留期 ' 設定為 ' 90 或更少的天數，但在 macOS 中不是 0 '
- 將帳戶鎖定閥值設定為5或更低的 macOS
- 開啟 macOS 上的防火牆
- 啟用閘道管理員
- 啟用系統完整性保護 (SIP) 
- 啟用 FileVault 磁片加密
- 將畫面設定為在 macOS 中的屏保程式開始時鎖定
- 確定屏保程式已設定為在 macOS 20 分鐘以內開始
- 安全主資料夾
- 開啟 macOS 的 Microsoft Defender 防毒軟體即時保護
- 在封鎖模式中開啟 macOS 的 Microsoft Defender 防毒軟體 PUA 保護
- 為 macOS 啟用 Microsoft Defender 防毒軟體雲端傳送保護
- 更新 macOS 的 Microsoft Defender 防毒軟體定義
- 修正 Microsoft Defender for Linux 的 Endpoint 感應器資料收集
- 修正 Microsoft Defender 以取得 Linux 的 Endpoint 受損通訊
- 無限制存取帳戶
- 開啟對 Linux Microsoft Defender 防毒軟體即時保護
- 開啟 Linux 的封鎖模式中的 Microsoft Defender 防毒軟體 PUA 保護
- 為 Linux 啟用 Microsoft Defender 防毒軟體雲端傳送保護
- 更新 Linux 的 Microsoft Defender 防毒軟體定義



## <a name="related-resources"></a>相關資源

- [Microsoft 安全評分概述](microsoft-secure-score.md)
- [評估您的安全性狀態](microsoft-secure-score-improvement-actions.md)
- [追蹤您的 Microsoft 安全分數記錄並符合目標](microsoft-secure-score-history-metrics-trends.md)
- [新功能](microsoft-secure-score-whats-new.md)
