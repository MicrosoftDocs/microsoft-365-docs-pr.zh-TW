---
title: Microsoft 365 稽核解決方案
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- m365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: 了解如何稽核 Microsoft 365 組織中使用者和管理員的活動。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d4a753a640b98125bc6ad02bd6043f28336e29b7
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256756"
---
# <a name="auditing-solutions-in-microsoft-365"></a>Microsoft 365 中的稽核解決方案

Microsoft 365 稽核解決方案提供了整合式解決方案，可協助組織有效地回應安全性事件、鑑識調查、內部調查和合規性義務。 在數十個 Microsoft 365 服務和解決方案中執行的數千個使用者和管理作業被擷取、記錄並保留在組織的整合稽核記錄中。 這些事件的稽核記錄可由組織中的安全性操作員、IT 管理員、內部風險小組以及合規性和法律調查人員進行搜尋。 此功能提供了對跨 Microsoft 365 組織執行的活動的可見度。

## <a name="microsoft-365-auditing-solutions"></a>Microsoft 365 稽核解決方案

Microsoft 365 提供兩種稽核解決方案：基本稽核和進階稽核。

![基本稽核和進階稽核的重要功能](..\media\AuditingSolutionsComparison.png)

### <a name="basic-audit"></a>基本稽核

基本稽核提供了記錄和搜尋已稽核活動的功能，並協助您的鑑識、IT、合規性和法律調查。

