---
title: 了解保留原則以自動保留或刪除內容
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
description: 透過保留原則來主動決定要保留內容、刪除內容，還是兩者 (保留然後刪除內容)；將單一原則套用到整個組織或套用到特定位置或使用者；以及將原則套用到所有內容或套用到符合特定條件的內容。
ms.openlocfilehash: 377c5e1f21938204123de298e620a3d0d2bb9755
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695136"
---
# <a name="learn-about-retention-policies"></a><span data-ttu-id="036d5-103">了解保留原則</span><span class="sxs-lookup"><span data-stu-id="036d5-103">Learn about retention policies</span></span>

><span data-ttu-id="036d5-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="036d5-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="036d5-p101">對大多數組織來說，其資料 (電子郵件、文件、即時訊息等) 的數量和複雜性日益增加。有效管理或控管此資訊至關重要，因為您需要：</span><span class="sxs-lookup"><span data-stu-id="036d5-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="036d5-107">**主動遵守產業規範和內部原則**，因此您需要將某些內容至少保留一段時間，例如，Sarbanes-Oxley 法案可能會要求您將某些類型的內容保留七年。</span><span class="sxs-lookup"><span data-stu-id="036d5-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 
    
- <span data-ttu-id="036d5-108">**降低發生訴訟或安全性漏洞的風險**，方法為永久刪除您不再需要保留的舊內容。</span><span class="sxs-lookup"><span data-stu-id="036d5-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="036d5-109">**協助貴組織有效分享知識並提高靈活度**，方法為確保使用者只使用目前和相關的內容。</span><span class="sxs-lookup"><span data-stu-id="036d5-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="036d5-p102">保留原則可協助您實現所有這些目標。管理內容通常需要下列兩個動作：</span><span class="sxs-lookup"><span data-stu-id="036d5-p102">A retention policy can help you achieve all of these goals. Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="036d5-112">**保留**內容，以便無法在保留期間結束之前將其永久刪除。</span><span class="sxs-lookup"><span data-stu-id="036d5-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="036d5-113">在保留期間結束之前，永久**刪除**內容。</span><span class="sxs-lookup"><span data-stu-id="036d5-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    
<span data-ttu-id="036d5-114">透過保留原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="036d5-114">With a retention policy, you can:</span></span>
  
- <span data-ttu-id="036d5-115">主動決定是否要保留內容、刪除內容，還是兩者，即保留然後刪除內容。</span><span class="sxs-lookup"><span data-stu-id="036d5-115">Decide proactively whether to retain content, delete content, or both—retain and then delete the content.</span></span>
    
- <span data-ttu-id="036d5-116">將單一原則套用到整個組織或套用到特定位置或使用者。</span><span class="sxs-lookup"><span data-stu-id="036d5-116">Apply a single policy to the entire organization or specific locations or users.</span></span>
    
