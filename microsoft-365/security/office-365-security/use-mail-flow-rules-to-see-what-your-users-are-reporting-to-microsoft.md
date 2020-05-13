---
title: 使用郵件流程規則來查看您的使用者報告給 Microsoft 哪些內容
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
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用郵件流程規則（也稱為傳輸規則），接收使用者向 Microsoft 報告的郵件副本。
ms.openlocfilehash: 3c0ff9556b9800a0c3be22f52d108d6b16cc6657
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213481"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>使用郵件流程規則來查看您的使用者報告給 Microsoft 哪些內容

在未使用 Exchange online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中使用信箱的 Microsoft 365 組織中，有多種方式可讓使用者將郵件報告給 Microsoft 進行分析，如[報告訊息和檔案至 microsoft](report-junk-email-messages-to-microsoft.md)中所述。

您可以建立郵件流程規則（也稱為傳輸規則），以尋找使用者向 Microsoft 報告的郵件，而且您可以設定密件副本收件者接收這些報告郵件的副本。

您可以在 Exchange 系統管理中心（EAC）中建立郵件流程規則，並 PowerShell （Exchange online PowerShell （包含 Exchange Online 中信箱的 Microsoft 365 組織）; 獨立 EOP PowerShell （沒有 Exchange Online 信箱的組織）。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您必須先在 Exchange Online 或 EOP 中指派許可權，才能執行這些程式。 具體而言，您必須被指派**傳輸規則**角色，預設會指派給**組織管理**、**規範管理**及**記錄管理**角色。 如需詳細資訊，請參閱[管理 Exchange Online 中的角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

- 若要開啟 EAC，請參閱 exchange Online 或[獨立 EOP 中的 exchange 系統管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)中的[exchange 系統管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要連線至獨立 EOP PowerShell，請參閱[connect To Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 如需 Exchange Online 和獨立 EOP 中郵件流程規則的相關資訊，請參閱下列主題：

  - [Exchange Online 中的郵件流程規則 (傳輸規則)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online 中的郵件流程規則條件和例外狀況 (述詞)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online 中的郵件流程規則動作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 EAC 來建立郵件流程規則，以接收報告訊息的副本

1. 在 EAC 中，移至 [郵件流程]**** \> [規則]****。

2. 按一下 [**新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後選取 [**建立新的規則**]。

3. 在開啟的 [**新增規則**] 頁面中，設定下列設定：

   - **名稱**：輸入規則的唯一描述性名稱。 例如，向 Microsoft 報告的 Bcc 郵件。

   - 按一下 [**更多選項**]。

   - 在下列情況下套用**此規則**：選取**收件**者 \> **位址包含下列任何文字**：在出現的 [**指定字詞或片語**] 對話方塊中，輸入下列其中一個值，按一下 [**新增**] ![ 圖示 ](../../media/ITPro-EAC-AddIcon.png) ，然後重複，直到您輸入所有值為止。

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     若要編輯專案，請選取它，然後按一下 [**編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。 若要移除專案，請選取它，然後按一下 [**移除** ![ 移除圖示] ](../../media/ITPro-EAC-DeleteIcon.png) 。

     完成後，按一下 [確定]****。

   - **請執行下列**動作：選取 [將收件者**新增** \> **至 Bcc**] 方塊。 在出現的對話方塊中，尋找並選取您要新增的收件者。 完成後，按一下 [確定]****。

4. 您可以進行其他選擇來審核規則、測試規則、在特定時間週期內啟動規則，以及其他設定。 建議您先測試規則，再加以強制執行。

5. 完成後，按一下 [儲存]****。

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 PowerShell 建立郵件流程規則，以接收報告訊息的副本

此範例會建立名為「Bcc 郵件」的新郵件流程規則，該規則會尋找使用本主題中所述方法向 Microsoft 報告的電子郵件訊息，並將使用者 laura@contoso.com 及 julia@contoso.com 新增為 Bcc 收件者。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要驗證您是否已設定郵件流程規則以接收報告的郵件副本，請執行下列任一步驟：

- 在 EAC 中，移至 [**郵件流程** \> **規則**] \> 選取規則 \> ，然後按一下 [**編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) ，然後驗證設定。

- 在 PowerShell 中，執行下列命令來確認設定：

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- 傳送測試郵件至其中一個報告電子郵件地址並確認結果。
