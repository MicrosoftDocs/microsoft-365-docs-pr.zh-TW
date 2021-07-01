---
title: 增加保留信箱的可復原項目配額
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 啟用封存信箱，並開啟自動展開的封存，以增加 Microsoft 365 中信箱的 [可復原的專案] 資料夾的大小。
ms.openlocfilehash: 47227e066f922a9e4b8bccedaa9573c001194836
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226584"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>增加保留信箱的可復原項目配額

自動套用至 Exchange Online 中新信箱的預設 Exchange 保留原則（名為「*預設 MRM 原則*」）包含一個名為「可復原的專案」的保留標記，該保留標記會移至封存。 這項保留標記會將專案從使用者主要信箱的 [可復原的專案] 資料夾移至使用者封存信箱中的 [可復原的專案] 資料夾之後，在14天的保留期間到期的專案。 為做到這一點，必須啟用使用者的封存信箱。 如果未啟用封存信箱，則不會採取任何動作，這表示在14天保留期間到期後，信箱的 [可復原的專案] 資料夾中的專案不會移至封存信箱。 因為保留信箱中未刪除任何專案，可能會超出 [可復原的專案] 資料夾的儲存配額，尤其是在未啟用使用者的封存信箱的情況下。

為了協助減少超過此限制的機率，[可復原的專案] 資料夾的儲存配額會自動從 30 GB 增加為 100 GB，當您在 Exchange Online 中的信箱上設定保留。 如果已啟用封存信箱，則封存信箱中 [可復原的專案] 資料夾的儲存配額也會從 30 GB 增加為 100 GB。 如果啟用 Exchange Online 中的自動擴充封存功能，使用者封存中 [可復原的專案] 資料夾的儲存配額將不受限制。

 下表摘要說明 [可復原的專案] 資料夾的儲存配額。

|**[可復原的專案] 資料夾的位置**|**未保留信箱**|**保留信箱**|
|:-----|:-----|:-----|
|主要信箱  <br/> |30 GB  <br/> |100 GB  <br/> |
|封存信箱<sup>\*</sup> <br/> |無限制  <br/> |無限制  <br/> |
|**[可復原的專案] 資料夾的儲存配額總計** <br/> |無限制  <br/> |無限制  <br/> |

> [!NOTE]
> <sup>\*</sup>使用 Exchange Online (方案 2) 授權的使用者，封存信箱的初始儲存配額為 100 GB。 不過，當已開啟信箱的自動展開封存功能時，封存信箱和 [可復原的專案] 資料夾的儲存配額會增至 110 GB。 必要時會布建額外的封存儲存空間，這會產生無限的封存儲存量。 如需自動展開封存的詳細資訊，請參閱[Office 365 中無限制的](unlimited-archiving.md)封存。

當信箱的主要信箱中 [可復原的專案] 資料夾的儲存配額接近達到限制時，您可以執行下列動作：

