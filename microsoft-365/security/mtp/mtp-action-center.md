---
title: 移至重要訊息中心檢視及核准自動化調查和補救工作
description: 使用重要訊息中心檢視自動化調查的詳細資料及核准擱置的動作
keywords: 重要訊息中心, 威脅防護, 調查, 警示, 擱置, 自動化, 偵測
search.appverid: met150
ms.prod: M365-security-compliance
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 950dec4c0b0a2de2bdc60a73a12f6c7895189ea4
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910973"
---
# <a name="go-to-the-action-center-to-view-remediation-actions"></a><span data-ttu-id="ba95b-104">移至重要訊息中心檢視補救動作</span><span class="sxs-lookup"><span data-stu-id="ba95b-104">Go to the Action center to view remediation actions</span></span>

<span data-ttu-id="ba95b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ba95b-105">**Applies to:**</span></span>
- <span data-ttu-id="ba95b-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="ba95b-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="ba95b-107">「單一玻璃窗」體驗</span><span class="sxs-lookup"><span data-stu-id="ba95b-107">A "single pane of glass" experience</span></span>

![重要訊息中心](../images/air-actioncenter.png)

<span data-ttu-id="ba95b-109">使用重要訊息中心查看組織的裝置和信箱目前和過去的調查結果。</span><span class="sxs-lookup"><span data-stu-id="ba95b-109">Use the Action center to see the results of current and past investigations across your organization's devices and mailboxes.</span></span> <span data-ttu-id="ba95b-110">根據威脅類型和[產生的結果](mtp-autoir-results.md#remediation-actions-following-automated-investigation)，補救動作會自動進行，或由貴組織的安全性作業小組核准進行。</span><span class="sxs-lookup"><span data-stu-id="ba95b-110">Depending on the type of threat and [resulting verdict](mtp-autoir-results.md#remediation-actions-following-automated-investigation), remediation actions occur automatically or upon approval by your organization’s security operations team.</span></span> <span data-ttu-id="ba95b-111">所有補救動作 (無論是等待核准或已核准) 皆合併在重要訊息中心。</span><span class="sxs-lookup"><span data-stu-id="ba95b-111">All remediation actions, whether they are pending approval or were already approved, are consolidated in the Action center.</span></span> 

<span data-ttu-id="ba95b-112">重要訊息中心提供工作的「單一玻璃窗」體驗，例如：</span><span class="sxs-lookup"><span data-stu-id="ba95b-112">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="ba95b-113">核准擱置的補救動作；</span><span class="sxs-lookup"><span data-stu-id="ba95b-113">Approving pending remediation actions;</span></span>
- <span data-ttu-id="ba95b-114">檢視已核准的補救動作的稽核記錄；以及</span><span class="sxs-lookup"><span data-stu-id="ba95b-114">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="ba95b-115">檢閱已完成的補救動作。</span><span class="sxs-lookup"><span data-stu-id="ba95b-115">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="ba95b-116">由於重要訊息中心可在工作中提供全面檢視 Microsoft 威脅防護，因此您的安全性作業小組可以更有效率地運作。</span><span class="sxs-lookup"><span data-stu-id="ba95b-116">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft Threat Protection at work.</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="ba95b-117">補救動作</span><span class="sxs-lookup"><span data-stu-id="ba95b-117">Remediation actions</span></span>

<span data-ttu-id="ba95b-118">下表列出重要訊息中心目前支援的補救動作：</span><span class="sxs-lookup"><span data-stu-id="ba95b-118">The following table lists remediation actions that are currently supported in the Action center:</span></span> 

|<span data-ttu-id="ba95b-119">端點補救動作</span><span class="sxs-lookup"><span data-stu-id="ba95b-119">Endpoints remediation actions</span></span>  |<span data-ttu-id="ba95b-120">電子郵件補救動作</span><span class="sxs-lookup"><span data-stu-id="ba95b-120">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="ba95b-121">隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="ba95b-121">Quarantine file</span></span><br/><span data-ttu-id="ba95b-122">移除登錄機碼</span><span class="sxs-lookup"><span data-stu-id="ba95b-122">Remove registry key</span></span><br/><span data-ttu-id="ba95b-123">刪除處理序</span><span class="sxs-lookup"><span data-stu-id="ba95b-123">Kill process</span></span> <br/><span data-ttu-id="ba95b-124">停止服務</span><span class="sxs-lookup"><span data-stu-id="ba95b-124">Stop the service application</span></span> <br/><span data-ttu-id="ba95b-125">移除登錄機碼</span><span class="sxs-lookup"><span data-stu-id="ba95b-125">Remove registry key</span></span> <br/><span data-ttu-id="ba95b-126">停用驅動程式</span><span class="sxs-lookup"><span data-stu-id="ba95b-126">Disable driver</span></span> <br/><span data-ttu-id="ba95b-127">移除排程工作</span><span class="sxs-lookup"><span data-stu-id="ba95b-127">Remove scheduled task</span></span>      |<span data-ttu-id="ba95b-128">虛刪除電子郵件訊息或群集</span><span class="sxs-lookup"><span data-stu-id="ba95b-128">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="ba95b-129">封鎖 URL (點擊時)</span><span class="sxs-lookup"><span data-stu-id="ba95b-129">Block URL (time-of-click)</span></span><br/><span data-ttu-id="ba95b-130">關閉外部郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="ba95b-130">Turn off external mail forwarding</span></span>          |

