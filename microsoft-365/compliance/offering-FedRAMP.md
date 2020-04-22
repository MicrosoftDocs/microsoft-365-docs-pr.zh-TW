---
title: 聯邦風險與授權管理計畫 (FedRAMP)
description: Microsoft 授與 US 聯邦風險和授權管理計畫 P-ATOs 和 ATOs。
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
ms.openlocfilehash: d5a6ee0b5ca5c9ba1fbf83f1076940a10134a9f6
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583590"
---
# <a name="federal-risk-and-authorization-management-program-fedramp"></a><span data-ttu-id="15e19-104">聯邦風險與授權管理計畫 (FedRAMP)</span><span class="sxs-lookup"><span data-stu-id="15e19-104">Federal Risk and Authorization Management Program (FedRAMP)</span></span>

## <a name="fedramp-overview"></a><span data-ttu-id="15e19-105">FedRAMP 概述</span><span class="sxs-lookup"><span data-stu-id="15e19-105">FedRAMP overview</span></span>

<span data-ttu-id="15e19-106">美國聯邦風險和授權管理計畫（FedRAMP）是為了提供標準化的方法，以在聯邦資訊安全性管理法案（FISMA）下評估、監控和授權雲端計算產品和服務，並加速聯邦代理商採用安全的雲端解決方案。</span><span class="sxs-lookup"><span data-stu-id="15e19-106">The US Federal Risk and Authorization Management Program (FedRAMP) was established to provide a standardized approach for assessing, monitoring, and authorizing cloud computing products and services under the Federal Information Security Management Act (FISMA), and to accelerate the adoption of secure cloud solutions by federal agencies.</span></span>

<span data-ttu-id="15e19-107">「管理」和「預算」的 Office 現在需要所有的執行聯邦代理商使用 FedRAMP 來驗證雲端服務的安全性。</span><span class="sxs-lookup"><span data-stu-id="15e19-107">The Office of Management and Budget now requires all executive federal agencies to use FedRAMP to validate the security of cloud services.</span></span> <span data-ttu-id="15e19-108">（其他代理商也採用它，所以也適用于公用部門的其他區域。）國家標準和技術協會（NIST）800-53 會設定標準，而 FedRAMP 是證明雲端服務提供者（CSP）符合該標準的程式。</span><span class="sxs-lookup"><span data-stu-id="15e19-108">(Other agencies have also adopted it, so it is useful in other areas of the public sector as well.) The National Institute of Standards and Technology (NIST) 800-53 sets the standard, and FedRAMP is the program that certifies that a cloud service provider (CSP) meets that standard.</span></span>

<span data-ttu-id="15e19-109">向聯邦代理商銷售服務的 Csp desiring 可以採取三個路徑來示範 FedRAMP 合規性：從共同授權委員會（JAB）獲得臨時授權，以進行操作（P-ATO）;接收從聯邦代理商運作的授權（ATO）。或獨立運作，以開發符合程式需求的 CSP 提供套件。</span><span class="sxs-lookup"><span data-stu-id="15e19-109">CSPs desiring to sell services to a federal agency can take three paths to demonstrate FedRAMP compliance: earn a Provisional Authority to Operate (P-ATO) from the Joint Authorization Board (JAB); receive an Authority to Operate (ATO) from a federal agency; or work independently to develop a CSP Supplied Package that meets program requirements.</span></span> <span data-ttu-id="15e19-110">這兩種路徑都需要由「FedRAMP 計畫管理 Office （PMO）」和由程式所獲得的獨立協力廠商組織進行評估的嚴格技術審查。</span><span class="sxs-lookup"><span data-stu-id="15e19-110">Each of these paths requires a stringent technical review by the FedRAMP Program Management Office (PMO) and an assessment by an independent third-party organization that is accredited by the program.</span></span>

<span data-ttu-id="15e19-111">根據 NIST 指導方針，以三個影響層級授與 FedRAMP 授權：低、中和高。</span><span class="sxs-lookup"><span data-stu-id="15e19-111">FedRAMP authorizations are granted at three impact levels based on NIST guidelines — low, medium, and high.</span></span> <span data-ttu-id="15e19-112">這些排名可影響組織的機密性、完整性或可用性喪失的影響：低（有限的影響）、中度（嚴重的不利影響）和高（嚴重或嚴重的影響）。</span><span class="sxs-lookup"><span data-stu-id="15e19-112">These rank the impact that the loss of confidentiality, integrity, or availability could have on an organization — low (limited effect), medium (serious adverse effect), and high (severe or catastrophic effect).</span></span>

