---
title: Exchange Online Protection 概觀
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解 Microsoft Exchange Online Protection （EOP），以及它如何協助保護您的組織抵禦垃圾郵件和惡意程式碼。
ms.openlocfilehash: 4630c58bef49f13a1ae1536336afbac170418dcc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036521"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="b90fa-103">Exchange Online Protection 概觀</span><span class="sxs-lookup"><span data-stu-id="b90fa-103">Exchange Online Protection overview</span></span>

<span data-ttu-id="b90fa-p101">Microsoft Exchange Online Protection (EOP) 是雲端式的電子郵件篩選服務，它能協助組織抵禦垃圾郵件和惡意軟體，同時也包括預防組織發生訊息原則違規的功能。EOP 能簡化訊息環境的管理，減輕維護內部部署硬體和軟體所衍生的繁重負擔。</span><span class="sxs-lookup"><span data-stu-id="b90fa-p101">Microsoft Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware, and includes features to safeguard your organization from messaging-policy violations. EOP can simplify the management of your messaging environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>

<span data-ttu-id="b90fa-106">下列清單說明您可以使用 EOP 來保護郵件的方法：</span><span class="sxs-lookup"><span data-stu-id="b90fa-106">The following list describes how you can use EOP for messaging protection:</span></span>

- <span data-ttu-id="b90fa-107">**在獨立案例中**：EOP 會為您的內部部署、Exchange 組織，或任何其他內部部署 SMTP 電子郵件解決方案，提供雲端式電子郵件保護。</span><span class="sxs-lookup"><span data-stu-id="b90fa-107">**In a standalone scenario**: EOP provides cloud-based email protection for your on-premises Exchange organization or for any other on-premises SMTP email solution.</span></span>

- <span data-ttu-id="b90fa-108">**作為 Exchange Online 的一部分**：EOP 是 Exchange Online 和 Office 365 中雲端託管信箱的內建保護。</span><span class="sxs-lookup"><span data-stu-id="b90fa-108">**As a part of Exchange Online**: EOP is the built-in protection for cloud-hosted mailboxes in Exchange Online and Office 365.</span></span> <span data-ttu-id="b90fa-109">請參閱[防禦威脅](protect-against-threats.md)，協助您設定 Exchange Online 的功能。</span><span class="sxs-lookup"><span data-stu-id="b90fa-109">See [Protect against threats](protect-against-threats.md) for help configuring these Exchange Online capabilities.</span></span>

- <span data-ttu-id="b90fa-110">**在混合式部署中**：EOP 可以設定為保護您的郵件環境，並在您混合使用內部部署及雲端信箱時控制郵件路由傳送。</span><span class="sxs-lookup"><span data-stu-id="b90fa-110">**In a hybrid deployment**: EOP can be configured to protect your messaging environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="b90fa-111">這些 Exchange Online Protection 文章適用於混合式和內部部署環境。</span><span class="sxs-lookup"><span data-stu-id="b90fa-111">These Exchange Online Protection articles apply to hybrid and on-premises environments.</span></span>

## <a name="how-eop-works"></a><span data-ttu-id="b90fa-112">EOP 的運作方式</span><span class="sxs-lookup"><span data-stu-id="b90fa-112">How EOP works</span></span>

<span data-ttu-id="b90fa-113">若要了解 EOP 的運作方式，查看它如何處理傳入電子郵件很有幫助：</span><span class="sxs-lookup"><span data-stu-id="b90fa-113">To understand how EOP works, it helps to see how it processes incoming email:</span></span>

![電子郵件流程圖。](../../media/GitHubBugs/emailprocessingineop1.png)

