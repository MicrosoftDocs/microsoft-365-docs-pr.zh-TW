---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessmentKB 表格
description: 在進階搜捕結構描述之 DeviceTvmSecureConfigurationAssessmentKB 表格中，了解由威脅與弱點管理評估的各種安全性設定。
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，table，欄，資料類型，描述，威脅 & 漏洞管理，TVM，裝置管理，安全性設定，MITRE ATT&CK framework，知識庫，KB，DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 23b109ee5c149ecf9015f8c1622e03b20bdf243c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907324"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用範圍：**
- Microsoft 365 Defender



在進階搜捕結構描述中的 `DeviceTvmSecureConfigurationAssessmentKB` 表格包含各種安全性設定的資訊 (如裝置是否已開啟自動更新)，是由[威脅與弱點管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)進行檢查。 其中也包含風險資訊、相關的行業效能評定，以及適用的 MITRE ATT&CK 技術和技巧。 使用這個參考來建立從表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 資料行名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `ConfigurationId` | string | 特定設定的唯一識別碼 |
| `ConfigurationImpact` | string | 設定對整個組態分數 (1-10) 的評分影響 |
| `ConfigurationName` | 字串 | 組態的顯示名稱 |
| `ConfigurationDescription` | 字串 | 組態的描述 |
| `RiskDescription` | 字串 | 相關風險的描述 |
| `ConfigurationCategory` | 字串 | 設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制|
| `ConfigurationSubcategory` | string |設定所屬的子類別或子群組。 在許多情況下，這會描述特定性能或功能。 |
| `ConfigurationBenchmarks` | 字串 | 行業效能評定清單建議相同或類似的設定 |
| `Tags` | 字串 | 代表用來識別或分類安全性設定之各種屬性的標籤 |
| `RemediationOptions` | string | 建議的動作可減少或解決任何相關聯的風險 |

## <a name="related-topics"></a>相關主題

- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [威脅與弱點管理的概觀](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)