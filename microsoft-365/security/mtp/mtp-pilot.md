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
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 4ec46891248c09f580b19d888573544ad2b4930f
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446864"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="62b90-104">執行試驗 Microsoft 威脅防護專案</span><span class="sxs-lookup"><span data-stu-id="62b90-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="62b90-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="62b90-105">**Applies to:**</span></span>
- <span data-ttu-id="62b90-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="62b90-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="62b90-107">若要有效判斷 Microsoft 威脅防護 (MTP) 的優點和採用方式，您可以執行試驗專案。</span><span class="sxs-lookup"><span data-stu-id="62b90-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="62b90-108">在實際執行環境中啟用 Microsoft 威脅防護，並啟動您的使用案例之前，最好要規劃決定要為試驗專案完成的工作，並設定成功準則。</span><span class="sxs-lookup"><span data-stu-id="62b90-108">Before enabling Microsoft Threat Protection in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="62b90-109">如何使用本次試驗行動手冊</span><span class="sxs-lookup"><span data-stu-id="62b90-109">How to use this pilot playbook</span></span>

<span data-ttu-id="62b90-110">本指南提供 Microsoft 威脅防護的概述，以及如何設定試驗專案的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="62b90-110">This guide provides an overview of Microsoft Threat Protection and step-by-step instructions on how to set up your pilot project.</span></span> 

![執行 Microsoft 威脅防護試驗的階段](../../media/pilotphases.png)

<span data-ttu-id="62b90-112">下列範例時程表視您環境中的適當資源而異。</span><span class="sxs-lookup"><span data-stu-id="62b90-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="62b90-113">有些偵測和工作流程可能需要比其他的更多學習時間。</span><span class="sxs-lookup"><span data-stu-id="62b90-113">Some detections and workflows might need more learning time than the others.</span></span>

