---
title: 還原非作用中的信箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 如果新的員工或其他使用者需要存取 Office 365 中非使用中信箱的內容，您可以將非使用中信箱的內容還原（或合併）到現有的信箱。
ms.openlocfilehash: 3352dfa582fb09a5f0a6c7ecbd807ed80593351f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621315"
---
# <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="32316-103">還原非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="32316-103">Restore an inactive mailbox</span></span>

<span data-ttu-id="32316-104">非使用中的信箱（也就是虛刪除信箱的類型）是用來在離開組織之後，保留離職員工的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="32316-104">An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="32316-105">如果另一位員工承擔已離開員工的工作責任，或是該員工回到您的組織，有兩種方式可以讓使用者使用非使用中信箱的內容：</span><span class="sxs-lookup"><span data-stu-id="32316-105">If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span>
  
- <span data-ttu-id="32316-106">**還原非使用中的信箱**如果另一位員工承擔已離開員工的工作責任，或是其他使用者必須存取非使用中信箱的內容，您可以將非使用中信箱的內容還原（或合併）到現有的信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-106">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="32316-107">您也可以從非使用中的信箱還原封存。</span><span class="sxs-lookup"><span data-stu-id="32316-107">You can also restore the archive from an inactive mailbox.</span></span> <span data-ttu-id="32316-108">還原後，非作用中的信箱會保留並保留為非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-108">After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox.</span></span> <span data-ttu-id="32316-109">本主題說明還原非使用中信箱的程式。</span><span class="sxs-lookup"><span data-stu-id="32316-109">This topic describes the procedures for restoring an inactive mailbox.</span></span>

- <span data-ttu-id="32316-110">**復原非使用中的信箱**如果已離開員工回到您的組織，或是聘用新的員工來承擔已離開員工的工作責任，您可以復原非使用中信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="32316-110">**Recover an inactive mailbox** If the departed employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox.</span></span> <span data-ttu-id="32316-111">這個方法會將非使用中的信箱轉換成包含非使用中信箱內容的新信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-111">This method converts the inactive mailbox to a new mailbox that contains the contents of the inactive mailbox.</span></span> <span data-ttu-id="32316-112">它會復原之後，非使用中的信箱不存在。</span><span class="sxs-lookup"><span data-stu-id="32316-112">After it's recovered, the inactive mailbox no longer exists.</span></span> <span data-ttu-id="32316-113">如需逐步程式，請參閱[復原 Office 365 中的非使用中信箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="32316-113">For the step-by-step procedures, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

<span data-ttu-id="32316-114">如需還原和復原非使用中信箱之差異的詳細資訊，請參閱本文中的**詳細資訊**一節。</span><span class="sxs-lookup"><span data-stu-id="32316-114">See the **More information** section in this article for more details about the differences between restoring and recovering an inactive mailbox.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="32316-115">開始之前</span><span class="sxs-lookup"><span data-stu-id="32316-115">Before you begin</span></span>

- <span data-ttu-id="32316-116">您必須使用 Exchange Online PowerShell 還原非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-116">You have to use Exchange Online PowerShell to restore an inactive mailbox.</span></span> <span data-ttu-id="32316-117">您無法使用 Exchange 系統管理中心（EAC）。</span><span class="sxs-lookup"><span data-stu-id="32316-117">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="32316-118">如需逐步指示，請參閱[Connect To Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="32316-118">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>

