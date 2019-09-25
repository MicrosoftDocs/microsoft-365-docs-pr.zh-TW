---
title: Office 365 郵件加密的舊版資訊
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 07/11/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
description: 如果您尚未将 Office 365 组织迁移到新的 OME 功能，但已部署 OME，则本文中的信息将应用于您的组织。 Microsoft 建议您在您的组织合理时尽快制定计划，以迁移到新的 OME 功能。 有关说明，请参阅设置在 Azure 信息保护之上构建的新 Office 365 消息加密功能。 如果要首先了解有关新功能工作方式的更多信息，请参阅 Office 365 邮件加密。 本文的其余部分是指在新的 OME 功能发布之前的 OME 行为。
ms.openlocfilehash: 70529e9aa5c444ab8fc57d4a9698295e50198725
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077121"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Office 365 郵件加密的舊版資訊

如果您尚未将 Office 365 组织迁移到新的 OME 功能，但已部署 OME，则本文中的信息将应用于您的组织。 Microsoft 建议您在您的组织合理时尽快制定计划，以迁移到新的 OME 功能。 有关说明，请参阅[设置在 Azure 信息保护 之上构建的新 Office 365 消息加密功能。](set-up-new-message-encryption-capabilities.md) 如果要首先了解有关新功能工作方式的更多信息，请参阅[Office 365 邮件加密](ome.md)。 本文的其余部分是指在新的 OME 功能发布之前的 OME 行为。
  
借助 Office 365 邮件加密，您的组织可以在组织内外人员之间发送和接收加密的电子邮件。 Office 365 邮件加密适用于Outlook.com、雅虎、Gmail 和其他电子邮件服务。 电子邮件加密有助于确保只有目标收件人才能查看邮件内容。
  
以下為一些範例：
  
- 银行员工向客户发送信用卡对帐单

- 保险公司代表为客户提供保单详细信息

- 抵押贷款经纪人向客户请求贷款申请的财务信息

- 医疗保健提供者向患者发送医疗保健信息

- 律师向客户或其他律师发送机密信息

## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Office 365 消息加密如何在没有新功能的情况下工作

Office 365 邮件加密是在 Microsoft Azure 权限管理 （Azure RMS） 上构建的在线服务。 使用 Azure RMS，管理员可以定义邮件流规则以确定加密条件。 例如，规则可以要求对发送给特定收件人的所有邮件进行加密。
  
观看此简短视频，了解 Office 365 邮件加密在没有新功能的情况下如何工作。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
当某人在 Exchange Online 中发送与加密规则匹配的电子邮件时，该邮件将随 HTML 附件一起发送。 收件人打开 HTML 附件，并按照说明在 Office 365 邮件加密门户上查看加密邮件。 收件人可以选择使用 Microsoft 帐户或与 Office 365 关联的工作或学校登录或使用一次性密码来查看邮件。 这两个选项都有助于确保只有目标收件人才能查看加密的邮件。 对于新的 OME 功能，此过程非常不同。
  
下图总结了电子邮件通过加密和解密过程的过程。
  
![顯示加密電子郵件路徑的圖表](media/O365-Office365MessageEncryption-Concept.png)
  
