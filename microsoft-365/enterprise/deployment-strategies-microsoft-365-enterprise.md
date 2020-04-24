---
title: Microsoft 365 企業版底層基礎結構部署策略
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解部署 Microsoft 365 企業版底層基礎結構階段的一些方法。
ms.openlocfilehash: 5eb4851a4c967baae268e04113b4e44023164db4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638149"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="e8a7e-103">Microsoft 365 企業版底層基礎結構部署策略</span><span class="sxs-lookup"><span data-stu-id="e8a7e-103">Microsoft 365 for enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="e8a7e-p101">您可以使用多種方法部署 Microsoft 365 企業版[底層基礎結構](deploy-foundation-infrastructure.md)的各個階段，並向使用者推廣其功能、軟體和服務。若要開始對這項工作進行專案管理 (可能龐大且複雜，取決於組織規模及現有基礎結構)，請考慮以下部署策略：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p101">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 for enterprise and roll out its capabilities, software, and services to your users. To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="e8a7e-106">序列部署</span><span class="sxs-lookup"><span data-stu-id="e8a7e-106">Serial deployment</span></span>
- <span data-ttu-id="e8a7e-107">具有非重疊使用者推出的平行部署</span><span class="sxs-lookup"><span data-stu-id="e8a7e-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="e8a7e-108">具有重疊使用者推出的平行部署</span><span class="sxs-lookup"><span data-stu-id="e8a7e-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="e8a7e-109">初期基礎結構和端對端設定的推出</span><span class="sxs-lookup"><span data-stu-id="e8a7e-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="e8a7e-110">使用這些策略了解如何管理整個專案，並更快速地實現 Microsoft 365 企業版的商業優勢。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 for enterprise.</span></span>

>[!Note]
><span data-ttu-id="e8a7e-p102">本文包含用於描述部署策略之一致方法的假設和簡化。這些部署策略是通用的，不限於任何特定的時間範圍，也不一定適用於所有組織和情況。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p102">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies. These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="e8a7e-113">典型企業組織的 IT 專案管理元素</span><span class="sxs-lookup"><span data-stu-id="e8a7e-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="e8a7e-p103">IT 基礎結構包含後端服務和向終端使用者推出的新增或改進的功能，或已安裝的軟體。IT 部門通常會以有條理的方式部署 IT 基礎結構的元素。成功部署 IT 基礎結構元素的方法包括：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p103">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users. IT departments typically deploy elements of an IT infrastructure in a methodical way. One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="e8a7e-117">試驗推出</span><span class="sxs-lookup"><span data-stu-id="e8a7e-117">A pilot rollout</span></span> 

  <span data-ttu-id="e8a7e-118">其中包含初始基礎結構設定，並推出給一組試驗使用者、進行測試，以及對基礎結構設定做後續修改。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="e8a7e-119">使用者推出</span><span class="sxs-lookup"><span data-stu-id="e8a7e-119">A user rollout</span></span>

  <span data-ttu-id="e8a7e-120">其中包含根據區域、部門、群組推出給貴組織的其他成員，或其他類型之設定或軟體的系統傳播。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="e8a7e-121">試驗推出的那一組使用者與使用者推出的使用者不同。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="e8a7e-122">本文使用以下圖形來描述這些定義：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-122">This article uses the following graphics to depict these definitions:</span></span> 

