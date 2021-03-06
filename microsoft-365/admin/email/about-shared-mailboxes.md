---
title: 關於共用信箱
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: 當多人需要存取相同的信箱時，會使用共用信箱。 深入瞭解建立共用信箱之前所需注意的事項。
ms.openlocfilehash: a251967670e19d8f387e3fc4f724a06ef674a2b4
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394036"
---
# <a name="about-shared-mailboxes"></a>關於共用信箱

如果有多個人員需要存取相同信箱 (例如公司資訊或支援電子郵件地址、接待處或其他可能由多人共用的功能)，就會使用共用信箱。

擁有群組信箱權限的使用者可以以信箱電子郵件地址的身分傳送或代表其傳送 (如果系統管理員已授與使用者執行該動作的權限)。 這對於說明和支援信箱特別有用，因為使用者可以透過「Contoso 支援」或「大樓 A 接待處」傳送電子郵件。

## <a name="before-you-begin"></a>在您開始之前

[建立共用信箱](create-a-shared-mailbox.md)之前，請先瞭解下列事項：

- **授權：** 您的共用信箱可以儲存至50GB 的資料，而不需要您指派授權給它。 超過此上限後，您必須指派授權給信箱才能儲存更多資料。 如需共用信箱授權的詳細資訊，請參閱[Exchange Online 限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#StorageLimits)。 當共用信箱到達儲存上限時，您可以接收電子郵件一段時間，但您將無法傳送新電子郵件。 之後，信箱將停止接收電子郵件。 傳送郵件到此信箱的寄件者會收到未傳遞回條。

- **使用者權限：** 您必須授與使用者 (成員資格) 使用共用信箱的許可權。 僅限貴組織內部的人員可以使用共用信箱。

- **外部使用者：** 您無法將公司外的人員 (例如 Gmail 帳戶) 存取您的共用信箱。 如果您想這麼做，請考慮改為建立 Outlook 群組。 若要深入瞭解，請參閱[Create a Microsoft 365 group in admin center](../create-groups/create-groups.md)。

- **與 Outlook 搭配使用：** 除了使用瀏覽器中的 Outlook 網頁版存取共用信箱之外，您也可以使用 iOS 應用程式或適用于 Android 應用程式 Outlook 的 Outlook。 若要深入瞭解，請參閱[Add a shared 信箱 to Outlook mobile](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f)。 另一個選項是建立共用信箱的群組。 若要深入瞭解，請參閱 [比較群組](../create-groups/compare-groups.md)。

- **加密：** 您無法加密從共用信箱傳送的電子郵件。 這是因為共用信箱沒有自己的安全性內容 (的使用者名稱/密碼) 因此無法指派金鑰。 如果有一個以上的人員是成員，而且他們會使用自己的金鑰來傳送/接收已加密的電子郵件，則其他成員可能能夠讀取電子郵件，而其他成員可能無法讀取，視電子郵件所加密的公開金鑰而定。

- **信箱轉換：** 您可以將使用者信箱轉換成共用信箱。 請參閱[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)。

- 系統 **管理員角色：** 具有全域管理員或 Exchange 系統管理員角色的使用者可以建立共用信箱。

- **訂閱需求：** 若要建立共用信箱，您必須訂閱 (Exchange Online 服務) 中包含電子郵件的 Microsoft 365 商務方案。 Microsoft 365 Apps 商務版訂閱不包含電子郵件。 Microsoft 365 商務標準版包括電子郵件。

- 登 **入：** 共用信箱不是由其相關聯的使用者帳戶用於直接登入。 您應該永遠封鎖共用信箱帳戶的登入，並將它封鎖。

- **太多使用者：** 當同時存取共用信箱的指定使用者太多時，他們可能會間歇無法連線到此信箱。 在此情況下，您可以考慮減少使用者數目或使用不同的工作負載，例如 Microsoft 365 群組或公用資料夾。

- **刪除郵件：** 不幸的是，您無法防止人員刪除共用信箱中的郵件。 其唯一的方法是建立 Microsoft 365 群組，而不是共用信箱。 Outlook 中的群組類似于共用信箱。 如需兩者的比較，請參閱 [比較群組](../create-groups/compare-groups.md)。 若要深入瞭解群組，請參閱 [深入瞭解群組](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。


> [!NOTE]
> 若要存取共用信箱，使用者必須具備 Exchange Online 授權，但共用信箱不需要個別的授權。 每個共用信箱都有對應的使用者帳戶。 注意到當您建立共用信箱時，系統如何要求您提供密碼嗎？ 帳戶有密碼，但它是系統產生的密碼 (未知)。 您不應該使用此帳戶登入共用信箱。 若沒有授權，共用信箱的限制為 50 GB。 若要將大小限制增加到 100 GB，則共用信箱必須獲指派 Exchange Online 方案 2 授權或具有 Exchange Online 封存附加元件授權的 Exchange Online 方案 1 授權。 這也可讓您啟用自動展開封存功能，以使用無限制的封存儲存容量。 同樣地，如果您想要讓共用信箱處於訴訟資料暫留狀態，則共用信箱必須有 Exchange Online 方案 2 授權或具有 Exchange Online 封存附加元件授權的 Exchange Online 方案 1 授權。 若要將高級功能（例如 Microsoft Defender）套用至 Office 365、Advanced eDiscovery 或自動保留原則，則必須為這些功能授權共用信箱。

## <a name="related-content"></a>相關內容

[建立共用信箱](create-a-shared-mailbox.md) (文章) \
[設定共用信箱](configure-a-shared-mailbox.md) (文章)
[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md) (文章)
[從共用信箱移除授權](remove-license-from-shared-mailbox.md) (文章)
[解決共用信箱的問題](resolve-issues-with-shared-mailboxes.md) (文章)