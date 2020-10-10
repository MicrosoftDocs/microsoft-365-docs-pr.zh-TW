---
title: 從 Microsoft Defender ATP 遷移高級搜尋查詢
description: 瞭解如何調整您的 Microsoft Defender ATP 查詢，讓您可以在 Microsoft 威脅防護中使用它們
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，microsoft defender atp，mdatp，search，查詢，遙測，自訂偵測，schema，kusto，microsoft 365，對應
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b1738180e192baafa60f76fada1e433319922b91
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412679"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a>從 Microsoft Defender ATP 遷移高級搜尋查詢

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：****
- Microsoft 威脅防護

從 Microsoft Defender ATP 移動您的高級搜尋工作流程，以主動使用更多資料集來尋找威脅。 在 Microsoft 威脅防護中，您可以存取其他 Microsoft 365 安全性解決方案中的資料，包括：

- Microsoft Defender 進階威脅防護
- Office 365 進階威脅防護
- Microsoft Cloud App Security
- Azure 進階威脅防護

>[!NOTE]
>大部分的 Microsoft Defender ATP 客戶可以 [使用不含其他授權的 Microsoft 威脅防護](prerequisites.md#licensing-requirements)。 若要從 Microsoft Defender ATP 開始轉換您的高級搜尋工作流程，請 [開啟 Microsoft 威脅防護](mtp-enable.md)。

您可以轉換，而不會影響現有的 Microsoft Defender ATP 工作流程。 儲存的查詢會保持不變，而且自訂偵測規則會繼續執行並產生警示。 不過，他們會在 Microsoft 威脅防護中看到。 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a>僅限 Microsoft 威脅防護中的架構表格
[Microsoft 威脅防護高級搜尋架構](advanced-hunting-schema-tables.md)提供額外的資料表，其中包含各種 Microsoft 365 安全性解決方案中的資料。 下清單格僅適用于 Microsoft 威脅防護：

| 表格名稱 | 描述 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | 與警示相關聯的檔案、IP 位址、URLs、使用者或裝置 |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | 來自 Microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的警示，包括嚴重性資訊和威脅類別  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | 雲端應用程式和服務中的檔相關活動 |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | 附加至電子郵件之檔案的相關資訊 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365 電子郵件事件，包括電子郵件傳遞和封鎖事件 |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Microsoft 365 將電子郵件傳遞至收件者信箱之後，進行傳遞後的安全性事件 |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | 有關電子郵件 URLs 的資訊 |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | 與執行 Active Directory (AD) 的內部部署網域控制站相關的事件。 此表格涵蓋網域控制站上的身分識別相關事件和系統事件範圍。 |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | 各來源的帳戶資訊，包括 Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Active Directory 和 Microsoft online services 上的驗證事件 |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | 使用 Active Directory 物件的查詢，例如使用者、群組、裝置和網域 |

## <a name="map-devicealertevents-table"></a>Map DeviceAlertEvents 表格
`AlertInfo`和 `AlertEvidence` tables 會取代 `DeviceAlertEvents` Microsoft Defender ATP 架構中的表格。 除了裝置警示的資料之外，這兩個表格也包含有關身分識別、應用程式及電子郵件警示的資料。

請使用下表來檢查資料 `DeviceAlertEvents` 行對應至 [表格] 中欄的方式 `AlertInfo` `AlertEvidence` 。

>[!TIP]
>除了下表所列的資料行以外，此 `AlertEvidence` 表格還包含許多其他的欄，可提供來自各種來源之更整體的警示。 [查看所有 AlertEvidence 欄](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents 欄 | 在 Microsoft 威脅防護中尋找相同資料的位置 |
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
| `ReportId` | 此欄通常用在 Microsoft Defender ATP 中，以尋找其他資料表中的相關記錄。 在 Microsoft 威脅防護中，您可以直接從資料表取得相關資料 `AlertEvidence` 。 |
| `Table` | 此欄通常用於 Microsoft Defender ATP 中其他資料表中的其他事件資訊。 在 Microsoft 威脅防護中，您可以直接從資料表取得相關資料 `AlertEvidence` 。 |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a>調整現有的 Microsoft Defender ATP 查詢
除非參考該表，否則 Microsoft Defender ATP 查詢將會以原樣運作 `DeviceAlertEvents` 。 若要在 Microsoft 威脅防護中使用這些查詢，請套用下列變更：

- 取代 `DeviceAlertEvents` `AlertInfo` 。
- 加入 `AlertInfo` 和上的 `AlertEvidence` 資料表， `AlertId` 以取得對等資料。

### <a name="original-query"></a>原始查詢
下列查詢會 `DeviceAlertEvents` 在 Microsoft DEFENDER ATP 中使用，以取得涉及 _powershell.exe_的警示：

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>修改的查詢
下列查詢已調整為用於 Microsoft 威脅防護。 `DeviceAlertEvents`它會加入 `AlertEvidence` 並檢查該表中的檔案名，而不是直接檢查檔案名。

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>相關主題
- [開啟 Microsoft 威脅防護](advanced-hunting-query-language.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [Microsoft Defender ATP 中的高級搜尋](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)