---
title: Advanced 搜尋架構中的 IdentityLogonEvents 表格
description: 深入瞭解在高級搜尋架構的 IdentityLogonEvents 資料表中，由 Active Directory 記錄的驗證事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，表格，欄，資料類型，描述，IdentityLogonEvents，Azure AD，Active Directory，Azure ATP，身分識別
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 2ecf6de79f5eab4aca7bc928ea64b780a257b908
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412727"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：****
- Microsoft 威脅防護

[！附注] `IdentityLogonEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含透過 Azure ATP 和驗證活動（透過 Microsoft Cloud App Security 所捕獲的 microsoft online 服務所捕獲）進行驗證的相關資訊。 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的 [內建架構參照](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。

>[!NOTE]
>下表涵蓋 Cloud App Security （特別是互動式登入及驗證活動）所追蹤的 Azure Active Directory (AD) 登入活動 ActiveSync 和其他舊版通訊協定。 您可以在 Azure AD 審核記錄中查看無法在此表格中使用的非互動式登入。 [深入瞭解將雲端 App 安全性連接至 Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `ActionType` | string | 觸發事件的活動類型。 如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `LogonType` | string | 登入會話的類型，特別：<br><br> - **互動式** 使用者會使用本機鍵盤和畫面，以實際方式與機器互動<br><br> - **遠端互動 (RDP) ** 登入-使用者利用遠端桌面、終端機服務、遠端協助或其他 RDP 用戶端從遠端與機器互動<br><br> - 使用 PsExec 存取機器時，或在機器上共用資源（如印表機和共用資料夾）存取時，所啟動的**網路**會話<br><br> - 由排程任務所啟動的**批次**會話<br><br> - **服務** -啟動時由服務啟動的會話 |
| `Application` | string | 執行錄製動作的應用程式 |
| `Protocol` | string | 使用的網路通訊協定 |
| `FailureReason` | string | 說明錄製的動作失敗原因的資訊 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountUpn` | string | 帳戶的使用者主要名稱 (UPN)  |
| `AccountSid` | string | 帳戶的安全性識別碼 (SID)  |
| `AccountObjectId` | string | Azure AD 中帳戶的唯一識別碼 |
| `AccountDisplayName` | string | 顯示在通訊錄中之帳戶使用者的名稱。 通常是指定的名稱或名字、中間初始名稱或姓氏的組合。 |
| `DeviceName` | string | 裝置的完整功能變數名稱 (FQDN)  |
| `DeviceType` | string | 裝置類型 |
| `OSPlatform` | string | 電腦上執行的作業系統平台。 這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。 |
| `IPAddress` | 字串 | 指派給端點的 IP 位址，並在相關的網路通訊期間使用 |
| `DestinationDeviceName` | string | 執行伺服器應用程式（處理錄製的動作）的裝置名稱 |
| `DestinationIPAddress` | string | 執行伺服器應用程式（處理錄製的動作）的裝置的 IP 位址 |
| `TargetDeviceName` | string | 套用錄製動作之裝置的完整功能變數名稱 (FQDN)  |
| `TargetAccountDisplayName` | string | 套用錄製的動作所套用之帳戶的顯示名稱 |
| `Location` | string | 與事件關聯的城市、國家或其他地理位置 |
| `Isp` | string | 網際網路服務提供者 (與端點 IP 位址相關聯的 ISP)  |
| `ReportId` | long | 事件的唯一識別碼 |
| `AdditionalFields` | string | 實體或事件的其他資訊 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [搜捕裝置、電子郵件、應用程式和身分識別](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
