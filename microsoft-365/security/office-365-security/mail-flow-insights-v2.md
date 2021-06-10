---
title: 郵件流程儀表板中的郵件流程洞察力
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 系統管理員可以深入瞭解安全性 & 規範中心的郵件流程儀表板中提供的真知灼見和報告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 39f7b43db62fd19f7500972a3016fdd8dd0875b6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203788"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>安全性與合規性中心內的郵件流程深入解析

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

系統管理員可以使用安全性 & 合規性中心內的郵件流程儀表板來探索趨勢、深入資訊，並採取行動來修正組織中與郵件流程相關的問題。

![安全性 & 規範中心內的郵件流程儀表板](../../media/mail-flow-dashboard-v2.png)

可用的真知灼見包括：

- [自動轉寄訊息深入解析](mfi-auto-forwarded-messages-report.md)

- [修正可能的郵件迴圈真知灼見](mfi-mail-loop-insight.md)<sup>1</sup>

- [修正郵件流程規則真知灼見](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>的速度

- [郵件流程圖](mfi-mail-flow-map-report.md)

- [轉寄的新網域電子郵件洞察力](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [新使用者轉寄電子郵件真知灼見](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [非公認的網域報告](mfi-non-accepted-domain-report.md)

- [未傳遞回報](mfi-non-delivery-report.md)

- [外寄和內送郵件流程深入解析](mfi-outbound-and-inbound-mail-flow.md)

- [佇列深入解析](mfi-queue-alerts-and-queues.md)

- [SMTP 驗證用戶端深入解析和報告](mfi-smtp-auth-clients-report.md)

- [上層網域郵件流程狀態深入解析](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> 當偵測到問題之後，就會在 [郵件流程] 儀表板的 [ **建議** ] 區域中顯示此真知灼見。 否則，您將看不到它。

<sup>2</sup> 郵件流程儀表板上不會顯示這種觀點，但在偵測到問題之後，會在 [轉寄 [報告](view-mail-flow-reports.md#forwarding-report) ] 頁面上顯示。 否則，您將看不到它。

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>查看郵件流程儀表板所需的許可權

郵件流程儀表板可用於下列角色群組的成員：

- 安全性 & 規範中心內的 **組織管理** (全域管理員) 。

- Exchange Azure Active Directory 中的 **[系統管理員](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)**。

- 郵件流程安全性 & 規範中心的 **系統管理員**。 如果帳戶不是「組織管理」或「Exchange 管理員」角色群組的成員，請考慮下列問題：
  - 使用者必須直接登入安全性 & 合規性中心 <https://protection.office.com> 。
  - 使用者只具有郵件流程儀表板的唯讀許可權。
  - 使用者將無法存取 Microsoft 365 系統管理中心。

如需許可權的詳細資訊，請參閱 [安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md) ，並 [讓使用者能夠存取安全性 & 規範中心](grant-access-to-the-security-and-compliance-center.md)。

## <a name="where-to-find-the-mail-flow-dashboard"></a>哪裡可以找到郵件流程儀表板

開啟安全性 & 合規性中心 <https://protection.office.com> ，展開 [ **郵件流程**]，然後選取 [ **儀表板**]。

若要直接移至 [郵件流程] 儀表板，請開啟] <https://protection.office.com/mailflow/dashboard> 。