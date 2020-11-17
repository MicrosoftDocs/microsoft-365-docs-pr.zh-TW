---
title: 建立分類器
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: 了解如何建立分類器
ms.openlocfilehash: 478b4253f7bb888323c2a873f3ab295cc841e193
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087676"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中建立分類器


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

分類器是一種模型類型，可用來自動化文件類型的識別和分類。 例如，您可能想要找出新增至文件庫的所有 *合約續約* 文件，例如如下圖所示。

![合約續約文件](../media/content-understanding/contract-renewal.png)

建立分類器可讓您建立將與該模型相關聯的新 [SharePoint 內容類型](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)。

建立分類器時，您必須建立 *說明* 以定義模型。 這可讓您記錄預期會持續發現此文件類型的常見資料。 

使用文件類型的範例 (「範例檔」) 來「訓練」您的模型，以找出擁有相同內容類型的檔案。

若要建立分類器，您必須：
1. 為模型命名。
2. 新增範例檔案。
3. 為範例檔案加上標籤。
4. 建立說明。
5. 測試您的模型。

> [!NOTE]
> 當您的模型使用分類器來識別和分類文件類型時，您也可以選擇從模型所識別的每個檔案中提取特定資訊。 方法是建立要新增至模型的 **[擷取器]**。 請參閱[建立擷取器](create-an-extractor.md)。

## <a name="name-your-model"></a>為模型命名

建立模型的第一個步驟是為其命名：

1. 從 [內容中心] 選取 **[新增]**，然後選取 **[建立模型]**。
2. 在 **[新增文件瞭解模型]** 窗格的 **[名稱]** 欄位中，輸入模型的名稱。 例如，如果您想要識別合約續約文件，可以將模型命名為 *[合約續約]*。
3. 選擇 **[建立]**。 這會為模型建立首頁。</br>

    ![分類器模型首頁](../media/content-understanding/model-home.png)

當您建立模型時，您也會建立新的網站內容類型。 內容類型代表具有共同特徵及共用特定內容的欄或中繼資料屬性集合的文件類別。 透過[內容類型資源庫](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f)管理 SharePoint 內容類型。 在此範例中，當您建立模型時，您會建立新的 *[合約續約]* 內容類型。

如果您想要將這個模型對應到 SharePoint 內容類型資源庫中現有的企業內容類型以使用其結構描述，請選取 **[進階設定]**。 企業內容類型儲存在 SharePoint 系統管理中心的內容類型中樞中，並與租用戶中的所有網站整合。 請注意，雖然您可以使用現有的內容類型來運用其結構描述以協助識別和分類，您仍然需要訓練模型，以從所識別的檔案擷取資訊。</br>