<span data-ttu-id="b90fa-115">傳入郵件最初會通過連線篩選，此篩選會檢查寄件者的信譽，並檢查郵件是否有惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="b90fa-115">An incoming message initially passes through connection filtering, which checks the sender's reputation and inspects the message for malware.</span></span> <span data-ttu-id="b90fa-116">大部分垃圾郵件都會在此時遭到阻止並由 EOP 刪除。</span><span class="sxs-lookup"><span data-stu-id="b90fa-116">The majority of spam is stopped at this point and deleted by EOP.</span></span> <span data-ttu-id="b90fa-117">郵件會繼續通過原則篩選，在此篩選中，會以從範本建立或強制執行的自訂郵件流程規則 (又稱為傳輸規則) 評估郵件。</span><span class="sxs-lookup"><span data-stu-id="b90fa-117">Messages continue through policy filtering, where messages are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template.</span></span> <span data-ttu-id="b90fa-118">例如，您可能有一個規則，會在特定寄件者的郵件送達時，傳送通知給管理員。</span><span class="sxs-lookup"><span data-stu-id="b90fa-118">For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender.</span></span> <span data-ttu-id="b90fa-119">(如果您有這項功能，資料遺失防護檢查會在此時執行；請參閱 [Exchange Online Protection 服務描述](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。) 接著，郵件會通過內容篩選，在此篩選中，會檢查內容是否有垃圾郵件常見的術語或內容。</span><span class="sxs-lookup"><span data-stu-id="b90fa-119">(Data loss prevention checks also occur at this point, if you have that feature; for information about feature availability, see the [Exchange Online Protection service description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).) Next, messages pass through content filtering, where content is checked for terminology or properties common to spam.</span></span> <span data-ttu-id="b90fa-120">經內容篩選認定為垃圾郵件的郵件，可以傳送至使用者的 [垃圾郵件] 資料夾，或者根據您在其他選項 (包括收件匣或自訂資料夾) 中的設定傳送至隔離區。</span><span class="sxs-lookup"><span data-stu-id="b90fa-120">A message determined to be spam by the content filter can be sent to a user's Junk Email folder or to the quarantine, among other options (including Inbox or custom folder), based on your settings.</span></span> <span data-ttu-id="b90fa-121">郵件順利通過這些保護層後，即會傳遞給收件者。</span><span class="sxs-lookup"><span data-stu-id="b90fa-121">After a message passes all of these protection layers successfully, it's delivered to the recipient.</span></span>

### <a name="eop-datacenters"></a><span data-ttu-id="b90fa-122">EOP 資料中心</span><span class="sxs-lookup"><span data-stu-id="b90fa-122">EOP datacenters</span></span>

<span data-ttu-id="b90fa-p104">EOP 會在用於提供最佳可用性的全球資料中心網路上執行。例如，如果資料中心變成無法使用，則會將電子郵件自動路由傳送至其他資料中心，而不會中斷服務。每一個資料中心的伺服器都會代表您接受郵件，在您的組織與網際網路之間提供隔離層，進而減少伺服器上的負載。透過這個高可用性的網路，Microsoft 可以確保電子郵件及時送達您的組織。</span><span class="sxs-lookup"><span data-stu-id="b90fa-p104">EOP runs on a worldwide network of datacenters that are designed to provide the best availability. For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service. Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the Internet, thereby reducing load on your servers. Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span>

<span data-ttu-id="b90fa-p105">EOP 會在資料中心之間執行負載平衡，但只在一個區域內。如果您佈建在一個區域中，則會以該區域的郵件路由來處理您的所有郵件。下列清單顯示 EOP 資料中心的地區郵件路由運作方式：</span><span class="sxs-lookup"><span data-stu-id="b90fa-p105">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>

- <span data-ttu-id="b90fa-130">在歐洲、中東和非洲 (EMEA)，所有 Exchange Online 信箱都位於 EMEA 資料中心，且所有郵件都透過 EMEA 資料中心傳送供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="b90fa-130">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>

- <span data-ttu-id="b90fa-131">在亞太地區 (APAC)，所有 Exchange Online 信箱都位於 APAC 資料中心，且郵件目前透過 APAC 資料中心傳送供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="b90fa-131">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>

- <span data-ttu-id="b90fa-132">在美洲，所有的 Exchange Online 信箱都位於美國資料中心，除了南美洲是使用位於巴西和智利資料中心，以及加拿大使用位於加拿大資料中心。</span><span class="sxs-lookup"><span data-stu-id="b90fa-132">In the Americas, all Exchange Online mailboxes are located in U.S. datacenters, with the exception of South America where datacenters in Brazil and Chile are used and in Canada where datacenters in Canada are used.</span></span> <span data-ttu-id="b90fa-133">所有電子郵件訊息（包括南美洲和加拿大客戶的訊息）都透過本地資料中心路由，以進行 EOP 篩選；隔離的電子郵件會儲存在租用者所在的資料中心。</span><span class="sxs-lookup"><span data-stu-id="b90fa-133">All email messages, including messages for customers in South America and Canada, are routed through local datacenters for EOP filtering; quarantined email is stored in the datacenter where the tenant is located.</span></span>

