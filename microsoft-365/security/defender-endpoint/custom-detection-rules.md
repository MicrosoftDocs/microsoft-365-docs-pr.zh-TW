---
title: 在 Microsoft Defender ATP 中建立自訂偵測規則
ms.reviewer: ''
description: 瞭解如何根據高級搜尋查詢建立自訂偵測規則
keywords: 自訂偵測、建立、管理、警示、編輯、執行隨選即用、頻率、間隔、偵測規則、高級搜尋、搜尋、查詢、回應動作、mdatp、microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: fc4c15d2e391176ed0b4420c13fb865674da0361
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163584"
---
# <a name="create-custom-detection-rules"></a><span data-ttu-id="e4392-104">建立自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="e4392-104">Create custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e4392-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e4392-105">**Applies to:**</span></span>
- [<span data-ttu-id="e4392-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e4392-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e4392-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4392-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e4392-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e4392-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e4392-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e4392-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="e4392-110">透過 [高級搜尋](advanced-hunting-overview.md) 查詢所建立的自訂偵測規則，可讓您主動監視各種事件和系統狀態，包括可疑的入侵行為和設定不當的裝置。</span><span class="sxs-lookup"><span data-stu-id="e4392-110">Custom detection rules built from [advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="e4392-111">您可以將其設定為定期執行，並在每個專案相符時產生提醒並採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="e4392-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="e4392-112">請閱讀本文以瞭解如何建立新的自訂偵測規則。</span><span class="sxs-lookup"><span data-stu-id="e4392-112">Read this article to learn how to create new custom detection rules.</span></span> <span data-ttu-id="e4392-113">或者， [請參閱查看和管理現有的規則](custom-detections-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="e4392-113">Or [see viewing and managing existing rules](custom-detections-manage.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e4392-114">若要建立或管理自訂的偵測， [您的角色](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) 必須具有「 **管理安全性設定** 」許可權。</span><span class="sxs-lookup"><span data-stu-id="e4392-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="1-prepare-the-query"></a><span data-ttu-id="e4392-115">1. 準備查詢。</span><span class="sxs-lookup"><span data-stu-id="e4392-115">1. Prepare the query.</span></span>

<span data-ttu-id="e4392-116">在 Microsoft Defender Security Center 中，移至 [ **高級搜尋** ]，然後選取現有的查詢或建立新的查詢。</span><span class="sxs-lookup"><span data-stu-id="e4392-116">In Microsoft Defender Security Center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="e4392-117">使用新的查詢時，請執行查詢以識別錯誤，並瞭解可能的結果。</span><span class="sxs-lookup"><span data-stu-id="e4392-117">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e4392-118">若要防止服務傳回太多警示，每個規則都限制為每次執行時只產生100警示。</span><span class="sxs-lookup"><span data-stu-id="e4392-118">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="e4392-119">在建立規則之前，請先調整您的查詢，以避免正常、日常活動的警示。</span><span class="sxs-lookup"><span data-stu-id="e4392-119">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>

### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="e4392-120">查詢結果中的必要欄</span><span class="sxs-lookup"><span data-stu-id="e4392-120">Required columns in the query results</span></span>

<span data-ttu-id="e4392-121">若要使用自訂偵測規則的查詢，查詢必須傳回下列資料行：</span><span class="sxs-lookup"><span data-stu-id="e4392-121">To use a query for a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- `DeviceId`
- `ReportId`

<span data-ttu-id="e4392-122">簡單的查詢（如未使用 `project` or `summarize` 運算子自訂或匯總結果的查詢）通常會傳回這些通用欄。</span><span class="sxs-lookup"><span data-stu-id="e4392-122">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="e4392-123">有多種方式可確保更複雜的查詢傳回這些欄位。</span><span class="sxs-lookup"><span data-stu-id="e4392-123">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="e4392-124">例如，如果您想要匯總和計數 `DeviceId` ，您仍然可以傳回， `Timestamp` 並 `ReportId` 從與每個裝置相關的最近事件中取得。</span><span class="sxs-lookup"><span data-stu-id="e4392-124">For example, if you prefer to aggregate and count by `DeviceId`, you can still return `Timestamp` and `ReportId` by getting them from the most recent event involving each device.</span></span>

<span data-ttu-id="e4392-125">下列範例查詢會計算具有防病毒偵測 () 的唯一裝置數目 `DeviceId` ，並使用這種方式，只尋找具有超過五個偵測的裝置。</span><span class="sxs-lookup"><span data-stu-id="e4392-125">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this to find only those devices with more than five detections.</span></span> <span data-ttu-id="e4392-126">若要傳回最新 `Timestamp` 和對應的 `ReportId` ，它會搭配 `summarize` 函數使用運算子 `arg_max` 。</span><span class="sxs-lookup"><span data-stu-id="e4392-126">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="e4392-127">為了獲得更佳的查詢效能，請設定符合規則之預定執行頻率的時間篩選。</span><span class="sxs-lookup"><span data-stu-id="e4392-127">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="e4392-128">由於頻率最低的執行是每24小時，篩選過去一天會涵蓋所有新的資料。</span><span class="sxs-lookup"><span data-stu-id="e4392-128">Since the least frequent run is every 24 hours, filtering for the past day will cover all new data.</span></span>

## <a name="2-create-a-new-rule-and-provide-alert-details"></a><span data-ttu-id="e4392-129">2. 建立新的規則，並提供警示詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e4392-129">2. Create a new rule and provide alert details.</span></span>

<span data-ttu-id="e4392-130">使用查詢編輯器中的查詢，選取 [ **建立偵測規則** ]，並指定下列警示詳細資料：</span><span class="sxs-lookup"><span data-stu-id="e4392-130">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="e4392-131">**偵測名稱**—偵測規則的名稱</span><span class="sxs-lookup"><span data-stu-id="e4392-131">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="e4392-132">**Frequency**：執行查詢和採取動作的間隔。</span><span class="sxs-lookup"><span data-stu-id="e4392-132">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="e4392-133">請參閱以下其他指導方針</span><span class="sxs-lookup"><span data-stu-id="e4392-133">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="e4392-134">**警示標題**—顯示規則所觸發警示的標題</span><span class="sxs-lookup"><span data-stu-id="e4392-134">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="e4392-135">**嚴重性**（取決於規則所識別的元件或活動的潛在風險。</span><span class="sxs-lookup"><span data-stu-id="e4392-135">**Severity**—potential risk of the component or activity identified by the rule.</span></span> [<span data-ttu-id="e4392-136">警示嚴重性的閱讀</span><span class="sxs-lookup"><span data-stu-id="e4392-136">Read about alert severities</span></span>](alerts-queue.md#severity)
- <span data-ttu-id="e4392-137">**類別**-威脅元件或活動的類型（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="e4392-137">**Category**—type of threat component or activity, if any.</span></span> [<span data-ttu-id="e4392-138">有關警示類別的閱讀資訊</span><span class="sxs-lookup"><span data-stu-id="e4392-138">Read about alert categories</span></span>](alerts-queue.md#understanding-alert-categories)
- <span data-ttu-id="e4392-139">**MITRE ATT&CK 技術**-由規則識別的一或多個攻擊技術（如 MITRE ATT 中所述）&CK framework。</span><span class="sxs-lookup"><span data-stu-id="e4392-139">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the MITRE ATT&CK framework.</span></span> <span data-ttu-id="e4392-140">本節不適用於某些警示類別，例如惡意軟體、勒索軟體、可疑活動和不需要的軟體</span><span class="sxs-lookup"><span data-stu-id="e4392-140">This section is not available with certain alert categories, such as malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="e4392-141">**描述**-規則所識別之元件或活動的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e4392-141">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="e4392-142">**建議動作**-回應者可能會採取以回應警示的其他動作</span><span class="sxs-lookup"><span data-stu-id="e4392-142">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

<span data-ttu-id="e4392-143">如需如何顯示警示詳細資訊的詳細資訊，請 [參閱警示佇列](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="e4392-143">For more information about how alert details are displayed, [read about the alert queue](alerts-queue.md).</span></span>

### <a name="rule-frequency"></a><span data-ttu-id="e4392-144">規則頻率</span><span class="sxs-lookup"><span data-stu-id="e4392-144">Rule frequency</span></span>

<span data-ttu-id="e4392-145">儲存之後，新的自訂偵測規則會立即執行並檢查過去30天的資料是否相符。</span><span class="sxs-lookup"><span data-stu-id="e4392-145">When saved, a new custom detection rule immediately runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="e4392-146">然後，該規則會以固定間隔重新執行，並根據您所選擇的頻率 lookback 持續時間：</span><span class="sxs-lookup"><span data-stu-id="e4392-146">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="e4392-147">**每24小時**-每24小時執行一次，檢查過去30天的資料</span><span class="sxs-lookup"><span data-stu-id="e4392-147">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="e4392-148">**每12小時**-每12小時執行一次，檢查過去24小時的資料</span><span class="sxs-lookup"><span data-stu-id="e4392-148">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="e4392-149">**每3小時**，每3小時執行一次，檢查過去6個小時的資料</span><span class="sxs-lookup"><span data-stu-id="e4392-149">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="e4392-150">**每小時-每小時執行一次**，檢查過去2個小時的資料</span><span class="sxs-lookup"><span data-stu-id="e4392-150">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4392-151">變更已排定為自訂偵測的查詢時，會立即執行的後續執行將會有30天的 lookback 視窗，就像是建立新的查詢一樣。</span><span class="sxs-lookup"><span data-stu-id="e4392-151">When changing a query that is already scheduled as a Custom Detection, it's next immediate execution will have a lookback window of 30 days, exactly as if a new query was being created.</span></span> <span data-ttu-id="e4392-152">變更大量查詢，而且時間篩選器的時間篩選高於選取頻率的預設 lookback 持續時間，可能會影響高級搜尋的整體配額消耗，並導致耗盡每日配額。</span><span class="sxs-lookup"><span data-stu-id="e4392-152">Changes to a large number of queries, and with time filters higher than the default lookback duration for the selected frequency, might have an impact in the overall quota consumption of Advanced Hunting and resulting in exhausting the daily quota.</span></span>

> [!TIP]
> <span data-ttu-id="e4392-153">使查詢中的時間篩選與 lookback 持續時間相符。</span><span class="sxs-lookup"><span data-stu-id="e4392-153">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="e4392-154">Lookback 持續時間以外的結果會被忽略。</span><span class="sxs-lookup"><span data-stu-id="e4392-154">Results outside of the lookback duration are ignored.</span></span>

<span data-ttu-id="e4392-155">選取您要監視偵測的頻率，並考慮組織的容量以回應提醒。</span><span class="sxs-lookup"><span data-stu-id="e4392-155">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

## <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="e4392-156">3. 選擇受影響的實體。</span><span class="sxs-lookup"><span data-stu-id="e4392-156">3. Choose the impacted entities.</span></span>

<span data-ttu-id="e4392-157">在查詢結果中識別欄，以找出主要受影響或受影響的實體。</span><span class="sxs-lookup"><span data-stu-id="e4392-157">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="e4392-158">例如，查詢可能會傳回裝置和使用者 IDs。</span><span class="sxs-lookup"><span data-stu-id="e4392-158">For example, a query might return both device and user IDs.</span></span> <span data-ttu-id="e4392-159">識別哪些欄位代表主要受影響的實體，可協助服務匯總相關的警示、關聯事件，以及目標回應動作。</span><span class="sxs-lookup"><span data-stu-id="e4392-159">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="e4392-160">您只能為每個實體類型選取一個欄。</span><span class="sxs-lookup"><span data-stu-id="e4392-160">You can select only one column for each entity type.</span></span> <span data-ttu-id="e4392-161">無法選取查詢未傳回的資料行。</span><span class="sxs-lookup"><span data-stu-id="e4392-161">Columns that are not returned by your query can't be selected.</span></span>

## <a name="4-specify-actions"></a><span data-ttu-id="e4392-162">4. 指定動作。</span><span class="sxs-lookup"><span data-stu-id="e4392-162">4. Specify actions.</span></span>

<span data-ttu-id="e4392-163">您的自訂偵測規則可對查詢所傳回的檔案或裝置自動採取動作。</span><span class="sxs-lookup"><span data-stu-id="e4392-163">Your custom detection rule can automatically take actions on files or devices that are returned by the query.</span></span>

### <a name="actions-on-devices"></a><span data-ttu-id="e4392-164">裝置上的動作</span><span class="sxs-lookup"><span data-stu-id="e4392-164">Actions on devices</span></span>

<span data-ttu-id="e4392-165">這些動作會套用至 `DeviceId` 查詢結果欄中的裝置：</span><span class="sxs-lookup"><span data-stu-id="e4392-165">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>

- <span data-ttu-id="e4392-166">**隔離裝置**--應用完整網路隔離，以防止裝置連接至任何應用程式或服務，但不包括 Defender for Endpoint service。</span><span class="sxs-lookup"><span data-stu-id="e4392-166">**Isolate device**—applies full network isolation, preventing the device from connecting to any application or service, except for the Defender for Endpoint service.</span></span> [<span data-ttu-id="e4392-167">深入瞭解裝置隔離</span><span class="sxs-lookup"><span data-stu-id="e4392-167">Learn more about device isolation</span></span>](respond-machine-alerts.md#isolate-devices-from-the-network)
- <span data-ttu-id="e4392-168">**收集調查套件**—收集 ZIP 檔案中的裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="e4392-168">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="e4392-169">深入瞭解調查套件</span><span class="sxs-lookup"><span data-stu-id="e4392-169">Learn more about the investigation package</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- <span data-ttu-id="e4392-170">**執行防病毒掃描**-在裝置上執行完整的 Microsoft Defender 防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="e4392-170">**Run antivirus scan**—performs a full Microsoft Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="e4392-171">**開始調查**-在裝置上開始 [自動調查](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="e4392-171">**Initiate investigation**—starts an [automated investigation](automated-investigations.md) on the device</span></span>
- <span data-ttu-id="e4392-172">**限制應用程式執行**—設定裝置上的限制，只允許以 Microsoft 發行的憑證簽署的檔案執行。</span><span class="sxs-lookup"><span data-stu-id="e4392-172">**Restrict app execution**—sets restrictions on the device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="e4392-173">深入瞭解限制應用程式執行</span><span class="sxs-lookup"><span data-stu-id="e4392-173">Learn more about restricting app execution</span></span>](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a><span data-ttu-id="e4392-174">檔上的動作</span><span class="sxs-lookup"><span data-stu-id="e4392-174">Actions on files</span></span>

<span data-ttu-id="e4392-175">這些動作會套用至查詢結果的 [或] 欄中的檔案 `SHA1` `InitiatingProcessSHA1` ：</span><span class="sxs-lookup"><span data-stu-id="e4392-175">These actions are applied to files in the `SHA1` or the `InitiatingProcessSHA1` column of the query results:</span></span>

- <span data-ttu-id="e4392-176">**Allow/封鎖**-自動將檔案新增至您的 [自訂指示器清單](manage-indicators.md) ，使其永遠可以執行或封鎖執行。</span><span class="sxs-lookup"><span data-stu-id="e4392-176">**Allow/Block**—automatically adds the file to your [custom indicator list](manage-indicators.md) so that it is always allowed to run or blocked from running.</span></span> <span data-ttu-id="e4392-177">您可以設定此動作的範圍，使其只會在選取的裝置群組上加以採用。</span><span class="sxs-lookup"><span data-stu-id="e4392-177">You can set the scope of this action so that it is taken only on selected device groups.</span></span> <span data-ttu-id="e4392-178">此範圍獨立于規則的範圍。</span><span class="sxs-lookup"><span data-stu-id="e4392-178">This scope is independent of the scope of the rule.</span></span>
- <span data-ttu-id="e4392-179">**隔離** 檔-從其目前的位置刪除檔案，並將複本放入隔離區</span><span class="sxs-lookup"><span data-stu-id="e4392-179">**Quarantine file**—deletes the file from its current location and places a copy in quarantine</span></span>

### <a name="actions-on-users"></a><span data-ttu-id="e4392-180">使用者的動作</span><span class="sxs-lookup"><span data-stu-id="e4392-180">Actions on users</span></span>

- <span data-ttu-id="e4392-181">將 **使用者標示為已遭破壞**-在 Azure Active Directory 中將使用者的風險層級設定為 "high"，以觸發對應的身分 [識別保護原則](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)。</span><span class="sxs-lookup"><span data-stu-id="e4392-181">**Mark user as compromised**—sets the user's risk level to "high" in Azure Active Directory, triggering the corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels).</span></span>

## <a name="5-set-the-rule-scope"></a><span data-ttu-id="e4392-182">5. 設定規則範圍。</span><span class="sxs-lookup"><span data-stu-id="e4392-182">5. Set the rule scope.</span></span>

<span data-ttu-id="e4392-183">設定範圍以指定規則涵蓋的裝置：</span><span class="sxs-lookup"><span data-stu-id="e4392-183">Set the scope to specify which devices are covered by the rule:</span></span>

- <span data-ttu-id="e4392-184">所有裝置</span><span class="sxs-lookup"><span data-stu-id="e4392-184">All devices</span></span>
- <span data-ttu-id="e4392-185">特定裝置群組</span><span class="sxs-lookup"><span data-stu-id="e4392-185">Specific device groups</span></span>

<span data-ttu-id="e4392-186">只會查詢範圍中裝置的資料。</span><span class="sxs-lookup"><span data-stu-id="e4392-186">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="e4392-187">此外，只會對那些裝置採取動作。</span><span class="sxs-lookup"><span data-stu-id="e4392-187">Also, actions will be taken only on those devices.</span></span>

## <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="e4392-188">6. 檢查並開啟規則。</span><span class="sxs-lookup"><span data-stu-id="e4392-188">6. Review and turn on the rule.</span></span>

<span data-ttu-id="e4392-189">檢查規則之後，請選取 [ **建立** ] 以儲存該規則。</span><span class="sxs-lookup"><span data-stu-id="e4392-189">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="e4392-190">自訂偵測規則會立即執行。</span><span class="sxs-lookup"><span data-stu-id="e4392-190">The custom detection rule immediately runs.</span></span> <span data-ttu-id="e4392-191">它會以檢查相符專案的設定頻率重新執行，並產生警示和採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="e4392-191">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

<span data-ttu-id="e4392-192">您可以 [查看和管理自訂的偵測規則](custom-detections-manage.md)、檢查其先前的執行，並查看其觸發的警示。</span><span class="sxs-lookup"><span data-stu-id="e4392-192">You can [view and manage custom detection rules](custom-detections-manage.md), check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="e4392-193">您也可以根據需要執行規則，並加以修改。</span><span class="sxs-lookup"><span data-stu-id="e4392-193">You can also run a rule on demand and modify it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e4392-194">相關主題</span><span class="sxs-lookup"><span data-stu-id="e4392-194">Related topics</span></span>

- [<span data-ttu-id="e4392-195">查看及管理自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="e4392-195">View and manage custom detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="e4392-196">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="e4392-196">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="e4392-197">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="e4392-197">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e4392-198">了解進階搜捕查詢語言</span><span class="sxs-lookup"><span data-stu-id="e4392-198">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e4392-199">查看和組織提醒</span><span class="sxs-lookup"><span data-stu-id="e4392-199">View and organize alerts</span></span>](alerts-queue.md)
