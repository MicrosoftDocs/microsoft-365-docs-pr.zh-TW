---
title: 監督原則
description: 瞭解如何在 Microsoft 365 中使用監察原則，以透過指定的檢閱者來捕獲員工的通訊以進行考試。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.custom: seo-marvel-apr2020
titleSuffix: Microsoft 365 Compliance
ms.openlocfilehash: 45dc5a3e9674ebdf9488d14813abf04fc81b6781
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327251"
---
# <a name="supervision-policies"></a>監督原則

>[!IMPORTANT]
>在2月2020中，遵循 Microsoft 365 合規性中的通訊相容性，便會停用 Office 365 中的監督。 監管原則將不再可供建立，而且最終將會在唯讀的唯讀存取之後移除原則。
>
>如果您使用監督，請注意：
>
>- 從2020年6月15日起，承租人將無法建立新的監察原則。
>- 2020年8月31日開始，現有的原則將停止捕獲新的郵件。
>- 從2020年10月26日開始，將會刪除現有的原則。
>
>我們積極鼓勵目前探索或使用 Office 365 內監察的客戶，以使用新的[通訊相容性](communication-compliance.md)解決方案，利用一組更豐富的智慧功能來處理通訊監視或法規需求。

Microsoft 365 中的監督原則可讓您透過指定的檢閱者，捕獲員工的通訊以進行檢查。 您可以定義特定原則，以在您的組織中捕獲內部及外部電子郵件、Microsoft 小組或協力廠商通訊。 然後，檢閱者可以檢閱郵件，以確定郵件符合您組織的郵件標準，並使用分類類型解析郵件。

這些原則也可協助您克服許多現代的相容性挑戰，包括：

- 監視不斷增加的通訊通道類型
- 不斷增加的郵件資料量
- 規章強制執行 & 遭到罰款的風險

在某些組織中，IT 支援和規範管理群組之間可能會有不同的職責。 Microsoft 365 支援監察性原則功能設定與所捕獲通訊原則設定之間的分隔。 例如，組織的 IT 群組可能負責設定角色許可權和群組，以支援由組織的合規性小組所設定及管理的監督原則。

如需監督原則的快速流覽，請參閱[Microsoft 機械通道](https://www.youtube.com/user/OfficeGarageSeries)上的[監管原則影片](https://youtu.be/C3Y8WZ7o_dI)。

## <a name="transitioning-from-supervision"></a>從監察中轉換

使用監察原則及規劃，以[在 Microsoft 365 中轉換至通訊合規性原則的](communication-compliance.md)組織，必須瞭解這些重要的要點：

- Microsoft 365 中的監督解決方案將會完全取代于 Microsoft 365 中的通訊相容性解決方案。 針對從監察原則過渡到通訊合規性的組織，建議在通訊合規性中建立新原則，這些原則與現有的監督原則具有相同的*條件*，以啟用新的調查和修正功能。 當轉換為 Microsoft 365 中的通訊法規遵從性時，如果您有內部合規性保留原則需求，您應該規劃從監察中匯出報表資料。
- 在過渡期間，組織可以並排使用這兩種解決方案，直到完全遷移，但每個方案中所用的原則都必須有*唯一的原則名稱*。 群組和自訂關鍵字字典可以在過渡期間內共用方案。
- Microsoft 365 原則相符專案中所儲存的監察性郵件，無法在 Microsoft 365 中移動或共用至通訊合規性。

如需 Office 365 中監督的退休資訊，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)以取得詳細資訊。

## <a name="scenarios-for-supervision-policies"></a>監察原則的案例

監督原則可協助您監視組織中的通訊數：

- **公司原則**

    員工必須遵循其所有與業務相關的通訊中可接受的使用、道德標準及其他公司原則。 監督原則可以偵測原則違規，並協助您採取糾正動作，協助緩解這些類型的事件。 例如，您可以監視潛在的人力資源違規，例如騷擾或使用不當或冒犯性語言的員工通訊。

- **風險管理**

    組織負責在其基礎結構和公司網路系統之間散佈的所有通訊。 使用監察原則來協助識別及管理可能的法律公開和風險，可協助您降低風險，使其不會損毀公司運作。 例如，您可以針對機密專案（例如即將進行的收購、合併、收入披露、reorganizations 或領導小組變更），監控您的組織是否有未授權的通訊。

