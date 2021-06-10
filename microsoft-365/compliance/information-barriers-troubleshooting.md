---
title: 疑難排解資訊屏障
description: 使用本文做為疑難排解資訊障礙的指南。
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
ms.openlocfilehash: de415ba7b68df786ead038bb72465c445a86ba5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928003"
---
# <a name="troubleshooting-information-barriers"></a><span data-ttu-id="f0530-103">疑難排解資訊屏障</span><span class="sxs-lookup"><span data-stu-id="f0530-103">Troubleshooting information barriers</span></span>

<span data-ttu-id="f0530-104">[資訊障礙](information-barriers.md) 可協助您的組織遵守法律需求和行業法規。</span><span class="sxs-lookup"><span data-stu-id="f0530-104">[Information barriers](information-barriers.md) can help your organization remain compliant with legal requirements and industry regulations.</span></span> <span data-ttu-id="f0530-105">例如，利用資訊障礙，您可以限制特定使用者群組之間的通訊，以避免利益衝突或其他問題。</span><span class="sxs-lookup"><span data-stu-id="f0530-105">For example, with information barriers, you can restrict communication between specific groups of users to avoid a conflict of interest or other issues.</span></span> <span data-ttu-id="f0530-106"> (若要深入瞭解如何設定資訊障礙，請參閱 [定義資訊障礙的原則](information-barriers-policies.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="f0530-106">(To learn more about how to set up information barriers, see [Define policies for information barriers](information-barriers-policies.md).)</span></span>

<span data-ttu-id="f0530-107">當有人在資訊壁壘出現之後發生意外問題時，您可以採取一些步驟來解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="f0530-107">In the event that people run into unexpected issues after information barriers are in place, there are some steps you can take to resolve those issues.</span></span> <span data-ttu-id="f0530-108">使用本文做為指南。</span><span class="sxs-lookup"><span data-stu-id="f0530-108">Use this article as a guide.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0530-109">若要執行本文所述的工作，您必須獲指派適當的角色，例如下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="f0530-109">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="f0530-110">-Microsoft 365 企業版全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="f0530-110">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="f0530-111">-全域管理員</span><span class="sxs-lookup"><span data-stu-id="f0530-111">- global administrator</span></span><br/><span data-ttu-id="f0530-112">-合規性管理員</span><span class="sxs-lookup"><span data-stu-id="f0530-112">- Compliance Administrator</span></span><br/><span data-ttu-id="f0530-113">-IB 相容性管理 (這是一個新的角色！ ) </span><span class="sxs-lookup"><span data-stu-id="f0530-113">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="f0530-114">若要深入瞭解資訊障礙的必要條件，請參閱 [資訊屏障原則) 的必要條件 (](information-barriers-policies.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="f0530-114">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="f0530-115">請務必 [連接至安全性 & 規範中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f0530-115">Make sure to [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a><span data-ttu-id="f0530-116">問題：使用者意外封鎖 Microsoft Teams 中的其他人進行通訊</span><span class="sxs-lookup"><span data-stu-id="f0530-116">Issue: Users are unexpectedly blocked from communicating with others in Microsoft Teams</span></span> 

<span data-ttu-id="f0530-117">在此情況下，使用者會在 Microsoft Teams 中報告與其他人進行通訊的意外問題。</span><span class="sxs-lookup"><span data-stu-id="f0530-117">In this case, people are reporting unexpected issues communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="f0530-118">部分範例如下：</span><span class="sxs-lookup"><span data-stu-id="f0530-118">Some examples are:</span></span>

- <span data-ttu-id="f0530-119">使用者可搜尋 Microsoft Teams 中的其他使用者，但找不到。</span><span class="sxs-lookup"><span data-stu-id="f0530-119">A user searches for, but is unable to find, another user in Microsoft Teams.</span></span>
- <span data-ttu-id="f0530-120">使用者可以在 Microsoft Teams 中找到，但無法選取其他使用者。</span><span class="sxs-lookup"><span data-stu-id="f0530-120">A user can find, but cannot select, another user in Microsoft Teams.</span></span>
- <span data-ttu-id="f0530-121">使用者可以查看其他使用者，但無法將郵件傳送到 Microsoft Teams 中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="f0530-121">A user can see another user, but cannot send messages to that other user in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="f0530-122">處理方式</span><span class="sxs-lookup"><span data-stu-id="f0530-122">What to do</span></span>

<span data-ttu-id="f0530-123">決定使用者是否受到資訊屏障原則的影響。</span><span class="sxs-lookup"><span data-stu-id="f0530-123">Determine whether the users are affected by an information barrier policy.</span></span> <span data-ttu-id="f0530-124">視原則的設定方式而定，資訊壁壘可能如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="f0530-124">Depending on how policies are configured, information barriers might be working as expected.</span></span> <span data-ttu-id="f0530-125">或者，您可能需要調整組織的原則。</span><span class="sxs-lookup"><span data-stu-id="f0530-125">Or, you might have to refine your organization's policies.</span></span>

1. <span data-ttu-id="f0530-126">使用 **InformationBarrierRecipientStatus** Cmdlet 搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="f0530-126">Use the **Get-InformationBarrierRecipientStatus** cmdlet with the Identity parameter.</span></span> 

    |<span data-ttu-id="f0530-127">**語法**</span><span class="sxs-lookup"><span data-stu-id="f0530-127">**Syntax**</span></span>|<span data-ttu-id="f0530-128">**範例**</span><span class="sxs-lookup"><span data-stu-id="f0530-128">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> <span data-ttu-id="f0530-129">您可以使用唯一識別每個收件者的任何 identity 值，例如 Name、Alias、辨別名稱 (DN) 、正常化 DN、電子郵件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="f0530-129">You can use any identity value that uniquely identifies each recipient, such as Name, Alias, Distinguished name (DN), Canonical DN, Email address, or GUID.</span></span> |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> <span data-ttu-id="f0530-130">在此範例中，我們為 Identity 參數使用別名 (*meganb*) 。</span><span class="sxs-lookup"><span data-stu-id="f0530-130">In this example, we are using an alias (*meganb*) for the Identity parameter.</span></span> <span data-ttu-id="f0530-131">此 Cmdlet 會傳回指出使用者是否受到資訊屏障原則影響的資訊。</span><span class="sxs-lookup"><span data-stu-id="f0530-131">This cmdlet will return information that indicates whether the user is affected by an information barrier policy.</span></span> <span data-ttu-id="f0530-132"> (，請參閱\ * ExoPolicyId： \<GUID> 。 ) </span><span class="sxs-lookup"><span data-stu-id="f0530-132">(Look for \*ExoPolicyId: \<GUID>.)</span></span> |

    <span data-ttu-id="f0530-133">**如果使用者未包含在資訊屏障原則中，請與支援人員聯繫**。</span><span class="sxs-lookup"><span data-stu-id="f0530-133">**If the users are not included in information barrier policies, contact support**.</span></span> <span data-ttu-id="f0530-134">否則，請繼續進行下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="f0530-134">Otherwise, proceed to the next step.</span></span>

2. <span data-ttu-id="f0530-135">瞭解資訊屏障原則中所包含的段落。</span><span class="sxs-lookup"><span data-stu-id="f0530-135">Find out which segments are included in an information barrier policy.</span></span> <span data-ttu-id="f0530-136">若要這麼做，請使用 `Get-InformationBarrierPolicy` Cmdlet 搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="f0530-136">To do this, use the `Get-InformationBarrierPolicy` cmdlet with the Identity parameter.</span></span> 

    |<span data-ttu-id="f0530-137">**語法**</span><span class="sxs-lookup"><span data-stu-id="f0530-137">**Syntax**</span></span>|<span data-ttu-id="f0530-138">**範例**</span><span class="sxs-lookup"><span data-stu-id="f0530-138">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> <span data-ttu-id="f0530-139">使用詳細資料，例如您在上一個步驟中所收到的原則 GUID (ExoPolicyId) 身分識別值。</span><span class="sxs-lookup"><span data-stu-id="f0530-139">Use details, such as the policy GUID (ExoPolicyId) you received during the previous step, as an identity value.</span></span> | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> <span data-ttu-id="f0530-140">在此範例中，我們取得的資訊屏障原則的詳細資訊 ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*。</span><span class="sxs-lookup"><span data-stu-id="f0530-140">In this example, we are getting detailed information about the information barrier policy that has ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span></span> |

    <span data-ttu-id="f0530-141">在您執行 Cmdlet 後，請在 [結果] 中，尋找 [ **AssignedSegment**]、[ **SegmentsAllowed**] 及 [ **SegmentsBlocked** ] 值。</span><span class="sxs-lookup"><span data-stu-id="f0530-141">After you run the cmdlet, in the results, look for **AssignedSegment**, **SegmentsAllowed**, and **SegmentsBlocked** values.</span></span>

    <span data-ttu-id="f0530-142">例如， `Get-InformationBarrierPolicy` 執行 Cmdlet 後，我們會在結果清單中看到下列專案：</span><span class="sxs-lookup"><span data-stu-id="f0530-142">For example, after running the `Get-InformationBarrierPolicy` cmdlet, we saw the following in our list of results:</span></span>

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    <span data-ttu-id="f0530-143">在此情況下，我們可以看到資訊障礙原則會影響銷售和研究中心中的人員。</span><span class="sxs-lookup"><span data-stu-id="f0530-143">In this case, we can see that an information barrier policy affects people who are in the Sales and Research segments.</span></span> <span data-ttu-id="f0530-144">在此情況下，會防止銷售人員與調查中的人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="f0530-144">In this case, people in Sales are prevented from communicating with people in Research.</span></span>

    <span data-ttu-id="f0530-145">如果看起來正確，則資訊壁壘會如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="f0530-145">If this seems correct, then information barriers are working as expected.</span></span> <span data-ttu-id="f0530-146">若未完成，請繼續進行下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="f0530-146">If not, proceed to the next step.</span></span>

3. <span data-ttu-id="f0530-147">請確定已正確定義您的區段。</span><span class="sxs-lookup"><span data-stu-id="f0530-147">Make sure your segments are defined correctly.</span></span> <span data-ttu-id="f0530-148">若要這麼做，請使用 `Get-OrganizationSegment` Cmdlet，並複查結果清單。</span><span class="sxs-lookup"><span data-stu-id="f0530-148">To do this, use the `Get-OrganizationSegment` cmdlet, and review the list of results.</span></span>

    |<span data-ttu-id="f0530-149">**語法**</span><span class="sxs-lookup"><span data-stu-id="f0530-149">**Syntax**</span></span>|<span data-ttu-id="f0530-150">**範例**</span><span class="sxs-lookup"><span data-stu-id="f0530-150">**Example**</span></span>|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> <span data-ttu-id="f0530-151">使用此 Cmdlet 搭配 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="f0530-151">Use this cmdlet with an Identity parameter.</span></span> | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> <span data-ttu-id="f0530-152">在此範例中，我們會取得 GUID 為 *c96e0837-c232-4a8a-841e-ef45787d8fcd* 之網段的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f0530-152">In this example, we are getting information about the segment that has GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.</span></span> |

    <span data-ttu-id="f0530-153">查看區段的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f0530-153">Review the details for the segment.</span></span> <span data-ttu-id="f0530-154">如有必要，請 [編輯區段](information-barriers-edit-segments-policies.md#edit-a-segment)，然後重新使用 `Start-InformationBarrierPoliciesApplication` Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f0530-154">If necessary, [edit a segment](information-barriers-edit-segments-policies.md#edit-a-segment), and then re-use the `Start-InformationBarrierPoliciesApplication` cmdlet.</span></span>

    <span data-ttu-id="f0530-155">**如果您仍有資訊屏障原則的問題，請與支援人員聯繫**。</span><span class="sxs-lookup"><span data-stu-id="f0530-155">**If you are still having issues with your information barrier policy, contact support**.</span></span>

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a><span data-ttu-id="f0530-156">問題：允許在 Microsoft Teams 封鎖的使用者之間進行通訊</span><span class="sxs-lookup"><span data-stu-id="f0530-156">Issue: Communications are allowed between users who should be blocked in Microsoft Teams</span></span>

<span data-ttu-id="f0530-157">在此情況下，雖然資訊壁壘已定義、使用中且已套用，但應禁止彼此進行通訊的人員可以在 Microsoft Teams 中互動及呼叫對方。</span><span class="sxs-lookup"><span data-stu-id="f0530-157">In this case, although information barriers are defined, active, and applied, people who should be prevented from communicating with each other are somehow able to chat with and call each other in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="f0530-158">處理方式</span><span class="sxs-lookup"><span data-stu-id="f0530-158">What to do</span></span>

<span data-ttu-id="f0530-159">確認有問題的使用者已包含在資訊屏障原則中。</span><span class="sxs-lookup"><span data-stu-id="f0530-159">Verify that the users in question are included in an information barrier policy.</span></span> 

1. <span data-ttu-id="f0530-160">使用具有 Identity 參數的 **InformationBarrierRecipientStatus** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f0530-160">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span>

    |<span data-ttu-id="f0530-161">**語法** _</span><span class="sxs-lookup"><span data-stu-id="f0530-161">**Syntax** _</span></span>|<span data-ttu-id="f0530-162">_ *範例*\*</span><span class="sxs-lookup"><span data-stu-id="f0530-162">_ *Example*\*</span></span>|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> <span data-ttu-id="f0530-163">您可以使用唯一識別每個使用者的任何值，例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="f0530-163">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> <span data-ttu-id="f0530-164">在此範例中，我們會參考 Office 365： *Megan* 的 *meganb* 中的兩個使用者帳戶，以及 *Alex* 的 *alexw* 。</span><span class="sxs-lookup"><span data-stu-id="f0530-164">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> |

    > [!TIP]
    > <span data-ttu-id="f0530-165">您也可以將此 Cmdlet 用於單一使用者： `Get-InformationBarrierRecipientStatus -Identity <value>`</span><span class="sxs-lookup"><span data-stu-id="f0530-165">You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`</span></span>

2. <span data-ttu-id="f0530-166">回顧結果。</span><span class="sxs-lookup"><span data-stu-id="f0530-166">Review the findings.</span></span> <span data-ttu-id="f0530-167">**InformationBarrierRecipientStatus 指令程式** 會傳回使用者的相關資訊，例如屬性值以及所套用的任何資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="f0530-167">The **Get-InformationBarrierRecipientStatus** cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>

    <span data-ttu-id="f0530-168">檢查結果，然後採取後續的步驟，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="f0530-168">Review the results, and then take your next steps, as described in the following table:</span></span>

    |<span data-ttu-id="f0530-169">**Results**</span><span class="sxs-lookup"><span data-stu-id="f0530-169">**Results**</span></span>|<span data-ttu-id="f0530-170">**接下來要執行的動作**</span><span class="sxs-lookup"><span data-stu-id="f0530-170">**What to do next**</span></span>|
    |:----------|:------------------|
    | <span data-ttu-id="f0530-171">未列出選定使用者 (s 的區段) </span><span class="sxs-lookup"><span data-stu-id="f0530-171">No segments are listed for the selected user(s)</span></span> | <span data-ttu-id="f0530-172">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="f0530-172">Do one of the following:</span></span><br/><span data-ttu-id="f0530-173">-在 Azure Active Directory 中編輯使用者設定檔，以將使用者指派至現有的區段。</span><span class="sxs-lookup"><span data-stu-id="f0530-173">- Assign users to an existing segment by editing their user profiles in Azure Active Directory.</span></span> <span data-ttu-id="f0530-174"> (請參閱[使用 Office 365 PowerShell 設定使用者帳戶屬性](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="f0530-174">(See [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).)</span></span><br/><span data-ttu-id="f0530-175">-使用 [支援的資訊障礙屬性](information-barriers-attributes.md)定義區段。</span><span class="sxs-lookup"><span data-stu-id="f0530-175">- Define a segment using a [supported attribute for information barriers](information-barriers-attributes.md).</span></span> <span data-ttu-id="f0530-176">然後， [定義新的原則](information-barriers-policies.md#part-2-define-information-barrier-policies) 或 [編輯現有的原則](information-barriers-edit-segments-policies.md#edit-a-policy) ，以包含該區段。</span><span class="sxs-lookup"><span data-stu-id="f0530-176">Then, either [define a new policy](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit an existing policy](information-barriers-edit-segments-policies.md#edit-a-policy) to include that segment.</span></span> |
    | <span data-ttu-id="f0530-177">會列出網段，但不會將資訊障礙原則指派給那些區段</span><span class="sxs-lookup"><span data-stu-id="f0530-177">Segments are listed but no information barrier policies are assigned to those segments</span></span> | <span data-ttu-id="f0530-178">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="f0530-178">Do one of the following:</span></span><br/><span data-ttu-id="f0530-179">- 為相關的每個區段[定義新的資訊屏障原則](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="f0530-179">- [Define a new information barrier policy](information-barriers-policies.md#part-2-define-information-barrier-policies) for each segment in question</span></span> <br/><span data-ttu-id="f0530-180">- [編輯現有的資訊屏障原則](information-barriers-edit-segments-policies.md#edit-a-policy) ，將其指派給正確的區段</span><span class="sxs-lookup"><span data-stu-id="f0530-180">- [Edit an existing information barrier policy](information-barriers-edit-segments-policies.md#edit-a-policy) to assign it to the correct segment</span></span> |
    | <span data-ttu-id="f0530-181">列出各段，且每個區段都包含在資訊屏障原則中</span><span class="sxs-lookup"><span data-stu-id="f0530-181">Segments are listed and each is included in an information barrier policy</span></span> | <span data-ttu-id="f0530-182">-執行 `Get-InformationBarrierPolicy` Cmdlet 以確認資訊屏障原則為作用中狀態。</span><span class="sxs-lookup"><span data-stu-id="f0530-182">- Run the `Get-InformationBarrierPolicy` cmdlet to verify that information barrier policies are active</span></span><br/><span data-ttu-id="f0530-183">-執行 `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet 以確認已套用原則</span><span class="sxs-lookup"><span data-stu-id="f0530-183">- Run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet to confirm the policies are applied</span></span><br/><span data-ttu-id="f0530-184">-執行 `Start-InformationBarrierPoliciesApplication` Cmdlet 以套用所有作用中的資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="f0530-184">- Run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies</span></span> |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a><span data-ttu-id="f0530-185">問題：我需要從資訊屏障原則中移除單一使用者</span><span class="sxs-lookup"><span data-stu-id="f0530-185">Issue: I need to remove a single user from an information barrier policy</span></span>

<span data-ttu-id="f0530-186">在此情況下，資訊屏障原則會生效，且意外封鎖一或多個使用者與 Microsoft Teams 中的其他使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="f0530-186">In this case, information barrier policies are in effect, and a one or more users are unexpectedly blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="f0530-187">您可以移除資訊屏障原則中的一或多個個別使用者，而不是完全移除資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="f0530-187">Rather than remove information barrier policies altogether, you can remove one or more individual users from information barrier policies.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="f0530-188">處理方式</span><span class="sxs-lookup"><span data-stu-id="f0530-188">What to do</span></span>

<span data-ttu-id="f0530-189">資訊屏障原則會指派給使用者區段。</span><span class="sxs-lookup"><span data-stu-id="f0530-189">Information barrier policies are assigned to segments of users.</span></span> <span data-ttu-id="f0530-190">區段是以 [使用者帳戶設定檔中](information-barriers-attributes.md)的特定屬性定義。</span><span class="sxs-lookup"><span data-stu-id="f0530-190">Segments are defined by using certain [attributes in user account profiles](information-barriers-attributes.md).</span></span> <span data-ttu-id="f0530-191">如果您必須從單一使用者移除原則，請考慮在 Azure Active Directory 中編輯該使用者的設定檔，讓使用者不再包含在受到資訊障礙影響的區段中。</span><span class="sxs-lookup"><span data-stu-id="f0530-191">If you must remove a policy from a single user, consider editing that user's profile in Azure Active Directory such that the user is no longer included in a segment affected by information barriers.</span></span>

1. <span data-ttu-id="f0530-192">使用具有 Identity 參數的 **InformationBarrierRecipientStatus** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f0530-192">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> <span data-ttu-id="f0530-193">此 Cmdlet 會傳回使用者的相關資訊，例如屬性值以及所套用的任何資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="f0530-193">This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>

    |<span data-ttu-id="f0530-194">**語法**</span><span class="sxs-lookup"><span data-stu-id="f0530-194">**Syntax**</span></span>|<span data-ttu-id="f0530-195">**範例**</span><span class="sxs-lookup"><span data-stu-id="f0530-195">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> <span data-ttu-id="f0530-196">您可以使用唯一識別每個使用者的任何值，例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="f0530-196">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> <span data-ttu-id="f0530-197">在此範例中，我們會參考 Office 365： *Megan* 的 *meganb* 中的兩個使用者帳戶，以及 *Alex* 的 *alexw* 。</span><span class="sxs-lookup"><span data-stu-id="f0530-197">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span>          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> <span data-ttu-id="f0530-198">您可以使用唯一識別使用者的任何值，例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="f0530-198">You can use any value that uniquely identifies the user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span>|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> <span data-ttu-id="f0530-199">在此範例中，我們會參考 Office 365： *jeanp* 中的單一帳戶。</span><span class="sxs-lookup"><span data-stu-id="f0530-199">In this example, we refer to a single account in Office 365: *jeanp*.</span></span> |

2. <span data-ttu-id="f0530-200">檢查結果，以查看是否已指派資訊屏障原則，以及 (s) 屬於哪個區段 (s) 使用者。</span><span class="sxs-lookup"><span data-stu-id="f0530-200">Review the results to see if information barrier policies are assigned, and to which segment(s) the user(s) belong.</span></span>

3. <span data-ttu-id="f0530-201">若要從受資訊障礙影響的區段中移除使用者，請[更新 Azure Active Directory 中的使用者設定檔資訊](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="f0530-201">To remove a user from a segment affected by information barriers, [update the user's profile information in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

4. <span data-ttu-id="f0530-202">等候大約30分鐘，以進行 FwdSync。</span><span class="sxs-lookup"><span data-stu-id="f0530-202">Wait about 30 minutes for FwdSync to occur.</span></span> <span data-ttu-id="f0530-203">或者，執行 Cmdlet 以套用所有作用中的 `Start-InformationBarrierPoliciesApplication` 資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="f0530-203">Or, run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies.</span></span>

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a><span data-ttu-id="f0530-204">問題：資訊障礙應用程式處理時間過長</span><span class="sxs-lookup"><span data-stu-id="f0530-204">Issue: The information barrier application process is taking too long</span></span>

<span data-ttu-id="f0530-205">在執行 **InformationBarrierPoliciesApplication 指令程式** 之後，處理常式會花很長的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="f0530-205">After running the **Start-InformationBarrierPoliciesApplication** cmdlet, the process is taking a really long time to finish.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="f0530-206">處理方式</span><span class="sxs-lookup"><span data-stu-id="f0530-206">What to do</span></span>

<span data-ttu-id="f0530-207">請記住，當您執行 policy application Cmdlet 時，會將資訊屏障原則套用 (或移除組織中所有帳戶的) （使用者）。</span><span class="sxs-lookup"><span data-stu-id="f0530-207">Keep in mind that when you run the policy application cmdlet, information barrier policies are being applied (or removed), user by user, for all accounts in your organization.</span></span> <span data-ttu-id="f0530-208">如果您有許多使用者，需要一些時間才能進行處理。</span><span class="sxs-lookup"><span data-stu-id="f0530-208">If you have a lot of users, it will take a while to process.</span></span> <span data-ttu-id="f0530-209"> (一般指導方針，處理5000使用者帳戶大約需要一小時。 ) </span><span class="sxs-lookup"><span data-stu-id="f0530-209">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

1. <span data-ttu-id="f0530-210">使用 **InformationBarrierPoliciesApplicationStatus** 指令程式來驗證最近的原則應用程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="f0530-210">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet to verify status of the most recent policy application.</span></span>

    |<span data-ttu-id="f0530-211">**若要查看最新的原則應用程式**</span><span class="sxs-lookup"><span data-stu-id="f0530-211">**To view the most recent policy application**</span></span>|<span data-ttu-id="f0530-212">**若要查看所有原則應用程式的狀態**</span><span class="sxs-lookup"><span data-stu-id="f0530-212">**To view status for all policy applications**</span></span>|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    <span data-ttu-id="f0530-213">這會顯示原則應用程式已完成、失敗或進行中的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f0530-213">This will display information about whether policy application completed, failed, or is in progress.</span></span>

2. <span data-ttu-id="f0530-214">根據上一個步驟的結果，執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="f0530-214">Depending on the results of the previous step, take one of the following steps:</span></span>
  
    |<span data-ttu-id="f0530-215">**狀態**</span><span class="sxs-lookup"><span data-stu-id="f0530-215">**Status**</span></span>|<span data-ttu-id="f0530-216">**下一步**</span><span class="sxs-lookup"><span data-stu-id="f0530-216">**Next step**</span></span>|
    |:---------|:------------|
    | <span data-ttu-id="f0530-217">**未開始**</span><span class="sxs-lookup"><span data-stu-id="f0530-217">**Not started**</span></span> | <span data-ttu-id="f0530-218">若 **InformationBarrierPoliciesApplication** Cmdlet 已執行超過45分鐘，請複查您的審核記錄檔，以查看原則定義中是否有任何錯誤，或應用程式尚未啟動的其他一些原因。</span><span class="sxs-lookup"><span data-stu-id="f0530-218">If it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started.</span></span> |
    | <span data-ttu-id="f0530-219">**已失敗**</span><span class="sxs-lookup"><span data-stu-id="f0530-219">**Failed**</span></span> | <span data-ttu-id="f0530-220">若應用程式失敗，請複查您的審核記錄檔。</span><span class="sxs-lookup"><span data-stu-id="f0530-220">If the application has failed, review your audit log.</span></span> <span data-ttu-id="f0530-221">另外，請複查您的區段和原則。</span><span class="sxs-lookup"><span data-stu-id="f0530-221">Also review your segments and policies.</span></span> <span data-ttu-id="f0530-222">是否有任何使用者被指派至多個區段？</span><span class="sxs-lookup"><span data-stu-id="f0530-222">Are any users assigned to more than one segment?</span></span> <span data-ttu-id="f0530-223">是否有任何區段被指派多個 poliicy？</span><span class="sxs-lookup"><span data-stu-id="f0530-223">Are any segments assigned more than one poliicy?</span></span> <span data-ttu-id="f0530-224">如有必要，請 [編輯區段](information-barriers-edit-segments-policies.md#edit-a-segment) 和/或 [編輯原則](information-barriers-edit-segments-policies.md#edit-a-policy)，然後再次執行 **InformationBarrierPoliciesApplication** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f0530-224">If necessary, [edit segments](information-barriers-edit-segments-policies.md#edit-a-segment) and/or [edit policies](information-barriers-edit-segments-policies.md#edit-a-policy), and then run the **Start-InformationBarrierPoliciesApplication** cmdlet again.</span></span> |
    | <span data-ttu-id="f0530-225">**進行中。**</span><span class="sxs-lookup"><span data-stu-id="f0530-225">**In progress**</span></span> | <span data-ttu-id="f0530-226">若應用程式仍在進行中，請允許更多的時間完成。</span><span class="sxs-lookup"><span data-stu-id="f0530-226">If the application is still in progress, allow more time for it to complete.</span></span> <span data-ttu-id="f0530-227">如果有好幾天，請收集您的審計記錄檔，然後與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="f0530-227">If it has been several days, gather your audit logs, and then contact support.</span></span> |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a><span data-ttu-id="f0530-228">問題：根本沒有套用資訊屏障原則</span><span class="sxs-lookup"><span data-stu-id="f0530-228">Issue: Information barrier policies are not being applied at all</span></span>

<span data-ttu-id="f0530-229">在此情況下，您已定義區段、定義的資訊關卡原則，並嘗試套用這些原則。</span><span class="sxs-lookup"><span data-stu-id="f0530-229">In this case, you have defined segments, defined information barrier policies, and have attempted to apply those policies.</span></span> <span data-ttu-id="f0530-230">不過，當您執行 `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet 時，您可以看到原則應用程式失敗。</span><span class="sxs-lookup"><span data-stu-id="f0530-230">However, when you run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, you can see that policy application has failed.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="f0530-231">處理方式</span><span class="sxs-lookup"><span data-stu-id="f0530-231">What to do</span></span>

<span data-ttu-id="f0530-232">請確定您的組織沒有適當的[Exchange 通訊錄原則](/exchange/address-books/address-book-policies/address-book-policies)。</span><span class="sxs-lookup"><span data-stu-id="f0530-232">Make sure that your organization does not have [Exchange address book policies](/exchange/address-books/address-book-policies/address-book-policies) in place.</span></span> <span data-ttu-id="f0530-233">這類原則會防止套用資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="f0530-233">Such policies will prevent information barrier policies from being applied.</span></span>

1. <span data-ttu-id="f0530-234">連線[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f0530-234">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f0530-235">執行 [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) Cmdlet，並檢查結果。</span><span class="sxs-lookup"><span data-stu-id="f0530-235">Run the [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) cmdlet, and review the results.</span></span>

    |<span data-ttu-id="f0530-236">**Results**</span><span class="sxs-lookup"><span data-stu-id="f0530-236">**Results**</span></span>|<span data-ttu-id="f0530-237">**下一步**</span><span class="sxs-lookup"><span data-stu-id="f0530-237">**Next step**</span></span>|
    |:----------|:------------|
    | <span data-ttu-id="f0530-238">列出 Exchange 通訊錄原則</span><span class="sxs-lookup"><span data-stu-id="f0530-238">Exchange address book policies are listed</span></span> | [<span data-ttu-id="f0530-239">移除通訊錄原則</span><span class="sxs-lookup"><span data-stu-id="f0530-239">Remove address book policies</span></span>](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | <span data-ttu-id="f0530-240">無通訊錄原則存在</span><span class="sxs-lookup"><span data-stu-id="f0530-240">No address book policies exist</span></span> |<span data-ttu-id="f0530-241">檢查您的審計記錄檔，以找出原則應用程式失敗的原因</span><span class="sxs-lookup"><span data-stu-id="f0530-241">Review your audit logs to find out why policy application is failing</span></span> |

3. <span data-ttu-id="f0530-242">[查看使用者帳戶、區段、原則或原則應用程式的狀態](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)。</span><span class="sxs-lookup"><span data-stu-id="f0530-242">[View status of user accounts, segments, policies, or policy application](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application).</span></span>

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a><span data-ttu-id="f0530-243">問題：資訊屏障原則未套用至所有指定的使用者</span><span class="sxs-lookup"><span data-stu-id="f0530-243">Issue: Information barrier policy not applied to all designated users</span></span>

<span data-ttu-id="f0530-244">定義資料段、定義資訊屏障原則，並嘗試套用這些原則之後，您可能會發現原則套用至某些收件者，而不是其他收件者。</span><span class="sxs-lookup"><span data-stu-id="f0530-244">After you have defined segments, defined information barrier policies, and have attempted to apply those policies, you may find that the policy is applying to some recipients, but not to others.</span></span>
<span data-ttu-id="f0530-245">當您執行 `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet 時，請搜尋輸出以取得類似的文字。</span><span class="sxs-lookup"><span data-stu-id="f0530-245">When you run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, search the output for text like this.</span></span>

> <span data-ttu-id="f0530-246">身份： `<application guid>`</span><span class="sxs-lookup"><span data-stu-id="f0530-246">Identity: `<application guid>`</span></span>
>
> <span data-ttu-id="f0530-247">收件者總數：81527</span><span class="sxs-lookup"><span data-stu-id="f0530-247">Total Recipients: 81527</span></span>
>
> <span data-ttu-id="f0530-248">失敗的收件者：2</span><span class="sxs-lookup"><span data-stu-id="f0530-248">Failed Recipients: 2</span></span>
>
> <span data-ttu-id="f0530-249">失敗類別：無</span><span class="sxs-lookup"><span data-stu-id="f0530-249">Failure Category: None</span></span>
>
> <span data-ttu-id="f0530-250">狀態：完成</span><span class="sxs-lookup"><span data-stu-id="f0530-250">Status: Complete</span></span>

### <a name="what-to-do"></a><span data-ttu-id="f0530-251">處理方式</span><span class="sxs-lookup"><span data-stu-id="f0530-251">What to do</span></span>

1. <span data-ttu-id="f0530-252">在審核記錄中搜尋 `<application guid>` 。</span><span class="sxs-lookup"><span data-stu-id="f0530-252">Search in the audit log for `<application guid>`.</span></span> <span data-ttu-id="f0530-253">您可以將此 PowerShell 程式碼和您的變數一起修改。</span><span class="sxs-lookup"><span data-stu-id="f0530-253">You can copy this PowerShell code and modify for your variables.</span></span>

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. <span data-ttu-id="f0530-254">檢查 [和] 欄位的值之審核記錄中的詳細 `"UserId"` 輸出 `"ErrorDetails"` 。</span><span class="sxs-lookup"><span data-stu-id="f0530-254">Check the detailed output from the audit log for the values of the `"UserId"` and `"ErrorDetails"` fields.</span></span> <span data-ttu-id="f0530-255">這可讓您失敗的原因。</span><span class="sxs-lookup"><span data-stu-id="f0530-255">This will give you the reason for the failure.</span></span> <span data-ttu-id="f0530-256">您可以將此 PowerShell 程式碼和您的變數一起修改。</span><span class="sxs-lookup"><span data-stu-id="f0530-256">You can copy this PowerShell code and modify for your variables.</span></span>

```powershell
   $DetailedLogs[1] |fl
```

<span data-ttu-id="f0530-257">例如：</span><span class="sxs-lookup"><span data-stu-id="f0530-257">For example:</span></span>

> <span data-ttu-id="f0530-258">"UserId"： User1</span><span class="sxs-lookup"><span data-stu-id="f0530-258">"UserId":  User1</span></span>
>
><span data-ttu-id="f0530-259">"ErrorDetails"： "Status： IBPolicyConflict。</span><span class="sxs-lookup"><span data-stu-id="f0530-259">"ErrorDetails":"Status: IBPolicyConflict.</span></span> <span data-ttu-id="f0530-260">錯誤： IB 區段 "segment id1" 和 IB 線段 "segment id2" 發生衝突，且無法指派給收件者。</span><span class="sxs-lookup"><span data-stu-id="f0530-260">Error: IB  segment "segment id1" and IB segment "segment id2" has conflict and cannot be assigned to the recipient.</span></span>

3. <span data-ttu-id="f0530-261">通常，您會發現使用者已包含在一個以上的區段中。</span><span class="sxs-lookup"><span data-stu-id="f0530-261">Usually, you will find that a user has been included in more than one segment.</span></span> <span data-ttu-id="f0530-262">您可以更新中的值以修正此問題 `-UserGroupFilter` `OrganizationSegments` 。</span><span class="sxs-lookup"><span data-stu-id="f0530-262">You can fix this by updating the `-UserGroupFilter` value in `OrganizationSegments`.</span></span>

4. <span data-ttu-id="f0530-263">使用這些程式 [資訊障礙原則](information-barriers-policies.md#part-3-apply-information-barrier-policies)，重新套用資訊屏障原則。</span><span class="sxs-lookup"><span data-stu-id="f0530-263">Re-apply information barrier policies using these procedures [Information Barriers policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).</span></span>

## <a name="resources"></a><span data-ttu-id="f0530-264">資源</span><span class="sxs-lookup"><span data-stu-id="f0530-264">Resources</span></span>

- [<span data-ttu-id="f0530-265">在 Microsoft Teams 中定義資訊障礙的原則</span><span class="sxs-lookup"><span data-stu-id="f0530-265">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="f0530-266">資訊屏障</span><span class="sxs-lookup"><span data-stu-id="f0530-266">Information barriers</span></span>](information-barriers.md)