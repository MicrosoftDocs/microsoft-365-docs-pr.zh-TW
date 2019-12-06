---
title: 合規性方案 - 雲端安全性聯盟 (CSA) STAR 自我評定
description: Microsoft STAR 自我評定詳細說明雲端服務如何符合雲端安全性聯盟需求。
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
ms.openlocfilehash: 73a21ba3089646df55ad51a7918749f29691aad8
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859423"
---
# <a name="cloud-security-alliance-csa-star-self-assessment"></a><span data-ttu-id="8cbd9-104">雲端安全性聯盟 (CSA) STAR 自我評定</span><span class="sxs-lookup"><span data-stu-id="8cbd9-104">Compliance offering: Cloud Security Alliance (CSA) STAR self-assessment</span></span>

## <a name="csa-star-self-assessment-overview"></a><span data-ttu-id="8cbd9-105">CSA STAR 自我評定概觀</span><span class="sxs-lookup"><span data-stu-id="8cbd9-105">CSA STAR self-assessment overview</span></span>

<span data-ttu-id="8cbd9-106">雲端安全性聯盟 (CSA) 是一個非贏利組織，由廣泛的行業從業者、公司和其他重要專案關係人聯盟所領導。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-106">The Cloud Security Alliance (CSA) is a nonprofit organization led by a broad coalition of industry practitioners, corporations, and other important stakeholders.</span></span> <span data-ttu-id="8cbd9-107">該組織致力於定義最佳做法，以協助確保更安全的雲端運算環境，並協助潛在的雲端客戶在將其 IT 營運轉換到雲端時做出明智的決策。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-107">It is dedicated to defining best practices to help ensure a more secure cloud computing environment, and to helping potential cloud customers make informed decisions when transitioning their IT operations to the cloud.</span></span>  
  
<span data-ttu-id="8cbd9-108">在 2010 年，CSA 發佈了一套可評估雲端 IT 營運的工具：CSA Governance、Risk Management 及 Compliance (GRC) Stack。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-108">In 2010, the CSA published a suite of tools to assess cloud IT operations: the CSA Governance, Risk Management, and Compliance (GRC) Stack.</span></span> <span data-ttu-id="8cbd9-109">這是專為協助雲端客戶評估雲端服務提供者 (CSP) 遵循業界最佳做法和標準並遵守法規的方式而設計。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-109">It was designed to help cloud customers assess how cloud service providers (CSPs) follow industry best practices and standards and comply with regulations.</span></span>  
  
<span data-ttu-id="8cbd9-110">在 2013 年，CSA 和英國標準協會 (British Standards Institution) 推出了安全性、信任與保證註冊 (STAR)，這是一個免費且可公開存取的註冊服務，CSA 可以在其中發佈與 CSA 相關的評定。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-110">In 2013, the CSA and the British Standards Institution launched the Security, Trust & Assurance Registry (STAR), a free, publicly accessible registry in which CSPs can publish their CSA-related assessments.</span></span>  
  
<span data-ttu-id="8cbd9-111">CSA STAR 是以 CSA GRC Stack 的兩個重要元件為基礎：</span><span class="sxs-lookup"><span data-stu-id="8cbd9-111">CSA STAR is based on two key components of the CSA GRC Stack:</span></span>

- <span data-ttu-id="8cbd9-112">雲端控制矩陣 (CCM)：這是一個控制措施架構，涵蓋 16 個網域之間的基本安全性原則，以協助雲端客戶評估 CSP 的整體安全性風險。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-112">Cloud Controls Matrix (CCM): a controls framework covering fundamental security principles across 16 domains to help cloud customers assess the overall security risk of a CSP.</span></span>
- <span data-ttu-id="8cbd9-113">自我評定問卷 (Consensus Assessments Initiative Questionnaire，CAIQ)：以 CCM 為主的 140 多個問題，客戶或雲端稽核人員可能會想要詢問 CSP，以評估其對 CSA 最佳做法的合規性。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-113">The Consensus Assessments Initiative Questionnaire (CAIQ): a set of more than 140 questions based on the CCM that a customer or cloud auditor may want to ask of CSPs to assess their compliance with CSA best practices.</span></span>

