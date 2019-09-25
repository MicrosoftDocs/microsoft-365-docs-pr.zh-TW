---
title: 撤銷由 Office 365 進階郵件加密所加密的電子郵件
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 作为 Office 365 管理员，您可以撤消使用 Office 365 高级邮件加密加密的某些电子邮件。
ms.openlocfilehash: e55129f68c7add589bd973b36f069d7cdbf631cf
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077581"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a>撤銷由 Office 365 進階郵件加密所加密的電子郵件

电子邮件吊销作为 Office 365 高级邮件加密的一部分提供。 在某些订阅中，Office 365 高级邮件加密在 Office 365 邮件加密之上可用。 高级邮件加密包含在[Microsoft 365 企业 E5、Office](https://www.microsoft.com/microsoft-365/enterprise/home)365 企业版 E5 和 Office 365 教育版 A5 中。 如果您的组织具有不包括 Office 365 高级邮件加密的 Office 365 订阅，则可以购买高级邮件加密作为符合高级合规性 SKU 的 E5 合规性的附加组件。

本文是关于[Office 365 消息加密](ome.md)的一系列较大文章的一部分。

如果使用 Office 365 高级邮件加密对邮件进行了加密，并且您是 Office 365 管理员，则可以在某些情况下撤消该邮件。 本文介绍了可以撤销的情况以及如何执行此操作。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>可以撤消的加密电子邮件

如果收件人收到基于链接的、品牌加密的电子邮件，则可以撤消加密电子邮件。 如果收件人在支持的 Outlook 客户端中收到本机内联体验，则无法撤消这些电子邮件。

收件人是否收到基于链接的体验或内联体验取决于收件人标识类型：Office 365 和 Microsoft 帐户收件人（例如，outlook.com用户）在支持的 Outlook 客户端中获得内联体验。 所有其他收件人类型（如 Gmail 收件人）都将获得基于链接的体验。

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>已吊销加密电子邮件的收件人体验

电子邮件被吊销后，收件人在通过 Office 365 邮件加密门户访问加密电子邮件时收到错误："发件人已吊销邮件"。

![显示已吊销加密电子邮件的屏幕截图。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>如何撤销加密的电子邮件

### <a name="step-1-obtain-the-message-id-of-the-email"></a>步驟 1。 获取电子邮件的邮件 ID

在撤销加密邮件之前，您需要收集邮件的邮件 ID。 MessageId 的格式通常为：

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

有多种方法可以查找要撤消的电子邮件的邮件 ID。 本节介绍几个选项，但您可以使用任何提供 ID 的方法。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>在安全&amp;合规性中心中使用邮件跟踪来标识要撤销的电子邮件的邮件 ID

1. 在[Office 365 安全&合规中心 中，使用"新邮件跟踪"](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)按发件人或收件人搜索电子邮件。

2. 找到电子邮件后，选择它可**显示"邮件跟踪详细信息"** 窗格。 **展开"详细信息"** 以查找邮件 ID。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>在安全&amp;合规性中心中使用 Office 邮件加密报告来标识要撤消的电子邮件的邮件 ID

1. 在安全&amp;合规性中心中，导航到**邮件加密报告**。 有关此报告的信息，请参阅[在&amp;安全合规性中心中查看电子邮件安全报告。](view-email-security-reports.md)

2. 选择"**查看详细信息"** 表并标识要撤销的邮件。

3. 双击邮件以查看包含消息 ID 的详细信息。

### <a name="step-2-verify-that-the-mail-is-revocable"></a>步驟 2。 验证邮件是否可撤销

要验证是否可以撤消邮件，请在安全&amp;合规性中心的详细信息表中检查"取消状态"字段是否在"加密"报表中**** 可见。

要验证是否可以使用 Windows Powershell 撤消特定电子邮件，请完成以下步骤。

1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。

2. 运行 Get-OMEMessage 状态 cmdlet，如下所示：

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   这将返回消息的主题以及消息是否可撤销。 For example,

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a>步驟 3。 撤销邮件

知道要撤消的电子邮件的邮件 ID 并验证邮件可撤销后，可以使用安全&amp;合规性中心或 Windows Powershell 撤消该电子邮件。

使用安全&amp;合规性中心撤销邮件

要撤消安全&amp;合规性中心中的电子邮件，在"加密报告"中，在邮件**的"详细信息"** 表中，**请选择"撤销邮件"。**

您可以使用 Windows Powershell 使用 Set-OMEMessageRevocation cmdlet 撤销电子邮件。

1. [連線至 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 运行 Set-OMEMessageresrescdlet，如下所示：

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 要检查电子邮件是否已吊销，请运行 Get-OMEMessage 状态 cmdlet，如下所示：

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    如果吊销成功，cmdlet 将返回以下结果：  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有关 Office 365 高级邮件加密的详细信息

- [Office 365 進階郵件加密](ome-advanced-message-encryption.md)

- [Office 365 高级邮件加密 - 电子邮件过期](ome-advanced-expiration.md)

- [消息策略和合规性服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
