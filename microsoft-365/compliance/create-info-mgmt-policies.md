---
title: 建立及套用資訊管理原則
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何設定資訊管理原則，以控制資訊的保留時間，以及追蹤使用資訊的人員。
ms.openlocfilehash: 2519f039e7495d01a828aee564ce1a6caf41342d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817992"
---
# <a name="create-and-apply-information-management-policies"></a><span data-ttu-id="0d6ea-103">建立及套用資訊管理原則</span><span class="sxs-lookup"><span data-stu-id="0d6ea-103">Create and apply information management policies</span></span>

<span data-ttu-id="0d6ea-104">資訊管理原則可讓您的組織控制保留內容的時間長短、審核人員對內容所做的動作，以及將條碼或標籤新增至檔。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-104">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="0d6ea-105">原則可協助強制遵從法律和政府法規或內部的商務程式。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-105">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="0d6ea-106">您可以以系統管理員的身分設定原則，以控制追蹤檔的方式，以及保留檔的時間長度。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-106">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>
  
<span data-ttu-id="0d6ea-107">您可以建立資訊管理原則，可在網站階層中的三個不同位置，從最廣泛到最窄的位置：</span><span class="sxs-lookup"><span data-stu-id="0d6ea-107">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
  
- <span data-ttu-id="0d6ea-108">建立原則，以用於網站集合中的多個內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-108">Create a policy to use on multiple content types within a site collection.</span></span>
    
- <span data-ttu-id="0d6ea-109">建立網站內容類型的原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-109">Create a policy for a site content type.</span></span>
    
- <span data-ttu-id="0d6ea-110">建立清單或文件庫的原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-110">Create a policy for a list or library.</span></span>
    
