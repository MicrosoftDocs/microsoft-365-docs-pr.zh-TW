---
title: 國民健保 (NHS) 資訊控管 (IG) 工具組
description: Azure 是經健康資訊信任聯盟一般安全性架構所認證。
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
ms.openlocfilehash: 69cc897f749a591da9bdc69057bccf2dc96351da
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859533"
---
# <a name="national-health-service-nhs-information-governance-ig-toolkit"></a><span data-ttu-id="63e2d-104">國民健保 (NHS) 資訊控管 (IG) 工具組</span><span class="sxs-lookup"><span data-stu-id="63e2d-104">National Health Service (NHS) Information Governance (IG) Toolkit</span></span>

## <a name="nhs-ig-toolkit-overview"></a><span data-ttu-id="63e2d-105">NHS IG 工具組概觀</span><span class="sxs-lookup"><span data-stu-id="63e2d-105">NHS IG Toolkit overview</span></span>

<span data-ttu-id="63e2d-106">國民健保 (NHS) 是英國的國家醫療體系，為英國公民提供大部分醫療保健服務，涵蓋所有照護作業領域。</span><span class="sxs-lookup"><span data-stu-id="63e2d-106">The National Health Service (NHS) is the national health system for England, and provides most of the healthcare for the citizens of England, covering all healthcare practice areas.</span></span> <span data-ttu-id="63e2d-107">NHS 創立於 1948 年，是世界上第一個單一支付者的醫療體系。</span><span class="sxs-lookup"><span data-stu-id="63e2d-107">Founded in 1948, the NHS was the world’s first single-payer health system.</span></span> <span data-ttu-id="63e2d-108">這也是世界上最大的醫療體系，雇用了超過 150 萬人，2016 年的預算為 1164 億英鎊。</span><span class="sxs-lookup"><span data-stu-id="63e2d-108">It is also the world’s largest health system, employing over 1.5 million people with a 2016 budget of £116.4 billion.</span></span>

<span data-ttu-id="63e2d-109">NHS 管理超過 6400 萬 NHS 病患的健康資料。</span><span class="sxs-lookup"><span data-stu-id="63e2d-109">The NHS manages the health data of more than 64 million NHS patients.</span></span> <span data-ttu-id="63e2d-110">NHS 病患資料的收集、儲存和處理受多項法令規定的約束，包括 1998 年資料保護法 (Data Protection Act) 和機密性 NHS 實務規範。</span><span class="sxs-lookup"><span data-stu-id="63e2d-110">The collection, storage, and processing of NHS patient data are subject to multiple laws and regulations, including the Data Protection Act of 1998 and the Confidentiality NHS Code of Practice.</span></span>

