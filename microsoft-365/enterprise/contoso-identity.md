---
title: Contoso Corporation 的身分識別
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何利用身分識別即服務 (IDaaS)，為其員工提供雲端式驗證，為其合作夥伴和客戶提供同盟驗證。
ms.openlocfilehash: 77c90740fd39080ccc204552bc8407aa107e354a
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633361"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="8e1fe-103">Contoso Corporation 的身分識別</span><span class="sxs-lookup"><span data-stu-id="8e1fe-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="8e1fe-104">Microsoft 在具有 Azure Active Directory (AD) 的雲端供應項目之間提供身分識別即服務 (IDaaS)。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-104">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="8e1fe-105">為了採用 Microsoft 365 企業版，Contoso 的 IDaaS 解決方案必須運用其內部部署的身分識別提供者，並且仍然包含使用其現有信任的第三方身分識別提供者的同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-105">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="8e1fe-106">Contoso 的 Active Directory Domain Services 樹系</span><span class="sxs-lookup"><span data-stu-id="8e1fe-106">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="8e1fe-107">Contoso 在 contoso.com 上會使用單一 Active Directory Domain Services (AD DS) 樹系，以及七個分屬全球各地區的子網域。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="8e1fe-108">總部、地區中心辦公室和衛星辦公室包含用於本機驗證與授權的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="8e1fe-109">這是 Contoso 樹系，具有包含區域中樞之不同世界各地的區域網域。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-109">Here is the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Contoso 的樹系和世界各地的網域](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="8e1fe-111">Contoso 希望在 contoso.com 樹系中使用帳戶和群組，以對其 Microsoft 365 工作負載和服務進行驗證及授權。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-111">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="8e1fe-112">Contoso 的同盟驗證基礎結構</span><span class="sxs-lookup"><span data-stu-id="8e1fe-112">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="8e1fe-113">Contoso 允許︰</span><span class="sxs-lookup"><span data-stu-id="8e1fe-113">Contoso allows:</span></span>

- <span data-ttu-id="8e1fe-114">客戶使用自己的 Microsoft、Facebook 或 Google 郵件帳戶登入其公用網站。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="8e1fe-115">廠商及合作夥伴使用自己的 LinkedIn、Salesforce 或 Google 郵件帳戶登入外部網路。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="8e1fe-p103">這是 Contoso DMZ，其中包含公用網站、合作夥伴外部網路，和一組 Active Directory 同盟服務 (AD FS) 伺服器。DMZ 會連線到網際網路，其中包含客戶、合作夥伴和網際網路服務。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-p103">Here is the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Contoso 對於客戶和合作夥伴同盟驗證的支援](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="8e1fe-119">DMZ 中的 AD FS 伺服器可協助依其身分識別提供者來驗證客戶的認證以存取公用網站，以及驗證合作夥伴的認證以存取合作夥伴外部網路。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-119">AD FS servers in the DMZ facilitate the authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="8e1fe-p104">Contoso 決定要保留此基礎結構，並讓它專屬於客戶和合作夥伴驗證。Contoso 的身分識別架構師會調查此基礎結構到 Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) 與 [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) 解決方案的轉換。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="8e1fe-122">用於雲端式驗證的混合式身分識別和密碼雜湊同步</span><span class="sxs-lookup"><span data-stu-id="8e1fe-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="8e1fe-123">Contoso 公司想要使用其內部部署 AD DS 樹系來對 Microsoft 365 雲端資源進行驗證。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-123">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="8e1fe-124">其決定使用密碼雜湊同步 (PHS)。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-124">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="8e1fe-125">PHS 會同步處理內部部署 AD DS 樹系與 Microsoft 365 企業版訂閱中的 Azure AD 租用戶，並複製使用者和群組帳戶以及雜湊版本的使用者帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="8e1fe-126">為了執行後續的目錄同步處理，Contoso 已在巴黎資料中心的伺服器上部署 Azure AD Connect 工具。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-126">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> 

<span data-ttu-id="8e1fe-127">這是執行 Azure AD Connect 的伺服器正在輪詢 Contoso AD 樹系是否有變更，然後將這些變更與 Azure AD 租用戶進行同步。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-127">Here is the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contoso 的 PHS 目錄同步處理基礎結構](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="8e1fe-129">身分識別和裝置存取的條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="8e1fe-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="8e1fe-130">Contoso 已針對三個保護層級建立一組 Azure AD 和 Intune 的[條件式存取原則](identity-access-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="8e1fe-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="8e1fe-131">**基本**保護適用於所有使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="8e1fe-131">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="8e1fe-132">**機密**保護適用於高階領導人和主管人員</span><span class="sxs-lookup"><span data-stu-id="8e1fe-132">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="8e1fe-133">**高管制**保護適用於財務、法務和研究部門中的特定使用者，他們需存取高管制的資料</span><span class="sxs-lookup"><span data-stu-id="8e1fe-133">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="8e1fe-134">這是 Contoso 身分識別及裝置條件式存取原則的結果集合。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-134">Here is Contoso's resulting set of identity and device Conditional Access policies.</span></span>

![Contoso 的身分識別及裝置條件式存取原則](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="8e1fe-136">下一步</span><span class="sxs-lookup"><span data-stu-id="8e1fe-136">Next step</span></span>

<span data-ttu-id="8e1fe-137">[了解](contoso-win10.md) Contoso 如何使用 Microsoft Endpoint Configuration Manager 基礎結構，在整個組織部署及保留目前的 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="8e1fe-137">[Learn](contoso-win10.md) how Contoso is leveraging its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e1fe-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8e1fe-138">See also</span></span>

[<span data-ttu-id="8e1fe-139">Microsoft 365 企業版的身分識別</span><span class="sxs-lookup"><span data-stu-id="8e1fe-139">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="8e1fe-140">部署指南</span><span class="sxs-lookup"><span data-stu-id="8e1fe-140">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8e1fe-141">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="8e1fe-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
