---
title: Microsoft 365 security center 中的 microsoft Defender for Endpoint
description: 深入瞭解 Microsoft Defender Security Center to the Microsoft 365 Security center 中的變更
keywords: Microsoft 365 security center、OATP、MDATP、MDO、MDE、單一窗格的玻璃、混合入口網站、安全性入口網站、defender 安全性入口網站快速入門
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 03b73901512522edec7fdbc579eaf4073eed5d48
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167443"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="dc725-104">Microsoft 365 security center 中的 microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dc725-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="dc725-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="dc725-105">**Applies to:**</span></span>

- [<span data-ttu-id="dc725-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc725-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="dc725-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dc725-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="dc725-108">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dc725-108">Microsoft Defender for Office 365</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)

<span data-ttu-id="dc725-109">改進的 [Microsoft 365 安全性中心](overview-security-center.md) [https://security.microsoft.com](https://security.microsoft.com) 結合了保護、偵測、調查和回應電子郵件、共同作業、身分識別及裝置威脅的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="dc725-109">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="dc725-110">此安全中心會將現有 Microsoft 安全性入口網站的功能，包括 Microsoft Defender Security Center 和 Office 365 Security & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="dc725-110">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="dc725-111">如果您熟悉 Microsoft Defender 安全中心，本文可協助說明改進的 Microsoft 365 安全性中心中的一些變更與改進。</span><span class="sxs-lookup"><span data-stu-id="dc725-111">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="dc725-112">不過，有一些新的和更新的元素需要注意。</span><span class="sxs-lookup"><span data-stu-id="dc725-112">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="dc725-113">從過去開始， [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) 已經是 microsoft Defender 的端點。</span><span class="sxs-lookup"><span data-stu-id="dc725-113">Historically, the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="dc725-114">企業安全小組已使用它來監視及協助回應潛在的持續威脅活動或資料違例的警示。</span><span class="sxs-lookup"><span data-stu-id="dc725-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="dc725-115">為了協助減少入口網站數目，Microsoft 365 的安全性中心將會在您的 Microsoft identity、資料、裝置、應用程式和基礎結構中監控和管理安全性的家鄉。</span><span class="sxs-lookup"><span data-stu-id="dc725-115">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc725-116">您在 Microsoft 365 的安全性中心看到的內容，取決於您目前的訂閱。</span><span class="sxs-lookup"><span data-stu-id="dc725-116">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="dc725-117">例如，如果您沒有 Microsoft Defender for Office 365 的授權，則不會顯示 [電子郵件 & 協同作業] 區段。</span><span class="sxs-lookup"><span data-stu-id="dc725-117">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

<span data-ttu-id="dc725-118">請參閱改進的 Microsoft 365 安全中心： [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="dc725-118">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="dc725-119">深入瞭解好處： [Microsoft 365 安全中心概述](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="dc725-119">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="dc725-120">變更的功能</span><span class="sxs-lookup"><span data-stu-id="dc725-120">What's changed</span></span>

<span data-ttu-id="dc725-121">此表格是 Microsoft Defender 安全中心與 Microsoft 365 安全性中心之間變更的快速參考。</span><span class="sxs-lookup"><span data-stu-id="dc725-121">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="dc725-122">警示和動作</span><span class="sxs-lookup"><span data-stu-id="dc725-122">Alerts and actions</span></span>

|<span data-ttu-id="dc725-123">**適用範圍**</span><span class="sxs-lookup"><span data-stu-id="dc725-123">**Area**</span></span>  |<span data-ttu-id="dc725-124">**變更描述**</span><span class="sxs-lookup"><span data-stu-id="dc725-124">**Description of change**</span></span>  |
|---------|---------|
| [<span data-ttu-id="dc725-125">事件 & 警示</span><span class="sxs-lookup"><span data-stu-id="dc725-125">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="dc725-126">在 Microsoft 365 的 [安全性中心] 中，您可以管理所有端點、電子郵件和身分識別的事件及警示。</span><span class="sxs-lookup"><span data-stu-id="dc725-126">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="dc725-127">我們已融合經驗，以協助您更輕鬆地找到相關的事件。</span><span class="sxs-lookup"><span data-stu-id="dc725-127">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="dc725-128">如需詳細資訊，請參閱 [事件概述](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="dc725-128">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="dc725-129">狩獵</span><span class="sxs-lookup"><span data-stu-id="dc725-129">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="dc725-130">修改在 Microsoft Defender for Endpoint 中建立的自訂偵測規則，以包含身分識別和電子郵件表格，會自動將其移至 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="dc725-130">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="dc725-131">其對應的警示也會出現在 Microsoft 365 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="dc725-131">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="dc725-132">如需這些變更的詳細資訊，請參閱 [遷移自訂偵測規則](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="dc725-132">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules).</span></span> <span data-ttu-id="dc725-133">`DeviceAlertEvents`Microsoft 365 Defender 沒有提供高級搜尋的表格。</span><span class="sxs-lookup"><span data-stu-id="dc725-133">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="dc725-134">若要在 Microsoft 365 Defender 中查詢裝置特有的警示資訊，您可以使用 `AlertInfo` 和 `AlertEvidence` 表格來從一組不同的來源取得更多資訊。</span><span class="sxs-lookup"><span data-stu-id="dc725-134">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="dc725-135">在不 DeviceAlertEvents 的情況下，使用 [寫入查詢](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)製作下一個裝置相關的查詢。</span><span class="sxs-lookup"><span data-stu-id="dc725-135">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="dc725-136">行動中心</span><span class="sxs-lookup"><span data-stu-id="dc725-136">Action center</span></span>](mtp-action-center.md)    | <span data-ttu-id="dc725-137">列出遵循自動調查和修正動作所採取的擱置及已完成動作。</span><span class="sxs-lookup"><span data-stu-id="dc725-137">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="dc725-138">先前，Microsoft Defender Security Center 中的「動作中心」會列出僅對裝置執行之修正動作的擱置和完成動作，同時自動調查會列出警示和狀態。</span><span class="sxs-lookup"><span data-stu-id="dc725-138">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="dc725-139">在改進的 Microsoft 365 安全性中心，「行動中心」會將修正動作和調查集中在電子郵件、裝置和使用者上，全部都位於一個位置。</span><span class="sxs-lookup"><span data-stu-id="dc725-139">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="dc725-140">威脅分析</span><span class="sxs-lookup"><span data-stu-id="dc725-140">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="dc725-141">移至導覽列的頂端，以方便探索和使用。</span><span class="sxs-lookup"><span data-stu-id="dc725-141">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="dc725-142">現在包括端點的威脅資訊，以及電子郵件與共同作業。</span><span class="sxs-lookup"><span data-stu-id="dc725-142">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="dc725-143">端點</span><span class="sxs-lookup"><span data-stu-id="dc725-143">Endpoints</span></span>

|<span data-ttu-id="dc725-144">**適用範圍**</span><span class="sxs-lookup"><span data-stu-id="dc725-144">**Area**</span></span>  |<span data-ttu-id="dc725-145">**變更描述**</span><span class="sxs-lookup"><span data-stu-id="dc725-145">**Description of change**</span></span>  |
|---------|---------|
|<span data-ttu-id="dc725-146">搜尋</span><span class="sxs-lookup"><span data-stu-id="dc725-146">Search</span></span>   |  <span data-ttu-id="dc725-147">而不是在標題中，Microsoft Defender for Endpoint 搜尋列會在 [端點] 區段下移動。</span><span class="sxs-lookup"><span data-stu-id="dc725-147">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="dc725-148">您可以繼續搜尋裝置、檔案、使用者、URLs、IPs、弱點、軟體及建議。</span><span class="sxs-lookup"><span data-stu-id="dc725-148">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="dc725-149">儀表板</span><span class="sxs-lookup"><span data-stu-id="dc725-149">Dashboard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="dc725-150">這是您的安全性運作儀表板。</span><span class="sxs-lookup"><span data-stu-id="dc725-150">This is your security operations dashboard.</span></span> <span data-ttu-id="dc725-151">查看已觸發的主動警示數目、哪些裝置面臨危險、哪些使用者有危險，以及警示、裝置和使用者的嚴重性層級。</span><span class="sxs-lookup"><span data-stu-id="dc725-151">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="dc725-152">您也可以查看任何裝置是否有感應器問題、整體服務健康情況，以及偵測到任何未解析之警示的方式。</span><span class="sxs-lookup"><span data-stu-id="dc725-152">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="dc725-153">裝置清單</span><span class="sxs-lookup"><span data-stu-id="dc725-153">Device inventory</span></span> | <span data-ttu-id="dc725-154">無變更。</span><span class="sxs-lookup"><span data-stu-id="dc725-154">No changes.</span></span> |
|[<span data-ttu-id="dc725-155">弱點管理</span><span class="sxs-lookup"><span data-stu-id="dc725-155">Vulnerability management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="dc725-156">名稱已縮短，可放入功能窗格中。</span><span class="sxs-lookup"><span data-stu-id="dc725-156">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="dc725-157">與「威脅與弱點管理」區段相同，其下所有頁面皆為相同。</span><span class="sxs-lookup"><span data-stu-id="dc725-157">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="dc725-158">合作夥伴和 APIs</span><span class="sxs-lookup"><span data-stu-id="dc725-158">Partners and APIs</span></span> | <span data-ttu-id="dc725-159">無變更。</span><span class="sxs-lookup"><span data-stu-id="dc725-159">No changes.</span></span> |
| <span data-ttu-id="dc725-160">評估 & 教學課程</span><span class="sxs-lookup"><span data-stu-id="dc725-160">Evaluations & tutorials</span></span>    |     <span data-ttu-id="dc725-161">新的測試和學習功能。</span><span class="sxs-lookup"><span data-stu-id="dc725-161">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="dc725-162">設定管理</span><span class="sxs-lookup"><span data-stu-id="dc725-162">Configuration management</span></span>   |  <span data-ttu-id="dc725-163">無變更。</span><span class="sxs-lookup"><span data-stu-id="dc725-163">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="dc725-164">**自動調查和修正** 現在是事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="dc725-164">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="dc725-165">您可以在 [ **事件 > 調查** ] 索引標籤中查看自動調查和修正事件。</span><span class="sxs-lookup"><span data-stu-id="dc725-165">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="dc725-166">存取與報告</span><span class="sxs-lookup"><span data-stu-id="dc725-166">Access and reporting</span></span>

|<span data-ttu-id="dc725-167">**適用範圍**</span><span class="sxs-lookup"><span data-stu-id="dc725-167">**Area**</span></span>  |<span data-ttu-id="dc725-168">**變更描述**</span><span class="sxs-lookup"><span data-stu-id="dc725-168">**Description of change**</span></span>  |
|---------|---------|
| <span data-ttu-id="dc725-169">報告</span><span class="sxs-lookup"><span data-stu-id="dc725-169">Reports</span></span>  | <span data-ttu-id="dc725-170">請參閱報告中的端點和電子郵件 & 共同作業，包括威脅防護、裝置健康情況和合規性，以及易受攻擊的裝置。</span><span class="sxs-lookup"><span data-stu-id="dc725-170">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="dc725-171">健康情況</span><span class="sxs-lookup"><span data-stu-id="dc725-171">Health</span></span>  |  <span data-ttu-id="dc725-172">目前連結到 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)中的「服務健康情況」頁面。</span><span class="sxs-lookup"><span data-stu-id="dc725-172">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="dc725-173">設定</span><span class="sxs-lookup"><span data-stu-id="dc725-173">Settings</span></span> |  <span data-ttu-id="dc725-174">管理您的 Microsoft 365 安全中心設定、Microsoft 365 Defender、端點、電子郵件 & 共同作業、身分識別及裝置探索。</span><span class="sxs-lookup"><span data-stu-id="dc725-174">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="dc725-175">Microsoft 365 安全性導覽和功能</span><span class="sxs-lookup"><span data-stu-id="dc725-175">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="dc725-176">左側導覽列或快速啟動列會非常熟悉。</span><span class="sxs-lookup"><span data-stu-id="dc725-176">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="dc725-177">不過，此安全中心有一些新的和更新的元素。</span><span class="sxs-lookup"><span data-stu-id="dc725-177">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="dc725-178">事件及警示</span><span class="sxs-lookup"><span data-stu-id="dc725-178">Incidents and alerts</span></span>

<span data-ttu-id="dc725-179">在您的電子郵件、裝置和身分識別上彙集事件及警示管理。</span><span class="sxs-lookup"><span data-stu-id="dc725-179">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="dc725-180">警示頁面會將攻擊信號結合在一起，以建立警示的完整內容。</span><span class="sxs-lookup"><span data-stu-id="dc725-180">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="dc725-181">現在，新的整合體驗，讓您可以在不同的工作負載中統一查看警示。</span><span class="sxs-lookup"><span data-stu-id="dc725-181">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="dc725-182">您可以快速地會審、調查和採取有效的動作。</span><span class="sxs-lookup"><span data-stu-id="dc725-182">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="dc725-183">深入了解事件</span><span class="sxs-lookup"><span data-stu-id="dc725-183">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="dc725-184">深入瞭解管理提醒</span><span class="sxs-lookup"><span data-stu-id="dc725-184">Learn more about managing alerts</span></span>](investigate-alerts.md)

![警示和動作的 [快速啟動] 欄](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="dc725-186">狩獵</span><span class="sxs-lookup"><span data-stu-id="dc725-186">Hunting</span></span>

<span data-ttu-id="dc725-187">使用 [高級搜尋查詢](advanced-hunting-overview.md)，主動搜尋您的端點、Office 365 信箱等威脅、惡意程式碼和惡意活動。</span><span class="sxs-lookup"><span data-stu-id="dc725-187">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="dc725-188">這些功能強大的查詢可用於尋找及審閱已知和潛在威脅的威脅指示器和實體。</span><span class="sxs-lookup"><span data-stu-id="dc725-188">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="dc725-189">[自訂偵測規則](custom-detection-rules.md) 可以從先進的搜尋查詢中建立，以協助您主動留意可能表示遭到破壞活動和配置錯誤裝置的事件。</span><span class="sxs-lookup"><span data-stu-id="dc725-189">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="dc725-190">行動中心</span><span class="sxs-lookup"><span data-stu-id="dc725-190">Action center</span></span>

<span data-ttu-id="dc725-191">行動中心會顯示自動化調查和回應功能所建立的調查。</span><span class="sxs-lookup"><span data-stu-id="dc725-191">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="dc725-192">在 Microsoft 365 Defender 中，這項自動化的自我修復功能可自動回應特定事件，以協助安全性小組。</span><span class="sxs-lookup"><span data-stu-id="dc725-192">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="dc725-193">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="dc725-193">Learn more about the Action center</span></span>](mtp-action-center.md)

### <a name="threat-analytics"></a><span data-ttu-id="dc725-194">威脅分析</span><span class="sxs-lookup"><span data-stu-id="dc725-194">Threat Analytics</span></span>

<span data-ttu-id="dc725-195">從 Microsoft 安全性調查專家那裡取得威脅情報。</span><span class="sxs-lookup"><span data-stu-id="dc725-195">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="dc725-196">威脅分析可協助安全性小組更有效率面臨面臨的新威脅。</span><span class="sxs-lookup"><span data-stu-id="dc725-196">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="dc725-197">威脅分析包括：</span><span class="sxs-lookup"><span data-stu-id="dc725-197">Threat Analytics includes:</span></span>

- <span data-ttu-id="dc725-198">Microsoft Defender for Office 365 中的電子郵件相關偵測和緩解。</span><span class="sxs-lookup"><span data-stu-id="dc725-198">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="dc725-199">這除了 Microsoft Defender for Endpoint 中已提供的端點資料之外。</span><span class="sxs-lookup"><span data-stu-id="dc725-199">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="dc725-200">與威脅相關的事件檢視。</span><span class="sxs-lookup"><span data-stu-id="dc725-200">Incidents view related to the threats.</span></span>
- <span data-ttu-id="dc725-201">在報告中快速識別及使用可行動資訊的增強體驗。</span><span class="sxs-lookup"><span data-stu-id="dc725-201">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="dc725-202">您可以從 Microsoft 365 的安全性中心左上方導覽列中存取威脅分析，或是從顯示組織之主要威脅的專用儀表板卡存取。</span><span class="sxs-lookup"><span data-stu-id="dc725-202">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="dc725-203">深入瞭解如何 [使用威脅分析追蹤和回應新興威脅](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)</span><span class="sxs-lookup"><span data-stu-id="dc725-203">Learn more about how to [track and respond to emerging threats with threat analytics](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="dc725-204">端點區段</span><span class="sxs-lookup"><span data-stu-id="dc725-204">Endpoints section</span></span>

<span data-ttu-id="dc725-205">查看和管理組織中端點的安全性。</span><span class="sxs-lookup"><span data-stu-id="dc725-205">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="dc725-206">如果您已使用 Microsoft Defender 安全中心，它看起來會很熟悉。</span><span class="sxs-lookup"><span data-stu-id="dc725-206">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![端點的快速啟動列](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="dc725-208">存取與報告</span><span class="sxs-lookup"><span data-stu-id="dc725-208">Access and reports</span></span>

<span data-ttu-id="dc725-209">查看報告、變更您的設定，以及修改使用者角色。</span><span class="sxs-lookup"><span data-stu-id="dc725-209">View reports, change your settings, and modify user roles.</span></span>

![存取與報告快速啟動列](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="dc725-211">SIEM API 連接</span><span class="sxs-lookup"><span data-stu-id="dc725-211">SIEM API connections</span></span>

<span data-ttu-id="dc725-212">如果您使用 [Defender For ENDPOINT SIEM API](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)，您可以繼續執行。</span><span class="sxs-lookup"><span data-stu-id="dc725-212">If you use the [Defender for Endpoint SIEM API](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="dc725-213">我們已在 API 負載上新增連結，指向 [警示] 頁面或 Microsoft 365 安全性入口網站中的 [事件] 頁面。</span><span class="sxs-lookup"><span data-stu-id="dc725-213">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="dc725-214">新的 API 欄位包括 LinkToMTP 及 IncidentLinkToMTP。</span><span class="sxs-lookup"><span data-stu-id="dc725-214">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="dc725-215">如需詳細資訊，請參閱 [將客戶從 Microsoft Defender For 端點重新導向至 Microsoft 365 安全中心](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="dc725-215">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="dc725-216">電子郵件警示</span><span class="sxs-lookup"><span data-stu-id="dc725-216">Email alerts</span></span>

<span data-ttu-id="dc725-217">您可以繼續使用用於端點的電子郵件警示。</span><span class="sxs-lookup"><span data-stu-id="dc725-217">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="dc725-218">我們已新增電子郵件中的新連結，指向 [提醒] 頁面或 Microsoft 365 [安全性中心] 中的 [事件] 頁面。</span><span class="sxs-lookup"><span data-stu-id="dc725-218">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="dc725-219">如需詳細資訊，請參閱 [將客戶從 Microsoft Defender For 端點重新導向至 Microsoft 365 安全中心](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="dc725-219">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).</span></span>

## <a name="related-information"></a><span data-ttu-id="dc725-220">相關資訊</span><span class="sxs-lookup"><span data-stu-id="dc725-220">Related information</span></span>

- [<span data-ttu-id="dc725-221">Microsoft 365 安全性中心</span><span class="sxs-lookup"><span data-stu-id="dc725-221">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="dc725-222">Microsoft 365 security center 中的 microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dc725-222">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="dc725-223">將帳戶從 Microsoft Defender for Endpoint 重新導向至 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="dc725-223">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)
