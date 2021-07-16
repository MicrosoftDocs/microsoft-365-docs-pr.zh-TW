---
title: 在試驗環境中嘗試 Microsoft 365 Defender 事件回應功能，以優先順序及管理事件、設定自動調查和回應，以及使用高級搜尋
description: 嘗試 Microsoft 365 Defender 的事件回應功能，以優先處理及管理事件、自動化調查，以及在威脅偵測中使用高級搜尋。
keywords: Microsoft 365 Defender 試用版，請嘗試 Microsoft 365 Defender，評估 Microsoft 365 Defender，Microsoft 365 Defender 評估實驗室，Microsoft 365 Defender 試驗，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c554f7bcedbdb64118639f5a455fd6f6e55daaa6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457810"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a><span data-ttu-id="913d7-104">在試驗環境中嘗試 Microsoft 365 Defender 事件回應功能</span><span class="sxs-lookup"><span data-stu-id="913d7-104">Try Microsoft 365 Defender incident response capabilities in a pilot environment</span></span>

<span data-ttu-id="913d7-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="913d7-105">**Applies to:**</span></span>
- <span data-ttu-id="913d7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="913d7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="913d7-107">本文是使用試驗環境在 Microsoft 365 Defender 中執行事件調查和回應的程式中的[步驟 2](eval-defender-investigate-respond.md) 。</span><span class="sxs-lookup"><span data-stu-id="913d7-107">This article is [Step 2 of 2](eval-defender-investigate-respond.md) in the process of performing an investigation and response of an incident in Microsoft 365 Defender using a pilot environment.</span></span> <span data-ttu-id="913d7-108">如需此程式的詳細資訊，請參閱 [概述](eval-defender-investigate-respond.md) 文章。</span><span class="sxs-lookup"><span data-stu-id="913d7-108">For more information about this process, see the [overview](eval-defender-investigate-respond.md) article.</span></span>

<span data-ttu-id="913d7-109">在執行[模擬攻擊的事件回應](eval-defender-investigate-respond-simulate-attack.md)後，以下是一些可探索的 Microsoft 365 Defender 功能：</span><span class="sxs-lookup"><span data-stu-id="913d7-109">Once you have performed an [incident response for a simulated attack](eval-defender-investigate-respond-simulate-attack.md), here are some Microsoft 365 Defender capabilities to explore:</span></span>

