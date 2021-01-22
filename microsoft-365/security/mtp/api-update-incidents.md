---
title: 更新事件 API
description: 瞭解如何使用 Microsoft 365 Defender API 更新事件
keywords: 更新、api、事件
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
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929067"
---
# <a name="update-incidents-api"></a>更新事件 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 365 Defender

> [!IMPORTANT]
> 部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="api-description"></a>API 描述

更新現有事件的屬性。 可更新的屬性為 ```status``` ：、 ```determination``` ```classification``` ```assignedTo``` 及 ```tags``` 。

### <a name="quotas-resource-allocation-and-other-constraints"></a>配額、資源配置及其他限制

1. 您每分鐘可以撥打多達 50 個通話，或是每小時撥打 1500 個通話，然後再達到節流閾值。
2. 只有在設為 `determination` `classification` TruePositive 時，您才能設定屬性。

如果您的要求已節流，它會返回 `429` 回應代碼。 回復內體會指出您可以開始撥打新電話的時間。

## <a name="permissions"></a>權限

呼叫此 API 需要下列其中一個許可權。 若要深入瞭解，包括如何選擇許可權，請參閱[存取 Microsoft 365 Defender API。](api-access.md)

許可權類型 | 權限 | 許可權顯示名稱
-|-|-
應用程式 | Incident.ReadWrite.All | 讀取及寫入所有事件
已委派 (公司或學校帳戶)  | Incident.ReadWrite | 讀取和寫入事件

> [!NOTE]
> 使用使用者認證取得權杖時，使用者需要有更新入口網站中事件的許可權。

## <a name="http-request"></a>HTTP 要求

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 說明
-|-|-
授權 | 字串 | Bearer {token}. **必要欄位**。
Content-Type | 字串 | application/json。 **必要欄位**。

## <a name="request-body"></a>要求內體

在要求內內容中，提供應該更新之欄位的值。 要求內內容中未包含的現有屬性會維持其值，除非因為相關值變更而必須重新計算。 為獲得最佳效果，您應省略未變更的現有值。

屬性	 | 類型 | 說明
-|-|-
地位 | Enum | 指定警示的目前狀態。 可能的值有：、 ```Active``` ```Resolved``` 及 ```Redirected``` 。
assignedTo | string | 事件的擁有者。
分類 | Enum | 警示的規格。 可能的值有 ```Unknown``` ```FalsePositive``` ```TruePositive``` ：、、。
測定 | Enum | 指定警示決定。 可能的值有 ```NotAvailable``` ：、 ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。
標籤 | 字串清單 | 事件標記清單。

## <a name="response"></a>回應

如果成功，此方法會返回 `200 OK` 。 回應內內容會包含具有更新屬性的事件實體。 如果找不到具有指定識別碼的事件，方法會返回 `404 Not Found` 。

## <a name="example"></a>範例

**請求**

以下是要求範例。

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**回應**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a>相關文章

- [存取 Microsoft 365 Defender API](api-access.md)
- [瞭解 API 限制與授權](api-terms.md)
- [瞭解錯誤碼](api-error-codes.md)
- [事件 API](api-incident.md)
- [列出事件](api-list-incidents.md)
- [事件概觀](incidents-overview.md)
