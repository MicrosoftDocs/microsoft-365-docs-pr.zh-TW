---
title: 清單調查 API
description: 使用此 API 來建立與取得調查集合相關的呼叫
keywords: api，graph api，支援的 api，調查集合
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 38485a5028626153c26cd1e11537ef7a2daf5296
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770142"
---
# <a name="list-investigations-api"></a>清單調查 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述
會檢索 [調查](investigation.md)的集合。
<br>支援 [OData V4 查詢](https://www.odata.org/documentation/)。
<br>支援 OData 的 ```$filter``` 查詢： ```startTime``` 、 ```state``` ```machineId``` 和 ```triggeringAlertId``` 屬性。
<br>請參閱[使用 Microsoft Defender For Endpoint 的 OData 查詢](exposed-apis-odata-samples.md)中的範例


## <a name="limitations"></a>限制
1. 頁面大小上限為10000。
2. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。 


## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   警示。已讀取。所有 |    「讀取所有警示」
應用程式 |   警示。 ReadWrite。 |   「讀取及寫入所有警示」
委派 (工作或學校帳戶)  | 警示。讀取 | 「讀取警示」
委派 (工作或學校帳戶)  | 警示。 ReadWrite | 「讀取及寫入警示」

>[!Note]
> 使用使用者認證取得權杖時：
>- 使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。


## <a name="request-body"></a>要求正文
空白

## <a name="response"></a>回應
若成功，這個方法會以 [調查](investigation.md) 條目的集合傳回200、Ok 回應碼。


## <a name="example"></a>範例

**請求**

以下是取得所有調查之要求的範例： 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

**回應**

以下是回應的範例：

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
