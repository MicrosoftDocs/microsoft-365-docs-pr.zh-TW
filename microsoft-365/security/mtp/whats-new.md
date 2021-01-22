---
title: Microsoft 365 Defender 的新功能
description: 列出 Microsoft 365 Defender 中的新功能
keywords: Microsoft 威脅防護的新增功能， ga， 一般可用， 功能， 可用， 新增
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8e66c734151e7476d7c54bd050891a1bffb17b3c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932019"
---
# <a name="whats-new-in-microsoft-365-defender"></a><span data-ttu-id="fe146-104">Microsoft 365 Defender 的新功能</span><span class="sxs-lookup"><span data-stu-id="fe146-104">What's new in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="fe146-105">想要體驗 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="fe146-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="fe146-106">您可以在實驗室 [環境中進行評估，](https://aka.ms/mtp-trial-lab) 或在生產 [環境中執行試驗專案](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="fe146-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="fe146-107">下列功能一般 (Microsoft 365 Defender) GA 更新版本。</span><span class="sxs-lookup"><span data-stu-id="fe146-107">The following features are generally available (GA) in the latest release of Microsoft 365 Defender.</span></span>

<span data-ttu-id="fe146-108">RSS 轉播：在此頁面更新時取得通知，方法如下：將下列 URL 複製並加入您的轉播閱讀程式：</span><span class="sxs-lookup"><span data-stu-id="fe146-108">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
> <span data-ttu-id="fe146-109">想要體驗 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="fe146-109">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="fe146-110">您可以在實驗室 [環境中進行評估，](https://aka.ms/mtp-trial-lab) 或在生產 [環境中執行試驗專案](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="fe146-110">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook)</span></span>
>

## <a name="september-2020"></a><span data-ttu-id="fe146-111">2020 年 9 月</span><span class="sxs-lookup"><span data-stu-id="fe146-111">September 2020</span></span>
- [<span data-ttu-id="fe146-112">IdentityDirectoryEvents 資料表</span><span class="sxs-lookup"><span data-stu-id="fe146-112">IdentityDirectoryEvents table</span></span>](advanced-hunting-identitydirectoryevents-table.md) <br> <span data-ttu-id="fe146-113">尋找涉及內部部署網域控制站執行 Active Directory (AD) 。</span><span class="sxs-lookup"><span data-stu-id="fe146-113">Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="fe146-114">此 [進位搜尋](advanced-hunting-overview.md) 架構表格涵蓋網域控制站上的一系列身分識別相關事件及系統事件。</span><span class="sxs-lookup"><span data-stu-id="fe146-114">This [advanced hunting](advanced-hunting-overview.md) schema table covers a range of identity-related events and system events on the domain controller.</span></span>
- [<span data-ttu-id="fe146-115">AssignedIPAddresses () 函數</span><span class="sxs-lookup"><span data-stu-id="fe146-115">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="fe146-116">在進位搜尋查詢中使用此函數，以快速取得指派給裝置的最新 IP 位址，或特定時間的最新 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="fe146-116">Use this function in your advanced hunting queries to quickly obtain the latest IP addresses assigned to a device or the most recent IP addresses from a specific time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="fe146-117">2020 年 7 月</span><span class="sxs-lookup"><span data-stu-id="fe146-117">July 2020</span></span>
- [<span data-ttu-id="fe146-118">FileProfile () 函數</span><span class="sxs-lookup"><span data-stu-id="fe146-118">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="fe146-119">在進一步搜尋查詢中使用此函數，以完整的檔案資訊來豐富結果。</span><span class="sxs-lookup"><span data-stu-id="fe146-119">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="fe146-120">身分識別與應用程式資料表</span><span class="sxs-lookup"><span data-stu-id="fe146-120">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="fe146-121">使用進位搜尋架構中的[IdentityLogonEvents、IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)和[AppFileEvents](advanced-hunting-appfileevents-table.md)資料表，深入瞭解驗證事件、Active Directory 查詢及應用程式相關活動。 [](advanced-hunting-identitylogonevents-table.md)</span><span class="sxs-lookup"><span data-stu-id="fe146-121">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="fe146-122">開始搜補</span><span class="sxs-lookup"><span data-stu-id="fe146-122">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="fe146-123">快速從調查事件到檢查特定事件、使用者、裝置或進一步搜尋的其他實體類型。</span><span class="sxs-lookup"><span data-stu-id="fe146-123">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types on advanced hunting.</span></span>

## <a name="june-2020"></a><span data-ttu-id="fe146-124">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="fe146-124">June 2020</span></span>
- <span data-ttu-id="fe146-125">Twitter 進紙</span><span class="sxs-lookup"><span data-stu-id="fe146-125">Twitter feed</span></span> <br> <span data-ttu-id="fe146-126">直接在儀表板內取得最新的安全性研究、威脅情報、產品新聞等等。</span><span class="sxs-lookup"><span data-stu-id="fe146-126">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="fe146-127">EmailPostDeliveryEvents 架構資料表</span><span class="sxs-lookup"><span data-stu-id="fe146-127">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="fe146-128">在進一步搜尋查詢中納入對電子郵件訊息採取之傳遞後動作的資訊。</span><span class="sxs-lookup"><span data-stu-id="fe146-128">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="fe146-129">檢查進位搜尋中的記錄</span><span class="sxs-lookup"><span data-stu-id="fe146-129">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="fe146-130">使用新的詳細資料面板快速檢查查詢結果中的記錄。</span><span class="sxs-lookup"><span data-stu-id="fe146-130">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="fe146-131">2020 年 5 月</span><span class="sxs-lookup"><span data-stu-id="fe146-131">May 2020</span></span>
- [<span data-ttu-id="fe146-132">自訂偵測</span><span class="sxs-lookup"><span data-stu-id="fe146-132">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="fe146-133">使用進位搜尋查詢來建立自訂偵測規則，自動監視並回應安全性事件和系統狀態。</span><span class="sxs-lookup"><span data-stu-id="fe146-133">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="fe146-134">2020 年 2 月</span><span class="sxs-lookup"><span data-stu-id="fe146-134">February 2020</span></span>
- [<span data-ttu-id="fe146-135">事件</span><span class="sxs-lookup"><span data-stu-id="fe146-135">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="fe146-136">確切知道攻擊開始在哪，以及其他詳細資料，説明您查看攻擊的範圍。</span><span class="sxs-lookup"><span data-stu-id="fe146-136">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="fe146-137">自動調查及回應</span><span class="sxs-lookup"><span data-stu-id="fe146-137">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="fe146-138">AIR 可讓您的安全性作業小組大幅增加貴組織處理安全性警示和事件的能力。</span><span class="sxs-lookup"><span data-stu-id="fe146-138">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="fe146-139">進一步搜尋增強功能</span><span class="sxs-lookup"><span data-stu-id="fe146-139">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="fe146-140">使用 Kusto 查詢語言及安全性優化的架構，在新式工作區中主動尋找威脅。</span><span class="sxs-lookup"><span data-stu-id="fe146-140">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="fe146-141">2019 年 3 月</span><span class="sxs-lookup"><span data-stu-id="fe146-141">March 2019</span></span>
- <span data-ttu-id="fe146-142">進階搜捕</span><span class="sxs-lookup"><span data-stu-id="fe146-142">Advanced hunting</span></span> <br> <span data-ttu-id="fe146-143">登陸頁面提供各種搜尋功能，讓您主動找出影響電子郵件和資料、裝置和身分身分的威脅。</span><span class="sxs-lookup"><span data-stu-id="fe146-143">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="fe146-144">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="fe146-144">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="fe146-145">組織安全性措施的度量，數位越高，表示已採取更多改進動作。</span><span class="sxs-lookup"><span data-stu-id="fe146-145">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="fe146-146">遵循安全性分數建議可保護貴組織不受威脅。</span><span class="sxs-lookup"><span data-stu-id="fe146-146">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="fe146-147">報告</span><span class="sxs-lookup"><span data-stu-id="fe146-147">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="fe146-148">功能豐富的卡片涵蓋安全性分析師和系統管理員在日常作業中追蹤的數個領域。</span><span class="sxs-lookup"><span data-stu-id="fe146-148">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
