---
title: 設定及控制外部電子郵件轉寄、自動轉寄、拒絕5.7.520 存取、停用外部轉寄、系統管理員已停用外部轉寄、輸出反垃圾郵件原則
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: bbe341899599d5092db0b0961add5a9825eca3b4
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616593"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="7c79b-103">在 Microsoft 365 中控制自動外部電子郵件轉接</span><span class="sxs-lookup"><span data-stu-id="7c79b-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7c79b-104">身為系統管理員，您可能會有公司需求，以限制或控制自動轉寄的郵件至外部收件者 (組織外) 收件者。</span><span class="sxs-lookup"><span data-stu-id="7c79b-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="7c79b-105">電子郵件轉寄可能非常有用，但由於可能洩漏資訊，也可能會造成安全性風險。</span><span class="sxs-lookup"><span data-stu-id="7c79b-105">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="7c79b-106">攻擊者可能會利用此資訊來攻擊您的組織或合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="7c79b-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="7c79b-107">Microsoft 365 提供下列自動轉送類型：</span><span class="sxs-lookup"><span data-stu-id="7c79b-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="7c79b-108">使用者可以設定 [收件匣規則](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) ，自動將郵件轉寄給外部寄件者 (故意或因遭到破壞的帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="7c79b-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="7c79b-109">系統管理員可以設定 [信箱轉送](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (又稱為 _SMTP 轉送_) ，以自動將郵件轉寄給外部收件者。</span><span class="sxs-lookup"><span data-stu-id="7c79b-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span>

<span data-ttu-id="7c79b-110">您可以使用輸出垃圾郵件篩選原則來控制自動轉寄給外部收件者。</span><span class="sxs-lookup"><span data-stu-id="7c79b-110">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="7c79b-111">有三個可用的設定：</span><span class="sxs-lookup"><span data-stu-id="7c79b-111">Three settings are available:</span></span>

- <span data-ttu-id="7c79b-112">**自動**：封鎖自動外部轉送。</span><span class="sxs-lookup"><span data-stu-id="7c79b-112">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="7c79b-113">內部自動轉送郵件功能將繼續運作。</span><span class="sxs-lookup"><span data-stu-id="7c79b-113">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="7c79b-114">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="7c79b-114">This is the default setting.</span></span>

- <span data-ttu-id="7c79b-115">**開啟**：允許和不限制自動外部轉送。</span><span class="sxs-lookup"><span data-stu-id="7c79b-115">**On**: Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="7c79b-116">**Off**：停用自動外部轉寄，將會造成未傳遞回報 (也稱為 NDR 或退回的郵件) 傳送給寄件者。</span><span class="sxs-lookup"><span data-stu-id="7c79b-116">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="7c79b-117">如需如何設定這些設定的指示，請參閱 [CONFIGURE EOP 中的外寄垃圾郵件篩選](configure-the-outbound-spam-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="7c79b-117">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7c79b-118">停用自動轉寄功能會停用 (使用者) 或信箱轉寄 (系統管理員) 將郵件重新導向至外部地址的任何收件匣規則。</span><span class="sxs-lookup"><span data-stu-id="7c79b-118">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="7c79b-119">內部使用者之間的自動轉送郵件不會受到輸出垃圾郵件篩選原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="7c79b-119">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="7c79b-120">您可以在 [ [自動轉寄的郵件] 報告](mfi-auto-forwarded-messages-report.md)中看到自動轉送郵件至外部收件者之使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7c79b-120">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="7c79b-121">輸出垃圾郵件篩選原則設定如何使用其他自動電子郵件轉接控制項</span><span class="sxs-lookup"><span data-stu-id="7c79b-121">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="7c79b-122">若您是系統管理員，您可能已經設定其他控制項，以允許或封鎖自動電子郵件轉發。</span><span class="sxs-lookup"><span data-stu-id="7c79b-122">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="7c79b-123">例如：</span><span class="sxs-lookup"><span data-stu-id="7c79b-123">For example:</span></span>

- <span data-ttu-id="7c79b-124">可允許或封鎖自動將電子郵件轉寄至部分或所有外部網域的[遠端網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains)。</span><span class="sxs-lookup"><span data-stu-id="7c79b-124">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="7c79b-125">Exchange [郵件流程規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 中的條件和動作 (也稱為傳輸規則) 偵測並封鎖自動轉寄的郵件至外部收件者。</span><span class="sxs-lookup"><span data-stu-id="7c79b-125">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="7c79b-126">遠端網域設定和郵件流程規則獨立于輸出垃圾郵件篩選原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="7c79b-126">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="7c79b-127">例如：</span><span class="sxs-lookup"><span data-stu-id="7c79b-127">For example:</span></span>

- <span data-ttu-id="7c79b-128">您允許遠端網域的自動轉寄，但是會封鎖輸出垃圾郵件篩選原則中的自動轉送。</span><span class="sxs-lookup"><span data-stu-id="7c79b-128">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="7c79b-129">在此範例中，自動轉寄的郵件會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="7c79b-129">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="7c79b-130">您可以在輸出垃圾郵件篩選原則中允許自動轉寄，但您可以使用郵件流程規則或遠端網域設定封鎖自動轉寄的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7c79b-130">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="7c79b-131">在此範例中，郵件流程規則或遠端網域設定會封鎖自動轉寄的郵件。</span><span class="sxs-lookup"><span data-stu-id="7c79b-131">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="7c79b-132">這種功能的獨立功能可讓您 (例如，) 允許在輸出垃圾郵件篩選原則中自動轉寄，但使用遠端網域來控制使用者可以轉寄郵件的外部網域。</span><span class="sxs-lookup"><span data-stu-id="7c79b-132">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="7c79b-133">封鎖的電子郵件轉發郵件</span><span class="sxs-lookup"><span data-stu-id="7c79b-133">The blocked email forwarding message</span></span>

<span data-ttu-id="7c79b-134">當以自動轉寄方式偵測到郵件，而組織原則 *封鎖* 該活動時，郵件會在包含下列資訊的 NDR 中傳回給寄件者：</span><span class="sxs-lookup"><span data-stu-id="7c79b-134">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
