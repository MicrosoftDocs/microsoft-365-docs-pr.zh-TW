---
title: 编辑信息障碍策略
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 了解如何编辑或删除信息障碍的策略。
ms.openlocfilehash: 20a1dd62fa80469a7a31db9b5541064ae16b4e02
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076240"
---
# <a name="edit-or-remove-information-barrier-policies"></a><span data-ttu-id="e6c9c-103">编辑（或删除）信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="e6c9c-103">Edit (or remove) information barrier policies</span></span>

<span data-ttu-id="e6c9c-104">[定义信息屏障策略](information-barriers-policies.md)后，您可能需要更改这些策略或用户细分，作为[故障排除](information-barriers-troubleshooting.md)的一部分或作为常规维护。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-104">After you have [defined information barrier policies](information-barriers-policies.md), you might need to make changes to those policies or to your user segments, as part of [troubleshooting](information-barriers-troubleshooting.md) or as regular maintenance.</span></span> <span data-ttu-id="e6c9c-105">使用本文作为指南。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-105">Use this article as a guide.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="e6c9c-106">您要執行的工作</span><span class="sxs-lookup"><span data-stu-id="e6c9c-106">What do you want to do?</span></span>

|<span data-ttu-id="e6c9c-107">動作</span><span class="sxs-lookup"><span data-stu-id="e6c9c-107">Action</span></span>  |<span data-ttu-id="e6c9c-108">描述</span><span class="sxs-lookup"><span data-stu-id="e6c9c-108">Description</span></span> |
|---------|---------|
|[<span data-ttu-id="e6c9c-109">编辑用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="e6c9c-109">Edit user account attributes</span></span>](#edit-user-account-attributes)     |<span data-ttu-id="e6c9c-110">在 Azure 活动目录中填充可用于定义段的属性。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-110">Fill in attributes in Azure Active Directory that can be used to define segments.</span></span><br/><span data-ttu-id="e6c9c-111">当用户未包含在用户应包含的细分中时，编辑用户帐户属性，更改用户位于哪个细分，或使用不同的属性定义细分。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-111">Edit user account attributes when users are not included in segments they should be, to change which segments users are in, or to define segments using different attributes.</span></span>         |
|[<span data-ttu-id="e6c9c-112">编辑线段</span><span class="sxs-lookup"><span data-stu-id="e6c9c-112">Edit a segment</span></span>](#edit-a-segment)     |<span data-ttu-id="e6c9c-113">当您希望更改线段的定义方式时，请编辑线段。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-113">Edit segments when you want to change how a segment is defined.</span></span> <br/><span data-ttu-id="e6c9c-114">例如，您可能最初*使用"部门"* 定义段，现在想要使用另一个属性，如*成员。*</span><span class="sxs-lookup"><span data-stu-id="e6c9c-114">For example, you might have originally defined segments using *Department* and now want to use another attribute, such as *MemberOf*.</span></span>         |
|[<span data-ttu-id="e6c9c-115">编辑策略</span><span class="sxs-lookup"><span data-stu-id="e6c9c-115">Edit a policy</span></span>](#edit-a-policy)     |<span data-ttu-id="e6c9c-116">当您希望更改策略的工作方式时，编辑信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-116">Edit an information barrier policy when you want to change how a policy works.</span></span><br/><span data-ttu-id="e6c9c-117">例如，您可能决定只允许仅在特定段之间发生通信，而不是阻止两个段之间的通信。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-117">For example, instead of blocking communications between two segments, you might decide you want to allow communications to occur only between certain segments.</span></span>         |
|[<span data-ttu-id="e6c9c-118">将策略设置为非活动状态</span><span class="sxs-lookup"><span data-stu-id="e6c9c-118">Set a policy to inactive status</span></span>](#set-a-policy-to-inactive-status)     |<span data-ttu-id="e6c9c-119">当您要对策略进行更改或不希望策略生效时，将策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-119">Set a policy to inactive status when you want to make changes to a policy, or when you don't want a policy to be in effect.</span></span>         |
|[<span data-ttu-id="e6c9c-120">删除策略</span><span class="sxs-lookup"><span data-stu-id="e6c9c-120">Remove a policy</span></span>](#remove-a-policy)     |<span data-ttu-id="e6c9c-121">当您不再需要特定策略时，请删除信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-121">Remove an information barrier policy when you no longer need a particular policy in place.</span></span>         |
|[<span data-ttu-id="e6c9c-122">停止策略应用程序</span><span class="sxs-lookup"><span data-stu-id="e6c9c-122">Stop a policy application</span></span>](#stop-a-policy-application)     |<span data-ttu-id="e6c9c-123">如果要停止应用信息屏障策略的过程，可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-123">Do this when you want to stop the process of applying information barrier policies.</span></span><br/><span data-ttu-id="e6c9c-124">请注意，停止策略应用程序不是即时的，也不会撤消已应用于用户的策略。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-124">Note that stopping a policy application is not instant, and it does not undo policies that are already applied to users.</span></span>         |
|[<span data-ttu-id="e6c9c-125">定义信息障碍的策略</span><span class="sxs-lookup"><span data-stu-id="e6c9c-125">Define policies for information barriers</span></span>](information-barriers-policies.md)     |<span data-ttu-id="e6c9c-126">当您尚未实施此类策略时，请定义信息屏障策略，并且必须限制或限制特定用户组之间的通信。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-126">Define an information barrier policy when you do not already have such policies in place, and you must restrict or limit communications between specific groups of users.</span></span>         |
|[<span data-ttu-id="e6c9c-127">排除信息障碍</span><span class="sxs-lookup"><span data-stu-id="e6c9c-127">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)     |<span data-ttu-id="e6c9c-128">遇到信息障碍的意外问题时，请参阅本文。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-128">Refer to this article when you run into unexpected issues with information barriers.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="e6c9c-129">要执行本文中描述的任务，必须为您分配适当的角色，例如：</span><span class="sxs-lookup"><span data-stu-id="e6c9c-129">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="e6c9c-130">- 微软365企业全球管理员</span><span class="sxs-lookup"><span data-stu-id="e6c9c-130">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="e6c9c-131">- Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="e6c9c-131">- Office 365 Global Administrator</span></span><br/><span data-ttu-id="e6c9c-132">- 合规管理员</span><span class="sxs-lookup"><span data-stu-id="e6c9c-132">- Compliance Administrator</span></span><br/><span data-ttu-id="e6c9c-133">- IB合规管理（这是一个新角色！</span><span class="sxs-lookup"><span data-stu-id="e6c9c-133">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="e6c9c-134">要了解有关信息障碍先决条件的详细信息，请参阅[先决条件（有关信息障碍策略）。](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="e6c9c-134">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="e6c9c-135">请确保连接到[Office 365 安全&合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-135">Make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="edit-user-account-attributes"></a><span data-ttu-id="e6c9c-136">编辑用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="e6c9c-136">Edit user account attributes</span></span>

<span data-ttu-id="e6c9c-137">使用此过程可以编辑用于分段用户的属性。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-137">Use this procedure to edit attributes that are used for segmenting users.</span></span> 

<span data-ttu-id="e6c9c-138">例如，如果您使用的是"部门"属性，并且一个或多个用户帐户当前没有为"部门"列出任何值，则必须编辑这些用户帐户以包括部门信息。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-138">For example, if you are using a Department attribute, and one or more user accounts do not currently have any values listed for Department, you must edit those user accounts to include Department information.</span></span> 

<span data-ttu-id="e6c9c-139">用户帐户属性用于定义段，以便可以分配信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-139">User account attributes are used for defining segments so that information barrier policies can be assigned.</span></span>

1. <span data-ttu-id="e6c9c-140">要查看特定用户帐户的详细信息（如属性值和分配的段），请使用具有标识参数的**获取信息系统接收状态**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-140">To view details for a specific user account, such as attribute values and assigned segment(s), use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> 

    |<span data-ttu-id="e6c9c-141">語法</span><span class="sxs-lookup"><span data-stu-id="e6c9c-141">Syntax</span></span>  |<span data-ttu-id="e6c9c-142">範例</span><span class="sxs-lookup"><span data-stu-id="e6c9c-142">Example</span></span>  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>   <span data-ttu-id="e6c9c-143">您可以使用唯一标识每个用户的任何值，例如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-143">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p>   <span data-ttu-id="e6c9c-144">（您也可以将此 cmdlet 用于单个用户： `Get-InformationBarrierRecipientStatus -Identity <value>`</span><span class="sxs-lookup"><span data-stu-id="e6c9c-144">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span>      |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`  <p>   <span data-ttu-id="e6c9c-145">在此示例中，我们在 Office 365 中提到了两个用户帐户：*梅根*的*meganb*和*Alexw*的*Alexw。*</span><span class="sxs-lookup"><span data-stu-id="e6c9c-145">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span>         |

2. <span data-ttu-id="e6c9c-146">确定要为用户帐户配置文件编辑的属性。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-146">Determine which attribute you want to edit for your user account profile(s).</span></span> <span data-ttu-id="e6c9c-147">有关详细信息，请参阅[属性信息屏障策略。](information-barriers-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="e6c9c-147">Refer to [Attributes for information barrier policies](information-barriers-attributes.md) for more details.</span></span> 

3. <span data-ttu-id="e6c9c-148">编辑一个或多个用户帐户以包括您在上一步中选择的属性的值。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-148">Edit one or more user accounts to include values for the attribute you selected in the previous step.</span></span> <span data-ttu-id="e6c9c-149">为此，请使用以下过程之一：</span><span class="sxs-lookup"><span data-stu-id="e6c9c-149">To do this, use one of the following procedures:</span></span>

    - <span data-ttu-id="e6c9c-150">要编辑单个帐户，请参阅[使用 Azure 活动目录 添加或更新用户的配置文件信息。](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="e6c9c-150">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

    - <span data-ttu-id="e6c9c-151">要编辑多个帐户（或使用 PowerShell 编辑单个帐户），请参阅[使用 Office 365 PowerShell 配置用户帐户属性。](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="e6c9c-151">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

## <a name="edit-a-segment"></a><span data-ttu-id="e6c9c-152">编辑线段</span><span class="sxs-lookup"><span data-stu-id="e6c9c-152">Edit a segment</span></span>

<span data-ttu-id="e6c9c-153">使用此过程编辑用户段的定义。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-153">Use this procedure edit the definition of a user segment.</span></span> <span data-ttu-id="e6c9c-154">例如，您可以更改段的名称，或用于确定段中包括谁的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-154">For example, you might change the name of a segment, or the filter that is used to determine who's included in the segment.</span></span>

1. <span data-ttu-id="e6c9c-155">要查看所有现有段，请使用**获取组织段**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-155">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="e6c9c-156">语法：`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="e6c9c-156">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="e6c9c-157">您将看到每个段和详细信息的列表，例如段类型、其 UserGroupFilter 值、创建或上次修改该值的人员、GUID 等。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-157">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="e6c9c-158">打印或保存段列表以供以后参考。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-158">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="e6c9c-159">例如，如果要编辑段，则需要知道其名称或标识值（这与"标识"参数一起使用）。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-159">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="e6c9c-160">要编辑段，请使用具有**标识**参数和相关详细信息**的"设置组织段**cmdlet"。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-160">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    |<span data-ttu-id="e6c9c-161">語法</span><span class="sxs-lookup"><span data-stu-id="e6c9c-161">Syntax</span></span>  |<span data-ttu-id="e6c9c-162">範例</span><span class="sxs-lookup"><span data-stu-id="e6c9c-162">Example</span></span>  |
    |---------|---------|
    |`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`     |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p><span data-ttu-id="e6c9c-163">在此示例中，对于具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的段，我们将部门名称更新为"HRDept"。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-163">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>         |

<span data-ttu-id="e6c9c-164">完成为组织编辑细分后，可以[定义](information-barriers-policies.md#part-2-define-information-barrier-policies)或[编辑](#edit-a-policy)信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-164">When you have finished editing segments for your organization, you can either [define](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

## <a name="edit-a-policy"></a><span data-ttu-id="e6c9c-165">编辑策略</span><span class="sxs-lookup"><span data-stu-id="e6c9c-165">Edit a policy</span></span>

1. <span data-ttu-id="e6c9c-166">要查看当前信息障碍策略的列表，请使用**获取信息障碍策略**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-166">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="e6c9c-167">语法：`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="e6c9c-167">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="e6c9c-168">在结果列表中，标识要更改的策略。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-168">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="e6c9c-169">请注意策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-169">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="e6c9c-170">使用具有**标识**参数**的"设置信息障碍策略**cmdlet"，并指定要进行更改。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-170">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="e6c9c-171">示例：假设定义了策略以阻止*研究*部分与*销售*和*市场营销*部门通信。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-171">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="e6c9c-172">该策略是使用此 cmdlet 定义的：`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="e6c9c-172">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>
    
    <span data-ttu-id="e6c9c-173">假设我们想要更改它，以便*研究*部分的人只能与*HR*部门中的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-173">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="e6c9c-174">要进行此更改，我们使用此 cmdlet：`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="e6c9c-174">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="e6c9c-175">在此示例中，我们将"段阻止"更改为"允许分段"，并指定了*HR*段。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-175">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="e6c9c-176">编辑完策略后，请确保应用更改。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-176">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="e6c9c-177">（请参阅[应用信息屏障策略。](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="e6c9c-177">(See [Apply information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)</span></span>

## <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="e6c9c-178">将策略设置为非活动状态</span><span class="sxs-lookup"><span data-stu-id="e6c9c-178">Set a policy to inactive status</span></span>

1. <span data-ttu-id="e6c9c-179">要查看当前信息障碍策略的列表，请使用**获取信息障碍策略**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-179">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="e6c9c-180">语法：`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="e6c9c-180">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="e6c9c-181">在结果列表中，标识要更改（或删除）的策略。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-181">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="e6c9c-182">请注意策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-182">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="e6c9c-183">要将策略的状态设置为非活动状态，请使用具有标识参数和状态参数设置为"非活动"**的"设置信息保护策略**cmdlet"。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-183">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    |<span data-ttu-id="e6c9c-184">語法</span><span class="sxs-lookup"><span data-stu-id="e6c9c-184">Syntax</span></span>  |<span data-ttu-id="e6c9c-185">範例</span><span class="sxs-lookup"><span data-stu-id="e6c9c-185">Example</span></span>  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Inactive`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p><span data-ttu-id="e6c9c-186">在此示例中，我们将 GUID *43c37853-ea10-4b90-a23d-ab8c9377247*设置为非活动状态的信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-186">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>         |

3. <span data-ttu-id="e6c9c-187">要应用更改，**请使用"开始信息策略**应用程序"cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-187">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="e6c9c-188">语法：`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="e6c9c-188">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="e6c9c-189">更改将（按用户）应用于您的组织。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-189">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="e6c9c-190">如果您的组织很大，则此过程可能需要 24 小时（或更长时间）才能完成。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-190">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="e6c9c-191">（作为一般准则，处理 5，000 个用户帐户大约需要一个小时。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-191">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="e6c9c-192">此时，一个或多个信息障碍策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-192">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="e6c9c-193">在此处，您可以执行以下任何操作：</span><span class="sxs-lookup"><span data-stu-id="e6c9c-193">From here, you can do any of the following:</span></span>
- <span data-ttu-id="e6c9c-194">保持现状（设置为非活动状态的策略对用户没有影响）</span><span class="sxs-lookup"><span data-stu-id="e6c9c-194">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="e6c9c-195">编辑策略</span><span class="sxs-lookup"><span data-stu-id="e6c9c-195">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="e6c9c-196">删除策略</span><span class="sxs-lookup"><span data-stu-id="e6c9c-196">Remove a policy</span></span>](#remove-a-policy)

## <a name="remove-a-policy"></a><span data-ttu-id="e6c9c-197">删除策略</span><span class="sxs-lookup"><span data-stu-id="e6c9c-197">Remove a policy</span></span>

1. <span data-ttu-id="e6c9c-198">要查看当前信息障碍策略的列表，请使用**获取信息障碍策略**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-198">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="e6c9c-199">语法：`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="e6c9c-199">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="e6c9c-200">在结果列表中，标识要删除的策略。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-200">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="e6c9c-201">请注意策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-201">Note the policy's GUID and name.</span></span> <span data-ttu-id="e6c9c-202">确保策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-202">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="e6c9c-203">使用具有标识参数**的删除信息策略**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-203">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="e6c9c-204">語法</span><span class="sxs-lookup"><span data-stu-id="e6c9c-204">Syntax</span></span>  |<span data-ttu-id="e6c9c-205">範例</span><span class="sxs-lookup"><span data-stu-id="e6c9c-205">Example</span></span>  |
    |---------|---------|
    |`Remove-InformationBarrierPolicy -Identity GUID`     |`Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p><span data-ttu-id="e6c9c-206">在此示例中，我们将删除具有 GUID *43c37853-ea10-4b90-a23d-ab8c93772471*的策略。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-206">In this example, we are removing the policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span>          |

    <span data-ttu-id="e6c9c-207">当出现提示时，请确认更改。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-207">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="e6c9c-208">对要删除的每个策略重复步骤 1-2。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-208">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="e6c9c-209">删除策略完成后，应用更改。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-209">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="e6c9c-210">为此，请使用**启动信息策略应用程序**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-210">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="e6c9c-211">语法：`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="e6c9c-211">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="e6c9c-212">更改将（按用户）应用于您的组织。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-212">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="e6c9c-213">如果您的组织很大，则此过程可能需要 24 小时（或更长时间）才能完成。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-213">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

## <a name="stop-a-policy-application"></a><span data-ttu-id="e6c9c-214">停止策略应用程序</span><span class="sxs-lookup"><span data-stu-id="e6c9c-214">Stop a policy application</span></span>

<span data-ttu-id="e6c9c-215">如果要在开始应用信息障碍策略后，要停止应用这些策略，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-215">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="e6c9c-216">请记住，该过程大约需要 30-35 分钟。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-216">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="e6c9c-217">要查看最新的信息障碍策略应用程序的状态，请使用**获取信息障碍策略应用程序状态**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-217">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="e6c9c-218">语法：`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="e6c9c-218">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="e6c9c-219">请注意应用程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-219">Note the application's GUID.</span></span>

2. <span data-ttu-id="e6c9c-220">使用具有标识参数的**停止信息策略应用程序**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-220">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="e6c9c-221">語法</span><span class="sxs-lookup"><span data-stu-id="e6c9c-221">Syntax</span></span>  |<span data-ttu-id="e6c9c-222">範例</span><span class="sxs-lookup"><span data-stu-id="e6c9c-222">Example</span></span>  |
    |---------|---------|
    |`Stop-InformationBarrierPoliciesApplication -Identity GUID`     |`Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p><span data-ttu-id="e6c9c-223">在此示例中，我们将阻止应用信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="e6c9c-223">In this example, we are stopping information barrier policies from being applied.</span></span>         |

## <a name="related-articles"></a><span data-ttu-id="e6c9c-224">相關文章</span><span class="sxs-lookup"><span data-stu-id="e6c9c-224">Related articles</span></span>

[<span data-ttu-id="e6c9c-225">获取信息障碍概述</span><span class="sxs-lookup"><span data-stu-id="e6c9c-225">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="e6c9c-226">定义信息障碍的策略</span><span class="sxs-lookup"><span data-stu-id="e6c9c-226">Define policies for information barriers</span></span>](information-barriers-policies.md)

[<span data-ttu-id="e6c9c-227">了解有关 Microsoft 团队中信息障碍的详细信息</span><span class="sxs-lookup"><span data-stu-id="e6c9c-227">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="e6c9c-228">信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="e6c9c-228">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="e6c9c-229">排除信息障碍</span><span class="sxs-lookup"><span data-stu-id="e6c9c-229">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)
