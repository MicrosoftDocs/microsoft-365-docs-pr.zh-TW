---
title: 批次更新警示實體 API
description: 瞭解如何使用此 API 更新批次中的 Microsoft Defender for Endpoint 警示。 您可以更新狀態、判斷、分類及分配屬性。
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
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166449"
---
# <a name="batch-update-alerts"></a>批次更新提醒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述
更新現有 [警示](alerts.md)批次的屬性。
<br>提交 **批註** 可用於或不更新屬性。
<br>可更新的屬性包括： `status` 、 `determination` 、 `classification` 和 `assignedTo` 。


## <a name="limitations"></a>限制
1. 您可以更新 API 中可用的警示。 如需詳細資訊，請參閱 [清單提醒](get-alerts.md) 。
2. 此 API 的速率限制為每分鐘10個通話，每小時500個通話。


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
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。
Content-Type | 字串 | application/json。 **必要欄位**。


## <a name="request-body"></a>要求正文
在 [要求內文] 中，提供要更新之警示的 IDs，以及您想要更新這些警示之相關欄位的值。
<br>在要求內文中未包含的現有屬性會維持先前的值，或根據其他屬性值的變更重新計算。 
<br>為了達到最佳效能，您不應包含尚未變更的現有值。

屬性	 | 類型 | 描述
:---|:---|:---
alertIds | 清單 &lt; 字串&gt;| 要更新之警示的 IDs 清單。 **Required**
地位 | 字串 | 指定所指定警示的更新狀態。 屬性值為： ' New '、' InProgress ' 和 ' 已解析」。
分配 | 字串 | 指定警示的擁有者
分類 | 字串 | 指定所指定警示的規格。 屬性值為： ' Unknown '、' FalsePositive '、' TruePositive '。 
測定 | 字串 | 指定所指定提醒的確定。 屬性值為： "NotAvailable"、"Apt"、"Malware"、"SecurityPersonnel"、"SecurityTesting"、"UnwantedSoftware"、"Other"
註解 | 字串 | 要新增至指定提醒的批註。

## <a name="response"></a>回應
如果成功，這個方法會傳回 200 OK，並提供空白的回應內文。


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
