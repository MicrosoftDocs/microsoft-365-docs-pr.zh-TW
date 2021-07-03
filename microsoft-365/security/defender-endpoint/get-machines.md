---
title: 列出電腦 API
description: 瞭解如何使用清單電腦 API，以取得與 Microsoft Defender for Endpoint cloud 通訊的電腦集合。
keywords: api、graph api、支援的 api、get、裝置
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection: M365-security-compliance
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d52e1b69311c26144684b90545e17934d1223332
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287852"
---
# <a name="list-machines-api"></a>列出電腦 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 描述
檢索與 Microsoft Defender for Endpoint cloud 通訊的 [電腦](machine.md) 集合。
<br>支援 [OData V4 查詢](https://www.odata.org/documentation/)。
<br>支援 OData 的 `$filter` 查詢：、、、 `computerDnsName` `lastSeen` `healthStatus` `osPlatform` `riskScore` 和 `rbacGroupId` 。
<br>在[使用 Defender For Endpoint 的 OData 查詢](exposed-apis-odata-samples.md)中，請參閱範例


## <a name="limitations"></a>限制
1. 您可以根據您設定的保留期間，取得上一個看到的裝置。
2. 頁面大小上限為10000。
3. 此 API 的速率限制為每分鐘100個通話，每小時1500個通話。 


## <a name="permissions"></a>權限

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   Read。所有 |  「讀取所有機器設定檔」
應用程式 |   ReadWrite。所有 | 「讀取及寫入所有機器資訊」
委派 (工作或學校帳戶)  | 電腦. 讀取 | 「讀取機器資訊」
委派 (工作或學校帳戶)  | ReadWrite | 「讀取及寫入機器資訊」

>[!Note]
> 使用使用者認證取得權杖時：
>- 使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) 
>- 回應僅包含使用者有權存取的裝置，並根據裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a>要求標頭

名稱 | 類型 | 說明
:---|:---|:---
授權 | 字串 | 載荷 {token}。 **必要**。


## <a name="request-body"></a>要求內文
空白

## <a name="response"></a>回應
如果成功且機器存在-200 OK （含）主體中的 [機器](machine.md) 實體清單。 如果沒有找到最近的電腦-404。


## <a name="example"></a>範例

**請求**

以下是要求的範例。

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

**回應**

以下是回應的範例。

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a>相關主題
- [使用 Microsoft Defender for Endpoint OData 查詢](exposed-apis-odata-samples.md)