- **啟用封存信箱，並開啟自動展開的封存。** 您可以為 [可復原的專案] 資料夾啟用無限的儲存容量，只要啟用封存信箱，然後在 Exchange Online 中開啟自動展開的封存功能即可。 這會導致主要信箱中 [可復原的專案] 資料夾的 110 GB 和使用者封存中 [可復原的專案] 資料夾的儲存容量量不限。 請參閱操作方法：[在安全性 & 規範中心啟用封存信箱](enable-archive-mailboxes.md)，並[在 Office 365 中啟用無限](enable-unlimited-archiving.md)封存。

    > [!NOTE]
    > 當您為接近超過 [可復原的專案] 資料夾的儲存配額的信箱啟用封存後，您可能會想要執行受管理的資料夾助理以手動觸發該信箱的處理常式，使到期的專案移至封存信箱中的 [可復原的專案] 資料夾。 如需指示，請參閱 [步驟 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 。 請注意，使用者信箱中的其他專案可能會移至新的封存信箱。 請考慮告知使用者啟用封存信箱之後可能會發生這種情況。

- **為保留信箱建立自訂的 Exchange 保留原則。** 除了為訴訟暫止或 In-Place 暫止啟用信箱的封存信箱和自動展開封存之外，您還可以為保留信箱建立自訂的 Exchange 保留原則。 這可讓您將保留原則套用至保留的信箱，與套用至未保留信箱的預設 MRM 原則不同，並可讓您套用為保留信箱所設計的保留標記。 這包括為 [可復原的專案] 資料夾建立新的保留標記。

本主題的其餘部分將說明為保留信箱建立自訂 Exchange 保留原則的逐步程式。

[步驟1：為 [可復原的專案] 資料夾建立自訂保留標記](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[步驟2：為保留信箱建立新的 Exchange 保留原則](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[步驟3：將新的 Exchange 保留原則套用至保留信箱](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[ (選用) 步驟4：執行受管理的資料夾助理以套用新的保留設定](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)

## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>步驟1：為 [可復原的專案] 資料夾建立自訂保留標記

第一步是針對 [可復原的專案] 資料夾，建立稱為保留原則標記或 RPT) 的自訂保留標記 (。 如先前所述，此 RPT 會將專案從使用者主要信箱的 [可復原的專案] 資料夾移至使用者封存信箱中的 [可復原的專案] 資料夾。 您必須使用 PowerShell 為 [可復原的專案] 資料夾建立 RPT。 您無法使用 Exchange 系統管理中心 (EAC) 。

1. [使用遠端 PowerShell 連線到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)

2. 執行下列命令，為 [可復原的專案] 資料夾建立新的 RPT：

    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    例如，下列命令會針對名為「暫止的信箱」的 [可復原的專案30天] 的 [可復原的專案] 資料夾建立 RPT，保留期間為30天。 這表示專案已在 [可復原的專案] 資料夾中的30天之後，它會移至使用者的封存信箱中的 [可復原的專案] 資料夾。

    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > 建議 [可復原的專案 RPT] 的  _AgeLimitForRetention_ 參數) 所定義的保留期間 (，與 RPT 將套用到之信箱的已刪除專案保留期間相同。 這可讓使用者在將刪除的專案移至封存信箱之前，先將其整個刪除的專案保留期間復原。 在上一個範例中，保留期間會設定為30天，但前提是信箱的刪除專案保留期間也是30天。 Exchange Online 信箱預設會將刪除的項目保留 14 天。 不過，您可以將此設定變更為最多30天。 如需詳細資訊，請參閱[變更 Exchange Online 中信箱的已刪除專案保留期間](https://www.microsoft.com/?ref=go)。

## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a>步驟2：為保留信箱建立新的 Exchange 保留原則

下一步是建立新的保留原則並新增保留標記，包括您在步驟1中建立的可復原專案 RPT。 在下一個步驟中，此新原則會套用至信箱保留。

在您建立新的保留原則之前，請先確定您想要新增的其他保留標記。 如需新增至預設 MRM 原則的保留標記清單，以及建立新保留標記的相關資訊，請參閱下列各項：

- [Exchange Online 中的預設保留原則](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- [支援保留原則標記的預設資料夾](/exchange/security-and-compliance/messaging-records-management/default-folders)

- [ [建立保留原則](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) ] 主題中的「建立保留標記」一節。

您可以使用 EAC 或 Exchange Online PowerShell 建立保留原則。

### <a name="use-the-eac-to-create-a-retention-policy"></a>使用 EAC 建立保留原則

1. 在 EAC 中，移至 [ **規範管理**] [ \> **保留原則**]，然後按一下 [ **新增**] [新增] ![ 圖示 ](../media/ITPro-EAC-AddIcon.gif) 。

2. 在 [ **新增保留原則** ] 頁面的 [ **名稱**] 下，輸入描述保留原則目的的名稱，然後按一下 [是]。例如， **保留信箱的 MRM 原則**。

3. 在 [ **保留標記**] 底下，按一下 [ **新增**] ![ 圖示 ](../media/ITPro-EAC-AddIcon.gif) 。

4. 在 [保留標記] 清單中，選取您在步驟1中建立的 [可復原的專案 RPT]，然後按一下 [ **新增**]。

    ![選取自訂的 [可復原的項目] 保留標記](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)

5. 選取要新增至保留原則的其他保留標記。 例如，您可能想要加入預設 MRM 原則中所包含的相同標記。

6. 完成新增保留標記之後，請按一下 **[確定]**。

7. 按一下 [ **儲存** ] 以建立新的保留原則。

    請注意，連結至保留原則的保留標記會顯示在詳細資料窗格中。

    ![連結到保留原則的保留標記，會顯示在詳細資料窗格中](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)

### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>使用 Exchange Online PowerShell 建立保留原則

執行下列命令，為保留信箱建立新的保留原則。

```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

例如，下列命令會建立上圖所顯示的保留原則及連結的保留標記。

```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a>步驟3：將新的 Exchange 保留原則套用至保留信箱

最後一個步驟是將您在步驟2中建立的新保留原則套用至組織中的信箱保留原則。 您可以使用 EAC 或 Exchange Online PowerShell 將保留原則套用至單一信箱或多個信箱。

### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>使用 EAC 來套用新的保留原則

1. 移至 **[** 收件者] [  >  **信箱**]。

2. 在清單視圖中，選取您要套用保留原則的信箱，然後按一下 [ **編輯** ![ 編輯圖示] ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。

3. 在 [ **使用者信箱** ] 頁面上，按一下 [ **信箱功能**]。

4. 在 [ **保留原則**] 底下，選取您在步驟2中建立的保留原則，然後按一下 [ **儲存**]。

您也可以使用 EAC 將保留原則套用至多個信箱。

1. 移至 **[** 收件者] [  >  **信箱**]。

2. 在清單檢視中，使用 Shift 鍵或 Ctrl 鍵來選取多個信箱。

3. 在詳細資料窗格中，按一下 [其他選項]。

4. 在 [保留原則] 下方，按一下 [更新]。

5. 在 [ **大量指派保留原則** ] 頁面上，選取您在步驟2中建立的保留原則，然後按一下 [ **儲存**]。

### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>使用 Exchange Online PowerShell 套用新的保留原則

您可以使用 Exchange Online PowerShell 將新的保留原則套用至單一信箱。 不過 PowerShell 的實際威力在於，您可以使用它來快速識別您組織中的所有信箱，不論是訴訟暫止或 In-Place 保留，然後在單一命令中將新的保留原則套用至保留的所有信箱。 以下是一些使用 Exchange PowerShell 將保留原則套用至一或多個信箱的範例。 所有範例會套用在步驟2中建立的保留原則。

此範例會將新的保留原則套用至 Pilar Pinilla 的信箱。

```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

本範例會將新的保留原則套用至組織中的所有處於訴訟暫止狀態的信箱。

```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

本範例會將新的保留原則套用至組織中 In-Place 保留的所有信箱。

```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

您可以使用 **Get-Mailbox** Cmdlet 來驗證是否已套用新的保留原則。

以下是一些範例，以驗證先前範例中的命令是否已將「保留信箱的 MRM 原則」保留原則套用至「In-Place 暫止」上的「訴訟暫止」和信箱上的信箱。

```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a> (選用) 步驟4：執行受管理的資料夾助理以套用新的保留設定

將新的 Exchange 保留原則套用至保留信箱之後，最多可能需要7天的 Exchange Online 中的受管理的資料夾助理使用新保留原則中的設定來處理這些信箱。 您可以使用 **Start-ManagedFolderAssistant** Cmdlet 手動觸發助理，以處理套用新保留原則的信箱，而不是等待受管理的資料夾助理執行。

執行下列命令，以啟動 Pilar Pinilla 信箱的受管理的資料夾助理。

```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

執行下列命令，以啟動保留所有信箱的受管理的資料夾助理。

```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>其他相關資訊

- 在您啟用使用者的封存信箱之後，請考慮告知使用者其信箱中的其他專案 (不只是「可復原的專案」資料夾中的專案) 可能會移至封存信箱。 這是因為指派給 Exchange Online 信箱的預設 MRM 原則所包含的保留標記 (預設的2年移至封存) 在專案傳遞至信箱或使用者建立的日期之後的兩年，將專案移至封存信箱。 如需詳細資訊，請參閱[Exchange Online 中的預設保留原則](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- 啟用使用者的封存信箱之後，您可能也會告訴使用者他們可以在其封存信箱的 [可復原的專案] 資料夾中復原已刪除的郵件。 在 Outlook 中，您可以選取封存信箱中的 [**刪除的郵件**] 資料夾，然後按一下 [從 [**首頁**] 索引標籤上的 [**從伺服器復原刪除的郵件**] 來執行此動作如需復原已刪除專案的詳細資訊，請參閱 [在 Windows 中復原已刪除的郵件 Outlook](https://go.microsoft.com/fwlink/p/?LinkId=624829)。
