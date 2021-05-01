---
title: Microsoft 365 Defender 中的事件
description: 調查 Microsoft 365 安全性中心內的裝置、使用者和信箱所看到的事件。
keywords: 事件、警示、調查、分析、回應、關聯、攻擊、電腦、裝置、使用者、身分識別、身分識別、信箱、電子郵件、365、microsoft、m365、事件回應、網路攻擊
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e2e29015d4cb5e04510577118eb847b9b596a6c5
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114279"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="b4707-104">Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="b4707-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b4707-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b4707-105">**Applies to:**</span></span>
- <span data-ttu-id="b4707-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4707-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="b4707-107">想要體驗 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="b4707-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="b4707-108">您可以[在實驗室環境中評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[在生產環境中執行試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="b4707-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="b4707-109">Microsoft 365 Defender 中的事件是組成攻擊之故事的相關警示和相關資料的集合。</span><span class="sxs-lookup"><span data-stu-id="b4707-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="b4707-110">Microsoft 365 服務和應用程式會在偵測到可疑或惡意事件或活動時建立警示。</span><span class="sxs-lookup"><span data-stu-id="b4707-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="b4707-111">個別警示可提供關於已完成或進行中攻擊的重要線索。</span><span class="sxs-lookup"><span data-stu-id="b4707-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="b4707-112">不過，攻擊一般會針對不同類型的實體（例如裝置、使用者和信箱）採用各種技術。</span><span class="sxs-lookup"><span data-stu-id="b4707-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="b4707-113">其結果是針對您租使用者中的多個實體的多個警示。</span><span class="sxs-lookup"><span data-stu-id="b4707-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="b4707-114">因為 piecing 個別警示共同取得攻擊的方式可能會是挑戰性和費時，所以 Microsoft 365 Defender 會自動將警示及其相關資訊匯總到事件中。</span><span class="sxs-lookup"><span data-stu-id="b4707-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender 如何將實體中的事件與事件產生關聯":::

<span data-ttu-id="b4707-116">請在 Microsoft 365 Defender (4 分鐘) 中觀看事件的這一小段簡介。</span><span class="sxs-lookup"><span data-stu-id="b4707-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="b4707-117">將相關警示分組到事件中，可讓您全面瞭解攻擊。</span><span class="sxs-lookup"><span data-stu-id="b4707-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="b4707-118">例如，您可以看到：</span><span class="sxs-lookup"><span data-stu-id="b4707-118">For example, you can see:</span></span>

- <span data-ttu-id="b4707-119">攻擊的開始位置。</span><span class="sxs-lookup"><span data-stu-id="b4707-119">Where the attack started.</span></span>
- <span data-ttu-id="b4707-120">使用的戰術。</span><span class="sxs-lookup"><span data-stu-id="b4707-120">What tactics were used.</span></span>
- <span data-ttu-id="b4707-121">攻擊進入您租使用者的距離。</span><span class="sxs-lookup"><span data-stu-id="b4707-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="b4707-122">攻擊的範圍，例如影響的裝置、使用者和信箱數目。</span><span class="sxs-lookup"><span data-stu-id="b4707-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="b4707-123">所有與攻擊相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="b4707-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="b4707-124">若[啟用](m365d-enable.md)，Microsoft 365 Defender 可以透過自動化和人工智慧來自動調查和解決提醒。</span><span class="sxs-lookup"><span data-stu-id="b4707-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="b4707-125">您也可以執行其他修復步驟，以解決攻擊。</span><span class="sxs-lookup"><span data-stu-id="b4707-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="b4707-126">Microsoft 365 安全性中心的事件及警示</span><span class="sxs-lookup"><span data-stu-id="b4707-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="b4707-127">您可以在 Microsoft 365 安全性中心 ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上，管理事件 **& 警示 > 事件**。</span><span class="sxs-lookup"><span data-stu-id="b4707-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="b4707-128">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="b4707-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 security center 中的 [事件] 頁面":::

<span data-ttu-id="b4707-130">選取 [事件名稱] 會顯示事件摘要，並可讓您存取具有其他資訊的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b4707-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 security center 中的事件摘要頁面範例":::

<span data-ttu-id="b4707-132">事件的其他索引標籤如下：</span><span class="sxs-lookup"><span data-stu-id="b4707-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="b4707-133">警示</span><span class="sxs-lookup"><span data-stu-id="b4707-133">Alerts</span></span> 

  <span data-ttu-id="b4707-134">與該事件相關的所有提醒，以及其資訊。</span><span class="sxs-lookup"><span data-stu-id="b4707-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="b4707-135">裝置</span><span class="sxs-lookup"><span data-stu-id="b4707-135">Devices</span></span>

  <span data-ttu-id="b4707-136">已識別為屬於事件一部分或與其相關的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="b4707-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="b4707-137">使用者</span><span class="sxs-lookup"><span data-stu-id="b4707-137">Users</span></span>

  <span data-ttu-id="b4707-138">已識別為屬於該事件或與其相關的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="b4707-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="b4707-139">信箱</span><span class="sxs-lookup"><span data-stu-id="b4707-139">Mailboxes</span></span>

  <span data-ttu-id="b4707-140">已識別為屬於事件一部分或與其相關的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="b4707-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="b4707-141">調查</span><span class="sxs-lookup"><span data-stu-id="b4707-141">Investigations</span></span>

  <span data-ttu-id="b4707-142">事件中的警示所觸發的所有自動調查。</span><span class="sxs-lookup"><span data-stu-id="b4707-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="b4707-143">證據與回應</span><span class="sxs-lookup"><span data-stu-id="b4707-143">Evidence and Response</span></span>

  <span data-ttu-id="b4707-144">事件中警示中所有支援的事件及可疑的實體。</span><span class="sxs-lookup"><span data-stu-id="b4707-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="b4707-145">以下是事件與其資料之間的關係，以及 Microsoft 365 security center 中事件的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b4707-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="在 Microsoft 365 安全中心的事件索引標籤上，事件及其資料的關聯性":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="b4707-147">Microsoft 365 Defender 的事件回應工作流程範例</span><span class="sxs-lookup"><span data-stu-id="b4707-147">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="b4707-148">以下是以「Microsoft 365 安全性中心」回應 Microsoft 365 中的事件的範例工作流程。</span><span class="sxs-lookup"><span data-stu-id="b4707-148">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Microsoft 365 的事件回應工作流程範例":::

<span data-ttu-id="b4707-150">在事件佇列中，針對分析和解決方式，識別最高優先順序的事件，讓他們可以進行回應。</span><span class="sxs-lookup"><span data-stu-id="b4707-150">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="b4707-151">這是下列專案的組合：</span><span class="sxs-lookup"><span data-stu-id="b4707-151">This is a combination of:</span></span>

- <span data-ttu-id="b4707-152">透過篩選和排序事件佇列來判斷最高優先順序事件的[會審](incident-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="b4707-152">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="b4707-153">透過修改其標題、將其指派給分析員，以及新增標記和批註來[管理](manage-incidents.md)事件。</span><span class="sxs-lookup"><span data-stu-id="b4707-153">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="b4707-154">針對每個事件，開始 [攻擊和警示分析](investigate-incidents.md)：</span><span class="sxs-lookup"><span data-stu-id="b4707-154">For each incident, begin an [attack and alert analysis](investigate-incidents.md):</span></span>
 
   <span data-ttu-id="b4707-155">a.</span><span class="sxs-lookup"><span data-stu-id="b4707-155">a.</span></span> <span data-ttu-id="b4707-156">請查看事件摘要，瞭解其範圍和嚴重性，以及會影響哪些實體 ([ **摘要** ] 索引標籤) 中。</span><span class="sxs-lookup"><span data-stu-id="b4707-156">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="b4707-157">b.</span><span class="sxs-lookup"><span data-stu-id="b4707-157">b.</span></span> <span data-ttu-id="b4707-158">開始分析警示，以瞭解其來源、範圍和嚴重性 (**警示** ] 索引標籤) 。</span><span class="sxs-lookup"><span data-stu-id="b4707-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="b4707-159">c.</span><span class="sxs-lookup"><span data-stu-id="b4707-159">c.</span></span> <span data-ttu-id="b4707-160">如有需要，請在 [ **裝置**]、[ **使用者**] 和 [ **信箱** ] 索引標籤)  (，收集受影響裝置、使用者和信箱的資訊。</span><span class="sxs-lookup"><span data-stu-id="b4707-160">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="b4707-161">d.</span><span class="sxs-lookup"><span data-stu-id="b4707-161">d.</span></span> <span data-ttu-id="b4707-162">請參閱「**調查**」索引標籤) 中 Microsoft 365 Defender 如何自動解決某些警示 (。</span><span class="sxs-lookup"><span data-stu-id="b4707-162">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="b4707-163">e.</span><span class="sxs-lookup"><span data-stu-id="b4707-163">e.</span></span> <span data-ttu-id="b4707-164">如有需要，請使用事件資料組中的資訊，以取得 (**證據與回應** ] 索引標籤) 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b4707-164">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="b4707-165">在分析之後或過程中執行包容，以減少攻擊和 eradication 安全性威脅的任何其他影響。</span><span class="sxs-lookup"><span data-stu-id="b4707-165">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="b4707-166">盡可能將租使用者資源還原為事件之前所用的狀態，從攻擊復原。</span><span class="sxs-lookup"><span data-stu-id="b4707-166">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="b4707-167">[解決](manage-incidents.md#resolve-incident) 事件，並在進行事件後學習需要一些時間，以進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="b4707-167">[Resolve](manage-incidents.md#resolve-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="b4707-168">瞭解攻擊的類型及其影響。</span><span class="sxs-lookup"><span data-stu-id="b4707-168">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="b4707-169">調查 [威脅分析](threat-analytics.md) 中的攻擊，以及安全性攻擊趨勢的安全性社區。</span><span class="sxs-lookup"><span data-stu-id="b4707-169">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="b4707-170">召回您用來解決事件的工作流程，並視需要更新您的標準工作流程、流程、原則及行動行動。</span><span class="sxs-lookup"><span data-stu-id="b4707-170">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="b4707-171">決定是否需要在安全性設定中進行變更，並加以實施。</span><span class="sxs-lookup"><span data-stu-id="b4707-171">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="b4707-172">如果您是新的安全性分析，請參閱 [回應第一個事件的簡介](incidents-overview.md) 以取得其他資訊，並逐步執行範例事件。</span><span class="sxs-lookup"><span data-stu-id="b4707-172">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="b4707-173">Microsoft 365 Defender 的安全性操作範例</span><span class="sxs-lookup"><span data-stu-id="b4707-173">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="b4707-174">以下是 Microsoft 365 Defender 的安全性運作範例。</span><span class="sxs-lookup"><span data-stu-id="b4707-174">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Micosoft 365 Defender 的安全性操作範例":::

<span data-ttu-id="b4707-176">每個任務可以包含：</span><span class="sxs-lookup"><span data-stu-id="b4707-176">Daily tasks can include:</span></span>

- <span data-ttu-id="b4707-177">[管理](manage-incidents.md) 事件</span><span class="sxs-lookup"><span data-stu-id="b4707-177">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="b4707-178">檢查 [自動調查和回應 (AIR) ](m365d-action-center.md) 動作</span><span class="sxs-lookup"><span data-stu-id="b4707-178">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions</span></span>
- <span data-ttu-id="b4707-179">查看最新的 [威脅分析](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="b4707-179">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="b4707-180">[回應](investigate-incidents.md) 事件</span><span class="sxs-lookup"><span data-stu-id="b4707-180">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="b4707-181">每月任務可以包含：</span><span class="sxs-lookup"><span data-stu-id="b4707-181">Monthly tasks can include:</span></span>

- <span data-ttu-id="b4707-182">檢查 [空中設定](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="b4707-182">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="b4707-183">檢查 [安全分數](microsoft-secure-score-improvement-actions.md) 和 [威脅 & 弱點管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="b4707-183">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="b4707-184">向您的 IT 安全性管理階層報告</span><span class="sxs-lookup"><span data-stu-id="b4707-184">Reporting to your IT security management chain</span></span>

<span data-ttu-id="b4707-185">每個季度的工作可以包含向首席資訊安全性監察官 (CISO) 中的安全性結果的報告及簡報。</span><span class="sxs-lookup"><span data-stu-id="b4707-185">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="b4707-186">每年的工作可以包含執行重大事件或破壞練習，以測試您的員工、系統和程式。</span><span class="sxs-lookup"><span data-stu-id="b4707-186">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="b4707-187">您可以使用每日、每月、每季及每年的工作來更新或修改程式、原則及安全性設定。</span><span class="sxs-lookup"><span data-stu-id="b4707-187">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b4707-188">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b4707-188">Next steps</span></span>

<span data-ttu-id="b4707-189">[ **事件** ] 頁面的 [事件] 佇列會列出最近的事件。</span><span class="sxs-lookup"><span data-stu-id="b4707-189">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="b4707-190">在這裡，您可以：</span><span class="sxs-lookup"><span data-stu-id="b4707-190">From here, you can:</span></span>

- <span data-ttu-id="b4707-191">根據嚴重性及其他因素，查看應 [優先](incident-queue.md) 考慮哪些事件。</span><span class="sxs-lookup"><span data-stu-id="b4707-191">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="b4707-192">[管理事件](manage-incidents.md)，包括重新命名、指派、分類，以及新增事件管理工作流程的標記和批註。</span><span class="sxs-lookup"><span data-stu-id="b4707-192">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments for your incident management workflow.</span></span>
- <span data-ttu-id="b4707-193">執行事件的 [分析](investigate-incidents.md) 。</span><span class="sxs-lookup"><span data-stu-id="b4707-193">Perform an [analysis](investigate-incidents.md) of an incident.</span></span>
