---
title: 建立分類器
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 了解如何建立分類器
ms.openlocfilehash: 948ece1a19b7e6049167c373b3200efd316a60cd
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338634"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="c99ac-103">在 Microsoft SharePoint Syntex 中建立分類器</span><span class="sxs-lookup"><span data-stu-id="c99ac-103">Create a classifier in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="c99ac-104">分類器是一種模型類型，可用來自動化文件類型的識別和分類。</span><span class="sxs-lookup"><span data-stu-id="c99ac-104">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="c99ac-105">例如，您可能想要找出新增至文件庫的所有*合約續約*文件，例如如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="c99ac-105">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![合約續約文件](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="c99ac-107">建立分類器可讓您建立將與該模型相關聯的新 [SharePoint 內容類型](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)。</span><span class="sxs-lookup"><span data-stu-id="c99ac-107">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="c99ac-108">建立分類器時，您必須建立*說明*以定義模型。</span><span class="sxs-lookup"><span data-stu-id="c99ac-108">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="c99ac-109">這可讓您記錄預期會持續發現此文件類型的常見資料。</span><span class="sxs-lookup"><span data-stu-id="c99ac-109">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="c99ac-110">使用文件類型的範例 (「範例檔」) 來「訓練」您的模型，以找出擁有相同內容類型的檔案。</span><span class="sxs-lookup"><span data-stu-id="c99ac-110">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="c99ac-111">若要建立分類器，您必須：</span><span class="sxs-lookup"><span data-stu-id="c99ac-111">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="c99ac-112">為模型命名。</span><span class="sxs-lookup"><span data-stu-id="c99ac-112">Name your model.</span></span>
2. <span data-ttu-id="c99ac-113">新增範例檔案。</span><span class="sxs-lookup"><span data-stu-id="c99ac-113">Add your example files.</span></span>
3. <span data-ttu-id="c99ac-114">為範例檔案加上標籤。</span><span class="sxs-lookup"><span data-stu-id="c99ac-114">Label your example files.</span></span>
4. <span data-ttu-id="c99ac-115">建立說明。</span><span class="sxs-lookup"><span data-stu-id="c99ac-115">Create an explanation.</span></span>
5. <span data-ttu-id="c99ac-116">測試您的模型。</span><span class="sxs-lookup"><span data-stu-id="c99ac-116">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="c99ac-117">當您的模型使用分類器來識別和分類文件類型時，您也可以選擇從模型所識別的每個檔案中提取特定資訊。</span><span class="sxs-lookup"><span data-stu-id="c99ac-117">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="c99ac-118">方法是建立要新增至模型的 **[擷取器]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-118">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="c99ac-119">請參閱[建立擷取器](create-an-extractor.md)。</span><span class="sxs-lookup"><span data-stu-id="c99ac-119">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="c99ac-120">為模型命名</span><span class="sxs-lookup"><span data-stu-id="c99ac-120">Name your model</span></span>

<span data-ttu-id="c99ac-121">建立模型的第一個步驟是為其命名：</span><span class="sxs-lookup"><span data-stu-id="c99ac-121">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="c99ac-122">從 [內容中心] 選取 **[新增]**，然後選取 **[建立模型]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-122">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="c99ac-123">在 **[新增文件瞭解模型]** 窗格的 **[名稱]** 欄位中，輸入模型的名稱。</span><span class="sxs-lookup"><span data-stu-id="c99ac-123">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="c99ac-124">例如，如果您想要識別合約續約文件，可以將模型命名為 *[合約續約]*。</span><span class="sxs-lookup"><span data-stu-id="c99ac-124">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="c99ac-125">選擇 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-125">Choose **Create**.</span></span> <span data-ttu-id="c99ac-126">這會為模型建立首頁。</span><span class="sxs-lookup"><span data-stu-id="c99ac-126">This creates a home page for the model.</span></span></br>

    ![分類器模型首頁](../media/content-understanding/model-home.png)

