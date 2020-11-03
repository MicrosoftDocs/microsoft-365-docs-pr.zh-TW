---
title: Microsoft 365 Defender API 中的事件資源類型
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
ms.openlocfilehash: 68bee647cdd5687dbaad08ce3cd01b427dabf030
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844017"
---
# <a name="incident-resource-type"></a>事件資源類型

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

>[!IMPORTANT] 
>一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="methods"></a>方法

方法	 |傳回類型 |描述
:---|:---|:---
[列出事件](api-list-incidents.md) | [事件](api-incident.md) 清單 | 取得事件清單。
[更新事件](api-update-incidents.md) | [事件](api-incident.md) | 更新特定的事件。


## <a name="properties"></a>屬性

屬性	 |    類型    |    描述
:---|:---|:---
incidentId | long | 事件唯一識別碼。
redirectIncidentId | 可為 null 的長 | 目前的事件彙總至的事件識別碼。
incidentName | string | 事件的名稱。
createdTime | DateTimeOffset | 在 UTC) 建立事件的日期和時間 (。
lastUpdateTime | DateTimeOffset | 上次更新事件) 的日期和時間 (。
分配 | string | 事件的擁有者。
嚴重性 | Enum | 事件的嚴重性。 可能的值為： ```UnSpecified``` 、、 ```Informational``` ```Low``` 、 ```Medium``` 和 ```High``` 。
地位 | Enum | 指定事件目前的狀態。 可能的值為 ```Active``` ： ```Resolved``` 和 ```Redirected``` 。
分類 | Enum | 事件的規格。 可能的值為： ```Unknown``` 、 ```FalsePositive``` 、 ```TruePositive``` 。
測定 | Enum | 指定事件的確定。 可能的值為：、、、、、、 ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。
標籤 | 字串清單 | 事件標記清單。
警報 | 警示清單 | 相關警示的清單。 請參閱 [List 事件](api-list-incidents.md) API 檔中的範例。
