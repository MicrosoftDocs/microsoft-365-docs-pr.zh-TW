---
title: 增加保留信箱的可復原項目配額
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 啟用封存信箱，並開啟自動擴充封存，增加 Microsoft 365 中信箱的 [可復原的專案] 資料夾的大小。
ms.openlocfilehash: 7b4ee808bc3004438c9eb7424a89c01567fc04d9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911271"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="538e1-103">增加保留信箱的可復原項目配額</span><span class="sxs-lookup"><span data-stu-id="538e1-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="538e1-104">預設的 Exchange 保留原則（名為「 *預設 MRM 原則*」）會自動套用至 Exchange Online 中的新信箱，包含一個名為「可復原的專案14天」的保留標記，可移至封存。</span><span class="sxs-lookup"><span data-stu-id="538e1-104">The default Exchange retention policy—named *Default MRM Policy*—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="538e1-105">這項保留標記會將專案從使用者主要信箱的 [可復原的專案] 資料夾移至使用者封存信箱中的 [可復原的專案] 資料夾之後，在14天的保留期間到期的專案。</span><span class="sxs-lookup"><span data-stu-id="538e1-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="538e1-106">為做到這一點，必須啟用使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="538e1-107">如果未啟用封存信箱，則不會採取任何動作，這表示在14天保留期間到期後，信箱的 [可復原的專案] 資料夾中的專案不會移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="538e1-108">因為保留信箱中未刪除任何專案，可能會超出 [可復原的專案] 資料夾的儲存配額，尤其是在未啟用使用者的封存信箱的情況下。</span><span class="sxs-lookup"><span data-stu-id="538e1-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="538e1-109">為了協助降低超過此限制的機率，[可復原的專案] 資料夾的儲存配額會在 Exchange Online 中的信箱上進行保留時，自動從 30 GB 增加為 100 GB。</span><span class="sxs-lookup"><span data-stu-id="538e1-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="538e1-110">如果已啟用封存信箱，則封存信箱中 [可復原的專案] 資料夾的儲存配額也會從 30 GB 增加為 100 GB。</span><span class="sxs-lookup"><span data-stu-id="538e1-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="538e1-111">如果啟用 Exchange Online 中的自動展開封存功能，使用者封存中 [可復原的專案] 資料夾的儲存配額將不受限制。</span><span class="sxs-lookup"><span data-stu-id="538e1-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="538e1-112">下表摘要說明 [可復原的專案] 資料夾的儲存配額。</span><span class="sxs-lookup"><span data-stu-id="538e1-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="538e1-113">**[可復原的專案] 資料夾的位置**</span><span class="sxs-lookup"><span data-stu-id="538e1-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="538e1-114">**未保留信箱**</span><span class="sxs-lookup"><span data-stu-id="538e1-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="538e1-115">**保留信箱**</span><span class="sxs-lookup"><span data-stu-id="538e1-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="538e1-116">主要信箱</span><span class="sxs-lookup"><span data-stu-id="538e1-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="538e1-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="538e1-117">30 GB</span></span>  <br/> |<span data-ttu-id="538e1-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="538e1-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="538e1-119">封存信箱<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="538e1-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="538e1-120">無限制</span><span class="sxs-lookup"><span data-stu-id="538e1-120">Unlimited</span></span>  <br/> |<span data-ttu-id="538e1-121">無限制</span><span class="sxs-lookup"><span data-stu-id="538e1-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="538e1-122">**[可復原的專案] 資料夾的儲存配額總計**</span><span class="sxs-lookup"><span data-stu-id="538e1-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="538e1-123">無限制</span><span class="sxs-lookup"><span data-stu-id="538e1-123">Unlimited</span></span>  <br/> |<span data-ttu-id="538e1-124">無限制</span><span class="sxs-lookup"><span data-stu-id="538e1-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="538e1-125"><sup>\*</sup> 使用 Exchange Online 的使用者，封存信箱的初始儲存配額為 100 GB (Plan 2) 授權。</span><span class="sxs-lookup"><span data-stu-id="538e1-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="538e1-126">不過，當已開啟信箱的自動展開封存功能時，封存信箱和 [可復原的專案] 資料夾的儲存配額會增至 110 GB。</span><span class="sxs-lookup"><span data-stu-id="538e1-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="538e1-127">必要時會布建額外的封存儲存空間，這會產生無限的封存儲存量。</span><span class="sxs-lookup"><span data-stu-id="538e1-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="538e1-128">如需有關自動展開封存的詳細資訊，請參閱 [Office 365 中的無限封存概述](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="538e1-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="538e1-129">當信箱的主要信箱中 [可復原的專案] 資料夾的儲存配額接近達到限制時，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="538e1-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="538e1-130">**啟用封存信箱，並開啟自動展開的封存。**</span><span class="sxs-lookup"><span data-stu-id="538e1-130">**Enable the archive mailbox and turn on auto-expanding archiving.**</span></span> <span data-ttu-id="538e1-131">您可以為 [可復原的專案] 資料夾啟用無限的儲存容量，只要啟用封存信箱，然後開啟 Exchange Online 中的自動擴充封存功能即可。</span><span class="sxs-lookup"><span data-stu-id="538e1-131">You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="538e1-132">這會導致主要信箱中 [可復原的專案] 資料夾的 110 GB 和使用者封存中 [可復原的專案] 資料夾的儲存容量量不限。</span><span class="sxs-lookup"><span data-stu-id="538e1-132">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="538e1-133">請參閱操作方法： [在安全性 & 規範中心啟用封存信箱](enable-archive-mailboxes.md) ，並 [在 Office 365 中啟用無限](enable-unlimited-archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="538e1-133">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="538e1-134">當您為接近超過 [可復原的專案] 資料夾的儲存配額的信箱啟用封存後，您可能會想要執行受管理的資料夾助理以手動觸發該信箱的處理常式，使到期的專案移至封存信箱中的 [可復原的專案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="538e1-134">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved to the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="538e1-135">如需指示，請參閱 [步驟 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 。</span><span class="sxs-lookup"><span data-stu-id="538e1-135">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="538e1-136">請注意，使用者信箱中的其他專案可能會移至新的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-136">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="538e1-137">請考慮告知使用者啟用封存信箱之後可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="538e1-137">Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="538e1-138">**為保留信箱建立自訂 Exchange 保留原則。**</span><span class="sxs-lookup"><span data-stu-id="538e1-138">**Create a custom Exchange retention policy for mailboxes on hold.**</span></span> <span data-ttu-id="538e1-139">除了為訴訟暫止或 In-Place 暫止啟用信箱的封存信箱和自動展開封存之外，您還可以為保留信箱建立自訂的 Exchange 保留原則。</span><span class="sxs-lookup"><span data-stu-id="538e1-139">In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom Exchange retention policy for mailboxes on hold.</span></span> <span data-ttu-id="538e1-140">這可讓您將保留原則套用至保留的信箱，與套用至未保留信箱的預設 MRM 原則不同，並可讓您套用為保留信箱所設計的保留標記。</span><span class="sxs-lookup"><span data-stu-id="538e1-140">This lets you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold, and lets you apply retention tags that are designed for mailboxes on hold.</span></span> <span data-ttu-id="538e1-141">這包括為 [可復原的專案] 資料夾建立新的保留標記。</span><span class="sxs-lookup"><span data-stu-id="538e1-141">This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="538e1-142">本主題的其餘部分將說明為保留信箱建立自訂 Exchange 保留原則的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="538e1-142">The remainder of this topic describes the step-by-step procedures to create a custom Exchange retention policy for mailboxes on hold.</span></span>
  
<span data-ttu-id="538e1-143">[步驟1：為 [可復原的專案] 資料夾建立自訂保留標記](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)</span><span class="sxs-lookup"><span data-stu-id="538e1-143">[Step 1: Create a custom retention tag for the Recoverable Items folder](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)</span></span>

[<span data-ttu-id="538e1-144">步驟2：為保留信箱建立新的 Exchange 保留原則</span><span class="sxs-lookup"><span data-stu-id="538e1-144">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[<span data-ttu-id="538e1-145">步驟3：將新的 Exchange 保留原則套用至保留信箱</span><span class="sxs-lookup"><span data-stu-id="538e1-145">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="538e1-146"> (選用) 步驟4：執行受管理的資料夾助理以套用新的保留設定</span><span class="sxs-lookup"><span data-stu-id="538e1-146">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="538e1-147">步驟1：為 [可復原的專案] 資料夾建立自訂保留標記</span><span class="sxs-lookup"><span data-stu-id="538e1-147">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="538e1-148">第一步是針對 [可復原的專案] 資料夾，建立稱為保留原則標記或 RPT) 的自訂保留標記 (。</span><span class="sxs-lookup"><span data-stu-id="538e1-148">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="538e1-149">如先前所述，此 RPT 會將專案從使用者主要信箱的 [可復原的專案] 資料夾移至使用者封存信箱中的 [可復原的專案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="538e1-149">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="538e1-150">您必須使用 PowerShell 為 [可復原的專案] 資料夾建立 RPT。</span><span class="sxs-lookup"><span data-stu-id="538e1-150">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="538e1-151">您無法使用 Exchange 系統管理中心 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="538e1-151">You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="538e1-152">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="538e1-152">Connect to Exchange Online using remote PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. <span data-ttu-id="538e1-153">執行下列命令，為 [可復原的專案] 資料夾建立新的 RPT：</span><span class="sxs-lookup"><span data-stu-id="538e1-153">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="538e1-154">例如，下列命令會針對名為「暫止的信箱」的 [可復原的專案30天] 的 [可復原的專案] 資料夾建立 RPT，保留期間為30天。</span><span class="sxs-lookup"><span data-stu-id="538e1-154">For example, the following command creates an RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days.</span></span> <span data-ttu-id="538e1-155">這表示專案已在 [可復原的專案] 資料夾中的30天之後，它會移至使用者的封存信箱中的 [可復原的專案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="538e1-155">This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="538e1-156">建議 [可復原的專案 RPT] 的  _AgeLimitForRetention_ 參數) 所定義的保留期間 (，與 RPT 將套用到之信箱的已刪除專案保留期間相同。</span><span class="sxs-lookup"><span data-stu-id="538e1-156">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="538e1-157">這可讓使用者在將刪除的專案移至封存信箱之前，先將其整個刪除的專案保留期間復原。</span><span class="sxs-lookup"><span data-stu-id="538e1-157">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="538e1-158">在上一個範例中，保留期間會設定為30天，但前提是信箱的刪除專案保留期間也是30天。</span><span class="sxs-lookup"><span data-stu-id="538e1-158">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="538e1-159">Exchange Online 信箱預設會將刪除的項目保留 14 天。</span><span class="sxs-lookup"><span data-stu-id="538e1-159">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="538e1-160">不過，您可以將此設定變更為最多30天。</span><span class="sxs-lookup"><span data-stu-id="538e1-160">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="538e1-161">如需詳細資訊，請參閱 [在 Exchange Online 中變更信箱的已刪除專案保留期間](https://www.microsoft.com/?ref=go)。</span><span class="sxs-lookup"><span data-stu-id="538e1-161">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go).</span></span> 
  
## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="538e1-162">步驟2：為保留信箱建立新的 Exchange 保留原則</span><span class="sxs-lookup"><span data-stu-id="538e1-162">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>

<span data-ttu-id="538e1-163">下一步是建立新的保留原則並新增保留標記，包括您在步驟1中建立的可復原專案 RPT。</span><span class="sxs-lookup"><span data-stu-id="538e1-163">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1.</span></span> <span data-ttu-id="538e1-164">在下一個步驟中，此新原則會套用至信箱保留。</span><span class="sxs-lookup"><span data-stu-id="538e1-164">This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="538e1-165">在您建立新的保留原則之前，請先確定您想要新增的其他保留標記。</span><span class="sxs-lookup"><span data-stu-id="538e1-165">Before you create the new retention policy, determine the additional retention tags that you want to add.</span></span> <span data-ttu-id="538e1-166">如需新增至預設 MRM 原則的保留標記清單，以及建立新保留標記的相關資訊，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="538e1-166">For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="538e1-167">Exchange Online 中的預設保留原則</span><span class="sxs-lookup"><span data-stu-id="538e1-167">Default Retention Policy in Exchange Online </span></span>](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)
    
- [<span data-ttu-id="538e1-168">支援保留原則標記的預設資料夾</span><span class="sxs-lookup"><span data-stu-id="538e1-168">Default folders that support Retention Policy Tags</span></span>](/exchange/security-and-compliance/messaging-records-management/default-folders)
    
- <span data-ttu-id="538e1-169">[ [建立保留原則](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) ] 主題中的「建立保留標記」一節。</span><span class="sxs-lookup"><span data-stu-id="538e1-169">The "Create a retention tag" section in the [Create a Retention Policy](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) topic.</span></span>
    
<span data-ttu-id="538e1-170">您可以使用 EAC 或 Exchange Online PowerShell 建立保留原則。</span><span class="sxs-lookup"><span data-stu-id="538e1-170">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="538e1-171">使用 EAC 建立保留原則</span><span class="sxs-lookup"><span data-stu-id="538e1-171">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="538e1-172">在 EAC 中，移至 [ **規範管理**] [ \> **保留原則**]，然後按一下 [ **新增**] [新增] ![ 圖示 ](../media/ITPro-EAC-AddIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="538e1-172">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="538e1-173">在 [ **新增保留原則** ] 頁面的 [ **名稱**] 下，輸入描述保留原則目的的名稱，然後按一下 [是]。例如， **保留信箱的 MRM 原則**。</span><span class="sxs-lookup"><span data-stu-id="538e1-173">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="538e1-174">在 [ **保留標記**] 底下，按一下 [ **新增**] ![ 圖示 ](../media/ITPro-EAC-AddIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="538e1-174">Under **Retention tags**, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="538e1-175">在 [保留標記] 清單中，選取您在步驟1中建立的 [可復原的專案 RPT]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="538e1-175">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![選取自訂的 [可復原的項目] 保留標記](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="538e1-177">選取要新增至保留原則的其他保留標記。</span><span class="sxs-lookup"><span data-stu-id="538e1-177">Select additional retention tags to add to the retention policy.</span></span> <span data-ttu-id="538e1-178">例如，您可能想要加入預設 MRM 原則中所包含的相同標記。</span><span class="sxs-lookup"><span data-stu-id="538e1-178">For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="538e1-179">完成新增保留標記之後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="538e1-179">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="538e1-180">按一下 [ **儲存** ] 以建立新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="538e1-180">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="538e1-181">請注意，連結至保留原則的保留標記會顯示在詳細資料窗格中。</span><span class="sxs-lookup"><span data-stu-id="538e1-181">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![連結到保留原則的保留標記，會顯示在詳細資料窗格中](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="538e1-183">使用 Exchange Online PowerShell 建立保留原則</span><span class="sxs-lookup"><span data-stu-id="538e1-183">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="538e1-184">執行下列命令，為保留信箱建立新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="538e1-184">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="538e1-185">例如，下列命令會建立上圖所顯示的保留原則及連結的保留標記。</span><span class="sxs-lookup"><span data-stu-id="538e1-185">For example, the following command creates the retention policy and linked retention tags that are displayed in the previous illustration.</span></span>
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="538e1-186">步驟3：將新的 Exchange 保留原則套用至保留信箱</span><span class="sxs-lookup"><span data-stu-id="538e1-186">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>

<span data-ttu-id="538e1-187">最後一個步驟是將您在步驟2中建立的新保留原則套用至組織中的信箱保留原則。</span><span class="sxs-lookup"><span data-stu-id="538e1-187">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="538e1-188">您可以使用 EAC 或 Exchange Online PowerShell 將保留原則套用至單一信箱或多個信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-188">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="538e1-189">使用 EAC 來套用新的保留原則</span><span class="sxs-lookup"><span data-stu-id="538e1-189">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="538e1-190">移至 **[** 收件者] [  >  **信箱**]。</span><span class="sxs-lookup"><span data-stu-id="538e1-190">Go to **Recipients** > **Mailboxes**.</span></span>
    
2. <span data-ttu-id="538e1-191">在清單視圖中，選取您要套用保留原則的信箱，然後按一下 [ **編輯** ![ 編輯圖示] ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="538e1-191">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="538e1-192">在 [ **使用者信箱** ] 頁面上，按一下 [ **信箱功能**]。</span><span class="sxs-lookup"><span data-stu-id="538e1-192">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="538e1-193">在 [ **保留原則**] 底下，選取您在步驟2中建立的保留原則，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="538e1-193">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="538e1-194">您也可以使用 EAC 將保留原則套用至多個信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-194">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="538e1-195">移至 **[** 收件者] [  >  **信箱**]。</span><span class="sxs-lookup"><span data-stu-id="538e1-195">Go to **Recipients** > **Mailboxes**.</span></span>
    
2. <span data-ttu-id="538e1-196">在清單檢視中，使用 Shift 鍵或 Ctrl 鍵來選取多個信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-196">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="538e1-197">在詳細資料窗格中，按一下 [其他選項]。</span><span class="sxs-lookup"><span data-stu-id="538e1-197">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="538e1-198">在 [保留原則] 下方，按一下 [更新]。</span><span class="sxs-lookup"><span data-stu-id="538e1-198">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="538e1-199">在 [ **大量指派保留原則** ] 頁面上，選取您在步驟2中建立的保留原則，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="538e1-199">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="538e1-200">使用 Exchange Online PowerShell 套用新的保留原則</span><span class="sxs-lookup"><span data-stu-id="538e1-200">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="538e1-201">您可以使用 Exchange Online PowerShell 將新的保留原則套用至單一信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-201">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="538e1-202">不過 PowerShell 的實際威力在於，您可以使用它來快速識別您組織中的所有信箱，不論是訴訟暫止或 In-Place 保留，然後在單一命令中將新的保留原則套用至保留的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-202">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="538e1-203">以下是一些使用 Exchange PowerShell 將保留原則套用至一或多個信箱的範例。</span><span class="sxs-lookup"><span data-stu-id="538e1-203">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="538e1-204">所有範例會套用在步驟2中建立的保留原則。</span><span class="sxs-lookup"><span data-stu-id="538e1-204">All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="538e1-205">此範例會將新的保留原則套用至 Pilar Pinilla 的信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-205">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="538e1-206">本範例會將新的保留原則套用至組織中的所有處於訴訟暫止狀態的信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-206">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="538e1-207">本範例會將新的保留原則套用至組織中 In-Place 保留的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-207">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="538e1-208">您可以使用 **Get-Mailbox** Cmdlet 來驗證是否已套用新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="538e1-208">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="538e1-209">以下是一些範例，以驗證先前範例中的命令是否已將「保留信箱的 MRM 原則」保留原則套用至「In-Place 暫止」上的「訴訟暫止」和信箱上的信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-209">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="538e1-210"> (選用) 步驟4：執行受管理的資料夾助理以套用新的保留設定</span><span class="sxs-lookup"><span data-stu-id="538e1-210">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="538e1-211">將新的 Exchange 保留原則套用至保留信箱之後，您可以在 Exchange Online 中長達7天使用新保留原則中的設定來處理這些信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-211">After you apply the new Exchange retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="538e1-212">您可以使用 **Start-ManagedFolderAssistant** Cmdlet 手動觸發助理，以處理套用新保留原則的信箱，而不是等待受管理的資料夾助理執行。</span><span class="sxs-lookup"><span data-stu-id="538e1-212">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="538e1-213">執行下列命令，以啟動 Pilar Pinilla 信箱的受管理的資料夾助理。</span><span class="sxs-lookup"><span data-stu-id="538e1-213">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="538e1-214">執行下列命令，以啟動保留所有信箱的受管理的資料夾助理。</span><span class="sxs-lookup"><span data-stu-id="538e1-214">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="538e1-215">其他資訊</span><span class="sxs-lookup"><span data-stu-id="538e1-215">More information</span></span>

- <span data-ttu-id="538e1-216">在您啟用使用者的封存信箱之後，請考慮告知使用者其信箱中的其他專案 (不只是「可復原的專案」資料夾中的專案) 可能會移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-216">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="538e1-217">這是因為指派給 Exchange Online 信箱的預設 MRM 原則所包含的保留標記 (名為 Default 2 年移至封存) 會在專案傳遞至信箱或使用者建立的日期之後的兩年後，將專案移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="538e1-217">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="538e1-218">如需詳細資訊，請參閱 [Exchange Online 中的預設保留原則 ](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)</span><span class="sxs-lookup"><span data-stu-id="538e1-218">For more information, see [Default Retention Policy in Exchange Online ](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)</span></span>
    
- <span data-ttu-id="538e1-219">啟用使用者的封存信箱之後，您可能也會告訴使用者他們可以在其封存信箱的 [可復原的專案] 資料夾中復原已刪除的郵件。</span><span class="sxs-lookup"><span data-stu-id="538e1-219">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="538e1-220">在 Outlook 中，您可以選取封存信箱中的 [**刪除的郵件**] 資料夾，然後按一下 [從 **首頁**] 索引標籤上的 [**從伺服器復原刪除的郵件**] 來執行此動作。如需復原已刪除專案的詳細資訊，請參閱 [在 Outlook For Windows 中復原已刪除的郵件](https://go.microsoft.com/fwlink/p/?LinkId=624829)。</span><span class="sxs-lookup"><span data-stu-id="538e1-220">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span>