---
title: 如何找出位於 Exchange Online 信箱的保留類型
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何識別可放在 Microsoft 365 的 Exchange Online 信箱上的不同保留類型。
ms.openlocfilehash: ea7beb34107fb5eaf61c56ece7bde8070e6467a6
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126804"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>如何找出位於 Exchange Online 信箱的保留類型

本文說明如何在 Microsoft 365 中識別放在 Exchange Online 信箱上的「保留」。

Microsoft 365 提供數種方式，讓您的組織可以防止信箱內容遭到永久刪除。 這可讓您的組織保留內容，以符合合規性法規或法律和其他調查類型。 以下是 Office 365 中的保留功能（也稱為*保留*）清單：

- **[訴訟暫](create-a-litigation-hold.md)止：** 適用于 Exchange Online 中使用者信箱的保留。

- ** [eDiscovery 保留](create-ediscovery-holds.md)：** 與安全性與合規性中心中的核心 eDiscovery 案例相關聯的保留。 eDiscovery 保留可以套用到使用者信箱，以及 Microsoft 365 群組和 Microsoft 小組對應的信箱。

- **[保留 In-Place](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds)：** 在 Exchange Online 中使用 Exchange 系統管理中心的「In-Place eDiscovery & 保留」工具，將套用至使用者信箱的保留。

- ** [Microsoft 365 保留原則](retention.md)：** 可以設定為保留（或保留然後刪除） Exchange Online 中使用者信箱的內容，以及 Microsoft 365 群組和 Microsoft 小組對應的信箱中的內容。 您也可以建立保留原則，以保留儲存在使用者信箱中的商務用 Skype 交談。

  有兩種類型的 Microsoft 365 保留原則可指派給信箱。

    - **特定位置保留原則：** 這些是指派給特定使用者之內容位置的原則。 您可以在 Exchange Online PowerShell 中使用**Get-Mailbox** Cmdlet，以取得指派給特定信箱之保留原則的相關資訊。

    - **整個組織保留原則：** 這些是指派給組織中所有內容位置的原則。 您可以在 Exchange Online PowerShell 中使用**Get-OrganizationConfig** Cmdlet，以取得整個組織保留原則的資訊。
    
  如需詳細資訊，請參閱[將保留原則套用至整個組織或特定位置](create-retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)區段。

- **[Microsoft 365 保留標籤](retention.md)：** 如果使用者將 Microsoft 365 保留標籤（已設定為保留內容或保留，然後刪除內容）套用至其信箱中的*任何*資料夾或專案，則會在信箱上保留信箱，就像該信箱已處於訴訟暫止狀態或指派給 Microsoft 365 保留原則一樣。 如需詳細資訊，請參閱「保留中的信箱」，[因為保留標籤已套用至本文中的資料夾或專案](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)一節。

若要管理暫止的信箱，您可能必須識別放在信箱上的保留類型，這樣才能執行工作，例如變更保留期間、暫時或永久移除保留，或排除來自 Microsoft 365 保留原則的信箱。 在這些情況下，第一步是識別放在信箱上的保留類型。 而且，由於多個保留（和不同類型的保留）可以放在單一信箱上，因此，如果您想要移除或變更保留，您必須識別位於信箱上的所有保留。

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>步驟1：取得放在信箱上之保留的 GUID

您可以在 Exchange Online PowerShell 中執行下列兩個 Cmdlet，以取得信箱中所放置之保留的 GUID。 在取得 GUID 之後，您可以使用它來識別步驟2中的特定保留。 GUID 未識別訴訟暫止。 已啟用或停用信箱的訴訟資料暫留。

- **Get-Mailbox：** 您可以使用此 Cmdlet 來判斷是否已啟用信箱的訴訟資料暫留，以及是否要取得 eDiscovery 保留的 Guid、In-Place 保留，以及專門指派給信箱的 Microsoft 365 保留原則。 此 Cmdlet 的輸出也會指出是否已明確從整個組織的保留原則中排除信箱。

- **Get-OrganizationConfig：** 使用此 Cmdlet 取得整個組織保留原則的 Guid。

若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

### <a name="get-mailbox"></a>Get-Mailbox

執行下列命令，以取得適用于信箱的保留和 Microsoft 365 保留原則的資訊。

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 屬性中的值太多，而且不是所有的值都顯示出來，您可以執行此 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 命令，將每個 GUID 顯示在不同的行上。

