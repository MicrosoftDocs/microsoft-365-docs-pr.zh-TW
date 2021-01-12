---
title: Microsoft Defender for Office 365 中的自動調查和回應
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/05/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 開始使用 Microsoft Defender for Office 365 中的自動調查和回應功能。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 6ccefb5c435f08fcef4dcc872af676fba70668ee
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794541"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f1ae9-104">Microsoft Defender for Office 365 中的自動調查和回應 (AIR) </span><span class="sxs-lookup"><span data-stu-id="f1ae9-104">Automated investigation and response (AIR) in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f1ae9-105">[Microsoft Defender For Office 365](office-365-atp.md) 包含強大的自動化調查和回應 (空氣) 功能，可節約您的安全性運作小組時間和工作。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-105">[Microsoft Defender for Office 365](office-365-atp.md) includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="f1ae9-106">當觸發警示時，您的安全性作業小組會檢查、優先順序及回應這些警示。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="f1ae9-107">保持傳入提醒的數量非常驚人。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="f1ae9-108">自動化某些工作可以協助。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-108">Automating some of those tasks can help.</span></span>

<span data-ttu-id="f1ae9-109">AIR 可讓您的安全性運作小組更有效率地運作。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-109">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="f1ae9-110">AIR 功能包括自動調查處理程式，以回應目前存在的已知威脅。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-110">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="f1ae9-111">適當的修正動作等待核准，讓安全性作業小組能夠有效地回應偵測到的威脅。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-111">Appropriate remediation actions await approval, enabling your security operations team to respond effectively to detected threats.</span></span> <span data-ttu-id="f1ae9-112">透過 AIR，您的安全性運作小組可以著重于優先順序較高的工作，而不會失去所觸發之重要警示的視線。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-112">With AIR, your security operations team can focus on higher-priority tasks without losing sight of important alerts that are triggered.</span></span>

<span data-ttu-id="f1ae9-113">本文說明：</span><span class="sxs-lookup"><span data-stu-id="f1ae9-113">This article describes:</span></span>