- **法規遵從性**

    大多數的組織必須遵守某些類型的規章遵循標準，成為其正常運作程式的一部分。 這些法規通常會要求組織執行某些類型的監察或監管程式，以進行適用于其行業的郵件功能。 財務行業規章機關（FINRA） Rule 3110 是一個很好的例子，讓組織具備監管程式程式，以監視員工的活動，以及其所參與的企業類型。 另一個範例可能需要在您的組織中監控經紀人代理商，以防範可能的 laundering、內幕交易、collusion 或 bribery 活動。 監督原則可協助您的組織提供監控和報告公司通訊的程式，以符合這些需求。

## <a name="components"></a>零件

### <a name="supervision-policy"></a>監督原則

在 [規範中心] 中建立監督原則。 這些原則定義哪些通訊和使用者在您的組織中可供審閱、定義通訊必須符合的自訂條件，以及指定應執行複查的人員。 「主管審查」角色群組中包含的使用者可以設定原則，以及已指派此角色的任何人員，都可以存取規範中心內的監管頁面。

### <a name="supervised-users"></a>監督的使用者

開始使用監督之前，必須先判斷誰需要查看其通訊。 在原則中，使用者電子郵件地址可識別要監督的個人或人員群組。 這些群組的一些範例是 Microsoft 365 群組、Exchange 型通訊群組清單和 Microsoft 小組頻道。 您也可以從監督的群組或群組清單中排除特定的使用者或群組。

