---
title: 管理信箱稽核
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
description: 信箱稽核記錄 （也稱為預設信箱稽核或信箱的稽核預設情況下） 的 Office 365 中預設已開啟。 這表示信箱擁有者、 代理人和系統管理員所執行的特定動作都會自動記錄在信箱稽核記錄，您可以搜尋的信箱上執行的活動。
ms.openlocfilehash: 059039205e82ea63b1dc14a8be5e768e9cdba069
ms.sourcegitcommit: e872676ec98036a50d3a0cb5071109ea5f5a7ae5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2020
ms.locfileid: "41515564"
---
# <a name="manage-mailbox-auditing"></a>管理信箱稽核

2019 年 1 月開始，Microsoft 開啟信箱稽核記錄功能預設為所有 Office 365 組織。 這表示自動記錄信箱擁有者、 代理人和系統管理員所執行某些動作，以及對應的信箱稽核記錄時，會提供您的信箱稽核記錄中搜尋它們。 信箱稽核依預設已開啟之前，您必須以手動啟用每個使用者信箱在您的組織中使用。

以下是一些信箱的稽核預設的優點：

- 自動啟用稽核，當您建立新的信箱。 您不需要以手動啟用為新的使用者。

- 您不需要管理稽核的信箱動作。 一組預先定義的信箱動作會針對每個登入類型 （系統管理員、 代理人和擁有者） 的預設稽核。

- 當 Microsoft 發行新的信箱動作 （尤其是動作有助於保護您的組織，並協助鑑定調查） 時，巨集指令會自動新增至預設稽核的信箱動作的清單。 這表示您不需要監視信箱上新增新動作。

- （因為您正在稽核所有信箱的相同的動作），您可以有整個組織的一致的信箱稽核原則。

