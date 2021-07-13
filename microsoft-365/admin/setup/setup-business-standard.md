---
title: 設定 Microsoft 365 商務標準版
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- BEA160
description: 當您購買 Microsoft 365 商務標準版時，您可以選擇使用自己的網域，或在註冊時購買一個網域。
ms.openlocfilehash: 861a9e38f10f0cd654e2b10c1879811cd668bc1f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393808"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="be90e-103">設定 Microsoft 商務標準版</span><span class="sxs-lookup"><span data-stu-id="be90e-103">Set up Microsoft Business Standard</span></span>



## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="be90e-104">新增您的網域以個人化登入</span><span class="sxs-lookup"><span data-stu-id="be90e-104">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="be90e-105">當您購買 Microsoft 365 商務標準版時，您可以選擇使用自己的網域，或在註冊時購買一個網域。</span><span class="sxs-lookup"><span data-stu-id="be90e-105">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="be90e-106">如果您在註冊時購買新的網域，則您的網域全都都已設定完畢，您可以移至 [新增使用者並指派授權](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="be90e-106">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="be90e-107">使用您的全域系統管理員認證登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="be90e-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="be90e-108">請選擇 **[移至設定]** 來啟動精靈。</span><span class="sxs-lookup"><span data-stu-id="be90e-108">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="be90e-109">在 **[安裝您的 Office 應用程式]** 頁面上，您可以選擇將應用程式安裝到自己的電腦上。</span><span class="sxs-lookup"><span data-stu-id="be90e-109">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="be90e-110">在 **[新增網域]** 步驟中，輸入您要使用的網域名城（例如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="be90e-110">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="be90e-p101">如果您在註冊時購買了網域，就不會在此看到 **[新增網域]** 步驟。請改為前往 [[新增使用者]](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="be90e-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="be90e-113">按照精靈中的步驟操作，在任何可驗證您擁有網域的[ 適用於 Office 365 的 DNS 主機服務供應商中建立 DNS 記錄](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。</span><span class="sxs-lookup"><span data-stu-id="be90e-113">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="be90e-114">如果您知道您的網域主機，請參閱[新增網域至 Microsoft 365](/microsoft-365/admin/setup/add-domain)。</span><span class="sxs-lookup"><span data-stu-id="be90e-114">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="be90e-115">如果您的主機服務供應商是 GoDaddy 或透過 [[網域連結]](/office365/admin/get-help-with-domains/domain-connect) 所啟用的另一個主機，這個過程便會很簡單，您自動便會被要求登入，並讓 Microsoft 替您進行驗證。</span><span class="sxs-lookup"><span data-stu-id="be90e-115">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![在 GoDaddy 確認存取頁面上，選取 [授權]。](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="be90e-117">新增使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="be90e-117">Add users and assign licenses</span></span>

