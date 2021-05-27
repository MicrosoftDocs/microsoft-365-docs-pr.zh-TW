---
title: Advanced 搜尋架構中的 DeviceInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceInfo 資料表中的作業系統、電腦名稱稱及其他機器資訊
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、Microsoft 365 Defender、Microsoft 365、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、machineinfo、DeviceInfo、裝置、電腦、OS、平臺、使用者
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
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689106"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender
- 適用於端點的 Microsoft Defender



[！附注] `DeviceInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含組織中裝置的相關資訊，包括作業系統版本、作用中使用者及電腦名稱稱。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ClientVersion` | string | 電腦上執行的端點代理程式或感應器版本 |
| `PublicIP` | string | 架電腦用來連接至 Microsoft Defender for Endpoint service 的公用 IP 位址。 這可以是電腦本身、NAT 裝置或 proxy 的 IP 位址 |
| `OSArchitecture` | 字串 | 電腦上執行的作業系統架構。 |
| `OSPlatform` | 字串 | 電腦上執行的作業系統平台。 這表示特定作業系統（包括相同家族內的變化），例如 Windows 10 和 Windows 7 |
| `OSBuild` | string | 電腦上所執行作業系統的組建版本 |
| `IsAzureADJoined` | 布林值 | 布林指標，表示機器是否已加入 Azure Active Directory |
| `AadObjectId` | string | Azure AD 中裝置的唯一識別碼 |
| `LoggedOnUsers` | string | 以 JSON 陣列格式出現事件時，在機器上記錄的所有使用者清單 |
| `RegistryDeviceTag` | string | 透過登錄加入的電腦標記 |
| `OSVersion` | 字串 | 電腦上執行的作業系統版本。 |
| `MachineGroup` | 字串 | 機器的電腦群組。 這個群組是由以角色為基礎的存取控制用來判斷對機器的存取權 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用 |
| `OnboardingStatus` | string | 表示裝置目前是架，或不是 Microsoft Defender For Endpoint，或是不支援裝置 |
|`AdditionalFields` | string | 有關 JSON 陣列格式之事件的其他資訊 |
|`DeviceCategory` | string | 在下列類別中群組特定裝置類型的更大分類：端點、網路裝置、IoT、不明 |
|`DeviceType` | string | 根據用途及功能的裝置類型，例如網路裝置、工作站、伺服器、行動裝置、遊戲主控台或印表機 |
|`DeviceSubType` | string | 某些類型裝置的其他修飾符，例如行動裝置可以是平板電腦或 smartphone |
|`Model` | string | 廠商或製造商產品的模型名稱或編號 |
|`Vendor` | string | 產品廠商或製造商的名稱 |
|`OSDistribution` | string | 分散式作業系統平臺，例如 Ubuntu 或 RedHat for Linux 平臺 |
|`OSVersionInfo` | string | 作業系統版本的其他相關資訊，例如常用名稱、程式碼名稱或版本號碼 |
|`MergedDeviceIds` | string | 已指派給相同裝置的先前裝置 IDs |
|`MergedToDeviceId` | string | 指派給裝置的最近裝置識別碼 |

`DeviceInfo`表格提供以心跳方式（即來自裝置的定期報告或信號）為基礎的裝置資訊。 每十五分鐘，裝置會傳送部分心跳，其中包含經常變更的屬性，如 `LoggedOnUsers` 。 一天一次，會傳送包含裝置之屬性的完整心跳。

您可以使用下列範例查詢取得裝置的最新狀態：

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
