---
title: Microsoft 365 Defender 的高級搜尋中的 AssignedIPAddresses () 功能
description: 瞭解如何使用 AssignedIPAddresses () 函數來取得指派給裝置的最新 IP 位址
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，FileProfile，file profile，function，豐富
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3760ff84e6abfbe05d9e4605d64087d0077300e3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058060"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

使用 `AssignedIPAddresses()` 您的 [高級搜尋](advanced-hunting-overview.md) 查詢中的功能，快速取得指派給裝置的最新 IP 位址。 如果您指定的是 timestamp 引數，此函數會在指定的時間取得最近的 IP 位址。 

此函數會傳回含下列各欄的資料表：

| 欄 | 資料類型 | 描述 |
|------------|-------------|-------------|
| `Timestamp` | datetime | 使用 IP 位址觀測裝置的最晚時間 |
| `IPAddress` | string | 裝置使用的 IP 位址 |
| `IPType` | string | 指出 IP 位址是否為公用或私人位址 |
| `NetworkAdapterType` | int | 已獲指派 IP 位址之裝置使用的網路介面卡類型。 如需可能的值，請參閱 [this 列舉](/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | 與指派之 IP 位址的介面卡相連的網路。 每個 JSON 陣列都包含網路名稱、類別 (public、private 或 domain) 、描述，以及表明其是否已公開連接到網際網路的旗標。 |

## <a name="syntax"></a>語法

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>引數

- **x** `DeviceId` 或 `DeviceName` 值，用以識別裝置
- **y**- `Timestamp` (datetime) 值指示函數從特定時間取得最近指派的 IP 位址。 若未指定，該函數會傳回最新的 IP 位址。

## <a name="examples"></a>範例

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>取得裝置24小時前使用的 IP 位址清單

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>取得裝置使用的 IP 位址，並尋找與其通訊的裝置
此查詢使用此 `AssignedIPAddresses()` 函數來取得 `example-device-name` 在特定日期 () 之前或之前的裝置 () 的指派 IP 位址 `example-date` 。 然後，它會使用 IP 位址尋找其他裝置所初始化之裝置的連線。 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-tables.md)