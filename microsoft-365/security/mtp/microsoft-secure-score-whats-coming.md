---
title: 什麼 Microsoft 安全分數即將？
description: 說明 Microsoft 安全分數 Microsoft 365 安全性中心、 詳細資料的計算方式，以及安全性系統管理員可以預期。
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365，安全分數資訊安全中心、 改進動作
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
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372001"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>什麼 Microsoft 安全分數即將？

若要讓 Microsoft 安全分數較佳的安全性狀態代表並改善可用性，我們會在不久的將來進行一些變更。 您的成績和最大可能分數會變更。 不過，這並不表示您的安全性狀態變更。

若要深入了解最近的變更，請參閱[What's new in Microsoft 安全分數？](microsoft-secure-score.md#whats-new)

## <a name="march-16th-2020"></a>16 2020 年 3 月

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>移除不符合預期可靠的度量單位，或沒有提供實用的安全性狀態表示改進動作

若要確保 Microsoft 安全分數才有意義，以及改進的每一個動作是可以測量且可靠，我們會移除下列改進動作。

- 商務用 OneDrive 中儲存使用者文件
- 設定 Office 365 ATP 安全附件原則
- 若要確認 Url 設定 Office 365 安全連結
- 不允許 [信箱委派]
- 允許匿名來賓共用網站和文件的連結
- 開啟雲端 App 安全性主控台
- 設定外部共用連結的到期時間

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Azure AD 改進動作支援安全的預設值

Microsoft 安全分數會更新改進動作來支援[Azure AD 中預設的安全性](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)，方便大家來協助保護您的組織使用的常見的攻擊的預先設定的安全性設定。

它會影響下列改進動作：

- 確定所有的使用者可以完成的安全存取多重要素驗證
- 需要 MFA 的系統管理角色
- 啟用原則，以封鎖舊版驗證