- <span data-ttu-id="f1ae9-114">[空氣的整體流向](#the-overall-flow-of-air);</span><span class="sxs-lookup"><span data-stu-id="f1ae9-114">The [overall flow of AIR](#the-overall-flow-of-air);</span></span>
- <span data-ttu-id="f1ae9-115">[如何取得空氣](#how-to-get-air);和</span><span class="sxs-lookup"><span data-stu-id="f1ae9-115">[How to get AIR](#how-to-get-air); and</span></span>
- <span data-ttu-id="f1ae9-116">設定或使用 AIR 功能 [所需的許可權](#required-permissions-to-use-air-capabilities) 。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-116">The [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span>

<span data-ttu-id="f1ae9-117">本文也包含 [後續步驟](#next-steps)，以及深入瞭解的資源。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-117">This article also includes [next steps](#next-steps), and resources to learn more.</span></span>

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="f1ae9-118">空氣的整體流動</span><span class="sxs-lookup"><span data-stu-id="f1ae9-118">The overall flow of AIR</span></span>

<span data-ttu-id="f1ae9-119">會觸發警示，安全性行動手冊會開始進行自動調查，進而會產生結果和建議的動作。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-119">An alert is triggered, and a security playbook starts an automated investigation, which results in findings and recommended actions.</span></span> <span data-ttu-id="f1ae9-120">以下是空氣的整體流動流程，逐步執行：</span><span class="sxs-lookup"><span data-stu-id="f1ae9-120">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="f1ae9-121">自動調查是以下列其中一種方式啟動：</span><span class="sxs-lookup"><span data-stu-id="f1ae9-121">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="f1ae9-122">[警示是](#which-alert-policies-trigger-automated-investigations)由電子郵件 (中的可疑專案（例如郵件、附件、URL 或遭到破壞的使用者帳戶) ）所觸發。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-122">An [alert is triggered](#which-alert-policies-trigger-automated-investigations) by something suspicious in email (such as a message, attachment, URL, or compromised user account).</span></span> <span data-ttu-id="f1ae9-123">會建立事件，並開始自動調查。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-123">An incident is created, and an automated investigation begins.</span></span>

     <span data-ttu-id="f1ae9-124">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="f1ae9-124">--- or ---</span></span>

   - <span data-ttu-id="f1ae9-125">安全分析員會在使用[威脅瀏覽器](threat-explorer.md)時[開始自動調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-125">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="f1ae9-126">當自動調查執行時，它會收集有關電子郵件的其他資料，以及與該電子郵件相關的實體。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-126">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="f1ae9-127">這類實體可以包含檔案、URLs 及收件者。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-127">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="f1ae9-128">調查的範圍會隨著新的和相關的提醒觸發而增加。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-128">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="f1ae9-129">在自動調查的期間和之後，都可以查看 [詳細資料和結果](air-view-investigation-results.md) 。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-129">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="f1ae9-130">結果包括可以採取的 [建議動作](air-remediation-actions.md) ，以回應及修正找到的任何威脅。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-130">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond to and remediate any threats that were found.</span></span> <span data-ttu-id="f1ae9-131">此外，也可以使用 [行動手冊記錄](air-view-investigation-results.md#playbook-log) 來追蹤所有調查活動。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-131">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>

4. <span data-ttu-id="f1ae9-132">您的安全性運作小組會檢查 [調查結果和建議](air-view-investigation-results.md)，並 [批准或拒絕修正動作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-132">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span>

5. <span data-ttu-id="f1ae9-133">當擱置的修復動作獲批准 (或拒絕) 時，自動調查即完成。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-133">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1ae9-134">在適用于 Office 365 的 Microsoft Defender 中，不會自動採取任何修正動作。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-134">In Microsoft Defender for Office 365, no remediation actions are taken automatically.</span></span> <span data-ttu-id="f1ae9-135">在組織的安全性小組核准後才能採取補救動作。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-135">Remediation actions are taken only upon approval by your organization's security team.</span></span>
>
> <span data-ttu-id="f1ae9-136">AIR 功能可透過識別修正動作來儲存您的安全性運作小組時間，並提供做出明智決定所需的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-136">AIR capabilities save your security operations team time by identifying remediation actions and providing the details needed to make an informed decision.</span></span>

<span data-ttu-id="f1ae9-137">在每次自動調查期間和之後，您的安全性作業小組可以：</span><span class="sxs-lookup"><span data-stu-id="f1ae9-137">During and after each automated investigation, your security operations team can:</span></span>

- [<span data-ttu-id="f1ae9-138">檢視與調查相關警示的詳細資料</span><span class="sxs-lookup"><span data-stu-id="f1ae9-138">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="f1ae9-139">查看調查的結果詳細資料</span><span class="sxs-lookup"><span data-stu-id="f1ae9-139">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="f1ae9-140">根據調查的結果檢閱和核准動作</span><span class="sxs-lookup"><span data-stu-id="f1ae9-140">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="f1ae9-141">如需詳細資訊，請參閱 [AIR 的運作方式](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-141">For a more detailed overview, see [How AIR works](automated-investigation-response-office.md).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="f1ae9-142">如何取得空中</span><span class="sxs-lookup"><span data-stu-id="f1ae9-142">How to get AIR</span></span>

<span data-ttu-id="f1ae9-143">AIR 功能包含在 [適用于 Office 365 的 Microsoft Defender](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)中，但前提是已設定您的原則及警示。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-143">AIR capabilities are included in [Microsoft Defender for Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2), provided your policies and alerts are configured.</span></span> <span data-ttu-id="f1ae9-144">如果您想要做一些協助，請遵循 [防範威脅](protect-against-threats.md) 以設定或設定下列保護設定的指導方針：</span><span class="sxs-lookup"><span data-stu-id="f1ae9-144">If you would like some help with this, follow the guidance in [Protect against threats](protect-against-threats.md) to set up or configure the following protection settings:</span></span>

1. <span data-ttu-id="f1ae9-145">應開啟[審核記錄](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) () </span><span class="sxs-lookup"><span data-stu-id="f1ae9-145">[Audit logging](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (should be turned on)</span></span>

2. [<span data-ttu-id="f1ae9-146">反惡意程式碼原則</span><span class="sxs-lookup"><span data-stu-id="f1ae9-146">Antimalware policies</span></span>](protect-against-threats.md#part-1---anti-malware-protection)

3. [<span data-ttu-id="f1ae9-147">Antiphishing 保護</span><span class="sxs-lookup"><span data-stu-id="f1ae9-147">Antiphishing protection</span></span>](protect-against-threats.md#part-2---anti-phishing-protection)

4. <span data-ttu-id="f1ae9-148">[反垃圾郵件保護](protect-against-threats.md#part-3---anti-spam-protection)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-148">[Antispam protection](protect-against-threats.md#part-3---anti-spam-protection).</span></span>

5. <span data-ttu-id="f1ae9-149">[安全連結和安全附件](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-149">[Safe Links and Safe Attachments](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).</span></span>

6. <span data-ttu-id="f1ae9-150">[SharePoint、OneDrive 和 Microsoft 小組的安全附件](protect-against-threats.md#part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-150">[Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](protect-against-threats.md#part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).</span></span>

7. <span data-ttu-id="f1ae9-151">[電子郵件的零小時自動清除](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-151">[Zero-hour auto purge for email](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop).</span></span>

<span data-ttu-id="f1ae9-152">此外，請務必 [檢查您組織的警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)，尤其是「 [威脅管理」類別中的預設原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-152">In addition, make sure to [review your organization's alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), especially the [default policies in the Threat management category](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies).</span></span>

## <a name="which-alert-policies-trigger-automated-investigations"></a><span data-ttu-id="f1ae9-153">哪些警示原則會觸發自動調查？</span><span class="sxs-lookup"><span data-stu-id="f1ae9-153">Which alert policies trigger automated investigations?</span></span>

<span data-ttu-id="f1ae9-154">Microsoft 365 提供許多內建的警示原則，可協助識別 Exchange 系統管理員許可權濫用、惡意程式碼活動、潛在的外部和內部威脅，以及資訊控管風險。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-154">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="f1ae9-155">某些預設的 [報警原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 可以觸發自動調查。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-155">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="f1ae9-156">下表說明觸發自動調查的警示、在 Microsoft 365 安全性中心的嚴重性，以及產生的方式：</span><span class="sxs-lookup"><span data-stu-id="f1ae9-156">The following table describes the alerts that trigger automated investigations, their severity in the Microsoft 365 security center, and how they're generated:</span></span>

|<span data-ttu-id="f1ae9-157">警報</span><span class="sxs-lookup"><span data-stu-id="f1ae9-157">Alert</span></span>|<span data-ttu-id="f1ae9-158">嚴重性</span><span class="sxs-lookup"><span data-stu-id="f1ae9-158">Severity</span></span>|<span data-ttu-id="f1ae9-159">警示的產生方式</span><span class="sxs-lookup"><span data-stu-id="f1ae9-159">How the alert is generated</span></span>|
|---|---|---|
|<span data-ttu-id="f1ae9-160">偵測到可能的惡意 URL 按一下</span><span class="sxs-lookup"><span data-stu-id="f1ae9-160">A potentially malicious URL click was detected</span></span>|<span data-ttu-id="f1ae9-161">**High**</span><span class="sxs-lookup"><span data-stu-id="f1ae9-161">**High**</span></span>|<span data-ttu-id="f1ae9-162">發生下列任何情況時，就會產生此警示：</span><span class="sxs-lookup"><span data-stu-id="f1ae9-162">This alert is generated when any of the following occurs:</span></span> <ul><li><span data-ttu-id="f1ae9-163">由組織中 [安全連結](atp-safe-links.md) 所保護的使用者按一下惡意連結</span><span class="sxs-lookup"><span data-stu-id="f1ae9-163">A user protected by [Safe Links](atp-safe-links.md) in your organization clicks a malicious link</span></span></li><li><span data-ttu-id="f1ae9-164">URLs 的判定變更是由 Microsoft Defender for Office 365 所識別</span><span class="sxs-lookup"><span data-stu-id="f1ae9-164">Verdict changes for URLs are identified by Microsoft Defender for Office 365</span></span></li><li><span data-ttu-id="f1ae9-165">根據組織的 [安全連結原則](set-up-atp-safe-links-policies.md)) ，使用者會覆寫安全連結警告頁面 (。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-165">Users override Safe Links warning pages (based on your organization's [Safe Links policy](set-up-atp-safe-links-policies.md)).</span></span></li></ul> <p> <span data-ttu-id="f1ae9-166">如需觸發此警示之事件的詳細資訊，請參閱 [設定安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-166">For more information on events that trigger this alert, see [Set up Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>|
|<span data-ttu-id="f1ae9-167">使用者報告電子郵件訊息為惡意程式碼或網路釣魚網路</span><span class="sxs-lookup"><span data-stu-id="f1ae9-167">An email message is reported by a user as malware or phish</span></span>|<span data-ttu-id="f1ae9-168">**資訊**</span><span class="sxs-lookup"><span data-stu-id="f1ae9-168">**Informational**</span></span>|<span data-ttu-id="f1ae9-169">當您組織中的使用者使用 [報告訊息增益集將](enable-the-report-message-add-in.md)郵件報告為網路釣魚電子郵件時，就會產生此警示。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-169">This alert is generated when users in your organization report messages as phishing email using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>|
|<span data-ttu-id="f1ae9-170">傳遞後移除包含惡意程式碼的電子郵件</span><span class="sxs-lookup"><span data-stu-id="f1ae9-170">Email messages containing malware are removed after delivery</span></span>|<span data-ttu-id="f1ae9-171">**資訊**</span><span class="sxs-lookup"><span data-stu-id="f1ae9-171">**Informational**</span></span>|<span data-ttu-id="f1ae9-172">當包含惡意程式碼的電子郵件訊息傳送至組織中的信箱時，就會產生此警示。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-172">This alert is generated when any email messages containing malware are delivered to mailboxes in your organization.</span></span> <span data-ttu-id="f1ae9-173">如果發生此事件，Microsoft 會使用 [零小時自動清除](zero-hour-auto-purge.md)，從 Exchange Online 信箱移除染毒郵件。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-173">If this event occurs, Microsoft removes the infected messages from Exchange Online mailboxes using [Zero-hour auto purge](zero-hour-auto-purge.md).</span></span>|
|<span data-ttu-id="f1ae9-174">傳遞後移除包含網路釣魚 URLs 的電子郵件</span><span class="sxs-lookup"><span data-stu-id="f1ae9-174">Email messages containing phish URLs are removed after delivery</span></span>|<span data-ttu-id="f1ae9-175">**資訊**</span><span class="sxs-lookup"><span data-stu-id="f1ae9-175">**Informational**</span></span>|<span data-ttu-id="f1ae9-176">當包含網路釣魚的任何郵件傳送至您組織中的信箱時，就會產生此警示。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-176">This alert is generated when any messages containing phish are delivered to mailboxes in your organization.</span></span> <span data-ttu-id="f1ae9-177">如果發生此事件，Microsoft 會使用 [零小時自動清除](zero-hour-auto-purge.md)，從 Exchange Online 信箱移除染毒郵件。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-177">If this event occurs, Microsoft removes the infected messages from Exchange Online mailboxes using [Zero-hour auto purge](zero-hour-auto-purge.md).</span></span>|
|<span data-ttu-id="f1ae9-178">偵測到可疑的電子郵件寄送模式</span><span class="sxs-lookup"><span data-stu-id="f1ae9-178">Suspicious email sending patterns are detected</span></span>|<span data-ttu-id="f1ae9-179">**Medium**</span><span class="sxs-lookup"><span data-stu-id="f1ae9-179">**Medium**</span></span>|<span data-ttu-id="f1ae9-180">當貴組織中的某人傳送了可疑的電子郵件，並有限制傳送電子郵件的風險時，就會產生此警示。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-180">This alert is generated when someone in your organization has sent suspicious email and is at risk of being restricted from sending email.</span></span> <span data-ttu-id="f1ae9-181">這是一種針對可能表示帳戶已受損，但不足以限制使用者之行為的早期警告。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-181">This is an early warning for behavior that might indicate that the account is compromised, but not severe enough to restrict the user.</span></span> <p> <span data-ttu-id="f1ae9-182">雖然這種情況很少見，但由此原則產生的警示可能是反常的。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-182">Although it's rare, an alert generated by this policy may be an anomaly.</span></span> <span data-ttu-id="f1ae9-183">不過，最好 [檢查使用者帳戶是否受損](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-183">However, it's a good idea to [check whether the user account is compromised](responding-to-a-compromised-email-account.md).</span></span>|
|<span data-ttu-id="f1ae9-184">限制使用者傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="f1ae9-184">A user is restricted from sending email</span></span>|<span data-ttu-id="f1ae9-185">**High**</span><span class="sxs-lookup"><span data-stu-id="f1ae9-185">**High**</span></span>|<span data-ttu-id="f1ae9-186">當您組織中的人員限制傳送輸出郵件時，就會產生此警示。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-186">This alert is generated when someone in your organization is restricted from sending outbound mail.</span></span> <span data-ttu-id="f1ae9-187">這通常 [是在電子郵件帳戶遭到破壞](responding-to-a-compromised-email-account.md)時產生的結果。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-187">This typically results when an [email account is compromised](responding-to-a-compromised-email-account.md).</span></span> <p> <span data-ttu-id="f1ae9-188">如需有關限制使用者的詳細資訊，請參閱 [從 Microsoft 365 中的受限使用者入口網站移除封鎖的使用者](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-188">For more information about restricted users, see [Remove blocked users from the Restricted Users portal in Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md).</span></span>|
|

> [!TIP]
> <span data-ttu-id="f1ae9-189">若要深入瞭解報警原則或編輯預設設定，請參閱 [Microsoft 365 規範中心的警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-189">To learn more about alert policies or edit the default settings, see [Alert policies in the Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="f1ae9-190">使用 AIR 功能所需的許可權</span><span class="sxs-lookup"><span data-stu-id="f1ae9-190">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="f1ae9-191">許可權是透過特定角色授與的，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="f1ae9-191">Permissions are granted through certain roles, such as those that are described in the following table:</span></span>

|<span data-ttu-id="f1ae9-192">工作</span><span class="sxs-lookup"><span data-stu-id="f1ae9-192">Task</span></span>|<span data-ttu-id="f1ae9-193">需要) 角色 (</span><span class="sxs-lookup"><span data-stu-id="f1ae9-193">Role(s) required</span></span>|
|---|---|
|<span data-ttu-id="f1ae9-194">設定 AIR 功能</span><span class="sxs-lookup"><span data-stu-id="f1ae9-194">Set up AIR features</span></span>|<span data-ttu-id="f1ae9-195">下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="f1ae9-195">One of the following roles:</span></span> <ul><li><span data-ttu-id="f1ae9-196">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="f1ae9-196">Global Administrator</span></span></li><li><span data-ttu-id="f1ae9-197">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="f1ae9-197">Security Administrator</span></span></li></ul> <p> <span data-ttu-id="f1ae9-198">您可以在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合規性中心](permissions-in-the-security-and-compliance-center.md)指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-198">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>|
|<span data-ttu-id="f1ae9-199">開始自動調查</span><span class="sxs-lookup"><span data-stu-id="f1ae9-199">Start an automated investigation</span></span> <p> <span data-ttu-id="f1ae9-200">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="f1ae9-200">--- or ---</span></span> <p> <span data-ttu-id="f1ae9-201">核准或拒絕建議的動作</span><span class="sxs-lookup"><span data-stu-id="f1ae9-201">Approve or reject recommended actions</span></span>|<span data-ttu-id="f1ae9-202">在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合規性中心](permissions-in-the-security-and-compliance-center.md)內指派的下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="f1ae9-202">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md):</span></span> <ul><li><span data-ttu-id="f1ae9-203">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="f1ae9-203">Global Administrator</span></span></li><li><span data-ttu-id="f1ae9-204">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="f1ae9-204">Security Administrator</span></span></li><li><span data-ttu-id="f1ae9-205">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="f1ae9-205">Security Reader</span></span> <br> <span data-ttu-id="f1ae9-206">--- 且 ---</span><span class="sxs-lookup"><span data-stu-id="f1ae9-206">--- and ---</span></span> </li><li><span data-ttu-id="f1ae9-207">搜尋和清除 (此角色只會指派在 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-207">Search and Purge (this role is assigned only in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="f1ae9-208">您可能需要建立新的角色群組，並將搜尋和清除角色新增至該新的角色群組。</span><span class="sxs-lookup"><span data-stu-id="f1ae9-208">You might have to create a new role group there and add the Search and Purge role to that new role group.</span></span></li></ul>|
|

## <a name="required-licenses"></a><span data-ttu-id="f1ae9-209">必要的授權</span><span class="sxs-lookup"><span data-stu-id="f1ae9-209">Required licenses</span></span>

<span data-ttu-id="f1ae9-210">[Microsoft Defender For Office 365 方案 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 授權應指派給：</span><span class="sxs-lookup"><span data-stu-id="f1ae9-210">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) licenses should be assigned to:</span></span>

- <span data-ttu-id="f1ae9-211">安全性管理員 (包括全域管理員) </span><span class="sxs-lookup"><span data-stu-id="f1ae9-211">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="f1ae9-212">組織的安全性運作小組 (包括安全性讀者和具有 **搜尋和清除** 角色的使用者) </span><span class="sxs-lookup"><span data-stu-id="f1ae9-212">Your organization's security operations team (including security readers and those with the **Search and Purge** role)</span></span>
- <span data-ttu-id="f1ae9-213">終端使用者</span><span class="sxs-lookup"><span data-stu-id="f1ae9-213">End users</span></span>

## <a name="next-steps"></a><span data-ttu-id="f1ae9-214">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f1ae9-214">Next steps</span></span>

- [<span data-ttu-id="f1ae9-215">查看自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="f1ae9-215">See details and results of an automated investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="f1ae9-216">審閱及核准擱置的動作</span><span class="sxs-lookup"><span data-stu-id="f1ae9-216">Review and approve pending actions</span></span>](air-remediation-actions.md)

## <a name="see-also"></a><span data-ttu-id="f1ae9-217">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f1ae9-217">See also</span></span>

- [<span data-ttu-id="f1ae9-218">Microsoft Defender for Endpoint 中的自動調查和修正</span><span class="sxs-lookup"><span data-stu-id="f1ae9-218">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="f1ae9-219">Microsoft 365 Defender 的自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="f1ae9-219">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
