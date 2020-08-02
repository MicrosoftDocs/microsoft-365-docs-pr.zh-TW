---
title: 建立分類器（預覽）
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何建立分類器
ms.openlocfilehash: 029ac16310f8e95a69a713896b1109a778eb3b8d
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537026"
---
# <a name="create-a-classifier-preview"></a><span data-ttu-id="4c873-103">建立分類器（預覽）</span><span class="sxs-lookup"><span data-stu-id="4c873-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="4c873-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="4c873-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="4c873-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="4c873-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="4c873-106">分類器是一種類型的模型，可自動化檔案類型的識別和分類。</span><span class="sxs-lookup"><span data-stu-id="4c873-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="4c873-107">例如，您可能想要識別新增至文件庫的所有*合約更新*檔，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4c873-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![合同更新檔](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="4c873-109">建立分類器將會建立新的[SharePoint 內容類型](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)，將會與模型產生關聯。</span><span class="sxs-lookup"><span data-stu-id="4c873-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="4c873-110">建立分類器時，您需要建立*說明*，以協助您在此檔案類型的情況下，透過注意您預期會發現的常見資料來定義模型。</span><span class="sxs-lookup"><span data-stu-id="4c873-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="4c873-111">您可以使用檔案類型（「範例檔案」）的範例，協助 "訓練" 您的模型來識別具有相同內容類型的檔案。</span><span class="sxs-lookup"><span data-stu-id="4c873-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="4c873-112">若要建立分類符，您必須：</span><span class="sxs-lookup"><span data-stu-id="4c873-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="4c873-113">命名模型</span><span class="sxs-lookup"><span data-stu-id="4c873-113">Name your model</span></span>
2. <span data-ttu-id="4c873-114">新增您的範例檔案</span><span class="sxs-lookup"><span data-stu-id="4c873-114">Add your example files</span></span>
3. <span data-ttu-id="4c873-115">標記範例檔案</span><span class="sxs-lookup"><span data-stu-id="4c873-115">Label your example files</span></span>
4. <span data-ttu-id="4c873-116">建立說明</span><span class="sxs-lookup"><span data-stu-id="4c873-116">Create an explanation</span></span>
5. <span data-ttu-id="4c873-117">測試您的模型</span><span class="sxs-lookup"><span data-stu-id="4c873-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="4c873-118">雖然您的模型使用分類器來識別和分類檔案類型，您也可以選擇從模型所識別的每個檔案中提取特定的資訊片段。</span><span class="sxs-lookup"><span data-stu-id="4c873-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="4c873-119">若要執行此動作，您可以建立要新增至模型的**解壓縮**程式，並在 [[建立解壓縮程式](create-an-extractor.md)] 中加以說明。</span><span class="sxs-lookup"><span data-stu-id="4c873-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="4c873-120">命名模型</span><span class="sxs-lookup"><span data-stu-id="4c873-120">Name your model</span></span>

<span data-ttu-id="4c873-121">第一步是在內容中心建立模型，其名稱如下：</span><span class="sxs-lookup"><span data-stu-id="4c873-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="4c873-122">在內容中心，按一下 [**新增**]，然後按一下 [**建立模型**]。</span><span class="sxs-lookup"><span data-stu-id="4c873-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="4c873-123">在 [**新增檔瞭解模型**] 窗格的 [**名稱**] 欄位中，輸入模型的名稱。</span><span class="sxs-lookup"><span data-stu-id="4c873-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="4c873-124">在我們的範例中，如果我們想要識別合同更新檔，我們可以命名此模型*合約更新*。</span><span class="sxs-lookup"><span data-stu-id="4c873-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="4c873-125">按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c873-125">Click **Create**.</span></span> <span data-ttu-id="4c873-126">這將會為模型建立首頁。</span><span class="sxs-lookup"><span data-stu-id="4c873-126">This will create a home page for the model.</span></span></br>

    ![分類器模型首頁](../media/content-understanding/model-home.png)

