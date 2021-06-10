---
title: 取得 CVE-KB 地圖 API
description: 瞭解如何使用 [取得 CVE-KB 對應 API]，以在 Microsoft Defender for Endpoint 中從 CVE 的摘要和 CVE 詳細資料中取得 CVE to KB 和 CVE 詳細資料的對應。
keywords: api，graph api，支援的 api，get，cve，kb
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
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166400"
---
# <a name="get-cve-kb-map-api"></a>取得 CVE-KB 地圖 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

會檢索 CVE 的到 KB 和 CVE 詳細資料的對應。

## <a name="permissions"></a>權限
使用者需要讀取權限。

## <a name="http-request"></a>HTTP 要求
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a>要求標頭

頁首 | 值 
:---|:---
授權 | 載荷 {token}。 **必要欄位**。
內容類型 | application/json

## <a name="request-body"></a>要求正文
空白

## <a name="response"></a>回應
如果成功和對應都存在-200 OK。

## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

**回應**

以下是回應的範例。

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