## <a name="microsoft-and-fedramp"></a><span data-ttu-id="15e19-113">Microsoft 和 FedRAMP</span><span class="sxs-lookup"><span data-stu-id="15e19-113">Microsoft and FedRAMP</span></span>

<span data-ttu-id="15e19-114">Microsoft 的政府雲端服務（包括 Azure 政府、Office 365 美國政府及 Dynamics 365 政府）符合美國聯邦風險和授權管理計畫（FedRAMP）的苛刻需求，讓美國聯邦代理商能夠從 Microsoft 雲端的成本節約和嚴格安全性中受益。</span><span class="sxs-lookup"><span data-stu-id="15e19-114">Microsoft’s government cloud services, including Azure Government, Office 365 U.S. Government, and Dynamics 365 Government meet the demanding requirements of the US Federal Risk and Authorization Management Program (FedRAMP), enabling U.S. federal agencies to benefit from the cost savings and rigorous security of the Microsoft Cloud.</span></span>

<span data-ttu-id="15e19-115">Microsoft 政府雲端服務提供公用部門的客戶可搭配 FedRAMP 和強健的指導方針與實施工具（包括 Azure 安全性與合規性 FedRAMP 藍圖），以協助在 FedRAMP 環境中自動化 Azure 資源的部署和設定。</span><span class="sxs-lookup"><span data-stu-id="15e19-115">Microsoft government cloud services offer public sector customers a rich array of services compliant with FedRAMP, and robust guidance and implementation tools, including the Azure Security and Compliance Blueprint for FedRAMP, which helps automate deployment and configuration of Azure resources in a FedRAMP environment.</span></span>

