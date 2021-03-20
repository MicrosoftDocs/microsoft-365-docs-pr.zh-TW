---
title: 內容搜尋的關鍵字查詢和搜尋條件
f1.keywords:
- NOCSH
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
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解您可以使用 Microsoft 365 中的搜尋和 eDiscovery 工具進行搜尋的電子郵件和檔案屬性。
ms.openlocfilehash: e3282cd5b8bcc493e7c423db72c086f953d114ec
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903581"
---
# <a name="keyword-queries-and-search-conditions-for-content-search-and-ediscovery"></a>內容搜尋和 eDiscovery 的關鍵字查詢和搜尋條件

本主題說明電子郵件和檔案屬性，您可以使用 Microsoft 365 規範中心的內容搜尋功能，在 Exchange Online 中搜尋電子郵件專案，以及儲存在 SharePoint 和 OneDrive 商務網站上的檔。 您也可以在安全性 & 規範中心 PowerShell 中使用 **\* -new-compliancesearch** Cmdlet 來搜尋這些屬性。 本主題也會說明下列事項：
  
- 使用布林值搜尋運算子、搜尋條件及其他搜尋查詢技術來精煉搜尋結果。

- 在 SharePoint 和商務 OneDrive 中搜尋敏感資料類型和自訂敏感資料類型。

- 搜尋與組織外部使用者共用的網站內容

如需如何建立內容搜尋的逐步指示，請參閱 [內容搜尋](content-search.md)。

> [!NOTE]
> Microsoft 365 規範中心的內容搜尋，以及安全性 & 合規性中心內的對應 **\* new-compliancesearch** Cmdlet PowerShell 使用關鍵字查詢語言 (KQL) 。 如需詳細資訊，請參閱 [關鍵字查詢語言語法參考](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)。 
  
## <a name="searchable-email-properties"></a>可搜尋的電子郵件屬性

下表列出可使用 Microsoft 365 規範中心的內容搜尋功能，或使用 **New-ComplianceSearch** 或 **Set-ComplianceSearch** Cmdlet 來搜尋的電子郵件屬性。 此表格包含每個屬性的  _值_ 語法的範例，以及範例所傳回之搜尋結果的描述。 您可以  `property:value` 在 [關鍵字] 方塊中輸入這些配對內容搜尋。 

