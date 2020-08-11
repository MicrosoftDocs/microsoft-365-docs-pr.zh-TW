---
title: " (預覽中建立表單處理模型) "
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
description: 在 Project Cortex 中建立表單處理模型。
ms.openlocfilehash: 733baf24d8a484571ba9882fdda2633dc2ce0504
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612771"
---
# <a name="create-a-form-processing-model-preview"></a><span data-ttu-id="c8cd1-103"> (預覽中建立表單處理模型) </span><span class="sxs-lookup"><span data-stu-id="c8cd1-103">Create a form processing model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="c8cd1-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c8cd1-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="c8cd1-106">使用[AI Builder](https://docs.microsoft.com/ai-builder/overview) -Microsoft PowerApps 專案 Cortex 中的功能使用者可以直接從 SharePoint 文件庫建立[表單處理模型](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="c8cd1-107">建立表單處理模型包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="c8cd1-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="c8cd1-108">步驟1：建立從處理模型建立內容類型</span><span class="sxs-lookup"><span data-stu-id="c8cd1-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="c8cd1-109">步驟2：新增及分析範例檔案</span><span class="sxs-lookup"><span data-stu-id="c8cd1-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="c8cd1-110">步驟3：選取表單欄位</span><span class="sxs-lookup"><span data-stu-id="c8cd1-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="c8cd1-111">步驟4：訓練及測試您的模型</span><span class="sxs-lookup"><span data-stu-id="c8cd1-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="c8cd1-112">步驟5：發佈您的模型</span><span class="sxs-lookup"><span data-stu-id="c8cd1-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="c8cd1-113">步驟6：使用您的模型</span><span class="sxs-lookup"><span data-stu-id="c8cd1-113">Step 6: Use your model</span></span>


## <a name="requirements"></a><span data-ttu-id="c8cd1-114">需求</span><span class="sxs-lookup"><span data-stu-id="c8cd1-114">Requirements</span></span>

