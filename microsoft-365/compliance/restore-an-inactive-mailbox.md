---
title: 在 Office 365 中还原非活动邮箱
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
description: 如果新员工或其他用户需要访问 Office 365 中非活动邮箱的内容，则可以将非活动邮箱的内容还原（或合并）到现有邮箱。
ms.openlocfilehash: 6bd147296e4324c5f75ff808768f8899cf9b59fd
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078175"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="793f7-103">在 Office 365 中还原非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="793f7-103">Restore an inactive mailbox in Office 365</span></span>

<span data-ttu-id="793f7-104">非活动邮箱（一种软删除邮箱）用于在前员工离开您的组织后保留其电子邮件。</span><span class="sxs-lookup"><span data-stu-id="793f7-104">An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="793f7-105">如果另一名员工承担离职员工的工作职责，或者该员工返回您的组织，则可以通过两种方式将非活动邮箱的内容提供给用户：</span><span class="sxs-lookup"><span data-stu-id="793f7-105">If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span> 
  
- <span data-ttu-id="793f7-106">**还原非活动邮箱**如果其他员工承担离职员工的工作职责，或者如果其他用户需要访问非活动邮箱的内容，则可以将非活动邮箱的内容还原（或合并）到现有邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-106">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="793f7-107">还可以从非活动邮箱还原存档。</span><span class="sxs-lookup"><span data-stu-id="793f7-107">You can also restore the archive from an inactive mailbox.</span></span> <span data-ttu-id="793f7-108">还原后，非活动邮箱将保留并保留为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-108">After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox.</span></span> <span data-ttu-id="793f7-109">本主题介绍还原非活动邮箱的过程。</span><span class="sxs-lookup"><span data-stu-id="793f7-109">This topic describes the procedures for restoring an inactive mailbox.</span></span> 
    
- <span data-ttu-id="793f7-110">**恢复非活动邮箱**如果离职员工返回您的组织，或者雇用新员工来承担离职员工的工作职责，则可以恢复非活动邮箱的内容。</span><span class="sxs-lookup"><span data-stu-id="793f7-110">**Recover an inactive mailbox** If the departed employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox.</span></span> <span data-ttu-id="793f7-111">此方法将非活动邮箱转换为包含非活动邮箱内容的新邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-111">This method converts the inactive mailbox to a new mailbox that contains the contents of the inactive mailbox.</span></span> <span data-ttu-id="793f7-112">它會復原之後，非使用中的信箱不存在。</span><span class="sxs-lookup"><span data-stu-id="793f7-112">After it's recovered, the inactive mailbox no longer exists.</span></span> <span data-ttu-id="793f7-113">有关分步过程，请参阅在 Office [365 中恢复非活动邮箱。](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="793f7-113">For the step-by-step procedures, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
<span data-ttu-id="793f7-114">有关还原和恢复非活动邮箱之间的差异的详细信息，请参阅本文中**的详细信息**部分。</span><span class="sxs-lookup"><span data-stu-id="793f7-114">See the **More information** section in this article for more details about the differences between restoring and recovering an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="793f7-115">開始之前</span><span class="sxs-lookup"><span data-stu-id="793f7-115">Before you begin</span></span>

- <span data-ttu-id="793f7-116">您必须使用 Exchange 联机电源外壳来还原非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-116">You have to use Exchange Online PowerShell to restore an inactive mailbox.</span></span> <span data-ttu-id="793f7-117">不能使用 Exchange 管理中心 （EAC）。</span><span class="sxs-lookup"><span data-stu-id="793f7-117">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="793f7-118">有关分步说明，请参阅[连接到交换在线 PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="793f7-118">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
- <span data-ttu-id="793f7-119">在 Exchange 联机 PowerShell 中运行以下命令，以获取组织中非活动邮箱的标识信息。</span><span class="sxs-lookup"><span data-stu-id="793f7-119">Run the following command in Exchange Online PowerShell to get identity information for the inactive mailboxes in your organization.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     <span data-ttu-id="793f7-120">使用此命令返回的信息还原特定的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-120">Use the information returned by this command to restore a specific inactive mailbox.</span></span>
    
