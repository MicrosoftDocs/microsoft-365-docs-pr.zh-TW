---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessment 資料表
description: 瞭解進位搜尋架構的 Device時間MSecureConfigurationAssesment 資料表中的安全性評定事件。 這些威脅&管理事件提供裝置資訊，以及安全性設定檔詳細資料、影響和合規性資訊。
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、威脅 & 弱點管理、TVM、裝置管理、安全性群組原則、DeviceMicmSecureConfigurationAssesment
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
ms.openlocfilehash: 6924bbc7a88a4f32d97534c72a180a1f1c4f7db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931095"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender



`DeviceTvmSecureConfigurationAssessment` 資料表中的每一個資料列都包含來自[威脅和弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的特定安全性設定評估事件。 使用這個參考資料來檢查最新的評估結果，並判斷裝置是否符合規定。

如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md)。

| 資料行名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `DeviceId` | string | 服務中裝置的唯一識別碼 |
| `DeviceName` | string | 裝置 FQDN (完整) 功能變數名稱 |
| `OSPlatform` | string | 在裝置上作業系統平臺。 這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。|
| `Timestamp` | datetime | 記錄的產生日期和時間 |
| `ConfigurationId` | string | 特定設定的唯一識別碼 |
| `ConfigurationCategory` | string | 設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制 |
| `ConfigurationSubcategory` | string | 設定所屬的子類別或子群組。 在許多情況下，這會描述特定性能或功能。 |
| `ConfigurationImpact` | string | 設定對整個設定分數 (1-10) 的評分影響 |
| `IsCompliant` | 布林值 | 指出設定或原則是否已正確設定 |
| `IsApplicable` | 布林值 | 指出該組配置或原則是否適用于裝置 |
| `Context` | string | 有關群組原則或群組原則的其他關係資訊 |
| `IsExpectedUserImpactCompliant` | 布林值 | 指出如果已應用程式組配置或原則，是否會影響使用者 |

## <a name="related-topics"></a>相關主題

- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [威脅與弱點管理的概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
