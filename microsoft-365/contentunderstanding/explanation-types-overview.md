---
title: 釋義類型
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 深入瞭解 Microsoft SharePoint Syntex 中的說明類型
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295770"
---
# <a name="introduction-to-explanation-types"></a>說明類型簡介

使用說明來協助您定義要標籤的資訊，並在檔中解壓縮 Microsoft SharePoint Syntex 的知識模型。 當您建立說明時，請務必選取 [說明] 類型。 

本文可協助您瞭解不同的說明類型及其使用方式。

   ![釋義類型](../media/content-understanding/explanation-types.png) 
   
可供使用的說明類型如下：

- **片語清單**：您可以在檔中使用的單字、片語、數位或其他字元的清單，或是您要解壓縮的資訊。 例如，文字字串 **引用位址** 是指您所識別的所有醫學參考檔。</br>

- [**模式] 清單**：列出數位、字母或其他字元的模式，您可以用來識別要解壓縮的資訊。 例如，您可以從所識別的所有醫學參考檔中，解開參考醫生的 **電話號碼** 。</br>

- **鄰近**性：說明彼此的接近說明。 例如，[街道 *號碼* 模式] 清單會在 [ *街道名稱* 片語] 清單的前面，而不是在 (您會瞭解本文稍後的標記) 中。 
 
## <a name="phrase-list"></a>片語清單

片語清單釋義類型通常是用來透過您的模型來識別和分類檔。 如 [ *引用位址* ] 標籤範例所述，它是您所識別檔中一致的文字、片語、數位或字元字串。

如果您所要取得的片語位於您的檔中一致的位置，您可以使用您的說明取得更好的成功。 例如，「 *引用位址* 」標籤可能一致地位於檔的第一個段落中。