- <span data-ttu-id="793f7-121">有关非活动邮箱的详细信息，请参阅 Office [365 中的非活动邮箱。](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="793f7-121">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="793f7-122">還原非作用中的信箱</span><span class="sxs-lookup"><span data-stu-id="793f7-122">Restore an inactive mailbox</span></span>

<span data-ttu-id="793f7-123">_使用"源邮箱"_ 和"_目标邮箱"_ 参数使用**New-邮箱还原请求**cmdlet 将非活动邮箱的内容还原到现有邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-123">Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="793f7-124">有关使用此 cmdlet 的详细信息，请参阅[新建邮箱还原请求](https://go.microsoft.com/fwlink/?linkid=856298)。</span><span class="sxs-lookup"><span data-stu-id="793f7-124">For more information about using this cmdlet, see [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).</span></span>
  
1. <span data-ttu-id="793f7-125">创建包含非活动邮箱属性的变量。</span><span class="sxs-lookup"><span data-stu-id="793f7-125">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="793f7-126">在前面的命令中，**使用"可分辨名称"\*\*\*\*或"ExchangeGUID"** 属性的值来标识非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-126">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox.</span></span> <span data-ttu-id="793f7-127">这些属性对于组织中的每个邮箱都是唯一的，而活动邮箱和非活动邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="793f7-127">These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="793f7-128">将非活动邮箱的内容还原到现有邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-128">Restore the contents of the inactive mailbox to an existing mailbox.</span></span> <span data-ttu-id="793f7-129">非活动邮箱（源邮箱）的内容将合并到现有邮箱（目标邮箱）中的相应文件夹中。</span><span class="sxs-lookup"><span data-stu-id="793f7-129">The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).</span></span>
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   <span data-ttu-id="793f7-130">或者，您可以在目标邮箱中指定一个顶级文件夹，用于从非活动邮箱还原内容。</span><span class="sxs-lookup"><span data-stu-id="793f7-130">Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox.</span></span> <span data-ttu-id="793f7-131">如果目标邮箱中不存在指定的目标文件夹或目标文件夹结构，则在还原过程中创建该文件夹或目标文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="793f7-131">If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process.</span></span> 
    
    <span data-ttu-id="793f7-132">本示例将邮箱项目和子文件夹从非活动邮箱复制到目标邮箱的顶级文件夹结构中名为"非活动邮箱"的文件夹。</span><span class="sxs-lookup"><span data-stu-id="793f7-132">This example copies mailbox items and subfolders from an inactive mailbox to a folder named "Inactive Mailbox" in the top-level folder structure of the target mailbox.</span></span>
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a><span data-ttu-id="793f7-133">从非活动邮箱还原存档</span><span class="sxs-lookup"><span data-stu-id="793f7-133">Restore the archive from an inactive mailbox</span></span>

<span data-ttu-id="793f7-134">如果非活动邮箱具有存档邮箱，也可以将其还原到现有邮箱的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-134">If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox.</span></span> <span data-ttu-id="793f7-135">要从非活动邮箱还原存档，必须将_SourceIsArchive_和_TargetIsAchive_开关添加到用于还原非活动邮箱的命令。</span><span class="sxs-lookup"><span data-stu-id="793f7-135">To restore the archive from an inactive mailbox, you have to add the  _SourceIsArchive_ and  _TargetIsAchive_ switches to the command used to restore an inactive mailbox.</span></span> 
  
1. <span data-ttu-id="793f7-136">创建包含非活动邮箱属性的变量。</span><span class="sxs-lookup"><span data-stu-id="793f7-136">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="793f7-137">在前面的命令中，**使用"可分辨名称"\*\*\*\*或"ExchangeGUID"** 属性的值来标识非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-137">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox.</span></span> <span data-ttu-id="793f7-138">这些属性对于组织中的每个邮箱都是唯一的，而活动邮箱和非活动邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="793f7-138">These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="793f7-139">将存档的内容从非活动邮箱（源存档）还原到现有邮箱（目标存档）的存档。</span><span class="sxs-lookup"><span data-stu-id="793f7-139">Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive).</span></span> <span data-ttu-id="793f7-140">在此示例中，源存档中的内容将复制到目标邮箱存档中名为"非活动邮箱存档"的文件夹。</span><span class="sxs-lookup"><span data-stu-id="793f7-140">In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.</span></span>

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a><span data-ttu-id="793f7-141">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="793f7-141">More information</span></span>

