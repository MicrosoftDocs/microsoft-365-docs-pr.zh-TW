---
title: 混合新式驗證概述和必要條件，以搭配內部部署商務用 Skype 和 Exchange 伺服器使用
ms.author: kvice
ms.reviewer: smithre4
author: kelleyvice-msft
manager: laurawi
ms.date: 10/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: ef753b32-7251-4c9e-b442-1a5aec14e58d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: 在本文中，您將深入瞭解混合式新式驗證，以及使用內部部署商務用 Skype 和 Exchange 伺服器的必要條件。
ms.openlocfilehash: 33bcf9bde2cda0388160337d3ffe6b81ab94eb12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907525"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a><span data-ttu-id="fd896-103">混合新式驗證概述和使用內部部署商務用 Skype 和 Exchange 伺服器的必要條件</span><span class="sxs-lookup"><span data-stu-id="fd896-103">Hybrid modern authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers</span></span>

<span data-ttu-id="fd896-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="fd896-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fd896-105">_新式驗證_ 是一種身分識別管理的方法，可提供更安全的使用者驗證和授權。</span><span class="sxs-lookup"><span data-stu-id="fd896-105">_Modern Authentication_ is a method of identity management that offers more secure user authentication and authorization.</span></span> <span data-ttu-id="fd896-106">可用於 Office 365 的混合部署商務用 Skype 伺服器內部部署，以及 Exchange 伺服器內部部署，以及分割網域商務用 Skype 混合式部署。</span><span class="sxs-lookup"><span data-stu-id="fd896-106">It's available for Office 365 hybrid deployments of Skype for Business server on-premises and Exchange server on-premises, as well as, split-domain Skype for Business hybrids.</span></span> <span data-ttu-id="fd896-107">本文連結至有關必要條件、設定/停用新式驗證及部分相關用戶端 (ex 的相關檔。</span><span class="sxs-lookup"><span data-stu-id="fd896-107">This article links to related docs about prerequisites, setup/disabling modern authentication, and to some of the related client (ex.</span></span> <span data-ttu-id="fd896-108">) 資訊 Outlook 和 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="fd896-108">Outlook and Skype clients) information.</span></span>

