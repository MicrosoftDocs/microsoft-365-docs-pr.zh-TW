---
title: 管理資訊障礙原則
description: 瞭解如何編輯或移除資訊障礙的原則。
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
ms.openlocfilehash: 668ca8e26371d80f068c2723357ce3ee407db03a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925549"
---
# <a name="manage-information-barrier-policies"></a><span data-ttu-id="bfe0f-103">管理資訊障礙原則</span><span class="sxs-lookup"><span data-stu-id="bfe0f-103">Manage information barrier policies</span></span>

<span data-ttu-id="bfe0f-104">[定義資訊障礙原則](information-barriers-policies.md)之後，您可能需要變更這些原則或使用者區段，以作為[疑難排解](information-barriers-troubleshooting.md)的一部分，或定期進行維護。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-104">After you have [defined information barrier policies](information-barriers-policies.md), you might need to make changes to those policies or to your user segments, as part of [troubleshooting](information-barriers-troubleshooting.md) or as regular maintenance.</span></span> <span data-ttu-id="bfe0f-105">使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-105">Use this article as a guide.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="bfe0f-106">您要執行的工作</span><span class="sxs-lookup"><span data-stu-id="bfe0f-106">What do you want to do?</span></span>

|<span data-ttu-id="bfe0f-107">**Action**</span><span class="sxs-lookup"><span data-stu-id="bfe0f-107">**Action**</span></span>|<span data-ttu-id="bfe0f-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="bfe0f-108">**Description**</span></span>|
|:---------|:--------------|
| [<span data-ttu-id="bfe0f-109">編輯使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="bfe0f-109">Edit user account attributes</span></span>](#edit-user-account-attributes) | <span data-ttu-id="bfe0f-110">在 Azure Active Directory 中填入可用於定義區段的屬性。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-110">Fill in attributes in Azure Active Directory that can be used to define segments.</span></span><br/><span data-ttu-id="bfe0f-111">當使用者未包含在其應包含的區隔時，請編輯使用者帳戶屬性、變更使用者所參與的區隔，或使用不同的屬性定義區隔。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-111">Edit user account attributes when users are not included in segments they should be, to change which segments users are in, or to define segments using different attributes.</span></span> |
| [<span data-ttu-id="bfe0f-112">編輯區隔</span><span class="sxs-lookup"><span data-stu-id="bfe0f-112">Edit a segment</span></span>](#edit-a-segment) | <span data-ttu-id="bfe0f-113">當您想要變更區隔的定義時，請編輯區隔。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-113">Edit segments when you want to change how a segment is defined.</span></span> <br/><span data-ttu-id="bfe0f-114">例如，您可能原本使用 *部門* 定義的區段，現在想要使用另一個屬性，例如 *MemberOf*。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-114">For example, you might have originally defined segments using *Department* and now want to use another attribute, such as *MemberOf*.</span></span> |
| [<span data-ttu-id="bfe0f-115">編輯原則</span><span class="sxs-lookup"><span data-stu-id="bfe0f-115">Edit a policy</span></span>](#edit-a-policy) | <span data-ttu-id="bfe0f-116">當您想要變更原則運作方式時，請編輯資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-116">Edit an information barrier policy when you want to change how a policy works.</span></span><br/><span data-ttu-id="bfe0f-117">例如，您可以決定只允許在特定的區段之間進行通訊，而不是封鎖兩個網段間的通訊。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-117">For example, instead of blocking communications between two segments, you might decide you want to allow communications to occur only between certain segments.</span></span> |
| [<span data-ttu-id="bfe0f-118">將原則設定為非使用中狀態</span><span class="sxs-lookup"><span data-stu-id="bfe0f-118">Set a policy to inactive status</span></span>](#set-a-policy-to-inactive-status) |<span data-ttu-id="bfe0f-119">當您想要變更原則或不想讓原則生效時，將原則設定為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-119">Set a policy to inactive status when you want to make changes to a policy, or when you don't want a policy to be in effect.</span></span> |
| [<span data-ttu-id="bfe0f-120">移除原則</span><span class="sxs-lookup"><span data-stu-id="bfe0f-120">Remove a policy</span></span>](#remove-a-policy) | <span data-ttu-id="bfe0f-121">當您不再需要特定的原則時，請移除資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-121">Remove an information barrier policy when you no longer need a particular policy in place.</span></span> |
| [<span data-ttu-id="bfe0f-122">停止原則應用程式</span><span class="sxs-lookup"><span data-stu-id="bfe0f-122">Stop a policy application</span></span>](#stop-a-policy-application) | <span data-ttu-id="bfe0f-123">當您想要停止套用資訊障礙原則的程式時，請採取此動作。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-123">Take this action when you want to stop the process of applying information barrier policies.</span></span><br/> <span data-ttu-id="bfe0f-124">停止原則應用程式不會立即運作，也不會復原已套用至使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-124">Stopping a policy application is not instant, and it does not undo policies that are already applied to users.</span></span> |
| [<span data-ttu-id="bfe0f-125">定義資訊屏障的原則</span><span class="sxs-lookup"><span data-stu-id="bfe0f-125">Define policies for information barriers</span></span>](information-barriers-policies.md) | <span data-ttu-id="bfe0f-126">定義資訊屏障原則時，當您不具備這類原則時，必須限制或限制特定使用者群組之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-126">Define an information barrier policy when you do not already have such policies in place, and you must restrict or limit communications between specific groups of users.</span></span> |
| [<span data-ttu-id="bfe0f-127">資訊屏障疑難排解</span><span class="sxs-lookup"><span data-stu-id="bfe0f-127">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md) | <span data-ttu-id="bfe0f-128">當您遇到資訊障礙的意外問題時，請參閱本文。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-128">Refer to this article when you run into unexpected issues with information barriers.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="bfe0f-129">若要執行本文所述的工作，您必須獲指派適當的角色，例如下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bfe0f-129">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="bfe0f-130">-Microsoft 365 企業版全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="bfe0f-130">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="bfe0f-131">-全域管理員</span><span class="sxs-lookup"><span data-stu-id="bfe0f-131">- Global Administrator</span></span><br/><span data-ttu-id="bfe0f-132">-合規性管理員</span><span class="sxs-lookup"><span data-stu-id="bfe0f-132">- Compliance Administrator</span></span><br/><span data-ttu-id="bfe0f-133">-IB 相容性管理 (這是一個新的角色！ ) </span><span class="sxs-lookup"><span data-stu-id="bfe0f-133">- IB Compliance Management (this is a new role!)</span></span><br><br><span data-ttu-id="bfe0f-134">若要深入瞭解資訊障礙的必要條件，請參閱 [資訊屏障原則) 的必要條件 (](information-barriers-policies.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-134">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><br><br> <span data-ttu-id="bfe0f-135">請務必 [連接至安全性 & 規範中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-135">Make sure to [connect to the Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="edit-user-account-attributes"></a><span data-ttu-id="bfe0f-136">編輯使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="bfe0f-136">Edit user account attributes</span></span>

<span data-ttu-id="bfe0f-137">使用此程式可編輯用於分割使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-137">Use this procedure to edit attributes that are used for segmenting users.</span></span> <span data-ttu-id="bfe0f-138">例如，如果您使用的是部門屬性，且有一或多個使用者帳戶目前未列出部門的任何值，您必須編輯這些使用者帳戶，以包含部門資訊。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-138">For example, if you are using a Department attribute, and one or more user accounts do not currently have any values listed for Department, you must edit those user accounts to include Department information.</span></span> <span data-ttu-id="bfe0f-139">使用者帳戶屬性可用來定義區段，這樣就可以指派資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-139">User account attributes are used for defining segments so that information barrier policies can be assigned.</span></span>

1. <span data-ttu-id="bfe0f-140">若要查看特定使用者帳戶的詳細資料，例如屬性值和指派的區段 (s) ，請使用 **InformationBarrierRecipientStatus 指令程式** 搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-140">To view details for a specific user account, such as attribute values and assigned segment(s), use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span>

    |<span data-ttu-id="bfe0f-141">**語法**</span><span class="sxs-lookup"><span data-stu-id="bfe0f-141">**Syntax**</span></span>|<span data-ttu-id="bfe0f-142">**範例**</span><span class="sxs-lookup"><span data-stu-id="bfe0f-142">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> <span data-ttu-id="bfe0f-143">您可以使用唯一識別每個使用者的任何值，例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-143">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p> <span data-ttu-id="bfe0f-144"> (您也可以將此 Cmdlet 用於單一使用者： `Get-InformationBarrierRecipientStatus -Identity <value>`) </span><span class="sxs-lookup"><span data-stu-id="bfe0f-144">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> <span data-ttu-id="bfe0f-145">在此範例中，我們會參考 Office 365： *Megan* 的 *meganb* 中的兩個使用者帳戶，以及 *Alex* 的 *alexw* 。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-145">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> |

2. <span data-ttu-id="bfe0f-146">決定您要編輯使用者帳戶設定檔的哪個屬性 (s) 。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-146">Determine which attribute you want to edit for your user account profile(s).</span></span> <span data-ttu-id="bfe0f-147">如需詳細資訊，請參閱 [資訊障礙原則的屬性](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-147">For more information, see [Attributes for information barrier policies](information-barriers-attributes.md).</span></span> 

3. <span data-ttu-id="bfe0f-148">編輯一或多個使用者帳戶，以包含您在上一個步驟中選取之屬性的值。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-148">Edit one or more user accounts to include values for the attribute you selected in the previous step.</span></span> <span data-ttu-id="bfe0f-149">若要採取此動作，請使用下列其中一個程式：</span><span class="sxs-lookup"><span data-stu-id="bfe0f-149">To take this action, use one of the following procedures:</span></span>

    - <span data-ttu-id="bfe0f-150">若要編輯單一帳戶，請參閱[使用 Azure Active Directory 新增或更新使用者的設定檔資訊](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-150">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

    - <span data-ttu-id="bfe0f-151">若要編輯多個帳戶 (或使用 PowerShell 編輯單一帳戶) ，請參閱[Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-151">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).</span></span>

## <a name="edit-a-segment"></a><span data-ttu-id="bfe0f-152">編輯區隔</span><span class="sxs-lookup"><span data-stu-id="bfe0f-152">Edit a segment</span></span>

<span data-ttu-id="bfe0f-153">使用此程式來編輯使用者區段的定義。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-153">Use this procedure edit the definition of a user segment.</span></span> <span data-ttu-id="bfe0f-154">例如，您可以變更區段的名稱或篩選，用來判斷區段中所包含的人員。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-154">For example, you might change the name of a segment, or the filter that is used to determine who's included in the segment.</span></span>

1. <span data-ttu-id="bfe0f-155">若要查看所有現有的區段，請使用 **OrganizationSegment** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-155">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>

    <span data-ttu-id="bfe0f-156">語法： `Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="bfe0f-156">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="bfe0f-157">您將會看到每個區段和詳細資料的清單，例如區段類型、它的 UserGroupFilter 值、建立或上次修改的人員、GUID 等等。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-157">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="bfe0f-158">列印或儲存區段清單以供日後參考。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-158">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="bfe0f-159">例如，如果您想要編輯區段，您必須知道其名稱或識別值 (此參數會搭配 Identity 參數) 使用。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-159">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="bfe0f-160">若要編輯片段，請使用 **OrganizationSegment 指令程式** 搭配 **Identity** 參數和相關的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-160">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span>

    |<span data-ttu-id="bfe0f-161">**語法**</span><span class="sxs-lookup"><span data-stu-id="bfe0f-161">**Syntax**</span></span>|<span data-ttu-id="bfe0f-162">**範例**</span><span class="sxs-lookup"><span data-stu-id="bfe0f-162">**Example**</span></span>|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> <span data-ttu-id="bfe0f-163">在此範例中，針對具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd* 的網段，我們將部門名稱更新為 "HRDept"。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-163">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span> |

<span data-ttu-id="bfe0f-164">完成組織的編輯資料段後，您就可以 [定義](information-barriers-policies.md#part-2-define-information-barrier-policies) 或 [編輯](#edit-a-policy) 資訊障礙原則。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-164">When you have finished editing segments for your organization, you can either [define](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

## <a name="edit-a-policy"></a><span data-ttu-id="bfe0f-165">編輯原則</span><span class="sxs-lookup"><span data-stu-id="bfe0f-165">Edit a policy</span></span>

1. <span data-ttu-id="bfe0f-166">若要查看目前資訊屏障原則的清單，請使用 **InformationBarrierPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-166">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="bfe0f-167">語法： `Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="bfe0f-167">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="bfe0f-168">在結果清單中，識別您要變更的原則。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-168">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="bfe0f-169">請注意原則的 GUID 和名稱。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-169">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="bfe0f-170">使用 **InformationBarrierPolicy** 指令程式搭配 **Identity** 參數，並指定您要進行的變更。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-170">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="bfe0f-171">範例：假設原則定義為封鎖「 *調查* 」區段與「 *銷售* 」和「 *行銷* 」區段的通訊。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-171">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="bfe0f-172">原則是使用下列 Cmdlet 來定義的： `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="bfe0f-172">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>

    <span data-ttu-id="bfe0f-173">假設我們想要變更它，讓 *調查* 區段中的人員只能與 *HR* 區段中的人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-173">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="bfe0f-174">若要進行此變更，我們使用此 Cmdlet： `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="bfe0f-174">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="bfe0f-175">在此範例中，我們已將 "SegmentsBlocked" 變更為 "SegmentsAllowed"，並指定 *HR* 段。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-175">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="bfe0f-176">當您完成編輯原則時，請務必套用您的變更。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-176">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="bfe0f-177"> (請參閱套用 [資訊屏障原則](information-barriers-policies.md#part-3-apply-information-barrier-policies)。 ) </span><span class="sxs-lookup"><span data-stu-id="bfe0f-177">(See [Apply information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)</span></span>

## <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="bfe0f-178">將原則設定為非使用中狀態</span><span class="sxs-lookup"><span data-stu-id="bfe0f-178">Set a policy to inactive status</span></span>

1. <span data-ttu-id="bfe0f-179">若要查看目前資訊屏障原則的清單，請使用 **InformationBarrierPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-179">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="bfe0f-180">語法： `Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="bfe0f-180">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="bfe0f-181">在結果清單中，找出您要變更的原則 (或移除) 。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-181">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="bfe0f-182">請注意原則的 GUID 和名稱。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-182">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="bfe0f-183">若要將原則的狀態設定為非使用中，請使用 **InformationBarrierPolicy** 指令程式搭配 Identity 參數，並將 State 參數設定為非使用中。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-183">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    |<span data-ttu-id="bfe0f-184">**語法**</span><span class="sxs-lookup"><span data-stu-id="bfe0f-184">**Syntax**</span></span>|<span data-ttu-id="bfe0f-185">**範例**</span><span class="sxs-lookup"><span data-stu-id="bfe0f-185">**Example**</span></span>|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> <span data-ttu-id="bfe0f-186">在此範例中，我們會將具有 GUID *43c37853-ea10-4b90-a23d-ab8c9377247* 的資訊屏障原則設定為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-186">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span> |

3. <span data-ttu-id="bfe0f-187">若要套用您的變更，請使用 **InformationBarrierPoliciesApplication** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-187">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="bfe0f-188">語法： `Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="bfe0f-188">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="bfe0f-189">為您的組織套用變更的使用者。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-189">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="bfe0f-190">如果您的組織很大，則可能需要24小時的時間，才能完成此程式 (或多個) 。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-190">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="bfe0f-191"> (一般指導方針，處理5000使用者帳戶大約需要一小時。 ) </span><span class="sxs-lookup"><span data-stu-id="bfe0f-191">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="bfe0f-192">此時，一或多項資訊障礙原則會設定為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-192">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="bfe0f-193">您可以從這裡執行下列任何動作：</span><span class="sxs-lookup"><span data-stu-id="bfe0f-193">From here, you can do any of the following actions:</span></span>

- <span data-ttu-id="bfe0f-194">將其保持在 (原則設定為非使用中狀態時，不會影響使用者) </span><span class="sxs-lookup"><span data-stu-id="bfe0f-194">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="bfe0f-195">編輯原則</span><span class="sxs-lookup"><span data-stu-id="bfe0f-195">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="bfe0f-196">移除原則</span><span class="sxs-lookup"><span data-stu-id="bfe0f-196">Remove a policy</span></span>](#remove-a-policy)

## <a name="remove-a-policy"></a><span data-ttu-id="bfe0f-197">移除原則</span><span class="sxs-lookup"><span data-stu-id="bfe0f-197">Remove a policy</span></span>

1. <span data-ttu-id="bfe0f-198">若要查看目前資訊屏障原則的清單，請使用 **InformationBarrierPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-198">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="bfe0f-199">語法： `Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="bfe0f-199">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="bfe0f-200">在結果清單中，識別您要移除的原則。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-200">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="bfe0f-201">請注意原則的 GUID 和名稱。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-201">Note the policy's GUID and name.</span></span> <span data-ttu-id="bfe0f-202">請確定原則設定為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-202">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="bfe0f-203">使用具有 Identity 參數的 **InformationBarrierPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-203">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="bfe0f-204">**語法**</span><span class="sxs-lookup"><span data-stu-id="bfe0f-204">**Syntax**</span></span>|<span data-ttu-id="bfe0f-205">**範例**</span><span class="sxs-lookup"><span data-stu-id="bfe0f-205">**Example**</span></span>|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> <span data-ttu-id="bfe0f-206">在此範例中，我們將移除具有 GUID *43c37853-ea10-4b90-a23d-ab8c93772471* 的原則。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-206">In this example, we are removing the policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> |

    <span data-ttu-id="bfe0f-207">出現提示時，請確認變更。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-207">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="bfe0f-208">針對您要移除的每個原則，重複步驟1-2。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-208">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="bfe0f-209">當您完成移除原則時，請套用您的變更。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-209">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="bfe0f-210">若要採取此動作，請使用 **InformationBarrierPoliciesApplication** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-210">To take this action, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="bfe0f-211">語法： `Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="bfe0f-211">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="bfe0f-212">為您的組織套用變更的使用者。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-212">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="bfe0f-213">如果您的組織很大，則可能需要24小時的時間，才能完成此程式 (或多個) 。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-213">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

## <a name="stop-a-policy-application"></a><span data-ttu-id="bfe0f-214">停止原則應用程式</span><span class="sxs-lookup"><span data-stu-id="bfe0f-214">Stop a policy application</span></span>

<span data-ttu-id="bfe0f-215">在您開始套用資訊屏障原則之後，如果您想要停止套用那些原則，請使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-215">After you have started applying information barrier policies, if you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="bfe0f-216">這會花費大約30-35 分鐘的時間來開始處理常式。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-216">It will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="bfe0f-217">若要查看最新資訊屏障原則應用程式的狀態，請使用 **InformationBarrierPoliciesApplicationStatus** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-217">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="bfe0f-218">語法： `Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="bfe0f-218">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="bfe0f-219">請記下應用程式的 GUID。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-219">Note the application's GUID.</span></span>

2. <span data-ttu-id="bfe0f-220">使用具有 Identity 參數的 **InformationBarrierPoliciesApplication** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-220">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="bfe0f-221">**語法**</span><span class="sxs-lookup"><span data-stu-id="bfe0f-221">**Syntax**</span></span>|<span data-ttu-id="bfe0f-222">**範例**</span><span class="sxs-lookup"><span data-stu-id="bfe0f-222">**Example**</span></span>|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> <span data-ttu-id="bfe0f-223">在此範例中，我們將停止套用資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="bfe0f-223">In this example, we are stopping information barrier policies from being applied.</span></span> |

## <a name="resources"></a><span data-ttu-id="bfe0f-224">資源</span><span class="sxs-lookup"><span data-stu-id="bfe0f-224">Resources</span></span>

- [<span data-ttu-id="bfe0f-225">取得資訊障礙的概覽</span><span class="sxs-lookup"><span data-stu-id="bfe0f-225">Get an overview of information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="bfe0f-226">定義資訊屏障的原則</span><span class="sxs-lookup"><span data-stu-id="bfe0f-226">Define policies for information barriers</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="bfe0f-227">深入瞭解 Microsoft Teams 中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="bfe0f-227">Learn more about information barriers in Microsoft Teams</span></span>](/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="bfe0f-228">深入瞭解 SharePoint 線上中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="bfe0f-228">Learn more about information barriers in SharePoint Online</span></span>](/sharepoint/information-barriers)
- [<span data-ttu-id="bfe0f-229">深入瞭解 OneDrive 中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="bfe0f-229">Learn more about information barriers in OneDrive</span></span>](/onedrive/information-barriers)
- [<span data-ttu-id="bfe0f-230">資訊屏障原則的屬性</span><span class="sxs-lookup"><span data-stu-id="bfe0f-230">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="bfe0f-231">疑難排解資訊屏障</span><span class="sxs-lookup"><span data-stu-id="bfe0f-231">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)