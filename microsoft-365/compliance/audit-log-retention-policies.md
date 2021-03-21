---
title: 管理稽核記錄保留原則
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 稽核記錄保留原則是 Microsoft 365 中新增的「進階稽核」功能的一部分。 稽核記錄保留原則可讓您指定要在組織中保留稽核記錄的時間長度。
ms.openlocfilehash: 53449b6b83373eb2f749a4547845866dbea4a2af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922849"
---
# <a name="manage-audit-log-retention-policies"></a><span data-ttu-id="c0c5f-104">管理稽核記錄保留原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-104">Manage audit log retention policies</span></span>

<span data-ttu-id="c0c5f-105">您可以在安全性與合規性中心中建立及管理稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-105">You can create and manage audit log retention policies in the Security & Compliance Center.</span></span> <span data-ttu-id="c0c5f-106">稽核記錄保留原則是 Microsoft 365 中新增的「進階稽核」功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-106">Audit log retention policies are part of the new Advanced Audit capabilities in Microsoft 365.</span></span> <span data-ttu-id="c0c5f-107">稽核記錄保留原則可讓您指定要在組織中保留稽核記錄的時間長度。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-107">An audit log retention policy lets you specify how long to retain audit logs in your organization.</span></span> <span data-ttu-id="c0c5f-108">您最多可以保留稽核記錄達 10 年的時間。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-108">You can retain audit logs for up to 10 years.</span></span> <span data-ttu-id="c0c5f-109">您可以根據下列準則來建立原則：</span><span class="sxs-lookup"><span data-stu-id="c0c5f-109">You can create policies based on the following criteria:</span></span>

- <span data-ttu-id="c0c5f-110">一或多個 Microsoft 365 服務中的所有活動</span><span class="sxs-lookup"><span data-stu-id="c0c5f-110">All activities in one or more Microsoft 365 services</span></span>

- <span data-ttu-id="c0c5f-111">所有使用者或特定使用者執行的特定活動 (Microsoft 365 服務中)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-111">Specific activities (in a Microsoft 365 service) performed by all users or by specific users</span></span>

- <span data-ttu-id="c0c5f-112">優先順序層級，指定若您在組織中有多個原則，要優先處理的原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-112">A priority level that specifies which policy takes precedence in you have multiple policies in your organization</span></span>

## <a name="default-audit-log-retention-policy"></a><span data-ttu-id="c0c5f-113">預設稽核記錄保留原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-113">Default audit log retention policy</span></span>

<span data-ttu-id="c0c5f-114">Microsoft 365 中的「進階稽核」可為所有組織提供預設的稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-114">Advanced Audit in Microsoft 365 provides a default audit log retention policy for all organizations.</span></span> <span data-ttu-id="c0c5f-115">此原則會保留所有 Exchange、SharePoint 和 Azure Active Directory 稽核記錄一年。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-115">This policy retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="c0c5f-116">此預設原則會保留包含 **Workload** 屬性 (這是發生活動所在的服務) 的 **AzureActiveDirectory**、**Exchange** 或 **SharePoint** 值的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-116">This default policy retains audit records that contain the value of **AzureActiveDirectory**, **Exchange**, or **SharePoint** for the **Workload** property (which is the service in which the activity occurred).</span></span> <span data-ttu-id="c0c5f-117">您無法修改預設原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-117">The default policy can't be modified.</span></span> <span data-ttu-id="c0c5f-118">如需預設原則中所包含每個工作負載的記錄類型的清單，請參閱本文的[詳細資訊](#more-information)一節。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-118">See the [More information](#more-information) section in this article for a list of record types for each workload that are included in the default policy.</span></span>

