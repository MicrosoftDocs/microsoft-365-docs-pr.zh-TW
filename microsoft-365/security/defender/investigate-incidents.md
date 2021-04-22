---
title: 分析 Microsoft 365 Defender 中的事件
description: 分析與裝置、使用者和信箱相關的事件。
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 22d3bba03745cee330f89b67061e6c6b13e78aed
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939739"
---
# <a name="analyze-incidents-in-microsoft-365-defender"></a><span data-ttu-id="a00a2-104">分析 Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="a00a2-104">Analyze incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a00a2-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a00a2-105">**Applies to:**</span></span>

- <span data-ttu-id="a00a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a00a2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a00a2-107">Microsoft 365 Defender 會將所有相關的警示、資產、調查和證據，集中于您的裝置、使用者和信箱，以讓您全面瞭解攻擊的整體廣度。</span><span class="sxs-lookup"><span data-stu-id="a00a2-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="a00a2-108">在事件內，您會分析影響網路的警示、瞭解其含義，以及對照證據來設計有效的修復計畫。</span><span class="sxs-lookup"><span data-stu-id="a00a2-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-analysis"></a><span data-ttu-id="a00a2-109">初始分析</span><span class="sxs-lookup"><span data-stu-id="a00a2-109">Initial analysis</span></span>

<span data-ttu-id="a00a2-110">深入瞭解詳細資料之前，請先查看事件的屬性與摘要。</span><span class="sxs-lookup"><span data-stu-id="a00a2-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="a00a2-111">您可以從選取 [核取記號] 欄開始選取該事件。</span><span class="sxs-lookup"><span data-stu-id="a00a2-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="a00a2-112">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="a00a2-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="從核取記號欄中選取事件的範例":::

