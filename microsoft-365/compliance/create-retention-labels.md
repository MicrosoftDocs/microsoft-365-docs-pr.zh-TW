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
ms.openlocfilehash: 1b34833c8320e5d27029474a4da9f0534a63dc51
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262384"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a><span data-ttu-id="da293-103">建立、發佈和自動套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="da293-103">Create, publish, and auto-apply retention labels</span></span>

><span data-ttu-id="da293-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="da293-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="da293-105">使用下列資訊來協助您建立[保留標籤](labels.md)，然後將標籤自動套用至文件和電子郵件，或發佈標籤，使得使用者可以手動套用標籤。</span><span class="sxs-lookup"><span data-stu-id="da293-105">Use the following information to help you create [retention labels](labels.md), and then automatically apply them to documents and emails, or publish them so that users can manually apply them.</span></span>

<span data-ttu-id="da293-106">保留標籤可協助您保留所需的內容，並刪除您不需要的內容。</span><span class="sxs-lookup"><span data-stu-id="da293-106">Retention labels help you retain what you need and delete what you don't.</span></span> <span data-ttu-id="da293-107">它們也可以用來將項目宣告為記錄，做為 Microsoft 365 資料的[記錄管理](records-management.md)解決方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="da293-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="da293-108">您建立及設定保留標籤的位置，取決於您是否使用記錄管理。</span><span class="sxs-lookup"><span data-stu-id="da293-108">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="da293-109">以下提供這兩個案例的指示。</span><span class="sxs-lookup"><span data-stu-id="da293-109">Instructions are provided for both scenarios.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="da293-110">開始之前</span><span class="sxs-lookup"><span data-stu-id="da293-110">Before you begin</span></span>