<span data-ttu-id="0d6ea-111">如需詳細資訊，請參閱[資訊管理原則簡介](intro-to-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-111">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a><span data-ttu-id="0d6ea-112">在網站集合內為多個內容類型建立原則</span><span class="sxs-lookup"><span data-stu-id="0d6ea-112">Create a policy for multiple content types within a site collection</span></span>
<span data-ttu-id="0d6ea-113"><a name="__toc261001590"> </a></span><span class="sxs-lookup"><span data-stu-id="0d6ea-113"><a name="__toc261001590"> </a></span></span>

<span data-ttu-id="0d6ea-114">為了確保將資訊原則套用至網站集合中的特定類型的所有檔，請考慮在網站集合層級建立原則，然後再將原則套用至內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-114">To ensure that an information policy is applied to all documents of a certain type within a site collection, consider creating the policy at the site collection level and then later apply the policy to content types.</span></span> <span data-ttu-id="0d6ea-115">這些稱為網站集合原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-115">These are referred to as site collection policies.</span></span> 
  
1. <span data-ttu-id="0d6ea-116">在 [網站集合首頁設定] 的 \> **Settings** ![ 標題列上 SharePoint 2016 設定] 按鈕。](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="0d6ea-116">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="0d6ea-117">\> [網站設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-117">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="0d6ea-118">在 SharePoint 群組連線的網站中，按一下 [**設定**]，按一下 [**網站內容**]，然後按一下 [**網站設定**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-118">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="0d6ea-119">在 [網站設定] 頁面的 [**網站集合管理** \> **內容類型原則範本**] 底下。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-119">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![網站設定頁面上的內容類型原則範本連結](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="0d6ea-121">在 [原則] 頁面上 \> **建立**。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-121">On the Policies page \> **Create**.</span></span> 
    
4. <span data-ttu-id="0d6ea-122">輸入原則的名稱和描述，然後撰寫簡短的原則聲明，以向使用者說明原則的用途。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-122">Enter a name and description for the policy, and then write a brief policy statement that explains to users what the policy is for.</span></span>
    
5. <span data-ttu-id="0d6ea-123">若要瞭解如何設定要與原則建立關聯的功能，請參閱下一節建立網站內容類型的原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-123">See the next section on creating policies for a site content type to learn how to set up the features you want to associate with the policy.</span></span> 
    
6. <span data-ttu-id="0d6ea-124">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-124">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-site-content-type"></a><span data-ttu-id="0d6ea-125">建立網站內容類型的原則</span><span class="sxs-lookup"><span data-stu-id="0d6ea-125">Create a policy for a site content type</span></span>
<span data-ttu-id="0d6ea-126"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="0d6ea-126"><a name="__create_a_policy"> </a></span></span>

<span data-ttu-id="0d6ea-127">新增資訊管理原則至內容類型，可讓原則功能與多個清單或文件庫輕鬆建立關聯。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-127">Adding an information management policy to a content type makes it easy to associate policy features with multiple lists or libraries.</span></span> <span data-ttu-id="0d6ea-128">您可以選擇新增現有的資訊管理原則至內容類型，或建立個別內容類型特有的唯一原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-128">You can choose to add an existing information management policy to a content type or create a unique policy specific to an individual content type.</span></span>
  
 <span data-ttu-id="0d6ea-129">您也可以新增資訊管理原則至清單特有的內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-129">You can also add an information management policy to a content type that is specific to lists.</span></span> <span data-ttu-id="0d6ea-130">這只會對使用內容類型的清單中的專案套用原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-130">This has the effect of applying the policy only to items in that list that are using the content type.</span></span> 
  
1. <span data-ttu-id="0d6ea-131">在 [網站集合首頁設定] 的 \> **Settings** ![ 標題列上 SharePoint 2016 設定] 按鈕。](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="0d6ea-131">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="0d6ea-132">\> [網站設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-132">\> **Site Settings**.</span></span>
    
    <span data-ttu-id="0d6ea-133">在 SharePoint 群組連線的網站中，按一下 [**設定**]，按一下 [**網站內容**]，然後按一下 [**網站設定**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-133">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="0d6ea-134">在 [網站設定] 頁面的 [**網頁設計工具庫** \> **網站內容類型**] 底下。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-134">On the Site Settings page, under **Web Designer Galleries** \> **Site content types**.</span></span>
  
![網站設定頁面上的網站內容類型連結](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. <span data-ttu-id="0d6ea-136">在 [網站內容類型設定] 頁面上，選取您要新增原則的內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-136">On the Site Content Type Settings page, select the content type that you want to add a policy to.</span></span>
    
4. <span data-ttu-id="0d6ea-137">在 [網站內容類型] 頁面上的 [**設定** \> **資訊管理原則設定**] 底下。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-137">On the Site Content Type page, under **Settings** \> **Information management policy settings**.</span></span>
    
5. <span data-ttu-id="0d6ea-138">在 [編輯原則] 頁面上，輸入原則的名稱和描述，然後撰寫簡短描述，以向使用者說明原則的用途。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-138">On the Edit Policy page, enter a name and description for the policy, and then write a brief description that explains to users what the policy is for.</span></span>
    
6. <span data-ttu-id="0d6ea-139">在下一節中，選取您要新增至資訊管理原則的個別原則功能。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-139">In the next sections, select the individual policy features that you want to add to your information management policy.</span></span> 
  
![內容原則的類型](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. <span data-ttu-id="0d6ea-141">若要指定受此原則制約之檔及專案的保留期間，請選擇 [**啟用保留**]，然後指定要在專案到期時執行的保留期間和動作。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-141">To specify a retention period for documents and items that are subject to this policy, choose **Enable Retention**, and then specify the retention period and the actions that you want to occur when the items expire.</span></span>
    
    <span data-ttu-id="0d6ea-142">指定保留期間</span><span class="sxs-lookup"><span data-stu-id="0d6ea-142">To specify a retention period</span></span>
    
||||||<span data-ttu-id="0d6ea-143">**1.**</span><span class="sxs-lookup"><span data-stu-id="0d6ea-143">**1.**</span></span>|<span data-ttu-id="0d6ea-144">\* \* 選擇 [新增記錄的保留階段] \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="0d6ea-144">\*\*Choose \*\*Add a retention stage for records…\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="0d6ea-145">2.</span><span class="sxs-lookup"><span data-stu-id="0d6ea-145">2.</span></span>  <br/> | <span data-ttu-id="0d6ea-146">選取 [保留期間] 選項，以指定檔或專案設為 [到期] 的時間。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-146">Select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="0d6ea-147">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="0d6ea-147">Do one of the following:</span></span>  <br/>  <span data-ttu-id="0d6ea-148">若要設定以日期屬性為基礎的到期日，在 [**事件** \> **此階段是以專案的日期] 屬性為基礎**，然後選取檔或專案動作（例如 [已建立] 或 [修改時間]）及此動作之後的時間增量（例如，當您想要專案到期時的天數、月數或年數）。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-148">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>  <br/>  <span data-ttu-id="0d6ea-149">若要使用自訂保留公式來判斷到期，請選擇 [**由此伺服器上安裝的自訂保留公式來設定**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-149">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>  <br/> <span data-ttu-id="0d6ea-150">> [!NOTE]> 只有當您的系統管理員已設定自訂公式時，才可使用此選項。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-150">> [!NOTE]>  This option is only available if a custom formula has been set up by your administrator.</span></span>           |
||||||<span data-ttu-id="0d6ea-151">3.</span><span class="sxs-lookup"><span data-stu-id="0d6ea-151">3.</span></span>  <br/> |<span data-ttu-id="0d6ea-152">只有在您為已有工作流程相關聯的清單、文件庫或內容類型定義原則時，才可以使用 [**開始工作流程**] 選項。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-152">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="0d6ea-153">然後，您就可以選擇要選擇的工作流程。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-153">You will then be given a choice of workflows to choose from.</span></span>  <br/> |
||||||<span data-ttu-id="0d6ea-154">4.</span><span class="sxs-lookup"><span data-stu-id="0d6ea-154">4.</span></span>  <br/> |<span data-ttu-id="0d6ea-155">在 [**迴圈**] 區段中，選取 [**重複此階段的動作 ...** ]。，然後輸入您想要動作執行的頻率。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-155">In the **Recurrence** section, select **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>  <br/> <span data-ttu-id="0d6ea-156">> [!NOTE]> 只有當您選取的動作可重複時，才可使用此選項。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-156">> [!NOTE]>  This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="0d6ea-157">例如，您無法為**永久刪除**動作設定迴圈。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-157">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>           |
||||||<span data-ttu-id="0d6ea-158">5.</span><span class="sxs-lookup"><span data-stu-id="0d6ea-158">5.</span></span>  <br/> |<span data-ttu-id="0d6ea-159">選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-159">Chose **OK**.</span></span>  <br/> |
   
1. <span data-ttu-id="0d6ea-160">若要對受此原則制約的檔和專案啟用審核，請選擇 [**啟用審核**]，然後指定您要審核的事件。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-160">To enable auditing for the documents and items that are subject to this policy, choose **Enable Auditing**, and then specify the events you want to audit.</span></span>
    
    <span data-ttu-id="0d6ea-161">啟用審核</span><span class="sxs-lookup"><span data-stu-id="0d6ea-161">To enable auditing</span></span>
    
||||||<span data-ttu-id="0d6ea-162">1. \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="0d6ea-162">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="0d6ea-163">在 [編輯原則] 頁面的 [ **under** **審計** **\>** **啟用審核**\* \*] 底下，然後選取您要保留審計追蹤之事件旁的核取方塊。 \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="0d6ea-163">\*\*\*\*On the Edit Policy page,\*\* **under** **Auditing** **\>** **Enable auditing** \*\*, and then select the check boxes next to the events you want to keep an audit trail for.\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="0d6ea-164">**2.**</span><span class="sxs-lookup"><span data-stu-id="0d6ea-164">**2.**</span></span> <br/> |<span data-ttu-id="0d6ea-165">**若要提示使用者在檔中插入這些條碼，請\*\*\*\*選擇 [** **在儲存或列印前插入條碼**] **。**</span><span class="sxs-lookup"><span data-stu-id="0d6ea-165">**To prompt users to insert these barcodes into documents,** **choose** **Prompt users to insert a barcode before saving or printing** **.**</span></span> <br/> |
||||||<span data-ttu-id="0d6ea-166">**3.**</span><span class="sxs-lookup"><span data-stu-id="0d6ea-166">**3.**</span></span> <br/> |<span data-ttu-id="0d6ea-167">**選擇** **[確定]** \* \*，將審核功能套用至原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-167">**Choose** **OK** \*\* to apply the auditing feature to the policy.</span></span> ** <br/> |
|||||||<span data-ttu-id="0d6ea-168">「審核原則」功能可讓組織建立及分析檔的審計追蹤，以及列出專案（例如工作清單、問題清單、討論群組和行事曆）。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-168">The Auditing Policy feature enables organizations to create and analyze audit trails for documents and to list items such as task lists, issues lists, discussion groups, and calendars.</span></span> <span data-ttu-id="0d6ea-169">這個原則功能提供一個審核記錄檔，可記錄事件，例如，查看、編輯或刪除內容。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-169">This policy feature provides an audit log that records events, such as when content is viewed, edited, or deleted.</span></span>  <br/> |
|||||||<span data-ttu-id="0d6ea-170">在資訊管理原則中啟用審核時，系統管理員可以在使用 Microsoft Excel 的原則使用狀況報告中查看審核資料，並匯總目前的使用量。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-170">When auditing is enabled as part of an information management policy, administrators can view the audit data in policy usage reports that are based in Microsoft Excel and that summarize current usage.</span></span> <span data-ttu-id="0d6ea-171">系統管理員可以使用這些報告來決定組織中資訊的使用方式。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-171">Administrators can use these reports to determine how information is being used within the organization.</span></span> <span data-ttu-id="0d6ea-172">這些報告也可協助組織驗證及記錄其法規遵從性，或調查可能的關注事項。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-172">These reports can also help organizations to verify and document their regulatory compliance or to investigate potential concerns.</span></span>  <br/> |
|||||||<span data-ttu-id="0d6ea-173">審核記錄會記錄下列資訊：事件名稱、事件的日期和時間，以及執行動作之使用者的系統名稱。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-173">The audit log records the following information: event name, date and time of the event, and system name of the user who performed the action.</span></span>  <br/> |
   
1. <span data-ttu-id="0d6ea-174">在原則中啟用條碼時，會將其新增至檔案屬性，並顯示在套用條碼的檔標頭區域中。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-174">When barcodes are enabled as part of a policy, they are added to document properties and displayed in the header area of the document to which the barcode is applied.</span></span> <span data-ttu-id="0d6ea-175">如同標籤，也可以手動移除檔中的條碼。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-175">Like labels, barcodes can also be manually removed from a document.</span></span> <span data-ttu-id="0d6ea-176">您可以指定在列印或儲存專案時，是否應提示使用者加入條碼，或者是否應使用 2010 Office 發行版本程式中的 [**插入**] 索引標籤手動插入條碼。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-176">You can specify whether users should be prompted to include the barcode when printing or saving an item or if the barcode should be inserted manually using the **Insert** tab in 2010 Office release programs.</span></span> 
    
    <span data-ttu-id="0d6ea-177">啟用條碼</span><span class="sxs-lookup"><span data-stu-id="0d6ea-177">To enable barcodes</span></span>
    
||||||<span data-ttu-id="0d6ea-178">1. \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="0d6ea-178">\*\*\*\*1.\*\*\*\*</span></span>|<span data-ttu-id="0d6ea-179">**在 [編輯原則] 頁面的 [**條碼\*\* \> **啟用條碼**] 底下。\*\*</span><span class="sxs-lookup"><span data-stu-id="0d6ea-179">**On the Edit Policy page, under **Barcodes**\> **Enable Barcodes**.**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="0d6ea-180">**2.**</span><span class="sxs-lookup"><span data-stu-id="0d6ea-180">**2.**</span></span> <br/> |<span data-ttu-id="0d6ea-181">若要提示使用者在檔中插入這些條碼，請選擇 [**在儲存或列印前插入條碼**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-181">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>  <br/> |
||||||<span data-ttu-id="0d6ea-182">**3.**</span><span class="sxs-lookup"><span data-stu-id="0d6ea-182">**3.**</span></span> <br/> |<span data-ttu-id="0d6ea-183">選擇 **[確定]** ，將條碼功能套用至原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-183">Choose **OK** to apply the barcode feature to the policy.</span></span>  <br/> |
|||||||
 <span data-ttu-id="0d6ea-184">條碼原則會產生程式碼39標準條碼。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-184">The barcode policy generates Code 39 standard barcodes.</span></span> <span data-ttu-id="0d6ea-185">每個條碼影像都會在條碼符號的下方包含文字，表示條碼值。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-185">Each barcode image includes text below the barcode symbol that represents the barcode value.</span></span> <span data-ttu-id="0d6ea-186">這可讓您即使在無法使用掃描硬體時，也會使用條碼資料。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-186">This enables the barcode data to be used even when scanning hardware is not available.</span></span> <span data-ttu-id="0d6ea-187">使用者可以在搜尋方塊中手動輸入條碼號碼，以在網站上尋找專案。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-187">Users can manually type the barcode number into the search box to locate the item on a site.</span></span>  <br/> |
   
1. <span data-ttu-id="0d6ea-188">若要要求受此原則制約的檔具有標籤，請選擇 [**啟用標籤**]，然後指定您要用於標籤的設定。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-188">To require that documents that are subject to this policy have labels, choose **Enable Labels**, and then specify the settings that you want for the labels.</span></span>
    
    <span data-ttu-id="0d6ea-189">啟用標籤</span><span class="sxs-lookup"><span data-stu-id="0d6ea-189">To enable labels</span></span>
    
||||||<span data-ttu-id="0d6ea-190">**1.**</span><span class="sxs-lookup"><span data-stu-id="0d6ea-190">**1.**</span></span>|<span data-ttu-id="0d6ea-191">\* \* 若要要求使用者新增標籤至檔，請選擇 [**在儲存或列印前先插入標籤**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-191">\*\*To require users to add a label to a document, choose **Prompt users to insert a label before saving or printing**.</span></span>  <br/> <span data-ttu-id="0d6ea-192">> [!NOTE]> 如果您想要標籤是選用的，請勿選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-192">> [!NOTE]>  If you want labels to be optional, do not select this check box.</span></span>        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||<span data-ttu-id="0d6ea-193">2.</span><span class="sxs-lookup"><span data-stu-id="0d6ea-193">2.</span></span>  <br/> |<span data-ttu-id="0d6ea-194">若要鎖定標籤，使其在插入之後無法變更，請選擇 [在新增標籤**後禁止變更**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-194">To lock a label so that it cannot be changed after it has been inserted, choose **Prevent changes to labels after they are added**.</span></span>  <br/>  <span data-ttu-id="0d6ea-195">當標籤文字插入用戶端應用程式（例如 Word、Excel 或 PowerPoint）中的專案時，此設定會防止標籤文字更新。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-195">This setting prevents the label text from updating once the label has been inserted into an item within a client application such as Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="0d6ea-196">如果您想要在更新此檔或專案的屬性時更新標籤，請勿選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-196">If you want the label to be updated when the properties for this document or item are updated, do not select this check box.</span></span>  <br/> |
||||||<span data-ttu-id="0d6ea-197">3.</span><span class="sxs-lookup"><span data-stu-id="0d6ea-197">3.</span></span>  <br/> |<span data-ttu-id="0d6ea-198">在 [標籤格式] 方塊中，輸入您想要顯示標籤的文字。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-198">In the Label format box, enter the text for the label as you want it to be displayed.</span></span> <span data-ttu-id="0d6ea-199">標籤最多可以包含10欄參照，每個都最多可包含255個字元。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-199">Labels can contain up to 10 column references, each of which can be up to 255 characters long.</span></span> <span data-ttu-id="0d6ea-200">若要建立標籤的格式，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="0d6ea-200">To create the format for your label, do the following:</span></span>  <br/> <span data-ttu-id="0d6ea-201">以您想要顯示的順序，輸入要包含在標籤中的欄名稱。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-201">Type the names of the columns that you want to include in the label in the order in which you want them to appear.</span></span> <span data-ttu-id="0d6ea-202">請以大括弧（）括住欄名稱 {} ，如 [編輯原則] 頁面上的範例所示。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-202">Enclose the column names in curly brackets ({}), as shown in the example on the Edit Policy page.</span></span>  <br/> <span data-ttu-id="0d6ea-203">輸入文字來識別方括弧外的欄，如 [編輯原則] 頁面上範例中所示。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-203">Type words to identify the columns outside the brackets, as shown in the example on the Edit Policy page.</span></span>  <br/> |
||||||<span data-ttu-id="0d6ea-204">4.</span><span class="sxs-lookup"><span data-stu-id="0d6ea-204">4.</span></span>  <br/> |<span data-ttu-id="0d6ea-205">若要新增分行符號，請在您想要出現分行符號的位置輸入**\n** 。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-205">To add a line break, enter **\n** where you want the line break to appear.</span></span>  <br/> |
||||||<span data-ttu-id="0d6ea-206">5.</span><span class="sxs-lookup"><span data-stu-id="0d6ea-206">5.</span></span>  <br/> |<span data-ttu-id="0d6ea-207">選取您想要的字型大小和樣式，並指定是否要在檔中左對齊、居中或靠右放置標籤。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-207">Select the font size and style that you want, and specify whether you want the label positioned left, center, or right within the document.</span></span>  <br/>  <span data-ttu-id="0d6ea-208">選取使用者電腦上可用的字型和樣式。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-208">Select a font and style that are available on the users' computers.</span></span> <span data-ttu-id="0d6ea-209">字型的大小會影響可以在標籤上顯示多少文字。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-209">The size of the font affects how much text can be displayed on the label.</span></span>  <br/> |
||||||<span data-ttu-id="0d6ea-210">6.</span><span class="sxs-lookup"><span data-stu-id="0d6ea-210">6.</span></span>  <br/> |<span data-ttu-id="0d6ea-211">輸入標籤的高度和寬度。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-211">Enter the height and width of the label.</span></span> <span data-ttu-id="0d6ea-212">標籤高度介於 .25 英寸到20英寸之間，標籤寬度可以介於 .25 英寸到20英寸之間。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-212">Label height can range from .25 inches to 20 inches, and label width can range from .25 inches to 20 inches.</span></span> <span data-ttu-id="0d6ea-213">標籤文字在標籤影像內一定會垂直置中對齊。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-213">Label text is always vertically centered within the label image.</span></span>  <br/> |
||||||<span data-ttu-id="0d6ea-214">7.</span><span class="sxs-lookup"><span data-stu-id="0d6ea-214">7.</span></span>  <br/> |<span data-ttu-id="0d6ea-215">選擇 **[** 重新整理] 以預覽標籤內容。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-215">Choose **Refresh** to preview the label content.</span></span>  <br/> |
   
1. <span data-ttu-id="0d6ea-216">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-216">Choose **OK**.</span></span>
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a><span data-ttu-id="0d6ea-217">建立清單、文件庫或資料夾的原則 (位置保留原則)</span><span class="sxs-lookup"><span data-stu-id="0d6ea-217">Create a policy for a list, library or folder (location-based retention policy)</span></span>
<span data-ttu-id="0d6ea-218"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="0d6ea-218"><a name="__create_a_policy"> </a></span></span>

<span data-ttu-id="0d6ea-219">您可以定義僅套用至特定清單、文件庫或資料夾的保留原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-219">You can define a retention policy that applies only to a specific list, library or folder.</span></span> <span data-ttu-id="0d6ea-220">不過，如果您以這種方式建立保留原則，便無法在其他清單、文件庫、資料夾或網站上重複使用此原則，您也無法將網站集合原則套用至根據位置原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-220">However, if you create a retention policy this way, you cannot reuse this policy on other lists, libraries, folders or sites, and you cannot apply a site collection policy to a location based policy.</span></span>
  
<span data-ttu-id="0d6ea-221">如果您想要將單一保留原則套用至單一位置的所有類型的內容，您很可能會想要使用以位置為基礎的保留。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-221">If you want to apply a single retention policy to all types of content in a single location, you will most likely want to use location-based retention.</span></span> <span data-ttu-id="0d6ea-222">在大多數其他情況下，您會想要驗證是否已指定所有內容類型的保留原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-222">In most other cases, you will want to verify that a retention policy is specified for all content types.</span></span>
  
 <span data-ttu-id="0d6ea-223">每個子資料夾都會繼承其父系的保留原則，除非您選擇中斷繼承，並在子層級定義新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-223">Each subfolder inherits the retention policy of its parent, unless you choose to break inheritance and define a new retention policy at the child level.</span></span> 
  
<span data-ttu-id="0d6ea-224">如果您想要定義「保留至清單或文件庫」以外的資訊管理原則，您必須為與該清單或文件庫相關聯的每個個別清單內容類型定義資訊管理原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-224">If you want to define an information management policy other than retention to a list or library, you need to define an information management policy for each individual list content type associated with that list or library.</span></span>
  
 <span data-ttu-id="0d6ea-225">如果您決定從內容類型切換至清單或文件庫的位置型原則，則只會使用保留原則做為以位置為基礎的原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-225">If at any point you decide to switch from content type to location-based policies for a list or library, only the retention policy will be used as the location-based policy.</span></span> <span data-ttu-id="0d6ea-226">所有其他管理原則（審計、條碼和條碼）都會從相關聯的內容類型繼承。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-226">All other management policies (audits, barcodes, and barcodes) will be inherited from the associated content types.</span></span> 
  
 <span data-ttu-id="0d6ea-227">您可以透過停用文件庫和資料夾型保留功能，停用網站集合的位置原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-227">Location based policies can be disabled for a site collection by deactivating the Library and Folder Based Retention feature.</span></span> <span data-ttu-id="0d6ea-228">這可讓網站集合管理員確保其內容類型原則不會被清單管理員的位置原則所取代。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-228">This enables site collection administrators to ensure that their content type policies are not overridden by a list administrator's location based policies.</span></span> 
  
<span data-ttu-id="0d6ea-229">您至少需要「管理清單」許可權，才可變更清單或文件庫的資訊管理原則設定。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-229">You need at least the Manage Lists permission to change the information management policy settings for a list or library.</span></span>
  
1. <span data-ttu-id="0d6ea-230">流覽至您要為其指定資訊管理原則的清單或文件庫。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-230">Navigate to the list or library for which you want to specify an information management policy.</span></span> 
    
2. <span data-ttu-id="0d6ea-231">在功能區上，選擇 [連結**庫**] 或 [**清單**] 索引標籤 \> **庫設定**或**清單設定**。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-231">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="0d6ea-232">在 SharePoint Online 中，按一下 [**設定**]，然後按一下 [**清單設定**] 或 [文檔**庫設定**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-232">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="0d6ea-233">在 [**許可權與管理** \> **資訊管理原則設定**] 底下。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-233">Under **Permissions and Management**\> **Information management policy settings**.</span></span>
  
![文件庫設定頁面上的資訊管理原則連結](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="0d6ea-235">在 [資訊管理原則設定] 頁面上，確定清單或文件庫的保留來源已設定為 [文件庫和資料夾]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-235">On the Information Management Policy Settings page, make sure that the source of retention for the list or library is set to Library and Folders.</span></span> 
  
<span data-ttu-id="0d6ea-236">如果**內容類型**顯示為來源，請按一下 [**變更來源**]，然後按一下 [文檔**庫和資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-236">If **Content Type** appears as the source, click **Change Source**, and then click **Library and Folders**.</span></span> <span data-ttu-id="0d6ea-237">系統會提醒您會忽略內容類型保留原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-237">You are alerted that content type retention policies will be ignored.</span></span> <span data-ttu-id="0d6ea-238">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-238">Choose **OK**.</span></span> 
    
5. <span data-ttu-id="0d6ea-239">在 [編輯原則] 頁面的 [以文檔**庫為基礎的保留排程**] 下，輸入您建立之原則的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-239">On the Edit Policy page, under **Library Based Retention Schedule**, enter a brief description for the policy you are creating.</span></span> 
    
6. <span data-ttu-id="0d6ea-240">選擇 [**新增保留階段 ...** ]</span><span class="sxs-lookup"><span data-stu-id="0d6ea-240">Choose **Add a retention stage…**</span></span>
    
     <span data-ttu-id="0d6ea-241">請注意，在 [記錄] 底下，您可以選取 [定義記錄的不同保留階段] 選項，以定義記錄的不同保留原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-241">Note that under Records, you can choose to define different retention policies for records by selecting the Define different retention stages for records option.</span></span> 
    
7. <span data-ttu-id="0d6ea-242">在 [階段內容] 對話方塊中，選取 [保留期間] 選項，以指定檔或專案設為 [到期] 的時間。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-242">In the Stage properties dialog, select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="0d6ea-243">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="0d6ea-243">Do one of the following:</span></span>
    
  - <span data-ttu-id="0d6ea-244">若要設定以日期屬性為基礎的到期日，在 [**事件** \> **此階段是以專案的日期] 屬性為基礎**，然後選取檔或專案動作（例如 [已建立] 或 [修改時間]）及此動作之後的時間增量（例如，當您想要專案到期時的天數、月數或年數）。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-244">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span> 
    
  - <span data-ttu-id="0d6ea-245">若要使用自訂保留公式來判斷到期，請選擇 [**由此伺服器上安裝的自訂保留公式來設定**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-245">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="0d6ea-246">只有當您的系統管理員已設定自訂公式時，才可使用此選項。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-246">This option is only available if a custom formula has been set up by your administrator.</span></span> 
  
  - <span data-ttu-id="0d6ea-247">在 [動作] 下，指定您要在檔或專案到期時執行的**動作**。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-247">Under **Action**, specify what you want to happen when the document or item expires.</span></span> <span data-ttu-id="0d6ea-248">若要啟用檔或專案（例如刪除）的特定動作，請從清單中選取動作。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-248">To enable a specific action to happen to the document or item (such as deletion), select an action from the list.</span></span> 
    
8. <span data-ttu-id="0d6ea-249">只有在您為已有工作流程相關聯的清單、文件庫或內容類型定義原則時，才可以使用 [**開始工作流程**] 選項。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-249">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="0d6ea-250">然後，您就可以選擇要選擇的工作流程。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-250">You will then be given a choice of workflows to choose from.</span></span> 
    
9. <span data-ttu-id="0d6ea-251">在 **[週期**] 下，選擇 [**重複此階段的動作 ...** ]。，然後輸入您想要動作執行的頻率。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-251">Under **Recurrence**, choose **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="0d6ea-252">只有當您選取的動作可重複時，才可使用此選項。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-252">This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="0d6ea-253">例如，您無法為**永久刪除**動作設定迴圈。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-253">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span> 
  
10. <span data-ttu-id="0d6ea-254">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-254">Choose **OK**.</span></span>
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a><span data-ttu-id="0d6ea-255">將網站集合原則套用至內容類型</span><span class="sxs-lookup"><span data-stu-id="0d6ea-255">Apply a site collection policy to a content type</span></span>
<span data-ttu-id="0d6ea-256"><a name="__apply_a_site"> </a></span><span class="sxs-lookup"><span data-stu-id="0d6ea-256"><a name="__apply_a_site"> </a></span></span>

<span data-ttu-id="0d6ea-257">如果已為網站集合原則的網站建立資訊管理原則，您可以將其中一個原則套用至內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-257">If information management policies have already been created for your site as site collection policies, you can apply one of the policies to a content type.</span></span> <span data-ttu-id="0d6ea-258">這樣一來，您就可以將相同原則套用至網站集合中不共用相同父內容類型的多個內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-258">By doing this, you can apply the same policy to multiple content types in a site collection that do not share the same parent content type.</span></span>
  
 <span data-ttu-id="0d6ea-259">如果您想要將原則套用至網站集合中的多個內容類型，且已設定 Managed Metadata Service，您可以使用內容類型發佈功能，將資訊管理原則發佈至多個網站集合。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-259">If you want to apply policies to multiple content types in a site collection, and you have a Managed Metadata Service configured, you can use Content Type Publishing to publish out information management polices to multiple site collections.</span></span> <span data-ttu-id="0d6ea-260">如需詳細資訊，請參閱[將原則套用到網站集合](#apply-a-policy-across-site-collections)中的一節。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-260">See the section [Apply a policy across site collections](#apply-a-policy-across-site-collections) for more information.</span></span> 
  
1. <span data-ttu-id="0d6ea-261">流覽至包含您要套用原則之內容類型的清單或文件庫。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-261">Navigate to the list or library that contains the content type to which you want to apply a policy.</span></span>
    
2. <span data-ttu-id="0d6ea-262">在功能區上，選擇 [連結**庫**] 或 [**清單**] 索引標籤 \> **庫設定**或**清單設定**。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-262">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>
    
    <span data-ttu-id="0d6ea-263">在 SharePoint Online 中，按一下 [**設定**]，然後按一下 [**清單設定**] 或 [文檔**庫設定**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-263">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span> 
    
3. <span data-ttu-id="0d6ea-264">在 [**許可權與管理** \> **資訊管理原則設定**] 底下。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-264">Under **Permissions and Management** \> **Information management policy settings**.</span></span>
  
![文件庫設定頁面上的資訊管理原則連結](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. <span data-ttu-id="0d6ea-266">確認 [原則來源] 設定為 [**內容類型**]，然後在 [**內容類型原則**] 底下，選取您要套用原則的內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-266">Verify that the policy source is set to **Content Types**, and under **Content Type Policies** select the content type you want to apply the policy to.</span></span> 
    
5. <span data-ttu-id="0d6ea-267">在 [**指定原則** \> **使用網站集合原則**] 底下，從清單中選取您要套用的原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-267">Under **Specify the Policy** \> **Use a site collection policy**, and then select the policy that you want to apply from the list.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="0d6ea-268">如果無法**使用 [使用網站集合原則**] 選項，則表示沒有為網站集合定義網站集合原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-268">If the **Use a site collection policy** option is not available, no site collection policies have been defined for the site collection.</span></span> 
  
6. <span data-ttu-id="0d6ea-269">選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-269">Choose **OK**.</span></span>
    
     <span data-ttu-id="0d6ea-270">如果您使用的清單或文件庫支援多個內容類型的管理，您可以在 [**內容類型**] 底下，選擇您要指定資訊管理原則的內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-270">If the list or library you are working with supports the management of multiple content types, under **Content Types** you can choose the content type for which you want to specify an information management policy.</span></span> <span data-ttu-id="0d6ea-271">這會將您直接帶到上述步驟5。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-271">This will take you directly to Step 5 above.</span></span> 
    
## <a name="apply-a-policy-across-site-collections"></a><span data-ttu-id="0d6ea-272">在網站集合中套用原則</span><span class="sxs-lookup"><span data-stu-id="0d6ea-272">Apply a policy across site collections</span></span>
<span data-ttu-id="0d6ea-273"><a name="__toc260646789"> </a></span><span class="sxs-lookup"><span data-stu-id="0d6ea-273"><a name="__toc260646789"> </a></span></span>

<span data-ttu-id="0d6ea-274">使用 Managed Metadata service 應用程式來設定內容類型發佈，以跨網站集合共用內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-274">Share content types across site collections by using a Managed Metadata service application to set up content type publishing.</span></span> <span data-ttu-id="0d6ea-275">內容類型發佈可協助您在整個網站中統一管理內容和中繼資料，因為內容類型可以集中建立及更新，而且可以將更新發佈至多個訂閱網站集合或 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-275">Content type publishing helps you manage content and metadata consistently across your sites because content types can be created and updated centrally, and updates can be published out to multiple subscribing site collections or Web applications.</span></span>
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a><span data-ttu-id="0d6ea-276">從現有的原則建立範本以用於跨網站集合</span><span class="sxs-lookup"><span data-stu-id="0d6ea-276">Create a template from an existing policy to use across site collections</span></span>
<span data-ttu-id="0d6ea-277"><a name="__toc262125409"> </a></span><span class="sxs-lookup"><span data-stu-id="0d6ea-277"><a name="__toc262125409"> </a></span></span>

<span data-ttu-id="0d6ea-278">您可以定義資訊管理原則，然後建立範本，以根據需要跨多個網站集合使用。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-278">You can define an information management policy and then create a template from it to use as needed across multiple site collections.</span></span> <span data-ttu-id="0d6ea-279">如果您想要備份資訊原則，也可以使用此方法，也可以做為另一個使用內容類型發佈，以在網站集合中套用一個原則的方法。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-279">This method can be used if you want to have a backup of your information policies, or it can also be used as an alternate method to using content type publishing for applying one policy across site collections.</span></span> <span data-ttu-id="0d6ea-280">您可以從一個網站集合匯出原則，然後將它匯入至另一個網站集合，以建立原則的範本或備份。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-280">You create a template or backup of the policy by exporting the policy from one site collection and then importing it to a saved location or to another site collection.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="0d6ea-281">如果您使用 [匯出/匯入] 功能做為一組原則範本的方式，請記住，在 policy .xml 檔案中存在唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-281">If you using the export/import feature as a way to make a set of policy templates, keep in mind that a unique identifier exists in the policy .xml file.</span></span> <span data-ttu-id="0d6ea-282">因此，您無法將該原則匯入網站一次，而不會變更此唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-282">Because of this, you cannot import that policy into a site more than once without changing this unique identifier.</span></span> 
  
### <a name="export-a-policy"></a><span data-ttu-id="0d6ea-283">匯出原則</span><span class="sxs-lookup"><span data-stu-id="0d6ea-283">Export a policy</span></span>
<span data-ttu-id="0d6ea-284"><a name="__toc260646790"> </a></span><span class="sxs-lookup"><span data-stu-id="0d6ea-284"><a name="__toc260646790"> </a></span></span>

1. <span data-ttu-id="0d6ea-285">在網站集合的首頁上，選擇 [**設定**] ![ [小型設定] 齒輪是用來取代網站設定。 ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **網站設定**。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-285">On the site collection home page, choose **Settings**![Small Settings gear that took the place of Site Settings.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="0d6ea-286">在 SharePoint 群組連線的網站中，按一下 [**設定**]，按一下 [**網站內容**]，然後按一下 [**網站設定**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-286">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="0d6ea-287">在 [網站設定] 頁面的 [**網站集合管理** \> **內容類型原則範本**] 底下。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-287">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span> 
  
![網站設定頁面上的內容類型原則範本連結](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. <span data-ttu-id="0d6ea-289">選擇您想要匯出的原則 \> 滾動至底部 \> **匯出**。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-289">Choose the policy you want to export \> scroll to the bottom \> **Export**.</span></span>
    
4. <span data-ttu-id="0d6ea-290">當提示您儲存或開啟檔案時，請選擇 [**儲存**]，然後選取要儲存檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-290">At the prompt to save or open the file, choose **Save**, and then select a location to save the file to.</span></span> <span data-ttu-id="0d6ea-291">請務必選取可供匯入原則之網站集合使用的位置。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-291">Be sure to select a location that is available to the site collections that are importing the policy.</span></span>
    
5. <span data-ttu-id="0d6ea-292">當 [下載完成] 對話方塊顯示時，選擇 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-292">When the Download Complete dialog is displayed, choose **Close**.</span></span>
    
### <a name="import-a-policy-to-a-different-site-collection"></a><span data-ttu-id="0d6ea-293">將原則匯入至不同的網站集合</span><span class="sxs-lookup"><span data-stu-id="0d6ea-293">Import a policy to a different site collection</span></span>
<span data-ttu-id="0d6ea-294"><a name="__toc260646791"> </a></span><span class="sxs-lookup"><span data-stu-id="0d6ea-294"><a name="__toc260646791"> </a></span></span>

<span data-ttu-id="0d6ea-295">匯入資訊管理原則可讓您在任何指定網站集合內的網站或清單層級，將其套用至多種內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-295">Importing an information management policy enables you to apply it to multiple content types at the site or list level within any given site collection.</span></span> <span data-ttu-id="0d6ea-296">執行這項作業的好處有兩個：您不需要在每個內容類型上重新定義及套用原則，也可以只對原則進行變更，只需在一個位置進行變更，就能更輕鬆地管理原則修正。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-296">The benefits of doing this are twofold: you don't have to re-define and apply the policy on each content type, and you can more easily manage policy modifications by making changes to the policy in just one place.</span></span>
  
1. <span data-ttu-id="0d6ea-297">在您要套用原則之網站集合的首頁上，選擇 [**設定** ![ 用來取代網站設定的小型設定齒輪]。 ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **網站設定**。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-297">On the home page of the site collection to which you want to apply the policy, choose **Settings**![Small Settings gear that took the place of Site Settings.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>
    
    <span data-ttu-id="0d6ea-298">在 SharePoint 群組連線的網站中，按一下 [**設定**]，按一下 [**網站內容**]，然後按一下 [**網站設定**]。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-298">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span> 
    
2. <span data-ttu-id="0d6ea-299">在 [網站設定] 頁面的 [**網站集合管理** \> **內容類型原則範本**] 底下。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-299">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>
    
3. <span data-ttu-id="0d6ea-300">在 [原則] 頁面匯 \> **入** \> **流覽**以尋找原則的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-300">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span></span> 
    
4. <span data-ttu-id="0d6ea-301">選取已在其中儲存原則的 XML 檔 \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-301">Select the XML file in which the policy has been saved \> **Open**.</span></span> 
    
5. <span data-ttu-id="0d6ea-302">在 [匯入網站集合原則] 頁面匯 \> **入**，將原則新增至網站集合。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-302">On the Import a Site Collection Policy page \> **Import** to add the policy to the site collection.</span></span> 
    
<span data-ttu-id="0d6ea-303">您的匯入原則現在可以套用到網站或清單層級的一或多個內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-303">Your imported policy can now be applied to one or many content types at the site or list level.</span></span> 
  
<span data-ttu-id="0d6ea-304">資訊管理原則可讓您的組織控制保留內容的時間長短、審核人員對內容所做的動作，以及將條碼或標籤新增至檔。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-304">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="0d6ea-305">原則可協助強制遵從法律和政府法規或內部的商務程式。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-305">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="0d6ea-306">您可以以系統管理員的身分設定原則，以控制追蹤檔的方式，以及保留檔的時間長度。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-306">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>

<span data-ttu-id="0d6ea-307">您可以建立資訊管理原則，可在網站階層中的三個不同位置，從最廣泛到最窄的位置：</span><span class="sxs-lookup"><span data-stu-id="0d6ea-307">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>
- <span data-ttu-id="0d6ea-308">建立原則，以用於網站集合中的多個內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-308">Create a policy to use on multiple content types within a site collection.</span></span>
- <span data-ttu-id="0d6ea-309">建立網站內容類型的原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-309">Create a policy for a site content type.</span></span>
- <span data-ttu-id="0d6ea-310">建立清單或文件庫的原則。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-310">Create a policy for a list or library.</span></span>

<span data-ttu-id="0d6ea-311">如需詳細資訊，請參閱[資訊管理原則簡介](intro-to-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0d6ea-311">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
  

