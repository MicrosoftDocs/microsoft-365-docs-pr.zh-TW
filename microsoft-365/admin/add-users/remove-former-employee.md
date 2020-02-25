---
title: 從 Office 365 中移除前任員工
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: '請遵循此檢查清單來移除 Office 365 及保護資料的員工。 '
ms.openlocfilehash: a59ad66f6c188695e6794bd259668b97669f2217
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239359"
---
# <a name="remove-a-former-employee-from-office-365"></a>從 Office 365 中移除前任員工
  
## <a name="sign-out-now"></a>立即登出！

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心] **開關將它開啟。

觀看有關移除員工。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

若要移除員工：

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 選取 [使用者名稱旁的方塊，然後選取 [**重設密碼**。

3. 輸入新密碼，然後再選取 [**重設**。 （不傳送給他們。）
    
4. 選取要移至其內容] 窗格中，然後在 [ **OneDrive** ] 索引標籤上，選取 [**啟動登出**使用者的名稱。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

2. 選取使用者，然後再選取 [**重設密碼**。

3. 輸入新密碼，然後再選取 [**重設**。 （不傳送給他們。）

4. 再次選取的使用者，展開 [ **OneDrive 設定**]，然後選取下一步] 為 [**起始****登出**。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

2. 選取使用者，然後再選取 [**重設密碼**。

3. 輸入新密碼，然後再選取 [**重設**。 （不傳送給他們。）

4. 再次選取的使用者，展開 [ **OneDrive 設定**]，然後選取下一步] 為 [**起始****登出**。

::: moniker-end

    
1 小時-或之後留下目前 Office 365] 頁面上進行的使用者會被提示要再次登入。 （存取權杖很適合一小時，讓時間表取決於該權杖上剩餘多少時間和超出其目前的網頁是否瀏覽。）
  
 **警告**： 如果使用者在網頁型 Outlook 中，只要在其信箱中，按一下 [周圍他們可能不會開始立即。 只要它們選取 OneDrive 等其他磚或重新整理其瀏覽器時，會初始化登出。 
  
若要使用 PowerShell 立即將使用者登出，請參閱 [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345) Cmdlet。 
  
如需花費多久時間以將某人退出電子郵件的詳細資訊，請參閱[終止員工的電子郵件工作階段所需注意的事項](#what-you-need-to-know-about-terminating-an-employees-email-session)。
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>移除員工及保護資料的所有步驟的概觀
<a name="bkmk_now"> </a>

我們經常遇到一個問題：「在員工離職時，我該如何保護資料？」。本文解說如何封鎖 Office 365 存取權，以及要保護資料所該執行的步驟。
  
> [!NOTE]
> 如果您是您可以刪除該員工的全域系統管理員，其電子郵件轉寄，選擇如何使用新的引導式的體驗其 OneDrive 內容處理的項目。 如需詳細資訊，請參閱[全域系統管理員： 刪除使用者](remove-former-employee.md)。 不過，建議您完成所有的其他步驟以確保員工都不會有您的公司資料的存取權此處列出。 
  
以下是快速概觀。 本文會詳細說明每個步驟。
  
|||
|:-----|:-----|
|**步驟** <br/> |**這樣做的原因** <br/> |
|1. [儲存離職員工信箱的內容](#save-the-contents-of-a-former-employees-mailbox) <br/> |對於即將接掌員工工作或萬一發生訴訟這些情況來說，這樣做非常有效。  <br/> |
|2.[將離職員工的電子郵件轉寄給另一個員工，或轉換為共用信箱](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |這讓離職員工的電子郵件地址也能繼續保持有效。如果客戶或合作夥伴仍將電子郵件傳送到離職員工的地址，這樣做可讓他們與接掌工作的人員取得聯繫。  <br/> |
|3. [抹除及封鎖離職員工的行動裝置](#wipe-and-block-a-former-employees-mobile-device) <br/> |從手機或平板電腦中移除您的業務資料。  <br/> |
|4. [封鎖離職員工的 Office 365 資料存取權](#block-a-former-employees-access-to-office-365-data)<br/> |可防止人員存取舊的 Office 365 信箱和資料。  <br/><br/> **提示**： 當您封鎖使用者存取時，您仍付費他們的授權。 您必須從您的訂閱中刪除該授權才能停止付費 (步驟 5)。           |
|5.[移動員工的 OneDrive 內容](get-access-to-and-back-up-a-former-user-s-data.md) (機器翻譯) <br/> |如果您只移除使用者的授權，但不刪除帳戶，則使用者 OneDrive 中的內容將會保留，即使超過 30 天後仍可存取。  <br/><br/> 在您刪除帳戶之前，您應該將其 OneDrive 內容移動至另一個可讓您輕鬆存取的位置。 刪除某個員工的帳戶之後，其 OneDrive 中的內容會保留**30**天。 不過，在這 30 天內，您可以還原使用者的帳戶，並取得其 OneDrive 內容的存取權。 如果您還原該使用者的帳戶，其 OneDrive 內容將會保留，即使超過 30 天後仍可存取。  <br/> |
|5a. 如果該人員使用個人電腦存取 OneDrive 和 SharePoint，會怎麼樣？  <br/> |如果他們使用個人電腦 (而不是公司核發的電腦) 從 OneDrive 和 SharePoint 下載檔案，您就無法抹除他們儲存的檔案。  <br/><br/> 他們將可繼續存取已同步處理到電腦的任何檔案。  <br/> |
|6. [移除並刪除離職員工的 Office 365 授權 ](#remove-and-delete-the-office-365-license-from-a-former-employee)<br/> |當您移除授權時，您可將授權指派給其他人員。或者，您也可以刪除授權，這樣就不必在雇用另一位人員之前繼續付費。<br/><br/> 當您移除或刪除授權時，使用者的舊電子郵件、 連絡人及行事曆會保留**30 天**，然後才永久刪除。 如果您移除或刪除使用者的授權，但不刪除帳戶，則使用者 OneDrive 中的將會保留，即使超過 30 天後仍可存取。  <br/> |
|7. [刪除離職員工的使用者帳戶](#delete-a-former-employees-user-account)<br/> |這會從您的系統管理中心移除帳戶。 保持有條不紊。  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>儲存離職員工信箱的內容
<a name="bkmk_preserve"> </a>

有兩種方法可儲存離職員工信箱的內容：
  
1. 將離職員工的電子郵件地址新增到您的 Outlook 2013 或 2016 版本，然後將資料匯出到 .pst 檔案。您可以視需要將資料匯入到其他電子郵件帳戶。若要了解做法，請參閱[存取及備份離職使用者的資料](get-access-to-and-back-up-a-former-user-s-data.md)。
    
    或
    
2. 在刪除使用者帳戶之前，將其信箱設為訴訟資料暫留或就地保留。雖然這個方法比第一個選項複雜，但如果發生下列情況，就適合採用這個方法︰您的企業方案包含封存和法務保存措施、企業可能要進行訴訟，以及企業擁有技術強大的 IT 部門。
    
    一旦您將信箱轉換成「非作用中的信箱」，系統管理員、法務人員或記錄管理員就能使用 Exchange Online 中的就地電子文件探索工具存取及搜尋當中的內容。
    
    非作用中的信箱無法接收電子郵件，也不會顯示於貴組織的共用通訊錄或其他清單中。
    
    若要了解如何保留信箱，請參閱[管理非使用中信箱在 Exchange Online](https://docs.microsoft.com/office365/securitycompliance/create-and-manage-inactive-mailboxes)。
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>將離職員工的電子郵件轉寄給另一個員工，或轉換為共用信箱
<a name="bkmk_forward"> </a>

在此步驟中，您將離職員工的電子郵件地址指派給其他員工，或是[將使用者的信箱轉換成您已建立的共用信箱](../email/convert-user-mailbox-to-shared-mailbox.md)。 
  
- 建立共用的信箱是較不昂貴的方式，因為您不需要支付授權 **，只要信箱小於 50GB**。 若超過 50GB，您將需要指派授權。 
    
- 假如您將信箱轉換成共用信箱，也能取得所有舊的電子郵件。這可能佔用大量空間。
    
- If you set up email forwarding, only  *new*  emails sent to the former employee will now be sent to the current employee. 
    
- 離職員工帳戶需具有授權才能使用電子郵件轉寄功能。
    
 > [!IMPORTANT] 
 > 如果您要設定電子郵件轉寄或共用的信箱，在結束時，不要刪除離職員工的帳戶。 該帳戶必須存在以做為電子郵件轉寄或共用信箱功能的錨點。 

::: moniker range="o365-worldwide"  

> [!NOTE]
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心] **開關將它開啟。

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您想要封鎖，該員工的名稱，然後選取 [**郵件**] 索引標籤。

3. 在 [**電子郵件轉寄**]，選取 [**管理電子郵件轉寄**。

4. 開啟 [**轉寄所有傳送到此信箱的電子郵件**。 在 [**轉寄地址**] 方塊中，輸入電子郵件地址目前員工 （或共用的信箱） 對於即將收到電子郵件。 
  
5. 選取 **[儲存]**。 
    
6. 請記住，不要刪除離職員工的帳戶。
 
::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您想要封鎖，並依序展開 [**郵件設定**的員工。

3. 旁**電子郵件轉寄**，選取 [**編輯**]。

4. 開啟 [**轉寄所有傳送到此信箱的電子郵件**。 在 [**轉寄地址**] 方塊中，輸入電子郵件地址目前員工 （或共用的信箱） 對於即將收到電子郵件。 
  
5. 選取 **[儲存]**。 
    
6. 請記住，不要刪除離職員工的帳戶。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您想要封鎖，並依序展開 [**郵件設定**的員工。

3. 旁**電子郵件轉寄**，選取 [**編輯**]。

4. 開啟 [**轉寄所有傳送到此信箱的電子郵件**。 在 [**轉寄地址**] 方塊中，輸入電子郵件地址目前員工 （或共用的信箱） 對於即將收到電子郵件。 
  
5. 選取 **[儲存]**。 
    
6. 請記住，不要刪除離職員工的帳戶。

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>抹除及封鎖離職員工的行動裝置
<a name="bkmk_mobile"> </a>

如果您的離職員工有組織的電話，您可以使用 Exchange 系統管理中心 抹除及封鎖該裝置，這樣就能從裝置中移除所有的組織資料，並讓裝置無法再連線到 Office 365。
  

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。

3. 在 Exchange 系統管理中心中，瀏覽至 [**收件者** \> **信箱**。 
    
4. 選取使用者，以及**行動裝置**] 下選取 [**檢視詳細資料]**。 
    
5. 在**行動裝置詳細資料**] 頁面上的**行動裝置**] 下選取 [行動裝置，請選取 [**清除資料**![清除裝置](../media/1c113a36-53cb-4974-884f-3ecd9535506e.png)，然後選取 [**封鎖**。 
    
6. 選取 **[儲存]**。 
    
    **提示**： 請務必移除或停用使用者從您的內部部署 Blackberry Enterprise Service。 您也應停用使用者的任何 Blackberry 裝置。 如需有關如何停用使用者的特定步驟，請參閱 Blackberry Business Cloud Services Administration Guide。 
    
## <a name="block-a-former-employees-access-to-office-365-data"></a>封鎖離職員工的 Office 365 資料存取權
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > 封鎖帳戶可能需要最多 24 小時才會生效。 如果您需要立即防止使用者的登入存取，您應 [重設其密碼](reset-passwords.md)，然後初始化可將使用者從所有裝置上的 Office 365 工作階段中登出的一次性事件。 請參閱[立即登出！](#sign-out-now)
 

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心] **開關將它開啟。

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工名稱及使用者的名稱下，選取符號的**封鎖這位使用者**。

3. 選取 [**封鎖登入的使用者**，然後再選取 [**儲存**。 

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工，然後選取 [**禁止登入**。

3. 選取 [**封鎖登入的使用者**，然後再選取 [**儲存**。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工，然後選取 [**禁止登入**。

3. 選取 [**封鎖登入的使用者**，然後再選取 [**儲存**。 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>封鎖離職員工的電子郵件存取權 (Exchange Online)
<a name="bkmk_block_email"> </a>

如果您的 Office 365 訂閱中包含 Office 365 電子郵件，您必須登入 Exchange 系統管理中心，並按照下列步驟封鎖離職員工存取電子郵件的權限。
  

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。
     
2. 在 Exchange 系統管理中心中，瀏覽至 [**收件者** \> **信箱**。 
    
3. 連按兩下使用者並移至 [**信箱功能**] 頁面上。 在 [**行動裝置**] 中，選取 [**停用 Exchange ActiveSync**和**停用裝置的 OWA、** 然後回答 **[是]** ，同時出現提示時。 
    
4. 在 [**電子郵件連線能力**，選取 [**停用**然後回答 **[是]** 時提示。 
    
## <a name="remove-and-delete-the-office-365-license-from-a-former-employee"></a>移除並刪除離職員工的 Office 365 授權
<a name="bkmk_remove"> </a>

貴組織有人離職之後，您須移除他們的 Office 365 授權，然後從您的訂閱中刪除授權，這樣才不用繼續為授權付費。如果您選擇不要從您的訂閱中刪除授權，您可以將授權指派給其他使用者。
  
在移除授權之後，該使用者的所有資料會保留 30 天。您可以[存取](get-access-to-and-back-up-a-former-user-s-data.md)資料，或者如果該使用者復職，也可以[還原](restore-user.md)帳戶。30 天之後，會從 Office 365 中永久刪除使用者的所有資料 (儲存在 SharePoint Online 的文件除外)，而且無法復原。 

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心] **開關將它開啟。

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您想要封鎖，該員工的名稱，然後選取 [**授權及應用程式**] 索引標籤。

4. 清除您要移除授權的核取方塊，然後選取 [**儲存變更**。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工，然後選取 [**產品授權**] 旁邊的 [**編輯**。

3. 在 [**產品授權**] 頁面上，切換關閉您想要移除，然後選取 [**儲存**授權對應。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工，然後選取 [**產品授權**] 旁邊的 [**編輯**。

3. 在 [**產品授權**] 頁面上，切換關閉您想要移除，然後選取 [**儲存**授權對應。

::: moniker-end


**若要減少您付費的授權數目**直到僱用另一個人，執行下列動作： 

::: moniker range="o365-worldwide"



1. 在系統管理中心，移至 [帳單]**** \> [產品與服務]<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank"></a> 頁面。


::: moniker-end

::: moniker range="o365-germany"

1. 在 [系統管理中心中，移至**帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">訂閱</a>] 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在 [系統管理中心中，移至**帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">訂閱</a>] 頁面。

::: moniker-end
    
2. 選取 [**新增/移除授權**來刪除授權，因此您不將它直到僱用另一個人支付]。

當您[新增](add-users.md)另一個人公司，系統會提示您購買授權在此同時，只有一個步驟 ！
    
如需有關管理商務用 Office 365 使用者授權的詳細資訊，請參閱[在商務用 Office 365 中指派授權給使用者](../manage/assign-licenses-to-users.md)，以及[在商務用 Office 365 中移除使用者授權](../manage/remove-licenses-from-users.md)。
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>已刪除的員工的帳戶會如何影響商務用 Skype
<a name="bkmk_remove"> </a>

當您在 Office 365 中移除使用者的授權後，系統會釋出與該使用者相關的 PSTN 通話號碼，方便您將該號碼指派給其他使用者。
  
如果授權被移除的使用者屬於某個佇列群組，通話佇列代理程式將無法再指定這些使用者。因此，我們建議您一併從與該通話佇列相關的群組中移除該使用者。 
  
## <a name="delete-a-former-employees-user-account"></a>刪除離職員工的使用者帳戶
<a name="bkmk_delete"> </a>

儲存並存取離職員工的所有使用者資料後，您可以刪除離職員工的帳戶。
  
如果您已經設定電子郵件轉寄功能或將它轉換為共用信箱的話，請不要刪除該帳戶。這兩者都需要該帳戶做為轉寄或共用信箱功能的錨點。

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心] **開關將它開啟。

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您想要刪除的員工的名稱。

3. 使用者的名稱下，選取符號**刪除使用者**。 選擇您要為此使用者的選項，然後選取 [**刪除的使用者**。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您想要刪除的員工的名稱。

3. 在頁面頂端，選取 [**刪除使用者**]。 選擇您要為此使用者的選項，然後選取 [**刪除的使用者**。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您想要刪除的員工的名稱。

3. 在頁面頂端，選取 [**刪除使用者**]。 選擇您要為此使用者的選項，然後選取 [**刪除的使用者**。

::: moniker-end

當您刪除使用者時，帳戶會變成非作用中的狀態並持續大約 30 天。在這段期間內，您可以還原該帳戶，但 30 天一過，就會永久刪除。
  
### <a name="does-your-organization-use-active-directory"></a>貴組織是否使用 Active Directory？

若貴組織從本機 Active Directory 環境將使用者帳戶同步處理至 Office 365，您必須在本機的 Active Directory 服務中刪除和還原這些使用者帳戶。您不能在 Office 365 刪除或還原使用者帳戶。
  
如需相關指示，請參閱這篇文章：[刪除使用者帳戶](https://go.microsoft.com/fwlink/?linkid=841808)。
  
如果您使用 Azure Active Directory，請參閱 [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell Cmdlet。 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>終止員工的電子郵件工作階段所需注意的事項
<a name="bkmk_session"> </a>

以下是如何讓員工退出電子郵件 (Exchange) 的詳細資訊。
  
|||
|:-----|:-----|
|**您可以執行的作業** <br/> |**做法** <br/> |
|終止工作階段 (例如 Outlook 網頁版、Outlook、Exchange Active Sync 等等)，並強制開啟新工作階段  <br/> |重設密碼  <br/> |
|終止工作階段並封鎖對日後工作階段的存取 (針對所有通訊協定)  <br/> |停用帳戶。例如 (在 Exchange 系統管理中心或使用 PowerShell)：  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|終止特定通訊協定的工作階段 (例如 ActiveSync)  <br/> |停用通訊協定。例如 (在 Exchange 系統管理中心或使用 PowerShell)：  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
上述作業可在 3 個位置完成：
  
|||
|:-----|:-----|
|**如果您在此處終止工作階段** <br/> |**需要多久時間** <br/> |
|在 Exchange 系統管理中心或使用 PowerShell  <br/> |預期的延遲是 30 分鐘內  <br/> |
|在 Azure Active Directory 系統管理中心  <br/> |預期的延遲是 60 分鐘  <br/> |
|在內部部署環境  <br/> |預期的延遲是 3 小時或更多  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>如何以最快速度取得帳戶終止的回應

 **最快**： 使用 Exchange 系統管理中心 （使用 PowerShell） 或 Azure Active Directory 系統管理中心。 在內部部署環境中，透過 DirSync 同步處理變更可能會花費數小時。 
  
 **使用者目前狀態內部部署與 Exchange 資料中心內的最快**： 終止工作階段使用 Azure Active Directory 系統管理中心或 Exchange 系統管理中心，並在內部部署環境中進行的變更。 若不採取此做法，在 Azure Active Directory 系統管理中心或 Exchange 系統管理中心進行的變更將被 DirSync 覆寫。 
  
## <a name="related-articles"></a>相關文章

[還原使用者](restore-user.md)
  
