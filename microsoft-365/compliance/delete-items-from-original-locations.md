---
title: 从原始位置删除项目
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文介绍如何使用安全&合规性中心中的新数据调查（预览）工具从其原始位置删除项目。
ms.openlocfilehash: d855a8e4c69d64cdb37c40b37b042c2571af67a8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070614"
---
# <a name="delete-items-from-their-original-location-preview"></a><span data-ttu-id="0ca07-103">从原始位置删除项目（预览）</span><span class="sxs-lookup"><span data-stu-id="0ca07-103">Delete items from their original location (Preview)</span></span>

<span data-ttu-id="0ca07-104">要从原始位置删除项目的功能位于"预览"中。</span><span class="sxs-lookup"><span data-stu-id="0ca07-104">The feature to delete items from their original location is in Preview.</span></span>

<span data-ttu-id="0ca07-105">使用数据调查，可以从其原始位置删除项目。</span><span class="sxs-lookup"><span data-stu-id="0ca07-105">Using data investigations, you can delete items from their original locations.</span></span> <span data-ttu-id="0ca07-106">这意味着您可以从整个组织的 Exchange 邮箱、SharePoint 站点和 OneDrive 帐户中删除项目。</span><span class="sxs-lookup"><span data-stu-id="0ca07-106">This means you can delete items from  Exchange mailboxes, SharePoint sites, and OneDrive accounts across your organization.</span></span> <span data-ttu-id="0ca07-107">由于您收集物品作为证据，因此在证据集中保留物品的副本，以便进一步调查或作为参考保留。</span><span class="sxs-lookup"><span data-stu-id="0ca07-107">Because you collected items as evidence, you have copies of the items retained in the evidence set for further investigation or keep as reference.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0ca07-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="0ca07-108">Before you begin</span></span>

- <span data-ttu-id="0ca07-109">要删除项目，您必须在"安全&合规性中心"中分配"**搜索和清除"** 角色。</span><span class="sxs-lookup"><span data-stu-id="0ca07-109">To delete items, you have to be assigned the **Search And Purge** role in the Security & Compliance Center.</span></span> <span data-ttu-id="0ca07-110">默认情况下，此角色分配给内置的数据调查员角色组。</span><span class="sxs-lookup"><span data-stu-id="0ca07-110">This role is assigned by default to the built-in Data Investigator role group.</span></span> 

- <span data-ttu-id="0ca07-111">本主题中的过程假定您已运行了与调查关联的搜索，并将搜索结果添加到证据集。</span><span class="sxs-lookup"><span data-stu-id="0ca07-111">The procedure in this topic assumes that you have run a search associated with an investigation and added the search results to an evidence set.</span></span> <span data-ttu-id="0ca07-112">在搜索结果有证据后，您可以选择一个或多个要删除的项目。</span><span class="sxs-lookup"><span data-stu-id="0ca07-112">After the search results are in evidence, you can select one or more items to delete.</span></span> <span data-ttu-id="0ca07-113">有关详细信息，请参阅[搜索调查中的数据。](search-for-data.md)</span><span class="sxs-lookup"><span data-stu-id="0ca07-113">For more information, see [Search for data in an investigation](search-for-data.md).</span></span>

- <span data-ttu-id="0ca07-114">请务必记住，仅删除原始内容位置中的项目（如 Exchange 邮箱、SharePoint 网站和 OneDrive 帐户）。</span><span class="sxs-lookup"><span data-stu-id="0ca07-114">It's important to keep in mind that only the items in the original content locations (such as Exchange mailboxes, SharePoint sites, and OneDrive accounts) are deleted.</span></span> <span data-ttu-id="0ca07-115">这些项目不会从证据集中删除。</span><span class="sxs-lookup"><span data-stu-id="0ca07-115">These items aren't deleted from the evidence set.</span></span> <span data-ttu-id="0ca07-116">这是因为证据集中的项目是原始副本。</span><span class="sxs-lookup"><span data-stu-id="0ca07-116">That's because the items in an evidence set are copies of the original.</span></span> <span data-ttu-id="0ca07-117">将搜索结果添加到证据集时，将复制这些项目。</span><span class="sxs-lookup"><span data-stu-id="0ca07-117">These items are copied when you added the results of a search to an evidence set.</span></span>

