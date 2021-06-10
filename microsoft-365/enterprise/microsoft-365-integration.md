---
title: 與內部部署環境的整合 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: 在本文中，您將瞭解如何將 Microsoft 365 與您現有的目錄服務和內部部署環境進行整合。
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923963"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="5eb79-103">與內部部署環境的整合 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5eb79-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="5eb79-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="5eb79-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5eb79-105">您可以使用現有的內部部署 Active Directory 網域服務，將 Microsoft 365 與現有的內部部署 Active Directory 網域服務 (AD DS) 和內部部署安裝的 Exchange Server、商務用 Skype Server 2015 或 SharePoint Server 整合。</span><span class="sxs-lookup"><span data-stu-id="5eb79-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="5eb79-106">當您整合 AD DS 時，您可以同步處理及管理這兩種環境的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="5eb79-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="5eb79-107">您也可以新增密碼雜湊同步處理 (PHS) 或單一登入 (SSO) ，讓使用者能夠使用內部部署認證登入這兩種環境。</span><span class="sxs-lookup"><span data-stu-id="5eb79-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="5eb79-108">當您整合內部部署伺服器產品時，您會建立混合式環境。</span><span class="sxs-lookup"><span data-stu-id="5eb79-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="5eb79-109">混合式環境可協助您將使用者或資訊遷移至 Microsoft 365，也可以繼續將部分使用者或部分資訊放入內部部署，並在雲中進行。</span><span class="sxs-lookup"><span data-stu-id="5eb79-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="5eb79-110">如需混合式環境的詳細資訊，請參閱 [混合雲端](../solutions/cloud-architecture-models.md#hybrid)。</span><span class="sxs-lookup"><span data-stu-id="5eb79-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="5eb79-111">您也可以在 Microsoft 365 系統管理中心中，使用 Azure Active Directory (Azure AD) 顧問，以取得自訂安裝指導， (您必須登入 Microsoft 365) ：</span><span class="sxs-lookup"><span data-stu-id="5eb79-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="5eb79-112">Azure AD 安裝指南</span><span class="sxs-lookup"><span data-stu-id="5eb79-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="5eb79-113">從您的組織目錄同步處理使用者</span><span class="sxs-lookup"><span data-stu-id="5eb79-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="5eb79-114">Active Directory Federation Services (AD FS) 部署顧問</span><span class="sxs-lookup"><span data-stu-id="5eb79-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="5eb79-115">開始之前</span><span class="sxs-lookup"><span data-stu-id="5eb79-115">Before you begin</span></span>

