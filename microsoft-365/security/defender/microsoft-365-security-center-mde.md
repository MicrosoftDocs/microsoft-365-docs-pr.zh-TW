---
title: Microsoft 365 security center 中的 Microsoft Defender for Endpoint
description: 深入瞭解 Microsoft Defender 資訊安全中心的 Microsoft 365 安全性中心的變更
keywords: 開始使用「Microsoft 365 安全性中心」、microsoft defender for Office 365、microsoft defender for Endpoint、MDO、MDE、單一窗格的玻璃、混合入口網站、安全性入口網站、Defender 安全性入口網站
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
ms.openlocfilehash: 487fc87c613d7321e3ae608097d98d2c90f8874e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771906"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="eb938-104">Microsoft 365 security center 中的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eb938-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="eb938-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="eb938-105">**Applies to:**</span></span>

- [<span data-ttu-id="eb938-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb938-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="eb938-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="eb938-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eb938-108">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="eb938-108">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a><span data-ttu-id="eb938-109">快速參考</span><span class="sxs-lookup"><span data-stu-id="eb938-109">Quick reference</span></span>

<span data-ttu-id="eb938-110">下圖列出在 Microsoft Defender 資訊安全中心和 Microsoft 365 安全中心之間的導覽變更。</span><span class="sxs-lookup"><span data-stu-id="eb938-110">The image and the table below lists the changes in navigation between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eb938-111">![移至何處的影像](../../media/mde-m3d-security-center.png)</span><span class="sxs-lookup"><span data-stu-id="eb938-111">![Image of what moved to where](../../media/mde-m3d-security-center.png)</span></span>

| <span data-ttu-id="eb938-112">Microsoft Defender 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="eb938-112">Microsoft Defender Security Center</span></span> | <span data-ttu-id="eb938-113">Microsoft 365 安全性中心</span><span class="sxs-lookup"><span data-stu-id="eb938-113">Microsoft 365 security center</span></span> |
|---------|---------|
| <span data-ttu-id="eb938-114">儀錶 板</span><span class="sxs-lookup"><span data-stu-id="eb938-114">Dashboards</span></span> <ul><li><span data-ttu-id="eb938-115">安全性作業</span><span class="sxs-lookup"><span data-stu-id="eb938-115">Security Operations</span></span></li><li><span data-ttu-id="eb938-116">威脅分析</span><span class="sxs-lookup"><span data-stu-id="eb938-116">Threat Analytics</span></span></li></ul>  |<span data-ttu-id="eb938-117">首頁</span><span class="sxs-lookup"><span data-stu-id="eb938-117">Home</span></span> <ul><li><span data-ttu-id="eb938-118">威脅分析</span><span class="sxs-lookup"><span data-stu-id="eb938-118">Threat analytics</span></span></li></ul>   |
| <span data-ttu-id="eb938-119">事件</span><span class="sxs-lookup"><span data-stu-id="eb938-119">Incidents</span></span> | <span data-ttu-id="eb938-120">事件 & 警示</span><span class="sxs-lookup"><span data-stu-id="eb938-120">Incidents & alerts</span></span> |
| <span data-ttu-id="eb938-121">裝置清單</span><span class="sxs-lookup"><span data-stu-id="eb938-121">Device inventory</span></span> | <span data-ttu-id="eb938-122">裝置清單</span><span class="sxs-lookup"><span data-stu-id="eb938-122">Device inventory</span></span> |
| <span data-ttu-id="eb938-123">警示佇列</span><span class="sxs-lookup"><span data-stu-id="eb938-123">Alerts queue</span></span> | <span data-ttu-id="eb938-124">事件 & 警示</span><span class="sxs-lookup"><span data-stu-id="eb938-124">Incidents & alerts</span></span> |
| <span data-ttu-id="eb938-125">自動化調查</span><span class="sxs-lookup"><span data-stu-id="eb938-125">Automated investigations</span></span> | <span data-ttu-id="eb938-126">控制中心</span><span class="sxs-lookup"><span data-stu-id="eb938-126">Action center</span></span> |
| <span data-ttu-id="eb938-127">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="eb938-127">Advanced hunting</span></span> | <span data-ttu-id="eb938-128">搜捕</span><span class="sxs-lookup"><span data-stu-id="eb938-128">Hunting</span></span> |
| <span data-ttu-id="eb938-129">報告</span><span class="sxs-lookup"><span data-stu-id="eb938-129">Reports</span></span> | <span data-ttu-id="eb938-130">報告</span><span class="sxs-lookup"><span data-stu-id="eb938-130">Reports</span></span> |
| <span data-ttu-id="eb938-131">合作夥伴 & APIs</span><span class="sxs-lookup"><span data-stu-id="eb938-131">Partners & APIs</span></span> | <span data-ttu-id="eb938-132">合作夥伴 & APIs</span><span class="sxs-lookup"><span data-stu-id="eb938-132">Partners & APIs</span></span> |
| <span data-ttu-id="eb938-133">威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="eb938-133">Threat & Vulnerability Management</span></span> | <span data-ttu-id="eb938-134">弱點管理</span><span class="sxs-lookup"><span data-stu-id="eb938-134">Vulnerability management</span></span> |
| <span data-ttu-id="eb938-135">評估與示教</span><span class="sxs-lookup"><span data-stu-id="eb938-135">Evaluation and tutorials</span></span> | <span data-ttu-id="eb938-136">評估 & 教學課程</span><span class="sxs-lookup"><span data-stu-id="eb938-136">Evaluation & tutorials</span></span> |
| <span data-ttu-id="eb938-137">設定管理</span><span class="sxs-lookup"><span data-stu-id="eb938-137">Configuration management</span></span> | <span data-ttu-id="eb938-138">設定管理</span><span class="sxs-lookup"><span data-stu-id="eb938-138">Configuration management</span></span> |
| <span data-ttu-id="eb938-139">設定</span><span class="sxs-lookup"><span data-stu-id="eb938-139">Settings</span></span> | <span data-ttu-id="eb938-140">設定</span><span class="sxs-lookup"><span data-stu-id="eb938-140">Settings</span></span> | 

<span data-ttu-id="eb938-141">改良的[Microsoft 365 安全性中心](overview-security-center.md) [https://security.microsoft.com](https://security.microsoft.com) 結合了保護、偵測、調查和回應電子郵件、共同作業、身分識別及裝置威脅的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="eb938-141">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="eb938-142">此安全中心會將現有 Microsoft 安全性入口網站的功能彙集在一起，包括 Microsoft Defender 資訊安全中心和 Office 365 安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="eb938-142">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="eb938-143">如果您熟悉 Microsoft Defender 資訊安全中心，本文會協助說明改進的 Microsoft 365 安全性中心的一些變更與改進。</span><span class="sxs-lookup"><span data-stu-id="eb938-143">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="eb938-144">不過，有一些新的和更新的元素需要注意。</span><span class="sxs-lookup"><span data-stu-id="eb938-144">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="eb938-145">從過去開始， [Microsoft Defender 資訊安全中心](/windows/security/threat-protection/microsoft-defender-atp/portal-overview)是 Microsoft Defender for Endpoint 的主版。</span><span class="sxs-lookup"><span data-stu-id="eb938-145">Historically, the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="eb938-146">Enterprise 安全小組已使用它監視及協助回應潛在的持續威脅活動或資料違例的警示。</span><span class="sxs-lookup"><span data-stu-id="eb938-146">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="eb938-147">為了協助減少入口網站數目，Microsoft 365 的安全性中心會在您的 Microsoft 身分識別、資料、裝置、應用程式和基礎結構之間進行監視和管理安全性的家鄉。</span><span class="sxs-lookup"><span data-stu-id="eb938-147">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="eb938-148">Microsoft 365 security center 中的 Microsoft Defender for Endpoint[可將受管理的安全性服務提供者 (MSSPs) 的存取](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)權[授與 Microsoft defender security center](mssp-access.md)中的相同存取方式。</span><span class="sxs-lookup"><span data-stu-id="eb938-148">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="eb938-149">您在「Microsoft 365 安全性中心」所看到的專案取決於您目前的訂閱。</span><span class="sxs-lookup"><span data-stu-id="eb938-149">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="eb938-150">例如，如果您沒有用於 Office 365 的 Microsoft Defender 授權，則不會顯示電子郵件 & 協同作業區段。</span><span class="sxs-lookup"><span data-stu-id="eb938-150">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

>[!Note]
><span data-ttu-id="eb938-151">無法使用新的整合入口網站：</span><span class="sxs-lookup"><span data-stu-id="eb938-151">The new unified portal is not available for:</span></span>
>- <span data-ttu-id="eb938-152">我們政府社群雲端 (GCC) </span><span class="sxs-lookup"><span data-stu-id="eb938-152">US Government Community Cloud (GCC)</span></span>
>- <span data-ttu-id="eb938-153">GCC 高) ，我們政府社群雲端高 (</span><span class="sxs-lookup"><span data-stu-id="eb938-153">US Government Community Cloud High (GCC High)</span></span>
>- <span data-ttu-id="eb938-154">美國國防部</span><span class="sxs-lookup"><span data-stu-id="eb938-154">US Department of Defense</span></span>
>- <span data-ttu-id="eb938-155">具有商業授權的所有美國政府機構</span><span class="sxs-lookup"><span data-stu-id="eb938-155">All US government institutions with commercial licenses</span></span>

<span data-ttu-id="eb938-156">請參閱改良的 Microsoft 365 安全性中心： [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="eb938-156">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="eb938-157">深入了解優點：[Microsoft 365 安全性中心的概觀](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="eb938-157">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="eb938-158">變更的項目</span><span class="sxs-lookup"><span data-stu-id="eb938-158">What's changed</span></span>

<span data-ttu-id="eb938-159">此表格是 Microsoft Defender 資訊安全中心與 Microsoft 365 安全中心之間的變更的快速參考。</span><span class="sxs-lookup"><span data-stu-id="eb938-159">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="eb938-160">警示和動作</span><span class="sxs-lookup"><span data-stu-id="eb938-160">Alerts and actions</span></span>

| <span data-ttu-id="eb938-161">區域</span><span class="sxs-lookup"><span data-stu-id="eb938-161">Area</span></span> | <span data-ttu-id="eb938-162">變更描述</span><span class="sxs-lookup"><span data-stu-id="eb938-162">Description of change</span></span> |
|---------|---------|
| [<span data-ttu-id="eb938-163">事件 & 警示</span><span class="sxs-lookup"><span data-stu-id="eb938-163">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="eb938-164">在 Microsoft 365 的安全性中心內，您可以管理所有端點、電子郵件及身分識別的事件和警示。</span><span class="sxs-lookup"><span data-stu-id="eb938-164">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="eb938-165">我們已融合經驗，以協助您更輕鬆地找到相關的事件。</span><span class="sxs-lookup"><span data-stu-id="eb938-165">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="eb938-166">如需詳細資訊，請參閱 [事件概述](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="eb938-166">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="eb938-167">搜捕</span><span class="sxs-lookup"><span data-stu-id="eb938-167">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="eb938-168">修改在 Microsoft Defender for Endpoint 中建立的自訂偵測規則，以包含身分識別和電子郵件表格，會自動將其移至 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="eb938-168">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="eb938-169">其對應的提醒也會出現在 Microsoft 365 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="eb938-169">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="eb938-170">如需這些變更的詳細資訊，請參閱 [遷移自訂偵測規則](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="eb938-170">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules).</span></span> <br><br><span data-ttu-id="eb938-171">`DeviceAlertEvents`Microsoft 365 Defender 中無法使用「高級搜尋」表格。</span><span class="sxs-lookup"><span data-stu-id="eb938-171">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="eb938-172">若要在 Microsoft 365 Defender 中查詢裝置特有的警示資訊，您可以使用 `AlertInfo` 和 `AlertEvidence` 表格來從一組不同的來源取得更多資訊。</span><span class="sxs-lookup"><span data-stu-id="eb938-172">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="eb938-173">在不 DeviceAlertEvents 的情況下，使用 [寫入查詢](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)製作下一個裝置相關的查詢。</span><span class="sxs-lookup"><span data-stu-id="eb938-173">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="eb938-174">控制中心</span><span class="sxs-lookup"><span data-stu-id="eb938-174">Action center</span></span>](m365d-action-center.md)    | <span data-ttu-id="eb938-175">列出遵循自動調查和修正動作所採取的擱置及已完成動作。</span><span class="sxs-lookup"><span data-stu-id="eb938-175">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="eb938-176">先前，Microsoft Defender 資訊安全中心中的行動中心是針對裝置上所執行的修復動作和已完成的動作列出，而且自動調查會列出警示和狀態。</span><span class="sxs-lookup"><span data-stu-id="eb938-176">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="eb938-177">在 [改進的 Microsoft 365 安全性中心] 中，行動中心會將修正動作和調查集中在電子郵件、裝置和使用者上，全部都位於一個位置。</span><span class="sxs-lookup"><span data-stu-id="eb938-177">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="eb938-178">威脅分析</span><span class="sxs-lookup"><span data-stu-id="eb938-178">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="eb938-179">移至導覽列的頂端，以方便探索和使用。</span><span class="sxs-lookup"><span data-stu-id="eb938-179">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="eb938-180">現在包括端點的威脅資訊，以及電子郵件與共同作業。</span><span class="sxs-lookup"><span data-stu-id="eb938-180">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="eb938-181">端點</span><span class="sxs-lookup"><span data-stu-id="eb938-181">Endpoints</span></span>

| <span data-ttu-id="eb938-182">區域</span><span class="sxs-lookup"><span data-stu-id="eb938-182">Area</span></span> | <span data-ttu-id="eb938-183">變更描述</span><span class="sxs-lookup"><span data-stu-id="eb938-183">Description of change</span></span> |
|---------|---------|
|<span data-ttu-id="eb938-184">搜尋</span><span class="sxs-lookup"><span data-stu-id="eb938-184">Search</span></span>   |  <span data-ttu-id="eb938-185">而不是在標題中，Microsoft Defender for Endpoint 搜尋列會在 [端點] 區段下移動。</span><span class="sxs-lookup"><span data-stu-id="eb938-185">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="eb938-186">您可以繼續搜尋裝置、檔案、使用者、URLs、IPs、弱點、軟體及建議。</span><span class="sxs-lookup"><span data-stu-id="eb938-186">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="eb938-187">儀表板</span><span class="sxs-lookup"><span data-stu-id="eb938-187">Dashboard</span></span>](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="eb938-188">這是您的安全性運作儀表板。</span><span class="sxs-lookup"><span data-stu-id="eb938-188">This is your security operations dashboard.</span></span> <span data-ttu-id="eb938-189">查看已觸發的主動警示數目、哪些裝置面臨危險、哪些使用者有危險，以及警示、裝置和使用者的嚴重性層級。</span><span class="sxs-lookup"><span data-stu-id="eb938-189">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="eb938-190">您也可以查看任何裝置是否有感應器問題、整體服務健康情況，以及偵測到任何未解析之警示的方式。</span><span class="sxs-lookup"><span data-stu-id="eb938-190">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="eb938-191">裝置清單</span><span class="sxs-lookup"><span data-stu-id="eb938-191">Device inventory</span></span> | <span data-ttu-id="eb938-192">無變更。</span><span class="sxs-lookup"><span data-stu-id="eb938-192">No changes.</span></span> |
|[<span data-ttu-id="eb938-193">弱點管理</span><span class="sxs-lookup"><span data-stu-id="eb938-193">Vulnerability management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="eb938-194">名稱已縮短，可放入功能窗格中。</span><span class="sxs-lookup"><span data-stu-id="eb938-194">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="eb938-195">其與威脅與弱點管理區段相同，所有頁面都位於下方。</span><span class="sxs-lookup"><span data-stu-id="eb938-195">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="eb938-196">合作夥伴和 APIs</span><span class="sxs-lookup"><span data-stu-id="eb938-196">Partners and APIs</span></span> | <span data-ttu-id="eb938-197">無變更。</span><span class="sxs-lookup"><span data-stu-id="eb938-197">No changes.</span></span> |
| <span data-ttu-id="eb938-198">評估 & 教學課程</span><span class="sxs-lookup"><span data-stu-id="eb938-198">Evaluations & tutorials</span></span>    |     <span data-ttu-id="eb938-199">新的測試和學習功能。</span><span class="sxs-lookup"><span data-stu-id="eb938-199">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="eb938-200">設定管理</span><span class="sxs-lookup"><span data-stu-id="eb938-200">Configuration management</span></span>   |  <span data-ttu-id="eb938-201">無變更。</span><span class="sxs-lookup"><span data-stu-id="eb938-201">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="eb938-202">**自動調查和修正** 現在是事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="eb938-202">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="eb938-203">您可以在 [ **事件 > 調查** ] 索引標籤中查看自動調查和修正事件。</span><span class="sxs-lookup"><span data-stu-id="eb938-203">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

> [!TIP]
> <span data-ttu-id="eb938-204">裝置搜尋會從端點 > 搜尋中完成。</span><span class="sxs-lookup"><span data-stu-id="eb938-204">Device search is done from Endpoints > Search.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="eb938-205">存取與報告</span><span class="sxs-lookup"><span data-stu-id="eb938-205">Access and reporting</span></span>

| <span data-ttu-id="eb938-206">區域</span><span class="sxs-lookup"><span data-stu-id="eb938-206">Area</span></span> | <span data-ttu-id="eb938-207">變更描述</span><span class="sxs-lookup"><span data-stu-id="eb938-207">Description of change</span></span> |
|---------|---------|
| <span data-ttu-id="eb938-208">報告</span><span class="sxs-lookup"><span data-stu-id="eb938-208">Reports</span></span>  | <span data-ttu-id="eb938-209">請參閱報告中的端點和電子郵件 & 共同作業，包括威脅防護、裝置健康情況和合規性，以及易受攻擊的裝置。</span><span class="sxs-lookup"><span data-stu-id="eb938-209">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="eb938-210">健康情況</span><span class="sxs-lookup"><span data-stu-id="eb938-210">Health</span></span>  |  <span data-ttu-id="eb938-211">目前[Microsoft 365 系統管理中心](https://admin.microsoft.com/)的「服務健康情況」頁面連結。</span><span class="sxs-lookup"><span data-stu-id="eb938-211">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="eb938-212">設定</span><span class="sxs-lookup"><span data-stu-id="eb938-212">Settings</span></span> |  <span data-ttu-id="eb938-213">管理 Microsoft 365 安全性中心的設定、Microsoft 365 Defender、端點、電子郵件 & 共同作業、身分識別及裝置探索。</span><span class="sxs-lookup"><span data-stu-id="eb938-213">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="eb938-214">Microsoft 365 安全性導覽和功能</span><span class="sxs-lookup"><span data-stu-id="eb938-214">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="eb938-215">左側瀏覽或快速啟動列看起來會很熟悉。</span><span class="sxs-lookup"><span data-stu-id="eb938-215">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="eb938-216">不過，此安全性中心有一些新的和更新的元素。</span><span class="sxs-lookup"><span data-stu-id="eb938-216">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="eb938-217">事件和警示</span><span class="sxs-lookup"><span data-stu-id="eb938-217">Incidents and alerts</span></span>

<span data-ttu-id="eb938-218">將橫跨電子郵件、裝置和身分識別的事件和警示管理結合在一起。</span><span class="sxs-lookup"><span data-stu-id="eb938-218">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="eb938-219">警示頁面會將攻擊信號結合在一起，以建立警示的完整內容。</span><span class="sxs-lookup"><span data-stu-id="eb938-219">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="eb938-220">全新、整合的體驗現在將不同工作負載的警示結合在一致的檢視中。</span><span class="sxs-lookup"><span data-stu-id="eb938-220">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="eb938-221">您可以快速分類、調查並採取有效動作。</span><span class="sxs-lookup"><span data-stu-id="eb938-221">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="eb938-222">深入了解事件</span><span class="sxs-lookup"><span data-stu-id="eb938-222">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="eb938-223">深入了解管理警示</span><span class="sxs-lookup"><span data-stu-id="eb938-223">Learn more about managing alerts</span></span>](investigate-alerts.md)

![警示與動作快速啟動列](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="eb938-225">搜捕</span><span class="sxs-lookup"><span data-stu-id="eb938-225">Hunting</span></span>

<span data-ttu-id="eb938-226">使用[進階搜捕查詢](advanced-hunting-overview.md)來主動搜尋端點、Office 365 信箱等的威脅、惡意程式碼和惡意活動。</span><span class="sxs-lookup"><span data-stu-id="eb938-226">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="eb938-227">這些功能強大的查詢可用於尋找及審閱已知和潛在威脅的威脅指示器和實體。</span><span class="sxs-lookup"><span data-stu-id="eb938-227">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="eb938-228">[自訂偵測規則](custom-detection-rules.md) 可以從先進的搜尋查詢中建立，以協助您主動留意可能表示遭到破壞活動和配置錯誤裝置的事件。</span><span class="sxs-lookup"><span data-stu-id="eb938-228">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="eb938-229">控制中心</span><span class="sxs-lookup"><span data-stu-id="eb938-229">Action center</span></span>

<span data-ttu-id="eb938-230">控制中心會顯示已由自動化調查及回應功能所建立的調查。</span><span class="sxs-lookup"><span data-stu-id="eb938-230">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="eb938-231">Microsoft 365 Defender 中的這個自動化、自我修復功能會透過自動回應特定事件來協助安全性小組。</span><span class="sxs-lookup"><span data-stu-id="eb938-231">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

<span data-ttu-id="eb938-232">[深入瞭解行動中心](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="eb938-232">[Learn more about the Action center](m365d-action-center.md).</span></span>

### <a name="threat-analytics"></a><span data-ttu-id="eb938-233">威脅分析</span><span class="sxs-lookup"><span data-stu-id="eb938-233">Threat Analytics</span></span>

<span data-ttu-id="eb938-234">從專業的 Microsoft 安全性研究工具取得威脅情報。</span><span class="sxs-lookup"><span data-stu-id="eb938-234">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="eb938-235">威脅分析可協助安全性小組在面對新興威脅時更有效率。</span><span class="sxs-lookup"><span data-stu-id="eb938-235">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="eb938-236">威脅分析包括：</span><span class="sxs-lookup"><span data-stu-id="eb938-236">Threat Analytics includes:</span></span>

- <span data-ttu-id="eb938-237">適用於 Office 365 的 Microsoft Defender 的電子郵件相關偵測和緩和措施。</span><span class="sxs-lookup"><span data-stu-id="eb938-237">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="eb938-238">這是已可透過適用於端點的 Microsoft Defender 取得的端點資料的增加項目。</span><span class="sxs-lookup"><span data-stu-id="eb938-238">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="eb938-239">與威脅相關的事件檢視。</span><span class="sxs-lookup"><span data-stu-id="eb938-239">Incidents view related to the threats.</span></span>
- <span data-ttu-id="eb938-240">用於快速識別及使用報告中可採取動作資訊的增強體驗。</span><span class="sxs-lookup"><span data-stu-id="eb938-240">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="eb938-241">您可以從 Microsoft 365 security center 的左上方導覽列中存取威脅分析，或是從顯示組織之主要威脅的專用儀表板卡存取。</span><span class="sxs-lookup"><span data-stu-id="eb938-241">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="eb938-242">深入瞭解如何 [使用威脅分析追蹤和回應新興威脅](./threat-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="eb938-242">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md).</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="eb938-243">端點區段</span><span class="sxs-lookup"><span data-stu-id="eb938-243">Endpoints section</span></span>

<span data-ttu-id="eb938-244">查看和管理組織中端點的安全性。</span><span class="sxs-lookup"><span data-stu-id="eb938-244">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="eb938-245">如果您已使用 Microsoft Defender 資訊安全中心，它看起來會很熟悉。</span><span class="sxs-lookup"><span data-stu-id="eb938-245">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![端點的快速啟動列](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="eb938-247">存取與報告</span><span class="sxs-lookup"><span data-stu-id="eb938-247">Access and reports</span></span>

<span data-ttu-id="eb938-248">檢視報告、變更您的設定，以及修改使用者角色。</span><span class="sxs-lookup"><span data-stu-id="eb938-248">View reports, change your settings, and modify user roles.</span></span>

![存取與報告快速啟動列](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="eb938-250">SIEM API 連接</span><span class="sxs-lookup"><span data-stu-id="eb938-250">SIEM API connections</span></span>

<span data-ttu-id="eb938-251">如果您使用 [Defender For ENDPOINT SIEM API](../defender-endpoint/enable-siem-integration.md)，您可以繼續執行。</span><span class="sxs-lookup"><span data-stu-id="eb938-251">If you use the [Defender for Endpoint SIEM API](../defender-endpoint/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="eb938-252">我們已在 API 負載上新增連結，指向 [警示] 頁面或 Microsoft 365 安全性入口網站中的 [事件] 頁面。</span><span class="sxs-lookup"><span data-stu-id="eb938-252">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="eb938-253">新的 API 欄位包括 LinkToMTP 及 IncidentLinkToMTP。</span><span class="sxs-lookup"><span data-stu-id="eb938-253">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="eb938-254">如需詳細資訊，請參閱重新導向[從 Microsoft Defender to Endpoint to to the Microsoft 365 security center 的帳戶](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="eb938-254">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="eb938-255">電子郵件警示</span><span class="sxs-lookup"><span data-stu-id="eb938-255">Email alerts</span></span>

<span data-ttu-id="eb938-256">您可以繼續使用用於端點的電子郵件警示。</span><span class="sxs-lookup"><span data-stu-id="eb938-256">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="eb938-257">我們已新增電子郵件中的新連結，指向 [提醒] 頁面或 Microsoft 365 安全性中心的 [事件] 頁面。</span><span class="sxs-lookup"><span data-stu-id="eb938-257">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="eb938-258">如需詳細資訊，請參閱重新導向[從 Microsoft Defender to Endpoint to to the Microsoft 365 security center 的帳戶](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="eb938-258">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="managed-security-service-providers-mssp"></a><span data-ttu-id="eb938-259">受管理的安全性服務提供者 (MSSP) </span><span class="sxs-lookup"><span data-stu-id="eb938-259">Managed Security Service Providers (MSSP)</span></span>

<span data-ttu-id="eb938-260">整合入口網站目前不支援在相同流覽會話中同時登入多個承租人。</span><span class="sxs-lookup"><span data-stu-id="eb938-260">Logging in to multiple tenants simultaneously in the same browsing session is currently not supported in the unified portal.</span></span> <span data-ttu-id="eb938-261">您可以選擇不使用自動重新導向，方法是 [回復至舊版的端點入口網站](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal)，以維護此功能直到問題解決為止。</span><span class="sxs-lookup"><span data-stu-id="eb938-261">You can opt-out of the automatic redirection by [reverting to the former Microsoft Defender for Endpoint portal](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal), to maintain this functionality until the issue is resolved.</span></span>

## <a name="related-information"></a><span data-ttu-id="eb938-262">相關資訊</span><span class="sxs-lookup"><span data-stu-id="eb938-262">Related information</span></span>

- [<span data-ttu-id="eb938-263">Microsoft 365 安全性中心</span><span class="sxs-lookup"><span data-stu-id="eb938-263">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="eb938-264">Microsoft 365 security center 中的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eb938-264">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="eb938-265">將帳戶從 Microsoft Defender for Endpoint 重新導向至 Microsoft 365 的安全性中心</span><span class="sxs-lookup"><span data-stu-id="eb938-265">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)
