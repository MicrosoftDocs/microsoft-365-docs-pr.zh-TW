---
title: 取得電腦登入使用者 API
description: 瞭解如何使用「取得機器登入使用者」 API，在 Microsoft Defender for Endpoint 中的裝置上，取回已登入使用者的集合。
keywords: api、graph api、支援的 api、get、device、登入、使用者
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 634a381ca862dc7580d82168a4b9540acc0cd394
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229020"
---
# <a name="get-machine-logon-users-api"></a>取得電腦登入使用者 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述
在特定裝置上檢索登入使用者的集合。

## <a name="limitations"></a>限制
1. 您可以根據您設定的保留期間，查詢上次更新的警示。
2. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。

## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 |權限|許可權顯示名稱
:---|:---|:---
應用程式 |User.Read.All |「讀取使用者設定檔」
委派 (工作或學校帳戶)  | User.Read.All | 「讀取使用者設定檔」

> [!NOTE]
> 使用使用者認證取得權杖時：
>
> - 使用者至少必須具備下列角色許可權：「View Data」。 如需詳細資訊，請參閱 [Create and manage roles](user-roles.md)) 。
> - 只有當使用者可以看見裝置時，回應才會包含使用者，視裝置群組設定而定。 如需詳細資訊，請參閱 [Create and manage device groups](machine-groups.md)。

## <a name="http-request"></a>HTTP 要求

```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要**。

## <a name="request-body"></a>要求內文

空白

## <a name="response"></a>回應

如果成功和裝置都存在-200 OK （含）主體中的 [使用者](user.md) 實體清單。 如果找不到裝置-找不到404。

## <a name="example"></a>範例

### <a name="request"></a>請求

以下是要求的範例。

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

### <a name="response"></a>回應

以下是回應的範例。

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
