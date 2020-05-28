---
title: 關於共用信箱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
description: 當多人需要存取相同的信箱時，會使用共用信箱。 深入瞭解建立共用信箱之前所需注意的事項。
ms.openlocfilehash: 6d9b7f59840b8eb4ce38822945066e14d9a86a4d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400205"
---
# <a name="about-shared-mailboxes"></a>關於共用信箱

如果有多個人員需要存取相同信箱 (例如公司資訊或支援電子郵件地址、接待處或其他可能由多人共用的功能)，就會使用共用信箱。

擁有群組信箱權限的使用者可以以信箱電子郵件地址的身分傳送或代表其傳送 (如果系統管理員已授與使用者執行該動作的權限)。 這對於說明和支援信箱特別有用，因為使用者可以透過「Contoso 支援」或「大樓 A 接待處」傳送電子郵件。

[建立共用信箱](create-a-shared-mailbox.md)之前，請先瞭解下列事項：

- **授權：** 您的共用信箱可以儲存至50GB 的資料，而不需要您指派授權給它。 超過此上限後，您必須指派授權給信箱才能儲存更多資料。 如需共用信箱授權的詳細資訊，請參閱[Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)。 當共用信箱到達儲存上限時，您可以接收電子郵件一段時間，但您將無法傳送新電子郵件。 之後，信箱將停止接收電子郵件。 傳送郵件到此信箱的寄件者會收到未傳遞回條。

- **使用者權限：** 您必須授與使用者許可權（成員資格），才能使用共用信箱。 僅限貴組織內部的人員可以使用共用信箱。

- **外部使用者：** 您無法將您的公司外部人員（例如，具有 Gmail 帳戶的人員）存取權給您的共用信箱。 如果您想這麼做，請考慮改為建立 Outlook 群組。 若要深入瞭解，請參閱[Create a Microsoft 365 group in admin center](../create-groups/create-groups.md)。

-  **與 Outlook 搭配使用：** 除了透過瀏覽器使用網頁上的 Outlook 來存取共用信箱之外，您也可以使用 Outlook 來 iOS 應用程式或適用于 Android 應用程式的 Outlook。 若要深入瞭解，請參閱<a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">將共用信箱新增至 Outlook mobile</a>。 另一個選項是建立共用信箱的群組。 若要深入瞭解，請參閱[比較群組](../create-groups/compare-groups.md)。  

- **加密：** 您無法加密從共用信箱傳送的電子郵件。 這是因為共用信箱沒有自己的安全性內容（username/密碼），所以無法指派金鑰。 如果有一個以上的人員是成員，而且他們會使用自己的金鑰來傳送/接收已加密的電子郵件，則其他成員可能能夠讀取電子郵件，而其他成員可能無法讀取，視電子郵件所加密的公開金鑰而定。

- **信箱轉換：** 您可以將使用者信箱轉換成共用信箱。 請參閱[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)。

- 系統**管理員角色：** 具有全域管理員或 Exchange 系統管理員角色的使用者可以建立共用信箱。

- **訂閱需求：** 若要建立共用信箱，您必須訂閱包含電子郵件（Exchange Online 服務）的 Microsoft 365 for business 方案。 Microsoft 365 商務應用程式訂閱不包含電子郵件;Microsoft 365 商務標準版。

- 登**入：** 共用信箱不是由其相關聯的使用者帳戶用於直接登入。 您應該永遠封鎖共用信箱帳戶的登入，並將它封鎖。

- **太多使用者：** 當同時存取共用信箱的指定使用者太多時，他們可能會間歇無法連線到此信箱。 在此情況下，您可以考慮減少使用者數目或使用不同的工作負載，例如 Microsoft 365 群組或公用資料夾。

- **刪除郵件：** 不幸的是，您無法防止人員刪除共用信箱中的郵件。 這項工作的唯一方法是建立 Microsoft 365 群組，而不是共用信箱。 Outlook 中的群組就像是共用信箱。 如需兩者的比較，請參閱[比較群組](../create-groups/compare-groups.md)。 若要深入瞭解群組，請參閱[深入瞭解群組](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)。

## <a name="related-articles"></a>相關文章

[建立共用信箱](create-a-shared-mailbox.md)

[設定共用信箱](configure-a-shared-mailbox.md)

[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)

[從共用信箱中移除授權](remove-license-from-shared-mailbox.md)

[解決共用信箱的問題](resolve-issues-with-shared-mailboxes.md)
