---
title: Office 365 郵件加密常見問題集
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/11/2019
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: 对 Office 365 中的新邮件保护功能如何工作有疑问？ 在此处查看答案。
ms.openlocfilehash: 1625ecd3f2c7991e2726539bcfa0c772d1ffea59
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077844"
---
# <a name="office-365-message-encryption-faq"></a>Office 365 郵件加密常見問題集

对 Office 365 中的新邮件保护功能如何工作有疑问？ 在此处查看答案。 此外，请查看 Azure[信息保护中有关数据保护的常见问题，](https://docs.microsoft.com/information-protection/get-started/faqs-rms)了解 Azure 信息保护中有关数据保护服务 Azure 权限管理的问题。

||
|:-----|
|本文是关于 Office 365 消息加密的较大系列文章的一部分。 本文面向管理员和 ITPros。 如果您只想查找有关发送或接收加密邮件的信息，请参阅[Office 365 邮件加密 （OME）](ome.md)中的文章列表，并找到最适合您需求的文章。 |
||
  
## <a name="what-is-office-365-message-encryption-ome"></a>什么是 Office 365 邮件加密 （OME）？

OME 结合了电子邮件加密和权限管理功能。 权限管理功能由 Azure 信息保护提供支持。
  
## <a name="who-can-use-ome"></a>谁可以使用 OME？

您可以在以下条件下使用 OME 的新功能：
  
- 如果您从未在 Office 365 中设置 OME 或 IRM 进行联机交换。

- 如果已设置 OME 和 IRM，则可以使用 Azure 信息保护中的 Azure 权限管理服务，可以使用这些步骤。

- 如果您使用"在线交换"与活动目录权限管理服务 （AD RMS）一起使用，则不能直接启用这些新功能。 相反，您需要首先[将 AD RMS 迁移到 Azure 信息保护。](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) 完成迁移后，可以成功设置 OME。

    如果选择继续使用本地 AD RMS 与 Exchange Online 一起使用，而不是迁移到 Azure 信息保护，您将无法使用这些新功能。

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>使用新的 OME 功能需要哪些订阅？

要使用新的 OME 功能，您需要以下计划之一：
  
- Office 365 邮件加密是 Office 365 企业版 E3 和 E5、微软企业 E3 和 E5、微软 365 企业版、Office 365 A1、A3 和 A5 以及 Office 365 政府 G3 和 G5 的一部分。 客户不需要其他许可证来接收由 Azure 信息保护支持的新保护功能。

- 您还可以将 Azure 信息保护计划 1 添加到以下计划中，以接收新的 Office 365 邮件加密功能：交换联机计划 1、交换联机计划 2、Office 365 F1、Office 365 业务要点、Office 365 业务高级版，或Office 365 企业版 E1。

- 从 Office 365 消息加密中受益的每个用户都需要获得该功能的许可。

- 有关完整列表，请参阅 Office 365 邮件加密的[Exchange 联机服务说明。](https://technet.microsoft.com/library/exchange-online-service-description.aspx)

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>是否可以在 Azure 信息保护中使用"联机交换"并携带自己的密钥 （BYOK）？

是的！ Microsoft 建议您在设置 OME 之前完成设置 BYOK 的步骤。
  
有关 BYOK 的详细信息，请参阅[规划和实现 Azure 信息保护租户密钥](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>具有 Azure 信息保护功能的 OME 和 BYOK 会更改 Microsoft 处理第三方数据请求（如传票）的方法吗？

否。 OME 和提供和控制您自己的加密密钥（称为 BYOK）的选项来自 Azure 信息保护，其设计不是响应执法传票。 OME 与用于 Azure 信息保护的 BYOK 一起专为注重合规性的客户而设计。 微软非常重视第三方对客户数据的请求。 作为云服务提供商，我们始终倡导客户数据的隐私。 如果我们收到传票，我们总是试图将第三方重定向到客户以获取信息。 （请阅读布拉德·史密斯的博客：[保护客户数据免受政府窥探）。](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) 我们会定期发布我们收到的请求的详细信息。 有关第三方数据请求的详细信息，请参阅响应政府和执法部门访问 Microsoft 信任中心[上的客户数据的请求。](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data) 此外，请参阅[在线服务条款 （OST）](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)中的"客户数据泄露"。
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>此功能与旧版 Office 365 邮件加密 （OME） 和信息权限管理 （IRM） 功能的关系如何？

Office 365 消息加密的新功能是现有 IRM 和旧版 OME 解决方案的演变。 下表提供了更多详细信息。
  
**比较旧版 OME、IRM 和新的 OME 功能**

|**功能**|**OME 的早期版本**|**IRM**|**新的 OME 功能**|
|:-----|:-----|:-----|:-----|
|**发送加密电子邮件**|只能通过 Exchange 邮件流规则|最终用户从 PC Outlook、Mac Outlook 或 Web 上的 Outlook 启动;或通过 Exchange 邮件流规则|最终用户从 PC Outlook、Mac Outlook 或 Web 上的 Outlook 启动;或通过邮件流规则|
|**权限管理**|-|不转发选项和自定义模板|不转发选项、仅加密选项、默认模板和自定义模板|
|**支持的收件人类型**|仅限外部收件人|仅限内部收件人|内部和外部收件人|
|**收件人的经验**|外部收件人收到一条 HTML 消息，该邮件在浏览器或下载的移动应用中下载并打开。|内部收件人仅在 Outlook 的 PC、Mac Outlook 和 Web 上的 Outlook 中收到加密电子邮件。|内部和外部收件人在 PC Outlook、Mac Outlook、Web Outlook、Android Outlook 和 iOS Outlook 中接收电子邮件，或者通过 Web 门户接收电子邮件，无论他们是否在同一 Office 365 组织或任何 Office 365 中组织。 OME 门户不需要单独下载。|
|**自带密钥支持**|無|無| BYOK 支持|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>如何为我的组织启用新的 OME 功能？

请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>以前的 OME 版本是否会被弃用？

您仍可以使用早期版本的 OME，此时不会弃用它。 但是，我们强烈建议组织使用新的和改进的 OME 解决方案。 尚未部署 OME 的客户无法设置早期版本的 OME 的新部署。
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>我的组织使用活动目录权限管理，我可以使用此功能吗？

否。 如果您使用"在线交换"与活动目录权限管理服务 （AD RMS）一起使用，则不能直接启用这些新功能。 相反，您需要首先[将 AD RMS 迁移到 Azure 信息保护。](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>我的组织具有 Exchange 混合部署。 我可以使用此功能吗？

本地用户可以使用 Exchange 联机邮件流规则发送加密邮件。 为此，您需要通过 Exchange Online 路由电子邮件。 有关详细信息，请参阅第[2 部分：将邮件配置为从电子邮件服务器流向 Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>要创建 OME 加密邮件，我需要使用哪些电子邮件客户端？ 哪些应用程序支持发送受保护的消息？

您可以为 PC 和 Mac 创建 Outlook 2016 和 Outlook 2013 以及 Web 上的 Outlook 中受保护的邮件。
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>支持哪些电子邮件客户端阅读和回复受保护的电子邮件？

如果您是 Office 365 用户，则可以从 PC 和 Mac Outlook（2013 和 2016）、Web Outlook 和 Outlook 移动版（Android 和 iOS）中阅读和响应。 如果您的组织允许，也可以使用 iOS 本机邮件客户端。 如果您是非 Office 365 用户，则可以通过 Web 浏览器读取和回复 Web 上的加密邮件。
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>受保护电子邮件中的附件支持哪些文件类型？ 附件是否可以继承与受保护电子邮件关联的保护策略？

您可以将任何文件类型附加到受保护的邮件，但保护策略仅适用于[此处](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)提及的文件格式。 
  
如果支持文件格式（如 Word、Excel 或 PowerPoint 文件），则即使收件人下载了附件后，该文件也始终受到保护。 例如，如果附件受"不转发"保护，并且原始收件人下载附件并将其转发到新收件人，则新收件人将无法打开受保护的文件。
  
## <a name="are-pdf-file-attachments-supported"></a>PDF 文件附件受支持吗？

如果将 PDF 文件附加到受保护的邮件，邮件本身将受到保护，但在收件人收到 PDF 文件后，不会对该文件应用额外的保护。 这意味着收件人可以保存为、转发、复制和打印 PDF 文件。
  
## <a name="are-onedrive-for-business-attachments-supported"></a>支持 OneDrive 业务附件吗？

Not yet. 不支持 OneDrive 业务附件，最终用户无法加密包含云 OneDrive 业务附件的邮件。
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>我可以通过设置策略自动加密邮件吗？

是。 使用 Exchange Online 中的邮件流规则根据特定条件自动加密邮件。 例如，您可以创建基于收件人 ID、收件人域或邮件正文或主题中的内容的策略。 请参阅[定义邮件流规则以加密 Office 365 中的电子邮件。](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>我能否通过安全&amp;合规性中心在数据丢失防护 （DLP） 中设置策略来自动加密邮件？

是的！ 您可以在 Exchange 联机中设置邮件流规则，也可以在安全&amp;合规性中心使用 DLP 设置邮件流规则。
  
## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>我可以打开发送到共享邮箱的加密邮件吗？

共享邮箱当前不支持加密的邮件。

## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>我能否使用公司品牌自定义加密邮件？

是的！ 有关自定义电子邮件和 OME 门户的信息，请参阅将组织的品牌添加到加密邮件中。 请参阅[将组织的品牌添加到加密邮件。](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>加密电子邮件是否有任何报告功能或见解？

安全和合规性中心中有一个加密报告。 请参阅[查看安全&合规性中心中的电子邮件安全报告。](view-email-security-reports.md)
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>我能否将邮件加密与合规性功能（如电子数据展示）一起使用？

是。 所有加密的电子邮件都可以通过 Office 365 合规性功能发现。
