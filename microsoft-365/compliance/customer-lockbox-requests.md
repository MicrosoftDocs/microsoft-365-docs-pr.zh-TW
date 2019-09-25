---
title: Office 365 客戶加密箱要求
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解客户密码箱请求，这些请求允许您控制 Microsoft 支持工程师在遇到问题时如何访问您的数据。
ms.openlocfilehash: 2cbf19ad3c648373704c379794e24590fcb6d290
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076423"
---
# <a name="customer-lockbox-in-office-365"></a><span data-ttu-id="f4401-103">Office 365 中的客户密码箱</span><span class="sxs-lookup"><span data-stu-id="f4401-103">Customer Lockbox in Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="f4401-104">本文提供当前仅适用于具有 Microsoft 365 E5、Office 365 E5、信息保护和合规性或高级合规性加载项订阅的组织的功能的部署和配置指南。</span><span class="sxs-lookup"><span data-stu-id="f4401-104">This article provides deployment and configuration guidance for a feature that is currently available only for organizations that have a Microsoft 365 E5, Office 365 E5, Information Protection and Compliance, or Advanced Compliance add-on subscription.</span></span>

<span data-ttu-id="f4401-105">客户密码箱可确保 Microsoft 在未经您明确批准的情况下无法访问您的内容以执行服务操作。</span><span class="sxs-lookup"><span data-stu-id="f4401-105">Customer Lockbox ensures that Microsoft cannot access your content to perform a service operation without your explicit approval.</span></span> <span data-ttu-id="f4401-106">客户密码箱将您带入审批工作流，以便请求访问您的内容。</span><span class="sxs-lookup"><span data-stu-id="f4401-106">Customer Lockbox brings you into the approval workflow for requests to access your content.</span></span>

<span data-ttu-id="f4401-107">有时，Microsoft 工程师会帮助排除故障并修复支持过程中的客户报告的问题。</span><span class="sxs-lookup"><span data-stu-id="f4401-107">Occasionally, Microsoft engineers help troubleshoot and fix customer reported issues in the support process.</span></span> <span data-ttu-id="f4401-108">通常，问题通过 Microsoft 为其服务准备的大量遥测和调试工具得到解决。</span><span class="sxs-lookup"><span data-stu-id="f4401-108">Usually, issues are fixed through extensive telemetry and debugging tools Microsoft has in place for its services.</span></span> <span data-ttu-id="f4401-109">但是，在某些情况下，需要 Microsoft 工程师访问客户内容以确定根本原因并解决问题。</span><span class="sxs-lookup"><span data-stu-id="f4401-109">However, some cases require a Microsoft engineer to access customer content to determine the root cause and fix the issue.</span></span> <span data-ttu-id="f4401-110">客户密码箱要求工程师请求客户访问，作为审批工作流的最后一步。</span><span class="sxs-lookup"><span data-stu-id="f4401-110">Customer Lockbox requires the engineer to request access from the customer as a final step in the approval workflow.</span></span> <span data-ttu-id="f4401-111">这为组织提供了批准或拒绝这些请求的选项，并为客户提供直接访问控制。</span><span class="sxs-lookup"><span data-stu-id="f4401-111">This gives organizations the option to approve or deny these requests, and provide direct-access control to the customer.</span></span>

### <a name="customer-lockbox-overview-video"></a><span data-ttu-id="f4401-112">客户密码箱概述视频</span><span class="sxs-lookup"><span data-stu-id="f4401-112">Customer Lockbox overview video</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

