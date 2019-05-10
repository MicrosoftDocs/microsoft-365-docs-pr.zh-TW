---
title: 設定 Microsoft 365 商務版
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
description: 了解如何設定 Microsoft 365 商務版。
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660732"
---
# <a name="set-up-microsoft-365-business"></a><span data-ttu-id="9184d-103">設定 Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="9184d-103">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="9184d-104">在您開始之前，請參閱[取得 Microsoft 365 商務版](get-microsoft-365-business.md)，如註冊的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9184d-104">Before you get started, see [Get Microsoft 365 Business](get-microsoft-365-business.md) for sign-up details.</span></span>

<span data-ttu-id="9184d-105">使用設定精靈] 中，並時您沒有內部部署 Active Directory 觀賞[簡短的影片，如何設定 Microsoft 365 商務版](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1)</span><span class="sxs-lookup"><span data-stu-id="9184d-105">Watch a [short video on how to set up Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) by using the set up wizard, and when you don't have an on-premises Active Directory</span></span>
  

## <a name="overview"></a><span data-ttu-id="9184d-106">概觀</span><span class="sxs-lookup"><span data-stu-id="9184d-106">Overview</span></span>

<span data-ttu-id="9184d-107">可以在安裝程式精靈] 完成大部分的設定步驟，但也會列出其他選項。</span><span class="sxs-lookup"><span data-stu-id="9184d-107">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>

