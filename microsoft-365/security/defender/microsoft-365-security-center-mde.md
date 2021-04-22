---
title: Microsoft 365 security center 中的 microsoft Defender for Endpoint
description: 深入瞭解 Microsoft Defender Security Center to the Microsoft 365 Security center 中的變更
keywords: Microsoft 365 security center 快速入門，Microsoft Defender for Office 365，Microsoft Defender for Endpoint，MDO，MDE，單一窗格的玻璃，融合入口網站，安全性入口網站，Defender 安全性入口網站
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: bad31160bb27c79f672ddd28a5fced3bf8c2ee1b
ms.sourcegitcommit: 682ed2c4e2bc6979025cdb89094866cef6c8751a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51943038"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="9e53f-104">Microsoft 365 security center 中的 microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9e53f-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9e53f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9e53f-105">**Applies to:**</span></span>

- [<span data-ttu-id="9e53f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e53f-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="9e53f-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9e53f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9e53f-108">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9e53f-108">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)

<span data-ttu-id="9e53f-109">改進的 [Microsoft 365 安全性中心](overview-security-center.md) [https://security.microsoft.com](https://security.microsoft.com) 結合了保護、偵測、調查和回應電子郵件、共同作業、身分識別及裝置威脅的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="9e53f-109">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="9e53f-110">此安全中心會將現有 Microsoft 安全性入口網站的功能，包括 Microsoft Defender Security Center 和 Office 365 Security & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="9e53f-110">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="9e53f-111">如果您熟悉 Microsoft Defender 安全中心，本文可協助說明改進的 Microsoft 365 安全性中心中的一些變更與改進。</span><span class="sxs-lookup"><span data-stu-id="9e53f-111">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="9e53f-112">不過，有一些新的和更新的元素需要注意。</span><span class="sxs-lookup"><span data-stu-id="9e53f-112">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="9e53f-113">從過去開始， [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) 已經是 microsoft Defender 的端點。</span><span class="sxs-lookup"><span data-stu-id="9e53f-113">Historically, the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9e53f-114">企業安全小組已使用它來監視及協助回應潛在的持續威脅活動或資料違例的警示。</span><span class="sxs-lookup"><span data-stu-id="9e53f-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="9e53f-115">為了協助減少入口網站數目，Microsoft 365 的安全性中心將會在您的 Microsoft identity、資料、裝置、應用程式和基礎結構中監控和管理安全性的家鄉。</span><span class="sxs-lookup"><span data-stu-id="9e53f-115">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="9e53f-116">Microsoft 365 security center 中的 microsoft Defender for Endpoint [可將受管理的安全性服務提供者的存取權授與受管理的安全性服務提供者 (MSSPs) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) ，方式 [是在 Microsoft Defender security center 中授與存取權](mssp-access.md)。</span><span class="sxs-lookup"><span data-stu-id="9e53f-116">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="9e53f-117">您在 Microsoft 365 的安全性中心看到的內容，取決於您目前的訂閱。</span><span class="sxs-lookup"><span data-stu-id="9e53f-117">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="9e53f-118">例如，如果您沒有 Microsoft Defender for Office 365 的授權，則不會顯示 [電子郵件 & 協同作業] 區段。</span><span class="sxs-lookup"><span data-stu-id="9e53f-118">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

>[!Note]
><span data-ttu-id="9e53f-119">無法使用新的整合入口網站：</span><span class="sxs-lookup"><span data-stu-id="9e53f-119">The new unified portal is not available for:</span></span>
>- <span data-ttu-id="9e53f-120">美國政府社區雲端 (GCC) </span><span class="sxs-lookup"><span data-stu-id="9e53f-120">US Government Community Cloud (GCC)</span></span>
>- <span data-ttu-id="9e53f-121">美國政府社區雲端高 (GCC 高) </span><span class="sxs-lookup"><span data-stu-id="9e53f-121">US Government Community Cloud High (GCC High)</span></span>
>- <span data-ttu-id="9e53f-122">美國國防部</span><span class="sxs-lookup"><span data-stu-id="9e53f-122">US Department of Defense</span></span>
>- <span data-ttu-id="9e53f-123">具有商業授權的所有美國政府機構</span><span class="sxs-lookup"><span data-stu-id="9e53f-123">All US government institutions with commercial licenses</span></span>

<span data-ttu-id="9e53f-124">請參閱改進的 Microsoft 365 安全中心： [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="9e53f-124">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="9e53f-125">深入了解優點：[Microsoft 365 安全性中心的概觀](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="9e53f-125">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="9e53f-126">變更的項目</span><span class="sxs-lookup"><span data-stu-id="9e53f-126">What's changed</span></span>

<span data-ttu-id="9e53f-127">此表格是 Microsoft Defender 安全中心與 Microsoft 365 安全性中心之間變更的快速參考。</span><span class="sxs-lookup"><span data-stu-id="9e53f-127">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="9e53f-128">警示和動作</span><span class="sxs-lookup"><span data-stu-id="9e53f-128">Alerts and actions</span></span>

|<span data-ttu-id="9e53f-129">**區域**</span><span class="sxs-lookup"><span data-stu-id="9e53f-129">**Area**</span></span>  |<span data-ttu-id="9e53f-130">**變更的描述**</span><span class="sxs-lookup"><span data-stu-id="9e53f-130">**Description of change**</span></span> |
|---------|---------|
| [<span data-ttu-id="9e53f-131">事件 & 警示</span><span class="sxs-lookup"><span data-stu-id="9e53f-131">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="9e53f-132">在 Microsoft 365 的 [安全性中心] 中，您可以管理所有端點、電子郵件和身分識別的事件及警示。</span><span class="sxs-lookup"><span data-stu-id="9e53f-132">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="9e53f-133">我們已融合經驗，以協助您更輕鬆地找到相關的事件。</span><span class="sxs-lookup"><span data-stu-id="9e53f-133">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="9e53f-134">如需詳細資訊，請參閱 [事件概述](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9e53f-134">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="9e53f-135">搜捕</span><span class="sxs-lookup"><span data-stu-id="9e53f-135">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="9e53f-136">修改在 Microsoft Defender for Endpoint 中建立的自訂偵測規則，以包含身分識別和電子郵件表格，會自動將其移至 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="9e53f-136">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="9e53f-137">其對應的警示也會出現在 Microsoft 365 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="9e53f-137">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="9e53f-138">如需這些變更的詳細資訊，請參閱 [遷移自訂偵測規則](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="9e53f-138">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules).</span></span> <br><br><span data-ttu-id="9e53f-139">`DeviceAlertEvents`Microsoft 365 Defender 沒有提供高級搜尋的表格。</span><span class="sxs-lookup"><span data-stu-id="9e53f-139">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="9e53f-140">若要在 Microsoft 365 Defender 中查詢裝置特有的警示資訊，您可以使用 `AlertInfo` 和 `AlertEvidence` 表格來從一組不同的來源取得更多資訊。</span><span class="sxs-lookup"><span data-stu-id="9e53f-140">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="9e53f-141">在不 DeviceAlertEvents 的情況下，使用 [寫入查詢](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)製作下一個裝置相關的查詢。</span><span class="sxs-lookup"><span data-stu-id="9e53f-141">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="9e53f-142">控制中心</span><span class="sxs-lookup"><span data-stu-id="9e53f-142">Action center</span></span>](m365d-action-center.md)    | <span data-ttu-id="9e53f-143">列出遵循自動調查和修正動作所採取的擱置及已完成動作。</span><span class="sxs-lookup"><span data-stu-id="9e53f-143">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="9e53f-144">先前，Microsoft Defender Security Center 中的「動作中心」會列出僅對裝置執行之修正動作的擱置和完成動作，同時自動調查會列出警示和狀態。</span><span class="sxs-lookup"><span data-stu-id="9e53f-144">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="9e53f-145">在改進的 Microsoft 365 安全性中心，「行動中心」會將修正動作和調查集中在電子郵件、裝置和使用者上，全部都位於一個位置。</span><span class="sxs-lookup"><span data-stu-id="9e53f-145">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="9e53f-146">威脅分析</span><span class="sxs-lookup"><span data-stu-id="9e53f-146">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="9e53f-147">移至導覽列的頂端，以方便探索和使用。</span><span class="sxs-lookup"><span data-stu-id="9e53f-147">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="9e53f-148">現在包括端點的威脅資訊，以及電子郵件與共同作業。</span><span class="sxs-lookup"><span data-stu-id="9e53f-148">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="9e53f-149">端點</span><span class="sxs-lookup"><span data-stu-id="9e53f-149">Endpoints</span></span>

|<span data-ttu-id="9e53f-150">**區域**</span><span class="sxs-lookup"><span data-stu-id="9e53f-150">**Area**</span></span>  |<span data-ttu-id="9e53f-151">**變更的描述**</span><span class="sxs-lookup"><span data-stu-id="9e53f-151">**Description of change**</span></span>  |
|---------|---------|
|<span data-ttu-id="9e53f-152">搜尋</span><span class="sxs-lookup"><span data-stu-id="9e53f-152">Search</span></span>   |  <span data-ttu-id="9e53f-153">而不是在標題中，Microsoft Defender for Endpoint 搜尋列會在 [端點] 區段下移動。</span><span class="sxs-lookup"><span data-stu-id="9e53f-153">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="9e53f-154">您可以繼續搜尋裝置、檔案、使用者、URLs、IPs、弱點、軟體及建議。</span><span class="sxs-lookup"><span data-stu-id="9e53f-154">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="9e53f-155">儀表板</span><span class="sxs-lookup"><span data-stu-id="9e53f-155">Dashboard</span></span>](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="9e53f-156">這是您的安全性運作儀表板。</span><span class="sxs-lookup"><span data-stu-id="9e53f-156">This is your security operations dashboard.</span></span> <span data-ttu-id="9e53f-157">查看已觸發的主動警示數目、哪些裝置面臨危險、哪些使用者有危險，以及警示、裝置和使用者的嚴重性層級。</span><span class="sxs-lookup"><span data-stu-id="9e53f-157">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="9e53f-158">您也可以查看任何裝置是否有感應器問題、整體服務健康情況，以及偵測到任何未解析之警示的方式。</span><span class="sxs-lookup"><span data-stu-id="9e53f-158">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="9e53f-159">裝置清單</span><span class="sxs-lookup"><span data-stu-id="9e53f-159">Device inventory</span></span> | <span data-ttu-id="9e53f-160">無變更。</span><span class="sxs-lookup"><span data-stu-id="9e53f-160">No changes.</span></span> |
|[<span data-ttu-id="9e53f-161">弱點管理</span><span class="sxs-lookup"><span data-stu-id="9e53f-161">Vulnerability management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="9e53f-162">名稱已縮短，可放入功能窗格中。</span><span class="sxs-lookup"><span data-stu-id="9e53f-162">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="9e53f-163">與「威脅與弱點管理」區段相同，其下所有頁面皆為相同。</span><span class="sxs-lookup"><span data-stu-id="9e53f-163">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="9e53f-164">合作夥伴和 APIs</span><span class="sxs-lookup"><span data-stu-id="9e53f-164">Partners and APIs</span></span> | <span data-ttu-id="9e53f-165">無變更。</span><span class="sxs-lookup"><span data-stu-id="9e53f-165">No changes.</span></span> |
| <span data-ttu-id="9e53f-166">評估 & 教學課程</span><span class="sxs-lookup"><span data-stu-id="9e53f-166">Evaluations & tutorials</span></span>    |     <span data-ttu-id="9e53f-167">新的測試和學習功能。</span><span class="sxs-lookup"><span data-stu-id="9e53f-167">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="9e53f-168">設定管理</span><span class="sxs-lookup"><span data-stu-id="9e53f-168">Configuration management</span></span>   |  <span data-ttu-id="9e53f-169">無變更。</span><span class="sxs-lookup"><span data-stu-id="9e53f-169">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="9e53f-170">**自動調查和修正** 現在是事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="9e53f-170">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="9e53f-171">您可以在 [ **事件 > 調查** ] 索引標籤中查看自動調查和修正事件。</span><span class="sxs-lookup"><span data-stu-id="9e53f-171">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

> [!TIP]
> <span data-ttu-id="9e53f-172">裝置搜尋會從端點 > 搜尋中完成。</span><span class="sxs-lookup"><span data-stu-id="9e53f-172">Device search is done from Endpoints > Search.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="9e53f-173">存取與報告</span><span class="sxs-lookup"><span data-stu-id="9e53f-173">Access and reporting</span></span>

|<span data-ttu-id="9e53f-174">**區域**</span><span class="sxs-lookup"><span data-stu-id="9e53f-174">**Area**</span></span>  |<span data-ttu-id="9e53f-175">**變更的描述**</span><span class="sxs-lookup"><span data-stu-id="9e53f-175">**Description of change**</span></span>  |
|---------|---------|
| <span data-ttu-id="9e53f-176">報告</span><span class="sxs-lookup"><span data-stu-id="9e53f-176">Reports</span></span>  | <span data-ttu-id="9e53f-177">請參閱報告中的端點和電子郵件 & 共同作業，包括威脅防護、裝置健康情況和合規性，以及易受攻擊的裝置。</span><span class="sxs-lookup"><span data-stu-id="9e53f-177">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="9e53f-178">健康情況</span><span class="sxs-lookup"><span data-stu-id="9e53f-178">Health</span></span>  |  <span data-ttu-id="9e53f-179">目前連結到 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)中的「服務健康情況」頁面。</span><span class="sxs-lookup"><span data-stu-id="9e53f-179">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="9e53f-180">設定</span><span class="sxs-lookup"><span data-stu-id="9e53f-180">Settings</span></span> |  <span data-ttu-id="9e53f-181">管理您的 Microsoft 365 安全中心設定、Microsoft 365 Defender、端點、電子郵件 & 共同作業、身分識別及裝置探索。</span><span class="sxs-lookup"><span data-stu-id="9e53f-181">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="9e53f-182">Microsoft 365 安全性導覽和功能</span><span class="sxs-lookup"><span data-stu-id="9e53f-182">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="9e53f-183">左側瀏覽或快速啟動列看起來會很熟悉。</span><span class="sxs-lookup"><span data-stu-id="9e53f-183">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="9e53f-184">不過，此安全性中心有一些新的和更新的元素。</span><span class="sxs-lookup"><span data-stu-id="9e53f-184">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="9e53f-185">事件和警示</span><span class="sxs-lookup"><span data-stu-id="9e53f-185">Incidents and alerts</span></span>

<span data-ttu-id="9e53f-186">將橫跨電子郵件、裝置和身分識別的事件和警示管理結合在一起。</span><span class="sxs-lookup"><span data-stu-id="9e53f-186">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="9e53f-187">警示頁面會將攻擊信號結合在一起，以建立警示的完整內容。</span><span class="sxs-lookup"><span data-stu-id="9e53f-187">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="9e53f-188">全新、整合的體驗現在將不同工作負載的警示結合在一致的檢視中。</span><span class="sxs-lookup"><span data-stu-id="9e53f-188">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="9e53f-189">您可以快速分類、調查並採取有效動作。</span><span class="sxs-lookup"><span data-stu-id="9e53f-189">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="9e53f-190">深入了解事件</span><span class="sxs-lookup"><span data-stu-id="9e53f-190">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="9e53f-191">深入了解管理警示</span><span class="sxs-lookup"><span data-stu-id="9e53f-191">Learn more about managing alerts</span></span>](investigate-alerts.md)

![警示與動作快速啟動列](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="9e53f-193">搜捕</span><span class="sxs-lookup"><span data-stu-id="9e53f-193">Hunting</span></span>

<span data-ttu-id="9e53f-194">使用[進階搜捕查詢](advanced-hunting-overview.md)來主動搜尋端點、Office 365 信箱等的威脅、惡意程式碼和惡意活動。</span><span class="sxs-lookup"><span data-stu-id="9e53f-194">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="9e53f-195">這些功能強大的查詢可用於尋找及審閱已知和潛在威脅的威脅指示器和實體。</span><span class="sxs-lookup"><span data-stu-id="9e53f-195">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="9e53f-196">[自訂偵測規則](custom-detection-rules.md) 可以從先進的搜尋查詢中建立，以協助您主動留意可能表示遭到破壞活動和配置錯誤裝置的事件。</span><span class="sxs-lookup"><span data-stu-id="9e53f-196">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="9e53f-197">控制中心</span><span class="sxs-lookup"><span data-stu-id="9e53f-197">Action center</span></span>

<span data-ttu-id="9e53f-198">控制中心會顯示已由自動化調查及回應功能所建立的調查。</span><span class="sxs-lookup"><span data-stu-id="9e53f-198">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="9e53f-199">Microsoft 365 Defender 中的這個自動化、自我修復功能會透過自動回應特定事件來協助安全性小組。</span><span class="sxs-lookup"><span data-stu-id="9e53f-199">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="9e53f-200">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="9e53f-200">Learn more about the Action center</span></span>](m365d-action-center.md)

### <a name="threat-analytics"></a><span data-ttu-id="9e53f-201">威脅分析</span><span class="sxs-lookup"><span data-stu-id="9e53f-201">Threat Analytics</span></span>

<span data-ttu-id="9e53f-202">從專業的 Microsoft 安全性研究工具取得威脅情報。</span><span class="sxs-lookup"><span data-stu-id="9e53f-202">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="9e53f-203">威脅分析可協助安全性小組在面對新興威脅時更有效率。</span><span class="sxs-lookup"><span data-stu-id="9e53f-203">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="9e53f-204">威脅分析包括：</span><span class="sxs-lookup"><span data-stu-id="9e53f-204">Threat Analytics includes:</span></span>

- <span data-ttu-id="9e53f-205">適用於 Office 365 的 Microsoft Defender 的電子郵件相關偵測和緩和措施。</span><span class="sxs-lookup"><span data-stu-id="9e53f-205">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9e53f-206">這是已可透過適用於端點的 Microsoft Defender 取得的端點資料的增加項目。</span><span class="sxs-lookup"><span data-stu-id="9e53f-206">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="9e53f-207">與威脅相關的事件檢視。</span><span class="sxs-lookup"><span data-stu-id="9e53f-207">Incidents view related to the threats.</span></span>
- <span data-ttu-id="9e53f-208">用於快速識別及使用報告中可採取動作資訊的增強體驗。</span><span class="sxs-lookup"><span data-stu-id="9e53f-208">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="9e53f-209">您可以從 Microsoft 365 的安全性中心左上方導覽列中存取威脅分析，或是從顯示組織之主要威脅的專用儀表板卡存取。</span><span class="sxs-lookup"><span data-stu-id="9e53f-209">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="9e53f-210">深入了解如何[使用威脅分析來追蹤和回應新興威脅](./threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="9e53f-210">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md)</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="9e53f-211">端點區段</span><span class="sxs-lookup"><span data-stu-id="9e53f-211">Endpoints section</span></span>

<span data-ttu-id="9e53f-212">查看和管理組織中端點的安全性。</span><span class="sxs-lookup"><span data-stu-id="9e53f-212">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="9e53f-213">如果您已使用 Microsoft Defender 安全中心，它看起來會很熟悉。</span><span class="sxs-lookup"><span data-stu-id="9e53f-213">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![端點的快速啟動列](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="9e53f-215">存取與報告</span><span class="sxs-lookup"><span data-stu-id="9e53f-215">Access and reports</span></span>

<span data-ttu-id="9e53f-216">檢視報告、變更您的設定，以及修改使用者角色。</span><span class="sxs-lookup"><span data-stu-id="9e53f-216">View reports, change your settings, and modify user roles.</span></span>

![存取與報告快速啟動列](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="9e53f-218">SIEM API 連接</span><span class="sxs-lookup"><span data-stu-id="9e53f-218">SIEM API connections</span></span>

<span data-ttu-id="9e53f-219">如果您使用 [Defender For ENDPOINT SIEM API](../defender-endpoint/enable-siem-integration.md)，您可以繼續執行。</span><span class="sxs-lookup"><span data-stu-id="9e53f-219">If you use the [Defender for Endpoint SIEM API](../defender-endpoint/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="9e53f-220">我們已在 API 負載上新增連結，指向 [警示] 頁面或 Microsoft 365 安全性入口網站中的 [事件] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9e53f-220">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="9e53f-221">新的 API 欄位包括 LinkToMTP 及 IncidentLinkToMTP。</span><span class="sxs-lookup"><span data-stu-id="9e53f-221">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="9e53f-222">如需詳細資訊，請參閱 [將客戶從 Microsoft Defender For 端點重新導向至 Microsoft 365 安全中心](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="9e53f-222">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="9e53f-223">電子郵件警示</span><span class="sxs-lookup"><span data-stu-id="9e53f-223">Email alerts</span></span>

<span data-ttu-id="9e53f-224">您可以繼續使用用於端點的電子郵件警示。</span><span class="sxs-lookup"><span data-stu-id="9e53f-224">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="9e53f-225">我們已新增電子郵件中的新連結，指向 [提醒] 頁面或 Microsoft 365 [安全性中心] 中的 [事件] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9e53f-225">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="9e53f-226">如需詳細資訊，請參閱 [將客戶從 Microsoft Defender For 端點重新導向至 Microsoft 365 安全中心](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="9e53f-226">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

## <a name="related-information"></a><span data-ttu-id="9e53f-227">相關資訊</span><span class="sxs-lookup"><span data-stu-id="9e53f-227">Related information</span></span>

- [<span data-ttu-id="9e53f-228">Microsoft 365 安全性中心</span><span class="sxs-lookup"><span data-stu-id="9e53f-228">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="9e53f-229">Microsoft 365 security center 中的 microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9e53f-229">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="9e53f-230">將帳戶從 Microsoft Defender for Endpoint 重新導向至 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="9e53f-230">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)