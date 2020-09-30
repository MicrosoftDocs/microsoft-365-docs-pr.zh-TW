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
keywords: 自動化的事件回應、調查、修正及威脅防護
ms.date: 09/29/2020
description: 深入瞭解 Microsoft Defender for Office 365 中的自動化調查和回應功能
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: ce95b91aa67f76cf46ce3ed6285e24d3e9edd146
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308951"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0f97a-104">Microsoft Defender for Office 365 的自動化調查和回應 (AIR) 的概覽</span><span class="sxs-lookup"><span data-stu-id="0f97a-104">An overview of automated investigation and response (AIR) in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0f97a-105">在觸發安全性警示時，您的安全性運作小組會檢查這些警示，並採取步驟來保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="0f97a-105">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="0f97a-106">在某些情況下，安全性作業小組可能感覺到所觸發的警示數量所淹沒。</span><span class="sxs-lookup"><span data-stu-id="0f97a-106">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="0f97a-107">Microsoft Defender for Office 365 中 (AIR) 功能的自動化調查和回應可提供協助。</span><span class="sxs-lookup"><span data-stu-id="0f97a-107">Automated investigation and response (AIR) capabilities in Microsoft Defender for Office 365 can help.</span></span> 

<span data-ttu-id="0f97a-108">AIR 可讓您的安全性運作小組更有效率地運作。</span><span class="sxs-lookup"><span data-stu-id="0f97a-108">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="0f97a-109">AIR 功能包括自動調查處理程式，以回應目前存在的已知威脅。</span><span class="sxs-lookup"><span data-stu-id="0f97a-109">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="0f97a-110">適當的修正動作等待核准，讓您的安全性作業小組能夠回應偵測到的威脅。</span><span class="sxs-lookup"><span data-stu-id="0f97a-110">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span> 

