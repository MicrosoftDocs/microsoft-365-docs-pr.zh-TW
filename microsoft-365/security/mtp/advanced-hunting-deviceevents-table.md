---
title: 進位搜尋架構中的 DeviceEvents 資料表
description: 瞭解進層搜尋架構資料表 (裝置事件的防毒軟體、防火牆和) 事件種類
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、安全性事件、防毒軟體、防火牆、探索防護、DeviceEvents
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
ms.openlocfilehash: 536d95f7226ba907d913df58a47508e44b50147a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931347"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender



進位搜尋架構中的其他裝置事件或資料表包含各種事件種類的資訊，包括由安全性控制項觸發的事件，例如 Windows Defender 防毒軟體和探索 `DeviceEvents` 保護。 [](advanced-hunting-overview.md) 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參考。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。


| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ActionType` | string | 觸發事件的活動類型。 請參閱入口 [網站內架構參考以](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 進一步查看詳細資料 |
| `FileName` | 字串 | 記錄動作已套用的檔案名稱 |
| `FolderPath` | 字串 | 包含已記錄動作所使用之檔案的資料夾 |
| `SHA1` | 字串 | 記錄動作已套用的檔案 SHA-1 |
| `SHA256` | 字串 | 記錄動作已套用的檔案 SHA-256。 此欄位通常未填入，可取得時請使用 SHA1 欄。 |
| `MD5` | 字串 | 已記錄動作所針對之檔案的 MD5 雜湊 |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountSid` | string | 帳戶 (安全性) SID 識別碼 |
| `RemoteUrl` | 字串 | 已連線到的 URL 或完整網域名稱 (FQDN) |
| `RemoteDeviceName` | 字串 | 在受影響電腦上執行遠端作業的機器名稱。 根據報告的事件，此名稱可能是完整功能變數名稱 (FQDN) 、NetBIOS 名稱，或不含網域資訊的主機名稱 |
| `ProcessId` | int | 新 (程式) 程式之 PID 的識別碼 |
| `ProcessCommandLine` | string | 用來建立新流程的命令列 |
| `ProcessCreationTime` | datetime | 建立程式的日期與時間 |
| `ProcessTokenElevation` | string | 指出使用者存取控制存在或不存在的權杖類型 (UAC) 新建立程式所使用的許可權提高 |
| `LogonId` | string | 登入會話的識別碼。 只有在重新開機之間，此識別碼才在同一部電腦上是唯一的 |
| `RegistryKey` | string | 已記錄動作所適用于的註冊表金鑰 |
| `RegistryValueName` | string | 記錄的動作所使用之註冊表值的名稱 |
| `RegistryValueData` | string | 記錄的動作所適用于之註冊表值的資料 |
| `RemoteIP` | 字串 | 連線到的 IP 位址 |
| `RemotePort` | int | 已連接之遠端裝置上的 TCP 埠 |
| `LocalIP` | string | 指派給通訊期間使用的本機電腦之 IP 位址 |
| `LocalPort` | int | 在通訊期間使用的本機電腦上使用 TCP 埠 |
| `FileOriginUrl` | string | 檔案下載的 URL |
| `FileOriginIP` | string | 檔案下載的 IP 位址 |
| `AdditionalFields` | string | 以 JSON 陣列格式顯示之事件的其他資訊 |
| `InitiatingProcessSHA1` | string | 初始化活動的影像 (的 SHA-1) 影像檔案 |
| `InitiatingProcessSHA256` | string | 初始化事件的 (的 SHA-256) 影像檔案。 此欄位通常未填入，可取得時請使用 SHA1 欄。 |
| `InitiatingProcessFileName` | 字串 | 初始化事件之程式的名稱 |
| `InitiatingProcessFolderPath` | string | 啟動事件之 (圖像) 的資料夾 |
| `InitiatingProcessId` | int | 程式識別碼 (初始化) 的 PID 值 |
| `InitiatingProcessCommandLine` | string | 用來執行初始化活動的程式命令列 |
| `InitiatingProcessCreationTime` | datetime | 啟動事件之程式開始的日期和時間 |
| `InitiatingProcessParentId` | int | 程式識別碼 (產生) 事件之父流程的 PID 值 |
| `InitiatingProcessParentFileName` | string | 指定事件所負責之程式之父程式的名稱 |
| `InitiatingProcessParentCreationTime` | datetime | 事件負責之程式父項開始的日期和時間 |
| `InitiatingProcessMD5` | string | 初始化活動的 (圖像) MD5 雜湊 |
| `InitiatingProcessAccountDomain` | string | 執行負責事件之程式之帳戶的網域 |
| `InitiatingProcessAccountName` | string | 執行負責事件之程式之帳戶的使用者名稱 |
| `InitiatingProcessAccountSid` | string | 執行 (之) 之帳戶的安全性識別碼為 SID 記錄 |
| `InitiatingProcessLogonId` | string | 初始化事件之程式登入會話的識別碼。 只有在重新開機之間，此識別碼才在同一部電腦上是唯一的 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一事件，此欄必須與 DeviceName 和 Timestamp 資料行一起使用 |
| `AppGuardContainerId` | string | Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