<span data-ttu-id="c99ac-128">當您建立模型時，您也會建立新的網站內容類型。</span><span class="sxs-lookup"><span data-stu-id="c99ac-128">When you create a model, you are also creating a new site content type.</span></span> <span data-ttu-id="c99ac-129">內容類型代表具有共同特徵及共用特定內容的欄或中繼資料屬性集合的文件類別。</span><span class="sxs-lookup"><span data-stu-id="c99ac-129">A content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="c99ac-130">透過[內容類型資源庫](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f)管理 [SharePoint 內容類型]。</span><span class="sxs-lookup"><span data-stu-id="c99ac-130">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="c99ac-131">在此範例中，當您建立模型時，您會建立新的 *[合約續約]* 內容類型。</span><span class="sxs-lookup"><span data-stu-id="c99ac-131">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="c99ac-132">如果您想要將這個模型對應到 SharePoint 內容類型資源庫中現有的企業內容類型以使用其結構描述，請選取 **[進階設定]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-132">Select **Advanced settings** if you want to map this model to an existing enterprise content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="c99ac-133">企業內容類型儲存在 SharePoint 系統管理中心的內容類型中樞中，並與租用戶中的所有網站整合。</span><span class="sxs-lookup"><span data-stu-id="c99ac-133">Enterprise content types are stored in the Content Type Hub in the SharePoint admin center and are syndicated to all sites in the tenant.</span></span> <span data-ttu-id="c99ac-134">請注意，雖然您可以使用現有的內容類型來運用其結構描述以協助識別和分類，您仍然需要訓練模型，以從所識別的檔案擷取資訊。</span><span class="sxs-lookup"><span data-stu-id="c99ac-134">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![進階設定](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="c99ac-136">新增範例檔案</span><span class="sxs-lookup"><span data-stu-id="c99ac-136">Add your example files</span></span>

<span data-ttu-id="c99ac-137">在模型首頁上，新增您的範例檔案，您需要協助訓練模型以識別您的文件類型。</span><span class="sxs-lookup"><span data-stu-id="c99ac-137">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="c99ac-138">您應將相同檔案用於分類器和[擷取器訓練](create-an-extractor.md)。</span><span class="sxs-lookup"><span data-stu-id="c99ac-138">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="c99ac-139">您隨時都可以選擇稍後再新增，但通常您會新增一整套範例檔案。</span><span class="sxs-lookup"><span data-stu-id="c99ac-139">You always have the option to add more later, but typically you add a full set of example files.</span></span> <span data-ttu-id="c99ac-140">標記一些以訓練您的模型，並測試其餘未標記的項目，以評估模型適用性。</span><span class="sxs-lookup"><span data-stu-id="c99ac-140">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="c99ac-141">針對訓練集，您會想要使用正面和負面的範例：</span><span class="sxs-lookup"><span data-stu-id="c99ac-141">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="c99ac-142">正面範例：代表檔案類型的文件。</span><span class="sxs-lookup"><span data-stu-id="c99ac-142">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="c99ac-143">這些包含的字串和資訊永遠存在於這種文件類型。</span><span class="sxs-lookup"><span data-stu-id="c99ac-143">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="c99ac-144">負面範例：任何不代表您要分類之文件的其他文件。</span><span class="sxs-lookup"><span data-stu-id="c99ac-144">Negative example: Any other document that does not represent the document you want to classify.</span></span> 

<span data-ttu-id="c99ac-145">請務必使用至少五個正面範例，以及至少一個負面範例來訓練您的模型。</span><span class="sxs-lookup"><span data-stu-id="c99ac-145">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="c99ac-146">您想要在訓練程序之後建立其他範本來測試模型。</span><span class="sxs-lookup"><span data-stu-id="c99ac-146">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="c99ac-147">若要新增範例檔案：</span><span class="sxs-lookup"><span data-stu-id="c99ac-147">To add example files:</span></span>

