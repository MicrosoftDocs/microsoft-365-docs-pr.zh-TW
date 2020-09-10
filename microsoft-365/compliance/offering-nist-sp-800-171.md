---
title: NIST SP 800 –171
description: Microsoft 雲端服務遵循 NIST SP 800 –171的指導方針，以保護 nonfederal 資訊系統中 (CUI) 控制的未分類資訊。
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
ms.openlocfilehash: 757541aa86049106ad06f02419fee02033c6a0e3
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417065"
---
# <a name="nist-sp-800171"></a><span data-ttu-id="f41d7-104">NIST SP 800 –171</span><span class="sxs-lookup"><span data-stu-id="f41d7-104">NIST SP 800–171</span></span>

## <a name="about-nist-sp-800171"></a><span data-ttu-id="f41d7-105">關於 NIST SP 800 –171</span><span class="sxs-lookup"><span data-stu-id="f41d7-105">About NIST SP 800–171</span></span>

<span data-ttu-id="f41d7-106">美國國家標準和技術協會 (NIST) 會促進及維護度量標準和準則，以協助保護聯邦機構的資訊和資訊系統。</span><span class="sxs-lookup"><span data-stu-id="f41d7-106">The US National Institute of Standards and Technology (NIST) promotes and maintains measurement standards and guidelines to help protect the information and information systems of federal agencies.</span></span> <span data-ttu-id="f41d7-107">若要回應管理層級13556管理受控未分類資訊 (CUI) ，已發佈 [NIST SP 800 – 171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)， *以保護 Nonfederal 資訊系統和組織中的受控未分類資訊*。</span><span class="sxs-lookup"><span data-stu-id="f41d7-107">In response to Executive Order 13556 on managing controlled unclassified information (CUI), it published [NIST SP 800–171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final), *Protecting Controlled Unclassified Information In Nonfederal Information Systems and Organizations*.</span></span> <span data-ttu-id="f41d7-108">CUI 會定義為由政府 (或其代表的實體所建立的資訊（包括數位和實體）) ，但不保密，仍然機密且需要保護。</span><span class="sxs-lookup"><span data-stu-id="f41d7-108">CUI is defined as information — both digital and physical — created by a government (or an entity on its behalf) that, while not classified, is still sensitive and requires protection.</span></span>

<span data-ttu-id="f41d7-109">NIST SP 800 –171最初是在2015年6月發佈，並已經過多次更新，以回應演變 cyberthreats。</span><span class="sxs-lookup"><span data-stu-id="f41d7-109">NIST SP 800–171 was originally published in June 2015 and has been updated several times since then in response to evolving cyberthreats.</span></span> <span data-ttu-id="f41d7-110">它提供有關如何在 nonfederal 資訊系統和組織中安全地存取、傳送和儲存 CUI 的指導方針;其需求分為四個主要類別：</span><span class="sxs-lookup"><span data-stu-id="f41d7-110">It provides guidelines on how CUI should be securely accessed, transmitted, and stored in nonfederal information systems and organizations; its requirements fall into four main categories:</span></span>

- <span data-ttu-id="f41d7-111">管理及保護的控制項和程式</span><span class="sxs-lookup"><span data-stu-id="f41d7-111">Controls and processes for managing and protecting</span></span>
- <span data-ttu-id="f41d7-112">IT 系統的監控與管理</span><span class="sxs-lookup"><span data-stu-id="f41d7-112">Monitoring and management of IT systems</span></span>
- <span data-ttu-id="f41d7-113">適用于使用者的清晰做法和程式</span><span class="sxs-lookup"><span data-stu-id="f41d7-113">Clear practices and procedures for end users</span></span>
- <span data-ttu-id="f41d7-114">技術和實體安全性措施的實施</span><span class="sxs-lookup"><span data-stu-id="f41d7-114">Implementation of technological and physical security measures</span></span>

## <a name="microsoft-and-nist-sp-800171"></a><span data-ttu-id="f41d7-115">Microsoft 和 NIST SP 800 –171</span><span class="sxs-lookup"><span data-stu-id="f41d7-115">Microsoft and NIST SP 800–171</span></span>

