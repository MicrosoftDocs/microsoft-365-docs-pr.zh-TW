---
title: DeviceInfo 資料表中的進階的狩獵結構描述
description: 了解 OS、 電腦名稱，以及 DeviceInfo 表格中其他電腦資訊的進階的狩獵結構描述
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 描述、 machineinfo，DeviceInfo，裝置、 機器上，作業系統、 平台使用者
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
ms.openlocfilehash: 4c8c5cef3ba99339176086ada055d266f92c30cf
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210445"
---
# <a name="deviceinfo"></a>DeviceInfo

適用於：****
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`DeviceInfo` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含機器在組織中，包括 OS 版本、 作用中使用者和電腦名稱的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | 字串 | 服務中電腦的唯一識別碼 |
| `DeviceName` | string | 電腦的完整網域名稱 (FQDN) |
| `ClientVersion` | string | 端點代理程式或感應器在機器上執行的版本 |
| `PublicIP` | string | 用來連線至 Microsoft Defender ATP 服務上架機器的公用 IP 位址。 這可能是電腦本身的 IP 位址、 NAT 裝置或 proxy |
| `OSArchitecture` | 字串 | 電腦上執行的作業系統架構。 |
| `OSPlatform` | string | 電腦上執行的作業系統平台。 這表示特定的作業系統，包括在相同的系列，例如 Windows 10 和 Windows 7 的變化 |
| `OSBuild` | string | 建置在機器上執行的作業系統版本 |
| `IsAzureADJoined` | 布林值 | 布林值的電腦是否加入 Azure Active Directory 指示器 |
| `LoggedOnUsers` | string | JSON 陣列格式中的事件次登入電腦的所有使用者的清單 |
| `RegistryDeviceTag` | string | 機器標記新增到登錄 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄 |
| `OSVersion` | string | 電腦上執行的作業系統版本。 |
| `MachineGroup` | string | 電腦的電腦群組。 此群組決定機器的存取權限時，是由角色型存取控制 |

## <a name="related-topics"></a>相關主題
- [主動威脅搜捕](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕所有裝置和電子郵件的威脅](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)