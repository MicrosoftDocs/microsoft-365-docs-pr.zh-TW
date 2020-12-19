---
title: Microsoft 365 Defender 事件 APIs 和事件資源類型
description: 深入瞭解 Microsoft 365 Defender 中的事件資源類型的方法和屬性
keywords: 事件、事件、api
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719331"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Defender 事件 API 和事件資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 365 Defender

> [!IMPORTANT]
> 一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

[事件](incidents-overview.md)是協助描述攻擊的相關警示集合。 您組織中不同實體的事件會由 Microsoft 365 Defender 自動匯總。 您可以使用事件 API，以程式設計方式存取您組織的事件及相關警示。

## <a name="quotas-and-resource-allocation"></a>配額和資源配置

您最多可以每分鐘要求50個通話或每小時1500通話。 每個方法也有它自己的配額。 如需方法特定配額的詳細資訊，請參閱對應于您要使用之方法的各篇文章。

`429`HTTP 回應碼表示您已到達配額（按傳送的要求數目，或已分派的執行時間）。 回應內文會包含時間，直到您到達的配額會重設。

## <a name="permissions"></a>權限

事件 API 需要不同類型的許可權才能提供其所有方法。 如需有關所需許可權的詳細資訊，請參閱各自的方法的文章。

## <a name="methods"></a>方法

方法	 | 傳回類型 | 描述
-|-|-
[列出事件](api-list-incidents.md) | [事件](api-incident.md) 清單 | 取得事件清單。
[更新事件](api-update-incidents.md) | [事件](api-incident.md) | 更新特定的事件。

## <a name="request-body-response-and-examples"></a>要求的主體、回應和範例

如需如何建立要求或剖析回應的詳細資訊，以及實際範例，請參閱各自的方法文章。

## <a name="common-properties"></a>一般屬性

屬性	 | 類型 | 描述
-|-|-
incidentId | long | 事件唯一識別碼。
redirectIncidentId | 可為 null 的長 | 目前的事件彙總至的事件識別碼。
incidentName | string | 事件的名稱。
createdTime | DateTimeOffset | 在 UTC) 建立事件的日期和時間 (。
lastUpdateTime | DateTimeOffset | 上次更新事件) 的日期和時間 (。
分配 | string | 事件的擁有者。
嚴重性 | Enum | 事件的嚴重性。 可能的值為：、、、 ```UnSpecified``` ```Informational``` ```Low``` ```Medium``` 、和 ```High``` 。
地位 | Enum | 指定事件目前的狀態。 可能的值為： ```Active``` 、 ```Resolved``` 、和 ```Redirected``` 。
分類 | Enum | 事件的規格。 可能的值為： ```Unknown``` 、 ```FalsePositive``` 、 ```TruePositive``` 。
測定 | Enum | 指定事件的確定。 可能的值為：、、、、、、 ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。
標籤 | 字串清單 | 事件標記清單。
警報 | 警示清單 | 相關警示的清單。 請參閱 [List 事件](api-list-incidents.md) API 檔中的範例。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender APIs 概述](api-overview.md)
- [事件概觀](incidents-overview.md)
- [列出事件 API](api-list-incidents.md)
- [更新事件 API](api-update-incidents.md)
