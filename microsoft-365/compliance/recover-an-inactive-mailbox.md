---
title: 復原非作用中的信箱
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
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
ms.custom: seo-marvel-apr2020
description: 瞭解如何將 Office 365 中非使用中信箱的內容，將其轉換成包含非使用中信箱內容的新信箱。
ms.openlocfilehash: e7f5ea9e3d47bf6b7ee6de495d2f5f47984cdf8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926171"
---
# <a name="recover-an-inactive-mailbox"></a>復原非作用中的信箱

非使用中的信箱 (是一種虛刪除的信箱) ，用來在離開組織之後保留離職員工的電子郵件。 如果該員工回到您的組織，或另一個員工採取離職員工的工作職責，有兩種方式可以讓使用者使用非使用中信箱的內容：

- **復原非使用中的信箱。** 如果離職員工回到您的組織，或聘用新的員工來承擔離職員工的工作責任，您可以復原非使用中信箱的內容。 這個方法會將非作用中的信箱轉換成包含非使用中信箱內容的新的 active 信箱。 它會復原之後，非使用中的信箱不存在。 本主題中的程式說明此方法。

- **還原非使用中的信箱。** 如果另一位員工承擔的是離職員工的工作責任，或是其他使用者需要存取非使用中信箱的內容，您可以還原 (或合併) 非使用中信箱的內容到現有的信箱。 您也可以從非使用中的信箱還原封存。 如需此方法的程式，請參閱[還原 Office 365 中的非使用中信箱](restore-an-inactive-mailbox.md)。

