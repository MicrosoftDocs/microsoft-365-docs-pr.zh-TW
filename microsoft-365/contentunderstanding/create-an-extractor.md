---
title: 建立擷取器
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 了解如何在 Microsoft SharePoint Syntex 中建立擷取器。
ms.openlocfilehash: b0b03d0e8804097f34f9cd5b17504263097d8696
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242497"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="1842e-103">在 Microsoft SharePoint Syntex 中建立擷取器</span><span class="sxs-lookup"><span data-stu-id="1842e-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="1842e-104">在建立分類器模型以自動識別和分類特定文件類型之前或之後，您可以選擇將擷取器新增至模型，以從這些文件中提取特定資訊。</span><span class="sxs-lookup"><span data-stu-id="1842e-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="1842e-105">例如，您可能會想要模型不僅能識別新增至文件庫的所有 *續約* 文件，還能在文件庫中將每份文件的 *服務開始日期* 顯示為欄值。</span><span class="sxs-lookup"><span data-stu-id="1842e-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="1842e-106">您必須為要擷取之文件的每個實體建立擷取器。</span><span class="sxs-lookup"><span data-stu-id="1842e-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="1842e-107">在我們的範例中，我們想要擷取由模型所識別之每份 **續約** 文件的 **服務開始日期** 。</span><span class="sxs-lookup"><span data-stu-id="1842e-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="1842e-108">我們希望能夠在所有  **續約** 文件的文件庫中看到一個檢視，並有欄位顯示每份文件的 **服務開始** 日期值。</span><span class="sxs-lookup"><span data-stu-id="1842e-108">We want to be able to see a view in the document library of all  **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="1842e-109">若要建立擷取器，您可以使用先前上傳來訓練分類程式的同一個檔案。</span><span class="sxs-lookup"><span data-stu-id="1842e-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="1842e-110">為您的擷取器命名</span><span class="sxs-lookup"><span data-stu-id="1842e-110">Name your extractor</span></span>

1. <span data-ttu-id="1842e-111">在模型首頁的 **[建立及訓練擷取器]** 磚中，按一下 **[訓練擷取器]**。</span><span class="sxs-lookup"><span data-stu-id="1842e-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="1842e-112">在 **[新增實體擷取器]** 畫面的 **[新擷取器名稱]** 欄位中輸入您的擷取器名稱。</span><span class="sxs-lookup"><span data-stu-id="1842e-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="1842e-113">例如，如果您想要從每個續約文件擷取服務開始日期，請將它命名為 **服務開始日期**。</span><span class="sxs-lookup"><span data-stu-id="1842e-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="1842e-114">您也可以選擇重複使用之前建立的欄位 (例如受管理的中繼資料欄)。</span><span class="sxs-lookup"><span data-stu-id="1842e-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
> [!NOTE]
> <span data-ttu-id="1842e-115">如果您建立新的提取清單，請選取 **[新增欄位輸入]**，然後選擇 **[單行文字]** 中的最大字元數上限為255。</span><span class="sxs-lookup"><span data-stu-id="1842e-115">If you create a new extractor, then select **New column type** and choose **Single line of text**, the maximum character limit is 255.</span></span> <span data-ttu-id="1842e-116">任何您所輸入超過限制的字元都會被截斷。</span><span class="sxs-lookup"><span data-stu-id="1842e-116">Any characters that you type exceeding the limit get truncated.</span></span> 
3. <span data-ttu-id="1842e-117">完成後，按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="1842e-117">When you're done, click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="1842e-118">新增標籤</span><span class="sxs-lookup"><span data-stu-id="1842e-118">Add a label</span></span>

