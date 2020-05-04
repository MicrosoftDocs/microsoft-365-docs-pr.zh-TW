---
title: 健康資訊信任同盟（HITRUST）常見的安全性架構（CSF）
description: Azure 和 Office 365 的健康資訊信任同盟（HITRUST）通用安全性架構（CSF）認證。
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
ms.openlocfilehash: fa35e71d2748e02da12a239f67134c1b25b5a369
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011826"
---
# <a name="health-information-trust-alliance-hitrust-common-security-framework-csf"></a><span data-ttu-id="746d8-104">健康資訊信任同盟（HITRUST）常見的安全性架構（CSF）</span><span class="sxs-lookup"><span data-stu-id="746d8-104">Health Information Trust Alliance (HITRUST) Common Security Framework (CSF)</span></span>

## <a name="hitrust--csf-overview"></a><span data-ttu-id="746d8-105">HITRUST-CSF 一覽</span><span class="sxs-lookup"><span data-stu-id="746d8-105">HITRUST — CSF overview</span></span>

<span data-ttu-id="746d8-106">「健康情況資訊信任同盟」（HITRUST）是由醫療保健行業之代表所管理的組織。</span><span class="sxs-lookup"><span data-stu-id="746d8-106">The Health Information Trust Alliance (HITRUST) is an organization governed by representatives from the healthcare industry.</span></span> <span data-ttu-id="746d8-107">HITRUST 建立並維護常見的安全性架構（CSF），這是一種 certifiable 架構，可協助醫療保健組織及其提供者以一致且簡潔的方式示範其安全性與合規性。</span><span class="sxs-lookup"><span data-stu-id="746d8-107">HITRUST created and maintains the Common Security Framework (CSF), a certifiable framework to help healthcare organizations and their providers demonstrate their security and compliance in a consistent and streamlined manner.</span></span>