## <a name="go-to-the-action-center"></a><span data-ttu-id="ba95b-131">移至重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="ba95b-131">Go to the admin center.</span></span>

1. <span data-ttu-id="ba95b-132">移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="ba95b-132">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in with an admin account.</span></span> 

2. <span data-ttu-id="ba95b-133">在功能窗格中，選擇 **[重要訊息中心]**。</span><span class="sxs-lookup"><span data-stu-id="ba95b-133">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="ba95b-134">您會在重要訊息中心看到兩個索引標籤：**[擱置中]** 和 **[歷史記錄]**。</span><span class="sxs-lookup"><span data-stu-id="ba95b-134">In the Action center, you’ll see two tabs: **Pending** and **History**.</span></span>

    - <span data-ttu-id="ba95b-135">**[擱置中]** 索引標籤會列出安全作業小組人員需要檢閱及核准才能繼續的調查。</span><span class="sxs-lookup"><span data-stu-id="ba95b-135">The **Pending** tab lists investigations that require review and approval by someone in your security operations team to continue.</span></span> <span data-ttu-id="ba95b-136">請務必檢閱您在這裡看到的擱置中項目並採取行動。</span><span class="sxs-lookup"><span data-stu-id="ba95b-136">Make sure to review and take action on pending items you see here.</span></span>

    - <span data-ttu-id="ba95b-137">**[歷史記錄]** 索引標籤會列出過去所做的調查和補救動作。</span><span class="sxs-lookup"><span data-stu-id="ba95b-137">The **History** tab lists past investigations and remediation actions that were taken automatically.</span></span> <span data-ttu-id="ba95b-138">您可以檢視過去一天、一周、一個月或六個月的資料。</span><span class="sxs-lookup"><span data-stu-id="ba95b-138">You can view data for the past day, week, month, or six months.</span></span>

4. <span data-ttu-id="ba95b-139">若只要顯示需要查看的欄，請選取 **[自訂欄]**。</span><span class="sxs-lookup"><span data-stu-id="ba95b-139">To show only the columns you want to see, select **Customize columns**.</span></span><br/><span data-ttu-id="ba95b-140">![Microsoft 威脅防護中的重要訊息中心](../images/mtp-action-center.png)</span><span class="sxs-lookup"><span data-stu-id="ba95b-140">![Action Center in Microsoft Threat Protection](../images/mtp-action-center.png)</span></span>