- <span data-ttu-id="b90fa-134">至於政府社群雲端 (GCC)，所有 Exchange Online 信箱都位於美國資料中心，且所有郵件都透過美國資料中心傳送供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="b90fa-134">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>

## <a name="eop-plans-and-features"></a><span data-ttu-id="b90fa-135">EOP 方案和功能</span><span class="sxs-lookup"><span data-stu-id="b90fa-135">EOP plans and features</span></span>

<span data-ttu-id="b90fa-136">以下是可用的 EOP 訂閱方案：</span><span class="sxs-lookup"><span data-stu-id="b90fa-136">The available EOP subscription plans are:</span></span>

- <span data-ttu-id="b90fa-137">**獨立 EOP**：您可以註冊 EOP 以保護內部部署的電子郵件組織。</span><span class="sxs-lookup"><span data-stu-id="b90fa-137">**EOP standalone**: You enroll in EOP to protect your on-premises email organization.</span></span>

- <span data-ttu-id="b90fa-138">**Exchange Online 中的 EOP 功能**：任何包括 Exchange Online (獨立版或 Office 365 一部分) 的訂閱，都會使用 EOP 來保護您的 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="b90fa-138">**EOP features in Exchange Online**: Any subscription that includes Exchange Online (standalone or as part of Office 365) uses EOP to protect your Exchange Online mailboxes.</span></span>

- <span data-ttu-id="b90fa-139">\*\*Exchange Enterprise CAL (含服務) \*\*：如果您有內部部署的 Exchange 組織，且您已購買額外的 Exchange Enterprise CAL (含服務) 授權，EOP 會包含在服務中。</span><span class="sxs-lookup"><span data-stu-id="b90fa-139">**Exchange Enterprise CAL with Services**: If you have an on-premises Exchange organization where you've purchased additional Exchange Enterprise CAL with Services licenses, EOP is part of the included services.</span></span>

<span data-ttu-id="b90fa-140">如需所有 EOP 訂閱方案之需求、重要限制和功能可用性的相關資訊，請參閱 [Exchange Online Protection 服務描述](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="b90fa-140">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection service description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

## <a name="setting-up-eop"></a><span data-ttu-id="b90fa-141">設定 EOP</span><span class="sxs-lookup"><span data-stu-id="b90fa-141">Setting up EOP</span></span>

<span data-ttu-id="b90fa-p107">設定 EOP 可以很簡單，對於具有一些符合性規則的小型組織來說，更是如此。不過，如果您的組織是具有多個網域、自訂符合性規則或混合郵件流程的大型組織，則在進行設定時可能需要更加詳盡的規劃及更多的時間。</span><span class="sxs-lookup"><span data-stu-id="b90fa-p107">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>

<span data-ttu-id="b90fa-144">如果已購買 EOP，請參閱[設定 EOP 服務](set-up-your-eop-service.md)，以確保完成所有必要的 EOP 設定步驟，來保護郵件環境。</span><span class="sxs-lookup"><span data-stu-id="b90fa-144">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b90fa-145">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b90fa-145">For more information</span></span>

[<span data-ttu-id="b90fa-146">EOP 功能</span><span class="sxs-lookup"><span data-stu-id="b90fa-146">EOP features</span></span>](eop-features.md)

[<span data-ttu-id="b90fa-147">EOP 一般常見問題集</span><span class="sxs-lookup"><span data-stu-id="b90fa-147">EOP general FAQ</span></span>](eop-general-faq.md)

[<span data-ttu-id="b90fa-148">EOP 排入佇列、延後和退回的訊息常見問題集</span><span class="sxs-lookup"><span data-stu-id="b90fa-148">EOP queued, deferred, and bounced messages FAQ</span></span>](eop-queued-deferred-and-bounced-messages-faq.md)

[<span data-ttu-id="b90fa-149">委派管理常見問題集</span><span class="sxs-lookup"><span data-stu-id="b90fa-149">Delegated administration FAQ</span></span>](delegated-administration-faq.md)

[<span data-ttu-id="b90fa-150">將網域與設定從某個 EOP 組織移到另一個 EOP 組織</span><span class="sxs-lookup"><span data-stu-id="b90fa-150">Move domains and settings from one EOP organization to another EOP organization</span></span>](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
