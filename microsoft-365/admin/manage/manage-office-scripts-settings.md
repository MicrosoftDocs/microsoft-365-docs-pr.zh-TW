---
title: 管理 [Office 指令碼] 設定
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 瞭解如何管理組織中使用者的 Office 腳本設定。
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058420"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="759c3-103">管理 [Office 指令碼] 設定</span><span class="sxs-lookup"><span data-stu-id="759c3-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="759c3-104">Office 腳本可讓使用者在網頁上的 Excel 中錄製、編輯和執行腳本，以自動化工作。</span><span class="sxs-lookup"><span data-stu-id="759c3-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="759c3-105">Office 腳本可搭配電源自動運作，而且使用者可以使用 Excel Online (商務) 連接器，在活頁簿上執行腳本。</span><span class="sxs-lookup"><span data-stu-id="759c3-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="759c3-106">Microsoft 365 系統管理員可以從 Microsoft 365 系統管理中心管理 Office 腳本設定。</span><span class="sxs-lookup"><span data-stu-id="759c3-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="759c3-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="759c3-107">Before you begin</span></span>

- <span data-ttu-id="759c3-108">若要管理 Office 腳本設定，您必須是全域系統管理員。如需詳細資訊，請參閱 [關於系統管理員角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="759c3-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="759c3-109">請確定貴組織中的使用者擁有有效的 Microsoft 365 或 Office 365 商業版或 EDU 方案授權，其中包含 Office 桌面應用程式的存取權，例如下列其中一個計畫：</span><span class="sxs-lookup"><span data-stu-id="759c3-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="759c3-110">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="759c3-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="759c3-111">Microsoft 365 Apps 商務版</span><span class="sxs-lookup"><span data-stu-id="759c3-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="759c3-112">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="759c3-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="759c3-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="759c3-113">Office 365 E3</span></span>
    - <span data-ttu-id="759c3-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="759c3-114">Office 365 E5</span></span>
    - <span data-ttu-id="759c3-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="759c3-115">Office 365 A3</span></span>
    - <span data-ttu-id="759c3-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="759c3-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="759c3-117">管理 Office 腳本及腳本的共用可用性</span><span class="sxs-lookup"><span data-stu-id="759c3-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="759c3-118">在 Microsoft 365 系統管理中心中，移至 [ **設定** \> **組織設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服務</a> ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="759c3-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="759c3-119">選取 [ **Office 腳本**]。</span><span class="sxs-lookup"><span data-stu-id="759c3-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="759c3-120">Office 腳本預設為開啟狀態，您組織中的每個人都可以存取和使用該功能及共用腳本。</span><span class="sxs-lookup"><span data-stu-id="759c3-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="759c3-121">若要關閉組織的 Office 腳本，請清除 [ **讓使用者能在 web 上的 Excel 中自動執行其工作** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="759c3-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="759c3-122">如果您先前已關閉組織的 Office 腳本，且想要將其重新開啟，請選取 **[讓使用者能在網頁上自動使用 Excel** 的工作]，然後指定誰可以存取和使用該功能：</span><span class="sxs-lookup"><span data-stu-id="759c3-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="759c3-123">若要讓組織中的所有使用者都能存取及使用 Office 腳本，請將 **每個人** () 選取的預設值。</span><span class="sxs-lookup"><span data-stu-id="759c3-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="759c3-124">若只要允許特定群組的成員存取及使用 Office 腳本，請選取 [ **特定群組**]，然後輸入群組的名稱或電子郵件別名，以將其新增至 [允許] 清單。</span><span class="sxs-lookup"><span data-stu-id="759c3-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="759c3-125">您可以只將一個群組新增至允許清單，而且必須是下列其中一個類型：</span><span class="sxs-lookup"><span data-stu-id="759c3-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="759c3-126">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="759c3-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="759c3-127">通訊群組</span><span class="sxs-lookup"><span data-stu-id="759c3-127">Distribution group</span></span>
        - <span data-ttu-id="759c3-128">安全性群組</span><span class="sxs-lookup"><span data-stu-id="759c3-128">Security group</span></span>
        - <span data-ttu-id="759c3-129">擁有郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="759c3-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="759c3-130">若要深入瞭解不同類型的群組，請參閱 [比較群組](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="759c3-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="759c3-131">若要讓能夠存取 Office 腳本的使用者與組織中的其他人共用其腳本，請選取 **[讓有權存取 Office 腳本的使用者能夠與組織中的其他人共用其腳本**。</span><span class="sxs-lookup"><span data-stu-id="759c3-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="759c3-132">不允許在組織外共用腳本。</span><span class="sxs-lookup"><span data-stu-id="759c3-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="759c3-133">如果您稍後關閉組織的腳本共用，使用者仍可以執行先前共用的腳本。</span><span class="sxs-lookup"><span data-stu-id="759c3-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="759c3-134">指定可以存取 Office 腳本的使用者可以共用其腳本：</span><span class="sxs-lookup"><span data-stu-id="759c3-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="759c3-135">若要讓所有擁有 Office 腳本存取權的使用者都能共用其腳本，請將 **每個人** () 選取的預設值。</span><span class="sxs-lookup"><span data-stu-id="759c3-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="759c3-136">若只要允許特定群組的成員存取 Office 腳本以共用其腳本，請選取 [ **特定群組**]，然後輸入群組的名稱或電子郵件別名，以將其新增至 [允許] 清單。</span><span class="sxs-lookup"><span data-stu-id="759c3-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="759c3-137">您可以只將一個群組新增至允許清單，而且必須是下列其中一個類型：</span><span class="sxs-lookup"><span data-stu-id="759c3-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="759c3-138">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="759c3-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="759c3-139">通訊群組</span><span class="sxs-lookup"><span data-stu-id="759c3-139">Distribution group</span></span>
        - <span data-ttu-id="759c3-140">安全性群組</span><span class="sxs-lookup"><span data-stu-id="759c3-140">Security group</span></span>
        - <span data-ttu-id="759c3-141">擁有郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="759c3-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="759c3-142">若要深入瞭解不同類型的群組，請參閱 [比較群組](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="759c3-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="759c3-143">若要允許使用者在電源自動化流程內執行其 Office 腳本，請選取 [ **讓具有 Office 腳本存取權的使用者可以使用 Power 自動化執行其腳本**。</span><span class="sxs-lookup"><span data-stu-id="759c3-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="759c3-144">這可讓使用者使用 [Excel Online (商務) 連接器的](/connectors/excelonlinebusiness)[ **執行腳本** ] 選項來新增流程步驟。</span><span class="sxs-lookup"><span data-stu-id="759c3-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="759c3-145">若要讓所有具備 Office 腳本存取權的使用者都能使用流程中的腳本，請將 **每個人** () 選取的預設值。</span><span class="sxs-lookup"><span data-stu-id="759c3-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="759c3-146">若要允許只有特定群組的成員可以存取 Office 腳本，以在流程中使用腳本，請選取 [ **特定群組**]，然後輸入群組的名稱或電子郵件別名，以將其新增至 [允許] 清單。</span><span class="sxs-lookup"><span data-stu-id="759c3-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="759c3-147">您可以只將一個群組新增至允許清單，而且必須是下列其中一個類型：</span><span class="sxs-lookup"><span data-stu-id="759c3-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="759c3-148">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="759c3-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="759c3-149">通訊群組</span><span class="sxs-lookup"><span data-stu-id="759c3-149">Distribution group</span></span>
        - <span data-ttu-id="759c3-150">安全性群組</span><span class="sxs-lookup"><span data-stu-id="759c3-150">Security group</span></span>
        - <span data-ttu-id="759c3-151">擁有郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="759c3-151">Mail-enabled security group</span></span>

        <span data-ttu-id="759c3-152">若要深入瞭解不同類型的群組，請參閱 [比較群組](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="759c3-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="759c3-153">若要深入瞭解使用 Office 腳本搭配電源自動化（包括資料遺失防護原則可能受到影響的方式），請參閱 [使用 Power Run 執行 Office 腳本](/office/dev/scripts/develop/power-automate-integration)。</span><span class="sxs-lookup"><span data-stu-id="759c3-153">To learn more about using Office Scripts with Power Automate, including how your data loss prevention policies may be impacted, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="759c3-154">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="759c3-154">Select **Save**.</span></span>

    <span data-ttu-id="759c3-155">[！注意] Office 腳本設定所做的變更可能需要長達48小時才能生效。</span><span class="sxs-lookup"><span data-stu-id="759c3-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="759c3-156">後續步驟</span><span class="sxs-lookup"><span data-stu-id="759c3-156">Next steps</span></span>

<span data-ttu-id="759c3-157">由於 Office 腳本可搭配電源自動化運作，因此建議您複查現有的資料遺失防護 (DLP) 原則，以確保當使用者使用 Office 腳本時，組織的資料仍保持受保護狀態。</span><span class="sxs-lookup"><span data-stu-id="759c3-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="759c3-158">如需詳細資訊，請參閱 [資料遺失防護 (DLP) 原則](/power-automate/prevent-data-loss)。</span><span class="sxs-lookup"><span data-stu-id="759c3-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="759c3-159">相關內容</span><span class="sxs-lookup"><span data-stu-id="759c3-159">Related content</span></span>

<span data-ttu-id="759c3-160">[Office 腳本技術檔](/office/dev/scripts/) (連結頁面) </span><span class="sxs-lookup"><span data-stu-id="759c3-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="759c3-161">[Excel 中的 Office 腳本簡介](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (文章) </span><span class="sxs-lookup"><span data-stu-id="759c3-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="759c3-162">[在 Excel 中為 Web (文章共用 Office 腳本](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b)) </span><span class="sxs-lookup"><span data-stu-id="759c3-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="759c3-163">[在網頁上的 Excel 中記錄、編輯及建立 Office 腳本](/office/dev/scripts/tutorials/excel-tutorial) (文章) </span><span class="sxs-lookup"><span data-stu-id="759c3-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