<span data-ttu-id="f41d7-116">已取得協力廠商評估組織，Kratos Secureinfo 和 Coalfire，與 Microsoft 合作以證明其內部範圍的雲端服務符合 NIST SP 800 –171中的準則，在 \*Nonfederal 資訊系統和組織中 (CUI) \*，在處理 CUI 時，保護受管理的未分類資訊。</span><span class="sxs-lookup"><span data-stu-id="f41d7-116">Accredited third-party assessment organizations, Kratos Secureinfo and Coalfire, partnered with Microsoft to attest that its in-scope cloud services meet the criteria in NIST SP 800–171, *Protecting Controlled Unclassified Information (CUI) in Nonfederal Information Systems and Organizations*, when they process CUI.</span></span> <span data-ttu-id="f41d7-117">[Microsoft 對 FedRAMP](offering-fedramp.md)需求的實施可協助確保 Microsoft 內建的雲端服務使用已到位的系統和做法，符合或超過 NIST SP 800 –171的需求。</span><span class="sxs-lookup"><span data-stu-id="f41d7-117">The [Microsoft implementation of FedRAMP](offering-fedramp.md) requirements help ensure Microsoft in-scope cloud services meet or exceed the requirements of NIST SP 800–171 using the systems and practices already in place.</span></span>

<span data-ttu-id="f41d7-118">NIST SP 800 –171的需求是 NIST SP 800-53 的子集（FedRAMP 使用的標準）。</span><span class="sxs-lookup"><span data-stu-id="f41d7-118">NIST SP 800–171 requirements are a subset of NIST SP 800-53, the standard that FedRAMP uses.</span></span> <span data-ttu-id="f41d7-119">在 NIST SP 800 –171中的附錄 D，可將其 CUI 安全性需求的直接對應至 NIST SP 800-53 中的相關安全性控制，但範圍內的雲端服務已在 FedRAMP 程式下評估並授權。</span><span class="sxs-lookup"><span data-stu-id="f41d7-119">Appendix D of NIST SP 800–171 provides a direct mapping of its CUI security requirements to the relevant security controls in NIST SP 800-53, for which the in-scope cloud services have already been assessed and authorized under the FedRAMP program.</span></span>

