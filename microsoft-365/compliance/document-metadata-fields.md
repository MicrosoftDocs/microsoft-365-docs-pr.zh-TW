---
title: '資料調查中的檔元資料欄位 (預覽) '
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在 [資料調查] (預覽) 中，查看列出證據集中檔之元資料欄位的表格。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f365ca6381fee2713f6e1c8e68eb9b1cd8e1fb88
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285389"
---
# <a name="document-metadata-fields-in-data-investigations-preview"></a>資料調查中的檔元資料欄位 (預覽) 

下表列出在資料調查 (預覽) 中進行調查之證據集中的檔元資料欄位。 該表會指出元資料欄位的名稱、在證據集內執行查詢時是否可以搜尋該欄位，是否有當查看證據集內所選取檔的檔案中繼資料，以及匯出檔時是否包含該欄位。 

> [!NOTE]
> 在 [ **證據集** ] 欄中可搜尋的括弧中的值是您可以搜尋的屬性名稱。 在 [ **檔中繼資料** ] 欄中的 [可查看的括弧] 中的值是您在查看檔中繼資料時所顯示的屬性名稱。

|**欄位名稱** </br>|**在證據集中搜尋** |**可在檔中繼資料中查看** |**出口** |
|:-------------------------- |:---------------------------------------- |:------------------------|:------------------|
|Case 標記                  | 是 (標記)                                       |                         | 是         |
|符合性標籤          |                                                 |                         | 是         |
|複合路徑              |                                                 |                         | 是         |
|容器識別碼               |                                                 |                         | 是         |
|交談索引         |                                                 |                         | 是         |
|監管人                  | 是 (保管人)                                  |   是 (保管人)        | 是         |
|資料來源                | 是 (來源)                                     |   是 (工作量)           | 是         |
|日期                       | 是 (日期)                                       |   是 (日期 UTC)         | 是         |
|Deduped 複合路徑      |                                                 |                         | 是         |
|Deduped 保管人         |                                                 |                         | 是         |
|Deduped 檔案 IDs           |                                                 |                         | 是         |
|Doc 作者                | 是 (author) *                                   |    是 (Author)          | 是         |
|Doc 批註               | 是 (批註)                                   |                         | 是         |
|Doc 公司                |                                                 |                         | 是         |
|Doc 日期建立           | 是 (createdTime) *                              |    是 (建立時間)    | 是         |
|修改的 Doc 日期          | 是 (lastModifiedDate) *                         |                         | 是         |
|Doc 關鍵字               |                                                 |                         | 是         |
|Doc 上次儲存者          |                                                 |                         | 是         |
|修改的 Doc            |                                                 |                         | 是         |
|Doc 主題                |                                                 |  是 (主旨/Title)     | 是         |
|Doc 範本               |                                                 |                         | 是         |
|Doc 標題                  | 是 (標題)                                      |  是 (標題)             | 是         |
|Doc 版本                |                                                 |                         | 是         |
|主要主題             | 是 (dominantTheme)                              |  是 (主要主題)    | 是         |
|重複子集           |                                                 |                         | 是         |
|電子郵件動作               |                                                 |                         | 是         |
|電子郵件密密                  | Yes (bcc)                                        |                         | 是         |
|電子郵件抄送                   | Yes (cc)                                         |                         | 是         |
|電子郵件交談識別碼      |                                                 |                         | 是         |
|電子郵件接收日期        | ) 接收 (                                  |   ) 接收 (        | 是         |
|電子郵件傳送日期            | 是 (傳送)                                       |   是 (傳送)             | 是         |
|電子郵件有附件       |                                                 |                         | 是         |
|電子郵件重要性           |                                                 |                         | 是         |
|電子郵件網際網路標頭     |                                                 |                         | 是         |
|電子郵件層級                |                                                 |                         | 是         |
|電子郵件訊息識別碼           |                                                 |                         | 是         |
|電子郵件參與者網域  | 是 (participantDomains)                         |                         | 是         |
|電子郵件參與者         | 是 (參與者)                               |                         | 是         |
|電子郵件收件者網域    | 是 (recipientDomains)                           |                         | 是         |
|電子郵件收件者           | 是 (收件者)                                 |                         | 是         |
|電子郵件安全性             |                                                 |                         | 是         |
|電子郵件寄件者               | 是 (寄件者)                                     |   是 (寄件者)           | 是         |
|電子郵件寄件者網域        | 是 (senderDomain)                               |                         | 是         |
|電子郵件敏感度          |                                                 |                         | 是         |
|電子郵件集                  | 是 (emailSetId)                                 |   是 (EmailSetID)       | 是         |
|電子郵件主題              | 是 (主體)                                    |   是 (主旨/Title)    | 是         |
|電子郵件執行緒               |                                                 |                         | 是         |
|電子郵件至                   | Yes ()                                         |                         | 是         |
|錯誤碼                 | 是 (processingStatus)                           |                         | 是         |
|匯出原生路徑         |                                                 |                         | 是         |
|解壓縮的文字長度      |                                                 |                         | 是         |
|解壓縮文字路徑        |                                                 |                         | 是         |
|系列識別碼                  | 是 (familyId)                                   |   是 (FamilyId)         | 是         |
|系列大小                |                                                 |                         | 是         |
|檔類別                 | 是 (fileClass)                                  |   Yes (File class)       | 是         |
|檔識別碼                    | 是 (fileId)                                     |   是 (識別碼)               | 是         |
|具有文字                   |                                                 |                         | 是         |
|包含類型             | 是 (inclusiveType)                              |   是 (包含類型)   | 是         |
|已修改輸入日期        |                                                 |                         | 是         |
|輸入檔識別碼              |                                                 |                         | 是         |
|輸入路徑                 |                                                 |                         | 是         |
|網際網路郵件識別碼        |                                                 |                         | 是         |
|代表          | 是 (markAsRepresentative)                       |                         | 是         |
|專案類別                 |                                                 |                         | 是         |
|載入識別碼                    | 是 (loadId)                                     |                         | 是         |
|位置名稱              |                                                 |                         | 是         |
|標示為 pivot            | 是 (markAsPivot)                                |   Yes (標示為 Pivot)  | 是         |
|郵件類型               | 是 (messageKind)                                |                         | 是         |
|原生副檔名           |                                                 |                         | 是         |
|原生檔案名           |                                                 |    是 (FileName)       | 是         |
|原生 MD5                 |                                                 |                         | 是         |
|原生 SHA 256             |                                                 |                         | 是         |
|原生大小                | 是 (大小)                                       |   是 (NativeSize)      | 是         |
|原生類型                | 是 (類型)                                   |   是 (檔案類型)        | 是         |
|ND 不排序（附加）     |                                                 |                         | 是         |
|ND 的排序（包括附加）     |                                                 |                         | 是         |
|ND 集                     |                                                 |                         | 是         |
|O365 作者               | 是 (author) *                                   |   是 (Sender/Author)    | 是         |
|O365 建立者            |                                                 |                         | 是         |
|O365 建立日期          | 是 (createdTime) *                              |                         | 是         |
|O365 修改日期         | 是 (lastModifiedDate) *                         |   是 (上次修改日期)  | 是      |
|O365 修改者           |                                                 |                         | 是         |
|父節點                |                                                 |                         | 是         |
|樞紐分析表識別碼                   | 是 (pivotId)                                    |  是 (PivotID)           | 是         |
|收件者計數            |                                                 |                         | 是         |
|列號                 |                                                 |                         | 是         |
|設定識別碼                     |                                                 |                         | 是         |
|先設定順序 inclusives |                                                 |                         | 是         |
|相似性百分比         |                                                 |                         | 是         |
|主題清單                | 是 (themesList)                                 | 是 (主題清單)        | 是         |
|字數統計                 | 是 (wordCount)                                  |                         | 是         |
| (問題的相關性分數)     | 是 (relevanceScore_issueNum)                    |                         |             |
|讀取百分位數的 (問題)     | 是 (readPercentile_issueNum)                    |                         |             |
| (問題的相關性標記)       | 是 (relevanceTag_issueNum)                      |                         |             |
|||||

  \* 對於這些欄位，如果檔內有內嵌值，搜尋會將這些值排定優先順序;否則，它會嘗試從 Office 365 顯示值。
