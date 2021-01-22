---
title: 進位搜尋架構中的 DeviceFileEvents 資料表
description: 瞭解進位搜尋架構的 DeviceFileEvents 資料表中與檔案相關的事件
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、表格、欄、資料類型、描述、filecreationevents、DeviceFileEvents、檔案、路徑、雜湊、sha1、sha256、md5
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
ms.openlocfilehash: cb51d9b94cc500361f836f7ba8bc4fc290436805
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931323"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

進 `DeviceFileEvents` 位搜尋架構 [中的](advanced-hunting-overview.md) 表格包含有關檔案建立、修改及其他檔案系統事件的資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

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
| `FileOriginUrl` | string | 檔案下載的 URL |
| `FileOriginReferrerUrl` | string | 連結至下載檔案的網頁 URL |
| `FileOriginIP` | string | 檔案下載的 IP 位址 |
| `InitiatingProcessAccountDomain` | string | 執行負責事件之程式之帳戶的網域 |
| `InitiatingProcessAccountName` | string | 執行負責事件之程式之帳戶的使用者名稱 |
| `InitiatingProcessAccountSid` | string | 執行 (之) 之帳戶的安全性識別碼為 SID |
| `InitiatingProcessMD5` | string | 初始化活動的 (圖像) MD5 雜湊 |
| `InitiatingProcessSHA1` | string | 初始化活動的影像 (的 SHA-1) 影像檔案 |
| `InitiatingProcessSHA256` | string | 初始化事件的 (的 SHA-256) 影像檔案。 此欄位通常未填入，可取得時請使用 SHA1 欄。 |
| `InitiatingProcessFolderPath` | 字串 | 啟動事件之 (圖像) 的資料夾 |
| `InitiatingProcessFileName` | string | 初始化事件之程式的名稱 |
| `InitiatingProcessId` | int | 程式識別碼 (初始化) 的 PID 值 |
| `InitiatingProcessCommandLine` | string | 用來執行初始化事件的流程的命令列 |
| `InitiatingProcessCreationTime` | datetime | 啟動事件之程式開始的日期和時間 |
| `InitiatingProcessIntegrityLevel` | string | 初始化事件之程式的完整性層級。 Windows 會依據特定特性指派完整性層級給程式，例如從網際網路下載啟動程式。 這些完整性等級會影響資源的許可權 |
| `InitiatingProcessTokenElevation` | string | 指出使用者存取控制存在或不存在的權杖類型 (UAC) 許可權提高已應用至初始化事件的流程 |
| `InitiatingProcessParentId` | int | 程式識別碼 (產生) 事件之父流程的 PID 值 |
| `InitiatingProcessParentFileName` | string | 指定事件所負責之程式之父程式的名稱 |
| `InitiatingProcessParentCreationTime` | datetime | 事件負責之程式父項開始的日期和時間 |
| `RequestProtocol` | string | 網路通訊協定 ，如果適用，用來初始化活動：未知、本地、SMB 或 MBS |
| `ShareName` | string | 包含檔案的共用資料夾名稱 |
| `RequestSourceIP` | string | 啟動活動的遠端裝置之 IPv4 或 IPv6 位址 |
| `RequestSourcePort` | string | 啟動活動之遠端裝置上的來源埠 |
| `RequestAccountName` | string | 用來遠端啟動活動的帳戶使用者名稱 |
| `RequestAccountDomain` | string | 用來遠端啟動活動之帳戶的網域 |
| `RequestAccountSid` | string | 用來 () 啟動活動的帳戶之 SID 識別碼 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一事件，此欄必須與 DeviceName 和 Timestamp 資料行一起使用 |
| `AppGuardContainerId` | string | Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼 |
| `SensitivityLabel` | string | 將標籤用於電子郵件、檔案或其他內容，以分類以保護資訊 |
| `SensitivitySubLabel` | string | 將子標記用於電子郵件、檔案或其他內容，以分類以利資訊保護;敏感度子標記會分組在敏感度標籤下，但會獨立處理 |
| `IsAzureInfoProtectionApplied` | 布林值 | 指出檔案是否由 Azure 資訊保護加密 |

>[!NOTE]
> 檔案雜湊資訊一定會在可用時顯示。 不過，無法計算 SHA1、SHA256 或 MD5 的原因有好幾種。 例如，檔案可能位於遠端儲存空間、由另一個程式鎖定、壓縮或標示為虛擬。 在這些情況下，檔案雜湊資訊會呈現空白。

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