請參閱 [詳細資訊](#more-information) 一節，以取得復原和還原非使用中信箱之差異的詳細資訊，以及復原非使用中信箱時所發生狀況的描述。

> [!NOTE]
> 您無法復原或還原已設定為自動展開封存的非使用中信箱。 如果您需要從自動展開封存的非使用中信箱復原資料，請使用內容搜尋來匯出信箱中的資料，然後匯入至另一個信箱。 如需相關指示，請參閱下列主題：
>
> - [內容搜尋](content-search.md)
> - [匯出內容搜尋結果](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a>復原非使用中信箱的需求

- 您必須使用 Exchange Online PowerShell 復原非使用中的信箱。 您無法使用 Exchange 系統管理中心 (EAC) 。 如需逐步指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 執行下列命令，以取得組織中非使用中信箱的身分識別資訊。

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  使用此命令傳回的資訊，以復原特定的非使用中信箱。

## <a name="recover-inactive-mailboxes"></a>復原非使用中的信箱

使用 **New-Mailbox** Cmdlet 搭配  *InactiveMailbox*  參數可復原非使用中的信箱。

1. 建立包含非使用中信箱之屬性的變數。

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > 在上述命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 屬性的值來識別非使用中的信箱。 這兩個屬性對於組織中的每個信箱都是唯一的，而使用中和非使用中的信箱可能會有相同的主要 SMTP 位址。

2. 這個範例會使用在上述命令中取得的屬性，並將非使用中的信箱恢復為使用者王小姐 Beebe 的使用中信箱。 請確定為  *Name*  和  *MicrosoftOnlineServicesID*  參數指定的值在您的組織中是唯一的。

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   已復原之非使用中信箱的主要 SMTP 位址，會具有與  *MicrosoftOnlineServicesID*  參數所指定的值相同的值。

復原非使用中的信箱之後，也會建立新的使用者帳戶。 您必須指派授權來啟用此使用者帳戶。 若要在 Microsoft 365 系統管理中心中指派授權，請參閱[同時新增使用者與指派授權](../admin/add-users/add-users.md)。

## <a name="more-information"></a>其他資訊

- **復原和還原非使用中信箱的主要差異為何？** 當您復原不在作用中的信箱時，信箱轉換成新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。 復原之後，非使用中的信箱不再存在，對新信箱中的內容所做的任何變更，都會影響原始在非使用中信箱中的內容。 相反地，當您還原非使用中的信箱時，內容只會複製到另一個信箱。 非使用中的信箱會保留並保持非作用中的信箱。 對目標信箱中的內容所做的任何變更，都不會影響保留在非使用中信箱的原始內容。 使用 In-Place eDiscovery 仍可搜尋非使用中的信箱，其內容可以還原至另一個信箱，也可以在稍後的日期復原或刪除。

- **當您復原非使用中的信箱時，會發生什麼事？** 當您復原非使用中的信箱時，會發生下列情況：

  - 已套用至非使用中信箱的保留，會根據對非使用中信箱的保留類型進行變更或移除。

    - **訴訟暫止。** 如果已啟用非使用中信箱的訴訟暫止，它會從復原的信箱中移除。

    - 已從復原的信箱中移除 **In-Place 保留** In-Place 保留。 這表示已復原的信箱會從任何 In-Place 保留或 In-Place eDiscovery 搜尋中移除成為來源信箱。

    - **使用保留鎖定 Microsoft 365 保留原則。** 如果將非作用中的信箱指派給保留原則，且保留鎖定 (稱為「 *鎖定保留原則* 」) 時，已復原的信箱會被指派至相同的鎖定保留原則。 如需已鎖定保留原則的詳細資訊，請參閱 [[使用保留鎖定來限制保留原則和保留標籤原則的變更](retention-preservation-lock.md)。

    - **Microsoft 365 保留原則，但不保留鎖定。** 非作用中的信箱會從套用至它的任何已解除鎖定的 Microsoft 365 保留原則中移除。 不過，已在復原的信箱上啟用訴訟暫止，以防止刪除超出特定時期之內容的任何整個組織保留原則刪除信箱內容。 您可以保留或移除訴訟暫止狀態。 如需詳細資訊，請參閱 [建立訴訟暫](create-a-litigation-hold.md)止。

  - 由 **RetainDeletedItemsFor** 信箱) 屬性定義的單一專案復原週期 (會設定為30天。 一般來說，在 Exchange Online 中建立新的信箱時，此保留期間會設定為14天。 將此值設定為30天的最大值，可讓您更多時間來復原已永久刪除 (或從非使用中信箱) 中清除的任何資料。 您也可以停用單一專案復原，或將單一專案恢復週期設回預設值14天。 如需詳細資訊，請參閱 [為信箱啟用或停用單一項目復原](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery)。

  - 啟用保留功能，保留期間設定為30天。 這表示預設 Exchange 保留原則，以及指派給新信箱的任何整個組織或全 Exchange Microsoft 365 保留原則，都不會處理30天。 這可讓退回的員工或已復原的非作用中信箱時間的新擁有者管理舊郵件。 否則，Exchange 或 Microsoft 365 保留原則可能會刪除舊的信箱專案 (或將專案移至封存信箱（如果已啟用) ，其已根據 Exchange 或 Microsoft 365 保留原則所設定的設定而過期）。 30天后，保留狀態會到期， **RetentionHoldEnabled** 信箱屬性設定為 **False**，受管理的資料夾助理會開始處理指派給信箱的原則。 如果您不需要這種額外時間，您只需要移除保留功能。 或者，您可以使用 **Set-Mailbox-EndDateForRetentionHold** 命令來增加保留功能的持續時間。 如需詳細資訊，請參閱 [將信箱設為保留狀態](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)。

- **如果您需要保留非使用中信箱的原始狀態，請在復原的信箱上放置保留。** 若要防止新的信箱擁有者或保留原則永久刪除已復原的非使用中信箱的任何郵件，您可以將信箱設為訴訟暫止狀態。 如需詳細資訊，請參閱 [建立訴訟暫](./create-a-litigation-hold.md)止。

- **復原非使用中的信箱時，可以使用哪個使用者識別碼？** 當您復原非使用中的信箱時，您為  *MicrosoftOnlineServicesID*  參數指定的值可能與非使用中信箱的原始值不同。 您也可以使用原始的使用者識別碼。 但如先前所述，當您復原非使用中的信箱時，請確定用於  *Name*  和  *MicrosoftOnlineServicesID*  的值在組織內是唯一的。

- **非使用中信箱的信箱保留期間尚未到期時，該怎麼辦？** 如果非使用中的信箱已虛刪除30天以內，則您無法使用 **New-Mailbox-InactiveMailbox** 命令來復原它。 您必須還原對應的使用者帳戶，以復原。 如需詳細資訊，請參閱 [刪除組織中的使用者](../admin/add-users/delete-a-user.md)。

- **如何知道非使用中信箱的虛刪除信箱保留期間是否已過期？** 執行下列命令。

  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```

  如果 **ExternalDirectoryObjectId** 屬性沒有值，表示信箱保留期間已到期，您可以執行 **New-Mailbox-InactiveMailbox** 命令來復原非使用中的信箱。 如果 **ExternalDirectoryObjectId** 屬性的值為虛刪除的信箱保留期間尚未到期，您必須還原使用者帳戶以復原信箱。 請參閱[刪除貴組織中的使用者](../admin/add-users/delete-a-user.md)。

- **在復原非使用中的信箱之後，請考慮啟用封存信箱。** 這可讓傳回的使用者或新員工將舊郵件移至封存信箱。 而且當保留狀態到期時，屬於預設 Exchange 保留原則一部分指派給 Exchange Online 信箱的封存原則，會將兩年或更舊的專案移至封存信箱。 如果您未啟用封存信箱，則兩年以前的專案會保留在使用者的主要信箱中。 如需詳細資訊，請參閱 [啟用封存信箱](enable-archive-mailboxes.md)。