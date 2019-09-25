---
title: 与合作伙伴合作，在 Office 365 中存档第三方数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 您的组织可以与 Microsoft 合作伙伴合作，设置自定义连接器，以便从数据源（如 Salesforce Chatter、Yahoo Messenger 或 Yammer）导入第三方数据。 这使您可以在 Office 365 中存档来自第三方数据源的数据，以便您可以使用 Office 365 合规性功能（如法律保留、内容搜索和保留策略）来管理组织第三方数据的治理。
ms.openlocfilehash: a22b4226efb582969072bbd92149080cca9b749c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077633"
---
# <a name="work-with-a-partner-to-archive-third-party-data-in-office-365"></a>与合作伙伴合作，在 Office 365 中存档第三方数据

您可以与 Microsoft 合作伙伴合作，将数据从第三方数据源导入 Office 365 并将其存档。 合作伙伴可以为您提供一个自定义连接器，该连接器配置为从第三方数据源中提取项目（定期），然后将这些项目导入 Office 365。 合作伙伴连接器将项目的内容从数据源转换为电子邮件格式，然后将项目存储在 Office 365 中的邮箱中。 导入第三方数据后，您可以将 Office 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核和 Office 365 保留策略）应用于此数据。
  
以下是与 Microsoft 合作伙伴合作将第三方数据导入 Office 365 的过程和必要步骤的概述。

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[Step 2: Create and configure a third-party data mailbox in Office 365](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[步驟 4：提供資訊給合作夥伴](#step-4-provide-your-partner-with-information)

[步骤 5：在 Azure 活动目录中注册第三方数据连接器](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>協力廠商資料匯入程序的運作方式

下图和说明说明了第三方数据导入过程在与合作伙伴合作时的工作原理。
  
![協力廠商資料匯入程序的運作方式](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. 客户与其选择的合作伙伴合作，配置一个连接器，该连接器将从第三方数据源中提取项目，然后将这些项目导入 Office 365。
    
2. 合作伙伴连接器通过第三方 API（按计划或按配置）连接到第三方数据源，并从数据源中提取项目。 協力廠商連接器會將項目的內容轉換為電子郵件訊息格式。 有关消息格式架构的说明，请参阅[详细信息](#more-information)部分。 
    
3. 合作伙伴连接器通过已知终结点使用 Exchange Web 服务 （EWS） 连接到 Office 365 中的 Azure 服务。
    
4. 項目是匯入至特定使用者的信箱或「全部擷取」協力廠商資料信箱。項目匯入至特定使用者信箱還是協力廠商資料信箱，是根據下列準則：
    
    a. **具有对应于 Office 365 用户帐户的用户 ID 的项目：** 如果合作伙伴连接器可以将第三方数据源中项的用户 ID 映射到 Office 365 中的特定用户 ID，则该项目将复制到用户的"可恢复项目"文件夹中**的"清除"** 文件夹。 使用者無法存取 [清除] 資料夾中的項目。 但是，您可以使用 Office 365 电子数据展示工具在"清除"文件夹中搜索项目。
    
    b. **没有与 Office 365 用户帐户对应的用户 ID 的项目：** 如果合作伙伴连接器无法将项目的用户 ID 映射到 Office 365 中的特定用户 ID，则该项目将复制到第三方数据邮箱的**收件箱**文件夹。 將項目匯入至收件匣可讓您或組織中的某個人登入協力廠商信箱來檢視和管理這些項目，並查看是否需要在協力廠商連接器組態中進行任何調整。
 
## <a name="step-1-find-a-third-party-data-partner"></a>步驟 1：尋找協力廠商資料合作夥伴

在 Office 365 中存档第三方数据的一个关键组件是查找并与其合作的 Microsoft 合作伙伴，该合作伙伴专门捕获来自第三方数据源的数据并将其导入 Office 365。 导入数据后，可以将其与组织的其他 Microsoft 数据一起存档和保存，例如来自 Exchange 的电子邮件和来自 SharePoint 和 OneDrive 的业务文档。 合作伙伴创建一个连接器，从组织的第三方数据源（如黑莓、Facebook、Google+、汤森路透、Twitter 和 YouTube）中提取数据，并将这些数据传递到 Office 365 API，该 API 将项目导入到 Exchange 邮箱（作为电子邮件。 
  
以下部分列出了参与 Office 365 中存档第三方数据的计划的 Microsoft 合作伙伴（以及他们支持的第三方数据源）。

[17a-4 LLC](#17a-4-llc)
  
[存档社交](#archivesocial)
  
[格洛巴内](#globanet)
  
[OpenText](#opentext)
  
[斯马什](#smarsh)

[韦尔巴](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

[17a-4 LLC](https://www.17a-4.com)支持以下第三方数据源：
  
- BlackBerry
    
- Bloomberg 資料流
    
- Cisco Jabber
    
- 事实集
    
- 嘻哈聊天
    
- 投资边缘
    
- 现场人员
    
- MessageLabs 資料流
    
- OpenText
    
- Oracle/ATG 'click-to-call' 即時說明
    
- 樞紐分析 IMTRADER
    
- Microsoft SharePoint
    
- 心对齐
    
- Sitrion One (Newsgator)
    
- 商務用 Skype (Lync/OCS)
    
- 商務用 Skype Online (Lync Online)
    
- SQL 資料庫
    
- 斯夸克
    
- Thomson Reuters Eikon Messenger
  

  
### <a name="archivesocial"></a>存档社交

[存档社交](https://www.archivesocial.com)支持以下第三方数据源： 
  
- Facebook
    
- Flickr
    
- 因斯塔格拉姆
    
- LinkedIn
    
- 兴趣
    
- Twitter
    
- Youtube
    
- 维梅奥
  
### <a name="globanet"></a>格洛巴内

[Globanet](https://www.globanet.com)支持以下第三方数据源： 
  
- 含樞紐分析用戶端的 AOL 
    
- BlackBerry Call Logs (v5、v10、v12)
    
- BlackBerry Messenger (v5、v10、v12)
    
- BlackBerry PIN (v5、v10、v12)
    
- BlackBerry SMS (v5、v10、v12)
    
- Bloomberg Chat
    
- Bloomberg 郵件
    
- Box
    
- CipherCloud for Salesforce Chatter
    
- 思科&amp;IM 状态服务器（v10、v10.5.1 SU1、v11.0、v11.5 SU2）

- 思科 Webex 团队

- Citrix&amp;工作区共享文件

- 人群通

- 自定义分隔的文本文件
    
- 自訂 XML 檔案
    
- 脸谱（页面）
    
- 事实集
    
- FXConnect
    
- ICE Chat/YellowJacket
    
- 摇摆
    
- Macgregor XIP

- Microsoft Exchange Server
    
- Microsoft OneDrive for Business

- Microsoft Teams
       
- Microsoft Yammer
    
- Mobile Guard
    
- 樞紐
    
- Salesforce Chatter

- 商務用 Skype Online
    
- 商務用 Skype 2007 版 R2 - 2016 (內部部署)
    
- Slack Enterprise Grid
    
- 交响乐
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Thomson Reuters Dealings 3000 / FX Trading
    
- Twitter
    
- UBS Chat
    
- Youtube
  
### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)支持以下第三方数据源： 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- 彭博
    
- Thomson Reuters
  
### <a name="smarsh"></a>斯马什

[Smarsh](https://www.smarsh.com)支持以下第三方数据源： 
  
- 目的
    
- American Idol
    
- Apple Juice
    
- 含樞紐分析用戶端的 AOL
    
- 阿瑞斯
    
- Bazaar Voice
    
- Bear Share
    
- Bit Torrent
    
- BlackBerry Call Logs (v5、v10、v12)
    
- BlackBerry Messenger (v5、v10、v12)
    
- BlackBerry PIN (v5、v10、v12)
    
- BlackBerry SMS (v5、v10、v12)
    
- Bloomberg 郵件
    
- 细胞信托
    
- Chat Import
    
- Chat Real Time Logging and Policy
    
- 颤 振
    
- 思科&amp;IM 状态服务器（v9.0.1、v9.1、v9.1.1 SU1、v10、v10.5.1 SU1）
    
- Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)
    
- Collaboration Import
    
- Collaboration Real Time Logging
    
- Direct Connect
    
- Facebook
    
- 事实集
    
- FastTrack
    
- 努格泰拉
    
- 谷歌+
    
- 转到MyPC
    
- 霍普斯特
    
- 胡伯康奈斯
    
- IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)
    
- IBM Connections Chat Cloud
    
- IBM Connections Social Cloud
    
- IBM SameTime Advanced 8.5.2 IFR1
    
- IBM SameTime Communicate 9.0
    
- IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)
    
- IBM SameTime Complete 9.0
    
- IBM SameTime Conference 9.0
    
- IBM SameTime Meeting 8.5.2 IFR1
    
- ICE/黄色夹克
    
- IM Import
    
- IM Real Time Logging and Policy
    
- Indii Messenger
    
- Instant Bloomberg
    
- Irc
    
- 摇摆
    
- Jive 6 Real Time Logging (v6、v7)
    
- Jive Import
    
- Jxta
    
- LinkedIn
    
- Microsoft Lync (2010、2013)
    
- MFTP
    
- Microsoft Lync 2013 Voice
    
- Microsoft SharePoint (2010、2013)
    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- 心对齐
    
- Mobile Guard
    
- Msn
    
- My Space
    
- 近地天体网络
    
- Office 365 Lync Dedicated
    
- Office 365 Shared IM
    
- 兴趣
    
- 樞紐
    
- Qq
    
- 商務用 Skype 2015
    
- 软埃瑟
    
- 交响乐
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Tor
    
- TTT
    
- Twitter
    
- 温MX
    
- 温尼
    
- 雅虎
    
- Yammer
    
- Youtube
    

### <a name="verba"></a>韦尔巴

[Verba](https://www.verba.com)支持以下第三方数据源： 
  
- Avaya Aura Video
    
- Avaya Aura Voice
    
- Avtec Radio
    
- Bosch/Telex Radio
    
- BroadSoft Video
    
- BroadSoft Voice
    
- Centile Voice
    
- Cisco Jabber IM
    
- Cisco UC Video
    
- Cisco UC Voice
    
- 思科 UCCX/UCCE 视频
    
- 思科 UCCX/UCCE 语音
    
- ESChat Radio
    
- Geoman Contact Expert
    
- IP Trade Voice
    
- Luware LUCS Contact Center
    
- Microsoft UC (Unified Communications)
    
- Mitel MiContact Center for Lync (prairieFyre)
    
- Oracle / Acme Packet Session Border Controller Video
    
- Oracle / Acme Packet Session Border Controller Voice
    
- Singtel Mobile Voice
    
- SIPREC Video
    
-  SIPREC Voice 
    
- 商務用 Skype/Lync IM
    
- 商務用 Skype/Lync Video
    
- 商務用 Skype/Lync Voice
    
- Speakerbus Voice
    
- Standard SIP/H.323 Video
    
- Standard SIP/H.323 Voice
    
- Truphone Voice
    
- TwistedPair Radio
    
- Windows Desktop Computer Screen
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a>步驟 2：在 Office 365 中建立及設定協力廠商資料信箱

以下是创建和配置用于将数据导入 Office 365 的第三方数据邮箱的步骤。 如前所述，如果合作伙伴连接器无法将该项目的用户 ID 映射到 Office 365 用户帐户，则项目将导入此邮箱。
  
 **在 Microsoft 365 管理中心完成这些任务**
  
1. 在 Office 365 中创建用户帐户，并为其分配 Exchange 在线计划 2 许可证;请参阅[将用户添加到 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098)。 需要计划 2 许可证才能将邮箱置于诉讼保留状态或启用具有无限存储配额的存档邮箱。
    
2. 将第三方数据邮箱的用户帐户添加到 Office 365 中的**Exchange 管理员**管理员角色;请参阅[在 Office 365 中分配管理员角色。](https://go.microsoft.com/fwlink/p/?LinkId=532393)
    
    > [!TIP]
    > 請寫下此使用者帳戶的認證。 您需要將它們提供給您的合作夥伴 (如步驟 4 中所述)。 
  
 **在 Exchange 管理中心完成这些任务**
  
1. 从组织中的通讯簿和其他地址列表中隐藏第三方数据邮箱;请参阅[管理用户邮箱](https://go.microsoft.com/fwlink/p/?LinkId=616058)。 或者，您可以运行以下 PowerShell 命令：
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. 将"**完全访问"** 权限分配给第三方数据邮箱，以便管理员或合规性官可以在 Outlook 桌面客户端中打开第三方数据邮箱;请参阅[管理收件人的权限。](https://go.microsoft.com/fwlink/p/?LinkId=692104)
    
3. 为第三方数据邮箱启用以下与合规性相关的 Office 365 功能：
    
    - 启用存档邮箱;请参阅[启用存档邮箱](enable-archive-mailboxes.md)和[启用无限制存档](enable-unlimited-archiving.md)。 这样，您就可以通过设置将第三方数据项目移动到存档邮箱的存档策略来释放主邮箱中的存储空间。 这为您提供了第三方数据的无限存储空间。
    
    - 將協力廠商資料信箱處於 [訴訟暫止] 狀態。 您还可以在安全和合规性中心应用 Office 365 保留策略。 将此邮箱置于保留状态将保留第三方数据项目（无限期或指定持续时间），并防止从邮箱中清除它们。 请参阅以下主题之一：
    
      - [將信箱設定為訴訟資料暫留狀態](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [Office 365 中的保留策略概述](retention-policies.md)
    
       
    
    - 为所有者、代理和管理员访问第三方数据邮箱启用邮箱审核日志记录;请参阅[在 Office 365 中启用邮箱审核。](enable-mailbox-auditing.md) 这允许您审核有权访问第三方数据邮箱的任何用户执行的所有活动。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>步驟 3：設定協力廠商資料的使用者信箱

下一步是設定使用者信箱以支援協力廠商資料。 使用 Exchange 管理中心或使用相应的 Windows PowerShell cmdlet 完成这些任务。
  
1. 为每个用户启用存档邮箱;请参阅[启用存档邮箱](enable-archive-mailboxes.md)和[启用无限制存档](enable-unlimited-archiving.md)。
    
2. 将用户邮箱置于诉讼保留状态或应用 Office 365 保留策略;请参阅以下主题之一： 
    
    - [將信箱設定為訴訟資料暫留狀態](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [Office 365 中的保留策略概述](retention-policies.md)
    
    如先前所述，將信箱置於保留狀態時，您可以設定從協力廠商資料來源保留項目多久的持續時間，或者您可以選擇無限期地保留項目。

## <a name="step-4-provide-your-partner-with-information"></a>步驟 4：提供資訊給合作夥伴

最後一個步驟是讓您的合作夥伴具有下列資訊，讓他們可以設定連接器以連接到您的 Office 365 組織，將資料匯入至使用者信箱和協力廠商資料信箱。 
  
- 用于连接到 Office 365 中的 Azure 服务的终结点：

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 您在步骤 2 中创建的第三方数据邮箱的登录凭据（Office 365 用户 ID 和密码）。 協力廠商連接器需要這些認證才能存取項目以及將其匯入至使用者信箱和協力廠商資料信箱。
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>步骤 5：在 Azure 活动目录中注册第三方数据连接器

从 2018 年 9 月 30 日开始，Office 365 中的 Azure 服务将开始使用 Exchange Online 中的现代身份验证来验证尝试连接到 Office 365 组织以导入数据的第三方数据连接器。 进行此更改的原因是，现代身份验证比当前方法提供了更多的安全性，该方法基于使用前面描述的终结点连接到 Azure 服务的白名单第三方连接器。

要使第三方数据连接器能够使用新的新式身份验证方法连接到 Office 365，Office 365 组织的管理员必须同意在 Azure 活动目录中将连接器注册为受信任的服务应用程序。 这是通过接受权限请求来允许连接器访问 Azure 活动目录中的组织数据来实现的。 接受此请求后，第三方数据连接器将作为企业应用程序添加到 Azure 活动目录，并表示为服务主体。 有关同意过程的详细信息，请参阅[租户管理员同意](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)。

以下是访问和接受注册连接器的请求的步骤：

1. 转到[此页面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)并使用 Office 365 全局管理员的凭据登录。<br/><br/>将显示以下对话框。 您可以展开分卡以查看将分配给连接器的权限。<br/><br/>![将显示权限请求对话框](media/O365-ThirdPartyDataConnector-OptIn1.png)
2. 按一下 [接受]****。

接受请求后，将显示[Azure 门户。](https://portal.azure.com) 要查看组织的应用程序列表，请单击**Azure 活动目录** > **企业应用程序**。 Office 365 第三方数据连接器列**在"企业"应用程序**边栏选项卡上。

> [!IMPORTANT]
> 2018 年 9 月 30 日之后，如果不在 Azure 活动目录中注册第三方数据连接器，则第三方数据将不再导入到组织中的邮箱中。 请注意，现有的第三方数据连接器（2018 年 9 月 30 日之前创建的数据连接器）也必须按照步骤 5 中的步骤在 Azure 活动目录中注册。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>撤销对第三方数据连接器的同意

组织同意在 Azure 活动目录中注册第三方数据连接器的权限请求后，您的组织可以随时撤消该同意。 但是，撤销连接器的同意意味着来自第三方数据源的数据将不再导入 Office 365。

要撤销对第三方数据连接器的同意，可以使用 Azure 门户中的**企业应用程序**边栏选项卡删除应用程序（通过删除相应的服务主体），或使用[在](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal)Office 365 PowerShell 中删除 MsolService 主体。 您还可以在 Azure 活动目录 PowerShell[中使用"删除 AzureADServiceCcd"](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal)
  
## <a name="more-information"></a>詳細資訊

- 如先前所述，協力廠商資料來源的項目是匯入至 Exchange 信箱做為電子郵件訊息。 合作伙伴连接器使用 Office 365 API 所需的架构导入项目。 下表說明協力廠商資料來源的項目在匯入至 Exchange 信箱當做為電子郵件之後的郵件屬性。 表格也會指出郵件屬性是否為必要的。 必須填入必要屬性。 如果项目缺少必填属性，则不会将其导入 Office 365。 导入过程返回一条错误消息，解释为何未导入项以及缺少哪个属性。
    
    |**郵件屬性**|**强制性？**|**描述**|**範例值**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |是  <br/> |最初在協力廠商資料來源中建立或傳送項目的使用者。 合作伙伴连接器尝试将用户 ID 从源项（例如 Twitter 句柄）映射到所有用户（FROM 和 TO 字段中的用户）的 Office 365 用户帐户。 郵件副本會匯入至每個參與者的信箱。 如果项目的参与者都不能映射到 Office 365 用户帐户，则该项目将导入 Office 365 中的第三方存档邮箱。  <br/> <br/> 标识为项目发件人的参与者必须在要导入到的 Office 365 组织中具有活动邮箱。 如果寄件者沒有作用中的信箱，則會傳回下列錯誤︰<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |是  <br/> |接收項目的使用者，如果適用於資料來源中的項目。  <br/> | `bob@contoso.com` <br/> |
    |**主题** <br/> |否  <br/> |來源項目的主旨。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**日期** <br/> |是  <br/> |项目最初创建或在客户数据源中过帐的日期。 例如，Twitter 消息被推特的日期。  <br/> | `01 NOV 2015` <br/> |
    |**身体** <br/> |否  <br/> |訊息或文章的內容。 對於某些資料來源，這個屬性的內容可能與 **SUBJECT** 屬性的內容相同。 在导入过程中，合作伙伴连接器尝试尽可能保持内容源的完全保真度。 如果可能的話，來源項目的內文中的檔案、圖形或其他內容會包含在此屬性中。 否則，來源項目的內容會包含在 **ATTACHMENT** 屬性。 此属性的内容取决于合作伙伴连接器和源平台的功能。  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**附件** <br/> |否  <br/> |如果数据源中的项目（如 Twitter 中的推文或即时消息对话）中的项目具有附加文件或包含图像，则合作伙伴连接将首先尝试在**BODY**属性中包含附件。 如果这是不可能的，则将其添加到 [ 附件 ] 属性中。 其他附件範例包括 Facebook 的「讚」、內容來源的中繼資料和訊息或文章的回應。  <br/> | `image.gif` <br/> |
    |**消息类** <br/> |是  <br/> | 這是多重值屬性，由合作夥伴連接器建立並填入。 此属性的格式为`IPM.NOTE.Source.Event`。 （此属性必须以`IPM.NOTE`开头。 此格式与消息类的`IPM.NOTE.X`格式类似。此属性包括以下信息：  <br/><br/>`Source`： 指示第三方数据源;例如，推特、脸谱或黑莓。  <br/> <br/>  `Event`： 指示在生成物料的第三方数据源中执行的活动类型;例如，推特的推文或Facebook上的帖子。 事件特定于数据源。  <br/> <br/>  此屬性的其中一個用途是要根據項目產生來源位置的資料來源或根據事件類型，篩選特定項目。 例如，在 eDiscovery 搜尋中，您可以建立搜尋查詢來尋找特定使用者所張貼的所有推文。  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- 当项目成功导入 Office 365 中的邮箱时，唯一标识符将作为 HTTP 响应的一部分返回给调用方。 此标识符称为`x-IngestionCorrelationID`，合作伙伴可用于后续故障排除目的，以便端到端跟踪物料。 建議夥伴擷取這項資訊並加以記錄。 以下是顯示此識別碼之 HTTP 回應的範例：

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- 您可以使用安全和合规性中心中的内容搜索工具搜索从第三方数据源导入 Office 365 中的邮箱的项目。 要专门搜索这些导入的项目，可以在内容搜索的关键字框中使用以下消息属性值对。
    
  - **`kind:externaldata`**：使用此属性值对搜索所有第三方数据类型。 例如，要搜索从第三方数据源导入并在导入项的 Subject 属性中包含单词"contoso"的项目，请使用关键字查询`kind:externaldata AND subject:contoso`。
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**：使用此属性值对仅搜索指定类型的第三方数据。 例如，要仅搜索"主题"属性中包含单词"contoso"的 Facebook 数据，请使用关键字查询`itemclass:ipm.externaldata.Facebook* AND subject:contoso`。 

  有关用于`itemclass`该属性的第三方数据类型的完整值列表，请参阅[使用内容搜索搜索已导入 Office 365 的第三方数据](use-content-search-to-search-third-party-data-that-was-imported.md)
    
   如需有關使用內容搜尋和建立關鍵字搜尋查詢的詳細資訊，請參閱︰
    
  - [Office 365 中的内容搜索](content-search.md)
    
  - [內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
 
