---
title: 服務組織控制 (SOC)
description: Microsoft 雲端服務符合服務組織控制的作業安全性標準。
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
ms.openlocfilehash: 7cb065bb63bc30c4704abd3d4239fd80bca6d21e
ms.sourcegitcommit: 7bb340f6b47378bcd1c6e770dc975931470bbc26
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/10/2020
ms.locfileid: "43225906"
---
# <a name="service-organization-controls-soc"></a><span data-ttu-id="dc1a1-104">服務組織控制 (SOC)</span><span class="sxs-lookup"><span data-stu-id="dc1a1-104">Service Organization Controls (SOC)</span></span>

## <a name="soc-1-2-and-3-reports-overview"></a><span data-ttu-id="dc1a1-105">SOC 1、2 和 3 報告概觀</span><span class="sxs-lookup"><span data-stu-id="dc1a1-105">SOC 1, 2, and 3 Reports overview</span></span>

<span data-ttu-id="dc1a1-106">越來越多企業將基本功能 (例如資料儲存空間和應用程式存取權) 外包給雲端服務提供者 (CSP) 和其他服務組織。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-106">Increasingly, businesses outsource basic functions such as data storage and access to applications to cloud service providers (CSPs) and other service organizations.</span></span> <span data-ttu-id="dc1a1-107">對此，美國會計師協會 (AICPA) 開發了服務組織控制 (SOC) 架構，這是一種可保護在雲端儲存及處理的資訊機密性和隱私權的控制標準。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-107">In response, the American Institute of Certified Public Accountants (AICPA) has developed the Service Organization Controls (SOC) framework, a standard for controls that safeguard the confidentiality and privacy of information stored and processed in the cloud.</span></span> <span data-ttu-id="dc1a1-108">此架構與國際服務組織的報告標準《國際鑑證業務準則》(ISAE) 相符。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-108">This framework aligns with the International Standard on Assurance Engagements (ISAE), the reporting standard for international service organizations.</span></span>

<span data-ttu-id="dc1a1-109">以 SOC 架構為基礎的服務稽核分為 SOC 1 和 SOC 2 類別，適用於範圍內的 Microsoft 雲端服務。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-109">Service audits based on the SOC framework fall into either SOC 1 and SOC 2 categories that apply to in-scope Microsoft cloud services.</span></span>

<span data-ttu-id="dc1a1-110">SOC 1 稽核 (適用於稽核財務報表的 CPA 公司) 評估影響使用提供者雲端服務的客戶財務報告的 CSP 內部控制效能。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-110">A SOC 1 audit, intended for CPA firms that audit financial statements, evaluates the effectiveness of a CSP's internal controls that affect the financial reports of a customer using the provider's cloud services.</span></span> <span data-ttu-id="dc1a1-111">《簽證服務準則公報第18 號》(SSAE 18) 和《國際鑑證業務準則第 3402 號》</span><span class="sxs-lookup"><span data-stu-id="dc1a1-111">The Statement on Standards for Attestation Engagements (SSAE 18) and the International Standards for Assurance Engagements No.</span></span> <span data-ttu-id="dc1a1-112">(ISAE 3402) 是執行稽核的標準，而且是 SOC 1 報告的基礎。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-112">3402 (ISAE 3402) are the standards under which the audit is performed, and is the basis of the SOC 1 report.</span></span>

<span data-ttu-id="dc1a1-113">SOC 2 稽核根據 AICPA 信任服務原則和標準來計量 CSP 系統的效能。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-113">A SOC 2 audit gauges the effectiveness of a CSP's system based on the AICPA Trust Service Principles and Criteria.</span></span> <span data-ttu-id="dc1a1-114">簽證準則 (AT) 第 101 節中的簽證服務是 SOC 2 和 SOC 3 報告的基礎。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-114">An Attest Engagement under Attestation Standards (AT) Section 101 is the basis of SOC 2 and SOC 3 reports.</span></span>

