---
title: 信息屏障策略的属性
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
description: 使用本文作为可用于信息屏障策略的各种属性的参考。
ms.openlocfilehash: 4198728d412062edced6238604b2b891da22aeac
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077135"
---
# <a name="attributes-for-information-barrier-policies"></a><span data-ttu-id="8eb04-103">信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="8eb04-103">Attributes for information barrier policies</span></span>

<span data-ttu-id="8eb04-104">Azure 活动目录中的某些属性可用于对用户进行分段。</span><span class="sxs-lookup"><span data-stu-id="8eb04-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="8eb04-105">定义段后，这些段可用作信息屏障策略的筛选器。</span><span class="sxs-lookup"><span data-stu-id="8eb04-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="8eb04-106">例如，**您可以使用"部门"** 按组织内部门定义用户细分（假设没有一名员工同时为两个部门工作）。</span><span class="sxs-lookup"><span data-stu-id="8eb04-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span> 

<span data-ttu-id="8eb04-107">本文介绍如何使用具有信息障碍的属性，并提供可以使用的属性列表。</span><span class="sxs-lookup"><span data-stu-id="8eb04-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="8eb04-108">要了解有关信息障碍的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="8eb04-108">To learn more about information barriers, see the following resources:</span></span>
- [<span data-ttu-id="8eb04-109">信息障碍</span><span class="sxs-lookup"><span data-stu-id="8eb04-109">Information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="8eb04-110">定义 Microsoft 团队中信息障碍的策略</span><span class="sxs-lookup"><span data-stu-id="8eb04-110">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="8eb04-111">编辑（或删除）信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="8eb04-111">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="8eb04-112">如何在信息屏障策略中使用属性</span><span class="sxs-lookup"><span data-stu-id="8eb04-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="8eb04-113">本文中列出的属性可用于定义或编辑用户段。</span><span class="sxs-lookup"><span data-stu-id="8eb04-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="8eb04-114">在[信息屏障策略](information-barriers-policies.md)中，定义的段用作参数（称为*UserGroupFilter*值）。</span><span class="sxs-lookup"><span data-stu-id="8eb04-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="8eb04-115">确定要用于定义段的属性。</span><span class="sxs-lookup"><span data-stu-id="8eb04-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="8eb04-116">（请参阅本文中的[参考](#reference)部分。</span><span class="sxs-lookup"><span data-stu-id="8eb04-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="8eb04-117">确保用户帐户已为您在步骤 1 中选择的属性填充了值。</span><span class="sxs-lookup"><span data-stu-id="8eb04-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="8eb04-118">查看用户帐户详细信息，如有必要，编辑用户帐户以包括属性值。</span><span class="sxs-lookup"><span data-stu-id="8eb04-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    - <span data-ttu-id="8eb04-119">要编辑多个帐户（或使用 PowerShell 编辑单个帐户），请参阅[使用 Office 365 PowerShell 配置用户帐户属性。](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="8eb04-119">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

    - <span data-ttu-id="8eb04-120">要编辑单个帐户，请参阅[使用 Azure 活动目录 添加或更新用户的配置文件信息。](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="8eb04-120">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="8eb04-121">[使用 PowerShell 定义段，](information-barriers-policies.md#define-segments-using-powershell)类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="8eb04-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="8eb04-122">範例</span><span class="sxs-lookup"><span data-stu-id="8eb04-122">Example</span></span>  |<span data-ttu-id="8eb04-123">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8eb04-123">Cmdlet</span></span>  |
    |---------|---------|
    |<span data-ttu-id="8eb04-124">使用"部门"属性定义称为"段 1"的段</span><span class="sxs-lookup"><span data-stu-id="8eb04-124">Define a segment called Segment1 using the Department attribute</span></span>     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |<span data-ttu-id="8eb04-125">使用成员Of属性定义称为段A的段（假设此属性包含组名称，如"BlueGroup"）</span><span class="sxs-lookup"><span data-stu-id="8eb04-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span>     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |<span data-ttu-id="8eb04-126">使用扩展属性1 定义名为 DayTrader 的段（假设此属性包含作业标题，如"DayTrader"）</span><span class="sxs-lookup"><span data-stu-id="8eb04-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span>|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="8eb04-127">定义线段时，对所有线段使用相同的属性。</span><span class="sxs-lookup"><span data-stu-id="8eb04-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="8eb04-128">例如，*如果使用"部门"* 定义某些细分，则*使用"部门"* 定义所有段。</span><span class="sxs-lookup"><span data-stu-id="8eb04-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="8eb04-129">不要*使用"部门"* 定义某些细分，*使用"成员"* 定义其他细分。</span><span class="sxs-lookup"><span data-stu-id="8eb04-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="8eb04-130">确保您的细分不重叠;每个用户应分配给一个段。</span><span class="sxs-lookup"><span data-stu-id="8eb04-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span> 

## <a name="reference"></a><span data-ttu-id="8eb04-131">參考</span><span class="sxs-lookup"><span data-stu-id="8eb04-131">Reference</span></span>

<span data-ttu-id="8eb04-132">下表列出了可用于信息障碍的属性。</span><span class="sxs-lookup"><span data-stu-id="8eb04-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="8eb04-133">Azure 活动目录属性名称</span><span class="sxs-lookup"><span data-stu-id="8eb04-133">Azure Active Directory property name</span></span><br/><span data-ttu-id="8eb04-134">（LDAP 显示名称）</span><span class="sxs-lookup"><span data-stu-id="8eb04-134">(LDAP display name)</span></span>  |<span data-ttu-id="8eb04-135">交换属性名称</span><span class="sxs-lookup"><span data-stu-id="8eb04-135">Exchange property name</span></span>  |
|---------|---------|
|<span data-ttu-id="8eb04-136">Co</span><span class="sxs-lookup"><span data-stu-id="8eb04-136">Co</span></span>       | <span data-ttu-id="8eb04-137">Co</span><span class="sxs-lookup"><span data-stu-id="8eb04-137">Co</span></span>        |
|<span data-ttu-id="8eb04-138">Company</span><span class="sxs-lookup"><span data-stu-id="8eb04-138">Company</span></span>     |<span data-ttu-id="8eb04-139">Company</span><span class="sxs-lookup"><span data-stu-id="8eb04-139">Company</span></span>         |
|<span data-ttu-id="8eb04-140">部門</span><span class="sxs-lookup"><span data-stu-id="8eb04-140">Department</span></span>     |<span data-ttu-id="8eb04-141">部門</span><span class="sxs-lookup"><span data-stu-id="8eb04-141">Department</span></span>         |
|<span data-ttu-id="8eb04-142">扩展属性1</span><span class="sxs-lookup"><span data-stu-id="8eb04-142">ExtensionAttribute1</span></span> |<span data-ttu-id="8eb04-143">自定义属性1</span><span class="sxs-lookup"><span data-stu-id="8eb04-143">CustomAttribute1</span></span>  |
|<span data-ttu-id="8eb04-144">扩展属性2</span><span class="sxs-lookup"><span data-stu-id="8eb04-144">ExtensionAttribute2</span></span> |<span data-ttu-id="8eb04-145">自定义属性2</span><span class="sxs-lookup"><span data-stu-id="8eb04-145">CustomAttribute2</span></span>  |
|<span data-ttu-id="8eb04-146">扩展属性3</span><span class="sxs-lookup"><span data-stu-id="8eb04-146">ExtensionAttribute3</span></span> |<span data-ttu-id="8eb04-147">自定义属性3</span><span class="sxs-lookup"><span data-stu-id="8eb04-147">CustomAttribute3</span></span>  |
|<span data-ttu-id="8eb04-148">扩展属性4</span><span class="sxs-lookup"><span data-stu-id="8eb04-148">ExtensionAttribute4</span></span> |<span data-ttu-id="8eb04-149">自定义属性4</span><span class="sxs-lookup"><span data-stu-id="8eb04-149">CustomAttribute4</span></span>  |
|<span data-ttu-id="8eb04-150">扩展属性5</span><span class="sxs-lookup"><span data-stu-id="8eb04-150">ExtensionAttribute5</span></span> |<span data-ttu-id="8eb04-151">自定义属性5</span><span class="sxs-lookup"><span data-stu-id="8eb04-151">CustomAttribute5</span></span>  |
|<span data-ttu-id="8eb04-152">扩展属性6</span><span class="sxs-lookup"><span data-stu-id="8eb04-152">ExtensionAttribute6</span></span> |<span data-ttu-id="8eb04-153">自定义属性6</span><span class="sxs-lookup"><span data-stu-id="8eb04-153">CustomAttribute6</span></span>  |
|<span data-ttu-id="8eb04-154">扩展属性7</span><span class="sxs-lookup"><span data-stu-id="8eb04-154">ExtensionAttribute7</span></span> |<span data-ttu-id="8eb04-155">自定义属性7</span><span class="sxs-lookup"><span data-stu-id="8eb04-155">CustomAttribute7</span></span>  |
|<span data-ttu-id="8eb04-156">扩展属性8</span><span class="sxs-lookup"><span data-stu-id="8eb04-156">ExtensionAttribute8</span></span> |<span data-ttu-id="8eb04-157">自定义属性8</span><span class="sxs-lookup"><span data-stu-id="8eb04-157">CustomAttribute8</span></span>  |
|<span data-ttu-id="8eb04-158">扩展属性9</span><span class="sxs-lookup"><span data-stu-id="8eb04-158">ExtensionAttribute9</span></span> |<span data-ttu-id="8eb04-159">自定义属性9</span><span class="sxs-lookup"><span data-stu-id="8eb04-159">CustomAttribute9</span></span>  |
|<span data-ttu-id="8eb04-160">扩展属性10</span><span class="sxs-lookup"><span data-stu-id="8eb04-160">ExtensionAttribute10</span></span> |<span data-ttu-id="8eb04-161">自定义属性10</span><span class="sxs-lookup"><span data-stu-id="8eb04-161">CustomAttribute10</span></span>  |
|<span data-ttu-id="8eb04-162">扩展属性11</span><span class="sxs-lookup"><span data-stu-id="8eb04-162">ExtensionAttribute11</span></span> |<span data-ttu-id="8eb04-163">自定义属性11</span><span class="sxs-lookup"><span data-stu-id="8eb04-163">CustomAttribute11</span></span>  |
|<span data-ttu-id="8eb04-164">扩展属性12</span><span class="sxs-lookup"><span data-stu-id="8eb04-164">ExtensionAttribute12</span></span> |<span data-ttu-id="8eb04-165">自定义属性12</span><span class="sxs-lookup"><span data-stu-id="8eb04-165">CustomAttribute12</span></span>  |
|<span data-ttu-id="8eb04-166">扩展属性13</span><span class="sxs-lookup"><span data-stu-id="8eb04-166">ExtensionAttribute13</span></span> |<span data-ttu-id="8eb04-167">自定义属性13</span><span class="sxs-lookup"><span data-stu-id="8eb04-167">CustomAttribute13</span></span>  |
|<span data-ttu-id="8eb04-168">扩展属性14</span><span class="sxs-lookup"><span data-stu-id="8eb04-168">ExtensionAttribute14</span></span> |<span data-ttu-id="8eb04-169">自定义属性14</span><span class="sxs-lookup"><span data-stu-id="8eb04-169">CustomAttribute14</span></span>  |
|<span data-ttu-id="8eb04-170">扩展属性15</span><span class="sxs-lookup"><span data-stu-id="8eb04-170">ExtensionAttribute15</span></span> |<span data-ttu-id="8eb04-171">自定义属性15</span><span class="sxs-lookup"><span data-stu-id="8eb04-171">CustomAttribute15</span></span>  |
|<span data-ttu-id="8eb04-172">MSExch扩展自定义属性1</span><span class="sxs-lookup"><span data-stu-id="8eb04-172">MSExchExtensionCustomAttribute1</span></span> |<span data-ttu-id="8eb04-173">扩展自定义属性1</span><span class="sxs-lookup"><span data-stu-id="8eb04-173">ExtensionCustomAttribute1</span></span> |
|<span data-ttu-id="8eb04-174">MSExch扩展自定义属性2</span><span class="sxs-lookup"><span data-stu-id="8eb04-174">MSExchExtensionCustomAttribute2</span></span> |<span data-ttu-id="8eb04-175">扩展自定义属性2</span><span class="sxs-lookup"><span data-stu-id="8eb04-175">ExtensionCustomAttribute2</span></span> |
|<span data-ttu-id="8eb04-176">MSExch扩展自定义属性3</span><span class="sxs-lookup"><span data-stu-id="8eb04-176">MSExchExtensionCustomAttribute3</span></span> |<span data-ttu-id="8eb04-177">扩展自定义属性3</span><span class="sxs-lookup"><span data-stu-id="8eb04-177">ExtensionCustomAttribute3</span></span> |
|<span data-ttu-id="8eb04-178">MSExch 扩展自定义属性4</span><span class="sxs-lookup"><span data-stu-id="8eb04-178">MSExchExtensionCustomAttribute4</span></span> |<span data-ttu-id="8eb04-179">扩展自定义属性4</span><span class="sxs-lookup"><span data-stu-id="8eb04-179">ExtensionCustomAttribute4</span></span> |
|<span data-ttu-id="8eb04-180">MSExch扩展自定义属性5</span><span class="sxs-lookup"><span data-stu-id="8eb04-180">MSExchExtensionCustomAttribute5</span></span> |<span data-ttu-id="8eb04-181">扩展自定义属性5</span><span class="sxs-lookup"><span data-stu-id="8eb04-181">ExtensionCustomAttribute5</span></span> |
|<span data-ttu-id="8eb04-182">邮件昵称</span><span class="sxs-lookup"><span data-stu-id="8eb04-182">MailNickname</span></span> |<span data-ttu-id="8eb04-183">別名</span><span class="sxs-lookup"><span data-stu-id="8eb04-183">Alias</span></span> |
|<span data-ttu-id="8eb04-184">物理交付办公室名称</span><span class="sxs-lookup"><span data-stu-id="8eb04-184">PhysicalDeliveryOfficeName</span></span> |<span data-ttu-id="8eb04-185">Office</span><span class="sxs-lookup"><span data-stu-id="8eb04-185">Office</span></span> |
|<span data-ttu-id="8eb04-186">PostalCode</span><span class="sxs-lookup"><span data-stu-id="8eb04-186">PostalCode</span></span> |<span data-ttu-id="8eb04-187">PostalCode</span><span class="sxs-lookup"><span data-stu-id="8eb04-187">PostalCode</span></span> |
|<span data-ttu-id="8eb04-188">代理地址</span><span class="sxs-lookup"><span data-stu-id="8eb04-188">ProxyAddresses</span></span> |<span data-ttu-id="8eb04-189">电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="8eb04-189">EmailAddresses</span></span> |
|<span data-ttu-id="8eb04-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="8eb04-190">StreetAddress</span></span> |<span data-ttu-id="8eb04-191">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="8eb04-191">StreetAddress</span></span> |
|<span data-ttu-id="8eb04-192">目标地址</span><span class="sxs-lookup"><span data-stu-id="8eb04-192">TargetAddress</span></span> |<span data-ttu-id="8eb04-193">外部电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="8eb04-193">ExternalEmailAddress</span></span> |
|<span data-ttu-id="8eb04-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="8eb04-194">UsageLocation</span></span> |<span data-ttu-id="8eb04-195">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="8eb04-195">UsageLocation</span></span> |
|<span data-ttu-id="8eb04-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="8eb04-196">UserPrincipalName</span></span>  |<span data-ttu-id="8eb04-197">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="8eb04-197">UserPrincipalName</span></span>  |
|<span data-ttu-id="8eb04-198">郵件</span><span class="sxs-lookup"><span data-stu-id="8eb04-198">Mail</span></span>   |<span data-ttu-id="8eb04-199">窗口电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="8eb04-199">WindowsEmailAddress</span></span>    |
|<span data-ttu-id="8eb04-200">描述</span><span class="sxs-lookup"><span data-stu-id="8eb04-200">Description</span></span>    |<span data-ttu-id="8eb04-201">描述</span><span class="sxs-lookup"><span data-stu-id="8eb04-201">Description</span></span>    |
|<span data-ttu-id="8eb04-202">成员</span><span class="sxs-lookup"><span data-stu-id="8eb04-202">MemberOf</span></span>   |<span data-ttu-id="8eb04-203">小组成员</span><span class="sxs-lookup"><span data-stu-id="8eb04-203">MemberOfGroup</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="8eb04-204">相關主題</span><span class="sxs-lookup"><span data-stu-id="8eb04-204">Related topics</span></span>

[<span data-ttu-id="8eb04-205">定义 Microsoft 团队中信息障碍的策略</span><span class="sxs-lookup"><span data-stu-id="8eb04-205">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)

[<span data-ttu-id="8eb04-206">排除信息障碍</span><span class="sxs-lookup"><span data-stu-id="8eb04-206">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)

[<span data-ttu-id="8eb04-207">信息障碍</span><span class="sxs-lookup"><span data-stu-id="8eb04-207">Information barriers</span></span>](information-barriers.md)