>[!IMPORTANT]
>監控原則所監控的使用者，必須具備 Microsoft 365 E5 相容性授權、具有高級合規性附加元件的 Office 365 企業版 E3 授權，或是包含在 Office 365 企業版 E5 訂閱中，或包含在 Microsoft 365 E5 訂閱中。如果您沒有現有的企業版 E5 計畫，而且想要嘗試監督，您可以[註冊 Office 365 Enterprise e5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。

### <a name="reviewers"></a>檢閱者

當您建立監督原則時，必須決定誰將會對監督使用者的郵件執行審查。 在原則中，使用者電子郵件地址可識別人員或群組，以查看已監督的通訊。 所有檢閱者都必須在 Exchange Online 上主控信箱。

### <a name="groups-for-supervised-users-and-reviewers"></a>監督的使用者和檢閱者群組

若要簡化您的設定，請為需要查看其通訊的使用者建立群組，並為查看那些通訊的使用者群組。 如果您正在使用群組，可能需要數個。 例如，如果您想要監視兩個不同的使用者群組之間的通訊，或是想要指定未監督的群組。

當您為監督的使用者選取 Microsoft 365 群組時，該原則會監控共用信箱的內容，以及與群組相關聯的 Microsoft 小組通道。 當您選取通訊群組清單時，該原則會監控個別的使用者信箱。

### <a name="supported-communication-types"></a>支援的通訊類型

透過監察原則，您可以選擇在下列一或多個通訊平臺中監視郵件：

- **Exchange 電子郵件：** 在 Exchange Online 上主控的信箱是 Microsoft 365 訂閱的一部分，都符合郵件監督。 電子郵件和附件符合監管原則條件立即可用於監控和監督報告。 支援的監察附件類型與[Exchange 郵件流程規則內容檢查支援的檔案類型](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)相同。

- **Microsoft 團隊：** 公開和私人 Microsoft 小組通道和個別聊天中的聊天通訊和相關聯的附件都會受到監督。 小組聊天符合監管原則條件的處理頻率為24小時一次，並可在監督報告中進行監視。 使用下列群組管理設定來監督小組中個別的使用者聊天與通道通訊：

    - **針對團隊聊天監察：** 指派個別使用者或指派[通訊群組](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)至監管原則。 此設定適用于1對1或1對許多使用者/聊天關聯。
    - 若**為小組通道通訊：** 將您想要監視的每個 Microsoft 小組通道或 Microsoft 365 群組指派給監管原則，其中包含特定使用者。 如果您將相同使用者新增至其他 Microsoft 小組通道或 Microsoft 365 群組，請務必將這些新的通道和群組新增至監管原則。

- **商務用 Skype Online：** 可監督商務用 Skype Online 中的聊天通訊和相關聯的附件。 商務用 Skype Online 聊天符合監管原則條件的處理頻率為每24小時一次，且可用於監控和監察報告。 受監視的聊天對話是源自[先前在商務用 Skype Online 中所儲存的交談](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)。  在商務用 Skype Online 中使用下列群組管理設定來監督使用者聊天通訊：

    - 若**為商務用 Skype Online 研討監察專案：** 指派個別使用者或指派[通訊群組](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)至監管原則。 此設定適用于1對1或1對許多使用者/聊天關聯。

- **協力廠商來源：** 您可以監督來自協力廠商來源（如 Facebook 或 DropBox）的通訊，以用於匯入到組織中信箱的資料。 [瞭解如何匯入協力廠商資料](archiving-third-party-data.md)。

依預設，每個原則都會保留每個原則所捕獲的通訊，即使使用者離開您的組織而且其信箱已刪除也是一樣。

### <a name="policy-settings"></a>原則設定

#### <a name="direction"></a>方向

依預設，會顯示**方向為**condition，而且無法移除。 原則中的通訊方向設定會個別或一起選擇：

- **輸入**：您可以選擇 [**輸入**]，以查看傳送**至**您選擇要從原則中未包含**之人員之**人員的通訊。
- **輸出**：您可以選擇 [**輸出**] 如果您想要從您選擇的人員那裡，查看**要對**原則中未包含**之**人員所傳送的通訊。
- **Internal**：您可以選擇 [**內部**]，以查看您在原則中所識別之人員**之間**傳送的通訊。

#### <a name="sensitive-information-types"></a>敏感性資訊類型

您可以選擇在監管原則中包含敏感資訊類型。 敏感資訊類型是預先定義或自訂的資料類型，可協助識別及保護信用卡號碼、銀行帳戶號碼、護照號碼等等。 「[資料遺失防護」（DLP）](data-loss-prevention-policies.md)的一部分，敏感資訊設定可使用模式、字元鄰近性、信賴層級，甚至是自訂資料類型，協助識別及標記可能機密的內容。 預設的機密資訊類型包括：

- 金融業
- 醫療與健康情況
- 隱私權
- 自訂資訊類型

若要深入瞭解敏感資訊詳細資料和預設類型中所包含的模式，請參閱[敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)。

#### <a name="custom-keyword-dictionaries"></a>自訂關鍵字字典

設定自訂關鍵字字典（或詞典），以提供組織或行業特有關鍵詞的簡單管理。 關鍵字字典最多可支援每個字典的100000字詞。 如有需要，您可以將多個自訂關鍵字字典套用至單一原則，或在每個原則中有單一關鍵字字典。 這些字典是指派于監管原則中的，可來源於檔案（例如 .csv 或 .txt 清單），或是您可以[在規範中心內匯入](create-a-keyword-dictionary.md)的清單。

#### <a name="offensive-language"></a>冒犯性語言

在您的組織中監控傳送或接收的電子郵件訊息，以用於冒犯性語言。 模型使用電腦學習、人工情報和關鍵字的組合，識別可能違反反騷擾和霸淩原則的電子郵件訊息中的語言。 冒犯性語言模型目前支援英文關鍵字，並監控電子郵件的正文。

>[!NOTE]
>如果您需要進行下列作業，請建立具有封鎖字詞之[自訂關鍵字字典](create-a-keyword-dictionary.md)的[資料遺失防護原則](create-test-tune-dlp-policy.md)：
>
>- 監控組織中的攻擊性語言的 Microsoft 小組通訊
>- 在組織中的通訊中防止或封鎖冒犯性語言

模型並未提供冒犯性語言的詳盡清單。 此外，語言和文化標準也會不斷變更，但在這些現實中，Microsoft 保留以其判斷來更新模型的權利。 雖然模型可協助您的組織監控冒犯性語言，但模型並未提供組織的唯一監視或定址這類語言的方式。 您的組織，而非 Microsoft，仍然負責監控與封鎖冒犯性語言相關的所有決策。

冒犯性語言模型會監控與下列語言類型相關的 sentiment 電子郵件：

|**類型**|**描述**|
|:-----|:-----|
| **Profanities** | Embarrass 大部分人員的運算式。 |
| **辱駡** | 針對特定群組（例如，種族、ethnicity、性方向、傷殘）進行快速 prejudice 的運算式。 |
| **嘲弄** | Taunt、condemn、ridicule 或可能導致 anger 或暴力的運算式。 |
| **偽裝運算式** | 含義或發音與另一個更具冒犯性字詞的運算式。 |

#### <a name="conditional-settings"></a>設定條件設定
<a name="ConditionalSettings"> </a>

您針對原則所選擇的條件，會套用到您組織中的電子郵件和協力廠商來源的通訊（如 Facebook 或 DropBox）。

下表說明每個條件的詳細資訊。
  
|**條件**|**如何使用此條件**|
|:-----|:-----|
| **從這些網域接收郵件** <br><br> **不會從這些網域接收郵件** | 套用原則，以包含或排除已接收郵件中的特定網域或電子郵件地址。 輸入每個網域或電子郵件地址，並以逗點分隔多個網域或電子郵件地址。 每個輸入的功能變數名稱或電子郵件地址會分開套用，只有一個網域或電子郵件地址必須套用原則才能套用至郵件。 <br><br> 如果您想要監視所有來自特定網域的電子郵件，但不想要排除（電子報、宣告等）以外的郵件，您必須設定條件：**不會從任何**排除電子郵件地址的網域條件接收郵件（範例是 "newsletter@contoso.com"）。 |
| **郵件會傳送至這些網域中的任何一個** <br><br> **郵件不會傳送至此任何網域** | 套用原則，以包含或排除已傳送郵件中的特定網域或電子郵件地址。 輸入每個網域或電子郵件地址，並以逗點分隔多個網域或電子郵件地址。 每個網域或電子郵件地址都是分開套用，只有一個網域或電子郵件地址必須套用原則才能套用至郵件。 <br><br> 如果您想要監視所有傳送至特定網域的電子郵件，但不想要排除已傳送且不需要檢查的郵件，則必須設定兩個條件： <br> -將**郵件傳送至任何**定義網域（"contoso.com"）的網域條件，然後 <br> -**不會將郵件傳送至任何**包括電子郵件地址（"subscriptions@contoso.com"）的網域條件。 |
| **郵件是使用下列任一標籤分類** <br><br> **郵件未使用下列任何一種標籤進行分類** | 在郵件中包含或排除某些保留標籤時套用原則。 保留標籤必須個別設定，且已設定的標籤會選做為此狀況的一部分。 您選擇的每一個標籤會分開套用（只有其中一個標籤必須套用，原則才能套用至郵件）。 如需設定保留標籤的詳細資訊，請參閱[保留標籤簡介](labels.md)。|
| **郵件包含下列任何文字** <br><br> **郵件不包含任何這些字詞** | 若要在郵件中包含或排除某些字詞或片語時套用原則，請輸入每個單字或片語，並以逗號分隔。 您輸入的每個字都會分開套用（只有一個字必須套用，原則才能套用至郵件）。 如需輸入單字或片語的詳細資訊，請參閱下一節[將字詞和片語比對電子郵件或附件](supervision-policies.md#Matchwords)。|
| **附件包含下列任一字** <br><br> **附件不包含任何這些字詞** | 若要在郵件附件（例如 Word 檔）中包含或排除某些字詞或片語時套用原則，請輸入每個單字或片語，並以逗號分隔。 您輸入的每個字都會分開套用（只有一個字必須套用，原則才能套用至附件）。 如需輸入單字或片語的詳細資訊，請參閱下一節[將字詞和片語比對電子郵件或附件](supervision-policies.md#Matchwords)。|
| **附件為下列其中一種檔案類型** <br><br> **附件不是任何檔案類型** | 若要監督包含或排除特定類型附件的通訊，請輸入副檔名（例如 .exe 或 .pdf）。 如果您想要包含或排除多個副檔名，請在個別的行上輸入這些副檔名。 只有一個附件副檔名必須符合原則才能套用。|
| **郵件大小大於** <br><br> **郵件大小不大於** | 若要根據特定大小來查看郵件，請使用下列條件，指定郵件可供審閱之前的最大或最小大小。 例如，如果您指定的**郵件大小大於** \> **1.0 MB**，則所有 1.01 MB 和更大的郵件都會進行審閱。 您可以選擇此條件的位元組、kb、mb 或 gb。|
| **附件大於** <br><br> **附件不大於** | 若要根據附件大小來查看郵件，請指定郵件之前的附件大小上限或最小值。 例如，如果您指定的**附件**大於 \> **2.0 mb**，所有附件為 2.01 MB 的郵件都會進行審閱。 您可以選擇此條件的位元組、kb、mb 或 gb。|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>比對電子郵件或附件的字詞和片語
<a name="Matchwords"> </a>您輸入的每個字和以逗號分開的每一個字都會分開套用（原則條件必須套用至電子郵件或附件，才只有一個字必須套用）。 例如，我們會使用條件，**訊息包含這些字中的任何字**，關鍵字 "銀行家" 和「內幕交易」會以逗號（銀行家，內部交易）隔開。 原則套用至所有包含 "銀行家" 或 "內幕交易" 字樣的郵件。 若要套用此原則條件，只須出現其中一個字或片語。 郵件或附件中的文字必須完全符合您所輸入的文字。

若要同時掃描相同關鍵字的電子郵件和附件，請建立[資料遺失防護原則](create-test-tune-dlp-policy.md)，其中包含您想要監視之字詞的[自訂關鍵字字典](create-a-keyword-dictionary.md)。 此原則設定可識別出現在電子郵件**或**電子郵件附件中的已定義關鍵字。 使用標準條件式原則設定（*郵件包含*其中任何一個字和*附件包含這些字中的任何一詞*）來識別郵件和附件中的字詞時，會**同時**顯示郵件和附件中的字詞。
  
##### <a name="enter-multiple-conditions"></a>輸入多個條件

如果您輸入多個條件，則 Microsoft 365 會同時使用所有條件，以決定何時將原則套用至通訊專案。 當您設定多個條件時，必須符合原則才能套用的所有條件，除非您輸入例外狀況。 例如，如果郵件包含 "商貿" 一詞，且大小超過 2 MB，您就需要套用原則。 不過，如果郵件也包含「由 Contoso 金融核准」一詞，則不應套用此原則。 因此，在此情況下，三個條件如下：
  
- **郵件包含下列任何文字**，關鍵字為 "商貿"

- **郵件大小**大於，值為 2 MB

- **郵件不包含這些字**，但關鍵字「Contoso 財務小組核准」

#### <a name="review-percentage"></a>審閱百分比

如果您想要減少要檢查的內容數量，您可以指定監管原則所控制之所有通訊的百分比。 會從符合所選原則條件的總內容百分比選取即時、隨機的內容樣本。 如果您想要檢閱者審閱所有專案，您可以在監督原則中輸入**100%** 。

## <a name="monitor--manage"></a>監視 & 管理

您可以輕鬆監控監察原則的結果，並套用解決標記。 您可以快速查看：

- 已審閱專案的狀態
- 監管中的使用者和群組
- 指定為檢閱者的使用者和群組

### <a name="supervision-policy-dashboard"></a>監察原則儀表板

使用監管原則儀表板管理監督原則結果，並解決未完成的專案。 這個儀表板允許檢閱者查看需要檢查的專案、對專案採取動作，並查看每個監管原則先前檢查和解決的專案結果。 您可以在**監管**中心  >  *開啟您的自訂原則*，以存取監管原則儀表板  >  ** **。

#### <a name="dashboard-home"></a>儀表板首頁

儀表板**首頁**包含數個區段，可協助您快速對您的監管原則採取行動。 您可以在這裡進行下列作業：

- 快速閱讀本周的擱置和解決的亮點
- 查看選取原則的監督使用者和監督群組清單
- 查看選取原則的檢閱者及審查小組清單
- 查看哪些通訊平臺具有原則監管的內容

#### <a name="review-tab"></a>審閱] 索引標籤

[**回顧**] 索引標籤是檢閱者分類及解析所選取原則所識別之專案的所在位置。 您可以在這裡進行下列作業：

- 依擱置、相容性、不相容和可疑專案進行篩選。
- 將單一專案標記為相容、不相容或可疑。 您也可以記錄專案的批註，以協助澄清所採取的標記動作。
- 將多個專案大量標記為相容性、不相容或可疑。 您也可以記錄含有多個專案的批註，以協助澄清所採取的標記動作。
- 查看單一專案的標記記錄。 包含解析專案的人員、動作的日期和時間、解析標籤及包含的任何批註。
- 將先前檢查過的專案重新分類為相容性、不相容或可疑。 您也可以記錄含單一或多個專案的批註，以協助澄清所採取的重新分類動作。

#### <a name="resolved-items-tab"></a>[解析的專案] 索引卷

[**已解決的專案**] 索引標籤可讓檢閱者查看所有先前已解析的選取原則的專案。 您可以在這裡進行下列作業：

- 快速查看及排序已解決專案的主旨、寄件者和日期
- 查看任何選取專案的分類和批註記錄

## <a name="reports"></a>報告

使用監督報告來查看原則及檢閱者層級的「審閱」活動。 您也可以針對每個原則，查看目前的「考核」活動狀態的即時統計資料。 您可以使用監督報告：
  
- 請確認您的原則的運作方式如預期。
- 瞭解需要複查的通訊數量。
- 瞭解有多少通訊不相容，以及哪些通訊已通過複查。 這項資訊可協助您決定是否微調原則或變更檢閱者人數。

### <a name="view-the-supervision-report"></a>查看監督報告

1. 使用具有查看監督報告許可權的許可權，登入「[規範中心](https://compliance.microsoft.com)」和「系統管理」帳戶的認證。
2. 請移至 [**報告**] \> **儀表板**或 [**監察**]，以查看監督報告的小工具，以取得目前的監督原則活動摘要。
3. 選取**監督**小工具，以開啟 [詳細報告] 頁面。

>[!NOTE]
>如果您無法存取 [**報告**] 頁面，請檢查您是否為主管考核角色群組的成員，如您的[組織中](configure-supervision-policies.md)所述，請參閱。 包含在此角色群組中，可讓您建立及管理監督原則，以及執行報告。
  
### <a name="how-to-use-the-report"></a>如何使用報表

這份報告會列出每個原則，以及審查程式中每個階段的通訊數目。 使用此報告可：
  
- 查看所有或特定原則的資料。
- 查看依標記類型、檢閱者或郵件類型分組的資料。
- 根據活動日期、原則及檢閱者活動，將資料匯出到 CSV 檔案。
- 根據活動日期、標記類型、檢閱者和郵件類型來篩選資料。

以下是顯示 [**標記類型**] 欄的值的明細。
  
|**標記類型**|**含義**|
|:-----|:-----|
| **未檢查** | 尚未檢查的電子郵件數目。 這些電子郵件在 Microsoft 365 監督儀表板中等候審閱。
| **Compliant** | 已複查並標示為相容的電子郵件數目。 這些訊息仍然需要解決。 |
| **有疑問的** | 已複查並標示為可疑的電子郵件數目。 做為其他檢閱者的標誌，以協助檢查電子郵件是否需要針對法規遵從性進行調查。 這些訊息仍然需要解決。 |
| **不相容（主動）** | 檢閱者目前正在調查的非相容電子郵件數目。 |
| **不相容（已解析）** | 檢閱者調查並解決不相容的電子郵件數目。 |
| **點擊原則** | 符合監管原則中所定義之一或多個條件的 Exchange、小組和協力廠商資料來源中的郵件總數（每日） |
| **在 Purview** | 監督原則掃描之 Exchange、小組和協力廠商資料來源中的郵件總數（每日） |
| **Resolved** | 分類為**已解析**的 Exchange、小組和協力廠商資料來源中的郵件總數|

>[!NOTE]
>監察原則必須先進行布建，然後才會顯示在報告中。 若刪除原則，仍然會顯示歷史資料。 不過，它們會標示為「不存在的原則」，而且無法使用**Export**功能。

## <a name="audit"></a>審計

在某些情況下，您必須提供資訊給法規或合規性審計員，以證明員工活動和通訊的監管。 此資訊可能是與定義的原則或任何時刻監管原則變更相關之所有監察作業的摘要。 監督原則具有內建的審計追蹤，可完成內部或外部審計的完整準備工作。 監督原則所監控之每個動作的詳細審計歷史記錄，都提供監督程式的證明。

在整合的審計記錄檔中，會審核和使用下列監督原則活動：

|**活動**|**關聯的命令**|
|:-----|:-----|
| **建立原則** | [新 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2) <br> [新 SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule) |
| **編輯原則** | [Set-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2) <br> [Set-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule) |
| **刪除原則** | [Remove-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2) |

在整合的審計記錄檔或[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) PowerShell Cmdlet 中查看審核活動。

例如，下列範例會傳回所有主管審查活動（原則和規則）的活動，並列出每個專案的詳細資訊：

```PowerShell
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

此範例會傳回通訊相容性原則的更新活動：

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeletedAuditData
```

除了監督報告和記錄中提供的資訊之外，您也可以使用[SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity?view=exchange-ps) PowerShell Cmdlet，傳回所有監管原則活動的完整詳細清單。

## <a name="ready-to-get-started"></a>準備好開始使用了嗎？

若要設定組織的監察原則，請參閱[設定監督原則](configure-supervision-policies.md)。
