---
title: 自動化調查和回應（AIR）-快速入門
keywords: AIR, autoIR, ATP, 自動化, 調查, 回應, 修正, 威脅, 進階, 威脅, 保護
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
description: 開始使用 Office 365 進階威脅防護方案 2 中的自動化調查及回應功能
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: cb65b5a7f0b12ff977c0e8bd92912b8f741a2281
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141544"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a><span data-ttu-id="90af1-104">開始使用 Office 365 中的自動調查和回應（AIR）</span><span class="sxs-lookup"><span data-stu-id="90af1-104">Get started using Automated investigation and response (AIR) in Office 365</span></span>

<span data-ttu-id="90af1-105">[Office 365 高級威脅防護](office-365-atp.md)（OFFICE 365 ATP）方案2包含強大的自動化調查和回應（空氣）功能，可儲存您的安全性運作小組時間和工作。</span><span class="sxs-lookup"><span data-stu-id="90af1-105">[Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) Plan 2 includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="90af1-106">當觸發警示時，您的安全性作業小組會檢查、優先順序及回應這些警示。</span><span class="sxs-lookup"><span data-stu-id="90af1-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="90af1-107">保持傳入提醒的數量非常驚人。</span><span class="sxs-lookup"><span data-stu-id="90af1-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="90af1-108">自動化某些部分可提供協助。</span><span class="sxs-lookup"><span data-stu-id="90af1-108">Automating some of this can help.</span></span> <span data-ttu-id="90af1-109">透過 AIR，您的安全性運作小組可以專注于優先順序較高的工作，而不會失去所觸發之警示的視線。</span><span class="sxs-lookup"><span data-stu-id="90af1-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of alerts that are triggered.</span></span>

