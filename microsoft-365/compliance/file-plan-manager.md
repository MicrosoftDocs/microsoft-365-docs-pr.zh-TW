---
title: 檔案計劃管理員的概觀
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 檔案計劃管理員提供對於保留標籤、保留標籤原則的進階管理功能，並且提供整合的方式讓標籤和標籤至內容活動周遊整個內容生命週期 – 從建立、共同作業、記錄宣告、保留，到最終的處置。
ms.openlocfilehash: a79f24beb83c27873824973410daff953e989175
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805886"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="4d488-103">檔案計劃管理員的概觀</span><span class="sxs-lookup"><span data-stu-id="4d488-103">Overview of file plan manager</span></span>

<span data-ttu-id="4d488-104">檔案計劃管理員提供對於保留標籤、保留標籤原則的進階管理功能，並且提供整合的方式讓標籤和標籤至內容活動周遊整個內容生命週期 – 從建立、共同作業、記錄宣告、保留，到最終的處置。</span><span class="sxs-lookup"><span data-stu-id="4d488-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span> 

<span data-ttu-id="4d488-105">若要存取安全性與合規性中心的檔案計劃管理員，請移至 **[記錄管理]** >  **[檔案計劃]**。</span><span class="sxs-lookup"><span data-stu-id="4d488-105">To access file plan manager in the security and compliance center, go to **Records management** > **File plan**.</span></span>

