---
title: EOP 中的郵件流程規則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: 您可以使用郵件流程規則 (傳輸規則) 識別並對透過您組織的郵件採取動作。
ms.openlocfilehash: 11bf2af56c6e85c868e2e0726736f624e196805c
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021046"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>獨立版 EOP 中的郵件流程規則 (傳輸規則)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在獨立 Exchange Online Protection (EOP 中) 沒有 Exchange Online 信箱的組織，您可以使用郵件流程 (規則（也稱為傳輸規則) ）來識別並對透過您的組織傳遞的郵件採取動作。

本主題說明郵件流程規則的元件和它們的運作方式。

如需建立、複製和管理郵件流程規則的步驟，請參閱 [管理 Exchange Online 中的郵件流程規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) (部分內容為機器翻譯)。 針對每個規則，您可以選擇強制執行規則、測試規則，或測試規則並通知寄件者。 若要深入了解測試選項，請參閱[測試郵件流程規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules)和 [Exchange Online 中的原則提示](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips) (部分內容為機器翻譯)。

如需符合郵件流程規則之郵件的摘要和詳細報告，請參閱 [Use mail protection reports，以查看有關惡意程式碼、垃圾郵件和規則](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)偵測的資料。

若要使用郵件流程規則實作特定的訊息原則，請參閱下列主題︰

