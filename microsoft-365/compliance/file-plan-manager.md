---
title: 檔案計劃管理員的概觀
ms.author: stephow
author: stephow-MSFT
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
ms.openlocfilehash: 38bfb1e6a6cde931804e518660ddf6c2b45205b0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077147"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="ae72f-103">檔案計劃管理員的概觀</span><span class="sxs-lookup"><span data-stu-id="ae72f-103">Overview of file plan manager</span></span>

<span data-ttu-id="ae72f-104">檔案計劃管理員提供對於保留標籤、保留標籤原則的進階管理功能，並且提供整合的方式讓標籤和標籤至內容活動周遊整個內容生命週期 – 從建立、共同作業、記錄宣告、保留，到最終的處置。</span><span class="sxs-lookup"><span data-stu-id="ae72f-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![檔案計劃頁面](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="ae72f-106">存取檔案計劃管理員</span><span class="sxs-lookup"><span data-stu-id="ae72f-106">Accessing file plan manager</span></span>

<span data-ttu-id="ae72f-107">存取檔案計劃管理員有兩個需求，需求如下：</span><span class="sxs-lookup"><span data-stu-id="ae72f-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="ae72f-108">Office 365 企業版 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="ae72f-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="ae72f-109">使用者已獲指派「安全性與合規性中心」的下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="ae72f-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span>
    - <span data-ttu-id="ae72f-110">保留管理員</span><span class="sxs-lookup"><span data-stu-id="ae72f-110">Retention Manager</span></span>
    - <span data-ttu-id="ae72f-111">僅檢視保留管理員</span><span class="sxs-lookup"><span data-stu-id="ae72f-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="ae72f-112">預設保留標籤和標籤原則</span><span class="sxs-lookup"><span data-stu-id="ae72f-112">Default retention labels and label policy</span></span>

<span data-ttu-id="ae72f-113">如果安全性與合規性中心中沒有保留標籤，第一次在左側導覽中選擇 [檔案計畫]\*\*\*\* 時，這會建立稱為**預設資料控管發佈原則**的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="ae72f-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="ae72f-114">此標籤原則包含三個保留標籤：</span><span class="sxs-lookup"><span data-stu-id="ae72f-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="ae72f-115">**作業程序**</span><span class="sxs-lookup"><span data-stu-id="ae72f-115">**Operational procedure**</span></span>
- <span data-ttu-id="ae72f-116">**一般業務**</span><span class="sxs-lookup"><span data-stu-id="ae72f-116">**Business general**</span></span>
- <span data-ttu-id="ae72f-117">**合約協定**</span><span class="sxs-lookup"><span data-stu-id="ae72f-117">**Contract agreement**</span></span>

<span data-ttu-id="ae72f-118">設定這些保留標籤只是為了保留內容，而非刪除內容。</span><span class="sxs-lookup"><span data-stu-id="ae72f-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="ae72f-119">此標籤原則將發佈到整個組織，並可加以停用或移除。</span><span class="sxs-lookup"><span data-stu-id="ae72f-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="ae72f-120">您可以判斷誰開啟了檔案計畫管理員並開始了初次執行體驗，方法是檢閱活動 [建立保留原則]\*\*\*\* 和 [為保留原則建立了保留組態]\*\*\*\* 的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="ae72f-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="ae72f-121">由於客戶的意見反應，我們已移除了會建立預設保留標籤和以上所提及的保留標籤原則的這項功能。</span><span class="sxs-lookup"><span data-stu-id="ae72f-121">Due to customer feedback, we have removed this feature that creates the default retention labels and label policy mentioned above.</span></span> <span data-ttu-id="ae72f-122">只有在 2019 年 4 月 11 日之前開啟檔案計劃管理員的情況下，才會看到這些保留標籤和保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="ae72f-122">You will only see this policy and labels if you used file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="ae72f-123">瀏覽您的檔案計劃</span><span class="sxs-lookup"><span data-stu-id="ae72f-123">Navigating your file plan</span></span>

<span data-ttu-id="ae72f-124">檔案計劃管理員可讓您更輕鬆地從單一檢視，查看所有保留標籤和原則及其設定。</span><span class="sxs-lookup"><span data-stu-id="ae72f-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="ae72f-125">請注意，在檔案計劃外部所建立的保留標籤可以在檔案計劃中使用，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ae72f-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="ae72f-126">在 [檔案計劃標籤]\*\*\*\* 索引標籤上，下列額外資訊和功能可供使用：</span><span class="sxs-lookup"><span data-stu-id="ae72f-126">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="ae72f-127">標籤設定資料行</span><span class="sxs-lookup"><span data-stu-id="ae72f-127">Label settings columns</span></span>

