---
title: 證券和 Exchange 傭金-法規系統合規性和完整性（SCI）
description: SCI 規則適用于 SCI 實體，包含這類自助組織（SROs）做為股票和選項交換、已註冊的清算機關和替代交易系統（ATSs）。
keywords: Microsoft 365, 合規性, 方案
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: e2b314934a51c16ab4e907b7d9f6208e7de21641
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065708"
---
# <a name="securities-and-exchange-commission-regulation-systems-compliance-and-integrity-sci"></a><span data-ttu-id="28e03-104">證券和 Exchange 傭金：法規系統規範與完整性（SCI）</span><span class="sxs-lookup"><span data-stu-id="28e03-104">Securities and Exchange Commission: Regulation Systems Compliance and Integrity (SCI)</span></span>

## <a name="about-regulation-sci"></a><span data-ttu-id="28e03-105">關於法規 SCI</span><span class="sxs-lookup"><span data-stu-id="28e03-105">About Regulation SCI</span></span>

<span data-ttu-id="28e03-106">美國證券和 Exchange 傭金（SEC）是美國聯邦政府的獨立代理商，以及美國證券市場的主要 overseer 和調節器。</span><span class="sxs-lookup"><span data-stu-id="28e03-106">The US Securities and Exchange Commission (SEC) is an independent agency of the US federal government and the primary overseer and regulator of US securities markets.</span></span> <span data-ttu-id="28e03-107">它會 wields 透過聯邦證券法律、提出新的證券規則，以及監督證券行業之市場法規的強制執行許可權。</span><span class="sxs-lookup"><span data-stu-id="28e03-107">It wields enforcement authority over federal securities laws, proposes new securities rules, and oversees market regulation of the securities industry.</span></span>

