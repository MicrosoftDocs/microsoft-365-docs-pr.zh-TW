---
title: NIST SP 800-171
description: NIST SP 800-171 指導方針來保護出版資訊系統中的控管的未分類的資訊 (CUI) 遵守 Microsoft 雲端服務。
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
ms.openlocfilehash: a08932d4f16a17b35fef11cdcd8243c96060a4b5
ms.sourcegitcommit: 82e6b56d7265f8389b0af8baf51acb3013d88754
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/07/2020
ms.locfileid: "41851780"
---
# <a name="nist-sp-800171"></a><span data-ttu-id="a1022-104">NIST SP 800-171</span><span class="sxs-lookup"><span data-stu-id="a1022-104">NIST SP 800–171</span></span>

## <a name="about-nist-sp-800171"></a><span data-ttu-id="a1022-105">關於 NIST SP 800-171</span><span class="sxs-lookup"><span data-stu-id="a1022-105">About NIST SP 800–171</span></span>

<span data-ttu-id="a1022-106">美國國家標準與技術 (NIST) 會升階，並維持度量的標準和指導方針來協助保護的資訊和聯邦機構資訊系統。</span><span class="sxs-lookup"><span data-stu-id="a1022-106">The US National Institute of Standards and Technology (NIST) promotes and maintains measurement standards and guidelines to help protect the information and information systems of federal agencies.</span></span> <span data-ttu-id="a1022-107">管理受控制非機密的資訊 (CUI) Executive 順序 13556 回應，它會發佈[NIST SP 800-171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)，*保護控制非機密資訊在 Nonfederal 資訊系統與組織*。</span><span class="sxs-lookup"><span data-stu-id="a1022-107">In response to Executive Order 13556 on managing controlled unclassified information (CUI), it published [NIST SP 800–171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final), *Protecting Controlled Unclassified Information In Nonfederal Information Systems and Organizations*.</span></span> <span data-ttu-id="a1022-108">CUI 指資訊 — 數位與實體 — government （或其代表為 entity） 所建立的而不會歸類，仍敏感，且需要保護。</span><span class="sxs-lookup"><span data-stu-id="a1022-108">CUI is defined as information — both digital and physical — created by a government (or an entity on its behalf) that, while not classified, is still sensitive and requires protection.</span></span>

<span data-ttu-id="a1022-109">NIST SP 800-171 原本在 2015 年 6 月發佈和已更新好幾次後再回應不斷 cyberthreats。</span><span class="sxs-lookup"><span data-stu-id="a1022-109">NIST SP 800–171 was originally published in June 2015 and has been updated several times since then in response to evolving cyberthreats.</span></span> <span data-ttu-id="a1022-110">它如何 CUI 應該是安全地存取、 傳輸和儲存在出版資訊系統與組織; 提供指導方針其需求分成四個主要類別：</span><span class="sxs-lookup"><span data-stu-id="a1022-110">It provides guidelines on how CUI should be securely accessed, transmitted, and stored in nonfederal information systems and organizations; its requirements fall into four main categories:</span></span>

- <span data-ttu-id="a1022-111">控制項和處理程序管理與保護</span><span class="sxs-lookup"><span data-stu-id="a1022-111">Controls and processes for managing and protecting</span></span>
- <span data-ttu-id="a1022-112">監控及管理 IT 系統</span><span class="sxs-lookup"><span data-stu-id="a1022-112">Monitoring and management of IT systems</span></span>
- <span data-ttu-id="a1022-113">清除作法和程序的使用者</span><span class="sxs-lookup"><span data-stu-id="a1022-113">Clear practices and procedures for end users</span></span>
- <span data-ttu-id="a1022-114">實作的技術及實體安全性措施</span><span class="sxs-lookup"><span data-stu-id="a1022-114">Implementation of technological and physical security measures</span></span>

## <a name="microsoft-and-nist-sp-800171"></a><span data-ttu-id="a1022-115">Microsoft 和 NIST SP 800-171</span><span class="sxs-lookup"><span data-stu-id="a1022-115">Microsoft and NIST SP 800–171</span></span>

<span data-ttu-id="a1022-116">此成員的協力廠商評估組織中，Kratos Secureinfo 和 Coalfire，建立與 Microsoft，以證明，其範圍內的雲端服務符合準則，NIST SP 800-171，*保護控制非機密資訊 (CUI) Nonfederal 資訊系統與組織中*，當他們處理 CUI 合作關係。</span><span class="sxs-lookup"><span data-stu-id="a1022-116">Accredited third-party assessment organizations, Kratos Secureinfo and Coalfire, partnered with Microsoft to attest that its in-scope cloud services meet the criteria in NIST SP 800–171, *Protecting Controlled Unclassified Information (CUI) in Nonfederal Information Systems and Organizations*, when they process CUI.</span></span> <span data-ttu-id="a1022-117">[Microsoft 實作 FedRAMP 的](offering-fedramp.md)需求可協助確保 Microsoft 範圍內雲端服務達到或超過 NIST SP 800-171 就地使用作法已經與系統的需求。</span><span class="sxs-lookup"><span data-stu-id="a1022-117">The [Microsoft implementation of FedRAMP](offering-fedramp.md) requirements help ensure Microsoft in-scope cloud services meet or exceed the requirements of NIST SP 800–171 using the systems and practices already in place.</span></span>

