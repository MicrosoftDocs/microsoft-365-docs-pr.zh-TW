---
title: 從 Microsoft Defender for Endpoint 進行進位搜尋查詢的遷移
description: 瞭解如何調整您的 Microsoft Defender 端點查詢，以便您可以在 Microsoft 365 Defender 中使用這些查詢
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、microsoft defender atp、mdatp、搜尋、查詢、遙測、自訂偵測、架構、kusto、microsoft 365、地圖
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 08bdd1e22040166bb3becac32580a185c74f34a0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932298"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>從 Microsoft Defender for Endpoint 進行進位搜尋查詢的遷移

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：
- Microsoft 365 Defender

將進一步搜尋工作流程從 Microsoft Defender for Endpoint 移至使用一組更廣泛的資料主動搜尋威脅。 在 Microsoft 365 Defender 中，您可以存取其他 Microsoft 365 安全性解決方案的資料，包括：

- 適用於端點的 Microsoft Defender
- 適用於 Office 365 的 Microsoft Defender
- Microsoft Cloud App Security
- 適用於身分識別的 Microsoft Defender

>[!NOTE]
>大部分的 Microsoft Defender for Endpoint 客戶 [可以使用 Microsoft 365 Defender，不需要其他授權](prerequisites.md#licensing-requirements)。 若要從 Defender for Endpoint 開始轉換進位搜尋工作流程，[請開啟 Microsoft 365 Defender。](mtp-enable.md)

您可以轉換而不影響到現有的端點工作流程 Defender。 已儲存的查詢會保持不變，而自訂偵測規則會繼續執行並產生警示。 不過，他們會在 Microsoft 365 Defender 中顯示。 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>僅適用于 Microsoft 365 Defender 的架構資料表
[Microsoft 365 Defender 進位搜尋](advanced-hunting-schema-tables.md)架構提供包含來自各種 Microsoft 365 安全性解決方案之資料的其他資料表。 下表僅適用于 Microsoft 365 Defender：

| 表格名稱 | 描述 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | 與警示相關聯的檔案、IP 位址、URL、使用者或裝置 |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | 來自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App 安全性及 Microsoft Defender 的身分識別通知，包括嚴重性資訊和威脅類別  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | 雲端應用程式和服務中的檔案相關活動 |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | 附加至電子郵件之檔案的資訊 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365 電子郵件事件，包括電子郵件傳遞和封鎖事件 |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Microsoft 365 將電子郵件送達收件者的信箱之後，在傳送後發生的安全性事件 |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | 電子郵件 URL 相關資訊 |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | 涉及內部部署網域控制站執行 Active Directory (AD) 。 下表涵蓋網域控制站上的一系列身分識別相關事件及系統事件。 |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | 各種來源的帳戶資訊，包括 Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Active Directory 和 Microsoft 線上服務上的驗證事件 |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Active Directory 物件的查詢，例如使用者、群組、裝置和網域 |

## <a name="map-devicealertevents-table"></a>Map DeviceAlertEvents 資料表
And `AlertInfo` `AlertEvidence` table 會取代 `DeviceAlertEvents` Microsoft Defender for Endpoint 架構中的資料表。 除了裝置警示資料，這兩個數據表包含身分驗證、應用程式和電子郵件警示的資料。

使用下表檢查欄如何 `DeviceAlertEvents` 與資料表中的資料行 `AlertInfo` `AlertEvidence` 進行關聯。

>[!TIP]
>除了下表的欄外，表格還包含許多其他欄，可提供更多來自各種來源 `AlertEvidence` 之通知的全貌。 [查看所有 AlertEvidence 欄](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents 欄 | Microsoft 365 Defender 的相同資料位置 |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` 和  `AlertEvidence` 表格 |
| `Timestamp` | `AlertInfo` 和  `AlertEvidence` 表格 |
| `DeviceId` | `AlertEvidence` 表 |
| `DeviceName` | `AlertEvidence` 表 |
| `Severity` | `AlertInfo` 表 |
| `Category` | `AlertInfo` 表 |
| `Title` | `AlertInfo` 表 |
| `FileName` | `AlertEvidence` 表 |
| `SHA1` | `AlertEvidence` 表 |
| `RemoteUrl` | `AlertEvidence` 表 |
| `RemoteIP` | `AlertEvidence` 表 |
| `AttackTechniques` | `AlertInfo` 表 |
| `ReportId` | 此欄通常是在 Microsoft Defender for Endpoint 中用來尋找其他資料表中的相關記錄。 在 Microsoft 365 Defender 中，您可以直接從資料表取得 `AlertEvidence` 相關的資料。 |
| `Table` | 此欄通常用於 Microsoft Defender for Endpoint，用於其他資料表中的其他事件資訊。 在 Microsoft 365 Defender 中，您可以直接從資料表取得 `AlertEvidence` 相關的資料。 |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>調整現有的 Microsoft Defender 端點查詢
除非參照資料表，否則 Microsoft Defender 的端點查詢將能如新 `DeviceAlertEvents` 工作。 若要在 Microsoft 365 Defender 中使用這些查詢，請進行以下變更：

- 取代 `DeviceAlertEvents` 為 `AlertInfo` 。
- 聯 `AlertInfo` 聯資料 `AlertEvidence` 表和資料表 `AlertId` 以取得相等的資料。

### <a name="original-query"></a>原始查詢
下列查詢會 `DeviceAlertEvents` 使用 Microsoft Defender for Endpoint 取得與下列powershell.exe：

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>已修改查詢
下列查詢已調整為在 Microsoft 365 Defender 中使用。 它無需直接檢查檔案名，而會聯入並檢查 `DeviceAlertEvents` `AlertEvidence` 資料表中的檔案名。

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>相關主題
- [開啟 Microsoft 365 Defender](advanced-hunting-query-language.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [Microsoft Defender for Endpoint 中的進位搜尋](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)