---
title: EOP 一般常見問題集
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: 在本主題中，您將會看到有關 Microsoft Exchange Online Protection （EOP）雲端主控的電子郵件篩選服務最常見的一般問題。
ms.openlocfilehash: 48841e5e68dd560329eadc0a654e6d8fe1b2d09e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036557"
---
# <a name="eop-general-faq"></a><span data-ttu-id="5186a-103">EOP 一般常見問題集</span><span class="sxs-lookup"><span data-stu-id="5186a-103">EOP general FAQ</span></span>

<span data-ttu-id="5186a-p101">在這裡，我們將回答有關於 Microsoft Exchange Online Protection (EOP) 雲端電子郵件篩選服務的最常見一般問題。如需其他常見問題集 (FAQ) 主題，請前往下列連結：</span><span class="sxs-lookup"><span data-stu-id="5186a-p101">Here we answer the most common general questions about the Microsoft Exchange Online Protection (EOP) cloud-hosted email filtering service. For additional frequently asked questions (FAQ) topics, go to the following links:</span></span>

- [<span data-ttu-id="5186a-106">EOP 排入佇列、延後和退回的訊息常見問題集</span><span class="sxs-lookup"><span data-stu-id="5186a-106">EOP queued, deferred, and bounced messages FAQ</span></span>](eop-queued-deferred-and-bounced-messages-faq.md)

- [<span data-ttu-id="5186a-107">委派管理常見問題集</span><span class="sxs-lookup"><span data-stu-id="5186a-107">Delegated administration FAQ</span></span>](delegated-administration-faq.md)

