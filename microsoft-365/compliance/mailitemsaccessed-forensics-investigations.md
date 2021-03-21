---
title: 使用進階稽核調查遭入侵帳戶
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用 MailItemsAccessed 信箱稽核動作執行遭入侵使用者帳戶的鑑識調查。
ms.openlocfilehash: e9dda101b330f6632e66c226156df3497ac38453
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903479"
---
# <a name="use-advanced-audit-to-investigate-compromised-accounts"></a>使用進階稽核調查遭入侵帳戶

遭入侵使用者帳戶 (也稱為「帳戶盜用」) 是一種攻擊類型，攻擊者取得使用者帳戶的存取權後會以該使用者的身分運作。 這些類型的攻擊有時會造成比攻擊者原先預期還要更大的危害。 調查遭入侵電子郵件帳戶時，您必須假設遭入侵的郵件資料多於追蹤攻擊者實際存在所表示的資料量。 視電子郵件訊息中的資料類型而定，您必須假設敏感性資訊已遭到入侵，除非您能證明敏感性資料並未公開，否則您將面臨法規處罰。 例如，若有證據顯示病患的健康資訊 (PHI) 遭到公開，則由 HIPAA 監管的組織會面臨巨額罰款。 在這些情況下，攻擊者不太可能對 PHI 有興趣，但是組織仍然必須上報有資料外洩，除非組織能夠特別證明沒有資料外洩。

為協助您調查遭入侵電子郵件帳戶，我們現在使用 *MailItemsAccessed* 信箱稽核動作，透過郵件通訊協定和用戶端，提供郵件資料的稽核存取權。 此新稽核動作將協助調查人員進一步瞭解電子郵件的資料外洩，並協助您找出可能已遭入侵之特定郵件項目的入侵範圍。 使用此新稽核動作的目的是協助主張特定郵件資料未遭入侵的鑑識辯護。 如果攻擊者取得特定郵件資料的存取權，Exchange Online 會稽核該事件，即使郵件項目沒有實際已遭讀取的徵兆亦如此。

## <a name="the-mailitemsaccessed-mailbox-auditing-action"></a>MailItemsAccessed 信箱稽核動作

