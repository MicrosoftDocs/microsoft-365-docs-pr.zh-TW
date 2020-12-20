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
ms.openlocfilehash: c405f2bf8d9700c9a0874ba9d921a290ae63de16
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719343"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a><span data-ttu-id="8cd76-103">了解保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="8cd76-103">Learn about retention policies and retention labels</span></span>

><span data-ttu-id="8cd76-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="8cd76-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8cd76-p101">對大多數組織來說，其資料 (電子郵件、文件、即時訊息等) 的數量和複雜性日益增加。有效管理或控管此資訊至關重要，因為您需要：</span><span class="sxs-lookup"><span data-stu-id="8cd76-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="8cd76-107">**主動遵守產業規範和內部原則**，因此您需要將某些內容至少保留一段時間，例如，Sarbanes-Oxley 法案可能會要求您將某些類型的內容保留七年。</span><span class="sxs-lookup"><span data-stu-id="8cd76-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 

- <span data-ttu-id="8cd76-108">**降低發生訴訟或安全性漏洞的風險**，方法為永久刪除您不再需要保留的舊內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="8cd76-109">**協助貴組織有效分享知識並提高靈活度**，方法為確保使用者只使用目前和相關的內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="8cd76-110">您設定的保留設定可協助您實現所有目標。</span><span class="sxs-lookup"><span data-stu-id="8cd76-110">Retention settings that you configure can help you achieve all these goals.</span></span> <span data-ttu-id="8cd76-111">管理內容通常需要以下兩個動作：</span><span class="sxs-lookup"><span data-stu-id="8cd76-111">Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="8cd76-112">**保留** 內容，以便無法在保留期間結束之前將其永久刪除。</span><span class="sxs-lookup"><span data-stu-id="8cd76-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="8cd76-113">在保留期間結束之前，永久 **刪除** 內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    

<span data-ttu-id="8cd76-114">使用這兩個保留動作，您可以設定以下結果的保留設定：</span><span class="sxs-lookup"><span data-stu-id="8cd76-114">With these two retention actions, you can configure retention settings for the following outcomes:</span></span>

- <span data-ttu-id="8cd76-115">僅保留：永久持續保留內容或保留指定的一段時間。</span><span class="sxs-lookup"><span data-stu-id="8cd76-115">Retain-only: Retain content forever or for a specified period of time.</span></span>
- <span data-ttu-id="8cd76-116">僅刪除：指定一段時間後刪除內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-116">Delete-only: Delete content after a specified period of time.</span></span>
- <span data-ttu-id="8cd76-117">保留並刪除：將內容保留指定的時間，然後將其刪除。</span><span class="sxs-lookup"><span data-stu-id="8cd76-117">Retain and then delete: Retain content for a specified period of time and then delete it.</span></span>

<span data-ttu-id="8cd76-118">這些保留設定可以使用就地內容，從而在您基於合規性原因而必須保留內容時，節省建立和設定額外儲存體的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="8cd76-118">These retention settings work with content in place that saves you the additional overheads of creating and configuring additional storage when you need to retain content for compliance reasons.</span></span> <span data-ttu-id="8cd76-119">此外，您不必執行自訂的程序來複製及同步處理這項資料。</span><span class="sxs-lookup"><span data-stu-id="8cd76-119">In addition, you don't need to implement customized processes to copy and synchronize this data.</span></span>

## <a name="how-retention-settings-work-with-content-in-place"></a><span data-ttu-id="8cd76-120">保留設定如何與就地內容搭配使用</span><span class="sxs-lookup"><span data-stu-id="8cd76-120">How retention settings work with content in place</span></span>

<span data-ttu-id="8cd76-121">當內容有指派保留設定時，該內容會保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="8cd76-121">When content has retention settings assigned to it, that content remains in its original location.</span></span> <span data-ttu-id="8cd76-122">若未發生任何變更，人員可以繼續使用其文件或郵件。</span><span class="sxs-lookup"><span data-stu-id="8cd76-122">People can continue to work with their documents or mail as if nothing's changed.</span></span> <span data-ttu-id="8cd76-123">但如果人員編輯或刪除保留原則中包含的內容，則會自動保留內容複本。</span><span class="sxs-lookup"><span data-stu-id="8cd76-123">But if they edit or delete content that's included in the retention policy, a copy of the content is automatically retained.</span></span>
  
- <span data-ttu-id="8cd76-124">對於 SharePoint 和 OneDrive 網站：複本會保留在 **文件保留庫** 中。</span><span class="sxs-lookup"><span data-stu-id="8cd76-124">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span>

- <span data-ttu-id="8cd76-125">針對 Exchange 信箱：複本會保留在 **[可復原的項目]** 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="8cd76-125">For Exchange mailboxes: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="8cd76-126">針對 Teams 和 Yammer 訊息：複本會保留在名為 **SubstrateHolds** 的隱藏資料夾中，以作為 Exchange [可復原的項目 **]** 資料夾中的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="8cd76-126">For Teams and Yammer messages: The copy is retained in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="8cd76-127">[文件保留庫] 會佔用不受網站儲存空間配額限制的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="8cd76-127">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota.</span></span> <span data-ttu-id="8cd76-128">當您對 SharePoint 和 Microsoft 365 群組使用保留設定時，可能需要增加您的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="8cd76-128">You might need to increase your storage when you use retention settings for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="8cd76-129">大部分的人員無法檢視這些安全的位置和保留的內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-129">These secure locations and the retained content are not visible to most people.</span></span> <span data-ttu-id="8cd76-130">在大部分的情況下，使用者甚至不需要知道其內容受保留設定的限制。</span><span class="sxs-lookup"><span data-stu-id="8cd76-130">In most cases, people do not even need to know that their content is subject to retention settings.</span></span>

<span data-ttu-id="8cd76-131">如需有關保留設定如何配合不同工作負載使用的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="8cd76-131">For more detailed information about how retention settings work for different workloads, see the following articles:</span></span>

