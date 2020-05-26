---
title: 刪除雲端信箱中的專案保留 [可復原的專案] 資料夾-系統管理說明
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 針對系統管理員：刪除使用者的 [可復原的專案] 資料夾中的專案，即使該信箱位於法律封存中也是一樣。 這是一種有效的方式，可刪除意外濺入 Microsoft 365 的資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ce363d558e5ce1de600ccf34863cc6524841e78b
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352178"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>刪除雲端式信箱的 [可復原的專案] 資料夾中的專案，保留系統管理員協助

Exchange Online 信箱的 [可復原的專案] 資料夾存在，可防止意外或惡意刪除。 它也用來儲存由規範功能（例如保留和 eDiscovery 搜尋）所保留及存取的專案。 不過，在某些情況下，組織可能會有不慎保留在必須刪除的 [可復原的專案] 資料夾中的資料。 例如，使用者可能會在不知情的情況下傳送或轉寄包含機密資訊的電子郵件，或是可能具有嚴重業務結果的資訊。 即使永久刪除郵件，該郵件仍可無限期保留，因為已對信箱進行合法保留。 此案例稱為資料外泄，因為資料已意外濺入 Office 365。 在這些情況下，您可以針對 Exchange Online 信箱刪除使用者的 [可復原的專案] 資料夾中的專案，即使該信箱是以 Office 365 中的其中一個不同的保留功能來保留。 這些保留類型包括在 Office 365 或 Microsoft 365 的安全性與合規性中心建立的訴訟封存、In-Place 保留、eDiscovery 保留和保留原則。
  
 本文說明如何從處於保留狀態的雲端式信箱的 [可復原的專案] 資料夾中刪除專案。 此套裝程式含停用對信箱的存取權並停用單一專案復原，停用受管理的資料夾助理處理信箱，暫時移除保留，從 [可復原的專案] 資料夾中刪除專案，然後將信箱還原為先前的設定。 處理常式如下： 
  
