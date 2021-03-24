---
title: 進階搜捕結構描述中的 DeviceTvmSecureConfigurationAssessment 資料表
description: 深入瞭解高級搜尋架構的 DeviceTvmSecureConfigurationAssessment 資料表中的威脅 & 漏洞管理安全性評估事件。 這些事件會提供裝置資訊，以及安全性設定詳細資料、影響和符合性資訊。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、威脅 & 漏洞管理、TVM、裝置管理、安全性設定、DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059767"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

適用於：
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

`DeviceTvmSecureConfigurationAssessment` 資料表中的每一個資料列都包含來自[威脅和弱點管理](next-gen-threat-and-vuln-mgt.md)的特定安全性設定評估事件。 使用這個參考資料來檢查最新的評估結果，並判斷裝置是否符合規定。

如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。

| 資料行名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `DeviceId` | string | 服務中裝置的唯一識別碼 |
| `DeviceName` | string | 裝置的完整功能變數名稱 (FQDN)  |
| `OSPlatform` | string | 裝置上所執行作業系統的平臺。 這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。|
| `Timestamp` | datetime |記錄的產生日期和時間 |
| `ConfigurationId` | string | 特定設定的唯一識別碼 |
| `ConfigurationCategory` | string | 設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制 |
| `ConfigurationSubcategory` | string |設定所屬的子類別或子群組。 在許多情況下，這會描述特定性能或功能。 |
| `ConfigurationImpact` | string | 設定對整個設定分數 (1-10) 的評分影響 |
| `IsCompliant` | 布林值 | 指出設定或原則是否已正確設定 |
| `IsApplicable` | 布林值 | 指出設定或原則是否適用于裝置 |
| `Context` | string | 有關設定或原則的其他相關資訊 |
| `IsExpectedUserImpactCompliant` | 布林值 | 指出如果套用設定或原則，是否會影響使用者 |

## <a name="related-topics"></a>相關主題

- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
- [威脅與弱點管理的概觀](next-gen-threat-and-vuln-mgt.md)