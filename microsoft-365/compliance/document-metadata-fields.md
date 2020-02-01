---
title: 文件的中繼資料欄位中資料調查 （預覽）
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 1edf55298981fe8c20a38c863229a7349d6b0862
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595178"
---
# <a name="document-metadata-fields-in-data-investigations-preview"></a>文件的中繼資料欄位中資料調查 （預覽）

下表列出文件的中繼資料欄位中的辨識項集合中調查資料調查 （預覽） 中。 表格會指出的中繼資料欄位名稱，是否可以搜尋欄位，當執行查詢中的辨識項設定、 欄位是否存在時的辨識項集中檢視選取的文件的檔案中繼資料和欄位是否包含何時會匯出文件。 

> [!NOTE]
> **Searchable 中辨識項設定**] 欄中的括號中的值是屬性的您可以搜尋的名稱。 在括號內**Viewable 中檔案的中繼資料**欄的值是您要檢視的檔案中繼資料時，會顯示屬性的名稱。

|**欄位名稱** </br>|**可辨識項集合中搜尋** |**可在 [檔案中繼資料** |**匯出** |
|:-------------------------- |:---------------------------------------- |:------------------------|:------------------|
|Case 標記                  | 是 （標記）                                      |                         | 是         |
|合規性標籤          |                                                 |                         | 是         |
|複合路徑              |                                                 |                         | 是         |
|容器識別碼               |                                                 |                         | 是         |
|交談的索引         |                                                 |                         | 是         |
|監管人                  | 是 (custodian)                                 |   是 (Custodian)       | 是         |
|資料來源                | [是] （來源）                                    |   是 （工作負載）          | 是         |
|日期                       | [是] (date)                                      |   [是] (Date UTC)        | 是         |
|Deduped 複合路徑      |                                                 |                         | 是         |
|Deduped 的 custodians         |                                                 |                         | 是         |
|Deduped 的檔案識別碼           |                                                 |                         | 是         |
|文件作者                | 是 （作者） *                                   |    是 （作者）         | 是         |
|文件註解               | 是 （註解）                                  |                         | 是         |
|Doc 公司                |                                                 |                         | 是         |
|建立 doc 日期           | 是 (createdTime) *                              |    [是] （建立時間）   | 是         |
|修改 doc 日期          | 是 (lastModifiedDate) *                         |                         | 是         |
|Doc 關鍵字               |                                                 |                         | 是         |
|上次儲存的文件          |                                                 |                         | 是         |
|修改過的文件            |                                                 |                         | 是         |
|Doc 主旨                |                                                 |  是 （主旨/標題）    | 是         |
|文件範本               |                                                 |                         | 是         |
|文件標題                  | 是 （標題）                                     |  是 （標題）            | 是         |
|文件版本                |                                                 |                         | 是         |
|主控項的佈景主題             | 是 (dominantTheme)                             |  是 （主控項佈景主題）   | 是         |
|重複的子集           |                                                 |                         | 是         |
|電子郵件動作               |                                                 |                         | 是         |
|電子郵件 [密件副本]                  | [是] (bcc)                                       |                         | 是         |
|電子郵件 [副本]                   | [是] (cc)                                        |                         | 是         |
|電子郵件交談識別碼      |                                                 |                         | 是         |
|接收的電子郵件日期        | 是 （接收）                                  |   是 （接收）        | 是         |
|送出的電子郵件日期            | 是 （傳送）                                      |   是 （傳送）            | 是         |
|電子郵件具有附件       |                                                 |                         | 是         |
|電子郵件重要性           |                                                 |                         | 是         |
|電子郵件網際網路標頭     |                                                 |                         | 是         |
|電子郵件層級                |                                                 |                         | 是         |
|電子郵件訊息識別碼           |                                                 |                         | 是         |
|電子郵件參與者網域  | 是 (participantDomains)                        |                         | 是         |
|電子郵件的參與者         | 是 （參與者）                              |                         | 是         |
|電子郵件收件者網域    | 是 (recipientDomains)                          |                         | 是         |
|電子郵件收件者           | 是 （收件者）                                |                         | 是         |
|電子郵件安全性             |                                                 |                         | 是         |
|電子郵件寄件者               | 是 （寄件者）                                    |   是 （寄件者）          | 是         |
|電子郵件寄件者網域        | 是 (senderDomain)                              |                         | 是         |
|電子郵件的敏感度          |                                                 |                         | 是         |
|電子郵件設定                  | 是 (emailSetId)                                |   是 (EmailSetID)      | 是         |
|電子郵件主旨              | 是 (subject)                                   |   是 （主旨/標題）   | 是         |
|電子郵件執行緒               |                                                 |                         | 是         |
|將電子郵件到                   | 是 （要）                                        |                         | 是         |
|錯誤碼                 | 是 (processingStatus)                          |                         | 是         |
|匯出原生路徑         |                                                 |                         | 是         |
|擷取的文字長度      |                                                 |                         | 是         |
|擷取的文字路徑        |                                                 |                         | 是         |
|家庭識別碼                  | 是 (Id)                                  |   是 (Id)        | 是         |
|家庭大小                |                                                 |                         | 是         |
|檔案類別                 | 是 (fileClass)                                 |   是 （檔類別）      | 是         |
|檔案識別碼                    | 是 (fileId)                                    |   是 (Id)              | 是         |
|具有文字                   |                                                 |                         | 是         |
|內含類型             | 是 (inclusiveType)                             |   是 （內含類型）  | 是         |
|輸入修改的日期        |                                                 |                         | 是         |
|輸入的檔案識別碼              |                                                 |                         | 是         |
|輸入的路徑                 |                                                 |                         | 是         |
|網際網路郵件識別碼        |                                                 |                         | 是         |
|代表          | 是 (markAsRepresentative)                      |                         | 是         |
|項目類別                 |                                                 |                         | 是         |
|負載識別碼                    | 是 (loadId)                                    |                         | 是         |
|位置名稱              |                                                 |                         | 是         |
|標示為樞紐分析表            | 是 (markAsPivot)                               |   [是] （標示為樞紐分析表） | 是         |
|訊息類型               | 是 (messageKind)                               |                         | 是         |
|原生副檔名           |                                                 |                         | 是         |
|原生檔案名稱           |                                                 |    是 (FileName)      | 是         |
|原生 MD5                 |                                                 |                         | 是         |
|原生 SHA 256             |                                                 |                         | 是         |
|原生大小                | 是 （大小）                                      |   是 (NativeSize)     | 是         |
|原生型別                | 是 (fileType)                                  |   是 （檔案類型）       | 是         |
|ND ET 排序 excl 附加     |                                                 |                         | 是         |
|ND ET 排序 incl 附加     |                                                 |                         | 是         |
|ND 組                     |                                                 |                         | 是         |
|O365 作者               | 是 （作者） *                                   |   是 （寄件者/作者）   | 是         |
|所建立的 O365            |                                                 |                         | 是         |
|建立的 O365 日期          | 是 (createdTime) *                              |                         | 是         |
|修改的 O365 日期         | 是 (lastModifiedDate) *                         |   是 （上次修改日期） | 是      |
|修改的 O365           |                                                 |                         | 是         |
|父節點                |                                                 |                         | 是         |
|樞紐分析表識別碼                   | 是 (pivotId)                                   |  是 (PivotID)          | 是         |
|收件者的計數            |                                                 |                         | 是         |
|列數                 |                                                 |                         | 是         |
|設定識別碼                     |                                                 |                         | 是         |
|第一次設定順序 inclusives |                                                 |                         | 是         |
|相似性 %         |                                                 |                         | 是         |
|佈景主題清單                | 是 (themesList)                                | 是 （佈景主題的清單）       | 是         |
|字數統計                 | 是 (wordCount)                                 |                         | 是         |
|相關性分數 （問題）    | 是 (relevanceScore_issueNum)                   |                         |             |
|讀取百分位數 （問題）    | 是 (readPercentile_issueNum)                   |                         |             |
|相關性標記 （問題）      | 是 (relevanceTag_issueNum)                     |                         |             |
|||||

  \*適用於這些欄位中，如果沒有內嵌的值內的文件，搜尋會排列優先順序那些值;否則，它會嘗試顯示 Office 365 中的值。
