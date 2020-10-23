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
ms.openlocfilehash: c1a7cd4d8f00c9e2433601903efd1fba7bb587f9
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681729"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="60f79-103">在 Microsoft 365 中控制自動外部電子郵件轉接</span><span class="sxs-lookup"><span data-stu-id="60f79-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="60f79-104">身為系統管理員，您可能會有公司需求，以限制或控制自動轉寄的郵件至外部收件者 (組織外) 收件者。</span><span class="sxs-lookup"><span data-stu-id="60f79-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="60f79-105">電子郵件轉寄可能非常有用，但由於可能洩漏資訊，也可能會造成安全性風險。</span><span class="sxs-lookup"><span data-stu-id="60f79-105">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="60f79-106">攻擊者可能會利用此資訊來攻擊您的組織或合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="60f79-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="60f79-107">Microsoft 365 提供下列自動轉送類型：</span><span class="sxs-lookup"><span data-stu-id="60f79-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="60f79-108">使用者可以設定 [收件匣規則](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) ，自動將郵件轉寄給外部寄件者 (故意或因遭到破壞的帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="60f79-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="60f79-109">系統管理員可以設定 [信箱轉送](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (又稱為 SMTP 轉送) ，以自動將郵件轉寄給外部收件者。</span><span class="sxs-lookup"><span data-stu-id="60f79-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as SMTP forwarding) to automatically forward messages to external recipients.</span></span>

<span data-ttu-id="60f79-110">您可以使用輸出垃圾郵件篩選原則來控制自動轉寄給外部收件者。</span><span class="sxs-lookup"><span data-stu-id="60f79-110">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="60f79-111">有三個可用的設定：</span><span class="sxs-lookup"><span data-stu-id="60f79-111">Three settings are available:</span></span>

- <span data-ttu-id="60f79-112">**自動**：封鎖自動外部轉送。</span><span class="sxs-lookup"><span data-stu-id="60f79-112">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="60f79-113">內部自動轉送郵件功能將繼續運作。</span><span class="sxs-lookup"><span data-stu-id="60f79-113">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="60f79-114">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="60f79-114">This is the default setting.</span></span>
- <span data-ttu-id="60f79-115">**開啟**：允許和不限制自動外部轉送。</span><span class="sxs-lookup"><span data-stu-id="60f79-115">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="60f79-116">**Off**：停用自動外部轉寄，將會造成未傳遞回報 (也稱為 NDR 或退回的郵件) 傳送給寄件者。</span><span class="sxs-lookup"><span data-stu-id="60f79-116">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="60f79-117">如需如何設定這些設定的指示，請參閱 [CONFIGURE EOP 中的外寄垃圾郵件篩選](configure-the-outbound-spam-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="60f79-117">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

<span data-ttu-id="60f79-118">**附註**：</span><span class="sxs-lookup"><span data-stu-id="60f79-118">**Notes**:</span></span>

- <span data-ttu-id="60f79-119">停用自動轉送也會停用將郵件重新導向至外部地址的收件匣規則。</span><span class="sxs-lookup"><span data-stu-id="60f79-119">Disabling automatic forwarding will also disable Inbox rules that redirect messages to external addresses.</span></span>

- <span data-ttu-id="60f79-120">內部使用者之間的自動轉送郵件不會受到輸出垃圾郵件篩選原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="60f79-120">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>

- <span data-ttu-id="60f79-121">您可以在 [ [自動轉寄的郵件] 報告](mfi-auto-forwarded-messages-report.md)中看到自動轉送郵件至外部收件者之使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="60f79-121">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="60f79-122">輸出垃圾郵件篩選原則設定如何使用其他自動電子郵件轉接控制項</span><span class="sxs-lookup"><span data-stu-id="60f79-122">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="60f79-123">若您是系統管理員，您可能已經設定其他控制項，以允許或封鎖自動電子郵件轉發。</span><span class="sxs-lookup"><span data-stu-id="60f79-123">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="60f79-124">例如：</span><span class="sxs-lookup"><span data-stu-id="60f79-124">For example:</span></span>

- <span data-ttu-id="60f79-125">可允許或封鎖自動將電子郵件轉寄至部分或所有外部網域的[遠端網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains)。</span><span class="sxs-lookup"><span data-stu-id="60f79-125">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>
- <span data-ttu-id="60f79-126">Exchange [郵件流程規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 中的條件和動作 (也稱為傳輸規則) 偵測並封鎖自動轉寄的郵件至外部收件者。</span><span class="sxs-lookup"><span data-stu-id="60f79-126">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="60f79-127">遠端網域設定和郵件流程規則獨立于輸出垃圾郵件篩選原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="60f79-127">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="60f79-128">例如：</span><span class="sxs-lookup"><span data-stu-id="60f79-128">For example:</span></span>

- <span data-ttu-id="60f79-129">您允許遠端網域的自動轉寄，但是會封鎖輸出垃圾郵件篩選原則中的自動轉送。</span><span class="sxs-lookup"><span data-stu-id="60f79-129">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="60f79-130">在此範例中，自動轉寄的郵件會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="60f79-130">In this example, automatically forwarded messages are blocked.</span></span>
- <span data-ttu-id="60f79-131">您可以在輸出垃圾郵件篩選原則中允許自動轉寄，但您可以使用郵件流程規則或遠端網域設定封鎖自動轉寄的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="60f79-131">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="60f79-132">在此範例中，郵件流程規則或遠端網域設定會封鎖自動轉寄的郵件。</span><span class="sxs-lookup"><span data-stu-id="60f79-132">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="60f79-133">這種功能的獨立功能可讓您 (例如，) 允許在輸出垃圾郵件篩選原則中自動轉寄，但使用遠端網域來控制使用者可以轉寄郵件的外部網域。</span><span class="sxs-lookup"><span data-stu-id="60f79-133">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="60f79-134">封鎖的電子郵件轉發郵件</span><span class="sxs-lookup"><span data-stu-id="60f79-134">The blocked email forwarding message</span></span>

<span data-ttu-id="60f79-135">當以自動轉寄方式偵測到郵件，而組織原則 *封鎖* 該活動時，郵件會在包含下列資訊的 NDR 中傳回給寄件者：</span><span class="sxs-lookup"><span data-stu-id="60f79-135">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
