---
title: 通訊規範功能參考
description: Microsoft 365 中的通訊相容性功能參考。 瞭解每個功能元件的詳細資料和規格。
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
ms.openlocfilehash: 733abf925c80f90527b67660b84aea3e0482e906
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42635161"
---
# <a name="communication-compliance-feature-reference"></a>通訊規範功能參考

## <a name="policies"></a>原則

您可以在 Microsoft 365 規範中心建立 Microsoft 365 組織的通訊相容性原則。 如果您有 Office 365 組織，您會在 Office 365 安全性 & 規範中心[設定監督原則](configure-supervision-policies.md)。 通訊相容性原則定義哪些通訊和使用者在您的組織中有權複查、定義通訊必須符合的自訂條件，以及指定誰應該進行評論。 「**主管審查系統管理員**」角色群組中包含的使用者可以設定原則，以及已指派此角色的任何人都可以存取 Microsoft 365 規範中心內的**通訊合規性**頁面。 如有需要，您可以將對原則的修改記錄匯出至 .csv 檔案，該檔案也包含待處理的提醒狀態、已呈報的專案，以及已解析的專案。 無法重新命名原則，而且無法在不再需要時加以刪除。

>[!NOTE]
>在 Office 365 的「安全性與合規性中心」中建立的監督原則，可將 Office 365 訂閱遷移至 Microsoft 365。 如果您是從 Office 365 訂閱遷移至 Microsoft 365 訂閱，您將需要建立新的通訊相容性原則，以取代現有的監督原則。

## <a name="policy-templates"></a>原則範本

原則範本是預先定義的原則設定，可讓您快速建立原則，以解決常見的相容性案例。 這兩個範本的條件和範圍各有不同，而且所有範本都使用相同的掃描信號類型。 您可以從下列原則範本中選擇：

|**適用範圍**|**原則範本**|**詳細資料**|
|:-----|:-----|:-----|
| **冒犯性語言和反騷擾** | 監視冒犯性語言的通訊 | -位置： Exchange、小組、商務用 Skype <br> -Direction:Inbound、輸出、內部 <br> -審閱百分比：100% <br> -條件：冒犯性語言分類程式 |
| **敏感資訊** | 監視敏感資訊的通訊 | -位置： Exchange、小組、商務用 Skype <br> -Direction:Inbound、輸出、內部 <br> -審閱百分比：10% <br> -條件：機密資訊、現成的內容模式和類型、自訂字典選項、大於 1 MB 的附件 |
| **法規遵從性** | 監視與金融法規合規性相關的資訊的通訊 | -位置： Exchange、小組、商務用 Skype <br> -Direction:Inbound、輸出 <br> -審閱百分比：10% <br> -條件：自訂字典選項，大於 1 MB 的附件 |

## <a name="supervised-users"></a>監督的使用者

開始使用通訊相容性之前，必須先判斷誰需要查看其通訊。 在原則中，使用者電子郵件地址可識別要監督的個人或人員群組。 這些群組的一些範例是 Office 365 群組、Exchange 型通訊群組清單和 Microsoft 小組頻道。 您也可以從特定的排除群組或群組清單之外的掃描中排除特定的使用者或群組。

