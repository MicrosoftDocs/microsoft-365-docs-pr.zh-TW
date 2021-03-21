---
title: 在 Microsoft 365 Defender 中建立及管理自訂偵測規則
description: 瞭解如何根據高級搜尋查詢建立及管理自訂偵測規則
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，自訂偵測，rules，schema，kusto，microsoft 365，Microsoft 威脅防護，RBAC，許可權，Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ed1eeb29119d477673bb04d9474bd38438db9fd9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928937"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="aeef9-104">建立及管理自訂的偵測規則</span><span class="sxs-lookup"><span data-stu-id="aeef9-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="aeef9-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="aeef9-105">**Applies to:**</span></span>
- <span data-ttu-id="aeef9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aeef9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="aeef9-107">自訂偵測規則是您可以使用 [高級搜尋](advanced-hunting-overview.md) 查詢進行設計和調整的規則。</span><span class="sxs-lookup"><span data-stu-id="aeef9-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="aeef9-108">這些規則可讓您主動監視各種事件和系統狀態，包括可疑的侵犯活動和設定不當的端點。</span><span class="sxs-lookup"><span data-stu-id="aeef9-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="aeef9-109">您可以將其設定為定期執行，並在每個專案相符時產生提醒並採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="aeef9-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="aeef9-110">管理自訂偵測的必要許可權</span><span class="sxs-lookup"><span data-stu-id="aeef9-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="aeef9-111">若要管理自訂偵測，您必須被指派其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="aeef9-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="aeef9-112">**安全性管理員**：具有此 [Azure Active Directory 角色](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 的使用者可以管理 Microsoft 365 安全性中心及其他入口網站和服務中的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="aeef9-112">**Security administrator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="aeef9-113">**安全操作員**-具有此 [Azure Active Directory 角色](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 的使用者可以管理提醒，並具有安全相關功能的全域唯讀許可權，包括 Microsoft 365 Security center 中的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="aeef9-113">**Security operator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="aeef9-114">只有在 Microsoft Defender for Endpoint 中關閉以角色為基礎的存取控制 (RBAC) 時，此角色才足以管理自訂偵測。</span><span class="sxs-lookup"><span data-stu-id="aeef9-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="aeef9-115">如果您已設定 RBAC，您也需要使用 Defender for Endpoint 的「 **管理安全性設定** 」許可權。</span><span class="sxs-lookup"><span data-stu-id="aeef9-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="aeef9-116">若要管理必要的許可權， **全域管理員** 可以：</span><span class="sxs-lookup"><span data-stu-id="aeef9-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="aeef9-117">在 [ **role** security admin] 底下的 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)中指派 **安全性管理員** 或 **安全性操作員** 角色  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeef9-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="aeef9-118">在 [**設定** 許可權角色] 底下的 [microsoft defender Security Center](https://securitycenter.windows.com/)中檢查 microsoft defender for Endpoint 的 RBAC 設定  >    >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aeef9-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="aeef9-119">選取對應的角色以指派「 **管理安全性設定** 」許可權。</span><span class="sxs-lookup"><span data-stu-id="aeef9-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="aeef9-120">若要管理自訂偵測，當已開啟 RBAC 時， **安全性操作員** 會需要 Microsoft Defender for Endpoint 中的「 **管理安全性設定** 」許可權。</span><span class="sxs-lookup"><span data-stu-id="aeef9-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="aeef9-121">建立自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="aeef9-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="aeef9-122">1. 準備查詢。</span><span class="sxs-lookup"><span data-stu-id="aeef9-122">1. Prepare the query.</span></span>

<span data-ttu-id="aeef9-123">在 Microsoft 365 的 [安全性中心] 中，移至 [ **高級搜尋** ]，然後選取現有的查詢或建立新的查詢。</span><span class="sxs-lookup"><span data-stu-id="aeef9-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="aeef9-124">使用新的查詢時，請執行查詢以識別錯誤，並瞭解可能的結果。</span><span class="sxs-lookup"><span data-stu-id="aeef9-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="aeef9-125">若要防止服務傳回太多警示，每個規則都限制為每次執行時只產生100警示。</span><span class="sxs-lookup"><span data-stu-id="aeef9-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="aeef9-126">在建立規則之前，請先調整您的查詢，以避免正常、日常活動的警示。</span><span class="sxs-lookup"><span data-stu-id="aeef9-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="aeef9-127">查詢結果中的必要欄</span><span class="sxs-lookup"><span data-stu-id="aeef9-127">Required columns in the query results</span></span>
<span data-ttu-id="aeef9-128">若要建立自訂偵測規則，查詢必須傳回下列資料行：</span><span class="sxs-lookup"><span data-stu-id="aeef9-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="aeef9-129">`Timestamp`-用於設定所產生警示的時間戳記</span><span class="sxs-lookup"><span data-stu-id="aeef9-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="aeef9-130">`ReportId`-啟用原始記錄的查閱</span><span class="sxs-lookup"><span data-stu-id="aeef9-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="aeef9-131">下列其中一欄可識別特定裝置、使用者或信箱：</span><span class="sxs-lookup"><span data-stu-id="aeef9-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="aeef9-132">`SenderFromAddress` (信封寄件者或 Return-Path 位址) </span><span class="sxs-lookup"><span data-stu-id="aeef9-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="aeef9-133">`SenderMailFromAddress` 電子郵件客戶程式顯示的 (寄件者位址) </span><span class="sxs-lookup"><span data-stu-id="aeef9-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="aeef9-134">當新的資料表新增至 [高級搜尋架構](advanced-hunting-schema-tables.md)時，將新增額外實體的支援。</span><span class="sxs-lookup"><span data-stu-id="aeef9-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="aeef9-135">簡單的查詢（如未使用 `project` or `summarize` 運算子自訂或匯總結果的查詢）通常會傳回這些通用欄。</span><span class="sxs-lookup"><span data-stu-id="aeef9-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="aeef9-136">有多種方式可確保更複雜的查詢傳回這些欄位。</span><span class="sxs-lookup"><span data-stu-id="aeef9-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="aeef9-137">例如，如果您想要依實體（如所示）匯總和計數 `DeviceId` ，仍然可以傳回 `Timestamp` ，並 `ReportId` 從每個唯一相關的最近事件中取得 `DeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="aeef9-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="aeef9-138">下列範例查詢計算使用防病毒偵測 () 的唯一裝置數目 `DeviceId` ，並使用此計數來找出超過五個偵測的裝置。</span><span class="sxs-lookup"><span data-stu-id="aeef9-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="aeef9-139">若要傳回最新 `Timestamp` 和對應的 `ReportId` ，它會搭配 `summarize` 函數使用運算子 `arg_max` 。</span><span class="sxs-lookup"><span data-stu-id="aeef9-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="aeef9-140">為了獲得更佳的查詢效能，請設定符合規則之預定執行頻率的時間篩選。</span><span class="sxs-lookup"><span data-stu-id="aeef9-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="aeef9-141">由於頻率最低的執行是 _每24小時_，篩選過去一天會涵蓋所有新的資料。</span><span class="sxs-lookup"><span data-stu-id="aeef9-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="aeef9-142">2. 建立新的規則，並提供警示詳細資料。</span><span class="sxs-lookup"><span data-stu-id="aeef9-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="aeef9-143">使用查詢編輯器中的查詢，選取 [ **建立偵測規則** ]，並指定下列警示詳細資料：</span><span class="sxs-lookup"><span data-stu-id="aeef9-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="aeef9-144">**偵測名稱**—偵測規則的名稱</span><span class="sxs-lookup"><span data-stu-id="aeef9-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="aeef9-145">**Frequency**：執行查詢和採取動作的間隔。</span><span class="sxs-lookup"><span data-stu-id="aeef9-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="aeef9-146">請參閱以下其他指導方針</span><span class="sxs-lookup"><span data-stu-id="aeef9-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="aeef9-147">**警示標題**—顯示規則所觸發警示的標題</span><span class="sxs-lookup"><span data-stu-id="aeef9-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="aeef9-148">**嚴重性**（由規則所識別之元件或活動的潛在風險）</span><span class="sxs-lookup"><span data-stu-id="aeef9-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="aeef9-149">**類別**：由規則識別的威脅元件或活動</span><span class="sxs-lookup"><span data-stu-id="aeef9-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="aeef9-150">**MITRE ATT&CK 技術**-由規則識別的一或多個攻擊技術（如 MITRE ATT 中所述） [&CK framework](https://attack.mitre.org/)。</span><span class="sxs-lookup"><span data-stu-id="aeef9-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="aeef9-151">此區段針對某些警示類別（包括惡意程式碼、勒索軟體、可疑活動和不需要的軟體）隱藏。</span><span class="sxs-lookup"><span data-stu-id="aeef9-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="aeef9-152">**描述**-規則所識別之元件或活動的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="aeef9-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="aeef9-153">**建議動作**-回應者可能會採取以回應警示的其他動作</span><span class="sxs-lookup"><span data-stu-id="aeef9-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="aeef9-154">規則頻率</span><span class="sxs-lookup"><span data-stu-id="aeef9-154">Rule frequency</span></span>
<span data-ttu-id="aeef9-155">當您儲存或編輯新規則時，它會執行並檢查過去30天的資料是否相符。</span><span class="sxs-lookup"><span data-stu-id="aeef9-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="aeef9-156">然後，此規則會以固定間隔重新執行，並根據您選擇的頻率套用 lookback 持續時間：</span><span class="sxs-lookup"><span data-stu-id="aeef9-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="aeef9-157">**每24小時**-每24小時執行一次，檢查過去30天的資料</span><span class="sxs-lookup"><span data-stu-id="aeef9-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="aeef9-158">**每12小時**-每12小時執行一次，檢查過去24小時的資料</span><span class="sxs-lookup"><span data-stu-id="aeef9-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="aeef9-159">**每3小時**，每3小時執行一次，檢查過去6個小時的資料</span><span class="sxs-lookup"><span data-stu-id="aeef9-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="aeef9-160">**每小時-每小時執行一次**，檢查過去2個小時的資料</span><span class="sxs-lookup"><span data-stu-id="aeef9-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="aeef9-161">使查詢中的時間篩選與 lookback 持續時間相符。</span><span class="sxs-lookup"><span data-stu-id="aeef9-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="aeef9-162">Lookback 持續時間以外的結果會被忽略。</span><span class="sxs-lookup"><span data-stu-id="aeef9-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="aeef9-163">選取頻率，以符合您要監視偵測的程度。</span><span class="sxs-lookup"><span data-stu-id="aeef9-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="aeef9-164">請考慮您組織的容量，以回應提醒。</span><span class="sxs-lookup"><span data-stu-id="aeef9-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="aeef9-165">3. 選擇受影響的實體。</span><span class="sxs-lookup"><span data-stu-id="aeef9-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="aeef9-166">在查詢結果中識別欄，以找出主要受影響或受影響的實體。</span><span class="sxs-lookup"><span data-stu-id="aeef9-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="aeef9-167">例如，查詢可能會傳回寄件者 (`SenderFromAddress` 或 `SenderMailFromAddress`) 和收件者 (`RecipientEmailAddress`) 位址。</span><span class="sxs-lookup"><span data-stu-id="aeef9-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="aeef9-168">識別哪些欄位代表主要受影響的實體，可協助服務匯總相關的警示、關聯事件，以及目標回應動作。</span><span class="sxs-lookup"><span data-stu-id="aeef9-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="aeef9-169">您只能為每個實體類型 (信箱、使用者或裝置) 選取一個資料行。</span><span class="sxs-lookup"><span data-stu-id="aeef9-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="aeef9-170">無法選取查詢未傳回的資料行。</span><span class="sxs-lookup"><span data-stu-id="aeef9-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="aeef9-171">4. 指定動作。</span><span class="sxs-lookup"><span data-stu-id="aeef9-171">4. Specify actions.</span></span>
<span data-ttu-id="aeef9-172">您的自訂偵測規則可在查詢所傳回的裝置、檔案或使用者上自動採取動作。</span><span class="sxs-lookup"><span data-stu-id="aeef9-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="aeef9-173">裝置上的動作</span><span class="sxs-lookup"><span data-stu-id="aeef9-173">Actions on devices</span></span>
<span data-ttu-id="aeef9-174">這些動作會套用至 `DeviceId` 查詢結果欄中的裝置：</span><span class="sxs-lookup"><span data-stu-id="aeef9-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="aeef9-175">**隔離裝置**—使用 Microsoft Defender for Endpoint 來套用完整網路隔離，以防止裝置連接至任何應用程式或服務。</span><span class="sxs-lookup"><span data-stu-id="aeef9-175">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="aeef9-176">深入瞭解 Microsoft Defender for Endpoint machine 隔離</span><span class="sxs-lookup"><span data-stu-id="aeef9-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="aeef9-177">**收集調查套件**—收集 ZIP 檔案中的裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="aeef9-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="aeef9-178">深入瞭解 Microsoft Defender for Endpoint 調查套件</span><span class="sxs-lookup"><span data-stu-id="aeef9-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="aeef9-179">**執行防病毒掃描**-在裝置上執行完整的 Windows Defender 防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="aeef9-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="aeef9-180">**開始調查**--在裝置上開始 [自動調查](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="aeef9-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="aeef9-181">**限制應用程式執行**—設定裝置上的限制，只允許以 Microsoft 發行的憑證簽署的檔案執行。</span><span class="sxs-lookup"><span data-stu-id="aeef9-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="aeef9-182">深入瞭解 Microsoft Defender for Endpoint 的應用程式限制</span><span class="sxs-lookup"><span data-stu-id="aeef9-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="aeef9-183">檔上的動作</span><span class="sxs-lookup"><span data-stu-id="aeef9-183">Actions on files</span></span>
<span data-ttu-id="aeef9-184">選取此選項時，您可以選擇對查詢結果的、、或欄中的檔案套用 **隔離檔** 動作 `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 。</span><span class="sxs-lookup"><span data-stu-id="aeef9-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="aeef9-185">此巨集指令會從目前的位置刪除檔案，並將複本放入隔離區。</span><span class="sxs-lookup"><span data-stu-id="aeef9-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="aeef9-186">使用者的動作</span><span class="sxs-lookup"><span data-stu-id="aeef9-186">Actions on users</span></span>
<span data-ttu-id="aeef9-187">選取此選項時，會對使用者于、或欄中的查詢結果，對使用者採取「將 **使用者標示為受損** 」動作 `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` 。</span><span class="sxs-lookup"><span data-stu-id="aeef9-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="aeef9-188">此動作會在 Azure Active Directory 中將使用者風險層級設為「高」，以觸發對應的身分 [識別保護原則](/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="aeef9-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="aeef9-189">Microsoft 365 Defender 目前不支援自訂偵測規則的 allow 或 block 動作。</span><span class="sxs-lookup"><span data-stu-id="aeef9-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="aeef9-190">5. 設定規則範圍。</span><span class="sxs-lookup"><span data-stu-id="aeef9-190">5. Set the rule scope.</span></span>
<span data-ttu-id="aeef9-191">設定範圍以指定規則涵蓋哪些裝置。</span><span class="sxs-lookup"><span data-stu-id="aeef9-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="aeef9-192">此範圍會影響檢查裝置的規則，而不會影響僅檢查信箱和使用者帳戶或身分識別的規則。</span><span class="sxs-lookup"><span data-stu-id="aeef9-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="aeef9-193">當您設定範圍時，您可以選取：</span><span class="sxs-lookup"><span data-stu-id="aeef9-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="aeef9-194">所有裝置</span><span class="sxs-lookup"><span data-stu-id="aeef9-194">All devices</span></span>
- <span data-ttu-id="aeef9-195">特定裝置群組</span><span class="sxs-lookup"><span data-stu-id="aeef9-195">Specific device groups</span></span>

<span data-ttu-id="aeef9-196">只會查詢範圍中裝置的資料。</span><span class="sxs-lookup"><span data-stu-id="aeef9-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="aeef9-197">此外，只會對那些裝置採取動作。</span><span class="sxs-lookup"><span data-stu-id="aeef9-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="aeef9-198">6. 檢查並開啟規則。</span><span class="sxs-lookup"><span data-stu-id="aeef9-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="aeef9-199">檢查規則之後，請選取 [ **建立** ] 以儲存該規則。</span><span class="sxs-lookup"><span data-stu-id="aeef9-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="aeef9-200">自訂偵測規則會立即執行。</span><span class="sxs-lookup"><span data-stu-id="aeef9-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="aeef9-201">它會以檢查相符專案的設定頻率重新執行，並產生警示和採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="aeef9-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>


>[!Important] 
><span data-ttu-id="aeef9-202">應該定期檢查自訂偵測，以取得效能和效能。</span><span class="sxs-lookup"><span data-stu-id="aeef9-202">Custom detections should be regularly reviewed for efficiency and effectiveness.</span></span> <span data-ttu-id="aeef9-203">若要確定您建立的偵測會觸發 true 警示，請遵循 [管理現有自訂偵測規則](#manage-existing-custom-detection-rules)中的步驟，以複查現有的自訂偵測。</span><span class="sxs-lookup"><span data-stu-id="aeef9-203">To make sure you are creating detections that trigger true alerts, take time to review your existing custom detections by following the steps in [Manage existing custom detection rules](#manage-existing-custom-detection-rules).</span></span> <br>  
<span data-ttu-id="aeef9-204">您可以維持對自訂偵測的 broadness 或明確程度的控制權，因此自訂偵測產生的任何 false 警示，都可能表示需要修改規則的特定參數。</span><span class="sxs-lookup"><span data-stu-id="aeef9-204">You maintain control over the broadness or specificity of your custom detections so any false alerts generated by custom detections might indicate a need to modify certain parameters of the rules.</span></span>


## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="aeef9-205">管理現有的自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="aeef9-205">Manage existing custom detection rules</span></span>
<span data-ttu-id="aeef9-206">您可以查看現有的自訂偵測規則清單，檢查其先前的執行，並查看其觸發的警示。</span><span class="sxs-lookup"><span data-stu-id="aeef9-206">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="aeef9-207">您也可以根據需要執行規則，並加以修改。</span><span class="sxs-lookup"><span data-stu-id="aeef9-207">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="aeef9-208">查看現有規則</span><span class="sxs-lookup"><span data-stu-id="aeef9-208">View existing rules</span></span>

<span data-ttu-id="aeef9-209">若要查看所有現有的自訂偵測規則，請流覽至 **搜尋**  >  **自訂** 偵測。</span><span class="sxs-lookup"><span data-stu-id="aeef9-209">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="aeef9-210">頁面會列出具有下列執行資訊的所有規則：</span><span class="sxs-lookup"><span data-stu-id="aeef9-210">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="aeef9-211">**上次執行** 時間-最後一次執行規則以檢查查詢符合專案並產生警示</span><span class="sxs-lookup"><span data-stu-id="aeef9-211">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="aeef9-212">**上次執行狀態**—是否已成功執行規則</span><span class="sxs-lookup"><span data-stu-id="aeef9-212">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="aeef9-213">**下一次執行**（下一個排程的執行）</span><span class="sxs-lookup"><span data-stu-id="aeef9-213">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="aeef9-214">**狀態**—是否已開啟或關閉規則</span><span class="sxs-lookup"><span data-stu-id="aeef9-214">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="aeef9-215">View rule details、modify rule 及 run rule</span><span class="sxs-lookup"><span data-stu-id="aeef9-215">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="aeef9-216">若要查看有關自訂偵測規則的完整資訊，請移至 **搜尋**  >  **自訂** 偵測，然後選取規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="aeef9-216">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="aeef9-217">然後您就可以查看規則的一般資訊，包括資訊的執行狀態和範圍。</span><span class="sxs-lookup"><span data-stu-id="aeef9-217">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="aeef9-218">此頁面也會提供觸發警示和動作的清單。</span><span class="sxs-lookup"><span data-stu-id="aeef9-218">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="aeef9-219">![自訂偵測規則詳細資料頁面](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="aeef9-219">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="aeef9-220">*自訂偵測規則詳細資料*</span><span class="sxs-lookup"><span data-stu-id="aeef9-220">*Custom detection rule details*</span></span>

<span data-ttu-id="aeef9-221">您也可以在此頁面上對規則採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="aeef9-221">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="aeef9-222">**Run**-立即執行規則。</span><span class="sxs-lookup"><span data-stu-id="aeef9-222">**Run**—run the rule immediately.</span></span> <span data-ttu-id="aeef9-223">這也會重設下一個執行的間隔。</span><span class="sxs-lookup"><span data-stu-id="aeef9-223">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="aeef9-224">**編輯**—修改規則但不變更查詢</span><span class="sxs-lookup"><span data-stu-id="aeef9-224">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="aeef9-225">**修改查詢**-在高級搜尋中編輯查詢</span><span class="sxs-lookup"><span data-stu-id="aeef9-225">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="aeef9-226">**開啟**  / **關閉**—啟用規則或停止執行</span><span class="sxs-lookup"><span data-stu-id="aeef9-226">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="aeef9-227">**刪除**—關閉規則並加以移除</span><span class="sxs-lookup"><span data-stu-id="aeef9-227">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="aeef9-228">查看及管理觸發的警示</span><span class="sxs-lookup"><span data-stu-id="aeef9-228">View and manage triggered alerts</span></span>

<span data-ttu-id="aeef9-229">在 [規則詳細資料] 畫面中 (**搜尋**  >  **自訂** 偵測  >  **[規則名稱]**) 中，移至 [**觸發警示**]，其中會列出與規則相符所產生的警示。</span><span class="sxs-lookup"><span data-stu-id="aeef9-229">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="aeef9-230">選取警示以查看與其相關的詳細資訊，並採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="aeef9-230">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="aeef9-231">透過設定其狀態和分類 (true 或 false 警示來管理提醒) </span><span class="sxs-lookup"><span data-stu-id="aeef9-231">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="aeef9-232">將警示連結到事件</span><span class="sxs-lookup"><span data-stu-id="aeef9-232">Link the alert to an incident</span></span>
- <span data-ttu-id="aeef9-233">在高級搜尋中執行觸發警示的查詢</span><span class="sxs-lookup"><span data-stu-id="aeef9-233">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="aeef9-234">審閱動作</span><span class="sxs-lookup"><span data-stu-id="aeef9-234">Review actions</span></span>
<span data-ttu-id="aeef9-235">在 [規則詳細資料] 畫面中 (**搜尋**  >  **自訂** 偵測  >  **[規則名稱]**) 中，移至 [**觸發的動作**]，其中會根據符合規則的相符，列出所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="aeef9-235">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="aeef9-236">若要快速查看資訊，並對表格中的專案採取動作，請使用表格左邊的選取範圍欄 [&#10003;]。</span><span class="sxs-lookup"><span data-stu-id="aeef9-236">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="aeef9-237">另請參閱</span><span class="sxs-lookup"><span data-stu-id="aeef9-237">See also</span></span>
- [<span data-ttu-id="aeef9-238">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="aeef9-238">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="aeef9-239">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="aeef9-239">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="aeef9-240">了解進階搜捕查詢語言</span><span class="sxs-lookup"><span data-stu-id="aeef9-240">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="aeef9-241">從 Microsoft Defender for Endpoint 遷移高級搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="aeef9-241">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mdatp.md)