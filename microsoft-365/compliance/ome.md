---
title: Office 365 郵件加密
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: 借助 Office 365 邮件加密，您的组织可以在组织内外人员之间发送和接收加密的电子邮件。 电子邮件加密有助于确保只有目标收件人才能查看邮件内容。
ms.openlocfilehash: f6f6f59225d267d08ba20e1fdea219dc5d890ed5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078188"
---
# <a name="office-365-message-encryption"></a>Office 365 郵件加密

人員通常會使用電子郵件來交換機密資訊，例如財務資料、法律合約、機密產品資訊、銷售報告和預測、病患健康資訊，或是客戶和員工資訊。因此，信箱可能會成為大量潛在機密資訊的存放庫，而且資訊外洩可能會變成組織的嚴重威脅。

借助 Office 365 邮件加密，您的组织可以在组织内外人员之间发送和接收加密的电子邮件。 Office 365 邮件加密适用于Outlook.com、雅虎、Gmail 和其他电子邮件服务。 电子邮件加密有助于确保只有目标收件人才能查看邮件内容。
  
本文的其余部分适用于新的 OME 功能。
  
## <a name="how-office-365-message-encryption-works"></a>Office 365 邮件加密的工作原理

Office 365 消息加密是在 Azure 权限管理 （Azure RMS） 上构建的在线服务，它是 Azure 信息保护的一部分。 这包括加密、标识和授权策略，以帮助保护您的电子邮件。 您可以使用权限管理[模板、"不转发"选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)和[仅加密选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)来加密邮件。

然后，用户可以使用这些选项加密电子邮件和各种 Office 365 附件。 有关受支持的附件类型的完整列表，请参阅电子邮件的[IRM 简介中的"IRM 策略附加到邮件时涵盖的文件类型"。](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)

作为管理员，您还可以定义邮件流规则以应用此保护。 例如，您可以创建一个规则，要求加密发送给特定收件人的所有邮件，或该规则包含主题行中的特定单词，并指定收件人无法复制或打印邮件的内容。

与早期版本的 OME 不同，无论您是在组织内部发送邮件，还是在 Office 365 之外向收件人发送电子邮件，新功能都提供统一的发件人体验。 此外，收到发送到 Outlook 2016 或 Web 上的 Outlook 中的 Office 365 帐户的受保护电子邮件的收件人无需执行任何其他操作才能查看该邮件。 它无缝工作。 使用其他电子邮件客户端和电子邮件服务提供商的收件人也有改进的体验。 有关详细信息，请参阅[了解 Office 365 中的受保护邮件](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)[以及如何打开受保护的邮件。](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)

有关早期版本的 OME 和新的 OME 功能之间的差异的详细列表，请参阅[比较 OME 版本。](ome-version-comparison.md)

当有人发送与加密邮件流规则匹配的电子邮件时，邮件在发送之前将被加密。 使用 Outlook 客户端读取邮件的所有 Office 365 最终用户都会接收加密和受权限保护的邮件的本机、一流的阅读体验，即使他们与发件人不在同一组织中。 支持的 Outlook 客户端包括 Outlook 桌面、Outlook Mac、iOS 和 Android 上的 Outlook 移动版以及 Web 上的 Outlook（以前称为 Outlook Web 应用程序）。
  
收到发送到其Outlook.com、Gmail 和 Yahoo 帐户的加密邮件或受权限保护的邮件的加密邮件的收件人会收到一封包装邮件，这些邮件将引导到 OME 门户，以便他们使用 Microsoft 帐户、Gmail 或雅虎凭据。
  
在 Outlook 以外的客户端上读取加密或受权限保护邮件的最终用户也使用 OME 门户查看他们收到的加密和受权限保护的邮件。

此外，如果受保护邮件的发件人位于 GCC High 中，并且收件人位于 GCC High 之外（包括商业 Office 365 用户、Outlook.com用户和其他电子邮件提供商（如 Gmail）的用户，则收件人将收到重定向到的包装邮件OME 门户，收件人能够读取和回复邮件。 否则，如果发件人和收件人都位于 GCC High 环境中，则使用 Outlook 客户端读取邮件的收件人会接收加密和受权限保护邮件的本机一流阅读体验，即使他们不在同一组织中作为发件人。 有关 GCC High 中不同体验的详细信息，请参阅[比较 OME 版本](ome-version-comparison.md)。
  
我们增加了可以使用 OME 加密的邮件和附件的大小限制。 有关限制的详细信息，请参阅[交换在线限制](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)。

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Office 365 高级邮件加密如何在 OME 之上工作

