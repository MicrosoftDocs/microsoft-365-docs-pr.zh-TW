---
title: Advanced 搜尋架構中的 CloudAppEvents 表格
description: 深入瞭解高級搜尋架構之 CloudAppEvents 資料表中 cloud apps and service 的事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，data type，description，CloudAppEvents，雲端 App 安全性，MCAS
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
ms.openlocfilehash: 17f424d368c0df2f07cda41917f005e4163e5750
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935866"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender



[！附注] `CloudAppEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含 Microsoft Cloud App Security 所涵蓋之各種雲端 app 和服務中的活動相關資訊。 如需完整清單，請跳至 [應用程式和服務涵蓋](#apps-and-services-covered)。 使用這個參考來建立從此表格取回之資訊的查詢。 

>[!IMPORTANT]
>此表格包含可用於表格的資訊 `AppFileEvents` 。 從2021年3月7日起，使用者在此日期以外的雲端服務中搜尋與檔案相關的活動，應改為使用 `CloudAppEvents` 表格。 <br><br>請務必搜尋查詢和自訂偵測規則，該規則仍會使用 `AppFileEvents` 該表，並進行編輯，以使用 `CloudAppEvents` 該表。 若要瞭解轉換受影響查詢的相關指引[，請參閱使用 Microsoft 365 Defender 高級搜尋來搜尋各項 cloud app activity](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)。


如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `ActionType` | string | 觸發事件的活動類型 |
| `Application` | string | 執行錄製動作的應用程式 |
| `ApplicationId` | string | 應用程式的唯一識別碼 |
| `AccountObjectId` | string | 帳戶在 Azure Active Directory 中的唯一識別碼 |
| `AccountDisplayName` | string | 顯示在通訊錄中之帳戶使用者的名稱。 通常是指定的名稱或名字、中間初始名稱或姓氏的組合。 |
| `IsAdminOperation` | string | 指出活動是否由系統管理員執行 |
| `DeviceType` | string | 根據用途及功能的裝置類型，例如「網路裝置」、「工作站」、「伺服器」、「Mobile」、「遊戲主控台」或「印表機」。 | 
| `OSPlatform` | string | 裝置上所執行作業系統的平臺。 此欄會指出特定的作業系統，包括相同系列內的變化，例如 Windows 10 和 Windows 7。 |
| `IPAddress` | string | 指派給端點的 IP 位址，並在相關的網路通訊期間使用 |
| `IsAnonymousProxy` | string | 指出 IP 位址是否屬於已知的匿名 proxy |
| `CountryCode` | string | 兩個字母的代碼，指出用戶端 IP 位址為 geolocated 的國家/地區 |
| `City` | string | 用戶端 IP 位址為 geolocated 的城市 |
| `Isp` | string | 網際網路服務提供者 (與 IP 位址相關聯的 ISP)  |
| `UserAgent` | string | 來自網頁瀏覽器或其他用戶端應用程式的使用者代理程式資訊 |
| `ActivityType` | string | 觸發事件的活動類型 |
| `ActivityObjects` | string | 錄製的活動中所涉及的物件（例如檔案或資料夾）的清單 |
| `ObjectName` | string | 已錄製動作套用至之物件的名稱 |
| `ObjectType` | string | 錄製的動作所套用的物件類型，例如檔案或資料夾 |
| `ObjectId` | string | 套用錄製動作之物件的唯一識別碼 |
| `ReportId` | string | 事件的唯一識別碼 |
| `RawEventData` | string | 來源應用程式或服務中 JSON 格式的原始事件資訊 |
| `AdditionalFields` | string | 實體或事件的其他資訊 |

## <a name="apps-and-services-covered"></a>應用程式和服務涵蓋

- Dropbox
- Dynamics 365
- Exchange Online
- Microsoft Teams
- 商務用 OneDrive
- 電源自動化
- Power BI
- SharePoint Online
- 商務用 Skype
- Office 365
- Yammer 

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
