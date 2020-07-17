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
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080110"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="7d119-103">在 Office 365 中設定外部電子郵件轉發功能</span><span class="sxs-lookup"><span data-stu-id="7d119-103">Configuring external email forwarding in Office 365</span></span>

<span data-ttu-id="7d119-104">外部轉送是由*輸出反垃圾郵件原則*所控制，並根據設定的設定範圍限定為使用者。</span><span class="sxs-lookup"><span data-stu-id="7d119-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="7d119-105">目前支援的設定如下：</span><span class="sxs-lookup"><span data-stu-id="7d119-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="7d119-106">**自動**–在這種模式下，系統負責決定是否允許轉寄的郵件。</span><span class="sxs-lookup"><span data-stu-id="7d119-106">**Automatic** – In this mode the system is responsible for deciding if a forwarded message is allowed or not.</span></span>  <span data-ttu-id="7d119-107">這是預設模式，在這種模式下，系統會封鎖自動外部轉送。</span><span class="sxs-lookup"><span data-stu-id="7d119-107">This is the default mode and in this mode the system will block automatic external forwarding.</span></span>

- <span data-ttu-id="7d119-108">**開啟**-允許和不限制自動外部轉送。</span><span class="sxs-lookup"><span data-stu-id="7d119-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="7d119-109">**Off** –會停用自動外部轉送，並會導致使用者未傳遞回報（NDR）。</span><span class="sxs-lookup"><span data-stu-id="7d119-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="7d119-110">如需如何設定這些設定的詳細資訊，請參閱[設定 EOP 中的外寄垃圾郵件篩選](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="7d119-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) for more information on how to configure these settings.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="7d119-111">控制外部電子郵件轉發</span><span class="sxs-lookup"><span data-stu-id="7d119-111">Controlling external email forwarding</span></span>

<span data-ttu-id="7d119-112">做為組織的系統管理員，您可能需要限制或控制誰可以使用收件匣規則或在組織外部的 SMTP 轉寄功能，自動轉寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7d119-112">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="7d119-113">電子郵件轉寄可能是一項非常實用的功能，但也可以透過可能披露的資訊來帶來風險，即使是提供可被攻擊者攻擊組織或其合作夥伴的資訊也是一樣的。</span><span class="sxs-lookup"><span data-stu-id="7d119-113">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="7d119-114">Office 365 不允許由收件匣規則或信箱設定自動進行外部轉送，這會提供安全的預設原則。</span><span class="sxs-lookup"><span data-stu-id="7d119-114">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="7d119-115">不過，系統管理員可以針對組織中的所有使用者或部分使用者修改這些設定。</span><span class="sxs-lookup"><span data-stu-id="7d119-115">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="7d119-116">在內部使用者之間轉發郵件不會受到這類修改的影響。</span><span class="sxs-lookup"><span data-stu-id="7d119-116">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="7d119-117">停用 Office 365 中的自動轉寄外部地址時，將會逐步顯示詳細資訊透過[訊息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter)文章進行通訊。</span><span class="sxs-lookup"><span data-stu-id="7d119-117">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="7d119-118">若要協助系統管理員準備這些變更，請提前修改原則，以確保使用者沒有任何中斷。</span><span class="sxs-lookup"><span data-stu-id="7d119-118">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="7d119-119">您組織中使用自動轉寄（收件匣規則或 SMTP 轉寄）使用者的詳細資訊，可在 [[自動轉寄的郵件] 報告](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide)中找到。</span><span class="sxs-lookup"><span data-stu-id="7d119-119">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="7d119-120">封鎖的電子郵件轉發郵件</span><span class="sxs-lookup"><span data-stu-id="7d119-120">The blocked email forwarding message</span></span>

<span data-ttu-id="7d119-121">當以自動轉寄方式偵測到郵件時，會將**未傳遞回報（NDR）** 的組織原則*封鎖*給使用者。</span><span class="sxs-lookup"><span data-stu-id="7d119-121">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="7d119-122">報告會指出郵件未傳遞。</span><span class="sxs-lookup"><span data-stu-id="7d119-122">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="7d119-123">NDR 會有下列格式：</span><span class="sxs-lookup"><span data-stu-id="7d119-123">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
