---
title: 規劃試驗 Microsoft 威脅防護專案
description: 規劃試驗 Microsoft 威脅防護專案與專案關係人，以管理期望並確保成功的結果。
keywords: Microsoft 威脅防護試驗，規劃試驗 Microsoft 威脅防護專案，評估 Microsoft 威脅防護中的實際執行、Microsoft 威脅防護試驗專案、網路安全性、高級持續性威脅、企業安全性、裝置、裝置、身分識別、使用者、資料、應用程式、事件、自動化調查和修正，以及高級搜尋
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: e62b4ec0ee6c9d05321accf269406e8127019f5b
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418106"
---
# <a name="planning-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="bf426-104">規劃試驗 Microsoft 威脅防護專案</span><span class="sxs-lookup"><span data-stu-id="bf426-104">Planning your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bf426-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bf426-105">**Applies to:**</span></span>
- <span data-ttu-id="bf426-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="bf426-106">Microsoft Threat Protection</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="規劃試驗 Microsoft 威脅防護專案" />
      <br/><span data-ttu-id="bf426-108">方案</a></span><span class="sxs-lookup"><span data-stu-id="bf426-108">Plan</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="準備您的 Microsoft 威脅防護試用實驗室或試驗環境" />
      <br/><span data-ttu-id="bf426-110">準備</a></span><span class="sxs-lookup"><span data-stu-id="bf426-110">Prepare</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="執行 Microsoft 威脅防護攻擊模擬" />
     <br/><span data-ttu-id="bf426-112">類比攻擊</a></span><span class="sxs-lookup"><span data-stu-id="bf426-112">Simulate attack</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="關閉並摘要您的 Microsoft 威脅防護試驗" />
     <br/><span data-ttu-id="bf426-114">結束和摘要</a></span><span class="sxs-lookup"><span data-stu-id="bf426-114">Close and summarize</a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="bf426-115">您目前正在規劃階段。</span><span class="sxs-lookup"><span data-stu-id="bf426-115">You're currently in the planning phase.</span></span>

<span data-ttu-id="bf426-116">為了確保您的試驗專案順利完成，您必須在開始時充分規劃並取得您的利益關係人的核准。</span><span class="sxs-lookup"><span data-stu-id="bf426-116">To ensure that your pilot project is a success, it is essential to plan thoroughly with and get approvals from your stakeholders in the beginning.</span></span> <span data-ttu-id="bf426-117">規劃的元素包括識別範圍、使用案例、需求及成功準則。</span><span class="sxs-lookup"><span data-stu-id="bf426-117">Elements of planning include identifying scope, use cases, requirements, and success criteria.</span></span>

<span data-ttu-id="bf426-118">本指南會引導您瞭解如何規劃試驗專案。</span><span class="sxs-lookup"><span data-stu-id="bf426-118">This guide walks you through how to plan your pilot project.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="bf426-119">為了獲得最佳結果，請盡可能請盡可能遵循試驗指示。</span><span class="sxs-lookup"><span data-stu-id="bf426-119">For optimum results, follow the pilot instructions as closely as possible.</span></span>


## <a name="scope"></a><span data-ttu-id="bf426-120">範圍</span><span class="sxs-lookup"><span data-stu-id="bf426-120">Scope</span></span>

<span data-ttu-id="bf426-121">試驗的範圍會根據您的環境及可接受的測試方法，決定測試的範圍。</span><span class="sxs-lookup"><span data-stu-id="bf426-121">The scope of the pilot will determine how broad the test will be, based on your environment and acceptable testing methods.</span></span> <span data-ttu-id="bf426-122">以下是一些需要考慮的範例範圍：</span><span class="sxs-lookup"><span data-stu-id="bf426-122">Here are some example scopes to consider:</span></span>
- <span data-ttu-id="bf426-123">開發或測試環境，其中包含端點、伺服器、網域控制站。</span><span class="sxs-lookup"><span data-stu-id="bf426-123">Development or test environment which includes endpoints, servers, domain controllers.</span></span>
- <span data-ttu-id="bf426-124">使用 Microsoft 365、Azure、Active Directory 服務、端點和伺服器的實際執行環境</span><span class="sxs-lookup"><span data-stu-id="bf426-124">Production environment with Microsoft 365, Azure, Active Directory services, endpoints, and servers</span></span>

