---
title: Office 365 中的 ATP 防網路釣魚功能
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解屬於 Office 365 高級威脅防護的反網路釣魚功能，以提供對商用 & spear 網路釣魚攻擊的保護。
ms.openlocfilehash: dda94145dfbef7466ebd8e1fb9f01d592515f598
ms.sourcegitcommit: 5e8901e7e571f20ede04f460bd3e7077dda004ca
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2020
ms.locfileid: "44875412"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a><span data-ttu-id="bf0c3-103">Office 365 中的 ATP 防網路釣魚功能</span><span class="sxs-lookup"><span data-stu-id="bf0c3-103">ATP anti-phishing capabilities in Office 365</span></span>

<span data-ttu-id="bf0c3-104">ATP 反網路釣魚是[Office 365 高級威脅防護](office-365-atp.md)的一部分。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-104">ATP anti-phishing is part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="bf0c3-105">ATP 反網路釣魚會將一組機器學習模型與冒充偵測演算法一起套用到內送郵件，以針對商品和魚叉式網路釣魚攻擊提供保護。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-105">ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection for commodity and spear phishing attacks.</span></span> <span data-ttu-id="bf0c3-106">所有郵件都受限於一組廣泛的機器學習模型，以偵測網路釣魚郵件，以及一組用來防禦各種使用者和網域模擬攻擊的高級演算法。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-106">All messages are subject to an extensive set of machine learning models trained to detect phishing messages, together with a set of advanced algorithms used to protect against various user and domain impersonation attacks.</span></span> <span data-ttu-id="bf0c3-107">ATP 反網路釣魚會根據您的 Office 365 全域或安全性管理員所設定的原則來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-107">ATP anti-phishing protects your organization according to polices that are set by your Office 365 global or security administrators.</span></span>
  
