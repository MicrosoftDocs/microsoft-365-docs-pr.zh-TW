---
title: 從 Microsoft Defender for Endpoint 遷移高級搜尋查詢
description: 瞭解如何調整 Microsoft defender for Endpoint 查詢，以便在 Microsoft 365 defender 中使用。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、Microsoft 365 defender、microsoft 365、m365、microsoft defender for 端點、搜尋、查詢、遙測、自訂偵測、架構、kusto、對應
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ba6f84f9f08d0635dab6ac65eaa697b8e0e73df7
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470685"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>從 Microsoft Defender for Endpoint 遷移高級搜尋查詢

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

從 Microsoft Defender for Endpoint 移動您的高級搜尋工作流程，以使用更多資料集主動搜尋威脅。 在 Microsoft 365 Defender 中，您可以存取其他 Microsoft 365 安全性解決方案中的資料，包括：

- 適用於端點的 Microsoft Defender
- 適用於 Office 365 的 Microsoft Defender
- Microsoft 雲端 App 安全性
- 適用於身分識別的 Microsoft Defender

>[!NOTE]
>大多數 Microsoft defender for Endpoint 客戶可以[使用 Microsoft 365 Defender，但不含其他授權](prerequisites.md#licensing-requirements)。 若要開始從 Endpoint for Endpoint 轉換您的高級搜尋工作流程，請[開啟 Microsoft 365 defender](m365d-enable.md)。

您可以轉換，而不會影響現有的端點工作流程。 儲存的查詢會保持不變，而且自訂偵測規則會繼續執行並產生警示。 不過，Microsoft 365 Defender 會顯示這些功能。 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>僅限 Microsoft 365 Defender 中的架構表格
[Microsoft 365 的 Defender 高級搜尋架構](advanced-hunting-schema-tables.md)提供額外的資料表，其中包含各種 Microsoft 365 安全性解決方案的資料。 下表僅適用于 Microsoft 365 Defender：

| 表格名稱 | 描述 |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | 與警示相關聯的檔案、IP 位址、URLs、使用者或裝置 |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | microsoft defender for Endpoint、microsoft defender for Office 365、Microsoft Cloud App Security 和 microsoft defender for Identity 的警示，包括嚴重性資訊和威脅類別  |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | 附加至電子郵件之檔案的相關資訊 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365 電子郵件事件，包括電子郵件傳遞和封鎖事件 |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Microsoft 365 將電子郵件傳遞至收件者信箱之後，進行傳遞後的安全性事件 |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | 有關電子郵件 URLs 的資訊 |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | 與執行 Active Directory (AD) 的內部部署網域控制站相關的事件。 此表格涵蓋網域控制站上的身分識別相關事件和系統事件範圍。 |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | 各來源的帳戶資訊，包括 Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Active Directory 和 Microsoft online services 上的驗證事件 |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | 使用 Active Directory 物件的查詢，例如使用者、群組、裝置和網域 |

>[!IMPORTANT]
> 使用只能在 Microsoft 365 Defender 中使用之架構表的查詢和自訂偵測只可在 Microsoft 365 Defender 中查看。

## <a name="map-devicealertevents-table"></a>Map DeviceAlertEvents 表格
`AlertInfo`和 `AlertEvidence` 表格會取代 `DeviceAlertEvents` Microsoft Defender for Endpoint 架構中的表格。 除了裝置警示的資料之外，這兩個表格也包含有關身分識別、應用程式及電子郵件警示的資料。

請使用下表來檢查資料 `DeviceAlertEvents` 行對應至 [表格] 中欄的方式 `AlertInfo` `AlertEvidence` 。

>[!TIP]
>除了下表中的欄以外，此表格還 `AlertEvidence` 包含許多其他的欄，可提供來自各種來源的更整體警示。 [查看所有 AlertEvidence 欄](advanced-hunting-alertevidence-table.md) 

| DeviceAlertEvents 欄 | 在 Microsoft 365 Defender 中尋找相同資料的位置 |
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
| `ReportId` | 此欄通常用在 Microsoft Defender for Endpoint 中，以尋找其他資料表中的相關記錄。 在 Microsoft 365 Defender 中，您可以直接從資料表取得相關資料 `AlertEvidence` 。 |
| `Table` | 此欄通常用於 Microsoft Defender for Endpoint 中其他資料表中的其他事件資訊。 在 Microsoft 365 Defender 中，您可以直接從資料表取得相關資料 `AlertEvidence` 。 |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>調整現有的 Microsoft Defender for Endpoint 查詢
Microsoft Defender for Endpoint 查詢會以-為單位運作，除非他們參考 `DeviceAlertEvents` 該表。 若要在 Microsoft 365 Defender 中使用這些查詢，請套用下列變更：

- 取代 `DeviceAlertEvents` `AlertInfo` 。
- 加入 `AlertInfo` 和上的 `AlertEvidence` 資料表， `AlertId` 以取得對等資料。

### <a name="original-query"></a>原始查詢
下列查詢會 `DeviceAlertEvents` 在 Microsoft Defender For Endpoint 中使用，以取得涉及 _powershell.exe_ 的警示：

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>修改的查詢
下列查詢已調整為用於 Microsoft 365 Defender。 `DeviceAlertEvents`它會加入 `AlertEvidence` 並檢查該表中的檔案名，而不是直接檢查檔案名。

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>遷移自訂偵測規則

當 Microsoft defender for Endpoint rules 在 Microsoft 365 defender 上編輯時，如果結果查詢只會查看裝置資料表，便會繼續像之前一樣運作。 

例如，自訂偵測規則所產生的警示，只要查詢裝置資料表，就會繼續傳遞到您的 SIEM 並產生電子郵件通知，視您在 Microsoft Defender for Endpoint 中的設定方式而定。 在 Defender for Endpoint 中的任何現有抑制規則也會繼續套用。

一旦您編輯了某一 defender for Endpoint 規則，讓它查詢身分識別和電子郵件表格（僅 Microsoft 365 defender 中提供），該規則就會自動移至 Microsoft 365 Defender。 

由遷移的規則所產生的警示：

- 在端點入口網站 (Microsoft Defender 資訊安全中心中不再顯示) 
- 停止傳遞到您的 SIEM 或產生電子郵件通知。 若要解決此變更，請透過 Microsoft 365 Defender 設定通知，以取得提醒。 您可以使用[Microsoft 365 Defender API](api-incident.md)接收客戶偵測警示或相關事件的通知。
- 不會由 Microsoft Defender for Endpoint 抑制規則抑制。 若要防止針對某些使用者、裝置或信箱產生警示，請修改對應的查詢以明確排除那些實體。

如果您以這種方式編輯規則，則在套用此類變更之前，系統會提示您進行確認。

由 Microsoft 365 Defender 入口網站中的自訂偵測規則所產生的新警示會顯示在警示頁面中，提供下列資訊：

- 提醒標題和描述 
- 受影響資產
- 回應提醒所採取的動作
- 觸發警示的查詢結果 
- 自訂偵測規則的資訊 
 
> [!div class="mx-imgBorder"]
> ![新警示頁面的圖像](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a>寫入不含 DeviceAlertEvents 的查詢

在 Microsoft 365 的 Defender 架構中， `AlertInfo` `AlertEvidence` 會提供和資料表，以容納不同來源的警示附帶的資訊集。 

若要取得您用來從 `DeviceAlertEvents` Microsoft Defender For Endpoint 架構中的表格取得的相同警示資訊，請篩選 `AlertInfo` 該表， `ServiceSource` 然後使用資料表加入每個唯一的 ID `AlertEvidence` ，以提供詳細的事件及實體資訊。 

請參閱下列範例查詢：

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

此查詢所產生的資料行數多於 `DeviceAlertEvents` Microsoft Defender For Endpoint 架構中的資料行數。 若要保持可管理的結果，請使用 `project` 僅取得您感興趣的欄。 在調查偵測到 PowerShell 活動時，可能會對下列專案欄感興趣的範例：

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

如果您想要針對警示中的特定實體進行篩選，您可以在中指定實體類型 `EntityType` 和要篩選的值來執行此動作。 下列範例會尋找特定的 IP 位址：

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a>另請參閱
- [開啟 Microsoft 365 Defender](advanced-hunting-query-language.md)
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [Microsoft Defender for Endpoint 中的高級搜尋](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)