> [!NOTE]
>• 關於信箱的稽核預設版本，請記得重要事情是： 您不需要執行任何動作來管理信箱的稽核。 不過，若要了解更多、 自訂預設設定，從信箱稽核或完全將其關閉，本主題可協助您。 <br><br>• 僅信箱稽核事件 E5 使用者都可以在安全 & 與規範中心中或透過 Office 365 管理活動 API 的稽核記錄搜尋。 如需詳細資訊，請參閱本主題[的詳細資訊](#more-information)一節。

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>確認信箱的稽核預設已開啟

若要確認該信箱上的預設開啟稽核功能為您的組織， [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中執行下列命令：

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

**為 False**的值會指出的組織已啟用信箱的稽核預設。 這在預設組織值會覆寫的稽核設定特定信箱上的信箱。 例如，如果停用信箱 （ *AuditEnabled*屬性是**False**信箱） 的信箱稽核，預設信箱動作會仍稽核的信箱，因為信箱的稽核預設的組織已啟用。

若要保留特定信箱的停用信箱稽核，您可以設定信箱稽核略過信箱擁有者，以及已被其他使用者委派信箱存取權。 如需詳細資訊，請參閱本主題中的 [[略過信箱稽核記錄](#bypass-mailbox-audit-logging)] 區段。

> [!NOTE]
> 當信箱上預設會開啟稽核組織時， *AuditEnabled*屬性信箱的受影響的信箱不會從**False**變更為 **，則為 True**。 換句話說，信箱的稽核依預設會忽略*AuditEnabled*屬性信箱上的信箱。

## <a name="supported-mailbox-types"></a>支援的信箱類型

下表顯示預設的稽核的信箱目前支援的信箱類型：

|**信箱類型**|**支援**|**不支援**|
|:---------|:---------:|:---------:|
|使用者信箱|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|共用信箱|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Office 365 群組信箱|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|資源信箱||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|公用資料夾信箱||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a>登入類型，以及信箱動作

登入類型分類的使用者，並未在信箱上的稽核的動作。 下列清單說明登入類型的信箱中所使用的稽核記錄：

- **擁有者**： 信箱擁有者 （與信箱相關聯的帳戶）。

- **委派**：

  - 使用者獲指派 SendAs、 SendOnBehalf 或 FullAccess 權限到另一個信箱。

  - 獲指派的 FullAccess 權限給使用者的信箱是系統管理員。

- **系統管理員**：

  - 信箱搜尋與下列的 Microsoft eDiscovery 工具之一：

    - 在 「 規範中心中的內容搜尋。

    - eDiscovery 或規範中心中的進階電子文件。

    - Exchange Online 中的就地 eDiscovery。

  - 信箱是藉由使用 Microsoft Exchange Server MAPI 編輯器來存取。

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>代表使用者信箱和共用的信箱的信箱動作

下表說明可用的信箱稽核記錄的使用者信箱以及共用信箱的信箱動作。

- 核取記號 ( ![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) 指示信箱動作可以記錄 （不是所有動作都可用於所有登入類型） 的登入類型。

- 星號 ( <sup>\*</sup> ) 核取記號表示信箱巨集指令會登入類型的預設記錄之後。

- 請記住，與信箱完整存取權限的系統管理員會被視為委派。

|**信箱動作**|**描述**|**Admin**|**委派**|**Owner**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**AddFolderPermissions**|**附註**： 雖然這個值會被接受為信箱的動作，但它已包含在**UpdateFolderPermissions**動作並不分開稽核。 換言之，請勿使用此值。||||
|**ApplyRecord**|項目標示為記錄。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Copy**|郵件已複製到另一個資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**Create**|在信箱中的 [行事曆、 連絡人、 備忘稿或工作] 資料夾中建立項目 （例如，會建立新的會議邀請）。 請注意不稽核建立、 傳送或接收郵件。 此外，建立信箱資料夾的動作也不會受到稽核。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**FolderBind**|存取信箱資料夾。 系統管理員或代理人開啟信箱時，也會記錄此巨集指令。 <br/><br/> **附註**： 合併委派所執行的資料夾繫結動作的稽核記錄。 個別資料夾存取產生一個稽核記錄 24 小時期間內。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|**HardDelete**|郵件已從 [可復原的項目] 資料夾中清除。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MailboxLogin**|使用者登入其信箱。 |||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MessageBind**|郵件已在 [預覽] 窗格中檢視，或開啟。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**ModifyFolderPermissions**|**附註**： 雖然這個值會被接受為信箱的動作，但它已包含在**UpdateFolderPermissions**動作並不分開稽核。 換言之，請勿使用此值。||||
|**Move**|郵件已移到另一個資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MoveToDeletedItems**|郵件已遭刪除並移至 [刪除的郵件] 資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**RecordDelete**|會標示為記錄的虛刪除 （移至 [可復原的項目] 資料夾） 項目。 標示為記錄的項目無法永久刪除 （清除從 [可復原的項目] 資料夾）。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**RemoveFolderPermissions**|**附註**： 雖然這個值會被接受為信箱的動作，但它已包含在**UpdateFolderPermissions**動作並不分開稽核。 換言之，請勿使用此值。||||
|**SendAs**|已使用 [傳送為] 權限傳送郵件。 這表示另一位使用者傳送的郵件，就好像它來自信箱擁有者。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|已使用 [代理傳送者] 權限傳送郵件。 這表示另一位使用者傳送代表信箱擁有者的郵件。 此郵件會向收件者指出誰代理傳送郵件，以及實際上是誰傳送郵件。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|郵件已永久刪除或從 [刪除的郵件] 資料夾中刪除。 虛刪除的項目會移至 [可復原的項目] 資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**更新**|郵件或其屬性已變更。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|行事曆委派已指派給信箱。 行事曆代理可讓其他有相同組織權限的人來管理信箱擁有者的行事曆。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateFolderPermissions**|資料夾權限已變更。 資料夾權限可控制組織中的哪些使用者可以存取信箱中的資料夾，以及這些資料夾中的郵件。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateInboxRules**|收件匣規則已新增、 移除或變更。 收件匣規則用來處理郵件使用者的收件匣根據指定的條件，並符合規則的條件，例如將郵件移至指定資料夾或刪除郵件時採取的動作。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

> [!IMPORTANT]
> 如果您自訂信箱来稽核的動作的任何登入類型*之前*的信箱稽核上依預設已啟用組織中，自訂的設定會保留在信箱上並不以覆寫預設信箱動作本節所述。 若要還原為其預設值 （其中您可以在任何時間） 的稽核信箱動作，請參閱本主題稍後的 [[還原預設信箱動作](#restore-the-default-mailbox-actions)] 區段。

### <a name="mailbox-actions-for-office-365-group-mailboxes"></a>Office 365 群組信箱的信箱動作

信箱稽核上預設會帶信箱稽核登入至 Office 365 群組信箱，但您不能自訂正在記錄的內容 （您無法新增或移除任何登入類型記錄的信箱動作）。

下表說明每個登入類型的 Office 365 群組信箱上的預設記錄的信箱動作。

請記住，與 Office 365 群組信箱完整存取權限的系統管理員會被視為委派。

|**信箱動作**|**描述**|**Admin**|**委派**|**Owner**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**Create**|建立的行事曆項目。 請注意不稽核建立、 傳送或接收郵件。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**HardDelete**|郵件已從 [可復原的項目] 資料夾中清除。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MoveToDeletedItems**|郵件已遭刪除並移至 [刪除的郵件] 資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**SendAs**|已使用 [傳送為] 權限傳送郵件。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|已使用 [代理傳送者] 權限傳送郵件。 |![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|郵件已永久刪除或從 [刪除的郵件] 資料夾中刪除。 虛刪除的項目會移至 [可復原的項目] 資料夾。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**更新**|郵件或其屬性已變更。|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![核取記號](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>確認記錄每個登入類型預設信箱動作

信箱的稽核的預設值時，會將新*DefaultAuditSet*屬性新增至所有的信箱。 此屬性的值會指出是否要對信箱稽核 （由 Microsoft 管理） 的預設信箱動作。

若要在使用者信箱或共用的信箱上顯示值，取代\<MailboxIdentity\>使用的名稱、 別名，電子郵件地址或使用者主要名稱 （使用者名稱） 的信箱，並在 Exchange Online PowerShell 中執行下列命令：

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

若要在 Office 365 群組的信箱上顯示值，取代\<MailboxIdentity\>與名稱、 別名或共用的信箱並執行下列命令在 Exchange Online PowerShell 中的電子郵件地址：

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

值`Admin, Delegate, Owner`表示：

- 要稽核所有三個登入類型的預設信箱動作。 請注意這是您會看到 Office 365 群組信箱的唯一值。

- *不具有*系統管理變更使用者信箱或共用的信箱上任何登入類型的稽核的信箱動作。 請注意這是預設狀態之後的信箱上預設開啟稽核功能最初貴組織中。

如果系統管理員具有曾經需要變更稽核登入類型 （藉由**將 Set-mailbox** cmdlet 上使用*AuditAdmin*、 *AuditDelegate*或*AuditOwner*參數） 的信箱動作，則此屬性值將會不同。

例如，值`Owner` *DefaultAuditSet*屬性是以使用者的信箱或共用的信箱表示：

- 要稽核的信箱擁有者的預設信箱動作。

- 稽核的信箱動作`Delegate`和`Admin`已經變更登入類型從預設動作。

*DefaultAuditSet*屬性空白值表示所有三個登入類型已變更的使用者信箱或共用的信箱的信箱動作。

如需詳細資訊，請參閱本主題中的[預設記錄變更或還原的信箱動作](#change-or-restore-mailbox-actions-logged-by-default)」 一節

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>顯示正在登入信箱的信箱動作

若要查看目前登入使用者信箱或共用的信箱的信箱動作，取代\<MailboxIdentity\>使用的名稱、 別名、 電子郵件地址或使用者主要名稱 （使用者名稱），信箱的並在 Exchange Online PowerShell 中執行一或多個下列命令。

> [!NOTE]
> 雖然您可以加入`-GroupMailbox`切換到 Office 365 群組信箱的下列**Get-mailbox**命令不認為您會看到的值。 預設和 Office 365 群組信箱稽核的靜態的信箱動作稍早在本主題中[的 Office 365 群組信箱的信箱動作](#mailbox-actions-for-office-365-group-mailboxes)節所述。

#### <a name="owner-actions"></a>擁有者動作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>代理人動作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>系統管理動作

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>變更或還原預設記錄的信箱動作

如同先前的說明，其中一個信箱稽核上具有預設的主要優點是： 您不需要管理稽核的信箱動作。 Microsoft 會為您，我們將會自動新增新的信箱動作，以稽核依預設，因為它們發行。

不過，您的組織可能需要稽核一組不同的使用者信箱的信箱動作，以及共用信箱。 本節中的程序顯示如何變更每個登入類型，稽核的信箱動作，以及如何回復到 Microsoft 受管理的預設動作。

> [!IMPORTANT]
> 如果您使用下列程序以自訂登入使用者信箱或共用信箱的信箱動作時，由 Microsoft 釋放任何新預設信箱動作將不會自動稽核這些信箱上。 您需要以手動方式將任何新的信箱動作新增至您自訂動作的清單。

### <a name="change-the-mailbox-actions-to-audit"></a>變更要稽核的信箱動作

您可以使用**Set-mailbox**指令程式上的*AuditAdmin*、 *AuditDelegate*或*AuditOwner*參數來變更使用者信箱的稽核和共用信箱 （稽核動作無法自訂信箱的 Office 365 群組） 的信箱動作。

您可以使用兩個不同的方法來指定信箱動作：

- *取代*（覆寫） 現有的信箱動作，使用下列語法： `action1,action2,...actionN`。

- *新增或移除*信箱動作，而不影響其他現有的值使用下列語法：`@{Add="action1","action2",..."actionN"}`或`@{Remove="action1","action2",..."actionN"}`。

此範例會變更使用來覆寫預設動作 SoftDelete 和 HardDelete 對名為 「 Gabriela Laureano 」 信箱的系統信箱動作。

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

此範例會新增信箱 laura@contoso.onmicrosoft.com MailboxLogin 擁有者動作。

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

此範例會移除團隊討論信箱 MoveToDeletedItems 委派巨集指令。

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

不論您使用的方法，自訂使用者信箱或共用的信箱的稽核的信箱動作有下列結果：

- 對於您自訂登入類型]，不再是由 Microsoft 管理稽核的信箱動作。

- 您自訂的登入類型不再顯示在信箱*DefaultAuditSet*屬性值為[先前所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。

### <a name="restore-the-default-mailbox-actions"></a>還原預設信箱動作

如果您自訂稽核使用者信箱或共用的信箱的信箱動作，您可以使用下列語法來還原一個或所有登入類型的預設信箱動作：

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

您可以指定多個以逗號隔開的*DefaultAuditSet*值

**附註**： 下列程序不適用於 Office 365 群組信箱 （它們限制為預設動作為 > 所述[以下](#mailbox-actions-for-office-365-group-mailboxes)）。

此範例會還原信箱 mark@contoso.onmicrosoft.com 上的所有登入類型的預設稽核信箱動作。

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

本範例會還原信箱 chris@contoso.onmicrosoft.com，系統管理員登入類型的預設稽核信箱動作，但其中的代理人和擁有者的自訂稽核的信箱動作登入類型。

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

還原他稽核的預設信箱動作登入類型有下列結果：

- 登入類型的預設信箱動作會被取代目前的信箱動作清單。

- 由 Microsoft 釋放任何新信箱動作會自動新增至登入類型的稽核動作清單。

- 信箱的*DefaultAuditSet*屬性值會更新以包含已還原的登入類型。

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>關閉信箱的稽核預設為您的組織

您可以關閉信箱稽核上預設為整個組織的 Exchange Online PowerShell 中執行下列命令：

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

關閉信箱的稽核預設具有下列結果：

- 信箱稽核已停用您的組織。

- 從您停用信箱的稽核依預設，沒有信箱動作稽核，即使稽核 （信箱上的*AuditEnabled*屬性為**True**） 的信箱上啟用。

- 代表新的信箱和設定*AuditEnabled*屬性信箱上的新的或現有的信箱設**為 True**則會忽略未啟用信箱稽核。

- 任何信箱稽核略過的關聯 （使用**Set-mailboxauditbypassassociation**指令程式來設定） 的設定會被忽略。

- 現有的信箱稽核記錄會保留直到稽核記錄檔保留天數到期的記錄。

### <a name="turn-on-mailbox-auditing-on-by-default"></a>信箱上開啟稽核預設

若要開啟信箱的稽核重新開啟您的組織，請在 Exchange Online PowerShell 中執行下列命令：

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>略過信箱稽核記錄

目前，您無法停用信箱稽核特定信箱的信箱上的稽核預設組織中開啟時。 例如， *AuditEnabled*信箱屬性設定為**False**則會忽略。

不過，您可以仍使用**Set-mailboxauditbypassassociation**指令程式在 Exchange Online PowerShell 以防止*任何及所有*的信箱動作所指定的使用者，使登入，不論動作發生的位置。 例如：

- 略過的使用者所執行的信箱擁有者動作不會記錄。

- 略過的使用者 （包括共用的信箱） 的其他使用者的信箱上所執行的代理人動作不會記錄。

- 略過的使用者所執行的系統管理動作不會記錄。

若要略過信箱稽核記錄的特定使用者，取代\<MailboxIdentity\>使用的名稱、 電子郵件地址、 別名或使用者主要名稱 （使用者名稱），使用者的並執行下列命令：

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

若要確認已針對指定的使用者略過的稽核，請執行下列命令：

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

**True 是表示**的值會指出該信箱稽核記錄就會略過的使用者。

## <a name="more-information"></a>詳細資訊

- 雖然信箱稽核記錄上預設會啟用所有的組織，只有具備 E5 授權的使用者將會傳回信箱稽核記錄事件，在[稽核記錄搜尋的安全性 & 合規性中心中](search-the-audit-log-in-security-and-compliance.md)或透過[Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。

  若要擷取沒有 E5 授權使用者的信箱稽核記錄項目，您可以：

  - 在 Exchange Online PowerShell 中使用下列 cmdlet:

    - [Search-mailboxauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog)來搜尋信箱稽核記錄檔中的特定使用者。

    - [New-mailboxauditlogsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-mailboxauditlogsearch)來搜尋信箱稽核記錄，針對特定使用者，並使透過電子郵件傳送給指定的收件者的結果。

  - Exchange Online 中使用 Exchange 系統管理中心 (EAC)，執行下列動作：

    - [匯出信箱稽核記錄](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [執行非擁有者信箱存取報告](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- 根據預設，信箱稽核記錄會保留 90 天在被刪除之前的記錄。 您可以在 Exchange Online PowerShell 中的**Set-mailbox**指令程式上使用*AuditLogAgeLimit*參數變更稽核記錄保留天數。 不過，增加此值不會讓您搜尋超過 90 天的 Office 365 稽核記錄中的事件。

  如果您增加保留天數時，您需要使用[Search-mailboxauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog)指令程式在 Exchange Online PowerShell 來搜尋使用者的信箱稽核記錄超過 90 天的記錄。

- 如果您已經變更*AuditLogAgeLimit*屬性之前信箱的稽核預設組織正在開啟信箱，現有的信箱稽核記錄保留限制無法變更。 換句話說，信箱的稽核預設不會影響信箱稽核記錄的目前保留限制。

- 若要變更*AuditLogAgeLimit*值位於 Office 365 群組信箱，您必須包含`-GroupMailbox`切換**Set-mailbox**命令中。

- 信箱稽核記錄的每位使用者的信箱中 [可復原的項目] 資料夾中 （名為*稽核*） 的子資料夾中儲存的記錄。 請謹記下列事項需要注意的信箱稽核記錄和可復原的項目] 資料夾：

  - [可復原的項目] 資料夾，（[警告] 配額為 20 GB） 的預設為 30 GB 的儲存配額的信箱稽核記錄個數。 儲存配額會自動增加至 100 GB （以 90 GB 警告] 配額） 時：

    - 保留在信箱上。

    - 信箱被指派給 「 規範中心中的保留原則。

  - 信箱稽核記錄也會計入[[可復原的項目] 資料夾的資料夾限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。 最大值為 3 百萬個項目 （稽核記錄） 可以儲存在 [稽核] 子資料夾。

    > [!NOTE]
    > 它是不太可能會影響信箱的稽核依預設，儲存空間配額或 [可復原的項目] 資料夾的資料夾限制。

    - 您可以執行下列命令在 Exchange Online PowerShell，在 [可復原的項目] 資料夾中的 [稽核] 子資料夾中顯示的大小和項目數：

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - 您無法直接存取稽核記錄檔中記錄 [可復原的項目] 資料夾中。相反地，您會使用**Search-mailboxauditlog**指令程式，或搜尋 Office 365 稽核記錄] 來尋找及檢視信箱稽核記錄。

- 如果信箱會處於暫止狀態或指派給 「 規範中心中的保留原則，稽核記錄會記錄仍會保留該信箱*AuditLogAgeLimit*屬性 （預設為 90 天） 所定義的持續時間。 若要保留稽核記錄會記錄較長的保留的信箱，您需要增加信箱的*AuditLogAgeLimit*值。