1. <span data-ttu-id="c99ac-148">在模型首頁上的 **[新增範例檔案]** 磚中，按一下 **[新增檔案]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-148">On the model home page, in the **Add example files** tile, click **Add files**.</span></span>
2. <span data-ttu-id="c99ac-149">在 **[選取您模型的範例檔案]** 頁面上，選取內容中心中 [訓練檔] 文件庫的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="c99ac-149">On the **Select example files for your model** page, select your example files from the Training files library in the content center.</span></span> <span data-ttu-id="c99ac-150">如果您還沒有將檔案上傳到該處，請按一下 **[上傳]**，將檔案複製到 [訓練檔] 文件庫，選擇立即上傳。</span><span class="sxs-lookup"><span data-stu-id="c99ac-150">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to copy them to the Training files library.</span></span>
3. <span data-ttu-id="c99ac-151">選取您要用來訓練模型的範例檔案之後，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![選取範例檔案](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="c99ac-153">為範例檔案加上標籤</span><span class="sxs-lookup"><span data-stu-id="c99ac-153">Label your example files</span></span>

<span data-ttu-id="c99ac-154">新增範例檔案之後，您必須將其標記為正面或負面範例。</span><span class="sxs-lookup"><span data-stu-id="c99ac-154">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="c99ac-155">在模型首頁的 **[分類檔案和執行訓練]** 磚中，按一下 **[訓練分類器]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-155">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="c99ac-156">這會顯示 [標籤] 頁面，該頁面顯示範例檔案清單，並在檢視器中顯示第一個檔案。</span><span class="sxs-lookup"><span data-stu-id="c99ac-156">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="c99ac-157">在第一個範例檔案頂端的檢視器中，您應該會看到一些文字，詢問該檔案是否為您剛建立的模型範例。</span><span class="sxs-lookup"><span data-stu-id="c99ac-157">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="c99ac-158">如果是正面範例，請選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="c99ac-159">如果是負面範例，請選取 **[否]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="c99ac-160">在左邊的 **[已標記範例]** 清單中，選取您想要做為範例的其他檔案，然後為其標記。</span><span class="sxs-lookup"><span data-stu-id="c99ac-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![分類器首頁](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="c99ac-162">至少標記五個正面範例。</span><span class="sxs-lookup"><span data-stu-id="c99ac-162">Label at least five positive examples.</span></span> <span data-ttu-id="c99ac-163">您也必須標記至少一個負面範例。</span><span class="sxs-lookup"><span data-stu-id="c99ac-163">You must also label at least one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="c99ac-164">建立說明。</span><span class="sxs-lookup"><span data-stu-id="c99ac-164">Create an explanation</span></span>

<span data-ttu-id="c99ac-165">下一個步驟是在 [訓練] 頁面建立說明。</span><span class="sxs-lookup"><span data-stu-id="c99ac-165">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="c99ac-166">說明可協助模型瞭解如何辨識文件。</span><span class="sxs-lookup"><span data-stu-id="c99ac-166">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="c99ac-167">例如，合約續約文件始終包含 *[要求其他公開揭示]* 文字字串。</span><span class="sxs-lookup"><span data-stu-id="c99ac-167">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="c99ac-168">與擷取程式搭配使用時，說明會識別您要從文件中提取的字串。</span><span class="sxs-lookup"><span data-stu-id="c99ac-168">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="c99ac-169">若要建立說明：</span><span class="sxs-lookup"><span data-stu-id="c99ac-169">To create an explanation:</span></span>

1. <span data-ttu-id="c99ac-170">從模型首頁中，選取 **[訓練]** 索引標籤，以移至 [訓練] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c99ac-170">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="c99ac-171">在 [訓練] 頁面的 **[已訓練檔案]** 區段中，您應該會看到您之前已標記的範例檔案清單。</span><span class="sxs-lookup"><span data-stu-id="c99ac-171">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="c99ac-172">從清單中選取其中一個正向檔案，它會顯示在檢視器中。</span><span class="sxs-lookup"><span data-stu-id="c99ac-172">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="c99ac-173">在 [說明] 區段中，選取 **[新增]**，然後選取 **[空白]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-173">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="c99ac-174">在 **[建立說明]** 頁面：</span><span class="sxs-lookup"><span data-stu-id="c99ac-174">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="c99ac-175">a.</span><span class="sxs-lookup"><span data-stu-id="c99ac-175">a.</span></span> <span data-ttu-id="c99ac-176">輸入 **[名稱]** (例如「公開揭示封鎖」)。</span><span class="sxs-lookup"><span data-stu-id="c99ac-176">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="c99ac-177">b.</span><span class="sxs-lookup"><span data-stu-id="c99ac-177">b.</span></span> <span data-ttu-id="c99ac-178">選取 **[類型]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-178">Select the **Type**.</span></span> <span data-ttu-id="c99ac-179">針對此範例，請選取 **[片語清單]**，因為您新增的是文字字串。</span><span class="sxs-lookup"><span data-stu-id="c99ac-179">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="c99ac-180">c.</span><span class="sxs-lookup"><span data-stu-id="c99ac-180">c.</span></span> <span data-ttu-id="c99ac-181">在 **[在這裡輸入]** 方塊中，輸入字串。</span><span class="sxs-lookup"><span data-stu-id="c99ac-181">In the **Type here** box, type the string.</span></span> <span data-ttu-id="c99ac-182">針對此範例，請新增「要求其他公開揭示」。</span><span class="sxs-lookup"><span data-stu-id="c99ac-182">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="c99ac-183">如果字串必須區分大小寫，您可以選取 **[區分大小寫]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-183">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="c99ac-184">d.</span><span class="sxs-lookup"><span data-stu-id="c99ac-184">d.</span></span> <span data-ttu-id="c99ac-185">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="c99ac-185">Click **Save**.</span></span>

    ![建立說明](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="c99ac-187">現在，模型會檢查您所建立的說明是否夠好，以便將剩餘的已標記範例檔案正確識別為正面和負面範例。</span><span class="sxs-lookup"><span data-stu-id="c99ac-187">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="c99ac-188">訓練完成之後，在 [已訓練檔案] 區段中檢查 **[評估]** 資料行，以查看結果。</span><span class="sxs-lookup"><span data-stu-id="c99ac-188">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="c99ac-189">如果您建立的說明足以符合您標記為正面或負面的結果，檔案就會顯示 **[符合]** 的值。</span><span class="sxs-lookup"><span data-stu-id="c99ac-189">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![符合值](../media/content-understanding/match.png) 

<span data-ttu-id="c99ac-191">如果您在已標記檔案上接收到 **[不符合]**，您可能需要建立額外的說明，以提供模型更多資訊來識別文件類型。</span><span class="sxs-lookup"><span data-stu-id="c99ac-191">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="c99ac-192">如果發生這種情況，請按一下檔案，以取得為什麼發生不相符的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c99ac-192">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="c99ac-193">測試您的模型</span><span class="sxs-lookup"><span data-stu-id="c99ac-193">Test your model</span></span>

<span data-ttu-id="c99ac-194">如果您在已標記的範例檔案上收到符合，您現在可以在尚未顯示模型的剩餘未標記範例檔案上測試模型。</span><span class="sxs-lookup"><span data-stu-id="c99ac-194">If you received a match on your labeled sample files, you can now  test your model on your remaining unlabeled example files that the model has not seen before.</span></span>  <span data-ttu-id="c99ac-195">這是一個選用但有用的步驟，可透過在模型以前從未見過的檔案中進行測試來評估模型的「適合性」或就緒狀態。</span><span class="sxs-lookup"><span data-stu-id="c99ac-195">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="c99ac-196">從模型首頁中，選取 **[測試]** 索引標籤。這會在未標記的範例檔案上執行模型。</span><span class="sxs-lookup"><span data-stu-id="c99ac-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="c99ac-197">在 **[測試檔案]** 清單中，您的範例檔案會呈現並顯示模型預測其為正面或負面範例。</span><span class="sxs-lookup"><span data-stu-id="c99ac-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="c99ac-198">使用這項資訊可協助您判斷分類器的效能，以找出您的文件。</span><span class="sxs-lookup"><span data-stu-id="c99ac-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![測試未標記的檔案](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="c99ac-200">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c99ac-200">See Also</span></span>
[<span data-ttu-id="c99ac-201">建立擷取器</span><span class="sxs-lookup"><span data-stu-id="c99ac-201">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="c99ac-202">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="c99ac-202">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="c99ac-203">說明類型</span><span class="sxs-lookup"><span data-stu-id="c99ac-203">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="c99ac-204">套用模型</span><span class="sxs-lookup"><span data-stu-id="c99ac-204">Apply a model</span></span>](apply-a-model.md) 
