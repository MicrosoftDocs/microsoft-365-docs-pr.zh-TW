---
title: 進階搜捕結構描述中的 DeviceTvmSoftwareVulnerabilitiesKB 表格
description: 了解由進階搜捕結構描述之 DeviceTvmSoftwareVulnerabilitiesKB 表格中之威脅與弱點管理所追蹤的軟體弱點。
keywords: 「高級搜尋」、「威脅搜尋」、「網路威脅搜尋」、「Microsoft 365 Defender」、「Microsoft 365」、「m365」、「搜尋」、「遙測」、「架構」、「kusto」、「表格」、「資料類型」、「描述」、「威脅 & 弱點管理、TVM、裝置管理、軟體、清查、弱點、CVE ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023794"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於**：
- Microsoft 365 Defender
- 適用於端點的 Microsoft Defender



進階搜捕結構描述中的 `DeviceTvmSoftwareVulnerabilitiesKB` 表格包含 [威脅與弱點管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)為裝置進行評估的弱點清單。 使用這個參考來建立從表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 資料行名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `CveId` | 字串 | 在常見弱點與漏洞 (CVE) 系統下指派給安全性弱點的唯一識別碼 |
| `CvssScore` | 字串 | 在常見弱點計分系統 (CVSS) 下指派給安全性弱點的嚴重性分數 |
| `IsExploitAvailable` | 布林值 | 表示該弱點的惡意探索代碼是否可供公開使用 |
| `VulnerabilitySeverityLevel` | 字串 | 安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素 |
| `LastModifiedTime` | datetime | 上次修改之項目及相關中繼資料的日期和時間 |
| `PublishedDate` | datetime | 公開的日期弱點 |
| `VulnerabilityDescription` | 字串 | 弱點及相關風險的描述 |
| `AffectedSoftware` | 字串 | 受此弱點影響的所有軟體產品清單 |

## <a name="related-topics"></a>相關主題

- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [威脅與弱點管理的概觀](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)