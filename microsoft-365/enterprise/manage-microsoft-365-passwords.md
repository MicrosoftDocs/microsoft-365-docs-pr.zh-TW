---
title: 管理 Microsoft 365 使用者帳戶密碼
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 瞭解如何管理 Microsoft 365 使用者帳戶密碼。
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905089"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="79c63-103">管理 Microsoft 365 使用者帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="79c63-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="79c63-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="79c63-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="79c63-105">您可以根據您的身分識別設定，以數種不同的方式管理 Microsoft 365 使用者帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="79c63-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="79c63-106">您可以在[Microsoft 365 系統管理中心](../admin/add-users/index.yml)、Active Directory 網域服務 (AD DS) 或 Azure Active Directory (Azure AD) 系統管理中心中管理使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="79c63-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="79c63-107">規劃管理使用者帳戶密碼的位置和方式</span><span class="sxs-lookup"><span data-stu-id="79c63-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="79c63-108">您可以管理使用者帳戶的位置和方式，取決於您要用於 Microsoft 365 的身分識別模型。</span><span class="sxs-lookup"><span data-stu-id="79c63-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="79c63-109">這兩種模型是僅限雲端和混合式的模型。</span><span class="sxs-lookup"><span data-stu-id="79c63-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="79c63-110">僅雲端</span><span class="sxs-lookup"><span data-stu-id="79c63-110">Cloud-only</span></span>

<span data-ttu-id="79c63-111">您可以在下列情況中管理使用者帳戶密碼：</span><span class="sxs-lookup"><span data-stu-id="79c63-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="79c63-112">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="79c63-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- <span data-ttu-id="79c63-113">Azure AD 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="79c63-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="79c63-114">混合式</span><span class="sxs-lookup"><span data-stu-id="79c63-114">Hybrid</span></span>

