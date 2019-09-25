---
title: 管理 Office 365 郵件加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 设置完 Office 365 消息加密 （OME） 后，可以通过多种方式自定义部署配置。 例如，您可以配置是否启用一次性密码、在 Web 上的 Outlook 中显示"保护"按钮等。 本文中的任务描述了如何。
ms.openlocfilehash: 5e087211ec72c9cc37896a9a48cc01ce3c1a8d07
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077183"
---
# <a name="manage-office-365-message-encryption"></a>管理 Office 365 郵件加密

设置完 Office 365 消息加密 （OME） 后，可以通过多种方式自定义部署配置。 例如，您可以配置是否启用一次性密码、在 Web 上的 Outlook 中显示**加密**按钮等。 本文中的任务描述了如何。

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>管理 Google、Yahoo 和 Microsoft 帐户收件人是否可以使用这些帐户登录到 Office 365 邮件加密门户

设置新的 Office 365 邮件加密功能时，组织中的用户可以向 Office 365 组织外部的收件人发送邮件。 如果收件人使用社交*ID（* 如 Google 帐户、雅虎帐户或 Microsoft 帐户），则收件人可以使用社交 ID 登录 OME 门户。 如果需要，您可以选择不允许收件人使用社交标识登录到 OME 门户。
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>管理收件人是否可以使用社交标识登录到 OME 门户
  
1. [使用远程电源外壳连接到在线交换。](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)

2. 使用社交 IdSignIn 参数运行 Set-OME 配置 cmdlet，如下所示：

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   例如，要禁用社交 ID：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   要启用社交 ID：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>管理 Office 365 邮件加密门户的一次性密码的使用

如果 OME 加密的邮件的收件人不使用 Outlook，而不考虑收件人使用的帐户，则收件人将收到一个限时 Web 视图链接，允许他们阅读邮件。 此链接包括一次性密码。 作为管理员，您可以决定收件人是否可以使用一次性密码登录到 OME 门户。
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>管理 OME 是否生成一次性密码
  
1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，然后启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。

2. 使用 OTP 启用参数运行 Set-OME 配置 cmdlet：

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   例如，要禁用一次性密码：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   要启用一次性密码：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>管理 Web Outlook 中"加密"按钮的显示

作为管理员，您可以管理是否向最终用户显示此按钮。
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>管理"加密"按钮是否显示在 Web 上的 Outlook 中
  
1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，然后启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。

2. 使用 -简化客户端访问启用参数运行 Set-IRM 配置 cmdlet：

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   例如，要**禁用"加密"** 按钮：

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   要**启用"加密"** 按钮：

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>为 iOS 邮件应用用户启用服务端电子邮件解密

iOS 邮件应用无法解密受 Office 365 邮件加密保护的邮件。 作为 Office 365 管理员，您可以对传递到 iOS 邮件应用的邮件应用服务端解密。 当您选择使用服务端解密时，服务会向 iOS 设备发送消息的解密副本。 客户端设备存储消息的解密副本。 即使 iOS 邮件应用不将客户端使用权限应用于用户，该邮件也会保留有关使用权限的信息。 用户可以复制或打印邮件，即使他们最初没有这样做的权限。 但是，如果用户尝试完成需要 Office 365 邮件服务器的操作（如转发邮件），则如果用户最初没有执行此操作的权限，则服务器将不允许执行该操作。 但是，最终用户可以通过从 iOS 邮件应用中的不同帐户转发邮件来绕过"不转发"使用限制。 无论您是否设置了邮件的服务端解密，在 iOS 邮件应用中都无法查看加密邮件和受权限保护邮件的附件。
  
如果选择不允许将解密邮件发送给 iOS 邮件应用用户，则用户会收到一条消息，指出他们无权查看邮件。 默认情况下，未启用电子邮件的服务端解密。
  
