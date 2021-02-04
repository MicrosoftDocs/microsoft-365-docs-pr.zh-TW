---
title: 了解保留原則和標籤，以自動保留或刪除內容
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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 了解保留原則和保留標籤，可協助您保留所需的內容，並刪除您不想要的內容。
ms.openlocfilehash: d834cc53677c8b7c01ed4bec40ed51983d41e9da
ms.sourcegitcommit: 4f40f5be140a23bacff6fd7b85536de14fc7d499
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084622"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a><span data-ttu-id="e6ff3-103">了解保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="e6ff3-103">Learn about retention policies and retention labels</span></span>

><span data-ttu-id="e6ff3-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="e6ff3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e6ff3-p101">對大多數組織來說，其資料 (電子郵件、文件、即時訊息等) 的數量和複雜性日益增加。有效管理或控管此資訊至關重要，因為您需要：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="e6ff3-107">**主動遵守產業規範和內部原則**，因此您需要將某些內容至少保留一段時間，例如，Sarbanes-Oxley 法案可能會要求您將某些類型的內容保留七年。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 

- <span data-ttu-id="e6ff3-108">**降低發生訴訟或安全性漏洞的風險**，方法為永久刪除您不再需要保留的舊內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="e6ff3-109">**協助貴組織有效分享知識並提高靈活度**，方法為確保使用者只使用目前和相關的內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="e6ff3-110">您設定的保留設定可協助您實現所有目標。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-110">Retention settings that you configure can help you achieve all these goals.</span></span> <span data-ttu-id="e6ff3-111">管理內容通常需要以下兩個動作：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-111">Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="e6ff3-112">**保留** 內容，以便無法在保留期間結束之前將其永久刪除。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="e6ff3-113">在保留期間結束之前，永久 **刪除** 內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    

<span data-ttu-id="e6ff3-114">使用這兩個保留動作，您可以設定以下結果的保留設定：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-114">With these two retention actions, you can configure retention settings for the following outcomes:</span></span>

- <span data-ttu-id="e6ff3-115">僅保留：永久持續保留內容或保留指定的一段時間。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-115">Retain-only: Retain content forever or for a specified period of time.</span></span>
- <span data-ttu-id="e6ff3-116">僅刪除：指定一段時間後刪除內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-116">Delete-only: Delete content after a specified period of time.</span></span>
- <span data-ttu-id="e6ff3-117">保留並刪除：將內容保留指定的時間，然後將其刪除。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-117">Retain and then delete: Retain content for a specified period of time and then delete it.</span></span>

<span data-ttu-id="e6ff3-118">這些保留設定可以使用就地內容，從而在您基於合規性原因而必須保留內容時，節省建立和設定額外儲存體的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-118">These retention settings work with content in place that saves you the additional overheads of creating and configuring additional storage when you need to retain content for compliance reasons.</span></span> <span data-ttu-id="e6ff3-119">此外，您不必執行自訂的程序來複製及同步處理這項資料。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-119">In addition, you don't need to implement customized processes to copy and synchronize this data.</span></span>

## <a name="how-retention-settings-work-with-content-in-place"></a><span data-ttu-id="e6ff3-120">保留設定如何與就地內容搭配使用</span><span class="sxs-lookup"><span data-stu-id="e6ff3-120">How retention settings work with content in place</span></span>

<span data-ttu-id="e6ff3-121">當內容有指派保留設定時，該內容會保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-121">When content has retention settings assigned to it, that content remains in its original location.</span></span> <span data-ttu-id="e6ff3-122">若未發生任何變更，人員可以繼續使用其文件或郵件。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-122">People can continue to work with their documents or mail as if nothing's changed.</span></span> <span data-ttu-id="e6ff3-123">但如果人員編輯或刪除保留原則中包含的內容，則會自動保留內容複本。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-123">But if they edit or delete content that's included in the retention policy, a copy of the content is automatically retained.</span></span>
  
- <span data-ttu-id="e6ff3-124">對於 SharePoint 和 OneDrive 網站：複本會保留在 **文件保留庫** 中。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-124">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span>

- <span data-ttu-id="e6ff3-125">針對 Exchange 信箱：複本會保留在 **[可復原的項目]** 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-125">For Exchange mailboxes: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="e6ff3-126">針對 Teams 和 Yammer 訊息：複本會保留在名為 **SubstrateHolds** 的隱藏資料夾中，以作為 Exchange [可復原的項目 **]** 資料夾中的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-126">For Teams and Yammer messages: The copy is retained in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="e6ff3-127">[文件保留庫] 會佔用不受網站儲存空間配額限制的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-127">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota.</span></span> <span data-ttu-id="e6ff3-128">當您對 SharePoint 和 Microsoft 365 群組使用保留設定時，可能需要增加您的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-128">You might need to increase your storage when you use retention settings for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="e6ff3-129">大部分的人員無法檢視這些安全的位置和保留的內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-129">These secure locations and the retained content are not visible to most people.</span></span> <span data-ttu-id="e6ff3-130">在大部分的情況下，使用者甚至不需要知道其內容受保留設定的限制。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-130">In most cases, people do not even need to know that their content is subject to retention settings.</span></span>

<span data-ttu-id="e6ff3-131">如需有關保留設定如何配合不同工作負載使用的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-131">For more detailed information about how retention settings work for different workloads, see the following articles:</span></span>

