---
title: 設定 Microsoft 365 商務基本版
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
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
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: 瞭解如何設定 Microsoft 365 商務基本版訂閱。
ms.openlocfilehash: 9b448db2a6b8c78bb5265b1e80a01e93c9a6c6ca
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778898"
---
# <a name="set-up-microsoft-365-business-basic"></a><span data-ttu-id="008a8-103">設定 Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="008a8-103">Set up Microsoft 365 Business Basic</span></span>

 <span data-ttu-id="008a8-104">觀看有關設定 Microsoft 365 商務基本版的短片。</span><span class="sxs-lookup"><span data-stu-id="008a8-104">Watch a short video about setting up Microsoft 365 Business Basic.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

<span data-ttu-id="008a8-105">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="008a8-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="008a8-106">新增您的網域以個人化登入</span><span class="sxs-lookup"><span data-stu-id="008a8-106">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="008a8-107">當您購買 Microsoft 365 商務基本版時，您可以選擇使用自己的網域，或在註冊時購買一個網域。</span><span class="sxs-lookup"><span data-stu-id="008a8-107">When you purchase Microsoft 365 Business Basic, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="008a8-108">如果您在註冊時購買新的網域，則您的網域全都都已設定完畢，您可以移至 [新增使用者並指派授權](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="008a8-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

 ::: moniker range="o365-worldwide"

1. <span data-ttu-id="008a8-109">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="008a8-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="008a8-110">如果您使用的是 Office 365 Germany，請移至[此系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=848041)。</span><span class="sxs-lookup"><span data-stu-id="008a8-110">If you're using Office 365 Germany, go to [this admin center](https://go.microsoft.com/fwlink/p/?linkid=848041).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="008a8-111">如果您使用的是由 21Vianet 運作的 Office 365，請移至[此系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=850627)。</span><span class="sxs-lookup"><span data-stu-id="008a8-111">If you're using Office 365 operated by 21Vianet, go to [this admin center.](https://go.microsoft.com/fwlink/p/?linkid=850627).</span></span>

::: moniker-end 

2. <span data-ttu-id="008a8-112">請選擇 **[移至設定]** 來啟動精靈。</span><span class="sxs-lookup"><span data-stu-id="008a8-112">Choose **Go to setup** to start the wizard.</span></span>
    
