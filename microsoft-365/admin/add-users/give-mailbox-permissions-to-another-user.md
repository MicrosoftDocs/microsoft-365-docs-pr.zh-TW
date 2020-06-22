---
title: 將信箱權限授予另一位其他使用者 - 系統管理員說明
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: '瞭解如何授予使用者存取另一個使用者信箱的權限。 這可讓使用者從其他使用者的信箱讀取郵件及傳送郵件。 '
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780598"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a>將信箱權限授予另一位其他使用者 - 系統管理員說明

身為系統管理員，公司可能會要求您授權部分使用者存取另一個使用者的信箱。 例如，您可能會想要授權助理來傳送或讀取直屬主管信箱的電子郵件，或是授權其中一個使用者代理另一個使用者傳送電子郵件。 本主題將向您說明如何完成這項作業。
  
如需有關建立及管理共用信箱的資訊，請參閱[建立共用信箱](../email/create-a-shared-mailbox.md)。
    
## <a name="looking-to-set-up-mailbox-permissions"></a>想知道如何設定信箱權限嗎？

Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:
  
 **設定權限：**
  
The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:
  
- [讀取另一個使用者信箱中的電子郵件](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [從另一個使用者的信箱傳送電子郵件](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [代理另一位使用者傳送電子郵件](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 **變更傳播：**
  
在您設定好權限後，系統需要 60 分鐘的時間，才能在整個系統中傳播並生效變更。
  
 **如何運用設定完成的權限：**
  
There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)
  
## <a name="send-email-from-another-users-mailbox"></a>從另一個使用者的信箱傳送電子郵件

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>頁面。  
    
2. 選取使用者名稱 (您計畫要賦予傳送權限的使用者)，以開啟其 [屬性] 窗格。
    
3. 在 **[郵件]** 索引標籤上，選取 **[管理信箱權限]**。

4. 選取 **[傳送為]** 旁邊的 **[編輯]**。 

5. 選取 **[新增權限]**，然後選擇您希望這位使用者能夠以其身分傳送的人員名稱。 
    
6. 選取 **[儲存]**。
 
::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。  

2. 選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。

3. 選取 **[傳送為]** 旁邊的 **[編輯]**。 

4. 選取 **[新增權限]**，然後選擇您希望這位使用者能夠以其身分傳送的人員名稱。 
    
5. 選取 **[儲存]**。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。 

2. 選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。

3. 選取 **[傳送為]** 旁邊的 **[編輯]**。 

4. 選取 **[新增權限]**，然後選擇您希望這位使用者能夠以其身分傳送的人員名稱。 
    
5. 選取 **[儲存]**。

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a>讀取另一個使用者信箱中的電子郵件

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>頁面。  
    
2. 選取使用者名稱 (要允許讀取的信箱)，以開啟其 [屬性] 窗格。
    
3. 在 **[郵件]** 索引標籤上，選取 **[管理信箱權限]**。
    
4. 選取 **[讀取和管理]** 旁邊的 **[編輯]**。 
    
5. 選取 **[新增權限]**，然後選擇您想要允許讀取此信箱之電子郵件的使用者名稱。

6. 選取 **[儲存]**。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。  
  
2. 選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。
    
3. 選取 **[讀取和管理]** 旁邊的 **[編輯]**。 
    
4. 選取 **[新增權限]**，然後選擇您想要允許讀取此信箱之電子郵件的使用者名稱。

5. 選取 **[儲存]**。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。 
  
2. 選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。
    
3. 選取 **[讀取和管理]** 旁邊的 **[編輯]**。 
    
4. 選取 **[新增權限]**，然後選擇您想要允許讀取此信箱之電子郵件的使用者名稱。

5. 選取 **[儲存]**。

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a>代理另一個使用者傳送電子郵件

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>頁面。  

2. 選取使用者名稱 (您計畫要賦予**代理傳送**權限的使用者)，以開啟其 [屬性] 窗格。
    
3. 在 **[郵件]** 索引標籤上，選取 **[管理信箱權限]**。
    
4. 選取 **[代理傳送者]** 旁邊的 **[編輯]**。

5. 選取 **[新增權限]**，然後選擇您想要允許代理此信箱傳送電子郵件的使用者名稱。

6. 選取 **[儲存]**。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。  

2. 選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。

3. 選取 **[代理傳送者]** 旁邊的 **[編輯]**。
    
4. 選取 **[新增權限]**，然後選擇您想要允許代理此信箱傳送電子郵件的使用者名稱。

5. 選取 **[儲存]**。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。 

2. 選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。

3. 選取 **[代理傳送者]** 旁邊的 **[編輯]**。
    
4. 選取 **[新增權限]**，然後選擇您想要允許代理此信箱傳送電子郵件的使用者名稱。

5. 選取 **[儲存]**。

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a>從 Outlook 和商務用 Outlook 網頁版傳送及讀取郵件


Want to know how to send email from another user's mailbox? Check out the following topics:
  
- [管理其他人的郵件和行事曆項目](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [從另一個使用者或群組傳送電子郵件](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
