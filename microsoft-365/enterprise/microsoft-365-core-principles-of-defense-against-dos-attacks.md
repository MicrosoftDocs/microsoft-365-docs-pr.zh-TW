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
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>防禦拒絕服務攻擊的核心原則

防禦網路型 DoS 攻擊時，三項核心原則是吸收、偵測和緩解。 在偵測之前會發生全部狀況，並在減輕之前進行偵測。 吸收對 DoS 攻擊的最佳防護。 如果偵測到攻擊，則無法加以緩解。 不過，如果即使不能吸收最小的 DoS 攻擊，服務也不會足夠長的時間來偵測到攻擊。

大多陣列織若要購買大量的容量以吸收 DoS 攻擊，並不具實惠的方式，因為這需要大量的技術和技術技能。 這會強調使用 Microsoft 雲端服務的其中一項安全性好處。 Microsoft 服務的實際規模是以經濟划算的方式，為雲端客戶提供強大的網路保護。 但在大規模的情況下，必須在吸收、偵測和緩解之間達到平衡。 若要找出這種平衡點，Microsoft 會研究攻擊成長率，以估計 Microsoft 需要吸收的數量。

偵測是指的是 cat 和滑鼠遊戲。 您必須經常尋找使用者受到攻擊的新方式，並嘗試擊敗您的系統。 偵測-> 緩解-> 偵測-> 緩解等等，是永久的持久狀態，持續無限期持續。

## <a name="defending-against-dos-attacks"></a>防禦 DoS 攻擊

若要順利防禦 DoS 攻擊，及早偵測是必要的。 在系統大量淹沒之前偵測攻擊，defenders 可以執行回應計畫。

下列公式可協助接近 DoS 攻擊的影響時間：

   ** (大小上限（以位元組/秒為單位）) /增長率 (（以位元組/秒為單位）) = 每秒影響 (的時間) **

若偵測的時間發生在時間影響之後，DoS 攻擊可能會成功。 若偵測的時間發生在影響時間之前，則攻擊服務應保持線上，且可供使用緩解策略。 因此，僅有兩個專案可以採取以防禦 DoS 攻擊的目的：

- 增加容量提高容量上限 (，進而提供更多時間來偵測攻擊) ;或
- 縮短偵測的時間。

增加容量對會計有直接影響。 Microsoft 建議客戶至少要開發至少基本的容量，以確保能經受一定程度的 DoS 攻擊。 實際吸收的容量因客戶而異，因為每個客戶都有自己的危險性、風險和財務 outlay 的臨界值。 基於經濟的考慮，在調查中的投資和時間減少偵測偵測的方式，通常是最具成本效益的防禦措施。
