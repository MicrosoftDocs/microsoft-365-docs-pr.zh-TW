---
title: Advanced 搜尋架構中的 DeviceNetworkEvents 表格
description: 深入瞭解您可以從高級搜尋架構的 DeviceNetworkEvents 表查詢的網路線上活動
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、schema reference、kusto、table、column、data type、devicenetworkevents、network connection、remote ip、local ip、NetworkCommunicationEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8c43d8ca790f246415a0419bca0adc3a21c92a84
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059791"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[！附注] `DeviceNetworkEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含有關網路連線和相關事件的資訊。 使用這個參考來建立從表格取回之資訊的查詢。

如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。

| 資料行名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中裝置的唯一識別碼 |
| `DeviceName` | string | 裝置的完整功能變數名稱 (FQDN)  |
| `ActionType` | string | 觸發事件的活動類型 |
| `RemoteIP` | 字串 | 連線到的 IP 位址 |
| `RemotePort` | int | 連線的遠端裝置上的 TCP 埠 |
| `RemoteUrl` | 字串 | 已連線到的 URL 或完整網域名稱 (FQDN) |
| `LocalIP` | 字串 | 指派給通訊期間所使用之本機裝置的 IP 位址 |
| `LocalPort` | int | 通訊期間使用的本機裝置上的 TCP 埠 |
| `Protocol` | string | 使用 IP 通訊協定，不論是 TCP 還是 UDP |
| `LocalIPType` | string | IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播 |
| `RemoteIPType` | string | IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播 |
| `InitiatingProcessSHA1` | string | 啟動事件) 的處理常式 (映射檔 SHA-1 |
| `InitiatingProcessMD5` | string | 啟動事件之程式 (映射檔) 的 MD5 雜湊 |
| `InitiatingProcessFileName` | string | 啟動事件的進程名稱 |
| `InitiatingProcessId` | int | 啟動事件之程式的進程識別碼 (PID)  |
| `InitiatingProcessCommandLine` | string | 用來執行啟動事件之處理常式的命令列 |
| `InitiatingProcessCreationTime` | datetime | 啟動事件處理常式的日期和時間 |
| `InitiatingProcessFolderPath` | string | 包含初始化事件之處理 (映射檔) 程式的資料夾 |
| `InitiatingProcessParentFileName` | string | 產生負責事件之處理常式的父進程名稱 |
| `InitiatingProcessParentId` | int | 產生負責事件之處理常式之父進程的進程識別碼 (PID)  |
| `InitiatingProcessParentCreationTime` | datetime | 啟動事件之處理常式的父項時的日期和時間 |
| `InitiatingProcessAccountDomain` | string | 執行負責事件之處理常式之帳戶的網域 |
| `InitiatingProcessAccountName` | string | 負責事件之處理常式的帳戶使用者名稱 |
| `InitiatingProcessAccountSid` | string | 執行事件負責處理之帳戶的安全性識別碼 (SID)  |
| `InitiatingProcessIntegrityLevel` | string | 啟動事件之處理常式的完整性層級。 Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。 這些完整性層級會影響資源的許可權 |
| `InitiatingProcessTokenElevation` | string | 指出是否存在使用者存取控制的 Token 類型 (UAC) 許可權提升會套用至啟動事件的程式。 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 `DeviceName` 和欄一起 `Timestamp` 使用 |
| `AppGuardContainerId` | string | Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
