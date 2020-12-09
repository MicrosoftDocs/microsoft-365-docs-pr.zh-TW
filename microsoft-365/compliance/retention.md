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
ms.openlocfilehash: e2833d966fb8a1fcc15cbeb02b781d9c0325b9c1
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519374"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a><span data-ttu-id="85f1a-103">了解保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="85f1a-103">Learn about retention policies and retention labels</span></span>

><span data-ttu-id="85f1a-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="85f1a-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="85f1a-p101">對大多數組織來說，其資料 (電子郵件、文件、即時訊息等) 的數量和複雜性日益增加。有效管理或控管此資訊至關重要，因為您需要：</span><span class="sxs-lookup"><span data-stu-id="85f1a-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="85f1a-107">**主動遵守產業規範和內部原則**，因此您需要將某些內容至少保留一段時間，例如，Sarbanes-Oxley 法案可能會要求您將某些類型的內容保留七年。</span><span class="sxs-lookup"><span data-stu-id="85f1a-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 

- <span data-ttu-id="85f1a-108">**降低發生訴訟或安全性漏洞的風險**，方法為永久刪除您不再需要保留的舊內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="85f1a-109">**協助貴組織有效分享知識並提高靈活度**，方法為確保使用者只使用目前和相關的內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="85f1a-110">您設定的保留設定可協助您實現所有目標。</span><span class="sxs-lookup"><span data-stu-id="85f1a-110">Retention settings that you configure can help you achieve all these goals.</span></span> <span data-ttu-id="85f1a-111">管理內容通常需要以下兩個動作：</span><span class="sxs-lookup"><span data-stu-id="85f1a-111">Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="85f1a-112">**保留** 內容，以便無法在保留期間結束之前將其永久刪除。</span><span class="sxs-lookup"><span data-stu-id="85f1a-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="85f1a-113">在保留期間結束之前，永久 **刪除** 內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    

<span data-ttu-id="85f1a-114">使用這兩個保留動作，您可以設定以下結果的保留設定：</span><span class="sxs-lookup"><span data-stu-id="85f1a-114">With these two retention actions, you can configure retention settings for the following outcomes:</span></span>

- <span data-ttu-id="85f1a-115">僅保留：永久持續保留內容或保留指定的一段時間。</span><span class="sxs-lookup"><span data-stu-id="85f1a-115">Retain-only: Retain content forever or for a specified period of time.</span></span>
- <span data-ttu-id="85f1a-116">僅刪除：指定一段時間後刪除內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-116">Delete-only: Delete content after a specified period of time.</span></span>
- <span data-ttu-id="85f1a-117">保留並刪除：將內容保留指定的時間，然後將其刪除。</span><span class="sxs-lookup"><span data-stu-id="85f1a-117">Retain and then delete: Retain content for a specified period of time and then delete it.</span></span>

<span data-ttu-id="85f1a-118">這些保留設定可以使用就地內容，從而在您基於合規性原因而必須保留內容時，節省建立和設定額外儲存體的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="85f1a-118">These retention settings work with content in place that saves you the additional overheads of creating and configuring additional storage when you need to retain content for compliance reasons.</span></span> <span data-ttu-id="85f1a-119">此外，您不必執行自訂的程序來複製及同步處理這項資料。</span><span class="sxs-lookup"><span data-stu-id="85f1a-119">In addition, you don't need to implement customized processes to copy and synchronize this data.</span></span>

## <a name="how-retention-settings-work-with-content-in-place"></a><span data-ttu-id="85f1a-120">保留設定如何與就地內容搭配使用</span><span class="sxs-lookup"><span data-stu-id="85f1a-120">How retention settings work with content in place</span></span>

<span data-ttu-id="85f1a-121">當內容有指派保留設定時，該內容會保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="85f1a-121">When content has retention settings assigned to it, that content remains in its original location.</span></span> <span data-ttu-id="85f1a-122">若未發生任何變更，人員可以繼續使用其文件或郵件。</span><span class="sxs-lookup"><span data-stu-id="85f1a-122">People can continue to work with their documents or mail as if nothing's changed.</span></span> <span data-ttu-id="85f1a-123">但如果人員編輯或刪除保留原則中包含的內容，則會自動保留內容複本。</span><span class="sxs-lookup"><span data-stu-id="85f1a-123">But if they edit or delete content that's included in the retention policy, a copy of the content is automatically retained.</span></span>
  
- <span data-ttu-id="85f1a-124">對於 SharePoint 和 OneDrive 網站：複本會保留在 **文件保留庫** 中。</span><span class="sxs-lookup"><span data-stu-id="85f1a-124">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span>

- <span data-ttu-id="85f1a-125">針對 Exchange 信箱：複本會保留在 **[可復原的項目]** 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="85f1a-125">For Exchange mailboxes: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="85f1a-126">針對 Teams 和 Yammer 訊息：複本會保留在名為 **SubstrateHolds** 的隱藏資料夾中，以作為 Exchange [可復原的項目 **]** 資料夾中的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="85f1a-126">For Teams and Yammer messages: The copy is retained in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="85f1a-127">[文件保留庫] 會佔用不受網站儲存空間配額限制的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="85f1a-127">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota.</span></span> <span data-ttu-id="85f1a-128">當您對 SharePoint 和 Microsoft 365 群組使用保留設定時，可能需要增加您的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="85f1a-128">You might need to increase your storage when you use retention settings for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="85f1a-129">大部分的人員無法檢視這些安全的位置和保留的內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-129">These secure locations and the retained content are not visible to most people.</span></span> <span data-ttu-id="85f1a-130">在大部分的情況下，使用者甚至不需要知道其內容受保留設定的限制。</span><span class="sxs-lookup"><span data-stu-id="85f1a-130">In most cases, people do not even need to know that their content is subject to retention settings.</span></span>

<span data-ttu-id="85f1a-131">如需有關保留設定如何配合不同工作負載使用的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="85f1a-131">For more detailed information about how retention settings work for different workloads, see the following articles:</span></span>

