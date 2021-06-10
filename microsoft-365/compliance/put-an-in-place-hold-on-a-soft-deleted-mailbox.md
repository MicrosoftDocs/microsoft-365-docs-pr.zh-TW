---
title: 將虛刪除信箱上的 In-Place 保留 Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何為虛刪除的信箱建立 In-Place 保留，使其成為非使用中的信箱，並保留其內容。
ms.openlocfilehash: 4cca34ab2ca3a946245f34a9b0d898a07537a722
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925519"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="af023-103">將虛刪除信箱上的 In-Place 保留 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="af023-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="af023-104">瞭解如何為虛刪除的信箱建立 In-Place 保留，使其成為非使用中的信箱，並保留其內容。</span><span class="sxs-lookup"><span data-stu-id="af023-104">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="af023-105">然後，您可以使用 Microsoft eDiscovery 工具來搜尋非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="af023-105">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af023-106">當我們繼續以保留信箱內容的不同方式投資時，我們宣佈 Exchange 系統管理中心 (EAC) 停用 In-Place 的封存。</span><span class="sxs-lookup"><span data-stu-id="af023-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="af023-107">從2020年7月1日起，您將無法在 Exchange Online 中建立新的 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="af023-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="af023-108">不過，您仍然可以管理 EAC 中的 In-Place，或是使用 Exchange Online PowerShell 中的 **Set-MailboxSearch** Cmdlet 來管理。</span><span class="sxs-lookup"><span data-stu-id="af023-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="af023-109">不過，從2020年10月1日開始，您將無法管理 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="af023-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="af023-110">您只會在 EAC 中或使用 **Remove-MailboxSearch** Cmdlet 中移除它們。</span><span class="sxs-lookup"><span data-stu-id="af023-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="af023-111">如需停用 In-Place 保留的詳細資訊，請參閱 [舊版 eDiscovery tools 的退休](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="af023-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="af023-112">您可能會有這樣的情況：某人已離開您的組織，而且其對應的使用者帳戶和信箱已遭刪除。</span><span class="sxs-lookup"><span data-stu-id="af023-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="af023-113">之後，您就會發現信箱中的資訊必須保留。</span><span class="sxs-lookup"><span data-stu-id="af023-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="af023-114">您可以做什麼？</span><span class="sxs-lookup"><span data-stu-id="af023-114">What can you do?</span></span> <span data-ttu-id="af023-115">如果已刪除的信箱保留期間尚未到期，您可以將 In-Place 保留已刪除的信箱 (稱為虛刪除的信箱 ) ，並使其成為非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="af023-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="af023-116">非使用中的  *信箱*  會在使用者離開組織之後，用來保留離職員工的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="af023-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="af023-117">非使用中信箱的內容會保留在所做的 In-Place 保留期間內，在未使用中時，會將其放在虛刪除信箱上。</span><span class="sxs-lookup"><span data-stu-id="af023-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="af023-118">將信箱設為非作用中之後，您可以使用 Exchange Online 中的 In-Place eDiscovery、安全性 & 合規性中心的內容搜尋或是 SharePoint Online 中的 ediscovery 中心來搜尋信箱。</span><span class="sxs-lookup"><span data-stu-id="af023-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="af023-119">在 Exchange Online 中，虛刪除的信箱是已刪除但可在特定保留期間內復原的信箱。</span><span class="sxs-lookup"><span data-stu-id="af023-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="af023-120">在 Exchange Online 中虛刪除的信箱保留期間是30天。</span><span class="sxs-lookup"><span data-stu-id="af023-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="af023-121">這表示信箱可以復原 (，或在30天內) 被刪除，使非作用中的信箱得以復原。</span><span class="sxs-lookup"><span data-stu-id="af023-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="af023-122">30天后，虛刪除的信箱會標示為永久刪除，且無法復原或設為非使用中。</span><span class="sxs-lookup"><span data-stu-id="af023-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="af023-123">In-Place 保留的需求</span><span class="sxs-lookup"><span data-stu-id="af023-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="af023-124">您必須在 Windows PowerShell 中使用 **New-MailboxSearch** 指令程式，以在虛刪除的信箱上放置 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="af023-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="af023-125">您無法使用 Exchange 系統管理中心 (EAC) 或「SharePoint Online 中的 eDiscovery 中心」。</span><span class="sxs-lookup"><span data-stu-id="af023-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="af023-126">若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="af023-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="af023-127">執行下列命令，以取得組織中虛刪除信箱的身分識別資訊。</span><span class="sxs-lookup"><span data-stu-id="af023-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="af023-128">如需非使用中信箱的詳細資訊，請參閱[Office 365 中的非使用中信箱概覽](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="af023-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="af023-129">在虛刪除的信箱上放置 In-Place，使其成為非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="af023-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="af023-130">使用 **New-MailboxSearch** Cmdlet 將虛刪除的信箱設為非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="af023-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="af023-131">如需詳細資訊，請參閱 [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)。</span><span class="sxs-lookup"><span data-stu-id="af023-131">For more information, see [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).</span></span>
  
1. <span data-ttu-id="af023-132">建立包含虛刪除信箱之屬性的變數。</span><span class="sxs-lookup"><span data-stu-id="af023-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="af023-133">在上述命令中，使用 **DistinguishedName** 或 **ExchangeGuid** 屬性的值來識別虛刪除的信箱。</span><span class="sxs-lookup"><span data-stu-id="af023-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="af023-134">這兩個屬性對於您組織中的每個信箱都是唯一的，而使用中信箱和虛刪除的信箱可能會有相同的主要 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="af023-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="af023-135">建立 In-Place 保留並將它放在虛刪除的信箱。</span><span class="sxs-lookup"><span data-stu-id="af023-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="af023-136">在此範例中，不會指定保留期間。</span><span class="sxs-lookup"><span data-stu-id="af023-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="af023-137">這表示專案會無限期保留，或直到從非使用中的信箱移除保留為止。</span><span class="sxs-lookup"><span data-stu-id="af023-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="af023-138">您也可以在建立 In-Place 保留時，指定保留期間。</span><span class="sxs-lookup"><span data-stu-id="af023-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="af023-139">這個範例會將非使用中信箱的專案保留大約7年。</span><span class="sxs-lookup"><span data-stu-id="af023-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="af023-140">片刻之後，請執行下列其中一個命令，以確認虛刪除的信箱是非作用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="af023-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="af023-141">或者</span><span class="sxs-lookup"><span data-stu-id="af023-141">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="af023-142">其他資訊</span><span class="sxs-lookup"><span data-stu-id="af023-142">More information</span></span>

<span data-ttu-id="af023-143">在您將虛刪除的信箱變為非使用中信箱之後，您可以使用許多方式來管理信箱。</span><span class="sxs-lookup"><span data-stu-id="af023-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="af023-144">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="af023-144">For more information, see:</span></span>
  
- [<span data-ttu-id="af023-145">變更非使用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="af023-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="af023-146">復原非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="af023-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="af023-147">還原非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="af023-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="af023-148">移除保留) [以刪除非使用中的信箱](delete-an-inactive-mailbox.md) (</span><span class="sxs-lookup"><span data-stu-id="af023-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>