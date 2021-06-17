---
title: 取得 IP 統計資料 API
description: 使用 Microsoft Defender for Endpoint 取得 IP 的最新統計資訊。
keywords: api、graph api、支援的 api、get、ip、統計資料、流行
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
ms.openlocfilehash: 4919f082c115d8a57960ec49532b6cda6a63833f
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998725"
---
# <a name="get-ip-statistics-api"></a>取得 IP 統計資料 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 描述
取得指定 IP 的統計資料。

## <a name="limitations"></a>限制
1. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。

## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   已讀取的 Ip。全部 |   「讀取 IP 位址設定檔」
委派 (工作或學校帳戶)  | 已讀取的 Ip。全部 |  「讀取 IP 位址設定檔」

>[!NOTE]
> 使用使用者認證取得權杖時：
>- 使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 描述
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要欄位**。

## <a name="request-uri-parameters"></a>要求 URI 參數

名稱 | 類型 | 描述
:---|:---|:---
lookBackHours | Int32 | 定義我們回叫以取得統計資料的小時數。 預設為30天。 此為選擇性欄位。

## <a name="request-body"></a>要求內文
空白

## <a name="response"></a>回應
如果成功，且 ip 存在-200，包含正文中的統計資料。 IP 不存在-找不到404。


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

**回應**

以下是回應的範例。


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| 名稱 | 描述 |
| :--- | :---------- |
| 組織的流行 | 開啟此 IP 之網路連線的裝置的 distinct 計數。 |
| 第一次查看的組織 | 組織中第一個此 IP 的連線。 |
| 上次查看的組織  | 組織中此 IP 的最後一個連接。 |

> [!NOTE]
> 這項統計資料是以過去30天內的資料為基礎。 