- [<span data-ttu-id="85f1a-132">了解 SharePoint 和 OneDrive 的保留功能</span><span class="sxs-lookup"><span data-stu-id="85f1a-132">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="85f1a-133">了解 Microsoft Teams 保留</span><span class="sxs-lookup"><span data-stu-id="85f1a-133">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="85f1a-134">了解 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="85f1a-134">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="85f1a-135">了解 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="85f1a-135">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="85f1a-136">保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="85f1a-136">Retention policies and retention labels</span></span>

<span data-ttu-id="85f1a-137">您可以透過標籤原則同時使用保留原則和保留標籤，以將保留設定指派給內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-137">You can use both retention policies and retention labels with label policies to assign your retention settings to content.</span></span> 

<span data-ttu-id="85f1a-138">使用保留原則為網站或信箱層級的內容指派相同的保留設定，並使用保留標籤來指派項目層級 (資料夾、文件、電子郵件) 的保留設定。</span><span class="sxs-lookup"><span data-stu-id="85f1a-138">Use a retention policy to assign the same retention settings for content at a site or mailbox level, and use a retention label to assign retention settings at an item level (folder, document, email).</span></span>

<span data-ttu-id="85f1a-139">例如，如果 SharePoint 網站中的所有文件都應該保留 5 年，使用保留原則比將相同的保留標籤套用至該網站中所有文件的方法更有效率。</span><span class="sxs-lookup"><span data-stu-id="85f1a-139">For example, if all documents in a SharePoint site should be retained for 5 years, it's more efficient to do this with a retention policy than apply the same retention label to all documents in that site.</span></span> <span data-ttu-id="85f1a-140">不過，如果該網站中的部分文件應保留 5 年，而其他文件保留 10 年，一個保留原則就不夠用。</span><span class="sxs-lookup"><span data-stu-id="85f1a-140">However, if some documents in that site should be retained for 5 years and others retained for 10 years, a retention policy wouldn't be able to do this.</span></span> <span data-ttu-id="85f1a-141">當您必須在項目層級指定保留設定時，請使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-141">When you need to specify retention settings at the item level, use retention labels.</span></span> 

<span data-ttu-id="85f1a-142">不同於保留原則，保留標籤的保留設定會隨著內容移至您 Microsoft 365 租用戶中不同的位置。</span><span class="sxs-lookup"><span data-stu-id="85f1a-142">Unlike retention policies, retention settings from retention labels travel with the content if it’s moved to a different location within your Microsoft 365 tenant.</span></span> <span data-ttu-id="85f1a-143">此外，保留標籤具有以下保留原則不支援的功能：</span><span class="sxs-lookup"><span data-stu-id="85f1a-143">In addition, retention labels have the following capabilities that retention policies don't support:</span></span> 
 
- <span data-ttu-id="85f1a-144">除了內容的年限或上次修改時間以外，還可選擇從為內容加上標籤的時間或根據事件來開始保留期間的選項。</span><span class="sxs-lookup"><span data-stu-id="85f1a-144">Options to start the retention period from when the content was labeled or based on an event, in addition to the age of the content or when it was last modified.</span></span>

- <span data-ttu-id="85f1a-145">使用[可訓練分類器](classifier-learn-about.md)來識別要加上標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-145">Use [trainable classifiers](classifier-learn-about.md) to identify content to label.</span></span>

- <span data-ttu-id="85f1a-146">為 SharePoint 文件套用預設標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-146">Apply a default label for SharePoint documents.</span></span>

- <span data-ttu-id="85f1a-147">支援[處置檢閱](disposition-reviews.md) 以在內容永久刪除之前檢閱。</span><span class="sxs-lookup"><span data-stu-id="85f1a-147">Support [disposition review](disposition-reviews.md) to review the content before it's permanently deleted.</span></span>

- <span data-ttu-id="85f1a-148">將內容標示為做為標籤設定一部分的[記錄](records-management.md#records)，並且在保留期間結束而刪除內容時，永遠都有 [處置證明](disposition.md#disposition-of-records) 。</span><span class="sxs-lookup"><span data-stu-id="85f1a-148">Mark the content as a [record](records-management.md#records) as part of the label settings, and always have [proof of disposition](disposition.md#disposition-of-records) when content is deleted at the end of its retention period.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="85f1a-149">保留原則</span><span class="sxs-lookup"><span data-stu-id="85f1a-149">Retention policies</span></span>

<span data-ttu-id="85f1a-150">保留原則可以套用到以下位置：</span><span class="sxs-lookup"><span data-stu-id="85f1a-150">Retention policies can be applied to the following locations:</span></span>
- <span data-ttu-id="85f1a-151">Exchange 電子郵件</span><span class="sxs-lookup"><span data-stu-id="85f1a-151">Exchange email</span></span>
- <span data-ttu-id="85f1a-152">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="85f1a-152">SharePoint site</span></span>
- <span data-ttu-id="85f1a-153">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="85f1a-153">OneDrive accounts</span></span>
- <span data-ttu-id="85f1a-154">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="85f1a-154">Microsoft 365 Groups</span></span>
- <span data-ttu-id="85f1a-155">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="85f1a-155">Skype for Business</span></span>
- <span data-ttu-id="85f1a-156">Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="85f1a-156">Exchange public folders</span></span>
- <span data-ttu-id="85f1a-157">Teams 通道訊息</span><span class="sxs-lookup"><span data-stu-id="85f1a-157">Teams channel messages</span></span>
- <span data-ttu-id="85f1a-158">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="85f1a-158">Teams chats</span></span>
- <span data-ttu-id="85f1a-159">Yammer 社群訊息</span><span class="sxs-lookup"><span data-stu-id="85f1a-159">Yammer community messages</span></span>
- <span data-ttu-id="85f1a-160">Yammer 私人訊息</span><span class="sxs-lookup"><span data-stu-id="85f1a-160">Yammer private messages</span></span>

<span data-ttu-id="85f1a-161">您可以輕鬆地將單一原則套用到多個位置，或特定位置或使用者。</span><span class="sxs-lookup"><span data-stu-id="85f1a-161">You can very efficiently apply a single policy to multiple locations, or to specific locations or users.</span></span>

<span data-ttu-id="85f1a-162">保留期間開始時，您可以選擇建立內容的時間，或者只支援檔案和 SharePoint、OneDrive 和 Microsoft 365 群組位置 (上次修改內容的時間) 的時間。</span><span class="sxs-lookup"><span data-stu-id="85f1a-162">For the start of the retention period, you can choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Microsoft 365 Groups locations, when the content was last modified.</span></span>

<span data-ttu-id="85f1a-163">專案會從保留原則指定的容器繼承保留設定。</span><span class="sxs-lookup"><span data-stu-id="85f1a-163">Items inherit the retention settings from their container specified in the retention policy.</span></span> <span data-ttu-id="85f1a-164">如果在爲了保留内容而設定原則時將專案移至容器外，則會在工作負荷的安全位置保留該專案的複本。</span><span class="sxs-lookup"><span data-stu-id="85f1a-164">If they are then moved outside that container when the policy is configured to retain content, a copy of that item is retained in the workload's secured location.</span></span> <span data-ttu-id="85f1a-165">不過，保留設定不會隨著內容移至新的位置。</span><span class="sxs-lookup"><span data-stu-id="85f1a-165">However, the retention settings don't travel with the content in its new location.</span></span> <span data-ttu-id="85f1a-166">如有需要，請使用保留標籤，而非保留原則。</span><span class="sxs-lookup"><span data-stu-id="85f1a-166">If that's required, use retention labels instead of retention policies.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="85f1a-167">保留標籤</span><span class="sxs-lookup"><span data-stu-id="85f1a-167">Retention labels</span></span>

<span data-ttu-id="85f1a-168">請針對需要不同保留設定的不同類型的內容，使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-168">Use retention labels for different types of content that require different retention settings.</span></span> <span data-ttu-id="85f1a-169">例如：</span><span class="sxs-lookup"><span data-stu-id="85f1a-169">For example:</span></span>
  
- <span data-ttu-id="85f1a-170">至少必須保留一小段時間的稅務表單。</span><span class="sxs-lookup"><span data-stu-id="85f1a-170">Tax forms that need to be retained for a minimum period of time.</span></span> 
    
- <span data-ttu-id="85f1a-171">到達特定年限之後需要永久刪除的新聞材料。</span><span class="sxs-lookup"><span data-stu-id="85f1a-171">Press materials that need to be permanently deleted when they reach a specific age.</span></span> 
    
- <span data-ttu-id="85f1a-172">需要先保留一段期間之然後再永久刪除的競爭力研究。</span><span class="sxs-lookup"><span data-stu-id="85f1a-172">Competitive research that needs to be retained for a specific period and then permanently deleted.</span></span> 
    
- <span data-ttu-id="85f1a-173">必須標示為記錄使之無法編輯或刪除的工作簽證。</span><span class="sxs-lookup"><span data-stu-id="85f1a-173">Work visas that must be marked as a record so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="85f1a-174">在這些情況下，保留標籤可讓您在項目層級 (文件或電子郵件) 套用治理控制的保留設定。</span><span class="sxs-lookup"><span data-stu-id="85f1a-174">In all these cases, retention labels let you apply retention settings for governance control at the item level (document or email).</span></span>
  
<span data-ttu-id="85f1a-175">使用保留標籤，您可以：</span><span class="sxs-lookup"><span data-stu-id="85f1a-175">With retention labels, you can:</span></span>
  
- <span data-ttu-id="85f1a-176">**讓貴組織中的人員手動將保留標籤套用** 至網頁上的 Outlook 和 Outlook、OneDrive、SharePoint 和 Microsoft 365 群組中的內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-176">**Enable people in your organization to apply a retention label manually** to content in Outlook and Outlook on the web, OneDrive, SharePoint, and Microsoft 365 groups.</span></span> <span data-ttu-id="85f1a-177">使用者通常都清楚知道自己處理的內容類型，因此可將內容分類並套用適當的保留設定。</span><span class="sxs-lookup"><span data-stu-id="85f1a-177">Users often know best what type of content they're working with, so they can classify it and have the appropriate retention settings applied.</span></span> 
    
- <span data-ttu-id="85f1a-178">在當內容符合特定條件時 **自動將保留標籤套用到內容**，例如內容包含：</span><span class="sxs-lookup"><span data-stu-id="85f1a-178">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    - <span data-ttu-id="85f1a-179">特定類型的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="85f1a-179">Specific types of sensitive information.</span></span>
    - <span data-ttu-id="85f1a-180">特定關鍵字符合您建立的查詢。</span><span class="sxs-lookup"><span data-stu-id="85f1a-180">Specific keywords that match a query you create.</span></span>
    - <span data-ttu-id="85f1a-181">可訓練分類器的模式比對。</span><span class="sxs-lookup"><span data-stu-id="85f1a-181">Pattern matches for a trainable classifier.</span></span>

- <span data-ttu-id="85f1a-182">針對 SharePoint 網站和 OneDrive 帳戶中的文件和電子郵件項目 (行事曆項除外)，**從內容加上標籤起就開始保留期間**。</span><span class="sxs-lookup"><span data-stu-id="85f1a-182">**Start the retention period from when the content was labeled** for documents in SharePoint sites and OneDrive accounts, and to email items with the exception of calendar items.</span></span> <span data-ttu-id="85f1a-183">如果您將具有此設定的保留標籤套用於行事曆項目，則保留期間從其傳送日期開始。</span><span class="sxs-lookup"><span data-stu-id="85f1a-183">If you apply a retention label with this configuration to a calendar item, the retention period starts from when it is sent.</span></span>

- <span data-ttu-id="85f1a-184">**當事件發生時 (例如員工離開組織或合約到期)，開始保留期間**。</span><span class="sxs-lookup"><span data-stu-id="85f1a-184">**Start the retention period when an event occurs**, such as employees leave the organization, or contracts expire.</span></span>

- <span data-ttu-id="85f1a-185">**將預設保留標籤套用至 SharePoint 中的文件庫、資料夾或文件集**，以便儲存在該位置中的所有文件都繼承預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-185">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that are stored in that location inherit the default retention label.</span></span>

<span data-ttu-id="85f1a-186">此外，保留標籤支援跨 Microsoft 365 應用程式和服務的電子郵件和文件[記錄管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-186">Additionally, retention labels support [records management](records-management.md) for email and documents across Microsoft 365 apps and services.</span></span> <span data-ttu-id="85f1a-187">您可以使用保留標籤將內容標記為記錄。</span><span class="sxs-lookup"><span data-stu-id="85f1a-187">You can use a retention label to mark items as a record.</span></span> <span data-ttu-id="85f1a-188">發生此情況且內容仍保留在 Microsoft 365 中時，標籤會針對法規原因可能所需的內容施加進一步的限制。</span><span class="sxs-lookup"><span data-stu-id="85f1a-188">When this happens and the content remains in Microsoft 365, the label places further restrictions on the content that might be needed for regulatory reasons.</span></span> <span data-ttu-id="85f1a-189">如需詳細資訊，請參閱 [比較允許或封鎖動作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-189">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

<span data-ttu-id="85f1a-190">與[敏感度標籤](sensitivity-labels.md)不同，如果內容是移至 Microsoft 365 以外的位置，保留標籤不會保留。</span><span class="sxs-lookup"><span data-stu-id="85f1a-190">Retention labels, unlike [sensitivity labels](sensitivity-labels.md), do not persist if the content is moved outside Microsoft 365.</span></span>

<span data-ttu-id="85f1a-191">針對租用戶支援的保留標籤數量沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="85f1a-191">There is no limit to the number of retention labels that are supported for a tenant.</span></span> <span data-ttu-id="85f1a-192">不過，10,000 個是針對租用戶支援的原則數目上限，其中包括會套用標籤 (保留標籤原則和自動套用保留原則) 的原則，以及保留原則。</span><span class="sxs-lookup"><span data-stu-id="85f1a-192">However, 10,000 is the maximum number of policies that are supported for a tenant and these include the policies that apply the labels (retention label policies and auto-apply retention policies), as well as retention policies.</span></span>

#### <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="85f1a-193">將內容分類而不套用任何動作</span><span class="sxs-lookup"><span data-stu-id="85f1a-193">Classifying content without applying any actions</span></span>

<span data-ttu-id="85f1a-194">雖然保留標籤的主要目的是要保留或刪除內容，但您也可以在不開啟任何保留或其他動作的情況下使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-194">Although the main purpose of retention labels is to retain or delete content, you can also use retention labels without turning on any retention or other actions.</span></span> <span data-ttu-id="85f1a-195">在此情況下，您可以使用保留標籤當做文字標籤，而不強制執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="85f1a-195">In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="85f1a-196">例如，您可以建立並套用名為「稍後檢閱」的保留標籤，而不執行任何動作，然後使用該標籤於稍後尋找該內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-196">For example, you can create and apply a retention label named "Review later" with no actions, and then use that label to find that content later.</span></span>
  
![僅限分類的標籤設定](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="85f1a-198">使用保留標籤作為 DLP 原則的條件</span><span class="sxs-lookup"><span data-stu-id="85f1a-198">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="85f1a-199">您可以將保留標籤做為 SharePoint 文件的資料外洩防護 (DLP) 原則中的條件。</span><span class="sxs-lookup"><span data-stu-id="85f1a-199">You can specify a retention label as a condition in a data loss prevention (DLP) policy for documents in SharePoint.</span></span> <span data-ttu-id="85f1a-200">例如，設定 DLP 原則以防止文件在組織外共用 (如果已套用指定的保留標籤)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-200">For example, configure a DLP policy to prevent documents from being shared outside the organization if they have a specified retention label applied to it.</span></span>

<span data-ttu-id="85f1a-201">如需詳細資訊，請參閱[使用保留標籤做為 DLP 原則中的條件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-201">For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

#### <a name="retention-labels-and-policies-that-apply-them"></a><span data-ttu-id="85f1a-202">保留標籤和套用其標籤的原則</span><span class="sxs-lookup"><span data-stu-id="85f1a-202">Retention labels and policies that apply them</span></span>

<span data-ttu-id="85f1a-203">保留標籤是獨立、可重複使用的建置組塊。</span><span class="sxs-lookup"><span data-stu-id="85f1a-203">Retention labels are independent, reusable building blocks.</span></span> <span data-ttu-id="85f1a-204">保留標籤原則的主要目的是將一組保留標籤分組，以及指定您想讓這些標籤出現的目標位置。</span><span class="sxs-lookup"><span data-stu-id="85f1a-204">The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear.</span></span> <span data-ttu-id="85f1a-205">然後，系統管理員和使用者可以將這些標籤套用至這些位置中的內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-205">Then, admins and users can apply those labels to content in those locations.</span></span>
  
![標籤、標籤原則和位置圖表](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
<span data-ttu-id="85f1a-207">當您發佈保留標籤時，會將這些標籤包含在保留標籤原則中，好讓系統管理員和使用者選擇：</span><span class="sxs-lookup"><span data-stu-id="85f1a-207">When you publish retention labels, they're included in a retention label policy that make them available for admins and users to select:</span></span>

- <span data-ttu-id="85f1a-208">單一保留標籤可納入多個保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="85f1a-208">A single retention label can be included in many retention label policies.</span></span>

- <span data-ttu-id="85f1a-209">保留標籤原則會指定要發佈保留標籤的位置。</span><span class="sxs-lookup"><span data-stu-id="85f1a-209">Retention label policies specify the locations to publish the retention labels.</span></span>

- <span data-ttu-id="85f1a-210">單一位置也可納入多個保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="85f1a-210">A single location can also be included in many retention label policies.</span></span>

<span data-ttu-id="85f1a-211">除了保留標籤原則以外，您也可以建立一或多個自動套用原則，每一個都有單一保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-211">In addition to retention label policies, you can also create one or more auto-apply policies, each with a single retention label.</span></span> <span data-ttu-id="85f1a-212">使用此原則，當您在原則中指定的條件滿足時，將自動套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-212">With this policy, a retention label is automatically applied when conditions that you specify in the policy are met.</span></span> 

#### <a name="retention-label-policies-and-locations"></a><span data-ttu-id="85f1a-213">保留標籤原則與位置</span><span class="sxs-lookup"><span data-stu-id="85f1a-213">Retention label policies and locations</span></span>

<span data-ttu-id="85f1a-214">可以將不同類型的保留標籤發佈到不同的位置，視保留標籤的功能而定。</span><span class="sxs-lookup"><span data-stu-id="85f1a-214">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
| <span data-ttu-id="85f1a-215">如果保留標籤是...</span><span class="sxs-lookup"><span data-stu-id="85f1a-215">If the retention label is…</span></span> | <span data-ttu-id="85f1a-216">標籤原則可套用至…</span><span class="sxs-lookup"><span data-stu-id="85f1a-216">Then the label policy can be applied to…</span></span> |
|:-----|:-----|
|<span data-ttu-id="85f1a-217">已發佈給系統管理員和使用者</span><span class="sxs-lookup"><span data-stu-id="85f1a-217">Published to admins and end users</span></span>  <br/> |<span data-ttu-id="85f1a-218">Exchange、SharePoint、OneDrive、Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="85f1a-218">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
|<span data-ttu-id="85f1a-219">根據敏感資訊類型或可訓練分類器而自動套用</span><span class="sxs-lookup"><span data-stu-id="85f1a-219">Auto-applied based on sensitive information types or trainable classifiers</span></span>  <br/> |<span data-ttu-id="85f1a-220">Exchange (僅限所有信箱)、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="85f1a-220">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="85f1a-221">根據查詢而自動套用</span><span class="sxs-lookup"><span data-stu-id="85f1a-221">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="85f1a-222">Exchange、SharePoint、OneDrive、Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="85f1a-222">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
   
<span data-ttu-id="85f1a-223">在 Exchange 中，您只能在新傳送的郵件 (傳輸中的資料) 上自動套用保留標籤功能，而非目前在信箱中的所有郵件 (待用資料)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-223">In Exchange, auto-apply retention labels are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="85f1a-224">此外，您只能在所有信箱中為敏感性資訊類型和可訓練分類器來自動套用保留標籤功能，但無法選取特定信箱。</span><span class="sxs-lookup"><span data-stu-id="85f1a-224">Also, auto-apply retention labels for sensitive information types and trainable classifiers apply to all mailboxes; you can't select specific mailboxes.</span></span>
  
<span data-ttu-id="85f1a-225">Exchange 公用資料夾、Skype、Teams 和 Yammer 訊息不支援保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-225">Exchange public folders, Skype, Teams and Yammer messages do not support retention labels.</span></span> <span data-ttu-id="85f1a-226">若要保留或刪除這些位置中的內容，請改用保留原則。</span><span class="sxs-lookup"><span data-stu-id="85f1a-226">To retain and delete contain from these locations, use retention policies instead.</span></span>

#### <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="85f1a-227">一次只能有一個保留標籤</span><span class="sxs-lookup"><span data-stu-id="85f1a-227">Only one retention label at a time</span></span>

<span data-ttu-id="85f1a-228">電子郵件或文件等內容一次只能套用一個保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-228">An email or document can have only a single retention label applied to it at a time.</span></span> <span data-ttu-id="85f1a-229">保留標籤可以由使用者或管理員[手動](create-apply-retention-labels.md#manually-apply-retention-labels)套用，也可以使用以下任一方法自動套用：</span><span class="sxs-lookup"><span data-stu-id="85f1a-229">A retention label can be applied [manually](create-apply-retention-labels.md#manually-apply-retention-labels) by an end user or admin, or automatically by using any of the following methods:</span></span>

- [<span data-ttu-id="85f1a-230">自動套用標籤原則</span><span class="sxs-lookup"><span data-stu-id="85f1a-230">Auto-apply label policy</span></span>](apply-retention-labels-automatically.md)
- [<span data-ttu-id="85f1a-231">SharePoint Syntex 中的文件瞭解模型</span><span class="sxs-lookup"><span data-stu-id="85f1a-231">Document understanding model for SharePoint Syntex</span></span>](https://docs.microsoft.com/microsoft-365/contentunderstanding/apply-a-retention-label-to-a-model)
- <span data-ttu-id="85f1a-232">[SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) 或 [Outlook 的預設標籤](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="85f1a-232">[Default label for SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) or [Outlook](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>
- [<span data-ttu-id="85f1a-233">Outlook 規則</span><span class="sxs-lookup"><span data-stu-id="85f1a-233">Outlook rules</span></span>](create-apply-retention-labels.md#automatically-applying-a-retention-label-to-email-by-using-rules)

<span data-ttu-id="85f1a-234">對於標準保留標籤 (它們不會將項目標記為[記錄或監管記錄](records-management.md#records))：</span><span class="sxs-lookup"><span data-stu-id="85f1a-234">For standard retention labels (they don't mark items as a [record or regulatory record](records-management.md#records)):</span></span>

- <span data-ttu-id="85f1a-235">系統管理員和使用者可以手動變更或移除套用於內容的現有保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-235">Admins and end users can manually change or remove an existing retention label that's applied on content.</span></span> 

- <span data-ttu-id="85f1a-236">當內容已套用保留標籤時，現有標籤不會自動移除或替換為另一個保留標籤，但有一個可能的例外：現有標籤已作為預設標籤套用。</span><span class="sxs-lookup"><span data-stu-id="85f1a-236">When content already has a retention label applied, the existing label won't be automatically removed or replaced by another retention label with one possible exception: The existing label was applied as a default label.</span></span>
    
    <span data-ttu-id="85f1a-237">有關使用預設標籤套用標籤行為的詳細資訊，請執行以下操作：</span><span class="sxs-lookup"><span data-stu-id="85f1a-237">For more information about the label behavior when it's applied by using a default label:</span></span>
    - <span data-ttu-id="85f1a-238">SharePoint 的預設標籤：[對 SharePoint 使用預設標籤時的標籤行為](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span><span class="sxs-lookup"><span data-stu-id="85f1a-238">Default label for SharePoint: [Label behavior when you use a default label for SharePoint](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span></span>
    - <span data-ttu-id="85f1a-239">Outlook 的預設標籤：[將預設保留標籤套用於 Outlook 資料夾](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="85f1a-239">Default label for Outlook: [Applying a default retention label to an Outlook folder](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>

- <span data-ttu-id="85f1a-240">如果有多個自動套用標籤原則可以套用保留標籤，並且內容滿足多個原則的條件，則套用最舊的自動套用標籤原則 (按建立日期) 的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-240">If there are multiple auto-apply label policies that could apply a retention label, and content meets the conditions of multiple policies, the retention label for the oldest auto-apply label policy (by date created) is applied.</span></span>

<span data-ttu-id="85f1a-241">當保留標籤將項目標記為記錄或監管記錄時，這些標籤不會自動變更。</span><span class="sxs-lookup"><span data-stu-id="85f1a-241">When retention labels mark items as a record or a regulatory record, these labels are never automatically changed.</span></span> <span data-ttu-id="85f1a-242">只有容器的管理員才能手動變更或移除將項目標記為記錄而不是監管記錄的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-242">Only admins for the container can manually change or remove retention labels that mark items as a record, but not regulatory records.</span></span> <span data-ttu-id="85f1a-243">如需詳細資訊，請參閱 [比較允許或封鎖動作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-243">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

#### <a name="monitoring-retention-labels"></a><span data-ttu-id="85f1a-244">監視保留標籤</span><span class="sxs-lookup"><span data-stu-id="85f1a-244">Monitoring retention labels</span></span>

<span data-ttu-id="85f1a-245">在 Microsoft 365 合規性中心中，使用 **資料分類** > **概觀** 來監視保留標籤在租用戶中的使用方式，並識別標籤項目的位置。</span><span class="sxs-lookup"><span data-stu-id="85f1a-245">From the Microsoft 365 compliance center, use **Data classification** > **Overview** to monitor how your retention labels are being used in your tenant, and identify where your labeled items are located.</span></span> <span data-ttu-id="85f1a-246">如需詳細資訊 (包括重要先決條件)，請參閱[了解您的資料 - 資料分類概觀](data-classification-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-246">For more information, including important prerequisites, see [Know your data - data classification overview](data-classification-overview.md).</span></span>

<span data-ttu-id="85f1a-247">然後您可以使用[內容總管](data-classification-content-explorer.md)和[活動總管](data-classification-activity-explorer.md)深入探討詳細資料。</span><span class="sxs-lookup"><span data-stu-id="85f1a-247">You can then drill down into details by using [content explorer](data-classification-content-explorer.md) and [activity explorer](data-classification-activity-explorer.md).</span></span>

> [!TIP]
><span data-ttu-id="85f1a-248">請考慮使用一些其他的資料分類深入解析 (例如可訓練分類器和敏感性資訊類型)，協助您識別可能需要保留或刪除的內容，或管理記錄。</span><span class="sxs-lookup"><span data-stu-id="85f1a-248">Consider using some of the other data classification insights, such as trainable classifiers and sensitive info types, to help you identify content that you might need to retain or delete, or manage as records.</span></span>

<span data-ttu-id="85f1a-249">Office 365 安全性與合規性中心具有來自 **資訊控管** > **儀表板** 的保留標籤同等概觀資訊，以及來自 **資訊控管** > **標籤活動總管** 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="85f1a-249">The Office 365 Security & Compliance Center has the equivalent overview information for retention labels from **Information governance** > **Dashboard**, and more detailed information from **Information governance** > **Label activity explorer**.</span></span> <span data-ttu-id="85f1a-250">如需從此舊版系統管理中心監視保留標籤的詳細資訊，請參閱下列文件：</span><span class="sxs-lookup"><span data-stu-id="85f1a-250">For more information about monitoring retention labels from this older admin center, see the following documentation:</span></span>
- [<span data-ttu-id="85f1a-251">檢視資料控管報告</span><span class="sxs-lookup"><span data-stu-id="85f1a-251">View the data governance reports</span></span>](view-the-data-governance-reports.md)
- [<span data-ttu-id="85f1a-252">利用標籤分析檢視標籤使用量</span><span class="sxs-lookup"><span data-stu-id="85f1a-252">View label usage with label analytics</span></span>](label-analytics.md)
- [<span data-ttu-id="85f1a-253">檢視文件的標籤活動</span><span class="sxs-lookup"><span data-stu-id="85f1a-253">View label activity for documents</span></span>](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a><span data-ttu-id="85f1a-254">使用內容搜尋來尋找具有特定保留標籤的所有內容</span><span class="sxs-lookup"><span data-stu-id="85f1a-254">Using Content Search to find all content with a specific retention label</span></span>

<span data-ttu-id="85f1a-255">將保留標籤套用至內容後 (無論是由使用者套用或自動套用)，您可以使用內容搜尋來尋找已套用特定保留標籤的所有項目。</span><span class="sxs-lookup"><span data-stu-id="85f1a-255">After retention labels are applied to content, either by users or auto-applied, you can use content search to find all items that have a specific retention label applied.</span></span>

<span data-ttu-id="85f1a-256">當您建立內容搜尋時，請選擇 **[保留標籤]** 條件，然後輸入完整的保留標籤名稱或是部分標籤名稱，再使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="85f1a-256">When you create a content search, choose the **Retention label** condition, and then enter the complete retention label name or part of the label name and use a wildcard.</span></span> <span data-ttu-id="85f1a-257">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-257">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![保留標籤條件](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a><span data-ttu-id="85f1a-259">比較保留原則和保留標籤的功能</span><span class="sxs-lookup"><span data-stu-id="85f1a-259">Compare capabilities for retention policies and retention labels</span></span>

<span data-ttu-id="85f1a-260">使用下列表格來協助您判斷是否要根據功能來使用保留原則或保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-260">Use the following table to help you identify whether to use a retention policy or retention label, based on capabilities.</span></span>

|<span data-ttu-id="85f1a-261">功能</span><span class="sxs-lookup"><span data-stu-id="85f1a-261">Capability</span></span>|<span data-ttu-id="85f1a-262">保留原則</span><span class="sxs-lookup"><span data-stu-id="85f1a-262">Retention policy</span></span> |<span data-ttu-id="85f1a-263">保留標籤</span><span class="sxs-lookup"><span data-stu-id="85f1a-263">Retention label</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="85f1a-264">可以保留然後刪除、僅保留或僅刪除的保留設定</span><span class="sxs-lookup"><span data-stu-id="85f1a-264">Retention settings that can retain and then delete, retain-only, or delete-only</span></span> |<span data-ttu-id="85f1a-265">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-265">Yes</span></span> |<span data-ttu-id="85f1a-266">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-266">Yes</span></span> |
|<span data-ttu-id="85f1a-267">支援的工作負載：</span><span class="sxs-lookup"><span data-stu-id="85f1a-267">Workloads supported:</span></span> <br /><span data-ttu-id="85f1a-268">- Exchange</span><span class="sxs-lookup"><span data-stu-id="85f1a-268">- Exchange</span></span> <br /><span data-ttu-id="85f1a-269">- SharePoint</span><span class="sxs-lookup"><span data-stu-id="85f1a-269">- SharePoint</span></span> <br /><span data-ttu-id="85f1a-270">- OneDrive</span><span class="sxs-lookup"><span data-stu-id="85f1a-270">- OneDrive</span></span> <br /><span data-ttu-id="85f1a-271">- Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="85f1a-271">- Microsoft 365 groups</span></span> <br /><span data-ttu-id="85f1a-272">- 商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="85f1a-272">- Skype for Business</span></span> <br /><span data-ttu-id="85f1a-273">- Teams</span><span class="sxs-lookup"><span data-stu-id="85f1a-273">- Teams</span></span><br /><span data-ttu-id="85f1a-274">- Yammer</span><span class="sxs-lookup"><span data-stu-id="85f1a-274">- Yammer</span></span>|<br /> <span data-ttu-id="85f1a-275">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-275">Yes</span></span> <br /> <span data-ttu-id="85f1a-276">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-276">Yes</span></span> <br /> <span data-ttu-id="85f1a-277">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-277">Yes</span></span> <br /> <span data-ttu-id="85f1a-278">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-278">Yes</span></span> <br /> <span data-ttu-id="85f1a-279">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-279">Yes</span></span> <br /> <span data-ttu-id="85f1a-280">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-280">Yes</span></span> <br /> <span data-ttu-id="85f1a-281">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-281">Yes</span></span> | <br /> <span data-ttu-id="85f1a-282">是，除了公用資料夾</span><span class="sxs-lookup"><span data-stu-id="85f1a-282">Yes, except public folders</span></span> <br /> <span data-ttu-id="85f1a-283">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-283">Yes</span></span> <br /> <span data-ttu-id="85f1a-284">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-284">Yes</span></span> <br /> <span data-ttu-id="85f1a-285">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-285">Yes</span></span> <br /> <span data-ttu-id="85f1a-286">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-286">No</span></span> <br /> <span data-ttu-id="85f1a-287">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-287">No</span></span> <br /> <span data-ttu-id="85f1a-288">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-288">No</span></span> |
|<span data-ttu-id="85f1a-289">自動套用的保留</span><span class="sxs-lookup"><span data-stu-id="85f1a-289">Retention applied automatically</span></span> | <span data-ttu-id="85f1a-290">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-290">Yes</span></span> | <span data-ttu-id="85f1a-291">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-291">Yes</span></span> |
|<span data-ttu-id="85f1a-292">根據條件套用保留</span><span class="sxs-lookup"><span data-stu-id="85f1a-292">Retention applied based on conditions</span></span> <br /> <span data-ttu-id="85f1a-293">- 敏感資訊類型、KQL 查詢、可訓練分類器</span><span class="sxs-lookup"><span data-stu-id="85f1a-293">- sensitive info types, KQL queries, trainable classifiers</span></span>| <span data-ttu-id="85f1a-294">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-294">No</span></span> | <span data-ttu-id="85f1a-295">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-295">Yes</span></span> |
|<span data-ttu-id="85f1a-296">手動套用的保留</span><span class="sxs-lookup"><span data-stu-id="85f1a-296">Retention applied manually</span></span> | <span data-ttu-id="85f1a-297">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-297">No</span></span> | <span data-ttu-id="85f1a-298">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-298">Yes</span></span> |
|<span data-ttu-id="85f1a-299">使用者的 UI 目前狀態</span><span class="sxs-lookup"><span data-stu-id="85f1a-299">UI presence for end users</span></span> | <span data-ttu-id="85f1a-300">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-300">No</span></span> | <span data-ttu-id="85f1a-301">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-301">Yes</span></span> |
|<span data-ttu-id="85f1a-302">如果內容已移動，則會持續存在</span><span class="sxs-lookup"><span data-stu-id="85f1a-302">Persists if the content is moved</span></span> | <span data-ttu-id="85f1a-303">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-303">No</span></span> | <span data-ttu-id="85f1a-304">是，在您的 Microsoft 365 租用戶中</span><span class="sxs-lookup"><span data-stu-id="85f1a-304">Yes, within your Microsoft 365 tenant</span></span> |
|<span data-ttu-id="85f1a-305">將項目宣告為記錄</span><span class="sxs-lookup"><span data-stu-id="85f1a-305">Declare item as a record</span></span>| <span data-ttu-id="85f1a-306">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-306">No</span></span> | <span data-ttu-id="85f1a-307">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-307">Yes</span></span> |
|<span data-ttu-id="85f1a-308">在加上標籤起或根據事件來開始保留期間</span><span class="sxs-lookup"><span data-stu-id="85f1a-308">Start the retention period when labeled or based on an event</span></span> | <span data-ttu-id="85f1a-309">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-309">No</span></span> | <span data-ttu-id="85f1a-310">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-310">Yes</span></span> |
|<span data-ttu-id="85f1a-311">處置檢閱</span><span class="sxs-lookup"><span data-stu-id="85f1a-311">Disposition review</span></span> | <span data-ttu-id="85f1a-312">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-312">No</span></span>| <span data-ttu-id="85f1a-313">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-313">Yes</span></span> |
|<span data-ttu-id="85f1a-314">最高 7 年的處置證明</span><span class="sxs-lookup"><span data-stu-id="85f1a-314">Proof of disposition for up to 7 years</span></span> | <span data-ttu-id="85f1a-315">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-315">No</span></span> |<span data-ttu-id="85f1a-316">是，當物料宣告為記錄時</span><span class="sxs-lookup"><span data-stu-id="85f1a-316">Yes, when item is declared a record</span></span>|
|<span data-ttu-id="85f1a-317">稽核系統管理員活動</span><span class="sxs-lookup"><span data-stu-id="85f1a-317">Audit admin activities</span></span>| <span data-ttu-id="85f1a-318">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-318">Yes</span></span> | <span data-ttu-id="85f1a-319">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-319">Yes</span></span>|
|<span data-ttu-id="85f1a-320">識別要保留的項目：</span><span class="sxs-lookup"><span data-stu-id="85f1a-320">Identify items subject to retention:</span></span> <br /> <span data-ttu-id="85f1a-321">- 內容搜尋</span><span class="sxs-lookup"><span data-stu-id="85f1a-321">- Content Search</span></span> <br /> <span data-ttu-id="85f1a-322">- 資料分類頁面、內容總管，活動總管</span><span class="sxs-lookup"><span data-stu-id="85f1a-322">- Data classification page, content explorer, activity explorer</span></span> | <br /> <span data-ttu-id="85f1a-323">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-323">No</span></span> <br /> <span data-ttu-id="85f1a-324">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-324">No</span></span> | <br /> <span data-ttu-id="85f1a-325">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-325">Yes</span></span> <br /> <span data-ttu-id="85f1a-326">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-326">Yes</span></span>|

<span data-ttu-id="85f1a-327">請注意，您可以使用保留原則和保留標籤做為補充保留方法。</span><span class="sxs-lookup"><span data-stu-id="85f1a-327">Note that you can use both retention policies and retention labels as complementary retention methods.</span></span> <span data-ttu-id="85f1a-328">例如：</span><span class="sxs-lookup"><span data-stu-id="85f1a-328">For example:</span></span>

1. <span data-ttu-id="85f1a-329">您建立並設定將在內容上次修改後五年自動刪除內容的保留原則，並將該原則套用於所有 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="85f1a-329">You create and configure a retention policy that automatically deletes content five years after it's last modified, and apply the policy to all OneDrive accounts.</span></span>

2. <span data-ttu-id="85f1a-330">您建立並設定永久保留內容的保留標籤，並將其新增至您發佈到所有 OneDrive 帳戶的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="85f1a-330">You create and configure a retention label that keeps content forever and add this to a label policy that you publish to all OneDrive accounts.</span></span> <span data-ttu-id="85f1a-331">您向使用者說明如何手動將此標籤套用於五年後未修改應從自動刪除排除的特定文件。</span><span class="sxs-lookup"><span data-stu-id="85f1a-331">You explain to users how to manually apply this label to specific documents that should be excluded from automatic deletion if not modified after five years.</span></span>

<span data-ttu-id="85f1a-332">有關保留原則和保留標籤如何搭配，以及如何判斷其合併結果的更多資訊，請參閱下一節解釋保留的原則和其優先順序。</span><span class="sxs-lookup"><span data-stu-id="85f1a-332">For more information about how retention policies and retention labels work together and how to determine their combined outcome, see the next section that explains the principles of retention and what takes precedence.</span></span>

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="85f1a-333">原則保留或何者優先</span><span class="sxs-lookup"><span data-stu-id="85f1a-333">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="85f1a-334">內容有可能套用多個會進行不同動作 (保留、刪除或保留然後刪除) 且保留期間不同的保留原則和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-334">It's possible or even likely that content might have several retention policies and retention labels applied to it, each with a different action (retain, delete, or retain and then delete) and retention period.</span></span> <span data-ttu-id="85f1a-335">哪個的優先順序較高？</span><span class="sxs-lookup"><span data-stu-id="85f1a-335">What takes precedence?</span></span> 

<span data-ttu-id="85f1a-336">在高層級中，您可以確保保留永遠優先於刪除，然後才是最長的保留期間勝出。</span><span class="sxs-lookup"><span data-stu-id="85f1a-336">At a high level, you can be assured that retention always takes precedence over deletion, and then the longest retention period wins.</span></span> 

<span data-ttu-id="85f1a-337">但還有其他一些因素需要考慮，因此請使用以下流程來了解每個層級從上到下扮演決勝局的結果：如果結果由第一層級決定，則無需前進到下一個層級，依此類推。</span><span class="sxs-lookup"><span data-stu-id="85f1a-337">However, there are a few more factors to throw into the mix, so use the following flow to understand the outcome where each level acts as a tie-breaker from top to bottom: If the outcome is determined by the first level, there's no need to progress to the next level, and so on.</span></span> <span data-ttu-id="85f1a-338">只有當結果無法由層級規則決定時，流程才會移至下一個層級，以決定保留設定優先權的結果。</span><span class="sxs-lookup"><span data-stu-id="85f1a-338">Only if the outcome can't be determined by the rules for the level does the flow move down to the next level to determine the outcome for which retention settings take precedence.</span></span>

![原則保留圖](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="85f1a-340">四個不同層級的說明：</span><span class="sxs-lookup"><span data-stu-id="85f1a-340">Explanation for the four different levels:</span></span>
  
1. <span data-ttu-id="85f1a-341">**保留優先於刪除。**</span><span class="sxs-lookup"><span data-stu-id="85f1a-341">**Retention wins over deletion.**</span></span> <span data-ttu-id="85f1a-342">假設某個保留原則設定在 3 年後刪除 Exchange 電子郵件，但另一個保留原則設定將 Exchange 電子郵件保留 5 年再刪除。</span><span class="sxs-lookup"><span data-stu-id="85f1a-342">Suppose that one retention policy is configured to delete Exchange email after three years, but another retention policy is configured to retain Exchange email for five years and then delete it.</span></span> <span data-ttu-id="85f1a-343">任何到達 3 年的內容會遭到刪除，並從使用者的檢視畫面隱藏，但仍會保留再 [可復原的項目] 資料夾中，直到內容到達 5 年，才會遭永久刪除。</span><span class="sxs-lookup"><span data-stu-id="85f1a-343">Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it is permanently deleted.</span></span> 
2. <span data-ttu-id="85f1a-344">**最長保留期間優先。**</span><span class="sxs-lookup"><span data-stu-id="85f1a-344">**The longest retention period wins.**</span></span> <span data-ttu-id="85f1a-345">如果內容受制於在不同的期間保留內容的多個保留設定，則該內容將一直保留到最長保留期間結束為止。</span><span class="sxs-lookup"><span data-stu-id="85f1a-345">If content is subject to multiple retention settings that retain content for different periods of time, the content will be retained until the end of the longest retention period.</span></span>
    
3. <span data-ttu-id="85f1a-346">**明確包含優先於隱含包含。**</span><span class="sxs-lookup"><span data-stu-id="85f1a-346">**Explicit inclusion wins over implicit inclusion.**</span></span> <span data-ttu-id="85f1a-347">也就是說：</span><span class="sxs-lookup"><span data-stu-id="85f1a-347">This means:</span></span> 
    
    1. <span data-ttu-id="85f1a-348">如果包含保留設定的保留標籤是由使用者手動指派至項目 (例如 Exchange 電子郵件或 OneDrive 文件)，則該保留標籤會優先於在網站或信箱層級指派的保留原則，以及指派給文件庫的預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-348">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a retention policy assigned at the site or mailbox level and a default retention label assigned to the document library.</span></span> <span data-ttu-id="85f1a-349">例如，如果明確保留標籤設定要保留內容十年，但對網站指派的保留原則設定為保留內容五年，則保留標籤會優先於原則。</span><span class="sxs-lookup"><span data-stu-id="85f1a-349">For example, if the explicit retention label is configured to retain content for ten years, but a retention policy assigned to the site is configured to retain content for only five years, the retention label takes precedence.</span></span>
    
    2. <span data-ttu-id="85f1a-350">如果保留原則包含特定位置 (例如特定使用者的信箱或 OneDrive 帳戶)，則該保留原則會優先於其他套用至所有使用者信箱或 OneDrive 帳戶但未特地包含該使用者信箱的保留原則。</span><span class="sxs-lookup"><span data-stu-id="85f1a-350">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive account, that retention policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="85f1a-351">**最短刪除期間優先。**</span><span class="sxs-lookup"><span data-stu-id="85f1a-351">**The shortest deletion period wins.**</span></span> <span data-ttu-id="85f1a-352">同樣地，如果內容受限於會刪除內容但不帶保留期間的多個保留設定，則會在最短刪除期間結束時刪除該內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-352">Similarly, if content is subject to multiple retention settings that delete content without a retention period, that content will be deleted at the end of the shortest retention period.</span></span> 

<span data-ttu-id="85f1a-353">最終，保留原則或保留標籤無法永久刪除任何電子文件探索保留的內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-353">Finally, a retention policy or retention label cannot permanently delete any content that's on hold for eDiscovery.</span></span> <span data-ttu-id="85f1a-354">將保留釋出時，該內容會再次符合上述的清理程序資格，並在工作負載的受保護位置中進行。</span><span class="sxs-lookup"><span data-stu-id="85f1a-354">When that hold is released, the content again becomes eligible for the cleanup process in the secured locations for the workload.</span></span>

## <a name="use-preservation-lock-to-restrict-changes-to-policies"></a><span data-ttu-id="85f1a-355">使用「保留鎖定」來限制原則變更</span><span class="sxs-lookup"><span data-stu-id="85f1a-355">Use Preservation Lock to restrict changes to policies</span></span>

<span data-ttu-id="85f1a-356">有些組織可能需要遵守由控管機構定義的規則，例如證券交易委員會 (SEC) 規定 17a-4，要求在保留原則開啟之後，不能關閉或執行較不嚴格的限制。</span><span class="sxs-lookup"><span data-stu-id="85f1a-356">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a policy for retention is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="85f1a-357">「保留鎖定」可確保您的組織能夠符合這類法規需求，因為它會鎖定保留原則或保留標籤原則，使得沒有任何人 (包括系統管理員) 可以關閉原則、刪除原則或降低限制。</span><span class="sxs-lookup"><span data-stu-id="85f1a-357">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy or retention label policy so that no one—including an administrator—can turn off the policy, delete the policy, or make it less restrictive.</span></span>
  
<span data-ttu-id="85f1a-358">建立保留原則或保留標籤原則之後，您可以套用「保留鎖定」。</span><span class="sxs-lookup"><span data-stu-id="85f1a-358">You apply Preservation Lock after the retention policy or retention label policy is created.</span></span> <span data-ttu-id="85f1a-359">如需更多資訊和指示，請參閲[使用保留鎖定來限制變更保留原則和保留標籤原則](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-359">For more information and instructions, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="releasing-a-policy-for-retention"></a><span data-ttu-id="85f1a-360">發佈保留原則</span><span class="sxs-lookup"><span data-stu-id="85f1a-360">Releasing a policy for retention</span></span>

<span data-ttu-id="85f1a-361">如果您的保留原則沒有保留鎖定，您可以隨時刪除您的原則，以便有效地關閉先前套用的保留設定。</span><span class="sxs-lookup"><span data-stu-id="85f1a-361">Providing your policies for retention don't have a Preservation Lock, you can delete your policies at any time, which effectively turns off the previously applied retention settings.</span></span> <span data-ttu-id="85f1a-362">您也可以維持原有的保留原則，但將位置狀態變更為 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="85f1a-362">You can also keep the policy but change the location status to off.</span></span>
 
<span data-ttu-id="85f1a-363">當您這麼做時，保留在文件保留庫中的任何 SharePoint 或 OneDrive 的內容不會立即永久被刪除。</span><span class="sxs-lookup"><span data-stu-id="85f1a-363">When you do either of these actions, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="85f1a-364">相反地，為了防止意外的資料遺失，我們有 30 天的寬限期，在這期間，保留文件庫中不會發生該原則的內容到期，因此，如有需要，您可以在這裡還原任何內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-364">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="85f1a-365">此外，您無法在寬限期期間手動刪除此內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-365">Additionally, you can't manually delete this content during the grace period.</span></span>

<span data-ttu-id="85f1a-366">您可以在寬限期期間將位置狀態變更為 [開啟]，這麼一來，該原則的內容將不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="85f1a-366">You can change the location status back to on during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="85f1a-367">SharePoint 和 OneDrive 中的此 30 天寬限期與 Exchange 中的 30 天延遲保留對應。</span><span class="sxs-lookup"><span data-stu-id="85f1a-367">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="85f1a-368">如需詳細資訊，請參閱[管理延遲保留信箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-368">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

## <a name="auditing-retention-configuration"></a><span data-ttu-id="85f1a-369">稽核保留設定</span><span class="sxs-lookup"><span data-stu-id="85f1a-369">Auditing retention configuration</span></span>

<span data-ttu-id="85f1a-370">[啟用稽核功能](turn-audit-log-search-on-or-off.md)後，系統會將保留原則和保留標籤的系統管理員動作儲存至稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="85f1a-370">Administrator actions for retention policies and retention labels are saved to the audit log when [auditing is enabled](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="85f1a-371">例如，建立、設定或刪除保留原則或標籤後，系統會建立稽核事件。</span><span class="sxs-lookup"><span data-stu-id="85f1a-371">For example, an audit event is created when a retention policy or label is created, configured, or deleted.</span></span> <span data-ttu-id="85f1a-372">如需完整清單，請參閱[保留原則和保留標籤活動](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-372">For the full list, see [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).</span></span>

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a><span data-ttu-id="85f1a-373">保留原則和保留標籤的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="85f1a-373">PowerShell cmdlets for retention policies and retention labels</span></span>

<span data-ttu-id="85f1a-374">若要使用保留 Cmdlet，您必須先[連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-374">To use the retention cmdlets, you must first [connect to the Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="85f1a-375">然後使用以下任一 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="85f1a-375">Then, use any of the following cmdlets:</span></span>

- [<span data-ttu-id="85f1a-376">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="85f1a-376">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [<span data-ttu-id="85f1a-377">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="85f1a-377">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [<span data-ttu-id="85f1a-378">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="85f1a-378">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [<span data-ttu-id="85f1a-379">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="85f1a-379">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [<span data-ttu-id="85f1a-380">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="85f1a-380">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [<span data-ttu-id="85f1a-381">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="85f1a-381">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [<span data-ttu-id="85f1a-382">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="85f1a-382">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [<span data-ttu-id="85f1a-383">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="85f1a-383">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [<span data-ttu-id="85f1a-384">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="85f1a-384">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [<span data-ttu-id="85f1a-385">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="85f1a-385">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [<span data-ttu-id="85f1a-386">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="85f1a-386">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [<span data-ttu-id="85f1a-387">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="85f1a-387">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [<span data-ttu-id="85f1a-388">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="85f1a-388">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [<span data-ttu-id="85f1a-389">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="85f1a-389">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a><span data-ttu-id="85f1a-390">何時使用保留原則和保留標籤或電子文件探索保留？</span><span class="sxs-lookup"><span data-stu-id="85f1a-390">When to use retention policies and retention labels or eDiscovery holds</span></span>

<span data-ttu-id="85f1a-391">雖然您使用保留設定和[電子文件探索案例所建立的保留](create-ediscovery-holds.md)都可以防止資料永久刪除，但它們是為不同情況而設計的。</span><span class="sxs-lookup"><span data-stu-id="85f1a-391">Although retention settings and [holds that you create with an eDiscovery case](create-ediscovery-holds.md) can both prevent data from being permanently deleted, they are designed for different scenarios.</span></span> <span data-ttu-id="85f1a-392">若要協助您了解差異及決定使用哪個，請使用下列指南：</span><span class="sxs-lookup"><span data-stu-id="85f1a-392">To help you understand the differences and decide which to use, use the following guidance:</span></span>

- <span data-ttu-id="85f1a-393">您在 [保留原則] 和 [保留標籤] 中指定的保留設定，是專為長期資訊控管而設計，以保留或刪除符合法規需求的資料。</span><span class="sxs-lookup"><span data-stu-id="85f1a-393">Retention settings that you specify in retention policies and retention labels are designed for a long-term information governance strategy to retain or delete data for compliance requirements.</span></span> <span data-ttu-id="85f1a-394">範圍通常很廣，主要重點是位置和內容，而不是個別使用者。</span><span class="sxs-lookup"><span data-stu-id="85f1a-394">The scope is usually broad with the main focus being the location and content rather than individual users.</span></span> <span data-ttu-id="85f1a-395">保留期間的開始和結束是可設定的，可選擇自動刪除內容，而不需要其他系統管理員介入。</span><span class="sxs-lookup"><span data-stu-id="85f1a-395">The start and end of the retention period is configurable, with the option to automatically delete content without additional administrator intervention.</span></span>

- <span data-ttu-id="85f1a-396">電子文件探索的保留 (核心電子文件探索或進階電子文件探索案例) 是專為保留資料以供法律調查所設計。</span><span class="sxs-lookup"><span data-stu-id="85f1a-396">Holds for eDiscovery (either Core eDiscovery or Advanced eDiscovery cases) are designed for a limited duration to preserve data for a legal investigation.</span></span> <span data-ttu-id="85f1a-397">該範圍是特定的，且重點是已識別使用者所擁有的內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-397">The scope is specific with the focus being content owned by identified users.</span></span> <span data-ttu-id="85f1a-398">保留期間的開始和結束不會進行設定，但與個別系統管理員的動作相關，沒有選項可在保留解除時自動刪除內容。</span><span class="sxs-lookup"><span data-stu-id="85f1a-398">The start and end of the preservation period isn't configurable but dependent on individual administrator actions, without an option to automatically delete content when the hold is released.</span></span>

<span data-ttu-id="85f1a-399">比較保留與電子文件探索保留的摘要：</span><span class="sxs-lookup"><span data-stu-id="85f1a-399">Summary to compare retention with holds:</span></span>

|<span data-ttu-id="85f1a-400">考量事項</span><span class="sxs-lookup"><span data-stu-id="85f1a-400">Consideration</span></span>|<span data-ttu-id="85f1a-401">保留</span><span class="sxs-lookup"><span data-stu-id="85f1a-401">Retention</span></span> |<span data-ttu-id="85f1a-402">電子文件探索保留</span><span class="sxs-lookup"><span data-stu-id="85f1a-402">eDiscovery holds</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="85f1a-403">商務需求：</span><span class="sxs-lookup"><span data-stu-id="85f1a-403">Business need:</span></span> |<span data-ttu-id="85f1a-404">合規性</span><span class="sxs-lookup"><span data-stu-id="85f1a-404">Compliance</span></span> |<span data-ttu-id="85f1a-405">法律資訊</span><span class="sxs-lookup"><span data-stu-id="85f1a-405">Legal</span></span> |
|<span data-ttu-id="85f1a-406">時間範圍：</span><span class="sxs-lookup"><span data-stu-id="85f1a-406">Time scope:</span></span> |<span data-ttu-id="85f1a-407">長期</span><span class="sxs-lookup"><span data-stu-id="85f1a-407">Long-term</span></span> |<span data-ttu-id="85f1a-408">短期</span><span class="sxs-lookup"><span data-stu-id="85f1a-408">Short-term</span></span> |
|<span data-ttu-id="85f1a-409">焦點：</span><span class="sxs-lookup"><span data-stu-id="85f1a-409">Focus:</span></span> |<span data-ttu-id="85f1a-410">廣泛的、內容型</span><span class="sxs-lookup"><span data-stu-id="85f1a-410">Broad, content-based</span></span> |<span data-ttu-id="85f1a-411">特定的、使用者型</span><span class="sxs-lookup"><span data-stu-id="85f1a-411">Specific, user-based</span></span> |
|<span data-ttu-id="85f1a-412">開始和結束日期可設定：</span><span class="sxs-lookup"><span data-stu-id="85f1a-412">Start and end date configurable:</span></span> |<span data-ttu-id="85f1a-413">是</span><span class="sxs-lookup"><span data-stu-id="85f1a-413">Yes</span></span> |<span data-ttu-id="85f1a-414">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-414">No</span></span> |
|<span data-ttu-id="85f1a-415">內容刪除：</span><span class="sxs-lookup"><span data-stu-id="85f1a-415">Content deletion:</span></span> |<span data-ttu-id="85f1a-416">是 (選用)</span><span class="sxs-lookup"><span data-stu-id="85f1a-416">Yes (optional)</span></span> |<span data-ttu-id="85f1a-417">否</span><span class="sxs-lookup"><span data-stu-id="85f1a-417">No</span></span> |
|<span data-ttu-id="85f1a-418">系統管理開銷：</span><span class="sxs-lookup"><span data-stu-id="85f1a-418">Administrative overheads:</span></span> |<span data-ttu-id="85f1a-419">低</span><span class="sxs-lookup"><span data-stu-id="85f1a-419">Low</span></span> |<span data-ttu-id="85f1a-420">高</span><span class="sxs-lookup"><span data-stu-id="85f1a-420">High</span></span> |

<span data-ttu-id="85f1a-421">如果內容同時受制於保留設定和電子文件探索保留，則電子文件探索保留的內容保留永遠優先。</span><span class="sxs-lookup"><span data-stu-id="85f1a-421">If content is subject to both retention settings and an eDiscovery hold, preserving content for the eDiscovery hold always takes precedence.</span></span> <span data-ttu-id="85f1a-422">如此一來，[保留的原則](#the-principles-of-retention-or-what-takes-precedence)會擴充至電子文件探索保留，因為系統會在管理員手動解除保留之前，將資料保留。</span><span class="sxs-lookup"><span data-stu-id="85f1a-422">In this way, the [principles of retention](#the-principles-of-retention-or-what-takes-precedence) expand to eDiscovery holds because they preserve data until an administrator manually releases the hold.</span></span> <span data-ttu-id="85f1a-423">不過，儘管這個優先順序，請不要將電子文件探索保留用於長期資訊控管。</span><span class="sxs-lookup"><span data-stu-id="85f1a-423">However, despite this precedence, don't use eDiscovery holds for long-term information governance.</span></span> <span data-ttu-id="85f1a-424">如果您擔心自動刪除資料，您可以設定保留設定以永遠保留項目，或對保留標籤使用[處置評審](disposition.md#disposition-reviews)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-424">If you are concerned about automatic deletion of data, you can configure retention settings to retain items forever, or use [disposition review](disposition.md#disposition-reviews) with retention labels.</span></span>

<span data-ttu-id="85f1a-425">如果您使用舊版電子文件探索工具來保留資料，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="85f1a-425">If you are using older eDiscovery tools to preserve data, see the following resources:</span></span>

- <span data-ttu-id="85f1a-426">Exchange：</span><span class="sxs-lookup"><span data-stu-id="85f1a-426">Exchange:</span></span> 
    - [<span data-ttu-id="85f1a-427">就地保留與訴訟資料暫留</span><span class="sxs-lookup"><span data-stu-id="85f1a-427">In-Place Hold and Litigation Hold</span></span>](https://go.microsoft.com/fwlink/?linkid=846124)
    - <span data-ttu-id="85f1a-428">[如何找出位於 Exchange Online 信箱的保留類型](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox) (英文)</span><span class="sxs-lookup"><span data-stu-id="85f1a-428">[How to identify the type of hold placed on an Exchange Online mailbox](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox)</span></span>

- <span data-ttu-id="85f1a-429">SharePoint 和 OneDrive：</span><span class="sxs-lookup"><span data-stu-id="85f1a-429">SharePoint and OneDrive:</span></span> 
    - <span data-ttu-id="85f1a-430">[在電子文件探索中心將內容新增至案例及保留來源](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (英文)</span><span class="sxs-lookup"><span data-stu-id="85f1a-430">[Add content to a case and place sources on hold in the eDiscovery Center](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)</span></span>

- [<span data-ttu-id="85f1a-431">舊版電子文件探索工具淘汰</span><span class="sxs-lookup"><span data-stu-id="85f1a-431">Retirement of legacy eDiscovery tools</span></span>](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a><span data-ttu-id="85f1a-432">請使用保留原則和保留標籤，而非舊版的功能</span><span class="sxs-lookup"><span data-stu-id="85f1a-432">Use retention policies and retention labels instead of older features</span></span>

<span data-ttu-id="85f1a-433">如果您必要在 Microsoft 365 中預先主動保留或刪除內容，我們建議您使用保留原則和保留標籤，而非以下較舊的功能。</span><span class="sxs-lookup"><span data-stu-id="85f1a-433">If you need to proactively retain or delete content in Microsoft 365 for information governance, we recommend that you use retention policies and retention labels instead of the following older features.</span></span>

<span data-ttu-id="85f1a-434">如果您目前使用這些較舊的功能，這些功能會隨著保留原則和保留標籤繼續運作。</span><span class="sxs-lookup"><span data-stu-id="85f1a-434">If you currently use these older features, they will continue to work side-by-side with retention policies and retention labels.</span></span> <span data-ttu-id="85f1a-435">不過，建議您今後改為使用保留原則和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="85f1a-435">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="85f1a-436">它們提供單一機制來集中管理 Microsoft 365 內容的保留與刪除。</span><span class="sxs-lookup"><span data-stu-id="85f1a-436">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="85f1a-437">**來自 Exchange Online 的舊版功能：**</span><span class="sxs-lookup"><span data-stu-id="85f1a-437">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="85f1a-438">[保留標記和保留原則](https://go.microsoft.com/fwlink/?linkid=846125)，又稱為[通訊記錄管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="85f1a-438">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>

<span data-ttu-id="85f1a-439">**來自 SharePoint 和 OneDrive 的舊版功能：**</span><span class="sxs-lookup"><span data-stu-id="85f1a-439">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="85f1a-440">[文件刪除原則](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="85f1a-440">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="85f1a-441">[設定就地記錄管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (僅保留)</span><span class="sxs-lookup"><span data-stu-id="85f1a-441">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="85f1a-442">[網站關閉及刪除的使用原則](https://support.microsoft.com/zh-TW/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="85f1a-442">[Use policies for site closure and deletion](https://support.microsoft.com/zh-TW/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="85f1a-443">[資訊管理原則](intro-to-info-mgmt-policies.md) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="85f1a-443">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="85f1a-444">如果您已設定 SharePoint 網站的內容類型原則或資訊管理原則，以保留清單或文件庫的內容，當保留原則生效時，會忽略這些原則。</span><span class="sxs-lookup"><span data-stu-id="85f1a-444">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 

## <a name="related-information"></a><span data-ttu-id="85f1a-445">相關資訊</span><span class="sxs-lookup"><span data-stu-id="85f1a-445">Related information</span></span>

- [<span data-ttu-id="85f1a-446">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="85f1a-446">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="85f1a-447">Microsoft Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="85f1a-447">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="85f1a-448">協助您符合資訊管理與記錄管理法規需求的資源</span><span class="sxs-lookup"><span data-stu-id="85f1a-448">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)

## <a name="next-steps"></a><span data-ttu-id="85f1a-449">後續步驟</span><span class="sxs-lookup"><span data-stu-id="85f1a-449">Next steps</span></span>

<span data-ttu-id="85f1a-450">如果您已準備好建立保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="85f1a-450">If you are ready to create retention policies, see [Create and configure retention policies](create-retention-policies.md).</span></span>

<span data-ttu-id="85f1a-451">若要建立及套用保留標籤：</span><span class="sxs-lookup"><span data-stu-id="85f1a-451">To create and apply retention labels:</span></span>
- [<span data-ttu-id="85f1a-452">建立保留標籤，並在應用程式中使用這些標籤</span><span class="sxs-lookup"><span data-stu-id="85f1a-452">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="85f1a-453">自動將保留標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="85f1a-453">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

