---
title: 使用檔案計畫管理整個內容生命週期的保留標籤
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
description: 檔案計畫為保留標籤提供進階管理功能。
ms.custom: seo-marvel-may2020
ms.openlocfilehash: a92f835658bdeedbc64d3d4f2349900e30ec6dda
ms.sourcegitcommit: 2b8c3fc39a7cbd4ca35e98dca430d2470cd2c925
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "47427022"
---
# <a name="use-file-plan-to-manage-retention-labels"></a><span data-ttu-id="a46a3-103">使用檔案計畫來管理保留標籤</span><span class="sxs-lookup"><span data-stu-id="a46a3-103">Use file plan to manage retention labels</span></span>

><span data-ttu-id="a46a3-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="a46a3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a46a3-105">雖然您可以透過 Microsoft 365 合規性中心的 [資訊控管]\*\*\*\* 建立及管理保留標籤，但來自 [記錄管理]\*\*\*\* 的檔案計畫還具有額外的管理功能：</span><span class="sxs-lookup"><span data-stu-id="a46a3-105">Although you can create and manage retention labels from **Information governance** in the Microsoft 365 compliance center, file plan from **Records management** has additional management capabilities:</span></span>

- <span data-ttu-id="a46a3-106">您可以從試算表匯入相關資訊，大量建立保留標籤。</span><span class="sxs-lookup"><span data-stu-id="a46a3-106">You can bulk-create retention labels by importing the relevant information from a spreadsheet.</span></span>

- <span data-ttu-id="a46a3-107">您可以從現有保留標籤匯出資訊，以便進行分析和離線共同作業或進行大量編輯。</span><span class="sxs-lookup"><span data-stu-id="a46a3-107">You can export the information from existing retention labels for analysis and offline collaboration, or for bulk-editing.</span></span>

- <span data-ttu-id="a46a3-108">有關保留標籤的詳細資訊將會顯示，讓您可以從一個檢視輕鬆查看所有保留標籤的各項設定。</span><span class="sxs-lookup"><span data-stu-id="a46a3-108">More information about the retention labels is displayed to make it easier to see into and across the settings of all your retention labels from one view.</span></span>

- <span data-ttu-id="a46a3-109">檔案計畫描述元針對每個標籤支援額外和選用的資訊。</span><span class="sxs-lookup"><span data-stu-id="a46a3-109">File plan descriptors support additional and optional information for each label.</span></span>

<span data-ttu-id="a46a3-110">檔案計畫可用於所有保留標籤，即使它們不會將內容標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="a46a3-110">File plan can be used for all retention labels, even if they don't mark content as a record.</span></span>

![檔案計畫頁面](../media/compliance-file-plan.png)

