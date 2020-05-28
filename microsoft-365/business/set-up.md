---
title: 設定 Microsoft 365 商務進階版
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 探索 Microsoft 365 商務版 Premium 的設定步驟，包括新增網域和使用者、設定安全性原則等等。
ms.openlocfilehash: 6606e9fd66aacab317e4b0bfd5ce2a090208018e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402939"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="9502c-103">在安裝精靈中設定 Microsoft 365 商務版 Premium</span><span class="sxs-lookup"><span data-stu-id="9502c-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="9502c-104">請觀看這段影片，以取得 Microsoft 365 商務版特優設定的概要。</span><span class="sxs-lookup"><span data-stu-id="9502c-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="9502c-105">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="9502c-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="9502c-106">新增您的網域、使用者及設定原則</span><span class="sxs-lookup"><span data-stu-id="9502c-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="9502c-107">[![[標籤] 可讓您知道系統管理中心正在變更，您可以在 aka.ms/aboutM365preview 取得更多詳細資料。](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="9502c-107">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="9502c-108">當您購買 Microsoft 365 商務版特優功能時，您可以選擇使用您擁有的網域，或在[註冊](sign-up.md)期間購買一個網域。</span><span class="sxs-lookup"><span data-stu-id="9502c-108">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="9502c-109">如果您在註冊時購買了新的網域，您的網域就是全部設定，您可以移至 [新增[使用者] 和 [指派授權](#add-users-and-assign-licenses)]。</span><span class="sxs-lookup"><span data-stu-id="9502c-109">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="9502c-110">將您的網域新增至個人化登入</span><span class="sxs-lookup"><span data-stu-id="9502c-110">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="9502c-111">使用您的全域系統管理員認證登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="9502c-111">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="9502c-112">選擇 [**移至設定**] 以啟動嚮導。</span><span class="sxs-lookup"><span data-stu-id="9502c-112">Choose **Go to setup** to start the wizard.</span></span>

    ![選取 [移至設定]。](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="9502c-114">在 [**安裝您的 Office 應用程式**] 頁面上，您可以選擇性地在您自己的電腦上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="9502c-114">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="9502c-115">在 [**新增網域**] 步驟中，輸入您要使用的功能變數名稱（例如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="9502c-115">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9502c-116">如果您是在註冊時購買網域，您將不會在這裡看到 [**新增網域**] 步驟。</span><span class="sxs-lookup"><span data-stu-id="9502c-116">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="9502c-117">請改改為 [[新增使用者](#add-users-and-assign-licenses)]。</span><span class="sxs-lookup"><span data-stu-id="9502c-117">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![個人化登入頁面的螢幕擷取畫面。](../media/adddomain.png)

    
4. <span data-ttu-id="9502c-119">依照嚮導中的步驟，在任何可驗證您擁有網域之[Office 365 的 dns 主機服務提供者處建立 dns 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。</span><span class="sxs-lookup"><span data-stu-id="9502c-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="9502c-120">如果您知道網域主機，請參閱[主機特定指示](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。</span><span class="sxs-lookup"><span data-stu-id="9502c-120">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="9502c-121">如果您的主機服務提供者是 GoDaddy 或另一個以[網域](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)連線方式啟用的主機，程式就很容易，而且您將會自動要求您登入，並讓 Microsoft 代表您進行驗證。</span><span class="sxs-lookup"><span data-stu-id="9502c-121">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![在 GoDaddy 確認存取] 頁面上，選取 [授權]。](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="9502c-123">新增使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="9502c-123">Add users and assign licenses</span></span>

<span data-ttu-id="9502c-124">您可以在嚮導中新增使用者，但您也可以稍後在系統管理中心[新增使用者](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="9502c-124">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="9502c-125">此外，如果您有本機的網域控制站，您可以使用[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)新增使用者。</span><span class="sxs-lookup"><span data-stu-id="9502c-125">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="9502c-126">在嚮導中新增使用者</span><span class="sxs-lookup"><span data-stu-id="9502c-126">Add users in the wizard</span></span>

<span data-ttu-id="9502c-127">您在嚮導中新增的任何使用者會自動指派 Microsoft 365 商務版優質授權。</span><span class="sxs-lookup"><span data-stu-id="9502c-127">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![嚮導中 [新增使用者] 頁面的螢幕擷取畫面](../media/addnewuserspage.png)

1. <span data-ttu-id="9502c-129">如果您的 Microsoft 365 商務版訂閱有現有的使用者（例如，如果您使用 Azure AD Connect），您可以選擇立即將授權指派給他們。</span><span class="sxs-lookup"><span data-stu-id="9502c-129">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="9502c-130">請繼續進行，為他們新增授權。</span><span class="sxs-lookup"><span data-stu-id="9502c-130">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="9502c-131">在您新增使用者之後，您也會看到一個選項，用來與您新增的新使用者共用認證。</span><span class="sxs-lookup"><span data-stu-id="9502c-131">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="9502c-132">您可以選擇列印認證、透過電子郵件傳送認證，或是下載認證。</span><span class="sxs-lookup"><span data-stu-id="9502c-132">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="9502c-133">連接您的網域</span><span class="sxs-lookup"><span data-stu-id="9502c-133">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="9502c-134">如果您選擇使用 name.onmicrosoft.com17 網域，或使用 Azure AD Connect 來設定使用者，您就不會看到此步驟。</span><span class="sxs-lookup"><span data-stu-id="9502c-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="9502c-135">若要設定服務，您必須更新 DNS 主機或網域註冊機構中的某些記錄。</span><span class="sxs-lookup"><span data-stu-id="9502c-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="9502c-136">設定精靈通常會偵測您的註冊機構，並提供您一個逐步指示連結，讓您更新在註冊機構網站上的 NS 記錄。</span><span class="sxs-lookup"><span data-stu-id="9502c-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="9502c-137">如果不是，請[變更名稱伺服器以設定 Office 365 與任何網域註冊](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)機構。</span><span class="sxs-lookup"><span data-stu-id="9502c-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="9502c-138">如果您有現有的 DNS 記錄（例如現有的網站），但您的 DNS 主機已啟用[網域](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)連線，請選擇 [**新增我的記錄**]。</span><span class="sxs-lookup"><span data-stu-id="9502c-138">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="9502c-139">在 [**選擇您的線上服務**] 頁面上，接受所有預設值，然後選擇 [**下一步]**，然後在您的 DNS 主機頁面上選擇 [**授權**]。</span><span class="sxs-lookup"><span data-stu-id="9502c-139">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="9502c-140">如果您有現有的 DNS 記錄與其他 DNS 主機（未啟用網域連線），您會想要管理自己的 DNS 記錄，以確保現有的服務保持連線。</span><span class="sxs-lookup"><span data-stu-id="9502c-140">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="9502c-141">如需詳細資訊，請參閱[網域基礎知識](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)。</span><span class="sxs-lookup"><span data-stu-id="9502c-141">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![開機記錄頁面。](../media/activaterecords.png)

2. <span data-ttu-id="9502c-143">依照嚮導中的步驟進行，然後會為您設定電子郵件和其他服務。</span><span class="sxs-lookup"><span data-stu-id="9502c-143">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="9502c-144">保護您的組織</span><span class="sxs-lookup"><span data-stu-id="9502c-144">Protect your organization</span></span> 

<span data-ttu-id="9502c-145">您在嚮導中設定的原則會自動套用至稱為「*所有使用者*」的[安全性群組](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)。</span><span class="sxs-lookup"><span data-stu-id="9502c-145">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="9502c-146">您也可以在系統管理中心建立其他群組，以指派原則。</span><span class="sxs-lookup"><span data-stu-id="9502c-146">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="9502c-147">在 [**加強來自高級網路威脅的保護**] 中，建議您接受預設值，讓[Office 365 的高級威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)掃描 office 應用程式中的檔案和連結。</span><span class="sxs-lookup"><span data-stu-id="9502c-147">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![[增加保護] 頁面的螢幕擷取畫面。](../media/increasetreatprotection.png)


2. <span data-ttu-id="9502c-149">在 [**防止敏感性資料洩漏**] 頁面上，接受預設值以開啟 Office 365 資料遺失防護（DLP）以追蹤 office 應用程式中的機密資料，並防止在組織外意外共用這些資料。</span><span class="sxs-lookup"><span data-stu-id="9502c-149">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="9502c-150">在 [**保護**行動裝置中的資料] 頁面上，將行動應用程式管理留給 [開啟]，展開設定並加以檢查，然後選取 [建立行動裝置**應用程式管理原則**]。</span><span class="sxs-lookup"><span data-stu-id="9502c-150">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![在 [行動裝置] 頁面中保護資料的螢幕擷取畫面。](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="9502c-152">保護 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="9502c-152">Secure Windows 10 PCs</span></span>

<span data-ttu-id="9502c-153">在左導覽上，選取 [**安裝**]，然後在 [登**入和安全性**] 下，選擇 [**保護您的 Windows 10 電腦**]。</span><span class="sxs-lookup"><span data-stu-id="9502c-153">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="9502c-154">選擇 [View] （**查看**）立即開始。</span><span class="sxs-lookup"><span data-stu-id="9502c-154">Choose **View** to get started.</span></span> <span data-ttu-id="9502c-155">請參閱[保護您的 Windows 10 電腦](secure-win-10-pcs.md)以取得完整的指示。</span><span class="sxs-lookup"><span data-stu-id="9502c-155">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="9502c-156">部署 Office 365 用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="9502c-156">Deploy Office 365 client apps</span></span>

<span data-ttu-id="9502c-157">如果您選擇在設定期間自動安裝 Office 應用程式，當使用者從 Windows 裝置登入 Azure AD 時，將會在 Windows 10 裝置上安裝應用程式，並使用其工作認證。</span><span class="sxs-lookup"><span data-stu-id="9502c-157">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="9502c-158">若要在行動裝置 iOS 或 Android 裝置上安裝 Office，請參閱為[Microsoft 365 商務版使用者設定行動裝置](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="9502c-158">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="9502c-159">您也可以個別安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="9502c-159">You can also install Office individually.</span></span> <span data-ttu-id="9502c-160">請參閱[在 PC 或 Mac 上安裝 Office](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)以取得指示。</span><span class="sxs-lookup"><span data-stu-id="9502c-160">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="9502c-161">請參閱</span><span class="sxs-lookup"><span data-stu-id="9502c-161">See also</span></span>

[<span data-ttu-id="9502c-162">商務用 Microsoft 365 訓練影片</span><span class="sxs-lookup"><span data-stu-id="9502c-162">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
