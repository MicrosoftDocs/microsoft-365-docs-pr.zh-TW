---
title: 在 Microsoft 365 Defender 中建立及管理自訂偵測規則
description: 瞭解如何根據進位搜尋查詢建立及管理自訂偵測規則
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、自訂偵測、規則、架構、kusto、microsoft 365、Microsoft Threat Protection、RBAC、許可權、Microsoft Defender ATP
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
ms.openlocfilehash: 8c7e47e66f9e5543cc122c5b5154207cae836d2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932919"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="82642-104">建立及管理自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="82642-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="82642-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="82642-105">**Applies to:**</span></span>
- <span data-ttu-id="82642-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82642-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="82642-107">自訂偵測規則是您可以使用進一步搜尋查詢設計和 [調整](advanced-hunting-overview.md) 的規則。</span><span class="sxs-lookup"><span data-stu-id="82642-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="82642-108">這些規則可讓您主動監控各種事件和系統狀態，包括可疑的外泄活動和錯誤配置的端點。</span><span class="sxs-lookup"><span data-stu-id="82642-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="82642-109">您可以將它們設定為定期執行、產生警示，以及每當有符合專案時採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="82642-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="82642-110">管理自訂偵測功能所需的許可權</span><span class="sxs-lookup"><span data-stu-id="82642-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="82642-111">若要管理自訂偵測，您必須被指派以下其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="82642-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="82642-112">**安全性系統管理員**-擁有 [此 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 角色的使用者可以管理 Microsoft 365 安全性中心及其他入口網站和服務的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="82642-112">**Security administrator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="82642-113">**安全性運算子**-擁有 [此 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 角色的使用者可以管理警示，並擁有安全性相關功能 ，包括 Microsoft 365 安全性中心內所有資訊之全域唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="82642-113">**Security operator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="82642-114">只有在 Microsoft Defender for Endpoint 中關閉以角色為基礎的存取控制 (RBAC) ，這個角色就足以管理自訂偵測。</span><span class="sxs-lookup"><span data-stu-id="82642-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="82642-115">如果您設定了 RBAC，您還需要管理端點的Defender 安全性設定許可權。</span><span class="sxs-lookup"><span data-stu-id="82642-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="82642-116">若要管理必要的許可權，全域 **管理員可以** ：</span><span class="sxs-lookup"><span data-stu-id="82642-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="82642-117">在 **Microsoft** [365](https://admin.microsoft.com/)系統管理中心中，在角色安全性系統管理員下指派安全性系統管理員 \*\*\*\*  >  **或安全性運算子角色**。</span><span class="sxs-lookup"><span data-stu-id="82642-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="82642-118">在設定許可權角色下，檢查 Microsoft [Defender](https://securitycenter.windows.com/)資訊安全中心端點的 Microsoft Defender  >  **RBAC**  >  **設定**。</span><span class="sxs-lookup"><span data-stu-id="82642-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="82642-119">選取對應的角色以指派 **管理安全性設定** 許可權。</span><span class="sxs-lookup"><span data-stu-id="82642-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="82642-120">若要管理自訂偵測，如果已開啟 RBAC，**安全性** 運算子需要在 Microsoft Defender for Endpoint 中管理安全性設定許可權。 </span><span class="sxs-lookup"><span data-stu-id="82642-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="82642-121">建立自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="82642-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="82642-122">1. 準備查詢。</span><span class="sxs-lookup"><span data-stu-id="82642-122">1. Prepare the query.</span></span>

<span data-ttu-id="82642-123">在 Microsoft 365 資訊安全中心，請前往進位搜尋並選取現有的查詢或建立新查詢。</span><span class="sxs-lookup"><span data-stu-id="82642-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="82642-124">使用新查詢時，執行查詢以找出錯誤並瞭解可能的結果。</span><span class="sxs-lookup"><span data-stu-id="82642-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="82642-125">為了防止服務回電太多通知，每一個規則每次執行時只能產生 100 個通知。</span><span class="sxs-lookup"><span data-stu-id="82642-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="82642-126">在建立規則之前，請調整查詢，以避免收到一般日常活動的警示。</span><span class="sxs-lookup"><span data-stu-id="82642-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="82642-127">查詢結果中所需的資料行</span><span class="sxs-lookup"><span data-stu-id="82642-127">Required columns in the query results</span></span>
<span data-ttu-id="82642-128">若要建立自訂偵測規則，查詢必須返回下列資料行：</span><span class="sxs-lookup"><span data-stu-id="82642-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="82642-129">`Timestamp`—用來設定產生警示的時間戳記</span><span class="sxs-lookup"><span data-stu-id="82642-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="82642-130">`ReportId`— 啟用原始記錄的查找</span><span class="sxs-lookup"><span data-stu-id="82642-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="82642-131">識別特定裝置、使用者或信箱的下列其中一欄：</span><span class="sxs-lookup"><span data-stu-id="82642-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="82642-132">`SenderFromAddress` (信封寄件者或Return-Path位址) </span><span class="sxs-lookup"><span data-stu-id="82642-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="82642-133">`SenderMailFromAddress` (用戶端視窗顯示的寄件者) </span><span class="sxs-lookup"><span data-stu-id="82642-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="82642-134">當新資料表新增到進一步搜尋架構時，將會新增其他 [實體的支援](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="82642-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="82642-135">簡單的查詢 ，例如不使用 or 運算子來自訂或匯總結果的查詢， `project` `summarize` 通常會返回這些共同資料行。</span><span class="sxs-lookup"><span data-stu-id="82642-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="82642-136">有多種方式可確保更複雜的查詢會回回這些資料行。</span><span class="sxs-lookup"><span data-stu-id="82642-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="82642-137">例如，如果您想要根據欄下的實體匯總和計算，您仍可返回並取得與每個唯一專案有關的最近 `DeviceId` `Timestamp` `ReportId` 事件 `DeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="82642-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="82642-138">以下的範例查詢會計算具有防毒軟體偵測 () 裝置的唯一裝置數量，並使用此計數僅尋找偵測超過五個 `DeviceId` 的裝置。</span><span class="sxs-lookup"><span data-stu-id="82642-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="82642-139">若要將最新 `Timestamp` 值及對應的值 `ReportId` 退回，它會 `summarize` 將運算子與 `arg_max` 函數一併使用。</span><span class="sxs-lookup"><span data-stu-id="82642-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="82642-140">為提升查詢的顯示效果，請設定符合規則預定執行頻率的時間篩選。</span><span class="sxs-lookup"><span data-stu-id="82642-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="82642-141">由於最不常執行的時間是 _每 24 小時_，因此篩選過去一天會涵蓋所有新資料。</span><span class="sxs-lookup"><span data-stu-id="82642-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="82642-142">2. 建立新規則並提供警示詳細資料。</span><span class="sxs-lookup"><span data-stu-id="82642-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="82642-143">在查詢編輯器中查詢時，選取建立 **偵測規則** 並指定下列警示詳細資料：</span><span class="sxs-lookup"><span data-stu-id="82642-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="82642-144">**偵測名稱**-偵測規則的名稱</span><span class="sxs-lookup"><span data-stu-id="82642-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="82642-145">**頻率**—執行查詢和採取動作的間隔。</span><span class="sxs-lookup"><span data-stu-id="82642-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="82642-146">請參閱下方的其他指引</span><span class="sxs-lookup"><span data-stu-id="82642-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="82642-147">**提醒標題**-顯示由規則引發之提醒的標題</span><span class="sxs-lookup"><span data-stu-id="82642-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="82642-148">**嚴重性**-規則所識別之元件或活動的潛在風險</span><span class="sxs-lookup"><span data-stu-id="82642-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="82642-149">**類別**—規則所識別的威脅元件或活動</span><span class="sxs-lookup"><span data-stu-id="82642-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="82642-150">**MITRE ATT&CK** 技術 — 一或多個由 RULE 所識別的受攻擊技術，如 [MITRE ATT&CK 架構所記錄](https://attack.mitre.org/)。</span><span class="sxs-lookup"><span data-stu-id="82642-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="82642-151">此區段會隱藏于特定的警示類別，包括惡意攻擊、勒索軟體、可疑活動以及不想要的軟體</span><span class="sxs-lookup"><span data-stu-id="82642-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="82642-152">**描述**— 規則所識別之元件或活動詳細資訊</span><span class="sxs-lookup"><span data-stu-id="82642-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="82642-153">**建議的動作**—回應者在回應通知時可能會採取的其他動作</span><span class="sxs-lookup"><span data-stu-id="82642-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="82642-154">規則頻率</span><span class="sxs-lookup"><span data-stu-id="82642-154">Rule frequency</span></span>
<span data-ttu-id="82642-155">當您儲存或編輯新規則時，它會執行並檢查過去 30 天內的資料是否一樣。</span><span class="sxs-lookup"><span data-stu-id="82642-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="82642-156">規則接著會以固定間隔再次執行，並依據您選擇的頻率來申請回期限：</span><span class="sxs-lookup"><span data-stu-id="82642-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="82642-157">**每 24 小時** 一次 — 每 24 小時執行一次，檢查過去 30 天的資料</span><span class="sxs-lookup"><span data-stu-id="82642-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="82642-158">**每 12 小時** 一次 — 每 12 小時執行一次，檢查過去 24 小時的資料</span><span class="sxs-lookup"><span data-stu-id="82642-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="82642-159">**每 3 小時** 一次 — 每 3 小時執行一次，檢查過去 6 小時的資料</span><span class="sxs-lookup"><span data-stu-id="82642-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="82642-160">**每小時一** 次 — 每小時執行一次，檢查過去 2 小時的資料</span><span class="sxs-lookup"><span data-stu-id="82642-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="82642-161">比對查詢中的時間篩選與回省期間。</span><span class="sxs-lookup"><span data-stu-id="82642-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="82642-162">會忽略回省期間以外的結果。</span><span class="sxs-lookup"><span data-stu-id="82642-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="82642-163">選取與您要密切監控偵測的頻率一樣的頻率。</span><span class="sxs-lookup"><span data-stu-id="82642-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="82642-164">考慮貴組織回應警示的能力。</span><span class="sxs-lookup"><span data-stu-id="82642-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="82642-165">3.選擇影響實體。</span><span class="sxs-lookup"><span data-stu-id="82642-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="82642-166">在查詢結果中找出預期會受影響或受影響的主要實體的資料行。</span><span class="sxs-lookup"><span data-stu-id="82642-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="82642-167">例如，查詢可能會 (寄件者) `SenderFromAddress` `SenderMailFromAddress` 寄件者 () `RecipientEmailAddress` 位址。</span><span class="sxs-lookup"><span data-stu-id="82642-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="82642-168">識別代表主要影響實體的這些欄，可協助服務匯總相關警示、關聯事件及目標回應動作。</span><span class="sxs-lookup"><span data-stu-id="82642-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="82642-169">您僅能針對信箱、使用者或裝置 (每個實體類型選取一) 。</span><span class="sxs-lookup"><span data-stu-id="82642-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="82642-170">無法選取查詢未返回的資料行。</span><span class="sxs-lookup"><span data-stu-id="82642-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="82642-171">4. 指定動作。</span><span class="sxs-lookup"><span data-stu-id="82642-171">4. Specify actions.</span></span>
<span data-ttu-id="82642-172">您的自訂偵測規則可以針對查詢所發回的裝置、檔案或使用者自動採取動作。</span><span class="sxs-lookup"><span data-stu-id="82642-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="82642-173">裝置上的動作</span><span class="sxs-lookup"><span data-stu-id="82642-173">Actions on devices</span></span>
<span data-ttu-id="82642-174">這些動作會適用于查詢結果 `DeviceId` 欄中的裝置：</span><span class="sxs-lookup"><span data-stu-id="82642-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="82642-175">**隔離裝置**— 使用 Microsoft Defender for Endpoint 來執行完整的網路隔離，防止裝置連接到任何應用程式或服務。</span><span class="sxs-lookup"><span data-stu-id="82642-175">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="82642-176">深入瞭解 Microsoft Defender for Endpoint 電腦隔離</span><span class="sxs-lookup"><span data-stu-id="82642-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="82642-177">**收集調查套件**— 收集 ZIP 檔案中的裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="82642-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="82642-178">深入瞭解 Microsoft Defender 端點調查套件</span><span class="sxs-lookup"><span data-stu-id="82642-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="82642-179">**執行防毒掃描**- 在裝置上執行完整的 Windows Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="82642-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="82642-180">**啟動調查**- 啟動 [裝置](mtp-autoir.md) 上的自動化調查</span><span class="sxs-lookup"><span data-stu-id="82642-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="82642-181">**限制應用程式執行**— 設定裝置限制，只允許以 Microsoft 發行憑證簽署的檔案執行。</span><span class="sxs-lookup"><span data-stu-id="82642-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="82642-182">使用 Microsoft Defender for Endpoint 深入瞭解應用程式限制</span><span class="sxs-lookup"><span data-stu-id="82642-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="82642-183">對檔案執行動作</span><span class="sxs-lookup"><span data-stu-id="82642-183">Actions on files</span></span>
<span data-ttu-id="82642-184">選取時，您可以選擇對查詢結果的、、或欄中的檔案執行 `SHA1` 隔離 `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 檔案動作。</span><span class="sxs-lookup"><span data-stu-id="82642-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="82642-185">這個動作會從檔案目前的位置刪除檔案，並隔離一份檔案。</span><span class="sxs-lookup"><span data-stu-id="82642-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="82642-186">對使用者採取的動作</span><span class="sxs-lookup"><span data-stu-id="82642-186">Actions on users</span></span>
<span data-ttu-id="82642-187">選取時 **，會針對** 查詢結果的 、或欄中的使用者採取將使用者標記為已 `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` 入侵的動作。</span><span class="sxs-lookup"><span data-stu-id="82642-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="82642-188">此動作在 Azure Active Directory 中將使用者風險層級設定為「高」，並觸發對應的 [身分識別保護原則](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="82642-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="82642-189">Microsoft 365 Defender 目前不支援自訂偵測規則的允許或封鎖動作。</span><span class="sxs-lookup"><span data-stu-id="82642-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="82642-190">5. 設定規則範圍。</span><span class="sxs-lookup"><span data-stu-id="82642-190">5. Set the rule scope.</span></span>
<span data-ttu-id="82642-191">設定範圍以指定規則涵蓋哪些裝置。</span><span class="sxs-lookup"><span data-stu-id="82642-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="82642-192">檢查裝置且不影響只檢查信箱和使用者帳戶或身分身分之規則的範圍規則。</span><span class="sxs-lookup"><span data-stu-id="82642-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="82642-193">設定範圍時，您可以選取：</span><span class="sxs-lookup"><span data-stu-id="82642-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="82642-194">所有裝置</span><span class="sxs-lookup"><span data-stu-id="82642-194">All devices</span></span>
- <span data-ttu-id="82642-195">特定裝置群組</span><span class="sxs-lookup"><span data-stu-id="82642-195">Specific device groups</span></span>

<span data-ttu-id="82642-196">系統只會查詢範圍中裝置的資料。</span><span class="sxs-lookup"><span data-stu-id="82642-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="82642-197">此外，只會在那些裝置上採取動作。</span><span class="sxs-lookup"><span data-stu-id="82642-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="82642-198">6. 檢查並開啟規則。</span><span class="sxs-lookup"><span data-stu-id="82642-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="82642-199">在審查規則之後，選取建立 **以** 儲存規則。</span><span class="sxs-lookup"><span data-stu-id="82642-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="82642-200">自訂偵測規則會立即執行。</span><span class="sxs-lookup"><span data-stu-id="82642-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="82642-201">它會根據已配置的頻率再次執行，以檢查符合專案、產生警示，以及採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="82642-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="82642-202">管理現有的自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="82642-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="82642-203">您可以檢閱現有自訂偵測規則的清單、檢查先前的執行，以及檢閱規則所觸發的警示。</span><span class="sxs-lookup"><span data-stu-id="82642-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="82642-204">您也可以依需求執行規則並進行修改。</span><span class="sxs-lookup"><span data-stu-id="82642-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="82642-205">查看現有規則</span><span class="sxs-lookup"><span data-stu-id="82642-205">View existing rules</span></span>

<span data-ttu-id="82642-206">若要查看所有現有的自訂偵測規則，請流覽至 **搜尋**  >  **自訂偵測**。</span><span class="sxs-lookup"><span data-stu-id="82642-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="82642-207">此頁面會列出所有規則，並包含下列執行資訊：</span><span class="sxs-lookup"><span data-stu-id="82642-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="82642-208">**上次執行** 時 -上次執行規則時，檢查查詢是否符合並產生警示</span><span class="sxs-lookup"><span data-stu-id="82642-208">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="82642-209">**上次執行狀態**- 是否順利執行規則</span><span class="sxs-lookup"><span data-stu-id="82642-209">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="82642-210">**下一次** 執行 -下一個已排程執行</span><span class="sxs-lookup"><span data-stu-id="82642-210">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="82642-211">**狀態**-無論規則已開啟或關閉</span><span class="sxs-lookup"><span data-stu-id="82642-211">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="82642-212">查看規則詳細資料、修改規則及執行規則</span><span class="sxs-lookup"><span data-stu-id="82642-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="82642-213">若要查看自訂偵測規則完整的資訊，請前往搜尋自訂偵測，  >  然後選取規則名稱。</span><span class="sxs-lookup"><span data-stu-id="82642-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="82642-214">接著，您可以查看規則的一般資訊，包括其執行狀態和範圍資訊。</span><span class="sxs-lookup"><span data-stu-id="82642-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="82642-215">此頁面也會提供觸發警示和動作的清單。</span><span class="sxs-lookup"><span data-stu-id="82642-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="82642-216">![自訂偵測規則詳細資料頁面](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="82642-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="82642-217">*自訂偵測規則詳細資料*</span><span class="sxs-lookup"><span data-stu-id="82642-217">*Custom detection rule details*</span></span>

<span data-ttu-id="82642-218">您也可以在此頁面上對規則執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="82642-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="82642-219">**執行**- 立即執行規則。</span><span class="sxs-lookup"><span data-stu-id="82642-219">**Run**—run the rule immediately.</span></span> <span data-ttu-id="82642-220">這樣也會重設下一次執行間隔。</span><span class="sxs-lookup"><span data-stu-id="82642-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="82642-221">**編輯**- 修改規則而不變更查詢</span><span class="sxs-lookup"><span data-stu-id="82642-221">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="82642-222">**修改查詢**- 在進一步搜尋中編輯查詢</span><span class="sxs-lookup"><span data-stu-id="82642-222">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="82642-223">**開啟**  / **關閉**-啟用規則或停止其運作</span><span class="sxs-lookup"><span data-stu-id="82642-223">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="82642-224">**刪除**- 關閉並移除規則</span><span class="sxs-lookup"><span data-stu-id="82642-224">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="82642-225">查看及管理觸發警示</span><span class="sxs-lookup"><span data-stu-id="82642-225">View and manage triggered alerts</span></span>

<span data-ttu-id="82642-226">在規則詳細資料畫面 (搜尋自訂偵測 [規則名稱]) ，請前往 [觸發的警示]，其中列出由規則比對產生的  >    >  警示。 </span><span class="sxs-lookup"><span data-stu-id="82642-226">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="82642-227">選取警示以查看其詳細資訊，並採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="82642-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="82642-228">您可以設定警示的狀態和分類， (或誤) </span><span class="sxs-lookup"><span data-stu-id="82642-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="82642-229">將警示連結至事件</span><span class="sxs-lookup"><span data-stu-id="82642-229">Link the alert to an incident</span></span>
- <span data-ttu-id="82642-230">執行觸發進位搜尋警示的查詢</span><span class="sxs-lookup"><span data-stu-id="82642-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="82642-231">檢查動作</span><span class="sxs-lookup"><span data-stu-id="82642-231">Review actions</span></span>
<span data-ttu-id="82642-232">在規則詳細資料畫面 (搜尋自訂偵測 [規則名稱]) ，請前往 [觸發的動作]，其中根據規則比對結果列出  >    >  已採取的動作。 </span><span class="sxs-lookup"><span data-stu-id="82642-232">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="82642-233">若要快速查看資訊，並針對表格中的專案採取動作，請使用表格左側的選取欄 [&#10003;]。</span><span class="sxs-lookup"><span data-stu-id="82642-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="82642-234">相關主題</span><span class="sxs-lookup"><span data-stu-id="82642-234">Related topic</span></span>
- [<span data-ttu-id="82642-235">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="82642-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="82642-236">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="82642-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="82642-237">了解進階搜捕查詢語言</span><span class="sxs-lookup"><span data-stu-id="82642-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
