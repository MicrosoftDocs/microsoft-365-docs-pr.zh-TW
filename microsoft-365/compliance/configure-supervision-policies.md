---
title: 為您的組織設定監督原則
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
description: 设置监督审核策略，以捕获员工通信以进行审核。
ms.openlocfilehash: ccbc5897ef8c6fb6018793ff7e3fe7731ee14710
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076612"
---
# <a name="configure-supervision-policies-for-your-organization"></a><span data-ttu-id="90f1f-103">為您的組織設定監督原則</span><span class="sxs-lookup"><span data-stu-id="90f1f-103">Configure supervision policies for your organization</span></span>

<span data-ttu-id="90f1f-104">使用监督策略捕获员工通信，供内部或外部审阅者检查。</span><span class="sxs-lookup"><span data-stu-id="90f1f-104">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="90f1f-105">有关监督策略如何帮助您监视组织中的通信的详细信息，请参阅[Office 365 中的"监督策略"。](supervision-policies.md)</span><span class="sxs-lookup"><span data-stu-id="90f1f-105">For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="90f1f-106">受监督策略监视的用户必须具有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证，或者包含在 Office 365 企业版 E5 订阅中。</span><span class="sxs-lookup"><span data-stu-id="90f1f-106">Users monitored by supervision policies must have either a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription.</span></span>
> <span data-ttu-id="90f1f-107">如果您没有现有的企业 E5 计划，并且想要尝试监督，则可以注册 Office [365 企业版 E5 的试用版。](https://go.microsoft.com/fwlink/p/?LinkID=698279)</span><span class="sxs-lookup"><span data-stu-id="90f1f-107">If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="90f1f-108">按照以下步骤在 Office 365 组织中设置和使用监督：</span><span class="sxs-lookup"><span data-stu-id="90f1f-108">Follow these steps to set up and use supervision in your Office 365 organization:</span></span>
  
- <span data-ttu-id="90f1f-109">**第 1 步（可选）：**[设置监督组](#step-1-set-up-groups-for-supervision-optional)</span><span class="sxs-lookup"><span data-stu-id="90f1f-109">**Step 1 (optional)**: [Set up groups for Supervision](#step-1-set-up-groups-for-supervision-optional)</span></span> 

    <span data-ttu-id="90f1f-110">在开始使用监督之前，请确定谁需要审核通信以及谁执行审核。</span><span class="sxs-lookup"><span data-stu-id="90f1f-110">Before you start using supervision, determine who needs communications reviewed and who performs reviews.</span></span> <span data-ttu-id="90f1f-111">如果你想开始与几个用户，看看监督是如何工作的，你可以跳过设置组现在。</span><span class="sxs-lookup"><span data-stu-id="90f1f-111">If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="90f1f-112">**第 2 步（必需）：**[在组织中提供监督](#step-2-make-supervision-available-in-your-organization-required)</span><span class="sxs-lookup"><span data-stu-id="90f1f-112">**Step 2 (required)**: [Make supervision available in your organization](#step-2-make-supervision-available-in-your-organization-required)</span></span>

    <span data-ttu-id="90f1f-113">将自己添加到"监督审核"角色组，以便可以设置策略。</span><span class="sxs-lookup"><span data-stu-id="90f1f-113">Add yourself to the Supervisory Review role group so you can set up policies.</span></span> <span data-ttu-id="90f1f-114">分配了此角色的任何人都可以访问合规中心**中的"监督"** 页面。</span><span class="sxs-lookup"><span data-stu-id="90f1f-114">Anyone who has this role assigned can access the **Supervision** page in the Compliance Center.</span></span> <span data-ttu-id="90f1f-115">如果可审阅的电子邮件托管在 Exchange 在线上，则每个审阅者必须具有[对 Exchange 在线的远程 PowerShell 访问权限。](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="90f1f-115">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="90f1f-116">**步骤 3（可选）：**[创建自定义敏感信息类型和自定义关键字字典](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span><span class="sxs-lookup"><span data-stu-id="90f1f-116">**Step 3 (optional)**: [Create custom sensitive information types and custom keyword dictionaries](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span></span>

    <span data-ttu-id="90f1f-117">如果您需要自定义敏感信息类型或自定义关键字字典作为监督策略，则需要在启动监督向导之前创建它。</span><span class="sxs-lookup"><span data-stu-id="90f1f-117">If you need a custom sensitive info type or a custom keyword dictionary for your supervision policy, you need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="90f1f-118">**第 4 步（必）：**[设置监督政策](#step-4-set-up-a-supervision-policy-required)</span><span class="sxs-lookup"><span data-stu-id="90f1f-118">**Step 4 (required)**: [Set up a supervision policy](#step-4-set-up-a-supervision-policy-required)</span></span>

    <span data-ttu-id="90f1f-119">您可以在合规中心创建监督策略。</span><span class="sxs-lookup"><span data-stu-id="90f1f-119">You create supervision policies in the Compliance Center.</span></span> <span data-ttu-id="90f1f-120">这些策略定义组织中哪些通信需要审核，并指定执行审核的人员。</span><span class="sxs-lookup"><span data-stu-id="90f1f-120">These policies define which communications are subject to review in your organization and specifies who performs reviews.</span></span> <span data-ttu-id="90f1f-121">通信包括电子邮件和 Microsoft 团队通信以及第三方平台通信（如 Facebook、Twitter 等）</span><span class="sxs-lookup"><span data-stu-id="90f1f-121">Communications include email and Microsoft Teams communications, and 3rd-party platform communications (such as Facebook, Twitter, etc.)</span></span>

- <span data-ttu-id="90f1f-122">**第 5 步（可选）：**[测试您的监督策略](#step-5-test-your-supervision-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="90f1f-122">**Step 5 (optional)**: [Test your supervision policy](#step-5-test-your-supervision-policy-optional)</span></span>

    <span data-ttu-id="90f1f-123">测试您的监督策略，以确保其按预期运行。</span><span class="sxs-lookup"><span data-stu-id="90f1f-123">Test your supervision policy to make sure it functions as desired.</span></span> <span data-ttu-id="90f1f-124">请务必确保您的合规战略符合您的标准。</span><span class="sxs-lookup"><span data-stu-id="90f1f-124">It is important to ensure that your compliance strategy is meeting your standards.</span></span>

- <span data-ttu-id="90f1f-125">**步骤 6（可选）：**[为不想使用 Office 365 监督仪表板的审阅者配置 Outlook 以审阅受监督的通信](#step-6-configure-outlook-for-reviewers-optional)</span><span class="sxs-lookup"><span data-stu-id="90f1f-125">**Step 6 (optional)**: [Configure Outlook for reviewers who do not want to use Office 365 supervision dashboard to review supervised communications](#step-6-configure-outlook-for-reviewers-optional)</span></span>

    <span data-ttu-id="90f1f-126">配置 Outlook 以允许审阅者访问 Outlook 客户端中的监督功能，以便他们可以评估和分类每个项目。</span><span class="sxs-lookup"><span data-stu-id="90f1f-126">Configure Outlook to give reviewers access to the supervision functionality within the Outlook client so they can assess and categorize each item.</span></span>

## <a name="step-1-set-up-groups-for-supervision-optional"></a><span data-ttu-id="90f1f-127">第 1 步：设置监督组（可选）</span><span class="sxs-lookup"><span data-stu-id="90f1f-127">Step 1: Set up groups for Supervision (optional)</span></span>

 <span data-ttu-id="90f1f-128">创建监督策略时，您可以定义谁审阅了他们的通信，谁执行审核。</span><span class="sxs-lookup"><span data-stu-id="90f1f-128">When you create a supervision policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="90f1f-129">在策略中，您将使用电子邮件地址来标识个人或组。</span><span class="sxs-lookup"><span data-stu-id="90f1f-129">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="90f1f-130">为了简化您的设置，您可以为审核其通信的人员创建组，并为审阅这些通信的人员创建组。</span><span class="sxs-lookup"><span data-stu-id="90f1f-130">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="90f1f-131">如果您使用的是组，则可能需要多个组。</span><span class="sxs-lookup"><span data-stu-id="90f1f-131">If you're using groups, you may need several.</span></span> <span data-ttu-id="90f1f-132">例如，您希望监视两个不同的人员组之间的通信，或者如果要指定一个不受监督的组。</span><span class="sxs-lookup"><span data-stu-id="90f1f-132">For example, you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="90f1f-133">使用以下图表帮助您在组织中配置组以进行监督策略：</span><span class="sxs-lookup"><span data-stu-id="90f1f-133">Use the following chart to help you configure groups in your organization for supervision policies:</span></span>

| <span data-ttu-id="90f1f-134">**政策成员**</span><span class="sxs-lookup"><span data-stu-id="90f1f-134">**Policy Member**</span></span> | <span data-ttu-id="90f1f-135">**支持的组**</span><span class="sxs-lookup"><span data-stu-id="90f1f-135">**Supported Groups**</span></span> | <span data-ttu-id="90f1f-136">**不支持的组**</span><span class="sxs-lookup"><span data-stu-id="90f1f-136">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="90f1f-137">受监督的用户</span><span class="sxs-lookup"><span data-stu-id="90f1f-137">Supervised users</span></span> <br> <span data-ttu-id="90f1f-138">非监督用户</span><span class="sxs-lookup"><span data-stu-id="90f1f-138">Non-supervised users</span></span> | <span data-ttu-id="90f1f-139">通訊群組</span><span class="sxs-lookup"><span data-stu-id="90f1f-139">Distribution groups</span></span> <br> <span data-ttu-id="90f1f-140">Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="90f1f-140">Office 365 groups</span></span> | <span data-ttu-id="90f1f-141">動態通訊群組</span><span class="sxs-lookup"><span data-stu-id="90f1f-141">Dynamic distribution groups</span></span> |
| <span data-ttu-id="90f1f-142">檢閱者</span><span class="sxs-lookup"><span data-stu-id="90f1f-142">Reviewers</span></span> | <span data-ttu-id="90f1f-143">擁有郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="90f1f-143">Mail-enabled security groups</span></span>  | <span data-ttu-id="90f1f-144">通訊群組</span><span class="sxs-lookup"><span data-stu-id="90f1f-144">Distribution groups</span></span> <br> <span data-ttu-id="90f1f-145">動態通訊群組</span><span class="sxs-lookup"><span data-stu-id="90f1f-145">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="90f1f-146">当您为受监督的用户选择 Office 365 组时，策略将监视共享 Office 365 邮箱和与该组关联的 Microsoft Teams 通道的内容。</span><span class="sxs-lookup"><span data-stu-id="90f1f-146">When you select an Office 365 group for supervised users, the policy monitors the content of the shared Office 365 mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="90f1f-147">选择通讯组列表时，策略将监视各个用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="90f1f-147">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="90f1f-148">要管理大型企业组织中受监督的用户，您可能需要监视大型组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="90f1f-148">To manage supervised users in large enterprise organizations, you may need to monitor all users across large groups.</span></span> <span data-ttu-id="90f1f-149">您可以使用 PowerShell 为分配的组配置全局监督策略的通讯组。</span><span class="sxs-lookup"><span data-stu-id="90f1f-149">You can use PowerShell to configure a distribution group for a global supervision policy for the assigned group.</span></span> <span data-ttu-id="90f1f-150">这使您能够使用单个策略监视数千个用户，并在新员工加入您的组织时更新监督策略。</span><span class="sxs-lookup"><span data-stu-id="90f1f-150">This enables you to monitor thousands of users with a single policy and keep the supervision policy updated as new employees join your organization.</span></span>

1. <span data-ttu-id="90f1f-151">使用以下属性为全局监督策略创建专用[通讯组：](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)确保此通讯组未用于其他目的或其他 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="90f1f-151">Create a dedicated [distribution group](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) for your global supervision policy with the following properties: Make sure that this distribution group isn't used for other purposes or other Office 365 services.</span></span>

    - <span data-ttu-id="90f1f-152">**成员分类限制 = 已关闭**。</span><span class="sxs-lookup"><span data-stu-id="90f1f-152">**MemberDepartRestriction = Closed**.</span></span> <span data-ttu-id="90f1f-153">确保用户无法从通讯组中删除自己。</span><span class="sxs-lookup"><span data-stu-id="90f1f-153">Ensures that users cannot remove themselves from the distribution group.</span></span>
    - <span data-ttu-id="90f1f-154">**成员联接限制 = 已关闭**。</span><span class="sxs-lookup"><span data-stu-id="90f1f-154">**MemberJoinRestriction = Closed**.</span></span> <span data-ttu-id="90f1f-155">确保用户无法将自己添加到通讯组。</span><span class="sxs-lookup"><span data-stu-id="90f1f-155">Ensures that users cannot add themselves to the distribution group.</span></span>
    - <span data-ttu-id="90f1f-156">**启用调节 = True**。</span><span class="sxs-lookup"><span data-stu-id="90f1f-156">**ModerationEnabled = True**.</span></span> <span data-ttu-id="90f1f-157">确保发送到此组的所有邮件都需获得批准，并且该组不用于在监督策略配置之外进行通信。</span><span class="sxs-lookup"><span data-stu-id="90f1f-157">Ensures that all messages sent to this group are subject to approval and that the group is not being used to communicate outside of the supervision policy configuration.</span></span>

    ```
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```
2. <span data-ttu-id="90f1f-158">选择未使用的[Exchange 自定义属性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)以跟踪添加到组织中监督策略的用户。</span><span class="sxs-lookup"><span data-stu-id="90f1f-158">Select an unused [Exchange custom attribute](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) to track users added to the supervision policy in your organization.</span></span>

3. <span data-ttu-id="90f1f-159">定期运行以下 PowerShell 脚本，将用户添加到监督策略：</span><span class="sxs-lookup"><span data-stu-id="90f1f-159">Run the following PowerShell script on a recurring schedule to add users to the supervision policy:</span></span>

    ```
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

<span data-ttu-id="90f1f-160">有关设置组的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="90f1f-160">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="90f1f-161">建立並管理通訊群組</span><span class="sxs-lookup"><span data-stu-id="90f1f-161">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="90f1f-162">管理啟用郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="90f1f-162">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="90f1f-163">Office 365 组概述</span><span class="sxs-lookup"><span data-stu-id="90f1f-163">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a><span data-ttu-id="90f1f-164">第 2 步：在组织中提供监督（必需）</span><span class="sxs-lookup"><span data-stu-id="90f1f-164">Step 2: Make supervision available in your organization (required)</span></span>

<span data-ttu-id="90f1f-165">要使"**监督"** 在合规中心中作为菜单选项可用，您必须分配监督审核管理员角色。</span><span class="sxs-lookup"><span data-stu-id="90f1f-165">To make **Supervision** available as a menu option in the Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="90f1f-166">为此，您可以将自己添加为"监督审核"角色组的成员，也可以创建角色组。</span><span class="sxs-lookup"><span data-stu-id="90f1f-166">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="90f1f-167">将成员添加到监督审核角色组</span><span class="sxs-lookup"><span data-stu-id="90f1f-167">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="90f1f-168">使用[https://protection.office.com](https://protection.office.com)Office 365 组织中的管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="90f1f-168">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="90f1f-169">在合规中心，**转到"权限"。**</span><span class="sxs-lookup"><span data-stu-id="90f1f-169">In the Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="90f1f-170">选择"**监督审阅"** 角色组，然后单击"编辑"图标。</span><span class="sxs-lookup"><span data-stu-id="90f1f-170">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="90f1f-171">在"**成员"** 部分中，添加要管理组织监督的人员。</span><span class="sxs-lookup"><span data-stu-id="90f1f-171">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="90f1f-172">创建新角色组</span><span class="sxs-lookup"><span data-stu-id="90f1f-172">Create a new role group</span></span>

1. <span data-ttu-id="90f1f-173">使用[https://protection.office.com](https://protection.office.com)Office 365 组织中的管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="90f1f-173">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="90f1f-174">在合规性中心中，**转到"权限"，** 然后单击"添加**+**（ ）。</span><span class="sxs-lookup"><span data-stu-id="90f1f-174">In the Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="90f1f-175">在"**角色"** 部分中，单击"添加 （**+**）"并向下滚动**到"监督审阅管理员"。**</span><span class="sxs-lookup"><span data-stu-id="90f1f-175">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**.</span></span> <span data-ttu-id="90f1f-176">将此角色添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="90f1f-176">Add this role to the role group.</span></span>

4. <span data-ttu-id="90f1f-177">在"**成员"** 部分中，添加要管理组织监督的人员。</span><span class="sxs-lookup"><span data-stu-id="90f1f-177">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

<span data-ttu-id="90f1f-178">有关角色组和权限的详细信息，请参阅[合规性中心的权限。](../security/office-365-security/protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="90f1f-178">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="90f1f-179">为审阅者启用远程 PowerShell 访问权限（如果电子邮件托管在 Exchange 在线上）</span><span class="sxs-lookup"><span data-stu-id="90f1f-179">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="90f1f-180">[按照"启用"或"禁用对 Exchange 在线电源外壳 "中的访问权限](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指导操作。</span><span class="sxs-lookup"><span data-stu-id="90f1f-180">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a><span data-ttu-id="90f1f-181">步骤 3：创建自定义敏感信息类型和自定义关键字字典（可选）</span><span class="sxs-lookup"><span data-stu-id="90f1f-181">Step 3: Create custom sensitive information types and custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="90f1f-182">为了从监管策略向导中现有的自定义敏感信息类型或自定义关键字字典中进行选择，首先需要根据需要创建这些项目。</span><span class="sxs-lookup"><span data-stu-id="90f1f-182">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-keyword-dictionarylexicon-optional"></a><span data-ttu-id="90f1f-183">创建自定义关键字词典/词典（可选）</span><span class="sxs-lookup"><span data-stu-id="90f1f-183">Create custom keyword dictionary/lexicon (optional)</span></span>

<span data-ttu-id="90f1f-184">使用文本编辑器（如记事本）创建包含要在监督策略中监视的关键字字词的文件。</span><span class="sxs-lookup"><span data-stu-id="90f1f-184">Use a text editor (like Notepad), to create a file that includes the keyword terms you'd like to monitor in a supervision policy.</span></span> <span data-ttu-id="90f1f-185">确保每个术语都位于单独的行上，并将文件以**Unicode/UTF-16（小 Endian）** 格式保存。</span><span class="sxs-lookup"><span data-stu-id="90f1f-185">Make sure that each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="90f1f-186">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="90f1f-186">Create custom sensitive information types</span></span>

1. <span data-ttu-id="90f1f-187">创建新的敏感信息类型，并在 Office 365 安全&合规性中心中添加自定义词典。</span><span class="sxs-lookup"><span data-stu-id="90f1f-187">Create a new sensitive information type and add your custom dictionary in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="90f1f-188">导航到**分类**\>**敏感信息类型，** 并**按照"新建敏感信息类型"向导**中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="90f1f-188">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="90f1f-189">在这里，您将：</span><span class="sxs-lookup"><span data-stu-id="90f1f-189">Here you will:</span></span>

    - <span data-ttu-id="90f1f-190">定义敏感信息类型的名称和说明</span><span class="sxs-lookup"><span data-stu-id="90f1f-190">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="90f1f-191">定义邻近度、置信度和主要模式元素</span><span class="sxs-lookup"><span data-stu-id="90f1f-191">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="90f1f-192">将自定义字典作为匹配元素的要求导入</span><span class="sxs-lookup"><span data-stu-id="90f1f-192">Import your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="90f1f-193">查看您的选择并创建敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="90f1f-193">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="90f1f-194">有关详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)和[创建关键字字典](create-a-keyword-dictionary.md)</span><span class="sxs-lookup"><span data-stu-id="90f1f-194">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md) and [Create a keyword dictionary](create-a-keyword-dictionary.md)</span></span>

    <span data-ttu-id="90f1f-195">创建自定义词典/词典后，您可以使用[Get-DlpKeyword](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)字典 cmdlet 查看已配置的关键字，或使用[Set-DlpKeyword 字典](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)cmdlet 添加和删除术语。</span><span class="sxs-lookup"><span data-stu-id="90f1f-195">After the custom dictionary/lexicon is created, you can view the configured keywords with the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

## <a name="step-4-set-up-a-supervision-policy-required"></a><span data-ttu-id="90f1f-196">第 4 步：设置监督策略（必需）</span><span class="sxs-lookup"><span data-stu-id="90f1f-196">Step 4: Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="90f1f-197">使用[https://protection.office.com](https://protection.office.com)Office 365 组织中的管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="90f1f-197">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="90f1f-198">在合规中心中，**选择"监督"。**</span><span class="sxs-lookup"><span data-stu-id="90f1f-198">In the Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="90f1f-199">**选择"创建"** 并按照向导设置策略配置。</span><span class="sxs-lookup"><span data-stu-id="90f1f-199">Select **Create** and follow the wizard to set up the policy configuration.</span></span> <span data-ttu-id="90f1f-200">使用向导，您将：</span><span class="sxs-lookup"><span data-stu-id="90f1f-200">Using the wizard, you will:</span></span>

    - <span data-ttu-id="90f1f-201">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="90f1f-201">Give the policy a name and description.</span></span>
    - <span data-ttu-id="90f1f-202">选择要监督的用户或组，包括选择要排除的用户或组。</span><span class="sxs-lookup"><span data-stu-id="90f1f-202">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="90f1f-203">定义监督政策[条件。](supervision-policies.md#ConditionalSettings)</span><span class="sxs-lookup"><span data-stu-id="90f1f-203">Define the supervision policy [conditions](supervision-policies.md#ConditionalSettings).</span></span> <span data-ttu-id="90f1f-204">您可以从消息地址、关键字、文件类型和大小匹配条件中进行选择。</span><span class="sxs-lookup"><span data-stu-id="90f1f-204">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="90f1f-205">选择是否希望包含敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="90f1f-205">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="90f1f-206">您可以在其中选择默认和自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="90f1f-206">This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="90f1f-207">选择是否要启用攻击性语言模型。</span><span class="sxs-lookup"><span data-stu-id="90f1f-207">Choose if you'd like to enable the offensive language model.</span></span> <span data-ttu-id="90f1f-208">这将检测电子邮件正文中发送或接收的不当语言。</span><span class="sxs-lookup"><span data-stu-id="90f1f-208">This detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="90f1f-209">定义要审阅的通信的百分比。</span><span class="sxs-lookup"><span data-stu-id="90f1f-209">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="90f1f-210">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="90f1f-210">Choose the reviewers for the policy.</span></span> <span data-ttu-id="90f1f-211">审阅者可以是单个用户或[已启用邮件的安全组。](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)</span><span class="sxs-lookup"><span data-stu-id="90f1f-211">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="90f1f-212">所有审阅者都必须在 Exchange 联机上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="90f1f-212">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="90f1f-213">查看策略选择并创建策略。</span><span class="sxs-lookup"><span data-stu-id="90f1f-213">Review your policy selections and create the policy.</span></span>

## <a name="step-5-test-your-supervision-policy-optional"></a><span data-ttu-id="90f1f-214">第 5 步：测试您的监督策略（可选）</span><span class="sxs-lookup"><span data-stu-id="90f1f-214">Step 5: Test your supervision policy (optional)</span></span>

<span data-ttu-id="90f1f-215">创建监督策略后，最好进行测试，以确保策略正确执行所定义的条件。</span><span class="sxs-lookup"><span data-stu-id="90f1f-215">After you create a supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="90f1f-216">如果监管策略包含敏感信息类型，您可能还需要[测试数据丢失防护 （DLP） 策略。](create-test-tune-dlp-policy.md)</span><span class="sxs-lookup"><span data-stu-id="90f1f-216">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types.</span></span> <span data-ttu-id="90f1f-217">请按照以下步骤测试您的监督策略：</span><span class="sxs-lookup"><span data-stu-id="90f1f-217">Follow these steps to test your supervision policy:</span></span>

1. <span data-ttu-id="90f1f-218">打开电子邮件客户端或 Microsoft Teams 以要测试的策略中定义的受监督用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="90f1f-218">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="90f1f-219">发送电子邮件或 Microsoft 团队聊天，满足您在监督策略中定义的条件。</span><span class="sxs-lookup"><span data-stu-id="90f1f-219">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy.</span></span> <span data-ttu-id="90f1f-220">这可以是关键字、附件大小、域等。请确保确定策略中配置的条件设置是否过于严格或过于宽松。</span><span class="sxs-lookup"><span data-stu-id="90f1f-220">This can be a keyword, attachment size, domain, etc. Make sure that you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!Note]
    > <span data-ttu-id="90f1f-221">受定义策略约束的电子邮件将近乎实时地处理，并在策略配置后立即进行测试。</span><span class="sxs-lookup"><span data-stu-id="90f1f-221">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured.</span></span> <span data-ttu-id="90f1f-222">Microsoft Teams 中的聊天最多可能需要 24 小时才能在策略中完全处理。</span><span class="sxs-lookup"><span data-stu-id="90f1f-222">Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="90f1f-223">作为监督策略中指定的审阅者登录到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="90f1f-223">Log into your Office 365 tenant as a reviewer designated in the supervision policy.</span></span> <span data-ttu-id="90f1f-224">导航**到"监督** > *自定义策略* > **打开"** 以查看策略的报告。</span><span class="sxs-lookup"><span data-stu-id="90f1f-224">Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

## <a name="step-6-configure-outlook-for-reviewers-optional"></a><span data-ttu-id="90f1f-225">步骤 6：为审阅者配置 Outlook（可选）</span><span class="sxs-lookup"><span data-stu-id="90f1f-225">Step 6: Configure Outlook for reviewers (optional)</span></span>

<span data-ttu-id="90f1f-226">想要使用 Outlook 而不是 Office 365 中的"监督"仪表板来审阅通信的审阅者必须配置其 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="90f1f-226">Reviewers that want to use Outlook instead of the Supervision dashboard in Office 365 to review communications must configure their Outlook client.</span></span>

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="90f1f-227">第 1 步：复制监督邮箱的地址</span><span class="sxs-lookup"><span data-stu-id="90f1f-227">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="90f1f-228">要配置 Outlook 桌面的审阅，您需要作为监督策略设置的一部分创建的监督邮箱的地址。</span><span class="sxs-lookup"><span data-stu-id="90f1f-228">To configure review for Outlook desktop, you need the address for the supervision mailbox created as part of the supervision policy setup.</span></span>
  
> [!NOTE]
> <span data-ttu-id="90f1f-229">如果其他人创建了该策略，则需要从他们那里获得此地址才能安装外接程序。</span><span class="sxs-lookup"><span data-stu-id="90f1f-229">If someone else created the policy, you need to get this address from them to install the add-in.</span></span>

<span data-ttu-id="90f1f-230">**查找监督邮箱地址**</span><span class="sxs-lookup"><span data-stu-id="90f1f-230">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="90f1f-231">使用组织中管理员帐户的凭据登录到[合规性中心。](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="90f1f-231">Sign into the [Compliance Center](https://compliance.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="90f1f-232">转到**监督**。</span><span class="sxs-lookup"><span data-stu-id="90f1f-232">Go to **Supervision**.</span></span>

3. <span data-ttu-id="90f1f-233">为要查看的通信选择监督策略。</span><span class="sxs-lookup"><span data-stu-id="90f1f-233">Select a supervision policy for the communications you want to review.</span></span>

4. <span data-ttu-id="90f1f-234">在策略详细信息弹出窗口中，**在"监督邮箱"** 下，复制地址。</span><span class="sxs-lookup"><span data-stu-id="90f1f-234">In the policy details flyout, under **Supervision mailbox**, copy the address.</span></span><br/><span data-ttu-id="90f1f-235">![监督政策详细信息的"监督邮箱"部分弹出窗口显示突出显示的监督邮箱地址](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span><span class="sxs-lookup"><span data-stu-id="90f1f-235">![The 'Supervision Mailbox' section of a supervision policy's details flyout showing the supervision mailbox address highlighted](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span></span>
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-access"></a><span data-ttu-id="90f1f-236">第 2 步：为 Outlook 访问配置监督邮箱</span><span class="sxs-lookup"><span data-stu-id="90f1f-236">Step 2: Configure the supervision mailbox for Outlook access</span></span>

<span data-ttu-id="90f1f-237">接下来，审阅者需要运行几个 Exchange 联机 PowerShell 命令，以便他们可以将 Outlook 连接到监督邮箱。</span><span class="sxs-lookup"><span data-stu-id="90f1f-237">Next, reviewers need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="90f1f-238">連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="90f1f-238">Connect to Exchange Online PowerShell.</span></span> [<span data-ttu-id="90f1f-239">該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="90f1f-239">How do I do this?</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. <span data-ttu-id="90f1f-240">运行以下命令，*其中SupervisoryReview{GUID}@domain.onmicrosoft.com*是您在上述步骤 1 中复制的地址，*而"用户"* 是将连接到步骤 3 中的监督邮箱的审阅者的名称。</span><span class="sxs-lookup"><span data-stu-id="90f1f-240">Run the following commands, where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will connect to the supervision mailbox in Step 3.</span></span>

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. <span data-ttu-id="90f1f-241">请等待至少一个小时，然后再继续执行步骤 3。</span><span class="sxs-lookup"><span data-stu-id="90f1f-241">Wait at least an hour before moving on to Step 3.</span></span>

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="90f1f-242">步骤 3：创建 Outlook 配置文件以连接到监督邮箱</span><span class="sxs-lookup"><span data-stu-id="90f1f-242">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="90f1f-243">对于最后一步，审阅者需要创建 Outlook 配置文件以连接到监督邮箱。</span><span class="sxs-lookup"><span data-stu-id="90f1f-243">For the final step, reviewers need to create an Outlook profile to connect to the supervision mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="90f1f-244">要创建新的 Outlook 配置文件，您将在 Windows 控制面板中使用"邮件"设置。</span><span class="sxs-lookup"><span data-stu-id="90f1f-244">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel.</span></span> <span data-ttu-id="90f1f-245">您访问这些设置的路径可能取决于您使用的 Windows 操作系统（Windows 7、Windows 8 或 Windows 10）以及安装的 Outlook 版本。</span><span class="sxs-lookup"><span data-stu-id="90f1f-245">The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using, and which version of Outlook is installed.</span></span>
  
1. <span data-ttu-id="90f1f-246">打开控制面板。</span><span class="sxs-lookup"><span data-stu-id="90f1f-246">Open the Control Panel.</span></span> <span data-ttu-id="90f1f-247">在窗口顶部**的"搜索"** 框中，**键入"邮件"。**</span><span class="sxs-lookup"><span data-stu-id="90f1f-247">In the **Search** box at the top of the window, type **Mail**.</span></span><br/><span data-ttu-id="90f1f-248">（不确定如何进入控制面板？</span><span class="sxs-lookup"><span data-stu-id="90f1f-248">(Not sure how to get to the Control Panel?</span></span> <span data-ttu-id="90f1f-249">请参阅[控制面板在哪里？）](https://support.microsoft.com/help/13764/windows-where-is-control-panel)</span><span class="sxs-lookup"><span data-stu-id="90f1f-249">See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span></span>
  
2. <span data-ttu-id="90f1f-250">打开"**邮件"** 应用。</span><span class="sxs-lookup"><span data-stu-id="90f1f-250">Open the **Mail** app.</span></span>

3. <span data-ttu-id="90f1f-251">在**邮件设置 - Outlook**中，**单击"显示配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="90f1f-251">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span><br/><span data-ttu-id="90f1f-252">![突出显示"显示配置文件"按钮的"邮件设置 - Outlook"对话框](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span><span class="sxs-lookup"><span data-stu-id="90f1f-252">![The 'Mail Setup - Outlook' dialog box with the 'Show Profiles' button highlighted](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span></span>
  
4. <span data-ttu-id="90f1f-253">**在"邮件"** 中，**单击"添加"。**</span><span class="sxs-lookup"><span data-stu-id="90f1f-253">In **Mail**, click **Add**.</span></span> <span data-ttu-id="90f1f-254">然后，**在新配置文件**中，输入监督邮箱的名称（如**监督**）。</span><span class="sxs-lookup"><span data-stu-id="90f1f-254">Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span><br/><span data-ttu-id="90f1f-255">!["配置文件名称"框中显示名称"新配置文件"对话框](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span><span class="sxs-lookup"><span data-stu-id="90f1f-255">![The 'New Profile' dialog showing the name 'Supervision' in the 'Profile Name' box](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span></span>
  
5. <span data-ttu-id="90f1f-256">在**将 Outlook 连接到 Office 365**中，**单击"连接到其他帐户"。**</span><span class="sxs-lookup"><span data-stu-id="90f1f-256">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span><br/><span data-ttu-id="90f1f-257">![突出显示"将 Outlook 连接到 Office 365"消息，并突出显示"连接到其他帐户"链接](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span><span class="sxs-lookup"><span data-stu-id="90f1f-257">![The 'Connect Outlook to Office 365' message with the 'Connect to a different account' link highlighted](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span></span>
  
6. <span data-ttu-id="90f1f-258">**在"自动帐户设置"** 中，**选择"手动设置"或其他服务器类型，** 然后单击"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="90f1f-258">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>

7. <span data-ttu-id="90f1f-259">**在"选择帐户类型"** 中，选择**Office 365**。</span><span class="sxs-lookup"><span data-stu-id="90f1f-259">In **Choose Your Account Type**, choose **Office 365**.</span></span> <span data-ttu-id="90f1f-260">然后，**在"电子邮件地址"** 框中输入以前复制的监督邮箱的地址。</span><span class="sxs-lookup"><span data-stu-id="90f1f-260">Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span><br/><span data-ttu-id="90f1f-261">![Outlook 中的"添加帐户"对话框中的"选择帐户类型"页面突出显示了"电子邮件地址"框。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span><span class="sxs-lookup"><span data-stu-id="90f1f-261">![The 'Choose Your Account Type' page of the 'Add Account' dialog in Outlook showing the 'Email Address' box highlighted.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span></span>
  
8. <span data-ttu-id="90f1f-262">当出现提示时，请输入 Office 365 凭据。</span><span class="sxs-lookup"><span data-stu-id="90f1f-262">When prompted, enter your Office 365 credentials.</span></span>

9. <span data-ttu-id="90f1f-263">如果成功，则"**监督\<"\>策略名称**文件夹将列在 Outlook 中的"文件夹列表"视图中。</span><span class="sxs-lookup"><span data-stu-id="90f1f-263">If successful, the **Supervision — \<policy name\>** folder is listed in the Folder List view in Outlook.</span></span>

## <a name="powershell-reference"></a><span data-ttu-id="90f1f-264">电源外壳参考</span><span class="sxs-lookup"><span data-stu-id="90f1f-264">PowerShell reference</span></span>

<span data-ttu-id="90f1f-265">如果需要，您可以使用以下 PowerShell cmdlet 创建和管理监督策略：</span><span class="sxs-lookup"><span data-stu-id="90f1f-265">If needed, you can create and manage supervision policies with the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="90f1f-266">新监督审查政策V2</span><span class="sxs-lookup"><span data-stu-id="90f1f-266">New-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="90f1f-267">获取监督审查策略V2</span><span class="sxs-lookup"><span data-stu-id="90f1f-267">Get-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="90f1f-268">设置-监督审查策略V2</span><span class="sxs-lookup"><span data-stu-id="90f1f-268">Set-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="90f1f-269">删除-监督审查策略V2</span><span class="sxs-lookup"><span data-stu-id="90f1f-269">Remove-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="90f1f-270">新监督审查规则</span><span class="sxs-lookup"><span data-stu-id="90f1f-270">New-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="90f1f-271">设置-监督审查规则</span><span class="sxs-lookup"><span data-stu-id="90f1f-271">Set-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="90f1f-272">获取监督审查活动</span><span class="sxs-lookup"><span data-stu-id="90f1f-272">Get-SupervisoryReviewActivity</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [<span data-ttu-id="90f1f-273">获取监督审查总体进度报告</span><span class="sxs-lookup"><span data-stu-id="90f1f-273">Get-SupervisoryReviewOverallProgressReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [<span data-ttu-id="90f1f-274">获取监督审查顶级案例报告</span><span class="sxs-lookup"><span data-stu-id="90f1f-274">Get-SupervisoryReviewTopCasesReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)
