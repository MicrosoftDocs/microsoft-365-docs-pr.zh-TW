---
title: Microsoft 365Defender 高級搜尋 API
description: 瞭解如何使用 Microsoft 365 Defender 的高級搜尋 API 執行高級搜尋查詢
keywords: 高級搜尋、APIs、api、M365 defender、Microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3ff62265783be846a95964164e372100fe1ef662
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769582"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365Defender 高級搜尋 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。 Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。

「[高級搜尋](advanced-hunting-overview.md)」是一個威脅搜尋工具，使用[專門構造的查詢](advanced-hunting-query-language.md)來檢查過去30天中 Microsoft 365 Defender 的事件資料。 您可以使用高級搜尋查詢檢查不尋常的活動、偵測可能的威脅，甚至回應攻擊。 Advanced 搜尋 API 可讓您以程式設計方式查詢事件資料。

## <a name="quotas-and-resource-allocation"></a>配額和資源配置

下列條件會與所有查詢相關。

1. 查詢會探索和傳回過去30天的資料。
2. 結果最多可返回100000列。
3. 每個租使用者最多可讓15個通話每分鐘一次。
4. 如果租使用者到達100%，直到接下來的15分鐘週期過後，便會封鎖查詢。
5. 如果單一要求的執行時間超過10分鐘，它會超時並傳回錯誤。
6. `429`HTTP 回應碼表示您已到達配額（按傳送的要求數目，或已分派的執行時間）。 請閱讀回應本文，以瞭解您已達到的限制。 

> [!NOTE]
> 以上所列的所有配額 (例如每個承租人大小每分鐘15個通話) 。 這些配額是最小值。

## <a name="permissions"></a>權限

需要有下列其中一個許可權，才能呼叫高級搜尋 API。 若要深入瞭解，包括如何選擇許可權，請參閱[Access the Microsoft 365 Defender Protection APIs](api-access.md)

許可權類型 | 權限 | 許可權顯示名稱
-|-|-
應用程式 | AdvancedHunting Read。 All | 執行高級查詢
委派 (工作或學校帳戶)  | AdvancedHunting 讀取 | 執行高級查詢

>[!Note]
> 使用使用者認證取得權杖時：
>
>- 使用者必須具有「查看資料 ' AD 角色
>- 使用者必須根據裝置群組設定，才能存取裝置。

## <a name="http-request"></a>HTTP 要求

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>要求標頭

頁首 | 值
-|-
授權 | 載荷 {token} **附注：必要**
Content-Type | application/json

## <a name="request-body"></a>要求正文

在要求主體中，提供具有下列參數的 JSON 物件：

參數 | 類型 | 描述
-|-|-
查詢 | 文字 | 要執行的查詢。 **附注：必要**

## <a name="response"></a>回應

如果成功，此方法將會傳回 `200 OK` ，以及回應內文中的 _QueryResponse_ 物件。

Response 物件包含三個最上層的屬性：

1. Stats-查詢效能統計資料的字典。
2. 架構-回應的架構，每個資料欄的 Name-Type 對的清單。
3. 結果-高級搜尋事件清單。

## <a name="example"></a>範例

在下列範例中，使用者會傳送下列查詢並接收包含、和的 API 回應 `Stats` 物件 `Schema` `Results` 。

### <a name="query"></a>查詢

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>Response 物件

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

- [存取 Microsoft 365 Defender APIs](api-access.md)
- [深入瞭解 API 限制和授權](api-terms.md)
- [瞭解錯誤碼](api-error-codes.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
