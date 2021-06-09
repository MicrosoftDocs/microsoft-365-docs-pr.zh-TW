---
title: 內幕風險管理審核記錄
description: 深入瞭解 Microsoft 365 中的「內幕風險管理」審核記錄
keywords: Microsoft 365, 內部風險管理, 風險管理, 合規性
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: bda9633ab37fd21fd66b3a8a53d4dd522e48ced1
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820271"
---
# <a name="insider-risk-management-audit-log"></a><span data-ttu-id="1889f-104">內幕風險管理審核記錄</span><span class="sxs-lookup"><span data-stu-id="1889f-104">Insider risk management audit log</span></span>

<span data-ttu-id="1889f-105">「內部使用者風險管理」審核記錄可讓您及時瞭解對「有問必答風險管理」功能所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="1889f-105">The insider risk management audit log enables you to stay informed on the actions that were taken on insider risk management features.</span></span> <span data-ttu-id="1889f-106">這份記錄允許獨立複查指派給一或多個「內幕人員風險管理」角色群組之使用者所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="1889f-106">This log allows independent review of the actions taken by users assigned to one or more insider risk management role groups.</span></span> <span data-ttu-id="1889f-107">在您的組織中自動啟用內部使用者風險管理審核記錄，而且無法停用。</span><span class="sxs-lookup"><span data-stu-id="1889f-107">The insider risk management audit log is automatically enabled in your organization and cannot be disabled.</span></span>

![內幕風險管理審核記錄](../media/insider-risk-audit-log.png)

<span data-ttu-id="1889f-109">當監視的活動發生時，審核記錄會自動和立即更新，而且記錄會在180天內保留有關活動的資訊 (大約六個月) 。</span><span class="sxs-lookup"><span data-stu-id="1889f-109">The audit log is automatically and immediately updated whenever monitored activities occur and the log retains information about the activity for 180 days (about six months).</span></span> <span data-ttu-id="1889f-110">180天后，活動的資料會從記錄中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="1889f-110">After 180 days, the data for the activity is permanently deleted from the log.</span></span>

<span data-ttu-id="1889f-111">活動監視中包含的領域包括：</span><span class="sxs-lookup"><span data-stu-id="1889f-111">Areas included in activity monitoring include:</span></span>

- <span data-ttu-id="1889f-112">原則</span><span class="sxs-lookup"><span data-stu-id="1889f-112">Policies</span></span>
- <span data-ttu-id="1889f-113">例</span><span class="sxs-lookup"><span data-stu-id="1889f-113">Cases</span></span>
- <span data-ttu-id="1889f-114">警示</span><span class="sxs-lookup"><span data-stu-id="1889f-114">Alerts</span></span>
- <span data-ttu-id="1889f-115">設定</span><span class="sxs-lookup"><span data-stu-id="1889f-115">Settings</span></span>
- <span data-ttu-id="1889f-116">使用者</span><span class="sxs-lookup"><span data-stu-id="1889f-116">Users</span></span>
- <span data-ttu-id="1889f-117">通知範本</span><span class="sxs-lookup"><span data-stu-id="1889f-117">Notice templates</span></span>

<span data-ttu-id="1889f-118">若要從審核記錄檔中查看和匯出資料，使用者必須被指派給「 *內部使用者風險管理* 」或「 *有問必答風險管理審計員* 」角色群組。</span><span class="sxs-lookup"><span data-stu-id="1889f-118">To view and export data from the audit log, users must be assigned to the *Insider Risk Management* or *Insider Risk Management Auditors* role groups.</span></span> <span data-ttu-id="1889f-119">若要深入瞭解「內幕風險管理」角色群組，請參閱「 [會員風險管理的快速入門」步驟1：啟用許可權](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)。</span><span class="sxs-lookup"><span data-stu-id="1889f-119">To learn more about insider risk management role groups, see [Getting started with insider risk management Step 1: Enabling permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management).</span></span>

>[!NOTE]
><span data-ttu-id="1889f-120">「內部使用者風險管理」審核記錄並未與 Microsoft 365 的審計記錄產生關聯，它們是獨立的審計系統，並在不同的活動上捕獲資訊。</span><span class="sxs-lookup"><span data-stu-id="1889f-120">The insider risk management audit log isn't associated with the Microsoft 365 audit log, they are independent auditing systems and capture information on separate activities.</span></span> <span data-ttu-id="1889f-121">停用 Microsoft 365 審核不會影響內幕風險管理內的活動稽核。</span><span class="sxs-lookup"><span data-stu-id="1889f-121">Disabling Microsoft 365 auditing doesn't impact activity auditing within insider risk management.</span></span>

