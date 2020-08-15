---
title: 防禦拒絕服務攻擊的 Microsoft 365 核心原則
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Microsoft 如何利用其在防護拒絕服務 (DoS) 攻擊中的吸收、偵測和緩解的核心原則。
ms.openlocfilehash: b04ec717f7c97e44c6ed4011156666e8c27f06c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688457"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="b7a42-103">防禦拒絕服務攻擊的核心原則</span><span class="sxs-lookup"><span data-stu-id="b7a42-103">Core principles of defense against denial-of-service attacks</span></span>

<span data-ttu-id="b7a42-104">防禦網路型 DoS 攻擊時，三項核心原則是吸收、偵測和緩解。</span><span class="sxs-lookup"><span data-stu-id="b7a42-104">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation.</span></span> <span data-ttu-id="b7a42-105">在偵測之前會發生全部狀況，並在減輕之前進行偵測。</span><span class="sxs-lookup"><span data-stu-id="b7a42-105">Absorption happens before detection, and detection happens before mitigation.</span></span> <span data-ttu-id="b7a42-106">吸收對 DoS 攻擊的最佳防護。</span><span class="sxs-lookup"><span data-stu-id="b7a42-106">Absorption is the best defense against a DoS attack.</span></span> <span data-ttu-id="b7a42-107">如果偵測到攻擊，則無法加以緩解。</span><span class="sxs-lookup"><span data-stu-id="b7a42-107">If the attack can't be detected, it can't be mitigated.</span></span> <span data-ttu-id="b7a42-108">不過，如果即使不能吸收最小的 DoS 攻擊，服務也不會足夠長的時間來偵測到攻擊。</span><span class="sxs-lookup"><span data-stu-id="b7a42-108">But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="b7a42-109">大多陣列織若要購買大量的容量以吸收 DoS 攻擊，並不具實惠的方式，因為這需要大量的技術和技術技能。</span><span class="sxs-lookup"><span data-stu-id="b7a42-109">It is not economically feasible for most organizations to purchase excess capacity to absorb DoS attacks, as this requires a considerable investment in technology and technical skills.</span></span> <span data-ttu-id="b7a42-110">這會強調使用 Microsoft 雲端服務的其中一項安全性好處。</span><span class="sxs-lookup"><span data-stu-id="b7a42-110">This highlights one of the security benefits of using Microsoft cloud services.</span></span> <span data-ttu-id="b7a42-111">Microsoft 服務的實際規模是以經濟划算的方式，為雲端客戶提供強大的網路保護。</span><span class="sxs-lookup"><span data-stu-id="b7a42-111">The sheer scale of Microsoft services provides strong network protection to cloud customers in a cost-effective manner.</span></span> <span data-ttu-id="b7a42-112">但在大規模的情況下，必須在吸收、偵測和緩解之間達到平衡。</span><span class="sxs-lookup"><span data-stu-id="b7a42-112">But even at a large scale, there must be a balance between absorption, detection, and mitigation.</span></span> <span data-ttu-id="b7a42-113">若要找出這種平衡點，Microsoft 會研究攻擊成長率，以估計 Microsoft 需要吸收的數量。</span><span class="sxs-lookup"><span data-stu-id="b7a42-113">To find that balance, Microsoft studies attack growth rates to estimate how much Microsoft needs to absorb.</span></span>

<span data-ttu-id="b7a42-114">偵測是指的是 cat 和滑鼠遊戲。</span><span class="sxs-lookup"><span data-stu-id="b7a42-114">Detection is a cat-and-mouse game.</span></span> <span data-ttu-id="b7a42-115">您必須經常尋找使用者受到攻擊的新方式，並嘗試擊敗您的系統。</span><span class="sxs-lookup"><span data-stu-id="b7a42-115">You must constantly look for new ways people are attack and try to defeat your systems.</span></span> <span data-ttu-id="b7a42-116">偵測-> 緩解-> 偵測-> 緩解等等，是永久的持久狀態，持續無限期持續。</span><span class="sxs-lookup"><span data-stu-id="b7a42-116">Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that continues indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="b7a42-117">防禦 DoS 攻擊</span><span class="sxs-lookup"><span data-stu-id="b7a42-117">Defending Against DoS Attacks</span></span>

<span data-ttu-id="b7a42-118">若要順利防禦 DoS 攻擊，及早偵測是必要的。</span><span class="sxs-lookup"><span data-stu-id="b7a42-118">To successfully defend against a DoS attack, early detection is essential.</span></span> <span data-ttu-id="b7a42-119">在系統大量淹沒之前偵測攻擊，defenders 可以執行回應計畫。</span><span class="sxs-lookup"><span data-stu-id="b7a42-119">By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="b7a42-120">下列公式可協助接近 DoS 攻擊的影響時間：</span><span class="sxs-lookup"><span data-stu-id="b7a42-120">The following formula helps approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="b7a42-121">\*\* (大小上限（以位元組/秒為單位）) /增長率 (（以位元組/秒為單位）) = 每秒影響 (的時間) \*\*</span><span class="sxs-lookup"><span data-stu-id="b7a42-121">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in sec)**</span></span>

<span data-ttu-id="b7a42-122">若偵測的時間發生在時間影響之後，DoS 攻擊可能會成功。</span><span class="sxs-lookup"><span data-stu-id="b7a42-122">If the time-to-detection occurs after time-to-impact, it is likely the DoS attack will be successful.</span></span> <span data-ttu-id="b7a42-123">若偵測的時間發生在影響時間之前，則攻擊服務應保持線上，且可供使用緩解策略。</span><span class="sxs-lookup"><span data-stu-id="b7a42-123">If the time-to-detection occurs before time-to-impact, the attacked services should remain online and accessible if mitigation strategies are used.</span></span> <span data-ttu-id="b7a42-124">因此，僅有兩個專案可以採取以防禦 DoS 攻擊的目的：</span><span class="sxs-lookup"><span data-stu-id="b7a42-124">Thus, there are only two things that can be done to defend against DoS attacks:</span></span>

- <span data-ttu-id="b7a42-125">增加容量提高容量上限 (，進而提供更多時間來偵測攻擊) ;或</span><span class="sxs-lookup"><span data-stu-id="b7a42-125">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="b7a42-126">縮短偵測的時間。</span><span class="sxs-lookup"><span data-stu-id="b7a42-126">Decrease the time to detect.</span></span>

<span data-ttu-id="b7a42-127">增加容量對會計有直接影響。</span><span class="sxs-lookup"><span data-stu-id="b7a42-127">Increasing capacity has a direct fiscal impact.</span></span> <span data-ttu-id="b7a42-128">Microsoft 建議客戶至少要開發至少基本的容量，以確保能經受一定程度的 DoS 攻擊。</span><span class="sxs-lookup"><span data-stu-id="b7a42-128">Microsoft recommends that customers develop at least basic absorption capacity to ensure that they can survive some level of DoS attack.</span></span> <span data-ttu-id="b7a42-129">實際吸收的容量因客戶而異，因為每個客戶都有自己的危險性、風險和財務 outlay 的臨界值。</span><span class="sxs-lookup"><span data-stu-id="b7a42-129">The actual absorption capacity varies from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay.</span></span> <span data-ttu-id="b7a42-130">基於經濟的考慮，在調查中的投資和時間減少偵測偵測的方式，通常是最具成本效益的防禦措施。</span><span class="sxs-lookup"><span data-stu-id="b7a42-130">For economic reasons, investments in research and time for ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