<span data-ttu-id="28e03-108">在11月2014中，SEC 採用[法規系統合規性和完整性（SCI）](https://www.sec.gov/rules/final/2014/34-73639.pdf) （以及 SCI 報告 SCI 事件的表單），以加強美國證券市場的技術基礎結構。</span><span class="sxs-lookup"><span data-stu-id="28e03-108">In November 2014, the SEC adopted [Regulation Systems Compliance and Integrity (SCI)](https://www.sec.gov/rules/final/2014/34-73639.pdf) (and Form SCI for reporting SCI events) to bolster the technology infrastructure in the US securities markets.</span></span> <span data-ttu-id="28e03-109">此項管理法規的設計是為了降低系統停機頻率、在發生這類事件時提升恢復能力，並增加證券市場技術的 SEC 監督，並強制執行其規章。</span><span class="sxs-lookup"><span data-stu-id="28e03-109">The regulation is designed to reduce the frequency of system outages, improve resiliency when such incidents do occur, and increase SEC oversight of securities market technology and enforcement of its regulations.</span></span>

<span data-ttu-id="28e03-110">SCI 規則適用于 SCI 實體，包含這類自助組織（SROs）做為股票和選項交換、已註冊的清算機關和替代交易系統（ATSs）。</span><span class="sxs-lookup"><span data-stu-id="28e03-110">The SCI rules apply to SCI entities, which include such self-regulatory organizations (SROs) as stock and options exchanges, registered clearing agencies, and alternative trading systems (ATSs).</span></span> <span data-ttu-id="28e03-111">規則主要規定直接支援主要證券市場功能的系統：貿易、淨空和結算、訂單路線、市場資料、市場規定和市場監控。</span><span class="sxs-lookup"><span data-stu-id="28e03-111">The rules primarily regulate the systems that directly support key securities market functions: trading, clearance and settlement, order routing, market data, market regulation, and market surveillance.</span></span>

## <a name="microsoft-and-sec-regulation-sci"></a><span data-ttu-id="28e03-112">Microsoft 和 SEC 法規 SCI</span><span class="sxs-lookup"><span data-stu-id="28e03-112">Microsoft and SEC Regulation SCI</span></span>

<span data-ttu-id="28e03-113">美國證券和 Exchange 傭金（SEC）採用規章 SCI，以加強運作及支援美國證券市場之金融組織的技術基礎結構。</span><span class="sxs-lookup"><span data-stu-id="28e03-113">The US Securities and Exchange Commission (SEC) adopted Regulation SCI to strengthen the technology infrastructure of the financial organizations that operate and support the US securities markets.</span></span> <span data-ttu-id="28e03-114">根據 SEC 監管，其需求的設計是要確保這些系統具有高可用性、強恢復性和低延遲（低大量的郵件，但延遲較小）。</span><span class="sxs-lookup"><span data-stu-id="28e03-114">Under SEC oversight, its requirements are designed to ensure that these systems have high availability, strong resiliency, and low latency (high volume of messages with little delay).</span></span>

<span data-ttu-id="28e03-115">為了協助指導我們必須遵守這種法規的金融服務客戶，Microsoft 已發佈[Microsoft AZURE SEC 規章系統合規性和完整性雲端實施指南](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers)。</span><span class="sxs-lookup"><span data-stu-id="28e03-115">To help guide US financial services customers who must comply with this regulation, Microsoft has published the [Microsoft Azure SEC Regulation Systems Compliance and Integrity Cloud Implementation Guide](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers).</span></span> <span data-ttu-id="28e03-116">本檔中的指導方針：</span><span class="sxs-lookup"><span data-stu-id="28e03-116">The guidance within this document:</span></span>

- <span data-ttu-id="28e03-117">提供支援強恢復性、高可用性和低延遲的整體 Azure 功能的概述。</span><span class="sxs-lookup"><span data-stu-id="28e03-117">Provides an overview of overall Azure capabilities that support strong resiliency, high availability, and low latency.</span></span>
- <span data-ttu-id="28e03-118">明確 Azure 位址的控制項區域和法規各部分。</span><span class="sxs-lookup"><span data-stu-id="28e03-118">Makes clear which control areas and regulatory aspects Azure addresses.</span></span> <span data-ttu-id="28e03-119">Azure 功能和服務對 SCI 需求的這種點對點對應，會針對法規架構來測量 Azure 的規範。</span><span class="sxs-lookup"><span data-stu-id="28e03-119">This point-by-point mapping of Azure features and services to SCI requirements measures Azure compliance against the regulatory framework.</span></span> <span data-ttu-id="28e03-120">它也可協助客戶瞭解他們可以將安全性責任移至 Azure，以在內部部署運作時，其已完全擁有。</span><span class="sxs-lookup"><span data-stu-id="28e03-120">It also helps customers understand where they can shift security responsibilities to Azure that they had fully owned when they operated on premises.</span></span> <span data-ttu-id="28e03-121">這些功能是由 Microsoft 在 Azure Sla 中所做的承諾所支援。</span><span class="sxs-lookup"><span data-stu-id="28e03-121">These capabilities are backed by the promises Microsoft makes in Azure SLAs.</span></span>
- <span data-ttu-id="28e03-122">指定客戶負責處理的每一項法規 SCI 需求，並提供 Azure 檔和服務，以協助他們處理這些責任。</span><span class="sxs-lookup"><span data-stu-id="28e03-122">Specifies each Regulation SCI requirement that is the customer’s responsibility to address, and offers Azure documentation and services to help them address these responsibilities.</span></span>

<span data-ttu-id="28e03-123">本檔提供重要規章 SCI focus 區域的完整檢查清單。</span><span class="sxs-lookup"><span data-stu-id="28e03-123">This document provides a thorough checklist of critical Regulation SCI focus areas.</span></span> <span data-ttu-id="28e03-124">這份檢查清單可協助金融組織瞭解如何採用 Azure 來協助確保他們的同盟、客戶和領導能夠遵守適用的法規需求。</span><span class="sxs-lookup"><span data-stu-id="28e03-124">This checklist helps financial organizations understand how they can adopt Azure to help assure their regulators, customers, and leadership that they can comply with the applicable regulatory requirements.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="28e03-125">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="28e03-125">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="28e03-126">Azure</span><span class="sxs-lookup"><span data-stu-id="28e03-126">Azure</span></span>](https://aka.ms/AzureCompliance)

## <a name="how-to-implement"></a><span data-ttu-id="28e03-127">實作方法</span><span class="sxs-lookup"><span data-stu-id="28e03-127">How to implement</span></span>

- <span data-ttu-id="28e03-128">[規章 SCI 實施指南](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers)：對應 Azure 功能與法規的對應，並詳述法規遵從性的共用責任。</span><span class="sxs-lookup"><span data-stu-id="28e03-128">[Regulation SCI Implementation Guide](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers): Maps Azure capabilities against the regulation and details the shared responsibility for compliance.</span></span>
- <span data-ttu-id="28e03-129">[設計可靠的 Azure 應用程式](https://docs.microsoft.com/azure/architecture/resiliency/)：如何在 Azure 應用程式設計的每一個步驟中建立可靠性的簡短概述。</span><span class="sxs-lookup"><span data-stu-id="28e03-129">[Designing reliable Azure applications](https://docs.microsoft.com/azure/architecture/resiliency/): A brief overview of how to build reliability into each step of Azure application design.</span></span>
- <span data-ttu-id="28e03-130">[設計高可用性的應用程式](https://docs.microsoft.com/azure/storage/common/storage-designing-ha-apps-with-ragrs)：開發人員如何協助確保其 Azure 儲存應用程式具有高可用性。</span><span class="sxs-lookup"><span data-stu-id="28e03-130">[Designing highly available applications](https://docs.microsoft.com/azure/storage/common/storage-designing-ha-apps-with-ragrs): How developers can help ensure that their Azure Storage applications are highly available.</span></span>
- <span data-ttu-id="28e03-131">[風險評定與合規性指南](https://aka.ms/RiskGovernanceGuide)：建立 Microsoft 雲端服務風險評定的監管模型和調整通知。</span><span class="sxs-lookup"><span data-stu-id="28e03-131">[Risk Assessment & Compliance Guide](https://aka.ms/RiskGovernanceGuide): Create a governance model for risk assessment of Microsoft cloud services, and regulator notification.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="28e03-132">常見問題集</span><span class="sxs-lookup"><span data-stu-id="28e03-132">Frequently asked questions</span></span>

<span data-ttu-id="28e03-133">**使用雲端技術時，共用責任是什麼意思？**</span><span class="sxs-lookup"><span data-stu-id="28e03-133">**What does shared responsibility mean when using cloud technology?**</span></span>

<span data-ttu-id="28e03-134">隨著計算環境從內部部署移至雲端的資料中心，安全性的責任也隨之，即雲端服務提供者（CSP）和客戶現在會分享該責任。</span><span class="sxs-lookup"><span data-stu-id="28e03-134">As computing environments move from datacenters on-premises to those in the cloud, the responsibility of security also shifts—the cloud services provider (CSP) and customer now share that responsibility.</span></span> <span data-ttu-id="28e03-135">針對每個應用程式和解決方案，該責任中有多少是對客戶而言的，而 CSP 的多少取決於客戶部署的 Azure 模型（IaaS、SaaS 或 PaaS）。</span><span class="sxs-lookup"><span data-stu-id="28e03-135">For every application and solution, how much of that responsibility falls on the customer and how much on the CSP depends on the Azure model that a customer deploys—IaaS, SaaS, or PaaS.</span></span> <span data-ttu-id="28e03-136">客戶的責任是要瞭解他們對實施必要安全性控制的責任程度。</span><span class="sxs-lookup"><span data-stu-id="28e03-136">It is the customer’s duty to understand to what degree they are accountable for implementing the required security controls.</span></span> <span data-ttu-id="28e03-137">不過，Microsoft 提供指導方針來協助客戶導覽此複雜的動態。</span><span class="sxs-lookup"><span data-stu-id="28e03-137">However, Microsoft provides guidance to help customers navigate this complex dynamic.</span></span> <span data-ttu-id="28e03-138">如需詳細資訊，請參閱[Cloud 計算的共用責任](https://gallery.technet.microsoft.com/Shared-Responsibilities-81d0ff91)。</span><span class="sxs-lookup"><span data-stu-id="28e03-138">For more information, read [Shared Responsibilities for Cloud Computing](https://gallery.technet.microsoft.com/Shared-Responsibilities-81d0ff91).</span></span>

<span data-ttu-id="28e03-139">**哪些金融機構可以利用 Azure 來協助滿足法規 SCI 需求？**</span><span class="sxs-lookup"><span data-stu-id="28e03-139">**Which financial institutions can take advantage of Azure to help meet Regulation SCI requirements?**</span></span>

<span data-ttu-id="28e03-140">受此法規制約的財務組織或 SCI 實體可以部署 Azure。</span><span class="sxs-lookup"><span data-stu-id="28e03-140">Financial organizations, or SCI entities, that are subject to this regulation can deploy Azure.</span></span> <span data-ttu-id="28e03-141">SEC 說其法規適用于 ' 自助組織（SROs），包括股票和選項交換、已註冊的清算機關、FINRA、MSRB、替代貿易系統（ATSs）、貿易 NMS 和非 NMS 股票超過指定的容量閾值、整合的市場資料 disseminators （計畫處理器）和特定的免除清算機關。 '</span><span class="sxs-lookup"><span data-stu-id="28e03-141">The SEC says its regulation applies to 'self-regulatory organizations (SROs), including stock and options exchanges, registered clearing agencies, FINRA, and the MSRB, alternative trading systems (ATSs), that trade NMS and non-NMS stocks exceeding specified volume thresholds, disseminators of consolidated market data (plan processors), and certain exempt clearing agencies.'</span></span>

## <a name="resources"></a><span data-ttu-id="28e03-142">資源</span><span class="sxs-lookup"><span data-stu-id="28e03-142">Resources</span></span>

- [<span data-ttu-id="28e03-143">每秒有關法規 SCI 的常見問題解答回應</span><span class="sxs-lookup"><span data-stu-id="28e03-143">SEC Responses to Frequently Asked Questions Concerning Regulation SCI</span></span>](https://www.sec.gov/divisions/marketreg/regulation-sci-faq.shtml)
- [<span data-ttu-id="28e03-144">商務持續性和嚴重損壞修復（BCDR）： Azure 配對區域</span><span class="sxs-lookup"><span data-stu-id="28e03-144">Business continuity and disaster recovery (BCDR): Azure Paired Regions</span></span>](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)
- [<span data-ttu-id="28e03-145">雲端計演算法規原則和 Microsoft Online Services 的合規性地圖</span><span class="sxs-lookup"><span data-stu-id="28e03-145">Compliance Map of Cloud Computing Regulatory Principles and Microsoft Online Services</span></span>](https://aka.ms/FinServ-Guide-US)
- [<span data-ttu-id="28e03-146">Microsoft 雲端財務服務合規性計劃</span><span class="sxs-lookup"><span data-stu-id="28e03-146">Microsoft Cloud Financial Services Compliance Program</span></span>](https://aka.ms/FSCP-Print)
- [<span data-ttu-id="28e03-147">Azure 的金融服務合規性</span><span class="sxs-lookup"><span data-stu-id="28e03-147">Financial services compliance in Azure</span></span>](https://aka.ms/FinServ-Compliance-Azure)
- [<span data-ttu-id="28e03-148">Microsoft 金融服務</span><span class="sxs-lookup"><span data-stu-id="28e03-148">Microsoft Financial Services</span></span>](https://aka.ms/FinServ-Compliance)
- [<span data-ttu-id="28e03-149">Microsoft 和 SEC Rule 17a-4</span><span class="sxs-lookup"><span data-stu-id="28e03-149">Microsoft and SEC Rule 17a-4</span></span>](offering-SEC-17a-4.md)
- [<span data-ttu-id="28e03-150">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="28e03-150">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
