---
title: ISO/IEC 27017:2015 資訊安全性控制的工作條例規定
description: Microsoft 雲端服務已實作此「資訊安全性控制的工作條例規定」。
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
ms.openlocfilehash: c289b8c3ad2e177a9c2ee575014d8682da553352
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417687"
---
# <a name="isoiec-270172015-code-of-practice-for-information-security-controls"></a><span data-ttu-id="09f52-104">資訊安全性控制的 ISO/IEC 27017:2015 工作條例規定</span><span class="sxs-lookup"><span data-stu-id="09f52-104">ISO/IEC 27017:2015 Code of Practice for Information Security Controls</span></span>

## <a name="iso-iec-27017-overview"></a><span data-ttu-id="09f52-105">ISO-IEC 27017 概觀</span><span class="sxs-lookup"><span data-stu-id="09f52-105">ISO-IEC 27017 Overview</span></span>

<span data-ttu-id="09f52-106">ISO/IEC 27017:2015 工作條例規定專為組織設計，可在基於 ISO/IEC 27002:2013 實作雲端運算資訊安全管理系統時，用來做為選取雲端服務資訊安全性控制的參考。</span><span class="sxs-lookup"><span data-stu-id="09f52-106">The ISO/IEC 27017:2015 code of practice is designed for organizations to use as a reference for selecting cloud services information security controls when implementing a cloud computing information security management system based on ISO/IEC 27002:2013.</span></span> <span data-ttu-id="09f52-107">雲端服務提供者也可以使用它做為實作常見防護控制的指導方針文件。</span><span class="sxs-lookup"><span data-stu-id="09f52-107">It can also be used by cloud service providers as a guidance document for implementing commonly accepted protection controls.</span></span>

<span data-ttu-id="09f52-108">此國際標準提供基於 ISO/IEC 27002 的額外雲端特定實作指導方針，並提供額外的控制來處理雲端特定資訊安全性威脅和風險，請查閱 ISO/IEC 27002:2013 的條款 5 至 18 中相關的控制、實作指導方針及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="09f52-108">This international standard provides additional cloud-specific implementation guidance based on ISO/IEC 27002, and provides additional controls to address cloud-specific information security threats and risks referring to clauses 5–18 in ISO/IEC 27002: 2013 for controls, implementation guidance, and other information.</span></span> <span data-ttu-id="09f52-109">具體來說，此標準提供 ISO/IEC 27002 中 37 項控制的指導方針，並提供未與 ISO/IEC 27002 中重複的七項新控制。</span><span class="sxs-lookup"><span data-stu-id="09f52-109">Specifically, this standard provides guidance on 37 controls in ISO/IEC 27002, and it also features seven new controls that are not duplicated in ISO/IEC 27002.</span></span> <span data-ttu-id="09f52-110">這些新的控制能解決下列重要領域：</span><span class="sxs-lookup"><span data-stu-id="09f52-110">These new controls address the following important areas:</span></span>

- <span data-ttu-id="09f52-111">雲端運算環境內的共同角色和責任</span><span class="sxs-lookup"><span data-stu-id="09f52-111">Shared roles and responsibilities within a cloud computing environment</span></span>
- <span data-ttu-id="09f52-112">在合約終止時移除並退回雲端服務客戶資產</span><span class="sxs-lookup"><span data-stu-id="09f52-112">Removal and return of cloud service customer assets upon contract termination</span></span>
- <span data-ttu-id="09f52-113">保護客戶的虛擬環境並與其他客戶的虛擬環境隔離</span><span class="sxs-lookup"><span data-stu-id="09f52-113">Protection and separation of a customer’s virtual environment from environments of other customers</span></span>
- <span data-ttu-id="09f52-114">虛擬機器強化需求，以滿足商務需求</span><span class="sxs-lookup"><span data-stu-id="09f52-114">Virtual machine hardening requirements to meet business needs</span></span>
- <span data-ttu-id="09f52-115">雲端運算環境系統管理操作的程序</span><span class="sxs-lookup"><span data-stu-id="09f52-115">Procedures for administrative operations of a cloud computing environment</span></span>
- <span data-ttu-id="09f52-116">讓客戶能夠監視雲端運算環境內的相關活動</span><span class="sxs-lookup"><span data-stu-id="09f52-116">Enabling customers to monitor relevant activities within a cloud computing environment</span></span>
- <span data-ttu-id="09f52-117">結合虛擬和實體網路的安全性管理</span><span class="sxs-lookup"><span data-stu-id="09f52-117">Alignment of security management for virtual and physical networks</span></span>

