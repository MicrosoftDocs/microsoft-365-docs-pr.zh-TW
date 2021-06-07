---
title: 自動套用保留標籤以保留或刪除內容
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
description: 建立保留標籤及自動套用標籤原則，以便您可以自動套用標籤以保留所需的內容，並刪除您不需要的內容。
ms.openlocfilehash: 0324f988402d407e30d10a725aa5acebb0a69964
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788391"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="7ae7d-103">自動套用保留標籤以保留或刪除內容</span><span class="sxs-lookup"><span data-stu-id="7ae7d-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="7ae7d-104">*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="7ae7d-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="7ae7d-105">[法規記錄](records-management.md#records)不支援此案例。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-105">This scenario is not supported for [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="7ae7d-106">[保留標籤](retention.md) 最實用的功能之一，是將標籤自動套用至符合特定條件的內容。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-106">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="7ae7d-107">在此情況下，貴組織中的人員不必親自套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-107">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="7ae7d-108">Microsoft 365 會執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-108">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="7ae7d-109">自動套用保留標籤很強大是因為：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-109">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="7ae7d-110">您不需要訓練您的使用者記下所有分類。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-110">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="7ae7d-111">您不需要仰賴使用者正確地將所有內容分類。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-111">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="7ae7d-112">使用者不再需要了解資料控管原則，他們可以專心工作。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-112">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="7ae7d-113">當內容包含敏感性資訊、關鍵字或[可訓練分類器](classifier-get-started-with.md)的相符項目時，您可以自動對該內容套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-113">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

> [!TIP]
> <span data-ttu-id="7ae7d-114">最近發行，使用可搜尋的屬性來識別 [Teams 會議錄製](#microsoft-teams-meeting-recordings)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-114">Recently released, use searchable properties to identify [Teams meeting recordings](#microsoft-teams-meeting-recordings).</span></span>

<span data-ttu-id="7ae7d-115">根據下列條件自動套用保留標籤的程式：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-115">The processes to automatically apply a retention label based on these conditions:</span></span>

![自動套用標籤的角色和工作圖](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="7ae7d-117">使用下列指示執行兩個系統管理員步驟。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-117">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="7ae7d-118">自動原則會使用條件的服務端標籤來自動套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-118">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="7ae7d-119">當您執行下列動作時，您也可以使用標籤原則以自動套用保留標籤：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-119">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="7ae7d-120">在 SharePoint Syntex 中套用保留標籤到文件瞭解模型</span><span class="sxs-lookup"><span data-stu-id="7ae7d-120">Apply a retention label to a document understanding model in SharePoint Syntex</span></span>
> - <span data-ttu-id="7ae7d-121">為 SharePoint 和 Outlook 套用預設的保留標籤</span><span class="sxs-lookup"><span data-stu-id="7ae7d-121">Apply a default retention label for SharePoint and Outlook</span></span>
>- <span data-ttu-id="7ae7d-122">使用 Outlook 規則將保留標籤套用至電子郵件</span><span class="sxs-lookup"><span data-stu-id="7ae7d-122">Apply a retention label to email by using Outlook rules</span></span>
>
> <span data-ttu-id="7ae7d-123">在這些情況下，請參閱 [在應用程式中建立集套用保留標籤](create-apply-retention-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-123">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7ae7d-124">開始之前</span><span class="sxs-lookup"><span data-stu-id="7ae7d-124">Before you begin</span></span>

<span data-ttu-id="7ae7d-125">您組織中的全域系統管理員擁有建立及管理保留標籤及其原則的完整權限。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-125">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="7ae7d-126">如果您未以全域系統管理員身分登入，請參閱[建立和管理保留標籤所需權限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-126">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="7ae7d-127">如何自動套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="7ae7d-127">How to auto-apply a retention label</span></span>

<span data-ttu-id="7ae7d-128">首先，建立您自己的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-128">First, create your retention label.</span></span> <span data-ttu-id="7ae7d-129">然後建立自動原則來套用該標籤。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-129">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="7ae7d-130">如果您已經建立保留標籤，請跳至 [建立自動原則](#step-2-create-an-auto-apply-policy)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-130">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="7ae7d-131">瀏覽指示取決於您使用的是否是 [記錄管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-131">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="7ae7d-132">以下提供這兩個案例的指示。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-132">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="7ae7d-133">步驟1: 建立保留標籤。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-133">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="7ae7d-134">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-134">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="7ae7d-135">如果您使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-135">If you are using records management:</span></span>
        - <span data-ttu-id="7ae7d-136">[解決方案]  >  [記錄管理]  >  [檔案計劃] 索引標籤 > [+ 建立標籤]  >  [保留標籤]</span><span class="sxs-lookup"><span data-stu-id="7ae7d-136">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="7ae7d-137">如果您未使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-137">If you are not using records management:</span></span>
       - <span data-ttu-id="7ae7d-138">[解決方案]  >  [資訊控管]  >  [標籤] 索引標籤 > [+ 建立標籤]</span><span class="sxs-lookup"><span data-stu-id="7ae7d-138">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="7ae7d-139">沒有立即看到您的選項？</span><span class="sxs-lookup"><span data-stu-id="7ae7d-139">Don't immediately see your option?</span></span> <span data-ttu-id="7ae7d-140">先選取 [顯示全部]。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-140">First select **Show all**.</span></span> 

2. <span data-ttu-id="7ae7d-141">遵循精靈中的提示進行。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-141">Follow the prompts in the wizard.</span></span> <span data-ttu-id="7ae7d-142">如果您使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-142">If you are using records management:</span></span>
    
    - <span data-ttu-id="7ae7d-143">如需檔案計劃描述元的詳細資訊，請參閱[使用檔案計劃管理保留標籤](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="7ae7d-143">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="7ae7d-144">若要使用保留標籤來宣告記錄，請選取 [將項目標記為記錄 **]**，或 [將項目標記為法規記錄 **]**。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-144">To use the retention label to declare records, select **Mark items as records**, or **Mark items as regulatory records**.</span></span> <span data-ttu-id="7ae7d-145">如需詳細資訊，請參閱[設定保留標籤以宣告記錄](declare-records.md#configuring-retention-labels-to-declare-records)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-145">For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="7ae7d-146">建立標籤並看到發佈標籤、自動套用標籤或僅保存標籤的選項：選取 **[自動將此標籤套用於特定類型的內容]**，然後選取 **[完成]** 以啟動 [建立自動標籤] 精靈，該精靈將直接帶您進入以下過程中的步驟 2。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-146">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="7ae7d-147">若要編輯現有的標籤，請選取它，然後選取 **[編輯標籤]** 以啟動編輯保留精靈讓您變更標籤描述和步驟 2 的任何 [合格設定](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-147">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="7ae7d-148">步驟2：建立自動套用原則</span><span class="sxs-lookup"><span data-stu-id="7ae7d-148">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="7ae7d-149">當您建立自動套用原則時，會根據您指定的條件，選取要自動套用至內容的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-149">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="7ae7d-150">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="7ae7d-151">如果您使用記錄管理：**資訊控管**：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-151">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="7ae7d-152">**[解決方案]**  > **[記錄管理]**  > **[標籤原則]** 索引標籤 > **[自動套用標籤]**</span><span class="sxs-lookup"><span data-stu-id="7ae7d-152">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="7ae7d-153">如果您未使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-153">If you are not using records management:</span></span>
        - <span data-ttu-id="7ae7d-154">**[解決方案]**  >  **[資訊控管]**  >  **[標籤原則]** 索引標籤 > **[自動套用標籤]**</span><span class="sxs-lookup"><span data-stu-id="7ae7d-154">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="7ae7d-155">沒有立即看到您的選項？</span><span class="sxs-lookup"><span data-stu-id="7ae7d-155">Don't immediately see your option?</span></span> <span data-ttu-id="7ae7d-156">先選取 [顯示全部]。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-156">First select **Show all**.</span></span> 

2. <span data-ttu-id="7ae7d-157">按照 [建立自動標籤精靈] 中的提示。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-157">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="7ae7d-158">如需有關設定會自動套用保留標籤之條件的詳細資訊，請參閱此頁面上的[設定自動套用保留標籤的條件](#configuring-conditions-for-auto-apply-retention-labels)一節。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-158">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="7ae7d-159">如需保留標籤支援的位置詳細資訊，請參閱[保留標籤和位置](retention.md#retention-label-policies-and-locations)一節。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-159">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="7ae7d-160">若要編輯現有的自動套用原則，請選取該原則以啟動可讓您變更所選取保留標籤和來自步驟 2 的任何[合格設定](#updating-retention-labels-and-their-policies)的編輯保留原則精靈。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-160">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

<span data-ttu-id="7ae7d-161">使用自動套用標籤原則為內容加上標籤之後，您無法透過變更內容或原則或使用新的自動套用標籤原則來自動移除或變更已套用的標籤。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-161">After content is labeled by using an auto-apply label policy, the applied label can't be automatically removed or changed by changing the content or the policy, or by a new auto-apply label policy.</span></span> <span data-ttu-id="7ae7d-162">如需詳細資訊，請參閱[一次僅一個保留標籤](retention.md#only-one-retention-label-at-a-time)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-162">For more information, see [Only one retention label at a time](retention.md#only-one-retention-label-at-a-time).</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="7ae7d-163">設定自動套用保留標籤的條件</span><span class="sxs-lookup"><span data-stu-id="7ae7d-163">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="7ae7d-164">您可以在內容包含以下資訊時，自動將保留標籤套用到內容：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-164">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="7ae7d-165">特定敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="7ae7d-165">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="7ae7d-166">符合您所建立查詢的特定關鍵字或可搜尋的屬性</span><span class="sxs-lookup"><span data-stu-id="7ae7d-166">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="7ae7d-167">可訓練分類器的符合項目</span><span class="sxs-lookup"><span data-stu-id="7ae7d-167">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="7ae7d-168">自動將標籤套用至包含特定類型敏感資訊的內容</span><span class="sxs-lookup"><span data-stu-id="7ae7d-168">Auto-apply labels to content with specific types of sensitive information</span></span>

> [!WARNING]
> <span data-ttu-id="7ae7d-169">此設定目前有已知的限制，其中當您所選的敏感性資訊類型有相符的項目時，所有未標記的電子郵件都必須套用選取的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-169">This configuration currently has a known limitation where all unlabeled emails always have the selected retention label applied when there is a match for your chosen sensitive information types.</span></span> <span data-ttu-id="7ae7d-170">例如，即使您將自動套用原則限定為特定的使用者，或是選取 Exchange 原則以外的位置，但一旦有相符的項目時，標籤就會套用到未標記的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-170">For example, even if you scope your auto-apply policy to specific users, or select locations other than Exchange for the policy, the label is always applied to unlabeled emails when there is a match.</span></span>

<span data-ttu-id="7ae7d-171">當您為敏感性資訊建立自動套用保留標籤原則時，系統會顯示與建立資料外洩防護 (DLP) 原則時相同的原則範本清單。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-171">When you create auto-apply retention label policies for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="7ae7d-172">每個範本預設會尋找特定類型的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-172">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="7ae7d-173">在下列範例中，敏感性資訊類型來自 **隱私權** 類別，以及 **美國個人識別資訊 (PII) 資料** 範本：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-173">In the following example, the sensitive info types are from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data** template:</span></span>

![敏感資訊類型的原則範本](../media/sensitive-info-configuration.png)

<span data-ttu-id="7ae7d-175">了解有關敏感性資訊類型的更多資訊，請參閱[敏感性資訊類型實體定義](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-175">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span> <span data-ttu-id="7ae7d-176">目前 [精確資料比對](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) 和 [文件指紋](document-fingerprinting.md) 在此案例中不支援。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-176">Currently, [exact data matches](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) and [document fingerprinting](document-fingerprinting.md) are not supported for this scenario.</span></span>

<span data-ttu-id="7ae7d-p114">選取原則範本後，可以新增或移除任何類型的敏感性資訊，且可以變更信賴等級和執行個體計數。在前一個範例螢幕擷取畫面中，已變更這些選項，因此只有符合以下條件時，才會自動套用保留標籤：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-p114">After you select a policy template, you can add or remove any types of sensitive information, and you can change the confidence level and instance count. In the previous example screenshot, these options have been changed so that a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="7ae7d-179">偵測到的敏感性資訊類型中的兩種具有至少 **中信賴等級** 的比對精確度 (或 [信賴等級](sensitive-information-type-learn-about.md#more-on-confidence-levels))，而一個為 **高信賴等級**。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-179">The type of sensitive information that's detected has a match accuracy (or [confidence level](sensitive-information-type-learn-about.md#more-on-confidence-levels)) of at least **Medium confidence** for two of the sensitive info types, and **High confidence** for one.</span></span> <span data-ttu-id="7ae7d-180">許多機密資訊類型是與多個合作夥伴所定義；比對精確度越高的模式需要更多證據 (例如關鍵字、日期或地址)，比對精確度越低的模式則需要較少證據。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-180">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="7ae7d-181">信賴等級越低，內容就越容易符合條件，但可能會產生更多誤判。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-181">The lower the confidence level, the easier it is for content to match the condition but with the potential for more false positives.</span></span>

- <span data-ttu-id="7ae7d-182">內容包含 1 到 9 個以下三種敏感性資訊類型其中之一的執行個體。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-182">The content contains between 1 and 9 instances of any of these three sensitive info types.</span></span> <span data-ttu-id="7ae7d-183">**至** 的預設值為 **Any**。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-183">The default for the **to** value is **Any**.</span></span>

<span data-ttu-id="7ae7d-184">有關這些選項的更多資訊，請參閱 DLP 檔案中的以下指導方針[調整規則以讓它們更容易更難符合](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-184">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="7ae7d-185">在使用敏感性資訊類型以自動套用保留標籤時，請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-185">To consider when using sensitive information types to auto-apply retention labels:</span></span>

- <span data-ttu-id="7ae7d-186">新增和修改的項目可自動貼上標籤。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-186">New and modified items can be auto-labeled.</span></span>

#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="7ae7d-187">自動將標籤套用至包含關鍵字或可搜尋屬性的內容</span><span class="sxs-lookup"><span data-stu-id="7ae7d-187">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="7ae7d-p117">您可以使用包含特定字詞、片語或可搜尋屬性的查詢，自動將標籤套用至內容。您可以使用 AND、OR 和 NOT 等搜尋運算子來精簡查詢。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-p117">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![查詢編輯器](../media/new-retention-query-editor.png)

<span data-ttu-id="7ae7d-191">如需使用關鍵字查詢語言 (KQL) 的查詢語法的詳細資訊，請參閱[關鍵字查詢語言 (KQL) 語法參考](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-191">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="7ae7d-192">查詢式自動套用原則使用與 eDiscovery 內容搜尋相同的搜尋索引來識別內容。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-192">Query-based auto-apply policies use the same search index as eDiscovery content search to identify content.</span></span> <span data-ttu-id="7ae7d-193">如需有關您可使用的可搜尋屬性詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-193">For more information about the searchable properties that you can use, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

<span data-ttu-id="7ae7d-194">在使用關鍵字或可搜尋屬性以自動套用保留標籤時，請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-194">Some things to consider when using keywords or searchable properties to auto-apply retention labels:</span></span>

- <span data-ttu-id="7ae7d-195">SharePoint、OneDrive 和 Exchange 的新增、已修改及既有項目將會自動標示。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-195">New, modified, and existing items will be auto-labeled for SharePoint, OneDrive, and Exchange.</span></span>

- <span data-ttu-id="7ae7d-196">針對 SharePoint，這些 KQL 查詢不支援編目屬性和自訂屬性，因此您必須僅使用預先定義的受管理屬性。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-196">For SharePoint, crawled properties and custom properties aren't supported for these KQL queries and you must use only predefined managed properties.</span></span> <span data-ttu-id="7ae7d-197">不過，您可以在租用戶等級使用對應，並使用預設啟用為精簡器的預先定義 Managed 屬性  (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09, and RefinableDouble00-09)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-197">However, you can use mappings at the tenant level with the predefined managed properties that are enabled as refiners by default (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09, and RefinableDouble00-09).</span></span> <span data-ttu-id="7ae7d-198">如需詳細資訊，請參閱[SharePoint 伺服器中的編目及受管理屬性概觀](/SharePoint/technical-reference/crawled-and-managed-properties-overview)，及如需相關指示，請參閱 [建立新的受管理屬性](/sharepoint/manage-search-schema#create-a-new-managed-property)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-198">For more information, see [Overview of crawled and managed properties in SharePoint Server](/SharePoint/technical-reference/crawled-and-managed-properties-overview), and for instructions, see [Create a new managed property](/sharepoint/manage-search-schema#create-a-new-managed-property).</span></span>

- <span data-ttu-id="7ae7d-199">如果您將自訂屬性對應到其中一個精簡器屬性，使用前請等候 24 小時，再在 KQL 查詢中使用該屬性來保留標籤。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-199">If you map a custom property to one of the refiner properties, wait 24 hours before you use it in your KQL query for a retention label.</span></span>

- <span data-ttu-id="7ae7d-200">儘管可以使用別名來重新命名 SharePoint 管理屬性，但不要在你的標籤中使用這些名稱進行 KQL 查詢。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-200">Although SharePoint managed properties can be renamed by using aliases, don't use these for KQL queries in your labels.</span></span> <span data-ttu-id="7ae7d-201">一律指定受管理屬性的實際名稱，例如，"RefinableString01"。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-201">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

- <span data-ttu-id="7ae7d-202">若要搜尋含有空格或特殊字元的值，請使用雙引號 (`" "`) 括住片語;例如，`subject:"Financial Statements"`。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-202">To search for values that contain spaces or special characters, use double quotation marks (`" "`) to contain the phrase; for example, `subject:"Financial Statements"`.</span></span>

- <span data-ttu-id="7ae7d-203">使用 *DocumentLink* 屬性取代 *Path* 並根據其 URL 比對項目。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-203">Use the *DocumentLink* property instead of *Path* to match an item based on its URL.</span></span> 

- <span data-ttu-id="7ae7d-204">不支援尾碼萬用字元搜尋 (像是 `*cat`) 或子字串萬用字元搜尋 (像是 `*cat*`)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-204">Suffix wildcard searches ( such as `*cat`) or substring wildcard searches (such as `*cat*`) aren't supported.</span></span> <span data-ttu-id="7ae7d-205">不過，會支援前置萬用字元搜尋 (例如 `cat*`)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-205">However, prefix wildcard searches (such as `cat*`) are supported.</span></span>

- <span data-ttu-id="7ae7d-206">請注意，部分編製索引的項目可能是導致無法將您預期的項目進行標示、或在您使用 NOT 運算子時，將您預期排除標示的項目進行標示的原因。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-206">Be aware that partially indexed items can be responsible for not labeling items that you're expecting, or labeling items that you're expecting to be excluded from labeling when you use the NOT operator.</span></span> <span data-ttu-id="7ae7d-207">如需詳細資訊，請參閱 [內容搜尋中的部分編製索引的項目](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-207">For more information, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>


<span data-ttu-id="7ae7d-208">範例查詢：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-208">Examples queries:</span></span>

| <span data-ttu-id="7ae7d-209">工作負載</span><span class="sxs-lookup"><span data-stu-id="7ae7d-209">Workload</span></span> | <span data-ttu-id="7ae7d-210">範例</span><span class="sxs-lookup"><span data-stu-id="7ae7d-210">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="7ae7d-211">Exchange</span><span class="sxs-lookup"><span data-stu-id="7ae7d-211">Exchange</span></span>   | `subject:"Financial Statements"` |
|<span data-ttu-id="7ae7d-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="7ae7d-212">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="7ae7d-213">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7ae7d-213">SharePoint</span></span> | `contenttype:document` |
|<span data-ttu-id="7ae7d-214">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7ae7d-214">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:document`|
|<span data-ttu-id="7ae7d-215">Exchange 或 SharePoint</span><span class="sxs-lookup"><span data-stu-id="7ae7d-215">Exchange or SharePoint</span></span> | `"customer information" OR "private"`|

<span data-ttu-id="7ae7d-216">更多複雜的問題:</span><span class="sxs-lookup"><span data-stu-id="7ae7d-216">More complex examples:</span></span>

<span data-ttu-id="7ae7d-217">當 Word 文件或 Excel 試算表含有關鍵字 **密碼**、**密碼** 或 **pw** 時，下列 SharePoint 查詢可以識別出這些檔案：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-217">The following query for SharePoint identifies Word documents or Excel spreadsheets when those files contain the keywords **password**, **passwords**, or **pw**:</span></span>

```
(password OR passwords OR pw) AND (filetype:doc* OR filetype:xls*)
```

<span data-ttu-id="7ae7d-218">當附加至電子郵件的 Word 文件或 PDF 中含有文字 **保密合約 (nda)** 或字詞 **non disclosure agreement (保密合約)** 時，下列 Exchange 查詢可以識別出這些檔案：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-218">The following query for Exchange identifies any Word document or PDF that contains the word **nda** or the phrase **non disclosure agreement** when those documents are attached to an email:</span></span>

```
(nda OR "non disclosure agreement") AND (attachmentnames:.doc* OR attachmentnames:.pdf)
```

<span data-ttu-id="7ae7d-219">下列 SharePoint 查詢會識別含有信用卡號碼的檔案：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-219">The following query for SharePoint identifies documents that contain a credit card number:</span></span> 

```
sensitivetype:"credit card number"
```

<span data-ttu-id="7ae7d-220">下列查詢包含部分的一般關鍵字，以協助識別含有法律內容的文件或電子郵件：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-220">The following query contains some typical keywords to help identify documents or emails that contain legal content:</span></span>

```
ACP OR (Attorney Client Privilege*) OR (AC Privilege)
```

<span data-ttu-id="7ae7d-221">下列查詢包含一般的關鍵字，以協助識別適用於人力資源的文件或電子郵件：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-221">The following query contains typical keywords to help identify documents or emails for human resources:</span></span> 

```
(resume AND staff AND employee AND salary AND recruitment AND candidate)
```

<span data-ttu-id="7ae7d-222">請注意，最後這個範例使用了最佳做法，即是在關鍵字之間一律包括運算子。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-222">Note that this final example uses the best practice of always including  operators between keywords.</span></span> <span data-ttu-id="7ae7d-223">在兩個關鍵字 (或兩個 property:value 運算式) 之間使用空格，效果等同於使用 AND。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-223">A space between keywords (or two property:value expressions) is the same as using AND.</span></span> <span data-ttu-id="7ae7d-224">只要一律新增運算子，您就可以更輕鬆地查看這個範例查詢只會識別含有所有這些關鍵字的內容，而不是含有任何關鍵字的內容。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-224">By always adding operators, it's easier to see that this example query will identify only content that contains all these keywords, instead of content that contains any of the keywords.</span></span> <span data-ttu-id="7ae7d-225">如果您想要識別包含任何關鍵字的內容，請指定或 (OR)，而不是和 (AND)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-225">If your intention is to identify content that contains any of the keywords, specify OR instead of AND.</span></span> <span data-ttu-id="7ae7d-226">如這個範例所示，當您一律指定運算子時，更容易正確解讀查詢。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-226">As this example shows, when you always specify the operators, it's easier to correctly interpret the query.</span></span> 

##### <a name="microsoft-teams-meeting-recordings"></a><span data-ttu-id="7ae7d-227">Microsoft Teams 會議錄製</span><span class="sxs-lookup"><span data-stu-id="7ae7d-227">Microsoft Teams meeting recordings</span></span>

> [!NOTE]
> <span data-ttu-id="7ae7d-228">必須將錄製儲存到 OneDrive 或 SharePoint，否則保留及刪除 Teams 會議錄製的功能無法運作。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-228">The ability to retain and delete Teams meeting recordings won't work before recordings are saved to OneDrive or SharePoint.</span></span> <span data-ttu-id="7ae7d-229">如需詳細資訊，請參閱[使用 [商務用 OneDrive] 和 SharePoint Online 或 Stream 進行會議錄製](/MicrosoftTeams/tmr-meeting-recording-change)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-229">For more information, see [Use OneDrive for Business and SharePoint Online or Stream for meeting recordings](/MicrosoftTeams/tmr-meeting-recording-change).</span></span>

<span data-ttu-id="7ae7d-230">若要識別儲存在使用者 OneDrive 帳戶或 SharePoint 中的 Microsoft Teams 會議錄製，請為 **關鍵字查詢編輯器** 指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-230">To identify Microsoft Teams meeting recordings that are stored in users' OneDrive accounts or in SharePoint, specify the following for the **Keyword query editor**:</span></span>

``` 
ProgID:Media AND ProgID:Meeting
```

<span data-ttu-id="7ae7d-p125">在多數時候，會議錄製都會儲存到 OneDrive，但頻道會議則是儲存在 SharePoint 中。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-p125">Most of the time, meeting recordings are saved to OneDrive. But for channel meetings, they are saved in SharePoint.</span></span>


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="7ae7d-233">使用可訓練分類器自動將標籤套用至內容</span><span class="sxs-lookup"><span data-stu-id="7ae7d-233">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="7ae7d-234">選擇用於可訓練分類器的選項時，可以選取其中一個內建分類器或自訂分類器。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-234">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="7ae7d-235">內建分類器包括 [履歷]、[原始程式碼]、[針對性騷擾]、[粗話] 和 [威脅]：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-235">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![選擇可訓練分類器](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="7ae7d-237">我們正在淘汰 [粗穢言語] 內建分類器，因為這個分類器產生了大量的誤報。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-237">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="7ae7d-238">請不要使用這個內建分類器，如果您目前正在使用此分類器，請將您的商務流程移開。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-238">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="7ae7d-239">建議您改用 [針對性騷擾]、[粗話] 和 [威脅] 內建分類器。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-239">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="7ae7d-240">若要使用此選項自動套用標籤，SharePoint 網站和信箱必須有至少 10 MB 的資料。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-240">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="7ae7d-241">如需可訓練分類器的詳細資訊，請參閱[深入了解可訓練分類器](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-241">For more information about trainable classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="7ae7d-242">如果您使用的是 Exchange 版可訓練分類器，請參閱[如何在內容總管中重新定型分類器 (預覽)](classifier-how-to-retrain-content-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-242">If you use trainable classifiers for Exchange, see [How to retrain a classifier in content explorer](classifier-how-to-retrain-content-explorer.md).</span></span>

<span data-ttu-id="7ae7d-243">在使用可訓練分類器以自動套用保留標籤時，請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-243">To consider when using trainable classifiers to auto-apply retention labels:</span></span>

- <span data-ttu-id="7ae7d-244">可自動標示新增和修改的項目，以及最近六個月的現有項目。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-244">New and modified items can be auto-labeled, and existing items from the last six months.</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="7ae7d-245">保留標籤要多久才會生效</span><span class="sxs-lookup"><span data-stu-id="7ae7d-245">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="7ae7d-246">當您自動套用保留標籤，可能需要最多 7 天，保留標籤才會套用至符合條件的所有現有內容。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-246">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自動標籤生效時的圖表](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

<span data-ttu-id="7ae7d-248">如果預期的標籤在七天之後未顯示，請在合規性中心的 [標籤原則 **]** 頁面中選取自動套用原則，以檢查其 [狀態 **]**。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-248">If the expected labels don't appear after seven days, check the **Status** of the auto-apply policy by selecting it from the **Label policies** page in the compliance center.</span></span> <span data-ttu-id="7ae7d-249">如果您看到 **關閉 (錯誤)** 狀態，且在位置的詳細資料中，看到訊息說明部署原則 (針對 SharePoint) 或嘗試重新部署原則 (針對 OneDrive) 所耗費的時間超過預期，請嘗試執行 [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell 命令以重試原則發佈：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-249">If you see the status of **Off (Error)** and in the details for the locations see a message that it's taking longer than expected to deploy the policy (for SharePoint) or to try redeploying the policy (for OneDrive), try running the [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell command to retry the policy distribution:</span></span>

1. <span data-ttu-id="7ae7d-250">[連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-250">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="7ae7d-251">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-251">Run the following command:</span></span>
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="7ae7d-252">更新保留標籤及其原則</span><span class="sxs-lookup"><span data-stu-id="7ae7d-252">Updating retention labels and their policies</span></span>

<span data-ttu-id="7ae7d-253">當您編輯保留標籤或自動套用原則，且保留標籤已套用至內容時，除了新識別的內容以外，您更新的設定會自動套用到此內容。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-253">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="7ae7d-254">在建立及儲存標籤或原則之後，部分設定無法變更，其中包括：</span><span class="sxs-lookup"><span data-stu-id="7ae7d-254">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="7ae7d-255">保留標籤和原則名稱，以及保留期間以外的保留設定。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-255">The retention label and policy name, and the retention settings except the retention period.</span></span> <span data-ttu-id="7ae7d-256">不過，當保留期間是以項目標記的時間為根據時，您就無法變更保留期間。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-256">However, you can't change the retention period when the retention period is based on when items were labeled.</span></span>
- <span data-ttu-id="7ae7d-257">將項目標記為記錄的選項。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-257">The option to mark items as a record.</span></span>

### <a name="deleting-retention-labels"></a><span data-ttu-id="7ae7d-258">刪除保留標籤</span><span class="sxs-lookup"><span data-stu-id="7ae7d-258">Deleting retention labels</span></span>

<span data-ttu-id="7ae7d-259">您可以刪除目前未包含在任何保留標籤原則中、未針對事件型保留所設定的保留標籤，或將項目標示為法規記錄。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-259">You can delete retention labels that aren't currently included in any retention label policies, that aren't configured for event-based retention, or mark items as regulatory records.</span></span>

<span data-ttu-id="7ae7d-260">針對您可以刪除的保留標籤，如果該標籤已套用至項目中，則會刪除失敗，而且您會看到一個連線至內容瀏覽器的連結，以識別已標籤的項目。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-260">For retention labels that you can delete, if they have been applied to items, the deletion fails and you see a link to content explorer to identify the labeled items.</span></span>

<span data-ttu-id="7ae7d-261">不過，內容瀏覽器最多可能需要兩天才能顯示已標籤的項目。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-261">However, it can take up to two days for content explorer to show the items that are labeled.</span></span> <span data-ttu-id="7ae7d-262">在此情況中，保留標籤可能會被刪除，而不會向您顯示連線至內容瀏覽器的連結。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-262">In this scenario, the retention label might be deleted without showing you the link to content explorer.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="7ae7d-263">鎖定原則以防止變更</span><span class="sxs-lookup"><span data-stu-id="7ae7d-263">Locking the policy to prevent changes</span></span>

<span data-ttu-id="7ae7d-264">如果您需要確保沒有人可以關閉原則、刪除原則或放寬限制，請參閱[使用「保留鎖定」來限制變更保留原則和保留標籤原則](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-264">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7ae7d-265">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7ae7d-265">Next steps</span></span>

<span data-ttu-id="7ae7d-266">請參閱 [使用保留標籤來管理儲存在 SharePoint 中的文件週期](auto-apply-retention-labels-scenario.md)，例如，在 SharePoint 中使用自動套用保留標籤原則和受管理的屬性，以及以事件為基礎的保留原則，開始保留期間。</span><span class="sxs-lookup"><span data-stu-id="7ae7d-266">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply retention label policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>