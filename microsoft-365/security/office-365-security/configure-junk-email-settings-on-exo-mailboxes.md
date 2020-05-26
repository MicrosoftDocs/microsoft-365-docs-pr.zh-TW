---
title: 設定 Exchange Online 信箱上的垃圾郵件設定
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在 Exchange Online 信箱中設定垃圾郵件設定。 在 Outlook 或 web 上的 Outlook 中，使用者可以使用許多這些設定。
ms.openlocfilehash: 72b2680cb16e9d8d0f33ee3ec8a080206c68bf97
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352507"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>設定 Exchange Online 信箱上的垃圾郵件設定

在 Exchange Online 中有信箱的 Microsoft 365 組織中，組織的反垃圾郵件設定是由 Exchange Online Protection （EOP）控制。 如需詳細資訊，請參閱[EOP 中的反垃圾郵件保護](anti-spam-protection.md)。

不過，系統管理員也可以在 Exchange Online 中個別的信箱上設定特定的反垃圾郵件設定：

- **啟用或停用垃圾郵件規則**：「垃圾郵件規則」是一種隱藏的收件匣規則，名稱為「垃圾郵件規則」預設會在每個信箱中啟用。 垃圾郵件規則會控制下列功能：

  - **根據反垃圾郵件原則將郵件移至 [垃圾郵件] 資料夾**：當反垃圾郵件原則使用 [**將郵件移至垃圾郵件] 資料夾**設定為垃圾郵件篩選判定時，垃圾郵件篩選規則會在郵件傳遞至信箱之後，將郵件移至 [垃圾郵件] 資料夾。 如需反垃圾郵件原則中垃圾郵件篩選 verdicts 的詳細資訊，請參閱[設定 EOP 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)。 同樣地，如果零小時自動清除（ZAP）決定傳遞的郵件為垃圾郵件或網路釣魚，垃圾郵件篩選規則會將郵件移至 [垃圾郵件] 資料夾，將**郵件移至**[垃圾郵件] 資料夾。垃圾郵件篩選判定的動作。 如需有關 ZAP 的詳細資訊，請參閱[在 Exchange Online 中以零小時自動清除（ZAP）](zero-hour-auto-purge.md)。
  
  - **使用者在 outlook 或網頁型 outlook 中為自己自行設定的垃圾郵件設定**：安全_組集合_為安全寄件者清單、安全收件者清單，以及每個信箱上的封鎖寄件者清單。 這些清單中的專案會決定垃圾郵件規則是否會將郵件移至 [收件匣] 或 [垃圾郵件] 資料夾。 使用者可以在 Outlook 或網頁型 outlook （先前稱為 Outlook Web App）中為自己的信箱設定安全清單集合。 系統管理員可以在任何使用者的信箱上設定安全清單集合。

當信箱上已啟用垃圾郵件規則時，EOP 可以根據垃圾郵件篩選判定動作將郵件移至 [垃圾郵件] 資料夾，並將郵件移至 [垃圾郵件]**資料夾**或信箱上的 [封鎖寄件者] 清單，並防止郵件傳遞至 [垃圾郵件] 資料夾（根據信箱上的 [安全的寄件者] 清單）。

 當信箱上的垃圾郵件規則停用時，EOP 無法根據垃圾郵件篩選判定動作將郵件移至垃圾郵件資料夾。**將郵件移至垃圾郵件資料夾**或信箱上的安全清單集合。

系統管理員可以使用 Exchange Online PowerShell 來停用、啟用和查看信箱上垃圾郵件規則的狀態。 系統管理員也可以使用 Exchange Online PowerShell 來設定信箱上的安全清單集合中的專案（[安全寄件者] 清單、[安全的收件者] 清單和 [封鎖寄件者] 清單）。

