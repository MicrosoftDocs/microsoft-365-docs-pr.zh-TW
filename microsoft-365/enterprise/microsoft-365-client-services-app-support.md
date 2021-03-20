---
title: Microsoft 365 用戶端及服務應用程式支援
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 在本文中，尋找 Microsoft 365 用戶端和服務應用程式支援的詳細資料。
ms.openlocfilehash: e380efffc1bf29cbd4d3a77d32e4d1f8b2994da3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905005"
---
# <a name="microsoft-365-client-and-services-app-support"></a><span data-ttu-id="943b1-103">Microsoft 365 用戶端及服務應用程式支援</span><span class="sxs-lookup"><span data-stu-id="943b1-103">Microsoft 365 client and services app support</span></span>

<span data-ttu-id="943b1-104">Microsoft 支援廣泛的安全性、驗證和合規性功能，以確保客戶資料安全，並可讓 IT 系統管理員在 Microsoft 365 系統管理中心中為其使用者自訂原則。</span><span class="sxs-lookup"><span data-stu-id="943b1-104">Microsoft supports a wide range of security, authentication, and compliance features to keep customer data safe and allows IT administrators to customize policies within the Microsoft 365 admin center for their users.</span></span> <span data-ttu-id="943b1-105">下列功能只是您可以設定的眾多企業功能的子集，具體取決於您的 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="943b1-105">The following features are just a subset of the many enterprise features that you can configure depending on your Microsoft 365 subscription.</span></span>

## <a name="client-and-service-support"></a><span data-ttu-id="943b1-106">用戶端和服務支援</span><span class="sxs-lookup"><span data-stu-id="943b1-106">Client and service support</span></span>

### <a name="continuous-access-evaluation-preview"></a><span data-ttu-id="943b1-107">連續存取評估 (預覽) </span><span class="sxs-lookup"><span data-stu-id="943b1-107">Continuous access evaluation (preview)</span></span>

<span data-ttu-id="943b1-108">連續存取評估的實施方式是讓服務（例如 Exchange Online、SharePoint 線上及小組）在 Azure Active Directory 中訂閱重要事件，以便在即時評估及強制執行這些事件。</span><span class="sxs-lookup"><span data-stu-id="943b1-108">Continuous access evaluation is implemented by enabling services, like Exchange Online, SharePoint Online, and Teams, to subscribe to critical events in Azure Active Directory so that those events can be evaluated and enforced near real time.</span></span> <span data-ttu-id="943b1-109">重大事件評估不依賴條件式存取原則，所以可用於任何租使用者。</span><span class="sxs-lookup"><span data-stu-id="943b1-109">Critical event evaluation does not rely on Conditional Access policies so is available in any tenant.</span></span>

<span data-ttu-id="943b1-110">下列事件目前已評估：</span><span class="sxs-lookup"><span data-stu-id="943b1-110">The following events are currently evaluated:</span></span>

- <span data-ttu-id="943b1-111">刪除或停用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="943b1-111">A user account is deleted or disabled</span></span>
- <span data-ttu-id="943b1-112">變更或重設使用者的密碼</span><span class="sxs-lookup"><span data-stu-id="943b1-112">The password for a user is changed or reset</span></span>
- <span data-ttu-id="943b1-113">已為使用者啟用多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="943b1-113">Multi-factor authentication is enabled for the user</span></span>
- <span data-ttu-id="943b1-114">管理員明確撤銷使用者的所有重新整理權杖</span><span class="sxs-lookup"><span data-stu-id="943b1-114">Administrator explicitly revokes all refresh tokens for a user</span></span>
- <span data-ttu-id="943b1-115">Azure AD 身分識別保護偵測到的使用者風險已提升</span><span class="sxs-lookup"><span data-stu-id="943b1-115">Elevated user risk detected by Azure AD Identity Protection</span></span>

<span data-ttu-id="943b1-116">如需用戶端和服務應用程式支援的連續存取評估的詳細資訊，請參閱 [連續存取評估 (預覽) ](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)。</span><span class="sxs-lookup"><span data-stu-id="943b1-116">For more information about continuous access evaluation for client and services app support, see [Continuous access evaluation (preview)](/azure/active-directory/conditional-access/concept-continuous-access-evaluation).</span></span>

## <a name="client-support"></a><span data-ttu-id="943b1-117">用戶端支援</span><span class="sxs-lookup"><span data-stu-id="943b1-117">Client support</span></span>

