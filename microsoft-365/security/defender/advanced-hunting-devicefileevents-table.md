---
title: Advanced 搜尋架構中的 DeviceFileEvents 表格
description: 深入瞭解高級搜尋架構的 DeviceFileEvents 資料表中的檔案相關事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，data type，description，filecreationevents，DeviceFileEvents，files，path，hash，sha1，sha256，md5
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
ms.openlocfilehash: 1b716a37aa39dffc8dc541335f42265ae47fe989
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52022996"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender
- 適用於端點的 Microsoft Defender

[！附注] `DeviceFileEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含檔建立、修改及其他檔案系統事件的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

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
| `FileOriginUrl` | string | 下載檔案所在的 URL |
| `FileOriginReferrerUrl` | string | 連結至已下載檔案的網頁 URL |
| `FileOriginIP` | string | 從中下載檔案的 IP 位址 |
| `PreviousFolderPath` | string | 在套用錄製的動作之前包含檔的原始檔案夾 |
| `PreviousFileName` | string | 重新命名為動作結果之檔案的原始名稱 |
| `FileSize` | long | 檔案大小（以位元組為單位） |
| `InitiatingProcessAccountDomain` | string | 執行負責事件之處理常式之帳戶的網域 |
| `InitiatingProcessAccountName` | string | 負責事件之處理常式的帳戶使用者名稱 |
| `InitiatingProcessAccountSid` | string | 執行事件負責處理之帳戶的安全性識別碼 (SID)  |
| `InitiatingProcessAccountUpn` | string | 執行事件負責之帳戶的使用者主要名稱 (UPN)  |
| `InitiatingProcessAccountObjectId` | string | 執行負責事件之處理常式之使用者帳戶的 Azure AD 物件識別碼 |
| `InitiatingProcessMD5` | string | 啟動事件之程式 (映射檔) 的 MD5 雜湊 |
| `InitiatingProcessSHA1` | string | 啟動事件) 的處理常式 (映射檔 SHA-1 |
| `InitiatingProcessSHA256` | string | 啟動事件) 的處理常式 (映射檔 SHA-256。 此欄位通常未填入，可取得時請使用 SHA1 欄。 |
| `InitiatingProcessFolderPath` | 字串 | 包含初始化事件之處理 (映射檔) 程式的資料夾 |
| `InitiatingProcessFileName` | string | 啟動事件的進程名稱 |
| `InitiatingProcessFileSize` | long | 初始化事件之處理 (映射檔) 的大小 |
| `InitiatingProcessVersionInfoCompanyName` | string | 處理常式 (映射檔的版本資訊中) 負責事件的公司名稱 |
| `InitiatingProcessVersionInfoProductName` | string | 處理常式 (映射檔的版本資訊中的產品名稱) 該事件的負責人 |
|` InitiatingProcessVersionInfoProductVersion` | string |  (映射檔的版本資訊中的產品版本) 負責事件的處理常式 |
|` InitiatingProcessVersionInfoInternalFileName` | string | 處理常式 (映射檔的版本資訊中的內部檔案名) 負責事件 |
| `InitiatingProcessVersionInfoOriginalFileName` | string | 處理常式 (映射檔的版本資訊中的原始檔案名) 負責事件。 |
| `InitiatingProcessVersionInfoFileDescription` | string | 處理常式 (映射檔的版本資訊的描述) 該事件的負責人 |
| `InitiatingProcessId` | int | 啟動事件之程式的進程識別碼 (PID)  |
| `InitiatingProcessCommandLine` | string | 用來執行啟動事件之處理常式的命令列 |
| `InitiatingProcessCreationTime` | datetime | 啟動事件處理常式的日期和時間 |
| `InitiatingProcessIntegrityLevel` | string | 啟動事件之處理常式的完整性層級。 Windows 會根據某些特性（例如從網際網路下載）將完整性層級指派給處理常式。 這些完整性層級會影響資源的許可權 |
| `InitiatingProcessTokenElevation` | string | 指出是否存在使用者存取控制的 Token 類型 (UAC) 許可權提升會套用至啟動事件的程式。 |
| `InitiatingProcessParentId` | int | 產生負責事件之處理常式之父進程的進程識別碼 (PID)  |
| `InitiatingProcessParentFileName` | string | 產生負責事件之處理常式的父進程名稱 |
| `InitiatingProcessParentCreationTime` | datetime | 啟動事件之處理常式的父項時的日期和時間 |
| `RequestProtocol` | string | 用於啟動活動的網路通訊協定（如果適用）：未知、本機、SMB 或 NFS |
| `RequestSourceIP` | string | 啟動活動之遠端裝置的 IPv4 或 IPv6 位址 |
| `RequestSourcePort` | string | 啟動活動的遠端裝置上的來源埠 |
| `RequestAccountName` | string | 遠端啟動活動所用的帳戶使用者名稱 |
| `RequestAccountDomain` | string | 用於遠端啟動活動之帳戶的網域 |
| `RequestAccountSid` | string | 遠端啟動活動所使用之帳戶的安全性識別碼 (SID)  |
| `ShareName` | string | 包含檔案的共用資料夾名稱 |
| `InitiatingProcessFileSize` | long | 執行事件處理常式的檔案大小 |
| `SensitivityLabel` | string | 套用至電子郵件、檔案或其他內容的標籤，以分類資訊保護 |
| `SensitivitySubLabel` | string | 套用至電子郵件、檔案或其他內容的 Sublabel，以分類資訊保護;敏感度分組是以靈敏度標籤群組，但是會個別處理 |
| `IsAzureInfoProtectionApplied` | 布林值 | 指出檔案是否由 Azure 資訊保護所加密 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用。 |
| `AppGuardContainerId` | string | Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼 |
| `AdditionalFields` | string | 實體或事件的其他資訊 |
>[!NOTE]
> 檔案雜湊資訊會在可用時永遠顯示。 不過，有數個可能的原因是無法計算 SHA1、SHA256 或 MD5。 例如，檔案可能位於遠端存放區、已壓縮或已標記為虛擬的另一個處理常式鎖定。 在這些情況下，檔雜湊資訊會顯示空白。

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
