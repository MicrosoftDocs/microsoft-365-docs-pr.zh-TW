---
title: 在 Defender 專案中執行您的試驗 Microsoft 365
description: 在生產環境中執行試用 Microsoft 365 Defender 專案，以有效判斷 Microsoft 365 Defender 的權益和採用方式。
keywords: Microsoft 365defender 試驗，執行試驗 Microsoft 365 defender 專案，評估 Microsoft 365 的 defender 生產中，Microsoft 365 defender 試驗專案，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 3219b329c53c32e02cd29acdd41a48cd93b2e8bb
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930508"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="4be58-104">在 Defender 專案中執行您的試驗 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4be58-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4be58-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="4be58-105">**Applies to:**</span></span>
- <span data-ttu-id="4be58-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4be58-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="4be58-107">本指南可協助您執行試驗專案，方法是提供指標，以確保您具有結構完善的計畫，並引導您完成使用攻擊類比功能，最後會以重要 aways 為前提，以反映及記錄結果。</span><span class="sxs-lookup"><span data-stu-id="4be58-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![執行 Microsoft 365 Defender 試驗的階段](../../media/pilotphases.png)


<span data-ttu-id="4be58-109">執行試驗可協助您有效地判斷採用 Microsoft 365 Defender 的益處。</span><span class="sxs-lookup"><span data-stu-id="4be58-109">Running a pilot helps you effectively determine the benefit of adopting Microsoft 365 Defender.</span></span> <span data-ttu-id="4be58-110">在實際執行環境中啟用 Microsoft 365 的 Defender 並啟動您的使用案例之前，最好是規劃如何決定要在試驗專案中完成的工作，以及設定成功準則。</span><span class="sxs-lookup"><span data-stu-id="4be58-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="4be58-111">如何使用本次試驗行動手冊</span><span class="sxs-lookup"><span data-stu-id="4be58-111">How to use this pilot playbook</span></span>

<span data-ttu-id="4be58-112">本指南提供如何設定試驗專案 Microsoft 365 Defender 及逐步指示的概述。</span><span class="sxs-lookup"><span data-stu-id="4be58-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="4be58-113">Microsoft 365Defender 是一種整合的後續企業防護套件，其可在所有端點、身分識別、電子郵件和應用程式上共同協調保護、偵測、防護、調查和回應，以提供複雜攻擊的整合式防護。</span><span class="sxs-lookup"><span data-stu-id="4be58-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="4be58-114">這樣做的方式是將下列功能結合到單一安全性解決方案中：</span><span class="sxs-lookup"><span data-stu-id="4be58-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="4be58-115">Microsoft Defender for Endpoint (端點) </span><span class="sxs-lookup"><span data-stu-id="4be58-115">Microsoft Defender for Endpoint (endpoints)</span></span>
  - <span data-ttu-id="4be58-116">Microsoft Defender Office 365 (電子郵件) </span><span class="sxs-lookup"><span data-stu-id="4be58-116">Microsoft Defender for Office 365 (email)</span></span> 
  - <span data-ttu-id="4be58-117">Microsoft Defender 身分識別 (身分識別) </span><span class="sxs-lookup"><span data-stu-id="4be58-117">Microsoft Defender for Identity (identity)</span></span> 
  - <span data-ttu-id="4be58-118">Microsoft Cloud App Security (應用程式) </span><span class="sxs-lookup"><span data-stu-id="4be58-118">Microsoft Cloud App Security (apps)</span></span>

