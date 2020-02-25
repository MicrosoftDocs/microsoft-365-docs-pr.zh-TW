---
title: 為使用者新增另一個電子郵件別名
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '了解如何可以有一個以上的電子郵件地址，呼叫與 Office 365 商務版帳戶相關聯的電子郵件別名。 '
ms.openlocfilehash: 10f219f380d30a5ee8e9822e7a35ee533d165c33
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251713"
---
# <a name="add-another-email-alias-for-a-user"></a>為使用者新增另一個電子郵件別名
  
本文適用於 Office 365 系統管理員擁有商務版訂閱。 它不是隸屬使用者。
  
Office 365 的主要電子郵件地址通常是建立其帳戶時，已指派給使用者的電子郵件地址。 When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps. They can also have more than one email address associated with their Office 365 for business account. These additional addresses are called aliases. 
  
例如，假設 Jenna 具有電子郵件地址 jenna@contosoco.com，但她也想要接收電子郵件在 jen@contosoco.com，因為有些人參照她該名稱。 您可以為她建立別名，如此這兩個電子郵件地址前往 Jenna 的收件匣。
<br><br>  
  
一個使用者最多可建立 400 個別名。 不需要額外費用或授權。
  
> [!Tip]
> 如果您想多位人員管理傳送到單一電子郵件地址，例如 info@NodPublishers.com 或 sales@NodPublishers.com，建立共用的信箱。 若要深入了解，請參閱[建立共用信箱](create-a-shared-mailbox.md)。
  
## <a name="add-email-aliases-to-a-user"></a>為使用者新增電子郵件別名
<a name="AddEmailPreview"> </a>

您必須具有[系統管理員權限](../add-users/about-admin-roles.md)若要這麼做。 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心] **開關將它開啟。

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 在 [**作用中使用者**] 頁面上，選取使用者 >**管理電子郵件別名**。 如果該人員沒有指派授權，您無法看到此選項。 
    
3. 選取 [ **+ 新增別名**，並為使用者輸入新的別名。   
    
    > [!Important] 
    > 如果您收到錯誤訊息 「**參數找不到符合參數名稱 ' EmailAddresses**，「 這表示，花費的時間較長的時間完成設定您的租用戶或您的自訂網域，如果您最近新增一個。 設定程序最多可能需要 4 個小時才能完成。 請稍候，讓設定程序完成，然後再試一次。 如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。
    
  
    > [!IMPORTANT]
    > 如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。 
  
    > [!TIP]
    > 電子郵件別名必須以來自下拉式清單的網域做為結尾。 若要將另一個網域名稱新增至清單，請參閱[新增網域至 Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx)。 
  
     
5. 當您完成時，選擇 [**儲存變更**。
    
6. 請等候 24 小時，讓新別名填入整個 Office 365。
    
    使用者現在有主要地址和一個別名。 例如，所有傳送到送達 Eliza Hoffman 主要地址、 Eliza@NodPublishers.com，以及其別名，Sales@NodPublishers.com，郵件會移至送達 Eliza 的收件匣。
    
  
7. **當使用者回覆時，*從*地址將會是其主要電子郵件別名。** For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox. When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。 
    
    
2. 在 [**作用中使用者**] 頁面上，選取您想要編輯的人員名稱。

3. 接下來為**的使用者名稱 / 電子郵件別名**，選取 [**編輯**]。

    > [!Important] 
    > 如果您收到錯誤訊息 「**參數找不到符合參數名稱 ' EmailAddresses**，「 這表示，花費的時間較長的時間完成設定您的租用戶或您的自訂網域，如果您最近新增一個。 設定程序最多可能需要 4 個小時才能完成。 請稍候，讓設定程序完成，然後再試一次。 如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。

4. 在 [**別名**] 下的 [文字] 方塊中，輸入新的電子郵件別名的第一個部分。 如果您已將自己的網域新增至 Office 365，您可以使用下拉式清單選擇新電子郵件別名的網域。 然後選取 [**新增**]。

    > [!IMPORTANT]
    > 如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。 
  
    > [!TIP]
    > 電子郵件別名必須以來自下拉式清單的網域做為結尾。 若要將另一個網域名稱新增至清單，請參閱[新增網域至 Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx)。 

5. 當您完成時，選取 [**儲存**]。

6. 請等候 24 小時，讓新別名填入整個 Office 365。 
    
    使用者現在有主要地址和一個別名。 例如，所有傳送到送達 Eliza Hoffman 主要地址、 Eliza@NodPublishers.com，以及其別名，Sales@NodPublishers.com，郵件會移至送達 Eliza 的收件匣。
    
  
7. **當使用者回覆時，*從*地址將會是其主要電子郵件別名。** For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox. When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。 

    
2. 在 [**作用中使用者**] 頁面上，選取您想要編輯的人員名稱。

3. 接下來為**的使用者名稱 / 電子郵件別名**，選取 [**編輯**]。

    > [!Important] 
    > 如果您收到錯誤訊息 「**參數找不到符合參數名稱 ' EmailAddresses**，「 這表示，花費的時間較長的時間完成設定您的租用戶或您的自訂網域，如果您最近新增一個。 設定程序最多可能需要 4 個小時才能完成。 請稍候，讓設定程序完成，然後再試一次。 如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。

4. 在 [**別名**] 下的 [文字] 方塊中，輸入新的電子郵件別名的第一個部分。 如果您已將自己的網域新增至 Office 365，您可以使用下拉式清單選擇新電子郵件別名的網域。 然後選取 [**新增**]。

    > [!IMPORTANT]
    > 如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。 
  
    > [!TIP]
    > 電子郵件別名必須以來自下拉式清單的網域做為結尾。 若要將另一個網域名稱新增至清單，請參閱[新增網域至 Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx)。 

5. 當您完成時，選取 [**儲存**]。

6. 請等候 24 小時，讓新別名填入整個 Office 365。 
    
    使用者現在有主要地址和一個別名。 例如，所有傳送到送達 Eliza Hoffman 主要地址、 Eliza@NodPublishers.com，以及其別名，Sales@NodPublishers.com，郵件會移至送達 Eliza 的收件匣。
    
  
7. **當使用者回覆時，*從*地址將會是其主要電子郵件別名。** For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox. When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>您收到 「 找不到符合參數名稱 EmailAddresses 」？


如果您收到 「**找不到符合參數名稱 EmailAddresses**」 錯誤訊息表示，花費的時間較長的時間完成設定您的租用戶或您的自訂網域，如果您最近新增一個。 設定程序最多可能需要 4 個小時才能完成。 請稍候，讓設定程序完成，然後再試一次。 如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>您是從 GoDaddy 或其他協力廠商購買訂閱嗎？


如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。
  
## <a name="related-articles"></a>相關文章

[從不同的地址傳送電子郵件](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[變更使用名稱和電子郵件地址](../add-users/change-a-user-name-and-email-address.md)
  

