---
title: 建立和管理非使用中信箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
ms.custom:
- seo-marvel-apr2020
description: 使用 Microsoft 365 中的非使用中信箱功能，保留已刪除信箱的內容。
ms.openlocfilehash: acd00fedcf0949b7d0c9f85c17039105e9b34821
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100802"
---
# <a name="create-and-manage-inactive-mailboxes"></a>建立和管理非使用中信箱

Microsoft 365 使您可以保留已刪除信箱的內容。 這項功能稱為 [非](inactive-mailboxes-in-office-365.md)使用中信箱。 非使用中的信箱可讓您在離開組織之後，保留離職的員工電子郵件。 在 Office 365 或 Microsoft 365) 中的 [安全性與合規性中心] 中 (建立訴訟保留原則或保留原則時，信箱會變成非使用中，以刪除對應的使用者帳戶之前的信箱。 非使用中信箱的內容會保留在信箱停用的保留期間內，直到未使用中的信箱為止。 這可讓系統管理員、合規性監察官和記錄管理員使用內容搜尋來搜尋和匯出非使用中信箱的內容。 非作用中的信箱無法接收電子郵件，也不會顯示於貴組織的共用通訊錄或其他清單中。
  
> [!IMPORTANT]
> 當我們繼續以保留信箱內容的不同方式投資時，我們宣佈 Exchange 系統管理中心的退休 In-Place 封存。 這表示您應該使用訴訟保留和保留原則來建立非使用中的信箱。 從2020年7月1日起，您將無法在 Exchange Online 中建立新的 In-Place 保留。 不過，您仍然可以變更置於非使用中信箱的 In-Place 保留期間。 不過，從2020年10月1日開始，您將無法變更保留期間。 您只能移除 In-Place 保留才能刪除非使用中的信箱。 在移除保留之前，仍會保留位於 In-Place 暫止的現有非作用中信箱。 如需停用 In-Place 保留的詳細資訊，請參閱 [舊版 eDiscovery tools 的退休](legacy-ediscovery-retirement.md)。
  
## <a name="preparations-before-creating-an-inactive-mailbox"></a>在建立非使用中的信箱之前準備

- 若要讓信箱成為非使用中的信箱，必須將其指派給 Exchange Online Plan 2 授權，以便在信箱刪除之前，封存保留或保留原則可以套用至信箱。 Exchange Online方案2授權屬於 Office 365 企業版 E3 和 E5 訂閱。 如果信箱已被指派 Exchange Online 方案1或 Exchange Online Kiosk 授權 (（分別是 Office 365 E1 及 F1 訂閱的一部分）) ，您必須為其指派個別的 Exchange Online 封存授權，以便在信箱刪除之前，保留可以套用到該信箱。 如需詳細資訊，請參閱[Exchange Online 封存](https://go.microsoft.com/fwlink/p/?LinkId=286153)。

- 刪除對應的使用者帳戶之後，就可以使用與已刪除 Exchange Online 信箱相關聯的授權。 然後，您可以 [將這些授權指派給其他使用者](../admin/manage/assign-licenses-to-users.md)。

- 如果設定保留或保留的訴訟暫止或保留原則 (，但在刪除之前未套用內容) 則信箱的內容將不會遭到保留，也不會被發現。 不過，刪除的信箱可以在刪除之後的30天內復原，但是在30天后會永久刪除信箱及其內容（如果未復原）。

- 如需訴訟暫止的詳細資訊，請參閱 [訴訟暫](/exchange/security-and-compliance/in-place-and-litigation-holds)止。 如需保留原則的詳細資訊，請參閱 [瞭解保留原則和保留標籤](retention.md)。
  
## <a name="create-an-inactive-mailbox"></a>建立非使用中的信箱

使信箱停用包括兩個步驟： 1) 將信箱設為訴訟暫止，或將保留原則套用至它，2) 刪除信箱或對應的使用者帳戶。 信箱停用之後，會保留其內容，直到取消保留原則或保留原則為止。
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-a-retention-policy"></a>步驟1：將信箱設為訴訟暫止或套用保留原則