- <span data-ttu-id="793f7-142">**恢复和恢复非活动邮箱之间的主要区别是什么？**</span><span class="sxs-lookup"><span data-stu-id="793f7-142">**What's the main difference between recovering and restoring an inactive mailbox?**</span></span> <span data-ttu-id="793f7-143">恢复非活动邮箱时，邮箱基本上将转换为新邮箱，非活动邮箱的内容和文件夹结构将保留，并且邮箱链接到新的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="793f7-143">When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account.</span></span> <span data-ttu-id="793f7-144">恢复后，非活动邮箱不再存在，对新邮箱中的内容所做的任何更改都将影响非活动邮箱中最初处于保留状态的内容。</span><span class="sxs-lookup"><span data-stu-id="793f7-144">After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox.</span></span> <span data-ttu-id="793f7-145">相反，还原非活动邮箱时，内容只会复制到另一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-145">Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox.</span></span> <span data-ttu-id="793f7-146">非活动邮箱将保留，并保留为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-146">The inactive mailbox is preserved and remains an inactive mailbox.</span></span> <span data-ttu-id="793f7-147">对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。</span><span class="sxs-lookup"><span data-stu-id="793f7-147">Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox.</span></span> <span data-ttu-id="793f7-148">仍可以使用安全&合规性中心[中的内容搜索工具](run-a-content-search-in-the-security-and-compliance-center.md)搜索非活动邮箱，其内容可以还原到另一个邮箱，也可以在以后恢复或删除。</span><span class="sxs-lookup"><span data-stu-id="793f7-148">The inactive mailbox can still be searched by using the [Content Search tool](run-a-content-search-in-the-security-and-compliance-center.md) in the Security & Compliance Center, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span> 
    
