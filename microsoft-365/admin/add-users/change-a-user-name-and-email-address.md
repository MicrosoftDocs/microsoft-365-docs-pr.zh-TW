---
title: 變更使用名稱和電子郵件地址
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb5ac074-e203-4e1f-9843-b9d1a3e03297
description: '了解全域系統管理員如何變更使用者的電子郵件地址和顯示名稱。 '
ms.openlocfilehash: 0c94114a50ce369ffb809e8f41060994f635a36c
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936524"
---
# <a name="change-a-user-name-and-email-address"></a>變更使用名稱和電子郵件地址

您可能需要變更某個使用者的電子郵件地址和顯示名稱，例如當使用者結婚或使用者的姓氏變更時。

觀看有關變更使用者電子郵件地址的短片。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SJuc] 

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

## <a name="change-a-users-email-address"></a>變更使用者的電子郵件地址

您必須是[全域系統管理員](about-admin-roles.md)才能執行這些步驟。 

::: moniker range="o365-worldwide"
 
1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。
    
2. 選取使用者名稱，然後在 **[帳戶]** 索引標籤上，選取 **[管理使用者名稱]**。
    
3. 在第一個方塊中，輸入新電子郵件地址的前半部。 如果您已將自己的網域新增到 Office 365，使用下拉式清單選擇新電子郵件別名的網域。 

4. 選取 **[儲存變更]**。

   
::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。  

2. 選取使用者。 在飛出窗格的 **[使用者名稱/電子郵件]** 旁邊，選取 **[編輯]**。

3. 在第一個方塊中，輸入新電子郵件地址的前半部。 如果您已將自己的網域新增至 Office 365，您可以使用下拉式清單選擇新電子郵件別名的網域。

4. 選取 **[儲存]**。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。 

2. 選取使用者。 在飛出窗格的 **[使用者名稱/電子郵件]** 旁邊，選取 **[編輯]**。

3. 在第一個方塊中，輸入新電子郵件地址的前半部。 如果您已將自己的網域新增至 Office 365，您可以使用下拉式清單選擇新電子郵件別名的網域。

4. 選取 **[儲存]**。

::: moniker-end

