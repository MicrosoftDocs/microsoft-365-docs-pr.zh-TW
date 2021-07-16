---
title: Microsoft 365 的承租人藍圖
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: 設定 Microsoft 365 承租人的藍圖。
ms.openlocfilehash: 4b94540293b86bd922ce4b29f970e52eb1245a01
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464030"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="93d3c-103">Microsoft 365 的承租人藍圖</span><span class="sxs-lookup"><span data-stu-id="93d3c-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="93d3c-104">您的 Microsoft 365 租使用者是指派給您組織的一組服務。</span><span class="sxs-lookup"><span data-stu-id="93d3c-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="93d3c-105">此租使用者通常會與一或多個公用 DNS 功能變數名稱產生關聯，並且充當不同訂閱的中央和獨立容器，以及您指派給使用者帳戶的授權。</span><span class="sxs-lookup"><span data-stu-id="93d3c-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="93d3c-106">如需詳細資訊，請參閱 [Microsoft 雲端供應專案的訂閱、授權、帳戶及承租人](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。</span><span class="sxs-lookup"><span data-stu-id="93d3c-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="93d3c-107">當您建立 Microsoft 365 租使用者時，您可以將其指派給特定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="93d3c-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="93d3c-108">您也可以讓租使用者使用多個地理位置，並將租使用者從一個位置移至另一個位置。</span><span class="sxs-lookup"><span data-stu-id="93d3c-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="93d3c-109">若要讓您的租使用者準備好進行使用者、群組、授權和雲端應用程式，請務必仔細規劃並執行您的租使用者設定。</span><span class="sxs-lookup"><span data-stu-id="93d3c-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="93d3c-110">設定 Microsoft 365 租使用者</span><span class="sxs-lookup"><span data-stu-id="93d3c-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="93d3c-111">確定您的網路已針對內部部署和遠端工作者的 Microsoft 365 存取進行優化後，您下一次的大型工作會進行規劃，然後針對 DNS 功能變數名稱、泛型服務，以及支援安全使用者登入的身分識別基礎結構，設定 Microsoft 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="93d3c-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="93d3c-112">方案</span><span class="sxs-lookup"><span data-stu-id="93d3c-112">Plan</span></span>

<span data-ttu-id="93d3c-113">若要規劃租使用者的執行：</span><span class="sxs-lookup"><span data-stu-id="93d3c-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="93d3c-114">瞭解訂閱、授權和 Azure Active Directory (Azure AD) 承租人</span><span class="sxs-lookup"><span data-stu-id="93d3c-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="93d3c-115">瞭解如何使用協力廠商 SSL 憑證</span><span class="sxs-lookup"><span data-stu-id="93d3c-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="93d3c-116">瞭解 Microsoft 365 租使用者與 Azure AD 服務整合的方式</span><span class="sxs-lookup"><span data-stu-id="93d3c-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="93d3c-117">規劃用戶端應用程式的支援</span><span class="sxs-lookup"><span data-stu-id="93d3c-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="93d3c-118">決定如何使用混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="93d3c-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="93d3c-119">規劃 Office 2007 和 Office 2010 升級</span><span class="sxs-lookup"><span data-stu-id="93d3c-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="93d3c-120">瞭解租使用者隔離</span><span class="sxs-lookup"><span data-stu-id="93d3c-120">Understand tenant isolation</span></span>](/compliance/assurance/microsoft-365-isolation-controls)

### <a name="deploy"></a><span data-ttu-id="93d3c-121">部署</span><span class="sxs-lookup"><span data-stu-id="93d3c-121">Deploy</span></span>

<span data-ttu-id="93d3c-122">若要部署您的租使用者：</span><span class="sxs-lookup"><span data-stu-id="93d3c-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="93d3c-123">為您的組織新增 [DNS 網域](../admin/setup/add-domain.md) 。</span><span class="sxs-lookup"><span data-stu-id="93d3c-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="93d3c-124">使用[Microsoft 365 系統管理中心中的設定指南](setup-guides-for-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="93d3c-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="93d3c-125">組建您的身分 [識別基礎結構](identity-roadmap-microsoft-365.md) ，並 [保護使用者登入](microsoft-365-secure-sign-in.md)。</span><span class="sxs-lookup"><span data-stu-id="93d3c-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="93d3c-126">移動租使用者的地理位置</span><span class="sxs-lookup"><span data-stu-id="93d3c-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="93d3c-127">Microsoft 繼續開啟新的資料中心地理位置， (geos) Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="93d3c-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="93d3c-128">這些新的資料中心 geos 可增加容量及計算資源，以支援客戶需求和使用量成長。</span><span class="sxs-lookup"><span data-stu-id="93d3c-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="93d3c-129">此外，新的資料中心 geos 提供核心客戶資料的地理位置資料派駐服務。</span><span class="sxs-lookup"><span data-stu-id="93d3c-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="93d3c-130">如需詳細資訊，請參閱[將核心資料移至新 Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md)。</span><span class="sxs-lookup"><span data-stu-id="93d3c-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="93d3c-131">部署 Microsoft 365 多地理位置</span><span class="sxs-lookup"><span data-stu-id="93d3c-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="93d3c-132">使用 Microsoft 365 多地理位置，您的組織可以將 Microsoft 365 存在狀態擴展到現有租用戶中的多個地理區域和/或國家/地區。</span><span class="sxs-lookup"><span data-stu-id="93d3c-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="93d3c-133">如需詳細資訊，請參閱 [Microsoft 365 多地理位置](microsoft-365-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="93d3c-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="93d3c-134">管理多個 Microsoft 365 承租人</span><span class="sxs-lookup"><span data-stu-id="93d3c-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="93d3c-135">雖然為您的 oganization 使用單一租使用者是理想的，但您可以是具有多個承租人的眾多組織之一。</span><span class="sxs-lookup"><span data-stu-id="93d3c-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="93d3c-136">原因包括合併和收購、您想要管理隔離，或您具有分散的方式。</span><span class="sxs-lookup"><span data-stu-id="93d3c-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="93d3c-137">如果您有多個 Microsoft 365 承租人，請參閱下列文章，以取得詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="93d3c-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="93d3c-138">租用戶間共同作業</span><span class="sxs-lookup"><span data-stu-id="93d3c-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="93d3c-139">跨租用戶信箱移轉</span><span class="sxs-lookup"><span data-stu-id="93d3c-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="93d3c-140">租用戶到租用戶的移轉</span><span class="sxs-lookup"><span data-stu-id="93d3c-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="93d3c-141">下一個步驟</span><span class="sxs-lookup"><span data-stu-id="93d3c-141">Next step</span></span>

<span data-ttu-id="93d3c-142">以 [訂閱、授權、帳戶及](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)租使用者的方式開始規劃承租人。</span><span class="sxs-lookup"><span data-stu-id="93d3c-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>