### <a name="certificate-based-authentication"></a><span data-ttu-id="943b1-118">憑證型驗證</span><span class="sxs-lookup"><span data-stu-id="943b1-118">Certificate-based authentication</span></span>

<span data-ttu-id="943b1-119">憑證型驗證 (CBA) 是使用數位憑證來識別使用者、電腦或裝置，然後再將存取權授與資源、網路、應用程式或服務。</span><span class="sxs-lookup"><span data-stu-id="943b1-119">Certificate-based authentication (CBA) is the use of a digital certificate to identify a user, machine, or device before granting access to a resource, network, application, or service.</span></span> <span data-ttu-id="943b1-120">在使用者驗證中，它通常會與傳統方法（如使用者名稱和密碼）搭配部署。</span><span class="sxs-lookup"><span data-stu-id="943b1-120">In user authentication, it is often deployed in coordination with traditional methods such as usernames and passwords.</span></span>

<span data-ttu-id="943b1-121">有些傳統的解決方案只適用于使用者，例如生物特徵和單一時間密碼 (OTP) 。</span><span class="sxs-lookup"><span data-stu-id="943b1-121">Some traditional solutions only work for users, such as biometrics and one-time passwords (OTP).</span></span> <span data-ttu-id="943b1-122">使用憑證型驗證時，相同的解決方案可用於所有端點;使用者、裝置和不斷增加的網際網路 (IoT) 。</span><span class="sxs-lookup"><span data-stu-id="943b1-122">With certificate-based authentication, the same solution can be used for all endpoints; users, devices, and the growing Internet of Things (IoT).</span></span>