> [!NOTE]
> <span data-ttu-id="f4401-113">客户密码箱支持访问 Exchange 在线、共享点联机和 OneDrive 中的数据的请求。</span><span class="sxs-lookup"><span data-stu-id="f4401-113">Customer Lockbox supports requests to access data in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="f4401-114">要推荐对其他 Office 365 服务的支持，请在[Office 365 用户语音](https://office365.uservoice.com/)中提交请求。</span><span class="sxs-lookup"><span data-stu-id="f4401-114">To recommend support for other Office 365 services, please submit a request at [Office 365 UserVoice](https://office365.uservoice.com/).</span></span>

## <a name="customer-lockbox-workflow"></a><span data-ttu-id="f4401-115">客户密码箱工作流</span><span class="sxs-lookup"><span data-stu-id="f4401-115">Customer Lockbox workflow</span></span>

<span data-ttu-id="f4401-116">以下步骤概述了由 Microsoft 工程师启动客户密码箱请求时的典型工作流：</span><span class="sxs-lookup"><span data-stu-id="f4401-116">The following steps outline the typical workflow when a Customer Lockbox request is initiated by a Microsoft engineer:</span></span>

1. <span data-ttu-id="f4401-117">组织中的某个人对其 Office 365 邮箱有问题。</span><span class="sxs-lookup"><span data-stu-id="f4401-117">Someone at an organization has an issue with their Office 365 mailbox.</span></span>

2. <span data-ttu-id="f4401-118">用户解决问题但无法修复后，他们将使用 Microsoft 支持打开支持请求。</span><span class="sxs-lookup"><span data-stu-id="f4401-118">After the user troubleshoots the issue, but can't fix it, they open a support request with Microsoft Support.</span></span>

3. <span data-ttu-id="f4401-119">支持工程师审核服务请求并确定需要访问客户的 Exchange 在线内容来修复问题。</span><span class="sxs-lookup"><span data-stu-id="f4401-119">A support engineer reviews the service request and determines a need to access customer’s Exchange Online content to repair the issue.</span></span>

4. <span data-ttu-id="f4401-120">支持工程师登录到客户密码箱请求工具，并通过指定客户的租户名称、服务请求编号以及需要访问数据的估计持续时间来发出数据访问请求。</span><span class="sxs-lookup"><span data-stu-id="f4401-120">The support engineer logs into the Customer Lockbox request tool and makes a data access request by specifying the customer's tenant name, service request number, and the estimated duration for which access to the data is needed.</span></span>

5. <span data-ttu-id="f4401-121">在 Microsoft 支持经理批准请求后，客户密码箱会向客户组织的指定审批人发送有关 Microsoft 挂起的访问请求的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="f4401-121">After a Microsoft Support manager approves the request, Customer Lockbox sends the designated approver at the customer's organization an email notification about the pending access request from Microsoft.</span></span>

    ![客户密码箱电子邮件通知示例](media/CustomerLockbox1.png)

   > [!NOTE]
   > <span data-ttu-id="f4401-123">在 Microsoft 365 管理中心中分配了[客户密码箱访问审批者管理员](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)角色的任何人都可以批准客户密码箱请求。</span><span class="sxs-lookup"><span data-stu-id="f4401-123">Anyone who is assigned the [Customer Lockbox access approver](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) admin role in Microsoft 365 admin center can approve Customer Lockbox requests.</span></span>

7. <span data-ttu-id="f4401-124">审批者登录到 Microsoft 365 管理中心并批准该请求。</span><span class="sxs-lookup"><span data-stu-id="f4401-124">The approver signs in to the Microsoft 365 admin center and approves the request.</span></span> <span data-ttu-id="f4401-125">此步骤通过搜索 Office 365 审核日志触发可用的审核记录的创建。</span><span class="sxs-lookup"><span data-stu-id="f4401-125">This step triggers the creation of an audit record available by searching the Office 365 audit log.</span></span> <span data-ttu-id="f4401-126">有关详细信息，请参阅[审核客户密码箱请求](#auditing-customer-lockbox-requests)部分。</span><span class="sxs-lookup"><span data-stu-id="f4401-126">For more information, see the [Auditing Customer Lockbox requests](#auditing-customer-lockbox-requests) section.</span></span>

   <span data-ttu-id="f4401-127">如果客户拒绝该请求或在 12 小时内未批准请求，则请求将过期，并且不授予 Microsoft 工程师访问权限。</span><span class="sxs-lookup"><span data-stu-id="f4401-127">If the customer rejects the request or the request isn’t approved within 12 hours, the request expires and no access is granted to the Microsoft engineer.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f4401-128">Microsoft 在要求您登录到 Office 365 的客户密码箱电子邮件通知中不包含任何链接。</span><span class="sxs-lookup"><span data-stu-id="f4401-128">Microsoft does not include any links in Customer Lockbox email notifications requiring you to sign in to Office 365.</span></span>

8. <span data-ttu-id="f4401-129">客户批准请求后，Microsoft 工程师会收到批准消息，登录到 Exchange Online 并修复客户的问题。</span><span class="sxs-lookup"><span data-stu-id="f4401-129">After the customer approves the request, the Microsoft engineer receives the approval message, logs into Exchange Online, and fixes the customer's issue.</span></span> <span data-ttu-id="f4401-130">Microsoft 工程师具有请求的持续时间来修复问题，之后将自动撤消访问权限。</span><span class="sxs-lookup"><span data-stu-id="f4401-130">Microsoft engineers have the requested duration to fix the issue after which the access is automatically revoked.</span></span>

> [!NOTE]
> <span data-ttu-id="f4401-131">Microsoft 工程师执行的所有操作都记录在 Office 365 审核日志中。</span><span class="sxs-lookup"><span data-stu-id="f4401-131">All actions performed by a Microsoft engineer are logged in the Office 365 audit log.</span></span> <span data-ttu-id="f4401-132">您可以搜索和查看这些审核记录，并可以搜索和查看。</span><span class="sxs-lookup"><span data-stu-id="f4401-132">You can search for and review these audit record and can be searched for and reviewed.</span></span>

## <a name="turn-customer-lockbox-requests-on-or-off"></a><span data-ttu-id="f4401-133">打开或关闭客户密码箱请求</span><span class="sxs-lookup"><span data-stu-id="f4401-133">Turn Customer Lockbox requests on or off</span></span>

<span data-ttu-id="f4401-134">Office 365 管理员可以在 Microsoft 365 管理中心打开客户密码箱控件。</span><span class="sxs-lookup"><span data-stu-id="f4401-134">An Office 365 administrator can turn on Customer Lockbox controls in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f4401-135">启用客户锁定盒后，Microsoft 需要获得组织的批准，然后才能访问其任何内容。</span><span class="sxs-lookup"><span data-stu-id="f4401-135">When Customer Lockbox is turned on, Microsoft is required to obtain an organization’s approval before accessing any of their content.</span></span>

> [!NOTE]
> <span data-ttu-id="f4401-136">要执行以下过程，您必须是 Microsoft 365 或 Office 365 组织的全局管理员，或者被分配客户**密码箱访问审批者**管理员角色。</span><span class="sxs-lookup"><span data-stu-id="f4401-136">To perform the following procedure, you must be a global administrator in your Microsoft 365 or Office 365 organization, or be assigned the **Customer Lockbox access approver** admin role.</span></span>

1. <span data-ttu-id="f4401-137">转到[https://admin.microsoft.com](https://admin.microsoft.com)并登录您的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="f4401-137">Go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="f4401-138">**单击"设置>&隐私。**</span><span class="sxs-lookup"><span data-stu-id="f4401-138">Click **Settings > Security & privacy**.</span></span>

    ![在管理中心编辑客户密码箱设置](media/CustomerLockbox2.png)

3. <span data-ttu-id="f4401-140">在"**客户锁定箱"** 磁贴上，**单击"编辑"，** 然后将切换**移动到"打开"** 或"**关闭"** 以打开或关闭要素。</span><span class="sxs-lookup"><span data-stu-id="f4401-140">On the **Customer Lockbox** tile, click **Edit**, and then move the toggle to **On** or **Off** to turn the feature on or off.</span></span>

    ![Require approval for Customer Lockbox](media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a><span data-ttu-id="f4401-142">批准或拒绝客户密码箱请求</span><span class="sxs-lookup"><span data-stu-id="f4401-142">Approve or deny a Customer Lockbox request</span></span>

> [!NOTE]
> <span data-ttu-id="f4401-143">要执行以下过程，您必须是 Microsoft 365 或 Office 365 组织的全局管理员，或者被分配客户**密码箱访问审批者**管理员角色。</span><span class="sxs-lookup"><span data-stu-id="f4401-143">To perform the following procedure, you must be a global administrator in your Microsoft 365 or Office 365 organization, or be assigned the **Customer Lockbox access approver** admin role.</span></span>

1. <span data-ttu-id="f4401-144">转到[https://admin.microsoft.com](https://admin.microsoft.com)并登录您的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="f4401-144">Go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="f4401-145">**单击"支持>客户密码箱请求**。</span><span class="sxs-lookup"><span data-stu-id="f4401-145">Click **Support > Customer Lockbox Requests**.</span></span>

    ![单击"支持"，然后单击"客户锁定框请求"](media/CustomerLockbox5.png)

    <span data-ttu-id="f4401-147">将显示客户密码箱请求的列表。</span><span class="sxs-lookup"><span data-stu-id="f4401-147">A list of Customer Lockbox requests is displayed.</span></span>

    ![客户密码箱请求列表](media/CustomerLockbox6.png)

3. <span data-ttu-id="f4401-149">选择客户锁定箱请求，然后单击"**批准"** 或"**拒绝"。**</span><span class="sxs-lookup"><span data-stu-id="f4401-149">Select a Customer Lockbox request, and then click **Approve** or **Deny**.</span></span>

    ![批准或拒绝客户密码箱请求](media/CustomerLockbox7.png)

    <span data-ttu-id="f4401-151">将显示有关客户密码箱请求的审批确认消息。</span><span class="sxs-lookup"><span data-stu-id="f4401-151">A confirmation message about the approval of the Customer Lockbox request is displayed.</span></span>

    ![批准或拒绝客户密码箱请求](media/CustomerLockbox8.png)

## <a name="auditing-customer-lockbox-requests"></a><span data-ttu-id="f4401-153">审核客户密码箱请求</span><span class="sxs-lookup"><span data-stu-id="f4401-153">Auditing Customer Lockbox requests</span></span> 

<span data-ttu-id="f4401-154">与客户密码箱请求对应的审核记录记录记录在 Office 365 审核日志中，可以使用 Office 365 安全&合规性中心的[审核日志搜索工具](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance)进行访问。</span><span class="sxs-lookup"><span data-stu-id="f4401-154">Audit records that correspond to the Customer Lockbox requests are logged in the Office 365 audit log and can be accessed by using the [Audit log search tool](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance) in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="f4401-155">与客户接受或拒绝客户密码箱请求相关的操作以及 Microsoft 工程师执行的操作（当访问请求获得批准时）将记录在 Office 365 审核日志中。</span><span class="sxs-lookup"><span data-stu-id="f4401-155">Actions related to a customer accepting or denying a Customer Lockbox request and actions performed by Microsoft engineers (when access requests are approved) are logged in the Office 365 audit log.</span></span> <span data-ttu-id="f4401-156">您可以搜索和查看这些审核记录。</span><span class="sxs-lookup"><span data-stu-id="f4401-156">You can search for and review these audit records.</span></span>

> [!NOTE]
> <span data-ttu-id="f4401-157">您必须在 Exchange Online 中分配"仅查看审核日志"角色才能搜索 Office 365 审核日志。</span><span class="sxs-lookup"><span data-stu-id="f4401-157">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log.</span></span> <span data-ttu-id="f4401-158">有关详细信息，请参阅在[Office 365 安全&合规性中心中搜索审核日志](https://docs.microsoft.com/en-us/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin)。</span><span class="sxs-lookup"><span data-stu-id="f4401-158">For more information, see [Search the audit log in the Office 365 Security & Compliance Center](https://docs.microsoft.com/en-us/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin).</span></span>

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a><span data-ttu-id="f4401-159">搜索审核日志，查找与客户密码箱请求相关的活动</span><span class="sxs-lookup"><span data-stu-id="f4401-159">Search the audit log for activity related to Customer Lockbox requests</span></span>

<span data-ttu-id="f4401-160">下面有关如何创建审核日志搜索查询以返回与客户密码箱相关的审核记录：</span><span class="sxs-lookup"><span data-stu-id="f4401-160">Here's how to create an audit log search query to return audit records related to Customer Lockbox:</span></span>

1. <span data-ttu-id="f4401-161">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="f4401-161">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="f4401-162">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f4401-162">Sign in to Office 365 using your work or school account.</span></span>

3. <span data-ttu-id="f4401-163">在"安全&合规中心"的左侧窗格中，单击"**搜索&调查** > **审核日志搜索**。</span><span class="sxs-lookup"><span data-stu-id="f4401-163">In the left pane of the Security & Compliance Center, click **Search & investigation** > **Audit log search**.</span></span>

    <span data-ttu-id="f4401-164">将显示**审核日志搜索**页。</span><span class="sxs-lookup"><span data-stu-id="f4401-164">The **Audit log search** page is displayed.</span></span>

    ![审核日志搜索页](media/auditlogsearch1.png)
  
4. <span data-ttu-id="f4401-166">配置以下搜索条件：</span><span class="sxs-lookup"><span data-stu-id="f4401-166">Configure the following search criteria:</span></span>

    <span data-ttu-id="f4401-167">a.</span><span class="sxs-lookup"><span data-stu-id="f4401-167">a.</span></span> <span data-ttu-id="f4401-168">**活动**- 将此字段留空，以便搜索返回所有活动的审核记录。</span><span class="sxs-lookup"><span data-stu-id="f4401-168">**Activities** - Leave this field blank so that the search returns audit records for all activities.</span></span> <span data-ttu-id="f4401-169">这是返回与客户密码箱请求和 Microsoft 工程师执行的相应活动相关的任何审核记录所必需的。</span><span class="sxs-lookup"><span data-stu-id="f4401-169">This is necessary to return any audit records related to Customer Lockbox requests and corresponding activity performed by Microsoft engineers.</span></span>

    <span data-ttu-id="f4401-170">b.</span><span class="sxs-lookup"><span data-stu-id="f4401-170">b.</span></span> <span data-ttu-id="f4401-171">**开始日期**和**结束日期**- 选择日期和时间范围以显示该时间段内发生的事件。</span><span class="sxs-lookup"><span data-stu-id="f4401-171">**Start date** and **End date** - Select a date and time range to display the events that occurred within that period.</span></span>

    <span data-ttu-id="f4401-172">c.</span><span class="sxs-lookup"><span data-stu-id="f4401-172">c.</span></span> <span data-ttu-id="f4401-173">**用户**- 将此字段留空。</span><span class="sxs-lookup"><span data-stu-id="f4401-173">**Users** - Leave this field blank.</span></span>

    <span data-ttu-id="f4401-174">d.</span><span class="sxs-lookup"><span data-stu-id="f4401-174">d.</span></span> <span data-ttu-id="f4401-175">**文件、文件夹或站点**- 将此字段留空。</span><span class="sxs-lookup"><span data-stu-id="f4401-175">**File, folder, or site** - Leave this field blank.</span></span>

5. <span data-ttu-id="f4401-176">**单击"搜索"** 以使用搜索条件运行搜索。</span><span class="sxs-lookup"><span data-stu-id="f4401-176">Click **Search** to run the search using your search criteria.</span></span> 

    <span data-ttu-id="f4401-177">搜索结果将加载，几分钟后，它们**将显示在"审核日志搜索"** 页上**的"结果"** 下。</span><span class="sxs-lookup"><span data-stu-id="f4401-177">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page.</span></span>

6. <span data-ttu-id="f4401-178">单击搜索结果页上**的"筛选结果"，** 然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="f4401-178">Click **Filter results** on the search results page, and do one of the following things:</span></span>

   - <span data-ttu-id="f4401-179">要显示与组织中批准或拒绝客户密码箱请求的审批人相关的审核记录：**在"活动"** 列下的框中，**键入"设置访问到客户数据请求**"。</span><span class="sxs-lookup"><span data-stu-id="f4401-179">To display audit records related to an approver in your organization approving or denying a Customer Lockbox request: In the box under the **Activity** column, type **Set-AccessToCustomerDataRequest**.</span></span>

   - <span data-ttu-id="f4401-180">要显示与 Microsoft 工程师执行响应已批准的客户密码箱请求的操作相关的审核记录：**在"用户"** 列下的框中，键入**Microsoft 操作员**。</span><span class="sxs-lookup"><span data-stu-id="f4401-180">To display audit records related to a Microsoft engineer performing actions in response to an approved Customer Lockbox request: In the box under the **User** column, type **Microsoft Operator**.</span></span> <span data-ttu-id="f4401-181">请注意，工程师执行的操作**显示在"活动"** 列中。</span><span class="sxs-lookup"><span data-stu-id="f4401-181">Note that the action performed by the engineer is displayed int the **Activity** column.</span></span>

      ![筛选"微软操作员"以显示审核记录](media/CustomerLockbox10.png)

7. <span data-ttu-id="f4401-183">在结果列表中，单击审核记录以显示它。</span><span class="sxs-lookup"><span data-stu-id="f4401-183">In the list of results, click an audit record to display it.</span></span>

### <a name="audit-record-for-a-customer-lockbox-access-request"></a><span data-ttu-id="f4401-184">客户密码箱访问请求的审核记录</span><span class="sxs-lookup"><span data-stu-id="f4401-184">Audit record for a Customer Lockbox access request</span></span>

<span data-ttu-id="f4401-185">当组织中的人员批准或拒绝客户密码箱请求时，审核记录将记录在 Office 365 审核日志中。</span><span class="sxs-lookup"><span data-stu-id="f4401-185">When a person in your organization approves or denies a Customer Lockbox request, an audit record is logged in the Office 365 audit log.</span></span> <span data-ttu-id="f4401-186">此记录包含以下信息。</span><span class="sxs-lookup"><span data-stu-id="f4401-186">This record contains the following information.</span></span> 

| <span data-ttu-id="f4401-187">审核记录属性</span><span class="sxs-lookup"><span data-stu-id="f4401-187">Audit record property</span></span>| <span data-ttu-id="f4401-188">描述</span><span class="sxs-lookup"><span data-stu-id="f4401-188">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="f4401-189">日期</span><span class="sxs-lookup"><span data-stu-id="f4401-189">Date</span></span>       | <span data-ttu-id="f4401-190">批准或拒绝客户密码箱请求的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="f4401-190">The date and time when the Customer Lockbox request was approved or denied.</span></span>
| <span data-ttu-id="f4401-191">IP 位址</span><span class="sxs-lookup"><span data-stu-id="f4401-191">IP address</span></span> | <span data-ttu-id="f4401-192">批准者用于批准或拒绝请求的计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f4401-192">The IP address of the machine the approver used to approve or deny a request.</span></span> |
| <span data-ttu-id="f4401-193">使用者</span><span class="sxs-lookup"><span data-stu-id="f4401-193">User</span></span>       | <span data-ttu-id="f4401-194">服务帐户 BOXServiceAccount_\[客户\]林 .prod.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="f4401-194">The service account BOXServiceAccount@\[customerforest\].prod.outlook.com.</span></span>            |
| <span data-ttu-id="f4401-195">活動</span><span class="sxs-lookup"><span data-stu-id="f4401-195">Activity</span></span>   | <span data-ttu-id="f4401-196">设置访问到客户数据请求;这是批准或拒绝客户密码箱请求时记录的审核活动。</span><span class="sxs-lookup"><span data-stu-id="f4401-196">Set-AccessToCustomerDataRequest; this is the auditing activity that is logged when you approve or deny a Customer Lockbox request.</span></span>                                |
| <span data-ttu-id="f4401-197">項目</span><span class="sxs-lookup"><span data-stu-id="f4401-197">Item</span></span>       | <span data-ttu-id="f4401-198">客户密码箱请求的 Guid</span><span class="sxs-lookup"><span data-stu-id="f4401-198">The Guid of the Customer Lockbox request</span></span>                             |

<span data-ttu-id="f4401-199">以下屏幕截图显示了与已批准的客户密码箱请求对应的审核日志记录的示例。</span><span class="sxs-lookup"><span data-stu-id="f4401-199">The following screenshot shows an example of an audit log record that corresponds to an approved Customer Lockbox request.</span></span> <span data-ttu-id="f4401-200">如果客户密码箱请求被拒绝，则**批准决策**参数的值**将为"拒绝"。**</span><span class="sxs-lookup"><span data-stu-id="f4401-200">If a Customer Lockbox request was denied, then the value of **ApprovalDecision** parameter would be **Deny**.</span></span>

![已批准的客户密码箱请求的审核记录](media/CustomerLockbox9.png)

> [!TIP]
> <span data-ttu-id="f4401-202">要在审核记录中显示更多详细信息，请单击"**更多信息"。**</span><span class="sxs-lookup"><span data-stu-id="f4401-202">To display more detailed information in an audit record, click **More information**.</span></span>

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a><span data-ttu-id="f4401-203">微软工程师执行的操作的审核记录</span><span class="sxs-lookup"><span data-stu-id="f4401-203">Audit record for an action performed by a Microsoft engineer</span></span>

<span data-ttu-id="f4401-204">如前所述，Microsoft 工程师在客户密码箱请求获得批准后执行的操作（并可能导致访问客户内容）将记录在审核日志中。</span><span class="sxs-lookup"><span data-stu-id="f4401-204">As previously explained, the actions performed by a Microsoft engineer after a Customer Lockbox request is approved (and that may result in accessing customer content) are logged in the audit log.</span></span> <span data-ttu-id="f4401-205">这些记录包含以下信息。</span><span class="sxs-lookup"><span data-stu-id="f4401-205">These records contain the following information.</span></span>

| <span data-ttu-id="f4401-206">审核记录属性</span><span class="sxs-lookup"><span data-stu-id="f4401-206">Audit record property</span></span>| <span data-ttu-id="f4401-207">描述</span><span class="sxs-lookup"><span data-stu-id="f4401-207">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="f4401-208">日期</span><span class="sxs-lookup"><span data-stu-id="f4401-208">Date</span></span>       | <span data-ttu-id="f4401-209">执行操作的日期时间。</span><span class="sxs-lookup"><span data-stu-id="f4401-209">Date time when the action was performed.</span></span> <span data-ttu-id="f4401-210">请注意，执行此操作的时间将在客户密码箱请求获得批准后的 4 小时内执行。</span><span class="sxs-lookup"><span data-stu-id="f4401-210">Note that the time that this action was performed will be within 4 hours of when the Customer Lockbox request was approved.</span></span>              |
| <span data-ttu-id="f4401-211">IP 位址</span><span class="sxs-lookup"><span data-stu-id="f4401-211">IP address</span></span> | <span data-ttu-id="f4401-212">微软工程师使用的机器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f4401-212">The IP Address of the machine Microsoft engineer used.</span></span> |
| <span data-ttu-id="f4401-213">使用者</span><span class="sxs-lookup"><span data-stu-id="f4401-213">User</span></span>       | <span data-ttu-id="f4401-214">微软运营商;此值指示此记录与客户密码箱请求相关。</span><span class="sxs-lookup"><span data-stu-id="f4401-214">Microsoft Operator; this value indicates that this record is related to a Customer Lockbox request.</span></span>                                  |
| <span data-ttu-id="f4401-215">活動</span><span class="sxs-lookup"><span data-stu-id="f4401-215">Activity</span></span>   | <span data-ttu-id="f4401-216">由 Microsoft 工程师执行的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="f4401-216">Name of the activity performed by the Microsoft engineer.</span></span>|
| <span data-ttu-id="f4401-217">項目</span><span class="sxs-lookup"><span data-stu-id="f4401-217">Item</span></span>       | <span data-ttu-id="f4401-218">\<空\></span><span class="sxs-lookup"><span data-stu-id="f4401-218">\<empty\></span></span>                                             |


## <a name="frequently-asked-questions"></a><span data-ttu-id="f4401-219">常見問題集</span><span class="sxs-lookup"><span data-stu-id="f4401-219">Frequently asked questions</span></span>

#### <a name="which-office-365-services-does-customer-lockbox-apply-to"></a><span data-ttu-id="f4401-220">客户密码箱适用于哪些 Office 365 服务？</span><span class="sxs-lookup"><span data-stu-id="f4401-220">Which Office 365 services does Customer Lockbox apply to?</span></span>

<span data-ttu-id="f4401-221">客户锁定盒当前受"Exchange 联机"""共享点联机"和"企业一个驱动器"支持。</span><span class="sxs-lookup"><span data-stu-id="f4401-221">Customer Lockbox is currently supported in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span>

#### <a name="is-customer-lockbox-available-to-all-office-365-customers"></a><span data-ttu-id="f4401-222">客户密码箱是否对所有 Office 365 客户可用？</span><span class="sxs-lookup"><span data-stu-id="f4401-222">Is Customer Lockbox available to all Office 365 customers?</span></span>

<span data-ttu-id="f4401-223">客户锁定盒包含在 Microsoft 365 或 Office 365 E5 订阅中，并可添加到具有信息保护和合规性或高级合规性加载项订阅的其他计划中。</span><span class="sxs-lookup"><span data-stu-id="f4401-223">Customer Lockbox is included with the Microsoft 365 or Office 365 E5 subscriptions and can be added to other plans with an Information Protection and Compliance or an Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="f4401-224">有关详细信息，请参阅 [计划和定价。](https://products.office.com/business/office-365-enterprise-e5-business-software) </span><span class="sxs-lookup"><span data-stu-id="f4401-224">Please see [Plans and pricing](https://products.office.com/business/office-365-enterprise-e5-business-software) for more information.</span></span>

#### <a name="what-is-customer-content"></a><span data-ttu-id="f4401-225">什么是客户内容？</span><span class="sxs-lookup"><span data-stu-id="f4401-225">What is customer content?</span></span>

<span data-ttu-id="f4401-226">客户内容是 Office 365 服务和应用程序的用户创建的数据。</span><span class="sxs-lookup"><span data-stu-id="f4401-226">Customer content is the data created by users of Office 365 services and applications.</span></span> <span data-ttu-id="f4401-227">客户内容的示例包括：</span><span class="sxs-lookup"><span data-stu-id="f4401-227">Examples of customer content include:</span></span>

- <span data-ttu-id="f4401-228">电子邮件正文或电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="f4401-228">Email body or email attachments</span></span>

- <span data-ttu-id="f4401-229">SharePoint 网站内容</span><span class="sxs-lookup"><span data-stu-id="f4401-229">SharePoint site contents</span></span>

- <span data-ttu-id="f4401-230">SharePoint 文件正文中的信息</span><span class="sxs-lookup"><span data-stu-id="f4401-230">Information in the body of a SharePoint file</span></span>

- <span data-ttu-id="f4401-231">Skype 业务演示文稿文件正文</span><span class="sxs-lookup"><span data-stu-id="f4401-231">Skype for Business presentation file body</span></span>

- <span data-ttu-id="f4401-232">即时消息 （IM） 或语音对话</span><span class="sxs-lookup"><span data-stu-id="f4401-232">Instant messages (IM) or voice conversations</span></span>

- <span data-ttu-id="f4401-233">客户生成的 Blob 或结构化存储数据（例如，SQL 容器）</span><span class="sxs-lookup"><span data-stu-id="f4401-233">Customer-generated blob or structured storage data (for example, SQL Containers)</span></span>

- <span data-ttu-id="f4401-234">客户拥有的安全信息（例如，证书、加密密钥和密码）</span><span class="sxs-lookup"><span data-stu-id="f4401-234">Customer-owned security information (for example, certificates, encryption keys, and passwords)</span></span>

- <span data-ttu-id="f4401-235">如果客户内容仍然存在，则推断和所有后续推断</span><span class="sxs-lookup"><span data-stu-id="f4401-235">Inferences, and all subsequent inferences, if customer content remains</span></span>

<span data-ttu-id="f4401-236">有关 Office 365 中客户内容的其他信息，请参阅[Office 365 信任中心](https://products.office.com/en-US/business/office-365-trust-center-privacy/)。</span><span class="sxs-lookup"><span data-stu-id="f4401-236">For additional information about customer content in Office 365, see the [Office 365 Trust Center](https://products.office.com/en-US/business/office-365-trust-center-privacy/).</span></span>

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a><span data-ttu-id="f4401-237">当有访问我的内容的请求时，会通知谁？</span><span class="sxs-lookup"><span data-stu-id="f4401-237">Who is notified when there is a request to access my content?</span></span>

<span data-ttu-id="f4401-238">将通知全局管理员和分配客户密码箱访问审批人管理员角色的任何人。</span><span class="sxs-lookup"><span data-stu-id="f4401-238">Global administrators and anyone assigned the Customer Lockbox access approver admin role are notified.</span></span> <span data-ttu-id="f4401-239">这些用户也可以批准客户密码箱请求。</span><span class="sxs-lookup"><span data-stu-id="f4401-239">These are also the same users who can approve for Customer Lockbox requests.</span></span>

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a><span data-ttu-id="f4401-240">谁可以在我的组织中批准或拒绝这些请求？</span><span class="sxs-lookup"><span data-stu-id="f4401-240">Who can approve or reject these requests in my organization?</span></span>

<span data-ttu-id="f4401-241">全局管理员和分配客户密码箱访问审批者管理员角色的任何人都可以批准客户密码箱请求。</span><span class="sxs-lookup"><span data-stu-id="f4401-241">Global administrators and anyone assigned the Customer Lockbox access approver admin role can approve Customer Lockbox requests.</span></span> <span data-ttu-id="f4401-242">客户在其组织中控制这些角色分配。</span><span class="sxs-lookup"><span data-stu-id="f4401-242">Customers control these role assignments in their organizations.</span></span>

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a><span data-ttu-id="f4401-243">如何选择加入客户密码箱？</span><span class="sxs-lookup"><span data-stu-id="f4401-243">How do I opt in to Customer Lockbox?</span></span>

<span data-ttu-id="f4401-244">全局管理员可以在 Microsoft 365 或 Microsoft 365 管理中心启用和配置客户锁定盒。</span><span class="sxs-lookup"><span data-stu-id="f4401-244">A global administrator can enable and configure Customer Lockbox in the Microsoft 365 or Microsoft 365 admin center.</span></span>

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a><span data-ttu-id="f4401-245">如果我批准客户密码箱请求，工程师可以做什么，我如何知道 Microsoft 工程师做了什么？</span><span class="sxs-lookup"><span data-stu-id="f4401-245">If I approve a Customer Lockbox request, what can the engineer do and how will I know what the Microsoft engineer did?</span></span>

<span data-ttu-id="f4401-246">批准客户密码箱请求后，Microsoft 工程师授予这些必要的权限，以便使用预先批准的 cmdlet 访问客户内容。</span><span class="sxs-lookup"><span data-stu-id="f4401-246">After you approve a Customer Lockbox request, the Microsoft engineer granted these necessary privileges to access customer content by using pre-approved cmdlets.</span></span> <span data-ttu-id="f4401-247">Microsoft 工程师针对客户密码箱请求执行的操作将记录在 Office 365 安全&合规性中心的审核日志中。</span><span class="sxs-lookup"><span data-stu-id="f4401-247">Actions taken by Microsoft engineers in response to Customer Lockbox requests are logged and accessible in the audit log in the Office 365 Security & Compliance Center.</span></span>

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a><span data-ttu-id="f4401-248">我如何知道 Microsoft 遵循审批流程？</span><span class="sxs-lookup"><span data-stu-id="f4401-248">How do I know that Microsoft follows the approval process?</span></span>

<span data-ttu-id="f4401-249">您可以使用 Microsoft 365 管理中心中的客户密码箱请求历史记录对发送给组织中管理员和审批者的电子邮件审批通知进行交叉引用。</span><span class="sxs-lookup"><span data-stu-id="f4401-249">You can cross-reference the email approval notifications sent to admins and approvers in your organization with the Customer Lockbox request history in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="f4401-250">客户密码箱包含在最新的[SOC 1 SSAE 16 审核报告中。](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)</span><span class="sxs-lookup"><span data-stu-id="f4401-250">Customer Lockbox is included in the latest [SOC 1 SSAE 16 audit report](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span> <span data-ttu-id="f4401-251">有关详细信息，可以在[Microsoft 服务信任门户](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)中找到最新的报告。</span><span class="sxs-lookup"><span data-stu-id="f4401-251">For more details, you can find the latest reports in the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span>

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a><span data-ttu-id="f4401-252">Microsoft 是否可以修改租户的审批人列表？</span><span class="sxs-lookup"><span data-stu-id="f4401-252">Can Microsoft modify the list of approvers for my tenant?</span></span> <span data-ttu-id="f4401-253">如果没有，它是如何防止的？</span><span class="sxs-lookup"><span data-stu-id="f4401-253">If not, how is it prevented?</span></span>

<span data-ttu-id="f4401-254">只有组织中的全球管理员才能指定谁可以批准客户密码箱请求。</span><span class="sxs-lookup"><span data-stu-id="f4401-254">Only a global administrator in your organization can specify who can approve Customer Lockbox requests.</span></span> <span data-ttu-id="f4401-255">这意味着只有 Azure 活动目录中的全局管理员组的成员才能指定谁可以批准请求。</span><span class="sxs-lookup"><span data-stu-id="f4401-255">That means only the members of the Global administrator group in Azure Active Directory can specify who can approve request.</span></span> <span data-ttu-id="f4401-256">Azure 活动目录中全局管理员组的成员身份仅由组织管理。</span><span class="sxs-lookup"><span data-stu-id="f4401-256">Membership of the Global administrator group in Azure Active Directory is managed only by your organization.</span></span>

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a><span data-ttu-id="f4401-257">如果我需要有关内容访问请求的更多信息来批准它，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="f4401-257">What if I need more information about a content access request to approve it?</span></span>

<span data-ttu-id="f4401-258">每个客户密码箱请求都包含 Office 365 服务请求编号。</span><span class="sxs-lookup"><span data-stu-id="f4401-258">Each Customer Lockbox request contains an Office 365 service request number.</span></span> <span data-ttu-id="f4401-259">您可以联系 Microsoft 支持并参考此服务号码以获取有关请求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4401-259">You can contact Microsoft Support and reference this service number to get more information about the request.</span></span>

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a><span data-ttu-id="f4401-260">批准客户密码箱请求后，权限有效多长时间？</span><span class="sxs-lookup"><span data-stu-id="f4401-260">When a Customer Lockbox request is approved, how long are the permissions valid?</span></span>

<span data-ttu-id="f4401-261">目前，授予 Microsoft 工程师的访问权限的最长期限为 4 小时。</span><span class="sxs-lookup"><span data-stu-id="f4401-261">Currently, the maximum period for the access permissions granted to the Microsoft engineer is 4 hours.</span></span> <span data-ttu-id="f4401-262">微软工程师也可以请求较短的周期。</span><span class="sxs-lookup"><span data-stu-id="f4401-262">The Microsoft engineer can also request a shorter period.</span></span>

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a><span data-ttu-id="f4401-263">如何获取所有客户密码箱请求的历史记录？</span><span class="sxs-lookup"><span data-stu-id="f4401-263">How can I get a history of all Customer Lockbox requests?</span></span>

<span data-ttu-id="f4401-264">所有客户密码箱请求都在 Microsoft 365 管理中心查看。</span><span class="sxs-lookup"><span data-stu-id="f4401-264">All Customer Lockbox requests are viewed in the Microsoft 365 admin center.</span></span>

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a><span data-ttu-id="f4401-265">如何将内容访问请求与相关的审核日志相关联？</span><span class="sxs-lookup"><span data-stu-id="f4401-265">How do I correlate the content access requests with the related audit logs?</span></span>

<span data-ttu-id="f4401-266">合规中心活动源包含客户密码箱的日志活动。</span><span class="sxs-lookup"><span data-stu-id="f4401-266">The Compliance Center Activity Feed contains log activities of Customer Lockbox.</span></span> <span data-ttu-id="f4401-267">客户可以根据收到的电子邮件请求从活动源中交叉引用客户密码箱日志活动。</span><span class="sxs-lookup"><span data-stu-id="f4401-267">Customers can cross-reference the Customer Lockbox log activities from the activity feed against the email request they receive.</span></span>

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a><span data-ttu-id="f4401-268">如果客户未响应客户密码箱请求，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="f4401-268">What happens when a customer doesn't respond to a Customer Lockbox request?</span></span>

<span data-ttu-id="f4401-269">客户密码箱请求的默认持续时间为 12 小时。</span><span class="sxs-lookup"><span data-stu-id="f4401-269">Customer Lockbox requests have a default duration of 12 hours.</span></span> <span data-ttu-id="f4401-270">如果您在 12 小时内未回复请求，则该请求将过期。</span><span class="sxs-lookup"><span data-stu-id="f4401-270">If you don't respond to a request within 12 hour, the request expires.</span></span>

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a><span data-ttu-id="f4401-271">当客户拒绝客户密码箱请求时，Microsoft 会执行什么操作？</span><span class="sxs-lookup"><span data-stu-id="f4401-271">What does Microsoft do when a customer rejects a Customer Lockbox request?</span></span>

<span data-ttu-id="f4401-272">如果客户拒绝客户密码箱请求，则无法访问客户内容。</span><span class="sxs-lookup"><span data-stu-id="f4401-272">If a customer rejects a Customer Lockbox request, no access to customer content occurs.</span></span> <span data-ttu-id="f4401-273">如果组织中的用户继续遇到需要 Microsoft 访问客户内容以解决此问题的服务问题，则服务问题可能会仍然存在，Microsoft 将通知用户。</span><span class="sxs-lookup"><span data-stu-id="f4401-273">If a user in your organization continues to experience a service issue requiring Microsoft to access customer content to resolve the issue, then the service issue might persist and Microsoft will inform the user about this.</span></span>

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a><span data-ttu-id="f4401-274">客户密码箱是否可防止执法机构或其他第三方的数据请求？</span><span class="sxs-lookup"><span data-stu-id="f4401-274">Does Customer Lockbox protect against data requests from law enforcement agencies or other third parties?</span></span>

<span data-ttu-id="f4401-275">否。</span><span class="sxs-lookup"><span data-stu-id="f4401-275">No.</span></span> <span data-ttu-id="f4401-276">微软认真对待第三方对客户数据的请求。</span><span class="sxs-lookup"><span data-stu-id="f4401-276">Microsoft takes third-party requests for customer data seriously.</span></span> <span data-ttu-id="f4401-277">作为云服务提供商，Microsoft 始终倡导客户数据的隐私。</span><span class="sxs-lookup"><span data-stu-id="f4401-277">As a cloud service provider, Microsoft always advocates for the privacy of customer data.</span></span> <span data-ttu-id="f4401-278">如果我们收到传票，Microsoft 总是尝试将第三方重定向到客户以获取信息。</span><span class="sxs-lookup"><span data-stu-id="f4401-278">In the event we get a subpoena, Microsoft always attempts to redirect the third party to the customer to obtain the information.</span></span> <span data-ttu-id="f4401-279">（阅读布拉德·史密斯的博客：[保护客户数据免受政府窥探）。](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)</span><span class="sxs-lookup"><span data-stu-id="f4401-279">(Read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)).</span></span> <span data-ttu-id="f4401-280">我们会定期发布有关 Microsoft 收到的执法请求[的详细信息。](https://www.microsoft.com/en-us/corporate-responsibility/lerr)</span><span class="sxs-lookup"><span data-stu-id="f4401-280">We periodically publish [detailed information](https://www.microsoft.com/en-us/corporate-responsibility/lerr) about the law enforcement requests that Microsoft receives.</span></span>

<span data-ttu-id="f4401-281">有关详细信息，请参阅[Microsoft 信任中心（](https://www.microsoft.com/en-us/trustcenter/default.aspx)有关第三方数据请求）和[在线服务条款](https://www.microsoft.com/Licensing/product-licensing/products.aspx)中的"披露客户数据"部分。</span><span class="sxs-lookup"><span data-stu-id="f4401-281">See the [Microsoft Trust Center](https://www.microsoft.com/en-us/trustcenter/default.aspx) regarding third-party data requests and the "Disclosure of Customer Data" section in the [Online Services Terms](https://www.microsoft.com/Licensing/product-licensing/products.aspx) for more information.</span></span>

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a><span data-ttu-id="f4401-282">Microsoft 如何确保其员工在 Office 365 应用程序中没有长期访问客户内容的访问权限？</span><span class="sxs-lookup"><span data-stu-id="f4401-282">How does Microsoft ensure that a member of its staff doesn't have standing access to customer content in Office 365 applications?</span></span>

<span data-ttu-id="f4401-283">Microsoft 通过访问控制系统和检测措施实施广泛的预防措施，以识别和解决规避这些访问控制系统的企图。</span><span class="sxs-lookup"><span data-stu-id="f4401-283">Microsoft implements extensive preventive measures through access control systems, and detective measures to identify and address attempts to circumvent these access control systems.</span></span> <span data-ttu-id="f4401-284">Office 365 使用最小特权和实时访问的原则运行。</span><span class="sxs-lookup"><span data-stu-id="f4401-284">Office 365 operates with the principles of least privilege and just-in-time access.</span></span> <span data-ttu-id="f4401-285">因此，任何 Microsoft 人员都无权持续访问客户内容。</span><span class="sxs-lookup"><span data-stu-id="f4401-285">Therefore, no Microsoft personnel have permission to access customer content on an ongoing basis.</span></span> <span data-ttu-id="f4401-286">如果授予权限，则其持续时间有限。</span><span class="sxs-lookup"><span data-stu-id="f4401-286">If permission is granted, it is for a limited duration.</span></span> 

<span data-ttu-id="f4401-287">Office 365 使用名为*Lockbox*的访问控制系统来处理权限请求，这些请求授予在服务中执行操作和管理功能的能力。</span><span class="sxs-lookup"><span data-stu-id="f4401-287">Office 365 uses an access control system called *Lockbox* to process requests for permissions that grant the ability to perform operational and administrative functions within the service.</span></span> <span data-ttu-id="f4401-288">操作员必须使用 Lockbox 请求访问客户内容，然后要求第二个人对请求执行操作（例如，批准该请求），然后才能授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="f4401-288">An operator must request access to customer content using Lockbox, which then requires a second person to take action on the request (e.g., approve it) before access is granted.</span></span> <span data-ttu-id="f4401-289">该第二个人不能是请求者，必须指定该人员来批准对客户内容的访问。</span><span class="sxs-lookup"><span data-stu-id="f4401-289">That second person can't be the requestor and must be designated to approve access to customer content.</span></span> <span data-ttu-id="f4401-290">仅当请求获得批准时，操作员才会获得对客户内容的临时访问权限。</span><span class="sxs-lookup"><span data-stu-id="f4401-290">Only if the request is approved does the operator acquire temporary access to customer content.</span></span> <span data-ttu-id="f4401-291">提升期到期后，锁箱将撤消访问权限。</span><span class="sxs-lookup"><span data-stu-id="f4401-291">After the elevation period expires, Lockbox revokes access.</span></span>

<span data-ttu-id="f4401-292">有关 Microsoft 常规安全实践的更多详细信息，请参阅[在线服务条款。](https://www.microsoft.com/licensing/product-licensing/products)</span><span class="sxs-lookup"><span data-stu-id="f4401-292">Please refer to the [Online Services Terms](https://www.microsoft.com/licensing/product-licensing/products) for more details about Microsoft general security practices.</span></span>

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a><span data-ttu-id="f4401-293">在什么情况下，Microsoft 工程师需要访问我的内容？</span><span class="sxs-lookup"><span data-stu-id="f4401-293">Under what circumstances do Microsoft engineers need access to my content?</span></span>

<span data-ttu-id="f4401-294">Microsoft 工程师需要访问客户内容的最常见情况是，客户发出需要访问以进行故障排除的支持请求。</span><span class="sxs-lookup"><span data-stu-id="f4401-294">The most common scenario where Microsoft engineers need access customer content is when the customer makes a support request requiring access for troubleshooting.</span></span> <span data-ttu-id="f4401-295">Office 365 的一项基本原则是，该服务在不使用 Microsoft 访问客户内容的情况下运行。</span><span class="sxs-lookup"><span data-stu-id="f4401-295">A foundational principle of Office 365 is that the service operates without Microsoft access to customer content.</span></span> <span data-ttu-id="f4401-296">Microsoft 执行的几乎所有服务操作都是完全自动化的，人工参与受到高度控制，并且从客户内容中抽象出来。</span><span class="sxs-lookup"><span data-stu-id="f4401-296">Nearly all service operations performed by Microsoft are fully automated and human involvement is highly controlled and abstracted away from customer content.</span></span> <span data-ttu-id="f4401-297">Office 365 的目标是在客户批准 Microsoft 访问的特定请求之前，不需要访问客户内容来支持服务。</span><span class="sxs-lookup"><span data-stu-id="f4401-297">The goal for Office 365 is access to customer content to support the service isn't needed until the customer approves a specific request for Microsoft access.</span></span>

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a><span data-ttu-id="f4401-298">我已经认为我的数据在 Microsoft 云中是安全的，那么为什么我需要客户密码箱？</span><span class="sxs-lookup"><span data-stu-id="f4401-298">I already thought my data was secure with the Microsoft cloud, so why do I need Customer Lockbox?</span></span>

<span data-ttu-id="f4401-299">客户密码箱通过为客户提供为服务操作提供显式访问授权的能力，提供了额外的控制层。</span><span class="sxs-lookup"><span data-stu-id="f4401-299">Customer Lockbox provides an extra layer of control by offering customers the ability to give explicit access authorization for service operations.</span></span> <span data-ttu-id="f4401-300">通过证明是明确的数据访问授权程序已经到位，客户密码箱还帮助客户履行某些合规义务，如 HIPAA 和 FEDRAMP。</span><span class="sxs-lookup"><span data-stu-id="f4401-300">By demonstrating that procedures are in place for explicit data access authorization, Customer Lockbox also helps customers meet certain compliance obligations such as HIPAA and FEDRAMP.</span></span>
