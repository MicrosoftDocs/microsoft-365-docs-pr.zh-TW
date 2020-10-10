---
title: Office 365 ATP 中的使用者標籤
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
ms.openlocfilehash: 475bf976a71fb688df8db9ac25f3b397c078d79a
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417272"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="15b8d-104">Office 365 ATP 中的使用者標籤</span><span class="sxs-lookup"><span data-stu-id="15b8d-104">User tags in Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="15b8d-105">使用者標記功能是在預覽中，並非所有人都可以使用，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="15b8d-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="15b8d-106">如需發行排程的相關資訊，請參閱 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="15b8d-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="15b8d-107">使用者標記是 [Office 365 Advanced 威脅防護 (ATP) ](office-365-atp.md)中的特定使用者群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="15b8d-107">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="15b8d-108">使用者標記有兩種類型：</span><span class="sxs-lookup"><span data-stu-id="15b8d-108">There are two types of user tags:</span></span>

- <span data-ttu-id="15b8d-109">**系統標記**：目前， [優先順序帳戶](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 是唯一的系統標記類型。</span><span class="sxs-lookup"><span data-stu-id="15b8d-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="15b8d-110">**自訂標記**：您可以自行建立這些使用者標記。</span><span class="sxs-lookup"><span data-stu-id="15b8d-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="15b8d-111">如果您的組織有 Office 365 ATP 方案 2 (包含在您的訂閱中，或作為附加元件) ，除了使用 [優先順序帳戶] 標記之外，您還可以建立自訂使用者標記。</span><span class="sxs-lookup"><span data-stu-id="15b8d-111">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="15b8d-112">在您將系統標記或自訂標記套用至使用者後，您可以使用這些標記做為預警、報告和調查中的篩選器：</span><span class="sxs-lookup"><span data-stu-id="15b8d-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="15b8d-113">安全性 & 規範中心的警示</span><span class="sxs-lookup"><span data-stu-id="15b8d-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="15b8d-114">威脅瀏覽器和即時偵測</span><span class="sxs-lookup"><span data-stu-id="15b8d-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="15b8d-115">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="15b8d-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="15b8d-116">行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="15b8d-116">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="15b8d-117">本文說明如何在安全性 & 規範中心內設定使用者標記。</span><span class="sxs-lookup"><span data-stu-id="15b8d-117">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="15b8d-118">安全性 & 合規性中心內沒有 Cmdlet 可管理使用者標記。</span><span class="sxs-lookup"><span data-stu-id="15b8d-118">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="15b8d-119">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="15b8d-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="15b8d-120">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="15b8d-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="15b8d-121">若要直接移至 [ **使用者標記** ] 頁面，請開啟] <https://protection.office.com/userTags> 。</span><span class="sxs-lookup"><span data-stu-id="15b8d-121">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="15b8d-122">若要建立、修改或移除 **自訂使用者標記**，您必須是 Security & 合規性中心內「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="15b8d-122">To create, modify, or remove **custom user tags**, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="15b8d-123">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="15b8d-123">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="15b8d-124">若要 (系統磁碟區標) 設定優先順序帳戶，您必須是 [全域系統管理員](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 或 [Exchange 系統管理員](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)。</span><span class="sxs-lookup"><span data-stu-id="15b8d-124">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="15b8d-125">您也可以在 Microsoft 365 admin center 中管理及監視優先順序帳戶。</span><span class="sxs-lookup"><span data-stu-id="15b8d-125">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="15b8d-126">如需相關指示，請參閱 [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。</span><span class="sxs-lookup"><span data-stu-id="15b8d-126">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="15b8d-127">使用安全中心建立使用者標記</span><span class="sxs-lookup"><span data-stu-id="15b8d-127">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="15b8d-128">在 [安全性中心] 中，移至 [ **威脅管理**] \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="15b8d-128">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="15b8d-129">在開啟的 [ **使用者標記** ] 頁面上，按一下 [ **建立標記**]。</span><span class="sxs-lookup"><span data-stu-id="15b8d-129">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="15b8d-130">[ **建立** 標籤] 嚮導會在新飛出時開啟。在 [ **定義標記** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="15b8d-130">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="15b8d-131">**名稱**：輸入標記的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="15b8d-131">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="15b8d-132">這是您會看到和使用的值。</span><span class="sxs-lookup"><span data-stu-id="15b8d-132">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="15b8d-133">**描述**：輸入標記的選用描述。</span><span class="sxs-lookup"><span data-stu-id="15b8d-133">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="15b8d-134">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="15b8d-134">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="15b8d-135">在 [ **指派信箱** ] 頁面上，執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="15b8d-135">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="15b8d-136">按一下 [ **新增信箱**]。</span><span class="sxs-lookup"><span data-stu-id="15b8d-136">Click **Add mailboxes**.</span></span> <span data-ttu-id="15b8d-137">在 [飛出顯示] 中，執行下列其中一個步驟，以新增個別使用者或群組：</span><span class="sxs-lookup"><span data-stu-id="15b8d-137">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="15b8d-138">在方塊中按一下，然後在清單中向內移動，以選取使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="15b8d-138">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="15b8d-139">在方塊中按一下並輸入，以篩選清單並選取使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="15b8d-139">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="15b8d-140">若要新增其他值，請按一下方塊中的空白區域。</span><span class="sxs-lookup"><span data-stu-id="15b8d-140">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="15b8d-141">若要從方塊中移除個別專案， **Remove**請 ![ 在方塊中按一下使用者或群組上的 [移除移除圖示] ](../../media/scc-remove-icon.png) 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="15b8d-141">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="15b8d-142">若要從方塊下方的清單中移除現有的專案，請按一下 [ **移除** ![ 移除圖示] ](../../media/scc-remove-icon.png) 專案。</span><span class="sxs-lookup"><span data-stu-id="15b8d-142">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="15b8d-143">完成後，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="15b8d-143">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="15b8d-144">按一下 [匯 **入** ]，選取包含使用者或群組之電子郵件地址的文字檔。</span><span class="sxs-lookup"><span data-stu-id="15b8d-144">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="15b8d-145">請確定文字檔包含每行一個專案。</span><span class="sxs-lookup"><span data-stu-id="15b8d-145">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="15b8d-146">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="15b8d-146">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="15b8d-147">在 [ **複查標記** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="15b8d-147">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="15b8d-148">您可以按一下 [特定] 區段中的 [ **編輯** ]，以進行變更。</span><span class="sxs-lookup"><span data-stu-id="15b8d-148">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="15b8d-149">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="15b8d-149">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="15b8d-150">使用安全中心來查看使用者標記</span><span class="sxs-lookup"><span data-stu-id="15b8d-150">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="15b8d-151">在 [安全性中心] 中，移至 [ **威脅管理**] \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="15b8d-151">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="15b8d-152">在開啟的 [ **使用者標記** ] 頁面上，選取您要查看的使用者標籤 (不要按一下核取方塊) 。</span><span class="sxs-lookup"><span data-stu-id="15b8d-152">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="15b8d-153">在顯示的唯讀詳細資訊飛出狀態中，複查設定。</span><span class="sxs-lookup"><span data-stu-id="15b8d-153">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="15b8d-154">完成時，請按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="15b8d-154">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="15b8d-155">使用 [安全性中心] 修改使用者標記</span><span class="sxs-lookup"><span data-stu-id="15b8d-155">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="15b8d-156">在 [安全性中心] 中，移至 [ **威脅管理**] \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="15b8d-156">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="15b8d-157">在開啟的 [ **使用者標記** ] 頁面上，選取您要查看的使用者標記，然後按一下 [ **編輯標記**]。</span><span class="sxs-lookup"><span data-stu-id="15b8d-157">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="15b8d-158">[原則] 嚮導會在 [ **編輯] 標記** 飛出的狀態中開啟。按 **[下一步]** 以複查及修改設定。</span><span class="sxs-lookup"><span data-stu-id="15b8d-158">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="15b8d-159">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="15b8d-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="15b8d-160">使用安全中心來移除使用者標記</span><span class="sxs-lookup"><span data-stu-id="15b8d-160">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="15b8d-161">**附注**：您無法移除內建的 [ **優先順序] 帳戶** 標記。</span><span class="sxs-lookup"><span data-stu-id="15b8d-161">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="15b8d-162">在 [安全性中心] 中，移至 [ **威脅管理**] \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="15b8d-162">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="15b8d-163">在開啟的 [ **使用者標記** ] 頁面上，選取您要移除的使用者標籤，按一下 [ **刪除**標籤]，然後選取 [ **是]，** 然後在顯示的警告中移除。</span><span class="sxs-lookup"><span data-stu-id="15b8d-163">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
