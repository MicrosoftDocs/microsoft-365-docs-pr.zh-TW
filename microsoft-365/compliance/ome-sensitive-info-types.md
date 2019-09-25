---
title: 使用 Office 365 郵件加密為貴組織建立敏感性資訊類型原則
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: 摘要：针对敏感信息类型的 Office 365 邮件加密策略。
ms.openlocfilehash: d74712798ba9d46614b5fc916e4b1ce111582304
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077973"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a><span data-ttu-id="a39c6-103">使用 Office 365 郵件加密為貴組織建立敏感性資訊類型原則</span><span class="sxs-lookup"><span data-stu-id="a39c6-103">Create a sensitive information type policy for your organization using Office 365 Message Encryption</span></span>

<span data-ttu-id="a39c6-104">您可以使用 Exchange 邮件流规则或 Office 365 数据丢失防护 （DLP） 使用 Office 365 邮件加密创建敏感信息类型策略。</span><span class="sxs-lookup"><span data-stu-id="a39c6-104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="a39c6-105">要创建 Exchange 邮件流规则，可以使用 Exchange 管理中心 （EAC） 或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a39c6-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="a39c6-106">使用 EAC 中的邮件流规则创建策略</span><span class="sxs-lookup"><span data-stu-id="a39c6-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="a39c6-107">登录到 Exchange 管理中心 （EAC） 并**转到"邮件流** > **规则"。**</span><span class="sxs-lookup"><span data-stu-id="a39c6-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="a39c6-108">在"规则"页上，创建应用 Office 365 邮件加密的规则。</span><span class="sxs-lookup"><span data-stu-id="a39c6-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="a39c6-109">您可以根据消息或附件中存在某些关键字或敏感信息类型等条件创建规则。</span><span class="sxs-lookup"><span data-stu-id="a39c6-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="a39c6-110">使用 PowerShell 中的邮件流规则创建策略</span><span class="sxs-lookup"><span data-stu-id="a39c6-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="a39c6-111">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="a39c6-111">Use a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="a39c6-112">有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="a39c6-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="a39c6-113">使用 Set-IRM 配置和新传输规则 cmdlet 创建策略。</span><span class="sxs-lookup"><span data-stu-id="a39c6-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

### <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="a39c6-114">使用 PowerShell 创建的邮件流规则示例</span><span class="sxs-lookup"><span data-stu-id="a39c6-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="a39c6-115">在 PowerShell 中运行以下命令以创建 Exchange 邮件流规则，该规则*使用"仅加密"* 策略自动加密在组织外发送的电子邮件（如果电子邮件或其附件包含以下敏感信息）类型：</span><span class="sxs-lookup"><span data-stu-id="a39c6-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="a39c6-116">ABA 路由编号</span><span class="sxs-lookup"><span data-stu-id="a39c6-116">ABA routing number</span></span>
- <span data-ttu-id="a39c6-117">信用卡号码</span><span class="sxs-lookup"><span data-stu-id="a39c6-117">Credit card Number</span></span>
- <span data-ttu-id="a39c6-118">缉毒署（DEA）编号</span><span class="sxs-lookup"><span data-stu-id="a39c6-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="a39c6-119">美国/英国</span><span class="sxs-lookup"><span data-stu-id="a39c6-119">U.S. / U.K.</span></span> <span data-ttu-id="a39c6-120">护照号码</span><span class="sxs-lookup"><span data-stu-id="a39c6-120">passport number</span></span>
- <span data-ttu-id="a39c6-121">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="a39c6-121">U.S. bank account number</span></span>
- <span data-ttu-id="a39c6-122">美国个人纳税人识别号 （ITIN）</span><span class="sxs-lookup"><span data-stu-id="a39c6-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="a39c6-123">美国社会安全号码 （SSN）</span><span class="sxs-lookup"><span data-stu-id="a39c6-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="a39c6-124">有关详细信息，请参阅设置[IRM 配置](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps)和新[传输规则](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="a39c6-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps) and [New-TransportRule](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="a39c6-125">收件人如何访问附件</span><span class="sxs-lookup"><span data-stu-id="a39c6-125">How recipients access attachments</span></span>

<span data-ttu-id="a39c6-126">在 Office 365 加密邮件后，收件人在访问和打开加密电子邮件时可以不受限制地访问附件。</span><span class="sxs-lookup"><span data-stu-id="a39c6-126">After Office 365 encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="a39c6-127">准备此更改</span><span class="sxs-lookup"><span data-stu-id="a39c6-127">To prepare for this change</span></span>

<span data-ttu-id="a39c6-128">您可能需要更新任何适用的最终用户文档和培训材料，以便为组织中人员进行此更改的准备。</span><span class="sxs-lookup"><span data-stu-id="a39c6-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="a39c6-129">根据需要与用户共享这些 Office 365 邮件加密资源：</span><span class="sxs-lookup"><span data-stu-id="a39c6-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="a39c6-130">在 PC Outlook 中发送、查看和回复加密邮件</span><span class="sxs-lookup"><span data-stu-id="a39c6-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="a39c6-131">Office 365 基本视频：办公室邮件加密</span><span class="sxs-lookup"><span data-stu-id="a39c6-131">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="a39c6-132">在审核日志中查看这些更改</span><span class="sxs-lookup"><span data-stu-id="a39c6-132">View these changes in the Audit log</span></span>

<span data-ttu-id="a39c6-133">Office 365 审核此活动，并使其可供 Office 365 管理员使用。</span><span class="sxs-lookup"><span data-stu-id="a39c6-133">Office 365 audits this activity and makes it available to Office 365 administrators.</span></span> <span data-ttu-id="a39c6-134">操作为"新传输规则"，安全&合规性中心审核日志搜索的示例审核条目片段如下：</span><span class="sxs-lookup"><span data-stu-id="a39c6-134">The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="a39c6-135">禁用或自定义敏感信息类型策略</span><span class="sxs-lookup"><span data-stu-id="a39c6-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="a39c6-136">创建 Exchange 邮件流规则后，可以通过转到 Exchange 管理中心 （EAC）**中的"邮件流** > **规则"** 来[禁用或编辑该规则，](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)并禁用"*加密出站敏感电子邮件（开箱即用规则）"* 规则".</span><span class="sxs-lookup"><span data-stu-id="a39c6-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
