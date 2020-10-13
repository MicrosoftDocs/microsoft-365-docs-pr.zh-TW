---
title: Microsoft 威脅防護中的事件概觀
description: 調查在不同裝置、使用者和信箱看到的事件。
keywords: 事件, 警示, 調查, 關聯, 攻擊, 電腦, 裝置, 使用者, 身分識別, 身分識別, 信箱, 電子郵件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3c50bbfbfdad85283f6e366a32c126958467f4a0
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431108"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="4a021-104">Microsoft 威脅防護中的事件概觀</span><span class="sxs-lookup"><span data-stu-id="4a021-104">Incidents overview in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4a021-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4a021-105">**Applies to:**</span></span>
- <span data-ttu-id="4a021-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="4a021-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="4a021-107">事件是以相關的警示為基礎。</span><span class="sxs-lookup"><span data-stu-id="4a021-107">Incidents are based on related alerts.</span></span> <span data-ttu-id="4a021-108">當在您的網路上發現惡意事件或活動時，系統會產生警示。</span><span class="sxs-lookup"><span data-stu-id="4a021-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="4a021-109">個別警示提供有關進行中攻擊的重要線索。</span><span class="sxs-lookup"><span data-stu-id="4a021-109">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="4a021-110">不過，攻擊通常會使用各種向量和技術來執行破壞。</span><span class="sxs-lookup"><span data-stu-id="4a021-110">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="4a021-111">將個別的線索 Piecing 在一起可能會非常困難而且耗時。</span><span class="sxs-lookup"><span data-stu-id="4a021-111">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="4a021-112">這段影片可讓您瞭解 Microsoft 威脅防護中的事件。</span><span class="sxs-lookup"><span data-stu-id="4a021-112">This short video gives an overview of incidents in Microsoft Threat Protection.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="4a021-113">事件是組成攻擊之故事的相關警示集合。</span><span class="sxs-lookup"><span data-stu-id="4a021-113">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="4a021-114">在網路中不同裝置、使用者和信箱實體中找到的惡意和可疑事件，會自動依 Microsoft 威脅防護來匯總。</span><span class="sxs-lookup"><span data-stu-id="4a021-114">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft Threat Protection.</span></span> <span data-ttu-id="4a021-115">將相關警示分組到事件中，可讓安全性 defenders 整個攻擊的觀點。</span><span class="sxs-lookup"><span data-stu-id="4a021-115">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="4a021-116">例如，安全性 defenders 可查看攻擊的開始位置、使用的戰術，以及攻擊進入網路的程度。</span><span class="sxs-lookup"><span data-stu-id="4a021-116">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="4a021-117">他們也可以查看受影響的範圍、影響的裝置、使用者和信箱數目、影響的程度，以及受影響實體的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4a021-117">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="4a021-118">若啟用，Microsoft 威脅防護便可透過自動化和人工智慧，自動調查和解決個別的提醒。</span><span class="sxs-lookup"><span data-stu-id="4a021-118">If enabled, Microsoft Threat Protection can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="4a021-119">安全性 defenders 也可以執行其他修復步驟，以直接從事件檢視解決攻擊。</span><span class="sxs-lookup"><span data-stu-id="4a021-119">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="4a021-120">過去30天的事件會顯示在事件佇列中。</span><span class="sxs-lookup"><span data-stu-id="4a021-120">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="4a021-121">從這裡，安全性 defenders 可根據風險層級及其他因素，查看應優先考慮哪些事件。</span><span class="sxs-lookup"><span data-stu-id="4a021-121">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="4a021-122">[安全性 defenders] 也可以重新命名事件，並將其指派給個別分析員、分類，並將標記新增至事件，以獲得更佳和更多自訂的事件管理體驗。</span><span class="sxs-lookup"><span data-stu-id="4a021-122">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="4a021-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="4a021-123">See also</span></span>
- [<span data-ttu-id="4a021-124">設定事件優先順序</span><span class="sxs-lookup"><span data-stu-id="4a021-124">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="4a021-125">調查事件</span><span class="sxs-lookup"><span data-stu-id="4a021-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="4a021-126">管理事件</span><span class="sxs-lookup"><span data-stu-id="4a021-126">Manage incidents</span></span>](manage-incidents.md)
