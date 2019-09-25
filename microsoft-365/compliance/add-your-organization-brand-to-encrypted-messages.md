---
title: 将组织品牌添加到加密邮件
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 作为 Office 365 全局管理员，您可以将组织的品牌应用于组织的加密电子邮件和加密门户的内容。
ms.openlocfilehash: dd08ffad4a50cafd90f2306645e93e623b8076cd
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076760"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>將貴組織的品牌新增至您的加密郵件

作为 Exchange 联机或 Exchange 联机保护管理员，您可以应用公司品牌来自定义组织的 Office 365 邮件加密电子邮件的外观和加密门户的内容。 使用 Get-OME 配置和设置-OME 配置 Windows PowerShell cmdlet，您可以自定义加密电子邮件收件人的查看体验的以下方面：
  
- 包含加密訊息的電子郵件簡介文字

- 包含加密訊息的電子郵件免責聲明文字

- 显示在 OME 门户中的文本

- 电子邮件和 OME 门户中显示的徽标

- 电子邮件和 OME 门户中的背景颜色

您也可以隨時回復為預設的外觀與風格。

 如果希望获得更多控制，可以使用 Office 365 高级邮件加密，并为来自组织的加密电子邮件创建多个模板。 使用这些模板，您可以控制的不仅仅是电子邮件的外观，还可以控制最终用户体验的某些部分。 例如，您可以指定应用了此模板的邮件收件人以及使用这些帐户的用户是否可以使用这些帐户登录到 Office 365 邮件加密门户。 您可以使用模板来实现多个用例，例如：

- 每个部门的模板，如财务、销售等。

- 不同产品的模板

- 不同地理区域或国家/地区的模板

- 是否希望允许撤销电子邮件

- 是否希望发送给外部收件人的电子邮件在指定天数后过期。

创建模板后，可以使用 Exchange 邮件流规则将它们应用于加密的电子邮件。 如果您有 Office 365 高级邮件加密，则可以撤消使用这些模板标记的任何电子邮件。
  
||
|:-----|
|本文是关于 Office 365 消息加密的较大系列文章的一部分。 本文面向管理员和 ITPros。 如果您只想查找有关发送或接收加密邮件的信息，请参阅[Office 365 邮件加密 （OME）](ome.md)中的文章列表，并找到最适合您需求的文章。|
||

## <a name="create-branding-templates"></a>创建品牌模板

您可以使用"新建 OME 配置 cmdlet"在 Windows PowerShell 中为您的组织创建品牌模板。 创建模板后，可以使用 Set-OME 配置 cmdlet 定义模板部分。 您可以创建多个模板。

![可自定义的电子邮件部件](media/ome-template-breakout.png)
  
1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。

2. 使用 New-OME 配置 cmdlet 创建新模板。

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   New-OMEConfiguration -Identity "Branding template 1"
   ```

3. 定义使用 Set-OME 配置 cmdlet 刚刚定义的模板的自定义，如[Set-OME 配置](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述，或使用下表进行指导。

|**若要自訂此加密經驗功能**|**使用这些命令**|
|:-----|:-----|
|背景色彩|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|商標|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支援的檔案格式：.png、.jpg、.bmp 或 .tiff  <br/> 標誌檔案的最佳大小：小於 40 KB  <br/> 標誌影像的最佳大小：170x70 像素|
|发件人姓名和电子邮件地址旁边的文本|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|"阅读消息"按钮上显示的文本|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|显示在"阅读消息"按钮下方的文本|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|包含加密訊息之電子郵件中的免責聲明|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|出現在加密郵件檢視入口網站上方的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|使用此自定义模板的一次性密码启用或禁用身份验证|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **範例：** <br/>为此自定义模板启用一次性密码 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> 禁用此自定义模板的一次性密码 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|启用或禁用此自定义模板的 Microsoft、Google 或 Yahoo 标识的身份验证|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **範例：** <br/>为此自定义模板启用社交 ID <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> 禁用此自定义模板的社交 ID <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a>从 OME 门户中删除品牌自定义和由 OME 加密的电子邮件
  
1. [連線至 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用"**设置-OME**配置"cmdlet，[如"设置-OME 配置"](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述。 要从免责声明文本、电子邮件文本和门户文本值中删除组织的品牌自定义项，请将值设置为空字符串 。 `""` 对于所有图像值（如徽标），将值设置为`"$null"`。

**加密自訂選項**

**將加密體驗的這項功能回復為預設文字和影像**|**使用这些命令**|
|:-----|:-----|
|加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|包含加密訊息之電子郵件中的免責聲明|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|出現在加密郵件檢視入口網站上方的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **恢复为默认值的示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
|商標|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **恢复为默认值的示例：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|背景色彩|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **恢复为默认值的示例：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a>创建将自定义品牌应用于加密电子邮件的 Exchange 邮件流规则

创建品牌模板后，可以创建 Exchange 邮件流规则，以基于特定条件应用该自定义品牌。 此类规则将在以下情况下应用自定义品牌：

- 如果电子邮件由来自 Web 上的 Outlook 或 Outlook 客户端（以前称为 Outlook Web 应用）客户端的最终用户手动加密

- 如果电子邮件由 Exchange 邮件流规则或 Office 365 数据丢失防护策略自动加密

有关如何创建应用加密的 Exchange 邮件流规则的信息，请参阅[定义邮件流规则以加密 Office 365 中的电子邮件。](define-mail-flow-rules-to-encrypt-email.md)

1. 在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录到[Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择"**管理员"** 磁贴。

3. 在微软365管理中心，选择**管理中心**\>**交换。**

4. 在 EAC 中，**转到"邮件流**\>**规则"** 并**选择"新建"**![图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)\>**创建新规则。** 有关使用 EAC 的详细信息，请参阅[Exchange 在线交换管理中心。](https://docs.microsoft.com/exchange/exchange-admin-center)

5. **在"名称"** 中键入规则的名称，如销售部门的"品牌"。

6. **在"应用此规则（如果**选择条件）中，从可用条件列表中**选择"发件人位于组织内**的条件"以及所需的其他条件。 例如，您可能希望将特定的品牌模板应用于：

     - 来自财务部门成员发送的所有加密电子邮件
     - 使用特定关键字（如"外部"或"合作伙伴"）发送的加密电子邮件
     - 发送到特定域的加密电子邮件

7. 从**执行以下内容**中，**选择"修改邮件安全性** > **将自定义品牌应用于 OME 消息"。** 接下来，从下拉列表中选择一个品牌模板。

8. （可选）如果希望邮件流规则在自定义品牌之外应用加密，**请选择"****修改邮件安全性"，** 然后**选择"应用 Office 365 邮件加密和权限保护"。** 从列表中选择 RMS 模板，**选择"保存"，** 然后选择"**确定"。**
  
     模板列表包括所有默认模板和选项，以及您为 Office 365 创建的任何自定义模板。 如果列表为空，请确保已使用"[设置新的 Office 365 邮件加密功能"](set-up-new-message-encryption-capabilities.md)中所述的新功能设置 Office 365 邮件加密。 有关默认模板的信息，请参阅[配置和管理 Azure 信息保护的模板。](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates) 有关"**不转发"** 选项的信息，请参阅[电子邮件的"不转发"选项。](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) 有关**仅加密**选项的信息，请参阅[电子邮件的"仅加密"选项。](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

     如果要指定其他操作，可以选择**添加操作。**
