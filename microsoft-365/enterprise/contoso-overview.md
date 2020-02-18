---
title: Contoso 公司概觀
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
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解 Contoso 公司的業務及其全球辦公室的分層架構。
ms.openlocfilehash: 856363881c749b06a530dc7cc4f0eb82dc155054
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068292"
---
# <a name="overview-of-the-contoso-corporation"></a><span data-ttu-id="31d11-103">Contoso 公司概觀</span><span class="sxs-lookup"><span data-stu-id="31d11-103">Overview of the Contoso Corporation</span></span>

![Contoso 公司](../media/contoso-overview/contoso-icon.png)

<span data-ttu-id="31d11-p101">Contoso 公司是一家跨國企業，總部設於法國巴黎。它是一家集製造、銷售與支援的集團，旗下商品超過 100,000 種。</span><span class="sxs-lookup"><span data-stu-id="31d11-p101">The Contoso Corporation is a multi-national business with headquarters in Paris, France. It is a conglomerate manufacturing, sales, and support organization with over 100,000 products.</span></span>

## <a name="contoso-around-the-world"></a><span data-ttu-id="31d11-107">世界各地的 Contoso</span><span class="sxs-lookup"><span data-stu-id="31d11-107">Contoso around the world</span></span>

<span data-ttu-id="31d11-108">圖 1 顯示在巴黎的總部和其他跨洲的地區中心及衛星辦公室。</span><span class="sxs-lookup"><span data-stu-id="31d11-108">Figure 1 shows the headquarters office in Paris and regional hub and satellite offices in various continents.</span></span>

![世界各地的 Contoso 辦公室](../media/contoso-overview/contoso-overview-fig1.png)

<span data-ttu-id="31d11-110">**圖 1：世界各地的 Contoso 辦公室**</span><span class="sxs-lookup"><span data-stu-id="31d11-110">**Figure 1: Contoso's offices around the world**</span></span>
 
<span data-ttu-id="31d11-111">Contoso 辦公室皆依照下列三層式架構設計。</span><span class="sxs-lookup"><span data-stu-id="31d11-111">Contoso's offices around the world follow a three-tier design.</span></span>

- <span data-ttu-id="31d11-112">總部</span><span class="sxs-lookup"><span data-stu-id="31d11-112">Headquarters</span></span>

  <span data-ttu-id="31d11-p102">Contoso 公司總部是個位於巴黎郊區的大型園區，園區中有多座建築物做為行政、工程和生產設施之用。所有 Contoso 的資料中心及其網際網路呈現設施均位於巴黎總部。</span><span class="sxs-lookup"><span data-stu-id="31d11-p102">The Contoso Corporation headquarters is a large corporate campus on the outskirts of Paris with dozens of buildings for administrative, engineering, and manufacturing facilities. All of Contoso's datacenters and its Internet presence are housed in the Paris headquarters.</span></span>

  <span data-ttu-id="31d11-115">總部共有 25,000 名員工。</span><span class="sxs-lookup"><span data-stu-id="31d11-115">The headquarters has 25,000 workers.</span></span>

- <span data-ttu-id="31d11-116">地區中心</span><span class="sxs-lookup"><span data-stu-id="31d11-116">Regional hubs</span></span>

  <span data-ttu-id="31d11-p103">地區中心辦公室主要服務全球特定區域 60% 的銷售和支援人員。每個地區中心均透過高頻寬 WAN 連結連線至巴黎總部。</span><span class="sxs-lookup"><span data-stu-id="31d11-p103">Regional hub offices serve a specific region of the world with 60% sales and support staff. Each regional hub is connected to the Paris headquarters with a high-bandwidth WAN link.</span></span>

  <span data-ttu-id="31d11-119">每個地區中心平均有 2,000 名員工。</span><span class="sxs-lookup"><span data-stu-id="31d11-119">Each regional hub has an average of 2,000 workers.</span></span>

- <span data-ttu-id="31d11-120">衛星辦公室</span><span class="sxs-lookup"><span data-stu-id="31d11-120">Satellite offices</span></span>

  <span data-ttu-id="31d11-p104">衛星辦公室容納 80% 的銷售與支援人員，負責為主要城市或分區的 Contoso 客戶提供現場服務，每個衛星辦公室均透過高頻寬 WAN 連結連線至地區中心。</span><span class="sxs-lookup"><span data-stu-id="31d11-p104">Satellite offices contain 80% sales and support staff and provide an on-site presence for Contoso customers in key cities or sub-regions. Each satellite office is connected to a regional hub with a high-bandwidth WAN link.</span></span>

  <span data-ttu-id="31d11-123">每個衛星辦公室平均有 250 名員工。</span><span class="sxs-lookup"><span data-stu-id="31d11-123">Each satellite office has an average of 250 workers.</span></span>

