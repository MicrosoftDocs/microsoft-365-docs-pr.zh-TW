---
title: 進位搜尋架構中的 DeviceInfo 表格
description: 在進位搜尋架構的 DeviceInfo 資料表中瞭解作業系統、電腦名稱稱和其他電腦資訊
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、machineinfo、DeviceInfo、裝置、電腦、作業系統、平臺、使用者
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
ms.openlocfilehash: e445902ee83b734f84d02607905413a14c016b8f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931275"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender



進位搜尋架構中的表格包含組織中機器的資訊，包括作業系統版本、使用中使用者 `DeviceInfo` 及電腦名稱稱。 [](advanced-hunting-overview.md) 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ClientVersion` | string | 在機器上運作端點代理程式或感應器的版本 |
| `PublicIP` | string | 上線電腦用來連接到 Microsoft Defender 端點服務的公用 IP 位址。 這可能是電腦本身的 IP 位址、NAT 裝置或 Proxy |
| `OSArchitecture` | 字串 | 電腦上執行的作業系統架構。 |
| `OSPlatform` | 字串 | 電腦上執行的作業系統平台。 這表示特定的作業系統，包括同一家庭內的變化，例如 Windows 10 和 Windows 7 |
| `OSBuild` | string | 建立電腦上所運作作業系統的版本 |
| `IsAzureADJoined` | 布林值 | 電腦是否已加入 Azure Active Directory 的布林值指示器 |
| `LoggedOnUsers` | string | 事件期間以 JSON 陣列格式登入電腦的所有使用者清單 |
| `RegistryDeviceTag` | string | 透過註冊表新增的機器標記 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一事件，此欄必須與 DeviceName 和時間戳記欄一起使用 |
| `OSVersion` | 字串 | 電腦上執行的作業系統版本。 |
| `MachineGroup` | 字串 | 電腦的機器群組。 角色型存取控制會使用這個群組來決定電腦的存取權限 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
