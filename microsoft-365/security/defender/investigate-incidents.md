---
title: 調查 Microsoft 365 Defender 中的事件
description: 調查與裝置、使用者和信箱相關的事件。
keywords: 事件，事件，分析，回應，機器，裝置，使用者，身分識別，郵件，電子郵件，信箱，調查，圖形，證據
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
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fdfc065aea3549e99de72c968c0fa19412f9e246
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105353"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="d3a50-104">調查 Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="d3a50-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d3a50-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d3a50-105">**Applies to:**</span></span>

- <span data-ttu-id="d3a50-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3a50-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d3a50-107">Microsoft 365 Defender 會將所有相關的警示、資產、調查和證據，全部從您的裝置、使用者和信箱匯總到事件中，讓您全面瞭解攻擊的整體廣度。</span><span class="sxs-lookup"><span data-stu-id="d3a50-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="d3a50-108">在事件內，您會分析影響網路的警示、瞭解其含義，以及對照證據來設計有效的修復計畫。</span><span class="sxs-lookup"><span data-stu-id="d3a50-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-investigation"></a><span data-ttu-id="d3a50-109">初始調查</span><span class="sxs-lookup"><span data-stu-id="d3a50-109">Initial investigation</span></span>

<span data-ttu-id="d3a50-110">深入瞭解詳細資料之前，請先查看事件的屬性與摘要。</span><span class="sxs-lookup"><span data-stu-id="d3a50-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="d3a50-111">您可以從選取 [核取記號] 欄開始選取該事件。</span><span class="sxs-lookup"><span data-stu-id="d3a50-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="d3a50-112">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="d3a50-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="從核取記號欄中選取事件的範例":::

