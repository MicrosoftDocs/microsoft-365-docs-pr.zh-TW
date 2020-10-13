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
ms.openlocfilehash: 0f1fa91bb81fd6cc87820f2b2d48e00e1b75a0c4
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446004"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="123ab-103">Microsoft 365 租使用者藍圖</span><span class="sxs-lookup"><span data-stu-id="123ab-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="123ab-104">您的 Microsoft 365 租使用者是指派給您組織的一組服務。</span><span class="sxs-lookup"><span data-stu-id="123ab-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="123ab-105">此租使用者通常會與一或多個 DNS 功能變數名稱產生關聯，並充當不同訂閱的中央容器，以及您指派給使用者帳戶的授權。</span><span class="sxs-lookup"><span data-stu-id="123ab-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span>

<span data-ttu-id="123ab-106">當您建立 Microsoft 365 租使用者時，您可以將其指派給特定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="123ab-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="123ab-107">您也可以讓租使用者使用多個地理位置，並將租使用者從一個位置移至另一個位置。</span><span class="sxs-lookup"><span data-stu-id="123ab-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="123ab-108">若要讓您的租使用者準備好用於網路和身分識別的基礎服務，請務必謹慎規劃並執行您的租使用者設定。</span><span class="sxs-lookup"><span data-stu-id="123ab-108">To get your tenant ready for the foundational services of networking and identity, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="plan"></a><span data-ttu-id="123ab-109">規劃</span><span class="sxs-lookup"><span data-stu-id="123ab-109">Plan</span></span>

<span data-ttu-id="123ab-110">若要規劃租使用者的執行：</span><span class="sxs-lookup"><span data-stu-id="123ab-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="123ab-111">瞭解訂閱、授權和 Azure Active Directory (Azure AD) 承租人</span><span class="sxs-lookup"><span data-stu-id="123ab-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="123ab-112">瞭解如何使用協力廠商 SSL 憑證</span><span class="sxs-lookup"><span data-stu-id="123ab-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="123ab-113">瞭解 Microsoft 365 租使用者與 Azure AD 服務的整合方式</span><span class="sxs-lookup"><span data-stu-id="123ab-113">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="123ab-114">規劃用戶端應用程式的支援</span><span class="sxs-lookup"><span data-stu-id="123ab-114">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="123ab-115">決定如何使用混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="123ab-115">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="123ab-116">規劃 Office 2007 和 Office 2010 升級</span><span class="sxs-lookup"><span data-stu-id="123ab-116">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="123ab-117">瞭解租使用者隔離</span><span class="sxs-lookup"><span data-stu-id="123ab-117">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="123ab-118">取得 Microsoft 365 服務保障的詳細資料</span><span class="sxs-lookup"><span data-stu-id="123ab-118">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="123ab-119">部署</span><span class="sxs-lookup"><span data-stu-id="123ab-119">Deploy</span></span>

<span data-ttu-id="123ab-120">若要部署租使用者，請 [新增組織的 DNS 網域](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) ，並使用 [Microsoft 365 系統管理中心中的設定指南](setup-guides-for-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="123ab-120">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization and use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="123ab-121">具有多個地理位置的承租人</span><span class="sxs-lookup"><span data-stu-id="123ab-121">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="123ab-122">使用 Microsoft 365 多地理位置，您的組織可以將 Microsoft 365 存在狀態擴展到現有租用戶中的多個地理區域和/或國家/地區。</span><span class="sxs-lookup"><span data-stu-id="123ab-122">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="123ab-123">如需 Microsoft 365 多地理位置的相關資訊，包括如何規劃、設定及管理，請 [從這裡開始](microsoft-365-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="123ab-123">For information about Microsoft 365 Multi-Geo, including how to plan, configure, and administer it, [start here](microsoft-365-multi-geo.md).</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="123ab-124">移動租使用者的地理位置</span><span class="sxs-lookup"><span data-stu-id="123ab-124">Move a tenant's geographic locations</span></span>

<span data-ttu-id="123ab-125">Microsoft 會繼續開啟新的資料中心地理位置， (geos) Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="123ab-125">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="123ab-126">這些新的資料中心 geos 可增加容量及計算資源，以支援客戶需求和使用量成長。</span><span class="sxs-lookup"><span data-stu-id="123ab-126">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="123ab-127">此外，新的資料中心 geos 提供核心客戶資料的地理位置資料派駐服務。</span><span class="sxs-lookup"><span data-stu-id="123ab-127">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="123ab-128">如需 Microsoft 365 資料中心地理位置的詳細資訊，包括如何要求地區資料移動，請 [從這裡開始](moving-data-to-new-datacenter-geos.md)。</span><span class="sxs-lookup"><span data-stu-id="123ab-128">For information about Microsoft 365 datacenter geo, including how to request a geo data move, [start here](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="123ab-129">下一步</span><span class="sxs-lookup"><span data-stu-id="123ab-129">Next step</span></span>

<span data-ttu-id="123ab-130">以 [訂閱、授權、帳戶及](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)租使用者的方式開始規劃承租人。</span><span class="sxs-lookup"><span data-stu-id="123ab-130">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

