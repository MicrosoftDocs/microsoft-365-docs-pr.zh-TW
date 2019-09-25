---
title: 为 Office 365 组织中的邮箱设置存档和删除策略
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
- MED150
- MBS150
- BCS160
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
description: 在 Office 365 中创建存档和删除策略，该策略会自动将项目移动到用户的存档邮箱。
ms.openlocfilehash: ca43498d785f1a5525a8159e7e553bd36257a7c2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077400"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-office-365-organization"></a><span data-ttu-id="8e667-103">为 Office 365 组织中的邮箱设置存档和删除策略</span><span class="sxs-lookup"><span data-stu-id="8e667-103">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>

 <span data-ttu-id="8e667-104">在 Office 365 中，管理员可以创建存档和删除策略，该策略会自动将项目移动到用户的存档邮箱，并自动从邮箱中删除项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-104">In Office 365, admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span> <span data-ttu-id="8e667-105">管理员通过创建分配给邮箱的保留策略来这样做，并在一段时间后将项目移动到用户的存档邮箱，并在项目达到特定期限后从邮箱中删除这些项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-105">The admin does this by creating a retention policy that's assigned to mailboxes, and moves items to a user's archive mailbox after a certain period of time and that also deletes items from the mailbox after they reach a certain age limit.</span></span> <span data-ttu-id="8e667-106">确定移动或删除哪些项以及何时移动和删除的实际规则称为保留标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-106">The actual rules that determine what items are moved or deleted and when that happens are called retention tags.</span></span> <span data-ttu-id="8e667-107">保留标记链接到保留策略，而保留策略又分配给用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-107">Retention tags are linked to a retention policy, that in turn is assigned to a user's mailbox.</span></span> <span data-ttu-id="8e667-108">保留标记将保留设置应用于用户邮箱中的单个邮件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="8e667-108">A retention tag applies retention settings to individual messages and folders in a user's mailbox.</span></span> <span data-ttu-id="8e667-109">它定义邮件在邮箱中保留的时间，以及当邮件达到指定的保留期限时，将执行什么操作。</span><span class="sxs-lookup"><span data-stu-id="8e667-109">It defines how long a message remains in the mailbox and what action is taken when the message reaches the specified retention age.</span></span> <span data-ttu-id="8e667-110">当邮件达到保留期时，邮件将移动到用户的存档邮箱或被删除。</span><span class="sxs-lookup"><span data-stu-id="8e667-110">When a message reaches its retention age, it's either moved to the user's archive mailbox or it's deleted.</span></span> 
  
<span data-ttu-id="8e667-111">本文中的步骤将为名为"Alpine House"的虚构组织设置存档和保留策略。</span><span class="sxs-lookup"><span data-stu-id="8e667-111">The steps in this article will set up an archiving and retention policy for a fictitious organization named Alpine House.</span></span> <span data-ttu-id="8e667-112">设置此策略包括以下任务：</span><span class="sxs-lookup"><span data-stu-id="8e667-112">Setting up this policy includes the following tasks:</span></span>
  
- <span data-ttu-id="8e667-113">为组织中的每个用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-113">Enabling an archive mailbox for every user in the organization.</span></span> <span data-ttu-id="8e667-114">这为用户提供了添加邮箱存储，并且是必需的，以便保留策略可以将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-114">This gives users addition mailbox storage, and is required so that a retention policy can move items to the archive mailbox.</span></span> <span data-ttu-id="8e667-115">它还允许用户通过将项目移动到其存档邮箱来存储存档信息。</span><span class="sxs-lookup"><span data-stu-id="8e667-115">It also let's a user store archival information by moving items to their archive mailbox.</span></span> 
    
- <span data-ttu-id="8e667-116">创建三个自定义保留标记，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8e667-116">Creating three custom retention tags that do the following:</span></span> 
    
  - <span data-ttu-id="8e667-117">自动将 3 年的项目移动到用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-117">Automatically moves items that are 3 years old to the user's archive mailbox.</span></span> <span data-ttu-id="8e667-118">将项目移动到存档邮箱将释放用户主邮箱中的空间。</span><span class="sxs-lookup"><span data-stu-id="8e667-118">Moving items to the archive mailbox frees up space in a user's primary mailbox.</span></span>
    
  - <span data-ttu-id="8e667-119">自动从"已删除项目"文件夹中删除具有 5 年历史的项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-119">Automatically deletes items that are 5 years old from the Deleted Items folder.</span></span> <span data-ttu-id="8e667-120">这还会释放用户主邮箱中的空间。</span><span class="sxs-lookup"><span data-stu-id="8e667-120">This also frees up space in the user's primary mailbox.</span></span> <span data-ttu-id="8e667-121">如有必要，用户将有机会恢复这些项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-121">User's will have the opportunity to recover these items if necessary.</span></span> <span data-ttu-id="8e667-122">有关详细信息，[请参阅"详细信息"](#more-information)部分中的脚注。</span><span class="sxs-lookup"><span data-stu-id="8e667-122">See the footnote in the [More information](#more-information) section for more details.</span></span> 
    
  - <span data-ttu-id="8e667-123">自动（并永久）从主邮箱和存档邮箱中删除具有 7 年历史的项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-123">Automatically (and permanently) deletes items that are 7 years old from both the primary and archive mailbox.</span></span> <span data-ttu-id="8e667-124">由于合规性法规，某些组织需要将电子邮件保留一段时间。</span><span class="sxs-lookup"><span data-stu-id="8e667-124">Because of compliance regulations, some organization's are required to retain email for a certain period of time.</span></span> <span data-ttu-id="8e667-125">此时间段过期后，组织可能希望永久删除这些项目用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-125">After this time period expires, an organization might want to permanently remove these items user mailboxes.</span></span> 
    
- <span data-ttu-id="8e667-126">创建新的保留策略，并将新的自定义保留标记添加到其中。</span><span class="sxs-lookup"><span data-stu-id="8e667-126">Creating a new retention policy and adding the new custom retention tags to it.</span></span> <span data-ttu-id="8e667-127">此外，您还将将内置保留标记添加到新的保留策略中。</span><span class="sxs-lookup"><span data-stu-id="8e667-127">Additionally, you'll also add built-in retention tags to the new retention policy.</span></span> <span data-ttu-id="8e667-128">这包括用户可以分配给其邮箱中的项目的个人标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-128">This includes personal tags that users can assign to items in their mailbox.</span></span> <span data-ttu-id="8e667-129">您还将添加一个保留标记，将项目从用户主邮箱中的"可恢复项目"文件夹中移动到其存档邮箱中的"可恢复项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="8e667-129">You'll also add a retention tag that moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="8e667-130">这有助于在用户的邮箱置于保留状态时释放用户可恢复项目文件夹中的空间。</span><span class="sxs-lookup"><span data-stu-id="8e667-130">This helps free up space in a user's Recoverable Items folder when their mailbox is placed on hold.</span></span>
    
