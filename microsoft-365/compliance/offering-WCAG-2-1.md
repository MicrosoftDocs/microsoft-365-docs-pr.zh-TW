---
title: Web 內容無障礙指導方針 2.1
description: Microsoft 發行了 WCAG 2.1 AA，其報告反映完整的產品或服務，或可個別安裝的部分產品。
keywords: Microsoft 365, 合規性, 方案
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: a1887bd2b6c04836ebb11d224fcc59debcd88e55
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859443"
---
# <a name="web-content-accessibility-guidelines-21"></a><span data-ttu-id="2ed82-104">網頁內容協助工具指導方針 2.1</span><span class="sxs-lookup"><span data-stu-id="2ed82-104">Web Content Accessibility Guidelines 2.1</span></span>

## <a name="about-wcag-21"></a><span data-ttu-id="2ed82-105">關於 WCAG 2.1</span><span class="sxs-lookup"><span data-stu-id="2ed82-105">About WCAG 2.1</span></span>

<span data-ttu-id="2ed82-106">WCAG 2.1 提供一個用於開發網頁內容的架構，除了圖形能力有限的裝置使用者之外，亦改善了身心障礙使用者的協助工具。</span><span class="sxs-lookup"><span data-stu-id="2ed82-106">WCAG 2.1 provides a framework for developing web content that improves accessibility for people with disabilities, in addition to users of devices with limited graphical abilities.</span></span> <span data-ttu-id="2ed82-107">WCAG 2.0 是由全球資訊網協會 (W3C) 於 2008 年所發行，其為專門建立網頁標準的國際組織，並於 2018 年 6 月更新為 WCAG 2.1。</span><span class="sxs-lookup"><span data-stu-id="2ed82-107">WCAG 2.0 was published in 2008 by the World Wide Web Consortium (W3C), an international organization dedicated to creating web standards, and updated to WCAG 2.1 in June 2018.</span></span> <span data-ttu-id="2ed82-108">在 2012 年，WCAG 2.0 也是由國際標準組織 (ISO) 作為 ISO/IEC 40500:2012 所發行。</span><span class="sxs-lookup"><span data-stu-id="2ed82-108">In 2012, WCAG 2.0 was also published by the International Organization for Standardization (ISO) as ISO/IEC 40500:2012.</span></span>  
  
<span data-ttu-id="2ed82-109">符合 WCAG 2.1 的內容亦符合 WCAG 2.0。</span><span class="sxs-lookup"><span data-stu-id="2ed82-109">Content that conforms to WCAG 2.1 also conforms to WCAG 2.0.</span></span> <span data-ttu-id="2ed82-110">針對 WCAG 2.0 的一致性原則需求，WCAG 2.1 可以提供衡量一致性的替代方法。</span><span class="sxs-lookup"><span data-stu-id="2ed82-110">For policies requiring conformance to WCAG 2.0, WCAG 2.1 can provide an alternate means of conformance.</span></span>  
  
