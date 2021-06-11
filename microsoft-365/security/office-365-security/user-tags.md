---
title: Microsoft Defender 中 Office 365 的使用者標記
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Microsoft Defender 的使用者標記中識別特定的使用者群組，以 Office 365 方案2。 標記篩選可用於 Office 365 的通知、報告和調查中，以快速識別已標記的使用者。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1fb948d63f7bc42839d6fae8a2138d4ad48d81f6
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879165"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="4f900-104">Microsoft Defender 中 Office 365 的使用者標記</span><span class="sxs-lookup"><span data-stu-id="4f900-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="4f900-105">使用者標記功能是在預覽中，並非所有人都可以使用，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="4f900-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="4f900-106">如需發行排程的相關資訊，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="4f900-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="4f900-107">使用者標記是 Microsoft Defender 中的特定使用者群組的識別碼，[以供 Office 365](defender-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="4f900-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="4f900-108">使用者標記有兩種類型：</span><span class="sxs-lookup"><span data-stu-id="4f900-108">There are two types of user tags:</span></span>

- <span data-ttu-id="4f900-109">**系統標記**：目前， [優先順序帳戶](../../admin/setup/priority-accounts.md) 是唯一的系統標記類型。</span><span class="sxs-lookup"><span data-stu-id="4f900-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="4f900-110">**自訂標記**：您可以自行建立這些使用者標記。</span><span class="sxs-lookup"><span data-stu-id="4f900-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="4f900-111">如果您的組織擁有 Office 365 方案中的 Defender， (包含在您的訂閱中或附加元件) 中，除了使用 [優先順序帳戶] 標籤之外，您還可以建立自訂使用者標記。</span><span class="sxs-lookup"><span data-stu-id="4f900-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="4f900-112">目前您只能將使用者標記套用至信箱使用者。</span><span class="sxs-lookup"><span data-stu-id="4f900-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="4f900-113">在您將系統標記或自訂標記套用至使用者後，您可以使用這些標記做為預警、報告和調查中的篩選器：</span><span class="sxs-lookup"><span data-stu-id="4f900-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="4f900-114">提醒</span><span class="sxs-lookup"><span data-stu-id="4f900-114">Alerts</span></span>](alerts.md)
- [<span data-ttu-id="4f900-115">威脅瀏覽器和即時偵測</span><span class="sxs-lookup"><span data-stu-id="4f900-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="4f900-116">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="4f900-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="4f900-117">行銷活動檢視</span><span class="sxs-lookup"><span data-stu-id="4f900-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="4f900-118">針對優先順序帳戶，您可以使用 Exchange 系統管理中心的「優先順序帳戶」報告 (EAC) 中的[電子郵件問題](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。</span><span class="sxs-lookup"><span data-stu-id="4f900-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="4f900-119">本文說明如何在 Microsoft 365 Defender 入口網站中設定使用者標記。</span><span class="sxs-lookup"><span data-stu-id="4f900-119">This article explains how to configure user tags in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="4f900-120">Microsoft 365 Defender 入口網站中沒有 Cmdlet 來管理使用者標記。</span><span class="sxs-lookup"><span data-stu-id="4f900-120">There are no cmdlets in Microsoft 365 Defender portal to manage user tags.</span></span>

<span data-ttu-id="4f900-121">若要查看使用者標記屬於策略的一部分，以協助保護高影響的使用者帳戶，請參閱[Microsoft 365 中優先順序帳戶的安全性建議](security-recommendations-for-priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="4f900-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4f900-122">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="4f900-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4f900-123">您可以在中開啟 Microsoft 365 的 Defender 入口網站 <https://security.microsoft.com/> 。</span><span class="sxs-lookup"><span data-stu-id="4f900-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="4f900-124">若要直接移至 [ **使用者標記** ] 頁面，請開啟] <https://security.microsoft.com/securitysettings/userTags> 。</span><span class="sxs-lookup"><span data-stu-id="4f900-124">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="4f900-125">您必須先在 Microsoft 365 Defender 入口網站中指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="4f900-125">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4f900-126">若要建立、修改和刪除使用者標記，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="4f900-126">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="4f900-127">若要在現有的使用者標記中新增及移除成員，您必須是「 **組織管理**」、「 **安全性管理員**」或「 **安全操作員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="4f900-127">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="4f900-128">若要唯讀的使用者標記存取權，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="4f900-128">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4f900-129">如需詳細資訊，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="4f900-129">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="4f900-130">將使用者新增至 Microsoft 365 admin center 中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="4f900-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4f900-131">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="4f900-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="4f900-132">使用者標記管理是由「 **標記讀取器** 」和「標籤 **管理員** 」角色所控制。</span><span class="sxs-lookup"><span data-stu-id="4f900-132">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="4f900-133">您也可以在 Microsoft 365 系統管理中心管理及監視優先順序帳戶。</span><span class="sxs-lookup"><span data-stu-id="4f900-133">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4f900-134">如需相關指示，請參閱 [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="4f900-134">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="4f900-135">如需 (系統管理員帳戶) 保護 _特權帳戶_ 的詳細資訊，請參閱 [本主題](/azure/architecture/framework/security/critical-impact-accounts)。</span><span class="sxs-lookup"><span data-stu-id="4f900-135">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a><span data-ttu-id="4f900-136">使用 Microsoft 365 Defender 入口網站建立使用者標記</span><span class="sxs-lookup"><span data-stu-id="4f900-136">Use the Microsoft 365 Defender portal to create user tags</span></span>

1. <span data-ttu-id="4f900-137">在 Microsoft 365 Defender 入口網站中，移至 **設定** \> **電子郵件 &** 共同作業 \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="4f900-137">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="4f900-138">在 [ **使用者標記** ] 頁面上，按一下 [ ![ 建立標記圖示 ](../../media/m365-cc-sc-create-icon.png) **建立標記**]。</span><span class="sxs-lookup"><span data-stu-id="4f900-138">On the **User tags** page, click ![Create tag icon](../../media/m365-cc-sc-create-icon.png) **Create tag**.</span></span>

3. <span data-ttu-id="4f900-139">[ **建立** 標籤] 嚮導會在新飛入的視窗中開啟。</span><span class="sxs-lookup"><span data-stu-id="4f900-139">The **Create tag** wizard opens in a new flyout.</span></span> <span data-ttu-id="4f900-140">在 [ **定義標記** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="4f900-140">On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="4f900-141">**名稱**：輸入標記的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="4f900-141">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="4f900-142">這是您會看到和使用的值。</span><span class="sxs-lookup"><span data-stu-id="4f900-142">This is the value that you'll see and use.</span></span> <span data-ttu-id="4f900-143">請注意，您在建立標記之後，您無法將其重新命名。</span><span class="sxs-lookup"><span data-stu-id="4f900-143">Note that you can't rename a tag after you create it.</span></span>
   - <span data-ttu-id="4f900-144">**描述**：輸入標記的選用描述。</span><span class="sxs-lookup"><span data-stu-id="4f900-144">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="4f900-145">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="4f900-145">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="4f900-146">在 [ **指派成員** ] 頁面上，執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="4f900-146">On the **Assign members** page, do either of the following steps:</span></span>
   - <span data-ttu-id="4f900-147">按一下 [ ![ 新增成員] 圖示 [ ](../../media/m365-cc-sc-create-icon.png) **新增成員**]。</span><span class="sxs-lookup"><span data-stu-id="4f900-147">Click ![Add members icon](../../media/m365-cc-sc-create-icon.png) **Add members**.</span></span> <span data-ttu-id="4f900-148">在 [飛出顯示] 中，執行下列其中一個步驟，以新增個別使用者或群組：</span><span class="sxs-lookup"><span data-stu-id="4f900-148">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="4f900-149">在方塊中按一下，然後在清單中向內移動，以選取使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="4f900-149">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="4f900-150">在方塊中按一下並輸入，以篩選清單並選取使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="4f900-150">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="4f900-151">若要新增其他值，請按一下方塊中的空白區域。</span><span class="sxs-lookup"><span data-stu-id="4f900-151">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="4f900-152">若要移除個別專案，請按一下</span><span class="sxs-lookup"><span data-stu-id="4f900-152">To remove individual entries, click</span></span> ![移除專案圖示](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="4f900-154">方塊中的條目旁邊。</span><span class="sxs-lookup"><span data-stu-id="4f900-154">next to the entry in the box.</span></span>
     - <span data-ttu-id="4f900-155">若要移除所有專案，請按一下方塊 ![ ](../../media/m365-cc-sc-remove-selection-icon.png) 上 **所選 nn 使用者和 nn 群組** 專案上的 [移除專案圖示]。</span><span class="sxs-lookup"><span data-stu-id="4f900-155">To remove all entries, click ![Remove entry icon](../../media/m365-cc-sc-remove-selection-icon.png) on the **Selected nn users and nn groups** item below the box.</span></span>

     <span data-ttu-id="4f900-156">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="4f900-156">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="4f900-157">回到 [ **指派成員** ] 頁面上，您也可以按一下 ![ 專案旁邊的 [刪除圖示] 來移除專案 ](../../media/m365-cc-sc-delete-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="4f900-157">Back on the **Assign members** page, you can also remove entries by clicking ![Delete icon](../../media/m365-cc-sc-delete-icon.png) next to the entry.</span></span>

   - <span data-ttu-id="4f900-158">按一下 [匯 **入** ]，選取包含使用者或群組之電子郵件地址的文字檔。</span><span class="sxs-lookup"><span data-stu-id="4f900-158">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="4f900-159">請確定文字檔包含每行一個專案。</span><span class="sxs-lookup"><span data-stu-id="4f900-159">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="4f900-160">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="4f900-160">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="4f900-161">在出現的 [ **複查標記** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="4f900-161">On the **Review tag** page that appears, review your settings.</span></span> <span data-ttu-id="4f900-162">您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="4f900-162">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="4f900-163">或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。</span><span class="sxs-lookup"><span data-stu-id="4f900-163">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="4f900-164">完成後，請按一下 [ **提交**]，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="4f900-164">When you're finished, click **Submit**, and then click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a><span data-ttu-id="4f900-165">使用 Microsoft 365 Defender 入口網站來查看使用者標記</span><span class="sxs-lookup"><span data-stu-id="4f900-165">Use the Microsoft 365 Defender portal to view user tags</span></span>

1. <span data-ttu-id="4f900-166">在 Microsoft 365 Defender 入口網站中，移至 **設定** \> **電子郵件 &** 共同作業 \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="4f900-166">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="4f900-167">在 [ **使用者標記** ] 頁面上，下列屬性會顯示在使用者標記清單中：</span><span class="sxs-lookup"><span data-stu-id="4f900-167">On the **User tags** page, the following properties are displayed in the list of user tags:</span></span>

   - <span data-ttu-id="4f900-168">**Tag**： user 標記的名稱。</span><span class="sxs-lookup"><span data-stu-id="4f900-168">**Tag**: The name of the user tag.</span></span> <span data-ttu-id="4f900-169">請注意，這包括內建的 **優先順序帳戶** 系統標記。</span><span class="sxs-lookup"><span data-stu-id="4f900-169">Note that this includes the built-in **Priority account** system tag.</span></span>
   - <span data-ttu-id="4f900-170">**適用** 于：成員數目</span><span class="sxs-lookup"><span data-stu-id="4f900-170">**Applied to**: The number of members</span></span>
   - <span data-ttu-id="4f900-171">**上次修改日期**</span><span class="sxs-lookup"><span data-stu-id="4f900-171">**Last modified**</span></span>
   - <span data-ttu-id="4f900-172">**建立于**</span><span class="sxs-lookup"><span data-stu-id="4f900-172">**Created on**</span></span>

3. <span data-ttu-id="4f900-173">當您按一下名稱來選取使用者標記時，詳細資料會顯示在浮出控制項中。</span><span class="sxs-lookup"><span data-stu-id="4f900-173">When you select a user tag by clicking on the name, the details are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a><span data-ttu-id="4f900-174">使用 Microsoft 365 Defender 入口網站修改使用者標記</span><span class="sxs-lookup"><span data-stu-id="4f900-174">Use the Microsoft 365 Defender portal to modify user tags</span></span>

1. <span data-ttu-id="4f900-175">在 Microsoft 365 Defender 入口網站中，移至 **設定** \> **電子郵件 &** 共同作業 \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="4f900-175">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="4f900-176">在 [ **使用者標記** ] 頁面上，選取清單中的 [使用者] 標籤，然後按一下 [ ![ 編輯標記圖示] [ ](../../media/m365-cc-sc-edit-icon.png) **編輯標記**]。</span><span class="sxs-lookup"><span data-stu-id="4f900-176">On the **User tags** page, select the user tag from the list, and then click ![Edit tag icon](../../media/m365-cc-sc-edit-icon.png) **Edit tag**.</span></span>

3. <span data-ttu-id="4f900-177">在出現的 [詳細資料] 浮出控制項中，如本文稍早[使用 Microsoft 365 Defender 入口網站來建立使用者標記](#use-the-microsoft-365-defender-portal-to-create-user-tags)一節所述，可提供相同的嚮導和設定。</span><span class="sxs-lookup"><span data-stu-id="4f900-177">In the details flyout that appears, the same wizard and settings are available as described in the [Use the Microsoft 365 Defender portal to create user tags](#use-the-microsoft-365-defender-portal-to-create-user-tags) section earlier in this article.</span></span>

   <span data-ttu-id="4f900-178">**附註**：</span><span class="sxs-lookup"><span data-stu-id="4f900-178">**Notes**:</span></span>

   - <span data-ttu-id="4f900-179">[ **定義** 標籤] 頁面不適用於內建的「 **優先順序帳戶** 」系統磁碟區標，所以您無法重新命名此標記或變更描述。</span><span class="sxs-lookup"><span data-stu-id="4f900-179">The **Define tag** page is not available for the built-in **Priority account** system tag, so you can't rename this tag or change the description.</span></span>
   - <span data-ttu-id="4f900-180">您無法重新命名自訂標記，但您可以變更描述。</span><span class="sxs-lookup"><span data-stu-id="4f900-180">You can't rename a custom tag, but you can change the description.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a><span data-ttu-id="4f900-181">使用 Microsoft 365 Defender 入口網站來移除使用者標記</span><span class="sxs-lookup"><span data-stu-id="4f900-181">Use the Microsoft 365 Defender portal to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="4f900-182">您無法移除內建的 [ **優先順序帳戶** 系統] 標記。</span><span class="sxs-lookup"><span data-stu-id="4f900-182">You can't remove the built-in **Priority account** system tag.</span></span>

1. <span data-ttu-id="4f900-183">在 Microsoft 365 Defender 入口網站中，移至 **設定** \> **電子郵件 &** 共同作業 \> **使用者標記**。</span><span class="sxs-lookup"><span data-stu-id="4f900-183">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="4f900-184">在 [ **使用者標記** ] 頁面上，從清單中選取 [使用者] 標籤，然後按一下 [ ![ 刪除標記圖示] [ ](../../media/m365-cc-sc-delete-icon.png) **刪除** 標籤]。</span><span class="sxs-lookup"><span data-stu-id="4f900-184">On the **User tags** page, select the user tag from the list, and then click ![Delete tag icon](../../media/m365-cc-sc-delete-icon.png) **Delete tag**.</span></span>

3. <span data-ttu-id="4f900-185">閱讀出現的確認對話方塊中的警告，然後按一下 [ **是]，[移除**]。</span><span class="sxs-lookup"><span data-stu-id="4f900-185">Read the warning in the confirmation dialog that appears, and then click **Yes, remove**.</span></span>
