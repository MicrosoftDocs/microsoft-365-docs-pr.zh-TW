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
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a>使用 Office 365 郵件加密為貴組織建立敏感性資訊類型原則

您可以使用 Exchange 邮件流规则或 Office 365 数据丢失防护 （DLP） 使用 Office 365 邮件加密创建敏感信息类型策略。 要创建 Exchange 邮件流规则，可以使用 Exchange 管理中心 （EAC） 或 PowerShell。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>使用 EAC 中的邮件流规则创建策略

登录到 Exchange 管理中心 （EAC） 并**转到"邮件流** > **规则"。** 在"规则"页上，创建应用 Office 365 邮件加密的规则。 您可以根据消息或附件中存在某些关键字或敏感信息类型等条件创建规则。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>使用 PowerShell 中的邮件流规则创建策略

使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。 使用 Set-IRM 配置和新传输规则 cmdlet 创建策略。

### <a name="example-mail-flow-rule-created-with-powershell"></a>使用 PowerShell 创建的邮件流规则示例

在 PowerShell 中运行以下命令以创建 Exchange 邮件流规则，该规则*使用"仅加密"* 策略自动加密在组织外发送的电子邮件（如果电子邮件或其附件包含以下敏感信息）类型：

- ABA 路由编号
- 信用卡号码
- 缉毒署（DEA）编号
- 美国/英国 护照号码
- 美国银行帐号
- 美国个人纳税人识别号 （ITIN）
- 美国社会安全号码 （SSN）

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

有关详细信息，请参阅设置[IRM 配置](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps)和新[传输规则](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps)。

## <a name="how-recipients-access-attachments"></a>收件人如何访问附件

在 Office 365 加密邮件后，收件人在访问和打开加密电子邮件时可以不受限制地访问附件。

## <a name="to-prepare-for-this-change"></a>准备此更改

您可能需要更新任何适用的最终用户文档和培训材料，以便为组织中人员进行此更改的准备。 根据需要与用户共享这些 Office 365 邮件加密资源：

- [在 PC Outlook 中发送、查看和回复加密邮件](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Office 365 基本视频：办公室邮件加密](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>在审核日志中查看这些更改

Office 365 审核此活动，并使其可供 Office 365 管理员使用。 操作为"新传输规则"，安全&合规性中心审核日志搜索的示例审核条目片段如下：

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>禁用或自定义敏感信息类型策略

创建 Exchange 邮件流规则后，可以通过转到 Exchange 管理中心 （EAC）**中的"邮件流** > **规则"** 来[禁用或编辑该规则，](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)并禁用"*加密出站敏感电子邮件（开箱即用规则）"* 规则".
