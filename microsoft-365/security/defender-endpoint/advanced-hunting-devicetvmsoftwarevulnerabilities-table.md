---
title: Advanced 搜尋架構中的 DeviceTvmSoftwareVulnerabilities 表格
description: 深入瞭解在裝置上找到的軟體弱點，以及可在高級搜尋架構的 DeviceTvmSoftwareVulnerabilities 資料表中處理每個弱點的可用安全性更新清單。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、架構參考、kusto、table、column、data type、description、威脅 & 漏洞管理、TVM、裝置管理、軟體、清查、弱點、CVE 識別碼、OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060260"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

「 `DeviceTvmSoftwareVulnerabilities` 高級搜尋」架構中的表格包含已安裝軟體產品中弱點的 [威脅 & 漏洞管理](next-gen-threat-and-vuln-mgt.md) 清單。 本表格也包含作業系統資訊、CVE 識別碼和弱點嚴重性的資訊。 例如，您可以使用此表格來搜尋有關其軟體中有嚴重弱點之裝置的事件。 使用這個參考來建立從表格取回之資訊的查詢。

>[!NOTE]
>`DeviceTvmSoftwareInventory`和 `DeviceTvmSoftwareVulnerabilities` tables 已取代 `DeviceTvmSoftwareInventoryVulnerabilities` 表格。 前兩個表格一起包含更多資料行，您可以用來協助通知您的漏洞管理活動。

如需進階搜捕結構描述中其他資料表的資訊，請參閱 [進階搜捕參考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。

| 資料行名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `DeviceId` | string | 服務中裝置的唯一識別碼 |
| `DeviceName` | string | 裝置的完整功能變數名稱 (FQDN)  |
| `OSPlatform` | string | 裝置上所執行作業系統的平臺。 這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。 |
| `OSVersion` | 字串 | 裝置上所執行的作業系統版本 |
| `OSArchitecture` | string | 裝置上所執行作業系統的架構 |
| `SoftwareVendor` | string | 軟體廠商的名稱 |
| `SoftwareName` | 字串 | 軟體產品名稱 |
| `SoftwareVersion` | 字串 | 軟體產品的版本號碼 |
| `CveId` | 字串 | 在常見弱點與漏洞 (CVE) 系統下指派給安全性弱點的唯一識別碼 |
| `VulnerabilitySeverityLevel` | 字串 | 安全性弱點之嚴重性層級的指派是根據 CVSS 分數，以及受威脅環境影響的動態因素 |
| `RecommendedSecurityUpdate` | 字串 | 軟體廠商提供的安全性更新名稱或描述，以解決此弱點 |
| `RecommendedSecurityUpdateId` | string | 對應的指導或知識庫 (KB) 文章的適用安全性更新或識別碼識別碼 |



## <a name="related-topics"></a>相關主題

- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
- [威脅與弱點管理的概觀](next-gen-threat-and-vuln-mgt.md)
