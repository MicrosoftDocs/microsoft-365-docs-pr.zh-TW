---
title: 取得高級搜尋的專家訓練
description: 來自高級搜尋專家的免費訓練和指導方針
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，搜尋，查詢，語言，訓練，案例，basic 到高級，影片，逐步指導
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
ms.technology: m365d
ms.openlocfilehash: 0b816956442408c9a61f662827f1fd45d9b6511f
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538852"
---
# <a name="get-expert-training-on-advanced-hunting"></a>取得高級搜尋的專家訓練

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender
- 適用於端點的 Microsoft Defender

透過 _追蹤敵人_，以提升您的高級搜尋知識，獲得新安全性分析師和經驗豐富威脅 hunters 的網路廣播系列。 該數列會逐步引導您建立您自己複雜的查詢的基本方法。 先從第一個影片開始，或跳到更多符合您經驗水準的視頻。

| 職稱 | 描述 | Watch | 查詢 | 
|--|--|--|--|
| 第1集： KQL 基礎 | 這一部分涵蓋 Microsoft 365 Defender 中的高級搜尋基本知識。 深入瞭解可用的高級搜尋資料和基本 KQL 語法及運算子。 | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14)  | [文字檔](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.txt) |
| 劇集2：聯接 | 繼續瞭解高級搜尋中的資料，以及如何將資料表結合在一起。 深入瞭解 `inner` 、 `outer` 、 `unique` 及 `semi` 加入，並瞭解預設 Kusto join 的細微差別 `innerunique` 。 | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33)  | [文字檔](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.txt) |
| 第3集：匯總、切換和視覺化資料 | 現在，您已瞭解如何篩選、處理及加入資料，這是時間摘要、量化、透視及顯示。 本文將討論 `summarize` 運算子和各種計算，同時還會引入架構中的其他資料表。 您也將瞭解如何將資料集變成可協助您抽出洞察力的圖表中。 | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52)  | [文字檔](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.txt) |
| 第4集：讓我們尋找！ 將 KQL 套用至事件追蹤 | 在此中，您將瞭解如何追蹤某些攻擊者的活動。 我們使用我們對 Kusto 和高級搜尋的深入瞭解，以追蹤攻擊。 瞭解欄位中使用的實際墩，包括 ABCs 的 cybersecurity，以及如何將其套用至事件回應。 | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36)  | [文字檔](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.txt) 


透過 L33TSP3AK 取得更多專家訓練 *： Microsoft 365 Defender 的高級搜尋*，這是一種網路廣播的網路廣播系列，用來尋找在 Microsoft 365 Defender 中使用「高級搜尋」來進行安全性調查的技術知識及實際技能。 

| 職稱 | 描述 | Watch | 查詢 | 
|--|--|--|--|
| 劇集1  | 在此中，您將瞭解執行高級搜尋查詢的不同最佳作法。 涵蓋的主題包括：如何優化您的查詢、使用勒索軟體的高級搜尋、將 JSON 當做動態類型處理，以及使用外部資料運算子。 | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34)  | [文字檔](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.txt) |
| 劇集2 | 在此中，您將瞭解如何透過收件匣轉寄規則調查和回應可疑或不尋常的登入位置和資料 exfiltration。 Sebastien Molendijk，Cloud Security CxE 的資深計畫經理，分享如何使用高級搜尋來調查使用 Microsoft Cloud App Security 資料的多階段事件。 | [YouTube](https://www.youtube.com/watch?v=QaUxdtNfbd8) (57:07)  | [文字檔](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/MCAS%20-%20The%20Hunt.txt)


## <a name="how-to-use-the-csl-file"></a>如何使用 CSL 檔案
開始劇集之前，請先[在 GitHub 上](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Webcasts)存取對應的文字檔，然後將其內容複寫到高級搜尋查詢編輯器。 當您觀賞劇集時，您可以使用複製的內容來追蹤喇叭，並執行查詢。 

下列來自包含查詢的文字檔摘錄會顯示一組完整的指導方針，其標示為批註 `//` 。

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

同一個文字檔會包含批註前面和後面的查詢，如下所示。 若要 [在編輯器中使用多個查詢](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)執行特定查詢，請將游標移至該查詢，然後選取 [ **執行查詢**]。   

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

CloudAppEvents
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
