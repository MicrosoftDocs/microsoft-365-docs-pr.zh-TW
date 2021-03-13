---
title: Microsoft Defender for Office 365 中的使用者標記
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Microsoft Defender for Office 365 方案2中識別具有使用者標記的特定使用者群組。 標記篩選可用於 Office 365 的 Microsoft Defender 中的提醒、報告和調查，以快速識別已標記的使用者。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80bd360888be3aeea42da6f9b58a119a9752d382
ms.sourcegitcommit: bf9e0091e5bdc78d9b23be64583eb816bb059eb2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2021
ms.locfileid: "50758889"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="d97b9-104">Microsoft Defender for Office 365 中的使用者標記</span><span class="sxs-lookup"><span data-stu-id="d97b9-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="d97b9-105">使用者標記功能是在預覽中，並非所有人都可以使用，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="d97b9-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="d97b9-106">如需發行排程的相關資訊，請參閱 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="d97b9-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="d97b9-107">使用者標記是 [Microsoft Defender For Office 365](office-365-atp.md)中特定使用者群組的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d97b9-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="d97b9-108">使用者標記有兩種類型：</span><span class="sxs-lookup"><span data-stu-id="d97b9-108">There are two types of user tags:</span></span>

- <span data-ttu-id="d97b9-109">**系統標記**：目前， [優先順序帳戶](../../admin/setup/priority-accounts.md) 是唯一的系統標記類型。</span><span class="sxs-lookup"><span data-stu-id="d97b9-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="d97b9-110">**自訂標記**：您可以自行建立這些使用者標記。</span><span class="sxs-lookup"><span data-stu-id="d97b9-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="d97b9-111">如果您的組織擁有 Office 365 的 Defender for Office 方案 2 (包含在您的訂閱中或作為附加元件) ，除了使用 [優先順序帳戶] 標記之外，您還可以建立自訂使用者標記。</span><span class="sxs-lookup"><span data-stu-id="d97b9-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="d97b9-112">在您將系統標記或自訂標記套用至使用者後，您可以使用這些標記做為預警、報告和調查中的篩選器：</span><span class="sxs-lookup"><span data-stu-id="d97b9-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="d97b9-113">安全性 & 規範中心的警示</span><span class="sxs-lookup"><span data-stu-id="d97b9-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="d97b9-114">威脅瀏覽器和即時偵測</span><span class="sxs-lookup"><span data-stu-id="d97b9-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="d97b9-115">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="d97b9-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="d97b9-116">行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="d97b9-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="d97b9-117">針對優先順序帳戶，您可以使用 Exchange 系統管理中心的 [優先順序帳戶] 報告 (EAC) 中的 [電子郵件問題](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) 。</span><span class="sxs-lookup"><span data-stu-id="d97b9-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="d97b9-118">本文說明如何在安全性 & 規範中心內設定使用者標記。</span><span class="sxs-lookup"><span data-stu-id="d97b9-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="d97b9-119">安全性 & 合規性中心內沒有 Cmdlet 可管理使用者標記。</span><span class="sxs-lookup"><span data-stu-id="d97b9-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

