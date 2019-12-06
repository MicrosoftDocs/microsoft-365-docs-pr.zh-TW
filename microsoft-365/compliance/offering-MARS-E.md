---
title: 交易可接受的最小風險標準 (MARS-E) 2.0 架構
description: Microsoft 符合美國交易可接受的最小風險標準 (MARS-E)。
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
ms.openlocfilehash: 27ef305d8f8df0469ec4d6d5f98b5c96127f0387
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859603"
---
# <a name="minimum-acceptable-risk-standards-for-exchanges-mars-e-20-framework"></a><span data-ttu-id="e7167-104">交易可接受的最小風險標準 (MARS-E) 2.0 架構</span><span class="sxs-lookup"><span data-stu-id="e7167-104">Minimum Acceptable Risk Standards for Exchanges (MARS-E) 2.0 Framework</span></span>

## <a name="mars-e-20-framework-overview"></a><span data-ttu-id="e7167-105">MARS-E 2.0 架構概觀</span><span class="sxs-lookup"><span data-stu-id="e7167-105">MARS-E 2.0 Framework overview</span></span>

<span data-ttu-id="e7167-106">在 2012 年，美國聯邦醫療保險和補助服務中心 (CMS) 發佈了交易可接受的最小風險標準 (MARS-E)，該標準依據 CMS 資訊安全性和隱私權計劃。</span><span class="sxs-lookup"><span data-stu-id="e7167-106">In 2012, the Center for Medicare and Medicaid Services (CMS) published the Minimum Acceptable Risk Standards for Exchanges (MARS-E) in accordance with CMS information security and privacy programs.</span></span> <span data-ttu-id="e7167-107">文件套件 (包括指導方針、需求及範本) 旨在解決患者保護與平價醫療法案 (ACA) 及採用 ACA 的美國衛生及公共服務部法規要求。</span><span class="sxs-lookup"><span data-stu-id="e7167-107">The suite of documents, including guidance, requirements, and templates, was designed to address mandates of the Patient Protection and Affordable Care Act (ACA) and regulations of the Department of Health and Human Services that apply to the ACA.</span></span> <span data-ttu-id="e7167-108">國家標準暨技術研究院 (NIST) 特別刊物 800-53 作為上層架構，可針對 ACA 要求健康情況交換與市場之間的所有系統、介面和連線，建立安全性與合規性需求。</span><span class="sxs-lookup"><span data-stu-id="e7167-108">The National Institute of Standards and Technology (NIST) Special Publication 800-53 serves as the parent framework that establishes the security and compliance requirements for all systems, interfaces, and connections between ACA-mandated health exchanges and marketplaces.</span></span>

<span data-ttu-id="e7167-109">在 MARS-E 發行之後，NIST 發行了更新，特別刊物 800-53r4，以解決日益增加的線上安全性挑戰，包括應用程式安全性；測試人員和進階持續威脅；供應鏈風險；以及行動裝置與雲端計算的可信賴度、保證及復原能力。</span><span class="sxs-lookup"><span data-stu-id="e7167-109">Following the release of MARS-E, NIST released an update, Special Publication 800-53r4, to address growing challenges to online security, including application security; insider and advanced persistent threats; supply chain risks; and the trustworthiness, assurance, and resilience of systems of mobile and cloud computing.</span></span> <span data-ttu-id="e7167-110">CMS 接著修訂 MARS-E 架構，以與 NIST 800.53r4 中的更新控制項和參數保持一致，在 2015 年發行 MARS-E 2.0。</span><span class="sxs-lookup"><span data-stu-id="e7167-110">CMS then revised the MARS-E framework to align with the updated controls and parameters in NIST 800.53r4, publishing MARS-E 2.0 in 2015.</span></span>

<span data-ttu-id="e7167-111">這些更新能解決受保護資料的健康情況交換機密性、完整性和可用性，其中包括個人識別資訊、受保護的健康資訊和聯邦稅務資訊。</span><span class="sxs-lookup"><span data-stu-id="e7167-111">These updates address the confidentiality, integrity, and availability in health exchanges of protected data, which includes personally identifiable information, protected health information, and federal tax information.</span></span> <span data-ttu-id="e7167-112">MARS-E 2.0 架構是用來保護受保護的資料，並適用於所有 ACA 管理實體，包括交換或市場：聯邦、州、國家醫療補助或兒童健康保險計劃 (CHIP) 機關，以及支援承包商。</span><span class="sxs-lookup"><span data-stu-id="e7167-112">The MARS-E 2.0 framework aims to secure this protected data and applies to all ACA administering entities, including exchanges or marketplaces — federal, state, state Medicaid, or Children’s Health Insurance Program (CHIP) agencies — and supporting contractors.</span></span>

