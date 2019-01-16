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
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866125"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="46b53-103">使用設定精靈來設定 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="46b53-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="46b53-104">完成步驟 1 到 4 下。</span><span class="sxs-lookup"><span data-stu-id="46b53-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="46b53-105">設定 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="46b53-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="46b53-106">觀賞影片如何設定 Microsoft 365 商務時您不需要在內部部署 Active Directory：</span><span class="sxs-lookup"><span data-stu-id="46b53-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="46b53-p101">安裝步驟包括包括本機 Active Directory 的設定資訊。如果您想要存取已加入網域的裝置會繼續，先閱讀下列文章的兩個不同的方法來啟用，並再執行安裝精靈完成的步驟：</span><span class="sxs-lookup"><span data-stu-id="46b53-p101">The set-up steps include information for setups that include local Active Directory. If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="46b53-109">啟用 Microsoft 365 商務一併管理已加入網域的 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="46b53-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="46b53-110">-這是建議的方式。</span><span class="sxs-lookup"><span data-stu-id="46b53-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="46b53-111">存取內部部署中 Microsoft 365 商務 Azure AD 加入裝置的資源</span><span class="sxs-lookup"><span data-stu-id="46b53-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="46b53-112">步驟 1： 個人化登入</span><span class="sxs-lookup"><span data-stu-id="46b53-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="46b53-p102">使用您的全域系統管理員認證登入[Microsoft 365 Business](https://portal.microsoft.com) 。選擇 [移至系統管理中心的 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="46b53-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="46b53-115">選擇 [**啟動安裝程式**（視您的狀態您可能會看到**繼續安裝**改用） 系統管理中心來啟動精靈。</span><span class="sxs-lookup"><span data-stu-id="46b53-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="46b53-116">輸入您要使用的網域名稱 (例如 contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="46b53-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="46b53-p103">繼續並即使您已使用 Azure AD 連線，例如時驗證其輸入您的網域。下列兩個步驟並不適用於您如果您用來驗證您的網域的 Azure AD 連線。</span><span class="sxs-lookup"><span data-stu-id="46b53-p103">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example. The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="46b53-119">遵循精靈中的步驟來[建立 DNS 記錄，任何 Office 365 的 DNS 主機供應商](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166)的驗證您擁有網域。</span><span class="sxs-lookup"><span data-stu-id="46b53-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="46b53-p104">您可以檢視的範例影片[視訊： 安裝 Office 365 中新的系統管理中心](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)。請注意這段影片中不含 Microsoft 365 業務的資料保護步驟。</span><span class="sxs-lookup"><span data-stu-id="46b53-p104">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="46b53-123">步驟 2： 新增使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="46b53-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="46b53-124">您可以在這裡新增使用者，或稍後在系統管理中心[新增使用者](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="46b53-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="46b53-125">您新增的使用者會自動取得 Microsoft 365 商務版授權。</span><span class="sxs-lookup"><span data-stu-id="46b53-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="46b53-p105">如果您的 Microsoft 365 商務版訂閱有現有的使用者 (例如，如果您使用 Azure AD Connect)，系統會提供立即將授權指派給他們的選項。請繼續進行，為他們新增授權。</span><span class="sxs-lookup"><span data-stu-id="46b53-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="46b53-p106">系統也會提供與您新增之使用者共用認證的選項。您可以選擇列印認證、透過電子郵件傳送認證，或是下載認證。</span><span class="sxs-lookup"><span data-stu-id="46b53-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="46b53-130">略過移轉電子郵件訊息，並在**移轉電子郵件**] 頁面上選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="46b53-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="46b53-131">如果您要移動從另一個電子郵件供應商並想要稍後複製資料時，您可以[移轉電子郵件和 Office 365 的連絡人](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)。</span><span class="sxs-lookup"><span data-stu-id="46b53-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="46b53-133">步驟 3： 連線您的網域</span><span class="sxs-lookup"><span data-stu-id="46b53-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="46b53-134">如果您選擇使用.onmicrosoft 網域或使用 Azure AD 連線，您不會看到此步驟。</span><span class="sxs-lookup"><span data-stu-id="46b53-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="46b53-135">若要設定服務，您必須更新 DNS 主機或網域註冊機構中的某些記錄。</span><span class="sxs-lookup"><span data-stu-id="46b53-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="46b53-p107">安裝精靈通常會偵測您註冊機構並讓您連結來更新您的 NS 記錄在註冊機構網站的逐步指示。如果它不會，[來設定 Office 365 搭配任何網域註冊機構變更 nameservers](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)。</span><span class="sxs-lookup"><span data-stu-id="46b53-p107">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website. If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="46b53-138">系統會為您設定電子郵件和其他服務</span><span class="sxs-lookup"><span data-stu-id="46b53-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="46b53-139">步驟 4： 管理裝置並搭配使用的檔案</span><span class="sxs-lookup"><span data-stu-id="46b53-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="46b53-p108">在**您的行動裝置上的保護工時檔案**] 頁面上設**保護工時檔案遺失或竊裝置的時機**和**管理使用者如何存取行動裝置上的 Office 檔案**設定**上**。您也可以存取按一下旁邊每個設定欄位符號每一個子設定。</span><span class="sxs-lookup"><span data-stu-id="46b53-p108">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**. You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="46b53-142">所有已獲授權的使用者的工作檔現在受到保護為他們推出 iOS 及 Android 裝置上[安裝 Office 應用程式](set-up-mobile-devices.md)（及以其 Microsoft 365 商務認證進行驗證）。</span><span class="sxs-lookup"><span data-stu-id="46b53-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="46b53-144">在 [**設定 Windows 10 裝置設定**] 頁面上設定**Secure Windows 10 裝置**設定為**上**。</span><span class="sxs-lookup"><span data-stu-id="46b53-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="46b53-145">您也可以存取按一下其旁邊的 v 字形每一個子設定。</span><span class="sxs-lookup"><span data-stu-id="46b53-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="46b53-p109">設定**Windows 10 裝置上安裝 Office**設定為 **[是]** 如果您的所有使用者有 Windows 10 電腦，而且可以是任何現有的 Office 安裝，或按一下 [隨選 Office 安裝。如果不是這樣，設定此選項為 [**否]**。您可以稍後從管理中心的 [[自動安裝 Office](auto-install-or-uninstall-office.md)之後您已準備使用者電腦。指示，請參閱[準備 Office 用戶端安裝](prepare-for-office-client-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="46b53-p109">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs. If this is not the case, set this option to **No**. You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers. For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="46b53-150">Windows 10 裝置上的授權的使用者的工作檔案會以其推出預估[加入其 Windows 10 裝置](set-up-windows-devices.md)Microsoft 365 商務 Azure AD 網域或同時加入 [Microsoft 365 時，[安裝新的電腦上的 Windows 10](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx)商務 Azure AD 網域。</span><span class="sxs-lookup"><span data-stu-id="46b53-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="46b53-151">按一下 [**下一步**並完成安裝程式。</span><span class="sxs-lookup"><span data-stu-id="46b53-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="46b53-152">請保持我們意見反應在 [協助改善體驗我們此步驟。</span><span class="sxs-lookup"><span data-stu-id="46b53-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="46b53-154">額外安全性設定</span><span class="sxs-lookup"><span data-stu-id="46b53-154">Additional security settings</span></span>

<span data-ttu-id="46b53-155">除了版本的安全性與規範設定在 [安裝精靈] 中的，您也可以設定下列其他設定：</span><span class="sxs-lookup"><span data-stu-id="46b53-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="46b53-p110">Set up 理想的不安全的附件。**進階威脅保護**(ATP) 識別惡意內容和協助保護您對網路釣魚配置和 ransomware 感染會再封鎖的不安全的附件傳送。若要啟用附件保護，請參閱[Set up Office 365 ATP 安全附件的原則](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy)。</span><span class="sxs-lookup"><span data-stu-id="46b53-p110">Set up protection against unsafe attachments. **Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections. To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="46b53-p111">當使用者按一下惡意連結保護您的環境。ATP 會在使用者按下這些時間檢查電子郵件中的連結。若不安全的連結，使用者會收到警告不適用於瀏覽網站或得知已封鎖網站。這有助於保護網路釣魚配置。[設定 Office 365 ATP 安全連結原則](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)或[Office 365 ATP 安全連結原則設定](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)。</span><span class="sxs-lookup"><span data-stu-id="46b53-p111">Protect your environment when users click malicious links. ATP examines links in email at the time a user clicks them. If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked. This helps protect against phishing schemes. [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="46b53-p112">您可以保留所有信箱內容包括將使用者的整個信箱置於**訴訟保留**所刪除的項目。指示，請參閱</span><span class="sxs-lookup"><span data-stu-id="46b53-p112">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**. For instructions, see</span></span> 
- <span data-ttu-id="46b53-166">[與 Exchange Online 封存的電子郵件保留設定](security-features.md#set-up-email-retention-with-exchange-online-archiving)。</span><span class="sxs-lookup"><span data-stu-id="46b53-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="46b53-p113">設定自訂**的保留原則**，例如以保留為特定的時間長度或結尾處的保留期限永久刪除內容。您可以啟用自訂的保留原則中的證券和規範管理中心，移至 [**資料控管** \> **保留**，然後依照精靈中的步驟。若要深入了解，請參閱 ＜ [Overview of 保留原則](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="46b53-p113">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard. To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="46b53-170">後續步驟</span><span class="sxs-lookup"><span data-stu-id="46b53-170">Next steps</span></span>

<span data-ttu-id="46b53-171">針對擁有其授權的使用者，下一個步驟是設定裝置。</span><span class="sxs-lookup"><span data-stu-id="46b53-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="46b53-172">請參閱[為 Microsoft 365 商務版使用者設定 Windows 裝置](set-up-windows-devices.md)和[為 Microsoft 365 商務版使用者設定行動裝置](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="46b53-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="46b53-173">請參閱[管理 Microsoft 365 商務版](manage.md)，取得有關如何設定裝置和 App 保護原則以及如何將資料從使用者裝置中移除的主題連結。</span><span class="sxs-lookup"><span data-stu-id="46b53-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