[步驟1：收集信箱的相關資訊](#step-1-collect-information-about-the-mailbox)

[步驟2：準備信箱](#step-2-prepare-the-mailbox)

[步驟3：移除信箱中的所有保留](#step-3-remove-all-holds-from-the-mailbox)

[步驟4：移除信箱的延遲保留](#step-4-remove-the-delay-hold-from-the-mailbox)

[步驟5：刪除 [可復原的專案] 資料夾中的專案](#step-5-delete-items-in-the-recoverable-items-folder)

[步驟6：將信箱還原為先前的狀態](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> 本文所述的程式會導致從 Exchange Online 信箱永久刪除（清除）的資料。 這表示您從 [可復原的專案] 資料夾中刪除的郵件無法復原，也不會供法律查詢或其他法規遵從性之用。 如果您想要從保留的信箱刪除郵件，做為訴訟暫止的一部分、In-Place 保留、eDiscovery 保留或在安全性與規範中心建立的保留原則，請在移除保留之前，先與您的記錄管理或法律部門核實。 您的組織可能具有定義信箱保留或資料外泄事件是否優先的原則。 
  
## <a name="before-you-begin"></a>開始之前

- 若要建立和執行內容搜尋，您必須是「eDiscovery 管理員」角色群組的成員，或者獲指派「符合性搜尋」管理角色。 若要刪除郵件，您必須是「組織管理」角色群組的成員，或者獲指派「搜尋及清除」管理角色。 如需新增使用者至角色群組的詳細資訊，請參閱[在安全性與合規性中心中指派電子文件探索權限](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)。

- 非使用中的信箱不支援本文所述的程式。 這是因為在您移除停用信箱之後，您無法將保留（或保留原則）重新套用至非使用中的信箱。 當您從非使用中的信箱移除保留時，它會變更為一般虛刪除信箱，且會在受管理的資料夾助理處理之後，從組織中永久刪除。

- 您無法對指派給已以保留鎖定鎖定之保留原則的信箱執行此程式。 這是因為保留鎖定可防止您從保留原則移除或排除信箱，以及停用信箱上的受管理的資料夾助理。 如需有關封鎖保留原則的詳細資訊，請參閱[使用保留鎖定以遵守法規需求](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)。

- 如果信箱未處於保留狀態（或沒有啟用單一專案復原），您可以從 [可復原的專案] 資料夾中刪除專案。 如需如何執行此動作的詳細資訊，請參閱[搜尋並刪除組織中的電子郵件訊息](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)。
  
## <a name="step-1-collect-information-about-the-mailbox"></a>步驟1：收集信箱的相關資訊

此第一步是從目標信箱收集會影響此程式的選取屬性。 請務必記下這些設定或將其儲存至文字檔，因為您會在從 [可復原的專案] 資料夾中刪除專案之後，變更部分的屬性，然後再回復為步驟6中的原始值。 以下是您需要收集的信箱屬性清單。
  
- *SingleItemRecoveryEnabled*和*RetainDeletedItemsFor*。 如有必要，您會停用單一復原，並增加步驟3中已刪除的郵件保留期間。 

- *LitigationHoldEnabled*和*InPlaceHolds*。 您必須識別放在信箱上的所有保留，以便您可以在步驟3中暫時移除。 請參閱[詳細資訊](#more-information)一節，以取得如何識別可能放置在信箱上之類型保留的秘訣。 

此外，您還需要取得信箱用戶端存取設定，這樣您就可以暫時停用這些設定，讓擁有者（或其他使用者）在此程式中無法存取信箱。 最後，您可以取得 [可復原的專案] 資料夾中的目前大小及專案數目。 在步驟5中刪除 [可復原的專案] 資料夾中的專案之後，您將使用此資訊來確認專案已移除。
  
1. [連線至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。 請務必使用使用者名稱和密碼，以在 Exchange Online 中指派適當的管理角色的系統管理員帳戶。 
    
2. 執行下列命令，以取得有關單一專案復原和刪除專案保留期間的資訊。

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   如果已啟用單一專案復原，您必須在步驟2中停用此修復。 如果刪除的專案保留期間未設定為30天（Exchange Online 中的最大值），則您可以在步驟2中增加。 
    
3. 執行下列命令以取得信箱的信箱訪問設定。 
    
    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   您將會停用步驟2中的所有 access 方法。
    
4. 執行下列命令，以取得有關信箱所套用之保留和保留原則的資訊。
    
    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > 如果*InPlaceHolds*屬性中的值太多，而且不是所有的值都顯示出來，您可以執行此 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 命令，以個別行顯示每一個值。 
  
5. 執行下列命令，以取得任何整個組織保留原則的資訊。 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   
   如果您的組織有任何組織範圍的保留原則，您必須在步驟3中從這些原則中排除信箱。

   > [!TIP]
    > 如果*InPlaceHolds*屬性中的值太多，而且不是所有的值都顯示出來，您可以執行此 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 命令，以個別行顯示每一個值。 
  
6. 執行下列命令，以取得使用者主要信箱中 [可復原的專案] 資料夾中的資料夾及子資料夾中目前的專案大小及總專案數目。 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   如果已啟用使用者的封存信箱，請執行下列命令，以取得封存信箱中 [可復原的專案] 資料夾中的資料夾與子資料夾中的專案大小和總數。 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   當您在步驟5中刪除專案時，您可以選擇刪除或不刪除使用者主要封存信箱中 [可復原的專案] 資料夾中的專案。 如果為信箱啟用自動擴充封存，則不會刪除輔助封存信箱中的專案。
  
## <a name="step-2-prepare-the-mailbox"></a>步驟2：準備信箱

收集和儲存信箱的相關資訊之後，下一步是執行下列工作來準備信箱： 
  
- **停用用戶端對信箱的存取權**，讓信箱擁有者無法存取其信箱，並在此程式期間對信箱資料進行任何變更。 
    
- 將**刪除的專案保留期間增加**至30天（Exchange Online 中的最大值），這樣就不會從 [可復原的專案] 資料夾清除專案，您可以在步驟5中刪除專案。 
    
- **停用單一專案**復原，使其在您從步驟5的 [可復原的專案] 資料夾中刪除之後，不會保留專案（在刪除的專案保留期間內）。 
    
- **停用受管理的資料夾助理**，使其不處理信箱，並保留您在步驟5中刪除的專案。 
    
在 Exchange Online PowerShell 中執行下列步驟。
  
1. 執行下列命令，以停用所有用戶端存取信箱。 命令語法假設所有的用戶端存取方法已在信箱上啟用。

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > 可能需要長達60分鐘的時間，才能停用所有用戶端存取方法至信箱。 請注意，停用這些存取方法不會中斷其目前已登入的信箱擁有者的連線。 如果擁有者未登入，當這些存取方法停用之後，他們將無法存取其信箱。 
  
2. 執行下列命令，以將刪除的專案保留期間增加30天的上限。 這會假設目前的設定小於30天。 

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 執行下列命令以停用單一專案復原。
    
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > 最多可能需要60分鐘，以停用單一專案復原。 在此期間過後，請勿刪除 [可復原的專案] 資料夾中的專案。 
  
4. 執行下列命令，以防止受管理的資料夾助理處理信箱。 如先前所述，只有具有保留鎖定原則的保留原則未套用至信箱時，您才可以停用受管理的資料夾助理。 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>步驟3：移除信箱中的所有保留

您可以從 [可復原的專案] 資料夾中刪除專案的最後一個步驟，就是移除放置在信箱上的所有保留（您在步驟1中所識別）。 所有保留都必須移除，這樣在您從 [可復原的專案] 資料夾中刪除之後，就不會保留專案。 下列各節包含在信箱上移除不同類型保留的相關資訊。 請參閱[詳細資訊](#more-information)一節，以取得如何識別可能放置在信箱上之類型保留的秘訣。 如需詳細資訊，請參閱 how [to 識別位於 Exchange Online 信箱的保留類型](identify-a-hold-on-an-exchange-online-mailbox.md)。
  
> [!CAUTION]
> 如先前所述，在從信箱移除保留之前，請先與您的記錄管理或法律部門聯繫。 
  
 ### <a name="litigation-hold"></a>訴訟暫止
  
在 Exchange Online PowerShell 中執行下列命令，以從信箱中移除訴訟暫止狀態。

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> 類似于停用用戶端存取方法和單一專案復原，可能需要長達60分鐘的時間來移除訴訟暫止狀態。 在此期間過後，請勿刪除 [可復原的專案] 資料夾中的專案。 
  
 ### <a name="in-place-hold"></a>原有範圍暫止
  
在 Exchange Online PowerShell 中執行下列命令，以識別放在信箱上的 In-Place 保留。 使用您在步驟1中識別的 In-Place 保留 GUID。 

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

在您識別 In-Place 保留後，您可以使用 Exchange 系統管理中心（EAC）或 Exchange Online PowerShell 從保留中移除信箱。 如需詳細資訊，請參閱[建立或移除 In-Place 保留](https://go.microsoft.com/fwlink/?linkid=852668)。
  
 ### <a name="retention-policies-applied-to-specific-mailboxes"></a>套用至特定信箱的保留原則
  
在[安全性 & 規範中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中執行下列命令，以識別套用至信箱的保留原則。 使用 `mbx` `skp` 您在步驟1中所識別之保留原則的 GUID （不包括或前置詞）。 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

在您識別保留原則之後，請移至 [安全性 & 規範中心] 中的 [**資訊管理** \> **保留**] 頁面，編輯您在上一個步驟中識別的保留原則，然後從保留原則中所包含的收件者清單中移除信箱。 
  
 ### <a name="organization-wide-retention-policies"></a>全組織保留原則
  
整個組織內和 Exchange 通用保留原則會套用至組織中的每個信箱。 當您在步驟1中執行**Get-OrganizationConfig** Cmdlet 時，會在組織層級（非信箱層級）套用這些功能。 在[安全性 & 規範中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中執行下列命令，以找出整個組織的保留原則。 `mbx`針對您在步驟1中識別的全組織保留原則，使用 GUID （不包括前置詞）。 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

在您識別整個組織的保留原則之後，請移至安全性 & 規範中心內的「**資訊管理**」 \> **保留**頁面，編輯您在上一個步驟中識別的每個整個組織保留原則，並將信箱新增至排除的收件者清單。 這樣做會將使用者的信箱從保留原則中移除。 

### <a name="retention-labels"></a>保留標籤

每當使用者套用設定為保留內容或保留的標籤，然後將內容刪除至其信箱中的任何資料夾或專案時， *ComplianceTagHoldApplied*信箱屬性都會設為**True**。 發生這種情況時，信箱會被視為保留，就像是設定為訴訟暫止或指派給保留原則一樣。

若要查看*ComplianceTagHoldApplied*屬性的值，請在 Exchange Online 中執行下列命令 PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

在您識別信箱已保留狀態，因為保留標籤套用到資料夾或專案，您可以使用安全性與合規性中心的內容搜尋工具，利用 New-compliancetag 搜尋條件來搜尋已標示的專案。 如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)中的「搜尋條件」一節。

如需標籤的詳細資訊，請參閱[標籤概觀](labels.md)。

 ### <a name="ediscovery-holds"></a>eDiscovery 保留
  
在[安全性 & 規範中心」 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)中執行下列命令，識別與套用至信箱的 ediscovery 案例（稱為*ediscovery 保留*）相關聯的保留。 使用 `UniH` 您在步驟1中識別的 eDiscovery 暫止的 GUID （不包括前置詞）。 第二個命令會顯示保留所關聯的 eDiscovery 案例名稱;第三個命令會顯示保留的名稱。 
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

在您識別 eDiscovery 案例名稱和保留後，請移至規範中心的 [ **ediscovery** \> **ediscovery** ] 頁面，開啟案例，然後從保留中移除信箱。 如需識別 eDiscovery 保留的詳細資訊，請參閱[如何識別位於 Exchange Online 信箱之保留類型](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)的「eDiscovery 保留」一節。
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>步驟4：移除信箱的延遲保留

從信箱移除任何類型的保留後， *DelayHoldApplied*或*DelayReleaseHoldApplied*信箱屬性的值會設為**True**。 這會在下一次受管理的資料夾助理處理信箱，並偵測已移除保留。 這稱為*延遲保留*，表示實際移除保留延遲30天，以防止資料從信箱中永久刪除。 （延遲保留的目的是讓系統管理員有機會搜尋或復原在移除保留後將會清除的信箱專案。） 將延遲保留放在信箱上時，信箱仍會被視為無限期的保留狀態，就像當信箱處於訴訟暫止狀態。 30天后，延遲保留會到期，而且 Microsoft 365 會自動嘗試移除延遲保留（透過將*DelayHoldApplied*或*DelayReleaseHoldApplied*屬性設為**False**），以移除 [保留]。 如需有關延遲保留的詳細資訊，請參閱[如何識別位於 Exchange Online 信箱之保留類型](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)的「管理延遲暫止的信箱」一節。

在您可以刪除步驟5中的專案之前，您必須移除信箱的延遲保留。 首先，在 Exchange Online 中執行下列命令，判斷是否要將延遲保留套用至信箱 PowerShell:

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

如果*DelayHoldApplied*或*DelayReleaseHoldApplied*屬性的值設為**False**，則不會在信箱上設定延遲保留。 您可以移至步驟5並刪除 [可復原的專案] 資料夾中的專案。

如果*DelayHoldApplied*或*DelayReleaseHoldApplied*屬性的值設為**True**，請執行下列其中一個命令，以移除延遲保留：

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

或

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

您必須在 Exchange Online 中指派合法保留角色，才能使用*RemoveDelayHoldApplied*或*RemoveDelayReleaseHoldApplied*參數。

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>步驟5：刪除 [可復原的專案] 資料夾中的專案

現在，您已準備好使用 [安全性 & 規範中心] 中的[New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)和[New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) Cmdlet 來實際刪除 [可復原的專案] 資料夾中的專案。 

若要執行此動作，請參閱[搜尋並刪除電子郵件訊息](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)。

### <a name="verify-that-items-were-deleted"></a>確認已刪除專案

若要確認您是否已成功刪除信箱的 [可復原的專案] 資料夾中的專案，請使用**Get-MailboxFolderStatistics** Cmdlet In Exchange Online PowerShell 以檢查 [可復原的專案] 資料夾中的專案大小和數目。 您可以將這些統計資料與您在步驟1中收集的統計資料進行比較。 
  
在中執行下列命令，以取得使用者主要信箱中 [可復原的專案] 資料夾中的資料夾與子資料夾中目前的專案大小及總專案數目。 
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

執行下列命令，以取得使用者封存信箱中 [可復原的專案] 資料夾中的資料夾及子資料夾中的專案大小和總數。 

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>步驟6：將信箱還原為先前的狀態

最後一個步驟是將信箱還原回先前的設定。 這表示重設您在步驟2中變更的屬性，並重新應用您在步驟3中移除的保留。 這包括：
  
- 將刪除的專案保留期間變更回其先前的值。 或者，您可以將此集保留為30天，這是 Exchange Online 中的最大值。
    
- 重新啟用單一專案復原。
    
- 重新啟用用戶端存取方法，讓擁有者可以存取其信箱。
    
- 重新應用您移除的保留和保留原則。
    
- 重新啟用受管理的資料夾助理以處理信箱。
    
> [!IMPORTANT]
> 建議您在重新啟用受管理的資料夾助理以處理信箱之前，先等候24小時後再重新套用保留原則（及驗證是否已到位）。 
  
在 Exchange Online PowerShell 中執行下列步驟（以指定的順序）。
  
1. 執行下列命令，將刪除的專案保留期間變更回其原始值。 這會假設上一個設定小於30天;例如，14天。 
    
    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. 執行下列命令，以重新啟用單一專案復原。
   
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. 執行下列命令，以重新啟用所有用戶端存取方法至信箱。
    
    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. 重新套用您在步驟3中移除的保留。 根據保留的類型，使用下列其中一個程式。
    
    **訴訟暫止**
    
    執行下列命令，以重新啟用信箱的訴訟暫止。
    
    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **原有範圍暫止**
    
    使用 EAC （或 Exchange Online PowerShell）將信箱重新加入 In-Place 保留。 
    
    **套用至特定信箱的保留原則**
    
    使用安全性 & 規範中心，將信箱新增回保留原則。 移至 [安全性 & 規範中心] 中的 [**資訊**控管 \> **保留**] 頁面，編輯保留原則，並將信箱重新新增至套用保留原則的收件者清單。 
    
    **全組織保留原則**
    
    如果您已移除整個組織或 Exchange 範圍的保留原則，請從原則中排除它，然後使用安全性 & 合規性中心，從排除的使用者清單中移除信箱。 移至 [安全性 & 規範中心] 中的 [**資訊**控管 \> **保留**] 頁面，編輯整個組織的保留原則，然後從排除的收件者清單中移除信箱。 這樣做會將保留原則重新套用至使用者的信箱。 
    
    **eDiscovery 案例保留**
    
    使用安全性 & 合規性中心，將信箱回復與 eDiscovery 案例相關聯的保留。 移至 [ **ediscovery** \> **ediscovery** ] 頁面，開啟案例，然後將信箱新增回保留。 
    
5. 執行下列命令，讓受管理的資料夾助理再次處理信箱。 如先前所述，建議您在重新啟用受管理的資料夾助理之前，先將保留原則重新套用保留或保留原則（並驗證已到位）後等候24小時。 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. 若要驗證信箱是否已回復回先前的設定，您可以執行下列命令，並將設定與您在步驟1中收集的設定進行比較。

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>詳細資訊

以下表格說明當您執行**Get-Mailbox**或**Get-OrganizationConfig** Cmdlet 時，如何根據*InPlaceHolds*屬性中的值來識別不同的保留類型。 如需詳細資訊，請參閱 how [to 識別位於 Exchange Online 信箱的保留類型](identify-a-hold-on-an-exchange-online-mailbox.md)。

如先前所述，您必須先移除信箱的所有保留和保留原則，才能成功刪除 [可復原的專案] 資料夾中的專案。 
  
|**保留類型**|**範例值**|**如何識別保留**|
|:-----|:-----|:-----|
|訴訟暫止  <br/> | `True` <br/> |*LitigationHoldEnabled*屬性設定為 `True` 。  <br/> |
|原有範圍暫止  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds*屬性包含放在信箱上的 IN-PLACE 保留 GUID。 您可以告訴這是 In-Place 保留，因為 GUID 不是以前置詞開頭。  <br/> 您可以使用 `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Exchange Online PowerShell 中的命令，取得信箱上 In-Place 保留的相關資訊。  <br/> |
| 套用至特定信箱之安全性 & 規範中心內的保留原則  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> 或  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |當您執行**Get-Mailbox** Cmdlet 時， *InPlaceHolds*屬性也會包含套用至信箱的保留原則的 guid。 您可以識別保留原則，因為 GUID 會以前置詞開頭 `mbx` 。 如果保留原則的 GUID 是以前置詞開頭 `skp` ，表示保留原則套用至商務用 Skype 交談。  <br/> 若要識別套用至信箱的保留原則，請在安全性 & 規範中心內執行下列命令 PowerShell: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>`mbx` `skp` 當您執行此命令時，請務必移除或首碼。  <br/> |
|安全性 & 規範中心內的整個組織保留原則  <br/> |無值  <br/> 或  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`（表示信箱已從整個組織的原則中排除）  <br/> |即使當您執行**Get-Mailbox** Cmdlet 時， *InPlaceHolds*屬性是空的，仍然有一個或多個組織範圍的保留原則會套用至信箱。  <br/> 若要確認這一點，您可以 `Get-OrganizationConfig | FL InPlaceHolds` 在 Exchange Online PowerShell 中執行命令，以取得整個組織保留原則的 guid 清單。 套用至 Exchange 信箱之全組織保留原則的 GUID 會以前置詞開始 `mbx` ; 例如， `mbxa3056bb15562480fadb46ce523ff7b02` 。  <br/> 若要識別套用至信箱的全組織保留原則，請在安全性 & 規範中心內執行下列命令 PowerShell: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>如果信箱已從整個組織的保留原則中排除，當您執行**Get-Mailbox** Cmdlet 時，保留原則的 GUID 會顯示在使用者信箱的*InPlaceHolds*屬性中;它會以前置詞識別 `-mbx` ; 例如，`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|安全性 & 規範中心的 eDiscovery 案例保留  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds*屬性也包含與可能位於信箱上安全性 & 合規性中心的 eDiscovery 案例相關聯之任何保留的 GUID。 您可以告訴這是 eDiscovery 案例保留，因為 GUID 是以前置詞開頭 `UniH` 。  <br/> 您可以使用 `Get-CaseHoldPolicy` 安全性 & 規範中心 PowerShell 中的指令程式，以取得與信箱的保留相關之 eDiscovery 案例的相關資訊。 例如，您可以執行命令 `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 以顯示信箱上的案例保留名稱。 `UniH`當您執行此命令時，請務必移除前置詞。  <br/><br/> 若要識別與信箱上的保留相關聯的 eDiscovery 案例，請執行下列命令：<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


