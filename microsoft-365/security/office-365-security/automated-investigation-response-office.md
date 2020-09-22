---
title: 自動調查和回應 (AIR) 概述
f1.keywords:
- NOCSH
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
ms.date: 08/21/2020
description: 深入瞭解 Office 365 高級威脅防護方案2中的自動化調查和回應功能。
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: d6793793a663e562b05df7e8458a6a8933e5ee47
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200342"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-365"></a><span data-ttu-id="e6672-103">Microsoft 365 中 (AIR) 的自動化調查和回應概覽</span><span class="sxs-lookup"><span data-stu-id="e6672-103">An overview of Automated investigation and response (AIR) in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e6672-104">在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="e6672-104">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="e6672-105">在某些情況下，安全性作業小組可能感覺到所觸發的警示數量所淹沒。</span><span class="sxs-lookup"><span data-stu-id="e6672-105">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="e6672-106">自動調查和回應 (Office 365 的 AIR) 功能 (Office 365 ATP) 可助您。</span><span class="sxs-lookup"><span data-stu-id="e6672-106">Automated investigation and response (AIR) capabilities in Office 365 Advanced Threat Protection (Office 365 ATP) can help.</span></span> 

<span data-ttu-id="e6672-107">AIR 可讓您的安全性運作小組更有效率地運作。</span><span class="sxs-lookup"><span data-stu-id="e6672-107">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="e6672-108">AIR 功能包括自動調查處理程式，以回應目前存在的已知威脅。</span><span class="sxs-lookup"><span data-stu-id="e6672-108">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="e6672-109">適當的修正動作等待核准，讓您的安全性作業小組能夠回應偵測到的威脅。</span><span class="sxs-lookup"><span data-stu-id="e6672-109">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span> 

