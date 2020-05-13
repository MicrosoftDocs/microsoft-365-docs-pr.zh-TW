---
title: 在獨立 EOP 中查看系統管理員審核記錄
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
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 系統管理員可以瞭解如何在獨立 Exchange Online Protection （EOP）中查看及搜尋管理審核記錄。
ms.openlocfilehash: 3aedebc97ccd32c1641510017a276ddbe4770633
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208473"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>在獨立 EOP 中查看系統管理員審核記錄

在沒有 Exchange Online 信箱的獨立 Exchange Online Protection （EOP）組織中，您可以使用 Exchange 系統管理中心（EAC）或獨立的 EOP PowerShell，在系統管理員審核記錄中搜尋並查看專案。

系統管理員審核記錄會根據獨立 EOP PowerShell Cmdlet，記錄由系統管理員及已獲指派系統管理許可權之使用者所執行的特定動作。 系統管理員審核記錄中的專案會提供您執行的指令程式、所使用的參數、使用 Cmdlet 的執行者，以及受影響物件的相關資訊。

> [!NOTE]
> <ul><li>系統管理員審核記錄預設為啟用，您無法停用。</li><li>系統管理員審核記錄不會根據以**Get**、 **Search**或**Test**動詞開頭的指令程式，記錄動作。</li><li>稽核記錄項目會保留 90 天的時間。 當專案超過90天時，它會被刪除</li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 若要開啟 Exchange 系統管理中心，請參閱[exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要連線至獨立 EOP PowerShell，請參閱[connect To Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 您必須已獲指派權限，才能執行這些程序。 具體說來，您需要 ComplianceManagement 審核記錄檔或 View-Only 的「審核記錄」角色，其預設會指派給、OrganizationManagement （全域管理員）和 SecurityAdministrator 角色群組。 如需詳細資訊，請參閱[獨立 EOP 中的許可權](feature-permissions-in-eop.md)和[使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 有問題嗎？ 在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>使用 EAC 來查看系統管理員審核記錄檔

1. 在 EAC 中，移至 [**規範管理**] [ \> **審計**]，然後選擇 [**執行系統管理員審計記錄報告**]。

2. 在開啟的 [**搜尋系統管理員角色群組變更**] 頁面上，選擇 [**開始日期**] 和 [**結束日期**] （預設範圍是過去兩周），然後選擇 [**搜尋**]。 All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:

   - **日期**：設定變更的日期和時間。 日期和時間會以格林威治標準時間 (UTC) 格式儲存。

   - **Cmdlet**：用來變更設定之 Cmdlet 的名稱。

   - **User**：變更設定之使用者的使用者帳戶名稱。

     可在多個頁面上顯示最多 5000 個項目。如果需要縮小搜尋結果，請指定較小的日期範圍。如果您選取個別的搜尋結果，下列其他資訊會顯示在詳細資料窗格中：

   - **已修改物件**： Cmdlet 所修改的物件。

   - **Parameters （參數： Value）**：使用的 Cmdlet 參數，以及使用參數指定的任何值。

3. 如果您要列印特定的稽核記錄項目，請選擇詳細資料窗格中的 [ **列印**] 按鈕。

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>使用獨立 EOP PowerShell 來查看系統管理員審核記錄檔

您可以使用獨立 EOP PowerShell 來搜尋符合您指定之準則的審計記錄專案。 請使用下列語法：

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**附註**：

- 您只能將_Parameters_參數與_Cmdlet_參數搭配使用。

- _ObjectIds_參數會依 Cmdlet 所修改的物件來篩選結果。 有效的值取決於物件在審計記錄中的表示方式。 例如：

  - 名稱
  - 正常化辨別名稱（例如，contoso.com/Users/Akia Al Zuhairi）

  您可能需要在此 Cmdlet 上使用其他篩選參數，以縮小結果，並識別您感興趣的物件類型。

- _UserIds_參數會依進行變更的使用者（執行 Cmdlet 的執行者）來篩選結果。

- 針對_StartDate_和_EndDate_參數，如果您指定的日期/時間值不含時區，則值為 [世界時（UTC）]。 若要指定這個參數的日期/時間值，請使用下列其中一個選項︰

  - 指定 UTC 的日期/時間值：例如，"2016-05-06 14:30:00z"。

  - 指定 [日期/時間] 值做為公式，以將您的本機時區中的日期/時間轉換成 UTC：例如， `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 。 如需詳細資訊，請參閱 [Get-Date](https://go.microsoft.com/fwlink/p/?LinkID=113313)。

- 根據預設，Cmdlet 會傳回最多1000個記錄專案。 使用_ResultSize_參數可指定最多250000個記錄專案。 或者，使用值傳回 `Unlimited` 所有專案。

此範例使用下列準則，執行所有稽核記錄項目的搜尋：

- **開始日期**：2019年8月4日
- **結束日期**：2019年10月3日
- **Cmdlet**： Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

如需詳細的語法及參數資訊，請參閱 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog)。

### <a name="view-details-of-audit-log-entries"></a>檢視稽核記錄項目的詳細資料

**Search-AdminAuditLog** Cmdlet 會傳回本主題稍後的「[審核記錄內容](#audit-log-contents)」區段中所述的欄位。 由指令程式傳回的欄位、兩個欄位**CmdletParameters**和**ModifiedProperties**，包含預設不會傳回的其他資訊。

若要檢視 **CmdletParameters** 和 **ModifiedProperties** 欄位的內容，請使用下列步驟。

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

## <a name="audit-log-contents"></a>稽核記錄內容

每個審計記錄專案都包含下表所述的資訊。 審核記錄檔包含一或多個審計記錄專案。

|||
|---|---|
|**Field**|**描述**|
|`RunspaceId`|此欄位是由 EOP 在內部使用。|
|`ObjectModified`|此欄位包含的物件是由欄位中指定的 Cmdlet 所修改 `CmdletName` 。|
|`CmdletName`|此欄位包含使用者在欄位中執行的 Cmdlet 名稱 `Caller` 。|
|`CmdletParameters`|此欄位包含在執列欄位中的 Cmdlet 時所指定的參數 `CmdletName` 。 此外，在此欄位中（但在預設輸出中看不到）是以參數指定的值（如果有的話）。|
|`ModifiedProperties`|此欄位包含在欄位中的物件上修改的屬性 `ObjectModified` 。 此欄位也儲存在此欄位中，但在預設輸出中不會顯示，也就是舊的屬性值及已儲存的新值。|
|`Caller`|此欄位包含在欄位中執行 Cmdlet 之使用者的使用者帳戶 `CmdletName` 。|
|`ExternalAccess`|此欄位是由 EOP 在內部使用。|
|`Succeeded`|此欄位會指定是否已成功執列欄位中的 Cmdlet `CmdletName` 。 其值為 `True` 或 `False` 。|
|`Error`|此欄位包含當欄位中的 Cmdlet 未能成功完成時所產生的錯誤訊息 `CmdletName` 。|
|`RunDate`|此欄位包含執列欄位中的指令程式的日期和時間 `CmdletName` 。 日期和時間會以格林威治標準時間 (UTC) 格式儲存。|
|`OriginatingServer`|此欄位會指出執列欄位中所指定之指令程式的伺服器 `CmdletName` 。|
|`ClientIP`|此欄位是由 EOP 在內部使用。|
|`SessionId`|此欄位是由 EOP 在內部使用。|
|`AppId`|此欄位是由 EOP 在內部使用。|
|`ClientAppId`|此欄位是由 EOP 在內部使用。|
|`Identity`|此欄位是由 EOP 在內部使用。|
|`IsValid`|此欄位是由 EOP 在內部使用。|
|`ObjectState`|此欄位是由 EOP 在內部使用。|
|
