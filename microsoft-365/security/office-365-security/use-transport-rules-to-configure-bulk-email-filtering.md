---
title: 使用郵件流程規則來篩選大量電子郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用郵件流程規則 (傳輸規則) 來識別及篩選大宗郵件 (在 Exchange Online Protection (EOP) 中) 的灰色郵件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 62db73ea917139d81a29569d5b452637fd053c92
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775192"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>在 EOP 中使用郵件流程規則來篩選大量電子郵件

在包含 Exchange Online 或獨立 Exchange online)  (Protection 中信箱的 Microsoft 365 組織中，EOP 會使用反垃圾郵件原則 (也稱為垃圾郵件篩選原則或內容篩選原則) ，以掃描輸入郵件中的垃圾郵件和大宗郵件 (也稱為灰色郵件) 。 如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

如果您想要更多的選項來篩選大宗郵件，您可以建立郵件流程規則 (也稱為傳輸規則) 搜尋大宗郵件中經常找到的文字模式或片語，並將這些郵件標示為垃圾郵件。 如需大宗郵件的詳細資訊，請參閱 EOP 中 [垃圾郵件和大量電子郵件之間的差異](what-s-the-difference-between-junk-email-and-bulk-email.md) 和 [大量投訴層級 (BCL) ](bulk-complaint-level-values.md)。

本主題說明如何使用 exchange Online 中的信箱，在 Exchange 系統管理中心中建立這些郵件流程規則 (EAC) 和 PowerShell (Exchange Online PowerShell，以供 Microsoft 365 組織使用。沒有 Exchange Online 信箱) 之組織的獨立 EOP PowerShell。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您必須已獲指派許可權，才能執行這些程式：

  - 在 Exchange Online 中，請參閱在 [Exchange online 中的功能許可權中](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)的「郵件流程」專案。
  
  - 在獨立 EOP 中，您需要傳輸規則角色，預設會指派給 OrganizationManagement、ComplianceManagement 和 RecordsManagement 角色。 如需詳細資訊，請參閱 [獨立 EOP 中的許可權](feature-permissions-in-eop.md) 和 [使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 若要在 Exchange Online 中開啟 EAC，請參閱 exchange [online 中的 exchange admin center](https://docs.microsoft.com/Exchange/exchange-admin-center)。 若要在獨立 EOP 中開啟 EAC，請參閱 [Exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 如需 Exchange Online 和獨立 EOP 中郵件流程規則的相關資訊，請參閱下列主題：

  - [Exchange Online 中的郵件流程規則 (傳輸規則)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online 中的郵件流程規則條件和例外狀況 (述詞)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online 中的郵件流程規則動作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- 在範例中用來識別大宗郵件的單字和文字模式清單並不詳盡;您可以視需要新增及移除專案。 不過，它們是一個很好的起點。

- 在主旨或郵件的其他標頭欄位中搜尋字詞或文字模式，會發生在郵件已從 MIME 內容傳輸編碼方法進行解碼*之後*，該編碼方法用來在 SMTP 伺服器之間傳送 ASCII 文字二進位訊息。您無法使用條件或例外狀況來搜尋主旨或郵件中其他標頭欄位的原始 (通常是 Base64) 編碼值。

- 下列程式會將大宗郵件標記為您整個組織的垃圾郵件。 不過，您可以新增另一個條件，只將這些規則套用至特定的收件者，這樣您就可以在一些高度具有目標的使用者上使用嚴格篩選，而其餘的使用者 (通常會取得已註冊) 大量電子郵件的使用者，不會受到影響。

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>使用 EAC 來建立郵件流程規則，以篩選大量電子郵件

1. 在 EAC 中，移至 [郵件流程]**** \> [規則]****。

2. 按一下 [ **新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後選取 [ **建立新的規則**]。

3. 在開啟的 [ **新增規則** ] 頁面中，設定下列設定：

   - **名稱**：輸入規則的唯一描述性名稱。

   - 按一下 [ **更多選項**]。

   - **在下列情況中套用此規則**：設定下列其中一項設定，以在使用正則運算式的郵件中尋找內容 (RegEx) 或字或片語：

     - **主語或** \> 本文主旨或內文 **符合這些文字模式**：在出現的 [ **指定字詞或片語** ] 對話方塊中，輸入下列其中一個值，按一下 [ **新增**] ![ 圖示 ](../../media/ITPro-EAC-AddIcon.png) ，然後重複，直到您輸入所有值為止。

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      若要編輯專案，請選取它，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。 若要移除專案，請選取它，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完成後，按一下 [確定]****。

     - **主語或** \> 本文主旨或內文 **包含下列任何文字**：在出現的 [ **指定字詞或片語** ] 對話方塊中，輸入下列其中一個值，按一下 [ **新增**] ![ 圖示 ](../../media/ITPro-EAC-AddIcon.png) ，然後重複，直到您輸入所有值為止。

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

      若要編輯專案，請選取它，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。 若要移除專案，請選取它，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完成後，按一下 [確定]****。

   - **請執行下列**動作：選取 **[修改郵件**內容] \> 。 ** (SCL) 設定垃圾郵件信賴等級 **。 在出現的 [ **指定 SCL** ] 對話方塊中，設定下列其中一個設定：

     - 若要將郵件標示為 **垃圾**郵件，請選取 [ **6**]。 您為反垃圾郵件原則中的 **垃圾** 郵件篩選 verdicts 設定的動作會套用至郵件 (預設值會將 **郵件移至 [垃圾郵件] 資料夾**) 。

     - 將郵件標示為 **高信賴度垃圾郵件** 選取 **9**。 您為反垃圾郵件原則中已設定 **高信賴垃圾郵件** 篩選 verdicts 的動作會套用至郵件 (預設值會將 **郵件移至 [垃圾郵件] 資料夾**) 。

    如需 SCL 值的詳細資訊，請參閱 [垃圾郵件信賴等級 (scl) 在 EOP 中](spam-confidence-levels.md)。

   完成後，請按一下 [儲存]****。

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>使用 PowerShell 建立郵件流程規則，以篩選大量電子郵件

使用下列語法來建立一或兩個郵件流程規則 (正則運算式與 words) ：

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

本範例會建立名為「大量電子郵件篩選-RegEx」的新規則，該規則使用主題中早期的正則運算式清單，將郵件設定為 **垃圾**郵件。

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

本範例會建立名為「大量電子郵件篩選-字」的新規則，該規則使用主題中相同的單字清單，將郵件設定為 **高信賴的垃圾郵件**。

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要驗證您是否已設定郵件流程規則以篩選大量電子郵件，請執行下列任一步驟：

- 在 EAC 中，移至 [ **郵件流程** \> **規則**] \> 選取規則 \> ，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) ，然後驗證設定。

- 在 PowerShell 中，以 \<Rule Name\> 規則名稱取代，並執行下列命令來確認設定：

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- 從外部帳戶，傳送測試郵件至受影響的收件者，其中包含其中一個短語或文字模式，並確認結果。
