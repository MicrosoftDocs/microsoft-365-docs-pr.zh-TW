---
title: 刪除雲端信箱中的專案保留 [可復原的專案] 資料夾-系統管理說明
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
description: 針對系統管理員：刪除使用者的 [可復原的專案] 資料夾中的專案，即使該信箱位於法律封存中也是一樣。 這是一種有效的方式，可刪除意外濺入 Microsoft 365 的資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ce363d558e5ce1de600ccf34863cc6524841e78b
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352178"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="f7c62-104">刪除雲端式信箱的 [可復原的專案] 資料夾中的專案，保留系統管理員協助</span><span class="sxs-lookup"><span data-stu-id="f7c62-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="f7c62-105">Exchange Online 信箱的 [可復原的專案] 資料夾存在，可防止意外或惡意刪除。</span><span class="sxs-lookup"><span data-stu-id="f7c62-105">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="f7c62-106">它也用來儲存由規範功能（例如保留和 eDiscovery 搜尋）所保留及存取的專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-106">It's also used to store items that are retained and accessed by compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="f7c62-107">不過，在某些情況下，組織可能會有不慎保留在必須刪除的 [可復原的專案] 資料夾中的資料。</span><span class="sxs-lookup"><span data-stu-id="f7c62-107">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="f7c62-108">例如，使用者可能會在不知情的情況下傳送或轉寄包含機密資訊的電子郵件，或是可能具有嚴重業務結果的資訊。</span><span class="sxs-lookup"><span data-stu-id="f7c62-108">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="f7c62-109">即使永久刪除郵件，該郵件仍可無限期保留，因為已對信箱進行合法保留。</span><span class="sxs-lookup"><span data-stu-id="f7c62-109">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="f7c62-110">此案例稱為資料外泄，因為資料已意外濺入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f7c62-110">This scenario is known as data spillage because data has been unintentionally spilled into Office 365.</span></span> <span data-ttu-id="f7c62-111">在這些情況下，您可以針對 Exchange Online 信箱刪除使用者的 [可復原的專案] 資料夾中的專案，即使該信箱是以 Office 365 中的其中一個不同的保留功能來保留。</span><span class="sxs-lookup"><span data-stu-id="f7c62-111">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="f7c62-112">這些保留類型包括在 Office 365 或 Microsoft 365 的安全性與合規性中心建立的訴訟封存、In-Place 保留、eDiscovery 保留和保留原則。</span><span class="sxs-lookup"><span data-stu-id="f7c62-112">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and retention policies created in the security and compliance center in Office 365 or Microsoft 365.</span></span>
  
 <span data-ttu-id="f7c62-113">本文說明如何從處於保留狀態的雲端式信箱的 [可復原的專案] 資料夾中刪除專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-113">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="f7c62-114">此套裝程式含停用對信箱的存取權並停用單一專案復原，停用受管理的資料夾助理處理信箱，暫時移除保留，從 [可復原的專案] 資料夾中刪除專案，然後將信箱還原為先前的設定。</span><span class="sxs-lookup"><span data-stu-id="f7c62-114">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="f7c62-115">處理常式如下：</span><span class="sxs-lookup"><span data-stu-id="f7c62-115">Here's the process:</span></span> 
  