- <span data-ttu-id="036d5-117">將原則套用到所有內容或套用到符合特定條件的內容，例如包含關鍵字或[敏感性資訊類型](what-the-sensitive-information-types-look-for.md)的內容。</span><span class="sxs-lookup"><span data-stu-id="036d5-117">Apply a policy to all content or to content when it meets specific conditions, such as content containing keywords or [types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
    
<span data-ttu-id="036d5-p103">當內容受限於保留原則時，人員可以繼續編輯及使用該內容，就像是完全沒變更一般。內容會保留在其原始位置。但在某人編輯或刪除受限於保留原則的內容時，則會在該內容的保留原則有效時，將原始內容的複本儲存至保留它所在的安全位置。如需詳細資訊，請參閱此頁面上的[保留原則如何與就地內容搭配使用](#how-a-retention-policy-works-with-content-in-place)一節</span><span class="sxs-lookup"><span data-stu-id="036d5-p103">When content is subject to a retention policy, people can continue to edit and work with the content as if nothing's changed. The content is retained in place, in its original location. But if someone edits or deletes content that's subject to the retention policy, a copy of the original content is saved to a secure location where it's retained while the retention policy for that content is in effect. For more information, see the [How a retention policy works with content in place](#how-a-retention-policy-works-with-content-in-place) section on this page</span></span>
  
<span data-ttu-id="036d5-122">此外，某些組織必須遵守美國證券交易委員會 (SEC) 規定 17a-4 等法規。</span><span class="sxs-lookup"><span data-stu-id="036d5-122">Additionally, some organizations have to comply with regulations such as Securities and Exchange Commission (SEC) Rule 17a-4.</span></span> <span data-ttu-id="036d5-123">這項法規要求在開啟保留原則之後，不能關閉該原則或執行較不嚴格的限制。</span><span class="sxs-lookup"><span data-stu-id="036d5-123">This regulation requires that after a retention policy is turned on, it cannot be turned off or made less restrictive.</span></span> <span data-ttu-id="036d5-124">若要滿足這個需求，您可以使用**保留鎖定**。</span><span class="sxs-lookup"><span data-stu-id="036d5-124">To meet this requirement, you can use **Preservation Lock**.</span></span> <span data-ttu-id="036d5-125">原則保留鎖定之後，任何人 (包括系統管理員) 均無法關閉保留原則或執行較不嚴格的限制。</span><span class="sxs-lookup"><span data-stu-id="036d5-125">After a retention policy's been locked, no one (including an administrator) can turn off the retention policy or make it less restrictive.</span></span> <span data-ttu-id="036d5-126">如需詳細資訊，請參閱此頁面上的[使用保留鎖定以符合法規需求](#use-preservation-lock-to-comply-with-regulatory-requirements)一節。</span><span class="sxs-lookup"><span data-stu-id="036d5-126">For more information, see the [Use Preservation Lock to comply with regulatory requirements](#use-preservation-lock-to-comply-with-regulatory-requirements) section on this page.</span></span>

## <a name="how-a-retention-policy-works-with-content-in-place"></a><span data-ttu-id="036d5-127">保留原則如何與就地內容搭配使用</span><span class="sxs-lookup"><span data-stu-id="036d5-127">How a retention policy works with content in place</span></span>

<span data-ttu-id="036d5-128">當您在保留原則中包含網站或信箱等位置時，內容會維持在其原本的位置。</span><span class="sxs-lookup"><span data-stu-id="036d5-128">When you include a location such as a site or mailbox in a retention policy, the content remains in its original location.</span></span> <span data-ttu-id="036d5-129">若未發生任何變更，人員可以繼續使用其文件或郵件。</span><span class="sxs-lookup"><span data-stu-id="036d5-129">People can continue to work with their documents or mail as if nothing's changed.</span></span> <span data-ttu-id="036d5-130">但如果人員編輯或刪除保留原則中包含的內容，則會保留您套用原則時即存在的內容複本。</span><span class="sxs-lookup"><span data-stu-id="036d5-130">But if they edit or delete content that's included in the retention policy, a copy of the content is retained as it existed when you applied the policy.</span></span>
  
- <span data-ttu-id="036d5-131">對於 SharePoint 和 OneDrive 網站：複本會保留在**文件保留庫**中。</span><span class="sxs-lookup"><span data-stu-id="036d5-131">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span> <span data-ttu-id="036d5-132">請注意，文件保留庫會佔用網站的儲存空間配額。</span><span class="sxs-lookup"><span data-stu-id="036d5-132">Be aware that the Preservation Hold library consumes storage quota for the site.</span></span>

- <span data-ttu-id="036d5-133">對於電子郵件和公用資料夾：複本會保留在 [可復原的項目]\*\*\*\* 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="036d5-133">For email and public folders: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="036d5-134">針對 Teams 內容：複本會保留在 Exchange [可復原的項目]\*\*\*\* 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="036d5-134">For Teams content: The copy is retained in the Exchange **Recoverable Items** folder.</span></span>

- <span data-ttu-id="036d5-135">若為 Microsoft 365 群組 ([先前稱為 Office 365 群組](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))：</span><span class="sxs-lookup"><span data-stu-id="036d5-135">For Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)):</span></span> 
    - <span data-ttu-id="036d5-136">群組信箱會保留在 Exchange [可復原的項目]\*\*\*\* 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="036d5-136">The group mailbox is retained in the Exchange **Recoverable Items** folder.</span></span>
    - <span data-ttu-id="036d5-137">任何網站內容都會保留在 [文件保留庫]\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="036d5-137">Any site content is retained in the **Preservation Hold** library.</span></span>

