---
title: 自動調查和回應 (AIR) -快速入門
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 09/29/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 開始使用 Microsoft Defender for Office 365 中的自動調查和回應功能。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: b844e4817bc77d7f6f4e99df53fc4b14c7e7110c
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308884"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a><span data-ttu-id="49ef7-104">開始使用 Office 365 中的自動調查和回應 (AIR) </span><span class="sxs-lookup"><span data-stu-id="49ef7-104">Get started using automated investigation and response (AIR) in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="49ef7-105">[Microsoft Defender For Office 365](office-365-atp.md) 包含強大的自動化調查和回應 (空氣) 功能，可節約您的安全性運作小組時間和工作。</span><span class="sxs-lookup"><span data-stu-id="49ef7-105">[Microsoft Defender for Office 365](office-365-atp.md) includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="49ef7-106">當觸發警示時，您的安全性作業小組會檢查、優先順序及回應這些警示。</span><span class="sxs-lookup"><span data-stu-id="49ef7-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="49ef7-107">保持傳入提醒的數量非常驚人。</span><span class="sxs-lookup"><span data-stu-id="49ef7-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="49ef7-108">自動化某些部分可提供協助。</span><span class="sxs-lookup"><span data-stu-id="49ef7-108">Automating some of this can help.</span></span> <span data-ttu-id="49ef7-109">透過 AIR，您的安全性運作小組可以專注于優先順序較高的工作，而不會失去所觸發之警示的視線。</span><span class="sxs-lookup"><span data-stu-id="49ef7-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of alerts that are triggered.</span></span>

