---
title: 進階搜捕結構描述中的 DeviceTvmSoftwareInventoryVulnerabilities 表格
description: 了解裝置中的軟體清單及其在進階搜捕結構描述之 DeviceTvmSoftwareInventoryVulnerabilities 表格中的弱點。
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 描述、 威脅 & 弱點管理、 TVM，裝置管理，軟體清查，弱點，CVE-2018 識別碼、 OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 92c06eb01abd13df22ae33e72d9663084b05f7ef
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600290"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

**適用範圍：**
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

進階搜捕結構描述中的 `DeviceTvmSoftwareInventoryVulnerabilities` 表格包含裝置上軟體庫存的 [威脅與弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)，以及這些軟體產品中的任何已知弱點。 本表格也包含作業系統資訊、CVE 識別碼和弱點嚴重性的資訊。 使用這個參照來建立從表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，請參閱 [進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `DeviceId` | 字串 | 服務中電腦的唯一識別碼 |
| `DeviceName` | 字串 | 電腦的完整網域名稱 (FQDN) |
| `OSPlatform` | 字串 | 電腦上執行的作業系統平台。 這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。 |
| `OSVersion` | 字串 | 電腦上執行的作業系統版本。 |
| `OSArchitecture` | 字串 | 電腦上執行的作業系統架構。 |
| `SoftwareVendor` | 字串 | 安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素 |
| `SoftwareName` | 字串 | 軟體產品名稱 |
| `SoftwareVersion` | 字串 | 軟體產品的版本號碼 |
| `CveId` | 字串 | 在常見弱點與漏洞 (CVE) 系統下指派給安全性弱點的唯一識別碼 |
| `VulnerabilitySeverityLevel` | 字串 | 安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素 |



## <a name="related-topics"></a>相關主題

- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
- [威脅與弱點管理的概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
