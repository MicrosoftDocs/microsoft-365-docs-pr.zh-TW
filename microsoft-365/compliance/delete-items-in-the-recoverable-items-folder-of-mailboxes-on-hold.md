---
title: 删除基于云的邮箱的"可恢复项目"文件夹中的项目保留 - 管理员帮助
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
description: 对于管理员：删除 Exchange 联机邮箱的用户可恢复项目文件夹中的项目，即使该邮箱处于合法保留状态也是如此。 这是删除意外泄漏到 Office 365 的数据的有效方法。
ms.openlocfilehash: 9da469af900c2610762338029aa80d31c7f10363
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070732"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="da4a9-104">删除基于云的邮箱的"可恢复项目"文件夹中的项目保留 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="da4a9-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="da4a9-105">Exchange Online 邮箱的可恢复项目文件夹存在，以防止意外或恶意删除。</span><span class="sxs-lookup"><span data-stu-id="da4a9-105">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="da4a9-106">它还用于存储由 Office 365 合规性功能（如保留和电子数据展示搜索）保留和访问的项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-106">It's also used to store items that are retained and accessed by Office 365 compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="da4a9-107">但是，在某些情况下，组织可能无意中保留在必须删除的"可恢复项目"文件夹中的数据。</span><span class="sxs-lookup"><span data-stu-id="da4a9-107">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="da4a9-108">例如，用户可能在不知不觉中发送或转发包含敏感信息或可能造成严重业务后果的信息的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="da4a9-108">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="da4a9-109">即使邮件被永久删除，也可能无限期地保留它，因为邮箱上已放置了法律保留。</span><span class="sxs-lookup"><span data-stu-id="da4a9-109">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="da4a9-110">此方案称为数据溢出，因为数据被无意中溢出到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="da4a9-110">This scenario is known as data spillage because data has been unintentionally spilled into Office 365.</span></span> <span data-ttu-id="da4a9-111">在这些情况下，您可以删除 Exchange Online 邮箱的用户"可恢复项目"文件夹中的项目，即使该邮箱在 Office 365 中具有不同的保留功能之一置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="da4a9-111">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="da4a9-112">这些类型的保留包括诉讼保留、就地保留、电子数据展示保留，以及 Office 365 保留策略，这些策略是在 Office 365 或 Microsoft 365 中的安全和合规性中心创建的 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="da4a9-112">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and Office 365 retention policies created in the security and compliance center in Office 365 or Microsoft 365.</span></span>
  
 <span data-ttu-id="da4a9-113">本文介绍如何从处于保留状态的基于云的邮箱的"可恢复项目"文件夹中删除项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-113">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="da4a9-114">此过程包括禁用对邮箱的访问和禁用单个项目恢复、禁用托管文件夹助理处理邮箱、临时删除保留、从"可恢复项目"文件夹中删除项目，然后恢复邮箱到其以前的配置。</span><span class="sxs-lookup"><span data-stu-id="da4a9-114">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="da4a9-115">过程是：</span><span class="sxs-lookup"><span data-stu-id="da4a9-115">Here's the process:</span></span> 
  
