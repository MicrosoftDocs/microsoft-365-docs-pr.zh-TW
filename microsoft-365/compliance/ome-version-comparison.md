---
title: Office 365 邮件加密 （OME） 版本比较
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
description: 有助于解释 Office 365 邮件加密版本之间的差异。
ms.openlocfilehash: b617d6a9f61ae8ec5a0133d405f89038bdab9fc4
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077972"
---
# <a name="compare-versions-of-ome"></a>比較 OME 版本

本文将旧版 Office 365 邮件加密 （OME） 与新的 OME 功能和 Office 365 高级邮件加密进行比较。 新功能是 OME 和信息权限管理 （IRM） 的合并和较新版本。 还概述了部署到海合会高地的独特特点。 两者可以共存于 Office 365 组织中。 有关新功能如何工作的信息，请参阅 Office [365 邮件加密 （OME）。](ome.md)

||
|:-----|
|本文是关于 Office 365 消息加密的较大系列文章的一部分。 本文面向管理员和 ITPros。 如果您只想查找有关发送或接收加密邮件的信息，请参阅[Office 365 邮件加密 （OME）](ome.md)中的文章列表，并找到最适合您需求的文章。 |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>特性和功能的并行比较

|                                   |旧功能       |                   |新功能              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**功能**                     | **舊版 OME**    | **IRM**           | **新的 OME 功能** |
|*发送加密邮件*        |通过交换邮件流规则|最终用户从 Outlook 桌面或 Web 上的 Outlook 启动;或通过 Exchange 邮件流规则|最终用户从 Outlook 桌面、Mac Outlook 或 Web 上的 Outlook 启动;通过 Exchange 邮件流规则（也称为传输规则）和 Office 365 数据丢失防护 （DLP）|
|*权限管理模板*       |   不適用      |不转发选项和自定义模板|不转发选项、仅加密选项和自定义模板|
|*收件者類型*                   |内部和外部收件人|仅限内部收件人         |内部和外部收件人|
|*内部收件人的经验*|收件人收到 HTML 消息，他们在 Web 浏览器或移动应用中下载并打开该邮件|Outlook 客户端中的本机内联体验|使用 Outlook 客户端为同一组织中的收件人提供本机内联体验。  收件人可以使用 Outlook 以外的客户端从 OME 门户读取邮件（无需下载或应用）。|
|*外部收件人的经验*|收件人收到 HTML 消息，他们在 Web 浏览器或移动应用中下载并打开该邮件|不適用|Office 365 收件人的本机内联体验。 所有其他收件人都可以从 OME 门户阅读邮件（无需下载或应用）。|
|*附件权限*           |对附件没有限制|附件受到保护|附件受"不转发"选项和自定义模板的保护。 管理员可以选择"仅加密"选项的附件是否受到保护。|
|*自带密钥 （BYOK） 支持*|無                |無               |BYOK 支持          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>与传统的 OME 产品具有新的 OME 功能的优势

新功能具有以下优点：

- 能够使用"仅加密"（支持安全协作）、不转发和自定义限制。
- 发件人可以从 Outlook 桌面、Mac Outlook 和 Web 客户端上的 Outlook 发送使用新功能手动加密的邮件。
- Office 365 收件人在支持的 Outlook 客户端中使用内联体验。 或者，管理员可以选择向 Office 365 收件人显示品牌体验。
- Office 365 以外的帐户（如 Gmail、雅虎和 Microsoft 帐户）与 OME 门户联合使用，该门户为这些收件人提供更好的用户体验。 所有其他标识使用一次性密码访问加密邮件。
- 管理员可以自定义品牌，并创建多个品牌模板。
- 管理员可以撤消使用新功能加密的电子邮件。
- 新功能通过安全&amp;合规性中心提供详细的使用情况报告。

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 高级邮件加密功能

Office 365 高级邮件加密在新的 OME 功能之上提供了其他功能。 您必须在组织中设置新的 Office 365 邮件加密功能，才能使用高级邮件加密功能。 此外，为了使用这些功能，收件人必须通过 OME 门户查看和回复安全邮件。 高级功能包括：

- 消息吊销

- 消息过期

- 多个品牌模板

GCC 高不支持 Office 365 高级邮件加密。

有关使用高级邮件加密的信息，请参阅[Office 365 高级邮件加密](ome-advanced-message-encryption.md)。

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>GCC 高部署中 Office 365 消息加密的独特特性

Office 365 高级邮件加密在 GCC 高环境中不可用。 您仍然可以在 GCC 高环境中使用单个品牌模板。

此外，如果您计划在 GCC 高环境中使用 Office 365 邮件加密，则收件人体验有一些独特的特征。

GCC 高不支持 Office 365 高级邮件加密。

### <a name="encrypted-email-from-gcc-high-to-gcc-high-recipients"></a>从 GCC 高到 GCC 高收件人的加密电子邮件

发件人可以在 Outlook 中手动加密 Web 上的 PC 和 Mac 和 Outlook 中的电子邮件，或者组织可以使用 Exchange 邮件流规则设置策略来加密电子邮件。

GCC High 中的收件人在 Web 上的 PC 和 Mac Outlook 和 Outlook 中接收与所有其他 Office 365 用户相同的内联阅读体验。

### <a name="encrypted-email-from-gcc-high-to-non-gcc-high-recipients"></a>从 GCC 高到非 GCC 高收件人的加密电子邮件

GCC 高内部的发件人可以在 GCC 高边界之外发送加密电子邮件。

GCC High 以外的所有收件人（包括商业 Office 365 用户、Outlook.com用户和其他电子邮件提供商（如 Gmail 和 Yahoo）的用户都会收到一封包装邮件。 此包装邮件将收件人重定向到 OME 门户，收件人可以在其中读取和回复邮件。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>在同一租户中共存旧 OME 和新功能

您可以在同一租户中同时使用旧版 OME 和新功能。 作为管理员，您可以通过选择要在创建邮件流规则时使用的 OME 版本来执行此操作。

- 要指定 OME 的旧版本，请使用 Exchange 邮件流规则操作**应用 OME 的早期版本。**

- 要指定新功能，请使用 Exchange 邮件流规则操作**应用 Office 365 邮件加密和权限保护**。

用户可以手动发送使用 Outlook 桌面、Outlook Mac 和 Web 上的 Outlook 中的新功能加密的邮件。

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>从旧版 OME 迁移到新功能

即使两个版本的 OME 可以共存，我们强烈建议您编辑使用规则操作的旧邮件流规则**应用 OME 的早期版本**以使用新功能。 更新这些规则以使用邮件流规则操作应用**Office 365 邮件加密和权限保护**。 有关说明，请参阅[定义邮件流规则以加密 Office 365 中的电子邮件。](define-mail-flow-rules-to-encrypt-email.md)

## <a name="get-started-with-ome"></a>开始使用 OME

通常，新的 OME 功能会自动为 Office 365 组织启用。 有关组织中新的 OME 功能的详细信息，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

如果启用了 Azure 信息保护，则 Office 365 组织将自动启用旧版 OME。 过去，即使未启用 Azure 信息保护，旧版 OME 也有效。 情况已经不同了。

要开始使用旧版 OME，如果已启用 Azure 信息保护，请配置使用规则操作的邮件流规则**应用 OME 的早期版本。** 有关说明，请参阅[定义邮件流规则以加密 Office 365 中的电子邮件。](define-mail-flow-rules-to-encrypt-email.md)