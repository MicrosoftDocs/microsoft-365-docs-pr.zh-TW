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
description: 電子郵件轉寄功能可讓您將傳送至 Microsoft 365 使用者信箱的電子郵件轉寄至組織內部或外部的其他信箱。
ms.openlocfilehash: 9d645c2b36bdac2ab53dcb8af4ff6ebdbd0ee601
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363788"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>設定 Microsoft 365 中的電子郵件轉寄功能

做為組織的系統管理員，您可能需要設定使用者信箱的電子郵件轉寄功能的公司需求。 電子郵件轉寄功能可讓您將傳送至使用者信箱的電子郵件轉寄至組織內部或外部的其他使用者信箱。

> [!IMPORTANT]
> 您可以使用輸出垃圾郵件篩選原則來控制自動轉寄給外部收件者。 如需詳細資訊，請參閱[在 Microsoft 365 中控制自動外部電子郵件轉接](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)。

## <a name="configure-email-forwarding"></a>設定電子郵件轉寄

在您設定電子郵件轉發之前，請注意下列事項：

- 允許自動轉寄的郵件傳送給遠端網域上的人員。 如需詳細資訊，請參閱 [管理遠端網域](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) 。

- 一旦您設定了電子郵件轉寄功能，就只會轉寄傳送給 *寄件者* 信箱的 **新** 電子郵件。

- 電子郵件轉寄要求 [  *寄件者*  ] 帳戶具有授權。 如果您正在設定電子郵件轉寄功能，因為使用者已離開您的組織，另一個選項是 [將其信箱轉換成共用信箱](convert-user-mailbox-to-shared-mailbox.md)。 這樣可以讓數個人員存取它。 不過，共用信箱不能超過50GB。

您必須是 Microsoft 365 的 Exchange 管理員或全域系統管理員，才可執行這些步驟。 如需詳細資訊，請參閱 [關於系統管理員角色](../add-users/about-admin-roles.md)的主題。

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 [ **使用者** 作用中 \> **[使用者](https://go.microsoft.com/fwlink/p/?linkid=834822)** ] 頁面。

2. 選取您要轉寄其電子郵件的使用者名稱，然後開啟 [屬性] 頁面。

3. 在 [ **郵件** ] 索引標籤上，選取 [ **管理電子郵件轉發**]。

4. 在 [電子郵件轉寄] 頁面上，選取 [ **轉寄所有傳送至此信箱的電子郵件**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。 如果您未看到此選項，請確定已將授權指派給使用者帳戶。 選取 **[儲存變更]**。

    **若要轉寄至多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。 
    
    1.  開啟 **outlook** > **Home** > **規則**> 選取 [**管理規則 & 警示**]  
    1. 選取 [ **新增規則**] > **選取 [在我收到的郵件上** 的套用規則] 清單中，然後按 **[下一步]**。
    1. 當要求此規則會套用至您收到的每封郵件時，請按一下 **[是]** 。 
    1. 在下一個清單中，選取 [動作重新 **導向至人員或公用群組** ]， **停止處理其他規則**
    1. 在視窗的下方，按一下帶底線片語的 [ **人員] 或 [公用群組** ]。
    1. 在 [至] 欄位中，輸入要轉寄郵件的 **電子郵件地址** ，然後按一下 **[確定]**。
    1. 選取 **完成**
    

     或者，在系統管理中心 [建立通訊群組](../setup/create-distribution-lists.md)， [新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。

5. 請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！  否則，電子郵件轉寄功能會停止。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 [ **使用者** 作用中 \> **[使用者](https://go.microsoft.com/fwlink/p/?linkid=847686)** ] 頁面。

2. 選取您要轉寄其電子郵件的使用者名稱，以開啟 [屬性] 頁面。

3. 展開 [ **郵件設定**]，然後在 [ **電子郵件轉發** ] 區段中，選取 [ **編輯**]。

4. 在 [電子郵件轉寄] 頁面上，將 [切換至] 設定為 [ **開啟**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。 如果您未看到此選項，請確定已將授權指派給使用者帳戶。 選取 **[儲存]**。

   **若要轉寄至多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。 若要深入瞭解，請參閱 [使用規則來自動轉寄郵件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

   或者，在系統管理中心 [建立通訊群組](../setup/create-distribution-lists.md)， [新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。

5. 請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！  否則，電子郵件轉寄功能會停止。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 [ **使用者** 作用中 \> **[使用者](https://go.microsoft.com/fwlink/p/?linkid=850628)** ] 頁面。

2. 選取您要轉寄其電子郵件的使用者名稱，以開啟 [屬性] 頁面。

3. 展開 [ **郵件設定**]，然後在 [ **電子郵件轉發** ] 區段中，選取 [ **編輯**]。

4. 在 [電子郵件轉寄] 頁面上，將 [切換至] 設定為 [ **開啟**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。 如果您未看到此選項，請確定已將授權指派給使用者帳戶。 選取 **[儲存]**。

   **若要轉寄至多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。 若要深入瞭解，請參閱 [使用規則來自動轉寄郵件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。

   或者，在系統管理中心 [建立通訊群組](../setup/create-distribution-lists.md)， [新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。

5. 請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！ 否則，電子郵件轉寄功能會停止。

::: moniker-end

## <a name="related-content"></a>相關內容 

[建立共用信箱](../email/create-a-shared-mailbox.md) (文章) \
[從不同的位址傳送電子郵件](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (文章) \
[變更使用者名稱和電子郵件地址](../add-users/change-a-user-name-and-email-address.md) (文章) 