## <a name="view-activity-in-the-insider-risk-audit-log"></a><span data-ttu-id="1889f-122">在「內幕風險審核」記錄中查看活動</span><span class="sxs-lookup"><span data-stu-id="1889f-122">View activity in the insider risk audit log</span></span>

<span data-ttu-id="1889f-123">若要查看監視的「內幕風險管理」的功能活動，請流覽至，然後在任何「內幕人員風險管理」索引標籤的右上方區域中，選取「 **內幕人士風險審核記錄** 」連結。根據預設，您會看到顯示的內幕程式風險管理活動的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1889f-123">To view feature activity monitored for insider risk management, navigate to, and select the **Insider risk audit log** link in the top-right area of any insider risk management tab. By default, you'll see the following information displayed for insider risk management activities:</span></span>

- <span data-ttu-id="1889f-124">**活動：** 由使用者在「內幕風險管理」方案中所進行之活動的描述。</span><span class="sxs-lookup"><span data-stu-id="1889f-124">**Activity:** A description of the activity taken within the insider risk management solution by a user.</span></span>
- <span data-ttu-id="1889f-125">**類別：** 執行活動的區域或專案。</span><span class="sxs-lookup"><span data-stu-id="1889f-125">**Category:** The area or item where the activity was performed.</span></span> <span data-ttu-id="1889f-126">例如，您會在執行原則變更活動時，看到 *原則* 做為類別。</span><span class="sxs-lookup"><span data-stu-id="1889f-126">For example, you'll see *Policies* as the category when policy change activities were performed.</span></span>
- <span data-ttu-id="1889f-127">**活動執行者：** 執行活動之使用者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="1889f-127">**Activity performed by:** The user name of the user that performed the activity.</span></span>
- <span data-ttu-id="1889f-128">**日期：** 活動的執行日期和時間。</span><span class="sxs-lookup"><span data-stu-id="1889f-128">**Date:** The date and time the activity was performed.</span></span> <span data-ttu-id="1889f-129">日期和時間為您的組織的本機日期和時間。</span><span class="sxs-lookup"><span data-stu-id="1889f-129">The date and time are the local date and time for your organization.</span></span>

<span data-ttu-id="1889f-130">如需記錄的活動的詳細資訊，請選取活動以顯示活動詳細資料窗格。</span><span class="sxs-lookup"><span data-stu-id="1889f-130">For more information about a logged activity, select the activity to display the activity details pane.</span></span> <span data-ttu-id="1889f-131">此窗格包含有關活動的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="1889f-131">This pane includes additional information about the activity.</span></span>

## <a name="columns-and-filtering"></a><span data-ttu-id="1889f-132">欄與篩選</span><span class="sxs-lookup"><span data-stu-id="1889f-132">Columns and filtering</span></span>

<span data-ttu-id="1889f-133">若要讓審計員查看記錄的活動變得更簡單，「 **有問必答風險審核記錄**」支援篩選。</span><span class="sxs-lookup"><span data-stu-id="1889f-133">To make it easier for auditors to review logged activity, filtering is supported in the **Insider risk audit log**.</span></span> <span data-ttu-id="1889f-134">針對基本篩選，佇列欄可用於新增至視圖，以在檔案和郵件上提供不同的轉動。</span><span class="sxs-lookup"><span data-stu-id="1889f-134">For basic filtering, queue columns are available to add to the view to provide different pivots on the files and messages.</span></span> <span data-ttu-id="1889f-135">您可以依 **類別、日期範圍** 及欄位所執行的 **活動** 來篩選活動。</span><span class="sxs-lookup"><span data-stu-id="1889f-135">You can filter activities by the **Category, Date range,** and **Activity performed by** fields.</span></span>

<span data-ttu-id="1889f-136">若要新增或移除活動佇列的欄標題，請使用 [ **自訂欄** ] 控制項，然後從 [欄選項] 中選取。</span><span class="sxs-lookup"><span data-stu-id="1889f-136">To add or remove column headings for the activity queue, use the **Customize columns** control and select from the column options.</span></span> <span data-ttu-id="1889f-137">這些欄會對應至「 **內幕風險審核」記錄** 中支援的常見條件，本文稍後會列出。</span><span class="sxs-lookup"><span data-stu-id="1889f-137">These columns map to common conditions supported in the **Insider risk audit log** and are listed later in this article.</span></span>

