---
title: 資訊屏障原則的屬性
f1.keywords:
- NOCSH
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
description: 這是您用來定義資訊障礙區段之 Azure Active Directory 使用者帳戶屬性的參考文章。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6b6fb9cbbe5840888114ba99a604d16117ec795d
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307992"
---
# <a name="attributes-for-information-barrier-policies"></a><span data-ttu-id="70856-103">資訊屏障原則的屬性</span><span class="sxs-lookup"><span data-stu-id="70856-103">Attributes for information barrier policies</span></span>

<span data-ttu-id="70856-104">Azure Active Directory 中的某些屬性可用於分割使用者。</span><span class="sxs-lookup"><span data-stu-id="70856-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="70856-105">在定義區段之後，就可以使用這些區段做為資訊屏障原則的篩選器。</span><span class="sxs-lookup"><span data-stu-id="70856-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="70856-106">例如，您可以使用 **部門** 在組織內依部門定義使用者的區段 (假設沒有任何人同時在兩個部門上運作) 。</span><span class="sxs-lookup"><span data-stu-id="70856-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span> 

<span data-ttu-id="70856-107">本文說明如何使用具有資訊障礙的屬性，並提供可使用的屬性清單。</span><span class="sxs-lookup"><span data-stu-id="70856-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="70856-108">若要深入瞭解資訊障礙，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="70856-108">To learn more about information barriers, see the following resources:</span></span>
- [<span data-ttu-id="70856-109">資訊屏障</span><span class="sxs-lookup"><span data-stu-id="70856-109">Information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="70856-110">在 Microsoft 小組中定義資訊障礙的原則</span><span class="sxs-lookup"><span data-stu-id="70856-110">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="70856-111">編輯 (或移除) 資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="70856-111">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="70856-112">如何使用資訊屏障原則中的屬性</span><span class="sxs-lookup"><span data-stu-id="70856-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="70856-113">本文所列的屬性可以用來定義或編輯使用者的區段。</span><span class="sxs-lookup"><span data-stu-id="70856-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="70856-114">在[資訊屏障原則](information-barriers-policies.md)中，已定義的區段做為參數 (稱為*UserGroupFilter*值) 。</span><span class="sxs-lookup"><span data-stu-id="70856-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="70856-115">決定要用來定義線段的屬性。</span><span class="sxs-lookup"><span data-stu-id="70856-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="70856-116"> (請參閱本文中的 [參考](#reference) 一節。 ) </span><span class="sxs-lookup"><span data-stu-id="70856-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="70856-117">請確定使用者帳戶已填入值，以供您在步驟1中選取的屬性 (s) 。</span><span class="sxs-lookup"><span data-stu-id="70856-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="70856-118">查看使用者帳戶詳細資料，必要時，編輯使用者帳戶以包含屬性值。</span><span class="sxs-lookup"><span data-stu-id="70856-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    - <span data-ttu-id="70856-119">若要編輯多個帳戶 (或使用 PowerShell 編輯單一帳戶) ，請參閱 [Configure user account properties With Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="70856-119">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell).</span></span>

    - <span data-ttu-id="70856-120">若要編輯單一帳戶，請參閱 [使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="70856-120">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="70856-121">[使用 PowerShell 定義線段](information-barriers-policies.md#define-segments-using-powershell)，類似下列範例：</span><span class="sxs-lookup"><span data-stu-id="70856-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="70856-122">範例</span><span class="sxs-lookup"><span data-stu-id="70856-122">Example</span></span>  |<span data-ttu-id="70856-123">指令程式</span><span class="sxs-lookup"><span data-stu-id="70856-123">Cmdlet</span></span>  |
    |---------|---------|
    |<span data-ttu-id="70856-124">使用部門屬性定義名為 Segment1 的區段</span><span class="sxs-lookup"><span data-stu-id="70856-124">Define a segment called Segment1 using the Department attribute</span></span>     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |<span data-ttu-id="70856-125">使用 MemberOf 屬性定義名為 SegmentA 的區段 (假設此屬性包含群組名稱，例如 "BlueGroup" ) </span><span class="sxs-lookup"><span data-stu-id="70856-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span>     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |<span data-ttu-id="70856-126">使用 ExtensionAttribute1 定義名為 DayTraders 的區段 (假設此屬性包含職稱，例如 "DayTrader" ) </span><span class="sxs-lookup"><span data-stu-id="70856-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span>|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="70856-127">當您定義區段時，請針對所有的區段使用相同的屬性。</span><span class="sxs-lookup"><span data-stu-id="70856-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="70856-128">例如，如果您使用 *部門*定義部分區段，請使用 *部門*定義所有的區段。</span><span class="sxs-lookup"><span data-stu-id="70856-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="70856-129">不要使用*MemberOf*來定義某些區段使用*部門*和其他。</span><span class="sxs-lookup"><span data-stu-id="70856-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="70856-130">請確定您的區段沒有交疊;每一位使用者都應該被指派為一個段落。</span><span class="sxs-lookup"><span data-stu-id="70856-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span> 

## <a name="reference"></a><span data-ttu-id="70856-131">參考</span><span class="sxs-lookup"><span data-stu-id="70856-131">Reference</span></span>

<span data-ttu-id="70856-132">下表列出您可以與資訊障礙搭配使用的屬性。</span><span class="sxs-lookup"><span data-stu-id="70856-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="70856-133">Azure Active Directory 屬性名稱</span><span class="sxs-lookup"><span data-stu-id="70856-133">Azure Active Directory property name</span></span><br/><span data-ttu-id="70856-134"> (LDAP 顯示名稱) </span><span class="sxs-lookup"><span data-stu-id="70856-134">(LDAP display name)</span></span>  |<span data-ttu-id="70856-135">Exchange 屬性名稱</span><span class="sxs-lookup"><span data-stu-id="70856-135">Exchange property name</span></span>  |
|---------|---------|
|<span data-ttu-id="70856-136">顯</span><span class="sxs-lookup"><span data-stu-id="70856-136">Co</span></span>       | <span data-ttu-id="70856-137">顯</span><span class="sxs-lookup"><span data-stu-id="70856-137">Co</span></span>        |
|<span data-ttu-id="70856-138">Company</span><span class="sxs-lookup"><span data-stu-id="70856-138">Company</span></span>     |<span data-ttu-id="70856-139">Company</span><span class="sxs-lookup"><span data-stu-id="70856-139">Company</span></span>         |
|<span data-ttu-id="70856-140">部門</span><span class="sxs-lookup"><span data-stu-id="70856-140">Department</span></span>     |<span data-ttu-id="70856-141">部門</span><span class="sxs-lookup"><span data-stu-id="70856-141">Department</span></span>         |
|<span data-ttu-id="70856-142">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="70856-142">ExtensionAttribute1</span></span> |<span data-ttu-id="70856-143">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="70856-143">CustomAttribute1</span></span>  |
|<span data-ttu-id="70856-144">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="70856-144">ExtensionAttribute2</span></span> |<span data-ttu-id="70856-145">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="70856-145">CustomAttribute2</span></span>  |
|<span data-ttu-id="70856-146">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="70856-146">ExtensionAttribute3</span></span> |<span data-ttu-id="70856-147">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="70856-147">CustomAttribute3</span></span>  |
|<span data-ttu-id="70856-148">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="70856-148">ExtensionAttribute4</span></span> |<span data-ttu-id="70856-149">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="70856-149">CustomAttribute4</span></span>  |
|<span data-ttu-id="70856-150">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="70856-150">ExtensionAttribute5</span></span> |<span data-ttu-id="70856-151">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="70856-151">CustomAttribute5</span></span>  |
|<span data-ttu-id="70856-152">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="70856-152">ExtensionAttribute6</span></span> |<span data-ttu-id="70856-153">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="70856-153">CustomAttribute6</span></span>  |
|<span data-ttu-id="70856-154">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="70856-154">ExtensionAttribute7</span></span> |<span data-ttu-id="70856-155">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="70856-155">CustomAttribute7</span></span>  |
|<span data-ttu-id="70856-156">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="70856-156">ExtensionAttribute8</span></span> |<span data-ttu-id="70856-157">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="70856-157">CustomAttribute8</span></span>  |
|<span data-ttu-id="70856-158">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="70856-158">ExtensionAttribute9</span></span> |<span data-ttu-id="70856-159">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="70856-159">CustomAttribute9</span></span>  |
|<span data-ttu-id="70856-160">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="70856-160">ExtensionAttribute10</span></span> |<span data-ttu-id="70856-161">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="70856-161">CustomAttribute10</span></span>  |
|<span data-ttu-id="70856-162">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="70856-162">ExtensionAttribute11</span></span> |<span data-ttu-id="70856-163">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="70856-163">CustomAttribute11</span></span>  |
|<span data-ttu-id="70856-164">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="70856-164">ExtensionAttribute12</span></span> |<span data-ttu-id="70856-165">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="70856-165">CustomAttribute12</span></span>  |
|<span data-ttu-id="70856-166">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="70856-166">ExtensionAttribute13</span></span> |<span data-ttu-id="70856-167">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="70856-167">CustomAttribute13</span></span>  |
|<span data-ttu-id="70856-168">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="70856-168">ExtensionAttribute14</span></span> |<span data-ttu-id="70856-169">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="70856-169">CustomAttribute14</span></span>  |
|<span data-ttu-id="70856-170">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="70856-170">ExtensionAttribute15</span></span> |<span data-ttu-id="70856-171">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="70856-171">CustomAttribute15</span></span>  |
|<span data-ttu-id="70856-172">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="70856-172">MSExchExtensionCustomAttribute1</span></span> |<span data-ttu-id="70856-173">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="70856-173">ExtensionCustomAttribute1</span></span> |
|<span data-ttu-id="70856-174">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="70856-174">MSExchExtensionCustomAttribute2</span></span> |<span data-ttu-id="70856-175">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="70856-175">ExtensionCustomAttribute2</span></span> |
|<span data-ttu-id="70856-176">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="70856-176">MSExchExtensionCustomAttribute3</span></span> |<span data-ttu-id="70856-177">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="70856-177">ExtensionCustomAttribute3</span></span> |
|<span data-ttu-id="70856-178">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="70856-178">MSExchExtensionCustomAttribute4</span></span> |<span data-ttu-id="70856-179">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="70856-179">ExtensionCustomAttribute4</span></span> |
|<span data-ttu-id="70856-180">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="70856-180">MSExchExtensionCustomAttribute5</span></span> |<span data-ttu-id="70856-181">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="70856-181">ExtensionCustomAttribute5</span></span> |
|<span data-ttu-id="70856-182">MailNickname</span><span class="sxs-lookup"><span data-stu-id="70856-182">MailNickname</span></span> |<span data-ttu-id="70856-183">別名</span><span class="sxs-lookup"><span data-stu-id="70856-183">Alias</span></span> |
|<span data-ttu-id="70856-184">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="70856-184">PhysicalDeliveryOfficeName</span></span> |<span data-ttu-id="70856-185">辦公室</span><span class="sxs-lookup"><span data-stu-id="70856-185">Office</span></span> |
|<span data-ttu-id="70856-186">PostalCode</span><span class="sxs-lookup"><span data-stu-id="70856-186">PostalCode</span></span> |<span data-ttu-id="70856-187">PostalCode</span><span class="sxs-lookup"><span data-stu-id="70856-187">PostalCode</span></span> |
|<span data-ttu-id="70856-188">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="70856-188">ProxyAddresses</span></span> |<span data-ttu-id="70856-189">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="70856-189">EmailAddresses</span></span> |
|<span data-ttu-id="70856-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="70856-190">StreetAddress</span></span> |<span data-ttu-id="70856-191">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="70856-191">StreetAddress</span></span> |
|<span data-ttu-id="70856-192">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="70856-192">TargetAddress</span></span> |<span data-ttu-id="70856-193">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="70856-193">ExternalEmailAddress</span></span> |
|<span data-ttu-id="70856-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="70856-194">UsageLocation</span></span> |<span data-ttu-id="70856-195">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="70856-195">UsageLocation</span></span> |
|<span data-ttu-id="70856-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="70856-196">UserPrincipalName</span></span>    |<span data-ttu-id="70856-197">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="70856-197">UserPrincipalName</span></span>    |
|<span data-ttu-id="70856-198">郵件</span><span class="sxs-lookup"><span data-stu-id="70856-198">Mail</span></span>    |<span data-ttu-id="70856-199">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="70856-199">WindowsEmailAddress</span></span>    |
|<span data-ttu-id="70856-200">描述</span><span class="sxs-lookup"><span data-stu-id="70856-200">Description</span></span>    |<span data-ttu-id="70856-201">描述</span><span class="sxs-lookup"><span data-stu-id="70856-201">Description</span></span>    |
|<span data-ttu-id="70856-202">MemberOf</span><span class="sxs-lookup"><span data-stu-id="70856-202">MemberOf</span></span>    |<span data-ttu-id="70856-203">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="70856-203">MemberOfGroup</span></span>    |

## <a name="related-topics"></a><span data-ttu-id="70856-204">相關主題</span><span class="sxs-lookup"><span data-stu-id="70856-204">Related topics</span></span>

[<span data-ttu-id="70856-205">在 Microsoft 小組中定義資訊障礙的原則</span><span class="sxs-lookup"><span data-stu-id="70856-205">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)

[<span data-ttu-id="70856-206">疑難排解資訊屏障</span><span class="sxs-lookup"><span data-stu-id="70856-206">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)

[<span data-ttu-id="70856-207">資訊屏障</span><span class="sxs-lookup"><span data-stu-id="70856-207">Information barriers</span></span>](information-barriers.md)



