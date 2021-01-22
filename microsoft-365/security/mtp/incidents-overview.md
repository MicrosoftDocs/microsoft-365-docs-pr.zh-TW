---
title: Microsoft 365 Defender 中的事件概觀
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
ms.openlocfilehash: 7fcbecddd5e8f83e9c78d6db90939fbfc2f2df07
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929279"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="2dd77-104">Microsoft 365 Defender 中的事件概觀</span><span class="sxs-lookup"><span data-stu-id="2dd77-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2dd77-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="2dd77-105">**Applies to:**</span></span>
- <span data-ttu-id="2dd77-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2dd77-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="2dd77-107">想要體驗 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="2dd77-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="2dd77-108">您可以在實驗室 [環境中進行評估，](https://aka.ms/mtp-trial-lab) 或在生產 [環境中執行試驗專案](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="2dd77-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="2dd77-109">事件是根據相關的警示。</span><span class="sxs-lookup"><span data-stu-id="2dd77-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="2dd77-110">當在您的網路上發現惡意事件或活動時，系統會產生警示。</span><span class="sxs-lookup"><span data-stu-id="2dd77-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="2dd77-111">個別警示可提供有關進行中攻擊的寶貴線索。</span><span class="sxs-lookup"><span data-stu-id="2dd77-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="2dd77-112">不過，攻擊通常會使用各種向量和技巧以執行外泄。</span><span class="sxs-lookup"><span data-stu-id="2dd77-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="2dd77-113">將個別的線索放在一起可能相當困難且耗時。</span><span class="sxs-lookup"><span data-stu-id="2dd77-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="2dd77-114">這段短片提供 Microsoft 365 Defender 中事件概觀。</span><span class="sxs-lookup"><span data-stu-id="2dd77-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="2dd77-115">事件是一組相關警示集合，這些警示會指出攻擊事件。</span><span class="sxs-lookup"><span data-stu-id="2dd77-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="2dd77-116">在網路的不同裝置、使用者和信箱實體中發現惡意和可疑事件時，Microsoft 365 Defender 會自動匯總。</span><span class="sxs-lookup"><span data-stu-id="2dd77-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="2dd77-117">將相關警示分組到事件後，安全性維護者可全面查看攻擊。</span><span class="sxs-lookup"><span data-stu-id="2dd77-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="2dd77-118">例如，安全性保護人員可以看到攻擊的開始位置、使用的策略，以及攻擊已進入網路多遠。</span><span class="sxs-lookup"><span data-stu-id="2dd77-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="2dd77-119">他們也可以查看攻擊的範圍，例如受攻擊的裝置數量、使用者和信箱數量、影響的範圍，以及受影響實體的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2dd77-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="2dd77-120">如果啟用，Microsoft 365 Defender 可透過自動化和人工智慧自動調查並解決個別警示。</span><span class="sxs-lookup"><span data-stu-id="2dd77-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="2dd77-121">安全性保護者也可以執行額外的修復步驟，直接從事件檢視中解決攻擊。</span><span class="sxs-lookup"><span data-stu-id="2dd77-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="2dd77-122">過去 30 天的事件會顯示在事件佇列中。</span><span class="sxs-lookup"><span data-stu-id="2dd77-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="2dd77-123">從這裡，安全性維護者可以看到哪些事件應該根據風險等級及其他因素來排列優先順序。</span><span class="sxs-lookup"><span data-stu-id="2dd77-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="2dd77-124">安全性保護者也可以重新命名事件、將事件指派給個別分析師、將事件分類，以及新增標記到事件，以提供更好的自訂事件管理體驗。</span><span class="sxs-lookup"><span data-stu-id="2dd77-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="2dd77-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2dd77-125">See also</span></span>
- [<span data-ttu-id="2dd77-126">設定事件優先順序</span><span class="sxs-lookup"><span data-stu-id="2dd77-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="2dd77-127">調查事件</span><span class="sxs-lookup"><span data-stu-id="2dd77-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="2dd77-128">管理事件</span><span class="sxs-lookup"><span data-stu-id="2dd77-128">Manage incidents</span></span>](manage-incidents.md)
