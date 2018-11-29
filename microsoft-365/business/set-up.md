---
title: 使用設定精靈來設定 Microsoft 365 商務版
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 了解如何設定 Microsoft 365 商務完成四個步驟。
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866125"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>使用設定精靈來設定 Microsoft 365 商務版

完成步驟 1 到 4 下。
  
### <a name="set-up-microsoft-365-business"></a>設定 Microsoft 365 商務版

觀賞影片如何設定 Microsoft 365 商務時您不需要在內部部署 Active Directory：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
安裝步驟包括包括本機 Active Directory 的設定資訊。如果您想要存取已加入網域的裝置會繼續，先閱讀下列文章的兩個不同的方法來啟用，並再執行安裝精靈完成的步驟：
  
- [啟用 Microsoft 365 商務一併管理已加入網域的 Windows 10 裝置](manage-windows-devices.md)
    
    -這是建議的方式。
    
- [存取內部部署中 Microsoft 365 商務 Azure AD 加入裝置的資源](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>步驟 1： 個人化登入

1. 使用您的全域系統管理員認證登入[Microsoft 365 Business](https://portal.microsoft.com) 。選擇 [移至系統管理中心的 [**管理**] 磚。 
    
2. 選擇 [**啟動安裝程式**（視您的狀態您可能會看到**繼續安裝**改用） 系統管理中心來啟動精靈。 
    
3. 輸入您要使用的網域名稱 (例如 contoso.com)。
    
    繼續並即使您已使用 Azure AD 連線，例如時驗證其輸入您的網域。下列兩個步驟並不適用於您如果您用來驗證您的網域的 Azure AD 連線。
    
4. 遵循精靈中的步驟來[建立 DNS 記錄，任何 Office 365 的 DNS 主機供應商](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166)的驗證您擁有網域。 
    
    您可以檢視的範例影片[視訊： 安裝 Office 365 中新的系統管理中心](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)。請注意這段影片中不含 Microsoft 365 業務的資料保護步驟。
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>步驟 2： 新增使用者並指派授權

1. 您可以在這裡新增使用者，或稍後在系統管理中心[新增使用者](add-users-m365b.md)。 
    
    您新增的使用者會自動取得 Microsoft 365 商務版授權。
    
2. 如果您的 Microsoft 365 商務版訂閱有現有的使用者 (例如，如果您使用 Azure AD Connect)，系統會提供立即將授權指派給他們的選項。請繼續進行，為他們新增授權。
    
3. 系統也會提供與您新增之使用者共用認證的選項。您可以選擇列印認證、透過電子郵件傳送認證，或是下載認證。
    
4. 略過移轉電子郵件訊息，並在**移轉電子郵件**] 頁面上選擇 [**下一步**。 
    
    如果您要移動從另一個電子郵件供應商並想要稍後複製資料時，您可以[移轉電子郵件和 Office 365 的連絡人](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)。
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>步驟 3： 連線您的網域

> [!NOTE]
> 如果您選擇使用.onmicrosoft 網域或使用 Azure AD 連線，您不會看到此步驟。 
  
若要設定服務，您必須更新 DNS 主機或網域註冊機構中的某些記錄。
  
1. 安裝精靈通常會偵測您註冊機構並讓您連結來更新您的 NS 記錄在註冊機構網站的逐步指示。如果它不會，[來設定 Office 365 搭配任何網域註冊機構變更 nameservers](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)。
    
2. 系統會為您設定電子郵件和其他服務
    
### <a name="step-4-manage-devices-and-work-files"></a>步驟 4： 管理裝置並搭配使用的檔案

1. 在**您的行動裝置上的保護工時檔案**] 頁面上設**保護工時檔案遺失或竊裝置的時機**和**管理使用者如何存取行動裝置上的 Office 檔案**設定**上**。您也可以存取按一下旁邊每個設定欄位符號每一個子設定。
  
  所有已獲授權的使用者的工作檔現在受到保護為他們推出 iOS 及 Android 裝置上[安裝 Office 應用程式](set-up-mobile-devices.md)（及以其 Microsoft 365 商務認證進行驗證）。 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. 在 [**設定 Windows 10 裝置設定**] 頁面上設定**Secure Windows 10 裝置**設定為**上**。
  
   您也可以存取按一下其旁邊的 v 字形每一個子設定。
  
3. 設定**Windows 10 裝置上安裝 Office**設定為 **[是]** 如果您的所有使用者有 Windows 10 電腦，而且可以是任何現有的 Office 安裝，或按一下 [隨選 Office 安裝。如果不是這樣，設定此選項為 [**否]**。您可以稍後從管理中心的 [[自動安裝 Office](auto-install-or-uninstall-office.md)之後您已準備使用者電腦。指示，請參閱[準備 Office 用戶端安裝](prepare-for-office-client-deployment.md)。
  
    Windows 10 裝置上的授權的使用者的工作檔案會以其推出預估[加入其 Windows 10 裝置](set-up-windows-devices.md)Microsoft 365 商務 Azure AD 網域或同時加入 [Microsoft 365 時，[安裝新的電腦上的 Windows 10](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx)商務 Azure AD 網域。 
  
4. 按一下 [**下一步**並完成安裝程式。 
  
    請保持我們意見反應在 [協助改善體驗我們此步驟。
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>額外安全性設定

除了版本的安全性與規範設定在 [安裝精靈] 中的，您也可以設定下列其他設定：
  
- Set up 理想的不安全的附件。**進階威脅保護**(ATP) 識別惡意內容和協助保護您對網路釣魚配置和 ransomware 感染會再封鎖的不安全的附件傳送。若要啟用附件保護，請參閱[Set up Office 365 ATP 安全附件的原則](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy)。
    
- 當使用者按一下惡意連結保護您的環境。ATP 會在使用者按下這些時間檢查電子郵件中的連結。若不安全的連結，使用者會收到警告不適用於瀏覽網站或得知已封鎖網站。這有助於保護網路釣魚配置。[設定 Office 365 ATP 安全連結原則](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)或[Office 365 ATP 安全連結原則設定](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)。
    
- 您可以保留所有信箱內容包括將使用者的整個信箱置於**訴訟保留**所刪除的項目。指示，請參閱 
- [與 Exchange Online 封存的電子郵件保留設定](security-features.md#set-up-email-retention-with-exchange-online-archiving)。
    
- 設定自訂**的保留原則**，例如以保留為特定的時間長度或結尾處的保留期限永久刪除內容。您可以啟用自訂的保留原則中的證券和規範管理中心，移至 [**資料控管** \> **保留**，然後依照精靈中的步驟。若要深入了解，請參閱 ＜ [Overview of 保留原則](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。
    
## <a name="next-steps"></a>後續步驟

針對擁有其授權的使用者，下一個步驟是設定裝置。<br/> 請參閱[為 Microsoft 365 商務版使用者設定 Windows 裝置](set-up-windows-devices.md)和[為 Microsoft 365 商務版使用者設定行動裝置](set-up-mobile-devices.md)。 <br/>請參閱[管理 Microsoft 365 商務版](manage.md)，取得有關如何設定裝置和 App 保護原則以及如何將資料從使用者裝置中移除的主題連結。 
  


