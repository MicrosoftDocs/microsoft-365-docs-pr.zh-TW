---
title: 進階搜捕 API
ms.reviewer: ''
description: 瞭解如何使用高級搜尋 API，在 Microsoft Defender for Endpoint 上執行高級查詢。 深入瞭解限制，並查看範例。
keywords: api、支援的 api、高級搜尋、查詢
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
ms.technology: mde
ms.openlocfilehash: caf7a1bacfd726c560356d542bec3cf56c6b39d4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200194"
---
# <a name="advanced-hunting-api"></a>高級搜尋 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a>限制
1. 您只可對過去30天的資料執行查詢。
2. 結果最多會包含100000列。
3. 每個租使用者的執行數目有限：
   - API 呼叫：每分鐘最多45個通話。
   - 執行時間：每小時10分鐘的執行時間，以及一天的執行時間的3個小時的執行時間。
4. 單一要求的最長執行時間為10分鐘。
5. 429回應會以要求數目或 CPU 來表示達到配額限制。 閱讀回應正文，以瞭解已達到的限制。 

## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   AdvancedQuery Read。 All |    「執行高級查詢」
委派 (工作或學校帳戶)  | AdvancedQuery 讀取 | 「執行高級查詢」

>[!Note]
> 使用使用者認證取得權杖時：
>- 使用者必須具有「查看資料 ' AD 角色
>- 使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) 

## <a name="http-request"></a>HTTP 要求
```
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>要求標頭

Header | 值 
:---|:---
授權 | 載荷 {token}。 **必要欄位**。
Content-Type    | application/json

## <a name="request-body"></a>要求正文
在要求主體中，提供具有下列參數的 JSON 物件：

參數 | 類型    | 描述
:---|:---|:---
查詢 | 文字 |  要執行的查詢。 **必要欄位**。

## <a name="response"></a>回應
如果成功，這個方法會傳回 200 OK，並在回應內文中 _QueryResponse_ 物件。


## <a name="example"></a>範例

請求

以下是要求的範例。

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

回應

以下是回應的範例。

>[!NOTE]
>在這裡顯示的回應物件可能會因簡潔而截斷。 所有屬性都將從實際通話傳回。

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topic"></a>相關主題
- [Microsoft Defender for Endpoint APIs 簡介](apis-intro.md)
- [從入口網站的高級搜尋](advanced-hunting-query-language.md)
- [使用 PowerShell 的高級搜尋](run-advanced-query-sample-powershell.md)
