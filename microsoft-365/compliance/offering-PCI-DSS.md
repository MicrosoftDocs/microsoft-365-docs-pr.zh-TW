---
title: 支付卡行業 (PCI) 資料安全標準 (DSS)
description: Azure、SharePoint Online 和商務用 OneDrive 符合支付卡行業資料安全標準第 1 級 3.2 版。
keywords: Microsoft 365, 合規性, 方案
localization_priority: Priority
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
ms.openlocfilehash: 12f61d84557cda1af518bb78de22f4901ebdc08f
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898091"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a><span data-ttu-id="199c6-104">支付卡行業 (PCI) 資料安全標準 (DSS)</span><span class="sxs-lookup"><span data-stu-id="199c6-104">Payment Card Industry (PCI) Data Security Standard (DSS)</span></span>

## <a name="pci-dss-overview"></a><span data-ttu-id="199c6-105">PCI DSS 概觀</span><span class="sxs-lookup"><span data-stu-id="199c6-105">PCI DSS overview</span></span>

<span data-ttu-id="199c6-106">支付卡行業 (PCI) 資料安全標準 (DSS) 是一個全球資訊安全性標準，旨在透過進一步控制信用卡資料來防止詐欺行為。</span><span class="sxs-lookup"><span data-stu-id="199c6-106">The Payment Card Industry (PCI) Data Security Standards (DSS) is a global information security standard designed to prevent fraud through increased control of credit card data.</span></span> <span data-ttu-id="199c6-107">任何規模的組織在接受來自五大信用卡品牌 (Visa、MasterCard、American Express、Discover 及 Japan Credit Bureau (JCB)) 的付款卡時，都必須遵循 PCI DSS 標準。</span><span class="sxs-lookup"><span data-stu-id="199c6-107">Organizations of all sizes must follow PCI DSS standards if they accept payment cards from the five major credit card brands — Visa, MasterCard, American Express, Discover, and the Japan Credit Bureau (JCB).</span></span> <span data-ttu-id="199c6-108">任何儲存、處理或傳輸付款和持卡人資料的組織皆需符合 PCI DSS 規範。</span><span class="sxs-lookup"><span data-stu-id="199c6-108">Compliance with PCI DSS is required for any organization that stores, processes, or transmits payment and cardholder data.</span></span>

## <a name="microsoft-and-pci-dss"></a><span data-ttu-id="199c6-109">Microsoft 和 PCI DSS</span><span class="sxs-lookup"><span data-stu-id="199c6-109">Microsoft and PCI DSS</span></span>

<span data-ttu-id="199c6-110">Microsoft 已透過經核准的合格資安評估商 (QSA) 完成年度 PCI DSS 評估。</span><span class="sxs-lookup"><span data-stu-id="199c6-110">Microsoft completed an annual PCI DSS assessment using an approved Qualified Security Assessor (QSA).</span></span> <span data-ttu-id="199c6-111">審查員已審查 Microsoft Azure、Microsoft 商務用 OneDrive 和 Microsoft SharePoint Online 環境，其中包括驗證基礎結構、開發、作業、管理、支援和範圍內服務。</span><span class="sxs-lookup"><span data-stu-id="199c6-111">The auditors reviewed Microsoft Azure, Microsoft OneDrive for Business, and Microsoft SharePoint Online  environments, which include validating the infrastructure, development, operations, management, support, and in-scope services.</span></span> <span data-ttu-id="199c6-112">PCI DSS 根據交易量指定 4 個合規性等級。</span><span class="sxs-lookup"><span data-stu-id="199c6-112">The PCI DSS designates four levels of compliance based on transaction volume.</span></span> <span data-ttu-id="199c6-113">Azure、商務用 OneDrive 和 SharePoint Online 通過服務提供者第 1 級 PCI DSS 3.2 版認證 (最高交易量，一年超過 600 萬)。</span><span class="sxs-lookup"><span data-stu-id="199c6-113">Azure, OneDrive for Business, and SharePoint Online are certified as compliant under PCI DSS version 3.2 at Service Provider Level 1 (the highest volume of transactions — more than 6 million a year).</span></span>

