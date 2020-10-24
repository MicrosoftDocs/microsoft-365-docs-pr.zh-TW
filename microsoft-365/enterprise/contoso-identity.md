---
title: Contoso Corporation 的身分識別
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何利用身分識別即服務 (IDaaS)，為其員工提供雲端式驗證，為其合作夥伴和客戶提供同盟驗證。
ms.openlocfilehash: dea0f53ef1c3fdc2ea32256303c6120c614c904d
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754633"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="be5bd-103">Contoso Corporation 的身分識別</span><span class="sxs-lookup"><span data-stu-id="be5bd-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="be5bd-104">Microsoft 透過 Azure Active Directory (Azure AD) ，以服務 (IDaaS) 所有雲端產品。</span><span class="sxs-lookup"><span data-stu-id="be5bd-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="be5bd-105">為了採用 Microsoft 365 for enterprise，Contoso IDaaS 解決方案必須使用內部部署身分識別提供者，並包含與其現有信任的協力廠商身分識別提供者的同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="be5bd-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="be5bd-106">Contoso Active Directory 網域服務樹系</span><span class="sxs-lookup"><span data-stu-id="be5bd-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="be5bd-107">Contoso 會使用單一 Active Directory 網域服務，將 contoso com 的單一 Active Directory 網域 (服務) 樹系 \. 與7個子域搭配使用，一個用於世界各地區的一個。</span><span class="sxs-lookup"><span data-stu-id="be5bd-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="be5bd-108">總部、地區中心辦公室和衛星辦公室包含用於本機驗證與授權的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="be5bd-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="be5bd-109">以下是 Contoso 樹系，具有地區性網域，包含區域中樞的不同部分。</span><span class="sxs-lookup"><span data-stu-id="be5bd-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Contoso 的樹系和世界各地的網域](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="be5bd-111">Contoso 決定使用 contoso com 樹系中的帳戶和群組 \. ，以進行 Microsoft 365 工作負載和服務的驗證和授權。</span><span class="sxs-lookup"><span data-stu-id="be5bd-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="be5bd-112">Contoso 同盟驗證基礎結構</span><span class="sxs-lookup"><span data-stu-id="be5bd-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="be5bd-113">Contoso 允許︰</span><span class="sxs-lookup"><span data-stu-id="be5bd-113">Contoso allows:</span></span>

- <span data-ttu-id="be5bd-114">客戶可以使用其 Microsoft、Facebook 或 Google 郵件帳戶登入公司的公開網站。</span><span class="sxs-lookup"><span data-stu-id="be5bd-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="be5bd-115">廠商和協力廠商使用其 LinkedIn、Salesforce 或 Google 郵件帳戶登入公司的外部網路。</span><span class="sxs-lookup"><span data-stu-id="be5bd-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="be5bd-p103">以下是包含公用網站、第三個外部網路，以及一組 Active Directory Federation Services (AD FS) 伺服器的 Contoso DMZ。DMZ 會連線到包含客戶、合作夥伴和網際網路服務的網際網路。</span><span class="sxs-lookup"><span data-stu-id="be5bd-p103">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Contoso 支援客戶與合作夥伴的同盟驗證](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="be5bd-119">在 DMZ 中的 AD FS 伺服器，可協助其身分識別提供者驗證客戶認證，以存取公用網站和夥伴驗證，以存取合作夥伴外部網路。</span><span class="sxs-lookup"><span data-stu-id="be5bd-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="be5bd-p104">Contoso 決定保留這種基礎結構，並將其專用於客戶及夥伴驗證。Contoso 身分識別架構師正在調查此基礎結構對 Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) 和 [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) 方案的轉換。</span><span class="sxs-lookup"><span data-stu-id="be5bd-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication. Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="be5bd-122">用於雲端式驗證的混合式身分識別和密碼雜湊同步</span><span class="sxs-lookup"><span data-stu-id="be5bd-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="be5bd-123">Contoso 想要將其內部部署 AD DS 樹系用於 Microsoft 365 雲端資源的驗證。</span><span class="sxs-lookup"><span data-stu-id="be5bd-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="be5bd-124">它決定使用密碼雜湊同步處理 (PHS) 。</span><span class="sxs-lookup"><span data-stu-id="be5bd-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="be5bd-125">PHS 會同步處理內部部署 AD DS 樹系與其 Microsoft 365 for enterprise 訂閱的 Azure AD 租使用者，並複製使用者和群組帳戶，以及散列版本的使用者帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="be5bd-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="be5bd-126">為了進行目錄同步處理，Contoso 已在其巴黎 datacenter 中的伺服器上部署 Azure AD Connect 工具。</span><span class="sxs-lookup"><span data-stu-id="be5bd-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="be5bd-127">以下是執行 Azure AD Connect 的伺服器輪詢 Contoso AD DS 樹系的變更，然後與 Azure AD 租使用者同步處理這些變更。</span><span class="sxs-lookup"><span data-stu-id="be5bd-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contoso PHS 目錄同步處理基礎結構](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="be5bd-129">身分識別和裝置存取的條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="be5bd-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="be5bd-130">Contoso 已針對三個保護層級建立一組 Azure AD 和 Intune 的[條件式存取原則](identity-access-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="be5bd-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="be5bd-131">*基準* 保護適用于所有使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="be5bd-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="be5bd-132">*機密* 保護適用于資深領導人和高層人員。</span><span class="sxs-lookup"><span data-stu-id="be5bd-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="be5bd-133">「*高管制*防護」適用于財務、法律和研究部門中具有高管制資料存取權的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="be5bd-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="be5bd-134">以下是 Contoso 身分識別和裝置條件式存取原則的結果集合。</span><span class="sxs-lookup"><span data-stu-id="be5bd-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Contoso 的身分識別及裝置條件式存取原則](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="be5bd-136">下一步</span><span class="sxs-lookup"><span data-stu-id="be5bd-136">Next step</span></span>

<span data-ttu-id="be5bd-137">瞭解 Contoso 如何使用其 Microsoft 端點 Configuration Manager 基礎結構，在其整個組織中 [部署及保留目前的 Windows 10 企業版](contoso-win10.md) 。</span><span class="sxs-lookup"><span data-stu-id="be5bd-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="be5bd-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="be5bd-138">See also</span></span>

[<span data-ttu-id="be5bd-139">Microsoft 365 的身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="be5bd-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="be5bd-140">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="be5bd-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="be5bd-141">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="be5bd-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
