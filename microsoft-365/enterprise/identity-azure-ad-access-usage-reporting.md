---
title: 步驟 13：監控租用戶和登入活動
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定 Azure AD 存取和使用情況報告。
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866105"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a>步驟 13：監控租用戶和登入活動

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步驟中，您將會使用 Azure AD 報告檢視稽核記錄和登入活動。兩種類型的報告皆可供使用。

**稽核記錄活動報告**會報告 Azure AD 租用戶中執行的每項工作歷程記錄。這份報告會回答如以下的問題：

- 哪個人員已將某人新增至系統管理群組？
- 哪個使用者正在登入特定的應用程式？
- 密碼重設的發生次數？

**登入活動報告**會報告哪個人員執行稽核記錄報告所報告的工作。這份報告會回答如以下的問題：

- 針對調查中的特定使用者，他們的登入模式是什麼？
- 一天、週或月的登入活動量為何？
- 這些登入嘗試不成功的次數有多少，且是針對哪一個帳戶？

如需報告以及如何存取他們的詳細資訊，請參閱 [Azure Active Directory 報告](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)。

在此步驟的結果中，您將了解這些報告以及如何使用這些報告來深入了解用於規劃與安全性目的之 Azure AD 事件與活動。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [允許使用者建立及管理自己的群組](identity-self-service-group-management.md) |