<span data-ttu-id="bf0c3-108">若要深入瞭解，請參閱[在 Office 365 中設定反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-108">To learn more, see [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf0c3-109">ATP 反網路釣魚只有在「高級威脅防護」（包括[microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 商務](https://www.microsoft.com/microsoft-365/business)版、Office 365 企業版 E5、Office 365 教育版 A5 等等）中才有提供。如果您的組織有 Office 365 訂閱，但未包含 Office 365 ATP，您可以將 ATP 購買為附加元件。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-109">ATP anti-phishing is only available in Advanced Threat Protection, which is included in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="bf0c3-110">如需詳細資訊，請參閱 [Office 365 進階威脅防護方案和定價](https://products.office.com/exchange/advance-threat-protection)和 [Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

## <a name="how-atp-anti-phishing-works"></a><span data-ttu-id="bf0c3-111">ATP 反網路釣魚的運作方式</span><span class="sxs-lookup"><span data-stu-id="bf0c3-111">How ATP anti-phishing works</span></span>

<span data-ttu-id="bf0c3-112">ATP 反網路釣魚檢查內送郵件的指示，郵件可能是網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-112">ATP anti-phishing checks incoming messages for indicators that the message may be phishing.</span></span> <span data-ttu-id="bf0c3-113">每當 ATP 原則涵蓋使用者（安全的附件、安全連結或反網路釣魚）時，就會透過分析郵件的多部機器教學模型評估內送郵件，以判斷原則是否套用至郵件，並根據設定的原則採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-113">Whenever a user is covered by an ATP policy (safe attachments, safe links or anti-phishing) the incoming message is evaluated by multiple machine learning models that analyze the message to determine if the policy applies to the message and the appropriate action is taken, based on the configured policy.</span></span>
  
<span data-ttu-id="bf0c3-114">ATP 反網路釣魚允許 Office 365 全域管理員或安全性系統管理員定義原則，以防範包含使用者或網域模擬的網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-114">ATP anti-phishing allows Office 365 global administrators or security admins to define policies that provide protection against phishing attacks that include impersonation of either users or domains.</span></span> <span data-ttu-id="bf0c3-115">（或兩者）。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-115">(or both).</span></span> <span data-ttu-id="bf0c3-116">Office 365 全域系統管理員或安全性系統管理員會在原則中定義使用者和網域應如何使用固定的使用者或網域清單，或透過信箱智慧加以保護，以防範模仿攻擊。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-116">Office 365 global administrators or security admins define within the policy which user and domains should be protected from impersonation attacks using either a fixed list of users or domains or by using mailbox intelligence.</span></span> <span data-ttu-id="bf0c3-117">信箱智慧指的是使用者的電子郵件習慣和個人連絡人的深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-117">Mailbox intelligence is an advanced understanding of a user's email habits and personal contacts.</span></span> <span data-ttu-id="bf0c3-118">ATP 瞭解每個個別使用者如何與組織內部和外部的使用者通訊，並建立這些關聯的對應。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-118">ATP learns how each individual user communicates with other users inside and outside the organization and builds up a map of these relationships.</span></span> <span data-ttu-id="bf0c3-119">此對應表允許 ATP 深入瞭解如何確認正確的郵件可識別為模擬的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-119">This map allows ATP to understand more details about how to ensure the right messages are identified as impersonation.</span></span>
  
<span data-ttu-id="bf0c3-120">ATP 反網路釣魚原則可以套用到組織中特定的一組人員或群組，或是整個網域或所有自訂網域。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-120">ATP anti-phishing polices can be applied to a specific set of people or groups in your organization, or to an entire domain or all of your custom domains.</span></span> <span data-ttu-id="bf0c3-121">若要深入瞭解，請參閱[在 Office 365 中設定反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-121">To learn more, see [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
## <a name="how-to-get-atp-anti-phishing"></a><span data-ttu-id="bf0c3-122">如何取得 ATP 反網路釣魚</span><span class="sxs-lookup"><span data-stu-id="bf0c3-122">How to get ATP anti-phishing</span></span>

<span data-ttu-id="bf0c3-123">ATP 反網路釣魚功能是[高級威脅防護](office-365-atp.md)的一部分;不過，當反網路釣魚原則定義時，ATP 反網路釣魚防護會套用。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-123">ATP Anti-Phishing features are part of [Advanced Threat Protection](office-365-atp.md); however, ATP anti-phishing protection applies when anti-phishing policies are defined.</span></span> <span data-ttu-id="bf0c3-124">（其中一個範例是類比型原則。）請參閱[在 Office 365 中設定反網路釣魚原則](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-124">(One example is an impersonation-based policy.) See [Set up anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a><span data-ttu-id="bf0c3-125">如何知道 ATP 反網路釣魚是否已到位</span><span class="sxs-lookup"><span data-stu-id="bf0c3-125">How to know if ATP anti-phishing is in place</span></span>

<span data-ttu-id="bf0c3-126">必須定義 ATP 反網路釣魚原則，保護功能才能生效。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-126">ATP anti-phishing policies must be defined in order for protection to be in effect.</span></span> <span data-ttu-id="bf0c3-127">請先檢查此項，以確認已就地保護。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-127">Check this first to verify protection is in place.</span></span>

<span data-ttu-id="bf0c3-128">此外，報告可用於示範服務對您組織的運作方式。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-128">In addition, reports are available to show how the service is working for your organization.</span></span> <span data-ttu-id="bf0c3-129">若要深入瞭解，請參閱[View reports For Office 365 Advanced 威脅 Protection](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-129">To learn more, see [View reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md).</span></span>

<span data-ttu-id="bf0c3-130">針對特定使用者，ATP 反網路釣魚機器教學模型為作用中，該使用者必須是定義的[ATP 安全附件](atp-safe-attachments.md)、 [ATP 安全連結](atp-safe-links.md)或 ATP 反網路釣魚原則的一部分。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-130">For ATP anti-phishing machine learning models to be active for a particular user, that user must be part of a defined [ATP Safe attachments](atp-safe-attachments.md), [ATP Safe Links](atp-safe-links.md), or ATP Anti-Phishing policy.</span></span> 

<span data-ttu-id="bf0c3-131">下表說明一些範例案例。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-131">The following table describes a few example scenarios.</span></span> <span data-ttu-id="bf0c3-132">在上述每個範例中，組織使用的是 Office 365 企業版 E5，其中包括「高級威脅防護」。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-132">In each of these examples, the organization is using Office 365 Enterprise E5, which includes Advanced Threat Protection.</span></span>
  
|<span data-ttu-id="bf0c3-133">**範例案例**</span><span class="sxs-lookup"><span data-stu-id="bf0c3-133">**Example scenario**</span></span>|<span data-ttu-id="bf0c3-134">**ATP 反網路釣魚是否適用于此案例？**</span><span class="sxs-lookup"><span data-stu-id="bf0c3-134">**Does ATP anti-phishing apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf0c3-135">Pat 的組織有 Office 365 企業版 E5，但沒有任何人已定義 ATP 安全附件、ATP 安全連結或 ATP 高級網路釣魚的任何原則。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-135">Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP safe attachments, ATP safe links or ATP advanced phishing yet.</span></span>|<span data-ttu-id="bf0c3-136">否。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-136">No.</span></span> <span data-ttu-id="bf0c3-137">雖然可以使用此功能，至少必須定義一個 ATP 原則，才能讓 ATP 機器學習模型能夠運作。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-137">Although the feature is available, at least one ATP policy must be defined in order for the ATP machine learning models to work.</span></span> <span data-ttu-id="bf0c3-138">若為模擬，ATP 反網路釣魚原則也必須已到位。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-138">For impersonation an ATP anti-phishing policy must also be in place.</span></span>|
|<span data-ttu-id="bf0c3-139">Lee 是 Contoso 銷售部門的員工。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-139">Lee is an employee in the sales department at Contoso.</span></span> <span data-ttu-id="bf0c3-140">「他的組織」有適當的 ATP 反網路釣魚原則，只適用于財務員工。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-140">Lee's organization has an ATP anti-phishing policy in place that applies to finance employees only.</span></span>|<span data-ttu-id="bf0c3-141">否。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-141">No.</span></span> <span data-ttu-id="bf0c3-142">在此情況下，ATP 反網路釣魚（機器模型和模擬保護）將會套用到財務員工，但其他員工（包括銷售部門）將不會。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-142">In this case, ATP anti-phishing (machine models and impersonation protection) would apply to finance employees, but other employees, including the sales department, would not.</span></span>|
|<span data-ttu-id="bf0c3-143">昨天，Jean-francois 組織的 Office 365 系統管理員會設定一種適用于所有員工的 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-143">Yesterday, an Office 365 administrator at Jean's organization set up an ATP anti-phishing policy that applies to all employees.</span></span> <span data-ttu-id="bf0c3-144">到目前為止，Jean-francois 收到一個包含原則所涵蓋之模仿的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-144">Earlier today, Jean received an email message that includes an impersonation covered by the policy.</span></span>|<span data-ttu-id="bf0c3-145">是。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-145">Yes.</span></span> <span data-ttu-id="bf0c3-146">在此範例中，Jean-francois 具有高級威脅防護的授權，並已定義包含 Jean-francois 的 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-146">In this example, Jean has a license for Advanced Threat Protection, and an ATP anti-phishing policy that includes Jean has been defined.</span></span> <span data-ttu-id="bf0c3-147">新原則通常需要 30 分鐘的時間才會在資料中心之間生效；在此案例中已經過了一天，所以原則應該會生效。</span><span class="sxs-lookup"><span data-stu-id="bf0c3-147">It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="bf0c3-148">相關主題</span><span class="sxs-lookup"><span data-stu-id="bf0c3-148">Related topics</span></span>

[<span data-ttu-id="bf0c3-149">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="bf0c3-149">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="bf0c3-150">Office 365 的防網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="bf0c3-150">Anti-phishing protection in Office 365</span></span>](anti-phishing-protection.md)
  
[<span data-ttu-id="bf0c3-151">在 Office 365 中設定反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="bf0c3-151">Set up anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
  
[<span data-ttu-id="bf0c3-152">Office 365 中的 ATP 安全連結</span><span class="sxs-lookup"><span data-stu-id="bf0c3-152">ATP safe links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="bf0c3-153">在 Office 365 中設定 ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="bf0c3-153">Set up ATP safe links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="bf0c3-154">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="bf0c3-154">ATP safe attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="bf0c3-155">在 Office 365 中設定 ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="bf0c3-155">Set up ATP safe attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="bf0c3-156">查看高級威脅防護的報告</span><span class="sxs-lookup"><span data-stu-id="bf0c3-156">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
