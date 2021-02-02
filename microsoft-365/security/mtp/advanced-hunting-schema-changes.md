---
title: Microsoft 365 Defender advanced 搜尋架構中的命名變更
description: 追蹤和審閱高級搜尋架構中的命名變更表格和欄
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、資料、命名變更、重新命名、Microsoft 威脅防護
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
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066866"
---
# <a name="advanced-hunting-schema---naming-changes"></a>高級搜尋架構命名變更

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

「 [高級搜尋」架構](advanced-hunting-schema-tables.md) 會定期更新，以加入新的資料表和欄。 在某些情況下，會重新命名或取代現有的欄名，以提升使用者經驗。 請參閱本文，以複查可能影響查詢的命名變更。

命名變更會自動套用至儲存在 [安全性中心] 中的查詢，包括自訂偵測規則所使用的查詢。 您不需要手動更新這些查詢。 不過，您將需要更新下列查詢：
- 使用 API 執行的查詢
- 儲存在安全性中心以外其他位置的查詢

## <a name="december-2020"></a>2020 年 12 月

| 表格名稱 | 原始欄名稱 | 新欄名稱 | 變更的原因
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | 客戶意見反應 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | 客戶意見反應 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | 客戶意見反應 |

## <a name="january-2021"></a>2021 年 1 月

| 資料行名稱 | 原始值名稱 | 新值名稱 | 變更的原因
|--|--|--|--|
| `DetectionSource` | MCAS |    Microsoft Cloud App Security | ..Org |
| `DetectionSource` | WindowsDefenderAtp|   EDR| ..Org |
| `DetectionSource` | WindowsDefenderAv | 防毒 | ..Org |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | ..Org |
| `DetectionSource` | CustomerTI |  自訂 TI | ..Org |
| `DetectionSource` | OfficeATP | 適用於 Office 365 的 Microsoft Defender | ..Org |
| `DetectionSource` | 具有 MTP 之   | Microsoft 365 Defender | ..Org |
| `DetectionSource` | AzureATP |    適用於身分識別的 Microsoft Defender | ..Org |
| `DetectionSource` | CustomDetection   | 自訂偵測 | ..Org |
| `DetectionSource` | AutomatedInvestigation |自動調查 | ..Org |
| `DetectionSource` | ThreatExperts | Microsoft 威脅專家 | ..Org |
| `DetectionSource` | 協力廠商的 TI | 協力廠商感應器 | ..Org |
| `ServiceSource` | Microsoft Defender ATP| 適用於端點的 Microsoft Defender | ..Org |
|`ServiceSource` |Microsoft 威脅防護   | Microsoft 365 Defender | ..Org |
| `ServiceSource` | Office 365 ATP  |適用於 Office 365 的 Microsoft Defender | ..Org |
| `ServiceSource` |Azure ATP    |適用於身分識別的 Microsoft Defender | ..Org |

`DetectionSource` 可用於 [AlertInfo](advanced-hunting-alertinfo-table.md) 表格。 `ServiceSource` 可用於 [AlertEvidence](advanced-hunting-alertevidence-table.md) 和 [AlertInfo](advanced-hunting-alertinfo-table.md) 資料表。 
## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解結構描述](advanced-hunting-schema-tables.md)