---
title: Microsoft 365 Defender 中的事件概述
description: 調查在不同裝置、使用者和信箱看到的事件。
keywords: 事件, 警示, 調查, 關聯, 攻擊, 電腦, 裝置, 使用者, 身分識別, 身分識別, 信箱, 電子郵件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: de3fba2692f5b6df7c7192c328a3911287cd7ce2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928721"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="d40c5-104">Microsoft 365 Defender 中的事件概述</span><span class="sxs-lookup"><span data-stu-id="d40c5-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d40c5-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="d40c5-105">**Applies to:**</span></span>
- <span data-ttu-id="d40c5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d40c5-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="d40c5-107">想要體驗 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="d40c5-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="d40c5-108">您可以 [在實驗室環境中進行評估](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) ，或 [在實際執行中執行您的試驗專案](./mtp-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="d40c5-108">You can [evaluate it in a lab environment](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](./mtp-pilot.md?ocid=cx-evalpilot).</span></span>
>


<span data-ttu-id="d40c5-109">事件是以相關的警示為基礎。</span><span class="sxs-lookup"><span data-stu-id="d40c5-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="d40c5-110">當在您的網路上發現惡意事件或活動時，系統會產生警示。</span><span class="sxs-lookup"><span data-stu-id="d40c5-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="d40c5-111">個別警示提供有關進行中攻擊的重要線索。</span><span class="sxs-lookup"><span data-stu-id="d40c5-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="d40c5-112">不過，攻擊通常會使用各種向量和技術來執行破壞。</span><span class="sxs-lookup"><span data-stu-id="d40c5-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="d40c5-113">將個別的線索 Piecing 在一起可能會非常困難而且耗時。</span><span class="sxs-lookup"><span data-stu-id="d40c5-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="d40c5-114">這段簡短的影片會概要說明 Microsoft 365 Defender 中的事件。</span><span class="sxs-lookup"><span data-stu-id="d40c5-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="d40c5-115">事件是組成攻擊之故事的相關警示集合。</span><span class="sxs-lookup"><span data-stu-id="d40c5-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="d40c5-116">在網路中不同裝置、使用者和信箱實體中找到的惡意和可疑事件，會自動由 Microsoft 365 Defender 進行匯總。</span><span class="sxs-lookup"><span data-stu-id="d40c5-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="d40c5-117">將相關警示分組到事件中，可讓安全性 defenders 整個攻擊的觀點。</span><span class="sxs-lookup"><span data-stu-id="d40c5-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="d40c5-118">例如，安全性 defenders 可查看攻擊的開始位置、使用的戰術，以及攻擊進入網路的程度。</span><span class="sxs-lookup"><span data-stu-id="d40c5-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="d40c5-119">他們也可以查看受影響的範圍、影響的裝置、使用者和信箱數目、影響的程度，以及受影響實體的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d40c5-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="d40c5-120">若啟用，Microsoft 365 Defender 便可透過自動化和人工智慧，自動調查和解決個別警示。</span><span class="sxs-lookup"><span data-stu-id="d40c5-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="d40c5-121">安全性 defenders 也可以執行其他修復步驟，以直接從事件檢視解決攻擊。</span><span class="sxs-lookup"><span data-stu-id="d40c5-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="d40c5-122">過去30天的事件會顯示在事件佇列中。</span><span class="sxs-lookup"><span data-stu-id="d40c5-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="d40c5-123">從這裡，安全性 defenders 可根據風險層級及其他因素，查看應優先考慮哪些事件。</span><span class="sxs-lookup"><span data-stu-id="d40c5-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="d40c5-124">[安全性 defenders] 也可以重新命名事件，並將其指派給個別分析員、分類，並將標記新增至事件，以獲得更佳和更多自訂的事件管理體驗。</span><span class="sxs-lookup"><span data-stu-id="d40c5-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="d40c5-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d40c5-125">See also</span></span>
- [<span data-ttu-id="d40c5-126">設定事件優先順序</span><span class="sxs-lookup"><span data-stu-id="d40c5-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="d40c5-127">調查事件</span><span class="sxs-lookup"><span data-stu-id="d40c5-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="d40c5-128">管理事件</span><span class="sxs-lookup"><span data-stu-id="d40c5-128">Manage incidents</span></span>](manage-incidents.md)