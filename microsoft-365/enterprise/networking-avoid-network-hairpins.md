---
title: 步驟 3：避免網路 Hairpin
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並移除網路 Hairpin 以取得更好的效能。
ms.openlocfilehash: 8d3c971c1295f8f1112c594635bfd791b251bd68
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370330"
---
# <a name="step-3-avoid-network-hairpins"></a>步驟 3：避免網路 Hairpin

*此為必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![階段 1 - 網路](./media/deploy-foundation-infrastructure/networking_icon-small.png)

當繫結到目的地的流量 (例如內部部署安全性堆疊、雲端存取代理程式或雲端 Web 閘道) 首先被導向另一個中繼位置時，會發生[網路 hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)。 範例如下。

![網路 hairpin 範例](./media/networking-avoid-network-hairpins/network-hairpin-example.png)

網路 hairpin 也可能是由於網路服務提供者在網際網路上的路由不良所導致。 

Hairpin 會增加延遲，並可能將流量重新導向距離較遠的位置。

若要最佳化 Microsoft 365 雲端型服務之流量的效能，請檢查提供當地網際網路連線的 ISP 是否在接近該位置之處具有與 Microsoft 全球網路的直接對等關係。這些連線沒有 Hairpin。

如果您為 Microsoft 365 流量使用雲端型網路或安全性服務，請務必評估 Hairpinning 效果，並了解它對效能的影響。請檢查下列各項：

- 針對您的分公司和 Microsoft 全球網路對等點，透過其轉送流量之服務提供者的數目和位置 
- 服務提供者與您的 ISP 和 Microsoft 之網路對等關係的品質 
- 服務提供者基礎結構中回載的效能影響

儘可能將您的邊緣路由器設定為直接傳送信任的 Microsoft 365 流量，而不是透過處理網際網路流量的協力廠商雲端或雲端型網路安全性廠商來進行 Proxy 處理或通道傳送。 

![略過網路 hairpin 的範例](./media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

做為過渡期的檢查點，您可以看到此步驟的[允出準則](networking-exit-criteria.md#crit-networking-step3)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![步驟 4](./media/stepnumbers/Step4.png)|[設定流量旁路](networking-configure-proxies-firewalls.md)|
