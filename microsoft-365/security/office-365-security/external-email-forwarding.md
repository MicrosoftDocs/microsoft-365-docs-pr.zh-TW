---
title: 設定及控制外部電子郵件轉寄、自動轉寄、拒絕5.7.520 存取、停用外部轉寄、系統管理員已停用外部轉寄、輸出反垃圾郵件原則
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: f729aa816caf8fb07499037ee27fbfc37b7205b3
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202876"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="36a8b-103">在 Office 365 中設定外部電子郵件轉發功能</span><span class="sxs-lookup"><span data-stu-id="36a8b-103">Configuring external email forwarding in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="36a8b-104">外部轉送是由 *輸出反垃圾郵件原則* 所控制，並根據設定的設定範圍限定為使用者。</span><span class="sxs-lookup"><span data-stu-id="36a8b-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="36a8b-105">目前支援的設定如下：</span><span class="sxs-lookup"><span data-stu-id="36a8b-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="36a8b-106">**自動** –在這種模式下，系統負責決定是否允許轉寄的郵件。</span><span class="sxs-lookup"><span data-stu-id="36a8b-106">**Automatic** – In this mode the system is responsible for deciding if a forwarded message is allowed or not.</span></span>  <span data-ttu-id="36a8b-107">這是預設模式，在這種模式下，系統會封鎖自動外部轉送。</span><span class="sxs-lookup"><span data-stu-id="36a8b-107">This is the default mode and in this mode the system will block automatic external forwarding.</span></span>

- <span data-ttu-id="36a8b-108">**開啟** -允許和不限制自動外部轉送。</span><span class="sxs-lookup"><span data-stu-id="36a8b-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="36a8b-109">**Off** –會停用自動外部轉送，並且會產生未傳遞回報 (NDR) 給使用者。</span><span class="sxs-lookup"><span data-stu-id="36a8b-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="36a8b-110">如需如何設定這些設定的詳細資訊，請參閱 [設定 EOP 中的外寄垃圾郵件篩選](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) 。</span><span class="sxs-lookup"><span data-stu-id="36a8b-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) for more information on how to configure these settings.</span></span>

> [!NOTE]
> <span data-ttu-id="36a8b-111">停用自動轉送也會 dsable 將郵件重新導向至外部地址的收件匣規則。</span><span class="sxs-lookup"><span data-stu-id="36a8b-111">Disabling automatic forwarding will also dsable Inbox rules that redirect messages to external addresses.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="36a8b-112">控制外部電子郵件轉發</span><span class="sxs-lookup"><span data-stu-id="36a8b-112">Controlling external email forwarding</span></span>

<span data-ttu-id="36a8b-113">做為組織的系統管理員，您可能需要限制或控制誰可以使用收件匣規則或在組織外部的 SMTP 轉寄功能，自動轉寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="36a8b-113">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="36a8b-114">電子郵件轉寄可能是一項非常實用的功能，但也可以透過可能披露的資訊來帶來風險，即使是提供可被攻擊者攻擊組織或其合作夥伴的資訊也是一樣的。</span><span class="sxs-lookup"><span data-stu-id="36a8b-114">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="36a8b-115">Office 365 不允許由收件匣規則或信箱設定自動進行外部轉送，這會提供安全的預設原則。</span><span class="sxs-lookup"><span data-stu-id="36a8b-115">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="36a8b-116">不過，系統管理員可以針對組織中的所有使用者或部分使用者修改這些設定。</span><span class="sxs-lookup"><span data-stu-id="36a8b-116">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="36a8b-117">在內部使用者之間轉發郵件不會受到這類修改的影響。</span><span class="sxs-lookup"><span data-stu-id="36a8b-117">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="36a8b-118">停用 Office 365 中的自動轉寄外部地址時，將會逐步顯示詳細資訊透過 [訊息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) 文章進行通訊。</span><span class="sxs-lookup"><span data-stu-id="36a8b-118">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="36a8b-119">若要協助系統管理員準備這些變更，請提前修改原則，以確保使用者沒有任何中斷。</span><span class="sxs-lookup"><span data-stu-id="36a8b-119">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="36a8b-120">在您組織中使用自動轉寄 (收件匣規則或 SMTP 轉送) 使用者的詳細資訊，可以在 [ [自動轉寄的郵件] 報告](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true)中找到。</span><span class="sxs-lookup"><span data-stu-id="36a8b-120">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span></span>

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a><span data-ttu-id="36a8b-121">這個原則如何與其他自動轉寄控制項搭配使用</span><span class="sxs-lookup"><span data-stu-id="36a8b-121">How does this policy work with other automatic forwarding controls</span></span>

<span data-ttu-id="36a8b-122">身為系統管理員，您可能已經有其他類型的控制項，例如封鎖 [遠端網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) 中的自動轉送，以及使用 Exchange Transport RULE (ETR) 。</span><span class="sxs-lookup"><span data-stu-id="36a8b-122">As an admin, you may already have other types of controls in place, such blocking automatic forwarding in [remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) and the use of an Exchange Transport Rule (ETR).</span></span> <span data-ttu-id="36a8b-123">這兩個控制項都獨立于此特定功能，例如，如果允許遠端網域的自動轉寄，但透過輸出垃圾郵件原則封鎖自動轉寄，結果將會封鎖自動轉寄的郵件。</span><span class="sxs-lookup"><span data-stu-id="36a8b-123">Both of these controls are independent of this particular feature, for example if you allow automatic forwarding for a remote domain, but block automatic forwarding via the outbound spam policy the result will be that the automatically forwarded message is blocked.</span></span> <span data-ttu-id="36a8b-124">同樣地，如果您允許在輸出垃圾郵件原則中自動轉寄，但在 ETR 或遠端網域中封鎖它，則這兩個控制項中的任何一個都會封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="36a8b-124">Similarly if you allow automatic forwarding in the outbound spam policy but block it in an ETR or remote domain then the message will be blocked by either of these controls.</span></span> <span data-ttu-id="36a8b-125">例如，您可以讓您在輸出垃圾郵件原則中允許自動轉寄，並利用遠端網域來控制使用者可以自動轉寄郵件的網域。</span><span class="sxs-lookup"><span data-stu-id="36a8b-125">This allows you to, for example, allow automatic forwarding in the outbound spam policy and utilize remote domains to control the domains that users can automatic forward messages to.</span></span>


## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="36a8b-126">封鎖的電子郵件轉發郵件</span><span class="sxs-lookup"><span data-stu-id="36a8b-126">The blocked email forwarding message</span></span>

<span data-ttu-id="36a8b-127">當以自動轉寄方式偵測到郵件 *時，如果* 有未傳遞回報的活動 \*\* (NDR) \*\* 會產生給使用者。</span><span class="sxs-lookup"><span data-stu-id="36a8b-127">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="36a8b-128">報告會指出郵件未傳遞。</span><span class="sxs-lookup"><span data-stu-id="36a8b-128">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="36a8b-129">NDR 會有下列格式：</span><span class="sxs-lookup"><span data-stu-id="36a8b-129">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