![描述試驗和使用者推出之定義的圖形](../media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="e8a7e-124">使用者推出的圖形陰影表示，透過使用結構化或有條理的方法 (例如群組、部門或區域)，在貴組織中從 0% 到 100% 的百分比。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-124">The shading for the user rollout graphic indicates the percentage across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="e8a7e-125">部署策略</span><span class="sxs-lookup"><span data-stu-id="e8a7e-125">Deployment strategies</span></span>

<span data-ttu-id="e8a7e-126">請考慮下列的部署策略：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-126">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="e8a7e-127">序列部署</span><span class="sxs-lookup"><span data-stu-id="e8a7e-127">Serial deployment</span></span>
- <span data-ttu-id="e8a7e-128">具有非重疊使用者推出的平行部署</span><span class="sxs-lookup"><span data-stu-id="e8a7e-128">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="e8a7e-129">具有重疊使用者推出的平行部署</span><span class="sxs-lookup"><span data-stu-id="e8a7e-129">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="e8a7e-130">初期基礎結構和端對端設定的推出</span><span class="sxs-lookup"><span data-stu-id="e8a7e-130">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="e8a7e-131">序列部署</span><span class="sxs-lookup"><span data-stu-id="e8a7e-131">Serial deployment</span></span>

<span data-ttu-id="e8a7e-p104">透過序列部署，您可以完整推行一個階段，讓該階段在進入下一個階段之前，能夠百分之百部署到所有使用者。以下是可能以這種方式部署的一些原因：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p104">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one. Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="e8a7e-134">風險降低</span><span class="sxs-lookup"><span data-stu-id="e8a7e-134">Risk mitigation</span></span>
- <span data-ttu-id="e8a7e-135">資源限制</span><span class="sxs-lookup"><span data-stu-id="e8a7e-135">Resourcing constraints</span></span>
- <span data-ttu-id="e8a7e-136">IT 部門資金週期</span><span class="sxs-lookup"><span data-stu-id="e8a7e-136">IT department funding cycles</span></span>
- <span data-ttu-id="e8a7e-137">IT 技術相依性</span><span class="sxs-lookup"><span data-stu-id="e8a7e-137">IT technology dependencies</span></span>
- <span data-ttu-id="e8a7e-138">業務變更管理和使用者阻力</span><span class="sxs-lookup"><span data-stu-id="e8a7e-138">Business change management and end-user resistance</span></span>

<span data-ttu-id="e8a7e-139">此甘特圖顯示了 Microsoft 365 企業版底層基礎結構階段 2-6 的簡化序列部署。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-139">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 for enterprise.</span></span>

![底層基礎結構階段 2-6 的序列部署](../media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="e8a7e-141">為了簡化討論和範例，請假設每個階段中的每個階段和部署區段都需要相同的時間。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-141">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="e8a7e-p105">階段 1：Microsoft 365 企業版底層基礎結構的網路為僅限 IT 部門使用的階段。使用者可從與 Microsoft 雲端資源之間最佳化連線中獲益，但不會因此而強加給他們。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p105">Phase 1: Networking of the Microsoft 365 for enterprise Foundation Infrastructure is an IT department-only phase. Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="e8a7e-144">以下是簡化的試驗使用者體驗，可做為範例：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-144">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="e8a7e-p106">我需要於 12 月使用智慧型手機啟用 MFA。(身分識別)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p106">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="e8a7e-p107">我於 3 月在 Windows 8.1 電腦上安裝了 Windows 10 企業版。(Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p107">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="e8a7e-149">我在 6 月時安裝了 Microsoft 365 Apps 企業版來取代 Office 2013。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-149">In June, I get Microsoft 365 Apps for enterprise installed, replacing Office 2013.</span></span> <span data-ttu-id="e8a7e-150">(Microsoft 365 Apps 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-150">(Microsoft 365 Apps for enterprise)</span></span>
- <span data-ttu-id="e8a7e-151">我於 9 月註冊裝置並套用了 App 和裝置原則。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-151">In September, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="e8a7e-152">(行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-152">(Mobile device management)</span></span>
- <span data-ttu-id="e8a7e-p110">我於 12 月安裝了 Azure 資訊保護用戶端，並接受有關如何將標籤套用至文件的訓練。(資訊保護)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p110">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="e8a7e-155">結果是 90 天的連續試驗推出頻率。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-155">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="e8a7e-156">以下是簡化的使用者體驗，可做為範例：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-156">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="e8a7e-p111">我需要於 1 月使用智慧型手機啟用 MFA。(身分識別)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p111">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="e8a7e-p112">我於 4 月在 Windows 8.1 電腦上安裝了 Windows 10 企業版。(Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p112">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="e8a7e-161">我在 7 月時安裝了 Microsoft 365 Apps 企業版來取代 Office 2013。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-161">In July, I get Microsoft 365 Apps for enterprise installed, replacing Office 2013.</span></span> <span data-ttu-id="e8a7e-162">(Microsoft 365 Apps 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-162">(Microsoft 365 Apps for enterprise)</span></span>
- <span data-ttu-id="e8a7e-163">我於 10 月註冊裝置並套用了 App 和裝置原則。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-163">In October, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="e8a7e-164">(行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-164">(Mobile device management)</span></span>
- <span data-ttu-id="e8a7e-p115">我於隔年 1 月安裝了 Azure 資訊保護用戶端，並接受有關如何將標籤套用至文件的訓練。(資訊保護)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p115">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="e8a7e-167">結果是 90 天的連續使用者推出頻率。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-167">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="e8a7e-168">此部署策略的缺點是，完整部署 Microsoft 365 企業版底層基礎結構可能需要很長時間。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-168">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 for enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="e8a7e-169">具有非重疊使用者推出的平行部署 (平行 1)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-169">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="e8a7e-p116">對於此部署策略，您可在目前階段之使用者推出的最後一部分啟動下一階段的試驗推出。以下是前一階段的使用者推出結束時，出現試驗推出的階段 2-6 部署。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p116">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase. Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

![具有非重疊使用者推出之階段 2-6 的平行部署](../media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="e8a7e-p117">最終的結果是，在下一個階段開始之前，目前階段的使用者推出會在貴組織內完成。非試驗推出的使用者不會同時處理多個階段的推出，但試驗推出會與使用者推同時進行。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p117">The end result is that user rollout for the current phase completes across your organization before the next one starts. Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="e8a7e-175">以下是簡化的試驗使用者體驗，可做為範例：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-175">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="e8a7e-p118">我需要於 12 月使用智慧型手機啟用 MFA。(身分識別)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p118">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="e8a7e-p119">我於 2 月在 Windows 8.1 電腦上安裝了 Windows 10 企業版。(Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p119">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="e8a7e-180">我在 4 月時安裝了 Microsoft 365 Apps 企業版來取代 Office 2013。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-180">In April, I get Microsoft 365 Apps for enterprise installed, replacing Office 2013.</span></span> <span data-ttu-id="e8a7e-181">(Microsoft 365 Apps 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-181">(Microsoft 365 Apps for enterprise)</span></span>
- <span data-ttu-id="e8a7e-182">我於 6 月註冊裝置並套用了 App 和裝置原則。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-182">In June, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="e8a7e-183">(行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-183">(Mobile device management)</span></span>
- <span data-ttu-id="e8a7e-p122">我於 8 月安裝了 Azure 資訊保護用戶端，並接受有關如何將標籤套用至文件的訓練。(資訊保護)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p122">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="e8a7e-186">結果是 60 天的連續試驗推出頻率。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-186">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="e8a7e-187">以下是簡化的使用者體驗，可做為範例：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-187">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="e8a7e-p123">我需要於 1 月使用智慧型手機啟用 MFA。(身分識別)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p123">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="e8a7e-p124">我於 3 月在 Windows 8.1 電腦上安裝了 Windows 10 企業版。(Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p124">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="e8a7e-192">我在 5 月時安裝了 Microsoft 365 Apps 企業版來取代 Office 2013。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-192">In May, I get Microsoft 365 Apps for enterprise installed, replacing Office 2013.</span></span> <span data-ttu-id="e8a7e-193">(Microsoft 365 Apps 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-193">(Microsoft 365 Apps for enterprise)</span></span>
- <span data-ttu-id="e8a7e-194">我於 7 月註冊裝置並套用了 App 和裝置原則。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-194">In July, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="e8a7e-195">(行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-195">(Mobile device management)</span></span>
- <span data-ttu-id="e8a7e-p127">我於 9 月安裝了 Azure 資訊保護用戶端，並接受有關如何將標籤套用至文件的訓練。(資訊保護)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p127">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="e8a7e-198">結果是 60 天的連續使用者推出頻率。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-198">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="e8a7e-199">此部署策略的優點是，可能會縮短完整部署 Microsoft 365 企業版底層基礎結構的時間，而無需讓 IT 部門和使用者同時處理多個推出。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-199">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 for enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="e8a7e-200">具有重疊使用者推出的平行部署 (平行 2)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-200">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="e8a7e-201">使用此部署策略，您將會：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-201">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="e8a7e-202">在目前階段之使用者推出的最後一部分啟動下一階段的試驗推出。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-202">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="e8a7e-203">使用者以沒有任何使用者正在同時處理多個階段推出的這類方式，在目前階段的使用者推出期間推出下一個階段。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-203">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time.</span></span> <span data-ttu-id="e8a7e-204">這會假設您會以使用地區、部門或其他群組的相同方式推出基礎結構的各個階段。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-204">This assumes that you are rolling out each phase of the foundation infrastructure in the same way, using regions, departments, or other groupings.</span></span>

<span data-ttu-id="e8a7e-205">以下是不同部署策略之間的簡化比較。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-205">Here is a simplified comparison between the different deployment strategies.</span></span>

![具有重疊使用者推出之階段 2-6 的平行部署](../media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="e8a7e-207">最後的結果是：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-207">The end result is that:</span></span>

- <span data-ttu-id="e8a7e-208">試驗推出從一個階段到下一階段，不必暫停。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-208">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="e8a7e-209">完成前一階段的使用者推出之前，就能開始下一階段的使用者推出，但沒有個別使用者一次推出多個階段。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-209">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="e8a7e-210">以下是簡化的試驗使用者體驗，可做為範例：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-210">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="e8a7e-p129">我需要於 12 月使用智慧型手機啟用 MFA。(身分識別)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p129">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="e8a7e-p130">我於 1 月在 Windows 8.1 電腦上安裝了 Windows 10 企業版。(Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p130">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="e8a7e-215">我在 2 月時安裝了 Microsoft 365 Apps 企業版來取代 Office 2013。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-215">In February, I get Microsoft 365 Apps for enterprise installed, replacing Office 2013.</span></span> <span data-ttu-id="e8a7e-216">(Microsoft 365 Apps 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-216">(Microsoft 365 Apps for enterprise)</span></span>
- <span data-ttu-id="e8a7e-217">我於 5 月註冊裝置並套用了 App 和裝置原則。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-217">In March, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="e8a7e-218">(行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-218">(Mobile device management)</span></span>
- <span data-ttu-id="e8a7e-p133">我於 4 月安裝了 Azure 資訊保護用戶端，並接受有關如何將標籤套用至文件的訓練。(資訊保護)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p133">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="e8a7e-221">結果是 30 天的連續試驗推出頻率。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-221">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="e8a7e-222">以下是簡化的使用者體驗，可做為範例：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-222">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="e8a7e-p134">我需要於 1 月使用智慧型手機啟用 MFA。(身分識別)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p134">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="e8a7e-p135">我於 2 月在 Windows 8.1 電腦上安裝了 Windows 10 企業版。(Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p135">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="e8a7e-227">我在 3 月時安裝了 Microsoft 365 Apps 企業版來取代 Office 2013。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-227">In March, I get Microsoft 365 Apps for enterprise installed, replacing Office 2013.</span></span> <span data-ttu-id="e8a7e-228">(Microsoft 365 Apps 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-228">(Microsoft 365 Apps for enterprise)</span></span>
- <span data-ttu-id="e8a7e-229">我於 4 月註冊裝置並套用了 App 和裝置原則。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-229">In April, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="e8a7e-230">(行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-230">(Mobile device management)</span></span>
- <span data-ttu-id="e8a7e-p138">我於 5 月安裝了 Azure 資訊保護用戶端，並接受有關如何將標籤套用至文件的訓練。(資訊保護)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p138">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="e8a7e-233">結果是 30 天的連續使用者推出頻率。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-233">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="e8a7e-234">此部署策略的優點是，它甚至可縮短完整部署 Microsoft 365 企業版底層基礎結構的時間，而不需使用者同時處理多個推出。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-234">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 for enterprise foundation infrastructure, still without having end-users deal with multiple rollouts the same time.</span></span> <span data-ttu-id="e8a7e-235">但是，使用者無法在連續階段之間休息。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-235">However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-the-end-to-end-configuration"></a><span data-ttu-id="e8a7e-236">初期基礎結構和端對端設定的推出</span><span class="sxs-lookup"><span data-stu-id="e8a7e-236">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="e8a7e-237">對於能夠將階段 2-6 壓縮為單一部署區段的小型組織，部署結果如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-237">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![初期基礎結構和端對端設定的推出](../media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="e8a7e-p140">IT 部門為階段 2-6 設定基礎結構，然後推出給試驗使用者，以檢查端對端的功能。例如，試驗使用者同時獲得下列功能：</span><span class="sxs-lookup"><span data-stu-id="e8a7e-p140">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality. For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="e8a7e-241">MFA 和其他身分識別功能 (身分識別)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-241">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="e8a7e-242">Windows 裝置上的 Windows 10 企業版 (Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-242">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="e8a7e-243">適用於 Office 套件的 Microsoft 365 Apps 企業版 (Microsoft 365 Apps 企業版)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-243">Microsoft 365 Apps for enterprise for the Office suite (Microsoft 365 Apps for enterprise)</span></span>
- <span data-ttu-id="e8a7e-244">App 和裝置原則 (行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-244">App and device policies (Mobile device management)</span></span>
- <span data-ttu-id="e8a7e-245">安裝 Azure 資訊保護用戶端，並對如何將標籤套用至文件進行訓練 (資訊保護)</span><span class="sxs-lookup"><span data-stu-id="e8a7e-245">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="e8a7e-246">試驗推出結束後，使用者推出將會開始，每個使用者在該推出中同時獲取所有功能。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-246">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="e8a7e-247">下一步</span><span class="sxs-lookup"><span data-stu-id="e8a7e-247">Next step</span></span>

<span data-ttu-id="e8a7e-248">使用[底層基礎結構](deploy-foundation-infrastructure.md)開始部署 Microsoft 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="e8a7e-248">Start your deployment of Microsoft 365 for enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
