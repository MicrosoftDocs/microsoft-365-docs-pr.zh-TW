---
title: 'DLP 原則條件、例外狀況和動作 (預覽) '
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 深入瞭解 dlp 原則狀況和例外狀況
ms.openlocfilehash: 5c2c8e010047c2de05cc8422da1958e2fe5fc54c
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604213"
---
# <a name="dlp-policy-conditions-exceptions-and-actions-preview"></a>DLP 原則條件、例外狀況和動作 (預覽) 

DLP 原則中的條件和例外情況可識別原則所套用的敏感專案。 動作會定義符合例外狀況的結果會產生什麼影響。

- 條件會定義要包含的專案
- 例外狀況定義要排除的專案。
- 動作會定義符合條件或例外狀況的結果
 
大多數的條件和例外狀況都有一個支援一或多個值的屬性。 例如，如果要將 DLP 原則套用至 Exchange 電子郵件，則 **寄件者** 為條件時，需要郵件的寄件者。 Some conditions have two properties. 例如， **郵件頭包含的任何字條件都** 需要一個屬性來指定郵件頭欄位，另一個屬性指定要在標頭欄位中尋找的文字。 有些條件或例外狀況沒有任何屬性。 例如， **附件是受密碼保護** 的條件，只會在受密碼保護的郵件中尋找附件。

動作通常需要其他屬性。 例如，當 DLP 原則規則重新導向郵件時，您必須指定重新導向郵件的位置。 
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>DLP 原則的條件和例外狀況

下列各節中的表格說明 DLP 中提供的條件和例外狀況。

