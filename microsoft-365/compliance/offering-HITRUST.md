---
title: 健康情況資訊信任聯盟 (HITRUST) 常見安全性架構 （csf） （機器翻譯）
description: Azure 與 Office 365 被認證以健康資訊信賴聯盟 (HITRUST) 常見安全性架構 （csf） （機器翻譯）。
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
ms.openlocfilehash: aa93ea90748f4beeb7a6d2ad6f537b098f19376c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602300"
---
# <a name="health-information-trust-alliance-hitrust-common-security-framework-csf"></a><span data-ttu-id="fcc75-104">健康情況資訊信任聯盟 (HITRUST) 常見安全性架構 （csf） （機器翻譯）</span><span class="sxs-lookup"><span data-stu-id="fcc75-104">Health Information Trust Alliance (HITRUST) Common Security Framework (CSF)</span></span>

## <a name="hitrust--csf-overview"></a><span data-ttu-id="fcc75-105">HITRUST — CSF 概觀</span><span class="sxs-lookup"><span data-stu-id="fcc75-105">HITRUST — CSF overview</span></span>

<span data-ttu-id="fcc75-106">健康資訊信賴聯盟 (HITRUST) 是由醫療保健產業的代表控管組織。</span><span class="sxs-lookup"><span data-stu-id="fcc75-106">The Health Information Trust Alliance (HITRUST) is an organization governed by representatives from the healthcare industry.</span></span> <span data-ttu-id="fcc75-107">HITRUST 建立並維護常見安全性架構 （csf） （機器翻譯），certifiable 的架構，以協助醫療保健組織和其提供者示範其安全性與合規性一致且操作簡便的方式。</span><span class="sxs-lookup"><span data-stu-id="fcc75-107">HITRUST created and maintains the Common Security Framework (CSF), a certifiable framework to help healthcare organizations and their providers demonstrate their security and compliance in a consistent and streamlined manner.</span></span>