- [<span data-ttu-id="fd896-109">何謂新式驗證？</span><span class="sxs-lookup"><span data-stu-id="fd896-109">What is modern authentication?</span></span>](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [<span data-ttu-id="fd896-110">使用新式驗證時會有什麼變更？</span><span class="sxs-lookup"><span data-stu-id="fd896-110">What changes when I use modern authentication?</span></span>](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [<span data-ttu-id="fd896-111">檢查您的內部部署環境的新式驗證狀態</span><span class="sxs-lookup"><span data-stu-id="fd896-111">Check the modern authentication status of your on-premises environment</span></span>](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [<span data-ttu-id="fd896-112">您是否符合新式驗證必要條件？</span><span class="sxs-lookup"><span data-stu-id="fd896-112">Do you meet modern authentication prerequisites?</span></span>](#do-you-meet-modern-authentication-prerequisites)
- [<span data-ttu-id="fd896-113">開始之前，我還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="fd896-113">What else do I need to know before I begin?</span></span>](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a><span data-ttu-id="fd896-114">何謂新式驗證？</span><span class="sxs-lookup"><span data-stu-id="fd896-114">What is modern authentication?</span></span>
<span data-ttu-id="fd896-115"><a name="BKMK_WhatisModAuth"> </a></span><span class="sxs-lookup"><span data-stu-id="fd896-115"><a name="BKMK_WhatisModAuth"> </a></span></span>

<span data-ttu-id="fd896-116">新式驗證是一項涵蓋在用戶端 (（例如，您的膝上型電腦或電話) 和伺服器）之間的驗證和授權方法的傘條款，以及一些依賴您可能已經熟悉之存取原則的安全性措施。</span><span class="sxs-lookup"><span data-stu-id="fd896-116">Modern authentication is an umbrella term for a combination of authentication and authorization methods between a client (for example, your laptop or your phone) and a server, as well as some security measures that rely on access policies that you may already be familiar with.</span></span> <span data-ttu-id="fd896-117">包括：</span><span class="sxs-lookup"><span data-stu-id="fd896-117">It includes:</span></span>

- <span data-ttu-id="fd896-118">**驗證方法**：多重要素驗證 (MFA) ;智慧卡驗證;以用戶端憑證為基礎的驗證</span><span class="sxs-lookup"><span data-stu-id="fd896-118">**Authentication methods**: Multi-factor authentication (MFA); smart card authentication; client certificate-based authentication</span></span>
- <span data-ttu-id="fd896-119">**授權方法**： Microsoft 在開啟授權 (OAuth 的實施) </span><span class="sxs-lookup"><span data-stu-id="fd896-119">**Authorization methods**: Microsoft's implementation of Open Authorization (OAuth)</span></span>
- <span data-ttu-id="fd896-120">**條件式存取原則**：行動應用程式管理 (MAM) 和 Azure Active Directory (Azure AD) 條件式存取</span><span class="sxs-lookup"><span data-stu-id="fd896-120">**Conditional access policies**: Mobile Application Management (MAM) and Azure Active Directory (Azure AD) Conditional Access</span></span>

<span data-ttu-id="fd896-121">以新式驗證來管理使用者身分識別，可讓系統管理員在保護資源時使用許多不同的工具，並提供更安全的身分識別管理方法給內部部署 (Exchange 及商務用 Skype) 、Exchange 混合式及商務用 Skype 混合式/分割網域案例。</span><span class="sxs-lookup"><span data-stu-id="fd896-121">Managing user identities with modern authentication gives administrators many different tools to use when it comes to securing resources and offers more secure methods of identity management to both on-premises (Exchange and Skype for Business), Exchange hybrid, and Skype for Business hybrid/split-domain scenarios.</span></span>

<span data-ttu-id="fd896-122">請注意，因為商務用 Skype 與 Exchange 密切合作，所以商務用 Skype 用戶端使用者的登入行為會受到 Exchange 新式驗證狀態的影響。</span><span class="sxs-lookup"><span data-stu-id="fd896-122">Be aware that because Skype for Business works closely with Exchange, the login behavior Skype for Business client users will see will be affected by the modern authentication status of Exchange.</span></span> <span data-ttu-id="fd896-123">如果您有商務用 Skype _分割網域的_ 混合架構，而且您有商務用 Skype 線上和商務用 Skype 內部部署，且同時位於這兩個位置的使用者，這也會適用。</span><span class="sxs-lookup"><span data-stu-id="fd896-123">This will also apply if you have a Skype for Business _split-domain_ hybrid architecture, in which you have both Skype for Business Online and Skype for Business on-premises, with users homed in both locations.</span></span>

<span data-ttu-id="fd896-124">如需 Office 365 中新式驗證的詳細資訊，請參閱[Office 365 用戶端應用程式支援-多重要素驗證](microsoft-365-client-support-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="fd896-124">For more information about modern authentication in Office 365, see [Office 365 Client App Support - Multi-factor authentication](microsoft-365-client-support-multi-factor-authentication.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd896-125">到2017年8月為止，所有包含商務用 Skype 線上和 Exchange 線上的新 Office 365 租使用者預設都會啟用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="fd896-125">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online will have modern authentication enabled by default.</span></span> <span data-ttu-id="fd896-126">預先存在的承租人不會變更其預設的 MA 狀態，但是所有的新承租人都會自動支援您所看到的一組擴充的身分識別功能。</span><span class="sxs-lookup"><span data-stu-id="fd896-126">Pre-existing tenants won't have a change in their default MA state, but all new tenants automatically support the expanded set of identity features you see listed above.</span></span> <span data-ttu-id="fd896-127">若要檢查您的 MA 狀態，請參閱 [查看內部部署環境的新式驗證狀態](hybrid-modern-auth-overview.md#BKMK_CheckStatus) 一節。</span><span class="sxs-lookup"><span data-stu-id="fd896-127">To check your MA status, see the [Check the modern authentication status of your on-premises environment](hybrid-modern-auth-overview.md#BKMK_CheckStatus) section.</span></span>

## <a name="what-changes-when-i-use-modern-authentication"></a><span data-ttu-id="fd896-128">使用新式驗證時會有什麼變更？</span><span class="sxs-lookup"><span data-stu-id="fd896-128">What changes when I use modern authentication?</span></span>
<span data-ttu-id="fd896-129"><a name="BKMK_WhatChanges"> </a></span><span class="sxs-lookup"><span data-stu-id="fd896-129"><a name="BKMK_WhatChanges"> </a></span></span>

<span data-ttu-id="fd896-130">搭配內部部署商務用 Skype 或 Exchange 伺服器使用新式驗證時，您仍然會 *驗證* 使用者內部部署，但 *授權* 其存取資源的情景， (如檔案或電子郵件) 變更。</span><span class="sxs-lookup"><span data-stu-id="fd896-130">When using modern authentication with on-premises Skype for Business or Exchange server, you're still *authenticating* users on-premises, but the story of *authorizing* their access to resources (like files or emails) changes.</span></span> <span data-ttu-id="fd896-131">這就是由於新式驗證有關用戶端和伺服器通訊的原因，在 (evoSTS 中設定 MA 結果所採取的步驟，是由 Azure AD) 設定為驗證服務器以商務用 Skype 和 Exchange 伺服器內部部署所使用的安全性權杖服務。</span><span class="sxs-lookup"><span data-stu-id="fd896-131">This is why, though modern authentication is about client and server communication, the steps taken during configuring MA result in evoSTS (a Security Token Service used by Azure AD) being set as Auth Server for Skype for Business and Exchange server on-premises.</span></span>

<span data-ttu-id="fd896-132">對 evoSTS 所做的變更可讓您的內部部署伺服器利用 OAuth (權杖發行) 來授權您的用戶端，也可讓您的內部部署使用雲端 (中常見的安全性方法，例如多重要素驗證) 。</span><span class="sxs-lookup"><span data-stu-id="fd896-132">The change to evoSTS allows your on-premises servers to take advantage of OAuth (token issuance) for authorizing your clients, and also lets your on-premises use security methods common in the cloud (like Multi-factor Authentication).</span></span> <span data-ttu-id="fd896-133">此外，evoSTS 會發出標記，允許使用者要求存取資源，而不提供密碼做為要求的一部分。</span><span class="sxs-lookup"><span data-stu-id="fd896-133">Additionally, the evoSTS issues tokens that allow users to request access to resources without supplying their password as part of the request.</span></span> <span data-ttu-id="fd896-134">不管您的使用者是在線上或內部部署) 的 (所在的位置，不論哪一個位置主控必要的資源，EvoSTS 將成為在設定新式驗證之後，授權使用者和用戶端的核心。</span><span class="sxs-lookup"><span data-stu-id="fd896-134">No matter where your users are homed (of online or on-premises), and no matter which location hosts the needed resource, EvoSTS will become the core of authorizing users and clients once modern authentication is configured.</span></span>

<span data-ttu-id="fd896-135">例如，如果商務用 Skype 用戶端需要存取 Exchange 伺服器以代表使用者取得行事曆資訊，它會使用 Active Directory 驗證程式庫 (ADAL) 來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="fd896-135">For example, if a Skype for Business client needs to access Exchange server to get calendar information on behalf of a user, it uses the Active Directory Authentication Library (ADAL) to do so.</span></span> <span data-ttu-id="fd896-136">ADAL 是一個程式碼庫，其設計目的是讓您的目錄中的安全資源可供使用 OAuth 安全性權杖的用戶端應用程式使用。</span><span class="sxs-lookup"><span data-stu-id="fd896-136">ADAL is a code library designed to make secured resources in your directory available to client applications using OAuth security tokens.</span></span> <span data-ttu-id="fd896-137">ADAL 可與 OAuth 搭配驗證宣告和 exchange token (，而不是密碼) ，以授與使用者對資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="fd896-137">ADAL works with OAuth to verify claims and to exchange tokens (rather than passwords), to grant a user access to a resource.</span></span> <span data-ttu-id="fd896-138">過去，在交易中（如下列所示）中的授權機構（即知道如何驗證使用者宣告及發出必要標記的伺服器），可能是內部部署的安全性權杖服務，甚至是 Active Directory Federation Services。</span><span class="sxs-lookup"><span data-stu-id="fd896-138">In the past, the authority in a transaction like this one -- the server that knows how to validate user claims and issue the needed tokens -- might have been a Security Token Service on-premises, or even Active Directory Federation Services.</span></span> <span data-ttu-id="fd896-139">不過，新式驗證使用 Azure AD 來集中該授權。</span><span class="sxs-lookup"><span data-stu-id="fd896-139">However, modern authentication centralizes that authority by using Azure AD.</span></span>

<span data-ttu-id="fd896-140">這也表示即使您的 Exchange 伺服器和商務用 Skype 環境可能完全在內部部署中，授權伺服器也是線上的，而您的內部部署環境必須能夠建立及維護雲端 (的 Office 365 訂閱連線，以及您的訂閱用來做為其目錄) 的 Azure AD 實例。</span><span class="sxs-lookup"><span data-stu-id="fd896-140">This also means that even though your Exchange server and Skype for Business environments may be entirely on-premises, the authorizing server will be online, and your on-premises environment must have the ability to create and maintain a connection to your Office 365 subscription in the Cloud (and the Azure AD instance that your subscription uses as its directory).</span></span>

<span data-ttu-id="fd896-141">什麼不會變更？</span><span class="sxs-lookup"><span data-stu-id="fd896-141">What doesn't change?</span></span> <span data-ttu-id="fd896-142">不論您是在分割網域混合，還是使用商務用 Skype 和 Exchange 伺服器內部部署，所有使用者都必須先驗證 *內部部署*。</span><span class="sxs-lookup"><span data-stu-id="fd896-142">Whether you're in a split-domain hybrid or using Skype for Business and Exchange server on-premises, all users must first authenticate *on-premises*.</span></span> <span data-ttu-id="fd896-143">在新式驗證的混合式實施中， _Lyncdiscovery_ 和 _自動_ 探索都指向您的內部部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="fd896-143">In a hybrid implementation of modern authentication, _Lyncdiscovery_ and _Autodiscovery_ both point to your on-premises server.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd896-144">如果您需要知道 MA 所支援的特定商務用 Skype 拓撲，已[在這裡記錄](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)。</span><span class="sxs-lookup"><span data-stu-id="fd896-144">If you need to know the specific Skype for Business topologies supported with MA, that's [documented right here](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported).</span></span>

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a><span data-ttu-id="fd896-145">檢查您的內部部署環境的新式驗證狀態</span><span class="sxs-lookup"><span data-stu-id="fd896-145">Check the modern authentication status of your on-premises environment</span></span>
<span data-ttu-id="fd896-146"><a name="BKMK_CheckStatus"> </a></span><span class="sxs-lookup"><span data-stu-id="fd896-146"><a name="BKMK_CheckStatus"> </a></span></span>

<span data-ttu-id="fd896-147">因為新式驗證變更了服務利用 OAuth/S2S 時所使用的授權伺服器，所以您需要知道內部部署商務用 Skype 和 Exchange 環境是否已啟用或停用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="fd896-147">Because modern authentication changes the authorization server used when services leverage OAuth/S2S, you need to know if modern authentication is enabled or disabled for your on-premises Skype for Business and Exchange environments.</span></span> <span data-ttu-id="fd896-148">您可以執行下列 PowerShell 命令，檢查 Exchange 伺服器上的狀態：</span><span class="sxs-lookup"><span data-stu-id="fd896-148">You can check the status on your Exchange servers by running the following PowerShell command:</span></span>

```powershell
Get-OrganizationConfig | ft OAuth*
```

<span data-ttu-id="fd896-149">如果 _OAuth2ClientProfileEnabled_ 屬性的值為 **False**，則會停用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="fd896-149">If the value of the _OAuth2ClientProfileEnabled_ property is **False**, then modern authentication is disabled.</span></span>

<span data-ttu-id="fd896-150">如需 Get-OrganizationConfig Cmdlet 的詳細資訊，請參閱 [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig)。</span><span class="sxs-lookup"><span data-stu-id="fd896-150">For more information about the Get-OrganizationConfig cmdlet, see [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).</span></span>

<span data-ttu-id="fd896-151">您可以執行下列 PowerShell 命令，檢查您的商務用 Skype 伺服器：</span><span class="sxs-lookup"><span data-stu-id="fd896-151">You can check your Skype for Business servers by running the following PowerShell command:</span></span>

```powershell
Get-CSOAuthConfiguration
```

<span data-ttu-id="fd896-152">如果命令傳回空的 _OAuthServers_ 屬性，或是不 **允許** _ClientADALAuthOverride_ 屬性的值，則會停用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="fd896-152">If the command returns an empty _OAuthServers_ property, or if the value of the _ClientADALAuthOverride_ property is not **Allowed**, then modern authentication is disabled.</span></span>

<span data-ttu-id="fd896-153">如需 Get-CsOAuthConfiguration Cmdlet 的詳細資訊，請參閱 [Get-CsOAuthConfiguration](/powershell/module/skype/get-csoauthconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="fd896-153">For more information about the Get-CsOAuthConfiguration cmdlet, see [Get-CsOAuthConfiguration](/powershell/module/skype/get-csoauthconfiguration).</span></span>

## <a name="do-you-meet-modern-authentication-prerequisites"></a><span data-ttu-id="fd896-154">您是否符合新式驗證必要條件？</span><span class="sxs-lookup"><span data-stu-id="fd896-154">Do you meet modern authentication prerequisites?</span></span>

<span data-ttu-id="fd896-155">繼續進行之前，請先確認並檢查清單中的這些專案：</span><span class="sxs-lookup"><span data-stu-id="fd896-155">Verify and check these items off your list before you continue:</span></span>

- <span data-ttu-id="fd896-156">**特定商務用 Skype**</span><span class="sxs-lookup"><span data-stu-id="fd896-156">**Skype for Business specific**</span></span>
  - <span data-ttu-id="fd896-157">所有伺服器都必須有2017累積更新 (CU5) 商務用 Skype Server 2015 或更新版本</span><span class="sxs-lookup"><span data-stu-id="fd896-157">All servers must have May 2017 cumulative update (CU5) for Skype for Business Server 2015 or later</span></span>
    - <span data-ttu-id="fd896-158">**例外** 狀況分支裝置 (SBA) 可以在目前的版本 (根據 Lync 2013) </span><span class="sxs-lookup"><span data-stu-id="fd896-158">**Exception** - Survivability Branch Appliance (SBA) can be on the current version (based on Lync 2013)</span></span>
  - <span data-ttu-id="fd896-159">您的 SIP 網域已新增為 Office 365 中的同盟網域</span><span class="sxs-lookup"><span data-stu-id="fd896-159">Your SIP domain is added as a Federated domain in Office 365</span></span>
  - <span data-ttu-id="fd896-160">所有 SFB 前端都必須有輸出至網際網路的連線，才能 Office 365 驗證 URLs (tcp 443) 和知名憑證根 crl (tcp 80) 列在[Microsoft 365 Office 和 IP 位址範圍](urls-and-ip-address-ranges.md)的「Office 365 通用和 URLs」區段的列56和125中。</span><span class="sxs-lookup"><span data-stu-id="fd896-160">All SFB Front Ends must have connections outbound to the internet, to Office 365 Authentication URLs (TCP 443) and well known certificate root CRLs (TCP 80) listed in Rows 56 and 125 of the 'Microsoft 365 Common and Office' section of [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>

- <span data-ttu-id="fd896-161">**混合 Office 365 環境中的商務用 Skype 內部部署**</span><span class="sxs-lookup"><span data-stu-id="fd896-161">**Skype for Business on-premises in a hybrid Office 365 environment**</span></span>
  - <span data-ttu-id="fd896-162">包含所有執行商務用 Skype Server 2019 之伺服器的商務用 Skype Server 2019 部署。</span><span class="sxs-lookup"><span data-stu-id="fd896-162">A Skype for Business Server 2019 deployment with all servers running Skype for Business Server 2019.</span></span>
  - <span data-ttu-id="fd896-163">包含所有執行商務用 Skype Server 2015 之伺服器的商務用 Skype Server 2015 部署。</span><span class="sxs-lookup"><span data-stu-id="fd896-163">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>
  - <span data-ttu-id="fd896-164">最多兩個不同伺服器版本的部署，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fd896-164">A deployment with a maximum of two different server versions as listed below:</span></span>
    - <span data-ttu-id="fd896-165">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="fd896-165">Skype for Business Server 2015</span></span>
    - <span data-ttu-id="fd896-166">商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="fd896-166">Skype for Business Server 2019</span></span>
  - <span data-ttu-id="fd896-167">所有的商務用 Skype 伺服器都必須已安裝最新的累計更新，請參閱[商務用 Skype Server 更新](/skypeforbusiness/sfb-server-updates)，以尋找並管理所有可用的更新。</span><span class="sxs-lookup"><span data-stu-id="fd896-167">All Skype for Business servers must have the latest cumulative updates installed, see [Skype for Business Server updates](/skypeforbusiness/sfb-server-updates) to find and manage all available updates.</span></span>
  - <span data-ttu-id="fd896-168">混合式環境中沒有 Lync Server 2010 或2013。</span><span class="sxs-lookup"><span data-stu-id="fd896-168">There is no Lync Server 2010 or 2013 in the hybrid environment.</span></span>

>[!NOTE]
><span data-ttu-id="fd896-169">如果您的商務用 Skype 前端伺服器使用 proxy 伺服器進行網際網路存取，則必須在每個前端使用 web.config 檔案的 [設定] 區段中輸入 proxy 伺服器的 IP 及埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fd896-169">If your Skype for Business front-end servers use a proxy server for Internet access, the proxy server IP and Port number used must be entered in the configuration section of the web.config file for each front end.</span></span>

- <span data-ttu-id="fd896-170">C:\Program Files \ 商務用 Skype Server 2015 \ Web Components\Web ticket\int\web.config</span><span class="sxs-lookup"><span data-stu-id="fd896-170">C:\Program Files\Skype for Business Server 2015\Web Components\Web ticket\int\web.config</span></span>
- <span data-ttu-id="fd896-171">C:\Program Files \ 商務用 Skype Server 2015 \ Web Components\Web ticket\ext\web.config</span><span class="sxs-lookup"><span data-stu-id="fd896-171">C:\Program Files\Skype for Business Server 2015\Web Components\Web ticket\ext\web.config</span></span>

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <proxy
        proxyaddress="https://192.168.100.60:8080"
        bypassonlocal="true" />
    </defaultProxy>
  </system.net>
</configuration>
```

> [!IMPORTANT]
> <span data-ttu-id="fd896-172">請務必訂閱 rss 摘要，以取得[Office 365 URLs 及 IP 位址範圍](urls-and-ip-address-ranges.md)，以最新的必要 URLs 清單保持最新。</span><span class="sxs-lookup"><span data-stu-id="fd896-172">Be sure to subscribe to the RSS feed for [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md) to stay current with the latest listings of required URLs.</span></span>

- <span data-ttu-id="fd896-173">**特定 Exchange Server**</span><span class="sxs-lookup"><span data-stu-id="fd896-173">**Exchange Server specific**</span></span>
  - <span data-ttu-id="fd896-174">您使用的是 Exchange server 2013 CU19，且 Exchange 伺服器 2016 CU8 和更新，或是 Exchange Server 2019 CU1 和向上。</span><span class="sxs-lookup"><span data-stu-id="fd896-174">You're using either Exchange server 2013 CU19 and up, Exchange server 2016 CU8 and up, or Exchange Server 2019 CU1 and up.</span></span>
  - <span data-ttu-id="fd896-175">環境中沒有 Exchange 伺服器2010。</span><span class="sxs-lookup"><span data-stu-id="fd896-175">There is no Exchange server 2010 in the environment.</span></span>
  - <span data-ttu-id="fd896-176">未設定 SSL 卸載。</span><span class="sxs-lookup"><span data-stu-id="fd896-176">SSL Offloading is not configured.</span></span> <span data-ttu-id="fd896-177">支援 SSL 終止和重新加密。</span><span class="sxs-lookup"><span data-stu-id="fd896-177">SSL termination and re-encryption is supported.</span></span>
  - <span data-ttu-id="fd896-178">在您的環境使用 proxy 伺服器基礎結構以允許伺服器連線至網際網路時，請確定所有 Exchange 伺服器都具有[InternetWebProxy](/powershell/module/exchange/set-exchangeserver)屬性定義的 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="fd896-178">In the event your environment utilizes a proxy server infrastructure to allow servers to connect to the Internet, be sure all Exchange servers have the proxy server defined in the [InternetWebProxy](/powershell/module/exchange/set-exchangeserver) property.</span></span>

- <span data-ttu-id="fd896-179">**混合 Office 365 環境中的 Exchange Server 內部部署**</span><span class="sxs-lookup"><span data-stu-id="fd896-179">**Exchange Server on-premises in a hybrid Office 365 environment**</span></span>

  - <span data-ttu-id="fd896-180">如果您使用 Exchange Server 2013，至少有一部伺服器必須安裝信箱和用戶端存取伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="fd896-180">If you are using Exchange Server 2013, at least one server must have the Mailbox and Client Access server roles installed.</span></span> <span data-ttu-id="fd896-181">雖然您可以在不同的伺服器上安裝信箱和用戶端存取角色，我們強烈建議您在同一部伺服器上安裝這兩種角色，以提供額外的可靠性並改善效能。</span><span class="sxs-lookup"><span data-stu-id="fd896-181">While it is possible to install the Mailbox and Client Access roles on separate servers, we strongly recommend that you install both roles on the same server to provide additional reliability and improved performance.</span></span>
  - <span data-ttu-id="fd896-182">如果您使用 Exchange server 2016 或更新版本，至少有一部伺服器必須已安裝信箱伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="fd896-182">If you are using Exchange server 2016 or later version, at least one server must have the Mailbox server role installed.</span></span>
  - <span data-ttu-id="fd896-183">混合式環境中沒有 Exchange 伺服器2007或2010。</span><span class="sxs-lookup"><span data-stu-id="fd896-183">There is no Exchange server 2007 or 2010 in the Hybrid environment.</span></span>
  - <span data-ttu-id="fd896-184">所有的 Exchange 伺服器都必須已安裝最新的累計更新，請參閱[Upgrade Exchange to all 累計更新](/exchange/plan-and-deploy/install-cumulative-updates)，以尋找並管理所有可用的更新。</span><span class="sxs-lookup"><span data-stu-id="fd896-184">All Exchange servers must have the latest cumulative updates installed, see [Upgrade Exchange to the latest Cumulative Updates](/exchange/plan-and-deploy/install-cumulative-updates) to find and manage all available updates.</span></span>

- <span data-ttu-id="fd896-185">**Exchange 用戶端和通訊協定需求**</span><span class="sxs-lookup"><span data-stu-id="fd896-185">**Exchange client and protocol requirements**</span></span>

    <span data-ttu-id="fd896-186">新式驗證的可用性是由用戶端、通訊協定和設定的組合所決定。</span><span class="sxs-lookup"><span data-stu-id="fd896-186">The availability of modern authentication is determined by the combination of the client, protocol, and configuration.</span></span> <span data-ttu-id="fd896-187">如果用戶端、通訊協定及（或）設定不支援新式驗證，則用戶端將繼續利用舊版驗證。</span><span class="sxs-lookup"><span data-stu-id="fd896-187">If modern authentication is not supported by the client, protocol, and/or configuration, then the client will continue to leverage legacy authentication.</span></span>
  
    <span data-ttu-id="fd896-188">在環境中啟用新式驗證時，下列用戶端和通訊協定支援使用內部部署 Exchange 新式驗證：</span><span class="sxs-lookup"><span data-stu-id="fd896-188">The following clients and protocols support modern authentication with on-premises Exchange when modern authentication is enabled in the environment:</span></span>

  |<span data-ttu-id="fd896-189">**用戶端**</span><span class="sxs-lookup"><span data-stu-id="fd896-189">**Clients**</span></span>|<span data-ttu-id="fd896-190">**主要通訊協定**</span><span class="sxs-lookup"><span data-stu-id="fd896-190">**Primary Protocol**</span></span>|<span data-ttu-id="fd896-191">**附註**</span><span class="sxs-lookup"><span data-stu-id="fd896-191">**Notes**</span></span>|
  |:-----|:-----|:-----|
  |<span data-ttu-id="fd896-192">Outlook 2013 和更新版本</span><span class="sxs-lookup"><span data-stu-id="fd896-192">Outlook 2013 and later</span></span>  <br/> |<span data-ttu-id="fd896-193">MAPI over HTTP</span><span class="sxs-lookup"><span data-stu-id="fd896-193">MAPI over HTTP</span></span>  <br/> |<span data-ttu-id="fd896-194">必須在 Exchange 內啟用 MAPI over HTTP，才能利用這些用戶端的新式驗證 (通常是針對 Exchange 2013 Service Pack 1 和更新版本中的新安裝啟用或設為 True) ;如需詳細資訊[，請參閱新式驗證如何運作 Office 2013 和 Office 2016 用戶端應用程式](modern-auth-for-office-2013-and-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="fd896-194">MAPI over HTTP must be enabled within Exchange in order to leverage modern authentication with these clients (usually enabled or True for new installs of Exchange 2013 Service Pack 1 and above); for more information see [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>  <br/> <span data-ttu-id="fd896-195">確定您執行的是最小必要組建 Outlook;請參閱[使用 Windows Installer (MSI) 之 Outlook 版本的最新更新](/officeupdates/outlook-updates-msi)。</span><span class="sxs-lookup"><span data-stu-id="fd896-195">Ensure you are running the minimum required build of Outlook; see [Latest updates for versions of Outlook that use Windows Installer (MSI)](/officeupdates/outlook-updates-msi).</span></span>  <br/> |
  |<span data-ttu-id="fd896-196">Mac 版 Outlook 2016 和更新版本</span><span class="sxs-lookup"><span data-stu-id="fd896-196">Outlook 2016 for Mac and later</span></span>  <br/> |<span data-ttu-id="fd896-197">Exchange Web 服務</span><span class="sxs-lookup"><span data-stu-id="fd896-197">Exchange Web Services</span></span>  <br/> |  <br/> |
  |<span data-ttu-id="fd896-198">iOS 和 Android 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="fd896-198">Outlook for iOS and Android</span></span>  <br/> | <span data-ttu-id="fd896-199">Microsoft sync 技術</span><span class="sxs-lookup"><span data-stu-id="fd896-199">Microsoft sync technology</span></span> <br/> |<span data-ttu-id="fd896-200">如需詳細資訊，請參閱[使用混合式新式驗證與適用于 iOS 和 Android 的 Outlook](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) 。</span><span class="sxs-lookup"><span data-stu-id="fd896-200">See [Using hybrid Modern Authentication with Outlook for iOS and Android](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) for more information.</span></span>  <br/> |
  |<span data-ttu-id="fd896-201">Exchange ActiveSync 用戶端 (例如，iOS11 Mail) </span><span class="sxs-lookup"><span data-stu-id="fd896-201">Exchange ActiveSync clients (e.g., iOS11 Mail)</span></span>  <br/> |<span data-ttu-id="fd896-202">Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="fd896-202">Exchange ActiveSync</span></span>  <br/> |<span data-ttu-id="fd896-203">針對支援新式驗證的 Exchange ActiveSync 用戶端，您必須重新建立設定檔，才能從基本驗證切換為新式驗證。</span><span class="sxs-lookup"><span data-stu-id="fd896-203">For Exchange ActiveSync clients that support modern authentication, you must recreate the profile in order to switch from basic authentication to modern authentication.</span></span>  <br/> |

    <span data-ttu-id="fd896-204">未列出的用戶端和（或）通訊協定 (例如，POP3) 不支援搭配內部部署 Exchange 的新式驗證，繼續利用舊版驗證機制，即使已在環境中啟用新式驗證之後。</span><span class="sxs-lookup"><span data-stu-id="fd896-204">Clients and/or protocols that are not listed (e.g., POP3) do not support modern authentication with on-premises Exchange and continue to leverage legacy authentication mechanisms even after modern authentication is enabled in the environment.</span></span>

- <span data-ttu-id="fd896-205">**一般必要條件**</span><span class="sxs-lookup"><span data-stu-id="fd896-205">**General prerequisites**</span></span>
  - <span data-ttu-id="fd896-206">資源樹系案例會需要與帳戶樹系進行雙向信任，以確保混合式新式驗證要求期間執行適當的 SID 查閱。</span><span class="sxs-lookup"><span data-stu-id="fd896-206">Resource forest scenarios will require a two-way trust with the account forest to ensure proper SID lookups are performed during hybrid modern authentication requests.</span></span> 
  - <span data-ttu-id="fd896-207">如果您使用 AD FS，則同盟應具備 Windows 2012 R2 AD FS 3.0 和更新版本。</span><span class="sxs-lookup"><span data-stu-id="fd896-207">If you use AD FS, you should have Windows 2012 R2 AD FS 3.0 and above for federation.</span></span>
  - <span data-ttu-id="fd896-208">您的身分識別設定是 Azure AD 連線所支援的任何類型，例如密碼雜湊同步處理、傳遞驗證，以及 Office 365 所支援的內部部署 STS。</span><span class="sxs-lookup"><span data-stu-id="fd896-208">Your identity configurations are any of the types supported by Azure AD Connect, such as password hash sync, pass-through authentication, and on-premises STS supported by Office 365.</span></span>
  - <span data-ttu-id="fd896-209">您已設定 Azure AD 連線，且可在使用者複寫及同步處理時運作。</span><span class="sxs-lookup"><span data-stu-id="fd896-209">You have Azure AD Connect configured and functioning for user replication and sync.</span></span>
  - <span data-ttu-id="fd896-210">您已驗證使用內部部署與 Office 365 環境之間的 Exchange 傳統混合拓撲模式設定混合。</span><span class="sxs-lookup"><span data-stu-id="fd896-210">You have verified that hybrid is configured using Exchange Classic Hybrid Topology mode between your on-premises and Office 365 environment.</span></span> <span data-ttu-id="fd896-211">Exchange 混合式的官方支援陳述說，您必須是目前的 cu 或目前的 cu-1。</span><span class="sxs-lookup"><span data-stu-id="fd896-211">Official support statement for Exchange hybrid says you must have either current CU or current CU - 1.</span></span>
    > [!NOTE]
    > <span data-ttu-id="fd896-212">[混合式代理程式](/exchange/hybrid-deployment/hybrid-agent)不支援混合式新式驗證。</span><span class="sxs-lookup"><span data-stu-id="fd896-212">Hybrid modern authentication is not supported with the [Hybrid Agent](/exchange/hybrid-deployment/hybrid-agent).</span></span>

  - <span data-ttu-id="fd896-213">請確定內部部署測試使用者以及位於 Office 365 的混合式測試使用者可以登入商務用 Skype 桌面用戶端 (如果想要使用新式驗證搭配 Skype) 和 Microsoft Outlook (（如果您想要搭配 Exchange) 使用新式驗證）。</span><span class="sxs-lookup"><span data-stu-id="fd896-213">Make sure both an on-premises test user, as well as a hybrid test user homed in Office 365, can login to the Skype for Business desktop client (if you want to use modern authentication with Skype) and Microsoft Outlook (if you want to use modern authentication with Exchange).</span></span>

## <a name="what-else-do-i-need-to-know-before-i-begin"></a><span data-ttu-id="fd896-214">開始之前，我還需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="fd896-214">What else do I need to know before I begin?</span></span>
<span data-ttu-id="fd896-215"><a name="BKMK_Whatelse"> </a></span><span class="sxs-lookup"><span data-stu-id="fd896-215"><a name="BKMK_Whatelse"> </a></span></span>

- <span data-ttu-id="fd896-216">內部部署伺服器的所有案例都包括設定新式驗證內部部署 (事實上，針對商務用 Skype，有支援的拓撲清單) 因此，負責驗證和授權的伺服器是在 Microsoft 雲端 (Azure AD Security Token Service 中，稱為「evoSTS ' ) ，並更新 URLs 或商務用 Skype 的內部部署安裝所使用的命名空間的 Azure ad。</span><span class="sxs-lookup"><span data-stu-id="fd896-216">All the scenarios for on-premises servers involve setting up modern authentication on-premises (in fact, for Skype for Business there is a list of supported topologies) so that the server responsible for authentication and authorization is in the Microsoft Cloud (Azure AD's security token service, called 'evoSTS'), and updating Azure AD about the URLs or namespaces used by your on-premises installation of either Skype for Business or Exchange.</span></span> <span data-ttu-id="fd896-217">因此，內部部署伺服器會採用 Microsoft Cloud 相依性。</span><span class="sxs-lookup"><span data-stu-id="fd896-217">Therefore, on-premises servers take on a Microsoft Cloud dependency.</span></span> <span data-ttu-id="fd896-218">採取此動作可能會看作是「混合驗證」。</span><span class="sxs-lookup"><span data-stu-id="fd896-218">Taking this action could be considered configuring 'hybrid auth'.</span></span>
- <span data-ttu-id="fd896-219">本文與其他專案連結，可協助您選擇支援的新式驗證拓撲 (只適用于商務用 Skype) 和說明如何針對 Exchange 內部部署和商務用 Skype 內部部署執行新式驗證的步驟。</span><span class="sxs-lookup"><span data-stu-id="fd896-219">This article links out to others that will help you choose supported modern authentication topologies (necessary only for Skype for Business), and how-to articles that outline the setup steps, or steps to disable modern authentication, for Exchange on-premises and Skype for Business on-premises.</span></span> <span data-ttu-id="fd896-220">如果您想要在您的伺服器環境中使用新式驗證，請在瀏覽器中，將此頁面最愛。</span><span class="sxs-lookup"><span data-stu-id="fd896-220">Favorite this page in your browser if you're going to need a home-base for using modern authentication in your server environment.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fd896-221">相關主題</span><span class="sxs-lookup"><span data-stu-id="fd896-221">Related Topics</span></span>
<span data-ttu-id="fd896-222"><a name="BKMK_URLListforMA"> </a></span><span class="sxs-lookup"><span data-stu-id="fd896-222"><a name="BKMK_URLListforMA"> </a></span></span>

- [<span data-ttu-id="fd896-223">如何設定 Exchange Server 內部部署以使用新式驗證</span><span class="sxs-lookup"><span data-stu-id="fd896-223">How to configure Exchange Server on-premises to use Modern Authentication</span></span>](configure-exchange-server-for-hybrid-modern-authentication.md)
- [<span data-ttu-id="fd896-224">新式驗證支援的商務用 Skype 拓撲</span><span class="sxs-lookup"><span data-stu-id="fd896-224">Skype for Business topologies supported with Modern Authentication</span></span>](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
- [<span data-ttu-id="fd896-225">如何設定商務用 Skype 內部部署以使用新式驗證</span><span class="sxs-lookup"><span data-stu-id="fd896-225">How to configure Skype for Business on-premises to use Modern Authentication</span></span>](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [<span data-ttu-id="fd896-226">從商務用 Skype 與 Exchange 移除或停用混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="fd896-226">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)