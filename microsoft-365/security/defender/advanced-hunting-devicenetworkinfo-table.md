---
title: Advanced 搜尋架構中的 DeviceNetworkInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceNetworkInfo 資料表中的網路設定資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，table，column，data type，description，machinenetworkinfo，DeviceNetworkInfo，device，dhcp，adapter，隧道
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6d860e20bdd116d579b3cb178e3352825c60fe44
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500907"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender



[！附注] `DeviceNetworkInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含電腦網路設定的相關資訊，包括網路介面卡、IP 及 MAC 位址，以及連線的網路或網域。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `NetworkAdapterName` | string | 網路介面卡的名稱 |
| `MacAddress` | string | 網路介面卡的 MAC 位址 |
| `NetworkAdapterType` | string | 網路介面卡類型。 如需可能的值，請參閱 [this 列舉](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | string | 網路介面卡的運作狀態。 如需可能的值，請參閱 [this 列舉](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | string | 隧道通訊協定，如果此介面是用於此用途，例如6to4、Teredo、ISATAP、PPTP、SSTP 和 SSH |
| `ConnectedNetworks` | string | 連接到配接器的網路。 每個 JSON 陣列都包含網路名稱、類別 (public、private 或 domain) 、描述及表明其是否已公開連接到網際網路的標誌。 |
| `DnsAddresses` | string | JSON 陣列格式的 DNS 伺服器位址 |
| `IPv4Dhcp` | string | DHCP 伺服器的 IPv4 位址 |
| `IPv6Dhcp` | string | DHCP 伺服器的 IPv6 位址 |
| `DefaultGateways` | string | 以 JSON 陣列格式的預設閘道位址 |
| `IPAddresses` | string | 包含所有指派給該配接器之 IP 位址的 JSON 陣列，以及其各自的子網前置詞和 IP 位址空間，例如 public、private 或 link 本機。 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)