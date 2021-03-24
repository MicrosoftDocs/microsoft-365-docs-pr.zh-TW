---
title: Microsoft 365 Defender 的新功能
description: 列出 Microsoft 365 Defender 中的新功能與功能
keywords: microsoft 威脅防護中的新功能，ga，一般可用，功能，可用，新
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
ms.openlocfilehash: e75cfe445f62860f8bdb1480fcf9029daa8ac6ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060383"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Microsoft 365 Defender 的新功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> 想要體驗 Microsoft 365 Defender？ 您可以 [在實驗室環境中進行評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ，或 [在實際執行中執行您的試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。
>

在最新版本的 Microsoft 365 Defender 中， (GA) 一般都有下列功能可供使用。

RSS 摘要：將下列 URL 複製並貼到您的摘要讀取器時，獲得此頁面的通知：
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="march-2021"></a>2021 年 3 月
- [CloudAppEvents 表格](advanced-hunting-cloudappevents-table.md) <br>尋找 Microsoft Cloud App Security 涵蓋的各種雲端應用程式和服務中的事件資訊。 此表格也包含先前在中提供的資訊 `AppFileEvents` 。
## <a name="february-2021"></a>2021 年 2 月
-  (預覽) 增強型[Microsoft 365 安全性中心 (https://security.microsoft.com) ](https://security.microsoft.com)現在已提供公開預覽。 這種新的經驗會將適用于 Office 365 的 Defender 和 Defender 帶入中央。 [深入了解變更的功能](./overview-security-center.md)。

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
- [Microsoft 安全分數](microsoft-secure-score.md) <br> 度量組織的安全性狀況，其值越高，表示採取的改善動作越多。 遵循安全性分數建議可保護您的組織免受威脅。 
- [報告](overview-security-center.md) <br>  可提供一系列的功能，涵蓋安全分析員和系統管理員在日常作業中所追蹤的各種區域。
