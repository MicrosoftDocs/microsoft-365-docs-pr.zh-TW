---
title: Office 365 中非活动邮箱概述
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
description: 了解如何通过将邮箱转换为非活动邮箱来保留前员工的邮箱内容。 为此，可以通过将邮箱置于诉讼保留状态或将 Office 365 保留策略应用于邮箱，然后删除相应的 Office 365 帐户来执行此操作。
ms.openlocfilehash: acfe0a3d8f3865cf0e30a938970235bf31dfbce4
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076271"
---
# <a name="overview-of-inactive-mailboxes-in-office-365"></a>Office 365 中非活动邮箱概述

您的組織可能需要將其保留組織之後保留先前的員工電子郵件。 根據您的組織保留需求，您可能需要幾個月數或年後結束工作，或您可能需要無限期保留信箱內容的保留信箱內容。 无论您需要保留电子邮件多长时间，都可以在 Office 365 中创建非活动邮箱，以保留前员工的邮箱。 
  
## <a name="what-are-inactive-mailboxes"></a>什麼是不在作用中的信箱？

当员工离开您的组织（或请长假）时，可以删除其 Office 365 帐户。 帐户删除后，员工的邮箱数据将保留 30 天。 在此期间，您仍可以通过取消删除帐户来恢复邮箱数据。 30 天后，数据将被永久删除。
  
但是，如果您的组织需要保留前员工的邮箱内容，则可以通过将邮箱置于诉讼保留状态或将 Office 365 保留策略应用于安全&合规中心的邮箱，将邮箱转换为非活动邮箱然后删除相应的 Office 365 帐户。 The contents of an inactive mailbox are retained for the duration of the Litigation Hold placed on the mailbox or the retention period of the Office 365 retention policy applied to it before the mailbox was deleted. You can still recover the corresponding user account for a 30-day period. 但是，30 天后，非活动邮箱将保留在 Office 365 中，直到删除保留或保留策略。 
  
> [!NOTE]
> 我們已將 2017 年 7 月 1 日的期限延後，以建立新的「就地保留」來建立非使用中的信箱。但到今年年底或明年年初，您將無法在 Exchange Online 中建立新的「就地保留」。到時，只有「訴訟資料暫留」和 Office 365 保留原則可以用來建立非使用中的信箱。不過，仍會支援「就地保留」上現有的非使用中信箱，並且您可以繼續管理非使用信箱上的「就地保留」。這包括變更「就地保留」期間，以及透過移除「就地保留」永久刪除非使用中的信箱。 
 
  
## <a name="inactive-mailboxes-and-office-365-retention-policies"></a>非使用中信箱和 Office 365 保留原則

除了诉讼保留之外，在安全&合规中心中使用新的 Office 365 保留策略功能是使邮箱处于非活动状态的另一种方法。 To use a retention policy to make an inactive mailbox: 
  
- 必须将其配置为保留内容或保留内容，然后删除内容。 如果保留原則設定為只刪除內容時，將原則套用至信箱將不會成為刪除信箱時不在作用中。

- 它具有 （因為 Skype 相關的內容會儲存在使用者的信箱中） 可套用到 Exchange 信箱或商務用 Skype位置。 
    
- 它可以是查詢為基礎，讓它會保留在符合搜尋查詢的項目。 
    
如需設定Office 365保留原則的詳細資訊，請參閱 ＜ [Overview of Office 365 中的保留原則](retention-policies.md)。
  
如果使用保留策略创建非活动邮箱，Office 365 将继续处理非活动邮箱上的保留策略。 這表示如果保留原則設定來保持不變，然後刪除內容，將移至可復原的項目資料夾保留期間到期時, 和最後清除從非使用中的信箱項目。 如果Office 365保留原則不設定成已刪除的項目，尚未被永久刪除之使用者所 （之前進行信箱不在作用中） 的項目不會移至 [可復原的項目] 資料夾與將會保留無限期之後信箱成為非使用中。 
  
您可能會考慮建立專用於非使用中信箱Office 365保留原則。以下是執行這項工作原因及謹記下列事項。
  
- 您可以設定保留信箱內容僅只要符合先前員工貴組織的需求所需的保留原則。
    
- 这是标识非活动邮箱的好方法，因为保留策略将仅应用于非活动邮箱。
    
