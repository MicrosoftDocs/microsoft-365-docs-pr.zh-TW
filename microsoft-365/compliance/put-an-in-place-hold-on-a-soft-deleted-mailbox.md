---
title: 在 Exchange 在线中对软删除邮箱进行就地保留
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 了解如何为软删除邮箱创建就地保留，使其处于非活动状态并保留其内容。 然后，您可以使用 Microsoft 电子数据展示工具搜索非活动邮箱。
ms.openlocfilehash: ce4121e6187a765b5a9e23d6e6e11d8cc2640161
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077800"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="95865-104">在 Exchange 在线中对软删除邮箱进行就地保留</span><span class="sxs-lookup"><span data-stu-id="95865-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="95865-105">了解如何为软删除邮箱创建就地保留，使其处于非活动状态并保留其内容。</span><span class="sxs-lookup"><span data-stu-id="95865-105">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="95865-106">然后，您可以使用 Microsoft 电子数据展示工具搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="95865-106">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>
  
> [!NOTE]
> <span data-ttu-id="95865-107">我们推迟了在 Exchange 在线中创建新的就地保留（在 Office 365 和 Exchange 在线独立计划中）的截止时间。</span><span class="sxs-lookup"><span data-stu-id="95865-107">We've postponed the deadline for creating new In-Place Holds in Exchange Online (in Office 365 and Exchange Online standalone plans).</span></span> <span data-ttu-id="95865-108">但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。</span><span class="sxs-lookup"><span data-stu-id="95865-108">But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="95865-109">作为使用就地保留的替代方法，您可以在安全&合规中心中使用[电子数据展示案例](https://go.microsoft.com/fwlink/?linkid=780738)或[保留策略。](https://go.microsoft.com/fwlink/?linkid=827811)</span><span class="sxs-lookup"><span data-stu-id="95865-109">As an alternative to using In-Place Holds, you can use [eDiscovery cases](https://go.microsoft.com/fwlink/?linkid=780738) or [retention policies](https://go.microsoft.com/fwlink/?linkid=827811) in the Security & Compliance Center.</span></span> <span data-ttu-id="95865-110">停用新的就地保留后，您仍可以修改现有的就地保留，并在 Exchange Server 2013 中创建新的就地保留，并且仍支持 Exchange 混合部署。</span><span class="sxs-lookup"><span data-stu-id="95865-110">After we decommission new In-Place Holds, you'll still be able to modify existing In-Place Holds, and creating new In-Place Holds in Exchange Server 2013 and Exchange hybrid deployments will still be supported.</span></span> <span data-ttu-id="95865-111">而且，您仍然可以将邮箱置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="95865-111">And, you'll still be able to place mailboxes on Litigation Hold.</span></span> 
  
<span data-ttu-id="95865-112">您可能有这样的情况：某人已离开您的组织，其相应的用户帐户和邮箱已被删除。</span><span class="sxs-lookup"><span data-stu-id="95865-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="95865-113">之后，您意识到邮箱中的信息需要保留。</span><span class="sxs-lookup"><span data-stu-id="95865-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="95865-114">你能做什么？</span><span class="sxs-lookup"><span data-stu-id="95865-114">What can you do?</span></span> <span data-ttu-id="95865-115">如果已删除的邮箱保留期尚未过期，则可以在已删除的邮箱（称为软删除邮箱）上放置一个就地保留，并将其作为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="95865-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="95865-116">*非活动邮箱*用于在前员工离开您的组织后保留其电子邮件。</span><span class="sxs-lookup"><span data-stu-id="95865-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="95865-117">非活动邮箱的内容在软删除邮箱处于非活动状态时保留在原位保留期间。</span><span class="sxs-lookup"><span data-stu-id="95865-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="95865-118">使邮箱处于非活动状态后，可以使用"交换在线"中的就地电子数据展示、安全&合规性中心的内容搜索或 SharePoint 在线中的电子数据展示中心来搜索邮箱。</span><span class="sxs-lookup"><span data-stu-id="95865-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="95865-119">在 Exchange Online 中，软删除邮箱是已删除但可在特定保留期内恢复的邮箱。</span><span class="sxs-lookup"><span data-stu-id="95865-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="95865-120">Exchange 联机中的软删除邮箱保留期为 30 天。</span><span class="sxs-lookup"><span data-stu-id="95865-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="95865-121">这意味着可以在删除后的 30 天内恢复（或使邮箱成为非活动邮箱）。</span><span class="sxs-lookup"><span data-stu-id="95865-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="95865-122">30 天后，软删除邮箱被标记为永久删除，无法恢复或处于非活动状态。</span><span class="sxs-lookup"><span data-stu-id="95865-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="95865-123">開始之前</span><span class="sxs-lookup"><span data-stu-id="95865-123">Before you begin</span></span>