![檔案計劃頁面](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="4d488-107">存取檔案計劃管理員</span><span class="sxs-lookup"><span data-stu-id="4d488-107">Accessing file plan manager</span></span>

<span data-ttu-id="4d488-108">存取檔案計劃管理員有兩個需求，需求如下：</span><span class="sxs-lookup"><span data-stu-id="4d488-108">There are two requirements to access file plan manager, they are:</span></span>

- <span data-ttu-id="4d488-109">Office 365 企業版 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="4d488-109">An Office 365 Enterprise E5 subscription.</span></span>

- <span data-ttu-id="4d488-110">使用者已獲指派安全性與合規性中心的下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="4d488-110">The user has been in assigned one of the following roles in the security and compliance center:</span></span>
    
    - <span data-ttu-id="4d488-111">保留管理員</span><span class="sxs-lookup"><span data-stu-id="4d488-111">Retention Manager</span></span>
    
    - <span data-ttu-id="4d488-112">僅檢視保留管理員</span><span class="sxs-lookup"><span data-stu-id="4d488-112">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="4d488-113">預設保留標籤和標籤原則</span><span class="sxs-lookup"><span data-stu-id="4d488-113">Default retention labels and label policy</span></span>

<span data-ttu-id="4d488-114">如果安全性與合規性中心中沒有保留標籤，第一次在左側導覽中選擇 [檔案計畫]\*\*\*\* 時，這會建立稱為**預設資料控管發佈原則**的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="4d488-114">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="4d488-115">此標籤原則包含三個保留標籤：</span><span class="sxs-lookup"><span data-stu-id="4d488-115">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="4d488-116">**作業程序**</span><span class="sxs-lookup"><span data-stu-id="4d488-116">**Operational procedure**</span></span>
- <span data-ttu-id="4d488-117">**一般業務**</span><span class="sxs-lookup"><span data-stu-id="4d488-117">**Business general**</span></span>
- <span data-ttu-id="4d488-118">**合約協定**</span><span class="sxs-lookup"><span data-stu-id="4d488-118">**Contract agreement**</span></span>

<span data-ttu-id="4d488-119">設定這些保留標籤只是為了保留內容，而非刪除內容。</span><span class="sxs-lookup"><span data-stu-id="4d488-119">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="4d488-120">此標籤原則將發佈到整個組織，並可加以停用或移除。</span><span class="sxs-lookup"><span data-stu-id="4d488-120">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="4d488-121">您可以判斷誰開啟了檔案計畫管理員並開始了初次執行體驗，方法是檢閱活動 [建立保留原則]\*\*\*\* 和 [為保留原則建立了保留組態]\*\*\*\* 的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="4d488-121">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="4d488-122">由於客戶的意見反應，我們已移除了會建立預設保留標籤和以上所提及的保留標籤原則的這項功能。</span><span class="sxs-lookup"><span data-stu-id="4d488-122">Due to customer feedback, we have removed this feature that creates the default retention labels and label policy mentioned above.</span></span> <span data-ttu-id="4d488-123">只有在 2019 年 4 月 11 日之前開啟檔案計劃管理員的情況下，才會看到這些保留標籤和保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="4d488-123">You will only see this policy and labels if you used file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="4d488-124">瀏覽您的檔案計劃</span><span class="sxs-lookup"><span data-stu-id="4d488-124">Navigating your file plan</span></span>

<span data-ttu-id="4d488-125">檔案計劃管理員可讓您更輕鬆地從單一檢視，查看所有保留標籤和原則及其設定。</span><span class="sxs-lookup"><span data-stu-id="4d488-125">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="4d488-126">請注意，在檔案計劃外部所建立的保留標籤可以在檔案計劃中使用，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="4d488-126">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="4d488-127">在檔案計劃 **[標籤]** 索引標籤上，下列額外資訊和功能可供使用：</span><span class="sxs-lookup"><span data-stu-id="4d488-127">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="4d488-128">標籤設定資料行</span><span class="sxs-lookup"><span data-stu-id="4d488-128">Label settings columns</span></span>

- <span data-ttu-id="4d488-p103">[根據]\*\*\*\* 會識別觸發程序類型，該觸發程序會開始保留期間。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="4d488-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="4d488-131">事件</span><span class="sxs-lookup"><span data-stu-id="4d488-131">Event</span></span>
    - <span data-ttu-id="4d488-132">建立時機</span><span class="sxs-lookup"><span data-stu-id="4d488-132">When created</span></span>
    - <span data-ttu-id="4d488-133">上次修改時間</span><span class="sxs-lookup"><span data-stu-id="4d488-133">When last modified</span></span>
    - <span data-ttu-id="4d488-134">套用標籤時機</span><span class="sxs-lookup"><span data-stu-id="4d488-134">When labeled</span></span>
- <span data-ttu-id="4d488-p104">[記錄]\*\*\*\* 會識別項目是否會在套用標籤時變成宣告的記錄。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="4d488-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="4d488-137">否</span><span class="sxs-lookup"><span data-stu-id="4d488-137">No</span></span>
    - <span data-ttu-id="4d488-138">是</span><span class="sxs-lookup"><span data-stu-id="4d488-138">Yes</span></span>
    - <span data-ttu-id="4d488-139">Yes(Regulatory)</span><span class="sxs-lookup"><span data-stu-id="4d488-139">Yes(Regulatory)</span></span>
- <span data-ttu-id="4d488-p105">[保留]\*\*\*\* 會識別保留類型。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="4d488-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="4d488-142">保留</span><span class="sxs-lookup"><span data-stu-id="4d488-142">Keep</span></span>
    - <span data-ttu-id="4d488-143">保留與刪除</span><span class="sxs-lookup"><span data-stu-id="4d488-143">Keep and delete</span></span>
    - <span data-ttu-id="4d488-144">刪除</span><span class="sxs-lookup"><span data-stu-id="4d488-144">Delete</span></span>
- <span data-ttu-id="4d488-p106">[處置]\*\*\*\* 會識別保留期間結束時內容會發生什麼情形。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="4d488-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="4d488-147">Null</span><span class="sxs-lookup"><span data-stu-id="4d488-147">null</span></span>
    - <span data-ttu-id="4d488-148">不執行任何動作</span><span class="sxs-lookup"><span data-stu-id="4d488-148">No action</span></span>
    - <span data-ttu-id="4d488-149">自動刪除</span><span class="sxs-lookup"><span data-stu-id="4d488-149">Auto-delete</span></span>
    - <span data-ttu-id="4d488-150">需要檢閱 (也稱為處置檢閱)</span><span class="sxs-lookup"><span data-stu-id="4d488-150">Review required (aka Disposition review)</span></span>

![檔案計劃中的標籤設定](media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="4d488-152">保留標籤檔案計劃描述元資料行</span><span class="sxs-lookup"><span data-stu-id="4d488-152">Retention label file plan descriptors columns</span></span>

<span data-ttu-id="4d488-153">您現在可以在保留標籤的設定中包含更多資訊。</span><span class="sxs-lookup"><span data-stu-id="4d488-153">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span> <span data-ttu-id="4d488-154">將檔案計劃描述元插入保留標籤會改善檔案計劃的管理性和組織。</span><span class="sxs-lookup"><span data-stu-id="4d488-154">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="4d488-155">為了協助您開始使用，檔案計劃管理員會為以下項目提供現成的值：功能/部門、類別、授權單位類型和條款/引文。</span><span class="sxs-lookup"><span data-stu-id="4d488-155">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span> <span data-ttu-id="4d488-156">您可以在建立或編輯保留標籤時新增全新檔案計劃描述元值。</span><span class="sxs-lookup"><span data-stu-id="4d488-156">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span> <span data-ttu-id="4d488-157">您也可以在匯入保留標籤到檔案計劃時，指定檔案計劃描述元。</span><span class="sxs-lookup"><span data-stu-id="4d488-157">You can also specify file plan descriptors when importing retention labels into your file plan.</span></span> 

<span data-ttu-id="4d488-158">以下是建立或編輯保留標籤時的檔案計劃描述元步驟檢視。</span><span class="sxs-lookup"><span data-stu-id="4d488-158">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![檔案計劃描述元](media/file-plan-descriptors.png)

<span data-ttu-id="4d488-160">以下是檔案計劃管理員的 **[標籤]** 索引標籤上，檔案計劃描述元的檢視。</span><span class="sxs-lookup"><span data-stu-id="4d488-160">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="4d488-162">匯出所有現有的保留標籤以分析及/或執行離線檢閱</span><span class="sxs-lookup"><span data-stu-id="4d488-162">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="4d488-163">您可以從檔案計劃管理員將所有保留標籤的詳細資料匯出至 .csv 檔案，以協助您加速與貴組織中資料控管專案關係人進行的定期合規性檢閱。</span><span class="sxs-lookup"><span data-stu-id="4d488-163">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="4d488-164">若要匯出所有保留標籤：在 **[檔案計劃]** 頁面，**[檔案計劃動作]** \> **[匯出標籤]**。</span><span class="sxs-lookup"><span data-stu-id="4d488-164">To export all retention labels: On the **File plan** page, **File plan actions** \> **Export labels**.</span></span>

![匯出檔案計劃的選項](media/file-plan-export-labels-option.png)

<span data-ttu-id="4d488-166">包含所有現有保留標籤的 \*.csv 檔案隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="4d488-166">A \*.csv file containing all existing retention labels will open.</span></span>

![顯示所有保留標籤的 CSV 檔案](media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="4d488-168">將保留標籤匯入至您的檔案計劃</span><span class="sxs-lookup"><span data-stu-id="4d488-168">Import labels into your file plan</span></span>

<span data-ttu-id="4d488-169">您可以在 [檔案計劃管理員] 大量匯入新的保留標籤，並修改現有的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="4d488-169">In the File plan manager, you can bulk import new retention labels and modify existing retention labels.</span></span>

<span data-ttu-id="4d488-170">若要匯出新的保留標籤，以及修改現有的保留標籤：</span><span class="sxs-lookup"><span data-stu-id="4d488-170">To import new retention labels and modify existing retention labels:</span></span> 

1. <span data-ttu-id="4d488-171">移至在 **[檔案計劃]** 頁面上的 **[檔案計劃動作]** >  **[匯入標籤]**。</span><span class="sxs-lookup"><span data-stu-id="4d488-171">On the **File plan** page, go to **File plan actions** > **Import labels**.</span></span>

   ![匯入檔案計劃的選項](media/file-plan-import-labels-option.png)

   ![下載空白檔案計劃範本的選項](media/file-plan-blank-template-option.png)

2. <span data-ttu-id="4d488-174">下載空白範本以匯入全新保留標籤。</span><span class="sxs-lookup"><span data-stu-id="4d488-174">Download a blank template to import new retention labels.</span></span> <span data-ttu-id="4d488-175">或者，您可以從當匯出組織中的現有保留標籤時所匯出的 .csv 檔案開始。</span><span class="sxs-lookup"><span data-stu-id="4d488-175">Alternatively, you can start with the .csv file that is exported when you export the existing retention labels in your organization.</span></span>

   ![Excel 中開啟空白檔案計劃範本](media/file-plan-blank-template.png)

3. <span data-ttu-id="4d488-177">填寫範本。</span><span class="sxs-lookup"><span data-stu-id="4d488-177">Fill-out the template.</span></span> <span data-ttu-id="4d488-178">下列描述檔案計劃範本中每個屬性的內容和有效值。</span><span class="sxs-lookup"><span data-stu-id="4d488-178">The following describes the properties and valid values for each property in the file plan template.</span></span><br/>

   |<span data-ttu-id="4d488-179">**屬性**</span><span class="sxs-lookup"><span data-stu-id="4d488-179">**Property**</span></span>|<span data-ttu-id="4d488-180">**類型**</span><span class="sxs-lookup"><span data-stu-id="4d488-180">**Type**</span></span>|<span data-ttu-id="4d488-181">**有效值**</span><span class="sxs-lookup"><span data-stu-id="4d488-181">**Valid values**</span></span>|
   |:-----|:-----|:-----|
   |<span data-ttu-id="4d488-182">LabelName</span><span class="sxs-lookup"><span data-stu-id="4d488-182">LabelName</span></span>|<span data-ttu-id="4d488-183">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-183">String</span></span>|<span data-ttu-id="4d488-184">此屬性會指定保留標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="4d488-184">This property specifies the name of the retention label.</span></span>|
   |<span data-ttu-id="4d488-185">留言</span><span class="sxs-lookup"><span data-stu-id="4d488-185">Comment</span></span>|<span data-ttu-id="4d488-186">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-186">String</span></span>|<span data-ttu-id="4d488-187">使用此屬性來新增系統管理員保留標籤相關的描述。</span><span class="sxs-lookup"><span data-stu-id="4d488-187">Use this property to add a description about the retention label for admins.</span></span> <span data-ttu-id="4d488-188">只有在安全性與合規性中心中管理標籤的系統管理員才會看到這個描述。</span><span class="sxs-lookup"><span data-stu-id="4d488-188">This description appears only to admins who manage the label in the security and compliance center.</span></span>|
   |<span data-ttu-id="4d488-189">附註</span><span class="sxs-lookup"><span data-stu-id="4d488-189">Notes</span></span>|<span data-ttu-id="4d488-190">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-190">String</span></span>|<span data-ttu-id="4d488-191">使用此屬性來新增使用者保留標籤相關的描述。</span><span class="sxs-lookup"><span data-stu-id="4d488-191">Use this property to add a description about the retention label for users.</span></span> <span data-ttu-id="4d488-192">當使用者將游標移到應用程式 (例如 Outlook、SharePoint 和 OneDrive) 中的標籤上時，就會出現此描述。</span><span class="sxs-lookup"><span data-stu-id="4d488-192">This description appears when users hover over the label in apps like Outlook, SharePoint, and OneDrive.</span></span> <span data-ttu-id="4d488-193">如果您將此屬性保留空白，則會顯示說明標籤之保留設定的預設描述。</span><span class="sxs-lookup"><span data-stu-id="4d488-193">If you leave this property blank, a default description is displayed, which explains the label's retention settings.</span></span> |
   |<span data-ttu-id="4d488-194">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="4d488-194">IsRecordLabel</span></span>|<span data-ttu-id="4d488-195">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-195">String</span></span>|<span data-ttu-id="4d488-196">此屬性會指定標籤是否為記錄標籤。</span><span class="sxs-lookup"><span data-stu-id="4d488-196">The 
                IsRecordLabel
              parameter specifies whether the label is a record label.</span></span> <span data-ttu-id="4d488-197">標記為記錄標籤的項目會宣告為記錄。</span><span class="sxs-lookup"><span data-stu-id="4d488-197">Items tagged with a record label are declared as records.</span></span> <span data-ttu-id="4d488-198">有效值為：</span><span class="sxs-lookup"><span data-stu-id="4d488-198">Valid values are:</span></span></br><span data-ttu-id="4d488-199">**TRUE**：標籤是記錄標籤。</span><span class="sxs-lookup"><span data-stu-id="4d488-199">**TRUE**: The label is a record label.</span></span> <span data-ttu-id="4d488-200">請注意，無法刪除宣告為記錄的項目。</span><span class="sxs-lookup"><span data-stu-id="4d488-200">Note that items that are declared as a record can't be deleted.</span></span> </br><span data-ttu-id="4d488-201">**FALSE**：該標籤不是記錄標籤。</span><span class="sxs-lookup"><span data-stu-id="4d488-201">**FALSE**: The label isn't a record label.</span></span> <span data-ttu-id="4d488-202">這是預設值。</span><span class="sxs-lookup"><span data-stu-id="4d488-202">This is the default value.</span></span>|
   |<span data-ttu-id="4d488-203">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="4d488-203">RetentionAction</span></span>|<span data-ttu-id="4d488-204">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-204">String</span></span>|<span data-ttu-id="4d488-205">此屬性指定由 RetentionDuration 屬性指定的值過期之後所要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="4d488-205">This property specifies what action to take after the value specified by the RetentionDuration property expires.</span></span> <span data-ttu-id="4d488-206">有效值為：</span><span class="sxs-lookup"><span data-stu-id="4d488-206">Valid values are:</span></span></br><span data-ttu-id="4d488-207">**Delete**：刪除早於 RetentionDuration 屬性指定值的項目。</span><span class="sxs-lookup"><span data-stu-id="4d488-207">**Delete**: Items older than the value specified by the RetentionDuration property are deleted.</span></span></br><span data-ttu-id="4d488-208">**Keep**：保留由 RetentionDuration 屬性指定期間內的項目，然後在期間到期時不執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="4d488-208">**Keep**: Retain items for the duration specified by the RetentionDuration property and then doing nothing when the duration period expires.</span></span> </br><span data-ttu-id="4d488-209">**KeepAndDelete**：保留由 RetentionDuration 屬性指定期間內的項目，然後在期間到期時將之刪除。</span><span class="sxs-lookup"><span data-stu-id="4d488-209">**KeepAndDelete**: Retain items for the duration specified by the RetentionDuration property and then delete them when the duration period expires.</span></span>   |
   |<span data-ttu-id="4d488-210">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="4d488-210">RetentionDuration</span></span>|<span data-ttu-id="4d488-211">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-211">String</span></span>|<span data-ttu-id="4d488-212">此屬性會指定要保留內容的天數。</span><span class="sxs-lookup"><span data-stu-id="4d488-212">The RetentionDuration parameter specifies the number of days to retain the content.</span></span> <span data-ttu-id="4d488-213">有效值為：</span><span class="sxs-lookup"><span data-stu-id="4d488-213">Valid values are:</span></span></br><span data-ttu-id="4d488-214">**無限制**：系統會無限期保留這些項目。</span><span class="sxs-lookup"><span data-stu-id="4d488-214">**Unlimited**: Items will be retained indefinitely.</span></span> </br><span data-ttu-id="4d488-215">***n***：正整數；例如 **365**。</span><span class="sxs-lookup"><span data-stu-id="4d488-215">***n***: A positive integer; for example, **365**.</span></span> 
   |<span data-ttu-id="4d488-216">RetentionType</span><span class="sxs-lookup"><span data-stu-id="4d488-216">RetentionType</span></span>|<span data-ttu-id="4d488-217">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-217">String</span></span>|<span data-ttu-id="4d488-218">此屬性會指定保留期限是否從內容建立日期、事件日期、標籤 (標記) 日期或上次修改日期開始算起。</span><span class="sxs-lookup"><span data-stu-id="4d488-218">This property specifies whether the retention duration is calculated from the content creation date, event date, labeled (tagged) date, or last modified date.</span></span> <span data-ttu-id="4d488-219">有效值為：</span><span class="sxs-lookup"><span data-stu-id="4d488-219">Valid values are:</span></span></br><span data-ttu-id="4d488-220">**CreationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="4d488-220">**CreationAgeInDays**</span></span></br><span data-ttu-id="4d488-221">**EventAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="4d488-221">**EventAgeInDays**</span></span></br><span data-ttu-id="4d488-222">**TaggedAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="4d488-222">**TaggedAgeInDays**</span></span></br><span data-ttu-id="4d488-223">**ModificationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="4d488-223">**ModificationAgeInDays**</span></span> |
   |<span data-ttu-id="4d488-224">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="4d488-224">ReviewerEmail</span></span>|<span data-ttu-id="4d488-225">SmtpAddress</span><span class="sxs-lookup"><span data-stu-id="4d488-225">SmtpAddress</span></span>|<span data-ttu-id="4d488-226">填入此屬性時，系統會在保留期間到期時觸發處置檢閱。</span><span class="sxs-lookup"><span data-stu-id="4d488-226">When this property is populated, a disposition review will be triggered when the retention duration expires.</span></span> <span data-ttu-id="4d488-227">此屬性會指定 **Delete** 和 **KeepAndDelete** 保留動作檢閱者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4d488-227">The ReviewerEmail parameter specifies the email address of a reviewer for Delete and KeepAndDelete retention actions.</span></span> <span data-ttu-id="4d488-228">您可以包含個別使用者、通訊群組或安全性群組，或 Office 365 群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4d488-228">You can include the email address of individual users, distribution or security groups, or Office 365 groups.</span></span> <span data-ttu-id="4d488-229">您可以指定以逗號隔開的多個電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4d488-229">You can specify multiple email addresses separated by commas.</span></span>|
   |<span data-ttu-id="4d488-230">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="4d488-230">ReferenceId</span></span>|<span data-ttu-id="4d488-231">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-231">String</span></span>|<span data-ttu-id="4d488-232">此屬性指定在 **[參考識別碼]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="4d488-232">This property specifies the value that's displayed in the **Reference Id** file plan descriptor.</span></span>| 
   |<span data-ttu-id="4d488-233">Departmentname</span><span class="sxs-lookup"><span data-stu-id="4d488-233">DepartmentName</span></span>|<span data-ttu-id="4d488-234">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-234">String</span></span>|<span data-ttu-id="4d488-235">此屬性指定在 **[功能/部門]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="4d488-235">This property specifies the value that's displayed in the **Function/department** file plan descriptor.</span></span>|
   |<span data-ttu-id="4d488-236">類別</span><span class="sxs-lookup"><span data-stu-id="4d488-236">Category</span></span>|<span data-ttu-id="4d488-237">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-237">String</span></span>|<span data-ttu-id="4d488-238">此屬性指定在 **[類別]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="4d488-238">This property specifies the value that's displayed in the **Category** file plan descriptor.</span></span>|
   |<span data-ttu-id="4d488-239">子類別</span><span class="sxs-lookup"><span data-stu-id="4d488-239">SubCategory</span></span>|<span data-ttu-id="4d488-240">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-240">String</span></span>|<span data-ttu-id="4d488-241">此屬性指定在 **[子類別]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="4d488-241">This property specifies the value that's displayed in the **Sub category** file plan descriptor.</span></span>|
   |<span data-ttu-id="4d488-242">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="4d488-242">AuthorityType</span></span>|<span data-ttu-id="4d488-243">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-243">String</span></span>|<span data-ttu-id="4d488-244">此屬性指定在 **[授權單位類型]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="4d488-244">This property specifies the value that's displayed in the **Authority type** file plan descriptor.</span></span>|
   |<span data-ttu-id="4d488-245">CitationName</span><span class="sxs-lookup"><span data-stu-id="4d488-245">CitationName</span></span>|<span data-ttu-id="4d488-246">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-246">String</span></span>|<span data-ttu-id="4d488-247">此屬性指定在 **[條款/引文]** 檔案計劃描述元中顯示的引文名稱，例如「2002 年的沙賓法案」。</span><span class="sxs-lookup"><span data-stu-id="4d488-247">This property specifies the name of the citation displayed in the **Provision/citation** file plan descriptor; for example "Sarbanes-Oxley Act or 2002".</span></span> |
   |<span data-ttu-id="4d488-248">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="4d488-248">CitationUrl</span></span>|<span data-ttu-id="4d488-249">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-249">String</span></span>|<span data-ttu-id="4d488-250">此屬性指定在 **[條款/引文]** 檔案計劃描述元中顯示的 URL。</span><span class="sxs-lookup"><span data-stu-id="4d488-250">This property specifies the URL that's displayed in the **Provision/citation** file plan descriptor.</span></span>|
   |<span data-ttu-id="4d488-251">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="4d488-251">CitationJurisdiction</span></span>|<span data-ttu-id="4d488-252">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-252">String</span></span>|<span data-ttu-id="4d488-253">此屬性指定在 **[條款/引文]** 檔案計劃描述元中顯示的管轄單位或代理機構；例如「美國證券交易委員會 (SEC)」。</span><span class="sxs-lookup"><span data-stu-id="4d488-253">This property specifies the jurisdiction or agency that's displayed in the **Provision/citation** file plan descriptor; for example, "U.S. Securities and Exchange Commission (SEC)".</span></span>|
   |<span data-ttu-id="4d488-254">Regulatory</span><span class="sxs-lookup"><span data-stu-id="4d488-254">Regulatory</span></span>|<span data-ttu-id="4d488-255">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-255">String</span></span>|<span data-ttu-id="4d488-256">保留空白。</span><span class="sxs-lookup"><span data-stu-id="4d488-256">(leave blank)</span></span> <span data-ttu-id="4d488-257">目前無法使用此屬性。</span><span class="sxs-lookup"><span data-stu-id="4d488-257">This property isn't used at this time.</span></span>|
   |<span data-ttu-id="4d488-258">EventType</span><span class="sxs-lookup"><span data-stu-id="4d488-258">EventType</span></span>|<span data-ttu-id="4d488-259">字串</span><span class="sxs-lookup"><span data-stu-id="4d488-259">String</span></span>|<span data-ttu-id="4d488-260">此屬性會指定與標籤相關聯的保留規則。</span><span class="sxs-lookup"><span data-stu-id="4d488-260">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="4d488-261">您可以使用唯一識別規則的任何值。</span><span class="sxs-lookup"><span data-stu-id="4d488-261">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="4d488-262">例如：</span><span class="sxs-lookup"><span data-stu-id="4d488-262">For example:</span></span></br><span data-ttu-id="4d488-263">**Name**</span><span class="sxs-lookup"><span data-stu-id="4d488-263">**Name**</span></span></br><span data-ttu-id="4d488-264">**Distinguished name (DN)**</span><span class="sxs-lookup"><span data-stu-id="4d488-264">**Distinguished name (DN)**</span></span></br><span data-ttu-id="4d488-265">**GUID**</span><span class="sxs-lookup"><span data-stu-id="4d488-265">**GUID**</span></span> </br><span data-ttu-id="4d488-266">您可以使用 [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) Cmdlet 來檢視可用的保留規則。</span><span class="sxs-lookup"><span data-stu-id="4d488-266">You can use the [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available retention rules.</span></span> <span data-ttu-id="4d488-267">請注意，如果從某 Office 365 組織中匯出標籤，在將標籤匯入至另​​一個 Office 365 組織時，則不能使用該組織的 EventType 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="4d488-267">Note that if you export labels from one Office 365 organization, you can't use the values for the EventType  property from that organization when importing labels to a different Office 365 organization.</span></span> <span data-ttu-id="4d488-268">這是因為對組織而言 EventType 值是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4d488-268">That because the EventType values are unique to an organization.</span></span> |
   |||

   <span data-ttu-id="4d488-269">以下是含有保留標籤相關資訊的範本範例。</span><span class="sxs-lookup"><span data-stu-id="4d488-269">Here's an example the template containing the information about retention labels.</span></span>

   ![已填入資訊的檔案計劃範本](media/file-plan-filled-out-template.png)

4. <span data-ttu-id="4d488-271">在匯入檔案計劃精靈頁面的步驟 3 下方，按一下 **[瀏覽檔案]** 以上傳填入的範本。</span><span class="sxs-lookup"><span data-stu-id="4d488-271">Under step 3 on the import file plan wizard page, click **Browse for files** to upload the filled-out template.</span></span> 

   <span data-ttu-id="4d488-272">檔案計劃管理員會驗證項目並且顯示匯入統計資料。</span><span class="sxs-lookup"><span data-stu-id="4d488-272">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

   ![檔案計劃匯入統計資料](media/file-plan-import-statistics.png)

   <span data-ttu-id="4d488-274">萬一有驗證錯誤，檔案計劃匯入將會繼續驗證匯入檔案中的每個項目，並在匯入檔案中顯示參考行/列數的所有錯誤、複製顯示的錯誤結果，讓您可以輕鬆地返回匯入檔案並更正錯誤。</span><span class="sxs-lookup"><span data-stu-id="4d488-274">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easily return to the import file and correct the errors.</span></span>

5. <span data-ttu-id="4d488-275">匯入完成後，返回檔案計劃管理員，讓新的保留標籤與新的或現有的保留標籤原則產生關聯。</span><span class="sxs-lookup"><span data-stu-id="4d488-275">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

   ![發佈標籤的選項](media/file-plan-publish-labels-option.png)
