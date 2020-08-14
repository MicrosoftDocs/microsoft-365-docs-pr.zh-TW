---
title: 自動套用保留標籤來保留或刪除內容
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
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 建立及自動發佈保留標籤，以便您可以自動套用標籤以保留所需的內容，並刪除您不需要的內容。
ms.openlocfilehash: 80a5ef502450a24d9c8aeeb08d571bfcbd51a4e3
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648802"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="764f4-103">自動套用保留標籤來保留或刪除內容</span><span class="sxs-lookup"><span data-stu-id="764f4-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="764f4-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="764f4-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="764f4-105">[保留標籤](retention.md) 最實用的功能之一，是將標籤自動套用至符合特定條件的內容。</span><span class="sxs-lookup"><span data-stu-id="764f4-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="764f4-106">在此情況下，貴組織中的人員不必親自套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="764f4-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="764f4-107">Microsoft 365 會執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="764f4-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="764f4-108">自動套用保留標籤很強大是因為：</span><span class="sxs-lookup"><span data-stu-id="764f4-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="764f4-109">您不需要訓練您的使用者記下所有分類。</span><span class="sxs-lookup"><span data-stu-id="764f4-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="764f4-110">您不需要仰賴使用者正確地將所有內容分類。</span><span class="sxs-lookup"><span data-stu-id="764f4-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="764f4-111">使用者不再需要了解資料控管原則，他們可以專心工作。</span><span class="sxs-lookup"><span data-stu-id="764f4-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="764f4-112">當該內容包含敏感資訊、關鍵字或 [可訓練分類器](classifier-getting-started-with.md) 的匹配項目時，您可以自動套用保留標籤到內容上。</span><span class="sxs-lookup"><span data-stu-id="764f4-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords, or a match for [trainable classifiers](classifier-getting-started-with.md).</span></span>
    
