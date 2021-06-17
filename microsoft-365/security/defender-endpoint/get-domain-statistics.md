---
title: 取得網域統計資料 API
description: 瞭解如何使用取得網域統計資料 API，在 Microsoft Defender for Endpoint 中取得指定網域上的統計資料。
keywords: api、graph api、支援的 api、get、domain、domain 相關裝置
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
ms.openlocfilehash: 50b05b98ba507e120bbd6a3dc09f4633dac3a005
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998773"
---
# <a name="get-domain-statistics-api"></a>取得網域統計資料 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 描述
在指定的網域上檢索統計資料。


## <a name="limitations"></a>限制
1. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。


## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   URL:。Read。所有 |  「讀取 URLs '
委派 (工作或學校帳戶)  | URL:。Read。所有 | 「讀取 URLs '

>[!Note]
> 使用使用者認證取得權杖時：
>- 使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a>要求標頭

標頭 | 值 
:---|:---
授權 | 載荷 {token}。 **必要欄位**。

## <a name="request-uri-parameters"></a>要求 URI 參數

名稱 | 類型 | 描述
:---|:---|:---
lookBackHours | Int32 | 定義我們回叫以取得統計資料的小時數。 預設為30天。 此為選擇性欄位。

## <a name="request-body"></a>要求內文
空白

## <a name="response"></a>回應
如果成功且網域存在-200 OK，包含回應內文的統計資料物件。 如果網域不存在-找不到404。


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

**回應**

以下是回應的範例。


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "organizationPrevalence": 4070,
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
