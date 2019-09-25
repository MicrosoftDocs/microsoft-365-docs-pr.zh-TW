---
title: Office 365 客户管理的加密功能
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要：了解 Microsoft Office 365 中的数据恢复能力。
ms.openlocfilehash: 7c4817a2982733bc1d292117811cb21aa5278972
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077869"
---
# <a name="customer-managed-encryption-features-in-office-365"></a>Office 365 中的客户管理的加密功能

除了由 Microsoft 管理的 Office 365 中的加密技术外，Office 365 还可用于您可以管理和配置的其他加密技术，例如：
- [Azure 版權管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)
- [安全多用途互联网邮件扩展](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)
- [Office 365 郵件加密](http://products.office.com/en-us/exchange/office-365-message-encryption)
- [与合作伙伴组织一起保护邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

有关这些技术的其他信息，请参阅[Office 365 服务说明。](https://technet.microsoft.com/en-us/library/office-365-service-descriptions.aspx)

## <a name="azure-rights-management"></a>Azure 版權管理
[Azure 权限管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)（Azure RMS） 是 Azure[信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)所使用的保护技术。 它使用加密、标识和授权策略来帮助跨多个平台和设备（手机、平板电脑和 PC）保护文件和电子邮件的安全。 信息可以在组织内外受到保护，因为保护仍保留在数据中。 Azure RMS 提供对所有文件类型的持久保护，保护任何地方的文件，支持企业对企业的协作，以及各种 Windows 和非 Windows 设备。 Azure RMS 保护还可以增强[数据丢失防护 （DLP） 策略。](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) 有关哪些应用程序和服务可以使用 Azure 信息保护中的 Azure 权限管理服务的详细信息，请参阅[应用程序如何支持 Azure 权限管理服务。](https://docs.microsoft.com/information-protection/understand-explore/applications-support)

Azure RMS 与 Office 365 集成，可供所有 Office 365 客户使用。 要将 Office 365 配置为使用 Azure RMS，请参阅[将 IRM 配置为在 SharePoint 管理中心中使用 Azure 权限管理和设置信息权限管理 （IRM）。](https://technet.microsoft.com/en-us/library/dn151475(v=exchg.150).aspx) 如果您操作本地活动目录 （AD） RMS 服务器，那么还可以[将 IRM 配置为使用本地 AD RMS 服务器，](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)但我们强烈建议您迁移到[Azure RMS，](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)以便使用与其他服务器安全协作等新功能组织。

使用 Azure RMS 保护客户数据时，Azure RMS 使用具有 SHA-256 哈希算法的 2048 位 RSA 非对称密钥来加密数据。 Office 文档和电子邮件的对称键是 AES 128 位（带有 PKCS_7 填充的 CBC 模式）。 对于受 Azure RMS 保护的每个文档或电子邮件，Azure RMS 将创建一个 AES 密钥（"内容密钥"），该密钥嵌入到文档中，并保留在文档版本中。 内容密钥受组织的 RSA 密钥（"Azure 信息保护租户密钥"）保护，作为文档中策略的一部分，并且该策略也由文档的作者签名。 此租户密钥对于受组织 Azure RMS 保护的所有文档和电子邮件是通用的，并且只有在组织使用客户管理的租户密钥时，Azure 信息保护管理员才能更改此密钥。 有关 Azure RMS 使用的加密控件的详细信息，请参阅[Azure RMS 的工作原理？在引擎盖下。](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work)

在默认的 Azure RMS 实现中，Microsoft 生成和管理每个租户唯一的根密钥。 客户可以使用[名为"自带密钥 （BYOK））"](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)的密钥管理方法，在 Azure RMS 中使用 Azure 密钥保管库服务管理其根密钥的生命周期，该方法允许您在本地 HSM 中生成密钥，并在以下时间保持对密钥的控制。转移到微软的FIPS 140-2级2级验证的HSM。 不会向任何人员授予对根密钥的访问，因为无法导出密钥或从保护他们的硬件安全模块中提取密钥。 此外，您可以随时访问显示根密钥的所有访问权限的近实时日志。 有关详细信息，请参阅[记录和分析 Azure 权限管理使用情况](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)。

Azure 权限管理可帮助缓解诸如窃听、中间人攻击、数据窃取和无意违反组织共享策略等威胁。 同时，未经授权的用户在传输过程中或静止过程中对客户数据的任何无理访问，如果用户没有适当的权限，则通过跟踪该数据的策略进行阻止，从而降低数据落入不法分子手中的风险。在知情或不知情的情况下提供数据丢失防护功能。 如果用作 Azure 信息保护的一部分，Azure RMS 还提供数据分类和标记功能、内容标记、文档访问跟踪和访问吊销功能。 要了解有关这些功能的详细信息，请参阅[什么是 Azure 信息保护、Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)[信息保护部署路线图](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)和[Azure 信息保护的快速入门教程。](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)

## <a name="secure-multipurpose-internet-mail-extension"></a>安全多用途互联网邮件扩展
安全/多用途互联网邮件扩展 （S/MIME） 是公钥加密和 MIME 数据数字签名的标准。 S/MIME 在 RFC 3369、3370、3850、3851 等中定义。 它允许用户加密电子邮件并对电子邮件进行数字签名。 使用 S/MIME 加密的电子邮件只能由电子邮件的收件人使用其私钥解密，该密钥仅对该收件人可用。 因此，电子邮件不能由电子邮件收件人以外的任何人解密。

[微软在Office365中支持S/MIME。](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx) 公共证书分发到客户的本地活动目录，并存储在可复制到 Office 365 租户的属性中。 与公钥对应的私钥将保留在本地，并且永远不会传输到 Office 365。 用户可以使用 Outlook、Web 上的 Outlook 和 Exchange ActiveSync 客户端在组织中的两个用户之间撰写、加密、解密、读取和数字签名电子邮件。 有关详细信息，请参阅现在[Office 365 中的 S/MIME 加密。](http://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)

## <a name="office-365-message-encryption"></a>Office 365 郵件加密
[Office 365 邮件加密](https://products.office.com/en-us/exchange/office-365-message-encryption)基于[Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)（AIP） 构建的 （OME） 使您能够向任何人发送加密且受权限保护的邮件。 OME 可缓解诸如窃听和中间人攻击等威胁以及其他威胁，例如未经授权用户未经授权而不必要地访问数据，而用户没有适当的权限。 我们进行了投资，为您提供基于 Azure 信息保护的更简单、更直观、更安全的电子邮件体验。 您可以保护从 Office 365 发送到组织内外的任何人的邮件。 可以使用任何标识（包括 Azure 活动目录、Microsoft 帐户和 Google ID）跨不同的邮件客户端进行查看。" 有关您的组织如何使用加密邮件的详细信息，请参阅[Office 365 邮件加密](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A)。

## <a name="transport-layer-security"></a>傳輸層安全性   
如果要确保与合作伙伴的安全通信，可以使用入站和出站连接器来提供安全和消息完整性。 您可以使用证书在每个连接器上配置强制入站和出站 TLS。 使用加密的 SMTP 通道可以防止数据通过中间人攻击被盗。 有关详细信息，请参阅[联机交换如何使用 TLS 来保护电子邮件连接。](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F)

## <a name="domain-keys-identified-mail"></a>域密钥标识邮件
交换联机保护 （EOP） 和交换联机支持域密钥标识邮件 （DKIM） 消息的入站验证。 DKIM 是一种验证消息是否从它说它源自的域发送，并且不是被其他人欺骗的方法。 它将电子邮件与负责发送电子邮件的组织联系起来，是电子邮件加密这一更大模式的一部分。 有关此范例的三个部分的详细信息，请参阅：
- [在 Office 365 中設定 SPF 以協助防止詐騙](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)
- [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)
- [使用 DMARC 在 Office 365 中验证电子邮件](https://https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