- **預設啟用**。 根據預設，所有具有相應訂閱的組織都會啟用基本稽核。 這意味著已稽核活動的記錄將被擷取和可搜尋。 唯一需要的設定是指派存取稽核記錄搜尋工具 (和相應的 cmdlet) 所需的授權，並確定為使用者指派了進階稽核功能的正確權限。
- **數千個可搜尋的稽核事件**。 您可以搜尋範圍廣泛、發生在貴組織中的大多數 Microsoft 365 服務中的已稽核活動。 有關您可以搜尋的活動之部分清單，請參閱[已稽核活動](search-the-audit-log-in-security-and-compliance.md#audited-activities)。 有關支援已稽核活動的服務和功能的清單，請參閱[稽核記錄的記錄類型](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)。
- **Microsoft 365 合規性中心中的稽核搜尋工具**。 使用 Microsoft 365 合規性中心中的稽核記錄搜尋工具搜尋稽核記錄。 您可以搜尋特定活動、特定使用者執行的活動以及日期範圍內發生的活動。 以下是合規中心稽核搜尋工具的螢幕擷取畫面。

   ![Microsoft 365 合規性中心中的稽核記錄搜尋工具](../media/AuditLogSearchToolMCC.png)

- **Search-UnifiedAuditLog cmdlet**。 您還可以在 Exchange Online PowerShell (搜尋工具的基礎 cmdlet) 中使用 **Search-UnifiedAuditLog** cmdlet 來搜尋稽核事件或在指令碼中使用。 如需詳細資訊，請參閱：

  - [Search-UnifiedAuditLog cmdlet 參考資料](/powershell/module/exchange/search-unifiedauditlog)
  - [使用 PowerShell 指令碼來搜尋稽核記錄](audit-log-search-script.md)

- **將稽核記錄匯出至 CSV 檔案**。 在合規性中心執行稽核記錄搜尋工具後，可以將搜尋返回的稽核記錄匯出至 CSV 檔案。 這可讓您對不同的稽核記錄屬性使用 Microsoft Excel 排序和篩選。 您還可以使用 Excel Power Query 轉換功能將 AuditData JSON 物件中的每個屬性分割至其資料行。 這可讓您有效地檢視和比較不同事件的類似資料。 如需詳細資訊，請參閱[匯出、設定及檢視稽核記錄檔的記錄](export-view-audit-log-records.md)。

- **透過 Office 365 管理活動 API 存取稽核記錄**。 存取和擷取稽核記錄的第三種方法是使用 Office 365 管理活動 API。 這使得組織保留稽核資料的時間長於預設的 90 天，並可讓它們將稽核資料匯入至 SIEM 解決方案。 如需詳細資訊，請參閱 [Office 365 管理活動 API 參考](/office/office-365-management-api/office-365-management-activity-api-reference)。

- **90 天稽核記錄保留**。 當使用者或系統管理員執行稽核的活動時，稽核記錄會隨即產生，並儲存在您組織的稽核記錄中。 在基本稽核中記錄將保留 90 天，這意味著您可以搜尋過去三個月內發生的活動。

### <a name="advanced-audit"></a>進階稽核

進階稽核提升了基本稽核功能，提供稽核記錄保留原則、更長的稽核記錄保留期、高價值重要事件以及對 Office 365 管理活動 API 的更高頻寬存取。

- **稽核記錄保留原則**。 您可以建立自訂稽核記錄保留原則，以將稽核記錄保留更長的時間，上限為一年 (對於具有所需附加元件授權的使用者，上限為 10 年)。 您可以建立原則，保留根據發生稽核活動的服務、特定稽核活動或執行稽核活動的使用者之稽核記錄。

- **稽核記錄的較長保留期**。 根據預設，Exchange、SharePoint 和 Azure Active Directory 稽核記錄保留一年。 根據預設，所有其他活動的稽核記錄保留 90 天，或者您可以使用稽核記錄保留原則設定更長的保留期。

- **高價值的重要事件**。 重要事件的稽核記錄可提供對事件的可見度 (例如存取郵件項目的時間、回覆和轉寄郵件項目的時間，或使用者在 Exchange Online 和 SharePoint Online 中搜尋的時間和內容)，協助貴組織進行鑑識和合規性調查。 這些重要事件可協助您調查可能的破壞，並判斷危害的範圍。

- **Office 365 管理活動 API 的更高頻寬**。 進階稽核透過 Office 365 管理活動 API 為組織提供了更多的頻寬以存取稽核記錄。 儘管所有組織 (具有基本稽核或進階稽核) 最初配置的基準為每分鐘 2000 個要求，但此限制將根據組織的基座數及其授權訂閱動態增加。 這導致使用進階稽核的組織取得的頻寬是使用基本稽核組織的兩倍。

有關進階稽核功能的詳細資訊，請參閱 [Microsoft 365 中的進階稽核](advanced-audit.md)。

## <a name="comparison-of-key-capabilities"></a>主要功能比較

以下表格比較了基本稽核和進階稽核中提供的主要功能。 進階稽核中包含所有基本稽核功能。

|功能|基本稽核|進階稽核|
|:------|:-------------|:-------------|
|預設啟用|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)|
|數千個可搜尋的稽核事件|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)|
|Microsoft 365 合規性中心中的稽核搜尋工具|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)|
|Search-UnifiedAuditLog cmdlet|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)|
|將稽核記錄匯出至 CSV 檔案|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)|
|透過 Office 365 管理活動 API 存取稽核記錄 <sup>1</sup>|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)</sup>|
|90 天稽核記錄保留|![支援](../media/check-mark.png)|![支援](../media/check-mark.png)|
|1 年稽核記錄保留||![支援](../media/check-mark.png)|
|10 年稽核記錄保留 <sup>2</sup>||![支援](../media/check-mark.png)|
|稽核記錄保留原則||![支援](../media/check-mark.png)|
|高值，重要事件||![支援](../media/check-mark.png)|
||||
> [!NOTE]
> <sup>1</sup> 進階稽核包括對 Office 365 管理活動 API 的更高頻寬存取，提供對稽核資料的更快存取。<br/><sup>2</sup> 除了進階稽核所需的權限 (在下一節中介紹) 之外，還必須為使用者指派 10 年稽核記錄保留附加元件授權，以將其稽核記錄保留 10 年。

## <a name="licensing-requirements"></a>授權需求

以下各節確定了基本稽核和進階稽核的授權需求。 進階稽核包含基本稽核功能。

### <a name="basic-audit"></a>基本稽核

- Microsoft 365 企業版 E3 訂閱
- Microsoft 365 商務進階版
- Microsoft 365 教育版 A3 訂閱
- Microsoft 365 政府版 G3 訂閱
- Microsoft 365 政府版 G1 訂閱
- Office 365 企業版 E3 訂閲
- Office 365 企業版 E1 訂閲
- Office 365 教育版 A1 訂閱
- Office 365 教育版 A3 訂閲

