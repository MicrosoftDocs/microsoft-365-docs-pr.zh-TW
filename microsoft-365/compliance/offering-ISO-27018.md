---
title: 保護雲端中個人資料的 ISO/IEC 27018 工作條例規定
description: Microsoft 是第一個遵守此雲端隱私權工作條例規定的雲端提供者。
keywords: Microsoft 365, 合規性, 方案
localization_priority: Priority
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
ms.openlocfilehash: 8e7dfcad68dc56e071072124c02c7e1346ddcde8
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843349"
---
# <a name="isoiec-27018-code-of-practice-for-protecting-personal-data-in-the-cloud"></a><span data-ttu-id="06073-104">保護雲端中個人資料的 ISO/IEC 27018 工作條例規定</span><span class="sxs-lookup"><span data-stu-id="06073-104">ISO/IEC 27018 Code of Practice for Protecting Personal Data in the Cloud</span></span>

## <a name="isoiec-27018-overview"></a><span data-ttu-id="06073-105">ISO/IEC 27018 概觀</span><span class="sxs-lookup"><span data-stu-id="06073-105">ISO/IEC 27018 overview</span></span>

<span data-ttu-id="06073-106">國際標準組織 (ISO) 是獨立的非政府組織，以及全球最大的自願性國際標準開發者。</span><span class="sxs-lookup"><span data-stu-id="06073-106">The International Organization for Standardization (ISO) is an independent nongovernmental organization and the world's largest developer of voluntary international standards.</span></span> <span data-ttu-id="06073-107">ISO/IEC 27000 標準系列可幫助各類型跟大小的組織保持資訊資產安全。</span><span class="sxs-lookup"><span data-stu-id="06073-107">The ISO/IEC 27000 family of standards helps organizations of every type and size keep information assets secure.</span></span>

<span data-ttu-id="06073-108">ISO 在 2014 年採用 ISO/IEC 27018:2014，此為 ISO/IEC 27001 的增補合約，並為雲端隱私權的第一個國際工作條例規定。</span><span class="sxs-lookup"><span data-stu-id="06073-108">In 2014, the ISO adopted ISO/IEC 27018:2014, an addendum to ISO/IEC 27001, the first international code of practice for cloud privacy.</span></span> <span data-ttu-id="06073-109">根據歐盟資料保護規定，它對作為個人識別資訊 (PII) 處理者的雲端服務提供者 (CSP) 提供特定指引，為保護 PII 評估風險和實作最先進的控制措施。</span><span class="sxs-lookup"><span data-stu-id="06073-109">Based on EU data-protection laws, it gives specific guidance to cloud service providers (CSPs) acting as processors of personally identifiable information (PII) on assessing risks and implementing state-of-the-art controls for protecting PII.</span></span>

<span data-ttu-id="06073-110">Microsoft 和 ISO/IEC 27018</span><span class="sxs-lookup"><span data-stu-id="06073-110">Microsoft and ISO/IEC 27018</span></span>

<span data-ttu-id="06073-111">在適用之獨立驗證的安全控制有實施並有效運作的情況下，合格的第三方驗證實體每年至少一次會稽核 Microsoft Azure 和 Azure 德國，已確定其 ISO/IEC 27001 與 ISO/IEC 27018 的合規性。</span><span class="sxs-lookup"><span data-stu-id="06073-111">At least once a year, Microsoft Azure and Azure Germany are audited for compliance with ISO/IEC 27001 and ISO/IEC 27018 by an accredited third-party certification body, providing independent validation that applicable security controls are in place and operating effectively.</span></span> <span data-ttu-id="06073-112">稽核者身為合規性驗證程序之一部分，在適用聲明中確認 Microsoft 範圍內雲端服務和商業技術支援服務已合併 ISO/IEC 27018 控制，用來保護 Azure 中的 PII。</span><span class="sxs-lookup"><span data-stu-id="06073-112">As part of this compliance verification process, the auditors validate in their statement of applicability that Microsoft in-scope cloud services and commercial technical support services have incorporated ISO/IEC 27018 controls for the protection of PII in Azure.</span></span> <span data-ttu-id="06073-113">若要維持合規性，Microsoft 雲端服務必須每年接受第三方檢閱。</span><span class="sxs-lookup"><span data-stu-id="06073-113">To remain compliant, Microsoft cloud services must be subject to annual third-party reviews.</span></span>

