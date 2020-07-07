---
title: 了解 Exchange 的保留
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
description: 了解 Exchange 電子郵件和 Exchange 公用資料夾專屬的保留行為。
ms.openlocfilehash: aa4142db2114b2b58cc391429f1389c6b9fad52d
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049891"
---
# <a name="learn-about-retention-policies-for-exchange"></a><span data-ttu-id="5ba65-103">了解 Exchange 的保留原則</span><span class="sxs-lookup"><span data-stu-id="5ba65-103">Learn about retention policies for Exchange</span></span>

<span data-ttu-id="5ba65-104">本文中的資訊可補充[了解保留原則](retention-policies.md)，因為其包含 Exchange 專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="5ba65-104">The information in this article supplements [Learn about retention policies](retention-policies.md) because it has information that's specific to Exchange.</span></span>

## <a name="how-a-retention-policy-works-with-exchange-locations"></a><span data-ttu-id="5ba65-105">保留原則如何與 Exchange 位置搭配使用</span><span class="sxs-lookup"><span data-stu-id="5ba65-105">How a retention policy works with Exchange locations</span></span>

<span data-ttu-id="5ba65-106">對於使用者的信箱、行事曆和其他項目，保留原則會在信箱層級套用。</span><span class="sxs-lookup"><span data-stu-id="5ba65-106">For a user's mail, calendar, and other items, a retention policy is applied at the level of a mailbox.</span></span>

<span data-ttu-id="5ba65-107">對於公用資料夾，保留原則會套用在資料夾層級套用，而不是信箱層級。</span><span class="sxs-lookup"><span data-stu-id="5ba65-107">For a public folder, a retention policy is applied at the folder level, not the mailbox level.</span></span> 

