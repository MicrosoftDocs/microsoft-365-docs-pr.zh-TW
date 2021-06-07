---
title: 防網路釣魚原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中可用的反網路釣魚原則。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 205fd5cd40d187eada4f6b87edf64c0d35f7e3b3
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788412"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Microsoft 365 中的反網路釣魚原則

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

使用 Exchange Online 信箱、獨立 Exchange Online Protection (EOP) 組織但不 Exchange Online 信箱的組織，以及 Office 365 組織的 Microsoft Defender，可在 Microsoft 365 組織中使用設定反網路釣魚防護設定的原則。

只有具有 Office 365 Defender 的組織才能使用 Microsoft defender for Office 365 中的反網路釣魚原則。 例如：

- Microsoft 365 企業版E5、Microsoft 365 教育版 A5 等等。
- [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 商務版](https://www.microsoft.com/microsoft-365/business)
- [以附加元件 Office 365 的 Microsoft Defender （適用于）](https://products.office.com/exchange/advance-threat-protection)

下表說明 EOP 中 Microsoft Defender for Office 365 中的反網路釣魚原則與反網路釣魚原則之間的高層次差異：

****

|功能|EOP 中的反網路釣魚原則|Microsoft Defender 中 Office 365 的反網路釣魚原則|
|---|:---:|:---:|
|自動建立的預設原則|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
|建立自訂原則|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
|原則設定<sup>\*</sup>|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
|類比設定||![核取記號](../../media/checkmark.png)|
|欺騙設定|![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
|高級網路釣魚臨界值||![核取記號](../../media/checkmark.png)|
|

<sup>\*</sup> 在 [預設原則] 中，[原則名稱] 和 [描述] 是唯讀的 (描述是空白的) ，而且您不能指定原則套用至所有收件者) 的 (。

若要設定反網路釣魚原則，請參閱下列文章：

- [在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)

- [在 Microsoft Defender 中設定 Office 365 的反網路釣魚原則](configure-atp-anti-phishing-policies.md)

本文的其餘部分將說明 EOP 和 Defender for Office 365 中的反網路釣魚原則中可用的設定。

## <a name="policy-settings"></a>原則設定

下列原則設定可用於 EOP 和 Microsoft Defender for Office 365 中的反網路釣魚原則：

- **名稱**：您無法重新命名預設的反網路釣魚原則。 在您建立自訂的反網路釣魚原則之後，就無法在安全性 & 規範中心內重新命名原則。

- **描述** 您無法將描述新增至預設的反網路釣魚原則，但您可以新增及變更所建立之自訂原則的描述。

- **適用于**：識別反網路釣魚原則套用的內部收件者。 此值是自訂原則中的必要條件，在預設原則中不可使用 (預設原則會套用至所有收件者) 。

  您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。 相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。 不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。

  - **收件** 者：一或多個信箱、郵件使用者或您組織中的郵件連絡人。
  - **收件者隸屬** 于組織中的一或多個群組。
  - **收件者網域是**： Microsoft 365 中的一或多個已設定公認的網域。

  - 例外狀況 **除外**：規則的例外狀況。 設定和行為完全像是條件：

    - **收件者為**
    - **收件者是的成員**
    - **收件者網域是**

  > [!NOTE]
  > 在自訂的反網路釣魚原則中，需要套用 **to** 設定來識別 <u>原則所套用</u>**的郵件收** 件者。 Microsoft Defender for Office 365 中的反網路釣魚原則也有[類比設定](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)，您可以在其中指定個別寄件者的電子郵件地址或寄件者網域，以供本文稍後所述<u>接收模擬保護</u>。

## <a name="spoof-settings"></a>欺騙設定

哄騙是指電子郵件中的寄件者位址 (電子郵件客戶程式中顯示的寄件者位址) 不符合電子郵件來源的網域。 如需有關欺騙的詳細資訊，請參閱[Microsoft 365 中的反欺騙防護](anti-spoofing-protection.md)。

下列欺騙設定可用於 EOP 和 Microsoft Defender for Office 365 中的反網路釣魚原則：

- **啟用欺騙情報？**：開啟或關閉欺騙智慧。 建議您讓它保持開啟狀態。

  啟用欺騙智慧功能時，欺騙性的 **智慧洞察力** 會顯示欺騙性寄件者，該寄件者會自動偵測到並允許或封鎖欺騙情報。 您可以手動覆寫欺騙性智慧結論，以允許或封鎖偵測中偵測到的欺騙寄件者。 但是當您這樣做時，欺騙的寄件者會從欺詐智慧洞察力中消失，而且現在只會在 [租使用者允許/封鎖] 清單的 [ **哄騙** ] 索引標籤上顯示。 您也可以在承租人允許/封鎖清單中為欺騙寄件者手動建立允許或封鎖專案。 如需詳細資訊，請參閱下列主題：

  - [EOP 中的欺騙智慧洞察力](learn-about-spoof-intelligence.md)
  - [在 EOP 中管理承租人允許/封鎖清單](tenant-allow-block-list.md)

  > [!NOTE]
  >
  > - 預設的反網路釣魚原則和您建立的任何新自訂反網路釣魚原則中，預設會啟用反欺騙保護。
  >
  > - 如果您的 MX 記錄未指向 Microsoft 365，您不需要停用反欺騙保護;請改為啟用連接器的增強篩選。 如需相關指示，請參閱[強化篩選的 Exchange Online 中的連接器](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。
  >
  > - 停用反欺騙保護只會停用 [複合驗證](email-validation-and-authentication.md#composite-authentication) 檢查的隱含欺騙保護。 如果寄件者失敗明確的 [DMARC](use-dmarc-to-validate-email.md) 檢查（原則設定為 [隔離] 或 [拒絕]），則郵件仍會被隔離或拒絕。

- **未經驗證的寄件者設定**：請參閱下一節中的資訊。

- **動作**：針對封鎖的欺騙寄件者的郵件 (會在租使用者允許/封鎖清單) 中自動封鎖，您也可以指定要對郵件採取的動作：

  - **將郵件移至收件者的 [垃圾郵件] 資料夾**：此為預設值。 郵件會傳遞至信箱，並移至 [垃圾郵件] 資料夾。 在 Exchange Online 中，郵件會移至 [垃圾郵件] 資料夾，如果信箱上已啟用垃圾郵件規則 (預設會啟用) 。 如需詳細資訊，請參閱在[Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

  - **隔離郵件**：將郵件傳送至隔離區，而不是預定的收件者。 如需隔離的相關資訊，請參閱下列文章：

    - [Microsoft 365 中的隔離](quarantine-email-messages.md)
    - [在 Microsoft 365 中管理被隔離的郵件和檔案成為系統管理員](manage-quarantined-messages-and-files.md)
    - [以 Microsoft 365 中的使用者身分找到和發行被隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)

### <a name="unauthenticated-sender"></a>未驗證寄件者

未經驗證的寄件者設定是 EOP 和 Microsoft Defender for Office 365 中的反網路釣魚原則中可用的[欺騙設定](#spoof-settings)的一部分，如前一節所述。

- **啟用未經驗證的寄件者問號 (？ ) 符號？**：當此設定開啟時，如果郵件未通過 SPF 或 DKIM 檢查， **且** 郵件未透過 DMARC 或 [複合驗證](email-validation-and-authentication.md#composite-authentication)，則會在寄件者的相片中新增一個問號。 關閉此設定時，不會將問號新增到寄件者的相片。

- **啟用**「透過」標籤？ <sup>\*</sup> ：當此設定開啟時，如果寄件者位址 <u></u>中的網域 (電子郵件) 客戶程式中顯示的郵件寄件者不同于 DKIM 簽章中的網域或 **郵件的** 寄件者位址中的網域，則會在 [寄件者] 方塊中新增 [via] 標記 (chris@contoso.com 透過 fabrikam.com) 。 如需這些位址的詳細資訊，請參閱 [電子郵件標準的概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

> [!NOTE]
> 目前，「透過」標籤 **？** 設定無法在所有組織中使用。 如果您沒有 **enable "via" 標記？** 設定，問號 **和** via 標籤都是由您組織中的 [ **啟用未經驗證的寄件者問號 (？ ) 符號？** ] 設定所控制。

若要防止問號或 via 標記新增至特定寄件者的郵件，您可以使用下列選項：

- 在 [[租使用者允許/封鎖] 清單](tenant-allow-block-list.md)中，允許哄騙寄件者在[欺騙性智慧洞察力](learn-about-spoof-intelligence.md)或手動。 當停用未經驗證的寄件者識別時，允許欺騙的寄件者會防止從寄件者的郵件中顯示透過標記。

- 設定寄件者網域的[電子郵件驗證](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own)。
  - 針對寄件者相片中的問號，SPF 或 DKIM 最為重要。
  - 在 [via] 標籤上，確認 DKIM 簽章中的網域，或 [ **郵件發件** 人位址相符 (] 或 [寄件者] 位址中) 網域的子域。

如需詳細資訊，請參閱[識別可疑郵件中的 Outlook .com 和 Outlook 網頁](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender 中 Office 365 的反網路釣魚原則中的獨佔設定

本節說明僅可用於 Office 365 的 Microsoft Defender 中的反網路釣魚原則中的原則設定。

> [!NOTE]
> Office 365 的 Microsoft Defender 中的預設反網路釣魚原則為所有收件者提供[欺騙保護](set-up-anti-phishing-policies.md#spoof-settings)和信箱智慧。 不過，預設原則中並未設定或啟用其他可用的模擬 [保護](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 功能和 [高級設定](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 。 若要啟用所有保護功能，請修改預設的反網路釣魚原則，或建立其他的反網路釣魚原則。

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender 中 Office 365 的反網路釣魚原則中的模擬設定

模仿是指寄件者或寄件者的電子郵件網域與實際寄件者或網域類似的位置：

- contoso.com 這個網域的網域模擬例子是 ćóntoso.com。
- 使用者 michelle@contoso.com 的模擬例子是 michele@contoso.com。

另外，模擬網域可能被視為合法 (註冊網域、設定的電子郵件驗證記錄等)，惟其目的是欺騙收件者。

下列模擬設定僅適用于 Microsoft Defender 的 Office 365 中的反網路釣魚原則：

- **新增要保護的使用者**：防止將指定的內部或外部電子郵件地址類比 **為郵件寄件者**。 例如，您會收到來自公司副總裁的電子郵件訊息，要求您傳送給她的部分內部公司資訊。 您會這麼做嗎？ 許多人員會在不想要的情況下傳送回復。

  您可以使用受保護的使用者加入內部和外部寄件者電子郵件地址，以防止模擬。 從使用者模擬中保護的 **寄件者** 清單，與原則所 **套用的收** 件者清單不同， (預設原則的所有收件者;在 [[原則設定](#policy-settings)] 區段的 [套用 **至**] 設定中設定的特定收件者) 。

  > [!NOTE]
  >
  > - 在每個反網路釣魚原則中，您可以指定最多60個受保護的使用者 (寄件者的電子郵件地址) 。 您無法在多個原則中指定同一個受保護的使用者。 因此，不論對收件者套用多少個原則，各位收件者的受保護的使用者數目 () 每個個別的收件者的郵寄地址上限為60。 如需原則優先順序的詳細資訊，以及在套用第一個原則之後，如何處理原則，請參閱 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。
  >
  > - 如果寄件者和收件者先前透過電子郵件進行通訊，使用者模擬保護便無法運作。 如果寄件者和收件者永不透過電子郵件進行通訊，郵件會被識別為類比嘗試。

  根據預設，不會將寄件者電子郵件地址設定為 **要保護的使用者** 類比保護。 因此，根據預設，在 [預設原則] 或 [自訂原則] 中，模擬保護不會涵蓋任何寄件者電子郵件地址。

  當您將內部或外部電子郵件地址新增至 **要保護的使用者** 清單時，來自這些 **寄件者** 的郵件會受到模仿保護檢查的制約。 **如果** 郵件傳送給收件者的郵件是套用至預設原則的所有 **收件** 者，則會檢查郵件，以進行模擬 (;**適用于** 自訂原則) 中的收件者。 如果在寄件者的電子郵件地址中偵測到模擬，使用者的類比保護動作會套用至郵件 (如何處理該郵件、是否顯示類比的使用者安全提示等等 ) 。

- **新增網域以加以保護**：防止 **在郵件寄件者的網域中** 類比指定的網域。 例如，您擁有的所有網域 ([公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 或特定網域 (您擁有的網域或夥伴網域) 。 保護自模擬的 **寄件者網域** 清單不同于原則所 **套用的收** 件者清單，以 (預設原則的所有收件者;在 [[原則設定](#policy-settings)] 區段的 [套用 **至**] 設定中設定的特定收件者) 。

  > [!NOTE]
  > 您可以在所有反網路釣魚原則中定義的受保護網域數目上限為50。

  根據預設，不會將寄件者網域設定為 **要保護的網域** 中的類比保護。 因此，根據預設，在 [預設原則] 或 [自訂原則] 中，模擬保護不會涵蓋任何寄件者網域。

  當您將網域新增至 **要保護的網域** 清單時，來自 **這些網域中寄件者** 的郵件會受到模擬保護檢查的制約。 **如果** 郵件傳送給收件者的郵件是套用至預設原則的所有 **收件** 者，則會檢查郵件，以進行模擬 (;**適用于** 自訂原則) 中的收件者。 如果在寄件者的網域中偵測到模擬，就會將網域的模仿保護動作套用至郵件 (應如何處理該郵件、是否顯示類比的使用者安全提示等等 ) 。

- **動作**：選擇要對輸入郵件採取的動作，該郵件包含對原則中受保護的使用者與受保護的網域的模仿嘗試。 您可以指定不同的使用者模擬，以類比受保護的使用者與模擬受保護的網域：

  - **不要套用任何動作**

  - 將 **郵件重新導向至其他電子郵件地址**：將郵件傳送給指定的收件者，而不是預定的收件者。

  - **將郵件移至收件者的 [垃圾郵件] 資料夾**：郵件會傳遞至信箱，並移至 [垃圾郵件] 資料夾。 在 Exchange Online 中，郵件會移至 [垃圾郵件] 資料夾，如果信箱上已啟用垃圾郵件規則 (預設會啟用) 。 如需詳細資訊，請參閱在[Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

  - **隔離郵件**：將郵件傳送至隔離區，而不是預定的收件者。 如需隔離的相關資訊，請參閱下列文章：
    - [Microsoft 365 中的隔離](quarantine-email-messages.md)
    - [在 Microsoft 365 中管理被隔離的郵件和檔案成為系統管理員](manage-quarantined-messages-and-files.md)
    - [以 Microsoft 365 中的使用者身分找到和發行被隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)

  - **傳遞郵件並將其他位址新增至 Bcc 行**：將郵件傳遞給預定的收件者，並以無訊息方式將郵件傳遞給指定的收件者。

  - **傳遞郵件之前將其刪除**：無訊息地刪除整個郵件，包括所有附件。

- **開啟模擬安全性秘訣**：開啟或關閉下列會顯示失敗模擬檢查之訊息的模擬安全性秘訣：
  - **顯示類比使用者的提示**：寄件者的位址包含受保護的使用者。
  - **顯示類比網域的秘訣**：寄件者位址包含受保護的網域。
  - **顯示不尋常字元的秘訣**：寄件者位址包含不尋常的字元集，例如數學符號和文字，或是混合的大小寫字母) 在受保護的寄件者或網域中 (。

  > [!IMPORTANT]
  >
  > 即使已關閉模擬安全性秘訣，**我們還是建議您使用** 郵件流程規則 (也稱為傳輸規則) 新增名為 **X-MS-Exchange-EnableFirstContactSafetyTip** 的郵件頭，並 **啟用** 對郵件的值。 安全提示會在第一次從寄件者收到郵件時通知收件者，或是不經常從寄件者取得郵件。 這項功能會針對潛在的模仿攻擊，新增額外的安全性防護層。
  >
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="具有多個收件者之類比保護的安全提示文字。":::

- **信箱智慧**：啟用或停用使用者的智慧 (AI) ，可決定使用者的電子郵件模式與經常的連絡人。 此設定可協助 AI 辨別來自合法和模擬寄件者的郵件。

  例如，Gabriela Laureano (glaureano@contoso.com) 是您公司的 CEO，所以您可以將其新增為使用者的受保護寄件者， **以保護** 原則的設定。 不過，原則所套用的某些收件者會定期與另一個名為 Gabriela Laureano 的廠商進行通訊，)  (glaureano@fabrikam.com。 因為這些收件者有 glaureano@fabrikam.com 的通訊歷程記錄，所以信箱智慧不會將 glaureano@fabrikam.com 的郵件識別為對這些收件者進行 glaureano@contoso.com 的模仿嘗試。

  若要使用由信箱智慧所學到的常用連絡人 (，但缺乏其) 來協助保護使用者免受模擬攻擊，您可以開啟 **信箱智慧類比防護**，並指定當您也開啟 **信箱智慧****時** 所要採取的動作。

- **信箱智慧型類比保護**：開啟此設定可指定要對郵件進行類比偵測時從信箱智慧結果採取的動作：

  - **請勿套用任何動作**：請注意，此值的結果與開啟 **信箱智慧** ，但是關閉 **信箱智慧型類比保護** 的結果相同。
  - **將郵件重新導向至其他電子郵件地址**
  - **將郵件移至收件者的 [垃圾郵件] 資料夾**
  - **隔離郵件**
  - **傳遞郵件並將其他位址新增至 Bcc 行**
  - **在傳遞郵件之前將其刪除**

- **新增信任的寄件者和網域**：模仿保護設定的例外狀況。 來自指定寄件者和寄件者網域的郵件，永遠不會分類為以模仿為模擬的受原則攻擊。 換句話說，受保護寄件者、受保護的網域或信箱智慧保護的動作不會套用到這些受信任的寄件者或寄件者網域。 這兩個清單的上限大約是1000個專案。

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender 中 Office 365 的反網路釣魚原則中的高級網路釣魚臨界值

下列高級網路釣魚臨界值僅可用於 Office 365 的 Microsoft Defender 中的反網路釣魚原則。 這些臨界值可控制將機器學習模型套用至郵件以判定網路釣魚是否判定的靈敏度：

- **1-Standard**：此為預設值。 針對郵件採取的動作嚴重性，取決於郵件為網路釣魚 (低、中、高或非常高的信賴度) 的置信度。 例如，以非常高的信賴程度識別為網路釣魚的郵件會套用最嚴重的動作，而識別為低信任程度之網路釣魚的郵件，則會套用較低的嚴重動作。

- **2-嚴格**：識別為具有高可信度之網路釣魚的郵件，就像是以非常高的信賴程度加以識別一樣加以對待。

- **3-更嚴格**：辨識為具有中等或高置信度之網路釣魚的郵件，視為以極高的信賴程度加以識別。

- **4-最主動**：以低、中或高置信度識別為網路釣魚的郵件，視為以極高的置信度識別。

誤報的機率 (，標記為壞) 會隨著您增加此設定而增加。 如需建議設定的詳細資訊，請參閱[Microsoft Defender 中的反網路釣魚原則，以取得 Office 365 設定](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。
