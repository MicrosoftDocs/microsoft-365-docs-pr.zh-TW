---
title: 執行試驗 Microsoft 威脅防護專案
description: 在生產環境中執行試驗 Microsoft 威脅防護專案，以有效判斷 Microsoft 威脅防護 (MTP) 的優點和採用方式。
keywords: Microsoft 威脅防護試驗，執行試驗 Microsoft 威脅防護專案，評估 Microsoft 威脅防護中的實際執行、Microsoft 威脅防護試驗專案、網路安全性、高級持續性威脅、企業安全性、裝置、裝置、身分識別、使用者、資料、應用程式、事件、自動化調查和修正，以及高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 88d92558d86e0aa2e90ef04d88a3cd4676386f15
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195624"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="2bc66-104">執行試驗 Microsoft 威脅防護專案</span><span class="sxs-lookup"><span data-stu-id="2bc66-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2bc66-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2bc66-105">**Applies to:**</span></span>
- <span data-ttu-id="2bc66-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="2bc66-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2bc66-107">若要有效判斷 Microsoft 威脅防護 (MTP) 的優點和採用方式，您可以執行試驗專案。</span><span class="sxs-lookup"><span data-stu-id="2bc66-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="2bc66-108">在實際執行環境中啟用 Microsoft 威脅防護，並以定義的使用案例開始之前，最好先進行規劃，以判斷必須在此試驗專案中完成的工作，以及成功的準則。</span><span class="sxs-lookup"><span data-stu-id="2bc66-108">Before enabling Microsoft Threat Protection in your production environment and starting with defined use cases, it is best to go through a planning process to determine the tasks that must be accomplished in this pilot project, and the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="2bc66-109">如何使用本次試驗行動手冊</span><span class="sxs-lookup"><span data-stu-id="2bc66-109">How to use this pilot playbook</span></span>

<span data-ttu-id="2bc66-110">本指南概括說明 Microsoft 威脅防護，以及如何設定試驗專案的逐步指導方針。</span><span class="sxs-lookup"><span data-stu-id="2bc66-110">This guide provides an overview of Microsoft Threat Protection and step-by-step guidance on how to set up your pilot project.</span></span> 

![執行 Microsoft 威脅防護試驗的階段](../../media/pilotphases.png)

<span data-ttu-id="2bc66-112">下列範例時程表視您環境中的適當資源而異。</span><span class="sxs-lookup"><span data-stu-id="2bc66-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="2bc66-113">有些偵測和工作流程可能需要比其他的更多學習時間。</span><span class="sxs-lookup"><span data-stu-id="2bc66-113">Some detections and workflows might need more learning time than the others.</span></span>

