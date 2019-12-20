---
title: 搜尋與標記
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 進階 eDiscovery 中搜尋和標記模組可讓您搜尋、 預覽，及組織您的案例中的文件。 目前，此模組處於 beta 版。
ms.openlocfilehash: f5e192988519a9190aa53efef35a8e584e0987cc
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802896"
---
# <a name="search-and-tagging"></a>搜尋與標記

進階 eDiscovery 中搜尋和標記模組可讓您搜尋、 預覽，及組織您的案例中的文件。 目前，此模組處於 beta 版。 搜尋及標記的簡短示範，請參閱[管理您的資料與進階電子文件](https://www.youtube.com/watch?v=VaPYL3DHP6I)影片。

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="search-the-documents-in-your-case"></a>搜尋您的案例中的文件

在處理進階電子文件探索案例中的文件 （並選擇性地執行分析或相關性模組後），您可以使用標記與搜尋來搜尋文件並再將它們組織藉由套用特定案例的標記 （也稱為標籤）。 您可以定義搜尋查詢中使用提供的條件卡或利用 KQL 類似的查詢語言中的關鍵字條件卡片。 常見的 KQL 語法，例如 AND、 OR、 NOT、 NEAR(n) 且支援，以及行尾的多重字元萬用字元 （*）。 

下表列出您可以搜尋使用 KQL 關鍵字查詢的屬性。 或者，您可以使用進階 eDiscovery 搜尋工具中的條件卡片，若要新增至搜尋查詢的條件 （選取的內容）。

|**屬性**|**描述**|
|:-----|:-----|
|**caselabel** <br/> | 標記的名稱建立/時套用標記的文件。 <br/> |
|**custodian** <br/> | 相關聯的文件; custodian受到限制。 <br/> |
|**date** <br/> | 傳送電子郵件; 日期網站文件的修改的日期。 <br/> |
|**fileid** <br/> | 在 case 檔案識別碼。 <br/> |
|**filetype** <br/> | 原生檔案的副檔名。 <br/> |
|**fileclass** <br/> | 電子郵件、 文件或附件。 <br/> |
|**senderauthor** <br/> | 寄件者的電子郵件;網站文件的作者。 <br/> |
|**size** <br/> | Kb 的檔案大小。 <br/> |
|**subjecttitle** <br/> | 電子郵件; 主旨網站文件的標題。 <br/> |
|**bcc** <br/> | 電子郵件的密件副本] 欄位。 <br/> |
|**cc** <br/> | 電子郵件 [副本] 欄位。 <br/> |
|**參與者** <br/> | 電子郵件執行緒，包括缺少連結中的所有參與者的電子郵件地址。 <br/> |
|**接收** <br/> | 已收到一封電子郵件的日期。 <br/> |
|**收件者** <br/> | 收件者的電子郵件，包含在收件者]、 [副本] 或 [密件副本] 欄位。 <br/> |
|**sender** <br/> | 電子郵件的寄件者。 <br/> |
|**lastmodifieddate** <br/> | 上次修改日期的網站文件。 <br/> |
|**傳送** <br/> | 電子郵件傳送的日期。 <br/> |
|**to** <br/> | 電子郵件] 欄位中所列的收件者。 <br/> |
|**作者** <br/> | 網站文件的作者。 <br/> |
|**title** <br/> | 網站文件的標題。 <br/> |
|**dominanttheme**\* <br/> | 項目與基準佈景主題。 <br/> |
|**themeslist**\* <br/> | 項目相關聯的佈景主題。 <br/> |
|**readpercentile_ [issuenum]**\*\* <br/> | 讀取百分位數的項目，如 [issuenum] 所定義的問題。 <br/> |
|**relevancescore_ [issuenum]**\*\* <br/> | 項目，由 [issuenum] 定義問題相關性分數。 <br/> |
|**relevancetag_ [tagname]**\*\* <br/> | 如果項目有已手動標示相關性，[tagname] 所定義的標籤。 <br/> |
|||

\*如果已經執行 [佈景主題模組才可用。

\*\*如果已經執行 [相關性模組才可用。

或者，您可以使用進階 eDiscovery 搜尋工具中的條件卡片，新增至搜尋查詢的條件 （選取的內容）。 下列螢幕擷取畫面顯示可以新增至查詢的條件。 [**群組**] 欄會指出屬性是否適用於電子郵件、 網站文件，或兩者 （由*常見*的值來表示）。 此資料行也會識別之後執行相關性模組都是可用的可搜尋屬性。

![在 [進階電子文件探索搜尋工具中的搜尋條件](media/AeDSearchConditions.png)

如需可搜尋屬性的詳細資訊，請參閱[關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。
  
## <a name="see-also"></a>另請參閱

[Office 365 進階電子文件探索](office-365-advanced-ediscovery.md)
  
[了解相關性評估](assessment-in-relevance-in-advanced-ediscovery.md)
  
[標記與評估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[標記與相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[決定根據結果](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[測試相關性分析](test-relevance-analysis-in-advanced-ediscovery.md)