<span data-ttu-id="90af1-110">本文說明空氣的[整體流動](#the-overall-flow-of-air)，[如何取得 air](#how-to-get-air)，以及設定或使用 AIR 功能[所需的許可權](#required-permissions-to-use-air-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="90af1-110">This article describes the [overall flow](#the-overall-flow-of-air) of AIR, [how to get AIR](#how-to-get-air), and the [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span> 

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="90af1-111">空氣的整體流動</span><span class="sxs-lookup"><span data-stu-id="90af1-111">The overall flow of AIR</span></span>

<span data-ttu-id="90af1-112">在高層次，會觸發警示，安全性行動手冊會開始和自動調查，進而會產生結果和建議。</span><span class="sxs-lookup"><span data-stu-id="90af1-112">At a high level, an alert is triggered, and a security playbook starts and automated investigation, which results in findings and recommendations.</span></span> <span data-ttu-id="90af1-113">以下是空氣的整體流動流程，逐步執行：</span><span class="sxs-lookup"><span data-stu-id="90af1-113">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="90af1-114">自動調查是以下列其中一種方式啟動：</span><span class="sxs-lookup"><span data-stu-id="90af1-114">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="90af1-115">由 Office 事件觸發[警示](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)，以建立事件。</span><span class="sxs-lookup"><span data-stu-id="90af1-115">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by an Office event, which creates an incident.</span></span> <span data-ttu-id="90af1-116">根據事件種類而定，[安全性行動手冊](automated-investigation-response-office.md#security-playbooks)會開始進行自動調查。</span><span class="sxs-lookup"><span data-stu-id="90af1-116">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) starts an automated investigation.</span></span> 

     <span data-ttu-id="90af1-117">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="90af1-117">--- or ---</span></span>
   
   - <span data-ttu-id="90af1-118">安全分析員會在使用[威脅瀏覽器](threat-explorer.md)時[開始自動調查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="90af1-118">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="90af1-119">當自動調查執行時，它會收集有關電子郵件的其他資料，以及與該電子郵件相關的實體。</span><span class="sxs-lookup"><span data-stu-id="90af1-119">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="90af1-120">這類實體可以包含檔案、URLs 及收件者。</span><span class="sxs-lookup"><span data-stu-id="90af1-120">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="90af1-121">調查的範圍會隨著新的和相關的提醒觸發而增加。</span><span class="sxs-lookup"><span data-stu-id="90af1-121">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="90af1-122">在自動調查的期間和之後，都可以查看[詳細資料和結果](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="90af1-122">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="90af1-123">結果包括可以採取以回應和修正任何找到之威脅的[建議動作](air-remediation-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="90af1-123">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="90af1-124">此外，也可以使用[行動手冊記錄](air-view-investigation-results.md#playbook-log)來追蹤所有調查活動。</span><span class="sxs-lookup"><span data-stu-id="90af1-124">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>

    <span data-ttu-id="90af1-125">如果您的組織使用自訂報告解決方案或協力廠商解決方案，您可以[使用 Office 365 管理活動 API](air-custom-reporting.md)來查看有關自動化調查和威脅的資訊。</span><span class="sxs-lookup"><span data-stu-id="90af1-125">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](air-custom-reporting.md) to view information about automated investigations and threats.</span></span>

4. <span data-ttu-id="90af1-126">您的安全性運作小組會檢查[調查結果和建議](air-view-investigation-results.md)，並[批准或拒絕修正動作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="90af1-126">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span> 

    <span data-ttu-id="90af1-127">當未決修正動作經核准（或拒絕）時，自動調查完成。</span><span class="sxs-lookup"><span data-stu-id="90af1-127">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="90af1-128">在 Office 365 ATP 中，不會自動採取任何修正動作。</span><span class="sxs-lookup"><span data-stu-id="90af1-128">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="90af1-129">在組織的安全性小組核准後才能採取補救動作。</span><span class="sxs-lookup"><span data-stu-id="90af1-129">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

<span data-ttu-id="90af1-130">在自動化調查程序期間及之後，您的安全性小組可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="90af1-130">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="90af1-131">檢視與調查相關警示的詳細資料</span><span class="sxs-lookup"><span data-stu-id="90af1-131">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="90af1-132">查看調查的結果詳細資料</span><span class="sxs-lookup"><span data-stu-id="90af1-132">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="90af1-133">根據調查的結果檢閱和核准動作</span><span class="sxs-lookup"><span data-stu-id="90af1-133">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="90af1-134">如需詳細資訊，請參閱[AIR 的運作方式](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。</span><span class="sxs-lookup"><span data-stu-id="90af1-134">For more details, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="90af1-135">如何取得空中</span><span class="sxs-lookup"><span data-stu-id="90af1-135">How to get AIR</span></span>

<span data-ttu-id="90af1-136">Office 365 的 AIR 功能包含在[office 365 高級威脅防護方案 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)。</span><span class="sxs-lookup"><span data-stu-id="90af1-136">Office 365 AIR capabilities are included in [Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2).</span></span> <span data-ttu-id="90af1-137">不過，您[應設定 Office 365 ATP 原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)，讓 AIR 如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="90af1-137">However, your [Office 365 ATP policies should be configured](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) in order for AIR to work as expected.</span></span> <span data-ttu-id="90af1-138">此外，請務必複查並可能設定組織的[警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)。</span><span class="sxs-lookup"><span data-stu-id="90af1-138">In addition, make sure to review and potentially configure your organization's [alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span> 

<span data-ttu-id="90af1-139">Microsoft 365 提供許多內建的警示原則，可協助識別 Exchange 系統管理員許可權濫用、惡意程式碼活動、潛在的外部和內部威脅，以及資訊控管風險。</span><span class="sxs-lookup"><span data-stu-id="90af1-139">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="90af1-140">某些預設的[報警原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)可以觸發自動調查。</span><span class="sxs-lookup"><span data-stu-id="90af1-140">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="90af1-141">包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="90af1-141">These include the following:</span></span>

- <span data-ttu-id="90af1-142">偵測到可能的惡意 URL 按一下</span><span class="sxs-lookup"><span data-stu-id="90af1-142">A potentially malicious URL click is detected</span></span>

- <span data-ttu-id="90af1-143">使用者將電子郵件訊息當做網路釣魚詐騙進行報告</span><span class="sxs-lookup"><span data-stu-id="90af1-143">An email message is reported by a user as phish</span></span>

- <span data-ttu-id="90af1-144">傳遞後移除包含惡意程式碼的電子郵件</span><span class="sxs-lookup"><span data-stu-id="90af1-144">Email messages containing malware are removed after delivery</span></span>

- <span data-ttu-id="90af1-145">傳遞後移除包含網路釣魚 URLs 的電子郵件</span><span class="sxs-lookup"><span data-stu-id="90af1-145">Email messages containing phish URLs are removed after delivery</span></span>

- <span data-ttu-id="90af1-146">偵測到可疑的電子郵件寄送模式</span><span class="sxs-lookup"><span data-stu-id="90af1-146">Suspicious email sending patterns are detected</span></span>

- <span data-ttu-id="90af1-147">限制使用者傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="90af1-147">A user is restricted from sending email</span></span>

<span data-ttu-id="90af1-148">[深入瞭解警示和空中](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。</span><span class="sxs-lookup"><span data-stu-id="90af1-148">[Learn more about alerts and AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="90af1-149">使用 AIR 功能所需的許可權</span><span class="sxs-lookup"><span data-stu-id="90af1-149">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="90af1-150">許可權是透過特定角色授與的，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="90af1-150">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="90af1-151">工作</span><span class="sxs-lookup"><span data-stu-id="90af1-151">Task</span></span> |<span data-ttu-id="90af1-152">需要角色</span><span class="sxs-lookup"><span data-stu-id="90af1-152">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="90af1-153">設定 AIR 功能</span><span class="sxs-lookup"><span data-stu-id="90af1-153">To set up AIR features</span></span> |<span data-ttu-id="90af1-154">下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="90af1-154">One of the following roles:</span></span> <br/><span data-ttu-id="90af1-155">-全域管理員</span><span class="sxs-lookup"><span data-stu-id="90af1-155">- Global Administrator</span></span><br/><span data-ttu-id="90af1-156">-安全性管理員</span><span class="sxs-lookup"><span data-stu-id="90af1-156">- Security Administrator</span></span> <br/><span data-ttu-id="90af1-157">您可以在[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)或[Security & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="90af1-157">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="90af1-158">核准或拒絕建議的動作</span><span class="sxs-lookup"><span data-stu-id="90af1-158">To approve or reject recommended actions</span></span>|<span data-ttu-id="90af1-159">在[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)或[Security & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)內指派的下列角色之一：</span><span class="sxs-lookup"><span data-stu-id="90af1-159">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="90af1-160">-全域管理員</span><span class="sxs-lookup"><span data-stu-id="90af1-160">- Global Administrator</span></span> <br/><span data-ttu-id="90af1-161">-安全性管理員</span><span class="sxs-lookup"><span data-stu-id="90af1-161">- Security Administrator</span></span><br/><span data-ttu-id="90af1-162">-安全性讀取器</span><span class="sxs-lookup"><span data-stu-id="90af1-162">- Security Reader</span></span> <br/><span data-ttu-id="90af1-163">--- 且 ---</span><span class="sxs-lookup"><span data-stu-id="90af1-163">--- and ---</span></span><br/><span data-ttu-id="90af1-164">-搜尋和清除（此角色只會指派在[安全性 & 合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="90af1-164">- Search and Purge (this role is assigned only in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="90af1-165">您可能需要建立新的角色群組，並將搜尋和清除角色新增至該新的角色群組。）</span><span class="sxs-lookup"><span data-stu-id="90af1-165">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

<span data-ttu-id="90af1-166">[Office 365 ATP 計畫 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)授權應指派給：</span><span class="sxs-lookup"><span data-stu-id="90af1-166">[Office 365 ATP Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) licenses should be assigned to:</span></span>
- <span data-ttu-id="90af1-167">安全性管理員（包括全域管理員）</span><span class="sxs-lookup"><span data-stu-id="90af1-167">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="90af1-168">組織的安全性運作小組（包括安全性讀者和具有搜尋及清除角色的使用者）</span><span class="sxs-lookup"><span data-stu-id="90af1-168">Your organization's security operations team (including security readers and those with the Search and Purge role)</span></span>
- <span data-ttu-id="90af1-169">使用者</span><span class="sxs-lookup"><span data-stu-id="90af1-169">End users</span></span>

<span data-ttu-id="90af1-170">此外，必須定義及套用[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies)原則，才能進行保護。</span><span class="sxs-lookup"><span data-stu-id="90af1-170">In addition, [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) policies must be defined and applied in order for protection to be in place.</span></span>

## <a name="next-steps"></a><span data-ttu-id="90af1-171">後續步驟</span><span class="sxs-lookup"><span data-stu-id="90af1-171">Next steps</span></span>

- [<span data-ttu-id="90af1-172">查看自動調查的詳細資料和結果</span><span class="sxs-lookup"><span data-stu-id="90af1-172">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="90af1-173">審閱及核准擱置的動作</span><span class="sxs-lookup"><span data-stu-id="90af1-173">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="90af1-174">相關文章</span><span class="sxs-lookup"><span data-stu-id="90af1-174">Related articles</span></span>

- [<span data-ttu-id="90af1-175">Microsoft Defender 高級威脅防護中的自動化調查和修復</span><span class="sxs-lookup"><span data-stu-id="90af1-175">Automated investigation and remediation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="90af1-176">Microsoft 威脅防護的自動化調查及回應</span><span class="sxs-lookup"><span data-stu-id="90af1-176">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
