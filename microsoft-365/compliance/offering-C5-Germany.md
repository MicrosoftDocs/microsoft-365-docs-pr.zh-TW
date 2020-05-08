---
title: 雲端運算合規性控制目錄 (C5)
description: 了解 Azure、Azure Government 和 Azure Germany 如何展示符合雲端運算合規性控制目錄 (C5) 的證明。
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
ms.openlocfilehash: 48b9e0135198f687430bf195c7dff8a405d15f7e
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065868"
---
# <a name="cloud-computing-compliance-controls-catalog-c5"></a><span data-ttu-id="dc203-104">雲端運算合規性控制目錄 (C5)</span><span class="sxs-lookup"><span data-stu-id="dc203-104">Cloud Computing Compliance Controls Catalog (C5)</span></span>

## <a name="c5-overview"></a><span data-ttu-id="dc203-105">C5 概觀</span><span class="sxs-lookup"><span data-stu-id="dc203-105">C5 overview</span></span>

<span data-ttu-id="dc203-106">在 2016 年，德國聯邦資訊安全局 (Bundesamt für Sicherheit in der Informationstechnik 或 BSI) 建立了雲端運算合規性控制目錄 (C5)。</span><span class="sxs-lookup"><span data-stu-id="dc203-106">In 2016, the German Federal Office for Information Security (Bundesamt für Sicherheit in der Informationstechnik, or BSI) created the Cloud Computing Compliance Controls Catalog (C5).</span></span> <span data-ttu-id="dc203-107">C5 是稽核的標準，為雲端安全性以及德國政府機關和與政府合作的組織採公用雲端解決方案建立強制性的最低基準。</span><span class="sxs-lookup"><span data-stu-id="dc203-107">C5 is an audited standard that establishes a mandatory minimum baseline for cloud security and the adoption of public cloud solutions by German government agencies and organizations that work with government.</span></span> <span data-ttu-id="dc203-108">私人部門也日益採用 C5。</span><span class="sxs-lookup"><span data-stu-id="dc203-108">C5 is also being increasingly adopted by the private sector.</span></span>

<span data-ttu-id="dc203-109">C5 需求目錄的目的旨在為認證雲端服務提供者提供一致的安全架構，並向客戶保證將對其資料進行安全管理。</span><span class="sxs-lookup"><span data-stu-id="dc203-109">The purpose of the C5 catalog of requirements is to provide a consistent security framework for certifying cloud service providers and to give customers assurance that their data will be managed securely.</span></span>

<span data-ttu-id="dc203-110">C5 基於國際公認的 IT 安全標準，例如 ISO/IEC 27001:2013、Cloud Security Alliance Cloud Controls Matrix 3.0.1，以及 BSI 自己的 IT-Grundschutz 目錄。</span><span class="sxs-lookup"><span data-stu-id="dc203-110">C5 is based on internationally recognized IT security standards like ISO/IEC 27001:2013, the Cloud Security Alliance Cloud Controls Matrix 3.0.1, and BSI’s own IT-Grundschutz Catalogues.</span></span> <span data-ttu-id="dc203-111">此目錄包含跨 17 個網域的 114 個需求 (例如資訊安全性與實際安全性的組織)，其中包含所有雲端服務提供者的基本安全性需求，以及處理高度機密資料的額外需求和需要高可用性的情況。</span><span class="sxs-lookup"><span data-stu-id="dc203-111">The catalog consists of 114 requirements across 17 domains — for example, the organization of information security and physical security — with security requirements basic to all cloud service providers, and additional requirements for processing highly confidential data and situations requiring high availability.</span></span>

<span data-ttu-id="dc203-112">BSI 也強調透明度。</span><span class="sxs-lookup"><span data-stu-id="dc203-112">The BSI also puts emphasis on transparency.</span></span> <span data-ttu-id="dc203-113">在審核過程中，雲端提供者必須包含詳細的系統描述，並公開環境參數 (例如管轄權和資料處理位置、服務的佈建，以及其他發給雲端服務的認證)，以及雲端提供者對公共機構有公開義務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dc203-113">As part of an audit, the cloud provider must include a detailed system description and disclose environmental parameters like jurisdiction and data processing location, provision of services, and other certifications issued to the cloud services, and information about the cloud provider’s disclosure obligations to public authorities.</span></span> <span data-ttu-id="dc203-114">這可協助潛在的雲端客戶決定雲端服務是否符合其基本需求，例如符合法律需求 (如資料保護、公司政策)，或能夠應付工業間諜的威脅。</span><span class="sxs-lookup"><span data-stu-id="dc203-114">This helps potential cloud customers decide whether the cloud services meet their essential requirements such as compliance with legal requirements like data protection, company policies, or the ability to address the threat of industrial espionage.</span></span>

