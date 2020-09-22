---
title: Advanced 搜尋架構中的 DeviceLogonEvents 表格
description: 深入瞭解高級搜尋架構的 DeviceLogonEvents 資料表中的驗證或登入事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，資料表，欄，資料類型，描述，logonevents，DeviceLogonEvents，authentication，logon，登入
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
ms.openlocfilehash: 1e866c2c7fb43b4ab041a1d3d5d6e66c2bbb0767
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197094"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：****
- Microsoft 威脅防護



[！附注] `DeviceLogonEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含有關裝置上使用者登入和其他驗證事件的資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的 [內建架構參照](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ActionType` | string |觸發事件的活動類型 |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountSid` | string | 帳戶的安全性識別碼 (SID)  |
| `LogonType` | string | 登入會話的類型，特別：<br><br> - **互動式** 使用者會使用本機鍵盤和畫面，以實際方式與機器互動<br><br> - **遠端互動 (RDP) ** 登入-使用者利用遠端桌面、終端機服務、遠端協助或其他 RDP 用戶端從遠端與機器互動<br><br> - 使用 PsExec 存取機器時，或在機器上共用資源（如印表機和共用資料夾）存取時，所啟動的**網路**會話<br><br> - 由排程任務所啟動的**批次**會話<br><br> - **服務** -啟動時由服務啟動的會話<br> |
| `LogonId` | string | 登入會話的識別碼。 只有在重新開機時，此識別碼在同一部電腦上是唯一的 |
| `RemoteDeviceName` | string | 在受影響的機器上執行遠端作業的機器名稱。 根據所報告的事件，此名稱可以是完整功能變數名稱 (FQDN) 、NetBIOS 名稱或沒有網域資訊的主機名稱。 |
| `RemoteIP` | 字串 | 連線到的 IP 位址 |
| `RemoteIPType` | string | IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播 |
| `RemotePort` | int | 連線的遠端裝置上的 TCP 埠 |
| `AdditionalFields` | string | 有關 JSON 陣列格式之事件的其他資訊 |
| `InitiatingProcessAccountDomain` | string | 執行負責事件之處理常式之帳戶的網域 |
| `InitiatingProcessAccountName` | string | 負責事件之處理常式的帳戶使用者名稱 |
| `InitiatingProcessAccountSid` | string | 執行事件負責處理之帳戶的安全性識別碼 (SID)  |
| `InitiatingProcessIntegrityLevel` | string | 啟動事件之處理常式的完整性層級。 Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。 這些完整性層級會影響資源的許可權 |
| `InitiatingProcessTokenElevation` | string | 指出是否存在使用者存取控制的 Token 類型 (UAC) 許可權提升會套用至啟動事件的程式。 |
| `InitiatingProcessSHA1` | string | 啟動事件) 的處理常式 (映射檔 SHA-1 |
| `InitiatingProcessSHA256` | string | 啟動事件) 的處理常式 (映射檔 SHA-256。 通常不會填入此欄位，可使用 SHA1] 欄位 |
| `InitiatingProcessMD5` | string | 啟動事件之程式 (映射檔) 的 MD5 雜湊 |
| `InitiatingProcessFileName` | string | 啟動事件的進程名稱 |
| `InitiatingProcessId` | int | 啟動事件之程式的進程識別碼 (PID)  |
| `InitiatingProcessCommandLine` | string | 用來執行啟動事件之處理常式的命令列 |
| `InitiatingProcessCreationTime` | datetime | 啟動事件處理常式的日期和時間 |
| `InitiatingProcessFolderPath` | string | 包含初始化事件之處理 (映射檔) 程式的資料夾 |
| `InitiatingProcessParentId` | int | 產生負責事件之處理常式之父進程的進程識別碼 (PID)  |
| `InitiatingProcessParentFileName` | string | 產生負責事件之處理常式的父進程名稱 |
| `InitiatingProcessParentCreationTime` | datetime | 啟動事件之處理常式的父項時的日期和時間 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用 |
| `AppGuardContainerId` | string | Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼 |
| `IsLocalAdmin` | 布林值 | 布林值指標，表示使用者是否為電腦上的本機系統管理員 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕裝置、電子郵件、應用程式和身分識別](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
