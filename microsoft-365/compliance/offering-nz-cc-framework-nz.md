---
title: 紐西蘭政府雲端運算安全性及隱私權考量
description: Microsoft NZ 位址發佈紐西蘭雲端運算架構中的問題。
keywords: Microsoft 365, compliance, offerings , 合規性, 方案
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: da5fbef7ed9ceb136f276e2d6baab0c94bba3c22
ms.sourcegitcommit: 82baed362528fed30e9e09c6a4a37c07be2f138d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40959532"
---
# <a name="new-zealand-government-cloud-computing-security-and-privacy-considerations"></a><span data-ttu-id="867fa-104">紐西蘭政府雲端運算安全性及隱私權考量</span><span class="sxs-lookup"><span data-stu-id="867fa-104">New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

## <a name="new-zealand-government-cloud-computing-security-and-privacy-overview"></a><span data-ttu-id="867fa-105">紐西蘭政府雲端運算安全性和隱私權的概觀</span><span class="sxs-lookup"><span data-stu-id="867fa-105">New Zealand Government Cloud Computing Security and Privacy overview</span></span>

<span data-ttu-id="867fa-106">在 2015 年 10 月紐西蘭政府背書 reaffirmed 其 「 先雲端 」 原則使用跨越多個公共部門資訊技術的修訂的全部政府 ICT 策略。</span><span class="sxs-lookup"><span data-stu-id="867fa-106">In October 2015, the New Zealand Government endorsed a revised all-government ICT strategy that reaffirmed its “cloud first” policy on using information technology across the public sector.</span></span> <span data-ttu-id="867fa-107">修訂的策略會保留 「 雲端運算風險和保證架構 」 開發並實作授權的 NZ 政府主要資訊長 (GCIO) 之下。</span><span class="sxs-lookup"><span data-stu-id="867fa-107">The revised strategy retains the “Cloud Computing Risk and Assurance Framework” that was developed and implemented under the authority of the NZ Government Chief Information Officer (GCIO).</span></span>

<span data-ttu-id="867fa-108">政府預期成配合此架構時評估和採用雲端服務的所有紐西蘭 State Service 行政機關。</span><span class="sxs-lookup"><span data-stu-id="867fa-108">The government expects all New Zealand State Service agencies to work within this framework when assessing and adopting cloud services.</span></span> <span data-ttu-id="867fa-109">< 的雲端運算需求 > 概述行政機關採用以及概觀政府雲端原則的歷程記錄的雲端服務時必須執行的動作。</span><span class="sxs-lookup"><span data-stu-id="867fa-109">“Requirements for Cloud Computing” outlines what agencies must do when adopting cloud services along with an overview of the history of the government’s cloud policy.</span></span>

<span data-ttu-id="867fa-110">若要協助 NZ 政府機構中舉行一致且健全到期盡職調查潛在的雲端解決方案，GCIO 已發佈 」 雲端運算:: 資訊安全性及隱私權考量 」 (「 雲端運算 ISPC 」)。</span><span class="sxs-lookup"><span data-stu-id="867fa-110">To assist NZ government agencies in conducting consistent and robust due diligence on potential cloud solutions, the GCIO has published “Cloud Computing: Information Security and Privacy Considerations” (the “Cloud Computing ISPC”).</span></span> <span data-ttu-id="867fa-111">本文件包含超過 100 個著重於資料主權、 隱私權、 安全性、 控管、 機密性、 資料完整性、 可用性和事件回應及管理的問題。</span><span class="sxs-lookup"><span data-stu-id="867fa-111">This document contains more than 100 questions focused on data sovereignty, privacy, security, governance, confidentiality, data integrity, availability, and incident response and management.</span></span> <span data-ttu-id="867fa-112">請注意 「 雲端運算 IPSC 」 不會定義針對哪些雲端服務提供者必須證明正式符合 NZ 政府標準。</span><span class="sxs-lookup"><span data-stu-id="867fa-112">Note that “Cloud Computing IPSC” does not define a NZ government standard against which cloud service providers must demonstrate formal compliance.</span></span> <span data-ttu-id="867fa-113">許多文件中設定的問題，不過，指向聚集了解如何雲端服務提供者遵守各種相關的標準的重要性。</span><span class="sxs-lookup"><span data-stu-id="867fa-113">Many of the questions set out in the document do, however, point toward the importance of understanding how cloud service providers comply with a wide array of relevant standards.</span></span>

<span data-ttu-id="867fa-114">Microsoft 和紐西蘭政府雲端運算安全性及隱私權考量</span><span class="sxs-lookup"><span data-stu-id="867fa-114">Microsoft and New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

