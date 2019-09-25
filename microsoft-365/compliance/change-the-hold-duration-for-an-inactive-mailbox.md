---
title: 更改 Office 365 中非活动邮箱的保留持续时间
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: 使 Office 365 邮箱处于非活动状态后，可以更改分配给非活动邮箱的保留或 Office 365 保留策略的持续时间。 保留持续时间定义"可恢复项目"文件夹中的项目持有时间。
ms.openlocfilehash: 7840131af3df32b8b8e5a0faa1b101f9ec8ef541
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076647"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="5defd-104">更改 Office 365 中非活动邮箱的保留持续时间</span><span class="sxs-lookup"><span data-stu-id="5defd-104">Change the hold duration for an inactive mailbox in Office 365</span></span>

<span data-ttu-id="5defd-105">非活动邮箱用于在前员工离开您的组织后保留其电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5defd-105">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="5defd-106">当在邮箱上放置诉讼保留、就地保留、Office 365 保留策略或与电子数据展示案例关联的保留时，邮箱将变为非活动状态，并且相应的 Office 365 用户帐户将被删除。</span><span class="sxs-lookup"><span data-stu-id="5defd-106">A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, an Office 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding Office 365 user account is deleted.</span></span> <span data-ttu-id="5defd-107">非活动邮箱的内容在邮箱处于非活动状态之前放在邮箱上的保留期间保留。</span><span class="sxs-lookup"><span data-stu-id="5defd-107">The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive.</span></span> <span data-ttu-id="5defd-108">保留持续时间定义"可恢复项目"文件夹中的项目持有时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-108">The hold duration defines how long items in the Recoverable Items folder are held.</span></span> <span data-ttu-id="5defd-109">当"可恢复项目"文件夹中的项目的保留持续时间过期时，该项目将从非活动邮箱中永久删除（清除）。</span><span class="sxs-lookup"><span data-stu-id="5defd-109">When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="5defd-110">使邮箱处于非活动状态后，可以更改分配给非活动邮箱的保留或 Office 365 保留策略的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-110">After a mailbox is made inactive, you can change the duration of the hold or Office 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5defd-p103">我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="5defd-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="5defd-116">開始之前</span><span class="sxs-lookup"><span data-stu-id="5defd-116">Before you begin</span></span>

- <span data-ttu-id="5defd-117">您必须使用 Exchange 在线 PowerShell 更改非活动邮箱的诉讼保留的保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-117">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox.</span></span> <span data-ttu-id="5defd-118">不能使用 Exchange 管理中心 （EAC）。</span><span class="sxs-lookup"><span data-stu-id="5defd-118">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="5defd-119">但是，您可以使用 Exchange 在线 PowerShell 或 EAC 来更改就地保留的保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-119">But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold.</span></span> <span data-ttu-id="5defd-120">您可以使用安全和合规性中心或安全&合规性中心 PowerShell 更改 Office 365 保留策略的保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-120">You can use the security and compliance center or the Security & Compliance Center PowerShell to change the hold duration for an Office 365 retention policy.</span></span>
    