- <span data-ttu-id="793f7-149">**如何查找非活动邮箱？**</span><span class="sxs-lookup"><span data-stu-id="793f7-149">**How do you find inactive mailboxes?**</span></span> <span data-ttu-id="793f7-150">要获取组织中非活动邮箱的列表并显示对还原非活动邮箱有用的信息，可以运行此命令。</span><span class="sxs-lookup"><span data-stu-id="793f7-150">To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.</span></span> 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- <span data-ttu-id="793f7-151">**使用诉讼保留或 Office 365 保留策略保留非活动邮箱内容。**</span><span class="sxs-lookup"><span data-stu-id="793f7-151">**Use a Litigation Hold or Office 365 retention policy to retain inactive mailbox content.**</span></span> <span data-ttu-id="793f7-152">如果要在还原非活动邮箱后保留其状态，则可以将目标邮箱置于[诉讼保留](https://go.microsoft.com/fwlink/?linkid=856286)状态，或在还原非活动邮箱之前应用[Office 365 保留策略。](retention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="793f7-152">If you want to retain the state of an inactive mailbox after it's restored, you can place the target mailbox on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) or apply an [Office 365 retention policy](retention-policies.md) before you restore the inactive mailbox.</span></span> <span data-ttu-id="793f7-153">这将阻止在将项目还原到目标邮箱后从非活动邮箱永久删除这些项目。</span><span class="sxs-lookup"><span data-stu-id="793f7-153">This will prevent the permanent deletion of any items from the inactive mailbox after they're restored to the target mailbox.</span></span> 
    
- <span data-ttu-id="793f7-154">**在还原非活动邮箱之前，启用目标邮箱的保留保留。**</span><span class="sxs-lookup"><span data-stu-id="793f7-154">**Enable retention hold on the target mailbox before you restore an inactive mailbox.**</span></span> <span data-ttu-id="793f7-155">由于非活动邮箱中的邮箱项目可能已旧，因此在还原非活动邮箱之前，可以考虑在目标邮箱上启用保留保留。</span><span class="sxs-lookup"><span data-stu-id="793f7-155">Because mailbox items from an inactive mailbox could be old, you might consider enabling retention hold on the target mailbox before you restore an inactive mailbox.</span></span> <span data-ttu-id="793f7-156">将邮箱置于保留保留状态时，在删除保留保留或保留期到期之前，不会处理分配给该邮箱的保留策略。</span><span class="sxs-lookup"><span data-stu-id="793f7-156">When you put a mailbox on retention hold, the retention policy that's assigned to it won't be processed until the retention hold is removed or until the retention hold period expires.</span></span> <span data-ttu-id="793f7-157">这为目标邮箱的所有者提供了管理来自非活动邮箱的旧邮件的时间。</span><span class="sxs-lookup"><span data-stu-id="793f7-157">This gives the owner of the target mailbox time to manage old messages from the inactive mailbox.</span></span> <span data-ttu-id="793f7-158">否则，保留策略可能会删除根据为目标邮箱配置的保留设置过期的旧项目（或将项目移动到存档邮箱（如果已启用）。"</span><span class="sxs-lookup"><span data-stu-id="793f7-158">Otherwise, the retention policy might delete old items (or move items to the archive mailbox, if it's enabled) that have expired based on the retention settings configured for the target mailbox.</span></span> <span data-ttu-id="793f7-159">有关详细信息，请参阅在[Exchange 联机中放置保留邮箱。](https://go.microsoft.com/fwlink/?linkid=856300)</span><span class="sxs-lookup"><span data-stu-id="793f7-159">For more information, see [Place a mailbox on retention hold in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).</span></span>
    
- <span data-ttu-id="793f7-160">**允许传统DN不匹配开关的作用是什么？**</span><span class="sxs-lookup"><span data-stu-id="793f7-160">**What does the AllowLegacyDNMismatch switch do?**</span></span> <span data-ttu-id="793f7-161">在前面还原非活动邮箱的示例中，**允许旧邮箱不匹配**开关用于允许将非活动邮箱还原到其他目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="793f7-161">In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox.</span></span> <span data-ttu-id="793f7-162">在典型的还原方案中，目标是还原源邮箱和目标邮箱是同一邮箱的内容。</span><span class="sxs-lookup"><span data-stu-id="793f7-162">In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox.</span></span> <span data-ttu-id="793f7-163">因此，**默认情况下，New-邮箱还原请求**cmdlet 检查以确保源邮箱和目标邮箱上的**LegacyExchangeDN**属性的值相同。</span><span class="sxs-lookup"><span data-stu-id="793f7-163">So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same.</span></span> <span data-ttu-id="793f7-164">这有助于防止意外将源邮箱还原到错误的目标邮箱中。</span><span class="sxs-lookup"><span data-stu-id="793f7-164">This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox.</span></span> <span data-ttu-id="793f7-165">如果尝试还原非活动邮箱而不**使用"允许遗留DN 不匹配"** 开关，则如果源邮箱和目标邮箱具有**旧版ExchangeDN**属性的不同值，则该命令可能会失败。</span><span class="sxs-lookup"><span data-stu-id="793f7-165">If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.</span></span> 
    
- <span data-ttu-id="793f7-166">**您可以将其他参数与 New-邮箱还原请求 cmdlet 一起实现非活动邮箱的不同还原方案。**</span><span class="sxs-lookup"><span data-stu-id="793f7-166">**You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.**</span></span> <span data-ttu-id="793f7-167">例如，可以运行此命令将存档从非活动邮箱还原到目标邮箱的主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="793f7-167">For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox.</span></span> 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  <span data-ttu-id="793f7-168">还可以通过运行此命令将非活动主邮箱还原到目标邮箱的存档中。</span><span class="sxs-lookup"><span data-stu-id="793f7-168">You can also restore the inactive primary mailbox into the archive of the target mailbox by running this command.</span></span>

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- <span data-ttu-id="793f7-169">**目标根文件夹参数的作用是什么？**</span><span class="sxs-lookup"><span data-stu-id="793f7-169">**What does the TargetRootFolder parameter do?**</span></span> <span data-ttu-id="793f7-170">如前所述，可以使用**TargetRootFolder**参数在目标邮箱中的文件夹结构（也称为根）顶部指定文件夹，用于还原非活动邮箱的内容。</span><span class="sxs-lookup"><span data-stu-id="793f7-170">As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox.</span></span> <span data-ttu-id="793f7-171">如果不使用此参数，则非活动邮箱中的邮箱项目将合并到目标邮箱的相应默认文件夹中，并在目标邮箱的根目录中重新创建自定义文件夹。</span><span class="sxs-lookup"><span data-stu-id="793f7-171">If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox.</span></span> <span data-ttu-id="793f7-172">下图突出显示了不使用和使用**TargetRootFolder**参数之间的这些差异。</span><span class="sxs-lookup"><span data-stu-id="793f7-172">The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.</span></span> 
    
    <span data-ttu-id="793f7-173">**未使用目标根文件夹参数时的目标邮箱中的文件夹层次结构**</span><span class="sxs-lookup"><span data-stu-id="793f7-173">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter isn't used**</span></span>
    
    ![未使用 TargetRootFolder 參數時的螢幕擷取畫面](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    <span data-ttu-id="793f7-175">**使用目标根文件夹参数时的目标邮箱中的文件夹层次结构**</span><span class="sxs-lookup"><span data-stu-id="793f7-175">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter is used**</span></span>
    
    ![使用 TargetRootFolder 參數時的螢幕擷取畫面](media/300da592-7323-48db-b8a4-07012259d113.png)

  

