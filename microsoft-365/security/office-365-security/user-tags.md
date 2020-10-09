---
title: Office 365 ATP 中的使用者標記
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Office 365 ATP 方案2中識別具有使用者標記的特定使用者群組。 標記篩選可用於 Office 365 ATP 中的提醒、報告和調查，以快速識別已標記的使用者。
ms.openlocfilehash: 16e756b95e16e40f4df738e825e842681c67e22c
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399382"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="99d61-104">Office 365 ATP 中的使用者標記</span><span class="sxs-lookup"><span data-stu-id="99d61-104">User tags in Office 365 ATP</span></span>

<span data-ttu-id="99d61-105">使用者標記是 [Office 365 Advanced 威脅防護 (ATP) ](office-365-atp.md)中的特定使用者群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="99d61-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="99d61-106">使用者標記有兩種類型：</span><span class="sxs-lookup"><span data-stu-id="99d61-106">There are two types of user tags:</span></span>

- <span data-ttu-id="99d61-107">**系統標記**：目前， [優先順序帳戶](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 是唯一的系統標記類型。</span><span class="sxs-lookup"><span data-stu-id="99d61-107">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="99d61-108">**自訂標記**：您可以自行建立這些使用者標記。</span><span class="sxs-lookup"><span data-stu-id="99d61-108">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="99d61-109">如果您的組織有 Office 365 ATP 方案 2 (包含在您的訂閱中，或作為附加元件) ，除了使用 [優先順序帳戶] 標記之外，您還可以建立自訂使用者標記。</span><span class="sxs-lookup"><span data-stu-id="99d61-109">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="99d61-110">在您將系統標記或自訂標記套用至使用者後，您可以使用這些標記做為預警、報告和調查中的篩選器：</span><span class="sxs-lookup"><span data-stu-id="99d61-110">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="99d61-111">安全性 & 規範中心的警示</span><span class="sxs-lookup"><span data-stu-id="99d61-111">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="99d61-112">威脅瀏覽器和即時偵測</span><span class="sxs-lookup"><span data-stu-id="99d61-112">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="99d61-113">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="99d61-113">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="99d61-114">行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="99d61-114">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="99d61-115">本文說明如何在安全性 & 規範中心內設定使用者標記。</span><span class="sxs-lookup"><span data-stu-id="99d61-115">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="99d61-116">安全性 & 合規性中心內沒有 Cmdlet 可管理使用者標記。</span><span class="sxs-lookup"><span data-stu-id="99d61-116">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="99d61-117">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="99d61-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="99d61-118">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="99d61-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="99d61-119">若要直接移至 [ **使用者標記** ] 頁面，請開啟] <https://protection.office.com/userTags> 。</span><span class="sxs-lookup"><span data-stu-id="99d61-119">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="99d61-120">若要建立、修改或移除 **自訂使用者標記**，您必須是 Security & 合規性中心內「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="99d61-120">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="99d61-121">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="99d61-121">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="99d61-122">若要 (系統磁碟區標) 設定優先順序帳戶，您必須是 [全域系統管理員](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 或 [Exchange 系統管理員](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)。</span><span class="sxs-lookup"><span data-stu-id="99d61-122">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="99d61-123">您也可以在 Microsoft 365 admin center 中管理及監視優先順序帳戶。</span><span class="sxs-lookup"><span data-stu-id="99d61-123">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="99d61-124">如需相關指示，請參閱 [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。</span><span class="sxs-lookup"><span data-stu-id="99d61-124">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="99d61-125">使用安全中心建立使用者標記</span><span class="sxs-lookup"><span data-stu-id="99d61-125">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="99d61-126">在 [安全性中心] 中，移至 [ **威脅管理**] \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="99d61-126">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="99d61-127">在開啟的 [ **使用者標記** ] 頁面上，按一下 [ **建立標記**]。</span><span class="sxs-lookup"><span data-stu-id="99d61-127">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="99d61-128">[ **建立** 標籤] 嚮導會在新飛出時開啟。在 [ **定義標記** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="99d61-128">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="99d61-129">**名稱**：輸入標記的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="99d61-129">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="99d61-130">這是您會看到和使用的值。</span><span class="sxs-lookup"><span data-stu-id="99d61-130">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="99d61-131">**描述**：輸入標記的選用描述。</span><span class="sxs-lookup"><span data-stu-id="99d61-131">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="99d61-132">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99d61-132">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="99d61-133">在 [ **指派信箱** ] 頁面上，執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="99d61-133">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="99d61-134">按一下 [ **新增信箱**]。</span><span class="sxs-lookup"><span data-stu-id="99d61-134">Click **Add mailboxes**.</span></span> <span data-ttu-id="99d61-135">在 [飛出顯示] 中，執行下列其中一個步驟，以新增個別使用者或群組：</span><span class="sxs-lookup"><span data-stu-id="99d61-135">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="99d61-136">在方塊中按一下，然後在清單中向內移動，以選取使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="99d61-136">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="99d61-137">在方塊中按一下並輸入，以篩選清單並選取使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="99d61-137">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="99d61-138">若要新增其他值，請按一下方塊中的空白區域。</span><span class="sxs-lookup"><span data-stu-id="99d61-138">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="99d61-139">若要從方塊中移除個別專案， **Remove**請 ![ 在方塊中按一下使用者或群組上的 [移除移除圖示] ](../../media/scc-remove-icon.png) 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="99d61-139">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="99d61-140">若要從方塊下方的清單中移除現有的專案，請按一下 [ **移除** ![ 移除圖示] ](../../media/scc-remove-icon.png) 專案。</span><span class="sxs-lookup"><span data-stu-id="99d61-140">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="99d61-141">完成後，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="99d61-141">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="99d61-142">按一下 [匯 **入** ]，選取包含使用者或群組之電子郵件地址的文字檔。</span><span class="sxs-lookup"><span data-stu-id="99d61-142">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="99d61-143">請確定文字檔包含每行一個專案。</span><span class="sxs-lookup"><span data-stu-id="99d61-143">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="99d61-144">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99d61-144">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="99d61-145">在 [ **複查標記** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="99d61-145">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="99d61-146">您可以按一下 [特定] 區段中的 [ **編輯** ]，以進行變更。</span><span class="sxs-lookup"><span data-stu-id="99d61-146">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="99d61-147">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="99d61-147">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="99d61-148">使用安全中心來查看使用者標記</span><span class="sxs-lookup"><span data-stu-id="99d61-148">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="99d61-149">在 [安全性中心] 中，移至 [ **威脅管理**] \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="99d61-149">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="99d61-150">在開啟的 [ **使用者標記** ] 頁面上，選取您要查看的使用者標籤 (不要按一下核取方塊) 。</span><span class="sxs-lookup"><span data-stu-id="99d61-150">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="99d61-151">在顯示的唯讀詳細資訊飛出狀態中，複查設定。</span><span class="sxs-lookup"><span data-stu-id="99d61-151">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="99d61-152">完成時，請按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99d61-152">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="99d61-153">使用 [安全性中心] 修改使用者標記</span><span class="sxs-lookup"><span data-stu-id="99d61-153">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="99d61-154">在 [安全性中心] 中，移至 [ **威脅管理**] \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="99d61-154">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="99d61-155">在開啟的 [ **使用者標記** ] 頁面上，選取您要查看的使用者標記，然後按一下 [ **編輯標記**]。</span><span class="sxs-lookup"><span data-stu-id="99d61-155">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="99d61-156">[原則] 嚮導會在 [ **編輯] 標記** 飛出的狀態中開啟。按 **[下一步]** 以複查及修改設定。</span><span class="sxs-lookup"><span data-stu-id="99d61-156">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="99d61-157">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="99d61-157">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="99d61-158">使用安全中心來移除使用者標記</span><span class="sxs-lookup"><span data-stu-id="99d61-158">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="99d61-159">**附注**：您無法移除內建的 [ **優先順序] 帳戶** 標記。</span><span class="sxs-lookup"><span data-stu-id="99d61-159">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="99d61-160">在 [安全性中心] 中，移至 [ **威脅管理**] \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="99d61-160">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="99d61-161">在開啟的 [ **使用者標記** ] 頁面上，選取您要移除的使用者標籤，按一下 [ **刪除**標籤]，然後選取 [ **是]，** 然後在顯示的警告中移除。</span><span class="sxs-lookup"><span data-stu-id="99d61-161">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
