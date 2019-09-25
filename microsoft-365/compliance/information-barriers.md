---
title: 信息障碍概述
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
description: 使用信息障碍确保在组织内使用 Microsoft 团队确保通信合规性。
ms.openlocfilehash: c4a9213e74129126da0cbc41b7bc210a10b34db2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077130"
---
# <a name="information-barriers"></a><span data-ttu-id="f31be-103">信息障碍</span><span class="sxs-lookup"><span data-stu-id="f31be-103">Information barriers</span></span>

## <a name="overview"></a><span data-ttu-id="f31be-104">概觀</span><span class="sxs-lookup"><span data-stu-id="f31be-104">Overview</span></span>

<span data-ttu-id="f31be-105">Microsoft 云服务包括强大的通信和协作功能。</span><span class="sxs-lookup"><span data-stu-id="f31be-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="f31be-106">但是，假设您要限制两个组之间的通信，以避免在组织中发生利益冲突。</span><span class="sxs-lookup"><span data-stu-id="f31be-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="f31be-107">或者，您可能希望限制组织内某些人员之间的通信，以保护内部信息。</span><span class="sxs-lookup"><span data-stu-id="f31be-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="f31be-108">Microsoft 365 支持跨组和组织之间的通信和协作，因此是否有方法在必要时限制特定用户组之间的通信？</span><span class="sxs-lookup"><span data-stu-id="f31be-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="f31be-109">有了信息障碍，你可以！</span><span class="sxs-lookup"><span data-stu-id="f31be-109">With information barriers, you can!</span></span> 