> [!NOTE]
> 在搜尋電子郵件屬性時，不可能搜尋指定屬性為空白或空白的專案。 例如，使用 [ *屬性：值* 一對主旨 **： "]** 搜尋具有空白主旨行的電子郵件會傳回零結果。 這也適用于搜尋網站和連絡人屬性。
  
| 屬性	 | 屬性描述 | 範例 | 範例所傳回的搜尋結果 |
|:-----|:-----|:-----|:-----|
|AttachmentNames|附加至電子郵件的檔案名稱。|`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual*` <br/> `attachmentnames:.pptx` |具有名為 annualreport.ppt 的附加檔案的郵件。 在第二個範例中，使用萬用字元會傳回附件的檔案名中包含 "年曆" 一詞的郵件。 第三個範例會傳回所有包含 .pptx 副檔名的附件。|
|密件副本|電子郵件訊息的 [密件副本] 欄位。<sup>1</sup>|`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`|所有範例都傳回具有 Pilar Pinilla 的郵件，包含在 [密件副本] 欄位中。|
|類別| 要搜尋的類別。 使用者可以使用先前稱為 Outlook Web App) 上 (的 Outlook 或 Outlook 來定義類別。 可能的值為：  <br/><br/>  藍色  <br/>  綠色  <br/>  橙  <br/>  紫色  <br/>  紅  <br/>  黃色|`category:"Red Category"`|來源信箱中已指派紅色類別的郵件。|
|副本|電子郵件訊息的 [副本] 欄位。<sup>1</sup>|`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`|在這兩個範例中，在 [副本] 欄位中指定 Pilar Pinilla 的郵件。|
|Folderid|特定信箱資料夾 (GUID) 的資料夾識別碼。 如果您使用此屬性，請務必搜尋指定資料夾所在的信箱。 只會搜尋指定的資料夾。 不會搜尋資料夾中的任何子資料夾。 若要搜尋子資料夾，您必須使用 Folderid 屬性做為您想要搜尋的子資料夾。  <br/> 如需搜尋 Folderid 屬性和使用腳本來取得特定信箱之資料夾 IDs 的詳細資訊，請參閱 [使用內容搜尋來尋找目標集合](use-content-search-for-targeted-collections.md)。|`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`|第一個範例會傳回指定之信箱資料夾中的所有專案。 第二個範例會傳回 garthf@contoso.com 所傳送或接收的指定信箱資料夾中的所有專案。|
|寄件者|電子郵件的寄件者。<sup>1</sup>|`from:pilarp@contoso.com`  <br/> `from:contoso.com`|指定的使用者所傳送或從指定的網域傳送的郵件。|
|HasAttachment|會指出郵件是否有附件。 使用值 **true** 或 **false**。|`from:pilar@contoso.com AND hasattachment:true`|指定使用者所傳送的具有附件的郵件。|
|Importance|電子郵件訊息的重要性，寄件者可在傳送郵件時指定。 根據預設，郵件會以一般重要性傳送，除非寄件者將重要性設定為 **高** 或 **低**。|`importance:high`  <br/> `importance:medium`  <br/> `importance:low`|標示為高重要性、中度重要性或低重要性的郵件。|
|IsRead|會指出是否已讀取郵件。 使用值 **true** 或 **false**。|`isread:true`  <br/> `isread:false`|第一個範例會傳回 IsRead 屬性設定為 **True** 的郵件。 第二個範例會傳回 IsRead 屬性設定為 **False** 的郵件。|
|ItemClass|使用此屬性可搜尋您的組織匯入 Office 365 的特定協力廠商資料類型。 請對此屬性使用下列語法：  `itemclass:ipm.externaldata.<third-party data type>*`|`itemclass:ipm.externaldata.Facebook* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`|第一個範例會傳回 Facebook 專案，包含在 Subject 屬性中包含 "contoso" 一詞。 第二個範例會傳回由王小姐 Beebe （包含關鍵字片語 "Northwind 商貿"）所張貼的 Twitter 專案。  <br/> 如需使用 ItemClass 屬性之協力廠商資料類型的完整值清單，請參閱 [使用內容搜尋來搜尋匯入至 Office 365 的協力廠商資料](use-content-search-to-search-third-party-data-that-was-imported.md)。|
|類型| 要搜尋的電子郵件類型。 可能的值：  <br/>  接觸  <br/>  文檔  <br/>  電子郵件  <br/>  externaldata  <br/>  傳真  <br/>  我  <br/>  期刊  <br/>  會議  <br/>  microsoftteams (會從 Microsoft 團隊中的研討、會議及通話傳回專案)   <br/>  筆記  <br/>  職位  <br/>  rssfeeds  <br/>  任務  <br/>  語音 信箱|`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`|第一個範例會傳回符合搜尋準則的電子郵件訊息。 第二個範例會傳回電子郵件、立即訊息交談 (，包括 Microsoft 團隊中的商務用 Skype 交談和聊天) ，以及符合搜尋準則的語音訊息。 第三個範例會傳回從協力廠商資料來源（如 Twitter、Facebook 和 Cisco Jabber) ）匯入至 Microsoft 365 信箱的專案，這些專案會符合搜尋準則。 如需詳細資訊，請參閱在 [Office 365 中封存協力廠商資料](https://www.microsoft.com/?ref=go)。|
|參與者|電子郵件訊息中的所有 [人員] 欄位。 這些欄位是寄件者、To、Cc 和 Bcc。<sup>1</sup>|`participants:garthf@contoso.com`  <br/> `participants:contoso.com`|傳送或傳送至 garthf@contoso.com 的郵件。 第二個範例會傳回 contoso.com 網域中的使用者所傳送或傳送的所有郵件。|
|Received|收件者接收到電子郵件的日期。|`received:04/15/2016`  <br/> `received>=01/01/2016 AND received<=03/31/2016`|2016年4月15日收到的郵件。 第二個範例會傳回所有在2016年1月1日（2016年3月31日）收到的郵件。|
|收件者|電子郵件訊息中的所有收件者欄位。 這些欄位是 To、Cc 和 Bcc。<sup>1</sup>|`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`|傳送至 garthf@contoso.com 的郵件。 第二個範例會傳回傳送至 contoso.com 網域中的任何收件者的郵件。|
|寄件日期|寄件者傳送電子郵件的日期。|`sent:07/01/2016`  <br/> `sent>=06/01/2016 AND sent<=07/01/2016`|在指定日期或指定的日期範圍內傳送的郵件。|
|Size|專案的大小（以位元組為單位）。|`size>26214400`  <br/> `size:1..1048567`|郵件大於25？？M b。 第二個範例會傳回介於1到1048567位元組 (1 MB) 大小的郵件。|
|主旨|電子郵件主題行中的文字。  <br/> **附注：** 當您在查詢中使用 Subject 屬性時，搜尋會傳回主旨行中包含您要搜尋之文字的所有郵件。 換句話說，查詢不會傳回只有完全相符的郵件。 例如，如果您搜尋  `subject:"Quarterly Financials"` ，您的結果將會包含主題為 "季度財務 2018" 的郵件。|`subject:"Quarterly Financials"`  <br/> `subject:northwind`|在主旨行文字的任何地方包含片語 "季度財務" 的郵件。 第二個範例會傳回所有包含主旨行中的「northwind word」的郵件。|
|收件者|電子郵件訊息的 [至] 欄位。<sup>1</sup>|`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`|所有範例會傳回在 [To：] 行中指定王 Beebe 的郵件。|
|||||
   
> [!NOTE]
> <sup>1</sup> 在收件者屬性值中，您可以使用電子郵件地址 (也稱為「 *使用者主體名稱* 」或「UPN」) 、[顯示名稱] 或 [別名] 以指定使用者。 例如，您可以使用 annb@contoso.com、annb 或 "王 Beebe" 來指定使用者王小姐 Beebe。

### <a name="recipient-expansion"></a>收件者擴充

當搜尋任何收件者屬性 (From、To、Cc、Bcc、參與者和收件者) 時，Microsoft 365 會嘗試在 Azure Active Directory (Azure AD) 中查看每位使用者的身分識別。  如果使用者在 Azure AD 中找到，該查詢就會展開，以包含使用者的電子郵件地址 (或 UPN) 、別名、顯示名稱和 LegacyExchangeDN。 例如， `participants:ronnie@contoso.com` 展開 to 的查詢 `participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"` 。

若要防止收件者展開，請將萬用字元 (星號) 新增至電子郵件地址的結尾，並使用減少的功能變數名稱;例如，請 `participants:"ronnie@contoso*"` 務必使用雙引號括住電子郵件地址。

不過，請注意防止搜尋查詢中的收件者擴充，可能會導致搜尋結果中未傳回相關的專案。 Exchange 中的電子郵件可以以不同的文字格式儲存在收件者欄位中。 收件者擴充的目的在於傳回可能包含不同文字格式的郵件，以協助緩解此事實。 因此，防止收件者展開可能會導致搜尋查詢不會傳回所有與調查相關的專案。

> [!NOTE]
> 如果您需要查看或減少因收件者擴充的搜尋查詢所傳回的專案，請考慮使用高級 eDiscovery。 您可以搜尋郵件 (利用收件者擴充) 、將它們新增至審閱集，然後使用「複查集合」查詢或篩選，以複查或縮小結果。 如需詳細資訊，請參閱 [收集案例的資料](collecting-data-for-ediscovery.md) 和 [查詢審閱集中的資料](review-set-search.md)。

## <a name="searchable-site-properties"></a>可搜尋的網站屬性

下表列出商務屬性的一些 SharePoint 和 OneDrive，可使用安全性 & 規範中心的內容搜尋功能，或使用 **New-ComplianceSearch** 或 **Set-ComplianceSearch** 指令程式來搜尋。 此表格包含每個屬性的  _值_ 語法的範例，以及範例所傳回之搜尋結果的描述。 
  
如需可搜尋的 SharePoint 屬性完整清單，請參閱 [SharePoint 中的編目和 managed 屬性的概述](/SharePoint/technical-reference/crawled-and-managed-properties-overview)。 您可以在可 **查詢** 的資料行中，以 [**是]** 標示的屬性進行搜尋。 
  
| 屬性	 | 屬性描述 | 範例 | 範例所傳回的搜尋結果 |
|:-----|:-----|:-----|:-----|
|作者|Office 檔中的 author 欄位，該欄位會在複製檔時保留。 例如，如果使用者建立檔，並將它的電子郵件給其他人，然後再將其上傳至 SharePoint，該檔仍會保留原來的作者。 請務必使用此屬性的使用者顯示名稱。|`author:"Garth Fort"`|所有由 Garth Fort 撰寫的檔。|
|ContentType|專案的 SharePoint 內容類型，例如專案、檔或影片。|`contenttype:document`|會傳回所有檔。|
|建立時間|建立專案的日期。|`created>=06/01/2016`|在2016年6月1日或之後建立的所有專案。|
|CreatedBy|建立或上傳專案的人員。 請務必使用此屬性的使用者顯示名稱。|`createdby:"Garth Fort"`|由 Garth Fort 建立或上傳的所有專案。|
|DetectedLanguage|專案的語言。|`detectedlanguage:english`|以英文顯示所有專案。|
|DocumentLink|SharePoint 上的特定資料夾或商務網站 OneDrive 的 (URL) 路徑。 如果您使用此屬性，請務必搜尋指定資料夾所在的網站。  <br/> 若要傳回位於為 documentlink 屬性指定之資料夾的子資料夾中的專案，您必須新增/ \* 至指定資料夾的 URL，例如，  `documentlink: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/>如需搜尋 documentlink 屬性和使用腳本來取得特定網站上資料夾的 documentlink URLs 的詳細資訊，請參閱 [使用內容搜尋來搜尋目標集合](use-content-search-for-targeted-collections.md)。|`documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"`  <br/> `documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`|第一個範例會傳回 Business folder 的指定 OneDrive 中的所有專案。 第二個範例會在指定的網站資料夾中傳回檔， (和所有子資料夾) 檔案名中包含 "機密" 一詞。|
|FileExtension|檔的副檔名;例如，.docx、one、.pptx 或 .xlsx。|`fileextension:xlsx`|Excel 2007 和更新版本 (所有 Excel 檔案) |
|FileName|檔案的名稱。|`filename:"marketing plan"`  <br/> `filename:estimate`|第一個範例會傳回標題中具有精確片語 "行銷 plan" 的檔案。 第二個範例會傳回檔案名中包含 "預估" 一字的檔案。|
|LastModifiedTime|上次變更專案的日期。|`lastmodifiedtime>=05/01/2016`  <br/> `lastmodifiedtime>=05/10/2016 AND lastmodifiedtime<=06/1/2016`|第一個範例會傳回在2016年5月1日或之後變更的專案。 第二個範例會傳回在5月1日、2016和6月1日（2016）之間變更的專案。|
|ModifiedBy|上次變更專案的人員。 請務必使用此屬性的使用者顯示名稱。|`modifiedby:"Garth Fort"`|由 Garth Fort 最後變更的所有專案。|
|路徑|SharePoint 或 OneDrive for Business site 中特定網站的路徑 (URL) 。  <br/> 若要傳回位於您為 path 屬性指定之網站的資料夾中的專案，您必須新增/ \* 至指定網站的 URL; 例如，  `path: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/> **附注：** 使用此  `Path` 屬性來搜尋 OneDrive 位置，不會在搜尋結果中傳回媒體檔案，例如 .png、tiff 或 .wav 檔案。 在搜尋查詢中使用不同的 site 屬性可搜尋 OneDrive 資料夾中的媒體檔案。 <br/>|`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/"`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/*" AND filename:confidential`|第一個範例會傳回 Business site 的指定 OneDrive 中的所有專案。 第二個範例會傳回指定網站中的檔 (和包含在檔案名中包含 "保密" 字樣的網站) 中的資料夾。|
|SharedWithUsersOWSUser|已與指定的使用者共用，並顯示在使用者的 OneDrive 商務版網站 **] 頁面上** 的檔。 這些是組織中其他人員與指定的使用者明確共用的檔。 當您匯出符合使用 SharedWithUsersOWSUser 屬性之搜尋查詢的檔時，檔會從與指定使用者共用檔之人員的原始內容位置匯出。 如需詳細資訊，請參閱 [搜尋組織內共用的網站內容](#searching-for-site-content-shared-within-your-organization)。|`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`|這兩個範例會傳回與 Garth Fort 明確共用的所有內部檔，並顯示在 Garth Fort 的 Business account OneDrive 中的 [ **與我共用** ] 頁面上。|
|網站|組織中的網站或網站群組的 URL。|`site:"https://contoso-my.sharepoint.com"`  <br/> `site:"https://contoso.sharepoint.com/sites/teams"`|第一個範例會傳回組織中所有使用者之商務網站的 OneDrive 的專案。 第二個範例會傳回所有小組網站中的專案。|
|Size|專案的大小（以位元組為單位）。|`size>=1`  <br/> `size:1..10000`|第一個範例會傳回大於1個位元組的專案。 第二個範例會傳回大小介於1到10000位元組的專案。|
|職稱|檔的標題。 Title 屬性是 Microsoft Office 檔中所指定的中繼資料。 它與檔的檔案名不同。|`title:"communication plan"`|在 Office 檔的 Title metadata 屬性中包含 "communication plan" 片語的任何檔。|
|||||

## <a name="searchable-contact-properties"></a>可搜尋連絡人屬性

下表列出已編制索引的連絡人內容，以及您可以搜尋使用內容搜尋的屬性。 這些是使用者可為連絡人設定的屬性， (也稱為個人連絡人) 位於使用者信箱的個人通訊錄中。 若要搜尋連絡人，您可以選取要搜尋的信箱，然後使用關鍵字查詢中的一或多個連絡人屬性。
  
> [!TIP]
> 若要搜尋包含空格或特殊字元的值，請使用雙引號 ( "" ) 以包含片語; 否則請使用雙引號。例如， `businessaddress:"123 Main Street"` 。
  
| 屬性	 | 屬性描述 |
|:-----|:-----|
|BusinessAddress|[ **商務位址** ] 屬性中的位址。 在連絡人的 [內容] 頁面上，此屬性也稱為「 **工作** 位址」。|
|BusinessPhone|任何 **商務電話** 號碼內容中的電話號碼。|
|CompanyName|**Company** 屬性中的名稱。|
|部門|**部門** 屬性中的名稱。|
|DisplayName|連絡人的顯示名稱。 這是連絡人的 [ **全名** ] 屬性中的名稱。|
|EmailAddress|連絡人的任何電子郵件地址屬性的位址。 使用者可以新增多個連絡人的電子郵件地址。 使用此屬性會傳回符合任何連絡人電子郵件地址的連絡人。|
|FileAs|**File as** 屬性。 此屬性可用來指定連絡人在使用者的連絡人清單中列出的方式。 例如，連絡人可以列為  *FirstName、LastName*  或  *LastName FirstName*。|
|GivenName|**第一個 name** 屬性的名稱。|
|HomeAddress|任何「 **住宅** 位址屬性的位址。|
|HomePhone|任何 **住宅** 電話號碼內容中的電話號碼。|
|IMAddress|IM 位址屬性，通常是用於立即訊息的電子郵件地址。|
|MiddleName|**中間** 名屬性中的名稱。|
|MobilePhone|在 [ **移動** 電話號碼] 屬性中的電話號碼。|
|暱稱|**昵稱** 屬性中的名稱。|
|OfficeLocation|**Office** 或 **office location** 屬性值。|
|OtherAddress|**其他** 位址屬性的值。|
|姓|**Last** name 屬性中的名稱。|
|職稱|職稱 **屬性中的標題** 。|
|||||

## <a name="searchable-sensitive-data-types"></a>可搜尋的敏感資料類型

您可以使用 Microsoft 365 規範中心的 eDiscovery 搜尋工具，搜尋儲存在 SharePoint 的檔或商務網站 OneDrive 的機密資料，例如信用卡號碼或社會保險號碼。 若要這麼做，您可以使用 `SensitiveType` 關鍵字查詢中敏感資訊類型的屬性和名稱 (或 ID) 。 例如，查詢會傳回 `SensitiveType:"Credit Card Number"` 包含信用卡號碼的檔。 查詢  `SensitiveType:"U.S. Social Security Number (SSN)"` 會傳回包含 U.S. 社會保險號碼的檔。

若要查看您可以搜尋的機密資訊類型清單，請移至 \> Microsoft 365 規範中心內的「資料分類的 **敏感資訊類型**」。 您也可以在安全性 & 相容性中心 PowerShell 中使用 **DlpSensitiveInformationType** Cmdlet，以顯示敏感資訊類型的清單。
  
如需使用屬性建立查詢的詳細資訊 `SensitiveType` ，請參閱 [表單 a 查詢以尋找儲存在網站上的敏感性資料](form-a-query-to-find-sensitive-data-stored-on-sites.md)。

### <a name="limitations-for-searching-sensitive-data-types"></a>搜尋敏感資料類型的限制

- 若要搜尋自訂的機密資訊類型，您必須在屬性中指定機密資訊類型的識別碼 `SensitiveType` 。 使用自訂敏感資訊類型的名稱 (如上一節中內建的敏感資訊類型範例中所示) 將不會傳回任何結果。 使用 [規範中心] 中 [**敏感資訊類型**] 頁面上的 [**發行者]** 欄 (或 PowerShell) 中的 **Publisher** 屬性，區分內建和自訂的機密資訊類型。 內建的敏感資料類型具有 `Microsoft Corporation` **發行者** 屬性的值。

  若要顯示組織中自訂敏感資料類型的名稱和識別碼，請在安全性 & 規範中心內執行下列命令 PowerShell:

  ```powershell
  Get-DlpSensitiveInformationType | Where-Object {$_.Publisher -ne "Microsoft Corporation"} | FT Name,Id
  ```

  然後，您可以在搜尋屬性中使用識別碼 `SensitiveType` ，傳回含有自訂敏感資料類型的檔; 例如， `SensitiveType:7e13277e-6b04-3b68-94ed-1aeb9d47de37`
  
- 您無法使用敏感資訊類型和 `SensitiveType` 搜尋屬性來搜尋位於 Exchange Online 信箱中的機密資料。 這包括1:1 聊天訊息、1： N 群組聊天訊息，以及 Microsoft 小組中的小組管道交談，因為所有內容都儲存在信箱中。 不過，您可以使用資料遺失防護 (DLP) 原則，以保護傳輸中的敏感電子郵件資料。 如需詳細資訊，請參閱 [資料遺失防護原則](data-loss-prevention-policies.md) 及 [搜尋及尋找個人資料](/compliance/regulatory/gdpr)的概述。
  
## <a name="search-operators"></a>搜尋運算子

布林值搜尋運算子（例如 **AND**、 **OR**、 **NOT**）可協助您在搜尋查詢中包含或排除特定的字詞，以定義更為精確的搜尋。 其他技術（如使用屬性運算子 (例如 `>=` or `..`) 、引號、括弧及萬用字元）可協助您精煉搜尋查詢。 下表列出您可以用來縮小或拓寬搜尋結果的運算子。 
  
| 運算子 | Usage | 描述 |
|:-----|:-----|:-----|
|AND|keyword1 與 keyword2|會傳回包含所有指定關鍵字或運算式的專案  `property:value` 。 例如，  `from:"Ann Beebe" AND subject:northwind` 會傳回 Beebe 中，包含主旨行中的「northwind」一詞的所有郵件。 <sup>2</sup>|
|+|keyword1 + keyword2 + keyword3|會 *傳回包含* `keyword2` 或 `keyword3` 同時包含的專案 `keyword1` 。   因此，此範例相當於查詢  `(keyword2 OR keyword3) AND keyword1` 。  <br/> 在  `keyword1 + keyword2` 符號) 之後的查詢 (與 **+** 使用 **AND** 運算子不同。 此查詢相當於並傳回  `"keyword1 + keyword2"` 精確階段的專案  `"keyword1 + keyword2"` 。|
|「或」|keyword1 或 keyword2|會傳回包含一或多個指定關鍵字或運算式的專案  `property:value` 。 <sup>2</sup>|
|不|keyword1 未 keyword2  <br/> 不是來自： "王 Beebe"  <br/> 非類型： im|排除關鍵字或運算式所指定的專案  `property:value` 。 在第二個範例中，排除王小姐 Beebe 所傳送的郵件。 第三個範例會排除任何立即訊息交談，例如儲存至 [交談歷程記錄] 信箱資料夾的商務用 Skype 交談。 <sup>2</sup>|
|-|keyword1 -keyword2|與 **NOT** 運算子相同。 所以此查詢會傳回包含的專案，  `keyword1` 並將包含的專案排除  `keyword2` 。|
|附近|keyword1 NEAR (n) keyword2|會傳回彼此接近的字詞，其中 n 等於文字相隔的專案數。 例如，傳回 `best NEAR(5) worst` 任何文字 "惡化" 位於5字 "最佳" 以內的專案。 若未指定數值，則預設的距離為八個字。 <sup>2</sup>|
|:|屬性：值|語法中的冒號 (： )  `property:value` 會指定要搜尋之屬性的值包含指定的值。 例如，會傳回  `recipients:garthf@contoso.com` 傳送至 garthf@contoso.com 的任何郵件。|
|=|property = 值|與 **：** 運算子相同。|
|\<|屬性 \< 值|表示所搜尋的屬性小於指定的值。 <sup>1</sup>|
|\>|屬性 \> 值|表示所搜尋的屬性大於指定的值。<sup>1</sup>|
|\<=|property \< = 值|表示所搜尋的屬性小於或等於特定值。<sup>1</sup>|
|\>=|property \> = 值|表示所搜尋的屬性大於或等於特定值。<sup>1</sup>|
|..|屬性： value1。value2|表示所搜尋的屬性大於或等於 value1 且小於或等於 value2。<sup>1</sup>|
|"  "|"公平值"  <br/> subject:"Quarterly Financials"|使用雙引號 ( "" ) 來搜尋關鍵字和搜尋查詢中的確切片語或字詞  `property:value` 。|
|\*|貓\*  <br/> subject： set\*|首碼萬用字元搜尋 (，星號會放在字結尾的字) 比對關鍵字或查詢中零個或多個字元的相符  `property:value` 。 例如，  `title:set*` 會傳回檔，其中包含 word set、setup 及 set (及其他以「設定」 ) 在檔標題中的文字。  <br/><br/> **附注：** 您只能使用首碼萬用字元搜尋;例如， **cat \* *_ 或 _* 集 \* *_。尾碼搜尋 (_* \* cat** ) 、中綴搜尋 (**c \* t**) 及子字串搜尋 (不支援 **\* cat \***) 。<br/><br/>此外，新增句點 ( \。 ) 至前置詞的萬用字元搜尋會變更傳回的結果。 這是因為句點會被視為停用字詞。 例如，搜尋 **cat \* *_ 和搜尋 _* cat。 \*** 會傳回不同的結果。 建議您不要在前置詞萬用字元搜尋中使用句點。 |
|(  )|從:contoso)  (公平或自由) 及 (  <br/>  (IPO 或初始) 及 (股票或共用)   <br/>  (季度財務) |括弧群組組成 Boolean 片語、  `property:value` items 和關鍵字。 例如，傳回  `(quarterly financials)` 包含文字季度和財務的專案。|
|||||
   
> [!NOTE]
> <sup>1</sup> 對具有日期或數值的屬性使用這個運算子。<br/> <sup>2</sup> 布林值搜尋運算子必須是大寫字母;例如 **和**。 如果您使用小寫運算子，例如 **和**，它會被視為搜尋查詢中的關鍵字。 
  
## <a name="search-conditions"></a>搜尋條件

您可以將條件新增至搜尋查詢，以縮小搜尋範圍，並傳回更精緻的結果集。 每個條件會將一個子句新增至 KQL 搜尋查詢，當您啟動搜尋時便會建立並執行。
  
[一般屬性的條件](#conditions-for-common-properties)

[郵件屬性的條件](#conditions-for-mail-properties)

[檔案屬性的條件](#conditions-for-document-properties)

[與條件搭配使用的運算子](#operators-used-with-conditions)

[使用條件的指導方針](#guidelines-for-using-conditions)

[在搜尋查詢中使用條件的範例](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>一般屬性的條件

在相同搜尋中搜尋信箱和網站時，使用通用屬性建立條件。 下表列出新增條件時所使用的可用屬性。
  
| 條件 | 描述 |
|:-----|:-----|
|日期|電子郵件，是由收件者接收或傳送給寄件者的郵件。 對於檔，是上次修改檔的日期。|
|寄件者/作者|電子郵件，是指傳送訊息的人員。 對於檔，為 [author] 欄位中的 Office 檔中所述的人員。 您可以輸入一個以上的名稱，以逗號分隔。 **Or** 運算子會以邏輯方式連接兩個或多個值。|
|大小 (位元組) |電子郵件和檔的專案大小 (以位元組) 。|
|主旨/職稱|電子郵件，郵件的主旨行中的文字。 檔的標題。 如先前所述，Title 屬性是 Microsoft Office 檔中指定的中繼資料。 您可以輸入多個主體/標題的名稱，以逗號分隔。 **Or** 運算子會以邏輯方式連接兩個或多個值。|
|規範標籤|針對電子郵件和檔，autolabel 由使用者手動指派的原則或保留標籤自動指派給郵件和檔的保留標籤。 保留標籤可用來分類電子郵件和檔以進行資訊控管，並根據標籤定義的設定來強制執行保留規則。 您可以輸入部分保留標籤名稱，並使用萬用字元或輸入完整的標籤名稱。 如需保留標籤的詳細資訊，請參閱 [瞭解保留原則和保留標籤](retention.md)。|
|||
  
### <a name="conditions-for-mail-properties"></a>郵件屬性的條件

在搜尋信箱或公用資料夾時，使用郵件屬性建立條件。 下表列出您可以用於條件的電子郵件屬性。 這些屬性是先前所述的電子郵件屬性的子集。 為了方便您，您可以重複這些描述。
  
| 條件 | 描述 |
|:-----|:-----|
|郵件類型| 要搜尋的郵件類型。 此屬性與 Kind 電子郵件屬性相同。 可能的值：  <br/><br/>  接觸  <br/>  文檔  <br/>  電子郵件  <br/>  externaldata  <br/>  傳真  <br/>  我  <br/>  期刊  <br/>  會議  <br/>  microsoftteams  <br/>  筆記  <br/>  職位  <br/>  rssfeeds  <br/>  任務  <br/>  語音 信箱|
|參與者|電子郵件訊息中的所有 [人員] 欄位。 這些欄位是從、To、Cc 和 Bcc。|
|類型|電子郵件專案的郵件類別屬性。 這是 ItemClass 電子郵件屬性的相同屬性。 也是多值的條件。 因此，若要選取多個郵件類別，請按住 **CTRL** 鍵，然後在下拉式清單中，按一下您要新增至條件的兩個或多個郵件類別。 您在清單中選取的每個郵件類別將會在對應的搜尋查詢中以 **OR** 運算子邏輯連接。  <br/> 如需 Exchange 所使用的郵件 (類別和其對應的郵件類別識別碼) 清單，而您可以在 **郵件類別** 清單中選取，請參閱 [專案類型和郵件類別](/office/vba/outlook/Concepts/Forms/item-types-and-message-classes)。|
|Received|收件者接收到電子郵件的日期。 此屬性與接收的電子郵件屬性相同。|
|收件者|電子郵件訊息中的所有收件者欄位。 這些欄位是 To、Cc 和 Bcc。|
|寄件者|電子郵件的寄件者。|
|寄件日期|寄件者傳送電子郵件的日期。 此屬性與已傳送的電子郵件屬性相同。|
|主旨|電子郵件主題行中的文字。|
|收件者|[收件者] 欄位中的電子郵件收件者。|
|||
  
### <a name="conditions-for-document-properties"></a>檔案屬性的條件

在 SharePoint 和 OneDrive 商務網站上搜尋檔時，使用檔案屬性建立條件。 下表列出您可以用於條件的檔案屬性。 這些屬性是先前所述之網站屬性的子集。 為了方便您，您可以重複這些描述。
  
| 條件 | 描述 |
|:-----|:-----|
|作者|Office 檔中的 author 欄位，該欄位會在複製檔時保留。 例如，如果使用者建立檔，並將它的電子郵件給其他人，然後再將其上傳至 SharePoint，該檔仍會保留原來的作者。|
|職稱|檔的標題。 Title 屬性是 Office 檔中所指定的中繼資料。 它與檔的檔案名不同。|
|建立時間|建立檔的日期。|
|上次修改日期|上次變更檔的日期。|
|檔案類型|檔的副檔名;例如，.docx、one、.pptx 或 .xlsx。 此屬性與 FileExtension 網站屬性相同。|
|||
  
### <a name="operators-used-with-conditions"></a>與條件搭配使用的運算子

當您新增條件時，您可以選取與條件的屬性類型相關的運算子。 下表說明用於條件的運算子，並列出搜尋查詢中所使用的對等運算子。
  
| 運算子 | 查詢對等 | 描述 |
|:-----|:-----|:-----|
|之後|`property>date`|搭配日期條件使用。 會傳回在指定的日期之後所傳送、接收或修改的專案。|
|之前|`property<date`|搭配日期條件使用。 會傳回在指定日期之前已傳送、接收或修改的專案。|
|之間|`date..date`|搭配日期和大小條件使用。 使用日期條件時，會傳回在指定的日期範圍內已傳送、接收或修改的專案。 使用大小條件時，會傳回大小位於指定範圍內的專案。|
|包含任何|`(property:value) OR (property:value)`|搭配用於指定字串值之屬性的條件。 傳回包含一或多個指定字串值之任何部分的專案。|
|不包含任何|`-property:value`  <br/> `NOT property:value`|搭配用於指定字串值之屬性的條件。 傳回不包含任何部分指定的字串值的專案。|
|不等於任何|`-property=value`  <br/> `NOT property=value`|搭配用於指定字串值之屬性的條件。 傳回不包含特定字串的專案。|
|等於|`size=value`|傳回與指定大小相等的專案。<sup>1</sup>|
|等於任何|`(property=value) OR (property=value)`|搭配用於指定字串值之屬性的條件。 傳回與一個或多個指定的字串值完全相符的專案。|
|大|`size>value`|傳回指定屬性大於指定值的專案。<sup>1</sup>|
|大於或等於|`size>=value`|傳回指定的屬性大於或等於指定值的專案。<sup>1</sup>|
|少|`size<value`|傳回大於或等於特定值的專案。<sup>1</sup>|
|小於或等於|`size<=value`|傳回大於或等於特定值的專案。<sup>1</sup>|
|不等於|`size<>value`|傳回與指定大小不相等的專案。<sup>1</sup>|
|||
   
> [!NOTE]
> <sup>1</sup> 此運算子僅適用于使用 Size 屬性的條件。 
  
### <a name="guidelines-for-using-conditions"></a>使用條件的指導方針

使用搜尋條件時，請牢記下列幾點。
  
- 條件會以 **AND** 運算子的邏輯方式連接至關鍵字查詢 (在關鍵字方塊中指定)。 這表示結果中包含的項目必須同時滿足關鍵字查詢與條件。 這就是條件如何協助您縮小搜尋結果。 
    
- 如果您將兩個或多個唯一條件新增至搜尋查詢 (條件指定不同的屬性) ，這些條件會由 **AND** 運算子邏輯連接。 這表示只有滿足所有條件的專案 (會傳回所有關鍵詞查詢) 。 
    
- 如果您為同一個屬性新增多個條件，這些條件會由 **OR** 運算子邏輯連接。 這表示滿足關鍵字查詢的專案，以及任何一個條件會傳回。 因此，依 **OR** 運算子將相同條件的群組連線到對方，然後由 **and** 運算子所連接的唯一條件集。 
    
- 如果您新增多個值 (以逗號或分號隔開) 單一條件，則這些值是由 **or** 運算子所連接。 這表示如果專案包含條件中屬性的任何指定值，則會傳回專案。 
    
- 使用 [關鍵字] 方塊和 [條件] 所建立的搜尋查詢會顯示在 [ **搜尋** ] 頁面上選取之搜尋的 [詳細資料] 窗格中。 在查詢中，標記法右邊的各項都會  `(c:c)` 指出新增至查詢的條件。 
    
- 條件只會將屬性新增至搜尋查詢;不要新增運算子。 這就是在詳細資料窗格中顯示的查詢不會顯示在標記法右邊的運算子  `(c:c)` 。 KQL 會根據先前所述的規則，在執行查詢時) ，新增邏輯運算子 (。 
    
- 您可以使用拖放控制項來 resequence 條件的順序。 按一下控制項上的條件，然後上下移動。
    
- 如先前所述，有些 condition 屬性可讓您輸入多個值。 每個值都是由 **OR** 運算子以邏輯方式連接。 這會產生與多個相同條件實例的相同邏輯，每個實例都有單一值。 下列圖例顯示具有多個值的單一條件的範例，以及 (相同屬性) 具有單一值的多個條件的範例。 這兩個範例會產生相同的查詢：  `(filetype:docx) OR (filetype:pptx) OR (filetype:xlsx)`
    
    ![具有多個值的一個條件](../media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![相同屬性的多重搜尋條件](../media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> 如果條件接受多個值，建議您使用單一條件，並指定多個值 (以逗號或分號) 分隔。 這有助於確定所套用的查詢邏輯是您想要的。 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>在搜尋查詢中使用條件的範例

下列範例會顯示以 GUI 為基礎之搜尋查詢的版本，該搜尋查詢語法會顯示在所選搜尋 (的 [詳細資料] 窗格中，也就是由 **Get-ComplianceSearch** Cmdlet) 所傳回，以及對應 KQL 查詢的邏輯。 
  
#### <a name="example-1"></a>範例 1

本範例會傳回商務網站的 SharePoint 和 OneDrive 上的檔，這些網站包含信用卡號碼，最後在2016年1月1日之前修改。
  
 **GUI**
  
![搜尋條件的第一個範例](../media/099515ba-d4ee-474e-af25-3aa48816b87b.gif)
  
 **搜尋查詢語法**
  
 `SensitiveType:"Credit Card Number"(c:c)(lastmodifiedtime<2016-01-01)`
  
 **搜尋查詢邏輯**
  
 `SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2016-01-01)`
  
#### <a name="example-2"></a>範例 2

此範例會傳回包含關鍵字 "report" 的電子郵件專案或檔，該關鍵字是在2105年4月1日之前所傳送或建立，而且在電子郵件的主旨欄位或檔的 title 屬性中包含 "northwind" 一詞。 查詢會排除符合其他搜尋準則的網頁。
  
 **GUI**
  
![搜尋條件的第二個範例](../media/fe07d495-df81-42da-8106-3cdb409c6e7f.gif)
  
 **搜尋查詢語法**
  
 `report(c:c)(date<2016-04-01)(subjecttitle:"northwind")(-filetype:aspx)`
  
 **搜尋查詢邏輯**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype:aspx)`
  