<span data-ttu-id="8cbd9-114">STAR 提供三個保證層級；CSA-STAR 自我評定是層級 1 的介紹性方案，免費開放給所有 CSP 使用。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-114">STAR provides three levels of assurance; CSA-STAR Self-Assessment is the introductory offering at Level 1, which is free and open to all CSPs.</span></span> <span data-ttu-id="8cbd9-115">STAR 方案的層級 2 進一步提升保證堆疊，其中涉及協力廠商評定的認證，而層級 3 則涉及以持續監視為主的認證。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-115">Going further up the assurance stack, Level 2 of the STAR program involves third-party assessment-based certifications, and Level 3 involves certifications based on continuous monitoring.</span></span>

## <a name="microsoft-and-csa-star-self-assessment"></a><span data-ttu-id="8cbd9-116">Microsoft 和 CSA STAR 自我評定</span><span class="sxs-lookup"><span data-stu-id="8cbd9-116">Microsoft and CSA STAR self-assessment</span></span>

<span data-ttu-id="8cbd9-117">在 STAR 自我評定中，CSP 可以提交下列兩種不同類型的文件，以表示對 CSA 最佳做法的合規性：已完成的 CAIQ，或是記載對 CCM 之合規性的報告。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-117">As part of the STAR Self-Assessment, CSPs can submit two different types of documents to indicate their compliance with CSA best practices: a completed CAIQ, or a report documenting compliance with CCM.</span></span> <span data-ttu-id="8cbd9-118">對於 CSA STAR 自我評定，Microsoft 會為 Microsoft Azure 發佈將 CAIQ 和 CCM 的報告，並為 Microsoft Dynamics 365 和 Microsoft Office 365 發佈 CCM 的報告。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-118">For the CSA STAR Self-Assessment, Microsoft publishes both a CAIQ and a CCM-based report for Microsoft Azure, and CCM-based reports for Microsoft Dynamics 365 and Microsoft Office 365.</span></span>  
  
