---
title: 非作用中信箱概觀
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
description: 深入瞭解如何將信箱變成非使用中的信箱，針對先前的員工保留信箱內容。 若要這麼做，您可以將信箱設為訴訟暫止，或將 Microsoft 365 保留原則套用至信箱，然後再移除對應的 Microsoft 365 帳戶。
ms.openlocfilehash: ab89f8a7262dcd4197c52275558d95f8053d2c9b
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679047"
---
# <a name="overview-of-inactive-mailboxes"></a>非作用中信箱概觀

您的組織可能需要將其保留組織之後保留先前的員工電子郵件。 根據您的組織保留需求，您可能需要幾個月數或年後結束工作，或您可能需要無限期保留信箱內容的保留信箱內容。 不論您需要保留電子郵件的時間為何，您可以建立非使用中的信箱以保留之前員工的信箱。 
  
## <a name="what-are-inactive-mailboxes"></a>什麼是不在作用中的信箱？

當員工離開您的組織（或進行長期的請假時），您可以移除其 Microsoft 365 帳戶。 移除帳戶後，該員工的信箱資料會保留30天。 在此期間內，您仍然可以撤銷復原帳戶，以復原信箱資料。 30天之後，會永久移除資料。
  
不過，如果您的組織需要保留之前員工的信箱內容，您可以將信箱設為非使用中的信箱，將信箱設為訴訟暫止，或將 Microsoft 365 保留原則套用至安全性 & 合規性中心的信箱，然後移除對應的 Microsoft 365 帳戶。 非使用中信箱的內容會保留在封存保留原則的持續期間內，或在刪除信箱之前，保留原則的保留期間。 You can still recover the corresponding user account for a 30-day period. 不過，30天后，非作用中的信箱會保留在 Microsoft 365 中，直到解除保留或保留原則為止。 
  
> [!IMPORTANT]
> 當我們繼續以保留信箱內容的不同方式投資時，我們宣佈在 Exchange 系統管理中心中封存 In-Place 的退休。 這表示您應該使用訴訟保留和 Microsoft 365 保留原則，以建立非使用中的信箱。 從2020年7月1日起，您將無法在 Exchange Online 中建立新的 In-Place 保留。 不過，您仍然可以變更置於非使用中信箱的 In-Place 保留期間。 不過，從2020年10月1日開始，您將無法變更保留期間。 您只能移除 In-Place 保留才能刪除非使用中的信箱。 在移除保留之前，仍會保留位於 In-Place 暫止的現有非作用中信箱。 如需停用 In-Place 保留時間的詳細資訊，請參閱[撤銷舊版 eDiscovery tools](legacy-ediscovery-retirement.md)。
  
## <a name="inactive-mailboxes-and-microsoft-365-retention-policies"></a>非使用中的信箱和 Microsoft 365 保留原則

除了訴訟暫止之外，使用安全性 & 規範中心內的新 Microsoft 365 保留原則功能，也就是讓信箱成為非使用中信箱的另一種方式。 To use a retention policy to make an inactive mailbox: 
  
- 必須設定它以保留內容或保留，然後刪除內容。 如果保留原則設定為僅刪除內容，則套用原則的信箱在信箱刪除時不會變成停用狀態。

- 它具有 （因為 Skype 相關的內容會儲存在使用者的信箱中） 可套用到 Exchange 信箱或商務用 Skype位置。
  
- 它可以是查詢為基礎，讓它會保留在符合搜尋查詢的項目。

如需設定保留原則的詳細資訊，請參閱[保留原則一覽](retention-policies.md)。
  
如果您使用保留原則來製作非使用中的信箱，Microsoft 365 會繼續處理非使用中信箱的保留原則。 這表示如果保留原則設定來保持不變，然後刪除內容，將移至可復原的項目資料夾保留期間到期時, 和最後清除從非使用中的信箱項目。 如果保留原則未設定為 [已刪除的專案]，則使用者未永久刪除的專案（信箱未使用之前）不會移至 [可復原的專案] 資料夾，而且會在信箱變成非使用中時無限期保留。 
  
您可以考慮針對非使用中的信箱，專門建立 Microsoft 365 保留原則。 以下是執行這項工作原因及謹記下列事項。
  
- 您可以設定保留信箱內容僅只要符合先前員工貴組織的需求所需的保留原則。

- 因為保留原則只會套用至非使用中的信箱，所以識別非使用中信箱是一種很好的方式。

- 您可以快速識別指派給組織中非使用中信箱的保留原則。 這可讓您更容易變更保留（或刪除）設定（必要時）。 這也會使永久刪除非使用中的信箱變得更容易，因為您可以使用安全性 & 合規性中心，將其從原則中移除。 否則，必須使用 Exchange Online PowerShell 移除非使用中信箱的訴訟暫止，或使用安全性 & 規範中心 PowerShell 從整個組織的 Microsoft 365 保留原則中排除非使用中的信箱。
    