<span data-ttu-id="a1022-118">NIST SP 800-171 需求是 NIST SP 800-53、 FedRAMP 使用標準的子集。</span><span class="sxs-lookup"><span data-stu-id="a1022-118">NIST SP 800–171 requirements are a subset of NIST SP 800-53, the standard that FedRAMP uses.</span></span> <span data-ttu-id="a1022-119">附錄 D 的 NIST SP 800-171 提供相關的安全性中的控制項 NIST SP 800-53、 其範圍內雲端服務已經已評估並授權下 FedRAMP 程式其 CUI 安全性需求的直接對應。</span><span class="sxs-lookup"><span data-stu-id="a1022-119">Appendix D of NIST SP 800–171 provides a direct mapping of its CUI security requirements to the relevant security controls in NIST SP 800-53, for which the in-scope cloud services have already been assessed and authorized under the FedRAMP program.</span></span>

<span data-ttu-id="a1022-120">任何實體的程序或儲存 US government CUI — 研究機構，諮詢公司，製造承包商 — 必須遵守嚴格的 NIST SP 800-171 需求。</span><span class="sxs-lookup"><span data-stu-id="a1022-120">Any entity that processes or stores US government CUI — research institutions, consulting companies, manufacturing contractors — must comply with the stringent requirements of NIST SP 800–171.</span></span> <span data-ttu-id="a1022-121">此證明表示範圍內的雲端服務可以容納想知道如何部署與 Microsoft 處於完整規範保證 CUI 工作負載的客戶的 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="a1022-121">This attestation means Microsoft in-scope cloud services can accommodate customers looking to deploy CUI workloads with the assurance that Microsoft is in full compliance.</span></span> <span data-ttu-id="a1022-122">例如，所有 DoD 承包商處理、 儲存，或傳輸涵蓋的防禦資訊使用範圍內的 Microsoft 雲端服務在其資訊系統符合防禦 DFARS 美國部門的子句需要安全性與合規性NIST SP 800-171 的需求。</span><span class="sxs-lookup"><span data-stu-id="a1022-122">For example, all DoD contractors who process, store, or transmit 'covered defense information' using in-scope Microsoft cloud services in their information systems meet the US Department of Defense DFARS clauses that require compliance with the security requirements of NIST SP 800–171.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="a1022-123">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="a1022-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="a1022-124">Azure 政府版</span><span class="sxs-lookup"><span data-stu-id="a1022-124">Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="a1022-125">Dynamics 365 美國政府版</span><span class="sxs-lookup"><span data-stu-id="a1022-125">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="a1022-126">Intune</span><span class="sxs-lookup"><span data-stu-id="a1022-126">Intune</span></span>
- [<span data-ttu-id="a1022-127">Office 365 美國政府社群雲端 (GCC)、 Office 365 GCC 高和 DoD</span><span class="sxs-lookup"><span data-stu-id="a1022-127">Office 365 U.S. Government Community Cloud (GCC), Office 365 GCC High, and DoD</span></span>](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="a1022-128">稽核、報告和憑證</span><span class="sxs-lookup"><span data-stu-id="a1022-128">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="a1022-129">Azure 政府版 Attestation 的合規性 NIST SP 800-171</span><span class="sxs-lookup"><span data-stu-id="a1022-129">Azure Government Attestation of Compliance with NIST SP 800–171</span></span>](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a><span data-ttu-id="a1022-130">實作方式</span><span class="sxs-lookup"><span data-stu-id="a1022-130">How to implement</span></span>

- <span data-ttu-id="a1022-131">[NIST SP 800-171 藍圖](https://aka.ms/NIST-800-171-Blueprint)： 取得實作與 NIST SP 800-171 遵循 Azure 中的工作負載的支援。</span><span class="sxs-lookup"><span data-stu-id="a1022-131">[NIST SP 800–171 Blueprint](https://aka.ms/NIST-800-171-Blueprint): Get support for implementing workloads in Azure that comply with NIST SP 800–171.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a1022-132">常見問題集</span><span class="sxs-lookup"><span data-stu-id="a1022-132">Frequently asked questions</span></span>

<span data-ttu-id="a1022-133">**可以使用 Microsoft 合規性 NIST SP 800-171 我的組織？**</span><span class="sxs-lookup"><span data-stu-id="a1022-133">**Can I use Microsoft compliance with NIST SP 800–171 for my organization?**</span></span>

<span data-ttu-id="a1022-134">是。</span><span class="sxs-lookup"><span data-stu-id="a1022-134">Yes.</span></span> <span data-ttu-id="a1022-135">Microsoft 客戶可以使用從獨立第三方評估組織 (3PAO) 報告中所述的稽核的控制項根據 FedRAMP 標準自己 FedRAMP 和 NIST 風險分析和限定性條件努力的一部分。</span><span class="sxs-lookup"><span data-stu-id="a1022-135">Microsoft customers may use the audited controls described in the reports from independent third-party assessment organizations (3PAO) on FedRAMP standards as part of their own FedRAMP and NIST risk analysis and qualification efforts.</span></span> <span data-ttu-id="a1022-136">這些報告足以 Microsoft 已實作其範圍內的雲端服務中的控制項的有效性。</span><span class="sxs-lookup"><span data-stu-id="a1022-136">These reports attest to the effectiveness of the controls Microsoft has implemented in its in-scope cloud services.</span></span> <span data-ttu-id="a1022-137">客戶負責確保，其 CUI 工作負載遵守 NIST SP 800-171 指導方針。</span><span class="sxs-lookup"><span data-stu-id="a1022-137">Customers are responsible for ensuring that their CUI workloads comply with NIST SP 800–171 guidelines.</span></span>

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a><span data-ttu-id="a1022-138">使用 Microsoft 合規性分數 」 來評估您的風險</span><span class="sxs-lookup"><span data-stu-id="a1022-138">Use Microsoft Compliance Score to assess your risk</span></span>

<span data-ttu-id="a1022-139">[Microsoft 合規性分數](compliance-score.md)是在[Microsoft 365 合規性中心](microsoft-365-compliance-center.md)中以協助您了解貴組織的合規性狀態，並採取動作，以協助降低風險的預覽功能。</span><span class="sxs-lookup"><span data-stu-id="a1022-139">[Microsoft Compliance Score](compliance-score.md) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization’s compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="a1022-140">[設定合規性分數](compliance-score-setup.md)之後, 使用預先設定的[NIST 800-171 範本](https://go.microsoft.com/fwlink/?linkid=2117526)可協助組織符合此法規的需求。</span><span class="sxs-lookup"><span data-stu-id="a1022-140">After [setting up Compliance Score](compliance-score-setup.md), use the pre-configured [NIST 800-171 template](https://go.microsoft.com/fwlink/?linkid=2117526) to help your organization meet the requirements for this regulation.</span></span>

## <a name="resources"></a><span data-ttu-id="a1022-141">資源</span><span class="sxs-lookup"><span data-stu-id="a1022-141">Resources</span></span>

- [<span data-ttu-id="a1022-142">Microsoft DoD 憑證符合 NIST 800-171 需求</span><span class="sxs-lookup"><span data-stu-id="a1022-142">Microsoft DoD Certification Meets NIST 800–171 Requirements</span></span>](offering-DoD-DISA-L2-L4-L5.md)
- [<span data-ttu-id="a1022-143">NIST 800-171 規範的開頭 Cybersecurity 文件</span><span class="sxs-lookup"><span data-stu-id="a1022-143">NIST 800–171 Compliance Starts with Cybersecurity Documentation</span></span>](https://www.nist800171.com/)
- [<span data-ttu-id="a1022-144">Microsoft 雲端服務 FedRAMP 授權</span><span class="sxs-lookup"><span data-stu-id="a1022-144">Microsoft Cloud Services FedRAMP Authorizations</span></span>](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [<span data-ttu-id="a1022-145">NIST 800-171 3.3 稽核和責任與 Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="a1022-145">NIST 800-171 3.3 Audit and Accountability with Office 365 GCC High</span></span>](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [<span data-ttu-id="a1022-146">Microsoft 和 NIST Cybersecurity Framework</span><span class="sxs-lookup"><span data-stu-id="a1022-146">Microsoft and the NIST Cybersecurity Framework</span></span>](offering-nist-csf.md)
- [<span data-ttu-id="a1022-147">Microsoft 政府雲端</span><span class="sxs-lookup"><span data-stu-id="a1022-147">Microsoft Government Cloud</span></span>](https://www.microsoft.com/enterprise/government)
- [<span data-ttu-id="a1022-148">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="a1022-148">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="a1022-149">下載方案背景資料</span><span class="sxs-lookup"><span data-stu-id="a1022-149">Download the offering backgrounder</span></span>

<span data-ttu-id="a1022-150">是否需要此方案的背景資料文件？</span><span class="sxs-lookup"><span data-stu-id="a1022-150">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="a1022-151">下載 [PDF](https://download.microsoft.com/download/9/8/F/98F1D966-FB62-4B58-B6F0-8F3DCCAC484A/NIST_SP-800-171-Compliance.pdf )。</span><span class="sxs-lookup"><span data-stu-id="a1022-151">Download the [PDF](https://download.microsoft.com/download/9/8/F/98F1D966-FB62-4B58-B6F0-8F3DCCAC484A/NIST_SP-800-171-Compliance.pdf ).</span></span>