![影像 of_Microsoft 365 defender 解決方案，適用于使用者、microsoft defender for Identity、端點 Microsoft defender for Endpoint、雲端應用程式、Microsoft Cloud App Security 及資料的 microsoft defender Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="4be58-120">透過整合型 Microsoft 365 Defender 解決方案，安全性專業人員可以結合 microsoft defender for Endpoint、microsoft defender for Office 365、microsoft defender 身分識別及 Microsoft Cloud App Security 接收，以及決定威脅的完整範圍和影響、它如何進入環境、受到影響的方式，以及目前對組織的影響。</span><span class="sxs-lookup"><span data-stu-id="4be58-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="4be58-121">Microsoft 365Defender 採取自動動作，以防止或停止攻擊及自我修復受影響的信箱、端點和使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="4be58-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="4be58-122">如需詳細資訊，請參閱[Microsoft 365 Defender 概述](microsoft-365-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="4be58-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>



<span data-ttu-id="4be58-123">下列範例時程表視您環境中的適當資源而異。</span><span class="sxs-lookup"><span data-stu-id="4be58-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="4be58-124">有些偵測和工作流程可能需要比其他的更多學習時間。</span><span class="sxs-lookup"><span data-stu-id="4be58-124">Some detections and workflows might need more learning time than the others.</span></span>

![執行 Microsoft 365 Defender 試驗的範例時程表](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="4be58-126">為了獲得最佳結果，請盡可能請盡可能遵循試驗指示。</span><span class="sxs-lookup"><span data-stu-id="4be58-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="4be58-127">試驗行動手冊階段</span><span class="sxs-lookup"><span data-stu-id="4be58-127">Pilot playbook phases</span></span> 

<span data-ttu-id="4be58-128">在執行 Microsoft 365 Defender 試驗中有四個階段：</span><span class="sxs-lookup"><span data-stu-id="4be58-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="4be58-129">階段</span><span class="sxs-lookup"><span data-stu-id="4be58-129">Phase</span></span> | <span data-ttu-id="4be58-130">描述</span><span class="sxs-lookup"><span data-stu-id="4be58-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="4be58-131">規劃</span><span class="sxs-lookup"><span data-stu-id="4be58-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="4be58-132">大約1天</span><span class="sxs-lookup"><span data-stu-id="4be58-132">~ 1 day</span></span>| <span data-ttu-id="4be58-133">深入瞭解在執行 Microsoft 365 Defender 試驗專案之前必須考慮的事項：</span><span class="sxs-lookup"><span data-stu-id="4be58-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="4be58-134">-範圍</span><span class="sxs-lookup"><span data-stu-id="4be58-134">- Scope</span></span> <br> <span data-ttu-id="4be58-135">-使用案例</span><span class="sxs-lookup"><span data-stu-id="4be58-135">- Use cases</span></span> <br><span data-ttu-id="4be58-136">- 需求：</span><span class="sxs-lookup"><span data-stu-id="4be58-136">- Requirements</span></span> <br><span data-ttu-id="4be58-137">-測試計劃</span><span class="sxs-lookup"><span data-stu-id="4be58-137">- Test plan</span></span> <br> <span data-ttu-id="4be58-138">-成功準則</span><span class="sxs-lookup"><span data-stu-id="4be58-138">- Success criteria</span></span> <br> <span data-ttu-id="4be58-139">-計分卡</span><span class="sxs-lookup"><span data-stu-id="4be58-139">- Scorecard</span></span> 
| [<span data-ttu-id="4be58-140">製備</span><span class="sxs-lookup"><span data-stu-id="4be58-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="4be58-141">大約2天</span><span class="sxs-lookup"><span data-stu-id="4be58-141">~2 days</span></span>|  <span data-ttu-id="4be58-142">Access Microsoft 365 的安全性中心設定 Microsoft 365 的 Defender 試驗環境。</span><span class="sxs-lookup"><span data-stu-id="4be58-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="4be58-143">您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="4be58-143">You'll be guided to:</span></span><br><br><span data-ttu-id="4be58-144">-識別利益關係人，並尋找您試驗的登出</span><span class="sxs-lookup"><span data-stu-id="4be58-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="4be58-145">-環境考慮</span><span class="sxs-lookup"><span data-stu-id="4be58-145">- Environment considerations</span></span> <br><span data-ttu-id="4be58-146">-Access</span><span class="sxs-lookup"><span data-stu-id="4be58-146">- Access</span></span> <br><span data-ttu-id="4be58-147">-Azure Active Directory 安裝程式</span><span class="sxs-lookup"><span data-stu-id="4be58-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="4be58-148">-設定順序</span><span class="sxs-lookup"><span data-stu-id="4be58-148">- Configuration order</span></span> <br> <span data-ttu-id="4be58-149">-註冊 Microsoft 365 E5 試用版</span><span class="sxs-lookup"><span data-stu-id="4be58-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="4be58-150">-設定網域</span><span class="sxs-lookup"><span data-stu-id="4be58-150">- Configure domain</span></span> <br><span data-ttu-id="4be58-151">-指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="4be58-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="4be58-152">-完成入口網站中的設定向導</span><span class="sxs-lookup"><span data-stu-id="4be58-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="4be58-153">攻擊模擬</span><span class="sxs-lookup"><span data-stu-id="4be58-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="4be58-154">大約2天</span><span class="sxs-lookup"><span data-stu-id="4be58-154">~2 days</span></span>| <span data-ttu-id="4be58-155">若要模擬攻擊，您將會得到下列指導：</span><span class="sxs-lookup"><span data-stu-id="4be58-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="4be58-156">-確認測試環境需求</span><span class="sxs-lookup"><span data-stu-id="4be58-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="4be58-157">-執行模擬</span><span class="sxs-lookup"><span data-stu-id="4be58-157">-  Run the simulation</span></span> <br><span data-ttu-id="4be58-158">-調查事件</span><span class="sxs-lookup"><span data-stu-id="4be58-158">- Investigate an incident</span></span> <br><span data-ttu-id="4be58-159">-解決事件</span><span class="sxs-lookup"><span data-stu-id="4be58-159">- resolve the incident</span></span> 
| [<span data-ttu-id="4be58-160">關閉及摘要</span><span class="sxs-lookup"><span data-stu-id="4be58-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="4be58-161">大約1天</span><span class="sxs-lookup"><span data-stu-id="4be58-161">~ 1 day</span></span>| <span data-ttu-id="4be58-162">當您到達程式的結尾時，系統會將您導向：</span><span class="sxs-lookup"><span data-stu-id="4be58-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="4be58-163">-流覽您的最後一個輸出</span><span class="sxs-lookup"><span data-stu-id="4be58-163">- Go through your final output</span></span><br><span data-ttu-id="4be58-164">-向您的專案關係人呈現您的輸出</span><span class="sxs-lookup"><span data-stu-id="4be58-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="4be58-165">-提供意見反應</span><span class="sxs-lookup"><span data-stu-id="4be58-165">- Provide feedback</span></span> <br><span data-ttu-id="4be58-166">-執行後續步驟</span><span class="sxs-lookup"><span data-stu-id="4be58-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="4be58-167">下一步</span><span class="sxs-lookup"><span data-stu-id="4be58-167">Next step</span></span>
|[<span data-ttu-id="4be58-168">規劃階段</span><span class="sxs-lookup"><span data-stu-id="4be58-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="4be58-169">規劃 Microsoft 365 Defender 試驗專案</span><span class="sxs-lookup"><span data-stu-id="4be58-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
