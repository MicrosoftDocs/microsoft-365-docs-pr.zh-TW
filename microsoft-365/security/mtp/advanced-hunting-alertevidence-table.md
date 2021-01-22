---
title: 進位搜尋架構中的 AlertEvidence 資料表
description: 在進位搜尋架構的 AlertEvidence 資料表中瞭解與警示相關聯的資訊
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、資料表、資料行、資料類型、描述、警示資訊、警示、實體、證據、檔案、IP 位址、裝置、電腦、使用者、帳戶
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
ms.openlocfilehash: c01b0aae1eff3d9b4add632aff0f13cb56941a30
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932297"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

進位搜尋架構中的表格包含與 `AlertEvidence` 來自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 及 Microsoft Defender for Identity 之警示相關聯的各種實體相關資訊，例如檔案、IP 位址[](advanced-hunting-overview.md)、URL、使用者或裝置。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `AlertId` | 字串 | 警示的唯一識別碼。 |
| `ServiceSource` | string | 提供警示資訊的產品或服務 |
| `EntityType` | string | 物件類型，例如檔案、程式、裝置或使用者 |
| `EvidenceRole` | string | 實體如何參與警示，指出該警示是否受到影響或僅與警示相關 |
| `EvidenceDirection` | string | 指出實體是網路連接的來源或目的地 |
| `FileName` | 字串 | 記錄動作已套用的檔案名稱 |
| `FolderPath` | 字串 | 包含已記錄動作所使用之檔案的資料夾 |
| `SHA1` | 字串 | 記錄動作已套用的檔案 SHA-1 |
| `SHA256` | 字串 | 記錄動作已套用的檔案 SHA-256。 此欄位通常不會填出，可用時請使用 SHA1 欄。 |
| `FileSize` | int | 檔案大小 ，以位元組為單位 |
| `ThreatFamily` | string | 已分類為以下專案之可疑或惡意檔案或程式下的惡意程式碼系列 |
| `RemoteIP` | 字串 | 連線到的 IP 位址 |
| `RemoteUrl` | 字串 | 已連線到的 URL 或完整網域名稱 (FQDN) |
| `AccountName` | 字串 | 帳戶的使用者名稱 |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountSid` | string | 帳戶 (安全性) SID 識別碼 |
| `AccountObjectId` | string | Azure Active Directory 中帳戶的唯一識別碼 |
| `DeviceId` | string | 服務中裝置的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `LocalIP` | string | 指派給通訊期間使用之本地裝置之 IP 位址 |
| `NetworkMessageId` | string | Office 365 產生的電子郵件唯一識別碼 |
| `EmailSubject` | 字串 | 電子郵件的主旨 |
| `ApplicationId` | 字串 | 應用程式的唯一識別碼 |
| `Application` | string | 執行錄製動作的應用程式 |
| `ProcessCommandLine` | string | 用來建立新流程的命令列 |
| `AdditionalFields` | string | 以 JSON 陣列格式顯示之事件的其他資訊 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
