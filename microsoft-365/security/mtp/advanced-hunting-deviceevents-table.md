---
title: DeviceEvents 資料表中的進階的狩獵結構描述
description: 了解防毒、 防火牆，與其他裝置事件 (DeviceEvents)] 表格中其他事件類型的進階的狩獵結構描述
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 安全性事件、 防毒軟體、 防火牆、 利用 guard，DeviceEvents
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
ms.openlocfilehash: aec5751cf400f94abaf259aaa5fe2238b4b91311
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809252"
---
# <a name="deviceevents"></a>DeviceEvents

適用於：****
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

其他裝置事件或`DeviceEvents`[進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含各種事件類型，包括由安全性控制，例如 Windows Defender 防毒軟體和惡意探索防護觸發的事件的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。


| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ActionType` | string | 觸發事件的活動類型 |
| `FileName` | string | 記錄動作已套用的檔案名稱 |
| `FolderPath` | string | 包含已錄製的巨集指令所套用之檔案的資料夾 |
| `SHA1` | string | 記錄動作已套用的檔案 SHA-1 |
| `SHA256` | 字串 | 記錄動作已套用的檔案 SHA-256。 通常沒有填入此欄位 — 使用時可用的 SHA1 欄 |
| `MD5` | string | 錄製巨集指令所套用之檔案的 MD5 雜湊 |
| `AccountDomain` | string | 此帳戶的網域 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountSid` | string | 安全性識別碼 (SID) 的帳戶 |
| `RemoteUrl` | string | 已連線到的 URL 或完整網域名稱 (FQDN) |
| `RemoteDeviceName` | 字串 | 執行受影響的電腦上的遠端作業的機器名稱。 根據所報告的事件，此名稱可能是完整網域名稱 (FQDN)、 NetBIOS 名稱或沒有網域資訊的主機名稱 |
| `ProcessId` | int | 處理程序識別碼 (PID) 的新建立的程序 |
| `ProcessCommandLine` | string | 用來建立新的程序的命令列 |
| `ProcessCreationTime` | datetime | 處理程序所建立的日期和時間 |
| `ProcessTokenElevation` | string | 指出使用者存取控制 (UAC) 提高權限套用至新建立的程序存在的 token 型別 |
| `LogonId` | string | 登入工作階段的識別碼。 此識別碼會在僅限之間重新啟動在同一部機器上的唯一 |
| `RegistryKey` | string | 錄製巨集指令所套用的登錄機碼 |
| `RegistryValueName` | string | 錄製巨集指令所套用的登錄值的名稱 |
| `RegistryValueData` | string | 錄製巨集指令所套用的登錄值的資料 |
| `RemoteIP` | string | 連線到的 IP 位址 |
| `RemotePort` | int | 已連線至遠端裝置上的 TCP 連接埠 |
| `LocalIP` | string | 指派給通訊期間，使用本機電腦的 IP 位址 |
| `LocalPort` | int | 在通訊期間，使用本機電腦上的 TCP 連接埠 |
| `FileOriginUrl` | string | 從何處下載檔案的 URL |
| `FileOriginIP` | string | 從何處下載檔案的 IP 位址 |
| `AdditionalFields` | string | 以 JSON 陣列格式事件相關的其他資訊 |
| `InitiatingProcessSHA1` | string | SHA-1 起始之事件程序 （影像檔案） |
| `InitiatingProcessSHA256` | string | SHA 256 初始化事件程序 （影像檔案）。 通常沒有填入此欄位 — 使用時可用的 SHA1 欄 |
| `InitiatingProcessFileName` | string | 初始化事件的處理序名稱 |
| `InitiatingProcessFolderPath` | string | 包含起始事件程序 （影像檔案） 的資料夾 |
| `InitiatingProcessId` | int | 處理程序識別碼 (PID) 的起始事件程序 |
| `InitiatingProcessCommandLine` | string | 用來執行初始化事件程序的命令列 |
| `InitiatingProcessCreationTime` | datetime | 初始化事件程序時已開始日期和時間 |
| `InitiatingProcessParentId` | int | 處理程序識別碼 (PID) 的產生處理程序負責事件父處理序 |
| `InitiatingProcessParentFileName` | string | 產生負責事件程序的父處理序名稱 |
| `InitiatingProcessParentCreationTime` | datetime | 日期和時間的父代負責事件程序已啟動時 |
| `InitiatingProcessMD5` | string | 初始化事件程序 （影像檔案） 的 MD5 雜湊 |
| `InitiatingProcessAccountDomain` | string | 執行負責事件程序的帳戶網域 |
| `InitiatingProcessAccountName` | string | 執行負責事件程序的帳戶使用者名稱 |
| `InitiatingProcessAccountSid` | string | 安全性識別碼 (SID) 執行負責事件程序的帳戶 |
| `InitiatingProcessLogonId` | string | 登入工作階段初始化事件程序的識別碼。 此識別碼會在僅限之間重新啟動在同一部機器上的唯一 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄 |
| `AppGuardContainerId` | string | 虛擬化的容器應用程式防護用於隔離瀏覽器活動識別碼 |

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