## <a name="audit-log-export"></a><span data-ttu-id="1889f-138">審核記錄匯出</span><span class="sxs-lookup"><span data-stu-id="1889f-138">Audit log export</span></span>

<span data-ttu-id="1889f-139">指派給「*內部使用者風險管理*」或「*內幕風險管理審計員*」角色群組的使用者，可以透過在「**有問必答風險審核記錄**」頁面上選取 [**匯出**]，將審核記錄中的所有活動匯出至 .csv (逗號分隔值) 檔案。</span><span class="sxs-lookup"><span data-stu-id="1889f-139">Users assigned to the *Insider Risk Management* or *Insider Risk Management Auditors* role groups can export all activity in the audit log to a .csv (comma-separated values) file by selecting **Export** on the **Insider risk audit log** page.</span></span> <span data-ttu-id="1889f-140">根據活動的不同，活動的某些欄位可能不適用於活動，而且這些欄位在匯出的檔案中會顯示為空白。</span><span class="sxs-lookup"><span data-stu-id="1889f-140">Depending on the activity, some fields for an activity may not be applicable to the activity and these fields will appear as blank in the exported file.</span></span>

<span data-ttu-id="1889f-141">檔案包含下欄欄位的活動資訊：</span><span class="sxs-lookup"><span data-stu-id="1889f-141">The file contains activity information for the following fields:</span></span>

