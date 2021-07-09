---
title: Microsoft 365 Defender 的新功能
description: 列出 Microsoft 365 Defender 中的新功能與功能
keywords: Microsoft 365 Defender 中的新功能、ga、一般可用、功能、可供使用的新功能
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: af5efb669b1f73b4008ac2c3fae251a4d08511dd
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53340981"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender 的新功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> 想要體驗 Microsoft 365 Defender 嗎？ 您可以[在實驗室環境中評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[在生產環境中執行試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。
>

在最新版的 Microsoft 365 Defender 中， (正式發行) 一般都提供下列功能。

RSS 摘要：將下列 URL 複製並貼到您的摘要讀取器時，獲得此頁面的通知：
```http
/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="july-2021"></a>2021年7月
- [Professional services 目錄](https://sip.security.microsoft.com/interoperability/professional_services)<br>利用支援的合作夥伴連線，增強平臺的偵測、調查和威脅智慧功能。
    

## <a name="may-2021"></a>2021 年 5 月

- [Microsoft 365 Defender 入口網站中的 [新增提醒] 頁面](https://techcommunity.microsoft.com/t5/microsoft-365-defender/easily-find-anomalies-in-incidents-and-alerts/ba-p/2339243) <br> 將內容的增強資訊提供給攻擊。 您可以看到哪些其他觸發的警示導致目前的警示，以及攻擊中所涉及的所有受影響的實體和活動，包括檔案、使用者和信箱。 如需詳細資訊，請參閱 [調查提醒](/microsoft-365/security/defender/investigate-alerts) 。
- [Microsoft 365 Defender 入口網站中的事件及警示的趨勢圖](https://techcommunity.microsoft.com/t5/microsoft-365-defender/new-alert-page-for-microsoft-365-defender-incident-detections/ba-p/2350425) <br> 判斷單一事件是否有多個警示，或是組織受到數個不同的事件攻擊。 如需詳細資訊，請參閱 [優先順序事件](/microsoft-365/security/defender/incident-queue) 。


## <a name="april-2021"></a>2021 年 4 月
- Microsoft 365 Defender<br> 改進的[Microsoft 365 Defender](https://security.microsoft.com)入口網站現已提供。 這種新的經驗會彙集一或多個端點、Office 365 的 defender、身分識別的 defender，以及更多的單一入口網站。 這是管理安全性控制的新家用。 [了解新功能](./overview-security-center.md)。

- [Microsoft 365 Defender 威脅分析報告](threat-analytics.md)<br>
 威脅分析可協助您回應並將主動攻擊的影響降至最低。 您也可以瞭解 Microsoft 365 Defender 解決方案封鎖的攻擊嘗試，並採取預防措施，緩解進一步披露及提高恢復的風險。 在統一的安全性體驗中，威脅分析現在可用於 microsoft defender for Endpoint 和 microsoft defender Office E5 授權擁有者。

## <a name="march-2021"></a>2021 年 3 月
- [CloudAppEvents 表格](advanced-hunting-cloudappevents-table.md) <br>在 Microsoft Cloud App Security 所涵蓋的各種雲端 app 和服務中，尋找有關事件的資訊。 此表格也包含先前在中提供的資訊 `AppFileEvents` 。
## <a name="february-2021"></a>2021 年 2 月
-  (預覽) 「增強[Microsoft 365 安全性中心」 https://security.microsoft.com) (](https://security.microsoft.com)現在可用於公開預覽。 這種全新體驗會將 defender 用於端點，將 Office 365 的 defender 用於中央。 [深入了解變更的功能](./overview-security-center.md)。

## <a name="september-2020"></a>2020 年 9 月
- [IdentityDirectoryEvents 表格](advanced-hunting-identitydirectoryevents-table.md) <br> 尋找與執行 Active Directory (AD) 之內部部署網域控制站有關的事件。 這個 [高級搜尋](advanced-hunting-overview.md) 架構表涵蓋網域控制站上的身分識別相關事件及系統事件範圍。
- [AssignedIPAddresses () 函數](advanced-hunting-assignedipaddresses-function.md) <br> 您可以在您的高級搜尋查詢中使用此功能，快速取得指派給裝置的最新 IP 位址，或從特定時間取得最近的 IP 位址。

## <a name="july-2020"></a>2020 年 7 月
- [FileProfile () 函數](advanced-hunting-fileprofile-function.md) <br> 在您的高級搜尋查詢中使用此功能，以豐富包含完整檔案資訊的結果。
- [身分識別和應用程式表格](advanced-hunting-schema-tables.md)<br> 使用高級搜尋架構中的 [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)、 [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)及 [AppFileEvents](advanced-hunting-appfileevents-table.md) 表格，可以深入瞭解驗證事件、Active Directory 查詢及應用程式相關的活動。
- [開始搜補](advanced-hunting-go-hunt.md)<br> 快速從調查事件，以在高級搜尋中檢查特定事件、使用者、裝置或其他實體類型。

## <a name="june-2020"></a>2020 年 6 月
- Twitter 摘要 <br> 深入瞭解儀表板內的最新安全性調查、威脅情報、產品新聞及其他。
- [EmailPostDeliveryEvents 架構表格](advanced-hunting-emailpostdeliveryevents-table.md) <br> 在您的高級搜尋查詢中包含對電子郵件訊息所進行投遞投遞動作的相關資訊。
- [在 [高級搜尋] 中檢查記錄](advanced-hunting-query-results.md#drill-down-from-query-results) <br> 使用新的 [詳細資料] 面板，快速檢查查詢結果中的記錄。

## <a name="may-2020"></a>2020 年 5 月
- [自訂偵測](custom-detections-overview.md) <br> 使用高級搜尋查詢來建立自訂偵測規則，以自動監控和回應安全性事件和系統狀態。

## <a name="february-2020"></a>2020 年 2 月
- [事件](incidents-overview.md) <br> 確切知道攻擊已啟動的位置，以及可協助您瞭解攻擊程度的其他詳細資料。
- [自動調查及回應](m365d-autoir.md) <br> AIR 可讓您的安全性作業小組大幅增加貴組織處理安全性警示和事件的能力。
- [高級搜尋增強功能](advanced-hunting-overview.md) <br> 使用 Kusto 查詢語言和安全性優化架構，主動搜尋整個現代 workspace 中的威脅。

## <a name="march-2019"></a>2019 年 3 月
- 進階搜捕 <br> 可讓您主動找到影響電子郵件和資料、裝置和身分識別之威脅的各種搜尋功能的登陸頁面。
- [Microsoft 安全分數](microsoft-secure-score.md) <br> 度量組織的安全性狀況，其值越高，表示採取的改善動作越多。 遵循安全性分數建議可保護貴組織免受威脅。 
- [報告](overview-security-center.md) <br>  可提供一系列的功能，涵蓋安全分析員和系統管理員在日常作業中所追蹤的各種區域。