<span data-ttu-id="da293-111">您的合規性小組中負責建立保留標籤的成員必須具備安全性 &amp; 合規性中心的權限。</span><span class="sxs-lookup"><span data-stu-id="da293-111">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="da293-112">根據預設，租用戶系統管理員將可存取此位置，並且可直接讓法務人員與其他人存取安全性 &amp; 合規性中心，而不需要為其提供租用戶系統管理員的所有權限。若要這麼做，我們建議您：移至安全性 &amp; 合規性中心的 [權限]\*\*\*\* 頁面，編輯 [合規性系統管理員]\*\*\*\* 角色群組，將該成員新增到此角色群組。</span><span class="sxs-lookup"><span data-stu-id="da293-112">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="da293-113">如需詳細資訊，請參閱[授與使用者存取 Office 365 安全性與合規性中心的權限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="da293-113">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="da293-p104">需要這些權限才能建立及套用保留標籤和標籤原則。原則強制執行不需要內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="da293-p104">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>

## <a name="create-and-configure-retention-labels"></a><span data-ttu-id="da293-116">建立及設定保留標籤</span><span class="sxs-lookup"><span data-stu-id="da293-116">Create and configure retention labels</span></span>

1. <span data-ttu-id="da293-117">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="da293-117">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="da293-118">如果您使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="da293-118">If you are using records management:</span></span>
        - <span data-ttu-id="da293-119">[解決方案]\*\*\*\*  >  [記錄管理]\*\*\*\*  >  [檔案計劃]\*\*\*\* 索引標籤 > [+ 建立標籤]\*\*\*\*  >  [保留標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="da293-119">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="da293-120">如果您未使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="da293-120">If you are not using records management:</span></span>
       - <span data-ttu-id="da293-121">[解決方案]\*\*\*\*  >  [資訊控管]\*\*\*\*  >  [標籤]\*\*\*\* 索引標籤 > [+ 建立標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="da293-121">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="da293-122">沒有立即看到您的選項？</span><span class="sxs-lookup"><span data-stu-id="da293-122">Don't immediately see your option?</span></span> <span data-ttu-id="da293-123">先選取 [顯示全部]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da293-123">First select **Show all**.</span></span> 

2. <span data-ttu-id="da293-124">遵循精靈中的提示進行。</span><span class="sxs-lookup"><span data-stu-id="da293-124">Follow the prompts in the wizard.</span></span> <span data-ttu-id="da293-125">如果您使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="da293-125">If you are using records management:</span></span>
    
    - <span data-ttu-id="da293-126">如需有關檔案計劃描述元的資訊，請參閱[檔案計劃管理員的概觀](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="da293-126">For information about the file plan descriptors, see [Overview of file plan manager](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="da293-127">若要使用保留標籤將內容宣告為記錄，請啟用 [使用標籤以將內容分類為「記錄」]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="da293-127">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="da293-128">重複這些步驟以建立更多標籤。</span><span class="sxs-lookup"><span data-stu-id="da293-128">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="da293-129">若要編輯現有的標籤，請將其選取，然後選取 [編輯標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da293-129">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="da293-130">這會啟動相同的精靈，讓您變更步驟 2 中的標籤描述和設定。</span><span class="sxs-lookup"><span data-stu-id="da293-130">This starts the same wizard, which lets you change the label descriptions and settings in step 2.</span></span>

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a><span data-ttu-id="da293-131">建立保留標籤原則來發佈保留標籤</span><span class="sxs-lookup"><span data-stu-id="da293-131">Publish retention labels by creating a retention label policy</span></span>

<span data-ttu-id="da293-132">發佈保留標籤，讓使用者可以手動套用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="da293-132">Publish retention labels so that they can be manually applied by users.</span></span>

1. <span data-ttu-id="da293-133">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="da293-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="da293-134">如果您使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="da293-134">If you are using records management:</span></span>
        - <span data-ttu-id="da293-135">[解決方案]\*\*\*\*  >  [記錄管理]\*\*\*\* > [標籤原則]\*\*\*\* 索引標籤 > [發佈標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="da293-135">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="da293-136">如果您未使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="da293-136">If you are not using records management:</span></span>
        - <span data-ttu-id="da293-137">[解決方案]\*\*\*\*  >  [資訊控管]\*\*\*\*  >  [標籤原則]\*\*\*\* 索引標籤 > [發佈標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="da293-137">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="da293-138">沒有立即看到您的選項？</span><span class="sxs-lookup"><span data-stu-id="da293-138">Don't immediately see your option?</span></span> <span data-ttu-id="da293-139">先選取 [顯示全部]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da293-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="da293-140">遵循精靈中的提示進行。</span><span class="sxs-lookup"><span data-stu-id="da293-140">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="da293-141">如需設定位置的相關資訊，請參閱此頁面上的[保留標籤和位置](#retention-labels-and-locations)一節。</span><span class="sxs-lookup"><span data-stu-id="da293-141">For information about configuring the locations, see the [Retention labels and locations](#retention-labels-and-locations) section on this page.</span></span> 

## <a name="auto-apply-a-retention-label"></a><span data-ttu-id="da293-142">自動套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="da293-142">Auto-apply a retention label</span></span>

<span data-ttu-id="da293-143">根據您指定的條件自動套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="da293-143">Auto-apply a retention label, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="da293-144">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，瀏覽至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="da293-144">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="da293-145">如果您使用記錄管理：**資訊控管**：</span><span class="sxs-lookup"><span data-stu-id="da293-145">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="da293-146">[解決方案]\*\*\*\*  >  [記錄管理]\*\*\*\*  >  [標籤原則]\*\*\*\* 索引標籤 > [自動套用標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="da293-146">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="da293-147">如果您未使用記錄管理：</span><span class="sxs-lookup"><span data-stu-id="da293-147">If you are not using records management:</span></span>
        - <span data-ttu-id="da293-148">[解決方案]\*\*\*\*  >  [資訊控管]\*\*\*\*  >  [標籤原則]\*\*\*\* 索引標籤 > [自動套用標籤]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="da293-148">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="da293-149">沒有立即看到您的選項？</span><span class="sxs-lookup"><span data-stu-id="da293-149">Don't immediately see your option?</span></span> <span data-ttu-id="da293-150">先選取 [顯示全部]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da293-150">First select **Show all**.</span></span> 

2. <span data-ttu-id="da293-151">遵循精靈中的提示進行。</span><span class="sxs-lookup"><span data-stu-id="da293-151">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="da293-152">如需有關設定會自動套用保留標籤之條件的詳細資訊，請參閱此頁面上的[設定自動套用保留標籤的條件](#configuring-conditions-for-auto-apply-retention-labels)一節。</span><span class="sxs-lookup"><span data-stu-id="da293-152">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="da293-153">如需設定位置的相關資訊，請參閱此頁面上的下一節，[保留標籤和位置](#retention-labels-and-locations)。</span><span class="sxs-lookup"><span data-stu-id="da293-153">For information about configuring the locations, see the next section on this page, [Retention labels and locations](#retention-labels-and-locations).</span></span>

## <a name="retention-labels-and-locations"></a><span data-ttu-id="da293-154">保留標籤和位置</span><span class="sxs-lookup"><span data-stu-id="da293-154">Retention labels and locations</span></span>

<span data-ttu-id="da293-155">可以將不同類型的保留標籤發佈到不同的位置，視保留標籤的功能而定。</span><span class="sxs-lookup"><span data-stu-id="da293-155">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
|<span data-ttu-id="da293-156">**如果保留標籤是...**</span><span class="sxs-lookup"><span data-stu-id="da293-156">**If the retention label is…**</span></span>|<span data-ttu-id="da293-157">**則標籤原則可套用至...**</span><span class="sxs-lookup"><span data-stu-id="da293-157">**Then the label policy can be applied to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da293-158">發佈給使用者</span><span class="sxs-lookup"><span data-stu-id="da293-158">Published to end users</span></span>  <br/> |<span data-ttu-id="da293-159">Exchange、SharePoint、OneDrive、Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="da293-159">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
|<span data-ttu-id="da293-160">根據敏感資訊類型而自動套用</span><span class="sxs-lookup"><span data-stu-id="da293-160">Auto-applied based on sensitive information types</span></span>  <br/> |<span data-ttu-id="da293-161">Exchange (僅限所有信箱)、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="da293-161">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="da293-162">根據查詢而自動套用</span><span class="sxs-lookup"><span data-stu-id="da293-162">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="da293-163">Exchange、SharePoint、OneDrive、Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="da293-163">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
   
<span data-ttu-id="da293-164">在 Exchange 中，您只能在新傳送的郵件 (傳輸中的資料) 上自動套用保留標籤功能 (適用於查詢和敏感性資訊類型)，而非目前在信箱中的所有郵件 (待用資料)。</span><span class="sxs-lookup"><span data-stu-id="da293-164">In Exchange, auto-apply retention labels (for both queries and sensitive information types) are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="da293-165">此外，您只能在所有信箱中為敏感性資訊類型自動套用保留標籤功能，但無法選取特定信箱。</span><span class="sxs-lookup"><span data-stu-id="da293-165">Also, auto-apply retention labels for sensitive information types can apply only to all mailboxes; you can't select the specific mailboxes.</span></span>
  
<span data-ttu-id="da293-166">Exchange 公用資料夾和 Skype 不支援保留標籤。</span><span class="sxs-lookup"><span data-stu-id="da293-166">Exchange public folders and Skype do not support retention labels.</span></span>


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="da293-167">設定自動套用保留標籤的條件</span><span class="sxs-lookup"><span data-stu-id="da293-167">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="da293-168">您可以在內容包含以下資訊時，自動將保留標籤套用到內容：</span><span class="sxs-lookup"><span data-stu-id="da293-168">You can apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="da293-169">特定敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="da293-169">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="da293-170">符合您所建立查詢的特定關鍵字</span><span class="sxs-lookup"><span data-stu-id="da293-170">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="da293-171">可訓練分類器的符合項目</span><span class="sxs-lookup"><span data-stu-id="da293-171">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![自動套用標籤的選擇條件頁面](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="da293-173">將自動套用保留標籤套用到符合您設定之條件的所有內容，最多可能需要 7 天的時間。</span><span class="sxs-lookup"><span data-stu-id="da293-173">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="da293-174">自動將標籤套用至包含特定類型敏感資訊的內容</span><span class="sxs-lookup"><span data-stu-id="da293-174">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="da293-175">當您為敏感性資訊建立自動套用保留標籤時，系統會顯示與建立資料外洩防護 (DLP) 原則時相同的原則範本清單。</span><span class="sxs-lookup"><span data-stu-id="da293-175">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="da293-176">每個原則範本預設會尋找特定類型的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="da293-176">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="da293-177">例如本文顯示的範本會尋找美國 ITIN、SSN 和護照號碼。</span><span class="sxs-lookup"><span data-stu-id="da293-177">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="da293-178">若要深入了解 DLP，請參閱[資料外洩防護原則概觀](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="da293-178">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![敏感資訊類型的原則範本](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="da293-p112">選取原則範本後，可以新增或移除任何類型的敏感資訊，且可以變更例項計數和比對精確度。此處所示的範例中，只有符合以下條件時，才會自動套用保留標籤：</span><span class="sxs-lookup"><span data-stu-id="da293-p112">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="da293-p113">內容包含 1 到 9 個下列三種敏感資訊類型。您可以刪除 \*\*max \*\* (上限) 值，條件就會變成 **any** (任何)。</span><span class="sxs-lookup"><span data-stu-id="da293-p113">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="da293-p114">偵測到的敏感資訊類型的比對精確度 (或信賴等級) 下限為 75。許多敏感資訊類型會定義多個模式，模式的比對精確度愈高，便需要尋找愈多證據 (例如關鍵字、日期、地址)，而較低比對精確度的模式則需要較少的證據。簡單來說，比對精確度的 **min** (下限) 愈低，就越容易找到與條件相符的內容。</span><span class="sxs-lookup"><span data-stu-id="da293-p114">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="da293-187">如需這些選項的詳細資訊，請參閱[調整規則，讓規則更容易或更難相符](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="da293-187">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![用於識別機密資訊類型的選項](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="da293-189">自動將標籤套用至包含關鍵字或可搜尋屬性的內容</span><span class="sxs-lookup"><span data-stu-id="da293-189">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="da293-p115">您可以自動將標籤套用至符合特定條件的內容。現在可用的條件支援將標籤套用至包含特定字詞、片語或可搜尋屬性的值。您可以使用 AND、OR、NOT 等搜尋運算子來精簡查詢。</span><span class="sxs-lookup"><span data-stu-id="da293-p115">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="da293-193">如需查詢語法的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="da293-193">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="da293-194">關鍵字查詢語言 (KQL) 語法參考</span><span class="sxs-lookup"><span data-stu-id="da293-194">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="da293-p116">查詢式標籤使用搜尋索引來識別內容。如需有效可搜尋屬性的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="da293-p116">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="da293-197">內容搜尋的關鍵字查詢與搜尋條件</span><span class="sxs-lookup"><span data-stu-id="da293-197">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="da293-198">SharePoint 伺服器中的編目及受控屬性概觀</span><span class="sxs-lookup"><span data-stu-id="da293-198">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="da293-199">範例查詢：</span><span class="sxs-lookup"><span data-stu-id="da293-199">Examples queries:</span></span>

- <span data-ttu-id="da293-200">Exchange</span><span class="sxs-lookup"><span data-stu-id="da293-200">Exchange</span></span>
    - <span data-ttu-id="da293-201">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="da293-201">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="da293-202">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="da293-202">recipients:garthf</span></span><!--nolink--><span data-ttu-id="da293-203">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="da293-203">@contoso.com</span></span>
- <span data-ttu-id="da293-204">SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="da293-204">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="da293-205">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="da293-205">contenttype:contract</span></span>
    - <span data-ttu-id="da293-206">site:https</span><span class="sxs-lookup"><span data-stu-id="da293-206">site:https</span></span><!--nolink--><span data-ttu-id="da293-207">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="da293-207">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![查詢編輯器](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="da293-209">使用可訓練分類器自動將標籤套用至內容</span><span class="sxs-lookup"><span data-stu-id="da293-209">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="da293-210">選擇用於可訓練分類器的選項時，可以選取其中一個內建分類器或自訂分類器。</span><span class="sxs-lookup"><span data-stu-id="da293-210">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="da293-211">內建分類器包括 [履歷]\*\*\*\*、[原始程式碼]\*\*\*\*、[針對性騷擾]\*\*\*\*、[粗話]\*\*\*\* 和 [威脅]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="da293-211">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![選擇可訓練分類器](../media/retention-label-classifers.png)

<span data-ttu-id="da293-213">若要使用此選項自動套用標籤，SharePoint Online 網站和信箱必須有至少 10 MB 的資料。</span><span class="sxs-lookup"><span data-stu-id="da293-213">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="da293-214">如需有關可訓練分類器的詳細資訊，請參閱[開始使用可訓練分類器 (預覽)](classifier-getting-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="da293-214">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="da293-215">如需組態範例，請參閱[如何準備及使用內建分類器](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)。</span><span class="sxs-lookup"><span data-stu-id="da293-215">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="da293-216">保留標籤要多久才會生效</span><span class="sxs-lookup"><span data-stu-id="da293-216">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="da293-217">當您發佈或自動套用保留標籤時，標籤不會立即生效：</span><span class="sxs-lookup"><span data-stu-id="da293-217">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="da293-218">首先，標籤原則必須先將系統管理中心與原則中的位置同步。</span><span class="sxs-lookup"><span data-stu-id="da293-218">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="da293-219">接著，位置可能會需要一些時間，將已發佈的保留標籤提供給使用者，或是將標籤自動套用到內容。</span><span class="sxs-lookup"><span data-stu-id="da293-219">Then the location might require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="da293-220">實際所需的時間取決於保留標籤的位置和類型。</span><span class="sxs-lookup"><span data-stu-id="da293-220">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="da293-221">已發佈的保留標籤</span><span class="sxs-lookup"><span data-stu-id="da293-221">Published retention labels</span></span>

<span data-ttu-id="da293-p119">如果您將保留標籤發佈到 SharePoint 或 OneDrive，需要一天的時間讓這些保留標籤向使用者顯示。此外，如果您將保留標籤發佈到 Exchange，可能需要 7 天來向使用者顯示這些保留標籤，且信箱至少必須包含 10 MB 的資料。</span><span class="sxs-lookup"><span data-stu-id="da293-p119">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![手動標籤生效的圖](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="da293-225">自動套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="da293-225">Auto-apply retention labels</span></span>

<span data-ttu-id="da293-226">如果您將保留標籤自動套用至符合特定條件的內容，保留標籤套用至符合條件的所有現有內容可能需要 7 天。</span><span class="sxs-lookup"><span data-stu-id="da293-226">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自動標籤生效時的圖表](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="da293-228">如何檢查發佈至 Exchange 之保留標籤的狀態</span><span class="sxs-lookup"><span data-stu-id="da293-228">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="da293-p120">在 Exchange Online 中，是透過每 7 天執行一次的程序，將保留標籤提供給使用者。您可以使用 Powershell 查看此程序上次執行的時間，依此判斷下一次執行時間。</span><span class="sxs-lookup"><span data-stu-id="da293-p120">In Exchange Online, retention labels are made available to end users by a process that runs every seven days. By using Powershell, you can see when this process last ran and thus determine when it will run again.</span></span>
  
1. <span data-ttu-id="da293-231">[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773)。</span><span class="sxs-lookup"><span data-stu-id="da293-231">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="da293-232">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="da293-232">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

<span data-ttu-id="da293-233">結果：`ELCLastSuccessTimeStamp` (UTC) 屬性會顯示系統上次處理您信箱的時間。</span><span class="sxs-lookup"><span data-stu-id="da293-233">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="da293-234">如果系統在您建立原則後都還未處理信箱，標籤就無法顯示。</span><span class="sxs-lookup"><span data-stu-id="da293-234">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="da293-235">若要強制處理信箱，請執行 `Start-ManagedFolderAssistant -Identity <user>`。</span><span class="sxs-lookup"><span data-stu-id="da293-235">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="da293-236">如果標籤沒有出現在 Outlook 網頁版中，而您認為應該要出現，請務必清除瀏覽器中的快取 (CTRL + F5)。</span><span class="sxs-lookup"><span data-stu-id="da293-236">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="da293-237">更新保留標籤及其原則</span><span class="sxs-lookup"><span data-stu-id="da293-237">Updating retention labels and their policies</span></span>

<span data-ttu-id="da293-238">如果您編輯保留標籤、保留標籤原則或自動套用原則，且保留標籤已套用至內容，除了新標示的內容以外，您更新的設定會自動套用到此內容。</span><span class="sxs-lookup"><span data-stu-id="da293-238">If you edit a retention label, retention label policy, or auto-apply policy and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly labeled.</span></span>

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a><span data-ttu-id="da293-239">尋找保留標籤的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="da293-239">Find the PowerShell cmdlets for retention labels</span></span>

<span data-ttu-id="da293-240">若要使用保留標籤 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="da293-240">To use the retention label cmdlets:</span></span>
  
1. [<span data-ttu-id="da293-241">連接到 Office 365 安全性與合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="da293-241">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="da293-242">使用這些 Office 365 安全性與合規性中心 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="da293-242">Use these Office 365 Security & Compliance Center cmdlets:</span></span>
    
    - [<span data-ttu-id="da293-243">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="da293-243">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetag)
    
    - [<span data-ttu-id="da293-244">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="da293-244">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-compliancetag)
    
    - [<span data-ttu-id="da293-245">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="da293-245">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-compliancetag)
    
    - [<span data-ttu-id="da293-246">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="da293-246">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-compliancetag)
    
    - [<span data-ttu-id="da293-247">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="da293-247">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/enable-compliancetagstorage)
    
    - [<span data-ttu-id="da293-248">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="da293-248">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetagstorage)
    
    - [<span data-ttu-id="da293-249">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="da293-249">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)
    
    - [<span data-ttu-id="da293-250">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="da293-250">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)
    
    - [<span data-ttu-id="da293-251">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="da293-251">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)
    
    - [<span data-ttu-id="da293-252">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="da293-252">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)
    
    - [<span data-ttu-id="da293-253">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="da293-253">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)
    
    - [<span data-ttu-id="da293-254">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="da293-254">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)
    
    - [<span data-ttu-id="da293-255">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="da293-255">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)
    
    - [<span data-ttu-id="da293-256">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="da293-256">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)
