---
title: 還原非作用中的信箱
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
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 瞭解如何還原 (或合併) 非使用中信箱的內容至 Office 365 中的現有信箱。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bc9039d21f76affce7f58f1f83597dd9e5eb4ecf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917297"
---
# <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="0f13a-103">還原非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="0f13a-103">Restore an inactive mailbox</span></span>

<span data-ttu-id="0f13a-104">非使用中的信箱 (是一種虛刪除的信箱) ，用來在離開組織之後保留離職員工的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0f13a-104">An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="0f13a-105">如果另一位員工承擔已離開員工的工作責任，或是該員工回到您的組織，有兩種方式可以讓使用者使用非使用中信箱的內容：</span><span class="sxs-lookup"><span data-stu-id="0f13a-105">If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span>

- <span data-ttu-id="0f13a-106">**還原非使用中的信箱** 如果另一位員工承擔已離開員工的工作責任，或是其他使用者需要存取非使用中信箱的內容，您可以還原 (或合併) 非使用中信箱的內容到現有的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-106">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="0f13a-107">您也可以從非使用中的信箱還原封存。</span><span class="sxs-lookup"><span data-stu-id="0f13a-107">You can also restore the archive from an inactive mailbox.</span></span> <span data-ttu-id="0f13a-108">還原後，非作用中的信箱會保留並保留為非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-108">After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox.</span></span> <span data-ttu-id="0f13a-109">本主題說明還原非使用中信箱的程式。</span><span class="sxs-lookup"><span data-stu-id="0f13a-109">This topic describes the procedures for restoring an inactive mailbox.</span></span>

- <span data-ttu-id="0f13a-110">**復原非使用中的信箱** 如果已離開員工回到您的組織，或是聘用新的員工來承擔已離開員工的工作責任，您可以復原非使用中信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="0f13a-110">**Recover an inactive mailbox** If the departed employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox.</span></span> <span data-ttu-id="0f13a-111">這個方法會將非使用中的信箱轉換成包含非使用中信箱內容的新信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-111">This method converts the inactive mailbox to a new mailbox that contains the contents of the inactive mailbox.</span></span> <span data-ttu-id="0f13a-112">它會復原之後，非使用中的信箱不存在。</span><span class="sxs-lookup"><span data-stu-id="0f13a-112">After it's recovered, the inactive mailbox no longer exists.</span></span> <span data-ttu-id="0f13a-113">如需逐步程式，請參閱[復原 Office 365 中的非使用中信箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="0f13a-113">For the step-by-step procedures, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