<span data-ttu-id="dc1a1-115">在 SOC 1 或 SOC 2 稽核結束時，服務稽核員會在 SOC 1 Type 2 或 SOC 2 Type 2 報告中提出意見，其中描述 CSP 的系統，並評估 CSP 對其控制項的描述是否公平。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-115">At the conclusion of a SOC 1 or SOC 2 audit, the service auditor renders an opinion in a SOC 1 Type 2 or SOC 2 Type 2 report, which describes the CSP's system and assesses the fairness of the CSP's description of its controls.</span></span> <span data-ttu-id="dc1a1-116">並且評估 CSP 的控制項是否適當設計、是否已在指定日期執行，且在指定的期間內有效運作。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-116">It also evaluates whether the CSP's controls are designed appropriately, were in operation on a specified date, and were operating effectively over a specified time period.</span></span>

<span data-ttu-id="dc1a1-117">稽核員也可建立 SOC 3 報告 (SOC 2 Type 2 稽核報告的簡化版)，該報告適用於想要保證 CSP 控制項但不需要完整 SOC 2 報告的使用者。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-117">Auditors can also create a SOC 3 report (an abbreviated version of the SOC 2 Type 2 audit report) for users who want assurance about the CSP's controls but don't need a full SOC 2 report.</span></span> <span data-ttu-id="dc1a1-118">只有當 CSP 的 SOC 2 稽核意見不合格時，才能授予 SOC 3 報告。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-118">A SOC 3 report can be conferred only if the CSP has an unqualified audit opinion for SOC 2.</span></span>

## <a name="microsoft-and-soc-1-2-and-3-reports"></a><span data-ttu-id="dc1a1-119">Microsoft 和 SOC 1、SOC 2 和 SOC 3 報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-119">Microsoft and SOC 1, 2, and 3 Reports</span></span>

<span data-ttu-id="dc1a1-120">獨立協力廠商稽核員會根據 SOC 報告架構對 Microsoft 涵蓋的雲端服務進行稽核，至少一年一次。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-120">Microsoft covered cloud services are audited at least annually against the SOC reporting framework by independent third-party auditors.</span></span> <span data-ttu-id="dc1a1-121">Microsoft 雲端服務的稽核涵蓋關於資料安全性、可用性、處理完整性和機密性等控制項 (如果每個服務的範圍內信任原則適用)。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-121">The audit for Microsoft cloud services covers controls for data security, availability, processing integrity, and confidentiality as applicable to in-scope trust principles for each service.</span></span>

<span data-ttu-id="dc1a1-122">Microsoft 已取得 SOC 1 Type 2、SOC 2 Type 2 和 SOC 3 報告。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-122">Microsoft has achieved SOC 1 Type 2, SOC 2 Type 2, and SOC 3 reports.</span></span> <span data-ttu-id="dc1a1-123">通常，SOC 1 和 SOC 2 報告僅提供與 Microsoft 簽署保密協議的客戶使用；SOC 3 報告則提供公開使用。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-123">In general, the availability of SOC 1 and SOC 2 reports is restricted to customers who have signed nondisclosure agreements with Microsoft; the SOC 3 report is publicly available.</span></span>

