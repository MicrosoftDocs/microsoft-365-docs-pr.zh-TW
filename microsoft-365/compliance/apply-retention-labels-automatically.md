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
ms.openlocfilehash: 9ab456cd5b1f5f1bf47a1e24a3d7e58b7992ede0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196376"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="b07cd-103">自動套用保留標籤來保留或刪除內容</span><span class="sxs-lookup"><span data-stu-id="b07cd-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="b07cd-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="b07cd-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

> [!NOTE]
> <span data-ttu-id="b07cd-105">[法規記錄](records-management.md#records)不支援此案例。</span><span class="sxs-lookup"><span data-stu-id="b07cd-105">This scenario is not supported for [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="b07cd-106">[保留標籤](retention.md) 最實用的功能之一，是將標籤自動套用至符合特定條件的內容。</span><span class="sxs-lookup"><span data-stu-id="b07cd-106">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="b07cd-107">在此情況下，貴組織中的人員不必親自套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b07cd-107">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="b07cd-108">Microsoft 365 會執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="b07cd-108">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="b07cd-109">自動套用保留標籤很強大是因為：</span><span class="sxs-lookup"><span data-stu-id="b07cd-109">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="b07cd-110">您不需要訓練您的使用者記下所有分類。</span><span class="sxs-lookup"><span data-stu-id="b07cd-110">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="b07cd-111">您不需要仰賴使用者正確地將所有內容分類。</span><span class="sxs-lookup"><span data-stu-id="b07cd-111">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="b07cd-112">使用者不再需要了解資料控管原則，他們可以專心工作。</span><span class="sxs-lookup"><span data-stu-id="b07cd-112">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="b07cd-113">當內容包含敏感性資訊、關鍵字或[可訓練分類器](classifier-get-started-with.md)的相符項目時，您可以自動對該內容套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b07cd-113">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

> [!TIP]
> <span data-ttu-id="b07cd-114">現在處於預覽階段，使用可搜尋的屬性來找出 [Teams 會議錄製](#microsoft-teams-meeting-recordings)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-114">Now in preview, use searchable properties to identify [Teams meeting recordings](#microsoft-teams-meeting-recordings).</span></span>

<span data-ttu-id="b07cd-115">根據下列條件自動套用保留標籤的程式：</span><span class="sxs-lookup"><span data-stu-id="b07cd-115">The processes to automatically apply a retention label based on these conditions:</span></span>

![自動套用標籤的角色和工作圖](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="b07cd-117">使用下列指示執行兩個系統管理員步驟。</span><span class="sxs-lookup"><span data-stu-id="b07cd-117">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="b07cd-118">自動原則會使用條件的服務端標籤來自動套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b07cd-118">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="b07cd-119">當您執行下列動作時，您也可以使用標籤原則以自動套用保留標籤：</span><span class="sxs-lookup"><span data-stu-id="b07cd-119">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="b07cd-120">將預設保留標籤套用至 SharePoint 文件庫、資料夾或檔組，讓該容器中未標記的內容自動加上標籤</span><span class="sxs-lookup"><span data-stu-id="b07cd-120">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="b07cd-121">使用規則將保留標籤自動套用至電子郵件</span><span class="sxs-lookup"><span data-stu-id="b07cd-121">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="b07cd-122">在這些情況下，請參閱 [在應用程式中建立集套用保留標籤](create-apply-retention-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-122">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b07cd-123">開始之前</span><span class="sxs-lookup"><span data-stu-id="b07cd-123">Before you begin</span></span>

<span data-ttu-id="b07cd-124">您組織中的全域系統管理員擁有建立及管理保留標籤及其原則的完整權限。</span><span class="sxs-lookup"><span data-stu-id="b07cd-124">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="b07cd-125">如果您未以全域系統管理員身分登入，請參閱[建立和管理保留標籤所需權限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-125">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="b07cd-126">如何自動套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="b07cd-126">How to auto-apply a retention label</span></span>

<span data-ttu-id="b07cd-127">首先，建立您自己的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b07cd-127">First, create your retention label.</span></span> <span data-ttu-id="b07cd-128">然後建立自動原則來套用該標籤。</span><span class="sxs-lookup"><span data-stu-id="b07cd-128">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="b07cd-129">如果您已經建立保留標籤，請跳至 [建立自動原則](#step-2-create-an-auto-apply-policy)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-129">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="b07cd-130">瀏覽指示取決於您使用的是否是 [記錄管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-130">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="b07cd-131">以下提供這兩個案例的指示。</span><span class="sxs-lookup"><span data-stu-id="b07cd-131">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="b07cd-132">步驟1: 建立保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b07cd-132">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="b07cd-133">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="b07cd-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="b07cd-134">如果您使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="b07cd-134">If you are using records management:</span></span>
        - <span data-ttu-id="b07cd-135">[解決方案]\*\*\*\*  >  [記錄管理]\*\*\*\*  >  [檔案計劃]\*\*\*\* 索引標籤 > [+ 建立標籤]\*\*\*\*  >  [保留標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b07cd-135">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="b07cd-136">如果您未使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="b07cd-136">If you are not using records management:</span></span>
       - <span data-ttu-id="b07cd-137">[解決方案]\*\*\*\*  >  [資訊控管]\*\*\*\*  >  [標籤]\*\*\*\* 索引標籤 > [+ 建立標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b07cd-137">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="b07cd-138">沒有立即看到您的選項？</span><span class="sxs-lookup"><span data-stu-id="b07cd-138">Don't immediately see your option?</span></span> <span data-ttu-id="b07cd-139">先選取 [顯示全部]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b07cd-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="b07cd-140">遵循精靈中的提示進行。</span><span class="sxs-lookup"><span data-stu-id="b07cd-140">Follow the prompts in the wizard.</span></span> <span data-ttu-id="b07cd-141">如果您使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="b07cd-141">If you are using records management:</span></span>
    
    - <span data-ttu-id="b07cd-142">如需檔案計劃描述元的詳細資訊，請參閱[使用檔案計劃管理保留標籤](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="b07cd-142">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="b07cd-143">若要使用保留標籤來宣告記錄，請選取 [將項目標記為記錄 **]**，或 [將項目標記為法規記錄 **]**。</span><span class="sxs-lookup"><span data-stu-id="b07cd-143">To use the retention label to declare records, select **Mark items as records**, or **Mark items as regulatory records**.</span></span> <span data-ttu-id="b07cd-144">如需詳細資訊，請參閱[設定保留標籤以宣告記錄](declare-records.md#configuring-retention-labels-to-declare-records)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-144">For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="b07cd-145">建立標籤並看到發佈標籤、自動套用標籤或僅保存標籤的選項：選取 **[自動將此標籤套用於特定類型的內容]**，然後選取 **[完成]** 以啟動 [建立自動標籤] 精靈，該精靈將直接帶您進入以下過程中的步驟 2。</span><span class="sxs-lookup"><span data-stu-id="b07cd-145">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="b07cd-146">若要編輯現有的標籤，請選取它，然後選取 **[編輯標籤]** 以啟動編輯保留精靈讓您變更標籤描述和步驟 2 的任何[合格設定](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-146">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="b07cd-147">步驟2：建立自動套用原則</span><span class="sxs-lookup"><span data-stu-id="b07cd-147">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="b07cd-148">當您建立自動套用原則時，會根據您指定的條件，選取要自動套用至內容的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b07cd-148">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="b07cd-149">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="b07cd-149">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="b07cd-150">如果您使用記錄管理：**資訊控管**：</span><span class="sxs-lookup"><span data-stu-id="b07cd-150">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="b07cd-151">**[解決方案]**  > \*\* [記錄管理]\*\*  > \*\* [標籤原則]\*\* 索引標籤 > **[自動套用標籤]**</span><span class="sxs-lookup"><span data-stu-id="b07cd-151">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="b07cd-152">如果您未使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="b07cd-152">If you are not using records management:</span></span>
        - <span data-ttu-id="b07cd-153">**[解決方案]**  >  **[資訊控管]**  >  **[標籤原則]** 索引標籤 > **[自動套用標籤]**</span><span class="sxs-lookup"><span data-stu-id="b07cd-153">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="b07cd-154">沒有立即看到您的選項？</span><span class="sxs-lookup"><span data-stu-id="b07cd-154">Don't immediately see your option?</span></span> <span data-ttu-id="b07cd-155">先選取 [顯示全部]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b07cd-155">First select **Show all**.</span></span> 

2. <span data-ttu-id="b07cd-156">按照 [建立自動標籤精靈] 中的提示。</span><span class="sxs-lookup"><span data-stu-id="b07cd-156">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="b07cd-157">如需有關設定會自動套用保留標籤之條件的詳細資訊，請參閱此頁面上的[設定自動套用保留標籤的條件](#configuring-conditions-for-auto-apply-retention-labels)一節。</span><span class="sxs-lookup"><span data-stu-id="b07cd-157">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="b07cd-158">如需保留標籤支援的位置詳細資訊，請參閱[保留標籤和位置](retention.md#retention-label-policies-and-locations)一節。</span><span class="sxs-lookup"><span data-stu-id="b07cd-158">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="b07cd-159">若要編輯現有的自動套用原則，請選取該原則以啟動 [編輯保留原則] 精靈，該精靈允許您更改所選的保留標籤和步驟 2 中的任何[合格設定](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-159">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="b07cd-160">設定自動套用保留標籤的條件</span><span class="sxs-lookup"><span data-stu-id="b07cd-160">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="b07cd-161">您可以在內容包含以下資訊時，自動將保留標籤套用到內容：</span><span class="sxs-lookup"><span data-stu-id="b07cd-161">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="b07cd-162">特定敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="b07cd-162">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="b07cd-163">符合您所建立查詢的特定關鍵字或可搜尋的屬性</span><span class="sxs-lookup"><span data-stu-id="b07cd-163">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="b07cd-164">可訓練分類器的符合項目</span><span class="sxs-lookup"><span data-stu-id="b07cd-164">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="b07cd-165">自動將標籤套用至包含特定類型敏感資訊的內容</span><span class="sxs-lookup"><span data-stu-id="b07cd-165">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="b07cd-166">當您為敏感性資訊建立自動套用保留標籤時，系統會顯示與建立資料外洩防護 (DLP) 原則時相同的原則範本清單。</span><span class="sxs-lookup"><span data-stu-id="b07cd-166">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="b07cd-167">每個範本預設會尋找特定類型的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="b07cd-167">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="b07cd-168">例如，此處顯示的範本從**隱私權**類別中查找美國 ITIN、SSN 和護照號碼，以及**美國個人識別資訊 (PII) 資料範本**：</span><span class="sxs-lookup"><span data-stu-id="b07cd-168">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template**:</span></span>

![敏感資訊類型的原則範本](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="b07cd-170">了解有關敏感性資訊類型的更多資訊，請參閱[敏感性資訊類型實體定義](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-170">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="b07cd-171">選取原則範本後，您可以新增或移除任何類型的機密資訊，也可以變更執行個體計數和比對精確度。</span><span class="sxs-lookup"><span data-stu-id="b07cd-171">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="b07cd-172">在下方顯示的示例螢幕擷取畫面中，只有在以下情况下才會自動套用保留標籤：</span><span class="sxs-lookup"><span data-stu-id="b07cd-172">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="b07cd-173">系統偵測到之機密資訊類型的比對精確度 (或信賴區間) 至少會有 75。</span><span class="sxs-lookup"><span data-stu-id="b07cd-173">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="b07cd-174">許多機密資訊類型是與多個合作夥伴所定義；比對精確度越高的模式需要更多證據 (例如關鍵字、日期或地址)，比對精確度越低的模式則需要較少證據。</span><span class="sxs-lookup"><span data-stu-id="b07cd-174">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="b07cd-175">**最小**比對精確度越低，內容就越容易與條件相符。</span><span class="sxs-lookup"><span data-stu-id="b07cd-175">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="b07cd-176">內容包含 1 到 9 個以下三種機密資訊類型其中之一的執行個體。</span><span class="sxs-lookup"><span data-stu-id="b07cd-176">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="b07cd-177">您可以删除 **to** 值，使其更改為**任何**。</span><span class="sxs-lookup"><span data-stu-id="b07cd-177">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="b07cd-178">有關這些選項的更多資訊，請參閱 DLP 檔案中的以下指導方針[調整規則以讓它們更容易更難符合](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-178">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![用於識別機密資訊類型的選項](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="b07cd-180">自動將標籤套用至包含關鍵字或可搜尋屬性的內容</span><span class="sxs-lookup"><span data-stu-id="b07cd-180">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="b07cd-p114">您可以使用包含特定字詞、片語或可搜尋屬性的查詢，自動將標籤套用至內容。您可以使用 AND、OR 和 NOT 等搜尋運算子來精簡查詢。</span><span class="sxs-lookup"><span data-stu-id="b07cd-p114">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![查詢編輯器](../media/new-retention-query-editor.png)

<span data-ttu-id="b07cd-184">如需使用關鍵字查詢語言 (KQL) 的查詢語法的詳細資訊，請參閱[關鍵字查詢語言 (KQL) 語法參考](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-184">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="b07cd-185">查詢型標籤會使用搜尋索引來識別內容。</span><span class="sxs-lookup"><span data-stu-id="b07cd-185">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="b07cd-186">如需有關您可使用的可搜尋屬性的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b07cd-186">For more information about the searchable properties that you can use, see:</span></span>

- [<span data-ttu-id="b07cd-187">內容搜尋的關鍵字查詢與搜尋條件</span><span class="sxs-lookup"><span data-stu-id="b07cd-187">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="b07cd-188">SharePoint 伺服器中的編目及受控屬性概觀</span><span class="sxs-lookup"><span data-stu-id="b07cd-188">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> <span data-ttu-id="b07cd-189">雖然 SharePoint 管理屬性支援別名，但當您設定保留標籤時，請不要使用這些別名。</span><span class="sxs-lookup"><span data-stu-id="b07cd-189">Although SharePoint managed properties support aliases, don't use these when you configure your retention labels.</span></span> <span data-ttu-id="b07cd-190">一律指定受管理屬性的實際名稱，例如，"RefinableString01"。</span><span class="sxs-lookup"><span data-stu-id="b07cd-190">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

<span data-ttu-id="b07cd-191">範例查詢：</span><span class="sxs-lookup"><span data-stu-id="b07cd-191">Examples queries:</span></span>

| <span data-ttu-id="b07cd-192">工作負載</span><span class="sxs-lookup"><span data-stu-id="b07cd-192">Workload</span></span> | <span data-ttu-id="b07cd-193">範例</span><span class="sxs-lookup"><span data-stu-id="b07cd-193">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="b07cd-194">Exchange</span><span class="sxs-lookup"><span data-stu-id="b07cd-194">Exchange</span></span>   | `subject:"Quarterly Financials"` |
|<span data-ttu-id="b07cd-195">Exchange</span><span class="sxs-lookup"><span data-stu-id="b07cd-195">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="b07cd-196">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b07cd-196">SharePoint</span></span> | `contenttype:contract` |
|<span data-ttu-id="b07cd-197">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b07cd-197">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

##### <a name="microsoft-teams-meeting-recordings"></a><span data-ttu-id="b07cd-198">Microsoft Teams 會議錄製</span><span class="sxs-lookup"><span data-stu-id="b07cd-198">Microsoft Teams meeting recordings</span></span>

> [!NOTE]
> <span data-ttu-id="b07cd-199">保留及刪除 Teams 會議錄製的功能已在預覽版中推出，且必須將錄製儲存到 OneDrive 或 SharePoint，否則無法運作。</span><span class="sxs-lookup"><span data-stu-id="b07cd-199">The ability to retain and delete Teams meeting recordings is rolling out in preview and won't work before recordings are saved to OneDrive or SharePoint.</span></span> <span data-ttu-id="b07cd-200">如需詳細資訊，請參閱[使用商務用 OneDrive 和 SharePoint 或 Stream 進行會議錄製](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-200">For more information, see [Use OneDrive for Business and SharePoint Online or Stream for meeting recordings](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change).</span></span>

<span data-ttu-id="b07cd-201">若要識別儲存在使用者 OneDrive 帳戶或 SharePoint 中的 Microsoft Teams 會議錄製，請為**關鍵字查詢編輯器**指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="b07cd-201">To identify Microsoft Teams meeting recordings that are stored in users' OneDrive accounts or in SharePoint, specify the following for the **Keyword query editor**:</span></span>

``` 
ProgID:Media AND ProgID:Meeting
```

<span data-ttu-id="b07cd-202">針對此保留標籤，您也必須透過建立標籤原則，將它發佈到相關使用者的 OneDrive 帳戶或 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="b07cd-202">For this retention label, you must also publish it to the relevant users' OneDrive accounts or SharePoint sites by creating a label policy.</span></span> <span data-ttu-id="b07cd-203">在多數時候，會議錄製都會儲存到 OneDrive，但針對頻道會議，則是將它們儲存在 SharePoint 中。</span><span class="sxs-lookup"><span data-stu-id="b07cd-203">Most of the time, the meeting recordings are saved to OneDrive, but for channel meetings, they are saved in SharePoint.</span></span>

<span data-ttu-id="b07cd-204">儲存自動套用原則後：</span><span class="sxs-lookup"><span data-stu-id="b07cd-204">When you have saved the auto-apply policy:</span></span>

1. <span data-ttu-id="b07cd-205">選取 [標籤原則 **]** 索引標籤 > [發佈標籤 **]**</span><span class="sxs-lookup"><span data-stu-id="b07cd-205">Select **Label policies** tab > **Publish labels**</span></span>

2. <span data-ttu-id="b07cd-206">當系統提示您選取標籤時，請選擇您使用 KQL 查詢建立的標籤，以找出 Teams 會議錄製。</span><span class="sxs-lookup"><span data-stu-id="b07cd-206">When prompted to select a label, choose the label you created with the KQL query to identify Teams meeting recordings.</span></span>

3. <span data-ttu-id="b07cd-207">當系統提示您輸入位置時，請選擇 [SharePoint 網站 **]**，然後選擇 [OneDrive 帳戶 **]**。</span><span class="sxs-lookup"><span data-stu-id="b07cd-207">When prompted for the location, choose **SharePoint sites** and **OneDrive accounts**.</span></span> <span data-ttu-id="b07cd-208">然後您可以保留預設值**全部**，或指定個別位置，例如，包含或排除特定 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="b07cd-208">You can then keep the default of **All**, or specify individual locations, such as including or excluding specific OneDrive accounts.</span></span>

4. <span data-ttu-id="b07cd-209">完成精靈並儲存此標籤原則。</span><span class="sxs-lookup"><span data-stu-id="b07cd-209">Complete the wizard and save this label policy.</span></span>

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="b07cd-210">使用可訓練分類器自動將標籤套用至內容</span><span class="sxs-lookup"><span data-stu-id="b07cd-210">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="b07cd-211">選擇用於可訓練分類器的選項時，可以選取其中一個內建分類器或自訂分類器。</span><span class="sxs-lookup"><span data-stu-id="b07cd-211">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="b07cd-212">內建分類器包括 [履歷]\*\*\*\*、[原始程式碼]\*\*\*\*、[針對性騷擾]\*\*\*\*、[粗話]\*\*\*\* 和 [威脅]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="b07cd-212">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![選擇可訓練分類器](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="b07cd-214">我們正在淘汰 [粗穢言語]\*\*\*\* 內建分類器，因為這個分類器產生了大量的誤報。</span><span class="sxs-lookup"><span data-stu-id="b07cd-214">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="b07cd-215">請不要使用這個內建分類器，如果您目前正在使用此分類器，請將您的商務流程移開。</span><span class="sxs-lookup"><span data-stu-id="b07cd-215">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="b07cd-216">建議您改用 [針對性騷擾]\*\*\*\*、[粗話]\*\*\*\* 和 [威脅]\*\*\*\* 內建分類器。</span><span class="sxs-lookup"><span data-stu-id="b07cd-216">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="b07cd-217">若要使用此選項自動套用標籤，SharePoint 網站和信箱必須有至少 10 MB 的資料。</span><span class="sxs-lookup"><span data-stu-id="b07cd-217">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="b07cd-218">如需可訓練分類器的詳細資訊，請參閱[了解可訓練分類器 (預覽)](classifier-learn-about.md)(部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-218">For more information about trainable classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="b07cd-219">如果您使用的是 Exchange 版可訓練分類器，請參閱最近發行的[如何在內容總管中重新定型分類器 (預覽)](classifier-how-to-retrain-content-explorer.md)(部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="b07cd-219">If you use trainable classifiers for Exchange, see the recently released [How to retrain a classifier in content explorer (preview)](classifier-how-to-retrain-content-explorer.md).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="b07cd-220">保留標籤要多久才會生效</span><span class="sxs-lookup"><span data-stu-id="b07cd-220">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="b07cd-221">當您自動套用保留標籤，可能需要最多 7 天，保留標籤才會套用至符合條件的所有現有內容。</span><span class="sxs-lookup"><span data-stu-id="b07cd-221">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自動標籤生效時的圖表](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="b07cd-223">更新保留標籤及其原則</span><span class="sxs-lookup"><span data-stu-id="b07cd-223">Updating retention labels and their policies</span></span>

<span data-ttu-id="b07cd-224">當您編輯保留標籤或自動套用原則，且保留標籤已套用至內容時，除了新識別的內容以外，您更新的設定會自動套用到此內容。</span><span class="sxs-lookup"><span data-stu-id="b07cd-224">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="b07cd-225">在建立及儲存標籤或原則之後，部分設定無法變更，其中包括：</span><span class="sxs-lookup"><span data-stu-id="b07cd-225">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="b07cd-226">保留期間以外的保留設定，除非您已將標籤設定為根據建立時間來保留或刪除內容。</span><span class="sxs-lookup"><span data-stu-id="b07cd-226">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="b07cd-227">將項目標記為記錄的選項。</span><span class="sxs-lookup"><span data-stu-id="b07cd-227">The option to mark items as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b07cd-228">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b07cd-228">Next steps</span></span>

<span data-ttu-id="b07cd-229">請參閱 [使用保留標籤來管理儲存在 SharePoint 中的文件週期](auto-apply-retention-labels-scenario.md)，例如，在 SharePoint 中使用自動套用原則和受管理的屬性，以及以事件為基礎的保留原則，開始保留期間。</span><span class="sxs-lookup"><span data-stu-id="b07cd-229">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
