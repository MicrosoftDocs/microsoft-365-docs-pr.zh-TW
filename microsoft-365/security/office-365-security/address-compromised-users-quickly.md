---
title: 利用自動調查和回應來處理已遭破壞的使用者帳戶
keywords: AIR，autoIR，ATP，自動化，調查，回應，修正，威脅，高級，威脅，保護，已遭破壞
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: 瞭解如何使用 Office 365 Advanced 威脅防護方案2中的自動調查和回應功能，以加速偵測和解決已遭破壞之使用者帳戶的處理常式。
ms.openlocfilehash: fa648b33180cab7d70348dc4d1d6e64930ecff99
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201228"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="3447c-104">利用自動調查和回應來處理已遭破壞的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="3447c-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3447c-105">[Office 365 Advanced 威脅防護方案 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) 包含功能強大的 [自動化調查和回應](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) 功能。</span><span class="sxs-lookup"><span data-stu-id="3447c-105">[Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) includes powerful [automated investigation and response](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) capabilities.</span></span> <span data-ttu-id="3447c-106">這類功能可讓您的安全性運作小組儲存大量的時間和精力處理威脅。</span><span class="sxs-lookup"><span data-stu-id="3447c-106">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="3447c-107">Microsoft 繼續加強安全性功能。</span><span class="sxs-lookup"><span data-stu-id="3447c-107">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="3447c-108">最近，AIR 功能已增強，可在目前預覽) 中包含已遭破壞的使用者安全性行動手冊 (。</span><span class="sxs-lookup"><span data-stu-id="3447c-108">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="3447c-109">請閱讀本文以深入瞭解已遭破壞的使用者安全性行動手冊。</span><span class="sxs-lookup"><span data-stu-id="3447c-109">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="3447c-110">透過 Office 365 ATP，查看日誌貼 [上的時間，以偵測並回應使用者的洩密和限制損等範圍，](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) 以取得其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3447c-110">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Office 365 ATP](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![針對已遭破壞的使用者進行自動調查](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="3447c-112">「已遭破壞的使用者安全性行動手冊」可讓貴組織的安全性小組進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="3447c-112">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="3447c-113">加速偵測到的使用者帳戶的偵測;</span><span class="sxs-lookup"><span data-stu-id="3447c-113">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="3447c-114">在帳戶被攻破時限制遭到破壞的範圍;和</span><span class="sxs-lookup"><span data-stu-id="3447c-114">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="3447c-115">更有效率地回應遭到破壞的使用者。</span><span class="sxs-lookup"><span data-stu-id="3447c-115">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="3447c-116">遭到破壞的使用者警示</span><span class="sxs-lookup"><span data-stu-id="3447c-116">Compromised user alerts</span></span>

<span data-ttu-id="3447c-117">當使用者帳戶受損時，會發生反常或反常的行為。</span><span class="sxs-lookup"><span data-stu-id="3447c-117">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="3447c-118">例如，網路釣魚和垃圾郵件可能會從受信任的使用者帳戶內部傳送。</span><span class="sxs-lookup"><span data-stu-id="3447c-118">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="3447c-119">Office 365 Advanced 威脅防護可以偵測到 Office 365 內的電子郵件模式和共同作業活動中的這類異常。</span><span class="sxs-lookup"><span data-stu-id="3447c-119">Office 365 Advanced Threat Protection can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="3447c-120">發生這種情況時，就會觸發警示，威脅緩解程式會開始進行。</span><span class="sxs-lookup"><span data-stu-id="3447c-120">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="3447c-121">例如，以下是由於可疑電子郵件傳送而觸發的警示：</span><span class="sxs-lookup"><span data-stu-id="3447c-121">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![因可疑電子郵件傳送而觸發的警示](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="3447c-123">以下是當使用者達到傳送限制時所觸發的警示的範例：</span><span class="sxs-lookup"><span data-stu-id="3447c-123">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![因傳送限制已達到所觸發的警示](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="3447c-125">調查和回應已遭破壞的使用者</span><span class="sxs-lookup"><span data-stu-id="3447c-125">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="3447c-126">當使用者帳戶遭到攻破時，會觸發警示。</span><span class="sxs-lookup"><span data-stu-id="3447c-126">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="3447c-127">在某些情況下，此使用者帳戶會遭到封鎖，並避免傳送任何後續的電子郵件訊息，直到您組織的安全作業小組解決問題為止。</span><span class="sxs-lookup"><span data-stu-id="3447c-127">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="3447c-128">在其他情況下，自動調查會開始，這可能會導致您的安全小組應採取建議的動作。</span><span class="sxs-lookup"><span data-stu-id="3447c-128">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="3447c-129">查看和調查限制的使用者</span><span class="sxs-lookup"><span data-stu-id="3447c-129">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="3447c-130">查看有關自動化調查的詳細資料</span><span class="sxs-lookup"><span data-stu-id="3447c-130">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="3447c-131">您必須具有適當的許可權，才能執行下列工作。</span><span class="sxs-lookup"><span data-stu-id="3447c-131">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="3447c-132">請參閱 [使用 AIR 功能所需的許可權](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="3447c-132">See [Required permissions to use AIR capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="3447c-133">查看和調查限制的使用者</span><span class="sxs-lookup"><span data-stu-id="3447c-133">View and investigate restricted users</span></span>

<span data-ttu-id="3447c-134">您有幾個選項可供您流覽至限制的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="3447c-134">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="3447c-135">例如，在安全性 & 規範中心，您可以前往「**威脅管理**」  >  **查看**  >  **限制的使用者**。</span><span class="sxs-lookup"><span data-stu-id="3447c-135">For example, in the Security & Compliance Center, you can go to **Threat management** > **Review** > **Restricted Users**.</span></span> <span data-ttu-id="3447c-136">下列程式說明如何使用「 **警示** 」儀表板進行流覽，這是查看可能已觸發的各種警示的好方法。</span><span class="sxs-lookup"><span data-stu-id="3447c-136">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="3447c-137">移至 [https://protection.office.com](https://protection.office.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="3447c-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="3447c-138">在功能窗格中，選擇 [**警示**  >  **儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="3447c-138">In the navigation pane, choose **Alerts** > **Dashboard**.</span></span>

3. <span data-ttu-id="3447c-139">在 [ **其他警示** ] 小工具中，選擇 [ **受限制的使用者**]。</span><span class="sxs-lookup"><span data-stu-id="3447c-139">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![其他提醒小工具](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="3447c-141">這會開啟受限制的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="3447c-141">This opens the list of restricted users.</span></span><br/>![Office 365 中的受限使用者](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="3447c-143">選取清單中的使用者帳戶，以查看詳細資料並採取動作，例如 [發行受限制的使用者](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam)。</span><span class="sxs-lookup"><span data-stu-id="3447c-143">Select a user account in the list to view details and take action, such as [releasing the restricted user](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="3447c-144">查看有關自動化調查的詳細資料</span><span class="sxs-lookup"><span data-stu-id="3447c-144">View details about automated investigations</span></span>

<span data-ttu-id="3447c-145">當自動調查開始時，您可以在安全性 & 規範中心中查看其詳細資料和結果。</span><span class="sxs-lookup"><span data-stu-id="3447c-145">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="3447c-146">移至**威脅管理**  >  **調查**，然後選取調查以查看其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3447c-146">Go to **Threat management** > **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="3447c-147">若要深入瞭解，請參閱 [查看調查的詳細資料](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results)。</span><span class="sxs-lookup"><span data-stu-id="3447c-147">To learn more, see [View details of an investigation](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="3447c-148">請記住下列幾點</span><span class="sxs-lookup"><span data-stu-id="3447c-148">Keep the following points in mind</span></span>

- <span data-ttu-id="3447c-149">**停留在提醒**上。</span><span class="sxs-lookup"><span data-stu-id="3447c-149">**Stay on top of your alerts**.</span></span> <span data-ttu-id="3447c-150">如您所知，入侵的可能性越長，您的組織、客戶及協力廠商的潛在影響程度越大，成本也越大。</span><span class="sxs-lookup"><span data-stu-id="3447c-150">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="3447c-151">及早偵測和及時回應對於緩解威脅很重要，尤其是在使用者的帳戶遭到破壞時。</span><span class="sxs-lookup"><span data-stu-id="3447c-151">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="3447c-152">「**自動化」協助（但不取代）您的安全性運作小組**。</span><span class="sxs-lookup"><span data-stu-id="3447c-152">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="3447c-153">自動化調查和回應功能可在初期偵測到遭到損害的使用者，但是您的安全性作業小組可能需要接洽並進行一些調查和修復。</span><span class="sxs-lookup"><span data-stu-id="3447c-153">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="3447c-154">需要一些協助嗎？</span><span class="sxs-lookup"><span data-stu-id="3447c-154">Need some help with this?</span></span> <span data-ttu-id="3447c-155">請參閱 [複查和核准動作](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions)。</span><span class="sxs-lookup"><span data-stu-id="3447c-155">See [Review and approve actions](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).</span></span>

- <span data-ttu-id="3447c-156">請**不要依賴可疑的登入警示做為您唯一的指示器**。</span><span class="sxs-lookup"><span data-stu-id="3447c-156">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="3447c-157">當使用者帳戶遭到攻破時，可能會或不會觸發可疑的登入警示。</span><span class="sxs-lookup"><span data-stu-id="3447c-157">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="3447c-158">有時候，它是一系列的活動，會在帳戶遭到洩漏後觸發警示。</span><span class="sxs-lookup"><span data-stu-id="3447c-158">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="3447c-159">想要瞭解更多關於提醒的資訊嗎？</span><span class="sxs-lookup"><span data-stu-id="3447c-159">Want to know more about alerts?</span></span> <span data-ttu-id="3447c-160">請參閱 [警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)。</span><span class="sxs-lookup"><span data-stu-id="3447c-160">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3447c-161">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3447c-161">Next steps</span></span>

- [<span data-ttu-id="3447c-162">回顧使用 AIR 功能所需的許可權</span><span class="sxs-lookup"><span data-stu-id="3447c-162">Review the required permissions to use AIR capabilities</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="3447c-163">在 Office 365 中尋找並調查惡意電子郵件</span><span class="sxs-lookup"><span data-stu-id="3447c-163">Find and investigate malicious email in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- <span data-ttu-id="3447c-164">[了解 Microsoft Defender ATP 中的 AIR](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="3447c-164">[Learn about AIR in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)</span></span>

- [<span data-ttu-id="3447c-165">造訪 Microsoft 365 藍圖，查看即將推出的功能</span><span class="sxs-lookup"><span data-stu-id="3447c-165">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

