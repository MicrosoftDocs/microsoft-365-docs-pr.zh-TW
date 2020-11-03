---
title: 聯邦風險與授權管理計畫 (FedRAMP)
description: Microsoft 授與 US 聯邦風險和授權管理計畫 P-ATOs 和 ATOs。
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
ms.openlocfilehash: 43a5c0f2e207274574c3c08eadd2804b9c241bb7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845063"
---
# <a name="federal-risk-and-authorization-management-program-fedramp"></a><span data-ttu-id="b6905-104">聯邦風險與授權管理計畫 (FedRAMP)</span><span class="sxs-lookup"><span data-stu-id="b6905-104">Federal Risk and Authorization Management Program (FedRAMP)</span></span>

## <a name="fedramp-overview"></a><span data-ttu-id="b6905-105">FedRAMP 概述</span><span class="sxs-lookup"><span data-stu-id="b6905-105">FedRAMP overview</span></span>

<span data-ttu-id="b6905-106">US 聯邦風險和授權管理計畫 (FedRAMP) ，以提供一種標準化的方法，用以評估、監控及授權《聯邦資訊安全性管理法案 (FISMA) 下的雲端計算產品和服務，並加速聯邦代理商採用安全的雲端解決方案。</span><span class="sxs-lookup"><span data-stu-id="b6905-106">The US Federal Risk and Authorization Management Program (FedRAMP) was established to provide a standardized approach for assessing, monitoring, and authorizing cloud computing products and services under the Federal Information Security Management Act (FISMA), and to accelerate the adoption of secure cloud solutions by federal agencies.</span></span>

<span data-ttu-id="b6905-107">「管理」和「預算」的 Office 現在需要所有的執行聯邦代理商使用 FedRAMP 來驗證雲端服務的安全性。</span><span class="sxs-lookup"><span data-stu-id="b6905-107">The Office of Management and Budget now requires all executive federal agencies to use FedRAMP to validate the security of cloud services.</span></span> <span data-ttu-id="b6905-108"> (其他機構也採用這種方式，所以也可用於公用部門的其他區域。 ) 國家標準和技術研究院 (NIST) SP 800-53 會設定必要的標準、建立資訊系統的安全性類別（機密性、完整性和可用性），以評估組織的潛在影響是否應該危及組織的資訊和資訊系統。</span><span class="sxs-lookup"><span data-stu-id="b6905-108">(Other agencies have also adopted it, so it is useful in other areas of the public sector as well.) The National Institute of Standards and Technology (NIST) SP 800-53 sets the mandatory standards, establish security categories of information systems—confidentiality, integrity, and availability—to assess the potential impact on an organization should its information and information systems be compromised.</span></span> <span data-ttu-id="b6905-109">FedRAMP 是一種程式，可證明雲端服務提供者 (CSP) 符合這些標準。</span><span class="sxs-lookup"><span data-stu-id="b6905-109">FedRAMP is the program that certifies that a cloud service provider (CSP) meets those standards.</span></span>

<span data-ttu-id="b6905-110">向聯邦代理商銷售服務的 Csp desiring 可採用三個路徑，以示範 FedRAMP 合規性：</span><span class="sxs-lookup"><span data-stu-id="b6905-110">CSPs desiring to sell services to a federal agency can take three paths to demonstrate FedRAMP compliance:</span></span>

- <span data-ttu-id="b6905-111">贏取 (P-ATO) 從聯合授權板 (JAB) 的臨時授權。</span><span class="sxs-lookup"><span data-stu-id="b6905-111">Earn a Provisional Authority to Operate (P-ATO) from the Joint Authorization Board (JAB).</span></span> <span data-ttu-id="b6905-112">JAB 是主要的控管和決策 FedRAMP。</span><span class="sxs-lookup"><span data-stu-id="b6905-112">The JAB is the primary governance and decision-making body for FedRAMP.</span></span> <span data-ttu-id="b6905-113">來自國防部門的代表、Homeland 的安全性，以及一般的服務管理服務于董事會。</span><span class="sxs-lookup"><span data-stu-id="b6905-113">Representatives from the Department of Defense, the Department of Homeland Security, and the General Services Administration serve on the board.</span></span> <span data-ttu-id="b6905-114">此局會授與 FedRAMP 規範的 Csp P-ATO。</span><span class="sxs-lookup"><span data-stu-id="b6905-114">The board grants a P-ATO to CSPs that have demonstrated FedRAMP compliance.</span></span>
- <span data-ttu-id="b6905-115">從聯邦代理商那裡接收 (ATO) 的授權。</span><span class="sxs-lookup"><span data-stu-id="b6905-115">Receive an Authority to Operate (ATO) from a federal agency.</span></span>
- <span data-ttu-id="b6905-116">或者，您可以個別合作，以開發符合程式需求的 CSP 提供套件。</span><span class="sxs-lookup"><span data-stu-id="b6905-116">Or, work independently to develop a CSP Supplied Package that meets program requirements.</span></span>

