---
title: 設定 Microsoft 365 商務基本版
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
description: 瞭解如何設定 Microsoft 365 商務基本版訂閱。
ms.openlocfilehash: f7569645753f292760f32ba932aac7b83c602b72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393820"
---
# <a name="set-up-microsoft-365-business-basic"></a><span data-ttu-id="88d4c-103">設定 Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="88d4c-103">Set up Microsoft 365 Business Basic</span></span>

## <a name="watch-set-up-microsoft-365-business-basic"></a><span data-ttu-id="88d4c-104">觀看：設定 Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="88d4c-104">Watch: Set up Microsoft 365 Business Basic</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

<span data-ttu-id="88d4c-105">如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](../../business-video/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="88d4c-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="88d4c-106">新增您的網域以個人化登入</span><span class="sxs-lookup"><span data-stu-id="88d4c-106">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="88d4c-107">當您購買 Microsoft 365 商務基本版時，您可以選擇使用自己的網域，或在註冊時購買一個網域。</span><span class="sxs-lookup"><span data-stu-id="88d4c-107">When you purchase Microsoft 365 Business Basic, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="88d4c-108">如果您在註冊時購買新的網域，則您的網域全都都已設定完畢，您可以移至 [新增使用者並指派授權](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="88d4c-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

 ::: moniker range="o365-worldwide"

1. <span data-ttu-id="88d4c-109">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="88d4c-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="88d4c-110">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="88d4c-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="88d4c-111">移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="88d4c-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="88d4c-112">請選擇 **[移至設定]** 來啟動精靈。</span><span class="sxs-lookup"><span data-stu-id="88d4c-112">Choose **Go to setup** to start the wizard.</span></span>
    
3. <span data-ttu-id="88d4c-113">在 **[新增網域]** 步驟中，輸入您要使用的網域名城（例如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="88d4c-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="88d4c-p101">如果您在註冊時購買了網域，就不會在此看到 **[新增網域]** 步驟。請改為前往 [[新增使用者]](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="88d4c-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="88d4c-116">按照精靈中的步驟操作，在任何可驗證您擁有網域的[ 適用於 Office 365 的 DNS 主機服務供應商中建立 DNS 記錄](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。</span><span class="sxs-lookup"><span data-stu-id="88d4c-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="88d4c-117">如果您知道您的網域主機，請參閱[新增網域至 Microsoft 365](/microsoft-365/admin/setup/add-domain)。</span><span class="sxs-lookup"><span data-stu-id="88d4c-117">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="88d4c-118">如果您的主機服務供應商是 GoDaddy 或透過 [[網域連結]](/office365/admin/get-help-with-domains/domain-connect) 所啟用的另一個主機，這個過程便會很簡單，您自動便會被要求登入，並讓 Microsoft 替您進行驗證。</span><span class="sxs-lookup"><span data-stu-id="88d4c-118">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![在 GoDaddy 確認存取頁面上，選取 [授權]。](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="88d4c-120">新增使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="88d4c-120">Add users and assign licenses</span></span>

<span data-ttu-id="88d4c-121">您可以在精靈中新增使用者，或稍後在系統管理中心[[新增使用者]](../add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="88d4c-121">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="88d4c-122">此外，如果您有本機網域控制站，您可以使用 [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express)新增使用者。</span><span class="sxs-lookup"><span data-stu-id="88d4c-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="88d4c-123">在精靈中新增使用者</span><span class="sxs-lookup"><span data-stu-id="88d4c-123">Add users in the wizard</span></span>

<span data-ttu-id="88d4c-124">您在精靈中所新增的任何使用者，都會自動指派 Microsoft 365 商務基本版授權。</span><span class="sxs-lookup"><span data-stu-id="88d4c-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Basic license.</span></span>

1. <span data-ttu-id="88d4c-p104">如果您的 Microsoft 365 商務基本版訂閱有現有的使用者 (例如，如果您使用 Azure AD Connect)，系統會提供立即將授權指派給他們的選項。請繼續進行，並為他們新增授權。</span><span class="sxs-lookup"><span data-stu-id="88d4c-p104">If your Microsoft 365 Business Basic subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="88d4c-p105">新增使用者之後，系統也會提供與您新增之使用者共用認證的選項。您可以選擇列印認證、透過電子郵件傳送認證，或是下載認證。</span><span class="sxs-lookup"><span data-stu-id="88d4c-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="88d4c-129">連接您的網域</span><span class="sxs-lookup"><span data-stu-id="88d4c-129">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="88d4c-130">如果您選擇使用 onmicrosoft 網域，或使用 Azure AD Connect 來設定使用者，您將不會看到此步驟。</span><span class="sxs-lookup"><span data-stu-id="88d4c-130">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="88d4c-131">若要設定服務，您必須更新 DNS 主機或網域註冊機構中的某些記錄。</span><span class="sxs-lookup"><span data-stu-id="88d4c-131">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="88d4c-132">設定精靈通常會偵測您的註冊機構，並提供您一個逐步指示連結，讓您更新在註冊機構網站上的 NS 記錄。</span><span class="sxs-lookup"><span data-stu-id="88d4c-132">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="88d4c-133">如果沒有，請[變更名稱伺服器，以透過任何網域註冊機構來設定 Office 365](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="88d4c-133">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="88d4c-134">如果您有現有的 DNS 記錄，例如現有網站，但您的 DNS 主機已啟用 [網域連線](/office365/admin/get-help-with-domains/domain-connect)，請選擇 **[為我新增記錄]**。</span><span class="sxs-lookup"><span data-stu-id="88d4c-134">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="88d4c-135">在 **[選擇您的線上服務]** 頁面，接受所有預設值，並選擇 **[下一步]**，然後在您的 DNS 主機頁面上選擇 **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="88d4c-135">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="88d4c-p108">如果您的現有 DNS 記錄中有其他 DNS 主機(該主機無法用於網域連線)，您最好能自己管理自己的 DNS 記錄，以確保現有服務保持連線。如需詳情，請查看[網域基本資料](/office365/admin/get-help-with-domains/dns-basics)。</span><span class="sxs-lookup"><span data-stu-id="88d4c-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="88d4c-138">按照精靈中的步驟進行，系統會為您設定電子郵件及其他服務。</span><span class="sxs-lookup"><span data-stu-id="88d4c-138">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="88d4c-139">註冊程序完成後，系統會將您導向系統管理中心，您可以在該處新增使用者，以及指派授權。</span><span class="sxs-lookup"><span data-stu-id="88d4c-139">When the signup process is complete, you'll be directed to the admin center, where you can add users, and assign licenses.</span></span> <span data-ttu-id="88d4c-140">完成初始安裝後，您可以使用系統管理中心的 [設定] 頁面繼續設定和設定訂閱隨附的服務。</span><span class="sxs-lookup"><span data-stu-id="88d4c-140">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="88d4c-141">如需有關安裝精靈和系統管理中心 [設定] 頁面的詳細資訊，請參閱[安裝精靈和設定頁面之間的差異](o365-setup-wizard-and-setup-page.md)。</span><span class="sxs-lookup"><span data-stu-id="88d4c-141">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>