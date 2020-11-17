---
title: 文件瞭解概觀
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: 取得 Microsoft SharePoint Syntex 中文件瞭解的概覽。
ms.openlocfilehash: b26ed9a9ed9b8d1f332ccf14377660e634349b3d
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087364"
---
# <a name="document-understanding-overview"></a>文件瞭解概觀


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

文件瞭解使用人工智慧 (AI) 模型來自動分類檔案及擷取資訊。 它最適用於非結構化文件，如信件或合约。 這些文件必須具有可根據片語或模式識別的文字。 所識別的文字指定了檔案的類型（它的分類）和您想要擷取的內容（它的擷取器）。

> [!NOTE]
> 如需有關文件瞭解案例範例的詳細資訊，請參閱 [SharePoint Syntex 採用：入門指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example)。

文件瞭解模型是在一種稱為 *内容中心* 的 SharePoint 網站中建立和管理的。 當套用至 SharePoint 文件庫時，模型與一個具有存儲所擷取資訊的欄的內容類型相關聯。 您建立的內容類型儲存在 SharePoint 內容類型庫中。 您也可以選擇使用現有內容類型來使用其架構。

將 *分類器* 和 *擷取器* 新增至文件瞭解模型中，以執行以下動作： 

- 分類器用來識別和分類上傳至文件庫的文件。 例如，可以「訓練」分類器來識別上傳到文件庫的所有 *合同續約* 文件。 合同續約內容類型由您在建立分類器時定義。

- 擷取器從這些文件中選取資訊。 例如，對於文件庫中識別的所有合同續約文件，檢視中顯示的欄也顯示每個合同續約文件的 *服務開始日期* 和 *客戶*。 

您可以在模型中使用範例檔案來訓練和測試分類器和擷取器。 範例檔案向您的模型範例提供在嘗試從檔案中識別和擷取資料時要查找的內容。 例如，您會以貴公司使用的合同續約文件範例來訓練您的合同續約分類器和擷取器。 您也可以使用範例檔案來測試模型的有效性。

發佈模型之後，請使用內容中心將它套用到您有權存取的任何 SharePoint 文件庫。  



## <a name="see-also"></a>另請參閱
[建立分類器](create-a-classifier.md)

[建立擷取器](create-an-extractor.md)

[建立內容中心](create-a-content-center.md)

[建立表單處理模型](create-a-form-processing-model.md)

[套用模型](apply-a-model.md)   

[文件瞭解和表單處理模型之間的差異](difference-between-document-understanding-and-form-processing-model.md)
  
[表單處理概觀](form-processing-overview.md)