<span data-ttu-id="e6672-110">本文提供空中的概覽。</span><span class="sxs-lookup"><span data-stu-id="e6672-110">This article provides an overview of AIR.</span></span> <span data-ttu-id="e6672-111">當您準備好開始使用 AIR 時，請參閱 [自動調查和回應威脅](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="e6672-111">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

## <a name="at-a-high-level"></a><span data-ttu-id="e6672-112">在高層級</span><span class="sxs-lookup"><span data-stu-id="e6672-112">At a high level</span></span>

<span data-ttu-id="e6672-113">當觸發警示時，安全性行動行動會生效。</span><span class="sxs-lookup"><span data-stu-id="e6672-113">As alerts are triggered, security playbooks go into effect.</span></span> <span data-ttu-id="e6672-114">根據情況而定，可以開始進行 [自動化調查過程](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) 。</span><span class="sxs-lookup"><span data-stu-id="e6672-114">Depending on the situation, an [automated investigation process](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) can begin.</span></span> <span data-ttu-id="e6672-115">在自動調查期間和之後，建議進行 [修正動作](air-remediation-actions.md) 。</span><span class="sxs-lookup"><span data-stu-id="e6672-115">During and after an automated investigation, [remediation actions](air-remediation-actions.md) are recommended.</span></span> <span data-ttu-id="e6672-116">Office 365 的 [高級威脅防護] 中不會自動採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="e6672-116">No actions are taken automatically in Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="e6672-117">您的安全性運作小組會評論，然後 [核准或拒絕每項修復動作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="e6672-117">Your security operations team reviews, and then [approves or rejects each remediation action](air-review-approve-pending-completed-actions.md).</span></span> <span data-ttu-id="e6672-118">在調查中的所有動作經核准或拒絕時，調查都會完成。</span><span class="sxs-lookup"><span data-stu-id="e6672-118">When all of the actions following an investigation are approved or rejected, the investigation completes.</span></span> <span data-ttu-id="e6672-119">所有這些活動都會在安全性 & 規範中心中追蹤和查看 (請參閱 [查看調查) 的詳細資料](air-view-investigation-results.md#view-details-of-an-investigation) 。</span><span class="sxs-lookup"><span data-stu-id="e6672-119">All of these activities are tracked and viewable in the Security & Compliance Center (see [View details of an investigation](air-view-investigation-results.md#view-details-of-an-investigation)).</span></span>

<span data-ttu-id="e6672-120">下列各節提供有關警示、安全性行動手冊及動作中的空氣範例的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e6672-120">The following sections provide more details about alerts, security playbooks, and examples of AIR in action.</span></span>

## <a name="alerts"></a><span data-ttu-id="e6672-121">警示</span><span class="sxs-lookup"><span data-stu-id="e6672-121">Alerts</span></span>

<span data-ttu-id="e6672-122">[警示](../../compliance/alert-policies.md#viewing-alerts) 代表事件回應的安全性作業小組工作流程的觸發器。</span><span class="sxs-lookup"><span data-stu-id="e6672-122">[Alerts](../../compliance/alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="e6672-123">決定要調查的適當一組提醒，同時確保沒有威脅 unaddressed 面臨挑戰。</span><span class="sxs-lookup"><span data-stu-id="e6672-123">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="e6672-124">當手動調查何時會以手動方式執行提醒時，安全性作業小組必須搜尋和關聯實體 (例如內容、裝置和使用者) 威脅以外的風險。</span><span class="sxs-lookup"><span data-stu-id="e6672-124">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (such as content, devices and users) at risk from threats.</span></span> <span data-ttu-id="e6672-125">這類工作和工作流程可能非常耗時且包含多個工具和系統。</span><span class="sxs-lookup"><span data-stu-id="e6672-125">Such tasks and workflows can be very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="e6672-126">透過利用關鍵安全性和威脅管理提醒自動觸發安全性回應行動手冊，透過 AIR、安全事件的調查和回應可自動進行。</span><span class="sxs-lookup"><span data-stu-id="e6672-126">With AIR, investigation and response for security events are automated by having key security and threat management alerts trigger security response playbooks automatically.</span></span> 

<span data-ttu-id="e6672-127">目前對於 AIR，會自動調查從下列類型的報警原則產生的警示：</span><span class="sxs-lookup"><span data-stu-id="e6672-127">Currently for AIR, alerts generated from the following kinds of alert policies are auto-investigated:</span></span>  

- <span data-ttu-id="e6672-128">偵測到可能的惡意 URL 按一下</span><span class="sxs-lookup"><span data-stu-id="e6672-128">A potentially malicious URL click was detected</span></span>
- <span data-ttu-id="e6672-129">使用者以網路釣魚方式舉報的電子郵件`*`</span><span class="sxs-lookup"><span data-stu-id="e6672-129">Email reported by user as phish`*`</span></span>
- <span data-ttu-id="e6672-130">傳遞後移除包含惡意程式碼的電子郵件`*`</span><span class="sxs-lookup"><span data-stu-id="e6672-130">Email messages containing malware removed after delivery`*`</span></span>
- <span data-ttu-id="e6672-131">傳遞後移除包含網路釣魚 URLs 的電子郵件`*`</span><span class="sxs-lookup"><span data-stu-id="e6672-131">Email messages containing phish URLs removed after delivery`*`</span></span>
- <span data-ttu-id="e6672-132">偵測到電子郵件傳送模式`#`</span><span class="sxs-lookup"><span data-stu-id="e6672-132">Suspicious email sending patterns detected`#`</span></span>
- <span data-ttu-id="e6672-133">使用者限制傳送電子郵件`#`</span><span class="sxs-lookup"><span data-stu-id="e6672-133">User restricted from sending email`#`</span></span>

> [!NOTE]
> <span data-ttu-id="e6672-134">以星號 () 標示的警示 `*` 會在安全性 & 規範中心內的各項警示原則中指派 *資訊* 嚴重性，並關閉電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="e6672-134">The alerts marked with an asterisk (`*`) are assigned an *Informational* severity in the respective alert policies within the Security & Compliance Center, with email notifications turned off.</span></span> <span data-ttu-id="e6672-135">您可以透過 [報警原則](../../compliance/alert-policies.md#alert-policy-settings)設定開啟電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="e6672-135">Email notifications can be turned on through [Alert policy configuration](../../compliance/alert-policies.md#alert-policy-settings).</span></span> <span data-ttu-id="e6672-136">使用雜湊 () 標示的警示， `#` 通常是與公共預覽行動手冊相關聯的警示。</span><span class="sxs-lookup"><span data-stu-id="e6672-136">Alerts marked with a hash (`#`) are generally available alerts associated with public preview playbooks.</span></span>

<span data-ttu-id="e6672-137">若要在安全性 & 規範中心中查看提醒，請選擇 [**提醒**] [  >  **查看提醒**]。</span><span class="sxs-lookup"><span data-stu-id="e6672-137">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="e6672-138">選取警示以查看其詳細資料，然後從那裡使用「 **查看調查** 」連結，以移至對應的 [調查](air-view-investigation-results.md#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="e6672-138">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](air-view-investigation-results.md#investigation-graph).</span></span>  

> [!NOTE]
> <span data-ttu-id="e6672-139">預設會在提醒視圖中隱藏資訊警示。</span><span class="sxs-lookup"><span data-stu-id="e6672-139">Informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="e6672-140">若要查看，請變更警示篩選，以包含資訊性警示。</span><span class="sxs-lookup"><span data-stu-id="e6672-140">To see them, change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="e6672-141">如果您的組織透過警示管理系統、服務管理系統、安全性資訊和事件管理 (SIEM) 系統來管理安全性警示，您可以透過電子郵件通知或透過 [Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)，將提醒傳送給該系統。</span><span class="sxs-lookup"><span data-stu-id="e6672-141">If your organization manages your security alerts through an alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="e6672-142">透過電子郵件或 API 的調查警示通知包含在安全性 & 規範中心中存取警示的連結，讓指派的安全性系統管理員可以快速流覽調查。</span><span class="sxs-lookup"><span data-stu-id="e6672-142">The investigation alert notifications via email or API include links to access the alerts in the Security & Compliance Center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![連結至調查的警示](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a><span data-ttu-id="e6672-144">安全性行動手冊</span><span class="sxs-lookup"><span data-stu-id="e6672-144">Security playbooks</span></span>

<span data-ttu-id="e6672-145">安全性行動行動是以 Office 高級威脅防護和 Microsoft 威脅防護為自動化的後端原則。</span><span class="sxs-lookup"><span data-stu-id="e6672-145">Security playbooks are back-end policies that are at the heart of automation in Office Advanced Threat Protection and Microsoft Threat Protection.</span></span> <span data-ttu-id="e6672-146">AIR 中所提供的安全性行動技巧是以常見的實際安全性案例為依據，並根據安全性運作小組的意見來開發。</span><span class="sxs-lookup"><span data-stu-id="e6672-146">The security playbooks provided in AIR are based on common real-world security scenarios and developed based on feedback from Security Operations teams.</span></span> <span data-ttu-id="e6672-147">當您的組織內觸發特定警示時，會自動啟動安全性行動手冊。</span><span class="sxs-lookup"><span data-stu-id="e6672-147">A security playbook is launched automatically when specific alerts are triggered within your organization.</span></span> <span data-ttu-id="e6672-148">警示觸發後，就會透過自動調查和回應 (AIR) 系統來執行相關聯的行動手冊。</span><span class="sxs-lookup"><span data-stu-id="e6672-148">Once the alert triggers, the associated playbook is run by the Automated Investigation and Response (AIR) system.</span></span> <span data-ttu-id="e6672-149">調查步驟：透過該特定警示行動手冊分析提醒，查看所有相關聯的中繼資料 (包括電子郵件訊息、使用者、主題、寄件者等 ) 。</span><span class="sxs-lookup"><span data-stu-id="e6672-149">The investigation steps through analysis of the alert based on that particular alert's playbook, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="e6672-150">根據調查行動手冊的結果，AIR 建議您的組織安全小組可以採取的一組動作來控制及緩解威脅。</span><span class="sxs-lookup"><span data-stu-id="e6672-150">Based on the investigation playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="e6672-151">您可以使用 AIR 的安全性行動方式，來處理目前的組織使用電子郵件所遇到的最常見威脅。</span><span class="sxs-lookup"><span data-stu-id="e6672-151">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations encounter today with email.</span></span> <span data-ttu-id="e6672-152">它們是以安全性作業和事件回應小組的輸入為基礎，包括協助保護 Microsoft 和客戶資產的人員。</span><span class="sxs-lookup"><span data-stu-id="e6672-152">They're based on input from Security Operations and Incident Response teams, including people who help defend Microsoft and our customers' assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="e6672-153">安全性行動行動是分階段推出</span><span class="sxs-lookup"><span data-stu-id="e6672-153">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="e6672-154">在飛機的一部分中，安全性行動行動是在階段中推出。</span><span class="sxs-lookup"><span data-stu-id="e6672-154">As part of AIR, security playbooks are rolling out in phases.</span></span> <span data-ttu-id="e6672-155">階段1現在已可供使用，且包含數個行動手冊，可提供安全性管理員可審查及核准的動作建議：</span><span class="sxs-lookup"><span data-stu-id="e6672-155">Phase 1 is now generally available and includes several playbooks that provide recommendations for actions that security administrators can review and approve:</span></span>

- <span data-ttu-id="e6672-156">使用者報告的網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="e6672-156">User-reported phish message</span></span>
- <span data-ttu-id="e6672-157">URL-按一下判定變更</span><span class="sxs-lookup"><span data-stu-id="e6672-157">URL-click verdict change</span></span>
- <span data-ttu-id="e6672-158">惡意程式碼偵測到傳遞後 (惡意程式碼 ZAP) </span><span class="sxs-lookup"><span data-stu-id="e6672-158">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="e6672-159">網路釣魚程式偵測到傳遞後的 ZAP (網路釣魚 ZAP) </span><span class="sxs-lookup"><span data-stu-id="e6672-159">Phish detected post-delivery ZAP (Phish ZAP)</span></span>

<span data-ttu-id="e6672-160">階段1也包含對管理員使用 [威脅 Explorer](threat-explorer.md))  (觸發電子郵件調查的支援。</span><span class="sxs-lookup"><span data-stu-id="e6672-160">Phase 1 also includes support for administrator triggered e-mail investigations (using [Threat Explorer](threat-explorer.md)).</span></span>

<span data-ttu-id="e6672-161">階段2現在的進度是 **公開預覽**中的下列行動手冊、提供動作的建議，以及 aiding 安全性管理員以調查問題：</span><span class="sxs-lookup"><span data-stu-id="e6672-161">Phase 2 is now progress with the following playbooks in **public preview**, providing recommendations for actions, and aiding security administrators in investigating issues:</span></span>

- <span data-ttu-id="e6672-162">使用者報告 (公開預覽的漏洞) </span><span class="sxs-lookup"><span data-stu-id="e6672-162">User reported as compromised (public preview)</span></span>

<span data-ttu-id="e6672-163">更多行動手冊會在完成時發佈。</span><span class="sxs-lookup"><span data-stu-id="e6672-163">More playbooks will be released as they are completed.</span></span> <span data-ttu-id="e6672-164">請造訪 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap) ，以查看已計畫及即將推出的內容。</span><span class="sxs-lookup"><span data-stu-id="e6672-164">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what else is planned and coming soon.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="e6672-165">行動行動包括調查和建議</span><span class="sxs-lookup"><span data-stu-id="e6672-165">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="e6672-166">在 AIR 中，每個安全性行動手冊包括：</span><span class="sxs-lookup"><span data-stu-id="e6672-166">In AIR, each security playbook includes:</span></span> 

- <span data-ttu-id="e6672-167">電子郵件實體的根調查 (例如檔案、URLs、收件者、IP 位址等) ）</span><span class="sxs-lookup"><span data-stu-id="e6672-167">a root investigation of an email's entities (such as files, URLs, recipients, IP addresses, and more),</span></span>
- <span data-ttu-id="e6672-168">進一步搜尋組織所收到的類似電子郵件</span><span class="sxs-lookup"><span data-stu-id="e6672-168">further hunting for similar emails received by the organization</span></span> 
- <span data-ttu-id="e6672-169">識別和關聯其他潛在威脅所採取的步驟，以及</span><span class="sxs-lookup"><span data-stu-id="e6672-169">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="e6672-170">建議的威脅修復動作。</span><span class="sxs-lookup"><span data-stu-id="e6672-170">recommended threat remediation actions.</span></span>

<span data-ttu-id="e6672-171">每個高階步驟都包含一些執行的子步驟，以提供對威脅的深入、詳盡及詳盡的回應。</span><span class="sxs-lookup"><span data-stu-id="e6672-171">Each high-level step includes a number of substeps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="e6672-172">範例：使用者報告的網路釣魚郵件啟動調查行動手冊</span><span class="sxs-lookup"><span data-stu-id="e6672-172">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="e6672-173">假設組織中的使用者收到他們認為是網路釣魚企圖的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e6672-173">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="e6672-174">使用者在報告這類訊息時，會使用 [報告訊息增益集](enable-the-report-message-add-in.md) 將其傳送至 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="e6672-174">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="e6672-175">提交也會傳送至您的系統，而且會顯示在 **提交** 視圖中 (先前稱為 **使用者報告** 的 view) 。</span><span class="sxs-lookup"><span data-stu-id="e6672-175">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="e6672-176">此外，使用者報告的訊息現在會觸發以系統為基礎的資訊性警示，這會自動啟動調查行動手冊。</span><span class="sxs-lookup"><span data-stu-id="e6672-176">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="e6672-177">在根調查階段中，會評估電子郵件的各個層面。</span><span class="sxs-lookup"><span data-stu-id="e6672-177">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="e6672-178">這些方面包括：</span><span class="sxs-lookup"><span data-stu-id="e6672-178">These aspects include:</span></span>

- <span data-ttu-id="e6672-179">決定可能的威脅類型;</span><span class="sxs-lookup"><span data-stu-id="e6672-179">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="e6672-180">誰送出;</span><span class="sxs-lookup"><span data-stu-id="e6672-180">Who sent it;</span></span>
- <span data-ttu-id="e6672-181">電子郵件傳送來源的 (傳送基礎結構) ;</span><span class="sxs-lookup"><span data-stu-id="e6672-181">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="e6672-182">電子郵件的其他實例是否已傳遞或封鎖;</span><span class="sxs-lookup"><span data-stu-id="e6672-182">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="e6672-183">我們分析員的評估;</span><span class="sxs-lookup"><span data-stu-id="e6672-183">An assessment from our analysts;</span></span>
- <span data-ttu-id="e6672-184">電子郵件是否與任何已知的市場活動相關聯;</span><span class="sxs-lookup"><span data-stu-id="e6672-184">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="e6672-185">等等。</span><span class="sxs-lookup"><span data-stu-id="e6672-185">and more.</span></span>

<span data-ttu-id="e6672-186">完成根調查之後，「行動手冊」會提供建議執行的動作清單，以供原始電子郵件和與其相關聯的實體使用。</span><span class="sxs-lookup"><span data-stu-id="e6672-186">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="e6672-187">接下來，會執行數個威脅調查和搜尋步驟：</span><span class="sxs-lookup"><span data-stu-id="e6672-187">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="e6672-188">類似的電子郵件會透過電子郵件聚簇搜尋加以識別。</span><span class="sxs-lookup"><span data-stu-id="e6672-188">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="e6672-189">此信號是與其他平臺（例如 [Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共用。</span><span class="sxs-lookup"><span data-stu-id="e6672-189">The signal is shared with other platforms, such as [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="e6672-190">決定是否任何使用者已透過可疑電子郵件訊息中的任何惡意連結進行按一下。</span><span class="sxs-lookup"><span data-stu-id="e6672-190">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="e6672-191">在 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 Office 365 的高級威脅防護 ([ATP](office-365-atp.md)) 之間進行檢查，以查看使用者是否會報告其他類似的訊息。</span><span class="sxs-lookup"><span data-stu-id="e6672-191">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="e6672-192">會執行檢查以查看使用者是否遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="e6672-192">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="e6672-193">這種檢查會利用跨 Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)的信號，以關聯任何相關的使用者活動異常。</span><span class="sxs-lookup"><span data-stu-id="e6672-193">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="e6672-194">在搜尋階段中，會將風險和威脅指派給各種搜尋步驟。</span><span class="sxs-lookup"><span data-stu-id="e6672-194">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="e6672-195">修正是行動手冊的最後階段。</span><span class="sxs-lookup"><span data-stu-id="e6672-195">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="e6672-196">在此階段中，會根據調查和搜尋階段採取補救措施。</span><span class="sxs-lookup"><span data-stu-id="e6672-196">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="e6672-197">範例：安全性管理員會觸發來自威脅瀏覽器的調查</span><span class="sxs-lookup"><span data-stu-id="e6672-197">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="e6672-198">除了警示所觸發的自動調查之外，您的組織的安全性運作小組也可在 [威脅瀏覽器](threat-explorer.md)的視圖中觸發自動調查。</span><span class="sxs-lookup"><span data-stu-id="e6672-198">In addition to automated investigations that are triggered by an alert, your organization's security operations team can trigger an automated investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>

<span data-ttu-id="e6672-199">例如，假設您在威脅瀏覽器中使用 **惡意** 代碼視圖。</span><span class="sxs-lookup"><span data-stu-id="e6672-199">For example, suppose that you are using the **Malware** view in Threat Explorer.</span></span> <span data-ttu-id="e6672-200">您可以使用圖表下方的索引標籤，選取 [ **電子郵件** ] 索引標籤。如果您選取清單中的一或多個專案，則會啟動 **+ 動作** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e6672-200">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span> 

![具有選取郵件的 Explorer](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="e6672-202">您可以使用 [ **動作** ] 功能表，選取 [ **觸發調查**]。</span><span class="sxs-lookup"><span data-stu-id="e6672-202">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![選取郵件的動作功能表](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="e6672-204">類似于警示所觸發的行動行動方式，從瀏覽器中的視圖觸發的自動調查包括根調查、識別和關聯威脅的步驟，以及緩解這些威脅的建議動作。</span><span class="sxs-lookup"><span data-stu-id="e6672-204">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a><span data-ttu-id="e6672-205">範例：使用 Office 365 管理活動 API，安全性運作小組與其 SIEM 整合 AIR</span><span class="sxs-lookup"><span data-stu-id="e6672-205">Example: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>

<span data-ttu-id="e6672-206">Office 365 ATP 中的 AIR 功能包括 [報告 & 詳細資料](air-view-investigation-results.md) ，安全性作業小組可用以監視和處理威脅。</span><span class="sxs-lookup"><span data-stu-id="e6672-206">AIR capabilities in Office 365 ATP include [reports & details](air-view-investigation-results.md) that security operations team can use to monitor and address threats.</span></span> <span data-ttu-id="e6672-207">不過，您也可以整合 AIR 功能與其他解決方案。</span><span class="sxs-lookup"><span data-stu-id="e6672-207">But you can also integrate AIR capabilities with other solutions.</span></span> <span data-ttu-id="e6672-208">範例包括安全性資訊和事件管理 (SIEM) 系統、案例管理系統或自訂報告解決方案。</span><span class="sxs-lookup"><span data-stu-id="e6672-208">Examples include a security information and event management (SIEM) system, a case management system, or a custom reporting solution.</span></span> <span data-ttu-id="e6672-209">您可以使用 [Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)來完成這些整合類型。</span><span class="sxs-lookup"><span data-stu-id="e6672-209">These kinds of integration can be done by using the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="e6672-210">例如，在最近，組織會設定安全性作業小組的方式，以查看已由 AIR 處理的使用者報告網路釣魚警報。</span><span class="sxs-lookup"><span data-stu-id="e6672-210">For example, recently, an organization set up a way for their security operations team to view user-reported phish alerts that were already processed by AIR.</span></span> <span data-ttu-id="e6672-211">其解決方案會將相關的警示與組織的 SIEM 伺服器及其案例管理系統整合在一起。</span><span class="sxs-lookup"><span data-stu-id="e6672-211">Their solution integrates relevant alerts with the organization's SIEM server and their case-management system.</span></span> <span data-ttu-id="e6672-212">此解決方案大幅減少誤報的數目，讓他們的安全性運作小組能夠專注于實際威脅的時間和工作。</span><span class="sxs-lookup"><span data-stu-id="e6672-212">The solution greatly reduces the number of false positives so that their security operations team can focus their time and effort on real threats.</span></span> <span data-ttu-id="e6672-213">若要深入瞭解此自訂解決方案，請參閱 [技術社區博客：使用 Office 365 ATP 和 O365 管理 API，改善 SOC 的效能](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="e6672-213">To learn more about this custom solution, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

## <a name="next-step"></a><span data-ttu-id="e6672-214">下一步</span><span class="sxs-lookup"><span data-stu-id="e6672-214">Next step</span></span>

- [<span data-ttu-id="e6672-215">開始使用 AIR</span><span class="sxs-lookup"><span data-stu-id="e6672-215">Get started using AIR</span></span>](office-365-air.md)

## <a name="see-also"></a><span data-ttu-id="e6672-216">請參閱</span><span class="sxs-lookup"><span data-stu-id="e6672-216">See also</span></span>

- [<span data-ttu-id="e6672-217">Microsoft 365 藍圖</span><span class="sxs-lookup"><span data-stu-id="e6672-217">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [<span data-ttu-id="e6672-218">Microsoft 威脅防護中的自動化調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="e6672-218">Automated investigation and response capabilities in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide)