<span data-ttu-id="8cbd9-119">了解 Microsoft 雲端上的 CSA STAR 自我評定優點：[下載 CSA STAR 自我評定背景資料](https://aka.ms/csastar-selfassessment-backgrounder) \(英文\)</span><span class="sxs-lookup"><span data-stu-id="8cbd9-119">Learn about the benefits of CSA STAR Self-Assessment on the Microsoft Cloud: [Download the CSA STAR Self-Assessment backgrounder](https://aka.ms/csastar-selfassessment-backgrounder)</span></span>

<span data-ttu-id="8cbd9-120">了解如何透過 Azure 安全性和合規性藍圖，加速您的 CSA STAR 自我評定部署：[下載 Azure 針對 CSA 自我評定的回應](https://gallery.technet.microsoft.com/Azure-Responses-to-CSA-46034a11) \(英文\)</span><span class="sxs-lookup"><span data-stu-id="8cbd9-120">Learn how to accelerate your CSA STAR Self-Assessment deployment with our Azure Security and Compliance Blueprint: [Download Azure response to the CSA Consensus Assessments](https://gallery.technet.microsoft.com/Azure-Responses-to-CSA-46034a11)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="8cbd9-121">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="8cbd9-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="8cbd9-122">Azure 和 Azure Government</span><span class="sxs-lookup"><span data-stu-id="8cbd9-122">Azure and Azure Government</span></span>](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [<span data-ttu-id="8cbd9-123">Dynamics 365 CSA STAR 自我評定</span><span class="sxs-lookup"><span data-stu-id="8cbd9-123">Dynamics 365 CSA STAR Self-Assessment</span></span>](https://cloudsecurityalliance.org/star/registry/microsoft/)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="8cbd9-124">稽核、報告和憑證</span><span class="sxs-lookup"><span data-stu-id="8cbd9-124">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="8cbd9-125">Azure 標準資訊要求回應</span><span class="sxs-lookup"><span data-stu-id="8cbd9-125">Azure standard response for request for information</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7ca8423-1bc5-4be0-bff8-b6056f87c134&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)
- [<span data-ttu-id="8cbd9-126">Azure 雲端安全性聯盟 CAIQ</span><span class="sxs-lookup"><span data-stu-id="8cbd9-126">Azure Cloud Security Alliance CAIQ</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a966a424-ecfd-4de2-9739-b08aee2d3ca0&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)
- [<span data-ttu-id="8cbd9-127">Azure 針對 CSA CAIQ v3.0.1 的回應</span><span class="sxs-lookup"><span data-stu-id="8cbd9-127">Azure responses to the CSA CAIQ v3.0.1</span></span>](https://gallery.technet.microsoft.com/Azure-Responses-to-CSA-46034a11)

## <a name="frequently-asked-questions"></a><span data-ttu-id="8cbd9-128">常見問題集</span><span class="sxs-lookup"><span data-stu-id="8cbd9-128">Frequently asked questions</span></span>

<span data-ttu-id="8cbd9-129">**CSA CCM 符合哪些產業標準？**</span><span class="sxs-lookup"><span data-stu-id="8cbd9-129">**Which industry standards does the CSA CCM align with?**</span></span>

<span data-ttu-id="8cbd9-130">CCM 符合產業公認的安全性標準、規定及控制措施架構，例如：ISO 27001、PCI DSS、HIPAA、AICPA SOC 2、NERC CIP、FedRAMP、NIST 等等。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-130">The CCM corresponds to industry-accepted security standards, regulations, and control frameworks such as ISO 27001, PCI DSS, HIPAA, AICPA SOC 2, NERC CIP, FedRAMP, NIST, and many more.</span></span> <span data-ttu-id="8cbd9-131">如需最新清單，請瀏覽 [CSA 網站](https://cloudsecurityalliance.org/)。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-131">For the most current list, visit the [CSA website](https://cloudsecurityalliance.org/).</span></span>

<span data-ttu-id="8cbd9-132">**為什麼 CSA STAR 自我評定很重要？**</span><span class="sxs-lookup"><span data-stu-id="8cbd9-132">**Why is the CSA STAR Self-Assessment important?**</span></span>

<span data-ttu-id="8cbd9-133">它可讓 CSP 以透明的方式記載對 CSA 發佈的最佳做法的合規性。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-133">It enables CSPs to document compliance with CSA published best practices in a transparent manner.</span></span> <span data-ttu-id="8cbd9-134">自我評定報告可公開取得，因此可協助雲端客戶深入了解 CSP 的安全性做法，並使用相同的基準來比較不同的 CSP。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-134">Self-assessment reports are publicly available, thereby helping cloud customers gain visibility into the security practices of CSPs, and compare various CSPs using the same baseline.</span></span>

<span data-ttu-id="8cbd9-135">**Microsoft 商務雲端服務達到哪些 CSA STAR 保證層級？**</span><span class="sxs-lookup"><span data-stu-id="8cbd9-135">**Which CSA STAR levels of assurance have Microsoft business cloud services attained?**</span></span>

- <span data-ttu-id="8cbd9-136">**層級 1**：**CSA STAR 自我評定**：Azure、Dynamics 365 和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-136">**Level 1**: **CSA STAR Self-Assessment**: Azure, Dynamics 365, and Office 365.</span></span> <span data-ttu-id="8cbd9-137">「自我評定」是雲端服務提供者所提供的免費方案，用於記載其安全性控制措施以協助客戶評估服務安全性。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-137">The Self-Assessment is a complimentary offering from cloud service providers to document their security controls to help customers assess the security of the service.</span></span>
- <span data-ttu-id="8cbd9-138">**層級 2**：**CSA STAR 認證**：Azure、Cloud App Security、Intune 和 Power BI。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-138">**Level 2**: **CSA STAR Certification**: Azure, Cloud App Security, Intune, and Power BI.</span></span> <span data-ttu-id="8cbd9-139">STAR 認證是以獲得 ISO/IEC 27001 認證並符合 CCM 中指定的準則為基礎。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-139">STAR Certification is based on achieving ISO/IEC 27001 certification and meeting criteria specified in the CCM.</span></span> <span data-ttu-id="8cbd9-140">該認證是在第三方嚴格評定雲端服務提供者的安全性控制措施和做法之後頒發。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-140">It is awarded after a rigorous third-party assessment of the security controls and practices of a cloud service provider.</span></span>
- <span data-ttu-id="8cbd9-141">**層級 2**：**CSA STAR 證明**：Azure 和 Intune。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-141">**Level 2**: **CSA STAR Attestation**: Azure and Intune.</span></span> <span data-ttu-id="8cbd9-142">CSA 和 AICPA 使用 AICPA (信任服務原則 AT 101) 和 CSA CCM 的準則，為進行 SOC 2 業務的 CPA 共同提供指導方針。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-142">CSA and the AICPA have collaborated to provide guidelines for CPAs to use in conducting SOC 2 engagements, using criteria from the AICPA (Trust Service Principles, AT 101) and the CSA CCM.</span></span> <span data-ttu-id="8cbd9-143">「STAR 證明」是以這些指導方針為基礎，並對雲端提供者進行嚴格的獨立評定之後頒發。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-143">STAR Attestation is based on these guidelines and is awarded after rigorous independent assessments of cloud providers.</span></span>

## <a name="resources"></a><span data-ttu-id="8cbd9-144">資源</span><span class="sxs-lookup"><span data-stu-id="8cbd9-144">Resources</span></span>

- [<span data-ttu-id="8cbd9-145">雲端安全性聯盟</span><span class="sxs-lookup"><span data-stu-id="8cbd9-145">Cloud Security Alliance</span></span>](https://cloudsecurityalliance.org/)
- [<span data-ttu-id="8cbd9-146">雲端控制矩陣 (CCM)</span><span class="sxs-lookup"><span data-stu-id="8cbd9-146">Cloud Controls Matrix (CCM)</span></span>](https://cloudsecurityalliance.org/group/cloud-controls-matrix/)
- [<span data-ttu-id="8cbd9-147">自我評定問卷 (CAIQ)</span><span class="sxs-lookup"><span data-stu-id="8cbd9-147">Consensus Assessments Initiative Questionnaire (CAIQ)</span></span>](https://cloudsecurityalliance.org/group/consensus-assessments/)
- [<span data-ttu-id="8cbd9-148">CSA 安全性、信任與保證註冊 (STAR)</span><span class="sxs-lookup"><span data-stu-id="8cbd9-148">CSA Security, Trust & Assurance Registry (STAR)</span></span>](https://cloudsecurityalliance.org/star/)
- [<span data-ttu-id="8cbd9-149">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="8cbd9-149">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="microsoft-csa-star-self-assessments"></a><span data-ttu-id="8cbd9-150">Microsoft CSA STAR 自我評定</span><span class="sxs-lookup"><span data-stu-id="8cbd9-150">Microsoft CSA STAR self-assessments</span></span>

- [<span data-ttu-id="8cbd9-151">Azure</span><span class="sxs-lookup"><span data-stu-id="8cbd9-151">Azure</span></span>](https://aka.ms/Azure_STAR)
- [<span data-ttu-id="8cbd9-152">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8cbd9-152">Dynamics 365</span></span>](https://aka.ms/DynamicsCRM_Online_STAR)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="8cbd9-153">下載方案背景資料</span><span class="sxs-lookup"><span data-stu-id="8cbd9-153">Download the offering backgrounder</span></span>

<span data-ttu-id="8cbd9-154">是否需要此方案的背景資料文件？</span><span class="sxs-lookup"><span data-stu-id="8cbd9-154">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="8cbd9-155">下載 [PDF](https://download.microsoft.com/download/7/C/E/7CE08DFE-86D6-4690-9455-5123DA0A7C09/CSA-STAR-SelfAssessment-Compliance.pdf)。</span><span class="sxs-lookup"><span data-stu-id="8cbd9-155">Download the [PDF](https://download.microsoft.com/download/7/C/E/7CE08DFE-86D6-4690-9455-5123DA0A7C09/CSA-STAR-SelfAssessment-Compliance.pdf).</span></span>

