---
title: 刪除雲端信箱保留的 [可復原的專案] 資料夾中的專案
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 瞭解系統管理員如何刪除 Exchange Online 信箱之使用者的 [可復原的專案] 資料夾中的專案，即使該信箱位於法律封存中也一樣。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 776113bcd6141c4f01c2da61f0bd71f99cffd3e2
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326639"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a><span data-ttu-id="f0476-103">刪除雲端式信箱中可復原的項目資料夾中的保留項目</span><span class="sxs-lookup"><span data-stu-id="f0476-103">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>

<span data-ttu-id="f0476-104">Exchange Online 信箱的 [可復原的專案] 資料夾存在於防止意外或惡意刪除的情況。</span><span class="sxs-lookup"><span data-stu-id="f0476-104">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="f0476-105">它也用來儲存由規範功能（例如保留和 eDiscovery 搜尋）所保留及存取的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-105">It's also used to store items that are retained and accessed by compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="f0476-106">不過，在某些情況下，組織可能會有不慎保留在必須刪除的 [可復原的專案] 資料夾中的資料。</span><span class="sxs-lookup"><span data-stu-id="f0476-106">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="f0476-107">例如，使用者可能會在不知情的情況下傳送或轉寄包含機密資訊的電子郵件，或是可能具有嚴重業務結果的資訊。</span><span class="sxs-lookup"><span data-stu-id="f0476-107">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="f0476-108">即使永久刪除郵件，該郵件仍可無限期保留，因為已對信箱進行合法保留。</span><span class="sxs-lookup"><span data-stu-id="f0476-108">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="f0476-109">此案例稱為 *資料外泄*，因為資料意外 *濺* 入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f0476-109">This scenario is known as *data spillage* because data has been unintentionally *spilled* into Office 365.</span></span> <span data-ttu-id="f0476-110">在這些情況下，您可以刪除 Exchange Online 信箱之使用者的 [可復原的專案] 資料夾中的專案，即使該信箱是以 Office 365 中的其中一個不同的保留功能來保留。</span><span class="sxs-lookup"><span data-stu-id="f0476-110">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="f0476-111">這些保留類型包括 Office 365 或 Microsoft 365 的「安全性與合規性中心」中建立的訴訟保留、In-Place 保留、eDiscovery 保留及保留原則。</span><span class="sxs-lookup"><span data-stu-id="f0476-111">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and retention policies created in the security and compliance center in Office 365 or Microsoft 365.</span></span>

<span data-ttu-id="f0476-112">本文說明系統管理員可以如何刪除保留中的雲端式信箱的 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-112">This article explains how admins can delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="f0476-113">此套裝程式含停用對信箱的存取權並停用單一專案復原，停用受管理的資料夾助理處理信箱，暫時移除保留，從 [可復原的專案] 資料夾中刪除專案，然後將信箱還原為先前的設定。</span><span class="sxs-lookup"><span data-stu-id="f0476-113">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="f0476-114">處理常式如下：</span><span class="sxs-lookup"><span data-stu-id="f0476-114">Here's the process:</span></span>
  