- <span data-ttu-id="95865-124">您必须使用 Windows PowerShell 中的**New-邮箱搜索**cmdlet 将原位保留放在软删除的邮箱上。</span><span class="sxs-lookup"><span data-stu-id="95865-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="95865-125">不能使用 Exchange 管理中心 （EAC） 或共享点在线中的电子数据展示中心。</span><span class="sxs-lookup"><span data-stu-id="95865-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 
    
- <span data-ttu-id="95865-126">若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="95865-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="95865-127">运行以下命令以获取有关组织中软删除邮箱的标识信息。</span><span class="sxs-lookup"><span data-stu-id="95865-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="95865-128">有关非活动邮箱的详细信息，请参阅 Office [365 中非活动邮箱的概述。](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="95865-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="95865-129">在软删除的邮箱上放置就地保留，使其成为非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="95865-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="95865-130">使用**New-邮箱搜索**cmdlet 将软删除邮箱变为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="95865-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="95865-131">有关详细信息，请参阅[新建邮箱搜索](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="95865-131">For more information, see [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="95865-132">创建包含软删除邮箱属性的变量。</span><span class="sxs-lookup"><span data-stu-id="95865-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span> 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="95865-133">在前面的命令中，**使用"可分辨名称"\*\*\*\*或"ExchangeGuid"** 属性的值来标识软删除的邮箱。</span><span class="sxs-lookup"><span data-stu-id="95865-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="95865-134">这些属性对于组织中的每个邮箱都是唯一的，而活动邮箱和软删除邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="95865-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="95865-135">创建就地保留并将其放置在软删除邮箱上。</span><span class="sxs-lookup"><span data-stu-id="95865-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="95865-136">在此示例中，未指定保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="95865-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="95865-137">这意味着项目将被无限期保留，或直到从非活动邮箱中删除保留。</span><span class="sxs-lookup"><span data-stu-id="95865-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   <span data-ttu-id="95865-138">您还可以在创建就地保留时指定保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="95865-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="95865-139">本示例在非活动邮箱中保留项目大约 7 年。</span><span class="sxs-lookup"><span data-stu-id="95865-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="95865-140">几分钟后，运行以下命令之一，以验证软删除邮箱是否为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="95865-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="95865-141">或</span><span class="sxs-lookup"><span data-stu-id="95865-141">Or</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="95865-142">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="95865-142">More information</span></span>

<span data-ttu-id="95865-143">将软删除邮箱制作为非活动邮箱后，可通过多种方式管理该邮箱。</span><span class="sxs-lookup"><span data-stu-id="95865-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="95865-144">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="95865-144">For more information, see:</span></span>
  
- [<span data-ttu-id="95865-145">變更非使用中信箱的保留期間</span><span class="sxs-lookup"><span data-stu-id="95865-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [<span data-ttu-id="95865-146">復原非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="95865-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)
    
- [<span data-ttu-id="95865-147">還原非使用中的信箱</span><span class="sxs-lookup"><span data-stu-id="95865-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)
    
- <span data-ttu-id="95865-148">[删除非活动邮箱](delete-an-inactive-mailbox.md)（通过拆下保持）</span><span class="sxs-lookup"><span data-stu-id="95865-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
