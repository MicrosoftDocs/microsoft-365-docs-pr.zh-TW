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
search.appverid:
- BCS160
- MET150
- MOE150
description: 當多人需要存取同一個信箱時，會使用共用信箱。 瞭解建立共用信箱之前必須知道哪些資訊。
ms.openlocfilehash: 744c4fece24cf1fa5ee7259a0d722ff123ff2664
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926507"
---
# <a name="about-shared-mailboxes"></a>關於共用信箱

如果有多個人員需要存取相同信箱 (例如公司資訊或支援電子郵件地址、接待處或其他可能由多人共用的功能)，就會使用共用信箱。

擁有群組信箱權限的使用者可以以信箱電子郵件地址的身分傳送或代表其傳送 (如果系統管理員已授與使用者執行該動作的權限)。 這對於說明和支援信箱特別有用，因為使用者可以透過「Contoso 支援」或「大樓 A 接待處」傳送電子郵件。

建立 [共用信箱之前](create-a-shared-mailbox.md)，以下是一些您應該瞭解的事：

- **授權：** 在不指派授權給共用信箱的情況下，您的共用信箱可以儲存最多 50 GB 的資料。 超過此上限後，您必須指派授權給信箱才能儲存更多資料。 如需共用信箱授權的詳細資訊，請參閱 [Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)。 當共用信箱到達儲存上限時，您可以接收電子郵件一段時間，但您將無法傳送新電子郵件。 之後，信箱將停止接收電子郵件。 傳送郵件到此信箱的寄件者會收到未傳遞回條。

- **使用者許可權：** 您需要提供使用者共用 (許可權) 共用信箱。 僅限貴組織內部的人員可以使用共用信箱。

- **外部使用者：** 您無法讓公司外部人員存取您的 (，例如擁有 Gmail 帳戶) 存取您的共用信箱。 如果您想這麼做，請考慮改為建立 Outlook 群組。 若要深入瞭解，請參閱在系統管理中心建立 [Microsoft 365 群組](../create-groups/create-groups.md)。

- **與 Outlook 一同使用：** 除了從瀏覽器使用 Outlook 網頁版存取共用信箱，您也可以使用 iOS 版 Outlook App 或 Android 版 Outlook App。 若要深入瞭解，請參閱[新增共用信箱至 Outlook Mobile。](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f) 另一個選項是建立共用信箱的群組。 若要深入瞭解，請參閱比較 [群組](../create-groups/compare-groups.md)。

- **加密：** 無法加密從共用信箱送出的電子郵件。 這是因為共用信箱沒有自己的安全性內容 (使用者名稱/密碼) 因此無法指派金鑰。 如果有不只一個人是成員，而他們傳送/接收他們以自己的金鑰加密的電子郵件，其他成員也許可以讀取電子郵件，而其他人可能無法讀取，視電子郵件加密的公用金鑰為哪一個。

- **信箱轉換：** 您可以將使用者信箱轉換為共用信箱。 請參閱[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)。

- **系統管理員角色：** 擁有全域系統管理員或 Exchange 系統管理員角色的使用者可以建立共用信箱。

- **訂閱需求：** 若要建立共用信箱，您必須訂閱商務用 Microsoft 365 方案，其中包含 Exchange Online (電子郵件) 。 商務用 Microsoft 365 應用程式訂閱不包含電子郵件。 Microsoft 365 商務標準版包含電子郵件。

- **已簽署：** 共用信箱的用意並非由其相關聯的使用者帳戶直接進行登錄。 您應該一直封鎖共用信箱帳戶的登錄，並且保持封鎖。

- **太多使用者：** 當同時存取共用信箱的指定使用者過多時，可能會間歇性地無法連接到此信箱。 在這種情況下，您可以考慮減少使用者人數，或是使用不同的工作量，例如 Microsoft 365 群組或公用資料夾。

- **刪除郵件：** 很抱歉，您無法防止人員刪除共用信箱中的郵件。 解決此問題的唯一方法，就是建立 Microsoft 365 群組，而非共用信箱。 Outlook 中的群組就像是共用信箱。 如要比較這兩個群組，請參閱 [比較群組](../create-groups/compare-groups.md)。 若要深入瞭解群組，請參閱深入瞭解 [群組](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

## <a name="related-articles"></a>相關文章

[建立共用信箱](create-a-shared-mailbox.md)

[設定共用信箱](configure-a-shared-mailbox.md)

[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)

[從共用信箱中移除授權](remove-license-from-shared-mailbox.md)

[解決共用信箱的問題](resolve-issues-with-shared-mailboxes.md)