1. <span data-ttu-id="9184d-108">[新增您的網域](#add-your-domain-to-personalize-sign-in)（如果您在[註冊](sign-up.md)購買您的網域，為已完成這個步驟。）</span><span class="sxs-lookup"><span data-stu-id="9184d-108">[Add your domain](#add-your-domain-to-personalize-sign-in) (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>
2. <span data-ttu-id="9184d-109">新增使用者]。</span><span class="sxs-lookup"><span data-stu-id="9184d-109">Add users.</span></span> <span data-ttu-id="9184d-110">您可以在任何的三種方式：</span><span class="sxs-lookup"><span data-stu-id="9184d-110">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="9184d-111">在[安裝精靈](#add-users-in-the-wizard)]。</span><span class="sxs-lookup"><span data-stu-id="9184d-111">In the [setup wizard](#add-users-in-the-wizard).</span></span>
    - <span data-ttu-id="9184d-112">如果您有內部部署 Active directory，請使用新增[的使用者使用 Azure AD Connect](#add-users-by-using-azure-ad-connect)目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="9184d-112">Use directory synchronization to [add users by using Azure AD Connect](#add-users-by-using-azure-ad-connect) if you have an on-premises Active directory.</span></span>
    - <span data-ttu-id="9184d-113">您也可以在系統管理中心的 [[新增使用者更新版本](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="9184d-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
3. <span data-ttu-id="9184d-114">設定安全性原則和設定裝置。</span><span class="sxs-lookup"><span data-stu-id="9184d-114">Set up security policies and configure devices.</span></span> <span data-ttu-id="9184d-115">您可以在任何的三種方式：</span><span class="sxs-lookup"><span data-stu-id="9184d-115">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="9184d-116">在[安裝精靈](#set-up-policies-in-the-wizard)]。</span><span class="sxs-lookup"><span data-stu-id="9184d-116">In the [setup wizard](#set-up-policies-in-the-wizard).</span></span>  
    - <span data-ttu-id="9184d-117">在[系統管理中心](#modify-or-add-policies-in-the-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="9184d-117">In the [admin center](#modify-or-add-policies-in-the-admin-center).</span></span>
    - <span data-ttu-id="9184d-118">在[Intune 系統管理中心](https://docs.microsoft.com/intune/what-is-device-management)中。</span><span class="sxs-lookup"><span data-stu-id="9184d-118">In the [Intune admin center](https://docs.microsoft.com/intune/what-is-device-management).</span></span>
4. <span data-ttu-id="9184d-119">設定及管理 Windows 10 裝置。</span><span class="sxs-lookup"><span data-stu-id="9184d-119">Set up and manage Windows 10 devices.</span></span>

    <span data-ttu-id="9184d-120">當您在 WIndows 10 裝置加入 Azure AD 時，取得套用所有原則。</span><span class="sxs-lookup"><span data-stu-id="9184d-120">When you join a WIndows 10 device to Azure AD, all the policies get applied to it.</span></span>
    - <span data-ttu-id="9184d-121">設定[安裝程式精靈](#set-up-policies-in-the-wizard)] 中的 Windows 10 裝置設定。</span><span class="sxs-lookup"><span data-stu-id="9184d-121">Set up Windows 10 device configurations in the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="9184d-122">將[新的 Windows 10 裝置](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device)加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="9184d-122">Join a [new Windows 10 device](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) to Azure AD.</span></span>
    - <span data-ttu-id="9184d-123">將[現有的 Windows 10 裝置](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro)加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="9184d-123">Join an [existing Windows 10 device](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) to Azure AD.</span></span>
1. <span data-ttu-id="9184d-124">安裝 Office 365 商務版。</span><span class="sxs-lookup"><span data-stu-id="9184d-124">Install Office 365 Business.</span></span>
    - <span data-ttu-id="9184d-125">您可以使用[安裝精靈](#set-up-policies-in-the-wizard)，在 Windows 裝置上自動安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="9184d-125">You can automatically install Office in the Windows devices by using the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="9184d-126">從自動[安裝 Office](auto-install-or-uninstall-office.md)系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="9184d-126">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
    - <span data-ttu-id="9184d-127">Windows 和裝置，可讓使用者[安裝 Office 應用程式](https://docs.microsoft.com/office365/admin/setup/install-applications)。</span><span class="sxs-lookup"><span data-stu-id="9184d-127">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
1. <span data-ttu-id="9184d-128">設定額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="9184d-128">Set up additional security.</span></span>
    - <span data-ttu-id="9184d-129">安裝精靈會新增原則來保護您的裝置，但您也可以利用的[其他安全性](#additional-security-settings)功能來幫助保護您的資料、 帳戶及電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9184d-129">The setup wizard adds policies to secure your devices, but you can also take advantage of [additional security](#additional-security-settings) capabilities to helps secure your data, accounts, and emails.</span></span> 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="9184d-130">新增您的網域使用者，並設定原則</span><span class="sxs-lookup"><span data-stu-id="9184d-130">Add your domain, users and set up policies</span></span>

![指向橫幅https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

<span data-ttu-id="9184d-132">當您購買 Microsoft 365 商務版時，您可以使用您自己的網域，或購買其中期間選擇[註冊](sign-up.md)。</span><span class="sxs-lookup"><span data-stu-id="9184d-132">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="9184d-133">如果您購買新的網域，當您註冊時，您的網域，且所有設定，而且您可以移到[新增使用者並指派授權](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="9184d-133">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="9184d-134">新增網域至個人化登入</span><span class="sxs-lookup"><span data-stu-id="9184d-134">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="9184d-135">使用全域系統管理員認證登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="9184d-135">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="9184d-136">選擇 [**新增網域**]，以啟動精靈]。</span><span class="sxs-lookup"><span data-stu-id="9184d-136">Choose **Add a domain** to start the wizard.</span></span>

    ![選取 [新增網域。](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="9184d-138">在精靈中，輸入您想要使用 （例如 contoso.com) 的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="9184d-138">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![個人化您的登入頁面的螢幕擷取畫面。](media/personalizesignin.png)

    
4. <span data-ttu-id="9184d-140">若要驗證您擁有該網域的[Office 365 任何 DNS 主機服務提供者處建立 DNS 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)，請遵循精靈中的步驟。</span><span class="sxs-lookup"><span data-stu-id="9184d-140">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="9184d-141">如果您知道您的網域主機，請參閱[主應用程式的特定指示](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。</span><span class="sxs-lookup"><span data-stu-id="9184d-141">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="9184d-142">如果您的主機服務提供者是 GoDaddy，程序簡單，而且您將會自動登入，並讓 Microsoft 代替您驗證要求：</span><span class="sxs-lookup"><span data-stu-id="9184d-142">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![在 GoDaddy 確認存取] 頁面上，選取 [授權]。](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="9184d-144">新增使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="9184d-144">Add users and assign licenses</span></span>

<span data-ttu-id="9184d-145">您可以新增使用者在精靈中，但您也可以在系統管理中心的 [[新增使用者更新版本](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="9184d-145">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="9184d-146">此外，如果您有在本機網域控制站，您可以新增使用者的[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)。</span><span class="sxs-lookup"><span data-stu-id="9184d-146">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="9184d-147">在精靈中新增使用者</span><span class="sxs-lookup"><span data-stu-id="9184d-147">Add users in the wizard</span></span>

<span data-ttu-id="9184d-148">您在精靈中新增的使用者自動取得 Microsoft 365 商務版授權。</span><span class="sxs-lookup"><span data-stu-id="9184d-148">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>
<span data-ttu-id="9184d-149">如果您已在本機網域控制站，並使用 Active Directory，請參閱[how to ddd 使用者藉由使用 Azure AD Connect](#add-users-by-using-azure-ad-connect)。</span><span class="sxs-lookup"><span data-stu-id="9184d-149">If you have a local domain controller, and are using Active Directory, see [how to ddd users by using Azure AD Connect](#add-users-by-using-azure-ad-connect).</span></span>

![在精靈中新增新使用者 」 頁面的螢幕擷取畫面](media/addnewuserspage.png)

1. <span data-ttu-id="9184d-p106">如果您的 Microsoft 365 商務版訂閱有現有的使用者 (例如，如果您使用 Azure AD Connect)，系統會提供立即將授權指派給他們的選項。請繼續進行，為他們新增授權。</span><span class="sxs-lookup"><span data-stu-id="9184d-p106">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="9184d-153">新增使用者之後，您也會取得與您新增新使用者共用認證的選項。</span><span class="sxs-lookup"><span data-stu-id="9184d-153">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="9184d-154">您可以選擇列印認證、透過電子郵件傳送認證，或是下載認證。</span><span class="sxs-lookup"><span data-stu-id="9184d-154">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="9184d-155">略過移轉電子郵件，並在**移轉電子郵件訊息**] 頁面上選擇 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9184d-155">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="9184d-156">如果您要移動從另一個電子郵件提供者，並想稍後複製資料，您可以[移轉電子郵件和連絡人移轉到 Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)。</span><span class="sxs-lookup"><span data-stu-id="9184d-156">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>

#### <a name="add-users-by-using-azure-ad-connect"></a><span data-ttu-id="9184d-157">使用 Azure AD Connect 來新增使用者</span><span class="sxs-lookup"><span data-stu-id="9184d-157">Add users by using Azure AD Connect</span></span>

 <span data-ttu-id="9184d-158">如果您有使用 Active Directory 的本機網域控制站，您同步處理您的使用者與 Microsoft 365 商務版使用[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)。</span><span class="sxs-lookup"><span data-stu-id="9184d-158">If you have a local domain controller with Active Directory, you synchronize your users with Microsoft 365 Business by using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span> <span data-ttu-id="9184d-159">在您開始安裝精靈之前，請完成此選項。</span><span class="sxs-lookup"><span data-stu-id="9184d-159">Complete this before you start the setup wizard.</span></span> <span data-ttu-id="9184d-160">您可以在系統管理中心下載它：</span><span class="sxs-lookup"><span data-stu-id="9184d-160">You can download it in the admin center:</span></span>

- <span data-ttu-id="9184d-161">移至**使用者** \> **作用中使用者**]，選取在頁面頂端的省略符號，然後選取 [下載 Azure AD Connect**目錄同步處理**。</span><span class="sxs-lookup"><span data-stu-id="9184d-161">Go to **Users** \> **Active users**, select the ellipses on the top of the page and then select **Directory synchronization** to download Azure AD Connect.</span></span>

    ![在作用中使用者] 頁面上選取 [省略符號 > 目錄 snchronization。](media/setupdirsync.png)

    > [!IMPORTANT]
    > <span data-ttu-id="9184d-163">如果您建立使用者如此一來，您仍必須在系統管理中心中指派授權給他們。</span><span class="sxs-lookup"><span data-stu-id="9184d-163">If you create users this way, you will still have to assign licenses to them in the admin center.</span></span>

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a><span data-ttu-id="9184d-164">繼續存取已加入網域的應用程式和裝置</span><span class="sxs-lookup"><span data-stu-id="9184d-164">Continue to access domain-joined apps and devices</span></span>

<span data-ttu-id="9184d-165">如果您想要繼續存取已加入網域的應用程式和裝置，請閱讀下列文章針對啟用的兩個不同的方式：</span><span class="sxs-lookup"><span data-stu-id="9184d-165">If you want to continue to access domain-joined apps and devices, read the following articles for two different way of enabling that:</span></span>
  
- [<span data-ttu-id="9184d-166">啟用由 Microsoft 365 商務版來管理已加入網域的 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="9184d-166">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    - <span data-ttu-id="9184d-167">這是建議的方式。</span><span class="sxs-lookup"><span data-stu-id="9184d-167">This is the recommended way.</span></span>

- [<span data-ttu-id="9184d-168">存取內部部署 Microsoft 365 商務版中的 Azure AD 加入裝置的資源</span><span class="sxs-lookup"><span data-stu-id="9184d-168">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)

### <a name="connect-your-domain"></a><span data-ttu-id="9184d-169">連接您的網域</span><span class="sxs-lookup"><span data-stu-id="9184d-169">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="9184d-170">如果您選擇.onmicrosoft 網域，或是用來設定使用者的 Azure AD Connect，您將不會看到此步驟。</span><span class="sxs-lookup"><span data-stu-id="9184d-170">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="9184d-171">若要設定服務，您必須更新 DNS 主機或網域註冊機構中的某些記錄。</span><span class="sxs-lookup"><span data-stu-id="9184d-171">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="9184d-172">設定精靈通常會偵測您的註冊機構，並提供您一個逐步指示連結，讓您更新在註冊機構網站上的 NS 記錄。</span><span class="sxs-lookup"><span data-stu-id="9184d-172">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="9184d-173">如果沒有，[以設定 Office 365 運用任何網域註冊機構變更名稱伺服器](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)。</span><span class="sxs-lookup"><span data-stu-id="9184d-173">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="9184d-174">如果您有現有的 DNS 記錄，例如現有的 iis 網站，您會想要管理 DNS 記錄，以確定現有服務保持聯繫。</span><span class="sxs-lookup"><span data-stu-id="9184d-174">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="9184d-175">如需詳細資訊的[網域基本概念](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="9184d-175">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![連接您的網域] 頁面上與我管理自己的 DNS 記錄。](media/connectyourdomainpage.png)

2. <span data-ttu-id="9184d-177">遵循精靈中的步驟和電子郵件和其他服務就會設定為您。</span><span class="sxs-lookup"><span data-stu-id="9184d-177">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="9184d-178">設定安全性原則和裝置設定</span><span class="sxs-lookup"><span data-stu-id="9184d-178">Set up security policies and device configurations</span></span> 

<span data-ttu-id="9184d-179">這些原則套用到每個使用者提供授權，或一群使用者如果您決定要將不同的原則指派給一群使用者。</span><span class="sxs-lookup"><span data-stu-id="9184d-179">These policies apply to every user you give a license to, or to a group of users if you decide to assign different policies to a set of users.</span></span>

#### <a name="set-up-policies-in-the-wizard"></a><span data-ttu-id="9184d-180">設定精靈] 中的原則</span><span class="sxs-lookup"><span data-stu-id="9184d-180">Set up policies in the wizard</span></span>

<span data-ttu-id="9184d-181">您在精靈中設定的原則會自動套用至名為*所有使用者*的[安全性群組](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)。</span><span class="sxs-lookup"><span data-stu-id="9184d-181">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span>

1. <span data-ttu-id="9184d-182">在 [**保護行動裝置上的工作檔案**] 選項上預設會選取**裝置遺失或遭竊時保護工作檔案**。</span><span class="sxs-lookup"><span data-stu-id="9184d-182">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="9184d-183">您有一個選項來開啟 [**管理使用者如何存取行動裝置上的 Office 檔案**，而且，所以建議您。</span><span class="sxs-lookup"><span data-stu-id="9184d-183">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![螢幕擷取畫面的保護工作檔案在行動裝置] 頁面上。](media/protectworkfilesondevices.png)

     - <span data-ttu-id="9184d-185">如果您依序展開 [**裝置遺失或遭竊時保護工作檔案**時，[預設值](protect-work-files-on-lost-or-stolen-device.md)，會預先選取：</span><span class="sxs-lookup"><span data-stu-id="9184d-185">If you expand **Protect work files when devices are lost or stolen**, the [default values](protect-work-files-on-lost-or-stolen-device.md) are pre-selected:</span></span>

        ![預設值為保護遺失的裝置上的檔案的螢幕擷取畫面。](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="9184d-187">如果您選取 [**管理使用者如何存取行動裝置上的 Office 檔案**，並予以展開，會顯示[預設值](manage-user-access-on-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="9184d-187">If you select **Manage how users access Office files on mobile devices** and expand it, the [default values](manage-user-access-on-mobile-devices.md) are shown.</span></span> <span data-ttu-id="9184d-188">建議您在設定時接受預設值，以建立適用於所有使用者的 Android、iOS 和 Windows 10 應用程式原則。</span><span class="sxs-lookup"><span data-stu-id="9184d-188">We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="9184d-189">設定完成後，您可以建立更多原則。</span><span class="sxs-lookup"><span data-stu-id="9184d-189">You can create more policies after setup completes.</span></span>

        ![行動裝置上的 Office 檔案的保護設定的螢幕擷取畫面。](media/useraccessonmobile.png)

2. <span data-ttu-id="9184d-191">在最後一個步驟保護資料和裝置可讓您保護 Windows 10 裝置設定原則。</span><span class="sxs-lookup"><span data-stu-id="9184d-191">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="9184d-192">使用者的 Windows 10 連線至您的組織時，會自動套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="9184d-192">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="9184d-193">您可以展開**保護 Windows 10 裝置**，以查看並修改[預設值](secure-windows-10-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="9184d-193">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="9184d-194">您也可以選擇在 Windows 10 裝置上[自動安裝 Office](install-office-on-windows-10-during-setup.md) 。</span><span class="sxs-lookup"><span data-stu-id="9184d-194">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![螢幕擷取畫面的設定 Windows 10 裝置設定] 頁面。](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a><span data-ttu-id="9184d-196">修改或新增原則在系統管理中心</span><span class="sxs-lookup"><span data-stu-id="9184d-196">Modify or add policies in the admin center</span></span>

<span data-ttu-id="9184d-197">請參閱[管理 Microsoft 365 商務版](manage.md)如需如何檢視和修改裝置和應用程式保護的主題連結原則，以及如何移除其中資料，或重設使用者的裝置。</span><span class="sxs-lookup"><span data-stu-id="9184d-197">See [manage Microsoft 365 Business](manage.md) for links to topics on how to view and modify device and app protection polices, and how to remove data from, or reset user devices.</span></span>

## <a name="deploy-and-manage-windows-10"></a><span data-ttu-id="9184d-198">部署及管理 Windows 10</span><span class="sxs-lookup"><span data-stu-id="9184d-198">Deploy and manage Windows 10</span></span>
<span data-ttu-id="9184d-199">若要手動連線到 Azure AD，其中的新電腦，或藉由變更登入設定檔的現有電腦安裝期間[設定為 Microsoft 365 商務版使用者的 Windows 裝置](set-up-windows-devices.md)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="9184d-199">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) to manually connect to Azure AD, either during setup for new computers, or by changing sign-in profile for existing computers.</span></span> 

### <a name="use-autopilot-to-set-up-new-devices"></a><span data-ttu-id="9184d-200">使用 Autopilot 來設定新裝置</span><span class="sxs-lookup"><span data-stu-id="9184d-200">Use Autopilot to set up new devices</span></span>

<span data-ttu-id="9184d-201">您可以使用[Windows Autopilot](add-autopilot-devices-and-profile.md)來自動預先設定**新**的 Windows 10 裝置的使用者，但它可能會比較容易取得[合作夥伴](https://www.microsoft.com/solution-providers/search)可以執行這項操作您。</span><span class="sxs-lookup"><span data-stu-id="9184d-201">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="9184d-202">您也可以移至[Microsoft 網上商店](https://go.microsoft.com/fwlink/?linkid=874598)，並要求您購買您的新裝置上設定雲端技術專家。</span><span class="sxs-lookup"><span data-stu-id="9184d-202">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

### <a name="access-on-premises-resources"></a><span data-ttu-id="9184d-203">存取內部部署資源</span><span class="sxs-lookup"><span data-stu-id="9184d-203">Access on-premises resources</span></span>

<span data-ttu-id="9184d-204">如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 商務版來保護 Windows 10 裝置，同時仍維持需要本機驗證的內部部署資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="9184d-204">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="9184d-205">請遵循[啟用由 Microsoft 365 商務版來管理已加入網域的 Windows 10 裝置](manage-windows-devices.md)設定此案例中的步驟。</span><span class="sxs-lookup"><span data-stu-id="9184d-205">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="9184d-206">這是慣用的方法，在此狀態的裝置稱為混合式 Azure AD 加入的裝置。</span><span class="sxs-lookup"><span data-stu-id="9184d-206">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

<span data-ttu-id="9184d-207">如果貴公司有本機 Active Directory，其中包含一些內部資源 （例如檔案共用和印表機），您可以授與您的 Azure AD 加入的裝置存取這些資源遵循以下步驟：[存取內部部署資源Microsoft 365 商務版中的 azure AD 加入裝置](access-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="9184d-207">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="9184d-208">部署 Office 365 用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="9184d-208">Deploy Office 365 client apps</span></span>

<span data-ttu-id="9184d-209">如果您選擇要設定自動安裝期間集的 Office 應用程式中的，應用程式會安裝在 Windows 10 裝置上，使用者已經登入後到 Azure AD 從他們的 Windows 裝置，使用其公司認證。</span><span class="sxs-lookup"><span data-stu-id="9184d-209">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="9184d-210">若要在行動裝置的 iOS 或 Android 裝置上安裝 Office，請參閱[為 Microsoft 365 商務版使用者的行動裝置上設定](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="9184d-210">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="9184d-211">您也可以個別安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="9184d-211">You can also install Office individually.</span></span> <span data-ttu-id="9184d-212">請參閱 <<c0>在 PC 或 Mac 上安裝 Office的指示。</span><span class="sxs-lookup"><span data-stu-id="9184d-212">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) for instructions.</span></span>

## <a name="additional-security-settings"></a><span data-ttu-id="9184d-213">額外的安全性設定</span><span class="sxs-lookup"><span data-stu-id="9184d-213">Additional security settings</span></span>

<span data-ttu-id="9184d-214">除了安全性與合規性設定安裝程式精靈] 中的，您也可以設定下列其他設定：</span><span class="sxs-lookup"><span data-stu-id="9184d-214">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="9184d-215">**電子郵件的惡意程式碼保護**</span><span class="sxs-lookup"><span data-stu-id="9184d-215">**Email malware protection**</span></span>
- <span data-ttu-id="9184d-216">**進階的威脅防護 (ATP) 的安全附件**</span><span class="sxs-lookup"><span data-stu-id="9184d-216">**Advanced Threat Protection (ATP) Safe Attachments**</span></span>
- <span data-ttu-id="9184d-217">**ATP 安全連結**</span><span class="sxs-lookup"><span data-stu-id="9184d-217">**ATP Safe Links**</span></span>
- <span data-ttu-id="9184d-218">**引起的防網路釣魚**</span><span class="sxs-lookup"><span data-stu-id="9184d-218">**APT anti-phishing**</span></span>
- <span data-ttu-id="9184d-219">**Exchange Online 封存**</span><span class="sxs-lookup"><span data-stu-id="9184d-219">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="9184d-220">**資料外洩防護 (DLP)**</span><span class="sxs-lookup"><span data-stu-id="9184d-220">**Data loss prevention (DLP)**</span></span>
- <span data-ttu-id="9184d-221">**Azure 資訊保護**（方案 1）</span><span class="sxs-lookup"><span data-stu-id="9184d-221">**Azure Information Protection** (Plan 1)</span></span>
- <span data-ttu-id="9184d-222">**Intune 入口網站可用性**</span><span class="sxs-lookup"><span data-stu-id="9184d-222">**Intune portal availability**</span></span>

<span data-ttu-id="9184d-223">若要取得啟動，請參閱[設定進階的安全性原則](set-up-advanced-security.md)。</span><span class="sxs-lookup"><span data-stu-id="9184d-223">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="9184d-224">另請參閱[上方的 10 種方法來保護您的 Microsoft 365 商務版](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)的最佳安全性作法藍圖。</span><span class="sxs-lookup"><span data-stu-id="9184d-224">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>