<span data-ttu-id="d97b9-120">若要查看使用者標記屬於策略的一部分，以協助保護高影響的使用者帳戶，請參閱 [Microsoft 365 中優先順序帳戶的安全性建議](security-recommendations-for-priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="d97b9-120">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d97b9-121">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="d97b9-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d97b9-122">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="d97b9-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d97b9-123">若要直接移至 [ **使用者標記** ] 頁面，請開啟] <https://protection.office.com/userTags> 。</span><span class="sxs-lookup"><span data-stu-id="d97b9-123">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="d97b9-124">您必須先獲得 [安全性與合規性中心] 指派的權限，才能使用此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="d97b9-124">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d97b9-125">若要建立、修改和刪除使用者標記，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d97b9-125">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="d97b9-126">若要在現有的使用者標記中新增及移除成員，您必須是「 **組織管理**」、「 **安全性管理員**」或「 **安全操作員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d97b9-126">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="d97b9-127">若要唯讀的使用者標記存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d97b9-127">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="d97b9-128">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d97b9-128">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="d97b9-129">**附註**：</span><span class="sxs-lookup"><span data-stu-id="d97b9-129">**Notes**:</span></span>

  - <span data-ttu-id="d97b9-130">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="d97b9-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d97b9-131">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="d97b9-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="d97b9-132">使用者標記管理是由「 **標記讀取器** 」和「標籤 **管理員** 」角色所控制。</span><span class="sxs-lookup"><span data-stu-id="d97b9-132">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="d97b9-133">您也可以在 Microsoft 365 admin center 中管理及監視優先順序帳戶。</span><span class="sxs-lookup"><span data-stu-id="d97b9-133">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d97b9-134">如需相關指示，請參閱 [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="d97b9-134">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-user-tags"></a><span data-ttu-id="d97b9-135">使用安全性 & 規範中心建立使用者標記</span><span class="sxs-lookup"><span data-stu-id="d97b9-135">Use the Security & Compliance Center to create user tags</span></span>

1. <span data-ttu-id="d97b9-136">在 [安全性 & 規範中心] 中，移至 [ **威脅管理**] \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="d97b9-136">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d97b9-137">在開啟的 [ **使用者標記** ] 頁面上，按一下 [ **建立標記**]。</span><span class="sxs-lookup"><span data-stu-id="d97b9-137">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="d97b9-138">[ **建立** 標籤] 嚮導會在新飛出時開啟。在 [ **定義標記** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="d97b9-138">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="d97b9-139">**名稱**：輸入標記的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="d97b9-139">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="d97b9-140">這是您會看到和使用的值。</span><span class="sxs-lookup"><span data-stu-id="d97b9-140">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="d97b9-141">**描述**：輸入標記的選用描述。</span><span class="sxs-lookup"><span data-stu-id="d97b9-141">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="d97b9-142">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="d97b9-142">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d97b9-143">在 [ **指派使用者** ] 頁面上，執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="d97b9-143">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="d97b9-144">按一下 [ **新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="d97b9-144">Click **Add users**.</span></span> <span data-ttu-id="d97b9-145">在 [飛出顯示] 中，執行下列其中一個步驟，以新增個別使用者或群組：</span><span class="sxs-lookup"><span data-stu-id="d97b9-145">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="d97b9-146">在方塊中按一下，然後在清單中向內移動，以選取使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="d97b9-146">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="d97b9-147">在方塊中按一下並輸入，以篩選清單並選取使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="d97b9-147">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="d97b9-148">若要新增其他值，請按一下方塊中的空白區域。</span><span class="sxs-lookup"><span data-stu-id="d97b9-148">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="d97b9-149">若要從方塊中移除個別專案， 請 ![ 在方塊中按一下使用者或群組上的 [移除移除圖示] ](../../media/scc-remove-icon.png) 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d97b9-149">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="d97b9-150">若要從方塊下方的清單中移除現有的專案，請按一下 [ **移除** ![ 移除圖示] ](../../media/scc-remove-icon.png) 專案。</span><span class="sxs-lookup"><span data-stu-id="d97b9-150">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="d97b9-151">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="d97b9-151">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="d97b9-152">按一下 [匯 **入** ]，選取包含使用者或群組之電子郵件地址的文字檔。</span><span class="sxs-lookup"><span data-stu-id="d97b9-152">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="d97b9-153">請確定文字檔包含每行一個專案。</span><span class="sxs-lookup"><span data-stu-id="d97b9-153">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="d97b9-154">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="d97b9-154">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d97b9-155">在 [ **複查標記** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="d97b9-155">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="d97b9-156">您可以按一下 [特定] 區段中的 [ **編輯** ]，以進行變更。</span><span class="sxs-lookup"><span data-stu-id="d97b9-156">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="d97b9-157">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="d97b9-157">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-view-user-tags"></a><span data-ttu-id="d97b9-158">使用安全性 & 規範中心來查看使用者標記</span><span class="sxs-lookup"><span data-stu-id="d97b9-158">Use the Security & Compliance Center to view user tags</span></span>

1. <span data-ttu-id="d97b9-159">在 [安全性 & 規範中心] 中，移至 [ **威脅管理**] \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="d97b9-159">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d97b9-160">在開啟的 [ **使用者標記** ] 頁面上，選取您要查看的使用者標籤 (不要按一下核取方塊) 。</span><span class="sxs-lookup"><span data-stu-id="d97b9-160">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="d97b9-161">在顯示的唯讀詳細資訊飛出狀態中，複查設定。</span><span class="sxs-lookup"><span data-stu-id="d97b9-161">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="d97b9-162">完成時，請按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="d97b9-162">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a><span data-ttu-id="d97b9-163">使用安全性 & 規範中心來修改使用者標記</span><span class="sxs-lookup"><span data-stu-id="d97b9-163">Use the Security & Compliance Center to modify user tags</span></span>

1. <span data-ttu-id="d97b9-164">在 [安全性 & 規範中心] 中，移至 [ **威脅管理**] \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="d97b9-164">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d97b9-165">在開啟的 [ **使用者標記** ] 頁面上，選取您要查看的使用者標記，然後按一下 [ **編輯標記**]。</span><span class="sxs-lookup"><span data-stu-id="d97b9-165">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="d97b9-166">[原則] 嚮導會在 [ **編輯] 標記** 飛出的狀態中開啟。按 **[下一步]** 以複查及修改設定。</span><span class="sxs-lookup"><span data-stu-id="d97b9-166">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="d97b9-167">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="d97b9-167">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a><span data-ttu-id="d97b9-168">使用安全性 & 規範中心移除使用者標記</span><span class="sxs-lookup"><span data-stu-id="d97b9-168">Use the Security & Compliance Center to remove user tags</span></span>

<span data-ttu-id="d97b9-169">**附注**：您無法移除內建的 [ **優先順序] 帳戶** 標記。</span><span class="sxs-lookup"><span data-stu-id="d97b9-169">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="d97b9-170">在 [安全性 & 規範中心] 中，移至 [ **威脅管理**] \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="d97b9-170">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d97b9-171">在開啟的 [ **使用者標記** ] 頁面上，選取您要移除的使用者標籤，按一下 [ **刪除** 標籤]，然後選取 [ **是]，** 然後在顯示的警告中移除。</span><span class="sxs-lookup"><span data-stu-id="d97b9-171">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
