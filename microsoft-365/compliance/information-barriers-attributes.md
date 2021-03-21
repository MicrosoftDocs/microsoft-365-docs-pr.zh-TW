---
title: 資訊屏障原則的屬性
description: 本文是 Azure Active Directory 使用者帳戶屬性的參考，您可以用來定義資訊屏障段。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee410bf455e770087da7999ad2019c17419a8e00
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919729"
---
# <a name="attributes-for-information-barrier-policies"></a><span data-ttu-id="b797f-103">資訊屏障原則的屬性</span><span class="sxs-lookup"><span data-stu-id="b797f-103">Attributes for information barrier policies</span></span>

<span data-ttu-id="b797f-104">Azure Active Directory 中的某些屬性可用於分割使用者。</span><span class="sxs-lookup"><span data-stu-id="b797f-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="b797f-105">在定義區段之後，就可以使用這些區段做為資訊屏障原則的篩選器。</span><span class="sxs-lookup"><span data-stu-id="b797f-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="b797f-106">例如，您可以使用 **部門** 在組織內依部門定義使用者的區段 (假設沒有任何人同時在兩個部門上運作) 。</span><span class="sxs-lookup"><span data-stu-id="b797f-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span>

<span data-ttu-id="b797f-107">本文說明如何使用具有資訊障礙的屬性，並提供可使用的屬性清單。</span><span class="sxs-lookup"><span data-stu-id="b797f-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="b797f-108">若要深入瞭解資訊障礙，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="b797f-108">To learn more about information barriers, see the following resources:</span></span>

