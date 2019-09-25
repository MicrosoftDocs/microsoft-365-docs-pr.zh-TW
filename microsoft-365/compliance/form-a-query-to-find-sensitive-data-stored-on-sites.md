---
title: 形成查詢以搜尋儲存在網站上的敏感資料
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 通过 SharePoint Online 中的数据丢失防护 （DLP），您可以发现包含整个租户敏感数据的文档。 探索文件之後，您可以與文件擁有者協力保護資料。 本主題可以協助您進行查詢，以搜尋敏感資料。
ms.openlocfilehash: c9013e8334a4ef891885c7bc53b746b2db42b156
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077029"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>形成查詢以搜尋儲存在網站上的敏感資料

使用者經常會在網站上儲存敏感資料，例如信用卡號碼、身分證字號，或其他個人資料，長期下來，這會讓組織處於資料遺失的巨大風險中。 存储在网站上的文档（包括 OneDrive 业务网站）可以与组织外部不应访问信息的人员共享。 通过 SharePoint Online 中的数据丢失防护 （DLP），您可以发现包含整个租户敏感数据的文档。 探索文件之後，您可以與文件擁有者協力保護資料。 本主題可以協助您進行查詢，以搜尋敏感資料。
  
> [!NOTE]
> 电子发现或电子数据展示和 DLP 是需要[SharePoint 在线计划 2](https://go.microsoft.com/fwlink/?LinkId=510080)的高级功能。 
  
## <a name="forming-a-basic-dlp-query"></a>形成基本 DLP 查詢

基本 DLP 查詢是由三個部分組成：SensitiveType、計數範圍及信賴範圍。 如下图所示，**敏感类型："\<\>类型"** 是必需的，**|\<计数范围\>** 和**|\<置信范围\>** 都是可选的。 
  
![查詢範例分為必要和選用](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>敏感類型 - 必要

那麼各個部分分別是什麼？ SharePoint DLP 查询通常从属性`SensitiveType:"`开始，从[敏感信息类型清单](https://go.microsoft.com/fwlink/?LinkID=509999)中输入信息类型名称，最后以 以`"`结束。 您还可以使用为组织创建的[自定义敏感信息类型](create-a-custom-sensitive-information-type.md)的名称。 例如，您可能要尋找包含信用卡號碼的文件。 在这种情况下，您将使用以下格式： `SensitiveType:"Credit Card Number"`。 由于您不包括计数范围或置信区间，因此查询将返回检测到信用卡号的每个文档。 這是您可以執行的最簡單的查詢，會傳回最多結果。 請記住，敏感類型的拼字和空格有影響。 
  
### <a name="ranges---optional"></a>範圍 - 選用

接下来的两个部分都是范围，因此让我们快速检查一个范围的外观。 在 SharePoint DLP 查询中，基本范围由两个按句点分隔的数字表示，如下所示： `[number]..[number]`。 例如，如果使用，`10..20`该范围将捕获从 10 到 20 的数字。 有許多不同的範圍組合，本主題涵蓋其中一些組合。 
  
让我们向查询添加计数范围。 可以使用计数范围来定义文档在包含查询结果之前需要包含的敏感信息的匹配次数。 例如，如果希望查询仅返回仅包含五个信用卡号的文档，请使用： `SensitiveType:"Credit Card Number|5"`。 計數範圍也可以協助您識別有高度風險的文件。 例如，您的組織可能會將具有 5 個以上信用卡號碼的文件視為高風險。 要查找符合此条件的文档，请使用此查询： `SensitiveType:"Credit Card Number|5.."`。 或者，您可以使用以下查询查找具有 5 个或更少信用卡号的文档： `SensitiveType:"Credit Card Number|..5"`。 
  
#### <a name="confidence-range"></a>信賴範圍

最後，信賴範圍是已偵測之敏感類型實際符合的信賴等級。 信賴範圍值的運作方式與計數範圍類似。 您不用包含計數範圍也可以形成查詢。 例如，要搜索具有任意数量的信用卡号的文档（只要置信区间为 85% 或更高），可以使用以下查询： `SensitiveType:"Credit Card Number|*|85.."`。 
  
> [!IMPORTANT]
> 星号 （ `*`） 是一个通配符，表示任何值都有效。 您可以在计数范围或置信范围内使用`*`通配符 （ ），但不能在敏感类型中使用。 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>可以在 eDiscovery 中心取得的其他查詢屬性和搜尋運算子

SharePoint 中的 DLP 还引入了"最后敏感内容Scan"属性，它可以帮助您搜索在特定时间范围内扫描的文件。 有关属性`LastSensitiveContentScan`的查询示例，请参阅下一节中[的复杂查询示例。](#examples-of-complex-queries) 
  
您不仅可以使用特定于 DLP 的属性来创建查询，还可以使用标准 SharePoint 电子数据展示搜索属性（`Author`如`FileExtension`或 ）。 您可以使用運算子來建立複雜查詢。 有关可用属性和运算符的列表，请参阅[使用搜索属性和运算符与电子数据展示](https://go.microsoft.com/fwlink/?LinkId=510093)博客文章。 
  
## <a name="examples-of-complex-queries"></a>範例

以下示例使用不同的敏感类型、属性和运算符来说明如何优化查询以准确查找要查找的内容。
  
|**Query**|**說明**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |名称可能看起来很奇怪，因为它太长，但它是该敏感类型的正确名称。 请确保使用[敏感信息类型清单](https://go.microsoft.com/fwlink/?LinkID=509999)中的确切名称。 您还可以使用为组织创建的[自定义敏感信息类型](create-a-custom-sensitive-information-type.md)的名称。  <br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |这将返回与敏感类型"信用卡号"至少匹配一个文档的文档。 每個範圍的值分別是最小值與最大值。 编写此查询的更简单`SensitiveType:"Credit Card Number"`方法是，但其中的乐趣在哪里？  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |这将返回 2018 年 8 月 11 日至 2018 年 8 月 13 日期间扫描的 5-25 个信用卡号的文档。  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |这将返回 2018 年 8 月 11 日至 2018 年 8 月 13 日期间扫描的 5-25 个信用卡号的文档。 具有 XLSX 扩展名的文件不包括在查询结果中。  `FileExtension`是可以在查询中包含的许多属性之一。 有关详细信息，请参阅[使用搜索属性和运算符与电子数据。](https://go.microsoft.com/fwlink/?LinkId=510093)  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |這會傳回包含信用卡號碼或身分證字號的文件。  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>範例

並非所有查詢都可以同等建立。 下表提供了在 SharePoint 中不与 DLP 配合的查询示例，并说明了原因。
  
|**不受支援的查詢**|**原因**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |您必須至少新增一個數值。  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule"不是有效的敏感类型名称。 只有[敏感信息类型](https://go.microsoft.com/fwlink/?LinkID=509999)中的名称在 DLP 查询中工作。  <br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |零作为范围内的最小值或最大值无效。  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |可能很难看到，但"信用"和"卡"之间有额外的空白，使查询无效。 使用[敏感信息类型清单](https://go.microsoft.com/fwlink/?LinkID=509999)中的确切敏感类型名称。  <br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |两个周期部分不应用空格分隔。  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |管道分隔符太多（|). 请改用以下格式：`SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |由于置信度值表示百分比，因此不能超过 100。 請改為選擇 1 到 100 的數字。  <br/> |
   
## <a name="for-more-information"></a>相關資訊

[機密資訊類型在找什麼](what-the-sensitive-information-types-look-for.md)
  
[在 Office 365 安全&amp;合规性中心运行内容搜索](run-a-content-search-in-the-security-and-compliance-center.md)
  
[內容搜尋的關鍵字查詢與搜尋條件](keyword-queries-and-search-conditions.md)
  