- [<span data-ttu-id="5186a-108">反垃圾郵件保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="5186a-108">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

- [<span data-ttu-id="5186a-109">隔離常見問題集</span><span class="sxs-lookup"><span data-stu-id="5186a-109">Quarantine FAQ</span></span>](quarantine-faq.md)

- [<span data-ttu-id="5186a-110">反惡意程式碼保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="5186a-110">Anti-malware protection FAQ</span></span>](anti-malware-protection-faq-eop.md)

- [<span data-ttu-id="5186a-111">郵件追蹤常見問題集</span><span class="sxs-lookup"><span data-stu-id="5186a-111">Message Trace FAQ</span></span>](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

<span data-ttu-id="5186a-112">**問：EOP 是什麼？**</span><span class="sxs-lookup"><span data-stu-id="5186a-112">**Q. What is EOP?**</span></span>

<span data-ttu-id="5186a-p102">答：EOP 是雲端電子郵件篩選服務，專門用來保護客戶遠離垃圾郵件與惡意程式碼，以及執行自訂原則規則。</span><span class="sxs-lookup"><span data-stu-id="5186a-p102">A. EOP is a cloud-hosted email filtering service built to protect customers from spam and malware, and to implement custom policy rules.</span></span>

<span data-ttu-id="5186a-115">**問：如何註冊 EOP 試用版或購買 EOP？**</span><span class="sxs-lookup"><span data-stu-id="5186a-115">**Q. How do I sign up for an EOP trial or purchase EOP?**</span></span>

<span data-ttu-id="5186a-p103">答：可透過以下網址註冊 EOP 試用版或購買 EOP：[Exchange Online Protection 首頁](https://products.office.com/exchange/exchange-email-security-spam-protection)。請注意，試用購買的功能與付費訂閱版相同，但另外包含 [Exchange Enterprise CAL with Services](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) 訂閱方案提供的其他功能。</span><span class="sxs-lookup"><span data-stu-id="5186a-p103">A. Sign up for an EOP trial or purchase EOP via the web at the [Exchange Online Protection home page](https://products.office.com/exchange/exchange-email-security-spam-protection). Note that the functionality for a trial purchase is the same as for a paid subscription, but also includes the additional features provided with the [Exchange Enterprise CAL with Services](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) subscription plan.</span></span>

<span data-ttu-id="5186a-119">**問：EOP 如何定價？**</span><span class="sxs-lookup"><span data-stu-id="5186a-119">**Q. How is EOP priced?**</span></span>

<span data-ttu-id="5186a-p104">答：EOP 是依使用者授權。如需最新定價資訊，請參閱 [Exchange Online Protection 首頁](https://products.office.com/exchange/exchange-email-security-spam-protection)。</span><span class="sxs-lookup"><span data-stu-id="5186a-p104">A. EOP is licensed by user. For the latest pricing information, see the [Exchange Online Protection home page](https://products.office.com/exchange/exchange-email-security-spam-protection).</span></span>

<span data-ttu-id="5186a-123">**問：將 EOP 放入實際執行環境需時多久？**</span><span class="sxs-lookup"><span data-stu-id="5186a-123">**Q. How long does it take to put EOP into production?**</span></span>

<span data-ttu-id="5186a-p105">答：當您依照[設定 EOP 服務](set-up-your-eop-service.md)中所述步驟變更 MX 記錄，以及透過 EOP 變更郵件流程，就會立即開始進行篩選。MX 記錄可能需要 24-48 個小時，以透過 DNS 進行傳播。在處理過程中，您隨時可以在 Exchange 系統管理中心 (EAC) 中微調您的保護設定。</span><span class="sxs-lookup"><span data-stu-id="5186a-p105">A. When you change your MX record, as per the steps outlined in [Set up your EOP service](set-up-your-eop-service.md), and your mail flows through EOP, filtering begins immediately. The MX record may take as long as 24-48 hours to propagate via DNS. You can fine tune your protection settings in the Exchange admin center (EAC) at any time during this process.</span></span>

<span data-ttu-id="5186a-128">**問：我是否需要使用 Microsoft 365 的所有功能才能使用 EOP？如果我只想要 EOP 保護，該怎麼辦？**</span><span class="sxs-lookup"><span data-stu-id="5186a-128">**Q. Do I have to use all features of Microsoft 365 to use EOP? What if I just want EOP protection and that's all?**</span></span>

<span data-ttu-id="5186a-129">答：</span><span class="sxs-lookup"><span data-stu-id="5186a-129">A.</span></span> <span data-ttu-id="5186a-130">您可以使用 EOP 來保護您的內部部署信箱，而不需要使用 Microsoft 365 的任何其他功能。</span><span class="sxs-lookup"><span data-stu-id="5186a-130">You can use EOP to protect your on-premises mailboxes without using any other features of Microsoft 365.</span></span> <span data-ttu-id="5186a-131">這稱為獨立訂閱。</span><span class="sxs-lookup"><span data-stu-id="5186a-131">This is known as a standalone subscription.</span></span> <span data-ttu-id="5186a-132">您可以在[Exchange Online Protection 服務說明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)中找到 EOP 功能的清單。</span><span class="sxs-lookup"><span data-stu-id="5186a-132">A list of EOP features can be found in the [Exchange Online Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

<span data-ttu-id="5186a-133">**問：在註冊透過 EOP 的電子郵件篩選時，為什麼需要 Microsoft 365 租使用者？**</span><span class="sxs-lookup"><span data-stu-id="5186a-133">**Q. Why do I need a Microsoft 365 tenant when signing up for email filtering through EOP?**</span></span>

<span data-ttu-id="5186a-134">答：</span><span class="sxs-lookup"><span data-stu-id="5186a-134">A.</span></span> <span data-ttu-id="5186a-135">Microsoft 365 是指可透過 Microsoft 365 租使用者存取的產品和服務集合所提供的名稱。</span><span class="sxs-lookup"><span data-stu-id="5186a-135">Microsoft 365 is the name given to a collection of products and services that may be accessed through an Microsoft 365 tenant.</span></span> <span data-ttu-id="5186a-136">請將 Microsoft 365 租使用者想像為您可以為電子郵件篩選新增授權的起始點。</span><span class="sxs-lookup"><span data-stu-id="5186a-136">Think of the Microsoft 365 tenant as the starting point to which you may add licenses for email filtering.</span></span>

<span data-ttu-id="5186a-137">**問：EOP 是否有通訊入口網站可讓我了解已知問題和預期的解決方案？有哪些新功能？**</span><span class="sxs-lookup"><span data-stu-id="5186a-137">**Q. Does EOP have a communication portal where I can find out about known issues and expected resolutions? What about new features?**</span></span>

<span data-ttu-id="5186a-138">答：</span><span class="sxs-lookup"><span data-stu-id="5186a-138">A.</span></span> <span data-ttu-id="5186a-139">Microsoft 365 系統管理中心將會包含這項資訊。</span><span class="sxs-lookup"><span data-stu-id="5186a-139">The Microsoft 365 admin center will have some of this information.</span></span> <span data-ttu-id="5186a-140">如果您受到服務等級事件的影響，您應該會在登入 Microsoft 365 系統管理中心後，看到一則通訊警示（通常伴隨鈴聲圖示）。</span><span class="sxs-lookup"><span data-stu-id="5186a-140">If you are impacted by a Service Level Event then you should see a communication alert (typically accompanied by a bell icon) after signing in to the Microsoft 365 admin center.</span></span> <span data-ttu-id="5186a-141">建議您詳讀內容並採取適當的行動。</span><span class="sxs-lookup"><span data-stu-id="5186a-141">We recommend that you read and act on any items as appropriate.</span></span>

<span data-ttu-id="5186a-142">關於新的 EOP 功能， [Microsoft 365 for business 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)是用來找出即將推出之新功能之相關資訊的好資源。</span><span class="sxs-lookup"><span data-stu-id="5186a-142">Regarding new EOP features, the [Microsoft 365 for business roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) is a good resource for finding out information about upcoming new features.</span></span> <span data-ttu-id="5186a-143">我們也會將有關新功能的博客文章張貼至[Microsoft 365 博客](https://www.microsoft.com/microsoft-365/blog/)網站。</span><span class="sxs-lookup"><span data-stu-id="5186a-143">We'll also be posting blog articles about new features to the [Microsoft 365 Blogs](https://www.microsoft.com/microsoft-365/blog/) website.</span></span>

<span data-ttu-id="5186a-144">**問：此服務可與舊版 Exchange (例如 Exchange Server 2010) 和非 Exchange 環境搭配使用嗎？**</span><span class="sxs-lookup"><span data-stu-id="5186a-144">**Q. Does the service work with legacy Exchange versions (such as Exchange Server 2010) and non-Exchange environments?**</span></span>

<span data-ttu-id="5186a-p110">答：可以，此服務與伺服器無關，可與任何 SMTP 郵件傳輸代理程式共用。</span><span class="sxs-lookup"><span data-stu-id="5186a-p110">A. Yes, the service is server agnostic and can be used with any SMTP mail transfer agent.</span></span>

<span data-ttu-id="5186a-147">**問：哪種組織規模可以使用此項服務？**</span><span class="sxs-lookup"><span data-stu-id="5186a-147">**Q. What size organization can use the service?**</span></span>

<span data-ttu-id="5186a-p111">問：所有規模都可以。無論您組織的成長速度多快，EOP 網路都有足夠容量可容納成長。</span><span class="sxs-lookup"><span data-stu-id="5186a-p111">A. Any size. The EOP network has sufficient capacity to accommodate your growth, no matter how fast your organization grows.</span></span>

<span data-ttu-id="5186a-151">**我需要哪些權限才能設定 EOP？**</span><span class="sxs-lookup"><span data-stu-id="5186a-151">**What permissions do I need to set up EOP?**</span></span>

<span data-ttu-id="5186a-152">為了設定 EOP，您必須是全域管理員或 Exchange 公司管理員（組織管理角色群組）。</span><span class="sxs-lookup"><span data-stu-id="5186a-152">In order to configure EOP, you must be a global admin, or an Exchange Company Administrator (the Organization Management role group).</span></span>

<span data-ttu-id="5186a-153">**問：我如何確定我的資料和私人資訊是安全的？**</span><span class="sxs-lookup"><span data-stu-id="5186a-153">**Q. How do I know my data and private information are safe?**</span></span>

<span data-ttu-id="5186a-p112">答：若想深入了解我們為了確保您的資料和私人資訊之安全所採取的措施，包括服務等級協定 (SLA) 的相關資訊，請前往 [Office 365 信任中心](https://www.microsoft.com/trust-center)。</span><span class="sxs-lookup"><span data-stu-id="5186a-p112">A. To learn more about the steps we've taken to ensure the safety of your data and private information, including information about Service Level Agreements (SLAs), go to the [Office 365 Trust Center](https://www.microsoft.com/trust-center).</span></span>

<span data-ttu-id="5186a-156">**問：是否有我應該知道的任何限制，例如郵件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="5186a-156">**Q. Are there any limits I should be aware of, such as message size limitations?**</span></span>

<span data-ttu-id="5186a-p113">答：是。如需 EOP 限制的詳細資訊，請參閱＜[Exchange Online Protection 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)＞。</span><span class="sxs-lookup"><span data-stu-id="5186a-p113">A. Yes. For more information about limits in EOP, see [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).</span></span>

<span data-ttu-id="5186a-160">**問： EOP 是否支援 PowerShell？**</span><span class="sxs-lookup"><span data-stu-id="5186a-160">**Q. Does EOP support PowerShell?**</span></span>

<span data-ttu-id="5186a-161">答：</span><span class="sxs-lookup"><span data-stu-id="5186a-161">A.</span></span> <span data-ttu-id="5186a-162">是的，可透過 PowerShell 取得完整的 EOP 功能。</span><span class="sxs-lookup"><span data-stu-id="5186a-162">Yes, full EOP functionality is available via PowerShell.</span></span> <span data-ttu-id="5186a-163">如需詳細資訊，請參閱 [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5186a-163">For more information, see [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).</span></span>