[<span data-ttu-id="f0476-115">步驟1：收集信箱的相關資訊</span><span class="sxs-lookup"><span data-stu-id="f0476-115">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="f0476-116">步驟2：準備信箱</span><span class="sxs-lookup"><span data-stu-id="f0476-116">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="f0476-117">步驟3：移除信箱中的所有保留</span><span class="sxs-lookup"><span data-stu-id="f0476-117">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="f0476-118">步驟4：移除信箱的延遲保留</span><span class="sxs-lookup"><span data-stu-id="f0476-118">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

<span data-ttu-id="f0476-119">[步驟5：刪除 [可復原的專案] 資料夾中的專案](#step-5-delete-items-in-the-recoverable-items-folder)</span><span class="sxs-lookup"><span data-stu-id="f0476-119">[Step 5: Delete items in the Recoverable Items folder](#step-5-delete-items-in-the-recoverable-items-folder)</span></span>

[<span data-ttu-id="f0476-120">步驟6：將信箱還原為先前的狀態</span><span class="sxs-lookup"><span data-stu-id="f0476-120">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="f0476-121">本文所述的程式會將資料永久刪除 (從 Exchange Online 信箱中清除) 。</span><span class="sxs-lookup"><span data-stu-id="f0476-121">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="f0476-122">這表示您從 [可復原的專案] 資料夾中刪除的郵件無法復原，也不會供法律查詢或其他法規遵從性之用。</span><span class="sxs-lookup"><span data-stu-id="f0476-122">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="f0476-123">如果您想要從保留的信箱刪除郵件，做為訴訟暫止的一部分、In-Place 保留、eDiscovery 保留或在安全性與規範中心建立的保留原則，請在移除保留之前，先與您的記錄管理或法律部門核實。</span><span class="sxs-lookup"><span data-stu-id="f0476-123">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or retention policy created in the security and compliance center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="f0476-124">您的組織可能具有定義信箱保留或資料外泄事件是否優先的原則。</span><span class="sxs-lookup"><span data-stu-id="f0476-124">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span>
  
## <a name="before-you-delete-items"></a><span data-ttu-id="f0476-125">刪除專案之前</span><span class="sxs-lookup"><span data-stu-id="f0476-125">Before you delete items</span></span>

- <span data-ttu-id="f0476-126">若要建立和執行內容搜尋，您必須是「eDiscovery 管理員」角色群組的成員，或者獲指派「符合性搜尋」管理角色。</span><span class="sxs-lookup"><span data-stu-id="f0476-126">To create and run a Content Search, you have to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role.</span></span> <span data-ttu-id="f0476-127">若要刪除郵件，您必須是「組織管理」角色群組的成員，或者獲指派「搜尋及清除」管理角色。</span><span class="sxs-lookup"><span data-stu-id="f0476-127">To delete messages, you have to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="f0476-128">如需新增使用者至角色群組的詳細資訊，請參閱[在安全性與合規性中心指派電子文件探索權限](./assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f0476-128">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](./assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="f0476-129">非使用中的信箱不支援本文所述的程式。</span><span class="sxs-lookup"><span data-stu-id="f0476-129">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="f0476-130">這是因為您無法將保留原則 (或保留原則) 重新套用至非作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-130">That's because you can't reapply a hold (or retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="f0476-131">當您從非使用中的信箱移除保留時，它會變更為一般虛刪除信箱，且會在受管理的資料夾助理處理之後，從組織中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="f0476-131">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>

- <span data-ttu-id="f0476-132">您無法針對已被指派保留設定的信箱，針對使用保留鎖定的原則來執行此程式。</span><span class="sxs-lookup"><span data-stu-id="f0476-132">You can't perform this procedure for a mailbox that has been assigned retention settings with a policy that's locked by using Preservation Lock.</span></span> <span data-ttu-id="f0476-133">這是因為這個鎖定可防止您從原則移除或排除信箱，以及停用信箱上的受管理的資料夾助理。</span><span class="sxs-lookup"><span data-stu-id="f0476-133">That's because this lock prevents you from removing or excluding the mailbox from the policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="f0476-134">如需鎖定原則以進行保留的詳細資訊，請參閱 [使用保留鎖定來限制保留原則和保留標籤原則的變更](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="f0476-134">For more information about locking policies for retention,see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

- <span data-ttu-id="f0476-135">如果信箱未處於保留狀態 (或未啟用單一專案復原) ，您可以從 [可復原的專案] 資料夾中刪除專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-135">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="f0476-136">如需如何執行此動作的詳細資訊，請參閱 [搜尋並刪除組織中的電子郵件訊息](./search-for-and-delete-messages-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="f0476-136">For more information about how to do this, see [Search for and delete email messages in your organization](./search-for-and-delete-messages-in-your-organization.md).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="f0476-137">步驟1：收集信箱的相關資訊</span><span class="sxs-lookup"><span data-stu-id="f0476-137">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="f0476-138">此第一步是從目標信箱收集會影響此程式的選取屬性。</span><span class="sxs-lookup"><span data-stu-id="f0476-138">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="f0476-139">請務必記下這些設定或將其儲存至文字檔，因為您會在從 [可復原的專案] 資料夾中刪除專案之後，變更部分的屬性，然後再回復為步驟6中的原始值。</span><span class="sxs-lookup"><span data-stu-id="f0476-139">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="f0476-140">以下是您需要收集的信箱屬性清單。</span><span class="sxs-lookup"><span data-stu-id="f0476-140">Here's a list of the mailbox properties you need to collect.</span></span>
  
- <span data-ttu-id="f0476-141">*SingleItemRecoveryEnabled*  和  *RetainDeletedItemsFor*。</span><span class="sxs-lookup"><span data-stu-id="f0476-141">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*.</span></span> <span data-ttu-id="f0476-142">如有必要，您會停用單一復原，並增加步驟3中已刪除的郵件保留期間。</span><span class="sxs-lookup"><span data-stu-id="f0476-142">If necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span>

- <span data-ttu-id="f0476-143">*LitigationHoldEnabled*  和  *InPlaceHolds*。</span><span class="sxs-lookup"><span data-stu-id="f0476-143">*LitigationHoldEnabled*  and  *InPlaceHolds*.</span></span> <span data-ttu-id="f0476-144">您必須識別放在信箱上的所有保留，以便您可以在步驟3中暫時移除。</span><span class="sxs-lookup"><span data-stu-id="f0476-144">You need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="f0476-145">請參閱 [詳細資訊](#more-information) 一節，以取得如何識別可能放置在信箱上之類型保留的秘訣。</span><span class="sxs-lookup"><span data-stu-id="f0476-145">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span>

<span data-ttu-id="f0476-146">此外，您還需要取得信箱用戶端存取設定，這樣您就可以暫時停用這些設定，讓擁有者 (或其他使用者) 無法在此程式中存取信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-146">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="f0476-147">最後，您可以取得 [可復原的專案] 資料夾中的目前大小及專案數目。</span><span class="sxs-lookup"><span data-stu-id="f0476-147">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="f0476-148">在步驟5中刪除 [可復原的專案] 資料夾中的專案之後，您將使用此資訊來確認專案已移除。</span><span class="sxs-lookup"><span data-stu-id="f0476-148">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were removed.</span></span>
  
1. <span data-ttu-id="f0476-149">[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f0476-149">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f0476-150">請務必使用使用者名稱和密碼給已獲指派適當管理角色 Exchange Online 中的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="f0476-150">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span>

2. <span data-ttu-id="f0476-151">執行下列命令，以取得有關單一專案復原和刪除專案保留期間的資訊。</span><span class="sxs-lookup"><span data-stu-id="f0476-151">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="f0476-152">如果已啟用單一專案復原，您必須在步驟2中停用此修復。</span><span class="sxs-lookup"><span data-stu-id="f0476-152">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="f0476-153">如果已刪除專案的保留期間未設定為30天 (Exchange Online) 中的最大值，則可以在步驟2中增加。</span><span class="sxs-lookup"><span data-stu-id="f0476-153">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span>

3. <span data-ttu-id="f0476-154">執行下列命令以取得信箱的信箱訪問設定。</span><span class="sxs-lookup"><span data-stu-id="f0476-154">Run the following command to get the mailbox access settings for the mailbox.</span></span>

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="f0476-155">您將會停用步驟2中的所有 access 方法。</span><span class="sxs-lookup"><span data-stu-id="f0476-155">You'll disable all of these access methods in Step 2.</span></span>

4. <span data-ttu-id="f0476-156">執行下列命令，以取得有關信箱所套用之保留和保留原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="f0476-156">Run the following command to get information about the holds and retention policies applied to the mailbox.</span></span>

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

    > [!TIP]
    > <span data-ttu-id="f0476-157">如果  *InPlaceHolds*  屬性中的值太多，而且不是所有的值都顯示出來，您可以執行此  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 命令，以個別行顯示每一個值。</span><span class="sxs-lookup"><span data-stu-id="f0476-157">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span>
  
5. <span data-ttu-id="f0476-158">執行下列命令，以取得任何整個組織保留原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="f0476-158">Run the following command to get information about any organization-wide retention policies.</span></span> 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   <span data-ttu-id="f0476-159">如果您的組織有任何組織範圍的保留原則，您必須在步驟3中從這些原則中排除信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-159">If your organization has any organization-wide retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span> <span data-ttu-id="f0476-160">最多可能需要24小時才能複製變更。</span><span class="sxs-lookup"><span data-stu-id="f0476-160">It may take up to 24 hours to replicate the change.</span></span>

    > [!TIP]
    > <span data-ttu-id="f0476-161">如果  *InPlaceHolds*  屬性中的值太多，而且不是所有的值都顯示出來，您可以執行此  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 命令，以個別行顯示每一個值。</span><span class="sxs-lookup"><span data-stu-id="f0476-161">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="f0476-162">執行下列命令，以判斷是否已將延遲保留套用至信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-162">Run the following command to determine if a delay hold is applied to the mailbox.</span></span>

   ```powershell
   Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
   ```

   <span data-ttu-id="f0476-163">如果 *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 屬性的值設為 **True**，延遲保留會套用至信箱，且必須加以移除。</span><span class="sxs-lookup"><span data-stu-id="f0476-163">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True**, a delay hold is applied to the mailbox and must be removed.</span></span> <span data-ttu-id="f0476-164">如需延遲保留的詳細資訊，請參閱「 [步驟4：移除信箱的延遲保留](#step-4-remove-the-delay-hold-from-the-mailbox)」。</span><span class="sxs-lookup"><span data-stu-id="f0476-164">For more information about delay holds, see [Step 4: Remove the delay hold from the mailbox](#step-4-remove-the-delay-hold-from-the-mailbox).</span></span>

   <span data-ttu-id="f0476-165">如果其中一個屬性的值設定為 **False**，延遲保留不會套用至信箱，您可以略過步驟4。</span><span class="sxs-lookup"><span data-stu-id="f0476-165">If the value of either properties is set to **False**, a delay hold is not applied to the mailbox, and you can skip Step 4.</span></span>

7. <span data-ttu-id="f0476-166">執行下列命令，以取得使用者主要信箱中 [可復原的專案] 資料夾中的資料夾及子資料夾中目前的專案大小及總專案數目。</span><span class="sxs-lookup"><span data-stu-id="f0476-166">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span>

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="f0476-167">如果已啟用使用者的封存信箱，請執行下列命令，以取得封存信箱中 [可復原的專案] 資料夾中的資料夾與子資料夾中的專案大小和總數。</span><span class="sxs-lookup"><span data-stu-id="f0476-167">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="f0476-168">當您在步驟5中刪除專案時，您可以選擇刪除或不刪除使用者主要封存信箱中 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-168">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="f0476-169">如果為信箱啟用自動擴充封存，則不會刪除輔助封存信箱中的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-169">If auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="f0476-170">步驟2：準備信箱</span><span class="sxs-lookup"><span data-stu-id="f0476-170">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="f0476-171">收集和儲存信箱的相關資訊之後，下一步是執行下列工作來準備信箱：</span><span class="sxs-lookup"><span data-stu-id="f0476-171">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span>
  
- <span data-ttu-id="f0476-172">**停用用戶端對信箱的存取權** ，讓信箱擁有者無法存取其信箱，並在此程式期間對信箱資料進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="f0476-172">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span>

- <span data-ttu-id="f0476-173">將 **刪除的專案保留期間增加** 至30天 (Exchange Online) 中的最大值，這樣就不會從 [可復原的專案] 資料夾中清除專案，就能在步驟5中刪除這些專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-173">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span>

- <span data-ttu-id="f0476-174">**停用單一專案** 復原，以在刪除專案的保留期間) 從步驟5的 [可復原的專案] 資料夾中刪除之後，就不會保留這些專案 (。</span><span class="sxs-lookup"><span data-stu-id="f0476-174">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span>

- <span data-ttu-id="f0476-175">**停用受管理的資料夾助理** ，使其不處理信箱，並保留您在步驟5中刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-175">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span>

<span data-ttu-id="f0476-176">在 Exchange Online PowerShell 中執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="f0476-176">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="f0476-177">執行下列命令，以停用所有用戶端存取信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-177">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="f0476-178">命令語法假設所有的用戶端存取方法已在信箱上啟用。</span><span class="sxs-lookup"><span data-stu-id="f0476-178">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

    > [!NOTE]
    > <span data-ttu-id="f0476-179">可能需要長達60分鐘的時間，才能停用所有用戶端存取方法至信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-179">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="f0476-180">請注意，如果停用這些存取方法，則不會中斷信箱擁有者的連線。</span><span class="sxs-lookup"><span data-stu-id="f0476-180">Note that disabling these access methods won't disconnect the mailbox owner if they are currently signed in.</span></span> <span data-ttu-id="f0476-181">如果擁有者未登入，當這些存取方法停用之後，他們將無法存取其信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-181">If the owner isn't signed in, they won't be able to access their mailbox after these access methods are disabled.</span></span>
  
2. <span data-ttu-id="f0476-182">執行下列命令，以將刪除的專案保留期間增加30天的上限。</span><span class="sxs-lookup"><span data-stu-id="f0476-182">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="f0476-183">這會假設目前的設定小於30天。</span><span class="sxs-lookup"><span data-stu-id="f0476-183">This assumes that the current setting is less than 30 days.</span></span>

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="f0476-184">執行下列命令以停用單一專案復原。</span><span class="sxs-lookup"><span data-stu-id="f0476-184">Run the following command to disable single item recovery.</span></span>

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

    > [!NOTE]
    > <span data-ttu-id="f0476-185">最多可能需要60分鐘，以停用單一專案復原。</span><span class="sxs-lookup"><span data-stu-id="f0476-185">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="f0476-186">在此期間過後，請勿刪除 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-186">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="f0476-187">執行下列命令，以防止受管理的資料夾助理處理信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-187">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="f0476-188">如先前所述，只有具有保留鎖定原則的保留原則未套用至信箱時，您才可以停用受管理的資料夾助理。</span><span class="sxs-lookup"><span data-stu-id="f0476-188">As previously explained, you can disable the Managed Folder Assistant only if a retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="f0476-189">步驟3：移除信箱中的所有保留</span><span class="sxs-lookup"><span data-stu-id="f0476-189">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="f0476-190">您可以從 [可復原的專案] 資料夾中刪除專案的最後一個步驟，就是移除您在信箱上的步驟 1) 中所識別的所有保留 (。</span><span class="sxs-lookup"><span data-stu-id="f0476-190">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="f0476-191">所有保留都必須移除，這樣在您從 [可復原的專案] 資料夾中刪除之後，就不會保留專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-191">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="f0476-192">下列各節包含在信箱上移除不同類型保留的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f0476-192">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="f0476-193">請參閱 [詳細資訊](#more-information) 一節，以取得如何識別可能放置在信箱上之類型保留的秘訣。</span><span class="sxs-lookup"><span data-stu-id="f0476-193">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="f0476-194">如需詳細資訊，請參閱 how [to 識別位於 Exchange Online 信箱上的保留類型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f0476-194">For more information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f0476-195">如先前所述，在從信箱移除保留之前，請先與您的記錄管理或法律部門聯繫。</span><span class="sxs-lookup"><span data-stu-id="f0476-195">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
### <a name="litigation-hold"></a><span data-ttu-id="f0476-196">訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="f0476-196">Litigation Hold</span></span>
  
<span data-ttu-id="f0476-197">在 Exchange Online PowerShell 中執行下列命令，以從信箱中移除訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="f0476-197">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> <span data-ttu-id="f0476-198">類似于停用用戶端存取方法和單一專案復原，可能需要長達60分鐘的時間來移除訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="f0476-198">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="f0476-199">在此期間過後，請勿刪除 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-199">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
### <a name="in-place-hold"></a><span data-ttu-id="f0476-200">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="f0476-200">In-Place Hold</span></span>
  
<span data-ttu-id="f0476-201">在 Exchange Online PowerShell 中執行下列命令，以識別放在信箱上的 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="f0476-201">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="f0476-202">使用您在步驟1中識別的 In-Place 保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="f0476-202">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span>

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

<span data-ttu-id="f0476-203">在您識別 In-Place 保留後，您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online PowerShell，從保留中移除信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-203">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="f0476-204">如需詳細資訊，請參閱 [建立或移除 In-Place 保留](/exchange/security-and-compliance/create-or-remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="f0476-204">For more information, see [Create or remove an In-Place Hold](/exchange/security-and-compliance/create-or-remove-in-place-holds).</span></span>
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="f0476-205">套用至特定信箱的保留原則</span><span class="sxs-lookup"><span data-stu-id="f0476-205">Retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="f0476-206">在 [安全性 & 規範中心 PowerShell](/powershell/exchange/exchange-online-powershell) 中執行下列命令，以識別套用至信箱的保留原則。</span><span class="sxs-lookup"><span data-stu-id="f0476-206">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) to identify the retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="f0476-207">此命令也會傳回套用至信箱的任何 Teams 交談保留原則。</span><span class="sxs-lookup"><span data-stu-id="f0476-207">This command will also return any Teams conversation retention policies applied to a mailbox.</span></span> <span data-ttu-id="f0476-208">`mbx` `skp` 針對您在步驟1中識別的保留原則，使用 GUID (不包括或首碼) 。</span><span class="sxs-lookup"><span data-stu-id="f0476-208">Use the GUID (not including the `mbx` or `skp` prefix) for the retention policy that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="f0476-209">在您識別保留原則之後，請移至 [安全性 & 規範中心] 中的 [**資訊管理**  >  **保留**] 頁面，編輯您在上一個步驟中識別的保留原則，然後從保留原則中所包含的收件者清單中移除信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-209">After you identify the retention policy, go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span>
  
### <a name="organization-wide-retention-policies"></a><span data-ttu-id="f0476-210">全組織保留原則</span><span class="sxs-lookup"><span data-stu-id="f0476-210">Organization-wide retention policies</span></span>
  
<span data-ttu-id="f0476-211">整個 Teams Exchange 組織中的整體保留原則會套用至組織中的每個信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-211">Organization-wide, Exchange-wide, and Teams-wide retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="f0476-212">它們會套用至組織層級 (不會在信箱層級) ，而且會在您于步驟1中執行 **Get-OrganizationConfig** 指令時傳回。</span><span class="sxs-lookup"><span data-stu-id="f0476-212">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="f0476-213">在 [安全性 & 規範中心 PowerShell](/powershell/exchange/exchange-online-powershell) 中執行下列命令，以找出整個組織的保留原則。</span><span class="sxs-lookup"><span data-stu-id="f0476-213">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) to identify the organization-wide retention policies.</span></span> <span data-ttu-id="f0476-214">使用 GUID (不要包含  `mbx` 您在步驟1中所識別之整個組織保留原則的首碼) 。</span><span class="sxs-lookup"><span data-stu-id="f0476-214">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="f0476-215">在您識別整個組織的保留原則之後，請移至安全性 & 規範中心內的「**資訊管理**」  >  **保留** 頁面，編輯您在上一個步驟中識別的每個整個組織保留原則，並將信箱新增至排除的收件者清單。</span><span class="sxs-lookup"><span data-stu-id="f0476-215">After you identify the organization-wide retention policies, go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="f0476-216">這樣做會將使用者的信箱從保留原則中移除。</span><span class="sxs-lookup"><span data-stu-id="f0476-216">Doing this will remove the user's mailbox from the retention policy.</span></span> <span data-ttu-id="f0476-217">最多可能需要24小時才能複製變更。</span><span class="sxs-lookup"><span data-stu-id="f0476-217">It may take up to 24 hours to replicate the change.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="f0476-218">保留標籤</span><span class="sxs-lookup"><span data-stu-id="f0476-218">Retention labels</span></span>

<span data-ttu-id="f0476-219">每當使用者套用設定為保留內容或保留的標籤，然後將內容刪除至其信箱中的任何資料夾或專案時， *ComplianceTagHoldApplied* 信箱屬性都會設為 **True**。</span><span class="sxs-lookup"><span data-stu-id="f0476-219">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="f0476-220">發生這種情況時，信箱會被視為保留，就像是設定為訴訟暫止或指派給保留原則一樣。</span><span class="sxs-lookup"><span data-stu-id="f0476-220">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to a retention policy.</span></span>

<span data-ttu-id="f0476-221">若要查看 *ComplianceTagHoldApplied* 屬性的值，請在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f0476-221">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="f0476-222">在您識別信箱已保留狀態，因為保留標籤套用到資料夾或專案，您可以使用安全性與合規性中心的內容搜尋工具，利用 New-compliancetag 搜尋條件來搜尋已標示的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-222">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the security and compliance center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="f0476-223">如需詳細資訊，請參閱 [內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)中的「搜尋條件」一節。</span><span class="sxs-lookup"><span data-stu-id="f0476-223">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="f0476-224">如需標籤的詳細資訊，請參閱 [瞭解保留原則和保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="f0476-224">For more information about labels, see [Learn about retention policies and retention labels](retention.md).</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="f0476-225">電子文件探索保留</span><span class="sxs-lookup"><span data-stu-id="f0476-225">eDiscovery holds</span></span>
  
<span data-ttu-id="f0476-226">在 [安全性 & 規範中心」 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中執行下列命令，以找出與電子檔探索 (案例（稱為 *Ediscovery 保留*) （已套用至信箱）相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="f0476-226">Run the following commands in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to identify the hold associated with an eDiscovery case (called *eDiscovery holds*) that's applied to the mailbox.</span></span> <span data-ttu-id="f0476-227">使用 GUID (不要包含  `UniH` 您在步驟1中識別的 eDiscovery 暫止) 首碼。</span><span class="sxs-lookup"><span data-stu-id="f0476-227">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="f0476-228">第二個命令會顯示保留所關聯的 eDiscovery 案例名稱;第三個命令會顯示保留的名稱。</span><span class="sxs-lookup"><span data-stu-id="f0476-228">The second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span>
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

<span data-ttu-id="f0476-229">在您識別 eDiscovery 案例名稱和保留後，請移至規範中心的 [ **ediscovery** \> **ediscovery** ] 頁面，開啟案例，然後從保留中移除信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-229">After you've identified the name of the eDiscovery case and the hold, go to the **eDiscovery** \> **eDiscovery** page in the compliance center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="f0476-230">如需識別 eDiscovery 保留的詳細資訊，請參閱[如何識別位於 Exchange Online 信箱上之保留類型](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)的「eDiscovery 保留」一節。</span><span class="sxs-lookup"><span data-stu-id="f0476-230">For more information about identifying eDiscovery holds, see the "eDiscovery holds" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="f0476-231">步驟4：移除信箱的延遲保留</span><span class="sxs-lookup"><span data-stu-id="f0476-231">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="f0476-232">從信箱移除任何類型的保留後， *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 信箱屬性的值會設為 **True**。</span><span class="sxs-lookup"><span data-stu-id="f0476-232">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="f0476-233">這會在下一次受管理的資料夾助理處理信箱，並偵測已移除保留。</span><span class="sxs-lookup"><span data-stu-id="f0476-233">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="f0476-234">這稱為 *延遲保留* ，表示實際移除保留延遲30天，以防止資料從信箱中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="f0476-234">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="f0476-235"> (延遲保留的目的是讓系統管理員能夠搜尋或復原在移除保留後將會清除的信箱專案。 ) 當信箱上的延遲保留時，信箱仍會被視為無限期的保留狀態，就像信箱處於訴訟暫止狀態一樣。</span><span class="sxs-lookup"><span data-stu-id="f0476-235">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="f0476-236">30天后，延遲保留會到期，而且 Microsoft 365 會嘗試將 *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 屬性設定為 **False**) ，以移除延遲保留 (，以移除 [保留]。</span><span class="sxs-lookup"><span data-stu-id="f0476-236">After 30 days, the delay hold expires, and Microsoft 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* or *DelayReleaseHoldApplied* property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="f0476-237">如需有關延遲保留的詳細資訊，請參閱[如何識別位於 Exchange Online 信箱上之保留類型](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)的「管理延遲暫止的信箱」一節。</span><span class="sxs-lookup"><span data-stu-id="f0476-237">For more information about a delay hold, see the "Managing mailboxes on delay hold" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

<span data-ttu-id="f0476-238">如果 *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 屬性的值設為 **True**，請執行下列其中一個命令，以移除延遲保留：</span><span class="sxs-lookup"><span data-stu-id="f0476-238">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True**, run one of the following commands to remove the delay hold:</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="f0476-239">或者</span><span class="sxs-lookup"><span data-stu-id="f0476-239">Or</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="f0476-240">您必須在 Exchange Online 中指派合法保留角色，才能使用 *RemoveDelayHoldApplied* 或 *RemoveDelayReleaseHoldApplied* 參數。</span><span class="sxs-lookup"><span data-stu-id="f0476-240">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="f0476-241">步驟5：刪除 [可復原的專案] 資料夾中的專案</span><span class="sxs-lookup"><span data-stu-id="f0476-241">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="f0476-242">現在，您已準備好使用 [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) 的 [可復原的專案] 資料夾中的專案，並在安全性 & 規範中心 PowerShell [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) Cmdlet 來刪除專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-242">Now you're ready to actually delete items in the Recoverable Items folder by using the [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) and [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) cmdlets in Security & Compliance Center PowerShell.</span></span>

<span data-ttu-id="f0476-243">若要搜尋位於 [可復原的專案] 資料夾中的專案，建議您執行 *目標集合*。</span><span class="sxs-lookup"><span data-stu-id="f0476-243">To search for items that are located in the Recoverable Items folder, we recommend that you perform a *targeted collection*.</span></span> <span data-ttu-id="f0476-244">這表示您將搜尋範圍縮小至 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-244">This means you narrow the scope of your search only to items located in the Recoverable Items folder.</span></span> <span data-ttu-id="f0476-245">若要執行此動作，您可以在 [ [使用目標集合的內容搜尋](use-content-search-for-targeted-collections.md) ] 文章中執行腳本。</span><span class="sxs-lookup"><span data-stu-id="f0476-245">You can do this by running the script in the [Use Content Search for targeted collections](use-content-search-for-targeted-collections.md) article.</span></span> <span data-ttu-id="f0476-246">此腳本會傳回目標 [可復原的專案] 資料夾中所有子資料夾的資料夾識別碼屬性值。</span><span class="sxs-lookup"><span data-stu-id="f0476-246">This script returns the value of the folder ID property for all the subfolders in the target Recoverable Items folder.</span></span> <span data-ttu-id="f0476-247">然後，您可以使用搜尋查詢中的資料夾識別碼，傳回位於該資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-247">Then you use the folder ID in a search query to return items located in that folder.</span></span>

<span data-ttu-id="f0476-248">以下是在使用者的 [可復原的專案] 資料夾中搜尋及刪除專案的程式：</span><span class="sxs-lookup"><span data-stu-id="f0476-248">Here's an overview of the process to search for and delete items in a user's Recoverable Items folder:</span></span>

1. <span data-ttu-id="f0476-249">執行目標集合腳本，傳回目標使用者信箱中所有資料夾的資料夾 IDs。</span><span class="sxs-lookup"><span data-stu-id="f0476-249">Run the targeted collection script that returns the folder IDs for all folders in the target user's mailbox.</span></span> <span data-ttu-id="f0476-250">腳本會連接至相同 PowerShell 會話中 Exchange Online PowerShell 與安全性 & 合規性 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f0476-250">The script connects to Exchange Online PowerShell and Security & Compliance PowerShell in the same PowerShell session.</span></span> <span data-ttu-id="f0476-251">如需詳細資訊，請參閱 [執行腳本以取得信箱的資料夾清單](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)。</span><span class="sxs-lookup"><span data-stu-id="f0476-251">For more information, see [Run the script to get a list of folders for a mailbox](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site).</span></span>

2. <span data-ttu-id="f0476-252">在 [可復原的專案] 資料夾中，複製所有子資料夾的資料夾 IDs。</span><span class="sxs-lookup"><span data-stu-id="f0476-252">Copy the folder IDs for all subfolders in the Recoverable Items folder.</span></span> <span data-ttu-id="f0476-253">或者，您也可以將腳本的輸出重新導向至文字檔。</span><span class="sxs-lookup"><span data-stu-id="f0476-253">Alternatively, you can redirect the output of the script to a text file.</span></span>

   <span data-ttu-id="f0476-254">以下是可復原的 [可復原的專案] 資料夾中的子資料夾清單和描述，您可以從中搜尋和刪除專案：</span><span class="sxs-lookup"><span data-stu-id="f0476-254">Here's a list and description of the subfolders in the Recoverable Items folder that you can search and delete items from:</span></span>

   - <span data-ttu-id="f0476-255">**刪除**：包含刪除專案保留期間尚未過期的虛刪除專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-255">**Deletions**: Contains soft-deleted items whose deleted item retention period has not expired.</span></span> <span data-ttu-id="f0476-256">使用者可以使用 Outlook 中的 [復原刪除的郵件] 工具，從這個子資料夾中復原虛刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-256">Users can recover soft-deleted items from this subfolder using the Recover Deleted Items tool in Outlook.</span></span>

   - <span data-ttu-id="f0476-257">**清除**：包含已刪除專案保留期間已過期的實刪除專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-257">**Purges**: Contains hard-deleted items whose deleted item retention period has expired.</span></span> <span data-ttu-id="f0476-258">使用者也可以從 [可復原的專案] 資料夾中清除專案，以實刪除專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-258">Users can also hard-delete items by purging items from their Recoverable Items folder.</span></span> <span data-ttu-id="f0476-259">如果信箱處於保留狀態，則會保留實刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-259">If the mailbox is on hold, hard-deleted items are preserved.</span></span> <span data-ttu-id="f0476-260">使用者看不到這個子資料夾。</span><span class="sxs-lookup"><span data-stu-id="f0476-260">This subfolder isn't visible to end users.</span></span>

   - <span data-ttu-id="f0476-261">**DiscoveryHolds**：包含已由 eDiscovery 保留或保留原則所保留的實刪除專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-261">**DiscoveryHolds**: Contains hard-deleted items that have been preserved by an eDiscovery hold or a retention policy.</span></span> <span data-ttu-id="f0476-262">使用者看不到這個子資料夾。</span><span class="sxs-lookup"><span data-stu-id="f0476-262">This subfolder isn't visible to end users.</span></span>

   - <span data-ttu-id="f0476-263">**SubstrateHolds**：包含已由保留原則或其他類型保留所保留的 Teams 和其他雲端型應用程式中的實刪除專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-263">**SubstrateHolds**: Contains hard-deleted items from Teams and other cloud-based apps that have been preserved by a retention policy or other type of hold.</span></span> <span data-ttu-id="f0476-264">使用者看不到這個子資料夾。</span><span class="sxs-lookup"><span data-stu-id="f0476-264">This subfolder isn't visible to end users.</span></span>

3. <span data-ttu-id="f0476-265">使用 **New-ComplianceSearch** Cmdlet (在安全性 & 規範中心 PowerShell) 或使用規範中心的內容搜尋工具，建立從目標使用者的 [可復原的專案] 資料夾中傳回專案的內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="f0476-265">Use the **New-ComplianceSearch** cmdlet (in Security & Compliance Center PowerShell) or use the Content search tool in the compliance center to create a content search that returns items from the target user's Recoverable Items folder.</span></span> <span data-ttu-id="f0476-266">若要執行此動作，您可以在要搜尋的所有子資料夾中，加入搜尋查詢中的 FolderId。</span><span class="sxs-lookup"><span data-stu-id="f0476-266">You can do this by including the FolderId in the search query for all subfolders that you want to search.</span></span> <span data-ttu-id="f0476-267">例如，下列查詢會傳回清除和 eDiscoveryHolds 子資料夾中的所有郵件：</span><span class="sxs-lookup"><span data-stu-id="f0476-267">For example, the following query returns all messages in the Purges and eDiscoveryHolds subfolders:</span></span>

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   <span data-ttu-id="f0476-268">如需執行使用 [資料夾識別碼] 屬性的內容搜尋的詳細資訊和範例，請參閱 [使用資料夾識別碼或執行目標集合](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)。</span><span class="sxs-lookup"><span data-stu-id="f0476-268">For more information and examples about running content searches that use the folder ID property, see [Use a folder ID or to perform a targeted collection](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection).</span></span>

   > [!NOTE]
   > <span data-ttu-id="f0476-269">如果您使用 **New-ComplianceSearch** Cmdlet 來搜尋 [可復原的專案] 資料夾，請務必使用 **Start-ComplianceSearch** Cmdlet 執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="f0476-269">If you use the **New-ComplianceSearch** cmdlet to search the Recoverable Items folder, be sure to use **Start-ComplianceSearch** cmdlet to run the search.</span></span>

4. <span data-ttu-id="f0476-270">在您建立內容搜尋並驗證它會傳回您要刪除的專案時，請使用 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` 安全性 & 相容性中心 PowerShell) 中的命令 (，永久刪除您在上一個步驟中建立的內容搜尋所傳回的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-270">After you've created a content search and validated that it returns the items that you wan to delete, use the `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command (in Security & Compliance Center PowerShell) to permanently delete the items returned by the content search that you created in the previous step.</span></span> <span data-ttu-id="f0476-271">例如，您可以執行類似下列命令的命令：</span><span class="sxs-lookup"><span data-stu-id="f0476-271">For example, you can run a command similar to the following command:</span></span>

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. <span data-ttu-id="f0476-272">當您執行上述命令時，每個信箱最多可刪除10個專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-272">A maximum of 10 items per mailbox are deleted when you run the previous command.</span></span> <span data-ttu-id="f0476-273">這表示，您可能需要多次執行 `New-ComplianceSearchAction -Purge` 命令，以刪除 [可復原的專案] 資料夾中的所有要刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-273">That means you may have to run the `New-ComplianceSearchAction -Purge` command multiple times to delete all the items that you want to delete in the Recoverable Items folder.</span></span> <span data-ttu-id="f0476-274">若要刪除其他專案，您必須先移除先前的符合性搜尋清除動作。</span><span class="sxs-lookup"><span data-stu-id="f0476-274">To delete additional items, you first have to remove the previous compliance search purge action.</span></span> <span data-ttu-id="f0476-275">您可以執行 Cmdlet 來執行此動作 `Remove-ComplianceSearchAction` 。</span><span class="sxs-lookup"><span data-stu-id="f0476-275">You do this by running the `Remove-ComplianceSearchAction` cmdlet.</span></span> <span data-ttu-id="f0476-276">例如，若要刪除上一個步驟中所執行的清除動作，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f0476-276">For example, to delete the purge action that was run in the previous step, run the following command:</span></span>

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   <span data-ttu-id="f0476-277">完成之後，您可以建立新的符合性搜尋清除動作，以刪除更多專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-277">After you do this, you can create a new compliance search purge action to delete more items.</span></span> <span data-ttu-id="f0476-278">在建立新的清除動作之前，必須先將其刪除。</span><span class="sxs-lookup"><span data-stu-id="f0476-278">You'll have to delete each purge action before creating a new one.</span></span>

   <span data-ttu-id="f0476-279">若要取得符合性搜尋動作的清單，您可以執行 `Get-ComplianceSearchAction` Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f0476-279">To get a list of the compliance search actions, you can run the `Get-ComplianceSearchAction` cmdlet.</span></span> <span data-ttu-id="f0476-280">清除動作會 `_Purge` 以附加至搜尋名稱來識別。</span><span class="sxs-lookup"><span data-stu-id="f0476-280">Purge actions are identified by `_Purge` appended to the search name.</span></span>

### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="f0476-281">確認已刪除專案</span><span class="sxs-lookup"><span data-stu-id="f0476-281">Verify that items were deleted</span></span>

<span data-ttu-id="f0476-282">若要確認您是否已成功刪除信箱的 [可復原的專案] 資料夾中的專案，請使用 Exchange Online PowerShell 中的 **Get-MailboxFolderStatistics** Cmdlet，檢查 [可復原的專案] 資料夾中的專案大小和數目。</span><span class="sxs-lookup"><span data-stu-id="f0476-282">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="f0476-283">您可以將這些統計資料與您在步驟1中收集的統計資料進行比較。</span><span class="sxs-lookup"><span data-stu-id="f0476-283">You can compare these statistics with the ones you collected in Step 1.</span></span>
  
<span data-ttu-id="f0476-284">在中執行下列命令，以取得使用者主要信箱中 [可復原的專案] 資料夾中的資料夾與子資料夾中目前的專案大小及總專案數目。</span><span class="sxs-lookup"><span data-stu-id="f0476-284">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span>
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

<span data-ttu-id="f0476-285">執行下列命令，以取得使用者封存信箱中 [可復原的專案] 資料夾中的資料夾及子資料夾中的專案大小和總數。</span><span class="sxs-lookup"><span data-stu-id="f0476-285">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span>

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="f0476-286">步驟6：將信箱還原為先前的狀態</span><span class="sxs-lookup"><span data-stu-id="f0476-286">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="f0476-287">最後一個步驟是將信箱還原回先前的設定。</span><span class="sxs-lookup"><span data-stu-id="f0476-287">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="f0476-288">這表示重設您在步驟2中變更的屬性，並重新應用您在步驟3中移除的保留。</span><span class="sxs-lookup"><span data-stu-id="f0476-288">This means resetting the properties that you changed in Step 2 and reapplying the holds that you removed in Step 3.</span></span> <span data-ttu-id="f0476-289">這包括：</span><span class="sxs-lookup"><span data-stu-id="f0476-289">This includes:</span></span>
  
- <span data-ttu-id="f0476-290">將刪除的專案保留期間變更回其先前的值。</span><span class="sxs-lookup"><span data-stu-id="f0476-290">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="f0476-291">或者，您可以將此集合保留為30天，Exchange Online 中的最大值。</span><span class="sxs-lookup"><span data-stu-id="f0476-291">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>

- <span data-ttu-id="f0476-292">重新啟用單一專案復原。</span><span class="sxs-lookup"><span data-stu-id="f0476-292">Re-enabling single Item recovery.</span></span>

- <span data-ttu-id="f0476-293">重新啟用用戶端存取方法，讓擁有者可以存取其信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-293">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>

- <span data-ttu-id="f0476-294">重新應用您移除的保留和保留原則。</span><span class="sxs-lookup"><span data-stu-id="f0476-294">Reapplying the holds and retention policies that you removed.</span></span>

- <span data-ttu-id="f0476-295">重新啟用受管理的資料夾助理以處理信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-295">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0476-296">建議您在重新套用保留原則或保留 (原則之後，等候24小時後再重新啟用受管理的資料夾助理以處理信箱，然後再進行) 。</span><span class="sxs-lookup"><span data-stu-id="f0476-296">We recommend that you wait 24 hours after re-applying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span>
  
<span data-ttu-id="f0476-297">請以 Exchange Online PowerShell 中的指定順序) 執行下列步驟 (。</span><span class="sxs-lookup"><span data-stu-id="f0476-297">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="f0476-298">執行下列命令，將刪除的專案保留期間變更回其原始值。</span><span class="sxs-lookup"><span data-stu-id="f0476-298">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="f0476-299">這會假設上一個設定小於30天;例如，14天。</span><span class="sxs-lookup"><span data-stu-id="f0476-299">This assumes that the previous setting is less than 30 days; for example, 14 days.</span></span>

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. <span data-ttu-id="f0476-300">執行下列命令，以重新啟用單一專案復原。</span><span class="sxs-lookup"><span data-stu-id="f0476-300">Run the following command to re-enable single item recovery.</span></span>

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="f0476-301">執行下列命令，以重新啟用所有用戶端存取方法至信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-301">Run the following command to re-enable all client access methods to the mailbox.</span></span>

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. <span data-ttu-id="f0476-302">重新套用您在步驟3中移除的保留。</span><span class="sxs-lookup"><span data-stu-id="f0476-302">Reapply the holds that you removed in Step 3.</span></span> <span data-ttu-id="f0476-303">根據保留的類型，使用下列其中一個程式。</span><span class="sxs-lookup"><span data-stu-id="f0476-303">Depending on the type of hold, use one of the following procedures.</span></span>

    <span data-ttu-id="f0476-304">**訴訟暫止**</span><span class="sxs-lookup"><span data-stu-id="f0476-304">**Litigation Hold**</span></span>

    <span data-ttu-id="f0476-305">執行下列命令，以重新啟用信箱的訴訟暫止。</span><span class="sxs-lookup"><span data-stu-id="f0476-305">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="f0476-306">**原有範圍暫止**</span><span class="sxs-lookup"><span data-stu-id="f0476-306">**In-Place Hold**</span></span>

    <span data-ttu-id="f0476-307">使用 EAC (或 Exchange Online PowerShell) ，將信箱重新新增至 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="f0476-307">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span>

    <span data-ttu-id="f0476-308">**套用至特定信箱的保留原則**</span><span class="sxs-lookup"><span data-stu-id="f0476-308">**Retention policies applied to specific mailboxes**</span></span>

    <span data-ttu-id="f0476-309">使用安全性 & 規範中心，將信箱新增回保留原則。</span><span class="sxs-lookup"><span data-stu-id="f0476-309">Use the Security & Compliance Center to add the mailbox back to the retention policy.</span></span> <span data-ttu-id="f0476-310">移至 [安全性 & 規範中心] 中的 [**資訊** 控管  >  **保留**] 頁面，編輯保留原則，並將信箱重新新增至套用保留原則的收件者清單。</span><span class="sxs-lookup"><span data-stu-id="f0476-310">Go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span>

    <span data-ttu-id="f0476-311">**全組織保留原則**</span><span class="sxs-lookup"><span data-stu-id="f0476-311">**Organization-wide Retention policies**</span></span>

    <span data-ttu-id="f0476-312">如果您移除整個組織或 Exchange 範圍的保留原則，請從原則中排除它，然後使用安全性 & 規範中心從排除的使用者清單中移除信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-312">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security & Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="f0476-313">移至 [安全性 & 規範中心] 中的 [**資訊** 控管  >  **保留**] 頁面，編輯整個組織的保留原則，然後從排除的收件者清單中移除信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-313">Go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="f0476-314">這樣做會將保留原則重新套用至使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-314">Doing this will reapply the retention policy to the user's mailbox.</span></span>

    <span data-ttu-id="f0476-315">**eDiscovery 案例保留**</span><span class="sxs-lookup"><span data-stu-id="f0476-315">**eDiscovery case holds**</span></span>

    <span data-ttu-id="f0476-316">使用安全性 & 合規性中心，將信箱回復與 eDiscovery 案例相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="f0476-316">Use the Security & Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="f0476-317">移至 [ **ediscovery**  >  **ediscovery** ] 頁面，開啟案例，然後將信箱新增回保留。</span><span class="sxs-lookup"><span data-stu-id="f0476-317">Go to the **eDiscovery** > **eDiscovery** page, open the case, and add the mailbox back to the hold.</span></span> 

5. <span data-ttu-id="f0476-318">執行下列命令，讓受管理的資料夾助理再次處理信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-318">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="f0476-319">如先前所述，建議您在重新套用保留原則或保留原則 (後等候24小時，然後在重新啟用受管理的資料夾助理之前，先確認該) 是否已到位。</span><span class="sxs-lookup"><span data-stu-id="f0476-319">As previously stated, we recommend that you wait 24 hours after reapplying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span>

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. <span data-ttu-id="f0476-320">若要驗證信箱是否已回復回先前的設定，您可以執行下列命令，並將設定與您在步驟1中收集的設定進行比較。</span><span class="sxs-lookup"><span data-stu-id="f0476-320">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a><span data-ttu-id="f0476-321">其他資訊</span><span class="sxs-lookup"><span data-stu-id="f0476-321">More information</span></span>

<span data-ttu-id="f0476-322">以下表格說明當您執行 **Get-Mailbox** 或 **Get-OrganizationConfig** Cmdlet 時，如何根據 *InPlaceHolds* 屬性中的值來識別不同的保留類型。</span><span class="sxs-lookup"><span data-stu-id="f0476-322">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="f0476-323">如需詳細資訊，請參閱 how [to 識別位於 Exchange Online 信箱上的保留類型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f0476-323">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="f0476-324">如先前所述，您必須先移除信箱的所有保留和保留原則，才能成功刪除 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f0476-324">As previously explained, you have to remove all holds and retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span>
  
| <span data-ttu-id="f0476-325">保留類型</span><span class="sxs-lookup"><span data-stu-id="f0476-325">Hold type</span></span> | <span data-ttu-id="f0476-326">範例值</span><span class="sxs-lookup"><span data-stu-id="f0476-326">Example value</span></span> | <span data-ttu-id="f0476-327">如何識別保留</span><span class="sxs-lookup"><span data-stu-id="f0476-327">How to identify the hold</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="f0476-328">訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="f0476-328">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="f0476-329">*LitigationHoldEnabled* 屬性設定為 `True` 。</span><span class="sxs-lookup"><span data-stu-id="f0476-329">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="f0476-330">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="f0476-330">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="f0476-331">*InPlaceHolds* 屬性包含放在信箱上的 In-Place 保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="f0476-331">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="f0476-332">您可以告訴這是 In-Place 保留，因為 GUID 不是以前置詞開頭。</span><span class="sxs-lookup"><span data-stu-id="f0476-332">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="f0476-333">您可以使用 `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Exchange Online PowerShell 中的命令，取得信箱上 In-Place 保留的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f0476-333">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="f0476-334">套用至特定信箱之安全性 & 規範中心內的保留原則</span><span class="sxs-lookup"><span data-stu-id="f0476-334">Retention policies in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="f0476-335">或</span><span class="sxs-lookup"><span data-stu-id="f0476-335">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="f0476-336">當您執行 **Get-Mailbox** Cmdlet 時，  *InPlaceHolds*  屬性也會包含套用至信箱的保留原則的 guid。</span><span class="sxs-lookup"><span data-stu-id="f0476-336">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of retention policies applied to the mailbox.</span></span> <span data-ttu-id="f0476-337">您可以識別保留原則，因為 GUID 會以前置詞開頭  `mbx` 。</span><span class="sxs-lookup"><span data-stu-id="f0476-337">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="f0476-338">如果保留原則的 GUID 以前置詞開頭，表示將 `skp` 保留原則套用至商務用 Skype 交談。</span><span class="sxs-lookup"><span data-stu-id="f0476-338">If the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="f0476-339">若要識別套用至信箱的保留原則，請在安全性 & 規範中心內執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f0476-339">To identity the retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="f0476-340">`mbx` `skp` 當您執行此命令時，請務必移除或首碼。</span><span class="sxs-lookup"><span data-stu-id="f0476-340">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="f0476-341">安全性 & 規範中心內的整個組織保留原則</span><span class="sxs-lookup"><span data-stu-id="f0476-341">Organization-wide retention policies in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="f0476-342">無值</span><span class="sxs-lookup"><span data-stu-id="f0476-342">No value</span></span>  <br/> <span data-ttu-id="f0476-343">或</span><span class="sxs-lookup"><span data-stu-id="f0476-343">or</span></span>  <br/>  <span data-ttu-id="f0476-344">`-mbxe9b52bf7ab3b46a286308ecb29624696` (表示信箱已從整個組織的原則中排除) </span><span class="sxs-lookup"><span data-stu-id="f0476-344">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="f0476-345">即使當您執行 **Get-Mailbox** Cmdlet 時， *InPlaceHolds* 屬性是空的，仍然有一個或多個組織範圍的保留原則會套用至信箱。</span><span class="sxs-lookup"><span data-stu-id="f0476-345">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="f0476-346">若要確認這一點，您可以 `Get-OrganizationConfig | FL InPlaceHolds` 在 Exchange Online PowerShell 中執行命令，以取得整個組織保留原則的 guid 清單。</span><span class="sxs-lookup"><span data-stu-id="f0476-346">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide retention policies.</span></span> <span data-ttu-id="f0476-347">套用至 Exchange 信箱的全組織保留原則的 GUID 會以前置詞開始 `mbx` ，例如 `mbxa3056bb15562480fadb46ce523ff7b02` 。</span><span class="sxs-lookup"><span data-stu-id="f0476-347">The GUID for organization-wide retention policies applied to Exchange mailboxes starts with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="f0476-348">若要識別套用至信箱的全組織保留原則，請在安全性 & 規範中心內執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f0476-348">To identity the organization-wide retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="f0476-349">如果信箱已從整個組織的保留原則中排除，當您執行 **Get-Mailbox** Cmdlet 時，保留原則的 GUID 會顯示在使用者信箱的 *InPlaceHolds* 屬性中;它會以前置詞識別 `-mbx` ; 例如，`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="f0476-349">If a mailbox is excluded from an organization-wide retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="f0476-350">安全性 & 規範中心的 eDiscovery 案例保留</span><span class="sxs-lookup"><span data-stu-id="f0476-350">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="f0476-351">*InPlaceHolds* 屬性也包含與可能位於信箱上安全性 & 合規性中心的 eDiscovery 案例相關聯之任何保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="f0476-351">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="f0476-352">您可以告訴這是 eDiscovery 案例保留，因為 GUID 是以前置詞開頭  `UniH` 。</span><span class="sxs-lookup"><span data-stu-id="f0476-352">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="f0476-353">您可以使用  `Get-CaseHoldPolicy` 安全性 & 規範中心 PowerShell 中的指令程式，以取得與信箱的保留相關之 eDiscovery 案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f0476-353">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="f0476-354">例如，您可以執行命令  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 以顯示信箱上的案例保留名稱。</span><span class="sxs-lookup"><span data-stu-id="f0476-354">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="f0476-355">`UniH`當您執行此命令時，請務必移除前置詞。</span><span class="sxs-lookup"><span data-stu-id="f0476-355">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="f0476-356">若要識別與信箱上的保留相關聯的 eDiscovery 案例，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f0476-356">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