<span data-ttu-id="f41d7-120">任何處理或儲存 US 政府 CUI 的實體（調研機構、諮詢公司、製造承包商）都必須遵守 NIST SP 800 –171的嚴格需求。</span><span class="sxs-lookup"><span data-stu-id="f41d7-120">Any entity that processes or stores US government CUI — research institutions, consulting companies, manufacturing contractors — must comply with the stringent requirements of NIST SP 800–171.</span></span> <span data-ttu-id="f41d7-121">這項證明意味著 Microsoft in 範圍的雲端服務可讓客戶在尋求部署 CUI 工作負載時，確保 Microsoft 符合完全規範。</span><span class="sxs-lookup"><span data-stu-id="f41d7-121">This attestation means Microsoft in-scope cloud services can accommodate customers looking to deploy CUI workloads with the assurance that Microsoft is in full compliance.</span></span> <span data-ttu-id="f41d7-122">例如，在其資訊系統中，使用範圍內的 Microsoft 雲端服務處理、儲存或傳輸「涵蓋的防禦資訊」的所有 DoD 承包商，都符合美國國防 DFARS 子句，需要符合 NIST SP 800 –171的安全性需求。</span><span class="sxs-lookup"><span data-stu-id="f41d7-122">For example, all DoD contractors who process, store, or transmit 'covered defense information' using in-scope Microsoft cloud services in their information systems meet the US Department of Defense DFARS clauses that require compliance with the security requirements of NIST SP 800–171.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="f41d7-123">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="f41d7-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="f41d7-124">Azure 政府</span><span class="sxs-lookup"><span data-stu-id="f41d7-124">Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="f41d7-125">美國政府的 Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f41d7-125">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="f41d7-126">Intune</span><span class="sxs-lookup"><span data-stu-id="f41d7-126">Intune</span></span>
- [<span data-ttu-id="f41d7-127">Office 365 美國政府社區雲端 (GCC) 、Office 365 GCC High 及 DoD</span><span class="sxs-lookup"><span data-stu-id="f41d7-127">Office 365 U.S. Government Community Cloud (GCC), Office 365 GCC High, and DoD</span></span>](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="f41d7-128">稽核、報告和憑證</span><span class="sxs-lookup"><span data-stu-id="f41d7-128">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="f41d7-129">具有 NIST SP 800 –171的 Azure 政府規範證明</span><span class="sxs-lookup"><span data-stu-id="f41d7-129">Azure Government Attestation of Compliance with NIST SP 800–171</span></span>](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a><span data-ttu-id="f41d7-130">實作方法</span><span class="sxs-lookup"><span data-stu-id="f41d7-130">How to implement</span></span>

- <span data-ttu-id="f41d7-131">[Azure 藍圖範例](https://docs.microsoft.com/azure/governance/blueprints/samples/)：取得支援以 NIST 為基礎的控制項的實施工作負載。</span><span class="sxs-lookup"><span data-stu-id="f41d7-131">[Azure Blueprint samples](https://docs.microsoft.com/azure/governance/blueprints/samples/): Get support for implementing workloads that comply with NIST-based controls.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f41d7-132">常見問題集</span><span class="sxs-lookup"><span data-stu-id="f41d7-132">Frequently asked questions</span></span>

<span data-ttu-id="f41d7-133">**我可以使用 Microsoft 法規遵從性，針對我的組織使用 NIST SP 800 –171？**</span><span class="sxs-lookup"><span data-stu-id="f41d7-133">**Can I use Microsoft compliance with NIST SP 800–171 for my organization?**</span></span>

<span data-ttu-id="f41d7-134">是。</span><span class="sxs-lookup"><span data-stu-id="f41d7-134">Yes.</span></span> <span data-ttu-id="f41d7-135">Microsoft 客戶可以使用來自獨立協力廠商評估組織的報告中所述的審核控制項， (3PAO) FedRAMP 標準的一部分 FedRAMP 及 NIST 風險分析和資格工作。</span><span class="sxs-lookup"><span data-stu-id="f41d7-135">Microsoft customers may use the audited controls described in the reports from independent third-party assessment organizations (3PAO) on FedRAMP standards as part of their own FedRAMP and NIST risk analysis and qualification efforts.</span></span> <span data-ttu-id="f41d7-136">這些報告證明 Microsoft 已在其範圍內雲端服務中實施之控制項的效能。</span><span class="sxs-lookup"><span data-stu-id="f41d7-136">These reports attest to the effectiveness of the controls Microsoft has implemented in its in-scope cloud services.</span></span> <span data-ttu-id="f41d7-137">客戶負責確保其 CUI 工作負載符合 NIST SP 800 –171的指導方針。</span><span class="sxs-lookup"><span data-stu-id="f41d7-137">Customers are responsible for ensuring that their CUI workloads comply with NIST SP 800–171 guidelines.</span></span>

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a><span data-ttu-id="f41d7-138">使用 Microsoft 合規性分數來評估風險</span><span class="sxs-lookup"><span data-stu-id="f41d7-138">Use Microsoft Compliance Score to assess your risk</span></span>

<span data-ttu-id="f41d7-139">[Microsoft 合規性分數](compliance-score.md)是 [Microsoft 365 合規性中心](microsoft-365-compliance-center.md)的預覽功能，可協助您了解組織的合規性狀況，並採取行動以協助降低風險。</span><span class="sxs-lookup"><span data-stu-id="f41d7-139">[Microsoft Compliance Score](compliance-score.md) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization’s compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="f41d7-140">[設定合規性分數](compliance-score-setup.md)後，請從**範本**下拉式功能表中選取預先設定的[NIST 800-171 範本](https://go.microsoft.com/fwlink/?linkid=2117526)，以協助您的組織符合此法規的需求。</span><span class="sxs-lookup"><span data-stu-id="f41d7-140">After [setting up Compliance Score](compliance-score-setup.md), select the pre-configured [NIST 800-171 template](https://go.microsoft.com/fwlink/?linkid=2117526) from the **Template** drop-down menu to help your organization meet the requirements for this regulation.</span></span>

## <a name="resources"></a><span data-ttu-id="f41d7-141">資源</span><span class="sxs-lookup"><span data-stu-id="f41d7-141">Resources</span></span>

- [<span data-ttu-id="f41d7-142">Microsoft DoD 認證符合 NIST 800 –171的需求</span><span class="sxs-lookup"><span data-stu-id="f41d7-142">Microsoft DoD Certification Meets NIST 800–171 Requirements</span></span>](offering-DoD-DISA-L2-L4-L5.md)
- [<span data-ttu-id="f41d7-143">NIST 800 –171相容性始于 Cybersecurity 檔</span><span class="sxs-lookup"><span data-stu-id="f41d7-143">NIST 800–171 Compliance Starts with Cybersecurity Documentation</span></span>](https://www.nist800171.com/)
- [<span data-ttu-id="f41d7-144">Microsoft Cloud Services FedRAMP 授權</span><span class="sxs-lookup"><span data-stu-id="f41d7-144">Microsoft Cloud Services FedRAMP Authorizations</span></span>](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [<span data-ttu-id="f41d7-145">NIST 800-171 3.3 審計和責任與 Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="f41d7-145">NIST 800-171 3.3 Audit and Accountability with Office 365 GCC High</span></span>](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [<span data-ttu-id="f41d7-146">Microsoft 和 NIST Cybersecurity Framework</span><span class="sxs-lookup"><span data-stu-id="f41d7-146">Microsoft and the NIST Cybersecurity Framework</span></span>](offering-nist-csf.md)
- [<span data-ttu-id="f41d7-147">Microsoft 政府雲端</span><span class="sxs-lookup"><span data-stu-id="f41d7-147">Microsoft Government Cloud</span></span>](https://www.microsoft.com/enterprise/government)
- [<span data-ttu-id="f41d7-148">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="f41d7-148">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