### <a name="advanced-audit"></a>進階稽核

- Microsoft 365 企業版 E5 訂閱
- Microsoft 365 企業版 E3 訂閱 + Microsoft 365 E5 合規性附加元件
- Microsoft 365 企業版 E3 訂閱 + Microsoft 365 E5 電子文件探索和稽核附加元件
- Microsoft 365 教育版 A5 訂閱
- Microsoft 365 教育版 A3 訂閱 + Microsoft 365 A5 合規性附加元件
- Microsoft 365 教育版 E3 訂閱 + Microsoft 365 A5 電子文件探索和稽核附加元件
- Microsoft 365 政府版 G5 訂閱
- Microsoft 365 政府版 G5 訂閱 + Microsoft 365 G5 合規性附加元件
- Microsoft 365 政府版 G5 訂閱 + Microsoft 365 G5 電子文件探索和稽核附加元件
- Office 365 企業版 E5 訂閱
- Office 365 教育版 A5 訂閲
- Office 365 企業版 E3 訂閱 + Office 365 進階合規性附加元件 (不再適用於新訂閱)

## <a name="set-up-microsoft-365-auditing-solutions"></a>設定 Microsoft 365 稽核解決方案

要開始使用 Microsoft 365 中的稽核解決方案，請參閱以下設定指引。

### <a name="set-up-basic-audit"></a>設定基本稽核。

第一步是設定基本稽核，然後開始執行稽核記錄搜尋。

![設定基本稽核的工作流程](../media/BasicAuditingWorkflow.png)

1. 請驗證貴組織是否具有支援基本稽核的訂閱，以及是否具有支援進階稽核的訂閱 (若適用)。

2. 將 Exchange Online 中的權限指派給貴組織中將使用 Microsoft 365 合規性中心稽核記錄搜尋工具或 **Search-UnifiedAuditLog** cmdlet 的人員。 特別是必須在 Exchange Online 中為使用者指派 [僅供檢視稽核記錄] 或 [稽核記錄角色]。

3. 搜尋稽核記錄。完成步驟 1 和步驟 2 後，貴組織中的使用者可以使用稽核記錄搜尋工具 (或相應的 cmdlet) 搜尋已稽核活動。

如需詳細指示，請參閱[設定基本稽核](set-up-basic-audit.md)。

### <a name="set-up-advanced-audit"></a>設定進階稽核

如果貴組織具有支援進階稽核的訂閱，請執行以下步驟以設定和使用進階稽核中的其他功能。

![設定進階稽核的工作流程](../media/AdvancedAuditWorkflow.png)

1. 為使用者設置進階稽核。 此步驟包括以下工作：

   - 驗證是否為使用者指派了進階稽核的適當權限或附加元件權限。
  
   - 必須為這些使用者啟用進階稽核應用程式/服務方案。
  
   - 啟用重要事件的稽核，然後為這些使用者啟用進階稽核應用程式/服務方案。

2. 允許使用者在 Exchange Online 和 SharePoint Online 中執行搜尋時記錄重要事件。

3. 設定稽核記錄保留原則。除了保留 Exchange、SharePoint 和 Azure AD 稽核記錄一年的預設原則之外，您還可以建立其他稽核記錄保留原則，以符合貴組織的安全性作業、IT 和合規性小組的需求。

4. 進行鑑識調查時搜尋重要事件和其他活動。在完成步驟 1 和步驟 2 後，您可以搜尋重要事件和對遭入侵帳戶的鑑識調查，以及其他類型安全性或合規性調查期間的其他活動稽核記錄。

如需詳細指示，請參閱[設定進階稽核](set-up-advanced-audit.md)。

## <a name="training"></a>訓練

訓練安全性作業小組、IT 管理員和合規性調查人員小組基礎稽核和進階稽核的基礎内容，可協助貴組織更快開始使用稽核來進行調查。 Microsoft 365 提供以下資源以協助組織中的這些使用者開始使用稽核：[描述 Microsoft 365 中的電子文件探索及稽核功能](/learn/modules/describe-ediscovery-capabilities-of-microsoft-365)。
