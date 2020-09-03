---
title: Microsoft 365 eDiscovery 和搜尋功能概述
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Microsoft 365 中的 eDiscovery 功能及其他搜尋功能的概覽，以供審計使用和透明性。
ms.openlocfilehash: ea7b221ab8fe2ff41d089bb344d2dce58002d0f5
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331856"
---
# <a name="microsoft-365-ediscovery-and-search-features-overview"></a>Microsoft 365 eDiscovery 和搜尋功能概述 

## <a name="ediscovery"></a>電子文件探索

EDiscovery 功能為系統管理員、合規性監察官及其他經授權的使用者提供單一位置，以進行 Microsoft 365 使用者活動的全面調查。 具有適當許可權的安全性監察官執行搜尋，並保留內容的位置。 搜尋結果與您從內容搜尋取得的結果相同，但 eDiscovery 案例是針對任何已套用的保留而建立的。 電子檔探索搜尋的結果會為安全性加密，您可以使用 [高級 eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)來分析匯出的資料。

## <a name="content-search"></a>內容搜尋

「[內容搜尋](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)」是 ediscovery 搜尋工具，可提供比先前 eDiscovery 搜尋工具更好的縮放比例和效能功能。 您可以使用內容搜尋來搜尋信箱、公用資料夾、SharePoint 線上網站，以及商務位置 OneDrive。 內容搜尋支援大型搜尋。 您可以搜尋的信箱和網站數目沒有限制。 在同一時間執行的搜尋數目也沒有限制。 在您執行搜尋之後，會在 [搜尋] 頁面的 [詳細資料] 窗格中顯示內容來源數目及估計的搜尋結果數目。 您可以預覽結果，或將結果匯出至本機電腦。 如果您的組織有 Microsoft 365 E5 訂閱，您可以使用[microsoft 365 Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)的強大分析功能，[準備結果](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare)以進行分析。

## <a name="audit-log-search"></a>審核記錄搜尋

除了在 Microsoft 365 組織中追蹤變更之外，您還可以查看審核報告和匯出審計記錄檔。 一旦為 Microsoft 365 租使用者啟用審核，使用者和管理活動就會記錄在事件記錄檔中，並可供搜尋。 例如，您可以使用信箱審核記錄，追蹤信箱擁有者以外的使用者對信箱執行的動作。 合規性監察官可以針對特定使用者活動使用搜尋和篩選功能。 例如，若要識別已查看或下載特定檔的使用者，如果系統管理員已執行使用者管理活動，或在過去的90天內，查看租使用者設定中的變更。 搜尋結果包含使用者或系統管理員所執行之特定活動的重要鑒證資訊。 請參閱 [搜尋審核記錄](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 檔，以取得 Microsoft 365 中所記錄之使用者和管理活動的描述。

在發生30分鐘內，會在記錄中顯示 SharePoint 線上和商務 OneDrive 相關的事件。 Exchange Online 中的事件會出現在發生24小時內的審計記錄檔中。 在發生分鐘內可提供來自 Azure AD 的登入事件，而且來自 Azure AD 的其他目錄事件會在發生24小時內提供。 您可以在審計記錄搜尋結果中出口通風口，以進行進一步的分析。 匯出單一審核記錄搜尋中的最多50000個專案。 若要匯出此限制的更多專案，請縮短日期範圍或執行多個審核記錄搜尋。

下表詳細資料顯示于活動報告中的一些資訊。 請參閱 [審計記錄檔中的詳細](https://docs.microsoft.com/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log) 內容，以取得每個 Microsoft 365 工作負載所收集之屬性的詳細資訊。

| 屬性	 | 說明 |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| 日期 | 事件的日期和時間 |
| 使用者 | 執行動作的使用者 |
| ClientIP | 記錄活動時所使用之裝置的 IPv4 或 IPv6 位址。 |
| CreationTime | 當使用者執行活動時，在協調世界時 (UTC) 的日期和時間。 |
| EventSource | 識別發生的事件。 可能的值為 SharePoint 和 ObjectModel。 |
| ID | 報表專案的識別碼。 識別碼可唯一識別報表專案。 |
| 作業 | 使用者或活動的名稱，對應于此使用者活動顯示結果中選取的值。 |
| OrganizationId | 發生此事件之組織之 Microsoft 365 服務的 GUID。 |
| UserAgent | 瀏覽器所提供之使用者瀏覽器的相關資訊。 |
| UserId | 執行動作屬性) 中所指定之動作的使用者，而該 (會導致記錄記錄。 |
| UserType | 執行作業的使用者類型。 下列值表示使用者類型。 |
|  | 0表示一般使用者。 |
|  | 2表示您的 Microsoft 365 組織中的系統管理員。 |
|  | 3表示 Microsoft 資料中心系統管理員或資料中心系統帳戶。 |
| 工作負載 | 發生活動的 Microsoft 365 服務。 此屬性的可能值如下： |
|  | Exchange Online |
|  | SharePoint Online |
|  | 商務用 OneDrive |
|  | Azure Active Directory 報告 |

如需搜尋 Microsoft 365 審核記錄的詳細步驟，請參閱在 [安全性 & 規範中心搜尋審核記錄](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)檔。

## <a name="search-unified-audit-log"></a>搜尋整合的審計記錄

使用「審核記錄搜尋」功能來搜尋整合的審計記錄。 Microsoft 365 也提供使用遠端 PowerShell 搜尋此記錄的功能。 Exchange Online PowerShell 中的 [Search-UnifiedAuditLog Cmdlet](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/Search-UnifiedAuditLog?view=exchange-ps) 是用來搜尋整合的審計記錄檔，這些事件與 exchange online 中的使用者作業、SharePoint 線上、OneDrive for Business 及 Azure AD 相關。 

您可以搜尋指定日期範圍內的所有事件，也可以根據特定準則來篩選結果，例如特定的動作、執行動作的使用者或目標物件。 系統管理員最多可使用三個同時執行 Exchange Online PowerShell 會話，以分割大量的日期範圍搜尋。