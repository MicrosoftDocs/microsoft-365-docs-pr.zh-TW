---
title: 執行您的試驗 Microsoft 365 Defender 專案
description: 在生產環境中執行您的試驗 Microsoft 365 Defender 專案，以有效判斷 Microsoft 365 Defender 的優點和採用方式。
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
ms.openlocfilehash: 350904022ec86acdbebf109dd5946598643aea83
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843657"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="d82b8-104">執行您的試驗 Microsoft 365 Defender 專案</span><span class="sxs-lookup"><span data-stu-id="d82b8-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d82b8-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="d82b8-105">**Applies to:**</span></span>
- <span data-ttu-id="d82b8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d82b8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d82b8-107">若要有效地判斷 Microsoft 365 Defender 的優點和採用方式，您可以執行試驗專案。</span><span class="sxs-lookup"><span data-stu-id="d82b8-107">To effectively determine the benefit and adoption of Microsoft 365 Defender, you can run a pilot project.</span></span> <span data-ttu-id="d82b8-108">在實際執行環境中啟用 Microsoft 365 Defender 並啟動您的使用案例之前，最好要規劃決定要為試驗專案完成的工作，以及設定成功準則。</span><span class="sxs-lookup"><span data-stu-id="d82b8-108">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="d82b8-109">如何使用本次試驗行動手冊</span><span class="sxs-lookup"><span data-stu-id="d82b8-109">How to use this pilot playbook</span></span>

<span data-ttu-id="d82b8-110">本指南概要說明 Microsoft 365 Defender 及如何設定試驗專案的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="d82b8-110">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="d82b8-111">Microsoft 365 Defender 是一種整合的後續企業防護套件，其可共同協調各端點、身分識別、電子郵件和應用程式的保護、偵測、防護、調查和回應，以提供複雜攻擊的整合式防護。</span><span class="sxs-lookup"><span data-stu-id="d82b8-111">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="d82b8-112">這樣做的方式是將下列功能結合到單一安全性解決方案中：</span><span class="sxs-lookup"><span data-stu-id="d82b8-112">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="d82b8-113">Microsoft Defender for Endpoint，Microsoft Defender 高級威脅防護的新名稱 (端點) </span><span class="sxs-lookup"><span data-stu-id="d82b8-113">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="d82b8-114">Microsoft Defender for Office 365，新的 Office 365 ATP 名稱 (電子郵件) </span><span class="sxs-lookup"><span data-stu-id="d82b8-114">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="d82b8-115">Microsoft Defender 身分識別，Azure ATP (身分識別的新名稱) </span><span class="sxs-lookup"><span data-stu-id="d82b8-115">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="d82b8-116">Microsoft Cloud App Security (app) </span><span class="sxs-lookup"><span data-stu-id="d82b8-116">Microsoft Cloud App Security (apps)</span></span>

