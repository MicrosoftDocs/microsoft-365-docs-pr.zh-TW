---
title: 在 Exchange Online 中的虛刪除信箱上放置 In-Place
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何為虛刪除的信箱建立 In-Place 保留，使其成為非使用中的信箱，並保留其內容。
ms.openlocfilehash: 638cc0554f216a0cb552c1f8eacef3d692d9f792
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423764"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>在 Exchange Online 中的虛刪除信箱上放置 In-Place

瞭解如何為虛刪除的信箱建立 In-Place 保留，使其成為非使用中的信箱，並保留其內容。 然後，您可以使用 Microsoft eDiscovery 工具來搜尋非使用中的信箱。

> [!IMPORTANT]
> 當我們繼續以保留信箱內容的不同方式投資時，我們宣佈 Exchange 系統管理中心 (EAC) 的退休 In-Place。 從2020年7月1日起，您將無法在 Exchange Online 中建立新的 In-Place 保留。 不過，您仍然可以管理 EAC 中的 In-Place，或是使用 Exchange Online PowerShell 中的 **Set-MailboxSearch** Cmdlet 來管理。 不過，從2020年10月1日開始，您將無法管理 In-Place 保留。 您只會在 EAC 中或使用 **Remove-MailboxSearch** Cmdlet 中移除它們。 如需停用 In-Place 保留的詳細資訊，請參閱 [舊版 eDiscovery tools 的退休](legacy-ediscovery-retirement.md)。
  
您可能會有這樣的情況：某人已離開您的組織，而且其對應的使用者帳戶和信箱已遭刪除。 之後，您就會發現信箱中的資訊必須保留。 您可以做什麼？ 如果已刪除的信箱保留期間尚未到期，您可以將 In-Place 保留已刪除的信箱 (稱為虛刪除的信箱 ) ，並使其成為非使用中的信箱。 非使用中的  *信箱*  會在使用者離開組織之後，用來保留離職員工的電子郵件。 非使用中信箱的內容會保留在所做的 In-Place 保留期間內，在未使用中時，會將其放在虛刪除信箱上。 將信箱設為非作用中之後，您可以使用 Exchange Online 中的 In-Place eDiscovery、安全性 & 規範中心的內容搜尋或 SharePoint Online 中的 eDiscovery 中心來搜尋信箱。 
  
> [!NOTE]
> 在 Exchange Online 中，虛刪除的信箱是已刪除但可在特定保留期間內復原的信箱。 Exchange Online 中的虛刪除信箱保留期間是30天。 這表示信箱可以復原 (，或在30天內) 被刪除，使非作用中的信箱得以復原。 30天后，虛刪除的信箱會標示為永久刪除，且無法復原或設為非使用中。 
  
## <a name="requirements-for-in-place-holds"></a>In-Place 保留的需求

- 您必須在 Windows PowerShell 中使用 **New-MailboxSearch** 指令程式，以便在虛刪除的信箱上進行 In-Place 保留。 您無法使用 Exchange 系統管理中心 (EAC) 或 SharePoint Online 中的 eDiscovery Center。 

- 若要了解如何使用 Windows PowerShell 連線到 Exchange Online，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 執行下列命令，以取得組織中虛刪除信箱的身分識別資訊。 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- 如需非使用中信箱的詳細資訊，請參閱 [Office 365 中的非使用中信箱概覽](inactive-mailboxes-in-office-365.md)。

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>在虛刪除的信箱上放置 In-Place，使其成為非使用中的信箱

使用 **New-MailboxSearch** Cmdlet 將虛刪除的信箱設為非使用中的信箱。 如需詳細資訊，請參閱 [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)。
  
1. 建立包含虛刪除信箱之屬性的變數。

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > 在上述命令中，使用 **DistinguishedName** 或 **ExchangeGuid** 屬性的值來識別虛刪除的信箱。 這兩個屬性對於您組織中的每個信箱都是唯一的，而使用中信箱和虛刪除的信箱可能會有相同的主要 SMTP 位址。 
  
2. 建立 In-Place 保留並將它放在虛刪除的信箱。 在此範例中，不會指定保留期間。 這表示專案會無限期保留，或直到從非使用中的信箱移除保留為止。

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   您也可以在建立 In-Place 保留時，指定保留期間。 這個範例會將非使用中信箱的專案保留大約7年。

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. 片刻之後，請執行下列其中一個命令，以確認虛刪除的信箱是非作用中的信箱。

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    或者
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>其他資訊

在您將虛刪除的信箱變為非使用中信箱之後，您可以使用許多方式來管理信箱。 如需詳細資訊，請參閱：
  
- [變更非使用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)

- [復原非使用中的信箱](recover-an-inactive-mailbox.md)

- [還原非使用中的信箱](restore-an-inactive-mailbox.md)

- 移除保留) [以刪除非使用中的信箱](delete-an-inactive-mailbox.md) (