> [!NOTE]
> <span data-ttu-id="c0c5f-119">預設的稽核記錄保留原則僅適用獲指派 Office 365 或 Microsoft 365 E5 授權或擁有 Microsoft 365 E5 合規性或 E5 電子文件探索和稽核附加元件授權的使用者所執行活動的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-119">The default audit log retention policy only applies to audit records for activity performed by users who are assigned an Office 365 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license.</span></span> <span data-ttu-id="c0c5f-120">如果組織中有非 E5 使用者或來賓使用者，其對應的稽核記錄會保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-120">If you have non-E5 users or guest users in your organization, their corresponding audit records are retained for 90 days.</span></span>

## <a name="before-you-create-an-audit-log-retention-policy"></a><span data-ttu-id="c0c5f-121">在建立稽核記錄保留原則之前</span><span class="sxs-lookup"><span data-stu-id="c0c5f-121">Before you create an audit log retention policy</span></span>

- <span data-ttu-id="c0c5f-122">您必須獲指派安全性與合規性中心中的「組織組態」角色，以才能建立或修改稽核保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-122">You have to be assigned the Organization Configuration role in the Security & Compliance Center to create or modify an audit retention policy.</span></span>

- <span data-ttu-id="c0c5f-123">您可以在組織中有最多 50 個稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-123">You can have a maximum of 50 audit log retention policies in your organization.</span></span>

- <span data-ttu-id="c0c5f-124">若要保留稽核記錄超過 90 天 (最多 1 年)，產生稽核記錄 (透過執行稽核活動) 的使用者必須獲指派 Office 365 E5 或 Microsoft 365 E5 授權，或擁有 365 Microsoft E5 合規性或 E5 電子文件探索與稽核附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-124">To retain an audit log for longer than 90 days (and up to 1 year), the user who generates the audit log (by performing an audited activity) must be assigned an Office 365 E5 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license.</span></span> <span data-ttu-id="c0c5f-125">若要保留稽核記錄 10 年，除了 E5 授權之外，還必須指派 10 年的稽核記錄保留附加元件授權給產生稽核記錄的使用者。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-125">To retain audit logs for 10 years, the user who generates the audit log must also be assigned a 10-year audit log retention add-on license in addition to an E5 license.</span></span>

- <span data-ttu-id="c0c5f-126">所有自訂稽核記錄保留原則 (由您的組織建立) 會優先於預設保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-126">All custom audit log retention policies (created by your organization) take priority over the default retention policy.</span></span> <span data-ttu-id="c0c5f-127">例如，如果您為具有的保留期間少於一年的建Exchange 信箱活動立稽核記錄保留原則，則 Exchange 信箱活動的稽核記錄將會保留較自訂原則所指定更短的持續時間。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-127">For example, if you create an audit log retention policy for Exchange mailbox activity that has a retention period that's shorter than one year, audit records for Exchange mailbox activities will be retained for the shorter duration specified by the custom policy.</span></span>

## <a name="create-an-audit-log-retention-policy"></a><span data-ttu-id="c0c5f-128">建立稽核記錄保留原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-128">Create an audit log retention policy</span></span>

1. <span data-ttu-id="c0c5f-129">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com)，並使用獲指派安全性與合規性中心的權限頁面中的「組織組態」角色的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-129">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in with a user account that's assigned the Organization Configuration role on the Permissions page in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="c0c5f-130">在 Microsoft 365 合規性中心的左窗格中，按一下 [顯示全部 **]**，然後按一下 [稽核 **]**。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-130">In the left pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

3. <span data-ttu-id="c0c5f-131">按一下 **[稽核保留原則]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-131">Click the **Audit retention policies** tab.</span></span>