- <span data-ttu-id="ae72f-p103">[根據]\*\*\*\* 會識別觸發程序類型，該觸發程序會開始保留期間。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="ae72f-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="ae72f-130">事件</span><span class="sxs-lookup"><span data-stu-id="ae72f-130">Event</span></span>
    - <span data-ttu-id="ae72f-131">建立時機</span><span class="sxs-lookup"><span data-stu-id="ae72f-131">When created</span></span>
    - <span data-ttu-id="ae72f-132">上次修改時間</span><span class="sxs-lookup"><span data-stu-id="ae72f-132">When last modified</span></span>
    - <span data-ttu-id="ae72f-133">套用標籤時機</span><span class="sxs-lookup"><span data-stu-id="ae72f-133">When labeled</span></span>
- <span data-ttu-id="ae72f-p104">[記錄]\*\*\*\* 會識別項目是否會在套用標籤時變成宣告的記錄。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="ae72f-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="ae72f-136">否</span><span class="sxs-lookup"><span data-stu-id="ae72f-136">No</span></span>
    - <span data-ttu-id="ae72f-137">是</span><span class="sxs-lookup"><span data-stu-id="ae72f-137">Yes</span></span>
    - <span data-ttu-id="ae72f-138">Yes(Regulatory)</span><span class="sxs-lookup"><span data-stu-id="ae72f-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="ae72f-p105">[保留]\*\*\*\* 會識別保留類型。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="ae72f-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="ae72f-141">保留</span><span class="sxs-lookup"><span data-stu-id="ae72f-141">Keep</span></span>
    - <span data-ttu-id="ae72f-142">保留與刪除</span><span class="sxs-lookup"><span data-stu-id="ae72f-142">Keep and delete</span></span>
    - <span data-ttu-id="ae72f-143">刪除</span><span class="sxs-lookup"><span data-stu-id="ae72f-143">Delete</span></span>
- <span data-ttu-id="ae72f-p106">[處置]\*\*\*\* 會識別保留期間結束時內容會發生什麼情形。有效的值是：</span><span class="sxs-lookup"><span data-stu-id="ae72f-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="ae72f-146">Null</span><span class="sxs-lookup"><span data-stu-id="ae72f-146">null</span></span>
    - <span data-ttu-id="ae72f-147">不執行任何動作</span><span class="sxs-lookup"><span data-stu-id="ae72f-147">No action</span></span>
    - <span data-ttu-id="ae72f-148">自動刪除</span><span class="sxs-lookup"><span data-stu-id="ae72f-148">Auto-delete</span></span>
    - <span data-ttu-id="ae72f-149">需要檢閱 (也稱為處置檢閱)</span><span class="sxs-lookup"><span data-stu-id="ae72f-149">Review required (aka Disposition review)</span></span>

