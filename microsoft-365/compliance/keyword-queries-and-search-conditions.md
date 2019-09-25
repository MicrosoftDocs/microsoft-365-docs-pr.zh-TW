---
title: 內容搜尋的關鍵字查詢和搜尋條件
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
description: '使用安全&合规中心的内容搜索工具，了解可在 Exchange 在线邮箱和 SharePoint 或 OneDrive 中搜索的业务网站的电子邮件和文件属性。  '
ms.openlocfilehash: 5b3438537e2936fa140052c6869f84937e103746
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076289"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>內容搜尋的關鍵字查詢和搜尋條件

本主题介绍可以使用安全&合规中心的内容搜索功能在 Exchange Online 中的电子邮件项目中搜索的电子邮件和文档属性，以及存储在 SharePoint 和 OneDrive 业务网站上的文档的电子邮件和文档属性。 您还可以使用**\*-合规性搜索**cmdlet 中的安全&合规性中心 PowerShell 来搜索这些属性。 本主题还介绍了：   
  
- 使用布尔搜索运算符、搜索条件和其他搜索查询技术来优化搜索结果。
    
- 在 SharePoint 和 OneDrive 中搜索敏感数据类型和自定义敏感数据类型。
    
- 搜索与组织外部用户共享的网站内容
    
有关如何创建内容搜索的分步说明，请参阅[Office 365 中的内容搜索。](content-search.md)

  
> [!NOTE]
> 安全&合规性中心的内容搜索以及相应的**\*-合规性搜索**cmdlet 在安全&合规中心 PowerShell 中使用关键字查询语言 （KQL）。 有关详细信息，请参阅[关键字查询语言语法参考](https://go.microsoft.com/fwlink/?LinkId=269603)。 
  
## <a name="searchable-email-properties"></a>可搜尋的電子郵件屬性

下表列出了可以使用安全&合规性中心的内容搜索功能**或使用"新合规性搜索"****或"设置合规性**搜索"cmdlet 进行搜索的电子邮件属性。 该表包含_属性：value_语法示例，以及示例返回的搜索结果的说明。 您可以在内容搜索的`property:value`关键字框中键入这些对。 

> [!NOTE]
> 搜索电子邮件属性时，无法搜索指定属性为空或为空的项目。 例如，使用*属性：value*对**subject："来**搜索具有空主题行的电子邮件将返回零结果。 这也适用于搜索站点和联系人属性。
  
|**屬性**|**屬性描述**|**範例**|**示例返回的搜索结果**|
|:-----|:-----|:-----|:-----|
|附件名称|附加到电子邮件的文件的名称。|`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual*`|具有名为年报表.ppt 的附加文件的邮件。 在第二个示例中，使用通配符返回附件文件名中带有单词"年"的消息。|
|密件副本|电子邮件的密件抄送字段。<sup>1</sup>|`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`|所有示例返回包含密件抄送字段中的 Pilar Pinilla 的消息。|
|類別| 要搜索的类别。 用户可以在 Web 上使用 Outlook 或 Outlook（以前称为 Outlook Web 应用）来定义类别。 可能的值如下：  <br/><br/>  蓝色  <br/>  绿色  <br/>  橙  <br/>  紫色  <br/>  红  <br/>  黄色|`category:"Red Category"`|已在源邮箱中分配红色类别的邮件。|
|副本|电子邮件的 Cc 字段。<sup>1</sup>|`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`|在这两个示例中，在 Cc 字段中指定了 Pilar Pinilla 的消息。|
|文件夹|特定邮箱文件夹的文件夹 ID （GUID）。 如果使用此属性，请确保搜索指定文件夹所在的邮箱。 将仅搜索指定的文件夹。 不会搜索文件夹中的任何子文件夹。 要搜索子文件夹，您需要为要搜索的子文件夹使用 Folderid 属性。  <br/> 有关搜索 Folderid 属性和使用脚本获取特定邮箱的文件夹 ID 的详细信息，请参阅[在 Office 365 中使用目标集合的内容搜索。](use-content-search-for-targeted-collections.md)|`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`|第一个示例返回指定邮箱文件夹中的所有项目。 第二个示例返回指定邮箱文件夹中由garthf@contoso.com发送或接收的所有项目。|
|寄件者|电子邮件的发件人。<sup>1</sup>|`from:pilarp@contoso.com`  <br/> `from:contoso.com`|由指定用户发送或从指定域发送的消息。|
|HasAttachment|指示邮件是否具有附件。 使用值**为真**或**假**。|`from:pilar@contoso.com AND hasattachment:true`|具有附件的指定用户发送的邮件。|
|Importance|电子邮件的重要性，发件人在发送邮件时可以指定该重要性。 默认情况下，邮件以正常重要性发送，除非发件人将重要性设置为**高**或**低。**|`importance:high`  <br/> `importance:medium`  <br/> `importance:low`|标记为高重要性、中等重要性或低重要性的消息。|
|IsRead|指示邮件是否已读取。 使用值**为真**或**假**。|`isread:true`  <br/> `isread:false`|第一个示例返回 IsRead 属性设置为**True**的消息。 第二个示例返回 IsRead 属性设置为**False**的消息。|
|项目类|使用此属性可搜索您的组织导入 Office 365 的特定第三方数据类型。 对此属性使用以下语法：`itemclass:ipm.externaldata.<third-party data type>*`|`itemclass:ipm.externaldata.Facebook* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`|第一个示例返回在"主题"属性中包含单词"contoso"的 Facebook 项目。 第二个示例返回由 Ann Beebe 发布的 Twitter 项目，这些项目包含关键字短语"北风交易者"。  <br/> 有关用于 ItemClass 属性的第三方数据类型的完整值列表，请参阅[使用内容搜索搜索已导入 Office 365 的第三方数据。](use-content-search-to-search-third-party-data-that-was-imported.md)|
|類型| 要搜索的电子邮件的类型。 可能的值：  <br/>  接触  <br/>  文档  <br/>  email  <br/>  外部数据  <br/>  传真  <br/>  我  <br/>  期刊  <br/>  会议  <br/>  微软团队（从 Microsoft 团队中的聊天、会议和呼叫中返回项目）  <br/>  笔记  <br/>  职位  <br/>  rssfeed  <br/>  任务  <br/>  语音 信箱|`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`|第一个示例返回符合搜索条件的电子邮件。 第二个示例返回电子邮件、即时消息对话（包括 Skype 业务对话和 Microsoft Teams 中的聊天）以及符合搜索条件的语音邮件。 第三个示例返回从第三方数据源（如 Twitter、Facebook 和思科 Jabber）导入到 Office 365 中邮箱的符合搜索条件的项目。 有关详细信息，请参阅在[Office 365 中存档第三方数据。](https://go.microsoft.com/fwlink/p/?linkid=716918)|
|参与者|所有人员都出现在电子邮件中。 这些字段是"来自、到"、抄送和密件抄送<sup>1</sup>|`participants:garthf@contoso.com`  <br/> `participants:contoso.com`|发送或发送到garthf@contoso.com的消息。 第二个示例返回由contoso.com域中的用户发送或发送给用户的所有消息。|
|Received|收件人收到电子邮件的日期。|`received:04/15/2016`  <br/> `received>=01/01/2016 AND received<=03/31/2016`|2016 年 4 月 15 日收到的消息。 第二个示例返回 2016 年 1 月 1 日至 2016 年 3 月 31 日期间收到的所有消息。|
|收件者|电子邮件中的所有收件人字段。 这些字段为"到"、抄送和密件抄送<sup>1</sup>|`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`|发送到garthf@contoso.com的消息。 第二个示例返回发送到contoso.com域中的任何收件人的邮件。|
|寄件日期|发件人发送电子邮件的日期。|`sent:07/01/2016`  <br/> `sent>=06/01/2016 AND sent<=07/01/2016`|在指定日期发送或在指定日期范围内发送的消息。|
|大小|项目的大小（以字节为单位）。|`size>26214400`  <br/> `size:1..1048567`|大于 25？M b。 第二个示例返回大小为 1 到 1，048，567 字节（1 MB）的消息。|
|主旨|电子邮件主题行中的文本。  <br/> **注意：** 在查询中使用 Subject 属性时，搜索将返回主题行包含要搜索的文本的所有消息。 换句话说，查询不会只返回完全匹配的消息。 例如，如果您搜索`subject:"Quarterly Financials"`，则搜索结果将包括主题为"2018 年季度财务"的消息。|`subject:"Quarterly Financials"`  <br/> `subject:northwind`|包含主题行文本中任意位置的短语"季度财务"的邮件。 第二个示例返回主题行中包含单词"北风"的所有消息。|
|收件者|电子邮件的"结束"字段。<sup>1</sup>|`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`|所有示例返回在"归："行中指定 Ann Beebe 的消息。|
|||||
   
> [!NOTE]
> <sup>1</sup>对于收件人属性的值，可以使用电子邮件地址（也称为*用户主体名称*或 UPN）、显示名称或别名来指定用户。 例如，您可以使用annb@contoso.com、annb 或"Ann Beebe"来指定用户 Ann Beebe。<br/><br/>在搜索任何收件人属性（来自、收件人、密件、密件抄送、参与者和收件人）时，Office 365 会尝试通过在 Azure 活动目录中查找每个用户的标识来扩展这些属性。  如果在 Azure 活动目录中找到该用户，则查询将展开以包括用户的电子邮件地址（或 UPN）、别名、显示名称和旧版ExchangeDN。<br/><br/>例如，查询（如`participants:ronnie@contoso.com`）将扩展到`participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"`。<br/><br/>为了防止收件人扩展，可以在搜索查询中向电子邮件地址的末尾添加通配符（星号）;例如， `participants:ronnie@contoso.com*`.

## <a name="searchable-site-properties"></a>可搜索网站属性

下表列出了一些"共享点"和"一个业务"属性，这些属性可以通过使用安全&合规性中心的内容搜索功能**或使用"新合规性搜索"****或"设置合规性搜索"进行搜索**cmdlet. 该表包含_属性：value_语法示例，以及示例返回的搜索结果的说明。 
  
有关可搜索的 SharePoint 属性的完整列表，请参阅[SharePoint 中已爬网和托管属性的概述。](https://go.microsoft.com/fwlink/p/?LinkId=331599) 可以搜索"**可查询"** 列中**标记为"是"** 的属性。 
  
|**屬性**|**屬性描述**|**範例**|**示例返回的搜索结果**|
|:-----|:-----|:-----|:-----|
|作者|Office 文档中的作者字段，如果复制文档，该文档将保持不变。 例如，如果用户创建文档并将其通过电子邮件发送给其他人，然后将其上载到 SharePoint，则文档仍将保留原始作者。 请确保为此属性使用用户的显示名称。|`author:"Garth Fort"`|所有由加思堡创作的文档。|
|内容类型|项目的 SharePoint 内容类型，如项目、文档或视频。|`contenttype:document`|所有文件都将返回。|
|建立時間|创建项目的日期。|`created\>=06/01/2016`|2016 年 6 月 1 日或之后创建的所有项目。|
|CreatedBy|创建或上载项目的人员。 请确保为此属性使用用户的显示名称。|`createdby:"Garth Fort"`|加思堡创建或上传的所有项目。|
|检测到的语言|项的语言。|`detectedlanguage:english`|所有英语项目。|
|文档链接|SharePoint 或一个业务站点上特定文件夹的路径 （URL）。 如果使用此属性，请确保搜索指定文件夹所在的站点。  <br/> 要返回位于为文档链接属性指定的文件夹子文件夹中的项目，必须将 /\*添加到指定文件夹的 URL;因此，必须将 /添加到指定文件夹的 URL 中。例如，`documentlink: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/>有关搜索文档链接属性和使用脚本获取特定网站上文件夹的文档链接 URL 的详细信息，请参阅[在 Office 365 中使用目标集合的内容搜索。](use-content-search-for-targeted-collections.md)|`documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"`  <br/> `documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`|第一个示例返回指定的 OneDrive for Business 文件夹中的所有项目。 第二个示例返回指定站点文件夹中的文档（和所有子文件夹），这些文件文件中包含单词"机密"。|
|文件扩展|文件的扩展名;例如，docx、1、pptx 或 xlsx。|`fileextension:xlsx`|所有 Excel 文件（Excel 2007 及更高版本）|
|FileName|文件的名称。|`filename:"marketing plan"`  <br/> `filename:estimate`|第一个示例返回标题中"营销计划"的确切短语的文件。 第二个示例返回文件名中带有单词"估计"的文件。|
|上次修改时间|上次更改项目的日期。|`lastmodifiedtime>=05/01/2016`  <br/> `lastmodifiedtime>=05/10/2016 AND lastmodifiedtime<=06/1/2016`|第一个示例返回在 2016 年 5 月 1 日或之后更改的项。 第二个示例返回 2016 年 5 月 1 日至 2016 年 6 月 1 日期间更改的项目。|
|ModifiedBy|上次更改项目的人员。 请确保为此属性使用用户的显示名称。|`modifiedby:"Garth Fort"`|加思堡上次更改的所有项目。|
|路徑|SharePoint 或一个业务站点中特定站点的路径 （URL）。  <br/> 要返回位于为路径属性指定的站点文件夹中的项目，必须将 /\*添加到指定站点的 URL;因此，必须将 /添加到指定站点的 URL 中。例如，`path: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/> **注意：** 使用`Path`属性搜索 OneDrive 位置不会返回搜索结果中的媒体文件，如 .png、.tiff 或 .wav 文件。 在搜索查询中使用其他站点属性在 OneDrive 文件夹中搜索媒体文件。 <br/>|`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/"`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/*" AND filename:confidential`|第一个示例返回指定的 OneDrive 业务站点中的所有项目。 第二个示例返回指定站点（和站点中的文件夹）中包含文件名中"机密"一词的文档。|
|与用户共享|已与指定用户共享并显示在用户 OneDrive 业务网站中的"**与我共享"** 页上的文档。 这些是组织中其他人已显式与指定用户共享的文档。 当您导出与使用 SharedWithUsersOWSUser 属性的搜索查询匹配的文档时，文档将从与指定用户共享文档的人员的原始内容位置导出。 有关详细信息，请参阅[搜索组织中共享的网站内容。](#searching-for-site-content-shared-within-your-organization)|`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`|这两个示例都返回与 Garth Fort 明确共享的所有内部文档，这些文档显示在 Garth Fort 的 OneDrive 商业帐户**中的"与我共享"** 页上。|
|網站|组织中网站或网站组的 URL。|`site:"https://contoso-my.sharepoint.com"`  <br/> `site:"https://contoso.sharepoint.com/sites/teams"`|第一个示例返回组织中所有用户的 OneDrive 业务站点中的项目。 第二个示例返回来自所有团队站点的项目。|
|大小|项目的大小（以字节为单位）。|`size>=1`  <br/> `size:1..10000`|第一个示例返回大于 1 字节的项目。 第二个示例返回大小为 1 到 10，000 字节的项。|
|標題|文档的标题。 "标题"属性是在 Microsoft Office 文档中指定的元数据。 它与文档的文件名不同。|`title:"communication plan"`|在 Office 文档的 Title 元数据属性中包含短语"通信计划"的任何文档。|
|||||
   
## <a name="searchable-contact-properties"></a>可搜索的联系人属性

下表列出了已编制索引的联系人属性，您可以使用内容搜索进行搜索。 这些属性可供用户为位于用户邮箱的个人通讯簿中的联系人（也称为个人联系人）配置。 要搜索联系人，可以选择要搜索的邮箱，然后在关键字查询中使用一个或多个联系人属性。
  
> [!TIP]
> 要搜索包含空格或特殊字符的值，请使用双引号 （""） 来包含短语;否则，使用双引号 （""） "例如， `businessaddress:"123 Main Street"`. 
  
|**屬性**|**屬性描述**|
|:-----|:-----|
|BusinessAddress|"**企业地址"** 属性中的地址。 属性也称为联系人属性页上**的工作**地址。|
|商务电话|**任何"商业电话号码"** 属性中的电话号码。|
|CompanyName|**公司**属性中的名称。|
|部門|**部门**属性中的名称。|
|DisplayName|联系人的显示名称。 这是联系人**的全名**属性中的名称。|
|EmailAddress|联系人的任何电子邮件地址属性的地址。 用户可以为联系人添加多个电子邮件地址。 使用此属性将返回与联系人的任何电子邮件地址匹配的联系人。|
|FileAs|**文件作为**属性。 此属性用于指定联系人在用户联系人列表中的列出方式。 例如，联系人可以*列为"姓名"、姓氏*或*姓氏。"*|
|给定名称|"**名字"** 属性中的名称。|
|HomeAddress|任何**家庭**地址属性中的地址。|
|家庭电话|任何**家庭**电话号码属性中的电话号码。|
|IMAddress|IM 地址属性，通常是用于即时消息的电子邮件地址。|
|MiddleName|**中间名**属性中的名称。|
|手机|"**移动**电话号码"属性中的电话号码。|
|暱稱|**"昵称"** 属性中的名称。|
|OfficeLocation|**"办公室"** 或"**办公室"位置**属性中的值。|
|OtherAddress|"**其他**地址"属性的值。|
|姓|"**姓氏"** 属性中的名称。|
|標題|"**作业标题"** 属性中的标题。|
|||||

## <a name="searchable-sensitive-data-types"></a>可搜索的敏感数据类型

您可以使用安全和合规性中心中的内容搜索功能来搜索存储在 SharePoint 和 OneDrive 商业网站上的文档中的敏感数据，如信用卡号或社会保险号。 可以通过在关键字查询中使用 属性`SensitiveType`和敏感信息类型的名称来执行此操作。 例如，查询`SensitiveType:"Credit Card Number"`返回包含信用卡号的文档。 查询`SensitiveType:"U.S. Social Security Number (SSN)"`返回包含美国社会保险号的文档。 要查看可搜索的敏感数据类型的列表，请访问安全&合规性中心的**分类**\>**敏感信息类型。** 或者，您可以使用安全&合规中心 PowerShell 中的**Get-Dlp 敏感信息类型**cmdlet 来显示敏感信息类型的列表。 
  
您还可以使用 属性`SensitiveType`搜索您（或其他管理员）为您的组织创建的自定义敏感信息类型的名称。 您可以使用"安全&合规性中心"（或 PowerShell 中的**Publisher**属性）**中的"敏感信息类型"** 页上**的"发布者"** 列来区分内置和自定义敏感信息类型。 有关详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。
  
有关使用 属性`SensitiveType`创建查询的详细信息，请参阅[形成查询以查找存储在站点上的敏感数据。](form-a-query-to-find-sensitive-data-stored-on-sites.md)

> [!NOTE]
> 不能使用敏感数据类型和`SensitiveType`搜索属性在 Exchange 联机邮箱中搜索处于静止状态的敏感数据。 但是，您可以使用数据丢失防护 （DLP） 策略来保护传输中的敏感电子邮件数据。 有关详细信息，请参阅[数据丢失防护策略概述](data-loss-prevention-policies.md)以及[搜索和查找个人数据。](search-for-and-find-personal-data.md)
  
## <a name="search-operators"></a>搜索运算符

布尔搜索运算符（如**AND、OR**和**NOT**）通过在搜索查询中包含或排除特定单词来帮助定义更精确的搜索。 **** 其他技术（如使用属性运算符（如\>+ 或 ..）、引号、括号和通配符）可帮助您优化搜索查询。 下表列出了可用于缩小或扩大搜索结果的运算符。 
  
|**Operator**|**Usage**|**描述**|
|:-----|:-----|:-----|
|AND|关键字1 和关键字2|返回包含所有指定关键字或`property:value`表达式的项目。 例如，`from:"Ann Beebe" AND subject:northwind`将返回 Ann Beebe 发送的所有消息，其中包含主题行中的"北风"一词。 <sup>2</sup>|
|+|关键字1 = 关键字2 + 关键字3|返回*包含*`keyword2``keyword3`*或*的项，以及也`keyword1`包含 的项。   因此，此示例等效于查询`(keyword2 OR keyword3) AND keyword1`。  <br/> 查询（`keyword1 + keyword2`**+** 符号后有空格）与使用 _ AND = 运算符不同。 此查询将等效于`"keyword1 + keyword2"`并返回具有精确阶段`"keyword1 + keyword2"`项的项目。|
|或|关键字1 OR关键字2|返回包含一个或多个指定关键字或`property:value`表达式的项目。 <sup>2</sup>|
|不|关键字1 not 关键字2  <br/> 不是来自："安比比"  <br/> 不种类：im|排除由关键字或`property:value`表达式指定的项。 在第二个示例中，排除 Ann Beebe 发送的消息。 第三个示例排除任何即时消息对话，例如保存到"对话历史记录"邮箱文件夹中的业务对话 Skype。 <sup>2</sup>|
|-|关键字1 -关键字2|与**NOT**运算符相同。 因此，此查询返回包含`keyword1`和 将排除包含`keyword2`的项的项。|
|附近|关键字1 NEAR（n） 关键字2|返回彼此靠近的单词的项目，其中 n 等于单词数分开。 例如，`best NEAR(5) worst`返回"最差"一词在"最佳"五个单词内的任何项。 如果未指定数字，则默认距离为 8 个单词。 <sup>2</sup>|
|ONEAR|关键字1 ONEAR（n） 关键字2|与**NEAR**类似，但返回的项中按指定顺序彼此靠近的单词。 例如，`best ONEAR(5) worst`返回在单词"最差"之前出现"最佳"一词且两个单词彼此在五个单词内的任何项。 如果未指定数字，则默认距离为 8 个单词。 <sup>2</sup> <br/> > [!NOTE]> 搜索邮箱时不支持**ONEAR**运算符。 它仅在搜索业务网站的 SharePoint 和 OneDrive 时有效。 如果要在同一搜索中搜索邮箱和网站，并且查询包括**ONEAR**运算符，则搜索返回邮箱项目，就像使用**NEAR**运算符一样。 换句话说，无论单词的发生顺序如何，搜索都会返回指定单词彼此靠近的项目。|
|:|属性：值|冒号（:)在`property:value`语法中指定要搜索的属性的值包含指定的值。 例如，`recipients:garthf@contoso.com`返回发送到garthf@contoso.com的任何消息。|
|=|属性_值|与 相同的 **：** 运算符。|
|\<|属性\<值|表示要搜索的属性小于指定值。 <sup>1</sup>|
|\>|属性\>值|表示要搜索的属性大于指定值。<sup>1</sup>|
|\<=|属性\<= 值|表示要搜索的属性小于或等于特定值。<sup>1</sup>|
|\>=|属性\>= 值|表示要搜索的属性大于或等于特定值。<sup>1</sup>|
|..|属性：值1.值2|表示要搜索的属性大于或等于值 1，小于或等于值 2。<sup>1</sup>|
|"  "|"公允价值"  <br/> subject:"Quarterly Financials"|使用双引号 （""） 在关键字和`property:value`搜索查询中搜索确切的短语或术语。|
|\*|猫\*  <br/> 主题：集\*|前缀通配符搜索（其中星号位于单词末尾）与关键字或`property:value`查询中的零个或多个字符匹配。 例如，`title:set*`返回文档标题中包含单词集、设置和设置（以及以"set"开头的其他单词）的文档。  <br/><br/> **注意：** 只能使用前缀通配符搜索;例如，**\*猫**或**设置。\*** 不支持后缀搜索**\***（ 猫 ）， infix 搜索 （**\*c t**） 和子字符串搜索 （**\*猫\***）.|
|(  )|（公平或免费）和（来自：contoso.com）  <br/> （IPO 或初始）和（股票或股票）  <br/> （季度财务）|括号将布尔词短语、`property:value`项目和关键字组合在一起。 例如，`(quarterly financials)`返回包含"季度"和"财务"等单词的物料。|
|||||
   
> [!NOTE]
> <sup>1</sup>对于具有日期或数值的属性，使用此运算符。<br/> <sup>2</sup>布尔搜索运算符必须大写;**例如，AND**。 如果使用小写运算符（如**和），** 它将在搜索查询中被视为关键字。 
  
## <a name="search-conditions"></a>搜尋條件

您可以向搜索查询添加条件以缩小搜索范围并返回更精细的结果集。 每個條件會將一個子句新增至 KQL 搜尋查詢，當您啟動搜尋時便會建立並執行。
  
[公共属性的条件](#conditions-for-common-properties)

[邮件属性的条件](#conditions-for-mail-properties)

[文档属性的条件](#conditions-for-document-properties)

[与条件一起使用的运算符](#operators-used-with-conditions)

[使用条件的指南](#guidelines-for-using-conditions)

[在搜索查询中使用条件的示例](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>公共属性的条件

在同一搜索中搜索邮箱和网站时，使用公共属性创建条件。 下表列出了添加条件时要使用的可用属性。
  
|**條件**|**描述**|
|:-----|:-----|
|日期|对于电子邮件，收件人接收或发件人发送邮件的日期。 对于文档，文档上次修改的日期。|
|发件人/作者|对于电子邮件，发送消息的人员。 对于文档，作者字段中引用的人员来自 Office 文档。 可以键入多个名称，用逗号分隔。 两个或多个值由**OR**运算符逻辑连接。|
|大小（以字节为单位）|对于电子邮件和文档，项目的大小（以字节为单位）。|
|主题/标题|对于电子邮件，邮件主题行中的文本。 对于文档，文档的标题。 如前所述，"标题"属性是在 Microsoft Office 文档中指定的元数据。 您可以键入多个主题/标题的名称，用逗号分隔。 两个或多个值由**OR**运算符逻辑连接。|
|合規性標籤|对于电子邮件和文档，通过用户手动分配的标签策略或标签自动分配给邮件和文档的标签。 标签用于对电子邮件和文档进行分类，以便进行数据治理，并根据标签定义的分类强制实施保留规则。 您可以键入标签名称的一部分并使用通配符或键入完整的标签名称。 有关详细信息，请参阅[Office 365 中的标签概述。](labels.md)|
|||
  
### <a name="conditions-for-mail-properties"></a>邮件属性的条件

在搜索邮箱或公用文件夹时使用邮件属性创建条件。 下表列出了可用于条件的电子邮件属性。 这些属性是前面描述的电子邮件属性的子集。 为了您的方便，这些描述重复出现。
  
|**條件**|**描述**|
|:-----|:-----|
|消息类型| 要搜索的消息类型。 这是与 Kind 电子邮件属性相同的属性。 可能的值：  <br/><br/>  接触  <br/>  文档  <br/>  email  <br/>  外部数据  <br/>  传真  <br/>  我  <br/>  期刊  <br/>  会议  <br/>  微软团队  <br/>  笔记  <br/>  职位  <br/>  rssfeed  <br/>  任务  <br/>  语音 信箱|
|参与者|所有人员都出现在电子邮件中。 这些字段是"来自、到"、抄送和密件抄送。|
|Type|电子邮件项的消息类属性。 这是与 ItemClass 电子邮件属性相同的属性。 这也是一个多值条件。 因此，要选择多个消息类，请按住**CTRL**键，然后单击要添加到条件的下拉列表中的两个或多个消息类。 在列表中选择的每个消息类将由**OR**运算符在相应的搜索查询中逻辑连接。  <br/> 有关 Exchange 使用的消息类（及其相应的消息类 ID）的列表，**您可以在"消息类"** 列表中选择，[请参阅"项类型"和"消息类"。](https://go.microsoft.com/fwlink/?linkid=848143)|
|Received|收件人收到电子邮件的日期。 这是与"接收的电子邮件"属性相同的属性。|
|收件者|电子邮件中的所有收件人字段。 这些字段为"到"、抄送和密件抄送。|
|寄件者|电子邮件的发件人。|
|寄件日期|发件人发送电子邮件的日期。 这是与"已发送的电子邮件"属性相同的属性。|
|主旨|电子邮件主题行中的文本。|
|收件者|"收件人"字段中电子邮件的收件人。|
|||
  
### <a name="conditions-for-document-properties"></a>文档属性的条件

在 SharePoint 和 OneDrive 上搜索业务站点的文档时，使用文档属性创建条件。 下表列出了可用于条件的文档属性。 这些属性是前面描述的站点属性的子集。 为了您的方便，这些描述重复出现。
  
|**條件**|**描述**|
|:-----|:-----|
|作者|Office 文档中的作者字段，如果复制文档，该文档将保持不变。 例如，如果用户创建文档并将其通过电子邮件发送给其他人，然后将其上载到 SharePoint，则文档仍将保留原始作者。|
|標題|文档的标题。 "Title"属性是在 Office 文档中指定的元数据。 它与文档的文件名不同。|
|建立時間|创建文档的日期。|
|上次修改日期|上次更改文档的日期。|
|檔案類型|文件的扩展名;例如，docx、1、pptx 或 xlsx。 这是与 File 分机网站属性相同的属性。|
|||
  
### <a name="operators-used-with-conditions"></a>与条件一起使用的运算符

添加条件时，可以选择与条件的属性类型相关的运算符。 下表描述了与条件一起使用的运算符，并列出了搜索查询中使用的等效项。
  
|**Operator**|**查询等效项**|**描述**|
|:-----|:-----|:-----|
|之後|`property>date`|与日期条件一起使用。 返回在指定日期之后发送、接收或修改的项目。|
|之前|`property<date`|与日期条件一起使用。 返回在指定日期之前发送、接收或修改的项。|
|之间|`date..date`|与日期和大小条件一起使用。 当与日期条件一起使用时，返回在指定日期范围内发送、接收或修改的项目。 当与大小条件一起使用时，返回大小在指定范围内的项。|
|包含任何|`(property:value) OR (property:value)`|与指定字符串值的属性的条件一起使用。 返回包含一个或多个指定字符串值的任何部分的项。|
|不包含任何|`-property:value`  <br/> `NOT property:value`|与指定字符串值的属性的条件一起使用。 返回不包含指定字符串值任何部分的项。|
|不等于任何|`-property=value`  <br/> `NOT property=value`|与指定字符串值的属性的条件一起使用。 返回不包含特定字符串的项。|
|等于|`size=value`|返回等于指定大小的项。<sup>1</sup>|
|等于任何|`(property=value) OR (property=value)`|与指定字符串值的属性的条件一起使用。 返回与一个或多个指定字符串值完全匹配的项。|
|大|`size>value`|返回指定属性大于指定值的项。<sup>1</sup>|
|大或等|`size>=value`|返回指定属性大于或等于指定值的项。<sup>1</sup>|
|少|`size<value`|返回大于或等于特定值的项。<sup>1</sup>|
|小于或相等|`size<=value`|返回大于或等于特定值的项。<sup>1</sup>|
|不等於|`size<>value`|返回不等于指定大小的项。<sup>1</sup>|
|||
   
> [!NOTE]
> <sup>1</sup>此运算符仅适用于使用 Size 属性的条件。 
  
### <a name="guidelines-for-using-conditions"></a>使用条件的指南

使用搜索条件时，请记住以下事项。
  
- 條件會以 **AND** 運算子的邏輯方式連接至關鍵字查詢 (在關鍵字方塊中指定)。 這表示結果中包含的項目必須同時滿足關鍵字查詢與條件。 這就是條件如何協助您縮小搜尋結果。 
    
- 如果向搜索查询添加两个或多个唯一条件（指定不同属性的条件），则这些条件由**AND**运算符在逻辑上连接。 这意味着仅返回满足所有条件的项目（除了任何关键字查询）。 
    
- 如果为同一属性添加多个条件，则**OR**运算符会以逻辑方式连接这些条件。 这意味着将返回满足关键字查询和任一条件的项目。 因此，相同条件的组由**OR**运算符相互连接，然后**AND**运算符连接一组唯一条件。 
    
- 如果将多个值（用逗号或分号分隔）添加到单个条件，则 OR**运算符将**连接这些值。 这意味着如果项包含条件中属性的任何指定值，则返回项。 
    
- 使用关键字框和条件创建的搜索查询将显示在所选搜索的详细信息窗格**中的"搜索"** 页上。 在查询中，符号`(c:c)`右侧的所有内容都指示添加到查询的条件。 
    
- 条件仅向搜索查询添加属性;不添加运算符。 这就是为什么详细信息窗格中显示的查询不显示在`(c:c)`符号右侧的运算符。 KQL 在执行查询时添加逻辑运算符（根据前面解释的规则）。 
    
- 您可以使用拖放控件重新排列条件的顺序。 单击某个条件的控件并将其向上或向下移动。
    
- 如前所述，某些条件属性允许您键入多个值。 每个值都由**OR**运算符逻辑连接。 这将导致与具有相同条件的多个实例相同的逻辑，其中每个实例都有一个值。 下图显示了具有多个值的单个条件的示例，以及具有单个值的多个条件（对于同一属性）的示例。 两个示例都会导致相同的查询：`(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![郵件必須符合規則中的所有條件。如果您需要符合一個條件或另一個條件，請對每一個條件使用不同的規則。例如，如果要對附件和內容符合特定模式的郵件加入相同的免責聲明，請為每一個條件建立一個規則。您可以輕易地複製規則。](media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![相同屬性的多重搜尋條件](media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> 如果条件接受多个值，我们建议您使用单个条件并指定多个值（用逗号或分号分隔）。 这有助于确保所应用的查询逻辑是您所想要的。 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>在搜索查询中使用条件的示例

以下示例显示具有条件的搜索查询的基于 GUI 的版本、所选搜索的详细信息窗格中显示的搜索查询语法（该语法也由**获取合规性搜索**cmdlet 返回），以及相应的 KQL 查询。 
  
#### <a name="example-1"></a>範例 1

本示例返回 SharePoint 和 OneDrive 商业站点上的文档，这些文档包含信用卡号，最后一次修改是在 2016 年 1 月 1 日之前。
  
 **GUI**
  
![搜尋條件的第一個範例](media/099515ba-d4ee-474e-af25-3aa48816b87b.gif)
  
 **搜索查询语法**
  
 `SensitiveType:"Credit Card Number(c:c)(lastmodifiedtime<2016-01-01)`
  
 **搜索查询逻辑**
  
 `SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2016-01-01)`
  
#### <a name="example-2"></a>範例 2

本示例返回包含关键字"Report"的电子邮件项目或文档，这些项目或文档是在 2105 年 4 月 1 日之前发送或创建的，并且在电子邮件的主题字段或文档的标题属性中包含单词"北风"。 查询不包括满足其他搜索条件的网页。
  
 **GUI**
  
![搜尋條件的第二個範例](media/fe07d495-df81-42da-8106-3cdb409c6e7f.gif)
  
 **搜索查询语法**
  
 `report(c:c)(date<2016-04-01)(subjecttitle:"northwind")(-filetype="aspx")`
  
 **搜索查询逻辑**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
#### <a name="example-3"></a>範例 3
<a name="conditionexamples"> </a>

本示例返回在 2016 年 12 月 1 日至 2016 年 11 月 30 日之间发送的电子邮件或日历会议，其中包含以"电话"或"智能手机"开头的单词。
  
 **GUI**
  
![搜尋條件的第三個範例](media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **搜索查询语法**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **搜索查询逻辑**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="searching-for-site-content-shared-with-external-users"></a>搜尋與外部使用者共用的網站內容

您还可以使用"安全&合规性中心"中的内容搜索功能来搜索存储在 SharePoint 和 OneDrive 上与组织外部人员共享的业务网站的文档。 这可以帮助您识别在组织外部共享的敏感或专有信息。 可以通过在关键字查询中使用 属性`ViewableByExternalUsers`来执行此操作。 此属性返回使用以下共享方法之一与外部用户共享的文档或网站： 
  
- 需要用户以经过身份验证的用户身份登录到组织的共享邀请。
    
- 匿名来宾链接，允许具有此链接的任何人访问资源，而无需经过身份验证。
    
以下為一些範例：
  
- 查询`ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"`返回与组织外部人员共享并包含信用卡号的所有项目。 
    
- 查询`ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"`返回组织中与外部用户共享的所有工作组网站上的文档列表。 
    
> [!TIP]
> 搜索查询（如`ViewableByExternalUsers:true AND ContentType:document`）可能会在搜索结果中返回大量 .aspx 文件。 要消除这些（或其他类型的文件），可以使用 属性来排除特定的`FileExtension`文件类型;否则，可以使用 该属性。例如`ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`. 
  
与组织外部人员共享的内容是什么？ 组织的 SharePoint 和 OneDrive 业务网站中的文档，这些文档通过发送共享邀请共享或在公共场所共享。 例如，以下用户活动会导致外部用户可查看的内容：
  
- 用户与组织外部的人员共享文件或文件夹。
    
- 用户创建共享文件并将链接发送给组织外部的人员。 此链接允许外部用户查看（或编辑）文件。
    
- 用户向组织外部的人员发送共享邀请或来宾链接，以查看（或编辑）共享文件。
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>使用"外部用户可查看"属性的问题

虽然该`ViewableByExternalUsers`属性表示文档或网站是否与外部用户共享的状态，但此属性的作用和反映存在一些注意事项。 在以下方案中，不会更新`ViewableByExternalUsers`该属性的值，并且使用此属性的内容搜索查询的结果可能不准确。 
  
- 对共享策略的更改，例如关闭站点或组织的外部共享。 即使外部访问可能已被吊销，该属性仍将显示以前共享的文档是外部可访问的。
    
- 对组成员身份的更改，例如将外部用户添加到 Office 365 组或 Office 365 安全组。 对于组有权访问的项目，该属性不会自动更新。
    
- 向收件人尚未接受邀请且因此尚未访问内容的外部用户发送共享邀请。
    
在这些情况下，在`ViewableByExternalUsers`重新爬网并重新编制文档库索引之前，属性不会反映当前共享状态。 

## <a name="searching-for-site-content-shared-within-your-organization"></a>搜索组织内共享的网站内容

如前所述，您可以使用 属性，`SharedWithUsersOWSUser`以便搜索组织中人员之间共享的文档。 当某人与组织内的其他用户共享文件（或文件夹）时，共享文件的链接将显示在与该文件共享的人员的 OneDrive 业务帐户中的"**与我共享"** 页上。 例如，要搜索与 Sara Davis 共享的文档，可以使用 查询`SharedWithUsersOWSUser:"sarad@contoso.com"`。 如果导出此搜索的结果，将下载原始文档（位于与 Sara 共享文档的人员的内容位置）。
  
使用 属性`SharedWithUsersOWSUser`时，必须与特定用户显式共享文档，才能在搜索结果中返回。 例如，当某人在其 OneDrive 帐户中共享文档时，他们可以选择与任何人（组织内部或外部）共享该文档，仅与组织内部的人员共享该文档，或与特定人员共享该文档。 下面是 OneDrive**中的"共享"** 窗口的屏幕截图，其中显示了三个共享选项。 
  
![只有与特定人员共享的文件才会由使用"共享与用户OWSUser"属性的搜索查询返回](media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
只有使用第三个选项共享的文档（与**特定人员**共享）将由使用 属性`SharedWithUsersOWSUser`的搜索查询返回。 

## <a name="searching-for-skype-for-business-conversations"></a>搜索 Skype 的业务对话

您可以使用以下关键字查询专门搜索 Skype 业务对话中的内容：

```
kind:im
```

以前的搜索查询还返回来自 Microsoft Teams 的聊天。 为了防止这种情况，可以使用以下关键字查询缩小搜索结果范围，以仅包括 Skype 商务对话：

```
kind:im AND subject:conversation
```

前面的关键字查询不包括 Microsoft Teams 中的聊天，因为 Skype 商务对话将保存为以单词"对话"开头的主题行的电子邮件。

要搜索在特定日期范围内发生的业务对话的 Skype，请使用以下关键字查询：

```
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="search-tips-and-tricks"></a>搜索提示和技巧

- 关键字搜索不区分大小写。 **例如，cat**和**CAT**返回相同的结果。 
    
- 布尔运算符**和，****或，****不，NEAR****和ONEAR**必须是大写。 **** 
    
- 两个关键字或两`property:value`个表达式之间的空格与使用**AND**相同。 例如，`from:"Sara Davis" subject:reorganization`返回 Sara Davis 发送的所有消息，其中包含主题行中的单词"重组"。 
    
- 使用与格式匹配的`property:value`语法。 值不区分大小写，并且它们不能在运算符之后有空格。 如果有空格，则预期值将是全文搜索。 例如，`to: pilarp`搜索"pilarp"作为关键字，而不是发送到 pilarp 的邮件。 
    
- 搜索收件人属性（如收件人、从、抄送或收件人）时，可以使用 SMTP 地址、别名或显示名称来表示收件人。 例如，您可以使用pilarp@contoso.com、皮拉普或"皮拉尔皮尼拉"。
    
- 只能使用前缀通配符搜索;例如，**\*猫**或**设置。\*** 不支持后缀搜索**\***（ 猫 ）， infix 搜索 （**\*c t**） 和子字符串搜索 （**\*猫\***）. 
    
- 搜索属性时，如果搜索值由多个单词组成，请使用双引号 （""）。 例如，`subject:budget Q1`返回在主题行中包含**预算**并在消息中的任何位置或任何消息属性中包含**Q1**的消息。 使用`subject:"budget Q1"`返回在主题行中的任何位置包含**预算 Q1**的所有消息。 
    
- 要从搜索结果中排除标有特定属性值的内容，请在此属性名称之前放置一个减号 （-）。 例如，`-from:"Sara Davis"`排除 Sara Davis 发送的任何邮件。

- 某些特殊字符不包括在搜索索引中，因此不可搜索，这些字符包括搜索运算符（+ - = :)和以下字符，要么被$null替换，要么可能导致错误，如果搜索！ [ % ] & ;_ / ?

- 您可以根据邮件类型导出项目。 例如，要在 Microsoft Teams 中导出 Skype 对话和聊天，请使用 语法`kind:im`。 要仅返回电子邮件，请使用`kind:email`。 要在 Microsoft Teams 中返回聊天、会议和呼叫，`kind:microsoftteams`请使用 。
