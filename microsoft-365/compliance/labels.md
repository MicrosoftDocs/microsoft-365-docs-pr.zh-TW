---
title: 保留標籤概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Office 365 中的保留標籤可以幫助您對正確的內容採取正確的動作。使用保留標籤，您可以分類整個組織中的資料以利控管，並根據該分類強制執行保留規則。您也可以使用保留標籤在 Office 365 中實作記錄管理。
ms.openlocfilehash: 71630812e75ef8b4af2f172f73e51d0084fb0df1
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076248"
---
# <a name="overview-of-retention-labels"></a><span data-ttu-id="b65ae-105">保留標籤概觀</span><span class="sxs-lookup"><span data-stu-id="b65ae-105">Overview of retention labels</span></span>

<span data-ttu-id="b65ae-p102">您的整個組織可能擁有不同類型的內容，需要採取不同的動作才能符合產業規範和內部原則。例如，您可能有：</span><span class="sxs-lookup"><span data-stu-id="b65ae-p102">Across your organization, you probably have different types of content that require different actions taken on them in order to comply with industry regulations and internal policies. For example, you might have:</span></span>
  
- <span data-ttu-id="b65ae-108">至少必須**保留**一小段時間的稅務表單。</span><span class="sxs-lookup"><span data-stu-id="b65ae-108">Tax forms that need to be **retained** for a minimum period of time.</span></span> 
    
- <span data-ttu-id="b65ae-109">到達特定年限之後需要**永久刪除**的新聞材料。</span><span class="sxs-lookup"><span data-stu-id="b65ae-109">Press materials that need to be **permanently deleted** when they reach a certain age.</span></span> 
    
- <span data-ttu-id="b65ae-110">需要先**保留**之然後再**永久刪除**的競爭力研究。</span><span class="sxs-lookup"><span data-stu-id="b65ae-110">Competitive research that needs to be both **retained** and then **permanently deleted**.</span></span> 
    
- <span data-ttu-id="b65ae-111">必須**標示為記錄**使之無法編輯或刪除的工作簽證。</span><span class="sxs-lookup"><span data-stu-id="b65ae-111">Work visas that must be **marked as a record** so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="b65ae-p103">在這些案例中，Office 365 中的保留標籤可以幫助您對正確的內容採取正確的動作。使用保留標籤，您可以分類整個組織中的資料以利管理，並根據該分類強制執行保留規則。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p103">In all of these cases, retention labels in Office 365 can help you take the right actions on the right content. With retention labels, you can classify data across your organization for governance, and enforce retention rules based on that classification.</span></span>
  
<span data-ttu-id="b65ae-114">使用保留標籤，您可以：</span><span class="sxs-lookup"><span data-stu-id="b65ae-114">With retention labels, you can:</span></span>
  
- <span data-ttu-id="b65ae-p104">**讓組織的人員可以手動套用保留標籤**至 Outlook 網頁版、Outlook 2010 及更新版本、OneDrive、SharePoint、Office 365 群組中的內容。使用者通常最清楚自己使用的內容類型，因此可以對其分類並套用適當的原則。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p104">**Enable people in your organization to apply a retention label manually** to content in Outlook on the web, Outlook 2010 and later, OneDrive, SharePoint, and Office 365 groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate policy applied.</span></span> 
    
- <span data-ttu-id="b65ae-117">在當內容符合特定條件時**自動將保留標籤套用到內容**，例如內容包含：</span><span class="sxs-lookup"><span data-stu-id="b65ae-117">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    
  - <span data-ttu-id="b65ae-118">特定類型的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="b65ae-118">Specific types of sensitive information.</span></span>
    
  - <span data-ttu-id="b65ae-119">特定關鍵字符合您建立的查詢。</span><span class="sxs-lookup"><span data-stu-id="b65ae-119">Specific keywords that match a query you create.</span></span>
    
  <span data-ttu-id="b65ae-120">自動將保留標籤套用到內容很重要，因為：</span><span class="sxs-lookup"><span data-stu-id="b65ae-120">The ability to apply retention labels to content automatically is important because:</span></span>
    
     - <span data-ttu-id="b65ae-121">您不需要訓練您的使用者記下所有分類。</span><span class="sxs-lookup"><span data-stu-id="b65ae-121">You don't need to train your users on all of your classifications.</span></span>
    
     - <span data-ttu-id="b65ae-122">您不需要仰賴使用者正確地將所有內容分類。</span><span class="sxs-lookup"><span data-stu-id="b65ae-122">You don't need to rely on users to classify all content correctly.</span></span>
    
   - <span data-ttu-id="b65ae-123">使用者不再需要了解資料控管原則，就可以專心工作。</span><span class="sxs-lookup"><span data-stu-id="b65ae-123">Users no longer need to know about data governance policies - they can instead focus on their work.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b65ae-p105">自動套用標籤的功能需要每位使用者均擁有 Office 365 Enterprise E5 授權，這些使用者有權編輯網站或信箱中已自動標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p105">The capability to apply labels automatically requires an Office 365 Enterprise E5 license for each user who has permissions to edit content that's been automatically labeled in a site or mailbox. Users who simply have read-only access do not require a license.</span></span>
      
- <span data-ttu-id="b65ae-p106">**在 Office 365 中實作記錄管理**，包括電子郵件和文件。您可以使用保留標籤將內容分類成記錄。在這種情況下，無法變更或移除標籤，且不能編輯或刪除內容。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p106">**Implement records management across Office 365**, including both email and documents. You can use a retention label to classify content as a record. When this happens, the label can't be changed or removed, and the content can't be edited or deleted.</span></span> 

- <span data-ttu-id="b65ae-129">**將預設保留標籤套用至 SharePoint 中的文件庫、資料夾或文件集**，以便該位置中的所有文件都繼承預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-129">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that arrive in that location inherit the default retention label.</span></span>  
    
<span data-ttu-id="b65ae-130">您可以在 Microsoft 365 合規性中心、Microsoft 365 安全性中心或 Office 365 安全性與合規性中心建立保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-130">You create and manage retention labels on the Labels page > Retention tab in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security  Compliance Center.</span></span> <span data-ttu-id="b65ae-131">在左側導覽中，選擇 **[分類] \*\* > \*\* [保留標籤] \*\* > \*\* [建立標籤]**。</span><span class="sxs-lookup"><span data-stu-id="b65ae-131">In the left nav, choose **Classification** > **Retention label** > **Create a label**.</span></span>

## <a name="how-retention-labels-work-with-retention-label-policies"></a><span data-ttu-id="b65ae-132">保留標籤如何與保留標籤原則一起使用</span><span class="sxs-lookup"><span data-stu-id="b65ae-132">How retention labels work with label policies</span></span>

<span data-ttu-id="b65ae-133">為貴組織中的人員提供保留標籤，將內容分類只需完成兩個步驟：首先，您必須建立保留標籤，接著將標籤發佈到您指定的位置。</span><span class="sxs-lookup"><span data-stu-id="b65ae-133">Making retention labels available to people in your organization so that they can classify content is a two-step process: first you create the labels, and then you publish them to the locations you choose. When you publish retention labels, a label policy gets created.</span></span> <span data-ttu-id="b65ae-134">當您發佈保留標籤時，系統會建立保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="b65ae-134">When you publish retention labels, a retention label policy gets created.</span></span>
  