<span data-ttu-id="b6905-117">這兩種路徑都需要由「FedRAMP Program Management Office (PMO) 進行嚴格的技術檢查，並由程式所獲得的獨立協力廠商組織進行評估。</span><span class="sxs-lookup"><span data-stu-id="b6905-117">Each of these paths requires a stringent technical review by the FedRAMP Program Management Office (PMO) and an assessment by an independent third-party organization that is accredited by the program.</span></span>

<span data-ttu-id="b6905-118">根據 NIST 指導方針，以三個影響層級授與 FedRAMP 授權：低、中和高。</span><span class="sxs-lookup"><span data-stu-id="b6905-118">FedRAMP authorizations are granted at three impact levels based on NIST guidelines—low, medium, and high.</span></span> <span data-ttu-id="b6905-119">這些層級會影響可能對組織造成的機密性、完整性或可用性喪失的影響：低 (有限的效果) 、中 (嚴重的不利影響) ，以及高 (嚴重或嚴重影響) 。</span><span class="sxs-lookup"><span data-stu-id="b6905-119">These levels rank the impact that the loss of confidentiality, integrity, or availability could have on an organization—low (limited effect), medium (serious adverse effect), and high (severe or catastrophic effect).</span></span>

## <a name="microsoft-and-fedramp"></a><span data-ttu-id="b6905-120">Microsoft 和 FedRAMP</span><span class="sxs-lookup"><span data-stu-id="b6905-120">Microsoft and FedRAMP</span></span>

<span data-ttu-id="b6905-121">Microsoft 的政府雲端服務（包括 Azure 政府、Dynamics 365 政府和 Office 365 美國政府）會符合 US 聯邦風險和授權管理計畫的苛刻需求 (FedRAMP) ，使美國聯邦代理商能夠從 Microsoft 雲端的成本節約和嚴格安全性中受益。</span><span class="sxs-lookup"><span data-stu-id="b6905-121">Microsoft’s government cloud services, including Azure Government, Dynamics 365 Government, and Office 365 U.S. Government meet the demanding requirements of the US Federal Risk and Authorization Management Program (FedRAMP), enabling U.S. federal agencies to benefit from the cost savings and rigorous security of the Microsoft Cloud.</span></span>