下表說明當您執行**Get-Mailbox** Cmdlet 時，如何根據*InPlaceHolds*屬性中的值來識別不同類型的保留。


|保留類型  |範例值  |如何識別保留  |
|---------|---------|---------|
|訴訟暫止     |    `True`     |     當*LitigationHoldEnabled*屬性設定為時，信箱的訴訟資料暫留已啟用 `True` 。    |
|eDiscovery 保留     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   *InPlaceHolds 屬性*包含與安全性與合規性中心中的 eDiscovery 案例相關聯之任何保留的 GUID。 您可以告訴這是 eDiscovery 封存，因為 GUID 是以前置詞開頭 `UniH` （表示整合保留）。      |
|原有範圍暫止     |     `c0ba3ce811b6432a8751430937152491` <br/> 或 <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     *InPlaceHolds*屬性包含放在信箱上的 IN-PLACE 保留 GUID。 您可以告知這是 In-Place 保留，因為 GUID 不是以前置詞開頭，也不是以前置詞開頭 `cld` 。     |
|專門套用至信箱的 Microsoft 365 保留原則     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> 或 <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     InPlaceHolds 屬性包含套用至信箱之任何特定位置保留原則的 Guid。 您可以識別保留原則，因為 GUID 是以 `mbx` 或前置詞開頭 `skp` 。 `skp`前置詞表示將保留原則套用至使用者信箱中的商務用 Skype 交談。    |
|從全組織的 Microsoft 365 保留原則中排除     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     如果信箱是從全組織的 Microsoft 365 保留原則中排除，則會在 InPlaceHolds 屬性中顯示信箱所排除的保留原則 GUID，並以前置詞加以識別 `-mbx` 。    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
當您執行**Get-Mailbox** Cmdlet 時，如果*InPlaceHolds*屬性是空的，則仍有一個或多個組織範圍的 Microsoft 365 保留原則會套用至信箱。 在 Exchange Online PowerShell 中執行下列命令，以取得整個組織的 Microsoft 365 保留原則的 Guid 清單。

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 屬性中的值太多，而且不是所有的值都顯示出來，您可以執行此 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 命令，將每個 GUID 顯示在不同的行上。

下表說明組織範圍的不同類型，以及如何在您執行**Get-OrganizationConfig** Cmdlet 時，根據*InPlaceHolds*屬性所包含的 guid 來識別每個類型。


|保留類型  |範例值  |描述  |
|---------|---------|---------|
|適用于 Exchange 信箱、Exchange 公用資料夾和團隊聊天的 Microsoft 365 保留原則    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   套用至 Exchange 信箱、Exchange 公用資料夾和1xN 聊天室的組織內的保留原則，都是由以前置詞開頭的 Guid 來識別 `mbx` 。 附注1xN 聊天會儲存在個別聊天參與者的信箱中。      |
|套用至 Microsoft 365 群組和團隊通道郵件的 microsoft 365 保留原則     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    在 Microsoft 小組中套用至 Microsoft 365 群組和通道郵件的全組織保留原則，會由以前置詞開頭的 Guid 來識別 `grp` 。 附注通道郵件會儲存在與 Microsoft 小組相關聯的群組信箱中。     |

如需適用于 Microsoft 小組之保留原則的詳細資訊，請參閱[瞭解 Microsoft 小組的保留原則](retention-policies-teams.md)。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>瞭解保留原則的 InPlaceHolds 值格式

除了前置詞（mbx、skp 或 grp），它會將 InPlaceHolds 屬性中的專案識別為 Microsoft 365 保留原則，此值也會包含一個尾碼，識別針對原則所設定的保留動作類型。 例如，下列範例中的動作尾碼會以粗體反白顯示：

   `skp127d7cf1076947929bf136b7a2a8c36f`**：1**

   `mbx7cfb30345d454ac0a989ab3041051209`**：2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**：3**

下表定義三種可能的保留動作：

|值  |描述  |
|---------|---------|
|**1**     | 表示保留原則已設定為刪除專案。 原則不會保留專案。        |
|**第**    |    表示保留原則設定為保留專案。 原則不會在保留期間到期之後刪除專案。     |
|**個**     |   表示保留原則已設定為保留專案，然後在保留期間到期時加以刪除。      |