<span data-ttu-id="dc1a1-124">了解 Microsoft 雲端上 SOC 1、2、3 的優勢：[下載 SOC 1 和 SOC 2 Type 2 報告背景資料](https://aka.ms/soc_backgrounder)</span><span class="sxs-lookup"><span data-stu-id="dc1a1-124">Learn about the benefits of SOC 1, 2, 3 on the Microsoft Cloud: [Download the SOC 1 and SOC 2 type 2 reports backgrounder](https://aka.ms/soc_backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="dc1a1-125">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="dc1a1-125">Microsoft in-scope cloud services</span></span>

### <a name="covered-services-for-soc-1-and-soc-2"></a><span data-ttu-id="dc1a1-126">SOC 1 和 SOC 2 涵蓋的服務</span><span class="sxs-lookup"><span data-stu-id="dc1a1-126">Covered services for SOC 1 and SOC 2</span></span>

- [<span data-ttu-id="dc1a1-127">Azure、Azure Government 和 Azure 德國</span><span class="sxs-lookup"><span data-stu-id="dc1a1-127">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="dc1a1-128">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dc1a1-128">Cloud App Security</span></span>
- [<span data-ttu-id="dc1a1-129">Dynamics 365 和 Dynamics 365 美國政府</span><span class="sxs-lookup"><span data-stu-id="dc1a1-129">Dynamics 365 and Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="dc1a1-130">Graph</span><span class="sxs-lookup"><span data-stu-id="dc1a1-130">Graph</span></span>
- <span data-ttu-id="dc1a1-131">Intune</span><span class="sxs-lookup"><span data-stu-id="dc1a1-131">Intune</span></span>
- <span data-ttu-id="dc1a1-132">Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="dc1a1-132">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="dc1a1-133">Microsoft Flow 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="dc1a1-133">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="dc1a1-134">Office 365、Office 365 美國政府和 Office 365 美國政府國防版</span><span class="sxs-lookup"><span data-stu-id="dc1a1-134">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="dc1a1-135">PowerApps 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="dc1a1-135">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="dc1a1-136">Power BI 雲端服務可作為獨立服務或包含在 Office 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="dc1a1-136">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="dc1a1-137">資料流</span><span class="sxs-lookup"><span data-stu-id="dc1a1-137">Stream</span></span>
- <span data-ttu-id="dc1a1-138">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="dc1a1-138">Azure DevOps Services</span></span>

### <a name="covered-services-for-soc-3"></a><span data-ttu-id="dc1a1-139">SOC 3 涵蓋的服務</span><span class="sxs-lookup"><span data-stu-id="dc1a1-139">Covered services for SOC 3</span></span>

- [<span data-ttu-id="dc1a1-140">Azure、Azure Government 和 Azure 德國</span><span class="sxs-lookup"><span data-stu-id="dc1a1-140">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="dc1a1-141">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dc1a1-141">Cloud App Security</span></span>
- <span data-ttu-id="dc1a1-142">圖形</span><span class="sxs-lookup"><span data-stu-id="dc1a1-142">Graph</span></span>
- <span data-ttu-id="dc1a1-143">Intune</span><span class="sxs-lookup"><span data-stu-id="dc1a1-143">Intune</span></span>
- <span data-ttu-id="dc1a1-144">Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="dc1a1-144">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="dc1a1-145">Microsoft Flow 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="dc1a1-145">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="dc1a1-146">PowerApps 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="dc1a1-146">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="dc1a1-147">Office 365、Office 365 美國政府和 Office 365 美國政府國防版</span><span class="sxs-lookup"><span data-stu-id="dc1a1-147">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="dc1a1-148">Power BI</span><span class="sxs-lookup"><span data-stu-id="dc1a1-148">Power BI</span></span>
- <span data-ttu-id="dc1a1-149">Stream</span><span class="sxs-lookup"><span data-stu-id="dc1a1-149">Stream</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="dc1a1-150">稽核、報告和憑證</span><span class="sxs-lookup"><span data-stu-id="dc1a1-150">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="dc1a1-151">稽核週期</span><span class="sxs-lookup"><span data-stu-id="dc1a1-151">Audit cycle</span></span>

<span data-ttu-id="dc1a1-152">Microsoft 雲端服務針對 SOC 1 (SSAE18，ISAE 3402) 和 SOC 2 (AT 第 101 節) 標準，至少一年稽核一次。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-152">Microsoft cloud services are audited at least annually against SOC 1 (SSAE18, ISAE 3402) and SOC 2 (AT Section 101) standards.</span></span>

#### <a name="azure-cloud-app-security-flow-graph-intune-power-bi-powerapps-stream-and-microsoft-datacenters"></a><span data-ttu-id="dc1a1-153">Azure、Cloud App Security、Flow、Graph、Intune、Power BI、PowerApps、Stream 和 Microsoft 資料中心</span><span class="sxs-lookup"><span data-stu-id="dc1a1-153">Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, and Microsoft Datacenters</span></span>

- [<span data-ttu-id="dc1a1-154">Azure 和 Azure Government SOC 1 Type 2 報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-154">Azure and Azure Government SOC 1 Type 2 Report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2099601)
- [<span data-ttu-id="dc1a1-155">Azure 和 Azure Government SOC 2 Type 2 報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-155">Azure and Azure Government SOC 2 Type 2 Report</span></span>](https://aka.ms/azuresoc2auditreport)
- [<span data-ttu-id="dc1a1-156">Azure 和 Azure Government SOC 3 報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-156">Azure and Azure Government SOC 3 Report</span></span>](https://aka.ms/azuresoc3auditreport)

#### <a name="dynamics-365"></a><span data-ttu-id="dc1a1-157">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="dc1a1-157">Dynamics 365</span></span>

- [<span data-ttu-id="dc1a1-158">Dynamics 365 SOC 1 Type 2 報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-158">Dynamics 365 SOC 1 Type 2 Report</span></span>](https://aka.ms/Dynamics365SOC1AuditReport)
- [<span data-ttu-id="dc1a1-159">Dynamics 365 SOC 2 AT 101 Type II 稽核報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-159">Dynamics 365 SOC 2 AT 101 Type II Audit Report</span></span>](https://aka.ms/Dynamics365SOC2AuditReport)
- [<span data-ttu-id="dc1a1-160">請參閱 Bridge Letter 和其他稽核報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-160">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

#### <a name="office-365"></a><span data-ttu-id="dc1a1-161">Office 365</span><span class="sxs-lookup"><span data-stu-id="dc1a1-161">Office 365</span></span>

- [<span data-ttu-id="dc1a1-162">Office 365 核心版 - SSAE 18 SOC 1 報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-162">Office 365 Core - SSAE 18 SOC 1 Report</span></span>](https://aka.ms/o365SOC-1)
- [<span data-ttu-id="dc1a1-163">Office 365 核心版 - SSAE 18 SOC 2 報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-163">Office 365 Core - SSAE 18 SOC 2 Report</span></span>](https://aka.ms/o365SOC-2)
- [<span data-ttu-id="dc1a1-164">Office 365 核心版 - SSAE 18 SOC 3 報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-164">Office 365 Core - SSAE 18 SOC 3 Report</span></span>](https://aka.ms/o365SOC-3)
- [<span data-ttu-id="dc1a1-165">Office 365 微服務 T1 - SSAE 18 SOC2 Type I 報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-165">Office 365 Microservices T1 – SSAE 18 SOC2 Type I Report</span></span>](https://aka.ms/o365-MS-SOC-2-type1)
- [<span data-ttu-id="dc1a1-166">Office 365 客戶加密箱 SOC 1 SSAE 16 稽核報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-166">Office 365 Customer Lockbox SOC 1 SSAE 16 Audit Report</span></span>](https://aka.ms/Office365CustomerLockboxSOCAuditReport)
- [<span data-ttu-id="dc1a1-167">Yammer SOC 2 AT 101 Type I 稽核報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-167">Yammer SOC 2 AT 101 Type I Audit Report</span></span>](https://aka.ms/YammerSOC2Type1AuditReport)
- [<span data-ttu-id="dc1a1-168">Yammer SOC 2 Type II 報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-168">Yammer SOC 2 Type II Report</span></span>](https://aka.ms/yammerSOC-2)
- [<span data-ttu-id="dc1a1-169">請參閱 Bridge Letter 和其他稽核報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-169">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a><span data-ttu-id="dc1a1-170">常見問題集</span><span class="sxs-lookup"><span data-stu-id="dc1a1-170">Frequently asked questions</span></span>

<span data-ttu-id="dc1a1-171">**如何取得 SOC 報告的複本？**</span><span class="sxs-lookup"><span data-stu-id="dc1a1-171">**How can I get copies of the SOC reports?**</span></span>

<span data-ttu-id="dc1a1-172">您的稽核員可以使用這些報告來比較 Microsoft 商務用雲端服務結果與您自己的法律和法規需求。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-172">With the reports, your auditors can compare Microsoft business cloud services results with your own legal and regulatory requirements.</span></span>

- <span data-ttu-id="dc1a1-173">您可以透過[服務信任平台](https://www.microsoft.com/trustcenter/STP/default.aspx)查看所有 SOC 報告。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-173">You can see all SOC reports through the [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx).</span></span>
- <span data-ttu-id="dc1a1-174">無法存取[服務信任平台](https://www.microsoft.com/trustcenter/STP/default.aspx)的 Azure DevOps 服務客戶可以向 [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) 傳送電子郵件，以取得其 SOC 1 和 SOC 2 報告。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-174">Azure DevOps Service customers that can't access [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx) can email [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) for its SOC 1 and SOC 2 reports.</span></span> <span data-ttu-id="dc1a1-175">此電子郵件僅用於要求 Azure DevOps SOC 報告。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-175">This email is to request Azure DevOps SOC reports only.</span></span>

<span data-ttu-id="dc1a1-176">**Azure SOC 報告多久發行一次？**</span><span class="sxs-lookup"><span data-stu-id="dc1a1-176">**How often are Azure SOC reports issued?**</span></span>

<span data-ttu-id="dc1a1-177">Azure、Cloud App Security、Flow、Graph、Intune、Power BI、PowerApps、串流和 Microsoft 資料中心的 SOC 報告皆以 12 個月執行 (稽核期間) 為基礎，且每半年季發行新報告 (期間結束於 3 月 31 日與 9 月 30 日)。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-177">SOC reports for Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, and Microsoft Datacenters are based on a rolling 12-month run window (audit period) with new reports issued semi-annually (period ends are March 31 and September 30).</span></span> <span data-ttu-id="dc1a1-178">橋接字母會每季發行 (通常是每季結束後當月的第一週)。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-178">Bridge letters are issued on a quarterly basis, usually in the first week of each month following the quarter end.</span></span> <span data-ttu-id="dc1a1-179">客戶可以從服務信任入口網站[下載](https://aka.ms/stp)最新報告。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-179">Customers can [download](https://aka.ms/stp) the latest reports from the Service Trust Portal.</span></span>

<span data-ttu-id="dc1a1-180">**我是否需要自行執行 Microsoft 資料中心的稽核？**</span><span class="sxs-lookup"><span data-stu-id="dc1a1-180">**Do I need to conduct my own audit of Microsoft datacenters?**</span></span>

<span data-ttu-id="dc1a1-181">否。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-181">No.</span></span> <span data-ttu-id="dc1a1-182">Microsoft 會與客戶共用獨立的稽核報告和認證，讓客戶能驗證 Microsoft 合規性及其安全性承諾。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-182">Microsoft shares the independent audit reports and certifications with customers so that they can verify Microsoft compliance with its security commitments.</span></span>

<span data-ttu-id="dc1a1-183">**我是否可以在組織的憑證程序中使用 Microsoft 合規性？**</span><span class="sxs-lookup"><span data-stu-id="dc1a1-183">**Can I use Microsoft's compliance in my organization's certification process?**</span></span>

<span data-ttu-id="dc1a1-184">是。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-184">Yes.</span></span> <span data-ttu-id="dc1a1-185">當您將應用程式和資料移轉到涵蓋的 Microsoft 雲端服務時，您可以將 Microsoft 持有的稽核和認證作為建立基礎。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-185">When you migrate your applications and data to covered Microsoft cloud services, you can build on the audits and certifications that Microsoft holds.</span></span> <span data-ttu-id="dc1a1-186">獨立報告可證明 Microsoft 實施用於維護資料安全性和隱私權的控制項效能。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-186">The independent reports attest to the effectiveness of controls that Microsoft has implemented to help maintain the security and privacy of your data.</span></span>

<span data-ttu-id="dc1a1-187">**我要從何處著手組織自身的合規性工作？**</span><span class="sxs-lookup"><span data-stu-id="dc1a1-187">**Where do I start with my organization's own compliance effort?**</span></span>

<span data-ttu-id="dc1a1-188">[適用於服務組織的 SOC 套件](https://aka.ms/soc-toolkit)是了解 SOC 報告程序及推動貴組織使用這些報告的實用資源。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-188">The [SOC Toolkit for Service Organizations](https://aka.ms/soc-toolkit) is a helpful resource for understanding SOC reporting processes and promoting your organization's use of them.</span></span>

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a><span data-ttu-id="dc1a1-189">使用 Microsoft 合規性分數來評估風險</span><span class="sxs-lookup"><span data-stu-id="dc1a1-189">Use Microsoft Compliance Score to assess your risk</span></span>

<span data-ttu-id="dc1a1-190">[Microsoft 合規性分數](compliance-score.md)是 [Microsoft 365 合規性中心](microsoft-365-compliance-center.md)的預覽功能，可協助您了解組織的合規性狀況，並採取行動以協助降低風險。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-190">[Microsoft Compliance Score](compliance-score.md) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="dc1a1-191">[設定合規性分數](compliance-score-setup.md)之後，從 [範本]\*\*\*\* 下拉式功能表中選擇預先設定的 [SOC 1 範本][](https://go.microsoft.com/fwlink/?linkid=2117918) 和 [SOC 2 範本][](https://go.microsoft.com/fwlink/?linkid=2117919)，以幫助您的組織滿足此法規的要求。</span><span class="sxs-lookup"><span data-stu-id="dc1a1-191">After [setting up Compliance Score](compliance-score-setup.md), select the pre-configured [SOC 1 template](https://go.microsoft.com/fwlink/?linkid=2117918) and the [SOC 2 template](https://go.microsoft.com/fwlink/?linkid=2117919) from the **Template** drop-down menu to help your organization meet the requirements for this regulation.</span></span>

## <a name="resources"></a><span data-ttu-id="dc1a1-192">資源</span><span class="sxs-lookup"><span data-stu-id="dc1a1-192">Resources</span></span>

- [<span data-ttu-id="dc1a1-193">使用 Microsoft 雲端服務，更進一步保護您的資料</span><span class="sxs-lookup"><span data-stu-id="dc1a1-193">Better protect your data by using Microsoft cloud services</span></span>](https://www.microsoft.com/trustcenter/guidance/protect-data)
- [<span data-ttu-id="dc1a1-194">服務組織控制 (SOC) 報告</span><span class="sxs-lookup"><span data-stu-id="dc1a1-194">Service Organization Control (SOC) Reports</span></span>](https://aka.ms/mssocreports)
- [<span data-ttu-id="dc1a1-195">SSAE 16 概觀</span><span class="sxs-lookup"><span data-stu-id="dc1a1-195">SSAE 16 Overview</span></span>](http://ssae16.com/SSAE16_overview.html)
- [<span data-ttu-id="dc1a1-196">ISAE 3402 概觀</span><span class="sxs-lookup"><span data-stu-id="dc1a1-196">ISAE 3402 Overview</span></span>](http://isae3402.com/ISAE3402_overview.html)
- [<span data-ttu-id="dc1a1-197">Microsoft Online Services 條款</span><span class="sxs-lookup"><span data-stu-id="dc1a1-197">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="dc1a1-198">Microsoft 政府雲端</span><span class="sxs-lookup"><span data-stu-id="dc1a1-198">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="dc1a1-199">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="dc1a1-199">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
