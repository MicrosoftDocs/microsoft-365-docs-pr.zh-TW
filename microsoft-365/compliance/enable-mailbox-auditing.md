---
title: 管理信箱稽核
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: 預設會在 Office 365 （也稱為「預設信箱審核」或「信箱審核」預設）中開啟信箱審核記錄。 這表示信箱擁有者、代理人和系統管理員所執行的某些動作會自動記錄在信箱審核記錄檔中，您可以在此搜尋在信箱上執行的活動。
ms.openlocfilehash: 6a1c435ca3be16ef2f4926cce56afe180c576f15
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634961"
---
# <a name="manage-mailbox-auditing"></a>管理信箱稽核

從2019年1月開始，Microsoft 預設會針對所有 Office 365 組織開啟信箱審核記錄。 這表示會自動記錄信箱擁有者、代理人和系統管理員所執行的某些動作，當您在信箱審核記錄檔中搜尋對應的信箱審核記錄時，就會提供這些記錄。 在信箱審核預設為開啟狀態之前，您必須針對組織中的每個使用者信箱手動啟用它。

以下是信箱審核的一些優點：

- 當您建立新的信箱時，會自動啟用審核。 您不需要為新使用者手動啟用它。

- 您不需要管理所審核的信箱動作。 預設會針對每個登入類型（系統管理員、委派及擁有者）審核一組預先定義的信箱動作。

- 當 Microsoft 發行新的信箱動作（特別有助於保護組織及協助進行鑒證調查的動作）時，會自動將該動作新增至預設會進行審核的信箱動作清單中。 這表示您不需要在信箱上監視新增的動作。

- 您的組織中的信箱審核原則一致（因為您正在審核所有信箱的相同動作）。

