---
title: 設定監督原則
description: 設定 Office 365 的通訊監督
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
titleSuffix: Office 365 Compliance
ms.openlocfilehash: 2935f6d163a954cf17e4e4ce3c357028c9763b3b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632368"
---
# <a name="configure-supervision-policies-in-office-365"></a><span data-ttu-id="e65fe-103">在 Office 365 中設定監督原則</span><span class="sxs-lookup"><span data-stu-id="e65fe-103">Configure supervision policies in Office 365</span></span>

>[!IMPORTANT]
><span data-ttu-id="e65fe-104">本主題適用于設定 Microsoft 365 訂閱中的監察原則。</span><span class="sxs-lookup"><span data-stu-id="e65fe-104">This topic applies to configuring supervision policies in a Microsoft 365 subscription.</span></span> <span data-ttu-id="e65fe-105">如果您想要為 Microsoft 365 訂閱設定通訊相容性，請參閱[設定 microsoft 365 中的通訊法規遵從性](communication-compliance-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="e65fe-105">If you want to configure communications compliance for a Microsoft 365 subscription, see [Configure communications compliance in Microsoft 365](communication-compliance-configure.md).</span></span>

<span data-ttu-id="e65fe-106">使用監督原則來捕獲員工通訊，以供內部或外部的檢閱者檢查。</span><span class="sxs-lookup"><span data-stu-id="e65fe-106">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="e65fe-107">如需監督原則如何協助您監視組織中通訊的詳細資訊，請參閱[Office 365 中的監管原則](supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e65fe-107">For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

>[!NOTE]
><span data-ttu-id="e65fe-108">監控原則所監控的使用者，必須具備 Microsoft 365 E5 相容性授權、具有高級合規性附加元件的 Office 365 企業版 E3 授權，或是包含在 Office 365 企業版 E5 訂閱中，或包含在 Microsoft 365 E5 訂閱中。</span><span class="sxs-lookup"><span data-stu-id="e65fe-108">Users monitored by supervision policies must have a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription, or be included in a Microsoft 365 E5 subscription.</span></span>
><span data-ttu-id="e65fe-109">如果您沒有現有的企業版 E5 計畫，而且想要嘗試監督，您可以[註冊 Office 365 Enterprise e5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="e65fe-109">If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="e65fe-110">請遵循下列步驟，在您的組織中設定及使用監督：</span><span class="sxs-lookup"><span data-stu-id="e65fe-110">Follow these steps to set up and use supervision in your organization:</span></span>
  
- <span data-ttu-id="e65fe-111">**步驟1（選用）**：[設定監督群組](#step-1-set-up-groups-for-supervision-optional)</span><span class="sxs-lookup"><span data-stu-id="e65fe-111">**Step 1 (optional)**: [Set up groups for supervision](#step-1-set-up-groups-for-supervision-optional)</span></span>

    <span data-ttu-id="e65fe-112">開始使用監察原則之前，請先決定誰需要檢查通訊，以及誰會執行評論。</span><span class="sxs-lookup"><span data-stu-id="e65fe-112">Before you start using supervision policies, determine who needs communications reviewed and who performs reviews.</span></span> <span data-ttu-id="e65fe-113">如果您想要開始使用少數使用者來查看監管的運作方式，您可以略過設定 [群組] 立即。</span><span class="sxs-lookup"><span data-stu-id="e65fe-113">If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="e65fe-114">**步驟2（必要）**：[讓監管可用於您的組織](#step-2-make-supervision-available-in-your-organization-required)</span><span class="sxs-lookup"><span data-stu-id="e65fe-114">**Step 2 (required)**: [Make supervision available in your organization](#step-2-make-supervision-available-in-your-organization-required)</span></span>

    <span data-ttu-id="e65fe-115">將您本人新增至主管審查角色群組，讓您可以設定原則。</span><span class="sxs-lookup"><span data-stu-id="e65fe-115">Add yourself to the Supervisory Review role group so you can set up policies.</span></span> <span data-ttu-id="e65fe-116">已指派此角色的任何人都可以存取安全性 & 規範中心內的**監管**頁面。</span><span class="sxs-lookup"><span data-stu-id="e65fe-116">Anyone who has this role assigned can access the **Supervision** page in the Security & Compliance Center.</span></span> <span data-ttu-id="e65fe-117">如果 reviewable 電子郵件主控于 Exchange Online，則每個檢閱者都必須有[Exchange online 的遠端 PowerShell 存取權](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e65fe-117">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e65fe-118">**步驟3（選用）**：[建立自訂機密資訊類型及自訂關鍵字字典](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span><span class="sxs-lookup"><span data-stu-id="e65fe-118">**Step 3 (optional)**: [Create custom sensitive information types and custom keyword dictionaries](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span></span>

    <span data-ttu-id="e65fe-119">如果您需要監管原則的自訂敏感資訊類型或自訂關鍵字字典，您必須在啟動監管嚮導之前加以建立。</span><span class="sxs-lookup"><span data-stu-id="e65fe-119">If you need a custom sensitive info type or a custom keyword dictionary for your supervision policy, you need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="e65fe-120">**步驟4（必要）**：[設定監督原則](#step-4-set-up-a-supervision-policy-required)</span><span class="sxs-lookup"><span data-stu-id="e65fe-120">**Step 4 (required)**: [Set up a supervision policy](#step-4-set-up-a-supervision-policy-required)</span></span>

    <span data-ttu-id="e65fe-121">您可以在安全性 & 規範中心建立監督原則。</span><span class="sxs-lookup"><span data-stu-id="e65fe-121">You create supervision policies in the Security & Compliance Center.</span></span> <span data-ttu-id="e65fe-122">這些原則定義哪些通訊會在您的組織中進行檢查，並指定誰會執行評論。</span><span class="sxs-lookup"><span data-stu-id="e65fe-122">These policies define which communications are subject to review in your organization and specifies who performs reviews.</span></span> <span data-ttu-id="e65fe-123">通訊包括電子郵件和 Microsoft 小組通訊，以及協力廠商平臺通訊（如 Facebook、Twitter 等）。</span><span class="sxs-lookup"><span data-stu-id="e65fe-123">Communications include email and Microsoft Teams communications, and 3rd-party platform communications (such as Facebook, Twitter, etc.).</span></span> <span data-ttu-id="e65fe-124">Microsoft 365 訂閱中的通訊監督不支援組織中所建立的監督原則。</span><span class="sxs-lookup"><span data-stu-id="e65fe-124">Supervision policies created in organizations are not supported in communication supervision in Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="e65fe-125">**步驟5（選用）**：[測試通訊監督原則](#step-5-test-your-supervision-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="e65fe-125">**Step 5 (optional)**: [Test your communication supervision policy](#step-5-test-your-supervision-policy-optional)</span></span>

    <span data-ttu-id="e65fe-126">測試您的監督原則，確定其運作正常。</span><span class="sxs-lookup"><span data-stu-id="e65fe-126">Test your supervision policy to make sure it functions as desired.</span></span> <span data-ttu-id="e65fe-127">務必確定您的規範策略符合您的標準。</span><span class="sxs-lookup"><span data-stu-id="e65fe-127">It is important to ensure that your compliance strategy is meeting your standards.</span></span>

## <a name="step-1-set-up-groups-for-supervision-optional"></a><span data-ttu-id="e65fe-128">步驟1：設定監督群組（選用）</span><span class="sxs-lookup"><span data-stu-id="e65fe-128">Step 1: Set up groups for supervision (optional)</span></span>

 <span data-ttu-id="e65fe-129">當您建立監督原則時，您會定義哪些人員已掃描其通訊，以及誰會執行評論。</span><span class="sxs-lookup"><span data-stu-id="e65fe-129">When you create a supervision policy, you define who has their communications scanned and who performs reviews.</span></span> <span data-ttu-id="e65fe-130">在原則中，您將使用電子郵件地址來識別個人或人員群組。</span><span class="sxs-lookup"><span data-stu-id="e65fe-130">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="e65fe-131">若要簡化您的設定，您可以為使用者建立群組，讓他們能夠掃描和群組其通訊。</span><span class="sxs-lookup"><span data-stu-id="e65fe-131">To simplify your setup, you can create groups for people who have their communication scanned and groups for people who review those communications.</span></span> <span data-ttu-id="e65fe-132">如果您正在使用群組，可能需要數個。</span><span class="sxs-lookup"><span data-stu-id="e65fe-132">If you're using groups, you may need several.</span></span> <span data-ttu-id="e65fe-133">例如，您想要監視兩個不同的使用者群組之間的通訊，或是想要指定不會受到監督的群組。</span><span class="sxs-lookup"><span data-stu-id="e65fe-133">For example, you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="e65fe-134">使用下列圖表可協助您設定組織中的通訊監管原則的群組：</span><span class="sxs-lookup"><span data-stu-id="e65fe-134">Use the following chart to help you configure groups in your organization for communication supervision policies:</span></span>

| <span data-ttu-id="e65fe-135">**原則成員**</span><span class="sxs-lookup"><span data-stu-id="e65fe-135">**Policy Member**</span></span> | <span data-ttu-id="e65fe-136">**支援的群組**</span><span class="sxs-lookup"><span data-stu-id="e65fe-136">**Supported Groups**</span></span> | <span data-ttu-id="e65fe-137">**不支援的群組**</span><span class="sxs-lookup"><span data-stu-id="e65fe-137">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="e65fe-138">監督的使用者</span><span class="sxs-lookup"><span data-stu-id="e65fe-138">Supervised users</span></span> <br> <span data-ttu-id="e65fe-139">非監督的使用者</span><span class="sxs-lookup"><span data-stu-id="e65fe-139">Non-supervised users</span></span> | <span data-ttu-id="e65fe-140">通訊群組</span><span class="sxs-lookup"><span data-stu-id="e65fe-140">Distribution groups</span></span> <br> <span data-ttu-id="e65fe-141">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="e65fe-141">Microsoft 365 groups</span></span> | <span data-ttu-id="e65fe-142">動態通訊群組</span><span class="sxs-lookup"><span data-stu-id="e65fe-142">Dynamic distribution groups</span></span> |
| <span data-ttu-id="e65fe-143">檢閱者</span><span class="sxs-lookup"><span data-stu-id="e65fe-143">Reviewers</span></span> | <span data-ttu-id="e65fe-144">擁有郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="e65fe-144">Mail-enabled security groups</span></span>  | <span data-ttu-id="e65fe-145">通訊群組</span><span class="sxs-lookup"><span data-stu-id="e65fe-145">Distribution groups</span></span> <br> <span data-ttu-id="e65fe-146">動態通訊群組</span><span class="sxs-lookup"><span data-stu-id="e65fe-146">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="e65fe-147">當您為監督的使用者選取 Microsoft 365 群組時，該原則會監控共用信箱的內容，以及與群組相關聯的 Microsoft 小組通道。</span><span class="sxs-lookup"><span data-stu-id="e65fe-147">When you select a Microsoft 365 group for supervised users, the policy monitors the content of the shared mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="e65fe-148">當您選取通訊群組清單時，該原則會監控個別的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="e65fe-148">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="e65fe-149">若要管理大型企業組織中的監督使用者，您可能需要跨大型群組監控所有使用者。</span><span class="sxs-lookup"><span data-stu-id="e65fe-149">To manage supervised users in large enterprise organizations, you may need to monitor all users across large groups.</span></span> <span data-ttu-id="e65fe-150">您可以使用 PowerShell 為指派的群組設定全域監督原則的通訊群組。</span><span class="sxs-lookup"><span data-stu-id="e65fe-150">You can use PowerShell to configure a distribution group for a global supervision policy for the assigned group.</span></span> <span data-ttu-id="e65fe-151">這可讓您以單一原則監控成千上萬的使用者，並在新員工加入您的組織時，維持監督原則的更新。</span><span class="sxs-lookup"><span data-stu-id="e65fe-151">This enables you to monitor thousands of users with a single policy and keep the supervision policy updated as new employees join your organization.</span></span>

1. <span data-ttu-id="e65fe-152">使用下列屬性，為全域監督原則建立專屬的[通訊群組](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)：請確定此通訊群組並未用於其他用途或其他 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="e65fe-152">Create a dedicated [distribution group](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) for your global supervision policy with the following properties: Make sure that this distribution group isn't used for other purposes or other Office 365 services.</span></span>

    - <span data-ttu-id="e65fe-153">**MemberDepartRestriction = 封閉式**。</span><span class="sxs-lookup"><span data-stu-id="e65fe-153">**MemberDepartRestriction = Closed**.</span></span> <span data-ttu-id="e65fe-154">確保使用者無法從通訊群組中移除自己。</span><span class="sxs-lookup"><span data-stu-id="e65fe-154">Ensures that users cannot remove themselves from the distribution group.</span></span>
    - <span data-ttu-id="e65fe-155">**MemberJoinRestriction = 封閉式**。</span><span class="sxs-lookup"><span data-stu-id="e65fe-155">**MemberJoinRestriction = Closed**.</span></span> <span data-ttu-id="e65fe-156">確保使用者無法將自己新增至通訊群組。</span><span class="sxs-lookup"><span data-stu-id="e65fe-156">Ensures that users cannot add themselves to the distribution group.</span></span>
    - <span data-ttu-id="e65fe-157">**ModerationEnabled = True**。</span><span class="sxs-lookup"><span data-stu-id="e65fe-157">**ModerationEnabled = True**.</span></span> <span data-ttu-id="e65fe-158">確定所有傳送至此群組的郵件都會受到核准，而且此群組並未用來在監督原則設定外進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e65fe-158">Ensures that all messages sent to this group are subject to approval and that the group is not being used to communicate outside of the supervision policy configuration.</span></span>

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. <span data-ttu-id="e65fe-159">選取未使用的[Exchange 自訂屬性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)，追蹤新增至組織中監管原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="e65fe-159">Select an unused [Exchange custom attribute](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) to track users added to the supervision policy in your organization.</span></span>

3. <span data-ttu-id="e65fe-160">在週期性排程上執行下列 PowerShell 腳本，將使用者新增至監管原則：</span><span class="sxs-lookup"><span data-stu-id="e65fe-160">Run the following PowerShell script on a recurring schedule to add users to the supervision policy:</span></span>

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

<span data-ttu-id="e65fe-161">如需設定群組的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="e65fe-161">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="e65fe-162">建立並管理通訊群組</span><span class="sxs-lookup"><span data-stu-id="e65fe-162">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="e65fe-163">管理啟用郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="e65fe-163">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="e65fe-164">Microsoft 365 群組的概述</span><span class="sxs-lookup"><span data-stu-id="e65fe-164">Overview of Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a><span data-ttu-id="e65fe-165">步驟2：讓監管可用於您的組織（必要）</span><span class="sxs-lookup"><span data-stu-id="e65fe-165">Step 2: Make supervision available in your organization (required)</span></span>

<span data-ttu-id="e65fe-166">若要讓**監督**成為安全 & 合規性中心的功能表選項，您必須獲指派主管審查系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="e65fe-166">To make **Supervision** available as a menu option in Security & Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="e65fe-167">若要這麼做，您可以將自己新增為主管審查角色群組的成員，也可以建立角色群組。</span><span class="sxs-lookup"><span data-stu-id="e65fe-167">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="e65fe-168">新增成員至主管審查角色群組</span><span class="sxs-lookup"><span data-stu-id="e65fe-168">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="e65fe-169">登入[https://protection.office.com](https://protection.office.com)在組織中使用管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="e65fe-169">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e65fe-170">在 [安全性 & 規範中心] 中，移至 [**許可權**]。</span><span class="sxs-lookup"><span data-stu-id="e65fe-170">In the Security & Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="e65fe-171">選取 [**主管審查**] 角色群組，然後按一下 [編輯] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e65fe-171">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="e65fe-172">在 [**成員**] 區段中，新增您要管理組織之通訊監督的人員。</span><span class="sxs-lookup"><span data-stu-id="e65fe-172">In the **Members** section, add the people who you want to manage communication supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="e65fe-173">建立新的角色群組</span><span class="sxs-lookup"><span data-stu-id="e65fe-173">Create a new role group</span></span>

1. <span data-ttu-id="e65fe-174">登入[https://protection.office.com/permissions](https://protection.office.com/permissions)在組織中使用管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="e65fe-174">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e65fe-175">在 [安全性 & 規範中心] 中，移至 [**許可權**]，**+** 然後按一下 [新增] （）。</span><span class="sxs-lookup"><span data-stu-id="e65fe-175">In the Security & Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="e65fe-176">在 [**角色**] 區段中，按一下**+**[新增] （），然後向下滾動至「**主管審查管理員**」。</span><span class="sxs-lookup"><span data-stu-id="e65fe-176">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**.</span></span> <span data-ttu-id="e65fe-177">將此角色新增至角色群組。</span><span class="sxs-lookup"><span data-stu-id="e65fe-177">Add this role to the role group.</span></span>

4. <span data-ttu-id="e65fe-178">在 [**成員**] 區段中，新增您要管理組織之通訊監督的人員。</span><span class="sxs-lookup"><span data-stu-id="e65fe-178">In the **Members** section, add the people who you want to manage communication supervision for your organization.</span></span>

<span data-ttu-id="e65fe-179">如需角色群組和權限的詳細資訊，請參閱[規範中心的權限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e65fe-179">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="e65fe-180">啟用檢閱者的遠端 PowerShell 存取（電子郵件主控于 Exchange Online）</span><span class="sxs-lookup"><span data-stu-id="e65fe-180">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="e65fe-181">遵循[啟用或停用 Exchange Online PowerShell 存取](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)的指導方針。</span><span class="sxs-lookup"><span data-stu-id="e65fe-181">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a><span data-ttu-id="e65fe-182">步驟3：建立自訂機密資訊類型及自訂關鍵字字典（選用）</span><span class="sxs-lookup"><span data-stu-id="e65fe-182">Step 3: Create custom sensitive information types and custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="e65fe-183">若要在監督原則嚮導中挑選現有的自訂敏感資訊類型或自訂關鍵字字典，您必須視需要建立這些專案。</span><span class="sxs-lookup"><span data-stu-id="e65fe-183">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-keyword-dictionarylexicon-optional"></a><span data-ttu-id="e65fe-184">建立自訂關鍵字字典/詞典（選用）</span><span class="sxs-lookup"><span data-stu-id="e65fe-184">Create custom keyword dictionary/lexicon (optional)</span></span>

<span data-ttu-id="e65fe-185">使用文字編輯器（例如記事本）來建立檔案，該檔案包含您想要在監管原則中監視的關鍵字字詞。</span><span class="sxs-lookup"><span data-stu-id="e65fe-185">Use a text editor (like Notepad), to create a file that includes the keyword terms you'd like to monitor in a supervision policy.</span></span> <span data-ttu-id="e65fe-186">請確定每個字詞都位於個別的一行，並以**Unicode/UTF-16 （小 Endian）** 格式儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="e65fe-186">Make sure that each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="e65fe-187">建立自訂機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="e65fe-187">Create custom sensitive information types</span></span>

1. <span data-ttu-id="e65fe-188">建立新的敏感資訊類型，並將您的自訂字典加入安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="e65fe-188">Create a new sensitive information type and add your custom dictionary in the Security & Compliance Center.</span></span> <span data-ttu-id="e65fe-189">流覽至 [**分類** \> **機密資訊類型**]，然後依照**新增的敏感資訊類型嚮導**中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="e65fe-189">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="e65fe-190">您將在這裡：</span><span class="sxs-lookup"><span data-stu-id="e65fe-190">Here you will:</span></span>

    - <span data-ttu-id="e65fe-191">定義敏感資訊類型的名稱和描述</span><span class="sxs-lookup"><span data-stu-id="e65fe-191">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="e65fe-192">定義鄰近性、信賴等級及主要模式元素</span><span class="sxs-lookup"><span data-stu-id="e65fe-192">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="e65fe-193">將您的自訂字典當作符合元素的需求匯入</span><span class="sxs-lookup"><span data-stu-id="e65fe-193">Import your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="e65fe-194">檢查您的選擇並建立機密資訊類型</span><span class="sxs-lookup"><span data-stu-id="e65fe-194">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="e65fe-195">如需詳細資訊，請參閱[建立自訂機密資訊類型](create-a-custom-sensitive-information-type.md)及[建立關鍵字字典](create-a-keyword-dictionary.md)</span><span class="sxs-lookup"><span data-stu-id="e65fe-195">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md) and [Create a keyword dictionary](create-a-keyword-dictionary.md)</span></span>

    <span data-ttu-id="e65fe-196">在建立自訂字典/詞典之後，您可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)指令程式來查看已設定的關鍵字，或是使用[DlpKeywordDictionary 指令程式](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)來新增及移除字詞。</span><span class="sxs-lookup"><span data-stu-id="e65fe-196">After the custom dictionary/lexicon is created, you can view the configured keywords with the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

## <a name="step-4-set-up-a-supervision-policy-required"></a><span data-ttu-id="e65fe-197">步驟4：設定監督原則（必要）</span><span class="sxs-lookup"><span data-stu-id="e65fe-197">Step 4: Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="e65fe-198">登入[https://protection.office.com](https://protection.office.com)在組織中使用管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="e65fe-198">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e65fe-199">在 [安全性 & 規範中心] 中，選取 [**監督**]。</span><span class="sxs-lookup"><span data-stu-id="e65fe-199">In the Security & Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="e65fe-200">選取 [**建立**]，然後依照嚮導設定原則設定。</span><span class="sxs-lookup"><span data-stu-id="e65fe-200">Select **Create** and follow the wizard to set up the policy configuration.</span></span> <span data-ttu-id="e65fe-201">使用此嚮導，您可以：</span><span class="sxs-lookup"><span data-stu-id="e65fe-201">Using the wizard, you will:</span></span>

    - <span data-ttu-id="e65fe-202">將原則命名為 [名稱] 和 [描述]。</span><span class="sxs-lookup"><span data-stu-id="e65fe-202">Give the policy a name and description.</span></span>
    - <span data-ttu-id="e65fe-203">選擇要監督的使用者或群組，包括選擇您想要排除的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="e65fe-203">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="e65fe-204">定義監督原則[條件](supervision-policies.md#ConditionalSettings)。</span><span class="sxs-lookup"><span data-stu-id="e65fe-204">Define the supervision policy [conditions](supervision-policies.md#ConditionalSettings).</span></span> <span data-ttu-id="e65fe-205">您可以選擇 [郵寄地址]、[關鍵字]、[檔案類型] 和 [大小相符] 條件。</span><span class="sxs-lookup"><span data-stu-id="e65fe-205">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="e65fe-206">選擇是否要包含機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="e65fe-206">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="e65fe-207">您可以在此選擇預設和自訂的機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="e65fe-207">This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="e65fe-208">選擇是否要啟用冒犯性語言模型。</span><span class="sxs-lookup"><span data-stu-id="e65fe-208">Choose if you'd like to enable the offensive language model.</span></span> <span data-ttu-id="e65fe-209">這會偵測到電子郵件內送出或接收到不適當的語言。</span><span class="sxs-lookup"><span data-stu-id="e65fe-209">This detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="e65fe-210">定義要複查的通訊百分比。</span><span class="sxs-lookup"><span data-stu-id="e65fe-210">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="e65fe-211">選擇原則的檢閱者。</span><span class="sxs-lookup"><span data-stu-id="e65fe-211">Choose the reviewers for the policy.</span></span> <span data-ttu-id="e65fe-212">檢閱者可以是個別的使用者或擁有[郵件功能的安全性群組](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="e65fe-212">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="e65fe-213">所有檢閱者都必須在 Exchange Online 上主控信箱。</span><span class="sxs-lookup"><span data-stu-id="e65fe-213">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="e65fe-214">檢查您的原則選擇並建立原則。</span><span class="sxs-lookup"><span data-stu-id="e65fe-214">Review your policy selections and create the policy.</span></span>

## <a name="step-5-test-your-supervision-policy-optional"></a><span data-ttu-id="e65fe-215">步驟5：測試您的監管原則（選用）</span><span class="sxs-lookup"><span data-stu-id="e65fe-215">Step 5: Test your supervision policy (optional)</span></span>

<span data-ttu-id="e65fe-216">在您建立通訊監督原則之後，建議您測試，以確定原則已正確地強制執行您所定義的條件。</span><span class="sxs-lookup"><span data-stu-id="e65fe-216">After you create a communication supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="e65fe-217">您也可以在您的監管原則包括機密資訊類型時，[測試您的資料遺失防護（DLP）原則](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="e65fe-217">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types.</span></span> <span data-ttu-id="e65fe-218">請遵循下列步驟來測試您的監管原則：</span><span class="sxs-lookup"><span data-stu-id="e65fe-218">Follow these steps to test your supervision policy:</span></span>

1. <span data-ttu-id="e65fe-219">開啟以您想要測試之原則中所定義之監督使用者的身分登入電子郵件客戶程式或 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="e65fe-219">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="e65fe-220">傳送電子郵件或 Microsoft 小組聊天，其符合您在監管原則中所定義的準則。</span><span class="sxs-lookup"><span data-stu-id="e65fe-220">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy.</span></span> <span data-ttu-id="e65fe-221">這可以是關鍵字、附件大小、網域等等。確定您決定原則中設定的設定條件設定過於嚴格，還是過於 lenient。</span><span class="sxs-lookup"><span data-stu-id="e65fe-221">This can be a keyword, attachment size, domain, etc. Make sure that you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    >[!NOTE]
    ><span data-ttu-id="e65fe-222">已定義原則的電子郵件會在近期即時處理，而且在設定原則之後可立即進行測試。</span><span class="sxs-lookup"><span data-stu-id="e65fe-222">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured.</span></span> <span data-ttu-id="e65fe-223">Microsoft 小組中的聊天可能需要長達24小時才能完全處理原則。</span><span class="sxs-lookup"><span data-stu-id="e65fe-223">Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="e65fe-224">以通訊監督原則中指定的檢閱者身分登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e65fe-224">Log into Microsoft 365 as a reviewer designated in the communication supervision policy.</span></span> <span data-ttu-id="e65fe-225">流覽至 [**監察** > ]*您的自訂原則* > **開啟**以查看原則的報告。</span><span class="sxs-lookup"><span data-stu-id="e65fe-225">Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