- <span data-ttu-id="5defd-121">要连接到 Exchange 在线 PowerShell 或安全&合规性中心 PowerShell，请参阅以下主题之一：</span><span class="sxs-lookup"><span data-stu-id="5defd-121">To connect to Exchange Online PowerShell or Security & Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="5defd-122">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="5defd-122">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [<span data-ttu-id="5defd-123">连接到 Office 365 安全&合规性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5defd-123">Connect to Office 365 Security& Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
- <span data-ttu-id="5defd-124">请注意，与电子数据展示案例关联的保留是无限保留，这意味着没有可以更改的保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-124">Note that holds associated with eDiscovery cases are infinite holds, which means there is no hold duration that can be changed.</span></span> <span data-ttu-id="5defd-125">项目将永久保留，或直到删除保留并删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5defd-125">Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="5defd-126">有关非活动邮箱的详细信息，请参阅 Office [365 中的非活动邮箱。](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="5defd-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="5defd-127">步骤 1：识别非活动邮箱上的保留</span><span class="sxs-lookup"><span data-stu-id="5defd-127">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="5defd-128">由于不同类型的保留或一个或多个 Office 365 保留策略可能放置在非活动邮箱上，因此第一步是标识非活动邮箱上的保留。</span><span class="sxs-lookup"><span data-stu-id="5defd-128">Because different types of holds or one or more Office 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="5defd-129">在 Exchange 联机 PowerShell 中运行以下命令，以显示组织中所有非活动邮箱的保留信息。</span><span class="sxs-lookup"><span data-stu-id="5defd-129">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
<span data-ttu-id="5defd-130">**诉讼保留**属性的**True**值表示非活动邮箱处于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="5defd-130">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="5defd-131">如果将就地保留、电子数据展示保留或 Office 365 保留策略放在非活动邮箱上，则保留或保留策略的 GUID 将显示为**InPlaceHolds**属性的值。</span><span class="sxs-lookup"><span data-stu-id="5defd-131">If an In-Place Hold, eDiscovery hold, or Office 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="5defd-132">例如，下面显示 5 个非活动邮箱的结果。</span><span class="sxs-lookup"><span data-stu-id="5defd-132">For example, the following shows results for 5 inactive mailboxes.</span></span> 
  
||
|:-----|
|
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```
   
<span data-ttu-id="5defd-133">下表标识了用于使每个邮箱处于非活动状态的五种不同的保留类型。</span><span class="sxs-lookup"><span data-stu-id="5defd-133">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="5defd-134">**非活动邮箱**</span><span class="sxs-lookup"><span data-stu-id="5defd-134">**Inactive mailbox**</span></span>|<span data-ttu-id="5defd-135">**保持类型**</span><span class="sxs-lookup"><span data-stu-id="5defd-135">**Hold type**</span></span>|<span data-ttu-id="5defd-136">**如何识别非活动邮箱的保留**</span><span class="sxs-lookup"><span data-stu-id="5defd-136">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5defd-137">安·比比</span><span class="sxs-lookup"><span data-stu-id="5defd-137">Ann Beebe</span></span>  <br/> |<span data-ttu-id="5defd-138">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="5defd-138">Litigation Hold</span></span>  <br/> |<span data-ttu-id="5defd-139">*诉讼保留属性*设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="5defd-139">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="5defd-140">皮拉尔·皮尼拉</span><span class="sxs-lookup"><span data-stu-id="5defd-140">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="5defd-141">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="5defd-141">In-Place Hold</span></span>  <br/> |<span data-ttu-id="5defd-142">*InPlaceHolds*属性包含放置在非活动邮箱上的就地保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5defd-142">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="5defd-143">您可以判断这是就地保留，因为 ID 不以前缀开头。</span><span class="sxs-lookup"><span data-stu-id="5defd-143">You can tell this is an In-Place Hold because the ID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="5defd-144">您可以使用 Exchange`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`联机 PowerShell 中的命令获取有关非活动邮箱的就地保留的信息。</span><span class="sxs-lookup"><span data-stu-id="5defd-144">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="5defd-145">马里奥·内塞塞</span><span class="sxs-lookup"><span data-stu-id="5defd-145">Mario Necaise</span></span>  <br/> |<span data-ttu-id="5defd-146">安全&合规性中心中的组织范围 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="5defd-146">Organization-wide Office 365 retention policy in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="5defd-147">*"InPlaceHolds"* 属性为空。</span><span class="sxs-lookup"><span data-stu-id="5defd-147">The  *InPlaceHolds*  property is empty.</span></span> <span data-ttu-id="5defd-148">这表示一个或多个组织范围或（Exchange 范围）Office 365 保留策略应用于非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5defd-148">This indicates that one or more organization-wide or (Exchange-wide) Office 365 retention policy is applied to the inactive mailbox.</span></span> <span data-ttu-id="5defd-149">在这种情况下，您可以在 Exchange Online `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` PowerShell 中运行该命令，以获取组织范围 Office 365 保留策略的 GUID 列表。</span><span class="sxs-lookup"><span data-stu-id="5defd-149">In this case, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies.</span></span> <span data-ttu-id="5defd-150">应用于 Exchange 邮箱的组织范围保留策略的 GUID 以`mbx`前缀开头;例如`mbxa3056bb15562480fadb46ce523ff7b02`.</span><span class="sxs-lookup"><span data-stu-id="5defd-150">The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <br/><span data-ttu-id="5defd-151">要标识应用于非活动邮箱的 Office 365 保留策略，在"安全&合规性中心 PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="5defd-151">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span>  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|<span data-ttu-id="5defd-152">卡罗尔·奥尔森</span><span class="sxs-lookup"><span data-stu-id="5defd-152">Carol Olson</span></span>  <br/> |<span data-ttu-id="5defd-153">安全&合规性中心中的 Office 365 保留策略应用于特定邮箱</span><span class="sxs-lookup"><span data-stu-id="5defd-153">Office 365 retention policy in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="5defd-154">*InPlaceHolds*属性包含应用于非活动邮箱的 Office 365 保留策略的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5defd-154">The  *InPlaceHolds*  property contains the GUID of the Office 365 retention policy that's applied to the inactive mailbox.</span></span> <span data-ttu-id="5defd-155">可以判断这是应用于特定邮箱的保留策略，因为 GUID 以`mbx`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="5defd-155">You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="5defd-156">请注意，如果应用于非活动邮箱的保留策略 GUID 以`skp`前缀开头，则表示保留策略应用于 Skype 业务对话。</span><span class="sxs-lookup"><span data-stu-id="5defd-156">Note that if GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, that would indicate that the retention policy is applied to Skype for Business conversations.</span></span>  <br/><br/> <span data-ttu-id="5defd-157">要标识应用于非活动邮箱的 Office 365 保留策略，在"安全&合规性中心 PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="5defd-157">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span><br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/><span data-ttu-id="5defd-158">运行此命令时，`mbx`请确保`skp`删除 或 前缀。</span><span class="sxs-lookup"><span data-stu-id="5defd-158">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="5defd-159">亚伯拉罕·麦克马洪</span><span class="sxs-lookup"><span data-stu-id="5defd-159">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="5defd-160">安全&合规中心持有电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="5defd-160">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="5defd-161">*InPlaceHolds*属性包含放置在非活动邮箱上的第一数据展示案例保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5defd-161">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="5defd-162">可以判断这是一个电子数据展示案例保留，因为 GUID 以`UniH`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="5defd-162">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="5defd-163">您可以使用安全&合规性`Get-CaseHoldPolicy`中心 PowerShell 中的 cmdlet 获取有关非活动邮箱保留关联的电子数据展示案例的信息。</span><span class="sxs-lookup"><span data-stu-id="5defd-163">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with.</span></span> <span data-ttu-id="5defd-164">例如，可以运行该命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`来显示非活动邮箱上的案例保留的名称。</span><span class="sxs-lookup"><span data-stu-id="5defd-164">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox.</span></span> <span data-ttu-id="5defd-165">运行此命令时，`UniH`请确保删除前缀。</span><span class="sxs-lookup"><span data-stu-id="5defd-165">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="5defd-166">要标识非活动邮箱上的保留与电子数据展示情况，应运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="5defd-166">To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.</span></span>  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> <span data-ttu-id="5defd-167">**注意：** 我们不建议对非活动邮箱使用电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="5defd-167">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes.</span></span> <span data-ttu-id="5defd-168">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span><span class="sxs-lookup"><span data-stu-id="5defd-168">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span></span> <span data-ttu-id="5defd-169">在某个时候，法律案例可能会结束，与案例关联的保留将被删除，电子数据展示案例将关闭（或删除）。</span><span class="sxs-lookup"><span data-stu-id="5defd-169">At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted).</span></span> <span data-ttu-id="5defd-170">事实上，如果放置在非活动邮箱上的保留与电子数据展示案例相关联，并且保留被释放或电子数据展示案例已关闭或删除，则非活动邮箱将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="5defd-170">In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="5defd-171">有关 Office 365 保留策略的详细信息，请参阅[保留策略概述](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5defd-171">For more information about Office 365 retention policies, see [Overview of retention policies](retention-policies.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="5defd-172">步骤 2：更改非活动邮箱的保留持续时间</span><span class="sxs-lookup"><span data-stu-id="5defd-172">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="5defd-173">确定非活动邮箱上放置的保留类型（以及是否存在多个保留）后，下一步是更改保留的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-173">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="5defd-174">更改诉讼保留的持续时间</span><span class="sxs-lookup"><span data-stu-id="5defd-174">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="5defd-175">下面讨论如何使用 Exchange Online PowerShell 更改放置在非活动邮箱上的诉讼保留的保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-175">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox.</span></span> <span data-ttu-id="5defd-176">不能使用 EAC。</span><span class="sxs-lookup"><span data-stu-id="5defd-176">You can't use the EAC.</span></span> <span data-ttu-id="5defd-177">运行以下命令以更改保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-177">Run the following command to change the hold duration.</span></span> <span data-ttu-id="5defd-178">在此示例中，保留持续时间更改为无限时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-178">In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="5defd-179">结果是，非活动邮箱中的项目将无限期保留，或者直到删除保留或保留持续时间更改为其他值。</span><span class="sxs-lookup"><span data-stu-id="5defd-179">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="5defd-180">标识非活动邮箱的最佳方法是使用其**可分辨名称**或 Exchange **GUID**值。</span><span class="sxs-lookup"><span data-stu-id="5defd-180">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value.</span></span> <span data-ttu-id="5defd-181">使用这些值之一有助于防止意外指定错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5defd-181">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="5defd-182">更改就地保留的持续时间</span><span class="sxs-lookup"><span data-stu-id="5defd-182">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="5defd-183">您可以使用 EAC 或 Exchange 在线电源外壳更改就地保留的保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-183">You can use the EAC or Exchange Online PowerShell to change the hold duration for an In-Place Hold.</span></span> 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a><span data-ttu-id="5defd-184">使用 EAC 更改保留持续时间</span><span class="sxs-lookup"><span data-stu-id="5defd-184">Use the EAC to change the hold duration</span></span>

1. <span data-ttu-id="5defd-185">如果您知道要更改的就地保留的名称，则转到下一步。</span><span class="sxs-lookup"><span data-stu-id="5defd-185">If you know the name of the In-Place Hold that you want to change, go to the next step.</span></span> <span data-ttu-id="5defd-186">否则，运行以下命令以获取放置在非活动邮箱上的就地保留的名称。</span><span class="sxs-lookup"><span data-stu-id="5defd-186">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox.</span></span> <span data-ttu-id="5defd-187">使用[您在步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获取的就地保持 GUID。</span><span class="sxs-lookup"><span data-stu-id="5defd-187">Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="5defd-188">在 EAC 中，转到**合规管理**\>**就地电子数据&amp;展示保留**。</span><span class="sxs-lookup"><span data-stu-id="5defd-188">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="5defd-189">选择要更改的就地保持，然后单击"**编辑"**![图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="5defd-189">Select the In-Place Hold you want to change, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="5defd-190">在**就地电子数据&amp;展示保留**属性页上，**单击"就地保留"。**</span><span class="sxs-lookup"><span data-stu-id="5defd-190">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**.</span></span> 
    
5. <span data-ttu-id="5defd-191">根据当前保留持续时间执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="5defd-191">Do one of the following based on the current hold duration:</span></span>
    
1. <span data-ttu-id="5defd-192">**单击"无限期保留"** 以无限期保留项目。</span><span class="sxs-lookup"><span data-stu-id="5defd-192">Click **Hold indefinitely** to hold items for an unlimited period of time.</span></span> 
    
2. <span data-ttu-id="5defd-193">**单击"指定相对于其接收日期保留物料的天数"** 以保留特定期间的物料。</span><span class="sxs-lookup"><span data-stu-id="5defd-193">Click **Specify number of days to hold items relative to their received date** to hold items for a specific period.</span></span> <span data-ttu-id="5defd-194">键入要为其保留项目的天数。</span><span class="sxs-lookup"><span data-stu-id="5defd-194">Type the number of days that you want to hold items for.</span></span> 
    
    ![變更就地保留之持續期間的螢幕擷取畫面](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. <span data-ttu-id="5defd-196">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5defd-196">Click **Save**.</span></span>
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a><span data-ttu-id="5defd-197">使用 Exchange 在线电源外壳更改保留持续时间</span><span class="sxs-lookup"><span data-stu-id="5defd-197">Use Exchange Online PowerShell to change the hold duration</span></span>

1. <span data-ttu-id="5defd-198">如果您知道要更改的就地保留的名称，则转到下一步。</span><span class="sxs-lookup"><span data-stu-id="5defd-198">If you know the name of the In-Place Hold that you want to change, go to the next step.</span></span> <span data-ttu-id="5defd-199">否则，运行以下命令以获取放置在非活动邮箱上的就地保留的名称。</span><span class="sxs-lookup"><span data-stu-id="5defd-199">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox.</span></span> <span data-ttu-id="5defd-200">使用[您在步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获取的就地保持 GUID。</span><span class="sxs-lookup"><span data-stu-id="5defd-200">Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="5defd-201">运行以下命令以更改保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-201">Run the following command to change the hold duration.</span></span> <span data-ttu-id="5defd-202">在此示例中，保留持续时间更改为 2，555 天（约 7 年）。</span><span class="sxs-lookup"><span data-stu-id="5defd-202">In this example, the hold duration is changed to 2,555 days (approximately 7 years).</span></span> 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     <span data-ttu-id="5defd-203">要将保留持续时间更改为无限制的时间，请使用 _-ItemHoldS 无限期限。_</span><span class="sxs-lookup"><span data-stu-id="5defd-203">To change the hold duration to an unlimited period of time, use  _-ItemHoldPeriod unlimited_.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="5defd-204">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="5defd-204">More information</span></span>

- <span data-ttu-id="5defd-205">**如何为非活动邮箱中的项目计算保留持续时间？**</span><span class="sxs-lookup"><span data-stu-id="5defd-205">**How is the hold duration calculated for an item in an inactive mailbox?**</span></span> <span data-ttu-id="5defd-206">持续时间从接收或创建邮箱项目的原始日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="5defd-206">The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="5defd-207">**当保留持续时间到期时会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="5defd-207">**What happens when the hold duration expires?**</span></span> <span data-ttu-id="5defd-208">当"可恢复项目"文件夹中的邮箱项目的保留持续时间过期时，该项目将从非活动邮箱中永久删除（清除）。</span><span class="sxs-lookup"><span data-stu-id="5defd-208">When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="5defd-209">如果没有为在非活动邮箱上放置的保留指定持续时间，则"可恢复项目"文件夹中的项目永远不会被清除（除非更改非活动邮箱的保留持续时间）。</span><span class="sxs-lookup"><span data-stu-id="5defd-209">If there is no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="5defd-210">**是否仍在非活动邮箱上处理 Exchange 保留策略？**</span><span class="sxs-lookup"><span data-stu-id="5defd-210">**Is an Exchange retention policy still processed on inactive mailboxes?**</span></span> <span data-ttu-id="5defd-211">如果 Exchange 保留策略（邮件记录管理或 Exchange Online 中的 MRM 功能）在邮箱处于非活动状态时应用于该邮箱，则删除策略（**配置为"删除**保留"操作的保留标记）将继续在非活动邮箱上处理。</span><span class="sxs-lookup"><span data-stu-id="5defd-211">If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox.</span></span> <span data-ttu-id="5defd-212">这意味着在保留期到期时，使用删除策略标记的项目将移动到"可恢复项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="5defd-212">That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires.</span></span> <span data-ttu-id="5defd-213">然后，当项目的保留期限到期时，将从非活动邮箱中清除这些项目。</span><span class="sxs-lookup"><span data-stu-id="5defd-213">Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="5defd-214">相反，分配给非活动邮箱的保留策略中包含的任何存档策略（即配置了使用**MoveToArchive**保留操作的保留标记）都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="5defd-214">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored.</span></span> <span data-ttu-id="5defd-215">这意味着在保留期到期时，使用存档策略标记的非活动邮箱中的项目将保留在主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5defd-215">That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires.</span></span> <span data-ttu-id="5defd-216">它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="5defd-216">They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="5defd-217">由于用户无法登录到非活动邮箱，因此没有理由使用数据中心资源来处理存档策略。</span><span class="sxs-lookup"><span data-stu-id="5defd-217">Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 
    
- <span data-ttu-id="5defd-218">**要检查新的保留持续时间，请运行以下命令之一。**</span><span class="sxs-lookup"><span data-stu-id="5defd-218">**To check the new hold duration, run one of the following commands.**</span></span> <span data-ttu-id="5defd-219">第一个命令是诉讼保留;第二个用于就地保持。</span><span class="sxs-lookup"><span data-stu-id="5defd-219">The first command is for Litigation Hold; the second is for In-Place Hold.</span></span> 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- <span data-ttu-id="5defd-220">**与常规邮箱一样，托管文件夹助理 （MFA） 也处理非活动邮箱。**</span><span class="sxs-lookup"><span data-stu-id="5defd-220">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.**</span></span> <span data-ttu-id="5defd-221">在 Exchange 在线中，MFA 大约每 7 天处理一次邮箱。</span><span class="sxs-lookup"><span data-stu-id="5defd-221">In Exchange Online, the MFA processes mailboxes approximately once every 7 days.</span></span> <span data-ttu-id="5defd-222">更改非活动邮箱的保留持续时间后，**可以使用"开始管理文件夹助理**cmdlet"立即开始处理非活动邮箱的新保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="5defd-222">After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox.</span></span> <span data-ttu-id="5defd-223">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="5defd-223">Run the following command.</span></span> 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="5defd-224">**如果在非活动邮箱上放置了许多保留，则并非所有保留 GUID 都会显示。**</span><span class="sxs-lookup"><span data-stu-id="5defd-224">**If a lot of holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.**</span></span> <span data-ttu-id="5defd-225">可以运行以下命令来显示放置在非活动邮箱上的所有保留（诉讼保留除外）的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5defd-225">You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