> [!NOTE]
>* 根據預設，應記住的信箱審核版本的重要事項是：您不需要執行任何動作來管理信箱審核。 不過，若要深入瞭解，請自訂信箱審核的預設設定，或完全關閉，本主題可協助您。 <br><br>* 預設情況下，只有 E5 使用者的信箱審核事件可在安全性 & 合規性中心或 Office 365 管理活動 API 中的審計記錄搜尋中取得。 如需詳細資訊，請參閱本主題中的[詳細資訊](#more-information)一節。

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>驗證預設開啟的信箱審核

若要確認您組織的預設信箱審核已開啟，請在[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中執行下列命令：

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

值**為 False**表示組織啟用預設的信箱審計。 依預設，組織值會覆寫特定信箱上的信箱審核設定。 例如，如果停用信箱的信箱審核（信箱上的*AuditEnabled*屬性為**False** ），仍然會為信箱審核預設信箱動作，因為預設會為組織啟用信箱審核。

若要將特定信箱的信箱審核停用，您可以為信箱擁有人或已被委派存取信箱之其他使用者設定信箱審核旁路。 如需詳細資訊，請參閱本主題中的「[略過信箱審核記錄](#bypass-mailbox-audit-logging)」一節。

> [!NOTE]
> 當組織的預設信箱審核為開啟狀態時，受影響的信箱的*AuditEnabled*屬性不會從**False**變更為**True**。 換句話說，依預設，信箱審核會忽略信箱上的*AuditEnabled*屬性。

## <a name="supported-mailbox-types"></a>支援的信箱類型

下表顯示預設情況下，信箱審核目前支援的信箱類型：

|**信箱類型**|**支援**|**不支援**|
|:---------|:---------:|:---------:|
|使用者信箱|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|共用信箱|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Office 365 群組信箱|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|資源信箱||![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|公用資料夾信箱||![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a>登入類型和信箱動作

登入類型會分類已在信箱上進行審核動作的使用者。 下列清單說明用於信箱審核記錄的登入類型：

- **擁有**者：信箱擁有人（與信箱相關聯的帳戶）。

- **委派**：

  - 已獲指派 SendAs、SendOnBehalf 或 FullAccess 許可權給另一個信箱的使用者。

  - 已獲指派 FullAccess 許可權給使用者信箱的系統管理員。

- 系統**管理員**：

  - 使用下列其中一個 Microsoft eDiscovery 工具來搜尋信箱：

    - 規範中心的內容搜尋。

    - 規範中心的 eDiscovery 或 Advanced eDiscovery。

    - 在 Exchange Online 中 In-Place eDiscovery。

  - 您可以使用 Microsoft Exchange Server MAPI 編輯器來存取信箱。

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>使用者信箱和共用信箱的信箱動作

下表說明信箱審核記錄中的使用者信箱和共用信箱可用的信箱動作。

- 一個核取記號（ ![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)）表示可以記錄登入類型的信箱動作（並非所有動作皆可用於所有登入類型）。

- 核取記號之後<sup>\*</sup>的星號（）表示登入類型的預設記錄為 [信箱] 動作。

- 請記住，對信箱具有「完整存取」許可權的系統管理員會被視為代理人。

|**信箱動作**|**描述**|**Admin**|**委託**|**Owner**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**AddFolderPermissions**|**附注**：雖然此值接受為信箱動作，但它已包含在**UpdateFolderPermissions**動作中，而且不會個別進行審核。 換句話說，請勿使用此值。||||
|**ApplyRecord**|專案標示為記錄。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Copy**|郵件已複製到另一個資料夾。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**Create**|在信箱的 [行事曆]、[連絡人]、[記事] 或 [任務] 資料夾中建立專案（例如，建立新的會議要求）。 請注意，不會審核建立、傳送或接收郵件。 此外，建立信箱資料夾的動作也不會受到稽核。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**預設值**||![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**FolderBind**|已存取信箱資料夾。 當系統管理員或代理人開啟信箱時，也會記錄此動作。 <br/><br/> **附注**：合併委派所執行之資料夾系結動作的審計記錄。 在24小時內，會為個別資料夾存取產生一個審計記錄。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|**HardDelete**|已從 [可復原的專案] 資料夾中清除郵件。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MailItemsAccessed**|郵件資料是由郵件通訊協定和用戶端存取。 這個值只適用于 E5 或 E5 相容性附加元件訂閱使用者。 如需詳細資訊，請參閱[存取重要事件以進行調查](advanced-audit.md#access-to-crucial-events-for-investigations)。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MailboxLogin**|使用者已登入其信箱。 |||![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MessageBind**|在 [預覽] 窗格中查看或由系統管理員開啟的郵件。**附注**：雖然此值會接受為信箱動作，但不再記錄這些動作。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**ModifyFolderPermissions**|**附注**：雖然此值接受為信箱動作，但它已包含在**UpdateFolderPermissions**動作中，而且不會個別進行審核。 換句話說，請勿使用此值。||||
|**Move**|郵件已移到另一個資料夾。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MoveToDeletedItems**|郵件已遭刪除並移至 [刪除的郵件] 資料夾。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**RecordDelete**|標示為記錄的專案已虛刪除（移至 [可復原的專案] 資料夾）。 標示為記錄的專案無法永久刪除（從 [可復原的專案] 資料夾中清除）。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**RemoveFolderPermissions**|**附注**：雖然此值接受為信箱動作，但它已包含在**UpdateFolderPermissions**動作中，而且不會個別進行審核。 換句話說，請勿使用此值。||||
|**SendAs**|已使用 [傳送為] 權限傳送郵件。 這表示另一位使用者已傳送郵件，就好像它來自信箱擁有者。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|已使用 [代理傳送者] 權限傳送郵件。 這表示另一位使用者代表信箱擁有者傳送郵件。 此郵件會向收件者指出誰代理傳送郵件，以及實際上是誰傳送郵件。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|郵件已永久刪除或從 [刪除的郵件] 資料夾中刪除。 虛刪除的專案會移至 [可復原的專案] 資料夾。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**更新**|郵件或其屬性已變更。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|已將行事曆委派指派給信箱。 行事曆代理可讓其他有相同組織權限的人來管理信箱擁有者的行事曆。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateComplianceTag**|其他保留標籤會套用至訊息項目（專案只能有一個已指派的保留標籤）。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**UpdateFolderPermissions**|資料夾權限已變更。 資料夾權限可控制組織中的哪些使用者可以存取信箱中的資料夾，以及這些資料夾中的郵件。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateInboxRules**|新增、移除或變更收件匣規則。 [收件匣] 規則是用來根據指定的條件處理使用者收件匣中的郵件，並在符合規則條件時採取動作，例如將郵件移至指定的資料夾或刪除郵件。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

> [!IMPORTANT]
> 如果您自訂在組織中啟用信箱審核*之前*針對任何登入類型進行審核的信箱動作，則自訂設定會保留在信箱上，而且不會以本節所述的預設信箱動作覆寫。 若要將「審核信箱」動作還原成其預設值（您可以隨時執行），請參閱本主題稍後的[還原預設信箱動作](#restore-the-default-mailbox-actions)一節。

### <a name="mailbox-actions-for-office-365-group-mailboxes"></a>Office 365 群組信箱的信箱動作

信箱審核預設會將信箱審核記錄到 Office 365 群組信箱，但您無法自訂要記錄的專案（您無法新增或移除記錄的任何登入類型的信箱動作）。

下表說明每種登入類型的 Office 365 群組信箱上預設會記錄的信箱動作。

請記住，對 Office 365 群組信箱具有「完整存取」許可權的系統管理員會被視為代理人。

|**信箱動作**|**描述**|**Admin**|**委託**|**Owner**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**Create**|建立行事曆專案。 請注意，不會審核建立、傳送或接收郵件。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**HardDelete**|已從 [可復原的專案] 資料夾中清除郵件。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MoveToDeletedItems**|郵件已遭刪除並移至 [刪除的郵件] 資料夾。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**SendAs**|已使用 [傳送為] 權限傳送郵件。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|已使用 [代理傳送者] 權限傳送郵件。 |![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|郵件已永久刪除或從 [刪除的郵件] 資料夾中刪除。 虛刪除的專案會移至 [可復原的專案] 資料夾。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**更新**|郵件或其屬性已變更。|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>確認每個登入類型的預設信箱動作都會進行記錄

信箱審核的預設值會將新的*DefaultAuditSet*屬性加入至所有信箱。 此屬性的值會指出是否要在信箱上審核預設的信箱動作（由 Microsoft 管理）。

若要在使用者信箱或共用信箱上顯示值， \<請\>以信箱的名稱、別名、電子郵件地址或使用者主要名稱（username）取代 MailboxIdentity，並在 Exchange Online 中執行下列命令 PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

若要在 Office 365 群組信箱上顯示值， \<請\>以共用信箱的名稱、別名或電子郵件地址取代 MailboxIdentity，並在 Exchange Online 中執行下列命令 PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

此值`Admin, Delegate, Owner`表示：

- 所有三種登入類型的預設信箱動作都會進行審核。 請注意，這是您可以在 Office 365 群組信箱上看到的唯一值。

- *管理員尚未*變更使用者信箱或共用信箱上任何登入類型的已審核信箱動作。 附注：這是預設會在您的組織中開啟信箱審核之後的預設狀態。

如果系統管理員曾經變更了為登入類型所審核的信箱動作（透過使用**Set-Mailbox**指令程式上的*AuditAdmin*、 *AuditDelegate*或*AuditOwner*參數），該屬性值將會不同。

例如，使用者信箱或`Owner`共用信箱上之*DefaultAuditSet*屬性的值會指出：

- 會審核信箱擁有者的預設信箱動作。

- 針對`Delegate`和登入類型所審核`Admin`的信箱動作，已從預設動作變更。

*DefaultAuditSet*屬性的空白值表示所有三種登入類型的信箱動作都已在使用者信箱或共用信箱上變更。

如需詳細資訊，請參閱本主題中的[變更或還原依預設所記錄的信箱動作](#change-or-restore-mailbox-actions-logged-by-default)一節。

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>顯示正在登入信箱的信箱動作

若要查看目前正在登入使用者信箱或共用信箱的信箱動作，請以\<信箱\>的名稱、別名、電子郵件地址或使用者主要名稱（username）取代 MailboxIdentity，並在 Exchange Online PowerShell 中執行下列一或多個命令。

> [!NOTE]
> 雖然您可以將`-GroupMailbox`參數新增至 Office 365 群組信箱的下列**Get-Mailbox**命令，但不會相信傳回的值。 本主題稍早的「 [office 365 群組信箱的信箱動作](#mailbox-actions-for-office-365-group-mailboxes)」一節將說明針對 Office 365 群組信箱所審核之預設和靜態信箱動作。

#### <a name="owner-actions"></a>擁有者動作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>委派動作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>系統管理動作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>變更或還原預設所記錄的信箱動作

如先前所述，預設會啟用信箱審核的其中一個重要優點是：您不需要管理所審核的信箱動作。 Microsoft 會為您做這種情況，而且在發佈新的信箱動作時，系統會自動將其新增為待審計。

不過，您的組織可能需要針對使用者信箱和共用信箱，審核一組不同的信箱動作。 本節中的程式說明如何變更針對每一種登入類型所審核的信箱動作，以及如何回復至 Microsoft 受管理的預設動作。

> [!IMPORTANT]
> 如果您使用下列程式自訂使用者信箱或共用信箱上所記錄的信箱動作，Microsoft 所發行的任何新預設信箱動作都不會自動在這些信箱上進行審核。 您必須手動將任何新的信箱動作新增至自訂動作清單。

### <a name="change-the-mailbox-actions-to-audit"></a>變更要審核的信箱動作

您可以使用**Set-Mailbox** Cmdlet 上的*AuditAdmin*、 *AuditDelegate*或*AuditOwner*參數，來變更針對使用者信箱和共用信箱進行審核的信箱動作（無法自訂 Office 365 群組信箱的已審核動作）。

您可以使用兩種不同的方法來指定信箱動作：

- 使用下列語法*取代*（覆寫）現有的信箱動作： `action1,action2,...actionN`。

- 使用下列語法，*新增或移除*不會影響其他現有值的信箱`@{Add="action1","action2",..."actionN"}`動作`@{Remove="action1","action2",..."actionN"}`：或。

在這個範例中，會使用 SoftDelete 和 HardDelete 覆寫預設動作，以變更名為 "Gabriela Laureano" 之信箱的系統管理員信箱動作。

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

本範例會將 MailboxLogin 的擁有者動作新增至信箱 laura@contoso.onmicrosoft.com。

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

本範例會移除小組討論信箱的 MoveToDeletedItems 委派動作。

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

不論使用哪一種方法，自訂使用者信箱或共用信箱上的已審核信箱動作都有下列結果：

- 針對您自訂的登入類型，會不再由 Microsoft 管理已審核的信箱動作。

- 您自訂的登入類型不再如[先前所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)，顯示在信箱的*DefaultAuditSet*屬性值中。

### <a name="restore-the-default-mailbox-actions"></a>還原預設的信箱動作

如果您自訂在使用者信箱或共用信箱上進行審核的信箱動作，您可以使用下列語法還原一或所有登入類型的預設信箱動作：

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

您可以指定多個以逗號分隔的*DefaultAuditSet*值。

**附注**：下列程式不適用於 Office 365 群組信箱（它們會限制于[此處](#mailbox-actions-for-office-365-group-mailboxes)所述的預設動作）。

本範例會在信箱 mark@contoso.onmicrosoft.com 上還原所有登入類型的預設已審核信箱動作。

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

此範例會還原信箱 chris@contoso.onmicrosoft.com 上系統管理員登入類型的預設已審核信箱動作，但會將委派及擁有者登入類型的自訂已審核信箱動作保留。

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

還原登入類型的預設已審核信箱動作具有下列結果：

- 目前的信箱動作清單會取代為登入類型的預設信箱動作。

- Microsoft 所發行的任何新信箱動作都會自動新增至登入類型的已審核動作清單。

- 信箱的*DefaultAuditSet*屬性值會更新，以包含還原的登入類型。

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>針對您的組織，關閉預設的信箱審計

您可以在 Exchange Online 中執行下列命令，關閉整個組織的預設信箱審計 PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

預設關閉信箱審核的結果如下：

- 您的組織已停用信箱審核。

- 從您已停用的信箱審核預設情況下，即使在信箱上啟用審核，也不會審核任何信箱動作（信箱上的*AuditEnabled*屬性為**True**）。

- 信箱審核未啟用新信箱，並將新的或現有的信箱上的*AuditEnabled*屬性設定為 True，則會忽略此**值**。

- 會忽略任何信箱審核略過的關聯設定（使用**Set-MailboxAuditBypassAssociation** Cmdlet 設定）。

- 現有的信箱審計記錄會保留，直到記錄的「審核記錄保留時間上限」到期為止。

### <a name="turn-on-mailbox-auditing-on-by-default"></a>依預設開啟信箱審計

若要為您的組織重新啟用信箱審核，請在 Exchange Online 中執行下列命令 PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>略過信箱審核記錄

目前，當組織中的信箱審核預設為開啟狀態時，您無法停用特定信箱的信箱審核。 例如，會忽略將*AuditEnabled*信箱屬性設定為**False** 。

不過，您仍然可以在 Exchange Online PowerShell 中使用**Set-MailboxAuditBypassAssociation**指令程式，以防止指定的使用者記錄*任何和所有*信箱動作，不論動作發生的位置為何。 例如：

- 未記錄略過使用者執行的信箱擁有者動作。

- 委派其他使用者信箱（包括共用信箱）上略過使用者執行的動作不會被記錄。

- 不會記錄略過使用者執行的系統管理員動作。

若要略過特定使用者的信箱審核記錄， \<請\>使用使用者的名稱、電子郵件地址、別名或使用者主要名稱（username）取代 MailboxIdentity，並執行下列命令：

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

若要確認指定的使用者已略過審核，請執行下列命令：

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

值**為 True**表示使用者略過信箱審核記錄。

## <a name="more-information"></a>詳細資訊

- 雖然預設會為所有組織啟用信箱審核記錄，但只有具有 E5 授權的使用者才會在[安全性 & 合規性中心](search-the-audit-log-in-security-and-compliance.md)或透過[Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) **的「** 審核記錄」搜尋中，傳回信箱審核記錄事件。

  若要取得沒有 E5 授權之使用者的信箱審計記錄專案，您可以：

  - 手動啟用個別信箱的信箱審核**後**，請在安全性 & 合規性中心或透過 Office 365 管理活動 API 中使用審核記錄搜尋。

  - 在 Exchange Online 中使用下列 Cmdlet PowerShell:

    - [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog)搜尋特定使用者的信箱審核記錄。

    - [New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-mailboxauditlogsearch)搜尋特定使用者的信箱審核記錄，並將結果透過電子郵件傳送給指定的收件者。

  - 在 Exchange Online 中使用 Exchange 系統管理中心（EAC）執行下列動作：

    - [匯出信箱稽核記錄](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [執行非擁有者信箱存取報告](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- 依預設，信箱審核記錄記錄會在刪除之前保留90天。 您可以使用 Exchange Online PowerShell 中**Set-Mailbox** Cmdlet 上的*AuditLogAgeLimit*參數，來變更審核記錄記錄的保留天數。 不過，增加此值不會讓您在 Office 365 審核記錄中搜尋超過90天的事件。

  如果您增加保留天數，您必須在 Exchange Online 中使用[Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog)指令程式 PowerShell 來搜尋使用者的信箱審核記錄中超過90天的記錄。

- 如果您已在信箱審核之前將信箱的*AuditLogAgeLimit*屬性變更為已開啟組織的預設值，則信箱的現有審核記錄保留時間限制不會變更。 換句話說，依預設，信箱審核不會影響信箱審核記錄的目前保留限制。

- 若要變更 Office 365 群組信箱上的*AuditLogAgeLimit*值，您必須在**Set-Mailbox**命令`-GroupMailbox`中包含該參數。

- 信箱審計記錄檔會儲存在每個使用者信箱的 [可復原的專案] 資料夾中的子資料夾（稱為「*審核*」）。 請記住下列有關信箱審計記錄和 [可復原的專案] 資料夾的事項：

  - 信箱審計記錄會根據 [可復原的專案] 資料夾的儲存配額進行計數（預設為30GB （警告配額為 20 GB）。 在下列情況時，儲存配額會自動增加為 100 GB （含 90 GB 的警告配額）：

    - 保留是放在信箱上。

    - 信箱會指派給規範中心內的保留原則。

  - 信箱審計記錄也會計入[[可復原的專案] 資料夾的資料夾限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。 最多可將3000000個專案（審計記錄）儲存在 [審計] 子資料夾中。

    > [!NOTE]
    > 根據預設，信箱審核可能會影響儲存配額或 [可復原的專案] 資料夾的資料夾限制。

    - 您可以在 Exchange Online PowerShell 中執行下列命令，以在 [可復原的專案] 資料夾的 [審計] 子資料夾中顯示專案的大小和數目：

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - 您無法直接存取 [可復原的專案] 資料夾中的審計記錄記錄;相反地，您可以使用**Search-MailboxAuditLog** Cmdlet 或搜尋 Office 365 的審計記錄檔，以尋找及查看信箱審計記錄。

- 如果信箱處於暫止狀態或指派給規範中心內的保留原則，則在信箱的*AuditLogAgeLimit*屬性（預設值為90天）定義的期間內仍會保留審核記錄記錄。 若要保留長期保留信箱的審計記錄檔，您需要增加信箱的*AuditLogAgeLimit*值。
