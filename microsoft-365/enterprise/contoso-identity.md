---
title: Contoso Corporation 的身分識別
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/17/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何利用身分識別即服務 (IDaaS)，為其員工提供雲端式驗證，為其合作夥伴和客戶提供同盟驗證。
ms.openlocfilehash: bcd83eaafb5df86d9a660aeb74b2e97f7bdc6b7b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277572"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="7af99-103">Contoso Corporation 的身分識別</span><span class="sxs-lookup"><span data-stu-id="7af99-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="7af99-104">**摘要：** Contoso 如何利用識別即服務 (IDaaS)，為其員工提供雲端式驗證，為其合作夥伴和客戶提供同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="7af99-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="7af99-105">Microsoft 在具有 Azure Active Directory (AD) 的雲端供應項目之間提供身分識別即服務 (IDaaS)。</span><span class="sxs-lookup"><span data-stu-id="7af99-105">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="7af99-106">為了採用 Microsoft 365 企業版，Contoso 的 IDaaS 解決方案必須運用其內部部署的身分識別提供者，並且仍然包含使用其現有信任的第三方身分識別提供者的同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="7af99-106">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (AD). To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="7af99-107">Contoso 的 Active Directory Domain Services 樹系</span><span class="sxs-lookup"><span data-stu-id="7af99-107">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="7af99-108">Contoso 在 contoso.com 上會使用單一 Active Directory Domain Services (AD DS) 樹系，以及七個分屬全球各地區的子網域。</span><span class="sxs-lookup"><span data-stu-id="7af99-108">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="7af99-109">總部、地區中心辦公室和衛星辦公室包含用於本機驗證與授權的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="7af99-109">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="7af99-110">圖 1 顯示 Contoso 樹系，具有包含區域中樞之不同世界各地的區域網域。</span><span class="sxs-lookup"><span data-stu-id="7af99-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="7af99-111">**圖 1：Contoso 的樹系和世界各地的網域**</span><span class="sxs-lookup"><span data-stu-id="7af99-111">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="7af99-112">Contoso 希望在 contoso.com 樹系中使用帳戶和群組，以對其 Microsoft 365 工作負載和服務進行驗證及授權。</span><span class="sxs-lookup"><span data-stu-id="7af99-112">Contoso wants to use the accounts and groups in the contoso.com forest for authentication and authorization for its cloud-based apps and workloads.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="7af99-113">Contoso 的同盟驗證基礎結構</span><span class="sxs-lookup"><span data-stu-id="7af99-113">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="7af99-114">Contoso 允許︰</span><span class="sxs-lookup"><span data-stu-id="7af99-114">Contoso allows:</span></span>

- <span data-ttu-id="7af99-115">客戶使用自己的 Microsoft、Facebook 或 Google 郵件帳戶登入其公用網站。</span><span class="sxs-lookup"><span data-stu-id="7af99-115">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="7af99-116">廠商及合作夥伴使用自己的 LinkedIn、Salesforce 或 Google 郵件帳戶登入外部網路。</span><span class="sxs-lookup"><span data-stu-id="7af99-116">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="7af99-p103">圖 2 顯示 Contoso DMZ，其中包含公用網站、合作夥伴外部網路，和一組 Active Directory 同盟服務 (AD FS) 伺服器。DMZ 會連線到網際網路，其中包含客戶、合作夥伴和網際網路服務。</span><span class="sxs-lookup"><span data-stu-id="7af99-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="7af99-119">**圖 2：Contoso 對於客戶和合作夥伴同盟驗證的支援**</span><span class="sxs-lookup"><span data-stu-id="7af99-119">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="7af99-120">DMZ 中的 AD FS 伺服器會驗證客戶的認證以存取公用網站，以及驗證合作夥伴的憑證以存取合作夥伴外部網路。</span><span class="sxs-lookup"><span data-stu-id="7af99-120">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="7af99-p104">Contoso 決定要保留此基礎結構，並讓它專屬於客戶和合作夥伴驗證。Contoso 的身分識別工程師會調查此基礎結構到 Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) 與 [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) 解決方案的轉換。</span><span class="sxs-lookup"><span data-stu-id="7af99-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="7af99-123">用於雲端式驗證的混合式身分識別和密碼雜湊同步</span><span class="sxs-lookup"><span data-stu-id="7af99-123">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="7af99-124">Contoso 公司想要使用其內部部署 AD DS 樹系來對 Microsoft 365 雲端資源進行驗證。</span><span class="sxs-lookup"><span data-stu-id="7af99-124">Contoso wanted to leverage its on-premises Windows Server AD forest for authentication to Microsoft 365 cloud resources. It decided on pass-through authentication (PTA) with password hash synchronization (PHS).</span></span> <span data-ttu-id="7af99-125">其決定使用密碼雜湊同步 (PHS)。</span><span class="sxs-lookup"><span data-stu-id="7af99-125">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="7af99-126">PHS 會同步處理內部部署 AD DS 樹系與 Microsoft 365 企業版訂閱中的 Azure AD 租用戶，並複製使用者和群組帳戶以及雜湊版本的使用者帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="7af99-126">PHS synchronizes the on-premises Windows Server AD forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords. Contoso decided on PHS to provide an alternate method of authentication directly with the Azure AD tenant in the event that PTA is not available.</span></span> 