- <span data-ttu-id="1889f-142">**活動執行者：** 修改專案值之使用者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="1889f-142">**Activity performed by:** The user name of the user modifying an item value.</span></span> <span data-ttu-id="1889f-143">此處所列的使用者已被指派至下列一或多個角色 [有問必答風險管理角色群組](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)：「 *內部使用者風險管理*」、「 *內幕人員風險管理*」、「 *有問必答風險管理分析* 者」、「 *有問必答風險管理調查* 人員」。</span><span class="sxs-lookup"><span data-stu-id="1889f-143">Users listed here were assigned to one or more of the following role [insider risk management role groups](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management): *Insider Risk Management*, *Insider Risk Management Admins*, *Insider Risk Management Analysts*, *Insider Risk Management Investigators*.</span></span> <span data-ttu-id="1889f-144">每個角色群組都具有不同的許可權等級來管理「有問必答風險」功能。</span><span class="sxs-lookup"><span data-stu-id="1889f-144">Each role group has different permission levels for managing insider risk features.</span></span>
- <span data-ttu-id="1889f-145">**活動：** 對專案所執行的活動。</span><span class="sxs-lookup"><span data-stu-id="1889f-145">**Activity:** The activity taken on an item.</span></span> <span data-ttu-id="1889f-146">值是 *查看、刪除、新增、編輯的原則、案例、使用者、警示* 和 *設定。*</span><span class="sxs-lookup"><span data-stu-id="1889f-146">Values are *Viewed, Deleted, Added, Edited policy, Case, User, Alert,* and *Settings.*</span></span>
- <span data-ttu-id="1889f-147">**已新增**：在活動期間新增的物件，例如使用者、檔案類型或網域。</span><span class="sxs-lookup"><span data-stu-id="1889f-147">**Added**: Objects that were added during the activity, such as users, file types, or domains.</span></span>
- <span data-ttu-id="1889f-148">**警示數量**：「有問必答風險管理」設定中所定義的警示磁片層級。</span><span class="sxs-lookup"><span data-stu-id="1889f-148">**Alert volume**: The level of alert volume defined in insider risk management settings.</span></span>
- <span data-ttu-id="1889f-149">**金額**：原則的目前選取的自訂指示器數量。</span><span class="sxs-lookup"><span data-stu-id="1889f-149">**Amount**: The currently selected custom indicator amounts for a policy.</span></span>
- <span data-ttu-id="1889f-150">**資產識別碼**：執行活動之優先順序實體資產的資產識別碼。</span><span class="sxs-lookup"><span data-stu-id="1889f-150">**Asset ID**: The asset ID of the priority physical asset the activity was performed on.</span></span>
- <span data-ttu-id="1889f-151">**類別：** 修改專案的類別。</span><span class="sxs-lookup"><span data-stu-id="1889f-151">**Category:** The category of the item modified.</span></span> <span data-ttu-id="1889f-152">值為 [*原則]、[案例*]、[通知]、[設定] 及 [注意事項]*範本。*</span><span class="sxs-lookup"><span data-stu-id="1889f-152">Values are *Policies, Cases, Users, Alerts, Settings,* and *Notice templates.*</span></span>
- <span data-ttu-id="1889f-153">**日期：** 在您組織的本機日期和時間中列出的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="1889f-153">**Date:** Date and time, listed in your organization's local date and time.</span></span>
- <span data-ttu-id="1889f-154">**描述**：由使用者進行處理之物件的描述輸入 (例如原則或優先順序使用者群組) 。</span><span class="sxs-lookup"><span data-stu-id="1889f-154">**Description**: The description input by the user for the object being acted on (such as a policy or a priority user group).</span></span>
- <span data-ttu-id="1889f-155">**DLP 原則**：資料遺失防護 (所選的 DLP) 原則，以觸發內幕風險管理原則中的納入。</span><span class="sxs-lookup"><span data-stu-id="1889f-155">**DLP policy**: The data loss prevention (DLP) policy selected to trigger inclusion in an insider risk management policy.</span></span>
- <span data-ttu-id="1889f-156">**標記**：在 (執行活動的內部有問必答風險設定中的標記，例如新增或移除指示器) 。</span><span class="sxs-lookup"><span data-stu-id="1889f-156">**Indicator**: The indicator in the within insider risk settings that the activity was performed on (such as adding or removing an indicator).</span></span>
- <span data-ttu-id="1889f-157">**通知範本**：執行活動的公告範本。</span><span class="sxs-lookup"><span data-stu-id="1889f-157">**Notice template**: The notice template the activity was performed on.</span></span>
- <span data-ttu-id="1889f-158">**天數**：在「有問必答風險設定」中定義的原則啟用視窗。</span><span class="sxs-lookup"><span data-stu-id="1889f-158">**Number of days**: The policy activation window defined in insider risk settings.</span></span>
- <span data-ttu-id="1889f-159">檔案 **數目**：「有問必答的風險管理」設定中所定義的檔案磁片區限制。</span><span class="sxs-lookup"><span data-stu-id="1889f-159">**Number of files**: The file volume limit defined in insider risk management settings.</span></span>
- <span data-ttu-id="1889f-160">**原則範本**：識別碼所歸屬的原則範本。</span><span class="sxs-lookup"><span data-stu-id="1889f-160">**Policy template**: The policy template that the indicators acted on belongs to.</span></span>
- <span data-ttu-id="1889f-161">**舊金額**：先前針對原則選取的自訂指示器金額。</span><span class="sxs-lookup"><span data-stu-id="1889f-161">**Previous amount**: The previously selected custom indicator amounts for a policy.</span></span>
- <span data-ttu-id="1889f-162">[**優先順序] 使用者群組**：執行活動的優先順序使用者群組。</span><span class="sxs-lookup"><span data-stu-id="1889f-162">**Priority user group**: The priority user group the activity was performed on.</span></span>
- <span data-ttu-id="1889f-163">**已移除**：在活動期間移除的物件，例如使用者、檔案類型或網域。</span><span class="sxs-lookup"><span data-stu-id="1889f-163">**Removed**: Objects that were removed during the activity, such as users, file types, or domains.</span></span>
- <span data-ttu-id="1889f-164">**寄件者**：執行活動之公告範本的 [寄件者] 欄位。</span><span class="sxs-lookup"><span data-stu-id="1889f-164">**Sender**: The sender field of the notice template the activity was performed on.</span></span>
- <span data-ttu-id="1889f-165">**目標原則**：執行活動的原則 (例如在) 中新增使用者或移除使用者。</span><span class="sxs-lookup"><span data-stu-id="1889f-165">**Target policy**: The policy the activity was performed on (such as adding a user to or removing a user from).</span></span>
- <span data-ttu-id="1889f-166">**範本訊息主體**：執行活動之公告範本的郵件內文。</span><span class="sxs-lookup"><span data-stu-id="1889f-166">**Template message body**: The message body of the notice template the activity was performed on.</span></span>
- <span data-ttu-id="1889f-167">**範本** 主旨：執行活動之公告範本的 [主旨] 欄位。</span><span class="sxs-lookup"><span data-stu-id="1889f-167">**Template subject**: The subject field of the notice template the activity was performed on.</span></span>
- <span data-ttu-id="1889f-168">**使用者：** 執行活動的使用者。</span><span class="sxs-lookup"><span data-stu-id="1889f-168">**User:** User the activity was performed on.</span></span>
