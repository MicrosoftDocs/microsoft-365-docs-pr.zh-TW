---
title: 建立分類器
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何建立分類器
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294899"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中建立分類器

本文內容適用于 Project Cortex 私人預覽。 [進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

分類器是一種模型，可讓您用來自動化檔案類型的身分識別和分類。 例如，您可能想要識別所有已新增至文件庫的 *合約更新* 檔，如下圖所示。

![合同更新檔](../media/content-understanding/contract-renewal.png)

建立分類程式可讓您建立新的 [SharePoint 內容類型](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) ，將會與模型產生關聯。

建立分類器時，您必須建立 *說明* 以定義模型。 這可讓您記下您預期會始終如一地找到這種檔案類型的常見資料。 

使用檔案類型的範例 ( "範例檔案" ) 以 "訓練" 您的模型來識別具有相同內容類型的檔案。

若要建立分類符，您必須：
1. 命名模型。
2. 新增您的範例檔案。
3. 為範例檔案加上標籤。
4. 建立說明。
5. 測試您的模型。

> [!NOTE]
> 雖然您的模型使用分類器來識別和分類檔案類型，您也可以選擇從模型所識別的每個檔案中提取特定的資訊片段。 建立 **解壓縮** 程式以新增至您的模型。 請參閱 [建立提取程式](create-an-extractor.md)。

## <a name="name-your-model"></a>命名模型

建立模型的第一個步驟是為其命名：

1. 從內容中心選取 [ **新增**]，然後 **建立模型**。
2. 在 [ **新增檔瞭解模型** ] 窗格的 [ **名稱** ] 欄位中，輸入模型的名稱。 例如，如果您想要識別合同更新檔，您可以命名模型 *合約更新*。
3. 	選擇 **[建立]**。 這會為模型建立首頁。</br>

    ![分類器模型首頁](../media/content-understanding/model-home.png)

當您建立模型時，您也是建立新的 SharePoint 內容類型。 SharePoint 內容類型代表具有共同特性並共用該特定內容之一組欄或中繼資料屬性的檔類別。 SharePoint 內容類型是透過 [內容類型庫](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f)進行管理。 在此範例中，當您建立模型時，會建立新的 *合約更新* 內容類型。

如果您想要將此模型對應至 SharePoint 內容類型庫中的現有內容類型，以使用其架構，請選取 [ **高級設定** ]。 請注意，雖然您可以使用現有的內容類型來利用其架構來協助識別和分類，但您仍然需要訓練模型，以從識別的檔案提取資訊。</br>

![進階設定](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>新增您的範例檔案

在模型首頁上，新增您所需的範例檔案，以協助訓練模型識別檔案類型。 </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> 您應該針對分類器和 [提取程式訓練](create-an-extractor.md)使用相同的檔案。 您可以選擇稍後新增更多，但通常您會新增一組完整的範例檔案。 標示部分以訓練模型，並測試其餘未標記的專案，以評估模型健身。 

針對您的訓練集，您想要使用正和負的範例：
- 肯定範例：代表檔案類型的檔。 這些包含的字串和資訊永遠都屬於這種檔案類型。
- 負數範例：不代表檔案類型的檔。 這些是遺失的字串和資訊，必須存在於這種檔案類型中。

請務必使用至少五個正值，以及至少一個否定性的範例訓練您的模型。  您想要建立其他專案，以在訓練程式之後測試您的模型。

若要新增範例檔案：

1. 從模型首頁的 [ **建立範例文件庫** ] 磚中，按一下 [ **新增**檔案]。
2. 在 [ **選取模型的範例** 檔案] 頁面上，從內容中心的範例檔案庫中選取範例檔案。 如果您還沒有上傳它們，請按一下 [ **上傳** ]，將其移至範例檔案庫中，選擇立即上傳。
3. 選取用來訓練模型的範例檔案之後，請按一下 [ **新增**]。

    ![選取範例檔案](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>標記範例檔案

在新增範例檔案之後，您必須將它們標示為正數或負數範例。

1. 從模型首頁的 [ **分類檔案及執行訓練** ] 磚上，按一下 [ **訓練分類器**]。
   這會顯示 [標籤] 頁面，顯示範例檔案的清單，第一個檔案會顯示在檢視器中。
2. 在第一個範例檔案頂端的檢視器中，您應該會看到文字，詢問檔案是否為您剛才建立的模型範例。 如果是正範例，請選取 **[是]**。 如果是負數範例，請選取 [ **否**]。
3. 從左側的 [已 **標記的範例** ] 清單中，選取您要做為範例的其他檔案，然後將它們標示。 

    ![分類器首頁](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> 標籤至少五個正範例，另一個為負的範例。 

## <a name="create-an-explanation"></a>建立說明

下一步是讓您在訓練頁面上建立說明。 說明可協助模型瞭解如何辨識檔。 例如，合約更新檔一定會包含 *其他披露文字字串的要求* 。

> [!Note]
> 與擷取器搭配使用時，說明您要從檔中解壓縮的字串。 

若要建立說明：

1. 從模型首頁，選取 [ **訓練** ] 索引標籤以移至 [訓練] 頁面。
2. 在 [訓練] 頁面的 [ **訓練有素** 的檔案] 區段中，您應該會看到先前標示的範例檔案清單。 從清單中選取其中一個正的檔案，然後在檢視器中顯示。
3. 在 [說明] 區段中，選取 [ **新增** ]，然後選取 [ **空白**]。
4. 在 [ **建立說明** ] 頁面上：</br>
    a. 輸入 **名稱** (例如，"披露 Block" ) 。</br>
    b. 選取 **類型**。 若為範例，請選取 [ **片語] 清單**，因為您新增了文字字串。</br>
    c. 在 [ **請輸入此文字** ] 方塊中，輸入字串。 在範例中，新增「要求其他披露」。 若字串必須區分大小寫，您可以選取 [區分 **大小寫** ]。</br>
    d. 按一下 **[儲存]**。

    ![建立說明](../media/content-understanding/explanation.png) 
    
 
5. 模型現在會檢查您建立的釋義是否足夠好，可正確識別其餘標示的範例檔案，如正值及負數範例。 在 [訓練有素的檔案] 區段中，檢查訓練已經完成之後，查看結果的 **評估** 欄。 如果您建立的說明足以符合您標示為正或負數的專案，則檔案會顯示 [ **符合**專案的值]。

    ![符合值](../media/content-understanding/match.png) 

如果您收到的標籤檔 **不相符** ，您可能需要建立其他說明，以提供模型詳細資訊，以識別檔案類型。 如果發生這種情況，請按一下檔案，以取得未相符之原因的詳細資訊。

## <a name="test-your-model"></a>測試您的模型

如果您收到的標記的範例檔案的相符，您現在可以在其餘未標記的範例檔案上測試模型。

1. 從模型的首頁中，選取 [ **測試** ] 索引標籤。 這會在未標記的範例檔案上執行模型。
2. 在 [ **測試** 檔案] 清單中，會顯示您的範例檔案，並顯示模型是否預測為正值或負數。 使用此資訊有助於決定您的分類程式在識別檔時的效能。

    ![測試未標記的檔案](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a>另請參閱
[建立提取程式](create-an-extractor.md)</br>
[檔理解概述](document-understanding-overview.md)</br>
[建立表單處理模型](create-a-form-processing-model.md)</br>
[套用模型](apply-a-model.md) 