![影像 of_Microsoft 365 Defender 解決方案，適用于使用者、Microsoft Defender 身分識別、端點 Microsoft Defender for Endpoint、雲端應用程式、Microsoft Cloud App Security 及 data、Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="d82b8-118">透過整合的 Microsoft 365 Defender 解決方案，安全性專業人員可以結合 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity 和 Microsoft Cloud App Security 接收，以及決定威脅的完整範圍和影響、它如何進入環境、其受到影響，以及目前對組織的影響。</span><span class="sxs-lookup"><span data-stu-id="d82b8-118">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="d82b8-119">Microsoft 365 Defender 採取自動動作，以防止或停止攻擊及自我修復受影響的信箱、端點和使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="d82b8-119">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="d82b8-120">如需詳細資訊，請參閱 [Microsoft 365 Defender 概述](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 。</span><span class="sxs-lookup"><span data-stu-id="d82b8-120">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>

![執行 Microsoft 365 Defender 試驗的階段](../../media/pilotphases.png)

<span data-ttu-id="d82b8-122">下列範例時程表視您環境中的適當資源而異。</span><span class="sxs-lookup"><span data-stu-id="d82b8-122">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="d82b8-123">有些偵測和工作流程可能需要比其他的更多學習時間。</span><span class="sxs-lookup"><span data-stu-id="d82b8-123">Some detections and workflows might need more learning time than the others.</span></span>

![執行 Microsoft 365 Defender 試驗的範例時程表](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="d82b8-125">為了獲得最佳結果，請盡可能請盡可能遵循試驗指示。</span><span class="sxs-lookup"><span data-stu-id="d82b8-125">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="d82b8-126">試驗行動手冊階段</span><span class="sxs-lookup"><span data-stu-id="d82b8-126">Pilot playbook phases</span></span> 

<span data-ttu-id="d82b8-127">在執行 Microsoft 365 Defender 試驗中有四個階段：</span><span class="sxs-lookup"><span data-stu-id="d82b8-127">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="d82b8-128">階段</span><span class="sxs-lookup"><span data-stu-id="d82b8-128">Phase</span></span> | <span data-ttu-id="d82b8-129">描述</span><span class="sxs-lookup"><span data-stu-id="d82b8-129">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="d82b8-130">![規劃](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="d82b8-130">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="d82b8-131">規劃</span><span class="sxs-lookup"><span data-stu-id="d82b8-131">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="d82b8-132">深入瞭解在執行 Microsoft 365 Defender 試驗專案之前，您需要考慮的事項：</span><span class="sxs-lookup"><span data-stu-id="d82b8-132">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="d82b8-133">-範圍</span><span class="sxs-lookup"><span data-stu-id="d82b8-133">- Scope</span></span> <br> <span data-ttu-id="d82b8-134">-使用案例</span><span class="sxs-lookup"><span data-stu-id="d82b8-134">- Use cases</span></span> <br><span data-ttu-id="d82b8-135">- 需求：</span><span class="sxs-lookup"><span data-stu-id="d82b8-135">- Requirements</span></span> <br><span data-ttu-id="d82b8-136">-測試計劃</span><span class="sxs-lookup"><span data-stu-id="d82b8-136">- Test plan</span></span> <br> <span data-ttu-id="d82b8-137">-成功準則</span><span class="sxs-lookup"><span data-stu-id="d82b8-137">- Success criteria</span></span> <br> <span data-ttu-id="d82b8-138">-計分卡</span><span class="sxs-lookup"><span data-stu-id="d82b8-138">- Scorecard</span></span> 
| <span data-ttu-id="d82b8-139">![製備](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="d82b8-139">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="d82b8-140">製備</span><span class="sxs-lookup"><span data-stu-id="d82b8-140">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="d82b8-141">存取 Microsoft 365 的安全性中心以設定您的 Microsoft 365 Defender 試驗環境。</span><span class="sxs-lookup"><span data-stu-id="d82b8-141">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="d82b8-142">您將會指導您：</span><span class="sxs-lookup"><span data-stu-id="d82b8-142">You'll be guided to:</span></span><br><br><span data-ttu-id="d82b8-143">-識別利益關係人，並尋找您試驗的登出</span><span class="sxs-lookup"><span data-stu-id="d82b8-143">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="d82b8-144">-環境考慮</span><span class="sxs-lookup"><span data-stu-id="d82b8-144">- Environment considerations</span></span> <br><span data-ttu-id="d82b8-145">-Access</span><span class="sxs-lookup"><span data-stu-id="d82b8-145">- Access</span></span> <br><span data-ttu-id="d82b8-146">-Azure Active Directory 安裝程式</span><span class="sxs-lookup"><span data-stu-id="d82b8-146">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="d82b8-147">-設定順序</span><span class="sxs-lookup"><span data-stu-id="d82b8-147">- Configuration order</span></span> <br> <span data-ttu-id="d82b8-148">-註冊 Microsoft 365 E5 試用版</span><span class="sxs-lookup"><span data-stu-id="d82b8-148">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="d82b8-149">-設定網域</span><span class="sxs-lookup"><span data-stu-id="d82b8-149">- Configure domain</span></span> <br><span data-ttu-id="d82b8-150">-指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="d82b8-150">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="d82b8-151">-完成入口網站中的設定向導</span><span class="sxs-lookup"><span data-stu-id="d82b8-151">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="d82b8-152">![攻擊模擬](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="d82b8-152">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="d82b8-153">攻擊模擬</span><span class="sxs-lookup"><span data-stu-id="d82b8-153">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="d82b8-154">若要模擬攻擊，您將會得到下列指導：</span><span class="sxs-lookup"><span data-stu-id="d82b8-154">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="d82b8-155">-確認測試環境需求</span><span class="sxs-lookup"><span data-stu-id="d82b8-155">- Verify the test environment requirements</span></span> <br><span data-ttu-id="d82b8-156">-執行模擬</span><span class="sxs-lookup"><span data-stu-id="d82b8-156">-  Run the simulation</span></span> <br><span data-ttu-id="d82b8-157">-調查事件</span><span class="sxs-lookup"><span data-stu-id="d82b8-157">- Investigate an incident</span></span> <br><span data-ttu-id="d82b8-158">-解決事件</span><span class="sxs-lookup"><span data-stu-id="d82b8-158">- resolve the incident</span></span> 
| <span data-ttu-id="d82b8-159">![關閉及摘要](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="d82b8-159">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="d82b8-160">關閉及摘要</span><span class="sxs-lookup"><span data-stu-id="d82b8-160">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="d82b8-161">當您到達程式的結尾時，系統會將您導向：</span><span class="sxs-lookup"><span data-stu-id="d82b8-161">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="d82b8-162">-流覽您的最後一個輸出</span><span class="sxs-lookup"><span data-stu-id="d82b8-162">- Go through your final output</span></span><br><span data-ttu-id="d82b8-163">-向您的專案關係人呈現您的輸出</span><span class="sxs-lookup"><span data-stu-id="d82b8-163">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="d82b8-164">-提供意見反應</span><span class="sxs-lookup"><span data-stu-id="d82b8-164">- Provide feedback</span></span> <br><span data-ttu-id="d82b8-165">-執行後續步驟</span><span class="sxs-lookup"><span data-stu-id="d82b8-165">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="d82b8-166">下一步</span><span class="sxs-lookup"><span data-stu-id="d82b8-166">Next step</span></span>
|<span data-ttu-id="d82b8-167">![規劃階段](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="d82b8-167">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="d82b8-168">規劃階段</span><span class="sxs-lookup"><span data-stu-id="d82b8-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="d82b8-169">規劃 Microsoft 365 Defender 試驗專案</span><span class="sxs-lookup"><span data-stu-id="d82b8-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
