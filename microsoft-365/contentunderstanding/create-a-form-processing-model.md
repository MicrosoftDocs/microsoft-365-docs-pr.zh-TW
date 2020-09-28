---
title: 建立表單處理模型
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
description: 在 Microsoft SharePoint Syntex 中建立表單處理模型。
ms.openlocfilehash: f61dbad837173c412daefb7285c4abff10a01817
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295475"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中建立表單處理模型

本文內容適用于 Project Cortex 私人預覽。 [進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。

使用 [AI Builder](https://docs.microsoft.com/ai-builder/overview) -Microsoft PowerApps 專案 Cortex 中的功能使用者可以直接從 SharePoint 文件庫建立 [表單處理模型](form-processing-overview.md) 。 

建立表單處理模型包含下列專案：
 - 步驟1：建立從處理模型建立內容類型
 - 步驟2：新增及分析範例檔案
 - 步驟3：選取表單欄位
 - 步驟4：訓練及測試您的模型
 - 步驟5：發佈您的模型
 - 步驟6：使用您的模型

## <a name="requirements"></a>需求

您只能在啟用它的 SharePoint 文件庫中建立表單處理模型。 如果已啟用表單處理，您可以在文件庫中的 [**自動化**] 功能表上看到 [ **AI** **產生器] 的 [建立表單處理模型]** 。  如果您需要在文件庫上啟用處理，必須與 SharePoint 管理員聯繫。

 ![建立 AI 產生器模型](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a>步驟1：建立表單處理模型

建立表單處理模型的第一個步驟是將其命名並建立新的內容類型，並為其建立新的文件庫視圖。

1. 從文件庫中，選取 [ **自動化** ] 功能表，選取 [ **AI**產生器]，然後選取 [ **建立表單處理模型**]。

    ![建立模型](../media/content-understanding/create-ai-builder-model.png)</br>

2. 在 [ **新增表單處理模型** ] 窗格的 [  **名稱** ] 欄位中，輸入模型 (的名稱，例如，[ *採購訂單* ]) 。

    ![新表單處理模型](../media/content-understanding/new-form-model.png)</br> 

3. 當您建立表單處理模型時，會建立新的 SharePoint 內容類型。 SharePoint 內容類型代表具有共同特性並共用該特定內容之一組欄或中繼資料屬性的檔類別。 SharePoint 內容類型是透過 [內容類型庫]()進行管理。

    如果您想要將此模型對應至 SharePoint 內容類型庫中的現有內容類型，以使用其架構，請選取 [ **高級設定** ]。 

4. 您的模型會在文件庫中為解壓縮的資料建立新的視圖。 如果您不想讓它成為預設視圖，請取消選取 **[將此視圖設定為預設值**]。

5. 選取 [建立]****。

## <a name="step-2-add-and-analyze-documents"></a>步驟2：新增及分析檔

在您建立新的表單處理模型之後，瀏覽器便會開啟新的 PowerApps AI Builder 表單處理模型頁面。 在此頁面上，您可以新增及分析您的範例檔。 </br>

> [!NOTE]
> 在尋找要使用的範例檔案時，請參閱 [表單處理模型輸入檔需求和優化秘訣](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)。 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. 選取 [ **新增檔** ] 以開始加入分析的範例檔，以決定可提取的命名值配對。 然後，您可以選擇 [ **從本機儲存區上傳**]、[ **SharePoint**] 或 [ **Azure Blob 儲存區**]。 您至少需要使用五個檔案進行訓練。

2. 新增檔案之後，請選取 [ **分析** ]，檢查是否有任何常見的資訊是檔案。 這可能需要數分鐘才能完成。</br> 
 
    ![分析檔](../media/content-understanding/analyze.png)</br> 

3. 在分析檔案之後，在 [ **選取您要儲存的表單欄位** ] 頁面中，選取檔案以查看偵測到的欄位。</br>

    ![選取表單域](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>步驟3：選取表單欄位

分析檔中的欄位後，您現在可以看到找到的欄位，並識別您想要儲存的欄位。 儲存的欄位會顯示為模型的文件庫視圖中的欄，並顯示每個檔中解壓縮的值。

1. 下一個頁面會顯示其中一個範例檔案，並會反白顯示系統自動偵測到的所有一般欄位。 </br>

    ![選取欄位頁面](../media/content-understanding/select-fields-page.png)</br> 

2. 選取您要儲存的欄位，然後選取核取方塊以確認您的選取範圍。 例如，在 [採購訂單模型] 中，選擇選取 [ *日期*]、[ *PO*] 和 [ *總計* ] 欄位。  請注意，您也可以選擇重新命名欄位。 </br>

    ![選取 PO#](../media/content-understanding/po.png)</br> 

3. 若 analysis 未偵測到欄位，您仍然可以選擇新增欄位。 反白顯示您想要解壓縮的資訊，然後在 [名稱] 方塊中，輸入您想要的名稱。 然後選取 [] 核取方塊。 請注意，您需要在剩餘的範例檔案中確認未檢查的欄位。

4. 選取您要儲存的欄位後，請按一下 [ **確認欄位** ]。 </br>
 
    ![選取欄位後確認欄位](../media/content-understanding/confirm-fields.png)</br> 
 
5. 在 [ **選取您要儲存的表單欄位** ] 頁面上，會顯示您所選取的欄位數目。 選取 **[完成]**。

## <a name="step-4-train-and-test-your-model"></a>步驟4：訓練及測試您的模型

選取您要儲存的欄位後，[ **模型摘要** ] 頁面可讓您訓練及測試模型。

1. 在 [ **模型摘要** ] 頁面上，儲存的欄位將會顯示在 [ **選取的欄位** ] 區段中。 選取 [ **訓練** ]，以在您的範例檔案上開始訓練。 請注意，這可能需要數分鐘才能完成。</br>

     ![選取欄位訓練](../media/content-understanding/select-fields-train.png)</br> 

2. 當您看到訓練已完成的通知時，請選取 [ **移至詳細資料] 頁面**。 

3. 在 [ **模型詳細資料** ] 頁面上，您可以選擇 [ **快速測試**] 以測試模型的運作方式。 這可讓您將檔案拖放至頁面，查看是否偵測到欄位。

    ![確認欄位](../media/content-understanding/select-fields-train.png)</br> 

2. 當您看到訓練已完成的通知時，請選取 [ **移至詳細資料] 頁面**。 

3. 在 [ **模型詳細資料** ] 頁面上，選擇 [ **快速測試**] 以測試模型的運作方式。 這可讓您將檔案拖放至頁面，查看是否偵測到欄位。

## <a name="step-5-publish-your-model"></a>步驟5：發佈您的模型

1. 如果您對模型結果滿意，請選取 [ **發佈** ] 以供使用。

2. 在發佈模型之後，請選取 [ **使用模型**]。 這會建立 PowerAutomate 流程，該流程可以在您的 SharePoint 文件庫中執行，並提取已在模型中識別的欄位，然後選取 [ **建立流程**]。
  
3. 完成後，您會看到訊息 **您的流程已成功建立**。
 
## <a name="step-6-use-your-model"></a>步驟6：使用您的模型

在發佈模型並建立其 PowerAutomate 流程之後，您可以在 SharePoint 文件庫中使用您的模型。

1. 在發佈模型之後，請選取 [ **移至 SharePoint** ] 以移至您的文件庫。

2. 在文件庫模型視圖中，請注意，您所選取的欄位現在會顯示為欄。</br>

    ![套用文件庫模型](../media/content-understanding/doc-lib-view.png)</br> 

3. 請注意，[ **檔** ] 旁邊的資訊連結會說明表單處理模型套用至此文件庫。

    ![Info 按鈕](../media/content-understanding/info-button.png)</br>  

4. 將檔案上傳至文件庫。 模型識別為其內容類型的任何檔案會列出您的視圖中的檔案，並顯示資料行中解壓縮的資料。</br>

    ![完成](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a>另請參閱
  
[電源自動化檔](https://docs.microsoft.com/power-automate/)</br>
[訓練：使用 AI 產生器改進商務效能](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