## <a name="microsoft-and-mars-e-20-framework"></a><span data-ttu-id="e7167-113">Microsoft 和 MARS-E 2.0 架構</span><span class="sxs-lookup"><span data-stu-id="e7167-113">Microsoft and MARS-E 2.0 framework</span></span>

<span data-ttu-id="e7167-114">目前沒有適用於 MARS-E 的正式授權和資格鑑定程序。</span><span class="sxs-lookup"><span data-stu-id="e7167-114">Currently, there is no formal authorization and accreditation process for MARS-E.</span></span> <span data-ttu-id="e7167-115">不過，Microsoft Azure 平台服務已經歷「中等影響等級」的獨立 FedRAMP 稽核，以及「高等影響等級」的 Azure Government 稽核，並根據 FedRAMP 標準獲得授權。</span><span class="sxs-lookup"><span data-stu-id="e7167-115">However, Microsoft Azure platform services have undergone independent FedRAMP audits at the Moderate Impact Level and Azure Government at the High Impact Level, and are authorized according to FedRAMP standards.</span></span> <span data-ttu-id="e7167-116">雖然這些標準不會專門專注於 MARS-E，但是 MARS-E 控制項需求與目標緊密地保持一致，並致力於保護 Azure 上資料的機密性、完整性和可用性。</span><span class="sxs-lookup"><span data-stu-id="e7167-116">Although these standards do not specifically focus on MARS-E, the MARS-E control requirements and objectives are closely aligned and serve to protect the confidentiality, integrity, and availability of data on Azure.</span></span>

