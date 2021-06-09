---
title: 設定 Microsoft 365 商務進階版
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 探索 Microsoft 365 商務進階版的設定步驟，包括新增網域和使用者、設定安全性原則等等。
ms.openlocfilehash: 3e15f16db2a233d2e11d444600398102b075932d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624382"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="50352-103">在安裝程式嚮導中設定 Microsoft 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="50352-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

## <a name="watch-overview-of-microsoft-365-setup"></a><span data-ttu-id="50352-104">觀賞： Microsoft 365 安裝程式的概覽</span><span class="sxs-lookup"><span data-stu-id="50352-104">Watch: Overview of Microsoft 365 setup</span></span>

<span data-ttu-id="50352-105">觀看這段影片，瞭解 Microsoft 365 商務進階版安裝程式的概況。</span><span class="sxs-lookup"><span data-stu-id="50352-105">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="50352-106">新增您的網域、使用者及設定原則</span><span class="sxs-lookup"><span data-stu-id="50352-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="50352-107">當您購買 Microsoft 365 商務進階版時，您可以選擇在[註冊](sign-up.md)時使用您擁有的網域，或是購買一個網域。</span><span class="sxs-lookup"><span data-stu-id="50352-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="50352-108">如果您在註冊時購買新的網域，則您的網域全都都已設定完畢，您可以移至 [新增使用者並指派授權](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="50352-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="50352-109">新增您的網域以個人化登入</span><span class="sxs-lookup"><span data-stu-id="50352-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="50352-110">使用您的全域系統管理員認證登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="50352-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="50352-111">請選擇 **[移至設定]** 來啟動精靈。</span><span class="sxs-lookup"><span data-stu-id="50352-111">Choose **Go to setup** to start the wizard.</span></span>

    ![選取 [移至設定]。](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="50352-113">在 **[安裝您的 Office 應用程式]** 頁面上，您可以選擇將應用程式安裝到自己的電腦上。</span><span class="sxs-lookup"><span data-stu-id="50352-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="50352-114">在 **[新增網域]** 步驟中，輸入您要使用的網域名城（例如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="50352-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="50352-p101">如果您在註冊時購買了網域，就不會在此看到 **[新增網域]** 步驟。請改為前往 [[新增使用者]](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="50352-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![個人化登入頁面的螢幕擷取畫面。](../media/adddomain.png)

    
4. <span data-ttu-id="50352-118">依照嚮導中的步驟，[在任何 dns 主機服務提供者上建立 dns 記錄](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)，以驗證您擁有該網域的 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="50352-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="50352-119">如果您知道您的網域主機，請參閱 [[主機特定指示]](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。</span><span class="sxs-lookup"><span data-stu-id="50352-119">If you know your domain host, see also the [host specific instructions](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="50352-120">如果您的主機服務供應商是 GoDaddy 或透過 [[網域連結]](/office365/admin/get-help-with-domains/domain-connect) 所啟用的另一個主機，這個過程便會很簡單，您自動便會被要求登入，並讓 Microsoft 替您進行驗證。</span><span class="sxs-lookup"><span data-stu-id="50352-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![在 GoDaddy 確認存取頁面上，選取 [授權]。](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="50352-122">新增使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="50352-122">Add users and assign licenses</span></span>

<span data-ttu-id="50352-123">您可以在精靈中新增使用者，或稍後在系統管理中心[[新增使用者]](../admin/add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="50352-123">You can add users in the wizard, but you can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="50352-124">此外，如果您有本機網域控制站，您可以使用 [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express)新增使用者。</span><span class="sxs-lookup"><span data-stu-id="50352-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="50352-125">在精靈中新增使用者</span><span class="sxs-lookup"><span data-stu-id="50352-125">Add users in the wizard</span></span>

<span data-ttu-id="50352-126">您在嚮導中新增的任何使用者會自動指派 Microsoft 365 商務進階版授權。</span><span class="sxs-lookup"><span data-stu-id="50352-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![嚮導中 [新增使用者] 頁面的螢幕擷取畫面](../media/addnewuserspage.png)

1. <span data-ttu-id="50352-128">例如，如果您的 Microsoft 365 商務進階版訂閱具有現有使用者 (例如，如果您使用 Azure AD 連線) ，您會看到立即指派授權的選項。</span><span class="sxs-lookup"><span data-stu-id="50352-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="50352-129">請繼續進行，為他們新增授權。</span><span class="sxs-lookup"><span data-stu-id="50352-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="50352-p105">新增使用者之後，系統也會提供與您新增之使用者共用認證的選項。您可以選擇列印認證、透過電子郵件傳送認證，或是下載認證。</span><span class="sxs-lookup"><span data-stu-id="50352-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="50352-132">連接您的網域</span><span class="sxs-lookup"><span data-stu-id="50352-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="50352-133">如果您選擇使用 onmicrosoft 網域，或使用 Azure AD Connect 來設定使用者，您將不會看到此步驟。</span><span class="sxs-lookup"><span data-stu-id="50352-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="50352-134">若要設定服務，您必須更新 DNS 主機或網域註冊機構中的某些記錄。</span><span class="sxs-lookup"><span data-stu-id="50352-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="50352-135">設定精靈通常會偵測您的註冊機構，並提供您一個逐步指示連結，讓您更新在註冊機構網站上的 NS 記錄。</span><span class="sxs-lookup"><span data-stu-id="50352-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="50352-136">如果不是，請[將名稱伺服器變更為設定任何網域註冊機構的 Microsoft 365](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="50352-136">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="50352-137">如果您有現有的 DNS 記錄，例如現有網站，但您的 DNS 主機已啟用 [網域連線](/office365/admin/get-help-with-domains/domain-connect)，請選擇 **[為我新增記錄]**。</span><span class="sxs-lookup"><span data-stu-id="50352-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="50352-138">在 **[選擇您的線上服務]** 頁面，接受所有預設值，並選擇 **[下一步]**，然後在您的 DNS 主機頁面上選擇 **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="50352-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="50352-p108">如果您的現有 DNS 記錄中有其他 DNS 主機(該主機無法用於網域連線)，您最好能自己管理自己的 DNS 記錄，以確保現有服務保持連線。如需詳情，請查看[網域基本資料](/office365/admin/get-help-with-domains/dns-basics)。</span><span class="sxs-lookup"><span data-stu-id="50352-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![開機記錄頁面。](../media/activaterecords.png)

2. <span data-ttu-id="50352-142">按照精靈中的步驟進行，系統會為您設定電子郵件及其他服務。</span><span class="sxs-lookup"><span data-stu-id="50352-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="50352-143">保護您的組織</span><span class="sxs-lookup"><span data-stu-id="50352-143">Protect your organization</span></span> 

<span data-ttu-id="50352-144">您在嚮導中設定的原則會自動套用至稱為「*所有使用者*」的 [安全性群組](/office365/admin/create-groups/compare-groups#security-groups)。</span><span class="sxs-lookup"><span data-stu-id="50352-144">The policies you set up in the wizard are applied automatically to a [Security group](/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="50352-145">您也可以在系統管理中心建立其他群組，以指派原則。</span><span class="sxs-lookup"><span data-stu-id="50352-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="50352-146">在 [**加強來自高級網路威脅的保護**] 中，建議您接受預設值，讓 [Office 365 高級威脅防護](../security/office-365-security/defender-for-office-365.md)掃描 Office 應用程式中的檔案和連結。</span><span class="sxs-lookup"><span data-stu-id="50352-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) scan files and links in Office apps.</span></span>

    ![[增加保護] 頁面的螢幕擷取畫面。](../media/increasetreatprotection.png)


2. <span data-ttu-id="50352-148">在 [**防止敏感性資料洩漏**] 頁面上，接受預設值以開啟 Office 365 資料遺失防護 (DLP) 追蹤 Office 應用程式中的機密資料，並防止在組織外意外共用這些資料。</span><span class="sxs-lookup"><span data-stu-id="50352-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="50352-149">在 [**保護行動裝置 Office 中的資料**] 頁面上，將行動應用程式管理保留在上，展開設定並加以查看，然後選取 [建立行動裝置 **應用程式管理原則**]。</span><span class="sxs-lookup"><span data-stu-id="50352-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![在行動頁面 Office 中保護資料的螢幕擷取畫面。](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="50352-151">保護 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="50352-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="50352-152">在左導覽上，選取 [**安裝**]，然後在 [登 **入和安全性**] 下，選擇 [**保護您的 Windows 10 電腦**。</span><span class="sxs-lookup"><span data-stu-id="50352-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="50352-153">選擇 [View] （ **查看** ）立即開始。</span><span class="sxs-lookup"><span data-stu-id="50352-153">Choose **View** to get started.</span></span> <span data-ttu-id="50352-154">如需完整的指示，請參閱[保護您的 Windows 10 電腦](secure-win-10-pcs.md)。</span><span class="sxs-lookup"><span data-stu-id="50352-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="50352-155">部署 Office 365 用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="50352-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="50352-156">如果您選擇在安裝期間自動安裝 Office 應用程式，當使用者從其 Windows 裝置登入 Azure AD 時，將會在 Windows 10 裝置上安裝應用程式，並使用其工作認證。</span><span class="sxs-lookup"><span data-stu-id="50352-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="50352-157">若要在行動裝置 iOS 或 Android 裝置上安裝 Office，請參閱為[Microsoft 365 商務進階版使用者設定行動裝置](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="50352-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="50352-158">您也可以個別安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="50352-158">You can also install Office individually.</span></span> <span data-ttu-id="50352-159">請參閱[在 PC 或 Mac 上安裝 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="50352-159">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="related-content"></a><span data-ttu-id="50352-160">相關內容</span><span class="sxs-lookup"><span data-stu-id="50352-160">Related content</span></span>

<span data-ttu-id="50352-161">[Microsoft 365 商務訓練](../business-video/index.yml)影片 (連結] 頁面) </span><span class="sxs-lookup"><span data-stu-id="50352-161">[Microsoft 365 for business training videos](../business-video/index.yml) (link page)</span></span>