![執行 Microsoft 威脅防護試驗的範例時程表](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="2bc66-115">為了獲得最佳結果，請盡可能請盡可能遵循試驗指示。</span><span class="sxs-lookup"><span data-stu-id="2bc66-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="2bc66-116">試驗行動手冊階段</span><span class="sxs-lookup"><span data-stu-id="2bc66-116">Pilot playbook phases</span></span> 

<span data-ttu-id="2bc66-117">執行 Microsoft 威脅防護試驗有四個階段：</span><span class="sxs-lookup"><span data-stu-id="2bc66-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="2bc66-118">階段</span><span class="sxs-lookup"><span data-stu-id="2bc66-118">Phase</span></span> | <span data-ttu-id="2bc66-119">描述</span><span class="sxs-lookup"><span data-stu-id="2bc66-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="2bc66-120">![規劃](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="2bc66-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="2bc66-121">規劃</span><span class="sxs-lookup"><span data-stu-id="2bc66-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="2bc66-122">深入瞭解在執行 Microsoft 威脅防護試驗專案之前，您需要考慮的事項：</span><span class="sxs-lookup"><span data-stu-id="2bc66-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="2bc66-123">-範圍</span><span class="sxs-lookup"><span data-stu-id="2bc66-123">- Scope</span></span> <br> <span data-ttu-id="2bc66-124">-使用案例</span><span class="sxs-lookup"><span data-stu-id="2bc66-124">- Use cases</span></span> <br><span data-ttu-id="2bc66-125">- 需求：</span><span class="sxs-lookup"><span data-stu-id="2bc66-125">- Requirements</span></span> <br><span data-ttu-id="2bc66-126">-測試計劃</span><span class="sxs-lookup"><span data-stu-id="2bc66-126">- Test plan</span></span> <br> <span data-ttu-id="2bc66-127">-成功準則</span><span class="sxs-lookup"><span data-stu-id="2bc66-127">- Success criteria</span></span> <br> <span data-ttu-id="2bc66-128">-計分卡</span><span class="sxs-lookup"><span data-stu-id="2bc66-128">- Scorecard</span></span> 
| <span data-ttu-id="2bc66-129">![製備](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="2bc66-129">![Preparation](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="2bc66-130">製備</span><span class="sxs-lookup"><span data-stu-id="2bc66-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="2bc66-131">存取 Microsoft 365 的安全性中心以設定您的 Microsoft 威脅防護試驗環境。</span><span class="sxs-lookup"><span data-stu-id="2bc66-131">Access Microsoft 365 Security Center to setup your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="2bc66-132">您將會得到指導：</span><span class="sxs-lookup"><span data-stu-id="2bc66-132">You will be guided to:</span></span><br><br><span data-ttu-id="2bc66-133">-識別利益關係人，並尋找您試驗的登出</span><span class="sxs-lookup"><span data-stu-id="2bc66-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="2bc66-134">-環境考慮</span><span class="sxs-lookup"><span data-stu-id="2bc66-134">- Environment considerations</span></span> <br><span data-ttu-id="2bc66-135">-Access</span><span class="sxs-lookup"><span data-stu-id="2bc66-135">- Access</span></span> <br><span data-ttu-id="2bc66-136">-Azure Active Directory 安裝程式</span><span class="sxs-lookup"><span data-stu-id="2bc66-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="2bc66-137">-設定順序</span><span class="sxs-lookup"><span data-stu-id="2bc66-137">- Configuration order</span></span> <br> <span data-ttu-id="2bc66-138">-註冊 Microsoft 365 E5 試用版</span><span class="sxs-lookup"><span data-stu-id="2bc66-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="2bc66-139">-設定網域</span><span class="sxs-lookup"><span data-stu-id="2bc66-139">- Configure domain</span></span> <br><span data-ttu-id="2bc66-140">-指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="2bc66-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="2bc66-141">-完成入口網站中的設定向導</span><span class="sxs-lookup"><span data-stu-id="2bc66-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="2bc66-142">![攻擊模擬](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="2bc66-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="2bc66-143">攻擊模擬</span><span class="sxs-lookup"><span data-stu-id="2bc66-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="2bc66-144">若要模擬攻擊，您將會得到下列指導：</span><span class="sxs-lookup"><span data-stu-id="2bc66-144">To simulate an attack, you will be guided to:</span></span><br><br><span data-ttu-id="2bc66-145">-確認測試環境需求</span><span class="sxs-lookup"><span data-stu-id="2bc66-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="2bc66-146">-執行模擬</span><span class="sxs-lookup"><span data-stu-id="2bc66-146">-  Run the simulation</span></span> <br><span data-ttu-id="2bc66-147">-調查事件</span><span class="sxs-lookup"><span data-stu-id="2bc66-147">- Investigate an incident</span></span> <br><span data-ttu-id="2bc66-148">-解決事件</span><span class="sxs-lookup"><span data-stu-id="2bc66-148">- resolve the incident</span></span> 
| <span data-ttu-id="2bc66-149">![關閉及摘要](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="2bc66-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="2bc66-150">關閉及摘要</span><span class="sxs-lookup"><span data-stu-id="2bc66-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="2bc66-151">當您已到達程式的結尾時，系統會將您導向：</span><span class="sxs-lookup"><span data-stu-id="2bc66-151">When you've reached the end of the process, you will be guided to:</span></span><br><br><span data-ttu-id="2bc66-152">-流覽您的最後一個輸出</span><span class="sxs-lookup"><span data-stu-id="2bc66-152">- Go through your final output</span></span><br><span data-ttu-id="2bc66-153">-向您的專案關係人呈現您的輸出</span><span class="sxs-lookup"><span data-stu-id="2bc66-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="2bc66-154">-提供意見反應</span><span class="sxs-lookup"><span data-stu-id="2bc66-154">- Provide feedback</span></span> <br><span data-ttu-id="2bc66-155">-執行後續步驟</span><span class="sxs-lookup"><span data-stu-id="2bc66-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="2bc66-156">下一步</span><span class="sxs-lookup"><span data-stu-id="2bc66-156">Next step</span></span>
|<span data-ttu-id="2bc66-157">![規劃階段](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="2bc66-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="2bc66-158">規劃階段</span><span class="sxs-lookup"><span data-stu-id="2bc66-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="2bc66-159">規劃 Microsoft 威脅防護試驗專案</span><span class="sxs-lookup"><span data-stu-id="2bc66-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|