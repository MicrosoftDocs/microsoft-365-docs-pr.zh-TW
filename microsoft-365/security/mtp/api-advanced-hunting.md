---
title: 高級搜尋 APIs
description: 瞭解如何使用 Microsoft 365 Defender API 執行高級搜尋查詢
keywords: 高級搜尋、APIs、api、MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c43d263009578af6280ffdc780ab0f9a174a3b97
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844029"
---
# <a name="advanced-hunting-apis"></a>高級搜尋 APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

>[!IMPORTANT] 
>一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="limitations"></a>限制
1. 您只可對過去30天的資料執行查詢。
2. 結果最多會包含100000列。
3. 執行數目會限制于每個承租人：每分鐘最多10個通話量、每小時10分鐘的執行時間，以及一天的執行時間的4小時的執行時間。
4. 單一要求的最長執行時間為10分鐘。
5. 429回應會以要求數目或 CPU 來表示達到配額限制。 429回應內文也會指出在更新配額之前所用的時間。 


## <a name="permissions"></a>權限
需要有下列其中一個許可權才能呼叫此 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [Access The Microsoft 365 Defender APIs](api-access.md)

許可權類型 |   權限  |   許可權顯示名稱
:---|:---|:---
應用程式 |   AdvancedHunting Read。 All |  「執行高級查詢」
委派 (工作或學校帳戶)  | AdvancedHunting 讀取 | 「執行高級查詢」

>[!Note]
> 使用使用者認證取得權杖時：
>- 使用者必須具有「查看資料 ' AD 角色
>- 使用者必須根據裝置群組設定，才能存取裝置。

## <a name="http-request"></a>HTTP 要求
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>要求標頭

Header | 值 
:---|:---
授權 | 載荷 {token}。 **必要欄位** 。
Content-Type    | application/json

## <a name="request-body"></a>要求正文
在要求主體中，提供具有下列參數的 JSON 物件：

參數 | 類型    | 描述
:---|:---|:---
查詢 | 文字 |  要執行的查詢。 **必要欄位** 。

## <a name="response"></a>回應
如果成功，這個方法會傳回 200 OK，並在回應內文中 _QueryResponse_ 物件。 <br><br>

Response 物件會劃分成3個部分 (屬性) ：<br>
1) ```Stats``` -查詢效能統計資料。<br>
2) ```Schema``` -回應的架構，每一欄的 Name-Type 組的清單。 <br>
3) ```Results``` -高級搜尋事件清單。

## <a name="example"></a>範例

請求

以下是要求的範例。


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

回應

以下是回應的範例。


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a>相關主題
- [存取 Microsoft 365 Defender APIs](api-access.md)