- [使用郵件流程規則來檢查 Exchange Online 中的郵件附件](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [設定 Office 365 企業版中的加密](../../compliance/set-up-encryption.md)

- [Exchange Online 中的全組織郵件免責聲明、簽名、頁尾或頁首](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) (部分內容為機器翻譯)

- [使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [在 EOP 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)

- [透過 Exchange Online Protection 中的檔案附件封鎖功能來降低惡意軟體威脅](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [定義 Office 365 中加密或解密電子郵件訊息的規則](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

下列影片提供在獨立 EOP 中設定郵件流程規則的示範。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>郵件流程規則元件

郵件流程規則是由條件、例外狀況、動作和屬性所組成︰

- **條件** ：識別您要套用動作的郵件。 有些條件會檢查郵件標頭欄位 (例如 [收件者]、[寄件者] 或 [副本] 欄位)。 有些條件則會檢查郵件屬性 (例如郵件主旨、內文、附件、郵件大小或郵件分類)。 在使用大部分的條件時，您都必須指定比較運算子 (例如等於、不等於或包含) 以及要比對的值。 如果沒有條件或例外狀況，則規則會套用至所有郵件。

如需獨立 EOP 中郵件流程規則條件的詳細資訊，請參閱 [郵件流程規則條件和例外狀況 () 在 Exchange Online 中](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

- **例外狀況** ：選擇性地識別不應該套用動作的郵件。 可在條件中使用的訊息識別碼也可用於例外狀況。 例外狀況可覆寫條件並防止規則動作套用到郵件，即使郵件符合所有設定的條件也是如此。

- **動作** ：指定對於符合規則中的條件，但不符合任何例外狀況的郵件，所應採取的動作。 有許多動作可用，例如，拒絕、刪除或重新導向郵件、新增其他收件者、在郵件主旨中新增前置詞，或是將免責聲明插入郵件內文。

如需獨立 EOP 中可用之郵件流程規則動作的詳細資訊，請參閱 [mail flow rule actions In Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。

- **屬性** ：指定其他不是條件、例外狀況或動作的規則設定。 例如，何時應套用規則、是否強制執行或測試規則，以及規則作用中的時間週期。

  如需詳細資訊，請參閱本主題中的[郵件流程規則屬性](#mail-flow-rule-properties)一節。

### <a name="multiple-conditions-exceptions-and-actions"></a>多個條件、例外狀況和動作

下表顯示規則中如何處理多個條件、條件值、例外狀況和動作。

****

|元件|邏輯|註解|
|---|---|---|
|註解|AND|郵件必須符合規則中的所有條件。如果您需要符合一個條件或另一個條件，請對每一個條件使用不同的規則。例如，若要將相同的免責聲明新增至附件和內容包含特定文字的郵件，請為每一個條件建立一個規則。在 EAC 中，您可以輕易地複製規則。|
|具有多個值的一個條件|或|有些條件允許您指定多個值。郵件必須符合任何一個 (而非全部) 指定的值。例如，如果電子郵件的主旨為股票價格資訊，而 **[主旨包含任何這些字詞]** 條件設定為符合 Contoso 或 股票這些字，則此電子郵件滿足該條件，因為主旨至少包含其中一個指定的值。  |
|多個例外狀況|OR|如果郵件符合任何例外狀況，則動作不會套用到郵件。郵件不必符合所有例外狀況。|
|多個動作|AND|符合規則條件的郵件可取得規則中指定的所有動作。例如，如果選取 [在郵件主旨前面加上] 和 [新增收件者到 [密件副本] 方塊] 動作，則兩個動作都會套用至郵件。 <p> 請記住，某些動作 (例如， **[刪除郵件而不通知任何人]** 動作) 會阻止後續規則套用至郵件。其他動作 (例如 **[轉寄郵件]** ) 則不允許額外的動作。<p> 您也可以在規則上設定動作，以便在套用該規則時，不要將後續的規則套件到郵件。|
|

### <a name="mail-flow-rule-properties"></a>郵件流程規則屬性

下表說明郵件流程規則中可用的規則屬性。

****

|EAC 中的屬性名稱|PowerShell 中的參數名稱|描述|
|---|---|---|
|**優先順序**|_優先順序_|表示規則套用到郵件的順序。預設優先順序是以規則的建立時間為基礎 (較舊規則的優先順序高於較新的規則，而較高優先順序的規則會在較低優先順序的規則之前處理)。   <p> 您可以在規則清單中向上或向下移動規則，以變更 EAC 中的規則優先順序。 在 PowerShell 中，您可以設定優先順序編號 (0 是優先順序最高的) 。 <p> 例如，如果有一個規則是拒絕含有信用卡號碼的郵件，而另一個規則是需要核准，則您一定希望先執行拒絕規則，並停止套用其他規則。  |
|**Mode**|_Mode_|您可以指定是否要讓規則立即開始處理郵件，或您是否想要測試規則，而不影響郵件傳遞 (不論是否有資料遺失防護或 DLP 原則提示)。 <p> 原則提示可在 Outlook 或 網頁型 Outlook 中呈現簡短附註，以提供可能原則違規的相關資訊給正在建立郵件的人員。如需詳細資訊，請參閱 **Policy Tips** 。  <p> 如需模式的詳細資訊，請參閱 **測試郵件流程規則** (部分內容為機器翻譯)。|
|**於下列日期啟用此規則** <p> **於下列日期停用此規則**|_ActivationDate_ <p> _ExpiryDate_|指定規則的有效日期範圍。|
|已選取或未選取 [開啟] 核取方塊|新規則： _New-TransportRule_ Cmdlet 上的 **Enabled** 參數。 <p> 現有規則：使用 **Enable-TransportRule** 或 **Disable-TransportRule** Cmdlet。 <p> 此值會顯示在規則的 **State** 屬性中。|您可以建立已停用的規則，而在您準備進行測試時加以啟用。或者，您可以在不刪除規則的情況下進行停用，以保留設定。|
|**如果無法完成規則處理時便順延郵件**|_RuleErrorAction_|您可以指定如果無法完成規則處理時，應該如何處理郵件。預設會忽略此規則，但您可以選擇重新提交郵件進行處理。|
|**符合郵件中的寄件者地址**|_SenderAddressLocation_|如果此規則使用可檢查寄件者電子郵件地址的條件或例外狀況，您可以查看郵件標頭、郵件信封或這兩者的值。|
|**停止處理其他規則**|_SenderAddressLocation_|這是適用於規則的動作，但它看起來像是 EAC 中的屬性。您可以選擇在規則處理郵件之後，停止將其他規則套用至郵件。|
|**Comments**|_Comments_|您可以輸入有關規則的描述性註解。|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>郵件流程規則套用至訊息的方式

通過組織中的所有郵件都會根據組織已啟用的郵件流程規則來評估。 規則會以 EAC 中的 [ **郵件流程** 規則] 頁面上所列的連續處理 \> **Rules** ，或是根據 PowerShell 中的對應 _優先順序_ 參數值進行處理。

每個規則也提供選項可於符合規則時停止處理其他規則。對於符合多個郵件流程規則中條件的郵件而言，此設定很重要 (您想要將哪個規則套用到郵件？全部？僅只一個？）。

### <a name="differences-in-processing-based-on-message-type"></a>郵件類型引發的處理差異

通過組織的郵件有幾種類型。下表顯示郵件流程規則可處理的郵件類型。

****

|通過組織的郵件有幾種類型。下表顯示傳輸規則可處理哪些郵件類型。|郵件類型|
|---|---|
|**一般郵件** ：包含單一 RTF 格式 (RTF)、HTML 或純文字郵件內文的郵件，或包含一組多部分或替代郵件內文的郵件。|是|
|**Office 365 郵件加密** ：Office 365 中 Office 365 郵件加密所加密的郵件。 如需詳細資訊，請參閱 [Office 365 加密](https://docs.microsoft.com/microsoft-365/compliance/encryption) (部分內容為機器翻譯)。|規則永遠可以存取信封標頭，並根據可檢查這些標頭的條件來處理郵件。 <p> 如需可檢查或修改加密郵件內容的規則，您必須確認已啟用傳輸解密 (強制或選擇性；預設值是選擇性)。 如需詳細資訊，請參閱[定義 Office 365 中將電子郵件加密或解密的規則](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email) (部分內容為機器翻譯)。|
|**S/MIME 加密的郵件**|規則只可以存取信封標頭，並根據可檢查這些標頭的條件來處理郵件。 <p> 無法處理具有需要檢查郵件內容之條件的規則，或具有可以修改郵件內容之動作的規則。|
|**RMS 保護的訊息** ：已套件 Active Directory Rights Management Services(AD RMS) 或 Azure 版權管理 (RMS) 原則的郵件。|規則永遠可以存取信封標頭，並根據可檢查這些標頭的條件來處理郵件。 <p> 如需可檢查或修改 RMS 保護之郵件內容的規則，您必須確認已啟用傳輸解密 (強制或選擇性；預設值是選擇性)。|
|**明文簽章的郵件** ：已簽署但未加密的郵件。|是|
|**UM 郵件** ：由整合通訊服務建立或處理的郵件 (如語音信箱、傳真、未接來電通知)，以及使用 Microsoft Outlook 語音存取 建立或轉寄的郵件。|是|
|**匿名郵件** ：匿名寄件者所傳送的郵件。|是|
|**讀取報告** ：為了回應寄件者的索取讀信回條而產生的報告。 讀取內含 `IPM.Note*.MdnRead` 或 `IPM.Note*.MdnNotRead` 之郵件類別的報告。|是|
|

## <a name="what-else-should-i-know"></a>其他注意事項

- 在 Exchange Online Protection 中，規則的 **版本** 或 **RuleVersion** 屬性值並不重要。

- 在建立或修改郵件流程規則之後，可能需要 30 分鐘，以將新規則或更新的規則套用至訊息。

## <a name="for-more-information"></a>如需詳細資訊

[使用郵件流程規則來檢查 Exchange Online 中的郵件附件](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[Office 365 中的電子郵件加密](../../compliance/email-encryption.md)

[日誌、傳輸和收件匣規則限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