>[!NOTE]
><span data-ttu-id="bf426-125">如果您還沒有完整的授權，您可以取得試用授權來 [評估 Microsoft 威脅防護](https://aka.ms/mtp-trial-lab) –規劃、準備、設定、設定和執行您的試驗專案。</span><span class="sxs-lookup"><span data-stu-id="bf426-125">If you don’t have the full licenses yet, you can get trial licenses to [evaluate Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) – plan, prepare, setup, configure, and run your pilot project.</span></span> <span data-ttu-id="bf426-126">您的利益關係人會在協助協助程式從開始到完成的過程中扮演重要角色。</span><span class="sxs-lookup"><span data-stu-id="bf426-126">Your stakeholders will play a big role in helping facilitate the process from start to finish.</span></span>

<span data-ttu-id="bf426-127">若要評估的作業系統類型，也應根據組織組成的定義。</span><span class="sxs-lookup"><span data-stu-id="bf426-127">The types of operating systems to be evaluated should also be defined based on the organizational makeup.</span></span> <span data-ttu-id="bf426-128">這可能包括下列各項： [Mac 端點](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements)、 [Linux 伺服器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements)、 [Windows 10 端點](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)、 [windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)。</span><span class="sxs-lookup"><span data-stu-id="bf426-128">This may include the following: [Mac endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux Servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span></span>

## <a name="use-cases"></a><span data-ttu-id="bf426-129">使用案例</span><span class="sxs-lookup"><span data-stu-id="bf426-129">Use cases</span></span>

<span data-ttu-id="bf426-130">使用案例代表所測試的工具應由其預定使用者使用的語句。</span><span class="sxs-lookup"><span data-stu-id="bf426-130">Use cases represent statements of how the tool being tested is meant to be consumed by its intended users.</span></span> <span data-ttu-id="bf426-131">您可以從特定角色的觀點來表述使用者故事，例如 SOC 分析員。</span><span class="sxs-lookup"><span data-stu-id="bf426-131">These can be formulated as user stories from the point of view of a particular persona, such as a SOC analyst.</span></span> <span data-ttu-id="bf426-132">例如：</span><span class="sxs-lookup"><span data-stu-id="bf426-132">For example:</span></span>
- <span data-ttu-id="bf426-133">在 SOC 分析員中，我需要在網路中的裝置、使用者和信箱之間，查看、關聯、評估和管理警示和事件。</span><span class="sxs-lookup"><span data-stu-id="bf426-133">As a SOC analyst, I need to view, correlate, assess and manage alerts and events across devices, users, and mailboxes in my network.</span></span> <span data-ttu-id="bf426-134">[事件管理]</span><span class="sxs-lookup"><span data-stu-id="bf426-134">[Incident management]</span></span>
- <span data-ttu-id="bf426-135">若為 SOC 分析員，我必須使用工具和程式來自動調查和回應我的網路中的惡意事件。</span><span class="sxs-lookup"><span data-stu-id="bf426-135">As a SOC analyst, I must have the tool and process to automatically investigate and respond to malicious events in my network.</span></span> <span data-ttu-id="bf426-136">[自動 IR]</span><span class="sxs-lookup"><span data-stu-id="bf426-136">[Auto IR]</span></span>
- <span data-ttu-id="bf426-137">若為 SOC 分析員，我必須從環境搜尋資料，以找出已知和潛在威脅，以及可疑活動。</span><span class="sxs-lookup"><span data-stu-id="bf426-137">As a SOC analyst, I must search data from my environment to find known and potential threats, and suspicious activities.</span></span> <span data-ttu-id="bf426-138">[高級搜尋]</span><span class="sxs-lookup"><span data-stu-id="bf426-138">[Advanced Hunting]</span></span>

<span data-ttu-id="bf426-139">請記住，這些使用案例應該在定義之範圍的參數中建立。</span><span class="sxs-lookup"><span data-stu-id="bf426-139">Keep in mind that these use cases should be created within the parameters of the defined scope.</span></span> <span data-ttu-id="bf426-140">例如，如果測試的範圍並未包含 Microsoft Cloud App Security 等工具的評估，則不應建立以這種方式做為資料來源的使用案例。</span><span class="sxs-lookup"><span data-stu-id="bf426-140">If, for example, the scope of testing does not include an evaluation of tools such as Microsoft Cloud App Security, then use cases that rely on this as a data source should not be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf426-141">需求</span><span class="sxs-lookup"><span data-stu-id="bf426-141">Requirements</span></span>

<span data-ttu-id="bf426-142">您可以從使用案例清單中開始建立需求。</span><span class="sxs-lookup"><span data-stu-id="bf426-142">From the list of use cases, you can start to create requirements.</span></span> <span data-ttu-id="bf426-143">需求包含的功能必須具備工具才能滿足使用案例。</span><span class="sxs-lookup"><span data-stu-id="bf426-143">Requirements include features a tool must have to satisfy the use cases.</span></span> <span data-ttu-id="bf426-144">這些需求可以分解成諸如設定與維護、支援整合的類別，以及功能特有的需求，例如搜尋功能和建立自訂警示的能力。</span><span class="sxs-lookup"><span data-stu-id="bf426-144">These requirements can be broken down into categories such as configuration and maintenance, support for integrations, and feature-specific requirements like hunting ability and the ability to build custom alerts.</span></span>

## <a name="test-plan"></a><span data-ttu-id="bf426-145">測試計劃</span><span class="sxs-lookup"><span data-stu-id="bf426-145">Test plan</span></span>

<span data-ttu-id="bf426-146">根據需求的不同，可能會適當的測試方法。</span><span class="sxs-lookup"><span data-stu-id="bf426-146">Depending on the requirements, different methods of testing may be appropriate.</span></span> <span data-ttu-id="bf426-147">例如，如果需求是評估自動修復的 efficacy，則測試計劃必須包含一些步驟，以產生在 Microsoft 威脅防護內觸發自動修正動作 (s) 的行為。</span><span class="sxs-lookup"><span data-stu-id="bf426-147">For instance, if the requirement is to evaluate the efficacy of Automated Remediation, the test plan needs to include steps to generate the behavior(s) that would trigger an automated remediation action within Microsoft Threat Protection.</span></span> <span data-ttu-id="bf426-148">如果需要偵測到特定行為或攻擊，測試可能需要更多步驟。</span><span class="sxs-lookup"><span data-stu-id="bf426-148">If the requirement is to detect a particular behavior or attack, then the test may involve more steps.</span></span> <span data-ttu-id="bf426-149">其重點是準備正確地測試您的需求。</span><span class="sxs-lookup"><span data-stu-id="bf426-149">The point is to have a plan in place to accurately test against your requirements.</span></span>

## <a name="success-criteria"></a><span data-ttu-id="bf426-150">成功準則</span><span class="sxs-lookup"><span data-stu-id="bf426-150">Success criteria</span></span>

<span data-ttu-id="bf426-151">成功準則最後是設定為針對您要測試的專案進行度量的條碼。</span><span class="sxs-lookup"><span data-stu-id="bf426-151">Success criteria is ultimately the bar set to measure against what you are testing.</span></span> <span data-ttu-id="bf426-152">不論是針對其他工具或是對其他工具進行) 測試的 Microsoft 威脅防護 (或任何其他技術，都必須有一些可定量的準則，以判斷該工具所提供的值。</span><span class="sxs-lookup"><span data-stu-id="bf426-152">Whether you are testing Microsoft Threat Protection (or any other technology for that matter) against other tools or by itself, there must be some quantifiable criteria to determine the value the tool provides.</span></span> <span data-ttu-id="bf426-153">根據範圍、需求和測試計劃，成功的準則會決定如何對測試進行評分。</span><span class="sxs-lookup"><span data-stu-id="bf426-153">Based on the scope, requirements, and testing plan, the success criteria will determine how to score the test.</span></span> <span data-ttu-id="bf426-154">根據您的需求，這應該不會有較低的透過或失敗的加權計分。</span><span class="sxs-lookup"><span data-stu-id="bf426-154">This should be less of a pass or fail and more of a weighted scoring based on your needs.</span></span> <span data-ttu-id="bf426-155">例如，若要成功，工具可能需要在您識別的某些重要區域中排名超過80%。</span><span class="sxs-lookup"><span data-stu-id="bf426-155">For example, to be successful, a tool may need to score above 80% in certain critical areas you identify.</span></span>

## <a name="scorecard"></a><span data-ttu-id="bf426-156">計分 卡</span><span class="sxs-lookup"><span data-stu-id="bf426-156">Scorecard</span></span>

<span data-ttu-id="bf426-157">讓方案的所有元素一起使用的一種方式，也可以建立計分卡。</span><span class="sxs-lookup"><span data-stu-id="bf426-157">One way to bring all elements of your plan together can be to create a scorecard.</span></span> <span data-ttu-id="bf426-158">請參閱下方的範例計分卡：</span><span class="sxs-lookup"><span data-stu-id="bf426-158">See a sample scorecard below:</span></span>

| <span data-ttu-id="bf426-159">使用案例</span><span class="sxs-lookup"><span data-stu-id="bf426-159">Use case</span></span> | <span data-ttu-id="bf426-160">需求</span><span class="sxs-lookup"><span data-stu-id="bf426-160">Requirements</span></span> | <span data-ttu-id="bf426-161">設定需求</span><span class="sxs-lookup"><span data-stu-id="bf426-161">Configuration requirements</span></span> | <span data-ttu-id="bf426-162">測試計劃</span><span class="sxs-lookup"><span data-stu-id="bf426-162">Test plan</span></span> | <span data-ttu-id="bf426-163">預期的結果</span><span class="sxs-lookup"><span data-stu-id="bf426-163">Expected outcome</span></span> | <span data-ttu-id="bf426-164">測試狀態</span><span class="sxs-lookup"><span data-stu-id="bf426-164">Test status</span></span> | <span data-ttu-id="bf426-165">分數</span><span class="sxs-lookup"><span data-stu-id="bf426-165">Score</span></span> | <span data-ttu-id="bf426-166">附註</span><span class="sxs-lookup"><span data-stu-id="bf426-166">Notes</span></span> |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|<span data-ttu-id="bf426-167">事件管理</span><span class="sxs-lookup"><span data-stu-id="bf426-167">Incident management</span></span>|<span data-ttu-id="bf426-168">-Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="bf426-168">-  Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="bf426-169">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="bf426-169">- Azure ATP</span></span> </br></br><span data-ttu-id="bf426-170">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="bf426-170">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="bf426-171">-Microsoft Cloud App Security (optional) </span><span class="sxs-lookup"><span data-stu-id="bf426-171">- Microsoft Cloud App Security (optional)</span></span>|<span data-ttu-id="bf426-172">如需詳細資訊，請參閱 [預備課程](https://aka.ms/mtp-trial-lab) 及設定準備工作</span><span class="sxs-lookup"><span data-stu-id="bf426-172">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> |[<span data-ttu-id="bf426-173">類比攻擊</span><span class="sxs-lookup"><span data-stu-id="bf426-173">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="bf426-174">調查事件</span><span class="sxs-lookup"><span data-stu-id="bf426-174">Investigate the incident</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |<span data-ttu-id="bf426-175">調查人員可以瞭解該事件的範圍與影響，並管理該事件</span><span class="sxs-lookup"><span data-stu-id="bf426-175">Investigators can understand the scope and impact of the incident and manage the incident</span></span>||||
|<span data-ttu-id="bf426-176">AutoIR</span><span class="sxs-lookup"><span data-stu-id="bf426-176">AutoIR</span></span>|<span data-ttu-id="bf426-177">-Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="bf426-177">-   Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="bf426-178">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="bf426-178">- Azure ATP</span></span> </br></br><span data-ttu-id="bf426-179">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="bf426-179">- Microsoft Defender ATP</span></span> |<span data-ttu-id="bf426-180">如需詳細資訊，請參閱 [預備課程](https://aka.ms/mtp-trial-lab) 及設定準備工作</span><span class="sxs-lookup"><span data-stu-id="bf426-180">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> <br><span data-ttu-id="bf426-181">啟用 AutoIR</span><span class="sxs-lookup"><span data-stu-id="bf426-181">Enable AutoIR</span></span>  |[<span data-ttu-id="bf426-182">類比攻擊</span><span class="sxs-lookup"><span data-stu-id="bf426-182">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="bf426-183">自動調查</span><span class="sxs-lookup"><span data-stu-id="bf426-183">Automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |<span data-ttu-id="bf426-184">Microsoft 威脅防護會自動修正警示和事件</span><span class="sxs-lookup"><span data-stu-id="bf426-184">Alerts and incidents are automatically remediated by Microsoft Threat Protection</span></span>||||
|<span data-ttu-id="bf426-185">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="bf426-185">Advanced hunting</span></span>|<span data-ttu-id="bf426-186">-Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="bf426-186">- Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="bf426-187">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="bf426-187">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="bf426-188">-Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="bf426-188">- Office 365 ATP</span></span>   |<span data-ttu-id="bf426-189">如需詳細資訊，請參閱 [預備課程](https://aka.ms/mtp-trial-lab) 及設定準備工作</span><span class="sxs-lookup"><span data-stu-id="bf426-189">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span>|[<span data-ttu-id="bf426-190">高級搜尋案例</span><span class="sxs-lookup"><span data-stu-id="bf426-190">Advanced hunting scenario</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |<span data-ttu-id="bf426-191">調查人員可以透過高級搜尋、切換至受影響的實體，以及建立自訂的偵測，尋找資料</span><span class="sxs-lookup"><span data-stu-id="bf426-191">Investigators can find data through advanced hunting, pivoting to impacted entities, and by creating custom detections</span></span>||||



## <a name="next-step"></a><span data-ttu-id="bf426-192">下一步</span><span class="sxs-lookup"><span data-stu-id="bf426-192">Next step</span></span>
|<span data-ttu-id="bf426-193">![準備階段](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="bf426-193">![Preparation phase](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="bf426-194">準備階段</span><span class="sxs-lookup"><span data-stu-id="bf426-194">Preparation phase</span></span>](prepare-mtpeval.md) | <span data-ttu-id="bf426-195">準備您的 Microsoft 威脅防護試驗環境</span><span class="sxs-lookup"><span data-stu-id="bf426-195">Prepare your Microsoft Threat Protection pilot environment</span></span>
|:-------|:-----|
