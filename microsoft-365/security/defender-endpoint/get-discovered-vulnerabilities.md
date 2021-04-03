---
title: 取得發現的弱點
description: 會檢索與指定裝置識別碼相關的已探索弱點的集合。
keywords: api，graph api，支援的 api，get，list，file，information，發現的弱點，威脅 & 漏洞管理 api，mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 73b8fe5140ff635791e7d42358024bb7fb4ee926
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570324"
---
# <a name="get-discovered-vulnerabilities"></a>取得發現的弱點

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 描述
會檢索與指定裝置識別碼相關的已探索弱點的集合。

## <a name="limitations"></a>限制
1. 此 API 的速率限制為每分鐘50個通話，每小時1500個通話。

## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 | 權限 | 許可權顯示名稱
:---|:---|:---
應用程式 |弱點。 Read。 All | 「讀取威脅及弱點管理弱點資訊」
委派 (工作或學校帳戶)  | 弱點。讀取 | 「讀取威脅及弱點管理弱點資訊」

## <a name="http-request"></a>HTTP 要求

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 說明
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。

## <a name="request-body"></a>要求正文

空白

## <a name="response"></a>回應

如果成功，這個方法會傳回200，並顯示本文中所發現的弱點資訊。

## <a name="example"></a>範例

### <a name="request"></a>請求

以下是要求的範例。

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a>回應

以下是回應的範例。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
}
```

## <a name="see-also"></a>另請參閱

- [風險威脅 & 弱點管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [組織中的薄弱環節](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
