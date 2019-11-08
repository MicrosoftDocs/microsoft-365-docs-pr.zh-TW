---
title: 修正電子郵件傳送問題的錯誤的程式碼 5.7.7xx in Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/11/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 了解如何在 Exchange Online （封鎖而無法傳送郵件的承租人） 中修正錯誤的程式碼 5.7.7xx 的電子郵件問題。
ms.openlocfilehash: 28ed444d821cbe00cfcb92872de15bb43a65ae28
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033874"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a><span data-ttu-id="bea6e-103">修正電子郵件傳送問題的錯誤的程式碼 5.7.7xx in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bea6e-103">Fix email delivery issues for error code 5.7.7xx in Exchange Online</span></span>

<span data-ttu-id="bea6e-104">這個主題會說明若您在未傳遞回報 （也稱為 NDR、 退回的郵件、 傳遞狀態通知或 DSN） 的狀態碼 550 5.7.7xx 您可以執行的動作。</span><span class="sxs-lookup"><span data-stu-id="bea6e-104">This topic describes what you can do if you see status code 550 5.7.7xx in a non-delivery report (also known as an NDR, bounce message, delivery status notification, or DSN).</span></span> <span data-ttu-id="bea6e-105">當您的租用戶限制在一或多種方式傳送電子郵件時，您會看到此自動化的通知。</span><span class="sxs-lookup"><span data-stu-id="bea6e-105">You'll see this automated notification when your tenant is restricted from sending email in one way or another.</span></span> <span data-ttu-id="bea6e-106">這些錯誤碼通常會為 705 或 750 變成。</span><span class="sxs-lookup"><span data-stu-id="bea6e-106">These error codes will usually come in as 705 or 750.</span></span>

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a><span data-ttu-id="bea6e-107">5.7.705： 租用戶已超出臨界值限制： 您需要知道</span><span class="sxs-lookup"><span data-stu-id="bea6e-107">5.7.705: Tenant has exceeded threshold restriction: What you need to know</span></span>

<span data-ttu-id="bea6e-108">內部寄件者無法看到此 NDR，每當您嘗試傳送郵件，如果您的租用戶遭到盜用了。</span><span class="sxs-lookup"><span data-stu-id="bea6e-108">Internal senders could see this NDR whenever you try to send mail if your tenant was compromised.</span></span> <span data-ttu-id="bea6e-109">這通常 occus 時從您的租用戶的流量大部分為可疑已偵測到和已經產生的郵件傳送的租用戶的能力。</span><span class="sxs-lookup"><span data-stu-id="bea6e-109">This usually occus when the majority of traffic from your tenant has been detected as suspicious and has resulted in a ban on sending ability for the tenant.</span></span> <span data-ttu-id="bea6e-110">這也可能是如果您的使用者從 Office 365 傳送大量的大宗郵件。</span><span class="sxs-lookup"><span data-stu-id="bea6e-110">This can also occur if your users send an large amount of bulk mail from Office 365.</span></span> <span data-ttu-id="bea6e-111">服務描述中所述，Exchange Online 客戶若需要傳送合法的大量商業電子郵件 （例如客戶電子報） 應使用專門提供這些服務的協力廠商提供者。</span><span class="sxs-lookup"><span data-stu-id="bea6e-111">As stated in the service description, Exchange Online customers who need to send legitimate bulk commercial email (for example, customer newsletters) should use third-party providers that specialize in these services.</span></span>

<span data-ttu-id="bea6e-112">一旦您的使用者共同租用戶，傳送透過服務的可疑郵件數量，所有使用者就都無法傳送的任何郵件，直到問題解決為止。</span><span class="sxs-lookup"><span data-stu-id="bea6e-112">Once your users collectively, as a tenant, send a certain amount of suspicious mail through the service, all users can be prevented from sending any mail until the problem is fixed.</span></span> <span data-ttu-id="bea6e-113">使用者會收到未傳遞回報 (NDR) 表示：</span><span class="sxs-lookup"><span data-stu-id="bea6e-113">Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="bea6e-114">550 5.7.705 存取被拒，租用戶已超出臨界值</span><span class="sxs-lookup"><span data-stu-id="bea6e-114">550 5.7.705 Access denied, tenant has exceeded threshold</span></span>

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a><span data-ttu-id="bea6e-115">5.7.750： 未註冊的網域的電子郵件限制： 您需要知道</span><span class="sxs-lookup"><span data-stu-id="bea6e-115">5.7.750: Unregistered Domain Email restriction: What you need to know</span></span>

<span data-ttu-id="bea6e-116">Office 365 允許轉送某些郵件透過 Exchange Online Protection (EOP) 的租用戶。</span><span class="sxs-lookup"><span data-stu-id="bea6e-116">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP).</span></span> <span data-ttu-id="bea6e-117">當使用者擁有 Office 365 信箱和外部的人員傳送他們電子郵件，但使其回到使用者的外部信箱設定電子郵件轉寄功能，就是一個支援的範例。</span><span class="sxs-lookup"><span data-stu-id="bea6e-117">One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox.</span></span> <span data-ttu-id="bea6e-118">這是最常見的學生，想要利用其個人電子郵件介面，但仍取得電子郵件與學校相關的教育版環境中。</span><span class="sxs-lookup"><span data-stu-id="bea6e-118">This is most common in education environments where students want to leverage their personal email interface but still get emails related to school.</span></span> <span data-ttu-id="bea6e-119">另一個例子是客戶在混合式案例，並有傳送超出 EOP 的電子郵件的內部部署伺服器時。</span><span class="sxs-lookup"><span data-stu-id="bea6e-119">Another example is when customers are in a hybrid scenario and have on-premises servers that send email out of EOP.</span></span>