<span data-ttu-id="49ef7-110">本文包括：</span><span class="sxs-lookup"><span data-stu-id="49ef7-110">This article includes:</span></span>
- <span data-ttu-id="49ef7-111">空氣的 [整體流向](#the-overall-flow-of-air) ;</span><span class="sxs-lookup"><span data-stu-id="49ef7-111">The [overall flow](#the-overall-flow-of-air) of AIR;</span></span>
- <span data-ttu-id="49ef7-112">[如何取得空氣](#how-to-get-air);和</span><span class="sxs-lookup"><span data-stu-id="49ef7-112">[How to get AIR](#how-to-get-air); and</span></span> 
- <span data-ttu-id="49ef7-113">設定或使用 AIR 功能 [所需的許可權](#required-permissions-to-use-air-capabilities) 。</span><span class="sxs-lookup"><span data-stu-id="49ef7-113">The [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span> 

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="49ef7-114">空氣的整體流動</span><span class="sxs-lookup"><span data-stu-id="49ef7-114">The overall flow of AIR</span></span>

<span data-ttu-id="49ef7-115">在高層次上會觸發警示，安全性行動手冊會開始進行自動調查，進而會產生結果和建議。</span><span class="sxs-lookup"><span data-stu-id="49ef7-115">At a high level, an alert is triggered, and a security playbook starts an automated investigation, which results in findings and recommendations.</span></span> <span data-ttu-id="49ef7-116">以下是空氣的整體流動流程，逐步執行：</span><span class="sxs-lookup"><span data-stu-id="49ef7-116">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="49ef7-117">自動調查是以下列其中一種方式啟動：</span><span class="sxs-lookup"><span data-stu-id="49ef7-117">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="49ef7-118">由 Office 事件觸發 [警示](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) ，以建立事件。</span><span class="sxs-lookup"><span data-stu-id="49ef7-118">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by an Office event, which creates an incident.</span></span> <span data-ttu-id="49ef7-119">根據事件種類而定， [安全性行動手冊](automated-investigation-response-office.md#security-playbooks) 會開始進行自動調查。</span><span class="sxs-lookup"><span data-stu-id="49ef7-119">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) starts an automated investigation.</span></span> 

     <span data-ttu-id="49ef7-120">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="49ef7-120">--- or ---</span></span>
   
   - <span data-ttu-id="49ef7-121">安全分析員會在使用[威脅瀏覽器](threat-explorer.md)時[開始自動調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="49ef7-121">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="49ef7-122">當自動調查執行時，它會收集有關電子郵件的其他資料，以及與該電子郵件相關的實體。</span><span class="sxs-lookup"><span data-stu-id="49ef7-122">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="49ef7-123">這類實體可以包含檔案、URLs 及收件者。</span><span class="sxs-lookup"><span data-stu-id="49ef7-123">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="49ef7-124">調查的範圍會隨著新的和相關的提醒觸發而增加。</span><span class="sxs-lookup"><span data-stu-id="49ef7-124">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="49ef7-125">在自動調查的期間和之後，都可以查看 [詳細資料和結果](air-view-investigation-results.md) 。</span><span class="sxs-lookup"><span data-stu-id="49ef7-125">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="49ef7-126">結果包括可以採取以回應和修正任何找到之威脅的 [建議動作](air-remediation-actions.md) 。</span><span class="sxs-lookup"><span data-stu-id="49ef7-126">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="49ef7-127">此外，也可以使用 [行動手冊記錄](air-view-investigation-results.md#playbook-log) 來追蹤所有調查活動。</span><span class="sxs-lookup"><span data-stu-id="49ef7-127">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>

    <span data-ttu-id="49ef7-128">如果您的組織使用自訂報告解決方案或協力廠商解決方案，您可以 [使用 Office 365 管理活動 API](air-custom-reporting.md) 來查看有關自動化調查和威脅的資訊。</span><span class="sxs-lookup"><span data-stu-id="49ef7-128">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](air-custom-reporting.md) to view information about automated investigations and threats.</span></span>

4. <span data-ttu-id="49ef7-129">您的安全性運作小組會檢查 [調查結果和建議](air-view-investigation-results.md)，並 [批准或拒絕修正動作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="49ef7-129">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span> 

    <span data-ttu-id="49ef7-130">當擱置的修復動作獲批准 (或拒絕) 時，自動調查即完成。</span><span class="sxs-lookup"><span data-stu-id="49ef7-130">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="49ef7-131">在 Office 365 ATP 中，不會自動採取任何修正動作。</span><span class="sxs-lookup"><span data-stu-id="49ef7-131">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="49ef7-132">在組織的安全性小組核准後才能採取補救動作。</span><span class="sxs-lookup"><span data-stu-id="49ef7-132">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

<span data-ttu-id="49ef7-133">在自動化調查程序期間及之後，您的安全性小組可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="49ef7-133">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="49ef7-134">檢視與調查相關警示的詳細資料</span><span class="sxs-lookup"><span data-stu-id="49ef7-134">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="49ef7-135">查看調查的結果詳細資料</span><span class="sxs-lookup"><span data-stu-id="49ef7-135">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="49ef7-136">根據調查的結果檢閱和核准動作</span><span class="sxs-lookup"><span data-stu-id="49ef7-136">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="49ef7-137">如需詳細資訊，請參閱 [AIR 的運作方式](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。</span><span class="sxs-lookup"><span data-stu-id="49ef7-137">For more details, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="49ef7-138">如何取得空中</span><span class="sxs-lookup"><span data-stu-id="49ef7-138">How to get AIR</span></span>

<span data-ttu-id="49ef7-139">AIR 功能包含在 [適用于 Office 365 的 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)中。</span><span class="sxs-lookup"><span data-stu-id="49ef7-139">AIR capabilities are included in [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2).</span></span> <span data-ttu-id="49ef7-140">不過，您 [必須設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) 您的原則，AIR 才能如期運作。</span><span class="sxs-lookup"><span data-stu-id="49ef7-140">However, your [policies must be configured](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) in order for AIR to work as expected.</span></span> <span data-ttu-id="49ef7-141">此外，請務必複查並可能設定組織的 [警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)。</span><span class="sxs-lookup"><span data-stu-id="49ef7-141">In addition, make sure to review and potentially configure your organization's [alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span> 

<span data-ttu-id="49ef7-142">Microsoft 365 提供許多內建的警示原則，可協助識別 Exchange 系統管理員許可權濫用、惡意程式碼活動、潛在的外部和內部威脅，以及資訊控管風險。</span><span class="sxs-lookup"><span data-stu-id="49ef7-142">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="49ef7-143">某些預設的 [報警原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 可以觸發自動調查。</span><span class="sxs-lookup"><span data-stu-id="49ef7-143">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="49ef7-144">包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="49ef7-144">These include the following:</span></span>

- <span data-ttu-id="49ef7-145">偵測到可能的惡意 URL 按一下</span><span class="sxs-lookup"><span data-stu-id="49ef7-145">A potentially malicious URL click is detected</span></span>

- <span data-ttu-id="49ef7-146">使用者將電子郵件訊息當做網路釣魚詐騙進行報告</span><span class="sxs-lookup"><span data-stu-id="49ef7-146">An email message is reported by a user as phish</span></span>

- <span data-ttu-id="49ef7-147">傳遞後移除包含惡意程式碼的電子郵件</span><span class="sxs-lookup"><span data-stu-id="49ef7-147">Email messages containing malware are removed after delivery</span></span>

- <span data-ttu-id="49ef7-148">傳遞後移除包含網路釣魚 URLs 的電子郵件</span><span class="sxs-lookup"><span data-stu-id="49ef7-148">Email messages containing phish URLs are removed after delivery</span></span>

- <span data-ttu-id="49ef7-149">偵測到可疑的電子郵件寄送模式</span><span class="sxs-lookup"><span data-stu-id="49ef7-149">Suspicious email sending patterns are detected</span></span>

- <span data-ttu-id="49ef7-150">限制使用者傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="49ef7-150">A user is restricted from sending email</span></span>

<span data-ttu-id="49ef7-151">[深入瞭解警示和空中](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。</span><span class="sxs-lookup"><span data-stu-id="49ef7-151">[Learn more about alerts and AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="49ef7-152">使用 AIR 功能所需的許可權</span><span class="sxs-lookup"><span data-stu-id="49ef7-152">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="49ef7-153">許可權是透過特定角色授與的，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="49ef7-153">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="49ef7-154">工作</span><span class="sxs-lookup"><span data-stu-id="49ef7-154">Task</span></span> |<span data-ttu-id="49ef7-155">需要) 角色 (</span><span class="sxs-lookup"><span data-stu-id="49ef7-155">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="49ef7-156">設定 AIR 功能</span><span class="sxs-lookup"><span data-stu-id="49ef7-156">To set up AIR features</span></span> |<span data-ttu-id="49ef7-157">下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="49ef7-157">One of the following roles:</span></span> <br/><span data-ttu-id="49ef7-158">-全域管理員</span><span class="sxs-lookup"><span data-stu-id="49ef7-158">- Global Administrator</span></span><br/><span data-ttu-id="49ef7-159">-安全性管理員</span><span class="sxs-lookup"><span data-stu-id="49ef7-159">- Security Administrator</span></span> <br/><span data-ttu-id="49ef7-160">您可以在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="49ef7-160">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="49ef7-161">核准或拒絕建議的動作</span><span class="sxs-lookup"><span data-stu-id="49ef7-161">To approve or reject recommended actions</span></span>|<span data-ttu-id="49ef7-162">在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) 內指派的下列其中一個角色) ：</span><span class="sxs-lookup"><span data-stu-id="49ef7-162">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="49ef7-163">-全域管理員</span><span class="sxs-lookup"><span data-stu-id="49ef7-163">- Global Administrator</span></span> <br/><span data-ttu-id="49ef7-164">-安全性管理員</span><span class="sxs-lookup"><span data-stu-id="49ef7-164">- Security Administrator</span></span><br/><span data-ttu-id="49ef7-165">-安全性讀取器</span><span class="sxs-lookup"><span data-stu-id="49ef7-165">- Security Reader</span></span> <br/><span data-ttu-id="49ef7-166">--- 且 ---</span><span class="sxs-lookup"><span data-stu-id="49ef7-166">--- and ---</span></span><br/><span data-ttu-id="49ef7-167">-搜尋和清除 (此角色只會指派在 [安全性 & 規範中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="49ef7-167">- Search and Purge (this role is assigned only in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="49ef7-168">您可能需要建立新的角色群組，並將搜尋和清除角色新增至該新的角色群組。 ) </span><span class="sxs-lookup"><span data-stu-id="49ef7-168">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

<span data-ttu-id="49ef7-169">若要將[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)授權指派給：</span><span class="sxs-lookup"><span data-stu-id="49ef7-169">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) licenses should be assigned to:</span></span>
- <span data-ttu-id="49ef7-170">安全性管理員 (包括全域管理員) </span><span class="sxs-lookup"><span data-stu-id="49ef7-170">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="49ef7-171">組織的安全性運作小組 (包括安全性讀者和具有搜尋和清除角色的使用者) </span><span class="sxs-lookup"><span data-stu-id="49ef7-171">Your organization's security operations team (including security readers and those with the Search and Purge role)</span></span>
- <span data-ttu-id="49ef7-172">終端使用者</span><span class="sxs-lookup"><span data-stu-id="49ef7-172">End users</span></span>

<span data-ttu-id="49ef7-173">此外，必須定義及套用 [Microsoft Defender For Office 365 原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) ，才能進行保護。</span><span class="sxs-lookup"><span data-stu-id="49ef7-173">In addition, [Microsoft Defender for Office 365 policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) must be defined and applied in order for protection to be in place.</span></span>

## <a name="next-steps"></a><span data-ttu-id="49ef7-174">後續步驟</span><span class="sxs-lookup"><span data-stu-id="49ef7-174">Next steps</span></span>

- [<span data-ttu-id="49ef7-175">查看自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="49ef7-175">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="49ef7-176">審閱及核准擱置的動作</span><span class="sxs-lookup"><span data-stu-id="49ef7-176">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="49ef7-177">相關文章</span><span class="sxs-lookup"><span data-stu-id="49ef7-177">Related articles</span></span>

- [<span data-ttu-id="49ef7-178">Microsoft Defender for Endpoint 中的自動調查和修正</span><span class="sxs-lookup"><span data-stu-id="49ef7-178">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="49ef7-179">Microsoft 365 Defender 的自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="49ef7-179">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