如需有關保留動作的詳細資訊，請參閱在[特定時間段內保留內容](create-retention-policies.md#retaining-content-for-a-specific-period-of-time)一節。
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>步驟2：使用 GUID 識別保留

在您取得套用至信箱之保留的 GUID 之後，下一步是使用該 GUID 來識別保留。 下列各節說明如何使用保留 GUID 識別保留（及其他資訊）的名稱。

### <a name="ediscovery-holds"></a>eDiscovery 保留

在安全性 & 規範中心 PowerShell 中執行下列命令，以找出套用至信箱的 eDiscovery 暫止狀態。 使用您在步驟1中識別的 eDiscovery 暫止的 GUID （不包括 UniH 前置詞）。 第一個命令會建立包含保留相關資訊的變數。 在其他命令中使用此變數。 第二個命令會顯示與該保留相關聯的 eDiscovery 案例名稱。 第三個命令會顯示保留的名稱，以及保留所套用的信箱清單。

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

若要連線至安全性 & 合規性中心 PowerShell，請參閱[connect To security & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

### <a name="in-place-holds"></a>就地保留

在 Exchange Online PowerShell 中執行下列命令，以識別套用至信箱的 In-Place 保留。 使用您在步驟1中識別的 In-Place 保留 GUID。 此命令會顯示保留專案的名稱，以及保留所套用的信箱清單。

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

如果 In-Place 保留的 GUID 是以前置詞開頭 `cld` ，請務必在執行先前的命令時包含首碼。

> [!IMPORTANT]
> 當我們繼續以保留信箱內容的不同方式投資時，我們宣佈在 Exchange 系統管理中心（EAC）中封存 In-Place 的退休。 從2020年7月1日起，您將無法在 Exchange Online 中建立新的 In-Place 保留。 不過，您仍然可以管理 EAC 中的 In-Place，或是使用 Exchange Online PowerShell 中的**Set-MailboxSearch** Cmdlet 來管理。 不過，從2020年10月1日開始，您將無法管理 In-Place 保留。 您只會在 EAC 中或使用**Remove-MailboxSearch** Cmdlet 中移除它們。 如需停用 In-Place 保留的詳細資訊，請參閱[舊版 eDiscovery tools 的退休](legacy-ediscovery-retirement.md)。

### <a name="microsoft-365-retention-policies"></a>Microsoft 365 保留原則

在 [安全性 & 規範 PowerShell 中心] 中執行下列命令，以身分識別套用至信箱的 Microsoft 365 保留原則（組織範圍或特定位置）。 使用您在步驟1中所識別的 GUID （不包括 mbx、skp 或 grp 的首碼或動作尾碼）。

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>因為保留標籤已套用至資料夾或專案，因此識別保留的信箱

每當使用者套用設定為保留內容或保留的保留標籤，然後將內容刪除至其信箱中的任何資料夾或專案時， *ComplianceTagHoldApplied*信箱屬性都會設為**True**。 當發生這種情況時，信箱會被視為保留，就像是設定為訴訟暫止或指派給 Microsoft 365 保留原則一樣。 當*ComplianceTagHoldApplied*屬性設定為**True**時，可能會發生下列情況：

- 如果信箱或使用者的使用者帳戶已刪除，則信箱會變成非使用中的[信箱](inactive-mailboxes-in-office-365.md)。
- 您無法停用信箱（主要信箱或封存信箱，如果已啟用）。
- 信箱中的專案可以保留的時間超過預期。 這是因為信箱處於保留狀態，因此不會永久刪除（清除）的專案。

若要查看*ComplianceTagHoldApplied*屬性的值，請在 Exchange Online 中執行下列命令 PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

如需保留標籤的詳細資訊，請參閱[保留標籤](retention.md#retention-labels)。

## <a name="managing-mailboxes-on-delay-hold"></a>管理延遲暫止的信箱

從信箱移除任何類型的保留後，會套用*延遲保留*。 這表示實際刪除保留的時間延遲30天，以防止資料從信箱中永久刪除（清除）。 這可讓系統管理員在移除保留後，搜尋或復原將會清除的信箱專案。 [延遲保留] 會在下一次受管理的資料夾助理處理信箱，並偵測已移除保留時，放在信箱上。 具體說來，當受管理的資料夾助理將下列其中一個信箱屬性設定為**True**時，會將延遲保留套用至信箱：

- **DelayHoldApplied：** 此屬性適用于儲存在使用者信箱中的電子郵件相關內容（由使用 Outlook 和 Outlook 網頁版的人員所產生）。

- **DelayReleaseHoldApplied：** 此屬性適用于以雲端為基礎的內容（由非 Outlook 應用程式（如 Microsoft 團隊、Microsoft Forms 及 Microsoft Yammer）所產生，該內容儲存在使用者的信箱中。 Microsoft app 所產生的雲端資料通常會儲存在使用者信箱中的隱藏資料夾中。
 
 將延遲保留放在信箱上時（如果上述任一屬性設定為**True**），信箱仍會被視為無限期保留期間（如同信箱處於訴訟暫止狀態時）。 30天后，延遲保留會到期，而且 Microsoft 365 會自動嘗試移除延遲保留（透過將 DelayHoldApplied 或 DelayReleaseHoldApplied 屬性設為**False**），以移除 [保留]。 在上述任一屬性設定為**False**之後，在下一次受管理的資料夾助理處理信箱時，會清除標示為待移除的對應專案。

若要查看信箱的 DelayHoldApplied 和 DelayReleaseHoldApplied 屬性的值，請在 Exchange Online PowerShell 中執行下列命令。

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

若要在到期之前移除延遲保留，您可以在 Exchange Online PowerShell 中執行下列命令（或兩者），視您要變更的屬性而定： 
 
```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

或者
 
```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

您必須在 Exchange Online 中指派合法保留角色，才能使用*RemoveDelayHoldApplied*或*RemoveDelayReleaseHoldApplied*參數。 

若要移除非使用中信箱的延遲保留，請在 Exchange Online 中執行下列其中一個命令 PowerShell:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

或者

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> 在上一個命令中指定非使用中信箱的最佳方式是使用其辨別名稱或 Exchange GUID 值。 使用其中一個值可協助避免意外指定錯誤的信箱。 

如需使用這些參數管理延遲保留的詳細資訊，請參閱[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。

在 [延遲保留] 中管理信箱時，請牢記下列事項：

- 如果 DelayHoldApplied 或 DelayReleaseHoldApplied 屬性設定為**True** ，且已刪除信箱（或對應的使用者帳戶），則信箱會變成非使用中的信箱。 這是因為如果其中一個屬性設定為**True**，並刪除保留的信箱導致非使用中的信箱，信箱會被視為保留。 若要刪除信箱，但未將其設為非使用中的信箱，您必須將這兩個屬性設定為**False**。

- 如先前所述，如果 DelayHoldApplied 或 DelayReleaseHoldApplied 屬性設定為**True**，信箱會被視為無限制保留期間的保留期間。 不過，這並不表示保留信箱中的*所有*內容。 它會根據設定為每個屬性的值而定。 例如，假設這兩個屬性都設定為**True** ，因為保留已從信箱中移除。 然後，只會移除套用至非 Outlook 雲端資料的延遲保留（使用*RemoveDelayReleaseHoldApplied*參數）。 在下一次受管理的資料夾助理處理信箱時，會清除標示為待移除的非 Outlook 專案。 因為 DelayHoldApplied 屬性仍設定為**True**，所以不會清除任何標為待移除的 Outlook 專案。 相反的情況也是真：如果 DelayHoldApplied 設定為**False** ，而 DelayReleaseHoldApplied 設定為**true**，則只會清除標示為待移除的 Outlook 專案。

## <a name="next-steps"></a>後續步驟

在您識別套用至信箱的保留後，您可以執行工作，例如變更保留期間、暫時或永久移除保留，或排除 Microsoft 365 保留原則中非使用中的信箱。 如需執行與保留相關之工作的詳細資訊，請參閱下列其中一個主題：

- 在安全性 & 規範中心」中執行[Set-RetentionCompliancePolicy AddExchangeLocationException \<user mailbox> ](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy?view=exchange-ps)命令，PowerShell 從整個組織的 Microsoft 365 保留原則中排除信箱。 這個命令僅可用於*ExchangeLocation*屬性值等於的保留原則 `All` 。

- 在 Exchange Online PowerShell 中執行[Set-Mailbox ExcludeFromOrgHolds \<hold GUID without prefix or suffix> ](https://docs.microsoft.com/powershell/module/exchange/set-mailbox?view=exchange-ps)命令，以從整個組織的 Microsoft 365 保留原則中排除非作用中的信箱。

- [變更非使用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)

- [刪除非使用中的信箱](delete-an-inactive-mailbox.md)

- [刪除雲端式信箱中可復原的項目資料夾中的保留項目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