<span data-ttu-id="8e667-131">您可以按照本文中的部分或全部步骤为您自己的组织中的邮箱设置存档和删除策略。</span><span class="sxs-lookup"><span data-stu-id="8e667-131">You can follow some or all of the steps in this article to set up an archive and deletion policy for mailboxes in your own organization.</span></span> <span data-ttu-id="8e667-132">我们建议您在组织中的所有邮箱上实现此过程之前，先在几个邮箱上测试此过程。</span><span class="sxs-lookup"><span data-stu-id="8e667-132">We recommend that you test this process on a few mailboxes before implementing it on all mailboxes in your organization.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="8e667-133">開始之前</span><span class="sxs-lookup"><span data-stu-id="8e667-133">Before you begin</span></span>

- <span data-ttu-id="8e667-134">您必须是 Office 365 组织的全局管理员才能执行本主题中的步骤。</span><span class="sxs-lookup"><span data-stu-id="8e667-134">You have to be a global administrator in your Office 365 organization to perform the steps in this topic.</span></span> 
    
-  <span data-ttu-id="8e667-135">当您在 Office 365 中创建新用户帐户并为用户分配 Exchange Online 许可证时，将自动为用户创建邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-135">When you create a new user account in Office 365 and assign the user an Exchange Online license, a mailbox is automatically created for the user.</span></span> <span data-ttu-id="8e667-136">创建邮箱后，将自动为其分配默认保留策略，名为"默认 MRM 策略"。</span><span class="sxs-lookup"><span data-stu-id="8e667-136">When the mailbox is created, it's automatically assigned a default retention policy, named Default MRM Policy.</span></span> <span data-ttu-id="8e667-137">在本文中，您将创建新的保留策略，然后将其分配给用户邮箱，以替换默认 MRM 策略。</span><span class="sxs-lookup"><span data-stu-id="8e667-137">In this article, you will create a new retention policy and then assign it to user mailboxes, replacing the Default MRM policy.</span></span> <span data-ttu-id="8e667-138">邮箱一次只能分配一个保留策略。</span><span class="sxs-lookup"><span data-stu-id="8e667-138">A mailbox can have only one retention policy assigned to it at any one time.</span></span>
    
- <span data-ttu-id="8e667-139">要了解有关 Exchange 联机保留标记和保留策略的信息，请参阅[保留标记和保留策略](https://go.microsoft.com/fwlink/p/?LinkId=404424)。</span><span class="sxs-lookup"><span data-stu-id="8e667-139">To learn more about retention tags and retention policies in Exchange Online, see [Retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424).</span></span>
    
## <a name="step-1-enable-archive-mailboxes-for-users"></a><span data-ttu-id="8e667-140">步骤 1：为用户启用存档邮箱</span><span class="sxs-lookup"><span data-stu-id="8e667-140">Step 1: Enable archive mailboxes for users</span></span>

<span data-ttu-id="8e667-141">第一步是为组织中的每个用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-141">The first step is to enable the archive mailbox for each user in your organization.</span></span> <span data-ttu-id="8e667-142">必须启用用户的存档邮箱，以便具有"移动到存档"保留操作的保留标记可以在保留期限到期后移动项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-142">A user's archive mailbox has to be enabled so that a retention tag with a "Move to Archive" retention action can move the item after the retention age expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8e667-143">在此过程中，您可以随时启用存档邮箱，只要在完成此过程之前的某个时间启用这些邮箱即可。</span><span class="sxs-lookup"><span data-stu-id="8e667-143">You can enable archive mailboxes any time during this process, just as long as they're enabled at some point before you complete the process.</span></span> <span data-ttu-id="8e667-144">如果未启用存档邮箱，则不对为其分配存档策略的任何项目执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="8e667-144">If an archive mailbox isn't enabled, no action is taken on any items that have an archive policy assigned to it.</span></span> 
  
1. <span data-ttu-id="8e667-145">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="8e667-145">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="8e667-146">Sign in to Office 365 using your global administrator account.</span><span class="sxs-lookup"><span data-stu-id="8e667-146">Sign in to Office 365 using your global administrator account.</span></span>
    
    
3. <span data-ttu-id="8e667-147">在安全&合规性中心，转到**数据治理**\>**存档**。</span><span class="sxs-lookup"><span data-stu-id="8e667-147">In the Security & Compliance Center, go to **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="8e667-148">将显示组织中的邮箱列表以及是否启用或禁用相应的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-148">A list of the mailboxes in your organization is displayed and whether the corresponding archive mailbox is enabled or disabled.</span></span> 
    
4. <span data-ttu-id="8e667-149">通过单击列表中的第一个邮箱，按住**Shift**键，然后单击列表中的最后一个邮箱，选择所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-149">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="8e667-150">此步骤假定未启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-150">This step assumes that no archive mailboxes are enabled.</span></span> <span data-ttu-id="8e667-151">如果您有任何启用了存档的邮箱，请按住**Ctrl**键并单击具有禁用存档邮箱的每个邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-151">If you have any mailboxes with the archive enabled, hold down the **Ctrl** key and click each mailbox that has a disabled archive mailbox.</span></span> <span data-ttu-id="8e667-152">或者，您可以**单击"存档邮箱"** 列标题，根据是否启用或禁用存档邮箱对行进行排序，以便更轻松地选择邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-152">Or you can click the **Archive mailbox** column header to sort the rows based on whether the archive mailbox is enabled or disabled to make it easier to select mailboxes.</span></span> 
  
5. <span data-ttu-id="8e667-153">在详细信息窗格中，**在"批量编辑"** 下单击"**启用"。**</span><span class="sxs-lookup"><span data-stu-id="8e667-153">In the details pane, under **Bulk Edit**, click **Enable**.</span></span>
    
    <span data-ttu-id="8e667-154">将显示一条警告，指出超过两年的项目将移动到新的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-154">A warning is displayed saying that items that are older than two years will be moved to the new archive mailbox.</span></span> <span data-ttu-id="8e667-155">这是因为在创建时分配了新用户邮箱的默认保留策略具有保留期为 2 年的存档默认策略标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-155">This is because the default retention policy that's assigned a new user mailbox when it's created has an archive default policy tag that has a retention age of 2 years.</span></span> <span data-ttu-id="8e667-156">您将在步骤 2 中创建的自定义存档默认策略标记的保留期为 3 年。</span><span class="sxs-lookup"><span data-stu-id="8e667-156">The custom archive default policy tag that you'll create in Step 2 has a retention age of 3 years.</span></span> <span data-ttu-id="8e667-157">这意味着 3 年或 3 年以上的项目将移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-157">That means items that are 3 years or older will be moved to the archive mailbox.</span></span>
    
6. <span data-ttu-id="8e667-158">单击"**是"** 关闭警告邮件并启动进程以启用每个选定邮箱的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-158">Click **Yes** to close the warning message and start the process to enable the archive mailbox for each selected mailbox.</span></span> 
    
7. <span data-ttu-id="8e667-159">该过程完成后，**单击"刷新**![刷新"](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)以**更新"存档"** 页上的列表。</span><span class="sxs-lookup"><span data-stu-id="8e667-159">When the process is complete, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the list on the **Archive** page.</span></span> 
    
    <span data-ttu-id="8e667-160">为组织中的所有用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-160">The archive mailbox is enabled for all user's in your organization.</span></span>
    
    ![启用存档邮箱的邮箱列表](media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)
  