> [!NOTE]
> <span data-ttu-id="036d5-138">[文件保留庫] 會佔用不受網站儲存空間配額限制的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="036d5-138">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota.</span></span> <span data-ttu-id="036d5-139">當您對 SharePoint 和 Microsoft 365 群組使用保留原則時，可能需要增加您的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="036d5-139">You might need to increase your storage when you use retention policies for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="036d5-140">大部分的人員無法檢視這些安全的位置和保留的內容。</span><span class="sxs-lookup"><span data-stu-id="036d5-140">These secure locations and the retained content are not visible to most people.</span></span> <span data-ttu-id="036d5-141">透過保留原則，人員甚至不需要知道其內容受限於原則。</span><span class="sxs-lookup"><span data-stu-id="036d5-141">With a retention policy, people do not even need to know that their content is subject to the policy.</span></span>

<span data-ttu-id="036d5-142">如需有關保留原則如何搭配不同工作負載使用的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="036d5-142">For more detailed information about how retention policies work with different workloads, see the following articles:</span></span>

- [<span data-ttu-id="036d5-143">了解 SharePoint 和 OneDrive 的保留原則</span><span class="sxs-lookup"><span data-stu-id="036d5-143">Learn about retention policies for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="036d5-144">了解 Microsoft Teams 的保留原則</span><span class="sxs-lookup"><span data-stu-id="036d5-144">Learn about retention policies for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="036d5-145">了解 Exchange 的保留原則</span><span class="sxs-lookup"><span data-stu-id="036d5-145">Learn about retention policies for Exchange</span></span>](retention-policies-exchange.md)

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="036d5-146">系統會優先處理保留原則嗎？</span><span class="sxs-lookup"><span data-stu-id="036d5-146">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="036d5-147">內容有可能套用多個會進行不同動作 (保留、刪除或保留然後刪除) 且保留期間不同的保留原則。</span><span class="sxs-lookup"><span data-stu-id="036d5-147">It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or retain and then delete) and retention period.</span></span> <span data-ttu-id="036d5-148">哪個的優先順序較高？</span><span class="sxs-lookup"><span data-stu-id="036d5-148">What takes precedence?</span></span> <span data-ttu-id="036d5-149">在最高層級中，某個保留原則所保留的內容無法被另一個保留原則永久刪除。</span><span class="sxs-lookup"><span data-stu-id="036d5-149">At the highest level, rest assured that content being retained by one retention policy can't be permanently deleted by another retention policy.</span></span>
  