### <a name="problems-with-unregistered-domains"></a><span data-ttu-id="bea6e-120">問題未註冊的網域</span><span class="sxs-lookup"><span data-stu-id="bea6e-120">Problems with unregistered domains</span></span>

<span data-ttu-id="bea6e-121">問題時，內部部署伺服器取得危害和最終轉送大量超出 EOP 垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="bea6e-121">The problem is when on-premises servers get compromised and end up relaying a large volume of spam out of EOP.</span></span> <span data-ttu-id="bea6e-122">在大多數情況下，右連接器已設定，但未註冊，也就是取消提供這項，網域從要傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="bea6e-122">In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains.</span></span> <span data-ttu-id="bea6e-123">Office 365，並讓合理的郵件來自未註冊的網域，但應在您計劃傳送出的每個網域的系統管理中心中設定公認的網域。</span><span class="sxs-lookup"><span data-stu-id="bea6e-123">Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="bea6e-124">一旦危害，租用戶就禁止傳送未註冊的網域的輸出郵件。</span><span class="sxs-lookup"><span data-stu-id="bea6e-124">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains.</span></span> <span data-ttu-id="bea6e-125">使用者會收到未傳遞回報 (NDR) 表示：</span><span class="sxs-lookup"><span data-stu-id="bea6e-125">Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="bea6e-126">550 5.7.750 服務無法使用。</span><span class="sxs-lookup"><span data-stu-id="bea6e-126">550 5.7.750 Service unavailable.</span></span> <span data-ttu-id="bea6e-127">封鎖來自未註冊的網域傳送的用戶端</span><span class="sxs-lookup"><span data-stu-id="bea6e-127">Client blocked from sending from unregistered domains</span></span>

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="bea6e-128">如何才能重新傳送解除封鎖租用戶</span><span class="sxs-lookup"><span data-stu-id="bea6e-128">How to unblocking tenant in order to send again</span></span>

<span data-ttu-id="bea6e-129">有幾個事項如果您的租用戶取得阻止傳送電子郵件：</span><span class="sxs-lookup"><span data-stu-id="bea6e-129">There are several things you need to do if your tenant get blocked for sending email:</span></span>

1. <span data-ttu-id="bea6e-130">請確定您網域的所有註冊 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="bea6e-130">Make sure that you register all of your domains in Microsoft 365 admin center.</span></span> <span data-ttu-id="bea6e-131">詳細資訊，請參閱[以下](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="bea6e-131">More information can be found [here](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="bea6e-132">尋找不尋常的連接器。</span><span class="sxs-lookup"><span data-stu-id="bea6e-132">Look for unusual connectors.</span></span> <span data-ttu-id="bea6e-133">惡意動作項目通常會傳送垃圾郵件您 Office 365 租用戶中建立新的輸入的連接器。</span><span class="sxs-lookup"><span data-stu-id="bea6e-133">Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam.</span></span> <span data-ttu-id="bea6e-134">檢查您的連接器的詳細資訊可以找到[以下](https://docs.microsoft.com/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="bea6e-134">More information on checking your connectors can be found [here](https://docs.microsoft.com/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="bea6e-135">鎖定您的內部部署伺服器，並確定他們沒有遭到盜用。</span><span class="sxs-lookup"><span data-stu-id="bea6e-135">Lock down your on-premises servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="bea6e-136">有許多因素所涉及在這裡，尤其是協力廠商的伺服器。</span><span class="sxs-lookup"><span data-stu-id="bea6e-136">There are many factors involved here, especially if these are third-party servers.</span></span> <span data-ttu-id="bea6e-137">無論如何，您將需要能夠確認是合法的所有郵件離開您的伺服器。</span><span class="sxs-lookup"><span data-stu-id="bea6e-137">Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="bea6e-138">完成時，您必須連絡 Microsoft 支援服務，並要求以取得您的租用戶解除封鎖再次傳送來自未註冊的網域。</span><span class="sxs-lookup"><span data-stu-id="bea6e-138">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.</span></span>  <span data-ttu-id="bea6e-139">提供錯誤碼很有幫助，但您想要證明您的環境受到保護，且不會在一次傳送垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="bea6e-139">Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again.</span></span> <span data-ttu-id="bea6e-140">在開啟支援案例的詳細資訊可以找到[以下](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)。</span><span class="sxs-lookup"><span data-stu-id="bea6e-140">More information on opening a support case can be found [here](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="bea6e-141">相關資訊</span><span class="sxs-lookup"><span data-stu-id="bea6e-141">For more information</span></span>

[<span data-ttu-id="bea6e-142">Office 365 電子郵件的反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="bea6e-142">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="bea6e-143">Office 365 中的電子郵件未傳遞回報</span><span class="sxs-lookup"><span data-stu-id="bea6e-143">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="bea6e-144">設定信箱的電子郵件轉寄功能</span><span class="sxs-lookup"><span data-stu-id="bea6e-144">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="bea6e-145">如何將多功能裝置或應用程式設定為使用 Office 365 傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="bea6e-145">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="bea6e-146">[管理公認的網域在 Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="bea6e-146">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