讓信箱處於訴訟暫止狀態，或套用設定為保留或保留，然後刪除內容的保留原則 () 會在信箱刪除之前，先將內容保留下來。 這兩種類型的保留都會保留所有信箱內容，包括已刪除的專案和已修改專案的原始版本。 已刪除及修改的專案會保留在指定期間內的非使用中信箱中，或是移除已套用至非使用中信箱的保留原則，以永久刪除非使用中的信箱。
  
如果保留已放在信箱上，或已將保留原則套用至信箱，則您只需要刪除步驟2中所述的相對應使用者帳戶。
  
如需將信箱設為訴訟暫止或套用保留原則的逐步程式，請參閱：
  
- [將信箱設定為訴訟資料暫留狀態](create-a-litigation-hold.md)

- [瞭解保留原則和保留標籤](retention.md)

> [!NOTE]
> 針對訴訟保留和保留原則，您可以建立無限期保留或以時間為基礎的保留。 在無限期保留中，非使用中信箱的內容會永遠保留，或直到取消保留或變更保留期間為止。 移除保留或保留原則之後 (假設信箱已在183天前刪除) ，則非作用中的信箱會標示為永久刪除，且信箱的內容將不再保留或可供調查。 在以時間為基礎的保留原則中，您可以指定保留的持續時間。 此持續時間視個別項目而定，會從接收或建立信箱項目的日期開始計算。 信箱專案的保留到期，且該專案移至或位於非使用中信箱的 [可復原的專案] 資料夾中之後，該專案就會永久刪除 (在已刪除專案的保留期間到期時從非使用中信箱) 清除。 
  
### <a name="step-2-delete-the-mailbox"></a>步驟 2：刪除信箱

在信箱保留或已套用保留原則之後，下一步是刪除信箱。 刪除信箱的最佳方式是在 Microsoft 365 系統管理中心刪除對應的使用者帳戶。 如需刪除使用者帳戶的詳細資訊，請參閱 [刪除組織中的使用者](../admin/add-users/delete-a-user.md)。
  
> [!NOTE]
> 您也可以在 Exchange Online PowerShell 中使用 **Remove-Mailbox** Cmdlet 刪除信箱。 如需詳細資訊，請參閱[刪除或還原 Exchange Online 中的使用者信箱](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes)。 
  
## <a name="view-a-list-of-inactive-mailboxes"></a>查看非使用中信箱的清單

若要在您的組織中查看非使用中的信箱清單：

1. 移至 <https://compliance.microsoft.com>，然後使用您組織中的系統管理員帳戶認證來登入。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [**全部顯示**]，然後按一下 [**資訊管理] > 保留**]。

   ![按一下 [保留] 頁面上的 [非使用中信箱] 按鈕。](../media/MCCInactiveMailboxes1.png)

3. 在 [ **保留** ] 頁面上，按一下 [非使用中 **信箱** ] 以顯示非使用中信箱的清單。

4. 選取非使用中的信箱以顯示具有非使用中信箱相關資訊的飛出頁面。

   ![飛出頁面顯示非使用中信箱的詳細資料](../media/MCCInactiveMailboxes2.png)  