<span data-ttu-id="1842e-119">下一個步驟是在範例訓練檔案中，將您要擷取的實體加上標籤。</span><span class="sxs-lookup"><span data-stu-id="1842e-119">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="1842e-120">建立擷取器會開啟 [擷取] 頁面。</span><span class="sxs-lookup"><span data-stu-id="1842e-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="1842e-121">您會在這裡看到範例檔案清單，而清單上的第一個檔案會顯示在檢視器中。</span><span class="sxs-lookup"><span data-stu-id="1842e-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="1842e-122">從檢視器中，選取您要從檔案中擷取的資料。</span><span class="sxs-lookup"><span data-stu-id="1842e-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="1842e-123">例如，如果您想要擷取 *[開始服務日期]*，請醒目提示第一個檔案中的日期值 (*[2019 年 10 月 14 日星期一]*)。</span><span class="sxs-lookup"><span data-stu-id="1842e-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="1842e-124">然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1842e-124">and then click **Save**.</span></span>  <span data-ttu-id="1842e-125">您應該會在 **[標籤]** 欄下的 [標籤範例清單] 中看到檔案的值。</span><span class="sxs-lookup"><span data-stu-id="1842e-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="1842e-126">選取 **[下一個檔案]** 以自動儲存，並開啟檢視器清單中的下一個檔案。</span><span class="sxs-lookup"><span data-stu-id="1842e-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="1842e-127">或者，選取 **[儲存]**，然後從 **[標籤範例]** 清單中選取另一個檔案。</span><span class="sxs-lookup"><span data-stu-id="1842e-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="1842e-128">在檢視器中，重複步驟 1 和 2，直到您將標籤儲存在所有五個檔案中。</span><span class="sxs-lookup"><span data-stu-id="1842e-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![進階設定](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="1842e-130">當您在五個檔案上加上標籤後，系統會顯示通知橫幅，通知您移至 [訓練]。</span><span class="sxs-lookup"><span data-stu-id="1842e-130">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="1842e-131">您可以選擇將更多文件加上標籤，或繼續前往訓練。</span><span class="sxs-lookup"><span data-stu-id="1842e-131">You can choose to more label more documents or advance to training.</span></span> 

### <a name="use-find-to-search-your-file"></a><span data-ttu-id="1842e-132">使用尋找來搜尋您的檔案</span><span class="sxs-lookup"><span data-stu-id="1842e-132">Use Find to search your file</span></span>
<span data-ttu-id="1842e-133">您可以使用<b>尋找</b>功能來搜尋您要加標籤文件中的實體。</span><span class="sxs-lookup"><span data-stu-id="1842e-133">You can use the <b>Find</b> feature to search for an entity in your document that you want to label.</span></span>

   ![在檔案中尋找](../media/content-understanding/find-feature.png) 

<span data-ttu-id="1842e-135">如果您要搜尋大型文件，或文件中有實體的多個執行個體，「尋找」功能就相當實用。</span><span class="sxs-lookup"><span data-stu-id="1842e-135">The Find feature is useful if you are searching a large document or if there are multiple instances of the entity in the document.</span></span> <span data-ttu-id="1842e-136">如果您發現多個執行個體，則可以在搜尋結果中選取您需要的一項，以移至檢視器中的該位置，以為其加標籤。</span><span class="sxs-lookup"><span data-stu-id="1842e-136">If you find multiple instances, you can select the one you need in the search results to go to that location in the viewer to label it.</span></span>


## <a name="add-an-explanation"></a><span data-ttu-id="1842e-137">新增說明</span><span class="sxs-lookup"><span data-stu-id="1842e-137">Add an explanation</span></span>

<span data-ttu-id="1842e-138">針對我們的範例，我們將建立一個說明，提供有關實體格式本身及其在範例文件中可能具有的變化的提示。</span><span class="sxs-lookup"><span data-stu-id="1842e-138">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="1842e-139">例如，日期值可以採用多種不同的格式，例如：</span><span class="sxs-lookup"><span data-stu-id="1842e-139">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="1842e-140">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="1842e-140">10/14/2019</span></span>
- <span data-ttu-id="1842e-141">2019 年 10 月 14 日</span><span class="sxs-lookup"><span data-stu-id="1842e-141">October 14, 2019</span></span>
- <span data-ttu-id="1842e-142">2019 年 10 月 14 日星期一</span><span class="sxs-lookup"><span data-stu-id="1842e-142">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="1842e-143">若要協助識別 *服務開始日期*，您可以建立模式說明。</span><span class="sxs-lookup"><span data-stu-id="1842e-143">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="1842e-144">在 [說明] 區段中，選取 **[新增]**，然後輸入名稱 (例如 *[日期]*)。</span><span class="sxs-lookup"><span data-stu-id="1842e-144">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="1842e-145">在 [類型] 中，選取 **[模式清單]**。</span><span class="sxs-lookup"><span data-stu-id="1842e-145">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="1842e-146">對於值，請提供其在範例檔案中顯示的日期變化。</span><span class="sxs-lookup"><span data-stu-id="1842e-146">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="1842e-147">例如，如果日期格式顯示為 0/00/0000，則輸入出現在文件中的所有變化，例如：</span><span class="sxs-lookup"><span data-stu-id="1842e-147">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="1842e-148">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="1842e-148">0/0/0000</span></span>
    - <span data-ttu-id="1842e-149">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="1842e-149">0/00/0000</span></span>
    - <span data-ttu-id="1842e-150">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="1842e-150">00/0/0000</span></span>
    - <span data-ttu-id="1842e-151">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="1842e-151">00/00/0000</span></span>