|<span data-ttu-id="913d7-110">功能</span><span class="sxs-lookup"><span data-stu-id="913d7-110">Capability</span></span> |<span data-ttu-id="913d7-111">描述</span><span class="sxs-lookup"><span data-stu-id="913d7-111">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="913d7-112">設定事件優先順序</span><span class="sxs-lookup"><span data-stu-id="913d7-112">Prioritize incidents</span></span>](#prioritize-incidents) | <span data-ttu-id="913d7-113">使用 [事件] 佇列的篩選和排序，判斷要解決的事件。</span><span class="sxs-lookup"><span data-stu-id="913d7-113">Use filtering and sorting of the incidents queue to determine which incidents to address next.</span></span> |
| [<span data-ttu-id="913d7-114">管理事件</span><span class="sxs-lookup"><span data-stu-id="913d7-114">Manage incidents</span></span>](#manage-incidents) | <span data-ttu-id="913d7-115">修改 incident 屬性，以確保正確的指派、新增標記和批註，以及解決事件。</span><span class="sxs-lookup"><span data-stu-id="913d7-115">Modify incident properties to ensure correct assignment, add tags and comments, and to resolve an incident.</span></span> |
| [<span data-ttu-id="913d7-116">自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="913d7-116">Automated investigation and response</span></span>](#examine-automated-investigation-and-response-with-the-action-center) | <span data-ttu-id="913d7-117">自動調查和回應 (空氣) 功能，可協助您的安全性運作小組更有效率地處理威脅。</span><span class="sxs-lookup"><span data-stu-id="913d7-117">Automated investigation and response (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span> <span data-ttu-id="913d7-118">「行動中心」是「單一窗格的玻璃」的事件和警示工作經驗，例如核准暫止的修復動作。</span><span class="sxs-lookup"><span data-stu-id="913d7-118">The Action center is a "single pane of glass" experience for incident and alert tasks such as approving pending remediation actions.</span></span> |
| [<span data-ttu-id="913d7-119">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="913d7-119">Advanced hunting</span></span>](#advanced-hunting) | <span data-ttu-id="913d7-120">查詢型威脅搜尋工具，可讓您主動檢查網路中的事件，並找出威脅指示器和實體。</span><span class="sxs-lookup"><span data-stu-id="913d7-120">A query-based threat-hunting tool that lets you proactively inspect events in your network and locate threat indicators and entities.</span></span> <span data-ttu-id="913d7-121">您也可以在調查和修正事件期間使用高級搜尋。</span><span class="sxs-lookup"><span data-stu-id="913d7-121">You also use advanced hunting during the investigation and remediation of an incident.</span></span> |
||||

## <a name="prioritize-incidents"></a><span data-ttu-id="913d7-122">設定事件優先順序</span><span class="sxs-lookup"><span data-stu-id="913d7-122">Prioritize incidents</span></span>

<span data-ttu-id="913d7-123">您可以從事件中取得事件佇列 **& 警示 >** Microsoft 365 Defender 入口網站 ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上的事件。</span><span class="sxs-lookup"><span data-stu-id="913d7-123">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="913d7-124">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="913d7-124">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件佇列的範例":::

<span data-ttu-id="913d7-126">**最新的 [事件及警示**] 區段會顯示過去24小時所收到的警示和事件數目圖表。</span><span class="sxs-lookup"><span data-stu-id="913d7-126">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="913d7-127">若要檢查事件清單並排定其工作分派和調查的重要性，您可以：</span><span class="sxs-lookup"><span data-stu-id="913d7-127">To examine the list of incidents and prioritize their importance for assignment and investigation, you can:</span></span> 

- <span data-ttu-id="913d7-128">設定可自訂的欄 (選取 **[選擇欄**) ]，可讓您深入瞭解事件或受影響的實體的不同特性。</span><span class="sxs-lookup"><span data-stu-id="913d7-128">Configure customizable columns (select **Choose columns**) to give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="913d7-129">這可協助您作出有關分析的事件優先順序決定。</span><span class="sxs-lookup"><span data-stu-id="913d7-129">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

- <span data-ttu-id="913d7-130">使用篩選以著重于特定案例或威脅。</span><span class="sxs-lookup"><span data-stu-id="913d7-130">Use filtering to focus on a specific scenario or threat.</span></span> <span data-ttu-id="913d7-131">在事件佇列上套用篩選器，可協助判斷哪些事件需要立即注意。</span><span class="sxs-lookup"><span data-stu-id="913d7-131">Applying filters on the incident queue can help determine which incidents require immediate attention.</span></span> 

<span data-ttu-id="913d7-132">從預設的事件佇列中，選取 [ **篩選** ] 以查看 **篩選** 窗格，您可以從中指定一組特定的事件。</span><span class="sxs-lookup"><span data-stu-id="913d7-132">From the default incident queue, select **Filters** to see a **Filters** pane, from which you can specify a specific set of incidents.</span></span> <span data-ttu-id="913d7-133">範例如下。</span><span class="sxs-lookup"><span data-stu-id="913d7-133">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="事件佇列之篩選窗格的範例":::

<span data-ttu-id="913d7-135">如需詳細資訊，請參閱 [優先順序事件](incident-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="913d7-135">For more information, see [Prioritize incidents](incident-queue.md).</span></span>

## <a name="manage-incidents"></a><span data-ttu-id="913d7-136">管理事件</span><span class="sxs-lookup"><span data-stu-id="913d7-136">Manage incidents</span></span>

<span data-ttu-id="913d7-137">您可以從「 **管理事件** 」窗格中管理事件的事件。</span><span class="sxs-lookup"><span data-stu-id="913d7-137">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="913d7-138">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="913d7-138">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="事件的管理事件窗格範例":::

<span data-ttu-id="913d7-140">您可以從下列專案上的 **管理事件** 連結，顯示此窗格：</span><span class="sxs-lookup"><span data-stu-id="913d7-140">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="913d7-141">事件佇列中事件的屬性窗格。</span><span class="sxs-lookup"><span data-stu-id="913d7-141">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="913d7-142">事件的 **摘要** 頁面。</span><span class="sxs-lookup"><span data-stu-id="913d7-142">**Summary** page of an incident.</span></span>

<span data-ttu-id="913d7-143">您可以透過下列方式管理您的事件：</span><span class="sxs-lookup"><span data-stu-id="913d7-143">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="913d7-144">編輯事件名稱</span><span class="sxs-lookup"><span data-stu-id="913d7-144">Edit the incident name</span></span>

  <span data-ttu-id="913d7-145">根據安全性小組的最佳作法，變更 utomatically 指派的名稱。</span><span class="sxs-lookup"><span data-stu-id="913d7-145">Change the utomatically assigned name based on your security team best practices.</span></span>
  
- <span data-ttu-id="913d7-146">新增事件標籤</span><span class="sxs-lookup"><span data-stu-id="913d7-146">Add incident tags</span></span>

  <span data-ttu-id="913d7-147">新增您的安全小組用來分類事件的標記，以後可以篩選這些事件。</span><span class="sxs-lookup"><span data-stu-id="913d7-147">Add tags that your security team uses to classify incidents, which can be later filtered.</span></span>
  
- <span data-ttu-id="913d7-148">指派事件給您自己</span><span class="sxs-lookup"><span data-stu-id="913d7-148">Assign the incident to yourself</span></span>

  <span data-ttu-id="913d7-149">將其指派給您的使用者帳戶名稱，以後可以篩選該名稱。</span><span class="sxs-lookup"><span data-stu-id="913d7-149">Assign it to your user account name, which can be later filtered.</span></span>
  
- <span data-ttu-id="913d7-150">解決事件</span><span class="sxs-lookup"><span data-stu-id="913d7-150">Resolve an incident</span></span>

  <span data-ttu-id="913d7-151">在事件修正後關閉事件。</span><span class="sxs-lookup"><span data-stu-id="913d7-151">Close the incident after it has been remediated.</span></span>
  
- <span data-ttu-id="913d7-152">設定它的分類和決定</span><span class="sxs-lookup"><span data-stu-id="913d7-152">Set its classification and determination</span></span>

  <span data-ttu-id="913d7-153">當您解決事件時，分類並選取威脅類型。</span><span class="sxs-lookup"><span data-stu-id="913d7-153">Classify and select the threat type when you resolve an incident.</span></span>
  
- <span data-ttu-id="913d7-154">新增註解</span><span class="sxs-lookup"><span data-stu-id="913d7-154">Add comments</span></span>

  <span data-ttu-id="913d7-155">根據安全性小組的最佳作法，使用備註做為進度、記事或其他資訊。</span><span class="sxs-lookup"><span data-stu-id="913d7-155">Use comments for progress, notes, or other information based on your security team best practices.</span></span> <span data-ttu-id="913d7-156">完整的批註記錄可從事件 [詳細資料] 頁面的 [ **批註和記錄** ] 選項中取得。</span><span class="sxs-lookup"><span data-stu-id="913d7-156">The full comment history is available from the **Comments and history** option in the details page of an incident.</span></span>

<span data-ttu-id="913d7-157">如需詳細資訊，請參閱 [管理事件](manage-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="913d7-157">For more information, see [Manage incidents](manage-incidents.md).</span></span>

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a><span data-ttu-id="913d7-158">使用行動中心檢查自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="913d7-158">Examine automated investigation and response with the Action center</span></span>

<span data-ttu-id="913d7-159">根據您的組織設定自動化調查和回應功能的方式，修復動作會自動採取或僅在安全操作小組核准時進行。</span><span class="sxs-lookup"><span data-stu-id="913d7-159">Depending on how automated investigation and response capabilities are configured for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="913d7-160">所有動作（不論是擱置或已完成的動作）都會列在重要訊息 [中心](m365d-action-center.md)，其中會列出裝置的擱置和完成的修正動作、電子郵件 & 共同作業內容，以及在一個位置的身分識別。</span><span class="sxs-lookup"><span data-stu-id="913d7-160">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md), which lists pending and completed remediation actions for your devices, email & collaboration content, and identities in one location.</span></span>

<span data-ttu-id="913d7-161">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="913d7-161">Here's an example.</span></span>

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Microsoft 365 Defender 的整合行動中心":::

<span data-ttu-id="913d7-163">您可以從「行動中心」選取 [擱置中的動作]，然後在彈出窗格中核准或拒絕。</span><span class="sxs-lookup"><span data-stu-id="913d7-163">From the Action center, you can select pending actions and then approve or reject them in the flyout pane.</span></span> <span data-ttu-id="913d7-164">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="913d7-164">Here's an example.</span></span>

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="核准或拒絕動作":::

<span data-ttu-id="913d7-166">請儘快核准 (或拒絕) 擱置的動作，如此您的自動化調查才能繼續進行，並可及時完成。</span><span class="sxs-lookup"><span data-stu-id="913d7-166">Approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span>

<span data-ttu-id="913d7-167">如需詳細資訊，請參閱 [自動化調查和回應](m365d-autoir.md) 及 [行動中心](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="913d7-167">For more information, see [Automated investigation and response](m365d-autoir.md) and [Action center](m365d-action-center.md).</span></span>

## <a name="advanced-hunting"></a><span data-ttu-id="913d7-168">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="913d7-168">Advanced hunting</span></span>

> [!NOTE]
> <span data-ttu-id="913d7-169">在我們逐步執行高級搜尋類比之前，請觀看下列影片，瞭解高級搜尋概念，查看在入口網站中的位置，並瞭解如何協助您進行安全性運作。</span><span class="sxs-lookup"><span data-stu-id="913d7-169">Before we walk you through the advanced hunting simulation, watch the following video to understand advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


<span data-ttu-id="913d7-170">如果 [選用的 fileless PowerShell 攻擊模擬](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) 已到達認證存取階段，您可以在調查中的任何一點使用高級搜尋，以主動從所產生的提醒及受影響的實體中，使用您已知道的事件及記錄來搜尋網路中的事件及記錄。</span><span class="sxs-lookup"><span data-stu-id="913d7-170">If the [optional fileless PowerShell attack simulation](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) were a real attack that had already reached the credential access stage, you can use advanced hunting at any point in the investigation to proactively search through events and records in the network using what you already know from the generated alerts and affected entities.</span></span> <span data-ttu-id="913d7-171">例如，您可以查詢過去30天內任何與外部 IP 位址的連線。</span><span class="sxs-lookup"><span data-stu-id="913d7-171">For instance, you can query for any connections to the external IP address in the past 30 days.</span></span>

### <a name="hunting-environment-requirements"></a><span data-ttu-id="913d7-172">搜尋環境需求</span><span class="sxs-lookup"><span data-stu-id="913d7-172">Hunting environment requirements</span></span>

<span data-ttu-id="913d7-173">這種模擬需要單一內部信箱和裝置。</span><span class="sxs-lookup"><span data-stu-id="913d7-173">There's a single internal mailbox and device required for this simulation.</span></span> <span data-ttu-id="913d7-174">您也需要外部電子郵件帳戶來傳送測試郵件。</span><span class="sxs-lookup"><span data-stu-id="913d7-174">You'll also need an external email account to send the test message.</span></span>

1. <span data-ttu-id="913d7-175">確認您的承租人已[啟用 Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on)。</span><span class="sxs-lookup"><span data-stu-id="913d7-175">Verify that your tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>
2. <span data-ttu-id="913d7-176">識別要用於接收電子郵件的目標信箱。</span><span class="sxs-lookup"><span data-stu-id="913d7-176">Identify a target mailbox to be used for receiving email.</span></span>

   - <span data-ttu-id="913d7-177">此信箱必須由 Microsoft Defender 監控 Office 365</span><span class="sxs-lookup"><span data-stu-id="913d7-177">This mailbox must be monitored by Microsoft Defender for Office 365</span></span>

   - <span data-ttu-id="913d7-178">要求3裝置必須存取此信箱</span><span class="sxs-lookup"><span data-stu-id="913d7-178">The device from requirement 3 needs to access this mailbox</span></span>

3. <span data-ttu-id="913d7-179">設定測試裝置：</span><span class="sxs-lookup"><span data-stu-id="913d7-179">Configure a test device:</span></span>

    <span data-ttu-id="913d7-180">a.</span><span class="sxs-lookup"><span data-stu-id="913d7-180">a.</span></span> <span data-ttu-id="913d7-181">請確認您使用的是 Windows 10 版本1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="913d7-181">Make sure you are using Windows 10 version 1903 or later version.</span></span>

    <span data-ttu-id="913d7-182">b.</span><span class="sxs-lookup"><span data-stu-id="913d7-182">b.</span></span> <span data-ttu-id="913d7-183">將測試裝置加入測試網域。</span><span class="sxs-lookup"><span data-stu-id="913d7-183">Join the test device to the test domain.</span></span>

    <span data-ttu-id="913d7-184">c.</span><span class="sxs-lookup"><span data-stu-id="913d7-184">c.</span></span> <span data-ttu-id="913d7-185">[開啟 Windows Defender 防毒軟體](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。</span><span class="sxs-lookup"><span data-stu-id="913d7-185">[Turn on Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="913d7-186">如果您無法啟用 Windows Defender 防毒軟體，請參閱[此疑難排解主題](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="913d7-186">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

    <span data-ttu-id="913d7-187">d.</span><span class="sxs-lookup"><span data-stu-id="913d7-187">d.</span></span> <span data-ttu-id="913d7-188">[在 Microsoft Defender For Endpoint 上的板載](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="913d7-188">[Onboard to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="913d7-189">執行模擬</span><span class="sxs-lookup"><span data-stu-id="913d7-189">Run the simulation</span></span>

1. <span data-ttu-id="913d7-190">從外部電子郵件帳戶，將電子郵件傳送至「搜尋環境需求」區段之步驟2中所識別的信箱。</span><span class="sxs-lookup"><span data-stu-id="913d7-190">From an external email account, send an email to the mailbox identified in step 2 of the hunting environment requirements section.</span></span> <span data-ttu-id="913d7-191">包含可透過任何現有電子郵件篩選原則所允許的附件。</span><span class="sxs-lookup"><span data-stu-id="913d7-191">Include an attachment that will be allowed through any existing email filter policies.</span></span> <span data-ttu-id="913d7-192">此檔案不需要是惡意或可執行檔。</span><span class="sxs-lookup"><span data-stu-id="913d7-192">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="913d7-193">建議的檔案類型為<i>.pdf</i>、 <i>.exe</i> (如允許) 或 Office 檔案類型（如 Word 檔案）。</span><span class="sxs-lookup"><span data-stu-id="913d7-193">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or an Office document type such as a Word file.</span></span>

2. <span data-ttu-id="913d7-194">從「搜尋環境需求」一節的步驟3中所設定的裝置，開啟已傳送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="913d7-194">Open the sent email from the device configured as defined in step 3 of the hunting environment requirements section.</span></span> <span data-ttu-id="913d7-195">開啟附件或將檔儲存到裝置。</span><span class="sxs-lookup"><span data-stu-id="913d7-195">Either open the attachment or save the file to the device.</span></span>

#### <a name="go-hunting"></a><span data-ttu-id="913d7-196">開始搜尋</span><span class="sxs-lookup"><span data-stu-id="913d7-196">Go hunting</span></span>

1. <span data-ttu-id="913d7-197">開啟[Microsoft 365 Defender 入口網站](https://security.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="913d7-197">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="913d7-198">從功能窗格中，選取 [ **搜尋] > [高級搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="913d7-198">From the navigation pane, select **Hunting > Advanced hunting**.</span></span>

3. <span data-ttu-id="913d7-199">建立以收集電子郵件事件開始的查詢。</span><span class="sxs-lookup"><span data-stu-id="913d7-199">Build a query that starts by gathering email events.</span></span>

   1. <span data-ttu-id="913d7-200">選取 [ **查詢 > 新增**]。</span><span class="sxs-lookup"><span data-stu-id="913d7-200">Select **Query > New**.</span></span>

   1. <span data-ttu-id="913d7-201">在 [**高級搜尋**] 底下的 **電子郵件** 群組中，按兩下 [ **EmailEvents**]。</span><span class="sxs-lookup"><span data-stu-id="913d7-201">In the **Email** groups under **Advanced hunting**, double-click **EmailEvents**.</span></span> <span data-ttu-id="913d7-202">您應該會在 [查詢] 視窗中看到這種情況。</span><span class="sxs-lookup"><span data-stu-id="913d7-202">You should see this in the query window.</span></span>

      ```console
      EmailEvents
      ```

   1. <span data-ttu-id="913d7-203">將查詢的時間範圍變更為過去24小時。</span><span class="sxs-lookup"><span data-stu-id="913d7-203">Change the time frame of the query to the last 24 hours.</span></span> <span data-ttu-id="913d7-204">假設您在執行上述類比時所傳送的電子郵件是在過去24小時內，否則請視需要變更時間範圍。</span><span class="sxs-lookup"><span data-stu-id="913d7-204">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame as needed.</span></span>

   1. <span data-ttu-id="913d7-205">選取 [ **執行查詢**]。</span><span class="sxs-lookup"><span data-stu-id="913d7-205">Select **Run query**.</span></span> <span data-ttu-id="913d7-206">您可能會有不同的結果，視您的試驗環境而定。</span><span class="sxs-lookup"><span data-stu-id="913d7-206">You may have differing results depending on your pilot environment.</span></span>

      > [!NOTE]
      > <span data-ttu-id="913d7-207">請參閱下一個步驟，篩選選項以限制資料傳回。</span><span class="sxs-lookup"><span data-stu-id="913d7-207">See the next step for filtering options to limit data return.</span></span>

      ![高級搜尋查詢結果的範例](../../media/mtp/fig19.png)

        > [!NOTE]
        > <span data-ttu-id="913d7-209">「高級搜尋」會以表格式資料顯示查詢結果。</span><span class="sxs-lookup"><span data-stu-id="913d7-209">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="913d7-210">您也可以選擇以其他格式類型（如圖表）來查看資料。</span><span class="sxs-lookup"><span data-stu-id="913d7-210">You can also opt to view the data in other format types such as charts.</span></span>

   1. <span data-ttu-id="913d7-211">查看結果，查看是否可以識別您開啟的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="913d7-211">Look at the results and see if you can identify the email you opened.</span></span> <span data-ttu-id="913d7-212">最多可能需要兩個小時的時間，郵件才會顯示在高級搜尋中。</span><span class="sxs-lookup"><span data-stu-id="913d7-212">It may take up to two hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="913d7-213">若要縮小結果，您可以將 **where** 條件新增至您的查詢，只會尋找「yahoo.com」為其 SenderMailFromDomain 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="913d7-213">To narrow down the results, you can add the **where** condition to your query to only look for emails that have "yahoo.com" as their SenderMailFromDomain.</span></span> <span data-ttu-id="913d7-214">範例如下。</span><span class="sxs-lookup"><span data-stu-id="913d7-214">Here is an example.</span></span>

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. <span data-ttu-id="913d7-215">按一下查詢中產生的資料列，以便檢查記錄。</span><span class="sxs-lookup"><span data-stu-id="913d7-215">Click the resulting rows from the query so you can inspect the record.</span></span>

      ![選取高級搜尋結果時所開啟之檢查記錄側面面板的範例](../../media/mtp/fig21.png)

4. <span data-ttu-id="913d7-217">現在，您已確認您可以看到電子郵件，新增附件的篩選器。</span><span class="sxs-lookup"><span data-stu-id="913d7-217">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="913d7-218">在環境中著重于所有包含附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="913d7-218">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="913d7-219">針對這種模擬，請將焦點放在輸入電子郵件，而不是從您的環境寄出。</span><span class="sxs-lookup"><span data-stu-id="913d7-219">For this simulation, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="913d7-220">移除您已新增的任何篩選，以找出郵件並新增 "|其中 **AttachmentCount > 0** 和 **EmailDirection**  ==  **"Inbound" "**</span><span class="sxs-lookup"><span data-stu-id="913d7-220">Remove any filters you have added to locate your message and add "| where **AttachmentCount > 0** and **EmailDirection** == **"Inbound""**</span></span>

   <span data-ttu-id="913d7-221">下列查詢會顯示結果，其清單比您的所有電子郵件事件的初始查詢更短：</span><span class="sxs-lookup"><span data-stu-id="913d7-221">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. <span data-ttu-id="913d7-222">接下來，包含附件的相關資訊 (例如：檔案名、雜湊) 結果集。</span><span class="sxs-lookup"><span data-stu-id="913d7-222">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="913d7-223">若要這麼做，請加入 **EmailAttachmentInfo** 表格。</span><span class="sxs-lookup"><span data-stu-id="913d7-223">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="913d7-224">在此情況下，要用於加入的一般欄位是 **NetworkMessageId** 和 **RecipientObjectId**。</span><span class="sxs-lookup"><span data-stu-id="913d7-224">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

   <span data-ttu-id="913d7-225">下列查詢也包含其他行 "| **project-Rename EmailTimestamp = Timestamp**"，可協助識別與您將在下一個步驟中新增之檔案動作相關的電子郵件與時間戳記有關的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="913d7-225">The following query also includes an additional line "| **project-rename EmailTimestamp=Timestamp**" that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. <span data-ttu-id="913d7-226">接下來，使用 **EmailAttachmentInfo** 表格中的 **SHA256** 值，尋找在該雜湊的端點) 上發生的 **DeviceFileEvents** (檔案動作。</span><span class="sxs-lookup"><span data-stu-id="913d7-226">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span> <span data-ttu-id="913d7-227">這裡的一般欄位將會是附件的 SHA256 雜湊。</span><span class="sxs-lookup"><span data-stu-id="913d7-227">The common field here will be the SHA256 hash for the attachment.</span></span>

   <span data-ttu-id="913d7-228">產生的表格現在包含端點 (Microsoft Defender for Endpoint) （例如裝置名稱）、已完成的動作 (在此情況下，篩選為只包括 FileCreated 事件) ，以及儲存檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="913d7-228">The resulting table now includes details from the endpoint (Microsoft Defender for Endpoint) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="913d7-229">也會包含與處理常式相關聯的帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="913d7-229">The account name associated with the process will also be included.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   <span data-ttu-id="913d7-230">您現在已經建立了一個查詢，它會識別所有使用者開啟或儲存附件的輸入電子郵件。</span><span class="sxs-lookup"><span data-stu-id="913d7-230">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="913d7-231">您也可以精煉此查詢，以篩選特定寄件者網域、檔案大小、檔案類型等等。</span><span class="sxs-lookup"><span data-stu-id="913d7-231">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7. <span data-ttu-id="913d7-232">函數是一種特殊的聯接方式，可讓您將更多的 TI 資料（如其流行、簽署者資訊等等）提取到更多的檔。若要取得檔案的詳細資料，請使用 **FileProfile ()** 函數豐富：</span><span class="sxs-lookup"><span data-stu-id="913d7-232">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc. To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a><span data-ttu-id="913d7-233">建立偵測</span><span class="sxs-lookup"><span data-stu-id="913d7-233">Create a detection</span></span>

<span data-ttu-id="913d7-234">當您建立一個查詢，識別您想要針對未來的情況收到 **警示** 的資訊時，您可以從查詢建立自訂偵測。</span><span class="sxs-lookup"><span data-stu-id="913d7-234">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span>

<span data-ttu-id="913d7-235">自訂偵測會根據您設定的頻率執行查詢，而查詢的結果會根據您所選擇的受影響資產，建立安全性警示。</span><span class="sxs-lookup"><span data-stu-id="913d7-235">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="913d7-236">這些警示會與事件相關聯，而且可以被會審為其中一項產品所產生的任何其他安全性警示。</span><span class="sxs-lookup"><span data-stu-id="913d7-236">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1. <span data-ttu-id="913d7-237">在 [查詢] 頁面上，移除 [前往搜尋指示] 的步驟7中所新增的行7和8，然後按一下 [ **建立偵測規則**]。</span><span class="sxs-lookup"><span data-stu-id="913d7-237">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span>

   ![在 [高級搜尋] 頁面中，您可以按一下 [建立偵測規則] 的範例](../../media/mtp/fig22.png)

   > [!NOTE]
   > <span data-ttu-id="913d7-239">如果您按一下 [ **建立偵測規則** ]，並在查詢中有語法錯誤，則您的偵測規則不會儲存。</span><span class="sxs-lookup"><span data-stu-id="913d7-239">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won't be saved.</span></span> <span data-ttu-id="913d7-240">請加倍檢查您的查詢，確定沒有任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="913d7-240">Double-check your query to ensure there's no errors.</span></span>

2. <span data-ttu-id="913d7-241">請填入必要的欄位，其中包含可讓安全性小組瞭解提醒的資訊、它的產生原因，以及您預期採取的動作。</span><span class="sxs-lookup"><span data-stu-id="913d7-241">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span>

   ![[建立偵測規則] 頁面的範例，您可以在其中定義警示詳細資料。](../../media/mtp/fig23.png)

   <span data-ttu-id="913d7-243">請務必以清晰的方式填寫欄位，以協助下一使用者對此偵測規則警示作出明智的決定。</span><span class="sxs-lookup"><span data-stu-id="913d7-243">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span>

3. <span data-ttu-id="913d7-244">選取此警示會影響哪些實體。</span><span class="sxs-lookup"><span data-stu-id="913d7-244">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="913d7-245">在此情況下，請選取 [ **裝置** 和 **信箱**]。</span><span class="sxs-lookup"><span data-stu-id="913d7-245">In this case, select **Device** and **Mailbox**.</span></span>

   ![[建立偵測規則] 頁面的範例，您可以在其中選擇受影響實體的參數](../../media/mtp/fig24.png)

4. <span data-ttu-id="913d7-247">決定觸發警示時應執行的動作。</span><span class="sxs-lookup"><span data-stu-id="913d7-247">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="913d7-248">在此情況下，請執行防病毒掃描，但可以採取其他動作。</span><span class="sxs-lookup"><span data-stu-id="913d7-248">In this case, run an antivirus scan, though other actions could be taken.</span></span>

   ![[建立偵測規則] 頁面範例，您可以在觸發警示時執行防病毒掃描，以協助解決威脅](../../media/mtp/fig25.png)

5. <span data-ttu-id="913d7-250">選取警示規則的範圍。</span><span class="sxs-lookup"><span data-stu-id="913d7-250">Select the scope for the alert rule.</span></span> <span data-ttu-id="913d7-251">因為此查詢涉及裝置，所以裝置群組會在此自訂偵測中與 Microsoft Defender for Endpoint coNtext 相關。</span><span class="sxs-lookup"><span data-stu-id="913d7-251">Since this query involves devices, the device groups are relevant in this custom detection according to Microsoft Defender for Endpoint context.</span></span> <span data-ttu-id="913d7-252">當您建立未包括裝置作為受影響實體的自訂偵測時，不適用範圍。</span><span class="sxs-lookup"><span data-stu-id="913d7-252">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>

   ![[建立偵測規則] 頁面的範例，您可以在其中設定警示規則的範圍，以管理您將看到的結果預期](../../media/mtp/fig26.png)

   <span data-ttu-id="913d7-254">在此試驗中，您可能會想要將此規則限制在實際執行環境中的測試裝置子集。</span><span class="sxs-lookup"><span data-stu-id="913d7-254">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6. <span data-ttu-id="913d7-255">選取 [建立 **]**。</span><span class="sxs-lookup"><span data-stu-id="913d7-255">Select **Create**.</span></span> <span data-ttu-id="913d7-256">然後，選取導覽窗格中的 **自訂偵測規則** 。</span><span class="sxs-lookup"><span data-stu-id="913d7-256">Then, select **Custom detection rules** from the navigation panel.</span></span>

   ![功能表中的自訂偵測規則選項範例](../../media/mtp/fig27a.png)

   ![顯示規則和執行詳細資料的偵測規則頁面範例](../../media/mtp/fig27b.png)

   <span data-ttu-id="913d7-259">在此頁面中，您可以選取將會開啟詳細資料頁面的偵測規則。</span><span class="sxs-lookup"><span data-stu-id="913d7-259">From this page, you can select the detection rule, which will open a details page.</span></span>

   ![[電子郵件附件] 頁面的範例，您可以在其中看到規則執行、觸發的警示和動作狀態、編輯偵測等](../../media/mtp/fig28.png)

<!--

### Advanced hunting walk-through exercises

To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities, and create custom detections and remediation actions.

> [!NOTE]
> Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.

|Title|Description|Download MP4|Watch on YouTube|CSL file to use|
|---|---|---|---|---|
|Episode 1: KQL fundamentals|We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender. Learn about available advanced hunting data and basic KQL syntax and operators.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Episode 1: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Episode 2: Joins|We'll continue learning about data in advanced hunting and how to join tables together. Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Episode 2: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Episode 3: Summarizing, pivoting, and visualizing data|Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing. In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema. We turn our datasets into charts that can help improve analysis.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Episode 3: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Episode 4: Let's hunt! Applying KQL to incident tracking|Time to track some attacker activity! In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack. Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episode 4: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

--> 

### <a name="expert-training-on-advanced-hunting"></a><span data-ttu-id="913d7-261">高級搜尋的專家訓練</span><span class="sxs-lookup"><span data-stu-id="913d7-261">Expert training on advanced hunting</span></span>

<span data-ttu-id="913d7-262">**追蹤敵人** 是新安全性分析師和經驗豐富威脅 hunters 的網路廣播系列。</span><span class="sxs-lookup"><span data-stu-id="913d7-262">**Tracking the adversary** is a webcast series for new security analysts and seasoned threat hunters.</span></span> <span data-ttu-id="913d7-263">它會引導您完成「高級搜尋」的基本概念，以建立您自己的複雜查詢。</span><span class="sxs-lookup"><span data-stu-id="913d7-263">It guides you through the basics of advanced hunting all the way to creating your own sophisticated queries.</span></span> 

<span data-ttu-id="913d7-264">請參閱 [取得高級搜尋上的專家訓練](advanced-hunting-expert-training.md) ，以開始著手。</span><span class="sxs-lookup"><span data-stu-id="913d7-264">See [Get expert training on advanced hunting](advanced-hunting-expert-training.md) to get started.</span></span>

### <a name="navigation-you-may-need"></a><span data-ttu-id="913d7-265">您可能需要的導覽</span><span class="sxs-lookup"><span data-stu-id="913d7-265">Navigation you may need</span></span>

[<span data-ttu-id="913d7-266">建立 Microsoft 365 Defender 評估環境</span><span class="sxs-lookup"><span data-stu-id="913d7-266">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
