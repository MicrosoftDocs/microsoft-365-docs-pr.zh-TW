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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '瞭解您可以如何有一個以上的電子郵件地址，稱為「電子郵件別名」，與您的 Microsoft 365 for business 帳戶相關聯。 '
ms.openlocfilehash: 778d927d9ab830aea674b9bff72df250e6e430b1
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400181"
---
# <a name="add-another-email-alias-for-a-user"></a>為使用者新增其他電子郵件別名

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end
  
本文適用于具有商務用訂閱的 Microsoft 365 系統管理員。 這不適用於家庭使用者。
  
Microsoft 365 中的主要電子郵件地址通常是使用者在建立帳戶時所指派的電子郵件地址。 When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps. 他們也可以有一個以上的電子郵件地址與其 Microsoft 365 for business 帳戶相關聯。 These additional addresses are called aliases. 
  
例如，假設 Jenna 具有電子郵件地址 jenna@contosoco.com，但她也想要在 jen@contosoco.com 接收電子郵件，因為有些人會以該名稱來參照她。 您可以為她建立別名，這樣兩個電子郵件地址就會移至 Jenna 的 [收件匣]。
<br><br>  
  
一個使用者最多可建立 400 個別名。 不需要額外費用或授權。
  
> [!Tip]
> 若要讓多位人員管理傳送到單一電子郵件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的電子郵件，請建立共用信箱。 若要深入瞭解，請參閱[建立共用信箱](create-a-shared-mailbox.md)。
  
## <a name="add-email-aliases-to-a-user"></a>為使用者新增電子郵件別名
<a name="AddEmailPreview"> </a>

您必須具有系統[管理員許可權](../add-users/about-admin-roles.md)，才可執行此動作。 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心] **開關將它開啟。

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 在 [作用中**使用者**] 頁面上，選取 [使用者 >**管理電子郵件別名**。 如果使用者未獲指派授權，您就不會看到此選項。 
    
3. 選取 [ **+ 新增別名**]，然後輸入使用者的新別名。   
    
    > [!Important] 
    > 如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。 設定程序最多可能需要 4 個小時才能完成。 請稍候，讓設定程序完成，然後再試一次。 如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。
    
  
    > [!IMPORTANT]
    > 如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。 
  
    > [!TIP]
    > 電子郵件別名必須以來自下拉式清單的網域做為結尾。 若要將另一個功能變數名稱新增至清單，請參閱[add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。 
  
     
5. 完成後，請選擇 [**儲存變更**]。
    
6. 請等候 24 小時，讓新別名填入整個 Office 365。
    
    使用者現在會有主要位址和別名。 例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。
    
  
7. **當使用者回復時，[*發件*人] 位址會是她的主要電子郵件別名。** For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox. When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。 
    
    
2. 在 [作用中**使用者**] 頁面上，選取您要編輯之人員的名稱。

3. 在 [使用者**名稱/電子郵件別名**] 旁，選取 [**編輯**]。

    > [!Important] 
    > 如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。 設定程序最多可能需要 4 個小時才能完成。 請稍候，讓設定程序完成，然後再試一次。 如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。

4. 在 [**別名**] 底下的文字方塊中，輸入新電子郵件別名的第一個部分。 如果您已將自己的網域新增至 Office 365，您可以使用下拉式清單選擇新電子郵件別名的網域。 然後選取 **[新增]**。

    > [!IMPORTANT]
    > 如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。 
  
    > [!TIP]
    > 電子郵件別名必須以來自下拉式清單的網域做為結尾。 若要將另一個功能變數名稱新增至清單，請參閱[add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。 

5. 當您完成時，請選取 [**儲存**]。

6. 請等候 24 小時，讓新別名填入整個 Office 365。 
    
    使用者現在會有主要位址和別名。 例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。
    
  
7. **當使用者回復時，[*發件*人] 位址會是她的主要電子郵件別名。** For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox. When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。 

    
2. 在 [作用中**使用者**] 頁面上，選取您要編輯之人員的名稱。

3. 在 [使用者**名稱/電子郵件別名**] 旁，選取 [**編輯**]。

    > [!Important] 
    > 如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。 設定程序最多可能需要 4 個小時才能完成。 請稍候，讓設定程序完成，然後再試一次。 如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。

4. 在 [**別名**] 底下的文字方塊中，輸入新電子郵件別名的第一個部分。 如果您已將自己的網域新增至 Office 365，您可以使用下拉式清單選擇新電子郵件別名的網域。 然後選取 **[新增]**。

    > [!IMPORTANT]
    > 如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。 
  
    > [!TIP]
    > 電子郵件別名必須以來自下拉式清單的網域做為結尾。 若要將另一個功能變數名稱新增至清單，請參閱[add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。 

5. 當您完成時，請選取 [**儲存**]。

6. 請等候 24 小時，讓新別名填入整個 Office 365。 
    
    使用者現在會有主要位址和別名。 例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。
    
  
7. **當使用者回復時，[*發件*人] 位址會是她的主要電子郵件別名。** For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox. When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>您取得的是「找不到符合參數名稱 EmailAddresses 的參數嗎」？


如果您收到錯誤訊息「**找不到符合參數名稱的參數 EmailAddresses**' 這表示要花很長的時間來完成設定您的租使用者，或自訂網域（如果您最近新增的話）。 設定程序最多可能需要 4 個小時才能完成。 請稍候，讓設定程序完成，然後再試一次。 如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>您是從 GoDaddy 或其他協力廠商購買訂閱嗎？


如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。
  
## <a name="related-articles"></a>相關文章

[從不同的地址傳送電子郵件](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[變更使用名稱和電子郵件地址](../add-users/change-a-user-name-and-email-address.md)
  