[<span data-ttu-id="da4a9-116">第 1 步：收集有关邮箱的信息</span><span class="sxs-lookup"><span data-stu-id="da4a9-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="da4a9-117">第 2 步：准备邮箱</span><span class="sxs-lookup"><span data-stu-id="da4a9-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="da4a9-118">步骤 3：从邮箱中删除所有保留</span><span class="sxs-lookup"><span data-stu-id="da4a9-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="da4a9-119">步骤 4：从邮箱中删除延迟保留</span><span class="sxs-lookup"><span data-stu-id="da4a9-119">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="da4a9-120">步骤 5：删除"可恢复项目"文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="da4a9-120">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="da4a9-121">步骤 6：将邮箱还原到其以前的状态</span><span class="sxs-lookup"><span data-stu-id="da4a9-121">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="da4a9-122">本文中概述的过程将导致数据从 Exchange 联机邮箱永久删除（清除）。</span><span class="sxs-lookup"><span data-stu-id="da4a9-122">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="da4a9-123">这意味着无法恢复从"可恢复项目"文件夹中删除的邮件，并且无法用于法律发现或其他合规性目的。</span><span class="sxs-lookup"><span data-stu-id="da4a9-123">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="da4a9-124">如果要从作为诉讼保留、就地保留、电子数据展示保留或在安全和合规性中心创建的 Office 365 保留策略的一部分而从保留的邮箱中删除邮件，请咨询您的记录管理或法律部门在拆下保持。</span><span class="sxs-lookup"><span data-stu-id="da4a9-124">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or Office 365 retention policy created in the security and compliance center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="da4a9-125">您的组织可能具有一个策略，用于定义邮箱处于保留状态还是数据溢出事件是否具有优先级。</span><span class="sxs-lookup"><span data-stu-id="da4a9-125">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="da4a9-126">開始之前</span><span class="sxs-lookup"><span data-stu-id="da4a9-126">Before you begin</span></span>

- <span data-ttu-id="da4a9-127">您必须在 Exchange Online 中分配以下两个管理角色，以便从步骤 5 中的"可恢复项目"文件夹中搜索和删除邮件。</span><span class="sxs-lookup"><span data-stu-id="da4a9-127">You have to be assigned both of the following management roles in Exchange Online to search for and delete messages from the Recoverable Items folder in Step 5.</span></span>
    
  - <span data-ttu-id="da4a9-128">**邮箱搜索**- 此角色允许您搜索组织中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-128">**Mailbox Search** - This role lets you to search mailboxes in your organization.</span></span> <span data-ttu-id="da4a9-129">默认情况下，Exchange 管理员不会分配此角色。</span><span class="sxs-lookup"><span data-stu-id="da4a9-129">Exchange administrators aren't assigned this role by default.</span></span> <span data-ttu-id="da4a9-130">要分配此角色，请将自己添加为 Exchange 联机中的发现管理角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="da4a9-130">To assign yourself this role, add yourself as a member of the Discovery Management role group in Exchange Online.</span></span> 
    
  - <span data-ttu-id="da4a9-131">**邮箱导入导出**- 此角色允许您从用户的邮箱中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="da4a9-131">**Mailbox Import Export** - This role lets you to delete messages from a user's mailbox.</span></span> <span data-ttu-id="da4a9-132">默认情况下，此角色不会分配给任何角色组。</span><span class="sxs-lookup"><span data-stu-id="da4a9-132">By default, this role isn't assigned to any role group.</span></span> <span data-ttu-id="da4a9-133">要从用户的邮箱中删除邮件，可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="da4a9-133">To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> 
    
- <span data-ttu-id="da4a9-134">对于非活动邮箱，不支持本文中描述的过程。</span><span class="sxs-lookup"><span data-stu-id="da4a9-134">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="da4a9-135">这是因为在删除非活动邮箱后，无法将保留（或 Office 365 保留策略）重新应用于该邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-135">That's because you can't re-apply a hold (or Office 365 retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="da4a9-136">从非活动邮箱中删除保留时，该保留将更改为正常的软删除邮箱，并在托管文件夹助理处理后从组织永久删除。</span><span class="sxs-lookup"><span data-stu-id="da4a9-136">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>
    
- <span data-ttu-id="da4a9-137">对于已分配给已锁定使用保留锁的 Office 365 保留策略的邮箱，无法执行此过程。</span><span class="sxs-lookup"><span data-stu-id="da4a9-137">You can't perform this procedure for a mailbox that has been assigned to an Office 365 retention policy that's been locked with a Preservation Lock.</span></span> <span data-ttu-id="da4a9-138">这是因为保留锁阻止您从 Office 365 保留策略中删除或删除邮箱，以及禁用邮箱上的托管文件夹助手。</span><span class="sxs-lookup"><span data-stu-id="da4a9-138">That's because a Preservation Lock prevents you from removing or excluding the mailbox from the Office 365 retention policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="da4a9-139">有关锁定保留策略的详细信息，请参阅[锁定保留策略](retention-policies.md#locking-a-retention-policy)。</span><span class="sxs-lookup"><span data-stu-id="da4a9-139">For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>
    
- <span data-ttu-id="da4a9-140">如果邮箱未置于保留状态（或未启用单个项目恢复），则只需从"可恢复项目"文件夹中删除这些项目即可。</span><span class="sxs-lookup"><span data-stu-id="da4a9-140">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can simply delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="da4a9-141">有关如何执行此操作的详细信息，请参阅[搜索和删除邮件](https://go.microsoft.com/fwlink/?linkid=852453)。</span><span class="sxs-lookup"><span data-stu-id="da4a9-141">For more information about how to do this, see [Search for and delete messages ](https://go.microsoft.com/fwlink/?linkid=852453).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="da4a9-142">第 1 步：收集有关邮箱的信息</span><span class="sxs-lookup"><span data-stu-id="da4a9-142">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="da4a9-143">第一步是从目标邮箱收集将影响此过程的选定属性。</span><span class="sxs-lookup"><span data-stu-id="da4a9-143">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="da4a9-144">请务必记下这些设置或将其保存到文本文件中，因为您将更改其中一些属性，然后在从"可恢复项目"文件夹中删除项目后恢复为步骤 6 中的原始值。</span><span class="sxs-lookup"><span data-stu-id="da4a9-144">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="da4a9-145">下面是需要收集的邮箱属性的列表。</span><span class="sxs-lookup"><span data-stu-id="da4a9-145">Here's a list of the mailbox properties you need to collect.</span></span>
  
-  <span data-ttu-id="da4a9-146">*单项恢复启用*和*保留删除项为*.如有必要，您将禁用单个恢复，并延长步骤 3 中已删除的项目保留期。</span><span class="sxs-lookup"><span data-stu-id="da4a9-146">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*  ; if necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 
    
-  <span data-ttu-id="da4a9-147">*诉讼保留*和*原位保留;* 您需要标识放置在邮箱上的所有保留，以便在步骤 3 中暂时删除它们。</span><span class="sxs-lookup"><span data-stu-id="da4a9-147">*LitigationHoldEnabled*  and  *InPlaceHolds*  ; you need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="da4a9-148">有关如何标识可能放置在邮箱上的类型保留的提示，[请参阅"详细信息"](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="da4a9-148">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
    
<span data-ttu-id="da4a9-149">此外，您需要获取邮箱客户端访问设置，以便可以暂时禁用这些设置，以便所有者（或其他用户）无法在此过程中访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-149">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="da4a9-150">最后，您可以在"可恢复项目"文件夹中获取当前大小和项目数。</span><span class="sxs-lookup"><span data-stu-id="da4a9-150">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="da4a9-151">删除步骤 5 中的"可恢复项目"文件夹中的项目后，将使用此信息来验证项目是否实际已删除。</span><span class="sxs-lookup"><span data-stu-id="da4a9-151">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were actually removed.</span></span>
  
1. <span data-ttu-id="da4a9-152">[連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="da4a9-152">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="da4a9-153">请确保对在 Exchange 联机中分配了相应管理角色的管理员帐户使用用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="da4a9-153">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="da4a9-154">运行以下命令以获取有关单个项目恢复和已删除项目保留期的信息。</span><span class="sxs-lookup"><span data-stu-id="da4a9-154">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="da4a9-155">如果启用了单个项目恢复，您必须在步骤 2 中禁用它。</span><span class="sxs-lookup"><span data-stu-id="da4a9-155">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="da4a9-156">如果已删除的项目保留期未设置为 30 天（Exchange Online 中的最大值），则可以在步骤 2 中增加该期限。</span><span class="sxs-lookup"><span data-stu-id="da4a9-156">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="da4a9-157">运行以下命令以获取邮箱的邮箱访问设置。</span><span class="sxs-lookup"><span data-stu-id="da4a9-157">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="da4a9-158">您将在步骤 2 中禁用所有这些访问方法。</span><span class="sxs-lookup"><span data-stu-id="da4a9-158">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="da4a9-159">运行以下命令以获取有关应用于邮箱的保留和 Office 365 保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="da4a9-159">Run the following command to get information about the holds and Office 365 retention policies applied to the mailbox.</span></span>
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="da4a9-160">如果*InPlaceHolds*属性中的值太多，并且并非所有值都显示，则可以运行该`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行上显示每个值。</span><span class="sxs-lookup"><span data-stu-id="da4a9-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="da4a9-161">运行以下命令以获取有关任何组织范围的 Office 365 保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="da4a9-161">Run the following command to get information about any organization-wide Office 365 retention policies.</span></span> 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   <span data-ttu-id="da4a9-162">如果您的组织具有任何组织范围的 Office 365 保留策略，则必须从步骤 3 中的这些策略中排除邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-162">If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="da4a9-163">如果*InPlaceHolds*属性中的值太多，并且并非所有值都显示，则可以运行该`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行上显示每个值。</span><span class="sxs-lookup"><span data-stu-id="da4a9-163">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="da4a9-164">运行以下命令以获取用户主邮箱中可恢复项目文件夹中的文件夹和子文件夹中的当前大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="da4a9-164">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="da4a9-165">如果启用了用户的存档邮箱，则运行以下命令以获取其存档邮箱中的可恢复项目文件夹中文件夹和子文件夹中的项目大小和总数。</span><span class="sxs-lookup"><span data-stu-id="da4a9-165">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="da4a9-166">删除步骤 5 中的项目时，可以选择删除或不删除用户主存档邮箱中的"可恢复项目"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-166">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="da4a9-167">请注意，如果为邮箱启用了自动展开存档，则不会删除辅助存档邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-167">Note that if auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="da4a9-168">第 2 步：准备邮箱</span><span class="sxs-lookup"><span data-stu-id="da4a9-168">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="da4a9-169">收集和保存有关邮箱的信息后，下一步是通过执行以下任务来准备邮箱：</span><span class="sxs-lookup"><span data-stu-id="da4a9-169">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="da4a9-170">**禁用客户端对邮箱的访问，** 以便邮箱所有者无法访问其邮箱，并在此过程期间对邮箱数据进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="da4a9-170">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="da4a9-171">**将已删除的项目保留期增加到**30 天（Exchange Online 中的最大值），以便在步骤 5 中删除项目之前，不会从"可恢复项目"文件夹中清除这些项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-171">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="da4a9-172">**禁用单个项目恢复，** 以便在从步骤 5 中的"可恢复项目"文件夹中删除项目后，不会保留项目（在已删除项目保留期的持续时间内）。</span><span class="sxs-lookup"><span data-stu-id="da4a9-172">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="da4a9-173">**禁用托管文件夹助手，** 使其不处理邮箱并保留您在步骤 5 中删除的项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-173">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="da4a9-174">在 Exchange 在线电源外壳中执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="da4a9-174">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="da4a9-175">运行以下命令以禁用对邮箱的所有客户端访问。</span><span class="sxs-lookup"><span data-stu-id="da4a9-175">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="da4a9-176">命令语法假定邮箱上启用了所有客户端访问方法。</span><span class="sxs-lookup"><span data-stu-id="da4a9-176">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > <span data-ttu-id="da4a9-177">最多可能需要 60 分钟才能禁用对邮箱的所有客户端访问方法。</span><span class="sxs-lookup"><span data-stu-id="da4a9-177">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="da4a9-178">请注意，禁用这些访问方法不会断开他们当前登录的邮箱所有者的连接。</span><span class="sxs-lookup"><span data-stu-id="da4a9-178">Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in.</span></span> <span data-ttu-id="da4a9-179">如果所有者未登录，则禁用这些访问方法后，他们将无法访问其邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-179">If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="da4a9-180">运行以下命令，将已删除的项目保留期最多增加 30 天。</span><span class="sxs-lookup"><span data-stu-id="da4a9-180">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="da4a9-181">这假定当前设置小于 30 天。</span><span class="sxs-lookup"><span data-stu-id="da4a9-181">This assumes that the current setting is less than 30 days.</span></span> 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="da4a9-182">运行以下命令以禁用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="da4a9-182">Run the following command to disable single item recovery.</span></span>
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="da4a9-183">禁用单个项目恢复可能需要长达 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="da4a9-183">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="da4a9-184">在此时间段过后，不要删除"可恢复项目"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-184">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="da4a9-185">运行以下命令以防止托管文件夹助理处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-185">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="da4a9-186">如前所述，仅当具有保留锁的 Office 365 保留策略未应用于邮箱时，才能禁用托管文件夹助手。</span><span class="sxs-lookup"><span data-stu-id="da4a9-186">As previously explained, you can disable the Managed Folder Assistant only if an Office 365 retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="da4a9-187">步骤 3：从邮箱中删除所有保留</span><span class="sxs-lookup"><span data-stu-id="da4a9-187">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="da4a9-188">从"可恢复项目"文件夹中删除项目的最后一步是删除放置在邮箱上的所有保留（您在步骤 1 中标识）。</span><span class="sxs-lookup"><span data-stu-id="da4a9-188">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="da4a9-189">必须删除所有保留，以便在从"可恢复项目"文件夹中删除项目后，不会保留这些项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-189">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="da4a9-190">以下部分包含有关删除邮箱上的不同类型的保留的信息。</span><span class="sxs-lookup"><span data-stu-id="da4a9-190">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="da4a9-191">有关如何标识可能放置在邮箱上的类型保留的提示，[请参阅"详细信息"](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="da4a9-191">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="da4a9-192">有关详细信息，请参阅[如何识别在 Exchange 联机邮箱上放置的保留类型。](identify-a-hold-on-an-exchange-online-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="da4a9-192">For additional information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="da4a9-193">如前所述，在从邮箱中删除保留之前，请咨询您的记录管理或法律部门。</span><span class="sxs-lookup"><span data-stu-id="da4a9-193">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="da4a9-194">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="da4a9-194">Litigation Hold</span></span>
  
<span data-ttu-id="da4a9-195">在 Exchange 联机 PowerShell 中运行以下命令，从邮箱中删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="da4a9-195">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="da4a9-196">与禁用客户端访问方法和单个项目恢复类似，删除诉讼保留可能需要长达 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="da4a9-196">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="da4a9-197">在此时间段过后，不要从"可恢复项目"文件夹中删除项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-197">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="da4a9-198">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="da4a9-198">In-Place Hold</span></span>
  
<span data-ttu-id="da4a9-199">在 Exchange 联机 PowerShell 中运行以下命令，以标识放置在邮箱上的就地保持。</span><span class="sxs-lookup"><span data-stu-id="da4a9-199">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="da4a9-200">使用 GUID 进行步骤 1 中标识的就地保持。</span><span class="sxs-lookup"><span data-stu-id="da4a9-200">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
<span data-ttu-id="da4a9-201">识别就地保留后，可以使用 Exchange 管理中心 （EAC） 或 Exchange 在线 PowerShell 从保留中删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-201">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="da4a9-202">有关详细信息，请参阅[创建或删除就地保留](https://go.microsoft.com/fwlink/?linkid=852668)。</span><span class="sxs-lookup"><span data-stu-id="da4a9-202">For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="da4a9-203">应用于特定邮箱的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="da4a9-203">Office 365 retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="da4a9-204">[在"安全&合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令，以标识应用于邮箱的 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="da4a9-204">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the Office 365 retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="da4a9-205">对步骤 1 中标识的`mbx`保留`skp`策略使用 GUID（不包括 或前缀）。</span><span class="sxs-lookup"><span data-stu-id="da4a9-205">Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
<span data-ttu-id="da4a9-206">确定保留策略后，转到安全&合规中心**中的"日期治理**\>**保留"** 页，编辑您在上一步中标识的保留策略，并从保留策略中包含的收件人。</span><span class="sxs-lookup"><span data-stu-id="da4a9-206">After you identify the retention policy, go to the **Date governance** \> **Retention** page in the Security & Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-office-365-retention-policies"></a><span data-ttu-id="da4a9-207">组织范围的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="da4a9-207">Organization-wide Office 365 retention policies</span></span>
  
<span data-ttu-id="da4a9-208">组织范围和 Exchange 范围的 Office 365 保留策略应用于组织中的每个邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-208">Organization-wide and Exchange-wide Office 365 retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="da4a9-209">它们在组织级别（而不是邮箱级别）应用，并在步骤 1 中运行**Get-组织 Config** cmdlet 时返回。</span><span class="sxs-lookup"><span data-stu-id="da4a9-209">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="da4a9-210">在[安全&合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令，以标识组织范围的 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="da4a9-210">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide Office 365 retention policies.</span></span> <span data-ttu-id="da4a9-211">对步骤 1 中标识的组织`mbx`范围保留策略使用 GUID（不包括前缀）。</span><span class="sxs-lookup"><span data-stu-id="da4a9-211">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="da4a9-212">确定组织范围的 Office 365 保留策略后，请转到安全&合规性中心**中的"日期治理**\>**保留"** 页，编辑您在上一步，并将邮箱添加到排除的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="da4a9-212">After you identify the organization-wide Office 365 retention policies, go to the **Date governance** \> **Retention** page in the Security & Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="da4a9-213">这样做会从保留策略中删除用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-213">Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="office-365-retention-labels"></a><span data-ttu-id="da4a9-214">Office 365 保留標籤</span><span class="sxs-lookup"><span data-stu-id="da4a9-214">Office 365 retention labels</span></span>

<span data-ttu-id="da4a9-215">每当用户应用配置为保留内容或保留内容，然后将内容删除到其邮箱中的任何文件夹或项目时，*符合性标记应用*邮箱属性将设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="da4a9-215">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="da4a9-216">发生这种情况时，邮箱将被视为处于保留状态，就像将其置于诉讼保留或分配给 Office 365 保留策略一样。</span><span class="sxs-lookup"><span data-stu-id="da4a9-216">When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span>

<span data-ttu-id="da4a9-217">要查看*符合性标记应用*属性的值，在 Exchange 在线 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="da4a9-217">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="da4a9-218">确定邮箱因保留标签应用于文件夹或项目而处于保留状态后，可以使用安全和合规性中心中的内容搜索工具使用"合规性标记"搜索条件搜索标记的项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-218">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the security and compliance center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="da4a9-219">有关详细信息，请参阅关键字查询中的"搜索条件"部分[和内容搜索的搜索条件。](keyword-queries-and-search-conditions.md#conditions-for-common-properties)</span><span class="sxs-lookup"><span data-stu-id="da4a9-219">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="da4a9-220">有关标签的详细信息，请参阅[Office 365 标签概述](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="da4a9-220">For more information about labels, see [Overview of Office 365 labels](labels.md).</span></span>

 ### <a name="ediscovery-case-holds"></a><span data-ttu-id="da4a9-221">电子数据展示案例保留</span><span class="sxs-lookup"><span data-stu-id="da4a9-221">eDiscovery case holds</span></span>
  
<span data-ttu-id="da4a9-222">[在"安全&合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令，以标识与应用于邮箱的电子数据展示案例关联的保留。</span><span class="sxs-lookup"><span data-stu-id="da4a9-222">Run the following commands in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox.</span></span> <span data-ttu-id="da4a9-223">使用 GUID（不包括`UniH`前缀）执行您在步骤 1 中标识的"电子数据展示"保留。</span><span class="sxs-lookup"><span data-stu-id="da4a9-223">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="da4a9-224">请注意，第二个命令显示保留关联的电子数据展示案例的名称;第二个命令显示保留与保存关联的案例的名称。第三个命令显示保留的名称。</span><span class="sxs-lookup"><span data-stu-id="da4a9-224">Note that the second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

<span data-ttu-id="da4a9-225">确定电子数据展示案例的名称和保留后，转到合规性中心**中的电子数据展示**\>**电子数据展示**页面，打开案例，然后从保留中删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-225">After you've identified the name of the eDiscovery case and the hold, go to the **eDiscovery** \> **eDiscovery** page in the compliance center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="da4a9-226">有关详细信息，请参阅[电子数据展示案例](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="da4a9-226">For more information, see [eDiscovery cases](ediscovery-cases.md).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="da4a9-227">步骤 4：从邮箱中删除延迟保留</span><span class="sxs-lookup"><span data-stu-id="da4a9-227">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="da4a9-228">从邮箱中删除任何类型的保留*后，DelayHold 应用*邮箱属性的值将设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="da4a9-228">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="da4a9-229">下次托管文件夹助理处理邮箱并检测到保留已被删除时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="da4a9-229">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="da4a9-230">这称为*延迟保留，* 这意味着实际删除保留将延迟 30 天，以防止数据从邮箱永久删除。</span><span class="sxs-lookup"><span data-stu-id="da4a9-230">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="da4a9-231">（延迟保留的目的是让管理员有机会搜索或恢复在删除保留后将清除的邮箱项目。 在邮箱上放置延迟保留时，邮箱仍被视为无限期处于保留状态，就像邮箱处于诉讼保留状态一样。</span><span class="sxs-lookup"><span data-stu-id="da4a9-231">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="da4a9-232">30 天后，延迟保留将过期，Office 365 将自动尝试删除延迟保留（通过将*DelayHold 应用*属性设置为**False），** 以便实际删除保留。</span><span class="sxs-lookup"><span data-stu-id="da4a9-232">After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold is actually removed.</span></span> 

<span data-ttu-id="da4a9-233">在删除步骤 5 中的项目之前，必须从邮箱中删除延迟保留。</span><span class="sxs-lookup"><span data-stu-id="da4a9-233">Before you can delete items in Step 5, you have to remove the delay hold from the mailbox.</span></span> <span data-ttu-id="da4a9-234">首先，通过在 Exchange 在线 PowerShell 中运行以下命令，确定是否将延迟保留应用于邮箱：</span><span class="sxs-lookup"><span data-stu-id="da4a9-234">First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="da4a9-235">如果*DelayHold 应用*属性的值设置为**False，** 则邮箱上尚未放置延迟保留。</span><span class="sxs-lookup"><span data-stu-id="da4a9-235">If the value of the *DelayHoldApplied* property is set to **False**, a delay hold has not been placed on the mailbox.</span></span> <span data-ttu-id="da4a9-236">您可以转到步骤 5 并删除"可恢复项目"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-236">You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="da4a9-237">如果*DelayHold 应用*属性的值设置为**True，** 则运行以下命令以删除延迟保留：</span><span class="sxs-lookup"><span data-stu-id="da4a9-237">If the value of the *DelayHoldApplied* property is set to **True**, run the following command to remove the delay hold:</span></span>

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="da4a9-238">请注意，您必须在"联机交换"中分配"法律保留"角色才能*使用"删除延迟应用"* 参数。</span><span class="sxs-lookup"><span data-stu-id="da4a9-238">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="da4a9-239">步骤 5：删除"可恢复项目"文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="da4a9-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="da4a9-240">现在，您可以使用 Exchange 在线 PowerShell 中的[搜索邮箱](https://go.microsoft.com/fwlink/?linkid=852595)cmdlet 实际删除"可恢复项目"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-240">Now you're ready to actually delete items in the Recoverable Items folder by using the [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="da4a9-241">运行**搜索邮箱**cmdlet 时，有三个选项。</span><span class="sxs-lookup"><span data-stu-id="da4a9-241">You have three options when running the **Search-Mailbox** cmdlet.</span></span> 
  
- <span data-ttu-id="da4a9-242">在删除项目之前，将项目复制到目标邮箱，以便在必要时在删除项目之前查看这些项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-242">Copy items to a target mailbox before you delete them so that you can review the items, if necessary, before you delete them.</span></span>
    
- <span data-ttu-id="da4a9-243">将项目复制到目标邮箱，并在同一命令中删除它们。</span><span class="sxs-lookup"><span data-stu-id="da4a9-243">Copy items to a target mailbox and delete them in the same command.</span></span>
    
- <span data-ttu-id="da4a9-244">删除项目而不将其复制到目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-244">Delete items without copying them to a target mailbox.</span></span> 
    
<span data-ttu-id="da4a9-245">请注意，在运行**搜索邮箱**cmdlet 时，用户主存档邮箱中的"可恢复项目"文件夹中的项目也将被删除。</span><span class="sxs-lookup"><span data-stu-id="da4a9-245">Note that items in the Recoverable Items folder in the user's primary archive mailbox will also be deleted when you run the **Search-Mailbox** cmdlet.</span></span> <span data-ttu-id="da4a9-246">为了防止这种情况，您可以*包括"不包含存档"* 开关。</span><span class="sxs-lookup"><span data-stu-id="da4a9-246">To prevent this, you can include the  *DoNotIncludeArchive*  switch.</span></span> <span data-ttu-id="da4a9-247">如前所述，如果为邮箱启用了自动展开存档，则 [搜索邮箱 ] cmdlet 不会删除辅助存档邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-247">And as previously stated, if auto-expanding archiving is enabled for the mailbox, the \*\* Search-Mailbox \*\* cmdlet doesn't deleted items in an auxiliary archive mailbox.</span></span> <span data-ttu-id="da4a9-248">有关自动扩展存档的详细信息，请参阅 Office [365 中无限制存档概述。](unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="da4a9-248">For more information about auto-expanding archive, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="da4a9-249">如果包含搜索查询（通过使用*搜索查询*参数），**搜索邮箱**cmdlet 将在搜索结果中返回最多 10，000 个项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-249">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results.</span></span> <span data-ttu-id="da4a9-250">因此，如果包含搜索查询，则可能需要多次运行**搜索邮箱**命令才能删除 10，000 多个项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-250">Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
  
<span data-ttu-id="da4a9-251">以下示例显示了每个选项的命令语法。</span><span class="sxs-lookup"><span data-stu-id="da4a9-251">The following examples show the command syntax for each of these options.</span></span> <span data-ttu-id="da4a9-252">这些示例使用`-SearchQuery size>0`参数值，该值从"可恢复项目"文件夹中的所有子文件夹中删除所有项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-252">These examples use the  `-SearchQuery size>0` parameter value, which deletes all items from all subfolders in the Recoverable Items folder.</span></span> <span data-ttu-id="da4a9-253">如果只需要删除符合特定条件的项目，还可以使用*SearchQuery*参数指定其他条件，例如邮件的主题或日期范围。</span><span class="sxs-lookup"><span data-stu-id="da4a9-253">If you need to delete only items that match specific conditions, you can also use the  *SearchQuery*  parameter to specify other conditions, such as the subject of a message or a date range.</span></span> <span data-ttu-id="da4a9-254">请参阅下面的[使用搜索查询参数的其他示例。](#other-examples-of-using-the-searchquery-parameter)</span><span class="sxs-lookup"><span data-stu-id="da4a9-254">See the [other examples of using the SearchQuery parameter](#other-examples-of-using-the-searchquery-parameter) below.</span></span> 
  
### <a name="example-1"></a><span data-ttu-id="da4a9-255">範例 1</span><span class="sxs-lookup"><span data-stu-id="da4a9-255">Example 1</span></span>

<span data-ttu-id="da4a9-256">本示例将用户可恢复项目文件夹中的所有项目复制到组织的发现搜索邮箱中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="da4a9-256">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox.</span></span> <span data-ttu-id="da4a9-257">这允许您在永久删除项目之前查看它们。</span><span class="sxs-lookup"><span data-stu-id="da4a9-257">This lets you review the items before you permanently delete them.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

<span data-ttu-id="da4a9-258">在前面的示例中，不需要将项目复制到发现搜索邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-258">In the previous example, it isn't required to copy items to the Discovery Search Mailbox.</span></span> <span data-ttu-id="da4a9-259">您可以将邮件复制到任何目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-259">You can copy messages to any target mailbox.</span></span> <span data-ttu-id="da4a9-260">但是，为了防止访问可能敏感的邮箱数据，我们建议将邮件复制到访问仅限于授权人员的邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-260">However, to prevent access to potentially sensitive mailbox data, we recommend copying messages to a mailbox that has access restricted to authorized personnel.</span></span> <span data-ttu-id="da4a9-261">默认情况下，对默认发现搜索邮箱的访问仅限于 Exchange 联机中的发现管理角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="da4a9-261">By default, access to the default Discovery Search Mailbox is restricted to members of the Discovery Management role group in Exchange Online.</span></span> 
  
### <a name="example-2"></a><span data-ttu-id="da4a9-262">範例 2</span><span class="sxs-lookup"><span data-stu-id="da4a9-262">Example 2</span></span>

<span data-ttu-id="da4a9-263">本示例将用户"可恢复项目"文件夹中的所有项目复制到组织的"发现搜索邮箱"中的文件夹，然后从用户的"可恢复项目"文件夹中删除这些项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-263">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox and then deletes the items from the user's Recoverable Items folder.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a><span data-ttu-id="da4a9-264">範例 3</span><span class="sxs-lookup"><span data-stu-id="da4a9-264">Example 3</span></span>

<span data-ttu-id="da4a9-265">本示例删除用户可恢复项目文件夹中的所有项目，而不将它们复制到目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-265">This example deletes all items in the user's Recoverable Items folder, without copying them to a target mailbox.</span></span> 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a><span data-ttu-id="da4a9-266">使用搜索查询参数的其他示例</span><span class="sxs-lookup"><span data-stu-id="da4a9-266">Other examples of using the SearchQuery parameter</span></span>

<span data-ttu-id="da4a9-267">下面是使用*SearchQuery*参数查找特定消息的几个示例。</span><span class="sxs-lookup"><span data-stu-id="da4a9-267">Here are a few examples of using the  *SearchQuery*  parameter to find specific messages.</span></span> <span data-ttu-id="da4a9-268">如果使用*SearchQuery*参数搜索特定项目，请考虑将搜索结果复制到目标邮箱，以便可以查看搜索结果，然后在必要时修改查询，然后再删除搜索结果。</span><span class="sxs-lookup"><span data-stu-id="da4a9-268">If you use the  *SearchQuery*  parameter to search for specific items, consider copying the search results to a target mailbox so that you can review the search results and then revise the query if necessary before you delete the results of a search.</span></span> 
  
<span data-ttu-id="da4a9-269">此示例返回在"主题"字段中包含特定短语的消息。</span><span class="sxs-lookup"><span data-stu-id="da4a9-269">This example returns messages that contain a specific phrase in the Subject field.</span></span>
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

<span data-ttu-id="da4a9-270">此示例返回在指定日期范围内发送的消息。</span><span class="sxs-lookup"><span data-stu-id="da4a9-270">This example returns messages that were sent within the specified date range.</span></span>
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
<span data-ttu-id="da4a9-271">此示例返回发送给指定人员的消息。</span><span class="sxs-lookup"><span data-stu-id="da4a9-271">This example returns messages that were sent to the specified person.</span></span>

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="da4a9-272">验证项目是否已删除</span><span class="sxs-lookup"><span data-stu-id="da4a9-272">Verify that items were deleted</span></span>

<span data-ttu-id="da4a9-273">要验证是否已成功从邮箱的"可恢复项目"文件夹中删除项目，请使用 Exchange 在线 PowerShell 中的**获取邮箱文件夹统计**cmdlet 来检查可恢复项目文件夹中的项目大小和数量。</span><span class="sxs-lookup"><span data-stu-id="da4a9-273">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="da4a9-274">您可以将这些统计信息与步骤 1 中收集的统计信息进行比较。</span><span class="sxs-lookup"><span data-stu-id="da4a9-274">You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="da4a9-275">运行以下命令以获取用户主邮箱中可恢复项目文件夹中的文件夹和子文件夹中的当前大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="da4a9-275">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
<span data-ttu-id="da4a9-276">运行以下命令以获取用户存档邮箱中可恢复项目文件夹中文件夹和子文件夹中的项目大小和总数。</span><span class="sxs-lookup"><span data-stu-id="da4a9-276">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="da4a9-277">步骤 6：将邮箱还原到其以前的状态</span><span class="sxs-lookup"><span data-stu-id="da4a9-277">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="da4a9-278">最后一步是将邮箱还原回其以前的配置。</span><span class="sxs-lookup"><span data-stu-id="da4a9-278">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="da4a9-279">这意味着重置您在步骤 2 中更改的属性，并重新应用在步骤 3 中删除的保留。</span><span class="sxs-lookup"><span data-stu-id="da4a9-279">This means resetting the properties that you changed in Step 2 and re-applying the holds that you removed in Step 3.</span></span> <span data-ttu-id="da4a9-280">其中包括：</span><span class="sxs-lookup"><span data-stu-id="da4a9-280">This includes:</span></span>
  
- <span data-ttu-id="da4a9-281">将已删除的物料保留期更改回其以前的值。</span><span class="sxs-lookup"><span data-stu-id="da4a9-281">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="da4a9-282">或者，您可以只保留此集为 30 天，这是 Exchange 在线中的最大值。</span><span class="sxs-lookup"><span data-stu-id="da4a9-282">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="da4a9-283">重新启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="da4a9-283">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="da4a9-284">重新启用客户端访问方法，以便所有者可以访问其邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-284">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="da4a9-285">重新应用已删除的保留和 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="da4a9-285">Re-applying the holds and Office 365 retention policies that you removed.</span></span>
    
- <span data-ttu-id="da4a9-286">重新启用托管文件夹助理以处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-286">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="da4a9-287">我们建议您在重新应用保留或 Office 365 保留策略（并验证其是否就位）后等待 24 小时，然后再重新启用托管文件夹助理以处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-287">We recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="da4a9-288">在 Exchange 在线电源外壳中执行以下步骤（按指定顺序）。</span><span class="sxs-lookup"><span data-stu-id="da4a9-288">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="da4a9-289">运行以下命令，将已删除的物料保留期更改回其原始值。</span><span class="sxs-lookup"><span data-stu-id="da4a9-289">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="da4a9-290">这假定以前的设置小于 30 天;如果此设置小于 30 天，则为例如14天。</span><span class="sxs-lookup"><span data-stu-id="da4a9-290">This assumes that the previous setting is less than 30 days; for example 14 days.</span></span> 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. <span data-ttu-id="da4a9-291">运行以下命令以重新启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="da4a9-291">Run the following command to re-enable single item recovery.</span></span>
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="da4a9-292">运行以下命令以重新启用邮箱中的所有客户端访问方法。</span><span class="sxs-lookup"><span data-stu-id="da4a9-292">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. <span data-ttu-id="da4a9-293">重新应用您在步骤 3 中删除的保留。</span><span class="sxs-lookup"><span data-stu-id="da4a9-293">Re-apply the holds that you removed in Step 3.</span></span> <span data-ttu-id="da4a9-294">根据保留的类型，使用以下过程之一。</span><span class="sxs-lookup"><span data-stu-id="da4a9-294">Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="da4a9-295">**诉讼保留**</span><span class="sxs-lookup"><span data-stu-id="da4a9-295">**Litigation Hold**</span></span>
    
    <span data-ttu-id="da4a9-296">运行以下命令以重新启用邮箱的诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="da4a9-296">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="da4a9-297">**原有範圍暫止**</span><span class="sxs-lookup"><span data-stu-id="da4a9-297">**In-Place Hold**</span></span>
    
    <span data-ttu-id="da4a9-298">使用 EAC（或交换在线电源外壳）将邮箱添加回就地保留。</span><span class="sxs-lookup"><span data-stu-id="da4a9-298">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="da4a9-299">**应用于特定邮箱的 Office 365 保留策略**</span><span class="sxs-lookup"><span data-stu-id="da4a9-299">**Office 365 retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="da4a9-300">使用安全&合规性中心将邮箱添加回保留策略。</span><span class="sxs-lookup"><span data-stu-id="da4a9-300">Use the Security & Compliance Center to add the mailbox back to the retention policy.</span></span> <span data-ttu-id="da4a9-301">转到安全&合规性中心**中的"日期治理**\>**保留"** 页，编辑保留策略，并将邮箱重新添加到应用保留策略的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="da4a9-301">Go to the **Date governance** \> **Retention** page in the Security & Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="da4a9-302">**组织范围的 Office 365 保留策略**</span><span class="sxs-lookup"><span data-stu-id="da4a9-302">**Organization-wide Office 365 retention policies**</span></span>
    
    <span data-ttu-id="da4a9-303">如果通过从策略中排除而删除了组织范围或 Exchange 范围的保留策略，则使用安全&合规性中心从排除的用户列表中删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-303">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security & Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="da4a9-304">转到安全&合规性中心**中的"日期治理**\>**保留"** 页，编辑组织范围的保留策略，并从排除的收件人列表中删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-304">Go to the **Date governance** \> **Retention** page in the Security & Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="da4a9-305">这样做会将保留策略重新应用于用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-305">Doing this will re-apply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="da4a9-306">**电子数据展示案例保留**</span><span class="sxs-lookup"><span data-stu-id="da4a9-306">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="da4a9-307">使用安全&合规性中心将邮箱添加回与电子数据展示案例关联的保留状态。</span><span class="sxs-lookup"><span data-stu-id="da4a9-307">Use the Security & Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="da4a9-308">转到**电子数据展示**\>**页面，** 打开案例，并将邮箱添加回保留状态。</span><span class="sxs-lookup"><span data-stu-id="da4a9-308">Go to the **eDiscovery** \> **eDiscovery** page, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="da4a9-309">运行以下命令以允许托管文件夹助理再次处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-309">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="da4a9-310">如前所述，我们建议您在重新应用保留或 Office 365 保留策略（并验证其是否就位）后等待 24 小时，然后再重新启用托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="da4a9-310">As previously stated, we recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. <span data-ttu-id="da4a9-311">要验证邮箱是否已还原到以前的配置，可以运行以下命令，然后将这些设置与步骤 1 中收集的设置进行比较。</span><span class="sxs-lookup"><span data-stu-id="da4a9-311">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a><span data-ttu-id="da4a9-312">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="da4a9-312">More information</span></span>

<span data-ttu-id="da4a9-313">下表描述了在运行**获取邮箱**或**获取组织 Config** cmdlet 时，如何根据*InPlaceHolds*属性中的值识别不同类型的保留。</span><span class="sxs-lookup"><span data-stu-id="da4a9-313">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="da4a9-314">有关详细信息，请参阅[如何识别放在 Exchange 联机邮箱上的保留类型。](identify-a-hold-on-an-exchange-online-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="da4a9-314">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="da4a9-315">如前所述，您必须从邮箱中删除所有保留和 Office 365 保留策略，然后才能成功删除"可恢复项目"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="da4a9-315">As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="da4a9-316">**保持类型**</span><span class="sxs-lookup"><span data-stu-id="da4a9-316">**Hold type**</span></span>|<span data-ttu-id="da4a9-317">**範例值**</span><span class="sxs-lookup"><span data-stu-id="da4a9-317">**Example value**</span></span>|<span data-ttu-id="da4a9-318">**如何识别保持**</span><span class="sxs-lookup"><span data-stu-id="da4a9-318">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="da4a9-319">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="da4a9-319">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="da4a9-320">*诉讼保留属性*设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="da4a9-320">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="da4a9-321">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="da4a9-321">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="da4a9-322">*InPlaceHolds*属性包含放置在邮箱上的就地保持的 GUID。</span><span class="sxs-lookup"><span data-stu-id="da4a9-322">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="da4a9-323">您可以判断这是就地保留，因为 GUID 不以前缀开头。</span><span class="sxs-lookup"><span data-stu-id="da4a9-323">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="da4a9-324">您可以使用 Exchange`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`联机 PowerShell 中的命令来获取有关邮箱就地保留的信息。</span><span class="sxs-lookup"><span data-stu-id="da4a9-324">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="da4a9-325">安全&合规性中心的 Office 365 保留策略应用于特定邮箱</span><span class="sxs-lookup"><span data-stu-id="da4a9-325">Office 365 retention policies in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="da4a9-326">或</span><span class="sxs-lookup"><span data-stu-id="da4a9-326">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="da4a9-327">运行**获取邮箱**cmdlet 时，InPlaceHolds 属性还包含应用于邮箱的 Office 365 保留策略的 GUID。 \*\*</span><span class="sxs-lookup"><span data-stu-id="da4a9-327">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox.</span></span> <span data-ttu-id="da4a9-328">您可以标识保留策略，因为 GUID 以`mbx`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="da4a9-328">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="da4a9-329">请注意，如果保留策略的 GUID 以`skp`前缀开头，则表示保留策略应用于 Skype 业务对话。</span><span class="sxs-lookup"><span data-stu-id="da4a9-329">Note that if the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="da4a9-330">要标识应用于邮箱的 Office 365 保留策略，在安全&合规性中心 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="da4a9-330">To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="da4a9-331">运行此命令时，`mbx`请确保`skp`删除 或 前缀。</span><span class="sxs-lookup"><span data-stu-id="da4a9-331">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="da4a9-332">安全&合规性中心中的组织范围 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="da4a9-332">Organization-wide Office 365 retention policies in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="da4a9-333">无值</span><span class="sxs-lookup"><span data-stu-id="da4a9-333">No value</span></span>  <br/> <span data-ttu-id="da4a9-334">或</span><span class="sxs-lookup"><span data-stu-id="da4a9-334">or</span></span>  <br/>  <span data-ttu-id="da4a9-335">`-mbxe9b52bf7ab3b46a286308ecb29624696`（指示邮箱从组织范围的策略中排除）</span><span class="sxs-lookup"><span data-stu-id="da4a9-335">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="da4a9-336">即使运行**Get-Mailbox** cmdlet 时*InPlaceHolds*属性为空，仍可能将一个或多个组织范围的 Office 365 保留策略应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="da4a9-336">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="da4a9-337">为了验证这一点，您可以在`Get-OrganizationConfig | FL InPlaceHolds`Exchange Online PowerShell 中运行该命令，以获取组织范围 Office 365 保留策略的 GUID 列表。</span><span class="sxs-lookup"><span data-stu-id="da4a9-337">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies.</span></span> <span data-ttu-id="da4a9-338">应用于 Exchange 邮箱的组织范围保留策略的 GUID 以`mbx`前缀开头;例如`mbxa3056bb15562480fadb46ce523ff7b02`.</span><span class="sxs-lookup"><span data-stu-id="da4a9-338">The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="da4a9-339">要标识应用于邮箱的组织范围 Office 365 保留策略，在"安全&合规性中心 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="da4a9-339">To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="da4a9-340">请注意，如果邮箱从组织范围的 Office 365 保留策略中排除，则在运行**Get-邮箱**cmdlet 时，保留策略的 GUID 将显示在用户邮箱的 InPlaceHolds 属性中;如果邮箱从组织范围的 Office 365 保留策略中排除，则保留策略的 GUID 将显示在用户邮箱的*InPlaceHolds*属性中。由前缀`-mbx`标识;例如，`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="da4a9-340">Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="da4a9-341">安全&合规中心持有电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="da4a9-341">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="da4a9-342">*InPlaceHolds*属性还包含与可能放置在邮箱的安全&合规性中心中电子数据展示案例关联的任何保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="da4a9-342">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="da4a9-343">可以判断这是一个电子数据展示案例保留，因为 GUID 以`UniH`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="da4a9-343">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="da4a9-344">您可以使用安全&合规性`Get-CaseHoldPolicy`中心 PowerShell 中的 cmdlet 来获取有关邮箱保留关联的电子数据展示案例的信息。</span><span class="sxs-lookup"><span data-stu-id="da4a9-344">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="da4a9-345">例如，可以运行该命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`来显示邮箱上的案例保留的名称。</span><span class="sxs-lookup"><span data-stu-id="da4a9-345">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="da4a9-346">运行此命令时，`UniH`请确保删除前缀。</span><span class="sxs-lookup"><span data-stu-id="da4a9-346">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="da4a9-347">要标识邮箱上的保留与之关联的电子数据展示案例，应运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="da4a9-347">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


