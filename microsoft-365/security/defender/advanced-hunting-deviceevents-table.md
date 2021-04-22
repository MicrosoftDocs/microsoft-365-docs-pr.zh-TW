---
title: Advanced 搜尋架構中的 DeviceEvents 表格
description: 深入瞭解其他裝置事件中的防毒程式、防火牆及其他事件種類 (DeviceEvents 的高級搜尋架構) 表格
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，data type，security 事件，防毒程式，防火牆，exploit guard，DeviceEvents
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
ms.openlocfilehash: fc28159f9f83354868142584740e2cb7810724b9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933682"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

Advanced 搜尋架構中的 [其他裝置] 事件或 `DeviceEvents` 表格包含各種事件種類的相關資訊，包括安全性控制（如 Windows Defender 防毒程式和 exploit protection）所觸發的事件。 [](advanced-hunting-overview.md) 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的內建架構參照。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。


| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ActionType` | string | 觸發事件的活動類型。 如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | 字串 | 記錄動作已套用的檔案名稱 |
| `FolderPath` | 字串 | 包含錄製的動作所套用之檔案的資料夾 |
| `SHA1` | 字串 | 記錄動作已套用的檔案 SHA-1 |
| `SHA256` | 字串 | 記錄動作已套用的檔案 SHA-256。 此欄位通常未填入，可取得時請使用 SHA1 欄。 |
| `MD5` | 字串 | 錄製的動作所套用的檔案 MD5 雜湊 |
| `FileSize` | long | 檔案大小（以位元組為單位） |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountSid` | string | 帳戶的安全性識別碼 (SID)  |
| `RemoteUrl` | 字串 | 已連線到的 URL 或完整網域名稱 (FQDN) |
| `RemoteDeviceName` | 字串 | 在受影響的機器上執行遠端作業的機器名稱。 根據所報告的事件，此名稱可以是完整功能變數名稱 (FQDN) 、NetBIOS 名稱或沒有網域資訊的主機名稱。 |
| `ProcessId` | int | 新建立程式的進程識別碼 (PID)  |
| `ProcessCommandLine` | string | 用來建立新程式的命令列 |
| `ProcessCreationTime` | datetime | 處理常式的建立日期和時間 |
| `ProcessTokenElevation` | string | 表示使用者存取控制是否存在的 Token 類型 (UAC) 許可權提升套用至新建立的程式 |
| `LogonId` | string | 登入會話的識別碼。 只有在重新開機時，此識別碼在同一部電腦上是唯一的 |
| `RegistryKey` | string | 套用錄製的動作所用的登錄機碼 |
| `RegistryValueName` | string | 已錄製動作套用至之登錄值的名稱 |
| `RegistryValueData` | string | 已錄製動作套用至之登錄值的資料 |
| `RemoteIP` | 字串 | 連線到的 IP 位址 |
| `RemotePort` | int | 連線的遠端裝置上的 TCP 埠 |
| `LocalIP` | string | 指派給通訊期間使用之本機電腦的 IP 位址 |
| `LocalPort` | int | 通訊期間使用的本機電腦上的 TCP 埠 |
| `FileOriginUrl` | string | 下載檔案所在的 URL |
| `FileOriginIP` | string | 從中下載檔案的 IP 位址 |
| `InitiatingProcessSHA1` | string | 啟動事件) 的處理常式 (映射檔 SHA-1 |
| `InitiatingProcessSHA256` | string | 啟動事件) 的處理常式 (映射檔 SHA-256。 此欄位通常未填入，可取得時請使用 SHA1 欄。 |
| `InitiatingProcessMD5` | 字串 | 啟動事件之程式 (映射檔) 的 MD5 雜湊 |
| `InitiatingProcessFileName` | string | 啟動事件的進程名稱 |
| `InitiatingProcessFileSize` | long | 執行事件處理常式的檔案大小 |
| `InitiatingProcessFolderPath` | string | 包含初始化事件之處理 (映射檔) 程式的資料夾 |
| `InitiatingProcessId` | int | 啟動事件之程式的進程識別碼 (PID)  |
| `InitiatingProcessCommandLine` | string | 用來執行啟動事件之處理常式的命令列 |
| `InitiatingProcessCreationTime` | datetime | 啟動事件處理常式的日期和時間 |
| `InitiatingProcessAccountDomain` | string | 執行負責事件之處理常式之帳戶的網域 |
| `InitiatingProcessAccountName` | string | 負責事件之處理常式的帳戶使用者名稱 |
| `InitiatingProcessAccountSid` | string | 執行事件負責處理之帳戶的安全性識別碼 (SID)  |
| `InitiatingProcessAccountUpn` | string | 執行事件負責之帳戶的使用者主要名稱 (UPN)  |
| `InitiatingProcessAccountObjectId` | string | 執行負責事件之處理常式之使用者帳戶的 Azure AD 物件識別碼 |
| `InitiatingProcessVersionInfoCompanyName` | string | 處理常式 (映射檔的版本資訊中) 負責事件的公司名稱 |
| `InitiatingProcessVersionInfoProductName` | string | 處理常式 (映射檔的版本資訊中的產品名稱) 該事件的負責人 |
| `InitiatingProcessVersionInfoProductVersion` | string |  (映射檔的版本資訊中的產品版本) 負責事件的處理常式 |
|` InitiatingProcessVersionInfoInternalFileName` | string | 處理常式 (映射檔的版本資訊中的內部檔案名) 負責事件 |
| `InitiatingProcessVersionInfoOriginalFileName` | string | 處理常式 (映射檔的版本資訊中的原始檔案名) 負責事件。 |
| `InitiatingProcessVersionInfoFileDescription` | string | 處理常式 (映射檔的版本資訊的描述) 該事件的負責人 |
| `InitiatingProcessParentId` | int | 產生負責事件之處理常式之父進程的進程識別碼 (PID)  |
| `InitiatingProcessParentFileName` | string | 產生負責事件之處理常式的父進程名稱 |
| `InitiatingProcessParentCreationTime` | datetime | 啟動事件之處理常式的父項時的日期和時間 |
| `InitiatingProcessLogonId` | string | 啟動事件之處理常式的登入會話識別碼。 只有在重新開機時，此識別碼在同一部電腦上是唯一的 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用 |
| `AppGuardContainerId` | string | Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼 |
| `AdditionalFields` | string | 有關 JSON 陣列格式之事件的其他資訊 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