<span data-ttu-id="06073-114">透過遵循 ISO/IEC 27001 的標準以及具體化於 ISO/IEC 27018 的工作條例規定，第一家合併此工作條例規定的主要雲端提供者 Microsoft 證明其隱私原則和程序是穩健且符合其高標準。</span><span class="sxs-lookup"><span data-stu-id="06073-114">By following the standards of ISO/IEC 27001 and the code of practice embodied in ISO/IEC 27018, Microsoft (the first major cloud provider to incorporate this code of practice) demonstrates that its privacy policies and procedures are robust and in line with its high standards.</span></span>

- <span data-ttu-id="06073-115">**Microsoft 雲端服務的客戶知道其資料儲存的位置。**</span><span class="sxs-lookup"><span data-stu-id="06073-115">**Customers of Microsoft cloud services know where their data is stored.**</span></span> <span data-ttu-id="06073-116">由於 ISO/IEC 27018 要求經認證的 CSP 通知客戶其資料可能儲存的國家/地區，因此 Microsoft 雲端服務客戶具有所需的可見度以遵循任何適用的資訊安全規則。</span><span class="sxs-lookup"><span data-stu-id="06073-116">Because ISO/IEC 27018 requires certified CSPs to inform customers of the countries in which their data may be stored, Microsoft cloud service customers have the visibility they need to comply with any applicable information security rules.</span></span>
- <span data-ttu-id="06073-117">**客戶資料不會沒有明確許可前即用來行銷或廣告。**</span><span class="sxs-lookup"><span data-stu-id="06073-117">**Customer data won't be used for marketing or advertising without explicit consent.**</span></span> <span data-ttu-id="06073-118">某些 CSP 使用客戶資料做為其個別的商業目的，包括目標廣告。</span><span class="sxs-lookup"><span data-stu-id="06073-118">Some CSPs use customer data for their own commercial ends, including for targeted advertising.</span></span> <span data-ttu-id="06073-119">由於 Microsoft 採用 ISO/IEC 27018 作為其範圍內企業雲端服務，因此客戶大可放心其資料永遠不會在明確許可前以此目的遭使用，而許可也不能成為雲端服務使用的條件。</span><span class="sxs-lookup"><span data-stu-id="06073-119">Because Microsoft has adopted ISO/IEC 27018 for its in-scope enterprise cloud services, customers can rest assured that their data will never be used for such purposes without explicit consent, and that consent cannot be a condition for use of the cloud service.</span></span>
- <span data-ttu-id="06073-120">**Microsoft 客戶知道其 PII 的現行狀況。**</span><span class="sxs-lookup"><span data-stu-id="06073-120">**Microsoft customers know what's happening with their PII.**</span></span> <span data-ttu-id="06073-121">ISO/IEC 27018 需要允許在合理的期間內傳回、轉移和安全處置個人資訊的原則。</span><span class="sxs-lookup"><span data-stu-id="06073-121">ISO/IEC 27018 requires a policy that allows for the return, transfer, and secure disposal of personal information within a reasonable period of time.</span></span> <span data-ttu-id="06073-122">如果 Microsoft 與其他需要存取客戶資料的公司合作，Microsoft 會主動地公開這些子處理者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="06073-122">If Microsoft works with other companies that need access to your customer data, Microsoft proactively discloses the identities of those sub-processors.</span></span>
- <span data-ttu-id="06073-123">**Microsoft 僅遵循具有法律約束力之客戶資料公開的要求。**</span><span class="sxs-lookup"><span data-stu-id="06073-123">**Microsoft complies only with legally binding requests for disclosure of customer data.**</span></span> <span data-ttu-id="06073-124">如果 Microsoft 必須遵守這項要求 (例如犯罪調查)，我們一定會先行通知客戶，除非法律有所禁止。</span><span class="sxs-lookup"><span data-stu-id="06073-124">If Microsoft must comply with such a request (as in the case of a criminal investigation), it will always notify the customer unless it is prohibited by law from doing so.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="06073-125">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="06073-125">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="06073-126">Azure、Azure Government 和 Azure 德國</span><span class="sxs-lookup"><span data-stu-id="06073-126">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="06073-127">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="06073-127">Azure DevOps Services</span></span>
- <span data-ttu-id="06073-128">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="06073-128">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="06073-129">Dynamics 365、Dynamics 365 和 Dynamics 365 德國</span><span class="sxs-lookup"><span data-stu-id="06073-129">Dynamics 365, Dynamics 365, and Dynamics 365 Germany</span></span>
- <span data-ttu-id="06073-130">Microsoft 專業服務：Azure、Dynamics 365、Intune 及商務用 Microsoft 365 中型企業和企業客戶的頂級與內部部署</span><span class="sxs-lookup"><span data-stu-id="06073-130">Microsoft Professional Services: Premier and On Premises for Azure, Dynamics 365, Intune, and for medium business and enterprise customers of Microsoft 365 for business</span></span>
- <span data-ttu-id="06073-131">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="06073-131">Microsoft Graph</span></span>
- <span data-ttu-id="06073-132">Microsoft Healthcare Bot</span><span class="sxs-lookup"><span data-stu-id="06073-132">Microsoft Healthcare Bot</span></span>
- <span data-ttu-id="06073-133">Intune</span><span class="sxs-lookup"><span data-stu-id="06073-133">Intune</span></span>
- <span data-ttu-id="06073-134">Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="06073-134">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="06073-135">Power Automate (先前為 Microsoft Flow) 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="06073-135">Power Automate (formerly Microsoft Flow): cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="06073-136">Office 365、Office 365 美國政府和 Office 365 美國政府國防版</span><span class="sxs-lookup"><span data-stu-id="06073-136">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2077751)
- <span data-ttu-id="06073-137">Office 365 德國</span><span class="sxs-lookup"><span data-stu-id="06073-137">Office 365 Germany</span></span>
- <span data-ttu-id="06073-138">OMS 服務對應</span><span class="sxs-lookup"><span data-stu-id="06073-138">OMS Service Map</span></span>
- <span data-ttu-id="06073-139">PowerApps 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="06073-139">PowerApps cloud service: either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="06073-140">Power BI 雲端服務可作為獨立服務或包含在 Office 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="06073-140">Power BI cloud service: either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="06073-141">Power BI Embedded</span><span class="sxs-lookup"><span data-stu-id="06073-141">Power BI Embedded</span></span>
- <span data-ttu-id="06073-142">Power Virtual Agent</span><span class="sxs-lookup"><span data-stu-id="06073-142">Power Virtual Agents</span></span>
- <span data-ttu-id="06073-143">Microsoft 威脅專家</span><span class="sxs-lookup"><span data-stu-id="06073-143">Microsoft Threat Experts</span></span>
- <span data-ttu-id="06073-144">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="06073-144">Microsoft Stream</span></span>
- <span data-ttu-id="06073-145">Microsoft Defender 進階威脅防護 - 端點偵測與回應、自動調查與補救、安全分數</span><span class="sxs-lookup"><span data-stu-id="06073-145">Microsoft Defender for Endpoint  — Endpoint Detection & Response, Automatic Investigation & Remediation, Secure Score</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="06073-146">稽核、報告和憑證</span><span class="sxs-lookup"><span data-stu-id="06073-146">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="06073-147">稽核週期</span><span class="sxs-lookup"><span data-stu-id="06073-147">Audit cycle</span></span>