- 您将能够快速识别分配给组织中非活动邮箱的保留策略。 This will make it easier to change the retention (or deletion) settings if necessary. 它还会使永久删除非活动邮箱变得更加容易，因为您只需使用安全&合规性中心即可将其从策略中删除。 否则，您必须使用 Exchange Online PowerShell 从非活动邮箱中删除诉讼保留，或使用安全&合规中心 PowerShell 从组织范围的 Office 365 保留策略中排除非活动邮箱。
    
- 如果您建立專用於非使用中信箱Office 365保留原則，您可以新增最多達 1000 個信箱原則。如果您是非常大型的組織，您可能必須建立多個Office 365保留原則，以用於非使用中的信箱。

> [!CAUTION]
> 如果使用保留策略使邮箱处于非活动状态，则在删除相应的 Office 365 用户帐户之前，不要更改或删除邮箱的用户主体名称 （UPN）。 此外，在使邮箱处于非活动状态之前，不要更改主 SMTP 地址（派生自 UPN）或从与邮箱关联的辅助 SMTP 地址列表中删除此电子邮件地址。 如果您更改 UPN 或电子邮件地址（在应用保留策略时分配给邮箱），然后删除用户帐户以使邮箱处于非活动状态，则当您不再需要保留 i 时，您将无法删除非活动邮箱t. 这是因为您无法使用 UPN 或电子邮件地址（以标识非活动邮箱）从保留策略中删除非活动邮箱，该地址与最初将保留策略应用于邮箱时存在的地址不同。 有关删除非活动邮箱的详细信息，请参阅删除 Office [365 中的非活动邮箱。](delete-an-inactive-mailbox.md)
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>不在作用中信箱和 eDiscovery 案件保留

如果与安全&合规中心中的电子数据展示案例关联的保留放在邮箱上，然后删除邮箱或用户的 Office 365 帐户，则该邮箱将成为非活动邮箱。 However, we don't recommend using eDiscovery case holds to make a mailbox inactive. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed. In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and then the hold is released or the eDiscovery case is closed (or deleted), the inactive mailbox will be permanently deleted. Additionally, you can't create a time-based eDiscovery hold. That's means content in an inactive mailbox will be retained forever or until the hold is removed and the inactive mailbox is deleted. Therefore, we recommend using a Litigation Hold or an Office 365 retention policy for inactive mailboxes.
  
有关电子数据展示案例和保留的详细信息，请参阅[电子数据展示案例](ediscovery-cases.md)。
  
## <a name="inactive-mailboxes-and-office-365-labels"></a>非使用中信箱和 Office 365 標籤

Office 365標籤有助於分類管理在組織中的電子郵件資料並強制執行該分類為基礎的保留規則。 標籤可以套用至電子郵件項目由使用者手動或自動將管理員及電子郵件項目只能有單一標籤指派給它。 如果用户邮箱中的单个电子邮件项目具有分配给它的标签（并且它被配置为保留或保留然后删除该项目），并且邮箱或用户的 Office 365 帐户被删除，则邮箱将成为非活动邮箱。 類似於 eDiscovery 案件保留，我們不建議使用標籤來讓信箱成為非使用中。 但是，我們建議您是使用訴訟暫止狀態或Office 365保留原則。 請注意但如果是標籤，可能不知道標籤已套用至電子郵件項目及刪除使用者帳戶時然後不經意進行非使用中的信箱。 
  
如需標籤的詳細資訊，請參閱 ＜ [Overview of Office 365 中的標籤](labels.md)。
  
## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>非使用中信箱和 Exchange MRM 保留原則

如果 Exchange 保留策略（邮件记录管理或联机交换中的 MRM 功能）在邮箱处于非活动状态时应用于该策略，则任何删除策略（**配置为"删除**保留"操作的保留标记）都将继续在非活动邮箱上处理。 這表示與刪除原則標記的項目要移至 [可復原的項目] 資料夾保留期間到期時。 保留期間到期時將這些項目已清除從非使用中的信箱。 如果不在作用中信箱的未指定保留持續時間，則會無限期保留復原的項目] 資料夾中的項目。 
  
相反，分配给非活动邮箱的保留策略中包含的任何存档策略（即配置了使用**MoveToArchive**保留操作的保留标记）都将被忽略。 這表示在非使用中信箱與封存原則標記的項目仍然在主要信箱的保留期間到期時。 它們不被移至封存信箱或封存信箱中 [可復原的項目] 資料夾。 他們將會無限期保留。 
  
## <a name="creating-an-inactive-mailbox"></a>建立非使用中的信箱