![原則保留圖](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="036d5-151">若要了解不同的保留原則如何套用至內容，請記住以下保留原則：</span><span class="sxs-lookup"><span data-stu-id="036d5-151">To understand how different retention policies are applied to content, keep these principles of retention in mind:</span></span>
  
1. <span data-ttu-id="036d5-152">**保留優先於刪除。**</span><span class="sxs-lookup"><span data-stu-id="036d5-152">**Retention wins over deletion.**</span></span> <span data-ttu-id="036d5-153">假設某個保留原則設定在 3 年後刪除 Exchange 電子郵件，但另一個保留原則設定將 Exchange 電子郵件保留 5 年再刪除。</span><span class="sxs-lookup"><span data-stu-id="036d5-153">Suppose that one retention policy is configured to delete Exchange email after three years, but another retention policy is configured to retain Exchange email for five years and then delete it.</span></span> <span data-ttu-id="036d5-154">任何到達 3 年的內容會遭到刪除，並從使用者的檢視畫面隱藏，但仍會保留再 [可復原的項目] 資料夾中，直到內容到達 5 年，才會遭永久刪除。</span><span class="sxs-lookup"><span data-stu-id="036d5-154">Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it is permanently deleted.</span></span> 
    
2. <span data-ttu-id="036d5-155">**最長保留期間優先。**</span><span class="sxs-lookup"><span data-stu-id="036d5-155">**The longest retention period wins.**</span></span> <span data-ttu-id="036d5-156">如果內容受多個用於保留內容的保留原則所限制，系統會將該內容保留最長的保留期間。</span><span class="sxs-lookup"><span data-stu-id="036d5-156">If content is subject to multiple retention policies that retain content, it will be retained until the end of the longest retention period.</span></span> 
    
3. <span data-ttu-id="036d5-157">**明確包含優先於隱含包含。**</span><span class="sxs-lookup"><span data-stu-id="036d5-157">**Explicit inclusion wins over implicit inclusion.**</span></span> <span data-ttu-id="036d5-158">也就是說：</span><span class="sxs-lookup"><span data-stu-id="036d5-158">This means:</span></span> 
    
    1. <span data-ttu-id="036d5-159">如果包含保留設定的保留標籤是由使用者手動指派至項目 (例如 Exchange 電子郵件或 OneDrive 文件)，則該保留標籤會優先於在網站或信箱層級指派的保留原則，以及文件庫指派的預設保留標籤。</span><span class="sxs-lookup"><span data-stu-id="036d5-159">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a retention policy assigned at the site or mailbox level and a default retention label assigned by the document library.</span></span> <span data-ttu-id="036d5-160">例如，如果明確保留標籤設定要保留內容 10 年，但對網站指派的保留原則設定為保留內容 5 年，則保留標籤會優先於原則。</span><span class="sxs-lookup"><span data-stu-id="036d5-160">For example, if the explicit retention label is configured to retain content for 10 years, but the retention policy assigned to the site is configured to retain content for only five years, the retention label takes precedence.</span></span> <span data-ttu-id="036d5-161">自動套用的保留標籤會被視為隱含，而非明確，因為這類標籤是由 Microsoft 365 自動套用。</span><span class="sxs-lookup"><span data-stu-id="036d5-161">Auto-applied retention labels are considered implicit rather than explicit, because they're applied automatically by Microsoft 365.</span></span>
    
    2. <span data-ttu-id="036d5-162">如果保留原則包含特定位置 (例如特定使用者的信箱或 OneDrive 帳戶)，則該保留原則會優先於其他套用至所有使用者信箱或 OneDrive 帳戶但未特地包含該使用者信箱的保留原則。</span><span class="sxs-lookup"><span data-stu-id="036d5-162">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive account, that retention policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="036d5-163">**最短刪除期間優先。**</span><span class="sxs-lookup"><span data-stu-id="036d5-163">**The shortest deletion period wins.**</span></span> <span data-ttu-id="036d5-164">同樣地，如果內容受限於會刪除內容但不帶保留期間的多個保留原則，則會在最短刪除期間結束時刪除該內容。</span><span class="sxs-lookup"><span data-stu-id="036d5-164">Similarly, if content is subject to multiple retention policies that delete content without a retention period, that content will be deleted at the end of the shortest retention period.</span></span> 
    
<span data-ttu-id="036d5-165">了解保留原則從上到下的仲裁流程：如果所有保留原則或保留標籤套用的規則都在同一個層級，則流程會移到下一個層級來決定套用規則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="036d5-165">Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all retention policies or retention labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.</span></span>
  
<span data-ttu-id="036d5-166">最終，保留原則或保留標籤無法永久刪除任何電子文件探索保留的內容。</span><span class="sxs-lookup"><span data-stu-id="036d5-166">Finally, a retention policy or retention label cannot permanently delete any content that's on hold for eDiscovery.</span></span> <span data-ttu-id="036d5-167">將保留釋出時，該內容會再次符合上述的清理程序資格。</span><span class="sxs-lookup"><span data-stu-id="036d5-167">When the hold is released, the content again becomes eligible for the cleanup process described above.</span></span>

## <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a><span data-ttu-id="036d5-168">使用保留鎖定以符合法規需求</span><span class="sxs-lookup"><span data-stu-id="036d5-168">Use Preservation Lock to comply with regulatory requirements</span></span>

<span data-ttu-id="036d5-169">有些組織可能需要遵守由控管機構定義的法規，例如證券交易委員會 (SEC) 規定 17a-4，要求在保留原則開啟之後，不能關閉或執行較不嚴格的限制。</span><span class="sxs-lookup"><span data-stu-id="036d5-169">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a retention policy is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="036d5-170">「保留鎖定」可確保您的組織能夠符合這類法規需求，因為它會鎖定保留原則，使得沒有任何人 (包括系統管理員) 可以關閉原則或降低限制。</span><span class="sxs-lookup"><span data-stu-id="036d5-170">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy so that no one—including the administrator—can turn off the policy or make it less restrictive.</span></span>
  
<span data-ttu-id="036d5-171">鎖定保留原則時：</span><span class="sxs-lookup"><span data-stu-id="036d5-171">When a retention policy is locked:</span></span>

- <span data-ttu-id="036d5-172">沒有人可以關閉它</span><span class="sxs-lookup"><span data-stu-id="036d5-172">No one can it turn off</span></span>
- <span data-ttu-id="036d5-173">可以新增位置但不能移除位置</span><span class="sxs-lookup"><span data-stu-id="036d5-173">Locations can be added but not removed</span></span> 
- <span data-ttu-id="036d5-174">不能在保留期間修改或刪除受限於原則的內容</span><span class="sxs-lookup"><span data-stu-id="036d5-174">Content subject to the policy can't be modified or deleted during the retention period</span></span>
- <span data-ttu-id="036d5-175">您可以延長保留期間，但不能減少保留期間</span><span class="sxs-lookup"><span data-stu-id="036d5-175">You can extend a retention period but not decrease it</span></span>

<span data-ttu-id="036d5-176">總而言之，鎖定的保留原則可以增加或延長，但是不能減少或關閉。</span><span class="sxs-lookup"><span data-stu-id="036d5-176">In summary, a locked retention policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="036d5-177">在您鎖定保留原則之前，務必了解影響，並確認您的組織是否需要符合合規性需求。</span><span class="sxs-lookup"><span data-stu-id="036d5-177">Before you lock a retention policy, it's critical that you understand the impact and confirm whether it's required for your organization to meet compliance requirements.</span></span>

## <a name="releasing-a-retention-policy"></a><span data-ttu-id="036d5-178">釋出保留原則</span><span class="sxs-lookup"><span data-stu-id="036d5-178">Releasing a retention policy</span></span>

<span data-ttu-id="036d5-179">如果您的保留原則沒有保留鎖定，則可以隨時關閉或刪除保留原則。</span><span class="sxs-lookup"><span data-stu-id="036d5-179">Providing your retention policy doesn't have a Preservation Lock, you can turn off or delete a retention policy at any time.</span></span> 

<span data-ttu-id="036d5-180">當您這麼做時，保留在文件保留庫中的任何 SharePoint 或 OneDrive 的內容不會立即永久被刪除。</span><span class="sxs-lookup"><span data-stu-id="036d5-180">When you do so, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="036d5-181">相反地，為了防止意外的資料遺失，我們有 30 天的寬限期，在這期間，保留文件庫中不會發生該原則的內容到期，因此，如有需要，您可以在這裡還原任何內容。</span><span class="sxs-lookup"><span data-stu-id="036d5-181">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="036d5-182">此外，您無法在寬限期期間手動刪除此內容。</span><span class="sxs-lookup"><span data-stu-id="036d5-182">Additionally, you can't manually delete this content during the grace period.</span></span>

<span data-ttu-id="036d5-183">您可以在寬限期期間再次開啟保留原則，這麼一來，將不會刪除該原則的內容。</span><span class="sxs-lookup"><span data-stu-id="036d5-183">You can turn on the retention policy again during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="036d5-184">SharePoint 和 OneDrive 中的此 30 天寬限期與 Exchange 中的 30 天延遲保留對應。</span><span class="sxs-lookup"><span data-stu-id="036d5-184">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="036d5-185">如需詳細資訊，請參閱[管理延遲保留信箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。</span><span class="sxs-lookup"><span data-stu-id="036d5-185">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

## <a name="use-a-retention-policy-instead-of-older-features"></a><span data-ttu-id="036d5-186">使用保留原則，而非較舊的功能</span><span class="sxs-lookup"><span data-stu-id="036d5-186">Use a retention policy instead of older features</span></span>

<span data-ttu-id="036d5-187">您可以輕鬆地將單一保留原則套用到整個組織，以及 Microsoft 365 中的多個位置，包括 Exchange Online、SharePoint Online、OneDrive 和 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="036d5-187">A single retention policy can easily apply to an entire organization and locations across Microsoft 365, including Exchange Online, SharePoint Online, OneDrive, and Microsoft 365 groups.</span></span> <span data-ttu-id="036d5-188">如果您需要保留或刪除 Microsoft 365 任何位置中的內容，建議您使用保留原則，並選擇性地使用[保留標籤](labels.md)來加以補充。</span><span class="sxs-lookup"><span data-stu-id="036d5-188">If you need to retain or delete content anywhere in Microsoft 365, we recommend that you use a retention policy and optionally supplement this with [retention labels](labels.md).</span></span>
  
<span data-ttu-id="036d5-189">如果您先前曾使用其他設定來保留或刪除 Microsoft 365 中的內容，該設定會繼續搭配保留原則和保留標籤運作。</span><span class="sxs-lookup"><span data-stu-id="036d5-189">If you have previously used other configurations to retain or delete content in Microsoft 365, they will continue to work side by side with retention policies and retention labels.</span></span> <span data-ttu-id="036d5-190">不過，建議您今後改為使用保留原則和保留標籤。</span><span class="sxs-lookup"><span data-stu-id="036d5-190">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="036d5-191">它們提供單一機制來集中管理 Microsoft 365 內容的保留與刪除。</span><span class="sxs-lookup"><span data-stu-id="036d5-191">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="036d5-192">您可能已使用的舊版功能：</span><span class="sxs-lookup"><span data-stu-id="036d5-192">The older features that you might have used:</span></span>
  
<span data-ttu-id="036d5-193">**來自 Exchange Online 的舊版功能：**</span><span class="sxs-lookup"><span data-stu-id="036d5-193">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="036d5-194">[就地保留與訴訟暫止](https://go.microsoft.com/fwlink/?linkid=846124) (電子文件探索保留)</span><span class="sxs-lookup"><span data-stu-id="036d5-194">[In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/?linkid=846124) (eDiscovery hold)</span></span> 

- [<span data-ttu-id="036d5-195">如何找出位於 Exchange Online 信箱的保留類型</span><span class="sxs-lookup"><span data-stu-id="036d5-195">How to identify the type of hold placed on an Exchange Online mailbox</span></span>](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- <span data-ttu-id="036d5-196">[保留標記和保留原則](https://go.microsoft.com/fwlink/?linkid=846125)，又稱為[通訊記錄管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="036d5-196">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>
    
<span data-ttu-id="036d5-197">另請參閱[舊版電子文件探索工具淘汰](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="036d5-197">See also [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>


<span data-ttu-id="036d5-198">**來自 SharePoint 和 OneDrive 的舊版功能：**</span><span class="sxs-lookup"><span data-stu-id="036d5-198">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="036d5-199">[在電子文件探索中心將內容新增至案例及保留來源](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (電子文件探索保留)</span><span class="sxs-lookup"><span data-stu-id="036d5-199">[Add content to a case and place sources on hold in the eDiscovery Center](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="036d5-200">[文件刪除原則](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="036d5-200">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="036d5-201">[設定就地記錄管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (僅保留)</span><span class="sxs-lookup"><span data-stu-id="036d5-201">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="036d5-202">[網站關閉及刪除的使用原則](https://support.microsoft.com/zh-TW/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="036d5-202">[Use policies for site closure and deletion](https://support.microsoft.com/zh-TW/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="036d5-203">[資訊管理原則](intro-to-info-mgmt-policies.md) (僅刪除)</span><span class="sxs-lookup"><span data-stu-id="036d5-203">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="036d5-204">如果您之前曾為了資訊控管而使用任何電子文件探索保留，若要獲得主動合規性，請改為使用保留原則。</span><span class="sxs-lookup"><span data-stu-id="036d5-204">If you've previously used any of the eDiscovery holds for the purpose of information governance, for proactive compliance, use a retention policy instead.</span></span> <span data-ttu-id="036d5-205">僅對保留使用電子文件探索。</span><span class="sxs-lookup"><span data-stu-id="036d5-205">Use eDiscovery for holds only.</span></span>
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a><span data-ttu-id="036d5-206">保留原則和 SharePoint 內容類型原則或資訊管理原則</span><span class="sxs-lookup"><span data-stu-id="036d5-206">Retention policies and SharePoint content type policies or information management policies</span></span>

<span data-ttu-id="036d5-207">如果您已設定 SharePoint 網站的內容類型原則或資訊管理原則，以保留清單或文件庫的內容，當保留原則生效時，會忽略這些原則。</span><span class="sxs-lookup"><span data-stu-id="036d5-207">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 
  
### <a name="preservation-policies-are-converted-to-retention-policies"></a><span data-ttu-id="036d5-208">保留原則會轉換為保留原則</span><span class="sxs-lookup"><span data-stu-id="036d5-208">Preservation policies are converted to retention policies</span></span>

<span data-ttu-id="036d5-209">如果您過去使用保留原則來保留信箱、SharePoint 或 OneDrive 網站或公用資料夾中的資料：該原則會自動轉換成僅使用保留動作的保留原則 (該原則不會刪除內容)。</span><span class="sxs-lookup"><span data-stu-id="036d5-209">If you were using a preservation policy to retain data in mailboxes, SharePoint or OneDrive sites, or public folders: That policy has been automatically converted to a retention policy that uses only the retain action—the policy won't delete content.</span></span> <span data-ttu-id="036d5-210">您不需要進行任何變更，就能獲得與您設定保留原則相同的效果。</span><span class="sxs-lookup"><span data-stu-id="036d5-210">No changes are needed from you for the same outcome as your configured preservation policy.</span></span>

<span data-ttu-id="036d5-211">您可以在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)的 [原則]\*\*\*\* 頁面，或在[安全性與合規性中心](https://protection.office.com/) 的 [資訊控管]\*\*\*\* 下的 [保留]\*\*\*\* 頁面上尋找任何設定的保留原則。&amp;</span><span class="sxs-lookup"><span data-stu-id="036d5-211">You can find any configured preservation policies on the **Policies** page in the [Microsoft 365 compliance center](https://compliance.microsoft.com/), or on the **Retention** page under **Information governance** in the [Security &amp; Compliance Center](https://protection.office.com/).</span></span> <span data-ttu-id="036d5-212">您可以編輯保留原則以變更保留期間，但您不能進行其他變更，例如新增或移除位置。</span><span class="sxs-lookup"><span data-stu-id="036d5-212">You can edit a preservation policy to change the retention period, but you can't make other changes, such as adding or removing locations.</span></span> 


## <a name="related-information"></a><span data-ttu-id="036d5-213">相關資訊</span><span class="sxs-lookup"><span data-stu-id="036d5-213">Related information</span></span>

- [<span data-ttu-id="036d5-214">了解保留標籤</span><span class="sxs-lookup"><span data-stu-id="036d5-214">Learn about retention labels</span></span>](labels.md)
- [<span data-ttu-id="036d5-215">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="036d5-215">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="036d5-216">Microsoft Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="036d5-216">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="036d5-217">符合美國證券交易委員會 (SEC) 規定 17A-4</span><span class="sxs-lookup"><span data-stu-id="036d5-217">Comply with SEC Rule 17a-4</span></span>](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a><span data-ttu-id="036d5-218">後續步驟</span><span class="sxs-lookup"><span data-stu-id="036d5-218">Next steps</span></span>

<span data-ttu-id="036d5-219">如果您已準備好建立保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="036d5-219">If you are ready to create retention polices, see [Create and configure retention policies](create-retention-policies.md).</span></span>

