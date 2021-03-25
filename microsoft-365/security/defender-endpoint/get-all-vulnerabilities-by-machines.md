---
title: 依機器和軟體取得所有的隱患
description: 根據機器及軟體，檢索影響組織的所有安全性漏洞清單。
keywords: api、graph api、支援的 api、get、弱點資訊、mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f7d67948e3b3e7a1a878386a397d2f4a6e8e998e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166402"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a>依機器及軟體列出弱點

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


會檢索影響每個 [機器](machine.md) 及 [軟體](software.md)之組織的所有安全性漏洞清單。
- 如果此弱點已修復 KB，它就會出現在回應中。
- 支援 [OData V4 查詢](https://www.odata.org/documentation/)。
- ```$filter```所有屬性都支援 OData。

>[!Tip]
>這是 [POWER BI 整合](api-power-bi.md)的理想 API。

## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   弱點。 Read。 All |    「讀取威脅及弱點管理弱點資訊」
委派 (工作或學校帳戶)  | 弱點。讀取 |   「讀取威脅及弱點管理弱點資訊」

## <a name="http-request"></a>HTTP 要求
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。


## <a name="request-body"></a>要求正文
空白

## <a name="response"></a>回應
如果成功，這個方法會傳回200的 [確定] 清單中的漏洞。


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

**回應**

以下是回應的範例。


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a>另請參閱

- [風險威脅和弱點管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [組織中的薄弱環節](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