<span data-ttu-id="a00a2-114">當您這麼做時，會開啟摘要窗格，其中會顯示事件的重要資訊（例如嚴重性），以及[MITRE ATT&CK &trade; ](https://attack.mitre.org/)類別的事件。</span><span class="sxs-lookup"><span data-stu-id="a00a2-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="a00a2-115">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="a00a2-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="事件摘要窗格的範例":::

<span data-ttu-id="a00a2-117">您可以從這裡選取 [ **開啟 incident] 頁面**。</span><span class="sxs-lookup"><span data-stu-id="a00a2-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="a00a2-118">這會開啟此事件的主頁面，您可以在此找到更多摘要資訊和索引標籤，以取得提醒、裝置、使用者、調查和證據。</span><span class="sxs-lookup"><span data-stu-id="a00a2-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="a00a2-119">您也可以從事件佇列中選取事件名稱，以開啟事件的主版頁面。</span><span class="sxs-lookup"><span data-stu-id="a00a2-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="a00a2-120">摘要</span><span class="sxs-lookup"><span data-stu-id="a00a2-120">Summary</span></span>

<span data-ttu-id="a00a2-121">[ **摘要** ] 頁面可讓您查看有關事件的最重要注意事項。</span><span class="sxs-lookup"><span data-stu-id="a00a2-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 安全中心內事件摘要頁面的範例":::

<span data-ttu-id="a00a2-123">「攻擊類別」可讓您直觀和數值的方式，顯示攻擊如何對 kill 鏈進行的進展。</span><span class="sxs-lookup"><span data-stu-id="a00a2-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="a00a2-124">與其他 Microsoft 安全性產品一樣，Microsoft 365 Defender 會對應至[MITRE ATT&CK &trade; ](https://attack.mitre.org/) framework。</span><span class="sxs-lookup"><span data-stu-id="a00a2-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="a00a2-125">範圍區段會顯示屬於此事件中影響最大的資產清單。</span><span class="sxs-lookup"><span data-stu-id="a00a2-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="a00a2-126">如果關於此資產的特定資訊，例如風險層級、調查優先順序以及資產上的任何標記，本區段也將會顯示這項資訊。</span><span class="sxs-lookup"><span data-stu-id="a00a2-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="a00a2-127">提醒時程表會提供 sneak，以即時查看警示的發生順序，以及這些警示連結至此事件的原因。</span><span class="sxs-lookup"><span data-stu-id="a00a2-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="a00a2-128">和 last-「證據」區段會摘要說明事件中包含多少不同的專案以及其修復狀態，所以您可以立即識別您是否需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="a00a2-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="a00a2-129">這項功能可讓您瞭解應注意的事件最重要特性，以協助您進行事件的初始診斷。</span><span class="sxs-lookup"><span data-stu-id="a00a2-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="a00a2-130">警示</span><span class="sxs-lookup"><span data-stu-id="a00a2-130">Alerts</span></span>

<span data-ttu-id="a00a2-131">您可以在 [ **警示** ] 索引標籤上，查看與該事件相關之警示的警示佇列及其他相關資訊，例如：</span><span class="sxs-lookup"><span data-stu-id="a00a2-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="a00a2-132">嚴重性。</span><span class="sxs-lookup"><span data-stu-id="a00a2-132">Severity.</span></span>
- <span data-ttu-id="a00a2-133">警示中所涉及的實體。</span><span class="sxs-lookup"><span data-stu-id="a00a2-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="a00a2-134">Microsoft Defender for Identity，microsoft defender for Endpoint，Microsoft defender for Office 365) 的警示來源 (。</span><span class="sxs-lookup"><span data-stu-id="a00a2-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="a00a2-135">連結在一起的原因。</span><span class="sxs-lookup"><span data-stu-id="a00a2-135">The reason they were linked together.</span></span>

<span data-ttu-id="a00a2-136">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="a00a2-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="事件提醒頁面的範例":::

<span data-ttu-id="a00a2-138">依預設，提醒會以時間順序排列，以讓您瞭解事件隨時間的播放方式。</span><span class="sxs-lookup"><span data-stu-id="a00a2-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="a00a2-139">選取每個提醒會帶您前往警示的主頁面，您可以在其中對該警示進行深入分析。</span><span class="sxs-lookup"><span data-stu-id="a00a2-139">Selecting each alert takes you to the alert's main page where you can conduct an in-depth analysis of that alert.</span></span> 

<span data-ttu-id="a00a2-140">瞭解如何在[分析提醒](investigate-alerts.md)中使用警示佇列及警示頁面</span><span class="sxs-lookup"><span data-stu-id="a00a2-140">Learn how to use the alert queue and alert pages in [analyze alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="a00a2-141">裝置</span><span class="sxs-lookup"><span data-stu-id="a00a2-141">Devices</span></span>

<span data-ttu-id="a00a2-142">[ **裝置** ] 索引標籤會列出與該事件相關的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="a00a2-142">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="a00a2-143">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="a00a2-143">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="事件的裝置頁面範例":::

<span data-ttu-id="a00a2-145">您可以選取裝置的核取記號，以查看裝置、目錄資料、作用中警示及已登入使用者的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a00a2-145">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="a00a2-146">選取裝置的名稱，以查看 Microsoft Defender for 端點裝置庫存中的裝置詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a00a2-146">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Microsoft Defender 端點的裝置頁面範例":::

<span data-ttu-id="a00a2-148">在 [裝置] 頁面上，您可以收集裝置的其他相關資訊，例如其所有警示、時程表及安全性建議。</span><span class="sxs-lookup"><span data-stu-id="a00a2-148">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="a00a2-149">例如，在 [ **時程表** ] 索引標籤中，您可以在機器時程表中向內移動，並以時間順序查看機器上所觀察到的所有事件和行為，並與所引發的警示交錯。</span><span class="sxs-lookup"><span data-stu-id="a00a2-149">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="a00a2-150">您可以在裝置頁面上執行手動掃描。</span><span class="sxs-lookup"><span data-stu-id="a00a2-150">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="a00a2-151">在 Microsoft 365 的 [安全性中心] 中，選擇 **> 裝置庫存的端點**。</span><span class="sxs-lookup"><span data-stu-id="a00a2-151">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="a00a2-152">選取具有警示的裝置，然後執行防病毒掃描。</span><span class="sxs-lookup"><span data-stu-id="a00a2-152">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="a00a2-153">在 [ **裝置庫存** ] 頁面上追蹤並顯示的動作（例如防病毒掃描）。</span><span class="sxs-lookup"><span data-stu-id="a00a2-153">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="a00a2-154">若要深入瞭解，請參閱 [在裝置上執行 Microsoft Defender 防病毒掃描](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。</span><span class="sxs-lookup"><span data-stu-id="a00a2-154">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="a00a2-155">使用者</span><span class="sxs-lookup"><span data-stu-id="a00a2-155">Users</span></span>

<span data-ttu-id="a00a2-156">[ **使用者** ] 索引標籤會列出已識別為屬於該事件或與其相關之所有使用者。</span><span class="sxs-lookup"><span data-stu-id="a00a2-156">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="a00a2-157">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="a00a2-157">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="事件的使用者頁面範例":::

<span data-ttu-id="a00a2-159">您可以為使用者選取核取記號，以查看使用者帳戶威脅、公開和連絡人資訊的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a00a2-159">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="a00a2-160">選取使用者名稱以查看其他使用者帳戶詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a00a2-160">Select the user name to see additional user account details.</span></span>

## <a name="mailboxes"></a><span data-ttu-id="a00a2-161">信箱</span><span class="sxs-lookup"><span data-stu-id="a00a2-161">Mailboxes</span></span>

<span data-ttu-id="a00a2-162">[ **信箱** ] 索引標籤會列出已識別為屬於該事件或與其相關的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="a00a2-162">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="a00a2-163">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="a00a2-163">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="事件的信箱頁面範例":::

<span data-ttu-id="a00a2-165">您可以選取信箱的核取記號，以查看作用中的警示清單。</span><span class="sxs-lookup"><span data-stu-id="a00a2-165">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="a00a2-166">選取信箱名稱，以查看 Microsoft Defender for Office 365 的 Explorer 頁面上的其他信箱詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a00a2-166">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="a00a2-167">調查</span><span class="sxs-lookup"><span data-stu-id="a00a2-167">Investigations</span></span>

<span data-ttu-id="a00a2-168">[ **調查** ] 索引標籤會列出此事件中的警示所觸發的所有自動調查。</span><span class="sxs-lookup"><span data-stu-id="a00a2-168">The **Investigations** tab lists all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="a00a2-169">調查會執行修正動作，或等候分析員的動作批准，視您如何設定自動調查以在 Microsoft Defender for Endpoint 和 Defender for Office 365 中執行。</span><span class="sxs-lookup"><span data-stu-id="a00a2-169">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="事件的調查頁面範例":::

<span data-ttu-id="a00a2-171">選取調查以瀏覽至 [調查詳細資料] 頁面，取得調查和修復狀態的完整資訊。</span><span class="sxs-lookup"><span data-stu-id="a00a2-171">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="a00a2-172">如果有任何動作出于調查的一部分而待核准，它們就會出現在 [擱置的動作] 索引標籤中。採取動作做為事件修復的一部分。</span><span class="sxs-lookup"><span data-stu-id="a00a2-172">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="a00a2-173">證據與回應</span><span class="sxs-lookup"><span data-stu-id="a00a2-173">Evidence and Response</span></span>

<span data-ttu-id="a00a2-174">[ **證據與回應** ] 索引標籤會顯示事件中的警示中所有支援的事件及可疑的實體。</span><span class="sxs-lookup"><span data-stu-id="a00a2-174">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="a00a2-175">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="a00a2-175">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="事件的證據與回應頁面範例":::

<span data-ttu-id="a00a2-177">Microsoft 365 Defender 會自動調查警示中的所有事件支援事件和可疑實體，以提供重要電子郵件、檔案、程式、服務、IP 位址等相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a00a2-177">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="a00a2-178">這可協助您快速偵測並封鎖事件中的潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="a00a2-178">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="a00a2-179">每個分析的實體都會以判定為序 (惡意、可疑、清除) 和修正狀態。</span><span class="sxs-lookup"><span data-stu-id="a00a2-179">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="a00a2-180">這可協助您瞭解整個事件的修復狀態，以及可以採取的後續步驟。</span><span class="sxs-lookup"><span data-stu-id="a00a2-180">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a00a2-181">相關主題</span><span class="sxs-lookup"><span data-stu-id="a00a2-181">Related topics</span></span>

- [<span data-ttu-id="a00a2-182">事件概觀</span><span class="sxs-lookup"><span data-stu-id="a00a2-182">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a00a2-183">設定事件優先順序</span><span class="sxs-lookup"><span data-stu-id="a00a2-183">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="a00a2-184">管理事件</span><span class="sxs-lookup"><span data-stu-id="a00a2-184">Manage incidents</span></span>](manage-incidents.md)