![標籤的角色和工作圖](media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
<span data-ttu-id="b65ae-136">保留標籤是由一或多個保留標籤原則所包含之可重複使用的獨立建構元素。</span><span class="sxs-lookup"><span data-stu-id="b65ae-136">Retention labels are independent, reusable building blocks that are included in one or more retention label policies.</span></span> <span data-ttu-id="b65ae-137">保留標籤原則的主要目的是將一組保留標籤分組，以及指定您想讓這些標籤出現的目標位置。</span><span class="sxs-lookup"><span data-stu-id="b65ae-137">Retention labels are independent, reusable building blocks that are included in a label policy and published to different locations. Retention labels can be reused across many policies. The primary purpose of the label policy is to group a set of retention labels and specify the locations where you want those labels to appear.</span></span>
  
![標籤、標籤原則和位置圖表](media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. <span data-ttu-id="b65ae-139">當您發佈保留標籤時，會將它們納入保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="b65ae-139">When you publish retention labels, they're included in a label policy. A single retention label can be included in many policies.</span></span> <span data-ttu-id="b65ae-140">請注意，保留標籤的名稱是固定的，且建立後即無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="b65ae-140">Please note, retention label names are immmutable and cannot be edited once created.</span></span>


2. <span data-ttu-id="b65ae-141">單一保留標籤可納入多個保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="b65ae-141">When you publish retention labels, they're included in a label policy. A single retention label can be included in many policies.</span></span>

3. <span data-ttu-id="b65ae-142">單一位置也可納入多個保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="b65ae-142">A single location can also be included in many retention label policies.</span></span>    
    
3. <span data-ttu-id="b65ae-143">保留標籤原則會指定要發佈保留標籤的位置。</span><span class="sxs-lookup"><span data-stu-id="b65ae-143">Label policies specify the locations to publish the retention labels.</span></span>
    
## <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="b65ae-144">一次只能有一個保留標籤</span><span class="sxs-lookup"><span data-stu-id="b65ae-144">Only one retention label at a time</span></span>

<span data-ttu-id="b65ae-145">請務必了解，電子郵件或文件等內容一次只能指派一個保留標籤：</span><span class="sxs-lookup"><span data-stu-id="b65ae-145">It's important to know that content like an email or document can have only a single retention label assigned to it at a time:</span></span>
  
- <span data-ttu-id="b65ae-146">針對使用者手動指派的保留標籤，使用者可以移除或變更獲指派的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-146">For labels assigned manually by end users, people can remove or change the retention label that's assigned.</span></span>
    
- <span data-ttu-id="b65ae-147">如果內容有指派自動套用的標籤，使用者可以手動指派保留標籤來取代自動套用的標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-147">If content has an auto-apply label assigned, an auto-apply label can be replaced by a retention label assigned manually by an end user.</span></span>
    
- <span data-ttu-id="b65ae-148">如果內容有使用者手動指派的保留標籤，則自動套用標籤無法取代手動指派的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-148">If content has a retention label assigned manually by an end user, an auto-apply label cannot replace the manually assigned retention label.</span></span>
    
- <span data-ttu-id="b65ae-149">如果有多項規則會指派自動套用標籤，且內容符合多項規則的條件，則會指派最舊規則的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-149">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the retention label for the oldest rule is assigned.</span></span>
    
<span data-ttu-id="b65ae-p111">手動指派標籤為明確指派，自動套用標籤為隱含指派。明確保留標籤的優先順序高於隱含標籤。如需詳細資訊，請參閱之後的[保留原則，哪一個優先？](#the-principles-of-retention-or-what-takes-precedence)小節。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p111">Manually assigned labels are explicitly assigned; auto-apply labels are implicitly assigned; an explicit retention label takes precedence over an implicit label. For more information, see the below section on [The principles of retention, or what takes precedence?](#the-principles-of-retention-or-what-takes-precedence).</span></span>

<span data-ttu-id="b65ae-p112">本節中所有的資訊僅適用於保留標籤。請注意，除了一個保留標籤之外，也可以將一個區分大小寫的標籤套用至內容的項目。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p112">All of the information in this section applies only to retention labels. Note that an item of content can also have one sensitivity label applied to it, in addition to one retention label.</span></span>
  
## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="b65ae-154">保留標籤要多久才會生效</span><span class="sxs-lookup"><span data-stu-id="b65ae-154">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="b65ae-155">當您發佈或自動套用保留標籤時，標籤不會立即生效：</span><span class="sxs-lookup"><span data-stu-id="b65ae-155">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="b65ae-156">首先，標籤原則必須先將系統管理中心與原則中的位置同步。</span><span class="sxs-lookup"><span data-stu-id="b65ae-156">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="b65ae-157">接著，位置可能會需要一些時間，將已發佈的保留標籤提供給使用者，或是將標籤自動套用到內容。</span><span class="sxs-lookup"><span data-stu-id="b65ae-157">Then the location may require time to make manual labels available to end users or auto-apply labels to content. How long this takes depends on the location and type of label.</span></span> <span data-ttu-id="b65ae-158">實際所需的時間取決於保留標籤的位置和類型。</span><span class="sxs-lookup"><span data-stu-id="b65ae-158">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="b65ae-159">已發佈的保留標籤</span><span class="sxs-lookup"><span data-stu-id="b65ae-159">Published retention labels</span></span>

<span data-ttu-id="b65ae-p114">如果您將保留標籤發佈到 SharePoint 或 OneDrive，需要一天的時間讓這些保留標籤向使用者顯示。此外，如果您將保留標籤發佈到 Exchange，可能需要 7 天來向使用者顯示這些保留標籤，且信箱至少必須包含 10 MB 的資料。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p114">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![手動標籤生效的圖](media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="b65ae-163">自動套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="b65ae-163">Auto-apply retention labels</span></span>

<span data-ttu-id="b65ae-164">如果您將保留標籤自動套用至符合特定條件的內容，保留標籤套用至符合條件的所有現有內容可能需要 7 天。</span><span class="sxs-lookup"><span data-stu-id="b65ae-164">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span> <span data-ttu-id="b65ae-165">但請注意，部署保留標籤之後套用至新的內容很快，通常在 15 分鐘之內。</span><span class="sxs-lookup"><span data-stu-id="b65ae-165">But note that after your retention labels are deployed, they are applied to new content quickly, typically in 15 minutes or less.</span></span>
  
![自動標籤生效的圖](media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="b65ae-167">如何檢查發佈至 Exchange 之保留標籤的狀態</span><span class="sxs-lookup"><span data-stu-id="b65ae-167">How to check on the status of Exchange labels</span></span>

<span data-ttu-id="b65ae-p116">在 Exchange Online 中，是透過每 7 天執行一次的程序，將保留標籤提供給使用者。您可以使用 Powershell 查看此程序上次執行的時間，依此判斷下一次執行時間。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p116">In Exchange Online, retention labels are made available to end users by a process that runs every seven days. By using Powershell, you can see when this process last ran and thus determine when it will run again.</span></span>
  
1. <span data-ttu-id="b65ae-170">[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-170">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="b65ae-171">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="b65ae-171">Run these commands.</span></span>
    
  ```
  $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
  ```

  ```
  $xmlprops = [xml]($logProps.MailboxLog)
  ```

  ```
  $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
  ```

<span data-ttu-id="b65ae-172">結果：`ELCLastSuccessTimeStamp` (UTC) 屬性會顯示系統上次處理您信箱的時間。</span><span class="sxs-lookup"><span data-stu-id="b65ae-172">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="b65ae-173">如果系統在您建立原則後都還未處理信箱，標籤就無法顯示。</span><span class="sxs-lookup"><span data-stu-id="b65ae-173">In the results, the   (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  .</span></span> <span data-ttu-id="b65ae-174">若要強制處理信箱，請執行 `Start-ManagedFolderAssistant -Identity <user>`。</span><span class="sxs-lookup"><span data-stu-id="b65ae-174">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="b65ae-175">如果標籤沒有出現在 Outlook 網頁版中，而您認為應該要出現，請務必清除瀏覽器中的快取 (CTRL + F5)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-175">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    
## <a name="retention-label-policies-and-locations"></a><span data-ttu-id="b65ae-176">保留標籤原則與位置</span><span class="sxs-lookup"><span data-stu-id="b65ae-176">Retention label policies and locations</span></span>

<span data-ttu-id="b65ae-177">可以將不同類型的保留標籤發佈到不同的位置，視保留標籤的功能而定。</span><span class="sxs-lookup"><span data-stu-id="b65ae-177">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
|<span data-ttu-id="b65ae-178">**如果保留標籤是...**</span><span class="sxs-lookup"><span data-stu-id="b65ae-178">**If the retention label is…**</span></span>|<span data-ttu-id="b65ae-179">**則標籤原則可套用至...**</span><span class="sxs-lookup"><span data-stu-id="b65ae-179">**Then the label policy can be applied to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b65ae-180">發佈給使用者</span><span class="sxs-lookup"><span data-stu-id="b65ae-180">Published to end users</span></span>  <br/> |<span data-ttu-id="b65ae-181">Exchange、SharePoint、OneDrive、Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="b65ae-181">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
|<span data-ttu-id="b65ae-182">根據敏感資訊類型而自動套用</span><span class="sxs-lookup"><span data-stu-id="b65ae-182">Auto-applied based on sensitive information types</span></span>  <br/> |<span data-ttu-id="b65ae-183">Exchange (僅限所有信箱)、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="b65ae-183">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="b65ae-184">根據查詢而自動套用</span><span class="sxs-lookup"><span data-stu-id="b65ae-184">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="b65ae-185">Exchange、SharePoint、OneDrive、Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="b65ae-185">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
   
<span data-ttu-id="b65ae-p118">請注意，在 Exchange 中自動套用保留標籤 (查詢和敏感資訊類型) 只會套用到新傳送的郵件 (傳送中的資料)，不會套用到目前信箱中的所有項目 (靜止的資料)。此外，用於敏感資訊類型的自動套用保留標籤只能套用到所有信箱，無法指定特定的信箱。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p118">Note that in Exchange, auto-apply retention labels (for both queries and sensitive information types) are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest). Also, auto-apply retention labels for sensitive information types can apply only to all mailboxes; you can't select the specific mailboxes.</span></span>
  
<span data-ttu-id="b65ae-188">請注意，Exchange 公用資料夾和 Skype 不支援標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-188">Note that Exchange public folders and Skype do not support labels.</span></span>
  
## <a name="how-retention-labels-enforce-retention"></a><span data-ttu-id="b65ae-189">保留標籤如何強制保留</span><span class="sxs-lookup"><span data-stu-id="b65ae-189">How retention labels enforce retention</span></span>

<span data-ttu-id="b65ae-p119">保留標籤可以強制執行與保留原則完全相同的保留動作。您可以使用保留標籤來實作複雜的內容規劃 (或檔案規劃)。如需保留運作方式的詳細資訊，請參閱[保留原則概觀](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p119">Retention labels can enforce exactly the same retention actions that a retention policy can. You can use retention labels to implement a sophisticated content plan (or file plan). For more information on how retention works, see [Overview of retention policies](retention-policies.md).</span></span>
  
<span data-ttu-id="b65ae-p120">除此之外，保留標籤有兩個只能用於保留標籤，但不能用於保留原則的保留選項。使用保留標籤，您可以：</span><span class="sxs-lookup"><span data-stu-id="b65ae-p120">In addition, a retention label has two retention options that are available only in a retention label and not in a retention policy. With a retention label, you can:</span></span>
  
- <span data-ttu-id="b65ae-p121">在保留期間結束時觸發處置檢閱，這樣能在刪除 SharePoint 和 OneDrive 文件之前，必須先檢閱它們。如需詳細資訊，請參閱[處置檢閱概觀](disposition-reviews.md)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p121">Trigger a disposition review at the end of the retention period, so that SharePoint and OneDrive documents must be reviewed before they can be deleted. For more information, see [Overview of disposition reviews](disposition-reviews.md).</span></span>
    
- <span data-ttu-id="b65ae-197">保留期間是從內容套用標籤時開始計算，而不是內容的壽命或上次修改時間。</span><span class="sxs-lookup"><span data-stu-id="b65ae-197">Start the retention period from when the content was labeled, instead of the age of the content or when it was last modified.</span></span> <span data-ttu-id="b65ae-198">請注意，此選項僅適用 SharePoint 網站和 OneDrive 帳戶中的內容。</span><span class="sxs-lookup"><span data-stu-id="b65ae-198">Note that this option applies only to content in SharePoint sites and OneDrive accounts.</span></span> <span data-ttu-id="b65ae-199">針對 Exchange 電子郵件，保留期間一律會取決於傳送或接收訊息的日期，無論在這裡選擇的選項為何。</span><span class="sxs-lookup"><span data-stu-id="b65ae-199">For Exchange email, the retention period is always based on the date when the message was sent or received, no matter which option you choose here.</span></span>
    
![保留設定與標籤專用的選項](media/c49118c9-6279-4661-94db-deffa76e27ac.png)
  
## <a name="where-published-retention-labels-can-appear-to-end-users"></a><span data-ttu-id="b65ae-201">可以向使用者顯示已發佈保留標籤的位置</span><span class="sxs-lookup"><span data-stu-id="b65ae-201">Where published retention labels can appear to end users</span></span>

<span data-ttu-id="b65ae-202">如果保留標籤將由使用者指派給內容，您可以將它發佈到：</span><span class="sxs-lookup"><span data-stu-id="b65ae-202">If your retention label will be assigned to content by end users, you can publish it to:</span></span>
  
- <span data-ttu-id="b65ae-203">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="b65ae-203">Outlook on the web</span></span>
    
- <span data-ttu-id="b65ae-204">Outlook 2010 及更新版本</span><span class="sxs-lookup"><span data-stu-id="b65ae-204">Outlook 2010 and later</span></span>
    
- <span data-ttu-id="b65ae-205">OneDrive</span><span class="sxs-lookup"><span data-stu-id="b65ae-205">OneDrive</span></span>
    
- <span data-ttu-id="b65ae-206">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b65ae-206">SharePoint</span></span>
    
- <span data-ttu-id="b65ae-207">Office 365 群組 (群組網站和Outlook 網頁版中的群組信箱)</span><span class="sxs-lookup"><span data-stu-id="b65ae-207">Office 365 groups (both the group site and group mailbox in Outlook on the web)</span></span>
    
<span data-ttu-id="b65ae-208">以下各節說明標籤在不同應用程式中向組織內人員顯示的方式。</span><span class="sxs-lookup"><span data-stu-id="b65ae-208">The sections below show how labels will appear in different apps to people in your organization.</span></span>
  
### <a name="outlook-on-the-web"></a><span data-ttu-id="b65ae-209">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="b65ae-209">Outlook on the web</span></span>

<span data-ttu-id="b65ae-210">若要在 Outlook 網頁版中的項目加上標籤，以滑鼠右鍵按一下該項目 \>[指派原則]\*\*\*\* \> 選擇保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-210">To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label.</span></span> 
  
![Outlook 網頁版中的指派原則功能表](media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
<span data-ttu-id="b65ae-p123">套用保留標籤後，您可以在項目頂端檢視該保留標籤以及它採取的動作。如果電子郵件已分類，且有相關聯的保留期間，您可以一目了然電子郵件的到期日。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p123">After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.</span></span>
  
![指派給 Outlook 網頁版電子郵件的標籤](media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
<span data-ttu-id="b65ae-215">您也可以將保留標籤套用到資料夾，在此情況下：</span><span class="sxs-lookup"><span data-stu-id="b65ae-215">You can also apply retention labels to folders, in which case:</span></span>
  
- <span data-ttu-id="b65ae-p124">資料夾中的所有項目會自動套用相同的保留標籤，**除了**已明確套用保留標籤的項目。已明確套用標籤的項目會保留現有的保留標籤。如需詳細資訊，請參閱之後的保留原則小節。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p124">All items in the folder automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them. Explicitly labeled items keep their existing retention label. For more information, see the below section on the principles of retention.</span></span> 
    
- <span data-ttu-id="b65ae-219">如果您變更或移除資料夾的預設保留標籤，資料夾中的所有項目也會變更或移除該保留標籤，**除了**明確套用保留標籤的項目。</span><span class="sxs-lookup"><span data-stu-id="b65ae-219">If you change or remove the default retention label for a folder, the retention label's also changed or removed for all items in the folder, **except** items with explicit retention labels.</span></span> 
    
- <span data-ttu-id="b65ae-220">如果您將有預設保留標籤的項目從某個資料夾移到另一個具有不同預設保留標籤的資料夾，該項目就會套用新的預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-220">If you move an item with a default retention label from one folder to another folder with a different default retention label, the item will get the new default retention label.</span></span>
    
- <span data-ttu-id="b65ae-221">如果您將有預設保留標籤的項目從某個資料夾移到另一個沒有不同預設保留標籤的資料夾，就會移除舊的預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-221">If you move an item with a default retention label from one folder to another folder with no default retention label, the old default retention label is removed.</span></span>
    
### <a name="outlook-2010-and-later"></a><span data-ttu-id="b65ae-222">Outlook 2010 及更新版本</span><span class="sxs-lookup"><span data-stu-id="b65ae-222">Outlook 2010 and later</span></span>

<span data-ttu-id="b65ae-223">若要在 Outlook 網頁版中的項目加上標籤，以滑鼠右鍵按一下該項目 \> 在 [功能區]\*\*\*\* 中 \> [指派原則]\*\*\*\* \> 選擇保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-223">To label an item in Outlook on the web, right-click the item \> on the **Ribbon** \> **Assign Policy** \> choose the retention label.</span></span> 
  
![指派原則按鈕](media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
<span data-ttu-id="b65ae-225">套用保留標籤後，您可以在項目頂端檢視該保留標籤以及所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="b65ae-225">After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.</span></span> <span data-ttu-id="b65ae-226">如果電子郵件已套用具有相關聯保留期間的保留標籤，您可以快速查看電子郵件的到期日。</span><span class="sxs-lookup"><span data-stu-id="b65ae-226">If an email has a retention label applied that has an associated retention period, you can see at a glance when the email will expire.</span></span>
  
<span data-ttu-id="b65ae-p126">您也可以將保留標籤套用到資料夾。這在 Outlook 2010 及更新版本中和在 Outlook 網頁版中的作用一樣。詳細資訊請參閱前一節。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p126">You can also apply retention labels to folders. This works the same in Outlook 2010 and later as it does in Outlook on the web -- see the previous section for more info.</span></span>
  
### <a name="onedrive-and-sharepoint"></a><span data-ttu-id="b65ae-229">OneDrive 和 SharePoint</span><span class="sxs-lookup"><span data-stu-id="b65ae-229">OneDrive and SharePoint</span></span>

<span data-ttu-id="b65ae-230">若要為 OneDrive 或 SharePoint 中的文件 (包括 OneNote 檔案) 加上標籤，請選取右上角的項目 \>、選擇 [開啟詳細資料窗格]\*\*\*\*![[資訊窗格] 圖示](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \>[套用保留標籤]\*\*\*\* \>，然後選擇保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-230">To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply label** \> choose the retention label.</span></span> 
  
<span data-ttu-id="b65ae-231">請注意，您也可以將保留標籤套用至資料夾或數個文件，可以為文件庫設定預設保留標籤；詳細資訊請參閱下一小節。</span><span class="sxs-lookup"><span data-stu-id="b65ae-231">Note that you can also apply a retention label to a folder or document set, and you can set a default retention label for a document library - see the section below for more information.</span></span>
  
![SharePoint 中項目的套用標籤清單](media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
<span data-ttu-id="b65ae-233">將保留標籤套用到項目之後，您可以選取項目，並在詳細資料窗格中檢視標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-233">After a retention label is applied to an item, you can view it in the details pane when that item's selected.</span></span>
  
![詳細資料窗格中顯示已套用的標籤](media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
<span data-ttu-id="b65ae-p127">您也可以建立包含**標籤**資料行或**項目是記錄**資料行的文件庫檢視，以便快速查看指派給所有項目的保留標籤以及哪些項目是記錄。不過請注意，您無法以**項目是記錄**資料行篩選檢視。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p127">You can also create a view of the library that contains the **Labels** column or **Item is a Record** column, so that you can see at a glance the retention labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column.</span></span> 
  
![自訂檢視中顯示的標籤資料行文件庫](media/e3392627-c0a3-405e-bb57-55f27c34cfdd.png)
  
### <a name="office-365-groups"></a><span data-ttu-id="b65ae-238">Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="b65ae-238">Office 365 groups</span></span>

<span data-ttu-id="b65ae-p128">當您將保留標籤發佈到 Office 365 群組時，保留標籤會顯示在群組網站和 Outlook 網頁版中的群組信箱。將保留標籤套用至內容和上述的套用至電子郵件和文件完全相同。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p128">When you publish retention labels to an Office 365 group, the retention labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a retention label to content is identical to that shown above for email and documents.</span></span>

<span data-ttu-id="b65ae-p129">若要保留 Office 365 群組的內容，您必須使用 Office 365 群組位置。雖然 Office 365 群組擁有 Exchange 信箱，包含整個 Exchange 位置的保留原則並不會包含 Office 365 群組信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p129">To retain content for an Office 365 group, you need to use the Office 365 groups location. Even though an Office 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Office 365 group mailboxes.</span></span>

<span data-ttu-id="b65ae-p130">此外，無法使用 Exchange 位置來包含或排除特定群組信箱。雖然 Exchange 位置最初允許選取群組信箱，但是當您嘗試儲存保留原則時，您會收到「RemoteGroupMailbox 不是Exchange 位置的有效選取項目」錯誤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p130">In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox. Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you'll receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>
  
## <a name="applying-a-retention-label-automatically-based-on-conditions"></a><span data-ttu-id="b65ae-245">根據條件自動套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="b65ae-245">Applying a retention label automatically based on conditions</span></span>

<span data-ttu-id="b65ae-p131">保留標籤最強大的功能之一，是能夠自動套用至符合特定條件的內容。在此情況下，貴組織中的人員不需要套用保留標籤，Office 365 會替他們做這些事。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p131">One of the most powerful features of retention labels is the ability to apply them automatically to content that matches certain conditions. In this case, people in your organization don't need to apply the retention labels - Office 365 does the work for them.</span></span>
  
![自動套用標籤的角色和工作圖](media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
<span data-ttu-id="b65ae-249">自動套用保留標籤很強大是因為：</span><span class="sxs-lookup"><span data-stu-id="b65ae-249">Auto-apply retention labels are powerful because:</span></span>
  
- <span data-ttu-id="b65ae-250">您不需要訓練您的使用者記下所有分類。</span><span class="sxs-lookup"><span data-stu-id="b65ae-250">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="b65ae-251">您不需要仰賴使用者正確地將所有內容分類。</span><span class="sxs-lookup"><span data-stu-id="b65ae-251">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="b65ae-252">使用者不再需要了解資料控管原則，他們可以專心工作。</span><span class="sxs-lookup"><span data-stu-id="b65ae-252">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="b65ae-253">您可以選擇當內容包含以下資訊時，自動將保留標籤套用到內容：</span><span class="sxs-lookup"><span data-stu-id="b65ae-253">You can choose to apply retention labels to content automatically when that content contains:</span></span>
  
- <span data-ttu-id="b65ae-254">特定類型的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="b65ae-254">Specific types of sensitive information.</span></span>
    
- <span data-ttu-id="b65ae-255">特定關鍵字符合您建立的查詢。</span><span class="sxs-lookup"><span data-stu-id="b65ae-255">Specific keywords that match a query you create.</span></span>
    
![自動套用標籤的條件選擇頁面](media/c0b7a3ef-bda0-494c-941d-f1f93753ecdd.png)
  
<span data-ttu-id="b65ae-257">請注意，自動套用保留標籤需要 Office 365 企業版 E5 訂用帳戶，且如前文所述，可能需要 7 天讓自動套用保留標籤套用至符合條件的所有內容。</span><span class="sxs-lookup"><span data-stu-id="b65ae-257">Note that auto-apply retention labels require an Office 365 Enterprise E5 subscription, and that it can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions, as described above.</span></span>
  
### <a name="auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="b65ae-258">自動將保留標籤套用至包含特定類型敏感資訊的內容</span><span class="sxs-lookup"><span data-stu-id="b65ae-258">Auto-apply retention labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="b65ae-p132">當您為敏感資訊建立自動套用保留標籤時，會看到和建立資料外洩防護 (DLP) 原則相同的原則範本清單。每個原則範本皆預先設定為尋找特定類型的敏感資訊，例如，此處顯示的範本會尋找美國 ITIN、SSN 和護照號碼。若要深入了解 DLP，請參閱[資料外洩防護原則概觀](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p132">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy. Each policy template is preconfigured to look for specific types of sensitive information - for example, the template shown here looks for U.S. ITIN, SSN, and passport numbers. To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![敏感資訊類型的原則範本](media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="b65ae-p133">選取原則範本後，可以新增或移除任何類型的敏感資訊，且可以變更例項計數和比對精確度。此處所示的範例中，只有符合以下條件時，才會自動套用保留標籤：</span><span class="sxs-lookup"><span data-stu-id="b65ae-p133">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="b65ae-p134">內容包含 1 到 9 個下列三種敏感資訊類型。您可以刪除 \*\*max \*\* (上限) 值，條件就會變成 **any** (任何)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p134">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="b65ae-p135">偵測到的敏感資訊類型的比對精確度 (或信賴等級) 下限為 75。許多敏感資訊類型會定義多個模式，模式的比對精確度愈高，便需要尋找愈多證據 (例如關鍵字、日期、地址)，而較低比對精確度的模式則需要較少的證據。簡單來說，比對精確度的 **min** (下限) 愈低，就越容易找到與條件相符的內容。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p135">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="b65ae-270">如需這些選項的詳細資訊，請參閱[調整規則，讓規則更容易或更難相符](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-270">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![用於識別機密資訊類型的選項](media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="b65ae-272">自動將標籤套用至包含關鍵字或可搜尋屬性的內容</span><span class="sxs-lookup"><span data-stu-id="b65ae-272">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="b65ae-p136">您可以自動將標籤套用至符合特定條件的內容。現在可用的條件支援將標籤套用至包含特定字詞、片語或可搜尋屬性的值。您可以使用 AND、OR、NOT 等搜尋運算子來精簡查詢。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p136">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="b65ae-276">如需查詢語法的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b65ae-276">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="b65ae-277">關鍵字查詢語言 (KQL) 語法參考</span><span class="sxs-lookup"><span data-stu-id="b65ae-277">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/zh-TW/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="b65ae-p137">查詢式標籤使用搜尋索引來識別內容。如需有效可搜尋屬性的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b65ae-p137">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="b65ae-280">內容搜尋的關鍵字查詢與搜尋條件</span><span class="sxs-lookup"><span data-stu-id="b65ae-280">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="b65ae-281">SharePoint 伺服器中的編目及受控屬性概觀</span><span class="sxs-lookup"><span data-stu-id="b65ae-281">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/zh-TW/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="b65ae-282">範例查詢：</span><span class="sxs-lookup"><span data-stu-id="b65ae-282">Examples queries:</span></span>

- <span data-ttu-id="b65ae-283">Exchange</span><span class="sxs-lookup"><span data-stu-id="b65ae-283">Exchange</span></span>
    - <span data-ttu-id="b65ae-284">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="b65ae-284">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="b65ae-285">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="b65ae-285">recipients:garthf</span></span><!--nolink--><span data-ttu-id="b65ae-286">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b65ae-286">@contoso.com</span></span>
- <span data-ttu-id="b65ae-287">SharePoint 和商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="b65ae-287">SharePoint and OneDrive for Business</span></span>
    - <span data-ttu-id="b65ae-288">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="b65ae-288">contenttype:contract</span></span>
    - <span data-ttu-id="b65ae-289">site:https</span><span class="sxs-lookup"><span data-stu-id="b65ae-289">site:https</span></span><!--nolink--><span data-ttu-id="b65ae-290">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="b65ae-290">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![查詢編輯器](media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)

## <a name="applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a><span data-ttu-id="b65ae-292">將預設保留標籤套用至 SharePoint 文件庫、資料夾或文件集中的所有內容</span><span class="sxs-lookup"><span data-stu-id="b65ae-292">Applying a default retention label to all content in a SharePoint library, folder, or document set</span></span>

<span data-ttu-id="b65ae-293">除了讓使用者將保留標籤套用至個別文件，您也可以將預設保留標籤套用到 SharePoint 文件庫、資料夾或文件集，讓該位置的所有文件套用預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-293">In addition to enabling people to apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set, so that all documents in that location get the default retention label.</span></span>
  
<span data-ttu-id="b65ae-p138">以文件庫來說，這是在文件庫的 [文件庫設定]\*\*\*\* 頁面完成。當您選擇預設保留標籤時，也可以選擇將其套用至文件庫中的任何現有項目。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p138">For a document library, this is done on the **Library settings** page for a document library. When you choose the default retention label, you can also choose to apply it to any existing items in the library.</span></span> 
  
<span data-ttu-id="b65ae-296">例如，如果您有一個行銷資料的標籤，而且您知道某個文件庫只包含這個類型的內容，就能將「行銷資料」標籤設為該文件庫中所有文件的預設標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-296">For example, if you have a tag for marketing materials, and you know a specific document library will contain only that type of content, you can make the Marketing Materials tag the default for all documents in that library.</span></span>
  
![文件庫設定頁面上的套用標籤選項](media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
<span data-ttu-id="b65ae-298">如果將預設保留標籤套用到文件庫、資料夾或文件集中的現有項目：</span><span class="sxs-lookup"><span data-stu-id="b65ae-298">If you apply a default retention label to existing items in the library, folder, or document set:</span></span>
  
- <span data-ttu-id="b65ae-p139">文件庫、資料夾或文件集中的所有項目會自動套用相同的標籤，**除了**已明確套用保留標籤的項目。已明確套用標籤的項目會保留現有的標籤。如需詳細資訊，請參閱之後的[保留原則，哪一個優先？](#the-principles-of-retention-or-what-takes-precedence)小節。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p139">All items in the library, folder, or document set automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them. Explicitly labeled items keep their existing label. For more information, see the below section on [The principles of retention, or what takes precedence?](#the-principles-of-retention-or-what-takes-precedence).</span></span>
    
- <span data-ttu-id="b65ae-302">如果您變更或移除文件庫、資料夾或文件集的預設保留標籤時，文件庫、資料夾或文件集中的所有項目也會變更或移除該保留標籤，**除了**明確套用保留標籤的項目。</span><span class="sxs-lookup"><span data-stu-id="b65ae-302">If you change or remove the default retention label for a library, folder, or document set, the retention label's also changed or removed for all items in the library, folder, or document set, **except** items with explicit retention labels.</span></span> 
    
- <span data-ttu-id="b65ae-303">如果將有預設保留標籤的項目從其文件庫、資料夾或文件集移到另一個文件庫、資料夾或文件集，該項目會保留現有的保留標籤，即使新位置有不同的預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-303">If you move an item with a default retention label from one library, folder, or document set to another library, folder, or document set, the item keeps its existing default retention label, even if the new location has a different default retention label.</span></span>
    
## <a name="applying-a-retention-label-to-email-by-using-rules"></a><span data-ttu-id="b65ae-304">使用規則將保留標籤套用至電子郵件</span><span class="sxs-lookup"><span data-stu-id="b65ae-304">Applying a retention label to email by using rules</span></span>

<span data-ttu-id="b65ae-305">在 Outlook 2010 及更新版本中，您可以建立規則來套用保留標籤或保留原則。</span><span class="sxs-lookup"><span data-stu-id="b65ae-305">In Outlook 2010 or later, you can create rules to apply a retention label or retention policy.</span></span>
  
<span data-ttu-id="b65ae-306">例如，您可以建立規則來將特定保留標籤套用到傳送至或接收自特定通訊群組的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="b65ae-306">For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.</span></span>
  
<span data-ttu-id="b65ae-307">若要建立規則，以滑鼠右鍵按一下項目\> [規則]\*\*\*\* \> [建立規則]\*\*\*\* \> [進階選項]\*\*\*\* \> [規則精靈]\*\*\*\* \> [套用保留原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b65ae-307">To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.</span></span>
  
![規則精靈與套用保留原則的選項](media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="b65ae-309">將內容分類而不套用任何動作</span><span class="sxs-lookup"><span data-stu-id="b65ae-309">Classifying content without applying any actions</span></span>

<span data-ttu-id="b65ae-p140">當您建立保留標籤時，可以只建立標籤而不開啟任何保留或進行其他動作，如下所示。在此情況下，您可以單純使用保留標籤作為文字標籤，不強制執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p140">When you create a retention label, you can do so without turning on any retention or other actions, as shown below. In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="b65ae-312">例如，您可以建立不帶任何動作、名為「稍後檢閱」的保留標籤，然後將此保留標籤自動套用到包含敏感資訊類型或查詢內容的內容。</span><span class="sxs-lookup"><span data-stu-id="b65ae-312">For example, you can create a retention label named "Review later" with no actions, and then auto-apply that retention label to content with sensitive information types or queried content.</span></span>
  
![標籤設定頁面中關閉保留](media/17ce863b-a823-426e-aaad-83718465f762.png)
  
## <a name="using-retention-labels-for-records-management"></a><span data-ttu-id="b65ae-314">將保留標籤用於記錄管理</span><span class="sxs-lookup"><span data-stu-id="b65ae-314">Using retention labels for records management</span></span>

<span data-ttu-id="b65ae-315">從高層次來看，記錄管理意味著：</span><span class="sxs-lookup"><span data-stu-id="b65ae-315">At a high level, records management means that:</span></span>
  
- <span data-ttu-id="b65ae-316">重要內容由使用者分類為記錄。</span><span class="sxs-lookup"><span data-stu-id="b65ae-316">Important content is classified as a record by users.</span></span>
    
- <span data-ttu-id="b65ae-317">不能修改或刪除記錄。</span><span class="sxs-lookup"><span data-stu-id="b65ae-317">A record can't be modified or deleted.</span></span>
    
- <span data-ttu-id="b65ae-318">記錄在其規定的壽命結束後終將丟棄。</span><span class="sxs-lookup"><span data-stu-id="b65ae-318">Records are finally disposed of after their stated lifetime is past.</span></span>
    
<span data-ttu-id="b65ae-p141">您可以使用保留標籤在 Office 365 中實作單一、一致的記錄管理策略，其他記錄管理功能 (如記錄中心) 則僅能套用至 SharePoint 內容。您可以對記錄強制執行保留動作，然後在記錄生命週期結束時，自動丟棄這些記錄。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p141">You can use retention labels to implement a single, consistent records-management strategy across Office 365, whereas other records-management features such as the Record Center apply only to SharePoint content. And you can enforce retention actions on records, so that they're disposed of automatically at the end of their lifecycle.</span></span>
  
<span data-ttu-id="b65ae-321">當您建立保留標籤時，可以選擇使用保留標籤將內容分類為記錄。</span><span class="sxs-lookup"><span data-stu-id="b65ae-321">When you create a retention label, you have the option to use the retention label to classify the content as a record.</span></span>
  
![將內容分類為記錄核取方塊](media/9c300739-d5d0-41d2-88dd-137f1cfc9cb6.png)
  
<span data-ttu-id="b65ae-323">如果將項目標示為記錄，會發生四件事：</span><span class="sxs-lookup"><span data-stu-id="b65ae-323">When an item is labeled as a record, four things happen:</span></span>
  
- <span data-ttu-id="b65ae-324">無法永久刪除此項目。</span><span class="sxs-lookup"><span data-stu-id="b65ae-324">The item can't be permanently deleted.</span></span>
    
- <span data-ttu-id="b65ae-325">無法編輯此項目。</span><span class="sxs-lookup"><span data-stu-id="b65ae-325">The item can't be edited.</span></span>
    
- <span data-ttu-id="b65ae-326">無法變更此標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-326">The label can't be changed.</span></span>
    
- <span data-ttu-id="b65ae-327">無法移除此標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-327">The label can't be removed.</span></span>
    
### <a name="who-can-classify-content-as-a-record"></a><span data-ttu-id="b65ae-328">誰可以將內容分類為記錄</span><span class="sxs-lookup"><span data-stu-id="b65ae-328">Who can classify content as a record</span></span>

<span data-ttu-id="b65ae-p142">針對 SharePoint 內容，預設成員群組 (「參與」權限等級) 中的任何使用者皆可以將記錄標籤套用至內容。只有網站集合管理員可以移除或變更已套用的保留標籤。此外，可以將內容分類為記錄的保留標籤[自動套用至內容](#auto-apply-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p142">For SharePoint content, any user in the default Members group (the Contribute permission level) can apply a record label to content. Only the site collection administrator can remove or change that retention label after it's been applied. In addition, a retention label that classifies content as a record can be [auto-applied to content](#auto-apply-retention-labels).</span></span>
  
### <a name="records-and-folders"></a><span data-ttu-id="b65ae-332">記錄和資料夾</span><span class="sxs-lookup"><span data-stu-id="b65ae-332">Records and folders</span></span>

<span data-ttu-id="b65ae-p143">您可以將保留標籤套用至 Exchange、SharePoint 或 OneDrive 中的資料夾。如果資料夾已標示為記錄，而您將項目移至該資料夾，該項目會標示為記錄。將項目移出資料夾，該項目仍會標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p143">You can apply a retention label to a folder in Exchange, SharePoint, or OneDrive. If a folder is labeled as a record, and you move an item into the folder, the item is labeled as a record. When you move the item out of the folder, the item will continue to be labeled as a record.</span></span>
  
### <a name="records-cant-be-deleted"></a><span data-ttu-id="b65ae-336">無法刪除記錄</span><span class="sxs-lookup"><span data-stu-id="b65ae-336">Records can't be deleted</span></span>

<span data-ttu-id="b65ae-337">如果您嘗試刪除 Exchange 中的一筆記錄，該項目會移到「可復原的項目」資料夾中，如[保留原則如何就地處理內容](retention-policies.md#how-a-retention-policy-works-with-content-in-place) 中所述。</span><span class="sxs-lookup"><span data-stu-id="b65ae-337">If you attempt to delete a record in Exchange, the item is moved to the Recoverable Items folder as described in [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
<span data-ttu-id="b65ae-338">如果您嘗試刪除 SharePoint 中的記錄，您會看到無法刪除該項目的錯誤，該項目仍會保留在文件庫中。</span><span class="sxs-lookup"><span data-stu-id="b65ae-338">If you attempt to delete a record in a SharePoint, you see an error that the item wasn't deleted, and the item remains in the library.</span></span>
  
![無法從 SharePoint 中刪除項目的訊息](media/d0020726-1593-4a96-b07c-89b275e75c49.png)
  
<span data-ttu-id="b65ae-340">如果您嘗試刪除 OneDrive 中的一筆記錄，該項目會移到「文件保留庫」中，如[保留原則如何就地處理內容](retention-policies.md#how-a-retention-policy-works-with-content-in-place) 中所述。</span><span class="sxs-lookup"><span data-stu-id="b65ae-340">If you attempt to delete a record in OneDrive, the item is moved to the Preservation Hold library as described in [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="b65ae-341">使用保留標籤作為 DLP 原則的條件</span><span class="sxs-lookup"><span data-stu-id="b65ae-341">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="b65ae-p144">保留標籤可強制執行保留內容的動作。此外，您也可以使用保留標籤作為資料外洩防護 (DLP) 原則的條件。DLP 原則可以對包含特定標籤的內容強制執行其他動作，例如限制存取。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p144">A retention label can enforce retention actions on content. In addition, you can use a retention label as a condition in a data loss prevention (DLP) policy, and the DLP policy can enforce other actions, such as restricting access, on content that contains a specific label.</span></span> 
  
<span data-ttu-id="b65ae-344">如需詳細資訊，請參閱[使用標籤做為條件的 DLP 原則](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-344">For more information, see [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="monitor-retention-labels"></a><span data-ttu-id="b65ae-345">監控保留標籤</span><span class="sxs-lookup"><span data-stu-id="b65ae-345">Monitor retention labels</span></span>

<span data-ttu-id="b65ae-p145">發佈或自動套用保留標籤後，您會想要確認它們如您的預期套用到內容。若要監控您的保留標籤，可以使用：</span><span class="sxs-lookup"><span data-stu-id="b65ae-p145">After you publish or auto-apply your retention labels, you'll want to verify that they're being applied to content as you intended. To monitor your retention labels, you can use the:</span></span>
  
- <span data-ttu-id="b65ae-p146">**標籤活動總管**。使用標籤活動總管 (如下所示)，可以快速搜尋和檢視過去 30 天在 SharePoint 和商務用 OneDrive 上所有內容的保留標籤活動。如需詳細資訊，請參閱[檢視文件的標籤活動](view-label-activity-for-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p146">**Label Activity Explorer**. With the explorer (shown below), you can quickly search and view retention label activity for all content across SharePoint and OneDrive for Business over the past 30 days. For more information, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

- <span data-ttu-id="b65ae-351">[標籤分析]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="b65ae-351">**Label analytics** page.</span></span> <span data-ttu-id="b65ae-352">在 Microsoft 365 合規性中心和 Microsoft 365 安全性中心中，您可以快速檢視最常使用的標籤和套用標籤的位置。</span><span class="sxs-lookup"><span data-stu-id="b65ae-352">In the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly view your top labels and where they're applied.</span></span> <span data-ttu-id="b65ae-353">您也可以檢視具有特定標籤的所有內容。</span><span class="sxs-lookup"><span data-stu-id="b65ae-353">You can also view all content with a specific label.</span></span> <span data-ttu-id="b65ae-354">如需詳細資訊，請參閱[利用標籤分析檢視標籤使用量](label-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-354">For more information, see [View label usage with label analytics](label-analytics.md).</span></span>
    
- <span data-ttu-id="b65ae-p148">**資料控管報告**。使用資料控管報告，可以快速檢視過去 90 天在 Exchange、SharePoint、商務用 OneDrive 上所有內容的保留標籤趨勢和活動。如需詳細資訊，請參閱[資料控管報告](view-the-data-governance-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p148">**Data governance reports**. With these reports, you can quickly view retention label trends and activity for all content across Exchange, SharePoint, and OneDrive for Business over the past 90 days. For more information, see [View the data governance reports](view-the-data-governance-reports.md).</span></span>
    
![標籤活動總管](media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a><span data-ttu-id="b65ae-359">使用內容搜尋來尋找套用特定保留標籤的所有內容</span><span class="sxs-lookup"><span data-stu-id="b65ae-359">Using Content Search to find all content with a specific retention label applied to it</span></span>

<span data-ttu-id="b65ae-360">將保留標籤指派至內容後 (無論是由使用者指派或自動套用)，您可以使用「內容搜尋」，尋找以特定保留標籤分類的所有內容。</span><span class="sxs-lookup"><span data-stu-id="b65ae-360">After retention labels are assigned to content, either by users or auto-applied, you can use content search to find all content that's classified with a specific retention label.</span></span>
  
<span data-ttu-id="b65ae-p149">當您建立內容搜尋時，請選擇 [合規性標籤]\*\*\*\* 條件，然後輸入完整的標籤名稱或是部分標籤名稱加上萬用字元。如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p149">When you create a content search, choose the **Compliance Tag** condition, and then enter the complete label name or part of the label name and use a wildcard. For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![合規性標籤條件](media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="b65ae-364">原則保留，哪一個優先？</span><span class="sxs-lookup"><span data-stu-id="b65ae-364">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="b65ae-p150">很有可能內容會套用多個保留原則，這些原則各有不同的動作 (保留、刪除或兩者) 和保留期間。哪一個優先？請放心，最低限度，由一個原則保留的內容不會被另一個原則永久刪除。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p150">It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or both) and retention period. What takes precedence? At the highest level, rest assured that content being retained by one policy can't be permanently deleted by another policy.</span></span>
  
![原則保留圖](media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="b65ae-369">若要了解不同標籤的保留動作如何套用至內容，請記住以下保留原則：</span><span class="sxs-lookup"><span data-stu-id="b65ae-369">To understand how different labels with retention actions are applied to content, keep these principles of retention in mind:</span></span>
  
1. <span data-ttu-id="b65ae-p151">**保留優先於刪除。** 假設一個保留原則要在 3 年後刪除 Exchange 電子郵件，但另一個保留原則要保留 Exchange 電子郵件 5 年再刪除。任何達到 3 年的內容會遭到刪除，在使用者檢視中看不到它們，但仍會保留在 [可復原的項目] 資料夾，直到內容達到 5 年，便會永久刪除。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p151">**Retention wins over deletion.** Suppose that one retention policy says to delete Exchange email after three years, but another retention policy says to retain Exchange email for five years and then delete it. Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it will be permanently deleted.</span></span> 
    
2. <span data-ttu-id="b65ae-p152">**最長保留期間優先。** 如果內容套用多個保留內容的原則，則會一直保留到最長保留期間結束為止。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p152">**The longest retention period wins.** If content's subject to multiple policies that retain content, it will be retained until the end of the longest retention period.</span></span> 
    
3. <span data-ttu-id="b65ae-p153">**明確包含優先於隱含包含。** 意思是：</span><span class="sxs-lookup"><span data-stu-id="b65ae-p153">**Explicit inclusion wins over implicit inclusion.** This means:</span></span> 
    
    1. <span data-ttu-id="b65ae-p154">如果包含保留設定的保留標籤是由使用者手動指派給項目 (例如 Exchange 電子郵件或 OneDrive 文件)，則此保留標籤優先於在網站或信箱層級指派的原則，並優先於文件庫指派的預設保留標籤。例如，如果明確保留標籤要保留 10 年，但指派給網站的保留原則只要保留 5 年，則保留標籤優先。請注意，自動套用的保留標籤會被視為隱含而不是明確，因為它們是由 Office 365 自動套用。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p154">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a policy assigned at the site or mailbox level and a default retention label assigned by the document library. For example, if the explicit retention label says to retain for ten years, but the retention policy assigned to the site says to retain for only five years, the retention label takes precedence. Note that auto-apply retention labels are considered implicit, not explicit, because they're applied automatically by Office 365.</span></span>
    
    2. <span data-ttu-id="b65ae-380">如果保留原則包含特定位置 (例如特定使用者的信箱或商務用 OneDrive 帳戶)，則此原則優先於其他套用至所有使用者信箱或商務用 OneDrive 帳戶但未特地包含該使用者信箱的保留原則。</span><span class="sxs-lookup"><span data-stu-id="b65ae-380">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive for Business account, that policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive for Business accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="b65ae-p155">**最短刪除期間優先。** 同樣地，如果內容套用多個刪除內容的原則 (無保留)，則會在最短保留期間結束時刪除。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p155">**The shortest deletion period wins.** Similarly, if content's subject to multiple policies that delete content (with no retention), it will be deleted at the end of the shortest retention period.</span></span> 
    
<span data-ttu-id="b65ae-383">了解保留原則從上到下的仲裁流程：如果所有原則或標籤套用的規則都在同一個層級，則流程會移到下一個層級來決定套用規則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="b65ae-383">Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all policies or labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.</span></span>
  
<span data-ttu-id="b65ae-p156">最後，保留原則或標籤無法永久刪除 eDiscovery 保留的任何內容。保留解除時，這些內容便再度符合上述的清理程序。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p156">Finally, a retention policy or label cannot permanently delete any content that's on hold for eDiscovery. When the hold is released, the content again becomes eligible for the cleanup process described above.</span></span>
  
## <a name="use-retention-labels-instead-of-these-features"></a><span data-ttu-id="b65ae-386">使用保留標籤而非這些功能</span><span class="sxs-lookup"><span data-stu-id="b65ae-386">Use retention labels instead of these features</span></span>

<span data-ttu-id="b65ae-p157">您可以輕鬆將保留標籤運用在整個組織及其 Office 365 內容，包括 Exchange、SharePoint、OneDrive、Office 365 群組。若您需要在 Office 365 任何地方分類內容或管理記錄，建議您使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p157">Retention labels can easily be made available to an entire organization and its content across Office 365, including Exchange, SharePoint, OneDrive, and Office 365 groups. If you need to classify content or manage records anywhere in Office 365, we recommend that you use retention labels.</span></span>
  
<span data-ttu-id="b65ae-389">Office 365 先前提供數種用於將內容分類以及管理記錄的功能，</span><span class="sxs-lookup"><span data-stu-id="b65ae-389">There are several other features that have previously been used to classify content or manage records in Office 365.</span></span> <span data-ttu-id="b65ae-390">如下所示。</span><span class="sxs-lookup"><span data-stu-id="b65ae-390">These are listed below.</span></span> <span data-ttu-id="b65ae-391">這些功能會繼續支援保留標籤。</span><span class="sxs-lookup"><span data-stu-id="b65ae-391">These features will continue to work side by side with retention labels.</span></span> <span data-ttu-id="b65ae-392">請注意，雖然有保留標籤實作與先前功能不同的實例，但是保留標籤的演進會促進 Office 365 記錄管理的未來發展。</span><span class="sxs-lookup"><span data-stu-id="b65ae-392">Note that while there are instances where the implementation of retention labels differs from previous features, the evolution of retention labels will drive the future of records management across Office 365.</span></span> <span data-ttu-id="b65ae-393">因此，我們建議您向前邁進，使用保留標籤而非這些功能來進行資料控管。</span><span class="sxs-lookup"><span data-stu-id="b65ae-393">Therefore, moving forward, for data governance, we recommend that you use retention labels instead of these features.</span></span>
  
### <a name="exchange-online"></a><span data-ttu-id="b65ae-394">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b65ae-394">Exchange Online</span></span>

- <span data-ttu-id="b65ae-395">[保留標記和保留原則](https://go.microsoft.com/fwlink/?linkid=846125)，又稱為[郵件記錄管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (僅限刪除)</span><span class="sxs-lookup"><span data-stu-id="b65ae-395">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (Deletion only)</span></span> 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="b65ae-396">SharePoint Online 和商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="b65ae-396">SharePoint Online and OneDrive for Business</span></span>

- <span data-ttu-id="b65ae-397">[設定就地記錄管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保留)</span><span class="sxs-lookup"><span data-stu-id="b65ae-397">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (Retention)</span></span> 
    
- <span data-ttu-id="b65ae-398">[記錄中心簡介](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (保留)</span><span class="sxs-lookup"><span data-stu-id="b65ae-398">[Introduction to the Records Center](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (Retention)</span></span> 
    
- <span data-ttu-id="b65ae-399">[資料管理原則](intro-to-info-mgmt-policies.md) (僅限刪除)</span><span class="sxs-lookup"><span data-stu-id="b65ae-399">[Information management policies](intro-to-info-mgmt-policies.md) (Deletion only)</span></span> 
    
## <a name="permissions"></a><span data-ttu-id="b65ae-400">權限</span><span class="sxs-lookup"><span data-stu-id="b65ae-400">Permissions</span></span>

<span data-ttu-id="b65ae-p159">您的合規性小組中將建立保留標籤的成員必須具備安全性與合規性中心的權限。根據預設，租用戶管理員將可存取此位置，並且可直接讓法務人員與其他人存取安全性與合規性中心，而不需要為其提供租用戶管理員的所有權限。若要這麼做，我們建議您：移至安全性與合規性中心的 [權限]\*\*\*\* 頁面，編輯 [合規性管理員]\*\*\*\* 角色群組，將該成員加入此角色群組。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p159">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="b65ae-403">如需詳細資訊，請參閱[授與使用者存取 Office 365 安全性與合規性中心的權限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b65ae-403">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="b65ae-p160">需要這些權限才能建立及套用保留標籤和標籤原則。原則強制執行不需要內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="b65ae-p160">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>  
## <a name="find-the-powershell-cmdlets-for-labels"></a><span data-ttu-id="b65ae-406">尋找標籤的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b65ae-406">Find the PowerShell cmdlets for labels</span></span>

<span data-ttu-id="b65ae-407">若要使用標籤 Cmdlet，您必須：</span><span class="sxs-lookup"><span data-stu-id="b65ae-407">To use the label cmdlets, you need to:</span></span>
  
1. [<span data-ttu-id="b65ae-408">連接到 Office 365 安全性與合規性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b65ae-408">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="b65ae-409">使用這些 Office 365 安全性與合規性中心 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b65ae-409">Use these Office 365 Security & Compliance Center cmdlets:</span></span>

  - [<span data-ttu-id="b65ae-410">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="b65ae-410">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetag)

  - [<span data-ttu-id="b65ae-411">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="b65ae-411">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-compliancetag)

  - [<span data-ttu-id="b65ae-412">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="b65ae-412">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-compliancetag)

  - [<span data-ttu-id="b65ae-413">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="b65ae-413">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-compliancetag)

  - [<span data-ttu-id="b65ae-414">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="b65ae-414">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/enable-compliancetagstorage)

  - [<span data-ttu-id="b65ae-415">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="b65ae-415">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetagstorage)

  - [<span data-ttu-id="b65ae-416">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="b65ae-416">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)

  - [<span data-ttu-id="b65ae-417">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="b65ae-417">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)

  - [<span data-ttu-id="b65ae-418">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="b65ae-418">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)

  - [<span data-ttu-id="b65ae-419">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="b65ae-419">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)

  - [<span data-ttu-id="b65ae-420">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="b65ae-420">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)

  - [<span data-ttu-id="b65ae-421">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="b65ae-421">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)

  - [<span data-ttu-id="b65ae-422">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="b65ae-422">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)

  - [<span data-ttu-id="b65ae-423">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="b65ae-423">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)