<span data-ttu-id="0f13a-114">如需還原和復原非使用中信箱之差異的詳細資訊，請參閱本文中的 [詳細資訊](#more-information) 一節。</span><span class="sxs-lookup"><span data-stu-id="0f13a-114">See the [More information](#more-information) section in this article for more details about the differences between restoring and recovering an inactive mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="0f13a-115">您無法復原或還原已設定為自動展開封存的非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-115">You can't recover or restore an inactive mailbox that's configured with an auto-expanding archive.</span></span> <span data-ttu-id="0f13a-116">如果您需要從自動展開封存的非使用中信箱復原資料，請使用內容搜尋來匯出信箱中的資料，然後匯入至另一個信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-116">If you need to recover data from an inactive mailbox with an auto-expanding archive, use content search to export the data from the mailbox and then import to another mailbox.</span></span> <span data-ttu-id="0f13a-117">如需相關指示，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="0f13a-117">For instructions, see following topics:</span></span>
>
> - [<span data-ttu-id="0f13a-118">內容搜尋</span><span class="sxs-lookup"><span data-stu-id="0f13a-118">Content search</span></span>](content-search.md)
> - [<span data-ttu-id="0f13a-119">匯出內容搜尋結果</span><span class="sxs-lookup"><span data-stu-id="0f13a-119">Export content search results</span></span>](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a><span data-ttu-id="0f13a-120">還原非使用中信箱的需求</span><span class="sxs-lookup"><span data-stu-id="0f13a-120">Requirements to restore an inactive mailbox</span></span>

- <span data-ttu-id="0f13a-121">您必須使用 Exchange Online PowerShell 還原非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-121">You have to use Exchange Online PowerShell to restore an inactive mailbox.</span></span> <span data-ttu-id="0f13a-122">您無法使用 Exchange 系統管理中心 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="0f13a-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="0f13a-123">如需逐步指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0f13a-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0f13a-124">在 Exchange Online PowerShell 中執行下列命令，以取得組織中非使用中信箱的身分識別資訊。</span><span class="sxs-lookup"><span data-stu-id="0f13a-124">Run the following command in Exchange Online PowerShell to get identity information for the inactive mailboxes in your organization.</span></span>

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  <span data-ttu-id="0f13a-125">使用由此命令傳回的資訊，還原特定的非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-125">Use the information returned by this command to restore a specific inactive mailbox.</span></span>

- <span data-ttu-id="0f13a-126">如需非使用中信箱的相關資訊，請參閱[Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="0f13a-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="restore-inactive-mailboxes"></a><span data-ttu-id="0f13a-127">還原非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="0f13a-127">Restore inactive mailboxes</span></span>

<span data-ttu-id="0f13a-128">使用 **New-MailboxRestoreRequest** Cmdlet 搭配  _SourceMailbox_ 及  _TargetMailbox_ 參數，將非使用中信箱的內容還原到現有信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-128">Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="0f13a-129">如需使用此 Cmdlet 的詳細資訊，請參閱 [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest)。</span><span class="sxs-lookup"><span data-stu-id="0f13a-129">For more information about using this cmdlet, see [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest).</span></span>

1. <span data-ttu-id="0f13a-130">建立包含非使用中信箱之屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="0f13a-130">Create a variable that contains the properties of the inactive mailbox.</span></span>

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="0f13a-131">在上述命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 屬性的值來識別非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-131">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox.</span></span> <span data-ttu-id="0f13a-132">這兩個屬性對於組織中的每個信箱都是唯一的，而使用中和非使用中的信箱可能會有相同的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="0f13a-132">These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span>

2. <span data-ttu-id="0f13a-133">將非使用中信箱的內容還原到現有的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-133">Restore the contents of the inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="0f13a-134">非使用中信箱的內容 (來源信箱) 會合並至現有信箱 (目標信箱) 中的對應資料夾。</span><span class="sxs-lookup"><span data-stu-id="0f13a-134">The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
   ```

   <span data-ttu-id="0f13a-135">或者，您也可以指定要從非使用中的信箱還原內容之目標信箱中的最上層資料夾。</span><span class="sxs-lookup"><span data-stu-id="0f13a-135">Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox.</span></span> <span data-ttu-id="0f13a-136">如果指定的目的檔案夾或目的檔案夾結構尚未存在於目標信箱中，則會在還原程式期間建立。</span><span class="sxs-lookup"><span data-stu-id="0f13a-136">If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process.</span></span>

   <span data-ttu-id="0f13a-137">此範例會將非使用中信箱的信箱專案及子資料夾，複製到目標信箱的最上層資料夾結構中名為 "非使用中信箱" 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="0f13a-137">This example copies mailbox items and subfolders from an inactive mailbox to a folder named "Inactive Mailbox" in the top-level folder structure of the target mailbox.</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a><span data-ttu-id="0f13a-138">從非使用中的信箱還原封存</span><span class="sxs-lookup"><span data-stu-id="0f13a-138">Restore the archive from an inactive mailbox</span></span>

<span data-ttu-id="0f13a-139">如果非使用中的信箱具有封存信箱，您也可以將它還原到現有信箱的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-139">If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox.</span></span> <span data-ttu-id="0f13a-140">若要從非使用中的信箱還原封存，您必須新增 _SourceIsArchive_ 和 _TargetIsArchive_ 切換至用來還原非使用中信箱的命令。</span><span class="sxs-lookup"><span data-stu-id="0f13a-140">To restore the archive from an inactive mailbox, you have to add the _SourceIsArchive_ and _TargetIsArchive_ switches to the command used to restore an inactive mailbox.</span></span>

1. <span data-ttu-id="0f13a-141">建立包含非使用中信箱之屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="0f13a-141">Create a variable that contains the properties of the inactive mailbox.</span></span>

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > <span data-ttu-id="0f13a-142">在上述命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 屬性的值來識別非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-142">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox.</span></span> <span data-ttu-id="0f13a-143">這兩個屬性對於組織中的每個信箱都是唯一的，而使用中和非使用中的信箱可能會有相同的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="0f13a-143">These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span>

2. <span data-ttu-id="0f13a-144">將封存的內容從非使用中的信箱還原到現有信箱的封存 (來源封存)  (目標封存) 。</span><span class="sxs-lookup"><span data-stu-id="0f13a-144">Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive).</span></span> <span data-ttu-id="0f13a-145">在此範例中，會將來源封存的內容複寫到目標信箱的封存中名為「非使用中信箱封存」的資料夾。</span><span class="sxs-lookup"><span data-stu-id="0f13a-145">In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
   ```

## <a name="more-information"></a><span data-ttu-id="0f13a-146">其他資訊</span><span class="sxs-lookup"><span data-stu-id="0f13a-146">More information</span></span>

- <span data-ttu-id="0f13a-147">**復原和還原非使用中信箱的主要差異為何？**</span><span class="sxs-lookup"><span data-stu-id="0f13a-147">**What's the main difference between recovering and restoring an inactive mailbox?**</span></span> <span data-ttu-id="0f13a-148">當您復原非使用中的信箱時，信箱基本上會轉換為新的信箱、非使用中信箱的內容和資料夾結構會保留，而且信箱會連結至新的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="0f13a-148">When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account.</span></span> <span data-ttu-id="0f13a-149">復原之後，非使用中的信箱不再存在，對新信箱中的內容所做的任何變更，都會影響原始在非使用中信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="0f13a-149">After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox.</span></span> <span data-ttu-id="0f13a-150">相反地，當您還原非使用中的信箱時，內容只會複製到另一個信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-150">Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox.</span></span> <span data-ttu-id="0f13a-151">非使用中的信箱會保留並保持非作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-151">The inactive mailbox is preserved and remains an inactive mailbox.</span></span> <span data-ttu-id="0f13a-152">對目標信箱中的內容所做的任何變更，都不會影響保留在非使用中信箱的原始內容。</span><span class="sxs-lookup"><span data-stu-id="0f13a-152">Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox.</span></span> <span data-ttu-id="0f13a-153">使用 [內容搜尋工具](content-search.md)仍可搜尋非使用中的信箱，其內容可以還原至另一個信箱，也可以在日後復原或刪除。</span><span class="sxs-lookup"><span data-stu-id="0f13a-153">The inactive mailbox can still be searched by using the [Content Search tool](content-search.md), its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span>

- <span data-ttu-id="0f13a-154">**如何找到非作用中的信箱？**</span><span class="sxs-lookup"><span data-stu-id="0f13a-154">**How do you find inactive mailboxes?**</span></span> <span data-ttu-id="0f13a-155">若要取得組織中非使用中信箱的清單，並顯示還原非使用中信箱的有用資訊，您可以執行此命令。</span><span class="sxs-lookup"><span data-stu-id="0f13a-155">To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.</span></span>

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- <span data-ttu-id="0f13a-156">**使用訴訟暫止或 Microsoft 365 保留原則，保留非使用中的信箱內容。**</span><span class="sxs-lookup"><span data-stu-id="0f13a-156">**Use a Litigation Hold or Microsoft 365 retention policy to retain inactive mailbox content.**</span></span> <span data-ttu-id="0f13a-157">如果您想要在還原非使用中的信箱時保留其狀態，您可以將目標信箱設定為[訴訟暫](create-a-litigation-hold.md)止，或套用[Microsoft 365 保留原則](retention.md)，再還原非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-157">If you want to retain the state of an inactive mailbox after it's restored, you can place the target mailbox on [Litigation Hold](create-a-litigation-hold.md) or apply an [Microsoft 365 retention policy](retention.md) before you restore the inactive mailbox.</span></span> <span data-ttu-id="0f13a-158">這會在還原至目標信箱後，避免永久刪除非作用中信箱中的任何專案。</span><span class="sxs-lookup"><span data-stu-id="0f13a-158">This will prevent the permanent deletion of any items from the inactive mailbox after they're restored to the target mailbox.</span></span>

- <span data-ttu-id="0f13a-159">**在還原非使用中的信箱之前，請先在目標信箱上啟用保留功能。**</span><span class="sxs-lookup"><span data-stu-id="0f13a-159">**Enable retention hold on the target mailbox before you restore an inactive mailbox.**</span></span> <span data-ttu-id="0f13a-160">由於非使用中信箱的信箱專案可能是舊的，因此您可以考慮在還原非使用中的信箱之前，先在目標信箱上啟用保留功能。</span><span class="sxs-lookup"><span data-stu-id="0f13a-160">Because mailbox items from an inactive mailbox could be old, you might consider enabling retention hold on the target mailbox before you restore an inactive mailbox.</span></span> <span data-ttu-id="0f13a-161">當您將信箱設為保留狀態時，將不會處理指派給它的保留原則，除非已移除保留狀態，或保留期間到期。</span><span class="sxs-lookup"><span data-stu-id="0f13a-161">When you put a mailbox on retention hold, the retention policy that's assigned to it won't be processed until the retention hold is removed or until the retention hold period expires.</span></span> <span data-ttu-id="0f13a-162">這可讓目標信箱的擁有者管理非使用中信箱的舊郵件。</span><span class="sxs-lookup"><span data-stu-id="0f13a-162">This gives the owner of the target mailbox time to manage old messages from the inactive mailbox.</span></span> <span data-ttu-id="0f13a-163">否則，保留原則可能會刪除舊專案 (或將專案移至封存信箱（如果已啟用，則會根據為目標信箱設定的保留設定）已到期) 。</span><span class="sxs-lookup"><span data-stu-id="0f13a-163">Otherwise, the retention policy might delete old items (or move items to the archive mailbox, if it's enabled) that have expired based on the retention settings configured for the target mailbox.</span></span> <span data-ttu-id="0f13a-164">如需詳細資訊，請參閱[在 Exchange Online 中將信箱設為保留狀態](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)。</span><span class="sxs-lookup"><span data-stu-id="0f13a-164">For more information, see [Place a mailbox on retention hold in Exchange Online](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).</span></span>

- <span data-ttu-id="0f13a-165">**AllowLegacyDNMismatch 參數會執行什麼動作？**</span><span class="sxs-lookup"><span data-stu-id="0f13a-165">**What does the AllowLegacyDNMismatch switch do?**</span></span> <span data-ttu-id="0f13a-166">在上述範例中，若要還原非使用中的信箱， **AllowLegacyDNMismatch** 參數會用於允許將非使用中的信箱還原至不同的目標信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-166">In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox.</span></span> <span data-ttu-id="0f13a-167">在一般還原案例中，目標是還原來源與目標信箱相同信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="0f13a-167">In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox.</span></span> <span data-ttu-id="0f13a-168">所以根據預設， **New-MailboxRestoreRequest** 指令程式會檢查，以確保來源和目標信箱上 **LegacyExchangeDN** 屬性的值相同。</span><span class="sxs-lookup"><span data-stu-id="0f13a-168">So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same.</span></span> <span data-ttu-id="0f13a-169">這有助於防止您不小心將來源信箱還原至錯誤的目標信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-169">This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox.</span></span> <span data-ttu-id="0f13a-170">如果您嘗試在未使用 **AllowLegacyDNMismatch** 參數的情況下還原非使用中的信箱，當來源和目標信箱的 **LegacyExchangeDN** 屬性值不同時，此命令可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="0f13a-170">If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.</span></span>

- <span data-ttu-id="0f13a-171">**您可以搭配使用 New-MailboxRestoreRequest Cmdlet 的其他參數，針對非使用中的信箱執行不同的還原案例。**</span><span class="sxs-lookup"><span data-stu-id="0f13a-171">**You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.**</span></span> <span data-ttu-id="0f13a-172">例如，您可以執行此命令，將非使用中信箱的封存還原至目標信箱的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="0f13a-172">For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox.</span></span>

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  <span data-ttu-id="0f13a-173">您也可以執行下列命令，將非使用中的主要信箱還原到目標信箱的封存中。</span><span class="sxs-lookup"><span data-stu-id="0f13a-173">You can also restore the inactive primary mailbox into the archive of the target mailbox by running this command.</span></span>

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- <span data-ttu-id="0f13a-174">**TargetRootFolder 參數的功能為何？**</span><span class="sxs-lookup"><span data-stu-id="0f13a-174">**What does the TargetRootFolder parameter do?**</span></span> <span data-ttu-id="0f13a-175">如先前所述，您可以使用 **TargetRootFolder** 參數來指定資料夾結構頂端的資料夾 (也稱為根) 的目標信箱中，以還原非使用中信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="0f13a-175">As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox.</span></span> <span data-ttu-id="0f13a-176">如果您未使用此參數，則非使用中信箱的信箱專案會合並至目標信箱的對應預設資料夾，而且會在目標信箱的根目錄中重新建立自訂資料夾。</span><span class="sxs-lookup"><span data-stu-id="0f13a-176">If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox.</span></span> <span data-ttu-id="0f13a-177">下列圖例會強調不使用和使用 **TargetRootFolder** 參數之間的差異。</span><span class="sxs-lookup"><span data-stu-id="0f13a-177">The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.</span></span>

  <span data-ttu-id="0f13a-178">**未使用 TargetRootFolder 參數時，目標信箱中的資料夾階層**</span><span class="sxs-lookup"><span data-stu-id="0f13a-178">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter isn't used**</span></span>

  ![未使用 TargetRootFolder 參數時的螢幕擷取畫面](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  <span data-ttu-id="0f13a-180">**使用 TargetRootFolder 參數時，目標信箱中的資料夾階層**</span><span class="sxs-lookup"><span data-stu-id="0f13a-180">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter is used**</span></span>

  ![使用 TargetRootFolder 參數時的螢幕擷取畫面](../media/300da592-7323-48db-b8a4-07012259d113.png)