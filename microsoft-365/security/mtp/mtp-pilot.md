---
title: 執行您的試驗 Microsoft 365 Defender 專案
description: 在生產環境中執行試驗 Microsoft 365 Defender 專案，以有效地判斷 Microsoft 365 Defender 的好處和採用。
keywords: Microsoft 威脅防護試驗、執行試驗 Microsoft 威脅防護專案、在生產環境中評估 Microsoft 威脅防護、Microsoft 威脅防護試驗專案、網路安全性、進一步持續性威脅、企業安全性、裝置、裝置、身分識別、使用者、資料、應用程式、事件、自動化調查與補救、進一步搜尋
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933027"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="15965-104">執行您的試驗 Microsoft 365 Defender 專案</span><span class="sxs-lookup"><span data-stu-id="15965-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="15965-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="15965-105">**Applies to:**</span></span>
- <span data-ttu-id="15965-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15965-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="15965-107">本指南可協助執行試驗專案，提供指標以確保您擁有結構良好的計畫、指引您使用受攻擊模擬功能，以及最後結束試驗並移開金鑰，以反映在檔結果上。</span><span class="sxs-lookup"><span data-stu-id="15965-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![執行 Microsoft 365 Defender 試驗階段](../../media/pilotphases.png)


<span data-ttu-id="15965-109">執行試驗可有效判斷採用 Microsoft 365 Defender 的好處。</span><span class="sxs-lookup"><span data-stu-id="15965-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="15965-110">在啟用您生產環境中的 Microsoft 365 Defender 並啟動使用案例之前，最好先規劃一下要完成試驗專案的工作，並設定成功準則。</span><span class="sxs-lookup"><span data-stu-id="15965-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="15965-111">如何使用此試驗手冊</span><span class="sxs-lookup"><span data-stu-id="15965-111">How to use this pilot playbook</span></span>

<span data-ttu-id="15965-112">本指南提供 Microsoft 365 Defender 概觀，以及如何設定試驗專案的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="15965-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="15965-113">Microsoft 365 Defender 是一套整合的預先和入侵後企業防護套件，以原生的方式協調端點、身分識別、電子郵件和應用程式的保護、偵測、防護、調查及回應，以提供整合式防護，防範複雜的攻擊。</span><span class="sxs-lookup"><span data-stu-id="15965-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="15965-114">將下列功能結合並結合成單一安全性解決方案，以這麼做：</span><span class="sxs-lookup"><span data-stu-id="15965-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="15965-115">Microsoft Defender for Endpoint， the new name for Microsoft Defender Advanced Threat Protection (endpoints) </span><span class="sxs-lookup"><span data-stu-id="15965-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="15965-116">Microsoft Defender for Office 365， the new name for Office 365 ATP (email) </span><span class="sxs-lookup"><span data-stu-id="15965-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="15965-117">Microsoft Defender for Identity， the new name for Azure ATP (identity) </span><span class="sxs-lookup"><span data-stu-id="15965-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="15965-118">Microsoft Cloud App 安全性 (應用程式) </span><span class="sxs-lookup"><span data-stu-id="15965-118">Microsoft Cloud App Security (apps)</span></span>

![適用于of_Microsoft使用者 、Microsoft Defender for Endpoint 端點、雲端應用程式、Microsoft Cloud App 安全性及資料之 Microsoft Defender for Office 365 之使用者的 365 Defender 解決方案影像](../../media/mtp/m365pillars.png)