若要停用信箱，它必須被指派Exchange Online (Plan 2) 授權使訴訟暫止狀態或Office 365保留原則可套用至信箱會在刪除之前。 删除邮箱后，与其关联的 Exchange 联机许可证将可用于分配给新用户。 不在作用中的信箱不需要持續進行的授權。
  
下表摘要說明程序，讓不同保留案例的非使用中信箱。 有关详细信息，请参阅在[Office 365 中管理非活动邮箱。](create-and-manage-inactive-mailboxes.md)
  
|**自。。。**|**做这个...**|**結果**|
|:-----|:-----|:-----|
|只有在員工離職之後無限期保留信箱內容  <br/> | 将邮箱置于诉讼保留状态，或将 Office 365 保留策略（配置为保留内容）应用于邮箱。  <br/>  不要將保留持續時間指定為訴訟暫止狀態或未設定刪除項目 ； Office 365保留原則或者您可以使用永久保留項目保留原則。  <br/>  移除使用者的Office 365帳戶。  <br/> |非活动邮箱中的所有内容（包括"可恢复项目"文件夹中的项目）将无限期保留。  <br/> |
|信箱內容保留特定的一段之後員工離職然後予以刪除  <br/> | 将 Office 365 保留策略应用于邮箱。  <br/>  配置保留策略以保留，然后在保留期到期时删除项目。  <br/>  移除使用者的Office 365帳戶。  <br/> |当邮箱项目的保留期到期时，该项目将移动到"可恢复项目"文件夹，然后在已删除的项目保留期（对于 Exchange 邮箱）过期时从非活动邮箱永久删除（清除）。 Office 365 保留策略的保留期可以基于邮箱项目接收或创建的原始日期或上次修改的时间进行配置。  <br/> |
   
**注：** 如果诉讼保留已放在邮箱上，或者 Office 365 保留策略（配置为保留或保留然后删除内容）已应用于邮箱，则所有操作就是删除相应的 Office 365 用户帐户创建非活动邮箱。 
  
## <a name="managing-inactive-mailboxes"></a>管理非使用中信箱

您讓信箱成為非使用中之後，您可以在非使用中的信箱上執行各種管理工作。
  
- **更改非活动邮箱的保留持续时间**使邮箱处于非活动状态后，您可以更改应用于非活动邮箱的诉讼保留或 Office 365 保留策略的保留持续时间。 有关分步过程，请参阅[更改 Office 365 中非活动邮箱的保留持续时间。](change-the-hold-duration-for-an-inactive-mailbox.md)

  > [!NOTE]
  > 不能将其他保留策略应用于非活动邮箱。 您只能更改应用于非活动邮箱的现有保留策略的保留期限。
    
- **恢复非活动邮箱**如果前员工（或休假的员工）返回您的组织，或者如果雇用新员工来承担前员工的工作职责，则可以恢复非活动邮箱的内容。 當您復原不在作用中的信箱時，信箱轉換成新的信箱、 保留的內容和非使用中的信箱資料夾結構，及信箱連結至新的使用者帳戶。 它會復原之後，非使用中的信箱不存在。 有关恢复非活动邮箱时发生的分步过程和信息，请参阅[在 Office 365 中恢复非活动邮箱。](recover-an-inactive-mailbox.md)
    
- **还原非活动邮箱**如果其他员工承担前员工的工作职责，或者如果其他人需要访问非活动邮箱的内容，则可以将非活动邮箱的内容还原（或合并）到现有邮箱。 當您還原非使用中信箱內容複製到另一個信箱。 非使用中的信箱，則會保留與會維持不在作用中的信箱。 非使用中信箱仍可搜尋使用 eDiscovery 工具、 其內容可以還原至另一個信箱和復原或刪除日後。 有关分步过程，请参阅[在 Office 365 中还原非活动邮箱。](restore-an-inactive-mailbox.md)
    
- **删除非活动邮箱**当您不再需要保留非活动邮箱的内容时，可以通过删除应用于非活动邮箱的所有保留或 Office 365 保留策略来永久删除它。 如果信箱進行非使用中超過 30 天之內，它會標示為永久刪除之後移除保留。 如果信箱可在過去 30 天內不在作用中，您可以使其成為使用一次之後移除保留或保留原則。 有关分步过程，请参阅[删除 Office 365 中的非活动邮箱。](delete-an-inactive-mailbox.md)