---
title: Advanced 搜尋架構中的 DeviceNetworkEvents 表格
description: 深入瞭解您可以從高級搜尋架構的 DeviceNetworkEvents 表查詢的網路線上活動
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，table，column，data type，devicenetworkevents，NetworkCommunicationEvents，network connection，remote ip，local ip
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3be6523372edcda520e05545c87385c0e1a42044
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617115"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

適用於：****
- Microsoft 威脅防護



[！附注] `DeviceNetworkEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含有關網路連線和相關事件的資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ActionType` | string | 觸發事件的活動類型 |
| `RemoteIP` | 字串 | 連線到的 IP 位址 |
| `RemotePort` | int | 連線的遠端裝置上的 TCP 埠 |
| `RemoteUrl` | string | 已連線到的 URL 或完整網域名稱 (FQDN) |
| `LocalIP` | string | 指派給通訊期間使用之本機電腦的 IP 位址 |
| `LocalPort` | int | 通訊期間使用的本機電腦上的 TCP 埠 |
| `Protocol` | string | 通訊期間使用的通訊協定 |
| `LocalIPType` | string | IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播 |
| `RemoteIPType` | string | IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播 |
| `InitiatingProcessSHA1` | string | 啟動事件之處理常式（映射檔）的 SHA-1 |
| `InitiatingProcessSHA256` | string | 啟動事件之處理常式（映射檔）的 SHA-256。 此欄位通常未填入，可取得時請使用 SHA1 欄。 |
| `InitiatingProcessMD5` | 字串 | 啟動事件之處理常式（映射檔）的 MD5 雜湊 |
| `InitiatingProcessFileName` | string | 啟動事件的進程名稱 |
| `InitiatingProcessId` | int | 啟動事件之處理常式的進程識別碼（PID） |
| `InitiatingProcessCommandLine` | string | 用來執行啟動事件之處理常式的命令列 |
| `InitiatingProcessCreationTime` | datetime | 啟動事件處理常式的日期和時間 |
| `InitiatingProcessFolderPath` | string | 包含初始化事件之處理常式（映射檔）的資料夾 |
| `InitiatingProcessParentFileName` | string | 產生負責事件之處理常式的父進程名稱 |
| `InitiatingProcessParentId` | int | 產生負責事件之處理常式之父進程的進程識別碼（PID） |
| `InitiatingProcessParentCreationTime` | datetime | 啟動事件之處理常式的父項時的日期和時間 |
| `InitiatingProcessAccountDomain` | string | 執行負責事件之處理常式之帳戶的網域 |
| `InitiatingProcessAccountName` | string | 負責事件之處理常式的帳戶使用者名稱 |
| `InitiatingProcessAccountSid` | string | 執行事件處理常式之帳戶的安全性識別碼（SID） |
| `InitiatingProcessIntegrityLevel` | string | 啟動事件之處理常式的完整性層級。 Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。 這些完整性層級會影響資源的許可權 |
| `InitiatingProcessTokenElevation` | string | 指出是否要將使用者存取控制（UAC）許可權提升套用至啟動事件之處理常式的 Token 類型 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用 |
| `AppGuardContainerId` | string | Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼 |

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
