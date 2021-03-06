---
title: 依識別碼取得軟體
description: 依設備群組來檢索曝光分數的清單。
keywords: api，graph api，支援的 api，get，軟體，Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d9a7d97cea96f919f1ec7cd1e37e7a8f27042c79
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845087"
---
# <a name="get-software-by-id"></a>依識別碼取得軟體

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

依識別碼檢索軟體詳細資料。

## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 | 已讀取軟體。所有 | 「讀取威脅和弱點管理軟體資訊」
委派 (工作或學校帳戶)  | 軟體. 讀取 | 「讀取威脅和弱點管理軟體資訊」

## <a name="http-request"></a>HTTP 要求
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a>要求標頭

| 名稱        | 類型 | 描述
|:--------------|:-------|:--------------|
| 授權 | 字串 | 載荷 {token}。**必要**。

## <a name="request-body"></a>要求正文
空白

## <a name="response"></a>回應
如果成功，這個方法會以本文中指定的軟體資料傳回 200 OK。 


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

**回應**

以下是回應的範例。

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a>相關主題
- [風險威脅 & 弱點管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [威脅 & 弱點軟體清單](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
