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
description: 在這裡，我們將回答有關於 Microsoft Exchange Online Protection (EOP) 雲端電子郵件篩選服務的最常見一般問題。如需其他常見問題集 (FAQ) 主題，請前往下列連結：
ms.openlocfilehash: 842f022edbba9d1a790a26987982c3bd508e9d5e
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893679"
---
# <a name="eop-general-faq"></a><span data-ttu-id="42747-104">EOP 一般常見問題集</span><span class="sxs-lookup"><span data-stu-id="42747-104">EOP general FAQ</span></span>

<span data-ttu-id="42747-p102">在這裡，我們將回答有關於 Microsoft Exchange Online Protection (EOP) 雲端電子郵件篩選服務的最常見一般問題。如需其他常見問題集 (FAQ) 主題，請前往下列連結：</span><span class="sxs-lookup"><span data-stu-id="42747-p102">Here we answer the most common general questions about the Microsoft Exchange Online Protection (EOP) cloud-hosted email filtering service. For additional frequently asked questions (FAQ) topics, go to the following links:</span></span>

- [<span data-ttu-id="42747-107">EOP 排入佇列、延後和退回的訊息常見問題集</span><span class="sxs-lookup"><span data-stu-id="42747-107">EOP queued, deferred, and bounced messages FAQ</span></span>](eop-queued-deferred-and-bounced-messages-faq.md)

- [<span data-ttu-id="42747-108">委派管理常見問題集</span><span class="sxs-lookup"><span data-stu-id="42747-108">Delegated administration FAQ</span></span>](delegated-administration-faq.md)

