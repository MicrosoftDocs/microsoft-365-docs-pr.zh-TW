---
title: Microsoft 365 資料永久性
ms.author: josephd
author: JoeDavies-MSFT
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
f1.keywords:
- NOCSH
description: 瞭解 Microsoft 365 如何保留可探索表單中的資料，以解決法規遵從性、內部管理需求和訴訟風險。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c070eea4498aca89d7cdb8fea233d9b9596491a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688456"
---
# <a name="immutability-in-microsoft-365"></a>Microsoft 365 中的不可變性

法規遵從性、內部管理需求或訴訟風險，都需要組織保留可探索表單中的電子郵件和相關資料。 系統中的所有資料都必須可探索，而且無法銷毀或變更。 這項業界標準的術語是「不永久性」。

傳統的可變性方法通常是透過將電子郵件訊息移至個別的唯讀儲存位置而運作。 雖然這類系統將保留信箱專案以供探索，但通常會從一般的日常工作流程中移除保留的專案，以影響使用者經驗。 針對 IT 專業人員，這種不間斷的做法需要部署及不斷維護個別的伺服器和儲存基礎結構。 探索是以郵件系統外部的工具來執行，並包含相關聯的部署和維護成本。

透過 Microsoft 365 及其服務中封存的就地保留和保留原則功能，您可以保留及保留許多類別的內送、內部和外送的資料。 這包括：

- 輸入和輸出的電子郵件通訊
- 包含在電子郵件表單或共用的線上檔中的書和記錄
- 會議邀請
- 傳真
- 立即訊息
- 線上會議期間共用的檔
- 語音 郵件

此外，Microsoft 已開發附加元件功能，以允許從其他來源中封存 [資料](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc) ，透過與協力廠商資料捕獲和管理解決方案整合。 匯入協力廠商資料後，您可以將 Microsoft 365 規範功能套用至資料，包括：

- [訴訟暫止](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)
- [In-Place eDiscovery 和保留](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)
- [合規性搜尋](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)
- [就地封存](https://docs.microsoft.com/microsoft-365/compliance/enable-archive-mailboxes)
- [信箱稽核](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing)
- [保留原則](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

例如，當信箱處於訴訟暫止狀態時，會保留協力廠商資料。 您可以使用 In-Place eDiscovery 或符合性搜尋來搜尋協力廠商資料。 或者，您可以將封存和保留原則套用至協力廠商資料，就像您可以使用 Microsoft 資料一樣。 在 Microsoft 365 中封存協力廠商資料可協助您的組織遵守政府和法規原則。

Microsoft 365 中的封存可讓證券和 Exchange 傭金 (SEC) 規則17a-4 相容的儲存體。 Microsoft 365 會使用就地保留原則和保留原則（包括保留鎖定），保留以不可重寫、不可讀寫格式收集之所有資料的永久檔。

特別是：

- 使用以上所述保留原則儲存的所有記錄會保留在一般使用者 purview 的專用儲存體區域中。 只有授權的使用者可以存取和搜尋這些記錄，但無法變更或清除這些記錄。
- 每個專案的中繼資料包含用於計算保留期間的時間戳記。 當接收或建立新的專案，且無法從中繼資料中修改或移除時，會套用時間戳記。
- Microsoft 365 中的封存可讓使用者將不同的保留原則和保留動作組合在一起，以建立更精細的保留原則。 這些原則會定義保留專案的類型或位置，以及保留期間。
- 保留鎖定功能可讓使用者選擇是否要將原則設為限制性原則。 限制性原則可防止任何人能夠移除、停用或變更保留原則。 這表示一旦啟用保留鎖定後，就無法停用，而且在保留期間內，保留原則所收集的現有保管人中的任何資料可能會覆寫、修改、清除或刪除。 此外，保留鎖定設定的保留期間可能不會縮短或減少。 不過，您可能會因為合法的需求繼續保留所述的儲存資料，因此可能會加長。 保留鎖定可確保沒有任何人（甚至是系統管理員或具有特定控制存取權的人員）可以變更設定或覆寫或清除已儲存的資料，並將 Microsoft 365 中的封存，與 SEC Rule 17a-4 的2003版本中所述的指導方針結合在一起。

若要瞭解 Microsoft 365 如何協助您達成法規義務（特別是與規則17a-4 規定相關），請參閱涵蓋 Exchange Online 封存、SharePoint 線上、商務 OneDrive 商務及商務用 Skype 的 [白皮書](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/2015/11/Microsoft-EOA-White-Paper.pdf) 。 這份白皮書也針對 Microsoft 365 封存功能和功能提供深入分析，針對每個需求低於 SEC Rule 17a-4，並向客戶示範 Microsoft 365 封存可如何讓他們符合這些需求。