<span data-ttu-id="0f97a-111">本文提供空中的概覽。</span><span class="sxs-lookup"><span data-stu-id="0f97a-111">This article provides an overview of AIR.</span></span> <span data-ttu-id="0f97a-112">當您準備好開始使用 AIR 時，請參閱 [自動調查和回應威脅](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="0f97a-112">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

## <a name="at-a-high-level"></a><span data-ttu-id="0f97a-113">在高層級</span><span class="sxs-lookup"><span data-stu-id="0f97a-113">At a high level</span></span>

<span data-ttu-id="0f97a-114">當觸發警示時，安全性行動行動會生效。</span><span class="sxs-lookup"><span data-stu-id="0f97a-114">As alerts are triggered, security playbooks go into effect.</span></span> <span data-ttu-id="0f97a-115">根據情況而定，可以開始進行 [自動化調查過程](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) 。</span><span class="sxs-lookup"><span data-stu-id="0f97a-115">Depending on the situation, an [automated investigation process](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) can begin.</span></span> <span data-ttu-id="0f97a-116">在自動調查期間和之後，建議進行 [修正動作](air-remediation-actions.md) 。</span><span class="sxs-lookup"><span data-stu-id="0f97a-116">During and after an automated investigation, [remediation actions](air-remediation-actions.md) are recommended.</span></span> <span data-ttu-id="0f97a-117">在 Microsoft Defender for Office 365 中不會自動採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="0f97a-117">No actions are taken automatically in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="0f97a-118">您的安全性運作小組會評論，然後 [核准或拒絕每項修復動作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="0f97a-118">Your security operations team reviews, and then [approves or rejects each remediation action](air-review-approve-pending-completed-actions.md).</span></span> <span data-ttu-id="0f97a-119">在調查中的所有動作經核准或拒絕時，調查都會完成。</span><span class="sxs-lookup"><span data-stu-id="0f97a-119">When all of the actions following an investigation are approved or rejected, the investigation completes.</span></span> <span data-ttu-id="0f97a-120">您可以在 Microsoft 365 的安全性中心 () 中追蹤和查看所有這些活動 [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="0f97a-120">All of these activities are tracked and viewable in the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="0f97a-121"> (若要深入瞭解，請參閱 [查看調查) 的詳細資料](air-view-investigation-results.md#view-details-of-an-investigation) 。</span><span class="sxs-lookup"><span data-stu-id="0f97a-121">(To learn more, see [View details of an investigation](air-view-investigation-results.md#view-details-of-an-investigation)).</span></span>

<span data-ttu-id="0f97a-122">下列各節提供有關警示、安全性行動手冊及動作中的空氣範例的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0f97a-122">The following sections provide more details about alerts, security playbooks, and examples of AIR in action.</span></span>

## <a name="alerts"></a><span data-ttu-id="0f97a-123">警示</span><span class="sxs-lookup"><span data-stu-id="0f97a-123">Alerts</span></span>

<span data-ttu-id="0f97a-124">[警示](../../compliance/alert-policies.md#viewing-alerts) 代表事件回應的安全性作業小組工作流程的觸發器。</span><span class="sxs-lookup"><span data-stu-id="0f97a-124">[Alerts](../../compliance/alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="0f97a-125">決定要調查的適當一組提醒，同時確保沒有威脅 unaddressed 面臨挑戰。</span><span class="sxs-lookup"><span data-stu-id="0f97a-125">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="0f97a-126">當手動調查何時會以手動方式執行提醒時，安全性作業小組必須搜尋和關聯實體 (例如內容、裝置和使用者) 威脅以外的風險。</span><span class="sxs-lookup"><span data-stu-id="0f97a-126">When investigations into alerts are performed manually, security operations teams must hunt and correlate entities (such as content, devices and users) at risk from threats.</span></span> <span data-ttu-id="0f97a-127">這類工作和工作流程可能非常耗時且包含多個工具和系統。</span><span class="sxs-lookup"><span data-stu-id="0f97a-127">Such tasks and workflows can be very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="0f97a-128">透過利用關鍵安全性和威脅管理提醒自動觸發安全性回應行動手冊，透過 AIR、安全事件的調查和回應可自動進行。</span><span class="sxs-lookup"><span data-stu-id="0f97a-128">With AIR, investigation and response for security events are automated by having key security and threat management alerts trigger security response playbooks automatically.</span></span> 

<span data-ttu-id="0f97a-129">目前對於 AIR，會自動調查從下列類型的報警原則產生的警示：</span><span class="sxs-lookup"><span data-stu-id="0f97a-129">Currently for AIR, alerts generated from the following kinds of alert policies are auto-investigated:</span></span>  

- <span data-ttu-id="0f97a-130">偵測到可能的惡意 URL 按一下</span><span class="sxs-lookup"><span data-stu-id="0f97a-130">A potentially malicious URL click was detected</span></span>
- <span data-ttu-id="0f97a-131">使用者以網路釣魚方式舉報的電子郵件`*`</span><span class="sxs-lookup"><span data-stu-id="0f97a-131">Email reported by user as phish`*`</span></span>
- <span data-ttu-id="0f97a-132">傳遞後移除包含惡意程式碼的電子郵件`*`</span><span class="sxs-lookup"><span data-stu-id="0f97a-132">Email messages containing malware removed after delivery`*`</span></span>
- <span data-ttu-id="0f97a-133">傳遞後移除包含網路釣魚 URLs 的電子郵件`*`</span><span class="sxs-lookup"><span data-stu-id="0f97a-133">Email messages containing phish URLs removed after delivery`*`</span></span>
- <span data-ttu-id="0f97a-134">偵測到電子郵件傳送模式</span><span class="sxs-lookup"><span data-stu-id="0f97a-134">Suspicious email sending patterns detected</span></span>
- <span data-ttu-id="0f97a-135">使用者限制傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="0f97a-135">User restricted from sending email</span></span>
- <span data-ttu-id="0f97a-136">管理員已觸發手動調查電子郵件`*`</span><span class="sxs-lookup"><span data-stu-id="0f97a-136">Admin triggered manual investigation of email`*`</span></span>

> [!NOTE]
> <span data-ttu-id="0f97a-137">以星號 () 標示的警示 `*` 會在 Microsoft 365 安全性中心內的各項警示原則中指派 *資訊* 嚴重性，並關閉電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="0f97a-137">The alerts marked with an asterisk (`*`) are assigned an *Informational* severity in the respective alert policies within the Microsoft 365 security center, with email notifications turned off.</span></span> <span data-ttu-id="0f97a-138">您可以透過 [報警原則](../../compliance/alert-policies.md#alert-policy-settings)設定開啟電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="0f97a-138">Email notifications can be turned on through [Alert policy configuration](../../compliance/alert-policies.md#alert-policy-settings).</span></span> 

<span data-ttu-id="0f97a-139">若要在安全性 & 規範中心中查看提醒，請選擇 [**提醒**] [  >  **查看提醒**]。</span><span class="sxs-lookup"><span data-stu-id="0f97a-139">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="0f97a-140">選取警示以查看其詳細資料，然後從那裡使用「 **查看調查** 」連結，以移至對應的 [調查](air-view-investigation-results.md#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="0f97a-140">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](air-view-investigation-results.md#investigation-graph).</span></span>  

> [!NOTE]
> <span data-ttu-id="0f97a-141">預設會在提醒視圖中隱藏資訊警示。</span><span class="sxs-lookup"><span data-stu-id="0f97a-141">Informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="0f97a-142">若要查看，請變更警示篩選，以包含資訊性警示。</span><span class="sxs-lookup"><span data-stu-id="0f97a-142">To see them, change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="0f97a-143">如果您的組織透過警示管理系統、服務管理系統、安全性資訊和事件管理 (SIEM) 系統來管理安全性警示，您可以透過電子郵件通知或透過 [Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)，將提醒傳送給該系統。</span><span class="sxs-lookup"><span data-stu-id="0f97a-143">If your organization manages your security alerts through an alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="0f97a-144">透過電子郵件或 API 的調查警示通知包含的連結可存取 Microsoft 365 安全中心的警示，讓指派的安全性系統管理員可以快速流覽調查。</span><span class="sxs-lookup"><span data-stu-id="0f97a-144">The investigation alert notifications via email or API include links to access the alerts in the Microsoft 365 security center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![連結至調查的警示](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a><span data-ttu-id="0f97a-146">安全性行動手冊</span><span class="sxs-lookup"><span data-stu-id="0f97a-146">Security playbooks</span></span>

<span data-ttu-id="0f97a-147">安全性行動手冊是以 Microsoft Defender for Office 365 和 Microsoft 威脅防護為自動化的後端原則。</span><span class="sxs-lookup"><span data-stu-id="0f97a-147">Security playbooks are back-end policies that are at the heart of automation in Microsoft Defender for Office 365 and Microsoft Threat Protection.</span></span> <span data-ttu-id="0f97a-148">AIR 中所提供的安全性行動技巧是以常見的實際安全性案例為依據，並根據安全性運作小組的意見來開發。</span><span class="sxs-lookup"><span data-stu-id="0f97a-148">The security playbooks provided in AIR are based on common real-world security scenarios and developed based on feedback from security operations teams.</span></span> <span data-ttu-id="0f97a-149">當您的組織內觸發特定警示時，會自動啟動安全性行動手冊。</span><span class="sxs-lookup"><span data-stu-id="0f97a-149">A security playbook is launched automatically when specific alerts are triggered within your organization.</span></span> <span data-ttu-id="0f97a-150">警示觸發後，會自動調查和回應系統執行相關聯的行動手冊。</span><span class="sxs-lookup"><span data-stu-id="0f97a-150">Once the alert triggers, the associated playbook is run by the automated investigation and response system.</span></span> <span data-ttu-id="0f97a-151">調查步驟：透過該特定警示行動手冊分析提醒，查看所有相關聯的中繼資料 (包括電子郵件訊息、使用者、主題、寄件者等 ) 。</span><span class="sxs-lookup"><span data-stu-id="0f97a-151">The investigation steps through analysis of the alert based on that particular alert's playbook, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="0f97a-152">根據調查行動手冊的結果，AIR 建議您的組織安全小組可以採取的一組動作來控制及緩解威脅。</span><span class="sxs-lookup"><span data-stu-id="0f97a-152">Based on the investigation playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="0f97a-153">您可以使用 AIR 的安全性行動方式，來處理目前的組織使用電子郵件所遇到的最常見威脅。</span><span class="sxs-lookup"><span data-stu-id="0f97a-153">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations encounter today with email.</span></span> <span data-ttu-id="0f97a-154">它們是以安全性作業和事件回應小組的輸入為基礎，包括協助保護 Microsoft 和客戶資產的人員。</span><span class="sxs-lookup"><span data-stu-id="0f97a-154">They're based on input from security operations and incident response teams, including people who help defend Microsoft and our customers' assets.</span></span>

- <span data-ttu-id="0f97a-155">使用者報告的網路釣魚郵件</span><span class="sxs-lookup"><span data-stu-id="0f97a-155">User-reported phish message</span></span>
- <span data-ttu-id="0f97a-156">URL-按一下判定變更</span><span class="sxs-lookup"><span data-stu-id="0f97a-156">URL-click verdict change</span></span>
- <span data-ttu-id="0f97a-157">惡意程式碼偵測到傳遞後 (惡意程式碼 ZAP) </span><span class="sxs-lookup"><span data-stu-id="0f97a-157">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="0f97a-158">網路釣魚程式偵測到傳遞後的 ZAP (網路釣魚 ZAP) </span><span class="sxs-lookup"><span data-stu-id="0f97a-158">Phish detected post-delivery ZAP (Phish ZAP)</span></span>
- <span data-ttu-id="0f97a-159">使用者報告為已遭破壞</span><span class="sxs-lookup"><span data-stu-id="0f97a-159">User reported as compromised</span></span> 
- <span data-ttu-id="0f97a-160">管理員從瀏覽器惡意程式碼、網路釣魚或所有電子郵件視圖觸發的手動電子郵件調查 () </span><span class="sxs-lookup"><span data-stu-id="0f97a-160">Manual email investigation (triggered by administrator from Explorer Malware, Phish, or All Email view)</span></span>

<span data-ttu-id="0f97a-161">更多行動手冊和行動手冊更新會在完成時發佈。</span><span class="sxs-lookup"><span data-stu-id="0f97a-161">More playbooks and playbook updates will be released as they are completed.</span></span> <span data-ttu-id="0f97a-162">請造訪 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap) ，以查看已計畫及即將推出的內容。</span><span class="sxs-lookup"><span data-stu-id="0f97a-162">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what else is planned and coming soon.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="0f97a-163">行動行動包括調查和建議</span><span class="sxs-lookup"><span data-stu-id="0f97a-163">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="0f97a-164">在 AIR 中，每個安全性行動手冊包括：</span><span class="sxs-lookup"><span data-stu-id="0f97a-164">In AIR, each security playbook includes:</span></span> 

- <span data-ttu-id="0f97a-165">電子郵件實體的根調查 (例如檔案、URLs、收件者、IP 位址等) ）</span><span class="sxs-lookup"><span data-stu-id="0f97a-165">a root investigation of an email's entities (such as files, URLs, recipients, IP addresses, and more),</span></span>
- <span data-ttu-id="0f97a-166">進一步搜尋組織所收到的類似電子郵件</span><span class="sxs-lookup"><span data-stu-id="0f97a-166">further hunting for similar emails received by the organization</span></span> 
- <span data-ttu-id="0f97a-167">識別和關聯其他潛在威脅所採取的步驟，以及</span><span class="sxs-lookup"><span data-stu-id="0f97a-167">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="0f97a-168">建議的威脅修復動作。</span><span class="sxs-lookup"><span data-stu-id="0f97a-168">recommended threat remediation actions.</span></span>

<span data-ttu-id="0f97a-169">每個高階步驟都包含一些執行的子步驟，以提供對威脅的深入、詳盡及詳盡的回應。</span><span class="sxs-lookup"><span data-stu-id="0f97a-169">Each high-level step includes a number of substeps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="0f97a-170">範例：使用者報告的網路釣魚郵件啟動調查行動手冊</span><span class="sxs-lookup"><span data-stu-id="0f97a-170">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="0f97a-171">假設組織中的使用者收到他們認為是網路釣魚企圖的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0f97a-171">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="0f97a-172">使用者在報告這類訊息時，會使用 [報告訊息增益集](enable-the-report-message-add-in.md) 將其傳送至 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="0f97a-172">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="0f97a-173">提交也會傳送至您的系統，而且會顯示在 **提交** 視圖中 (先前稱為 **使用者報告** 的 view) 。</span><span class="sxs-lookup"><span data-stu-id="0f97a-173">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="0f97a-174">此外，使用者報告的訊息現在會觸發以系統為基礎的資訊性警示，這會自動啟動調查行動手冊。</span><span class="sxs-lookup"><span data-stu-id="0f97a-174">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="0f97a-175">在根調查階段中，會評估電子郵件的各個層面。</span><span class="sxs-lookup"><span data-stu-id="0f97a-175">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="0f97a-176">這些方面包括：</span><span class="sxs-lookup"><span data-stu-id="0f97a-176">These aspects include:</span></span>

- <span data-ttu-id="0f97a-177">決定可能的威脅類型;</span><span class="sxs-lookup"><span data-stu-id="0f97a-177">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="0f97a-178">誰送出;</span><span class="sxs-lookup"><span data-stu-id="0f97a-178">Who sent it;</span></span>
- <span data-ttu-id="0f97a-179">電子郵件傳送來源的 (傳送基礎結構) ;</span><span class="sxs-lookup"><span data-stu-id="0f97a-179">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="0f97a-180">電子郵件的其他實例是否已傳遞或封鎖;</span><span class="sxs-lookup"><span data-stu-id="0f97a-180">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="0f97a-181">我們分析員的評估;</span><span class="sxs-lookup"><span data-stu-id="0f97a-181">An assessment from our analysts;</span></span>
- <span data-ttu-id="0f97a-182">電子郵件是否與任何已知的市場活動相關聯;</span><span class="sxs-lookup"><span data-stu-id="0f97a-182">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="0f97a-183">等等。</span><span class="sxs-lookup"><span data-stu-id="0f97a-183">and more.</span></span>

<span data-ttu-id="0f97a-184">完成根調查之後，「行動手冊」會提供建議執行的動作清單，以供原始電子郵件和與其相關聯的實體使用。</span><span class="sxs-lookup"><span data-stu-id="0f97a-184">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="0f97a-185">接下來，會執行數個威脅調查和搜尋步驟：</span><span class="sxs-lookup"><span data-stu-id="0f97a-185">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="0f97a-186">類似的電子郵件會透過電子郵件聚簇搜尋加以識別。</span><span class="sxs-lookup"><span data-stu-id="0f97a-186">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="0f97a-187">此信號是與其他平臺（例如 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共用。</span><span class="sxs-lookup"><span data-stu-id="0f97a-187">The signal is shared with other platforms, such as [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="0f97a-188">決定是否任何使用者已透過可疑電子郵件訊息中的任何惡意連結進行按一下。</span><span class="sxs-lookup"><span data-stu-id="0f97a-188">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="0f97a-189">在 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 Office 365 的高級威脅防護 ([ATP](office-365-atp.md)) 之間進行檢查，以查看使用者是否會報告其他類似的訊息。</span><span class="sxs-lookup"><span data-stu-id="0f97a-189">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="0f97a-190">會執行檢查以查看使用者是否遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="0f97a-190">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="0f97a-191">這種檢查會利用跨 Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)的信號，以關聯任何相關的使用者活動異常。</span><span class="sxs-lookup"><span data-stu-id="0f97a-191">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="0f97a-192">在搜尋階段中，會將風險和威脅指派給各種搜尋步驟。</span><span class="sxs-lookup"><span data-stu-id="0f97a-192">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="0f97a-193">修正是行動手冊的最後階段。</span><span class="sxs-lookup"><span data-stu-id="0f97a-193">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="0f97a-194">在此階段中，會根據調查和搜尋階段採取補救措施。</span><span class="sxs-lookup"><span data-stu-id="0f97a-194">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="0f97a-195">範例：安全性管理員會觸發來自威脅瀏覽器的調查</span><span class="sxs-lookup"><span data-stu-id="0f97a-195">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="0f97a-196">除了警示所觸發的自動調查之外，您的組織的安全性運作小組也可在 [威脅瀏覽器](threat-explorer.md)的視圖中觸發自動調查。</span><span class="sxs-lookup"><span data-stu-id="0f97a-196">In addition to automated investigations that are triggered by an alert, your organization's security operations team can trigger an automated investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>  <span data-ttu-id="0f97a-197">這種調查也會建立警示，使 Microsoft Defender 事件和外部 SIEM 工具可以查看已觸發此調查。</span><span class="sxs-lookup"><span data-stu-id="0f97a-197">This investigation also creates an alert, so that Microsoft Defender Incidents and external SIEM tools can see that this investigation was triggered.</span></span> 

<span data-ttu-id="0f97a-198">例如，假設您在瀏覽器中使用 **惡意** 代碼視圖。</span><span class="sxs-lookup"><span data-stu-id="0f97a-198">For example, suppose that you are using the **Malware** view in Explorer.</span></span> <span data-ttu-id="0f97a-199">您可以使用圖表下方的索引標籤，選取 [ **電子郵件** ] 索引標籤。如果您選取清單中的一或多個專案，則會啟動 **+ 動作** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="0f97a-199">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span> 

![具有選取郵件的 Explorer](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="0f97a-201">您可以使用 [ **動作** ] 功能表，選取 [ **觸發調查**]。</span><span class="sxs-lookup"><span data-stu-id="0f97a-201">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![選取郵件的動作功能表](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="0f97a-203">類似于警示所觸發的行動行動方式，從瀏覽器中的視圖觸發的自動調查包括根調查、識別和關聯威脅的步驟，以及緩解這些威脅的建議動作。</span><span class="sxs-lookup"><span data-stu-id="0f97a-203">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a><span data-ttu-id="0f97a-204">範例：使用 Office 365 管理活動 API，安全性運作小組與其 SIEM 整合 AIR</span><span class="sxs-lookup"><span data-stu-id="0f97a-204">Example: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>

<span data-ttu-id="0f97a-205">Microsoft Defender for Office 365 中的 AIR 功能包括 [報告 & 詳細資料](air-view-investigation-results.md) ，安全性作業小組可用以監視和處理威脅。</span><span class="sxs-lookup"><span data-stu-id="0f97a-205">AIR capabilities in Microsoft Defender for Office 365 include [reports & details](air-view-investigation-results.md) that security operations teams can use to monitor and address threats.</span></span> <span data-ttu-id="0f97a-206">不過，您也可以整合 AIR 功能與其他解決方案。</span><span class="sxs-lookup"><span data-stu-id="0f97a-206">But you can also integrate AIR capabilities with other solutions.</span></span> <span data-ttu-id="0f97a-207">範例包括安全性資訊和事件管理 (SIEM) 系統、案例管理系統或自訂報告解決方案。</span><span class="sxs-lookup"><span data-stu-id="0f97a-207">Examples include a security information and event management (SIEM) system, a case management system, or a custom reporting solution.</span></span> <span data-ttu-id="0f97a-208">您可以使用 [Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)來完成這些類型的整合。</span><span class="sxs-lookup"><span data-stu-id="0f97a-208">These kinds of integrations can be done by using the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="0f97a-209">例如，在最近，組織會設定安全性作業小組的方式，以查看已由 AIR 處理的使用者報告網路釣魚警報。</span><span class="sxs-lookup"><span data-stu-id="0f97a-209">For example, recently, an organization set up a way for their security operations team to view user-reported phish alerts that were already processed by AIR.</span></span> <span data-ttu-id="0f97a-210">其解決方案會將相關的警示與組織的 SIEM 伺服器及其案例管理系統整合在一起。</span><span class="sxs-lookup"><span data-stu-id="0f97a-210">Their solution integrates relevant alerts with the organization's SIEM server and their case-management system.</span></span> <span data-ttu-id="0f97a-211">此解決方案大幅減少誤報的數目，讓他們的安全性運作小組能夠專注于實際威脅的時間和工作。</span><span class="sxs-lookup"><span data-stu-id="0f97a-211">The solution greatly reduces the number of false positives so that their security operations team can focus their time and effort on real threats.</span></span> <span data-ttu-id="0f97a-212">若要深入瞭解此自訂解決方案，請參閱 [技術社區博客：使用 Office 365 ATP 和 O365 管理 API，改善 SOC 的效能](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="0f97a-212">To learn more about this custom solution, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0f97a-213">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0f97a-213">Next steps</span></span>

- [<span data-ttu-id="0f97a-214">開始使用 AIR</span><span class="sxs-lookup"><span data-stu-id="0f97a-214">Get started using AIR</span></span>](office-365-air.md)

- [<span data-ttu-id="0f97a-215">流覽 Microsoft 365 藍圖，以查看已計畫及即將發行的專案</span><span class="sxs-lookup"><span data-stu-id="0f97a-215">Visit the Microsoft 365 Roadmap to see what's planned and releasing soon</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [<span data-ttu-id="0f97a-216">深入瞭解 Microsoft 365 Defender 中的其他自動化調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="0f97a-216">Learn about additional automated investigation and response capabilities in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