- [<span data-ttu-id="42747-109">反垃圾郵件保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="42747-109">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

- [<span data-ttu-id="42747-110">隔離常見問題集</span><span class="sxs-lookup"><span data-stu-id="42747-110">Quarantine FAQ</span></span>](quarantine-faq.md)

- [<span data-ttu-id="42747-111">反惡意程式碼保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="42747-111">Anti-malware protection FAQ</span></span>](anti-malware-protection-faq-eop.md)

- [<span data-ttu-id="42747-112">郵件追蹤常見問題集</span><span class="sxs-lookup"><span data-stu-id="42747-112">Message Trace FAQ</span></span>](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

<span data-ttu-id="42747-113">**問：EOP 是什麼？**</span><span class="sxs-lookup"><span data-stu-id="42747-113">**Q. What is EOP?**</span></span>

<span data-ttu-id="42747-p103">答：EOP 是雲端電子郵件篩選服務，專門用來保護客戶遠離垃圾郵件與惡意程式碼，以及執行自訂原則規則。</span><span class="sxs-lookup"><span data-stu-id="42747-p103">A. EOP is a cloud-hosted email filtering service built to protect customers from spam and malware, and to implement custom policy rules.</span></span>

<span data-ttu-id="42747-116">**問：如何註冊 EOP 試用版或購買 EOP？**</span><span class="sxs-lookup"><span data-stu-id="42747-116">**Q. How do I sign up for an EOP trial or purchase EOP?**</span></span>

<span data-ttu-id="42747-p104">答：可透過以下網址註冊 EOP 試用版或購買 EOP：[Exchange Online Protection 首頁](https://products.office.com/exchange/exchange-email-security-spam-protection)。請注意，試用購買的功能與付費訂閱版相同，但另外包含 [Exchange Enterprise CAL with Services](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) 訂閱方案提供的其他功能。</span><span class="sxs-lookup"><span data-stu-id="42747-p104">A. Sign up for an EOP trial or purchase EOP via the web at the [Exchange Online Protection home page](https://products.office.com/exchange/exchange-email-security-spam-protection). Note that the functionality for a trial purchase is the same as for a paid subscription, but also includes the additional features provided with the [Exchange Enterprise CAL with Services](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) subscription plan.</span></span>

<span data-ttu-id="42747-120">**問：EOP 如何定價？**</span><span class="sxs-lookup"><span data-stu-id="42747-120">**Q. How is EOP priced?**</span></span>

<span data-ttu-id="42747-p105">答：EOP 是依使用者授權。如需最新定價資訊，請參閱 [Exchange Online Protection 首頁](https://products.office.com/exchange/exchange-email-security-spam-protection)。</span><span class="sxs-lookup"><span data-stu-id="42747-p105">A. EOP is licensed by user. For the latest pricing information, see the [Exchange Online Protection home page](https://products.office.com/exchange/exchange-email-security-spam-protection).</span></span>

<span data-ttu-id="42747-124">**問：將 EOP 放入實際執行環境需時多久？**</span><span class="sxs-lookup"><span data-stu-id="42747-124">**Q. How long does it take to put EOP into production?**</span></span>

<span data-ttu-id="42747-p106">答：當您依照[設定 EOP 服務](set-up-your-eop-service.md)中所述步驟變更 MX 記錄，以及透過 EOP 變更郵件流程，就會立即開始進行篩選。MX 記錄可能需要 24-48 個小時，以透過 DNS 進行傳播。在處理過程中，您隨時可以在 Exchange 系統管理中心 (EAC) 中微調您的保護設定。</span><span class="sxs-lookup"><span data-stu-id="42747-p106">A. When you change your MX record, as per the steps outlined in [Set up your EOP service](set-up-your-eop-service.md), and your mail flows through EOP, filtering begins immediately. The MX record may take as long as 24-48 hours to propagate via DNS. You can fine tune your protection settings in the Exchange admin center (EAC) at any time during this process.</span></span>

<span data-ttu-id="42747-129">**問：我必須使用 Microsoft Office 365 的所有功能才能使用 EOP 嗎？如果我只想要 EOP 保護呢？**</span><span class="sxs-lookup"><span data-stu-id="42747-129">**Q. Do I have to use all features of Microsoft Office 365 to use EOP? What if I just want EOP protection and that's all?**</span></span>

<span data-ttu-id="42747-p107">答：您可以使用 EOP 保護您的內部部署信箱，而不需使用 Office 365 的任何其他功能。這也稱為獨立訂閱。[Exchange Online Protection 服務描述](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)會提供 EOP 功能的清單。</span><span class="sxs-lookup"><span data-stu-id="42747-p107">A. You can use EOP to protect your on-premises mailboxes without using any other features of Office 365. This is known as a standalone subscription. A list of EOP features can be found in the [Exchange Online Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

<span data-ttu-id="42747-134">**問：透過 EOP 註冊電子郵件篩選時，為什麼需要 Office 365 租用戶？**</span><span class="sxs-lookup"><span data-stu-id="42747-134">**Q. Why do I need an Office 365 tenant when signing up for email filtering through EOP?**</span></span>

<span data-ttu-id="42747-p108">答：Office 365 是提供給一組可透過 Office 365 租用戶存取的產品和服務名稱。請將 Office 365 租用戶想像成新增授權以篩選電子郵件的起點。</span><span class="sxs-lookup"><span data-stu-id="42747-p108">A. Office 365 is the name given to a collection of products and services that may be accessed through an Office 365 tenant. Think of the Office 365 tenant as the starting point to which you may add licenses for email filtering.</span></span>

<span data-ttu-id="42747-138">**問：EOP 是否有通訊入口網站可讓我了解已知問題和預期的解決方案？有哪些新功能？**</span><span class="sxs-lookup"><span data-stu-id="42747-138">**Q. Does EOP have a communication portal where I can find out about known issues and expected resolutions? What about new features?**</span></span>

<span data-ttu-id="42747-139">答：</span><span class="sxs-lookup"><span data-stu-id="42747-139">A.</span></span> <span data-ttu-id="42747-140">Microsoft 365 系統管理中心將會包含這項資訊。</span><span class="sxs-lookup"><span data-stu-id="42747-140">The Microsoft 365 admin center will have some of this information.</span></span> <span data-ttu-id="42747-141">如果您受到服務等級事件的影響，您應該會在登入 Microsoft 365 系統管理中心後，看到一則通訊警示（通常伴隨鈴聲圖示）。</span><span class="sxs-lookup"><span data-stu-id="42747-141">If you are impacted by a Service Level Event then you should see a communication alert (typically accompanied by a bell icon) after signing in to the Microsoft 365 admin center.</span></span> <span data-ttu-id="42747-142">建議您詳讀內容並採取適當的行動。</span><span class="sxs-lookup"><span data-stu-id="42747-142">We recommend that you read and act on any items as appropriate.</span></span>

<span data-ttu-id="42747-143">關於新的 EOP 功能，[商務用 Office 365 導覽圖](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)是很好的資源，可以在其中尋找新功能的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="42747-143">Regarding new EOP features, the [Office 365 for business roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) is a good resource for finding out information about upcoming new features.</span></span> <span data-ttu-id="42747-144">我們也會將有關新功能的博客文章張貼至[Microsoft 365 博客](https://www.microsoft.com/microsoft-365/blog/)網站。</span><span class="sxs-lookup"><span data-stu-id="42747-144">We'll also be posting blog articles about new features to the [Microsoft 365 Blogs](https://www.microsoft.com/microsoft-365/blog/) website.</span></span>

<span data-ttu-id="42747-145">**問：此服務可與舊版 Exchange (例如 Exchange Server 2010) 和非 Exchange 環境搭配使用嗎？**</span><span class="sxs-lookup"><span data-stu-id="42747-145">**Q. Does the service work with legacy Exchange versions (such as Exchange Server 2010) and non-Exchange environments?**</span></span>

<span data-ttu-id="42747-p111">答：可以，此服務與伺服器無關，可與任何 SMTP 郵件傳輸代理程式共用。</span><span class="sxs-lookup"><span data-stu-id="42747-p111">A. Yes, the service is server agnostic and can be used with any SMTP mail transfer agent.</span></span>

<span data-ttu-id="42747-148">**問：哪種組織規模可以使用此項服務？**</span><span class="sxs-lookup"><span data-stu-id="42747-148">**Q. What size organization can use the service?**</span></span>

<span data-ttu-id="42747-p112">問：所有規模都可以。無論您組織的成長速度多快，EOP 網路都有足夠容量可容納成長。</span><span class="sxs-lookup"><span data-stu-id="42747-p112">A. Any size. The EOP network has sufficient capacity to accommodate your growth, no matter how fast your organization grows.</span></span>

<span data-ttu-id="42747-152">**我需要哪些權限才能設定 EOP？**</span><span class="sxs-lookup"><span data-stu-id="42747-152">**What permissions do I need to set up EOP?**</span></span>

<span data-ttu-id="42747-153">若要設定 EOP，您必須是 Office 365 全域管理員或 Exchange 公司管理員 (組織管理角色群組)。</span><span class="sxs-lookup"><span data-stu-id="42747-153">In order to configure EOP, you must be an Office 365 Global Admin, or an Exchange Company Administrator (the Organization Management role group).</span></span>

<span data-ttu-id="42747-154">**問：我如何確定我的資料和私人資訊是安全的？**</span><span class="sxs-lookup"><span data-stu-id="42747-154">**Q. How do I know my data and private information are safe?**</span></span>

<span data-ttu-id="42747-p113">答：若想深入了解我們為了確保您的資料和私人資訊之安全所採取的措施，包括服務等級協定 (SLA) 的相關資訊，請前往 [Office 365 信任中心](https://www.microsoft.com/trust-center)。</span><span class="sxs-lookup"><span data-stu-id="42747-p113">A. To learn more about the steps we've taken to ensure the safety of your data and private information, including information about Service Level Agreements (SLAs), go to the [Office 365 Trust Center](https://www.microsoft.com/trust-center).</span></span>

<span data-ttu-id="42747-157">**問：是否有我應該知道的任何限制，例如郵件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="42747-157">**Q. Are there any limits I should be aware of, such as message size limitations?**</span></span>

<span data-ttu-id="42747-p114">答：是。如需 EOP 限制的詳細資訊，請參閱＜[Exchange Online Protection 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)＞。</span><span class="sxs-lookup"><span data-stu-id="42747-p114">A. Yes. For more information about limits in EOP, see [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).</span></span>

<span data-ttu-id="42747-161">**問： EOP 是否支援 PowerShell？**</span><span class="sxs-lookup"><span data-stu-id="42747-161">**Q. Does EOP support PowerShell?**</span></span>

<span data-ttu-id="42747-162">答：</span><span class="sxs-lookup"><span data-stu-id="42747-162">A.</span></span> <span data-ttu-id="42747-163">是的，可透過 PowerShell 取得完整的 EOP 功能。</span><span class="sxs-lookup"><span data-stu-id="42747-163">Yes, full EOP functionality is available via PowerShell.</span></span> <span data-ttu-id="42747-164">如需詳細資訊，請參閱 [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="42747-164">For more information, see [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).</span></span>
