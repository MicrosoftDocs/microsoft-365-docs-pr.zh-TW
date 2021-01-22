---
title: 進位搜尋架構中的 IdentityLogonEvents 資料表
description: 瞭解 Active Directory 在進一步搜尋架構的 IdentityLogonEvents 資料表中記錄的驗證事件
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、表格、欄、資料類型、描述、IdentityLogonEvents、Azure AD、Active Directory、Azure ATP、身分識別
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
ms.openlocfilehash: 1df1295b3386b94e3737c53ac8226c719c8bfa08
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929919"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

進位搜尋架構中的表格包含由 Microsoft Defender 針對 Microsoft Cloud App Security 所取得之 Microsoft 線上服務所取得之身分識別與驗證活動所拍攝之內部部署 Active Directory 所進行之 `IdentityLogonEvents` 驗證活動的資訊。 [](advanced-hunting-overview.md) 使用這個參考來建立從此表格取回之資訊的查詢。

>[!TIP]
> 有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參照。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

>[!NOTE]
>下表涵蓋 Azure Active Directory (AD) 由雲端 App 安全性所追蹤的登入活動，以及使用 ActiveSync 和其他舊版通訊協定所追蹤的特別互動式登入和驗證活動。 您可以在 Azure AD 稽核記錄中查看此表格中未提供的非互動標誌。 [深入瞭解將雲端 App 安全性與 Microsoft 365 連接](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。

| 欄名稱 | 資料類型 | 描述 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 事件記錄的日期和時間 |
| `ActionType` | string | 觸發事件的活動類型。 請參閱入口 [網站內架構參考以](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 進一步查看詳細資料 |
| `LogonType` | string | 登入會話的類型，特別是：<br><br> - **互動** - 使用者會使用本機鍵盤和螢幕與電腦進行實際互動<br><br> - **遠端互動式 (RDP)** 標誌 - 使用者會使用遠端桌面、終端機服務、遠端協助或其他 RDP 用戶端，與電腦進行遠端互動<br><br> - **網路** - 當使用 PsExec 存取電腦時，或當電腦上的共用資源 ，例如印表機和共用資料夾存取時初始化的會話<br><br> - **批次** - 由排程任務啟動的會話<br><br> - **服務** - 服務啟動時所啟動的會話 |
| `Application` | string | 執行錄製動作的應用程式 |
| `Protocol` | string | 已使用網路通訊協定 |
| `FailureReason` | string | 說明錄製動作失敗原因的資訊 |
| `AccountName` | string | 帳戶的使用者名稱 |
| `AccountDomain` | string | 帳戶的網域 |
| `AccountUpn` | string | 帳戶 (UPN) 使用者主體名稱 |
| `AccountSid` | string | 帳戶 (安全性) SID 識別碼 |
| `AccountObjectId` | string | Azure AD 中帳戶的唯一識別碼 |
| `AccountDisplayName` | string | 顯示在通訊錄中的帳戶使用者名稱。 通常是指定或名字、中間名、姓氏或名字的組合。 |
| `DeviceName` | string | 裝置 FQDN (完整) 功能變數名稱 |
| `DeviceType` | string | 裝置類型 |
| `OSPlatform` | string | 電腦上執行的作業系統平台。 這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。 |
| `IPAddress` | 字串 | 指派給端點的 IP 位址，用於相關網路通訊期間 |
| `DestinationDeviceName` | string | 執行處理錄製動作之伺服器應用程式之裝置的名稱 |
| `DestinationIPAddress` | string | 執行處理錄製動作之伺服器應用程式的裝置 IP 位址 |
| `TargetDeviceName` | string | 已記錄動作 (之) 之裝置之 FQDN 中完整功能變數名稱 |
| `TargetAccountDisplayName` | string | 顯示所記錄動作所適用于之帳戶的名稱 |
| `Location` | string | 與活動相關的城市、國家/地區或其他地理位置 |
| `Isp` | string | 與端點 IP 位址 (ISP) 網際網路服務提供者 |
| `ReportId` | long | 事件的唯一識別碼 |
| `AdditionalFields` | string | 實體或事件的其他相關資訊 |

## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解查詢語言](advanced-hunting-query-language.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
