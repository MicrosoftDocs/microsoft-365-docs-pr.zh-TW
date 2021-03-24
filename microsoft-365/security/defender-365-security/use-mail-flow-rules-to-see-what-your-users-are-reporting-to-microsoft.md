---
title: 使用郵件流程規則來查看您的使用者報告給 Microsoft 哪些內容
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用郵件流程規則 (也稱為傳輸規則) 接收使用者向 Microsoft 報告的郵件副本。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e6428a228ae64562f0b529f6aa90ddc3be46fdc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057211"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>使用郵件流程規則來查看您的使用者報告給 Microsoft 哪些內容

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱時，使用者可以使用多種方式，將郵件報告給 Microsoft 進行分析，如 [報表訊息和檔案至 microsoft](report-junk-email-messages-to-microsoft.md)所述。

您可以建立郵件流程規則 (也稱為傳輸規則) ，它會尋找使用者向 Microsoft 報告的郵件，而且您可以設定密件副本收件者接收這些報告郵件的副本。

您可以在 Exchange 系統管理中心中建立郵件流程規則 (EAC) 並 PowerShell Exchange Online 中包含信箱的 Microsoft 365 組織 (Exchange Online PowerShell;沒有 Exchange Online 信箱) 之組織的獨立 EOP PowerShell。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您必須先在 Exchange Online 或 Exchange Online Protection 中指派許可權，才能執行本文中的程式。 具體說來，您需要「 **傳輸規則** 」角色，該角色會指派給「 **組織管理**」、「 **合規性管理** 」 (全域系統管理員) ，並依預設 **記錄管理** 角色群組。

  如需詳細資訊，請參閱下列主題：

  - [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)
  - [獨立版 EOP 中的權限](feature-permissions-in-eop.md)
  - [使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 若要在 Exchange Online 中開啟 EAC，請參閱 exchange [online 中的 exchange admin center](/Exchange/exchange-admin-center)。 若要在獨立 EOP 中開啟 EAC，請參閱 [Exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 如需 Exchange Online 和獨立 EOP 中郵件流程規則的相關資訊，請參閱下列主題：
  - [Exchange Online 中的郵件流程規則 (傳輸規則)](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Exchange Online 中的郵件流程規則條件和例外狀況 (述詞)](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Exchange Online 中的郵件流程規則動作](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 EAC 來建立郵件流程規則，以接收報告訊息的副本

1. 在 EAC 中，移至 [郵件流程] \> [規則]。

2. 按一下 [ **新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後選取 [ **建立新的規則**]。

3. 在開啟的 [ **新增規則** ] 頁面中，設定下列設定：

   - **名稱**：輸入規則的唯一描述性名稱。 例如，向 Microsoft 報告的 Bcc 郵件。

   - 按一下 [ **更多選項**]。

   - 在下列情況下套用 **此規則**：選取 **收件** 者 \> **位址包含下列任何文字**：在出現的 [**指定字詞或片語**] 對話方塊中，輸入下列其中一個值，按一下 [**新增**] ![ 圖示 ](../../media/ITPro-EAC-AddIcon.png) ，然後重複，直到您輸入所有值為止。

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     若要編輯專案，請選取它，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。 若要移除專案，請選取它，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-DeleteIcon.png) 。

     完成後，按一下 [確定]。

   - **請執行下列** 動作：選取 [將收件者 **新增** \> **至 Bcc**] 方塊。 在出現的對話方塊中，尋找並選取您要新增的收件者。 完成後，按一下 [確定]。

4. 您可以進行其他選擇來審核規則、測試規則、在特定時間週期內啟動規則，以及其他設定。 建議您先測試規則，再加以強制執行。

5. 完成後，請按一下 **[儲存]**。

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 PowerShell 建立郵件流程規則，以接收報告訊息的副本

此範例會建立名為「Bcc 郵件」的新郵件流程規則，它會向 Microsoft 報告出使用本文所述方法向 Microsoft 報告的電子郵件訊息，並將使用者 laura@contoso.com 及 julia@contoso.com 新增為 Bcc 收件者。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

如需詳細的語法和參數資訊，請參閱 [New-TransportRule](/powershell/module/exchange/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要驗證您是否已設定郵件流程規則以接收報告的郵件副本，請執行下列任一步驟：

- 在 EAC 中，移至 [ **郵件流程** \> **規則**] \> 選取規則 \> ，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) ，然後驗證設定。

- 在 PowerShell 中，執行下列命令來確認設定：

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- 傳送測試郵件至其中一個報告電子郵件地址並確認結果。