#### <a name="example-3"></a>範例 3

本範例會傳回在12/1/2016 和11/30/2016 之間傳送且包含開頭為 "phone" 或 "smartphone" 文字的電子郵件訊息或行事曆會議。
  
 **GUI**
  
![搜尋條件的第三個範例](../media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **搜尋查詢語法**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **搜尋查詢邏輯**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="special-characters"></a>特殊字元

有些特殊字元不會包含在搜尋索引中，因此無法進行搜尋。 這也包含在搜尋查詢中代表搜尋運算子的特殊字元。 以下是特殊字元的清單，這些字元是由實際搜尋查詢中的空格取代，或是導致搜尋錯誤。

`+ - = : ! @ # % ^ & ; _ / ? ( ) [ ] { }`

## <a name="searching-for-site-content-shared-with-external-users"></a>搜尋與外部使用者共用的網站內容

您也可以使用安全性 & 合規性中心內的「內容搜尋」功能，搜尋儲存在 SharePoint 上的檔，以及與組織外部人員共用的商務網站 OneDrive。 這可協助您識別在組織外共用的敏感或專有資訊。 您可以使用關鍵字查詢中的屬性來執行此動作  `ViewableByExternalUsers` 。 此屬性會傳回使用下列共用方法之一，與外部使用者共用的檔或網站： 
  
- 共用邀請，需要使用者登入您的組織成為已驗證的使用者。
    
- 匿名來賓連結，可讓具有此連結的任何人存取資源，而不需要進行驗證。
    
以下為一些範例：
  
- 查詢  `ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"` 會傳回所有與組織外部人員共用的專案，並包含信用卡號碼。 
    
- 查詢  `ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"` 會傳回組織中所有與外部使用者共用之小組網站上的檔案清單。 
    
> [!TIP]
> 搜尋結果中的搜尋查詢  `ViewableByExternalUsers:true AND ContentType:document` 可能會傳回許多 .aspx 檔案。 若要將這些 (或其他類型的檔案) 中，您可以使用此  `FileExtension` 屬性排除特定的檔案類型，例如  `ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx` 。 
  
與組織外部人員共用的內容為何？ 您組織中的檔，可透過傳送共用邀請或在公用位置中共用的方式，在組織的 SharePoint 和 OneDrive 中共用。 例如，下列使用者活動會產生外部使用者可查看的內容：
  
- 使用者與組織外部的人員共用檔案或資料夾。
    
- 使用者建立共用檔案的連結並傳送給組織外部的人員。 此連結可讓外部使用者 (或編輯) 檔案中查看。
    
- 使用者將共用邀請或來賓連結傳送給組織外部的人員，以查看 (或編輯) 共用檔案。
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>使用 ViewableByExternalUsers 屬性的問題

雖然  `ViewableByExternalUsers` 此屬性代表的是檔或網站與外部使用者共用的狀態，但是此屬性的功能和不會反映的注意事項。 在下列案例中，屬性值將  `ViewableByExternalUsers` 不會更新，而且使用此屬性的內容搜尋查詢結果可能不准確。 
  
- 對共用原則所做的變更，例如關閉網站或組織的外部共用。 即使已撤銷外部存取，屬性仍然會將先前的共用檔顯示為外部可存取的。
    
- 群組成員資格的變更，例如新增或移除外部使用者至 Microsoft 365 群組或 Microsoft 365 安全性群組。 此屬性不會自動更新為群組具有存取權的專案。
    
- 將共用邀請傳送給沒有收件者接受邀請的外部使用者，因此還沒有內容的存取權。
    
在這些情況下，  `ViewableByExternalUsers` 除非網站或文件庫是重新編目和重新編制索引，否則屬性不會反映目前的共用狀態。 

## <a name="searching-for-site-content-shared-within-your-organization"></a>搜尋組織內共用的網站內容

如先前所述，您可以使用  `SharedWithUsersOWSUser` 屬性來搜尋組織中的人員間共用的檔。 當人員與組織內的其他使用者共用檔案 (或資料夾) 時，共用檔案的連結會出現在共用該檔案之人員的商務用帳戶 OneDrive 中的 [ **與我共用** ] 頁面上。 例如，若要搜尋已與 Sara Davis 共用的檔，您可以使用查詢  `SharedWithUsersOWSUser:"sarad@contoso.com"` 。 如果您匯出此搜尋的結果，則會下載原始檔案 (位於共用該檔之人員的內容位置，且該人員已使用 Sara) 共用。
  
使用屬性時，必須與特定使用者明確共用檔，以在搜尋結果中傳回  `SharedWithUsersOWSUser` 。 例如，當人員在其 OneDrive 帳戶中共用檔時，可以選擇將其與組織內的任何人 (共用) 、只與組織內的人員共用，或與特定人員共用。 以下是 OneDrive 中 [ **共用** ] 視窗的螢幕擷取畫面，顯示三個共用選項。 
  
![使用 SharedWithUsersOWSUser 屬性的搜尋查詢會傳回與特定人員共用的檔案](../media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
使用此屬性的搜尋查詢，只會傳回使用第三個選項共用的檔 (與 **特定人員**) 共用  `SharedWithUsersOWSUser` 。 

## <a name="searching-for-skype-for-business-conversations"></a>搜尋商務用 Skype 交談

您可以使用下列關鍵字查詢，在商務用 Skype 交談中特別搜尋內容：

```powershell
kind:im
```

先前的搜尋查詢也會從 Microsoft 小組傳回聊天。 若要避免這種情況，您可以縮小搜尋結果，以包含使用下列關鍵字查詢的商務用 Skype 交談：

```powershell
kind:im AND subject:conversation
```

上一個關鍵字查詢不包括 Microsoft 團隊中的研討，因為商務用 Skype 交談是以電子郵件形式儲存，而主題行會以「交談」一詞開頭。

若要搜尋在特定日期範圍內發生的商務用 Skype 交談，請使用下列關鍵字查詢：

```powershell
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="search-tips-and-tricks"></a>搜尋秘訣與技巧

- 關鍵字搜尋不區分大小寫。 例如， **cat** 和 **cat** 會傳回相同的結果。 

- 布林運算子 **AND**、 **OR**、 **NOT** 和 **NEAR** 必須是大寫。 

- 兩個關鍵字之間的空格或兩個  `property:value` 運算式與使用 **AND** 相同。 例如，傳回  `from:"Sara Davis" subject:reorganization` 所有由 Sara Davis 所傳送，包含主旨行中的 word 重新組織的郵件。 

- 使用符合格式的語法 `property:value` 。 值不區分大小寫，而且在運算子之後不能有空格。 如果有空格，您的預期值將會是全文檢索。 例如 `to: pilarp` ，搜尋 "pilarp" 做為關鍵字，而不是傳送給 pilarp 的郵件。 

- 搜尋收件者屬性（例如 To、From、Cc 或收件者）時，您可以使用 SMTP 位址、別名或顯示名稱來表示收件者。 例如，您可以使用 pilarp@contoso.com、pilarp 或 "Pilar Pinilla"。

- 您只能使用首碼萬用字元搜尋;例如， **cat \* *_ 或 _* 集 \* *_。尾碼搜尋 (_* \* cat**) 、中綴搜尋 (**c \* t**) 及子字串搜尋 (不支援 **\* cat \***) 。

- 搜尋屬性時，如果搜尋值是由多個字組成，請使用雙引號 ( "" ) 。 例如，傳回在主旨 `subject:budget Q1` 行中包含 **預算** 的郵件，或在郵件中或任何郵件內容中包含 **Q1** 的郵件。 使用 `subject:"budget Q1"` 會傳回所有包含「 **預算 Q1** 」主題行中的郵件。

- 若要從搜尋結果中排除以特定屬性值標示的內容，請在屬性名稱前面加上減號 ( ) 。 例如， `-from:"Sara Davis"` 排除在 Sara Davis 所傳送的任何郵件。

- 您可以根據郵件類型匯出專案。 例如，若要在 Microsoft 小組中匯出 Skype 交談和聊天，請使用語法 `kind:im` 。 若只要傳回電子郵件訊息，您會使用 `kind:email` 。 若要傳回 Microsoft 小組中的研討、會議及通話，請使用 `kind:microsoftteams` 。