- <span data-ttu-id="32316-119">在 Exchange Online PowerShell 中執行下列命令，以取得組織中非使用中信箱的身分識別資訊。</span><span class="sxs-lookup"><span data-stu-id="32316-119">Run the following command in Exchange Online PowerShell to get identity information for the inactive mailboxes in your organization.</span></span>

    ```powershell
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     <span data-ttu-id="32316-120">使用由此命令傳回的資訊，還原特定的非使用中信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-120">Use the information returned by this command to restore a specific inactive mailbox.</span></span>

- <span data-ttu-id="32316-121">如需非使用中信箱的相關資訊，請參閱[Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="32316-121">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="32316-122">還原非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="32316-122">Restore an inactive mailbox</span></span>

<span data-ttu-id="32316-123">使用**New-MailboxRestoreRequest** Cmdlet 搭配_SourceMailbox_及_TargetMailbox_參數，將非使用中信箱的內容還原到現有信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-123">Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="32316-124">如需使用此 Cmdlet 的詳細資訊，請參閱[New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298)。</span><span class="sxs-lookup"><span data-stu-id="32316-124">For more information about using this cmdlet, see [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).</span></span>
  
1. <span data-ttu-id="32316-125">建立包含非使用中信箱之屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="32316-125">Create a variable that contains the properties of the inactive mailbox.</span></span>

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="32316-126">在上述命令中，使用**DistinguishedName**或**ExchangeGUID**屬性的值來識別非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-126">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox.</span></span> <span data-ttu-id="32316-127">這兩個屬性對於組織中的每個信箱都是唯一的，而使用中和非使用中的信箱可能會有相同的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="32316-127">These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span>
  
2. <span data-ttu-id="32316-128">將非使用中信箱的內容還原到現有的信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-128">Restore the contents of the inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="32316-129">非使用中信箱的內容（來源信箱）將會合並至現有信箱中的對應資料夾（目標信箱）。</span><span class="sxs-lookup"><span data-stu-id="32316-129">The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).</span></span>

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```

   <span data-ttu-id="32316-130">或者，您也可以指定要從非使用中的信箱還原內容之目標信箱中的最上層資料夾。</span><span class="sxs-lookup"><span data-stu-id="32316-130">Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox.</span></span> <span data-ttu-id="32316-131">如果指定的目的檔案夾或目的檔案夾結構尚未存在於目標信箱中，則會在還原程式期間建立。</span><span class="sxs-lookup"><span data-stu-id="32316-131">If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process.</span></span> 

    <span data-ttu-id="32316-132">此範例會將非使用中信箱的信箱專案及子資料夾，複製到目標信箱的最上層資料夾結構中名為 "非使用中信箱" 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="32316-132">This example copies mailbox items and subfolders from an inactive mailbox to a folder named "Inactive Mailbox" in the top-level folder structure of the target mailbox.</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a><span data-ttu-id="32316-133">從非使用中的信箱還原封存</span><span class="sxs-lookup"><span data-stu-id="32316-133">Restore the archive from an inactive mailbox</span></span>

<span data-ttu-id="32316-134">如果非使用中的信箱具有封存信箱，您也可以將它還原到現有信箱的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-134">If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox.</span></span> <span data-ttu-id="32316-135">若要從非使用中的信箱還原封存，您必須新增_SourceIsArchive_及_TargetIsAchive_切換至用來還原非使用中信箱的命令。</span><span class="sxs-lookup"><span data-stu-id="32316-135">To restore the archive from an inactive mailbox, you have to add the  _SourceIsArchive_ and  _TargetIsAchive_ switches to the command used to restore an inactive mailbox.</span></span>
  
1. <span data-ttu-id="32316-136">建立包含非使用中信箱之屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="32316-136">Create a variable that contains the properties of the inactive mailbox.</span></span>

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!NOTE]
    > <span data-ttu-id="32316-137">在上述命令中，使用**DistinguishedName**或**ExchangeGUID**屬性的值來識別非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-137">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox.</span></span> <span data-ttu-id="32316-138">這兩個屬性對於組織中的每個信箱都是唯一的，而使用中和非使用中的信箱可能會有相同的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="32316-138">These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="32316-139">將封存的內容從非作用中的信箱（來源封存）還原至現有信箱的封存（目標封存）。</span><span class="sxs-lookup"><span data-stu-id="32316-139">Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive).</span></span> <span data-ttu-id="32316-140">在此範例中，會將來源封存的內容複寫到目標信箱的封存中名為「非使用中信箱封存」的資料夾。</span><span class="sxs-lookup"><span data-stu-id="32316-140">In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.</span></span>

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

## <a name="more-information"></a><span data-ttu-id="32316-141">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="32316-141">More information</span></span>

