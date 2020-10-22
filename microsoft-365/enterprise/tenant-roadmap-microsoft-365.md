---
title: Microsoft 365 租使用者藍圖
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: 設定 Microsoft 365 承租人的藍圖。
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656004"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="0bc4d-103">Microsoft 365 租使用者藍圖</span><span class="sxs-lookup"><span data-stu-id="0bc4d-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="0bc4d-104">您的 Microsoft 365 租使用者是指派給您組織的一組服務。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="0bc4d-105">此租使用者通常會與一或多個 DNS 功能變數名稱產生關聯，並充當不同訂閱的中央容器，以及您指派給使用者帳戶的授權。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="0bc4d-106">如需詳細資訊，請參閱 [Microsoft 雲端供應專案的訂閱、授權、帳戶及承租人](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="0bc4d-107">當您建立 Microsoft 365 租使用者時，您可以將其指派給特定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="0bc4d-108">您也可以讓租使用者使用多個地理位置，並將租使用者從一個位置移至另一個位置。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="0bc4d-109">若要讓您的承租人準備好身分識別，請務必謹慎規劃並執行您的租使用者設定。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-109">To get your tenant ready for identity, it's critical to carefully plan and execute your tenant configuration.</span></span>


## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="0bc4d-110">設定您的 Microsoft 365 租使用者</span><span class="sxs-lookup"><span data-stu-id="0bc4d-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="0bc4d-111">確定您的網路可針對內部部署和遠端工作者存取 Microsoft 365 之後，您的下一個重要工作是針對 DNS 功能變數名稱、泛型服務，以及支援安全使用者登入的身分識別基礎結構，設定您的 Microsoft 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

## <a name="plan"></a><span data-ttu-id="0bc4d-112">計劃</span><span class="sxs-lookup"><span data-stu-id="0bc4d-112">Plan</span></span>

<span data-ttu-id="0bc4d-113">若要規劃租使用者的執行：</span><span class="sxs-lookup"><span data-stu-id="0bc4d-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="0bc4d-114">瞭解訂閱、授權和 Azure Active Directory (Azure AD) 承租人</span><span class="sxs-lookup"><span data-stu-id="0bc4d-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="0bc4d-115">瞭解如何使用協力廠商 SSL 憑證</span><span class="sxs-lookup"><span data-stu-id="0bc4d-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="0bc4d-116">瞭解 Microsoft 365 租使用者與 Azure AD 服務的整合方式</span><span class="sxs-lookup"><span data-stu-id="0bc4d-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="0bc4d-117">規劃用戶端應用程式的支援</span><span class="sxs-lookup"><span data-stu-id="0bc4d-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="0bc4d-118">決定如何使用混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="0bc4d-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="0bc4d-119">規劃 Office 2007 和 Office 2010 升級</span><span class="sxs-lookup"><span data-stu-id="0bc4d-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="0bc4d-120">瞭解租使用者隔離</span><span class="sxs-lookup"><span data-stu-id="0bc4d-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="0bc4d-121">取得 Microsoft 365 服務保障的詳細資料</span><span class="sxs-lookup"><span data-stu-id="0bc4d-121">Get the details on Microsoft 365 service assurance</span></span>](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a><span data-ttu-id="0bc4d-122">部署</span><span class="sxs-lookup"><span data-stu-id="0bc4d-122">Deploy</span></span>

<span data-ttu-id="0bc4d-123">若要部署您的租使用者：</span><span class="sxs-lookup"><span data-stu-id="0bc4d-123">To deploy your tenant:</span></span> 

- <span data-ttu-id="0bc4d-124">為您的組織新增 [DNS 網域](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-124">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="0bc4d-125">使用 [Microsoft 365 系統管理中心的設定指南](setup-guides-for-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-125">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="0bc4d-126">組建您的身分 [識別基礎結構](identity-roadmap-microsoft-365.md) ，並 [保護使用者登入](microsoft-365-secure-sign-in.md)。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-126">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="0bc4d-127">移動租使用者的地理位置</span><span class="sxs-lookup"><span data-stu-id="0bc4d-127">Move a tenant's geographic locations</span></span>

<span data-ttu-id="0bc4d-128">Microsoft 會繼續開啟新的資料中心地理位置， (geos) Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-128">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="0bc4d-129">這些新的資料中心 geos 可增加容量及計算資源，以支援客戶需求和使用量成長。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-129">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="0bc4d-130">此外，新的資料中心 geos 提供核心客戶資料的地理位置資料派駐服務。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-130">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="0bc4d-131">如需詳細資訊，請參閱 [將核心資料移至新的 Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md)。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-131">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="0bc4d-132">部署 Microsoft 365 多地理位置</span><span class="sxs-lookup"><span data-stu-id="0bc4d-132">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="0bc4d-133">使用 Microsoft 365 多地理位置，您的組織可以將 Microsoft 365 存在狀態擴展到現有租用戶中的多個地理區域和/或國家/地區。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-133">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="0bc4d-134">如需詳細資訊，請參閱 [Microsoft 365 多地理](microsoft-365-multi-geo.md)位置。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-134">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenancies"></a><span data-ttu-id="0bc4d-135">管理多個 Microsoft 365 租用</span><span class="sxs-lookup"><span data-stu-id="0bc4d-135">Manage multiple Microsoft 365 tenancies</span></span> 

<span data-ttu-id="0bc4d-136">雖然有單一租使用者 oganization 是理想的，但您可以是許多組織中有多個租用的組織。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-136">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenancies.</span></span> <span data-ttu-id="0bc4d-137">多個租用的原因可能包括合併和收購、您想要管理隔離，或您有分散的原因。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-137">Reasons for multiple tenancies can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="0bc4d-138">如果您有多個 Microsoft 365 租用，請參閱下列文章，以取得詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="0bc4d-138">If you have multiple Microsoft 365 tenancies, see these articles for more information about:</span></span>

- [<span data-ttu-id="0bc4d-139">租用戶間共同作業</span><span class="sxs-lookup"><span data-stu-id="0bc4d-139">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="0bc4d-140">跨租用戶信箱移轉</span><span class="sxs-lookup"><span data-stu-id="0bc4d-140">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="0bc4d-141">租用戶到租用戶的移轉</span><span class="sxs-lookup"><span data-stu-id="0bc4d-141">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a><span data-ttu-id="0bc4d-142">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0bc4d-142">Next step</span></span>

<span data-ttu-id="0bc4d-143">以 [訂閱、授權、帳戶及](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)租使用者的方式開始規劃承租人。</span><span class="sxs-lookup"><span data-stu-id="0bc4d-143">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