<span data-ttu-id="06073-148">Microsoft 雲端和商業技術支援服務會一年根據 ISO/IEC 27018 工作條例規定進行一次稽核，以作為 ISO/IEC 27001 憑證程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="06073-148">Microsoft cloud and commercial technical support services are audited once a year for the ISO/IEC 27018 code of practice as part of the certification process for ISO/IEC 27001.</span></span>

### <a name="audits-and-reports"></a><span data-ttu-id="06073-149">稽核和報告</span><span class="sxs-lookup"><span data-stu-id="06073-149">Audits and reports</span></span>

- [<span data-ttu-id="06073-150">Azure、Dynamics 365 和線上服務：ISO27018 憑證</span><span class="sxs-lookup"><span data-stu-id="06073-150">Azure, Dynamics 365, and Online Services: ISO27018 Certificate</span></span>](https://aka.ms/azureiso27018cert)
- [<span data-ttu-id="06073-151">Azure、Dynamics 365 和線上服務：ISO27018 評估報告</span><span class="sxs-lookup"><span data-stu-id="06073-151">AAzure, Dynamics 365, and Online Services: ISO27018 Assessment Report</span></span>](https://aka.ms/azureiso27001report)
- [<span data-ttu-id="06073-152">Azure 德國：ISO 27018 保護雲端中個人資料的工作條例規定 憑證</span><span class="sxs-lookup"><span data-stu-id="06073-152">Azure Germany: ISO27018 Code of Practice for Protecting Personal Data in the Cloud Certificate</span></span>](https://servicetrust.microsoft.com/Documents/ComplianceReports?downloadDocument=1&documentId=6a0dab80-8382-4af6-980c-ed2ed9a341c6)

### <a name="office-365"></a><span data-ttu-id="06073-153">Office 365</span><span class="sxs-lookup"><span data-stu-id="06073-153">Office 365</span></span>

- [<span data-ttu-id="06073-154">Office 365：ISO 27001、27018 和 27017 稽核評估報告</span><span class="sxs-lookup"><span data-stu-id="06073-154">Office 365: ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)
- [<span data-ttu-id="06073-155">Yammer ISO 27018 稽核評定報告</span><span class="sxs-lookup"><span data-stu-id="06073-155">Yammer ISO 27018 Audit Assessment Report</span></span>](https://aka.ms/YammerISO27018Auditreport)

### <a name="azure-devops-services"></a><span data-ttu-id="06073-156">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="06073-156">Azure DevOps Services</span></span>

- [<span data-ttu-id="06073-157">Azure DevOps Services：ISO 27018 憑證 PII 665918</span><span class="sxs-lookup"><span data-stu-id="06073-157">Azure DevOps Services: ISO27018 Certificate PII 665918</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2062252)

## <a name="frequently-asked-questions"></a><span data-ttu-id="06073-158">常見問題集</span><span class="sxs-lookup"><span data-stu-id="06073-158">Frequently asked questions</span></span>

<span data-ttu-id="06073-159">**ISO/IEC 27018 適用於何者？**</span><span class="sxs-lookup"><span data-stu-id="06073-159">**To whom does ISO/IEC 27018 apply?**</span></span>

<span data-ttu-id="06073-160">此工作條例規定適用於在其他組織合約之下處理 PII 的 CSP。</span><span class="sxs-lookup"><span data-stu-id="06073-160">This code of practice applies to CSPs that process PII under contract for other organizations.</span></span> <span data-ttu-id="06073-161">在 Microsoft，此也套用於這些 CSP 的支援。</span><span class="sxs-lookup"><span data-stu-id="06073-161">At Microsoft, it also applies to the support of those CSPs.</span></span>

<span data-ttu-id="06073-162">**「個人資訊控制者」與「個人資訊處理者」有何不同？**</span><span class="sxs-lookup"><span data-stu-id="06073-162">**What is the difference between 'personal information controllers' and 'personal information processors'?**</span></span>

<span data-ttu-id="06073-163">在 ISO/IEC 27018 之中：</span><span class="sxs-lookup"><span data-stu-id="06073-163">In the context of ISO/IEC 27018:</span></span>

- <span data-ttu-id="06073-164">「控制者」控制個人資訊的集合、持有、處理或使用；它們包含代表另一家公司控制的人員。</span><span class="sxs-lookup"><span data-stu-id="06073-164">'Controllers' control the collection, holding, processing, or use of personal information; they include those who control it on another company's behalf.</span></span>
- <span data-ttu-id="06073-165">「處理者」則代表控制者處理資訊；它們不會針對如何使用資訊或處理目的做決策。</span><span class="sxs-lookup"><span data-stu-id="06073-165">'Processors' process information on behalf of controllers; they do not make decisions as to how to use the information or the purposes of the processing.</span></span> <span data-ttu-id="06073-166">Microsoft 做為您的供應商，是為您提供企業雲端服務的資訊處理者。</span><span class="sxs-lookup"><span data-stu-id="06073-166">In providing its enterprise cloud services, Microsoft (as a vendor to you) is an information processor.</span></span>

<span data-ttu-id="06073-167">**可以在何處查看 Microsoft 的 ISO/IEC 27018 合規性資訊？**</span><span class="sxs-lookup"><span data-stu-id="06073-167">**Where can I view Microsoft compliance information for ISO/IEC 27018?**</span></span>

- <span data-ttu-id="06073-168">您可以檢閱來自 [Azure](https://go.microsoft.com/fwlink/p/?linkid=2078016)、[Microsoft 專業服務](https://www.bsigroup.com/Our-services/Management-system-certification/Certificate-and-Client-Directory-Search/Certificate-Client-Directory-Search-Results/?searchkey=company%3dMicrosoft%2bCorporation&licencenumber=PII%20642270)和 [Power BI](https://go.microsoft.com/fwlink/p/?linkid=2078016) 之 BSI 的 ISO/IEC 27018 憑證。</span><span class="sxs-lookup"><span data-stu-id="06073-168">You can review the ISO/IEC 27018 certificates from BSI for [Azure](https://go.microsoft.com/fwlink/p/?linkid=2078016), [Microsoft Professional Services](https://www.bsigroup.com/Our-services/Management-system-certification/Certificate-and-Client-Directory-Search/Certificate-Client-Directory-Search-Results/?searchkey=company%3dMicrosoft%2bCorporation&licencenumber=PII%20642270), and [Power BI](https://go.microsoft.com/fwlink/p/?linkid=2078016).</span></span>
- <span data-ttu-id="06073-169">您也可以檢閱來自 BSI 的 ISO/IEC 27001 憑證，該憑證是根據 [Dynamics 365](https://aka.ms/Dynamics-CRM-Online-Cert)、[Office 365](https://aka.ms/Office365-Cert) 和 [Azure DevOps Services](https://go.microsoft.com/fwlink/p/?linkid=2062159) 的 ISO/IEC 27018 憑證。</span><span class="sxs-lookup"><span data-stu-id="06073-169">You can also review ISO/IEC 27001 certificates from BSI upon which ISO/IEC 27018 certification is based for [Dynamics 365](https://aka.ms/Dynamics-CRM-Online-Cert), [Office 365](https://aka.ms/Office365-Cert), and [Azure DevOps Services](https://go.microsoft.com/fwlink/p/?linkid=2062159).</span></span>
- <span data-ttu-id="06073-170">若要查看驗證 Microsoft 是否符合 ISO / IEC 27018 合規性之獨立稽核者的 BSI 報告，請造訪 [服務信任入口網站](https://aka.ms/stphelp)。</span><span class="sxs-lookup"><span data-stu-id="06073-170">To review the BSI reports, the independent auditor that validated Microsoft compliance with ISO/IEC 27018, visit the [Service Trust Portal](https://aka.ms/stphelp).</span></span>

<span data-ttu-id="06073-171">**我是否可以在組織的憑證程序中使用 Microsoft 合規性？**</span><span class="sxs-lookup"><span data-stu-id="06073-171">**Can I use Microsoft's compliance in my organization's certification process?**</span></span>

<span data-ttu-id="06073-172">是。</span><span class="sxs-lookup"><span data-stu-id="06073-172">Yes.</span></span> <span data-ttu-id="06073-173">如果 ISO/IEC 27018 合規性對您的企業和在任何 Microsoft 範圍內的企業雲端服務作部署的實作很重要，您可以在合規性評定中使用 Microsoft 的 ISO/IEC 27018 證明，並搭配 Microsoft 的 ISO/IEC 27001 憑證。</span><span class="sxs-lookup"><span data-stu-id="06073-173">If compliance with ISO/IEC 27018 is important for your business and implementations deployed on any of Microsoft in-scope enterprise cloud services, you can use Microsoft's attestation of compliance with ISO/IEC 27018 with Microsoft's certification for ISO/IEC 27001 in your compliance assessment.</span></span>

<span data-ttu-id="06073-174">不過，您有責任確保處理者有參與評估合規性的實作，以及組織中的控制和程序。</span><span class="sxs-lookup"><span data-stu-id="06073-174">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a><span data-ttu-id="06073-175">使用 Microsoft 合規性管理員來評定風險</span><span class="sxs-lookup"><span data-stu-id="06073-175">Use Microsoft Compliance Manager to assess your risk</span></span>

<span data-ttu-id="06073-176">[Microsoft 合規性管理員](compliance-manager.md)是 [Microsoft 365 合規性中心](microsoft-365-compliance-center.md)的功能，可協助您了解組織的合規性態勢，並採取行動以協助降低風險。</span><span class="sxs-lookup"><span data-stu-id="06073-176">[Microsoft Compliance Manager](compliance-manager.md) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="06073-177">合規性管理員會提供特優範本以為此法規建立評定。</span><span class="sxs-lookup"><span data-stu-id="06073-177">Compliance Manager offers a premium template for building an assessment for this regulation.</span></span> <span data-ttu-id="06073-178">可在合規性管理員的 [評定範本] 頁面尋找範本。</span><span class="sxs-lookup"><span data-stu-id="06073-178">Find the template in the **assessment templates** page in Compliance Manager.</span></span> <span data-ttu-id="06073-179">了解如何[在合規性管理員中建立評定](compliance-manager-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="06073-179">Learn how to [build assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

## <a name="resources"></a><span data-ttu-id="06073-180">資源</span><span class="sxs-lookup"><span data-stu-id="06073-180">Resources</span></span>

- [<span data-ttu-id="06073-181">ISO/IEC 27018：2014 工作條例規定</span><span class="sxs-lookup"><span data-stu-id="06073-181">ISO/IEC 27018:2014 code of practice</span></span>](https://aka.ms/ISO.IEC_27018.2014)
- [<span data-ttu-id="06073-182">Microsoft 通用控制措施中樞合規性架構</span><span class="sxs-lookup"><span data-stu-id="06073-182">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="06073-183">Microsoft 企業雲端和技術服務的資料存取原則</span><span class="sxs-lookup"><span data-stu-id="06073-183">Data access policies for Microsoft enterprise cloud and technical services</span></span>](https://www.microsoft.com/trustcenter/Privacy/Who-can-access-your-data-and-on-what-terms)
- [<span data-ttu-id="06073-184">Microsoft Online Services 條款</span><span class="sxs-lookup"><span data-stu-id="06073-184">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="06073-185">Microsoft 政府雲端</span><span class="sxs-lookup"><span data-stu-id="06073-185">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="06073-186">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="06073-186">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
