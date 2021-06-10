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
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何將信箱變成非使用中的信箱，保留先前員工的信箱內容。
ms.openlocfilehash: 6aeb10f1557a991523b60b8e8e85a99fc61f4b87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911249"
---
# <a name="overview-of-inactive-mailboxes"></a>非作用中信箱概觀

您的組織可能需要將其保留組織之後保留先前的員工電子郵件。 根據您的組織保留需求，您可能需要幾個月數或年後結束工作，或您可能需要無限期保留信箱內容的保留信箱內容。 無論您需要保留電子郵件多久，都可以建立非使用中的信箱來保留前員工的信箱。

## <a name="what-are-inactive-mailboxes"></a>什麼是不在作用中的信箱？

當員工離開組織 (或前往長期休假) 時，您可以移除其 Microsoft 365 帳戶。 移除帳戶後，該員工的信箱資料會保留30天。 在此期間內，您仍然可以撤銷復原帳戶，以復原信箱資料。 30天之後，會永久移除資料。

不過，如果您的組織需要保留之前員工的信箱內容，您可以將信箱設為非使用中的信箱，將信箱設為訴訟暫止，或將 Microsoft 365 保留原則套用至安全性 & 合規性中心的信箱，然後移除對應的 Microsoft 365 帳戶。 非使用中信箱的內容會保留在封存保留原則的持續期間內，或在刪除信箱之前，保留原則的保留期間。 You can still recover the corresponding user account for a 30-day period. 不過，30天后，非使用中的信箱會保留在 Microsoft 365，直到保留或保留原則移除為止。

> [!IMPORTANT]
> 當我們繼續以保留信箱內容的不同方式投資時，我們宣佈 Exchange 系統管理中心的退休 In-Place 封存。 這表示您應該使用訴訟保留和 Microsoft 365 保留原則，以建立非使用中的信箱。 從2020年7月1日起，您將無法在 Exchange Online 中建立新的 In-Place 保留。 不過，您仍然可以變更置於非使用中信箱的 In-Place 保留期間。 不過，從2020年10月1日開始，您將無法變更保留期間。 您只能移除 In-Place 保留才能刪除非使用中的信箱。 在移除保留之前，仍會保留位於 In-Place 暫止的現有非作用中信箱。 如需停用 In-Place 保留時間的詳細資訊，請參閱 [撤銷舊版 eDiscovery tools](legacy-ediscovery-retirement.md)。

## <a name="inactive-mailboxes-and-microsoft-365-retention-policies"></a>非使用中信箱及 Microsoft 365 保留原則

除了訴訟暫止之外，使用 Microsoft 365 規範中心內的「新 Microsoft 365 保留原則」功能也是讓信箱非使用中的另一種方式。 To use a retention policy to make an inactive mailbox:

- 必須設定它以保留內容或保留，然後刪除內容。 如果保留原則設定為僅刪除內容，則套用原則的信箱在刪除使用者帳戶時不會變成停用狀態。

- 它具有 （因為 Skype 相關的內容會儲存在使用者的信箱中） 可套用到 Exchange 信箱或商務用 Skype位置。

- 它可以是查詢為基礎，讓它會保留在符合搜尋查詢的項目。

如需保留原則的詳細資訊，請參閱 [瞭解保留原則和保留標籤](retention.md)。

如果您使用保留原則來產生非使用中的信箱，Microsoft 365 會繼續處理非使用中信箱的保留原則。 這表示如果保留原則設定來保持不變，然後刪除內容，將移至可復原的項目資料夾保留期間到期時, 和最後清除從非使用中的信箱項目。 如果保留原則未設定為 [已刪除的專案]，則在信箱成為非使用中之前，使用者未永久刪除的專案 () 不會移至 [可復原的專案] 資料夾，而且會在信箱變成非使用中時無限期保留。

您可能會考慮建立專用於非使用中信箱的 Microsoft 365 保留原則。 以下是執行這項工作原因及謹記下列事項。

- 您可以設定保留信箱內容僅只要符合先前員工貴組織的需求所需的保留原則。

- 因為保留原則只會套用至非使用中的信箱，所以識別非使用中信箱是一種很好的方式。

- 您可以快速識別指派給組織中非使用中信箱的保留原則。 這可讓您在必要時，更容易變更保留 (或刪除) 設定。 這也會使永久刪除非使用中的信箱變得更容易，因為您可以使用安全性 & 合規性中心，將其從原則中移除。 否則，您必須使用 Exchange Online PowerShell 移除非使用中信箱的訴訟暫止，或使用安全性 & 規範中心 PowerShell 從整個組織的 Microsoft 365 保留原則中排除非使用中的信箱。

