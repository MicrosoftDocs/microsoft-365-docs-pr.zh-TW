---
title: 使用內容搜尋來搜尋協力廠商匯入的資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: 使用內容搜尋 eDiscovery 工具，透過建立查詢，在 Microsoft 365 中搜尋從協力廠商資料來源匯入信箱的專案。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324569"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>使用內容搜尋來搜尋自訂夥伴連接器匯入的協力廠商資料

您可以使用安全性 & 合規性中心的[內容搜尋 eDiscovery 工具](content-search.md)，從協力廠商資料來源搜尋 Microsoft 365 中已匯入信箱的專案。 您可以建立查詢來搜尋所有匯入的協力廠商資料項目，也可以建立查詢來搜尋特定的協力廠商資料項目。 此外，您也可以建立查詢型保留原則或以查詢為基礎的 eDiscovery 保留，以保留協力廠商資料。
  
如需使用協力廠商資料匯入協力廠商資料的詳細資訊，以及您可以匯入至 Microsoft 365 的協力廠商資料類型清單，請參閱[在 Office 365 中使用協力廠商資料的合作](work-with-partner-to-archive-third-party-data.md)。

> [!IMPORTANT]
> 本文中的指導方針只適用于自訂夥伴連接器匯入的協力廠商資料。 本文不適用於使用 Microsoft 規範中心內 [協力廠商資料連線器](archiving-third-party-data.md#third-party-data-connectors) 匯入的協力廠商資料。
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>建立查詢以搜尋所有協力廠商資料

若要搜尋 (或保留狀態) 您已匯入 Office 365 的協力廠商資料類型，您可以 `kind:externaldata` 在內容搜尋的 [關鍵字] 方塊中，或建立查詢型保留時，使用郵件屬性-值對。 例如，若要搜尋從任何協力廠商資料來源匯入的專案，並在匯入專案的 Subject 屬性中包含 "contoso" 一詞，您可以使用下列查詢： 
  
```powershell
kind:externaldata AND subject:contoso
```

上一個關鍵字查詢範例包含 subject 屬性。 如需可包含在關鍵字查詢中的協力廠商資料項目的其他屬性清單，請參閱使用[協力廠商在 Office 365 中封存協力廠商資料](work-with-partner-to-archive-third-party-data.md#more-information)的「其他資訊」一節。
  
建立查詢以搜尋並保留協力廠商資料時，您也可以使用條件來縮小搜尋結果。 如需建立內容搜尋查詢的詳細資訊，請參閱 [內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>建立查詢以搜尋特定類型的協力廠商資料

除了搜尋所有類型的協力廠商資料之外，您可以使用下列郵件 *屬性：值* 組合，在內容搜尋的關鍵字方塊中，建立只搜尋協力廠商資料的指定類型的查詢：
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

例如，若要在 Subject 屬性中搜尋包含 "contoso" 一詞的 Facebook 資料，您可以使用下列查詢：
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

下表列出您可以搜尋的協力廠商資料類型，以及用於郵件屬性的值，  `itemclass:` 以特別搜尋該類型的協力廠商資料。 查詢語法不區分大小寫。 
  
|**協力廠商資料類型**|**屬性值 `itemclass:`**|
|:-----|:-----|
|目的  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|含樞紐分析用戶端的 AOL  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|阿瑞斯  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Axs 預留位置  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|黑 莓  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry 通話記錄  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry 信使  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry 簡訊  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|彭博  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg Message  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|Bloomberg 訊息  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM &amp; 顯示伺服器  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud for Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Direct Connect  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google +  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google 交談  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM 連線  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|ICE Chat  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|Irc  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|Jxta  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|構思對齊  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|Msn  <br/> | `ipm.externaldata.MSN*` <br/> |
|Myspace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|Pivot  <br/> | `ipm.externaldata.Pivot*` <br/> |
|Qq  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|商務用 Skype  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Squawker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS Chat  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|雅虎！  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
