---
title: DeviceNetworkInfo 資料表中的進階的狩獵結構描述
description: 了解 DeviceNetworkInfo 表格中的進階的狩獵結構描述的網路組態資訊
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 描述、 machinenetworkinfo，DeviceNetworkInfo，裝置]，機器、 mac、 ip、 介面卡、 dns、 dhcp、 閘道、 通道
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 938eb02da1b37f27f15f06ad67748a9e3beca68a
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210415"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

適用於：****
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`DeviceNetworkInfo` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含機器，包括網路介面卡、 IP 與 MAC 位址，並已連線的網路或網域的網路組態的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | 字串 | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄 |
| `NetworkAdapterName` | string | 網路介面卡的名稱 |
| `MacAddress` | string | 網路介面卡的 MAC 位址 |
| `NetworkAdapterType` | string | 網路介面卡類型。 可能的值，請參閱[此列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | string | 網路介面卡的作業狀態。 可能的值，請參閱[此列舉](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | string | 通道通訊協定，如果介面可用於此目的，例如 6to4、 Teredo、 ISATAP、 PPTP、 SSTP 及 SSH |
| `ConnectedNetworks` | string | 網路介面卡所連接的連接。 每一個 JSON 陣列包含的網路名稱、 類別 （公用、 私用或網域）、 描述及旗標，指出是否它連線公開至網際網路 |
| `DnsAddresses` | string | DNS 伺服器位址，以 JSON 陣列格式 |
| `IPv4Dhcp` | string | DHCP 伺服器的 IPv4 位址 |
| `IPv6Dhcp` | string | IPv6 位址的 DHCP 伺服器 |
| `DefaultGateways` | string | 以 JSON 陣列格式的預設閘道地址 |
| `IPAddresses` | string | JSON 陣列，其中包含所有指派給介面卡，以及其各自的子網路前置詞和 IP 位址空間，例如公用、 私用] 或連結-本機的 IP 位址 |

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
