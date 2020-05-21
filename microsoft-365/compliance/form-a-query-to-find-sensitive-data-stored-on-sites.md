---
title: 形成查詢以搜尋儲存在網站上的敏感資料
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 透過資料遺失防護（DLP）的 SharePoint 線上，您可以發現整個租使用者中包含敏感性資料的檔。 探索文件之後，您可以與文件擁有者協力保護資料。 本主題可以協助您進行查詢，以搜尋敏感資料。
ms.openlocfilehash: 78f7f07bf6b2fbb0781f4bda8716b84399eef561
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327911"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>形成查詢以搜尋儲存在網站上的敏感資料

使用者經常會在網站上儲存敏感資料，例如信用卡號碼、身分證字號，或其他個人資料，長期下來，這會讓組織處於資料遺失的巨大風險中。 儲存在網站上的檔（包括商務網站 OneDrive）可以與組織外部的人員共用，而不應該存取訊號。 透過資料遺失防護（DLP）的 SharePoint 線上，您可以發現整個租使用者中包含敏感性資料的檔。 探索文件之後，您可以與文件擁有者協力保護資料。 本主題可以協助您進行查詢，以搜尋敏感資料。
  
> [!NOTE]
> 電子化探索（或 eDiscovery）和 DLP 是需要[SharePoint 線上方案 2](https://go.microsoft.com/fwlink/?LinkId=510080)的高級功能。 
  
## <a name="forming-a-basic-dlp-query"></a>形成基本 DLP 查詢

基本 DLP 查詢是由三個部分組成：SensitiveType、計數範圍及信賴範圍。 如下圖所示， **SensitiveType: " \< type \> "** 是必要的，且** | \< 計數範圍 \> **和** | \< 信賴範圍 \> **都是選用的。 
  
![查詢範例分為必要和選用](../media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>敏感類型 - 必要

那麼各個部分分別是什麼？ SharePoint DLP 查詢通常會以屬性 `SensitiveType:"` 和[機密資訊類型清單](https://go.microsoft.com/fwlink/?LinkID=509999)中的資訊類型名稱開始，並以 `"` 。 您也可以使用您為組織建立的[自訂機密資訊類型](create-a-custom-sensitive-information-type.md)的名稱。 例如，您可能要尋找包含信用卡號碼的文件。 在這種情況下，您會使用下列格式： `SensitiveType:"Credit Card Number"` 。 因為您未包含計數範圍或信賴範圍，所以查詢會傳回偵測到信用卡號碼的每個檔。 這是您可以執行的最簡單的查詢，會傳回最多結果。 請記住，敏感類型的拼字和空格有影響。 
  
### <a name="ranges---optional"></a>範圍 - 選用

接下來的兩個部分皆為範圍，讓我們快速檢查範圍的外觀。 在 SharePoint DLP 查詢中，基本範圍是以兩個數字來表示，這兩個數字是以兩個句點隔開，如下所示： `[number]..[number]` 。 例如，如果 `10..20` 使用，該範圍會從10到20取得數位。 有許多不同的範圍組合，本主題涵蓋其中一些組合。 
  
讓我們將計數範圍新增至查詢。 您可以使用 count 範圍來定義檔在查詢結果中包含之前必須包含的機密資訊發生次數。 例如，如果您希望查詢只傳回正好包含五個信用卡號碼的檔，請使用下列： `SensitiveType:"Credit Card Number|5"` 。 計數範圍也可以協助您識別有高度風險的文件。 例如，您的組織可能會將具有 5 個以上信用卡號碼的文件視為高風險。 若要尋找符合此準則的檔，您可以使用此查詢： `SensitiveType:"Credit Card Number|5.."` 。 或者，您可以使用下列查詢找到具有五個或更少信用卡號碼的檔： `SensitiveType:"Credit Card Number|..5"` 。 
  
#### <a name="confidence-range"></a>信賴範圍

最後，信賴範圍是已偵測之敏感類型實際符合的信賴等級。 信賴範圍值的運作方式與計數範圍類似。 您不用包含計數範圍也可以形成查詢。 例如，若要搜尋具有任何數目的信用卡號碼的檔，只要信賴範圍為85% 或更高，您就可以使用此查詢： `SensitiveType:"Credit Card Number|*|85.."` 。 
  
> [!IMPORTANT]
> 星號（ `*` ）是一種萬用字元，表示任何值都可以運作。 您可以 `*` 在計數範圍或信賴範圍中（但不是以敏感類型）使用萬用字元（）。 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>可以在 eDiscovery 中心取得的其他查詢屬性和搜尋運算子

DLP in SharePoint 也會引入 LastSensitiveContentScan 屬性，可協助您搜尋特定時間範圍內掃描的檔案。 如需屬性的查詢範例 `LastSensitiveContentScan` ，請參閱下一節中的[複雜查詢範例](#examples-of-complex-queries)。 
  
您不僅可以使用 DLP 特有的屬性來建立查詢，也可以使用標準 SharePoint eDiscovery 搜尋屬性（例如 `Author` or） `FileExtension` 。 您可以使用運算子來建立複雜查詢。 如需可用的屬性及運算子清單，請參閱[使用搜尋屬性和操作員搭配 eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093)博客文章。 
  
## <a name="examples-of-complex-queries"></a>範例

下列範例會使用不同的敏感類型、屬性及運算子，以說明如何細化您的查詢，以準確找到您所要尋找的專案。
  
|**Query**|**說明**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |這種名稱似乎很奇怪，但它是該機密類型的正確名稱。 請務必使用[敏感資訊類型清查](https://go.microsoft.com/fwlink/?LinkID=509999)中的確切名稱。 您也可以使用您為組織建立的[自訂機密資訊類型](create-a-custom-sensitive-information-type.md)的名稱。  <br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |這會傳回具有至少一個符合機密類型 "信用卡號碼" 的檔。 每個範圍的值分別是最小值與最大值。 編寫此查詢的簡單方法是 `SensitiveType:"Credit Card Number"` ，但在哪裡很有趣呢？  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |這會傳回檔，其5-25 會從8月11日到2018到8月13日（2018）為止掃描。  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |這會傳回檔，其5-25 會從8月11日到2018到8月13日（2018）為止掃描。 具有 .XLSX 副檔名的檔案不會包含在查詢結果中。  `FileExtension`是您可以在查詢中包含的眾多屬性之一。 如需詳細資訊，請參閱搭配[EDiscovery 使用 Search 屬性和運算子](https://go.microsoft.com/fwlink/?LinkId=510093)。  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |這會傳回包含信用卡號碼或身分證字號的文件。  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>範例

並非所有查詢都可以同等建立。 下表提供 SharePoint 中無法使用 DLP 的查詢範例，並說明原因。
  
|**不受支援的查詢**|**原因**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |您必須至少新增一個數值。  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule" 不是有效的機密類型名稱。 DLP 查詢中只有[敏感資訊類型清查](https://go.microsoft.com/fwlink/?LinkID=509999)的名稱。  <br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |0不是有效的範圍中的最小值或最大值。  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |可能很難看到，但「信用卡」和「卡片」之間有多餘的空白，使查詢無效。 使用[敏感資訊類型清查](https://go.microsoft.com/fwlink/?LinkID=509999)中的完全機密類型名稱。  <br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |兩個週期的部分不應該以空格隔開。  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |有太多管道分隔符號（|). 請改為遵循此格式：`SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |因為信賴值代表百分比，所以不能超過100。 請改為選擇 1 到 100 的數字。  <br/> |
   
## <a name="for-more-information"></a>相關資訊

- [敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md)
- [執行內容搜尋](content-search.md)
- [內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
  

