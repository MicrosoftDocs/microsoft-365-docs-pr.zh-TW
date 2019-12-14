---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessmentKB 表格
description: 在進階搜捕結構描述之 DeviceTvmSecureConfigurationAssessmentKB 表格中，了解由威脅與弱點管理評估的各種安全性設定。
keywords: 進階搜捕、威脅搜捕、網路威脅搜捕、搜尋、查詢、遙測、結構描述參考、Kusto、表格、欄、資料類型、描述、威脅與弱點管理、TVM、裝置管理、安全性設定、MITRE ATT&CK 架構、知識庫、KB、DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 62c21545be31c7332fba28348b7159a0d46aa4b3
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910891"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

**適用範圍：**
- Microsoft 威脅防護

[!include[Prerelease information](prerelease.md)]

在進階搜捕結構描述中的 `DeviceTvmSecureConfigurationAssessmentKB` 表格包含各種安全性設定的資訊 (如裝置是否已開啟自動更新)，是由[威脅與弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)進行檢查。 其中也包含風險資訊、相關的行業效能評定，以及適用的 MITRE ATT&CK 技術和技巧。 使用這個參考來建立從表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `ConfigurationId` | 字串 | 特定組態的唯一識別碼 |
| `ConfigurationImpact` | 字串 | 設定對整個組態分數 (1-10) 的評分影響 |
| `ConfigurationName` | 字串 | 組態的顯示名稱 |
| `ConfigurationDescription` | 字串 | 組態的描述 |
| `RiskDescription` | 字串 | 相關風險的描述 |
| `ConfigurationCategory` | 字串 | 組態所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制|
| `ConfigurationSubcategory` | 字串 |組態所屬的子類別或子群組。 在許多情況下，這會描述特定性能或功能。 |
| `ConfigurationBenchmarks` | 字串 | 行業效能評定清單建議相同或類似的設定 |
| `RelatedMitreTechniques` | 字串 | 與設定相關的 Mitre ATT&CK 架構技術清單 |
| `RelatedMitreTactics ` | 字串 | 與設定相關的 Mitre ATT&CK 架構技巧清單 |

## <a name="related-topics"></a>相關主題

- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [威脅與弱點管理的概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
