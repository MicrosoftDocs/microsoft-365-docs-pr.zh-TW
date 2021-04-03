---
title: Advanced 搜尋架構中的 DeviceFileEvents 表格
description: 深入瞭解高級搜尋架構的 DeviceFileEvents 資料表中的檔案相關事件
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、devicefileevents、檔、路徑、雜湊、sha1、sha256、md5、FileCreationEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 323cc8e809b81f937a29e41f24c2976c3d5c175b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500860"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[！附注] `DeviceFileEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含檔建立、修改及其他檔案系統事件的相關資訊。 使用這個參考來建立從表格取回之資訊的查詢。

如需高級搜尋架構中其他資料表的詳細資訊，請參閱「  [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。

| 資料行名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中裝置的唯一識別碼 |
| `DeviceName` | string | 裝置的完整功能變數名稱 (FQDN)  |
| `ActionType` | string | 觸發事件的活動類型 |
| `FileName` | 字串 | 記錄動作已套用的檔案名稱 |
| `FolderPath` | 字串 | 包含錄製的動作所套用之檔案的資料夾 |
| `SHA1` | 字串 | 記錄動作已套用的檔案 SHA-1 |
| `SHA256` | 字串 | 記錄動作已套用的檔案 SHA-256。 通常不會填入此欄位，可使用 SHA1] 欄位 |
| `MD5` | string | 錄製的動作所套用的檔案 MD5 雜湊 |
| `FileOriginUrl` | string | 下載檔案所在的 URL |
| `FileOriginReferrerUrl` | string | 連結至已下載檔案的網頁 URL |
| `FileOriginIP` | string | 從中下載檔案的 IP 位址 |
| `InitiatingProcessAccountDomain` | string | 執行負責事件之處理常式之帳戶的網域 |
| `InitiatingProcessAccountName` | string | 負責事件之處理常式的帳戶使用者名稱 |
| `InitiatingProcessAccountSid` | string | 執行事件負責處理之帳戶的安全性識別碼 (SID)  |
| `InitiatingProcessMD5` | string | 啟動事件之程式 (映射檔) 的 MD5 雜湊 |
| `InitiatingProcessSHA1` | string | 啟動事件) 的處理常式 (映射檔 SHA-1 |
| `InitiatingProcessFolderPath` | string | 包含初始化事件之處理 (映射檔) 程式的資料夾 |
| `InitiatingProcessFileName` | string | 啟動事件的進程名稱 |
| `InitiatingProcessId` | int | 啟動事件之程式的進程識別碼 (PID)  |
| `InitiatingProcessCommandLine` | string | 用來執行啟動事件之處理常式的命令列 |
| `InitiatingProcessCreationTime` | datetime | 啟動事件處理常式的日期和時間 |
| `InitiatingProcessIntegrityLevel` | string | 啟動事件之處理常式的完整性層級。 Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。 這些完整性層級會影響資源的許可權 |
| `InitiatingProcessTokenElevation` | string | 指出是否存在使用者存取控制的 Token 類型 (UAC) 許可權提升會套用至啟動事件的程式。 |
| `InitiatingProcessParentId` | int | 產生負責事件之處理常式之父進程的進程識別碼 (PID)  |
| `InitiatingProcessParentFileName` | string | 產生負責事件之處理常式的父進程名稱 |
| `InitiatingProcessParentCreationTime` | datetime | 啟動事件之處理常式的父項時的日期和時間 |
| `RequestProtocol` | string | 用於啟動活動的網路通訊協定（如果適用）：未知、本機、SMB 或 NFS |
| `ShareName` | string | 包含檔案的共用資料夾名稱 |
| `RequestSourceIP` | string | 啟動活動之遠端裝置的 IPv4 或 IPv6 位址 |
| `RequestSourcePort` | string | 啟動活動的遠端裝置上的來源埠 |
| `RequestAccountName` | string | 遠端啟動活動所用的帳戶使用者名稱 |
| `RequestAccountDomain` | string | 用於遠端啟動活動之帳戶的網域 |
| `RequestAccountSid` | string | 遠端啟動活動之帳戶 (SID) 的安全性識別碼 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用 |
| `AppGuardContainerId` | string | Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼 |
| `SensitivityLabel` | string | 套用至電子郵件、檔案或其他內容的標籤，以分類資訊保護 |
| `SensitivitySubLabel` | string | 套用至電子郵件、檔案或其他內容的 Sublabel，以分類資訊保護;敏感度分組是以靈敏度標籤群組，但是會個別處理 |
| `IsAzureInfoProtectionApplied` | 布林值 | 指出檔案是否由 Azure 資訊保護所加密 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