<span data-ttu-id="e7167-117">深入了解 MARS-E 2.0 架構在 Microsoft 雲端上的優點：[下載 MARS-E 背景資料](https://aka.ms/mars-e-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="e7167-117">Learn more about the benefits of MARS-E 2.0 Framework on the Microsoft Cloud: [Download the MARS-E backgrounder](https://aka.ms/mars-e-backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="e7167-118">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="e7167-118">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="e7167-119">Azure 和 Azure Government</span><span class="sxs-lookup"><span data-stu-id="e7167-119">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="e7167-120">Intune</span><span class="sxs-lookup"><span data-stu-id="e7167-120">Intune</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="e7167-121">稽核、報告和認證</span><span class="sxs-lookup"><span data-stu-id="e7167-121">Audits, reports, and certificates</span></span>

<span data-ttu-id="e7167-122">Microsoft 商務雲端服務每年會針對 FedRAMP 授權程序進行監視和評估。</span><span class="sxs-lookup"><span data-stu-id="e7167-122">Microsoft business cloud services are monitored and assessed each year for the FedRAMP authorization process.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="e7167-123">常見問題集</span><span class="sxs-lookup"><span data-stu-id="e7167-123">Frequently asked questions</span></span>

<span data-ttu-id="e7167-124">**該標準適用於誰？**</span><span class="sxs-lookup"><span data-stu-id="e7167-124">**To whom does the standard apply?**</span></span>

<span data-ttu-id="e7167-125">MARS-E 適用於所有平價醫療法案管理實體，包括交換或市場，例如管理基本健康計劃的聯邦、州、醫療補助和 CHIP 機構，以及其所有承包商和轉包商。</span><span class="sxs-lookup"><span data-stu-id="e7167-125">MARS-E applies to all Affordable Care Act administering entities, including exchanges or marketplaces — federal, state, Medicaid, and CHIP agencies administering the Basic Health Program — as well as all their contractors and subcontractors.</span></span>

<span data-ttu-id="e7167-126">**Microsoft 如何使用這個標準示範 Azure 和 Azure Government 合規性？**</span><span class="sxs-lookup"><span data-stu-id="e7167-126">**How does Microsoft demonstrate Azure and Azure Government compliance with this standard?**</span></span>

<span data-ttu-id="e7167-127">使用第三方針對 FedRAMP 授權所準備的正式稽核報告，Microsoft 可以顯示相關控制項所述的資訊，這些報告示範 Azure 功能符合 MARS-E 安全性和隱私權控制項需求。</span><span class="sxs-lookup"><span data-stu-id="e7167-127">Using the formal audit reports prepared by third parties for FedRAMP authorizations, Microsoft is able to show how relevant controls noted that within these reports demonstrate Azure capabilities in meeting MARS-E security and privacy control requirements.</span></span> <span data-ttu-id="e7167-128">Microsoft 所實作的已稽核控制項，可保護儲存在 Azure 平台上資料的機密性、完整性和可用性，並對應至 MARS-E 中識別為Microsoft 責任的已定義適用法規需求。</span><span class="sxs-lookup"><span data-stu-id="e7167-128">Audited controls implemented by Microsoft serve to protect the confidentiality, integrity, and availability of data stored on the Azure platform, and correspond to the applicable regulatory requirements defined in MARS-E that have been identified as the responsibility of Microsoft.</span></span>

<span data-ttu-id="e7167-129">**使用這個標準時，Microsoft 對維護合規性有何責任？**</span><span class="sxs-lookup"><span data-stu-id="e7167-129">**What are Microsoft's responsibilities for maintaining compliance with this standard?**</span></span>

<span data-ttu-id="e7167-130">Microsoft 可確保 Azure 平台符合管理[線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)和適用服務等級協定 (SLA) 中定義的條款。</span><span class="sxs-lookup"><span data-stu-id="e7167-130">Microsoft ensures that the Azure platform meets the terms defined within the governing [Online Services Terms](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31) and applicable service level agreements (SLAs).</span></span> <span data-ttu-id="e7167-131">這些條款定義我們對於實作及維護足以保護 Azure 平台和監視系統控制項的職責。</span><span class="sxs-lookup"><span data-stu-id="e7167-131">These define our responsibility for implementing and maintaining controls adequate to secure the Azure platform and monitor the system.</span></span>

<span data-ttu-id="e7167-132">**我是否可以為我的組織在 MARS-E 資格考核中使用 Microsoft 合規性？**</span><span class="sxs-lookup"><span data-stu-id="e7167-132">**Can I use Microsoft's compliance in the MARS-E qualification efforts for my organization?**</span></span>

<span data-ttu-id="e7167-133">是。</span><span class="sxs-lookup"><span data-stu-id="e7167-133">Yes.</span></span> <span data-ttu-id="e7167-134">FedRAMP 標準的第三方稽核報告證明 Microsoft 為了維護 Azure 平台安全性和隱私權而實作的控制項有效性。</span><span class="sxs-lookup"><span data-stu-id="e7167-134">Third-party audit reports to the FedRAMP standards attest to the effectiveness of the controls Microsoft has implemented to maintain the security and privacy of the Azure platform.</span></span> <span data-ttu-id="e7167-135">Azure 和 Azure Government 客戶可以使用這些相關報告中所述的已稽核控制項作為自己 FedRAMP 和 MARS-E 風險分析和資格考核的一部分。</span><span class="sxs-lookup"><span data-stu-id="e7167-135">Azure and Azure Government customers may use the audited controls described in these related reports as part of their own FedRAMP and MARS-E risk analysis and qualification efforts.</span></span>

## <a name="resources"></a><span data-ttu-id="e7167-136">資源</span><span class="sxs-lookup"><span data-stu-id="e7167-136">Resources</span></span>

- <span data-ttu-id="e7167-137">MARS-E 法規指導方針，MARS-E 文件套件，2.0 版</span><span class="sxs-lookup"><span data-stu-id="e7167-137">MARS-E regulatory guidance, MARS-E Document Suite, Version 2.0</span></span>
    - [<span data-ttu-id="e7167-138">第 II 卷：交易可接受的最小風險標準</span><span class="sxs-lookup"><span data-stu-id="e7167-138">Volume II: Minimum acceptable risk standards for exchanges</span></span>](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/2-MARS-E-v2-0-Minimum-Acceptable-Risk-Standards-for-Exchanges-11102015.pdf)
    - [<span data-ttu-id="e7167-139">第 III 卷：適用於交換可接受的最小風險安全性與隱私權控制項的目錄</span><span class="sxs-lookup"><span data-stu-id="e7167-139">Volume III: Catalog of minimum acceptable risk security and privacy controls for exchanges</span></span>](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/3-MARS-E-v2-0-Catalog-of-Security-and-Privacy-Controls-11102015.pdf)
- [<span data-ttu-id="e7167-140">線上服務的 Microsoft 合規性架構白皮書</span><span class="sxs-lookup"><span data-stu-id="e7167-140">Microsoft compliance framework for online services white paper</span></span>](https://aka.ms/compliance-framework)
- [<span data-ttu-id="e7167-141">Microsoft Online Services 條款</span><span class="sxs-lookup"><span data-stu-id="e7167-141">Microsoft Online Services Terms</span></span>](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)
- [<span data-ttu-id="e7167-142">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="e7167-142">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="e7167-143">下載方案背景資料</span><span class="sxs-lookup"><span data-stu-id="e7167-143">Download the offering backgrounder</span></span>

<span data-ttu-id="e7167-144">是否需要此方案的背景資料文件？</span><span class="sxs-lookup"><span data-stu-id="e7167-144">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="e7167-145">下載 [PDF](https://download.microsoft.com/download/7/C/2/7C2690A7-19CC-4EED-A47A-B43CC418790A/MARS-E-Compliance.pdf)。</span><span class="sxs-lookup"><span data-stu-id="e7167-145">Download the [PDF](https://download.microsoft.com/download/7/C/2/7C2690A7-19CC-4EED-A47A-B43CC418790A/MARS-E-Compliance.pdf).</span></span>