- 如果您專門針對非使用中的信箱建立 Microsoft 365 保留原則，則最多可以將1000信箱新增至原則。 如果您是大型組織，您可能必須建立一個以上的 Microsoft 365 保留原則，以用於非使用中的信箱。

> [!CAUTION]
> 如果您使用保留原則停用信箱，請不要在刪除對應的使用者帳戶之前，變更或移除信箱的使用者主要名稱（UPN）。 此外，請不要變更主要 SMTP 位址（派生自 UPN），或從與信箱相關聯的次要 SMTP 地址清單中移除此電子郵件地址，然後再將信箱設為非使用中。 如果您變更 UPN 或電子郵件地址（在套用保留原則時已指派給信箱），然後刪除使用者帳戶以停用信箱，當您不再需要保留時，您將無法刪除非使用中的信箱。 這是因為您無法使用 UPN 或電子郵件地址（識別非使用中的信箱）從保留原則中移除非使用中的信箱，這與保留原則最初套用至信箱時所存在的信箱不同。 如需刪除非使用中信箱的詳細資訊，請參閱[刪除 Office 365 中的非使用中信箱](delete-an-inactive-mailbox.md)。
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>不在作用中信箱和 eDiscovery 案件保留

如果與安全性 & 合規性中心的 eDiscovery 案例相關聯的保留已放在信箱上，然後刪除信箱或使用者帳戶，則信箱會變成非使用中的信箱。 However, we don't recommend using eDiscovery case holds to make a mailbox inactive. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed. In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and then the hold is released or the eDiscovery case is closed (or deleted), the inactive mailbox will be permanently deleted. 此外，您也無法建立以時間為基礎的 eDiscovery 保留。 這表示非使用中信箱中的內容會永遠保留，或直到刪除保留並刪除非作用中信箱為止。 因此，建議使用非使用中信箱的訴訟暫止或保留原則。
  
如需有關 eDiscovery 案例和保留的詳細資訊，請參閱[eDiscovery 案例](ediscovery-cases.md)。

## <a name="inactive-mailboxes-and-labels"></a>非使用中的信箱及標籤

標籤可協助您分類組織中的電子郵件資料，以進行管理，並根據該分類強制執行保留規則。 標籤可以套用至電子郵件項目由使用者手動或自動將管理員及電子郵件項目只能有單一標籤指派給它。 如果使用者信箱中的單一電子郵件專案已指派標籤（而且已設定為保留或保留，然後刪除該專案），而且信箱或使用者帳戶已被刪除，則信箱會變成非使用中的信箱。 類似於 eDiscovery 案件保留，我們不建議使用標籤來讓信箱成為非使用中。 我們建議您改為使用訴訟暫止或保留原則。 在 [標籤] 的情況下，您可能不會意識到已套用至電子郵件專案的標籤，當您刪除使用者帳戶時，不小心產生非使用中的信箱。 
  
如需標籤的詳細資訊，請參閱 ＜ [Overview of Office 365 中的標籤](labels.md)。
  
## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>非使用中的信箱和自動展開的封存

無法復原或還原使用自動展開封存設定的非使用中信箱。 在需要從自動展開封存的非使用中信箱復原資料的情況下，建議您使用內容搜尋工具從信箱中匯出資料，然後匯入至另一個信箱。 如需搜尋非使用中信箱及匯出搜尋結果的逐步指示，請參閱：

