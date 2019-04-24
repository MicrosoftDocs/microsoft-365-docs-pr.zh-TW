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
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 了解如何設定 Microsoft 365 商務版，請完成四個步驟。
ms.openlocfilehash: a1c8a41c3e291983276280a063248bdd10a7f85a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283876"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>使用設定精靈來設定 Microsoft 365 商務版

完成步驟 1-4 下方。
  
### <a name="set-up-microsoft-365-business"></a>設定 Microsoft 365 商務版

觀看有關如何設定 Microsoft 365 商務版，當您不需要內部部署 Active Directory 的影片：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
正確設定步驟包括包含本機 Active Directory 的設定資訊。 如果您想要繼續存取已加入網域的裝置，請閱讀下列文章針對兩個不同的方法來啟用，並完成步驟，才能執行設定精靈：
  
- [啟用由 Microsoft 365 商務版來管理已加入網域的 Windows 10 裝置](manage-windows-devices.md)
    
    -這是建議的方式。
    
- [存取內部部署 Microsoft 365 商務版中的 Azure AD 加入裝置的資源](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>步驟 1： 個人化登入

1. 使用您的全域系統管理員認證登入 [Microsoft 365 商務版](https://portal.microsoft.com)。 選擇 [移至系統管理中心的 [**管理**] 磚。 
    
2. 選擇 [**啟動安裝程式**（根據您的狀態，您可能會看到**繼續安裝程式**改為） 中的系統管理中心來啟動精靈。 
    
3. 輸入您要使用的網域名稱 (例如 contoso.com)。
    
    繼續進行並輸入您的網域，例如，即使您已在使用 Azure AD Connect 期間進行過驗證。 下列兩個步驟不適用於您，如果您使用 Azure AD Connect 來驗證您的網域。
    
4. 若要驗證您擁有該網域的[Office 365 任何 DNS 主機服務提供者處建立 DNS 記錄](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166)，請遵循精靈中的步驟。 
    
    您可以檢視範例影片[影片： 在新版系統管理中心設定 Office 365](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)。 請注意，此影片不包含 Microsoft 365 商務版的資料保護步驟。
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>步驟 2： 新增使用者並指派授權

1. 您可以在這裡新增使用者，或稍後在系統管理中心[新增使用者](add-users-m365b.md)。 
    
    您新增的使用者會自動取得 Microsoft 365 商務版授權。
    
2. 如果您的 Microsoft 365 商務版訂閱有現有的使用者 (例如，如果您使用 Azure AD Connect)，系統會提供立即將授權指派給他們的選項。請繼續進行，為他們新增授權。
    
3. 系統也會提供與您新增之使用者共用認證的選項。您可以選擇列印認證、透過電子郵件傳送認證，或是下載認證。
    
4. 略過移轉電子郵件，並在**移轉電子郵件訊息**] 頁面上選擇 [**下一步**。 
    
    如果您要移動從另一個電子郵件提供者，並想稍後複製資料，您可以[移轉電子郵件和連絡人移轉到 Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)。
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>步驟 3： 連線您的網域

> [!NOTE]
> 如果您選擇.onmicrosoft 網域，或使用 Azure AD Connect，您將不會看到此步驟。 
  
若要設定服務，您必須更新 DNS 主機或網域註冊機構中的某些記錄。
  
1. 設定精靈通常會偵測您的註冊機構，並提供您一個逐步指示連結，讓您更新在註冊機構網站上的 NS 記錄。 如果沒有，[以設定 Office 365 運用任何網域註冊機構變更名稱伺服器](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)。
    
2. 系統會為您設定電子郵件和其他服務
    
### <a name="step-4-manage-devices-and-work-files"></a>步驟 4： 管理裝置和工作檔案

1. 在**行動裝置上保護工作檔案**] 頁面上會設定**裝置遺失或遭竊時保護工作檔案**及**管理使用者如何存取行動裝置上的 Office 檔案**的設定為**上**。 您也可以存取每一項設定旁邊 > 形箭號，即可每一個子設定。
  
  所有經授權的使用者的工作檔案現在受到保護時推出 iOS 和 Android 裝置上[安裝 Office 應用程式](set-up-mobile-devices.md)（和其 Microsoft 365 商務版認證以進行驗證）。 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. 在 [**設定 Windows 10 裝置設定**] 頁面上設定**Secure Windows 10 裝置**設定為**上**。
  
   您也可以存取其旁邊 > 形箭號，即可每一個子設定。
  
3. 將**Windows 10 裝置上安裝 Office** ] 設定為 **[是]** 如果您的所有使用者有 Windows 10 電腦，而且可以是任何現有的 Office 安裝，或按一下 [隨 Office 安裝。 如果這不是這種情況，設定此選項為 [**否]**。 您可以稍後再從管理中心的 [[自動安裝 Office](auto-install-or-uninstall-office.md)之後您備妥使用者的電腦。 如需相關指示，請參閱[準備 Office 用戶端安裝](prepare-for-office-client-deployment.md)。
  
    Windows 10 裝置上的授權的使用者的工作檔案會為他們推出投影到 Microsoft 365 商務版 Azure AD 網域或同時加入 Microsoft 365 的 [[安裝 Windows 10 的新電腦上](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx)的 [[加入其 Windows 10 裝置](set-up-windows-devices.md)商務 Azure AD 網域。 
  
4. 按一下 [**下一步**，您完成安裝程式。 
  
    請將保留給我們的意見反應這個步驟，以協助我們改進經驗。
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>額外的安全性設定

除了安全性與合規性設定安裝程式精靈] 中的，您也可以設定下列其他設定：
  
- 設定防範不安全的附件。 **進階威脅防護**(ATP) 會識別惡意內容，並再封鎖不安全附件，傳遞致力於保護您抵禦網路釣魚配置和勒索軟體感染。 若要啟用附件保護，請參閱 <<c0>設定 Office 365 ATP 安全附件原則。
    
- 保護您的環境，當使用者按一下惡意連結。 ATP 會在使用者按一下這些階段檢查電子郵件中的連結。 不安全連結時，使用者是警告未以瀏覽網站，或通知網站已被封鎖。 這有助於防止網路釣魚配置。 [設定 Office 365 ATP 安全連結原則](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)或[設定 Office 365 ATP 安全連結原則](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)。
    
- 您可以保留所有信箱內容包括將使用者的整個信箱放在**訴訟資料暫留**已刪除的項目。 如需相關指示，請參閱 
- [設定搭配 Exchange Online Archiving 的電子郵件保留](security-features.md#set-up-email-retention-with-exchange-online-archiving)。
    
- 設定自訂的**保留原則**，例如，以保留經過一段時間，或在保留期間結束永久刪除內容。 您可以啟用自訂的保留原則中的證券和合規性中心，前往 [**資料控管** \> **保留**，然後依照精靈中的步驟。 若要深入了解，請參閱[保留原則的概觀](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。
    
## <a name="next-steps"></a>後續步驟

針對擁有其授權的使用者，下一個步驟是設定裝置。<br/> 請參閱[為 Microsoft 365 商務版使用者設定 Windows 裝置](set-up-windows-devices.md)和[為 Microsoft 365 商務版使用者設定行動裝置](set-up-mobile-devices.md)。 <br/>請參閱[管理 Microsoft 365 商務版](manage.md)，取得有關如何設定裝置和 App 保護原則以及如何將資料從使用者裝置中移除的主題連結。 
  