<span data-ttu-id="199c6-114">評估會提供合規性證明 (AoC) 供客戶使用，以及 QSA 發出的合規性報告 (RoC)。</span><span class="sxs-lookup"><span data-stu-id="199c6-114">The assessment results in an Attestation of Compliance (AoC), which is available to customers and Report on Compliance (RoC) issued by the QSA.</span></span> <span data-ttu-id="199c6-115">合規性的有效期從通過審核及收到評估商提供的 AoC 開始，並在 AoC 簽署日一年後結束。</span><span class="sxs-lookup"><span data-stu-id="199c6-115">The effective period for compliance begins upon passing the audit and receiving the AoC from the assessor and ends one year from the date the AoC is signed.</span></span> 

<span data-ttu-id="199c6-116">想要開發持卡人環境或支付卡處理服務的客戶可在許多基礎部分使用這些驗證，從而降低自行取得 PCI DSS 認證的相關工作量和成本。</span><span class="sxs-lookup"><span data-stu-id="199c6-116">Customers who want to develop a cardholder environment or card processing service can use these validations in many of the underlying portions, thereby reducing the associated effort and costs of getting their own PCI DSS certification.</span></span>

<span data-ttu-id="199c6-117">請注意，Azure、商務用 OneDrive 和 SharePoint Online 的 PCI DSS 合規性狀態不會自動轉換成客戶在這些平台上建立或託管的服務的 PCI DSS 認證。</span><span class="sxs-lookup"><span data-stu-id="199c6-117">It is important to understand that PCI DSS compliance status for Azure, OneDrive for Business, and SharePoint Online not automatically translate to PCI DSS certification for the services that customers build or host on these platforms.</span></span> <span data-ttu-id="199c6-118">客戶需負責確保符合 PCI DSS 要求。</span><span class="sxs-lookup"><span data-stu-id="199c6-118">Customers are responsible for ensuring that they achieve compliance with PCI DSS requirements.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="199c6-119">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="199c6-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="199c6-120">Azure 和 Azure Government</span><span class="sxs-lookup"><span data-stu-id="199c6-120">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="199c6-121">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="199c6-121">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="199c6-122">Flow 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="199c6-122">Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="199c6-123">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="199c6-123">Microsoft Graph</span></span>
- <span data-ttu-id="199c6-124">Intune</span><span class="sxs-lookup"><span data-stu-id="199c6-124">Intune</span></span>
- [<span data-ttu-id="199c6-125">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="199c6-125">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- <span data-ttu-id="199c6-126">PowerApps 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="199c6-126">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="199c6-127">Power BI 雲端服務可作為獨立服務或包含在 Office 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="199c6-127">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="199c6-128">商務用 OneDrive 和 SharePoint Online (僅限美國)</span><span class="sxs-lookup"><span data-stu-id="199c6-128">OneDrive for Business and SharePoint Online (United States only)</span></span>

## <a name="audit-reports-and-certificates"></a><span data-ttu-id="199c6-129">稽核、報告和憑證</span><span class="sxs-lookup"><span data-stu-id="199c6-129">Audit, reports, and certificates</span></span>

- [<span data-ttu-id="199c6-130">Azure PCI DSS 合規性證明 (AoC)</span><span class="sxs-lookup"><span data-stu-id="199c6-130">Azure PCI DSS Attestation of Compliance (AoC)</span></span>](https://aka.ms/azure-pci)
- [<span data-ttu-id="199c6-131">商務用 OneDrive 和 SharePoint Online PCI DSS 合規性證明 (AoC)</span><span class="sxs-lookup"><span data-stu-id="199c6-131">OneDrive for Business and SharePoint Online PCI DSS Attestation of Compliance (AoC)</span></span>](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a><span data-ttu-id="199c6-132">在 Azure 執行 PCI DSS 解決方案</span><span class="sxs-lookup"><span data-stu-id="199c6-132">Get your PCI DSS solution running on Azure</span></span>

<span data-ttu-id="199c6-133">使用 Azure 安全性與合規性 PCI DSS 藍圖，在雲端更快速地建立及部署 PCI DSS 解決方案。</span><span class="sxs-lookup"><span data-stu-id="199c6-133">Build and deploy your PCI DSS solution in the cloud even faster with the Azure Security and Compliance PCI DSS Blueprint.</span></span> <span data-ttu-id="199c6-134">取得參考架構、部署指南、控制措施實作對應、自動化的指令碼等。</span><span class="sxs-lookup"><span data-stu-id="199c6-134">Get reference architectures, deployment guidance, control implementation mappings, automated scripts and more.</span></span> <span data-ttu-id="199c6-135">[開始使用 Azure PCI DSS 藍圖](https://aka.ms/pciblueprint)。</span><span class="sxs-lookup"><span data-stu-id="199c6-135">[Start using the Azure PCI DSS Blueprint](https://aka.ms/pciblueprint).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="199c6-136">常見問題集</span><span class="sxs-lookup"><span data-stu-id="199c6-136">Frequently asked questions</span></span>

<span data-ttu-id="199c6-137">**為什麼合規性證明 (AoC) 封面頁顯示「2018 年 6 月」？**</span><span class="sxs-lookup"><span data-stu-id="199c6-137">**Why does the Attestation of Compliance (AoC) cover page say “June 2018”?**</span></span>

<span data-ttu-id="199c6-138">封面頁上的 2018 年 6 月日期是發佈 AoC 範本的時間。</span><span class="sxs-lookup"><span data-stu-id="199c6-138">The June 2018 date on the cover page is when the AoC template was published.</span></span> <span data-ttu-id="199c6-139">如需評估的日期，請參閱第 2 節。</span><span class="sxs-lookup"><span data-stu-id="199c6-139">Refer to Section 2 for the date of the assessment.</span></span>

<span data-ttu-id="199c6-140">**為什麼有多個 Azure 合規性證明 (AoC)？**</span><span class="sxs-lookup"><span data-stu-id="199c6-140">**Why are there multiple Azure Attestations of Compliance (AoCs)?**</span></span>

<span data-ttu-id="199c6-141">Azure AoC 套件具有對應於 Azure 公用、德國和政府雲端的 AoC。</span><span class="sxs-lookup"><span data-stu-id="199c6-141">The Azure AoC package has AoCs corresponding to Azure Public, Germany, and Government cloud.</span></span> <span data-ttu-id="199c6-142">客戶應使用與其 Azure 環境相對應的 AoC。</span><span class="sxs-lookup"><span data-stu-id="199c6-142">Customers should use the AoC that corresponds with their Azure environment.</span></span>  

<span data-ttu-id="199c6-143">**PA DSS 和 PCI DSS 之間的關聯是什麼？**</span><span class="sxs-lookup"><span data-stu-id="199c6-143">**What is the relationship between the PA DSS and PCI DSS?**</span></span>

<span data-ttu-id="199c6-144">支付應用程式資料安全標準 (PA DSS) 是符合 PCI DSS 的一組要求，且取代 Visa 的支付應用程式最佳實務，並合併其他主要發卡機構的合規性要求。</span><span class="sxs-lookup"><span data-stu-id="199c6-144">The Payment Application Data Security Standard (PA DSS) is a set of requirements that comply with the PCI DSS, and replaces Visa’s Payment Application Best Practices, and consolidates the compliance requirements of the other primary card issuers.</span></span> <span data-ttu-id="199c6-145">PA DSS 可協助軟體廠商開發協力廠商應用程式，在卡片授權或結算程序中儲存、處理或傳輸持卡人付款資料。</span><span class="sxs-lookup"><span data-stu-id="199c6-145">The PA DSS helps software vendors develop third-party applications that store, process, or transmit cardholder payment data as part of a card authorization or settlement process.</span></span> <span data-ttu-id="199c6-146">零售商必須使用 PA DSS 認證應用程式以有效地達到其 PCI DSS 合規性。</span><span class="sxs-lookup"><span data-stu-id="199c6-146">Retailers must use PA DSS certified applications to efficiently achieve their PCI DSS compliance.</span></span> <span data-ttu-id="199c6-147">PA DSS 不適用於 Azure。</span><span class="sxs-lookup"><span data-stu-id="199c6-147">The PA DSS does not apply to Azure.</span></span>

<span data-ttu-id="199c6-148">**什麼是收單行？Azure 使用收單行嗎？**</span><span class="sxs-lookup"><span data-stu-id="199c6-148">**What is an acquirer and does Azure use one?**</span></span>

<span data-ttu-id="199c6-149">收單行是處理支付卡交易的銀行或其他實體。</span><span class="sxs-lookup"><span data-stu-id="199c6-149">An acquirer is a bank or other entity that processes payment card transactions.</span></span> <span data-ttu-id="199c6-150">Azure 不會以服務提供支付卡處理，因此不會使用收單行。</span><span class="sxs-lookup"><span data-stu-id="199c6-150">Azure does not offer payment card processing as a service and thus does not use an acquirer.</span></span>

<span data-ttu-id="199c6-151">**PCI DSS 適用於哪些組織和商家？**</span><span class="sxs-lookup"><span data-stu-id="199c6-151">**To what organizations and merchants does the PCI DSS apply?**</span></span>

<span data-ttu-id="199c6-152">PCI DSS 適用於任何接受、傳輸或儲存持卡人資料的公司，無論規模或交易次數。</span><span class="sxs-lookup"><span data-stu-id="199c6-152">PCI DSS applies to any company, no matter the size, or number of transactions, that accepts, transmits, or stores cardholder data.</span></span> <span data-ttu-id="199c6-153">也就是說，如果任何客戶使用信用卡或轉帳卡付款給某公司，便適用 PCI DSS 要求。</span><span class="sxs-lookup"><span data-stu-id="199c6-153">That is, if any customer ever pays a company using a credit or debit card, then the PCI DSS requirements apply.</span></span> <span data-ttu-id="199c6-154">系統會根據 12 個月內的總交易量，以四個層級中的其中一個層級驗證公司。</span><span class="sxs-lookup"><span data-stu-id="199c6-154">Companies are validated at one of four levels based on the total transaction volume over a 12-month period.</span></span> <span data-ttu-id="199c6-155">第 1 級適用於每年處理超過 600 萬筆交易的公司；第 2 級適用於 100 萬至 600 萬筆交易；第 3 級適用於 20,000 至 1 百萬筆交易；而第 4 級則適用於少於 20,000 筆交易。</span><span class="sxs-lookup"><span data-stu-id="199c6-155">Level 1 is for companies that process over 6 million transactions a year; Level 2 for 1 million to 6 million transactions; Level 3 is for 20,000 to 1 million transactions; and Level 4 is for fewer than 20,000 transactions.</span></span>

<span data-ttu-id="199c6-156">**我該從哪裡開始針對部署在 Azure 上的解決方案進行組織的 PCI DSS 合規性工作？**</span><span class="sxs-lookup"><span data-stu-id="199c6-156">**Where do I begin my organization’s PCI DSS compliance efforts for a solution deployed on Azure?**</span></span>

<span data-ttu-id="199c6-157">PCI 安全標準協會提供的資訊可協助您了解特定合規性要求。</span><span class="sxs-lookup"><span data-stu-id="199c6-157">The information that the PCI Security Standards Council makes available is a good place to learn about specific compliance requirements.</span></span> <span data-ttu-id="199c6-158">該協會發佈 [PCI DSS 快速參考指南](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)，提供涉及支付卡處理的商家和其他組織參考。</span><span class="sxs-lookup"><span data-stu-id="199c6-158">The council publishes the [PCI DSS Quick Reference Guide](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) for merchants and others involved in payment card processing.</span></span> <span data-ttu-id="199c6-159">本指南說明 PCI DSS 如何協助保護支付卡交易環境和申請方式。</span><span class="sxs-lookup"><span data-stu-id="199c6-159">The guide explains how the PCI DSS can help protect a payment card transaction environment and how to apply it.</span></span>

<span data-ttu-id="199c6-160">合規性涉及數個因素，包括評估未裝載於 Azure 的系統和程序。</span><span class="sxs-lookup"><span data-stu-id="199c6-160">Compliance involves several factors, including assessing the systems and processes not hosted on Azure.</span></span> <span data-ttu-id="199c6-161">個別要求會根據所使用的 Azure 服務和服務在解決方案內的使用方式而有所不同。</span><span class="sxs-lookup"><span data-stu-id="199c6-161">Individual requirements vary based on which Azure services are used and how they are employed within the solution.</span></span>

<span data-ttu-id="199c6-162">**美國以外的國家/地區是否有符合 PCI DSS 規範的商務用 OneDrive 和 SharePoint Online 方案？**</span><span class="sxs-lookup"><span data-stu-id="199c6-162">**Are there plans for OneDrive for Business and SharePoint Online to be PCI DSS-compliant outside of the United States?**</span></span>

<span data-ttu-id="199c6-163">目前符合 PCI DSS 規範的商務用 OneDrive 和 SharePoint Online 僅限美國。</span><span class="sxs-lookup"><span data-stu-id="199c6-163">Currently OneDrive for Business and SharePoint Online is PCI-DSS compliant only in the United States (US).</span></span> <span data-ttu-id="199c6-164">Microsoft 會評估美國以外地區的需求和時間表，並在其他地區新增至藍圖時提供更新。</span><span class="sxs-lookup"><span data-stu-id="199c6-164">Microsoft will evaluate the requirements and timelines for regions outside of US and provide updates when and if other regions are added to the roadmap.</span></span>

<span data-ttu-id="199c6-165">**商務用 OneDrive 和 SharePoint Online 的適用範圍為何？**</span><span class="sxs-lookup"><span data-stu-id="199c6-165">**What is in-scope for OneDrive for Business and SharePoint Online?**</span></span>

<span data-ttu-id="199c6-166">目前，只有上傳至商務用 OneDrive 和 SharePoint Online 的檔案和文件會收到 PCI DSS 的投訴。</span><span class="sxs-lookup"><span data-stu-id="199c6-166">Currently, only files and documents uploaded to OneDrive for Business and SharePoint Online will be complaint with PCI DSS.</span></span>

## <a name="resources"></a><span data-ttu-id="199c6-167">資源</span><span class="sxs-lookup"><span data-stu-id="199c6-167">Resources</span></span>

- [<span data-ttu-id="199c6-168">PCI 安全標準協會</span><span class="sxs-lookup"><span data-stu-id="199c6-168">PCI Security Standards Council</span></span>](https://www.pcisecuritystandards.org/)
- [<span data-ttu-id="199c6-169">PCI 資料安全性標準</span><span class="sxs-lookup"><span data-stu-id="199c6-169">PCI Data Security Standard</span></span>](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [<span data-ttu-id="199c6-170">Azure PCI DSS 3.2.1 藍圖</span><span class="sxs-lookup"><span data-stu-id="199c6-170">Azure PCI DSS 3.2.1 Blueprint</span></span>](https://docs.microsoft.com/azure/governance/blueprints/samples/pci-dss-3.2.1/)
- [<span data-ttu-id="199c6-171">PCI DSS 快速參考指南</span><span class="sxs-lookup"><span data-stu-id="199c6-171">PCI DSS Quick Reference Guide</span></span>](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [<span data-ttu-id="199c6-172">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="199c6-172">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
