---
title: 取得披露分數
description: 會檢索組織公開分數。
keywords: api、graph api、支援的 api、get、洩密分數、組織公開分數
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7037e49a7f750597af15cfb16e1552aeb98859a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166395"
---
# <a name="get-exposure-score"></a>取得披露分數

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

會檢索組織公開分數。

## <a name="permissions"></a>權限

需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 | 權限 | 許可權顯示名稱
:---|:---|:---
應用程式 | Read。所有 | 「讀取威脅和弱點管理得分」
委派 (工作或學校帳戶)  | 讀取 | 「讀取威脅和弱點管理得分」

## <a name="http-request"></a>HTTP 要求

```
GET /api/exposureScore
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。

## <a name="request-body"></a>要求正文

空白

## <a name="response"></a>回應

如果成功，這個方法會傳回 200 OK，並在回應內文中包含曝光資料。

## <a name="example"></a>範例

### <a name="request"></a>請求

以下是要求的範例。

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a>回應

以下是回應的範例。

>[!NOTE]
>在這裡顯示的回應清單可能會因簡潔而截斷。 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a>另請參閱

- [風險威脅 & 弱點管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [威脅 & 漏洞洩密分數](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