<span data-ttu-id="63e2d-111">NHS 委託健康與社會照護資訊中心 (HSCIC) 制定並維護管理病患資料收集、儲存和處理的單一標準，即[資訊控管 (IG) 工具組](https://www.igt.hscic.gov.uk/resources/About%20the%20IG%20Toolkit.pdf)。</span><span class="sxs-lookup"><span data-stu-id="63e2d-111">The NHS commissioned the Health and Social Care Information Centre (HSCIC) to develop and maintain a single standard that governs the collection, storage, and processing of patient data, the [Information Governance (IG) Toolkit](https://www.igt.hscic.gov.uk/resources/About%20the%20IG%20Toolkit.pdf).</span></span> <span data-ttu-id="63e2d-112">IG 工具組旨在鼓勵和指導有意透過遵循指導方針的流程來託管個人健康資料的組織。</span><span class="sxs-lookup"><span data-stu-id="63e2d-112">The IG Toolkit is designed to encourage and guide organizations that are interested in hosting personal health data through the process of complying with the guidelines.</span></span>

<span data-ttu-id="63e2d-113">所有有權存取 NHS 病患資料的組織都需要使用 NHS IG 工具組提供證據，證明他們正在採取適當措施保護病患資料。</span><span class="sxs-lookup"><span data-stu-id="63e2d-113">All organizations that have access to NHS patient data are required to provide evidence, by using the NHS IG Toolkit, that they are taking adequate measures to protect patient data.</span></span>

<span data-ttu-id="63e2d-114">此外，像 Microsoft 這樣的為醫療保健提供者提供平台的組織也使用該工具組針對 NHS 資訊控管、安全性和隱私權要求，對他們的安全性和隱私權控制進行自我評估。</span><span class="sxs-lookup"><span data-stu-id="63e2d-114">Also, organizations such as Microsoft that provide a platform for healthcare providers use the toolkit to conduct a self-assessment on their security and privacy controls against NHS information governance, security, and privacy requirements.</span></span>

<span data-ttu-id="63e2d-115">遵守 NHS IG 工具組有助於保護病患資料的完整性和機密性，避免未經授權的存取、遺失、損壞和毀壞。</span><span class="sxs-lookup"><span data-stu-id="63e2d-115">Adherence with the NHS IG Toolkit helps protect the integrity and confidentiality of patient data against unauthorized access, loss, damage, and destruction.</span></span> <span data-ttu-id="63e2d-116">必須採取適當的緩解步驟，以補救在評估過程中發現的任何不符合合規性問題。</span><span class="sxs-lookup"><span data-stu-id="63e2d-116">Appropriate mitigating steps must be taken to remediate any noncompliance issues identified during the assessment process.</span></span>

<span data-ttu-id="63e2d-117">NHS IG 工具組旨在：</span><span class="sxs-lookup"><span data-stu-id="63e2d-117">The NHS IG Toolkit is intended to:</span></span>

- <span data-ttu-id="63e2d-118">提供標準，解決客戶對 NHS 病患資料安全性和機密性，以及對業務之影響的共同顧慮</span><span class="sxs-lookup"><span data-stu-id="63e2d-118">Provide a standard to address common customer concerns about the security and confidentiality of NHS patient data and the impact on business</span></span>
- <span data-ttu-id="63e2d-119">展示可衡量的合規性，並深入了解病患資料的潛在風險</span><span class="sxs-lookup"><span data-stu-id="63e2d-119">Demonstrate measurable compliance and provide visibility into potential risks to patient data</span></span>
- <span data-ttu-id="63e2d-120">提升 NHS 和合作夥伴組織的信任和公眾信任</span><span class="sxs-lookup"><span data-stu-id="63e2d-120">Promote trust and public confidence in NHS and partner organizations</span></span>

## <a name="microsoft-and-nhs-ig-toolkit"></a><span data-ttu-id="63e2d-121">Microsoft 與 NHS IG 工具組</span><span class="sxs-lookup"><span data-stu-id="63e2d-121">Microsoft and NHS IG Toolkit</span></span>

<span data-ttu-id="63e2d-122">作為商業協力廠商，Microsoft Azure 已完成 [NHS IG 工具組評估](https://www.igt.hscic.gov.uk/AssessmentReportCriteria.aspx?tk=427399452776248&lnv=3&cb=48ea00e0-c594-4758-8634-f22b6efa0c39&sViewOrgId=50721&sDesc=8JH14)等級 2。</span><span class="sxs-lookup"><span data-stu-id="63e2d-122">As a commercial third party, Microsoft Azure has completed level 2 of the [NHS IG Toolkit assessment](https://www.igt.hscic.gov.uk/AssessmentReportCriteria.aspx?tk=427399452776248&lnv=3&cb=48ea00e0-c594-4758-8634-f22b6efa0c39&sViewOrgId=50721&sDesc=8JH14).</span></span> <span data-ttu-id="63e2d-123">中期評估預計在發佈新版本的 NHS IG 工具組時完成。</span><span class="sxs-lookup"><span data-stu-id="63e2d-123">Interim assessments are also expected to be completed during the year when a new version of the NHS IG Toolkit is released.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="63e2d-124">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="63e2d-124">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="63e2d-125">Azure 和 Azure Government</span><span class="sxs-lookup"><span data-stu-id="63e2d-125">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="63e2d-126">Intune</span><span class="sxs-lookup"><span data-stu-id="63e2d-126">Intune</span></span>
- <span data-ttu-id="63e2d-127">Power BI：雲端服務可作為獨立服務或包含在 Office 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="63e2d-127">Power BI: cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="63e2d-128">稽核、報告和憑證</span><span class="sxs-lookup"><span data-stu-id="63e2d-128">Audits, reports, and certificates</span></span>

<span data-ttu-id="63e2d-129">Azure 評估每年續約一次：[Microsoft Azure IG 工具組評定報告](https://www.igt.hscic.gov.uk/AssessmentReportCriteria.aspx?tk=427399452776248&lnv=3&cb=48ea00e0-c594-4758-8634-f22b6efa0c39&sViewOrgId=50721&sDesc=8JH14)</span><span class="sxs-lookup"><span data-stu-id="63e2d-129">The Azure assessment is renewed annually: [Microsoft Azure IG Toolkit Assessment Report](https://www.igt.hscic.gov.uk/AssessmentReportCriteria.aspx?tk=427399452776248&lnv=3&cb=48ea00e0-c594-4758-8634-f22b6efa0c39&sViewOrgId=50721&sDesc=8JH14)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="63e2d-130">常見問題集</span><span class="sxs-lookup"><span data-stu-id="63e2d-130">Frequently asked questions</span></span>

<span data-ttu-id="63e2d-131">**誰可以利用 Azure NHS IG 工具組評估？**</span><span class="sxs-lookup"><span data-stu-id="63e2d-131">**Who can take advantage of the Azure NHS IG Toolkit assessment?**</span></span>

<span data-ttu-id="63e2d-132">希望使用 Microsoft Azure 作為託管 NHS 病患資料之平台的組織可以在 Microsoft 的評定報告的基礎上啟動自己的 NHS IG 工具組評估，同時牢記他們還必須處理任何其他控制措施，特別是那些不由雲端服務提供者負責的控制措施。</span><span class="sxs-lookup"><span data-stu-id="63e2d-132">Organizations that want to use Microsoft Azure as a platform to host NHS patient data can build on Microsoft’s assessment report to launch their own NHS IG Toolkit assessment, keeping in mind that they also must address any additional controls, especially those not under the responsibility of the Cloud Service Provider.</span></span>

<span data-ttu-id="63e2d-133">**我要從何處著手組織自身的合規性工作？**</span><span class="sxs-lookup"><span data-stu-id="63e2d-133">**Where do I start with my organization’s own compliance effort?**</span></span>

<span data-ttu-id="63e2d-134">鼓勵有意託管 NHS 病患資料的組織透過[檢閱 NHS IG 工具組指導方針](https://www.igt.hscic.gov.uk/requirementsorganisation.aspx)來確定其必須具備的範圍和控制措施，以熟悉管理要求。</span><span class="sxs-lookup"><span data-stu-id="63e2d-134">Organizations that are interested in hosting NHS patient data are encouraged to become familiar with the governing requirements by [reviewing the NHS IG Toolkit guidelines](https://www.igt.hscic.gov.uk/requirementsorganisation.aspx) to determine the scope and controls that they must have in place.</span></span>

<span data-ttu-id="63e2d-135">**IG 工具組的等級為何？**</span><span class="sxs-lookup"><span data-stu-id="63e2d-135">**What are the IG Toolkit attainment levels?**</span></span>

<span data-ttu-id="63e2d-136">IG 工具組的等級為 0 到 3：</span><span class="sxs-lookup"><span data-stu-id="63e2d-136">IG Toolkit attainment levels are from 0 to 3:</span></span>

- <span data-ttu-id="63e2d-137">沒有足夠的證據達到等級 1</span><span class="sxs-lookup"><span data-stu-id="63e2d-137">There is insufficient evidence to attain level 1</span></span>
- <span data-ttu-id="63e2d-138">組織已開始規劃符合規範所需的原則、程式和/或流程</span><span class="sxs-lookup"><span data-stu-id="63e2d-138">The organization has begun to plan the policies, procedures, and/or processes that are necessary to become compliant</span></span>
- <span data-ttu-id="63e2d-139">已核准並實作的 IG 原則和程序已提供給所有相關員工</span><span class="sxs-lookup"><span data-stu-id="63e2d-139">There are approved and implemented IG policies and procedures in place that have been made available to all relevant staff</span></span>
- <span data-ttu-id="63e2d-140">監控並確保員工合規性，以及原則和程序的有效性</span><span class="sxs-lookup"><span data-stu-id="63e2d-140">Staff compliance and the effectiveness of the policies and procedures are monitored and assured</span></span>

## <a name="resources"></a><span data-ttu-id="63e2d-141">資源</span><span class="sxs-lookup"><span data-stu-id="63e2d-141">Resources</span></span>

- [<span data-ttu-id="63e2d-142">資訊控管工具組</span><span class="sxs-lookup"><span data-stu-id="63e2d-142">Information Governance Toolkit</span></span>](https://www.igt.hscic.gov.uk/)
- [<span data-ttu-id="63e2d-143">Microsoft Azure IG 工具組評定報告</span><span class="sxs-lookup"><span data-stu-id="63e2d-143">Microsoft Azure IG Toolkit Assessment Report</span></span>](https://www.igt.hscic.gov.uk/AssessmentReportCriteria.aspx?tk=427399452776248&lnv=3&cb=48ea00e0-c594-4758-8634-f22b6efa0c39&sViewOrgId=50721&sDesc=8JH14)
- [<span data-ttu-id="63e2d-144">IG 工具組需求</span><span class="sxs-lookup"><span data-stu-id="63e2d-144">IG Toolkit requirements</span></span>](https://www.igt.hscic.gov.uk/requirementsorganisation.aspx?tk=427399392327814&cb=5815499d-070a-49e2-ac2e-c70d74d81ddc&lnv=2&clnav=YES)
- [<span data-ttu-id="63e2d-145">IG 工具組常見問題集</span><span class="sxs-lookup"><span data-stu-id="63e2d-145">IG Toolkit FAQ</span></span>](https://www.igt.hscic.gov.uk/resources/About%20the%20IG%20Toolkit.pdf)
- [<span data-ttu-id="63e2d-146">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="63e2d-146">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="63e2d-147">下載方案背景資料</span><span class="sxs-lookup"><span data-stu-id="63e2d-147">Download the offering backgrounder</span></span>

<span data-ttu-id="63e2d-148">是否需要此方案的背景資料文件？</span><span class="sxs-lookup"><span data-stu-id="63e2d-148">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="63e2d-149">下載 [PDF](https://download.microsoft.com/download/7/F/6/7F6EBDDE-F3EF-4225-ACDA-ADCD851430C4/NHS_IG-Compliance.pdf)。</span><span class="sxs-lookup"><span data-stu-id="63e2d-149">Download the [PDF](https://download.microsoft.com/download/7/F/6/7F6EBDDE-F3EF-4225-ACDA-ADCD851430C4/NHS_IG-Compliance.pdf).</span></span>