- 如果您專門針對非使用中的信箱建立 Microsoft 365 保留原則，則最多可以將1000個信箱新增至原則。 如果您是大型組織，您可能必須建立一個以上的 Microsoft 365 保留原則，以用於非使用中的信箱。

> [!CAUTION]
> 如果您使用保留原則停用信箱，請勿在刪除對應的使用者帳戶之前，變更或移除信箱 (UPN) 的使用者主要名稱。 此外，請不要變更派生自) UPN 的主要 SMTP 位址 (，或從與信箱關聯的次要 SMTP 地址清單中移除此電子郵件地址，然後再將信箱設為非使用中。 如果您在套用保留原則時變更指派給信箱的 UPN 或電子郵件地址 () 然後刪除使用者帳戶以停用信箱，當您不再需要保留時，您將無法刪除非使用中的信箱。 這是因為您無法使用 UPN 或電子郵件地址 (來移除保留原則中的非使用中信箱，以識別與保留原則最初套用至信箱時存在的非作用中信箱) 不同。 如需刪除非使用中信箱的相關資訊，請參閱[Delete Office 365 中的非使用中信箱](delete-an-inactive-mailbox.md)。

## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>不在作用中信箱和 eDiscovery 案件保留

如果與安全性 & 合規性中心的 eDiscovery 案例相關聯的保留已放在信箱上，然後刪除信箱或使用者帳戶，則信箱會變成非使用中的信箱。 However, we don't recommend using eDiscovery case holds to make a mailbox inactive. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed. In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and then the hold is released or the eDiscovery case is closed (or deleted), the inactive mailbox will be permanently deleted. 此外，您也無法建立以時間為基礎的 eDiscovery 保留。 這表示非使用中信箱中的內容會永遠保留，或直到刪除保留並刪除非作用中信箱為止。 因此，建議使用非使用中信箱的訴訟暫止或保留原則。

如需有關 eDiscovery 案例和保留的詳細資訊，請參閱 [eDiscovery 案例](./get-started-core-ediscovery.md)。

## <a name="inactive-mailboxes-and-labels"></a>非使用中的信箱及標籤

保留標籤可協助您分類組織中的電子郵件資料，以進行管理，並根據該分類強制執行保留規則。 保留標籤可以由使用者手動或由系統管理員手動套用至電子郵件專案，而且電子郵件專案只能有指派單一標籤。 如果使用者信箱中的單一電子郵件專案已獲指派標籤 (而且其設定為保留或保留，然後刪除專案) 且信箱或使用者帳戶已刪除，則信箱會變成非使用中的信箱。 與 eDiscovery 案例保留類似，我們不建議使用保留標籤使信箱成為非使用中。 我們建議您改為使用訴訟暫止或保留原則。 在保留標籤的情況下，您可能不會意識到已將保留標籤套用至電子郵件專案，當您刪除使用者帳戶時，不小心會產生非使用中的信箱。

如需保留原則和保留標籤的詳細資訊，請參閱[瞭解 Office 365 中的保留原則和保留標籤](retention.md)。

## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>非使用中的信箱和自動展開的封存

無法復原或還原使用自動展開封存設定的非使用中信箱。 在需要從自動展開封存的非使用中信箱復原資料的情況下，建議您使用內容搜尋工具從信箱中匯出資料，然後匯入至另一個信箱。 如需搜尋非使用中信箱及匯出搜尋結果的逐步指示，請參閱：

- [內容搜尋](content-search.md)

- [匯出內容搜尋結果](export-search-results.md)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>非使用中信箱和 Exchange MRM 保留原則

如果 Exchange 保留原則 (通訊記錄管理或 MRM，Exchange Online) 中的功能會套用至非使用中的信箱時，任何使用「**刪除** 保留動作」設定之保留標記的刪除原則 (都會繼續在非使用中的信箱上進行處理。 這表示與刪除原則標記的項目要移至 [可復原的項目] 資料夾保留期間到期時。 保留期間到期時將這些項目已清除從非使用中的信箱。 如果不在作用中信箱的未指定保留持續時間，則會無限期保留復原的項目] 資料夾中的項目。

相反地，任何封存原則 (，其是以指派給非使用中信箱之保留原則中所包含的 **MoveToArchive** 保留動作) 所設定的保留標記會被忽略。 這表示使用封存原則標記的非作用中信箱中的專案會在保留期間到期時保留在主要信箱中。 它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。 他們將會無限期保留。

## <a name="creating-an-inactive-mailbox"></a>建立非使用中的信箱

若要將信箱設為非使用中狀態，必須將其指派給 Exchange Online Plan 2 授權 (或 Exchange Online 方案1授權與 Exchange Online 封存附加元件授權) ，這樣才能將訴訟暫止或 Microsoft 365 保留原則套用至信箱，然後再加以刪除。 刪除使用者帳戶之後，就可以將任何與該使用者帳戶相關聯的 Exchange Online 授權指派給新的使用者。

下表摘要說明程序，讓不同保留案例的非使用中信箱。 如需詳細資訊，請參閱 [管理非](create-and-manage-inactive-mailboxes.md)使用中的信箱。

****

|自。。。|執行這項作業...|結果|
|---|---|---|
|只有在員工離職之後無限期保留信箱內容|將信箱設為訴訟暫止，或套用設定為保留內容) 信箱的 Microsoft 365 保留原則 (。 <br/> 請勿指定訴訟暫止保留期間或未設定保留原則，以刪除專案。 此外，您也可以使用保留原則永遠保留專案。 <br/> 移除使用者的 Microsoft 365 帳戶。|非使用中信箱中的所有內容（包括 [可復原的專案] 資料夾中的專案）都會無限期保留。|
|信箱內容保留特定的一段之後員工離職然後予以刪除|將 Microsoft 365 保留原則套用至信箱。 <br/> 在保留期間到期時，設定保留原則以保留，然後刪除專案。 <br/> 移除使用者的 Microsoft 365 帳戶。|當信箱專案的保留期間到期時，該專案會移至 [可復原的專案] 資料夾，當 Exchange) 信箱的已刪除專案保留期間 (到期時，它會永久刪除 (從非使用中信箱中清除) 。 Microsoft 365 保留原則的保留期間，可根據原始日期來設定信箱專案的接收或建立日期，或上次修改時間。|
|

**附注：** 如果已在信箱上設定訴訟資料暫留，或是設定保留或保留的 Microsoft 365 保留原則 (，且已將內容刪除) 已套用至信箱，則您只需要刪除對應的使用者帳戶，即可建立非使用中的信箱。

## <a name="managing-inactive-mailboxes"></a>管理非作用中信箱

您讓信箱成為非使用中之後，您可以在非使用中的信箱上執行各種管理工作。

- **變更非使用中信箱的保留期間。** 信箱變為非使用中之後，您可以變更保留期間的訴訟暫止或 Microsoft 365 保留原則套用至非使用中的信箱。 如需逐步程式，請參閱 [變更非使用中信箱的保留期間](change-the-hold-duration-for-an-inactive-mailbox.md)。

  > [!NOTE]
  > 您無法將其他保留原則套用至非使用中的信箱。 您只可以變更已套用至非使用中信箱之現有保留原則的保留期間。

- **復原非使用中的信箱。** 如果離職員工 (或員工休假休假) 會傳回您的組織，或是聘用新的員工來承擔離職員工的工作責任，您可以復原非使用中信箱的內容。 當您復原非使用中的信箱時，信箱會轉換成新的信箱、非使用中信箱的內容和資料夾結構會保留，而且信箱會連結至新的使用者帳戶。 它會復原之後，非使用中的信箱不存在。 如需逐步程式和復原非使用中的信箱時發生的資訊，請參閱 [復原非使用中的信箱](recover-an-inactive-mailbox.md)。

  > [!NOTE]
  > 如果您復原指派給保留原則的非作用中信箱，且保留鎖定 (稱為 *鎖定的保留原則*) ，則會將復原的信箱指派給相同的鎖定保留原則。 如果您復原指派給保留原則但未保留鎖定的非使用中信箱，則會從解除鎖定的保留原則中移除復原的信箱。 不過，已在復原的信箱上啟用訴訟暫止，以防止刪除超出特定時期之內容的任何整個組織保留原則刪除信箱內容。

- **還原非使用中的信箱。** 如果另一位員工承擔的是離職員工的工作責任，或是其他人需要存取非使用中信箱的內容，您可以還原 (或合併) 非使用中信箱的內容到現有的信箱。 當您還原非使用中信箱內容複製到另一個信箱。 非使用中的信箱，則會保留與會維持不在作用中的信箱。 非使用中的信箱仍可使用 eDiscovery 工具進行搜尋，其內容可以還原至另一個信箱，而且可以在以後復原或刪除。 如需逐步程式，請參閱 [還原非使用中的信箱](restore-an-inactive-mailbox.md)。

- **刪除非使用中的信箱。** 當您不再需要保留非使用中信箱的內容時，您可以移除所有保留原則或 Microsoft 365 套用至非使用中信箱的保留原則，永久刪除該信箱。 如果信箱進行非使用中超過 30 天之內，它會標示為永久刪除之後移除保留。 如果信箱可在過去 30 天內不在作用中，您可以使其成為使用一次之後移除保留或保留原則。 如需逐步程式，請參閱 [刪除非使用中的信箱](delete-an-inactive-mailbox.md)。