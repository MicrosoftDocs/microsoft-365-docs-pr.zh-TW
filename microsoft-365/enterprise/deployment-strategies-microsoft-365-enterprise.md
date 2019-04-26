---
title: Microsoft 365 企業版底層基礎結構部署策略
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/23/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解部署 Microsoft 365 企業版底層基礎結構階段的一些方法。
ms.openlocfilehash: fb4cf301f1e450cd5db9b392c0ca2d8e3767242a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289540"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="b6919-103">Microsoft 365 企業版底層基礎結構部署策略</span><span class="sxs-lookup"><span data-stu-id="b6919-103">Microsoft 365 Enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="b6919-p101">您可以使用多種方法部署 Microsoft 365 企業版[底層基礎結構](deploy-foundation-infrastructure.md)的各個階段，並向使用者推廣其功能、軟體和服務。若要開始對這項工作進行專案管理 (可能龐大且複雜，取決於組織規模及現有基礎結構)，請考慮以下部署策略：</span><span class="sxs-lookup"><span data-stu-id="b6919-p101">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 Enterprise and roll out its capabilities, software, and services to your users. To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="b6919-106">序列部署</span><span class="sxs-lookup"><span data-stu-id="b6919-106">Serial deployment</span></span>
- <span data-ttu-id="b6919-107">具有非重疊使用者推出的平行部署</span><span class="sxs-lookup"><span data-stu-id="b6919-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="b6919-108">具有重疊使用者推出的平行部署</span><span class="sxs-lookup"><span data-stu-id="b6919-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="b6919-109">初期基礎結構和端對端設定的推出</span><span class="sxs-lookup"><span data-stu-id="b6919-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="b6919-110">使用這些策略了解如何管理整個專案，並更快速地實現 Microsoft 365 企業版的商業優勢。</span><span class="sxs-lookup"><span data-stu-id="b6919-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="b6919-p102">本文包含用於描述部署策略之一致方法的假設和簡化。這些部署策略是通用的，不限於任何特定的時間範圍，也不一定適用於所有組織和情況。</span><span class="sxs-lookup"><span data-stu-id="b6919-p102">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies. These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="b6919-113">典型企業組織的 IT 專案管理元素</span><span class="sxs-lookup"><span data-stu-id="b6919-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="b6919-p103">IT 基礎結構包含後端服務和向終端使用者推出的新增或改進的功能，或已安裝的軟體。IT 部門通常會以有條理的方式部署 IT 基礎結構的元素。成功部署 IT 基礎結構元素的方法包括：</span><span class="sxs-lookup"><span data-stu-id="b6919-p103">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users. IT departments typically deploy elements of an IT infrastructure in a methodical way. One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="b6919-117">試驗推出</span><span class="sxs-lookup"><span data-stu-id="b6919-117">A pilot rollout</span></span> 

  <span data-ttu-id="b6919-118">其中包含初始基礎結構設定，並推出給一組試驗使用者、進行測試，以及對基礎結構設定做後續修改。</span><span class="sxs-lookup"><span data-stu-id="b6919-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="b6919-119">使用者推出</span><span class="sxs-lookup"><span data-stu-id="b6919-119">A user rollout</span></span>

  <span data-ttu-id="b6919-120">其中包含根據區域、部門、群組推出給貴組織的其他成員，或其他類型之設定或軟體的系統傳播。</span><span class="sxs-lookup"><span data-stu-id="b6919-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="b6919-121">試驗推出的那一組使用者與使用者推出的使用者不同。</span><span class="sxs-lookup"><span data-stu-id="b6919-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="b6919-122">本文使用以下圖形來描述這些定義：</span><span class="sxs-lookup"><span data-stu-id="b6919-122">This article uses the following graphics to depict these definitions:</span></span> 

