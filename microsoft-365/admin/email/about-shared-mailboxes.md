---
title: 關於共用信箱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: 有多人需要存取同一個信箱時，會使用共用的信箱。 了解您需要知道之前建立共用的信箱。
ms.openlocfilehash: a5565f7299a8565b9f70745efebea3444296f353
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251717"
---
# <a name="about-shared-mailboxes"></a>關於共用信箱

如果有多個人員需要存取相同信箱 (例如公司資訊或支援電子郵件地址、接待處或其他可能由多人共用的功能)，就會使用共用信箱。

擁有群組信箱權限的使用者可以以信箱電子郵件地址的身分傳送或代表其傳送 (如果系統管理員已授與使用者執行該動作的權限)。 這會特別有用的說明和支援的信箱，因為使用者可以傳送電子郵件從 「 Contoso 支援 」 或 「 建置接收 Desk。

之前[建立共用的信箱](create-a-shared-mailbox.md)時，以下是您應該要知道的事項。

- **授權：** 您的共用的信箱可以儲存最多 50GB 的資料，而不會您指派授權給它。 超過此上限後，您必須指派授權給信箱才能儲存更多資料。 如需共用的信箱授權的詳細資訊，請參閱[Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)。 當共用信箱到達儲存上限時，您可以接收電子郵件一段時間，但您將無法傳送新電子郵件。 之後，信箱將停止接收電子郵件。 傳送郵件到此信箱的寄件者會收到未傳遞回條。

- **使用者權限：** 您要授與使用共用的信箱的使用者權限 （成員資格）。 僅限貴組織內部的人員可以使用共用信箱。

- **外部使用者：** 您不能授與人員外部商務 （例如使用 Gmail 帳戶的人） 存取您的共用信箱。 如果您想這麼做，請考慮改為建立 Outlook 群組。 若要深入了解，請參閱[在系統管理中心建立 Office 365 群組](../create-groups/create-groups.md)。

-  **與 Outlook 搭配使用：** 除了使用從您的瀏覽器網頁型 Outlook 來存取共用的信箱，您也可以使用 Outlook for iOS app 或 Outlook for Android 應用程式。 若要了解更多，請參閱<a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">新增至 Outlook 行動裝置共用信箱</a>。 另一個選項是建立您的共用信箱的群組。 若要深入了解，請參閱[比較群組](../create-groups/compare-groups.md)。  

- **加密：** 從共用信箱傳送的電子郵件無法加密。 這是因為共用的信箱不具有自己的安全性內容 （使用者名稱與密碼），讓它不能指定索引鍵。 如果一個以上的人員為成員，以及他們傳送/接收電子郵件他們自己的機碼會使用加密、 其他成員可能無法讀取電子郵件和其他人可能不、 哪一個公開金鑰，這取決於電子郵件加密所使用。

- **信箱轉換：** 您可以將使用者信箱轉換成共用信箱。 請參閱[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)。

- **系統管理員角色：** 使用全域系統管理員或 Exchange 系統管理員角色可以建立的使用者共用信箱。

- **訂閱需求：** 若要建立共用的信箱，您需要 Office 365 訂閱包含電子郵件 （Exchange Online 服務） 的商務方案。 Office 365 商務版訂閱不包含電子郵件;Office 365 商務進階版會執行。

- **登入：** 共用的信箱不適合直接登入其相關聯的使用者帳戶。 您應該一律封鎖登入共用的信箱帳戶，並保持封鎖。

- **太多的使用者：** 太多指定的使用者，同時存取共用的信箱時，他們可能會間歇性地無法連線到此信箱。 在此情況下，您可以考慮降低的使用者數目，或使用不同的工作負載，例如 Office 365 群組或公用資料夾。

- **刪除的郵件：** 不幸的是，您無法防止人員刪除共用信箱中的郵件。 此問題的唯一因應措施，便是建立 Office 365 群組來取代共用信箱。 Outlook 中的群組就像是共用信箱。 如需兩者的比較，請參閱[比較群組](../create-groups/compare-groups.md)。 若要深入了解群組，請參閱[了解更多關於群組](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)

## <a name="related-articles"></a>相關文章

[建立共用信箱](create-a-shared-mailbox.md)

[設定共用信箱](configure-a-shared-mailbox.md)

[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)

[從共用信箱中移除授權](remove-license-from-shared-mailbox.md)

[解決共用信箱的問題](resolve-issues-with-shared-mailboxes.md)