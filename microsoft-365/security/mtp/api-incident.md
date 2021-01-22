---
title: Microsoft 365 Defender 事件 API 和事件資源類型
description: 瞭解 Microsoft 365 Defender 中事件資源類型的方法和屬性
keywords: 事件、事件、api
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928351"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Defender 事件 API 和事件資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 365 Defender

> [!IMPORTANT]
> 部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

事件 [是](incidents-overview.md) 相關警示的集合，可協助描述攻擊。 Microsoft 365 Defender 會自動匯總貴組織中不同實體的事件。 您可以使用事件 API 以程式方式存取貴組織的事件和相關警示。

## <a name="quotas-and-resource-allocation"></a>配額和資源配置

您每分鐘可要求多達 50 個通話或每小時 1500 個通話。 每種方法也有自己的配額。 有關特定方法配額詳細資訊，請參閱您想要使用之方法的各自文章。

HTTP 回應碼表示您已達到配額，可以是已傳送的要求數，或是已分配 `429` 執行時間。 回復內體會包含重設您達到的配額之前的時間。

## <a name="permissions"></a>權限

事件 API 會針對每個方法要求不同類型的許可權。 有關所需許可權詳細資訊，請參閱各自方法的文章。

## <a name="methods"></a>方法

方法	 | 傳回類型 | 描述
-|-|-
[列出事件](api-list-incidents.md) | [事件](api-incident.md) 清單 | 取得事件清單。
[更新事件](api-update-incidents.md) | [事件](api-incident.md) | 更新特定事件。

## <a name="request-body-response-and-examples"></a>要求本文、回應和範例

請參閱其各自的方法文章，以瞭解如何建構要求或剖析回應的詳細資訊，以及實用範例。

## <a name="common-properties"></a>一般屬性

屬性	 | 類型 | 說明
-|-|-
incidentId | long | 事件唯一識別碼。
redirectIncidentId | 可 Null long | 合併目前事件的事件識別碼。
incidentName | string | 事件的名稱。
createdTime | DateTimeOffset | 事件建立後 (以 UTC) 日期及時間。
lastUpdateTime | DateTimeOffset | 事件上次更新的 (時間) 以 UTC 表示。
assignedTo | string | 事件的擁有者。
嚴重性 | Enum | 事件的嚴重性。 可能的值有 ```UnSpecified``` ：、 ```Informational``` ```Low``` ```Medium``` 及 ```High``` 。
地位 | Enum | 指定事件目前的狀態。 可能的值有：、 ```Active``` ```Resolved``` 及 ```Redirected``` 。
分類 | Enum | 事件的規格。 可能的值有 ```Unknown``` ```FalsePositive``` ```TruePositive``` ：、、。
測定 | Enum | 指定事件判定。 可能的值有 ```NotAvailable``` ：、 ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。
標籤 | 字串清單 | 事件標記清單。
警報 | 警示清單 | 相關警示清單。 請參閱清單事件 API [檔的](api-list-incidents.md) 範例。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender API 概觀](api-overview.md)
- [事件概觀](incidents-overview.md)
- [清單事件 API](api-list-incidents.md)
- [更新事件 API](api-update-incidents.md)