4. <span data-ttu-id="c0c5f-132">按一下 **[建立稽核保留原則]**，然後在飛出視窗頁面中填寫下列欄位：</span><span class="sxs-lookup"><span data-stu-id="c0c5f-132">Click **Create audit retention policy**, and then complete the following fields on the flyout page:</span></span>

    ![新的稽核保留原則飛出視窗頁面](../media/CreateAuditLogRetentionPolicy.png)

   1. <span data-ttu-id="c0c5f-134">**原則名稱：** 稽核記錄保留原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-134">**Policy name:** The name of the audit log retention policy.</span></span> <span data-ttu-id="c0c5f-135">這個名稱需為貴組織中的唯一名稱，而且在建立原則之後即無法變更。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-135">This name must be unique in your organization, and it can't be change after the policy is created.</span></span>

   2. <span data-ttu-id="c0c5f-136">**描述：** 選用，但對於提供原則相關資訊 (例如記錄類型或工作負載)、原則中指定的使用者和持續時間有幫助。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-136">**Description:** Optional, but helpful to provide information about the policy, such as the record type or workload, users specified in the policy, and the duration.</span></span>

   3. <span data-ttu-id="c0c5f-137">**使用者：** 選取一或多個要套用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-137">**Users:** Select one or more users to apply the policy to.</span></span> <span data-ttu-id="c0c5f-138">如果將此方塊保留空白，則原則會套用至所有使用者。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-138">If you leave this box blank, then the policy will apply to all users.</span></span> <span data-ttu-id="c0c5f-139">如果將 [記錄類型 **]** 保留空白，則必須選取使用者。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-139">If you leave the **Record type** blank, then you must select a user.</span></span>

   4. <span data-ttu-id="c0c5f-140">**記錄類型：** 原則適用的稽核記錄類型。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-140">**Record type:** The audit record type the policy applies to.</span></span> <span data-ttu-id="c0c5f-141">如果將此屬性保留空白，則必須在 [使用者 **]** 方塊中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-141">If you leave this property blank, you must select a user in the **Users** box.</span></span> <span data-ttu-id="c0c5f-142">您可以選取單一記錄類型或多個記錄類型：</span><span class="sxs-lookup"><span data-stu-id="c0c5f-142">You can select a single record type or multiple record types:</span></span>

   - <span data-ttu-id="c0c5f-143">如果您選取單一記錄類型，則會動態顯示 [活動 **]** 欄位。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-143">If you select a single record type, the **Activities** field is dynamically displayed.</span></span> <span data-ttu-id="c0c5f-144">您可以使用下拉式清單從選取的記錄類型中選取活動，以便套用原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-144">You can use the drop-down list to select activities from the selected record type to apply the policy to.</span></span> <span data-ttu-id="c0c5f-145">如果您未選擇特定活動，則原則會套用至所選記錄類型的所有活動。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-145">If you don't choose specific activities, the policy will apply to all activities of the selected record type.</span></span>

   - <span data-ttu-id="c0c5f-146">如果您選取多個記錄類型，就無法選取活動。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-146">If you select multiple record types, you don't have the ability to select activities.</span></span> <span data-ttu-id="c0c5f-147">原則會套用至所選記錄類型的所有活動。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-147">The policy will apply to all activities of the selected record types.</span></span>

   5. <span data-ttu-id="c0c5f-148">**持續時間：** 保留符合原則準則之稽核記錄的時間量。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-148">**Duration:** The amount of time to retain the audit logs that meet the criteria of the policy.</span></span>

   6. <span data-ttu-id="c0c5f-149">**優先順序：** 此值會決定組織中稽核記錄保留原則的處理順序。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-149">**Priority:** This value determines the order in which audit log retention policies in your organization are processed.</span></span> <span data-ttu-id="c0c5f-150">較高的值表示優先順序較高。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-150">A higher value indicates a higher priority.</span></span> <span data-ttu-id="c0c5f-151">例如，優先順序值為 **5** 的原則會優先於優先順序值為 **0** 的原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-151">For example, a policy with a priority value of **5** would take priority over a policy with a priority value of **0**.</span></span> <span data-ttu-id="c0c5f-152">如先前所述，任何自訂稽核記錄保留原則的優先順序都會高於組織的預設原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-152">As previously explained, any custom audit log retention policy takes priority over the default policy for your organization.</span></span>

