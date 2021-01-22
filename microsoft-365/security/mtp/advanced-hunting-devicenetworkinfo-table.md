---
title: 進位搜尋架構中的 DeviceNetworkInfo 資料表
description: 在進位搜尋架構的 DeviceNetworkInfo 資料表中瞭解網路組式資訊
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、machinenetworkinfo、DeviceNetworkInfo、裝置、電腦、mac、ip、配卡、dns、dhcp、閘道、裝置
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
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931203"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender



進位搜尋架構中的表格包含機器網路設定的資訊，包括網路介面卡、IP 和 MAC 位址， `DeviceNetworkInfo` 以及已連接的網路或網域。 [](advanced-hunting-overview.md) 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一事件，此欄必須與 DeviceName 和時間戳記欄一起使用 |
| `NetworkAdapterName` | string | 網路介面卡的名稱 |
| `MacAddress` | string | 網路介面卡的 MAC 位址 |
| `NetworkAdapterType` | string | 網路介面卡類型。 有關可能的值，請參閱 [此列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | string | 網路介面卡的營運狀態。 有關可能的值，請參閱 [此列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | string | 如果介面用於此目的 ，例如 6to4、Teredo、ISATAP、PPTP、SSTP 和 SSH，則建立通訊協定 |
| `ConnectedNetworks` | string | 介面卡所連接的網路。 每個 JSON 陣列都包含網路名稱、類別 (公用、私人或網域) 、描述，以及指出該陣列是否公開連接至網際網路的標標。 |
| `DnsAddresses` | string | JSON 陣列格式的 DNS 伺服器位址 |
| `IPv4Dhcp` | string | DHCP 伺服器的 IPv4 位址 |
| `IPv6Dhcp` | string | DHCP 伺服器的 IPv6 位址 |
| `DefaultGateways` | string | JSON 陣列格式的預設閘道位址 |
| `IPAddresses` | string | JSON 陣列，其中包含指派給配卡的所有 IP 位址，以及各自的子網首碼和 IP 位址空間，例如公用、私人或 link-local |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
