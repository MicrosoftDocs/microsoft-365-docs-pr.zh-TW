---
title: Advanced 搜尋架構中的 DeviceInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceInfo 資料表中的作業系統、電腦名稱稱及其他機器資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，資料表，欄，資料類型，描述，machineinfo，DeviceInfo，device，machine，OS，平臺，使用者
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
ms.openlocfilehash: 1bb48b4332bc9d60de15bb513f04a503d6a6913b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842711"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender



[！附注] `DeviceInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含組織中電腦的相關資訊，包括作業系統版本、作用中使用者及電腦名稱稱。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ClientVersion` | string | 電腦上執行的端點代理程式或感應器版本 |
| `PublicIP` | string | 架電腦用來連接至 Microsoft Defender for Endpoint service 的公用 IP 位址。 這可以是電腦本身、NAT 裝置或 proxy 的 IP 位址 |
| `OSArchitecture` | 字串 | 電腦上執行的作業系統架構。 |
| `OSPlatform` | 字串 | 電腦上執行的作業系統平台。 這表示特定作業系統（包括相同家族內的變化，例如 Windows 10 和 Windows 7） |
| `OSBuild` | string | 電腦上所執行作業系統的組建版本 |
| `IsAzureADJoined` | 布林值 | 對電腦是否加入 Azure Active Directory 的布林指標 |
| `LoggedOnUsers` | string | 以 JSON 陣列格式出現事件時，在機器上記錄的所有使用者清單 |
| `RegistryDeviceTag` | string | 透過登錄加入的電腦標記 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用 |
| `OSVersion` | 字串 | 電腦上執行的作業系統版本。 |
| `MachineGroup` | 字串 | 機器的電腦群組。 這個群組是由以角色為基礎的存取控制用來判斷對機器的存取權 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕裝置、電子郵件、應用程式和身分識別](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
