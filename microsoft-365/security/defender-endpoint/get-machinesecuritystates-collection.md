---
title: 取得電腦安全性性狀態集合 API
description: 使用 Microsoft Defender for Endpoint 來檢索裝置安全性狀態的集合。
keywords: api、graph api、支援的 api、get、device、security、state
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200362"
---
# <a name="get-machines-security-states-collection-api"></a>取得電腦安全性性狀態集合 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

會檢索裝置安全性狀態的集合。

## <a name="permissions"></a>權限
使用者需要讀取權限。

## <a name="http-request"></a>HTTP 要求
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a>要求標頭

Header | 值 
:---|:---
授權 | 載荷 {token}。 **必要欄位**。
內容類型 | application/json

## <a name="request-body"></a>要求正文
空白

## <a name="response"></a>回應
如果成功-200 確定。

## <a name="example"></a>範例

**請求**

以下是要求的範例。

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

**回應**

以下是回應的範例。
欄位 *識別碼* 包含裝置識別碼，且等於裝置資訊中的欄位 *識別碼**。 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
