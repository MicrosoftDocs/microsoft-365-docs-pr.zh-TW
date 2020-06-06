---
title: 在獨立版 EOP 中執行系統管理員角色群組報告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 管理員可以瞭解如何在獨立 Exchange Online Protection （EOP）中執行系統管理員角色群組報告。 當系統管理員在系統管理員角色群組中新增或移除成員時，此報告會登入，EOP 記錄每次出現一次。
ms.openlocfilehash: 0c504460657a153aad7d3dd065c81007a68ba916
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587361"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>在獨立版 EOP 中執行系統管理員角色群組報告

在沒有 Exchange Online 信箱的獨立 Exchange Online Protection （EOP）組織中，當系統管理員新增成員至或移除系統管理角色群組中的成員時，服務會記錄每個事件。 如需獨立 EOP 中角色群組的詳細資訊，請參閱[獨立 EOP 中的許可權](feature-permissions-in-eop.md)。

當您在 Exchange 系統管理中心（EAC）中執行系統管理員角色群組報告時，專案會顯示為搜尋結果，並包含受影響的角色群組、變更角色群組成員資格的人員，以及進行的成員資格更新。 使用此報告可監視指派給組織使用者的系統管理權限變更。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 若要開啟 Exchange 系統管理中心，請參閱[exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 您必須已獲指派權限，才能執行這些程序。 具體說來，您需要 ComplianceManagement 審核記錄檔或 View-Only 的「審核記錄」角色，其預設會指派給、OrganizationManagement （全域管理員）和 SecurityAdministrator 角色群組。 如需詳細資訊，請參閱[獨立 EOP 中的許可權](feature-permissions-in-eop.md)和[使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 有問題嗎？ 在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>使用 EAC 執行系統管理員角色群組報告

執行系統管理員角色群組報告，以在特定時間範圍內尋找組織中管理角色群組的變更。

1. 在 EAC 中，移至 [**規範管理**] [ \> **審計**]，然後選擇 [**執行系統管理員角色群組報告**]。

2. 在開啟的 [**搜尋系統管理員角色群組變更**] 頁面上，設定下列設定：

   - **開始日期**和**結束日期**：輸入日期範圍。 依預設，報告會搜尋過去兩週以來對系統管理員角色群組所做的變更。

   - **選取角色群組**：根據預設，會搜尋所有角色群組。 若要依特定角色群組篩選結果，請按一下 [**選取角色群組**]。 在出現的對話方塊中，選取角色群組，然後按一下 [**載入 >**]。 視需要重複此步驟，然後在完成時按一下 **[確定]** 。

3. 完成後，請按一下 [**搜尋**]。

如果使用您指定的準則找到任何變更，它們會出現在結果窗格中。按一下搜尋結果中的角色群組，即可在詳細資料窗格中查看變更。

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

如果您已經成功執行系統管理員角色群組報告，已在日期範圍內變更的角色群組會顯示在搜尋結果窗格中。如果沒有任何結果，則表示在指定的日期範圍內，沒有對角色群組進行任何變更。如果您認為應該有結果，請變更日期範圍，然後重新執行報告。

## <a name="monitor-changes-to-role-group-membership"></a>監視角色群組成員資格的變更

在角色群組中新增或移除成員時，搜尋結果會顯示在詳細資料窗格中，指出角色群組成員資格已經更新，並列出目前的成員。結果不會明確表示已新增或移除哪一位使用者。

若要判斷是否已新增或移除某位使用者，您必須比較報告中的兩個個別項目。例如，以下是 **HelpDesk** 角色群組的記錄項目：

> 1/27/2018 4:43 PM <br> 系統管理員 <br> Updated members:Administrator;annb,florencef;pilarp <br> 2/06/2018 10:09 AM <br> 系統管理員 <br> Updated members:Administrator;annb;florencef;pilarp;tonip <br> 2/19/2018 2:12 PM <br> 系統管理員 <br> Updated members:Administrator;annb;florencef;tonip

在此範例中，系統管理員使用者帳戶做了以下變更：

- 在2/06/2018 上，他們新增了使用者 tonip。

- 在2/19/2018 上，他們移除使用者 pilarp。

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>使用獨立 Exchange Online PowerShell 來搜尋審計記錄專案

您可以使用 Exchange Online PowerShell 來搜尋符合您指定之準則的審計記錄專案。 如需搜尋準則的清單，請參閱[Search-AdminAuditLog 搜尋準則](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)。 此程式會使用**Search-AdminAuditLog** Cmdlet，並以 Exchange Online PowerShell 顯示搜尋結果。 當您需要傳回的一組結果超過 **New-AdminAuditLogSearch** Cmdlet 或 EAC「稽核報告」報告中所定義的限制時，就可以使用這個 Cmdlet。

若要搜尋指定準則的稽核記錄，請使用下列語法。

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> 根據預設， **Search-AdminAuditLog** 指令程式最多會傳回 1,000 個記錄項目。 使用_ResultSize_參數可指定最多250000個記錄專案。 或者，使用值傳回 `Unlimited` 所有專案。

此範例使用下列準則，執行所有稽核記錄項目的搜尋：

- **開始日期**：08/04/2018

- **結束日期**：10/03/2018

- **使用者 IDs**： davids、chrisd、kima

- **Cmdlet**： **Set-Mailbox**

- **Parameters**： _ProhibitSendQuota_、 _ProhibitSendReceiveQuota_、 _IssueWarningQuota_、 _MaxSendSize_、 _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

此範例搜尋特定信箱的變更。如果您在進行疑難排解或需要提供調查的資訊，這會很有用。使用下列準則：

- **開始日期**：05/01/2018

- **結束日期**：10/03/2018

- **物件識別碼**： contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

如果您的搜尋傳回許多記錄專案，建議您使用使用 Exchange Online PowerShell 中提供的程式，**來搜尋審計記錄專案，並將結果傳送給**本主題稍後的收件者。 該章節中的程序會以電子郵件附件形式將 XML 檔案傳送給您指定的收件者，讓您更輕鬆擷取感興趣的資料。

如需詳細的語法及參數資訊，請參閱 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)。

### <a name="view-details-of-audit-log-entries"></a>檢視稽核記錄項目的詳細資料

**Search-AdminAuditLog** Cmdlet 會傳回[審核記錄內容](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)中所述的欄位。 在此指令程式傳回的欄位中， **CmdletParameters** 和 **ModifiedProperties** 兩個欄位包含依預設無法檢視的其他資訊。

若要檢視 **CmdletParameters** 和 **ModifiedProperties** 欄位的內容，請使用下列步驟。 或者，您可以使用**Exchange Online PowerShell 中的程式來搜尋審計記錄專案，並將結果傳送到**本主題稍後的收件者，以建立 XML 檔案。

此程序採用下列概念：

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. 決定您要搜尋的準則、執行 **Search-AdminAuditLog** 指令程式，然後使用下列命令將結果儲存在變數中。

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. 每個審計記錄專案都是以陣列元素形式儲存在變數中 `$Results` 。 您可以指定陣列項目索引來選取陣列元素。 陣列元素索引從零 (0) 開始，表示第一個陣列元素。 例如，若要擷取第 5 個陣列元素，其索引為 4，請使用下列命令。

    ```PowerShell
    $Results[4]
    ```

3. 上一個命令會傳回儲存在陣列元素 4 中的記錄項目。若要查看此記錄項目的 **CmdletParameters** 和 **ModifiedProperties** 欄位的內容，請使用下列命令。

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. 若要檢視另一個記錄項目的 **CmdletParameters** 或 **ModifiedParameters** 欄位，請變更陣列元素索引。