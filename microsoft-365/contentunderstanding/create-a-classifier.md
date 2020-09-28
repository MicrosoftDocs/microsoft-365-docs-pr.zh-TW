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
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="f328e-103">在 Microsoft SharePoint Syntex 中建立分類器</span><span class="sxs-lookup"><span data-stu-id="f328e-103">Create a classifier in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="f328e-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="f328e-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="f328e-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="f328e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="f328e-106">分類器是一種模型，可讓您用來自動化檔案類型的身分識別和分類。</span><span class="sxs-lookup"><span data-stu-id="f328e-106">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="f328e-107">例如，您可能想要識別所有已新增至文件庫的 *合約更新* 檔，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="f328e-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![合同更新檔](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="f328e-109">建立分類程式可讓您建立新的 [SharePoint 內容類型](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) ，將會與模型產生關聯。</span><span class="sxs-lookup"><span data-stu-id="f328e-109">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="f328e-110">建立分類器時，您必須建立 *說明* 以定義模型。</span><span class="sxs-lookup"><span data-stu-id="f328e-110">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="f328e-111">這可讓您記下您預期會始終如一地找到這種檔案類型的常見資料。</span><span class="sxs-lookup"><span data-stu-id="f328e-111">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="f328e-112">使用檔案類型的範例 ( "範例檔案" ) 以 "訓練" 您的模型來識別具有相同內容類型的檔案。</span><span class="sxs-lookup"><span data-stu-id="f328e-112">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="f328e-113">若要建立分類符，您必須：</span><span class="sxs-lookup"><span data-stu-id="f328e-113">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="f328e-114">命名模型。</span><span class="sxs-lookup"><span data-stu-id="f328e-114">Name your model.</span></span>
2. <span data-ttu-id="f328e-115">新增您的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="f328e-115">Add your example files.</span></span>
3. <span data-ttu-id="f328e-116">為範例檔案加上標籤。</span><span class="sxs-lookup"><span data-stu-id="f328e-116">Label your example files.</span></span>
4. <span data-ttu-id="f328e-117">建立說明。</span><span class="sxs-lookup"><span data-stu-id="f328e-117">Create an explanation.</span></span>
5. <span data-ttu-id="f328e-118">測試您的模型。</span><span class="sxs-lookup"><span data-stu-id="f328e-118">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="f328e-119">雖然您的模型使用分類器來識別和分類檔案類型，您也可以選擇從模型所識別的每個檔案中提取特定的資訊片段。</span><span class="sxs-lookup"><span data-stu-id="f328e-119">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="f328e-120">建立 **解壓縮** 程式以新增至您的模型。</span><span class="sxs-lookup"><span data-stu-id="f328e-120">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="f328e-121">請參閱 [建立提取程式](create-an-extractor.md)。</span><span class="sxs-lookup"><span data-stu-id="f328e-121">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="f328e-122">命名模型</span><span class="sxs-lookup"><span data-stu-id="f328e-122">Name your model</span></span>

<span data-ttu-id="f328e-123">建立模型的第一個步驟是為其命名：</span><span class="sxs-lookup"><span data-stu-id="f328e-123">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="f328e-124">從內容中心選取 [ **新增**]，然後 **建立模型**。</span><span class="sxs-lookup"><span data-stu-id="f328e-124">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="f328e-125">在 [ **新增檔瞭解模型** ] 窗格的 [ **名稱** ] 欄位中，輸入模型的名稱。</span><span class="sxs-lookup"><span data-stu-id="f328e-125">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="f328e-126">例如，如果您想要識別合同更新檔，您可以命名模型 *合約更新*。</span><span class="sxs-lookup"><span data-stu-id="f328e-126">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="f328e-127">	選擇 *\*[建立]*\*。</span><span class="sxs-lookup"><span data-stu-id="f328e-127">Choose **Create**.</span></span> <span data-ttu-id="f328e-128">這會為模型建立首頁。</span><span class="sxs-lookup"><span data-stu-id="f328e-128">This creates a home page for the model.</span></span></br>

    ![分類器模型首頁](../media/content-understanding/model-home.png)

