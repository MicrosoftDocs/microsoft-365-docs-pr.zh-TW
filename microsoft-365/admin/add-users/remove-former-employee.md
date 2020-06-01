---
title: 移除離職員工
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: '遵循此檢查清單，從 Microsoft 365 中移除員工，並保護資料安全。 '
ms.openlocfilehash: 1b691d948576a3949d637d2de05b6f931844037c
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431650"
---
# <a name="remove-a-former-employee"></a>移除離職員工

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end
  
## <a name="sign-out-now"></a>立即登出！

::: moniker range="o365-worldwide"

觀賞有關移除員工的簡短影片。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

若要移除員工：

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 選取使用者名稱旁的方塊，然後選取 [**重設密碼**]。

3. 輸入新密碼，然後選取 [**重設**]。 （不要將其傳送給他們）。
    
4. 選取使用者的名稱以移至其屬性窗格，然後在 [ **OneDrive** ] 索引標籤上，選取 [**啟動登出**]。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

2. 選取使用者，然後選取 [**重設密碼**]。

3. 輸入新密碼，然後選取 [**重設**]。 （不要將其傳送給他們）。

4. 再次選取使用者，展開 [ **OneDrive 設定**]，然後選取 [登出] 旁邊**的**[**啟動**]。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

2. 選取使用者，然後選取 [**重設密碼**]。

3. 輸入新密碼，然後選取 [**重設**]。 （不要將其傳送給他們）。

4. 再次選取使用者，展開 [ **OneDrive 設定**]，然後選取 [登出] 旁邊**的**[**啟動**]。

::: moniker-end

    
在一小時內，或在他們保留目前的 Microsoft 365 頁面時，系統會提示他們重新登入。 （存取權杖適用于一個小時，所以時程表取決於該權杖所留下的時間，以及是否要流覽至目前的網頁。）
  
 **警告**：如果使用者在 Outlook 網頁版上，只要在其信箱中按一下 [離開]，就不會立即開啟。 當他們選取不同的麻將牌（例如 OneDrive，或重新整理其瀏覽器）時，就會開始登出。 
  
若要使用 PowerShell 立即將使用者登出，請參閱 [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345) Cmdlet。 
  
