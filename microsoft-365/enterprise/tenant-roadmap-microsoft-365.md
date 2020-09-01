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
ms.collection: M365-subscription-management
ms.custom: it-pro
description: 設定 Microsoft 365 承租人的藍圖。
ms.openlocfilehash: 540d1bc53ac06b85d22a8a60a62e51761e10339c
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315750"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="c75e5-103">Microsoft 365 租使用者藍圖</span><span class="sxs-lookup"><span data-stu-id="c75e5-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="c75e5-104">您的 Microsoft 365 租使用者是指派給您組織的一組服務。</span><span class="sxs-lookup"><span data-stu-id="c75e5-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="c75e5-105">此租使用者通常與一或多個 DNS 功能變數名稱相關聯，其作用中為不同訂閱的中央容器，以及您指派給使用者帳戶的授權。</span><span class="sxs-lookup"><span data-stu-id="c75e5-105">This tenant is typically associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> 

<span data-ttu-id="c75e5-106">當您建立 Microsoft 365 租使用者時，您可以將其指派給特定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="c75e5-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="c75e5-107">您也可以讓租使用者使用多個地理位置，並將租使用者從一個位置移至另一個位置。</span><span class="sxs-lookup"><span data-stu-id="c75e5-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="c75e5-108">規劃良好且執行的租使用者設定對於網路和身分識別的基礎服務的準備很重要。</span><span class="sxs-lookup"><span data-stu-id="c75e5-108">A well-planned and executed tenant configuration is critical to getting it ready for the foundational services of networking and identity.</span></span>

## <a name="plan"></a><span data-ttu-id="c75e5-109">方案</span><span class="sxs-lookup"><span data-stu-id="c75e5-109">Plan</span></span>

<span data-ttu-id="c75e5-110">若要規劃租使用者的執行：</span><span class="sxs-lookup"><span data-stu-id="c75e5-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="c75e5-111">瞭解訂閱、授權和 Azure Active Directory (Azure AD) 承租人</span><span class="sxs-lookup"><span data-stu-id="c75e5-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="c75e5-112">瞭解如何使用協力廠商 SSL 憑證</span><span class="sxs-lookup"><span data-stu-id="c75e5-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="c75e5-113">Microsoft 365 系統管理中心的 Access 安裝指南</span><span class="sxs-lookup"><span data-stu-id="c75e5-113">Access setup guides in the Microsoft 365 admin center</span></span>](setup-guides-for-microsoft-365.md)
- [<span data-ttu-id="c75e5-114">瞭解 Microsoft 365 租使用者與 Azure AD 服務的整合方式</span><span class="sxs-lookup"><span data-stu-id="c75e5-114">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="c75e5-115">規劃用戶端應用程式的支援</span><span class="sxs-lookup"><span data-stu-id="c75e5-115">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="c75e5-116">決定如何使用混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="c75e5-116">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="c75e5-117">規劃 Office 2007 和 Office 2010 升級</span><span class="sxs-lookup"><span data-stu-id="c75e5-117">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="c75e5-118">瞭解租使用者隔離</span><span class="sxs-lookup"><span data-stu-id="c75e5-118">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="c75e5-119">取得 Microsoft 365 服務保障的詳細資料</span><span class="sxs-lookup"><span data-stu-id="c75e5-119">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="c75e5-120">部署</span><span class="sxs-lookup"><span data-stu-id="c75e5-120">Deploy</span></span>

<span data-ttu-id="c75e5-121">若要部署您的租使用者，請為您 [的組織新增 DNS 網域](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 。</span><span class="sxs-lookup"><span data-stu-id="c75e5-121">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="c75e5-122">具有多個地理位置的承租人</span><span class="sxs-lookup"><span data-stu-id="c75e5-122">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="c75e5-123">使用 Microsoft 365 多地理位置，您的組織可以將 Microsoft 365 存在狀態擴展到現有租用戶中的多個地理區域和/或國家/地區。</span><span class="sxs-lookup"><span data-stu-id="c75e5-123">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="c75e5-124">[開始](microsoft-365-multi-geo.md) 瞭解、規劃、設定及管理 Microsoft 365 多地理位置。</span><span class="sxs-lookup"><span data-stu-id="c75e5-124">[Get started](microsoft-365-multi-geo.md) in understanding, planning, configuring, and then administering with Microsoft 365 Multi-Geo.</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="c75e5-125">移動租使用者的地理位置</span><span class="sxs-lookup"><span data-stu-id="c75e5-125">Move a tenant's geographic locations</span></span>

<span data-ttu-id="c75e5-126">Microsoft 會繼續開啟新的資料中心地理位置， (geos) Microsoft 365 服務。</span><span class="sxs-lookup"><span data-stu-id="c75e5-126">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="c75e5-127">這些新的資料中心 geos 可增加容量及計算資源，以支援客戶需求和使用量成長。</span><span class="sxs-lookup"><span data-stu-id="c75e5-127">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="c75e5-128">此外，新的資料中心 geos 提供核心客戶資料的地理位置資料派駐服務。</span><span class="sxs-lookup"><span data-stu-id="c75e5-128">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="c75e5-129">開始瞭解和要求地區資料移動，將 [核心資料移至新的 Microsoft 365 datacenter geo](moving-data-to-new-datacenter-geos.md)。</span><span class="sxs-lookup"><span data-stu-id="c75e5-129">Get started in understanding and requesting a geo data move with [Moving core data to new Microsoft 365 datacenter geo](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="c75e5-130">下一步</span><span class="sxs-lookup"><span data-stu-id="c75e5-130">Next step</span></span>

<span data-ttu-id="c75e5-131">以 [訂閱、授權、帳戶及](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)租使用者的方式開始規劃承租人。</span><span class="sxs-lookup"><span data-stu-id="c75e5-131">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