<span data-ttu-id="d3a50-114">當您這麼做時，會開啟摘要窗格，其中會顯示事件的重要資訊（例如嚴重性），以及[MITRE ATT&CK &trade; ](https://attack.mitre.org/)類別的事件。</span><span class="sxs-lookup"><span data-stu-id="d3a50-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="d3a50-115">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="d3a50-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="事件摘要窗格的範例":::

<span data-ttu-id="d3a50-117">您可以從這裡選取 [ **開啟 incident] 頁面**。</span><span class="sxs-lookup"><span data-stu-id="d3a50-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="d3a50-118">這會開啟此事件的主頁面，您可以在此找到更多摘要資訊和索引標籤，以取得提醒、裝置、使用者、調查和證據。</span><span class="sxs-lookup"><span data-stu-id="d3a50-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="d3a50-119">您也可以從事件佇列中選取事件名稱，以開啟事件的主版頁面。</span><span class="sxs-lookup"><span data-stu-id="d3a50-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="d3a50-120">摘要</span><span class="sxs-lookup"><span data-stu-id="d3a50-120">Summary</span></span>

<span data-ttu-id="d3a50-121">[ **摘要** ] 頁面可讓您查看有關事件的最重要注意事項。</span><span class="sxs-lookup"><span data-stu-id="d3a50-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 security center 中的事件摘要頁面範例":::

<span data-ttu-id="d3a50-123">「攻擊類別」可讓您直觀和數值的方式，顯示攻擊如何對 kill 鏈進行的進展。</span><span class="sxs-lookup"><span data-stu-id="d3a50-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="d3a50-124">與其他 Microsoft 安全性產品一樣，Microsoft 365 Defender 會對應至[MITRE ATT&CK &trade; ](https://attack.mitre.org/) framework。</span><span class="sxs-lookup"><span data-stu-id="d3a50-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="d3a50-125">範圍區段會顯示屬於此事件中影響最大的資產清單。</span><span class="sxs-lookup"><span data-stu-id="d3a50-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="d3a50-126">如果關於此資產的特定資訊，例如風險層級、調查優先順序以及資產上的任何標記，本區段也將會顯示這項資訊。</span><span class="sxs-lookup"><span data-stu-id="d3a50-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="d3a50-127">提醒時程表會提供 sneak，以即時查看警示的發生順序，以及這些警示連結至此事件的原因。</span><span class="sxs-lookup"><span data-stu-id="d3a50-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="d3a50-128">和 last-「證據」區段會摘要說明事件中包含多少不同的專案以及其修復狀態，所以您可以立即識別您是否需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="d3a50-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="d3a50-129">這項功能可讓您瞭解應注意的事件最重要特性，以協助您進行事件的初始診斷。</span><span class="sxs-lookup"><span data-stu-id="d3a50-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="d3a50-130">警示</span><span class="sxs-lookup"><span data-stu-id="d3a50-130">Alerts</span></span>

<span data-ttu-id="d3a50-131">您可以在 [ **警示** ] 索引標籤上，查看與該事件相關之警示的警示佇列及其他相關資訊，例如：</span><span class="sxs-lookup"><span data-stu-id="d3a50-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="d3a50-132">嚴重性。</span><span class="sxs-lookup"><span data-stu-id="d3a50-132">Severity.</span></span>
- <span data-ttu-id="d3a50-133">警示中所涉及的實體。</span><span class="sxs-lookup"><span data-stu-id="d3a50-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="d3a50-134"> (microsoft defender for Identity、microsoft defender for Endpoint、microsoft defender for Office 365) 的警示來源。</span><span class="sxs-lookup"><span data-stu-id="d3a50-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="d3a50-135">連結在一起的原因。</span><span class="sxs-lookup"><span data-stu-id="d3a50-135">The reason they were linked together.</span></span>

<span data-ttu-id="d3a50-136">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="d3a50-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="事件提醒頁面的範例":::

<span data-ttu-id="d3a50-138">依預設，提醒會以時間順序排列，以讓您瞭解事件隨時間的播放方式。</span><span class="sxs-lookup"><span data-stu-id="d3a50-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="d3a50-139">當您在事件內選取警示時，Microsoft 365 Defender 會顯示針對整體事件內容的警示資訊。</span><span class="sxs-lookup"><span data-stu-id="d3a50-139">When you select an alert within an incident, Microsoft 365 Defender displays the alert information specific to the context of the overall incident.</span></span> 

<span data-ttu-id="d3a50-140">您可以看到警示的事件，哪些其他觸發的警示會導致目前的警示，以及攻擊中所涉及的所有受影響實體和活動，包括檔案、使用者和信箱。</span><span class="sxs-lookup"><span data-stu-id="d3a50-140">You can see the events of the alert, which other triggered alerts caused the current alert, and all the affected entities and activities involved in the attack, including files, users, and mailboxes.</span></span>

<span data-ttu-id="d3a50-141">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="d3a50-141">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="事件中警示詳細資料頁面的範例":::

<span data-ttu-id="d3a50-143">此事件提醒頁面包含下列區段：</span><span class="sxs-lookup"><span data-stu-id="d3a50-143">This incident alert page is composed of these sections:</span></span>

- <span data-ttu-id="d3a50-144">警示案例，包含發生狀況的摘要</span><span class="sxs-lookup"><span data-stu-id="d3a50-144">Alert story, which includes a summary of what happened</span></span>
- <span data-ttu-id="d3a50-145">相關的事件及警示</span><span class="sxs-lookup"><span data-stu-id="d3a50-145">Related events and alerts</span></span>
- <span data-ttu-id="d3a50-146">摘要詳細資料</span><span class="sxs-lookup"><span data-stu-id="d3a50-146">Summary details</span></span>

<span data-ttu-id="d3a50-147">瞭解如何在 [調查提醒](investigate-alerts.md)中使用警示佇列及警示頁面。</span><span class="sxs-lookup"><span data-stu-id="d3a50-147">Learn how to use the alert queue and alert pages in [investigate alerts](investigate-alerts.md).</span></span>

## <a name="devices"></a><span data-ttu-id="d3a50-148">裝置</span><span class="sxs-lookup"><span data-stu-id="d3a50-148">Devices</span></span>

<span data-ttu-id="d3a50-149">[ **裝置** ] 索引標籤會列出與該事件相關的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="d3a50-149">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="d3a50-150">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="d3a50-150">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="事件的裝置頁面範例":::

<span data-ttu-id="d3a50-152">您可以選取裝置的核取記號，以查看裝置、目錄資料、作用中警示及已登入使用者的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d3a50-152">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="d3a50-153">選取裝置的名稱，以查看 Microsoft Defender for 端點裝置庫存中的裝置詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d3a50-153">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Microsoft Defender 端點的裝置頁面範例":::

<span data-ttu-id="d3a50-155">在 [裝置] 頁面上，您可以收集裝置的其他相關資訊，例如其所有警示、時程表及安全性建議。</span><span class="sxs-lookup"><span data-stu-id="d3a50-155">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="d3a50-156">例如，在 [ **時程表** ] 索引標籤中，您可以在機器時程表中向內移動，並以時間順序查看機器上所觀察到的所有事件和行為，並與所引發的警示交錯。</span><span class="sxs-lookup"><span data-stu-id="d3a50-156">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="d3a50-157">您可以在裝置頁面上執行手動掃描。</span><span class="sxs-lookup"><span data-stu-id="d3a50-157">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="d3a50-158">在 [Microsoft 365 安全性中心] 中，選擇 [**端點] > 裝置庫存**]。</span><span class="sxs-lookup"><span data-stu-id="d3a50-158">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="d3a50-159">選取具有警示的裝置，然後執行防病毒掃描。</span><span class="sxs-lookup"><span data-stu-id="d3a50-159">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="d3a50-160">在 [ **裝置庫存** ] 頁面上追蹤並顯示的動作（例如防病毒掃描）。</span><span class="sxs-lookup"><span data-stu-id="d3a50-160">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="d3a50-161">若要深入瞭解，請參閱[執行 Microsoft Defender 防毒軟體掃描裝置](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。</span><span class="sxs-lookup"><span data-stu-id="d3a50-161">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="d3a50-162">使用者</span><span class="sxs-lookup"><span data-stu-id="d3a50-162">Users</span></span>

<span data-ttu-id="d3a50-163">[ **使用者** ] 索引標籤會列出已識別為屬於該事件或與其相關之所有使用者。</span><span class="sxs-lookup"><span data-stu-id="d3a50-163">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="d3a50-164">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="d3a50-164">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="事件的使用者頁面範例":::

<span data-ttu-id="d3a50-166">您可以為使用者選取核取記號，以查看使用者帳戶威脅、公開和連絡人資訊的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d3a50-166">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="d3a50-167">選取使用者名稱以查看其他使用者帳戶詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d3a50-167">Select the user name to see additional user account details.</span></span>

<span data-ttu-id="d3a50-168">瞭解如何在 [調查使用者](investigate-users.md)中查看其他使用者資訊及管理事件的使用者。</span><span class="sxs-lookup"><span data-stu-id="d3a50-168">Learn how to view additional user information and manage the users of an incident in [investigate users](investigate-users.md).</span></span>


## <a name="mailboxes"></a><span data-ttu-id="d3a50-169">信箱</span><span class="sxs-lookup"><span data-stu-id="d3a50-169">Mailboxes</span></span>

<span data-ttu-id="d3a50-170">[ **信箱** ] 索引標籤會列出已識別為屬於該事件或與其相關的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="d3a50-170">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="d3a50-171">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="d3a50-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="事件的信箱頁面範例":::

<span data-ttu-id="d3a50-173">您可以選取信箱的核取記號，以查看作用中的警示清單。</span><span class="sxs-lookup"><span data-stu-id="d3a50-173">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="d3a50-174">選取信箱名稱，以查看 Microsoft Defender for Office 365 的 Explorer 頁面上的其他信箱詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d3a50-174">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="d3a50-175">調查</span><span class="sxs-lookup"><span data-stu-id="d3a50-175">Investigations</span></span>

<span data-ttu-id="d3a50-176">[ **調查** ] 索引標籤會列出此事件中的警示所觸發的所有 [自動調查](m365d-autoir.md) 。</span><span class="sxs-lookup"><span data-stu-id="d3a50-176">The **Investigations** tab lists all the [automated investigations](m365d-autoir.md) triggered by alerts in this incident.</span></span> <span data-ttu-id="d3a50-177">調查會執行修正動作，或等候分析員的動作核准，視您如何設定自動調查，以在 Microsoft Defender for Endpoint 和 Defender for Office 365 中執行。</span><span class="sxs-lookup"><span data-stu-id="d3a50-177">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="事件的調查頁面範例":::

<span data-ttu-id="d3a50-179">選取調查以流覽至其詳細資料頁面，以取得調查和修正狀態的完整資訊。</span><span class="sxs-lookup"><span data-stu-id="d3a50-179">Select an investigation to navigate to its details page for full information on the investigation and remediation status.</span></span> <span data-ttu-id="d3a50-180">如果有任何動作出于調查的一部分而待核准，它們就會出現在 [ **擱置的動作記錄** ] 索引標籤中。採取動作做為事件修復的一部分。</span><span class="sxs-lookup"><span data-stu-id="d3a50-180">If there are any actions pending for approval as part of the investigation, they will appear in the **Pending actions history** tab. Take action as part of incident remediation.</span></span>

<span data-ttu-id="d3a50-181">此外，還會顯示一個 **調查圖表** 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="d3a50-181">There is also an **Investigation graph** tab that shows:</span></span>

- <span data-ttu-id="d3a50-182">組織中受影響資產的警示連接。</span><span class="sxs-lookup"><span data-stu-id="d3a50-182">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="d3a50-183">哪些實體與哪些警示相關，以及如何成為攻擊本文的一部分。</span><span class="sxs-lookup"><span data-stu-id="d3a50-183">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="d3a50-184">事件的警示。</span><span class="sxs-lookup"><span data-stu-id="d3a50-184">The alerts for the incident.</span></span>

<span data-ttu-id="d3a50-185">調查圖表可協助您透過連線屬於攻擊一部分相關資產（如使用者、裝置和信箱）的不同可疑實體，快速瞭解攻擊的完整範圍。</span><span class="sxs-lookup"><span data-stu-id="d3a50-185">The investigation graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="d3a50-186">如需詳細資訊，請參閱[Microsoft 365 Defender 中的自動化調查和回應](m365d-autoir.md)。</span><span class="sxs-lookup"><span data-stu-id="d3a50-186">For more information, see [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="d3a50-187">證據與回應</span><span class="sxs-lookup"><span data-stu-id="d3a50-187">Evidence and Response</span></span>

<span data-ttu-id="d3a50-188">[ **證據與回應** ] 索引標籤會顯示事件中的警示中所有支援的事件及可疑的實體。</span><span class="sxs-lookup"><span data-stu-id="d3a50-188">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="d3a50-189">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="d3a50-189">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="事件的證據與回應頁面範例":::

<span data-ttu-id="d3a50-191">Microsoft 365 Defender 會自動調查警示中的所有事件支援事件和可疑實體，以提供重要電子郵件、檔案、程式、服務、IP 位址等相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d3a50-191">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="d3a50-192">這可協助您快速偵測並封鎖事件中的潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="d3a50-192">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="d3a50-193">每個分析的實體都會以判定為序 (惡意、可疑、清除) 和修正狀態。</span><span class="sxs-lookup"><span data-stu-id="d3a50-193">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="d3a50-194">這可協助您瞭解整個事件的修復狀態，以及可以採取的後續步驟。</span><span class="sxs-lookup"><span data-stu-id="d3a50-194">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d3a50-195">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d3a50-195">Next steps</span></span>

<span data-ttu-id="d3a50-196">視需要：</span><span class="sxs-lookup"><span data-stu-id="d3a50-196">As needed:</span></span>

- [<span data-ttu-id="d3a50-197">調查事件的警示</span><span class="sxs-lookup"><span data-stu-id="d3a50-197">Investigate the alerts of an incident</span></span>](investigate-alerts.md)
- [<span data-ttu-id="d3a50-198">調查事件的使用者</span><span class="sxs-lookup"><span data-stu-id="d3a50-198">Investigate the users of an incident</span></span>](investigate-users.md)

## <a name="see-also"></a><span data-ttu-id="d3a50-199">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d3a50-199">See also</span></span>

- [<span data-ttu-id="d3a50-200">事件概觀</span><span class="sxs-lookup"><span data-stu-id="d3a50-200">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d3a50-201">設定事件優先順序</span><span class="sxs-lookup"><span data-stu-id="d3a50-201">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="d3a50-202">管理事件</span><span class="sxs-lookup"><span data-stu-id="d3a50-202">Manage incidents</span></span>](manage-incidents.md)