如需花費多久時間以將某人退出電子郵件的詳細資訊，請參閱[終止員工的電子郵件工作階段所需注意的事項](#what-you-need-to-know-about-terminating-an-employees-email-session)。
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>移除員工及保護資料的所有步驟的概觀
<a name="bkmk_now"> </a>

我們常遇到的問題是：「員工離開組織時，應如何保護資料？」 本文說明如何封鎖 Microsoft 365 的存取，以及您應採取哪些步驟保護您的資料。
  
> [!NOTE]
> 如果您是全域系統管理員，您可以刪除員工、轉寄其電子郵件、使用新的引導體驗選擇要如何處理其 OneDrive 內容。 如需詳細資訊，請參閱[全域系統管理員：刪除使用者](remove-former-employee.md)。 不過，我們建議您完成此處所列的所有其他步驟，以確定員工沒有公司資料的存取權。 
  
以下是快速概觀。 本文會詳細說明每個步驟。
  
|||
|:-----|:-----|
|**步驟** <br/> |**這樣做的原因** <br/> |
|1. [儲存離職員工信箱的內容](#save-the-contents-of-a-former-employees-mailbox) <br/> |對於即將接掌員工工作或萬一發生訴訟這些情況來說，這樣做非常有效。  <br/> |
|2.[將離職員工的電子郵件轉寄給另一個員工，或轉換為共用信箱](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |這讓離職員工的電子郵件地址也能繼續保持有效。如果客戶或合作夥伴仍將電子郵件傳送到離職員工的地址，這樣做可讓他們與接掌工作的人員取得聯繫。  <br/> |
|3. [抹除及封鎖離職員工的行動裝置](#wipe-and-block-a-former-employees-mobile-device) <br/> |從手機或平板電腦中移除您的業務資料。  <br/> |
|4.[封鎖離職員工對 Microsoft 365 資料的存取權](#block-a-former-employees-access-to-microsoft-365-data)<br/> |它可防止人員存取其舊的 Microsoft 365 信箱和資料。  <br/><br/> **提示**：當您封鎖使用者的存取權時，您仍需支付其授權。 您必須從您的訂閱中刪除該授權才能停止付費 (步驟 5)。           |
|5.[移動員工的 OneDrive 內容](get-access-to-and-back-up-a-former-user-s-data.md) (機器翻譯) <br/> |如果您只移除使用者的授權，但不刪除帳戶，則使用者 OneDrive 中的內容將會保留，即使超過 30 天後仍可存取。  <br/><br/> 在您刪除帳戶之前，您應該將其 OneDrive 內容移動至另一個可讓您輕鬆存取的位置。 在您刪除員工的帳戶之後，其 OneDrive 中的內容會保留**30**天。 不過，在這 30 天內，您可以還原使用者的帳戶，並取得其 OneDrive 內容的存取權。 如果您還原該使用者的帳戶，其 OneDrive 內容將會保留，即使超過 30 天後仍可存取。  <br/> |
|5a. 如果該人員使用個人電腦存取 OneDrive 和 SharePoint，會怎麼樣？  <br/> |如果他們使用個人電腦 (而不是公司核發的電腦) 從 OneDrive 和 SharePoint 下載檔案，您就無法抹除他們儲存的檔案。  <br/><br/> 他們將可繼續存取已同步處理到電腦的任何檔案。  <br/> |
|6.[從離職員工移除並刪除 Microsoft 365 授權](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |當您移除授權時，您可將授權指派給其他人員。或者，您也可以刪除授權，這樣就不必在雇用另一位人員之前繼續付費。<br/><br/> 當您移除或刪除授權時，使用者的舊電子郵件、連絡人及行事曆會保留**30 天**，然後永久刪除。 如果您移除或刪除使用者的授權，但不刪除帳戶，則使用者 OneDrive 中的將會保留，即使超過 30 天後仍可存取。  <br/> |
|7. [刪除離職員工的使用者帳戶](#delete-a-former-employees-user-account)<br/> |這會從您的系統管理中心移除帳戶。 保持有條不紊。  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>儲存離職員工信箱的內容
<a name="bkmk_preserve"> </a>

有兩種方法可儲存離職員工信箱的內容：
  
1. 將離職員工的電子郵件地址新增到您的 Outlook 2013 或 2016 版本，然後將資料匯出到 .pst 檔案。您可以視需要將資料匯入到其他電子郵件帳戶。若要了解做法，請參閱[存取及備份離職使用者的資料](get-access-to-and-back-up-a-former-user-s-data.md)。
    
    或
    
2. 在刪除使用者帳戶之前，將其信箱設為訴訟資料暫留或就地保留。雖然這個方法比第一個選項複雜，但如果發生下列情況，就適合採用這個方法︰您的企業方案包含封存和法務保存措施、企業可能要進行訴訟，以及企業擁有技術強大的 IT 部門。
    
    一旦您將信箱轉換成「非作用中的信箱」，系統管理員、法務人員或記錄管理員就能使用 Exchange Online 中的就地電子文件探索工具存取及搜尋當中的內容。
    
    非作用中的信箱無法接收電子郵件，也不會顯示於貴組織的共用通訊錄或其他清單中。
    
    若要瞭解如何對信箱進行保留，請參閱[在 Exchange Online 中管理非使用中的信箱](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)。
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>將離職員工的電子郵件轉寄給另一個員工，或轉換為共用信箱
<a name="bkmk_forward"> </a>

在此步驟中，您將離職員工的電子郵件地址指派給其他員工，或是[將使用者的信箱轉換成您已建立的共用信箱](../email/convert-user-mailbox-to-shared-mailbox.md)。 
  
- 建立共用信箱是不太昂貴的方式，因為您不需要支付授權，只要信箱小於**50GB**。 若超過 50GB，您將需要指派授權。 
    
- 假如您將信箱轉換成共用信箱，也能取得所有舊的電子郵件。這可能佔用大量空間。
    
- If you set up email forwarding, only  *new*  emails sent to the former employee will now be sent to the current employee. 
    
- 離職員工帳戶需具有授權才能使用電子郵件轉寄功能。
    
 > [!IMPORTANT] 
 > 如果您正在設定電子郵件轉寄或共用信箱，請不要刪除離職員工的帳戶。 該帳戶必須存在以做為電子郵件轉寄或共用信箱功能的錨點。 

::: moniker range="o365-worldwide"  

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工名稱，然後選取 [**郵件**] 索引標籤。

3. 在 [**電子郵件**轉寄] 底下，選取 [**管理電子郵件轉發**]。

4. 開啟 [**轉寄所有傳送至此信箱的電子郵件**]。 在 [轉寄**位址**] 方塊中，輸入即將取得電子郵件的目前員工（或共用信箱）的電子郵件地址。 
  
5. 選取 **[儲存]**。 
    
6. 請記住，不要刪除離職員工的帳戶。
 
::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工，然後展開 [**郵件設定**]。

3. 在 [**電子郵件轉發**] 旁，選取 [**編輯**]。

4. 開啟 [**轉寄所有傳送至此信箱的電子郵件**]。 在 [轉寄**位址**] 方塊中，輸入即將取得電子郵件的目前員工（或共用信箱）的電子郵件地址。 
  
5. 選取 **[儲存]**。 
    
6. 請記住，不要刪除離職員工的帳戶。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工，然後展開 [**郵件設定**]。

3. 在 [**電子郵件轉發**] 旁，選取 [**編輯**]。

4. 開啟 [**轉寄所有傳送至此信箱的電子郵件**]。 在 [轉寄**位址**] 方塊中，輸入即將取得電子郵件的目前員工（或共用信箱）的電子郵件地址。 
  
5. 選取 **[儲存]**。 
    
6. 請記住，不要刪除離職員工的帳戶。

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>抹除及封鎖離職員工的行動裝置
<a name="bkmk_mobile"> </a>

如果您的離職員工有組織的電話，您可以使用 Exchange 系統管理中心 抹除及封鎖該裝置，這樣就能從裝置中移除所有的組織資料，並讓裝置無法再連線到 Office 365。
  

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。

3. 在 Exchange 系統管理中心中，**流覽至 [** 收件者] [ \> **信箱**]。 
    
4. 選取使用者，然後在 [行動**裝置**] 底下，選取 [**查看詳細資料**]。 
    
5. 在 [行動**裝置詳細資料**] 頁面的 [行動**裝置**] 下，選取行動裝置，選取 [**清除資料** ![ 清除裝置] ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) ，然後選取 [**封鎖**]。 
    
6. 選取 **[儲存]**。 
    
    **秘訣**：請確定您已移除或停用內部部署 Blackberry Enterprise Service 中的使用者。 您也應停用使用者的任何 Blackberry 裝置。 如需有關如何停用使用者的特定步驟，請參閱 Blackberry Business Cloud Services Administration Guide。 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>封鎖離職員工對 Microsoft 365 資料的存取權
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > 封鎖帳戶最多可能需要24小時才會生效。 如果您需要立即避免使用者登入存取，您應該[重設其密碼](reset-passwords.md)，然後啟動一次性事件，將其從所有裝置的 Microsoft 365 會話中登出。 請參閱[立即登出！](#sign-out-now)
 

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工名稱，在使用者的名稱下，選取 [**封鎖此使用者**的符號]。

3. 選取 [**封鎖使用者登入**]，然後選取 [**儲存**]。 

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工，然後選取 [封鎖登**入**]。

3. 選取 [**封鎖使用者登入**]，然後選取 [**儲存**]。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工，然後選取 [封鎖登**入**]。

3. 選取 [**封鎖使用者登入**]，然後選取 [**儲存**]。 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>封鎖離職員工的電子郵件存取權 (Exchange Online)
<a name="bkmk_block_email"> </a>

如果您的電子郵件是 Microsoft 365 訂閱的一部分，您必須登入 Exchange 系統管理中心以執行下列步驟，以封鎖您的離職員工存取其電子郵件。
  

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。
     
2. 在 Exchange 系統管理中心中，**流覽至 [** 收件者] [ \> **信箱**]。 
    
3. 按兩下使用者並移至 [**信箱功能**] 頁面。 在 [行動**裝置**] 下，選取 [**停用 Exchange ActiveSync** ] 和 [**停用裝置的 OWA]，** 然後在出現提示時回答 **[是]** 
    
4. 在 [**電子郵件**連線] 下，選取 [**停**用並在提示時回答**Yes]** 。 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>移除並刪除離職員工的 Microsoft 365 授權
<a name="bkmk_remove"> </a>

所以，當有人離開您的組織後，您就不會繼續支付授權，因此您必須移除其 Microsoft 365 授權，然後將其從您的訂閱中刪除。 如果您選擇不要從您的訂閱中刪除授權，您可以將授權指派給其他使用者。
  
在移除授權之後，該使用者的所有資料會保留 30 天。 您可以[存取](get-access-to-and-back-up-a-former-user-s-data.md)資料，或者如果該使用者復職，也可以[還原](restore-user.md)帳戶。 30天后，會從 Microsoft 365 永久刪除使用者的所有資料（儲存在 SharePoint Online 上的檔除外），且無法復原。 

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工名稱，然後選取 [**授權與應用程式**] 索引標籤。

4. 清除您要移除之授權的核取方塊，然後選取 [**儲存變更**]。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工，然後在 [**產品授權**] 旁，選取 [**編輯**]。

3. 在 [**產品授權**] 頁面上，關閉您要移除的授權，然後選取 [**儲存**]。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要封鎖的員工，然後在 [**產品授權**] 旁，選取 [**編輯**]。

3. 在 [**產品授權**] 頁面上，關閉您要移除的授權，然後選取 [**儲存**]。

::: moniker-end


**若要減少**您在雇用另一個人之前所支付的授權數量，請執行下列操作： 

::: moniker range="o365-worldwide"



1. 在系統管理中心，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[您的產品]</a> 頁面。


::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，前往 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">[訂閱]</a> 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，前往 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[訂閱]</a> 頁面。

::: moniker-end
    
2. 選取 [**新增/移除**授權] 以刪除授權，以便在您雇用另一個人之前不必支付。

當您在公司中[新增](add-users.md)其他人員時，系統會同時提示您購買授權，只須一個步驟！
    
如需管理 Microsoft 365 for business 之使用者授權的詳細資訊，請參閱[在 microsoft 365 for business 中指派授權給使用者](../manage/assign-licenses-to-users.md)，以及[從 Microsoft 365 for business 中的使用者移除授權](../manage/remove-licenses-from-users.md)。
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>已刪除的員工的帳戶會如何影響商務用 Skype
<a name="bkmk_remove"> </a>

當您在 Office 365 中移除使用者的授權後，系統會釋出與該使用者相關的 PSTN 通話號碼，方便您將該號碼指派給其他使用者。
  
如果授權被移除的使用者屬於某個佇列群組，通話佇列代理程式將無法再指定這些使用者。因此，我們建議您一併從與該通話佇列相關的群組中移除該使用者。 
  
## <a name="delete-a-former-employees-user-account"></a>刪除離職員工的使用者帳戶
<a name="bkmk_delete"> </a>

儲存並存取離職員工的所有使用者資料後，您可以刪除離職員工的帳戶。
  
如果您已經設定電子郵件轉寄功能或將它轉換為共用信箱的話，請不要刪除該帳戶。這兩者都需要該帳戶做為轉寄或共用信箱功能的錨點。

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要刪除的員工名稱。

3. 在使用者的名稱下，選取 [**刪除使用者**的符號]。 為此使用者選擇您想要的選項，然後選取 [**刪除使用者**]。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要刪除的員工名稱。

3. 在頁面頂端，選取 [**刪除使用者**]。 為此使用者選擇您想要的選項，然後選取 [**刪除使用者**]。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要刪除的員工名稱。

3. 在頁面頂端，選取 [**刪除使用者**]。 為此使用者選擇您想要的選項，然後選取 [**刪除使用者**]。

::: moniker-end

當您刪除使用者時，帳戶會變成非作用中的狀態並持續大約 30 天。在這段期間內，您可以還原該帳戶，但 30 天一過，就會永久刪除。
  
### <a name="does-your-organization-use-active-directory"></a>貴組織是否使用 Active Directory？

如果您的組織將使用者帳戶從本機 Active Directory 環境同步處理至 Microsoft 365，您必須在本機 Active Directory 服務中刪除及還原這些使用者帳戶。 您不能在 Office 365 刪除或還原使用者帳戶。
  
如需相關指示，請參閱本文：[刪除使用者帳戶](https://go.microsoft.com/fwlink/?linkid=841808)。
  
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

 **最快**：使用 Exchange 系統管理中心（使用 PowerShell）或 Azure Active Directory 系統管理中心。 在內部部署環境中，透過 DirSync 同步處理變更可能會花費數小時。 
  
 使用**內部部署與 Exchange Datacenter 中的使用者速度最快**：使用 Azure Active Directory 系統管理中心/Exchange 系統管理中心終止會話，並在內部部署環境中也進行變更。 若不採取此做法，在 Azure Active Directory 系統管理中心或 Exchange 系統管理中心進行的變更將被 DirSync 覆寫。 
  
## <a name="related-articles"></a>相關文章

[還原使用者](restore-user.md)
  