- [<span data-ttu-id="8cd76-132">了解 SharePoint 和 OneDrive 的保留功能</span><span class="sxs-lookup"><span data-stu-id="8cd76-132">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="8cd76-133">了解 Microsoft Teams 保留</span><span class="sxs-lookup"><span data-stu-id="8cd76-133">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="8cd76-134">了解 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="8cd76-134">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="8cd76-135">了解 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="8cd76-135">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="8cd76-136">保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="8cd76-136">Retention policies and retention labels</span></span>

<span data-ttu-id="8cd76-137">您可以透過標籤原則同時使用保留原則和保留標籤，以將保留設定指派給內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-137">You can use both retention policies and retention labels with label policies to assign your retention settings to content.</span></span> 

<span data-ttu-id="8cd76-138">使用保留原則為網站或信箱層級的內容指派相同的保留設定，並使用保留標籤來指派項目層級 (資料夾、文件、電子郵件) 的保留設定。</span><span class="sxs-lookup"><span data-stu-id="8cd76-138">Use a retention policy to assign the same retention settings for content at a site or mailbox level, and use a retention label to assign retention settings at an item level (folder, document, email).</span></span>

<span data-ttu-id="8cd76-139">例如，如果 SharePoint 網站中的所有文件都應該保留 5 年，使用保留原則比將相同的保留標籤套用至該網站中所有文件的方法更有效率。</span><span class="sxs-lookup"><span data-stu-id="8cd76-139">For example, if all documents in a SharePoint site should be retained for 5 years, it's more efficient to do this with a retention policy than apply the same retention label to all documents in that site.</span></span> <span data-ttu-id="8cd76-140">不過，如果該網站中的部分文件應保留 5 年，而其他文件保留 10 年，一個保留原則就不夠用。</span><span class="sxs-lookup"><span data-stu-id="8cd76-140">However, if some documents in that site should be retained for 5 years and others retained for 10 years, a retention policy wouldn't be able to do this.</span></span> <span data-ttu-id="8cd76-141">當您必須在項目層級指定保留設定時，請使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-141">When you need to specify retention settings at the item level, use retention labels.</span></span> 

<span data-ttu-id="8cd76-142">不同於保留原則，保留標籤的保留設定會隨著內容移至您 Microsoft 365 租用戶中不同的位置。</span><span class="sxs-lookup"><span data-stu-id="8cd76-142">Unlike retention policies, retention settings from retention labels travel with the content if it’s moved to a different location within your Microsoft 365 tenant.</span></span> <span data-ttu-id="8cd76-143">此外，保留標籤具有以下保留原則不支援的功能：</span><span class="sxs-lookup"><span data-stu-id="8cd76-143">In addition, retention labels have the following capabilities that retention policies don't support:</span></span> 
 
- <span data-ttu-id="8cd76-144">除了內容的年限或上次修改時間以外，還可選擇從為內容加上標籤的時間或根據事件來開始保留期間的選項。</span><span class="sxs-lookup"><span data-stu-id="8cd76-144">Options to start the retention period from when the content was labeled or based on an event, in addition to the age of the content or when it was last modified.</span></span>

- <span data-ttu-id="8cd76-145">使用[可訓練分類器](classifier-learn-about.md)來識別要加上標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-145">Use [trainable classifiers](classifier-learn-about.md) to identify content to label.</span></span>

- <span data-ttu-id="8cd76-146">為 SharePoint 文件套用預設標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-146">Apply a default label for SharePoint documents.</span></span>

- <span data-ttu-id="8cd76-147">支援[處置檢閱](disposition-reviews.md) 以在內容永久刪除之前檢閱。</span><span class="sxs-lookup"><span data-stu-id="8cd76-147">Support [disposition review](disposition-reviews.md) to review the content before it's permanently deleted.</span></span>

- <span data-ttu-id="8cd76-148">將內容標示為做為標籤設定一部分的[記錄](records-management.md#records)，並且在保留期間結束而刪除內容時，永遠都有 [處置證明](disposition.md#disposition-of-records) 。</span><span class="sxs-lookup"><span data-stu-id="8cd76-148">Mark the content as a [record](records-management.md#records) as part of the label settings, and always have [proof of disposition](disposition.md#disposition-of-records) when content is deleted at the end of its retention period.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="8cd76-149">保留原則</span><span class="sxs-lookup"><span data-stu-id="8cd76-149">Retention policies</span></span>

<span data-ttu-id="8cd76-150">保留原則可以套用到以下位置：</span><span class="sxs-lookup"><span data-stu-id="8cd76-150">Retention policies can be applied to the following locations:</span></span>
- <span data-ttu-id="8cd76-151">Exchange 電子郵件</span><span class="sxs-lookup"><span data-stu-id="8cd76-151">Exchange email</span></span>
- <span data-ttu-id="8cd76-152">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="8cd76-152">SharePoint site</span></span>
- <span data-ttu-id="8cd76-153">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="8cd76-153">OneDrive accounts</span></span>
- <span data-ttu-id="8cd76-154">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="8cd76-154">Microsoft 365 Groups</span></span>
- <span data-ttu-id="8cd76-155">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="8cd76-155">Skype for Business</span></span>
- <span data-ttu-id="8cd76-156">Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="8cd76-156">Exchange public folders</span></span>
- <span data-ttu-id="8cd76-157">Teams 通道訊息</span><span class="sxs-lookup"><span data-stu-id="8cd76-157">Teams channel messages</span></span>
- <span data-ttu-id="8cd76-158">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="8cd76-158">Teams chats</span></span>
- <span data-ttu-id="8cd76-159">Yammer 社群訊息</span><span class="sxs-lookup"><span data-stu-id="8cd76-159">Yammer community messages</span></span>
- <span data-ttu-id="8cd76-160">Yammer 私人訊息</span><span class="sxs-lookup"><span data-stu-id="8cd76-160">Yammer private messages</span></span>

<span data-ttu-id="8cd76-161">您可以輕鬆地將單一原則套用到多個位置，或特定位置或使用者。</span><span class="sxs-lookup"><span data-stu-id="8cd76-161">You can very efficiently apply a single policy to multiple locations, or to specific locations or users.</span></span>

<span data-ttu-id="8cd76-162">保留期間開始時，您可以選擇建立內容的時間，或者只支援檔案和 SharePoint、OneDrive 和 Microsoft 365 群組位置 (上次修改內容的時間) 的時間。</span><span class="sxs-lookup"><span data-stu-id="8cd76-162">For the start of the retention period, you can choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Microsoft 365 Groups locations, when the content was last modified.</span></span>

<span data-ttu-id="8cd76-163">專案會從保留原則指定的容器繼承保留設定。</span><span class="sxs-lookup"><span data-stu-id="8cd76-163">Items inherit the retention settings from their container specified in the retention policy.</span></span> <span data-ttu-id="8cd76-164">如果在爲了保留内容而設定原則時將專案移至容器外，則會在工作負荷的安全位置保留該專案的複本。</span><span class="sxs-lookup"><span data-stu-id="8cd76-164">If they are then moved outside that container when the policy is configured to retain content, a copy of that item is retained in the workload's secured location.</span></span> <span data-ttu-id="8cd76-165">不過，保留設定不會隨著內容移至新的位置。</span><span class="sxs-lookup"><span data-stu-id="8cd76-165">However, the retention settings don't travel with the content in its new location.</span></span> <span data-ttu-id="8cd76-166">如有需要，請使用保留標籤，而非保留原則。</span><span class="sxs-lookup"><span data-stu-id="8cd76-166">If that's required, use retention labels instead of retention policies.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="8cd76-167">保留標籤</span><span class="sxs-lookup"><span data-stu-id="8cd76-167">Retention labels</span></span>

<span data-ttu-id="8cd76-168">請針對需要不同保留設定的不同類型的內容，使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-168">Use retention labels for different types of content that require different retention settings.</span></span> <span data-ttu-id="8cd76-169">例如：</span><span class="sxs-lookup"><span data-stu-id="8cd76-169">For example:</span></span>
  
- <span data-ttu-id="8cd76-170">至少必須保留一小段時間的稅務表單。</span><span class="sxs-lookup"><span data-stu-id="8cd76-170">Tax forms that need to be retained for a minimum period of time.</span></span> 
    
- <span data-ttu-id="8cd76-171">到達特定年限之後需要永久刪除的新聞材料。</span><span class="sxs-lookup"><span data-stu-id="8cd76-171">Press materials that need to be permanently deleted when they reach a specific age.</span></span> 
    
- <span data-ttu-id="8cd76-172">需要先保留一段期間之然後再永久刪除的競爭力研究。</span><span class="sxs-lookup"><span data-stu-id="8cd76-172">Competitive research that needs to be retained for a specific period and then permanently deleted.</span></span> 
    
- <span data-ttu-id="8cd76-173">必須標示為記錄使之無法編輯或刪除的工作簽證。</span><span class="sxs-lookup"><span data-stu-id="8cd76-173">Work visas that must be marked as a record so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="8cd76-174">在這些情況下，保留標籤可讓您在項目層級 (文件或電子郵件) 套用治理控制的保留設定。</span><span class="sxs-lookup"><span data-stu-id="8cd76-174">In all these cases, retention labels let you apply retention settings for governance control at the item level (document or email).</span></span>
  
<span data-ttu-id="8cd76-175">使用保留標籤，您可以：</span><span class="sxs-lookup"><span data-stu-id="8cd76-175">With retention labels, you can:</span></span>
  
- <span data-ttu-id="8cd76-176">**讓貴組織中的人員手動將保留標籤套用** 至網頁上的 Outlook 和 Outlook、OneDrive、SharePoint 和 Microsoft 365 群組中的內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-176">**Enable people in your organization to apply a retention label manually** to content in Outlook and Outlook on the web, OneDrive, SharePoint, and Microsoft 365 groups.</span></span> <span data-ttu-id="8cd76-177">使用者通常都清楚知道自己處理的內容類型，因此可將內容分類並套用適當的保留設定。</span><span class="sxs-lookup"><span data-stu-id="8cd76-177">Users often know best what type of content they're working with, so they can classify it and have the appropriate retention settings applied.</span></span> 
    
- <span data-ttu-id="8cd76-178">在當內容符合特定條件時 **自動將保留標籤套用到內容**，例如內容包含：</span><span class="sxs-lookup"><span data-stu-id="8cd76-178">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    - <span data-ttu-id="8cd76-179">特定類型的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="8cd76-179">Specific types of sensitive information.</span></span>
    - <span data-ttu-id="8cd76-180">特定關鍵字符合您建立的查詢。</span><span class="sxs-lookup"><span data-stu-id="8cd76-180">Specific keywords that match a query you create.</span></span>
    - <span data-ttu-id="8cd76-181">可訓練分類器的模式比對。</span><span class="sxs-lookup"><span data-stu-id="8cd76-181">Pattern matches for a trainable classifier.</span></span>

- <span data-ttu-id="8cd76-182">針對 SharePoint 網站和 OneDrive 帳戶中的文件和電子郵件項目 (行事曆項除外)，**從內容加上標籤起就開始保留期間**。</span><span class="sxs-lookup"><span data-stu-id="8cd76-182">**Start the retention period from when the content was labeled** for documents in SharePoint sites and OneDrive accounts, and to email items with the exception of calendar items.</span></span> <span data-ttu-id="8cd76-183">如果您將具有此設定的保留標籤套用於行事曆項目，則保留期間從其傳送日期開始。</span><span class="sxs-lookup"><span data-stu-id="8cd76-183">If you apply a retention label with this configuration to a calendar item, the retention period starts from when it is sent.</span></span>

- <span data-ttu-id="8cd76-184">**當事件發生時 (例如員工離開組織或合約到期)，開始保留期間**。</span><span class="sxs-lookup"><span data-stu-id="8cd76-184">**Start the retention period when an event occurs**, such as employees leave the organization, or contracts expire.</span></span>

- <span data-ttu-id="8cd76-185">**將預設保留標籤套用至 SharePoint 中的文件庫、資料夾或文件集**，以便儲存在該位置中的所有文件都繼承預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-185">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that are stored in that location inherit the default retention label.</span></span>

<span data-ttu-id="8cd76-186">此外，保留標籤支援跨 Microsoft 365 應用程式和服務的電子郵件和文件[記錄管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-186">Additionally, retention labels support [records management](records-management.md) for email and documents across Microsoft 365 apps and services.</span></span> <span data-ttu-id="8cd76-187">您可以使用保留標籤將內容標記為記錄。</span><span class="sxs-lookup"><span data-stu-id="8cd76-187">You can use a retention label to mark items as a record.</span></span> <span data-ttu-id="8cd76-188">發生此情況且內容仍保留在 Microsoft 365 中時，標籤會針對法規原因可能所需的內容施加進一步的限制。</span><span class="sxs-lookup"><span data-stu-id="8cd76-188">When this happens and the content remains in Microsoft 365, the label places further restrictions on the content that might be needed for regulatory reasons.</span></span> <span data-ttu-id="8cd76-189">如需詳細資訊，請參閱 [比較允許或封鎖動作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-189">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

<span data-ttu-id="8cd76-190">與[敏感度標籤](sensitivity-labels.md)不同，如果內容是移至 Microsoft 365 以外的位置，保留標籤不會保留。</span><span class="sxs-lookup"><span data-stu-id="8cd76-190">Retention labels, unlike [sensitivity labels](sensitivity-labels.md), do not persist if the content is moved outside Microsoft 365.</span></span>

<span data-ttu-id="8cd76-191">針對租用戶支援的保留標籤數量沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="8cd76-191">There is no limit to the number of retention labels that are supported for a tenant.</span></span> <span data-ttu-id="8cd76-192">不過，10,000 個是針對租用戶支援的原則數目上限，其中包括會套用標籤 (保留標籤原則和自動套用保留原則) 的原則，以及保留原則。</span><span class="sxs-lookup"><span data-stu-id="8cd76-192">However, 10,000 is the maximum number of policies that are supported for a tenant and these include the policies that apply the labels (retention label policies and auto-apply retention policies), as well as retention policies.</span></span>

#### <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="8cd76-193">將內容分類而不套用任何動作</span><span class="sxs-lookup"><span data-stu-id="8cd76-193">Classifying content without applying any actions</span></span>

<span data-ttu-id="8cd76-194">雖然保留標籤的主要目的是要保留或刪除內容，但您也可以在不開啟任何保留或其他動作的情況下使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-194">Although the main purpose of retention labels is to retain or delete content, you can also use retention labels without turning on any retention or other actions.</span></span> <span data-ttu-id="8cd76-195">在此情況下，您可以使用保留標籤當做文字標籤，而不強制執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="8cd76-195">In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="8cd76-196">例如，您可以建立並套用名為「稍後檢閱」的保留標籤，而不執行任何動作，然後使用該標籤於稍後尋找該內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-196">For example, you can create and apply a retention label named "Review later" with no actions, and then use that label to find that content later.</span></span>
  
![僅限分類的標籤設定](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="8cd76-198">使用保留標籤作為 DLP 原則的條件</span><span class="sxs-lookup"><span data-stu-id="8cd76-198">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="8cd76-199">您可以將保留標籤做為 SharePoint 文件的資料外洩防護 (DLP) 原則中的條件。</span><span class="sxs-lookup"><span data-stu-id="8cd76-199">You can specify a retention label as a condition in a data loss prevention (DLP) policy for documents in SharePoint.</span></span> <span data-ttu-id="8cd76-200">例如，設定 DLP 原則以防止文件在組織外共用 (如果已套用指定的保留標籤)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-200">For example, configure a DLP policy to prevent documents from being shared outside the organization if they have a specified retention label applied to it.</span></span>

<span data-ttu-id="8cd76-201">如需詳細資訊，請參閱[使用保留標籤做為 DLP 原則中的條件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-201">For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

#### <a name="retention-labels-and-policies-that-apply-them"></a><span data-ttu-id="8cd76-202">保留標籤和套用其標籤的原則</span><span class="sxs-lookup"><span data-stu-id="8cd76-202">Retention labels and policies that apply them</span></span>

<span data-ttu-id="8cd76-203">保留標籤是獨立、可重複使用的建置組塊。</span><span class="sxs-lookup"><span data-stu-id="8cd76-203">Retention labels are independent, reusable building blocks.</span></span> <span data-ttu-id="8cd76-204">保留標籤原則的主要目的是將一組保留標籤分組，以及指定您想讓這些標籤出現的目標位置。</span><span class="sxs-lookup"><span data-stu-id="8cd76-204">The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear.</span></span> <span data-ttu-id="8cd76-205">然後，系統管理員和使用者可以將這些標籤套用至這些位置中的內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-205">Then, admins and users can apply those labels to content in those locations.</span></span>
  
![標籤、標籤原則和位置圖表](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
<span data-ttu-id="8cd76-207">當您發佈保留標籤時，會將這些標籤包含在保留標籤原則中，好讓系統管理員和使用者選擇：</span><span class="sxs-lookup"><span data-stu-id="8cd76-207">When you publish retention labels, they're included in a retention label policy that make them available for admins and users to select:</span></span>

- <span data-ttu-id="8cd76-208">單一保留標籤可納入多個保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="8cd76-208">A single retention label can be included in many retention label policies.</span></span>

- <span data-ttu-id="8cd76-209">保留標籤原則會指定要發佈保留標籤的位置。</span><span class="sxs-lookup"><span data-stu-id="8cd76-209">Retention label policies specify the locations to publish the retention labels.</span></span>

- <span data-ttu-id="8cd76-210">單一位置也可納入多個保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="8cd76-210">A single location can also be included in many retention label policies.</span></span>

<span data-ttu-id="8cd76-211">除了保留標籤原則以外，您也可以建立一或多個自動套用原則，每一個都有單一保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-211">In addition to retention label policies, you can also create one or more auto-apply policies, each with a single retention label.</span></span> <span data-ttu-id="8cd76-212">使用此原則，當您在原則中指定的條件滿足時，將自動套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-212">With this policy, a retention label is automatically applied when conditions that you specify in the policy are met.</span></span>

#### <a name="retention-label-policies-and-locations"></a><span data-ttu-id="8cd76-213">保留標籤原則與位置</span><span class="sxs-lookup"><span data-stu-id="8cd76-213">Retention label policies and locations</span></span>

<span data-ttu-id="8cd76-214">可以將不同類型的保留標籤發佈到不同的位置，視保留標籤的功能而定。</span><span class="sxs-lookup"><span data-stu-id="8cd76-214">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
| <span data-ttu-id="8cd76-215">如果保留標籤是...</span><span class="sxs-lookup"><span data-stu-id="8cd76-215">If the retention label is…</span></span> | <span data-ttu-id="8cd76-216">標籤原則可套用至…</span><span class="sxs-lookup"><span data-stu-id="8cd76-216">Then the label policy can be applied to…</span></span> |
|:-----|:-----|
|<span data-ttu-id="8cd76-217">已發佈給系統管理員和使用者</span><span class="sxs-lookup"><span data-stu-id="8cd76-217">Published to admins and end users</span></span>  <br/> |<span data-ttu-id="8cd76-218">Exchange、SharePoint、OneDrive、Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="8cd76-218">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
|<span data-ttu-id="8cd76-219">根據敏感資訊類型或可訓練分類器而自動套用</span><span class="sxs-lookup"><span data-stu-id="8cd76-219">Auto-applied based on sensitive information types or trainable classifiers</span></span>  <br/> |<span data-ttu-id="8cd76-220">Exchange (僅限所有信箱)、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="8cd76-220">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="8cd76-221">根據查詢而自動套用</span><span class="sxs-lookup"><span data-stu-id="8cd76-221">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="8cd76-222">Exchange、SharePoint、OneDrive、Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="8cd76-222">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
   
<span data-ttu-id="8cd76-223">在 Exchange 中，您只能在新傳送的郵件 (傳輸中的資料) 上自動套用保留標籤功能，而非目前在信箱中的所有郵件 (待用資料)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-223">In Exchange, auto-apply retention labels are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="8cd76-224">此外，您只能在所有信箱中為敏感性資訊類型和可訓練分類器來自動套用保留標籤功能，但無法選取特定信箱。</span><span class="sxs-lookup"><span data-stu-id="8cd76-224">Also, auto-apply retention labels for sensitive information types and trainable classifiers apply to all mailboxes; you can't select specific mailboxes.</span></span>
  
<span data-ttu-id="8cd76-225">Exchange 公用資料夾、Skype、Teams 和 Yammer 訊息不支援保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-225">Exchange public folders, Skype, Teams and Yammer messages do not support retention labels.</span></span> <span data-ttu-id="8cd76-226">若要保留或刪除這些位置中的內容，請改用保留原則。</span><span class="sxs-lookup"><span data-stu-id="8cd76-226">To retain and delete contain from these locations, use retention policies instead.</span></span>

#### <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="8cd76-227">一次只能有一個保留標籤</span><span class="sxs-lookup"><span data-stu-id="8cd76-227">Only one retention label at a time</span></span>

<span data-ttu-id="8cd76-228">電子郵件或文件等內容一次只能套用一個保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-228">An email or document can have only a single retention label applied to it at a time.</span></span> <span data-ttu-id="8cd76-229">保留標籤可以由使用者或管理員[手動](create-apply-retention-labels.md#manually-apply-retention-labels)套用，也可以使用以下任一方法自動套用：</span><span class="sxs-lookup"><span data-stu-id="8cd76-229">A retention label can be applied [manually](create-apply-retention-labels.md#manually-apply-retention-labels) by an end user or admin, or automatically by using any of the following methods:</span></span>

- [<span data-ttu-id="8cd76-230">自動套用標籤原則</span><span class="sxs-lookup"><span data-stu-id="8cd76-230">Auto-apply label policy</span></span>](apply-retention-labels-automatically.md)
- [<span data-ttu-id="8cd76-231">SharePoint Syntex 中的文件瞭解模型</span><span class="sxs-lookup"><span data-stu-id="8cd76-231">Document understanding model for SharePoint Syntex</span></span>](https://docs.microsoft.com/microsoft-365/contentunderstanding/apply-a-retention-label-to-a-model)
- <span data-ttu-id="8cd76-232">[SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) 或 [Outlook 的預設標籤](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="8cd76-232">[Default label for SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) or [Outlook](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>
- [<span data-ttu-id="8cd76-233">Outlook 規則</span><span class="sxs-lookup"><span data-stu-id="8cd76-233">Outlook rules</span></span>](create-apply-retention-labels.md#automatically-applying-a-retention-label-to-email-by-using-rules)

<span data-ttu-id="8cd76-234">對於標準保留標籤 (它們不會將項目標記為[記錄或監管記錄](records-management.md#records))：</span><span class="sxs-lookup"><span data-stu-id="8cd76-234">For standard retention labels (they don't mark items as a [record or regulatory record](records-management.md#records)):</span></span>

- <span data-ttu-id="8cd76-235">系統管理員和使用者可以手動變更或移除套用於內容的現有保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-235">Admins and end users can manually change or remove an existing retention label that's applied on content.</span></span> 

- <span data-ttu-id="8cd76-236">當內容已套用保留標籤時，現有標籤不會自動移除或替換為另一個保留標籤，但有一個可能的例外：現有標籤已作為預設標籤套用。</span><span class="sxs-lookup"><span data-stu-id="8cd76-236">When content already has a retention label applied, the existing label won't be automatically removed or replaced by another retention label with one possible exception: The existing label was applied as a default label.</span></span>
    
    <span data-ttu-id="8cd76-237">有關使用預設標籤套用標籤行為的詳細資訊，請執行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8cd76-237">For more information about the label behavior when it's applied by using a default label:</span></span>
    - <span data-ttu-id="8cd76-238">SharePoint 的預設標籤：[對 SharePoint 使用預設標籤時的標籤行為](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span><span class="sxs-lookup"><span data-stu-id="8cd76-238">Default label for SharePoint: [Label behavior when you use a default label for SharePoint](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span></span>
    - <span data-ttu-id="8cd76-239">Outlook 的預設標籤：[將預設保留標籤套用於 Outlook 資料夾](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="8cd76-239">Default label for Outlook: [Applying a default retention label to an Outlook folder](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>

- <span data-ttu-id="8cd76-240">如果有多個自動套用標籤原則可以套用保留標籤，並且內容滿足多個原則的條件，則套用最舊的自動套用標籤原則 (按建立日期) 的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-240">If there are multiple auto-apply label policies that could apply a retention label, and content meets the conditions of multiple policies, the retention label for the oldest auto-apply label policy (by date created) is applied.</span></span>

<span data-ttu-id="8cd76-241">當保留標籤將項目標記為記錄或監管記錄時，這些標籤不會自動變更。</span><span class="sxs-lookup"><span data-stu-id="8cd76-241">When retention labels mark items as a record or a regulatory record, these labels are never automatically changed.</span></span> <span data-ttu-id="8cd76-242">只有容器的管理員才能手動變更或移除將項目標記為記錄而不是監管記錄的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-242">Only admins for the container can manually change or remove retention labels that mark items as a record, but not regulatory records.</span></span> <span data-ttu-id="8cd76-243">如需詳細資訊，請參閱 [比較允許或封鎖動作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-243">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

#### <a name="monitoring-retention-labels"></a><span data-ttu-id="8cd76-244">監視保留標籤</span><span class="sxs-lookup"><span data-stu-id="8cd76-244">Monitoring retention labels</span></span>

<span data-ttu-id="8cd76-245">在 Microsoft 365 合規性中心中，使用 **資料分類** > **概觀** 來監視保留標籤在租用戶中的使用方式，並識別標籤項目的位置。</span><span class="sxs-lookup"><span data-stu-id="8cd76-245">From the Microsoft 365 compliance center, use **Data classification** > **Overview** to monitor how your retention labels are being used in your tenant, and identify where your labeled items are located.</span></span> <span data-ttu-id="8cd76-246">如需詳細資訊 (包括重要先決條件)，請參閱[了解您的資料 - 資料分類概觀](data-classification-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-246">For more information, including important prerequisites, see [Know your data - data classification overview](data-classification-overview.md).</span></span>

<span data-ttu-id="8cd76-247">然後您可以使用[內容總管](data-classification-content-explorer.md)和[活動總管](data-classification-activity-explorer.md)深入探討詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8cd76-247">You can then drill down into details by using [content explorer](data-classification-content-explorer.md) and [activity explorer](data-classification-activity-explorer.md).</span></span>

> [!TIP]
><span data-ttu-id="8cd76-248">請考慮使用一些其他的資料分類深入解析 (例如可訓練分類器和敏感性資訊類型)，協助您識別可能需要保留或刪除的內容，或管理記錄。</span><span class="sxs-lookup"><span data-stu-id="8cd76-248">Consider using some of the other data classification insights, such as trainable classifiers and sensitive info types, to help you identify content that you might need to retain or delete, or manage as records.</span></span>

<span data-ttu-id="8cd76-249">Office 365 安全性與合規性中心具有來自 **資訊控管** > **儀表板** 的保留標籤同等概觀資訊，以及來自 **資訊控管** > **標籤活動總管** 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8cd76-249">The Office 365 Security & Compliance Center has the equivalent overview information for retention labels from **Information governance** > **Dashboard**, and more detailed information from **Information governance** > **Label activity explorer**.</span></span> <span data-ttu-id="8cd76-250">如需從此舊版系統管理中心監視保留標籤的詳細資訊，請參閱下列文件：</span><span class="sxs-lookup"><span data-stu-id="8cd76-250">For more information about monitoring retention labels from this older admin center, see the following documentation:</span></span>
- [<span data-ttu-id="8cd76-251">檢視資料控管報告</span><span class="sxs-lookup"><span data-stu-id="8cd76-251">View the data governance reports</span></span>](view-the-data-governance-reports.md)
- [<span data-ttu-id="8cd76-252">利用標籤分析檢視標籤使用量</span><span class="sxs-lookup"><span data-stu-id="8cd76-252">View label usage with label analytics</span></span>](label-analytics.md)
- [<span data-ttu-id="8cd76-253">檢視文件的標籤活動</span><span class="sxs-lookup"><span data-stu-id="8cd76-253">View label activity for documents</span></span>](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a><span data-ttu-id="8cd76-254">使用內容搜尋來尋找具有特定保留標籤的所有內容</span><span class="sxs-lookup"><span data-stu-id="8cd76-254">Using Content Search to find all content with a specific retention label</span></span>

<span data-ttu-id="8cd76-255">將保留標籤套用至內容後 (無論是由使用者套用或自動套用)，您可以使用內容搜尋來尋找已套用特定保留標籤的所有項目。</span><span class="sxs-lookup"><span data-stu-id="8cd76-255">After retention labels are applied to content, either by users or auto-applied, you can use content search to find all items that have a specific retention label applied.</span></span>

<span data-ttu-id="8cd76-256">當您建立內容搜尋時，請選擇 **[保留標籤]** 條件，然後輸入完整的保留標籤名稱或是部分標籤名稱，再使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="8cd76-256">When you create a content search, choose the **Retention label** condition, and then enter the complete retention label name or part of the label name and use a wildcard.</span></span> <span data-ttu-id="8cd76-257">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-257">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![保留標籤條件](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a><span data-ttu-id="8cd76-259">比較保留原則和保留標籤的功能</span><span class="sxs-lookup"><span data-stu-id="8cd76-259">Compare capabilities for retention policies and retention labels</span></span>

<span data-ttu-id="8cd76-260">使用下列表格來協助您判斷是否要根據功能來使用保留原則或保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-260">Use the following table to help you identify whether to use a retention policy or retention label, based on capabilities.</span></span>

|<span data-ttu-id="8cd76-261">功能</span><span class="sxs-lookup"><span data-stu-id="8cd76-261">Capability</span></span>|<span data-ttu-id="8cd76-262">保留原則</span><span class="sxs-lookup"><span data-stu-id="8cd76-262">Retention policy</span></span> |<span data-ttu-id="8cd76-263">保留標籤</span><span class="sxs-lookup"><span data-stu-id="8cd76-263">Retention label</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8cd76-264">可以保留然後刪除、僅保留或僅刪除的保留設定</span><span class="sxs-lookup"><span data-stu-id="8cd76-264">Retention settings that can retain and then delete, retain-only, or delete-only</span></span> |<span data-ttu-id="8cd76-265">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-265">Yes</span></span> |<span data-ttu-id="8cd76-266">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-266">Yes</span></span> |
|<span data-ttu-id="8cd76-267">支援的工作負載：</span><span class="sxs-lookup"><span data-stu-id="8cd76-267">Workloads supported:</span></span> <br /><span data-ttu-id="8cd76-268">- Exchange</span><span class="sxs-lookup"><span data-stu-id="8cd76-268">- Exchange</span></span> <br /><span data-ttu-id="8cd76-269">- SharePoint</span><span class="sxs-lookup"><span data-stu-id="8cd76-269">- SharePoint</span></span> <br /><span data-ttu-id="8cd76-270">- OneDrive</span><span class="sxs-lookup"><span data-stu-id="8cd76-270">- OneDrive</span></span> <br /><span data-ttu-id="8cd76-271">- Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="8cd76-271">- Microsoft 365 groups</span></span> <br /><span data-ttu-id="8cd76-272">- 商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="8cd76-272">- Skype for Business</span></span> <br /><span data-ttu-id="8cd76-273">- Teams</span><span class="sxs-lookup"><span data-stu-id="8cd76-273">- Teams</span></span><br /><span data-ttu-id="8cd76-274">- Yammer</span><span class="sxs-lookup"><span data-stu-id="8cd76-274">- Yammer</span></span>|<br /> <span data-ttu-id="8cd76-275">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-275">Yes</span></span> <br /> <span data-ttu-id="8cd76-276">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-276">Yes</span></span> <br /> <span data-ttu-id="8cd76-277">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-277">Yes</span></span> <br /> <span data-ttu-id="8cd76-278">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-278">Yes</span></span> <br /> <span data-ttu-id="8cd76-279">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-279">Yes</span></span> <br /> <span data-ttu-id="8cd76-280">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-280">Yes</span></span> <br /> <span data-ttu-id="8cd76-281">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-281">Yes</span></span> | <br /> <span data-ttu-id="8cd76-282">是，除了公用資料夾</span><span class="sxs-lookup"><span data-stu-id="8cd76-282">Yes, except public folders</span></span> <br /> <span data-ttu-id="8cd76-283">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-283">Yes</span></span> <br /> <span data-ttu-id="8cd76-284">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-284">Yes</span></span> <br /> <span data-ttu-id="8cd76-285">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-285">Yes</span></span> <br /> <span data-ttu-id="8cd76-286">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-286">No</span></span> <br /> <span data-ttu-id="8cd76-287">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-287">No</span></span> <br /> <span data-ttu-id="8cd76-288">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-288">No</span></span> |
|<span data-ttu-id="8cd76-289">自動套用的保留</span><span class="sxs-lookup"><span data-stu-id="8cd76-289">Retention applied automatically</span></span> | <span data-ttu-id="8cd76-290">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-290">Yes</span></span> | <span data-ttu-id="8cd76-291">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-291">Yes</span></span> |
|<span data-ttu-id="8cd76-292">根據條件套用保留</span><span class="sxs-lookup"><span data-stu-id="8cd76-292">Retention applied based on conditions</span></span> <br /> <span data-ttu-id="8cd76-293">- 敏感資訊類型、KQL 查詢和關鍵字、可訓練分類器</span><span class="sxs-lookup"><span data-stu-id="8cd76-293">- sensitive info types, KQL queries and keywords, trainable classifiers</span></span>| <span data-ttu-id="8cd76-294">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-294">No</span></span> | <span data-ttu-id="8cd76-295">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-295">Yes</span></span> |
|<span data-ttu-id="8cd76-296">手動套用的保留</span><span class="sxs-lookup"><span data-stu-id="8cd76-296">Retention applied manually</span></span> | <span data-ttu-id="8cd76-297">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-297">No</span></span> | <span data-ttu-id="8cd76-298">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-298">Yes</span></span> |
|<span data-ttu-id="8cd76-299">使用者的 UI 目前狀態</span><span class="sxs-lookup"><span data-stu-id="8cd76-299">UI presence for end users</span></span> | <span data-ttu-id="8cd76-300">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-300">No</span></span> | <span data-ttu-id="8cd76-301">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-301">Yes</span></span> |
|<span data-ttu-id="8cd76-302">如果內容已移動，則會持續存在</span><span class="sxs-lookup"><span data-stu-id="8cd76-302">Persists if the content is moved</span></span> | <span data-ttu-id="8cd76-303">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-303">No</span></span> | <span data-ttu-id="8cd76-304">是，在您的 Microsoft 365 租用戶中</span><span class="sxs-lookup"><span data-stu-id="8cd76-304">Yes, within your Microsoft 365 tenant</span></span> |
|<span data-ttu-id="8cd76-305">將項目宣告為記錄</span><span class="sxs-lookup"><span data-stu-id="8cd76-305">Declare item as a record</span></span>| <span data-ttu-id="8cd76-306">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-306">No</span></span> | <span data-ttu-id="8cd76-307">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-307">Yes</span></span> |
|<span data-ttu-id="8cd76-308">在加上標籤起或根據事件來開始保留期間</span><span class="sxs-lookup"><span data-stu-id="8cd76-308">Start the retention period when labeled or based on an event</span></span> | <span data-ttu-id="8cd76-309">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-309">No</span></span> | <span data-ttu-id="8cd76-310">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-310">Yes</span></span> |
|<span data-ttu-id="8cd76-311">處置檢閱</span><span class="sxs-lookup"><span data-stu-id="8cd76-311">Disposition review</span></span> | <span data-ttu-id="8cd76-312">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-312">No</span></span>| <span data-ttu-id="8cd76-313">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-313">Yes</span></span> |
|<span data-ttu-id="8cd76-314">最高 7 年的處置證明</span><span class="sxs-lookup"><span data-stu-id="8cd76-314">Proof of disposition for up to 7 years</span></span> | <span data-ttu-id="8cd76-315">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-315">No</span></span> |<span data-ttu-id="8cd76-316">是，當物料宣告為記錄時</span><span class="sxs-lookup"><span data-stu-id="8cd76-316">Yes, when item is declared a record</span></span>|
|<span data-ttu-id="8cd76-317">稽核系統管理員活動</span><span class="sxs-lookup"><span data-stu-id="8cd76-317">Audit admin activities</span></span>| <span data-ttu-id="8cd76-318">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-318">Yes</span></span> | <span data-ttu-id="8cd76-319">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-319">Yes</span></span>|
|<span data-ttu-id="8cd76-320">識別要保留的項目：</span><span class="sxs-lookup"><span data-stu-id="8cd76-320">Identify items subject to retention:</span></span> <br /> <span data-ttu-id="8cd76-321">- 內容搜尋</span><span class="sxs-lookup"><span data-stu-id="8cd76-321">- Content Search</span></span> <br /> <span data-ttu-id="8cd76-322">- 資料分類頁面、內容總管，活動總管</span><span class="sxs-lookup"><span data-stu-id="8cd76-322">- Data classification page, content explorer, activity explorer</span></span> | <br /> <span data-ttu-id="8cd76-323">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-323">No</span></span> <br /> <span data-ttu-id="8cd76-324">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-324">No</span></span> | <br /> <span data-ttu-id="8cd76-325">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-325">Yes</span></span> <br /> <span data-ttu-id="8cd76-326">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-326">Yes</span></span>|

<span data-ttu-id="8cd76-327">請注意，您可以使用保留原則和保留標籤做為補充保留方法。</span><span class="sxs-lookup"><span data-stu-id="8cd76-327">Note that you can use both retention policies and retention labels as complementary retention methods.</span></span> <span data-ttu-id="8cd76-328">例如：</span><span class="sxs-lookup"><span data-stu-id="8cd76-328">For example:</span></span>

1. <span data-ttu-id="8cd76-329">您建立並設定將在內容上次修改後五年自動刪除內容的保留原則，並將該原則套用於所有 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="8cd76-329">You create and configure a retention policy that automatically deletes content five years after it's last modified, and apply the policy to all OneDrive accounts.</span></span>

2. <span data-ttu-id="8cd76-330">您建立並設定永久保留內容的保留標籤，並將其新增至您發佈到所有 OneDrive 帳戶的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="8cd76-330">You create and configure a retention label that keeps content forever and add this to a label policy that you publish to all OneDrive accounts.</span></span> <span data-ttu-id="8cd76-331">您向使用者說明如何手動將此標籤套用於五年後未修改應從自動刪除排除的特定文件。</span><span class="sxs-lookup"><span data-stu-id="8cd76-331">You explain to users how to manually apply this label to specific documents that should be excluded from automatic deletion if not modified after five years.</span></span>

<span data-ttu-id="8cd76-332">有關保留原則和保留標籤如何搭配，以及如何判斷其合併結果的更多資訊，請參閱下一節解釋保留的原則和其優先順序。</span><span class="sxs-lookup"><span data-stu-id="8cd76-332">For more information about how retention policies and retention labels work together and how to determine their combined outcome, see the next section that explains the principles of retention and what takes precedence.</span></span>

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="8cd76-333">原則保留或何者優先</span><span class="sxs-lookup"><span data-stu-id="8cd76-333">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="8cd76-334">與保留標籤不同，您可以對同一內容套用多個保留原則。</span><span class="sxs-lookup"><span data-stu-id="8cd76-334">Unlike retention labels, you can apply more than one retention policy to the same content.</span></span> <span data-ttu-id="8cd76-335">每個保留原則都可能導致一個保留動作和一個刪除動作。</span><span class="sxs-lookup"><span data-stu-id="8cd76-335">Each retention policy can result in a retain action and a delete action.</span></span> <span data-ttu-id="8cd76-336">此外，該項也可以透過保留標籤執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="8cd76-336">Additionally, that item could also be subject to these actions from a retention label.</span></span>

<span data-ttu-id="8cd76-337">在這種情況下，當項目可能受到多個可能相互衝突的保留設定的約束時，確定結果的優先順序是什麼？</span><span class="sxs-lookup"><span data-stu-id="8cd76-337">In this scenario, when items can be subject to multiple retention settings that could conflict with one another, what takes precedence to determine the outcome?</span></span>

<span data-ttu-id="8cd76-338">結果不是哪一個保留原則或單個保留標籤優先採用，而是項目被保留多長時間 (如果適用) 以及何時删除項目 (如果適用)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-338">The outcome isn't which single retention policy or single retention label wins, but how long an item is retained (if applicable) and when an item is deleted (if applicable).</span></span> <span data-ttu-id="8cd76-339">這兩個動作是根據套用於項目的所有保留設定獨立計算的。</span><span class="sxs-lookup"><span data-stu-id="8cd76-339">These two actions are calculated independently from each other, from all the retention settings applied to an item.</span></span>

<span data-ttu-id="8cd76-340">例如，項目可能受一個為只删除動作設定的保留原則和另一個設定為保留然後删除的保留原則的約束。</span><span class="sxs-lookup"><span data-stu-id="8cd76-340">For example, an item might be subject to one retention policy that is configured for a delete-only action, and another retention policy that is configured to retain and then delete.</span></span> <span data-ttu-id="8cd76-341">因此，此項只有一個保留動作和兩個刪除動作。</span><span class="sxs-lookup"><span data-stu-id="8cd76-341">Consequently, this item has just one retain action but two delete actions.</span></span> <span data-ttu-id="8cd76-342">保留和删除動作可能會彼此相互衝突，並且這兩個删除動作的日期可能有衝突。</span><span class="sxs-lookup"><span data-stu-id="8cd76-342">The retention and deletion actions could be in conflict with one another and the two deletion actions might have a conflicting date.</span></span> <span data-ttu-id="8cd76-343">若要達成結果，您必須套用保留原則。</span><span class="sxs-lookup"><span data-stu-id="8cd76-343">To work out the outcome, you must apply the principles of retention.</span></span>

<span data-ttu-id="8cd76-344">在高層級中，您可以確保保留永遠優先於刪除，然後最長的保留期間勝出。</span><span class="sxs-lookup"><span data-stu-id="8cd76-344">At a high level, you can be assured that retention always takes precedence over deletion, and the longest retention period wins.</span></span> <span data-ttu-id="8cd76-345">這兩個簡單的規則總是决定項目將被保留多長時間。</span><span class="sxs-lookup"><span data-stu-id="8cd76-345">These two simple rules always decide how long an item will be retained.</span></span>

<span data-ttu-id="8cd76-346">决定何時删除項目還有幾個因素，其中包括從保留標籤中删除動作始終優先於從保留原則中删除動作。</span><span class="sxs-lookup"><span data-stu-id="8cd76-346">There are a few more factors that determine when an item will be deleted, which include the delete action from a retention label always takes precedence over the delete action from a retention policy.</span></span>

<span data-ttu-id="8cd76-347">使用以下流程來瞭解單個項目的保留和删除結果，其中每個層級從上到下都起到了「核心分裂」的作用。</span><span class="sxs-lookup"><span data-stu-id="8cd76-347">Use the following flow to understand the retention and deletion outcomes for a single item, where each level acts as a tie-breaker from top to bottom.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cd76-348">如果使用的是保留標籤：在使用此流程確定同一項目上多個保留設定的結果之前，請確保您知道[套用了哪個保留標籤](#only-one-retention-label-at-a-time)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-348">If you are using retention labels: Before using this flow to determine the outcome of multiple retention settings on the same item, make sure you know [which retention label is applied](#only-one-retention-label-at-a-time).</span></span>

![原則保留圖](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="8cd76-350">四個不同層級的說明：</span><span class="sxs-lookup"><span data-stu-id="8cd76-350">Explanation for the four different levels:</span></span>
  
1. <span data-ttu-id="8cd76-351">**保留優先於刪除。**</span><span class="sxs-lookup"><span data-stu-id="8cd76-351">**Retention wins over deletion.**</span></span> <span data-ttu-id="8cd76-352">如果內容還具有保留設定，則不會永久删除該內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-352">Content won't be permanently deleted when it also has retention settings to retain it.</span></span>  
    
    <span data-ttu-id="8cd76-353">範例：電子郵件受 Exchange 保留原則的約束，該原則設定為在三年後删除項目，並且套用了保留標籤，該標籤設定為保留項目五年。</span><span class="sxs-lookup"><span data-stu-id="8cd76-353">Example: An email message is subject to a retention policy for Exchange that is configured to delete items after three years and it also has a retention label applied that is configured to retain items for five years.</span></span>
    
    <span data-ttu-id="8cd76-354">此電子郵件保留五年，因為此保留動作優先於删除動作。</span><span class="sxs-lookup"><span data-stu-id="8cd76-354">The email message is retained for five years because this retention action takes precedence over deletion.</span></span> <span data-ttu-id="8cd76-355">由於延遲删除動作，電子郵件將在五年時間結束時被删除。</span><span class="sxs-lookup"><span data-stu-id="8cd76-355">The email message is deleted at the end of the five years because of the deferred delete action.</span></span>

2. <span data-ttu-id="8cd76-356">**最長保留期間優先。**</span><span class="sxs-lookup"><span data-stu-id="8cd76-356">**The longest retention period wins.**</span></span> <span data-ttu-id="8cd76-357">如果內容受制於在不同的期間保留內容的多個保留設定，則該內容將一直保留到最長保留期間結束為止。</span><span class="sxs-lookup"><span data-stu-id="8cd76-357">If content is subject to multiple retention settings that retain content for different periods of time, the content will be retained until the end of the longest retention period.</span></span>
    
    <span data-ttu-id="8cd76-358">範例：Marketing SharePoint 網站中的文件受兩個保留原則的約束。</span><span class="sxs-lookup"><span data-stu-id="8cd76-358">Example: Documents in the Marketing SharePoint site are subject to two retention policies.</span></span> <span data-ttu-id="8cd76-359">為所有 SharePoint 網站設定了第一個保留原則，以將項目保留五年。</span><span class="sxs-lookup"><span data-stu-id="8cd76-359">The first retention policy is configured for all SharePoint sites to retain items for five years.</span></span> <span data-ttu-id="8cd76-360">第二個保留原則是為特定的 SharePoint 網站設定的，以將項目保留十年。</span><span class="sxs-lookup"><span data-stu-id="8cd76-360">The second retention policy is configured for specific SharePoint sites to retain items for ten years.</span></span>
    
    <span data-ttu-id="8cd76-361">此 Marketing SharePoint 網站中的文件保留十年，因為這是最長的保留期。</span><span class="sxs-lookup"><span data-stu-id="8cd76-361">Documents in this Marketing SharePoint site are retained for ten years because that's the longest retention period.</span></span>

3. <span data-ttu-id="8cd76-362">**明確優先於隱含。**</span><span class="sxs-lookup"><span data-stu-id="8cd76-362">**Explicit wins over implicit.**</span></span> <span data-ttu-id="8cd76-363">適用於確定删除項目的時間：</span><span class="sxs-lookup"><span data-stu-id="8cd76-363">Applicable to determine when items will be deleted:</span></span> 
    
    1. <span data-ttu-id="8cd76-364">與保留原則相比，保留標籤 (無論套用的是什麼) 提供明確保留，因為保留設定套用於單個項目，而不是從容器隱含分配。</span><span class="sxs-lookup"><span data-stu-id="8cd76-364">A retention label (however it was applied) provides explicit retention in comparison with retention policies, because the retention settings are applied to an individual item rather than implicitly assigned from a container.</span></span> <span data-ttu-id="8cd76-365">這意味著從保留標籤執行的删除動作始終優先於任何保留原則中的删除動作。</span><span class="sxs-lookup"><span data-stu-id="8cd76-365">This means that a delete action from a retention label always takes precedence over a delete action from any retention policy.</span></span>
        
        <span data-ttu-id="8cd76-366">範例：文件受兩個保留原則的約束，這兩個原則的删除動作分別為 5 年和 10 年，保留標籤的删除動作為 7 年。</span><span class="sxs-lookup"><span data-stu-id="8cd76-366">Example: A document is subject to two retention policies that have a delete action of five years and ten years respectively, and also a retention label that has a delete action of seven years.</span></span>
        
        <span data-ttu-id="8cd76-367">文件在七年後被删除，因為從保留標籤中的删除動作優先。</span><span class="sxs-lookup"><span data-stu-id="8cd76-367">The document is deleted after seven years because the delete action from the retention label takes precedence.</span></span>
    
    2. <span data-ttu-id="8cd76-368">只有保留原則時：如果某個位置的保留原則的作用域是使用包含設定 (例如 Exchange 電子郵件的特定使用者)，則對於同一位置，保留原則優先於未限定範圍的保留原則。</span><span class="sxs-lookup"><span data-stu-id="8cd76-368">When you have retention policies only: If a retention policy for a location is scoped to use an include configuration (such as specific users for Exchange email) that retention policy takes precedence over unscoped retention policies for the same location.</span></span>
        
        <span data-ttu-id="8cd76-369">未限定範圍的保留原則是指在不指定特定實例的情况下選取位置。</span><span class="sxs-lookup"><span data-stu-id="8cd76-369">An unscoped retention policy is where a location is selected without specifying specific instances.</span></span> <span data-ttu-id="8cd76-370">例如，**Exchange 電子郵件** 和 **[所有收件人]** 的預設設置都是未限定範圍的保留原則。</span><span class="sxs-lookup"><span data-stu-id="8cd76-370">For example, **Exchange email** and the default setting of **All recipients** is an unscoped retention policy.</span></span> <span data-ttu-id="8cd76-371">或者，**SharePoint 網站** 和 **所有網站** 的預設設定。</span><span class="sxs-lookup"><span data-stu-id="8cd76-371">Or, **SharePoint sites** and the default setting of **All sites**.</span></span> <span data-ttu-id="8cd76-372">當確定保留原則的作用域時，它們在此層級上具有相同的優先順序。</span><span class="sxs-lookup"><span data-stu-id="8cd76-372">When retention policies are scoped, they have equal precedence at this level.</span></span>
        
        <span data-ttu-id="8cd76-373">範例 1：電子郵件受兩個保留原則的約束。</span><span class="sxs-lookup"><span data-stu-id="8cd76-373">Example 1: An email message is subject to two retention policies.</span></span> <span data-ttu-id="8cd76-374">第一個保留原則是未限定範圍的，並在 10 年後删除項目。</span><span class="sxs-lookup"><span data-stu-id="8cd76-374">The first retention policy is unscoped and deletes items after ten years.</span></span> <span data-ttu-id="8cd76-375">第二個保留原則的範圍是特定郵箱，並在五年後删除項目。</span><span class="sxs-lookup"><span data-stu-id="8cd76-375">The second retention policy is scoped to specific mailboxes and deletes items after five years.</span></span>
        
        <span data-ttu-id="8cd76-376">電子郵件在五年後被删除，因為範圍保留原則中的删除動作優先於未限定範圍的保留原則。</span><span class="sxs-lookup"><span data-stu-id="8cd76-376">The email message is deleted after five years because the deletion action from the scoped retention policy takes precedence over the unscoped retention policy.</span></span>
        
        <span data-ttu-id="8cd76-377">範例 2：使用者 OneDrive 帳戶中的文件受兩個保留原則的約束。</span><span class="sxs-lookup"><span data-stu-id="8cd76-377">Example 2: A document in a user's OneDrive account is subject to two retention policies.</span></span> <span data-ttu-id="8cd76-378">第一個保留原則的範圍是包括此使用者的 OneDrive 帳戶，並在 10 年後執行删除動作。</span><span class="sxs-lookup"><span data-stu-id="8cd76-378">The first retention policy is scoped to include this user's OneDrive account and has a delete action after 10 years.</span></span> <span data-ttu-id="8cd76-379">第二個保留原則的範圍是包括此使用者的 OneDrive 帳戶，並在七年後執行删除動作。</span><span class="sxs-lookup"><span data-stu-id="8cd76-379">The second retention policy is scoped to include this user's OneDrive account and has a delete action after seven years.</span></span>
        
        <span data-ttu-id="8cd76-380">無法在此層級確定何時删除此文件，因為這兩個保留原則都有範圍。</span><span class="sxs-lookup"><span data-stu-id="8cd76-380">When this document will be deleted can't be determined at this level because both retention policies are scoped.</span></span>

4. <span data-ttu-id="8cd76-381">**最短刪除期間優先。**</span><span class="sxs-lookup"><span data-stu-id="8cd76-381">**The shortest deletion period wins.**</span></span> <span data-ttu-id="8cd76-382">適用於確定何時從保留原則中删除項目，並且無法從上一層級解析結果：在最短保留期結束時删除內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-382">Applicable to determine when items will be deleted from retention policies and the outcome couldn't be resolved from the previous level: Content is deleted at the end of the shortest retention period.</span></span>
    
    <span data-ttu-id="8cd76-383">範例：使用者 OneDrive 帳戶中的文件受兩個保留原則的約束。</span><span class="sxs-lookup"><span data-stu-id="8cd76-383">Example: A document in a user's OneDrive account is subject to two retention policies.</span></span> <span data-ttu-id="8cd76-384">第一個保留原則的範圍是包括此使用者的 OneDrive 帳戶，並在 10 年後執行删除動作。</span><span class="sxs-lookup"><span data-stu-id="8cd76-384">The first retention policy is scoped to include this user's OneDrive account and has a delete action after 10 years.</span></span> <span data-ttu-id="8cd76-385">第二個保留原則的範圍是包括此使用者的 OneDrive 帳戶，並在七年後執行删除動作。</span><span class="sxs-lookup"><span data-stu-id="8cd76-385">The second retention policy is scoped to include this user's OneDrive account and has a delete action after seven years.</span></span>
    
    <span data-ttu-id="8cd76-386">此檔案將在七年後删除，因為這是這兩個範圍內保留原則的最短保留期。</span><span class="sxs-lookup"><span data-stu-id="8cd76-386">This document will be deleted after seven years because that's the shortest retention period for these two scoped retention policies.</span></span>

<span data-ttu-id="8cd76-387">請注意，受 eDiscovery 保留約束的項目也屬於保留的第一準則；任何保留原則或保留標籤都不能删除它們。</span><span class="sxs-lookup"><span data-stu-id="8cd76-387">Note that items subject to eDiscovery hold also fall under the first principle of retention; they cannot be deleted by any retention policy or retention label.</span></span> <span data-ttu-id="8cd76-388">當解除保留後，保留準則繼續適用於他們。</span><span class="sxs-lookup"><span data-stu-id="8cd76-388">When that hold is released, the principles of retention continue to apply to them.</span></span> <span data-ttu-id="8cd76-389">例如，它們可能會受到未到期的保留期或延遲的删除動作的影響。</span><span class="sxs-lookup"><span data-stu-id="8cd76-389">For example, they could then be subject to an unexpired retention period or a deferred delete action.</span></span>

<span data-ttu-id="8cd76-390">結合保留和删除動作的更複雜的範例：</span><span class="sxs-lookup"><span data-stu-id="8cd76-390">More complex examples that combine retain and delete actions:</span></span>

1. <span data-ttu-id="8cd76-391">項目套用了以下保留設定：</span><span class="sxs-lookup"><span data-stu-id="8cd76-391">An item has the following retention settings applied to it:</span></span>
    
    - <span data-ttu-id="8cd76-392">僅在五年後删除的保留原則</span><span class="sxs-lookup"><span data-stu-id="8cd76-392">A retention policy for delete-only after five years</span></span>
    - <span data-ttu-id="8cd76-393">保留三年然後删除的保留原則</span><span class="sxs-lookup"><span data-stu-id="8cd76-393">A retention policy that retains for three years and then deletes</span></span>
    - <span data-ttu-id="8cd76-394">只保留七年的保留標籤</span><span class="sxs-lookup"><span data-stu-id="8cd76-394">A retention label that retains-only for seven years</span></span>
    
    <span data-ttu-id="8cd76-395">**結果**：該項目保留七年，因為保留優先於删除，七年是最長的保留期。</span><span class="sxs-lookup"><span data-stu-id="8cd76-395">**Outcome**: The item is retained for seven years because retention takes precedence over deletion and seven years is the longest retention period.</span></span> <span data-ttu-id="8cd76-396">在保留期結束時，由於保留原則中的删除動作在保留項目時被延后，因此將删除該項目。</span><span class="sxs-lookup"><span data-stu-id="8cd76-396">At the end of this retention period, the item is deleted because of the delete action from the retention policies that was deferred while the item was retained.</span></span>
    
    <span data-ttu-id="8cd76-397">雖然這兩個保留原則的删除動作的日期不同，但可以删除的項目最早是在最長保留期結束時，因此不存在要解决的衝突。</span><span class="sxs-lookup"><span data-stu-id="8cd76-397">Although the two retention policies have different dates for the delete actions, the earliest the item can be deleted is at the end of the longest retention period, so there is no conflict to resolve.</span></span>

2.  <span data-ttu-id="8cd76-398">項目套用了以下保留設定：</span><span class="sxs-lookup"><span data-stu-id="8cd76-398">An item has the following retention settings applied to it:</span></span>
    
    - <span data-ttu-id="8cd76-399">一種未限定範圍的保留原則，僅在 10 年後删除</span><span class="sxs-lookup"><span data-stu-id="8cd76-399">An unscoped retention policy that deletes-only after ten years</span></span>
    - <span data-ttu-id="8cd76-400">保留五年，然後删除的限定範圍的保留原則</span><span class="sxs-lookup"><span data-stu-id="8cd76-400">A scoped retention policy that retains for five years and then deletes</span></span>
    - <span data-ttu-id="8cd76-401">保留三年然後删除的保留標籤</span><span class="sxs-lookup"><span data-stu-id="8cd76-401">A retention label that retains for three years and then deletes</span></span>
    
    <span data-ttu-id="8cd76-402">**結果**：這個項目保留五年，因為這是最長的保留期。</span><span class="sxs-lookup"><span data-stu-id="8cd76-402">**Outcome**: The item is retained for fives years because that's the longest retention period.</span></span> <span data-ttu-id="8cd76-403">在該保留期結束時，該項目將被删除，因為在保留該項目的同時，保留標籤的三年后删除動作被延遲。</span><span class="sxs-lookup"><span data-stu-id="8cd76-403">At the end of that retention period, the item is deleted because of the delete action of three years from the retention label that was deferred while the item was retained.</span></span> <span data-ttu-id="8cd76-404">保留標籤中的删除優先於從所有保留原則中的删除。</span><span class="sxs-lookup"><span data-stu-id="8cd76-404">Deletion from retention labels take precedence over deletion from all retention policies.</span></span>

## <a name="use-preservation-lock-to-restrict-changes-to-policies"></a><span data-ttu-id="8cd76-405">使用「保留鎖定」來限制原則變更</span><span class="sxs-lookup"><span data-stu-id="8cd76-405">Use Preservation Lock to restrict changes to policies</span></span>

<span data-ttu-id="8cd76-406">有些組織可能需要遵守由控管機構定義的規則，例如證券交易委員會 (SEC) 規定 17a-4，要求在保留原則開啟之後，不能關閉或執行較不嚴格的限制。</span><span class="sxs-lookup"><span data-stu-id="8cd76-406">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a policy for retention is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="8cd76-407">「保留鎖定」可確保您的組織能夠符合這類法規需求，因為它會鎖定保留原則或保留標籤原則，使得沒有任何人 (包括系統管理員) 可以關閉原則、刪除原則或降低限制。</span><span class="sxs-lookup"><span data-stu-id="8cd76-407">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy or retention label policy so that no one—including an administrator—can turn off the policy, delete the policy, or make it less restrictive.</span></span>
  
<span data-ttu-id="8cd76-408">建立保留原則或保留標籤原則之後，您可以套用「保留鎖定」。</span><span class="sxs-lookup"><span data-stu-id="8cd76-408">You apply Preservation Lock after the retention policy or retention label policy is created.</span></span> <span data-ttu-id="8cd76-409">如需更多資訊和指示，請參閲[使用保留鎖定來限制變更保留原則和保留標籤原則](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-409">For more information and instructions, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="releasing-a-policy-for-retention"></a><span data-ttu-id="8cd76-410">發佈保留原則</span><span class="sxs-lookup"><span data-stu-id="8cd76-410">Releasing a policy for retention</span></span>

<span data-ttu-id="8cd76-411">如果您的保留原則沒有保留鎖定，您可以隨時刪除您的原則，以便有效地關閉先前套用的保留設定。</span><span class="sxs-lookup"><span data-stu-id="8cd76-411">Providing your policies for retention don't have a Preservation Lock, you can delete your policies at any time, which effectively turns off the previously applied retention settings.</span></span> <span data-ttu-id="8cd76-412">您也可以維持原有的保留原則，但將位置狀態變更為 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="8cd76-412">You can also keep the policy but change the location status to off.</span></span>
 
<span data-ttu-id="8cd76-413">當您這麼做時，保留在文件保留庫中的任何 SharePoint 或 OneDrive 的內容不會立即永久被刪除。</span><span class="sxs-lookup"><span data-stu-id="8cd76-413">When you do either of these actions, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="8cd76-414">相反地，為了防止意外的資料遺失，我們有 30 天的寬限期，在這期間，保留文件庫中不會發生該原則的內容到期，因此，如有需要，您可以在這裡還原任何內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-414">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="8cd76-415">此外，您無法在寬限期期間手動刪除此內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-415">Additionally, you can't manually delete this content during the grace period.</span></span>

<span data-ttu-id="8cd76-416">您可以在寬限期期間將位置狀態變更為 [開啟]，這麼一來，該原則的內容將不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="8cd76-416">You can change the location status back to on during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="8cd76-417">SharePoint 和 OneDrive 中的此 30 天寬限期與 Exchange 中的 30 天延遲保留對應。</span><span class="sxs-lookup"><span data-stu-id="8cd76-417">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="8cd76-418">如需詳細資訊，請參閱[管理延遲保留信箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-418">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

## <a name="auditing-retention-configuration"></a><span data-ttu-id="8cd76-419">稽核保留設定</span><span class="sxs-lookup"><span data-stu-id="8cd76-419">Auditing retention configuration</span></span>

<span data-ttu-id="8cd76-420">[啟用稽核功能](turn-audit-log-search-on-or-off.md)後，系統會將保留原則和保留標籤的系統管理員動作儲存至稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="8cd76-420">Administrator actions for retention policies and retention labels are saved to the audit log when [auditing is enabled](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="8cd76-421">例如，建立、設定或刪除保留原則或標籤後，系統會建立稽核事件。</span><span class="sxs-lookup"><span data-stu-id="8cd76-421">For example, an audit event is created when a retention policy or label is created, configured, or deleted.</span></span> <span data-ttu-id="8cd76-422">如需完整清單，請參閱[保留原則和保留標籤活動](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-422">For the full list, see [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).</span></span>

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a><span data-ttu-id="8cd76-423">保留原則和保留標籤的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8cd76-423">PowerShell cmdlets for retention policies and retention labels</span></span>

<span data-ttu-id="8cd76-424">若要使用保留 Cmdlet，您必須先[連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-424">To use the retention cmdlets, you must first [connect to the Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="8cd76-425">然後使用以下任一 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8cd76-425">Then, use any of the following cmdlets:</span></span>

- [<span data-ttu-id="8cd76-426">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="8cd76-426">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [<span data-ttu-id="8cd76-427">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="8cd76-427">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [<span data-ttu-id="8cd76-428">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="8cd76-428">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [<span data-ttu-id="8cd76-429">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="8cd76-429">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [<span data-ttu-id="8cd76-430">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="8cd76-430">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [<span data-ttu-id="8cd76-431">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="8cd76-431">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [<span data-ttu-id="8cd76-432">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="8cd76-432">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [<span data-ttu-id="8cd76-433">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="8cd76-433">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [<span data-ttu-id="8cd76-434">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="8cd76-434">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [<span data-ttu-id="8cd76-435">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="8cd76-435">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [<span data-ttu-id="8cd76-436">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="8cd76-436">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [<span data-ttu-id="8cd76-437">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="8cd76-437">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [<span data-ttu-id="8cd76-438">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="8cd76-438">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [<span data-ttu-id="8cd76-439">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="8cd76-439">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a><span data-ttu-id="8cd76-440">何時使用保留原則和保留標籤或電子文件探索保留？</span><span class="sxs-lookup"><span data-stu-id="8cd76-440">When to use retention policies and retention labels or eDiscovery holds</span></span>

<span data-ttu-id="8cd76-441">雖然您使用保留設定和[電子文件探索案例所建立的保留](create-ediscovery-holds.md)都可以防止資料永久刪除，但它們是為不同情況而設計的。</span><span class="sxs-lookup"><span data-stu-id="8cd76-441">Although retention settings and [holds that you create with an eDiscovery case](create-ediscovery-holds.md) can both prevent data from being permanently deleted, they are designed for different scenarios.</span></span> <span data-ttu-id="8cd76-442">若要協助您了解差異及決定使用哪個，請使用下列指南：</span><span class="sxs-lookup"><span data-stu-id="8cd76-442">To help you understand the differences and decide which to use, use the following guidance:</span></span>

- <span data-ttu-id="8cd76-443">您在 [保留原則] 和 [保留標籤] 中指定的保留設定，是專為長期資訊控管而設計，以保留或刪除符合法規需求的資料。</span><span class="sxs-lookup"><span data-stu-id="8cd76-443">Retention settings that you specify in retention policies and retention labels are designed for a long-term information governance strategy to retain or delete data for compliance requirements.</span></span> <span data-ttu-id="8cd76-444">範圍通常很廣，主要重點是位置和內容，而不是個別使用者。</span><span class="sxs-lookup"><span data-stu-id="8cd76-444">The scope is usually broad with the main focus being the location and content rather than individual users.</span></span> <span data-ttu-id="8cd76-445">保留期間的開始和結束是可設定的，可選擇自動刪除內容，而不需要其他系統管理員介入。</span><span class="sxs-lookup"><span data-stu-id="8cd76-445">The start and end of the retention period is configurable, with the option to automatically delete content without additional administrator intervention.</span></span>

- <span data-ttu-id="8cd76-446">電子文件探索的保留 (核心電子文件探索或進階電子文件探索案例) 是專為保留資料以供法律調查所設計。</span><span class="sxs-lookup"><span data-stu-id="8cd76-446">Holds for eDiscovery (either Core eDiscovery or Advanced eDiscovery cases) are designed for a limited duration to preserve data for a legal investigation.</span></span> <span data-ttu-id="8cd76-447">該範圍是特定的，且重點是已識別使用者所擁有的內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-447">The scope is specific with the focus being content owned by identified users.</span></span> <span data-ttu-id="8cd76-448">保留期間的開始和結束不會進行設定，但與個別系統管理員的動作相關，沒有選項可在保留解除時自動刪除內容。</span><span class="sxs-lookup"><span data-stu-id="8cd76-448">The start and end of the preservation period isn't configurable but dependent on individual administrator actions, without an option to automatically delete content when the hold is released.</span></span>

<span data-ttu-id="8cd76-449">比較保留與電子文件探索保留的摘要：</span><span class="sxs-lookup"><span data-stu-id="8cd76-449">Summary to compare retention with holds:</span></span>

|<span data-ttu-id="8cd76-450">考量事項</span><span class="sxs-lookup"><span data-stu-id="8cd76-450">Consideration</span></span>|<span data-ttu-id="8cd76-451">保留</span><span class="sxs-lookup"><span data-stu-id="8cd76-451">Retention</span></span> |<span data-ttu-id="8cd76-452">電子文件探索保留</span><span class="sxs-lookup"><span data-stu-id="8cd76-452">eDiscovery holds</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8cd76-453">商務需求：</span><span class="sxs-lookup"><span data-stu-id="8cd76-453">Business need:</span></span> |<span data-ttu-id="8cd76-454">合規性</span><span class="sxs-lookup"><span data-stu-id="8cd76-454">Compliance</span></span> |<span data-ttu-id="8cd76-455">法律資訊</span><span class="sxs-lookup"><span data-stu-id="8cd76-455">Legal</span></span> |
|<span data-ttu-id="8cd76-456">時間範圍：</span><span class="sxs-lookup"><span data-stu-id="8cd76-456">Time scope:</span></span> |<span data-ttu-id="8cd76-457">長期</span><span class="sxs-lookup"><span data-stu-id="8cd76-457">Long-term</span></span> |<span data-ttu-id="8cd76-458">短期</span><span class="sxs-lookup"><span data-stu-id="8cd76-458">Short-term</span></span> |
|<span data-ttu-id="8cd76-459">焦點：</span><span class="sxs-lookup"><span data-stu-id="8cd76-459">Focus:</span></span> |<span data-ttu-id="8cd76-460">廣泛的、內容型</span><span class="sxs-lookup"><span data-stu-id="8cd76-460">Broad, content-based</span></span> |<span data-ttu-id="8cd76-461">特定的、使用者型</span><span class="sxs-lookup"><span data-stu-id="8cd76-461">Specific, user-based</span></span> |
|<span data-ttu-id="8cd76-462">開始和結束日期可設定：</span><span class="sxs-lookup"><span data-stu-id="8cd76-462">Start and end date configurable:</span></span> |<span data-ttu-id="8cd76-463">是</span><span class="sxs-lookup"><span data-stu-id="8cd76-463">Yes</span></span> |<span data-ttu-id="8cd76-464">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-464">No</span></span> |
|<span data-ttu-id="8cd76-465">內容刪除：</span><span class="sxs-lookup"><span data-stu-id="8cd76-465">Content deletion:</span></span> |<span data-ttu-id="8cd76-466">是 (選用)</span><span class="sxs-lookup"><span data-stu-id="8cd76-466">Yes (optional)</span></span> |<span data-ttu-id="8cd76-467">否</span><span class="sxs-lookup"><span data-stu-id="8cd76-467">No</span></span> |
|<span data-ttu-id="8cd76-468">系統管理開銷：</span><span class="sxs-lookup"><span data-stu-id="8cd76-468">Administrative overheads:</span></span> |<span data-ttu-id="8cd76-469">低</span><span class="sxs-lookup"><span data-stu-id="8cd76-469">Low</span></span> |<span data-ttu-id="8cd76-470">高</span><span class="sxs-lookup"><span data-stu-id="8cd76-470">High</span></span> |

<span data-ttu-id="8cd76-471">如果內容同時受制於保留設定和電子文件探索保留，則電子文件探索保留的內容保留永遠優先。</span><span class="sxs-lookup"><span data-stu-id="8cd76-471">If content is subject to both retention settings and an eDiscovery hold, preserving content for the eDiscovery hold always takes precedence.</span></span> <span data-ttu-id="8cd76-472">如此一來，[保留的原則](#the-principles-of-retention-or-what-takes-precedence)會擴充至電子文件探索保留，因為系統會在管理員手動解除保留之前，將資料保留。</span><span class="sxs-lookup"><span data-stu-id="8cd76-472">In this way, the [principles of retention](#the-principles-of-retention-or-what-takes-precedence) expand to eDiscovery holds because they preserve data until an administrator manually releases the hold.</span></span> <span data-ttu-id="8cd76-473">不過，儘管這個優先順序，請不要將電子文件探索保留用於長期資訊控管。</span><span class="sxs-lookup"><span data-stu-id="8cd76-473">However, despite this precedence, don't use eDiscovery holds for long-term information governance.</span></span> <span data-ttu-id="8cd76-474">如果您擔心自動刪除資料，您可以設定保留設定以永遠保留項目，或對保留標籤使用[處置評審](disposition.md#disposition-reviews)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-474">If you are concerned about automatic deletion of data, you can configure retention settings to retain items forever, or use [disposition review](disposition.md#disposition-reviews) with retention labels.</span></span>

<span data-ttu-id="8cd76-475">如果您使用舊版電子文件探索工具來保留資料，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="8cd76-475">If you are using older eDiscovery tools to preserve data, see the following resources:</span></span>

- <span data-ttu-id="8cd76-476">Exchange：</span><span class="sxs-lookup"><span data-stu-id="8cd76-476">Exchange:</span></span> 
    - [<span data-ttu-id="8cd76-477">就地保留與訴訟資料暫留</span><span class="sxs-lookup"><span data-stu-id="8cd76-477">In-Place Hold and Litigation Hold</span></span>](https://go.microsoft.com/fwlink/?linkid=846124)
    - <span data-ttu-id="8cd76-478">[如何找出位於 Exchange Online 信箱的保留類型](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox) (英文)</span><span class="sxs-lookup"><span data-stu-id="8cd76-478">[How to identify the type of hold placed on an Exchange Online mailbox](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox)</span></span>

- <span data-ttu-id="8cd76-479">SharePoint 和 OneDrive：</span><span class="sxs-lookup"><span data-stu-id="8cd76-479">SharePoint and OneDrive:</span></span> 
    - <span data-ttu-id="8cd76-480">[在電子文件探索中心將內容新增至案例及保留來源](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (英文)</span><span class="sxs-lookup"><span data-stu-id="8cd76-480">[Add content to a case and place sources on hold in the eDiscovery Center](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)</span></span>

- [<span data-ttu-id="8cd76-481">舊版電子文件探索工具淘汰</span><span class="sxs-lookup"><span data-stu-id="8cd76-481">Retirement of legacy eDiscovery tools</span></span>](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a><span data-ttu-id="8cd76-482">請使用保留原則和保留標籤，而非舊版的功能</span><span class="sxs-lookup"><span data-stu-id="8cd76-482">Use retention policies and retention labels instead of older features</span></span>

<span data-ttu-id="8cd76-483">如果您必要在 Microsoft 365 中預先主動保留或刪除內容，我們建議您使用保留原則和保留標籤，而非以下較舊的功能。</span><span class="sxs-lookup"><span data-stu-id="8cd76-483">If you need to proactively retain or delete content in Microsoft 365 for information governance, we recommend that you use retention policies and retention labels instead of the following older features.</span></span>

<span data-ttu-id="8cd76-484">如果您目前使用這些較舊的功能，這些功能會隨著保留原則和保留標籤繼續運作。</span><span class="sxs-lookup"><span data-stu-id="8cd76-484">If you currently use these older features, they will continue to work side-by-side with retention policies and retention labels.</span></span> <span data-ttu-id="8cd76-485">不過，建議您今後改為使用保留原則和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8cd76-485">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="8cd76-486">它們提供單一機制來集中管理 Microsoft 365 內容的保留與刪除。</span><span class="sxs-lookup"><span data-stu-id="8cd76-486">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="8cd76-487">**來自 Exchange Online 的舊版功能：**</span><span class="sxs-lookup"><span data-stu-id="8cd76-487">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="8cd76-488">[保留標記和保留原則](https://go.microsoft.com/fwlink/?linkid=846125)，又稱為[通訊記錄管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="8cd76-488">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>

<span data-ttu-id="8cd76-489">**來自 SharePoint 和 OneDrive 的舊版功能：**</span><span class="sxs-lookup"><span data-stu-id="8cd76-489">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="8cd76-490">[文件刪除原則](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="8cd76-490">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="8cd76-491">[設定就地記錄管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (僅保留)</span><span class="sxs-lookup"><span data-stu-id="8cd76-491">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="8cd76-492">[網站關閉及刪除的使用原則](https://support.microsoft.com/zh-TW/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="8cd76-492">[Use policies for site closure and deletion](https://support.microsoft.com/zh-TW/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="8cd76-493">[資訊管理原則](intro-to-info-mgmt-policies.md) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="8cd76-493">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="8cd76-494">如果您已設定 SharePoint 網站的內容類型原則或資訊管理原則，以保留清單或文件庫的內容，當保留原則生效時，會忽略這些原則。</span><span class="sxs-lookup"><span data-stu-id="8cd76-494">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 

## <a name="related-information"></a><span data-ttu-id="8cd76-495">相關資訊</span><span class="sxs-lookup"><span data-stu-id="8cd76-495">Related information</span></span>

- [<span data-ttu-id="8cd76-496">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="8cd76-496">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="8cd76-497">Microsoft Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="8cd76-497">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="8cd76-498">協助您符合資訊管理與記錄管理法規需求的資源</span><span class="sxs-lookup"><span data-stu-id="8cd76-498">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)

## <a name="next-steps"></a><span data-ttu-id="8cd76-499">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8cd76-499">Next steps</span></span>

<span data-ttu-id="8cd76-500">如果您已準備好建立保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8cd76-500">If you are ready to create retention policies, see [Create and configure retention policies](create-retention-policies.md).</span></span>

<span data-ttu-id="8cd76-501">若要建立及套用保留標籤：</span><span class="sxs-lookup"><span data-stu-id="8cd76-501">To create and apply retention labels:</span></span>
- [<span data-ttu-id="8cd76-502">建立保留標籤，並在應用程式中使用這些標籤</span><span class="sxs-lookup"><span data-stu-id="8cd76-502">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="8cd76-503">自動將保留標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="8cd76-503">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