如果識別標籤需要區分大小寫，則使用片語清單類型可讓您選取 **唯一的確切大小寫** 核取方塊，以在您的說明中指定。

   ![區分大小寫](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>模式清單

當您建立說明，識別及提取檔中的資訊時，模式清單類型特別有用。 它通常會以不同的格式顯示，例如日期、電話號碼或信用卡號碼。 例如，可以使用不同的格式來顯示日期， (1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1、2020等等 ) 。 透過在您嘗試識別及解壓縮的資料中取得任何可能的變化，以定義 [模式] 清單，可讓您的說明更有效率。 

在 [ **電話號碼** ] 範例中，從模型所識別的所有醫療參考檔中，抽出每一位參考醫生的電話號碼。 當您建立說明時，請選取 [模式] 清單類型以允許您預期傳回的不同格式。

   ![電話號碼模式清單](../media/content-understanding/pattern-list.png)

在此範例中，選取 [ **0-9 中的任何數位** ] 核取方塊。 選取此項會將您的模式清單中所使用的每個「0」值都識別為從0到9的任何數位。

   ![0-9 的任何數位](../media/content-understanding/digit-identity.png)

同樣地，如果您建立包含文字字元的 [模式] 清單，請選取 [a-z] 核取方塊 **中的任何字母** 。 選取這種方式可辨識 pattern 清單中所用的每一個 "a" 字元，是從 "a" 到 "z" 的任何字元。

例如，如果您建立一個 **日期** 模式清單，而您想確定日期格式（例如 *1 月1日）* 可辨識為2020，您必須：
- 將 *aaa 0、0000* 和 *aaa 00，0000* 新增至您的模式清單。
- 請確定也選取 **了 a-z 中的任何字母** 。

   ![A-z 中的任何字母](../media/content-understanding/any-letter.png)

此外，如果您在 [您的模式] 清單中有大小寫需求，您可以選擇 **僅完全符合大小寫** 核取方塊。 在日期範例中，如果您需要將月份的第一個字母大寫，您必須：

- 將 *Aaa 0、0000* 和 *Aaa 00，0000* 新增至您的模式清單。
- 請確定也 **只會選取完全大寫** 。

   ![只完全符合大小寫](../media/content-understanding/exact-caps.png)

> [!NOTE]
> 除了手動建立模式清單說明之外，您也可以使用 [說明] 連結 [庫]() ，針對一般模式清單（例如 *日期*、 *電話號碼*、 *信用卡號碼*等）使用預先進行的模式清單範本。 

## <a name="proximity"></a>近似性 

「鄰近性說明類型可協助您的模型定義另一個資料的接近程度，以識別資料。 例如，在模型中，您已定義兩個說明，用以標示客戶的 *街道位址號碼* 和 *電話號碼*。 

此外，您也會注意到客戶的電話號碼一定會出現在街道位址號碼之前。 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond，WA 98034<br>

使用「鄰近性說明」來定義電話號碼說明的距離，以更好地識別檔中的街道位址號碼。

   ![鄰近性說明](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>何謂標記？

若要使用鄰近性說明類型，請瞭解 token 的含義，因為標記的數目就是近程說明如何測量對另一個說明之間的距離。  

Token 是連續的 span (不會有空格或標點符號) 字母和數位。 空格不是標記。 每個標點符號都是一個標記符。 下表顯示如何決定片語中的標記數目的一些範例。

|短語|標記數目|說明|
|--|--|--|
|`Dog`|1 |單一單字沒有標點符號或空格。|
|`RMT33W`|1 |記錄定位器編號。 它可能會有數位和字母，但沒有任何標點。|
|`425-555-5555`|5 |電話號碼。 每個標點符號都是單一標記，所以  `425-555-5555` 為5個權杖：<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7 |`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>設定鄰近性釋義類型

在此範例中，設定近程設定，讓我們能夠定義 *電話號碼* 說明的標記數目的範圍（來自 *街道位址號碼* 說明）。

您應該會看到最小範圍為 "0"，因為電話號碼與街道位址號碼之間沒有任何標記。

不過，範例檔中的一些電話號碼會附加 * (行動) *。

Nestor Wilke<br>
111-111-1111 (mobile) <br>
One Microsoft Way<br>
Redmond，WA 98034<br>

* (mobile) *中有三個權杖：

|短語|權杖計數|
|--|--|
|(|1 |
|移動|2 |
|)|3 |

將 [鄰近性] 設定設定為0到3的範圍。

   ![近程範例](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a>使用說明程式庫

雖然您可以手動新增各種模式清單值以供您的說明，但在說明程式庫中，使用預先建立的範本是很容易的。

例如，請使用已包含一些模式清單值的模式清單範本，而不是手動新增*日期*變化*的日期。*</br>

   ![說明程式庫](../media/content-understanding/explanation-template.png)</br>
 
說明程式庫包含許多常用的模式清單說明，包括：</br>

- 日期</br>
- 日期 (數值) </br>
- Time</br>
- 數字</br>
- 電話號碼</br>
- 郵遞區號</br>
- 句子的第一個單字</br>
- 信用卡</br>
- 社會安全號碼</br>

請注意，說明程式庫也包含片語清單說明的範本，包括：
- 句子結尾
- 貨幣

#### <a name="to-use-a-template-from-the-explanation-library"></a>使用說明程式庫中的範本

1. 從模型**訓練**頁面的 [**說明**] 區段中，選取 [**新增**]，然後選取 [**從範本**]。</br>

   ![從範本建立](../media/content-understanding/from-template.png)</br>

2.  在 [ **說明範本** ] 頁面上，選取您要使用的說明，然後選取 [ **新增**]。</br>

       ![選取範本](../media/content-understanding/phone-template.png)</br>

3. 您所選取之範本的資訊會顯示在 [ **建立說明** ] 頁面上。 如有需要，請編輯說明名稱，並在 [模式] 清單中新增或移除專案。 </br> 

   ![編輯範本](../media/content-understanding/phone-template-live.png)</br>

4. 完成時，請選取 [ **儲存**]。
