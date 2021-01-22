---
title: Microsoft 365 Defender 進位搜尋 API
description: 瞭解如何使用 Microsoft 365 Defender 進位搜尋 API 執行進位搜尋查詢
keywords: 進位搜尋、API、api、MTP、M365 Defender、Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 4213773c3305c28f0913013d8f7634c083811f52
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932079"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender Advanced 搜尋 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 威脅防護

> [!IMPORTANT]
> 部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

[進位](advanced-hunting-overview.md) 搜尋是威脅搜尋工具，使用 [特殊](advanced-hunting-query-language.md) 建構的查詢來檢查過去 30 天 Microsoft 365 Defender 中的事件資料。 您可以使用進一步搜尋查詢來檢查異常活動、偵測可能的威脅，甚至回應攻擊。 進位搜尋 API 可讓您程式化查詢事件資料。

## <a name="quotas-and-resource-allocation"></a>配額和資源配置

下列條件會與其他查詢相關。

1. 查詢會探索並返回過去 30 天的資料。
2. 結果可返回最多 100，000 列。
3. 您每一個租使用者每分鐘可以撥打多達 10 個通話。
4. 每個租使用者每小時有 10 分鐘的執行時間。
5. 每個租使用者都有四個總執行時間。
6. 如果單一要求執行時間超過 10 分鐘，就會將時間用完並退回錯誤。
7. HTTP 回應碼表示您已達到配額，可以是已傳送的要求數，或是已分配 `429` 執行時間。 回復內體會包含重設您達到之配額之前的時間。

## <a name="permissions"></a>權限

需要下列其中一個許可權才能呼叫進一步搜尋 API。 若要深入瞭解，包括如何選擇許可權，請參閱 [存取 Microsoft 365 Defender Protection API](api-access.md)

許可權類型 | 權限 | 許可權顯示名稱
-|-|-
應用程式 | AdvancedHunting.Read.All | 執行進位查詢
已委派 (公司或學校帳戶)  | AdvancedHunting.Read | 執行進位查詢

>[!Note]
> 使用使用者認證取得權杖時：
>
>- 使用者必須擁有 'View Data' AD 角色
>- 使用者必須能根據裝置群組設定存取裝置。

## <a name="http-request"></a>HTTP 要求

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>要求標頭

Header | 值
-|-
授權 | Bearer {token} **Note： required**
Content-Type | application/json

## <a name="request-body"></a>要求內體

在要求內文中，提供 JSON 物件與下列參數：

參數 | 類型 | 說明
-|-|-
查詢 | 文字 | 要執行的查詢。 **注意：必填**

## <a name="response"></a>回應

如果成功，此方法會傳回，且回應本文中會傳回 `200 OK` _QueryResponse_ 物件。

回應物件包含三個頂層屬性：

1. 狀態 - 查詢績效統計的字典。
2. 架構 - 回應的架構，一份每個Name-Type組的清單。
3. 結果 - 進位搜尋事件的清單。

## <a name="example"></a>範例

在下列範例中，使用者傳送下列查詢並接收包含 、及 的 API `Stats` `Schema` 回應物件 `Results` 。

### <a name="query"></a>查詢

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>回應物件

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

## <a name="related-articles"></a>相關文章

- [存取 Microsoft 365 Defender API](api-access.md)
- [瞭解 API 限制與授權](api-terms.md)
- [瞭解錯誤碼](api-error-codes.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
