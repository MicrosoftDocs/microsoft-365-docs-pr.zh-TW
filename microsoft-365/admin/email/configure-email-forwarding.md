---
title: 設定電子郵件轉寄
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: 使用 Office365 設定電子郵件轉轉至一或多個電子郵件帳戶。
ms.openlocfilehash: 1168b549443de218339b1b8dcb32e57da175a2aa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926639"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>在 Microsoft 365 中設定電子郵件轉轉

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true) (英文)。

::: moniker-end

做為組織的系統管理員，您可能會有公司要求為使用者信箱設定電子郵件轉轉。 電子郵件轉寄功能可讓您將寄至使用者信箱的電子郵件訊息轉寄到組織內外的其他使用者信箱。

> [!IMPORTANT]
> 您可以使用外發垃圾郵件篩選策略來控制自動轉轉給外部收件者。 詳細資訊請參閱 Microsoft [365 中的控制自動外部電子郵件轉轉](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)。

## <a name="configure-email-forwarding"></a>設定電子郵件轉寄

設定電子郵件轉轉之前，請注意下列事項：

- 設定電子郵件轉寄功能後，系統只會轉寄從信箱 *寄* 到該郵件的新電子郵件。

- 電子郵件轉轉會要求  *從帳戶*  擁有授權。 如果您因為使用者離開您的組織而設定電子郵件轉轉，另一個選項是 [將其信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)。 如此一來，多人就可以存取。 不過，共用信箱不可超過 50 GB。

您必須是 Microsoft 365 中的 Exchange 系統管理員或全域系統管理員，才能執行這些步驟。 詳細資訊請參閱關於系統管理員 [角色的主題](../add-users/about-admin-roles.md)。

::: moniker range="o365-worldwide"

1. 在系統管理中心中，前往使用者使用 \> **[中使用者](https://go.microsoft.com/fwlink/p/?linkid=834822)** 頁面。

2. 選取您想要轉看其電子郵件的使用者名稱，以開啟屬性頁面。

3. 在郵件 **上，** 選取管理 **電子郵件轉寄**。

4. 在電子郵件轉寄頁面上，選取轉寄所有寄到此信箱的電子郵件，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的一份副本。 如果您未看到此選項，請確定已指派授權給使用者帳戶。 選取 **[儲存變更]**。

    **若要轉轉多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉往位址。 若要深入瞭解，請參閱 [使用規則自動轉轉郵件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

     或者，在系統管理中心建立[](../setup/create-distribution-lists.md)通訊群組，新增位址[](add-user-or-contact-to-distribution-list.md)至群組，然後設定轉場，使用本文中的指示指向 DL。

5. 不要刪除您轉轉電子郵件之使用者的帳戶，或移除他們的授權！  如果您這麼做，電子郵件轉轉功能將會停止。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，前往使用者使用 \> **[中使用者](https://go.microsoft.com/fwlink/p/?linkid=847686)** 頁面。

2. 選取您想要轉看其電子郵件的使用者名稱，以開啟屬性頁面。

3. 展開 **郵件設定**，然後在電子郵件轉寄 **區** 段 **，選取編輯**。

4. 在電子郵件轉轉頁面上，將開關設為開啟、輸入轉場地址，並選擇是否要保留已轉轉電子郵件的副本。 如果您未看到此選項，請確定已指派授權給使用者帳戶。 選取 [儲存]。

   **若要轉轉多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉往位址。 若要深入瞭解，請參閱 [使用規則自動轉轉郵件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

   或者，在系統管理中心建立[](../setup/create-distribution-lists.md)通訊群組，新增位址[](add-user-or-contact-to-distribution-list.md)至群組，然後設定轉場，使用本文中的指示指向 DL。

5. 不要刪除您轉轉電子郵件之使用者的帳戶，或移除他們的授權！  如果您這麼做，電子郵件轉轉功能將會停止。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，前往使用者使用 \> **[中使用者](https://go.microsoft.com/fwlink/p/?linkid=850628)** 頁面。

2. 選取您想要轉看其電子郵件的使用者名稱，以開啟屬性頁面。

3. 展開 **郵件設定**，然後在電子郵件轉寄 **區** 段 **，選取編輯**。

4. 在電子郵件轉轉頁面上，將開關設為開啟、輸入轉場地址，並選擇是否要保留已轉轉電子郵件的副本。 如果您未看到此選項，請確定已指派授權給使用者帳戶。 選取 [儲存]。

   **若要轉轉多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉往位址。 若要深入瞭解，請參閱 [使用規則自動轉轉郵件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

   或者，在系統管理中心建立[](../setup/create-distribution-lists.md)通訊群組，新增位址[](add-user-or-contact-to-distribution-list.md)至群組，然後設定轉場，使用本文中的指示指向 DL。

5. 不要刪除您轉轉電子郵件之使用者的帳戶，或移除他們的授權！  如果您這麼做，電子郵件轉轉功能將會停止。

::: moniker-end