4. <span data-ttu-id="1842e-152">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1842e-152">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="1842e-153">如需深入了解說明類型，請參閱[說明類型](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview)。</span><span class="sxs-lookup"><span data-stu-id="1842e-153">For more learn more about explanation types, see [Explanation types](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="1842e-154">使用說明文件庫</span><span class="sxs-lookup"><span data-stu-id="1842e-154">Use the Explanation library</span></span>

<span data-ttu-id="1842e-155">若要建立日期等項目的說明，[使用說明文件庫](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library)比手動輸入所有變化要容易得多。</span><span class="sxs-lookup"><span data-stu-id="1842e-155">For creating explanations for items such as dates, it is easier to [use the explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) than to manually enter all variations.</span></span> <span data-ttu-id="1842e-156">說明文件庫是一組內建的片語和模式說明。</span><span class="sxs-lookup"><span data-stu-id="1842e-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="1842e-157">文件庫會嘗試提供所有格式的常用片語或模式清單，例如日期、電話號碼、郵遞區號等等。</span><span class="sxs-lookup"><span data-stu-id="1842e-157">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="1842e-158">在 *[服務開始日期]* 範例中，使用說明文件庫中，*[日期]* 的內建說明更有效率：</span><span class="sxs-lookup"><span data-stu-id="1842e-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="1842e-159">在 **[說明]** 區段中，選取 **[新增]**，然後選取 **[從說明文件庫]**。</span><span class="sxs-lookup"><span data-stu-id="1842e-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="1842e-160">從說明文件庫，選取 **[日期]**。</span><span class="sxs-lookup"><span data-stu-id="1842e-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="1842e-161">您可以檢視已辨識的所有日期變化。</span><span class="sxs-lookup"><span data-stu-id="1842e-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="1842e-162">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="1842e-162">Select **Add**.</span></span></br>

    ![說明文件庫](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="1842e-164">在 **[建立說明]** 頁面上，說明文件庫中的 *[日期]* 資訊會自動填入欄位。</span><span class="sxs-lookup"><span data-stu-id="1842e-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="1842e-165">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1842e-165">Select **Save**.</span></span></br>

    ![日期](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="1842e-167">訓練模型</span><span class="sxs-lookup"><span data-stu-id="1842e-167">Train the model</span></span> 

<span data-ttu-id="1842e-168">儲存說明後即會開始訓練。</span><span class="sxs-lookup"><span data-stu-id="1842e-168">Saving your explanation start the training.</span></span> <span data-ttu-id="1842e-169">如果您的模型有足夠的資訊可以從標籤的範例檔案擷取資料，您將會看到每個標示為 **[相符]** 的檔案。</span><span class="sxs-lookup"><span data-stu-id="1842e-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![相符](../media/content-understanding/match2.png) 

<span data-ttu-id="1842e-171">如果說明所需的資訊不足，無法找到您想要擷取的資料，每個檔案將會標籤為 **[不相符]**。</span><span class="sxs-lookup"><span data-stu-id="1842e-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="1842e-172">您可以按一下 **[不相符]** 檔案，以查看更多不相符原因的資訊。</span><span class="sxs-lookup"><span data-stu-id="1842e-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="1842e-173">新增其他說明</span><span class="sxs-lookup"><span data-stu-id="1842e-173">Add another explanation</span></span>

<span data-ttu-id="1842e-174">通常不相符是因為我們所提供的說明並未提供足夠的資訊，無法擷取服務開始日期值來符合我們加上標籤的檔案。</span><span class="sxs-lookup"><span data-stu-id="1842e-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="1842e-175">您可能需要編輯，或新增其他說明。</span><span class="sxs-lookup"><span data-stu-id="1842e-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="1842e-176">在我們的範例中，請注意，文字字串 *開始服務日期* 始終位於實際值之前。</span><span class="sxs-lookup"><span data-stu-id="1842e-176">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="1842e-177">若要協助識別服務開始日期，您必須建立片語說明。</span><span class="sxs-lookup"><span data-stu-id="1842e-177">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="1842e-178">在 [說明] 區段中，選取 **[新增]**，然後輸入名稱 (例如 *[前置詞字串]*)。</span><span class="sxs-lookup"><span data-stu-id="1842e-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="1842e-179">在 [類型] 中，選取 **[片語清單]**。</span><span class="sxs-lookup"><span data-stu-id="1842e-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="1842e-180">使用 *[服務開始日期]* 做為值。</span><span class="sxs-lookup"><span data-stu-id="1842e-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="1842e-181">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1842e-181">Select **Save**.</span></span>

    ![前置詞字串](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="1842e-183">再次訓練模型</span><span class="sxs-lookup"><span data-stu-id="1842e-183">Train the model again</span></span>

<span data-ttu-id="1842e-184">儲存說明之後即會再次開始訓練，這次使用範例中的兩個說明。</span><span class="sxs-lookup"><span data-stu-id="1842e-184">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="1842e-185">如果您的模型有足夠的資訊可以從標籤的範例檔案擷取資料，您會看到每個標示為 **[相符]** 的檔案。</span><span class="sxs-lookup"><span data-stu-id="1842e-185">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="1842e-186">如果您在標籤的檔案上再次收到 **[不相符]**，您可能需要建立其他說明，以提供模型以取得更多資訊來識別文件類型，或考慮變更現有的文件類型。</span><span class="sxs-lookup"><span data-stu-id="1842e-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="1842e-187">測試您的模型</span><span class="sxs-lookup"><span data-stu-id="1842e-187">Test your model</span></span>

<span data-ttu-id="1842e-188">如果您在標籤的範例檔案上收到 [相符]，您現在可以在剩餘未標籤的範例檔案上測試模型。</span><span class="sxs-lookup"><span data-stu-id="1842e-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="1842e-189">這是一個選用但有用的步驟，可透過在模型以前從未見過的檔案中進行測試來評估模型的「適合性」或就緒狀態。</span><span class="sxs-lookup"><span data-stu-id="1842e-189">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="1842e-190">從模型首頁中，按一下 **[測試]** 索引標籤。這會在未標籤的範例檔案上執行模型。</span><span class="sxs-lookup"><span data-stu-id="1842e-190">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="1842e-191">如果模型可以擷取所需的資訊，就會在 **[測試檔案]** 清單中顯示您的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="1842e-191">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="1842e-192">使用這項資訊可協助您判斷分類器識別文件的效能。</span><span class="sxs-lookup"><span data-stu-id="1842e-192">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![測試您的檔案](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="1842e-194">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1842e-194">See Also</span></span>
[<span data-ttu-id="1842e-195">建立分類器</span><span class="sxs-lookup"><span data-stu-id="1842e-195">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="1842e-196">說明類型</span><span class="sxs-lookup"><span data-stu-id="1842e-196">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="1842e-197">在建立擷取器時運用字詞庫分類法</span><span class="sxs-lookup"><span data-stu-id="1842e-197">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="1842e-198">文件了解概觀</span><span class="sxs-lookup"><span data-stu-id="1842e-198">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="1842e-199">套用模型</span><span class="sxs-lookup"><span data-stu-id="1842e-199">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="1842e-200">SharePoint Syntex 協助工具模式</span><span class="sxs-lookup"><span data-stu-id="1842e-200">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)
