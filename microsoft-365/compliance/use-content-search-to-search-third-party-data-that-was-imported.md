---
title: 使用内容搜索搜索导入 Office 365 的第三方数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: 使用内容搜索电子数据展示工具搜索从第三方数据源导入 Office 365 中的邮箱的项目。 您可以创建查询以搜索所有导入的项目，也可以创建查询以搜索特定的第三方数据类型。 本文列出了可用于关键字查询的值，以搜索可导入 Office 365 的第三方数据类型。
ms.openlocfilehash: 2d531557054398be4ca963a9b09943f1bf583d10
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077438"
---
# <a name="use-content-search-to-search-third-party-data-imported-to-office-365"></a>使用内容搜索搜索导入 Office 365 的第三方数据

您可以使用安全&合规性中心中[的内容搜索电子数据展示工具](content-search.md)搜索从第三方数据源导入 Office 365 中的邮箱的项目。 您可以创建查询以搜索所有导入的第三方数据项，也可以创建查询以搜索特定的第三方数据项。 此外，您还可以创建基于查询的 Office 365 保留策略或基于查询的 eDiscovery 保留，以在 Office 365 中保留第三方数据。 
  
有关导入第三方数据以及可以导入 Office 365 的第三方数据类型列表的详细信息，请参阅[与合作伙伴合作以在 Office 365 中存档第三方数据。](work-with-partner-to-archive-third-party-data.md) 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>创建查询以搜索所有第三方数据

要搜索（或置于保留状态）已导入 Office 365 的任何类型的第三方数据，可以在关键字框中使用`kind:externaldata`消息属性值对进行内容搜索或创建基于查询的保留时。 例如，要搜索从任何第三方数据源导入的项，并在导入项的 Subject 属性中包含单词"contoso"，请使用以下查询： 
  
```
kind:externaldata AND subject:contoso
```

前面的关键字查询示例包括主题属性。 有关可以包含在关键字查询中的第三方数据项的其他属性的列表，请参阅[在 Office 365 中与合作伙伴合作存档第三方数据](work-with-partner-to-archive-third-party-data.md#more-information)中的"详细信息"部分。
  
创建查询以搜索和保存第三方数据时，还可以使用条件来缩小搜索结果的范围。 有关创建内容搜索查询的详细信息，请参阅[关键字查询和内容搜索的搜索条件。](keyword-queries-and-search-conditions.md)
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>创建查询以搜索特定类型的第三方数据

您可以使用以下消息*属性：* 内容搜索关键字框中的值对，创建仅搜索指定类型第三方数据的查询，而不是搜索所有类型的第三方数据：
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

例如，要搜索"主题"属性中包含单词"contoso"的 Facebook 数据，请使用以下查询：
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

下表列出了可以搜索的第三方数据类型，以及用于`itemclass:`消息属性以专门搜索该类型第三方数据的值。 查询语法不区分大小写。 
  
|**第三方数据类型**|**`itemclass:`属性值**|
|:-----|:-----|
|目的  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|含樞紐分析用戶端的 AOL  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|阿瑞斯  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Axs 占位符  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|集市之声  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|熊股  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|比特托伦特  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|黑 莓  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|黑莓通话记录  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|黑莓信使  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|黑莓 PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|黑莓短信  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|彭博  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg 郵件  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|彭博消息  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
|思科&amp;IM 状态服务器  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud for Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Direct Connect  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|努格泰拉  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|谷歌+  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|谷歌对话  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|转到MyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|嘻哈聊天  <br/> | `ipm.externaldata.HipChat*` <br/> |
|霍普斯特  <br/> | `ipm.externaldata.Hopster*` <br/> |
|胡伯康奈斯  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM 连接  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM 同时  <br/> | `ipm.externaldata.Sametime*` <br/> |
|ICE 聊天  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|因斯塔格拉姆  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|投资边缘  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|Irc  <br/> | `ipm.externaldata.IRC*` <br/> |
|摇摆  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApi 保留  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|Jxta  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|微软UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|心灵对齐  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|Msn  <br/> | `ipm.externaldata.MSN*` <br/> |
|Myspace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|近地天体网络  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|开纳普  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|兴趣  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|樞紐  <br/> | `ipm.externaldata.Pivot*` <br/> |
|Qq  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|商務用 Skype  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|软埃瑟  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|斯夸克  <br/> | `ipm.externaldata.Squawker*` <br/> |
|交响乐  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS Chat  <br/> | `ipm.externaldata.UBS*` <br/> |
|维梅奥  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|温MX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|温尼  <br/> | `ipm.externaldata.Winny*` <br/> |
|雅虎！  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|黄色夹克  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|Youtube  <br/> | `ipm.externaldata.YouTube*` <br/> |
