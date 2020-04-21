---
title: 安全性與合規性中心內的郵件流程深入解析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 系統管理員可以深入瞭解安全性 & 規範中心內的郵件流程儀表板。
ms.openlocfilehash: 64bf1f2af967f841cd4c21be19fce914df136815
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630464"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>安全性與合規性中心內的郵件流程深入解析

系統管理員可以使用安全性 & 合規性中心內的郵件流程儀表板來探索趨勢、深入探索，並採取行動以修正組織中與郵件流程相關的問題。

郵件流程儀表板中提供的洞察力、報告和構件如下：

- [郵件流程圖報告](mfi-mail-flow-map-report.md)

- [網域郵件流程狀態洞察力](mfi-domain-mail-flow-status-insight.md)

- [SMTP 驗證用戶端報告](mfi-smtp-auth-clients-report.md)

- [寄件者網域洞察力](mfi-sender-domain-insight.md)

- [未傳遞回報](mfi-non-delivery-report.md)

- [非公認的網域報告](mfi-non-accepted-domain-report.md)

- [外寄和內送的郵件流程](mfi-outbound-and-inbound-mail-flow.md)

- [佇列的警示和佇列](mfi-queue-alerts-and-queues.md)

- [自動轉寄訊息的報告](mfi-auto-forwarded-messages-report.md)

- [郵件迴圈深入解析](mfi-mail-loop-insight.md)

- [緩慢的郵件流程規則深入解析](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>查看郵件流程儀表板所需的許可權

您可以在郵件流程儀表板上進行下列作業：

- **全域系統管理員**角色的成員。

- **Exchange 系統管理員**角色的成員。

- 安全性 & 合規性中心內的**郵件流程系統管理員角色**的成員。 如果此角色明確指派給非全域管理員或 Exchange 系統管理員角色成員的使用者：

  - 使用者必須直接登入安全性 & 合規性中心[https://protection.office.com](https://protection.office.com)。

  - 使用者只具有郵件流程儀表板的唯讀許可權。

  - 使用者將無法存取 Microsoft 365 系統管理中心。

如需全域系統管理員角色的詳細資訊，請參閱[關於 Microsoft 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。

如需將安全性 & 規範中心角色指派給使用者的詳細資訊，請參閱[授與使用者存取安全性 & 規範中心](grant-access-to-the-security-and-compliance-center.md)。

## <a name="where-to-find-the-mail-flow-dashboard"></a>哪裡可以找到郵件流程儀表板

1. 移至安全性 & 合規性中心， [https://protection.office.com](https://protection.office.com)網址為。

2. 展開 [**郵件流程**]，然後選取 [**儀表板**]。

   ![安全性 & 規範中心內的郵件流程儀表板](../../media/mail-flow-dashboard-v2.png)
