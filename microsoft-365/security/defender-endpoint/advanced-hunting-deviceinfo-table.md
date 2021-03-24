---
title: Advanced 搜尋架構中的 DeviceInfo 表格
description: 深入瞭解高級搜尋架構的 DeviceInfo 資料表中的作業系統、電腦名稱稱及其他裝置資訊
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、deviceinfo、裝置、OS、平臺、使用者、DeviceInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059795"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[！附注] `DeviceInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含組織中裝置的相關資訊，包括作業系統版本、作用中使用者及電腦名稱稱。 使用這個參考來建立從表格取回之資訊的查詢。

如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。

| 資料行名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `DeviceId` | string | 服務中裝置的唯一識別碼 |
| `DeviceName` | string | 裝置的完整功能變數名稱 (FQDN)  |
| `ClientVersion` | string | 裝置上所執行之端點代理程式或感應器的版本 |
| `PublicIP` | string | 架裝置用來連線到端點服務之 Defender 的公用 IP 位址。 這可能是裝置本身的 IP 位址、NAT 裝置或 proxy |
| `OSArchitecture` | string | 裝置上所執行作業系統的架構 |
| `OSPlatform` | string | 裝置上所執行作業系統的平臺。 這表示特定作業系統（包括相同家族內的變化，例如 Windows 10 和 Windows 7） |
| `OSBuild` | string | 裝置上所執行作業系統的組建版本 |
| `IsAzureADJoined` | 布林值 | 表示裝置是否已加入 Azure Active Directory 的布林指標 |
| `LoggedOnUsers` | string | 以 JSON 陣列格式出現事件時，在裝置上登入之所有使用者的清單 |
| `RegistryDeviceTag` | string | 透過登錄新增的裝置標記 |
| `ReportId` | long | 以重複計數器為基礎的事件識別碼。 若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用 |
| `OSVersion` | string | 裝置上所執行的作業系統版本 |
| `MachineGroup` | string | 機器的電腦群組。 這個群組是由以角色為基礎的存取控制用來判斷對機器的存取權 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [了解結構描述](advanced-hunting-schema-reference.md)