<span data-ttu-id="764f4-113">根據下列條件自動套用保留標籤的程式：</span><span class="sxs-lookup"><span data-stu-id="764f4-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![自動套用標籤的角色和工作圖](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="764f4-115">使用下列指示執行兩個系統管理員步驟。</span><span class="sxs-lookup"><span data-stu-id="764f4-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="764f4-116">自動原則會使用條件的服務端標籤來自動套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="764f4-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="764f4-117">當您執行下列動作時，您也可以使用標籤原則以自動套用保留標籤：</span><span class="sxs-lookup"><span data-stu-id="764f4-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="764f4-118">將預設保留標籤套用至 SharePoint 文件庫、資料夾或檔組，讓該容器中未標記的內容自動加上標籤</span><span class="sxs-lookup"><span data-stu-id="764f4-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="764f4-119">使用規則將保留標籤自動套用至電子郵件</span><span class="sxs-lookup"><span data-stu-id="764f4-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="764f4-120">在這些情況下，請參閱 [在應用程式中建立集套用保留標籤](create-apply-retention-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="764f4-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="764f4-121">開始之前</span><span class="sxs-lookup"><span data-stu-id="764f4-121">Before you begin</span></span>

<span data-ttu-id="764f4-122">您組織中的全域系統管理員擁有建立及管理保留標籤及其原則的完整權限。</span><span class="sxs-lookup"><span data-stu-id="764f4-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="764f4-123">如果您未以全域系統管理員身分登入，請參閱[建立和管理保留標籤所需權限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="764f4-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="764f4-124">如何自動套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="764f4-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="764f4-125">首先，建立您自己的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="764f4-125">First, create your retention label.</span></span> <span data-ttu-id="764f4-126">然後建立自動原則來套用該標籤。</span><span class="sxs-lookup"><span data-stu-id="764f4-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="764f4-127">如果您已經建立保留標籤，請跳至 [建立自動原則](#step-2-create-an-auto-apply-policy)。</span><span class="sxs-lookup"><span data-stu-id="764f4-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="764f4-128">瀏覽指示取決於您使用的是否是 [記錄管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="764f4-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="764f4-129">以下提供這兩個案例的指示。</span><span class="sxs-lookup"><span data-stu-id="764f4-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="764f4-130">步驟1: 建立保留標籤。</span><span class="sxs-lookup"><span data-stu-id="764f4-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="764f4-131">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="764f4-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="764f4-132">如果您使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="764f4-132">If you are using records management:</span></span>
        - <span data-ttu-id="764f4-133">[解決方案]\*\*\*\*  >  [記錄管理]\*\*\*\*  >  [檔案計劃]\*\*\*\* 索引標籤 > [+ 建立標籤]\*\*\*\*  >  [保留標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="764f4-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="764f4-134">如果您未使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="764f4-134">If you are not using records management:</span></span>
       - <span data-ttu-id="764f4-135">[解決方案]\*\*\*\*  >  [資訊控管]\*\*\*\*  >  [標籤]\*\*\*\* 索引標籤 > [+ 建立標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="764f4-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="764f4-136">沒有立即看到您的選項？</span><span class="sxs-lookup"><span data-stu-id="764f4-136">Don't immediately see your option?</span></span> <span data-ttu-id="764f4-137">先選取 [顯示全部]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="764f4-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="764f4-138">遵循精靈中的提示進行。</span><span class="sxs-lookup"><span data-stu-id="764f4-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="764f4-139">如果您使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="764f4-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="764f4-140">如需檔案計劃描述元的詳細資訊，請參閱[使用檔案計劃管理保留標籤](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="764f4-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="764f4-141">若要使用保留標籤將內容宣告為記錄，請啟用 [使用標籤以將內容分類為「記錄」]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="764f4-141">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

<span data-ttu-id="764f4-142">若要編輯現有的標籤，請選取它，然後選取 [編輯標籤]\*\*\*\* 以啟動相同的精靈讓您變更標籤描述和步驟 2 的任何[合格設定](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="764f4-142">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="764f4-143">或者，選取任何一個可用的 **[編輯]** 選項，直接移至相關頁面以進行更新。</span><span class="sxs-lookup"><span data-stu-id="764f4-143">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="764f4-144">步驟2：建立自動套用原則</span><span class="sxs-lookup"><span data-stu-id="764f4-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="764f4-145">當您建立自動套用原則時，會根據您指定的條件，選取要自動套用至內容的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="764f4-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="764f4-146">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="764f4-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="764f4-147">如果您使用記錄管理：**資訊控管**：</span><span class="sxs-lookup"><span data-stu-id="764f4-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="764f4-148">[解決方案]\*\*\*\*  >  [記錄管理]\*\*\*\*  >  [標籤原則]\*\*\*\* 索引標籤 > [自動套用標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="764f4-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="764f4-149">如果您未使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="764f4-149">If you are not using records management:</span></span>
        - <span data-ttu-id="764f4-150">[解決方案]\*\*\*\*  >  [資訊控管]\*\*\*\*  >  [標籤原則]\*\*\*\* 索引標籤 > [自動套用標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="764f4-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="764f4-151">沒有立即看到您的選項？</span><span class="sxs-lookup"><span data-stu-id="764f4-151">Don't immediately see your option?</span></span> <span data-ttu-id="764f4-152">先選取 [顯示全部]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="764f4-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="764f4-153">遵循精靈中的提示進行。</span><span class="sxs-lookup"><span data-stu-id="764f4-153">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="764f4-154">如需有關設定會自動套用保留標籤之條件的詳細資訊，請參閱此頁面上的[設定自動套用保留標籤的條件](#configuring-conditions-for-auto-apply-retention-labels)一節。</span><span class="sxs-lookup"><span data-stu-id="764f4-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="764f4-155">如需保留標籤支援的位置詳細資訊，請參閱[保留標籤和位置](retention.md#retention-label-policies-and-locations)一節。</span><span class="sxs-lookup"><span data-stu-id="764f4-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="764f4-156">若要編輯現有的自動套用標籤原則，請選取它，然後選取 [編輯原則]\*\*\*\* 以啟動相同的精靈讓您變更標籤描述和步驟 2 的任何[合格設定](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="764f4-156">To edit an existing auto-apply label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="764f4-157">或者，選取任何一個可用的 [編輯]\*\*\*\* 選項，直接移至相關頁面以進行更新。</span><span class="sxs-lookup"><span data-stu-id="764f4-157">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="764f4-158">設定自動套用保留標籤的條件</span><span class="sxs-lookup"><span data-stu-id="764f4-158">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="764f4-159">您可以在內容包含以下資訊時，自動將保留標籤套用到內容：</span><span class="sxs-lookup"><span data-stu-id="764f4-159">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="764f4-160">特定敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="764f4-160">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="764f4-161">符合您所建立查詢的特定關鍵字</span><span class="sxs-lookup"><span data-stu-id="764f4-161">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="764f4-162">可訓練分類器的符合項目</span><span class="sxs-lookup"><span data-stu-id="764f4-162">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="764f4-163">自動將標籤套用至包含特定類型敏感資訊的內容</span><span class="sxs-lookup"><span data-stu-id="764f4-163">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="764f4-164">當您為敏感性資訊建立自動套用保留標籤時，系統會顯示與建立資料外洩防護 (DLP) 原則時相同的原則範本清單。</span><span class="sxs-lookup"><span data-stu-id="764f4-164">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="764f4-165">每個原則範本預設會尋找特定類型的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="764f4-165">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="764f4-166">例如本文顯示的範本會尋找美國 ITIN、SSN 和護照號碼。</span><span class="sxs-lookup"><span data-stu-id="764f4-166">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="764f4-167">若要深入了解 DLP，請參閱[資料外洩防護原則概觀](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="764f4-167">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![敏感資訊類型的原則範本](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="764f4-p112">選取原則範本後，可以新增或移除任何類型的敏感資訊，且可以變更例項計數和比對精確度。此處所示的範例中，只有符合以下條件時，才會自動套用保留標籤：</span><span class="sxs-lookup"><span data-stu-id="764f4-p112">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="764f4-p113">內容包含 1 到 9 個下列三種敏感資訊類型。您可以刪除 \*\*max \*\* (上限) 值，條件就會變成 **any** (任何)。</span><span class="sxs-lookup"><span data-stu-id="764f4-p113">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="764f4-173">系統偵測到之機密資訊類型的比對精確度 (或信賴區間) 至少會有 75。</span><span class="sxs-lookup"><span data-stu-id="764f4-173">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="764f4-174">許多機密資訊類型是與多個合作夥伴所定義；比對精確度越高的模式需要更多證據 (例如關鍵字、日期或地址)，比對精確度越低的模式則需要較少證據。</span><span class="sxs-lookup"><span data-stu-id="764f4-174">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="764f4-175">**最小**比對精確度越低，內容就越容易與條件相符。</span><span class="sxs-lookup"><span data-stu-id="764f4-175">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="764f4-176">如需這些選項的詳細資訊，請參閱[調整規則，讓規則更容易或更難相符](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="764f4-176">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![用於識別機密資訊類型的選項](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="764f4-178">自動將標籤套用至包含關鍵字或可搜尋屬性的內容</span><span class="sxs-lookup"><span data-stu-id="764f4-178">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="764f4-p115">您可以自動將標籤套用至符合特定條件的內容。現在可用的條件支援將標籤套用至包含特定字詞、片語或可搜尋屬性的值。您可以使用 AND、OR、NOT 等搜尋運算子來精簡查詢。</span><span class="sxs-lookup"><span data-stu-id="764f4-p115">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="764f4-182">自動將標籤套用至可搜尋的屬性時，無法在查詢中使用受管理屬性的別名。</span><span class="sxs-lookup"><span data-stu-id="764f4-182">While auto-applying labels for searchable properties, an alias for a managed property cannot be used in the query.</span></span> <span data-ttu-id="764f4-183">它必須是受管理屬性的實際名稱，例如 RefinableString01。</span><span class="sxs-lookup"><span data-stu-id="764f4-183">It must be the actual name of the managed property, for example, RefinableString01.</span></span>

<span data-ttu-id="764f4-184">如需查詢語法的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="764f4-184">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="764f4-185">關鍵字查詢語言 (KQL) 語法參考</span><span class="sxs-lookup"><span data-stu-id="764f4-185">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="764f4-p117">查詢式標籤使用搜尋索引來識別內容。如需有效可搜尋屬性的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="764f4-p117">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="764f4-188">內容搜尋的關鍵字查詢與搜尋條件</span><span class="sxs-lookup"><span data-stu-id="764f4-188">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="764f4-189">SharePoint 伺服器中的編目及受控屬性概觀</span><span class="sxs-lookup"><span data-stu-id="764f4-189">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="764f4-190">範例查詢：</span><span class="sxs-lookup"><span data-stu-id="764f4-190">Examples queries:</span></span>

- <span data-ttu-id="764f4-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="764f4-191">Exchange</span></span>
    - <span data-ttu-id="764f4-192">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="764f4-192">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="764f4-193">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="764f4-193">recipients:garthf</span></span><!--nolink--><span data-ttu-id="764f4-194">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="764f4-194">@contoso.com</span></span>
- <span data-ttu-id="764f4-195">SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="764f4-195">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="764f4-196">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="764f4-196">contenttype:contract</span></span>
    - <span data-ttu-id="764f4-197">site:https</span><span class="sxs-lookup"><span data-stu-id="764f4-197">site:https</span></span><!--nolink--><span data-ttu-id="764f4-198">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="764f4-198">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![查詢編輯器](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="764f4-200">使用可訓練分類器自動將標籤套用至內容</span><span class="sxs-lookup"><span data-stu-id="764f4-200">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="764f4-201">選擇用於可訓練分類器的選項時，可以選取其中一個內建分類器或自訂分類器。</span><span class="sxs-lookup"><span data-stu-id="764f4-201">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="764f4-202">內建分類器包括 [履歷]\*\*\*\*、[原始程式碼]\*\*\*\*、[針對性騷擾]\*\*\*\*、[粗話]\*\*\*\* 和 [威脅]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="764f4-202">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![選擇可訓練分類器](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="764f4-204">我們正在淘汰 [粗穢言語]\*\*\*\* 內建分類器，因為這個分類器產生了大量的誤報。</span><span class="sxs-lookup"><span data-stu-id="764f4-204">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="764f4-205">請不要使用這個內建分類器，如果您目前正在使用此分類器，請將您的商務流程移開。</span><span class="sxs-lookup"><span data-stu-id="764f4-205">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="764f4-206">建議您改用 [針對性騷擾]\*\*\*\*、[粗話]\*\*\*\* 和 [威脅]\*\*\*\* 內建分類器。</span><span class="sxs-lookup"><span data-stu-id="764f4-206">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="764f4-207">若要使用此選項自動套用標籤，SharePoint Online 網站和信箱必須有至少 10 MB 的資料。</span><span class="sxs-lookup"><span data-stu-id="764f4-207">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="764f4-208">如需有關可訓練分類器的詳細資訊，請參閱[開始使用可訓練分類器 (預覽)](classifier-getting-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="764f4-208">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="764f4-209">如需組態範例，請參閱[如何準備及使用內建分類器](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)。</span><span class="sxs-lookup"><span data-stu-id="764f4-209">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="764f4-210">保留標籤要多久才會生效</span><span class="sxs-lookup"><span data-stu-id="764f4-210">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="764f4-211">當您自動套用保留標籤，可能需要最多 7 天，保留標籤才會套用至符合條件的所有現有內容。</span><span class="sxs-lookup"><span data-stu-id="764f4-211">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自動標籤生效時的圖表](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="764f4-213">更新保留標籤及其原則</span><span class="sxs-lookup"><span data-stu-id="764f4-213">Updating retention labels and their policies</span></span>

<span data-ttu-id="764f4-214">當您編輯保留標籤或自動套用原則，且保留標籤已套用至內容時，除了新識別的內容以外，您更新的設定會自動套用到此內容。</span><span class="sxs-lookup"><span data-stu-id="764f4-214">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="764f4-215">在建立及儲存標籤或原則之後，部分設定無法變更，其中包括：</span><span class="sxs-lookup"><span data-stu-id="764f4-215">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="764f4-216">保留期間以外的保留設定，除非您已將標籤設定為根據建立時間來保留或刪除內容。</span><span class="sxs-lookup"><span data-stu-id="764f4-216">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="764f4-217">分類為記錄的選項。</span><span class="sxs-lookup"><span data-stu-id="764f4-217">The option to classify as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="764f4-218">後續步驟</span><span class="sxs-lookup"><span data-stu-id="764f4-218">Next steps</span></span>

<span data-ttu-id="764f4-219">請參閱 [使用保留標籤來管理儲存在 SharePoint 中的文件週期](auto-apply-retention-labels-scenario.md)，例如，在 SharePoint 中使用自動套用原則和受管理的屬性，以及以事件為基礎的保留原則，開始保留期間。</span><span class="sxs-lookup"><span data-stu-id="764f4-219">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