> [!NOTE]
> 來自使用者已新增至自己安全寄件者清單中寄件者的郵件將會略過 EOP 篩選（SCL 為-1）。 若要防止使用者將專案新增至 Outlook 的安全寄件者清單，請使用本主題稍後的 [[關於 Outlook 中的垃圾郵件設定](#about-junk-email-settings-in-outlook)] 區段中所述的群組原則。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您只可以使用 Exchange Online PowerShell 來執行這些程式。 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

- 您必須已獲指派許可權，才能執行這些程式。 具體而言，您需要 **「郵件**收件者」角色（預設會指派給**組織管理**、**收件者管理**和**自訂郵件**收件者角色群組）或 [**使用者選項**] 角色（預設會指派給「**組織管理** **」和「服務台」** 角色群組）。 若要將使用者新增至 Exchange Online 中的角色群組，請參閱[Modify role groups In Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。 請注意，具有預設許可權的使用者可以在自己的信箱上執行這些相同的程式，只要他們可以[存取 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。

- 在獨立版 EOP 環境中，EOP 會保護內部部署 Exchange 信箱，您必須在內部部署 Exchange 中設定郵件流程規則 (又稱為傳輸規則) 以轉譯 EOP 垃圾郵件篩選裁決，這樣垃圾郵件規則才可以將郵件移至 [垃圾郵件] 資料夾。 如需詳細資訊，請參閱[設定獨立版 EOP 將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

- 共用信箱的安全寄件者不會與 Azure AD 同步處理，也不會 EOP 設計。

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>使用 Exchange Online PowerShell 啟用或停用信箱中的垃圾郵件規則

> [!NOTE]
> 您只能使用 **Set-MailboxJunkEmailConfiguration** Cmdlet 來停用已在 Outlook (在快取 Exchange 模式) 或 網頁型 Outlook 中開啟的信箱的垃圾郵件規則。 若尚未開啟信箱，您會收到錯誤： `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` 如果您想要針對大量作業隱藏此錯誤，您可以將此錯誤新增 `-ErrorAction SlientlyContinue` 至**Set-MailboxJunkEmailConfiguration**命令。

若要啟用或停用信箱中的垃圾郵件規則，請使用下列語法：

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

本範例會停用 Ori Epstein 的信箱上的垃圾郵件規則。

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

本範例會停用組織中所有使用者信箱的垃圾郵件規則。

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

如需詳細的語法及參數資訊，請參閱[Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。

> [!NOTE]
> 
> - 如果使用者從未開啟其信箱，當您執行先前的命令時，可能會收到錯誤。 若要抑制大量作業的此錯誤，請新增 `-ErrorAction SlientlyContinue` 至**Set-MailboxJunkEmailConfiguration**命令。
> 
> - 即使您停用垃圾郵件規則，Outlook 垃圾郵件篩選器（取決於其設定方式）也可以判斷郵件是否為垃圾郵件，以及是否可以將郵件移至 [收件匣] 或 [垃圾郵件] 資料夾（根據其本身的垃圾郵件，以及信箱上的安全清單集合）。 如需詳細資訊，請參閱本主題中的＜[關於 Outlook 中的垃圾郵件設定](#about-junk-email-settings-in-outlook)＞章節。

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您已成功啟用或停用信箱上的垃圾郵件規則，請使用下列程序：

- 以信箱的名稱、別名或電子郵件地址取代_ \< \> MailboxIdentity_ ，並執行下列命令來驗證**Enabled**屬性值：

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>使用 Exchange Online PowerShell 設定信箱上的安全清單集合

信箱上的安全清單集合包含 [安全寄件者] 清單、[安全收件者] 清單及 [封鎖寄件者] 清單。 根據預設，使用者可以在 Outlook 或網頁型 Outlook 中設定自己信箱上的安全清單集合。 系統管理員可以使用 **Set-MailboxJunkEmailConfiguration** Cmdlet 上的對應參數，在使用者的信箱上設定安全清單集合。 下表將說明這些參數。

|||
|---|---|
|**Set-MailboxJunkEmailConfiguration 的參數**|**網頁上的 Outlook 設定**|
|_BlockedSendersAndDomains_|**將來自這些寄件者或網域的電子郵件移至我的 [垃圾郵件] 資料夾**|
|_ContactsTrusted_|**信任來自我的連絡人的電子郵件**|
|_TrustedListsOnly_|**只信任「我的安全寄件者和網域」清單中的電子郵件和安全郵寄清單中的位址**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**不將這些寄件者的電子郵件移至我的垃圾郵件資料夾**|
|

<sup>\*</sup>**附注**：

- 在 Exchange Online 中，無法辨識 [安全的寄件者] 清單或 [ _TrustedSendersAndDomains_ ] 參數中的**網域專案**，因此只會使用電子郵件地址。 在具有目錄同步處理的獨立 EOP 中，預設不會同步處理網域專案，但您可以啟用網域的同步處理。 如需詳細資訊，請參閱[KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange)。

- 您無法使用**Set-MailboxJunkEmailConfiguration** Cmdlet 直接修改 [安全的收件者] 清單（ _TrustedRecipientsAndDomains_參數無法使用）。 修改 [安全寄件者] 清單中，這些變更就會同步處理至 [安全收件者] 清單。

若要設定信箱上的安全清單集合，請使用下列語法：

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

若要輸入多個值，並覆寫_BlockedSendersAndDomains_和_TrustedSendersAndDomains_參數的任何現有專案，請使用下列語法： `"<Value1>","<Value2>"...` 。 若要新增或移除一個或多個值，而不影響其他現有的專案，請使用下列語法：`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

本範例會將 Ori Epstein 信箱上的安全清單集合設定為下列設定：

- 將 shopping@fabrikam.com 值新增至 [封鎖的寄件者] 清單。

- 從 [安全的寄件者] 清單和 [安全的收件者] 清單中移除 value chris@fourthcoffee.com。

- 設定要視為受信任寄件者的 [連絡人] 資料夾中的連絡人。

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

這個範例會移除組織中所有使用者信箱的 [封鎖寄件者] 清單中的網域 contoso.com。

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

如需詳細的語法及參數資訊，請參閱[Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。

> [!NOTE]
> 
> - 如果使用者從未開啟其信箱，當您執行先前的命令時，可能會收到錯誤。 若要抑制大量作業的此錯誤，請新增 `-ErrorAction SlientlyContinue` 至**Set-MailboxJunkEmailConfiguration**命令。
> 
> - 即使停用信箱上的垃圾郵件規則，仍然可以設定安全清單集合，而 Outlook 垃圾郵件篩選器可以將郵件移至收件匣或 [垃圾郵件] 資料夾。 如需詳細資訊，請參閱本主題中的＜[關於 Outlook 中的垃圾郵件設定](#about-junk-email-settings-in-outlook)＞章節。
> 
> - Outlook 垃圾郵件篩選器有其他安全清單集合設定（例如，**自動將我的電子郵件新增至安全寄件者清單**）。 如需詳細資訊，請參閱＜[使用垃圾郵件篩選器來控制要查看的訊息](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077)＞。

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要驗證您是否已成功設定信箱上的安全清單集合，請使用任何下列程序：

- 以信箱的名稱、別名或電子郵件地址取代_ \< MailboxIdentity \> _ ，並執行下列命令來驗證屬性值：

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  如果值清單過長，請使用下列語法：

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>關於 Outlook 中的垃圾郵件設定

若要啟用、停用及設定 Outlook 中可用的用戶端垃圾郵件篩選器設定，請使用「群組」原則。 如需詳細資訊，請參閱系統[管理範本檔案（ADMX/ADML）和 Office 自訂365工具（適用于企業、office 2019 及 office 2016](https://www.microsoft.com/download/details.aspx?id=49030) ）和[如何使用群組原則部署垃圾郵件設定，例如安全寄件者清單](https://support.microsoft.com/help/2252421/how-to-deploy-junk-email-settings-such-as-the-safe-senders-list-by-usi)。

當 outlook 垃圾郵件篩選器設定為預設值時，**不會自動篩選****家用** \> **垃圾** \> **郵件 E-Mail 選項** \> **選項**，Outlook 不會嘗試將 massages 歸類為垃圾郵件，但仍然使用安全性群組集合（安全的寄件者清單、安全的收件者清單和封鎖的寄件者清單）將郵件移至 [垃圾郵件] 資料夾傳送後。 如需這些設定的詳細資訊，請參閱[垃圾郵件篩選程式的概述](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。

當 Outlook 垃圾郵件篩選器設定為 **[低]** 或 **[高]** 時，Outlook [垃圾郵件篩選器] 會使用它自己的 SmartScreen 篩選技術來進行識別，並將垃圾郵件移至 [垃圾郵件] 資料夾。 這種垃圾郵件分類與 EOP 所決定的垃圾郵件信賴等級（SCL）不同。 實際上，Outlook 會忽略 SCL EOP （除非 EOP 標示郵件以略過垃圾郵件篩選），並使用其自己的準則來判斷郵件是否為垃圾郵件。 當然，EOP 和 Outlook 的垃圾郵件可能都是相同的。 如需這些設定的詳細資訊，請參閱[變更垃圾郵件篩選器中的保護層級](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。

> [!NOTE]
> 在11月2016中，Microsoft 已停止為 Exchange 和 Outlook 中的 SmartScreen 篩選器產生垃圾郵件定義更新。 現有的 SmartScreen 垃圾郵件定義會保留，但其效果可能會隨著時間降低。 如需詳細資訊，請參閱 [Outlook 和 Exchange 中 SmartScreen 的取代支援](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)。

因此，Outlook 垃圾郵件篩選器可以使用信箱的安全清單集合和其自己的垃圾郵件分類，將郵件移至 [垃圾郵件] 資料夾，即使信箱中已停用垃圾郵件規則也是一樣。

Outlook 和 網頁型 Outlook 兩者都支援安全清單集合。 安全清單集合會儲存在 Exchange Online 信箱中，所以 Outlook 中的安全清單集合變更會顯示在 Outlook 網頁版中，反之亦然。

## <a name="limits-for-junk-email-settings"></a>垃圾郵件設定的限制

儲存在使用者信箱中的安全清單集合（[安全的寄件者] 清單、[安全的收件者] 清單和 [封鎖的寄件者] 清單）也會同步處理至 EOP。 使用目錄同步作業時，安全清單集合會同步至 Azure AD。

- 使用者信箱中的安全清單集合具有 510 KB 的限制，其中包括所有清單，再加上其他垃圾郵件篩選設定。 如果使用者超過此限制，將會收到類似以下的 Outlook 錯誤訊息：

  > 無法/無法新增至 [伺服器] [垃圾郵件] 清單。 您可以在伺服器上的大小超過所允許的大小。 除非您的垃圾郵件清單縮小為伺服器允許的大小，否則伺服器上的垃圾郵件篩選器將會停用。

  如需此限制及其變更方式的詳細資訊，請參閱[KB2669081](https://support.microsoft.com/help/2669081/outlook-error-indicates-that-you-are-over-the-junk-e-mail-list-limit)。

- EOP 中的同步安全清單集合具有下列同步處理限制：

  - 1024 [安全寄件者] 清單、[安全的收件者] 清單和外部連絡人（如果啟用 [**來自我的連絡人的信任電子郵件**]）的專案總數
  - 500封鎖的寄件者清單與封鎖的網域清單中的專案總數。

  達到1024專案限制時，會發生下列情況：
  
  - 清單會停止接受 PowerShell 和 Outlook 網頁版中的專案，但不會顯示錯誤。

    Outlook 使用者可以繼續加入超過1024個專案，直到達到 Outlook 限制 510 KB 為止。 EOP 篩選傳遞至信箱（郵件流程規則、反欺騙等等）之後，Outlook 可以使用這些額外的專案。

- 透過目錄同步作業，專案會依照下列順序同步到 Azure AD：

  1. 如果已啟用 [**來自我的連絡人的信任電子郵件**]，則為郵件連絡人。
  2. 每當為第一個1024專案進行變更時，安全寄件者清單及安全收件者清單都會加上重複記錄，並依字母順序排序。

  使用第一個1024專案，並在郵件頭中戳相關的資訊。
  
  超過1024的專案（未同步至 Azure AD）是由 Outlook 處理（而不是網頁上的 Outlook），而且不會在郵件頭中標記任何資訊。

如您所見，啟用 [**來自我的連絡人的信任電子郵件**] 設定會減少安全寄件者的數目，以及可同步處理的安全收件者數目。 如果有問題，我們建議使用「群組原則」關閉此功能：

- 檔案名： outlk16。 opax
- 原則設定：**信任來自連絡人的電子郵件**