<span data-ttu-id="943b1-123">如需用戶端和服務應用程式支援之憑證型驗證的詳細資訊，請參閱 [Microsoft 365 用戶端應用程式支援：憑證型驗證](microsoft-365-client-support-certificate-based-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="943b1-123">For more information about certificate-based authentication for client and services app support, see [Microsoft 365 Client App Support: Certificate-based Authentication](microsoft-365-client-support-certificate-based-authentication.md).</span></span>

### <a name="conditional-access"></a><span data-ttu-id="943b1-124">條件式存取</span><span class="sxs-lookup"><span data-stu-id="943b1-124">Conditional Access</span></span>

<span data-ttu-id="943b1-125">條件式存取是 Azure Active Directory 用來將信號一起使用的工具，以作出決策，並強制執行組織存取原則。</span><span class="sxs-lookup"><span data-stu-id="943b1-125">Conditional Access is the tool used by Azure Active Directory to bring signals together, to make decisions, and enforce organizational access policies.</span></span> <span data-ttu-id="943b1-126">條件式存取是在新的身分識別導向控制模型的核心。</span><span class="sxs-lookup"><span data-stu-id="943b1-126">Conditional Access is at the heart of the new identity-driven control model.</span></span>

<span data-ttu-id="943b1-127">條件式存取原則是用來授與資源存取權的 if 語句。</span><span class="sxs-lookup"><span data-stu-id="943b1-127">Conditional Access policies are if-then statements for granting access to resources.</span></span> <span data-ttu-id="943b1-128">若使用者想要存取資源，使用者必須完成動作。</span><span class="sxs-lookup"><span data-stu-id="943b1-128">If a user wants to access a resource, then the user must complete an action.</span></span> <span data-ttu-id="943b1-129">在進行原則訪問決策時，條件式存取可使用的常見信號包括：</span><span class="sxs-lookup"><span data-stu-id="943b1-129">Common signals that Conditional Access can use when making a policy access decision include:</span></span>

- <span data-ttu-id="943b1-130">使用者或群組成員資格</span><span class="sxs-lookup"><span data-stu-id="943b1-130">User or group membership</span></span>
- <span data-ttu-id="943b1-131">IP 位置資訊</span><span class="sxs-lookup"><span data-stu-id="943b1-131">IP location information</span></span>
- <span data-ttu-id="943b1-132">裝置資訊</span><span class="sxs-lookup"><span data-stu-id="943b1-132">Device information</span></span>
- <span data-ttu-id="943b1-133">應用程式資訊</span><span class="sxs-lookup"><span data-stu-id="943b1-133">Application information</span></span>
- <span data-ttu-id="943b1-134">即時及計算的風險偵測</span><span class="sxs-lookup"><span data-stu-id="943b1-134">Real-time and calculated risk detection</span></span>
- <span data-ttu-id="943b1-135">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="943b1-135">Microsoft Cloud App Security (MCAS)</span></span>

<span data-ttu-id="943b1-136">進行這些存取決定時，原則可以採取不同的動作：</span><span class="sxs-lookup"><span data-stu-id="943b1-136">When making these access decisions, the policies can take different actions:</span></span>

- <span data-ttu-id="943b1-137">原則可以封鎖存取：此設定是最具限制性的動作，可防止使用者存取資源。</span><span class="sxs-lookup"><span data-stu-id="943b1-137">The policy can block access: This configuration is the most restrictive action and prevents the user from accessing the resource.</span></span>
- <span data-ttu-id="943b1-138">原則可以授與存取權：此設定的限制較少，但仍然需要下列一或多個選項：</span><span class="sxs-lookup"><span data-stu-id="943b1-138">The policy can grant access: This configuration is a less restrictive decision and may still require one or more of the following options:</span></span>

    - <span data-ttu-id="943b1-139">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="943b1-139">Multi-factor authentication</span></span>
    - <span data-ttu-id="943b1-140">要標示為相容的裝置</span><span class="sxs-lookup"><span data-stu-id="943b1-140">The device to be marked as compliant</span></span>
    - <span data-ttu-id="943b1-141">裝置的混合式 Azure AD 已加入</span><span class="sxs-lookup"><span data-stu-id="943b1-141">The device is hybrid Azure AD joined</span></span>
    - <span data-ttu-id="943b1-142">核准的用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="943b1-142">An approved client app</span></span>
    - <span data-ttu-id="943b1-143">已設定 (預覽的應用程式保護原則) </span><span class="sxs-lookup"><span data-stu-id="943b1-143">App protection policy configured (preview)</span></span>

<span data-ttu-id="943b1-144">如需用戶端和服務應用程式支援的條件式存取的相關資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="943b1-144">For more information about Conditional Access for client and services app support, see:</span></span>

- [<span data-ttu-id="943b1-145">Microsoft 365 用戶端應用程式支援：以裝置為基礎的條件式存取</span><span class="sxs-lookup"><span data-stu-id="943b1-145">Microsoft 365 Client App Support: Device-based Conditional Access</span></span>](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a><span data-ttu-id="943b1-146">行動應用程式管理</span><span class="sxs-lookup"><span data-stu-id="943b1-146">Mobile application management</span></span>

<span data-ttu-id="943b1-147">使用者通常會從相同行動裝置存取組織和個人檔、電子郵件和資料。</span><span class="sxs-lookup"><span data-stu-id="943b1-147">Users often access both organization and personal documents, email, and data from the same mobile device.</span></span> <span data-ttu-id="943b1-148">這些裝置通常是由個人擁有，應設定為同時保護組織資料和使用者個人隱私權。</span><span class="sxs-lookup"><span data-stu-id="943b1-148">Those devices are often personally owned and should be configured to protect both organization data and the user's personal privacy.</span></span>

<span data-ttu-id="943b1-149">當使用者存取組織資料時，組織必須確信組織原則（例如設定原則及保護原則）得以套用，以協助保護裝置上的組織資料。</span><span class="sxs-lookup"><span data-stu-id="943b1-149">When a user accesses organization data, the organization must be confident that organization policies, such as configuration policies and protection policies, are applied to help protect organization data on the device.</span></span> <span data-ttu-id="943b1-150">此外，使用者在裝置上的個人內容應該保留在組織的控制範圍之外。</span><span class="sxs-lookup"><span data-stu-id="943b1-150">Additionally, the user's personal content on the device should remain outside of the organization's control.</span></span>

<span data-ttu-id="943b1-151">若為組織管理的內容，您可以套用應用程式管理原則，以控制如何使用 Microsoft Intune 存取、共用和使用資料。</span><span class="sxs-lookup"><span data-stu-id="943b1-151">For organization-managed content, you can apply application management policies to control how data is accessed, shared, and used by using Microsoft Intune.</span></span> <span data-ttu-id="943b1-152">例如，支援下列動作：</span><span class="sxs-lookup"><span data-stu-id="943b1-152">For example, the following actions are supported:</span></span>

- <span data-ttu-id="943b1-153">Remote 擦除受管理的組織內容 (也稱為組織資料) </span><span class="sxs-lookup"><span data-stu-id="943b1-153">Remote wipe the managed organization content (also referred to org data)</span></span>
- <span data-ttu-id="943b1-154">避免將組織內容粘貼到非組織位置</span><span class="sxs-lookup"><span data-stu-id="943b1-154">Prevent pasting organization content into non-organization locations</span></span>
- <span data-ttu-id="943b1-155">需要 PIN 才能存取組織內容</span><span class="sxs-lookup"><span data-stu-id="943b1-155">Require a PIN to access organization content</span></span>
- <span data-ttu-id="943b1-156">防止受管理的應用程式在越獄或根的裝置上執行</span><span class="sxs-lookup"><span data-stu-id="943b1-156">Prevent managed apps from running on jailbroken or rooted devices</span></span>
- <span data-ttu-id="943b1-157">防止將組織內容儲存至未核准的雲端儲存提供者</span><span class="sxs-lookup"><span data-stu-id="943b1-157">Prevent organization content from being saved to unapproved cloud storage providers</span></span>
- <span data-ttu-id="943b1-158">防止未核准的內容傳輸到受管理的應用程式</span><span class="sxs-lookup"><span data-stu-id="943b1-158">Prevent unapproved content from being transferred into managed applications</span></span>
- <span data-ttu-id="943b1-159">只有在套用原則之後才允許存取組織內容</span><span class="sxs-lookup"><span data-stu-id="943b1-159">Allow access to organization content only after policies have been applied</span></span>
- <span data-ttu-id="943b1-160">提供應用程式設定以管理應用程式的行為和設定</span><span class="sxs-lookup"><span data-stu-id="943b1-160">Deliver application configuration to manage the application's behavior and settings</span></span>
- <span data-ttu-id="943b1-161">停用多身分識別功能或個人用途，將受管理的應用程式限制為已定義的身分識別。</span><span class="sxs-lookup"><span data-stu-id="943b1-161">Restrict the managed application to a defined identity by disabling multi-identity capabilities or personal usage</span></span>

<span data-ttu-id="943b1-162">如需使用 Microsoft Intune 行動應用程式管理的詳細資訊，請參閱 [什麼是 Microsoft intune 應用程式管理？](/mem/intune/apps/app-management)</span><span class="sxs-lookup"><span data-stu-id="943b1-162">For more information about mobile application management with Microsoft Intune, see [What is Microsoft Intune app management?](/mem/intune/apps/app-management)</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="943b1-163">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="943b1-163">Multi-factor authentication</span></span>

<span data-ttu-id="943b1-164">[多重要素驗證 (MFA) 是一種電腦存取控制方法，在此方法中，使用者只有在成功顯示幾個個別的證據以驗證機制後，才會被授與存取權。</span><span class="sxs-lookup"><span data-stu-id="943b1-164">[Multi-factor authentication (MFA) is a method of computer access control in which a user is granted access only after successfully presenting several separate pieces of evidence to an authentication mechanism.</span></span> <span data-ttu-id="943b1-165">此方法通常至少使用下列兩種類別：</span><span class="sxs-lookup"><span data-stu-id="943b1-165">This method typically uses at least two of the following categories:</span></span>

- <span data-ttu-id="943b1-166">知識 (他們知道的內容) </span><span class="sxs-lookup"><span data-stu-id="943b1-166">Knowledge (something they know)</span></span>
- <span data-ttu-id="943b1-167">已擁有 () 的內容</span><span class="sxs-lookup"><span data-stu-id="943b1-167">Possession (something they have)</span></span>
- <span data-ttu-id="943b1-168">Inherence () 的內容</span><span class="sxs-lookup"><span data-stu-id="943b1-168">Inherence (something they are)</span></span>

<span data-ttu-id="943b1-169">如需用戶端和服務應用程式支援之多重要素驗證的詳細資訊，請參閱 [Microsoft 365 用戶端應用程式支援：多重要素驗證](microsoft-365-client-support-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="943b1-169">For more information about multi-factor authentication for client and services app support, see [Microsoft 365 Client App Support: Multi-factor authentication](microsoft-365-client-support-multi-factor-authentication.md).</span></span>

### <a name="single-sign-on"></a><span data-ttu-id="943b1-170">單一登入</span><span class="sxs-lookup"><span data-stu-id="943b1-170">Single sign-on</span></span>

<span data-ttu-id="943b1-171">單一登入 (SSO) 會在使用者登入 Azure Active Directory 中的應用程式時，加入安全性和便利性。</span><span class="sxs-lookup"><span data-stu-id="943b1-171">Single sign-on (SSO) adds security and convenience when your users sign-on to applications in Azure Active Directory.</span></span> <span data-ttu-id="943b1-172">使用單一登入時，使用者可以使用一個帳戶登入一次，以存取內部部署 Active Directory 網域服務 (AD DS) 加入網域的裝置、軟體為服務 (SaaS) 應用程式，以及組織中的 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="943b1-172">With single sign-on, users sign in once with one account to access on-premises Active Directory Domain Services (AD DS) domain-joined devices, software as a service (SaaS) applications, and web applications in your organization.</span></span>

<span data-ttu-id="943b1-173">如需有關用戶端和服務應用程式支援的單一登入的詳細資訊，請參閱 [Microsoft 365 用戶端應用程式支援：單一登入](microsoft-365-client-support-single-sign-on.md)。</span><span class="sxs-lookup"><span data-stu-id="943b1-173">For more information about single sign-on for client and services app support, see [Microsoft 365 Client App Support: Single sign-on](microsoft-365-client-support-single-sign-on.md).</span></span>

## <a name="services-support"></a><span data-ttu-id="943b1-174">服務支援</span><span class="sxs-lookup"><span data-stu-id="943b1-174">Services support</span></span>

### <a name="modern-authentication"></a><span data-ttu-id="943b1-175">新式驗證</span><span class="sxs-lookup"><span data-stu-id="943b1-175">Modern authentication</span></span>

<span data-ttu-id="943b1-176">新式驗證可讓客戶針對 Office 365 進行驗證的新案例，並針對租使用者系統管理員強制執行各 Office 365 租使用者的特定驗證需求，例如：</span><span class="sxs-lookup"><span data-stu-id="943b1-176">Modern authentication enables new scenarios for customers to authenticate against Office 365 and for tenant admins to enforce specific authentication requirements across the Office 365 tenancy, such as:</span></span>

- <span data-ttu-id="943b1-177">多重要素驗證支援與租使用者和服務的管理互動，以及與應用程式及其資料的使用者互動</span><span class="sxs-lookup"><span data-stu-id="943b1-177">Multi-factor authentication support for administrative interaction with the tenancy and services, and end-user interaction with applications and their data</span></span>
- <span data-ttu-id="943b1-178">條件式存取</span><span class="sxs-lookup"><span data-stu-id="943b1-178">Conditional access</span></span>
- <span data-ttu-id="943b1-179">SAML-based 協力廠商身分識別提供者登入</span><span class="sxs-lookup"><span data-stu-id="943b1-179">SAML-based third-party identity provider sign-in</span></span>
- <span data-ttu-id="943b1-180">個人電腦上的智慧卡登入</span><span class="sxs-lookup"><span data-stu-id="943b1-180">Smartcard log on personal computers</span></span>
- <span data-ttu-id="943b1-181">行動裝置上的憑證型驗證</span><span class="sxs-lookup"><span data-stu-id="943b1-181">Certificate-based authentication on mobile devices</span></span>
- <span data-ttu-id="943b1-182">不再需要透過基本驗證傳輸認證。</span><span class="sxs-lookup"><span data-stu-id="943b1-182">No longer require the transmission of credentials over basic authentication.</span></span>

<span data-ttu-id="943b1-183">如需新式驗證服務支援的相關資訊，請參閱 [authentication 與 authorization](/azure/active-directory/develop/authentication-vs-authorization)。</span><span class="sxs-lookup"><span data-stu-id="943b1-183">For more information about modern authentication services support, see [Authentication vs. authorization](/azure/active-directory/develop/authentication-vs-authorization).</span></span>

### <a name="azure-active-directory-conditional-access"></a><span data-ttu-id="943b1-184">Azure Active Directory 條件式存取</span><span class="sxs-lookup"><span data-stu-id="943b1-184">Azure Active Directory Conditional Access</span></span>

<span data-ttu-id="943b1-185">Azure Active Directory (Azure AD) 條件式存取規則，可讓客戶根據諸如裝置規範或網路位置等屬性，控制線上服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="943b1-185">Azure Active Directory (Azure AD) Conditional Access rules allow customers to control access to online services, based on attributes such as device compliance or network location.</span></span> <span data-ttu-id="943b1-186">您可以使用下列解決方案：</span><span class="sxs-lookup"><span data-stu-id="943b1-186">The following solutions may be used:</span></span>

- <span data-ttu-id="943b1-187">Azure AD 多重要素驗證-基礎的條件式存取</span><span class="sxs-lookup"><span data-stu-id="943b1-187">Azure AD multi-factor authentication-based Conditional Access</span></span>
- <span data-ttu-id="943b1-188">Azure AD 位置基礎的條件式存取</span><span class="sxs-lookup"><span data-stu-id="943b1-188">Azure AD location-based Conditional Access</span></span>
- <span data-ttu-id="943b1-189">Azure AD 裝置基礎的條件式存取</span><span class="sxs-lookup"><span data-stu-id="943b1-189">Azure AD device-based Conditional Access</span></span>

<span data-ttu-id="943b1-190">Azure AD 條件式存取規則會套用於每個應用程式，客戶可以根據不同的條件來控制存取。</span><span class="sxs-lookup"><span data-stu-id="943b1-190">Azure AD Conditional access rules are applied per-application and are available for customers to control access based on different conditions.</span></span> <span data-ttu-id="943b1-191">使用行動 [裝置管理 (MDM) 或 Intune](/mem/intune/fundamentals/what-is-device-management)，客戶必須能夠將 Microsoft 365 的存取許可權制為僅限使用組織裝置的使用者，或是已註冊個人裝置以進行管理的使用者。</span><span class="sxs-lookup"><span data-stu-id="943b1-191">Using [Mobile Device Management (MDM) or Intune](/mem/intune/fundamentals/what-is-device-management), customers must be able to restrict access to Microsoft 365 to only those users who are using an organization device or who have enrolled their personal device for management.</span></span> <span data-ttu-id="943b1-192">例如，客戶可以設定條件式存取規則，以強制執行下列控制項：</span><span class="sxs-lookup"><span data-stu-id="943b1-192">For example, customers may configure Conditional Access rules to enforce controls such as:</span></span>

- <span data-ttu-id="943b1-193">只允許來自已加入網域或符合網域的裝置的存取權</span><span class="sxs-lookup"><span data-stu-id="943b1-193">Only allow access from devices that are domain joined or domain compliant</span></span>
- <span data-ttu-id="943b1-194">針對所有 Exchange Online 服務存取強制執行多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="943b1-194">Enforce multi-factor authentication for all access to Exchange Online services</span></span>

<span data-ttu-id="943b1-195">如需 Azure Active Directory 條件式存取的相關資訊，請參閱 [什麼是條件式存取？](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="943b1-195">For more information about Azure Active Directory Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span>

### <a name="tls-12-support"></a><span data-ttu-id="943b1-196">TLS 1.2 支援</span><span class="sxs-lookup"><span data-stu-id="943b1-196">TLS 1.2 support</span></span>

<span data-ttu-id="943b1-197">若要為我們的客戶提供一流的加密，Microsoft 計畫停止支援傳輸層安全性 (TLS) 版本1.0 和 1.1 in Office 365 和 Office 365 GCC。</span><span class="sxs-lookup"><span data-stu-id="943b1-197">To provide the best-in-class encryption to our customers, Microsoft plans to discontinue support for Transport Layer Security (TLS) versions 1.0 and 1.1 in Office 365 and Office 365 GCC.</span></span>

<span data-ttu-id="943b1-198">我們明白資料的安全性很重要，也承諾透明公開可能會影響 TLS 服務使用的變更。</span><span class="sxs-lookup"><span data-stu-id="943b1-198">We understand that the security of your data is important, and we're committed to transparency about changes that may affect your use of the TLS service.</span></span> <span data-ttu-id="943b1-199">建議所有用戶端伺服器及瀏覽器-伺服器的組合使用 TLS 1.2 (或更新版本) ，以維護 Office 365 服務的連線。</span><span class="sxs-lookup"><span data-stu-id="943b1-199">We recommend that all client-server and browser-server combinations use TLS 1.2 (or a later version) to maintain connection to Office 365 services.</span></span> <span data-ttu-id="943b1-200">您可能必須更新特定的用戶端-伺服器及瀏覽器伺服器組合。</span><span class="sxs-lookup"><span data-stu-id="943b1-200">You might have to update certain client-server and browser-server combinations.</span></span>

<span data-ttu-id="943b1-201">如需 TLS 1.2 支援和服務支援的詳細資訊，請參閱在 [office 365 和 office 365 GCC 中準備 TLS 1.2](../compliance/prepare-tls-1.2-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="943b1-201">For more information about TLS 1.2 support and services support, see [Preparing for TLS 1.2 in Office 365 and Office 365 GCC](../compliance/prepare-tls-1.2-in-office-365.md).</span></span>