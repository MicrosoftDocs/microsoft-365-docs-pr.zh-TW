---
title: NIST SP 800-171
description: Microsoft 雲端服務遵循 NIST SP 800-171 指導方針，以保護 nonfederal 資訊系統中受控制的未分類資訊 (CUI) 。
keywords: Microsoft 365, 合規性, 方案
localization_priority: None
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 9874a68978e5755e8e86ff476ec96170878a10da
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208085"
---
# <a name="nist-sp-800-171"></a><span data-ttu-id="c5232-104">NIST SP 800-171</span><span class="sxs-lookup"><span data-stu-id="c5232-104">NIST SP 800-171</span></span>

## <a name="about-nist-sp-800-171"></a><span data-ttu-id="c5232-105">關於 NIST SP 800-171</span><span class="sxs-lookup"><span data-stu-id="c5232-105">About NIST SP 800-171</span></span>

<span data-ttu-id="c5232-106">美國國家標準和技術協會 (NIST) 會促進及維護度量標準和準則，以協助保護聯邦機構的資訊和資訊系統。</span><span class="sxs-lookup"><span data-stu-id="c5232-106">The US National Institute of Standards and Technology (NIST) promotes and maintains measurement standards and guidelines to help protect the information and information systems of federal agencies.</span></span> <span data-ttu-id="c5232-107">如需管理受控未分類資訊的管理順序 13556 (CUI) ，它已發佈 [NIST SP 800-171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)， *保護 Nonfederal 資訊系統和組織中的受控未分類資訊*。</span><span class="sxs-lookup"><span data-stu-id="c5232-107">In response to Executive Order 13556 on managing controlled unclassified information (CUI), it published [NIST SP 800-171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final), *Protecting Controlled Unclassified Information In Nonfederal Information Systems and Organizations*.</span></span> <span data-ttu-id="c5232-108">CUI 會定義為由政府 (或其代表的實體所建立的資訊（包括數位和實體）) ，但不保密，仍然機密且需要保護。</span><span class="sxs-lookup"><span data-stu-id="c5232-108">CUI is defined as information — both digital and physical — created by a government (or an entity on its behalf) that, while not classified, is still sensitive and requires protection.</span></span>

<span data-ttu-id="c5232-109">NIST SP 800-171 最初發佈于6月2015，已于此後更新數次，以回應演變的 cyberthreats。</span><span class="sxs-lookup"><span data-stu-id="c5232-109">NIST SP 800-171 was originally published in June 2015 and has been updated several times since then in response to evolving cyberthreats.</span></span> <span data-ttu-id="c5232-110">它提供有關如何在 nonfederal 資訊系統和組織中安全地存取、傳送和儲存 CUI 的指導方針;其需求分為四個主要類別：</span><span class="sxs-lookup"><span data-stu-id="c5232-110">It provides guidelines on how CUI should be securely accessed, transmitted, and stored in nonfederal information systems and organizations; its requirements fall into four main categories:</span></span>

- <span data-ttu-id="c5232-111">管理及保護的控制項和程式</span><span class="sxs-lookup"><span data-stu-id="c5232-111">Controls and processes for managing and protecting</span></span>
- <span data-ttu-id="c5232-112">IT 系統的監控與管理</span><span class="sxs-lookup"><span data-stu-id="c5232-112">Monitoring and management of IT systems</span></span>
- <span data-ttu-id="c5232-113">適用于使用者的清晰做法和程式</span><span class="sxs-lookup"><span data-stu-id="c5232-113">Clear practices and procedures for end users</span></span>
- <span data-ttu-id="c5232-114">技術和實體安全性措施的實施</span><span class="sxs-lookup"><span data-stu-id="c5232-114">Implementation of technological and physical security measures</span></span>

## <a name="microsoft-and-nist-sp-800-171"></a><span data-ttu-id="c5232-115">Microsoft 和 NIST SP 800-171</span><span class="sxs-lookup"><span data-stu-id="c5232-115">Microsoft and NIST SP 800-171</span></span>

<span data-ttu-id="c5232-116">已取得協力廠商評估組織，Kratos Secureinfo 和 Coalfire，與 Microsoft 合作以證明其範圍內的雲端服務符合 NIST SP 800-171 中的準則， *保護受控未分類資訊 (CUI) 在 Nonfederal 資訊系統和組織中*處理 CUI。</span><span class="sxs-lookup"><span data-stu-id="c5232-116">Accredited third-party assessment organizations, Kratos Secureinfo and Coalfire, partnered with Microsoft to attest that its in-scope cloud services meet the criteria in NIST SP 800-171, *Protecting Controlled Unclassified Information (CUI) in Nonfederal Information Systems and Organizations*, when they process CUI.</span></span> <span data-ttu-id="c5232-117">[Microsoft 對 FedRAMP](offering-fedramp.md)需求的實施，可協助確保 Microsoft 內部的雲端服務使用已到位的系統和做法，符合或超過 NIST SP 800-171 的需求。</span><span class="sxs-lookup"><span data-stu-id="c5232-117">The [Microsoft implementation of FedRAMP](offering-fedramp.md) requirements help ensure Microsoft in-scope cloud services meet or exceed the requirements of NIST SP 800-171 using the systems and practices already in place.</span></span>

