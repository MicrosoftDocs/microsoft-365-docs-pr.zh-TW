---
title: Microsoft 365 Defender 的新功能
description: 列出 Microsoft 365 Defender 中的新功能
keywords: Microsoft 威脅防護的新增功能， ga， 一般可用， 功能， 可用， 新增
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8e66c734151e7476d7c54bd050891a1bffb17b3c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932019"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender 的新功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> 想要體驗 Microsoft 365 Defender 嗎？ 您可以在實驗室 [環境中進行評估，](https://aka.ms/mtp-trial-lab) 或在生產 [環境中執行試驗專案](https://aka.ms/m365d-pilotplaybook)。
>

下列功能一般 (Microsoft 365 Defender) GA 更新版本。

RSS 轉播：在此頁面更新時取得通知，方法如下：將下列 URL 複製並加入您的轉播閱讀程式：
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
> 想要體驗 Microsoft 365 Defender 嗎？ 您可以在實驗室 [環境中進行評估，](https://aka.ms/mtp-trial-lab) 或在生產 [環境中執行試驗專案](https://aka.ms/m365d-pilotplaybook)
>

## <a name="september-2020"></a>2020 年 9 月
- [IdentityDirectoryEvents 資料表](advanced-hunting-identitydirectoryevents-table.md) <br> 尋找涉及內部部署網域控制站執行 Active Directory (AD) 。 此 [進位搜尋](advanced-hunting-overview.md) 架構表格涵蓋網域控制站上的一系列身分識別相關事件及系統事件。
- [AssignedIPAddresses () 函數](advanced-hunting-assignedipaddresses-function.md) <br> 在進位搜尋查詢中使用此函數，以快速取得指派給裝置的最新 IP 位址，或特定時間的最新 IP 位址。

## <a name="july-2020"></a>2020 年 7 月
- [FileProfile () 函數](advanced-hunting-fileprofile-function.md) <br> 在進一步搜尋查詢中使用此函數，以完整的檔案資訊來豐富結果。
- [身分識別與應用程式資料表](advanced-hunting-schema-tables.md)<br> 使用進位搜尋架構中的[IdentityLogonEvents、IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)和[AppFileEvents](advanced-hunting-appfileevents-table.md)資料表，深入瞭解驗證事件、Active Directory 查詢及應用程式相關活動。 [](advanced-hunting-identitylogonevents-table.md)
- [開始搜補](advanced-hunting-go-hunt.md)<br> 快速從調查事件到檢查特定事件、使用者、裝置或進一步搜尋的其他實體類型。

## <a name="june-2020"></a>2020 年 6 月
- Twitter 進紙 <br> 直接在儀表板內取得最新的安全性研究、威脅情報、產品新聞等等。
- [EmailPostDeliveryEvents 架構資料表](advanced-hunting-emailpostdeliveryevents-table.md) <br> 在進一步搜尋查詢中納入對電子郵件訊息採取之傳遞後動作的資訊。
- [檢查進位搜尋中的記錄](advanced-hunting-query-results.md#drill-down-from-query-results) <br> 使用新的詳細資料面板快速檢查查詢結果中的記錄。

## <a name="may-2020"></a>2020 年 5 月
- [自訂偵測](custom-detections-overview.md) <br> 使用進位搜尋查詢來建立自訂偵測規則，自動監視並回應安全性事件和系統狀態。

## <a name="february-2020"></a>2020 年 2 月
- [事件](incidents-overview.md) <br> 確切知道攻擊開始在哪，以及其他詳細資料，説明您查看攻擊的範圍。
- [自動調查及回應](mtp-autoir.md) <br> AIR 可讓您的安全性作業小組大幅增加貴組織處理安全性警示和事件的能力。
- [進一步搜尋增強功能](advanced-hunting-overview.md) <br> 使用 Kusto 查詢語言及安全性優化的架構，在新式工作區中主動尋找威脅。

## <a name="march-2019"></a>2019 年 3 月
- 進階搜捕 <br> 登陸頁面提供各種搜尋功能，讓您主動找出影響電子郵件和資料、裝置和身分身分的威脅。
- [Microsoft 安全分數](microsoft-secure-score.md) <br> 組織安全性措施的度量，數位越高，表示已採取更多改進動作。 遵循安全性分數建議可保護貴組織不受威脅。 
- [報告](monitoring-and-reporting.md) <br>  功能豐富的卡片涵蓋安全性分析師和系統管理員在日常作業中追蹤的數個領域。
