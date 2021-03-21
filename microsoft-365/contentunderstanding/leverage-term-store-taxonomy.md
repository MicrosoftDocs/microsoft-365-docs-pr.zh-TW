---
title: 在建立擷取器時運用字詞庫分類法
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 在 Microsoft SharePoint Syntex 中建立文件瞭解模型時，使用字詞庫分類法。
ms.openlocfilehash: b8dfc028e0a18f3345fec466ec5e0079ed2d11ce
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925341"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>在建立擷取器時運用字詞庫分類法

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

當您使用 SharePoint Syntex 中的文件瞭解模型來建立擷取器時，可以利用[字詞庫](/sharepoint/managed-metadata)中的全域字詞組來顯示所選取資料的首選字詞。  

舉例來說，您的模型識別並分類上傳至文件庫的所有 **[合約]** 文件。  此外，模型也會從每個合約擷取 **[合約服務]** 值，並將它顯示在文件庫檢視的欄中。 在合於中的各種合約服務值中，貴公司已不再使用並重新命名了數個舊值。 例如，所有提及 *「設計」*、*「圖形」* 或 *「地形」* 契约服務的條款現在都應該稱為 *「創造性」*。 每當您的模型從合約文件中選取過期的字詞時，您希望它在庫檢視中顯示目前字詞 「創造性」。 在下列範例中，在訓練模型時我們看到其中一個範例檔包含過期的字詞 *「設計」*。

   ![字詞庫](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a>在您的擷取器中使用受管理的中繼資料欄

在 SharePoint 系統管理中心的 [受管理的中繼資料] 服務 (MMS) 字詞庫中設定字詞組。 在下列範例中，*[合約服務]* [字詞組](/sharepoint/managed-metadata#term-set) 設定為包含數個字詞，包括 *「創造性」*。  它的詳細資料表明這個字詞有三個同義字（*「設計」*、*「圖形」* 和 *「地形」*），這些同義詞應該被翻譯成 *「創造性」*。 

   ![字詞組](../media/content-understanding/term-store.png)</br>

您可能會想要在字詞組中使用同義字的原因有很多。 例如，可能存在過期字詞、重新命名的字詞或組織部門之間在命名方面的差异。

若要使受管理的中繼資料欄位可供您在模型中建立擷取器時使用，您需要[將其添加為受管理的中繼資料網站欄](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f)。 新增網站欄後，您可以在建立模型擷取器時進行選取。

   ![合約服務](../media/content-understanding/contract-services.png)</br>


將模型套用至文件庫後，當文件上載到庫時，當擷取器找到任何同義字值（*「設計」*、*「圖形」* 和 *「地形」*）時，*創意服務* 欄將顯示首選字詞（*「創造性」*）。

   ![合約服務欄](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a>另請參閱
[受管理的中繼資料簡介](/sharepoint/managed-metadata#terms)

[建立擷取器](create-an-extractor.md)

[建立受管理的中繼資料欄](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)