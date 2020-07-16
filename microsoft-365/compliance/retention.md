---
title: 瞭解保留原則和標籤，以自動保留或刪除內容
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
description: 瞭解保留原則和保留標籤，可協助您保留所需的內容，並刪除您不想要的內容。
ms.openlocfilehash: b67320af6f388386d7b7723bbe3f645b46eed8e7
ms.sourcegitcommit: f7566dd6010744c72684efdc37f4471672330b61
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138211"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a><span data-ttu-id="8c43b-103">瞭解保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="8c43b-103">Learn about retention policies and retention labels</span></span>

><span data-ttu-id="8c43b-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="8c43b-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="8c43b-p101">對大多數組織來說，其資料 (電子郵件、文件、即時訊息等) 的數量和複雜性日益增加。有效管理或控管此資訊至關重要，因為您需要：</span><span class="sxs-lookup"><span data-stu-id="8c43b-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="8c43b-107">**主動遵守產業規範和內部原則**，因此您需要將某些內容至少保留一段時間，例如，Sarbanes-Oxley 法案可能會要求您將某些類型的內容保留七年。</span><span class="sxs-lookup"><span data-stu-id="8c43b-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 
- <span data-ttu-id="8c43b-108">**降低發生訴訟或安全性漏洞的風險**，方法為永久刪除您不再需要保留的舊內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="8c43b-109">**協助貴組織有效分享知識並提高靈活度**，方法為確保使用者只使用目前和相關的內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="8c43b-110">您設定的保留設定可協助您實現所有目標。</span><span class="sxs-lookup"><span data-stu-id="8c43b-110">Retention settings that you configure can help you achieve all these goals.</span></span> <span data-ttu-id="8c43b-111">管理內容通常需要以下兩個動作：</span><span class="sxs-lookup"><span data-stu-id="8c43b-111">Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="8c43b-112">**保留**內容，以便無法在保留期間結束之前將其永久刪除。</span><span class="sxs-lookup"><span data-stu-id="8c43b-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="8c43b-113">在保留期間結束之前，永久**刪除**內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    

<span data-ttu-id="8c43b-114">使用這兩個保留動作，您可以設定以下結果的保留設定：</span><span class="sxs-lookup"><span data-stu-id="8c43b-114">With these two retention actions, you can configure retention settings for the following outcomes:</span></span>

- <span data-ttu-id="8c43b-115">僅保留：永久持續保留內容或保留指定的一段時間。</span><span class="sxs-lookup"><span data-stu-id="8c43b-115">Retain-only: Retain content forever or for a specified period of time.</span></span>
- <span data-ttu-id="8c43b-116">僅刪除：指定一段時間後刪除內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-116">Delete-only: Delete content after a specified period of time.</span></span>
- <span data-ttu-id="8c43b-117">保留並刪除：將內容保留指定的時間，然後將其刪除。</span><span class="sxs-lookup"><span data-stu-id="8c43b-117">Retain and then delete: Retain content for a specified period of time and then delete it.</span></span>

<span data-ttu-id="8c43b-118">這些保留設定可以使用就地內容，從而在您基於合規性原因而必須保留內容時，節省建立和設定額外儲存體的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="8c43b-118">These retention settings work with content in place that saves you the additional overheads of creating and configuring additional storage when you need to retain content for compliance reasons.</span></span> <span data-ttu-id="8c43b-119">此外，您不必執行自訂的程序來複製及同步處理這項資料。</span><span class="sxs-lookup"><span data-stu-id="8c43b-119">In addition, you don't need to implement customized processes to copy and synchronize this data.</span></span>

## <a name="how-retention-settings-work-with-content-in-place"></a><span data-ttu-id="8c43b-120">保留設定如何與就地內容搭配使用</span><span class="sxs-lookup"><span data-stu-id="8c43b-120">How retention settings work with content in place</span></span>

<span data-ttu-id="8c43b-121">當內容有指派保留設定時，該內容會保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="8c43b-121">When content has retention settings assigned to it, that content remains in its original location.</span></span> <span data-ttu-id="8c43b-122">若未發生任何變更，人員可以繼續使用其文件或郵件。</span><span class="sxs-lookup"><span data-stu-id="8c43b-122">People can continue to work with their documents or mail as if nothing's changed.</span></span> <span data-ttu-id="8c43b-123">但如果人員編輯或刪除保留原則中包含的內容，則會自動保留您套用保留設定時即存在的內容複本。</span><span class="sxs-lookup"><span data-stu-id="8c43b-123">But if they edit or delete content that's included in the retention policy, a copy of the content is automatically retained as it existed when you applied the retention settings.</span></span>
  
- <span data-ttu-id="8c43b-124">對於 SharePoint 和 OneDrive 網站：複本會保留在**文件保留庫**中。</span><span class="sxs-lookup"><span data-stu-id="8c43b-124">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span>

- <span data-ttu-id="8c43b-125">針對 Exchange 信箱：複本會保留在 **[可復原的項目]** 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="8c43b-125">For Exchange mailboxes: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="8c43b-126">針對 Teams 頻道和交談訊息：複本會保留在 Exchange **[可復原的項目]** 資料夾中的隱藏資料夾內。</span><span class="sxs-lookup"><span data-stu-id="8c43b-126">For Teams channel and chat messages: The copy is retained in a hidden folder within the Exchange **Recoverable Items** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="8c43b-127">[文件保留庫] 會佔用不受網站儲存空間配額限制的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="8c43b-127">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota.</span></span> <span data-ttu-id="8c43b-128">當您對 SharePoint 和 Microsoft 365 群組使用保留設定時，可能需要增加您的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="8c43b-128">You might need to increase your storage when you use retention settings for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="8c43b-129">大部分的人員無法檢視這些安全的位置和保留的內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-129">These secure locations and the retained content are not visible to most people.</span></span> <span data-ttu-id="8c43b-130">在大部分的情況下，使用者甚至不需要知道其內容受保留設定的限制。</span><span class="sxs-lookup"><span data-stu-id="8c43b-130">In most cases, people do not even need to know that their content is subject to retention settings.</span></span>

<span data-ttu-id="8c43b-131">如需有關保留設定如何配合不同工作負載使用的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="8c43b-131">For more detailed information about how retention settings work for different workloads, see the following articles:</span></span>

