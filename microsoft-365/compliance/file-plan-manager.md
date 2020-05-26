---
title: 檔案計劃管理員的概觀
f1.keywords:
- NOCSH
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
ms.openlocfilehash: d47e0df05ec7dacbb2d0eaa9a7593183d5d0c557
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352136"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="940e2-103">檔案計劃管理員的概觀</span><span class="sxs-lookup"><span data-stu-id="940e2-103">Overview of file plan manager</span></span>

><span data-ttu-id="940e2-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="940e2-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="940e2-105">檔案計劃管理員提供對於保留標籤、保留標籤原則的進階管理功能，並且提供整合的方式讓標籤和標籤至內容活動周遊整個內容生命週期 – 從建立、共同作業、記錄宣告、保留，到最終的處置。</span><span class="sxs-lookup"><span data-stu-id="940e2-105">File plan manager provides advanced management capabilities for retention labels, retention label policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span> 

<span data-ttu-id="940e2-106">若要存取安全性與合規性中心的檔案計劃管理員，請移至 **[記錄管理]** >  **[檔案計劃]**。</span><span class="sxs-lookup"><span data-stu-id="940e2-106">To access file plan manager in the security and compliance center, go to **Records management** > **File plan**.</span></span>

![檔案計劃頁面](../media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="940e2-108">存取檔案計劃管理員</span><span class="sxs-lookup"><span data-stu-id="940e2-108">Accessing file plan manager</span></span>

<span data-ttu-id="940e2-109">若要存取檔案規劃管理員，必須擁有下列其中一種系統管理員角色：</span><span class="sxs-lookup"><span data-stu-id="940e2-109">To access file plan manager, you must have one of the following admin roles:</span></span>
    
- <span data-ttu-id="940e2-110">保留管理員</span><span class="sxs-lookup"><span data-stu-id="940e2-110">Retention Manager</span></span>

- <span data-ttu-id="940e2-111">僅檢視保留管理員</span><span class="sxs-lookup"><span data-stu-id="940e2-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="940e2-112">預設保留標籤和標籤原則</span><span class="sxs-lookup"><span data-stu-id="940e2-112">Default retention labels and label policy</span></span>

<span data-ttu-id="940e2-113">如果安全性與合規性中心中沒有保留標籤，第一次在左側導覽中選擇 [檔案計畫]\*\*\*\* 時，這會建立稱為**預設資料控管發佈原則**的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="940e2-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="940e2-114">此標籤原則包含三個保留標籤：</span><span class="sxs-lookup"><span data-stu-id="940e2-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="940e2-115">**作業程序**</span><span class="sxs-lookup"><span data-stu-id="940e2-115">**Operational procedure**</span></span>
- <span data-ttu-id="940e2-116">**一般業務**</span><span class="sxs-lookup"><span data-stu-id="940e2-116">**Business general**</span></span>
- <span data-ttu-id="940e2-117">**合約協定**</span><span class="sxs-lookup"><span data-stu-id="940e2-117">**Contract agreement**</span></span>

<span data-ttu-id="940e2-118">設定這些保留標籤只是為了保留內容，而非刪除內容。</span><span class="sxs-lookup"><span data-stu-id="940e2-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="940e2-119">此標籤原則將發佈到整個組織，並可加以停用或移除。</span><span class="sxs-lookup"><span data-stu-id="940e2-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="940e2-120">您可以判斷誰開啟了檔案計畫管理員並開始了初次執行體驗，方法是檢閱活動 [建立保留原則]\*\*\*\* 和 [為保留原則建立了保留組態]\*\*\*\* 的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="940e2-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="940e2-121">由於客戶的意見反應，我們已移除了會建立預設保留標籤和以上所提及的保留標籤原則的這項功能。</span><span class="sxs-lookup"><span data-stu-id="940e2-121">Due to customer feedback, we have removed this feature that creates the default retention labels and retention label policy mentioned above.</span></span> <span data-ttu-id="940e2-122">只有在 2019 年 4 月 11 日之前開啟檔案計劃管理員的情況下，才會看到這些保留標籤和保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="940e2-122">You will only see these retention labels and retention label policy if you opened file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="940e2-123">瀏覽您的檔案計劃</span><span class="sxs-lookup"><span data-stu-id="940e2-123">Navigating your file plan</span></span>

<span data-ttu-id="940e2-124">檔案計劃管理員可讓您更輕鬆地從單一檢視，查看所有保留標籤和原則及其設定。</span><span class="sxs-lookup"><span data-stu-id="940e2-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="940e2-125">請注意，在檔案計劃外部所建立的保留標籤可以在檔案計劃中使用，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="940e2-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="940e2-126">在檔案計劃 **[標籤]** 索引標籤上，下列額外資訊和功能可供使用：</span><span class="sxs-lookup"><span data-stu-id="940e2-126">On the file plan **Labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="940e2-127">標籤設定資料行</span><span class="sxs-lookup"><span data-stu-id="940e2-127">Label settings columns</span></span>

- <span data-ttu-id="940e2-p103">[根據]\*\*\*\* 會識別觸發程序類型，該觸發程序會開始保留期間。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="940e2-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="940e2-130">事件</span><span class="sxs-lookup"><span data-stu-id="940e2-130">Event</span></span>
    - <span data-ttu-id="940e2-131">建立時機</span><span class="sxs-lookup"><span data-stu-id="940e2-131">When created</span></span>
    - <span data-ttu-id="940e2-132">上次修改時間</span><span class="sxs-lookup"><span data-stu-id="940e2-132">When last modified</span></span>
    - <span data-ttu-id="940e2-133">套用標籤時機</span><span class="sxs-lookup"><span data-stu-id="940e2-133">When labeled</span></span>
- <span data-ttu-id="940e2-p104">[記錄]\*\*\*\* 會識別項目是否會在套用標籤時變成宣告的記錄。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="940e2-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="940e2-136">否</span><span class="sxs-lookup"><span data-stu-id="940e2-136">No</span></span>
    - <span data-ttu-id="940e2-137">是</span><span class="sxs-lookup"><span data-stu-id="940e2-137">Yes</span></span>
    - <span data-ttu-id="940e2-138">Yes(Regulatory)</span><span class="sxs-lookup"><span data-stu-id="940e2-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="940e2-p105">[保留]\*\*\*\* 會識別保留類型。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="940e2-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="940e2-141">保留</span><span class="sxs-lookup"><span data-stu-id="940e2-141">Keep</span></span>
    - <span data-ttu-id="940e2-142">保留與刪除</span><span class="sxs-lookup"><span data-stu-id="940e2-142">Keep and delete</span></span>
    - <span data-ttu-id="940e2-143">刪除</span><span class="sxs-lookup"><span data-stu-id="940e2-143">Delete</span></span>
- <span data-ttu-id="940e2-p106">[處置]\*\*\*\* 會識別保留期間結束時內容會發生什麼情形。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="940e2-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="940e2-146">Null</span><span class="sxs-lookup"><span data-stu-id="940e2-146">null</span></span>
    - <span data-ttu-id="940e2-147">不執行任何動作</span><span class="sxs-lookup"><span data-stu-id="940e2-147">No action</span></span>
    - <span data-ttu-id="940e2-148">自動刪除</span><span class="sxs-lookup"><span data-stu-id="940e2-148">Auto-delete</span></span>
    - <span data-ttu-id="940e2-149">需要檢閱 (也稱為處置檢閱)</span><span class="sxs-lookup"><span data-stu-id="940e2-149">Review required (aka Disposition review)</span></span>

![檔案計劃中的標籤設定](../media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="940e2-151">保留標籤檔案計劃描述元資料行</span><span class="sxs-lookup"><span data-stu-id="940e2-151">Retention label file plan descriptors columns</span></span>

<span data-ttu-id="940e2-152">您現在可以在保留標籤的設定中包含更多資訊。</span><span class="sxs-lookup"><span data-stu-id="940e2-152">You can now include more information in the configuration of your retention labels.</span></span> <span data-ttu-id="940e2-153">將檔案計劃描述元插入保留標籤會改善檔案計劃的管理性和組織。</span><span class="sxs-lookup"><span data-stu-id="940e2-153">Inserting file plan descriptors into retention  labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="940e2-154">為了協助您開始使用，檔案計劃管理員會為以下項目提供現成的值：功能/部門、類別、授權單位類型和條款/引文。</span><span class="sxs-lookup"><span data-stu-id="940e2-154">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation.</span></span> <span data-ttu-id="940e2-155">您可以在建立或編輯保留標籤時新增全新檔案計劃描述元值。</span><span class="sxs-lookup"><span data-stu-id="940e2-155">You can add new file plan descriptor values when creating or editing a retention label.</span></span> <span data-ttu-id="940e2-156">您也可以在匯入保留標籤到檔案計劃時，指定檔案計劃描述元。</span><span class="sxs-lookup"><span data-stu-id="940e2-156">You can also specify file plan descriptors when importing retention labels into your file plan.</span></span> 

<span data-ttu-id="940e2-157">以下是建立或編輯保留標籤時的檔案計劃描述元步驟檢視。</span><span class="sxs-lookup"><span data-stu-id="940e2-157">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![檔案計劃描述元](../media/file-plan-descriptors.png)

<span data-ttu-id="940e2-159">以下是檔案計劃管理員的 **[標籤]** 索引標籤上，檔案計劃描述元的檢視。</span><span class="sxs-lookup"><span data-stu-id="940e2-159">Here's a view of the file plan descriptors columns on the **Labels** tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](../media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="940e2-161">匯出所有現有的保留標籤以分析及/或執行離線檢閱</span><span class="sxs-lookup"><span data-stu-id="940e2-161">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="940e2-162">您可以從檔案計劃管理員將所有保留標籤的詳細資料匯出至 .csv 檔案，以協助您加速與貴組織中資料控管專案關係人進行的定期合規性檢閱。</span><span class="sxs-lookup"><span data-stu-id="940e2-162">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="940e2-163">若要匯出所有保留標籤：在 **[檔案計劃]** 頁面，**[檔案計劃動作]** \> **[匯出標籤]**。</span><span class="sxs-lookup"><span data-stu-id="940e2-163">To export all retention labels: On the **File plan** page, **File plan actions** \> **Export labels**.</span></span>

![匯出檔案計劃的選項](../media/file-plan-export-labels-option.png)

<span data-ttu-id="940e2-165">包含所有現有保留標籤的 \*.csv 檔案隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="940e2-165">A \*.csv file containing all existing retention labels will open.</span></span>

![顯示所有保留標籤的 CSV 檔案](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="940e2-167">將保留標籤匯入至您的檔案計劃</span><span class="sxs-lookup"><span data-stu-id="940e2-167">Import retention labels into your file plan</span></span>

<span data-ttu-id="940e2-168">您可以在 [檔案計劃管理員] 大量匯入新的保留標籤，並修改現有的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="940e2-168">In the File plan manager, you can bulk import new retention labels and modify existing retention labels.</span></span>

<span data-ttu-id="940e2-169">若要匯出新的保留標籤，以及修改現有的保留標籤：</span><span class="sxs-lookup"><span data-stu-id="940e2-169">To import new retention labels and modify existing retention labels:</span></span> 

1. <span data-ttu-id="940e2-170">移至在 **[檔案計劃]** 頁面上的 **[檔案計劃動作]** >  **[匯入標籤]**。</span><span class="sxs-lookup"><span data-stu-id="940e2-170">On the **File plan** page, go to **File plan actions** > **Import labels**.</span></span>

   ![匯入檔案計劃的選項](../media/file-plan-import-labels-option.png)

   ![下載空白檔案計劃範本的選項](../media/file-plan-blank-template-option.png)

2. <span data-ttu-id="940e2-173">下載空白範本以匯入全新保留標籤。</span><span class="sxs-lookup"><span data-stu-id="940e2-173">Download a blank template to import new retention labels.</span></span> <span data-ttu-id="940e2-174">或者，您可以從當匯出組織中的現有保留標籤時所匯出的 .csv 檔案開始。</span><span class="sxs-lookup"><span data-stu-id="940e2-174">Alternatively, you can start with the .csv file that is exported when you export the existing retention labels in your organization.</span></span>

   ![Excel 中開啟空白檔案計劃範本](../media/file-plan-blank-template.png)

3. <span data-ttu-id="940e2-176">填寫範本。</span><span class="sxs-lookup"><span data-stu-id="940e2-176">Fill-out the template.</span></span> <span data-ttu-id="940e2-177">下列描述檔案計劃範本中每個屬性的內容和有效值。</span><span class="sxs-lookup"><span data-stu-id="940e2-177">The following describes the properties and valid values for each property in the file plan template.</span></span> <span data-ttu-id="940e2-178">匯入時，每個值最多可以包含 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="940e2-178">For import, each value has a maximum length of 64 characters.</span></span> <br/>

   |<span data-ttu-id="940e2-179">**屬性**</span><span class="sxs-lookup"><span data-stu-id="940e2-179">**Property**</span></span>|<span data-ttu-id="940e2-180">**類型**</span><span class="sxs-lookup"><span data-stu-id="940e2-180">**Type**</span></span>|<span data-ttu-id="940e2-181">**有效值**</span><span class="sxs-lookup"><span data-stu-id="940e2-181">**Valid values**</span></span>|
   |:-----|:-----|:-----|
   |<span data-ttu-id="940e2-182">LabelName</span><span class="sxs-lookup"><span data-stu-id="940e2-182">LabelName</span></span>|<span data-ttu-id="940e2-183">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-183">String</span></span>|<span data-ttu-id="940e2-184">此屬性會指定保留標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="940e2-184">This property specifies the name of the retention label.</span></span>|
   |<span data-ttu-id="940e2-185">留言</span><span class="sxs-lookup"><span data-stu-id="940e2-185">Comment</span></span>|<span data-ttu-id="940e2-186">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-186">String</span></span>|<span data-ttu-id="940e2-187">使用此屬性來新增系統管理員保留標籤相關的描述。</span><span class="sxs-lookup"><span data-stu-id="940e2-187">Use this property to add a description about the retention label for admins.</span></span> <span data-ttu-id="940e2-188">只有在安全性與合規性中心中管理標籤的系統管理員才會看到這個描述。</span><span class="sxs-lookup"><span data-stu-id="940e2-188">This description appears only to admins who manage the label in the security and compliance center.</span></span>|
   |<span data-ttu-id="940e2-189">附註</span><span class="sxs-lookup"><span data-stu-id="940e2-189">Notes</span></span>|<span data-ttu-id="940e2-190">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-190">String</span></span>|<span data-ttu-id="940e2-191">使用此屬性來新增使用者保留標籤相關的描述。</span><span class="sxs-lookup"><span data-stu-id="940e2-191">Use this property to add a description about the retention label for users.</span></span> <span data-ttu-id="940e2-192">當使用者將游標移到應用程式 (例如 Outlook、SharePoint 和 OneDrive) 中的標籤上時，就會出現此描述。</span><span class="sxs-lookup"><span data-stu-id="940e2-192">This description appears when users hover over the label in apps like Outlook, SharePoint, and OneDrive.</span></span> <span data-ttu-id="940e2-193">如果您將此屬性保留空白，則會顯示說明標籤之保留設定的預設描述。</span><span class="sxs-lookup"><span data-stu-id="940e2-193">If you leave this property blank, a default description is displayed, which explains the label's retention settings.</span></span> |
   |<span data-ttu-id="940e2-194">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="940e2-194">IsRecordLabel</span></span>|<span data-ttu-id="940e2-195">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-195">String</span></span>|<span data-ttu-id="940e2-196">此屬性會指定標籤是否為記錄標籤。</span><span class="sxs-lookup"><span data-stu-id="940e2-196">This property specifies whether the label is a record label.</span></span> <span data-ttu-id="940e2-197">標記為記錄標籤的項目會宣告為記錄。</span><span class="sxs-lookup"><span data-stu-id="940e2-197">Items tagged with a record label are declared as records.</span></span> <span data-ttu-id="940e2-198">有效值為：</span><span class="sxs-lookup"><span data-stu-id="940e2-198">Valid values are:</span></span></br><span data-ttu-id="940e2-199">**TRUE**：標籤是記錄標籤。</span><span class="sxs-lookup"><span data-stu-id="940e2-199">**TRUE**: The label is a record label.</span></span> <span data-ttu-id="940e2-200">請注意，無法刪除宣告為記錄的項目。</span><span class="sxs-lookup"><span data-stu-id="940e2-200">Note that items that are declared as a record can't be deleted.</span></span> </br><span data-ttu-id="940e2-201">**FALSE**：該標籤不是記錄標籤。</span><span class="sxs-lookup"><span data-stu-id="940e2-201">**FALSE**: The label isn't a record label.</span></span> <span data-ttu-id="940e2-202">這是預設值。</span><span class="sxs-lookup"><span data-stu-id="940e2-202">This is the default value.</span></span>|
   |<span data-ttu-id="940e2-203">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="940e2-203">RetentionAction</span></span>|<span data-ttu-id="940e2-204">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-204">String</span></span>|<span data-ttu-id="940e2-205">此屬性指定由 RetentionDuration 屬性指定的值過期之後所要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="940e2-205">This property specifies what action to take after the value specified by the RetentionDuration property expires.</span></span> <span data-ttu-id="940e2-206">有效值為：</span><span class="sxs-lookup"><span data-stu-id="940e2-206">Valid values are:</span></span></br><span data-ttu-id="940e2-207">**Delete**：刪除早於 RetentionDuration 屬性指定值的項目。</span><span class="sxs-lookup"><span data-stu-id="940e2-207">**Delete**: Items older than the value specified by the RetentionDuration property are deleted.</span></span></br><span data-ttu-id="940e2-208">**Keep**：保留由 RetentionDuration 屬性指定期間內的項目，然後在期間到期時不執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="940e2-208">**Keep**: Retain items for the duration specified by the RetentionDuration property and then doing nothing when the duration period expires.</span></span> </br><span data-ttu-id="940e2-209">**KeepAndDelete**：保留由 RetentionDuration 屬性指定期間內的項目，然後在期間到期時將之刪除。</span><span class="sxs-lookup"><span data-stu-id="940e2-209">**KeepAndDelete**: Retain items for the duration specified by the RetentionDuration property and then delete them when the duration period expires.</span></span>   |
   |<span data-ttu-id="940e2-210">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="940e2-210">RetentionDuration</span></span>|<span data-ttu-id="940e2-211">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-211">String</span></span>|<span data-ttu-id="940e2-212">此屬性會指定要保留內容的天數。</span><span class="sxs-lookup"><span data-stu-id="940e2-212">This property specifies the number of days to retain the content.</span></span> <span data-ttu-id="940e2-213">有效值為：</span><span class="sxs-lookup"><span data-stu-id="940e2-213">Valid values are:</span></span></br><span data-ttu-id="940e2-214">**無限制**：系統會無限期保留這些項目。</span><span class="sxs-lookup"><span data-stu-id="940e2-214">**Unlimited**: Items will be retained indefinitely.</span></span> </br><span data-ttu-id="940e2-215">***n***：正整數；例如 **365**。</span><span class="sxs-lookup"><span data-stu-id="940e2-215">***n***: A positive integer; for example, **365**.</span></span> 
   |<span data-ttu-id="940e2-216">RetentionType</span><span class="sxs-lookup"><span data-stu-id="940e2-216">RetentionType</span></span>|<span data-ttu-id="940e2-217">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-217">String</span></span>|<span data-ttu-id="940e2-218">此屬性會指定保留期限是否從內容建立日期、事件日期、標籤 (標記) 日期或上次修改日期開始算起。</span><span class="sxs-lookup"><span data-stu-id="940e2-218">This property specifies whether the retention duration is calculated from the content creation date, event date, labeled (tagged) date, or last modified date.</span></span> <span data-ttu-id="940e2-219">有效值為：</span><span class="sxs-lookup"><span data-stu-id="940e2-219">Valid values are:</span></span></br><span data-ttu-id="940e2-220">**CreationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="940e2-220">**CreationAgeInDays**</span></span></br><span data-ttu-id="940e2-221">**EventAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="940e2-221">**EventAgeInDays**</span></span></br><span data-ttu-id="940e2-222">**TaggedAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="940e2-222">**TaggedAgeInDays**</span></span></br><span data-ttu-id="940e2-223">**ModificationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="940e2-223">**ModificationAgeInDays**</span></span> |
   |<span data-ttu-id="940e2-224">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="940e2-224">ReviewerEmail</span></span>|<span data-ttu-id="940e2-225">SmtpAddress</span><span class="sxs-lookup"><span data-stu-id="940e2-225">SmtpAddress</span></span>|<span data-ttu-id="940e2-226">填入此屬性時，系統會在保留期間到期時觸發處置檢閱。</span><span class="sxs-lookup"><span data-stu-id="940e2-226">When this property is populated, a disposition review will be triggered when the retention duration expires.</span></span> <span data-ttu-id="940e2-227">此屬性會指定 **KeepAndDelete** 保留動作檢閱者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="940e2-227">This property specifies the email address of a reviewer for the **KeepAndDelete** retention action.</span></span> <span data-ttu-id="940e2-228">您可以包含個別使用者、通訊群組或安全性群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="940e2-228">You can include the email address of individual users, distribution, or security groups.</span></span> <span data-ttu-id="940e2-229">您可以使用分號指定多個電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="940e2-229">You can specify multiple email addresses separated by semicolons.</span></span>|
   |<span data-ttu-id="940e2-230">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="940e2-230">ReferenceId</span></span>|<span data-ttu-id="940e2-231">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-231">String</span></span>|<span data-ttu-id="940e2-232">此屬性指定在 **[參考識別碼]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="940e2-232">This property specifies the value that's displayed in the **Reference Id** file plan descriptor.</span></span>| 
   |<span data-ttu-id="940e2-233">Departmentname</span><span class="sxs-lookup"><span data-stu-id="940e2-233">DepartmentName</span></span>|<span data-ttu-id="940e2-234">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-234">String</span></span>|<span data-ttu-id="940e2-235">此屬性指定在 **[功能/部門]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="940e2-235">This property specifies the value that's displayed in the **Function/department** file plan descriptor.</span></span>|
   |<span data-ttu-id="940e2-236">類別</span><span class="sxs-lookup"><span data-stu-id="940e2-236">Category</span></span>|<span data-ttu-id="940e2-237">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-237">String</span></span>|<span data-ttu-id="940e2-238">此屬性指定在 **[類別]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="940e2-238">This property specifies the value that's displayed in the **Category** file plan descriptor.</span></span>|
   |<span data-ttu-id="940e2-239">子類別</span><span class="sxs-lookup"><span data-stu-id="940e2-239">SubCategory</span></span>|<span data-ttu-id="940e2-240">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-240">String</span></span>|<span data-ttu-id="940e2-241">此屬性指定在 **[子類別]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="940e2-241">This property specifies the value that's displayed in the **Sub category** file plan descriptor.</span></span>|
   |<span data-ttu-id="940e2-242">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="940e2-242">AuthorityType</span></span>|<span data-ttu-id="940e2-243">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-243">String</span></span>|<span data-ttu-id="940e2-244">此屬性指定在 **[授權單位類型]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="940e2-244">This property specifies the value that's displayed in the **Authority type** file plan descriptor.</span></span>|
   |<span data-ttu-id="940e2-245">CitationName</span><span class="sxs-lookup"><span data-stu-id="940e2-245">CitationName</span></span>|<span data-ttu-id="940e2-246">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-246">String</span></span>|<span data-ttu-id="940e2-247">此屬性指定在 **[條款/引文]** 檔案計劃描述元中顯示的引文名稱，例如「2002 年的沙賓法案」。</span><span class="sxs-lookup"><span data-stu-id="940e2-247">This property specifies the name of the citation displayed in the **Provision/citation** file plan descriptor; for example "Sarbanes-Oxley Act or 2002".</span></span> |
   |<span data-ttu-id="940e2-248">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="940e2-248">CitationUrl</span></span>|<span data-ttu-id="940e2-249">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-249">String</span></span>|<span data-ttu-id="940e2-250">此屬性指定在 **[條款/引文]** 檔案計劃描述元中顯示的 URL。</span><span class="sxs-lookup"><span data-stu-id="940e2-250">This property specifies the URL that's displayed in the **Provision/citation** file plan descriptor.</span></span>|
   |<span data-ttu-id="940e2-251">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="940e2-251">CitationJurisdiction</span></span>|<span data-ttu-id="940e2-252">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-252">String</span></span>|<span data-ttu-id="940e2-253">此屬性指定在 **[條款/引文]** 檔案計劃描述元中顯示的管轄單位或代理機構；例如「美國證券交易委員會 (SEC)」。</span><span class="sxs-lookup"><span data-stu-id="940e2-253">This property specifies the jurisdiction or agency that's displayed in the **Provision/citation** file plan descriptor; for example, "U.S. Securities and Exchange Commission (SEC)".</span></span>|
   |<span data-ttu-id="940e2-254">Regulatory</span><span class="sxs-lookup"><span data-stu-id="940e2-254">Regulatory</span></span>|<span data-ttu-id="940e2-255">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-255">String</span></span>|<span data-ttu-id="940e2-256">保留空白。</span><span class="sxs-lookup"><span data-stu-id="940e2-256">Leave blank.</span></span> <span data-ttu-id="940e2-257">目前無法使用此屬性。</span><span class="sxs-lookup"><span data-stu-id="940e2-257">This property isn't used at this time.</span></span>|
   |<span data-ttu-id="940e2-258">EventType</span><span class="sxs-lookup"><span data-stu-id="940e2-258">EventType</span></span>|<span data-ttu-id="940e2-259">字串</span><span class="sxs-lookup"><span data-stu-id="940e2-259">String</span></span>|<span data-ttu-id="940e2-260">此屬性會指定與標籤相關聯的保留規則。</span><span class="sxs-lookup"><span data-stu-id="940e2-260">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="940e2-261">您可以使用唯一識別規則的任何值。</span><span class="sxs-lookup"><span data-stu-id="940e2-261">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="940e2-262">例如：</span><span class="sxs-lookup"><span data-stu-id="940e2-262">For example:</span></span></br><span data-ttu-id="940e2-263">**Name**</span><span class="sxs-lookup"><span data-stu-id="940e2-263">**Name**</span></span></br><span data-ttu-id="940e2-264">**Distinguished name (DN)**</span><span class="sxs-lookup"><span data-stu-id="940e2-264">**Distinguished name (DN)**</span></span></br><span data-ttu-id="940e2-265">**GUID**</span><span class="sxs-lookup"><span data-stu-id="940e2-265">**GUID**</span></span> </br><span data-ttu-id="940e2-266">您可以使用 [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule?view=exchange-ps) Cmdlet 來檢視可用的保留規則。</span><span class="sxs-lookup"><span data-stu-id="940e2-266">You can use the [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available retention rules.</span></span> <span data-ttu-id="940e2-267">請注意，如果從某組織中匯出標籤，在將標籤匯入至另​​一個組織時，不可使用該組織的 EventType 屬性值。</span><span class="sxs-lookup"><span data-stu-id="940e2-267">Note that if you export labels from one organization, you can't use the values for the EventType  property from that organization when importing labels to a different organization.</span></span> <span data-ttu-id="940e2-268">這是因為對組織而言 EventType 值是唯一的。</span><span class="sxs-lookup"><span data-stu-id="940e2-268">That because the EventType values are unique to an organization.</span></span> |
   |||

   <span data-ttu-id="940e2-269">以下是含有保留標籤相關資訊的範本範例。</span><span class="sxs-lookup"><span data-stu-id="940e2-269">Here's an example the template containing the information about retention labels.</span></span>

   ![已填入資訊的檔案計劃範本](../media/file-plan-filled-out-template.png)

4. <span data-ttu-id="940e2-271">在匯入檔案計劃精靈頁面的步驟 3 下方，按一下 **[瀏覽檔案]** 以上傳填入的範本。</span><span class="sxs-lookup"><span data-stu-id="940e2-271">Under step 3 on the import file plan wizard page, click **Browse for files** to upload the filled-out template.</span></span> 

   <span data-ttu-id="940e2-272">檔案計劃管理員會驗證項目並且顯示匯入統計資料。</span><span class="sxs-lookup"><span data-stu-id="940e2-272">File plan manager will validate the entries and display the import statistics.</span></span>

   ![檔案計劃匯入統計資料](../media/file-plan-import-statistics.png)

   <span data-ttu-id="940e2-274">萬一有驗證錯誤，檔案計劃匯入將會繼續驗證匯入檔案中的每個項目，並在匯入檔案中顯示參考行/列數的所有錯誤、複製顯示的錯誤結果，讓您可以輕鬆地返回匯入檔案並更正錯誤。</span><span class="sxs-lookup"><span data-stu-id="940e2-274">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easily return to the import file and correct the errors.</span></span>

5. <span data-ttu-id="940e2-275">匯入完成後，返回檔案計劃管理員，讓新的保留標籤與新的或現有的保留標籤原則產生關聯。</span><span class="sxs-lookup"><span data-stu-id="940e2-275">When the import is complete, return to file plan manager to associate the new retention labels to new or existing retention label policies.</span></span>

   ![發佈標籤的選項](../media/file-plan-publish-labels-option.png)
