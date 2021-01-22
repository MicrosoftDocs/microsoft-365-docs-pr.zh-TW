---
title: 進位搜尋架構中的 DeviceLogonEvents 資料表
description: 瞭解進位搜尋架構的 DeviceLogonEvents 資料表中的驗證或登登事件
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、表格、欄、資料類型、描述、logonevents、DeviceLogonEvents、驗證、登入、登入
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
ms.openlocfilehash: 3a5666cc106365876956c8e313f9cd2f5a996e6f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931227"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender



進 `DeviceLogonEvents` 位搜尋架構 [中的](advanced-hunting-overview.md) 表格包含使用者標誌及裝置上的其他驗證事件相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參考。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ActionType` | string |觸發事件的活動類型 |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountSid` | string | 帳戶 (安全性) SID 識別碼 |
| `LogonType` | string | 登入會話的類型，特別是：<br><br> - **互動** - 使用者會使用本機鍵盤和螢幕與電腦進行實際互動<br><br> - **遠端互動式 (RDP)** 標誌 - 使用者會使用遠端桌面、終端機服務、遠端協助或其他 RDP 用戶端，與電腦進行遠端互動<br><br> - **網路** - 當使用 PsExec 存取電腦時，或當電腦上的共用資源 ，例如印表機和共用資料夾存取時初始化的會話<br><br> - **批次** - 由排程任務啟動的會話<br><br> - **服務** - 服務啟動時所啟動的會話<br> |
| `LogonId` | string | 登入會話的識別碼。 只有在重新開機之間，此識別碼才在同一部電腦上是唯一的 |
| `RemoteDeviceName` | string | 在受影響電腦上執行遠端作業的機器名稱。 根據報告的事件，此名稱可能是完整功能變數名稱 (FQDN) 、NetBIOS 名稱或不含網域資訊的主機名稱 |
| `RemoteIP` | 字串 | 連線到的 IP 位址 |
| `RemoteIPType` | string | IP 位址類型，例如公用、私人、保留、Loopback、Teredo、FourToSixMapping 和 Broadcast |
| `RemotePort` | int | 正在連接之遠端裝置上的 TCP 埠 |
| `AdditionalFields` | string | 以 JSON 陣列格式顯示之事件的其他資訊 |
| `InitiatingProcessAccountDomain` | string | 執行負責事件之程式之帳戶的網域 |
| `InitiatingProcessAccountName` | string | 執行負責事件之程式之帳戶的使用者名稱 |
| `InitiatingProcessAccountSid` | string | 執行 (之) 之帳戶的安全性識別碼為 SID |
| `InitiatingProcessIntegrityLevel` | string | 初始化事件之程式的完整性層級。 Windows 會依據特定特性指派完整性層級給程式，例如從網際網路下載啟動程式。 這些完整性等級會影響資源的許可權 |
| `InitiatingProcessTokenElevation` | string | 指出使用者存取控制存在或不存在的權杖類型 (UAC) 許可權提高已應用至初始化事件的流程 |
| `InitiatingProcessSHA1` | string | 初始化活動的影像 (的 SHA-1) 影像檔案 |
| `InitiatingProcessSHA256` | string | 初始化事件的 (的 SHA-256) 影像檔案。 此欄位通常無法填出，請使用 SHA1 欄 |
| `InitiatingProcessMD5` | string | 初始化活動的 (圖像) MD5 雜湊 |
| `InitiatingProcessFileName` | string | 初始化事件之程式的名稱 |
| `InitiatingProcessId` | int | 程式識別碼 (初始化) 的 PID 值 |
| `InitiatingProcessCommandLine` | string | 用來執行初始化事件的流程的命令列 |
| `InitiatingProcessCreationTime` | datetime | 啟動事件之程式開始的日期和時間 |
| `InitiatingProcessFolderPath` | string | 啟動事件之 (圖像) 的資料夾 |
| `InitiatingProcessParentId` | int | 程式識別碼 (產生) 事件之父流程的 PID 值 |
| `InitiatingProcessParentFileName` | string | 指定事件所負責之程式之父程式的名稱 |
| `InitiatingProcessParentCreationTime` | datetime | 事件負責之程式父項開始的日期和時間 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一事件，此欄必須與 DeviceName 和 Timestamp 資料行一起使用 |
| `AppGuardContainerId` | string | Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼 |
| `IsLocalAdmin` | 布林值 | 使用者是否在電腦本機系統管理員的布林值指示器 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
