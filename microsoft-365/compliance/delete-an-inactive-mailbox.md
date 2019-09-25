---
title: 删除 Office 365 中的非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: 当您不再需要保留 Office 365 非活动邮箱的内容时，可以通过删除保留来永久删除非活动邮箱。 删除保留后，非活动邮箱将被标记为删除，并在处理后永久删除。
ms.openlocfilehash: b6cea7284ccb930ef10ec96c082291acb9f66f2f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070624"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="f685e-104">删除 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="f685e-104">Delete an inactive mailbox in Office 365</span></span>

<span data-ttu-id="f685e-105">在前任員工離開您的組織之後，可透過非使用中信箱來保留其電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f685e-105">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="f685e-106">当您不再需要保留非活动邮箱的内容时，可以通过删除保留来永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-106">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="f685e-107">此外，有可能在非活动邮箱上放置多个保留。</span><span class="sxs-lookup"><span data-stu-id="f685e-107">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="f685e-108">例如，非活动邮箱可能放在诉讼保留和一个或多个就地保留上。</span><span class="sxs-lookup"><span data-stu-id="f685e-108">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="f685e-109">此外，Office 365 保留策略（在 Office 365 或 Microsoft 365 中的安全和合规性中心创建）可能应用于非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-109">Additionally, an Office 365 retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="f685e-110">您必须从非活动邮箱中删除所有保留和 Office 365 保留策略才能将其删除。</span><span class="sxs-lookup"><span data-stu-id="f685e-110">You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="f685e-111">删除保留和保留策略后，非活动邮箱将被标记为删除，并在处理后永久删除。</span><span class="sxs-lookup"><span data-stu-id="f685e-111">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f685e-p103">我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
<span data-ttu-id="f685e-117">有关从非活动邮箱中删除保留后发生的情况的说明，[请参阅"详细信息"](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="f685e-117">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="f685e-118">開始之前</span><span class="sxs-lookup"><span data-stu-id="f685e-118">Before you begin</span></span>

- <span data-ttu-id="f685e-119">您必须使用 Exchange 在线 PowerShell 从非活动邮箱中删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="f685e-119">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="f685e-120">不能使用 Exchange 管理中心 （EAC）。</span><span class="sxs-lookup"><span data-stu-id="f685e-120">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="f685e-121">有关分步说明，请参阅[连接到交换在线 PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="f685e-121">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="f685e-122">您可以使用 Exchange 在线电源外壳或 EAC 从非活动邮箱中删除就地保留。</span><span class="sxs-lookup"><span data-stu-id="f685e-122">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="f685e-123">在删除保留并删除非活动邮箱之前，可以将非活动邮箱的内容复制到其他邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-123">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="f685e-124">有关详细信息，请参阅[在 Office 365 中还原非活动邮箱。](restore-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="f685e-124">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="f685e-125">如果从非活动邮箱中删除保留或 Office 365 保留策略，并且邮箱的软删除邮箱保留期已过期，则邮箱将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="f685e-125">If you remove the hold or Office 365 retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="f685e-126">删除后，无法恢复。</span><span class="sxs-lookup"><span data-stu-id="f685e-126">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="f685e-127">在删除保留之前，请确保不再需要邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="f685e-127">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="f685e-128">如果要重新激活非活动邮箱，可以恢复它。</span><span class="sxs-lookup"><span data-stu-id="f685e-128">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="f685e-129">有关详细信息，请参阅[在 Office 365 中恢复非活动邮箱。](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="f685e-129">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="f685e-130">有关非活动邮箱的详细信息，请参阅 Office [365 中的非活动邮箱。](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f685e-130">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="f685e-131">步骤 1：识别非活动邮箱上的保留</span><span class="sxs-lookup"><span data-stu-id="f685e-131">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="f685e-132">如前所述，诉讼保留、就地保留或 Office 365 保留策略可能放置在非活动邮箱中。</span><span class="sxs-lookup"><span data-stu-id="f685e-132">As previously stated, a Litigation Hold, In-Place Hold, or Office 365 retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="f685e-133">第一步是标识非活动邮箱上的保留。</span><span class="sxs-lookup"><span data-stu-id="f685e-133">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="f685e-134">运行以下命令以显示组织中所有非活动邮箱的保留信息。</span><span class="sxs-lookup"><span data-stu-id="f685e-134">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="f685e-135">**诉讼保留**属性的**True**值表示非活动邮箱处于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="f685e-135">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="f685e-136">如果将就地保留放在非活动邮箱上，则保留的 GUID 将显示为**InPlaceHolds**属性的值。</span><span class="sxs-lookup"><span data-stu-id="f685e-136">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="f685e-137">例如，两个非活动邮箱的以下结果显示，在 Ann Beebe 上放置了诉讼保留，在 Pilar Pinilla 上放置了两个就地保留。</span><span class="sxs-lookup"><span data-stu-id="f685e-137">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="f685e-138">如果将大量就地保留放在非活动邮箱上，则并非所有就地保留 GUID 都会显示。</span><span class="sxs-lookup"><span data-stu-id="f685e-138">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="f685e-139">可以运行以下命令以显示所有就地保持 GUID：`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="f685e-139">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="f685e-140">步骤 2：从非活动邮箱中删除保留</span><span class="sxs-lookup"><span data-stu-id="f685e-140">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="f685e-141">确定非活动邮箱上放置的保留类型（以及是否存在多个保留）后，下一步是删除邮箱上的保留。</span><span class="sxs-lookup"><span data-stu-id="f685e-141">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="f685e-142">如前所述，您必须删除所有保留才能永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-142">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="f685e-143">删除诉讼保留</span><span class="sxs-lookup"><span data-stu-id="f685e-143">Remove a Litigation Hold</span></span>

<span data-ttu-id="f685e-144">如前所述，您必须使用 Windows PowerShell 从非活动邮箱中删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="f685e-144">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="f685e-145">不能使用 EAC。</span><span class="sxs-lookup"><span data-stu-id="f685e-145">You can't use the EAC.</span></span> <span data-ttu-id="f685e-146">运行以下命令以删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="f685e-146">Run the following command to remove a Litigation Hold.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="f685e-147">标识非活动邮箱的最佳方法是使用其可分辨名称或 Exchange GUID 值。</span><span class="sxs-lookup"><span data-stu-id="f685e-147">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="f685e-148">使用这些值之一有助于防止意外指定错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-148">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="f685e-149">移除就地保留</span><span class="sxs-lookup"><span data-stu-id="f685e-149">Remove In-Place Holds</span></span>

 <span data-ttu-id="f685e-150">有两种方法可以从非活动邮箱中删除就地保留：</span><span class="sxs-lookup"><span data-stu-id="f685e-150">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="f685e-151">**删除就地保留对象**如果要永久删除的非活动邮箱是就地保留的唯一源邮箱，则只需删除就地保留对象即可。</span><span class="sxs-lookup"><span data-stu-id="f685e-151">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f685e-152">您必须禁用保留，然后才能删除就地保留对象。</span><span class="sxs-lookup"><span data-stu-id="f685e-152">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="f685e-153">如果尝试删除启用了保留的就地保留对象，您将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="f685e-153">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="f685e-154">**将非活动邮箱作为就地保留的源邮箱删除**如果要保留其他源邮箱以进行就地保留，可以从源邮箱列表中删除非活动邮箱，并保留就地保留对象。</span><span class="sxs-lookup"><span data-stu-id="f685e-154">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="f685e-155">使用 EAC 删除就地保留</span><span class="sxs-lookup"><span data-stu-id="f685e-155">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="f685e-156">如果您知道要删除的就地保留的名称，则可以转到下一步。</span><span class="sxs-lookup"><span data-stu-id="f685e-156">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span></span> <span data-ttu-id="f685e-157">否则，请运行以下命令以获取放置在要永久删除的非活动邮箱上的就地保留的名称。</span><span class="sxs-lookup"><span data-stu-id="f685e-157">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span></span> <span data-ttu-id="f685e-158">使用您在步骤 1 中获取的就地保留[GUID：识别非活动邮箱上的保留。](#step-1-identify-the-holds-on-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="f685e-158">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="f685e-159">在 EAC 中，转到**合规管理**\>**就地电子数据&amp;展示保留**。</span><span class="sxs-lookup"><span data-stu-id="f685e-159">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="f685e-160">选择要删除的就地保持，然后单击"**编辑**![编辑"图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="f685e-160">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="f685e-161">在"**就地"电子数据&amp;展示保留**属性页上，**单击"就地保留"，** 取消选中与**所选邮箱中的搜索查询匹配的"保留"框中的"放置内容"，\*\*\*\*然后单击"保存"。**</span><span class="sxs-lookup"><span data-stu-id="f685e-161">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="f685e-162">在**就地电子&amp;数据展示保留**页上，再次选择就地保持，然后单击"**删除"**![图标](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)。</span><span class="sxs-lookup"><span data-stu-id="f685e-162">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="f685e-163">在警告中，单击"**是"** 以删除就地保留。</span><span class="sxs-lookup"><span data-stu-id="f685e-163">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="f685e-164">使用 Exchange 在线电源外壳删除就地保留</span><span class="sxs-lookup"><span data-stu-id="f685e-164">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="f685e-165">创建一个变量，其中包含要删除的就地保留的属性。</span><span class="sxs-lookup"><span data-stu-id="f685e-165">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="f685e-166">使用您在步骤 1 中获取的就地保留[GUID：识别非活动邮箱上的保留。](#step-1-identify-the-holds-on-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="f685e-166">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="f685e-167">禁用就地保留。</span><span class="sxs-lookup"><span data-stu-id="f685e-167">Disable the hold on the In-Place Hold.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. <span data-ttu-id="f685e-168">删除就地保留。</span><span class="sxs-lookup"><span data-stu-id="f685e-168">Delete the In-Place Hold.</span></span>
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="f685e-169">使用 EAC 从就地保留中删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="f685e-169">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="f685e-170">如果您知道放置在非活动邮箱上的就地保留的名称，则可以转到下一步。</span><span class="sxs-lookup"><span data-stu-id="f685e-170">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span></span> <span data-ttu-id="f685e-171">否则，运行以下命令以获取放置在邮箱上的就地保留的名称。</span><span class="sxs-lookup"><span data-stu-id="f685e-171">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span></span> <span data-ttu-id="f685e-172">使用您在步骤 1 中获取的就地保留[GUID：识别非活动邮箱上的保留。](#step-1-identify-the-holds-on-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="f685e-172">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="f685e-173">在 EAC 中，转到**合规管理**\>**就地电子数据&amp;展示保留**。</span><span class="sxs-lookup"><span data-stu-id="f685e-173">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="f685e-174">选择放置在非活动邮箱上的就地保持，然后单击"**编辑**![编辑"图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="f685e-174">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="f685e-175">在**就地电子数据展示&amp;保留**属性页上，单击"**源"。**</span><span class="sxs-lookup"><span data-stu-id="f685e-175">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="f685e-176">在源邮箱列表中，单击要删除的非活动邮箱的名称，然后单击"**删除"**![图标](media/adf01106-cc79-475c-8673-065371c1897b.gif)。</span><span class="sxs-lookup"><span data-stu-id="f685e-176">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="f685e-177">**单击"保存"** 以保存更改。</span><span class="sxs-lookup"><span data-stu-id="f685e-177">Click **Save** to save the change.</span></span> <span data-ttu-id="f685e-178">将显示一条消息，指出操作已成功完成。</span><span class="sxs-lookup"><span data-stu-id="f685e-178">A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="f685e-179">重复步骤 1 到 6 以删除放置在非活动邮箱上的其他就地保留。</span><span class="sxs-lookup"><span data-stu-id="f685e-179">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="f685e-180">使用 Exchange 在线 PowerShell 从就地保留中删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="f685e-180">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="f685e-181">如果就地保留包含大量源邮箱，则非活动邮箱可能不会列在 EAC**中的"源"** 页上。</span><span class="sxs-lookup"><span data-stu-id="f685e-181">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="f685e-182">编辑就地保留时，"**源"** 页上最多显示 3，000 个邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-182">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="f685e-183">**如果"源"** 页上未列出非活动邮箱，则可以使用 Exchange 在线 PowerShell 将其从就地保留中删除。</span><span class="sxs-lookup"><span data-stu-id="f685e-183">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="f685e-184">创建一个变量，其中包含放置在非活动邮箱上的就地保留的属性。</span><span class="sxs-lookup"><span data-stu-id="f685e-184">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="f685e-185">使用您在步骤 1 中获取的就地保留[GUID：识别非活动邮箱上的保留。](#step-1-identify-the-holds-on-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="f685e-185">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="f685e-186">验证非活动邮箱是否列为就地保留的源邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-186">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
```
  $InPlaceHold.Sources
```

   <span data-ttu-id="f685e-187">**注意：**"就地保留"的*源*属性通过*源 ExchangeDN*属性标识源邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-187">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="f685e-188">由于此属性唯一标识非活动邮箱，因此使用"就地保留"中的*源*属性有助于防止删除错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-188">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="f685e-189">如果两个邮箱具有相同的别名或 SMTP 地址，这也有助于避免出现问题。</span><span class="sxs-lookup"><span data-stu-id="f685e-189">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="f685e-190">从变量中的源邮箱列表中删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-190">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="f685e-191">请确保使用上一步中命令返回的非活动邮箱的**LegacyExchangeDN。**</span><span class="sxs-lookup"><span data-stu-id="f685e-191">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. <span data-ttu-id="f685e-192">验证非活动邮箱是否从变量中的源邮箱列表中删除。</span><span class="sxs-lookup"><span data-stu-id="f685e-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
```
  $InPlaceHold.Sources
```

5. <span data-ttu-id="f685e-193">使用更新的源邮箱列表修改就地保留，该列表不包括非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. <span data-ttu-id="f685e-194">验证非活动邮箱是否已从就地保留的源邮箱列表中删除。</span><span class="sxs-lookup"><span data-stu-id="f685e-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a><span data-ttu-id="f685e-195">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="f685e-195">More information</span></span>

- <span data-ttu-id="f685e-196">**非活动邮箱是软删除邮箱的类型。**</span><span class="sxs-lookup"><span data-stu-id="f685e-196">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="f685e-197">在 Exchange Online 中，软删除邮箱是已删除但可在特定保留期内恢复的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-197">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="f685e-198">Exchange 联机中的软删除邮箱保留期为 30 天。</span><span class="sxs-lookup"><span data-stu-id="f685e-198">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="f685e-199">这意味着邮箱可以在软删除后的 30 天内恢复。</span><span class="sxs-lookup"><span data-stu-id="f685e-199">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="f685e-200">30 天后，软删除邮箱被标记为永久删除，无法恢复。</span><span class="sxs-lookup"><span data-stu-id="f685e-200">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="f685e-201">**删除非活动邮箱上的保留后会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="f685e-201">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="f685e-202">该邮箱被视为其他软删除邮箱，并在 30 天软删除邮箱保留期到期后标记为永久删除。</span><span class="sxs-lookup"><span data-stu-id="f685e-202">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="f685e-203">此保留期从首次使邮箱处于非活动状态的日期开始。</span><span class="sxs-lookup"><span data-stu-id="f685e-203">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="f685e-204">此日期称为软删除日期，即相应的 Office 365 用户帐户被删除的日期，或**使用"删除**邮箱"cmdlet 删除 Exchange Online 邮箱的日期。</span><span class="sxs-lookup"><span data-stu-id="f685e-204">This date is known as the soft-deleted date, which is the date the corresponding Office 365 user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="f685e-205">软删除日期不是您删除保留的日期。</span><span class="sxs-lookup"><span data-stu-id="f685e-205">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="f685e-206">**在删除保留后，非活动邮箱是否立即永久删除？**</span><span class="sxs-lookup"><span data-stu-id="f685e-206">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="f685e-207">如果非活动邮箱的软删除日期超过 30 天，则删除保留后不会永久删除该邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-207">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="f685e-208">该邮箱将被标记为永久删除，并在下次处理时将其删除。</span><span class="sxs-lookup"><span data-stu-id="f685e-208">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="f685e-209">**软删除邮箱保留期如何影响非活动邮箱？**</span><span class="sxs-lookup"><span data-stu-id="f685e-209">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="f685e-210">如果非活动邮箱的软删除日期比删除保留的日期早 30 天，则邮箱将被标记为永久删除。</span><span class="sxs-lookup"><span data-stu-id="f685e-210">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="f685e-211">但是，如果非活动邮箱在过去 30 天内具有软删除日期，而您删除了保留，则可以恢复邮箱，直到软删除邮箱保留期到期。</span><span class="sxs-lookup"><span data-stu-id="f685e-211">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="f685e-212">有关详细信息，请参阅[联机交换中删除或还原用户邮箱。](https://go.microsoft.com/fwlink/?linkid=856835)</span><span class="sxs-lookup"><span data-stu-id="f685e-212">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="f685e-213">软删除邮箱保留期到期后，您已按照恢复非活动邮箱的过程。</span><span class="sxs-lookup"><span data-stu-id="f685e-213">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="f685e-214">有关详细信息，请参阅[在 Office 365 中恢复非活动邮箱。](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="f685e-214">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="f685e-215">**删除保留后，如何显示有关非活动邮箱的信息？**</span><span class="sxs-lookup"><span data-stu-id="f685e-215">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="f685e-216">删除保留并将非活动邮箱还原回软删除邮箱后，不会使用"*非活动邮箱"* 参数与**Get-邮箱**cmdlet 一起返回。</span><span class="sxs-lookup"><span data-stu-id="f685e-216">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="f685e-217">但是，您可以使用**获取邮箱 -软删除邮箱**命令显示有关邮箱的信息。</span><span class="sxs-lookup"><span data-stu-id="f685e-217">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="f685e-218">例如：</span><span class="sxs-lookup"><span data-stu-id="f685e-218">For example:</span></span> 
    
```
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
```
  
<span data-ttu-id="f685e-219">在上面的*示例中，WhenSoftDeletedd*属性标识软删除日期，在此示例中为 2014 年 10 月 30 日。</span><span class="sxs-lookup"><span data-stu-id="f685e-219">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="f685e-220">如果此软删除邮箱以前是已为其删除保留的非活动邮箱，则将在*WhenSoftDeleteds*属性的值后 30 天永久删除该邮箱。</span><span class="sxs-lookup"><span data-stu-id="f685e-220">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="f685e-221">在这种情况下，邮箱在 2014 年 11 月 30 日之后将永久删除。</span><span class="sxs-lookup"><span data-stu-id="f685e-221">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