Office 365 高级邮件加密允许您创建多个品牌模板，以便您可以微调对收件人邮件的控制，并创建自定义品牌体验以支持不同的组织结构。

Office 365 中的高级邮件加密可帮助您履行合规性义务，这些义务要求对外部收件人对加密电子邮件的访问进行更灵活的控制。 借助 Office 365 中的高级邮件加密，作为管理员，您可以使用检测敏感信息类型（例如 PII、财务或运行状况信息）的自动策略或关键字来增强在组织外部共享的敏感电子邮件通过安全 Web 门户对加密电子邮件的访问过期来保护。 此外，作为管理员，您可以通过随时撤销对电子邮件的访问权限，进一步控制通过 Office 365 Web 门户外部访问的加密电子邮件。

邮件吊销和过期仅适用于用户发送给 Office 365 组织外部收件人的电子邮件。 此外，收件人必须通过 Web 门户访问电子邮件。 为了确保收件人使用门户接收电子邮件，请设置应用包装的自定义品牌模板。 然后，在邮件流规则中应用品牌模板。 有关高级邮件加密的详细信息，请参阅[Office 365 高级邮件加密](ome-advanced-message-encryption.md)。

## <a name="defining-rules-for-office-365-message-encryption"></a>定义 Office 365 邮件加密规则

启用 Office 365 邮件加密新功能的一种方法是交换联机和交换联机保护管理员定义邮件流规则。 这些规则确定应在什么条件下加密电子邮件。 为规则设置加密操作时，任何与规则条件匹配的消息在发送之前都将被加密。
  
邮件流规则非常灵活，允许您组合条件，以便在单个规则中满足特定的安全要求。 例如，您可以创建一个规则来加密包含指定关键字并发送给外部收件人的所有邮件。 Office 365 邮件加密的新功能还加密加密电子邮件收件人的回复。
  
有关如何创建邮件流规则以利用新的 OME 功能的详细信息，请参阅[定义 Office 365 邮件加密规则](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="get-started-with-the-new-ome-capabilities"></a>开始使用新的 OME 功能

如果您已准备好开始使用组织内的新 OME 功能，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>发送、查看和回复加密的电子邮件

使用 Office 365 邮件加密，用户可以在 Web 上从 Outlook 和 Outlook 发送加密电子邮件。 此外，管理员可以在 Office 365 中设置邮件流规则，以便根据关键字匹配或其他条件自动加密电子邮件。
  
在 Office 365 组织中加密邮件的收件人将能够在任何版本 Outlook 中无缝读取这些邮件，包括 PC Outlook、Mac Outlook、Web 上 Outlook、iOS Outlook 和 Android Outlook。 在其他电子邮件客户端上接收加密邮件的用户可以在 OME 门户中查看邮件。
  
有关如何发送和查看加密邮件的详细指导，请查看以下文章：
  
|||
|:-----|:-----|
|阅读本文...  <br/> |如果你是...  <br/> |
|[了解 Office 365 中的受保护邮件](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx) <br/> |想要详细了解加密邮件的工作原理以及可用的选项的最终用户。  <br/> |
|[如何打开受保护的邮件？](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx) <br/> |想要读取发送给您的受保护邮件的最终用户。 本文包含有关从多个版本的 Outlook 和来自不同电子邮件帐户（包括 Office 365 外部（如 gmail 和 Yahoo！ 帐户。  <br/> |
|[在 Outlook 中发送、查看和回复加密邮件](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx) <br/> |想要从 Outlook 发送、查看或回复加密邮件的最终用户。 即使您不是 Office 365 组织的成员，您仍然会收到 Outlook 中发送给你的加密邮件的通知。 有关如何查看和回复从 Office 365 发送的加密邮件的说明，请使用本文。  <br/> |
|[发送数字签名或加密邮件](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547) <br/> |希望使用 Outlook For Mac 发送、查看或回复加密邮件的最终用户。 本文还介绍了使用 OME 以外的加密方法，如 S/MIME。  <br/> |
|[在 Android 设备上查看加密邮件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> |最终用户在 Android 设备上收到使用 Office 365 邮件加密加密的邮件，您可以使用免费的 OME 查看器应用查看邮件并发送加密回复。 本文将介绍如何。  <br/> |
|[在 iPhone 或 iPad 上查看加密邮件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |最终用户在 iPhone 或 iPad 上收到使用 Office 365 邮件加密加密的邮件，您可以使用免费的 OME 查看器应用程序查看邮件并发送加密回复。 本文将介绍如何。  <br/> |
||