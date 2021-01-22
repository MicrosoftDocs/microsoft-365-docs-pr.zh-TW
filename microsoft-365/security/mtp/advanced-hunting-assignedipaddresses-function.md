---
title: AssignedIPAddresses () 函數在 Microsoft 365 Defender 進步搜尋中
description: 瞭解如何使用 AssignedIPAddresses () 函數，以取得指派給裝置的最新 IP 位址
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、FileProfile、檔案設定檔、函數、擴充
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d16cd7efc49cc2498eff3f705bb43fa62f37d975
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933015"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

在 `AssignedIPAddresses()` 進位搜尋 [查詢中使用此](advanced-hunting-overview.md) 函數來快速取得已指派給裝置的最新 IP 位址。 如果您指定時間戳記引數，此函數會于指定時間取得最新的 IP 位址。 

此函數會返回具有下列資料行的表格：

| 欄 | 資料類型 | 描述 |
|------------|-------------|-------------|
| `Timestamp` | datetime | 裝置使用 IP 位址觀察的最近時間 |
| `IPAddress` | string | 裝置使用的 IP 位址 |
| `IPType` | string | 指出 IP 位址是公用還是私人位址 |
| `NetworkAdapterType` | int | 已指派 IP 位址之裝置使用的網路介面卡類型。 有關可能的值，請參閱 [此列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | 具有已指派 IP 位址的介面卡所連接的網路。 每個 JSON 陣列都包含網路名稱、類別 (公用、私人或網域) 、描述及旗標，指出該陣列是否公開連接至網際網路 |

## <a name="syntax"></a>語法

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>引數

- **x** `DeviceId` — `DeviceName` 或識別裝置的值
- **y**— (時間) 值，指示函數從特定時間取得最近指派的 `Timestamp` IP 位址。 如果未指定，函數會回電最新的 IP 位址。

## <a name="examples"></a>範例

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>取得裝置 24 小時前使用的 IP 位址清單

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>取得裝置使用的 IP 位址，並尋找與裝置通訊的裝置
此查詢會使用函數，取得特定日期或 () 裝置所指派的 IP `AssignedIPAddresses()` `example-device-name` `example-date` 位址 () 。 接著，它會使用 IP 位址尋找由其他裝置啟動之裝置的連接。 

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
