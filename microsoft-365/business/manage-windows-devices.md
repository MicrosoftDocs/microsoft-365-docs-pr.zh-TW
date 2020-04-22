---
title: 啟用已加入網域的 Windows 10 裝置以供商務用 Microsoft 365 管理
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 瞭解如何啟用 Microsoft 365，以在幾個步驟中保護本機作用中已加入目錄的 Windows 10 裝置。
ms.openlocfilehash: 431c1be74723e156befb13ffe1ed98b48b9a23cb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633276"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-for-business"></a><span data-ttu-id="af9dd-103">啟用已加入網域的 Windows 10 裝置以供商務用 Microsoft 365 管理</span><span class="sxs-lookup"><span data-stu-id="af9dd-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 for business</span></span>

<span data-ttu-id="af9dd-104">如果您的組織使用 Windows Server Active Directory 內部部署，您可以設定 Microsoft 365 for business 來保護您的 Windows 10 裝置，同時仍保持存取需要本機驗證的內部部署資源。</span><span class="sxs-lookup"><span data-stu-id="af9dd-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 for business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="af9dd-105">若要設定此保護，您可以執行**混合式 AZURE AD 聯結裝置**。</span><span class="sxs-lookup"><span data-stu-id="af9dd-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="af9dd-106">這些裝置會同時加入您的內部部署 Active Directory 和您的 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="af9dd-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="af9dd-107">這段影片說明如何針對最常見的案例設定此功能的步驟，在後續步驟中也會詳細說明。</span><span class="sxs-lookup"><span data-stu-id="af9dd-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="af9dd-108">1. 準備目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="af9dd-108">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="af9dd-109">在您從本機 Active Directory 網域同步處理使用者和電腦之前，請先複查[準備好目錄同步處理至 Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="af9dd-109">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="af9dd-110">具體說來：</span><span class="sxs-lookup"><span data-stu-id="af9dd-110">In particular:</span></span>

   - <span data-ttu-id="af9dd-111">請確定目錄中的下列屬性沒有重複專案： **mail**、 **proxyAddresses**及**userPrincipalName**。</span><span class="sxs-lookup"><span data-stu-id="af9dd-111">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="af9dd-112">這些值必須是唯一的，而且必須移除任何重複專案。</span><span class="sxs-lookup"><span data-stu-id="af9dd-112">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="af9dd-113">建議您為每個本機使用者帳戶設定**userPrincipalName** （UPN）屬性，使其符合與授權的 Microsoft 365 使用者相對應的主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="af9dd-113">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="af9dd-114">例如： *mary.shelley@contoso.com* ，而不是*mary@contoso。*</span><span class="sxs-lookup"><span data-stu-id="af9dd-114">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="af9dd-115">如果 Active Directory 網域以非可路由的尾碼（如 .com*或* *lan*）結束，請不要依 internet 路由尾碼（如 *.com*或*org*）來調整本機使用者帳戶的 UPN 尾碼，如[準備目錄同步處理的非路由網域](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)中所述。</span><span class="sxs-lookup"><span data-stu-id="af9dd-115">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="af9dd-116">2. 安裝及設定 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="af9dd-116">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="af9dd-117">若要將您的使用者、群組和連絡人從本機 Active Directory 同步處理至 Azure Active Directory，請安裝 Azure Active Directory Connect，並設定目錄同步作業。</span><span class="sxs-lookup"><span data-stu-id="af9dd-117">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> <span data-ttu-id="af9dd-118">請參閱[設定 Office 365 的目錄同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)處理以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="af9dd-118">See [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="af9dd-119">Microsoft 365 for business 的步驟完全相同。</span><span class="sxs-lookup"><span data-stu-id="af9dd-119">The steps are exactly the same for Microsoft 365 for business.</span></span> 

<span data-ttu-id="af9dd-120">當您設定 Azure AD Connect 的選項時，建議您啟用 **[密碼同步**處理]、[**無縫單一 Sign-On**] 及 [**密碼寫回**功能]，這是 Microsoft 365 for business 中也支援的功能。</span><span class="sxs-lookup"><span data-stu-id="af9dd-120">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="af9dd-121">在 Azure AD Connect 中，除了核取方塊之外，還有其他一些步驟可用於密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="af9dd-121">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="af9dd-122">如需詳細資訊，請參閱 how [to：設定密碼回寫](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。</span><span class="sxs-lookup"><span data-stu-id="af9dd-122">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

## <a name="3-configure-hybrid-azure-ad-join"></a><span data-ttu-id="af9dd-123">3. 設定混合式 Azure AD 聯結</span><span class="sxs-lookup"><span data-stu-id="af9dd-123">3. Configure Hybrid Azure AD Join</span></span>

<span data-ttu-id="af9dd-124">將 Windows 10 裝置加入混合式 Azure AD 之前，請確定您符合下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="af9dd-124">Before you enable Windows 10 devices to be Hybrid Azure AD joined, make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="af9dd-125">您正在執行最新版本的 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="af9dd-125">You're running the latest version of Azure AD Connect.</span></span>

   - <span data-ttu-id="af9dd-126">Azure AD connect 已同步處理要成為混合式 Azure AD 之裝置的所有電腦物件。</span><span class="sxs-lookup"><span data-stu-id="af9dd-126">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="af9dd-127">若電腦物件屬於特定的組織單位（OU），請確定這些 Ou 設定為同時在 Azure AD connect 中進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="af9dd-127">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>

<span data-ttu-id="af9dd-128">若要將現有的已加入網域的 Windows 10 裝置註冊成混合式 Azure AD 加入，請遵循教學課程中的步驟[：設定受管理網域的混合式 Azure Active Directory 加入](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)。</span><span class="sxs-lookup"><span data-stu-id="af9dd-128">To register existing domain-joined Windows 10 devices as Hybrid Azure AD joined, follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="af9dd-129">這種混合式-可讓您現有的內部部署 Active Directory 加入 Windows 10 電腦，並讓其成為雲端就緒。</span><span class="sxs-lookup"><span data-stu-id="af9dd-129">This hybrid-enables your existing on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a><span data-ttu-id="af9dd-130">4. 啟用自動註冊 Windows 10</span><span class="sxs-lookup"><span data-stu-id="af9dd-130">4. Enable automatic enrollment for Windows 10</span></span>

 <span data-ttu-id="af9dd-131">若要在 Intune 中自動註冊用於行動裝置管理的 Windows 10 裝置，請參閱[使用群組原則自動註冊 windows 10 裝置](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)。</span><span class="sxs-lookup"><span data-stu-id="af9dd-131">To automatically enroll Windows 10 devices for mobile device management in Intune, see [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span></span> <span data-ttu-id="af9dd-132">您可以在本機電腦層級設定群組原則，也可以針對大量作業，使用群組原則管理主控台和 ADMX 範本，在您的網域控制站上建立此群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="af9dd-132">You can set the Group Policy at a local computer level, or for bulk operations, you can use the Group Policy Management Console and ADMX templates to create this Group Policy setting on your Domain Controller.</span></span>

## <a name="5-configure-seamless-single-sign-on"></a><span data-ttu-id="af9dd-133">5. 設定無縫單一 Sign-On</span><span class="sxs-lookup"><span data-stu-id="af9dd-133">5. Configure Seamless Single Sign-On</span></span>

  <span data-ttu-id="af9dd-134">無縫 SSO 會在使用公司電腦時，自動將使用者登入其 Microsoft 365 雲端資源。</span><span class="sxs-lookup"><span data-stu-id="af9dd-134">Seamless SSO automatically signs users into their Microsoft 365 cloud resources when they use corporate computers.</span></span> <span data-ttu-id="af9dd-135">只需部署[Azure Active Directory 無縫單一 Sign-On](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)中所述的兩個群組原則選項之一：快速入門。</span><span class="sxs-lookup"><span data-stu-id="af9dd-135">Simply deploy one of the two Group Policy options described in [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span></span> <span data-ttu-id="af9dd-136">**群組原則**選項不允許使用者變更其設定，而**群組原則偏好**設定選項會設定值，但也會讓使用者可設定。</span><span class="sxs-lookup"><span data-stu-id="af9dd-136">The **Group Policy** option doesn't allow users to change their settings, while the **Group Policy Preference** option sets the values but also leaves them user-configurable.</span></span>

## <a name="6-set-up-windows-hello-for-business"></a><span data-ttu-id="af9dd-137">6. 設定 Windows Hello 企業版</span><span class="sxs-lookup"><span data-stu-id="af9dd-137">6. Set up Windows Hello for Business</span></span>

 <span data-ttu-id="af9dd-138">Windows Hello 企業版取代密碼，具有強雙因素驗證（2FA），用於簽署本機電腦。</span><span class="sxs-lookup"><span data-stu-id="af9dd-138">Windows Hello for Business replaces passwords with strong two-factor authentication (2FA) for signing into a local computer.</span></span> <span data-ttu-id="af9dd-139">其中一個因素是非對稱金鑰配對，另一個是 PIN 或其他本機手勢（如指紋或面部認可）（如果您的裝置支援它）。</span><span class="sxs-lookup"><span data-stu-id="af9dd-139">One factor is an asymmetric key pair, and the other is a PIN or other local gesture such as fingerprint or facial recognition if your device supports it.</span></span> <span data-ttu-id="af9dd-140">建議您在可能的情況下，將密碼與2FA 和 Windows Hello 企業版取代。</span><span class="sxs-lookup"><span data-stu-id="af9dd-140">We recommend that you replace passwords with 2FA and Windows Hello for Business where possible.</span></span>

<span data-ttu-id="af9dd-141">若要設定混合式 Windows Hello 企業版，請複查[混合金鑰信任 Windows Hello 企業版必要條件](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)。</span><span class="sxs-lookup"><span data-stu-id="af9dd-141">To configure Hybrid Windows Hello for Business, review the [Hybrid Key trust Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span></span> <span data-ttu-id="af9dd-142">然後依照[設定混合式 Windows Hello 企業版金鑰信任設定](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="af9dd-142">Then follow the instructions in [Configure Hybrid Windows Hello for Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span></span> 