>[!IMPORTANT]
>通訊相容性原則所涵蓋的使用者，必須具備 Microsoft 365 E5 相容性授權、具有高級合規性附加元件的 Office 365 企業版 E3 授權，或是包含在 Office 365 企業版 E5 訂閱中。如果您沒有現有的企業版 E5 計畫，而且想要嘗試通訊相容性，您可以[註冊 Office 365 企業版 e5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。

## <a name="reviewers"></a>檢閱者

當您建立通訊相容性原則時，必須決定誰會審核使用者的郵件。 在原則中，使用者電子郵件地址可識別人員或群組，以查看已監督的通訊。 所有檢閱者都必須在 Exchange Online 上主控信箱，而且必須為**案例管理**和**審閱**角色指派信箱。

## <a name="groups-for-supervised-users-and-reviewers"></a>監督的使用者和檢閱者群組

若要簡化您的設定，請為需要查看其通訊的使用者建立群組，並為查看那些通訊的使用者群組。 如果您正在使用群組，可能需要數個。 例如，如果您想要掃描兩個不同的使用者群組之間的通訊，或是想要指定未監督的群組。

當您為監督的使用者選取 Office 365 群組時，該原則會掃描共用 Office 365 信箱的內容，以及與群組相關聯的 Microsoft 小組頻道。 當您選取通訊群組清單時，該原則會掃描個別的使用者信箱。

## <a name="supported-communication-types"></a>支援的通訊類型

透過通訊相容性原則，您可以選擇以群組或獨立來源的方式，在下列一或多個通訊平臺中掃描郵件。 依預設，每個原則都會保留每個原則所捕獲的通訊，即使使用者離開您的組織而且已刪除其信箱也是一樣。

- **Microsoft 小組**：您可以掃描公開和私人 Microsoft 團隊通道和個別聊天中的聊天通訊和相關聯的附件。 小組聊天和附件符合通訊合規性原則的情況可能需要長達24小時才能處理。 使用下列群組管理設定來監督小組中個別的使用者聊天與通道通訊：

    - **小組聊天通訊：** 指派個別使用者或指派[通訊群組](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)至通訊相容性原則。 此設定適用于一對一或一對多的使用者/聊天關聯。
    - 若**為小組通道通訊：** 將您想要掃描的每個 Microsoft 小組通道或 Office 365 群組指派給通訊相容性原則，其中包含特定的使用者。 如果您將相同使用者新增至其他 Microsoft 小組通道或 Office 365 群組，請務必將這些新的通道和群組新增至通訊合規性原則。

- **Exchange 電子郵件**：在 exchange Online 中主控的信箱，作為 Microsoft 365 或 Office 365 訂閱的一部分，都符合郵件掃描的條件。 Exchange 電子郵件訊息和附件符合通訊合規性原則的情況可能需要長達24小時才能處理。 支援的通訊遵循類型與[Exchange 郵件流程規則內容檢查所支援的檔案類型](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)相同。

- **商務用 Skype online**：可監督商務用 skype online 中的聊天通訊和相關聯的附件。 商務用 Skype Online 聊天符合通訊相容性原則的情況可能需要長達24小時才能處理。 受監視的聊天對話是源自[先前在商務用 Skype Online 中所儲存的交談](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)。  在商務用 Skype Online 中使用下列群組管理設定來監督使用者聊天通訊：

    - 若**為商務用 Skype Online 聊天通訊**：指派個別使用者或指派[通訊群組](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)至通訊相容性原則。 此設定適用于一對一或一對多的使用者/聊天關聯。

- **協力廠商來源**：您可以掃描來自協力廠商來源的通訊，以用於將資料匯入至 Microsoft 365 組織中的信箱。 連接器支援下列協力廠商資源：

    - [立即 Bloomberg](archive-instant-bloomberg-data.md)
    - [Facebook](archive-facebook-data-with-sample-connector.md)
    - [LinkedIn](archive-linkedin-data.md)
    - SAP SuccessFactors
    - [Twitter](archive-twitter-data-with-sample-connector.md)
    - [自訂資料連線器](archiving-third-party-data.md)

您必須先為 Microsoft 365 組織設定協力廠商連接器，才能將連接器指派給通訊相容性原則。 通訊相容性原則嚮導的 [ **Third-Party 來源**] 區段只會顯示目前設定的協力廠商連接器。

## <a name="transitioning-from-supervision-in-office-365"></a>從 Office 365 的監察過渡

組織使用 Office 365 中的監察原則，並在 Microsoft 365 中將其轉換為通訊法規遵從性原則時，需要瞭解這些重要的要點：

- 這兩種解決方案可能會同時用於您的組織，但是每個方案中所用的原則都必須有唯一的原則名稱。 群組和自訂關鍵字字典可以在過渡期間內共用方案。
- Office 365 原則相符中所儲存的監察性郵件，無法在 Microsoft 365 中移動或共用到通訊合規性中。
- Office 365 中的監督解決方案將會完全取代于 Microsoft 365 中的通訊相容性解決方案。 建議您在通訊合規性中建立新原則，這些原則與現有的監察原則具有相同的設定，以使用新的調查和修正功能。 當轉換為 Microsoft 365 中的通訊法規遵從性時，如果您有內部合規性保留原則需求，您應該規劃從 Office 365 中的監察權匯出報表資料。

如需 Office 365 中監督的退休資訊，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)以取得詳細資訊。

## <a name="policy-settings"></a>原則設定

### <a name="users"></a>使用者

您可以選擇選取 [**所有使用者**] 或 [在通訊合規性原則中定義特定的使用者]。 選取 [**所有使用者**] 會將原則套用至所有使用者，並將所有使用者都包含在成員中的群組。 定義特定的使用者會將原則套用至已定義的使用者，並將定義的使用者包含在成員中的任何群組。

