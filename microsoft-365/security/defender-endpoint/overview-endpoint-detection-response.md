---
title: 端點偵測和回應功能的概覽
ms.reviewer: ''
description: 深入瞭解 Microsoft Defender for Endpoint 中的端點偵測和回應功能
keywords: Microsoft Defender for Endpoint，endpoint 偵測和回應，回應，偵測，cybersecurity，保護
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b00bef611a3e4b33bf15a5366b09a96f68d4c1a2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933514"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="fceb9-104">端點偵測和回應概述</span><span class="sxs-lookup"><span data-stu-id="fceb9-104">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fceb9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="fceb9-105">**Applies to:**</span></span>
- [<span data-ttu-id="fceb9-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fceb9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fceb9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fceb9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fceb9-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="fceb9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fceb9-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="fceb9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="fceb9-110">Defender for Endpoint endpoint 偵測和回應功能提供接近即時及可行動的高級攻擊偵測。</span><span class="sxs-lookup"><span data-stu-id="fceb9-110">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="fceb9-111">安全性分析人員可以有效地排定警示的優先順序、深入了解入侵的全貌，並採取回應動作來補救威脅。</span><span class="sxs-lookup"><span data-stu-id="fceb9-111">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="fceb9-112">偵測到威脅時，系統中就會建立警示，讓分析者可進行調查。</span><span class="sxs-lookup"><span data-stu-id="fceb9-112">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="fceb9-113">系統會將採用相同攻擊技巧或歸咎於相同攻擊者的警示彙總到稱為 _事件_ 的實體中。</span><span class="sxs-lookup"><span data-stu-id="fceb9-113">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="fceb9-114">以這種方式彙總警示，可讓分析人員集體調查和回應威脅。</span><span class="sxs-lookup"><span data-stu-id="fceb9-114">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="fceb9-115">「採用破壞的思維」思維方式，「端點的 Defender」會持續收集行為網路遙測。</span><span class="sxs-lookup"><span data-stu-id="fceb9-115">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="fceb9-116">其中包括程序資訊、網路活動、核心和記憶體管理員的深度光纖、使用者登入活動、登錄和檔案系統變更等等。</span><span class="sxs-lookup"><span data-stu-id="fceb9-116">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="fceb9-117">此資訊會儲存六個月，讓分析人員能夠及時重返攻擊開始的時候。</span><span class="sxs-lookup"><span data-stu-id="fceb9-117">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="fceb9-118">接著，分析人員即可在各種檢視中進行樞紐分析，並透過多個面向著手調查。</span><span class="sxs-lookup"><span data-stu-id="fceb9-118">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="fceb9-119">回應功能讓您能夠對受影響的實體採取行動，立即補救威脅。</span><span class="sxs-lookup"><span data-stu-id="fceb9-119">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="fceb9-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="fceb9-120">Related topics</span></span>
- [<span data-ttu-id="fceb9-121"> 安全性操作儀表板</span><span class="sxs-lookup"><span data-stu-id="fceb9-121">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="fceb9-122">事件佇列</span><span class="sxs-lookup"><span data-stu-id="fceb9-122">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="fceb9-123">警示佇列</span><span class="sxs-lookup"><span data-stu-id="fceb9-123">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="fceb9-124">裝置清單</span><span class="sxs-lookup"><span data-stu-id="fceb9-124">Devices list</span></span>](machines-view-overview.md)