![檔案計劃中的標籤設定](media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="ae72f-151">保留標籤檔案計劃描述元資料行</span><span class="sxs-lookup"><span data-stu-id="ae72f-151">Label file plan descriptors columns</span></span>

<span data-ttu-id="ae72f-p107">您現在可以在保留標籤組態中包含詳細資訊。將檔案計劃描述元插入保留標籤可以改善檔案計劃的管理性和組織。</span><span class="sxs-lookup"><span data-stu-id="ae72f-p107">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="ae72f-p108">為了讓您開始使用，檔案計劃管理員會為以下項目提供現成的值：函式/部門、分類、授權類型和佈建/引文。您可以在建立或編輯保留標籤時新增檔案計劃描述元值。</span><span class="sxs-lookup"><span data-stu-id="ae72f-p108">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="ae72f-156">以下是建立或編輯保留標籤時的檔案計劃描述元步驟檢視。</span><span class="sxs-lookup"><span data-stu-id="ae72f-156">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![檔案計劃描述元](media/file-plan-descriptors.png)

<span data-ttu-id="ae72f-158">以下是檔案計劃管理員的標籤索引標籤上，檔案計劃描述元的檢視。</span><span class="sxs-lookup"><span data-stu-id="ae72f-158">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="ae72f-160">匯出所有現有的保留標籤以分析及/或執行離線檢閱</span><span class="sxs-lookup"><span data-stu-id="ae72f-160">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="ae72f-161">您可以從檔案計劃管理員將所有保留標籤的詳細資料匯出至 .csv 檔案，以協助您加速與貴組織中資料控管專案關係人進行的定期合規性檢閱。</span><span class="sxs-lookup"><span data-stu-id="ae72f-161">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="ae72f-162">若要匯出所有保留標籤，請移至 [檔案計劃管理員]\*\*\*\* \> [檔案計劃動作]\*\*\*\* \> [匯出標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ae72f-162">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![匯出檔案計劃的選項](media/file-plan-export-labels-option.png)

<span data-ttu-id="ae72f-164">包含所有現有保留標籤的 \*.csv 檔案隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="ae72f-164">A \*.csv file containing all existing retention labels will open.</span></span>

![顯示所有保留標籤的 CSV 檔案](media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="ae72f-166">將保留標籤匯入至您的檔案計劃</span><span class="sxs-lookup"><span data-stu-id="ae72f-166">Import labels into your file plan</span></span>

<span data-ttu-id="ae72f-167">您可以從檔案計劃管理員大量匯入新的保留標籤，以及修改現有的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="ae72f-167">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="ae72f-168">若要匯入新的保留標籤並更新現有的保留標籤，請移至 [檔案計劃管理員]\*\*\*\* \> [檔案計劃動作]\*\*\*\* \> [匯入標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ae72f-168">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![匯入檔案計劃的選項](media/file-plan-import-labels-option.png)

![下載空白檔案計劃範本的選項](media/file-plan-blank-template-option.png)

<span data-ttu-id="ae72f-171">下載空白範本 (或從匯出目前的檔案計劃開始)。</span><span class="sxs-lookup"><span data-stu-id="ae72f-171">Download a blank template (or start from an export of your current file plan).</span></span>

![在 Excel 中開啟空白檔案計劃範本](media/file-plan-blank-template.png)

<span data-ttu-id="ae72f-173">填寫範本。</span><span class="sxs-lookup"><span data-stu-id="ae72f-173">Fill-out the template.</span></span> <span data-ttu-id="ae72f-174">下表提供有效的值。</span><span class="sxs-lookup"><span data-stu-id="ae72f-174">This table provides valid values.</span></span>

|<span data-ttu-id="ae72f-175">**屬性**</span><span class="sxs-lookup"><span data-stu-id="ae72f-175">**Property**</span></span>|<span data-ttu-id="ae72f-176">**類型**</span><span class="sxs-lookup"><span data-stu-id="ae72f-176">**Type**</span></span>|<span data-ttu-id="ae72f-177">**有效值**</span><span class="sxs-lookup"><span data-stu-id="ae72f-177">**Valid values**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ae72f-178">LabelName</span><span class="sxs-lookup"><span data-stu-id="ae72f-178">LabelName</span></span>|<span data-ttu-id="ae72f-179">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-179">String</span></span>|<span data-ttu-id="ae72f-180">如果值包含空格，請使用引號 (") 括住值。</span><span class="sxs-lookup"><span data-stu-id="ae72f-180">If the value contains spaces, enclose the value in quotation marks (").</span></span>|
|<span data-ttu-id="ae72f-181">註解</span><span class="sxs-lookup"><span data-stu-id="ae72f-181">Comment</span></span>|<span data-ttu-id="ae72f-182">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-182">String</span></span>|<span data-ttu-id="ae72f-183">如果值包含空格，請使用引號 (") 括住值。</span><span class="sxs-lookup"><span data-stu-id="ae72f-183">If the value contains spaces, enclose the value in quotation marks (").</span></span> |
|<span data-ttu-id="ae72f-184">記事</span><span class="sxs-lookup"><span data-stu-id="ae72f-184">Notes</span></span>|<span data-ttu-id="ae72f-185">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-185">String</span></span>|<span data-ttu-id="ae72f-186">自訂</span><span class="sxs-lookup"><span data-stu-id="ae72f-186">Custom</span></span>|
|<span data-ttu-id="ae72f-187">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="ae72f-187">IsRecordLabel</span></span>|<span data-ttu-id="ae72f-188">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-188">String</span></span>|<span data-ttu-id="ae72f-189">$true: The label is a record label.</span><span class="sxs-lookup"><span data-stu-id="ae72f-189">The 
                IsRecordLabel
              parameter specifies whether the label is a record label.</span></span></br><span data-ttu-id="ae72f-190">$false：該標籤不是記錄標籤。</span><span class="sxs-lookup"><span data-stu-id="ae72f-190">$false: The label isn't a record label.</span></span> <span data-ttu-id="ae72f-191">這是預設值。</span><span class="sxs-lookup"><span data-stu-id="ae72f-191">This is the default value.</span></span>|
|<span data-ttu-id="ae72f-192">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="ae72f-192">RetentionAction</span></span>|<span data-ttu-id="ae72f-193">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-193">String</span></span>|<span data-ttu-id="ae72f-194">刪除</span><span class="sxs-lookup"><span data-stu-id="ae72f-194">Delete</span></span></br><span data-ttu-id="ae72f-195">保留</span><span class="sxs-lookup"><span data-stu-id="ae72f-195">Keep</span></span></br><span data-ttu-id="ae72f-196">KeepAndDelete</span><span class="sxs-lookup"><span data-stu-id="ae72f-196">KeepAndDelete</span></span> |
|<span data-ttu-id="ae72f-197">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="ae72f-197">RetentionDuration</span></span>|<span data-ttu-id="ae72f-198">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-198">String</span></span>|<span data-ttu-id="ae72f-199">此屬性會指定要保留內容的天數。</span><span class="sxs-lookup"><span data-stu-id="ae72f-199">The RetentionDuration parameter specifies the number of days to retain the content.</span></span> <span data-ttu-id="ae72f-200">有效值為：</span><span class="sxs-lookup"><span data-stu-id="ae72f-200">Valid values are:</span></span></br><span data-ttu-id="ae72f-201">正整數。</span><span class="sxs-lookup"><span data-stu-id="ae72f-201">A positive integer.</span></span></br><span data-ttu-id="ae72f-202">不限任何值。</span><span class="sxs-lookup"><span data-stu-id="ae72f-202">The default value is unlimited.</span></span>|
|<span data-ttu-id="ae72f-203">RetentionType</span><span class="sxs-lookup"><span data-stu-id="ae72f-203">RetentionType</span></span>|<span data-ttu-id="ae72f-204">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-204">String</span></span>|<span data-ttu-id="ae72f-205">此屬性會指定保留期限是否從內容建立日期、標籤 (標記) 日期或上次修改日期開始算起。</span><span class="sxs-lookup"><span data-stu-id="ae72f-205">The RetentionType parameter specifies whether the retention duration is calculated  from the content creation date, tagged date, or last modification date.</span></span> <span data-ttu-id="ae72f-206">有效值為：</span><span class="sxs-lookup"><span data-stu-id="ae72f-206">Valid values are:</span></span></br><span data-ttu-id="ae72f-207">CreationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="ae72f-207">CreationAgeInDays</span></span></br><span data-ttu-id="ae72f-208">EventAgeInDays</span><span class="sxs-lookup"><span data-stu-id="ae72f-208">EventAgeInDays</span></span></br><span data-ttu-id="ae72f-209">ModificationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="ae72f-209">ModificationAgeInDays</span></span></br><span data-ttu-id="ae72f-210">TaggedAgeInDays</span><span class="sxs-lookup"><span data-stu-id="ae72f-210">TaggedAgeInDays</span></span> |
|<span data-ttu-id="ae72f-211">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="ae72f-211">ReviewerEmail</span></span>|<span data-ttu-id="ae72f-212">SmtpAddress[]</span><span class="sxs-lookup"><span data-stu-id="ae72f-212">SmtpAddress</span></span>|<span data-ttu-id="ae72f-213">此屬性會指定 Delete 和 KeepAndDelete 保留動作檢閱者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ae72f-213">The ReviewerEmail parameter specifies the email address of a reviewer for Delete and KeepAndDelete retention actions.</span></span> <span data-ttu-id="ae72f-214">您可以指定多個以逗號隔開的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ae72f-214">You can specify multiple email addresses separated by commas.</span></span>|
|<span data-ttu-id="ae72f-215">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="ae72f-215">ReferenceId</span></span>|<span data-ttu-id="ae72f-216">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-216">String</span></span>|<span data-ttu-id="ae72f-217">自訂</span><span class="sxs-lookup"><span data-stu-id="ae72f-217">Custom</span></span>|
|<span data-ttu-id="ae72f-218">Departmentname</span><span class="sxs-lookup"><span data-stu-id="ae72f-218">DepartmentName</span></span>|<span data-ttu-id="ae72f-219">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-219">String</span></span>|<span data-ttu-id="ae72f-220">自訂</span><span class="sxs-lookup"><span data-stu-id="ae72f-220">Custom</span></span>|
|<span data-ttu-id="ae72f-221">類別</span><span class="sxs-lookup"><span data-stu-id="ae72f-221">Category</span></span>|<span data-ttu-id="ae72f-222">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-222">String</span></span>|<span data-ttu-id="ae72f-223">自訂</span><span class="sxs-lookup"><span data-stu-id="ae72f-223">Custom</span></span>|
|<span data-ttu-id="ae72f-224">類別</span><span class="sxs-lookup"><span data-stu-id="ae72f-224">SubCategory</span></span>|<span data-ttu-id="ae72f-225">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-225">String</span></span>|<span data-ttu-id="ae72f-226">自訂</span><span class="sxs-lookup"><span data-stu-id="ae72f-226">Custom</span></span>|
|<span data-ttu-id="ae72f-227">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="ae72f-227">AuthorityType</span></span>|<span data-ttu-id="ae72f-228">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-228">String</span></span>|<span data-ttu-id="ae72f-229">自訂</span><span class="sxs-lookup"><span data-stu-id="ae72f-229">Custom</span></span>|
|<span data-ttu-id="ae72f-230">CitationName</span><span class="sxs-lookup"><span data-stu-id="ae72f-230">CitationName</span></span>|<span data-ttu-id="ae72f-231">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-231">String</span></span>|<span data-ttu-id="ae72f-232">自訂</span><span class="sxs-lookup"><span data-stu-id="ae72f-232">Custom</span></span>|
|<span data-ttu-id="ae72f-233">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="ae72f-233">CitationUrl</span></span>|<span data-ttu-id="ae72f-234">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-234">String</span></span>|<span data-ttu-id="ae72f-235">自訂</span><span class="sxs-lookup"><span data-stu-id="ae72f-235">Custom</span></span>|
|<span data-ttu-id="ae72f-236">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="ae72f-236">CitationJurisdiction</span></span>|<span data-ttu-id="ae72f-237">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-237">String</span></span>|<span data-ttu-id="ae72f-238">自訂</span><span class="sxs-lookup"><span data-stu-id="ae72f-238">Custom</span></span>|
|<span data-ttu-id="ae72f-239">Regulatory</span><span class="sxs-lookup"><span data-stu-id="ae72f-239">Regulatory</span></span>|<span data-ttu-id="ae72f-240">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-240">String</span></span>|<span data-ttu-id="ae72f-241">自訂</span><span class="sxs-lookup"><span data-stu-id="ae72f-241">Custom</span></span>|
|<span data-ttu-id="ae72f-242">EventType</span><span class="sxs-lookup"><span data-stu-id="ae72f-242">EventType</span></span>|<span data-ttu-id="ae72f-243">字串</span><span class="sxs-lookup"><span data-stu-id="ae72f-243">String</span></span>|<span data-ttu-id="ae72f-244">此屬性會指定與標籤相關聯的保留規則。</span><span class="sxs-lookup"><span data-stu-id="ae72f-244">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="ae72f-245">您可以使用唯一識別規則的任何值。</span><span class="sxs-lookup"><span data-stu-id="ae72f-245">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="ae72f-246">例如：</span><span class="sxs-lookup"><span data-stu-id="ae72f-246">For example:</span></span></br><span data-ttu-id="ae72f-247">名稱</span><span class="sxs-lookup"><span data-stu-id="ae72f-247">Name</span></span></br><span data-ttu-id="ae72f-248">辨別名稱 (DN)</span><span class="sxs-lookup"><span data-stu-id="ae72f-248">Distinguished name (DN)</span></span></br><span data-ttu-id="ae72f-249">GUID</span><span class="sxs-lookup"><span data-stu-id="ae72f-249">GUID</span></span> </br><span data-ttu-id="ae72f-250">您可以使用 [Get-RetentionComplianceRule](https://docs.microsoft.com/zh-TW/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) Cmdlet 來檢視可用的保留規則。</span><span class="sxs-lookup"><span data-stu-id="ae72f-250">You can use the [Get-RetentionComplianceRule](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available retention rules.</span></span>|

![已填入資訊的檔案計劃範本](media/file-plan-filled-out-template.png)

<span data-ttu-id="ae72f-252">上傳已填入資訊的範本，檔案計劃管理員會驗證項目並且顯示匯入統計資料。</span><span class="sxs-lookup"><span data-stu-id="ae72f-252">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![檔案計劃匯入統計資料](media/file-plan-import-statistics.png)

<span data-ttu-id="ae72f-254">萬一有驗證錯誤，檔案計劃匯入將會繼續驗證匯入檔案中的每個項目，並在匯入檔案中顯示參考行/列數的所有錯誤、複製顯示的錯誤結果，讓您可以輕鬆地返回匯入檔案並更正錯誤。</span><span class="sxs-lookup"><span data-stu-id="ae72f-254">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easilly return to the import file and correct the errors.</span></span> 

<span data-ttu-id="ae72f-255">匯入完成後，返回檔案計劃管理員，讓新的保留標籤與新的或現有的保留標籤原則產生關聯。</span><span class="sxs-lookup"><span data-stu-id="ae72f-255">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![發佈標籤的選項](media/file-plan-publish-labels-option.png)

