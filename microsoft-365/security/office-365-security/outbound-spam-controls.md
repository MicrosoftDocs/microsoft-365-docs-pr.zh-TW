---
title: 輸出垃圾郵件保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 中的外寄垃圾郵件控制項，以及在您需要傳送大宗郵件時要執行的動作。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0fb6bfe5d83c551c0a93cc7b453b27a2d7b476bc
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538732"
---
# <a name="outbound-spam-protection-in-eop"></a><span data-ttu-id="46e96-103">EOP 中的外寄垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="46e96-103">Outbound spam protection in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="46e96-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="46e96-104">**Applies to**</span></span>
- [<span data-ttu-id="46e96-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="46e96-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="46e96-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="46e96-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="46e96-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="46e96-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="46e96-108">在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織若沒有 Exchange Online 信箱，我們會認真管理輸出垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="46e96-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, we take managing outbound spam seriously.</span></span> <span data-ttu-id="46e96-109">即使一個客戶有意或無意地從其組織傳送垃圾郵件，該動作可能會降低整個服務的信譽，並可能影響其他客戶的電子郵件傳遞。</span><span class="sxs-lookup"><span data-stu-id="46e96-109">Even if one customer intentionally or unintentionally sends spam from their organization, that action can degrade the reputation of the whole service and can affect email delivery for other customers.</span></span>

<span data-ttu-id="46e96-110">本文說明設計用來協助防止輸出垃圾郵件的控制項和通知，以及您在需要傳送大宗郵件時可以採取的動作。</span><span class="sxs-lookup"><span data-stu-id="46e96-110">This article describes the controls and notifications that are designed to help prevent outbound spam, and what you can do if you need to send mass mailings.</span></span>

## <a name="what-admins-can-do-to-control-outbound-spam"></a><span data-ttu-id="46e96-111">管理員可控制輸出垃圾郵件的工作</span><span class="sxs-lookup"><span data-stu-id="46e96-111">What admins can do to control outbound spam</span></span>

- <span data-ttu-id="46e96-112">**使用內建通知**：當使用者超過傳送限制的 [服務](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 或 [輸出垃圾郵件原則](configure-the-outbound-spam-policy.md) ，且限制傳送電子郵件時，名為「 **使用者限制傳送電子郵件** 的預設警示原則」會傳送電子郵件通知給 **TenantAdmins** (**Global admins**) 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="46e96-112">**Use built-in notifications**: When a user exceeds sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) and is restricted from sending email, the default alert policy named **User restricted from sending email** sends email notifications to members of the **TenantAdmins** (**Global admins**) group.</span></span> <span data-ttu-id="46e96-113">若要設定接收這些通知的人員，請參閱 [驗證受限使用者的警示設定](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="46e96-113">To configure who else receives these notifications, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="46e96-114">此外，已 **超過名稱電子郵件傳送限制** 的預設警示原則，以及 **可疑的電子郵件傳送模式** ，偵測到 **TenantAdmins** (**Global admins**) 群組的成員傳送電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="46e96-114">Also, the default alert policies named **Email sending limit exceeded** and **Suspicious email sending patterns detected** send email notifications to members of the **TenantAdmins** (**Global admins**) group.</span></span> <span data-ttu-id="46e96-115">如需警示原則的詳細資訊，請參閱[Microsoft 365 中的警示原則](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="46e96-115">For more information about alert policies, see [Alert policies in Microsoft 365](../../compliance/alert-policies.md).</span></span>

- <span data-ttu-id="46e96-116">**複查來自協力廠商電子郵件提供者的垃圾郵件**：許多電子郵件服務（如 Outlook .com、Yahoo 和 AOL）都提供回應迴圈，在此情況下，如果服務中的任何使用者將電子 Microsoft 365 郵件標記為垃圾郵件，則會將郵件打包並送回我們進行審閱。</span><span class="sxs-lookup"><span data-stu-id="46e96-116">**Review spam complaints from third-party email providers**: Many email services like Outlook.com, Yahoo, and AOL provide a feedback loop where if any user in their service marks an email from Microsoft 365 as spam, the message is packaged up and sent back to us for review.</span></span> <span data-ttu-id="46e96-117">若要深入瞭解 Outlook .com 的寄件者支援，請移至 <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="46e96-117">To learn more about sender support for Outlook.com, go to <https://sendersupport.olc.protection.outlook.com/pm/services.aspx>.</span></span>

## <a name="how-eop-controls-outbound-spam"></a><span data-ttu-id="46e96-118">EOP 如何控制輸出垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="46e96-118">How EOP controls outbound spam</span></span>

- <span data-ttu-id="46e96-119">**輸出電子郵件流量的隔離**：掃描透過服務傳送的每個輸出郵件是否有垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="46e96-119">**Segregation of outbound email traffic**: Every outbound message that's sent through the service is scanned for spam.</span></span> <span data-ttu-id="46e96-120">如果將郵件決定為垃圾郵件，則會從名為「 _高風險傳遞集_ 區」的次要、較著名的 IP 位址集區傳遞。</span><span class="sxs-lookup"><span data-stu-id="46e96-120">If the message is determined to be spam, it's delivered from a secondary, less reputable IP address pool named the _high-risk delivery pool_.</span></span> <span data-ttu-id="46e96-121">如需詳細資訊，請參閱[外寄郵件的較高風險傳遞集區](high-risk-delivery-pool-for-outbound-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="46e96-121">For more information, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>

- <span data-ttu-id="46e96-122">**監視來源 IP 位址信譽**： Microsoft 365 查詢各種協力廠商 ip 封鎖清單。</span><span class="sxs-lookup"><span data-stu-id="46e96-122">**Monitoring our source IP address reputation**: Microsoft 365 queries various third-party IP block lists.</span></span> <span data-ttu-id="46e96-123">如果此清單上出現用於輸出電子郵件的任何 IP 位址，就會產生警示。</span><span class="sxs-lookup"><span data-stu-id="46e96-123">An alert is generated if any of the IP addresses that we use for outbound email appear on these lists.</span></span> <span data-ttu-id="46e96-124">這種監視功能可讓我們在垃圾郵件導致聲譽降低時，快速反應。</span><span class="sxs-lookup"><span data-stu-id="46e96-124">This monitoring allows us to react quickly when spam has caused our reputation to degrade.</span></span> <span data-ttu-id="46e96-125">警示產生時，我們會提供內部檔，說明如何從封鎖清單中移除 delisted)  (的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="46e96-125">When an alert is generated, we have internal documentation that outlines how to get our IP addresses remove (delisted) from block lists.</span></span>

- <span data-ttu-id="46e96-126">**停用傳送太多垃圾郵件的帳戶** <sup>\*</sup> ：即使我們會將輸出的垃圾郵件分割成高風險傳遞集區，我們也無法允許帳戶 (經常) 傳送垃圾郵件的帳戶。</span><span class="sxs-lookup"><span data-stu-id="46e96-126">**Disable accounts that send too much spam**<sup>\*</sup>: Even though we segregate outbound spam into the high-risk delivery pool, we can't allow an account (often, a compromised account) to send spam indefinitely.</span></span> <span data-ttu-id="46e96-127">我們會監控傳送垃圾郵件的帳戶，當郵件超過 undisclosed 限制時，系統會封鎖該帳戶傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="46e96-127">We monitor accounts that are sending spam, and when they exceed an undisclosed limit, the account is blocked from sending email.</span></span> <span data-ttu-id="46e96-128">個別使用者和整個承租人各有不同的臨界值。</span><span class="sxs-lookup"><span data-stu-id="46e96-128">There are different thresholds for individual users and the entire tenant.</span></span>

- <span data-ttu-id="46e96-129">**停用傳送太高電子郵件的帳戶太快** <sup>\*</sup> ：除了對標示為垃圾郵件的郵件限制以外，當郵件達到整體輸出郵件限制時，也有限制會封鎖帳戶，而不論輸出郵件中的垃圾郵件篩選是否正確。</span><span class="sxs-lookup"><span data-stu-id="46e96-129">**Disabling accounts that send too much email too quickly**<sup>\*</sup>: In addition to the limits that look for messages marked as spam, there are also limits that block accounts when they reach an overall outbound message limit, regardless the spam filtering verdict on the outbound messages.</span></span> <span data-ttu-id="46e96-130">已遭破壞的帳戶可能會傳送零天的 (，但先前未辨識) 垃圾郵件篩選器錯過的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="46e96-130">A compromised account could send zero-day (previously unrecognized) spam that is missed by the spam filter.</span></span> <span data-ttu-id="46e96-131">由於很難識別合法大宗郵件活動與垃圾郵件活動，因此這些限制可協助您降低任何可能的損毀。</span><span class="sxs-lookup"><span data-stu-id="46e96-131">Because it can be difficult to identify a legitimate mass mailing campaign vs. a spam campaign, these limits help to minimize any potential damage.</span></span>

<span data-ttu-id="46e96-132"><sup>\*</sup> 我們不會通告確切的限制，因此垃圾郵件製造者無法在系統上玩遊戲，因此我們可以視需要增加或減少限制。</span><span class="sxs-lookup"><span data-stu-id="46e96-132"><sup>\*</sup> We don't advertise the exact limits so spammers can't game the system, and so we can increase or decrease the limits as necessary.</span></span> <span data-ttu-id="46e96-133">這類限制可讓平均的企業使用者超過平均的使用程度，而且可提供足夠低的程度，以協助包含垃圾郵件製造者造成的損毀。</span><span class="sxs-lookup"><span data-stu-id="46e96-133">The limits are high enough to prevent an average business user from ever exceeding them, and low enough to help contain the damage caused by a spammer.</span></span>

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a><span data-ttu-id="46e96-134">建議若要透過 EOP 傳送大宗郵件的客戶</span><span class="sxs-lookup"><span data-stu-id="46e96-134">Recommendations for customers who want to send mass mailings through EOP</span></span>

<span data-ttu-id="46e96-135">在想要傳送大量電子郵件的客戶之間，您很難進行平衡，而不是使用不良的收件者購買做法，保護服務免受遭到攻破的帳戶和大量電子郵件寄件者。</span><span class="sxs-lookup"><span data-stu-id="46e96-135">It's difficult to strike a balance between customers who want to send a large volume of email vs. protecting the service from compromised accounts and bulk email senders with poor recipient acquisition practices.</span></span> <span data-ttu-id="46e96-136">在協力廠商 IP 封鎖清單上 Microsoft 365 電子郵件來源平臺的成本，大於封鎖傳送太多電子郵件的使用者。</span><span class="sxs-lookup"><span data-stu-id="46e96-136">The cost of a Microsoft 365 email source landing on a third-party IP block list is greater than blocking a user who's sending too much email.</span></span>

<span data-ttu-id="46e96-137">如[Exchange Online 服務描述](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)所述，在使用 EOP 傳送大量電子郵件時，不支援使用服務，而且只允許以「最大努力」為基礎。</span><span class="sxs-lookup"><span data-stu-id="46e96-137">As described in the [Exchange Online Service Description](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), using EOP to send bulk email is not a supported use of the service, and is only permitted on a "best-effort" basis.</span></span> <span data-ttu-id="46e96-138">若客戶想要傳送大量電子郵件，建議您執行下列解決方案：</span><span class="sxs-lookup"><span data-stu-id="46e96-138">For customers who do want to send bulk email, we recommend the following solutions:</span></span>

- <span data-ttu-id="46e96-139">**透過內部部署電子郵件伺服器傳送大量電子郵件**：客戶會維護自己的電子郵件基礎結構，以進行大宗郵件。</span><span class="sxs-lookup"><span data-stu-id="46e96-139">**Send bulk email through on-premises email servers**: Customers maintain their own email infrastructure for mass mailings.</span></span>

- <span data-ttu-id="46e96-140">**使用協力廠商大量電子郵件提供者**：您可以使用多個協力廠商大量電子郵件解決方案提供者來傳送大宗郵件。</span><span class="sxs-lookup"><span data-stu-id="46e96-140">**Use a third-party bulk email provider**: There are several third-party bulk email solution providers that you can use to send mass mailings.</span></span> <span data-ttu-id="46e96-141">這些公司的利益與客戶合作，以確保電子郵件傳送慣例良好的 vested。</span><span class="sxs-lookup"><span data-stu-id="46e96-141">These companies have a vested interest in working with customers to ensure good email sending practices.</span></span>

<span data-ttu-id="46e96-142">郵件、行動裝置、惡意程式碼抗濫用的運作群組 (MAAWG) 會發佈其成員資格名單，網址為 <https://www.maawg.org/about/roster> 。</span><span class="sxs-lookup"><span data-stu-id="46e96-142">The Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publishes its membership roster at <https://www.maawg.org/about/roster>.</span></span> <span data-ttu-id="46e96-143">有幾個大量的電子郵件提供者在清單中，而且也稱為「負責的網際網路公民」。</span><span class="sxs-lookup"><span data-stu-id="46e96-143">Several bulk email providers are on the list, and are known to be responsible internet citizens.</span></span>
