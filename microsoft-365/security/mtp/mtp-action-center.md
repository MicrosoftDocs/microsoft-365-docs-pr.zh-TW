---
title: 移至重要訊息中心檢視及核准自動化調查和補救工作
description: 使用重要訊息中心檢視自動化調查的詳細資料及核准擱置的動作
keywords: 重要訊息中心, 威脅防護, 調查, 警示, 擱置, 自動化, 偵測
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 651beeff6326e6cab898c4297bcd50edc241a9d4
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413683"
---
# <a name="the-action-center"></a><span data-ttu-id="0df61-104">重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="0df61-104">The Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0df61-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0df61-105">**Applies to:**</span></span>
- <span data-ttu-id="0df61-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="0df61-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0df61-107">使用重要訊息中心查看組織的裝置和信箱目前和過去的調查結果。</span><span class="sxs-lookup"><span data-stu-id="0df61-107">Use the Action center to see the results of current and past investigations across your organization's devices and mailboxes.</span></span> <span data-ttu-id="0df61-108">根據威脅類型和產生的判定，您的組織的安全性運作小組會自動或核准執行 [修正動作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) 。</span><span class="sxs-lookup"><span data-stu-id="0df61-108">Depending on the type of threat and resulting verdict, [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="0df61-109">所有補救動作 (無論是等待核准或已核准) 皆合併在重要訊息中心。</span><span class="sxs-lookup"><span data-stu-id="0df61-109">All remediation actions, whether they are pending approval or were already approved, are consolidated in the Action center.</span></span> 