5. <span data-ttu-id="ba95b-141">選取清單中的項目以檢視更多有關某調查的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ba95b-141">Select an item in the list to view more details about an investigation.</span></span> <span data-ttu-id="ba95b-142">調查詳細資料檢視隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="ba95b-142">The investigation details view opens.</span></span><br/>![調查詳細資料](../images/mtp-air-investdetails.png)

    - <span data-ttu-id="ba95b-144">如果調查與電子郵件內容相關 (例如，實體為信箱)，便會在 Office 365 安全性與合規性中心 ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)) 開啟調查詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ba95b-144">If the investigation pertains to email content (such as, the entity is a mailbox), investigation details open in the Office 365 Security & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)).</span></span> 

    - <span data-ttu-id="ba95b-145">如果調查涉及裝置，便會在安全中心 ([https://security.microsoft.com](https://security.microsoft.com)) 開啟調查詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ba95b-145">If the investigation involves a device, investigation details open in the security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> 

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="ba95b-146">重要訊息中心的必要權限</span><span class="sxs-lookup"><span data-stu-id="ba95b-146">Required permissions for Action center tasks</span></span>

<span data-ttu-id="ba95b-147">若要核准或拒絕重要訊息中心的擱置中動作，您必須具有下表所列的權限：</span><span class="sxs-lookup"><span data-stu-id="ba95b-147">To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="ba95b-148">補救動作</span><span class="sxs-lookup"><span data-stu-id="ba95b-148">Remediation action</span></span> |<span data-ttu-id="ba95b-149">必要角色和權限</span><span class="sxs-lookup"><span data-stu-id="ba95b-149">Required licenses and permissions</span></span> |
|--|----|
|<span data-ttu-id="ba95b-150">Microsoft Defender ATP 補救 (裝置)</span><span class="sxs-lookup"><span data-stu-id="ba95b-150">Microsoft Defender ATP remediation (devices)</span></span> |<span data-ttu-id="ba95b-151">在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 指派**安全性系統管理員**角色</span><span class="sxs-lookup"><span data-stu-id="ba95b-151">**Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="ba95b-152">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="ba95b-152">\* or ‘.’</span></span><br/><span data-ttu-id="ba95b-153">在 Microsoft Defender ATP 中指派**作用中補救動作**角色</span><span class="sxs-lookup"><span data-stu-id="ba95b-153">**Active remediation actions** role assigned in Microsoft Defender ATP</span></span> <br/> <br/> <span data-ttu-id="ba95b-154">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="ba95b-154">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="ba95b-155">- [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="ba95b-155">Administrator role permissions in Azure Active Directory</span></span><br/><span data-ttu-id="ba95b-156">- [建立及管理角色型存取控制的角色 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="ba95b-156">- [Create and manage roles for role-based access control (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span></span>  |
|<span data-ttu-id="ba95b-157">Office 365 ATP 補救 (Office 內容和電子郵件)</span><span class="sxs-lookup"><span data-stu-id="ba95b-157">Office 365 ATP remediation (Office content and email)</span></span>  |<span data-ttu-id="ba95b-158">在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 指派**安全性系統管理員**角色</span><span class="sxs-lookup"><span data-stu-id="ba95b-158">**Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="ba95b-159">--- 且 ---</span><span class="sxs-lookup"><span data-stu-id="ba95b-159">--- and ---</span></span> <br/><span data-ttu-id="ba95b-160">在 Office 365 安全性與合規性中心指派 ([https://protection.office.com](https://protection.office.com)) **搜尋和清除**角色</span><span class="sxs-lookup"><span data-stu-id="ba95b-160">Search and Purge (this is assigned only in the Office 365 Security & Compliance Center)</span></span> <br/><br/><span data-ttu-id="ba95b-161">**重要**：如果您只在 Office 365 安全性與合規性中心指派安全性系統管理員角色，便無法存取重要訊息中心或 Microsoft 威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="ba95b-161">**IMPORTANT**: If you have the Security Administrator role assigned only in the Office 365 Security & Compliance Center, you will not be able to access the Action center or Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="ba95b-162">您必須在 Azure Active Directory 或 Microsoft 365 系統管理中心指派安全性系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="ba95b-162">You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="ba95b-163">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="ba95b-163">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="ba95b-164">- [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="ba95b-164">Administrator role permissions in Azure Active Directory</span></span><br/><span data-ttu-id="ba95b-165">- [Office 365 安全性與合規性中心中的權限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="ba95b-165">Permissions page in the Office 365 Security & Compliance Center</span></span> |

> [!NOTE]
> <span data-ttu-id="ba95b-166">在 Azure Active Directory 中指派為**全域管理員**角色的使用者可核准或拒絕重要訊息中心的任何擱置中動作。</span><span class="sxs-lookup"><span data-stu-id="ba95b-166">Users who have the **Global Administrator** role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="ba95b-167">不過，最佳做法是貴組織限制指派為全域管理員角色的人員人數。</span><span class="sxs-lookup"><span data-stu-id="ba95b-167">However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned.</span></span> <span data-ttu-id="ba95b-168">我們建議您針對重要訊息中心權限使用**安全性系統管理員**、**作用中補救動作**，以及上述 **「搜尋」和「清除」角色**。</span><span class="sxs-lookup"><span data-stu-id="ba95b-168">We recommend using the **Security Administrator**, **Active remediation actions**, and **Search and Purge** roles listed above for Action center permissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ba95b-169">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ba95b-169">Next steps</span></span> 

- [<span data-ttu-id="ba95b-170">深入了解 Microsoft 威脅防護中的事件</span><span class="sxs-lookup"><span data-stu-id="ba95b-170">Learn more about incidents in Microsoft Threat Protection</span></span>](incidents-overview.md)
- [<span data-ttu-id="ba95b-171">檢視自動調查的結果</span><span class="sxs-lookup"><span data-stu-id="ba95b-171">View the results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="ba95b-172">深入了解 Microsoft 威脅防護中的搜捕</span><span class="sxs-lookup"><span data-stu-id="ba95b-172">Learn about hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)