<span data-ttu-id="f328e-130">當您建立模型時，您也是建立新的 SharePoint 內容類型。</span><span class="sxs-lookup"><span data-stu-id="f328e-130">When you create a model, you are also creating a new SharePoint content type.</span></span> <span data-ttu-id="f328e-131">SharePoint 內容類型代表具有共同特性並共用該特定內容之一組欄或中繼資料屬性的檔類別。</span><span class="sxs-lookup"><span data-stu-id="f328e-131">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="f328e-132">SharePoint 內容類型是透過 [內容類型庫](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f)進行管理。</span><span class="sxs-lookup"><span data-stu-id="f328e-132">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="f328e-133">在此範例中，當您建立模型時，會建立新的 *合約更新* 內容類型。</span><span class="sxs-lookup"><span data-stu-id="f328e-133">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="f328e-134">如果您想要將此模型對應至 SharePoint 內容類型庫中的現有內容類型，以使用其架構，請選取 [ **高級設定** ]。</span><span class="sxs-lookup"><span data-stu-id="f328e-134">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="f328e-135">請注意，雖然您可以使用現有的內容類型來利用其架構來協助識別和分類，但您仍然需要訓練模型，以從識別的檔案提取資訊。</span><span class="sxs-lookup"><span data-stu-id="f328e-135">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![進階設定](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="f328e-137">新增您的範例檔案</span><span class="sxs-lookup"><span data-stu-id="f328e-137">Add your example files</span></span>

<span data-ttu-id="f328e-138">在模型首頁上，新增您所需的範例檔案，以協助訓練模型識別檔案類型。</span><span class="sxs-lookup"><span data-stu-id="f328e-138">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="f328e-139">您應該針對分類器和 [提取程式訓練](create-an-extractor.md)使用相同的檔案。</span><span class="sxs-lookup"><span data-stu-id="f328e-139">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="f328e-140">您可以選擇稍後新增更多，但通常您會新增一組完整的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="f328e-140">You always have the option to add more later, but typically you add a full set of sample files.</span></span> <span data-ttu-id="f328e-141">標示部分以訓練模型，並測試其餘未標記的專案，以評估模型健身。</span><span class="sxs-lookup"><span data-stu-id="f328e-141">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="f328e-142">針對您的訓練集，您想要使用正和負的範例：</span><span class="sxs-lookup"><span data-stu-id="f328e-142">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="f328e-143">肯定範例：代表檔案類型的檔。</span><span class="sxs-lookup"><span data-stu-id="f328e-143">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="f328e-144">這些包含的字串和資訊永遠都屬於這種檔案類型。</span><span class="sxs-lookup"><span data-stu-id="f328e-144">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="f328e-145">負數範例：不代表檔案類型的檔。</span><span class="sxs-lookup"><span data-stu-id="f328e-145">Negative example: Documents that do not represent the document type.</span></span> <span data-ttu-id="f328e-146">這些是遺失的字串和資訊，必須存在於這種檔案類型中。</span><span class="sxs-lookup"><span data-stu-id="f328e-146">These are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="f328e-147">請務必使用至少五個正值，以及至少一個否定性的範例訓練您的模型。</span><span class="sxs-lookup"><span data-stu-id="f328e-147">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="f328e-148">您想要建立其他專案，以在訓練程式之後測試您的模型。</span><span class="sxs-lookup"><span data-stu-id="f328e-148">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="f328e-149">若要新增範例檔案：</span><span class="sxs-lookup"><span data-stu-id="f328e-149">To add sample files:</span></span>

1. <span data-ttu-id="f328e-150">從模型首頁的 [ **建立範例文件庫** ] 磚中，按一下 [ **新增**檔案]。</span><span class="sxs-lookup"><span data-stu-id="f328e-150">From the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="f328e-151">在 [ **選取模型的範例** 檔案] 頁面上，從內容中心的範例檔案庫中選取範例檔案。</span><span class="sxs-lookup"><span data-stu-id="f328e-151">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="f328e-152">如果您還沒有上傳它們，請按一下 [ **上傳** ]，將其移至範例檔案庫中，選擇立即上傳。</span><span class="sxs-lookup"><span data-stu-id="f328e-152">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="f328e-153">選取用來訓練模型的範例檔案之後，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="f328e-153">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![選取範例檔案](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="f328e-155">標記範例檔案</span><span class="sxs-lookup"><span data-stu-id="f328e-155">Label your example files</span></span>

<span data-ttu-id="f328e-156">在新增範例檔案之後，您必須將它們標示為正數或負數範例。</span><span class="sxs-lookup"><span data-stu-id="f328e-156">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="f328e-157">從模型首頁的 [ **分類檔案及執行訓練** ] 磚上，按一下 [ **訓練分類器**]。</span><span class="sxs-lookup"><span data-stu-id="f328e-157">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="f328e-158">這會顯示 [標籤] 頁面，顯示範例檔案的清單，第一個檔案會顯示在檢視器中。</span><span class="sxs-lookup"><span data-stu-id="f328e-158">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="f328e-159">在第一個範例檔案頂端的檢視器中，您應該會看到文字，詢問檔案是否為您剛才建立的模型範例。</span><span class="sxs-lookup"><span data-stu-id="f328e-159">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="f328e-160">如果是正範例，請選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="f328e-160">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="f328e-161">如果是負數範例，請選取 [ **否**]。</span><span class="sxs-lookup"><span data-stu-id="f328e-161">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="f328e-162">從左側的 [已 **標記的範例** ] 清單中，選取您要做為範例的其他檔案，然後將它們標示。</span><span class="sxs-lookup"><span data-stu-id="f328e-162">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![分類器首頁](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="f328e-164">標籤至少五個正範例，另一個為負的範例。</span><span class="sxs-lookup"><span data-stu-id="f328e-164">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="f328e-165">建立說明</span><span class="sxs-lookup"><span data-stu-id="f328e-165">Create an explanation</span></span>

<span data-ttu-id="f328e-166">下一步是讓您在訓練頁面上建立說明。</span><span class="sxs-lookup"><span data-stu-id="f328e-166">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="f328e-167">說明可協助模型瞭解如何辨識檔。</span><span class="sxs-lookup"><span data-stu-id="f328e-167">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="f328e-168">例如，合約更新檔一定會包含 *其他披露文字字串的要求* 。</span><span class="sxs-lookup"><span data-stu-id="f328e-168">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="f328e-169">與擷取器搭配使用時，說明您要從檔中解壓縮的字串。</span><span class="sxs-lookup"><span data-stu-id="f328e-169">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="f328e-170">若要建立說明：</span><span class="sxs-lookup"><span data-stu-id="f328e-170">To create an explanation:</span></span>

1. <span data-ttu-id="f328e-171">從模型首頁，選取 [ **訓練** ] 索引標籤以移至 [訓練] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f328e-171">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="f328e-172">在 [訓練] 頁面的 [ **訓練有素** 的檔案] 區段中，您應該會看到先前標示的範例檔案清單。</span><span class="sxs-lookup"><span data-stu-id="f328e-172">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="f328e-173">從清單中選取其中一個正的檔案，然後在檢視器中顯示。</span><span class="sxs-lookup"><span data-stu-id="f328e-173">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="f328e-174">在 [說明] 區段中，選取 [ **新增** ]，然後選取 [ **空白**]。</span><span class="sxs-lookup"><span data-stu-id="f328e-174">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="f328e-175">在 [ **建立說明** ] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="f328e-175">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="f328e-176">a.</span><span class="sxs-lookup"><span data-stu-id="f328e-176">a.</span></span> <span data-ttu-id="f328e-177">輸入 **名稱** (例如，"披露 Block" ) 。</span><span class="sxs-lookup"><span data-stu-id="f328e-177">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="f328e-178">b.</span><span class="sxs-lookup"><span data-stu-id="f328e-178">b.</span></span> <span data-ttu-id="f328e-179">選取 **類型**。</span><span class="sxs-lookup"><span data-stu-id="f328e-179">Select the **Type**.</span></span> <span data-ttu-id="f328e-180">若為範例，請選取 [ **片語] 清單**，因為您新增了文字字串。</span><span class="sxs-lookup"><span data-stu-id="f328e-180">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="f328e-181">c.</span><span class="sxs-lookup"><span data-stu-id="f328e-181">c.</span></span> <span data-ttu-id="f328e-182">在 [ **請輸入此文字** ] 方塊中，輸入字串。</span><span class="sxs-lookup"><span data-stu-id="f328e-182">In the **Type here** box, type the string.</span></span> <span data-ttu-id="f328e-183">在範例中，新增「要求其他披露」。</span><span class="sxs-lookup"><span data-stu-id="f328e-183">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="f328e-184">若字串必須區分大小寫，您可以選取 [區分 **大小寫** ]。</span><span class="sxs-lookup"><span data-stu-id="f328e-184">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="f328e-185">d.</span><span class="sxs-lookup"><span data-stu-id="f328e-185">d.</span></span> <span data-ttu-id="f328e-186">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="f328e-186">Click **Save**.</span></span>

    ![建立說明](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="f328e-188">模型現在會檢查您建立的釋義是否足夠好，可正確識別其餘標示的範例檔案，如正值及負數範例。</span><span class="sxs-lookup"><span data-stu-id="f328e-188">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="f328e-189">在 [訓練有素的檔案] 區段中，檢查訓練已經完成之後，查看結果的 **評估** 欄。</span><span class="sxs-lookup"><span data-stu-id="f328e-189">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="f328e-190">如果您建立的說明足以符合您標示為正或負數的專案，則檔案會顯示 [ **符合**專案的值]。</span><span class="sxs-lookup"><span data-stu-id="f328e-190">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![符合值](../media/content-understanding/match.png) 

<span data-ttu-id="f328e-192">如果您收到的標籤檔 **不相符** ，您可能需要建立其他說明，以提供模型詳細資訊，以識別檔案類型。</span><span class="sxs-lookup"><span data-stu-id="f328e-192">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="f328e-193">如果發生這種情況，請按一下檔案，以取得未相符之原因的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f328e-193">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="f328e-194">測試您的模型</span><span class="sxs-lookup"><span data-stu-id="f328e-194">Test your model</span></span>

<span data-ttu-id="f328e-195">如果您收到的標記的範例檔案的相符，您現在可以在其餘未標記的範例檔案上測試模型。</span><span class="sxs-lookup"><span data-stu-id="f328e-195">If you received a match on your labeled sample files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="f328e-196">從模型的首頁中，選取 [ **測試** ] 索引標籤。 這會在未標記的範例檔案上執行模型。</span><span class="sxs-lookup"><span data-stu-id="f328e-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="f328e-197">在 [ **測試** 檔案] 清單中，會顯示您的範例檔案，並顯示模型是否預測為正值或負數。</span><span class="sxs-lookup"><span data-stu-id="f328e-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="f328e-198">使用此資訊有助於決定您的分類程式在識別檔時的效能。</span><span class="sxs-lookup"><span data-stu-id="f328e-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![測試未標記的檔案](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="f328e-200">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f328e-200">See Also</span></span>
[<span data-ttu-id="f328e-201">建立提取程式</span><span class="sxs-lookup"><span data-stu-id="f328e-201">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="f328e-202">檔理解概述</span><span class="sxs-lookup"><span data-stu-id="f328e-202">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="f328e-203">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="f328e-203">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="f328e-204">套用模型</span><span class="sxs-lookup"><span data-stu-id="f328e-204">Apply a model</span></span>](apply-a-model.md) 