新 MailItemsAccessed 動作屬於新 [Advanced Audit](advanced-audit.md) 功能。 這是 [Exchange 信箱稽核](/office365/securitycompliance/enable-mailbox-auditing#mailbox-auditing-actions)的功能之一，獲派 Office 365 或 Microsoft 365 E5 授權的使用者或訂閱 Microsoft 365 E5 合規性附加元件的組織依預設會啟用此動作。

MailItemsAccessed 信箱稽核動作涵蓋所有郵件通訊協定：POP、IMAP、MAPI、EWS、Exchange ActiveSync 和 REST。 此動作也涵蓋兩種類型的郵件存取：「同步處理」和「繫結」。

### <a name="auditing-sync-access"></a>稽核同步處理存取

同步處理作業只有在信箱是透過 Windows 或 Mac 的電腦版 Outlook 用戶端進行存取時才會記錄。 在同步處理作業期間，這些用戶端通常會從雲端下載大量的郵件項目到本機電腦。 同步處理作業的稽核量會變得相當可觀。 因此，我們不針對每個已同步處理的郵件產生稽核記錄，我們只針對其中包含已同步處理項目的郵件資料夾產生稽核事件。 這是假設已同步處理資料夾中「所有」郵件項目皆已遭入侵。 存取類型會記錄在稽核記錄的 OperationProperties 欄位。 

如需顯示稽核記錄中同步處理存取類型的範例，請參閱「[使用 MailItemsAccessed 稽核記錄進行鑑識調查](#use-mailitemsaccessed-audit-records-for-forensic-investigations)」一節中的步驟 2。

### <a name="auditing-bind-access"></a>稽核繫結存取

繫結作業是電子郵件訊息的個別存取。 若是繫結存取，稽核記錄中會記錄個別訊息的 InternetMessageId。 MailItemsAccessed 稽核動作會記錄繫結作業然後彙總至單一稽核記錄。 間隔 2 分鐘內發生的所有繫結作業會彙總於 AuditData 屬性內 Folders 欄位中的單一稽核記錄。 遭存取的每個訊息會使用其 InternetMessageId 加以識別。 記錄中所彙總的繫結作業數量會顯示在 AuditData 屬性中的 OperationCount 欄位。

如需顯示稽核記錄中繫結存取類型的範例，請參閱「[使用 MailItemsAccessed 稽核記錄進行鑑識調查](#use-mailitemsaccessed-audit-records-for-forensic-investigations)」一節中的步驟 4。

### <a name="throttling-of-mailitemsaccessed-audit-records"></a>MailItemsAccessed 稽核記錄的節流

如果在 24 小時內產生超過 1,000 個 MailItemsAccessed 稽核記錄，Exchange Online 會針對 MailItemsAccessed 活動停止產生稽核記錄。 當信箱受到節流控制，MailItemsAccessed 活動會在信箱開始節流後停止記錄 24 小時。 如果發生這種情況，信箱很可能會在此期間遭到入侵。 MailItemsAccessed 活動將會在下一個 24 小時後繼續記錄。  

以下是有關節流必須記住的事項：

- 在 Exchange Online 的所有信箱中，受到節流控制的信箱比例低於 1%

- 當信箱受到節流控制時，只有 MailItemsAccessed 活動的稽核記錄不會進行稽核。 其他的信箱稽核動作不受影響。

- 僅針對信箱的繫結作業進行節流控制。 同步處理作業的稽核記錄不會受到節流控制。

- 如果信箱受到節流控制，您可能會假設稽核記錄中有未記錄到的 MailItemsAccessed 活動。

如需顯示稽核記錄中 IsThrottled 屬性的範例，請參閱「[使用 MailItemsAccessed 稽核記錄進行鑑識調查](#use-mailitemsaccessed-audit-records-for-forensic-investigations)」一節中的步驟 1。

## <a name="use-mailitemsaccessed-audit-records-for-forensic-investigations"></a>使用 MailItemsAccessed 稽核記錄進行鑑識調查

信箱稽核會產生存取電子郵件訊息的稽核記錄，因此您可以確信電子郵件訊息並未遭到入侵。 基於此原因，在不確定某些資料已遭存取的情況下，我們會假設資料已遭存取而記錄下所有的郵件存取活動。

使用 MailItemsAccessed 稽核記錄做為鑑識之用的執行時機通常是在解決資料外洩並驅逐攻擊者之後。 若要開始調查，您應該找出已遭入侵的信箱組，然後判定攻擊者可以存取組織內信箱的時間範圍。 接著，您可以在 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 中使用 **Search-UnifiedAuditLog** 或 **Search-MailboxAuditLog** Cmdlet，搜尋對應到資料外洩的稽核記錄。 

您可以執行下列其中一個命令來搜尋 MailItemsAccessed 稽核記錄：

**整合的稽核記錄**

```powershell
Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000
```

**信箱稽核記錄**

```powershell
Search-MailboxAuditLog -Identity <user> -StartDate 01/06/2020 -EndDate 01/20/2020 -Operations MailItemsAccessed -ResultSize 1000 -ShowDetails
```

> [!TIP]
> 這兩個 Cmdlet 之間的主要差異在於，您可以使用 **Search-UnifiedAuditLog** Cmdlet 搜尋由一或多個使用者執行之活動的稽核記錄。 這是因為 *UserIds* 是多值參數。 **Search-MailboxAuditLog** Cmdlet 則是搜尋單一使用者的信箱稽核記錄。

以下是使用 MailItemsAccessed 稽核記錄調查遭入侵使用者攻擊的步驟。 每個步驟都會顯示 **Search-UnifiedAuditLog** 或 **Search-MailboxAuditLog** Cmdlet 的命令語法。

1. 檢查信箱是否受到節流控制。 若有的話，這表示有些信箱稽核記錄未被記錄下來。 在所有記錄皆有 IsThrottled 為 True 的情況下，您應該假設記錄產生後的 24 小時內，所有的信箱存取皆未經稽核且所有郵件資料已遭入侵。

   若要搜尋其中信箱是受節流控制的 MailItemsAccessed 記錄，請執行下列命令：

   **整合的稽核記錄**
 
   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"IsThrottled","Value":"True"*'} | FL
   ```

   **信箱稽核記錄**

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*IsThrottled:True*"} | FL
   ```

2. 檢查同步處理活動。 如果攻擊者使用電子郵件用戶端下載信箱中的訊息，攻擊者可以將電腦從網際網路斷開，然後在本機存取訊息，而不需要與伺服器互動。 這表示信箱稽核無法稽核這些活動。

   若要搜尋其中郵件項目是透過同步處理作業進行存取的 MailItemsAccessed 記錄，請執行下列命令：

   **整合的稽核記錄**

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 02/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Sync"*'} | FL
   ```

   **信箱稽核記錄**

   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Sync*"} | FL
   ```

3. 檢查同步處理活動以判定其中發生之背景與攻擊者存取信箱時所使用之背景相同的任何活動。 背景可以透過用來存取信箱和郵件通訊協定的用戶端電腦 IP 位址找出並區別。 如需詳細資訊，請參閱「[找出不同稽核記錄的存取背景](#identifying-the-access-contexts-of-different-audit-records)」一節。

   使用下方列出的屬性進行調查。 這些屬性位於 AuditData 或 OperationProperties 屬性中。 如果有任何同步處理發生的背景與攻擊者的活動背景相同，則請假設攻擊者已將所有郵件項目同步處理至他們的用戶端，這表示整個信箱可能已經遭到入侵。

   |屬性	         | 說明 |
   |:---------------- | :----------|
   |ClientInfoString | 描述通訊協定、用戶端 (包括版本)|
   |ClientIPAddress  | 用戶端電腦的 IP 位址。|
   |SessionId        | 工作階段識別碼可協助區分同一帳戶中攻擊者的動作和每天例行的使用者活動 (在帳戶遭入侵的情況下)|
   |UserId           | 使用者讀取訊息的 UPN。|
   |||

4. 檢查繫結活動。 執行步驟 2 和步驟 3 之後，您可以確信由攻擊者執行的所有其他信箱存取皆已擷取在 MailItemsAccessed 稽核記錄中，其中有 MailAccessType 屬性，值為 Bind。

   若要搜尋其中郵件項目是透過繫結作業進行存取的 MailItemsAccessed 記錄，請執行下列命令。

   **整合的稽核記錄**

   ```powershell
   Search-UnifiedAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -UserIds <user1,user2> -Operations MailItemsAccessed -ResultSize 1000 | Where {$_.AuditData -like '*"MailAccessType","Value":"Bind"*'} | FL
   ```
 
   **信箱稽核記錄**
   
   ```powershell
   Search-MailboxAuditLog -StartDate 01/06/2020 -EndDate 01/20/2020 -Identity <user> -Operations MailItemsAccessed -ResultSize 10000 -ShowDetails | Where {$_.OperationProperties -like "*MailAccessType:Bind*"} | FL
   ```

   遭到存取的電子郵件訊息可以透過其網際網路訊息識別碼加以識別。您也可以檢查是否有任何稽核記錄的背景與其他攻擊者活動的背景相同。 如需詳細資訊，請參閱「[找出不同稽核記錄的存取背景](#identifying-the-access-contexts-of-different-audit-records)」一節。
 
   您可以透過兩種不同的方式來使用繫結作業的稽核資料：

     - 透過使用 InternetMessageId 找到訊息，然後檢查是否有任何訊息包含敏感性資訊，存取或收集攻擊者已存取的所有電子郵件訊息。

     - 使用 InternetMessageId 搜尋與一組疑似敏感性電子郵件訊息相關的稽核記錄。 如果您只關注小量的訊息，那麼這個方式就相當實用。

## <a name="filtering-of-duplicate-audit-records"></a>篩選重複的稽核記錄

篩選出在彼此間隔一小時內發生之相同繫結作業的重複稽核作業以移除稽核干擾。 同步處理作業也會以一小時的時間間隔篩選出。 以相同的 InternetMessageId 為例，如果下方表格中所述屬性有任何不同，則此刪除重複程序便會發生例外。 如果這些屬性之一在重複的作業中不相同，系統會產生新稽核記錄。 下一小節將會詳細說明此程序。

| 屬性	| 說明|
|:--------|:---------|
|ClientIPAddress | 用戶端電腦的 IP 位址。|
|ClientInfoString| 用戶端用來存取信箱的用戶端通訊協定。| 
|ParentFolder    | 遭存取郵件項目的完整資料夾路徑。 |
|Logon_type      | 執行動作的使用者登入類型。 登入類型 (及其對應的 Enum 值) 是擁有者 (0)、管理員 (1) 或代理人 (2)。|
|MailAccessType  | 存取是繫結或同步處理作業。|
|MailboxUPN      | 遭讀取訊息所在的信箱 UPN。|
|User            | 讀取訊息的使用者 UPN。|
|SessionId       | 工作階段識別碼可協助區分同一信箱中攻擊者的動作和每天例行的使用者活動 (在帳戶遭入侵的情況下)。如需有關工作階段的詳細資訊，請參閱[考量攻擊者活動在 Exchange Online 工作階段內的背景](https://techcommunity.microsoft.com/t5/exchange-team-blog/contextualizing-attacker-activity-within-sessions-in-exchange/ba-p/608801)。|
||||

## <a name="identifying-the-access-contexts-of-different-audit-records"></a>找出不同稽核記錄的存取背景

攻擊者通常會在信箱擁有者存取信箱的同一時間存取信箱。 若要區分出攻擊者和信箱擁有者的存取，我們有定義存取背景的稽核記錄屬性。 如先前所述，當這些屬性的值不同時，即使活動發生於彙總期間，系統也會產生個別的稽核記錄。 下列範例中有三種不同的稽核記錄。 每一個都可以透過 SessionId 和 ClientIPAddress 屬性來區分。 遭到存取的訊息也可以識別出來。

|稽核記錄 1  |稽核記錄 2  |稽核記錄 3|
|---------|---------|---------|
|ClientIPAddress **1**<br/>SessionId **2**|ClientIPAddress **2**<br/>SessionId **2**|ClientIPAddress **1**<br/>SessionId **3**|
|InternetMessageId **A**<br/>InternetMessageId **D**<br/>InternetMessageId **E**<br/>InternetMessageId **F**<br/>|InternetMessageId **A**<br/>InternetMessageId **C**|InternetMessageId **B** |
||||

如果[前一小節](#filtering-of-duplicate-audit-records)之表格所列的屬性有任何不同，系統會產生另一個稽核記錄以追蹤新背景。 視活動發生的背景而定，系統會將存取排序整理到個別的稽核記錄。

例如，在以下螢幕擷取畫面中顯示的稽核記錄中，雖然我們是同時從 EWSEditor 和 OWA 存取郵件，但是存取活動會根據存取的發生背景而彙整於不同的稽核記錄中。 在此情況下，背景由 ClientInfoString 屬性的不同值所定義。

![依背景而異的稽核記錄](../media/MailItemsAccessed4.png)

以下是先前的螢幕擷取畫面中所示命令的語法：

```powershell
Search-MailboxAuditLog -Identity admin -ShowDetails -Operations MailItemsAccessed -ResultSize 2000 | Select LastAccessed,Operation,AuditOperationsCountInAggregatedRecord,ClientInfoString
```