- [Office 365 中的內容搜尋](https://docs.microsoft.com/microsoft-365/compliance/content-search)

- [匯出內容搜尋結果](https://docs.microsoft.com/microsoft-365/compliance/export-search-results)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>非使用中信箱和 Exchange MRM 保留原則

如果 Exchange 保留原則（[通訊記錄管理] 或 [MRM] 功能在 Exchange Online 中）套用至非使用中時，則會繼續在非使用中的信箱上處理任何刪除原則（即使用 [**刪除**保留] 動作設定的保留標記）。 這表示與刪除原則標記的項目要移至 [可復原的項目] 資料夾保留期間到期時。 保留期間到期時將這些項目已清除從非使用中的信箱。 如果不在作用中信箱的未指定保留持續時間，則會無限期保留復原的項目] 資料夾中的項目。 
  
相反地，會忽略指派給非使用中信箱之保留原則中所包含的任何封存原則（也就是設定為**MoveToArchive**保留動作的保留標記）。 這表示使用封存原則標記的非作用中信箱中的專案會在保留期間到期時保留在主要信箱中。 它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。 他們將會無限期保留。 
  
## <a name="creating-an-inactive-mailbox"></a>建立非使用中的信箱

若要將信箱設為非使用中狀態，必須將其指派為 Exchange Online Plan 2 授權（或 exchange online Plan 1 授權與 Exchange Online 封存附加元件授權），這樣才能將訴訟暫止或 Microsoft 365 保留原則套用至信箱，然後再將其刪除。 在刪除信箱之後，就可以將任何與其相關聯的 Exchange Online 授權指派給新的使用者。
  
下表摘要說明程序，讓不同保留案例的非使用中信箱。 如需詳細資訊，請參閱[管理非](create-and-manage-inactive-mailboxes.md)使用中的信箱。
  
|**自。。。**|**執行此動作 .。。**|**結果**|
|:-----|:-----|:-----|
|只有在員工離職之後無限期保留信箱內容  <br/> | 將信箱設為訴訟暫止，或將 Microsoft 365 保留原則（設定為保留內容）套用至信箱。  <br/>  請勿指定訴訟暫止保留期間或未設定保留原則，以刪除專案。 此外，您也可以使用保留原則永遠保留專案。  <br/>  移除使用者的 Microsoft 365 帳戶。  <br/> |非使用中信箱中的所有內容（包括 [可復原的專案] 資料夾中的專案）都會無限期保留。  <br/> |
|信箱內容保留特定的一段之後員工離職然後予以刪除  <br/> | 將 Microsoft 365 保留原則套用至信箱。  <br/>  在保留期間到期時，設定保留原則以保留，然後刪除專案。  <br/>  移除使用者的 Microsoft 365 帳戶。  <br/> |當信箱專案的保留期間到期時，該專案會移至 [可復原的專案] 資料夾，當已刪除的專案保留期間（適用于 Exchange 信箱）到期時，它會永久刪除（清除）的非使用中信箱。 Microsoft 365 保留原則的保留期間可根據原始日期來設定信箱專案的接收或建立時間，或上次修改時間。  <br/> |
   
**附注：** 如果已在信箱上設定訴訟資料暫留，或是 Microsoft 365 保留原則（已設定為保留或保留，然後刪除內容）已套用至信箱，您只需要刪除對應的使用者帳戶，即可建立非使用中的信箱。 
  
## <a name="managing-inactive-mailboxes"></a>管理非使用中信箱

您讓信箱成為非使用中之後，您可以在非使用中的信箱上執行各種管理工作。
  
- **變更非使用中信箱的保留期間。** 將信箱設為非使用中之後，您可以變更已套用至非使用中信箱的訴訟暫止或 Microsoft 365 保留原則的保留期間。 如需逐步程式，請參閱[變更非使用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)。

  > [!NOTE]
  > 您無法將其他保留原則套用至非使用中的信箱。 您只可以變更已套用至非使用中信箱之現有保留原則的保留期間。
    
- **復原非使用中的信箱。** 如果離職員工（或請假休假）傳回給您的組織，或是雇用新的員工來承擔離職員工的工作責任，您可以復原非使用中信箱的內容。 當您復原非使用中的信箱時，信箱會轉換成新的信箱、非使用中信箱的內容和資料夾結構會保留，而且信箱會連結至新的使用者帳戶。 它會復原之後，非使用中的信箱不存在。 如需逐步程式和復原非使用中的信箱時發生的資訊，請參閱[復原非使用中的信箱](recover-an-inactive-mailbox.md)。

  > [!NOTE]
  > 如果您使用保留鎖定（稱為*鎖定的保留原則*）來復原指派給保留原則的非使用中信箱，則會將復原的信箱指派至相同的鎖定保留原則。 如果您復原指派給保留原則但未保留鎖定的非使用中信箱，則會從解除鎖定的保留原則中移除復原的信箱。 不過，已在復原的信箱上啟用訴訟暫止，以防止刪除超出特定時期之內容的任何整個組織保留原則刪除信箱內容。

- **還原非使用中的信箱。** 如果另一位員工承擔的是離職員工的工作責任，或是其他人需要存取非使用中信箱的內容，您可以將非使用中信箱的內容還原（或合併）到現有的信箱。 當您還原非使用中信箱內容複製到另一個信箱。 非使用中的信箱，則會保留與會維持不在作用中的信箱。 非使用中的信箱仍可使用 eDiscovery 工具進行搜尋，其內容可以還原至另一個信箱，而且可以在以後復原或刪除。 如需逐步程式，請參閱[還原非使用中的信箱](restore-an-inactive-mailbox.md)。
    
- **刪除非使用中的信箱。** 當您不再需要保留非使用中信箱的內容時，您可以移除所有保留原則或 Microsoft 365 保留原則套用至非使用中的信箱，永久刪除該信箱。 如果信箱進行非使用中超過 30 天之內，它會標示為永久刪除之後移除保留。 如果信箱可在過去 30 天內不在作用中，您可以使其成為使用一次之後移除保留或保留原則。 如需逐步程式，請參閱[刪除非使用中的信箱](delete-an-inactive-mailbox.md)。