![進階設定](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>新增範例檔案

在模型首頁上，新增您的範例檔案，您需要協助訓練模型以識別您的文件類型。 </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> 您應將相同檔案用於分類器和[擷取器訓練](create-an-extractor.md)。 您隨時都可以選擇稍後再新增，但通常您會新增一整套範例檔案。 標記一些以訓練您的模型，並測試其餘未標記的項目，以評估模型適用性。 

針對訓練集，您會想要使用正面和負面的範例：
- 正面範例：代表檔案類型的文件。 這些包含的字串和資訊永遠存在於這種文件類型。
- 負面範例：任何不代表您要分類之文件的其他文件。 

請務必使用至少五個正面範例，以及至少一個負面範例來訓練您的模型。  您想要在訓練程序之後建立其他範本來測試模型。

若要新增範例檔案：

1. 在模型首頁上的 **[新增範例檔案]** 磚中，按一下 **[新增檔案]**。
2. 在 **[選取您模型的範例檔案]** 頁面上，選取內容中心中 [訓練檔] 文件庫的範例檔案。 如果您還沒有將檔案上傳到該處，請按一下 **[上傳]**，將檔案複製到 [訓練檔] 文件庫，選擇立即上傳。
3. 選取您要用來訓練模型的範例檔案之後，請按一下 **[新增]**。

    ![選取範例檔案](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>為範例檔案加上標籤

新增範例檔案之後，您必須將其標記為正面或負面範例。

1. 在模型首頁的 **[分類檔案和執行訓練]** 磚中，按一下 **[訓練分類器]**。
   這會顯示 [標籤] 頁面，該頁面顯示範例檔案清單，並在檢視器中顯示第一個檔案。
2. 在第一個範例檔案頂端的檢視器中，您應該會看到一些文字，詢問該檔案是否為您剛建立的模型範例。 如果是正面範例，請選取 **[是]**。 如果是負面範例，請選取 **[否]**。
3. 在左邊的 **[已標記範例]** 清單中，選取您想要做為範例的其他檔案，然後為其標記。 

    ![分類器首頁](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> 至少標記五個正面範例。 您也必須標記至少一個負面範例。 

## <a name="create-an-explanation"></a>建立說明。

下一個步驟是在 [訓練] 頁面建立說明。 說明可協助模型瞭解如何辨識文件。 例如，合約續約文件始終包含 *[要求其他公開揭示]* 文字字串。

> [!Note]
> 與擷取程式搭配使用時，說明會識別您要從文件中提取的字串。 

若要建立說明：

1. 從模型首頁中，選取 **[訓練]** 索引標籤，以移至 [訓練] 頁面。
2. 在 [訓練] 頁面的 **[已訓練檔案]** 區段中，您應該會看到您之前已標記的範例檔案清單。 從清單中選取其中一個正向檔案，它會顯示在檢視器中。
3. 在 [說明] 區段中，選取 **[新增]**，然後選取 **[空白]**。
4. 在 **[建立說明]** 頁面：</br>
    a. 輸入 **[名稱]** (例如「公開揭示封鎖」)。</br>
    b. 選取 **[類型]**。 針對此範例，請選取 **[片語清單]**，因為您新增的是文字字串。</br>
    c. 在 **[在這裡輸入]** 方塊中，輸入字串。 針對此範例，請新增「要求其他公開揭示」。 如果字串必須區分大小寫，您可以選取 **[區分大小寫]**。</br>
    d. 按一下 **[儲存]**。

    ![建立說明](../media/content-understanding/explanation.png) 
    
5. 現在，[內容中心] 會檢查您所建立的說明是否夠完整，以便將剩餘的已標記範例檔案正確識別為正面和負面範例。 訓練完成之後，在 [已訓練檔案] 區段中檢查 **[評估]** 資料行，以查看結果。 如果您建立的說明足以符合您標記為正面或負面的結果，檔案就會顯示 **[符合]** 的值。

    ![符合值](../media/content-understanding/match.png) 

如果您在已標記檔案上接收到 **[不符合]**，您可能需要建立額外的說明，以提供模型更多資訊來識別文件類型。 如果發生這種情況，請按一下檔案，以取得為什麼發生不相符的詳細資訊。

## <a name="test-your-model"></a>測試您的模型

如果您在已標記的範例檔案上收到符合，您現在可以在尚未顯示模型的剩餘未標記範例檔案上測試模型。  這是一個選用但有用的步驟，可透過在模型以前從未見過的檔案中進行測試來評估模型的「適合性」或就緒狀態。

1. 從模型首頁中，選取 **[測試]** 索引標籤。這會在未標記的範例檔案上執行模型。
2. 在 **[測試檔案]** 清單中，您的範例檔案會呈現並顯示模型預測其為正面或負面範例。 使用這項資訊可協助您判斷分類器的效能，以找出您的文件。

    ![測試未標記的檔案](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a>另請參閱
[建立擷取器](create-an-extractor.md)

[文件瞭解概觀](document-understanding-overview.md)

[說明類型](explanation-types-overview.md)

[套用模型](apply-a-model.md) 