## <a name="delete-items"></a><span data-ttu-id="0ca07-118">刪除項目</span><span class="sxs-lookup"><span data-stu-id="0ca07-118">Delete items</span></span>

<span data-ttu-id="0ca07-119">执行以下步骤从项目的原始位置删除项目：</span><span class="sxs-lookup"><span data-stu-id="0ca07-119">Perform the following steps to delete items from their original location:</span></span>

1. <span data-ttu-id="0ca07-120">在"**数据调查"** 工具中，打开包含要删除的项目的数据调查，然后单击"**证据"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0ca07-120">In the **Data Investigations** tool, open the data investigation that contains the items you want to delete, and then click the **Evidence** tab.</span></span>

2. <span data-ttu-id="0ca07-121">选择要删除的项目。</span><span class="sxs-lookup"><span data-stu-id="0ca07-121">Select the items that you want to delete.</span></span> <span data-ttu-id="0ca07-122">您可以选择证据集中的所有项目，也可以只选择项的子集。</span><span class="sxs-lookup"><span data-stu-id="0ca07-122">You can select all items in the evidence set or select just a subset of items.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="0ca07-123">如果在 SharePoint 和 OneDrive 中选择电子邮件或附加到文档的文件的附件，则当从原始位置删除项目时，也将选择并删除父项。</span><span class="sxs-lookup"><span data-stu-id="0ca07-123">If you select the attachments of an email or a file attached to a document in SharePoint and OneDrive, the parent item will be also be selected and deleted when the item is deleted from its original location.</span></span> <span data-ttu-id="0ca07-124">同样，如果选择具有附件的项目，则父项项和所有附件都将被删除。</span><span class="sxs-lookup"><span data-stu-id="0ca07-124">Similarly, if you select an item that has attachments, the parent item item and all attachments are deleted.</span></span>
 
2. <span data-ttu-id="0ca07-125">**单击"操作"，\*\*\*\*然后单击"从原始位置删除项目"。**</span><span class="sxs-lookup"><span data-stu-id="0ca07-125">Click **Action** and then click **Delete items from original locations**.</span></span>

   ![单击"操作"，然后单击"从原始位置删除项目"](media/DataInvestigationsDeleteItems1.png)

3. <span data-ttu-id="0ca07-127">在弹出窗口页上，验证要删除的项目和相关子文档的数量，然后单击"**删除"。**</span><span class="sxs-lookup"><span data-stu-id="0ca07-127">On the flyout page, verify the number of items and related child documents that will be deleted, and then click **Delete**.</span></span>

   ![弹出窗口显示选择删除的项目数和任何附加文档数](media/DataInvestigationsDeleteItems2.png)

   > [!NOTE]
   > <span data-ttu-id="0ca07-129">在上一个屏幕截图中，项目数指示选择要删除的项目数。</span><span class="sxs-lookup"><span data-stu-id="0ca07-129">In the previous screenshot, the number of items indicates the number of items that are selected for deletion.</span></span> <span data-ttu-id="0ca07-130">文档数指示项目总数，包括附加到父项的任何文件。</span><span class="sxs-lookup"><span data-stu-id="0ca07-130">The number of documents indicates to total number of items including any files that are attached to a parent item.</span></span> <span data-ttu-id="0ca07-131">例如，如果选择一封电子邮件，并且该邮件包含附加的 Word 文档，则**仅"选定文档"** 下显示的项目和文档数将是**1 个项目（2 个文档）。**</span><span class="sxs-lookup"><span data-stu-id="0ca07-131">For example, if you select one email message and that message has an attached Word document, the number of items and documents displayed under **Selected documents only** would be **1 items (2 documents)**.</span></span>

<span data-ttu-id="0ca07-132">**您可以在"作业"** 选项卡上跟踪"**删除原始位置**作业"项的进度。单击该作业可显示"飞出"页。</span><span class="sxs-lookup"><span data-stu-id="0ca07-132">You can track the progress of the **Delete items from original locations** job on the **Jobs** tab. Click the job to display the flyout page.</span></span> 

