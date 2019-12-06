---
title: 使用郵件流程規則來設定 Exchange Online Protection 中篩選大量電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 系統管理員可以了解如何使用 Exchange Online Protection 中的郵件流程規則的大量電子郵件篩選。
ms.openlocfilehash: 4f53ee482567a3c76acb4ee8ca0ffb10f6f8cca0
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866745"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>使用郵件流程規則來設定 Exchange Online Protection 中篩選大量電子郵件

您可以設定全公司內容篩選的垃圾郵件和大量電子郵件使用的預設垃圾郵件內容篩選器原則。 請參閱[設定垃圾郵件篩選器原則](configure-your-spam-filter-policies.md)and [Set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)有關如何設定內容篩選原則。

如果您想要更多選項] 來篩選大量郵件，您可以建立要搜尋的文字模式或經常大量電子郵件中找到的片語的郵件流程規則 （也稱為傳輸規則）。 任何包含這些特性的郵件會被標示為垃圾郵件。 使用這些規則有助於減少貴組織接收到的不想要的大量電子郵件數量。

> [!IMPORTANT]
> 建立郵件流程規則記載本主題之前，建議您先閱讀[垃圾郵件和大量電子郵件之間的差異為何？](what-s-the-difference-between-junk-email-and-bulk-email.md)和[大量抱怨層級的值](bulk-complaint-level-values.md)。<br>
> 下列程序會針對您整個組織將郵件標記為垃圾郵件。 不過，您可以新增另一項條件，只將這些規則套用至貴組織中的特定收件者。 如此一來，積極的大量電子郵件篩選設定可以套用至高目標的幾個使用者在您的使用者 （大部分取得他們註冊的帶正負號的大量電子郵件） 的其餘部分時不會受到影響。

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>建立郵件流程規則，以篩選大量電子郵件根據文字模式

1. 在 Exchange 系統管理中心 (EAC) 中，移至 [郵件流程]**** \> [規則]****。

2. 按一下 [**新增**![加入圖示](../media/ITPro-EAC-AddIcon.gif)]，然後選取 [**建立新的規則**。

3. 指定規則的名稱。

4. 按一下 [**更多選項**![更多選項圖示](../media/ITPro-EAC-MoreOptionsIcon.png)。 在**套用此規則情況**] 下選取 [**主旨或本文** \> **主旨或內文符合這些文字模式**。

5. 在 [**指定單字或片語**] 對話方塊中，新增下列規則運算式通常位於大量電子郵件，一次，然後完成後，按一下 [**確定]** :

   - `If you are unable to view the content of this email\, please`

   - `\>(safe )?unsubscribe( here)?\</a\>`

   - `If you do not wish to receive further communications like this\, please`

   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

   - `To stop receiving these+emails\:http\://`

   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

   - `no longer (wish )?(to )?(be sent|receive) w+ email`

   - `If you are unable to view the content of this email\, please click here`

   - `To ensure you receive (your daily deals|our e-?mails)\, add`

   - `If you no longer wish to receive these emails`

   - `to change your (subscription preferences|preferences or unsubscribe)`

   - `click (here to|the) unsubscribe`

   上面的清單並未常見於大量電子郵件; 中的規則運算式可以新增或移除視需要更多。 不過，它是不錯的起點。

   在主旨或郵件的其他標頭欄位中搜尋字詞或文字模式，會發生在郵件已從 MIME 內容傳輸編碼方法進行解碼*之後*，該編碼方法用來在 SMTP 伺服器之間傳送 ASCII 文字二進位訊息。您無法使用條件或例外狀況來搜尋主旨或郵件中其他標頭欄位的原始 (通常是 Base64) 編碼值。

6. 在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。

7. 在 **[指定 SCL]** 對話方塊中，將 SCL 設定為 **5**、**6** 或 **9**，然後按一下 **[確定]**。

   將 SCL 設為 5 或 6 會採取 **[垃圾郵件]** 動作，將 SCL 設為 9 會採取 **[高信賴度的垃圾郵件]** 動作 (在內容篩選原則中設定)。 服務將執行內容篩選原則中所設定的動作。 預設動作是要將郵件傳遞至收件者的垃圾郵件] 資料夾，但是可以設定不同的動作，如所述[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。

   如果您設定的動作是要隔離郵件，而不是將它傳送給收件者的垃圾郵件] 資料夾，就會傳送訊息至管理員隔離區為郵件流程規則比對，且已將無法使用使用者垃圾郵件隔離區中或透過使用者垃圾郵件通知。

   如需服務中各 SCL 值的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。

8. 儲存規則。

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>建立郵件流程規則，以篩選器片語為基礎的大量電子郵件

1. 在 EAC 中，移至 [郵件流程]**** \> [規則]****。

2. 按一下 [**新增**![加入圖示](../media/ITPro-EAC-AddIcon.gif)]，然後選取 [**建立新的規則**。

3. 指定規則的名稱。

4. 按一下 [更多選項]****。 在**套用此規則情況**] 下選取 [**主旨或本文** \> **主旨或內文包含任何這些字詞**。

5. 在 [**指定單字或片語**] 對話方塊中，新增下列常見於大量電子郵件，一次中然後當您完成時按一下 [**確定]** :

   - `to change your preferences or unsubscribe`

   - `Modify email preferences or unsubscribe`

   - `This is a promotional email`

   - `You are receiving this email because you requested a subscription`

   - `click here to unsubscribe`

   - `You have received this email because you are subscribed`

   - `If you no longer wish to receive our email newsletter`

   - `to unsubscribe from this newsletter`

   - `If you have trouble viewing this email`

   - `This is an advertisement`

   - `you would like to unsubscribe or change your`

   - `view this email as a webpage`

   - `You are receiving this email because you are subscribed`

   這份清單並非常見於大量電子郵件; 中的片語可以新增或移除視需要更多。 不過，它是不錯的起點。

6. 在 [**執行下列動作**，選取 [**修改訊息屬性** \> **設定垃圾郵件信賴等級 (SCL)**。

7. 在 **[指定 SCL]** 對話方塊中，將 SCL 設定為 **5**、**6** 或 **9**，然後按一下 **[確定]**。

   將 SCL 設為 5 或 6 會採取 **[垃圾郵件]** 動作，將 SCL 設為 9 會採取 **[高信賴度的垃圾郵件]** 動作 (在內容篩選原則中設定)。 服務將執行內容篩選原則中所設定的動作。 預設動作是要將郵件傳遞至收件者的垃圾郵件] 資料夾，但是可以設定不同的動作，如所述[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。

   如果您設定的動作是要隔離郵件，而不是將它傳送給收件者的垃圾郵件] 資料夾，就會傳送訊息至管理員隔離區為郵件流程規則比對，且已將無法使用使用者垃圾郵件隔離區中或透過使用者垃圾郵件通知。

   如需服務中各 SCL 值的詳細資訊，請參閱[垃圾郵件信賴等級](spam-confidence-levels.md)。

8. 儲存規則。

## <a name="for-more-information"></a>相關資訊

[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)

[大量抱怨層級值](bulk-complaint-level-values.md)

[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)

[進階垃圾郵件篩選選項](advanced-spam-filtering-asf-options.md)
