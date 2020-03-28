---
title: 手動將郵件提交給 Microsoft 進行分析
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: '您和您的使用者可以將假的否定和誤報垃圾郵件提交給 Microsoft 進行分析。 '
ms.openlocfilehash: 13b2e42f749b54e0c2b71fe095c077992560ea8c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032801"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>手動將郵件提交給 Microsoft 進行分析

> [!NOTE]
> 如果您是 Office 365 組織中 Exchange Online 信箱的系統管理員，建議您在 Office 365 安全性 & 規範中心使用提交入口網站。 如需詳細資訊，請參閱[使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。

當您組織中的使用者在其收件匣中收到垃圾郵件（垃圾郵件）或網路釣魚郵件時，或是因為郵件標示為垃圾郵件而未收到合法電子郵件時，可能會令人感到沮喪。 我們不斷微調垃圾郵件篩選器，使其更準確。

您和您的使用者可以提交誤報（不良電子郵件標記為壞）、誤報（允許錯誤郵件）和網路以進行分析，以協助此程式。

> [!NOTE]
> 由於我們收到大量送出的報送，我們可能無法回答所有要求進行分析。

## <a name="submit-false-negatives-to-microsoft"></a>將漏報提交給 Microsoft

> [!TIP]
> 在 Outlook 和網頁型 Outlook （先前稱為 Outlook Web App）中的使用者可以使用 Microsoft Outlook 的報告訊息增益集，而不是使用下列程式來報告漏報。 如需如何安裝及使用此工具的詳細資訊，請參閱[Enable The Report Message 增益集](enable-the-report-message-add-in.md)。

如果您收到的郵件透過應識別為垃圾郵件篩選的垃圾郵件篩選，您可以視需要將郵件提交至 Microsoft 垃圾郵件分析和 Microsoft 網路釣魚分析小組。 分析員會檢查郵件，並將其新增至全服務篩選準則（如果符合分類準則）。

1. 使用下列其中一個收件者建立新的空白電子郵件訊息：

   - **垃圾郵件**：`junk@office365.microsoft.com`

   - **網路釣魚**：`phish@office365.microsoft.com`

2. 將垃圾郵件或網路釣魚郵件拖放到新郵件中。 這會將垃圾郵件或網路釣魚郵件儲存為新郵件中的附件。 請勿複製及貼上郵件內容或轉寄郵件（我們需要原始郵件，才能檢查郵件頭）。

   > [!NOTE]
   > <ul><li>您可以在新郵件中附加多封郵件。 請確定所有郵件都是相同類型：網路釣魚詐騙郵件或垃圾郵件。</li><li>將新郵件的內文保留空白。<li></li>使用 .msg （預設 Outlook 格式）或 .eml （預設 Outlook 網頁格式）格式的附加郵件。</li></ul>

3. 當您完成時，按一下 [**傳送**]。

> [!TIP]
> 系統管理員可以使用數種不同的方式封鎖正 misidentified 為垃圾郵件的特定郵件。 如需詳細資訊，請參閱[在 Office 365 中建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md)。

## <a name="submit-false-positives-to-microsoft"></a>將誤報提交給 Microsoft

> [!TIP]
> 您不用使用下列程式來報告誤報，Outlook 和網頁型 Outlook 中的使用者可以使用 Microsoft Outlook 的報告訊息增益集。 如需如何安裝及使用此工具的詳細資訊，請參閱[Enable The Report Message 增益集](enable-the-report-message-add-in.md)。

如果郵件被錯誤地辨識為垃圾郵件，您可以將郵件提交給 Microsoft 垃圾郵件分析小組。 分析員會評估郵件，並根據分析的結果，可以調整整個服務篩選器以允許郵件通過。

1. `not_junk@office365.microsoft.com`以收件者的身分建立新的空白電子郵件訊息：

2. 將 misidentified 郵件拖曳並放入新的郵件。 這會將 misidentified 郵件儲存為新郵件中的附件。 請勿複製及貼上郵件內容或轉寄郵件（我們需要原始郵件，才能檢查郵件頭）。

   > [!NOTE]
   > <ul><li>您可以在新郵件中附加多封郵件。 請確定所有郵件都是相同類型：網路釣魚詐騙郵件或垃圾郵件。</li><li>將新郵件的內文保留空白。<li></li>使用 .msg （預設 Outlook 格式）或 .eml （預設 Outlook 網頁格式）格式的附加郵件。</li></ul>

3. 當您完成時，按一下 [**傳送**]。

> [!TIP]
> 系統管理員有幾種不同的方式可讓特定郵件略過垃圾郵件篩選。 如需詳細資訊，請參閱[在 Office 365 中建立安全寄件者清單](create-safe-sender-lists-in-office-365.md)。

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>建立郵件流程規則，以接收報告給 Microsoft 的郵件副本

您可以建立郵件流程規則（也稱為傳輸規則），以使用本主題中所述的方法來尋找向 Microsoft 報告的電子郵件訊息，而且您可以設定密件副本收件者接收這些報告的郵件副本。

您可以在 Exchange 系統管理中心（EAC）和 PowerShell （Office 365 客戶的 Exchange Online PowerShell 中建立郵件流程規則;Exchange Online Protection PowerShell 適用于獨立 EOP 客戶）。

### <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您必須先在 Exchange Online 中指派許可權，才能執行這些程式。 具體而言，您必須被指派**傳輸規則**角色，預設會指派給**組織管理**、**規範管理**及**記錄管理**角色。 如需詳細資訊，請參閱[管理 Exchange Online 中的角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

- 若要在 Exchange Online 中開啟 EAC，請參閱 exchange [online 中的 exchange admin center](https://docs.microsoft.com/Exchange/exchange-admin-center)。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要連線到獨立的 Exchange Online Protection PowerShell，請參閱[connect To Exchange Online protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 如需 Exchange Online 和獨立 EOP 中郵件流程規則的相關資訊，請參閱下列主題：

  - [Exchange Online 中的郵件流程規則 (傳輸規則)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online 中的郵件流程規則條件和例外狀況 (述詞)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online 中的郵件流程規則動作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 EAC 來建立郵件流程規則，以接收報告訊息的副本

1. 在 EAC 中，移至 [郵件流程]**** \> [規則]****。

2. 按一下 [**新增** ![加入](../../media/ITPro-EAC-AddIcon.png)圖示]，然後選取 [**建立新的規則**]。

3. 在開啟的 [**新增規則**] 頁面中，設定下列設定：

   - **名稱**：輸入規則的唯一描述性名稱。 例如，向 Microsoft 報告的 Bcc 郵件。

   - 按一下 [**更多選項**]。

   - 在下列情況下套用**此規則**：選取**收件**\>**位址包含下列任何文字**：在出現的 [**指定字詞或片語**] 對話方塊中，輸入下列其中一個值，](../../media/ITPro-EAC-AddIcon.png)按一下 [**新增** ![] 圖示，然後重複，直到您輸入所有值為止。

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     若要編輯專案，請選取它， **Edit** ![然後按一下 [](../../media/ITPro-EAC-EditIcon.png)編輯編輯圖示]。 若要移除專案，請選取它， **Remove** ![然後按一下 [](../../media/ITPro-EAC-DeleteIcon.png)移除移除圖示]。

     完成後，按一下 [確定]****。

   - **請執行下列**動作：選取 [將收件者**新增** \> **至 Bcc**] 方塊。 在出現的對話方塊中，尋找並選取您要新增的收件者。 完成後，按一下 [確定]****。

4. 您可以進行其他選擇來審核規則、測試規則、在特定時間週期內啟動規則，以及其他設定。 建議您先測試規則，再加以強制執行。

5. 完成後，請按一下 **[儲存]**。

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 PowerShell 建立郵件流程規則，以接收報告訊息的副本

此範例會建立名為「Bcc 郵件」的新郵件流程規則，該規則會尋找使用本主題中所述方法向 Microsoft 報告的電子郵件訊息，並將使用者 laura@contoso.com 及 julia@contoso.com 新增為 Bcc 收件者。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)。

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要驗證您是否已設定郵件流程規則以接收報告的郵件副本，請執行下列任一步驟：

- 在 EAC 中，移至 [**郵件流程** \> **規則** \> ] 選取\>規則，然後按一下](../../media/ITPro-EAC-EditIcon.png)[**編輯** ![編輯圖示]，然後驗證設定。

- 在 PowerShell 中，執行下列命令來確認設定：

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- 傳送測試郵件至其中一個報告電子郵件地址並確認結果。