[<span data-ttu-id="f7c62-116">步驟1：收集信箱的相關資訊</span><span class="sxs-lookup"><span data-stu-id="f7c62-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="f7c62-117">步驟2：準備信箱</span><span class="sxs-lookup"><span data-stu-id="f7c62-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="f7c62-118">步驟3：移除信箱中的所有保留</span><span class="sxs-lookup"><span data-stu-id="f7c62-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="f7c62-119">步驟4：移除信箱的延遲保留</span><span class="sxs-lookup"><span data-stu-id="f7c62-119">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

<span data-ttu-id="f7c62-120">[步驟5：刪除 [可復原的專案] 資料夾中的專案](#step-5-delete-items-in-the-recoverable-items-folder)</span><span class="sxs-lookup"><span data-stu-id="f7c62-120">[Step 5: Delete items in the Recoverable Items folder](#step-5-delete-items-in-the-recoverable-items-folder)</span></span>

[<span data-ttu-id="f7c62-121">步驟6：將信箱還原為先前的狀態</span><span class="sxs-lookup"><span data-stu-id="f7c62-121">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="f7c62-122">本文所述的程式會導致從 Exchange Online 信箱永久刪除（清除）的資料。</span><span class="sxs-lookup"><span data-stu-id="f7c62-122">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="f7c62-123">這表示您從 [可復原的專案] 資料夾中刪除的郵件無法復原，也不會供法律查詢或其他法規遵從性之用。</span><span class="sxs-lookup"><span data-stu-id="f7c62-123">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="f7c62-124">如果您想要從保留的信箱刪除郵件，做為訴訟暫止的一部分、In-Place 保留、eDiscovery 保留或在安全性與規範中心建立的保留原則，請在移除保留之前，先與您的記錄管理或法律部門核實。</span><span class="sxs-lookup"><span data-stu-id="f7c62-124">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or retention policy created in the security and compliance center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="f7c62-125">您的組織可能具有定義信箱保留或資料外泄事件是否優先的原則。</span><span class="sxs-lookup"><span data-stu-id="f7c62-125">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="f7c62-126">開始之前</span><span class="sxs-lookup"><span data-stu-id="f7c62-126">Before you begin</span></span>

- <span data-ttu-id="f7c62-127">若要建立和執行內容搜尋，您必須是「eDiscovery 管理員」角色群組的成員，或者獲指派「符合性搜尋」管理角色。</span><span class="sxs-lookup"><span data-stu-id="f7c62-127">To create and run a Content Search, you have to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role.</span></span> <span data-ttu-id="f7c62-128">若要刪除郵件，您必須是「組織管理」角色群組的成員，或者獲指派「搜尋及清除」管理角色。</span><span class="sxs-lookup"><span data-stu-id="f7c62-128">To delete messages, you have to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="f7c62-129">如需新增使用者至角色群組的詳細資訊，請參閱[在安全性與合規性中心中指派電子文件探索權限](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)。</span><span class="sxs-lookup"><span data-stu-id="f7c62-129">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).</span></span>

- <span data-ttu-id="f7c62-130">非使用中的信箱不支援本文所述的程式。</span><span class="sxs-lookup"><span data-stu-id="f7c62-130">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="f7c62-131">這是因為在您移除停用信箱之後，您無法將保留（或保留原則）重新套用至非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-131">That's because you can't reapply a hold (or retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="f7c62-132">當您從非使用中的信箱移除保留時，它會變更為一般虛刪除信箱，且會在受管理的資料夾助理處理之後，從組織中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="f7c62-132">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>

- <span data-ttu-id="f7c62-133">您無法對指派給已以保留鎖定鎖定之保留原則的信箱執行此程式。</span><span class="sxs-lookup"><span data-stu-id="f7c62-133">You can't perform this procedure for a mailbox that has been assigned to a retention policy that's been locked with a Preservation Lock.</span></span> <span data-ttu-id="f7c62-134">這是因為保留鎖定可防止您從保留原則移除或排除信箱，以及停用信箱上的受管理的資料夾助理。</span><span class="sxs-lookup"><span data-stu-id="f7c62-134">That's because a Preservation Lock prevents you from removing or excluding the mailbox from the retention policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="f7c62-135">如需有關封鎖保留原則的詳細資訊，請參閱[使用保留鎖定以遵守法規需求](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)。</span><span class="sxs-lookup"><span data-stu-id="f7c62-135">For more information about locking retention policies,see [Use Preservation Lock to comply with regulatory requirements](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

- <span data-ttu-id="f7c62-136">如果信箱未處於保留狀態（或沒有啟用單一專案復原），您可以從 [可復原的專案] 資料夾中刪除專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-136">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="f7c62-137">如需如何執行此動作的詳細資訊，請參閱[搜尋並刪除組織中的電子郵件訊息](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="f7c62-137">For more information about how to do this, see [Search for and delete email messages in your organization](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="f7c62-138">步驟1：收集信箱的相關資訊</span><span class="sxs-lookup"><span data-stu-id="f7c62-138">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="f7c62-139">此第一步是從目標信箱收集會影響此程式的選取屬性。</span><span class="sxs-lookup"><span data-stu-id="f7c62-139">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="f7c62-140">請務必記下這些設定或將其儲存至文字檔，因為您會在從 [可復原的專案] 資料夾中刪除專案之後，變更部分的屬性，然後再回復為步驟6中的原始值。</span><span class="sxs-lookup"><span data-stu-id="f7c62-140">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="f7c62-141">以下是您需要收集的信箱屬性清單。</span><span class="sxs-lookup"><span data-stu-id="f7c62-141">Here's a list of the mailbox properties you need to collect.</span></span>
  
- <span data-ttu-id="f7c62-142">*SingleItemRecoveryEnabled*和*RetainDeletedItemsFor*。</span><span class="sxs-lookup"><span data-stu-id="f7c62-142">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*.</span></span> <span data-ttu-id="f7c62-143">如有必要，您會停用單一復原，並增加步驟3中已刪除的郵件保留期間。</span><span class="sxs-lookup"><span data-stu-id="f7c62-143">If necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 

- <span data-ttu-id="f7c62-144">*LitigationHoldEnabled*和*InPlaceHolds*。</span><span class="sxs-lookup"><span data-stu-id="f7c62-144">*LitigationHoldEnabled*  and  *InPlaceHolds*.</span></span> <span data-ttu-id="f7c62-145">您必須識別放在信箱上的所有保留，以便您可以在步驟3中暫時移除。</span><span class="sxs-lookup"><span data-stu-id="f7c62-145">You need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="f7c62-146">請參閱[詳細資訊](#more-information)一節，以取得如何識別可能放置在信箱上之類型保留的秘訣。</span><span class="sxs-lookup"><span data-stu-id="f7c62-146">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 

<span data-ttu-id="f7c62-147">此外，您還需要取得信箱用戶端存取設定，這樣您就可以暫時停用這些設定，讓擁有者（或其他使用者）在此程式中無法存取信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-147">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="f7c62-148">最後，您可以取得 [可復原的專案] 資料夾中的目前大小及專案數目。</span><span class="sxs-lookup"><span data-stu-id="f7c62-148">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="f7c62-149">在步驟5中刪除 [可復原的專案] 資料夾中的專案之後，您將使用此資訊來確認專案已移除。</span><span class="sxs-lookup"><span data-stu-id="f7c62-149">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were removed.</span></span>
  
1. <span data-ttu-id="f7c62-150">[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="f7c62-150">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="f7c62-151">請務必使用使用者名稱和密碼，以在 Exchange Online 中指派適當的管理角色的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="f7c62-151">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="f7c62-152">執行下列命令，以取得有關單一專案復原和刪除專案保留期間的資訊。</span><span class="sxs-lookup"><span data-stu-id="f7c62-152">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="f7c62-153">如果已啟用單一專案復原，您必須在步驟2中停用此修復。</span><span class="sxs-lookup"><span data-stu-id="f7c62-153">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="f7c62-154">如果刪除的專案保留期間未設定為30天（Exchange Online 中的最大值），則您可以在步驟2中增加。</span><span class="sxs-lookup"><span data-stu-id="f7c62-154">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="f7c62-155">執行下列命令以取得信箱的信箱訪問設定。</span><span class="sxs-lookup"><span data-stu-id="f7c62-155">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="f7c62-156">您將會停用步驟2中的所有 access 方法。</span><span class="sxs-lookup"><span data-stu-id="f7c62-156">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="f7c62-157">執行下列命令，以取得有關信箱所套用之保留和保留原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="f7c62-157">Run the following command to get information about the holds and retention policies applied to the mailbox.</span></span>
    
    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="f7c62-158">如果*InPlaceHolds*屬性中的值太多，而且不是所有的值都顯示出來，您可以執行此 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 命令，以個別行顯示每一個值。</span><span class="sxs-lookup"><span data-stu-id="f7c62-158">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="f7c62-159">執行下列命令，以取得任何整個組織保留原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="f7c62-159">Run the following command to get information about any organization-wide retention policies.</span></span> 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   
   <span data-ttu-id="f7c62-160">如果您的組織有任何組織範圍的保留原則，您必須在步驟3中從這些原則中排除信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-160">If your organization has any organization-wide retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="f7c62-161">如果*InPlaceHolds*屬性中的值太多，而且不是所有的值都顯示出來，您可以執行此 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 命令，以個別行顯示每一個值。</span><span class="sxs-lookup"><span data-stu-id="f7c62-161">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="f7c62-162">執行下列命令，以取得使用者主要信箱中 [可復原的專案] 資料夾中的資料夾及子資料夾中目前的專案大小及總專案數目。</span><span class="sxs-lookup"><span data-stu-id="f7c62-162">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="f7c62-163">如果已啟用使用者的封存信箱，請執行下列命令，以取得封存信箱中 [可復原的專案] 資料夾中的資料夾與子資料夾中的專案大小和總數。</span><span class="sxs-lookup"><span data-stu-id="f7c62-163">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="f7c62-164">當您在步驟5中刪除專案時，您可以選擇刪除或不刪除使用者主要封存信箱中 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-164">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="f7c62-165">如果為信箱啟用自動擴充封存，則不會刪除輔助封存信箱中的專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-165">If auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="f7c62-166">步驟2：準備信箱</span><span class="sxs-lookup"><span data-stu-id="f7c62-166">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="f7c62-167">收集和儲存信箱的相關資訊之後，下一步是執行下列工作來準備信箱：</span><span class="sxs-lookup"><span data-stu-id="f7c62-167">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="f7c62-168">**停用用戶端對信箱的存取權**，讓信箱擁有者無法存取其信箱，並在此程式期間對信箱資料進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="f7c62-168">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="f7c62-169">將**刪除的專案保留期間增加**至30天（Exchange Online 中的最大值），這樣就不會從 [可復原的專案] 資料夾清除專案，您可以在步驟5中刪除專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-169">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="f7c62-170">**停用單一專案**復原，使其在您從步驟5的 [可復原的專案] 資料夾中刪除之後，不會保留專案（在刪除的專案保留期間內）。</span><span class="sxs-lookup"><span data-stu-id="f7c62-170">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="f7c62-171">**停用受管理的資料夾助理**，使其不處理信箱，並保留您在步驟5中刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-171">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="f7c62-172">在 Exchange Online PowerShell 中執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="f7c62-172">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="f7c62-173">執行下列命令，以停用所有用戶端存取信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-173">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="f7c62-174">命令語法假設所有的用戶端存取方法已在信箱上啟用。</span><span class="sxs-lookup"><span data-stu-id="f7c62-174">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="f7c62-175">可能需要長達60分鐘的時間，才能停用所有用戶端存取方法至信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-175">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="f7c62-176">請注意，停用這些存取方法不會中斷其目前已登入的信箱擁有者的連線。</span><span class="sxs-lookup"><span data-stu-id="f7c62-176">Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in.</span></span> <span data-ttu-id="f7c62-177">如果擁有者未登入，當這些存取方法停用之後，他們將無法存取其信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-177">If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="f7c62-178">執行下列命令，以將刪除的專案保留期間增加30天的上限。</span><span class="sxs-lookup"><span data-stu-id="f7c62-178">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="f7c62-179">這會假設目前的設定小於30天。</span><span class="sxs-lookup"><span data-stu-id="f7c62-179">This assumes that the current setting is less than 30 days.</span></span> 

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="f7c62-180">執行下列命令以停用單一專案復原。</span><span class="sxs-lookup"><span data-stu-id="f7c62-180">Run the following command to disable single item recovery.</span></span>
    
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="f7c62-181">最多可能需要60分鐘，以停用單一專案復原。</span><span class="sxs-lookup"><span data-stu-id="f7c62-181">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="f7c62-182">在此期間過後，請勿刪除 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-182">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="f7c62-183">執行下列命令，以防止受管理的資料夾助理處理信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-183">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="f7c62-184">如先前所述，只有具有保留鎖定原則的保留原則未套用至信箱時，您才可以停用受管理的資料夾助理。</span><span class="sxs-lookup"><span data-stu-id="f7c62-184">As previously explained, you can disable the Managed Folder Assistant only if a retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="f7c62-185">步驟3：移除信箱中的所有保留</span><span class="sxs-lookup"><span data-stu-id="f7c62-185">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="f7c62-186">您可以從 [可復原的專案] 資料夾中刪除專案的最後一個步驟，就是移除放置在信箱上的所有保留（您在步驟1中所識別）。</span><span class="sxs-lookup"><span data-stu-id="f7c62-186">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="f7c62-187">所有保留都必須移除，這樣在您從 [可復原的專案] 資料夾中刪除之後，就不會保留專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-187">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="f7c62-188">下列各節包含在信箱上移除不同類型保留的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f7c62-188">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="f7c62-189">請參閱[詳細資訊](#more-information)一節，以取得如何識別可能放置在信箱上之類型保留的秘訣。</span><span class="sxs-lookup"><span data-stu-id="f7c62-189">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="f7c62-190">如需詳細資訊，請參閱 how [to 識別位於 Exchange Online 信箱的保留類型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f7c62-190">For more information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f7c62-191">如先前所述，在從信箱移除保留之前，請先與您的記錄管理或法律部門聯繫。</span><span class="sxs-lookup"><span data-stu-id="f7c62-191">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="f7c62-192">訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="f7c62-192">Litigation Hold</span></span>
  
<span data-ttu-id="f7c62-193">在 Exchange Online PowerShell 中執行下列命令，以從信箱中移除訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="f7c62-193">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="f7c62-194">類似于停用用戶端存取方法和單一專案復原，可能需要長達60分鐘的時間來移除訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="f7c62-194">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="f7c62-195">在此期間過後，請勿刪除 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-195">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="f7c62-196">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="f7c62-196">In-Place Hold</span></span>
  
<span data-ttu-id="f7c62-197">在 Exchange Online PowerShell 中執行下列命令，以識別放在信箱上的 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="f7c62-197">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="f7c62-198">使用您在步驟1中識別的 In-Place 保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="f7c62-198">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

<span data-ttu-id="f7c62-199">在您識別 In-Place 保留後，您可以使用 Exchange 系統管理中心（EAC）或 Exchange Online PowerShell 從保留中移除信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-199">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="f7c62-200">如需詳細資訊，請參閱[建立或移除 In-Place 保留](https://go.microsoft.com/fwlink/?linkid=852668)。</span><span class="sxs-lookup"><span data-stu-id="f7c62-200">For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="f7c62-201">套用至特定信箱的保留原則</span><span class="sxs-lookup"><span data-stu-id="f7c62-201">Retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="f7c62-202">在[安全性 & 規範中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中執行下列命令，以識別套用至信箱的保留原則。</span><span class="sxs-lookup"><span data-stu-id="f7c62-202">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="f7c62-203">使用 `mbx` `skp` 您在步驟1中所識別之保留原則的 GUID （不包括或前置詞）。</span><span class="sxs-lookup"><span data-stu-id="f7c62-203">Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="f7c62-204">在您識別保留原則之後，請移至 [安全性 & 規範中心] 中的 [**資訊管理** \> **保留**] 頁面，編輯您在上一個步驟中識別的保留原則，然後從保留原則中所包含的收件者清單中移除信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-204">After you identify the retention policy, go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-retention-policies"></a><span data-ttu-id="f7c62-205">全組織保留原則</span><span class="sxs-lookup"><span data-stu-id="f7c62-205">Organization-wide retention policies</span></span>
  
<span data-ttu-id="f7c62-206">整個組織內和 Exchange 通用保留原則會套用至組織中的每個信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-206">Organization-wide and Exchange-wide retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="f7c62-207">當您在步驟1中執行**Get-OrganizationConfig** Cmdlet 時，會在組織層級（非信箱層級）套用這些功能。</span><span class="sxs-lookup"><span data-stu-id="f7c62-207">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="f7c62-208">在[安全性 & 規範中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中執行下列命令，以找出整個組織的保留原則。</span><span class="sxs-lookup"><span data-stu-id="f7c62-208">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide retention policies.</span></span> <span data-ttu-id="f7c62-209">`mbx`針對您在步驟1中識別的全組織保留原則，使用 GUID （不包括前置詞）。</span><span class="sxs-lookup"><span data-stu-id="f7c62-209">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="f7c62-210">在您識別整個組織的保留原則之後，請移至安全性 & 規範中心內的「**資訊管理**」 \> **保留**頁面，編輯您在上一個步驟中識別的每個整個組織保留原則，並將信箱新增至排除的收件者清單。</span><span class="sxs-lookup"><span data-stu-id="f7c62-210">After you identify the organization-wide retention policies, go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="f7c62-211">這樣做會將使用者的信箱從保留原則中移除。</span><span class="sxs-lookup"><span data-stu-id="f7c62-211">Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="retention-labels"></a><span data-ttu-id="f7c62-212">保留標籤</span><span class="sxs-lookup"><span data-stu-id="f7c62-212">Retention labels</span></span>

<span data-ttu-id="f7c62-213">每當使用者套用設定為保留內容或保留的標籤，然後將內容刪除至其信箱中的任何資料夾或專案時， *ComplianceTagHoldApplied*信箱屬性都會設為**True**。</span><span class="sxs-lookup"><span data-stu-id="f7c62-213">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="f7c62-214">發生這種情況時，信箱會被視為保留，就像是設定為訴訟暫止或指派給保留原則一樣。</span><span class="sxs-lookup"><span data-stu-id="f7c62-214">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to a retention policy.</span></span>

<span data-ttu-id="f7c62-215">若要查看*ComplianceTagHoldApplied*屬性的值，請在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f7c62-215">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="f7c62-216">在您識別信箱已保留狀態，因為保留標籤套用到資料夾或專案，您可以使用安全性與合規性中心的內容搜尋工具，利用 New-compliancetag 搜尋條件來搜尋已標示的專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-216">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the security and compliance center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="f7c62-217">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)中的「搜尋條件」一節。</span><span class="sxs-lookup"><span data-stu-id="f7c62-217">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="f7c62-218">如需標籤的詳細資訊，請參閱[標籤概觀](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="f7c62-218">For more information about labels, see [Overview of labels](labels.md).</span></span>

 ### <a name="ediscovery-holds"></a><span data-ttu-id="f7c62-219">eDiscovery 保留</span><span class="sxs-lookup"><span data-stu-id="f7c62-219">eDiscovery holds</span></span>
  
<span data-ttu-id="f7c62-220">在[安全性 & 規範中心」 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)中執行下列命令，識別與套用至信箱的 ediscovery 案例（稱為*ediscovery 保留*）相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="f7c62-220">Run the following commands in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) to identify the hold associated with an eDiscovery case (called *eDiscovery holds*) that's applied to the mailbox.</span></span> <span data-ttu-id="f7c62-221">使用 `UniH` 您在步驟1中識別的 eDiscovery 暫止的 GUID （不包括前置詞）。</span><span class="sxs-lookup"><span data-stu-id="f7c62-221">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="f7c62-222">第二個命令會顯示保留所關聯的 eDiscovery 案例名稱;第三個命令會顯示保留的名稱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-222">The second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

<span data-ttu-id="f7c62-223">在您識別 eDiscovery 案例名稱和保留後，請移至規範中心的 [ **ediscovery** \> **ediscovery** ] 頁面，開啟案例，然後從保留中移除信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-223">After you've identified the name of the eDiscovery case and the hold, go to the **eDiscovery** \> **eDiscovery** page in the compliance center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="f7c62-224">如需識別 eDiscovery 保留的詳細資訊，請參閱[如何識別位於 Exchange Online 信箱之保留類型](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)的「eDiscovery 保留」一節。</span><span class="sxs-lookup"><span data-stu-id="f7c62-224">For more information about identifying eDiscovery holds, see the "eDiscovery holds" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="f7c62-225">步驟4：移除信箱的延遲保留</span><span class="sxs-lookup"><span data-stu-id="f7c62-225">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="f7c62-226">從信箱移除任何類型的保留後， *DelayHoldApplied*或*DelayReleaseHoldApplied*信箱屬性的值會設為**True**。</span><span class="sxs-lookup"><span data-stu-id="f7c62-226">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="f7c62-227">這會在下一次受管理的資料夾助理處理信箱，並偵測已移除保留。</span><span class="sxs-lookup"><span data-stu-id="f7c62-227">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="f7c62-228">這稱為*延遲保留*，表示實際移除保留延遲30天，以防止資料從信箱中永久刪除。</span><span class="sxs-lookup"><span data-stu-id="f7c62-228">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="f7c62-229">（延遲保留的目的是讓系統管理員有機會搜尋或復原在移除保留後將會清除的信箱專案。） 將延遲保留放在信箱上時，信箱仍會被視為無限期的保留狀態，就像當信箱處於訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="f7c62-229">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="f7c62-230">30天后，延遲保留會到期，而且 Microsoft 365 會自動嘗試移除延遲保留（透過將*DelayHoldApplied*或*DelayReleaseHoldApplied*屬性設為**False**），以移除 [保留]。</span><span class="sxs-lookup"><span data-stu-id="f7c62-230">After 30 days, the delay hold expires, and Microsoft 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* or *DelayReleaseHoldApplied* property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="f7c62-231">如需有關延遲保留的詳細資訊，請參閱[如何識別位於 Exchange Online 信箱之保留類型](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)的「管理延遲暫止的信箱」一節。</span><span class="sxs-lookup"><span data-stu-id="f7c62-231">For more information about a delay hold, see the "Managing mailboxes on delay hold" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

<span data-ttu-id="f7c62-232">在您可以刪除步驟5中的專案之前，您必須移除信箱的延遲保留。</span><span class="sxs-lookup"><span data-stu-id="f7c62-232">Before you can delete items in Step 5, you have to remove a delay hold from the mailbox.</span></span> <span data-ttu-id="f7c62-233">首先，在 Exchange Online 中執行下列命令，判斷是否要將延遲保留套用至信箱 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f7c62-233">First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

<span data-ttu-id="f7c62-234">如果*DelayHoldApplied*或*DelayReleaseHoldApplied*屬性的值設為**False**，則不會在信箱上設定延遲保留。</span><span class="sxs-lookup"><span data-stu-id="f7c62-234">If the value of either the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **False**, a delay hold has not been placed on the mailbox.</span></span> <span data-ttu-id="f7c62-235">您可以移至步驟5並刪除 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-235">You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="f7c62-236">如果*DelayHoldApplied*或*DelayReleaseHoldApplied*屬性的值設為**True**，請執行下列其中一個命令，以移除延遲保留：</span><span class="sxs-lookup"><span data-stu-id="f7c62-236">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True**, run one of the following commands to remove the delay hold:</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="f7c62-237">或</span><span class="sxs-lookup"><span data-stu-id="f7c62-237">Or</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="f7c62-238">您必須在 Exchange Online 中指派合法保留角色，才能使用*RemoveDelayHoldApplied*或*RemoveDelayReleaseHoldApplied*參數。</span><span class="sxs-lookup"><span data-stu-id="f7c62-238">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="f7c62-239">步驟5：刪除 [可復原的專案] 資料夾中的專案</span><span class="sxs-lookup"><span data-stu-id="f7c62-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="f7c62-240">現在，您已準備好使用 [安全性 & 規範中心] 中的[New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)和[New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) Cmdlet 來實際刪除 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-240">Now you're ready to actually delete items in the Recoverable Items folder by using the [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch) and [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) cmdlets in the Security & Compliance Center.</span></span> 

<span data-ttu-id="f7c62-241">若要執行此動作，請參閱[搜尋並刪除電子郵件訊息](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="f7c62-241">To do this, see [Search for and delete email messages](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).</span></span>

### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="f7c62-242">確認已刪除專案</span><span class="sxs-lookup"><span data-stu-id="f7c62-242">Verify that items were deleted</span></span>

<span data-ttu-id="f7c62-243">若要確認您是否已成功刪除信箱的 [可復原的專案] 資料夾中的專案，請使用**Get-MailboxFolderStatistics** Cmdlet In Exchange Online PowerShell 以檢查 [可復原的專案] 資料夾中的專案大小和數目。</span><span class="sxs-lookup"><span data-stu-id="f7c62-243">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="f7c62-244">您可以將這些統計資料與您在步驟1中收集的統計資料進行比較。</span><span class="sxs-lookup"><span data-stu-id="f7c62-244">You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="f7c62-245">在中執行下列命令，以取得使用者主要信箱中 [可復原的專案] 資料夾中的資料夾與子資料夾中目前的專案大小及總專案數目。</span><span class="sxs-lookup"><span data-stu-id="f7c62-245">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

<span data-ttu-id="f7c62-246">執行下列命令，以取得使用者封存信箱中 [可復原的專案] 資料夾中的資料夾及子資料夾中的專案大小和總數。</span><span class="sxs-lookup"><span data-stu-id="f7c62-246">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="f7c62-247">步驟6：將信箱還原為先前的狀態</span><span class="sxs-lookup"><span data-stu-id="f7c62-247">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="f7c62-248">最後一個步驟是將信箱還原回先前的設定。</span><span class="sxs-lookup"><span data-stu-id="f7c62-248">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="f7c62-249">這表示重設您在步驟2中變更的屬性，並重新應用您在步驟3中移除的保留。</span><span class="sxs-lookup"><span data-stu-id="f7c62-249">This means resetting the properties that you changed in Step 2 and reapplying the holds that you removed in Step 3.</span></span> <span data-ttu-id="f7c62-250">這包括：</span><span class="sxs-lookup"><span data-stu-id="f7c62-250">This includes:</span></span>
  
- <span data-ttu-id="f7c62-251">將刪除的專案保留期間變更回其先前的值。</span><span class="sxs-lookup"><span data-stu-id="f7c62-251">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="f7c62-252">或者，您可以將此集保留為30天，這是 Exchange Online 中的最大值。</span><span class="sxs-lookup"><span data-stu-id="f7c62-252">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="f7c62-253">重新啟用單一專案復原。</span><span class="sxs-lookup"><span data-stu-id="f7c62-253">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="f7c62-254">重新啟用用戶端存取方法，讓擁有者可以存取其信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-254">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="f7c62-255">重新應用您移除的保留和保留原則。</span><span class="sxs-lookup"><span data-stu-id="f7c62-255">Reapplying the holds and retention policies that you removed.</span></span>
    
- <span data-ttu-id="f7c62-256">重新啟用受管理的資料夾助理以處理信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-256">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="f7c62-257">建議您在重新啟用受管理的資料夾助理以處理信箱之前，先等候24小時後再重新套用保留原則（及驗證是否已到位）。</span><span class="sxs-lookup"><span data-stu-id="f7c62-257">We recommend that you wait 24 hours after re-applying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="f7c62-258">在 Exchange Online PowerShell 中執行下列步驟（以指定的順序）。</span><span class="sxs-lookup"><span data-stu-id="f7c62-258">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="f7c62-259">執行下列命令，將刪除的專案保留期間變更回其原始值。</span><span class="sxs-lookup"><span data-stu-id="f7c62-259">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="f7c62-260">這會假設上一個設定小於30天;例如，14天。</span><span class="sxs-lookup"><span data-stu-id="f7c62-260">This assumes that the previous setting is less than 30 days; for example, 14 days.</span></span> 
    
    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. <span data-ttu-id="f7c62-261">執行下列命令，以重新啟用單一專案復原。</span><span class="sxs-lookup"><span data-stu-id="f7c62-261">Run the following command to re-enable single item recovery.</span></span>
   
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="f7c62-262">執行下列命令，以重新啟用所有用戶端存取方法至信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-262">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. <span data-ttu-id="f7c62-263">重新套用您在步驟3中移除的保留。</span><span class="sxs-lookup"><span data-stu-id="f7c62-263">Reapply the holds that you removed in Step 3.</span></span> <span data-ttu-id="f7c62-264">根據保留的類型，使用下列其中一個程式。</span><span class="sxs-lookup"><span data-stu-id="f7c62-264">Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="f7c62-265">**訴訟暫止**</span><span class="sxs-lookup"><span data-stu-id="f7c62-265">**Litigation Hold**</span></span>
    
    <span data-ttu-id="f7c62-266">執行下列命令，以重新啟用信箱的訴訟暫止。</span><span class="sxs-lookup"><span data-stu-id="f7c62-266">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="f7c62-267">**原有範圍暫止**</span><span class="sxs-lookup"><span data-stu-id="f7c62-267">**In-Place Hold**</span></span>
    
    <span data-ttu-id="f7c62-268">使用 EAC （或 Exchange Online PowerShell）將信箱重新加入 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="f7c62-268">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="f7c62-269">**套用至特定信箱的保留原則**</span><span class="sxs-lookup"><span data-stu-id="f7c62-269">**Retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="f7c62-270">使用安全性 & 規範中心，將信箱新增回保留原則。</span><span class="sxs-lookup"><span data-stu-id="f7c62-270">Use the Security & Compliance Center to add the mailbox back to the retention policy.</span></span> <span data-ttu-id="f7c62-271">移至 [安全性 & 規範中心] 中的 [**資訊**控管 \> **保留**] 頁面，編輯保留原則，並將信箱重新新增至套用保留原則的收件者清單。</span><span class="sxs-lookup"><span data-stu-id="f7c62-271">Go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="f7c62-272">**全組織保留原則**</span><span class="sxs-lookup"><span data-stu-id="f7c62-272">**Organization-wide Retention policies**</span></span>
    
    <span data-ttu-id="f7c62-273">如果您已移除整個組織或 Exchange 範圍的保留原則，請從原則中排除它，然後使用安全性 & 合規性中心，從排除的使用者清單中移除信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-273">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security & Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="f7c62-274">移至 [安全性 & 規範中心] 中的 [**資訊**控管 \> **保留**] 頁面，編輯整個組織的保留原則，然後從排除的收件者清單中移除信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-274">Go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="f7c62-275">這樣做會將保留原則重新套用至使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-275">Doing this will reapply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="f7c62-276">**eDiscovery 案例保留**</span><span class="sxs-lookup"><span data-stu-id="f7c62-276">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="f7c62-277">使用安全性 & 合規性中心，將信箱回復與 eDiscovery 案例相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="f7c62-277">Use the Security & Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="f7c62-278">移至 [ **ediscovery** \> **ediscovery** ] 頁面，開啟案例，然後將信箱新增回保留。</span><span class="sxs-lookup"><span data-stu-id="f7c62-278">Go to the **eDiscovery** \> **eDiscovery** page, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="f7c62-279">執行下列命令，讓受管理的資料夾助理再次處理信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-279">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="f7c62-280">如先前所述，建議您在重新啟用受管理的資料夾助理之前，先將保留原則重新套用保留或保留原則（並驗證已到位）後等候24小時。</span><span class="sxs-lookup"><span data-stu-id="f7c62-280">As previously stated, we recommend that you wait 24 hours after reapplying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. <span data-ttu-id="f7c62-281">若要驗證信箱是否已回復回先前的設定，您可以執行下列命令，並將設定與您在步驟1中收集的設定進行比較。</span><span class="sxs-lookup"><span data-stu-id="f7c62-281">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a><span data-ttu-id="f7c62-282">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="f7c62-282">More information</span></span>

<span data-ttu-id="f7c62-283">以下表格說明當您執行**Get-Mailbox**或**Get-OrganizationConfig** Cmdlet 時，如何根據*InPlaceHolds*屬性中的值來識別不同的保留類型。</span><span class="sxs-lookup"><span data-stu-id="f7c62-283">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="f7c62-284">如需詳細資訊，請參閱 how [to 識別位於 Exchange Online 信箱的保留類型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f7c62-284">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="f7c62-285">如先前所述，您必須先移除信箱的所有保留和保留原則，才能成功刪除 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="f7c62-285">As previously explained, you have to remove all holds and retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="f7c62-286">**保留類型**</span><span class="sxs-lookup"><span data-stu-id="f7c62-286">**Hold type**</span></span>|<span data-ttu-id="f7c62-287">**範例值**</span><span class="sxs-lookup"><span data-stu-id="f7c62-287">**Example value**</span></span>|<span data-ttu-id="f7c62-288">**如何識別保留**</span><span class="sxs-lookup"><span data-stu-id="f7c62-288">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7c62-289">訴訟暫止</span><span class="sxs-lookup"><span data-stu-id="f7c62-289">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="f7c62-290">*LitigationHoldEnabled*屬性設定為 `True` 。</span><span class="sxs-lookup"><span data-stu-id="f7c62-290">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="f7c62-291">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="f7c62-291">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="f7c62-292">*InPlaceHolds*屬性包含放在信箱上的 IN-PLACE 保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="f7c62-292">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="f7c62-293">您可以告訴這是 In-Place 保留，因為 GUID 不是以前置詞開頭。</span><span class="sxs-lookup"><span data-stu-id="f7c62-293">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="f7c62-294">您可以使用 `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Exchange Online PowerShell 中的命令，取得信箱上 In-Place 保留的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f7c62-294">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="f7c62-295">套用至特定信箱之安全性 & 規範中心內的保留原則</span><span class="sxs-lookup"><span data-stu-id="f7c62-295">Retention policies in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="f7c62-296">或</span><span class="sxs-lookup"><span data-stu-id="f7c62-296">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="f7c62-297">當您執行**Get-Mailbox** Cmdlet 時， *InPlaceHolds*屬性也會包含套用至信箱的保留原則的 guid。</span><span class="sxs-lookup"><span data-stu-id="f7c62-297">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of retention policies applied to the mailbox.</span></span> <span data-ttu-id="f7c62-298">您可以識別保留原則，因為 GUID 會以前置詞開頭 `mbx` 。</span><span class="sxs-lookup"><span data-stu-id="f7c62-298">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="f7c62-299">如果保留原則的 GUID 是以前置詞開頭 `skp` ，表示保留原則套用至商務用 Skype 交談。</span><span class="sxs-lookup"><span data-stu-id="f7c62-299">If the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="f7c62-300">若要識別套用至信箱的保留原則，請在安全性 & 規範中心內執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f7c62-300">To identity the retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="f7c62-301">`mbx` `skp` 當您執行此命令時，請務必移除或首碼。</span><span class="sxs-lookup"><span data-stu-id="f7c62-301">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="f7c62-302">安全性 & 規範中心內的整個組織保留原則</span><span class="sxs-lookup"><span data-stu-id="f7c62-302">Organization-wide retention policies in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="f7c62-303">無值</span><span class="sxs-lookup"><span data-stu-id="f7c62-303">No value</span></span>  <br/> <span data-ttu-id="f7c62-304">或</span><span class="sxs-lookup"><span data-stu-id="f7c62-304">or</span></span>  <br/>  <span data-ttu-id="f7c62-305">`-mbxe9b52bf7ab3b46a286308ecb29624696`（表示信箱已從整個組織的原則中排除）</span><span class="sxs-lookup"><span data-stu-id="f7c62-305">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="f7c62-306">即使當您執行**Get-Mailbox** Cmdlet 時， *InPlaceHolds*屬性是空的，仍然有一個或多個組織範圍的保留原則會套用至信箱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-306">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="f7c62-307">若要確認這一點，您可以 `Get-OrganizationConfig | FL InPlaceHolds` 在 Exchange Online PowerShell 中執行命令，以取得整個組織保留原則的 guid 清單。</span><span class="sxs-lookup"><span data-stu-id="f7c62-307">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide retention policies.</span></span> <span data-ttu-id="f7c62-308">套用至 Exchange 信箱之全組織保留原則的 GUID 會以前置詞開始 `mbx` ; 例如， `mbxa3056bb15562480fadb46ce523ff7b02` 。</span><span class="sxs-lookup"><span data-stu-id="f7c62-308">The GUID for organization-wide retention policies applied to Exchange mailboxes starts with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="f7c62-309">若要識別套用至信箱的全組織保留原則，請在安全性 & 規範中心內執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f7c62-309">To identity the organization-wide retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="f7c62-310">如果信箱已從整個組織的保留原則中排除，當您執行**Get-Mailbox** Cmdlet 時，保留原則的 GUID 會顯示在使用者信箱的*InPlaceHolds*屬性中;它會以前置詞識別 `-mbx` ; 例如，`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="f7c62-310">If a mailbox is excluded from an organization-wide retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="f7c62-311">安全性 & 規範中心的 eDiscovery 案例保留</span><span class="sxs-lookup"><span data-stu-id="f7c62-311">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="f7c62-312">*InPlaceHolds*屬性也包含與可能位於信箱上安全性 & 合規性中心的 eDiscovery 案例相關聯之任何保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="f7c62-312">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="f7c62-313">您可以告訴這是 eDiscovery 案例保留，因為 GUID 是以前置詞開頭 `UniH` 。</span><span class="sxs-lookup"><span data-stu-id="f7c62-313">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="f7c62-314">您可以使用 `Get-CaseHoldPolicy` 安全性 & 規範中心 PowerShell 中的指令程式，以取得與信箱的保留相關之 eDiscovery 案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f7c62-314">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="f7c62-315">例如，您可以執行命令 `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 以顯示信箱上的案例保留名稱。</span><span class="sxs-lookup"><span data-stu-id="f7c62-315">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="f7c62-316">`UniH`當您執行此命令時，請務必移除前置詞。</span><span class="sxs-lookup"><span data-stu-id="f7c62-316">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="f7c62-317">若要識別與信箱上的保留相關聯的 eDiscovery 案例，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f7c62-317">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