5. <span data-ttu-id="c0c5f-153">按一下 [儲存] 建立新的稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-153">Click **Save** to create the new audit log retention policy.</span></span>

   <span data-ttu-id="c0c5f-154">新原則會顯示在 **[稽核保留原則]** 索引標籤的清單中。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-154">The new policy is displayed in the list on the **Audit retention policies** tab.</span></span>

## <a name="manage-audit-log-retention-policies"></a><span data-ttu-id="c0c5f-155">管理稽核記錄保留原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-155">Manage audit log retention policies</span></span>

<span data-ttu-id="c0c5f-156">稽核記錄保留原則列在 **[稽核保留原則]** 索引標籤中 (又稱為 *[儀表板]*)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-156">Audit log retention policies are listed on the **Audit retention policies** tab (also called the *dashboard*).</span></span> <span data-ttu-id="c0c5f-157">您可以使用儀表板來查看、編輯及刪除稽核保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-157">You can use the dashboard to view, edit, and delete audit retention policies.</span></span>

### <a name="view-policies-in-the-dashboard"></a><span data-ttu-id="c0c5f-158">在儀表板中查看原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-158">View policies in the dashboard</span></span>

<span data-ttu-id="c0c5f-159">稽核記錄保留原則列在儀表板中。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-159">Audit log retention policies are listed in the dashboard.</span></span> <span data-ttu-id="c0c5f-160">在儀表板中查看原則的優點之一，就是您可以按一下 **[先順序]** 欄，以按照套用的優先順序列出原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-160">One advantage of viewing policies in the dashboard is that you can click the **Priority** column to list the policies in the priority in which they are applied.</span></span> <span data-ttu-id="c0c5f-161">如先前所述，較高的值表示優先順序較高。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-161">As previously explained, a higher value indicates a higher priority.</span></span>

![[稽核保留原則] 儀表板中的 [優先順序] 欄](../media/AuditLogRetentionDashboardPriority.png)

<span data-ttu-id="c0c5f-163">您也可以選取要在彈出式頁面上顯示其設定的原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-163">You can also select a policy to display its settings on the flyout page.</span></span>

> [!NOTE]
> <span data-ttu-id="c0c5f-164">儀表板中不會顯示貴組織的預設稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-164">The default audit log retention policy for your organization isn't displayed in the dashboard.</span></span>

### <a name="edit-policies-in-the-dashboard"></a><span data-ttu-id="c0c5f-165">在儀表板中編輯原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-165">Edit policies in the dashboard</span></span>