<span data-ttu-id="fcc75-108">CSF 基礎 HIPAA 和 HITECH 動作，也就是美國醫療法律已建立的使用中，洩漏、 需求和保護的個別識別健康情況資訊，以及強制執行不符合規範。</span><span class="sxs-lookup"><span data-stu-id="fcc75-108">The CSF builds on HIPAA and the HITECH Act, which are US healthcare laws that have established requirements for the use, disclosure, and safeguarding of individually identifiable health information, and that enforce noncompliance.</span></span> <span data-ttu-id="fcc75-109">HITRUST 提供基準 — 標準化的合規性架構、 評估以及憑證程序-針對哪些雲端服務提供者和涵蓋的狀況實體可測量合規性。</span><span class="sxs-lookup"><span data-stu-id="fcc75-109">HITRUST provides a benchmark — a standardized compliance framework, assessment, and certification process — against which cloud service providers and covered health entities can measure compliance.</span></span> <span data-ttu-id="fcc75-110">CSF 也會併入醫療保健特定安全性、 隱私權和其他法規要求從這類現有的架構，以支付卡產業資料安全標準 ([PCI DSS](https://www.microsoft.com/trustcenter/compliance/pci))， [ISO/IEC 27001](https://www.microsoft.com/trustcenter/compliance/iso-iec-27001)資訊安全性管理標準，最少可接受的風險標準的交換 ([MARS-E](https://www.microsoft.com/trustcenter/compliance/mars-e))。</span><span class="sxs-lookup"><span data-stu-id="fcc75-110">The CSF also incorporates healthcare-specific security, privacy, and other regulatory requirements from such existing frameworks as the Payment Card Industry Data Security Standard ([PCI-DSS](https://www.microsoft.com/trustcenter/compliance/pci)), [ISO/IEC 27001](https://www.microsoft.com/trustcenter/compliance/iso-iec-27001) information security management standards, and Minimum Acceptable Risk Standards for Exchanges ([MARS-E](https://www.microsoft.com/trustcenter/compliance/mars-e)).</span></span>

<span data-ttu-id="fcc75-111">CSF 分為 19 不同的網域，包括端點保護、 行動裝置安全性和存取控制。</span><span class="sxs-lookup"><span data-stu-id="fcc75-111">The CSF is divided into 19 different domains, including endpoint protection, mobile device security, and access control.</span></span> <span data-ttu-id="fcc75-112">HITRUST 需要認證不受這些控制項的 IT 供應項目。</span><span class="sxs-lookup"><span data-stu-id="fcc75-112">HITRUST certifies IT offerings against these controls.</span></span> <span data-ttu-id="fcc75-113">HITRUST 也適應組織根據組織、 系統或法規的風險的憑證需求的因素。</span><span class="sxs-lookup"><span data-stu-id="fcc75-113">HITRUST also adapts requirements for certification to the risks of an organization based on organizational, system, and regulatory factors.</span></span>

<span data-ttu-id="fcc75-114">健康情況資訊信任聯盟 (HITRUST) 常見安全性架構 （csf） （機器翻譯）</span><span class="sxs-lookup"><span data-stu-id="fcc75-114">Health Information Trust Alliance (HITRUST) Common Security Framework (CSF)</span></span>

<span data-ttu-id="fcc75-115">HITRUST 提供三種程度的保證或評量層級： 自我評估、 CSF 驗證，且 CSF 認證。</span><span class="sxs-lookup"><span data-stu-id="fcc75-115">HITRUST offers three degrees of assurance, or levels of assessment: self-assessment, CSF validated, and CSF-certified.</span></span> <span data-ttu-id="fcc75-116">每個層級會建置，利用提高其下方的一個嚴謹。</span><span class="sxs-lookup"><span data-stu-id="fcc75-116">Each level builds with increasing rigor on the one below it.</span></span> <span data-ttu-id="fcc75-117">具有最高的層級，CSF 認證符合組織的 CSF 的憑證需求。</span><span class="sxs-lookup"><span data-stu-id="fcc75-117">An organization with the highest level, CSF-certified, meets all the certification requirements of the CSF.</span></span> <span data-ttu-id="fcc75-118">Microsoft Azure 和 Office 365 的第一個獲得認證的超大型雲端服務，以接收 HITRUST CSF 的憑證。</span><span class="sxs-lookup"><span data-stu-id="fcc75-118">Microsoft Azure and Office 365 are the first hyperscale cloud services to receive certification for the HITRUST CSF.</span></span> <span data-ttu-id="fcc75-119">Coalfire，HITRUST 評估者公司中，執行如何 Azure 與 Office 365 實作的安全性、 隱私權和法規需求，以保護敏感資訊為基礎的評估。</span><span class="sxs-lookup"><span data-stu-id="fcc75-119">Coalfire, a HITRUST assessor firm, performed the assessments based on how Azure and Office 365 implement security, privacy, and regulatory requirements to protect sensitive information.</span></span> <span data-ttu-id="fcc75-120">Microsoft 支援 HITRUST 共用責任程式。</span><span class="sxs-lookup"><span data-stu-id="fcc75-120">Microsoft supports the HITRUST Shared Responsibility Program.</span></span>

<span data-ttu-id="fcc75-121">了解如何開始加速 HITRUST 部署與我們的 Azure 安全性與合規性藍圖。</span><span class="sxs-lookup"><span data-stu-id="fcc75-121">Learn how to accelerate your HITRUST deployment with our Azure Security and Compliance Blueprint.</span></span>

[<span data-ttu-id="fcc75-122">下載 Microsoft Azure HITRUST 客戶責任矩陣 (CRM) 藍圖 v9.0d</span><span class="sxs-lookup"><span data-stu-id="fcc75-122">Download the Microsoft Azure HITRUST Customer Responsibility Matrix (CRM) blueprint v9.0d</span></span>](https://servicetrust.microsoft.com/ViewPage/Blueprint?command=Download&downloadType=Document&downloadId=3ccde498-4761-4be0-be8b-cd8d379a3a4f&docTab=fc060920-cdb8-11e7-bacf-0bf52b09d912_Healthcare_Blueprint)

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="fcc75-123">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="fcc75-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="fcc75-124">Azure 和 Azure Government</span><span class="sxs-lookup"><span data-stu-id="fcc75-124">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="fcc75-125">Intune</span><span class="sxs-lookup"><span data-stu-id="fcc75-125">Intune</span></span>
- [<span data-ttu-id="fcc75-126">Office 365 和 Office 365 美國政府</span><span class="sxs-lookup"><span data-stu-id="fcc75-126">Office 365 and Office 365 U.S. Government</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="fcc75-127">稽核、報告和認證</span><span class="sxs-lookup"><span data-stu-id="fcc75-127">Audits, reports, and certificates</span></span>

<span data-ttu-id="fcc75-128">Azure 與 Office 365 HITRUST CSF 憑證時才有效兩年。</span><span class="sxs-lookup"><span data-stu-id="fcc75-128">The HITRUST CSF certification of Azure and Office 365 is valid for two years.</span></span>

- [<span data-ttu-id="fcc75-129">Azure HITRUST 字母的憑證</span><span class="sxs-lookup"><span data-stu-id="fcc75-129">Azure HITRUST Letter of Certification</span></span>](https://aka.ms/AzureHiTrustLetterofCertification)
- [<span data-ttu-id="fcc75-130">Office 365 HITRUST 字母的憑證</span><span class="sxs-lookup"><span data-stu-id="fcc75-130">Office 365 HITRUST Letter of Certification</span></span>](https://aka.ms/O365HITRUSTcertification)

## <a name="accelerate-your-deployment-of-hipaahitrust-solutions-on-azure"></a><span data-ttu-id="fcc75-131">Azure 上加速 HIPAA/HITRUST 解決方案的部署</span><span class="sxs-lookup"><span data-stu-id="fcc75-131">Accelerate your deployment of HIPAA/HITRUST solutions on Azure</span></span>

<span data-ttu-id="fcc75-132">開始在善用的健康情況雲端的優勢 Azure 安全性與合規性藍圖資料解決方案 — HIPAA/HITRUST 健康狀況資料和 AI。</span><span class="sxs-lookup"><span data-stu-id="fcc75-132">Get a head start on taking advantage of the benefits of the cloud for health data solutions with the Azure Security and Compliance Blueprint — HIPAA/HITRUST Health Data and AI.</span></span> <span data-ttu-id="fcc75-133">這個藍圖提供工具和指引，協助您開始今天建置 HIPAA/HITRUST 解決方案。</span><span class="sxs-lookup"><span data-stu-id="fcc75-133">This blueprint provides tools and guidance to get you started building HIPAA/HITRUST solutions today.</span></span>

[<span data-ttu-id="fcc75-134">開始使用 Azure HIPAA/HITRUST 藍圖</span><span class="sxs-lookup"><span data-stu-id="fcc75-134">Start using the Azure HIPAA/HITRUST Blueprint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2100613)

## <a name="accelerate-your-hipaahitrust-compliance-when-using-office-365"></a><span data-ttu-id="fcc75-135">使用 Office 365 時，加速 HIPAA/HITRUST 合規性</span><span class="sxs-lookup"><span data-stu-id="fcc75-135">Accelerate your HIPAA/HITRUST compliance when using Office 365</span></span>

<span data-ttu-id="fcc75-136">使用 Office 365 安全與合規性方式與合規性分數，可讓您執行像是 NIST CSF 和 NIST 800-53 等的 HIPAA 和安全性控制架構的健康情況法規風險評估管理健全狀況資訊。</span><span class="sxs-lookup"><span data-stu-id="fcc75-136">Use Office 365 to manage health information in a secure and compliant way with Compliance Score, which enables you to perform risk assessments against health regulations like HIPAA and security control frameworks like NIST CSF and NIST 800-53.</span></span> <span data-ttu-id="fcc75-137">您可以依照逐步指引，了解如何實作及維護的資料保護控制項，可協助您符合醫療保健合規性責任。</span><span class="sxs-lookup"><span data-stu-id="fcc75-137">You can follow step-by-step guidance to know how to implement and maintain data protection controls that help you meet healthcare compliance obligations.</span></span>

[<span data-ttu-id="fcc75-138">開始使用合規性分數</span><span class="sxs-lookup"><span data-stu-id="fcc75-138">Start using Compliance Score</span></span>](compliance-score.md)

## <a name="collaborate-with-microsoft-in-the-hitrust-shared-responsibility-program"></a><span data-ttu-id="fcc75-139">Microsoft 在 HITRUST 共用的責任程式與共同作業</span><span class="sxs-lookup"><span data-stu-id="fcc75-139">Collaborate with Microsoft in the HITRUST Shared Responsibility Program</span></span>

<span data-ttu-id="fcc75-140">Accelerate 達成 HITRUST 合規性解決方案在 Microsoft Azure 上裝載的預先填入完全與您評估繼承而來，或 azure 共用責任措施，在 HITRUST MyCSF 工具中，並進行共同作業與 Microsoft 您評量。</span><span class="sxs-lookup"><span data-stu-id="fcc75-140">Accelerate achieving HITRUST compliance for your solution hosted on Microsoft Azure by pre-populating your assessment with fully inherited or shared responsibility controls for Azure in the HITRUST MyCSF tool, and collaborating with Microsoft on your assessment.</span></span>

[<span data-ttu-id="fcc75-141">深入了解</span><span class="sxs-lookup"><span data-stu-id="fcc75-141">Learn more</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2100268)

## <a name="frequently-asked-questions"></a><span data-ttu-id="fcc75-142">常見問題集</span><span class="sxs-lookup"><span data-stu-id="fcc75-142">Frequently asked questions</span></span>

<span data-ttu-id="fcc75-143">**可以使用 Azure HITRUST 合規性來建置在我的組織憑證處理程序嗎？**</span><span class="sxs-lookup"><span data-stu-id="fcc75-143">**Can I use the Azure HITRUST compliance to build on my organization's certification process?**</span></span>

<span data-ttu-id="fcc75-144">是。</span><span class="sxs-lookup"><span data-stu-id="fcc75-144">Yes.</span></span> <span data-ttu-id="fcc75-145">如果您的業務需要部署在 Microsoft 服務的實作 HITRUST 憑證，您可以建置 Azure HITRUST 符合性時進行您合規性的評估。</span><span class="sxs-lookup"><span data-stu-id="fcc75-145">If your business requires a HITRUST certification for implementations deployed on Microsoft services, you can build on Azure HITRUST compliance when you conduct your compliance assessment.</span></span> <span data-ttu-id="fcc75-146">不過，您必須負責評估 HITRUST 需求和您自己的組織內的控制項。</span><span class="sxs-lookup"><span data-stu-id="fcc75-146">However, you are responsible for evaluating the HITRUST requirements and controls within your own organization.</span></span>

<span data-ttu-id="fcc75-147">**如何取得一份 HITRUST 憑證？**</span><span class="sxs-lookup"><span data-stu-id="fcc75-147">**How can I get a copy of the HITRUST certification?**</span></span>

<span data-ttu-id="fcc75-148">您可以下載一份字母[Azure](https://aka.ms/AzureHiTrustLetterofCertification)與[Office 365](https://aka.ms/O365HITRUSTcertification)的憑證。</span><span class="sxs-lookup"><span data-stu-id="fcc75-148">You can download a copy of letter of certification for [Azure](https://aka.ms/AzureHiTrustLetterofCertification) and [Office 365](https://aka.ms/O365HITRUSTcertification).</span></span>

<span data-ttu-id="fcc75-149">**什麼是 Office 365 的範圍內服務？**</span><span class="sxs-lookup"><span data-stu-id="fcc75-149">**What are the in-scope services for Office 365?**</span></span>

<span data-ttu-id="fcc75-150">HITRUST CSF 憑證的範圍內的服務為 Exchange Online 封存、 Exchange Online Protection、 Exchange Online、 Skype for Business、 管理中心、 SharePoint Online、 Project Online、 OneDrive for Business、 Office Online、 MyAnalytics、 MicrosoftTeams，Office 專業增強版 Office 365 的多重租用戶定域機組中和 Office 365 GCC。</span><span class="sxs-lookup"><span data-stu-id="fcc75-150">The in-scope services of HITRUST CSF certification are Exchange Online Archiving, Exchange Online Protection, Exchange Online, Skype for Business, Admin Center, SharePoint Online, Project Online, OneDrive for Business, Office Online, MyAnalytics, Microsoft Teams, Office ProPlus in Office 365 Multi-tenant cloud and Office 365 GCC.</span></span>

> [!NOTE]
> <span data-ttu-id="fcc75-151">Office 365 專業增強版可讓您存取各種雲端服務，例如漫遊設定、 授權和 OneDrive 消費者雲端儲存空間，並可能在未來啟用其他雲端服務的存取。</span><span class="sxs-lookup"><span data-stu-id="fcc75-151">Office 365 ProPlus enables access to various cloud services, such as Roaming Settings, Licensing, and OneDrive consumer cloud storage, and may enable access to additional cloud services in the future.</span></span> <span data-ttu-id="fcc75-152">漫遊設定和授權支援 HITRUST 標準。</span><span class="sxs-lookup"><span data-stu-id="fcc75-152">Roaming Settings and Licensing support the standards for HITRUST.</span></span> <span data-ttu-id="fcc75-153">OneDrive 消費者雲端儲存空間不，和其他雲端服務，可透過 Office 365 專業增強版和 Microsoft 可能會提供在未來也可能不是，支援這些 standards.\*</span><span class="sxs-lookup"><span data-stu-id="fcc75-153">OneDrive consumer cloud storage does not, and other cloud services that are accessible through Office 365 ProPlus and that Microsoft may offer in the future also may not, support these standards.\*</span></span>

<span data-ttu-id="fcc75-154">**為何不在此憑證的範圍部分 Office 365 服務？**</span><span class="sxs-lookup"><span data-stu-id="fcc75-154">**Why are some Office 365 services not in the scope of this certification?**</span></span>

<span data-ttu-id="fcc75-155">Microsoft 提供相較於其他雲端服務提供者的最完整供應項目。</span><span class="sxs-lookup"><span data-stu-id="fcc75-155">Microsoft provides the most comprehensive offerings compared to other cloud service providers.</span></span> <span data-ttu-id="fcc75-156">若要可跟得我們廣泛的合規性供應項目的不同區域及產業，我們會根據市場需求、 客戶的意見反應，以及產品生命週期我們保證努力範圍中包含服務。</span><span class="sxs-lookup"><span data-stu-id="fcc75-156">To keep up with our broad compliance offerings across regions and industries, we include services in the scope of our assurance efforts based on the market demand, customer feedback, and product lifecycle.</span></span> <span data-ttu-id="fcc75-157">如果服務不包含目前範圍中的特定的法規提供，您的組織有責任評定根據您的合規性責任的風險，並判斷的方式會處理該服務中的資料。</span><span class="sxs-lookup"><span data-stu-id="fcc75-157">If a service is not included in the current scope of a specific compliance offering, your organization has the responsibility to assess the risks based on your compliance obligations and determine the way you process the data in that service.</span></span> <span data-ttu-id="fcc75-158">我們持續收集客戶的意見反應，並使用管理者和稽核員 」 以展開我們的合規性涵蓋範圍，以滿足您的安全性與合規性需求。</span><span class="sxs-lookup"><span data-stu-id="fcc75-158">We continuously collect feedback from customers and work with regulators and auditors to expand our compliance coverage to meet your security and compliance needs.</span></span>

<span data-ttu-id="fcc75-159">**Microsoft 憑證意思如果我的組織使用 Azure 或 Office 365，它是與 HITRUST CSF 相容？**</span><span class="sxs-lookup"><span data-stu-id="fcc75-159">**Does Microsoft certification mean that if my organization uses Azure or Office 365, it is compliant with HITRUST CSF?**</span></span>

<span data-ttu-id="fcc75-160">當您以 Office 365 像 SaaS 儲存您的資料時，是 Microsoft 與您的組織，以達到符合性之間的共用的責任。</span><span class="sxs-lookup"><span data-stu-id="fcc75-160">When you store your data in a SaaS like Office 365, it’s a shared responsibility between Microsoft and your organization to achieve compliance.</span></span> <span data-ttu-id="fcc75-161">Microsoft 管理大部分的基礎結構的控制項包括實體安全性、 網路控制項、 應用程式層級控制項等等，以及您的組織有管理存取控制及保護機密資料的責任。</span><span class="sxs-lookup"><span data-stu-id="fcc75-161">Microsoft manages majority of the infrastructure controls including physical security, network controls, application level controls, etc., and your organization has the responsibility to manage access controls and protect your sensitive data.</span></span> <span data-ttu-id="fcc75-162">Office 365 HITRUST 憑證示範合規性的 Microsoft 的控制項架構。</span><span class="sxs-lookup"><span data-stu-id="fcc75-162">The Office 365 HITRUST certification demonstrates the compliance of Microsoft’s control framework.</span></span> <span data-ttu-id="fcc75-163">建立的您的組織需要實作和維護您自己的資料保護控制項，以符合 HITRUST CSF 需求。</span><span class="sxs-lookup"><span data-stu-id="fcc75-163">Building on that, your organization needs to implement and maintain your own data protection controls to meet HITRUST CSF requirements.</span></span>

<span data-ttu-id="fcc75-164">**Microsoft 是否提供 「 我的組織，以實作適當的控制項，使用 Office 365 時的指引？**</span><span class="sxs-lookup"><span data-stu-id="fcc75-164">**Does Microsoft provide guidance for my organization to implement appropriate controls when using Office 365?**</span></span>

<span data-ttu-id="fcc75-165">是，您可以在合規性分數找到建議的客戶動作，使用雲端服務時，跨 Microsoft 雲端解決方案，可協助您的組織符合複雜的合規性責任。</span><span class="sxs-lookup"><span data-stu-id="fcc75-165">Yes, you can find recommended customer actions in Compliance Score, cross-Microsoft Cloud solutions that help your organization meet complex compliance obligations when using cloud services.</span></span> <span data-ttu-id="fcc75-166">具體而言，對於 HITRUST CSF，我們建議您執行使用 NIST CSF 評估與 NIST 800-53 合規性分數的風險評定。</span><span class="sxs-lookup"><span data-stu-id="fcc75-166">Specifically, for HITRUST CSF, we recommend that you perform risk assessments using the NIST 800-53 and NIST CSF assessments in Compliance Score.</span></span> <span data-ttu-id="fcc75-167">在評估，我們提供您的逐步指引和 Microsoft 解決方案可用來實作您的資料保護控制項。</span><span class="sxs-lookup"><span data-stu-id="fcc75-167">In the assessments, we provide you with step-by-step guidance and the Microsoft solutions you can use to implement your data protection controls.</span></span> <span data-ttu-id="fcc75-168">您可以深入了解[Microsoft 合規性](compliance-score.md)分數的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="fcc75-168">You can learn more about Compliance Score in [Microsoft Compliance Score](compliance-score.md).</span></span>

<span data-ttu-id="fcc75-169">**如何邀請與 Microsoft？**</span><span class="sxs-lookup"><span data-stu-id="fcc75-169">**How do I engage with Microsoft?**</span></span>

<span data-ttu-id="fcc75-170">登入 HITRUST MyCSF® 工具，並預先填入您在 Microsoft Azure 上任一完全繼承或共用責任措施以裝載 azure 解決方案的評估。</span><span class="sxs-lookup"><span data-stu-id="fcc75-170">Log in to the HITRUST MyCSF® tool and pre-populate your assessment for your solution hosted on Microsoft Azure with either fully inherited or shared responsibility controls for Azure.</span></span> <span data-ttu-id="fcc75-171">Microsoft HITRUST 系統管理員接著會完成上 MyCSF® 工具使用其帳戶的評估其組件。</span><span class="sxs-lookup"><span data-stu-id="fcc75-171">A Microsoft HITRUST Administrator will then complete their part of the assessment using their account on the MyCSF® tool.</span></span>

## <a name="resources"></a><span data-ttu-id="fcc75-172">資源</span><span class="sxs-lookup"><span data-stu-id="fcc75-172">Resources</span></span>

- [<span data-ttu-id="fcc75-173">HITRUST 結盟</span><span class="sxs-lookup"><span data-stu-id="fcc75-173">HITRUST Alliance</span></span>](https://hitrustalliance.net/)
- [<span data-ttu-id="fcc75-174">HITRUST CSF 8.1</span><span class="sxs-lookup"><span data-stu-id="fcc75-174">HITRUST CSF 8.1</span></span>](https://hitrustalliance.net/csf-license-agreement/)
- [<span data-ttu-id="fcc75-175">了解及使用 CSF</span><span class="sxs-lookup"><span data-stu-id="fcc75-175">Understanding and Leveraging the CSF</span></span>](https://hitrustalliance.net/understanding-leveraging-csf/)
- [<span data-ttu-id="fcc75-176">進一步了解如何在 HITRUST 共用責任程式</span><span class="sxs-lookup"><span data-stu-id="fcc75-176">Find out more about the HITRUST Shared Responsibility Program</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2100268)
- [<span data-ttu-id="fcc75-177">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="fcc75-177">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="fcc75-178">下載方案背景資料</span><span class="sxs-lookup"><span data-stu-id="fcc75-178">Download the offering backgrounder</span></span>

<span data-ttu-id="fcc75-179">是否需要此方案的背景資料文件？</span><span class="sxs-lookup"><span data-stu-id="fcc75-179">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="fcc75-180">下載 [PDF](https://download.microsoft.com/download/7/2/6/7265470A-862D-4665-91E8-E17BF0C8A1E2/HITRUST-Compliance.pdf)。</span><span class="sxs-lookup"><span data-stu-id="fcc75-180">Download the [PDF](https://download.microsoft.com/download/7/2/6/7265470A-862D-4665-91E8-E17BF0C8A1E2/HITRUST-Compliance.pdf).</span></span>