- [<span data-ttu-id="b797f-109">資訊屏障</span><span class="sxs-lookup"><span data-stu-id="b797f-109">Information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="b797f-110">在 Microsoft 小組中定義資訊障礙的原則</span><span class="sxs-lookup"><span data-stu-id="b797f-110">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="b797f-111">編輯 (或移除) 資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="b797f-111">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="b797f-112">如何使用資訊屏障原則中的屬性</span><span class="sxs-lookup"><span data-stu-id="b797f-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="b797f-113">本文所列的屬性可以用來定義或編輯使用者的區段。</span><span class="sxs-lookup"><span data-stu-id="b797f-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="b797f-114">在 [資訊屏障原則](information-barriers-policies.md)中，已定義的區段做為參數 (稱為 *UserGroupFilter* 值) 。</span><span class="sxs-lookup"><span data-stu-id="b797f-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="b797f-115">決定要用來定義線段的屬性。</span><span class="sxs-lookup"><span data-stu-id="b797f-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="b797f-116"> (請參閱本文中的 [參考](#reference) 一節。 ) </span><span class="sxs-lookup"><span data-stu-id="b797f-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="b797f-117">請確定使用者帳戶已填入值，以供您在步驟1中選取的屬性 (s) 。</span><span class="sxs-lookup"><span data-stu-id="b797f-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="b797f-118">查看使用者帳戶詳細資料，必要時，編輯使用者帳戶以包含屬性值。</span><span class="sxs-lookup"><span data-stu-id="b797f-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    - <span data-ttu-id="b797f-119">若要編輯多個帳戶 (或使用 PowerShell 編輯單一帳戶) ，請參閱 [Configure user account properties With Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="b797f-119">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).</span></span>

    - <span data-ttu-id="b797f-120">若要編輯單一帳戶，請參閱 [使用 Azure Active Directory 新增或更新使用者的設定檔資訊](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="b797f-120">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="b797f-121">[使用 PowerShell 定義線段](information-barriers-policies.md#define-segments-using-powershell)，類似下列範例：</span><span class="sxs-lookup"><span data-stu-id="b797f-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="b797f-122">**範例**</span><span class="sxs-lookup"><span data-stu-id="b797f-122">**Example**</span></span>|<span data-ttu-id="b797f-123">**指令程式**</span><span class="sxs-lookup"><span data-stu-id="b797f-123">**Cmdlet**</span></span>|
    |:----------|:---------|
    | <span data-ttu-id="b797f-124">使用部門屬性定義名為 Segment1 的區段</span><span class="sxs-lookup"><span data-stu-id="b797f-124">Define a segment called Segment1 using the Department attribute</span></span> | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | <span data-ttu-id="b797f-125">使用 MemberOf 屬性定義名為 SegmentA 的區段 (假設此屬性包含群組名稱，例如 "BlueGroup" ) </span><span class="sxs-lookup"><span data-stu-id="b797f-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span> | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | <span data-ttu-id="b797f-126">使用 ExtensionAttribute1 定義名為 DayTraders 的區段 (假設此屬性包含職稱，例如 "DayTrader" ) </span><span class="sxs-lookup"><span data-stu-id="b797f-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span> | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="b797f-127">當您定義區段時，請針對所有的區段使用相同的屬性。</span><span class="sxs-lookup"><span data-stu-id="b797f-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="b797f-128">例如，如果您使用 *部門* 定義部分區段，請使用 *部門* 定義所有的區段。</span><span class="sxs-lookup"><span data-stu-id="b797f-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="b797f-129">不要使用 *MemberOf* 來定義某些區段使用 *部門* 和其他。</span><span class="sxs-lookup"><span data-stu-id="b797f-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="b797f-130">請確定您的區段沒有交疊;每一位使用者都應該被指派為一個段落。</span><span class="sxs-lookup"><span data-stu-id="b797f-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span>

## <a name="reference"></a><span data-ttu-id="b797f-131">參考</span><span class="sxs-lookup"><span data-stu-id="b797f-131">Reference</span></span>

<span data-ttu-id="b797f-132">下表列出您可以與資訊障礙搭配使用的屬性。</span><span class="sxs-lookup"><span data-stu-id="b797f-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="b797f-133">**Azure Active Directory 屬性名稱 <br/> (LDAP 顯示名稱)**</span><span class="sxs-lookup"><span data-stu-id="b797f-133">**Azure Active Directory property name<br/>(LDAP display name)**</span></span>|<span data-ttu-id="b797f-134">**Exchange 屬性名稱**</span><span class="sxs-lookup"><span data-stu-id="b797f-134">**Exchange property name**</span></span>|
|:---------------------------------------------------------------|:-------------------------|
| <span data-ttu-id="b797f-135">顯</span><span class="sxs-lookup"><span data-stu-id="b797f-135">Co</span></span> | <span data-ttu-id="b797f-136">顯</span><span class="sxs-lookup"><span data-stu-id="b797f-136">Co</span></span> |
| <span data-ttu-id="b797f-137">Company</span><span class="sxs-lookup"><span data-stu-id="b797f-137">Company</span></span> | <span data-ttu-id="b797f-138">Company</span><span class="sxs-lookup"><span data-stu-id="b797f-138">Company</span></span> |
| <span data-ttu-id="b797f-139">部門</span><span class="sxs-lookup"><span data-stu-id="b797f-139">Department</span></span> | <span data-ttu-id="b797f-140">部門</span><span class="sxs-lookup"><span data-stu-id="b797f-140">Department</span></span> |
| <span data-ttu-id="b797f-141">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="b797f-141">ExtensionAttribute1</span></span> | <span data-ttu-id="b797f-142">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="b797f-142">CustomAttribute1</span></span> |
| <span data-ttu-id="b797f-143">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="b797f-143">ExtensionAttribute2</span></span> | <span data-ttu-id="b797f-144">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="b797f-144">CustomAttribute2</span></span> |
| <span data-ttu-id="b797f-145">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="b797f-145">ExtensionAttribute3</span></span> | <span data-ttu-id="b797f-146">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="b797f-146">CustomAttribute3</span></span> |
| <span data-ttu-id="b797f-147">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="b797f-147">ExtensionAttribute4</span></span> | <span data-ttu-id="b797f-148">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="b797f-148">CustomAttribute4</span></span> |
| <span data-ttu-id="b797f-149">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="b797f-149">ExtensionAttribute5</span></span> | <span data-ttu-id="b797f-150">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="b797f-150">CustomAttribute5</span></span> |
| <span data-ttu-id="b797f-151">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="b797f-151">ExtensionAttribute6</span></span> | <span data-ttu-id="b797f-152">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="b797f-152">CustomAttribute6</span></span> |
| <span data-ttu-id="b797f-153">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="b797f-153">ExtensionAttribute7</span></span> | <span data-ttu-id="b797f-154">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="b797f-154">CustomAttribute7</span></span> |
| <span data-ttu-id="b797f-155">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="b797f-155">ExtensionAttribute8</span></span> | <span data-ttu-id="b797f-156">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="b797f-156">CustomAttribute8</span></span> |
| <span data-ttu-id="b797f-157">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="b797f-157">ExtensionAttribute9</span></span> | <span data-ttu-id="b797f-158">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="b797f-158">CustomAttribute9</span></span> |
| <span data-ttu-id="b797f-159">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="b797f-159">ExtensionAttribute10</span></span> | <span data-ttu-id="b797f-160">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="b797f-160">CustomAttribute10</span></span> |
| <span data-ttu-id="b797f-161">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="b797f-161">ExtensionAttribute11</span></span> | <span data-ttu-id="b797f-162">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="b797f-162">CustomAttribute11</span></span> |
| <span data-ttu-id="b797f-163">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="b797f-163">ExtensionAttribute12</span></span> | <span data-ttu-id="b797f-164">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="b797f-164">CustomAttribute12</span></span> |
| <span data-ttu-id="b797f-165">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="b797f-165">ExtensionAttribute13</span></span> | <span data-ttu-id="b797f-166">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="b797f-166">CustomAttribute13</span></span> |
| <span data-ttu-id="b797f-167">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="b797f-167">ExtensionAttribute14</span></span> | <span data-ttu-id="b797f-168">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="b797f-168">CustomAttribute14</span></span> |
| <span data-ttu-id="b797f-169">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="b797f-169">ExtensionAttribute15</span></span> | <span data-ttu-id="b797f-170">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="b797f-170">CustomAttribute15</span></span> |
| <span data-ttu-id="b797f-171">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="b797f-171">MSExchExtensionCustomAttribute1</span></span> | <span data-ttu-id="b797f-172">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="b797f-172">ExtensionCustomAttribute1</span></span> |
| <span data-ttu-id="b797f-173">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="b797f-173">MSExchExtensionCustomAttribute2</span></span> | <span data-ttu-id="b797f-174">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="b797f-174">ExtensionCustomAttribute2</span></span> |
| <span data-ttu-id="b797f-175">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="b797f-175">MSExchExtensionCustomAttribute3</span></span> | <span data-ttu-id="b797f-176">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="b797f-176">ExtensionCustomAttribute3</span></span> |
| <span data-ttu-id="b797f-177">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="b797f-177">MSExchExtensionCustomAttribute4</span></span> | <span data-ttu-id="b797f-178">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="b797f-178">ExtensionCustomAttribute4</span></span> |
| <span data-ttu-id="b797f-179">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="b797f-179">MSExchExtensionCustomAttribute5</span></span> | <span data-ttu-id="b797f-180">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="b797f-180">ExtensionCustomAttribute5</span></span> |
| <span data-ttu-id="b797f-181">MailNickname</span><span class="sxs-lookup"><span data-stu-id="b797f-181">MailNickname</span></span> | <span data-ttu-id="b797f-182">別名</span><span class="sxs-lookup"><span data-stu-id="b797f-182">Alias</span></span> |
| <span data-ttu-id="b797f-183">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="b797f-183">PhysicalDeliveryOfficeName</span></span> | <span data-ttu-id="b797f-184">辦公室</span><span class="sxs-lookup"><span data-stu-id="b797f-184">Office</span></span> |
| <span data-ttu-id="b797f-185">PostalCode</span><span class="sxs-lookup"><span data-stu-id="b797f-185">PostalCode</span></span> | <span data-ttu-id="b797f-186">PostalCode</span><span class="sxs-lookup"><span data-stu-id="b797f-186">PostalCode</span></span> |
| <span data-ttu-id="b797f-187">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b797f-187">ProxyAddresses</span></span> | <span data-ttu-id="b797f-188">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="b797f-188">EmailAddresses</span></span> |
| <span data-ttu-id="b797f-189">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="b797f-189">StreetAddress</span></span> | <span data-ttu-id="b797f-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="b797f-190">StreetAddress</span></span> |
| <span data-ttu-id="b797f-191">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="b797f-191">TargetAddress</span></span> | <span data-ttu-id="b797f-192">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="b797f-192">ExternalEmailAddress</span></span> |
| <span data-ttu-id="b797f-193">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="b797f-193">UsageLocation</span></span> | <span data-ttu-id="b797f-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="b797f-194">UsageLocation</span></span> |
| <span data-ttu-id="b797f-195">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="b797f-195">UserPrincipalName</span></span> | <span data-ttu-id="b797f-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="b797f-196">UserPrincipalName</span></span> |
| <span data-ttu-id="b797f-197">郵件</span><span class="sxs-lookup"><span data-stu-id="b797f-197">Mail</span></span> | <span data-ttu-id="b797f-198">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="b797f-198">WindowsEmailAddress</span></span> |
| <span data-ttu-id="b797f-199">描述</span><span class="sxs-lookup"><span data-stu-id="b797f-199">Description</span></span> | <span data-ttu-id="b797f-200">描述</span><span class="sxs-lookup"><span data-stu-id="b797f-200">Description</span></span> |
| <span data-ttu-id="b797f-201">MemberOf</span><span class="sxs-lookup"><span data-stu-id="b797f-201">MemberOf</span></span> | <span data-ttu-id="b797f-202">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="b797f-202">MemberOfGroup</span></span> |

## <a name="resources"></a><span data-ttu-id="b797f-203">資源</span><span class="sxs-lookup"><span data-stu-id="b797f-203">Resources</span></span>

- [<span data-ttu-id="b797f-204">在 Microsoft 小組中定義資訊障礙的原則</span><span class="sxs-lookup"><span data-stu-id="b797f-204">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="b797f-205">疑難排解資訊屏障</span><span class="sxs-lookup"><span data-stu-id="b797f-205">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)
- [<span data-ttu-id="b797f-206">資訊屏障</span><span class="sxs-lookup"><span data-stu-id="b797f-206">Information barriers</span></span>](information-barriers.md)