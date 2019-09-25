---
title: 数据丢失防护与微软团队
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 您现在可以将 DLP 策略应用于 Microsoft 团队聊天和频道。 阅读本文以了解有关其工作原理的更多内容。
ms.openlocfilehash: 9c8c122a84a739a0cc2942f63ff319121510415b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076331"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="afa12-104">数据丢失防护与微软团队</span><span class="sxs-lookup"><span data-stu-id="afa12-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="afa12-105">最近，Microsoft Teams 聊天和频道消息中添加了数据丢失防护功能，这些功能适用于获得 Office 365 高级合规性许可的用户，该功能可作为独立选项提供，并包含在 Office 365 E5 和 Microsoft 365 E5 合规性中。</span><span class="sxs-lookup"><span data-stu-id="afa12-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="afa12-106">Office 365 和 Microsoft 365 E3 包括针对共享点联机、OneDrive 和联机交换的 DLP 保护。</span><span class="sxs-lookup"><span data-stu-id="afa12-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="afa12-107">这还包括通过 Teams 共享的文件，因为团队使用 SharePoint Online 和 OneDrive 来共享文件。</span><span class="sxs-lookup"><span data-stu-id="afa12-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="afa12-108">支持团队聊天中的 DLP 保护需要 E5。</span><span class="sxs-lookup"><span data-stu-id="afa12-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="afa12-109">要了解有关许可要求详细信息，请参阅[Microsoft 365 租户级服务许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="afa12-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="afa12-110">微软团队的 DLP 概述</span><span class="sxs-lookup"><span data-stu-id="afa12-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="afa12-111">最近，[数据丢失防护](data-loss-prevention-policies.md)（DLP） 功能已扩展为包括 Microsoft Teams 聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="afa12-111">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams chat and channel messages.</span></span> <span data-ttu-id="afa12-112">如果您的组织具有 DLP，您现在可以定义阻止人们在 Microsoft Teams 频道或聊天会话中共享敏感信息的策略。</span><span class="sxs-lookup"><span data-stu-id="afa12-112">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="afa12-113">以下是此保护的工作原理的一些示例：</span><span class="sxs-lookup"><span data-stu-id="afa12-113">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="afa12-114">**示例 1：保护消息中的敏感信息。**</span><span class="sxs-lookup"><span data-stu-id="afa12-114">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="afa12-115">假设有人试图在 Teams 与来宾（外部用户）的聊天或频道中共享敏感信息。</span><span class="sxs-lookup"><span data-stu-id="afa12-115">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="afa12-116">如果定义了 DLP 策略以防止这种情况，则将删除包含发送给外部用户的敏感信息的邮件。</span><span class="sxs-lookup"><span data-stu-id="afa12-116">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="afa12-117">根据 DLP 策略的配置方式，这会自动发生，并在几秒钟内发生。</span><span class="sxs-lookup"><span data-stu-id="afa12-117">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="afa12-118">微软团队的 DLP 在与具有以下内容的 Microsoft Teams 用户共享时阻止敏感内容：</span><span class="sxs-lookup"><span data-stu-id="afa12-118">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="afa12-119">- [团队和渠道中的访客访问;](https://docs.microsoft.com/MicrosoftTeams/guest-access)或</span><span class="sxs-lookup"><span data-stu-id="afa12-119">- [guest access](https://docs.microsoft.com/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="afa12-120">- 会议和聊天会话中的[外部访问。](https://docs.microsoft.com/MicrosoftTeams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="afa12-120">- [external access](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="afa12-121">仅当发送方和接收方处于"仅组"模式并使用[Microsoft Teams 本机联合](https://docs.microsoft.com/microsoftteams/manage-external-access)时，外部聊天会话的 DLP 才起作用。</span><span class="sxs-lookup"><span data-stu-id="afa12-121">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](https://docs.microsoft.com/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="afa12-122">团队的 DLP[不会阻止与](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)Skype 交互的消息，也不会阻止 Skype 进行业务或非本机联合聊天会话。</span><span class="sxs-lookup"><span data-stu-id="afa12-122">DLP for Teams does not block messages in [interop](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="afa12-123">**示例 2：保护文档中的敏感信息。**</span><span class="sxs-lookup"><span data-stu-id="afa12-123">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="afa12-124">假设有人尝试与 Microsoft Teams 频道或聊天中的来宾共享文档，并且该文档包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="afa12-124">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="afa12-125">如果定义了 DLP 策略以防止这种情况，则不会为这些用户打开文档。</span><span class="sxs-lookup"><span data-stu-id="afa12-125">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="afa12-126">请注意，在这种情况下，您的 DLP 策略必须包括 SharePoint 和 OneDrive，才能提供保护。</span><span class="sxs-lookup"><span data-stu-id="afa12-126">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="afa12-127">（这是 Microsoft Teams 中显示的 SharePoint 的 DLP 示例，因此要求用户获得 Office 365 DLP（包含在 Office 365 E3 中）的许可，但不需要用户获得 Office 365 高级合规性的许可。</span><span class="sxs-lookup"><span data-stu-id="afa12-127">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="afa12-128">策略提示有助于教育用户</span><span class="sxs-lookup"><span data-stu-id="afa12-128">Policy tips help educate users</span></span>

<span data-ttu-id="afa12-129">与 DLP 在[Exchange、Outlook、Web 上 Outlook、](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)[共享点联机、企业网站的 OneDrive](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)和[Office 桌面客户端](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)中的工作方式类似，当操作与 DLP 策略冲突时，会出现策略提示。</span><span class="sxs-lookup"><span data-stu-id="afa12-129">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="afa12-130">下面是策略提示的示例：</span><span class="sxs-lookup"><span data-stu-id="afa12-130">Here's an example of a policy tip:</span></span>

![团队中阻止的邮件通知](media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="afa12-132">在这种情况下，发件人试图在 Microsoft Teams 频道中共享一个社会安全号码。</span><span class="sxs-lookup"><span data-stu-id="afa12-132">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="afa12-133">"**我能做什么？"** 链接将打开一个对话框，该对话框为发件人提供解决问题的选项。</span><span class="sxs-lookup"><span data-stu-id="afa12-133">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="afa12-134">请注意，在这种情况下，发件人可以选择重写策略，或通知管理员查看和解决策略。</span><span class="sxs-lookup"><span data-stu-id="afa12-134">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![解决被阻止邮件的选项](media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="afa12-136">在组织中，您可以选择允许用户覆盖 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="afa12-136">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="afa12-137">而且，在配置 DLP 策略时，可以使用默认策略提示，或为组织[自定义策略提示。](#to-customize-policy-tips)</span><span class="sxs-lookup"><span data-stu-id="afa12-137">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span> 

<span data-ttu-id="afa12-138">回到我们的示例，发件人在 Teams 频道中共享了一个社会保险号，以下是收件人看到的内容：</span><span class="sxs-lookup"><span data-stu-id="afa12-138">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

![邮件被阻止](media/dlp-teams-blockedmessage-notification-to-user.png)

<span data-ttu-id="afa12-140">**"这是什么？"** 链接将打开一篇关于 DLP 策略[的文章，](data-loss-prevention-policies.md)这有助于解释邮件被阻止的原因。</span><span class="sxs-lookup"><span data-stu-id="afa12-140">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="afa12-141">自定义策略提示</span><span class="sxs-lookup"><span data-stu-id="afa12-141">To customize policy tips</span></span>

<span data-ttu-id="afa12-142">要执行此任务，必须为您分配一个具有编辑 DLP 策略的权限的角色。</span><span class="sxs-lookup"><span data-stu-id="afa12-142">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="afa12-143">要了解更多信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="afa12-143">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="afa12-144">转到 Office 365 安全&合规性中心[https://protection.office.com](https://protection.office.com)（ ） 并登录。</span><span class="sxs-lookup"><span data-stu-id="afa12-144">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="afa12-145">选择**数据丢失防护** > **策略**。</span><span class="sxs-lookup"><span data-stu-id="afa12-145">Choose **Data loss prevention** > **Policy**.</span></span> 

3. <span data-ttu-id="afa12-146">选择策略，**在"策略设置"** 旁边选择"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="afa12-146">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="afa12-147">创建新规则或编辑策略的现有规则。</span><span class="sxs-lookup"><span data-stu-id="afa12-147">Either create a new rule, or edit an existing rule for the policy.</span></span><br/>![编辑策略的规则](media/dlp-teams-editrule.png)<br/>

5. <span data-ttu-id="afa12-149">在"**用户通知"** 选项卡上，**选择"自定义电子邮件文本"** 和/**或"自定义策略提示文本**选项"。</span><span class="sxs-lookup"><span data-stu-id="afa12-149">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span><br/><span data-ttu-id="afa12-150">![自定义用户通知和策略提示](media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="afa12-150">![Customize user notifications and policy tips](media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="afa12-151">指定要用于电子邮件通知和/或策略提示的文本，然后**选择"保存"。**</span><span class="sxs-lookup"><span data-stu-id="afa12-151">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span> 

7. <span data-ttu-id="afa12-152">在"**策略设置"** 选项卡上，**选择"保存"。**</span><span class="sxs-lookup"><span data-stu-id="afa12-152">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="afa12-153">等待大约一个小时，让您的更改通过数据中心工作并同步到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="afa12-153">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="afa12-154">将 Microsoft 团队作为位置添加到现有 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="afa12-154">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="afa12-155">要执行此任务，必须为您分配一个具有编辑 DLP 策略的权限的角色。</span><span class="sxs-lookup"><span data-stu-id="afa12-155">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="afa12-156">要了解更多信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="afa12-156">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="afa12-157">转到 Office 365 安全&合规性中心[https://protection.office.com](https://protection.office.com)（ ） 并登录。</span><span class="sxs-lookup"><span data-stu-id="afa12-157">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="afa12-158">选择**数据丢失防护** > **策略**。</span><span class="sxs-lookup"><span data-stu-id="afa12-158">Choose **Data loss prevention** > **Policy**.</span></span> 

3. <span data-ttu-id="afa12-159">选择策略，并**查看"位置"** 下的值。</span><span class="sxs-lookup"><span data-stu-id="afa12-159">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="afa12-160">如果您看到**团队聊天和频道消息，** 您都已设置。</span><span class="sxs-lookup"><span data-stu-id="afa12-160">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="afa12-161">如果没有，请单击"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="afa12-161">If you don't, click **Edit**.</span></span><br/><span data-ttu-id="afa12-162">![现有策略的位置](media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="afa12-162">![Locations for existing policy](media/dlp-teams-editexistingpolicy.png)</span></span><br/>

4. <span data-ttu-id="afa12-163">在"**状态"** 列中，**打开"团队聊天"和"频道消息"** 的策略。</span><span class="sxs-lookup"><span data-stu-id="afa12-163">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span><br/><span data-ttu-id="afa12-164">![用于团队聊天和渠道的 DLP](media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="afa12-164">![DLP for Teams chats and channels](media/dlp-teams-addteamschatschannels.png)</span></span><br/>

5. <span data-ttu-id="afa12-165">保留所有帐户的默认设置，或指定要包括或排除哪些帐户。</span><span class="sxs-lookup"><span data-stu-id="afa12-165">Keep the default settings of all accounts, or specify which accounts to include or exclude.</span></span>

6. <span data-ttu-id="afa12-166">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afa12-166">Click **Save**.</span></span>

<span data-ttu-id="afa12-167">等待大约一个小时，让您的更改通过数据中心工作并同步到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="afa12-167">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->
## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="afa12-168">为微软团队定义新的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="afa12-168">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="afa12-169">要执行此任务，必须为您分配一个具有编辑 DLP 策略的权限的角色。</span><span class="sxs-lookup"><span data-stu-id="afa12-169">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="afa12-170">要了解更多信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="afa12-170">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="afa12-171">转到 Office 365 安全&合规性中心[https://protection.office.com](https://protection.office.com)（ ） 并登录。</span><span class="sxs-lookup"><span data-stu-id="afa12-171">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="afa12-172">选择**数据丢失防护** > **策略** > **+ 创建策略**。</span><span class="sxs-lookup"><span data-stu-id="afa12-172">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span> 

3. <span data-ttu-id="afa12-173">选择一个[模板，](data-loss-prevention-policies.md#dlp-policy-templates)然后选择"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="afa12-173">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span><br/><span data-ttu-id="afa12-174">在我们的示例中，我们选择了美国个人身份信息数据模板。</span><span class="sxs-lookup"><span data-stu-id="afa12-174">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span><br/><span data-ttu-id="afa12-175">![DLP 策略的隐私模板](media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="afa12-175">![Privacy template for DLP policy](media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="afa12-176">在"**为策略命名"** 选项卡上，为策略指定名称和说明，然后选择"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="afa12-176">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span> 

5. <span data-ttu-id="afa12-177">在"**选择位置"** 选项卡上，保留所有位置的默认设置，或**选择"让我选择特定位置"，** 然后选择"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="afa12-177">On the **Choose locations** tab, keep the default setting of all locations, or select **Let me choose specific locations**, and then choose **Next**.</span></span><br/><span data-ttu-id="afa12-178">如果选择了特定位置，请为 DLP 策略选择这些位置，然后选择"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="afa12-178">If you chose specific locations, select them for your DLP policy, and then choose **Next**.</span></span><br/><span data-ttu-id="afa12-179">![DLP 策略位置](media/dlp-teams-selectlocationsnewpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="afa12-179">![DLP policy locations](media/dlp-teams-selectlocationsnewpolicy.png)</span></span><br/>
    > [!NOTE]
    > <span data-ttu-id="afa12-180">如果要确保包含敏感信息的文档不会不适当地共享，请确保**SharePoint 站点**和**OneDrive 帐户**以及**Teams 聊天和频道消息**处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="afa12-180">If you want to make sure documents that contain sensitive information are not shared inappropriately, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>
<br/>

6. <span data-ttu-id="afa12-181">在"**策略设置"** 选项卡上，在"**自定义要保护的内容类型""** 中保留默认简单设置，或**选择"使用高级设置"，** 然后选择"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="afa12-181">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="afa12-182">如果选择高级设置，则可以为策略创建或编辑规则。</span><span class="sxs-lookup"><span data-stu-id="afa12-182">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="afa12-183">（要获取有关此的帮助，请参阅[简单设置与高级设置。](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)</span><span class="sxs-lookup"><span data-stu-id="afa12-183">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="afa12-184">在"**策略设置"** 选项卡上，**在"如果我们检测到敏感信息时，您希望做什么？"**，查看设置。</span><span class="sxs-lookup"><span data-stu-id="afa12-184">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="afa12-185">（您可以在此处选择保留默认[策略提示和电子邮件通知，](use-notifications-and-policy-tips.md)或对其进行自定义。</span><span class="sxs-lookup"><span data-stu-id="afa12-185">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span><br/><span data-ttu-id="afa12-186">![带提示和通知的 DLP 策略设置](media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="afa12-186">![DLP policy settings with tips and notifications](media/dlp-teams-policysettings-tipsemails.png)</span></span><br/><span data-ttu-id="afa12-187">完成审阅或编辑设置后，选择"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="afa12-187">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="afa12-188">在"**策略设置"** 选项卡上，在"**是否要打开策略或先测试内容？"，** 选择是打开策略，[先测试它，](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)还是立即将其关闭，然后选择"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="afa12-188">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span><br/><span data-ttu-id="afa12-189">![指定是否打开策略](media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="afa12-189">![Specify whether to turn the policy on](media/dlp-teams-policysettings-turnonnow.png)</span></span><br/>

9. <span data-ttu-id="afa12-190">在"**查看设置"** 选项卡上，查看新策略的设置。</span><span class="sxs-lookup"><span data-stu-id="afa12-190">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="afa12-191">**选择"编辑"** 进行更改。</span><span class="sxs-lookup"><span data-stu-id="afa12-191">Choose **Edit** to make changes.</span></span> <span data-ttu-id="afa12-192">完成后，**选择"创建"。**</span><span class="sxs-lookup"><span data-stu-id="afa12-192">When you're finished, choose **Create**.</span></span> 

<span data-ttu-id="afa12-193">等待大约一个小时，让新策略通过数据中心并同步到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="afa12-193">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="afa12-194">相關文章</span><span class="sxs-lookup"><span data-stu-id="afa12-194">Related articles</span></span>

[<span data-ttu-id="afa12-195">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="afa12-195">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="afa12-196">針對 DLP 原則傳送電子郵件通知並顯示原則提示</span><span class="sxs-lookup"><span data-stu-id="afa12-196">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
