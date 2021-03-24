---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessmentKB 表格
description: 深入瞭解 Advanced 搜尋架構的 DeviceTvmSecureConfigurationAssessmentKB 資料表中威脅 & 漏洞管理所評估的各種安全設定。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、威脅 & 漏洞管理、TVM、裝置管理、安全性設定、MITRE ATT&CK framework，知識庫，KB，DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059764"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用範圍：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

在進階搜捕結構描述中的 `DeviceTvmSecureConfigurationAssessmentKB` 表格包含各種安全性設定的資訊 (如裝置是否已開啟自動更新)，是由[威脅與弱點管理](next-gen-threat-and-vuln-mgt.md)進行檢查。 其中也包含風險資訊、相關的行業效能評定，以及適用的 MITRE ATT&CK 技術和技巧。 使用這個參考來建立從表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference) (部分內容為機器翻譯)。

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
| `RelatedMitreTechniques` | 字串 | 與設定相關的 Mitre ATT&CK 架構技術清單 |
| `RelatedMitreTactics ` | 字串 | 與設定相關的 Mitre ATT&CK 架構技巧清單 |

## <a name="related-topics"></a>相關主題

- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
- [威脅與弱點管理的概觀](next-gen-threat-and-vuln-mgt.md)
