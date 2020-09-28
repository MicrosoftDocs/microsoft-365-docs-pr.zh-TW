---
title: 建立提取程式時利用字詞存放區分類
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
description: 在 Microsoft SharePoint Syntex 中的檔理解模型中建立提取程式時，利用字詞存放區分類。
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295774"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>建立提取程式時利用字詞存放區分類


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

當您在 SharePoint Syntex 中的檔理解模型中建立解壓縮程式時，您可以利用 [受管理的中繼資料服務](https://docs.microsoft.com/sharepoint/managed-metadata#terms) 字詞庫分類法，以顯示您提取之資料的慣用字詞。  

例如，您的模型會識別和分類所有上傳至文件庫的 **合約** 檔。  此外，此模型也會從每個合約中解壓縮 **合約服務** 值，並將其顯示在文件庫視圖中的一欄。 在合同中的各種合約服務值中，您公司不再使用的數個舊值，且已重新命名。 例如，所有對字詞 *設計*、 *圖形*或 *拓撲* 的合約服務的參考，都應該稱為 *創造性*。 當您的模型從合約檔中解壓縮一個過期的字詞時，您想要讓它在您的文件庫視圖中顯示目前的字詞創意。 在下列範例中，訓練模型時，我們看到一個範例檔會包含已過時的 *設計*術語。

   ![字詞庫](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a>字詞集合同義字 

字片語是在受管理的中繼資料服務術語存放區的 SharePoint 系統管理中心設定。 在下列範例中， *合約服務*字片語 [設定](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) 為包含許多字詞，包括 *創造性*。  它的詳細資料會顯示這項字詞具有三個同義字 (*設計*、 *圖形*和 *拓撲*) ，且同義字應轉譯成 *創造性*。

   ![字詞組](../media/content-understanding/term-store.png)</br>

<Mike，這裡是我無法確定如何描述這種情況的地方。  什麼動作會告訴模型當我建立提取器以提取及顯示合約服務欄時，該資料行如何「標示」如何使用受管理的中繼資料字片語進行創造性服務？ >

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a>設定受管理的元資料欄位的文件庫網站欄


   ![建立受管理的中繼資料](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a>另請參閱
[受管理的中繼資料簡介](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[建立提取程式](create-an-extractor.md)</br>
[建立受管理的中繼資料欄](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





