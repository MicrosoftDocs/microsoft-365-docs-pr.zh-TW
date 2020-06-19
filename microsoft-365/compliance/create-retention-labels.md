---
title: 建立、發佈和自動套用保留標籤
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
description: 建立、發佈及自動套用保留標籤，以在您的 Office 365 環境中保留您需要的內容、刪除您不想要的項目，以及將項目宣告為記錄的相關指示。
ms.openlocfilehash: 035038c90179354e0497813326b1fdad01693bec
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761649"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a><span data-ttu-id="bf27f-103">建立、發佈和自動套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="bf27f-103">Create, publish, and auto-apply retention labels</span></span>

><span data-ttu-id="bf27f-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="bf27f-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="bf27f-105">使用下列資訊來協助您建立[保留標籤](labels.md)，然後將標籤自動套用至文件和電子郵件，或發佈標籤，使得使用者可以手動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="bf27f-105">Use the following information to help you create [retention labels](labels.md), and then automatically apply them to documents and emails, or publish them so that users can manually apply them.</span></span>

<span data-ttu-id="bf27f-106">保留標籤可協助您保留所需的內容，並刪除您不需要的內容。</span><span class="sxs-lookup"><span data-stu-id="bf27f-106">Retention labels help you retain what you need and delete what you don't.</span></span> <span data-ttu-id="bf27f-107">它們也可以用來將項目宣告為記錄，做為 Microsoft 365 資料的[記錄管理](records-management.md)解決方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="bf27f-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="bf27f-108">您建立及設定保留標籤的位置，取決於您是否使用記錄管理。</span><span class="sxs-lookup"><span data-stu-id="bf27f-108">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="bf27f-109">以下提供這兩個案例的指示。</span><span class="sxs-lookup"><span data-stu-id="bf27f-109">Instructions are provided for both scenarios.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bf27f-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="bf27f-110">Before you begin</span></span>

