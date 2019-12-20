---
title: DeviceLogonEvents 資料表中的進階的狩獵結構描述
description: 了解驗證] 或 [進階的狩獵結構描述 DeviceLogonEvents 表格中的登入事件
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 描述、 logonevents，DeviceLogonEvents，驗證、 登入、 登入
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
ms.openlocfilehash: 5e694bb58952acb0e6cd0b436c72ed3cf170a5c5
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809250"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

適用於：****
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`DeviceLogonEvents` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含使用者的登入及其他驗證事件的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | 字串 | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ActionType` | string |觸發事件的活動類型 |
| `AccountDomain` | string | 此帳戶的網域 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountSid` | string | 安全性識別碼 (SID) 的帳戶 |
| `LogonType` | string | 輸入的登入工作階段，特別是：<br><br> - 使用本機鍵盤和螢幕的機器與實體互動**互動**使用者<br><br> - **遠端互動式 (RDP) 登入**使用者互動遠端使用遠端桌面、 終端機服務、 遠端協助 」 或其他 RDP 用戶端電腦<br><br> - **網路**-起始當機器會存取使用 PsExec 或存取在機器上，例如印表機和共用的資料夾的共用的資源的工作階段<br><br> - **批次**排定的工作所起始的工作階段<br><br> - **服務**-為啟動時，服務所起始的工作階段<br> |
| `LogonId` | string | 登入工作階段的識別碼。 此識別碼會在僅限之間重新啟動在同一部機器上的唯一 |
| `RemoteDeviceName` | string | 執行受影響的電腦上的遠端作業的機器名稱。 根據所報告的事件，此名稱可能是完整網域名稱 (FQDN)，NetBIOS 名稱或沒有網域資訊的主機名稱 |
| `RemoteIP` | 字串 | 連線到的 IP 位址 |
| `RemoteIPType` | string | IP 位址，例如公用、 私用、 保留、 回送、 Teredo、 FourToSixMapping 及廣播的類型 |
| `RemotePort` | int | 已連線至遠端裝置上的 TCP 連接埠 |
| `AdditionalFields` | string | 以 JSON 陣列格式事件相關的其他資訊 |
| `InitiatingProcessAccountDomain` | string | 執行負責事件程序的帳戶網域 |
| `InitiatingProcessAccountName` | string | 執行負責事件程序的帳戶使用者名稱 |
| `InitiatingProcessAccountSid` | string | 安全性識別碼 (SID) 執行負責事件程序的帳戶 |
| `InitiatingProcessIntegrityLevel` | string | 初始化事件程序的完整性層級。 Windows 會指派完整性層級根據若干特質程序，例如如果他們已啟動從網際網路下載。 這些完整性層級影響資源的權限 |
| `InitiatingProcessTokenElevation` | string | 指出使用者存取控制 (UAC) 提高權限套用至初始化事件程序存在的 token 型別 |
| `InitiatingProcessSHA1` | string | SHA-1 起始之事件程序 （影像檔案） |
| `InitiatingProcessSHA256` | string | SHA 256 初始化事件程序 （影像檔案）。 通常沒有填入此欄位 — 使用時可用的 SHA1 欄 |
| `InitiatingProcessMD5` | string | 初始化事件程序 （影像檔案） 的 MD5 雜湊 |
| `InitiatingProcessFileName` | string | 初始化事件的處理序名稱 |
| `InitiatingProcessId` | int | 處理程序識別碼 (PID) 的起始事件程序 |
| `InitiatingProcessCommandLine` | string | 用來執行初始化事件程序的命令列 |
| `InitiatingProcessCreationTime` | datetime | 初始化事件程序時已開始日期和時間 |
| `InitiatingProcessFolderPath` | string | 包含起始事件程序 （影像檔案） 的資料夾 |
| `InitiatingProcessParentId` | int | 處理程序識別碼 (PID) 的產生處理程序負責事件父處理序 |
| `InitiatingProcessParentFileName` | string | 產生負責事件程序的父處理序名稱 |
| `InitiatingProcessParentCreationTime` | datetime | 日期和時間的父代負責事件程序已啟動時 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄 |
| `AppGuardContainerId` | string | 虛擬化的容器應用程式防護用於隔離瀏覽器活動識別碼 |
| `IsLocalAdmin` | 布林值 | 布林值的使用者是否在電腦上的本機系統管理員指示器 |

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