<span data-ttu-id="b6905-122">Microsoft 政府雲端服務提供 public tool 客戶與 FedRAMP 及強大的指導方針和執行工具（包括 [FedRAMP 高藍圖](https://aka.ms/fedrampblueprint)）相容，可協助客戶針對必須執行 FedRAMP 高控制措施的任何 Azure 部署架構，部署一組核心原則。</span><span class="sxs-lookup"><span data-stu-id="b6905-122">Microsoft government cloud services offer public sector customers a rich array of services compliant with FedRAMP, and robust guidance and implementation tools, including the [FedRAMP High blueprint](https://aka.ms/fedrampblueprint), which helps customers deploy a core set of policies for any Azure-deployed architecture that must implement FedRAMP High controls.</span></span>

## <a name="microsoft-azure-p-atos"></a><span data-ttu-id="b6905-123">Microsoft Azure P-ATOs</span><span class="sxs-lookup"><span data-stu-id="b6905-123">Microsoft Azure P-ATOs</span></span>

<span data-ttu-id="b6905-124">Azure 和 Azure 政府已從聯合授權板取得「高影響」層級的 P-ATO，其最大的 FedRAMP 資格鑒定，可授權 Azure 和 Azure 政府使用以處理高度機密的資料。</span><span class="sxs-lookup"><span data-stu-id="b6905-124">Azure and Azure Government have earned a P-ATO at the High Impact Level from the Joint Authorization Board, the highest bar for FedRAMP accreditation, which authorizes the use of Azure and Azure Government to process highly sensitive data.</span></span>

<span data-ttu-id="b6905-125">Azure 和 Azure 政府的 FedRAMP audit 包含的資訊安全性管理系統，涵蓋範圍內服務的基礎結構、開發、作業、管理及支援。</span><span class="sxs-lookup"><span data-stu-id="b6905-125">The FedRAMP audit of Azure and Azure Government included the information security management system that encompasses infrastructure, development, operations, management, and support of in-scope services.</span></span> <span data-ttu-id="b6905-126">授與 P-ATO 後，CSP 仍然需要授權 (從其運作的任何政府機構 ATO) 。</span><span class="sxs-lookup"><span data-stu-id="b6905-126">Once a P-ATO is granted, a CSP still requires an authorization (an ATO) from any government agency it works with.</span></span> <span data-ttu-id="b6905-127">針對 Azure，政府代理商可以使用其自己的安全性授權程式中的 Azure P-ATO，並依據它，作為發行同時符合 FedRAMP 需求的代理商 ATO 的基礎。</span><span class="sxs-lookup"><span data-stu-id="b6905-127">For Azure, a government agency can use the Azure P-ATO in its own security authorization process and rely on it as the basis for issuing an agency ATO that also meets FedRAMP requirements.</span></span>

<span data-ttu-id="b6905-128">Azure 在 FedRAMP 高影響層級繼續支援較多的服務，而不是任何其他雲端提供者。</span><span class="sxs-lookup"><span data-stu-id="b6905-128">Azure continues to support more services at FedRAMP High Impact levels than any other cloud provider.</span></span> <span data-ttu-id="b6905-129">而且，Azure 公有雲端中 FedRAMP 高，可滿足許多美國政府客戶的需求，具有較嚴格需求的代理商會繼續依賴 Azure 政府，其可提供額外的保護措施，例如對人員的進一步篩選。</span><span class="sxs-lookup"><span data-stu-id="b6905-129">And while FedRAMP High in the Azure public cloud will meet the needs of many US government customers, agencies with more stringent requirements will continue to rely on Azure Government, which provides additional safeguards such as the heightened screening of personnel.</span></span> <span data-ttu-id="b6905-130">Microsoft 會列出目前在 Azure 政府中可用的所有 [azure 公用服務](https://docs.microsoft.com/azure/azure-government/compliance/azure-services-in-fedramp-auditscope#azure-public-services-by-audit-scope) 至 FedRAMP 高界限，以及為當年計畫的服務。</span><span class="sxs-lookup"><span data-stu-id="b6905-130">Microsoft lists all [Azure public services currently available](https://docs.microsoft.com/azure/azure-government/compliance/azure-services-in-fedramp-auditscope#azure-public-services-by-audit-scope) in Azure Government to the FedRAMP High boundary, as well as services planned for the current year.</span></span>

## <a name="microsoft-dynamics-365-us-government-ato"></a><span data-ttu-id="b6905-131">Microsoft Dynamics 365 美國政府 ATO</span><span class="sxs-lookup"><span data-stu-id="b6905-131">Microsoft Dynamics 365 U.S. Government ATO</span></span>

<span data-ttu-id="b6905-132">Dynamics 365 美國政府已授與 ATO (HUD) 的「美國機架」和「城市開發」高影響層級的 FedRAMP 機關。</span><span class="sxs-lookup"><span data-stu-id="b6905-132">Dynamics 365 U.S. Government was granted a FedRAMP Agency ATO at the High Impact Level by the US Department of Housing and Urban Development (HUD).</span></span> <span data-ttu-id="b6905-133">雖然憑證的範圍限制為政府系 Cloud，但 Dynamics 365 美國政府商務和企業方案卻是在相同組嚴格的 FedRAMP 控制項之後運作。</span><span class="sxs-lookup"><span data-stu-id="b6905-133">Although the scope of the certification is limited to the Government Community Cloud, Dynamics 365 U.S. Government business and enterprise plans operate following the same set of stringent FedRAMP controls.</span></span>

## <a name="microsoft-office-365-and-office-365-us-government-atos"></a><span data-ttu-id="b6905-134">Microsoft Office 365 和 Office 365 美國政府 ATOs</span><span class="sxs-lookup"><span data-stu-id="b6905-134">Microsoft Office 365 and Office 365 U.S. Government ATOs</span></span>

- <span data-ttu-id="b6905-135">Office 365 和 Office 365 美國政府已從美國衛生部門的健康情況及人事服務 (DHHS) 中 ATO。</span><span class="sxs-lookup"><span data-stu-id="b6905-135">Office 365 and Office 365 U.S. Government have an ATO from the US Department of Health and Human Services (DHHS).</span></span>
- <span data-ttu-id="b6905-136">Office 365 美國政府國防版已 P-ATO 美國國防資訊系統代理商 (DISA) 。</span><span class="sxs-lookup"><span data-stu-id="b6905-136">Office 365 U.S. Government Defense has a P-ATO from the US Defense Information Systems Agency (DISA).</span></span> <span data-ttu-id="b6905-137">任何想要部署 Office 365 美國政府國防版的客戶，都可能會使用 DISA P-ATO 產生代理商 ATO，以記錄其接受。</span><span class="sxs-lookup"><span data-stu-id="b6905-137">Any customer wishing to deploy Office 365 U.S. Government Defense may use the DISA P‑ATO to generate an agency ATO to document their acceptance of it.</span></span>
- <span data-ttu-id="b6905-138">Office 365 (enterprise and business 方案) 和 Office 365 美國政府在 Inspector 的 DHHS Office 中的「中級」影響層級擁有 FedRAMP Agency ATO。</span><span class="sxs-lookup"><span data-stu-id="b6905-138">Office 365 (enterprise and business plans) and Office 365 U.S. Government have a FedRAMP Agency ATO at the Moderate Impact Level from the DHHS Office of the Inspector General.</span></span> <span data-ttu-id="b6905-139">Office 365 美國政府是第一個以雲端為基礎的電子郵件和共同作業服務，可取得這種授權。</span><span class="sxs-lookup"><span data-stu-id="b6905-139">Office 365 U.S. Government was the first cloud-based email and collaboration service to obtain this authorization.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="b6905-140">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="b6905-140">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="b6905-141">Azure 和 Azure Government</span><span class="sxs-lookup"><span data-stu-id="b6905-141">Azure and Azure Government</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2095323)
- [<span data-ttu-id="b6905-142">美國政府的 Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b6905-142">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="b6905-143">Intune</span><span class="sxs-lookup"><span data-stu-id="b6905-143">Intune</span></span>
- [<span data-ttu-id="b6905-144">Office 365 和 Office 365 美國 Governmen</span><span class="sxs-lookup"><span data-stu-id="b6905-144">Office 365 and Office 365 U.S. Governmen</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2077751)
- <span data-ttu-id="b6905-145">Office 365 美國政府國防版</span><span class="sxs-lookup"><span data-stu-id="b6905-145">Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="b6905-146">Power BI 雲端服務可作為獨立服務或包含在 Office 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="b6905-146">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="b6905-147">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b6905-147">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="b6905-148">Azure 政府中使用 Azure Active Directory 需要使用 azure public 雲端上部署于 Azure 政府以外的元件。</span><span class="sxs-lookup"><span data-stu-id="b6905-148">The use of Azure Active Directory within Azure Government requires the use of components that are deployed outside of Azure Government on the Azure public cloud.</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="b6905-149">稽核、報告和憑證</span><span class="sxs-lookup"><span data-stu-id="b6905-149">Audits, reports, and certificates</span></span>

<span data-ttu-id="b6905-150">Microsoft 必須每年重新認證其雲端服務，以維護其 P-ATO 和 ATO。</span><span class="sxs-lookup"><span data-stu-id="b6905-150">Microsoft is required to recertify its cloud services each year to maintain its P-ATOs and ATOs.</span></span> <span data-ttu-id="b6905-151">若要這麼做，Microsoft 必須不斷監控和評估其安全性控制，並示範服務的安全性仍保持合規性。</span><span class="sxs-lookup"><span data-stu-id="b6905-151">To do so, Microsoft must monitor and assess its security controls continuously, and demonstrate that the security of its services remains in compliance.</span></span>

- [<span data-ttu-id="b6905-152">Microsoft cloud services FedRAMP 授權</span></span><span class="sxs-lookup"><span data-stu-id="b6905-152">Microsoft cloud services FedRAMP authorizations</span></span></span>](https://marketplace.fedramp.gov/#/product/azure-government?sort=productName&productNameSearch=azure)
- [<span data-ttu-id="b6905-153">Microsoft FedRAMP 稽核報告</span></span><span class="sxs-lookup"><span data-stu-id="b6905-153">Microsoft FedRAMP Audit Reports</span></span></span>](https://aka.ms/MicrosoftFedRAMPAuditDocuments)  

<span data-ttu-id="b6905-154">若要接收其他的 FedRAMP 報告，請傳送電子郵件至 [Azure 聯邦檔](mailto:AzFedDoc@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b6905-154">To receive other FedRAMP reports, send email to [Azure Federal Documentation](mailto:AzFedDoc@microsoft.com).</span></span>

## <a name="quickly-deploy-your-fedramp-solutions-on-azure-government"></a><span data-ttu-id="b6905-155">在 Azure 政府上快速部署您的 FedRAMP 解決方案</span><span class="sxs-lookup"><span data-stu-id="b6905-155">Quickly deploy your FedRAMP solutions on Azure Government</span></span>

<span data-ttu-id="b6905-156">讓 Microsoft 引導您完成 ATO 處理常式，並使用 FedRAMP 的高藍圖快速部署您的 FedRAMP 解決方案，這可協助客戶針對必須實施 FedRAMP 高控制措施的任何 Azure 部署架構，實施一組核心原則。</span><span class="sxs-lookup"><span data-stu-id="b6905-156">Let Microsoft guide you through the ATO process and quickly deploy your FedRAMP solutions using the FedRAMP High blueprint, which helps customers implement a core set of policies for any Azure-deployed architecture that must implement FedRAMP High controls.</span></span>

[<span data-ttu-id="b6905-157">開始使用 Azure FedRAMP 高藍圖</span><span class="sxs-lookup"><span data-stu-id="b6905-157">Start using the Azure FedRAMP High Blueprint</span></span>](https://aka.ms/fedrampblueprint)

## <a name="frequently-asked-questions"></a><span data-ttu-id="b6905-158">常見問題集</span><span class="sxs-lookup"><span data-stu-id="b6905-158">Frequently asked questions</span></span>

<span data-ttu-id="b6905-159">**Microsoft cloud services 是否符合《聯邦資訊安全性管理法案 (FISMA) ？**</span><span class="sxs-lookup"><span data-stu-id="b6905-159">**Do Microsoft cloud services comply with the Federal Information Security Management Act (FISMA)?**</span></span>

<span data-ttu-id="b6905-160">FISMA 是一種聯邦法律，只需要我們的聯邦代理商和其合作夥伴才能從符合 FISMA 需求的組織購買資訊系統和服務。</span><span class="sxs-lookup"><span data-stu-id="b6905-160">FISMA is the federal law that requires US federal agencies and their partners to procure information systems and services only from organizations that adhere to FISMA requirements.</span></span> <span data-ttu-id="b6905-161">大部分的代理商及其廠商會指出其是否符合 FISMA 規範，參考其如何在特殊出版物 800-53 rev 4 中符合 NIST 所識別的控制項。</span><span class="sxs-lookup"><span data-stu-id="b6905-161">Most agencies and their vendors that indicate that they are FISMA-compliant are referring to how they meet the controls identified by the NIST in Special Publication 800-53 rev 4.</span></span> <span data-ttu-id="b6905-162">FISMA 處理常式 (，但不是由2011中的 FedRAMP 所取代的基礎標準本身) 。</span><span class="sxs-lookup"><span data-stu-id="b6905-162">The FISMA process (but not the underlying standards themselves) was replaced by FedRAMP in 2011.</span></span>

<span data-ttu-id="b6905-163">**FedRAMP 適用的人員？**</span><span class="sxs-lookup"><span data-stu-id="b6905-163">**To whom does FedRAMP apply?**</span></span>

<span data-ttu-id="b6905-164">' FedRAMP 對於聯邦代理商雲端部署和服務模型，「低」和「適中風險影響層級」是必要的。 '</span><span class="sxs-lookup"><span data-stu-id="b6905-164">'FedRAMP is mandatory for federal agency cloud deployments and service models at the low and moderate risk impact levels.'</span></span> <span data-ttu-id="b6905-165">任何想要接洽 CSP 的聯邦代理商，都可能需要符合 FedRAMP 的規格。</span><span class="sxs-lookup"><span data-stu-id="b6905-165">Any federal agency that wants to engage a CSP may be required to meet FedRAMP specifications.</span></span> <span data-ttu-id="b6905-166">此外，在聯邦政府使用的產品或服務中使用雲端技術的公司，可能需要取得 ATO。</span><span class="sxs-lookup"><span data-stu-id="b6905-166">In addition, companies that employ cloud technologies in products or services used by the federal government may be required to obtain an ATO.</span></span>

<span data-ttu-id="b6905-167">**我的代理人會從何處開始執行其專屬的合規性工作？**</span><span class="sxs-lookup"><span data-stu-id="b6905-167">**Where does my agency start its own compliance effort?**</span></span>

<span data-ttu-id="b6905-168">如需聯邦代理商順利流覽 FedRAMP 並符合其需求的相關步驟，請移至「 [取得授權」：「代理程式授權](https://www.fedramp.gov/agency-authorization/)」。</span><span class="sxs-lookup"><span data-stu-id="b6905-168">For an overview of the steps federal agencies must take to successfully navigate FedRAMP and meet its requirements, go to [Get Authorized: Agency Authorization](https://www.fedramp.gov/agency-authorization/).</span></span>

<span data-ttu-id="b6905-169">**我是否可以在代理人的授權過程中使用 Microsoft 規範？**</span><span class="sxs-lookup"><span data-stu-id="b6905-169">**Can I use Microsoft compliance in my agency’s authorization process?**</span></span>

<span data-ttu-id="b6905-170">是。</span><span class="sxs-lookup"><span data-stu-id="b6905-170">Yes.</span></span> <span data-ttu-id="b6905-171">您可以使用 Microsoft 雲端服務的認證，作為需要聯邦政府機構 ATO 之任何計畫或倡議的基礎。</span><span class="sxs-lookup"><span data-stu-id="b6905-171">You may use the certifications of Microsoft cloud services as the foundation for any program or initiative that requires an ATO from a federal government agency.</span></span> <span data-ttu-id="b6905-172">不過，您必須為這些服務之外的元件達成您自己的授權。</span><span class="sxs-lookup"><span data-stu-id="b6905-172">However, you need to achieve your own authorizations for components outside these services.</span></span>

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a><span data-ttu-id="b6905-173">使用 Microsoft 合規性管理員來評定風險</span><span class="sxs-lookup"><span data-stu-id="b6905-173">Use Microsoft Compliance Manager to assess your risk</span></span>

<span data-ttu-id="b6905-174">[Microsoft 合規性管理員](compliance-manager.md)是 [Microsoft 365 合規性中心](microsoft-365-compliance-center.md)的功能，可協助您了解組織的合規性態勢，並採取行動以協助降低風險。</span><span class="sxs-lookup"><span data-stu-id="b6905-174">[Microsoft Compliance Manager](compliance-manager.md) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="b6905-175">合規性管理員會提供特優範本以為此法規建立評定。</span><span class="sxs-lookup"><span data-stu-id="b6905-175">Compliance Manager offers a premium template for building an assessment for this regulation.</span></span> <span data-ttu-id="b6905-176">可在合規性管理員的 [評定範本] 頁面尋找範本。</span><span class="sxs-lookup"><span data-stu-id="b6905-176">Find the template in the **assessment templates** page in Compliance Manager.</span></span> <span data-ttu-id="b6905-177">了解如何[在合規性管理員中建立評定](compliance-manager-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="b6905-177">Learn how to [build assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

## <a name="resources"></a><span data-ttu-id="b6905-178">資源</span><span class="sxs-lookup"><span data-stu-id="b6905-178">Resources</span></span>

- [<span data-ttu-id="b6905-179">聯邦風險和授權管理計畫</span><span class="sxs-lookup"><span data-stu-id="b6905-179">Federal Risk and Authorization Management Program</span></span>](https://www.fedramp.gov/)
- [<span data-ttu-id="b6905-180">FedRAMP 安全性評估架構</span><span class="sxs-lookup"><span data-stu-id="b6905-180">FedRAMP Security Assessment Framework</span></span>](https://www.fedramp.gov/assets/resources/documents/FedRAMP_Security_Assessment_Framework.pdf)
- [<span data-ttu-id="b6905-181">在 Microsoft 中管理雲端的合規性</span><span class="sxs-lookup"><span data-stu-id="b6905-181">Managing compliance in the cloud at Microsoft</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="b6905-182">Microsoft 政府雲端</span><span class="sxs-lookup"><span data-stu-id="b6905-182">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="b6905-183">Azure 規範服務</span><span class="sxs-lookup"><span data-stu-id="b6905-183">Azure Compliance Offerings</span></span>](https://aka.ms/azurecompliance)