<span data-ttu-id="31d11-p105">25% 的 Contoso 員工屬於行動工作者，當中又以地區中心和衛星辦公室的行動工作者人數佔較高的百分比。為行動工作者提供較完善的支援是 Contoso 的一項重要業務目標。 </span><span class="sxs-lookup"><span data-stu-id="31d11-p105">25% of Contoso's workforce is mobile-only, with a higher percentage of mobile-only workers in the regional hubs and satellite offices. Providing better support for mobile-only workers is an important business goal for Contoso.</span></span>

## <a name="design-considerations-for-microsoft-365-enterprise"></a><span data-ttu-id="31d11-126">Microsoft 365 企業版的設計考量</span><span class="sxs-lookup"><span data-stu-id="31d11-126">Design considerations for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="31d11-127">Contoso 的 IT 架構識別在部署 Microsoft 365 企業版時的以下設計需求和考量：</span><span class="sxs-lookup"><span data-stu-id="31d11-127">Contoso's IT architects identified the following design requirements and considerations when deploying Microsoft 365 Enterprise:</span></span> 

- <span data-ttu-id="31d11-128">多個地理位置與其須遵守的當地法規及規範</span><span class="sxs-lookup"><span data-stu-id="31d11-128">Multiple geographic locations with local regulations and compliance requirements</span></span>
- <span data-ttu-id="31d11-129">在總部辦公室的中央內部資料中心和地區應用程式伺服器中，裝載內部業務應用程式</span><span class="sxs-lookup"><span data-stu-id="31d11-129">A central intranet datacenter in the headquarters office and regional application servers that host internal line of business applications</span></span>
- <span data-ttu-id="31d11-130">現有的 Microsoft Endpoint Configuration Manager 基礎架構</span><span class="sxs-lookup"><span data-stu-id="31d11-130">An existing Microsoft Endpoint Configuration Manager infrastructure</span></span>
- <span data-ttu-id="31d11-131">混合的用戶端電腦裝置，包括 Windows、Mac 和 Linux</span><span class="sxs-lookup"><span data-stu-id="31d11-131">A mix of client computing devices, including Windows, Mac, and Linux</span></span>
- <span data-ttu-id="31d11-132">混合的個人及公司行動裝置，包括 iOS (iPhone 和 iPad)、Android 智慧型手機及平板電腦</span><span class="sxs-lookup"><span data-stu-id="31d11-132">A mix of personal and company-owned mobile devices, including iOS (iPhone and iPad) and Android smart phones and tablets</span></span>
- <span data-ttu-id="31d11-133">為數眾多的遠端和行動工作者</span><span class="sxs-lookup"><span data-stu-id="31d11-133">Many remote and mobile workers</span></span>
- <span data-ttu-id="31d11-134">為數眾多的事業夥伴</span><span class="sxs-lookup"><span data-stu-id="31d11-134">Many business partners</span></span>
- <span data-ttu-id="31d11-135">數量龐大的客戶及個人識別資訊</span><span class="sxs-lookup"><span data-stu-id="31d11-135">A large amount of customer and personally identifiable information</span></span>
- <span data-ttu-id="31d11-136">數量龐大的高價值產品設計規格智慧財產及製造交易秘密</span><span class="sxs-lookup"><span data-stu-id="31d11-136">A large amount of high-value intellectual property in the form of design specifications for products and manufacturing trade secrets</span></span>

## <a name="next-step"></a><span data-ttu-id="31d11-137">下一步</span><span class="sxs-lookup"><span data-stu-id="31d11-137">Next step</span></span>

<span data-ttu-id="31d11-138">[深入了解](contoso-infra-needs.md) Contoso 公司的內部部署 IT 基礎架構，以及 Microsoft 365 企業版如何解決其業務需求。</span><span class="sxs-lookup"><span data-stu-id="31d11-138">[Learn](contoso-infra-needs.md) about the Contoso Corporation’s on-premises IT infrastructure and how their business needs were addressed with Microsoft 365 Enterprise.</span></span>

## <a name="see-also"></a><span data-ttu-id="31d11-139">請參閱</span><span class="sxs-lookup"><span data-stu-id="31d11-139">See also</span></span>

[<span data-ttu-id="31d11-140">部署指南</span><span class="sxs-lookup"><span data-stu-id="31d11-140">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="31d11-141">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="31d11-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)