<span data-ttu-id="bf27f-111">您的合規性小組中負責建立保留標籤的成員必須具備安全性 &amp; 合規性中心的權限。</span><span class="sxs-lookup"><span data-stu-id="bf27f-111">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="bf27f-112">根據預設，租用戶系統管理員將可存取此位置，並且可直接讓法務人員與其他人存取安全性 &amp; 合規性中心，而不需要為其提供租用戶系統管理員的所有權限。若要這麼做，我們建議您：移至安全性 &amp; 合規性中心的 [權限]\*\*\*\* 頁面，編輯 [合規性系統管理員]\*\*\*\* 角色群組，將該成員新增到此角色群組。</span><span class="sxs-lookup"><span data-stu-id="bf27f-112">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="bf27f-113">如需詳細資訊，請參閱[授與使用者存取 Office 365 安全性與合規性中心的權限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="bf27f-113">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="bf27f-114">These permissions are required only to create and apply retention labels and a label policy.</span><span class="sxs-lookup"><span data-stu-id="bf27f-114">These permissions are required only to create and apply retention labels and a label policy.</span></span> <span data-ttu-id="bf27f-115">Policy enforcement does not require access to the content.</span><span class="sxs-lookup"><span data-stu-id="bf27f-115">Policy enforcement does not require access to the content.</span></span>

## <a name="create-and-configure-retention-labels"></a><span data-ttu-id="bf27f-116">建立及設定保留標籤</span><span class="sxs-lookup"><span data-stu-id="bf27f-116">Create and configure retention labels</span></span>

1. <span data-ttu-id="bf27f-117">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="bf27f-117">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="bf27f-118">如果您使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="bf27f-118">If you are using records management:</span></span>
        - <span data-ttu-id="bf27f-119">[解決方案]\*\*\*\*  >  [記錄管理]\*\*\*\*  >  [檔案計劃]\*\*\*\* 索引標籤 > [+ 建立標籤]\*\*\*\*  >  [保留標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bf27f-119">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="bf27f-120">如果您未使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="bf27f-120">If you are not using records management:</span></span>
       - <span data-ttu-id="bf27f-121">[解決方案]\*\*\*\*  >  [資訊控管]\*\*\*\*  >  [標籤]\*\*\*\* 索引標籤 > [+ 建立標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bf27f-121">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="bf27f-122">沒有立即看到您的選項？</span><span class="sxs-lookup"><span data-stu-id="bf27f-122">Don't immediately see your option?</span></span> <span data-ttu-id="bf27f-123">先選取 [顯示全部]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf27f-123">First select **Show all**.</span></span> 

2. <span data-ttu-id="bf27f-124">遵循精靈中的提示進行。</span><span class="sxs-lookup"><span data-stu-id="bf27f-124">Follow the prompts in the wizard.</span></span> <span data-ttu-id="bf27f-125">如果您使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="bf27f-125">If you are using records management:</span></span>
    
    - <span data-ttu-id="bf27f-126">如需檔案計劃描述元的詳細資訊，請參閱[使用檔案計劃管理保留標籤](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="bf27f-126">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="bf27f-127">若要使用保留標籤將內容宣告為記錄，請啟用 [使用標籤以將內容分類為「記錄」]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bf27f-127">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="bf27f-128">重複這些步驟以建立更多標籤。</span><span class="sxs-lookup"><span data-stu-id="bf27f-128">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="bf27f-129">若要編輯現有的標籤，請選取它，然後選取 [編輯標籤]\*\*\*\* 以啟動相同的精靈讓您變更標籤描述和步驟 2 的任何[合格設定](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="bf27f-129">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="bf27f-130">或者，選取任何一個可用的 [編輯]\*\*\*\* 選項，直接移至相關頁面以進行更新。</span><span class="sxs-lookup"><span data-stu-id="bf27f-130">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a><span data-ttu-id="bf27f-131">建立保留標籤原則來發佈保留標籤</span><span class="sxs-lookup"><span data-stu-id="bf27f-131">Publish retention labels by creating a retention label policy</span></span>

<span data-ttu-id="bf27f-132">發佈保留標籤，讓使用者可以手動套用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="bf27f-132">Publish retention labels so that they can be manually applied by users.</span></span>

1. <span data-ttu-id="bf27f-133">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="bf27f-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="bf27f-134">如果您使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="bf27f-134">If you are using records management:</span></span>
        - <span data-ttu-id="bf27f-135">[解決方案]\*\*\*\*  >  [記錄管理]\*\*\*\* > [標籤原則]\*\*\*\* 索引標籤 > [發佈標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bf27f-135">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="bf27f-136">如果您未使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="bf27f-136">If you are not using records management:</span></span>
        - <span data-ttu-id="bf27f-137">[解決方案]\*\*\*\*  >  [資訊控管]\*\*\*\*  >  [標籤原則]\*\*\*\* 索引標籤 > [發佈標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bf27f-137">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="bf27f-138">沒有立即看到您的選項？</span><span class="sxs-lookup"><span data-stu-id="bf27f-138">Don't immediately see your option?</span></span> <span data-ttu-id="bf27f-139">先選取 [顯示全部]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf27f-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="bf27f-140">遵循精靈中的提示進行。</span><span class="sxs-lookup"><span data-stu-id="bf27f-140">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="bf27f-141">如需保留標籤支援的位置詳細資訊，請參閱[保留標籤和位置](labels.md#retention-label-policies-and-locations)一節。</span><span class="sxs-lookup"><span data-stu-id="bf27f-141">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span> 

<span data-ttu-id="bf27f-142">若要編輯現有的保留標籤原則，請選取它，然後選取 [編輯原則]\*\*\*\*，即可啟動相同的精靈讓您變更原則描述和步驟 2 的任何[合格設定](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="bf27f-142">To edit an existing retention label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="bf27f-143">或者，選取任何一個可用的 [編輯]\*\*\*\* 選項，直接移至相關頁面以進行更新。</span><span class="sxs-lookup"><span data-stu-id="bf27f-143">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

## <a name="auto-apply-a-retention-label"></a><span data-ttu-id="bf27f-144">自動套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="bf27f-144">Auto-apply a retention label</span></span>

<span data-ttu-id="bf27f-145">根據您指定的條件自動套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="bf27f-145">Auto-apply a retention label, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="bf27f-146">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="bf27f-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="bf27f-147">如果您使用記錄管理：**資訊控管**：</span><span class="sxs-lookup"><span data-stu-id="bf27f-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="bf27f-148">[解決方案]\*\*\*\*  >  [記錄管理]\*\*\*\*  >  [標籤原則]\*\*\*\* 索引標籤 > [自動套用標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bf27f-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="bf27f-149">如果您未使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="bf27f-149">If you are not using records management:</span></span>
        - <span data-ttu-id="bf27f-150">[解決方案]\*\*\*\*  >  [資訊控管]\*\*\*\*  >  [標籤原則]\*\*\*\* 索引標籤 > [自動套用標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bf27f-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="bf27f-151">沒有立即看到您的選項？</span><span class="sxs-lookup"><span data-stu-id="bf27f-151">Don't immediately see your option?</span></span> <span data-ttu-id="bf27f-152">先選取 [顯示全部]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf27f-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="bf27f-153">遵循精靈中的提示進行。</span><span class="sxs-lookup"><span data-stu-id="bf27f-153">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="bf27f-154">如需有關設定會自動套用保留標籤之條件的詳細資訊，請參閱此頁面上的[設定自動套用保留標籤的條件](#configuring-conditions-for-auto-apply-retention-labels)一節。</span><span class="sxs-lookup"><span data-stu-id="bf27f-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="bf27f-155">如需保留標籤支援的位置詳細資訊，請參閱[保留標籤和位置](labels.md#retention-label-policies-and-locations)一節。</span><span class="sxs-lookup"><span data-stu-id="bf27f-155">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="bf27f-156">若要編輯現有的自動套用標籤原則，請選取它，然後選取 [編輯原則]\*\*\*\* 以啟動相同的精靈讓您變更標籤描述和步驟 2 的任何[合格設定](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="bf27f-156">To edit an existing auto-apply label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="bf27f-157">或者，選取任何一個可用的 [編輯]\*\*\*\* 選項，直接移至相關頁面以進行更新。</span><span class="sxs-lookup"><span data-stu-id="bf27f-157">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="bf27f-158">設定自動套用保留標籤的條件</span><span class="sxs-lookup"><span data-stu-id="bf27f-158">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="bf27f-159">您可以在內容包含以下資訊時，自動將保留標籤套用到內容：</span><span class="sxs-lookup"><span data-stu-id="bf27f-159">You can apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="bf27f-160">特定敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="bf27f-160">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="bf27f-161">符合您所建立查詢的特定關鍵字</span><span class="sxs-lookup"><span data-stu-id="bf27f-161">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="bf27f-162">可訓練分類器的符合項目</span><span class="sxs-lookup"><span data-stu-id="bf27f-162">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![自動套用標籤的選擇條件頁面](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="bf27f-164">將自動套用保留標籤套用到符合您設定之條件的所有內容，最多可能需要 7 天的時間。</span><span class="sxs-lookup"><span data-stu-id="bf27f-164">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="bf27f-165">自動將標籤套用至包含特定類型敏感資訊的內容</span><span class="sxs-lookup"><span data-stu-id="bf27f-165">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="bf27f-166">當您為敏感性資訊建立自動套用保留標籤時，系統會顯示與建立資料外洩防護 (DLP) 原則時相同的原則範本清單。</span><span class="sxs-lookup"><span data-stu-id="bf27f-166">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="bf27f-167">每個原則範本預設會尋找特定類型的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="bf27f-167">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="bf27f-168">例如本文顯示的範本會尋找美國 ITIN、SSN 和護照號碼。</span><span class="sxs-lookup"><span data-stu-id="bf27f-168">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="bf27f-169">若要深入了解 DLP，請參閱[資料外洩防護原則概觀](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bf27f-169">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![敏感資訊類型的原則範本](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="bf27f-171">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span><span class="sxs-lookup"><span data-stu-id="bf27f-171">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="bf27f-172">In the example shown here, a retention label will be auto-applied only when:</span><span class="sxs-lookup"><span data-stu-id="bf27f-172">In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="bf27f-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="bf27f-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="bf27f-174">You can delete the **max** value so that it changes to **any**.</span><span class="sxs-lookup"><span data-stu-id="bf27f-174">You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="bf27f-175">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span><span class="sxs-lookup"><span data-stu-id="bf27f-175">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="bf27f-176">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span><span class="sxs-lookup"><span data-stu-id="bf27f-176">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="bf27f-177">Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span><span class="sxs-lookup"><span data-stu-id="bf27f-177">Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="bf27f-178">如需這些選項的詳細資訊，請參閱[調整規則，讓規則更容易或更難相符](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="bf27f-178">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![用於識別機密資訊類型的選項](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="bf27f-180">自動將標籤套用至包含關鍵字或可搜尋屬性的內容</span><span class="sxs-lookup"><span data-stu-id="bf27f-180">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="bf27f-181">You can auto-apply labels to content that satisfies certain conditions.</span><span class="sxs-lookup"><span data-stu-id="bf27f-181">You can auto-apply labels to content that satisfies certain conditions.</span></span> <span data-ttu-id="bf27f-182">The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties.</span><span class="sxs-lookup"><span data-stu-id="bf27f-182">The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties.</span></span> <span data-ttu-id="bf27f-183">You can refine your query by using search operators like AND, OR, and NOT.</span><span class="sxs-lookup"><span data-stu-id="bf27f-183">You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="bf27f-184">如需查詢語法的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="bf27f-184">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="bf27f-185">關鍵字查詢語言 (KQL) 語法參考</span><span class="sxs-lookup"><span data-stu-id="bf27f-185">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="bf27f-186">Query-based labels use the search index to identify content.</span><span class="sxs-lookup"><span data-stu-id="bf27f-186">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="bf27f-187">For more information on valid searchable properties, see:</span><span class="sxs-lookup"><span data-stu-id="bf27f-187">For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="bf27f-188">內容搜尋的關鍵字查詢與搜尋條件</span><span class="sxs-lookup"><span data-stu-id="bf27f-188">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="bf27f-189">SharePoint 伺服器中的編目及受控屬性概觀</span><span class="sxs-lookup"><span data-stu-id="bf27f-189">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="bf27f-190">範例查詢：</span><span class="sxs-lookup"><span data-stu-id="bf27f-190">Examples queries:</span></span>

- <span data-ttu-id="bf27f-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="bf27f-191">Exchange</span></span>
    - <span data-ttu-id="bf27f-192">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="bf27f-192">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="bf27f-193">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="bf27f-193">recipients:garthf</span></span><!--nolink--><span data-ttu-id="bf27f-194">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf27f-194">@contoso.com</span></span>
- <span data-ttu-id="bf27f-195">SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="bf27f-195">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="bf27f-196">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="bf27f-196">contenttype:contract</span></span>
    - <span data-ttu-id="bf27f-197">site:https</span><span class="sxs-lookup"><span data-stu-id="bf27f-197">site:https</span></span><!--nolink--><span data-ttu-id="bf27f-198">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="bf27f-198">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![查詢編輯器](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="bf27f-200">使用可訓練分類器自動將標籤套用至內容</span><span class="sxs-lookup"><span data-stu-id="bf27f-200">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="bf27f-201">選擇用於可訓練分類器的選項時，可以選取其中一個內建分類器或自訂分類器。</span><span class="sxs-lookup"><span data-stu-id="bf27f-201">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="bf27f-202">內建分類器包括 [履歷]\*\*\*\*、[原始程式碼]\*\*\*\*、[針對性騷擾]\*\*\*\*、[粗話]\*\*\*\* 和 [威脅]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="bf27f-202">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![選擇可訓練分類器](../media/retention-label-classifers.png)

<span data-ttu-id="bf27f-204">若要使用此選項自動套用標籤，SharePoint Online 網站和信箱必須有至少 10 MB 的資料。</span><span class="sxs-lookup"><span data-stu-id="bf27f-204">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="bf27f-205">如需有關可訓練分類器的詳細資訊，請參閱[開始使用可訓練分類器 (預覽)](classifier-getting-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="bf27f-205">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="bf27f-206">如需組態範例，請參閱[如何準備及使用內建分類器](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)。</span><span class="sxs-lookup"><span data-stu-id="bf27f-206">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="bf27f-207">保留標籤要多久才會生效</span><span class="sxs-lookup"><span data-stu-id="bf27f-207">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="bf27f-208">當您發佈或自動套用保留標籤時，標籤不會立即生效：</span><span class="sxs-lookup"><span data-stu-id="bf27f-208">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="bf27f-209">首先，標籤原則必須先將系統管理中心與原則中的位置同步。</span><span class="sxs-lookup"><span data-stu-id="bf27f-209">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="bf27f-210">接著，位置可能會需要一些時間，將已發佈的保留標籤提供給使用者，或是將標籤自動套用到內容。</span><span class="sxs-lookup"><span data-stu-id="bf27f-210">Then the location might require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="bf27f-211">實際所需的時間取決於保留標籤的位置和類型。</span><span class="sxs-lookup"><span data-stu-id="bf27f-211">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="bf27f-212">已發佈的保留標籤</span><span class="sxs-lookup"><span data-stu-id="bf27f-212">Published retention labels</span></span>

<span data-ttu-id="bf27f-213">If you publish retention labels to SharePoint or OneDrive, those labels  typically appear for end users to select within one day.</span><span class="sxs-lookup"><span data-stu-id="bf27f-213">If you publish retention labels to SharePoint or OneDrive, those labels  typically appear for end users to select within one day.</span></span> <span data-ttu-id="bf27f-214">However, allow up to seven days.</span><span class="sxs-lookup"><span data-stu-id="bf27f-214">However, allow up to seven days.</span></span> <span data-ttu-id="bf27f-215">If you publish retention labels to Exchange, it can take up to seven days for those retention labels to appear for end users, and the mailbox must contain at least 10 MB of data.</span><span class="sxs-lookup"><span data-stu-id="bf27f-215">If you publish retention labels to Exchange, it can take up to seven days for those retention labels to appear for end users, and the mailbox must contain at least 10 MB of data.</span></span>

<span data-ttu-id="bf27f-216">例如：</span><span class="sxs-lookup"><span data-stu-id="bf27f-216">For example:</span></span>
  
![手動標籤生效的圖](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="bf27f-218">自動套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="bf27f-218">Auto-apply retention labels</span></span>

<span data-ttu-id="bf27f-219">如果您將保留標籤自動套用至符合特定條件的內容，可能需要最多 7 天，保留標籤才會套用至符合條件的所有現有內容。</span><span class="sxs-lookup"><span data-stu-id="bf27f-219">If you auto-apply retention labels to content matching specific conditions, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自動標籤生效時的圖表](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="bf27f-221">如何檢查發佈至 Exchange 之保留標籤的狀態</span><span class="sxs-lookup"><span data-stu-id="bf27f-221">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="bf27f-222">在 Exchange Online 中，使用者可透過每 7 天執行一次的程序取得保留標籤。</span><span class="sxs-lookup"><span data-stu-id="bf27f-222">In Exchange Online, retention labels are made available to end users by a process that runs every seven days.</span></span> <span data-ttu-id="bf27f-223">您可以使用 PowerShell 查看這項程序上次執行的時間，藉此判斷下次的執行時間。</span><span class="sxs-lookup"><span data-stu-id="bf27f-223">By using Powershell, you can see when this process last ran and therefore identify when it will run again.</span></span>
  
1. <span data-ttu-id="bf27f-224">[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773)。</span><span class="sxs-lookup"><span data-stu-id="bf27f-224">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="bf27f-225">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="bf27f-225">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}   ```

In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.
    
If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).
    

## Updating retention labels and their policies

When you edit a retention label, retention label policy, or auto-apply policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.

Some settings can't be changed after the label or policy is created and saved, which include:
- The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.
- The option to classify as a record.

## Find the PowerShell cmdlets for retention labels

To use the retention label cmdlets:
  
1. [Connect to the Office 365 Security & Compliance Center Powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. Use these Office 365 Security & Compliance Center cmdlets:
    
    - [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