### <a name="direction"></a>方向

依預設，會顯示**方向為**condition，而且無法移除。 原則中的通訊方向設定會個別或一起選擇：

- **輸入**：您可以選擇**輸入**，以檢查傳送**給**您選擇監督之人員的通訊。
- **輸出**：若您想要檢查從您選擇進行監督**之**人員所傳送的通訊，您可以選擇 [**輸出**]。
- **Internal**：您可以選擇 [**內部**]，以查看您在原則中所識別之人員**之間**傳送的通訊。

### <a name="sensitive-information-types"></a>敏感資訊類型

您可以選擇將敏感資訊類型包含在您的通訊合規性原則中。 敏感資訊類型是預先定義或自訂的資料類型，可協助識別及保護信用卡號碼、銀行帳戶號碼、護照號碼等等。 在 Office 365[資料遺失防護（DLP）](data-loss-prevention-policies.md)中，敏感資訊設定可使用模式、字元鄰近性、信賴等級，甚至是自訂資料類型，協助識別及標記可能機密的內容。 預設的機密資訊類型包括：

- 金融業
- 醫療與健康情況
- 隱私權
- 自訂資訊類型

若要深入瞭解敏感資訊詳細資料和預設類型中所包含的模式，請參閱[哪些敏感資訊類型的外觀](what-the-sensitive-information-types-look-for.md)。

### <a name="custom-keyword-dictionaries"></a>自訂關鍵字字典

設定自訂關鍵字字典（或詞典），以提供組織或行業特有關鍵詞的簡單管理。 關鍵字字典可支援每個字典最多100000個字詞，並支援任何語言。 如有需要，您可以將多個自訂關鍵字字典套用至單一原則，或在每個原則中有單一關鍵字字典。 這些字典是以通訊相容性原則指派，也可以來源於檔案（例如 .csv 或 .txt 清單），或是從您可以[在規範中心內匯入](create-a-keyword-dictionary.md)的清單中。 當您需要支援組織和原則特有的條款或語言時，請使用自訂字典。

### <a name="classifiers"></a>分類

內建的分類程式會針對不同類型的相容性問題，在組織中的所有通訊通道上，掃描傳送或接收的郵件。 分類器使用人工智慧和關鍵字的組合，識別可能違反反騷擾原則的郵件中的語言。 內建的分類器目前只支援電子郵件中的英文關鍵字。

通訊相容性內建的分類程式會掃描下列語言類型的字詞和 sentiment 的通訊：

- **威脅**：掃描對人員或財產認可暴力或實體傷害的威脅。
- **騷擾**：掃描針對種族、color、宗教、全國原產地的攻擊性行為。
- **猥褻語言**：掃描大多數人員 embarrass 的 profane 運算式。

內建的分類器不會在這些區域中提供詳盡的字詞清單。 此外，語言和文化標準也會不斷變更，但在這些現實中，Microsoft 保留以其判斷來更新分類器的權利。 雖然分類程式可協助您的組織監控這些區域，但分類程式不是要提供組織的唯一監視或定址這類語言的方法。 您的組織，而非 Microsoft，仍然負責這些區域中與掃描及封鎖語言相關的所有決策。

如需 Microsoft 365 中的分類器相關資訊，請參閱[類元](classifier-getting-started-with.md)。

### <a name="conditional-settings"></a>設定條件設定
<a name="ConditionalSettings"> </a>

您針對原則所選擇的條件，會套用到您組織中的電子郵件和協力廠商來源的通訊（如 Facebook 或 DropBox）。

下表說明每個條件的詳細資訊。
  
