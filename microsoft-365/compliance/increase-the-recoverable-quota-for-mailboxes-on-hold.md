---
title: 增加保留信箱的可復原項目配額
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: '启用存档邮箱并启用自动展开存档，以增加 Office 365 中邮箱的可恢复项目文件夹的大小。 '
ms.openlocfilehash: 4c2e36dae3c8677579569d55a9c5b88efb5c54e5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076264"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="6c919-103">增加保留信箱的可復原項目配額</span><span class="sxs-lookup"><span data-stu-id="6c919-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="6c919-104">自动应用于 Exchange Online 中新邮箱的默认保留策略（名为"默认 MRM 策略"）包含名为"可恢复项目"的保留标记，14 天移动到存档状态。</span><span class="sxs-lookup"><span data-stu-id="6c919-104">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="6c919-105">此保留标记在 14 天的保留期过期后将项目从用户主邮箱中的"可恢复项目"文件夹中移动到用户存档邮箱中的"可恢复项目"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6c919-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="6c919-106">为此，必须启用用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="6c919-107">如果未启用存档邮箱，则不执行任何操作，这意味着在 14 天保留期到期后，保留邮箱的"可恢复项目"文件夹中的项目不会移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="6c919-108">由于保留的邮箱中未删除任何内容，因此可能会超出"可恢复项目"文件夹的存储配额，尤其是在未启用用户的存档邮箱时。</span><span class="sxs-lookup"><span data-stu-id="6c919-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="6c919-109">为了帮助减少超出此限制的可能性，在 Exchange Online 中的邮箱上放置保留时，"可恢复项目"文件夹的存储配额将自动从 30 GB 增加到 100 GB。</span><span class="sxs-lookup"><span data-stu-id="6c919-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="6c919-110">如果启用了存档邮箱，则存档邮箱中的"可恢复项目"文件夹的存储配额也将从 30 GB 增加到 100 GB。</span><span class="sxs-lookup"><span data-stu-id="6c919-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="6c919-111">如果启用了 Exchange Online 中的自动扩展存档功能，则用户存档中的"可恢复项目"文件夹的存储配额将不受限制。</span><span class="sxs-lookup"><span data-stu-id="6c919-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="6c919-112">下表汇总了"可恢复项目"文件夹的存储配额。</span><span class="sxs-lookup"><span data-stu-id="6c919-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="6c919-113">**可恢复项目文件夹的位置**</span><span class="sxs-lookup"><span data-stu-id="6c919-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="6c919-114">**邮箱未保持**</span><span class="sxs-lookup"><span data-stu-id="6c919-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="6c919-115">**邮箱保持**</span><span class="sxs-lookup"><span data-stu-id="6c919-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c919-116">主邮箱</span><span class="sxs-lookup"><span data-stu-id="6c919-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="6c919-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="6c919-117">30 GB</span></span>  <br/> |<span data-ttu-id="6c919-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="6c919-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="6c919-119">存档邮箱<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6c919-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="6c919-120">無限制</span><span class="sxs-lookup"><span data-stu-id="6c919-120">Unlimited</span></span>  <br/> |<span data-ttu-id="6c919-121">無限制</span><span class="sxs-lookup"><span data-stu-id="6c919-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="6c919-122">**可恢复项目文件夹的总存储配额**</span><span class="sxs-lookup"><span data-stu-id="6c919-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="6c919-123">無限制</span><span class="sxs-lookup"><span data-stu-id="6c919-123">Unlimited</span></span>  <br/> |<span data-ttu-id="6c919-124">無限制</span><span class="sxs-lookup"><span data-stu-id="6c919-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="6c919-125"><sup>\*</sup>对于具有 Exchange Online（计划 2）许可证的用户，存档邮箱的初始存储配额为 100 GB。</span><span class="sxs-lookup"><span data-stu-id="6c919-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="6c919-126">但是，当为保留的邮箱启用自动展开存档时，存档邮箱和可恢复项目文件夹的存储配额将增加到 110 GB。</span><span class="sxs-lookup"><span data-stu-id="6c919-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="6c919-127">必要时将预配额外的存档存储空间，从而导致无限量的存档存储。</span><span class="sxs-lookup"><span data-stu-id="6c919-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="6c919-128">有关自动扩展存档的详细信息，请参阅[Office 365 中无限制存档概述。](unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="6c919-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="6c919-129">当保留邮箱的主邮箱中的"可恢复项目"文件夹的存储配额接近其限制时，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6c919-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="6c919-130">**启用存档邮箱并启用自动展开存档**- 只需启用存档邮箱，然后在 Exchange 中打开自动扩展存档功能，即可为"可恢复项目"文件夹启用无限存储容量在线。</span><span class="sxs-lookup"><span data-stu-id="6c919-130">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="6c919-131">这将导致主邮箱中的可恢复项目文件夹的 110 GB 和用户存档中的可恢复项目文件夹的无限容量的存储容量。</span><span class="sxs-lookup"><span data-stu-id="6c919-131">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="6c919-132">查看方法：[在"安全&合规性中心启用存档邮箱，](enable-archive-mailboxes.md)并在[Office 365 中启用无限制存档。](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="6c919-132">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6c919-133">启用接近超出"可恢复项目"文件夹的存储配额的邮箱的存档后，可能需要运行托管文件夹助手以手动触发助手以处理邮箱，以便移动过期邮件。存档邮箱中的可恢复项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="6c919-133">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="6c919-134">有关说明，请参阅[步骤 4。](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)</span><span class="sxs-lookup"><span data-stu-id="6c919-134">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="6c919-135">请注意，用户邮箱中的其他项目可能会移动到新的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-135">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="6c919-136">请考虑在启用存档邮箱后告诉用户可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="6c919-136">Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="6c919-137">**为保留邮箱创建自定义保留策略**- 除了启用存档邮箱和自动扩展对诉讼保留或就地保留的邮箱的存档外，您可能还希望为上的邮箱创建自定义保留策略保持。</span><span class="sxs-lookup"><span data-stu-id="6c919-137">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold.</span></span> <span data-ttu-id="6c919-138">这样，您就将保留策略应用于保留邮箱，该保留策略与应用于未处于保留状态的邮箱的默认 MRM 策略不同。</span><span class="sxs-lookup"><span data-stu-id="6c919-138">This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold.</span></span> <span data-ttu-id="6c919-139">这允许您应用专为保留邮箱设计的保留标记。</span><span class="sxs-lookup"><span data-stu-id="6c919-139">This lets you to apply retention tags that are specifically designed for mailboxes on hold.</span></span> <span data-ttu-id="6c919-140">这包括为"可恢复项目"文件夹创建新的保留标记。</span><span class="sxs-lookup"><span data-stu-id="6c919-140">This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="6c919-141">本主题的其余部分介绍为保留邮箱创建自定义保留策略的分步过程。</span><span class="sxs-lookup"><span data-stu-id="6c919-141">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="6c919-142">步骤 1：为"可恢复项目"文件夹创建自定义保留标记</span><span class="sxs-lookup"><span data-stu-id="6c919-142">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

<span data-ttu-id="6c919-143">•[步骤 2：为保留的邮箱创建新的保留策略](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="6c919-143">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="6c919-144">步骤 3：将新的保留策略应用于保留的邮箱</span><span class="sxs-lookup"><span data-stu-id="6c919-144">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="6c919-145">（可选）步骤 4：运行托管文件夹助手以应用新的保留设置</span><span class="sxs-lookup"><span data-stu-id="6c919-145">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="6c919-146">步骤 1：为"可恢复项目"文件夹创建自定义保留标记</span><span class="sxs-lookup"><span data-stu-id="6c919-146">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="6c919-147">第一步是为"可恢复项目"文件夹创建自定义保留标记（称为保留策略标记或 RPT）。</span><span class="sxs-lookup"><span data-stu-id="6c919-147">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="6c919-148">如前所述，此 RPT 将项目从用户主邮箱中的"可恢复项目"文件夹移动到用户存档邮箱中的"可恢复项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="6c919-148">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="6c919-149">您必须使用 PowerShell 为"可恢复项目"文件夹创建 RPT。</span><span class="sxs-lookup"><span data-stu-id="6c919-149">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="6c919-150">不能使用 Exchange 管理中心 （EAC）。</span><span class="sxs-lookup"><span data-stu-id="6c919-150">You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="6c919-151">使用遠端 PowerShell 連線到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6c919-151">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="6c919-152">运行以下命令为"可恢复项目"文件夹创建新的 RPT：</span><span class="sxs-lookup"><span data-stu-id="6c919-152">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="6c919-153">例如，以下命令为名为"可恢复项目 30 天，邮箱保留期"的可恢复项目文件夹创建 RPT，保留期为 30 天。</span><span class="sxs-lookup"><span data-stu-id="6c919-153">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days.</span></span> <span data-ttu-id="6c919-154">这意味着，在项目在"可恢复项目"文件夹中保留 30 天后，它将移动到用户存档邮箱中的"可恢复项目"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6c919-154">This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="6c919-155">我们建议可恢复项目 RPT 的保留期（由_期限保留_参数定义）与将应用于 RPT 的邮箱的已删除项目保留期相同。</span><span class="sxs-lookup"><span data-stu-id="6c919-155">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="6c919-156">这允许用户在将已删除的项目移动到存档邮箱之前恢复已删除的项目。</span><span class="sxs-lookup"><span data-stu-id="6c919-156">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="6c919-157">在前面的示例中，保留期设置为 30 天，其假设邮箱的已删除项目保留期也是 30 天。</span><span class="sxs-lookup"><span data-stu-id="6c919-157">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="6c919-158">Exchange Online 信箱預設會將刪除的項目保留 14 天。</span><span class="sxs-lookup"><span data-stu-id="6c919-158">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="6c919-159">但是，您可以将此设置更改为最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="6c919-159">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="6c919-160">有关详细信息，请参阅更改[Exchange Online 中邮箱的已删除项目保留期。](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span><span class="sxs-lookup"><span data-stu-id="6c919-160">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="6c919-161">步骤 2：为保留的邮箱创建新的保留策略</span><span class="sxs-lookup"><span data-stu-id="6c919-161">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="6c919-162">下一步是创建新的保留策略，并向其添加保留标记，包括您在步骤 1 中创建的可恢复项目 RPT。</span><span class="sxs-lookup"><span data-stu-id="6c919-162">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1.</span></span> <span data-ttu-id="6c919-163">此新策略将在下一步中应用于保留的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-163">This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="6c919-164">在创建新的保留策略之前，请确定要添加的其他保留标记。</span><span class="sxs-lookup"><span data-stu-id="6c919-164">Before you create the new retention policy, determine the additional retention tags that you want to add.</span></span> <span data-ttu-id="6c919-165">有关添加到默认 MRM 策略的保留标记的列表以及有关创建新保留标记的信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="6c919-165">For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="6c919-166">在线交换中的默认保留策略</span><span class="sxs-lookup"><span data-stu-id="6c919-166">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="6c919-167">支援保留原則標記的預設資料夾</span><span class="sxs-lookup"><span data-stu-id="6c919-167">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="6c919-168">[创建保留策略](https://go.microsoft.com/fwlink/p/?LinkId=404422)主题中的"创建保留标记"部分。</span><span class="sxs-lookup"><span data-stu-id="6c919-168">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="6c919-169">您可以使用 EAC 或 Exchange 在线电源外壳创建保留策略。</span><span class="sxs-lookup"><span data-stu-id="6c919-169">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="6c919-170">使用 EAC 创建保留策略</span><span class="sxs-lookup"><span data-stu-id="6c919-170">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="6c919-171">在 EAC 中，转到**合规性管理**\>**保留策略，\*\*\*\*然后单击"添加**![添加图标"。](media/ITPro-EAC-AddIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="6c919-171">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="6c919-172">在"**新建保留策略"** 页上，**在"名称"** 下键入描述保留策略用途的名称;在"名称"下键入名称。"例如，**保留邮箱的 MRM 策略**。</span><span class="sxs-lookup"><span data-stu-id="6c919-172">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="6c919-173">**在"保留"标记**下，**单击"添加**![图标"。](media/ITPro-EAC-AddIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="6c919-173">Under **Retention tags**, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="6c919-174">在保留标记列表中，选择在步骤 1 中创建的可恢复项目 RPT，然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="6c919-174">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![選取自訂的 [可復原的項目] 保留標記](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="6c919-176">选择要添加到保留策略的其他保留标记。</span><span class="sxs-lookup"><span data-stu-id="6c919-176">Select additional retention tags to add to the retention policy.</span></span> <span data-ttu-id="6c919-177">例如，您可能希望添加默认 MRM 策略中包含的相同标记。</span><span class="sxs-lookup"><span data-stu-id="6c919-177">For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="6c919-178">添加完保留标记后，单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="6c919-178">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="6c919-179">**单击"保存"** 以创建新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="6c919-179">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="6c919-180">请注意，链接到保留策略的保留标记将显示在详细信息窗格中。</span><span class="sxs-lookup"><span data-stu-id="6c919-180">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![連結到保留原則的保留標記，會顯示在詳細資料窗格中](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="6c919-182">使用 Exchange 在线电源外壳创建保留策略</span><span class="sxs-lookup"><span data-stu-id="6c919-182">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="6c919-183">运行以下命令为保留邮箱创建新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="6c919-183">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="6c919-184">例如，以下命令创建保留策略和链接保留标记，这些标记显示在上图中。</span><span class="sxs-lookup"><span data-stu-id="6c919-184">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="6c919-185">步骤 3：将新的保留策略应用于保留的邮箱</span><span class="sxs-lookup"><span data-stu-id="6c919-185">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="6c919-186">最后一步是将您在步骤 2 中创建的新保留策略应用于组织中处于保留状态的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-186">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="6c919-187">您可以使用 EAC 或 Exchange 在线 PowerShell 将保留策略应用于单个邮箱或多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-187">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="6c919-188">使用 EAC 应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="6c919-188">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="6c919-189">转到**收件人**\>**邮箱**。</span><span class="sxs-lookup"><span data-stu-id="6c919-189">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="6c919-190">在列表视图中，选择要应用保留策略的邮箱，然后单击"**编辑"**![图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="6c919-190">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="6c919-191">在"**用户邮箱"** 页上，**单击"邮箱功能"。**</span><span class="sxs-lookup"><span data-stu-id="6c919-191">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="6c919-192">**在"保留策略"** 下，选择在步骤 2 中创建的保留策略，**然后单击"保存"。**</span><span class="sxs-lookup"><span data-stu-id="6c919-192">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="6c919-193">您还可以使用 EAC 将保留策略应用于多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-193">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="6c919-194">转到**收件人**\>**邮箱**。</span><span class="sxs-lookup"><span data-stu-id="6c919-194">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="6c919-195">在清單檢視中，使用 Shift 鍵或 Ctrl 鍵來選取多個信箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-195">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="6c919-196">在詳細資料窗格中，按一下 [其他選項]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6c919-196">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="6c919-197">在 [保留原則]\*\*\*\* 下方，按一下 [更新]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6c919-197">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="6c919-198">在**批量分配保留策略**页上，选择在步骤 2 中创建的保留策略，**然后单击"保存"。**</span><span class="sxs-lookup"><span data-stu-id="6c919-198">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="6c919-199">使用 Exchange 在线电源外壳应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="6c919-199">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="6c919-200">您可以使用 Exchange 在线 PowerShell 将新的保留策略应用于单个邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-200">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="6c919-201">但是，PowerShell 的真正功能是，您可以使用它快速标识组织中处于"诉讼保留"或"就地保留"中的所有邮箱，然后在单个命令中将新的保留策略应用于保留中的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-201">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="6c919-202">下面是使用 Exchange PowerShell 将保留策略应用于一个或多个邮箱的一些示例。</span><span class="sxs-lookup"><span data-stu-id="6c919-202">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="6c919-203">所有示例都应用在步骤 2 中创建的保留策略。</span><span class="sxs-lookup"><span data-stu-id="6c919-203">All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="6c919-204">本示例将新的保留策略应用于 Pilar Pinilla 的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-204">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="6c919-205">本示例将新的保留策略应用于组织中处于诉讼保留状态的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-205">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="6c919-206">本示例将新的保留策略应用于组织中的所有邮箱，这些邮箱处于就地保留状态。</span><span class="sxs-lookup"><span data-stu-id="6c919-206">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="6c919-207">您可以使用**获取邮箱**cmdlet 来验证是否已应用新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="6c919-207">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="6c919-208">下面是一些示例，用于验证上述示例中的命令是否将"保留邮箱的 MRM 策略"保留策略应用于诉讼保留上的邮箱和就地保留的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-208">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="6c919-209">（可选）步骤 4：运行托管文件夹助手以应用新的保留设置</span><span class="sxs-lookup"><span data-stu-id="6c919-209">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="6c919-210">将新的保留策略应用于保留的邮箱后，托管文件夹助理最多可能需要 7 天时间才能使用新保留策略中的设置处理这些邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-210">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="6c919-211">**您可以使用"开始管理文件夹**助手"cmdlet 手动触发助手以处理应用新保留策略的邮箱，而不是等待托管文件夹助手运行。</span><span class="sxs-lookup"><span data-stu-id="6c919-211">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="6c919-212">运行以下命令以启动 Pilar Pinilla 邮箱的托管文件夹助手。</span><span class="sxs-lookup"><span data-stu-id="6c919-212">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="6c919-213">运行以下命令以启动保留的所有邮箱的托管文件夹助手。</span><span class="sxs-lookup"><span data-stu-id="6c919-213">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="6c919-214">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="6c919-214">More information</span></span>

- <span data-ttu-id="6c919-215">启用用户的存档邮箱后，请考虑告诉用户其邮箱中的其他项目（而不仅仅是"可恢复项目"文件夹中的项目）可能会移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c919-215">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="6c919-216">这是因为分配给 Exchange Online 邮箱的默认 MRM 策略包含保留标记（名为"默认 2 年移动到存档"），该标记在项目传递到邮箱或由用户。</span><span class="sxs-lookup"><span data-stu-id="6c919-216">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="6c919-217">有关详细信息，请参阅[联机交换中的默认保留策略](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span><span class="sxs-lookup"><span data-stu-id="6c919-217">For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="6c919-218">启用用户的存档邮箱后，还可以告诉用户，他们可以在其存档邮箱的"可恢复项目"文件夹中恢复已删除的项目。</span><span class="sxs-lookup"><span data-stu-id="6c919-218">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="6c919-219">他们可以在 Outlook 中执行此操作，为此可以在"主页"选项卡上选择"**已删除项目"** 文件夹，然后单击"**从主"** 选项卡**上的"从服务器恢复已删除项目"。** 有关恢复已删除项目的详细信息，请参阅[Windows Outlook 中恢复已删除的项目。](https://go.microsoft.com/fwlink/p/?LinkId=624829)</span><span class="sxs-lookup"><span data-stu-id="6c919-219">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