有关详细信息，以及有关客户体验的视图，请参阅[查看 iPhone 或 iPad 上的加密邮件。](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>管理 iOS 邮件应用用户是否可以查看受 Office 365 邮件加密保护的邮件
  
1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，然后启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。

2. 使用"允许RMS 支持未启迪应用"参数运行"设置活动同步组织 cmdlet"：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   例如，要将服务配置为在邮件发送到未开明的应用（如 iOS 邮件应用）之前解密邮件：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   或者，要将服务配置为不向未启用的应用发送解密消息：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> 单个邮箱策略 （OWA/ActiveSync） 将覆盖这些设置（即，如果 -IRMEnabled 在相应的 OWA 邮箱策略或 ActiveSync 邮箱策略中设置为 False，则这些配置将不适用）。

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>为 Web 浏览器邮件客户端启用服务端解密电子邮件附件

通常，当您使用 Office 365 邮件加密时，附件会自动加密。 作为 Office 365 管理员，您可以对用户从 Web 浏览器下载的电子邮件附件应用服务端解密。
  
使用服务端解密时，服务会向设备发送文件的解密副本。 邮件仍加密。 即使浏览器不将客户端使用权限应用于用户，电子邮件附件也会保留有关使用权限的信息。 用户可以复制或打印电子邮件附件，即使他们最初没有这样做的权限。 但是，如果用户尝试完成需要 Office 365 邮件服务器的操作（如转发附件），则如果用户最初没有执行此操作的权限，则服务器将不允许执行该操作。
  
无论您是否设置了服务端附件解密，用户都无法在 iOS 邮件应用中查看加密邮件和受权限保护邮件的任何附件。
  
如果选择不允许解密的电子邮件附件（默认设置），则用户会收到一条消息，指出他们无权查看附件。
  
有关 Office 365 如何使用"仅加密"选项实现电子邮件和电子邮件附件加密的详细信息，请参阅[电子邮件的"仅加密"选项。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>管理是否从 Web 浏览器下载时解密电子邮件附件
  
1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，然后启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。

2. 使用"解密附件从门户"参数运行 Set-IRM 配置 cmdlet：

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   例如，要将服务配置为在用户从 Web 浏览器下载电子邮件附件时解密这些附件：

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   要将服务配置为在下载时保留加密的电子邮件附件：

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a>确保所有外部收件人使用 OME 门户读取加密邮件 – 仅限 Office 365 高级邮件加密

如果您有 Office 365 高级邮件加密，则可以使用自定义品牌模板强制收件人接收包装邮件，指示他们在 OME 门户中读取加密电子邮件，而不是在 Web 上使用 Outlook 或 Outlook。 如果您使用该控件希望更好地控制收件人使用他们收到的邮件的方式，则可能需要执行此操作。 例如，如果外部收件人在 Web 门户中查看电子邮件，则可以为电子邮件设置到期日期，也可以撤消该电子邮件。 这些功能仅通过 OME 门户支持。 创建邮件流规则时，可以使用"加密"选项和"不转发"选项。

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a>创建自定义模板以强制所有外部收件人使用 OME 门户，并确保加密电子邮件可撤销并在 7 天后过期

1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，然后启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。

2. 运行新 OME 配置 cmdlet：

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   要`template name`用于 Office 365 邮件加密自定义品牌模板的名称。 For example,

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. 运行新传输规则 cmdlet：

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    其中：

   - `mail flow rule name`是要用于新邮件流规则的名称。

   - `option name`或`Encrypt`。 `Do Not Forward`

   - `template name`是您为自定义品牌模板提供的名称，例如`One week expiration`。

   要使用"一周过期"模板加密所有外部电子邮件，并应用"仅加密"选项：

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   要使用"一周过期"模板加密所有外部电子邮件，并应用"不转发"选项：

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>自定义电子邮件和 OME 门户的外观

有关如何为组织自定义 OME 的详细信息，请参阅[将组织的品牌添加到加密邮件](add-your-organization-brand-to-encrypted-messages.md)中。
  
## <a name="disable-the-new-capabilities-for-ome"></a>禁用 OME 的新功能

我们希望它不会实现它，但如果需要，禁用 OME 的新功能非常简单。 首先，您需要删除已创建的任何使用新的 OME 功能的邮件流规则。 有关删除邮件流规则的信息，请参阅[管理邮件流规则](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。 然后，在 Exchange 在线电源外壳中完成这些步骤。
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>禁用 OME 的新功能
  
1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。

2. 如果在 Web 上的 Outlook 中启用**了"加密"** 按钮，请禁用该按钮，使用"简化客户端访问启用"参数运行 Set-IRM 配置 cmdlet。 否则，请跳过此步骤。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. 禁用 OME 的新功能，使用设置为 false 的 AzureRMS 许可启用参数运行 Set-IRM 配置 cmdlet：

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
