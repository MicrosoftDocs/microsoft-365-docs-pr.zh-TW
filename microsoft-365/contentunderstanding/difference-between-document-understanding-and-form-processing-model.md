---
title: '檔瞭解和表單處理模型之間的差異 (預覽) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 說明文件瞭解和表單處理模型之間的主要差異。
ms.openlocfilehash: 7c480b91c1ddd75016b4bd35faa3d5692cacd103
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612735"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a>檔瞭解和表單處理模型之間的差異 (預覽) 

> [!Note] 
> 本文內容適用于 Project Cortex 私人預覽。 [進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。

專案 Cortex 中的內容瞭解可讓您識別和分類上載至 SharePoint 文件庫的檔，以及提取每個檔案的相關資訊。  例如，當檔案上傳至 SharePoint 文件庫時，識別為*購買訂單*的所有檔案都會以這種方式分類，並顯示在顯示它們的自訂文件庫視圖中。 此外，您可以從每個檔案中拉入特定資訊 (例如， *PO 號碼*和*合計*) ，並將其顯示在文件庫視圖中的欄中。 


內容瞭解可讓您建立*模型*，以識別及解壓縮您所需的資訊。  可使用的模型類型有兩種：

- [檔理解模型](document-understanding-overview.md)
- [表單處理模型](form-processing-overview.md)

雖然這兩種模型一般都使用相同的目的，但有一些重要差異會影響您可以選擇使用的專案。


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>結構化與非結構化及半結構化內容

使用檔理解模型來識別及提取非結構化檔中的資料，例如信件或合約，而您想要提取的文字實體會位於檔的句子或特定區域中。 例如，非結構化檔可以是以不同方式撰寫的合約更新信件。 不過，各項合約更新檔的本文中的資訊都是一致的，例如文字字串「服務的開始日期」，然後是實際的日期。   

使用表單處理模型來識別檔案，並從結構化或半結構化的檔（例如表單或發票）中提取資料，您可以在其中包含明確的索引鍵-值對 (例如， *Date： 10/1/2020*) * 或 table 資料。 舉例來說，表單處理的一個不錯的候選人是公司的訂單要求表單，用戶端需要在該表單中提供其資訊，以供位於檔版面配置相同區域中的特定欄位（例如*名稱*、*電話號碼*、*總成本*等）。 納稅表單是結構化檔的好例子。 

## <a name="where-they-are-created"></a>建立位置

檔理解模型是在 SharePoint 內容中心網站中建立及管理的。 您必須具有內容中心網站的存取權，才可建立檔理解模型，或將其中一項套用至 SharePoint 文件庫。 

當您建立檔理解模型時，會建立新的[SharePoint 內容類型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)儲存至 SharePoint 內容類型庫。 您也可以視需要使用現有的內容類型來定義模型。

表單處理模型是在 PowerApps [AI](https://docs.microsoft.com/ai-builder/overview)產生器中建立，但是會直接從 SharePoint 文件庫開始建立。 您必須在文件庫上啟用表單處理模型建立，使用者才可以為其建立表單處理模型，而管理員可以在內容瞭解管理設定中執行這項作業。 表單處理模型會使用 PowerAutomate 流程，在將檔案上傳至文件庫時處理檔案。

表單處理模型也會建立新的[SharePoint 內容類型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)，也就是儲存在 SharePoint 內容類型庫中。

## <a name="where-they-can-be-applied"></a>可以套用的位置

檔理解模型可以套用到您具有存取權的不同 SharePoint 文件庫。 您可以使用內容中心，不只是建立檔理解模型，也可以將它套用至不同文件庫。 內容中心針對檔瞭解模型的使用方式及套用位置，提供了更集中的控制，因為這項資訊必須匯總至內容中心。

表單處理模型目前只能套用到其建立所在的 SharePoint 文件庫。 這可讓具有網站存取權的任何授權使用者建立表單處理模型。




 ## <a name="see-also"></a>另請參閱
[訓練：使用 AI 產生器改進商務效能](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[建立分類器](create-a-classifier.md)</br>
[建立提取程式](create-an-extractor.md)</br>
[套用檔理解模型](apply-a-model.md)</br>
[建立表單處理模型](create-a-form-processing-model.md)</br>



  
  



