---
title: '建立分類器 (預覽) '
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
description: 瞭解如何建立分類器
ms.openlocfilehash: 088770ace8914b583b184c78c3ce110d9d68b4c7
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612605"
---
# <a name="create-a-classifier-preview"></a>建立分類器 (預覽) 

> [!Note] 
> 本文內容適用于 Project Cortex 私人預覽。 [進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

分類器是一種類型的模型，可自動化檔案類型的識別和分類。 例如，您可能想要識別新增至文件庫的所有*合約更新*檔，如下所示。

![合同更新檔](../media/content-understanding/contract-renewal.png)

建立分類器將會建立新的[SharePoint 內容類型](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)，將會與模型產生關聯。

建立分類器時，您需要建立*說明*，以協助您在此檔案類型的情況下，透過注意您預期會發現的常見資料來定義模型。 

您可以使用檔案類型的範例 ( 「範例檔案」 ) ，協助您 "訓練" 您的模型來識別具有相同內容類型的檔案。

若要建立分類符，您必須：
1. 命名模型
2. 新增您的範例檔案
3. 標記範例檔案
4. 建立說明
5. 測試您的模型 

> [!Note]
> 雖然您的模型使用分類器來識別和分類檔案類型，您也可以選擇從模型所識別的每個檔案中提取特定的資訊片段。 若要執行此動作，您可以建立要新增至模型的**解壓縮**程式，並在 [[建立解壓縮程式](create-an-extractor.md)] 中加以說明。

## <a name="name-your-model"></a>命名模型

第一步是在內容中心建立模型，其名稱如下：

1. 在內容中心，按一下 [**新增**]，然後按一下 [**建立模型**]。
2. 在 [**新增檔瞭解模型**] 窗格的 [**名稱**] 欄位中，輸入模型的名稱。 在我們的範例中，如果我們想要識別合同更新檔，我們可以命名此模型*合約更新*。
3. 按一下 [建立]****。 這將會為模型建立首頁。</br>

    ![分類器模型首頁](../media/content-understanding/model-home.png)

當您建立模型時，會建立新的 SharePoint 內容類型。 SharePoint 內容類型代表具有共同特性並共用該特定內容之一組欄或中繼資料屬性的檔類別。 SharePoint 內容類型是透過[內容類型庫]()進行管理。 在我們的範例中，當我們建立模型時，我們會建立新的*合約更新*內容類型。

如果您想要將此模型對應至 SharePoint 內容類型庫中的現有內容類型，以使用其架構，請選取 [**高級設定**]。 請注意，雖然您可以使用現有的內容類型來利用其架構來協助識別和分類，但您仍然需要訓練模型，以從識別的檔案提取資訊。</br>

![進階設定](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>新增您的範例檔案

在模型首頁上，您可以新增您所需的範例檔案，以協助訓練模型識別檔案類型。 </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> 分類器和[提取程式訓練](create-an-extractor.md)都應該使用相同的檔案。 您可以選擇稍後新增更多，但通常您應該新增一組完整的範例檔案。 您將會標示部分以訓練模型，並測試其餘未標記的模型，以評估模型健身。 

針對您的訓練集，您會想要使用正的範例和消極的範例：
- 肯定範例：代表檔案類型的檔。 它們包含的字串和資訊永遠都屬於這種檔案類型。
- 負數範例：不代表檔案類型的檔。  它們遺漏的字串和資訊需要存在於這種檔案類型中。

您至少要使用五個正的範例和一個負數範例來訓練您的模型。  您會想要有其他的考試之後測試您的模型。

若要新增範例檔案：

1. 在模型首頁上，按一下 [**組建範例文件庫**] 磚中的 [**新增**檔案]。
2. 在 [**選取模型的範例**檔案] 頁面上，從內容中心的範例檔案庫中選取範例檔案。 如果您還沒有上傳這些檔案，您可以按一下 [**上傳**]，將其移至範例檔案庫。
3. 選取用來訓練模型的範例檔案之後，請按一下 [**新增**]。

    ![選取範例檔案](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>標記範例檔案

在新增範例檔案之後，您必須將它們標為正範例或負數範例。

1. 在模型首頁上，按一下 [**分類檔案及執行訓練**] 磚上的 [**訓練分類器**]。
   這會顯示 [標籤] 頁面，顯示範例檔案的清單，第一個檔案會顯示在檢視器中。
2. 在檢視器中第一個範例檔案的上方，您會看到文字詢問您的檔案是否為您剛才建立的模型範例。 如果是正範例，請選取 **[是]**。 如果是負數範例，請選取 [**否**]。
3. 從左側的 [已**標記的範例**] 清單中，選取您要做為範例的其他檔案，並將它們標示好。 

    ![分類器模型首頁](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> 標籤至少五個正範例，另一個為負的範例。 

## <a name="create-an-explanation"></a>建立說明

下一步是在訓練頁面上建立說明。  說明是協助模型瞭解如何辨識此檔的提示或線索。 例如，我們的合約更新檔一定會包含*額外披露文字字串的要求*。

> [!Note]
> 與擷取器搭配使用時，說明是用來識別您想要從檔中解壓縮的字串。 

若要建立說明：

1. 在模型首頁上，按一下 [**火車**] 索引標籤以移至 [訓練] 頁面。
2. 在 [訓練] 頁面的 [**訓練有素**的檔案] 區段中，您將會看到您先前已標示的範例檔案清單。 從清單中選取其中一個正檔，它會顯示在檢視器中。
3. 在 [說明] 區段中，按一下 [**新增**]，然後按一下 [**空白**]。
4. 在 [**建立說明**] 頁面上：</br>
    a. 輸入**名稱** (例如，"披露 Block" ) 。</br>
    b. 選取**類型**。 在我們的範例中，我們會選取**片語清單**，因為我們會加入文字字串。</br>
    c. 在 [**請輸入此文字**] 方塊中，輸入字串。  在我們的範例中，我們將新增「要求其他披露」。 若字串必須區分大小寫，您可以選取 [區分**大小寫**]。</br>
    d. 按一下 [儲存]****。

    ![建立說明](../media/content-understanding/explanation.png) 
    
 
5.  模型現在會檢查您建立的釋義是否足夠好，以找出您的剩餘標記範例檔案正確，如正值及負數範例。 在 [訓練有素的檔案] 區段中，檢查訓練**值**欄之後，查看結果。  如果您建立的釋義足以符合為 (正值或負數) 所做的標記，則檔案會顯示**符合**專案的值。

    ![建立說明](../media/content-understanding/match.png) 

如果您在已標示的檔案上收到**不一致**的資訊，您可能需要建立額外的說明，以提供模型以進一步識別檔案類型的資訊。 您可以按一下檔案，以取得為何不符的詳細資訊。

## <a name="test-your-model"></a>測試您的模型

如果您在已標示的範例檔案上收到相符的檔，您現在可以在其餘未標記的範例檔案上測試您的模型。

1. 在模型首頁上，按一下 [**測試**] 索引標籤。 這會在未標記的範例檔案上執行該模型。
2. 在 [**測試**檔案] 清單中，您的範例檔案會顯示，而且會顯示模型是否預測為正數或負數範例。 您可以使用這項資訊來協助您判斷您的分類器在識別檔時的效能。

    ![測試未標記的檔案](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a>另請參閱
[建立提取程式](create-an-extractor.md)</br>
[檔理解概述](document-understanding-overview.md)</br>
[建立表單處理模型](create-a-form-processing-model.md)</br>
[套用模型](apply-a-model.md) 




