---
title: '檔理解一覽 (預覽) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 深入瞭解 Project Cortex 中的檔知識。
ms.openlocfilehash: c1e4092164ee96d4f244f10be9ebab62a2c8da5b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950045"
---
# <a name="document-understanding-overview-preview"></a>檔理解一覽 (預覽) 
> [!Note] 
> 專案 Cortex 目前在預覽中。 [進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

檔瞭解使用 AI 模型自動進行檔案分類和資訊提取。 它最適合使用非結構化檔，如信件或合約。 檔應有文字可根據片語或模式識別。 識別的文字可以指定其 (分類的檔案類型) 以及您想提取 (其擷取器) 的內容。

檔理解模型是在一種稱為內容中心的 SharePoint 網站中建立及管理。 套用至 SharePoint 文件庫時，模型會與內容類型相關聯，該內容類型具有用來儲存提取資訊的欄。 您建立的內容類型會儲存在 SharePoint 內容類型庫中。 您也可以選擇使用現有的內容類型，以便使用其架構。

您可以將 *分類* 器和 *擷取器* 新增至檔理解模型，以執行下列作業： 

- 分類器是用來識別和分類上傳至文件庫的檔。 例如，分類器可以「訓練」，識別所有上傳至文件庫的 *合約更新* 檔。 當您建立分類器時，即會定義「合約更新」內容類型。

- 從這些檔中擷取器提取資訊。 例如，針對文件庫中識別的所有合約更新檔，欄會顯示在您的視圖中，也會顯示每個合約更新檔的 *服務開始日期* 和  *用戶端* 。 

您可以使用範例檔案訓練及測試模型中的分類器和擷取器。 範例檔案會提供您的模型範例，說明在嘗試識別及解壓縮資料時所要尋找的專案。 例如，您可以使用貴公司所用的合約更新檔範例，訓練您的合約更新類元和擷取器。 您也可以使用範例檔來測試模型的效能。

在發佈模型之後，請使用內容中心將其套用至您具有存取權的任何 SharePoint 文件庫。  


## <a name="see-also"></a>另請參閱
[建立分類器](create-a-classifier.md)</br>
[建立提取程式](create-an-extractor.md)</br>
[建立內容中心](create-a-content-center.md) 
[建立表單處理模型](create-a-form-processing-model.md)</br>
[套用模型](apply-a-model.md)   
[檔瞭解和表單處理模型之間的差異](difference-between-document-understanding-and-form-processing-model.md)  
[表單處理概覽](form-processing-overview.md)




