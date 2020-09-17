---
title: Microsoft 威脅防護的新增功能
description: 列出 Microsoft 威脅防護中的新功能與功能
keywords: microsoft 威脅防護中的新功能，ga，一般可用，功能，可用，新
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: da3fd8b97899e302c9b7b24a5c0677534b579981
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47947981"
---
# <a name="whats-new-in-microsoft-threat-protection"></a><span data-ttu-id="7c12a-104">Microsoft 威脅防護的新增功能</span><span class="sxs-lookup"><span data-stu-id="7c12a-104">What's new in Microsoft Threat Protection</span></span>

<span data-ttu-id="7c12a-105">在最新版本的 Microsoft 威脅防護中， (GA) 一般都有下列功能可供使用。</span><span class="sxs-lookup"><span data-stu-id="7c12a-105">The following features are generally available (GA) in the latest release of Microsoft Threat Protection.</span></span>

<span data-ttu-id="7c12a-106">RSS 摘要：將下列 URL 複製並貼到您的摘要讀取器時，獲得此頁面的通知：</span><span class="sxs-lookup"><span data-stu-id="7c12a-106">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="september-2020"></a><span data-ttu-id="7c12a-107">2020 年 9 月</span><span class="sxs-lookup"><span data-stu-id="7c12a-107">September 2020</span></span>
- [<span data-ttu-id="7c12a-108">AssignedIPAddresses ( # A1 函數</span><span class="sxs-lookup"><span data-stu-id="7c12a-108">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="7c12a-109">在您的 [高級搜尋](advanced-hunting-overview.md) 查詢中使用此功能，可快速取得從指定時間點指派給裝置或最近的 ip 位址的最新 ip 位址。</span><span class="sxs-lookup"><span data-stu-id="7c12a-109">Use this function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="7c12a-110">2020 年 7 月</span><span class="sxs-lookup"><span data-stu-id="7c12a-110">July 2020</span></span>
- [<span data-ttu-id="7c12a-111">FileProfile ( # A1 函數</span><span class="sxs-lookup"><span data-stu-id="7c12a-111">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="7c12a-112">在您的高級搜尋查詢中使用此功能，以豐富包含完整檔案資訊的結果。</span><span class="sxs-lookup"><span data-stu-id="7c12a-112">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="7c12a-113">身分識別和應用程式表格</span><span class="sxs-lookup"><span data-stu-id="7c12a-113">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="7c12a-114">使用高級搜尋架構中的 [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)、 [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)及 [AppFileEvents](advanced-hunting-appfileevents-table.md) 表格，可以深入瞭解驗證事件、Active Directory 查詢及應用程式相關的活動。</span><span class="sxs-lookup"><span data-stu-id="7c12a-114">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="7c12a-115">去搜尋</span><span class="sxs-lookup"><span data-stu-id="7c12a-115">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="7c12a-116">使用查詢式的高級搜尋功能，快速從調查事件，以檢查特定事件、使用者、裝置或其他實體類型。</span><span class="sxs-lookup"><span data-stu-id="7c12a-116">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types using query-based advanced hunting capabilities.</span></span>

## <a name="june-2020"></a><span data-ttu-id="7c12a-117">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="7c12a-117">June 2020</span></span>
- <span data-ttu-id="7c12a-118">Twitter 摘要</span><span class="sxs-lookup"><span data-stu-id="7c12a-118">Twitter feed</span></span> <br> <span data-ttu-id="7c12a-119">深入瞭解儀表板內的最新安全性調查、威脅情報、產品新聞及其他。</span><span class="sxs-lookup"><span data-stu-id="7c12a-119">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="7c12a-120">EmailPostDeliveryEvents 架構表格</span><span class="sxs-lookup"><span data-stu-id="7c12a-120">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="7c12a-121">在您的高級搜尋查詢中包含對電子郵件訊息所進行投遞投遞動作的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7c12a-121">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- <span data-ttu-id="7c12a-122">[在 [高級搜尋] 中檢查記錄](advanced-hunting-query-results.md#drill-down-from-query-results)</span><span class="sxs-lookup"><span data-stu-id="7c12a-122">[Inspect records in advanced hunting](advanced-hunting-query-results.md#drill-down-from-query-results)</span></span> <br> <span data-ttu-id="7c12a-123">使用新的 [詳細資料] 面板，快速檢查查詢結果中的記錄。</span><span class="sxs-lookup"><span data-stu-id="7c12a-123">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="7c12a-124">2020 年 5 月</span><span class="sxs-lookup"><span data-stu-id="7c12a-124">May 2020</span></span>
- [<span data-ttu-id="7c12a-125">自訂偵測</span><span class="sxs-lookup"><span data-stu-id="7c12a-125">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="7c12a-126">使用高級搜尋查詢來建立自訂偵測規則，以自動監控和回應安全性事件和系統狀態。</span><span class="sxs-lookup"><span data-stu-id="7c12a-126">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="7c12a-127">2020 年 2 月</span><span class="sxs-lookup"><span data-stu-id="7c12a-127">February 2020</span></span>
- [<span data-ttu-id="7c12a-128">事件</span><span class="sxs-lookup"><span data-stu-id="7c12a-128">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="7c12a-129">確切知道攻擊已啟動的位置，以及可協助您瞭解攻擊程度的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7c12a-129">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="7c12a-130">自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="7c12a-130">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="7c12a-131">AIR 可讓您的安全性作業小組大幅增加貴組織處理安全性警示和事件的能力。</span><span class="sxs-lookup"><span data-stu-id="7c12a-131">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="7c12a-132">高級搜尋增強功能</span><span class="sxs-lookup"><span data-stu-id="7c12a-132">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="7c12a-133">使用 Kusto 查詢語言和安全性優化架構，主動搜尋整個現代 workspace 中的威脅。</span><span class="sxs-lookup"><span data-stu-id="7c12a-133">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="7c12a-134">2019 年 3 月</span><span class="sxs-lookup"><span data-stu-id="7c12a-134">March 2019</span></span>
- <span data-ttu-id="7c12a-135">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="7c12a-135">Advanced hunting</span></span> <br> <span data-ttu-id="7c12a-136">可讓您主動找到影響電子郵件和資料、裝置和身分識別之威脅的各種搜尋功能的登陸頁面。</span><span class="sxs-lookup"><span data-stu-id="7c12a-136">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="7c12a-137">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="7c12a-137">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="7c12a-138">度量組織的安全性狀況，其值越高，表示採取的改善動作越多。</span><span class="sxs-lookup"><span data-stu-id="7c12a-138">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="7c12a-139">遵循安全性分數建議可保護您的組織免受威脅。</span><span class="sxs-lookup"><span data-stu-id="7c12a-139">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="7c12a-140">報告</span><span class="sxs-lookup"><span data-stu-id="7c12a-140">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="7c12a-141">可提供一系列的功能，涵蓋安全分析員和系統管理員在日常作業中所追蹤的各種區域。</span><span class="sxs-lookup"><span data-stu-id="7c12a-141">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