<span data-ttu-id="c0c5f-166">若要編輯原則，請選取該原則以顯示彈出式頁面。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-166">To edit a policy, select it to display the flyout page.</span></span> <span data-ttu-id="c0c5f-167">您可以修改一個或多個設定，然後儲存變更。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-167">You can modify one or more setting and then save your changes.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c0c5f-168">若使用 **New UnifiedAuditLogRetentionPolicy** Cmdlet，則可以為儀表版中的 **[建立稽核保留原則]** 工具中不可用的記錄類型或活動建立稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-168">If you use the **New-UnifiedAuditLogRetentionPolicy** cmdlet, it's possible to create an audit log retention policy for record types or activities that aren't available in the **Create audit retention policy** tool in the dashboard.</span></span> <span data-ttu-id="c0c5f-169">在這種情況下，您將無法從儀表板中的 **[稽核保留原則]** 中編輯原則 (例如，變更保留期或新增和移除活動)。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-169">In this case, you won't be able to edit the policy (for example, change the retention duration or add and remove activities) from the **Audit retention policies** dashboard.</span></span> <span data-ttu-id="c0c5f-170">您只能在 [合規性中心] 中檢視及刪除原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-170">You'll only be able to view and delete the policy in the compliance center.</span></span> <span data-ttu-id="c0c5f-171">若要編輯策略，必須在安全性與合規性中心 PowerShell 中使用[Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-171">To edit the policy, you'll have to use the [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell.</span></span><br/><br/><span data-ttu-id="c0c5f-172">**提示：** 彈出式頁面頂端會顯示一則訊息，指出必須使用 PowerShell 編輯的原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-172">**Tip:** A message is displayed at the top of the flyout page for policies that have to be edited using PowerShell.</span></span>

### <a name="delete-policies-in-the-dashboard"></a><span data-ttu-id="c0c5f-173">在儀表板中刪除原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-173">Delete policies in the dashboard</span></span>

<span data-ttu-id="c0c5f-174">若要刪除原則，請按一下 **[刪除]** ![[刪除圖示]](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)圖示，然後確認想要刪除原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-174">To delete a policy, click the **Delete** ![Delete icon](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg) icon and then confirm that you want to delete the policy.</span></span> <span data-ttu-id="c0c5f-175">該原則會從儀表板中移除，但您可能需要長達 30 分鐘的時間，該原則才會從貴組織中移除。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-175">The policy is removed from the dashboard, but it might take up to 30 minutes for the policy to be removed from your organization.</span></span>

## <a name="create-and-manage-audit-log-retention-policies-in-powershell"></a><span data-ttu-id="c0c5f-176">在 PowerShell 中建立並管理稽核記錄保留原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-176">Create and manage audit log retention policies in PowerShell</span></span>

<span data-ttu-id="c0c5f-177">您也可以使用安全性與合規性中心 PowerShell 來建立並管理稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-177">You can also use Security & Compliance Center PowerShell to create and manage audit log retention policies.</span></span> <span data-ttu-id="c0c5f-178">使用 PowerShell 的一個原因是，您可以為無法在 UI 中使用的記錄類型或活動建立原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-178">One reason to use PowerShell is to create a policy for a record type or activity that isn't available in the UI.</span></span>

### <a name="create-an-audit-log-retention-policy-in-powershell"></a><span data-ttu-id="c0c5f-179">在 PowerShell 中建立稽核記錄保留原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-179">Create an audit log retention policy in PowerShell</span></span>

<span data-ttu-id="c0c5f-180">請依照以下步驟，在 PowerShell 中建立稽核記錄保留原則：</span><span class="sxs-lookup"><span data-stu-id="c0c5f-180">Follow these steps to create an audit log retention policy in PowerShell:</span></span>

1. <span data-ttu-id="c0c5f-181">[連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-181">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c0c5f-182">執行下列命令以建立稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-182">Run the following command to create an audit log retention policy.</span></span>

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TenYears -Priority 100
   ```

    <span data-ttu-id="c0c5f-183">此範例會建立名為「Microsoft Teams 稽核原則」的稽核記錄保留原則，其中具有這些設定：</span><span class="sxs-lookup"><span data-stu-id="c0c5f-183">This example creates an audit log retention policy named "Microsoft Teams Audit Policy" with these settings:</span></span>

   - <span data-ttu-id="c0c5f-184">原則的描述。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-184">A description of the policy.</span></span>

   - <span data-ttu-id="c0c5f-185">保留所有 Microsoft Teams 活動 (如 *RecordType* 參數所定義)。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-185">Retains all Microsoft Teams activities (as defined by the *RecordType* parameter).</span></span>

   - <span data-ttu-id="c0c5f-186">保留 Microsoft Teams 稽核記錄 10 年。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-186">Retains Microsoft Teams audit logs for 10 years.</span></span>

   - <span data-ttu-id="c0c5f-187">優先順序為 100。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-187">A priority of 100.</span></span>

<span data-ttu-id="c0c5f-188">以下是建立稽核記錄保留原則的另一個範例。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-188">Here's another example of creating an audit log retention policy.</span></span> <span data-ttu-id="c0c5f-189">此原則會保留使用者 admin@contoso.onmicrosoft.com 的「使用者已登入」活動稽核記錄六個月。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-189">This policy retains audit logs for the "User logged in" activity for six months for the user admin@contoso.onmicrosoft.com.</span></span>

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

<span data-ttu-id="c0c5f-190">如需詳細資訊，請參閱 [New-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/new-unifiedauditlogretentionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-190">For more information, see [New-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/new-unifiedauditlogretentionpolicy).</span></span>

### <a name="view-policies-in-powershell"></a><span data-ttu-id="c0c5f-191">在 PowerShell 中查看原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-191">View policies in PowerShell</span></span>

<span data-ttu-id="c0c5f-192">在安全性與合規性中心 PowerShell 中使用 [Get-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/get-unifiedauditlogretentionpolicy) Cmdlet 來檢視稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-192">Use the [Get-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/get-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell to view audit log retention policies.</span></span>

<span data-ttu-id="c0c5f-193">以下的範例命令可用來顯示組織中所有的稽核記錄保留原則設定。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-193">Here's a sample command to display the settings for all audit log retention policies in your organization.</span></span> <span data-ttu-id="c0c5f-194">此命令會將原則的優先順序從最高到最低排序。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-194">This command sorts the policies from the highest to lowest priority.</span></span>

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> <span data-ttu-id="c0c5f-195">**Get-UnifiedAuditLogRetentionPolicy** Cmdlet 不會傳回組織的預設稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-195">The **Get-UnifiedAuditLogRetentionPolicy** cmdlet doesn't return the default audit log retention policy for your organization.</span></span>

### <a name="edit-policies-in-powershell"></a><span data-ttu-id="c0c5f-196">在 PowerShell 中編輯原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-196">Edit policies in PowerShell</span></span>

<span data-ttu-id="c0c5f-197">在安全性與合規性中心 PowerShell 中使用 [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) Cmdlet 來編輯現有的稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-197">Use the [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell to edit an existing audit log retention policy.</span></span>

### <a name="delete-policies-in-powershell"></a><span data-ttu-id="c0c5f-198">在 PowerShell 中刪除原則</span><span class="sxs-lookup"><span data-stu-id="c0c5f-198">Delete policies in PowerShell</span></span>

<span data-ttu-id="c0c5f-199">在安全性與合規性中心 PowerShell 中使用 [Remove-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/remove-unifiedauditlogretentionpolicy) Cmdlet 來刪除稽核記錄保留原則。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-199">Use the [Remove-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/remove-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell to delete an audit log retention policy.</span></span> <span data-ttu-id="c0c5f-200">從貴組織中移除原則可能需要多達 30 分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-200">It might take up to 30 minutes for the policy to be removed from your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="c0c5f-201">其他資訊</span><span class="sxs-lookup"><span data-stu-id="c0c5f-201">More information</span></span>

<span data-ttu-id="c0c5f-202">如先前所述，根據預設，Azure Active Directory、Exchange 和 SharePoint 中的作業稽核記錄會保留一年。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-202">As previously stated, audit records for operations in Azure Active Directory, Exchange, and SharePoint are retained for one year by default.</span></span> <span data-ttu-id="c0c5f-203">下表列出預設稽核記錄保留原則中(針對各項服務)所包含的所有記錄類型。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-203">The following table lists all the record types (for each of these services) included in the default audit log retention policy.</span></span> <span data-ttu-id="c0c5f-204">這表示具有此記錄類型的稽核記錄將保留一年，除非特定記錄類型、作業或使用者的自訂稽核記錄保留原則具有優先順序。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-204">This means that audit logs for any operation with this record type are retained for one year unless a custom audit log retention policy takes precedence for a specific record type, operation, or user.</span></span> <span data-ttu-id="c0c5f-205">每種記錄類型的 Enum 值 (在稽核記錄中顯示為 RecordType 屬性的值) 會顯示在括弧中。</span><span class="sxs-lookup"><span data-stu-id="c0c5f-205">The Enum value (which is displayed as the value for the RecordType property in an audit record) for each record type is shown in parentheses.</span></span>

|<span data-ttu-id="c0c5f-206">AzureActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="c0c5f-206">AzureActiveDirectory</span></span> |<span data-ttu-id="c0c5f-207">Exchange</span><span class="sxs-lookup"><span data-stu-id="c0c5f-207">Exchange</span></span>  |<span data-ttu-id="c0c5f-208">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c0c5f-208">SharePoint</span></span>|
|:---------|:---------|:---------|
|<span data-ttu-id="c0c5f-209">AzureActiveDirectory (8)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-209">AzureActiveDirectory (8)</span></span>|<span data-ttu-id="c0c5f-210">ExchangeAdmin (1)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-210">ExchangeAdmin (1)</span></span>|<span data-ttu-id="c0c5f-211">ComplianceDLPSharePoint (11)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-211">ComplianceDLPSharePoint (11)</span></span>|
|<span data-ttu-id="c0c5f-212">AzureActiveDirectoryAccountLogon (9)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-212">AzureActiveDirectoryAccountLogon (9)</span></span>|<span data-ttu-id="c0c5f-213">ExchangeItem (2)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-213">ExchangeItem (2)</span></span>|<span data-ttu-id="c0c5f-214">ComplianceDLPSharePointClassification (33)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-214">ComplianceDLPSharePointClassification (33)</span></span>|
|<span data-ttu-id="c0c5f-215">AzureActiveDirectoryStsLogon (15)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-215">AzureActiveDirectoryStsLogon (15)</span></span>|<span data-ttu-id="c0c5f-216">行銷活動 (62)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-216">Campaign (62)</span></span>|<span data-ttu-id="c0c5f-217">Project (35)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-217">Project (35)</span></span>|
||<span data-ttu-id="c0c5f-218">ComplianceDLPExchange (13)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-218">ComplianceDLPExchange (13)</span></span>|<span data-ttu-id="c0c5f-219">SharePoint (4)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-219">SharePoint (4)</span></span>|
||<span data-ttu-id="c0c5f-220">ComplianceSupervisionExchange (68)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-220">ComplianceSupervisionExchange (68)</span></span>|<span data-ttu-id="c0c5f-221">SharePointCommentOperation (37)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-221">SharePointCommentOperation (37)</span></span>|
||<span data-ttu-id="c0c5f-222">CustomerKeyServiceEncryption (69)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-222">CustomerKeyServiceEncryption (69)</span></span>|<span data-ttu-id="c0c5f-223">SharePointContentTypeOperation (55)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-223">SharePointContentTypeOperation (55)</span></span>|
||<span data-ttu-id="c0c5f-224">ExchangeAggregatedOperation (19)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-224">ExchangeAggregatedOperation (19)</span></span>|<span data-ttu-id="c0c5f-225">SharePointFieldOperation (56)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-225">SharePointFieldOperation (56)</span></span>|
||<span data-ttu-id="c0c5f-226">ExchangeItemAggregated (50)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-226">ExchangeItemAggregated (50)</span></span>|<span data-ttu-id="c0c5f-227">SharePointFileOperation (6)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-227">SharePointFileOperation (6)</span></span>|
||<span data-ttu-id="c0c5f-228">ExchangeItemGroup (3)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-228">ExchangeItemGroup (3)</span></span>|<span data-ttu-id="c0c5f-229">SharePointListOperation (36)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-229">SharePointListOperation (36)</span></span>|
||<span data-ttu-id="c0c5f-230">InformationBarrierPolicyApplication (53)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-230">InformationBarrierPolicyApplication (53)</span></span>|<span data-ttu-id="c0c5f-231">SharePointSharingOperation (14)</span><span class="sxs-lookup"><span data-stu-id="c0c5f-231">SharePointSharingOperation (14)</span></span>|
||||