8. <span data-ttu-id="8e667-162">保持安全&合规中心打开状态。</span><span class="sxs-lookup"><span data-stu-id="8e667-162">Leave the Security & Compliance Center open.</span></span> <span data-ttu-id="8e667-163">您将在下一步中使用它。</span><span class="sxs-lookup"><span data-stu-id="8e667-163">You'll use it in the next step.</span></span>
    
## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a><span data-ttu-id="8e667-164">步骤 2：为存档和删除策略创建新的保留标记</span><span class="sxs-lookup"><span data-stu-id="8e667-164">Step 2: Create new retention tags for the archive and deletion policies</span></span>

<span data-ttu-id="8e667-165">在此步骤中，您将创建前面描述的三个自定义保留标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-165">In this step, you'll create the three custom retention tags that were previously described.</span></span>
  
- <span data-ttu-id="8e667-166">阿尔卑斯之家 3 年移动到存档（自定义存档政策）</span><span class="sxs-lookup"><span data-stu-id="8e667-166">Alpine House 3 Year Move to Archive (custom archive policy)</span></span>
    
- <span data-ttu-id="8e667-167">阿尔卑斯房子7年永久删除（自定义删除政策）</span><span class="sxs-lookup"><span data-stu-id="8e667-167">Alpine House 7 Year Permanently Delete (custom deletion policy)</span></span>
    
- <span data-ttu-id="8e667-168">阿尔卑斯房子删除项目 5 年删除和允许恢复 （自定义标签的已删除项目文件夹）</span><span class="sxs-lookup"><span data-stu-id="8e667-168">Alpine House Deleted Items 5 Years Delete and Allow Recovery (custom tag for the Deleted Items folder)</span></span>
    
<span data-ttu-id="8e667-169">要创建新的保留标记，您将在 Exchange 在线组织中使用 Exchange 管理中心 （EAC）。</span><span class="sxs-lookup"><span data-stu-id="8e667-169">To create new retention tags, you'll use the Exchange admin center (EAC) in your Exchange Online organization.</span></span>
  
1. <span data-ttu-id="8e667-170">在"安全&合规性中心"中，单击左上角的应用启动器，**然后单击"管理"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="8e667-170">In the Security & Compliance Center, click the app launcher  in the upper left corner, and then click the **Admin** tile .</span></span> 
    
2. <span data-ttu-id="8e667-171">在 Microsoft 365 管理中心的左侧导航窗格中，**单击"管理中心"，\*\*\*\*然后单击"交换"。**</span><span class="sxs-lookup"><span data-stu-id="8e667-171">In the left navigation pane of the Microsoft 365 admin center, click **Admin centers**, and then click **Exchange**.</span></span>
    
    ![屏幕截图显示 Microsoft 365 管理中心，其中"管理中心"选项已展开，并选择了"交换"。](media/47399df2-0bc4-42e2-b183-07750a46bc68.png)
  
3. <span data-ttu-id="8e667-173">在 EAC 中，转到**合规性管理**\>**保留标记**</span><span class="sxs-lookup"><span data-stu-id="8e667-173">In the EAC, go to **Compliance management** \> **Retention tags**</span></span>
    
    <span data-ttu-id="8e667-174">将显示组织的保留标记列表。</span><span class="sxs-lookup"><span data-stu-id="8e667-174">A list of the retention tags for your organization is displayed.</span></span>
    
### <a name="create-a-custom-archive-default-policy-tag"></a><span data-ttu-id="8e667-175">创建自定义存档默认策略标记</span><span class="sxs-lookup"><span data-stu-id="8e667-175">Create a custom archive default policy tag</span></span>
  
<span data-ttu-id="8e667-176">首先，您将创建一个自定义存档默认策略标记 （DPT），该标记将在 3 年后将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-176">First, you'll create a custom archive default policy tag (DPT) that will move items to the archive mailbox after 3 years.</span></span> 
  