## <a name="microsoft-and-c5"></a><span data-ttu-id="dc203-115">Microsoft 和 C5</span><span class="sxs-lookup"><span data-stu-id="dc203-115">Microsoft and C5</span></span>

<span data-ttu-id="dc203-116">Microsoft 雲端服務針對 SOC 2 (AT 第 101 節) 標準，至少一年稽核一次。</span><span class="sxs-lookup"><span data-stu-id="dc203-116">Microsoft cloud services are audited at least annually against SOC 2 (AT Section 101) standards.</span></span> <span data-ttu-id="dc203-117">根據 BSI，C5 稽核可與 SOC 2 稽核結合，以重複使用部分的系統描述和重疊控制的稽核結果。</span><span class="sxs-lookup"><span data-stu-id="dc203-117">According to BSI, a C5 audit can be combined with a SOC 2 audit to reuse parts of the system description and audit results for overlapping controls.</span></span> <span data-ttu-id="dc203-118">Microsoft Azure、Azure Government 和 Azure Germany 根據獨立稽核員執行的稽核評估來維護合併的報告 (C5、SOC 2 類型 2、CSA STAR 證明)，該報告展示符合 C5 的證明。</span><span class="sxs-lookup"><span data-stu-id="dc203-118">Microsoft Azure, Azure Government, and Azure Germany maintain a combined report (C5, SOC 2 Type 2, CSA STAR Attestation) based on the audit assessment performed by an independent auditor, which demonstrates proof of compliance with C5.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="dc203-119">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="dc203-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="dc203-120">Azure、Azure Government 和 Azure Germany</span><span class="sxs-lookup"><span data-stu-id="dc203-120">Azure, Azure Government, and Azure Germany</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="dc203-121">Office 365 德國</span><span class="sxs-lookup"><span data-stu-id="dc203-121">Office 365 Germany</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="dc203-122">稽核、報告和憑證</span><span class="sxs-lookup"><span data-stu-id="dc203-122">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="dc203-123">Azure, Azure Government, and Azure Germany SOC 2 Type II Report.pdf</span><span class="sxs-lookup"><span data-stu-id="dc203-123">Azure, Azure Government, and Azure Germany SOC 2 Type II Report.pdf</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2093520)

## <a name="frequently-asked-questions"></a><span data-ttu-id="dc203-124">常見問題集</span><span class="sxs-lookup"><span data-stu-id="dc203-124">Frequently asked questions</span></span>

<span data-ttu-id="dc203-125">**我是否可以搭配使用 Microsoft 合規性與 C5 來協助組織取得自己的 C5 證明？**</span><span class="sxs-lookup"><span data-stu-id="dc203-125">**Can I use Microsoft compliance with C5 to help my organization get its own C5 attestation?**</span></span>

<span data-ttu-id="dc203-126">是。</span><span class="sxs-lookup"><span data-stu-id="dc203-126">Yes.</span></span> <span data-ttu-id="dc203-127">您可以使用 Microsoft 雲端服務的證明，做為需要 C5 的任何方案或計畫基礎。</span><span class="sxs-lookup"><span data-stu-id="dc203-127">You may use the attestation of Microsoft cloud services as the foundation for any program or initiative that requires C5.</span></span> <span data-ttu-id="dc203-128">不過，您需要為外部元件或在這些服務之上建置的元件實現您自己的 C5 證明。</span><span class="sxs-lookup"><span data-stu-id="dc203-128">However, you need to achieve your own C5 attestation for components outside or built on top of these services.</span></span>

<span data-ttu-id="dc203-129">**C5 與 IT-Grundschutz 目錄有何不同？**</span><span class="sxs-lookup"><span data-stu-id="dc203-129">**What’s the difference between C5 and the IT-Grundschutz Catalogues?**</span></span>

