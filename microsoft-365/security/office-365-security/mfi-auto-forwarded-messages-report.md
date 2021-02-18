---
title: 自動轉寄訊息深入解析
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 系統管理員可以在安全性 & 合規性中心的郵件流程儀表板中瞭解自動轉寄的郵件報告。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8f5e7088a88307576a054a1f6833101789d68d01
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290630"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>在安全性 & 規範中心內，自動轉寄的郵件會深入瞭解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在 [Security & 合規性中心](https://protection.office.com)的 [郵件流程儀表板](mail-flow-insights-v2.md)中，可洞察的 **自動轉寄郵件** 會顯示自動從您的組織轉送到外部網域中收件者之郵件的相關資訊。

![安全性 & 規範中心內自動轉寄的郵件小工具](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>自動轉寄的郵件詳細資料

當您按一下小工具中的郵件數目時，會出現一個彈出窗格，顯示自動轉寄郵件的詳細資訊：

- 透過 **轉送方法自動轉寄的郵件**：

  - **依郵件流程規則**
  - **依收件匣規則**
  - 透過 **SMTP** 轉寄：此方法會指出系統管理員可以在信箱上設定的自動轉寄，如 [設定信箱的電子郵件](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)轉寄中所述。
  - 有關詳細資訊，請查看 [轉接報告](view-mail-flow-reports.md#forwarding-report) 的連結。

- **依網域和使用者自動轉寄郵件**：

  - **前5個網域會轉寄至**
  - **新的網域 (上周)**
  - **前5個轉接使用者**
  - **新使用者 (上周)**
  - 有關詳細資訊，請查看「轉寄 [修改」報告](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 的連結。

![安全性 & 規範中心內自動轉寄郵件報告的詳細資料彈出報告](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>深入解析

這兩種洞察力是根據報表資料產生的：

- [新增使用者轉送電子郵件](mfi-new-users-forwarding-email.md)
- [轉寄電子郵件的新網域](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>請參閱

如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。
