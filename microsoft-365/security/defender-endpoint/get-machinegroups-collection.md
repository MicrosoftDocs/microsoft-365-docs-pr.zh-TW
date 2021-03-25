---
title: 取得 RBAC 機器群組集合 API
description: 瞭解如何使用「取得 KB 集合 API」，在 Microsoft Defender 高級威脅防護中取得 RBAC 裝置群組的集合。
keywords: api、graph api、支援的 api、get、RBAC、group
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
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166426"
---
# <a name="get-kb-collection-api"></a>取得 KB 集合 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


會檢索 RBAC 裝置群組的集合。

## <a name="permissions"></a>權限
使用者需要讀取權限。

## <a name="http-request"></a>HTTP 要求
```
GET /testwdatppreview/machinegroups
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
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

**回應**

以下是回應的範例。
欄位識別碼包含裝置資訊中的裝置群組 **識別碼** 及等於欄位 **rbacGroupId** 。 [！注意] 只有一個群組適用于尚未指派給任何群組的所有裝置的欄位 **取消** 群組功能。 這個群組的一般名稱為 "UnassignedGroup"。

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