<span data-ttu-id="746d8-108">CSF 建立于 HIPAA 和高科技法案，這是美國醫療保健法，已針對個別身分識別健康資訊的使用、披露和保護，以及強制執行不相容的要求。</span><span class="sxs-lookup"><span data-stu-id="746d8-108">The CSF builds on HIPAA and the HITECH Act, which are US healthcare laws that have established requirements for the use, disclosure, and safeguarding of individually identifiable health information, and that enforce noncompliance.</span></span> <span data-ttu-id="746d8-109">HITRUST 提供一個基準-標準化的規範架構、評估和認證程式，讓雲端服務提供者和涵蓋的健康情況實體可以測量規范。</span><span class="sxs-lookup"><span data-stu-id="746d8-109">HITRUST provides a benchmark — a standardized compliance framework, assessment, and certification process — against which cloud service providers and covered health entities can measure compliance.</span></span> <span data-ttu-id="746d8-110">CSF 也會將這些現有框架的醫療保健特定安全性、隱私權及其他法規需求納入支付卡行業資料安全性標準（[PCI-DSS](https://www.microsoft.com/trustcenter/compliance/pci)）、 [ISO/IEC 27001](https://www.microsoft.com/trustcenter/compliance/iso-iec-27001)資訊安全性管理標準，以及交換（[火星-E](https://www.microsoft.com/trustcenter/compliance/mars-e)）的最低可接受風險標準。</span><span class="sxs-lookup"><span data-stu-id="746d8-110">The CSF also incorporates healthcare-specific security, privacy, and other regulatory requirements from such existing frameworks as the Payment Card Industry Data Security Standard ([PCI-DSS](https://www.microsoft.com/trustcenter/compliance/pci)), [ISO/IEC 27001](https://www.microsoft.com/trustcenter/compliance/iso-iec-27001) information security management standards, and Minimum Acceptable Risk Standards for Exchanges ([MARS-E](https://www.microsoft.com/trustcenter/compliance/mars-e)).</span></span>

<span data-ttu-id="746d8-111">CSF 分為19個不同的網域，包括 endpoint protection、行動裝置安全性和存取控制。</span><span class="sxs-lookup"><span data-stu-id="746d8-111">The CSF is divided into 19 different domains, including endpoint protection, mobile device security, and access control.</span></span> <span data-ttu-id="746d8-112">HITRUST 會針對這些控制項來驗證 IT 產品。</span><span class="sxs-lookup"><span data-stu-id="746d8-112">HITRUST certifies IT offerings against these controls.</span></span> <span data-ttu-id="746d8-113">HITRUST 也會根據組織、系統和法規因素，改編組織風險的認證需求。</span><span class="sxs-lookup"><span data-stu-id="746d8-113">HITRUST also adapts requirements for certification to the risks of an organization based on organizational, system, and regulatory factors.</span></span>

<span data-ttu-id="746d8-114">健康資訊信任同盟（HITRUST）常見的安全性架構（CSF）</span><span class="sxs-lookup"><span data-stu-id="746d8-114">Health Information Trust Alliance (HITRUST) Common Security Framework (CSF)</span></span>

<span data-ttu-id="746d8-115">HITRUST 提供三種確定性或評估等級：自我評估、CSF 驗證及 CSF 認證。</span><span class="sxs-lookup"><span data-stu-id="746d8-115">HITRUST offers three degrees of assurance, or levels of assessment: self-assessment, CSF validated, and CSF-certified.</span></span> <span data-ttu-id="746d8-116">每個層級組建都會在其下一個層級上增加嚴謹。</span><span class="sxs-lookup"><span data-stu-id="746d8-116">Each level builds with increasing rigor on the one below it.</span></span> <span data-ttu-id="746d8-117">最高層次的組織，CSF 認證，符合 CSF 的所有認證需求。</span><span class="sxs-lookup"><span data-stu-id="746d8-117">An organization with the highest level, CSF-certified, meets all the certification requirements of the CSF.</span></span> <span data-ttu-id="746d8-118">Microsoft Azure 和 Office 365 是第一個超大型雲端服務，可接收 HITRUST CSF 的認證。</span><span class="sxs-lookup"><span data-stu-id="746d8-118">Microsoft Azure and Office 365 are the first hyperscale cloud services to receive certification for the HITRUST CSF.</span></span> <span data-ttu-id="746d8-119">Coalfire，HITRUST assessor 事務所，會根據 Azure 和 Office 365 如何執行安全性、隱私權和法規需求，來執行評估，以保護機密資訊。</span><span class="sxs-lookup"><span data-stu-id="746d8-119">Coalfire, a HITRUST assessor firm, performed the assessments based on how Azure and Office 365 implement security, privacy, and regulatory requirements to protect sensitive information.</span></span> <span data-ttu-id="746d8-120">Microsoft 支援 HITRUST 共用責任計畫。</span><span class="sxs-lookup"><span data-stu-id="746d8-120">Microsoft supports the HITRUST Shared Responsibility Program.</span></span>

<span data-ttu-id="746d8-121">瞭解如何使用 Azure 安全性和合規性藍圖加速您的 HITRUST 部署。</span><span class="sxs-lookup"><span data-stu-id="746d8-121">Learn how to accelerate your HITRUST deployment with our Azure Security and Compliance Blueprint.</span></span>

[<span data-ttu-id="746d8-122">下載 Microsoft Azure HITRUST 客戶責任矩陣（CRM）藍圖，9.0 d</span><span class="sxs-lookup"><span data-stu-id="746d8-122">Download the Microsoft Azure HITRUST Customer Responsibility Matrix (CRM) blueprint v9.0d</span></span>](https://servicetrust.microsoft.com/ViewPage/Blueprint?command=Download&downloadType=Document&downloadId=3ccde498-4761-4be0-be8b-cd8d379a3a4f&docTab=fc060920-cdb8-11e7-bacf-0bf52b09d912_Healthcare_Blueprint)

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="746d8-123">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="746d8-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="746d8-124">Azure 和 Azure Government</span><span class="sxs-lookup"><span data-stu-id="746d8-124">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="746d8-125">Intune</span><span class="sxs-lookup"><span data-stu-id="746d8-125">Intune</span></span>
- [<span data-ttu-id="746d8-126">Office 365 和 Office 365 美國政府</span><span class="sxs-lookup"><span data-stu-id="746d8-126">Office 365 and Office 365 U.S. Government</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="746d8-127">稽核、報告和認證</span><span class="sxs-lookup"><span data-stu-id="746d8-127">Audits, reports, and certificates</span></span>

<span data-ttu-id="746d8-128">Azure 和 Office 365 的 HITRUST CSF 憑證是兩年有效。</span><span class="sxs-lookup"><span data-stu-id="746d8-128">The HITRUST CSF certification of Azure and Office 365 is valid for two years.</span></span>

- [<span data-ttu-id="746d8-129">Azure 憑證憑證 HITRUST</span><span class="sxs-lookup"><span data-stu-id="746d8-129">Azure HITRUST Letter of Certification</span></span>](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=02eaae7a-9d65-42e6-aec8-a8e22de1a494&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_GRC_Assessment_Reports)
- [<span data-ttu-id="746d8-130">Office 365 HITRUST 憑證</span><span class="sxs-lookup"><span data-stu-id="746d8-130">Office 365 HITRUST Letter of Certification</span></span>](https://aka.ms/O365HITRUSTcertification)

## <a name="accelerate-your-deployment-of-hipaahitrust-solutions-on-azure"></a><span data-ttu-id="746d8-131">加速部署 Azure 上的 HIPAA/HITRUST 解決方案</span><span class="sxs-lookup"><span data-stu-id="746d8-131">Accelerate your deployment of HIPAA/HITRUST solutions on Azure</span></span>

<span data-ttu-id="746d8-132">透過 Azure 安全性與合規性藍圖，利用雲端針對健康情況資料解決方案的優點，HIPAA/HITRUST 健康情況資料和 AI。</span><span class="sxs-lookup"><span data-stu-id="746d8-132">Get a head start on taking advantage of the benefits of the cloud for health data solutions with the Azure Security and Compliance Blueprint — HIPAA/HITRUST Health Data and AI.</span></span> <span data-ttu-id="746d8-133">此藍圖提供的工具和指引，可讓您立即開始建立 HIPAA/HITRUST 解決方案。</span><span class="sxs-lookup"><span data-stu-id="746d8-133">This blueprint provides tools and guidance to get you started building HIPAA/HITRUST solutions today.</span></span>

[<span data-ttu-id="746d8-134">開始使用 Azure HIPAA/HITRUST 藍圖</span><span class="sxs-lookup"><span data-stu-id="746d8-134">Start using the Azure HIPAA/HITRUST Blueprint</span></span>](https://docs.microsoft.com/azure/governance/blueprints/samples/hipaa-hitrust/)

## <a name="accelerate-your-hipaahitrust-compliance-when-using-office-365"></a><span data-ttu-id="746d8-135">使用 Office 365 時，加速您的 HIPAA/HITRUST 合規性</span><span class="sxs-lookup"><span data-stu-id="746d8-135">Accelerate your HIPAA/HITRUST compliance when using Office 365</span></span>

<span data-ttu-id="746d8-136">使用 Office 365，以符合合規性分數的安全且相容的方式來管理健康情況資訊，這可讓您針對類似 HIPAA 和安全性控制架構（如 NIST CSF 和 NIST 800-53）的健康情況規定執行風險評估。</span><span class="sxs-lookup"><span data-stu-id="746d8-136">Use Office 365 to manage health information in a secure and compliant way with Compliance Score, which enables you to perform risk assessments against health regulations like HIPAA and security control frameworks like NIST CSF and NIST 800-53.</span></span> <span data-ttu-id="746d8-137">您可以依照逐步指導方針，瞭解如何實施及維護資料保護控制，以協助您符合醫療保健規範義務。</span><span class="sxs-lookup"><span data-stu-id="746d8-137">You can follow step-by-step guidance to know how to implement and maintain data protection controls that help you meet healthcare compliance obligations.</span></span>

[<span data-ttu-id="746d8-138">開始使用合規性分數</span><span class="sxs-lookup"><span data-stu-id="746d8-138">Start using Compliance Score</span></span>](compliance-score.md)

## <a name="collaborate-with-microsoft-in-the-hitrust-shared-responsibility-program"></a><span data-ttu-id="746d8-139">在 HITRUST 共用責任計畫中與 Microsoft 共同作業</span><span class="sxs-lookup"><span data-stu-id="746d8-139">Collaborate with Microsoft in the HITRUST Shared Responsibility Program</span></span>

<span data-ttu-id="746d8-140">在 HITRUST MyCSF 工具中預先填入您的評估搭配 Azure 的完全繼承或共用責任控制，以加速 HITRUST Microsoft Azure 上的解決方案，並在您的評估上與 Microsoft 合作，以達到法規的要求。</span><span class="sxs-lookup"><span data-stu-id="746d8-140">Accelerate achieving HITRUST compliance for your solution hosted on Microsoft Azure by pre-populating your assessment with fully inherited or shared responsibility controls for Azure in the HITRUST MyCSF tool, and collaborating with Microsoft on your assessment.</span></span>

[<span data-ttu-id="746d8-141">深入了解</span><span class="sxs-lookup"><span data-stu-id="746d8-141">Learn more</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2100268)

## <a name="frequently-asked-questions"></a><span data-ttu-id="746d8-142">常見問題集</span><span class="sxs-lookup"><span data-stu-id="746d8-142">Frequently asked questions</span></span>

<span data-ttu-id="746d8-143">**我可以使用 Azure HITRUST 合規性來建立組織的認證程式嗎？**</span><span class="sxs-lookup"><span data-stu-id="746d8-143">**Can I use the Azure HITRUST compliance to build on my organization's certification process?**</span></span>

<span data-ttu-id="746d8-144">是。</span><span class="sxs-lookup"><span data-stu-id="746d8-144">Yes.</span></span> <span data-ttu-id="746d8-145">如果您的公司需要在 Microsoft 服務上部署的實施 HITRUST 認證，您可以在執行法規遵從性評估時，建立 Azure HITRUST 相容性。</span><span class="sxs-lookup"><span data-stu-id="746d8-145">If your business requires a HITRUST certification for implementations deployed on Microsoft services, you can build on Azure HITRUST compliance when you conduct your compliance assessment.</span></span> <span data-ttu-id="746d8-146">不過，您負責評估 HITRUST 需求和您自己組織內的控制。</span><span class="sxs-lookup"><span data-stu-id="746d8-146">However, you are responsible for evaluating the HITRUST requirements and controls within your own organization.</span></span>

<span data-ttu-id="746d8-147">**如何取得 HITRUST 認證的複本？**</span><span class="sxs-lookup"><span data-stu-id="746d8-147">**How can I get a copy of the HITRUST certification?**</span></span>

<span data-ttu-id="746d8-148">您可以下載[Azure](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=02eaae7a-9d65-42e6-aec8-a8e22de1a494&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_GRC_Assessment_Reports)和[Office 365](https://aka.ms/O365HITRUSTcertification)的憑證憑證的副本。</span><span class="sxs-lookup"><span data-stu-id="746d8-148">You can download a copy of letter of certification for [Azure](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=02eaae7a-9d65-42e6-aec8-a8e22de1a494&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_GRC_Assessment_Reports) and [Office 365](https://aka.ms/O365HITRUSTcertification).</span></span>

<span data-ttu-id="746d8-149">**Office 365 的範圍內服務有哪些？**</span><span class="sxs-lookup"><span data-stu-id="746d8-149">**What are the in-scope services for Office 365?**</span></span>

<span data-ttu-id="746d8-150">HITRUST CSF 認證的範圍內服務是 Exchange Online 封存、Exchange Online Protection、Exchange Online、商務365用 Skype、系統管理中心、SharePoint 線上、Project Online、OneDrive for Business、Office Online、MyAnalytics、Microsoft 團隊、Microsoft 365 多租使用者雲端和 Office 365 GCC。</span><span class="sxs-lookup"><span data-stu-id="746d8-150">The in-scope services of HITRUST CSF certification are Exchange Online Archiving, Exchange Online Protection, Exchange Online, Skype for Business, Admin Center, SharePoint Online, Project Online, OneDrive for Business, Office Online, MyAnalytics, Microsoft Teams, Microsoft 365 Apps for enterprise in Office 365 Multi-tenant cloud and Office 365 GCC.</span></span>

> [!NOTE]
> <span data-ttu-id="746d8-151">Microsoft 365 應用程式企業版可讓您存取各種雲端服務，例如漫遊設定、授權和 OneDrive 使用者雲端儲存裝置，並可讓今後存取其他雲端服務。</span><span class="sxs-lookup"><span data-stu-id="746d8-151">Microsoft 365 Apps for enterprise enables access to various cloud services, such as Roaming Settings, Licensing, and OneDrive consumer cloud storage, and may enable access to additional cloud services in the future.</span></span> <span data-ttu-id="746d8-152">漫遊設定和授權支援 HITRUST 的標準。</span><span class="sxs-lookup"><span data-stu-id="746d8-152">Roaming Settings and Licensing support the standards for HITRUST.</span></span> <span data-ttu-id="746d8-153">OneDrive 使用者雲端儲存區未提供，而且可透過 Microsoft 365 應用程式存取的其他雲端服務，以及 Microsoft 未來可能會提供的雲服務，也可能會支援這些標準。 \*</span><span class="sxs-lookup"><span data-stu-id="746d8-153">OneDrive consumer cloud storage does not, and other cloud services that are accessible through Microsoft 365 Apps for enterprise and that Microsoft may offer in the future also may not, support these standards.\*</span></span>

<span data-ttu-id="746d8-154">**為什麼有些 Office 365 服務不在此認證的範圍內？**</span><span class="sxs-lookup"><span data-stu-id="746d8-154">**Why are some Office 365 services not in the scope of this certification?**</span></span>

<span data-ttu-id="746d8-155">Microsoft 提供最全面的選項，與其他雲端服務提供者相較。</span><span class="sxs-lookup"><span data-stu-id="746d8-155">Microsoft provides the most comprehensive offerings compared to other cloud service providers.</span></span> <span data-ttu-id="746d8-156">為了維持跨地區和行業的廣泛合規性服務，我們根據市場需求、客戶意見反應及產品生命週期，在我們的保證工作範圍內加入服務。</span><span class="sxs-lookup"><span data-stu-id="746d8-156">To keep up with our broad compliance offerings across regions and industries, we include services in the scope of our assurance efforts based on the market demand, customer feedback, and product lifecycle.</span></span> <span data-ttu-id="746d8-157">如果服務並未包含在特定規范產品的目前範圍內，則您的組織有責任根據您的合規性義務評估風險，並決定處理該服務中資料的方式。</span><span class="sxs-lookup"><span data-stu-id="746d8-157">If a service is not included in the current scope of a specific compliance offering, your organization has the responsibility to assess the risks based on your compliance obligations and determine the way you process the data in that service.</span></span> <span data-ttu-id="746d8-158">我們會持續收集客戶的意見反應，與管理機構和審計員合作，以擴大我們的安全性和合規性需求。</span><span class="sxs-lookup"><span data-stu-id="746d8-158">We continuously collect feedback from customers and work with regulators and auditors to expand our compliance coverage to meet your security and compliance needs.</span></span>

<span data-ttu-id="746d8-159">**Microsoft 憑證表示如果我的組織使用 Azure 或 Office 365，其相容性為 HITRUST CSF？**</span><span class="sxs-lookup"><span data-stu-id="746d8-159">**Does Microsoft certification mean that if my organization uses Azure or Office 365, it is compliant with HITRUST CSF?**</span></span>

<span data-ttu-id="746d8-160">當您將資料儲存在 Office 365 之類的 SaaS 中時，Microsoft 與您的組織之間必須共同擔負，以達成法規。</span><span class="sxs-lookup"><span data-stu-id="746d8-160">When you store your data in a SaaS like Office 365, it’s a shared responsibility between Microsoft and your organization to achieve compliance.</span></span> <span data-ttu-id="746d8-161">Microsoft 會管理大部分的基礎結構控制，包括實體安全性、網路控制、應用層級控制等，而且您的組織有責任管理存取控制和保護您的敏感性資料。</span><span class="sxs-lookup"><span data-stu-id="746d8-161">Microsoft manages majority of the infrastructure controls including physical security, network controls, application level controls, etc., and your organization has the responsibility to manage access controls and protect your sensitive data.</span></span> <span data-ttu-id="746d8-162">Office 365 HITRUST 認證示範 Microsoft 的控制架構合規性。</span><span class="sxs-lookup"><span data-stu-id="746d8-162">The Office 365 HITRUST certification demonstrates the compliance of Microsoft’s control framework.</span></span> <span data-ttu-id="746d8-163">為此，您的組織必須實施及維護您自己的資料保護控制，以符合 HITRUST CSF 需求。</span><span class="sxs-lookup"><span data-stu-id="746d8-163">Building on that, your organization needs to implement and maintain your own data protection controls to meet HITRUST CSF requirements.</span></span>

<span data-ttu-id="746d8-164">**使用 Office 365 時，Microsoft 是否會為我的組織提供指導，以執行適當的控制項？**</span><span class="sxs-lookup"><span data-stu-id="746d8-164">**Does Microsoft provide guidance for my organization to implement appropriate controls when using Office 365?**</span></span>

<span data-ttu-id="746d8-165">是的，您可以在合規性分數中尋找建議的客戶動作，以協助您的組織在使用雲端服務時符合複雜的合規性義務。</span><span class="sxs-lookup"><span data-stu-id="746d8-165">Yes, you can find recommended customer actions in Compliance Score, cross-Microsoft Cloud solutions that help your organization meet complex compliance obligations when using cloud services.</span></span> <span data-ttu-id="746d8-166">具體說來，針對 HITRUST CSF，我們建議您使用 NIST 800-53 和 NIST CSF 評估遵循合規性分數來執行風險評估。</span><span class="sxs-lookup"><span data-stu-id="746d8-166">Specifically, for HITRUST CSF, we recommend that you perform risk assessments using the NIST 800-53 and NIST CSF assessments in Compliance Score.</span></span> <span data-ttu-id="746d8-167">在評估中，我們為您提供逐步指導方針，以及您可以用來實施資料保護控制的 Microsoft 解決方案。</span><span class="sxs-lookup"><span data-stu-id="746d8-167">In the assessments, we provide you with step-by-step guidance and the Microsoft solutions you can use to implement your data protection controls.</span></span> <span data-ttu-id="746d8-168">您可以深入瞭解[Microsoft 合規性](compliance-score.md)分數中的合規性分數。</span><span class="sxs-lookup"><span data-stu-id="746d8-168">You can learn more about Compliance Score in [Microsoft Compliance Score](compliance-score.md).</span></span>

<span data-ttu-id="746d8-169">**如何與 Microsoft 接洽？**</span><span class="sxs-lookup"><span data-stu-id="746d8-169">**How do I engage with Microsoft?**</span></span>

<span data-ttu-id="746d8-170">登入 HITRUST MyCSF®工具，並預先填入 Microsoft Azure 上的您的解決方案評估，以及 Azure 的完全繼承或共用責任控制。</span><span class="sxs-lookup"><span data-stu-id="746d8-170">Log in to the HITRUST MyCSF® tool and pre-populate your assessment for your solution hosted on Microsoft Azure with either fully inherited or shared responsibility controls for Azure.</span></span> <span data-ttu-id="746d8-171">Microsoft HITRUST 系統管理員會在 [MyCSF®] 工具上使用其帳戶完成評估的部分。</span><span class="sxs-lookup"><span data-stu-id="746d8-171">A Microsoft HITRUST Administrator will then complete their part of the assessment using their account on the MyCSF® tool.</span></span>

## <a name="resources"></a><span data-ttu-id="746d8-172">資源</span><span class="sxs-lookup"><span data-stu-id="746d8-172">Resources</span></span>

- [<span data-ttu-id="746d8-173">HITRUST 同盟</span><span class="sxs-lookup"><span data-stu-id="746d8-173">HITRUST Alliance</span></span>](https://hitrustalliance.net/)
- [<span data-ttu-id="746d8-174">HITRUST CSF 9。3</span><span class="sxs-lookup"><span data-stu-id="746d8-174">HITRUST CSF 9.3</span></span>](https://hitrustalliance.net/csf-license-agreement/)
- [<span data-ttu-id="746d8-175">瞭解和利用 CSF</span><span class="sxs-lookup"><span data-stu-id="746d8-175">Understanding and Leveraging the CSF</span></span>](https://hitrustalliance.net/understanding-leveraging-csf/)
- [<span data-ttu-id="746d8-176">進一步瞭解 HITRUST 共用責任計畫</span><span class="sxs-lookup"><span data-stu-id="746d8-176">Find out more about the HITRUST Shared Responsibility Program</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2100268)
- [<span data-ttu-id="746d8-177">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="746d8-177">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="746d8-178">下載方案背景資料</span><span class="sxs-lookup"><span data-stu-id="746d8-178">Download the offering backgrounder</span></span>

<span data-ttu-id="746d8-179">是否需要此方案的背景資料文件？</span><span class="sxs-lookup"><span data-stu-id="746d8-179">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="746d8-180">下載 [PDF](https://download.microsoft.com/download/7/2/6/7265470A-862D-4665-91E8-E17BF0C8A1E2/HITRUST-Compliance.pdf)。</span><span class="sxs-lookup"><span data-stu-id="746d8-180">Download the [PDF](https://download.microsoft.com/download/7/2/6/7265470A-862D-4665-91E8-E17BF0C8A1E2/HITRUST-Compliance.pdf).</span></span>