![](./media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="b6919-123">使用者推出的圖形陰影表示，透過使用結構化或有條理的方法 (例如群組、部門或區域)，在貴組織中從 0% 到 100% 的百分比。</span><span class="sxs-lookup"><span data-stu-id="b6919-123">The shading for the user rollout graphic indicates the percentage across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="b6919-124">部署策略</span><span class="sxs-lookup"><span data-stu-id="b6919-124">Deployment strategies</span></span>

<span data-ttu-id="b6919-125">請考慮下列的部署策略：</span><span class="sxs-lookup"><span data-stu-id="b6919-125">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="b6919-126">序列部署</span><span class="sxs-lookup"><span data-stu-id="b6919-126">Serial deployment</span></span>
- <span data-ttu-id="b6919-127">具有非重疊使用者推出的平行部署</span><span class="sxs-lookup"><span data-stu-id="b6919-127">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="b6919-128">具有重疊使用者推出的平行部署</span><span class="sxs-lookup"><span data-stu-id="b6919-128">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="b6919-129">初期基礎結構和端對端設定的推出</span><span class="sxs-lookup"><span data-stu-id="b6919-129">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="b6919-130">序列部署</span><span class="sxs-lookup"><span data-stu-id="b6919-130">Serial deployment</span></span>

<span data-ttu-id="b6919-p104">透過序列部署，您可以完整推行一個階段，讓該階段在進入下一個階段之前，能夠百分之百部署到所有使用者。以下是可能以這種方式部署的一些原因：</span><span class="sxs-lookup"><span data-stu-id="b6919-p104">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one. Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="b6919-133">風險降低</span><span class="sxs-lookup"><span data-stu-id="b6919-133">Risk mitigation</span></span>
- <span data-ttu-id="b6919-134">資源限制</span><span class="sxs-lookup"><span data-stu-id="b6919-134">Resourcing constraints</span></span>
- <span data-ttu-id="b6919-135">IT 部門資金週期</span><span class="sxs-lookup"><span data-stu-id="b6919-135">IT department funding cycles</span></span>
- <span data-ttu-id="b6919-136">IT 技術相依性</span><span class="sxs-lookup"><span data-stu-id="b6919-136">IT technology dependencies</span></span>
- <span data-ttu-id="b6919-137">業務變更管理和使用者阻力</span><span class="sxs-lookup"><span data-stu-id="b6919-137">Business change management and end-user resistance</span></span>

<span data-ttu-id="b6919-138">此甘特圖顯示了 Microsoft 365 企業版底層基礎結構階段 2-6 的簡化序列部署。</span><span class="sxs-lookup"><span data-stu-id="b6919-138">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 Enterprise.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="b6919-139">為了簡化討論和範例，請假設每個階段中的每個階段和部署區段都需要相同的時間。</span><span class="sxs-lookup"><span data-stu-id="b6919-139">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="b6919-p105">階段 1：Microsoft 365 企業版底層基礎結構的網路為僅限 IT 部門使用的階段。使用者可從與 Microsoft 雲端資源之間最佳化連線中獲益，但不會因此而強加給他們。</span><span class="sxs-lookup"><span data-stu-id="b6919-p105">Phase 1: Networking of the Microsoft 365 Enterprise Foundation Infrastructure is an IT department-only phase. Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="b6919-142">試驗使用者體驗的簡化範例：</span><span class="sxs-lookup"><span data-stu-id="b6919-142">Simplified example pilot user experience:</span></span>

- <span data-ttu-id="b6919-p106">我需要於 12 月使用智慧型手機啟用 MFA。(身分識別)</span><span class="sxs-lookup"><span data-stu-id="b6919-p106">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="b6919-145">我於 3 月在 Windows 8.1 電腦上安裝了 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="b6919-145">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span> <span data-ttu-id="b6919-146">(Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="b6919-146">Windows 10 Enterprise</span></span>
- <span data-ttu-id="b6919-p108">我於 6 月安裝了 Office 365 專業增強版，取代原本的 Office 2013。(Office 365 專業增強版)</span><span class="sxs-lookup"><span data-stu-id="b6919-p108">In June, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="b6919-p109">我於 9 月取得裝置註冊和 App，並套用條件式存取原則。(行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="b6919-p109">In September, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="b6919-p110">我於 12 月安裝了 Azure 資訊保護用戶端，並接受有關如何將標籤套用至文件的訓練。(資訊保護)</span><span class="sxs-lookup"><span data-stu-id="b6919-p110">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="b6919-153">結果是 90 天的連續試驗推出頻率。</span><span class="sxs-lookup"><span data-stu-id="b6919-153">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="b6919-154">使用者體驗的簡化範例：</span><span class="sxs-lookup"><span data-stu-id="b6919-154">Simplified example end-user experience:</span></span>

- <span data-ttu-id="b6919-p111">我需要於 1 月使用智慧型手機啟用 MFA。(身分識別)</span><span class="sxs-lookup"><span data-stu-id="b6919-p111">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="b6919-p112">我於 4 月在 Windows 8.1 電腦上安裝了 Windows 10 企業版。(Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="b6919-p112">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="b6919-p113">我於 7 月安裝了 Office 365 專業增強版，取代原本的 Office 2013。(Office 365 專業增強版)</span><span class="sxs-lookup"><span data-stu-id="b6919-p113">In July, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="b6919-p114">我於 10 月取得裝置註冊和 App，並套用條件式存取原則。(行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="b6919-p114">In October, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="b6919-p115">我於隔年 1 月安裝了 Azure 資訊保護用戶端，並接受有關如何將標籤套用至文件的訓練。(資訊保護)</span><span class="sxs-lookup"><span data-stu-id="b6919-p115">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="b6919-165">結果是 90 天的連續使用者推出頻率。</span><span class="sxs-lookup"><span data-stu-id="b6919-165">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="b6919-166">此部署策略的缺點是，完整部署 Microsoft 365 企業版底層基礎結構可能需要很長時間。</span><span class="sxs-lookup"><span data-stu-id="b6919-166">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 Enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="b6919-167">具有非重疊使用者推出的平行部署 (平行 1)</span><span class="sxs-lookup"><span data-stu-id="b6919-167">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="b6919-p116">對於此部署策略，您可在目前階段之使用者推出的最後一部分啟動下一階段的試驗推出。以下是前一階段的使用者推出結束時，出現試驗推出的階段 2-6 部署。</span><span class="sxs-lookup"><span data-stu-id="b6919-p116">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase. Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

<span data-ttu-id="b6919-170">以下是平行和序列部署策略之間的簡化比較。</span><span class="sxs-lookup"><span data-stu-id="b6919-170">Here is a simplified comparison between parallel and serial deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="b6919-p117">最終的結果是，在下一個階段開始之前，目前階段的使用者推出會在貴組織內完成。非試驗推出的使用者不會同時處理多個階段的推出，但試驗推出會與使用者推同時進行。</span><span class="sxs-lookup"><span data-stu-id="b6919-p117">The end result is that user rollout for the current phase completes across your organization before the next one starts. Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="b6919-173">試驗使用者體驗的簡化範例：</span><span class="sxs-lookup"><span data-stu-id="b6919-173">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="b6919-p118">我需要於 12 月使用智慧型手機啟用 MFA。(身分識別)</span><span class="sxs-lookup"><span data-stu-id="b6919-p118">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="b6919-176">我於 2 月在 Windows 8.1 電腦上安裝了 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="b6919-176">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span> <span data-ttu-id="b6919-177">(Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="b6919-177">Windows 10 Enterprise</span></span>
- <span data-ttu-id="b6919-p120">我於 4 月安裝了 Office 365 專業增強版，取代原本的 Office 2013。(Office 365 專業增強版)</span><span class="sxs-lookup"><span data-stu-id="b6919-p120">In April, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="b6919-p121">我於 6 月取得裝置註冊和 App，並套用條件式存取原則。(行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="b6919-p121">In June, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="b6919-p122">我於 8 月安裝了 Azure 資訊保護用戶端，並接受有關如何將標籤套用至文件的訓練。(資訊保護)</span><span class="sxs-lookup"><span data-stu-id="b6919-p122">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="b6919-184">結果是 60 天的連續試驗推出頻率。</span><span class="sxs-lookup"><span data-stu-id="b6919-184">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="b6919-185">使用者體驗的簡化範例：</span><span class="sxs-lookup"><span data-stu-id="b6919-185">Simplified example end-user experience:</span></span>

- <span data-ttu-id="b6919-p123">我需要於 1 月使用智慧型手機啟用 MFA。(身分識別)</span><span class="sxs-lookup"><span data-stu-id="b6919-p123">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="b6919-p124">我於 3 月在 Windows 8.1 電腦上安裝了 Windows 10 企業版。(Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="b6919-p124">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="b6919-p125">我於 5 月安裝了 Office 365 專業增強版，取代原本的 Office 2013。(Office 365 專業增強版)</span><span class="sxs-lookup"><span data-stu-id="b6919-p125">In May, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="b6919-p126">我於 7 月取得裝置註冊和 App，並套用條件式存取原則。(行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="b6919-p126">In July, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="b6919-p127">我於 9 月安裝了 Azure 資訊保護用戶端，並接受有關如何將標籤套用至文件的訓練。(資訊保護)</span><span class="sxs-lookup"><span data-stu-id="b6919-p127">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="b6919-196">結果是 60 天的連續使用者推出頻率。</span><span class="sxs-lookup"><span data-stu-id="b6919-196">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="b6919-197">此部署策略的優點是，可能會縮短完整部署 Microsoft 365 企業版底層基礎結構的時間，而無需讓 IT 部門和使用者同時處理多個推出。</span><span class="sxs-lookup"><span data-stu-id="b6919-197">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="b6919-198">具有重疊使用者推出的平行部署 (平行 2)</span><span class="sxs-lookup"><span data-stu-id="b6919-198">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="b6919-199">使用此部署策略，您將會：</span><span class="sxs-lookup"><span data-stu-id="b6919-199">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="b6919-200">在目前階段之使用者推出的最後一部分啟動下一階段的試驗推出。</span><span class="sxs-lookup"><span data-stu-id="b6919-200">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="b6919-p128">在目前階段的使用者推出期間，使用者推出下一階段的方式是，沒有使用者同時處理多個階段的推出。這假設您以相同方式透過區域、部門或其他方法推出底層基礎結構的每一階段。</span><span class="sxs-lookup"><span data-stu-id="b6919-p128">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time. This assumes that you are rolling out each phase of the foundation infrastructure in the same way, via regions, departments, or other.</span></span>

<span data-ttu-id="b6919-203">以下是不同部署策略之間的簡化比較。</span><span class="sxs-lookup"><span data-stu-id="b6919-203">Here is a simplified comparison between the different deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="b6919-204">最後的結果是：</span><span class="sxs-lookup"><span data-stu-id="b6919-204">The end result is that:</span></span>

- <span data-ttu-id="b6919-205">試驗推出從一個階段到下一階段，不必暫停。</span><span class="sxs-lookup"><span data-stu-id="b6919-205">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="b6919-206">完成前一階段的使用者推出之前，就能開始下一階段的使用者推出，但沒有個別使用者一次推出多個階段。</span><span class="sxs-lookup"><span data-stu-id="b6919-206">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="b6919-207">試驗使用者體驗的簡化範例：</span><span class="sxs-lookup"><span data-stu-id="b6919-207">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="b6919-p129">我需要於 12 月使用智慧型手機啟用 MFA。(身分識別)</span><span class="sxs-lookup"><span data-stu-id="b6919-p129">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="b6919-p130">我於 1 月在 Windows 8.1 電腦上安裝了 Windows 10 企業版。(Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="b6919-p130">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="b6919-p131">我於 2 月安裝了 Office 365 專業增強版，取代原本的 Office 2013。(Office 365 專業增強版)</span><span class="sxs-lookup"><span data-stu-id="b6919-p131">In February, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="b6919-p132">我於 3 月取得裝置註冊和 App，並套用條件式存取原則。(行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="b6919-p132">In March, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="b6919-p133">我於 4 月安裝了 Azure 資訊保護用戶端，並接受有關如何將標籤套用至文件的訓練。(資訊保護)</span><span class="sxs-lookup"><span data-stu-id="b6919-p133">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="b6919-218">結果是 30 天的連續試驗推出頻率。</span><span class="sxs-lookup"><span data-stu-id="b6919-218">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="b6919-219">使用者體驗的簡化範例：</span><span class="sxs-lookup"><span data-stu-id="b6919-219">Simplified example end-user experience:</span></span>

- <span data-ttu-id="b6919-p134">我需要於 1 月使用智慧型手機啟用 MFA。(身分識別)</span><span class="sxs-lookup"><span data-stu-id="b6919-p134">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="b6919-p135">我於 2 月在 Windows 8.1 電腦上安裝了 Windows 10 企業版。(Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="b6919-p135">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="b6919-p136">我於 3 月安裝了 Office 365 專業增強版，取代原本的 Office 2013。(Office 365 專業增強版)</span><span class="sxs-lookup"><span data-stu-id="b6919-p136">In March, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="b6919-p137">我於 4 月取得裝置註冊和 App，並套用條件式存取原則。(行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="b6919-p137">In April, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="b6919-p138">我於 5 月安裝了 Azure 資訊保護用戶端，並接受有關如何將標籤套用至文件的訓練。(資訊保護)</span><span class="sxs-lookup"><span data-stu-id="b6919-p138">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="b6919-230">結果是 30 天的連續使用者推出頻率。</span><span class="sxs-lookup"><span data-stu-id="b6919-230">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="b6919-p139">此部署策略的優點是，可能會縮短完整部署 Microsoft 365 企業版底層基礎結構的時間，而無需讓個別使用者同時處理多個推出。但是，使用者無法在連續階段之間休息。</span><span class="sxs-lookup"><span data-stu-id="b6919-p139">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, still without having individual users deal with multiple rollouts the same time. However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-end-to-end-configuration"></a><span data-ttu-id="b6919-233">初期基礎結構和端對端設定的推出</span><span class="sxs-lookup"><span data-stu-id="b6919-233">Up-front infrastructure and rollout of end-to-end configuration</span></span>

<span data-ttu-id="b6919-234">對於能夠將階段 2-6 壓縮為單一部署區段的小型組織，部署結果如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6919-234">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![](./media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="b6919-p140">IT 部門為階段 2-6 設定基礎結構，然後推出給試驗使用者，以檢查端對端的功能。例如，試驗使用者同時獲得下列功能：</span><span class="sxs-lookup"><span data-stu-id="b6919-p140">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality. For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="b6919-237">MFA 和其他身分識別功能 (身分識別)</span><span class="sxs-lookup"><span data-stu-id="b6919-237">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="b6919-238">Windows 裝置上的 Windows 10 企業版 (Windows 10 企業版)</span><span class="sxs-lookup"><span data-stu-id="b6919-238">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="b6919-239">Office 365 專業增強版的 Office 套件 (Office 365 專業增強版)</span><span class="sxs-lookup"><span data-stu-id="b6919-239">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="b6919-240">App 和條件式存取原則 (行動裝置管理)</span><span class="sxs-lookup"><span data-stu-id="b6919-240">App and conditional access policies (Mobile device management)</span></span>
- <span data-ttu-id="b6919-241">安裝 Azure 資訊保護用戶端，並對如何將標籤套用至文件進行訓練 (資訊保護)</span><span class="sxs-lookup"><span data-stu-id="b6919-241">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="b6919-242">試驗推出結束後，使用者推出將會開始，每個使用者在該推出中同時獲取所有功能。</span><span class="sxs-lookup"><span data-stu-id="b6919-242">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="b6919-243">下一步</span><span class="sxs-lookup"><span data-stu-id="b6919-243">Next step</span></span>

<span data-ttu-id="b6919-244">使用[底層基礎結構](deploy-foundation-infrastructure.md)部署 Microsoft 365 企業版。</span><span class="sxs-lookup"><span data-stu-id="b6919-244">Start your deployment of Microsoft 365 Enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
