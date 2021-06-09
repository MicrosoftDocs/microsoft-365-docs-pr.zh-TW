---
title: 調查 [Defender for Endpoint Devices] 清單中的裝置
description: 查看警示、網路連線資訊、新增裝置標記和群組，以及檢查服務健康情況，以調查受影響的裝置。
keywords: 裝置，標記，群組，端點，警示佇列，警示，裝置名稱，網域，最後查看的，內部 IP，作用中的警示，威脅類別，篩選，排序，檢查警示，網路，連線，類型，stealer，勒索軟體，exploit，low，low，嚴重性，服務健康情況
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e64f17f2bedea89db1190e6c758c514f14fc3a68
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843575"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="82457-104">調查 Microsoft Defender for Endpoint Devices 清單中的裝置</span><span class="sxs-lookup"><span data-stu-id="82457-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="82457-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="82457-105">**Applies to:**</span></span>
- [<span data-ttu-id="82457-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="82457-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="82457-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82457-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="82457-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="82457-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="82457-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="82457-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="82457-110">調查特定裝置上產生之警示的詳細資料，識別可能與警示或可能的破壞範圍有關的其他行為或事件。</span><span class="sxs-lookup"><span data-stu-id="82457-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="82457-111">作為調查或回應程式的一部分，您可以從裝置收集調查套件。</span><span class="sxs-lookup"><span data-stu-id="82457-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="82457-112">方法如下： [從裝置收集調查套件](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices)。</span><span class="sxs-lookup"><span data-stu-id="82457-112">Here's how: [Collect investigation package from devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="82457-113">您可以按一下 [受影響的裝置]，只要您在入口網站中看到這些裝置，即可開啟有關該裝置的詳細報告。</span><span class="sxs-lookup"><span data-stu-id="82457-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="82457-114">受影響的裝置會在下列方面加以識別：</span><span class="sxs-lookup"><span data-stu-id="82457-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="82457-115">裝置清單</span><span class="sxs-lookup"><span data-stu-id="82457-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="82457-116">警示佇列</span><span class="sxs-lookup"><span data-stu-id="82457-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="82457-117"> 安全性操作儀表板</span><span class="sxs-lookup"><span data-stu-id="82457-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="82457-118">任何個別警示</span><span class="sxs-lookup"><span data-stu-id="82457-118">Any individual alert</span></span>
- <span data-ttu-id="82457-119">任何個別檔詳細資料檢視</span><span class="sxs-lookup"><span data-stu-id="82457-119">Any individual file details view</span></span>
- <span data-ttu-id="82457-120">任何 IP 位址或網域詳細資料檢視</span><span class="sxs-lookup"><span data-stu-id="82457-120">Any IP address or domain details view</span></span>

<span data-ttu-id="82457-121">當您調查特定裝置時，您會看到：</span><span class="sxs-lookup"><span data-stu-id="82457-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="82457-122">裝置詳細資料</span><span class="sxs-lookup"><span data-stu-id="82457-122">Device details</span></span>
- <span data-ttu-id="82457-123">回應動作</span><span class="sxs-lookup"><span data-stu-id="82457-123">Response actions</span></span>
- <span data-ttu-id="82457-124">索引標籤 (概述、警示、時程表、安全性建議、軟體清查、發現的弱點、遺失的 Kb) </span><span class="sxs-lookup"><span data-stu-id="82457-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="82457-125"> (主動警示、登入的使用者、安全性評估) </span><span class="sxs-lookup"><span data-stu-id="82457-125">Cards (active alerts, logged on users, security assessment)</span></span>

![裝置視圖的影像](images/specific-device.png)

## <a name="device-details"></a><span data-ttu-id="82457-127">裝置詳細資料</span><span class="sxs-lookup"><span data-stu-id="82457-127">Device details</span></span>

<span data-ttu-id="82457-128">[裝置詳細資料] 區段提供裝置的網域、作業系統和健康狀態等資訊。</span><span class="sxs-lookup"><span data-stu-id="82457-128">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="82457-129">如果裝置上有可用的調查套件，您會看到可讓您下載套件的連結。</span><span class="sxs-lookup"><span data-stu-id="82457-129">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="82457-130">回應動作</span><span class="sxs-lookup"><span data-stu-id="82457-130">Response actions</span></span>

<span data-ttu-id="82457-131">回應動作會沿著特定裝置頁面的頂端執行，並包含：</span><span class="sxs-lookup"><span data-stu-id="82457-131">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="82457-132">管理標籤</span><span class="sxs-lookup"><span data-stu-id="82457-132">Manage tags</span></span>
- <span data-ttu-id="82457-133">隔離裝置</span><span class="sxs-lookup"><span data-stu-id="82457-133">Isolate device</span></span>
- <span data-ttu-id="82457-134">限制應用程式執行</span><span class="sxs-lookup"><span data-stu-id="82457-134">Restrict app execution</span></span>
- <span data-ttu-id="82457-135">執行防毒掃描</span><span class="sxs-lookup"><span data-stu-id="82457-135">Run antivirus scan</span></span>
- <span data-ttu-id="82457-136">收集調查套件</span><span class="sxs-lookup"><span data-stu-id="82457-136">Collect investigation package</span></span>
- <span data-ttu-id="82457-137">啟動 Live Response Session</span><span class="sxs-lookup"><span data-stu-id="82457-137">Initiate Live Response Session</span></span>
- <span data-ttu-id="82457-138">啟動自動調查</span><span class="sxs-lookup"><span data-stu-id="82457-138">Initiate automated investigation</span></span>
- <span data-ttu-id="82457-139">諮詢威脅專家</span><span class="sxs-lookup"><span data-stu-id="82457-139">Consult a threat expert</span></span>
- <span data-ttu-id="82457-140">控制中心</span><span class="sxs-lookup"><span data-stu-id="82457-140">Action center</span></span>

<span data-ttu-id="82457-141">您可以在行動中心、特定裝置頁面或特定檔案頁面中採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="82457-141">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="82457-142">如需如何對裝置採取動作的詳細資訊，請參閱 [在裝置上採取回應動作](respond-machine-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="82457-142">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="82457-143">如需詳細資訊，請參閱 [調查使用者實體](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="82457-143">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="82457-144">索引標籤</span><span class="sxs-lookup"><span data-stu-id="82457-144">Tabs</span></span>

<span data-ttu-id="82457-145">索引標籤提供與裝置相關的相關安全性和威脅防護資訊。</span><span class="sxs-lookup"><span data-stu-id="82457-145">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="82457-146">在每個索引標籤中，您可以從欄標題上方的列中選取 [ **自訂欄位** ]，以自訂所顯示的欄位。</span><span class="sxs-lookup"><span data-stu-id="82457-146">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="82457-147">概觀</span><span class="sxs-lookup"><span data-stu-id="82457-147">Overview</span></span>
<span data-ttu-id="82457-148">[ **一覽表** ] 索引標籤會顯示作用中警示、登入使用者及安全性評估的 [卡片](#cards) 。</span><span class="sxs-lookup"><span data-stu-id="82457-148">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![裝置頁面上的 [一覽影像] 索引標籤](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="82457-150">警示</span><span class="sxs-lookup"><span data-stu-id="82457-150">Alerts</span></span>

<span data-ttu-id="82457-151">[ **警示** ] 索引標籤提供與裝置相關聯的警示清單。</span><span class="sxs-lookup"><span data-stu-id="82457-151">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="82457-152">此清單是篩選的 [警示佇列](alerts-queue.md)版本，會顯示警示的簡短描述、嚴重性 (高、中、低、資訊) 、佇列中的狀態 (新的、進行中、已解決) 、分類 (未設定、false 警示、true 警示) 、調查狀態、警報類型、處理警示的人員，以及最後一個活動。</span><span class="sxs-lookup"><span data-stu-id="82457-152">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="82457-153">您也可以篩選警示。</span><span class="sxs-lookup"><span data-stu-id="82457-153">You can also filter the alerts.</span></span>

![與裝置相關的提醒影像](images/alerts-device.png)

<span data-ttu-id="82457-155">選取警示左側的圓形圖示時，會顯示飛出。</span><span class="sxs-lookup"><span data-stu-id="82457-155">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="82457-156">您可以從這個面板管理警示，並查看詳細資料，例如事件編號及相關裝置。</span><span class="sxs-lookup"><span data-stu-id="82457-156">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="82457-157">一次可選取多個提醒。</span><span class="sxs-lookup"><span data-stu-id="82457-157">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="82457-158">若要查看警示（包括事件圖形和處理樹狀目錄）的完整網頁檢視，請選取警示的標題。</span><span class="sxs-lookup"><span data-stu-id="82457-158">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="82457-159">時間表</span><span class="sxs-lookup"><span data-stu-id="82457-159">Timeline</span></span>

<span data-ttu-id="82457-160">[ **時程表** ] 索引標籤可提供在裝置上觀察到之事件及相關警示的按時間查看。</span><span class="sxs-lookup"><span data-stu-id="82457-160">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="82457-161">這可協助您關聯任何事件、檔案及 IP 位址與裝置相關聯。</span><span class="sxs-lookup"><span data-stu-id="82457-161">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="82457-162">時程表也可讓您選擇性地向下流覽至指定期間內發生的事件。</span><span class="sxs-lookup"><span data-stu-id="82457-162">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="82457-163">您可以在選取的時段內，查看裝置上發生之事件的時態順序。</span><span class="sxs-lookup"><span data-stu-id="82457-163">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="82457-164">若要進一步控制您的視圖，您可以依事件群組篩選或自訂欄位。</span><span class="sxs-lookup"><span data-stu-id="82457-164">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="82457-165">若要顯示防火牆事件，您必須啟用審核原則，請參閱「 [審核篩選平臺](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)連線」。</span><span class="sxs-lookup"><span data-stu-id="82457-165">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="82457-166">防火牆涵蓋下列事件</span><span class="sxs-lookup"><span data-stu-id="82457-166">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="82457-167">[5025](/windows/security/threat-protection/auditing/event-5025) -防火牆服務已停止</span><span class="sxs-lookup"><span data-stu-id="82457-167">[5025](/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="82457-168">[5031](/windows/security/threat-protection/auditing/event-5031) -應用程式阻止接收網路上的傳入連線</span><span class="sxs-lookup"><span data-stu-id="82457-168">[5031](/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="82457-169">[5157](/windows/security/threat-protection/auditing/event-5157) -封鎖的連線</span><span class="sxs-lookup"><span data-stu-id="82457-169">[5157](/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![具有事件的裝置時程表圖像](images/timeline-device.png)

<span data-ttu-id="82457-171">一些功能包括：</span><span class="sxs-lookup"><span data-stu-id="82457-171">Some of the functionality includes:</span></span>

- <span data-ttu-id="82457-172">搜尋特定事件</span><span class="sxs-lookup"><span data-stu-id="82457-172">Search for specific events</span></span>
  - <span data-ttu-id="82457-173">使用搜尋列尋找特定的時程表事件。</span><span class="sxs-lookup"><span data-stu-id="82457-173">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="82457-174">篩選特定日期的事件</span><span class="sxs-lookup"><span data-stu-id="82457-174">Filter events from a specific date</span></span>
  - <span data-ttu-id="82457-175">選取表格左上方的行事曆圖示，以顯示過去一天、一周、30天或自訂範圍中的事件。</span><span class="sxs-lookup"><span data-stu-id="82457-175">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="82457-176">依預設，裝置時程表會設定為顯示過去30天的事件。</span><span class="sxs-lookup"><span data-stu-id="82457-176">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="82457-177">透過高亮顯示區段，使用 [時程表] 跳到特定的時刻。</span><span class="sxs-lookup"><span data-stu-id="82457-177">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="82457-178">時程表上指出自動調查的箭號</span><span class="sxs-lookup"><span data-stu-id="82457-178">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="82457-179">匯出詳細的裝置時程表事件</span><span class="sxs-lookup"><span data-stu-id="82457-179">Export detailed device timeline events</span></span>
  - <span data-ttu-id="82457-180">匯出目前日期或指定日期範圍的裝置時程表，最多7天。</span><span class="sxs-lookup"><span data-stu-id="82457-180">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="82457-181">**其他資訊** 區段提供有關特定事件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="82457-181">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="82457-182">這些詳細資料會視事件種類而異，例如：</span><span class="sxs-lookup"><span data-stu-id="82457-182">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="82457-183">由應用程式防護所包含-web 瀏覽器事件受到隔離容器的限制</span><span class="sxs-lookup"><span data-stu-id="82457-183">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="82457-184">偵測到主動威脅-執行威脅時，發生威脅偵測</span><span class="sxs-lookup"><span data-stu-id="82457-184">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="82457-185">修正失敗-已呼叫對偵測到的威脅進行修正，但失敗</span><span class="sxs-lookup"><span data-stu-id="82457-185">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="82457-186">修正成功-已停止並清理偵測到的威脅</span><span class="sxs-lookup"><span data-stu-id="82457-186">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="82457-187">使用者略過的警告-使用者已解除 Windows Defender SmartScreen 警告，並覆寫該</span><span class="sxs-lookup"><span data-stu-id="82457-187">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="82457-188">偵測到可疑的腳本-發現可能有惡意的腳本</span><span class="sxs-lookup"><span data-stu-id="82457-188">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="82457-189">警示類別-如果事件導致警示產生，警示類別 ( 「橫向移動」，例如，) 會提供</span><span class="sxs-lookup"><span data-stu-id="82457-189">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="82457-190">事件詳細資料</span><span class="sxs-lookup"><span data-stu-id="82457-190">Event details</span></span>
<span data-ttu-id="82457-191">選取事件，以查看該事件的相關詳細資料。</span><span class="sxs-lookup"><span data-stu-id="82457-191">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="82457-192">會顯示一個窗格，顯示一般的事件資訊。</span><span class="sxs-lookup"><span data-stu-id="82457-192">A panel displays to show general event information.</span></span> <span data-ttu-id="82457-193">當可用且資料可用時，顯示相關實體及其關聯的圖形也會顯示出來。</span><span class="sxs-lookup"><span data-stu-id="82457-193">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="82457-194">若要進一步檢查事件和相關事件，您可以選擇 **尋找相關事件**，以快速執行 [高級搜尋](advanced-hunting-overview.md)查詢。</span><span class="sxs-lookup"><span data-stu-id="82457-194">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="82457-195">此查詢會傳回選取的事件，以及相同端點上同時發生之其他事件的清單。</span><span class="sxs-lookup"><span data-stu-id="82457-195">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![事件詳細資料面板的影像](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="82457-197">安全性建議</span><span class="sxs-lookup"><span data-stu-id="82457-197">Security recommendations</span></span>

<span data-ttu-id="82457-198">**安全性建議** 是由 Microsoft Defender 為端點 [威脅 & 漏洞管理](tvm-dashboard-insights.md) 功能產生。</span><span class="sxs-lookup"><span data-stu-id="82457-198">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="82457-199">選取建議會顯示一個窗格，您可以在其中查看相關的詳細資料，例如建議的描述，以及不採用此相關的潛在風險。</span><span class="sxs-lookup"><span data-stu-id="82457-199">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="82457-200">如需詳細資訊，請參閱 [安全性建議](tvm-security-recommendation.md) 。</span><span class="sxs-lookup"><span data-stu-id="82457-200">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![安全性建議的圖像] 索引標籤](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="82457-202">軟體庫存</span><span class="sxs-lookup"><span data-stu-id="82457-202">Software inventory</span></span>

<span data-ttu-id="82457-203">[ **軟體清查** ] 索引標籤可讓您在裝置上查看軟體，以及任何弱點或威脅。</span><span class="sxs-lookup"><span data-stu-id="82457-203">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="82457-204">選取軟體的名稱會帶您前往 [軟體詳細資料] 頁面，您可以在此頁面上查看安全性建議、發現的漏洞、已安裝的裝置及版本發行。</span><span class="sxs-lookup"><span data-stu-id="82457-204">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="82457-205">詳細資訊請參閱[軟體清查](tvm-software-inventory.md)</span><span class="sxs-lookup"><span data-stu-id="82457-205">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![[軟體清查] 索引標籤的影像](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="82457-207">發現的弱點</span><span class="sxs-lookup"><span data-stu-id="82457-207">Discovered vulnerabilities</span></span>

<span data-ttu-id="82457-208">[已 **發現的漏洞** ] 索引標籤會顯示裝置上已發現之弱點的名稱、嚴重性及威脅深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="82457-208">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="82457-209">選取特定的漏洞會顯示描述及詳細資料。</span><span class="sxs-lookup"><span data-stu-id="82457-209">Selecting specific vulnerabilities will show a description and details.</span></span>

![[發現的弱點] 索引標籤的影像](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="82457-211">遺失 Kb</span><span class="sxs-lookup"><span data-stu-id="82457-211">Missing KBs</span></span>
<span data-ttu-id="82457-212">[ **遺失 kb** ] 索引標籤會列出裝置缺少的安全性更新。</span><span class="sxs-lookup"><span data-stu-id="82457-212">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![遺失 kb] 索引標籤的影像](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="82457-214">卡</span><span class="sxs-lookup"><span data-stu-id="82457-214">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="82457-215">主動警示</span><span class="sxs-lookup"><span data-stu-id="82457-215">Active alerts</span></span>

<span data-ttu-id="82457-216">如果您已啟用 Microsoft Defender 身分識別功能，且有任何作用中警示， **Azure 高級威脅防護** 卡會顯示與裝置相關的警示，以及其風險層級的高層次概述。</span><span class="sxs-lookup"><span data-stu-id="82457-216">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Microsoft Defender for Identity feature, and there are any active alerts.</span></span> <span data-ttu-id="82457-217">如需詳細資訊，請流覽中的「警示」。</span><span class="sxs-lookup"><span data-stu-id="82457-217">More information is available in the "Alerts" drill down.</span></span>

![使用中警示卡的影像](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="82457-219">您必須在 Microsoft Defender for Identity 和 Defender for Endpoint 上啟用整合，才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="82457-219">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="82457-220">在 [Defender for Endpoint] 中，您可以在 [高級功能] 中啟用這項功能。</span><span class="sxs-lookup"><span data-stu-id="82457-220">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="82457-221">如需如何啟用高級功能的詳細資訊，請參閱 [開啟高級功能](advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="82457-221">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="82457-222">登入的使用者</span><span class="sxs-lookup"><span data-stu-id="82457-222">Logged on users</span></span>

<span data-ttu-id="82457-223">**登入的使用者** 卡片會顯示過去30天內已登入的使用者人數，以及最常和最少的使用者。</span><span class="sxs-lookup"><span data-stu-id="82457-223">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="82457-224">選取「查看所有使用者」連結會開啟詳細資料窗格，其中會顯示使用者類型、登入類型，以及使用者第一次查看時間等資訊。</span><span class="sxs-lookup"><span data-stu-id="82457-224">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="82457-225">如需詳細資訊，請參閱 [調查使用者實體](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="82457-225">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![使用者詳細資料窗格的影像](images/logged-on-users.png)

### <a name="security-assessments"></a><span data-ttu-id="82457-227">安全性評估</span><span class="sxs-lookup"><span data-stu-id="82457-227">Security assessments</span></span>

<span data-ttu-id="82457-228">**安全性評估** 卡會顯示整體公開階層、安全性建議、安裝的軟體，以及發現的弱點。</span><span class="sxs-lookup"><span data-stu-id="82457-228">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="82457-229">裝置的公開層級取決於其擱置的安全性建議的累計影響。</span><span class="sxs-lookup"><span data-stu-id="82457-229">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![安全性評估卡的影像](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="82457-231">相關主題</span><span class="sxs-lookup"><span data-stu-id="82457-231">Related topics</span></span>

- [<span data-ttu-id="82457-232">查看和組織 Microsoft Defender for Endpoint 警示佇列</span><span class="sxs-lookup"><span data-stu-id="82457-232">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="82457-233">管理 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="82457-233">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="82457-234">調查 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="82457-234">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="82457-235">調查與 Defender for Endpoint alert 相關聯的檔案</span><span class="sxs-lookup"><span data-stu-id="82457-235">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="82457-236">調查與 Defender for Endpoint alert 相關聯的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="82457-236">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="82457-237">調查與 Defender for Endpoint alert 相關聯的網域</span><span class="sxs-lookup"><span data-stu-id="82457-237">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="82457-238">調查 Endpoint for Endpoint 中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="82457-238">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="82457-239">安全性建議</span><span class="sxs-lookup"><span data-stu-id="82457-239">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="82457-240">軟體庫存</span><span class="sxs-lookup"><span data-stu-id="82457-240">Software inventory</span></span>](tvm-software-inventory.md)