<span data-ttu-id="15e19-116">深入瞭解 Microsoft Cloud 上的 FEDRAMP 好處：[下載 FedRAMP 合規性 backgrounder](https://aka.ms/fedramp-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="15e19-116">Learn about the benefits of FEDRAMP on the Microsoft Cloud: [Download the FedRAMP compliance backgrounder](https://aka.ms/fedramp-backgrounder)</span></span>

<span data-ttu-id="15e19-117">瞭解如何使用 Azure 安全性和合規性藍圖加速您的 FEDRAMP 部署：[下載 azure-藍圖 FedRAMP 高 SSP](https://servicetrust.microsoft.com/ViewPage/Blueprint?command=Download&downloadType=Document&downloadId=64de30d4-42c6-47e7-bd52-0be935710df9&docTab=fc060920-cdb8-11e7-bacf-0bf52b09d912_FedRAMP%20Blueprint)</span><span class="sxs-lookup"><span data-stu-id="15e19-117">Learn how to accelerate your FEDRAMP deployment with our Azure Security and Compliance Blueprint: [Download the Azure — Blueprint FedRAMP High SSP](https://servicetrust.microsoft.com/ViewPage/Blueprint?command=Download&downloadType=Document&downloadId=64de30d4-42c6-47e7-bd52-0be935710df9&docTab=fc060920-cdb8-11e7-bacf-0bf52b09d912_FedRAMP%20Blueprint)</span></span>

## <a name="microsoft-azure-p-atos"></a><span data-ttu-id="15e19-118">Microsoft Azure P-ATOs</span><span class="sxs-lookup"><span data-stu-id="15e19-118">Microsoft Azure P-ATOs</span></span>

<span data-ttu-id="15e19-119">Azure 和 Azure 政府已從共同授權委員會取得 P-ATO</span><span class="sxs-lookup"><span data-stu-id="15e19-119">Azure and Azure Government have earned a P-ATO from the Joint Authorization Board</span></span>

<span data-ttu-id="15e19-120">JAB 是主要的控管和決策 FedRAMP。</span><span class="sxs-lookup"><span data-stu-id="15e19-120">The JAB is the primary governance and decision-making body for FedRAMP.</span></span> <span data-ttu-id="15e19-121">來自國防部門的代表、Homeland 的安全性，以及一般的服務管理服務于董事會。</span><span class="sxs-lookup"><span data-stu-id="15e19-121">Representatives from the Department of Defense, the Department of Homeland Security, and the General Services Administration serve on the board.</span></span> <span data-ttu-id="15e19-122">此局會授與 FedRAMP 規範的 Csp P-ATO。</span><span class="sxs-lookup"><span data-stu-id="15e19-122">The board grants a P-ATO to CSPs that have demonstrated FedRAMP compliance.</span></span>

<span data-ttu-id="15e19-123">Azure 會以中等影響等級維護 P-ATO。</span><span class="sxs-lookup"><span data-stu-id="15e19-123">Azure maintains a P-ATO at the Moderate Impact Level.</span></span> <span data-ttu-id="15e19-124">（Azure 是第一個公用雲端，其基礎結構和平臺服務可接收 P-ATO。）JAB 也為「高影響層級」（即「FedRAMP 資格鑒定」的最高的資料行，授權使用 Azure 政府處理高度機密的資料）授與 P-ATO。</span><span class="sxs-lookup"><span data-stu-id="15e19-124">(Azure was the first public cloud with infrastructure and platform services to receive a P-ATO.) The JAB has also granted Azure Government a P-ATO at the High Impact Level, the highest bar for FedRAMP accreditation, which authorizes the use of Azure Government to process highly sensitive data.</span></span> <span data-ttu-id="15e19-125">強制性的 NIST 800-53 標準會建立資訊系統的安全性類別（機密性、完整性和可用性），以評估組織的潛在影響是否應該危及其資訊和資訊系統。</span><span class="sxs-lookup"><span data-stu-id="15e19-125">The mandatory NIST 800-53 standards establish security categories of information systems — confidentiality, integrity, and availability — to assess the potential impact on an organization should its information and information systems be compromised.</span></span> <span data-ttu-id="15e19-126">Azure 和 Azure 政府的 FedRAMP audit 包含的資訊安全性管理系統，涵蓋範圍內服務的基礎結構、開發、作業、管理及支援。</span><span class="sxs-lookup"><span data-stu-id="15e19-126">The FedRAMP audit of Azure and Azure Government included the Information Security Management System that encompasses infrastructure, development, operations, management, and support of in-scope services.</span></span>

<span data-ttu-id="15e19-127">授與 P-ATO 後，CSP 仍需從其所使用之任何政府機關的授權（ATO）。</span><span class="sxs-lookup"><span data-stu-id="15e19-127">Once a P-ATO is granted, a CSP still requires an authorization — an ATO — from any government agency it works with.</span></span> <span data-ttu-id="15e19-128">在 Azure 的情況下，政府代理商可以使用其自己的安全性授權程式中的 Azure P-ATO，並依據它，作為發行同時符合 FedRAMP 需求的代理商 ATO 的基礎。</span><span class="sxs-lookup"><span data-stu-id="15e19-128">In the case of Azure, a government agency can use the Azure P-ATO in its own security authorization process and rely on it as the basis for issuing an agency ATO that also meets FedRAMP requirements.</span></span>

## <a name="dynamics-365-us-government-ato"></a><span data-ttu-id="15e19-129">Dynamics 365 美國政府 ATO</span><span class="sxs-lookup"><span data-stu-id="15e19-129">Dynamics 365 U.S. Government ATO</span></span>

- <span data-ttu-id="15e19-130">Dynamics 365 美國政府已從 HUD 接收 ATO</span><span class="sxs-lookup"><span data-stu-id="15e19-130">Dynamics 365 U.S. Government has received an ATO from HUD</span></span>
- <span data-ttu-id="15e19-131">Dynamics 365 美國政府已透過機架和市內開發（HUD）系的高影響層級授與 FedRAMP 機關 ATO。</span><span class="sxs-lookup"><span data-stu-id="15e19-131">Dynamics 365 U.S. Government was granted a FedRAMP Agency ATO at the High Impact Level by the Department of Housing and Urban Development (HUD).</span></span> <span data-ttu-id="15e19-132">（請注意，雖然認證的範圍限制為政府系 Cloud，但 Dynamics 365 美國政府商務和企業計畫則會在相同的嚴格 FedRAMP 控制群組的情況下運作。）</span><span class="sxs-lookup"><span data-stu-id="15e19-132">(Note that although the scope of the certification is limited to the Government Community Cloud, Dynamics 365 U.S. Government business and enterprise plans operate following the same set of stringent FedRAMP controls.)</span></span>

## <a name="office-365-atos"></a><span data-ttu-id="15e19-133">Office 365 ATOs</span><span class="sxs-lookup"><span data-stu-id="15e19-133">Office 365 ATOs</span></span>

- <span data-ttu-id="15e19-134">Office 365，Office 365 美國政府已從 DHHS ATO。</span><span class="sxs-lookup"><span data-stu-id="15e19-134">Office 365, Office 365 U.S. Government have an ATO from DHHS.</span></span>
- <span data-ttu-id="15e19-135">Office 365 美國政府國防版有 P-ATO 來自國防資訊系統 Agency （DISA）。</span><span class="sxs-lookup"><span data-stu-id="15e19-135">Office 365 U.S. Government Defense has a P-ATO from Defense Information Systems Agency (DISA).</span></span>
- <span data-ttu-id="15e19-136">Office 365 （Enterprise and Business 方案）和 Office 365 美國政府在 Inspector 的「健康情況」和「人力資源」（DHHS）」辦公室中，都有 FedRAMP Agency 的影響層級的 ATO。</span><span class="sxs-lookup"><span data-stu-id="15e19-136">Office 365 (Enterprise and Business plans) and Office 365 U.S. Government have a FedRAMP Agency ATO at the Moderate Impact Level from the Department of Health and Human Services (DHHS) Office of the Inspector General.</span></span> <span data-ttu-id="15e19-137">Office 365 美國政府是第一個以雲端為基礎的電子郵件和共同作業服務，可取得這種授權。</span><span class="sxs-lookup"><span data-stu-id="15e19-137">Office 365 U.S. Government was the first cloud-based email and collaboration service to obtain this authorization.</span></span>
- <span data-ttu-id="15e19-138">任何要使用 O365 美國政府國防版的客戶都可以利用 DISA P-ATO 產生 Agency ATO，以記錄其對 O365 的認可。</span><span class="sxs-lookup"><span data-stu-id="15e19-138">Any customer wishing to consume O365 U.S. Government Defense may utilize the DISA P-ATO to generate an Agency ATO to document their acceptance of O365.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="15e19-139">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="15e19-139">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="15e19-140">Azure 和 Azure Government</span><span class="sxs-lookup"><span data-stu-id="15e19-140">Azure and Azure Government</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2095323)
- [<span data-ttu-id="15e19-141">美國政府的 Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="15e19-141">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="15e19-142">Intune</span><span class="sxs-lookup"><span data-stu-id="15e19-142">Intune</span></span>
- [<span data-ttu-id="15e19-143">Office 365 和 Office 365 美國政府</span><span class="sxs-lookup"><span data-stu-id="15e19-143">Office 365 and Office 365 U.S. Government</span></span>](https://aka.ms/o365-compliance-framework)
- <span data-ttu-id="15e19-144">Office 365 美國政府國防版</span><span class="sxs-lookup"><span data-stu-id="15e19-144">Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="15e19-145">Power BI 雲端服務可作為獨立服務或包含在 Office 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="15e19-145">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="15e19-146">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="15e19-146">Microsoft Defender ATP</span></span>

> [!NOTE]
> <span data-ttu-id="15e19-147">Azure 政府中使用 Azure Active Directory 需要使用 azure public 雲端上部署于 Azure 政府以外的元件。</span><span class="sxs-lookup"><span data-stu-id="15e19-147">The use of Azure Active Directory within Azure Government requires the use of components that are deployed outside of Azure Government on the Azure public cloud.</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="15e19-148">稽核、報告和憑證</span><span class="sxs-lookup"><span data-stu-id="15e19-148">Audits, reports, and certificates</span></span>

<span data-ttu-id="15e19-149">Microsoft 每年都需要 recertify 其雲端服務，以維護其 P-ATO 和 ATOs。</span><span class="sxs-lookup"><span data-stu-id="15e19-149">Microsoft is required to recertify its cloud services each year to maintain its P-ATO and ATOs.</span></span> <span data-ttu-id="15e19-150">若要這麼做，Microsoft 必須不斷監控和評估其安全性控制，並示範服務的安全性仍保持合規性。</span><span class="sxs-lookup"><span data-stu-id="15e19-150">To do so, Microsoft must monitor and assess its security controls continuously, and demonstrate that the security of its services remains in compliance.</span></span>

- [<span data-ttu-id="15e19-151">Microsoft 雲端服務授權</span><span class="sxs-lookup"><span data-stu-id="15e19-151">Microsoft cloud services authorizations</span></span>](https://marketplace.fedramp.gov/#/product/azure-government?sort=productName&productNameSearch=azure)
- [<span data-ttu-id="15e19-152">Microsoft FedRAMP 稽核報告</span><span class="sxs-lookup"><span data-stu-id="15e19-152">Microsoft FedRAMP Audit Reports</span></span>](https://aka.ms/MicrosoftFedRAMPAuditDocuments)

## <a name="ramp-up-your-fedramp-solutions-on-azure-government"></a><span data-ttu-id="15e19-153">提升 Azure 政府的 FedRAMP 解決方案</span><span class="sxs-lookup"><span data-stu-id="15e19-153">Ramp up your FedRAMP solutions on Azure Government</span></span>

<span data-ttu-id="15e19-154">讓 Microsoft 引導您完成 ATO 處理常式，並使用 Azure 安全性和合規性 FedRAMP 藍圖快速部署您的 FedRAMP 解決方案。</span><span class="sxs-lookup"><span data-stu-id="15e19-154">Let Microsoft guide you through the ATO process and quickly deploy your FedRAMP solutions with the Azure Security and Compliance FedRAMP blueprint.</span></span> <span data-ttu-id="15e19-155">我們的藍圖可讓您開始使用參考架構、部署指南、控制執行對應、ATO 工廠支援等等。</span><span class="sxs-lookup"><span data-stu-id="15e19-155">Our blueprint gets you started with reference architectures, deployment guidance, control implementation mappings, ATO Factory support, and more.</span></span>

[<span data-ttu-id="15e19-156">開始使用 Azure FedRAMP 藍圖</span><span class="sxs-lookup"><span data-stu-id="15e19-156">Start using the Azure FedRAMP Blueprint</span></span>](https://aka.ms/fedrampblueprint)

## <a name="frequently-asked-questions"></a><span data-ttu-id="15e19-157">常見問題集</span><span class="sxs-lookup"><span data-stu-id="15e19-157">Frequently asked questions</span></span>

<span data-ttu-id="15e19-158">**Microsoft cloud services 是否遵從聯邦資訊安全性管理法案（FISMA）？**</span><span class="sxs-lookup"><span data-stu-id="15e19-158">**Do Microsoft cloud services comply with the Federal Information Security Management Act (FISMA)?**</span></span>

<span data-ttu-id="15e19-159">FISMA 是一種聯邦法律，只需要我們的聯邦代理商和其合作夥伴才能從符合 FISMA 需求的組織購買資訊系統和服務。</span><span class="sxs-lookup"><span data-stu-id="15e19-159">FISMA is a federal law that requires US federal agencies and their partners to procure information systems and services only from organizations that adhere to FISMA requirements.</span></span> <span data-ttu-id="15e19-160">大部分的代理商及其廠商會指出其是否符合 FISMA 規範，參考其如何在特殊出版物 800-53 rev 4 中符合 NIST 所識別的控制項。</span><span class="sxs-lookup"><span data-stu-id="15e19-160">Most agencies and their vendors that indicate that they are FISMA-compliant are referring to how they meet the controls identified by the NIST in Special Publication 800-53 rev 4.</span></span> <span data-ttu-id="15e19-161">FISMA 處理常式（但不是基礎標準本身）已由2011中的 FedRAMP 所取代。</span><span class="sxs-lookup"><span data-stu-id="15e19-161">The FISMA process (but not the underlying standards themselves) was replaced by FedRAMP in 2011.</span></span>

<span data-ttu-id="15e19-162">**FedRAMP 適用的人員？**</span><span class="sxs-lookup"><span data-stu-id="15e19-162">**To whom does FedRAMP apply?**</span></span>

<span data-ttu-id="15e19-163">' FedRAMP 對於聯邦代理商雲端部署和服務模型，「低」和「適中風險影響層級」是必要的。 '</span><span class="sxs-lookup"><span data-stu-id="15e19-163">'FedRAMP is mandatory for federal agency cloud deployments and service models at the low and moderate risk impact levels.'</span></span> <span data-ttu-id="15e19-164">任何想要接洽 CSP 的聯邦代理商，都可能需要符合 FedRAMP 的規格。</span><span class="sxs-lookup"><span data-stu-id="15e19-164">Any federal agency that wants to engage a CSP may be required to meet FedRAMP specifications.</span></span> <span data-ttu-id="15e19-165">此外，在聯邦政府使用的產品或服務中使用雲端技術的公司，可能需要取得 ATO。</span><span class="sxs-lookup"><span data-stu-id="15e19-165">In addition, companies that employ cloud technologies in products or services used by the federal government may be required to obtain an ATO.</span></span>

<span data-ttu-id="15e19-166">**我的代理人會從何處開始執行其專屬的合規性工作？**</span><span class="sxs-lookup"><span data-stu-id="15e19-166">**Where does my agency start its own compliance effort?**</span></span>

<span data-ttu-id="15e19-167">如需聯邦代理商成功流覽 FedRAMP 並符合其需求的步驟，請移至[www.fedramp.gov/participate/agencies](https://www.fedramp.gov/agency-authorization/)。</span><span class="sxs-lookup"><span data-stu-id="15e19-167">For an overview of the steps federal agencies must take to successfully navigate FedRAMP and meet its requirements, go to [www.fedramp.gov/participate/agencies](https://www.fedramp.gov/agency-authorization/).</span></span>

<span data-ttu-id="15e19-168">**我是否可以在代理人的授權過程中使用 Microsoft 規範？**</span><span class="sxs-lookup"><span data-stu-id="15e19-168">**Can I use Microsoft compliance in my agency’s authorization process?**</span></span>

<span data-ttu-id="15e19-169">是。</span><span class="sxs-lookup"><span data-stu-id="15e19-169">Yes.</span></span> <span data-ttu-id="15e19-170">您可以使用 Microsoft 雲端服務的認證，作為需要聯邦政府機構 ATO 之任何計畫或倡議的基礎。</span><span class="sxs-lookup"><span data-stu-id="15e19-170">You may use the certifications of Microsoft cloud services as the foundation for any program or initiative that requires an ATO from a federal government agency.</span></span> <span data-ttu-id="15e19-171">不過，您必須為這些服務之外的元件達成您自己的授權。</span><span class="sxs-lookup"><span data-stu-id="15e19-171">However, you need to achieve your own authorizations for components outside these services.</span></span>

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a><span data-ttu-id="15e19-172">使用 Microsoft 合規性分數來評估風險</span><span class="sxs-lookup"><span data-stu-id="15e19-172">Use Microsoft Compliance Score to assess your risk</span></span>

<span data-ttu-id="15e19-173">[Microsoft 合規性分數](compliance-score.md)是 [Microsoft 365 合規性中心](microsoft-365-compliance-center.md)的預覽功能，可協助您了解組織的合規性狀況，並採取行動以協助降低風險。</span><span class="sxs-lookup"><span data-stu-id="15e19-173">[Microsoft Compliance Score](compliance-score.md) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization’s compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="15e19-174">[設定合規性分數](compliance-score-setup.md)後，請從**範本**下拉式功能表中選取預先設定的[FedRAMP 範本](https://go.microsoft.com/fwlink/?linkid=2118102)，以協助您的組織符合此法規的需求。</span><span class="sxs-lookup"><span data-stu-id="15e19-174">After [setting up Compliance Score](compliance-score-setup.md), select the pre-configured [FedRAMP template](https://go.microsoft.com/fwlink/?linkid=2118102) from the **Template** drop-down menu to help your organization meet the requirements for this regulation.</span></span>

## <a name="resources"></a><span data-ttu-id="15e19-175">資源</span><span class="sxs-lookup"><span data-stu-id="15e19-175">Resources</span></span>

- [<span data-ttu-id="15e19-176">聯邦風險和授權管理計畫</span><span class="sxs-lookup"><span data-stu-id="15e19-176">Federal Risk and Authorization Management Program</span></span>](https://www.fedramp.gov/)
- [<span data-ttu-id="15e19-177">Microsoft 通用控制措施中樞合規性架構</span><span class="sxs-lookup"><span data-stu-id="15e19-177">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="15e19-178">Microsoft 政府雲端</span><span class="sxs-lookup"><span data-stu-id="15e19-178">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="15e19-179">FedRAMP 安全性評估架構</span><span class="sxs-lookup"><span data-stu-id="15e19-179">FedRAMP Security Assessment Framework</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2099507)
- [<span data-ttu-id="15e19-180">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="15e19-180">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