<span data-ttu-id="79c63-115">使用混合式身分識別時，密碼會儲存在 AD DS 中，因此您必須使用內部部署 AD DS 工具來管理使用者帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="79c63-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="79c63-116">即使使用密碼雜湊同步處理 (PHS) ，在此中，Azure AD 會在 AD DS 中儲存已雜湊版本的已雜湊版本，您和使用者必須在 AD DS 中管理其密碼。</span><span class="sxs-lookup"><span data-stu-id="79c63-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="79c63-117">透過 [密碼寫回](#pw_writeback)，您的使用者可以透過 Azure AD 變更其 AD DS 密碼。</span><span class="sxs-lookup"><span data-stu-id="79c63-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="79c63-118">防止不正確的密碼</span><span class="sxs-lookup"><span data-stu-id="79c63-118">Prevent bad passwords</span></span>

<span data-ttu-id="79c63-119">您所有的使用者都應使用 [Microsoft 密碼指導方針](https://www.microsoft.com/research/publication/password-guidance)來建立使用者帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="79c63-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="79c63-120">若要防止使用者建立容易猜測的密碼，請使用 Azure AD 密碼保護，此功能會同時使用全域禁止密碼清單和您指定的選用自訂禁止密碼清單。</span><span class="sxs-lookup"><span data-stu-id="79c63-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="79c63-121">例如，您可以指定組織的特定字詞，例如：</span><span class="sxs-lookup"><span data-stu-id="79c63-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="79c63-122">品牌名稱</span><span class="sxs-lookup"><span data-stu-id="79c63-122">Brand names</span></span>
- <span data-ttu-id="79c63-123">產品名稱</span><span class="sxs-lookup"><span data-stu-id="79c63-123">Product names</span></span>
- <span data-ttu-id="79c63-124">位置 (例如公司總部)</span><span class="sxs-lookup"><span data-stu-id="79c63-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="79c63-125">公司的特定內部條款</span><span class="sxs-lookup"><span data-stu-id="79c63-125">Company-specific internal terms</span></span>
- <span data-ttu-id="79c63-126">具有特定公司意義的縮寫</span><span class="sxs-lookup"><span data-stu-id="79c63-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="79c63-127">您可以在雲端和您的[內部部署 AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)[中](/azure/active-directory/authentication/concept-password-ban-bad)，禁止不良密碼。</span><span class="sxs-lookup"><span data-stu-id="79c63-127">You can ban bad passwords [in the cloud](/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="79c63-128">簡化使用者登入</span><span class="sxs-lookup"><span data-stu-id="79c63-128">Simplify user sign-in</span></span>

<span data-ttu-id="79c63-129">Azure AD 無縫單一 Sign-On (Azure AD 無縫 SSO) 搭配 PHS 及 Pass-Through 驗證 (PTA) ，讓使用者能夠登入使用 Azure AD 使用者帳戶的服務，而不必輸入密碼，而在許多情況下，他們的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="79c63-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="79c63-130">這可讓使用者更容易存取以雲端為基礎的應用程式，例如 Office 365，而不需要任何額外的內部部署元件，例如身分識別同盟伺服器。</span><span class="sxs-lookup"><span data-stu-id="79c63-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="79c63-131">您可以使用 Azure AD Connect 工具設定 Azure AD 無縫 SSO。</span><span class="sxs-lookup"><span data-stu-id="79c63-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="79c63-132">請參閱[設定 Azure AD 無縫 SSO 的指示](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。</span><span class="sxs-lookup"><span data-stu-id="79c63-132">See the [instructions to configure Azure AD Seamless SSO](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="79c63-133">簡化 AD DS 的密碼更新</span><span class="sxs-lookup"><span data-stu-id="79c63-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="79c63-134">透過密碼寫回，您可以允許使用者透過 Azure AD 重設其密碼，然後再將其複寫到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="79c63-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="79c63-135">使用者不需要存取其內部部署 AD DS 來更新其密碼。</span><span class="sxs-lookup"><span data-stu-id="79c63-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="79c63-136">對於沒有內部部署網路遠端存取連線的漫遊或遠端使用者而言，這非常有用。</span><span class="sxs-lookup"><span data-stu-id="79c63-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="79c63-137">為了充分利用 Azure AD Identity Protection 功能 (例如當偵測到高風險的帳戶洩露時，要求使用者變更其內部部署密碼)，需要密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="79c63-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="79c63-138">如需詳細資訊和設定指示，請參閱 [Azure AD SSPR 密碼回寫](/azure/active-directory/active-directory-passwords-writeback)。</span><span class="sxs-lookup"><span data-stu-id="79c63-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="79c63-p108">升級至最新版的 Azure AD Connect，以確保在新版本發行後能夠使用新功能並獲得最佳體驗。如需詳細資訊，請參閱 [Azure AD Connect 的自訂安裝](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。</span><span class="sxs-lookup"><span data-stu-id="79c63-p108">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="79c63-141">簡化密碼重設</span><span class="sxs-lookup"><span data-stu-id="79c63-141">Simplify password resets</span></span>

<span data-ttu-id="79c63-142">自助密碼重設 (SSPR) 可讓使用者重設或解除鎖定密碼或帳戶。</span><span class="sxs-lookup"><span data-stu-id="79c63-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="79c63-143">您可以使用詳細的報告來追蹤使用者何時存取系統，以及使用通知來警示誤用或濫用。</span><span class="sxs-lookup"><span data-stu-id="79c63-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="79c63-144">您必須啟用 [密碼回寫](#pw_writeback) ，才能部署密碼重設。</span><span class="sxs-lookup"><span data-stu-id="79c63-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="79c63-145">請參閱[推出密碼重設的指示](/azure/active-directory/authentication/howto-sspr-deployment)。</span><span class="sxs-lookup"><span data-stu-id="79c63-145">See the [instructions to roll out password reset](/azure/active-directory/authentication/howto-sspr-deployment).</span></span>