## <a name="microsoft-and-isoiec-27017"></a><span data-ttu-id="09f52-118">Microsoft 和 ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="09f52-118">Microsoft and ISO/IEC 27017</span></span>

<span data-ttu-id="09f52-119">ISO/IEC 27017 在為雲端服務提供者和雲端服務客戶提供指導方針方面與眾不同。</span><span class="sxs-lookup"><span data-stu-id="09f52-119">ISO/IEC 27017 is unique in providing guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="09f52-120">它也會為雲端服務客戶提供有關他們應該對雲端服務提供者所預期的實務資訊。</span><span class="sxs-lookup"><span data-stu-id="09f52-120">It also provides cloud service customers with practical information on what they should expect from cloud service providers.</span></span> <span data-ttu-id="09f52-121">透過確保客戶了解在雲端中的共用責任，客戶可以直接從 ISO/IEC 27017 獲益。</span><span class="sxs-lookup"><span data-stu-id="09f52-121">Customers can benefit directly from ISO/IEC 27017 by ensuring they understand the shared responsibilities in the cloud.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="09f52-122">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="09f52-122">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="09f52-123">Azure、Azure Government 和 Azure 德國</span><span class="sxs-lookup"><span data-stu-id="09f52-123">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="09f52-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="09f52-124">Microsoft Cloud App Security</span></span>
- [<span data-ttu-id="09f52-125">Dynamics 365、Dynamics 365 和 Dynamics 365 德國</span><span class="sxs-lookup"><span data-stu-id="09f52-125">Dynamics 365, Dynamics 365, and Dynamics 365 Germany</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="09f52-126">Microsoft Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="09f52-126">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="09f52-127">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="09f52-127">Microsoft Graph</span></span>
- <span data-ttu-id="09f52-128">Microsoft Healthcare Bot</span><span class="sxs-lookup"><span data-stu-id="09f52-128">Microsoft Healthcare Bot</span></span>
- <span data-ttu-id="09f52-129">Intune</span><span class="sxs-lookup"><span data-stu-id="09f52-129">Intune</span></span>
- <span data-ttu-id="09f52-130">Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="09f52-130">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="09f52-131">Power Automate (先前為 Microsoft Flow) 雲端服務可作為獨立服務或包含在 Office 365 或 Dynamics 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="09f52-131">Power Automate (formerly Microsoft Flow) cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="09f52-132">Office 365、Office 365 美國政府、Office 365 美國政府國防版和 Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="09f52-132">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense, and Office 365 Germany</span></span>
- <span data-ttu-id="09f52-133">PowerApps 雲端服務，以獨立服務形式提供或包含在 Office 365 或 Dynamics 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="09f52-133">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="09f52-134">Power BI 雲端服務可作為獨立服務或包含在 Office 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="09f52-134">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="09f52-135">Power BI Embedded</span><span class="sxs-lookup"><span data-stu-id="09f52-135">Power BI Embedded</span></span>
- <span data-ttu-id="09f52-136">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="09f52-136">Microsoft Stream</span></span>
- <span data-ttu-id="09f52-137">請參閱 Office 365 中涵蓋服務的[詳細清單](https://go.microsoft.com/fwlink/p/?linkid=2077751)。</span><span class="sxs-lookup"><span data-stu-id="09f52-137">See a [detailed list](https://go.microsoft.com/fwlink/p/?linkid=2077751) of covered services in Office 365</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="09f52-138">稽核、報告和認證</span><span class="sxs-lookup"><span data-stu-id="09f52-138">Audits, reports, and certificates</span></span>

<span data-ttu-id="09f52-139">Microsoft 雲端服務會每年隨著 ISO/IEC 27001:2013 的認證程序，針對 ISO/IEC 27017:2015 工作條例規定進行一次稽核。</span><span class="sxs-lookup"><span data-stu-id="09f52-139">Microsoft cloud services are audited once a year for the ISO/IEC 27017:2015 code of practice as part of the certification process for ISO/IEC 27001:2013.</span></span>

- [<span data-ttu-id="09f52-140">Azure ISO 27017 認證</span><span class="sxs-lookup"><span data-stu-id="09f52-140">Azure ISO 27017 Certificate</span></span>](https://aka.ms/azureiso27017cert)
- [<span data-ttu-id="09f52-141">Azure ISO 27017 評定報告</span><span class="sxs-lookup"><span data-stu-id="09f52-141">Azure ISO 27017 Assessment report</span></span>](https://aka.ms/azureiso27017report)
- [<span data-ttu-id="09f52-142">Office 365：ISO 27001、27018 和 27017 稽核評估報告</span><span class="sxs-lookup"><span data-stu-id="09f52-142">Office 365: ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)

## <a name="frequently-asked-questions"></a><span data-ttu-id="09f52-143">常見問題集</span><span class="sxs-lookup"><span data-stu-id="09f52-143">Frequently asked questions</span></span>

<span data-ttu-id="09f52-144">標準的適用對象為何？</span><span class="sxs-lookup"><span data-stu-id="09f52-144">To whom does the standard apply?</span></span>

<span data-ttu-id="09f52-145">此工作條例規定可提供雲端服務提供者和雲端服務客戶的控制和實作指導方針。</span><span class="sxs-lookup"><span data-stu-id="09f52-145">This code of practice provides controls and implementation guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="09f52-146">它的結構格式類似於 ISO/IEC 27002:2013。</span><span class="sxs-lookup"><span data-stu-id="09f52-146">It is structured in a format similar to ISO/IEC 27002:2013.</span></span>

<span data-ttu-id="09f52-147">**可以在何處檢視 Microsoft 的 ISO/IEC 27017:2015 合規性資訊？**</span><span class="sxs-lookup"><span data-stu-id="09f52-147">**Where can I view Microsoft’s compliance information for ISO/IEC 27017:2015?**</span></span>

<span data-ttu-id="09f52-148">您可以下載適用於 Azure、Intune 和 Power BI 的 [ISO/IEC 27017:2015 認證](https://aka.ms/azureiso27017)。</span><span class="sxs-lookup"><span data-stu-id="09f52-148">You can download the [ISO/IEC 27017:2015 certificate](https://aka.ms/azureiso27017) for Azure, Intune, and Power BI.</span></span>

<span data-ttu-id="09f52-149">**我是否可以在組織的認證程序中使用 Microsoft 服務的 ISO/IEC 27017 合規性？**</span><span class="sxs-lookup"><span data-stu-id="09f52-149">**Can I use the ISO/IEC 27017 compliance of Microsoft services in my organization’s certification process?**</span></span>

<span data-ttu-id="09f52-150">是的。</span><span class="sxs-lookup"><span data-stu-id="09f52-150">Yes.</span></span> <span data-ttu-id="09f52-151">如果貴公司正在尋求用於在任何 Microsoft 範圍內企業雲端服務上所部署實作的認證，則可以在您的合規性評定中使用 Microsoft 的相關認證。</span><span class="sxs-lookup"><span data-stu-id="09f52-151">If your business is seeking certification for implementations deployed on any Microsoft in-scope enterprise cloud services, you can use Microsoft’s relevant certifications in your compliance assessment.</span></span> <span data-ttu-id="09f52-152">不過，您有責任確保評定者有參與評估合規性的實作，以及組織中的控制和程序。</span><span class="sxs-lookup"><span data-stu-id="09f52-152">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

<span data-ttu-id="09f52-153">**如何取得適用稽核報告的複本？**</span><span class="sxs-lookup"><span data-stu-id="09f52-153">**How can I get copies of the applicable audit reports?**</span></span>

<span data-ttu-id="09f52-154">[服務信任入口網站](https://aka.ms/stphelp)提供獨立的協力廠商稽核報告和其他相關文件。</span><span class="sxs-lookup"><span data-stu-id="09f52-154">The [Service Trust Portal](https://aka.ms/stphelp) provides independent, third-party audit reports and other related documentation.</span></span> <span data-ttu-id="09f52-155">您可以使用入口網站來下載並檢閱此文件，以獲得您自己的法規需求的協助。</span><span class="sxs-lookup"><span data-stu-id="09f52-155">You can use the portal to download and review this documentation for assistance with your own regulatory requirements.</span></span>

## <a name="resources"></a><span data-ttu-id="09f52-156">資源</span><span class="sxs-lookup"><span data-stu-id="09f52-156">Resources</span></span>

- [<span data-ttu-id="09f52-157">ISO/IEC 27017:2015 工作條例規定</span><span class="sxs-lookup"><span data-stu-id="09f52-157">ISO/IEC 27017:2015 code of practice</span></span>](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=43757)
- [<span data-ttu-id="09f52-158">Microsoft Online Services 條款</span><span class="sxs-lookup"><span data-stu-id="09f52-158">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="09f52-159">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="09f52-159">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