<span data-ttu-id="867fa-115">若要協助進行其分析和評估，Microsoft 企業雲端服務的行政機關，Microsoft 紐西蘭已產生一系列的文件顯示其企業雲端服務如何處理中 」 雲端運算 ISPC 」 所設定的問題將它們連結到 Microsoft 雲端服務用來對照認證的標準。</span><span class="sxs-lookup"><span data-stu-id="867fa-115">To help agencies undertake their analysis and evaluation of Microsoft enterprise cloud services, Microsoft New Zealand has produced a series of documents showing how its enterprise cloud services address the questions set out in the “Cloud Computing ISPC” by linking them to the standards against which Microsoft cloud services are certified.</span></span> <span data-ttu-id="867fa-116">這些認證是核心 Microsoft 如何確保公用和私人磁區客戶，其雲端服務會設計、 建置基礎，和 21vianet 運作的有效減輕隱私權和安全性風險並處理資料主權考量。</span><span class="sxs-lookup"><span data-stu-id="867fa-116">These certifications are central to how Microsoft assures both public and private sector customers that its cloud services are designed, built, and operated to effectively mitigate privacy and security risks and address data sovereignty concerns.</span></span>

<span data-ttu-id="867fa-117">了解 NZ CC 架構在 Microsoft 雲端的優勢：[下載 NZ CC framework 背景資料](https://aka.ms/nzcc-framework-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="867fa-117">Learn about the benefits of NZ CC Framework on the Microsoft Cloud: [Download the NZ CC framework backgrounder](https://aka.ms/nzcc-framework-backgrounder)</span></span>

<span data-ttu-id="867fa-118">了解如何開始加速 NZ CC Framework 部署與我們的 Azure 安全性與合規性藍圖：[下載 Azure 回應 NZ CC 架構](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)</span><span class="sxs-lookup"><span data-stu-id="867fa-118">Learn how to accelerate your NZ CC Framework deployment with our Azure Security and Compliance Blueprint: [Download Azure response to the NZ CC Framework](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="867fa-119">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="867fa-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="867fa-120">Azure 和 Azure Government</span><span class="sxs-lookup"><span data-stu-id="867fa-120">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="867fa-121">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="867fa-121">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="867fa-122">Intune</span><span class="sxs-lookup"><span data-stu-id="867fa-122">Intune</span></span>
- <span data-ttu-id="867fa-123">Power BI 雲端服務可作為獨立服務或包含在 Office 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="867fa-123">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- [<span data-ttu-id="867fa-124">Office 365</span><span class="sxs-lookup"><span data-stu-id="867fa-124">Office 365</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="867fa-125">Exchange Online、 SharePoint Online 和商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="867fa-125">Exchange Online, SharePoint Online, and Skype for Business Online.</span></span> <span data-ttu-id="867fa-126">Microsoft NZ 具有合作 GCIO 小組，以開發整合 Exchange Online 的參考架構和 SEEMail 所述，本白皮書[Office 365: SEEMail 整合和參考架構](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf)</span><span class="sxs-lookup"><span data-stu-id="867fa-126">Microsoft NZ has worked with the GCIO team to develop a reference architecture for integrating Exchange Online and SEEMail described in the white paper [Office 365: SEEMail Integration and Reference Architecture](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="867fa-127">常見問題集</span><span class="sxs-lookup"><span data-stu-id="867fa-127">Frequently asked questions</span></span>

<span data-ttu-id="867fa-128">**對象架構適？**</span><span class="sxs-lookup"><span data-stu-id="867fa-128">**To whom does the framework apply?**</span></span>

<span data-ttu-id="867fa-129">落在此 GCIO 強制的組織 — 公開及非公用服務部門、 20 學狀況版和七個皇冠實體 — 當他們在決定在使用雲端服務時必須遵守架構。</span><span class="sxs-lookup"><span data-stu-id="867fa-129">Organizations that fall under the GCIO mandate — the public and non-public service departments, the 20 district health boards, and seven Crown entities — must adhere to the framework when they are deciding on the use of a cloud service.</span></span>

<span data-ttu-id="867fa-130">**我機構可以在我們 ICT 系統的認證程序中使用此架構的 Microsoft 的回覆嗎？**</span><span class="sxs-lookup"><span data-stu-id="867fa-130">**Can my agency use Microsoft’s responses to this framework in the certification process of our ICT systems?**</span></span>

<span data-ttu-id="867fa-131">如果您 agency，才能進行憑證和 」 資格鑑定的[紐西蘭資訊安全性手動](https://go.microsoft.com/fwlink/p/?linkid=2099496)其 ICT 系統，然後您就可以使用這些回應您分析的一部分。</span><span class="sxs-lookup"><span data-stu-id="867fa-131">If your agency is required to undertake certification and accreditation of its ICT system under the [New Zealand Information Security Manual](https://go.microsoft.com/fwlink/p/?linkid=2099496), then you can use these responses as part of your analysis.</span></span>

## <a name="resources"></a><span data-ttu-id="867fa-132">資源</span><span class="sxs-lookup"><span data-stu-id="867fa-132">Resources</span></span>

- [<span data-ttu-id="867fa-133">近岸託管的辦公室生產力服務的安全性需求： Office 365 的符合性聲明指南</span><span class="sxs-lookup"><span data-stu-id="867fa-133">Security requirements for offshore hosted Office productivity services: conformance guide for Office 365</span></span>](https://aka.ms/o365-gcio-conformance-guidance)
- [<span data-ttu-id="867fa-134">Microsoft Azure 合規性內容中的紐西蘭安全性及隱私權需求</span><span class="sxs-lookup"><span data-stu-id="867fa-134">Microsoft Azure compliance in the context of New Zealand security and privacy requirements</span></span>](https://aka.ms/azurecompliancenewzealand)
- [<span data-ttu-id="867fa-135">NZ 政府 ICT 策略 2015</span><span class="sxs-lookup"><span data-stu-id="867fa-135">NZ Government ICT Strategy 2015</span></span>](https://www.ict.govt.nz/strategy-and-action-plan/strategy/)
- [<span data-ttu-id="867fa-136">NZ 政府需求雲端運算</span><span class="sxs-lookup"><span data-stu-id="867fa-136">NZ Government requirements for cloud computing</span></span>](https://aka.ms/NZ-Cloud-Requirements)
- [<span data-ttu-id="867fa-137">雲端運算： 資訊安全性及隱私權考量 (ISPC)</span><span class="sxs-lookup"><span data-stu-id="867fa-137">Cloud Computing: Information Security and Privacy Considerations (ISPC)</span></span>](https://www.digital.govt.nz/standards-and-guidance/technology-and-architecture/cloud-services/)
- [<span data-ttu-id="867fa-138">Microsoft Online Services 條款</span><span class="sxs-lookup"><span data-stu-id="867fa-138">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- <span data-ttu-id="867fa-139">[Office 365: SEEMail 整合和參考架構](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf)（其他 Microsoft NZ 指導雲端服務採用）</span><span class="sxs-lookup"><span data-stu-id="867fa-139">[Office 365: SEEMail Integration and Reference Architecture](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf) (additional Microsoft NZ guidance on cloud service adoption)</span></span>
- [<span data-ttu-id="867fa-140">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="867fa-140">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="microsoft-responses-to-cloud-computing-ipsc"></a><span data-ttu-id="867fa-141">「 雲端運算 IPSC 」 的 Microsoft 回覆</span><span class="sxs-lookup"><span data-stu-id="867fa-141">Microsoft responses to “Cloud Computing IPSC”</span></span>

- [<span data-ttu-id="867fa-142">Azure</span><span class="sxs-lookup"><span data-stu-id="867fa-142">Azure</span></span>](https://aka.ms/Azure-NZ-response)
- [<span data-ttu-id="867fa-143">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="867fa-143">Dynamics 365</span></span>](https://aka.ms/d365-nz-response)
- [<span data-ttu-id="867fa-144">Intune</span><span class="sxs-lookup"><span data-stu-id="867fa-144">Intune</span></span>](https://aka.ms/Intune-NZ-response)
- [<span data-ttu-id="867fa-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="867fa-145">Office 365</span></span>](https://aka.ms/O365-NZ-Response)
- [<span data-ttu-id="867fa-146">Power BI</span><span class="sxs-lookup"><span data-stu-id="867fa-146">Power BI</span></span>](https://download.microsoft.com/download/5/1/7/51726B9B-2E76-49C4-9D4F-A36BF025CB93/Response-to-GCIO-105-questions-Power-BI.pdf)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="867fa-147">下載方案背景資料</span><span class="sxs-lookup"><span data-stu-id="867fa-147">Download the offering backgrounder</span></span>

<span data-ttu-id="867fa-148">是否需要此方案的背景資料文件？</span><span class="sxs-lookup"><span data-stu-id="867fa-148">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="867fa-149">下載 [PDF](https://download.microsoft.com/download/6/6/4/664E4B6F-15C6-421E-8F74-3FA468587A47/NZ_CC_Compliance_Backgrounder.pdf)。</span><span class="sxs-lookup"><span data-stu-id="867fa-149">Download the [PDF](https://download.microsoft.com/download/6/6/4/664E4B6F-15C6-421E-8F74-3FA468587A47/NZ_CC_Compliance_Backgrounder.pdf).</span></span>