![執行 Microsoft 威脅防護試驗的範例時程表](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="62b90-115">為了獲得最佳結果，請盡可能請盡可能遵循試驗指示。</span><span class="sxs-lookup"><span data-stu-id="62b90-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="62b90-116">試驗行動手冊階段</span><span class="sxs-lookup"><span data-stu-id="62b90-116">Pilot playbook phases</span></span> 

<span data-ttu-id="62b90-117">執行 Microsoft 威脅防護試驗有四個階段：</span><span class="sxs-lookup"><span data-stu-id="62b90-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="62b90-118">階段</span><span class="sxs-lookup"><span data-stu-id="62b90-118">Phase</span></span> | <span data-ttu-id="62b90-119">描述</span><span class="sxs-lookup"><span data-stu-id="62b90-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="62b90-120">![規劃](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="62b90-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="62b90-121">規劃</span><span class="sxs-lookup"><span data-stu-id="62b90-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="62b90-122">深入瞭解在執行 Microsoft 威脅防護試驗專案之前，您需要考慮的事項：</span><span class="sxs-lookup"><span data-stu-id="62b90-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="62b90-123">-範圍</span><span class="sxs-lookup"><span data-stu-id="62b90-123">- Scope</span></span> <br> <span data-ttu-id="62b90-124">-使用案例</span><span class="sxs-lookup"><span data-stu-id="62b90-124">- Use cases</span></span> <br><span data-ttu-id="62b90-125">- 需求：</span><span class="sxs-lookup"><span data-stu-id="62b90-125">- Requirements</span></span> <br><span data-ttu-id="62b90-126">-測試計劃</span><span class="sxs-lookup"><span data-stu-id="62b90-126">- Test plan</span></span> <br> <span data-ttu-id="62b90-127">-成功準則</span><span class="sxs-lookup"><span data-stu-id="62b90-127">- Success criteria</span></span> <br> <span data-ttu-id="62b90-128">-計分卡</span><span class="sxs-lookup"><span data-stu-id="62b90-128">- Scorecard</span></span> 
| <span data-ttu-id="62b90-129">![製備](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="62b90-129">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="62b90-130">製備</span><span class="sxs-lookup"><span data-stu-id="62b90-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="62b90-131">存取 Microsoft 365 的安全性中心以設定您的 Microsoft 威脅防護試驗環境。</span><span class="sxs-lookup"><span data-stu-id="62b90-131">Access Microsoft 365 Security Center to set up your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="62b90-132">您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="62b90-132">You'll be guided to:</span></span><br><br><span data-ttu-id="62b90-133">-識別利益關係人，並尋找您試驗的登出</span><span class="sxs-lookup"><span data-stu-id="62b90-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="62b90-134">-環境考慮</span><span class="sxs-lookup"><span data-stu-id="62b90-134">- Environment considerations</span></span> <br><span data-ttu-id="62b90-135">-Access</span><span class="sxs-lookup"><span data-stu-id="62b90-135">- Access</span></span> <br><span data-ttu-id="62b90-136">-Azure Active Directory 安裝程式</span><span class="sxs-lookup"><span data-stu-id="62b90-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="62b90-137">-設定順序</span><span class="sxs-lookup"><span data-stu-id="62b90-137">- Configuration order</span></span> <br> <span data-ttu-id="62b90-138">-註冊 Microsoft 365 E5 試用版</span><span class="sxs-lookup"><span data-stu-id="62b90-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="62b90-139">-設定網域</span><span class="sxs-lookup"><span data-stu-id="62b90-139">- Configure domain</span></span> <br><span data-ttu-id="62b90-140">-指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="62b90-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="62b90-141">-完成入口網站中的設定向導</span><span class="sxs-lookup"><span data-stu-id="62b90-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="62b90-142">![攻擊模擬](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="62b90-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="62b90-143">攻擊模擬</span><span class="sxs-lookup"><span data-stu-id="62b90-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="62b90-144">若要模擬攻擊，您將會得到下列指導：</span><span class="sxs-lookup"><span data-stu-id="62b90-144">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="62b90-145">-確認測試環境需求</span><span class="sxs-lookup"><span data-stu-id="62b90-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="62b90-146">-執行模擬</span><span class="sxs-lookup"><span data-stu-id="62b90-146">-  Run the simulation</span></span> <br><span data-ttu-id="62b90-147">-調查事件</span><span class="sxs-lookup"><span data-stu-id="62b90-147">- Investigate an incident</span></span> <br><span data-ttu-id="62b90-148">-解決事件</span><span class="sxs-lookup"><span data-stu-id="62b90-148">- resolve the incident</span></span> 
| <span data-ttu-id="62b90-149">![關閉及摘要](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="62b90-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="62b90-150">關閉及摘要</span><span class="sxs-lookup"><span data-stu-id="62b90-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="62b90-151">當您到達程式的結尾時，系統會將您導向：</span><span class="sxs-lookup"><span data-stu-id="62b90-151">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="62b90-152">-流覽您的最後一個輸出</span><span class="sxs-lookup"><span data-stu-id="62b90-152">- Go through your final output</span></span><br><span data-ttu-id="62b90-153">-向您的專案關係人呈現您的輸出</span><span class="sxs-lookup"><span data-stu-id="62b90-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="62b90-154">-提供意見反應</span><span class="sxs-lookup"><span data-stu-id="62b90-154">- Provide feedback</span></span> <br><span data-ttu-id="62b90-155">-執行後續步驟</span><span class="sxs-lookup"><span data-stu-id="62b90-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="62b90-156">下一步</span><span class="sxs-lookup"><span data-stu-id="62b90-156">Next step</span></span>
|<span data-ttu-id="62b90-157">![規劃階段](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="62b90-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="62b90-158">規劃階段</span><span class="sxs-lookup"><span data-stu-id="62b90-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="62b90-159">規劃 Microsoft 威脅防護試驗專案</span><span class="sxs-lookup"><span data-stu-id="62b90-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
