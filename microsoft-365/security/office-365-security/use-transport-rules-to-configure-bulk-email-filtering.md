---
title: 使用郵件流程規則來篩選 Office 365 中的大量電子郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
description: 系統管理員可以瞭解如何使用 Exchange Online Protection 中的郵件流程規則，以進行大量電子郵件篩選。
ms.openlocfilehash: 229a66658e041be737efbc4cbb7c36ba667d3aed
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631070"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a>使用郵件流程規則來篩選 Office 365 中的大量電子郵件

如果您是使用 Exchange Online 中的信箱或獨立 Exchange Online Protection （EOP）客戶但沒有 Exchange Online 信箱的 Microsoft 365 客戶，EOP 會使用反垃圾郵件原則（也稱為垃圾郵件篩選原則或內容篩選原則）來掃描輸入郵件中的垃圾郵件和大宗郵件（也稱為灰色郵件）。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

如果您想要更多的選項來篩選大宗郵件，您可以建立郵件流程規則（也稱為傳輸規則），以搜尋大宗郵件中經常找到的文字模式或片語，並將這些郵件標示為垃圾郵件。 如需大宗郵件的詳細資訊，請參閱 Office 365 中的[垃圾郵件和大量電子郵件](what-s-the-difference-between-junk-email-and-bulk-email.md)以及[大量投訴（BCL）](bulk-complaint-level-values.md)之間的差異。

本主題說明如何在 Exchange 系統管理中心（EAC）和 PowerShell （Microsoft 365 客戶的 Exchange Online PowerShell 中建立這些郵件流程規則;Exchange Online Protection PowerShell 適用于獨立 EOP 客戶）。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您必須先在 Exchange Online 中指派許可權，才能執行這些程式。 具體而言，您必須被指派**傳輸規則**角色，預設會指派給**組織管理**、**規範管理**及**記錄管理**角色。 如需詳細資訊，請參閱[管理 Exchange Online 中的角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

- 若要在 Exchange Online 中開啟 EAC，請參閱 exchange [online 中的 exchange admin center](https://docs.microsoft.com/Exchange/exchange-admin-center)。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要連接至獨立版 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 如需 Exchange Online 和獨立 EOP 中郵件流程規則的相關資訊，請參閱下列主題：

  - [Exchange Online 中的郵件流程規則 (傳輸規則)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online 中的郵件流程規則條件和例外狀況 (述詞)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online 中的郵件流程規則動作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- 在範例中用來識別大宗郵件的單字和文字模式清單並不詳盡;您可以視需要新增及移除專案。 不過，它們是一個很好的起點。

- 在主旨或郵件的其他標頭欄位中搜尋字詞或文字模式，會發生在郵件已從 MIME 內容傳輸編碼方法進行解碼*之後*，該編碼方法用來在 SMTP 伺服器之間傳送 ASCII 文字二進位訊息。您無法使用條件或例外狀況來搜尋主旨或郵件中其他標頭欄位的原始 (通常是 Base64) 編碼值。

- 下列程式會將大宗郵件標記為您整個組織的垃圾郵件。 不過，您可以新增另一個條件，只將這些規則套用至特定的收件者，這樣您就可以在一些高度目標的使用者上使用嚴格篩選，而其餘的使用者（大部分已註冊的大量電子郵件）不會受到影響。

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>使用 EAC 來建立郵件流程規則，以篩選大量電子郵件

1. 在 EAC 中，移至 [郵件流程]**** \> [規則]****。

2. 按一下 [**新增** ![加入](../../media/ITPro-EAC-AddIcon.png)圖示]，然後選取 [**建立新的規則**]。

3. 在開啟的 [**新增規則**] 頁面中，設定下列設定：

   - **名稱**：輸入規則的唯一描述性名稱。

   - 按一下 [**更多選項**]。

   - **在下列情況中套用此規則**：設定下列其中一個設定，以使用正則運算式（RegEx）或字詞或片語來尋找郵件中的內容：

     - 主旨**或** \>本文的主旨或內文**符合這些文字模式**：在出現的 [**指定字詞或片語**] 對話方塊中，輸入下列其中一個值，按一下 [](../../media/ITPro-EAC-AddIcon.png)**新增** ![] 圖示，然後重複，直到您輸入所有值為止。

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

      若要編輯專案，請選取它， **Edit** ![然後按一下 [](../../media/ITPro-EAC-EditIcon.png)編輯編輯圖示]。 若要移除專案，請選取它， **Remove** ![然後按一下 [](../../media/ITPro-EAC-DeleteIcon.png)移除移除圖示]。

       完成後，按一下 [確定]****。

     - 主旨**或** \>本文的主旨或內文**包含下列任何文字**：在出現的 [**指定字詞或片語**] 對話方塊中，輸入下列其中一個值，按一下 [**新增** ![] 圖示](../../media/ITPro-EAC-AddIcon.png)，然後重複，直到您輸入所有值為止。

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

      若要編輯專案，請選取它， **Edit** ![然後按一下 [](../../media/ITPro-EAC-EditIcon.png)編輯編輯圖示]。 若要移除專案，請選取它， **Remove** ![然後按一下 [](../../media/ITPro-EAC-DeleteIcon.png)移除移除圖示]。

       完成後，按一下 [確定]****。

   - **請執行下列**動作：選取 [**修改郵件屬性** \> ]**設定垃圾郵件信賴等級（SCL）**。 在出現的 [**指定 SCL** ] 對話方塊中，設定下列其中一個設定：

     - 若要將郵件標示為**垃圾**郵件，請選取 [ **6**]。 您為反垃圾郵件原則中的**垃圾**郵件篩選 verdicts 設定的動作會套用至郵件（預設值為 [**將郵件移至垃圾郵件資料夾**]）。

     - 將郵件標示為**高信賴度垃圾郵件**選取**9**。 您為反垃圾郵件原則中已設定**高信賴度垃圾郵件**篩選 verdicts 的動作會套用至郵件（預設值為 [**將郵件移至垃圾郵件資料夾**]）。

    如需 SCL 值的詳細資訊，請參閱[Office 365 中的垃圾郵件信賴等級（SCL）](spam-confidence-levels.md)。

   完成後，請按一下 [儲存]****。

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>使用 PowerShell 建立郵件流程規則，以篩選大量電子郵件

使用下列語法來建立一或兩個郵件流程規則（正則運算式與字）：

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

本範例會建立名為「大量電子郵件篩選-RegEx」的新規則，該規則使用主題中早期的正則運算式清單，將郵件設定為**垃圾**郵件。

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

本範例會建立名為「大量電子郵件篩選-字」的新規則，該規則使用主題中相同的單字清單，將郵件設定為**高信賴的垃圾郵件**。

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要驗證您是否已設定郵件流程規則以篩選大量電子郵件，請執行下列任一步驟：

- 在 EAC 中，移至 [**郵件流程** \> **規則** \> ] 選取\>規則，然後按一下](../../media/ITPro-EAC-EditIcon.png)[**編輯** ![編輯圖示]，然後驗證設定。

- 在 PowerShell 中， \<以規則\>名稱取代規則名稱，並執行下列命令來確認設定：

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- 從外部帳戶，傳送測試郵件至受影響的收件者，其中包含其中一個短語或文字模式，並確認結果。