- [<span data-ttu-id="8c43b-132">瞭解 SharePoint 和 OneDrive 的保留功能</span><span class="sxs-lookup"><span data-stu-id="8c43b-132">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="8c43b-133">了解 Microsoft Teams 保留</span><span class="sxs-lookup"><span data-stu-id="8c43b-133">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="8c43b-134">了解 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="8c43b-134">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="8c43b-135">保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="8c43b-135">Retention policies and retention labels</span></span>

<span data-ttu-id="8c43b-136">您可以同時使用保留原則和保留標籤，以將保留設定指派給內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-136">You can use both retention policies and retention labels to assign your retention settings to content.</span></span> 

<span data-ttu-id="8c43b-137">使用保留原則為網站或信箱層級的內容指派相同的保留設定，並使用保留標籤來指派項目層級 (資料夾、文件、電子郵件) 的保留設定。</span><span class="sxs-lookup"><span data-stu-id="8c43b-137">Use a retention policy to assign the same retention settings for content at a site or mailbox level, and use a retention label to assign retention settings at an item level (folder, document, email).</span></span>

<span data-ttu-id="8c43b-138">例如，如果 SharePoint 網站中的所有文件都應該保留五年，使用保留原則比將相同的保留標籤套用至該網站中所有文件的方法更有效率。</span><span class="sxs-lookup"><span data-stu-id="8c43b-138">For example, if all documents in a SharePoint site should be retained for five years, it's more efficient to do this with a retention policy than apply the same retention label to all documents in that site.</span></span> <span data-ttu-id="8c43b-139">不過，如果該網站中的部分文件應保留五年，而其他文件保留十年，一個保留原則就不夠用。</span><span class="sxs-lookup"><span data-stu-id="8c43b-139">However, if some documents in that site should be retained for five years and others retained for ten years, a retention policy wouldn't be able to do this.</span></span> <span data-ttu-id="8c43b-140">當您必須在項目層級指定保留設定時，請使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-140">When you need to specify retention settings at the item level, use retention labels.</span></span> 

<span data-ttu-id="8c43b-141">不同於保留原則，保留標籤的保留設定會隨著內容複製或移至其他 Microsoft 365 位置而保留。</span><span class="sxs-lookup"><span data-stu-id="8c43b-141">Unlike retention policies, retention settings from retention labels persist with the content if it’s copied or moved to a different Microsoft 365 location.</span></span> <span data-ttu-id="8c43b-142">此外，保留標籤具有以下保留原則不支援的功能：</span><span class="sxs-lookup"><span data-stu-id="8c43b-142">In addition, retention labels have the following capabilities that retention policies don't support:</span></span> 
 
- <span data-ttu-id="8c43b-143">除了內容的年限或上次修改時間以外，還可選擇從為內容加上標籤的時間或根據事件來開始保留期間的選項。</span><span class="sxs-lookup"><span data-stu-id="8c43b-143">Options to start the retention period from when the content was labeled or based on an event, in addition to the age of the content or when it was last modified.</span></span>

- <span data-ttu-id="8c43b-144">使用[可訓練分類器](classifier-getting-started-with.md)來識別要加上標籤的內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-144">Use [trainable classifiers](classifier-getting-started-with.md) to identify content to label.</span></span>

- <span data-ttu-id="8c43b-145">為 SharePoint 文件套用預設標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-145">Apply a default label for SharePoint documents.</span></span>

- <span data-ttu-id="8c43b-146">支援[處置檢閱](disposition-reviews.md) 以在內容永久刪除之前檢閱。</span><span class="sxs-lookup"><span data-stu-id="8c43b-146">Support [disposition review](disposition-reviews.md) to review the content before it's permanently deleted.</span></span>

- <span data-ttu-id="8c43b-147">將內容標示為做為標籤設定一部分的[記錄](records.md)，並且在保留期間結束而刪除內容時，永遠都有 [處置證明](disposition.md#disposition-of-records) 。</span><span class="sxs-lookup"><span data-stu-id="8c43b-147">Mark the content as a [record](records.md) as part of the label settings, and always have [proof of disposition](disposition.md#disposition-of-records) when content is deleted at the end of its retention period.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="8c43b-148">保留原則</span><span class="sxs-lookup"><span data-stu-id="8c43b-148">Retention policies</span></span>

<span data-ttu-id="8c43b-149">保留原則可以套用到以下位置：</span><span class="sxs-lookup"><span data-stu-id="8c43b-149">Retention policies can be applied to the following locations:</span></span>
- <span data-ttu-id="8c43b-150">Exchange 電子郵件</span><span class="sxs-lookup"><span data-stu-id="8c43b-150">Exchange email</span></span>
- <span data-ttu-id="8c43b-151">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="8c43b-151">SharePoint site</span></span>
- <span data-ttu-id="8c43b-152">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="8c43b-152">OneDrive accounts</span></span>
- <span data-ttu-id="8c43b-153">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="8c43b-153">Microsoft 365 groups</span></span>
- <span data-ttu-id="8c43b-154">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="8c43b-154">Skype for Business</span></span>
- <span data-ttu-id="8c43b-155">Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="8c43b-155">Exchange public folders</span></span>
- <span data-ttu-id="8c43b-156">Teams 通道訊息</span><span class="sxs-lookup"><span data-stu-id="8c43b-156">Teams channel messages</span></span>
- <span data-ttu-id="8c43b-157">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="8c43b-157">Teams chats</span></span>

<span data-ttu-id="8c43b-158">您可以輕鬆地將單一原則套用到多個位置，或特定位置或使用者。</span><span class="sxs-lookup"><span data-stu-id="8c43b-158">You can very efficiently apply a single policy to multiple locations, or to specific locations or users.</span></span>
    
<span data-ttu-id="8c43b-159">您也可以將原則套用到所有內容，或符合特定條件的內容 (例如包含關鍵字或[機密資訊類型](sensitive-information-type-entity-definitions.md))。</span><span class="sxs-lookup"><span data-stu-id="8c43b-159">You can also apply a policy to all content or to content when it meets specific conditions, such as content that contains keywords or [sensitive information types](sensitive-information-type-entity-definitions.md).</span></span>

#### <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a><span data-ttu-id="8c43b-160">使用保留鎖定以符合法規需求</span><span class="sxs-lookup"><span data-stu-id="8c43b-160">Use Preservation Lock to comply with regulatory requirements</span></span>

<span data-ttu-id="8c43b-161">有些組織可能需要遵守由控管機構定義的法規，例如證券交易委員會 (SEC) 規定 17a-4，要求在保留原則開啟之後，不能關閉或執行較不嚴格的限制。</span><span class="sxs-lookup"><span data-stu-id="8c43b-161">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a retention policy is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="8c43b-162">「保留鎖定」可確保您的組織能夠符合這類法規需求，因為它會鎖定保留原則，使得沒有任何人 (包括系統管理員) 可以關閉原則、刪除原則或降低限制。</span><span class="sxs-lookup"><span data-stu-id="8c43b-162">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy so that no one—including the administrator—can turn off the policy, delete the policy, or make it less restrictive.</span></span>
  
<span data-ttu-id="8c43b-163">鎖定保留原則時：</span><span class="sxs-lookup"><span data-stu-id="8c43b-163">When a retention policy is locked:</span></span>

- <span data-ttu-id="8c43b-164">沒有人可以關閉它</span><span class="sxs-lookup"><span data-stu-id="8c43b-164">No one can it turn off</span></span>
- <span data-ttu-id="8c43b-165">可以新增位置但不能移除位置</span><span class="sxs-lookup"><span data-stu-id="8c43b-165">Locations can be added but not removed</span></span>
- <span data-ttu-id="8c43b-166">不能在保留期間修改或刪除受限於原則的內容</span><span class="sxs-lookup"><span data-stu-id="8c43b-166">Content subject to the policy can't be modified or deleted during the retention period</span></span>
- <span data-ttu-id="8c43b-167">您可以延長保留期間，但不能減少保留期間</span><span class="sxs-lookup"><span data-stu-id="8c43b-167">You can extend a retention period but not decrease it</span></span>

<span data-ttu-id="8c43b-168">總而言之，鎖定的保留原則可以增加或延長，但是不能減少或關閉。</span><span class="sxs-lookup"><span data-stu-id="8c43b-168">In summary, a locked retention policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8c43b-169">在您鎖定保留原則之前，務必了解影響，並確認您的組織是否需要符合法規需求。</span><span class="sxs-lookup"><span data-stu-id="8c43b-169">Before you lock a retention policy, it's critical that you understand the impact and confirm whether it's required for your organization to meet regulatory requirements.</span></span> <span data-ttu-id="8c43b-170">套用保留鎖定之後，系統管理員將無法停用或刪除保留原則。</span><span class="sxs-lookup"><span data-stu-id="8c43b-170">Administrators won't be able to disable or delete a retention policy after the preservation lock is applied.</span></span>

#### <a name="releasing-a-retention-policy"></a><span data-ttu-id="8c43b-171">釋出保留原則</span><span class="sxs-lookup"><span data-stu-id="8c43b-171">Releasing a retention policy</span></span>

<span data-ttu-id="8c43b-172">如果您的保留原則沒有保留鎖定，則可以隨時關閉或刪除保留原則。</span><span class="sxs-lookup"><span data-stu-id="8c43b-172">Providing your retention policy doesn't have a Preservation Lock, you can turn off or delete a retention policy at any time.</span></span> 

<span data-ttu-id="8c43b-173">當您這麼做時，保留在文件保留庫中的任何 SharePoint 或 OneDrive 的內容不會立即永久被刪除。</span><span class="sxs-lookup"><span data-stu-id="8c43b-173">When you do so, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="8c43b-174">相反地，為了防止意外的資料遺失，我們有 30 天的寬限期，在這期間，保留文件庫中不會發生該原則的內容到期，因此，如有需要，您可以在這裡還原任何內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-174">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="8c43b-175">此外，您無法在寬限期期間手動刪除此內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-175">Additionally, you can't manually delete this content during the grace period.</span></span>

<span data-ttu-id="8c43b-176">您可以在寬限期期間再次開啟保留原則，這麼一來，將不會刪除該原則的內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-176">You can turn on the retention policy again during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="8c43b-177">SharePoint 和 OneDrive 中的此 30 天寬限期與 Exchange 中的 30 天延遲保留對應。</span><span class="sxs-lookup"><span data-stu-id="8c43b-177">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="8c43b-178">如需詳細資訊，請參閱[管理延遲保留信箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。</span><span class="sxs-lookup"><span data-stu-id="8c43b-178">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="8c43b-179">保留標籤</span><span class="sxs-lookup"><span data-stu-id="8c43b-179">Retention labels</span></span>

<span data-ttu-id="8c43b-180">請針對需要不同保留設定的不同類型的內容，使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-180">Use retention labels for different types of content that require different retention settings.</span></span> <span data-ttu-id="8c43b-181">例如：</span><span class="sxs-lookup"><span data-stu-id="8c43b-181">For example:</span></span>
  
- <span data-ttu-id="8c43b-182">至少必須保留一小段時間的稅務表單。</span><span class="sxs-lookup"><span data-stu-id="8c43b-182">Tax forms that need to be retained for a minimum period of time.</span></span> 
    
- <span data-ttu-id="8c43b-183">到達特定年限之後需要永久刪除的新聞材料。</span><span class="sxs-lookup"><span data-stu-id="8c43b-183">Press materials that need to be permanently deleted when they reach a specific age.</span></span> 
    
- <span data-ttu-id="8c43b-184">需要先保留一段期間之然後再永久刪除的競爭力研究。</span><span class="sxs-lookup"><span data-stu-id="8c43b-184">Competitive research that needs to be retained for a specific period and then permanently deleted.</span></span> 
    
- <span data-ttu-id="8c43b-185">必須標示為記錄使之無法編輯或刪除的工作簽證。</span><span class="sxs-lookup"><span data-stu-id="8c43b-185">Work visas that must be marked as a record so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="8c43b-186">在這些情況下，保留標籤可讓您在項目層級 (文件或電子郵件) 套用治理控制的保留設定。</span><span class="sxs-lookup"><span data-stu-id="8c43b-186">In all these cases, retention labels let you apply retention settings for governance control at the item level (document or email).</span></span>
  
<span data-ttu-id="8c43b-187">使用保留標籤，您可以：</span><span class="sxs-lookup"><span data-stu-id="8c43b-187">With retention labels, you can:</span></span>
  
- <span data-ttu-id="8c43b-188">**讓貴組織中的人員手動將保留標籤套用**至網頁上的 Outlook 和 Outlook、OneDrive、SharePoint 和 Microsoft 365 群組中的內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-188">**Enable people in your organization to apply a retention label manually** to content in Outlook and Outlook on the web, OneDrive, SharePoint, and Microsoft 365 groups.</span></span> <span data-ttu-id="8c43b-189">使用者通常都清楚知道自己處理的內容類型，因此可將內容分類並套用適當的保留設定。</span><span class="sxs-lookup"><span data-stu-id="8c43b-189">Users often know best what type of content they're working with, so they can classify it and have the appropriate retention settings applied.</span></span> 
    
- <span data-ttu-id="8c43b-190">在當內容符合特定條件時**自動將保留標籤套用到內容**，例如內容包含：</span><span class="sxs-lookup"><span data-stu-id="8c43b-190">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    - <span data-ttu-id="8c43b-191">特定類型的敏感資訊。</span><span class="sxs-lookup"><span data-stu-id="8c43b-191">Specific types of sensitive information.</span></span>
    - <span data-ttu-id="8c43b-192">特定關鍵字符合您建立的查詢。</span><span class="sxs-lookup"><span data-stu-id="8c43b-192">Specific keywords that match a query you create.</span></span>
    - <span data-ttu-id="8c43b-193">可訓練分類器的模式比對。</span><span class="sxs-lookup"><span data-stu-id="8c43b-193">Pattern matches for a trainable classifier.</span></span>

- <span data-ttu-id="8c43b-194">針對 SharePoint 網站和 OneDrive 帳戶中的文件和電子郵件項目 (行事曆項除外)，**從內容加上標籤起就開始保留期間**。</span><span class="sxs-lookup"><span data-stu-id="8c43b-194">**Start the retention period from when the content was labeled** for documents in SharePoint sites and OneDrive accounts, and to email items with the exception of calendar items.</span></span> <span data-ttu-id="8c43b-195">如果您將具有此設定的保留標籤套用於行事曆項目，則保留期間從其傳送日期開始。</span><span class="sxs-lookup"><span data-stu-id="8c43b-195">If you apply a retention label with this configuration to a calendar item, the retention period starts from when it is sent.</span></span>

- <span data-ttu-id="8c43b-196">**當事件發生時 (例如員工離開組織或合約到期)，開始保留期間**。</span><span class="sxs-lookup"><span data-stu-id="8c43b-196">**Start the retention period when an event occurs**, such as employees leave the organization, or contracts expire.</span></span>

- <span data-ttu-id="8c43b-197">**將預設保留標籤套用至 SharePoint 中的文件庫、資料夾或文件集**，以便儲存在該位置中的所有文件都繼承預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-197">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that are stored in that location inherit the default retention label.</span></span>

<span data-ttu-id="8c43b-198">此外，保留標籤支援跨 Microsoft 365 應用程式和服務的電子郵件和文件[記錄管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="8c43b-198">Additionally, retention labels support [records management](records-management.md) for email and documents across Microsoft 365 apps and services.</span></span> <span data-ttu-id="8c43b-199">您可以使用保留標籤將內容分類為記錄。</span><span class="sxs-lookup"><span data-stu-id="8c43b-199">You can use a retention label to classify content as a record.</span></span> <span data-ttu-id="8c43b-200">如果您這麼做，且內容仍然在 Microsoft 365 中時，將無法變更或移除標籤，也無法編輯或刪除相關內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-200">When this happens and the content remains in Microsoft 365, the label can't be changed or removed, and the content can't be edited or deleted.</span></span> 

<span data-ttu-id="8c43b-201">與[敏感度標籤](sensitivity-labels.md)不同，如果內容是移至 Microsoft 365 以外的位置，保留標籤不會保留。</span><span class="sxs-lookup"><span data-stu-id="8c43b-201">Retention labels, unlike [sensitivity labels](sensitivity-labels.md), do not persist if the content is moved outside Microsoft 365.</span></span>

<span data-ttu-id="8c43b-202">針對租用戶支援的保留標籤數量沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="8c43b-202">There is no limit to the number of retention labels that are supported for a tenant.</span></span> <span data-ttu-id="8c43b-203">不過，10,000 個是針對租用戶支援的原則數目上限，其中包括會套用標籤 (保留標籤原則和自動套用保留原則) 的原則，以及保留原則。</span><span class="sxs-lookup"><span data-stu-id="8c43b-203">However, 10,000 is the maximum number of policies that are supported for a tenant and these include the policies that apply the labels (retention label policies and auto-apply retention policies), as well as retention policies.</span></span>

#### <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="8c43b-204">將內容分類而不套用任何動作</span><span class="sxs-lookup"><span data-stu-id="8c43b-204">Classifying content without applying any actions</span></span>

<span data-ttu-id="8c43b-205">雖然保留標籤的主要目的是要保留或刪除內容，但您也可以在不開啟任何保留或其他動作的情況下使用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-205">Although the main purpose of retention labels is to retain or delete content, you can also use retention labels without turning on any retention or other actions.</span></span> <span data-ttu-id="8c43b-206">在此情況下，您可以使用保留標籤當做文字標籤，而不強制執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="8c43b-206">In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="8c43b-207">例如，您可以建立並套用名為「稍後檢閱」的保留標籤，而不執行任何動作，然後使用該標籤於稍後尋找該內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-207">For example, you can create and apply a retention label named "Review later" with no actions, and then use that label to find that content later.</span></span>
  
![標籤設定頁面中關閉保留](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="8c43b-209">使用保留標籤作為 DLP 原則的條件</span><span class="sxs-lookup"><span data-stu-id="8c43b-209">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="8c43b-210">您可以將保留標籤做為 SharePoint 文件的資料外洩防護 (DLP) 原則中的條件。</span><span class="sxs-lookup"><span data-stu-id="8c43b-210">You can specify a retention label as a condition in a data loss prevention (DLP) policy for documents in SharePoint.</span></span> <span data-ttu-id="8c43b-211">例如，設定 DLP 原則以防止文件在組織外共用 (如果已套用指定的保留標籤)。</span><span class="sxs-lookup"><span data-stu-id="8c43b-211">For example, configure a DLP policy to prevent documents from being shared outside the organization if they have a specified retention label applied to it.</span></span>

<span data-ttu-id="8c43b-212">如需詳細資訊，請參閱[使用保留標籤做為 DLP 原則中的條件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="8c43b-212">For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

#### <a name="retention-labels-and-policies-that-apply-them"></a><span data-ttu-id="8c43b-213">保留標籤和套用其標籤的原則</span><span class="sxs-lookup"><span data-stu-id="8c43b-213">Retention labels and policies that apply them</span></span>

<span data-ttu-id="8c43b-214">保留標籤是獨立、可重複使用的建置組塊。</span><span class="sxs-lookup"><span data-stu-id="8c43b-214">Retention labels are independent, reusable building blocks.</span></span> <span data-ttu-id="8c43b-215">保留標籤原則的主要目的是將一組保留標籤分組，以及指定您想讓這些標籤出現的目標位置。</span><span class="sxs-lookup"><span data-stu-id="8c43b-215">The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear.</span></span> <span data-ttu-id="8c43b-216">然後，系統管理員和使用者可以將這些標籤套用至這些位置中的內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-216">Then, admins and users can apply those labels to content in those locations.</span></span>
  
![標籤、標籤原則和位置圖表](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
<span data-ttu-id="8c43b-218">當您發佈保留標籤時，會將這些標籤包含在保留標籤原則中，好讓系統管理員和使用者選擇：</span><span class="sxs-lookup"><span data-stu-id="8c43b-218">When you publish retention labels, they're included in a retention label policy that make them available for admins and users to select:</span></span>

- <span data-ttu-id="8c43b-219">單一保留標籤可納入多個保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="8c43b-219">A single retention label can be included in many retention label policies.</span></span>

- <span data-ttu-id="8c43b-220">保留標籤原則會指定要發佈保留標籤的位置。</span><span class="sxs-lookup"><span data-stu-id="8c43b-220">Retention label policies specify the locations to publish the retention labels.</span></span>

- <span data-ttu-id="8c43b-221">單一位置也可納入多個保留標籤原則。</span><span class="sxs-lookup"><span data-stu-id="8c43b-221">A single location can also be included in many retention label policies.</span></span>

<span data-ttu-id="8c43b-222">除了保留標籤原則以外，您也可以建立一或多個自動套用原則，每一個都有單一保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-222">In addition to retention label policies, you can also create one or more auto-apply policies, each with a single retention label.</span></span> <span data-ttu-id="8c43b-223">使用此原則，當您在原則中指定的條件滿足時，將自動套用保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-223">With this policy, a retention label is automatically applied when conditions that you specify in the policy are met.</span></span> 

#### <a name="retention-label-policies-and-locations"></a><span data-ttu-id="8c43b-224">保留標籤原則與位置</span><span class="sxs-lookup"><span data-stu-id="8c43b-224">Retention label policies and locations</span></span>

<span data-ttu-id="8c43b-225">可以將不同類型的保留標籤發佈到不同的位置，視保留標籤的功能而定。</span><span class="sxs-lookup"><span data-stu-id="8c43b-225">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
| <span data-ttu-id="8c43b-226">如果保留標籤是...</span><span class="sxs-lookup"><span data-stu-id="8c43b-226">If the retention label is…</span></span> | <span data-ttu-id="8c43b-227">標籤原則可套用至…</span><span class="sxs-lookup"><span data-stu-id="8c43b-227">Then the label policy can be applied to…</span></span> |
|:-----|:-----|
|<span data-ttu-id="8c43b-228">已發佈給系統管理員和使用者</span><span class="sxs-lookup"><span data-stu-id="8c43b-228">Published to admins and end users</span></span>  <br/> |<span data-ttu-id="8c43b-229">Exchange、SharePoint、OneDrive、Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="8c43b-229">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
|<span data-ttu-id="8c43b-230">根據敏感資訊類型或可訓練分類器而自動套用</span><span class="sxs-lookup"><span data-stu-id="8c43b-230">Auto-applied based on sensitive information types or trainable classifiers</span></span>  <br/> |<span data-ttu-id="8c43b-231">Exchange (僅限所有信箱)、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c43b-231">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="8c43b-232">根據查詢而自動套用</span><span class="sxs-lookup"><span data-stu-id="8c43b-232">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="8c43b-233">Exchange、SharePoint、OneDrive、Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="8c43b-233">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
   
<span data-ttu-id="8c43b-234">在 Exchange 中，您只能在新傳送的郵件 (傳輸中的資料) 上自動套用保留標籤功能，而非目前在信箱中的所有郵件 (待用資料)。</span><span class="sxs-lookup"><span data-stu-id="8c43b-234">In Exchange, auto-apply retention labels are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="8c43b-235">此外，您只能在所有信箱中為敏感性資訊類型和可訓練分類器來自動套用保留標籤功能，但無法選取特定信箱。</span><span class="sxs-lookup"><span data-stu-id="8c43b-235">Also, auto-apply retention labels for sensitive information types and trainable classifiers apply to all mailboxes; you can't select specific mailboxes.</span></span>
  
<span data-ttu-id="8c43b-236">Exchange 公用資料夾、Skype 和 Teams 頻道訊息和聊天不支援保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-236">Exchange public folders, Skype, and Teams channel messages and chats do not support retention labels.</span></span> <span data-ttu-id="8c43b-237">若要保留或刪除這些位置中的內容，請改用保留原則。</span><span class="sxs-lookup"><span data-stu-id="8c43b-237">To retain and delete contain from these locations, use retention policies instead.</span></span>

#### <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="8c43b-238">一次只能有一個保留標籤</span><span class="sxs-lookup"><span data-stu-id="8c43b-238">Only one retention label at a time</span></span>

<span data-ttu-id="8c43b-239">電子郵件或文件等內容一次只能指派一個保留標籤：</span><span class="sxs-lookup"><span data-stu-id="8c43b-239">An email or document can have only a single retention label assigned to it at a time:</span></span>
  
- <span data-ttu-id="8c43b-240">針對系統管理員或使用者手動指派的保留標籤，人員可以移除或變更獲指派的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-240">For retention labels assigned manually by admins or end users, people can remove or change the retention label that's assigned.</span></span>
    
- <span data-ttu-id="8c43b-241">如果內容已指派自動套用標籤，這個標籤會由已發佈的保留標籤取代。</span><span class="sxs-lookup"><span data-stu-id="8c43b-241">If content has an auto-apply label assigned, this label can be replaced by a published retention label.</span></span>
    
- <span data-ttu-id="8c43b-242">如果內容已指派已發佈的保留標籤，則自動套用標籤不能取代之。</span><span class="sxs-lookup"><span data-stu-id="8c43b-242">If content has a published retention label assigned, an auto-apply label cannot replace it.</span></span>
    
- <span data-ttu-id="8c43b-243">如果有多項規則會指派自動套用標籤，且內容符合多項規則的條件，則會指派最舊規則的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-243">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the retention label for the oldest rule is assigned.</span></span>
    
<span data-ttu-id="8c43b-244">若要了解如何以及為何套用某個保留標籤 (而非其他標籤)，請務必了解明確指派標籤與隱含指派標籤之間的差異：</span><span class="sxs-lookup"><span data-stu-id="8c43b-244">To understand how and why one retention label is applied rather than another, it's helpful to understand the difference between explicitly assign a label, and implicitly assigned a label:</span></span>

- <span data-ttu-id="8c43b-245">從標籤原則套用的保留標籤會明確指派</span><span class="sxs-lookup"><span data-stu-id="8c43b-245">Retention labels applied from a label policy are explicitly assigned</span></span>
- <span data-ttu-id="8c43b-246">從自動套用原則自動套用的保留標籤會被隱式指派</span><span class="sxs-lookup"><span data-stu-id="8c43b-246">Retention labels applied automatically from an auto-apply policy are implicitly assigned</span></span>

<span data-ttu-id="8c43b-247">明確指派的保留標籤會優先於隱式指派的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-247">An explicitly assigned retention label takes precedence over an implicitly assigned retention label.</span></span> <span data-ttu-id="8c43b-248">如需詳細資訊，請參閱此頁面上的[原則保留或何者優先？](retention.md#the-principles-of-retention-or-what-takes-precedence)一節。</span><span class="sxs-lookup"><span data-stu-id="8c43b-248">For more information, see the [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) section on this page.</span></span>

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a><span data-ttu-id="8c43b-249">使用內容搜尋來尋找套用特定保留標籤的所有內容</span><span class="sxs-lookup"><span data-stu-id="8c43b-249">Using Content Search to find all content with a specific retention label applied to it</span></span>

<span data-ttu-id="8c43b-250">將保留標籤指派至內容後 (無論是由使用者指派或自動套用)，您可以使用「內容搜尋」，尋找以特定保留標籤分類的所有內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-250">After retention labels are assigned to content, either by users or auto-applied, you can use content search to find all content that's classified with a specific retention label.</span></span>
  
<span data-ttu-id="8c43b-251">當您建立內容搜尋時，請選擇 **[合規性標籤]** 條件，然後輸入完整的保留標籤名稱或是部分標籤名稱，再使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="8c43b-251">When you create a content search, choose the **Compliance label** condition, and then enter the complete retention label name or part of the label name and use a wildcard.</span></span> <span data-ttu-id="8c43b-252">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="8c43b-252">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![合規性標籤條件](../media/compliance-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a><span data-ttu-id="8c43b-254">比較保留原則和保留標籤的功能</span><span class="sxs-lookup"><span data-stu-id="8c43b-254">Compare capabilities for retention policies and retention labels</span></span>

<span data-ttu-id="8c43b-255">使用下列表格來協助您判斷是否要根據功能來使用保留原則或保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-255">Use the following table to help you identify whether to use a retention policy or retention label, based on capabilities.</span></span>

|<span data-ttu-id="8c43b-256">功能</span><span class="sxs-lookup"><span data-stu-id="8c43b-256">Capability</span></span>|<span data-ttu-id="8c43b-257">保留原則</span><span class="sxs-lookup"><span data-stu-id="8c43b-257">Retention policy</span></span> |<span data-ttu-id="8c43b-258">保留標籤</span><span class="sxs-lookup"><span data-stu-id="8c43b-258">Retention label</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8c43b-259">可以保留然後刪除、僅保留或僅刪除的保留設定</span><span class="sxs-lookup"><span data-stu-id="8c43b-259">Retention settings that can retain and then delete, retain-only, or delete-only</span></span> |<span data-ttu-id="8c43b-260">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-260">Yes</span></span> |<span data-ttu-id="8c43b-261">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-261">Yes</span></span> |
|<span data-ttu-id="8c43b-262">支援的工作負載：</span><span class="sxs-lookup"><span data-stu-id="8c43b-262">Workloads supported:</span></span> <br /><span data-ttu-id="8c43b-263">- Exchange</span><span class="sxs-lookup"><span data-stu-id="8c43b-263">- Exchange</span></span> <br /><span data-ttu-id="8c43b-264">- SharePoint</span><span class="sxs-lookup"><span data-stu-id="8c43b-264">- SharePoint</span></span> <br /><span data-ttu-id="8c43b-265">- OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c43b-265">- OneDrive</span></span> <br /><span data-ttu-id="8c43b-266">- Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="8c43b-266">- Microsoft 365 groups</span></span> <br /><span data-ttu-id="8c43b-267">- 商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="8c43b-267">- Skype for Business</span></span> <br /><span data-ttu-id="8c43b-268">- Teams</span><span class="sxs-lookup"><span data-stu-id="8c43b-268">- Teams</span></span>|<br /> <span data-ttu-id="8c43b-269">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-269">Yes</span></span> <br /> <span data-ttu-id="8c43b-270">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-270">Yes</span></span> <br /> <span data-ttu-id="8c43b-271">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-271">Yes</span></span> <br /> <span data-ttu-id="8c43b-272">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-272">Yes</span></span> <br /> <span data-ttu-id="8c43b-273">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-273">Yes</span></span> <br /> <span data-ttu-id="8c43b-274">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-274">Yes</span></span> | <br /> <span data-ttu-id="8c43b-275">是，除了公用資料夾</span><span class="sxs-lookup"><span data-stu-id="8c43b-275">Yes, except public folders</span></span> <br /> <span data-ttu-id="8c43b-276">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-276">Yes</span></span> <br /> <span data-ttu-id="8c43b-277">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-277">Yes</span></span> <br /> <span data-ttu-id="8c43b-278">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-278">Yes</span></span> <br /> <span data-ttu-id="8c43b-279">否</span><span class="sxs-lookup"><span data-stu-id="8c43b-279">No</span></span> <br /> <span data-ttu-id="8c43b-280">否</span><span class="sxs-lookup"><span data-stu-id="8c43b-280">No</span></span>  |
|<span data-ttu-id="8c43b-281">自動套用的保留</span><span class="sxs-lookup"><span data-stu-id="8c43b-281">Retention applied automatically</span></span> | <span data-ttu-id="8c43b-282">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-282">Yes</span></span> | <span data-ttu-id="8c43b-283">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-283">Yes</span></span> |
|<span data-ttu-id="8c43b-284">手動套用的保留</span><span class="sxs-lookup"><span data-stu-id="8c43b-284">Retention applied manually</span></span> | <span data-ttu-id="8c43b-285">否</span><span class="sxs-lookup"><span data-stu-id="8c43b-285">No</span></span> | <span data-ttu-id="8c43b-286">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-286">Yes</span></span> |
|<span data-ttu-id="8c43b-287">使用者的 UI 目前狀態</span><span class="sxs-lookup"><span data-stu-id="8c43b-287">UI presence for end users</span></span> | <span data-ttu-id="8c43b-288">否</span><span class="sxs-lookup"><span data-stu-id="8c43b-288">No</span></span> | <span data-ttu-id="8c43b-289">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-289">Yes</span></span> |
|<span data-ttu-id="8c43b-290">如果內容已移動，則會持續存在</span><span class="sxs-lookup"><span data-stu-id="8c43b-290">Persists if the content is moved</span></span> | <span data-ttu-id="8c43b-291">否</span><span class="sxs-lookup"><span data-stu-id="8c43b-291">No</span></span> | <span data-ttu-id="8c43b-292">是，在 Microsoft 365 中</span><span class="sxs-lookup"><span data-stu-id="8c43b-292">Yes, within Microsoft 365</span></span> |
|<span data-ttu-id="8c43b-293">將項目宣告為記錄</span><span class="sxs-lookup"><span data-stu-id="8c43b-293">Declare item as a record</span></span>| <span data-ttu-id="8c43b-294">否</span><span class="sxs-lookup"><span data-stu-id="8c43b-294">No</span></span> | <span data-ttu-id="8c43b-295">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-295">Yes</span></span> |
|<span data-ttu-id="8c43b-296">在加上標籤起或根據事件來開始保留期間</span><span class="sxs-lookup"><span data-stu-id="8c43b-296">Start the retention period when labeled or based on an event</span></span> | <span data-ttu-id="8c43b-297">否</span><span class="sxs-lookup"><span data-stu-id="8c43b-297">No</span></span> | <span data-ttu-id="8c43b-298">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-298">Yes</span></span> |
|<span data-ttu-id="8c43b-299">處置檢閱</span><span class="sxs-lookup"><span data-stu-id="8c43b-299">Disposition review</span></span> | <span data-ttu-id="8c43b-300">否</span><span class="sxs-lookup"><span data-stu-id="8c43b-300">No</span></span>| <span data-ttu-id="8c43b-301">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-301">Yes</span></span> |
|<span data-ttu-id="8c43b-302">最高 7 年的處置證明</span><span class="sxs-lookup"><span data-stu-id="8c43b-302">Proof of disposition for up to 7 years</span></span> | <span data-ttu-id="8c43b-303">否</span><span class="sxs-lookup"><span data-stu-id="8c43b-303">No</span></span> |<span data-ttu-id="8c43b-304">是，當物料宣告為記錄時</span><span class="sxs-lookup"><span data-stu-id="8c43b-304">Yes, when item is declared a record</span></span>|
|<span data-ttu-id="8c43b-305">識別要保留的項目：</span><span class="sxs-lookup"><span data-stu-id="8c43b-305">Identify items subject to retention:</span></span> <br /> <span data-ttu-id="8c43b-306">- 內容搜尋</span><span class="sxs-lookup"><span data-stu-id="8c43b-306">- Content Search</span></span> <br /> <span data-ttu-id="8c43b-307">- 資料分類頁面、內容總管，活動總管</span><span class="sxs-lookup"><span data-stu-id="8c43b-307">- Data classification page, content explorer, activity explorer</span></span> | <br /> <span data-ttu-id="8c43b-308">否</span><span class="sxs-lookup"><span data-stu-id="8c43b-308">No</span></span> <br /> <span data-ttu-id="8c43b-309">否</span><span class="sxs-lookup"><span data-stu-id="8c43b-309">No</span></span> | <br /> <span data-ttu-id="8c43b-310">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-310">Yes</span></span> <br /> <span data-ttu-id="8c43b-311">是</span><span class="sxs-lookup"><span data-stu-id="8c43b-311">Yes</span></span>|

<span data-ttu-id="8c43b-312">請注意，您可以使用保留原則和保留標籤做為補充保留方法。</span><span class="sxs-lookup"><span data-stu-id="8c43b-312">Note that you can use both retention policies and retention labels as complementary retention methods.</span></span> <span data-ttu-id="8c43b-313">例如：</span><span class="sxs-lookup"><span data-stu-id="8c43b-313">For example:</span></span>

1. <span data-ttu-id="8c43b-314">您建立並設定將在內容上次修改後五年自動刪除內容的保留原則，並將該原則套用於所有 OneDrive 帳戶。</span><span class="sxs-lookup"><span data-stu-id="8c43b-314">You create and configure a retention policy that automatically deletes content five years after it's last modified, and apply the policy to all OneDrive accounts.</span></span>

2. <span data-ttu-id="8c43b-315">您建立並設定永久保留內容的保留標籤，並將其新增至您發佈到所有 OneDrive 帳戶的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="8c43b-315">You create and configure a retention label that keeps content forever and add this to a label policy that you publish to all OneDrive accounts.</span></span> <span data-ttu-id="8c43b-316">您向使用者說明如何手動將此標籤套用於五年後未修改應從自動刪除排除的特定文件。</span><span class="sxs-lookup"><span data-stu-id="8c43b-316">You explain to users how to manually apply this label to specific documents that should be excluded from automatic deletion if not modified after five years.</span></span>

<span data-ttu-id="8c43b-317">有關保留原則和保留標籤如何搭配，以及如何判斷其合併結果的更多資訊，請參閱下一節解釋保留的原則和其優先順序。</span><span class="sxs-lookup"><span data-stu-id="8c43b-317">For more information about how retention policies and retention labels work together and how to determine their combined outcome, see the next section that explains the principles of retention and what takes precedence.</span></span>

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="8c43b-318">原則保留或何者優先</span><span class="sxs-lookup"><span data-stu-id="8c43b-318">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="8c43b-319">內容有可能套用多個會進行不同動作 (保留、刪除或保留然後刪除) 且保留期間不同的保留原則和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-319">It's possible or even likely that content might have several retention policies and retention labels applied to it, each with a different action (retain, delete, or retain and then delete) and retention period.</span></span> <span data-ttu-id="8c43b-320">哪個的優先順序較高？</span><span class="sxs-lookup"><span data-stu-id="8c43b-320">What takes precedence?</span></span> 

<span data-ttu-id="8c43b-321">在高層級中，您可以確保保留永遠優先於刪除，然後才是最長的保留期間勝出。</span><span class="sxs-lookup"><span data-stu-id="8c43b-321">At a high level, you can be assured that retention always takes precedence over deletion, and then the longest retention period wins.</span></span> 

<span data-ttu-id="8c43b-322">但還有其他一些因素需要考慮，因此請使用以下流程來了解每個層級從上到下扮演決勝局的結果：如果結果由第一層級決定，則無需前進到下一個層級，依此類推。</span><span class="sxs-lookup"><span data-stu-id="8c43b-322">However, there are a few more factors to throw into the mix, so use the following flow to understand the outcome where each level acts as a tie-breaker from top to bottom: If the outcome is determined by the first level, there's no need to progress to the next level, and so on.</span></span> <span data-ttu-id="8c43b-323">只有當結果無法由層級規則決定時，流程才會移至下一個層級，以決定保留設定優先權的結果。</span><span class="sxs-lookup"><span data-stu-id="8c43b-323">Only if the outcome can't be determined by the rules for the level does the flow move down to the next level to determine the outcome for which retention settings take precedence.</span></span>

![原則保留圖](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="8c43b-325">四個不同層級的說明：</span><span class="sxs-lookup"><span data-stu-id="8c43b-325">Explanation for the four different levels:</span></span>
  
1. <span data-ttu-id="8c43b-326">**保留優先於刪除。**</span><span class="sxs-lookup"><span data-stu-id="8c43b-326">**Retention wins over deletion.**</span></span> <span data-ttu-id="8c43b-327">假設某個保留原則設定在 3 年後刪除 Exchange 電子郵件，但另一個保留原則設定將 Exchange 電子郵件保留 5 年再刪除。</span><span class="sxs-lookup"><span data-stu-id="8c43b-327">Suppose that one retention policy is configured to delete Exchange email after three years, but another retention policy is configured to retain Exchange email for five years and then delete it.</span></span> <span data-ttu-id="8c43b-328">任何到達 3 年的內容會遭到刪除，並從使用者的檢視畫面隱藏，但仍會保留再 [可復原的項目] 資料夾中，直到內容到達 5 年，才會遭永久刪除。</span><span class="sxs-lookup"><span data-stu-id="8c43b-328">Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it is permanently deleted.</span></span> 
2. <span data-ttu-id="8c43b-329">**最長保留期間優先。**</span><span class="sxs-lookup"><span data-stu-id="8c43b-329">**The longest retention period wins.**</span></span> <span data-ttu-id="8c43b-330">如果內容受制於在不同的期間保留內容的多個保留設定，則該內容將一直保留到最長保留期間結束為止。</span><span class="sxs-lookup"><span data-stu-id="8c43b-330">If content is subject to multiple retention settings that retain content for different periods of time, the content will be retained until the end of the longest retention period.</span></span>
    
3. <span data-ttu-id="8c43b-331">**明確包含優先於隱含包含。**</span><span class="sxs-lookup"><span data-stu-id="8c43b-331">**Explicit inclusion wins over implicit inclusion.**</span></span> <span data-ttu-id="8c43b-332">也就是說：</span><span class="sxs-lookup"><span data-stu-id="8c43b-332">This means:</span></span> 
    
    1. <span data-ttu-id="8c43b-333">如果包含保留設定的保留標籤是由使用者手動指派至項目 (例如 Exchange 電子郵件或 OneDrive 文件)，則該保留標籤會優先於在網站或信箱層級指派的保留原則，以及指派給文件庫的預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-333">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a retention policy assigned at the site or mailbox level and a default retention label assigned to the document library.</span></span> <span data-ttu-id="8c43b-334">例如，如果明確保留標籤設定要保留內容十年，但對網站指派的保留原則設定為保留內容五年，則保留標籤會優先於原則。</span><span class="sxs-lookup"><span data-stu-id="8c43b-334">For example, if the explicit retention label is configured to retain content for ten years, but a retention policy assigned to the site is configured to retain content for only five years, the retention label takes precedence.</span></span> <span data-ttu-id="8c43b-335">自動套用的保留標籤會被視為隱含，而非明確，因為這類標籤是由 Microsoft 365 自動套用。</span><span class="sxs-lookup"><span data-stu-id="8c43b-335">Auto-applied retention labels are considered implicit rather than explicit, because they're applied automatically by Microsoft 365.</span></span>
    
    2. <span data-ttu-id="8c43b-336">如果保留原則包含特定位置 (例如特定使用者的信箱或 OneDrive 帳戶)，則該保留原則會優先於其他套用至所有使用者信箱或 OneDrive 帳戶但未特地包含該使用者信箱的保留原則。</span><span class="sxs-lookup"><span data-stu-id="8c43b-336">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive account, that retention policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="8c43b-337">**最短刪除期間優先。**</span><span class="sxs-lookup"><span data-stu-id="8c43b-337">**The shortest deletion period wins.**</span></span> <span data-ttu-id="8c43b-338">同樣地，如果內容受限於會刪除內容但不帶保留期間的多個保留設定，則會在最短刪除期間結束時刪除該內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-338">Similarly, if content is subject to multiple retention settings that delete content without a retention period, that content will be deleted at the end of the shortest retention period.</span></span> 

<span data-ttu-id="8c43b-339">最終，保留原則或保留標籤無法永久刪除任何電子文件探索保留的內容。</span><span class="sxs-lookup"><span data-stu-id="8c43b-339">Finally, a retention policy or retention label cannot permanently delete any content that's on hold for eDiscovery.</span></span> <span data-ttu-id="8c43b-340">將保留釋出時，該內容會再次符合上述的清理程序資格，並在工作負載的受保護位置中進行。</span><span class="sxs-lookup"><span data-stu-id="8c43b-340">When that hold is released, the content again becomes eligible for the cleanup process in the secured locations for the workload.</span></span>

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a><span data-ttu-id="8c43b-341">保留原則和保留標籤的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8c43b-341">PowerShell cmdlets for retention policies and retention labels</span></span>

<span data-ttu-id="8c43b-342">若要使用保留 Cmdlet，您必須先[連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8c43b-342">To use the retention cmdlets, you must first [connect to the Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> <span data-ttu-id="8c43b-343">然後使用以下任一 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8c43b-343">Then, use any of the following cmdlets:</span></span>

- [<span data-ttu-id="8c43b-344">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="8c43b-344">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [<span data-ttu-id="8c43b-345">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="8c43b-345">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [<span data-ttu-id="8c43b-346">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="8c43b-346">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [<span data-ttu-id="8c43b-347">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="8c43b-347">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [<span data-ttu-id="8c43b-348">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="8c43b-348">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [<span data-ttu-id="8c43b-349">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="8c43b-349">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [<span data-ttu-id="8c43b-350">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="8c43b-350">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [<span data-ttu-id="8c43b-351">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="8c43b-351">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [<span data-ttu-id="8c43b-352">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="8c43b-352">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [<span data-ttu-id="8c43b-353">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="8c43b-353">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [<span data-ttu-id="8c43b-354">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="8c43b-354">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [<span data-ttu-id="8c43b-355">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="8c43b-355">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [<span data-ttu-id="8c43b-356">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="8c43b-356">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [<span data-ttu-id="8c43b-357">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="8c43b-357">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a><span data-ttu-id="8c43b-358">請使用保留原則和保留標籤，而非舊版的功能</span><span class="sxs-lookup"><span data-stu-id="8c43b-358">Use retention policies and retention labels instead of older features</span></span>

<span data-ttu-id="8c43b-359">如果您必要在 Microsoft 365 中預先主動保留或刪除內容，我們建議您使用保留原則和保留標籤，而非以下較舊的功能。</span><span class="sxs-lookup"><span data-stu-id="8c43b-359">If you need to proactively retain or delete content in Microsoft 365 for information governance, we recommend that you use retention policies and retention labels instead of the following older features.</span></span> 
  
<span data-ttu-id="8c43b-360">如果您目前使用這些較舊的功能，這些功能會隨著保留原則和保留標籤繼續運作。</span><span class="sxs-lookup"><span data-stu-id="8c43b-360">If you currently use these older features, they will continue to work side-by-side with retention policies and retention labels.</span></span> <span data-ttu-id="8c43b-361">不過，建議您今後改為使用保留原則和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="8c43b-361">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="8c43b-362">它們提供單一機制來集中管理 Microsoft 365 內容的保留與刪除。</span><span class="sxs-lookup"><span data-stu-id="8c43b-362">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="8c43b-363">**來自 Exchange Online 的舊版功能：**</span><span class="sxs-lookup"><span data-stu-id="8c43b-363">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="8c43b-364">[就地保留與訴訟暫止](https://go.microsoft.com/fwlink/?linkid=846124) (電子文件探索保留)</span><span class="sxs-lookup"><span data-stu-id="8c43b-364">[In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/?linkid=846124) (eDiscovery hold)</span></span> 

- [<span data-ttu-id="8c43b-365">如何找出位於 Exchange Online 信箱的保留類型</span><span class="sxs-lookup"><span data-stu-id="8c43b-365">How to identify the type of hold placed on an Exchange Online mailbox</span></span>](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- <span data-ttu-id="8c43b-366">[保留標記和保留原則](https://go.microsoft.com/fwlink/?linkid=846125)，又稱為[通訊記錄管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="8c43b-366">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>
    
<span data-ttu-id="8c43b-367">另請參閱[舊版電子文件探索工具淘汰](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="8c43b-367">See also [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>


<span data-ttu-id="8c43b-368">**來自 SharePoint 和 OneDrive 的舊版功能：**</span><span class="sxs-lookup"><span data-stu-id="8c43b-368">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="8c43b-369">[在電子文件探索中心將內容新增至案例及保留來源](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (電子文件探索保留)</span><span class="sxs-lookup"><span data-stu-id="8c43b-369">[Add content to a case and place sources on hold in the eDiscovery Center](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="8c43b-370">[文件刪除原則](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="8c43b-370">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="8c43b-371">[設定就地記錄管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (僅保留)</span><span class="sxs-lookup"><span data-stu-id="8c43b-371">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="8c43b-372">[網站關閉及刪除的使用原則](https://support.microsoft.com/zh-TW/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="8c43b-372">[Use policies for site closure and deletion](https://support.microsoft.com/zh-TW/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="8c43b-373">[資訊管理原則](intro-to-info-mgmt-policies.md) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="8c43b-373">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="8c43b-374">如果您之前曾為了資訊控管而使用任何電子文件探索保留，若要獲得主動合規性，請改為使用保留原則。</span><span class="sxs-lookup"><span data-stu-id="8c43b-374">If you've previously used any of the eDiscovery holds for the purpose of information governance, for proactive compliance, use a retention policy instead.</span></span> <span data-ttu-id="8c43b-375">僅對保留使用電子文件探索。</span><span class="sxs-lookup"><span data-stu-id="8c43b-375">Use eDiscovery for holds only.</span></span>
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a><span data-ttu-id="8c43b-376">保留原則和 SharePoint 內容類型原則或資訊管理原則</span><span class="sxs-lookup"><span data-stu-id="8c43b-376">Retention policies and SharePoint content type policies or information management policies</span></span>

<span data-ttu-id="8c43b-377">如果您已設定 SharePoint 網站的內容類型原則或資訊管理原則，以保留清單或文件庫的內容，當保留原則生效時，會忽略這些原則。</span><span class="sxs-lookup"><span data-stu-id="8c43b-377">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 

## <a name="related-information"></a><span data-ttu-id="8c43b-378">相關資訊</span><span class="sxs-lookup"><span data-stu-id="8c43b-378">Related information</span></span>

- [<span data-ttu-id="8c43b-379">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="8c43b-379">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="8c43b-380">Microsoft Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="8c43b-380">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="8c43b-381">符合美國證券交易委員會 (SEC) 規定 17A-4</span><span class="sxs-lookup"><span data-stu-id="8c43b-381">Comply with SEC Rule 17a-4</span></span>](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a><span data-ttu-id="8c43b-382">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8c43b-382">Next steps</span></span>

<span data-ttu-id="8c43b-383">如果您已準備好建立保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8c43b-383">If you are ready to create retention policies, see [Create and configure retention policies](create-retention-policies.md).</span></span>

<span data-ttu-id="8c43b-384">若要建立及套用保留標籤：</span><span class="sxs-lookup"><span data-stu-id="8c43b-384">To create and apply retention labels:</span></span>
- [<span data-ttu-id="8c43b-385">建立保留標籤，並在應用程式中使用這些標籤</span><span class="sxs-lookup"><span data-stu-id="8c43b-385">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="8c43b-386">自動將保留標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="8c43b-386">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)
