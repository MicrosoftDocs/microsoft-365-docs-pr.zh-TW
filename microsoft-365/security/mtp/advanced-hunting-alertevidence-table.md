---
title: Advanced 搜尋架構中的 AlertEvidence 表格
description: 深入瞭解與高級搜尋架構之 AlertEvidence 表格中的警示相關的資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，資料表，欄，資料類型，描述，AlertInfo，alert，實體，證據，檔案，IP 位址，裝置，機器，使用者，帳戶
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7f6a4f7592e6a8fde0b7ae6269f07ce7f76a5730
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430160"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：****
- Microsoft 威脅防護

[！附注] `AlertEvidence` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含各種實體（檔案、IP 位址、URLs、使用者或裝置）相關資訊，這些資訊與 Microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App SECURITY 和 Azure atp 相關聯的警示相關聯。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `AlertId` | 字串 | 警示的唯一識別碼。 |
| `ServiceSource` | string | 提供提醒資訊的產品或服務 |
| `EntityType` | string | 物件的類型，例如檔案、進程、裝置或使用者 |
| `EvidenceRole` | string | 如何將實體包含在警示中，指出它會受到影響或僅僅是相關的 |
| `EvidenceDirection` | string | 指出實體是否為網路連線的來源或目的地 |
| `FileName` | 字串 | 記錄動作已套用的檔案名稱 |
| `FolderPath` | 字串 | 包含錄製的動作所套用之檔案的資料夾 |
| `SHA1` | 字串 | 記錄動作已套用的檔案 SHA-1 |
| `SHA256` | 字串 | 記錄動作已套用的檔案 SHA-256。 通常不會填入此欄位，可用時使用 SHA1] 欄位。 |
| `FileSize` | int | 檔案大小（以位元組為單位） |
| `ThreatFamily` | string | 已分類的可疑或惡意檔或程式的惡意程式碼系列 |
| `RemoteIP` | 字串 | 連線到的 IP 位址 |
| `RemoteUrl` | 字串 | 已連線到的 URL 或完整網域名稱 (FQDN) |
| `AccountName` | 字串 | 帳戶的使用者名稱 |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountSid` | string | 帳戶的安全性識別碼 (SID)  |
| `AccountObjectId` | string | Azure Active Directory 中帳戶的唯一識別碼 |
| `DeviceId` | string | 服務中裝置的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `LocalIP` | string | 指派給通訊期間所使用之本機裝置的 IP 位址 |
| `NetworkMessageId` | string | Office 365 產生的電子郵件唯一識別碼 |
| `EmailSubject` | 字串 | 電子郵件的主旨 |
| `ApplicationId` | 字串 | 應用程式的唯一識別碼 |
| `Application` | string | 執行錄製動作的應用程式 |
| `ProcessCommandLine` | string | 用來建立新程式的命令列 |
| `AdditionalFields` | string | 有關 JSON 陣列格式之事件的其他資訊 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕裝置、電子郵件、應用程式和身分識別](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
