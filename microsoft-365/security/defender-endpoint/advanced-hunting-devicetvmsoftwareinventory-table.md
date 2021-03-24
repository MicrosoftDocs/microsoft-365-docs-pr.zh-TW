---
title: Advanced 搜尋架構中的 DeviceTvmSoftwareInventory 表格
description: 深入瞭解在高級搜尋架構的 DeviceTvmSoftwareInventory 資料表中，裝置中的軟體清單。
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
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060015"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

「 `DeviceTvmSoftwareInventory` 高級搜尋」架構中的表格包含目前安裝在網路裝置上之軟體的 [威脅 & 漏洞管理](next-gen-threat-and-vuln-mgt.md) 清單，包括支援資訊的結束。 例如，您可以針對與目前具有漏洞軟體版本一起安裝的裝置，尋找相關事件。 使用這個參考來建立從表格取回之資訊的查詢。

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
| `EndOfSupportStatus` | 字串 | 會指出軟體產品的生命週期階段相對於其指定的支援終止 (EOS) 或生命週期 (EOL) 日期 |
| `EndOfSupportDate` | string | 支援終止 (EOS) 或使用壽命結束 (EOL) 軟體產品的日期 |



## <a name="related-topics"></a>相關主題

- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
- [威脅與弱點管理的概觀](next-gen-threat-and-vuln-mgt.md)