- <span data-ttu-id="32316-142">**復原和還原非使用中信箱的主要差異為何？**</span><span class="sxs-lookup"><span data-stu-id="32316-142">**What's the main difference between recovering and restoring an inactive mailbox?**</span></span> <span data-ttu-id="32316-143">當您復原非使用中的信箱時，信箱基本上會轉換為新的信箱、非使用中信箱的內容和資料夾結構會保留，而且信箱會連結至新的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="32316-143">When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account.</span></span> <span data-ttu-id="32316-144">復原之後，非使用中的信箱不再存在，對新信箱中的內容所做的任何變更，都會影響原始在非使用中信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="32316-144">After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox.</span></span> <span data-ttu-id="32316-145">相反地，當您還原非使用中的信箱時，內容只會複製到另一個信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-145">Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox.</span></span> <span data-ttu-id="32316-146">非使用中的信箱會保留並保持非作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-146">The inactive mailbox is preserved and remains an inactive mailbox.</span></span> <span data-ttu-id="32316-147">對目標信箱中的內容所做的任何變更，都不會影響保留在非使用中信箱的原始內容。</span><span class="sxs-lookup"><span data-stu-id="32316-147">Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox.</span></span> <span data-ttu-id="32316-148">使用[內容搜尋工具](content-search.md)仍可搜尋非使用中的信箱，其內容可以還原至另一個信箱，也可以在日後復原或刪除。</span><span class="sxs-lookup"><span data-stu-id="32316-148">The inactive mailbox can still be searched by using the [Content Search tool](content-search.md), its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span>

