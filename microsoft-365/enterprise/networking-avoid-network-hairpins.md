---
title: 步驟 3：避免網路 hairpin
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並移除網路 hairpin 以取得更好的效能。
ms.openlocfilehash: 7277b8f5c07bc156599f946e032c3345da3316e9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866758"
---
# <a name="step-3-avoid-network-hairpins"></a>步驟 3：避免網路 hairpin

*此為必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

當前往目的地的流量首先導向至另一個中繼位置 (例如內部部署安全性堆疊、雲端存取代理程式或雲端型閘道) 時，就會發生[網路 hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)。由於網路服務提供者，網路 hairpin 也可能是由網際網路上不良的路由所造成。hairpin 會新增延遲，並可能將流量重新導向到遠距位置。

若要最佳化 Microsoft 365 雲端型服務之流量的效能，請檢查提供當地網際網路連線的 ISP 是否在接近該位置之處具有與 Microsoft 全球網路的直接對等關係。這些連線沒有 hairpin。

如果您對 Microsoft 365 流量使用雲端型網路或安全性服務，請確定評估 hairpinning 效果，並了解其對效能的影響。請檢查下列各項：

- 針對您的分支辦公室和 Microsoft 全球網路對等點，透過其轉送流量之服務提供者的數目和位置 
- 服務提供者與您的 ISP 和 Microsoft 之網路對等關係的品質 
- 服務提供者基礎結構中回載的效能影響

儘可能將您的邊緣路由器設定為直接傳送信任的 Microsoft 365 流量，而不是透過處理網際網路流量的協力廠商雲端或雲端型網路安全性廠商來進行 Proxy 或通道傳送。 

作為過渡期的檢查點，您可以看到此步驟的[允出準則](networking-exit-criteria.md#crit-networking-step3)。

## <a name="next-step"></a>後續步驟

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[設定流量旁路](networking-configure-proxies-firewalls.md)|
