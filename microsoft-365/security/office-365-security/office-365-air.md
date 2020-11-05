---
title: 開始使用 Microsoft Defender for Office 365 中的自動調查和回應
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/04/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 開始使用 Microsoft Defender for Office 365 中的自動調查和回應功能。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 7e9b786a9d00a34f5e2e88a8481e82fa8425a501
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925601"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4cdf3-104">開始使用 Microsoft Defender for Office 365 中的自動調查和回應 (AIR) </span><span class="sxs-lookup"><span data-stu-id="4cdf3-104">Get started using automated investigation and response (AIR) in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4cdf3-105">[Microsoft Defender For Office 365](office-365-atp.md) 包含強大的自動化調查和回應 (空氣) 功能，可節約您的安全性運作小組時間和工作。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-105">[Microsoft Defender for Office 365](office-365-atp.md) includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="4cdf3-106">當觸發警示時，您的安全性作業小組會檢查、優先順序及回應這些警示。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="4cdf3-107">保持傳入提醒的數量非常驚人。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="4cdf3-108">自動化某些工作可以協助。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-108">Automating some of those tasks can help.</span></span> <span data-ttu-id="4cdf3-109">透過 AIR，您的安全性運作小組可以著重于優先順序較高的工作，而不會失去所觸發之重要警示的視線。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of important alerts that are triggered.</span></span>

