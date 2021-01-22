---
title: 取得進位搜尋專家訓練
description: 來自進一步搜尋專家的免費訓練和指南
keywords: 進位搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、語言、訓練、案例、基本到進進、影片、逐步說明
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
ms.openlocfilehash: d7c2ccb12cb096359e558af9e1b4a962a9130be5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929631"
---
# <a name="get-expert-training-on-advanced-hunting"></a>取得進位搜尋專家訓練

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

使用追蹤新安全性分析師和經驗豐富的威脅員的一系列網路廣播系列，快速提升您的進一步搜尋知識。 本系列會引導您完成基本功能，以建立自己的複雜查詢。 從基本功能的第一段影片開始，或跳至符合您經驗等級的進一步影片。


| 職稱 | 說明 | Watch | 查詢 | 
|--|--|--|--|
| 第 1 集：KQL 基礎 | 本集涵蓋 Microsoft 365 Defender 進位搜尋的基本功能。 瞭解可用的進位搜尋資料和基本 KQL 語法及運算子。 | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54：14)  | [CSL 檔案](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| 第 2 集：加入 | 繼續學習進一搜尋的資料，以及如何將表格連接在一起。 瞭解 `inner` 、 `outer` `unique` 及聯聯，並瞭解預設 `semi` Kusto 聯聯的細微 `innerunique` 之處。 | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53：33)  | [CSL 檔案](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| 第 3 集：摘要、樞紐分析及視覺化資料 | 現在，您學習了篩選、操作及連接資料，是時候進行摘要、量化、樞紐分析及視覺化了。 此集探討運算子 `summarize` 和各種計算，同時在架構仲介紹其他資料表。 您也會瞭解如何將資料集轉換成圖表，説明您解壓縮深入見解。 | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48：52)  | [CSL 檔案](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| 第 4 集：讓我們來搜尋吧！ 將 KQL 應用至事件追蹤 | 在這集中，您將學習如何追蹤一些攻擊者的活動。 我們運用我們改善對庫斯圖的理解和進一步搜尋來追蹤攻擊。 瞭解該欄位中使用的實際訣竅，包括網路安全性的 ABC，以及如何將它們套用至事件回應。 | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59：36)  | [CSL 檔案](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>如何使用 CSL 檔案
開始一集之前，請存取 [GitHub 上對應的 Kusto CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) 檔案，將其內容複寫到進位搜尋查詢編輯器。 當您觀看集時，您可以使用複製的內容來追蹤演講者並執行查詢。 

CSL 檔案的下列摘錄內容顯示標示為批註的一套完整的指引 `//` 。

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

相同的 CSL 檔案包含批註之前和之後的查詢，如下所示。 若要在編輯器中使用多個查詢執行特定的查詢 [，將游標](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)移至該查詢，然後選取執行 **查詢**。   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp

AppFileEvents
| take 100
| sort by Timestamp desc
```
     
## <a name="related-topics"></a>相關主題
- [進階搜捕概觀](advanced-hunting-overview.md)
- [了解進階搜捕查詢語言](advanced-hunting-query-language.md)
- [使用查詢結果工作](advanced-hunting-query-results.md)
- [使用共用查詢](advanced-hunting-shared-queries.md)
- [跨裝置、電子郵件、應用程式和身分識別搜捕](advanced-hunting-query-emails-devices.md)
- [了解結構描述](advanced-hunting-schema-tables.md)
- [套用查詢最佳做法](advanced-hunting-best-practices.md)
