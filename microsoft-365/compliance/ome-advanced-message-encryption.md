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
# <a name="office-365-advanced-message-encryption"></a><span data-ttu-id="1f7ba-103">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="1f7ba-103">Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="1f7ba-104">在某些订阅中，Office 365 高级邮件加密在 Office 365 邮件加密之上可用。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="1f7ba-105">高级邮件加密包含在[Microsoft 365 企业 E5、Office](https://www.microsoft.com/microsoft-365/enterprise/home)365 企业版 E5 和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="1f7ba-106">如果您的组织具有不包括 Office 365 高级邮件加密的 Office 365 订阅，则可以购买高级邮件加密作为符合高级合规性 SKU 的 E5 合规性的附加组件。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-106">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="1f7ba-107">Office 365 中的高级邮件加密可帮助客户履行合规性义务，这些义务要求对外部收件人及其访问加密电子邮件进行更灵活的控制。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-107">Advanced Message Encryption in Office 365 helps customers meet compliance obligations that require more flexible controls over external recipients and their access to encrypted emails.</span></span> <span data-ttu-id="1f7ba-108">使用 Office 365 中的高级邮件加密，您可以使用自动策略控制在组织外部共享的敏感电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-108">With Advanced Message Encryption in Office 365, you can control sensitive emails shared outside the organization with automatic policies.</span></span> <span data-ttu-id="1f7ba-109">您可以配置这些策略以识别敏感信息类型（如 PII、财务或运行状况标识），或者可以使用关键字来增强保护。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-109">You configure these policies to identify sensitive information types such as PII, Financial, or Health IDs, or you can use keywords to enhance protection.</span></span> <span data-ttu-id="1f7ba-110">配置策略后，可以将策略与自定义品牌电子邮件模板配对，然后添加到期日期，以便对适合该策略的电子邮件进行额外控制。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-110">Once you've configured the policies, you pair policies with custom branded email templates and then add an expiration date for extra control of emails that fit the policy.</span></span> <span data-ttu-id="1f7ba-111">此外，管理员还可以通过随时撤销对邮件的访问，进一步控制通过安全 Web 门户外部访问的加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-111">Also, admins can further control encrypted emails accessed externally through a secure web portal by revoking access to the mail at any time.</span></span>

<span data-ttu-id="1f7ba-112">您只能撤销和设置发送给外部收件人的电子邮件的到期日期。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-112">You can only revoke and set an expiration date for emails sent to external recipients.</span></span>

<span data-ttu-id="1f7ba-113">使用 Office 365 高级邮件加密，无论何时应用自定义品牌模板，Office 365 都会将包装器应用于适合应用模板的邮件流规则的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-113">With Office 365 Advanced Message Encryption, anytime you apply a custom branding template, Office 365 applies a wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="1f7ba-114">您只能撤消邮件，并将到期日期应用于用户通过门户接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-114">You can only revoke messages and apply expiration dates to messages that users receive through the portal.</span></span> <span data-ttu-id="1f7ba-115">换句话说，应用了自定义品牌模板的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-115">In other words, email that has a custom branding template applied.</span></span>

## <a name="get-started-with-office-365-advanced-message-encryption"></a><span data-ttu-id="1f7ba-116">开始使用 Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="1f7ba-116">Get started with Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="1f7ba-117">以下主题介绍如何设置和使用高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-117">The following topics describe how you set up and use Advanced Message Encryption.</span></span>

<span data-ttu-id="1f7ba-118">您的组织必须具有包含 Office 365 高级邮件加密的订阅。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-118">Your organization must have a subscription that includes Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="1f7ba-119">有关受支持的订阅的详细信息，请参阅[消息策略和合规性服务说明。](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)</span><span class="sxs-lookup"><span data-stu-id="1f7ba-119">For detailed information about supported subscriptions, see the [Message policy and compliance service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

<span data-ttu-id="1f7ba-120">如果尚未设置 Office 365 邮件加密，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-120">If you do not have Office 365 Message Encryption set up already, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="1f7ba-121">[设置由 Office 365 高级邮件加密加密的电子邮件的到期日期。](ome-advanced-expiration.md)</span><span class="sxs-lookup"><span data-stu-id="1f7ba-121">[Set an expiration date for email encrypted by Office 365 Advanced Message Encryption](ome-advanced-expiration.md).</span></span> <span data-ttu-id="1f7ba-122">通过自动策略控制在组织外部共享的敏感电子邮件，通过安全 Web 门户对加密电子邮件的访问过期来增强保护。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-122">Control sensitive emails shared outside the organization with automatic policies that enhance protection by expiring access through a secure web portal to encrypted emails.</span></span>

<span data-ttu-id="1f7ba-123">[撤销由 Office 365 高级邮件加密加密的电子邮件。](revoke-ome-encrypted-mail.md)</span><span class="sxs-lookup"><span data-stu-id="1f7ba-123">[Revoke email encrypted by Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md).</span></span> <span data-ttu-id="1f7ba-124">控制在组织外部共享的敏感电子邮件，并通过通过安全 Web 门户撤销对加密电子邮件的访问来增强保护。</span><span class="sxs-lookup"><span data-stu-id="1f7ba-124">Control sensitive emails shared outside the organization and enhance protection by revoking access through a secure web portal to encrypted emails.</span></span>  