**重要**：如果您收到錯誤訊息，請參閱 [解決錯誤訊息](#resolve-error-messages)。

## <a name="set-the-primary-email-address"></a>設定主要電子郵件地址

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。
    
2. 選取使用者名稱，然後在 **[帳戶]** 索引標籤上，選取 **[管理電子郵件別名]**。

3. 針對您要為該人員設為主要電子郵件地址的電子郵件地址，選取 **[設為主要]**。 
    
    **重要**：如果您是從 GoDaddy 或其他提供管理主控台的協力廠商服務購買 Office 365，就不會看到此選項。 在這種情況下，請改為登入 GoDaddy/協力廠商的管理主控台設定主要別名。 
    
    補充一點，您必須是全域系統管理員才能看到此選項。如果您沒有看到這個選項，表示您無權變更使用者的名稱和主要電子郵件地址。
  
4. 您會看到一個黃色的大型警告，指出您即將變更使用者的登入資訊。 選取 **[儲存]**，再選取 **[關閉]**。
    
5. 提供該人員下列資訊：
 
  - 這項變更可能需要一些時間。
  
  - Their new username. They'll need it to sign in to Microsoft 365.
    
  - 如果他們使用商務用 Skype Online，他們必須重新排定所有他們舉辦的商務用 Skype Online 會議，並通知外部連絡人更新他們的連絡資訊。

  - 如果他們使用的是 OneDrive，則該位置的 URL 已變更。 如果他們的 OneDrive 中有 OneNote 筆記本，他們可能需要關閉筆記本，然後在 OneNote 中重新開啟。 如果他們的 OneDrive 中含有共用檔案，檔案的連結可能無法運作，而使用者可以重新共用。    
  
  - 如果他們的密碼也變更了，系統會要求他們在行動裝置上輸入新密碼，否則將無法進行同步處理。
  
::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。  

2. 選取使用者。 在飛出窗格的 **[使用者名稱/電子郵件]** 旁邊，選取 **[編輯]**。

3. 針對您要為該人員設為主要電子郵件地址的電子郵件地址，選取 **[設為主要]**。 
    
    **重要**：如果您是從 GoDaddy 或其他提供管理主控台的協力廠商服務購買 Office 365，就不會看到此選項。 在這種情況下，請改為登入 GoDaddy/協力廠商的管理主控台設定主要別名。 
    
    補充一點，您必須是全域系統管理員才能看到此選項。如果您沒有看到這個選項，表示您無權變更使用者的名稱和主要電子郵件地址。
  
4. 您會看到一個黃色的大型警告，指出您即將變更使用者的登入資訊。 選取 **[儲存]**，再選取 **[關閉]**。
    
5. 告知該人員下列資訊：
 
  - 此變更可能需要一些時間才能生效。
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - 如果他們使用商務用 Skype Online，請告知他們需要重新排定所有他們舉辦的商務用 Skype Online 會議，而且他們需要通知其外部連絡人更新舊的連絡資訊。

  - 如果他們使用的是 OneDrive，請告知他們該位置的 URL 已變更。 如果他們的 OneDrive 中有 OneNote 筆記本，他們可能必須關閉筆記本，然後在 OneNote 中重新開啟。 如果他們的 OneDrive 中含有共用檔案，檔案的連結可能無法運作，而使用者可以重新共用。    
  
  - 如果他們的密碼也變更了，請告知他們系統會要求在其行動裝置上輸入新密碼，否則將無法進行同步處理。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。 

2. 選取使用者。 在飛出窗格的 **[使用者名稱/電子郵件]** 旁邊，選取 **[編輯]**。

3. 針對您要為該人員設為主要電子郵件地址的電子郵件地址，選取 **[設為主要]**。 
    
    **重要**：如果您是從 GoDaddy 或其他提供管理主控台的協力廠商服務購買 Office 365，就不會看到此選項。 在這種情況下，請改為登入 GoDaddy/協力廠商的管理主控台設定主要別名。 
    
    補充一點，您必須是全域系統管理員才能看到此選項。如果您沒有看到這個選項，表示您無權變更使用者的名稱和主要電子郵件地址。
  
4. 您會看到一個黃色的大型警告，指出您即將變更使用者的登入資訊。 選取 **[儲存]**，再選取 **[關閉]**。
    
5. 告知該人員下列資訊：
 
  - 此變更可能需要一些時間才能生效。
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - 如果他們使用商務用 Skype Online，請告知他們需要重新排定所有他們舉辦的商務用 Skype Online 會議，而且他們需要通知其外部連絡人更新舊的連絡資訊。

  - 如果他們使用的是 OneDrive，請告知他們該位置的 URL 已變更。 如果他們的 OneDrive 中有 OneNote 筆記本，他們可能必須關閉筆記本，然後在 OneNote 中重新開啟。 如果他們的 OneDrive 中含有共用檔案，檔案的連結可能無法運作，而使用者可以重新共用。    
  
  - 如果他們的密碼也變更了，請告知他們系統會要求在其行動裝置上輸入新密碼，否則將無法進行同步處理。

::: moniker-end
  
## <a name="change-a-users-display-name"></a>變更使用者的顯示名稱

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 選取使用者名稱，然後在 **[帳戶]** 索引標籤上，選取 **[管理連絡人資訊]**。

3. 在 **[顯示名稱]** 方塊中，輸入該人員的新名稱，然後選取 **[儲存]**。

    如果收到 **[很抱歉，無法編輯該使用者。請檢閱使用者資訊，然後再試一次]** 的錯誤訊息，請參閱[解決錯誤訊息](#resolve-error-messages)。

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username.

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。  

2. 選取使用者。 在飛出窗格中，選取 **[連絡人資訊]** 旁的 **[編輯]**。

3. 在 **[顯示名稱]** 方塊中，輸入該人員的新名稱，然後選取 **[儲存]**。

    如果收到 **[很抱歉，無法編輯該使用者。請檢閱使用者資訊，然後再試一次]** 的錯誤訊息，請參閱[解決錯誤訊息](#resolve-error-messages)。

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。 

2. 選取使用者。 在飛出窗格中，選取 **[連絡人資訊]** 旁的 **[編輯]**。

3. 在 **[顯示名稱]** 方塊中，輸入該人員的新名稱，然後選取 **[儲存]**。

    如果收到 **[很抱歉，無法編輯該使用者。請檢閱使用者資訊，然後再試一次]** 的錯誤訊息，請參閱[解決錯誤訊息](#resolve-error-messages)。

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

## <a name="resolve-error-messages"></a>解決錯誤訊息

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>[找不到符合參數名稱 'EmailAddresses' 的參數]

如果您收到 **[找不到符合參數名稱 'EmailAddresses' 的參數]** 的錯誤訊息，表示需要久一點的時間，才能完成設定您的租用戶或您的自訂網域 (如果您最近剛新增自訂網域的話)。 設定程序最多可能需要 4 個小時才能完成。 請稍候，讓設定程序完成，然後再試一次。 如果問題仍然存在，請連絡[客戶支援](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)，他們會為您執行完整的同步處理。
  
### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>[很抱歉，無法編輯該使用者。 請檢閱使用者資訊，然後再試一次]

如果收到 **[很抱歉，無法編輯該使用者。請檢閱使用者資訊，然後再試一次]** 的錯誤訊息， 表示您並非全域系統管理員，無權變更使用者的名稱。 請聯繫貴公司的全域系統管理員來進行變更。


## <a name="what-to-do-with-old-email-addresses"></a>該如何處理舊的電子郵件地址

使用者的前一個主要電子郵件地址會保留為其他電子郵件地址。 **強烈建議您不要移除舊電子郵件地址。**
  
Some people might continue to send email to the person's old email address and deleting it may result in NDR failures. Microsoft automatically routes it to the new one. Also, do not reuse old SMTP email addresses and apply them to new accounts. This can also cause NDR failures or delivery to an unintended mailbox.
   
## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>人員的離線通訊錄無法與全域通訊清單同步處理時該怎麼辦？

If they are using Exchange Online or if their account is linked with your organization's on-premises Exchange environment, you might see this error when you try to change a username and email address: "This user is synchronized with your local Active Directory. Some details can be edited only through your local Active Directory."
  
This is due to the Microsoft Online Email Routing Address (MOERA). The MOERA is constructed from the person's  _userPrincipalName_ attribute in Active Directory and is automatically assigned to the cloud account during the initial sync and once created, it cannot be modified or removed in Office 365. You can subsequently change the username in the Active Directory, but it doesn't change the MOERA and you may run into issues displaying the newly changed name in the Global Address List. 
  
若要修正此問題，請使用您的 Microsoft 365 系統管理員認證登入[適用於 PowerShell 的 Azure Active Directory 模組]( https://go.microsoft.com/fwlink/?LinkId=823193)， 然後使用下列語法： 
  
```powershell
Set-MsolUserPrincipalName -UserPrincipalName anne.wallace@contoso.onmicrosoft.com -NewUserPrincipalName anne.jones@contoso.com
```

> [!TIP]
> 這會變更人員的 **userPrincipalName** 屬性，且與他們的 Microsoft Online Email Routing Address (MOERA) 電子郵件地址無關。 不過，這是讓人員的登入 UPN 符合其主要 SMTP 地址的最佳做法。 
  
若要了解如何分別在 Active Directory、Windows Server 2003 及較舊版本中變更使用者名稱，請參閱[重新命名使用者帳戶](https://go.microsoft.com/fwlink/?LinkId=809091)。
  
## <a name="related-articles"></a>相關文章

[系統管理員：重設一或多個使用者的密碼](reset-passwords.md)
  
[為使用者新增另一個電子郵件地址](../email/add-another-email-alias-for-a-user.md)
