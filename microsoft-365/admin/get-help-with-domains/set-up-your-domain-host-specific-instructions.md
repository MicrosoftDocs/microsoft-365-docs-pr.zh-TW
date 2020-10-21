---
title: 設定您的網域 (主機專用指示)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: 瞭解如何管理您自己的 DNS 記錄，或讓 Microsoft 為您管理您的 DNS 記錄。
ms.openlocfilehash: a22968fdfcdb6be8ecfdc9dde351de034edce4b2
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645296"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="86928-103">設定您的網域 (主機專用指示)</span><span class="sxs-lookup"><span data-stu-id="86928-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="86928-104">若要開始使用自訂網域 (contoso.com) 與 Microsoft 365，您必須驗證您的網域，並設定您的網域的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="86928-104">To start using a custom domain (contoso.com) with Microsoft 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="86928-105">您可以使用網域主機上的系統管理工具來新增及管理 DNS 記錄，或對您的網域記錄提供 Microsoft 控制，我們會為您設定這些記錄。</span><span class="sxs-lookup"><span data-stu-id="86928-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="86928-106">請選取下列您的網域主機，以取得確切的步驟。</span><span class="sxs-lookup"><span data-stu-id="86928-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="86928-107">如果您不確定您的主機是誰，請參閱 [尋找您的網域註冊機構](find-your-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="86928-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-microsoft-365-manage-your-dns-records"></a><span data-ttu-id="86928-108">讓 Microsoft 365 管理您的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="86928-108">Let Microsoft 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="86928-109">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="86928-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="86928-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="86928-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="86928-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="86928-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="86928-112">Google 網域</span><span class="sxs-lookup"><span data-stu-id="86928-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="86928-113">Hostgator   </span><span class="sxs-lookup"><span data-stu-id="86928-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="86928-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="86928-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="86928-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="86928-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="86928-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="86928-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="86928-117">或者，瞭解如何 [使用任何網域註冊機構變更名稱伺服器以設定 Microsoft 365](change-nameservers-at-any-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="86928-117">Or, learn how to [change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="86928-118">管理您自己的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="86928-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="86928-119">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="86928-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="86928-120">懸停</span><span class="sxs-lookup"><span data-stu-id="86928-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="86928-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="86928-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="86928-122">由 Google (eNom) 管理 </span><span class="sxs-lookup"><span data-stu-id="86928-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="86928-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="86928-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="86928-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="86928-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="86928-125">Azure DNS 區域</span><span class="sxs-lookup"><span data-stu-id="86928-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="86928-126">name.com</span><span class="sxs-lookup"><span data-stu-id="86928-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="86928-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="86928-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="86928-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="86928-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="86928-129">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="86928-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="86928-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="86928-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="86928-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="86928-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="86928-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="86928-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="86928-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="86928-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="86928-134">網路解決方案</span><span class="sxs-lookup"><span data-stu-id="86928-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="86928-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="86928-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="86928-136">Ovh</span><span class="sxs-lookup"><span data-stu-id="86928-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="86928-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="86928-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="86928-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="86928-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="86928-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="86928-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="86928-140">Microsoft 365 的 Register365</span><span class="sxs-lookup"><span data-stu-id="86928-140">Register365 for Microsoft 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="86928-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="86928-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="86928-142"> web.com </span><span class="sxs-lookup"><span data-stu-id="86928-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="86928-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="86928-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="86928-144"> Windows 型 DNS</span><span class="sxs-lookup"><span data-stu-id="86928-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="86928-145">Google 網域</span><span class="sxs-lookup"><span data-stu-id="86928-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="86928-146">Wix</span><span class="sxs-lookup"><span data-stu-id="86928-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="86928-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="86928-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="86928-148">雅虎！  小型企業</span><span class="sxs-lookup"><span data-stu-id="86928-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="86928-149">我需要一般指示，因為我的網域主機未出現在此清單中。 </span><span class="sxs-lookup"><span data-stu-id="86928-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
