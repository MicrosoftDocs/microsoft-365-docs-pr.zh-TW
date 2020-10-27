---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessment 資料表
description: 深入瞭解高級搜尋架構的 DeviceTvmSecureConfigurationAssessment 資料表中的安全性評估事件。 這些威脅 & 弱點管理事件會提供裝置資訊，以及安全性設定詳細資料、影響和符合性資訊。
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，資料表，欄，資料類型，描述，威脅 & 漏洞管理，TVM，裝置管理，安全性設定，DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 356548c3115aacce8c76d7fbc552811c168750ed
ms.sourcegitcommit: e8b3855302fc34d09b6df6c737033a2f326d6eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48770070"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於： 
- Microsoft 威脅防護



`DeviceTvmSecureConfigurationAssessment` 資料表中的每一個資料列都包含來自[威脅和弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的特定安全性設定評估事件。 使用這個參考資料來檢查最新的評估結果，並判斷裝置是否符合規定。

如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md)。

| 資料行名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `DeviceId` | string | 服務中裝置的唯一識別碼 |
| `DeviceName` | string | 裝置的完整功能變數名稱 (FQDN)  |
| `OSPlatform` | string | 裝置上所執行作業系統的平臺。 這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。|
| `Timestamp` | datetime | 記錄的產生日期和時間 |
| `ConfigurationId` | string | 特定設定的唯一識別碼 |
| `ConfigurationCategory` | string | 設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制 |
| `ConfigurationSubcategory` | string | 設定所屬的子類別或子群組。 在許多情況下，這會描述特定性能或功能。 |
| `ConfigurationImpact` | string | 設定對整個設定分數 (1-10) 的評分影響 |
| `IsCompliant` | 布林值 | 指出設定或原則是否已正確設定 |
| `IsApplicable` | 布林值 | 指出設定或原則是否適用于裝置 |
| `Context` | string | 有關設定或原則的其他相關資訊 |
| `IsExpectedUserImpactCompliant` | 布林值 | 指出如果套用設定或原則，是否會影響使用者 |

## <a name="related-topics"></a>相關主題

- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕裝置、電子郵件、應用程式和身分識別](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [威脅與弱點管理的概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