<span data-ttu-id="7af99-127">為了執行後續的目錄同步處理，Contoso 已在巴黎資料中心的伺服器上部署 Azure AD Connect 工具。</span><span class="sxs-lookup"><span data-stu-id="7af99-127">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter. Figure 4 shows the server running Azure AD Connect polling the Contoso Windows Server AD forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span> <span data-ttu-id="7af99-128">圖 3 顯示執行 Azure AD Connect 的伺服器正在輪詢 Contoso AD 樹系是否有變更，然後將這些變更與 Azure AD 租用戶進行同步。</span><span class="sxs-lookup"><span data-stu-id="7af99-128">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter. Figure 4 shows the server running Azure AD Connect polling the Contoso Windows Server AD forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="7af99-129">**圖 3：Contoso 的 PHS 目錄同步處理基礎結構**</span><span class="sxs-lookup"><span data-stu-id="7af99-129">**Figure 4: Contoso's PHS directory synchronization infrastructure**</span></span>


## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="7af99-130">身分識別和裝置存取的條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="7af99-130">Conditional access policies for identity and device access</span></span>

<span data-ttu-id="7af99-131">Contoso 已針對三個保護層級建立一組 Azure AD 和 Intune 的[條件式存取原則](identity-access-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="7af99-131">Contoso created a set of Azure AD and Intune [conditional access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="7af99-132">**基本**保護適用於所有使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7af99-132">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="7af99-133">**機密**保護適用於高階領導人和主管人員</span><span class="sxs-lookup"><span data-stu-id="7af99-133">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="7af99-134">**高管制**保護適用於財務、法務和研究部門中的特定使用者，他們需存取高管制的資料</span><span class="sxs-lookup"><span data-stu-id="7af99-134">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="7af99-135">圖 4 顯示身分識別及裝置條件式存取原則的結果集合。</span><span class="sxs-lookup"><span data-stu-id="7af99-135">Figure 5 shows their resulting set of conditional access policies for identity.</span></span>

![](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="7af99-136">**圖 4：Contoso 的身分識別及裝置條件式存取原則**</span><span class="sxs-lookup"><span data-stu-id="7af99-136">**Figure 4: Contoso’s identity and device conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="7af99-137">下一步</span><span class="sxs-lookup"><span data-stu-id="7af99-137">Next step</span></span>

<span data-ttu-id="7af99-138">[了解](contoso-win10.md) Contoso 如何使用 System Center Configuration Manager 基礎結構，在整個組織部署及保持目前的 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="7af99-138">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="7af99-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7af99-139">See also</span></span>

[<span data-ttu-id="7af99-140">Microsoft 365 企業版的身分識別</span><span class="sxs-lookup"><span data-stu-id="7af99-140">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="7af99-141">部署指南</span><span class="sxs-lookup"><span data-stu-id="7af99-141">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7af99-142">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="7af99-142">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
