---
title: 更新事件 API
description: 瞭解如何使用 Microsoft 365 Defender API 更新事件
keywords: update、api、incident
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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719401"
---
# <a name="update-incidents-api"></a>更新事件 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 365 Defender

> [!IMPORTANT]
> 一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="api-description"></a>API 描述

更新現有事件的屬性。 可更新的屬性包括：、、、 ```status``` ```determination``` ```classification``` ```assignedTo``` 和 ```tags``` 。

### <a name="quotas-resource-allocation-and-other-constraints"></a>配額、資源配置及其他限制

1. 您最多可以每分鐘撥打50個通話或每小時1500個通話，然後再按節流臨界值。
2. `determination`只有在設定為 TruePositive 時，您才可以設定屬性 `classification` 。

如果您的要求遭到限制，它會傳回 `429` 回應碼。 回應內文會指出您可以開始進行新呼叫的時間。

## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [Access The Microsoft 365 Defender APIs](api-access.md)。

許可權類型 | 權限 | 許可權顯示名稱
-|-|-
應用程式 | Incident。 ReadWrite。 | 讀取和寫入所有事件
委派 (工作或學校帳戶)  | Incident。 ReadWrite | 讀取和寫入事件

> [!NOTE]
> 使用使用者認證取得權杖時，使用者必須具有更新入口網站中的事件的許可權。

## <a name="http-request"></a>HTTP 要求

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
-|-|-
授權 | 字串 | 載荷 {token}。 **必要欄位**。
Content-Type | 字串 | application/json。 **必要欄位**。

## <a name="request-body"></a>要求正文

在要求內文中，提供應該更新之欄位的值。 在要求內文中未包含的現有屬性會維持其值，除非因相關值的變更而必須重新計算這些屬性。 為了達到最佳效能，您應該省略尚未變更的現有值。

屬性	 | 類型 | 描述
-|-|-
地位 | Enum | 指定警示的目前狀態。 可能的值為： ```Active``` 、 ```Resolved``` 、和 ```Redirected``` 。
分配 | string | 事件的擁有者。
分類 | Enum | 警示的規格。 可能的值為： ```Unknown``` 、 ```FalsePositive``` 、 ```TruePositive``` 。
測定 | Enum | 指定報警的決定。 可能的值為：、、、、、、 ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。
標籤 | 字串清單 | 事件標記清單。

## <a name="response"></a>回應

如果成功，則此方法會傳回 `200 OK` 。 回應內文會包含具有更新屬性的 incident 實體。 如果找不到具有指定識別碼的事件，此方法就會傳回 `404 Not Found` 。

## <a name="example"></a>範例

**請求**

以下是要求的範例。

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

- [存取 Microsoft 365 Defender APIs](api-access.md)
- [深入瞭解 API 限制和授權](api-terms.md)
- [瞭解錯誤碼](api-error-codes.md)
- [事件 API](api-incident.md)
- [列出事件](api-list-incidents.md)
- [事件概觀](incidents-overview.md)