<span data-ttu-id="c8cd1-115">您只能在啟用它的 SharePoint 文件庫中建立表單處理模型。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-115">You can only create a form processing model in SharePoint document libraries in which it is enabled.</span></span> <span data-ttu-id="c8cd1-116">如果已啟用表單處理，您就可以在文件庫中的 [**自動化**] 功能表上看到 [ **AI** **產生器] 的「建立表單處理模型**」。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-116">If form processing is enabled, you will be able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="c8cd1-117">如果您需要在文件庫上啟用處理，請與您的系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-117">If you need from processing enabled on your document library, contact your admin.</span></span>

 ![建立 AI 產生器模型](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="c8cd1-119">步驟1：建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="c8cd1-119">Step 1: Create a Form Processing model</span></span>

<span data-ttu-id="c8cd1-120">建立表單處理模型的第一個步驟是將其命名為 [定義新的內容類型]，並為其建立新的文件庫視圖。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-120">The first step in creating a form processing model is to name it to create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="c8cd1-121">在文件庫中，選取 [**自動化**] 功能表，選取 [ **AI**產生器]，然後選取 [**建立表單處理模型**]。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-121">In your document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![建立 AI 產生器模型](../media/content-understanding/create-ai-builder-model.png)</br>
2. <span data-ttu-id="c8cd1-123">在 [**新增表單處理模型**] 窗格的 [**名稱**] 欄位中，輸入模型 (的名稱，例如，[*採購訂單*]) 。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![新表單處理模型](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="c8cd1-125">當您建立表單處理模型時，會建立新的 SharePoint 內容類型。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-125">When you create a form processing model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="c8cd1-126">SharePoint 內容類型代表具有共同特性並共用該特定內容之一組欄或中繼資料屬性的檔類別。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="c8cd1-127">SharePoint 內容類型是透過[內容類型庫]()進行管理。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="c8cd1-128">如果您想要將此模型對應至 SharePoint 內容類型庫中的現有內容類型，以使用其架構，請選取 [**高級設定**]。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="c8cd1-129">您的模型會在文件庫中為解壓縮的資料建立新的視圖。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-129">Your model will create a new view in your document library for your extracted data.</span></span> <span data-ttu-id="c8cd1-130">如果您不想讓它成為預設視圖，請取消選取 **[將此視圖設定為預設值**]。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>
5. <span data-ttu-id="c8cd1-131">選取 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-131">Select **Create**.</span></span>


## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="c8cd1-132">步驟2：新增及分析檔</span><span class="sxs-lookup"><span data-stu-id="c8cd1-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="c8cd1-133">在您建立新的表單處理模型之後，瀏覽器將會開啟新的 PowerApps AI Builder 表單處理模型頁面。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-133">After you create your new form processing model, your browser will open a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="c8cd1-134">在此頁面上，您可以新增及分析您的範例檔。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!Note]
> <span data-ttu-id="c8cd1-135">在尋找要使用的範例檔案時，請參閱[表單處理模型輸入檔需求和優化秘訣](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 

1. <span data-ttu-id="c8cd1-137">按一下 [**新增檔**] 以開始新增分析的範例檔，以決定可提取的命名值配對。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-137">Click **Add documents** to begin adding example documents that are analyzed to determine what named value pairs can be extracted.</span></span> <span data-ttu-id="c8cd1-138">您可以選擇 [**從本機儲存區上傳**]、[ **SharePoint**] 或 [ **Azure Blob 儲存區**]。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-138">You can choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="c8cd1-139">您至少需要使用五個檔案進行訓練。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-139">You will need to use at least five files for training.</span></span>
2. <span data-ttu-id="c8cd1-140">新增檔案之後，請選取 [**分析**]，檢查任何常見的資訊是否為所有檔案。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-140">After adding your files, select **Analyze** to check for any information that is common is all files.</span></span> <span data-ttu-id="c8cd1-141">請注意，這可能需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-141">Note that this may take several minutes to complete.</span></span></br> 
 
    ![分析檔](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="c8cd1-143">分析完畢之後，在 [**選取您要儲存的表單欄位**] 頁面上，按一下檔案以查看偵測到的欄位。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-143">After they have been analyzed, in the **Select the form fields you want to save** page, click the file to see the fields that were detected.</span></span></br>

    ![選取表單域](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="c8cd1-145">步驟3：選取表單欄位</span><span class="sxs-lookup"><span data-stu-id="c8cd1-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="c8cd1-146">分析檔中的欄位後，您現在可以查看找到的欄位，以及您想要儲存的欄位。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-146">After analyzing your documents for fields, you can now see which fields were found, and which ones you want to save.</span></span> <span data-ttu-id="c8cd1-147">儲存的欄位將顯示為模型文件庫視圖中的欄，並且會顯示從每個檔中解壓縮的值。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-147">Saved fields will display as columns in your model's document library view and will show the values extracted from each document.</span></span>

1. <span data-ttu-id="c8cd1-148">下一個頁面會顯示其中一個範例檔案，並會反白顯示系統自動偵測到的所有一般欄位。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-148">The next page will display one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![選取表單域](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="c8cd1-150">選取您要儲存的欄位，然後選取核取方塊以確認您的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-150">Select the fields you want to save, and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="c8cd1-151">例如，在 [採購訂單模型] 中，您可以選擇選取 [*日期*]、[ *PO*] 和 [*總計*] 欄位。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-151">For example, in the Purchase Order model, you can choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="c8cd1-152">請注意，您也可以選擇重新命名欄位。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![選取 PO#](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="c8cd1-154">若 analysis 未偵測到欄位，您仍然可以選擇新增欄位。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="c8cd1-155">反白顯示您想要解壓縮的資訊，並在 [名稱] 方塊中輸入您要指定的名稱。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-155">Highlight the information you want to extract, and in the name box type in the name you want to give it.</span></span> <span data-ttu-id="c8cd1-156">然後選取 [檢查]。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-156">Then select the check.</span></span> <span data-ttu-id="c8cd1-157">請注意，您必須在其餘的範例檔案中確認未檢查的欄位。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-157">Note that you will need to confirm undetected fields in your remaining example files.</span></span>
4. <span data-ttu-id="c8cd1-158">選取您要儲存的欄位後，請按一下 [**確認欄位**]。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-158">Click **Confirm fields** after you have selected the fields you want to save.</span></span> </br>
 
    ![確認欄位](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="c8cd1-160">在 [**選取您要儲存的表單欄位**] 頁面上，它會顯示您所選取的欄位數目。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-160">On the **Select the form fields you want to save** page, it will show the number of fields you have selected.</span></span> <span data-ttu-id="c8cd1-161">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="c8cd1-162">步驟4：訓練及測試您的模型</span><span class="sxs-lookup"><span data-stu-id="c8cd1-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="c8cd1-163">選取您想要儲存的欄位後，**模型摘要**頁面可讓您訓練及測試模型。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-163">After selecting the fields you want to save, the **Model Summary** page will let you train and test your model.</span></span>

1. <span data-ttu-id="c8cd1-164">在 [**模型摘要**] 頁面上，儲存的欄位將會顯示在 [**選取的欄位**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="c8cd1-165">選取 [**訓練**]，以在您的範例檔案上開始訓練。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="c8cd1-166">請注意，這可能需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-166">Note that this may take a few minutes to complete.</span></span></br>
    <span data-ttu-id="c8cd1-167">![確認欄位](../media/content-understanding/select-fields-train.png)</span><span class="sxs-lookup"><span data-stu-id="c8cd1-167">![Confirm fields](../media/content-understanding/select-fields-train.png)</span></span></br> 
2. <span data-ttu-id="c8cd1-168">當您看到訓練已完成的通知時，請選取 [**移至詳細資料] 頁面**。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 
3. <span data-ttu-id="c8cd1-169">在 [**模型詳細資料**] 頁面上，您可以選擇 [**快速測試**] 以測試模型的運作方式。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="c8cd1-170">這可讓您將檔案拖放至頁面，查看是否偵測到欄位。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="c8cd1-171">步驟5：發佈您的模型</span><span class="sxs-lookup"><span data-stu-id="c8cd1-171">Step 5: Publish your model</span></span>



1. <span data-ttu-id="c8cd1-172">如果您對模型結果滿意，請選取 [**發佈**] 以供使用。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-172">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>
2. <span data-ttu-id="c8cd1-173">發行模型之後，請選取 [**使用模型**]。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-173">After the model published, select **Use model**.</span></span> <span data-ttu-id="c8cd1-174">這會建立 PowerAutomate 流程，它會在您的 SharePoint 文件庫中執行，並會解壓縮已在模型中識別的欄位。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-174">This creates a PowerAutomate flow that will run in your SharePoint document library and will extract the fields that have been identified in the model.</span></span> <span data-ttu-id="c8cd1-175">選取 [**建立流程**]。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-175">Select **Create Flow**.</span></span>  
3. <span data-ttu-id="c8cd1-176">完成後，您會看到訊息**您的流程已成功建立**。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-176">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="c8cd1-177">步驟6：使用您的模型</span><span class="sxs-lookup"><span data-stu-id="c8cd1-177">Step 6: Use your model</span></span>

<span data-ttu-id="c8cd1-178">在發佈模型並建立其 PowerAutomate 流程之後，您可以在 SharePoint 文件庫中使用您的模型。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-178">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="c8cd1-179">在發佈模型之後，請選取 [**移至 SharePoint** ] 以移至您的文件庫。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-179">After publishing your model , select **Go to SharePoint** to go to your document library.</span></span>
2. <span data-ttu-id="c8cd1-180">在您的文件庫模型視圖上，請注意，您所選取的欄位現在會顯示為欄。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-180">On your document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![套用模型的文件庫](../media/content-understanding/doc-lib-view.png)</br> 

    <span data-ttu-id="c8cd1-182">另外請注意，[**檔**] 旁邊的資訊連結會指出表單處理模型已套用至此文件庫。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-182">Also notice that the information link next to **Documents** will note that a forms processing model is applied to this document library.</span></span>

    ![提取](../media/content-understanding/info-button.png)</br>  

3. <span data-ttu-id="c8cd1-184">將檔案上傳至文件庫。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-184">Upload files to your document library.</span></span> <span data-ttu-id="c8cd1-185">模型識別為其內容類型的任何檔案，都將會在您的視圖中列出檔案，並將提取的資料顯示在欄中。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-185">Any files that the model identifies as it's content type will list the files in your view, and will display the extracted data in the columns.</span></span></br>

    ![提取](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a><span data-ttu-id="c8cd1-187">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c8cd1-187">See Also</span></span>
  
[<span data-ttu-id="c8cd1-188">電源自動化檔</span><span class="sxs-lookup"><span data-stu-id="c8cd1-188">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="c8cd1-189">訓練：使用 AI 產生器改進商務效能</span><span class="sxs-lookup"><span data-stu-id="c8cd1-189">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