- [寄件者](#senders)
- [收件者](#recipients)
- [郵件主題或本文](#message-subject-or-body)
- [Attachments](#attachments)
- [郵件頭](#message-headers)
- [郵件屬性](#message-properties)

### <a name="senders"></a>寄件者


|**DLP 中的條件或例外狀況**  |**Microsoft 365 PowerShell 中的條件/例外參數** |**屬性類型**  |**描述**|
|---------|---------|---------|---------|
|寄件者是 |條件： *從* <br/> 例外狀況： *ExceptIfFrom*      |Addresses |     組織中指定的信箱、郵件使用者、郵件連絡人或 Microsoft 365 群組所傳送的郵件。|
|寄件者 IP 位址為     |條件： *SenderIPRanges*<br/> 例外狀況： *ExceptIfSenderIPRanges*         |  IPAddressRanges       | 寄件者的 IP 位址符合指定 IP 位址的郵件，或位於指定的 IP 位址範圍內。       |
|寄件者位址包含文字   | 條件： *FromAddressContainsWords* <br/> 例外狀況： *ExceptIfFromAddressContainsWords*        |   Words      |   寄件者電子郵件地址中包含指定文字的郵件。|
| 寄件者位址符合模式    | 條件： *FromAddressMatchesPatterns* <br/> 例外狀況： *ExceptFromAddressMatchesPatterns*       |      模式   |  寄件者的電子郵件地址包含符合指定正則運算式之文字模式的郵件。  |
|Sender domain 是  |  條件： *SenderDomainIs* <br/> 例外狀況： *ExceptIfSenderDomainIs*       |DomainName         |     寄件者電子郵件地址的網域符合指定值的郵件。 如果您需要尋找 *包含* 指定網域的寄件者網域 (例如，網域的任何子域) ，請使用 **寄件者位址符合** (*FromAddressMatchesPatterns*) 條件，並使用語法： ' \. domain \. com $ ' 指定網域。    |
|寄件者範圍    | 條件： *FromScope* <br/> 例外狀況： *ExceptIfFromScope*    | UserScopeFrom    |    由內部或外部寄件者所傳送的郵件。    |

### <a name="recipients"></a>收件者

|**DLP 中的條件或例外狀況**| **Microsoft 365 PowerShell 中的條件/例外參數** |    **屬性類型** | **描述**|
|---------|---------|---------|---------|
|收件者為|  條件： *SentTo* <br/> 例外狀況： *ExceptIfSentTo* | Addresses | 其中一位收件者是組織中指定的信箱、郵件使用者或郵件連絡人的郵件。 收件者可以位於郵件 **的 [收** 件者 **]、[** 副本] 或 [ **密件副本** ] 欄位。|
|收件者網域為|   條件： *RecipientDomainIs* <br/> 例外狀況： *ExceptIfRecipientDomainIs* |   DomainName |    寄件者電子郵件地址的網域符合指定值的郵件。|
|收件者位址包含文字|  條件： *RecipientAddressContainsWords* <br/> 例外狀況： *ExceptIfRecipientAddressContainsWords*|    Words|  在收件者的電子郵件地址中包含指定文字的郵件。 <br/>**注意事項**：這種情況並未考慮傳送至收件者 Proxy 位址的郵件。而只比對傳送至收件者主要電子郵件地址的郵件。|
|收件者位址符合模式| 條件： *RecipientAddressMatchesPatterns* <br/> 例外狀況： *ExceptIfRecipientAddressMatchesPatterns*|   模式    |收件者的電子郵件地址包含符合指定正則運算式之文字模式的郵件。 <br/> **注意事項**：這種情況並未考慮傳送至收件者 Proxy 位址的郵件。而只比對傳送至收件者主要電子郵件地址的郵件。|
|傳送給隸屬的| 條件： *SentToMemberOf* <br/> 例外狀況： *ExceptIfSentToMemberOf*|  Addresses|  郵件包含的收件者屬於指定通訊群組、擁有郵件功能的安全性群組或 Microsoft 365 群組的成員。 群組可以位於郵件的 [ **收件者**] **、[** 副本] 或 [ **密件副本** ] 欄位中。|

### <a name="message-subject-or-body"></a>郵件主題或本文

|**DLP 中的條件或例外狀況** | **Microsoft 365 PowerShell 中的條件/例外參數** |**屬性類型**| **描述**|
|---------|---------|---------|---------|
|主旨包含字詞或片語| 條件： *SubjectContainsWords* <br/> 例外狀況： *ExceptIf SubjectContainsWords*| Words   |在 [主旨] 欄位中具有指定文字的郵件。|
|主題符合模式|條件： *SubjectMatchesPatterns* <br/> 例外狀況： *ExceptIf SubjectMatchesPatterns*|模式   |使用主旨欄位包含符合指定正則運算式之文字模式的郵件。|
|內容包含|  條件： *ContentContainsSensitiveInformation* <br/> 例外狀況 *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  包含資料遺失防護 (DLP) 原則所定義之敏感資訊的郵件或檔。|
| 主旨或內文符合模式    | 條件： *SubjectOrBodyMatchesPatterns* <br/> 例外狀況： *ExceptIfSubjectOrBodyMatchesPatterns*    | 模式    | 主旨欄位或郵件內文包含符合指定正則運算式之文字模式的郵件。    |
| 主旨或內文包含文字    | 條件： *SubjectOrBodyContainsWords* <br/> 例外狀況： *ExceptIfSubjectOrBodyContainsWords*    | Words    | 在 [主旨] 欄位或郵件內文中具有指定文字的郵件    |


### <a name="attachments"></a>附件

|**DLP 中的條件或例外狀況**| **Microsoft 365 PowerShell 中的條件/例外參數**| **屬性類型**   |**描述**|
|---------|---------|---------|---------|
|附件受密碼保護|條件： *DocumentIsPasswordProtected* <br/> 例外狀況： *ExceptIfDocumentIsPasswordProtected*|無| 郵件中的附件受到密碼保護 (，因此無法) 進行掃描。 密碼偵測只適用于 Office 檔、.zip 檔及7z 檔案。|
|附件的副檔名是|條件： *ContentExtensionMatchesWords* <br/> 例外狀況： *ExceptIfContentExtensionMatchesWords*|  Words   |附件的副檔名符合任何指定文字的郵件。|
|無法掃描任何電子郵件附件的內容|條件： *DocumentIsUnsupported* <br/>例外狀況： *ExceptIf DocumentIsUnsupported*|   不適用|    Exchange Online 未原本識別附件的郵件。|
|任何電子郵件附件的內容未完成掃描|   條件： *ProcessingLimitExceeded* <br/> 例外狀況： *ExceptIfProcessingLimitExceeded*|    不適用 |規則引擎無法完成附件掃描的訊息。 您可以使用此條件建立共同運作的規則，以識別及處理無法完全掃描內容的郵件。|
|檔案名稱包含文字|條件： *DocumentNameMatchesWords* <br/> 例外狀況： *ExceptIfDocumentNameMatchesWords* |Words  |附件的檔案名符合任何指定文字的郵件。|
|檔案名稱符合模式|條件： *DocumentNameMatchesPatterns* <br/> 例外狀況： *ExceptIfDocumentNameMatchesPatterns*|    模式    |附件的檔案名包含符合指定正則運算式之文字模式的郵件。|
|文件屬性為|條件： *ContentPropertyContainsWords* <br/> 例外狀況： *ExceptIfContentPropertyContainsWords* |Words| 附件的副檔名符合任何指定文字的郵件或檔。|
|檔案大小等於或大於| 條件： *DocumentSizeOver* <br/> 例外狀況： *ExceptIfDocumentSizeOver*|    大小    |任何附件大於或等於指定值的郵件。|

### <a name="message-headers"></a>郵件頭

|**DLP 中的條件或例外狀況**| **Microsoft 365 PowerShell 中的條件/例外參數**| **屬性類型**|  **描述**|
|---------|---------|---------|---------|
|標頭包含字或片語|條件： *HeaderContainsWords* <br/> 例外狀況： *ExceptIfHeaderContainsWords*|  雜湊表  |包含指定之標頭欄位及該標頭欄位的值包含指定文字的郵件。|
|標頭符合模式|   條件： *HeaderMatchesPatterns* <br/> 例外狀況： *ExceptIfHeaderMatchesPatterns*|    雜湊表  |包含指定之標頭欄位的郵件，而該標頭欄位的值包含指定的正則運算式。|

### <a name="message-properties"></a>郵件屬性

|**DLP 中的條件或例外狀況**| **Microsoft 365 PowerShell 中的條件/例外參數**| **屬性類型**   |**描述**|
|---------|---------|---------|---------|
|郵件大小超過|條件： *MessageSizeOver* <br/> 例外狀況： *ExceptIfMessageSizeOver*| 大小    |郵件的總大小 (郵件加上附件) 大於或等於指定的值。 <br/>**附注**：信箱的郵件大小限制會在郵件流程規則之前評估。 信箱過大的郵件會遭到拒絕，但具有此條件的規則才能對郵件採取動作。|
| 重要性    | 條件： *WithImportance* <br/> 例外狀況： *ExceptIfWithImportance*    | Importance    | 以指定的重要性層級標記的郵件。    |
| 內容字元集包含文字    | 條件： *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*    | CharacterSets    | 具有任何指定之字元集名稱的郵件。    |
| 具有寄件者覆寫    | 條件： *HasSenderOverride* <br/> 例外狀況： *ExceptIfHasSenderOverride*    | 不適用    | 寄件者已選擇覆寫資料遺失防護 (DLP) 原則的郵件。 如需 DLP 原則的詳細資訊，請參閱 [資料遺失防護](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)。   |
| 郵件類型符合    | 條件： *MessageTypeMatches* <br/> 例外狀況： *ExceptIfMessageTypeMatches*    | MessageType    | 指定類型的郵件。    |

## <a name="actions-for-dlp-policies"></a>DLP 原則的動作

此表說明 DLP 中可用的動作。


|**DLP 中的動作**|**Microsoft 365 PowerShell 中的動作參數**|**屬性類型**|**描述**|
|---------|---------|---------|---------|
|設定標頭|SetHeader|第一個屬性： *標頭名稱* </br> 第二個屬性： *標頭值*|SetHeader 參數會指定 DLP 規則的動作，以新增或修改郵件頭中的標頭欄位和值。 這個參數使用語法 "HeaderName： HeaderValue"。 您可以指定多個標頭名稱及以逗號分隔的值組|
|移除標頭| RemoveHeader| 第一個屬性： *MessageHeaderField*</br> 第二個屬性： *字串*|  RemoveHeader 參數會指定 DLP 規則的動作，該規則會從郵件頭中移除標頭欄位。 這個參數使用語法 "HeaderName" 或 "HeaderName： HeaderValue"。您可以指定多個標頭名稱或標頭名稱及用逗號分隔的值組|
|將郵件重新導向至特定使用者|*RedirectMessageTo*|Addresses| 將郵件重新導向至指定的收件者。 郵件不會傳遞給原始的收件者，也不會傳送任何通知給寄件者或原始的收件者。|
|轉寄郵件以核准給寄件者的管理員| 仲裁|第一個屬性： *ModerateMessageByManager*</br> 第二個屬性： *Boolean*|適中參數會指定將電子郵件訊息傳送給仲裁者的 DLP 規則動作。 這個參數使用下列語法： @ {ModerateMessageByManager = <$true \| $false>;|
|將郵件轉寄給特定核准者| 仲裁|第一個屬性： *ModerateMessageByUser*</br>第二個屬性： *位址*|適中參數會指定將電子郵件訊息傳送給仲裁者的 DLP 規則動作。 這個參數會使用下列語法： @ {ModerateMessageByUser = @ ( "emailaddress1"，"emailaddress2",... "emailaddressN" ) }|
|新增收件者|AddRecipients|第一個屬性： *欄位*</br>第二個屬性： *位址*| 在郵件的 [收件者/Cc/Bcc] 欄位中新增一或多個收件者。 這個參數使用下列語法： @ {<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"}|
|將寄件者的管理員新增為收件者|AddRecipients | 第一個屬性： *AddedManagerAction*</br>第二個屬性： *欄位* | 將寄件者的管理員新增到郵件中，當作指定的收件者類型 ( 至、抄送、Bcc ) 或將郵件重新導向給寄件者的管理員，而不會通知寄件者或收件者。 只有在 Active Directory 中定義寄件者的管理員屬性時，此動作才有效。 此參數會使用下列語法： @ {AddManagerAsRecipientType = "<To \| Cc \| Bcc>"}|    
前置主題    |PrependSubject    |字串    |會將指定的文字加入郵件的 [主旨] 欄位的開頭。 請考慮使用空格或冒號 (： ) 做為指定之文字的最後一個字元，以與原始的主旨文字區別。</br>若要防止將相同字串新增至已包含主旨 (中之文字的郵件，例如，回復) 中，新增「主旨包含字」 (ExceptIfSubjectContainsWords) 例外規則。    |
套用 HTML 免責聲明    |ApplyHtmlDisclaimer    |第一個屬性： *文字*</br>第二個屬性： *位置*</br>第三個屬性： *Fallback 動作*    |將指定的 HTML 免責聲明套用至郵件所需的位置。</br>此參數會使用下列語法： @ {Text = "";Location = <Append \| 前置>;FallbackAction = <Wrap \| 略過 \| 拒絕>}