![重要訊息中心](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="0df61-111">「單一玻璃窗」體驗</span><span class="sxs-lookup"><span data-stu-id="0df61-111">A "single pane of glass" experience</span></span>

<span data-ttu-id="0df61-112">重要訊息中心提供工作的「單一玻璃窗」體驗，例如：</span><span class="sxs-lookup"><span data-stu-id="0df61-112">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="0df61-113">核准擱置的補救動作；</span><span class="sxs-lookup"><span data-stu-id="0df61-113">Approving pending remediation actions;</span></span>
- <span data-ttu-id="0df61-114">檢視已核准的補救動作的稽核記錄；以及</span><span class="sxs-lookup"><span data-stu-id="0df61-114">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="0df61-115">檢閱已完成的補救動作。</span><span class="sxs-lookup"><span data-stu-id="0df61-115">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="0df61-116">由於重要訊息中心可在工作中提供全面檢視 Microsoft 威脅防護，因此您的安全性作業小組可以更有效率地運作。</span><span class="sxs-lookup"><span data-stu-id="0df61-116">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft Threat Protection at work.</span></span>

## <a name="go-to-the-action-center"></a><span data-ttu-id="0df61-117">移至重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="0df61-117">Go to the Action center</span></span>

1. <span data-ttu-id="0df61-118">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="0df61-118">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="0df61-119">在功能窗格中，選擇 [控制中心]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0df61-119">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="0df61-120">在 [操作中心] 中，您會看到兩個索引標籤： **擱置** 和 **記錄**。</span><span class="sxs-lookup"><span data-stu-id="0df61-120">In the Action center, you'll see two tabs: **Pending** and **History**.</span></span>

    - <span data-ttu-id="0df61-121">**[擱置中]** 索引標籤會列出安全作業小組人員需要檢閱及核准才能繼續的調查。</span><span class="sxs-lookup"><span data-stu-id="0df61-121">The **Pending** tab lists investigations that require review and approval by someone in your security operations team to continue.</span></span> <span data-ttu-id="0df61-122">請務必檢閱您在這裡看到的擱置中項目並採取行動。</span><span class="sxs-lookup"><span data-stu-id="0df61-122">Make sure to review and take action on pending items you see here.</span></span>

    - <span data-ttu-id="0df61-123">**[歷史記錄]** 索引標籤會列出過去所做的調查和補救動作。</span><span class="sxs-lookup"><span data-stu-id="0df61-123">The **History** tab lists past investigations and remediation actions that were taken automatically.</span></span> <span data-ttu-id="0df61-124">您可以檢視過去一天、一周、一個月或六個月的資料。</span><span class="sxs-lookup"><span data-stu-id="0df61-124">You can view data for the past day, week, month, or six months.</span></span>

4. <span data-ttu-id="0df61-125">若只要顯示需要查看的欄，請選取 **[自訂欄]**。</span><span class="sxs-lookup"><span data-stu-id="0df61-125">To show only the columns you want to see, select **Customize columns**.</span></span><br/><span data-ttu-id="0df61-126">![Microsoft 威脅防護中的重要訊息中心](../../media/mtp-action-center.png)</span><span class="sxs-lookup"><span data-stu-id="0df61-126">![Action Center in Microsoft Threat Protection](../../media/mtp-action-center.png)</span></span>

5. <span data-ttu-id="0df61-127">選取清單中的項目以檢視更多有關某調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0df61-127">Select an item in the list to view more details about an investigation.</span></span> <span data-ttu-id="0df61-128">調查詳細資料檢視隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="0df61-128">The investigation details view opens.</span></span><br/>![調查詳細資料](../../media/mtp-air-investdetails.png)

    - <span data-ttu-id="0df61-130">如果調查與電子郵件內容相關 (例如，實體為信箱) ，在安全性 & 規範中心中開啟調查詳細資料 ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)) 。</span><span class="sxs-lookup"><span data-stu-id="0df61-130">If the investigation pertains to email content (such as, the entity is a mailbox), investigation details open in the Security & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)).</span></span> 

    - <span data-ttu-id="0df61-131">如果調查涉及裝置，便會在安全中心 ([https://security.microsoft.com](https://security.microsoft.com)) 開啟調查詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0df61-131">If the investigation involves a device, investigation details open in the security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> 

> [!TIP]
> <span data-ttu-id="0df61-132">如果您認為 Microsoft 威脅防護中的自動調查和回應功能已錯過或錯誤地偵測到某項功能，請告訴我們！</span><span class="sxs-lookup"><span data-stu-id="0df61-132">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="0df61-133">請參閱 how [to (AIR) Microsoft 威脅防護中的功能，以自動化調查和回應報告誤報的誤報/負片](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="0df61-133">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="available-actions"></a><span data-ttu-id="0df61-134">可用動作</span><span class="sxs-lookup"><span data-stu-id="0df61-134">Available actions</span></span>

<span data-ttu-id="0df61-135">採取補救措施時，這些動作會列在重要訊息中心的 [記錄] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="0df61-135">As remediation actions are taken, they're listed on the History tab in the Action center.</span></span> <span data-ttu-id="0df61-136">這類動作包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="0df61-136">Such actions include the following:</span></span>

- <span data-ttu-id="0df61-137">收集調查套件</span><span class="sxs-lookup"><span data-stu-id="0df61-137">Collect investigation package</span></span> 
- <span data-ttu-id="0df61-138">隔離裝置 (此動作可復原) </span><span class="sxs-lookup"><span data-stu-id="0df61-138">Isolate device (this action can be undone)</span></span> 
- <span data-ttu-id="0df61-139">下架機</span><span class="sxs-lookup"><span data-stu-id="0df61-139">Offboard machine</span></span> 
- <span data-ttu-id="0df61-140">發行程式碼執行</span><span class="sxs-lookup"><span data-stu-id="0df61-140">Release code execution</span></span> 
- <span data-ttu-id="0df61-141">從隔離區發行</span><span class="sxs-lookup"><span data-stu-id="0df61-141">Release from quarantine</span></span> 
- <span data-ttu-id="0df61-142">要求範例</span><span class="sxs-lookup"><span data-stu-id="0df61-142">Request sample</span></span> 
- <span data-ttu-id="0df61-143">限制程式碼執行 (可以復原此動作) </span><span class="sxs-lookup"><span data-stu-id="0df61-143">Restrict code execution (this action can be undone)</span></span> 
- <span data-ttu-id="0df61-144">執行防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="0df61-144">Run antivirus scan</span></span> 
- <span data-ttu-id="0df61-145">停止和隔離</span><span class="sxs-lookup"><span data-stu-id="0df61-145">Stop and quarantine</span></span> 

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="0df61-146">重要訊息中心的必要權限</span><span class="sxs-lookup"><span data-stu-id="0df61-146">Required permissions for Action center tasks</span></span>

<span data-ttu-id="0df61-147">若要核准或拒絕重要訊息中心的擱置中動作，您必須具有下表所列的權限：</span><span class="sxs-lookup"><span data-stu-id="0df61-147">To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="0df61-148">補救動作</span><span class="sxs-lookup"><span data-stu-id="0df61-148">Remediation action</span></span> |<span data-ttu-id="0df61-149">必要角色和權限</span><span class="sxs-lookup"><span data-stu-id="0df61-149">Required roles and permissions</span></span> |
|--|----|
|<span data-ttu-id="0df61-150">Microsoft Defender ATP 補救 (裝置)</span><span class="sxs-lookup"><span data-stu-id="0df61-150">Microsoft Defender ATP remediation (devices)</span></span> |<span data-ttu-id="0df61-151">在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 指派安全性系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="0df61-151">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="0df61-152">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="0df61-152">--- or ---</span></span><br/><span data-ttu-id="0df61-153">在 Microsoft Defender ATP 中指派作用中補救動作角色</span><span class="sxs-lookup"><span data-stu-id="0df61-153">Active remediation actions role assigned in Microsoft Defender ATP</span></span> <br/> <br/> <span data-ttu-id="0df61-154">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="0df61-154">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="0df61-155">- [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="0df61-155">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="0df61-156">- [建立及管理角色型存取控制的角色 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="0df61-156">- [Create and manage roles for role-based access control (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span></span>  |
|<span data-ttu-id="0df61-157">Office 365 ATP 補救 (Office 內容和電子郵件)</span><span class="sxs-lookup"><span data-stu-id="0df61-157">Office 365 ATP remediation (Office content and email)</span></span>  |<span data-ttu-id="0df61-158">在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 指派安全性系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="0df61-158">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="0df61-159">--- 且 ---</span><span class="sxs-lookup"><span data-stu-id="0df61-159">--- and ---</span></span> <br/><span data-ttu-id="0df61-160">搜尋及清除已指派安全性 & 規範中心 (的角色 [https://protection.office.com](https://protection.office.com)) </span><span class="sxs-lookup"><span data-stu-id="0df61-160">Search and Purge role assigned the Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span> <br/><br/><span data-ttu-id="0df61-161">**重要**：如果您已將安全性系統管理員角色指派給安全性 & 合規性中心，您將無法存取「行動中心」或「Microsoft 威脅防護」功能。</span><span class="sxs-lookup"><span data-stu-id="0df61-161">**IMPORTANT**: If you have the Security Administrator role assigned only in the Security & Compliance Center, you will not be able to access the Action center or Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="0df61-162">您必須在 Azure Active Directory 或 Microsoft 365 系統管理中心指派安全性系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="0df61-162">You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="0df61-163">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="0df61-163">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="0df61-164">- [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="0df61-164">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="0df61-165">- [安全性 & 規範中心的許可權](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="0df61-165">- [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span></span> |

> [!NOTE]
> <span data-ttu-id="0df61-166">在 Azure Active Directory 中指派為全域管理員角色的使用者可核准或拒絕重要訊息中心的任何擱置中動作。</span><span class="sxs-lookup"><span data-stu-id="0df61-166">Users who have the Global Administrator role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="0df61-167">不過，最佳做法是貴組織限制指派為全域管理員角色的人員人數。</span><span class="sxs-lookup"><span data-stu-id="0df61-167">However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned.</span></span> <span data-ttu-id="0df61-168">我們建議您針對重要訊息中心權限使用安全性系統管理員、作用中補救動作，以及上述「搜尋」和「清除」角色。</span><span class="sxs-lookup"><span data-stu-id="0df61-168">We recommend using the Security Administrator, Active remediation actions, and Search and Purge roles listed above for Action center permissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0df61-169">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0df61-169">Next steps</span></span> 

- [<span data-ttu-id="0df61-170">自動調查後核准或拒絕擱置的動作</span><span class="sxs-lookup"><span data-stu-id="0df61-170">Approve or reject pending actions following an automated investigation</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="0df61-171">檢視自動調查的結果</span><span class="sxs-lookup"><span data-stu-id="0df61-171">View the results of an automated investigation</span></span>](mtp-autoir-results.md)