<span data-ttu-id="be90e-118">您可以在精靈中新增使用者，或稍後在系統管理中心[[新增使用者]](../add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="be90e-118">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="be90e-119">此外，如果您有本機網域控制站，您可以使用 [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express)新增使用者。</span><span class="sxs-lookup"><span data-stu-id="be90e-119">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="be90e-120">在精靈中新增使用者</span><span class="sxs-lookup"><span data-stu-id="be90e-120">Add users in the wizard</span></span>

<span data-ttu-id="be90e-121">您在精靈中所新增的任何使用者，都會自動指派 Microsoft 365 商務標準版授權。</span><span class="sxs-lookup"><span data-stu-id="be90e-121">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="be90e-p104">如果您的 Microsoft 365 商務標準版訂閱有現有的使用者 (例如，如果您使用 Azure AD Connect 的話)，系統會提供立即將授權指派給他們的選項。請繼續進行，並為他們新增授權。</span><span class="sxs-lookup"><span data-stu-id="be90e-p104">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="be90e-p105">新增使用者之後，系統也會提供與您新增之使用者共用認證的選項。您可以選擇列印認證、透過電子郵件傳送認證，或是下載認證。</span><span class="sxs-lookup"><span data-stu-id="be90e-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="be90e-126">連接您的網域</span><span class="sxs-lookup"><span data-stu-id="be90e-126">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="be90e-127">如果您選擇使用 onmicrosoft 網域，或使用 Azure AD Connect 來設定使用者，您將不會看到此步驟。</span><span class="sxs-lookup"><span data-stu-id="be90e-127">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="be90e-128">若要設定服務，您必須更新 DNS 主機或網域註冊機構中的某些記錄。</span><span class="sxs-lookup"><span data-stu-id="be90e-128">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="be90e-129">設定精靈通常會偵測您的註冊機構，並提供您一個逐步指示連結，讓您更新在註冊機構網站上的 NS 記錄。</span><span class="sxs-lookup"><span data-stu-id="be90e-129">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="be90e-130">如果沒有，請[變更名稱伺服器，以透過任何網域註冊機構來設定 Office 365](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="be90e-130">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="be90e-131">如果您有現有的 DNS 記錄，例如現有網站，但您的 DNS 主機已啟用 [網域連線](/office365/admin/get-help-with-domains/domain-connect)，請選擇 **[為我新增記錄]**。</span><span class="sxs-lookup"><span data-stu-id="be90e-131">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="be90e-132">在 **[選擇您的線上服務]** 頁面，接受所有預設值，並選擇 **[下一步]**，然後在您的 DNS 主機頁面上選擇 **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="be90e-132">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="be90e-p108">如果您的現有 DNS 記錄中有其他 DNS 主機(該主機無法用於網域連線)，您最好能自己管理自己的 DNS 記錄，以確保現有服務保持連線。如需詳情，請查看[網域基本資料](/office365/admin/get-help-with-domains/dns-basics)。</span><span class="sxs-lookup"><span data-stu-id="be90e-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="be90e-135">按照精靈中的步驟進行，系統會為您設定電子郵件及其他服務。</span><span class="sxs-lookup"><span data-stu-id="be90e-135">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="be90e-136">註冊程序完成後，系統會將您導向系統管理中心，您可以在該處按照精靈來安裝 Office 應用程式、新增您的網域、新增使用者，以及指派授權。</span><span class="sxs-lookup"><span data-stu-id="be90e-136">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="be90e-137">完成初始安裝後，您可以使用系統管理中心的 [設定] 頁面繼續設定和設定訂閱隨附的服務。</span><span class="sxs-lookup"><span data-stu-id="be90e-137">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="be90e-138">如需有關安裝精靈和系統管理中心 [設定] 頁面的詳細資訊，請參閱[安裝精靈和設定頁面之間的差異](o365-setup-wizard-and-setup-page.md)。</span><span class="sxs-lookup"><span data-stu-id="be90e-138">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="be90e-139">完成設定</span><span class="sxs-lookup"><span data-stu-id="be90e-139">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="be90e-140">設定 Outlook 以收發電子郵件</span><span class="sxs-lookup"><span data-stu-id="be90e-140">Set up Outlook for email</span></span>

1. <span data-ttu-id="be90e-141">在 Windows [開始] 功能表上，搜尋並選取 Outlook</span><span class="sxs-lookup"><span data-stu-id="be90e-141">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="be90e-142">(如果您是使用 Mac，請從工具列開啟 Outlook 或使用 Finder 尋找)。</span><span class="sxs-lookup"><span data-stu-id="be90e-142">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="be90e-143">如果您剛安裝 Outlook，請在 [歡迎] 頁面上選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="be90e-143">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="be90e-144">依序選擇 **[檔案]** \> **[資訊]** \> **[新增帳戶]**。</span><span class="sxs-lookup"><span data-stu-id="be90e-144">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="be90e-145">輸入您的 Microsoft 電子郵件地址，然後選取 **[連線]**。</span><span class="sxs-lookup"><span data-stu-id="be90e-145">Enter your Microsoft email address and select **Connect**.</span></span>

## <a name="watch-set-up-outlook-for-email"></a><span data-ttu-id="be90e-146">觀看：設定 Outlook 以收發電子郵件</span><span class="sxs-lookup"><span data-stu-id="be90e-146">Watch: Set up Outlook for email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="be90e-147">如需更多資訊，請參閱[設定 Outlook 以收發電子郵件](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f)。</span><span class="sxs-lookup"><span data-stu-id="be90e-147">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="be90e-148">匯入電子郵件</span><span class="sxs-lookup"><span data-stu-id="be90e-148">Import email</span></span>

<span data-ttu-id="be90e-149">如果您使用的是 Outlook 搭配另一個電子郵件帳戶，您可以將之前的電子郵件、行事曆和連絡人匯入到新的 Microsoft 帳戶。</span><span class="sxs-lookup"><span data-stu-id="be90e-149">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="be90e-150">**匯出舊的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="be90e-150">**Export your old email**</span></span>

    <span data-ttu-id="be90e-151">在 Outlook 中，依序選擇 **[檔案]** \> **[開啟和匯出]** \> **[匯入/匯出]**。</span><span class="sxs-lookup"><span data-stu-id="be90e-151">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="be90e-152">選取 **[匯出至檔案]**，然後遵循步驟來匯出您的 Outlook 資料檔 (.pst) 和任何子資料夾。</span><span class="sxs-lookup"><span data-stu-id="be90e-152">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="be90e-153">**匯入舊的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="be90e-153">**Import your old email**</span></span>

    <span data-ttu-id="be90e-154">在 Outlook 中，再次選擇 **[檔案]** \> **[開啟和匯出]** \> **[匯入/匯出]**。</span><span class="sxs-lookup"><span data-stu-id="be90e-154">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="be90e-155">這次請選取 **[從其他程式或檔案匯入]**，並遵循步驟來匯入舊電子郵件時建立的備份檔案。</span><span class="sxs-lookup"><span data-stu-id="be90e-155">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

## <a name="watch-import-and-redirect-email"></a><span data-ttu-id="be90e-156">觀看：匯入和重新導向電子郵件</span><span class="sxs-lookup"><span data-stu-id="be90e-156">Watch: Import and redirect email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="be90e-157">如需更多資訊，請參閱[使用 Outlook 匯入電子郵件](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de)。</span><span class="sxs-lookup"><span data-stu-id="be90e-157">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="be90e-158">您也可以使用 Exchange 系統管理中心匯入每個人的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="be90e-158">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="be90e-159">如需詳細資訊，請參閱[[移轉多個電子郵件帳戶]](/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="be90e-159">For more information, see [migrate multiple email accounts](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="be90e-160">使用公用網站</span><span class="sxs-lookup"><span data-stu-id="be90e-160">Use a public website</span></span>

<span data-ttu-id="be90e-161">Microsoft 365 不包含貴公司的公用網站。</span><span class="sxs-lookup"><span data-stu-id="be90e-161">Microsoft 365 doesn't include a public website for your business.</span></span> <span data-ttu-id="be90e-162">如果您想要設立一個，請考慮使用 Microsoft 合作夥伴，例如 GoDaddy 或 WIX。</span><span class="sxs-lookup"><span data-stu-id="be90e-162">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="be90e-163">從系統管理中心，移至 **[資源]**，然後選取 **[公用網站]**。</span><span class="sxs-lookup"><span data-stu-id="be90e-163">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="be90e-164">選取其中一個選項下方的 **[深入了解]**，然後註冊網站合作夥伴，使用他們的工具來設立和設計您的網站。</span><span class="sxs-lookup"><span data-stu-id="be90e-164">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

## <a name="watch-create-your-business-website"></a><span data-ttu-id="be90e-165">觀看：建立您的商務網站</span><span class="sxs-lookup"><span data-stu-id="be90e-165">Watch: Create your business website</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a><span data-ttu-id="be90e-166">相關內容</span><span class="sxs-lookup"><span data-stu-id="be90e-166">Related content</span></span>

<span data-ttu-id="be90e-167">[建立網站](../../business-video/create-web-site.md) (影片)</span><span class="sxs-lookup"><span data-stu-id="be90e-167">[Create a website](../../business-video/create-web-site.md) (video)\</span></span>
<span data-ttu-id="be90e-168">[商務用 Microsoft 365](../../business-video/index.yml) (連結頁面)</span><span class="sxs-lookup"><span data-stu-id="be90e-168">[Microsoft 365 for your business](../../business-video/index.yml) (link page)</span></span>
