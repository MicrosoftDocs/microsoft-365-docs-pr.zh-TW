---
title: 如何找出位於 Exchange Online 信箱的保留類型
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: 了解如何标识可放置在 Office 365 邮箱上的不同类型的保留。 这些类型的保留包括诉讼保留、电子数据展示保留和 Office 365 保留策略。 您还可以确定用户是否已被从组织范围的保留策略中排除
ms.openlocfilehash: 47e7ffff1703c0de94f014dc18e249cc9775e3e2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076288"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a><span data-ttu-id="a8070-105">如何找出位於 Exchange Online 信箱的保留類型</span><span class="sxs-lookup"><span data-stu-id="a8070-105">How to identify the type of hold placed on an Exchange Online mailbox</span></span>

<span data-ttu-id="a8070-106">本文介绍如何识别放在 Office 365 中的 Exchange 联机邮箱上的保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-106">This article explains how to identify holds placed on Exchange Online mailboxes in Office 365.</span></span>

<span data-ttu-id="a8070-107">Office 365 提供了多种方法，您的组织可以防止邮箱内容被永久删除。</span><span class="sxs-lookup"><span data-stu-id="a8070-107">Office 365 offers several ways that your organization can prevent mailbox content from being permanently deleted.</span></span> <span data-ttu-id="a8070-108">这使您的组织能够保留内容以满足合规性法规，或在法律和其他类型的调查期间。</span><span class="sxs-lookup"><span data-stu-id="a8070-108">This allows your organization to retain content to meet compliance regulations or during legal and other types of investigations.</span></span> <span data-ttu-id="a8070-109">下面是 Office 365 中的保留功能（也称为*保留）* 的列表：</span><span class="sxs-lookup"><span data-stu-id="a8070-109">Here's a list of the retention features (also called *holds*) in Office 365:</span></span>

