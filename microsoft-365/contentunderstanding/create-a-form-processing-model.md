---
title: 建立表單處理模型
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 在 Microsoft SharePoint Syntex 中建立表單處理模型。
ms.openlocfilehash: 27e80a7b3626170e45ceaa55f1269e50d8fdab9e
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337262"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="3efc2-103">在 Microsoft SharePoint Syntex 中建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="3efc2-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>


<span data-ttu-id="3efc2-104">使用 [AI Builder](https://docs.microsoft.com/ai-builder/overview) - Microsoft PowerApps 中的功能- SharePoint Syntex 使用者可以直接從 SharePoint 文件庫建立[表單處理模型](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3efc2-104">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - SharePoint Syntex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="3efc2-105">建立表單處理模型涉及以下內容：</span><span class="sxs-lookup"><span data-stu-id="3efc2-105">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="3efc2-106">步驟 1：建立表單處理模型以建立內容類型</span><span class="sxs-lookup"><span data-stu-id="3efc2-106">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="3efc2-107">步驟 2：新增和分析範例檔案</span><span class="sxs-lookup"><span data-stu-id="3efc2-107">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="3efc2-108">步驟 3：選取您的表單欄位</span><span class="sxs-lookup"><span data-stu-id="3efc2-108">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="3efc2-109">步驟 4：訓練和測試您的模型</span><span class="sxs-lookup"><span data-stu-id="3efc2-109">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="3efc2-110">步驟 5：發佈您的模型</span><span class="sxs-lookup"><span data-stu-id="3efc2-110">Step 5: Publish your model</span></span>
 - <span data-ttu-id="3efc2-111">步驟 6：使用您的模型</span><span class="sxs-lookup"><span data-stu-id="3efc2-111">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="3efc2-112">需求</span><span class="sxs-lookup"><span data-stu-id="3efc2-112">Requirements</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>


<span data-ttu-id="3efc2-113">您只能在啟用此表單的 SharePoint 文件庫中建立表單處理模型。</span><span class="sxs-lookup"><span data-stu-id="3efc2-113">You can only create a form processing model in SharePoint document libraries for which it is enabled.</span></span> <span data-ttu-id="3efc2-114">如果已啟用表單處理，您可在文件庫的 **[自動執行]** 功能表底下看到 **AI Builder\*\*\*\*「建立表單處理模型」**。</span><span class="sxs-lookup"><span data-stu-id="3efc2-114">If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="3efc2-115">如果您需要在文件庫啟用處理，您必須聯繫您的 SharePoint 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="3efc2-115">If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![建立 AI Builder 模型](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="3efc2-117">步驟 1：建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="3efc2-117">Step 1: Create a form Processing model</span></span>

<span data-ttu-id="3efc2-118">建立表單處理模型的第一步是命名並建立定義新內容類型，並為其建立新文件庫檢視。</span><span class="sxs-lookup"><span data-stu-id="3efc2-118">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="3efc2-119">從文件庫中，選取 **[自動化]** 選單，選取 **[AI Builder]**，然後選取 **[建立表單處理模型]**。</span><span class="sxs-lookup"><span data-stu-id="3efc2-119">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![建立模型](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="3efc2-121">在 **[新表單處理模型]** 窗格的 **[名稱]** 欄位中，輸入您的模型名稱（例如 *[採購單]*）。</span><span class="sxs-lookup"><span data-stu-id="3efc2-121">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![新表單處理模型](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="3efc2-123">建立表單處理模型時，將建立新 SharePoint 內容類型。</span><span class="sxs-lookup"><span data-stu-id="3efc2-123">When you create a form processing model, you create a new SharePoint content type.</span></span> <span data-ttu-id="3efc2-124">SharePoint 內容類型表示具有共同特徵並共用特定內容的欄或中繼資料屬性的文件類別。</span><span class="sxs-lookup"><span data-stu-id="3efc2-124">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="3efc2-125">透過[內容類型庫]()管理 [SharePoint 內容類型]。</span><span class="sxs-lookup"><span data-stu-id="3efc2-125">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="3efc2-126">如果您想要將這個模型對應到 SharePoint 內容類型庫中現有的內容類型以使用其架構，請選取 **[進階設定]**。</span><span class="sxs-lookup"><span data-stu-id="3efc2-126">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="3efc2-127">您的模型在文件庫中為選取的資料建立新檢視。</span><span class="sxs-lookup"><span data-stu-id="3efc2-127">Your model creates a new view in your document library for your extracted data.</span></span> <span data-ttu-id="3efc2-128">如果不希望它成為預設檢視，請取消選擇 **[將檢視設定為預設檢視]**。</span><span class="sxs-lookup"><span data-stu-id="3efc2-128">If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="3efc2-129">選取 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="3efc2-129">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="3efc2-130">步驟 2：新增和分析範例文件</span><span class="sxs-lookup"><span data-stu-id="3efc2-130">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="3efc2-131">建立新表單處理模型後，瀏覽器將打開新 PowerApps AI Builder 表單處理模型頁面。</span><span class="sxs-lookup"><span data-stu-id="3efc2-131">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="3efc2-132">您可以在這個頁面上新增及分析範例文件。</span><span class="sxs-lookup"><span data-stu-id="3efc2-132">On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="3efc2-133">尋找要使用的範例檔案時，請參閱[表單處理模型輸入文件需求和優化秘訣](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)。</span><span class="sxs-lookup"><span data-stu-id="3efc2-133">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="3efc2-135">選取 **[新增文件]** 開始新增範例文件，分析它們以決定可擷取的命名值對。</span><span class="sxs-lookup"><span data-stu-id="3efc2-135">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted.</span></span> <span data-ttu-id="3efc2-136">然後，您可以選擇 **[從本機儲存空間]**、**SharePoint** 或 **[Azure Blob 儲存體]** 上傳。</span><span class="sxs-lookup"><span data-stu-id="3efc2-136">You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="3efc2-137">您至少需要使用五個檔案進行訓練。</span><span class="sxs-lookup"><span data-stu-id="3efc2-137">You need to use at least five files for training.</span></span>

2. <span data-ttu-id="3efc2-138">新增檔案後，請選取 **[分析]**，檢查是否有任何常見的資訊為 [所有檔案]。</span><span class="sxs-lookup"><span data-stu-id="3efc2-138">After adding files, select **Analyze** to check for any information common is all files.</span></span> <span data-ttu-id="3efc2-139">這可能需要數分鐘的時間來完成。</span><span class="sxs-lookup"><span data-stu-id="3efc2-139">This may take several minutes to complete.</span></span></br> 
 
    ![分析檔案](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="3efc2-141">檔案分析完成之後，在 **[選取您要儲存的表單欄位]** 頁面選取檔案以檢視檢測到的欄位。</span><span class="sxs-lookup"><span data-stu-id="3efc2-141">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![選取表單欄位](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="3efc2-143">步驟 3：選取您的表單欄位</span><span class="sxs-lookup"><span data-stu-id="3efc2-143">Step 3: Select your form fields</span></span>

<span data-ttu-id="3efc2-144">分析完檔案的欄位之後，您現在可以查看找到的欄位，並確定要儲存的欄位。</span><span class="sxs-lookup"><span data-stu-id="3efc2-144">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save.</span></span> <span data-ttu-id="3efc2-145">儲存的欄位會在模型的 [文件庫] 檢視中顯示為欄，並顯示每份文件中擷取的值。</span><span class="sxs-lookup"><span data-stu-id="3efc2-145">Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="3efc2-146">下一頁將顯示其中一個範例檔案，並將醒目顯示系統自動偵測到的所有一般欄位。</span><span class="sxs-lookup"><span data-stu-id="3efc2-146">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![[選取欄位] 頁面](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="3efc2-148">選取您要儲存的欄位，然後選取該核取方塊以確認您的選擇。</span><span class="sxs-lookup"><span data-stu-id="3efc2-148">Select the fields that you want to save and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="3efc2-149">例如，在 [採購單模型] 中，選擇選取 *[日期]*、*PO*，以及 *[總計]* 欄位。</span><span class="sxs-lookup"><span data-stu-id="3efc2-149">For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="3efc2-150">請注意，可以隨您意願選擇重新命名欄位。</span><span class="sxs-lookup"><span data-stu-id="3efc2-150">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![選取 PO#](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="3efc2-152">如果分析未偵測到欄位，您仍然可以選擇將其新增。</span><span class="sxs-lookup"><span data-stu-id="3efc2-152">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="3efc2-153">亮顯您要擷取的資訊，然後在名稱方塊中輸入您想要的名稱。</span><span class="sxs-lookup"><span data-stu-id="3efc2-153">Highlight the information you want to extract, and in the name box type in the name you want.</span></span> <span data-ttu-id="3efc2-154">然後選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3efc2-154">Then select the check box.</span></span> <span data-ttu-id="3efc2-155">請注意，您需要確認剩餘範例檔案中未偵測到的欄位。</span><span class="sxs-lookup"><span data-stu-id="3efc2-155">Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="3efc2-156">選取您要儲存的欄位之後，請按一下 **[確認欄位]**。</span><span class="sxs-lookup"><span data-stu-id="3efc2-156">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![選取欄位之後確認欄位](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="3efc2-158">在 **[選取您要儲存的表單欄位]** 頁，會顯示您選取的欄位數量。</span><span class="sxs-lookup"><span data-stu-id="3efc2-158">On the **Select the form fields you want to save** page, it shows the number of fields you have selected.</span></span> <span data-ttu-id="3efc2-159">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3efc2-159">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="3efc2-160">步驟 4：訓練和測試您的模型</span><span class="sxs-lookup"><span data-stu-id="3efc2-160">Step 4: Train and test your model</span></span>

<span data-ttu-id="3efc2-161">選取您要儲存的欄位之後， **[模型摘要]** 頁面可讓您訓練並測試模型。</span><span class="sxs-lookup"><span data-stu-id="3efc2-161">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="3efc2-162">在 **[模型摘要]** 頁面上，已儲存的欄位會顯示在 **[已選取欄位]** 區段中。</span><span class="sxs-lookup"><span data-stu-id="3efc2-162">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="3efc2-163">選取 **[訓練]** 以開始訓練您的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="3efc2-163">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="3efc2-164">請注意，這可能需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="3efc2-164">Note that this may take a few minutes to complete.</span></span></br>

     ![選取欄位訓練](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="3efc2-166">當您看到訓練已完成的通知時，選取 **[移至詳細資訊頁面]**。</span><span class="sxs-lookup"><span data-stu-id="3efc2-166">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="3efc2-167">在 **[模型詳細資料]** 頁面上，您可以選取 **[快速測試]** 來選擇測試模型的運作方式。</span><span class="sxs-lookup"><span data-stu-id="3efc2-167">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="3efc2-168">這可讓您將檔案拖放至頁面，並查看是否已偵測欄位。</span><span class="sxs-lookup"><span data-stu-id="3efc2-168">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![確認欄位](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="3efc2-170">當您看到訓練已完成的通知時，選取 **[移至詳細資訊頁面]**。</span><span class="sxs-lookup"><span data-stu-id="3efc2-170">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="3efc2-171">在 **[模型詳細資料]** 頁面上，選取 **[快速測試]** 來選擇測試模型的運作方式。</span><span class="sxs-lookup"><span data-stu-id="3efc2-171">On the **Model details** page, choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="3efc2-172">這可讓您將檔案拖放至頁面，並查看是否已偵測欄位。</span><span class="sxs-lookup"><span data-stu-id="3efc2-172">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="3efc2-173">步驟 5：發佈您的模型</span><span class="sxs-lookup"><span data-stu-id="3efc2-173">Step 5: Publish your model</span></span>

1. <span data-ttu-id="3efc2-174">如果您對模型結果感到滿意，請選取 **[發佈]** 以使其可用。</span><span class="sxs-lookup"><span data-stu-id="3efc2-174">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="3efc2-175">在模型發佈之後，選取 **[使用模型]**。</span><span class="sxs-lookup"><span data-stu-id="3efc2-175">After the model is published, select **Use model**.</span></span> <span data-ttu-id="3efc2-176">這將建立一個可以在您的 SharePoint 文件庫中運行的 PowerAutomate流程，並選取在模型中標識的欄位，然後選取 **[建立流程]**。</span><span class="sxs-lookup"><span data-stu-id="3efc2-176">This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="3efc2-177">完成時，您會看到 **「流程已成功建立」** 的訊息。</span><span class="sxs-lookup"><span data-stu-id="3efc2-177">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="3efc2-178">步驟 6：使用您的模型</span><span class="sxs-lookup"><span data-stu-id="3efc2-178">Step 6: Use your model</span></span>

<span data-ttu-id="3efc2-179">發佈模型並建立 PowerAutomate 流程之後，您就可以在 SharePoint 文件庫中使用您的模型。</span><span class="sxs-lookup"><span data-stu-id="3efc2-179">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="3efc2-180">發佈模型之後，請選取 **[移至 SharePoint]** 以移至您的文件庫。</span><span class="sxs-lookup"><span data-stu-id="3efc2-180">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="3efc2-181">請注意，在 [文件庫模型] 檢視中，您選取的欄位目前顯示為欄。</span><span class="sxs-lookup"><span data-stu-id="3efc2-181">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![已套用文件庫模型](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="3efc2-183">請注意，**[文件]** 旁邊的資訊連結注釋表單處理模型已套用至此文件庫。</span><span class="sxs-lookup"><span data-stu-id="3efc2-183">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![[資訊] 按鈕](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="3efc2-185">上傳檔案至您的文件庫。</span><span class="sxs-lookup"><span data-stu-id="3efc2-185">Upload files to your document library.</span></span> <span data-ttu-id="3efc2-186">模型標識為其內容類型的任何檔案都會列出檢視中的檔案，並在欄中顯示選取的資料。</span><span class="sxs-lookup"><span data-stu-id="3efc2-186">Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![完成](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="3efc2-188">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3efc2-188">See Also</span></span>
  
[<span data-ttu-id="3efc2-189">Power Automate 文件</span><span class="sxs-lookup"><span data-stu-id="3efc2-189">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="3efc2-190">訓練：使用 AI Builder 改善商務效能</span><span class="sxs-lookup"><span data-stu-id="3efc2-190">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