![从原始位置作业中删除项目弹出窗口页面](media/DataInvestigationsDeleteItems3.png)

<span data-ttu-id="0ca07-134">删除作业中的项时，作业状态**设置为"成功"。**</span><span class="sxs-lookup"><span data-stu-id="0ca07-134">When the items in the job are deleted, the job status is set to **Successful**.</span></span> <span data-ttu-id="0ca07-135">还会显示已完成作业的时间和日期。</span><span class="sxs-lookup"><span data-stu-id="0ca07-135">The time and date of the completed job is also displayed.</span></span> 

![已完成的删除项作业](media/DataInvestigationsDeleteItems4.png)

> [!NOTE]
> <span data-ttu-id="0ca07-137">您可能会收到"**从原始位置作业中删除项目"** 的状态"**部分成功"。**</span><span class="sxs-lookup"><span data-stu-id="0ca07-137">You may receive a status of **Partially Successful** for the **Delete items from original locations** job.</span></span> <span data-ttu-id="0ca07-138">有许多情况导致此作业状态。</span><span class="sxs-lookup"><span data-stu-id="0ca07-138">There are a number of situations that result in this job status.</span></span> <span data-ttu-id="0ca07-139">有关详细信息，请参阅本文[中的"部分成功删除"](#partially-successful-deletions)部分部分。</span><span class="sxs-lookup"><span data-stu-id="0ca07-139">For more information, see the [Partially successful deletions](#partially-successful-deletions) section in this article.</span></span>

## <a name="what-happens-when-you-delete-items"></a><span data-ttu-id="0ca07-140">删除项目时会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="0ca07-140">What happens when you delete items</span></span>

<span data-ttu-id="0ca07-141">此时，当您从其原始内容位置删除项目时，这些项目将*软删除。*</span><span class="sxs-lookup"><span data-stu-id="0ca07-141">At this time, when you delete items from their original content location, the items are *soft-deleted*.</span></span> <span data-ttu-id="0ca07-142">这意味着项目将移动到特殊位置并保留，直到已删除的项目保留期到期，并且某个项目被标记为从 Office 365 永久删除。</span><span class="sxs-lookup"><span data-stu-id="0ca07-142">This means that items are moved to special location and retained until the deleted item retention period expires and an item is marked for permanent deletion from Office 365.</span></span> <span data-ttu-id="0ca07-143">软删除项目意味着用户仍可以恢复这些项目，直到保留期到期。</span><span class="sxs-lookup"><span data-stu-id="0ca07-143">Soft-deleting items means that users can still recover these items until the retention period expires.</span></span> <span data-ttu-id="0ca07-144">以下是有关从 Exchange 邮箱和 SharePoint 和一个业务网站软删除项目时发生的情况的说明，以及用户在从原始位置删除项目后可以执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="0ca07-144">Here are descriptions about what happens when items are soft-deleted from Exchange mailboxes and SharePoint and OneDrive for Business sites, and what users can do after items are deleted from their original locations.</span></span>

- <span data-ttu-id="0ca07-145">**邮箱：** 软删除邮箱项目时，它将移动到邮箱中的"可恢复项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ca07-145">**Mailboxes:** When a mailbox item is soft-deleted, it's moved to the Recoverable Items folder in the mailbox.</span></span> <span data-ttu-id="0ca07-146">此行为类似于当用户从"已删除项目"文件夹中删除项目或通过按 Shift + 删除来永久删除项目时。</span><span class="sxs-lookup"><span data-stu-id="0ca07-146">This behavior is similar to when a user deletes an item from the Deleted Items folder or permanently deletes an item by pressing Shift + Delete.</span></span> <span data-ttu-id="0ca07-147">此时，用户可以在已删除的项目保留期到期之前恢复该项目。</span><span class="sxs-lookup"><span data-stu-id="0ca07-147">At this point, the user can recover the item up until the deleted item retention period expires.</span></span> <span data-ttu-id="0ca07-148">在 Office 365 中，删除的项目保留期默认为 14 天，但管理员可以将保留期增加到 30 天。</span><span class="sxs-lookup"><span data-stu-id="0ca07-148">In Office 365, the deleted item retention period is 14 days by default, but an admin can increase the retention period to 30 days.</span></span> <span data-ttu-id="0ca07-149">保留期到期后，项目将移动到隐藏文件夹（*称为"清除"* 文件夹）。</span><span class="sxs-lookup"><span data-stu-id="0ca07-149">After the retention period expires, the item is moved to a hidden folder (called the *Purges* folder).</span></span> <span data-ttu-id="0ca07-150">下次处理邮箱时，该项目将从 Office 365 永久删除。</span><span class="sxs-lookup"><span data-stu-id="0ca07-150">The item is permanently removed from Office 365 the next time the mailbox is processed.</span></span> <span data-ttu-id="0ca07-151">邮箱每七天处理一次）。</span><span class="sxs-lookup"><span data-stu-id="0ca07-151">Mailboxes are processed once every seven days).</span></span>

- <span data-ttu-id="0ca07-152">**共享点和 OneDrive 站点：** 软删除站点上的文件或文档时，会将其移动到站点的回收站（也称为*第一阶段*回收站）。</span><span class="sxs-lookup"><span data-stu-id="0ca07-152">**SharePoint and OneDrive sites:** When a file or document on a site is soft-deleted, it's moved to the site's Recycle Bin (also called the *first-stage* Recycle Bin).</span></span> <span data-ttu-id="0ca07-153">项目在回收站中保留 93 天（Office 365 中站点的已删除项目保留期）。</span><span class="sxs-lookup"><span data-stu-id="0ca07-153">The item remains in the Recycle Bin for 93 days (the deleted item retention period for sites in Office 365).</span></span> <span data-ttu-id="0ca07-154">在 93 天期间，已删除的项目仍可由 SharePoint 中的网站集管理员或 OneDrive 中的用户或管理员恢复。</span><span class="sxs-lookup"><span data-stu-id="0ca07-154">During the 93-day period, deleted items can still be recovered by a site collection administrator in SharePoint or by the user or admin in OneDrive.</span></span> <span data-ttu-id="0ca07-155">也可以从第一阶段回收站中删除项目。</span><span class="sxs-lookup"><span data-stu-id="0ca07-155">Items can also be deleted from the first-stage recycle bin.</span></span> <span data-ttu-id="0ca07-156">发生这种情况时，项目将移动到站点集的回收站，称为*第二阶段*回收站。</span><span class="sxs-lookup"><span data-stu-id="0ca07-156">When that happens, the items are moved to the Recycle Bin for the site collection, which is called the *second-stage* Recycle Bin.</span></span> <span data-ttu-id="0ca07-157">第一阶段和第二阶段回收站的保留期均为 93 天。这意味着第二阶段回收站保留在项目最初删除时开始。</span><span class="sxs-lookup"><span data-stu-id="0ca07-157">The retention period is 93 days for both the first-stage and second-stage recycle bins. That means the second-stage Recycle Bin retention starts when the item is initially deleted.</span></span> <span data-ttu-id="0ca07-158">这意味着两个回收站的总最长保留期为 93 天。如果从第二阶段回收站中删除项目（由管理员手动删除，或在保留期到期时自动删除该项目），则管理员无法再访问该项目。</span><span class="sxs-lookup"><span data-stu-id="0ca07-158">That means the total maximum retention time is 93 days for both recycle bins. If an item is deleted from the second-stage Recycle Bin (either manually by an admin or automatically when the retention period expires), it's no longer accessible by an admin.</span></span>

## <a name="what-happens-if-a-content-location-is-on-hold"></a><span data-ttu-id="0ca07-159">如果内容位置处于保留状态，会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="0ca07-159">What happens if a content location is on hold</span></span>

<span data-ttu-id="0ca07-160">在 Office 365 中，邮箱和站点可以置于保留状态或分配给保留策略。</span><span class="sxs-lookup"><span data-stu-id="0ca07-160">In Office 365, mailboxes and sites can be placed on hold or assigned to a retention policy.</span></span> <span data-ttu-id="0ca07-161">这意味着，在项目保留期到期或删除保留之前，不会永久删除任何内容。</span><span class="sxs-lookup"><span data-stu-id="0ca07-161">This means that nothing is permanently removed until the retention period for an item expires or until the hold is removed.</span></span> <span data-ttu-id="0ca07-162">即使您从其原始位置删除项目，该项目也可能不会从 Office 365 永久删除。</span><span class="sxs-lookup"><span data-stu-id="0ca07-162">Even if you delete an item from its original location, the item may not be permanently removed from Office 365.</span></span> <span data-ttu-id="0ca07-163">例如，如果邮箱处于保留状态，软删除的项目最终将移动到"可恢复项目"文件夹中的"清除"或"发现保留"子文件夹，并保留到保留期限或保留期到期。</span><span class="sxs-lookup"><span data-stu-id="0ca07-163">For example, if a mailbox is on hold, soft-deleted items are eventually moved to Purges or DiscoveryHold subfolders in the Recoverable Items folder and retained until the hold duration or retention period expires.</span></span> <span data-ttu-id="0ca07-164">对于网站，移动到回收站的项目的副本将复制到在将保留或保留策略放在站点上时创建的保留保留库。</span><span class="sxs-lookup"><span data-stu-id="0ca07-164">For sites, a copy of the item that's moved to the Recycle Bin is copied to the Preservation Hold library that's created when a hold or retention policy is placed on a site.</span></span>

## <a name="partially-successful-deletions"></a><span data-ttu-id="0ca07-165">部分成功删除</span><span class="sxs-lookup"><span data-stu-id="0ca07-165">Partially successful deletions</span></span>

<span data-ttu-id="0ca07-166">**从原始位置的删除项**作业完成运行后，您可能会**收到"部分成功"** 的作业状态。</span><span class="sxs-lookup"><span data-stu-id="0ca07-166">After the **Delete items from original locations** job has completed running, you may received a job status of **Partially Successful**.</span></span> <span data-ttu-id="0ca07-167">通常，此状态指示作业成功运行，但并非所有项目都软删除。</span><span class="sxs-lookup"><span data-stu-id="0ca07-167">In general, this status indicates that the job ran successfully, but not all items were soft-deleted.</span></span> <span data-ttu-id="0ca07-168">下面是导致部分成功删除的原因列表：</span><span class="sxs-lookup"><span data-stu-id="0ca07-168">Here's a list of reasons that result in partially successful deletions:</span></span>

- <span data-ttu-id="0ca07-169">邮箱项目已位于源邮箱中的"可恢复项目"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0ca07-169">A mailbox item was already located in the Recoverable Items folder in the source mailbox.</span></span>

- <span data-ttu-id="0ca07-170">从源邮箱中的"可恢复项目"文件夹中清除邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="0ca07-170">A mailbox item was purged from the Recoverable Items folder in the source mailbox.</span></span>

- <span data-ttu-id="0ca07-171">文档已位于 SharePoint 或 OneDrive 站点的第一阶段回收站中。</span><span class="sxs-lookup"><span data-stu-id="0ca07-171">A document was already located in the first-stage Recycle Bin in a SharePoint or OneDrive site.</span></span>

- <span data-ttu-id="0ca07-172">文档添加到证据集后，将其移动到其他 SharePoint 站点。</span><span class="sxs-lookup"><span data-stu-id="0ca07-172">A document was moved to a different SharePoint site after it was added to the evidence set.</span></span> <span data-ttu-id="0ca07-173">在这种情况下，文档不会移动到移动到站点中的回收站。</span><span class="sxs-lookup"><span data-stu-id="0ca07-173">In this case, the document isn't moved to the Recycle Bin in the site it was moved to.</span></span>

- <span data-ttu-id="0ca07-174">文档在添加到证据集后，在 SharePoint 或 OneDrive 中永久删除（移动到第二阶段回收站）。</span><span class="sxs-lookup"><span data-stu-id="0ca07-174">A document was permanently deleted in SharePoint or OneDrive (moved to the second-stage Recycle Bin) after it was added to the evidence set.</span></span>
