---
title: 取得 MachineAction 物件 API
description: 瞭解如何使用 Get MachineAction API，以在 Microsoft Defender for Endpoint 中以其識別碼來取得特定的電腦動作。
keywords: api，graph api，支援的 api，machineaction 物件
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
ms.openlocfilehash: dcb00d0d2afc7f873ea9c4afa3174ac46babf879
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770778"
---
# <a name="get-machineaction-api"></a>取得 machineAction API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述
依識別碼檢索特定的 [電腦動作](machineaction.md) 。


## <a name="limitations"></a>限制
1. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。


## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解（包括如何選擇許可權），請參閱 [使用 Defender For Endpoint APIs](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   Read。所有 |  「讀取所有機器設定檔」
應用程式 |   ReadWrite。所有 | 「讀取及寫入所有機器資訊」
委派 (工作或學校帳戶)  | 電腦. 讀取 | 「讀取機器資訊」
委派 (工作或學校帳戶)  | ReadWrite | 「讀取及寫入機器資訊」

>[!Note]
> 使用使用者認證取得權杖時：
>- 使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。


## <a name="request-body"></a>要求正文
空白

## <a name="response"></a>回應
若成功，這個方法會傳回200，具有 [機器動作](machineaction.md) 實體的 Ok 回應碼。 如果找不到具有指定識別碼的 machine action 實體-找不到404。

## <a name="example"></a>範例

**請求**

以下是要求的範例。

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

**回應**

以下是回應的範例。


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}


```