- <span data-ttu-id="32316-149">**如何找到非作用中的信箱？**</span><span class="sxs-lookup"><span data-stu-id="32316-149">**How do you find inactive mailboxes?**</span></span> <span data-ttu-id="32316-150">若要取得組織中非使用中信箱的清單，並顯示還原非使用中信箱的有用資訊，您可以執行此命令。</span><span class="sxs-lookup"><span data-stu-id="32316-150">To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.</span></span>

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- <span data-ttu-id="32316-151">**使用訴訟暫止或 Microsoft 365 保留原則，保留非使用中的信箱內容。**</span><span class="sxs-lookup"><span data-stu-id="32316-151">**Use a Litigation Hold or Microsoft 365 retention policy to retain inactive mailbox content.**</span></span> <span data-ttu-id="32316-152">如果您想要在還原非使用中的信箱時保留其狀態，您可以將目標信箱設定為[訴訟暫](https://go.microsoft.com/fwlink/?linkid=856286)止，或套用[Microsoft 365 保留原則](retention-policies.md)，再還原非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-152">If you want to retain the state of an inactive mailbox after it's restored, you can place the target mailbox on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) or apply an [Microsoft 365 retention policy](retention-policies.md) before you restore the inactive mailbox.</span></span> <span data-ttu-id="32316-153">這會在還原至目標信箱後，避免永久刪除非作用中信箱中的任何專案。</span><span class="sxs-lookup"><span data-stu-id="32316-153">This will prevent the permanent deletion of any items from the inactive mailbox after they're restored to the target mailbox.</span></span>

- <span data-ttu-id="32316-154">**在還原非使用中的信箱之前，請先在目標信箱上啟用保留功能。**</span><span class="sxs-lookup"><span data-stu-id="32316-154">**Enable retention hold on the target mailbox before you restore an inactive mailbox.**</span></span> <span data-ttu-id="32316-155">由於非使用中信箱的信箱專案可能是舊的，因此您可以考慮在還原非使用中的信箱之前，先在目標信箱上啟用保留功能。</span><span class="sxs-lookup"><span data-stu-id="32316-155">Because mailbox items from an inactive mailbox could be old, you might consider enabling retention hold on the target mailbox before you restore an inactive mailbox.</span></span> <span data-ttu-id="32316-156">當您將信箱設為保留狀態時，將不會處理指派給它的保留原則，除非已移除保留狀態，或保留期間到期。</span><span class="sxs-lookup"><span data-stu-id="32316-156">When you put a mailbox on retention hold, the retention policy that's assigned to it won't be processed until the retention hold is removed or until the retention hold period expires.</span></span> <span data-ttu-id="32316-157">這可讓目標信箱的擁有者管理非使用中信箱的舊郵件。</span><span class="sxs-lookup"><span data-stu-id="32316-157">This gives the owner of the target mailbox time to manage old messages from the inactive mailbox.</span></span> <span data-ttu-id="32316-158">否則，保留原則可能會刪除舊專案（或將專案移至封存信箱（如果已啟用），該信箱會根據針對目標信箱設定的保留設定而到期。</span><span class="sxs-lookup"><span data-stu-id="32316-158">Otherwise, the retention policy might delete old items (or move items to the archive mailbox, if it's enabled) that have expired based on the retention settings configured for the target mailbox.</span></span> <span data-ttu-id="32316-159">如需詳細資訊，請參閱在[Exchange Online 中將信箱設為保留狀態](https://go.microsoft.com/fwlink/?linkid=856300)。</span><span class="sxs-lookup"><span data-stu-id="32316-159">For more information, see [Place a mailbox on retention hold in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).</span></span>

- <span data-ttu-id="32316-160">**AllowLegacyDNMismatch 參數會執行什麼動作？**</span><span class="sxs-lookup"><span data-stu-id="32316-160">**What does the AllowLegacyDNMismatch switch do?**</span></span> <span data-ttu-id="32316-161">在上述範例中，若要還原非使用中的信箱， **AllowLegacyDNMismatch**參數會用於允許將非使用中的信箱還原至不同的目標信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-161">In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox.</span></span> <span data-ttu-id="32316-162">在一般還原案例中，目標是還原來源與目標信箱相同信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="32316-162">In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox.</span></span> <span data-ttu-id="32316-163">所以根據預設， **New-MailboxRestoreRequest**指令程式會檢查，以確保來源和目標信箱上**LegacyExchangeDN**屬性的值相同。</span><span class="sxs-lookup"><span data-stu-id="32316-163">So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same.</span></span> <span data-ttu-id="32316-164">這有助於防止您不小心將來源信箱還原至錯誤的目標信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-164">This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox.</span></span> <span data-ttu-id="32316-165">如果您嘗試在未使用**AllowLegacyDNMismatch**參數的情況下還原非使用中的信箱，當來源和目標信箱的**LegacyExchangeDN**屬性值不同時，此命令可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="32316-165">If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.</span></span>

- <span data-ttu-id="32316-166">**您可以搭配使用 New-MailboxRestoreRequest Cmdlet 的其他參數，針對非使用中的信箱執行不同的還原案例。**</span><span class="sxs-lookup"><span data-stu-id="32316-166">**You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.**</span></span> <span data-ttu-id="32316-167">例如，您可以執行此命令，將非使用中信箱的封存還原至目標信箱的主要信箱。</span><span class="sxs-lookup"><span data-stu-id="32316-167">For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox.</span></span> 

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  <span data-ttu-id="32316-168">您也可以執行下列命令，將非使用中的主要信箱還原到目標信箱的封存中。</span><span class="sxs-lookup"><span data-stu-id="32316-168">You can also restore the inactive primary mailbox into the archive of the target mailbox by running this command.</span></span>

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- <span data-ttu-id="32316-169">**TargetRootFolder 參數的功能為何？**</span><span class="sxs-lookup"><span data-stu-id="32316-169">**What does the TargetRootFolder parameter do?**</span></span> <span data-ttu-id="32316-170">如先前所述，您可以使用**TargetRootFolder**參數來指定目標信箱中資料夾結構（也稱為根）頂端的資料夾，以還原非使用中信箱的內容。</span><span class="sxs-lookup"><span data-stu-id="32316-170">As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox.</span></span> <span data-ttu-id="32316-171">如果您未使用此參數，則非使用中信箱的信箱專案會合並至目標信箱的對應預設資料夾，而且會在目標信箱的根目錄中重新建立自訂資料夾。</span><span class="sxs-lookup"><span data-stu-id="32316-171">If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox.</span></span> <span data-ttu-id="32316-172">下列圖例會強調不使用和使用**TargetRootFolder**參數之間的差異。</span><span class="sxs-lookup"><span data-stu-id="32316-172">The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.</span></span>

    <span data-ttu-id="32316-173">**未使用 TargetRootFolder 參數時，目標信箱中的資料夾階層**</span><span class="sxs-lookup"><span data-stu-id="32316-173">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter isn't used**</span></span>

    ![未使用 TargetRootFolder 參數時的螢幕擷取畫面](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    <span data-ttu-id="32316-175">**使用 TargetRootFolder 參數時，目標信箱中的資料夾階層**</span><span class="sxs-lookup"><span data-stu-id="32316-175">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter is used**</span></span>

    ![使用 TargetRootFolder 參數時的螢幕擷取畫面](../media/300da592-7323-48db-b8a4-07012259d113.png)