<span data-ttu-id="f31be-110">信息障碍正在推出，从微软团队开始。</span><span class="sxs-lookup"><span data-stu-id="f31be-110">Information barriers are rolling out now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="f31be-111">假设[您的订阅](#required-licenses-and-permissions)包含信息障碍，合规性管理员或信息障碍管理员可以定义策略以允许或阻止 Microsoft Teams 中的用户组之间的通信。</span><span class="sxs-lookup"><span data-stu-id="f31be-111">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="f31be-112">信息屏障策略可用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="f31be-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="f31be-113">日交易者不能呼叫营销团队中的某个人</span><span class="sxs-lookup"><span data-stu-id="f31be-113">A day trader cannot call someone on the marketing team</span></span>
- <span data-ttu-id="f31be-114">处理公司机密信息的财务人员无法接收组织内某些团体的电话</span><span class="sxs-lookup"><span data-stu-id="f31be-114">Finance personnel working on confidential company information cannot receive calls from certain groups within their organization</span></span>
- <span data-ttu-id="f31be-115">具有商业机密材料的内部团队无法与组织内某些组中的人在线通话或聊天</span><span class="sxs-lookup"><span data-stu-id="f31be-115">An internal team with trade secret material cannot call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="f31be-116">研究团队只能与产品开发团队在线通话或聊天</span><span class="sxs-lookup"><span data-stu-id="f31be-116">A research team can only call or chat online with a product development team</span></span>

<span data-ttu-id="f31be-117">对于所有这些示例方案（以及更多），可以定义信息屏障策略，以防止或允许 Microsoft 团队中的通信。</span><span class="sxs-lookup"><span data-stu-id="f31be-117">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="f31be-118">此类策略可以防止人们呼叫或聊天，或阻止人们与 Microsoft Teams 中的特定组通信。</span><span class="sxs-lookup"><span data-stu-id="f31be-118">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="f31be-119">在信息障碍策略生效后，每当受这些策略保护的用户尝试与 Microsoft Teams 中的其他人通信时，都会进行检查以阻止（或允许）通信（由信息屏障策略定义）。</span><span class="sxs-lookup"><span data-stu-id="f31be-119">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="f31be-120">要了解有关具有信息障碍的用户体验的详细信息，请参阅[Microsoft 团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="f31be-120">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f31be-121">目前，信息障碍不适用于电子邮件通信或通过 SharePoint 在线或 OneDrive 进行文件共享。</span><span class="sxs-lookup"><span data-stu-id="f31be-121">Currently, information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="f31be-122">此外，信息障碍独立于[合规性边界。](tagging-and-assessment-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="f31be-122">In addition, information barriers are independent from [compliance boundaries](tagging-and-assessment-in-advanced-ediscovery.md).</span></span><p><span data-ttu-id="f31be-123">在定义和应用信息障碍策略之前，请确保您的组织没有有效的[Exchange 通讯簿策略。](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies)</span><span class="sxs-lookup"><span data-stu-id="f31be-123">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="f31be-124">（信息障碍基于通讯簿策略。</span><span class="sxs-lookup"><span data-stu-id="f31be-124">(Information barriers are based on address book policies.)</span></span> 

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="f31be-125">信息障碍会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="f31be-125">What happens with information barriers</span></span>

<span data-ttu-id="f31be-126">当信息障碍策略到位时，不应与其他特定用户通信的用户将无法查找、选择、聊天或呼叫这些用户。</span><span class="sxs-lookup"><span data-stu-id="f31be-126">When information barrier policies are in place, people who should not communicate with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="f31be-127">在存在信息障碍时，会进行检查，以防止未经授权的通信。</span><span class="sxs-lookup"><span data-stu-id="f31be-127">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="f31be-128">最初，信息障碍仅适用于 Microsoft 团队聊天和渠道。</span><span class="sxs-lookup"><span data-stu-id="f31be-128">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="f31be-129">在 Microsoft 团队中，信息障碍策略确定并防止以下类型的未经授权的通信：</span><span class="sxs-lookup"><span data-stu-id="f31be-129">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>
- <span data-ttu-id="f31be-130">搜索用户</span><span class="sxs-lookup"><span data-stu-id="f31be-130">Searching for a user</span></span>
- <span data-ttu-id="f31be-131">将成员添加到团队</span><span class="sxs-lookup"><span data-stu-id="f31be-131">Adding a member to a team</span></span>
- <span data-ttu-id="f31be-132">与某人启动聊天会话</span><span class="sxs-lookup"><span data-stu-id="f31be-132">Starting a chat session with someone</span></span>
- <span data-ttu-id="f31be-133">开始群聊</span><span class="sxs-lookup"><span data-stu-id="f31be-133">Starting a group chat</span></span>
- <span data-ttu-id="f31be-134">邀请某人加入会议</span><span class="sxs-lookup"><span data-stu-id="f31be-134">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="f31be-135">共享屏幕</span><span class="sxs-lookup"><span data-stu-id="f31be-135">Sharing a screen</span></span>
- <span data-ttu-id="f31be-136">拨打电话</span><span class="sxs-lookup"><span data-stu-id="f31be-136">Placing a call</span></span> 

<span data-ttu-id="f31be-137">如果相关人员包含在信息屏障策略中以防止活动，则他们将无法继续。</span><span class="sxs-lookup"><span data-stu-id="f31be-137">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="f31be-138">此外，信息障碍策略中包含的每个人可能会被阻止与 Microsoft 团队中的其他人通信。</span><span class="sxs-lookup"><span data-stu-id="f31be-138">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="f31be-139">当受信息障碍策略影响的人员属于同一团队或群聊时，他们可能会从这些聊天会话中删除，并且可能不允许与群组进一步通信。</span><span class="sxs-lookup"><span data-stu-id="f31be-139">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="f31be-140">要了解有关具有信息障碍的用户体验的详细信息，请参阅[Microsoft 团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="f31be-140">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="f31be-141">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="f31be-141">Required licenses and permissions</span></span>

<span data-ttu-id="f31be-142">信息障碍正在推出，并包含在订阅中，例如：</span><span class="sxs-lookup"><span data-stu-id="f31be-142">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="f31be-143">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f31be-143">Microsoft 365 E5</span></span>
- <span data-ttu-id="f31be-144">办公室 365 E5</span><span class="sxs-lookup"><span data-stu-id="f31be-144">Office 365 E5</span></span>
- <span data-ttu-id="f31be-145">Office 365 進階合規性</span><span class="sxs-lookup"><span data-stu-id="f31be-145">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="f31be-146">微软 365 E5 信息保护和合规性</span><span class="sxs-lookup"><span data-stu-id="f31be-146">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="f31be-147">有关详细信息，请参阅[合规性解决方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。</span><span class="sxs-lookup"><span data-stu-id="f31be-147">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="f31be-148">要[定义或编辑信息障碍策略，](information-barriers-policies.md)必须为您分配以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="f31be-148">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="f31be-149">微软 365 全球管理员</span><span class="sxs-lookup"><span data-stu-id="f31be-149">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="f31be-150">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="f31be-150">Office 365 global administrator</span></span>
- <span data-ttu-id="f31be-151">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="f31be-151">Compliance administrator</span></span>
- <span data-ttu-id="f31be-152">IB 合规管理（这是一个新角色！</span><span class="sxs-lookup"><span data-stu-id="f31be-152">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="f31be-153">（要了解有关角色和权限的列表，请参阅[Office 365 安全&合规性中心的权限。](../security/office-365-security/protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="f31be-153">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)</span></span>

<span data-ttu-id="f31be-154">您必须熟悉 PowerShell cmdlet，才能定义、验证或编辑信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="f31be-154">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="f31be-155">尽管我们[在"工作方式"一文](information-barriers-policies.md)中提供了几个 PowerShell cmdlet 示例，但您需要了解组织的其他详细信息（如参数）。</span><span class="sxs-lookup"><span data-stu-id="f31be-155">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f31be-156">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f31be-156">Next steps</span></span>

- [<span data-ttu-id="f31be-157">了解有关 Microsoft 团队中信息障碍的详细信息</span><span class="sxs-lookup"><span data-stu-id="f31be-157">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [<span data-ttu-id="f31be-158">查看可用于信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="f31be-158">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)

- [<span data-ttu-id="f31be-159">定义信息障碍的策略</span><span class="sxs-lookup"><span data-stu-id="f31be-159">Define policies for information barriers</span></span>](information-barriers-policies.md)

- [<span data-ttu-id="f31be-160">编辑（或删除）信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="f31be-160">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md.md) 

