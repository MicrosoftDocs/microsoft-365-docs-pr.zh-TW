---
title: 在 Office 365 中刪除非作用中的信箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: 當您不再需要保留 Office 365 非使用中信箱的內容時，您可以移除 [保留]，以永久刪除非使用中的信箱。 移除保留後，非作用中的信箱會標示為待刪除，並且會在處理完後永久刪除。
ms.openlocfilehash: 69628a0e3c39a0a842b2efa58c34b75c7663c728
ms.sourcegitcommit: 7646e2d742d1b2fad085a00200a2a10461dd4bac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978253"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a>在 Office 365 中刪除非作用中的信箱

在前任員工離開您的組織之後，可透過非使用中信箱來保留其電子郵件。 當您不再需要保留非使用中信箱的內容時，您可以移除 [保留]，以永久刪除非使用中的信箱。 此外，可能會在非使用中的信箱上放置多個保留。 例如，非使用中的信箱可能處於訴訟暫止狀態，且有一或多個 In-Place 保留。 此外，Office 365 保留原則（在 Office 365 或 Microsoft 365 中的安全性與合規性中心建立）可能會套用到非使用中的信箱。 您必須移除非使用中信箱的所有保留和 Office 365 保留原則，才能加以刪除。 移除保留和保留原則之後，非作用中的信箱會標示為待刪除，並且會在處理完後永久刪除。
  
> [!IMPORTANT]
> 當我們繼續以保留信箱內容的不同方式投資時，我們宣佈在 Exchange 系統管理中心中封存 In-Place 的退休。 這表示您應該使用訴訟保留和 Office 365 保留原則來建立非使用中的信箱。 從2020年7月1日起，您將無法在 Exchange Online 中建立新的 In-Place 保留。 不過，您仍然可以變更置於非使用中信箱的 In-Place 保留期間。 不過，從2020年10月1日開始，您將無法變更保留期間。 您只能移除 In-Place 保留才能刪除非使用中的信箱。 在移除保留之前，仍會保留位於 In-Place 暫止的現有非作用中信箱。 如需停用 In-Place 保留的詳細資訊，請參閱[舊版 eDiscovery tools 的退休](legacy-ediscovery-retirement.md)。
  