<span data-ttu-id="5eb79-116">在整合 Microsoft 365 和內部部署環境之前，您也需要進行[網路規劃和效能調整](network-planning-and-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="5eb79-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="5eb79-117">您也會想要瞭解可用的身分 [識別模型](about-microsoft-365-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="5eb79-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="5eb79-118">請參閱[管理 Microsoft 365 帳戶](manage-microsoft-365-accounts.md)，以取得可用於管理 Microsoft 365 使用者帳戶的工具清單。</span><span class="sxs-lookup"><span data-stu-id="5eb79-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="5eb79-119">將 Microsoft 365 與 AD DS 整合</span><span class="sxs-lookup"><span data-stu-id="5eb79-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="5eb79-120">如果您在 AD DS 中有現有的使用者帳戶，您不想要在 Microsoft 365 中重新建立所有這些帳戶，以及在環境間引入差異或錯誤的風險。</span><span class="sxs-lookup"><span data-stu-id="5eb79-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="5eb79-121">目錄同步處理可協助您在您的內部部署與線上環境間鏡像這些帳戶。</span><span class="sxs-lookup"><span data-stu-id="5eb79-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="5eb79-122">透過目錄同步作業，您的使用者不需要記住每個環境的新資訊，而且您不需要建立或更新帳戶兩次。</span><span class="sxs-lookup"><span data-stu-id="5eb79-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="5eb79-123">您將需要 [準備內部部署目錄](prepare-for-directory-synchronization.md) ，以進行目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="5eb79-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![使用目錄同步處理將內部部署和線上使用者帳戶資訊同步處理](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="5eb79-125">如果您想要讓使用者能夠使用內部部署認證登入 Microsoft 365，您也可以設定 SSO。</span><span class="sxs-lookup"><span data-stu-id="5eb79-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="5eb79-126">使用 SSO 時，Microsoft 365 設定為信任內部部署環境以進行使用者驗證。</span><span class="sxs-lookup"><span data-stu-id="5eb79-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![使用單一登入時，在內部部署環境和線上環境中皆可使用相同的帳戶。](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="5eb79-128">目錄同步處理時使用或不使用密碼雜湊同步處理或未通過驗證 (PTA) </span><span class="sxs-lookup"><span data-stu-id="5eb79-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="5eb79-129">使用者使用使用者帳戶登入其內部部署環境 (網域 \ 使用者名稱) 。</span><span class="sxs-lookup"><span data-stu-id="5eb79-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="5eb79-130">當他們前往 Microsoft 365 時，他們必須使用其工作或學校帳戶 (user@domain.com) 登入。</span><span class="sxs-lookup"><span data-stu-id="5eb79-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="5eb79-131">這兩個環境中的使用者名稱相同。</span><span class="sxs-lookup"><span data-stu-id="5eb79-131">The user name is the same in both environments.</span></span> <span data-ttu-id="5eb79-132">當您新增 PHS 或 PTA 時，使用者會在兩個環境中使用相同的密碼，但在登入 Microsoft 365 時，必須提供這些認證。</span><span class="sxs-lookup"><span data-stu-id="5eb79-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="5eb79-133">目錄與 PHS 的同步處理是最常使用的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="5eb79-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="5eb79-134">若要設定目錄同步處理，請使用 Azure AD 連線。</span><span class="sxs-lookup"><span data-stu-id="5eb79-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="5eb79-135">如需相關指示，請參閱[使用 express 設定](/azure/active-directory/hybrid/how-to-connect-install-express)Microsoft 365 的和 Azure AD 連線[設定目錄同步](set-up-directory-synchronization.md)處理。</span><span class="sxs-lookup"><span data-stu-id="5eb79-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

<span data-ttu-id="5eb79-136">深入瞭解[準備目錄同步處理至 Microsoft 365](prepare-for-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="5eb79-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="5eb79-137">與 SSO 同步處理的目錄</span><span class="sxs-lookup"><span data-stu-id="5eb79-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="5eb79-138">使用者可以使用其使用者帳戶登入其內部部署環境。</span><span class="sxs-lookup"><span data-stu-id="5eb79-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="5eb79-139">當他們前往 Microsoft 365 時，會自動登入這些記錄，或者使用其內部部署環境所用的相同認證來登入 (網域 \ 使用者名稱) 。</span><span class="sxs-lookup"><span data-stu-id="5eb79-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="5eb79-140">若要設定 SSO，您也可以使用 Azure AD 連線。</span><span class="sxs-lookup"><span data-stu-id="5eb79-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="5eb79-141">如需相關指示，請參閱[AZURE AD 連線的自訂安裝](/azure/active-directory/hybrid/how-to-connect-install-custom)。</span><span class="sxs-lookup"><span data-stu-id="5eb79-141">For instructions, see [Custom installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>

<span data-ttu-id="5eb79-142">如需詳細資訊，請參閱 [單一登入](/azure/active-directory/manage-apps/what-is-single-sign-on)。</span><span class="sxs-lookup"><span data-stu-id="5eb79-142">For more information, see [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="5eb79-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="5eb79-143">Azure AD Connect</span></span>

<span data-ttu-id="5eb79-144">Azure AD 連線取代舊版本的身分識別整合工具，例如 DirSync 和 Azure AD 同步。若要從 Azure Active Directory 同步處理至 Azure AD 連線，請參閱[升級指示](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started)。</span><span class="sxs-lookup"><span data-stu-id="5eb79-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span></span> 

## <a name="see-also"></a><span data-ttu-id="5eb79-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5eb79-145">See also</span></span>

[<span data-ttu-id="5eb79-146">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="5eb79-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)