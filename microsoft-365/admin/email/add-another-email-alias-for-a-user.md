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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '瞭解您可以如何具有一個以上的電子郵件地址，稱為「電子郵件別名」，與您的商務用 Microsoft 365 相關聯。 '
ms.openlocfilehash: fd5fe2906335c8c2d1f41ac7643b7312138e15f5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241685"
---
# <a name="add-another-email-alias-for-a-user"></a>為使用者新增其他電子郵件別名
  
本文適用于具有商務訂閱的 Microsoft 365 管理員。 這不適用於家庭使用者。
  
在 Microsoft 365 中，主要的電子郵件地址通常是使用者在建立帳戶時所指派的電子郵件地址。 When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps. 他們也可以有一個以上的電子郵件地址與其 Microsoft 365 的商務帳戶相關聯。 These additional addresses are called aliases. 
  
例如，假設 Jenna 具有電子郵件地址 jenna@contosoco.com，但她也想要在 jen@contosoco.com 接收電子郵件，因為有些人會以該名稱來參照她。 您可以為她建立別名，這樣兩個電子郵件地址就會移至 Jenna 的 [收件匣]。
<br><br>  
  
一個使用者最多可建立 400 個別名。不需要額外費用或授權。
  
> [!Tip]
> 若要讓多位人員管理傳送到單一電子郵件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的電子郵件，請建立共用信箱。 若要深入瞭解，請參閱 [建立共用信箱](create-a-shared-mailbox.md)。
  
## <a name="add-email-aliases-to-a-user"></a>為使用者新增電子郵件別名

您必須具有系統 [管理員許可權](../add-users/about-admin-roles.md) ，才可執行此動作。 

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 在 [作用中 **使用者** ] 頁面上，選取 [使用者 > **管理使用者名稱和電子郵件**。 如果使用者未獲指派授權，您就不會看到此選項。 
    
3. 選取 [ **+ 新增別名** ]，然後輸入使用者的新別名。   
    
    > [!Important] 
    > 如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。 設定程序最多可能需要 4 個小時才能完成。 請稍候，讓設定程序完成，然後再試一次。 如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。
    
  
    > [!IMPORTANT]
    > 如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。 
  
    > [!TIP]
    > 電子郵件別名必須以來自下拉式清單的網域做為結尾。 若要將另一個功能變數名稱新增至清單，請參閱[add a domain to Microsoft 365](../setup/add-domain.md)。 
  
     
5. 完成後，請選擇 [ **儲存變更**]。
    
6. 請等候24小時，讓新的別名填滿整個 Microsoft 365。
    
    使用者現在會有主要位址和別名。 例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。
    
  
7. **當使用者回復時，[*發件* 人] 位址將取決於她的 Outlook 用戶端。網頁上的 Outlook 會使用接收電子郵件的別名 (我們會將其稱為「乒乓球) 」。Outlook 桌面會使用她的主要電子郵件別名。** For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox. 當送達 eliza 使用 Outlook 桌面回復郵件時，她的主要電子郵件地址會顯示為 Eliza@NodPublishers.com，而非 Sales@NodPublishers.com。
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>您取得的是「找不到符合參數名稱 EmailAddresses 的參數嗎」？

如果您收到錯誤訊息「**找不到符合參數名稱的參數 EmailAddresses**' 這表示要花很長的時間來完成設定您的租使用者，或自訂網域（如果您最近新增的話）。 設定程序最多可能需要 4 個小時才能完成。 請稍候，讓設定程序完成，然後再試一次。 如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>您是從 GoDaddy 或其他協力廠商購買訂閱嗎？


如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。

## <a name="sending-email-from-the-proxy-address-easily"></a>輕鬆從 proxy 位址傳送電子郵件

新功能在2021年4月推出，可讓使用者在網頁上使用 Outlook 時，輕鬆地從別名傳送。 當該功能推出租使用者系統管理員使用 Cmdlet 的租用時 `Set-OrganizationConfig -SendFromAliasEnabled $true` ，租用中的使用者就可以存取核取方塊清單，其中每個專案都會對應至其 Outlook 設定中的別名。 選取別名會將其顯示在撰寫表單的 [寄件者] 下拉式清單中。
  
## <a name="related-articles"></a>相關文章

[從不同的地址傳送電子郵件](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[變更使用名稱和電子郵件地址](../add-users/change-a-user-name-and-email-address.md)
