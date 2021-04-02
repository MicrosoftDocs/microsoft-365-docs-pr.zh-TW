---
title: Advanced 搜尋架構中的 DeviceEvents 表格
description: 深入瞭解其他裝置事件中的防毒程式、防火牆及其他事件種類 (DeviceEvents 的高級搜尋架構) 表格
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、架構參考、kusto、table、column、data type、security 事件、防毒程式、防火牆、exploit guard、MiscEvents
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
ms.openlocfilehash: 1e67da3a5d93c5e8c86afd755c882f3f0459aab0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499193"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Advanced 搜尋架構中的 [其他裝置] 事件或 `DeviceEvents` 表格包含各種事件種類的相關資訊，包括安全性控制所觸發的事件，例如 Microsoft Defender 防毒程式和 exploit protection。 [](advanced-hunting-overview.md) 使用這個參考來建立從表格取回之資訊的查詢。

如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。

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
| `AccountDomain` | string | 帳戶的網域 |
| `AccountName` |string | 帳戶的使用者名稱 |
| `AccountSid` | string | 帳戶的安全性識別碼 (SID)  |
| `RemoteUrl` | 字串 | 已連線到的 URL 或完整網域名稱 (FQDN) |
| `RemoteDeviceName` | 字串 | 在受影響的裝置上執行遠端作業的裝置名稱。 根據所報告的事件，此名稱可以是完整功能變數名稱 (FQDN) 、NetBIOS 名稱或沒有網域資訊的主機名稱。 |
| `ProcessId` | int | 新建立程式的進程識別碼 (PID)  |
| `ProcessCommandLine` | string | 用來建立新程式的命令列 |
| `ProcessCreationTime` | datetime | 處理常式的建立日期和時間 |
| `ProcessTokenElevation` | string | 表示使用者存取控制是否存在的 Token 類型 (UAC) 許可權提升套用至新建立的程式 |
| `LogonId` | string | 登入會話的識別碼。 只有在重新開機時，此識別碼在相同裝置上才是唯一的 |
| `RegistryKey` | string | 套用錄製的動作所用的登錄機碼 |
| `RegistryValueName` | string | 已錄製動作套用至之登錄值的名稱 |
| `RegistryValueData` | string | 已錄製動作套用至之登錄值的資料 |
| `RemoteIP` | 字串 | 連線到的 IP 位址 |
| `RemotePort` | int | 連線的遠端裝置上的 TCP 埠 |
| `LocalIP` | string | 指派給通訊期間所使用之本機裝置的 IP 位址 |
| `LocalPort` | int | 通訊期間使用的本機裝置上的 TCP 埠 |
| `FileOriginUrl` | string | 下載檔案所在的 URL |
| `FileOriginIP` | string | 從中下載檔案的 IP 位址 |
| `AdditionalFields` | string | 有關 JSON 陣列格式之事件的其他資訊 |
| `InitiatingProcessSHA1` | string | 啟動事件) 的處理常式 (映射檔 SHA-1 |
| `InitiatingProcessSHA256` | string | 啟動事件) 的處理常式 (映射檔 SHA-256。 通常不會填入此欄位，可使用 SHA1] 欄位 |
| `InitiatingProcessFileName` | string | 啟動事件的進程名稱 |
| `InitiatingProcessFolderPath` | string | 包含初始化事件之處理 (映射檔) 程式的資料夾 |
| `InitiatingProcessId` | int | 啟動事件之程式的進程識別碼 (PID)  |
| `InitiatingProcessCommandLine` | string | 用來執行啟動事件之處理常式的命令列 |
| `InitiatingProcessCreationTime` | datetime | 啟動事件處理常式的日期和時間 |
| `InitiatingProcessParentId` | int | 產生負責事件之處理常式之父進程的進程識別碼 (PID)  |
| `InitiatingProcessParentFileName` | string | 產生負責事件之處理常式的父進程名稱 |
| `InitiatingProcessParentCreationTime` | datetime | 啟動事件之處理常式的父項時的日期和時間 |
| `InitiatingProcessMD5` | string | 啟動事件之程式 (映射檔) 的 MD5 雜湊 |
| `InitiatingProcessAccountDomain` | string | 執行負責事件之處理常式之帳戶的網域 |
| `InitiatingProcessAccountName` | string | 負責事件之處理常式的帳戶使用者名稱 |
| `InitiatingProcessAccountSid` | string | 執行事件負責處理之帳戶的安全性識別碼 (SID)  |
| `InitiatingProcessLogonId` | string | 啟動事件之處理常式的登入會話識別碼。 只有在重新開機時，此識別碼在相同裝置上才是唯一的 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 `DeviceName` 和欄一起 `Timestamp` 使用 |
| `AppGuardContainerId` | string | Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼 |


## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
