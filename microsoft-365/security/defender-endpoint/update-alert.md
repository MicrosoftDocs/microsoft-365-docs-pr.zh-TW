---
title: 更新警示實體 API
description: 瞭解如何使用此 API 更新 Microsoft Defender ATP 警示。 您可以更新狀態、判斷、分類及分配屬性。
keywords: api、graph api、支援的 api、get、警示、資訊、識別碼
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7dd3ab3da34efa6cb954db2a596d7a1e48efedf1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199306"
---
# <a name="update-alert"></a>更新警示

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述
更新現有 [警示](alerts.md)的屬性。
<br>提交 **批註** 可用於或不更新屬性。
<br>可更新的屬性包括： ```status``` 、 ```determination``` 、 ```classification``` 和 ```assignedTo``` 。


## <a name="limitations"></a>限制
1. 您可以更新可在 API 中使用的警示。 如需詳細資訊，請參閱 [清單提醒](get-alerts.md) 。
2. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。


## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   警示。 ReadWrite。 |  「讀取及寫入所有警示」
委派 (工作或學校帳戶)  | 警示。 ReadWrite | 「讀取及寫入警示」

>[!Note]
> 使用使用者認證取得權杖時：
>- 使用者至少必須具備下列角色許可權：「警示調查」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) 
>- 使用者必須能夠存取與警示相關聯的裝置，其基礎取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求
```
PATCH /api/alerts/{id}
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
地位 | 字串 | 指定警示的目前狀態。 屬性值為： ' New '、' InProgress ' 和 ' 已解析」。
分配 | 字串 | 警示的擁有者
分類 | 字串 | 指定警示的規格。 屬性值為： ' Unknown '、' FalsePositive '、' TruePositive '。 
測定 | 字串 | 指定報警的決定。 屬性值為： "NotAvailable"、"Apt"、"Malware"、"SecurityPersonnel"、"SecurityTesting"、"UnwantedSoftware"、"Other"
註解 | 字串 | 要新增至警示的批註。

## <a name="response"></a>回應
如果成功，這個方法會傳回 200 OK，以及回應內文中的 [警示](alerts.md) 實體具有更新的屬性。 如果找不到具有指定識別碼的警示-找不到404。


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