- [<span data-ttu-id="e6ff3-132">了解 SharePoint 和 OneDrive 的保留功能</span><span class="sxs-lookup"><span data-stu-id="e6ff3-132">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="e6ff3-133">了解 Microsoft Teams 保留</span><span class="sxs-lookup"><span data-stu-id="e6ff3-133">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="e6ff3-134">了解 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="e6ff3-134">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="e6ff3-135">了解 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="e6ff3-135">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="e6ff3-136">保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="e6ff3-136">Retention policies and retention labels</span></span>

<span data-ttu-id="e6ff3-137">若要將保留設定指派給內容，請將 **保留原則** 和 **保留標籤與標籤原則** 一起使用。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-137">To assign your retention settings to content, use **retention policies** and **retention labels with label policies**.</span></span> <span data-ttu-id="e6ff3-138">您可以只使用其中一種方法，也可以將它們結合使用。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-138">You can use just one of these methods, or combine them.</span></span>

<span data-ttu-id="e6ff3-139">使用保留原則為網站或信箱層級的內容指派相同的保留設定，並使用保留標籤來指派項目層級 (資料夾、文件、電子郵件) 的保留設定。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-139">Use a retention policy to assign the same retention settings for content at a site or mailbox level, and use a retention label to assign retention settings at an item level (folder, document, email).</span></span>

<span data-ttu-id="e6ff3-140">例如，如果 SharePoint 網站中的所有文件都應該保留 5 年，使用保留原則比將相同的保留標籤套用至該網站中所有文件的方法更有效率。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-140">For example, if all documents in a SharePoint site should be retained for 5 years, it's more efficient to do this with a retention policy than apply the same retention label to all documents in that site.</span></span> <span data-ttu-id="e6ff3-141">不過，如果該網站中的部分文件應保留 5 年，而其他文件保留 10 年，一個保留原則就不夠用。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-141">However, if some documents in that site should be retained for 5 years and others retained for 10 years, a retention policy wouldn't be able to do this.</span></span> <span data-ttu-id="e6ff3-142">當您必須在項目層級指定保留設定時，請使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-142">When you need to specify retention settings at the item level, use retention labels.</span></span> 

<span data-ttu-id="e6ff3-143">不同於保留原則，保留標籤的保留設定會隨著內容移至您 Microsoft 365 租用戶中不同的位置。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-143">Unlike retention policies, retention settings from retention labels travel with the content if it’s moved to a different location within your Microsoft 365 tenant.</span></span> <span data-ttu-id="e6ff3-144">此外，保留標籤具有以下保留原則不支援的功能：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-144">In addition, retention labels have the following capabilities that retention policies don't support:</span></span> 
 
- <span data-ttu-id="e6ff3-145">除了內容的年限或上次修改時間以外，還可選擇從為內容加上標籤的時間或根據事件來開始保留期間的選項。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-145">Options to start the retention period from when the content was labeled or based on an event, in addition to the age of the content or when it was last modified.</span></span>

- <span data-ttu-id="e6ff3-146">使用[可訓練分類器](classifier-learn-about.md)來識別要加上標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-146">Use [trainable classifiers](classifier-learn-about.md) to identify content to label.</span></span>

- <span data-ttu-id="e6ff3-147">為 SharePoint 文件套用預設標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-147">Apply a default label for SharePoint documents.</span></span>

- <span data-ttu-id="e6ff3-148">支援[處置檢閱](disposition-reviews.md) 以在內容永久刪除之前檢閱。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-148">Support [disposition review](disposition-reviews.md) to review the content before it's permanently deleted.</span></span>

- <span data-ttu-id="e6ff3-149">將內容標示為做為標籤設定一部分的[記錄](records-management.md#records)，並且在保留期間結束而刪除內容時，永遠都有 [處置證明](disposition.md#disposition-of-records) 。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-149">Mark the content as a [record](records-management.md#records) as part of the label settings, and always have [proof of disposition](disposition.md#disposition-of-records) when content is deleted at the end of its retention period.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="e6ff3-150">保留原則</span><span class="sxs-lookup"><span data-stu-id="e6ff3-150">Retention policies</span></span>

<span data-ttu-id="e6ff3-151">保留原則可以套用到以下位置：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-151">Retention policies can be applied to the following locations:</span></span>
- <span data-ttu-id="e6ff3-152">Exchange 電子郵件</span><span class="sxs-lookup"><span data-stu-id="e6ff3-152">Exchange email</span></span>
- <span data-ttu-id="e6ff3-153">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="e6ff3-153">SharePoint site</span></span>
- <span data-ttu-id="e6ff3-154">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="e6ff3-154">OneDrive accounts</span></span>
- <span data-ttu-id="e6ff3-155">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="e6ff3-155">Microsoft 365 Groups</span></span>
- <span data-ttu-id="e6ff3-156">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e6ff3-156">Skype for Business</span></span>
- <span data-ttu-id="e6ff3-157">Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="e6ff3-157">Exchange public folders</span></span>
- <span data-ttu-id="e6ff3-158">Teams 通道訊息</span><span class="sxs-lookup"><span data-stu-id="e6ff3-158">Teams channel messages</span></span>
- <span data-ttu-id="e6ff3-159">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="e6ff3-159">Teams chats</span></span>
- <span data-ttu-id="e6ff3-160">Yammer 社群訊息</span><span class="sxs-lookup"><span data-stu-id="e6ff3-160">Yammer community messages</span></span>
- <span data-ttu-id="e6ff3-161">Yammer 私人訊息</span><span class="sxs-lookup"><span data-stu-id="e6ff3-161">Yammer private messages</span></span>

<span data-ttu-id="e6ff3-162">您可以輕鬆地將單一原則套用到多個位置，或特定位置或使用者。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-162">You can very efficiently apply a single policy to multiple locations, or to specific locations or users.</span></span>

<span data-ttu-id="e6ff3-163">保留期間開始時，您可以選擇建立內容的時間，或者只支援檔案和 SharePoint、OneDrive 和 Microsoft 365 群組位置 (上次修改內容的時間) 的時間。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-163">For the start of the retention period, you can choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Microsoft 365 Groups locations, when the content was last modified.</span></span>

<span data-ttu-id="e6ff3-164">專案會從保留原則指定的容器繼承保留設定。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-164">Items inherit the retention settings from their container specified in the retention policy.</span></span> <span data-ttu-id="e6ff3-165">如果在爲了保留内容而設定原則時將專案移至容器外，則會在工作負荷的安全位置保留該專案的複本。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-165">If they are then moved outside that container when the policy is configured to retain content, a copy of that item is retained in the workload's secured location.</span></span> <span data-ttu-id="e6ff3-166">不過，保留設定不會隨著內容移至新的位置。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-166">However, the retention settings don't travel with the content in its new location.</span></span> <span data-ttu-id="e6ff3-167">如有需要，請使用保留標籤，而非保留原則。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-167">If that's required, use retention labels instead of retention policies.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="e6ff3-168">保留標籤</span><span class="sxs-lookup"><span data-stu-id="e6ff3-168">Retention labels</span></span>

<span data-ttu-id="e6ff3-169">請針對需要不同保留設定的不同類型的內容，使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-169">Use retention labels for different types of content that require different retention settings.</span></span> <span data-ttu-id="e6ff3-170">例如：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-170">For example:</span></span>
  
- <span data-ttu-id="e6ff3-171">至少必須保留一小段時間的稅務表單。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-171">Tax forms that need to be retained for a minimum period of time.</span></span> 
    
- <span data-ttu-id="e6ff3-172">到達特定年限之後需要永久刪除的新聞材料。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-172">Press materials that need to be permanently deleted when they reach a specific age.</span></span> 
    
- <span data-ttu-id="e6ff3-173">需要先保留一段期間之然後再永久刪除的競爭力研究。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-173">Competitive research that needs to be retained for a specific period and then permanently deleted.</span></span> 
    
- <span data-ttu-id="e6ff3-174">必須標示為記錄使之無法編輯或刪除的工作簽證。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-174">Work visas that must be marked as a record so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="e6ff3-175">在這些情況下，保留標籤可讓您在項目層級 (文件或電子郵件) 套用治理控制的保留設定。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-175">In all these cases, retention labels let you apply retention settings for governance control at the item level (document or email).</span></span>
  
<span data-ttu-id="e6ff3-176">使用保留標籤，您可以：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-176">With retention labels, you can:</span></span>
  
- <span data-ttu-id="e6ff3-177">**讓貴組織中的人員手動將保留標籤套用** 至網頁上的 Outlook 和 Outlook、OneDrive、SharePoint 和 Microsoft 365 群組中的內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-177">**Enable people in your organization to apply a retention label manually** to content in Outlook and Outlook on the web, OneDrive, SharePoint, and Microsoft 365 groups.</span></span> <span data-ttu-id="e6ff3-178">使用者通常都清楚知道自己處理的內容類型，因此可將內容分類並套用適當的保留設定。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-178">Users often know best what type of content they're working with, so they can classify it and have the appropriate retention settings applied.</span></span> 
    
- <span data-ttu-id="e6ff3-179">在當內容符合特定條件時 **自動將保留標籤套用到內容**，例如內容包含：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-179">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    - <span data-ttu-id="e6ff3-180">特定類型的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-180">Specific types of sensitive information.</span></span>
    - <span data-ttu-id="e6ff3-181">特定關鍵字符合您建立的查詢。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-181">Specific keywords that match a query you create.</span></span>
    - <span data-ttu-id="e6ff3-182">可訓練分類器的模式比對。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-182">Pattern matches for a trainable classifier.</span></span>

- <span data-ttu-id="e6ff3-183">針對 SharePoint 網站和 OneDrive 帳戶中的文件和電子郵件項目 (行事曆項除外)，**從內容加上標籤起就開始保留期間**。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-183">**Start the retention period from when the content was labeled** for documents in SharePoint sites and OneDrive accounts, and to email items with the exception of calendar items.</span></span> <span data-ttu-id="e6ff3-184">如果您將具有此設定的保留標籤套用於行事曆項目，則保留期間從其傳送日期開始。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-184">If you apply a retention label with this configuration to a calendar item, the retention period starts from when it is sent.</span></span>

- <span data-ttu-id="e6ff3-185">**當事件發生時 (例如員工離開組織或合約到期)，開始保留期間**。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-185">**Start the retention period when an event occurs**, such as employees leave the organization, or contracts expire.</span></span>

- <span data-ttu-id="e6ff3-186">**將預設保留標籤套用至 SharePoint 中的文件庫、資料夾或文件集**，以便儲存在該位置中的所有文件都繼承預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-186">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that are stored in that location inherit the default retention label.</span></span>

<span data-ttu-id="e6ff3-187">此外，保留標籤支援跨 Microsoft 365 應用程式和服務的電子郵件和文件[記錄管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-187">Additionally, retention labels support [records management](records-management.md) for email and documents across Microsoft 365 apps and services.</span></span> <span data-ttu-id="e6ff3-188">您可以使用保留標籤將內容標記為記錄。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-188">You can use a retention label to mark items as a record.</span></span> <span data-ttu-id="e6ff3-189">發生此情況且內容仍保留在 Microsoft 365 中時，標籤會針對法規原因可能所需的內容施加進一步的限制。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-189">When this happens and the content remains in Microsoft 365, the label places further restrictions on the content that might be needed for regulatory reasons.</span></span> <span data-ttu-id="e6ff3-190">如需詳細資訊，請參閱 [比較允許或封鎖動作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-190">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

<span data-ttu-id="e6ff3-191">與[敏感度標籤](sensitivity-labels.md)不同，如果內容是移至 Microsoft 365 以外的位置，保留標籤不會保留。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-191">Retention labels, unlike [sensitivity labels](sensitivity-labels.md), do not persist if the content is moved outside Microsoft 365.</span></span>

<span data-ttu-id="e6ff3-192">針對租用戶支援的保留標籤數量沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-192">There is no limit to the number of retention labels that are supported for a tenant.</span></span> <span data-ttu-id="e6ff3-193">不過，10,000 個是針對租用戶支援的原則數目上限，其中包括會套用標籤 (保留標籤原則和自動套用保留原則) 的原則，以及保留原則。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-193">However, 10,000 is the maximum number of policies that are supported for a tenant and these include the policies that apply the labels (retention label policies and auto-apply retention policies), as well as retention policies.</span></span>

#### <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="e6ff3-194">將內容分類而不套用任何動作</span><span class="sxs-lookup"><span data-stu-id="e6ff3-194">Classifying content without applying any actions</span></span>

<span data-ttu-id="e6ff3-195">雖然保留標籤的主要目的是要保留或刪除內容，但您也可以在不開啟任何保留或其他動作的情況下使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-195">Although the main purpose of retention labels is to retain or delete content, you can also use retention labels without turning on any retention or other actions.</span></span> <span data-ttu-id="e6ff3-196">在此情況下，您可以使用保留標籤當做文字標籤，而不強制執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-196">In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="e6ff3-197">例如，您可以建立並套用名為「稍後檢閱」的保留標籤，而不執行任何動作，然後使用該標籤於稍後尋找該內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-197">For example, you can create and apply a retention label named "Review later" with no actions, and then use that label to find that content later.</span></span>
  
![僅限分類的標籤設定](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="e6ff3-199">使用保留標籤作為 DLP 原則的條件</span><span class="sxs-lookup"><span data-stu-id="e6ff3-199">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="e6ff3-200">您可以將保留標籤做為 SharePoint 文件的資料外洩防護 (DLP) 原則中的條件。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-200">You can specify a retention label as a condition in a data loss prevention (DLP) policy for documents in SharePoint.</span></span> <span data-ttu-id="e6ff3-201">例如，設定 DLP 原則以防止文件在組織外共用 (如果已套用指定的保留標籤)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-201">For example, configure a DLP policy to prevent documents from being shared outside the organization if they have a specified retention label applied to it.</span></span>

<span data-ttu-id="e6ff3-202">如需詳細資訊，請參閱[使用保留標籤做為 DLP 原則中的條件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-202">For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

#### <a name="retention-labels-and-policies-that-apply-them"></a><span data-ttu-id="e6ff3-203">保留標籤和套用其標籤的原則</span><span class="sxs-lookup"><span data-stu-id="e6ff3-203">Retention labels and policies that apply them</span></span>

<span data-ttu-id="e6ff3-204">當您發佈保留標籤時，會將這些標籤包含在 **保留標籤原則** 中，好讓系統管理員和使用者將其套用至內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-204">When you publish retention labels, they're included in a **retention label policy** that makes them available for admins and users to apply to content.</span></span> <span data-ttu-id="e6ff3-205">如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-205">As the following diagram shows:</span></span>

1. <span data-ttu-id="e6ff3-206">單一保留標籤可納入多個保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-206">A single retention label can be included in multiple retention label policies.</span></span>

2. <span data-ttu-id="e6ff3-207">保留標籤原則會指定要發佈保留標籤的位置。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-207">Retention label policies specify the locations to publish the retention labels.</span></span> <span data-ttu-id="e6ff3-208">同一位置可以納入多個保留標籤原則中。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-208">The same location can be included in multiple retention label policies.</span></span>

![如何將保留標籤新增至指定位置的標籤原則](../media/retention-labels-and-policies.png)

<span data-ttu-id="e6ff3-210">您也可以建立一或多個 **自動套用原則**，每一個都有單一保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-210">You can also create one or more **auto-apply retention label policies**, each with a single retention label.</span></span> <span data-ttu-id="e6ff3-211">使用此原則，當您在原則中指定的條件滿足時，將自動套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-211">With this policy, a retention label is automatically applied when conditions that you specify in the policy are met.</span></span>

#### <a name="retention-label-policies-and-locations"></a><span data-ttu-id="e6ff3-212">保留標籤原則與位置</span><span class="sxs-lookup"><span data-stu-id="e6ff3-212">Retention label policies and locations</span></span>

<span data-ttu-id="e6ff3-213">可以將不同類型的保留標籤發佈到不同的位置，視保留標籤的功能而定。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-213">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
| <span data-ttu-id="e6ff3-214">如果保留標籤是...</span><span class="sxs-lookup"><span data-stu-id="e6ff3-214">If the retention label is…</span></span> | <span data-ttu-id="e6ff3-215">標籤原則可套用至…</span><span class="sxs-lookup"><span data-stu-id="e6ff3-215">Then the label policy can be applied to…</span></span> |
|:-----|:-----|
|<span data-ttu-id="e6ff3-216">已發佈給系統管理員和使用者</span><span class="sxs-lookup"><span data-stu-id="e6ff3-216">Published to admins and end users</span></span>  <br/> |<span data-ttu-id="e6ff3-217">Exchange、SharePoint、OneDrive、Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="e6ff3-217">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
|<span data-ttu-id="e6ff3-218">根據敏感資訊類型或可訓練分類器而自動套用</span><span class="sxs-lookup"><span data-stu-id="e6ff3-218">Auto-applied based on sensitive information types or trainable classifiers</span></span>  <br/> |<span data-ttu-id="e6ff3-219">Exchange (僅限所有信箱)、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="e6ff3-219">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="e6ff3-220">根據查詢而自動套用</span><span class="sxs-lookup"><span data-stu-id="e6ff3-220">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="e6ff3-221">Exchange、SharePoint、OneDrive、Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="e6ff3-221">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
   
<span data-ttu-id="e6ff3-222">在 Exchange 中，自動套用的保留標籤僅套用至新傳送的郵件 (傳輸中的資料)，而非目前在信箱中的所有郵件 (待用資料)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-222">In Exchange, retention labels that you auto-apply are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="e6ff3-223">此外，您只能在所有信箱中為敏感性資訊類型和可訓練分類器來自動套用保留標籤功能，但無法選取特定信箱。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-223">Also, auto-apply retention labels for sensitive information types and trainable classifiers apply to all mailboxes; you can't select specific mailboxes.</span></span>
  
<span data-ttu-id="e6ff3-224">Exchange 公用資料夾、Skype、Teams 和 Yammer 訊息不支援保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-224">Exchange public folders, Skype, Teams and Yammer messages do not support retention labels.</span></span> <span data-ttu-id="e6ff3-225">若要保留或刪除這些位置中的內容，請改用保留原則。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-225">To retain and delete contain from these locations, use retention policies instead.</span></span>

#### <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="e6ff3-226">一次只能有一個保留標籤</span><span class="sxs-lookup"><span data-stu-id="e6ff3-226">Only one retention label at a time</span></span>

<span data-ttu-id="e6ff3-227">電子郵件或文件等內容一次只能套用一個保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-227">An email or document can have only a single retention label applied to it at a time.</span></span> <span data-ttu-id="e6ff3-228">保留標籤可以由使用者或管理員[手動](create-apply-retention-labels.md#manually-apply-retention-labels)套用，也可以使用以下任一方法自動套用：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-228">A retention label can be applied [manually](create-apply-retention-labels.md#manually-apply-retention-labels) by an end user or admin, or automatically by using any of the following methods:</span></span>

- [<span data-ttu-id="e6ff3-229">自動套用標籤原則</span><span class="sxs-lookup"><span data-stu-id="e6ff3-229">Auto-apply label policy</span></span>](apply-retention-labels-automatically.md)
- [<span data-ttu-id="e6ff3-230">SharePoint Syntex 中的文件瞭解模型</span><span class="sxs-lookup"><span data-stu-id="e6ff3-230">Document understanding model for SharePoint Syntex</span></span>](https://docs.microsoft.com/microsoft-365/contentunderstanding/apply-a-retention-label-to-a-model)
- <span data-ttu-id="e6ff3-231">[SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) 或 [Outlook 的預設標籤](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="e6ff3-231">[Default label for SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) or [Outlook](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>
- [<span data-ttu-id="e6ff3-232">Outlook 規則</span><span class="sxs-lookup"><span data-stu-id="e6ff3-232">Outlook rules</span></span>](create-apply-retention-labels.md#automatically-applying-a-retention-label-to-email-by-using-rules)

<span data-ttu-id="e6ff3-233">對於標準保留標籤 (它們不會將項目標記為[記錄或監管記錄](records-management.md#records))：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-233">For standard retention labels (they don't mark items as a [record or regulatory record](records-management.md#records)):</span></span>

- <span data-ttu-id="e6ff3-234">系統管理員和使用者可以手動變更或移除套用於內容的現有保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-234">Admins and end users can manually change or remove an existing retention label that's applied on content.</span></span> 

- <span data-ttu-id="e6ff3-235">當內容已套用保留標籤時，現有標籤不會自動移除或替換為另一個保留標籤，但有一個可能的例外：現有標籤已作為預設標籤套用。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-235">When content already has a retention label applied, the existing label won't be automatically removed or replaced by another retention label with one possible exception: The existing label was applied as a default label.</span></span>
    
    <span data-ttu-id="e6ff3-236">有關使用預設標籤套用標籤行為的詳細資訊，請執行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-236">For more information about the label behavior when it's applied by using a default label:</span></span>
    - <span data-ttu-id="e6ff3-237">SharePoint 的預設標籤：[對 SharePoint 使用預設標籤時的標籤行為](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span><span class="sxs-lookup"><span data-stu-id="e6ff3-237">Default label for SharePoint: [Label behavior when you use a default label for SharePoint](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span></span>
    - <span data-ttu-id="e6ff3-238">Outlook 的預設標籤：[將預設保留標籤套用於 Outlook 資料夾](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="e6ff3-238">Default label for Outlook: [Applying a default retention label to an Outlook folder](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>

- <span data-ttu-id="e6ff3-239">如果有多個自動套用標籤原則可以套用保留標籤，並且內容滿足多個原則的條件，則套用最舊的自動套用標籤原則 (按建立日期) 的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-239">If there are multiple auto-apply label policies that could apply a retention label, and content meets the conditions of multiple policies, the retention label for the oldest auto-apply label policy (by date created) is applied.</span></span>

<span data-ttu-id="e6ff3-240">當保留標籤將項目標記為記錄或監管記錄時，這些標籤不會自動變更。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-240">When retention labels mark items as a record or a regulatory record, these labels are never automatically changed.</span></span> <span data-ttu-id="e6ff3-241">只有容器的管理員才能手動變更或移除將項目標記為記錄而不是監管記錄的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-241">Only admins for the container can manually change or remove retention labels that mark items as a record, but not regulatory records.</span></span> <span data-ttu-id="e6ff3-242">如需詳細資訊，請參閱 [比較允許或封鎖動作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-242">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

#### <a name="monitoring-retention-labels"></a><span data-ttu-id="e6ff3-243">監視保留標籤</span><span class="sxs-lookup"><span data-stu-id="e6ff3-243">Monitoring retention labels</span></span>

<span data-ttu-id="e6ff3-244">在 Microsoft 365 合規性中心中，使用 **資料分類** > **概觀** 來監視保留標籤在租用戶中的使用方式，並識別標籤項目的位置。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-244">From the Microsoft 365 compliance center, use **Data classification** > **Overview** to monitor how your retention labels are being used in your tenant, and identify where your labeled items are located.</span></span> <span data-ttu-id="e6ff3-245">如需詳細資訊 (包括重要先決條件)，請參閱[了解您的資料 - 資料分類概觀](data-classification-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-245">For more information, including important prerequisites, see [Know your data - data classification overview](data-classification-overview.md).</span></span>

<span data-ttu-id="e6ff3-246">然後您可以使用[內容總管](data-classification-content-explorer.md)和[活動總管](data-classification-activity-explorer.md)深入探討詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-246">You can then drill down into details by using [content explorer](data-classification-content-explorer.md) and [activity explorer](data-classification-activity-explorer.md).</span></span>

> [!TIP]
><span data-ttu-id="e6ff3-247">請考慮使用一些其他的資料分類深入解析 (例如可訓練分類器和敏感性資訊類型)，協助您識別可能需要保留或刪除的內容，或管理記錄。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-247">Consider using some of the other data classification insights, such as trainable classifiers and sensitive info types, to help you identify content that you might need to retain or delete, or manage as records.</span></span>

<span data-ttu-id="e6ff3-248">Office 365 安全性與合規性中心具有來自 **資訊控管** > **儀表板** 的保留標籤同等概觀資訊，以及來自 **資訊控管** > **標籤活動總管** 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-248">The Office 365 Security & Compliance Center has the equivalent overview information for retention labels from **Information governance** > **Dashboard**, and more detailed information from **Information governance** > **Label activity explorer**.</span></span> <span data-ttu-id="e6ff3-249">如需從此舊版系統管理中心監視保留標籤的詳細資訊，請參閱下列文件：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-249">For more information about monitoring retention labels from this older admin center, see the following documentation:</span></span>
- [<span data-ttu-id="e6ff3-250">檢視資料控管報告</span><span class="sxs-lookup"><span data-stu-id="e6ff3-250">View the data governance reports</span></span>](view-the-data-governance-reports.md)
- <span data-ttu-id="e6ff3-251">[開始使用資料分類](data-classification-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-251">[Get started with data classification](data-classification-overview.md).</span></span>
- [<span data-ttu-id="e6ff3-252">檢視文件的標籤活動</span><span class="sxs-lookup"><span data-stu-id="e6ff3-252">View label activity for documents</span></span>](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a><span data-ttu-id="e6ff3-253">使用內容搜尋來尋找具有特定保留標籤的所有內容</span><span class="sxs-lookup"><span data-stu-id="e6ff3-253">Using Content Search to find all content with a specific retention label</span></span>

<span data-ttu-id="e6ff3-254">將保留標籤套用至內容後 (無論是由使用者套用或自動套用)，您可以使用內容搜尋來尋找已套用特定保留標籤的所有項目。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-254">After retention labels are applied to content, either by users or auto-applied, you can use content search to find all items that have a specific retention label applied.</span></span>

<span data-ttu-id="e6ff3-255">當您建立內容搜尋時，請選擇 **[保留標籤]** 條件，然後輸入完整的保留標籤名稱或是部分標籤名稱，再使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-255">When you create a content search, choose the **Retention label** condition, and then enter the complete retention label name or part of the label name and use a wildcard.</span></span> <span data-ttu-id="e6ff3-256">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-256">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![保留標籤條件](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a><span data-ttu-id="e6ff3-258">比較保留原則和保留標籤的功能</span><span class="sxs-lookup"><span data-stu-id="e6ff3-258">Compare capabilities for retention policies and retention labels</span></span>

<span data-ttu-id="e6ff3-259">使用下列表格來協助您判斷是否要根據功能來使用保留原則或保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-259">Use the following table to help you identify whether to use a retention policy or retention label, based on capabilities.</span></span>

|<span data-ttu-id="e6ff3-260">功能</span><span class="sxs-lookup"><span data-stu-id="e6ff3-260">Capability</span></span>|<span data-ttu-id="e6ff3-261">保留原則</span><span class="sxs-lookup"><span data-stu-id="e6ff3-261">Retention policy</span></span> |<span data-ttu-id="e6ff3-262">保留標籤</span><span class="sxs-lookup"><span data-stu-id="e6ff3-262">Retention label</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e6ff3-263">可以保留然後刪除、僅保留或僅刪除的保留設定</span><span class="sxs-lookup"><span data-stu-id="e6ff3-263">Retention settings that can retain and then delete, retain-only, or delete-only</span></span> |<span data-ttu-id="e6ff3-264">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-264">Yes</span></span> |<span data-ttu-id="e6ff3-265">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-265">Yes</span></span> |
|<span data-ttu-id="e6ff3-266">支援的工作負載：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-266">Workloads supported:</span></span> <br /><span data-ttu-id="e6ff3-267">- Exchange</span><span class="sxs-lookup"><span data-stu-id="e6ff3-267">- Exchange</span></span> <br /><span data-ttu-id="e6ff3-268">- SharePoint</span><span class="sxs-lookup"><span data-stu-id="e6ff3-268">- SharePoint</span></span> <br /><span data-ttu-id="e6ff3-269">- OneDrive</span><span class="sxs-lookup"><span data-stu-id="e6ff3-269">- OneDrive</span></span> <br /><span data-ttu-id="e6ff3-270">- Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="e6ff3-270">- Microsoft 365 groups</span></span> <br /><span data-ttu-id="e6ff3-271">- 商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e6ff3-271">- Skype for Business</span></span> <br /><span data-ttu-id="e6ff3-272">- Teams</span><span class="sxs-lookup"><span data-stu-id="e6ff3-272">- Teams</span></span><br /><span data-ttu-id="e6ff3-273">- Yammer</span><span class="sxs-lookup"><span data-stu-id="e6ff3-273">- Yammer</span></span>|<br /> <span data-ttu-id="e6ff3-274">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-274">Yes</span></span> <br /> <span data-ttu-id="e6ff3-275">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-275">Yes</span></span> <br /> <span data-ttu-id="e6ff3-276">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-276">Yes</span></span> <br /> <span data-ttu-id="e6ff3-277">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-277">Yes</span></span> <br /> <span data-ttu-id="e6ff3-278">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-278">Yes</span></span> <br /> <span data-ttu-id="e6ff3-279">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-279">Yes</span></span> <br /> <span data-ttu-id="e6ff3-280">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-280">Yes</span></span> | <br /> <span data-ttu-id="e6ff3-281">是，除了公用資料夾</span><span class="sxs-lookup"><span data-stu-id="e6ff3-281">Yes, except public folders</span></span> <br /> <span data-ttu-id="e6ff3-282">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-282">Yes</span></span> <br /> <span data-ttu-id="e6ff3-283">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-283">Yes</span></span> <br /> <span data-ttu-id="e6ff3-284">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-284">Yes</span></span> <br /> <span data-ttu-id="e6ff3-285">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-285">No</span></span> <br /> <span data-ttu-id="e6ff3-286">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-286">No</span></span> <br /> <span data-ttu-id="e6ff3-287">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-287">No</span></span> |
|<span data-ttu-id="e6ff3-288">自動套用的保留</span><span class="sxs-lookup"><span data-stu-id="e6ff3-288">Retention applied automatically</span></span> | <span data-ttu-id="e6ff3-289">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-289">Yes</span></span> | <span data-ttu-id="e6ff3-290">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-290">Yes</span></span> |
|<span data-ttu-id="e6ff3-291">根據條件套用保留</span><span class="sxs-lookup"><span data-stu-id="e6ff3-291">Retention applied based on conditions</span></span> <br /> <span data-ttu-id="e6ff3-292">- 敏感資訊類型、KQL 查詢和關鍵字、可訓練分類器</span><span class="sxs-lookup"><span data-stu-id="e6ff3-292">- sensitive info types, KQL queries and keywords, trainable classifiers</span></span>| <span data-ttu-id="e6ff3-293">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-293">No</span></span> | <span data-ttu-id="e6ff3-294">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-294">Yes</span></span> |
|<span data-ttu-id="e6ff3-295">手動套用的保留</span><span class="sxs-lookup"><span data-stu-id="e6ff3-295">Retention applied manually</span></span> | <span data-ttu-id="e6ff3-296">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-296">No</span></span> | <span data-ttu-id="e6ff3-297">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-297">Yes</span></span> |
|<span data-ttu-id="e6ff3-298">使用者的 UI 目前狀態</span><span class="sxs-lookup"><span data-stu-id="e6ff3-298">UI presence for end users</span></span> | <span data-ttu-id="e6ff3-299">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-299">No</span></span> | <span data-ttu-id="e6ff3-300">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-300">Yes</span></span> |
|<span data-ttu-id="e6ff3-301">如果內容已移動，則會持續存在</span><span class="sxs-lookup"><span data-stu-id="e6ff3-301">Persists if the content is moved</span></span> | <span data-ttu-id="e6ff3-302">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-302">No</span></span> | <span data-ttu-id="e6ff3-303">是，在您的 Microsoft 365 租用戶中</span><span class="sxs-lookup"><span data-stu-id="e6ff3-303">Yes, within your Microsoft 365 tenant</span></span> |
|<span data-ttu-id="e6ff3-304">將項目宣告為記錄</span><span class="sxs-lookup"><span data-stu-id="e6ff3-304">Declare item as a record</span></span>| <span data-ttu-id="e6ff3-305">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-305">No</span></span> | <span data-ttu-id="e6ff3-306">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-306">Yes</span></span> |
|<span data-ttu-id="e6ff3-307">在加上標籤起或根據事件來開始保留期間</span><span class="sxs-lookup"><span data-stu-id="e6ff3-307">Start the retention period when labeled or based on an event</span></span> | <span data-ttu-id="e6ff3-308">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-308">No</span></span> | <span data-ttu-id="e6ff3-309">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-309">Yes</span></span> |
|<span data-ttu-id="e6ff3-310">處置檢閱</span><span class="sxs-lookup"><span data-stu-id="e6ff3-310">Disposition review</span></span> | <span data-ttu-id="e6ff3-311">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-311">No</span></span>| <span data-ttu-id="e6ff3-312">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-312">Yes</span></span> |
|<span data-ttu-id="e6ff3-313">最高 7 年的處置證明</span><span class="sxs-lookup"><span data-stu-id="e6ff3-313">Proof of disposition for up to 7 years</span></span> | <span data-ttu-id="e6ff3-314">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-314">No</span></span> |<span data-ttu-id="e6ff3-315">是，當物料宣告為記錄時</span><span class="sxs-lookup"><span data-stu-id="e6ff3-315">Yes, when item is declared a record</span></span>|
|<span data-ttu-id="e6ff3-316">稽核系統管理員活動</span><span class="sxs-lookup"><span data-stu-id="e6ff3-316">Audit admin activities</span></span>| <span data-ttu-id="e6ff3-317">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-317">Yes</span></span> | <span data-ttu-id="e6ff3-318">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-318">Yes</span></span>|
|<span data-ttu-id="e6ff3-319">識別要保留的項目：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-319">Identify items subject to retention:</span></span> <br /> <span data-ttu-id="e6ff3-320">- 內容搜尋</span><span class="sxs-lookup"><span data-stu-id="e6ff3-320">- Content Search</span></span> <br /> <span data-ttu-id="e6ff3-321">- 資料分類頁面、內容總管，活動總管</span><span class="sxs-lookup"><span data-stu-id="e6ff3-321">- Data classification page, content explorer, activity explorer</span></span> | <br /> <span data-ttu-id="e6ff3-322">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-322">No</span></span> <br /> <span data-ttu-id="e6ff3-323">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-323">No</span></span> | <br /> <span data-ttu-id="e6ff3-324">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-324">Yes</span></span> <br /> <span data-ttu-id="e6ff3-325">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-325">Yes</span></span>|

<span data-ttu-id="e6ff3-326">請注意，您可以使用保留原則和保留標籤做為補充保留方法。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-326">Note that you can use both retention policies and retention labels as complementary retention methods.</span></span> <span data-ttu-id="e6ff3-327">例如：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-327">For example:</span></span>

1. <span data-ttu-id="e6ff3-328">您建立並設定將在內容上次修改後五年自動刪除內容的保留原則，並將該原則套用於所有 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-328">You create and configure a retention policy that automatically deletes content five years after it's last modified, and apply the policy to all OneDrive accounts.</span></span>

2. <span data-ttu-id="e6ff3-329">您建立並設定永久保留內容的保留標籤，並將其新增至您發佈到所有 OneDrive 帳戶的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-329">You create and configure a retention label that keeps content forever and add this to a label policy that you publish to all OneDrive accounts.</span></span> <span data-ttu-id="e6ff3-330">您向使用者說明如何手動將此標籤套用於五年後未修改應從自動刪除排除的特定文件。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-330">You explain to users how to manually apply this label to specific documents that should be excluded from automatic deletion if not modified after five years.</span></span>

<span data-ttu-id="e6ff3-331">有關保留原則和保留標籤如何搭配，以及如何判斷其合併結果的更多資訊，請參閱下一節解釋保留的原則和其優先順序。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-331">For more information about how retention policies and retention labels work together and how to determine their combined outcome, see the next section that explains the principles of retention and what takes precedence.</span></span>

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="e6ff3-332">原則保留或何者優先</span><span class="sxs-lookup"><span data-stu-id="e6ff3-332">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="e6ff3-333">與保留標籤不同，您可以對同一內容套用多個保留原則。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-333">Unlike retention labels, you can apply more than one retention policy to the same content.</span></span> <span data-ttu-id="e6ff3-334">每個保留原則都可能導致一個保留動作和一個刪除動作。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-334">Each retention policy can result in a retain action and a delete action.</span></span> <span data-ttu-id="e6ff3-335">此外，該項也可以透過保留標籤執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-335">Additionally, that item could also be subject to these actions from a retention label.</span></span>

<span data-ttu-id="e6ff3-336">在這種情況下，當項目可能受到多個可能相互衝突的保留設定的約束時，確定結果的優先順序是什麼？</span><span class="sxs-lookup"><span data-stu-id="e6ff3-336">In this scenario, when items can be subject to multiple retention settings that could conflict with one another, what takes precedence to determine the outcome?</span></span>

<span data-ttu-id="e6ff3-337">結果不是哪一個保留原則或單個保留標籤優先採用，而是項目被保留多長時間 (如果適用) 以及何時删除項目 (如果適用)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-337">The outcome isn't which single retention policy or single retention label wins, but how long an item is retained (if applicable) and when an item is deleted (if applicable).</span></span> <span data-ttu-id="e6ff3-338">這兩個動作是根據套用於項目的所有保留設定獨立計算的。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-338">These two actions are calculated independently from each other, from all the retention settings applied to an item.</span></span>

<span data-ttu-id="e6ff3-339">例如，項目可能受一個為只删除動作設定的保留原則和另一個設定為保留然後删除的保留原則的約束。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-339">For example, an item might be subject to one retention policy that is configured for a delete-only action, and another retention policy that is configured to retain and then delete.</span></span> <span data-ttu-id="e6ff3-340">因此，此項只有一個保留動作和兩個刪除動作。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-340">Consequently, this item has just one retain action but two delete actions.</span></span> <span data-ttu-id="e6ff3-341">保留和删除動作可能會彼此相互衝突，並且這兩個删除動作的日期可能有衝突。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-341">The retention and deletion actions could be in conflict with one another and the two deletion actions might have a conflicting date.</span></span> <span data-ttu-id="e6ff3-342">若要達成結果，您必須套用保留原則。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-342">To work out the outcome, you must apply the principles of retention.</span></span>

<span data-ttu-id="e6ff3-343">在高層級中，您可以確保保留永遠優先於刪除，然後最長的保留期間勝出。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-343">At a high level, you can be assured that retention always takes precedence over deletion, and the longest retention period wins.</span></span> <span data-ttu-id="e6ff3-344">這兩個簡單的規則總是决定項目將被保留多長時間。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-344">These two simple rules always decide how long an item will be retained.</span></span>

<span data-ttu-id="e6ff3-345">决定何時删除項目還有幾個因素，其中包括從保留標籤中删除動作始終優先於從保留原則中删除動作。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-345">There are a few more factors that determine when an item will be deleted, which include the delete action from a retention label always takes precedence over the delete action from a retention policy.</span></span>

<span data-ttu-id="e6ff3-346">使用以下流程來瞭解單個項目的保留和删除結果，其中每個層級從上到下扮演解決衝突的決勝局角色。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-346">Use the following flow to understand the retention and deletion outcomes for a single item, where each level acts as a tie-breaker for conflicts, from top to bottom.</span></span> <span data-ttu-id="e6ff3-347">如果結果是由第一層級決定 (因為沒有更多的衝突)，則無需前進到下一個層級，依此類推。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-347">If the outcome is determined by the first level because there are no further conflicts, there's no need to progress to the next level, and so on.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6ff3-348">如果使用的是保留標籤：在使用此流程確定同一項目上多個保留設定的結果之前，請確保您知道[套用了哪個保留標籤](#only-one-retention-label-at-a-time)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-348">If you are using retention labels: Before using this flow to determine the outcome of multiple retention settings on the same item, make sure you know [which retention label is applied](#only-one-retention-label-at-a-time).</span></span>

![原則保留圖](../media/principles-of-retention.png)
  
<span data-ttu-id="e6ff3-350">四個不同層級的說明：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-350">Explanation for the four different levels:</span></span>
  
1. <span data-ttu-id="e6ff3-351">**保留優先於刪除。**</span><span class="sxs-lookup"><span data-stu-id="e6ff3-351">**Retention wins over deletion.**</span></span> <span data-ttu-id="e6ff3-352">如果內容還具有保留設定，則不會永久删除該內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-352">Content won't be permanently deleted when it also has retention settings to retain it.</span></span>  
    
    <span data-ttu-id="e6ff3-353">範例：電子郵件受 Exchange 保留原則的約束，該原則設定為在三年後删除項目，並且套用了保留標籤，該標籤設定為保留項目五年。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-353">Example: An email message is subject to a retention policy for Exchange that is configured to delete items after three years and it also has a retention label applied that is configured to retain items for five years.</span></span>
    
    <span data-ttu-id="e6ff3-354">此電子郵件保留五年，因為此保留動作優先於删除動作。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-354">The email message is retained for five years because this retention action takes precedence over deletion.</span></span> <span data-ttu-id="e6ff3-355">由於延遲删除動作，電子郵件將在五年時間結束時被删除。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-355">The email message is deleted at the end of the five years because of the deferred delete action.</span></span>

2. <span data-ttu-id="e6ff3-356">**最長保留期間優先。**</span><span class="sxs-lookup"><span data-stu-id="e6ff3-356">**The longest retention period wins.**</span></span> <span data-ttu-id="e6ff3-357">如果內容受制於在不同的期間保留內容的多個保留設定，則該內容將一直保留到最長保留期間結束為止。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-357">If content is subject to multiple retention settings that retain content for different periods of time, the content will be retained until the end of the longest retention period.</span></span>
    
    <span data-ttu-id="e6ff3-358">範例：Marketing SharePoint 網站中的文件受兩個保留原則的約束。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-358">Example: Documents in the Marketing SharePoint site are subject to two retention policies.</span></span> <span data-ttu-id="e6ff3-359">為所有 SharePoint 網站設定了第一個保留原則，以將項目保留五年。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-359">The first retention policy is configured for all SharePoint sites to retain items for five years.</span></span> <span data-ttu-id="e6ff3-360">第二個保留原則是為特定的 SharePoint 網站設定的，以將項目保留十年。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-360">The second retention policy is configured for specific SharePoint sites to retain items for ten years.</span></span>
    
    <span data-ttu-id="e6ff3-361">此 Marketing SharePoint 網站中的文件保留十年，因為這是最長的保留期。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-361">Documents in this Marketing SharePoint site are retained for ten years because that's the longest retention period.</span></span>

3. <span data-ttu-id="e6ff3-362">**明確優先於隱含。**</span><span class="sxs-lookup"><span data-stu-id="e6ff3-362">**Explicit wins over implicit.**</span></span> <span data-ttu-id="e6ff3-363">適用於確定删除項目的時間：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-363">Applicable to determine when items will be deleted:</span></span> 
    
    1. <span data-ttu-id="e6ff3-364">與保留原則相比，保留標籤 (無論套用的是什麼) 提供明確保留，因為保留設定套用於單個項目，而不是從容器隱含分配。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-364">A retention label (however it was applied) provides explicit retention in comparison with retention policies, because the retention settings are applied to an individual item rather than implicitly assigned from a container.</span></span> <span data-ttu-id="e6ff3-365">這意味著從保留標籤執行的删除動作始終優先於任何保留原則中的删除動作。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-365">This means that a delete action from a retention label always takes precedence over a delete action from any retention policy.</span></span>
        
        <span data-ttu-id="e6ff3-366">範例：文件受兩個保留原則的約束，這兩個原則的删除動作分別為 5 年和 10 年，保留標籤的删除動作為 7 年。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-366">Example: A document is subject to two retention policies that have a delete action of five years and ten years respectively, and also a retention label that has a delete action of seven years.</span></span>
        
        <span data-ttu-id="e6ff3-367">文件在七年後被删除，因為從保留標籤中的删除動作優先。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-367">The document is deleted after seven years because the delete action from the retention label takes precedence.</span></span>
    
    2. <span data-ttu-id="e6ff3-368">只有保留原則時：如果某個位置的保留原則的作用域是使用包含設定 (例如 Exchange 電子郵件的特定使用者)，則對於同一位置，保留原則優先於未限定範圍的保留原則。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-368">When you have retention policies only: If a retention policy for a location is scoped to use an include configuration (such as specific users for Exchange email) that retention policy takes precedence over unscoped retention policies for the same location.</span></span>
        
        <span data-ttu-id="e6ff3-369">未限定範圍的保留原則是指在不指定特定實例的情况下選取位置。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-369">An unscoped retention policy is where a location is selected without specifying specific instances.</span></span> <span data-ttu-id="e6ff3-370">例如，**Exchange 電子郵件** 和 **[所有收件人]** 的預設設置都是未限定範圍的保留原則。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-370">For example, **Exchange email** and the default setting of **All recipients** is an unscoped retention policy.</span></span> <span data-ttu-id="e6ff3-371">或者，**SharePoint 網站** 和 **所有網站** 的預設設定。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-371">Or, **SharePoint sites** and the default setting of **All sites**.</span></span> <span data-ttu-id="e6ff3-372">當確定保留原則的作用域時，它們在此層級上具有相同的優先順序。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-372">When retention policies are scoped, they have equal precedence at this level.</span></span>
        
        <span data-ttu-id="e6ff3-373">範例 1：電子郵件受兩個保留原則的約束。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-373">Example 1: An email message is subject to two retention policies.</span></span> <span data-ttu-id="e6ff3-374">第一個保留原則是未限定範圍的，並在 10 年後删除項目。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-374">The first retention policy is unscoped and deletes items after ten years.</span></span> <span data-ttu-id="e6ff3-375">第二個保留原則的範圍是特定郵箱，並在五年後删除項目。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-375">The second retention policy is scoped to specific mailboxes and deletes items after five years.</span></span>
        
        <span data-ttu-id="e6ff3-376">電子郵件在五年後被删除，因為範圍保留原則中的删除動作優先於未限定範圍的保留原則。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-376">The email message is deleted after five years because the deletion action from the scoped retention policy takes precedence over the unscoped retention policy.</span></span>
        
        <span data-ttu-id="e6ff3-377">範例 2：使用者 OneDrive 帳戶中的文件受兩個保留原則的約束。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-377">Example 2: A document in a user's OneDrive account is subject to two retention policies.</span></span> <span data-ttu-id="e6ff3-378">第一個保留原則的範圍是包括此使用者的 OneDrive 帳戶，並在 10 年後執行删除動作。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-378">The first retention policy is scoped to include this user's OneDrive account and has a delete action after 10 years.</span></span> <span data-ttu-id="e6ff3-379">第二個保留原則的範圍是包括此使用者的 OneDrive 帳戶，並在七年後執行删除動作。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-379">The second retention policy is scoped to include this user's OneDrive account and has a delete action after seven years.</span></span>
        
        <span data-ttu-id="e6ff3-380">無法在此層級確定何時删除此文件，因為這兩個保留原則都有範圍。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-380">When this document will be deleted can't be determined at this level because both retention policies are scoped.</span></span>

4. <span data-ttu-id="e6ff3-381">**最短刪除期間優先。**</span><span class="sxs-lookup"><span data-stu-id="e6ff3-381">**The shortest deletion period wins.**</span></span> <span data-ttu-id="e6ff3-382">適用於確定何時從保留原則中删除項目，並且無法從上一層級解析結果：在最短保留期結束時删除內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-382">Applicable to determine when items will be deleted from retention policies and the outcome couldn't be resolved from the previous level: Content is deleted at the end of the shortest retention period.</span></span>
    
    <span data-ttu-id="e6ff3-383">範例：使用者 OneDrive 帳戶中的文件受兩個保留原則的約束。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-383">Example: A document in a user's OneDrive account is subject to two retention policies.</span></span> <span data-ttu-id="e6ff3-384">第一個保留原則的範圍是包括此使用者的 OneDrive 帳戶，並在 10 年後執行删除動作。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-384">The first retention policy is scoped to include this user's OneDrive account and has a delete action after 10 years.</span></span> <span data-ttu-id="e6ff3-385">第二個保留原則的範圍是包括此使用者的 OneDrive 帳戶，並在七年後執行删除動作。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-385">The second retention policy is scoped to include this user's OneDrive account and has a delete action after seven years.</span></span>
    
    <span data-ttu-id="e6ff3-386">此檔案將在七年後删除，因為這是這兩個範圍內保留原則的最短保留期。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-386">This document will be deleted after seven years because that's the shortest retention period for these two scoped retention policies.</span></span>

<span data-ttu-id="e6ff3-387">請注意，受 eDiscovery 保留約束的項目也屬於保留的第一準則；任何保留原則或保留標籤都不能删除它們。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-387">Note that items subject to eDiscovery hold also fall under the first principle of retention; they cannot be deleted by any retention policy or retention label.</span></span> <span data-ttu-id="e6ff3-388">當解除保留後，保留準則繼續適用於他們。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-388">When that hold is released, the principles of retention continue to apply to them.</span></span> <span data-ttu-id="e6ff3-389">例如，它們可能會受到未到期的保留期或延遲的删除動作的影響。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-389">For example, they could then be subject to an unexpired retention period or a deferred delete action.</span></span>

<span data-ttu-id="e6ff3-390">結合保留和删除動作的更複雜的範例：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-390">More complex examples that combine retain and delete actions:</span></span>

1. <span data-ttu-id="e6ff3-391">項目套用了以下保留設定：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-391">An item has the following retention settings applied to it:</span></span>
    
    - <span data-ttu-id="e6ff3-392">僅在五年後删除的保留原則</span><span class="sxs-lookup"><span data-stu-id="e6ff3-392">A retention policy for delete-only after five years</span></span>
    - <span data-ttu-id="e6ff3-393">保留三年然後删除的保留原則</span><span class="sxs-lookup"><span data-stu-id="e6ff3-393">A retention policy that retains for three years and then deletes</span></span>
    - <span data-ttu-id="e6ff3-394">只保留七年的保留標籤</span><span class="sxs-lookup"><span data-stu-id="e6ff3-394">A retention label that retains-only for seven years</span></span>
    
    <span data-ttu-id="e6ff3-395">**結果**：該項目保留七年，因為保留優先於删除，七年是最長的保留期。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-395">**Outcome**: The item is retained for seven years because retention takes precedence over deletion and seven years is the longest retention period.</span></span> <span data-ttu-id="e6ff3-396">在保留期結束時，由於保留原則中的删除動作在保留項目時被延后，因此將删除該項目。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-396">At the end of this retention period, the item is deleted because of the delete action from the retention policies that was deferred while the item was retained.</span></span>
    
    <span data-ttu-id="e6ff3-397">雖然這兩個保留原則的删除動作的日期不同，但可以删除的項目最早是在最長保留期結束時，而該日期比這兩種刪除日期更長。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-397">Although the two retention policies have different dates for the delete actions, the earliest the item can be deleted is at the end of the longest retention period, which is longer than both deletion dates.</span></span> <span data-ttu-id="e6ff3-398">在此範例中，刪除日期沒有發生任何衝突需要解決，因此所有的衝突都會由第二層級解決。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-398">In this example, there is no conflict to resolve for the deletion dates so all conflicts are resolved by the second level.</span></span>

2.  <span data-ttu-id="e6ff3-399">項目套用了以下保留設定：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-399">An item has the following retention settings applied to it:</span></span>
    
    - <span data-ttu-id="e6ff3-400">一種未限定範圍的保留原則，僅在 10 年後删除</span><span class="sxs-lookup"><span data-stu-id="e6ff3-400">An unscoped retention policy that deletes-only after ten years</span></span>
    - <span data-ttu-id="e6ff3-401">保留五年，然後删除的限定範圍的保留原則</span><span class="sxs-lookup"><span data-stu-id="e6ff3-401">A scoped retention policy that retains for five years and then deletes</span></span>
    - <span data-ttu-id="e6ff3-402">保留三年然後删除的保留標籤</span><span class="sxs-lookup"><span data-stu-id="e6ff3-402">A retention label that retains for three years and then deletes</span></span>
    
    <span data-ttu-id="e6ff3-403">**結果**：該項目保留五年，因為這是最長的保留期。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-403">**Outcome**: The item is retained for five years because that's the longest retention period.</span></span> <span data-ttu-id="e6ff3-404">在該保留期結束時，該項目將被删除，因為在保留該項目的同時，保留標籤的三年后删除動作被延遲。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-404">At the end of that retention period, the item is deleted because of the delete action of three years from the retention label that was deferred while the item was retained.</span></span> <span data-ttu-id="e6ff3-405">保留標籤中的删除優先於從所有保留原則中的删除。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-405">Deletion from retention labels takes precedence over deletion from all retention policies.</span></span> <span data-ttu-id="e6ff3-406">在此範例中，所有衝突都會由第三層處理解決。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-406">In this example, all conflicts are resolved by the third level.</span></span>

## <a name="use-preservation-lock-to-restrict-changes-to-policies"></a><span data-ttu-id="e6ff3-407">使用「保留鎖定」來限制原則變更</span><span class="sxs-lookup"><span data-stu-id="e6ff3-407">Use Preservation Lock to restrict changes to policies</span></span>

<span data-ttu-id="e6ff3-408">有些組織可能需要遵守由控管機構定義的規則，例如證券交易委員會 (SEC) 規定 17a-4，要求在保留原則開啟之後，不能關閉或執行較不嚴格的限制。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-408">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a policy for retention is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="e6ff3-409">「保留鎖定」可確保您的組織能夠符合這類法規需求，因為它會鎖定保留原則或保留標籤原則，使得沒有任何人 (包括系統管理員) 可以關閉原則、刪除原則或降低限制。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-409">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy or retention label policy so that no one—including an administrator—can turn off the policy, delete the policy, or make it less restrictive.</span></span>
  
<span data-ttu-id="e6ff3-410">建立保留原則或保留標籤原則之後，您可以套用「保留鎖定」。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-410">You apply Preservation Lock after the retention policy or retention label policy is created.</span></span> <span data-ttu-id="e6ff3-411">如需更多資訊和指示，請參閲[使用保留鎖定來限制變更保留原則和保留標籤原則](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-411">For more information and instructions, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="releasing-a-policy-for-retention"></a><span data-ttu-id="e6ff3-412">發佈保留原則</span><span class="sxs-lookup"><span data-stu-id="e6ff3-412">Releasing a policy for retention</span></span>

<span data-ttu-id="e6ff3-413">如果您的保留原則沒有保留鎖定，您可以隨時刪除您的原則，以便有效地關閉先前套用的保留設定。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-413">Providing your policies for retention don't have a Preservation Lock, you can delete your policies at any time, which effectively turns off the previously applied retention settings.</span></span> <span data-ttu-id="e6ff3-414">您也可以維持原有的保留原則，但將位置狀態變更為 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-414">You can also keep the policy but change the location status to off.</span></span>
 
<span data-ttu-id="e6ff3-415">當您這麼做時，保留在文件保留庫中的任何 SharePoint 或 OneDrive 的內容不會立即永久被刪除。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-415">When you do either of these actions, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="e6ff3-416">相反地，為了防止意外的資料遺失，我們有 30 天的寬限期，在這期間，保留文件庫中不會發生該原則的內容到期，因此，如有需要，您可以在這裡還原任何內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-416">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="e6ff3-417">此外，您無法在寬限期期間手動刪除此內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-417">Additionally, you can't manually delete this content during the grace period.</span></span>

<span data-ttu-id="e6ff3-418">您可以在寬限期期間將位置狀態變更為 [開啟]，這麼一來，該原則的內容將不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-418">You can change the location status back to on during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="e6ff3-419">SharePoint 和 OneDrive 中的此 30 天寬限期與 Exchange 中的 30 天延遲保留對應。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-419">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="e6ff3-420">如需詳細資訊，請參閱[管理延遲保留信箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-420">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

## <a name="auditing-retention-configuration"></a><span data-ttu-id="e6ff3-421">稽核保留設定</span><span class="sxs-lookup"><span data-stu-id="e6ff3-421">Auditing retention configuration</span></span>

<span data-ttu-id="e6ff3-422">[啟用稽核功能](turn-audit-log-search-on-or-off.md)後，系統會將保留原則和保留標籤的系統管理員動作儲存至稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-422">Administrator actions for retention policies and retention labels are saved to the audit log when [auditing is enabled](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="e6ff3-423">例如，建立、設定或刪除保留原則或標籤後，系統會建立稽核事件。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-423">For example, an audit event is created when a retention policy or label is created, configured, or deleted.</span></span> <span data-ttu-id="e6ff3-424">如需完整清單，請參閱[保留原則和保留標籤活動](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-424">For the full list, see [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).</span></span>

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a><span data-ttu-id="e6ff3-425">保留原則和保留標籤的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e6ff3-425">PowerShell cmdlets for retention policies and retention labels</span></span>

<span data-ttu-id="e6ff3-426">若要使用保留 Cmdlet，您必須先[連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-426">To use the retention cmdlets, you must first [connect to the Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="e6ff3-427">然後使用以下任一 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-427">Then, use any of the following cmdlets:</span></span>

- [<span data-ttu-id="e6ff3-428">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="e6ff3-428">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [<span data-ttu-id="e6ff3-429">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="e6ff3-429">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [<span data-ttu-id="e6ff3-430">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="e6ff3-430">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [<span data-ttu-id="e6ff3-431">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="e6ff3-431">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [<span data-ttu-id="e6ff3-432">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="e6ff3-432">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [<span data-ttu-id="e6ff3-433">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="e6ff3-433">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [<span data-ttu-id="e6ff3-434">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="e6ff3-434">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [<span data-ttu-id="e6ff3-435">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="e6ff3-435">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [<span data-ttu-id="e6ff3-436">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="e6ff3-436">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [<span data-ttu-id="e6ff3-437">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="e6ff3-437">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [<span data-ttu-id="e6ff3-438">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="e6ff3-438">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [<span data-ttu-id="e6ff3-439">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="e6ff3-439">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [<span data-ttu-id="e6ff3-440">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="e6ff3-440">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [<span data-ttu-id="e6ff3-441">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="e6ff3-441">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a><span data-ttu-id="e6ff3-442">何時使用保留原則和保留標籤或電子文件探索保留？</span><span class="sxs-lookup"><span data-stu-id="e6ff3-442">When to use retention policies and retention labels or eDiscovery holds</span></span>

<span data-ttu-id="e6ff3-443">雖然您使用保留設定和[電子文件探索案例所建立的保留](create-ediscovery-holds.md)都可以防止資料永久刪除，但它們是為不同情況而設計的。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-443">Although retention settings and [holds that you create with an eDiscovery case](create-ediscovery-holds.md) can both prevent data from being permanently deleted, they are designed for different scenarios.</span></span> <span data-ttu-id="e6ff3-444">若要協助您了解差異及決定使用哪個，請使用下列指南：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-444">To help you understand the differences and decide which to use, use the following guidance:</span></span>

- <span data-ttu-id="e6ff3-445">您在 [保留原則] 和 [保留標籤] 中指定的保留設定，是專為長期資訊控管而設計，以保留或刪除符合法規需求的資料。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-445">Retention settings that you specify in retention policies and retention labels are designed for a long-term information governance strategy to retain or delete data for compliance requirements.</span></span> <span data-ttu-id="e6ff3-446">範圍通常很廣，主要重點是位置和內容，而不是個別使用者。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-446">The scope is usually broad with the main focus being the location and content rather than individual users.</span></span> <span data-ttu-id="e6ff3-447">保留期間的開始和結束是可設定的，可選擇自動刪除內容，而不需要其他系統管理員介入。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-447">The start and end of the retention period is configurable, with the option to automatically delete content without additional administrator intervention.</span></span>

- <span data-ttu-id="e6ff3-448">電子文件探索的保留 (核心電子文件探索或進階電子文件探索案例) 是專為保留資料以供法律調查所設計。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-448">Holds for eDiscovery (either Core eDiscovery or Advanced eDiscovery cases) are designed for a limited duration to preserve data for a legal investigation.</span></span> <span data-ttu-id="e6ff3-449">該範圍是特定的，且重點是已識別使用者所擁有的內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-449">The scope is specific with the focus being content owned by identified users.</span></span> <span data-ttu-id="e6ff3-450">保留期間的開始和結束不會進行設定，但與個別系統管理員的動作相關，沒有選項可在保留解除時自動刪除內容。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-450">The start and end of the preservation period isn't configurable but dependent on individual administrator actions, without an option to automatically delete content when the hold is released.</span></span>

<span data-ttu-id="e6ff3-451">比較保留與電子文件探索保留的摘要：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-451">Summary to compare retention with holds:</span></span>

|<span data-ttu-id="e6ff3-452">考量事項</span><span class="sxs-lookup"><span data-stu-id="e6ff3-452">Consideration</span></span>|<span data-ttu-id="e6ff3-453">保留</span><span class="sxs-lookup"><span data-stu-id="e6ff3-453">Retention</span></span> |<span data-ttu-id="e6ff3-454">電子文件探索保留</span><span class="sxs-lookup"><span data-stu-id="e6ff3-454">eDiscovery holds</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e6ff3-455">商務需求：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-455">Business need:</span></span> |<span data-ttu-id="e6ff3-456">合規性</span><span class="sxs-lookup"><span data-stu-id="e6ff3-456">Compliance</span></span> |<span data-ttu-id="e6ff3-457">法律資訊</span><span class="sxs-lookup"><span data-stu-id="e6ff3-457">Legal</span></span> |
|<span data-ttu-id="e6ff3-458">時間範圍：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-458">Time scope:</span></span> |<span data-ttu-id="e6ff3-459">長期</span><span class="sxs-lookup"><span data-stu-id="e6ff3-459">Long-term</span></span> |<span data-ttu-id="e6ff3-460">短期</span><span class="sxs-lookup"><span data-stu-id="e6ff3-460">Short-term</span></span> |
|<span data-ttu-id="e6ff3-461">焦點：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-461">Focus:</span></span> |<span data-ttu-id="e6ff3-462">廣泛的、內容型</span><span class="sxs-lookup"><span data-stu-id="e6ff3-462">Broad, content-based</span></span> |<span data-ttu-id="e6ff3-463">特定的、使用者型</span><span class="sxs-lookup"><span data-stu-id="e6ff3-463">Specific, user-based</span></span> |
|<span data-ttu-id="e6ff3-464">開始和結束日期可設定：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-464">Start and end date configurable:</span></span> |<span data-ttu-id="e6ff3-465">是</span><span class="sxs-lookup"><span data-stu-id="e6ff3-465">Yes</span></span> |<span data-ttu-id="e6ff3-466">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-466">No</span></span> |
|<span data-ttu-id="e6ff3-467">內容刪除：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-467">Content deletion:</span></span> |<span data-ttu-id="e6ff3-468">是 (選用)</span><span class="sxs-lookup"><span data-stu-id="e6ff3-468">Yes (optional)</span></span> |<span data-ttu-id="e6ff3-469">否</span><span class="sxs-lookup"><span data-stu-id="e6ff3-469">No</span></span> |
|<span data-ttu-id="e6ff3-470">系統管理開銷：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-470">Administrative overheads:</span></span> |<span data-ttu-id="e6ff3-471">低</span><span class="sxs-lookup"><span data-stu-id="e6ff3-471">Low</span></span> |<span data-ttu-id="e6ff3-472">高</span><span class="sxs-lookup"><span data-stu-id="e6ff3-472">High</span></span> |

<span data-ttu-id="e6ff3-473">如果內容同時受制於保留設定和電子文件探索保留，則電子文件探索保留的內容保留永遠優先。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-473">If content is subject to both retention settings and an eDiscovery hold, preserving content for the eDiscovery hold always takes precedence.</span></span> <span data-ttu-id="e6ff3-474">如此一來，[保留的原則](#the-principles-of-retention-or-what-takes-precedence)會擴充至電子文件探索保留，因為系統會在管理員手動解除保留之前，將資料保留。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-474">In this way, the [principles of retention](#the-principles-of-retention-or-what-takes-precedence) expand to eDiscovery holds because they preserve data until an administrator manually releases the hold.</span></span> <span data-ttu-id="e6ff3-475">不過，儘管這個優先順序，請不要將電子文件探索保留用於長期資訊控管。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-475">However, despite this precedence, don't use eDiscovery holds for long-term information governance.</span></span> <span data-ttu-id="e6ff3-476">如果您擔心自動刪除資料，您可以設定保留設定以永遠保留項目，或對保留標籤使用[處置評審](disposition.md#disposition-reviews)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-476">If you are concerned about automatic deletion of data, you can configure retention settings to retain items forever, or use [disposition review](disposition.md#disposition-reviews) with retention labels.</span></span>

<span data-ttu-id="e6ff3-477">如果您使用舊版電子文件探索工具來保留資料，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-477">If you are using older eDiscovery tools to preserve data, see the following resources:</span></span>

- <span data-ttu-id="e6ff3-478">Exchange：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-478">Exchange:</span></span> 
    - [<span data-ttu-id="e6ff3-479">就地保留與訴訟資料暫留</span><span class="sxs-lookup"><span data-stu-id="e6ff3-479">In-Place Hold and Litigation Hold</span></span>](https://go.microsoft.com/fwlink/?linkid=846124)
    - <span data-ttu-id="e6ff3-480">[如何找出位於 Exchange Online 信箱的保留類型](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox) (英文)</span><span class="sxs-lookup"><span data-stu-id="e6ff3-480">[How to identify the type of hold placed on an Exchange Online mailbox](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox)</span></span>

- <span data-ttu-id="e6ff3-481">SharePoint 和 OneDrive：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-481">SharePoint and OneDrive:</span></span> 
    - <span data-ttu-id="e6ff3-482">[在電子文件探索中心將內容新增至案例及保留來源](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (英文)</span><span class="sxs-lookup"><span data-stu-id="e6ff3-482">[Add content to a case and place sources on hold in the eDiscovery Center](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)</span></span>

- [<span data-ttu-id="e6ff3-483">舊版電子文件探索工具淘汰</span><span class="sxs-lookup"><span data-stu-id="e6ff3-483">Retirement of legacy eDiscovery tools</span></span>](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a><span data-ttu-id="e6ff3-484">請使用保留原則和保留標籤，而非舊版的功能</span><span class="sxs-lookup"><span data-stu-id="e6ff3-484">Use retention policies and retention labels instead of older features</span></span>

<span data-ttu-id="e6ff3-485">如果您必要在 Microsoft 365 中預先主動保留或刪除內容，我們建議您使用保留原則和保留標籤，而非以下較舊的功能。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-485">If you need to proactively retain or delete content in Microsoft 365 for information governance, we recommend that you use retention policies and retention labels instead of the following older features.</span></span>

<span data-ttu-id="e6ff3-486">如果您目前使用這些較舊的功能，這些功能會隨著保留原則和保留標籤繼續運作。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-486">If you currently use these older features, they will continue to work side-by-side with retention policies and retention labels.</span></span> <span data-ttu-id="e6ff3-487">不過，建議您今後改為使用保留原則和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-487">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="e6ff3-488">它們提供單一機制來集中管理 Microsoft 365 內容的保留與刪除。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-488">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="e6ff3-489">**來自 Exchange Online 的舊版功能：**</span><span class="sxs-lookup"><span data-stu-id="e6ff3-489">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="e6ff3-490">[保留標記和保留原則](https://go.microsoft.com/fwlink/?linkid=846125)，又稱為[通訊記錄管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="e6ff3-490">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>

<span data-ttu-id="e6ff3-491">**來自 SharePoint 和 OneDrive 的舊版功能：**</span><span class="sxs-lookup"><span data-stu-id="e6ff3-491">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="e6ff3-492">[文件刪除原則](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="e6ff3-492">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="e6ff3-493">[設定就地記錄管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (僅保留)</span><span class="sxs-lookup"><span data-stu-id="e6ff3-493">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="e6ff3-494">[網站關閉及刪除的使用原則](https://support.microsoft.com/zh-TW/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="e6ff3-494">[Use policies for site closure and deletion](https://support.microsoft.com/zh-TW/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="e6ff3-495">[資訊管理原則](intro-to-info-mgmt-policies.md) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="e6ff3-495">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="e6ff3-496">如果您已設定 SharePoint 網站的內容類型原則或資訊管理原則，以保留清單或文件庫的內容，當保留原則生效時，會忽略這些原則。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-496">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 

## <a name="related-information"></a><span data-ttu-id="e6ff3-497">相關資訊</span><span class="sxs-lookup"><span data-stu-id="e6ff3-497">Related information</span></span>

- [<span data-ttu-id="e6ff3-498">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="e6ff3-498">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="e6ff3-499">Microsoft Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="e6ff3-499">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="e6ff3-500">協助您符合資訊管理與記錄管理法規需求的資源</span><span class="sxs-lookup"><span data-stu-id="e6ff3-500">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)

## <a name="configuration-guidance"></a><span data-ttu-id="e6ff3-501">配置指導方針</span><span class="sxs-lookup"><span data-stu-id="e6ff3-501">Configuration guidance</span></span>

<span data-ttu-id="e6ff3-502">如果您已準備好建立保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e6ff3-502">If you are ready to create retention policies, see [Create and configure retention policies](create-retention-policies.md).</span></span>

<span data-ttu-id="e6ff3-503">若要建立及套用保留標籤：</span><span class="sxs-lookup"><span data-stu-id="e6ff3-503">To create and apply retention labels:</span></span>
- [<span data-ttu-id="e6ff3-504">建立保留標籤，並在應用程式中使用這些標籤</span><span class="sxs-lookup"><span data-stu-id="e6ff3-504">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="e6ff3-505">自動將保留標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="e6ff3-505">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