您可以按一下 [ ![ 匯出搜尋結果圖示] [ ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **匯出** ]，以查看或下載包含有關組織中非使用中信箱之其他資訊的 CSV 檔案。

或者，您也可以在 Exchange Online PowerShell 中執行下列命令，以顯示非使用中信箱的清單。

```powershell
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

您也可以執行下列命令，將非使用中信箱和其他資訊的清單匯出至 CSV 檔案。 在此範例中，會在目前目錄中建立 CSV 檔案。

```powershell
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```

> [!NOTE]
> 非使用中的信箱可能與使用中的使用者信箱具有相同的 SMTP 位址。 在此情況下， **DistinguishedName** 或 **ExchangeGuid** 屬性的值可以用來唯一識別非使用中的信箱。
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>搜尋和匯出非使用中信箱的內容

您可以使用安全性 & 規範中心中的「內容搜尋」工具，存取非使用中信箱的內容。 在搜尋非使用中的信箱時，您可以建立關鍵字搜尋查詢以搜尋特定項目，也可以傳回非使用中信箱的完整內容。 您可以預覽搜尋結果，或是將搜尋結果匯出為 Outlook 資料 (PST) 檔或個別的電子郵件。 如需搜尋信箱及匯出搜尋結果的逐步程式，請參閱下列主題：
  
- [內容搜尋](content-search.md)

- [匯出搜尋結果](export-search-results.md)

搜尋非作用中信箱時，請注意以下幾點。
  
- 如果內容搜尋包含使用者信箱，且該信箱已變為非使用中，當您在未使用的情況下執行搜尋時，內容搜尋會繼續搜尋非使用中的信箱。

- 在某些情況下，使用者可能會有一個使用中信箱和非使用中的信箱，且該信箱具有相同的 SMTP 位址。 在此情況下，只會搜尋您所選做為內容搜尋位置的特定信箱。 換句話說，如果您將使用者的信箱新增至搜尋中，則不能假設會搜尋其作用中和非使用中的信箱;只會搜尋您明確新增到搜尋中的信箱。

- 我們強烈建議您避免使用具有相同 SMTP 地址的作用中信箱及非作用中信箱。 如果您需要重複使用目前指派給非使用中信箱的 SMTP 位址，建議您復原非使用中的信箱，或將非使用中信箱的內容還原至作用中的信箱 (或封存使用中信箱) ，然後刪除非使用中的信箱。

## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>變更非作用中信箱的保留持續時間

將信箱設為非使用中之後，您可以變更保留期間或套用至非使用中信箱的保留原則。 如需逐步程式，請參閱[變更 Office 365 中非使用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)。
  
## <a name="recover-an-inactive-mailbox"></a>復原非作用中的信箱

如果離職員工回到您的組織，或是聘用新的員工來承擔已離開員工的工作責任，您可以復原非使用中信箱的內容。 當您復原不在作用中的信箱時，信箱轉換成新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。 它會復原之後，非使用中的信箱不存在。 如需還原非使用中信箱時的逐步程式及詳細資訊，請參閱[復原 Office 365 中的非使用中信箱](recover-an-inactive-mailbox.md)。
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>將非使用中信箱的內容還原到另一個信箱

如果另一位員工承擔的是離職員工的工作責任，或是其他人需要存取非使用中信箱的內容，您可以還原 (或合併) 非使用中信箱的內容到現有的信箱。 當您還原非使用中信箱內容複製到另一個信箱。 非使用中的信箱，則會保留與會維持不在作用中的信箱。 使用 eDiscovery 仍可搜尋非使用中的信箱，其內容可以還原至另一個信箱，也可以在日後復原或刪除。 如需逐步程式，請參閱[還原 Office 365 中的非使用中信箱](restore-an-inactive-mailbox.md)。
  
## <a name="delete-an-inactive-mailbox"></a>刪除非作用中的信箱

如果您不再需要保留非使用中信箱的內容，您可以移除停用信箱或移除非使用中信箱所套用的保留原則，以永久刪除非使用中的信箱。 信箱會在您移除保留或保留原則之後保留183天。 在183天后，信箱將會標示為永久刪除，且信箱會變成不可復原。 如果停用的信箱在過去183天內已刪除，您仍然可以復原它。 如需移除保留或保留原則以永久刪除非使用中信箱的逐步程式，請參閱 [刪除非使用中的信箱](delete-an-inactive-mailbox.md)。