- <span data-ttu-id="a8070-110">**[诉讼保留](create-a-litigation-hold.md)：** 应用于联机交换中的用户邮箱的保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-110">**[Litigation Hold](create-a-litigation-hold.md):** Holds that are applied to user mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="a8070-111">**[电子数据展示持有](ediscovery-cases.md#step-4-place-content-locations-on-hold)：** 与安全和合规性中心中的电子数据展示案例关联的保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-111">**[eDiscovery hold](ediscovery-cases.md#step-4-place-content-locations-on-hold):** Holds that are associated with an eDiscovery case in the security and compliance center.</span></span> <span data-ttu-id="a8070-112">电子数据展示保留可应用于用户邮箱和 Office 365 组和 Microsoft 团队的相应邮箱。</span><span class="sxs-lookup"><span data-stu-id="a8070-112">eDiscovery holds can be applied to user mailboxes and to the corresponding mailbox for Office 365 Groups and Microsoft Teams.</span></span>

- <span data-ttu-id="a8070-113">**[就地保持](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds)：** 使用 Exchange 管理中心中的 Exchange 管理中心中的"就地"电子数据&保留工具应用于用户邮箱的保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-113">**[In-Place Hold](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Holds that are applied to user mailboxes by using the In-Place eDiscovery & Hold tool in the Exchange admin center in Exchange Online.</span></span>

- <span data-ttu-id="a8070-114">\*\* [Office 365 保留策略](retention-policies.md)：\*\* 可以配置为在 Exchange 联机用户邮箱中以及 Office 365 组和 Microsoft 团队的相应邮箱中保留（或保留和删除）用户邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="a8070-114">**[Office 365 retention policies](retention-policies.md):** Can be configured to retain (or retain and then delete) content in user mailboxes in Exchange Online and in the corresponding mailbox for Office 365 Groups and Microsoft Teams.</span></span> <span data-ttu-id="a8070-115">您还可以创建保留策略以保留存储在用户邮箱中的 Skype 业务对话。</span><span class="sxs-lookup"><span data-stu-id="a8070-115">You can also create a retention policy to retain Skype for Business Conversations, which are stored in user mailboxes.</span></span>

  <span data-ttu-id="a8070-116">可以分配给邮箱的 Office 365 保留策略有两种类型。</span><span class="sxs-lookup"><span data-stu-id="a8070-116">There are two types of Office 365 retention policies that can be assigned to mailboxes.</span></span>

    - <span data-ttu-id="a8070-117">**特定位置保留策略：** 这些是分配给特定用户的内容位置的策略。</span><span class="sxs-lookup"><span data-stu-id="a8070-117">**Specific location retention policies:** These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="a8070-118">您可以使用 Exchange 在线 PowerShell 中的**获取邮箱**cmdlet 获取有关分配给特定邮箱的保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="a8070-118">You use the **Get-Mailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific mailboxes.</span></span>

    - <span data-ttu-id="a8070-119">**组织范围的保留策略：** 这些是分配给组织中所有内容位置的策略。</span><span class="sxs-lookup"><span data-stu-id="a8070-119">**Organization-wide retention policies:** These are policies that are assigned to all content locations in your organization.</span></span> <span data-ttu-id="a8070-120">您可以使用 Exchange 在线 PowerShell 中的**获取组织 Config** cmdlet 来获取有关组织范围保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="a8070-120">You use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>
  <span data-ttu-id="a8070-121">有关详细信息，请参阅[Office 365 保留策略概述](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)中的"将保留策略应用于整个组织或特定位置"部分。</span><span class="sxs-lookup"><span data-stu-id="a8070-121">For more information, see the "Applying a retention policy to an entire organization or specific locations" section in [Overview of Office 365 retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

- <span data-ttu-id="a8070-122">**[Office 365 保留标签：](labels.md)** 如果用户将 Office 365 保留标签（配置为保留内容或保留内容，然后删除内容）*应用于其*邮箱中的任何文件夹或项目，则会在邮箱上放置保留，就像邮箱是置于诉讼保留或分配给 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="a8070-122">**[Office 365 retention labels](labels.md):** If a user applies an Office 365 retention label (one that's configured to retain content or retain and then delete content) to *any* folder or item in their mailbox, a hold is placed on the mailbox as if the mailbox was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span> <span data-ttu-id="a8070-123">有关详细信息，请参阅[保留中的标识邮箱，因为保留标签已应用于本文中的文件夹或项目](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)部分。</span><span class="sxs-lookup"><span data-stu-id="a8070-123">For more information, see the [Identifying mailboxes on hold because a retention label has been applied to a folder or item](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) section in this article.</span></span>

<span data-ttu-id="a8070-124">要管理保留邮箱，您可能需要标识放置在邮箱上的保留类型，以便可以执行诸如更改保留持续时间、临时或永久删除保留或从 Office 365 保留策略中排除邮箱等任务。</span><span class="sxs-lookup"><span data-stu-id="a8070-124">To manage mailboxes on hold, you may have to identify the type of hold that's placed on a mailbox so that you can perform tasks such as changing the hold duration, temporarily or permanently removing the hold, or excluding a mailbox from an Office 365 retention policy.</span></span> <span data-ttu-id="a8070-125">在这些情况下，第一步是标识放置在邮箱上的保留类型。</span><span class="sxs-lookup"><span data-stu-id="a8070-125">In these cases, the first step is to identify the type of hold placed on the mailbox.</span></span> <span data-ttu-id="a8070-126">由于可以将多个保留（和不同类型的保留）放置在单个邮箱上，因此如果要删除或更改保留，必须标识放置在邮箱上的所有保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-126">And because multiple holds (and different types of holds) can be placed on a single mailbox, you have to identify all holds placed on a mailbox if you want to remove or change a hold.</span></span>

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a><span data-ttu-id="a8070-127">步骤 1：获取放置在邮箱上的保留的 GUID</span><span class="sxs-lookup"><span data-stu-id="a8070-127">Step 1: Obtain the GUID for holds placed on a mailbox</span></span>

<span data-ttu-id="a8070-128">您可以在 Exchange 在线 PowerShell 中运行以下两个 cmdlet，以获取放置在邮箱上的保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="a8070-128">You can run the following two cmdlets in Exchange Online PowerShell to get the GUID of the holds that are placed on a mailbox.</span></span> <span data-ttu-id="a8070-129">获取 GUID 后，可以使用它来标识步骤 2 中的特定保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-129">After you obtain a GUID, you use it to identify the specific hold in Step 2.</span></span> <span data-ttu-id="a8070-130">GUID 未识别诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-130">A Litigation Hold isn't identified by a GUID.</span></span> <span data-ttu-id="a8070-131">对于邮箱启用或禁用诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-131">Litigation Holds are either enabled or disabled for a mailbox.</span></span>

- <span data-ttu-id="a8070-132">**获取邮箱：** 使用此 cmdlet 可确定是否已为邮箱启用诉讼保留，并获取电子数据展示保留、就地保留和 Office 365 保留策略的 GUID，这些策略专门分配给邮箱。</span><span class="sxs-lookup"><span data-stu-id="a8070-132">**Get-Mailbox:** Use this cmdlet to determine whether Litigation Hold is enabled for a mailbox and to get the GUIDs for eDiscovery holds, In-Place Holds, and Office 365 retention policies that are specifically assigned to a mailbox.</span></span> <span data-ttu-id="a8070-133">此 cmdlet 的输出还将指示邮箱是否已显式从组织范围的保留策略中排除。</span><span class="sxs-lookup"><span data-stu-id="a8070-133">The output of this cmdlet will also indicate if a mailbox has been explicitly excluded from an organization-wide retention policy.</span></span>

- <span data-ttu-id="a8070-134">**获取组织配置：** 使用此 cmdlet 获取组织范围保留策略的 GUID。</span><span class="sxs-lookup"><span data-stu-id="a8070-134">**Get-OrganizationConfig:** Use this cmdlet to get the GUIDs for organization-wide retention policies.</span></span>

<span data-ttu-id="a8070-135">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="a8070-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

### <a name="get-mailbox"></a><span data-ttu-id="a8070-136">Get-Mailbox</span><span class="sxs-lookup"><span data-stu-id="a8070-136">Get-Mailbox</span></span>

<span data-ttu-id="a8070-137">运行以下命令以获取有关应用于邮箱的保留和 Office 365 保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="a8070-137">Run the following command to get information about the holds and Office 365 retention policies applied to a mailbox.</span></span>

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="a8070-138">如果 InPlaceHolds 属性中的值太多，并且并非所有值都显示，则可以运行该`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行上显示每个 GUID。</span><span class="sxs-lookup"><span data-stu-id="a8070-138">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="a8070-139">下表介绍在运行**Get-Mailbox** cmdlet 时，如何根据*InPlaceHolds*属性中的值识别不同类型的保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-139">The following table describes how to identify different types of holds based on the values in the *InPlaceHolds* property when you run the **Get-Mailbox** cmdlet.</span></span>


|<span data-ttu-id="a8070-140">保持类型</span><span class="sxs-lookup"><span data-stu-id="a8070-140">Hold type</span></span>  |<span data-ttu-id="a8070-141">範例值</span><span class="sxs-lookup"><span data-stu-id="a8070-141">Example value</span></span>  |<span data-ttu-id="a8070-142">如何识别保持</span><span class="sxs-lookup"><span data-stu-id="a8070-142">How to identify the hold</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a8070-143">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="a8070-143">Litigation Hold</span></span>     |    `True`     |     <span data-ttu-id="a8070-144">*当"诉讼保留"* 属性设置为`True`时，将启用邮箱的"诉讼保留"。</span><span class="sxs-lookup"><span data-stu-id="a8070-144">Litigation Hold is enabled for a mailbox when the *LitigationHoldEnabled* property is set to `True`.</span></span>    |
|<span data-ttu-id="a8070-145">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="a8070-145">eDiscovery hold</span></span>     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   <span data-ttu-id="a8070-146">*InPlaceHolds 属性*包含与安全和合规性中心中的电子数据展示案例关联的任何保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="a8070-146">The *InPlaceHolds property* contains the GUID of any hold associated with an eDiscovery case in the security and compliance center.</span></span> <span data-ttu-id="a8070-147">可以判断这是一个电子数据展示保留，因为 GUID 以`UniH`前缀开头（表示统一保留）。</span><span class="sxs-lookup"><span data-stu-id="a8070-147">You can tell this is an eDiscovery hold because the GUID starts with the `UniH` prefix (which denotes a Unified Hold).</span></span>      |
|<span data-ttu-id="a8070-148">原有範圍暫止</span><span class="sxs-lookup"><span data-stu-id="a8070-148">In-Place Hold</span></span>     |     `c0ba3ce811b6432a8751430937152491` <br/> <span data-ttu-id="a8070-149">或</span><span class="sxs-lookup"><span data-stu-id="a8070-149">or</span></span> <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     <span data-ttu-id="a8070-150">*InPlaceHolds*属性包含放置在邮箱上的就地保持的 GUID。</span><span class="sxs-lookup"><span data-stu-id="a8070-150">The *InPlaceHolds* property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="a8070-151">您可以判断这是一个就地保留，因为 GUID 要么不以前缀开头，要么以`cld`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="a8070-151">You can tell this is an In-Place Hold because the GUID either doesn't start with a prefix or it starts with the `cld` prefix.</span></span>     |
|<span data-ttu-id="a8070-152">专门应用于邮箱的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="a8070-152">Office 365 retention policy specifically applied to the mailbox</span></span>     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> <span data-ttu-id="a8070-153">或</span><span class="sxs-lookup"><span data-stu-id="a8070-153">or</span></span> <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     <span data-ttu-id="a8070-154">InPlaceHolds 属性包含应用于邮箱的任何特定位置保留策略的 GUID。</span><span class="sxs-lookup"><span data-stu-id="a8070-154">The InPlaceHolds property contains GUIDs of any specific location retention policy that's applied to the mailbox.</span></span> <span data-ttu-id="a8070-155">您可以标识保留策略，因为 GUID 以`mbx`或`skp`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="a8070-155">You can identify retention policies because the GUID starts with the `mbx` or the `skp` prefix.</span></span> <span data-ttu-id="a8070-156">前`skp`缀表示保留策略应用于用户邮箱中的 Skype 业务对话。</span><span class="sxs-lookup"><span data-stu-id="a8070-156">The `skp` prefix indicates that the retention policy is applied to Skype for Business conversations in the user's mailbox.</span></span>    |
|<span data-ttu-id="a8070-157">从组织范围的 Office 365 保留策略中排除</span><span class="sxs-lookup"><span data-stu-id="a8070-157">Excluded from an organization-wide Office 365 retention policy</span></span>     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     <span data-ttu-id="a8070-158">如果邮箱从组织范围的 Office 365 保留策略中排除，则邮箱从中删除的保留策略的 GUID 将显示在 InPlaceHolds 属性中，并由`-mbx`前缀标识。</span><span class="sxs-lookup"><span data-stu-id="a8070-158">If a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy the mailbox is excluded from is displayed in the InPlaceHolds property and is identified by the `-mbx` prefix.</span></span>    |

### <a name="get-organizationconfig"></a><span data-ttu-id="a8070-159">获取组织配置</span><span class="sxs-lookup"><span data-stu-id="a8070-159">Get-OrganizationConfig</span></span>
<span data-ttu-id="a8070-160">如果在运行**Get-Mailbox** cmdlet*时，InPlaceHolds*属性为空，则仍有一个或多个组织范围的 Office 365 保留策略应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="a8070-160">If the *InPlaceHolds* property is empty when you run the **Get-Mailbox** cmdlet, there still may be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span> <span data-ttu-id="a8070-161">在 Exchange 在线 PowerShell 中运行以下命令，以获取组织范围 Office 365 保留策略的 GUID 列表。</span><span class="sxs-lookup"><span data-stu-id="a8070-161">Run the following command in Exchange Online PowerShell to get a list of GUIDs for organization-wide Office 365 retention policies.</span></span>

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="a8070-162">如果 InPlaceHolds 属性中的值太多，并且并非所有值都显示，则可以运行该`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行上显示每个 GUID。</span><span class="sxs-lookup"><span data-stu-id="a8070-162">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="a8070-163">下表描述了不同类型的组织范围保留，以及如何在运行**Get-组织 Config** cmdlet 时根据*InPlaceHolds*属性中包含的 GUID 标识每种类型。</span><span class="sxs-lookup"><span data-stu-id="a8070-163">The following table describes the different types of organization-wide holds and how to identify each type based on the GUIDs contained in *InPlaceHolds* property when you run the **Get-OrganizationConfig** cmdlet.</span></span>


|<span data-ttu-id="a8070-164">保持类型</span><span class="sxs-lookup"><span data-stu-id="a8070-164">Hold type</span></span>  |<span data-ttu-id="a8070-165">範例值</span><span class="sxs-lookup"><span data-stu-id="a8070-165">Example value</span></span>  |<span data-ttu-id="a8070-166">描述</span><span class="sxs-lookup"><span data-stu-id="a8070-166">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a8070-167">Office 365 保留策略应用于 Exchange 邮箱、Exchange 公用文件夹和团队聊天</span><span class="sxs-lookup"><span data-stu-id="a8070-167">Office 365 retention policies applied to Exchange mailboxes, Exchange public folders, and Teams chats</span></span>    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   <span data-ttu-id="a8070-168">应用于 Exchange 邮箱、Exchange 公用文件夹和 Microsoft 团队中的 1xN 聊天的组织范围保留策略由以`mbx`前缀开头的 GUID 标识。</span><span class="sxs-lookup"><span data-stu-id="a8070-168">Organization-wide retention policies applied to Exchange mailboxes, Exchange public folders, and 1xN chats in Microsoft Teams are identified by GUIDs that start with the `mbx` prefix.</span></span> <span data-ttu-id="a8070-169">注意 1xN 聊天存储在各个聊天参与者的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="a8070-169">Note 1xN chats are stored in the mailbox of the individual chat participants.</span></span>      |
|<span data-ttu-id="a8070-170">Office 365 保留策略应用于 Office 365 组和 Teams 频道邮件</span><span class="sxs-lookup"><span data-stu-id="a8070-170">Office 365 retention policy applied to Office 365 Groups and Teams channel messages</span></span>     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    <span data-ttu-id="a8070-171">应用于 Office 365 组和 Microsoft 团队中的渠道消息的组织范围保留策略由以`grp`前缀开头的 GUID 标识。</span><span class="sxs-lookup"><span data-stu-id="a8070-171">Organization-wide retention policies applied to Office 365 groups and channel messages in Microsoft Teams are identified by GUIDs that start with the `grp` prefix.</span></span> <span data-ttu-id="a8070-172">注意通道邮件存储在与 Microsoft 团队关联的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="a8070-172">Note channel messages are stored in the group mailbox that is associated with a Microsoft Team.</span></span>     |

<span data-ttu-id="a8070-173">有关应用于 Microsoft 团队的详细信息保留策略，请参阅[保留策略的"](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)团队位置"部分概述 。</span><span class="sxs-lookup"><span data-stu-id="a8070-173">For more information retention policies applied to Microsoft Teams, see the "Teams location" section [Overview of retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a><span data-ttu-id="a8070-174">了解保留策略的 InPlace 保留值的格式</span><span class="sxs-lookup"><span data-stu-id="a8070-174">Understanding the format of the InPlaceHolds value for retention policies</span></span>

<span data-ttu-id="a8070-175">除了前缀（mbx、skp 或 grp）将 InPlaceHolds 属性中的项标识为 Office 365 保留策略之外，该值还包含一个后缀，用于标识为策略配置的保留操作的类型。</span><span class="sxs-lookup"><span data-stu-id="a8070-175">In addition to the prefix (mbx, skp, or grp) that identifies an item in the InPlaceHolds property as an Office 365 retention policy, the value also contains a suffix that identifies the type of retention action that's configured for the policy.</span></span> <span data-ttu-id="a8070-176">例如，以下示例中以粗体突出显示操作后缀：</span><span class="sxs-lookup"><span data-stu-id="a8070-176">For example, the action suffix is highlighted in bold type in the following examples:</span></span>

   <span data-ttu-id="a8070-177">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span><span class="sxs-lookup"><span data-stu-id="a8070-177">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span></span>

   <span data-ttu-id="a8070-178">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span><span class="sxs-lookup"><span data-stu-id="a8070-178">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span></span>

   <span data-ttu-id="a8070-179">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span><span class="sxs-lookup"><span data-stu-id="a8070-179">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span></span>

<span data-ttu-id="a8070-180">下表定义了三种可能的保留操作：</span><span class="sxs-lookup"><span data-stu-id="a8070-180">The following table defines the three possible retention actions:</span></span>

|<span data-ttu-id="a8070-181">值</span><span class="sxs-lookup"><span data-stu-id="a8070-181">Value</span></span>  |<span data-ttu-id="a8070-182">描述</span><span class="sxs-lookup"><span data-stu-id="a8070-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="a8070-183">**1**</span><span class="sxs-lookup"><span data-stu-id="a8070-183">**1**</span></span>     | <span data-ttu-id="a8070-184">指示保留策略配置为删除项目。</span><span class="sxs-lookup"><span data-stu-id="a8070-184">Indicates that the retention policy is configured to delete items.</span></span> <span data-ttu-id="a8070-185">策略不保留项目。</span><span class="sxs-lookup"><span data-stu-id="a8070-185">The policy doesn't retain items.</span></span>        |
|<span data-ttu-id="a8070-186">**2**</span><span class="sxs-lookup"><span data-stu-id="a8070-186">**2**</span></span>    |    <span data-ttu-id="a8070-187">指示保留策略配置为保留物料。</span><span class="sxs-lookup"><span data-stu-id="a8070-187">Indicates that the retention policy is configured to hold items.</span></span> <span data-ttu-id="a8070-188">保留期到期后，策略不会删除项目。</span><span class="sxs-lookup"><span data-stu-id="a8070-188">The policy doesn't delete items after the retention period expires.</span></span>     |
|<span data-ttu-id="a8070-189">**3**</span><span class="sxs-lookup"><span data-stu-id="a8070-189">**3**</span></span>     |   <span data-ttu-id="a8070-190">指示保留策略配置为保留项目，然后在保留期到期后将其删除。</span><span class="sxs-lookup"><span data-stu-id="a8070-190">Indicates that the retention policy is configured to hold items and then delete them after the retention period expires.</span></span>      |

<span data-ttu-id="a8070-191">有关保留操作的详细信息，请参阅[保留策略概述](retention-policies.md#retaining-content-for-a-specific-period-of-time)中的"保留特定时间段的内容"部分。</span><span class="sxs-lookup"><span data-stu-id="a8070-191">For more information about retention actions, see the "Retaining content for a specific period of time" section in [Overview of retention policies](retention-policies.md#retaining-content-for-a-specific-period-of-time).</span></span>
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a><span data-ttu-id="a8070-192">步骤 2：使用 GUID 标识保持</span><span class="sxs-lookup"><span data-stu-id="a8070-192">Step 2: Use the GUID to identify the hold</span></span>

<span data-ttu-id="a8070-193">获取应用于邮箱的保留的 GUID 后，下一步是使用该 GUID 标识保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-193">After you obtain the GUID for a hold that is applied to a mailbox, the next step is to use that GUID to identify the hold.</span></span> <span data-ttu-id="a8070-194">以下各节演示如何使用保留 GUID 标识保留的名称（和其他信息）。</span><span class="sxs-lookup"><span data-stu-id="a8070-194">The following sections show how to identify the name of the hold (and other information) by using the hold GUID.</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="a8070-195">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="a8070-195">eDiscovery holds</span></span>

<span data-ttu-id="a8070-196">在安全&合规性中心 PowerShell 中运行以下命令，以标识应用于邮箱的电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-196">Run the following commands in Security & Compliance Center PowerShell to identify an eDiscovery hold that's applied to the mailbox.</span></span> <span data-ttu-id="a8070-197">使用 GUID（不包括 UniH 前缀）执行您在步骤 1 中标识的"电子数据展示"保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-197">Use the GUID (not including the UniH prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="a8070-198">第一个命令创建一个变量，其中包含有关保留的信息。</span><span class="sxs-lookup"><span data-stu-id="a8070-198">The first command creates a variable that contains information about the hold.</span></span> <span data-ttu-id="a8070-199">此变量用于其他命令。</span><span class="sxs-lookup"><span data-stu-id="a8070-199">This variable is used in the other commands.</span></span> <span data-ttu-id="a8070-200">第二个命令显示保留关联的电子数据展示案例的名称。</span><span class="sxs-lookup"><span data-stu-id="a8070-200">The second command displays the name of the eDiscovery case the hold is associated with.</span></span> <span data-ttu-id="a8070-201">第三个命令显示保留的名称和保留应用于的邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="a8070-201">The third command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

<span data-ttu-id="a8070-202">要连接到安全&合规性中心 PowerShell，请参阅[连接到安全&合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="a8070-202">To connect to Security & Compliance Center PowerShell, see  [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

### <a name="in-place-holds"></a><span data-ttu-id="a8070-203">就地保留</span><span class="sxs-lookup"><span data-stu-id="a8070-203">In-Place Holds</span></span>

<span data-ttu-id="a8070-204">在 Exchange 联机 PowerShell 中运行以下命令，以标识应用于邮箱的就地保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-204">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's applied to the mailbox.</span></span> <span data-ttu-id="a8070-205">使用 GUID 进行步骤 1 中标识的就地保持。</span><span class="sxs-lookup"><span data-stu-id="a8070-205">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> <span data-ttu-id="a8070-206">该命令显示保留的名称和保留应用于的邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="a8070-206">The command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
<span data-ttu-id="a8070-207">如果就地保留的 GUID 以`cld`前缀开头，请确保在运行上一个命令时包含前缀。</span><span class="sxs-lookup"><span data-stu-id="a8070-207">If the GUID for the In-Place Hold starts with the `cld` prefix, be sure to include the prefix when running the previous command.</span></span>

### <a name="office-365-retention-policies"></a><span data-ttu-id="a8070-208">Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="a8070-208">Office 365 retention policies</span></span>

<span data-ttu-id="a8070-209">在"安全&合规性中心 PowerShell 中运行以下命令，以标识应用于邮箱的 Office 365 保留策略（组织范围或特定位置）。</span><span class="sxs-lookup"><span data-stu-id="a8070-209">Run the following command in Security & Compliance Center PowerShell to identity the Office 365 retention policy (organization-wide or specific location) that's applied to the mailbox.</span></span> <span data-ttu-id="a8070-210">使用您在步骤 1 中标识的 GUID（不包括 mbx、skp 或 grp 前缀或操作后缀）。</span><span class="sxs-lookup"><span data-stu-id="a8070-210">Use the GUID (not including the mbx, skp, or grp prefix or the action suffix) that you identified in Step 1.</span></span>

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a><span data-ttu-id="a8070-211">标识保留邮箱，因为保留标签已应用于文件夹或项目</span><span class="sxs-lookup"><span data-stu-id="a8070-211">Identifying mailboxes on hold because a retention label has been applied to a folder or item</span></span>

<span data-ttu-id="a8070-212">每当用户应用配置为保留内容或保留内容，然后将内容删除到其邮箱中的任何文件夹或项目时，*符合性标记应用*邮箱属性将设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="a8070-212">Whenever a user applies a retention label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="a8070-213">发生这种情况时，邮箱将被视为处于保留状态，就像邮箱被置于诉讼保留或分配给 Office 365 保留策略一样。</span><span class="sxs-lookup"><span data-stu-id="a8070-213">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span> <span data-ttu-id="a8070-214">当*符合性标记应用*属性设置为**True**时，可能会出现以下情况：</span><span class="sxs-lookup"><span data-stu-id="a8070-214">When the *ComplianceTagHoldApplied* property is set to **True**, the following things may occur:</span></span>

- <span data-ttu-id="a8070-215">如果邮箱或用户的 Office 365 用户帐户被删除，则邮箱将成为[非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a8070-215">If the mailbox or the user's Office 365 user account is deleted, the mailbox becomes an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span>
- <span data-ttu-id="a8070-216">无法禁用邮箱（主邮箱或存档邮箱（如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="a8070-216">You aren't able to disable the mailbox (either the primary mailbox or the archive mailbox, if it's enabled).</span></span>
- <span data-ttu-id="a8070-217">邮箱中的项目保留时间可能比预期长。</span><span class="sxs-lookup"><span data-stu-id="a8070-217">Items in the mailbox may be retained longer than expected.</span></span> <span data-ttu-id="a8070-218">这是因为邮箱处于保留状态，因此不会永久删除（清除）任何项目。</span><span class="sxs-lookup"><span data-stu-id="a8070-218">This is because the mailbox is on hold and therefore no items are permanently deleted (purged).</span></span>

<span data-ttu-id="a8070-219">要查看*符合性标记应用*属性的值，在 Exchange 在线 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a8070-219">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="a8070-220">有关保留标签的详细信息，请参阅[Office 365 保留标签概述](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="a8070-220">For more information about retention labels, see [Overview of Office 365 retention labels](labels.md).</span></span>

## <a name="managing-mailboxes-on-delay-hold"></a><span data-ttu-id="a8070-221">管理延迟保留的邮箱</span><span class="sxs-lookup"><span data-stu-id="a8070-221">Managing mailboxes on delay hold</span></span>

<span data-ttu-id="a8070-222">从邮箱中删除任何类型的保留*后，DelayHold 应用*邮箱属性的值将设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="a8070-222">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="a8070-223">下次托管文件夹助理处理邮箱并检测到保留已被删除时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="a8070-223">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold was removed.</span></span> <span data-ttu-id="a8070-224">这称为*延迟保留，* 这意味着实际删除保留将延迟 30 天，以防止数据从邮箱永久删除（清除）。</span><span class="sxs-lookup"><span data-stu-id="a8070-224">This is called a *delay hold* and means that the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted (purged) from the mailbox.</span></span> <span data-ttu-id="a8070-225">这使管理员有机会搜索或恢复在删除保留后将清除的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="a8070-225">This gives admins an opportunity to search for or recover mailbox items that will be purged after the hold is removed.</span></span> <span data-ttu-id="a8070-226">在邮箱上放置延迟保留时，邮箱仍被视为无限期处于保留状态，就像邮箱处于诉讼保留状态一样。</span><span class="sxs-lookup"><span data-stu-id="a8070-226">When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="a8070-227">30 天后，延迟保留将过期，Office 365 将自动尝试删除延迟保留（通过将*DelayHold 应用*属性设置为**False），** 以便删除保留。</span><span class="sxs-lookup"><span data-stu-id="a8070-227">After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="a8070-228">在"*延迟应用"* 属性为**False**后，在托管文件夹助理下一次处理邮箱时，将清除标记为要删除的项目。</span><span class="sxs-lookup"><span data-stu-id="a8070-228">After the *DelayHoldApplied* property to **False**, items that are marked for removal are purged the next time the mailbox is processed by the Managed Folder Assistant.</span></span>

<span data-ttu-id="a8070-229">要查看邮箱的*DelayHold 应用*属性的值，在 Exchange 联机 PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="a8070-229">To view the value for the *DelayHoldApplied* property for a mailbox, run the following command in Exchange Online PowerShell.</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="a8070-230">要在延迟过期之前删除延迟保留，可以在 Exchange 在线 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a8070-230">To remove the delay hold before it expires, you can run the following command in Exchange Online PowerShell:</span></span> 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="a8070-231">您必须在联机交换中分配"法律保留"角色才能*使用"删除延迟应用"* 参数</span><span class="sxs-lookup"><span data-stu-id="a8070-231">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter</span></span> 

<span data-ttu-id="a8070-232">要删除非活动邮箱的延迟保留，请运行 Exchange 在线 PowerShell 中的以下命令：</span><span class="sxs-lookup"><span data-stu-id="a8070-232">To remove the delay hold on an inactive mailbox, run the following command in Exchange Online PowerShell:</span></span>

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> <span data-ttu-id="a8070-233">在前面的命令中指定非活动邮箱的最佳方法是使用其可分辨名称或 Exchange GUID 值。</span><span class="sxs-lookup"><span data-stu-id="a8070-233">The best way to specify an inactive mailbox in the previous command is to use its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="a8070-234">使用这些值之一有助于防止意外指定错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a8070-234">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="a8070-235">後續步驟</span><span class="sxs-lookup"><span data-stu-id="a8070-235">Next steps</span></span>

<span data-ttu-id="a8070-236">标识应用于邮箱的保留后，可以执行诸如更改保留持续时间、临时或永久删除保留或从 Office 365 保留策略中排除非活动邮箱等任务。</span><span class="sxs-lookup"><span data-stu-id="a8070-236">After you identify the holds that are applied to a mailbox, you can perform tasks such as changing the duration of the hold, temporarily or permanently removing the hold, or excluding an inactive mailbox from an Office 365 retention policy.</span></span> <span data-ttu-id="a8070-237">有关执行与保留相关的任务的详细信息，请参阅以下主题之一：</span><span class="sxs-lookup"><span data-stu-id="a8070-237">For more information about performing tasks related to holds, see the one of the following topics:</span></span>

- <span data-ttu-id="a8070-238">在安全&合规性中心 PowerShell 中[运行"\<设置保留合规性策略 - 添加ExchangeLocationException 用户邮箱>"](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)命令，以从组织范围的 Office 365 保留策略中排除邮箱。</span><span class="sxs-lookup"><span data-stu-id="a8070-238">Run the [Set-RetentionCompliancePolicy -AddExchangeLocationException \<user mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) command in Security & Compliance Center PowerShell to exclude a mailbox from an organization-wide Office 365 retention policy.</span></span> <span data-ttu-id="a8070-239">此命令只能用于*ExchangeLocation*属性的值等于 的`All`保留策略。</span><span class="sxs-lookup"><span data-stu-id="a8070-239">This command can only be used for retention policies where the value for the *ExchangeLocation* property equals `All`.</span></span>

- <span data-ttu-id="a8070-240">在 Exchange Online PowerShell 中[运行"设置邮箱 - 排除 FromOrgHolds"\<保留 GUID，不带前缀或后缀>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)命令，以便从组织范围的 Office 365 保留策略中排除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="a8070-240">Run the [Set-Mailbox -ExcludeFromOrgHolds \<hold GUID without prefix or suffix>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide Office 365 retention policy.</span></span>

- [<span data-ttu-id="a8070-241">更改 Office 365 中非活动邮箱的保留持续时间</span><span class="sxs-lookup"><span data-stu-id="a8070-241">Change the hold duration for an inactive mailbox in Office 365</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="a8070-242">删除 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="a8070-242">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

- [<span data-ttu-id="a8070-243">刪除雲端式信箱中可復原的項目資料夾中的保留項目</span><span class="sxs-lookup"><span data-stu-id="a8070-243">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