1. <span data-ttu-id="8e667-177">在"**保留标记"** 页上，**单击"新建"图标，**![](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)然后选择**自动应用于整个邮箱（默认）。**</span><span class="sxs-lookup"><span data-stu-id="8e667-177">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="8e667-178">在**自动应用于整个邮箱（默认）的"新建"标记**上，完成以下字段：</span><span class="sxs-lookup"><span data-stu-id="8e667-178">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![创建新存档默认策略标记的设置](media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
1. <span data-ttu-id="8e667-180">**名称**键入新保留标记的名称。</span><span class="sxs-lookup"><span data-stu-id="8e667-180">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="8e667-181">**保留操作\*\*\*\*选择"移动到存档"，** 在保留期到期时将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-181">**Retention action** Select **Move to Archive** to move items to the archive mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="8e667-182">**保留期**选择**当项目达到以下年龄（以天）** 时，然后输入保留期的持续时间。</span><span class="sxs-lookup"><span data-stu-id="8e667-182">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="8e667-183">对于此方案，项目将在 1095 天（3 年）后移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-183">For this scenario, items will be moved to the archive mailbox after 1095 days (3 years).</span></span>
    
4. <span data-ttu-id="8e667-184">**评论**（可选）键入一个注释来解释自定义保留标记的用途。</span><span class="sxs-lookup"><span data-stu-id="8e667-184">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="8e667-185">**单击"保存"** 以创建自定义存档 DPT。</span><span class="sxs-lookup"><span data-stu-id="8e667-185">Click **Save** to create the custom archive DPT.</span></span> 
    
    <span data-ttu-id="8e667-186">新的存档 DPT 将显示在保留标记列表中。</span><span class="sxs-lookup"><span data-stu-id="8e667-186">The new archive DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-deletion-default-policy-tag"></a><span data-ttu-id="8e667-187">创建自定义删除默认策略标记</span><span class="sxs-lookup"><span data-stu-id="8e667-187">Create a custom deletion default policy tag</span></span>
  
<span data-ttu-id="8e667-188">接下来，您将创建另一个自定义 DPT，但此策略将是一个删除策略，在 7 年后永久删除项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-188">Next, you'll create another custom DPT but this one will be a deletion policy that permanently deletes items after 7 years.</span></span>
  
1. <span data-ttu-id="8e667-189">在"**保留标记"** 页上，**单击"新建"图标，**![](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)然后选择**自动应用于整个邮箱（默认）。**</span><span class="sxs-lookup"><span data-stu-id="8e667-189">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="8e667-190">在**自动应用于整个邮箱（默认）的"新建"标记**上，完成以下字段：</span><span class="sxs-lookup"><span data-stu-id="8e667-190">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![设置以创建新的删除默认策略标记](media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
1. <span data-ttu-id="8e667-192">**名称**键入新保留标记的名称。</span><span class="sxs-lookup"><span data-stu-id="8e667-192">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="8e667-193">**保留操作\*\*\*\*选择"永久删除"** 以在保留期到期时从邮箱中清除项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-193">**Retention action** Select **Permanently Delete** to purge items from the mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="8e667-194">**保留期**选择**当项目达到以下年龄（以天）** 时，然后输入保留期的持续时间。</span><span class="sxs-lookup"><span data-stu-id="8e667-194">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="8e667-195">对于此方案，项目将在 2555 天（7 年）后清除。</span><span class="sxs-lookup"><span data-stu-id="8e667-195">For this scenario, items will be purged after 2555 days (7 years).</span></span>
    
4. <span data-ttu-id="8e667-196">**评论**（可选）键入一个注释来解释自定义保留标记的用途。</span><span class="sxs-lookup"><span data-stu-id="8e667-196">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="8e667-197">**单击"保存"** 以创建自定义删除 DPT。</span><span class="sxs-lookup"><span data-stu-id="8e667-197">Click **Save** to create the custom deletion DPT.</span></span> 
    
    <span data-ttu-id="8e667-198">新的删除 DPT 将显示在保留标记列表中。</span><span class="sxs-lookup"><span data-stu-id="8e667-198">The new deletion DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a><span data-ttu-id="8e667-199">为"已删除项目"文件夹创建自定义保留策略标记</span><span class="sxs-lookup"><span data-stu-id="8e667-199">Create a custom retention policy tag for the Deleted Items folder</span></span>
  
<span data-ttu-id="8e667-200">您将创建的最后一个保留标记是"已删除项目"文件夹的自定义保留策略标记 （RPT）。</span><span class="sxs-lookup"><span data-stu-id="8e667-200">The last retention tag that you'll create is a custom retention policy tag (RPT) for the Deleted Items folder.</span></span> <span data-ttu-id="8e667-201">此标记将在 5 年后删除"已删除项目"文件夹中的项目，并提供一个恢复期，用户可以使用"恢复已删除项目"工具恢复项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-201">This tag will delete items in the Deleted Items folder after 5 years, and provides a recovery period when users can use the Recover Deleted Items tool to recover an item.</span></span>
  
1. <span data-ttu-id="8e667-202">在"**保留标记"** 页上，**单击"新建"图标，**![](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)然后选择**自动应用于默认文件夹**。</span><span class="sxs-lookup"><span data-stu-id="8e667-202">On the **Retention tags** page, click **New tag** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to a default folder**.</span></span> 
    
2. <span data-ttu-id="8e667-203">在**自动应用于默认文件夹页的"新建"标记**上，完成以下字段：</span><span class="sxs-lookup"><span data-stu-id="8e667-203">On the **New tag applied automatically to a default folder** page, complete the following fields:</span></span> 
    
    ![为"已删除项目"文件夹创建新的保留策略标记的设置](media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
1. <span data-ttu-id="8e667-205">**名称**键入新保留标记的名称。</span><span class="sxs-lookup"><span data-stu-id="8e667-205">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="8e667-206">**将此标记应用于以下默认文件夹**在下拉列表中，**选择"已删除项目"。**</span><span class="sxs-lookup"><span data-stu-id="8e667-206">**Apply this tag to the following default folder** In the drop-down list, select **Deleted Items**.</span></span>
    
3. <span data-ttu-id="8e667-207">**保留操作\*\*\*\*选择"删除"和"允许恢复"，** 以便在保留期到期时删除项目，但允许用户在已删除的项目保留期内（默认情况下为 14 天）恢复已删除的项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-207">**Retention action** Select **Delete and Allow Recovery** to delete items when the retention period expires, but allow users to recover a deleted item within the deleted item retention period (which by default is 14 days).</span></span> 
    
4. <span data-ttu-id="8e667-208">**保留期**选择**当项目达到以下年龄（以天）** 时，然后输入保留期的持续时间。</span><span class="sxs-lookup"><span data-stu-id="8e667-208">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="8e667-209">对于此方案，项目将在 1825 天（5 年）后删除。</span><span class="sxs-lookup"><span data-stu-id="8e667-209">For this scenario, items will be deleted after 1825 days (5 years).</span></span>
    
5. <span data-ttu-id="8e667-210">**评论**（可选）键入一个注释来解释自定义保留标记的用途。</span><span class="sxs-lookup"><span data-stu-id="8e667-210">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="8e667-211">**单击"保存"** 为"已删除项目"文件夹创建自定义 RPT。</span><span class="sxs-lookup"><span data-stu-id="8e667-211">Click **Save** to create the custom RPT for the Deleted Items folder.</span></span> 
    
    <span data-ttu-id="8e667-212">新的 RPT 显示在保留标记列表中。</span><span class="sxs-lookup"><span data-stu-id="8e667-212">The new RPT is displayed in the list of retention tags.</span></span>

## <a name="step-3-create-a-new-retention-policy"></a><span data-ttu-id="8e667-213">步骤 3：创建新的保留策略</span><span class="sxs-lookup"><span data-stu-id="8e667-213">Step 3: Create a new retention policy</span></span>

<span data-ttu-id="8e667-214">创建自定义保留标记后，下一步是创建新的保留策略并添加保留标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-214">After you create the custom retention tags, the next step is to create a new retention policy and add the retention tags.</span></span> <span data-ttu-id="8e667-215">您将添加在步骤 2 中创建的三个自定义保留标记，以及第一部分中提到的内置标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-215">You'll add the three custom retention tags that you created in Step 2, and the built-in tags that were mentioned in the first section.</span></span> <span data-ttu-id="8e667-216">在步骤 4 中，您将为此新的保留策略分配给用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-216">In Step 4, you'll assign this new retention policy to user mailboxes.</span></span>
  
1. <span data-ttu-id="8e667-217">在 EAC 中，转到**合规性管理**\>**保留策略**。</span><span class="sxs-lookup"><span data-stu-id="8e667-217">In the EAC, go to **Compliance management** \> **Retention policies**.</span></span>
    
2. <span data-ttu-id="8e667-218">在"**保留策略"** 页上，**单击"新建"**![图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)。</span><span class="sxs-lookup"><span data-stu-id="8e667-218">On the **Retention policies** page, click **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
3. <span data-ttu-id="8e667-219">在"**名称"** 框中，键入新保留策略的名称;如果键入新保留策略的名称，则键入名称。例如，**阿尔卑斯房屋档案和删除政策。**</span><span class="sxs-lookup"><span data-stu-id="8e667-219">In the **Name** box, type a name for the new retention policy; for example, **Alpine House Archive and Deletion Policy**.</span></span> 
    
4. <span data-ttu-id="8e667-220">**在"保留"标记**下，**单击"添加新"**![图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)。</span><span class="sxs-lookup"><span data-stu-id="8e667-220">Under **Retention tags**, click **Add** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
    <span data-ttu-id="8e667-221">将显示组织中保留标记的列表。</span><span class="sxs-lookup"><span data-stu-id="8e667-221">A list of the retention tags in your organization is displayed.</span></span> <span data-ttu-id="8e667-222">请注意，将显示您在步骤 2 中创建的自定义标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-222">Note the custom tags that you created in Step 2 are displayed.</span></span>
    
5. <span data-ttu-id="8e667-223">添加以下屏幕截图中突出显示的 9 个保留标记（这些标记[在"详细信息"](#more-information)部分中进行了更详细的描述）。</span><span class="sxs-lookup"><span data-stu-id="8e667-223">Add the 9 retention tags that are highlighted in the following screenshot (these tags are described in more detail in the [More information](#more-information) section).</span></span> <span data-ttu-id="8e667-224">要添加保留标记，请选择它，然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="8e667-224">To add a retention tag, select it and then click **Add**.</span></span> 
    
    ![将保留标记添加到新的保留策略](media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > <span data-ttu-id="8e667-226">您可以通过按住**Ctrl**键，然后单击每个标记来选择多个保留标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-226">You can select multiple retention tags by holding down the **Ctrl** key and then clicking each tag.</span></span> 
  
6. <span data-ttu-id="8e667-227">添加保留标记后，单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="8e667-227">After you've added the retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="8e667-228">在"**新建保留策略"** 页上，**单击"保存"** 以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="8e667-228">On the **New retention policy** page, click **Save** to create the new policy.</span></span> 
    
    <span data-ttu-id="8e667-229">新的保留策略将显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="8e667-229">The new retention policy is displayed in the list.</span></span> <span data-ttu-id="8e667-230">选择它可显示链接到详细信息窗格中的保留标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-230">Select it to display the retention tags linked to it in the details pane.</span></span>
    
    ![新的保留策略和链接的保留标记列表](media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a><span data-ttu-id="8e667-232">步骤 4：将新的保留策略分配给用户邮箱</span><span class="sxs-lookup"><span data-stu-id="8e667-232">Step 4: Assign the new retention policy to user mailboxes</span></span>

<span data-ttu-id="8e667-233">创建新邮箱时，默认情况下会为其分配名为"默认 MRM"的策略。</span><span class="sxs-lookup"><span data-stu-id="8e667-233">When a new mailbox is created, a retention policy named Default MRM policy is assigned to it by default.</span></span> <span data-ttu-id="8e667-234">在此步骤中，您将通过将在步骤 3 中创建的新保留策略分配给组织中的用户邮箱来替换此保留策略（因为邮箱只能为其分配一个保留策略）。</span><span class="sxs-lookup"><span data-stu-id="8e667-234">In this step, you'll replace this retention policy (because a mailbox can have only one retention policy assigned to it) by assigning the new retention policy that you created in Step 3 to the user mailboxes in your organization.</span></span> <span data-ttu-id="8e667-235">此步骤假定您将新策略分配给组织中的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-235">This step assumes that you'll assign the new policy to all mailboxes in your organization.</span></span>
  
1. <span data-ttu-id="8e667-236">在 EAC 中，转到**收件人**\>**邮箱**。</span><span class="sxs-lookup"><span data-stu-id="8e667-236">In the EAC, go to **Recipients** \> **Mailboxes**.</span></span>
    
    <span data-ttu-id="8e667-237">将显示组织中所有用户邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="8e667-237">A list of all user mailboxes in your organization is displayed.</span></span> 
    
2. <span data-ttu-id="8e667-238">通过单击列表中的第一个邮箱，按住**Shift**键，然后单击列表中的最后一个邮箱，选择所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-238">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
3. <span data-ttu-id="8e667-239">在 EAC 右侧的详细信息窗格中，**在"批量编辑"** 下单击"**更多选项"。**</span><span class="sxs-lookup"><span data-stu-id="8e667-239">In the details pane on the right side of the EAC, under **Bulk Edit**, click **More options**.</span></span>
    
4. <span data-ttu-id="8e667-240">在 [保留原則]\*\*\*\* 下方，按一下 [更新]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e667-240">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="8e667-241">在批量分配保留策略页上，**在"选择保留策略"** 下拉列表中，选择在步骤 3 中创建的保留策略;选择"批量**分配保留策略"。** 例如，**阿尔卑斯房屋档案和保留政策。**</span><span class="sxs-lookup"><span data-stu-id="8e667-241">On the **Bulk assign retention policy** page, in the **Select the retention policy** drop-down list, select the retention policy that you created in Step 3; for example, **Alpine House Archive and Retention Policy**.</span></span>
    
6. <span data-ttu-id="8e667-242">**单击"保存"** 可保存新的保留策略分配。</span><span class="sxs-lookup"><span data-stu-id="8e667-242">Click **Save** to save the new retention policy assignment.</span></span> 
    
7. <span data-ttu-id="8e667-243">要验证新的保留策略是否已分配给邮箱，可以执行以下操作：选择邮箱页上的邮箱，然后单击"编辑"。</span><span class="sxs-lookup"><span data-stu-id="8e667-243">To verify that the new retention policy was assigned to mailboxes, you can do the following: select a mailbox on the Mailboxes page, and then click Edit.</span></span> 
    
1. <span data-ttu-id="8e667-244">**在"邮箱"** 页上选择邮箱，然后单击"**编辑**![编辑"。](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png)</span><span class="sxs-lookup"><span data-stu-id="8e667-244">Select a mailbox on the **Mailboxes** page, and then click **Edit** ![Edit](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png).</span></span> 
    
2. <span data-ttu-id="8e667-245">在所选用户的邮箱属性页上，**单击"邮箱功能"。**</span><span class="sxs-lookup"><span data-stu-id="8e667-245">On the mailbox properties page for the selected user, click **Mailbox features**.</span></span>
    
    <span data-ttu-id="8e667-246">分配给邮箱的新策略的名称**将显示在"保留策略"** 下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="8e667-246">The name of the new policy assigned to the mailbox is displayed in the **Retention policy** drop-down list.</span></span> 

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a><span data-ttu-id="8e667-247">（可选）步骤 5：运行托管文件夹助手以应用新设置</span><span class="sxs-lookup"><span data-stu-id="8e667-247">(Optional) Step 5: Run the Managed Folder Assistant to apply the new settings</span></span>

<span data-ttu-id="8e667-248">将新的保留策略应用于步骤 4 中的邮箱后，在 Exchange Online 中最多可能需要 7 天时间才能将新的保留设置应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-248">After you apply the new retention policy to mailboxes in Step 4, it can take up to 7 days in Exchange Online for the new retention settings to be applied to the mailboxes.</span></span> <span data-ttu-id="8e667-249">这是因为称为托管文件夹助理的进程每 7 天处理一次邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-249">This is because a process called the Managed Folder Assistant processes mailboxes once every 7 days.</span></span> <span data-ttu-id="8e667-250">您可以通过在 Exchange 在线 PowerShell 中**运行"开始管理文件夹助手**cmdlet"来强制发生这种情况，而不是等待托管文件夹助手运行。</span><span class="sxs-lookup"><span data-stu-id="8e667-250">Instead of waiting for the Managed Folder Assistant to run, you can force this to happen by running the **Start-ManagedFolderAssistant** cmdlet in Exchange Online PowerShell.</span></span> 
  
 <span data-ttu-id="8e667-251">**运行托管文件夹助理时会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="8e667-251">**What happens when you run the Managed Folder Assistant?**</span></span> <span data-ttu-id="8e667-252">它通过检查邮箱中的项目并确定它们是否需要保留来应用保留策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="8e667-252">It applies the settings in the retention policy by inspecting items in the mailbox and determining whether they're subject to retention.</span></span> <span data-ttu-id="8e667-253">然后，使用适当的保留标记标记要保留的项目，然后对超过保留期限的项目执行指定的保留操作。</span><span class="sxs-lookup"><span data-stu-id="8e667-253">It then stamps items subject to retention with the appropriate retention tag, and then takes the specified retention action on items past their retention age.</span></span> 
  
<span data-ttu-id="8e667-254">以下是连接到 Exchange Online PowerShell，然后在组织中的每个邮箱上运行托管文件夹助手的步骤。</span><span class="sxs-lookup"><span data-stu-id="8e667-254">Here are the steps to connect to Exchange Online PowerShell, and then run the Managed Folder Assistant on every mailbox in your organization.</span></span>
  
1. <span data-ttu-id="8e667-255">在您的本機電腦上開啟 Windows PowerShell，並執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="8e667-255">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="8e667-256">在**Windows PowerShell 凭据请求**对话框中，键入 Office 365 全局管理员帐户的用户名和密码，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="8e667-256">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global admin account, and then click **OK**.</span></span>
    
2. <span data-ttu-id="8e667-257">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="8e667-257">Run the following command.</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="8e667-258">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="8e667-258">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

4. <span data-ttu-id="8e667-259">若要確認您已連線至 Exchange Online 組織，執行下列命令以取得貴組織中所有信箱的清單：</span><span class="sxs-lookup"><span data-stu-id="8e667-259">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```

    > [!NOTE]
    > <span data-ttu-id="8e667-260">有关详细信息，或者如果您在连接到 Exchange 在线组织时遇到问题，请参阅[连接到 Exchange 在线 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)。</span><span class="sxs-lookup"><span data-stu-id="8e667-260">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span> 
  
5. <span data-ttu-id="8e667-261">运行以下两个命令以启动组织中的所有用户邮箱的托管文件夹助手。</span><span class="sxs-lookup"><span data-stu-id="8e667-261">Run the following two commands to start the Managed Folder Assistant for all user mailboxes in your organization.</span></span>
    
    ```
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

<span data-ttu-id="8e667-262">這就對了！</span><span class="sxs-lookup"><span data-stu-id="8e667-262">That's it!</span></span> <span data-ttu-id="8e667-263">您为"阿尔卑斯之家"组织设置了存档和删除策略。</span><span class="sxs-lookup"><span data-stu-id="8e667-263">You've set up an archive and deletion policy for the Alpine House organization.</span></span>
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a><span data-ttu-id="8e667-264">（可选）步骤 6：将新的保留策略作为组织的默认值</span><span class="sxs-lookup"><span data-stu-id="8e667-264">(Optional) Step 6: Make the new retention policy the default for your organization</span></span>

<span data-ttu-id="8e667-265">在步骤 4 中，必须将新的保留策略分配给现有邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-265">In Step 4, you have to assign the new retention policy to existing mailboxes.</span></span> <span data-ttu-id="8e667-266">但是，您可以配置 Exchange 联机，以便将新的保留策略分配给将来创建的新邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-266">But you can configure Exchange Online so that the new retention policy is assigned to new mailboxes that are created in the future.</span></span> <span data-ttu-id="8e667-267">为此，请使用 Exchange 在线 PowerShell 更新组织的默认邮箱计划。</span><span class="sxs-lookup"><span data-stu-id="8e667-267">You do this by using Exchange Online PowerShell to update your organization's default mailbox plan.</span></span> <span data-ttu-id="8e667-268">*邮箱计划是*自动配置新邮箱上的属性的模板。</span><span class="sxs-lookup"><span data-stu-id="8e667-268">A *mailbox plan* is a template that automatically configures properties on new mailboxes.</span></span>  <span data-ttu-id="8e667-269">在此可选步骤中，您可以将分配给邮箱计划的当前保留策略（默认情况下为默认 MRM 策略）替换为在步骤 3 中创建的保留策略。</span><span class="sxs-lookup"><span data-stu-id="8e667-269">In this optional step, you can replace the current retention policy that's assigned to the mailbox plan (by default, the Default MRM Policy) with the retention policy that you created in Step 3.</span></span> <span data-ttu-id="8e667-270">更新邮箱计划后，新的保留策略将分配给新邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-270">After you update the mailbox plan, the new retention policy will be assigned to new mailboxes.</span></span>

1. <span data-ttu-id="8e667-271">[连接到 Exchange 在线电源外壳](https://go.microsoft.com/fwlink/p/?LinkId=517283)或查看步骤 5。</span><span class="sxs-lookup"><span data-stu-id="8e667-271">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) or see Step 5.</span></span>

2. <span data-ttu-id="8e667-272">运行以下命令以显示有关组织中邮箱计划的信息。</span><span class="sxs-lookup"><span data-stu-id="8e667-272">Run the following command to display information about the mailbox plans in your organization.</span></span>

    ```
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```
    <span data-ttu-id="8e667-273">请注意设置为默认值的邮箱计划。</span><span class="sxs-lookup"><span data-stu-id="8e667-273">Note the mailbox plan that's set as the default.</span></span>

3. <span data-ttu-id="8e667-274">运行以下命令，将您在步骤 3 中创建的新保留策略（**例如，阿尔卑斯房屋存档和保留策略）** 分配给默认邮箱计划。</span><span class="sxs-lookup"><span data-stu-id="8e667-274">Run the following command to assign the new retention policy that you created in Step 3 (for example, **Alpine House Archive and Retention Policy**) to the default mailbox plan.</span></span> <span data-ttu-id="8e667-275">本示例假定默认邮箱计划的名称为**ExchangeOnlineEnterprise**。</span><span class="sxs-lookup"><span data-stu-id="8e667-275">This example assumes the name of the default mailbox plan is **ExchangeOnlineEnterprise**.</span></span>

    ```
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```
4. <span data-ttu-id="8e667-276">您可以在步骤 2 中重新运行该命令，以验证分配给默认邮箱计划的保留策略是否已更改。</span><span class="sxs-lookup"><span data-stu-id="8e667-276">You can re-run the command in step 2 to verify that the retention policy assigned to the default mailbox plan was changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="8e667-277">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="8e667-277">More information</span></span>

- <span data-ttu-id="8e667-278">如何计算保留期？</span><span class="sxs-lookup"><span data-stu-id="8e667-278">How is retention age calculated?</span></span> <span data-ttu-id="8e667-279">邮箱项目的保留期限从传递日期或创建日期计算，这些项目（如未发送但由用户创建的草稿邮件）的创建日期。</span><span class="sxs-lookup"><span data-stu-id="8e667-279">The retention age of mailbox items is calculated from the date of delivery or the date of creation for items such as draft messages that aren't sent but are created by the user.</span></span> <span data-ttu-id="8e667-280">當受管理的資料夾助理員處理信箱中的項目時，它會針對其保留標記具有 [刪除並允許復原] 或 [永久刪除] 保留動作的所有項目，加上開始日期和到期日的戳記。</span><span class="sxs-lookup"><span data-stu-id="8e667-280">When the Managed Folder Assistant processes items in a mailbox, it stamps a start date and an expiration date for all items that have retention tags with the Delete and Allow Recovery or Permanently Delete retention action.</span></span> <span data-ttu-id="8e667-281">具有存档标记的项目将加盖移动日期。</span><span class="sxs-lookup"><span data-stu-id="8e667-281">Items that have an archive tag are stamped with a move date.</span></span> 
    
- <span data-ttu-id="8e667-282">下表提供了有关添加到自定义保留策略的每个保留标记的详细信息，该策略是通过执行本主题中的步骤创建的。</span><span class="sxs-lookup"><span data-stu-id="8e667-282">The following table provides more information about each retention tag that is added to the custom retention policy that was created by following the steps in this topic.</span></span>
    
    |<span data-ttu-id="8e667-283">**保留标记**</span><span class="sxs-lookup"><span data-stu-id="8e667-283">**Retention tag**</span></span>|<span data-ttu-id="8e667-284">**此标记的作用**</span><span class="sxs-lookup"><span data-stu-id="8e667-284">**What this tag does**</span></span>|<span data-ttu-id="8e667-285">**内置还是定制？**</span><span class="sxs-lookup"><span data-stu-id="8e667-285">**Built-in or custom?**</span></span>|<span data-ttu-id="8e667-286">**Type**</span><span class="sxs-lookup"><span data-stu-id="8e667-286">**Type**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8e667-287">阿尔卑斯房子3年移动到档案馆</span><span class="sxs-lookup"><span data-stu-id="8e667-287">Alpine House 3 Year Move to Archive</span></span>  <br/> |<span data-ttu-id="8e667-288">将 1095 天（3 年）旧的项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-288">Moves items that are 1095 days (3 years) old to the archive mailbox.</span></span>  <br/> |<span data-ttu-id="8e667-289">自定义（请参阅[步骤 2：为存档和删除策略创建新的保留标记）](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)</span><span class="sxs-lookup"><span data-stu-id="8e667-289">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="8e667-290">默认策略标记（存档）;此标记将自动应用于整个邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-290">Default Policy Tag (archive); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="8e667-291">阿尔卑斯房子7年永久删除</span><span class="sxs-lookup"><span data-stu-id="8e667-291">Alpine House 7 Year Permanently Delete</span></span>  <br/> |<span data-ttu-id="8e667-292">永久删除主邮箱或存档邮箱中的项目，当它们已使用 7 年。</span><span class="sxs-lookup"><span data-stu-id="8e667-292">Permanently deletes items in the primary mailbox or the archive mailbox when they are 7 years old.</span></span>  <br/> |<span data-ttu-id="8e667-293">自定义（请参阅[步骤 2：为存档和删除策略创建新的保留标记）](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)</span><span class="sxs-lookup"><span data-stu-id="8e667-293">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="8e667-294">默认策略标记（删除）;此标记将自动应用于整个邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-294">Default Policy Tag (deletion); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="8e667-295">阿尔卑斯房子删除项目 5 年删除和允许恢复</span><span class="sxs-lookup"><span data-stu-id="8e667-295">Alpine House Deleted Items 5 Years Delete and Allow Recovery</span></span>  <br/> |<span data-ttu-id="8e667-296">从"已删除项目"文件夹中删除具有 5 年历史的项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-296">Deletes items from the Deleted Items folder that are 5 years old.</span></span> <span data-ttu-id="8e667-297">用户可以在删除这些项目后最多 14 天内恢复这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e667-297">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="8e667-298">自定义（请参阅[步骤 2：为存档和删除策略创建新的保留标记）](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)</span><span class="sxs-lookup"><span data-stu-id="8e667-298">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="8e667-299">保留策略标记（已删除的项目）;此标记将自动应用于"已删除项目"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-299">Retention Policy Tag (Deleted Items); this tag is automatically applied to items in the Deleted items folder.</span></span>  <br/> |
    |<span data-ttu-id="8e667-300">可恢复项目 14 天 移动到存档</span><span class="sxs-lookup"><span data-stu-id="8e667-300">Recoverable Items 14 days Move to Archive</span></span>  <br/> |<span data-ttu-id="8e667-301">将"可恢复项目"文件夹中已有 14 天的项目移动到存档邮箱中的"可恢复项目"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8e667-301">Moves items that have been in the Recoverable Items folder for 14 days to the Recoverable Items folder in the archive mailbox.</span></span>  <br/> |<span data-ttu-id="8e667-302">内置</span><span class="sxs-lookup"><span data-stu-id="8e667-302">Built-in</span></span>  <br/> |<span data-ttu-id="8e667-303">保留策略标记（可恢复项目）;此标记将自动应用于"可恢复项目"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-303">Retention Policy Tag (Recoverable Items); this tag is automatically applied to items in the Recoverable Items folder.</span></span>  <br/> |
    |<span data-ttu-id="8e667-304">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="8e667-304">Junk Email</span></span>  <br/> |<span data-ttu-id="8e667-305">永久删除在"垃圾邮件"文件夹中已包含 30 天的项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-305">Permanently deletes items that have been in the Junk Email folder for 30 days.</span></span> <span data-ttu-id="8e667-306">用户可以在删除这些项目后最多 14 天内恢复这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e667-306">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="8e667-307">内置</span><span class="sxs-lookup"><span data-stu-id="8e667-307">Built-in</span></span>  <br/> |<span data-ttu-id="8e667-308">保留策略标记（垃圾邮件）;此标记将自动应用于垃圾邮件文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-308">Retention Policy Tag (Junk Email); this tag is automatically applied to items in Junk Email folder.</span></span>  <br/> |
    |<span data-ttu-id="8e667-309">1 個月刪除</span><span class="sxs-lookup"><span data-stu-id="8e667-309">1 Month Delete</span></span>  <br/> |<span data-ttu-id="8e667-310">永久删除 30 天前的项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-310">Permanently deletes items that are 30 days old.</span></span> <span data-ttu-id="8e667-311">用户可以在删除这些项目后最多 14 天内恢复这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e667-311">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="8e667-312">内置</span><span class="sxs-lookup"><span data-stu-id="8e667-312">Built-in</span></span>  <br/> |<span data-ttu-id="8e667-313">个人;用户可以应用此标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-313">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="8e667-314">1 年刪除</span><span class="sxs-lookup"><span data-stu-id="8e667-314">1 Year Delete</span></span>  <br/> |<span data-ttu-id="8e667-315">永久删除 365 天的项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-315">Permanently deletes items that are 365 days old.</span></span> <span data-ttu-id="8e667-316">用户可以在删除这些项目后最多 14 天内恢复这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e667-316">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="8e667-317">内置</span><span class="sxs-lookup"><span data-stu-id="8e667-317">Built-in</span></span>  <br/> |<span data-ttu-id="8e667-318">个人;用户可以应用此标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-318">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="8e667-319">永不刪除</span><span class="sxs-lookup"><span data-stu-id="8e667-319">Never Delete</span></span>  <br/> |<span data-ttu-id="8e667-320">此标记可防止保留策略删除项目。</span><span class="sxs-lookup"><span data-stu-id="8e667-320">This tag prevent items from being deleted by a retention policy.</span></span>  <br/> |<span data-ttu-id="8e667-321">内置</span><span class="sxs-lookup"><span data-stu-id="8e667-321">Built-in</span></span>  <br/> |<span data-ttu-id="8e667-322">个人;用户可以应用此标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-322">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="8e667-323">個人 1 年移至封存</span><span class="sxs-lookup"><span data-stu-id="8e667-323">Personal 1 year move to archive</span></span>  <br/> |<span data-ttu-id="8e667-324">在 1 年后将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-324">Moves items to the archive mailbox after 1 year.</span></span>  <br/> |<span data-ttu-id="8e667-325">内置</span><span class="sxs-lookup"><span data-stu-id="8e667-325">Built-in</span></span>  <br/> |<span data-ttu-id="8e667-326">个人;用户可以应用此标记。</span><span class="sxs-lookup"><span data-stu-id="8e667-326">Personal; this tag can be applied by users.</span></span>  <br/> |
   
    > <span data-ttu-id="8e667-327"><sup>\*</sup>用户可以在 Web 上的 Outlook 和 Outlook 中使用"恢复已删除项目"工具（以前称为 Outlook Web 应用）在已删除的项目保留期内恢复已删除的项目，默认情况下，在 Exchange Online 中为 14 天。</span><span class="sxs-lookup"><span data-stu-id="8e667-327"><sup>\*</sup> Users can use the Recover Deleted Items tool in Outlook and Outlook on the web (formerly known as Outlook Web App) to recover a deleted item within the deleted item retention period, which by default is 14 days in Exchange Online.</span></span> <span data-ttu-id="8e667-328">管理员可以使用 Windows PowerShell 将已删除的项目保留期增加到最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="8e667-328">An administrator can use Windows PowerShell to increase the deleted item retention period to a maximum of 30 days.</span></span> <span data-ttu-id="8e667-329">有关详细信息，请参阅：恢复[Windows Outlook 中的已删除项目，](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)并[更改联机交换邮箱中已删除的项目保留期](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span><span class="sxs-lookup"><span data-stu-id="8e667-329">For more information, see: [Recover deleted items in Outlook for Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) and [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span></span>
  
- <span data-ttu-id="8e667-330">使用**可恢复项目 14 天移动到存档**保留标记有助于释放用户主邮箱中"可恢复项目"文件夹中的存储空间。</span><span class="sxs-lookup"><span data-stu-id="8e667-330">Using the **Recoverable Items 14 days Move to Archive** retention tag helps free up storage space in the Recoverable Items folder in the user's primary mailbox.</span></span> <span data-ttu-id="8e667-331">当用户的邮箱被置于保留状态时，这非常有用，这意味着不会永久删除用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e667-331">This is useful when a user's mailbox is placed on hold, which means nothing is ever permanently deleted the user's mailbox.</span></span> <span data-ttu-id="8e667-332">如果不将项目移动到存档邮箱，则可能会达到主邮箱中可恢复项目文件夹的存储配额。</span><span class="sxs-lookup"><span data-stu-id="8e667-332">Without moving items to the archive mailbox, it's possible the storage quota for the Recoverable Items folder in the primary mailbox will be reached.</span></span> <span data-ttu-id="8e667-333">有关此以及如何避免它的详细信息，请参阅[增加保留邮箱的可恢复项目配额。](https://go.microsoft.com/fwlink/p/?LinkId=786479)</span><span class="sxs-lookup"><span data-stu-id="8e667-333">For more information about this and how to avoid it, see [Increase the Recoverable Items quota for mailboxes on hold](https://go.microsoft.com/fwlink/p/?LinkId=786479).</span></span>