<span data-ttu-id="2ed82-111">每個指導方針的一致性需求是透過三種等級來衡量：A、AA 和 AAA。</span><span class="sxs-lookup"><span data-stu-id="2ed82-111">Conformance requirements for each guideline are measured in three levels: A, AA, and AAA.</span></span> <span data-ttu-id="2ed82-112">由於 Microsoft 是全世界各州/省和政府主要的軟體和雲端服務提供者，因此致力於遵守所有相關[國際標準和合規性控制](https://go.microsoft.com/fwlink/p/?linkid=2052226)。</span><span class="sxs-lookup"><span data-stu-id="2ed82-112">Because Microsoft is a major software and cloud-services provider to states and governments around the world, it is committed to complying with all relevant [international standards and compliance controls](https://go.microsoft.com/fwlink/p/?linkid=2052226).</span></span> <span data-ttu-id="2ed82-113">透過遵守這些大範圍的協助工具標準，Microsoft 確保政府內部和外部的所有客戶可以使用 Microsoft 服務和產品。</span><span class="sxs-lookup"><span data-stu-id="2ed82-113">By adhering to these wide-ranging accessibility standards, Microsoft ensures that all customers — both inside and outside of government — can use Microsoft services and products.</span></span>  

## <a name="microsoft-and-wcag-21"></a><span data-ttu-id="2ed82-114">Microsoft 與 WCAG 2.1</span><span class="sxs-lookup"><span data-stu-id="2ed82-114">Microsoft and WCAG 2.1</span></span>

<span data-ttu-id="2ed82-115">Microsoft 遵循 WCAG 2.1 (ISO/IEC 40500) 標準點，以承諾讓所有客戶都能存取技術和資料。</span><span class="sxs-lookup"><span data-stu-id="2ed82-115">Microsoft’s adherence to the WCAG 2.1 (ISO/IEC 40500) standard points to its commitment to making technology and data accessible for all customers.</span></span> <span data-ttu-id="2ed82-116">WCAG 2.1 (ISO/IEC 40500) 是補充 EN 301 549 (歐洲) 和 Section 508 (美國) 的國際協助工具需求。</span><span class="sxs-lookup"><span data-stu-id="2ed82-116">WCAG 2.1 (ISO/IEC 40500) is the international accessibility requirement that complements EN 301 549 (Europe) and Section 508 (U.S.).</span></span>  
  
<span data-ttu-id="2ed82-117">Microsoft 發行了 WCAG 2.1，其報告反映完整產品或服務。</span><span class="sxs-lookup"><span data-stu-id="2ed82-117">Microsoft publishes WCAG 2.1 reports that reflect the complete product or service.</span></span> <span data-ttu-id="2ed82-118">通常不會建立個別功能或元件的報告。</span><span class="sxs-lookup"><span data-stu-id="2ed82-118">It generally does not create reports for individual features or components.</span></span> <span data-ttu-id="2ed82-119">Microsoft 有時候可能會為現有產品發行新元件，或為現有元件發行新版本，其讓使用者可以選擇個別單獨安裝，且 Microsoft 也可能會發行該元件的 WCAG 2.1 報告。</span><span class="sxs-lookup"><span data-stu-id="2ed82-119">Sometimes, Microsoft might release a new component for an existing product, or a new version of an existing component, which users can choose to install separately, and Microsoft might also publish a WCAG 2.1 report for that component.</span></span>  
  
[<span data-ttu-id="2ed82-120">下載 WCAG 2.1 (ISO/IEC 40500) 協助工具標準</span><span class="sxs-lookup"><span data-stu-id="2ed82-120">Download the WCAG 2.1 (ISO/IEC 40500) accessibility standards</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2052226)

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="2ed82-121">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="2ed82-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="2ed82-122">Azure 和 Azure Government</span><span class="sxs-lookup"><span data-stu-id="2ed82-122">Azure and Azure Government</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="2ed82-123">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="2ed82-123">Azure DevOps Services</span></span>
- <span data-ttu-id="2ed82-124">Dynamics 365 和 Dynamics 365 美國政府</span><span class="sxs-lookup"><span data-stu-id="2ed82-124">Dynamics 365 and Dynamics 365 U.S. Government</span></span>
- <span data-ttu-id="2ed82-125">Intune</span><span class="sxs-lookup"><span data-stu-id="2ed82-125">Intune</span></span>
- <span data-ttu-id="2ed82-126">Office 365 和 Office 365 美國政府</span><span class="sxs-lookup"><span data-stu-id="2ed82-126">Office 365 and Office 365 U.S. Government</span></span>
- <span data-ttu-id="2ed82-127">Office 365 美國政府國防版</span><span class="sxs-lookup"><span data-stu-id="2ed82-127">Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="2ed82-128">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="2ed82-128">Windows Server 2016</span></span>

## <a name="microsoft-accessibility-conformance-reports"></a><span data-ttu-id="2ed82-129">Microsoft 協助工具一致性報告</span><span class="sxs-lookup"><span data-stu-id="2ed82-129">Microsoft accessibility conformance reports</span></span>

<span data-ttu-id="2ed82-130">尋找針對我們所有產品和服務的 WCAG 報告。</span><span class="sxs-lookup"><span data-stu-id="2ed82-130">Find WCAG reports for all our products and services.</span></span>

[<span data-ttu-id="2ed82-131">**深入了解**</span><span class="sxs-lookup"><span data-stu-id="2ed82-131">**Learn more**</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050974)

## <a name="resources"></a><span data-ttu-id="2ed82-132">資源</span><span class="sxs-lookup"><span data-stu-id="2ed82-132">Resources</span></span>

<span data-ttu-id="2ed82-133">Microsoft 協助工具網站：取得使用協助工具功能和探索 Microsoft 創新協助所有人達成更多目標的方法。</span><span class="sxs-lookup"><span data-stu-id="2ed82-133">[Microsoft accessibility site — Get information on using accessibility features and explore the ways Microsoft innovates to help everyone achieve more.</span></span>

[<span data-ttu-id="2ed82-134">Office 365 協助工具中心</span><span class="sxs-lookup"><span data-stu-id="2ed82-134">Office 365 Accessibility Center</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051801)
    - <span data-ttu-id="2ed82-135">適用於身心障礙使用者的 Office 365 資源。</span><span class="sxs-lookup"><span data-stu-id="2ed82-135">Office 365 resources for people with disabilities.</span></span>

[<span data-ttu-id="2ed82-136">企業身心障礙人士 Answer Desk</span><span class="sxs-lookup"><span data-stu-id="2ed82-136">Enterprise Disability Answer Desk</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050890)
    - <span data-ttu-id="2ed82-137">針對我們的產品和服務或合規性有相關協助工具問題之企業客戶所提供的專用支援。</span><span class="sxs-lookup"><span data-stu-id="2ed82-137">Dedicated support for enterprise customers with accessibility questions about our products and services or compliance.</span></span>

[<span data-ttu-id="2ed82-138">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="2ed82-138">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="2ed82-139">下載方案背景資料</span><span class="sxs-lookup"><span data-stu-id="2ed82-139">Download the offering backgrounder</span></span>

<span data-ttu-id="2ed82-140">是否需要此方案的背景資料文件？</span><span class="sxs-lookup"><span data-stu-id="2ed82-140">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="2ed82-141">下載 [PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf)。</span><span class="sxs-lookup"><span data-stu-id="2ed82-141">Download the [PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf).</span></span>