3. <span data-ttu-id="008a8-113">在 **[新增網域]** 步驟中，輸入您要使用的網域名城（例如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="008a8-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="008a8-114">如果您在註冊時購買了網域，就不會在此看到 **[新增網域]** 步驟。</span><span class="sxs-lookup"><span data-stu-id="008a8-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="008a8-115">改移至 [[新增使用者]](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="008a8-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="008a8-116">按照精靈中的步驟操作，在任何可驗證您擁有網域的[ 適用於 Office 365 的 DNS 主機服務供應商中建立 DNS 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。</span><span class="sxs-lookup"><span data-stu-id="008a8-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="008a8-117">如果您知道您的網域主機，請參閱 [[主機特定指示]](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。</span><span class="sxs-lookup"><span data-stu-id="008a8-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="008a8-118">如果您的主機服務供應商是 GoDaddy 或透過 [[網域連結]](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) 所啟用的另一個主機，這個過程便會很簡單，您自動便會被要求登入，並讓 Microsoft 替您進行驗證。</span><span class="sxs-lookup"><span data-stu-id="008a8-118">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![在 GoDaddy 確認存取頁面上，選取 [授權]。](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="008a8-120">新增使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="008a8-120">Add users and assign licenses</span></span>

<span data-ttu-id="008a8-121">您可以在精靈中新增使用者，或稍後在系統管理中心[[新增使用者]](../add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="008a8-121">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="008a8-122">此外，如果您有本機網域控制站，您可以使用 [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)新增使用者。</span><span class="sxs-lookup"><span data-stu-id="008a8-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="008a8-123">在精靈中新增使用者</span><span class="sxs-lookup"><span data-stu-id="008a8-123">Add users in the wizard</span></span>

<span data-ttu-id="008a8-124">您在精靈中所新增的任何使用者，都會自動指派 Microsoft 365 商務基本版授權。</span><span class="sxs-lookup"><span data-stu-id="008a8-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Basic license.</span></span>

1. <span data-ttu-id="008a8-125">如果您的 Microsoft 365 商務基本版訂閱有現有的使用者 (例如，如果您使用 Azure AD Connect 的話)，系統會提供立即將授權指派給他們的選項。</span><span class="sxs-lookup"><span data-stu-id="008a8-125">If your Microsoft 365 Business Basic subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="008a8-126">請繼續進行，為他們新增授權。</span><span class="sxs-lookup"><span data-stu-id="008a8-126">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="008a8-127">新增使用者之後，您也會看到與您新增之使用者共用認證的選項。</span><span class="sxs-lookup"><span data-stu-id="008a8-127">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="008a8-128">您可以選擇列印認證、透過電子郵件傳送認證，或是下載認證。</span><span class="sxs-lookup"><span data-stu-id="008a8-128">You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="008a8-129">連接您的網域</span><span class="sxs-lookup"><span data-stu-id="008a8-129">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="008a8-130">如果您選擇使用 onmicrosoft 網域，或使用 Azure AD Connect 來設定使用者，您將不會看到此步驟。</span><span class="sxs-lookup"><span data-stu-id="008a8-130">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="008a8-131">若要設定服務，您必須更新 DNS 主機或網域註冊機構中的某些記錄。</span><span class="sxs-lookup"><span data-stu-id="008a8-131">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="008a8-132">設定精靈通常會偵測您的註冊機構，並提供您一個逐步指示連結，讓您更新在註冊機構網站上的 NS 記錄。</span><span class="sxs-lookup"><span data-stu-id="008a8-132">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="008a8-133">如果沒有，請[變更名稱伺服器，以透過任何網域註冊機構來設定 Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)。</span><span class="sxs-lookup"><span data-stu-id="008a8-133">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="008a8-134">如果您有現有的 DNS 記錄，例如現有網站，但您的 DNS 主機已啟用 [網域連線](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)，請選擇 **[為我新增記錄]**。</span><span class="sxs-lookup"><span data-stu-id="008a8-134">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="008a8-135">在 **[選擇您的線上服務]** 頁面，接受所有預設值，並選擇 **[下一步]**，然後在您的 DNS 主機頁面上選擇 **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="008a8-135">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="008a8-136">如果您的現有 DNS 記錄中有其他 DNS 主機(該主機無法用於網域連線)，您最好能自己管理自己的 DNS 記錄，以確保現有服務保持連線。</span><span class="sxs-lookup"><span data-stu-id="008a8-136">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="008a8-137">如需詳細資訊，請參閱 [網域基本資訊](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)。</span><span class="sxs-lookup"><span data-stu-id="008a8-137">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="008a8-138">按照精靈中的步驟進行，系統會為您設定電子郵件及其他服務。</span><span class="sxs-lookup"><span data-stu-id="008a8-138">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="008a8-139">註冊程序完成後，系統會將您導向系統管理中心，您可以在該處新增使用者，以及指派授權。</span><span class="sxs-lookup"><span data-stu-id="008a8-139">When the signup process is complete, you'll be directed to the admin center, where you can add users, and assign licenses.</span></span> <span data-ttu-id="008a8-140">完成初始安裝後，您可以使用系統管理中心的 [設定] \*\*\*\* 頁面繼續設定和設定訂閱隨附的服務。</span><span class="sxs-lookup"><span data-stu-id="008a8-140">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="008a8-141">如需有關安裝精靈和系統管理中心 [設定]\*\*\*\* 頁面的詳細資訊，請參閱[安裝精靈和設定頁面之間的差異](o365-setup-wizard-and-setup-page.md)。</span><span class="sxs-lookup"><span data-stu-id="008a8-141">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>