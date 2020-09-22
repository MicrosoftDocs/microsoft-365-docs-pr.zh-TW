---
title: 郵件流程圖
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用安全性 & 合規性中心內郵件流程儀表板中的郵件流程地圖，以視覺化和追蹤郵件如何透過連接器傳送或從其組織傳送，而不使用連接器。
ms.openlocfilehash: 74cabb7f7b34be6248d18d71565c8a9729d7e38b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199368"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>安全性 & 規範中心內的郵件流程地圖

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[安全性 & 合規性中心](https://protection.office.com)的[郵件流程儀表板](mail-flow-insights-v2.md)中的**郵件流程地圖**，可提供郵件透過您的組織流動的洞察力。 您可以使用此資訊來瞭解模式、識別異常，並在發生問題時修正問題。

![安全性 & 規範中心內郵件流程儀表板中的郵件流程對應構件](../../media/mfi-mail-flow-map-widget.png)

根據預設，構件會顯示上一天的郵件流程模式，稱為「 *Sankey* 圖表」圖表。 您可以使用向左箭號及向右箭號向右箭號 ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) 來顯示不同天的資訊。 每個不同的色彩都代表不同輸入或輸出連接器上的郵件流程 (或不使用連接器) 。 如果您將游標懸停在特定色彩上，就會針對該類型的連接器顯示郵件數目。

## <a name="report-view-for-the-mail-flow-map"></a>郵件流程地圖的報表檢視

按一下 [ **郵件流程地圖** ] 小工具，將會帶您前往 **郵件流程地圖** 報告。

報表檢視提供下列圖表：

- **顯示資料：概述**：這基本上是更大的小工具視圖。 如果您將游標懸停在特定色彩上，就會針對該類型的連接器顯示郵件數目。

  ![郵件流程地圖報告中的概覽視圖](../../media/mfi-mail-flow-map-report-overview.png)

- **顯示資料：詳細資料**：此視圖顯示連接器和目的地網域的詳細資料。 會列出上方寄件者和收件者網域，其餘部分則放入 **其他**人。 如果您將游標懸停在特定的色彩及區段上，就會顯示訊息的數目。

  ![郵件流程地圖報告中的詳細資料檢視](../../media/mfi-mail-flow-map-report-detail.png)

如果您按一下報表檢視中的 [ **篩選器** ]，您可以指定具有 **開始日期** 和 **結束日期**的日期範圍。

若要將特定日期範圍的報告傳送至一或多個收件者，請按一下 [ **要求下載**]。

相關的洞察力會顯示在郵件流程地圖底下（如果有的話） (例如， [修正可能的郵件迴圈洞察力](mfi-mail-loop-insight.md)) 。

## <a name="details-table-view-for-the-mail-flow-map"></a>郵件流程地圖的詳細資料表格視圖

如果您按一下報表檢視中的 [ **查看詳細資料] 表格** ，會顯示下列資訊：

- **Date**
- **類別**
- **連接器/協力廠商服務提供者**
- **寄件者/收件者網域**
- **訊息計數**

如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期**的日期範圍。

如果您選取某列，則會在浮出控制項中顯示類似的詳細資料：

![從郵件流程地圖的詳細資料表格中彈出詳細資料](../../media/mfi-mail-flow-map-view-details-table-details.png)

若要將特定日期範圍的報告傳送至一或多個收件者，請按一下 [ **要求下載**]。

若要回到 [報告] 視圖，請按一下 [ **查看報告**]。

## <a name="see-also"></a>請參閱

如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。