<span data-ttu-id="a46a3-112">如需有關保留標籤為何及其使用方式的相關資訊，請參閱[瞭解保留原則及保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="a46a3-112">For information about what retention labels are and how to use them, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="accessing-file-plan"></a><span data-ttu-id="a46a3-113">存取檔案計畫</span><span class="sxs-lookup"><span data-stu-id="a46a3-113">Accessing file plan</span></span>

<span data-ttu-id="a46a3-114">若要存取檔案計畫，您必須擁有下列其中一種系統管理員角色：</span><span class="sxs-lookup"><span data-stu-id="a46a3-114">To access file plan, you must have one of the following admin roles:</span></span>
    
- <span data-ttu-id="a46a3-115">保留管理員</span><span class="sxs-lookup"><span data-stu-id="a46a3-115">Retention Manager</span></span>

- <span data-ttu-id="a46a3-116">僅檢視保留管理員</span><span class="sxs-lookup"><span data-stu-id="a46a3-116">View-only Retention Manager</span></span>

<span data-ttu-id="a46a3-117">在 Microsoft 365 合規性中心中，移至 [解決方案]\*\*\*\*  >  [記錄管理]\*\*\*\*  >  [檔案計畫]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a46a3-117">In the Microsoft 365 compliance center, go to **Solutions** > **Records management** > **File plan**.</span></span> 

<span data-ttu-id="a46a3-118">如果功能窗格中未顯示 [記錄管理]\*\*\*\*，請先向下捲動，然後選取 [顯示全部]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a46a3-118">If **Records management** doesn't display in the navigation pane, first scroll down, and select **Show all**.</span></span>

![檔案計畫頁面](../media/compliance-file-plan.png)

## <a name="navigating-your-file-plan"></a><span data-ttu-id="a46a3-120">瀏覽您的檔案計畫</span><span class="sxs-lookup"><span data-stu-id="a46a3-120">Navigating your file plan</span></span>

<span data-ttu-id="a46a3-121">如果您已透過 Microsoft 365 合規性中心的 [資訊控管]\*\*\*\* 建立保留標籤，則這些標籤會自動顯示在您的檔案計畫中。</span><span class="sxs-lookup"><span data-stu-id="a46a3-121">If you've already created retention labels from **Information governance** in the Microsoft 365 compliance center, these labels automatically display in your file plan.</span></span> 

<span data-ttu-id="a46a3-122">同樣地，如果您現在在檔案計畫中建立保留標籤，如果未將標籤設定為將內容標示為記錄，則也可以從 [資訊控管]\*\*\*\* 中取得。</span><span class="sxs-lookup"><span data-stu-id="a46a3-122">Similarly, if you now create retention labels in file plan, they are also available from **Information governance** if the labels aren't configured to mark content as a record.</span></span>

<span data-ttu-id="a46a3-123">在 [檔案計畫]\*\*\*\* 頁面上，您會看到所有標籤，具有其狀態和設定、選用的檔案計畫描述元、用來分析或啟用標籤離線檢閱的匯出選項，以及用來建立保留標籤的匯入選項。</span><span class="sxs-lookup"><span data-stu-id="a46a3-123">On the **File plan** page, you see all your labels with their status and settings, optional file plan descriptors, an export option to analyze or enable offline reviews of your labels, and an import option to create retention labels.</span></span> 

### <a name="label-settings-columns"></a><span data-ttu-id="a46a3-124">標籤設定欄</span><span class="sxs-lookup"><span data-stu-id="a46a3-124">Label settings columns</span></span>

<span data-ttu-id="a46a3-125">除了標籤 [名稱]\*\*\*\* 以外的所有欄，都可以透過選取 [自訂欄]\*\*\*\* 選項來顯示或隱藏。</span><span class="sxs-lookup"><span data-stu-id="a46a3-125">All columns except the label **Name** can be displayed or hidden by selecting the **Customize columns** option.</span></span> <span data-ttu-id="a46a3-126">但根據預設，前幾欄會顯示標籤狀態及其設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="a46a3-126">But by default, the first few columns display information about the label status and its settings:</span></span> 

- <span data-ttu-id="a46a3-127">[狀態]\*\*\*\* 可識別標籤是否包含在標籤原則或自動套用原則中 (**作用中**) 與否 (**非作用中**)。</span><span class="sxs-lookup"><span data-stu-id="a46a3-127">**Status** identifies whether the label is included in a label policy or auto-apply policy (**Active**) or not (**Inactive**).</span></span>

- <span data-ttu-id="a46a3-128">[根據]\*\*\*\* 可識別保留期間如何與何時開始。</span><span class="sxs-lookup"><span data-stu-id="a46a3-128">**Based on** identifies how or when the retention period begins.</span></span> <span data-ttu-id="a46a3-129">有效值：</span><span class="sxs-lookup"><span data-stu-id="a46a3-129">Valid values:</span></span>
    - <span data-ttu-id="a46a3-130">事件</span><span class="sxs-lookup"><span data-stu-id="a46a3-130">Event</span></span>
    - <span data-ttu-id="a46a3-131">建立時機</span><span class="sxs-lookup"><span data-stu-id="a46a3-131">When created</span></span>
    - <span data-ttu-id="a46a3-132">上次修改日期</span><span class="sxs-lookup"><span data-stu-id="a46a3-132">Last modified</span></span>
    - <span data-ttu-id="a46a3-133">已套用標籤時</span><span class="sxs-lookup"><span data-stu-id="a46a3-133">When labeled</span></span>

- <span data-ttu-id="a46a3-134">[記錄中]\*\*\*\* 可識別套用標籤時，項目是否標記為記錄。</span><span class="sxs-lookup"><span data-stu-id="a46a3-134">**Is record** identifies if the item is marked as a record when the label is applied.</span></span> <span data-ttu-id="a46a3-135">有效值：</span><span class="sxs-lookup"><span data-stu-id="a46a3-135">Valid values:</span></span>
    - <span data-ttu-id="a46a3-136">否</span><span class="sxs-lookup"><span data-stu-id="a46a3-136">No</span></span>
    - <span data-ttu-id="a46a3-137">是</span><span class="sxs-lookup"><span data-stu-id="a46a3-137">Yes</span></span>

- <span data-ttu-id="a46a3-138">[保留期間]\*\*\*\* 可識別保留期間。</span><span class="sxs-lookup"><span data-stu-id="a46a3-138">**Retention duration** identifies the retention period.</span></span> <span data-ttu-id="a46a3-139">有效值：</span><span class="sxs-lookup"><span data-stu-id="a46a3-139">Valid values:</span></span>
    - <span data-ttu-id="a46a3-140">天</span><span class="sxs-lookup"><span data-stu-id="a46a3-140">Days</span></span>
    - <span data-ttu-id="a46a3-141">月</span><span class="sxs-lookup"><span data-stu-id="a46a3-141">Months</span></span>
    - <span data-ttu-id="a46a3-142">年</span><span class="sxs-lookup"><span data-stu-id="a46a3-142">Years</span></span>
    - <span data-ttu-id="a46a3-143">永久</span><span class="sxs-lookup"><span data-stu-id="a46a3-143">Forever</span></span>
    - <span data-ttu-id="a46a3-144">無</span><span class="sxs-lookup"><span data-stu-id="a46a3-144">None</span></span>

- <span data-ttu-id="a46a3-145">[處置類型]\*\*\*\* 可識別保留期間結束時，內容會發生什麼情形。</span><span class="sxs-lookup"><span data-stu-id="a46a3-145">**Disposition type** identifies what happens to the content at the end of the retention period.</span></span> <span data-ttu-id="a46a3-146">有效值：</span><span class="sxs-lookup"><span data-stu-id="a46a3-146">Valid values:</span></span>
    - <span data-ttu-id="a46a3-147">不執行任何動作</span><span class="sxs-lookup"><span data-stu-id="a46a3-147">No action</span></span>
    - <span data-ttu-id="a46a3-148">自動刪除</span><span class="sxs-lookup"><span data-stu-id="a46a3-148">Auto-delete</span></span>
    - <span data-ttu-id="a46a3-149">需要檢閱</span><span class="sxs-lookup"><span data-stu-id="a46a3-149">Review required</span></span>

### <a name="file-plan-descriptors-columns"></a><span data-ttu-id="a46a3-150">檔案計畫描述元欄</span><span class="sxs-lookup"><span data-stu-id="a46a3-150">File plan descriptors columns</span></span>

<span data-ttu-id="a46a3-151">檔案計畫可讓您隨著保留標籤包含更多資訊。</span><span class="sxs-lookup"><span data-stu-id="a46a3-151">File plan lets you include more information as part of your retention labels.</span></span> <span data-ttu-id="a46a3-152">這些檔案計畫描述元提供更多可改善您要加上標籤之內容的可管理性和組織的選項。</span><span class="sxs-lookup"><span data-stu-id="a46a3-152">These file plan descriptors provide more options to improve the manageability and organization of the content you need to label.</span></span>

<span data-ttu-id="a46a3-153">根據預設，從 [參照識別碼]\*\*\*\* 開始，接下來的幾個欄會顯示這些檔案計畫描述元，供您在建立保留標籤或編輯現有標籤時指定。</span><span class="sxs-lookup"><span data-stu-id="a46a3-153">By default, starting with **Reference ID**, the next few columns display these file plan descriptors that you can specify when you create a retention label, or edit an existing label.</span></span> 

<span data-ttu-id="a46a3-154">為了讓您開始使用，以下檔案計畫描述元有一些現成可用的值：</span><span class="sxs-lookup"><span data-stu-id="a46a3-154">To get you started, there are some out-of-box values for the following file plan descriptors:</span></span> 
- <span data-ttu-id="a46a3-155">商務功能/部門</span><span class="sxs-lookup"><span data-stu-id="a46a3-155">Business function/department</span></span>
- <span data-ttu-id="a46a3-156">類別</span><span class="sxs-lookup"><span data-stu-id="a46a3-156">Category</span></span>
- <span data-ttu-id="a46a3-157">授權單位類型</span><span class="sxs-lookup"><span data-stu-id="a46a3-157">Authority type</span></span>
- <span data-ttu-id="a46a3-158">條款/引文</span><span class="sxs-lookup"><span data-stu-id="a46a3-158">Provision/citation</span></span> 

<span data-ttu-id="a46a3-159">建立或編輯保留標籤時，檔案計畫描述元的範例：</span><span class="sxs-lookup"><span data-stu-id="a46a3-159">Example of file plan descriptors when you create or edit a retention label:</span></span>

![建立或編輯保留標籤時的檔案計畫描述元](../media/file-plan-descriptors.png)

<span data-ttu-id="a46a3-161">檔案計畫描述元欄的範例檢視：</span><span class="sxs-lookup"><span data-stu-id="a46a3-161">Example view of the file plan descriptors columns:</span></span>

![檔案計畫描述元欄](../media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-retention-labels-to-analyze-or-enable-offline-reviews"></a><span data-ttu-id="a46a3-163">匯出所有保留標籤以分析或啟用離線檢閱</span><span class="sxs-lookup"><span data-stu-id="a46a3-163">Export all retention labels to analyze or enable offline reviews</span></span>

<span data-ttu-id="a46a3-164">您可以從檔案計畫，將所有保留標籤的詳細資料匯出至 .csv 檔案，以協助您加速與組織中資料控管專案關係人進行的定期合規性檢閱。</span><span class="sxs-lookup"><span data-stu-id="a46a3-164">From your file plan, you can export the details of all retention labels into a .csv file to help you facilitate periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="a46a3-165">若要匯出所有保留標籤：在 [檔案計畫]\*\*\*\* 頁面上，按一下 [匯出]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="a46a3-165">To export all retention labels: On the **File plan** page, click **Export**:</span></span>

![匯出檔案計畫的選項](../media/compliance-file-plan-export-labels.png)

<span data-ttu-id="a46a3-167">包含所有現有保留標籤的 \*.csv 檔案隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="a46a3-167">A \*.csv file that contains all existing retention labels opens.</span></span> <span data-ttu-id="a46a3-168">例如：</span><span class="sxs-lookup"><span data-stu-id="a46a3-168">For example:</span></span>

![顯示所有保留標籤的 CSV 檔案](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="a46a3-170">將保留標籤匯入至您的檔案計劃</span><span class="sxs-lookup"><span data-stu-id="a46a3-170">Import retention labels into your file plan</span></span>

<span data-ttu-id="a46a3-171">在檔案計畫中，您可以大量匯入新保留標籤，並使用相同的方法來大量修改現有的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="a46a3-171">In file plan, you can bulk-import new retention labels, and use the same method to bulk-modify existing retention labels.</span></span>

<span data-ttu-id="a46a3-172">若要匯出新的保留標籤，以及修改現有的保留標籤：</span><span class="sxs-lookup"><span data-stu-id="a46a3-172">To import new retention labels and modify existing retention labels:</span></span> 

1. <span data-ttu-id="a46a3-173">在 [檔案計畫]\*\*\*\* 頁面上，按一下 [匯入]\*\*\*\* 以使用 [填寫並匯入您的檔案計畫]\*\*\*\* 頁面：</span><span class="sxs-lookup"><span data-stu-id="a46a3-173">On the **File plan** page, click **Import** to use the **Fill out and import your file plan** page:</span></span>

   ![匯入檔案計劃的選項](../media/compliance-file-plan-import-labels.png)

   ![下載空白檔案計劃範本的選項](../media/file-plan-blank-template-option.png)

2. <span data-ttu-id="a46a3-176">下載空白範本以匯入全新保留標籤。</span><span class="sxs-lookup"><span data-stu-id="a46a3-176">Download a blank template to import new retention labels.</span></span> <span data-ttu-id="a46a3-177">或者，您可以從當匯出組織中的現有保留標籤時所匯出的 .csv 檔案開始。</span><span class="sxs-lookup"><span data-stu-id="a46a3-177">Alternatively, you can start with the .csv file that is exported when you export the existing retention labels in your organization.</span></span>

   ![Excel 中開啟空白檔案計畫範本](../media/file-plan-blank-template.png)

3. <span data-ttu-id="a46a3-179">使用說明每個屬性的屬性和有效值的以下資訊填寫範本。</span><span class="sxs-lookup"><span data-stu-id="a46a3-179">Fill out the template, using the following information that describes the properties and valid values for each property.</span></span> <span data-ttu-id="a46a3-180">匯入時，每個值的長度最多可以包含 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="a46a3-180">For import, each value has a maximum length of 64 characters.</span></span> <br/>

   |<span data-ttu-id="a46a3-181">屬性	</span><span class="sxs-lookup"><span data-stu-id="a46a3-181">Property</span></span>|<span data-ttu-id="a46a3-182">類型</span><span class="sxs-lookup"><span data-stu-id="a46a3-182">Type</span></span>|<span data-ttu-id="a46a3-183">有效值</span><span class="sxs-lookup"><span data-stu-id="a46a3-183">Valid values</span></span>|
   |:-----|:-----|:-----|
   |<span data-ttu-id="a46a3-184">LabelName</span><span class="sxs-lookup"><span data-stu-id="a46a3-184">LabelName</span></span>|<span data-ttu-id="a46a3-185">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-185">String</span></span>|<span data-ttu-id="a46a3-186">此屬性會指定保留標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="a46a3-186">This property specifies the name of the retention label.</span></span>|
   |<span data-ttu-id="a46a3-187">留言</span><span class="sxs-lookup"><span data-stu-id="a46a3-187">Comment</span></span>|<span data-ttu-id="a46a3-188">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-188">String</span></span>|<span data-ttu-id="a46a3-189">使用此屬性來新增系統管理員保留標籤相關的描述。</span><span class="sxs-lookup"><span data-stu-id="a46a3-189">Use this property to add a description about the retention label for admins.</span></span> <span data-ttu-id="a46a3-190">只有在合規性中心中管理保留標籤的系統管理員才會看到這個描述。</span><span class="sxs-lookup"><span data-stu-id="a46a3-190">This description appears only to admins who manage the retention label in the compliance center.</span></span>|
   |<span data-ttu-id="a46a3-191">附註</span><span class="sxs-lookup"><span data-stu-id="a46a3-191">Notes</span></span>|<span data-ttu-id="a46a3-192">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-192">String</span></span>|<span data-ttu-id="a46a3-193">使用此屬性來新增使用者保留標籤相關的描述。</span><span class="sxs-lookup"><span data-stu-id="a46a3-193">Use this property to add a description about the retention label for users.</span></span> <span data-ttu-id="a46a3-194">當使用者將游標移到應用程式 (例如 Outlook、SharePoint 和 OneDrive) 中的標籤上時，就會出現此描述。</span><span class="sxs-lookup"><span data-stu-id="a46a3-194">This description appears when users hover over the label in apps like Outlook, SharePoint, and OneDrive.</span></span> <span data-ttu-id="a46a3-195">如果您將此屬性保留空白，則會顯示說明標籤之保留設定的預設描述。</span><span class="sxs-lookup"><span data-stu-id="a46a3-195">If you leave this property blank, a default description is displayed, which explains the label's retention settings.</span></span> |
   |<span data-ttu-id="a46a3-196">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="a46a3-196">IsRecordLabel</span></span>|<span data-ttu-id="a46a3-197">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-197">String</span></span>|<span data-ttu-id="a46a3-198">此屬性會指定標籤是否將內容標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="a46a3-198">This property specifies whether the label marks the content as a record.</span></span> <span data-ttu-id="a46a3-199">有效值為：</span><span class="sxs-lookup"><span data-stu-id="a46a3-199">Valid values are:</span></span> </br><span data-ttu-id="a46a3-200">**TRUE**：標籤會將項目標示為記錄，並因此無法刪除該項目。</span><span class="sxs-lookup"><span data-stu-id="a46a3-200">**TRUE**: The label marks the item as a record and as a result, the item can't be deleted.</span></span> </br><span data-ttu-id="a46a3-201">**FALSE**：標籤不會將內容標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="a46a3-201">**FALSE**: The label doesn't mark the content as a record.</span></span> <span data-ttu-id="a46a3-202">這是預設值。</span><span class="sxs-lookup"><span data-stu-id="a46a3-202">This is the default value.</span></span>|
   |<span data-ttu-id="a46a3-203">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="a46a3-203">RetentionAction</span></span>|<span data-ttu-id="a46a3-204">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-204">String</span></span>|<span data-ttu-id="a46a3-205">此屬性指定由 RetentionDuration 屬性指定的值過期之後所要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="a46a3-205">This property specifies what action to take after the value specified by the RetentionDuration property expires.</span></span> <span data-ttu-id="a46a3-206">有效值為：</span><span class="sxs-lookup"><span data-stu-id="a46a3-206">Valid values are:</span></span> </br><span data-ttu-id="a46a3-207">**Delete**：刪除早於 RetentionDuration 屬性指定值的項目。</span><span class="sxs-lookup"><span data-stu-id="a46a3-207">**Delete**: Items older than the value specified by the RetentionDuration property are deleted.</span></span></br><span data-ttu-id="a46a3-208">**Keep**：保留由 RetentionDuration 屬性指定期間內的項目，然後在期間到期時不執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="a46a3-208">**Keep**: Retain items for the duration specified by the RetentionDuration property and then do nothing when the duration period expires.</span></span> </br><span data-ttu-id="a46a3-209">**KeepAndDelete**：保留由 RetentionDuration 屬性指定期間內的項目，然後在期間到期時將之刪除。</span><span class="sxs-lookup"><span data-stu-id="a46a3-209">**KeepAndDelete**: Retain items for the duration specified by the RetentionDuration property and then delete them when the duration period expires.</span></span>   |
   |<span data-ttu-id="a46a3-210">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="a46a3-210">RetentionDuration</span></span>|<span data-ttu-id="a46a3-211">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-211">String</span></span>|<span data-ttu-id="a46a3-212">此屬性會指定要保留內容的天數。</span><span class="sxs-lookup"><span data-stu-id="a46a3-212">This property specifies the number of days to retain the content.</span></span> <span data-ttu-id="a46a3-213">有效值為：</span><span class="sxs-lookup"><span data-stu-id="a46a3-213">Valid values are:</span></span> </br><span data-ttu-id="a46a3-214">**無限制**：系統會無限期保留這些項目。</span><span class="sxs-lookup"><span data-stu-id="a46a3-214">**Unlimited**: Items will be retained indefinitely.</span></span> </br><span data-ttu-id="a46a3-215">***n***：正整數；例如 **365**。</span><span class="sxs-lookup"><span data-stu-id="a46a3-215">***n***: A positive integer; for example, **365**.</span></span> 
   |<span data-ttu-id="a46a3-216">RetentionType</span><span class="sxs-lookup"><span data-stu-id="a46a3-216">RetentionType</span></span>|<span data-ttu-id="a46a3-217">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-217">String</span></span>|<span data-ttu-id="a46a3-218">此屬性會指定保留期限是否從內容建立日期、事件日期、已套用標籤日期或上次修改日期算起。</span><span class="sxs-lookup"><span data-stu-id="a46a3-218">This property specifies whether the retention duration is calculated from the content creation date, event date, when labeled date, or last modified date.</span></span> <span data-ttu-id="a46a3-219">有效值為：</span><span class="sxs-lookup"><span data-stu-id="a46a3-219">Valid values are:</span></span> </br><span data-ttu-id="a46a3-220">**CreationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="a46a3-220">**CreationAgeInDays**</span></span></br><span data-ttu-id="a46a3-221">**EventAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="a46a3-221">**EventAgeInDays**</span></span></br><span data-ttu-id="a46a3-222">**TaggedAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="a46a3-222">**TaggedAgeInDays**</span></span></br><span data-ttu-id="a46a3-223">**ModificationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="a46a3-223">**ModificationAgeInDays**</span></span> |
   |<span data-ttu-id="a46a3-224">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="a46a3-224">ReviewerEmail</span></span>|<span data-ttu-id="a46a3-225">SmtpAddress</span><span class="sxs-lookup"><span data-stu-id="a46a3-225">SmtpAddress</span></span>|<span data-ttu-id="a46a3-226">填入此屬性時，系統會在保留期間到期時觸發處置檢閱。</span><span class="sxs-lookup"><span data-stu-id="a46a3-226">When this property is populated, a disposition review will be triggered when the retention duration expires.</span></span> <span data-ttu-id="a46a3-227">此屬性會指定 **KeepAndDelete** 保留動作檢閱者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a46a3-227">This property specifies the email address of a reviewer for the **KeepAndDelete** retention action.</span></span> <span data-ttu-id="a46a3-228">您可以包含個別使用者、通訊群組或安全性群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a46a3-228">You can include the email address of individual users, distribution groups, or security groups.</span></span> <span data-ttu-id="a46a3-229">您可以使用分號指定多個電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a46a3-229">You can specify multiple email addresses separated by semicolons.</span></span>|
   |<span data-ttu-id="a46a3-230">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="a46a3-230">ReferenceId</span></span>|<span data-ttu-id="a46a3-231">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-231">String</span></span>|<span data-ttu-id="a46a3-232">此屬性指定在 [參考識別碼]\*\*\*\* 檔案計劃描述元中顯示的值，您可以將它用作組織的唯一值。</span><span class="sxs-lookup"><span data-stu-id="a46a3-232">This property specifies the value that's displayed in the **Reference Id** file plan descriptor, which you can use as a unique value to your organization.</span></span>| 
   |<span data-ttu-id="a46a3-233">Departmentname</span><span class="sxs-lookup"><span data-stu-id="a46a3-233">DepartmentName</span></span>|<span data-ttu-id="a46a3-234">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-234">String</span></span>|<span data-ttu-id="a46a3-235">此屬性指定在 **[功能/部門]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="a46a3-235">This property specifies the value that's displayed in the **Function/department** file plan descriptor.</span></span>|
   |<span data-ttu-id="a46a3-236">類別</span><span class="sxs-lookup"><span data-stu-id="a46a3-236">Category</span></span>|<span data-ttu-id="a46a3-237">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-237">String</span></span>|<span data-ttu-id="a46a3-238">此屬性指定在 **[類別]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="a46a3-238">This property specifies the value that's displayed in the **Category** file plan descriptor.</span></span>|
   |<span data-ttu-id="a46a3-239">子類別</span><span class="sxs-lookup"><span data-stu-id="a46a3-239">SubCategory</span></span>|<span data-ttu-id="a46a3-240">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-240">String</span></span>|<span data-ttu-id="a46a3-241">此屬性指定在 **[子類別]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="a46a3-241">This property specifies the value that's displayed in the **Sub category** file plan descriptor.</span></span>|
   |<span data-ttu-id="a46a3-242">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="a46a3-242">AuthorityType</span></span>|<span data-ttu-id="a46a3-243">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-243">String</span></span>|<span data-ttu-id="a46a3-244">此屬性指定在 **[授權單位類型]** 檔案計劃描述元中顯示的值。</span><span class="sxs-lookup"><span data-stu-id="a46a3-244">This property specifies the value that's displayed in the **Authority type** file plan descriptor.</span></span>|
   |<span data-ttu-id="a46a3-245">CitationName</span><span class="sxs-lookup"><span data-stu-id="a46a3-245">CitationName</span></span>|<span data-ttu-id="a46a3-246">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-246">String</span></span>|<span data-ttu-id="a46a3-247">此屬性指定在 [條款/引文]\*\*\*\* 檔案計畫描述元中顯示的引文名稱。</span><span class="sxs-lookup"><span data-stu-id="a46a3-247">This property specifies the name of the citation displayed in the **Provision/citation** file plan descriptor.</span></span> <span data-ttu-id="a46a3-248">例如，「2002 年沙賓法案」。</span><span class="sxs-lookup"><span data-stu-id="a46a3-248">For example, "Sarbanes-Oxley Act of 2002".</span></span> |
   |<span data-ttu-id="a46a3-249">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="a46a3-249">CitationUrl</span></span>|<span data-ttu-id="a46a3-250">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-250">String</span></span>|<span data-ttu-id="a46a3-251">此屬性指定在 **[條款/引文]** 檔案計劃描述元中顯示的 URL。</span><span class="sxs-lookup"><span data-stu-id="a46a3-251">This property specifies the URL that's displayed in the **Provision/citation** file plan descriptor.</span></span>|
   |<span data-ttu-id="a46a3-252">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="a46a3-252">CitationJurisdiction</span></span>|<span data-ttu-id="a46a3-253">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-253">String</span></span>|<span data-ttu-id="a46a3-254">此屬性指定在 [條款/引文]\*\*\*\* 檔案計畫描述元中顯示的管轄單位或代理機構。</span><span class="sxs-lookup"><span data-stu-id="a46a3-254">This property specifies the jurisdiction or agency that's displayed in the **Provision/citation** file plan descriptor.</span></span> <span data-ttu-id="a46a3-255">例如「美國證券交易委員會 (SEC)」</span><span class="sxs-lookup"><span data-stu-id="a46a3-255">For example, "U.S. Securities and Exchange Commission (SEC)".</span></span>|
   |<span data-ttu-id="a46a3-256">Regulatory</span><span class="sxs-lookup"><span data-stu-id="a46a3-256">Regulatory</span></span>|<span data-ttu-id="a46a3-257">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-257">String</span></span>|<span data-ttu-id="a46a3-258">保留空白。</span><span class="sxs-lookup"><span data-stu-id="a46a3-258">Leave blank.</span></span> <span data-ttu-id="a46a3-259">目前無法使用此屬性。</span><span class="sxs-lookup"><span data-stu-id="a46a3-259">This property isn't used at this time.</span></span>|
   |<span data-ttu-id="a46a3-260">EventType</span><span class="sxs-lookup"><span data-stu-id="a46a3-260">EventType</span></span>|<span data-ttu-id="a46a3-261">字串</span><span class="sxs-lookup"><span data-stu-id="a46a3-261">String</span></span>|<span data-ttu-id="a46a3-262">此屬性會指定與標籤相關聯的保留規則。</span><span class="sxs-lookup"><span data-stu-id="a46a3-262">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="a46a3-263">您可以使用唯一識別規則的任何值。</span><span class="sxs-lookup"><span data-stu-id="a46a3-263">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="a46a3-264">例如：</span><span class="sxs-lookup"><span data-stu-id="a46a3-264">For example:</span></span></br><span data-ttu-id="a46a3-265">**Name**</span><span class="sxs-lookup"><span data-stu-id="a46a3-265">**Name**</span></span></br><span data-ttu-id="a46a3-266">**Distinguished name (DN)**</span><span class="sxs-lookup"><span data-stu-id="a46a3-266">**Distinguished name (DN)**</span></span></br><span data-ttu-id="a46a3-267">**GUID**</span><span class="sxs-lookup"><span data-stu-id="a46a3-267">**GUID**</span></span> </br><span data-ttu-id="a46a3-268">您可以使用 [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule) Cmdlet 來檢視可用的保留規則。</span><span class="sxs-lookup"><span data-stu-id="a46a3-268">You can use the [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule) cmdlet to view the available retention rules.</span></span> <span data-ttu-id="a46a3-269">請注意，因為 EventType 值是每個組織特有，如果從某組織匯出標籤，您無法使用來自該組織的 EventType 屬性值，來將標籤匯入至不同組織。</span><span class="sxs-lookup"><span data-stu-id="a46a3-269">Note that because the EventType values are unique to an organization, if you export labels from one organization, you can't use the values for the EventType property from that organization to import labels into a different organization.</span></span>|
   |||

   <span data-ttu-id="a46a3-270">以下是含有保留標籤相關資訊的範本範例。</span><span class="sxs-lookup"><span data-stu-id="a46a3-270">Here's an example of the template containing the information about retention labels.</span></span>

   ![已填入資訊的檔案計畫範本](../media/file-plan-filled-out-template.png)

4. <span data-ttu-id="a46a3-272">在 [填寫並匯入您的檔案計畫]\*\*\*\* 頁面的步驟 3 下方，按一下 [瀏覽檔案]\*\*\*\* 以上傳填寫的範本。</span><span class="sxs-lookup"><span data-stu-id="a46a3-272">Under step 3 on the **Fill out and import your file plan** page, click **Browse for files** to upload the filled-out template.</span></span> 

   <span data-ttu-id="a46a3-273">檔案計畫會驗證項目並顯示匯入統計資料。</span><span class="sxs-lookup"><span data-stu-id="a46a3-273">File plan validates the entries and displays the import statistics.</span></span>

   ![檔案計畫匯入統計資料](../media/file-plan-import-statistics.png)

   <span data-ttu-id="a46a3-275">如果發生驗證錯誤，檔案計畫匯入會繼續驗證匯入檔案中的每個項目，並顯示參考匯入檔案中該行和列號的所有錯誤。</span><span class="sxs-lookup"><span data-stu-id="a46a3-275">If there's a validation error, file plan import continues to validate every entry in the import file and displays all errors  referencing the line and row numbers in the import file.</span></span> <span data-ttu-id="a46a3-276">複製顯示的錯誤結果，以便在您回到匯入檔案時可加以修正。</span><span class="sxs-lookup"><span data-stu-id="a46a3-276">Copy the displayed error results so you can correct them when you return to the import file.</span></span>

<span data-ttu-id="a46a3-277">匯入完成後，您現在可以將保留標籤新增至新的保留標籤原則，或自動套用。</span><span class="sxs-lookup"><span data-stu-id="a46a3-277">When the import is complete, you can now add the retention labels to a new retention label policy, or auto-apply them.</span></span> <span data-ttu-id="a46a3-278">您可以直接從 [檔案計畫]\*\*\*\* 頁面執行此動作，方法是選取 [+ 建立標籤]\*\*\*\* 下拉式清單，然後選取 [發佈標籤的原則]\*\*\*\* 或 [自動套用標籤的原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a46a3-278">You can do this right from the **File plan** page by selecting the dropdown from **+ Create a label** and then **Policy to publish labels**, or **Policy to auto-apply a label**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a46a3-279">後續步驟</span><span class="sxs-lookup"><span data-stu-id="a46a3-279">Next steps</span></span>

<span data-ttu-id="a46a3-280">如需有關建立和編輯保留標籤及其原則的詳細資訊，可參閱下列指南：</span><span class="sxs-lookup"><span data-stu-id="a46a3-280">For more information about creating and editing retention labels and their policies, see the following guidance:</span></span>
- [<span data-ttu-id="a46a3-281">建立保留標籤，並在應用程式中使用這些標籤</span><span class="sxs-lookup"><span data-stu-id="a46a3-281">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="a46a3-282">自動將保留標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="a46a3-282">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)