<span data-ttu-id="dc203-130">IT-Grundschutz 提供了特定的方法，可協助組織識別及實施 IT 系統的安全性措施，也是建立 C5 標準的其中一個元素。</span><span class="sxs-lookup"><span data-stu-id="dc203-130">IT-Grundschutz supplies the specific methodology to help organizations identify and implement security measures for IT systems and is one of the elements upon which the C5 standards are built.</span></span> <span data-ttu-id="dc203-131">C5 為雲端服務提供者提供一組稽核標準，但會將實作的詳細資料留給雲端服務提供者。</span><span class="sxs-lookup"><span data-stu-id="dc203-131">C5 provides a set of audit standards for cloud service providers but leaves the details of implementation up to the cloud service provider.</span></span>

<span data-ttu-id="dc203-132">**什麼是 Microsoft Cloud Germany？**</span><span class="sxs-lookup"><span data-stu-id="dc203-132">**What is Microsoft Cloud Germany?**</span></span>

<span data-ttu-id="dc203-133">Microsoft Cloud Germany 實際位於德國，遵守德國隱私權法的要求，該要求限制了將個人資料傳輸到其他國家/地區的行為，並防範其他司法管轄機關存取可能違反國內法律的內容。</span><span class="sxs-lookup"><span data-stu-id="dc203-133">Microsoft Cloud Germany is physically based in Germany, adhering to the requirement of German privacy law, which limits the transfer of personal data to other countries and offers protection against access by authorities from other jurisdictions who could violate domestic laws.</span></span> <span data-ttu-id="dc203-134">Azure Germany 從資料駐留在德國的德國資料中心提供 Azure 服務，並透過受德國法律管理的獨特資料信任者模型提供嚴格的資料存取和控制措施。</span><span class="sxs-lookup"><span data-stu-id="dc203-134">Azure Germany delivers Azure services from German datacenters with data residency in Germany, and it delivers strict data access and control measures provided through a unique data trustee model governed under German law.</span></span>

## <a name="resources"></a><span data-ttu-id="dc203-135">資源</span><span class="sxs-lookup"><span data-stu-id="dc203-135">Resources</span></span>

- <span data-ttu-id="dc203-136">雲端運算合規性控制目錄 (C5) ([英文](https://www.bsi.bund.de/EN/Topics/CloudComputing/Compliance_Criteria_Catalogue/Compliance_Criteria_Catalogue_node.html)) ([德文](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Kriterienkatalog/Kriterienkatalog_node.html))</span><span class="sxs-lookup"><span data-stu-id="dc203-136">Cloud Computing Compliance Controls Catalogue (C5) ([English](https://www.bsi.bund.de/EN/Topics/CloudComputing/Compliance_Criteria_Catalogue/Compliance_Criteria_Catalogue_node.html)) ([German](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Kriterienkatalog/Kriterienkatalog_node.html))</span></span>
- <span data-ttu-id="dc203-137">雲端運算提供者的安全性建議([英文](https://www.bsi.bund.de/EN/Topics/CloudComputing/Secure_use_of_cloud_services/Secure_use_cloud_services_node.html)) ([德文](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Sichere_Nutzung_Cloud/Sichere_Nutzung_Cloud_node.html))</span><span class="sxs-lookup"><span data-stu-id="dc203-137">Security Recommendations for Cloud Computing Providers ([English](https://www.bsi.bund.de/EN/Topics/CloudComputing/Secure_use_of_cloud_services/Secure_use_cloud_services_node.html)) ([German](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Sichere_Nutzung_Cloud/Sichere_Nutzung_Cloud_node.html))</span></span>
- [<span data-ttu-id="dc203-138">合規性報告：C5- und SOC-Testate Azure Deutschland</span><span class="sxs-lookup"><span data-stu-id="dc203-138">Compliance Reports: C5- und SOC-Testate Azure Deutschland</span></span>](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=df100ae1-baf9-4785-8a6d-864c0bc5c308&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)
- <span data-ttu-id="dc203-139">Microsoft Azure Germany 的 [IT-Grundschutz 合規性活頁簿](https://gallery.technet.microsoft.com/Azure-Germany-IT-fca4afd7)</span><span class="sxs-lookup"><span data-stu-id="dc203-139">[IT-Grundschutz Compliance Workbook](https://gallery.technet.microsoft.com/Azure-Germany-IT-fca4afd7) for Microsoft Azure Germany</span></span>
- [<span data-ttu-id="dc203-140">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="dc203-140">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