請參閱[詳細資訊](#more-information)一節，以取得從非使用中的信箱移除保留專案之後所發生狀況的描述。
  
## <a name="before-you-begin"></a>開始之前

- 您必須使用 Exchange Online PowerShell 移除非使用中信箱的訴訟暫止狀態。 您無法使用 Exchange 系統管理中心（EAC）。 如需逐步指示，請參閱[Connect To Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。 您可以使用 Exchange Online PowerShell 或 EAC 從非使用中的信箱移除 In-Place 保留。 
    
- 您可以將非使用中信箱的內容複寫到另一個信箱，然後再移除保留和刪除非使用中的信箱。 如需詳細資訊，請參閱[Restore a 非使用中的信箱在 Office 365](restore-an-inactive-mailbox.md)。
    
- 如果您移除非使用中信箱的保留原則或 Office 365 保留原則，且該信箱的虛刪除信箱保留期間已過期，則會永久刪除該信箱。 刪除後，便無法復原。 在您移除保留之前，請確定您不再需要信箱中的內容。 如果您想要重新啟用非使用中的信箱，可以進行復原。 如需詳細資訊，請參閱[復原 Office 365 中的非使用中信箱](recover-an-inactive-mailbox.md)。
    
- 如需非使用中信箱的相關資訊，請參閱[Office 365 中的非使用中信箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>步驟1：識別非使用中信箱上的封存

如先前所述，訴訟暫止、In-Place 保留或 Office 365 保留原則可能會放在非使用中的信箱上。 第一步是在非使用中的信箱上識別保留。
  
執行下列命令，以顯示組織中所有非使用中信箱的保留資訊。
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

**True**的**LitigationHoldEnabled**屬性值表示非使用中的信箱處於訴訟暫止狀態。 如果將 In-Place 定格放在非使用中的信箱上，則保留的 GUID 會顯示為**InPlaceHolds**屬性的值。 例如，下列兩個非使用中信箱的結果會顯示對王 Beebe 進行訴訟暫止，並將兩個 In-Place 保留置於 Pilar Pinilla。 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> 如果有大量的 In-Place 保留在非使用中的信箱上，則不會顯示所有 In-Place 保留 Guid。 您可以執行下列命令來顯示所有 In-Place 保留的 Guid：`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>步驟2：移除非使用中信箱的保留

在您識別在非使用中的信箱上放置的保留類型（以及是否有多個保留）之後，下一步是移除信箱上的保留。 如先前所述，您必須移除所有保留以永久刪除非使用中的信箱。 
  
### <a name="remove-a-litigation-hold"></a>移除訴訟暫止

如先前所述，您必須使用 Windows PowerShell 移除非使用中信箱的訴訟暫止狀態。 您無法使用 EAC。 執行下列命令，以移除訴訟暫止狀態。
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> 識別非使用中信箱的最佳方式是使用其辨別名稱或 Exchange GUID 值。 使用其中一個值可協助避免意外指定錯誤的信箱。 
  
### <a name="remove-in-place-holds"></a>移除 In-Place 保留

 有兩種方式可以移除非使用中信箱的 In-Place 保留： 
  
- **刪除 In-Place 保留物件**如果您想要永久刪除的非作用中信箱是唯一的 In-Place 保留來源信箱，您只需刪除 In-Place 保留物件即可。 
    
    > [!NOTE]
    > 您必須先停用保留，才能刪除 In-Place 保留物件。 如果您嘗試刪除已啟用保留的 In-Place 保留物件，您會收到錯誤訊息。 
  
- **移除非使用中的信箱做為 In-Place 保留的來源信箱**如果您想要保留其他來源信箱以供 In-Place 保留，您可以從來源信箱清單中移除非使用中的信箱，並保留 In-Place 保留物件。 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>使用 EAC 來刪除 In-Place 暫止

1. 如果您知道要刪除的 In-Place 保留名稱，您可以移至下一個步驟。 否則，請執行下列命令，以取得放在您要永久刪除之非使用中信箱上的 In-Place 保留名稱。 使用您在步驟1中取得的 In-Place 保留 GUID [：識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. 在 EAC 中，移至 [**規範管理** \> **] &amp; In-Place eDiscovery 保留**]。
    
3. 選取您要刪除的 In-Place 保留，然後按一下 [**編輯** ![編輯圖示](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)]。
    
4. 在 [ **In-Place eDiscovery &amp;暫**止屬性] 頁面上，按一下 [ **In-Place 保留**]，取消選取 [**將符合搜尋查詢的內容放入保留的所選信箱**] 方塊，然後按一下 [**儲存**]。
    
5. 在 [ **In-Place eDiscovery &amp;保留**] 頁面上，再次選取 In-Place [保留]，然後按一下 [](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)**刪除**![刪除圖示]。
    
6. 在警告中，按一下 **[是]** 以刪除 In-Place 保留。 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>使用 Exchange Online PowerShell 刪除 In-Place 保留

1. 建立包含您要刪除之 In-Place 保留之屬性的變數。 使用您在步驟1中取得的 In-Place 保留 GUID [：識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. 停用 In-Place 暫止的保留。
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. 刪除 In-Place 保留。
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>使用 EAC 從 In-Place 保留中移除非使用中的信箱

1. 如果您知道放在非使用中信箱上的 In-Place 保留名稱，您可以移至下一個步驟。 否則，請執行下列命令，以取得信箱上所放置的 In-Place 暫止名稱。 使用您在步驟1中取得的 In-Place 保留 GUID [：識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. 在 EAC 中，移至 [**規範管理** \> **] &amp; In-Place eDiscovery 保留**]。
    
3. 選取非使用中信箱上的 In-Place 保留，然後按一下 [**編輯** ![編輯圖示](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)]。
    
4. 在 [ **In-Place eDiscovery &amp;暫**止屬性] 頁面上，按一下 [**來源**]。
    
5. 在來源信箱清單中，按一下您要移除之非使用中信箱的名稱，然後按一下 [**移除**![移除圖示](../media/adf01106-cc79-475c-8673-065371c1897b.gif)]。
    
6. 按一下 [**儲存**] 以儲存變更。 隨即顯示一則訊息，指出作業已成功完成。 
    
7. 重複步驟1到6，以移除非使用中信箱上的其他 In-Place 保留。
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>使用 Exchange Online PowerShell 從 In-Place 保留中移除非使用中的信箱

如果 In-Place 保留包含大量的來源信箱，則可能是非使用中的信箱不會列在 EAC 的 [**來源**] 頁面上。 當您編輯 In-Place 保留時，[**來源**] 頁面上最多可顯示3000個信箱。 如果「**來源**」頁面沒有列出非使用中的信箱，您可以使用 Exchange Online PowerShell 將其從 In-Place 保留中移除。 
  
1. 建立包含非使用中信箱上的 In-Place 保留屬性的變數。 使用您在步驟1中取得的 In-Place 保留 GUID [：識別非使用中信箱上的保留](#step-1-identify-the-holds-on-an-inactive-mailbox)。
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. 確認非使用中的信箱已列為 In-Place 保留的來源信箱。 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   **附注：** In-Place 保留的 source 屬性會依其*LegacyExchangeDN*屬性*識別來源信箱*。 由於此屬性唯一識別非使用中的信箱，因此使用 In-Place 保留中的*來源*屬性可協助避免移除錯誤的信箱。 如果兩個信箱具有相同的別名或 SMTP 位址，也有助於避免發生問題。 
   
3. 從變數中的來源信箱清單中移除非使用中的信箱。 請務必使用上一個步驟中命令所傳回的非使用中信箱的**LegacyExchangeDN** 。 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    例如，下列命令會移除 Pilar Pinilla 的非使用中信箱。
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. 確認非使用中信箱已從變數中的來源信箱清單中移除。
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. 使用更新的來源信箱清單（不含非使用中的信箱）修改 In-Place 保留。
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. 確認已從 In-Place 保留的來源信箱清單中移除非使用中信箱。
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>詳細資訊

- **非使用中的信箱是虛刪除信箱的類型。** 在 Exchange Online 中，虛刪除的信箱是已刪除但可在特定保留期間內復原的信箱。 Exchange Online 中的虛刪除信箱保留期間是30天。 這表示信箱可在虛刪除的30天內復原。 30天后，虛刪除的信箱會標示為永久刪除，且無法復原。 
    
- **移除非使用中信箱的保留後，會發生什麼情況？** 信箱會被視為其他虛刪除的信箱，並在30天的虛刪除信箱保留期間到期後標示為永久刪除。 此保留期間會在信箱最初變為非使用中的日期開始。 此日期稱為虛刪除日期，也就是在刪除對應的 Office 365 使用者帳戶，或是使用**Remove-Mailbox** Cmdlet 刪除 Exchange Online 信箱時的日期。 [虛刪除] 日期不是移除保留的日期。 
    
- **移除保留後，是否會永久刪除非作用中的信箱？** 如果非使用中信箱的虛刪除日期超過30天，則在您移除保留後，就不會永久刪除該信箱。 信箱將會標示為永久刪除，而且會在下一次處理時刪除。 
    
- **虛刪除信箱保留期間對非使用中信箱的影響如何？** 如果非使用中信箱的虛刪除日期超過超過30天，則在刪除保留的日期之前，會將信箱標記為永久刪除。 不過，如果非使用中的信箱在過去30天內有虛刪除的日期，而且您移除保留，您可以將信箱復原，直到虛刪除的信箱保留期間到期為止。 如需詳細資訊，請參閱[刪除或還原 Exchange Online 中的使用者信箱](https://go.microsoft.com/fwlink/?linkid=856835)。 當虛刪除的信箱保留期間到期後，您必須遵循復原非使用中信箱的程式。 如需詳細資訊，請參閱[復原 Office 365 中的非使用中信箱](recover-an-inactive-mailbox.md)。
    
- **移除保留後，如何顯示非使用中信箱的相關資訊？** 在移除保留，且非作用中的信箱回復回虛刪除信箱之後，就不會使用*InactiveMailboxOnly*參數搭配**Get-Mailbox** Cmdlet 來傳回。 不過，您可以使用**Get-Mailbox-SoftDeletedMailbox**命令來顯示信箱的相關資訊。 例如： 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  在上述範例中， *WhenSoftDeleted*屬性會識別虛刪除的日期，在此範例中為2014年10月30日。 如果此虛刪除信箱先前為已移除保留的非使用中信箱，則會在*WhenSoftDeleted*屬性值後的30天內永久刪除該信箱。 在此情況下，信箱會在2014年11月30日之後永久刪除。