<span data-ttu-id="4c873-128">當您建立模型時，會建立新的 SharePoint 內容類型。</span><span class="sxs-lookup"><span data-stu-id="4c873-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="4c873-129">SharePoint 內容類型代表具有共同特性並共用該特定內容之一組欄或中繼資料屬性的檔類別。</span><span class="sxs-lookup"><span data-stu-id="4c873-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="4c873-130">SharePoint 內容類型是透過[內容類型庫]()進行管理。</span><span class="sxs-lookup"><span data-stu-id="4c873-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="4c873-131">在我們的範例中，當我們建立模型時，我們會建立新的*合約更新*內容類型。</span><span class="sxs-lookup"><span data-stu-id="4c873-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="4c873-132">如果您想要將此模型對應至 SharePoint 內容類型庫中的現有內容類型，以使用其架構，請選取 [**高級設定**]。</span><span class="sxs-lookup"><span data-stu-id="4c873-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="4c873-133">請注意，雖然您可以使用現有的內容類型來利用其架構來協助識別和分類，但您仍然需要訓練模型，以從識別的檔案提取資訊。</span><span class="sxs-lookup"><span data-stu-id="4c873-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![進階設定](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="4c873-135">新增您的範例檔案</span><span class="sxs-lookup"><span data-stu-id="4c873-135">Add your example files</span></span>

<span data-ttu-id="4c873-136">在模型首頁上，您可以新增您所需的範例檔案，以協助訓練模型識別檔案類型。</span><span class="sxs-lookup"><span data-stu-id="4c873-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="4c873-137">分類器和[提取程式訓練](create-an-extractor.md)都應該使用相同的檔案。</span><span class="sxs-lookup"><span data-stu-id="4c873-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="4c873-138">您可以選擇稍後新增更多，但通常您應該新增一組完整的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="4c873-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="4c873-139">您將會標示部分以訓練模型，並測試其餘未標記的模型，以評估模型健身。</span><span class="sxs-lookup"><span data-stu-id="4c873-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="4c873-140">針對您的訓練集，您會想要使用正的範例和消極的範例：</span><span class="sxs-lookup"><span data-stu-id="4c873-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="4c873-141">肯定範例：代表檔案類型的檔。</span><span class="sxs-lookup"><span data-stu-id="4c873-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="4c873-142">它們包含的字串和資訊永遠都屬於這種檔案類型。</span><span class="sxs-lookup"><span data-stu-id="4c873-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="4c873-143">負數範例：不代表檔案類型的檔。</span><span class="sxs-lookup"><span data-stu-id="4c873-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="4c873-144">它們遺漏的字串和資訊需要存在於這種檔案類型中。</span><span class="sxs-lookup"><span data-stu-id="4c873-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="4c873-145">您至少要使用五個正的範例和一個負數範例來訓練您的模型。</span><span class="sxs-lookup"><span data-stu-id="4c873-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="4c873-146">您會想要有其他的考試之後測試您的模型。</span><span class="sxs-lookup"><span data-stu-id="4c873-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="4c873-147">若要新增範例檔案：</span><span class="sxs-lookup"><span data-stu-id="4c873-147">To add sample files:</span></span>

1. <span data-ttu-id="4c873-148">在模型首頁上，按一下 [**組建範例文件庫**] 磚中的 [**新增**檔案]。</span><span class="sxs-lookup"><span data-stu-id="4c873-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="4c873-149">在 [**選取模型的範例**檔案] 頁面上，從內容中心的範例檔案庫中選取範例檔案。</span><span class="sxs-lookup"><span data-stu-id="4c873-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="4c873-150">如果您還沒有上傳這些檔案，您可以按一下 [**上傳**]，將其移至範例檔案庫。</span><span class="sxs-lookup"><span data-stu-id="4c873-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="4c873-151">選取用來訓練模型的範例檔案之後，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="4c873-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![選取範例檔案](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="4c873-153">標記範例檔案</span><span class="sxs-lookup"><span data-stu-id="4c873-153">Label your example files</span></span>

<span data-ttu-id="4c873-154">在新增範例檔案之後，您必須將它們標為正範例或負數範例。</span><span class="sxs-lookup"><span data-stu-id="4c873-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="4c873-155">在模型首頁上，按一下 [**分類檔案及執行訓練**] 磚上的 [**訓練分類器**]。</span><span class="sxs-lookup"><span data-stu-id="4c873-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="4c873-156">這會顯示 [標籤] 頁面，顯示範例檔案的清單，第一個檔案會顯示在檢視器中。</span><span class="sxs-lookup"><span data-stu-id="4c873-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="4c873-157">在檢視器中第一個範例檔案的上方，您會看到文字詢問您的檔案是否為您剛才建立的模型範例。</span><span class="sxs-lookup"><span data-stu-id="4c873-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="4c873-158">如果是正範例，請選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="4c873-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="4c873-159">如果是負數範例，請選取 [**否**]。</span><span class="sxs-lookup"><span data-stu-id="4c873-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="4c873-160">從左側的 [已**標記的範例**] 清單中，選取您要做為範例的其他檔案，並將它們標示好。</span><span class="sxs-lookup"><span data-stu-id="4c873-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![分類器模型首頁](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="4c873-162">標籤至少五個正範例，另一個為負的範例。</span><span class="sxs-lookup"><span data-stu-id="4c873-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="4c873-163">建立說明</span><span class="sxs-lookup"><span data-stu-id="4c873-163">Create an explanation</span></span>

<span data-ttu-id="4c873-164">下一步是在訓練頁面上建立說明。</span><span class="sxs-lookup"><span data-stu-id="4c873-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="4c873-165">說明是協助模型瞭解如何辨識此檔的提示或線索。</span><span class="sxs-lookup"><span data-stu-id="4c873-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="4c873-166">例如，我們的合約更新檔一定會包含*額外披露文字字串的要求*。</span><span class="sxs-lookup"><span data-stu-id="4c873-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="4c873-167">與擷取器搭配使用時，說明是用來識別您想要從檔中解壓縮的字串。</span><span class="sxs-lookup"><span data-stu-id="4c873-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="4c873-168">若要建立說明：</span><span class="sxs-lookup"><span data-stu-id="4c873-168">To create an explanation:</span></span>

1. <span data-ttu-id="4c873-169">在模型首頁上，按一下 [**火車**] 索引標籤以移至 [訓練] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4c873-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="4c873-170">在 [訓練] 頁面的 [**訓練有素**的檔案] 區段中，您將會看到您先前已標示的範例檔案清單。</span><span class="sxs-lookup"><span data-stu-id="4c873-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="4c873-171">從清單中選取其中一個正檔，它會顯示在檢視器中。</span><span class="sxs-lookup"><span data-stu-id="4c873-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="4c873-172">在 [說明] 區段中，按一下 [**新增**]，然後按一下 [**空白**]。</span><span class="sxs-lookup"><span data-stu-id="4c873-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="4c873-173">在 [**建立說明**] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="4c873-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="4c873-174">a.</span><span class="sxs-lookup"><span data-stu-id="4c873-174">a.</span></span> <span data-ttu-id="4c873-175">輸入**名稱**（例如，「披露組塊」）。</span><span class="sxs-lookup"><span data-stu-id="4c873-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="4c873-176">b.</span><span class="sxs-lookup"><span data-stu-id="4c873-176">b.</span></span> <span data-ttu-id="4c873-177">選取**類型**。</span><span class="sxs-lookup"><span data-stu-id="4c873-177">Select the **Type**.</span></span> <span data-ttu-id="4c873-178">在我們的範例中，我們會選取**片語清單**，因為我們會加入文字字串。</span><span class="sxs-lookup"><span data-stu-id="4c873-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="4c873-179">c.</span><span class="sxs-lookup"><span data-stu-id="4c873-179">c.</span></span> <span data-ttu-id="4c873-180">在 [**請輸入此文字**] 方塊中，輸入字串。</span><span class="sxs-lookup"><span data-stu-id="4c873-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="4c873-181">在我們的範例中，我們將新增「要求其他披露」。</span><span class="sxs-lookup"><span data-stu-id="4c873-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="4c873-182">若字串必須區分大小寫，您可以選取 [區分**大小寫**]。</span><span class="sxs-lookup"><span data-stu-id="4c873-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="4c873-183">d.</span><span class="sxs-lookup"><span data-stu-id="4c873-183">d.</span></span> <span data-ttu-id="4c873-184">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c873-184">Click **Save**.</span></span>

    ![建立說明](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="4c873-186">模型現在會檢查您建立的釋義是否足夠好，以找出您的剩餘標記範例檔案正確，如正值及負數範例。</span><span class="sxs-lookup"><span data-stu-id="4c873-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="4c873-187">在 [訓練有素的檔案] 區段中，檢查訓練**值**欄之後，查看結果。</span><span class="sxs-lookup"><span data-stu-id="4c873-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="4c873-188">如果您建立的釋義足以符合您為其標示的專案（肯定或否定），檔案會顯示 [**符合**專案] 的值。</span><span class="sxs-lookup"><span data-stu-id="4c873-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![建立說明](../media/content-understanding/match.png) 

<span data-ttu-id="4c873-190">如果您在已標示的檔案上收到**不一致**的資訊，您可能需要建立額外的說明，以提供模型以進一步識別檔案類型的資訊。</span><span class="sxs-lookup"><span data-stu-id="4c873-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="4c873-191">您可以按一下檔案，以取得為何不符的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4c873-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="4c873-192">測試您的模型</span><span class="sxs-lookup"><span data-stu-id="4c873-192">Test your model</span></span>

<span data-ttu-id="4c873-193">如果您在已標示的範例檔案上收到相符的檔，您現在可以在其餘未標記的範例檔案上測試您的模型。</span><span class="sxs-lookup"><span data-stu-id="4c873-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="4c873-194">在模型首頁上，按一下 [**測試**] 索引標籤。 這會在未標記的範例檔案上執行該模型。</span><span class="sxs-lookup"><span data-stu-id="4c873-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="4c873-195">在 [**測試**檔案] 清單中，您的範例檔案會顯示，而且會顯示模型是否預測為正數或負數範例。</span><span class="sxs-lookup"><span data-stu-id="4c873-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="4c873-196">您可以使用這項資訊來協助您判斷您的分類器在識別檔時的效能。</span><span class="sxs-lookup"><span data-stu-id="4c873-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![測試未標記的檔案](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="4c873-198">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4c873-198">See Also</span></span>
[<span data-ttu-id="4c873-199">建立提取程式</span><span class="sxs-lookup"><span data-stu-id="4c873-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="4c873-200">檔理解概述</span><span class="sxs-lookup"><span data-stu-id="4c873-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="4c873-201">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="4c873-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="4c873-202">套用模型</span><span class="sxs-lookup"><span data-stu-id="4c873-202">Apply a model</span></span>](apply-a-model.md) 




