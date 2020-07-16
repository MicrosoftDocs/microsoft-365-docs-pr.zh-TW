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
description: 了解 Exchange 保留的運作方式。
ms.openlocfilehash: e1860b9ff9c521a5a6a61c58d822a2a893570e99
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127440"
---
# <a name="learn-about-retention-for-exchange"></a><span data-ttu-id="a0652-103">了解 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="a0652-103">Learn about retention for Exchange</span></span>

<span data-ttu-id="a0652-104">本文中的資訊可補充 [了解保留原則](retention.md)，因為其包含 Exchange 專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="a0652-104">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Exchange.</span></span>

## <a name="how-retention-works-for-exchange"></a><span data-ttu-id="a0652-105">Exchange 保留功能的運作方式</span><span class="sxs-lookup"><span data-stu-id="a0652-105">How retention works for Exchange</span></span>

<span data-ttu-id="a0652-106">信箱和公用資料夾都是使用 [可復原的項目][](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) 資料夾來保留項目。</span><span class="sxs-lookup"><span data-stu-id="a0652-106">Both a mailbox and a public folder use the [Recoverable Items folder](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) to retain items.</span></span> <span data-ttu-id="a0652-107">已獲指派電子文件探索權限的人員可以檢視其他使用者的 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="a0652-107">Only people who have been assigned eDiscovery permissions can view items in another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="a0652-108">當使用者從 [刪除的郵件] 資料夾以外的資料夾刪除郵件時，根據預設，會將該郵件移至 [刪除的郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a0652-108">When a person deletes a message in a folder other than the Deleted Items folder, by default, the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="a0652-109">當使用者從 [刪除的郵件] 資料夾中刪除項目時，郵件會移至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a0652-109">When a person deletes an item in the Deleted Items folder, the message is moved to the Recoverable Items folder.</span></span> <span data-ttu-id="a0652-110">不過，使用者可以將任何資料夾中的項目虛刪除 (Shift+Delete)，這會略過 [刪除的郵件] 資料夾，並將項目移至 [可復原的項目] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="a0652-110">However, a user can soft delete an item (Shift+Delete) in any folder, which bypasses the Deleted Items folder and moves the item directly to the Recoverable Items folder.</span></span>
  
<span data-ttu-id="a0652-111">將保留原則設定至 Exchange 資料時，計時器工作會定期評估 [可復原的項目] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="a0652-111">When you apply retention settings to Exchange data, a timer job periodically evaluates items in the Recoverable Items folder.</span></span> <span data-ttu-id="a0652-112">如果項目不符合至少一個保留原則或保留標籤的規則，則會永久刪除 [可復原的項目] 資料夾中的項目 (也就是「實刪除」)。</span><span class="sxs-lookup"><span data-stu-id="a0652-112">If an item doesn't match the rules of at least one retention policy or retention label, the item is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>

<span data-ttu-id="a0652-113">計時器工作最多可能需要七天才能執行，且 Exchange 位置必須包含至少 10 MB。</span><span class="sxs-lookup"><span data-stu-id="a0652-113">The timer job can take up to seven days to run and the Exchange location must contain at least 10 MB.</span></span>
  
<span data-ttu-id="a0652-114">當使用者嘗試變更信箱項目的內容時 (例如主旨、內文、附件、寄件者和收件者，或是傳送或接收郵件的日期)，在認可變更之前，會先將原始項目的複本儲存至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a0652-114">When a user attempts to change properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Recoverable Items folder before the change is committed.</span></span> <span data-ttu-id="a0652-115">後續每次變更都會執行此動作。</span><span class="sxs-lookup"><span data-stu-id="a0652-115">This action happens for each subsequent change.</span></span> <span data-ttu-id="a0652-116">在保留期間結束時，系統會永久刪除 [可復原的項目] 資料夾中的複本。</span><span class="sxs-lookup"><span data-stu-id="a0652-116">At the end of the retention period, copies in the Recoverable Items folder are permanently deleted.</span></span>

<span data-ttu-id="a0652-117">將保留設定套用至 Exchange 內容後，內容的路徑會取決於保留設定為保留和刪除、僅保留或僅刪除。</span><span class="sxs-lookup"><span data-stu-id="a0652-117">After retention settings are applied to Exchange content, the paths the content takes depend on whether the retention settings are to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="a0652-118">當保留設定為保留和刪除時：</span><span class="sxs-lookup"><span data-stu-id="a0652-118">When the retention settings are to retain and delete:</span></span>

![電子郵件和公用資料夾中的保留流程圖](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. <span data-ttu-id="a0652-120">**如果使用者在保留期間修改或永久刪除項目** (按 SHIFT+DELETE 或從 [刪除的郵件] 刪除)：系統會將項目移動 (或複製 - 在編輯的情況下) 到 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a0652-120">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period: The item is moved (or copied, in the case of edit) to the Recoverable Items folder.</span></span> <span data-ttu-id="a0652-121">計時器工作會在此處定期執行，並識別保留期間已過期的項目，而且會在保留期間結束的 14 天內永久刪除這些項目。</span><span class="sxs-lookup"><span data-stu-id="a0652-121">There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="a0652-122">請注意，14 天是預設的設定，但最多可設定為 30 天。</span><span class="sxs-lookup"><span data-stu-id="a0652-122">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span>

2. <span data-ttu-id="a0652-123">**如果未在保留期間修改或刪除項目**：系統會在信箱中的所有資料夾上定期執行相同程序，找到保留期間已過期的項目，並在保留期間結束的 14 天內永久刪除這些項目。</span><span class="sxs-lookup"><span data-stu-id="a0652-123">**If the item is not modified or deleted** during the retention period: The same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="a0652-124">請注意，14 天是預設的設定，但最多可設定為 30 天。</span><span class="sxs-lookup"><span data-stu-id="a0652-124">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span> 

<span data-ttu-id="a0652-125">當保留設定為僅保留或僅刪除時，內容路徑為保留和刪除的變化：</span><span class="sxs-lookup"><span data-stu-id="a0652-125">When the retention settings are retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-settings"></a><span data-ttu-id="a0652-126">僅保留保留設定的內容路徑</span><span class="sxs-lookup"><span data-stu-id="a0652-126">Content paths for retain-only retention settings</span></span>

1. <span data-ttu-id="a0652-127">在保留期間，**如果項目遭修改或刪除**：則會在 [可復原的項目] 資料夾中建立原始項目的複本，並保留到保留期間結束時，然後在該項目到期後 14 天內永久刪除 [可復原的項目] 資料夾中的複本。</span><span class="sxs-lookup"><span data-stu-id="a0652-127">**If the item is modified or deleted** during the retention period: A copy of the original item is created in the Recoverable Items folder and retained until the end of the retention period, when the copy in the Recoverable Items folder is permanently deleted within 14 days after the item expires.</span></span> 

2. <span data-ttu-id="a0652-128">在保留期間，**如果未修改或刪除項目**：保留期間前後沒有任何變化；項目仍會保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="a0652-128">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the item remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-settings"></a><span data-ttu-id="a0652-129">僅刪除保留設定的內容路徑</span><span class="sxs-lookup"><span data-stu-id="a0652-129">Content paths for delete-only retention settings</span></span>

1. <span data-ttu-id="a0652-130">**如果未在保留期間刪除項目**：在保留原則中設定的期間結束時，系統會將項目移至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a0652-130">**If the item is not deleted** during the configured period: At the end of the configured period in the retention policy, the item is moved to the Recoverable Items folder.</span></span> 

2. <span data-ttu-id="a0652-131">**如果在保留期間刪除項目**：系統會立即將項目移至 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a0652-131">**If the item is deleted** during the configured period: The item is immediately moved to the Recoverable Items folder.</span></span> <span data-ttu-id="a0652-132">如果使用者從該處刪除項目或清空 [可復原的項目] 資料夾，就會永久刪除項目。</span><span class="sxs-lookup"><span data-stu-id="a0652-132">If a user deletes the item from there or empties the Recoverable Items folder, the item is permanently deleted.</span></span> <span data-ttu-id="a0652-133">否則，系統會在項目在 [可復原的項目] 資料夾中保留 14 天後永久刪除。</span><span class="sxs-lookup"><span data-stu-id="a0652-133">Otherwise, the item is permanently deleted after being in the Recoverable Items folder for 14 days.</span></span> 

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="a0652-134">當使用者離開組織時</span><span class="sxs-lookup"><span data-stu-id="a0652-134">When a user leaves the organization</span></span> 

<span data-ttu-id="a0652-135">如果組織中的使用者離職，且保留原則中包含使用者的信箱，在刪除使用者的 Microsoft 365 帳戶後，信箱會變成非作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="a0652-135">If a user leaves your organization and the user's mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Microsoft 365 account is deleted.</span></span> <span data-ttu-id="a0652-136">在變成非作用的狀態之前，非作用中信箱的內容仍受限於信箱上所設之任何保留原則，且內容可供電子文件探索搜尋。</span><span class="sxs-lookup"><span data-stu-id="a0652-136">The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="a0652-137">如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a0652-137">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="a0652-138">配置指導方針</span><span class="sxs-lookup"><span data-stu-id="a0652-138">Configuration guidance</span></span>

<span data-ttu-id="a0652-139">如果您已準備好在 Microsoft 365 中設定保留，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="a0652-139">If you're ready to configure retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>