<span data-ttu-id="15965-120">使用整合的 Microsoft 365 Defender 解決方案，安全性專業人員可以整合 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity 和 Microsoft Cloud App Security 收到的威脅訊號，並判斷威脅的完整範圍和影響、其進入環境方式、影響的範圍，以及目前對組織的影響。</span><span class="sxs-lookup"><span data-stu-id="15965-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="15965-121">Microsoft 365 Defender 會採取自動動作來防止或停止受攻擊和自我攻擊的信箱、端點和使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="15965-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="15965-122">請參閱 [Microsoft 365 Defender 概觀](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 以瞭解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="15965-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="15965-123">下列範例時程表視您環境中正確的資源而異。</span><span class="sxs-lookup"><span data-stu-id="15965-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="15965-124">有些偵測和工作流程可能需要比其他偵測和工作流程更多的學習時間。</span><span class="sxs-lookup"><span data-stu-id="15965-124">Some detections and workflows might need more learning time than the others.</span></span>

![執行 Microsoft 365 Defender 試驗的範例時程表](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="15965-126">為獲得最佳結果，請盡可能遵循試驗指示。</span><span class="sxs-lookup"><span data-stu-id="15965-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="15965-127">試驗劇本階段</span><span class="sxs-lookup"><span data-stu-id="15965-127">Pilot playbook phases</span></span> 

<span data-ttu-id="15965-128">執行 Microsoft 365 Defender 試驗有四個階段：</span><span class="sxs-lookup"><span data-stu-id="15965-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="15965-129">階段</span><span class="sxs-lookup"><span data-stu-id="15965-129">Phase</span></span> | <span data-ttu-id="15965-130">說明</span><span class="sxs-lookup"><span data-stu-id="15965-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="15965-131">規劃</span><span class="sxs-lookup"><span data-stu-id="15965-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="15965-132">~ 1 天</span><span class="sxs-lookup"><span data-stu-id="15965-132">~ 1 day</span></span>| <span data-ttu-id="15965-133">瞭解執行 Microsoft 365 Defender 試驗專案前需考慮哪些專案：</span><span class="sxs-lookup"><span data-stu-id="15965-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="15965-134">- 範圍</span><span class="sxs-lookup"><span data-stu-id="15965-134">- Scope</span></span> <br> <span data-ttu-id="15965-135">- 使用案例</span><span class="sxs-lookup"><span data-stu-id="15965-135">- Use cases</span></span> <br><span data-ttu-id="15965-136">- 需求：</span><span class="sxs-lookup"><span data-stu-id="15965-136">- Requirements</span></span> <br><span data-ttu-id="15965-137">- 測試計劃</span><span class="sxs-lookup"><span data-stu-id="15965-137">- Test plan</span></span> <br> <span data-ttu-id="15965-138">- 成功準則</span><span class="sxs-lookup"><span data-stu-id="15965-138">- Success criteria</span></span> <br> <span data-ttu-id="15965-139">- 計分卡</span><span class="sxs-lookup"><span data-stu-id="15965-139">- Scorecard</span></span> 
| [<span data-ttu-id="15965-140">製備</span><span class="sxs-lookup"><span data-stu-id="15965-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="15965-141">~2 天</span><span class="sxs-lookup"><span data-stu-id="15965-141">~2 days</span></span>|  <span data-ttu-id="15965-142">存取 Microsoft 365 資訊安全中心以設定您的 Microsoft 365 Defender 試驗環境。</span><span class="sxs-lookup"><span data-stu-id="15965-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="15965-143">系統將會引導您進行：</span><span class="sxs-lookup"><span data-stu-id="15965-143">You'll be guided to:</span></span><br><br><span data-ttu-id="15965-144">- 找出專案關係人，並針對您的試驗尋求籤簽</span><span class="sxs-lookup"><span data-stu-id="15965-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="15965-145">- 環境考慮</span><span class="sxs-lookup"><span data-stu-id="15965-145">- Environment considerations</span></span> <br><span data-ttu-id="15965-146">- Access</span><span class="sxs-lookup"><span data-stu-id="15965-146">- Access</span></span> <br><span data-ttu-id="15965-147">- Azure Active Directory 設定</span><span class="sxs-lookup"><span data-stu-id="15965-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="15965-148">- 組組順序</span><span class="sxs-lookup"><span data-stu-id="15965-148">- Configuration order</span></span> <br> <span data-ttu-id="15965-149">- 註冊 Microsoft 365 E5 試用版</span><span class="sxs-lookup"><span data-stu-id="15965-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="15965-150">- 設定網域</span><span class="sxs-lookup"><span data-stu-id="15965-150">- Configure domain</span></span> <br><span data-ttu-id="15965-151">- 指派 Microsoft 365 E5 授權</span><span class="sxs-lookup"><span data-stu-id="15965-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="15965-152">- 完成入口網站中的設定精靈</span><span class="sxs-lookup"><span data-stu-id="15965-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="15965-153">攻擊模擬</span><span class="sxs-lookup"><span data-stu-id="15965-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="15965-154">~2 天</span><span class="sxs-lookup"><span data-stu-id="15965-154">~2 days</span></span>| <span data-ttu-id="15965-155">若要模擬攻擊，您將受指引到：</span><span class="sxs-lookup"><span data-stu-id="15965-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="15965-156">- 確認測試環境需求</span><span class="sxs-lookup"><span data-stu-id="15965-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="15965-157">- 執行模擬</span><span class="sxs-lookup"><span data-stu-id="15965-157">-  Run the simulation</span></span> <br><span data-ttu-id="15965-158">- 調查事件</span><span class="sxs-lookup"><span data-stu-id="15965-158">- Investigate an incident</span></span> <br><span data-ttu-id="15965-159">- 解決事件</span><span class="sxs-lookup"><span data-stu-id="15965-159">- resolve the incident</span></span> 
| [<span data-ttu-id="15965-160">結語和摘要</span><span class="sxs-lookup"><span data-stu-id="15965-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="15965-161">~ 1 天</span><span class="sxs-lookup"><span data-stu-id="15965-161">~ 1 day</span></span>| <span data-ttu-id="15965-162">當您已達到程式結尾時，會引導您進行以下操作：</span><span class="sxs-lookup"><span data-stu-id="15965-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="15965-163">- 完成最終輸出</span><span class="sxs-lookup"><span data-stu-id="15965-163">- Go through your final output</span></span><br><span data-ttu-id="15965-164">- 向專案關係人呈現您的輸出</span><span class="sxs-lookup"><span data-stu-id="15965-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="15965-165">- 提供意見回饋</span><span class="sxs-lookup"><span data-stu-id="15965-165">- Provide feedback</span></span> <br><span data-ttu-id="15965-166">- 採取下列步驟</span><span class="sxs-lookup"><span data-stu-id="15965-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="15965-167">下一步</span><span class="sxs-lookup"><span data-stu-id="15965-167">Next step</span></span>
|[<span data-ttu-id="15965-168">規劃階段</span><span class="sxs-lookup"><span data-stu-id="15965-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="15965-169">規劃您的 Microsoft 365 Defender 試驗專案</span><span class="sxs-lookup"><span data-stu-id="15965-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