<span data-ttu-id="4cdf3-110">本文說明：</span><span class="sxs-lookup"><span data-stu-id="4cdf3-110">This article describes:</span></span>
- <span data-ttu-id="4cdf3-111">[空氣的整體流向](#the-overall-flow-of-air);</span><span class="sxs-lookup"><span data-stu-id="4cdf3-111">The [overall flow of AIR](#the-overall-flow-of-air);</span></span>
- <span data-ttu-id="4cdf3-112">[如何取得空氣](#how-to-get-air);和</span><span class="sxs-lookup"><span data-stu-id="4cdf3-112">[How to get AIR](#how-to-get-air); and</span></span> 
- <span data-ttu-id="4cdf3-113">設定或使用 AIR 功能 [所需的許可權](#required-permissions-to-use-air-capabilities) 。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-113">The [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span> 

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="4cdf3-114">空氣的整體流動</span><span class="sxs-lookup"><span data-stu-id="4cdf3-114">The overall flow of AIR</span></span>

<span data-ttu-id="4cdf3-115">會觸發警示，安全性行動手冊會開始進行自動調查，進而會產生結果和建議的動作。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-115">An alert is triggered, and a security playbook starts an automated investigation, which results in findings and recommended actions.</span></span> <span data-ttu-id="4cdf3-116">以下是空氣的整體流動流程，逐步執行：</span><span class="sxs-lookup"><span data-stu-id="4cdf3-116">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="4cdf3-117">自動調查是以下列其中一種方式啟動：</span><span class="sxs-lookup"><span data-stu-id="4cdf3-117">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="4cdf3-118">在電子郵件 (例如郵件、附件或 URL) 等電子郵件的可疑專案中，會觸發 [警示](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) 。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-118">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by something suspicious in email (such as a message, attachment, or URL).</span></span> <span data-ttu-id="4cdf3-119">建立事件。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-119">An incident is created.</span></span> <span data-ttu-id="4cdf3-120">根據事件的類型而定， [安全性行動手冊](automated-investigation-response-office.md#security-playbooks) 會執行，並且自動調查開始。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-120">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) runs, and an automated investigation begins.</span></span> 

     <span data-ttu-id="4cdf3-121">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="4cdf3-121">--- or ---</span></span>
   
   - <span data-ttu-id="4cdf3-122">安全分析員會在使用[威脅瀏覽器](threat-explorer.md)時[開始自動調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-122">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="4cdf3-123">當自動調查執行時，它會收集有關電子郵件的其他資料，以及與該電子郵件相關的實體。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-123">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="4cdf3-124">這類實體可以包含檔案、URLs 及收件者。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-124">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="4cdf3-125">調查的範圍會隨著新的和相關的提醒觸發而增加。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-125">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="4cdf3-126">在自動調查的期間和之後，都可以查看 [詳細資料和結果](air-view-investigation-results.md) 。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-126">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="4cdf3-127">結果包括可以採取的 [建議動作](air-remediation-actions.md) ，以回應及修正找到的任何威脅。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-127">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond to and remediate any threats that were found.</span></span> <span data-ttu-id="4cdf3-128">此外，也可以使用 [行動手冊記錄](air-view-investigation-results.md#playbook-log) 來追蹤所有調查活動。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-128">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>


4. <span data-ttu-id="4cdf3-129">您的安全性運作小組會檢查 [調查結果和建議](air-view-investigation-results.md)，並 [批准或拒絕修正動作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-129">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span> 

5. <span data-ttu-id="4cdf3-130">當擱置的修復動作獲批准 (或拒絕) 時，自動調查即完成。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-130">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4cdf3-131">在適用于 Office 365 的 Microsoft Defender 中，不會自動採取任何修正動作。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-131">In Microsoft Defender for Office 365, no remediation actions are taken automatically.</span></span> <span data-ttu-id="4cdf3-132">在組織的安全性小組核准後才能採取補救動作。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-132">Remediation actions are taken only upon approval by your organization's security team.</span></span> <span data-ttu-id="4cdf3-133">不過，AIR 功能會透過識別修正動作來儲存您的安全性運作小組時間，並提供做出明智決定所需的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-133">However, AIR capabilities save your security operations team time by identifying remediation actions and providing the details needed to make an informed decision.</span></span>

<span data-ttu-id="4cdf3-134">在每次自動調查期間和之後，您的安全性作業小組可以：</span><span class="sxs-lookup"><span data-stu-id="4cdf3-134">During and after each automated investigation, your security operations team can:</span></span>

- [<span data-ttu-id="4cdf3-135">檢視與調查相關警示的詳細資料</span><span class="sxs-lookup"><span data-stu-id="4cdf3-135">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="4cdf3-136">查看調查的結果詳細資料</span><span class="sxs-lookup"><span data-stu-id="4cdf3-136">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="4cdf3-137">根據調查的結果檢閱和核准動作</span><span class="sxs-lookup"><span data-stu-id="4cdf3-137">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="4cdf3-138">如需詳細資訊，請參閱 [AIR 的運作方式](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-138">For a more detailed overview, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="4cdf3-139">如何取得空中</span><span class="sxs-lookup"><span data-stu-id="4cdf3-139">How to get AIR</span></span>

<span data-ttu-id="4cdf3-140">AIR 功能包含在 [適用于 Office 365 的 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)中，但前提是已設定您的原則及警示。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-140">AIR capabilities are included in [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2), provided your policies and alerts are configured.</span></span> <span data-ttu-id="4cdf3-141">如果您想要做一些協助，請遵循 [防範威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) 以設定或設定下列保護設定的指導方針：</span><span class="sxs-lookup"><span data-stu-id="4cdf3-141">If you would like some help with this, follow the guidance in [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) to set up or configure the following protection settings:</span></span> 

1. <span data-ttu-id="4cdf3-142">應開啟[審核記錄](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) () </span><span class="sxs-lookup"><span data-stu-id="4cdf3-142">[Audit logging](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (should be turned on)</span></span>

2. [<span data-ttu-id="4cdf3-143">反惡意程式碼原則</span><span class="sxs-lookup"><span data-stu-id="4cdf3-143">Antimalware policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-1---anti-malware-protection)

3. [<span data-ttu-id="4cdf3-144">Antiphishing 保護</span><span class="sxs-lookup"><span data-stu-id="4cdf3-144">Antiphishing protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
   
4. <span data-ttu-id="4cdf3-145">[反垃圾郵件保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection)。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-145">[Antispam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection).</span></span>
   
5. <span data-ttu-id="4cdf3-146">[安全連結和安全附件](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-146">[Safe Links and Safe Attachments](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).</span></span>
   
6. <span data-ttu-id="4cdf3-147">[SharePoint、OneDrive 和 Microsoft 小組的安全附件](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-147">[Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).</span></span>
   
7. <span data-ttu-id="4cdf3-148">[電子郵件的零小時自動清除](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop)。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-148">[Zero-hour auto purge for email](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop).</span></span>

<span data-ttu-id="4cdf3-149">此外，請務必 [檢查您組織的警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)，尤其是「 [威脅管理」類別中的預設原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-149">In addition, make sure to [review your organization's alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), especially the [default policies in the Threat management category](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies).</span></span> 

## <a name="which-alert-policies-trigger-automated-investigations"></a><span data-ttu-id="4cdf3-150">哪些警示原則會觸發自動調查？</span><span class="sxs-lookup"><span data-stu-id="4cdf3-150">Which alert policies trigger automated investigations?</span></span>

<span data-ttu-id="4cdf3-151">Microsoft 365 提供許多內建的警示原則，可協助識別 Exchange 系統管理員許可權濫用、惡意程式碼活動、潛在的外部和內部威脅，以及資訊控管風險。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-151">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="4cdf3-152">某些預設的 [報警原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 可以觸發自動調查。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-152">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="4cdf3-153">包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="4cdf3-153">These include the following:</span></span>

- <span data-ttu-id="4cdf3-154">偵測到可能的惡意 URL 按一下</span><span class="sxs-lookup"><span data-stu-id="4cdf3-154">A potentially malicious URL click is detected</span></span>
- <span data-ttu-id="4cdf3-155">使用者將電子郵件訊息當做網路釣魚詐騙進行報告</span><span class="sxs-lookup"><span data-stu-id="4cdf3-155">An email message is reported by a user as phish</span></span>
- <span data-ttu-id="4cdf3-156">傳遞後移除包含惡意程式碼的電子郵件</span><span class="sxs-lookup"><span data-stu-id="4cdf3-156">Email messages containing malware are removed after delivery</span></span>
- <span data-ttu-id="4cdf3-157">傳遞後移除包含網路釣魚 URLs 的電子郵件</span><span class="sxs-lookup"><span data-stu-id="4cdf3-157">Email messages containing phish URLs are removed after delivery</span></span>
- <span data-ttu-id="4cdf3-158">偵測到可疑的電子郵件寄送模式</span><span class="sxs-lookup"><span data-stu-id="4cdf3-158">Suspicious email sending patterns are detected</span></span>
- <span data-ttu-id="4cdf3-159">限制使用者傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="4cdf3-159">A user is restricted from sending email</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="4cdf3-160">使用 AIR 功能所需的許可權</span><span class="sxs-lookup"><span data-stu-id="4cdf3-160">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="4cdf3-161">許可權是透過特定角色授與的，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="4cdf3-161">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="4cdf3-162">工作</span><span class="sxs-lookup"><span data-stu-id="4cdf3-162">Task</span></span> |<span data-ttu-id="4cdf3-163">需要) 角色 (</span><span class="sxs-lookup"><span data-stu-id="4cdf3-163">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="4cdf3-164">設定 AIR 功能</span><span class="sxs-lookup"><span data-stu-id="4cdf3-164">To set up AIR features</span></span> |<span data-ttu-id="4cdf3-165">下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="4cdf3-165">One of the following roles:</span></span> <br/><span data-ttu-id="4cdf3-166">-全域管理員</span><span class="sxs-lookup"><span data-stu-id="4cdf3-166">- Global Administrator</span></span><br/><span data-ttu-id="4cdf3-167">-安全性管理員</span><span class="sxs-lookup"><span data-stu-id="4cdf3-167">- Security Administrator</span></span> <br/><span data-ttu-id="4cdf3-168">您可以在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-168">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="4cdf3-169">核准或拒絕建議的動作</span><span class="sxs-lookup"><span data-stu-id="4cdf3-169">To approve or reject recommended actions</span></span>|<span data-ttu-id="4cdf3-170">在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) 內指派的下列其中一個角色) ：</span><span class="sxs-lookup"><span data-stu-id="4cdf3-170">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="4cdf3-171">-全域管理員</span><span class="sxs-lookup"><span data-stu-id="4cdf3-171">- Global Administrator</span></span> <br/><span data-ttu-id="4cdf3-172">-安全性管理員</span><span class="sxs-lookup"><span data-stu-id="4cdf3-172">- Security Administrator</span></span><br/><span data-ttu-id="4cdf3-173">-安全性讀取器</span><span class="sxs-lookup"><span data-stu-id="4cdf3-173">- Security Reader</span></span> <br/><span data-ttu-id="4cdf3-174">--- 且 ---</span><span class="sxs-lookup"><span data-stu-id="4cdf3-174">--- and ---</span></span><br/><span data-ttu-id="4cdf3-175">-搜尋和清除 (此角色只會指派在 [安全性 & 規範中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="4cdf3-175">- Search and Purge (this role is assigned only in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="4cdf3-176">您可能需要建立新的角色群組，並將搜尋和清除角色新增至該新的角色群組。 ) </span><span class="sxs-lookup"><span data-stu-id="4cdf3-176">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

## <a name="required-licenses"></a><span data-ttu-id="4cdf3-177">必要的授權</span><span class="sxs-lookup"><span data-stu-id="4cdf3-177">Required licenses</span></span>

<span data-ttu-id="4cdf3-178">若要將[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)授權指派給：</span><span class="sxs-lookup"><span data-stu-id="4cdf3-178">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) licenses should be assigned to:</span></span>
- <span data-ttu-id="4cdf3-179">安全性管理員 (包括全域管理員) </span><span class="sxs-lookup"><span data-stu-id="4cdf3-179">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="4cdf3-180">組織的安全性運作小組 (包括安全性讀者和具有搜尋和清除角色的使用者) </span><span class="sxs-lookup"><span data-stu-id="4cdf3-180">Your organization's security operations team (including security readers and those with the Search and Purge role)</span></span>
- <span data-ttu-id="4cdf3-181">使用者</span><span class="sxs-lookup"><span data-stu-id="4cdf3-181">End users</span></span>


## <a name="next-steps"></a><span data-ttu-id="4cdf3-182">後續步驟</span><span class="sxs-lookup"><span data-stu-id="4cdf3-182">Next steps</span></span>

- [<span data-ttu-id="4cdf3-183">查看自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="4cdf3-183">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="4cdf3-184">審閱及核准擱置的動作</span><span class="sxs-lookup"><span data-stu-id="4cdf3-184">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="4cdf3-185">相關文章</span><span class="sxs-lookup"><span data-stu-id="4cdf3-185">Related articles</span></span>

- [<span data-ttu-id="4cdf3-186">Microsoft Defender for Endpoint 中的自動調查和修正</span><span class="sxs-lookup"><span data-stu-id="4cdf3-186">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="4cdf3-187">Microsoft 365 Defender 的自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="4cdf3-187">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
