---
title: 防網路釣魚原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 和 Office 365 的高級威脅防護 (Office 365 ATP) 中可用的反網路釣魚原則。
ms.openlocfilehash: a7db287b8a8efb5c41488529fcaa8789b2f594b5
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652714"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Microsoft 365 中的反網路釣魚原則

使用 Exchange Online 信箱、獨立 Exchange Online Protection (EOP) 組織（沒有 Exchange Online 信箱）和 Office 365 高級威脅防護 (Office 365 ATP) 組織，可在 Microsoft 365 組織中取得設定反網路釣魚保護設定的原則。

ATP 反網路釣魚原則僅可用於具有 Office 365 ATP 的組織。 例如：

- Microsoft 365 企業版 E5、Microsoft 365 教育版 A5 等等。
- [Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 商務版](https://www.microsoft.com/microsoft-365/business)
- [Office 365 ATP 做為附加元件](https://products.office.com/exchange/advance-threat-protection)

所有其他組織皆具有反網路釣魚原則。

下表說明反網路釣魚原則與 ATP 反網路釣魚原則之間的高層級差異：

****

|功能|防網路釣魚原則|ATP 反網路釣魚原則|
|---|:---:|:---:|
|自動建立的預設原則|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|建立自訂原則|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|原則設定<sup>\*</sup>|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|類比設定||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|欺騙設定|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|高級網路釣魚臨界值||![核取記號](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup>在 [預設原則] 中，[原則名稱] 和 [描述] 是唯讀的 (描述是空白的) ，而且您不能指定原則套用至所有收件者) 的 (。

若要設定反網路釣魚原則，請參閱下列主題：

- [在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)

- [在 Microsoft 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)

本主題的其餘部分將說明反網路釣魚原則和 ATP 反網路釣魚原則中可用的設定。

## <a name="spoof-settings"></a>欺騙設定

哄騙是指電子郵件中的寄件者位址 (電子郵件客戶程式中所顯示的寄件者位址) 不會符合電子郵件來源的網域。 如需有關欺騙的詳細資訊，請參閱[Microsoft 365 中的反欺騙保護](anti-spoofing-protection.md)。

下列欺騙設定可在反網路釣魚原則和 ATP 反網路釣魚原則中使用：

- **反欺騙保護**：啟用或停用反欺詐防護。 建議您讓它保留啟用狀態。 您可以使用**哄騙智慧原則**來允許或封鎖特定的欺騙內部和外部寄件者。 如需詳細資訊，請參閱[在 Microsoft 365 中設定詐騙情報](learn-about-spoof-intelligence.md)。

  > [!NOTE]
  > 預設會在 EOP 的預設反網路釣魚原則、預設的 ATP 反網路釣魚原則，以及您建立的新自訂反網路釣魚原則或 ATP 反網路釣魚原則中啟用欺騙設定。 <br/><br/> 如果您的 MX 記錄未指向 Microsoft 365，您就不需要停用反欺騙保護;請改為啟用連接器的增強篩選。 如需相關指示，請參閱[在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

  針對來自封鎖欺騙寄件者的郵件，您也可以指定要對郵件採取的動作：

  - **將郵件移至 [垃圾郵件] 資料夾**：此為預設值。 郵件會傳遞至信箱，並移至 [垃圾郵件] 資料夾。 在 Exchange Online 中，郵件會移至 [垃圾郵件] 資料夾，如果信箱上已啟用垃圾郵件規則 (預設會啟用該信箱) 。 如需詳細資訊，請參閱[在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

  - **隔離郵件**：將郵件傳送至隔離區，而不是預定的收件者。 如需隔離的相關資訊，請參閱下列主題：

    - [Microsoft 365 中的隔離](quarantine-email-messages.md)
    - [在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案](manage-quarantined-messages-and-files.md)
    - [以 Microsoft 365 中的使用者身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)

- **未經驗證的寄件者**：啟用或停用 Outlook 中不明的寄件者識別。 特別是：

  - 當郵件未通過 SPF 或 DKIM 檢查 **，且**郵件未通過 DMARC 或[複合驗證](email-validation-and-authentication.md#composite-authentication)時，就會在寄件者的相片中加入一個問號 (？ ) 。

  - 如果 [寄件者] 位址中的網域 (電子郵件) 客戶程式中顯示的郵件寄件者不同于 DKIM 簽章中的網域或**郵件**的 [寄件者] 位址中的網域，則會新增 via 標籤<u> (chris@contoso.com 透過</u>michelle@fabrikam.com) 。 如需這些位址的詳細資訊，請參閱[電子郵件標準的概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

  若要防止這些識別碼新增至特定寄件者的郵件，您可以使用下列選項：

  - 允許寄件者在欺騙智慧原則中哄騙。 如需相關指示，請參閱[Configure 哄騙情報 In Microsoft 365](learn-about-spoof-intelligence.md)。

  - 設定寄件者網域的[電子郵件驗證](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own)。
  
    - 針對寄件者相片中的問號，SPF 或 DKIM 最為重要。
    - 在 [via] 標籤上，確認 DKIM 簽章中的網域，或 [**郵件發件**人位址相符 (] 或 [寄件者] 位址中) 網域的子域。

  如需詳細資訊，請參閱[在 Outlook.com 中識別可疑郵件和網頁上的 Outlook](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>ATP 反網路釣魚原則中的獨佔設定

本節說明只可用於 ATP 反網路釣魚原則中的原則設定。

> [!NOTE]
> 根據預設，不會設定或開啟 ATP 獨佔設定，即使在預設原則中也是一樣。 若要利用這些功能，您必須在預設的 ATP 反網路釣魚原則中啟用和設定這些功能，或建立及設定自訂 ATP 反網路釣魚原則。

### <a name="policy-settings-in-atp-anti-phishing-policies"></a>ATP 反網路釣魚原則中的原則設定

下列原則設定僅適用于 ATP 反網路釣魚原則中：

- **名稱**：您無法重新命名預設的反網路釣魚原則，但您可以命名和重新命名您建立的自訂原則。

- **描述**您無法將描述新增至預設的反網路釣魚原則，但您可以新增及變更所建立之自訂原則的描述。

- **適用于**：識別 ATP 反網路釣魚原則適用的內部收件者。 此值是自訂原則中的必要條件，在預設原則中不可使用 (預設原則會套用至所有收件者) 。

    您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。 相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。 不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。

  - **收件**者：一或多個信箱、郵件使用者或您組織中的郵件連絡人。
  - **收件者隸屬**于組織中的一或多個群組。
  - **收件者網域是**： Microsoft 365 中的一或多個已設定公認的網域。

  - 例外狀況**除外**：規則的例外狀況。 設定和行為完全像是條件：

    - **收件者為**
    - **收件者是的成員**
    - **收件者網域是**

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>ATP 反網路釣魚原則中的類比設定

模仿是指寄件者或寄件者的電子郵件網域與實際寄件者或網域類似的位置：

- 網域 contoso.com 的模仿範例是ćóntoso.com。

- 使用者 michelle@contoso.com 的模仿範例是 michele@contoso.com。

另一個模擬的網域可能會被視為合法 (已註冊的網域、設定的電子郵件驗證記錄等等 ) ，但其目的是欺騙收件者。

下列模擬設定僅適用于 ATP 反網路釣魚原則中：

- **要保護的使用者**：防止指定的內部或外部使用者進行類比。 例如，主管 (內部) 和董事會成員 (外部) 。 您最多可以新增60的內部和外部地址。 此受保護的使用者清單與套用**至**設定之原則的收件者清單不同。

  例如，您在套用至名為「主管」群組的原則中，將 Felipe Apodaca (felipea@contoso.com) 指定為受保護的使用者。 傳送給主管群組成員的輸入郵件，其中 Felipe Apodaca 是類比的，原則 (您為類比使用者設定的動作) 。

- **要保護的網域**：防止類比指定的網域。 例如，您擁有的所有網域 ([公認的網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 或特定網域 (您擁有的網域或夥伴網域) 。 受保護網域的清單與套用**至**設定之原則所套用的網域清單不同。

  例如，您在套用至群組成員的群組成員的原則中，將 tailspintoys.com 指定為受保護的網域。 傳送給主管群組成員的輸入郵件會由原則 (，讓原則您為類比網域設定的動作) 。

- **受保護的使用者或網域的動作**：選擇要針對輸入郵件採取的動作，該郵件包含對原則中受保護的使用者與受保護的網域的模仿嘗試。 您可以指定不同的使用者模擬，以類比受保護的使用者與模擬受保護的網域：

  - **不要套用任何動作**

  - 將**郵件重新導向至其他電子郵件地址**：將郵件傳送給指定的收件者，而不是預定的收件者。

  - **將郵件移至 [垃圾郵件] 資料夾**：郵件會傳遞至信箱，並移至 [垃圾郵件] 資料夾。 在 Exchange Online 中，郵件會移至 [垃圾郵件] 資料夾，如果信箱上已啟用垃圾郵件規則 (預設會啟用該信箱) 。 如需詳細資訊，請參閱[在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

    - **隔離郵件**：將郵件傳送至隔離區，而不是預定的收件者。 如需隔離的相關資訊，請參閱下列主題：

    - [Microsoft 365 中的隔離](quarantine-email-messages.md)
    - [在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案](manage-quarantined-messages-and-files.md)
    - [以 Microsoft 365 中的使用者身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)

  - **傳遞郵件並將其他位址新增至 Bcc 行**：將郵件傳遞給預定的收件者，並以無訊息方式將郵件傳遞給指定的收件者。

  - **傳遞郵件之前將其刪除**：無訊息地刪除整個郵件，包括所有附件。

- **安全性秘訣**：啟用或停用下列會顯示失敗之模擬檢查的模仿安全性秘訣：

  - **類比使用者**：寄件者位址包含受保護的使用者。
  - **類比網域**：寄件者位址包含受保護的網域。
  - 不**尋常的字元**： From 位址包含不尋常的字元集 (例如數學符號和文字，或是混合的大小寫字母) 在受保護的寄件者或網域中。

- **信箱智慧**：啟用或停用使用者的智慧 (AI) ，可決定使用者的電子郵件模式與經常的連絡人。 此設定可協助 AI 區分合法和欺騙的電子郵件與這些連絡人。 信箱智慧只適用于 Exchange Online 信箱。

- **信箱智慧**型模擬保護：根據每個使用者的個人寄件者地圖，啟用或停用增強型類比結果。 這種智慧可讓 Microsoft 365 自訂使用者模擬偵測，並更好地處理誤報。 偵測到使用者模擬時，您可以定義要對郵件採取的特定動作：

  - **不要套用任何動作**
  - **將郵件重新導向至其他電子郵件地址**
  - **將郵件移至 [垃圾郵件] 資料夾**
  - **隔離郵件**
  - **傳遞郵件並將其他位址新增至 Bcc 行**
  - **在傳遞郵件之前將其刪除**

- **受信任的寄件者和網域**：模仿保護設定的例外狀況。 來自指定寄件者和寄件者網域的郵件，永遠不會分類為以模仿為模擬的受原則攻擊。 換句話說，受保護寄件者、受保護的網域或信箱智慧保護的動作不會套用到這些受信任的寄件者或寄件者網域。 這兩個清單的上限大約是1000個專案。

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a>ATP 反網路釣魚原則中的高級網路釣魚臨界值

下列高級網路釣魚臨界值僅可用於 ATP 反網路釣魚原則，以控制將機器學習模型套用至郵件以判定網路釣魚是否判定的敏感程度：

- **1-Standard**：此為預設值。 針對郵件採取的動作嚴重性，取決於郵件為網路釣魚 (低、中、高或非常高的信賴度) 的置信度。 例如，以非常高的信賴程度識別為網路釣魚的郵件會套用最嚴重的動作，而識別為低信任程度之網路釣魚的郵件，則會套用較低的嚴重動作。

- **2-嚴格**：識別為具有高可信度之網路釣魚的郵件，就像是以非常高的信賴程度加以識別一樣加以對待。

- **3-更嚴格**：辨識為具有中等或高置信度之網路釣魚的郵件，視為以極高的信賴程度加以識別。

- **4-最主動**：以低、中或高置信度識別為網路釣魚的郵件，視為以極高的置信度識別。

誤報的機率 (，標記為壞) 會隨著您增加此設定而增加。 如需建議設定的詳細資訊，請參閱[OFFICE ATP 反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)。
