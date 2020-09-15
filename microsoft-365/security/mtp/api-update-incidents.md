---
title: 更新事件 API
description: 瞭解如何使用 Microsoft 威脅防護 API 更新事件
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
ms.openlocfilehash: e790f4f415575323cfdd5fc15db41baa8b59c7f6
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650184"
---
# <a name="update-incidents-api"></a>更新事件 API

適用於：****
- Microsoft 威脅防護

>[!IMPORTANT] 
>一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>API 描述
更新現有事件的屬性。
<br>可更新的屬性包括： ```status``` 、、 ```determination``` ```classification``` 、 ```assignedTo``` 和 ```tags``` 。


## <a name="limitations"></a>限制
1. 此 API 的速率限制為每分鐘50個通話，每小時1500個通話。
2. 您可以設定 [ ```determination``` 只有當分類已設定為 TruePositive]。


## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [Access The Microsoft 威脅防護 APIs](api-access.md)。

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   Incident。 ReadWrite。 |    「讀取和寫入所有事件」
委派 (工作或學校帳戶)  | Incident。 ReadWrite | 「讀取和寫入事件」

>[!NOTE]
> 使用使用者認證取得權杖時：
>- 使用者必須具有更新入口網站中之事件的許可權。


## <a name="http-request"></a>HTTP 要求

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。
Content-Type | 字串 | application/json。 **必要欄位**。


## <a name="request-body"></a>要求正文
在要求內文中，提供應該更新之相關欄位的值。
<br>在要求內文中未包含的現有屬性會維持先前的值，或根據其他屬性值的變更重新計算。 
<br>為了達到最佳效能，您不應包含尚未變更的現有值。

屬性	 | 類型 | 描述
:---|:---|:---
地位 | Enum | 指定警示的目前狀態。 可能的值為 ```Active``` ： ```Resolved``` 和 ```Redirected``` 。
分配 | string | 事件的擁有者。
分類 | Enum | 警示的規格。 可能的值為： ```Unknown``` 、 ```FalsePositive``` 、 ```TruePositive``` 。
測定 | Enum | 指定報警的決定。 可能的值為：、、、、、、 ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。
標籤 | 字串清單 | 事件標記清單。



## <a name="response"></a>回應
如果成功，這個方法會傳回 200 OK，以及回應內文中的事件實體具有更新的屬性。 如果找不到具有指定識別碼的事件-找不到404。


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a>相關主題
- [事件 APIs](api-incident.md)
- [列出事件](api-list-incidents.md)