|**條件**|**如何使用此條件**|
|:-----|:-----|
| **內容符合任何這些分類器** | 當郵件中包含或排除任何分類器時，套用至原則。 有些分類器是在您的租使用者中預先定義的，而且自訂分類器必須分開設定，才能用於此條件。 只有一個分類器可以定義為原則中的條件。 如需設定分類程式的詳細資訊，請參閱[類元](classifier-getting-started-with.md)。 |
| **內容包含下列任何敏感資訊類型** | 當郵件中包含或排除任何敏感資訊類型時，套用至原則。 有些分類器是在您的租使用者中預先定義的，而且自訂分類器可以個別設定，也可以個別設定，也可以是條件指派過程的一部分。 您選擇的每一種機密資訊類型都是分開套用的，而且只有其中一個敏感資訊類型必須套用，原則才能套用至郵件。 如需自訂敏感資訊類型的詳細資訊，請參閱[自訂敏感資訊類型](custom-sensitive-info-types.md)。 |
| **從這些網域接收郵件**  <br><br> **不會從這些網域接收郵件** | 套用原則，以包含或排除已接收郵件中的特定網域或電子郵件地址。 輸入每個網域或電子郵件地址，並以逗點分隔多個網域或電子郵件地址。 每個輸入的功能變數名稱或電子郵件地址會分開套用，只有一個網域或電子郵件地址必須套用原則才能套用至郵件。 <br><br> 如果您想要從特定網域掃描所有電子郵件，但想要排除不需要檢查的郵件（電子報、宣告等等），您必須設定**不會從任何**包括電子郵件地址（例如 "newsletter@contoso.com"）的網域條件接收郵件。 |
| **郵件會傳送至這些網域中的任何一個**  <br><br> **郵件不會傳送至此任何網域** | 套用原則，以包含或排除已傳送郵件中的特定網域或電子郵件地址。 輸入每個網域或電子郵件地址，並以逗點分隔多個網域或電子郵件地址。 每個網域或電子郵件地址都是分開套用，只有一個網域或電子郵件地址必須套用原則才能套用至郵件。 <br><br> 如果您想要掃描傳送至特定網域的所有電子郵件，但想要排除不需要檢查的已傳送郵件，則必須設定兩個條件： <br> -將**郵件傳送至任何**定義網域（"contoso.com"）的網域條件，然後 <br> -**不會將郵件傳送至任何**包括電子郵件地址（"subscriptions@contoso.com"）的網域條件。 |
| **郵件是使用下列任一標籤分類**  <br><br> **郵件未使用下列任何一種標籤進行分類** | 在郵件中包含或排除某些保留標籤時套用原則。 保留標籤必須個別設定，且已設定的標籤會選做為此狀況的一部分。 您選擇的每一個標籤會分開套用（只有其中一個標籤必須套用，原則才能套用至郵件）。 如需設定保留標籤的詳細資訊，請參閱[保留標籤簡介](labels.md)。|
| **郵件包含下列任何文字**  <br><br> **郵件不包含任何這些字詞** | 若要在郵件中包含或排除某些字詞或片語時套用原則，請輸入每個單字或片語，並以逗號分隔。 您輸入的每個字都會分開套用（只有一個字必須套用，原則才能套用至郵件）。 如需輸入單字或片語的詳細資訊，請參閱下一節[將字詞和片語比對電子郵件或附件](communication-compliance-feature-reference.md#Matchwords)。|
| **附件包含下列任一字**  <br><br> **附件不包含任何這些字詞** | 若要在郵件附件（例如 Word 檔）中包含或排除某些字詞或片語時套用原則，請輸入每個單字或片語，並以逗號分隔。 您輸入的每個字都會分開套用（只有一個字必須套用，原則才能套用至附件）。 如需輸入單字或片語的詳細資訊，請參閱下一節[將字詞和片語比對電子郵件或附件](communication-compliance-feature-reference.md#Matchwords)。|
| **附件為下列其中一種檔案類型**  <br><br> **附件不是任何檔案類型** | 若要監督包含或排除特定類型附件的通訊，請輸入副檔名（例如 .exe 或 .pdf）。 如果您想要包含或排除多個副檔名，請在個別的行上輸入這些副檔名。 只有一個附件副檔名必須符合原則才能套用。|
| **郵件大小大於**  <br><br> **郵件大小不大於** | 若要根據特定大小來查看郵件，請使用下列條件，指定郵件在進行審閱之前可以具有的最大或最小大小。 例如，如果您指定的**郵件大小大於** \> **1.0 MB**，則所有 1.01 MB 和更大的郵件都會進行審閱。 您可以選擇此條件的位元組、kb、mb 或 gb。|
| **附件大於**  <br><br> **附件不大於** | 若要根據附件大小來查看郵件，請指定郵件之前的附件大小上限或最小值。 例如，如果您指定的**附件** \>大於**2.0 mb**，所有附件為 2.01 MB 的郵件都會進行審閱。 您可以選擇此條件的位元組、kb、mb 或 gb。|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>比對電子郵件或附件的字詞和片語
<a name="Matchwords"> </a>

您輸入的每個字和以逗號分開的每一個字都會分開套用（原則條件必須套用至電子郵件或附件，才只有一個字必須套用）。 例如，我們會使用條件，**訊息包含這些字中的任何字**，關鍵字 "銀行家" 和「內幕交易」會以逗號（銀行家，內部交易）隔開。 原則套用至所有包含 "銀行家" 或 "內幕交易" 字樣的郵件。 若要套用此原則條件，只須出現其中一個字或片語。 郵件或附件中的文字必須完全符合您所輸入的文字。

若要同時掃描相同關鍵字的電子郵件和附件，請建立[資料遺失防護原則](create-test-tune-dlp-policy.md)，其中包含您想要掃描郵件中的字詞的[自訂關鍵字字典](create-a-keyword-dictionary.md)。 此原則設定可識別出現在電子郵件**或**電子郵件附件中的已定義關鍵字。 使用標準條件式原則設定（*郵件包含*這些字和附件中的任何一個*字*）來識別郵件和附件中的字詞時，必須**同時**存在郵件和附件中的字詞。
  
#### <a name="enter-multiple-conditions"></a>輸入多個條件

如果您輸入多個條件，Microsoft 365 會同時使用所有條件，以決定何時將監察原則套用至通訊專案。 當您設定多個條件時，必須符合原則才能套用的所有條件，除非您輸入例外狀況。 例如，如果郵件包含 "商貿" 一詞，且大小超過 2 MB，您就需要套用原則。 不過，如果郵件也包含「由 Contoso 金融核准」一詞，則不應套用此原則。 在此範例中，三個條件的定義如下：
  
- **郵件包含下列任何文字**，關鍵字為 "商貿"
- **郵件大小**大於，值為 2 MB
- **郵件不包含這些字**，但關鍵字「Contoso 財務小組核准」

### <a name="review-percentage"></a>審閱百分比

如果您想要減少要檢查的內容數量，您可以指定監管原則所控制之所有通訊的百分比。 會從符合所選原則條件的總內容百分比選取即時、隨機的內容樣本。 如果您想要檢閱者審閱所有專案，您可以在通訊相容性原則中設定**100%** 。

## <a name="notices"></a>通知

如果您想要在問題解決程式的過程中傳送使用者的電子郵件提醒通知與原則相符，您可以建立通知範本。 通知只能傳送到與產生特定報警的原則相符相關聯的員工電子郵件地址。 在修復工作流程中，選取要套用到原則違規的公告範本時，您可以選擇接受範本中所定義的欄位值，或是視需要覆寫欄位。

通知範本是自訂的電子郵件範本，您可以在其中定義下列郵件欄位：

|**Field**|**Required**| **詳細資料** |
|:-----|:-----|:-----|
|**範本名稱** | 是 | 您將在修正期間于通知工作流程中選取之公告範本的易記名稱，會支援文字字元。 |
| **寄件者位址** | 是 | 一或多個使用者或群組的位址，會將郵件傳送給具有原則相符的該員工，並從 Active Directory 中為您的訂閱選取。 |
| **抄送和 BCC 位址** | 否 | 選取的使用者或群組，以取得您訂閱之 Active Directory 的原則相符的通知。 |
| **Subject** | 是 | 顯示在郵件主旨行中的資訊，支援文字字元。 |
| **郵件內文** | 是 | 出現在郵件內文中的資訊支援文字或 HTML 值。 |

### <a name="html-for-notices"></a>用於通知的 HTML

如果您想要建立超過簡單的文字式電子郵件訊息以進行通知，您可以在 [公告範本] 的 [郵件內文] 欄位中使用 HTML，建立更詳細的訊息。 下列範例會提供基本的 HTML 電子郵件通知範本的郵件內文格式：

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
<p>A recent message you've sent has generated a policy alert for the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

>[!NOTE]
>通訊相容性通知範本中的 HTML href 屬性執行目前只支援單一單引號標記，而不支援 URL 參照的雙引號。

## <a name="filters"></a>篩選

通訊相容性篩選器可讓您篩選和排序警示訊息，以加速調查和修正動作。 篩選可用於每個原則的**擱置**及**已解析**的索引標籤。 若要儲存篩選或篩選設定為已儲存的篩選器查詢，必須將一或多個值設定為篩選選取專案。 下表概述篩選詳細資料：

|**Filter**|**詳細資料**|
|:-----|:-----|
| **Date** | 組織中的使用者傳送或接收郵件的日期。 |
| **檔類別** | 以郵件類型為基礎的郵件類別（*郵件*或*附件*）。 |
| **具有附件** | 附件存在於郵件中。 |
| **專案類別** | 根據郵件類型、電子郵件、Microsoft 小組聊天、Bloonmberg 等的郵件來源。 |
| **收件者網域** | 郵件已傳送至的網域。 根據預設，此網域通常是您的 Microsoft 365 訂閱網域。 |
| **收件者** | 郵件已傳送至的使用者。 |
| **Sender** | 傳送郵件的人員。 |
| **寄件者網域** | 傳送郵件的網域。 |
| **大小** | 郵件大小（以 KB 為單位）。 |
| **主旨/職稱** | 郵件主題或聊天室。 |
| **標記** | 指派給郵件的標記，無論是*可疑*、*相容*或*不相容*。 |
| **升級至** | 加入郵件提升動作之人員的使用者名稱。 |
| **分類** | 套用至郵件的內建和自訂分類符的名稱。 某些範例包含*冒犯性語言*、*目標騷擾*、*猥褻*性、*威脅*等等。

## <a name="alert-policies"></a>警示原則

設定原則之後，系統會自動建立對應的警示原則，並針對符合原則中所定義條件的郵件產生警示。 依預設，所有原則都會在相關聯的警示原則中為介質指定嚴重性層級。 在相關聯的 Office 365 報警原則中符合匯總觸發器閾值等級之後，就會針對通訊相容性原則產生警示。

針對通訊相容性原則，依預設設定下列警示原則值：

|**警示原則觸發器**|**預設值**|
|:-----|:-----|
| 聚集 | 簡單匯總 |
| 臨界值 | 4個活動 |
| 視窗 | 60分鐘 |

>[!Note]
>針對通訊相容性原則，警示原則閾值觸發設定可支援3或以上的最小值。

您可以在 Office 365 Security & 合規性中心的 [**提醒**原則] 頁面上，變更觸發器的預設設定，以及活動的期間和警示原則中的特定使用者。

### <a name="change-the-severity-level-for-an-alert-policy"></a>變更報警原則的嚴重性等級

如果您想要變更特定通訊相容性原則的警示原則中所指派的嚴重性等級，請完成下列步驟：

1. 使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://compliance.microsoft.com](https://compliance.microsoft.com)。

2. 在 Microsoft 365 規範中心內，移至 [**原則**]。

3. 在 [**原則**] 頁面上選取 [ **office 365 警示**]，以開啟 [ **office 365 安全性 & 規範中心**] 中的 [**警示原則**] 頁面。

4. 選取您要更新之通訊相容性原則的核取方塊，然後選取 [**編輯原則**]。

5. 在 [**描述**] 索引標籤上，選取 [**嚴重性**] 下拉式清單以設定原則警示等級。

6. 選取 [**儲存**]，將新的嚴重性等級套用到原則。

7. 選取 [關閉]，**結束**[警示原則詳細資料] 頁面。

## <a name="audit"></a>審計

在某些情況下，您必須提供資訊給法規或合規性審計員，以證明員工活動和通訊的監管。 此資訊可能是與定義之組織原則相關聯的所有活動摘要，或任何隨通相容性原則變更的摘要。 通訊相容性原則具有內建的審計追蹤，可提供內部或外部審計的完整準備工作。 每個建立、編輯和刪除動作的詳細審計歷史記錄，都是由您的通訊原則所捕獲，以提供監察程式的證明。

>[!Important]
>您的組織必須啟用審核，才會記錄通訊相容性事件。 若要啟用審核，請參閱[啟用 Office 365 審核記錄](communication-compliance-configure.md#step-2-required-enable-the-office-365-audit-log)。

若要查看通訊相容性原則活動，請在任何原則的主版頁面上，選取 [**匯出檢閱活動**] 控制項。 此動作會以 .csv 格式產生包含下列資訊的審計檔案：

|**Field**|**詳細資料**|
|:-----|:-----|
| **CreationDate** | 在原則中執行活動的日期。 |
| **UserIds** | 在原則中執行活動的使用者。 |
| **Operations** | 對原則執行的作業。 |
| **AuditData** | 此欄位是所有原則活動的主要資料來源。 所有活動都會以逗號分隔符號錄製及分隔。 |

您也可以在整合的審計記錄中或使用[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) PowerShell Cmdlet 來查看審核活動。

例如，下列範例會傳回所有主管審查活動的活動（原則和規則）：

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

此範例會傳回通訊相容性原則的更新活動：

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

## <a name="ready-to-get-started"></a>準備好開始使用了嗎？

若要設定 Microsoft 365 組織的通訊相容性，請參閱[設定您的 microsoft 365 組織的通訊相容性](communication-compliance-configure.md)。
