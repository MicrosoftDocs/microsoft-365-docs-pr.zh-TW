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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 3ec17204903f3e83f3fbfd126d57d0b9ca5d56f7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843789"
---
# <a name="the-action-center"></a><span data-ttu-id="7eb03-104">重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="7eb03-104">The Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7eb03-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="7eb03-105">**Applies to:**</span></span>
- <span data-ttu-id="7eb03-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7eb03-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7eb03-107">使用重要訊息中心查看組織的裝置和信箱目前和過去的調查結果。</span><span class="sxs-lookup"><span data-stu-id="7eb03-107">Use the Action center to see the results of current and past investigations across your organization's devices and mailboxes.</span></span> <span data-ttu-id="7eb03-108">根據威脅類型和產生的判定，您的組織的安全性運作小組會自動或核准執行 [修正動作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) 。</span><span class="sxs-lookup"><span data-stu-id="7eb03-108">Depending on the type of threat and resulting verdict, [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="7eb03-109">所有補救動作 (無論是等待核准或已核准) 皆合併在重要訊息中心。</span><span class="sxs-lookup"><span data-stu-id="7eb03-109">All remediation actions, whether they are pending approval or were already approved, are consolidated in the Action center.</span></span> 

![重要訊息中心](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="7eb03-111">「單一玻璃窗」體驗</span><span class="sxs-lookup"><span data-stu-id="7eb03-111">A "single pane of glass" experience</span></span>

<span data-ttu-id="7eb03-112">重要訊息中心提供工作的「單一玻璃窗」體驗，例如：</span><span class="sxs-lookup"><span data-stu-id="7eb03-112">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="7eb03-113">核准擱置的補救動作；</span><span class="sxs-lookup"><span data-stu-id="7eb03-113">Approving pending remediation actions;</span></span>
- <span data-ttu-id="7eb03-114">檢視已核准的補救動作的稽核記錄；以及</span><span class="sxs-lookup"><span data-stu-id="7eb03-114">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="7eb03-115">檢閱已完成的補救動作。</span><span class="sxs-lookup"><span data-stu-id="7eb03-115">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="7eb03-116">您的安全性運作小組可以更有效率地運作，因為行動中心會在工作中提供完整的 Microsoft 365 Defender 的觀點。</span><span class="sxs-lookup"><span data-stu-id="7eb03-116">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft 365 Defender at work.</span></span>

## <a name="go-to-the-action-center"></a><span data-ttu-id="7eb03-117">移至重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="7eb03-117">Go to the Action center</span></span>

1. <span data-ttu-id="7eb03-118">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="7eb03-118">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="7eb03-119">在功能窗格中，選擇 [控制中心]。</span><span class="sxs-lookup"><span data-stu-id="7eb03-119">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="7eb03-120">在 [操作中心] 中，您會看到兩個索引標籤： **擱置** 和 **記錄** 。</span><span class="sxs-lookup"><span data-stu-id="7eb03-120">In the Action center, you'll see two tabs: **Pending** and **History**.</span></span>

    - <span data-ttu-id="7eb03-121">**[擱置中]** 索引標籤會列出安全作業小組人員需要檢閱及核准才能繼續的調查。</span><span class="sxs-lookup"><span data-stu-id="7eb03-121">The **Pending** tab lists investigations that require review and approval by someone in your security operations team to continue.</span></span> <span data-ttu-id="7eb03-122">請務必檢閱您在這裡看到的擱置中項目並採取行動。</span><span class="sxs-lookup"><span data-stu-id="7eb03-122">Make sure to review and take action on pending items you see here.</span></span>

    - <span data-ttu-id="7eb03-123">**[歷史記錄]** 索引標籤會列出過去所做的調查和補救動作。</span><span class="sxs-lookup"><span data-stu-id="7eb03-123">The **History** tab lists past investigations and remediation actions that were taken automatically.</span></span> <span data-ttu-id="7eb03-124">您可以檢視過去一天、一周、一個月或六個月的資料。</span><span class="sxs-lookup"><span data-stu-id="7eb03-124">You can view data for the past day, week, month, or six months.</span></span>

4. <span data-ttu-id="7eb03-125">若只要顯示需要查看的欄，請選取 **[自訂欄]** 。</span><span class="sxs-lookup"><span data-stu-id="7eb03-125">To show only the columns you want to see, select **Customize columns**.</span></span><br/><span data-ttu-id="7eb03-126">![Microsoft 365 Defender 中的動作中心](../../media/mtp-action-center.png)</span><span class="sxs-lookup"><span data-stu-id="7eb03-126">![Action Center in Microsoft 365 Defender](../../media/mtp-action-center.png)</span></span>

5. <span data-ttu-id="7eb03-127">選取清單中的項目以檢視更多有關某調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7eb03-127">Select an item in the list to view more details about an investigation.</span></span> <span data-ttu-id="7eb03-128">調查詳細資料檢視隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="7eb03-128">The investigation details view opens.</span></span><br/>![調查詳細資料](../../media/mtp-air-investdetails.png)

    - <span data-ttu-id="7eb03-130">如果調查與電子郵件內容相關 (例如，實體為信箱) ，在安全性 & 規範中心中開啟調查詳細資料 ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)) 。</span><span class="sxs-lookup"><span data-stu-id="7eb03-130">If the investigation pertains to email content (such as, the entity is a mailbox), investigation details open in the Security & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)).</span></span> 

    - <span data-ttu-id="7eb03-131">如果調查涉及裝置，便會在安全中心 ([https://security.microsoft.com](https://security.microsoft.com)) 開啟調查詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7eb03-131">If the investigation involves a device, investigation details open in the security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> 

> [!TIP]
> <span data-ttu-id="7eb03-132">如果您認為 Microsoft 365 Defender 中的自動調查和回應功能已錯過或錯誤地偵測到某項功能，請讓我們知道！</span><span class="sxs-lookup"><span data-stu-id="7eb03-132">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="7eb03-133">請參閱 [如何在自動調查和回應中報告誤報/負片 (Microsoft 365 Defender 中的 AIR) 功能](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="7eb03-133">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="available-actions"></a><span data-ttu-id="7eb03-134">可用動作</span><span class="sxs-lookup"><span data-stu-id="7eb03-134">Available actions</span></span>

<span data-ttu-id="7eb03-135">採取補救措施時，這些動作會列在重要訊息中心的 [記錄] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="7eb03-135">As remediation actions are taken, they're listed on the History tab in the Action center.</span></span> <span data-ttu-id="7eb03-136">這類動作包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="7eb03-136">Such actions include the following:</span></span>

- <span data-ttu-id="7eb03-137">收集調查套件</span><span class="sxs-lookup"><span data-stu-id="7eb03-137">Collect investigation package</span></span> 
- <span data-ttu-id="7eb03-138">隔離裝置 (此動作可復原) </span><span class="sxs-lookup"><span data-stu-id="7eb03-138">Isolate device (this action can be undone)</span></span> 
- <span data-ttu-id="7eb03-139">下架機</span><span class="sxs-lookup"><span data-stu-id="7eb03-139">Offboard machine</span></span> 
- <span data-ttu-id="7eb03-140">發行程式碼執行</span><span class="sxs-lookup"><span data-stu-id="7eb03-140">Release code execution</span></span> 
- <span data-ttu-id="7eb03-141">從隔離區發行</span><span class="sxs-lookup"><span data-stu-id="7eb03-141">Release from quarantine</span></span> 
- <span data-ttu-id="7eb03-142">要求範例</span><span class="sxs-lookup"><span data-stu-id="7eb03-142">Request sample</span></span> 
- <span data-ttu-id="7eb03-143">限制程式碼執行 (可以復原此動作) </span><span class="sxs-lookup"><span data-stu-id="7eb03-143">Restrict code execution (this action can be undone)</span></span> 
- <span data-ttu-id="7eb03-144">執行防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="7eb03-144">Run antivirus scan</span></span> 
- <span data-ttu-id="7eb03-145">停止和隔離</span><span class="sxs-lookup"><span data-stu-id="7eb03-145">Stop and quarantine</span></span> 

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="7eb03-146">重要訊息中心的必要權限</span><span class="sxs-lookup"><span data-stu-id="7eb03-146">Required permissions for Action center tasks</span></span>

<span data-ttu-id="7eb03-147">若要核准或拒絕重要訊息中心的擱置中動作，您必須具有下表所列的權限：</span><span class="sxs-lookup"><span data-stu-id="7eb03-147">To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="7eb03-148">補救動作</span><span class="sxs-lookup"><span data-stu-id="7eb03-148">Remediation action</span></span> |<span data-ttu-id="7eb03-149">必要角色和權限</span><span class="sxs-lookup"><span data-stu-id="7eb03-149">Required roles and permissions</span></span> |
|--|----|
|<span data-ttu-id="7eb03-150">Microsoft Defender for Endpoint 修復 (裝置) </span><span class="sxs-lookup"><span data-stu-id="7eb03-150">Microsoft Defender for Endpoint remediation (devices)</span></span> |<span data-ttu-id="7eb03-151">在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 指派安全性系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="7eb03-151">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="7eb03-152">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="7eb03-152">--- or ---</span></span><br/><span data-ttu-id="7eb03-153">在 Microsoft Defender for Endpoint 中指派作用中的修正動作角色</span><span class="sxs-lookup"><span data-stu-id="7eb03-153">Active remediation actions role assigned in Microsoft Defender for Endpoint</span></span> <br/> <br/> <span data-ttu-id="7eb03-154">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="7eb03-154">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="7eb03-155">- [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="7eb03-155">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="7eb03-156">- [建立及管理角色型存取控制 (Microsoft Defender for Endpoint) ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="7eb03-156">- [Create and manage roles for role-based access control (Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span></span>  |
|<span data-ttu-id="7eb03-157">Microsoft Defender for Office 365 修正 (Office 內容和電子郵件) </span><span class="sxs-lookup"><span data-stu-id="7eb03-157">Microsoft Defender for Office 365 remediation (Office content and email)</span></span>  |<span data-ttu-id="7eb03-158">在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 指派安全性系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="7eb03-158">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="7eb03-159">--- 且 ---</span><span class="sxs-lookup"><span data-stu-id="7eb03-159">--- and ---</span></span> <br/><span data-ttu-id="7eb03-160">搜尋及清除已指派安全性 & 規範中心 (的角色 [https://protection.office.com](https://protection.office.com)) </span><span class="sxs-lookup"><span data-stu-id="7eb03-160">Search and Purge role assigned the Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span> <br/><br/><span data-ttu-id="7eb03-161">**重要** ：如果您已將安全性系統管理員角色指派給安全性 & 合規性中心，您將無法存取「行動中心」或「Microsoft 365 Defender」功能。</span><span class="sxs-lookup"><span data-stu-id="7eb03-161">**IMPORTANT** : If you have the Security Administrator role assigned only in the Security & Compliance Center, you will not be able to access the Action center or Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="7eb03-162">您必須在 Azure Active Directory 或 Microsoft 365 系統管理中心指派安全性系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="7eb03-162">You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="7eb03-163">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="7eb03-163">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="7eb03-164">- [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="7eb03-164">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="7eb03-165">- [安全性 & 規範中心的許可權](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="7eb03-165">- [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span></span> |

> [!NOTE]
> <span data-ttu-id="7eb03-166">在 Azure Active Directory 中指派為全域管理員角色的使用者可核准或拒絕重要訊息中心的任何擱置中動作。</span><span class="sxs-lookup"><span data-stu-id="7eb03-166">Users who have the Global Administrator role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="7eb03-167">不過，最佳做法是貴組織限制指派為全域管理員角色的人員人數。</span><span class="sxs-lookup"><span data-stu-id="7eb03-167">However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned.</span></span> <span data-ttu-id="7eb03-168">我們建議您針對重要訊息中心權限使用安全性系統管理員、作用中補救動作，以及上述「搜尋」和「清除」角色。</span><span class="sxs-lookup"><span data-stu-id="7eb03-168">We recommend using the Security Administrator, Active remediation actions, and Search and Purge roles listed above for Action center permissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7eb03-169">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7eb03-169">Next steps</span></span> 

- [<span data-ttu-id="7eb03-170">自動調查後核准或拒絕擱置的動作</span><span class="sxs-lookup"><span data-stu-id="7eb03-170">Approve or reject pending actions following an automated investigation</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="7eb03-171">檢視自動調查的結果</span><span class="sxs-lookup"><span data-stu-id="7eb03-171">View the results of an automated investigation</span></span>](mtp-autoir-results.md)

