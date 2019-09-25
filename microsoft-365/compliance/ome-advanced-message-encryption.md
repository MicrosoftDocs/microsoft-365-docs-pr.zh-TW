---
title: Office 365 進階郵件加密
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Office 365 中的高级邮件加密通过允许管理员通过 Office 365 Web 门户过期和撤销对加密电子邮件的访问权限，帮助组织履行其合规性义务。
ms.openlocfilehash: dcef5f861711acffb8359063373cd90d4b122d88
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077845"
---
# <a name="office-365-advanced-message-encryption"></a>Office 365 進階郵件加密

在某些订阅中，Office 365 高级邮件加密在 Office 365 邮件加密之上可用。 高级邮件加密包含在[Microsoft 365 企业 E5、Office](https://www.microsoft.com/microsoft-365/enterprise/home)365 企业版 E5 和 Office 365 教育版 A5 中。 如果您的组织具有不包括 Office 365 高级邮件加密的 Office 365 订阅，则可以购买高级邮件加密作为符合高级合规性 SKU 的 E5 合规性的附加组件。

Office 365 中的高级邮件加密可帮助客户履行合规性义务，这些义务要求对外部收件人及其访问加密电子邮件进行更灵活的控制。 使用 Office 365 中的高级邮件加密，您可以使用自动策略控制在组织外部共享的敏感电子邮件。 您可以配置这些策略以识别敏感信息类型（如 PII、财务或运行状况标识），或者可以使用关键字来增强保护。 配置策略后，可以将策略与自定义品牌电子邮件模板配对，然后添加到期日期，以便对适合该策略的电子邮件进行额外控制。 此外，管理员还可以通过随时撤销对邮件的访问，进一步控制通过安全 Web 门户外部访问的加密电子邮件。

您只能撤销和设置发送给外部收件人的电子邮件的到期日期。

使用 Office 365 高级邮件加密，无论何时应用自定义品牌模板，Office 365 都会将包装器应用于适合应用模板的邮件流规则的电子邮件。 您只能撤消邮件，并将到期日期应用于用户通过门户接收的邮件。 换句话说，应用了自定义品牌模板的电子邮件。

## <a name="get-started-with-office-365-advanced-message-encryption"></a>开始使用 Office 365 高级邮件加密

以下主题介绍如何设置和使用高级邮件加密。

您的组织必须具有包含 Office 365 高级邮件加密的订阅。 有关受支持的订阅的详细信息，请参阅[消息策略和合规性服务说明。](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

如果尚未设置 Office 365 邮件加密，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

[设置由 Office 365 高级邮件加密加密的电子邮件的到期日期。](ome-advanced-expiration.md) 通过自动策略控制在组织外部共享的敏感电子邮件，通过安全 Web 门户对加密电子邮件的访问过期来增强保护。

[撤销由 Office 365 高级邮件加密加密的电子邮件。](revoke-ome-encrypted-mail.md) 控制在组织外部共享的敏感电子邮件，并通过通过安全 Web 门户撤销对加密电子邮件的访问来增强保护。  