<span data-ttu-id="c5232-118">NIST SP 800-171 的需求是 NIST SP 800-53 （FedRAMP 使用的標準）的子集。</span><span class="sxs-lookup"><span data-stu-id="c5232-118">NIST SP 800-171 requirements are a subset of NIST SP 800-53, the standard that FedRAMP uses.</span></span> <span data-ttu-id="c5232-119">NIST SP 800-171 的附錄 D 可將其 CUI 安全性需求直接對應至 NIST SP 800-53 中的相關安全性控制，其範圍內的雲端服務已在 FedRAMP 程式下評估並授權。</span><span class="sxs-lookup"><span data-stu-id="c5232-119">Appendix D of NIST SP 800-171 provides a direct mapping of its CUI security requirements to the relevant security controls in NIST SP 800-53, for which the in-scope cloud services have already been assessed and authorized under the FedRAMP program.</span></span>

<span data-ttu-id="c5232-120">任何處理或儲存我們政府 CUI 的實體（調研機構、諮詢公司、製造承包商）都必須遵守 NIST SP 800-171 的嚴格需求。</span><span class="sxs-lookup"><span data-stu-id="c5232-120">Any entity that processes or stores US government CUI — research institutions, consulting companies, manufacturing contractors — must comply with the stringent requirements of NIST SP 800-171.</span></span> <span data-ttu-id="c5232-121">這項證明意味著 Microsoft in 範圍的雲端服務可讓客戶在尋求部署 CUI 工作負載時，確保 Microsoft 符合完全規範。</span><span class="sxs-lookup"><span data-stu-id="c5232-121">This attestation means Microsoft in-scope cloud services can accommodate customers looking to deploy CUI workloads with the assurance that Microsoft is in full compliance.</span></span> <span data-ttu-id="c5232-122">例如，在其資訊系統中使用內部範圍的 Microsoft 雲端服務處理、儲存或傳輸「涵蓋的防禦資訊」的所有 DoD 承包商，都符合美國國防部 DFARS 子句，需要符合 NIST SP 800-171 的安全性需求。</span><span class="sxs-lookup"><span data-stu-id="c5232-122">For example, all DoD contractors who process, store, or transmit 'covered defense information' using in-scope Microsoft cloud services in their information systems meet the US Department of Defense DFARS clauses that require compliance with the security requirements of NIST SP 800-171.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="c5232-123">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="c5232-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="c5232-124">Azure 政府</span><span class="sxs-lookup"><span data-stu-id="c5232-124">Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="c5232-125">美國政府的 Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c5232-125">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="c5232-126">Intune</span><span class="sxs-lookup"><span data-stu-id="c5232-126">Intune</span></span>
- [<span data-ttu-id="c5232-127">Office 365 美國政府社區雲端 (GCC) 、Office 365 GCC High 及 DoD</span><span class="sxs-lookup"><span data-stu-id="c5232-127">Office 365 U.S. Government Community Cloud (GCC), Office 365 GCC High, and DoD</span></span>](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="c5232-128">稽核、報告和認證</span><span class="sxs-lookup"><span data-stu-id="c5232-128">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="c5232-129">與 NIST SP 800-171 相容性的 Azure 政府證明</span><span class="sxs-lookup"><span data-stu-id="c5232-129">Azure Government Attestation of Compliance with NIST SP 800-171</span></span>](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a><span data-ttu-id="c5232-130">實作方法</span><span class="sxs-lookup"><span data-stu-id="c5232-130">How to implement</span></span>

- <span data-ttu-id="c5232-131">[Azure 藍圖範例](https://docs.microsoft.com/azure/governance/blueprints/samples/)：取得支援以 NIST 為基礎的控制項的實施工作負載。</span><span class="sxs-lookup"><span data-stu-id="c5232-131">[Azure Blueprint samples](https://docs.microsoft.com/azure/governance/blueprints/samples/): Get support for implementing workloads that comply with NIST-based controls.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c5232-132">常見問題集</span><span class="sxs-lookup"><span data-stu-id="c5232-132">Frequently asked questions</span></span>

<span data-ttu-id="c5232-133">**我可以使用 Microsoft 對我的組織使用 NIST SP 800-171 的規範嗎？**</span><span class="sxs-lookup"><span data-stu-id="c5232-133">**Can I use Microsoft compliance with NIST SP 800-171 for my organization?**</span></span>

<span data-ttu-id="c5232-134">是。</span><span class="sxs-lookup"><span data-stu-id="c5232-134">Yes.</span></span> <span data-ttu-id="c5232-135">Microsoft 客戶可以使用來自獨立協力廠商評估組織的報告中所述的審核控制項， (3PAO) FedRAMP 標準的一部分 FedRAMP 及 NIST 風險分析和資格工作。</span><span class="sxs-lookup"><span data-stu-id="c5232-135">Microsoft customers may use the audited controls described in the reports from independent third-party assessment organizations (3PAO) on FedRAMP standards as part of their own FedRAMP and NIST risk analysis and qualification efforts.</span></span> <span data-ttu-id="c5232-136">這些報告證明 Microsoft 已在其範圍內雲端服務中實施之控制項的效能。</span><span class="sxs-lookup"><span data-stu-id="c5232-136">These reports attest to the effectiveness of the controls Microsoft has implemented in its in-scope cloud services.</span></span> <span data-ttu-id="c5232-137">客戶負責確保其 CUI 工作負載符合 NIST SP 800-171 指導方針。</span><span class="sxs-lookup"><span data-stu-id="c5232-137">Customers are responsible for ensuring that their CUI workloads comply with NIST SP 800-171 guidelines.</span></span>

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a><span data-ttu-id="c5232-138">使用 Microsoft 合規性管理員評估您的風險</span><span class="sxs-lookup"><span data-stu-id="c5232-138">Use Microsoft Compliance Manager to assess your risk</span></span>

<span data-ttu-id="c5232-139">[Microsoft 合規性管理員](compliance-manager.md) 是 [microsoft 365 規範中心](microsoft-365-compliance-center.md) 的一項功能，可協助您瞭解組織的合規性狀況，並採取行動以協助降低風險。</span><span class="sxs-lookup"><span data-stu-id="c5232-139">[Microsoft Compliance Manager](compliance-manager.md) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="c5232-140">合規性管理員提供為此法規建立評估的高級範本。</span><span class="sxs-lookup"><span data-stu-id="c5232-140">Compliance Manager offers a premium template for building an assessment for this regulation.</span></span> <span data-ttu-id="c5232-141">在 [合規性管理員] 的 [ **評估範本** ] 頁面中尋找範本。</span><span class="sxs-lookup"><span data-stu-id="c5232-141">Find the template in the **assessment templates** page in Compliance Manager.</span></span> <span data-ttu-id="c5232-142">瞭解如何 [在合規性管理員中建立評估](compliance-manager-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="c5232-142">Learn how to [build assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

## <a name="resources"></a><span data-ttu-id="c5232-143">資源</span><span class="sxs-lookup"><span data-stu-id="c5232-143">Resources</span></span>

- [<span data-ttu-id="c5232-144">Microsoft DoD 認證符合 NIST 800-171 的需求</span><span class="sxs-lookup"><span data-stu-id="c5232-144">Microsoft DoD Certification Meets NIST 800-171 Requirements</span></span>](offering-DoD-DISA-L2-L4-L5.md)
- [<span data-ttu-id="c5232-145">NIST 800-171 合規性始于 Cybersecurity 檔</span><span class="sxs-lookup"><span data-stu-id="c5232-145">NIST 800-171 Compliance Starts with Cybersecurity Documentation</span></span>](https://www.nist800171.com/)
- [<span data-ttu-id="c5232-146">Microsoft Cloud Services FedRAMP 授權</span><span class="sxs-lookup"><span data-stu-id="c5232-146">Microsoft Cloud Services FedRAMP Authorizations</span></span>](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [<span data-ttu-id="c5232-147">NIST 800-171 3.3 審計和責任與 Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="c5232-147">NIST 800-171 3.3 Audit and Accountability with Office 365 GCC High</span></span>](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [<span data-ttu-id="c5232-148">Microsoft 和 NIST Cybersecurity Framework</span><span class="sxs-lookup"><span data-stu-id="c5232-148">Microsoft and the NIST Cybersecurity Framework</span></span>](offering-nist-csf.md)
- [<span data-ttu-id="c5232-149">Microsoft 政府雲端</span><span class="sxs-lookup"><span data-stu-id="c5232-149">Microsoft Government Cloud</span></span>](https://www.microsoft.com/enterprise/government)
- [<span data-ttu-id="c5232-150">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="c5232-150">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
