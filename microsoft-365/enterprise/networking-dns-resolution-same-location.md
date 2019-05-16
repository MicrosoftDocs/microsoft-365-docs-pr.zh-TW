---
title: 步驟 2：設定每個辦公室的當地網際網路連線
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定 DNS 解析以提升效能。
ms.openlocfilehash: 2b3c38a9bf259f453121f7878992d1dc50f2ce97
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073263"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a>步驟 2：設定每個辦公室的當地網際網路連線

*這是必要步驟，且同時適用於 Microsoft 365 企業版 E3 與 E5 版本*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

在步驟 2 中，您確定您的每個辦公室都有當地網際網路連線，並使用當地 DNS 伺服器。這兩個元素需要減少連線延遲，並確定內部部署用戶端電腦連線至 Microsoft 365 雲端型服務的最近進入點。

在大型組織的傳統網路中，網際網路流量會透過網路骨幹傳送至網際網路連線。這無法很好地用於將全球分散式軟體即服務 (SaaS) 基礎結構的效能最佳化，此基礎結構包含 Office 365，以及 Microsoft 365 中的 Enterprise Mobility + Security (EMS) 產品。

Microsoft 全球網路包含全球 Microsoft 365 雲端服務集的前端伺服器。為獲得最佳效能，內部部署用戶端應該存取地理位置上最接近它們的前端伺服器，而不是透過網路骨幹傳送流量，以及存取最接近組織中央網際網路連線的前端伺服器。

為了將用戶端要求導向至地理位置上最接近的前端伺服器，Microsoft 的 DNS 伺服器會使用對應用戶端初始連線要求的 DNS 查詢。因此，為達到最低網路延遲：

- 您組織的所有辦公室都應具有當地網際網路連線，以[最佳化](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories)類別網路流量。
- 每個當地網際網路連線應該使用當地 DNS 伺服器，以從該位置傳送連出網際網路流量。

如需詳細資訊，請參閱[在本機上輸出網路連線](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally)。 

做為過渡期的檢查點，您可以看到此步驟的[允出準則](networking-exit-criteria.md#crit-networking-step2)。

## <a name="next-step"></a>後續步驟

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[避免網路 Hairpin](networking-avoid-network-hairpins.md)|
