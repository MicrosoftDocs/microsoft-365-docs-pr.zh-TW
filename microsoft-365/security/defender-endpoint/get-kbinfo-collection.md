---
title: 取得 KB 集合 API
description: 使用 Microsoft Defender for Endpoint，檢索知識文庫的集合 (KB 的) 和 KB 詳細資料。
keywords: api、graph api、支援的 api、get、kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166478"
---
# <a name="get-kb-collection-api"></a>取得 KB 集合 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

會檢索 KB 的和 KB 詳細資料的集合。

## <a name="permissions"></a>權限
使用者需要讀取權限。

## <a name="http-request"></a>HTTP 要求
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a>要求標頭

頁首 | 值 
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

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

**回應**

以下是回應的範例。

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