<span data-ttu-id="5ba65-108">信箱和公用資料夾都是使用 [可復原的項目][](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) 資料夾來保留項目。</span><span class="sxs-lookup"><span data-stu-id="5ba65-108">Both a mailbox and a public folder use the [Recoverable Items folder](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) to retain items.</span></span> <span data-ttu-id="5ba65-109">已獲指派電子文件探索權限的人員可以檢視其他使用者的 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="5ba65-109">Only people who have been assigned eDiscovery permissions can view items in another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="5ba65-110">當使用者從 [刪除的郵件] 資料夾以外的資料夾刪除郵件時，根據預設，會將該郵件移至 [刪除的郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="5ba65-110">When a person deletes a message in a folder other than the Deleted Items folder, by default, the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="5ba65-111">當使用者從 [刪除的郵件] 資料夾中刪除項目時，郵件會移至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="5ba65-111">When a person deletes an item in the Deleted Items folder, the message is moved to the Recoverable Items folder.</span></span> <span data-ttu-id="5ba65-112">不過，使用者可以將任何資料夾中的項目虛刪除 (Shift+Delete)，這會略過 [刪除的郵件] 資料夾，並將項目移至 [可復原的項目] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="5ba65-112">However, a user can soft delete an item (Shift+Delete) in any folder, which bypasses the Deleted Items folder and moves the item directly to the Recoverable Items folder.</span></span>
  
<span data-ttu-id="5ba65-113">將保留原則套用至 Exchange 位置時，計時器工作會定期評估 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="5ba65-113">When you apply a retention policy to an Exchange location, a timer job periodically evaluates items in the Recoverable Items folder.</span></span> <span data-ttu-id="5ba65-114">如果項目不符合至少一個保留原則的規則，則會永久刪除 [可復原的項目] 資料夾中的項目 (也就是「實刪除」)。</span><span class="sxs-lookup"><span data-stu-id="5ba65-114">If an item doesn't match the rules of at least one retention policy, the item is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>

<span data-ttu-id="5ba65-115">計時器工作最多可能需要七天才能執行，且 Exchange 位置必須包含至少 10 MB。</span><span class="sxs-lookup"><span data-stu-id="5ba65-115">The timer job can take up to seven days to run and the Exchange location must contain at least 10 MB.</span></span>
  
<span data-ttu-id="5ba65-116">當使用者嘗試變更信箱項目的內容時 (例如主旨、內文、附件、寄件者和收件者，或是傳送或接收郵件的日期)，在認可變更之前，會先將原始項目的複本儲存至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="5ba65-116">When a user attempts to change properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Recoverable Items folder before the change is committed.</span></span> <span data-ttu-id="5ba65-117">後續每次變更都會執行此動作。</span><span class="sxs-lookup"><span data-stu-id="5ba65-117">This action happens for each subsequent change.</span></span> <span data-ttu-id="5ba65-118">在保留期間結束時，系統會永久刪除 [可復原的項目] 資料夾中的複本。</span><span class="sxs-lookup"><span data-stu-id="5ba65-118">At the end of the retention period, copies in the Recoverable Items folder are permanently deleted.</span></span>

<span data-ttu-id="5ba65-119">將保留原則指派至信箱或公用資料夾後，內容的路徑會取決於保留設定為保留和刪除、僅保留或僅刪除。</span><span class="sxs-lookup"><span data-stu-id="5ba65-119">After a retention policy is assigned to a mailbox or public folder, the paths the content takes depend on whether the retention settings are to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="5ba65-120">當保留設定為保留和刪除時：</span><span class="sxs-lookup"><span data-stu-id="5ba65-120">When the retention settings are to retain and delete:</span></span>

![電子郵件和公用資料夾中的保留流程圖](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. <span data-ttu-id="5ba65-122">**如果使用者在保留期間修改或永久刪除項目** (按 SHIFT+DELETE 或從 [刪除的郵件] 刪除)：系統會將項目移動 (或複製 - 在編輯的情況下) 到 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="5ba65-122">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period: The item is moved (or copied, in the case of edit) to the Recoverable Items folder.</span></span> <span data-ttu-id="5ba65-123">計時器工作會在此處定期執行，並識別保留期間已過期的項目，而且會在保留期間結束的 14 天內永久刪除這些項目。</span><span class="sxs-lookup"><span data-stu-id="5ba65-123">There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="5ba65-124">請注意，14 天是預設的設定，但最多可設定為 30 天。</span><span class="sxs-lookup"><span data-stu-id="5ba65-124">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span>

2. <span data-ttu-id="5ba65-125">**如果未在保留期間修改或刪除項目**：系統會在信箱中的所有資料夾上定期執行相同程序，找到保留期間已過期的項目，並在保留期間結束的 14 天內永久刪除這些項目。</span><span class="sxs-lookup"><span data-stu-id="5ba65-125">**If the item is not modified or deleted** during the retention period: The same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="5ba65-126">請注意，14 天是預設的設定，但最多可設定為 30 天。</span><span class="sxs-lookup"><span data-stu-id="5ba65-126">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span> 

<span data-ttu-id="5ba65-127">當保留設定為僅保留或僅刪除時，內容路徑為保留和刪除的變化：</span><span class="sxs-lookup"><span data-stu-id="5ba65-127">When the retention settings are retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-settings"></a><span data-ttu-id="5ba65-128">僅保留保留設定的內容路徑</span><span class="sxs-lookup"><span data-stu-id="5ba65-128">Content paths for retain-only retention settings</span></span>

1. <span data-ttu-id="5ba65-129">在保留期間，**如果項目遭修改或刪除**：則會在 [可復原的項目] 資料夾中建立原始項目的複本，並保留到保留期間結束時，然後在該項目到期後 14 天內永久刪除 [可復原的項目] 資料夾中的複本。</span><span class="sxs-lookup"><span data-stu-id="5ba65-129">**If the item is modified or deleted** during the retention period: A copy of the original item is created in the Recoverable Items folder and retained until the end of the retention period, when the copy in the Recoverable Items folder is permanently deleted within 14 days after the item expires.</span></span> 

2. <span data-ttu-id="5ba65-130">在保留期間，**如果未修改或刪除項目**：保留期間前後沒有任何變化；項目仍會保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="5ba65-130">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the item remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-settings"></a><span data-ttu-id="5ba65-131">僅刪除保留設定的內容路徑</span><span class="sxs-lookup"><span data-stu-id="5ba65-131">Content paths for delete-only retention settings</span></span>

1. <span data-ttu-id="5ba65-132">**如果未在保留期間刪除項目**：在保留原則中設定的期間結束時，系統會將項目移至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="5ba65-132">**If the item is not deleted** during the configured period: At the end of the configured period in the retention policy, the item is moved to the Recoverable Items folder.</span></span> 

2. <span data-ttu-id="5ba65-133">**如果在保留期間刪除項目**：系統會立即將項目移至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="5ba65-133">**If the item is deleted** during the configured period: The item is immediately moved to the Recoverable Items folder.</span></span> <span data-ttu-id="5ba65-134">如果使用者從該處刪除項目或清空 [可復原的項目] 資料夾，就會永久刪除項目。</span><span class="sxs-lookup"><span data-stu-id="5ba65-134">If a user deletes the item from there or empties the Recoverable Items folder, the item is permanently deleted.</span></span> <span data-ttu-id="5ba65-135">否則，系統會在項目在 [可復原的項目] 資料夾中保留 14 天後永久刪除。</span><span class="sxs-lookup"><span data-stu-id="5ba65-135">Otherwise, the item is permanently deleted after being in the Recoverable Items folder for 14 days.</span></span> 

## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a><span data-ttu-id="5ba65-136">從保留原則中排除特定類型的 Exchange 項目</span><span class="sxs-lookup"><span data-stu-id="5ba65-136">Excluding specific types of Exchange items from a retention policy</span></span>

<span data-ttu-id="5ba65-137">您可以使用 PowerShell，在保留原則設定為僅保留時，從保留原則中排除特定類型的 Exchange 項目。</span><span class="sxs-lookup"><span data-stu-id="5ba65-137">By using PowerShell, you can exclude specific types of Exchange items from a retention policy when the retention settings are for retain-only.</span></span> <span data-ttu-id="5ba65-138">例如，您可以排除語音信箱訊息、IM 交談，與信箱中的其他商務用 Skype Online 內容。</span><span class="sxs-lookup"><span data-stu-id="5ba65-138">For example, you can exclude voicemail messages, IM conversations, and other Skype for Business Online content in mailboxes.</span></span> <span data-ttu-id="5ba65-139">您也可以排除行事曆、筆記和工作項目。</span><span class="sxs-lookup"><span data-stu-id="5ba65-139">You can also exclude calendar, note, and task items.</span></span> <span data-ttu-id="5ba65-140">此功能僅在使用 PowerShell 時才可供使用；當您在 Microsoft 365 合規性中心使用精靈建立保留原則時，無法使用此功能。</span><span class="sxs-lookup"><span data-stu-id="5ba65-140">This capability is available only by using PowerShell; it's not available when you create a retention policy by using the wizard in the Microsoft 365 compliance center.</span></span>
  
<span data-ttu-id="5ba65-141">若要在保留原則中排除您選取的 Exchange 項目類型，請使用 [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) 和 [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule) Cmdlet 搭配 `ExcludedItemClasses` 參數。</span><span class="sxs-lookup"><span data-stu-id="5ba65-141">To exclude your selected types for Exchange items in a retention policy, use the  `ExcludedItemClasses` parameter with the [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) and  [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule) cmdlets.</span></span>

<span data-ttu-id="5ba65-142">若要使用保留原則 Cmdlet，您必須先[連線至安全性與合規性中心 Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="5ba65-142">To use the retention policies cmdlets, you must first [connect to Security & Compliance Center Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="5ba65-143">當使用者離開組織時</span><span class="sxs-lookup"><span data-stu-id="5ba65-143">When a user leaves the organization</span></span> 

<span data-ttu-id="5ba65-144">如果組織中的使用者離職，且保留原則中包含使用者的信箱，在刪除使用者的 Microsoft 365 帳戶後，信箱會變成非作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="5ba65-144">If a user leaves your organization and the user's mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Microsoft 365 account is deleted.</span></span> <span data-ttu-id="5ba65-145">在變成非作用的狀態之前，非作用中信箱的內容仍受限於信箱上所設之任何保留原則，且內容可供電子文件探索搜尋。</span><span class="sxs-lookup"><span data-stu-id="5ba65-145">The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="5ba65-146">如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="5ba65-146">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

## <a name="how-to-configure-a-retention-policy-for-exchange"></a><span data-ttu-id="5ba65-147">如何為 Exchange 設定保留原則</span><span class="sxs-lookup"><span data-stu-id="5ba65-147">How to configure a retention policy for Exchange</span></span>

<span data-ttu-id="5ba65-148">按照 [建立及設定保留原則][](create-retention-policies.md) 和 [選擇位置]\*\*\*\* 精靈頁面中的指示進行，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="5ba65-148">Follow the instructions for [Create and configure retention policies](create-retention-policies.md) and for the **Choose locations**  page of the wizard, select one of the following options:</span></span>

- <span data-ttu-id="5ba65-149">**僅將原則套用到 Exchange 電子郵件、公用資料夾、Office 365 群組、OneDrive 及 SharePoint 文件中的內容**</span><span class="sxs-lookup"><span data-stu-id="5ba65-149">**Apply policy only to content in Exchange email, public folders, Office 365 groups, OneDrive and SharePoint documents**</span></span>

- <span data-ttu-id="5ba65-150">**[讓我選擇特定位置]** > **[Exchange 電子郵件]**、**[Exchange 公開資料夾]**，和 **[Office 365 群組]**。</span><span class="sxs-lookup"><span data-stu-id="5ba65-150">**Let me choose specific locations** > **Exchange email**, **Exchange public folders**, and **Office 365 groups**.</span></span>

<span data-ttu-id="5ba65-151">即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件**位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="5ba65-151">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="5ba65-152">若要保留這些信箱中的內容，請選取 **[Office 365 群組]** 位置。</span><span class="sxs-lookup"><span data-stu-id="5ba65-152">To retain content in these mailboxes, select the **Office 365 groups** location.</span></span>