有关详细信息，请参阅在新的[OME 功能发布之前的旧版 Office 365 邮件加密的服务信息。](legacy-information-for-message-encryption.md#LegacyServiceInfo)
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>为不使用新的 OME 功能的 Office 365 邮件加密定义邮件流规则

要启用 Office 365 邮件加密而无需新功能，Exchange 联机和交换联机保护管理员定义 Exchange 邮件流规则。 这些规则确定在什么条件下应加密电子邮件，以及删除邮件加密的条件。 为规则设置加密操作时，任何与规则条件匹配的消息在发送之前都将被加密。
  
邮件流规则非常灵活，允许您组合条件，以便在单个规则中满足特定的安全要求。 例如，您可以创建一个规则来加密包含指定关键字并发送给外部收件人的所有邮件。 Office 365 邮件加密还加密来自加密电子邮件收件人的回复，您可以创建一个规则来解密这些回复，以方便您的电子邮件用户。 这样，组织中的用户就不必登录到加密门户来查看答复。
  
有关如何创建 Exchange 邮件流规则的详细信息，请参阅定义[Office 365 邮件加密规则。](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>发送、查看和回复加密的电子邮件

使用 Office 365 邮件加密，电子邮件将根据管理员定义的规则自动加密。 包含加密邮件的电子邮件将到达收件人的收件箱中，并带有附加的 HTML 文件。
  
收件人按照邮件中的说明打开附件，并使用 Microsoft 帐户或与 Office 365 关联的工作或学校进行身份验证。 如果收件人没有任一帐户，则会引导他们创建一个 Microsoft 帐户，以便他们登录以查看加密的邮件。 或者，收件人可以选择获取一次性密码来查看邮件。 登录或使用一次性密码后，收件人可以查看解密邮件并发送加密回复。
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>使用 Office 365 邮件加密自定义加密邮件

作为 Exchange 联机和交换联机保护管理员，您可以自定义加密邮件。 例如，您可以添加公司的品牌和徽标，指定简介，并在加密邮件和收件人查看加密邮件的门户中添加免责声明文本。 您可以使用 Windows PowerShell 指令程式，自訂以下方面的加密電子郵件收件者視覺體驗：
  
- 包含加密訊息的電子郵件簡介文字

- 包含加密訊息的電子郵件免責聲明文字

- 將會出現在訊息檢視入口網站的入口網站文字

- 將會出現在電子郵件和檢視入口網站的標誌

您也可以隨時回復為預設的外觀與風格。
  
下列範例顯示 ContosoPharma 在電子郵件附件中的自訂標誌：
  
![已加密郵件頁面的檢視範例](media/TA-OME-3attachment2.jpg)
  
 **使用组织品牌自定义加密电子邮件和加密门户**
  
1. 使用远程电源外壳联机连接到交换，如[使用远程电源外壳联机连接到交换](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated)中所述。

2. 使用此处描述的 Set-OME 配置 cmdlet：[设置-OME 配置](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)或使用下表进行指导。

   **加密自訂選項**

|**若要自訂此加密經驗功能**|**請使用這些 Windows PowerShell 命令**|
|:-----|:-----|
|加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **示例：**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
|包含加密訊息之電子郵件中的免責聲明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **示例：**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
|出現在加密郵件檢視入口網站上方的文字  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **示例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
|商標  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **示例：**`Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支援的檔案格式：.png、.jpg、.bmp 或 .tiff  <br/> 標誌檔案的最佳大小：小於 40 KB  <br/> 標誌影像的最佳大小：170x70 像素  <br/> |

 **从加密电子邮件和加密门户中删除品牌自定义**
  
1. 使用远程电源外壳联机连接到交换，如[使用远程电源外壳联机连接到交换](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)中所述。

2. 使用此处描述的设置-OME 配置 cmdlet：[设置-OME 配置](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)。 要从免责声明文本、电子邮件文本和门户文本值中删除组织的品牌自定义项，请将值设置为空字符串 。 `""` 对于所有图像值（如徽标），将值设置为`"$null"`。

   **加密自訂選項**

|**將加密體驗的這項功能回復為預設文字和影像**|**請使用這些 Windows PowerShell 命令**|
|:-----|:-----|
|加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **示例：**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|包含加密訊息之電子郵件中的免責聲明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **示例：**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|出現在加密郵件檢視入口網站上方的文字  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **恢复为默认值的示例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|商標  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **恢复为默认值的示例：**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |

## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>在新的 OME 功能发布之前，旧版 Office 365 邮件加密的服务信息
<a name="LegacyServiceInfo"> </a>

下表提供了在新的 OME 功能发布之前 Office 365 消息加密服务的技术详细信息。
  
|**服务详情**|**描述**|
|:-----|:-----|
|客户端设备要求  <br/> |只要可以在支持 Form Post 的现代浏览器中打开 HTML 附件，可以在任何客户端设备上查看加密邮件。  <br/> |
|加密算法和联邦信息处理标准 （FIPS） 合规性  <br/> |Office 365 消息加密使用与 Windows Azure 信息权限管理 （IRM） 相同的加密密钥，并支持加密模式 2（RSA 的 2K 密钥和 SHA-1 系统的 256 位密钥）。 有关基础 IRM 加密模式的详细信息，请参阅[AD RMS 加密模式](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx)。  <br/> |
|支持的消息类型  <br/> |Office 365 邮件加密仅支持具有消息类 ID 为**IPM 的项目。注意**. 有关详细信息，请参阅[项类型和消息类](https://msdn.microsoft.com/library/office/ff861573.aspx)。  <br/> |
|郵件大小限制  <br/> |Office 365 消息加密可以加密高达 25 MB 的邮件。 有关邮件大小限制的详细信息，请参阅[交换联机限制](http://technet.microsoft.com/library/exchange-online-limits.aspx)。  <br/> |
|交换在线电子邮件保留策略  <br/> |联机交换不会存储加密的邮件。  <br/> |
|对 Office 365 邮件加密的语言支持  <br/> | Office 365 邮件加密支持 Office 365 语言，如下所示：  <br/>  传入的电子邮件和附加的 HTML 文件根据发件人的语言设置进行本地化。  <br/>  查看门户根据收件人的浏览器设置进行本地化。  <br/>  加密邮件的正文（内容）未本地化。  <br/> |
|OME 门户和 OME 查看器应用程序的隐私信息  <br/> |[Office 365 消息加密门户隐私声明](https://privacy.microsoft.com/en-US/privacystatement)提供有关 Microsoft 执行和不做您的私人信息的详细信息。  <br/> |

## <a name="frequently-asked-questions-about-legacy-ome"></a>有关旧版 OME 的常见问题
<a name="LegacyServiceInfo"> </a>

对 Office 365 邮件加密有疑问？ 以下是一些解答。 如果找不到所需内容，请查看[Office 365 社区中](http://community.office365.com/en-us/forums/default.aspx)的 Office 365 社区论坛。
  
 **问：我的用户向组织外部的收件人发送加密的电子邮件。外部收件人是否必须执行任何操作才能读取和回复使用 Office 365 邮件加密加密的电子邮件？**
  
組織外部的收件者收到以 Office 365 加密的電子郵件時，可以這兩種方式檢視郵件：
  
- 通过使用 Microsoft 帐户或与 Office 365 关联的工作或学校帐户登录。

- 通过使用一次性密码。

 **問：Office 365 加密郵件是儲存於雲端或 Microsoft 伺服器上嗎？**
  
否，加密邮件保留在收件人的电子邮件系统上，当收件人打开邮件时，邮件将临时发布，以便在 Office 365 服务器上查看。 郵件並不會儲存於該處。
  
 **問：我可以使用自己的品牌自訂加密電子郵件嗎？**
  
是。 您可以使用 Windows PowerShell Cmdlet 自訂加密電子郵件頂端顯示的預設文字、免責聲明文字，及要用於電子郵件和加密入口網站的標誌。 如需詳細資訊，請參閱[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)。
  
 **問：我組織內每位使用者是否皆需備有服務授權？**
  
組織中傳送加密電子郵件的每位使用者皆需有授權。
  
 **問：外部收件者需要訂閱嗎？**
  
否，外部收件者不需要訂閱即可讀取或回覆加密郵件。
  
 **问：Office 365 邮件加密与权限管理服务 （RMS） 有什么不同？**
  
RMS 通过提供内置模板（如：不转发和公司机密）为组织的内部电子邮件提供信息权限保护功能。 Office 365 郵件加密支援傳送至外部收件者和內部收件者之郵件的電子郵件加密。
  
 **问：Office 365 邮件加密与 S/MIME 有什么不同？**
  
S/MIME 基本上是一種用戶端加密技術，需要複雜的憑證管理與發佈基礎結構。 Office 365 邮件加密使用邮件流规则（也称为传输规则），并且不依赖于证书发布。
  
 **問：我可以透過行動裝置閱讀加密郵件嗎？**
  
是的，您可以通过从[谷歌Play商店](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409)和[苹果应用商店](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409)下载OME查看器应用程序来查看Android和iOS上的消息。 在 OME 檢視器應用程式中開啟 HTML 附件，然後依照指示開啟加密的郵件。 對其他行動裝置而言，只要郵件用戶端支援表單張貼，您便能夠開啟 HTML 附件。
  
 **問：回覆和轉寄郵件皆會加密嗎？**
  
是的。在整個執行緒期間都會對回應持續加密。
  
 **问：Office 365 邮件加密是否提供本地化？**
  
內送電子郵件和 HTML 內容均依據寄件者電子郵件設定進行當地語系化。檢視入口網站會依據收件者的瀏覽器設定進行當地語系化。不過，加密郵件的實際內文 (內容) 不會進行當地語系化。
  
 **问：Office 365 邮件加密使用什么加密方法？**
  
Office 365 消息加密使用权限管理服务 （RMS） 作为其加密基础结构。 使用的加密方法取決於您在哪裡取得用來加密及解密郵件的 RMS 金鑰。
  
- 如果使用 Microsoft Azure RMS 获取密钥，则使用加密模式 2。 密碼編譯模式 2 是已更新並增強的 AD RMS 密碼編譯實作。 它支援使用 RSA 2048 進行簽章和加密，也支援使用 SHA-256 進行簽章。

- 如果您使用 Active Directory (AD) RMS 來取得金鑰，則會使用密碼編譯模式 1 或密碼編譯模式 2。使用的方法取決於內部部署 AD RMS 部署。密碼編譯模式 1 是原始的 AD RMS 密碼編譯實作。它支援使用 RSA 1024 進行簽章和加密，也支援使用 SHA-1 進行簽章。這個模式會繼續受到 RMS 所有目前的版本支援。

有关详细信息，请参阅[AD RMS 加密模式](http://go.microsoft.com/fwlink/p/?LinkId=398616)。
  
 **问：为什么某些加密邮件来自Office365@messaging.microsoft.com？**
  
從加密入口網站或透過 OME 檢視器應用程式傳送加密的回覆時，傳送方的電子郵件地址會設為 Office365@messaging.microsoft.com，因為加密的郵件是透過 Microsoft 端點傳送。這有助於避免加密的郵件被標示為垃圾郵件。因為有此標示，加密入口網站中顯示的電子郵件名稱和地址不會變更。此外，此標示只會套用到透過入口網站傳送的郵件，而不會套用到透過任何其他電子郵件用戶端傳送的郵件。
  
 **问：我是交换托管加密 （EHE） 订阅者。在哪里可以了解有关升级到 Office 365 邮件加密的更多信息？**
  
所有 EHE 客戶都已升級至 Office 365 郵件加密。 有关详细信息，请访问 Exchange[托管加密升级中心](http://go.microsoft.com/fwlink/p/?LinkID=511077)。
  
 **问：我是否需要打开组织防火墙中的任何 URL、IP 地址或端口来支持 Office 365 邮件加密？**
  
是。 您必须将联机 Exchange 的 URL 添加到组织的允许列表中，以便对由 Office 365 邮件加密加密的邮件启用身份验证。 如需 Exchange Online URL 的清單，請參閱 [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx)。
  
 **問：我可以將 Office 365 加密郵件傳送給多少位收件者？**
  
收件人限制为每封邮件 500 个收件人，或者，在通讯组列表扩展后合并时，邮件**的"收件人"** 字段中有 11，980 个字符，以先到者为准。
  
 **問：是否可以撤銷傳送給特定收件者的郵件？**
  
否。 发送邮件后，您无法撤消发送给特定人员的邮件。
  
 **問：是否可以檢視已接收和讀取的加密郵件的報表？**
  
没有显示是否已查看加密邮件的报表，但可以使用 Office 365 报告来确定匹配特定邮件流规则（也称为传输规则）的邮件数。
  
 **問：Microsoft 會如何利用透過 OME 入口網站和 OME 檢視器應用程式所取得我的資訊？**
  
[Office 365 消息加密门户隐私声明](https://privacy.microsoft.com/en-US/privacystatement)提供有关 Microsoft 执行和不做您的私人信息的详细信息。
 
