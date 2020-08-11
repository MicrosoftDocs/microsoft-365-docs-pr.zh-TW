---
title: '建立解壓縮程式 (預覽) '
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
description: 瞭解如何建立提取程式
ms.openlocfilehash: 64dede9f6613da82c65ca12c6c335a25301f5b9e
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612759"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="06669-103">建立解壓縮程式 (預覽) </span><span class="sxs-lookup"><span data-stu-id="06669-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="06669-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="06669-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="06669-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="06669-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="06669-106">在您建立分類器模型以自動化特定檔案類型的身分識別和分類的情況下，您可以選擇將擷取器新增至您的模型，以從這些檔中拉出特定資訊。</span><span class="sxs-lookup"><span data-stu-id="06669-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="06669-107">例如，您可能想要模型不僅識別所有已新增至文件庫的*合約更新*檔，還會將每個檔的*服務開始日期*顯示為文件庫中的欄。</span><span class="sxs-lookup"><span data-stu-id="06669-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="06669-108">您必須為想要提取之檔中的每個實體建立解壓縮程式。</span><span class="sxs-lookup"><span data-stu-id="06669-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="06669-109">在我們的範例中，我們想要針對模型所識別的每個*合約更新*檔，解壓縮*服務的開始日期*。</span><span class="sxs-lookup"><span data-stu-id="06669-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="06669-110">我們想要能夠在所有*合約更新*檔的文件庫中查看視圖，並顯示顯示每個檔之服務開始日期值的欄。</span><span class="sxs-lookup"><span data-stu-id="06669-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="06669-111">在建立提取程式之前，您必須[新增](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files)您所需的範例檔案，以協助訓練模型識別您想要提取的資訊。</span><span class="sxs-lookup"><span data-stu-id="06669-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="06669-112">請使用您用來建立分類器的相同範例檔案。</span><span class="sxs-lookup"><span data-stu-id="06669-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="06669-113">命名解壓縮程式</span><span class="sxs-lookup"><span data-stu-id="06669-113">Name your extractor</span></span>

1. <span data-ttu-id="06669-114">在模型首頁上，按一下 [**建立及火車擷取器**] 磚中的 [**訓練提取**程式]。</span><span class="sxs-lookup"><span data-stu-id="06669-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="06669-115">在 [**新增實體解壓縮**程式] 畫面上，在 [**新的解壓縮程式名稱**] 欄位中輸入解壓縮程式的名稱。</span><span class="sxs-lookup"><span data-stu-id="06669-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="06669-116">例如，如果我們想要從每個合約更新檔中解壓縮服務的開始日期，我們可以命名 it**服務的開始日期**。</span><span class="sxs-lookup"><span data-stu-id="06669-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="06669-117">按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06669-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="06669-118">新增標籤</span><span class="sxs-lookup"><span data-stu-id="06669-118">Add a label</span></span>

<span data-ttu-id="06669-119">下一步是將您想要在範例訓練檔案中解壓縮的資訊加上標籤。</span><span class="sxs-lookup"><span data-stu-id="06669-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="06669-120">建立解壓縮程式將會開啟 [解壓縮程式] 頁面，您會在其中看到範例檔案的清單，並在檢視器中顯示清單上的第一個檔案。</span><span class="sxs-lookup"><span data-stu-id="06669-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="06669-121">在檢視器中，選取您要從檔案中解壓縮的資料。</span><span class="sxs-lookup"><span data-stu-id="06669-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="06669-122">例如，如果您想要解壓縮的*開始服務日期*，您會在第一個檔案 (*星期一，10月14日，2019*) 中，反白顯示它的日期值。</span><span class="sxs-lookup"><span data-stu-id="06669-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="06669-123">然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06669-123">Then click **Save**.</span></span>  <span data-ttu-id="06669-124">您會在 [**標籤**] 欄底下的 [標籤範例] 清單中看到檔案的值顯示。</span><span class="sxs-lookup"><span data-stu-id="06669-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="06669-125">選取 **[下一個**檔案] 以自動儲存並開啟檢視器清單中的下一個檔案，您也可以選取 [**儲存**]，然後從 [**標記的範例**] 清單中選取另一個檔案。</span><span class="sxs-lookup"><span data-stu-id="06669-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="06669-126">在檢視器中重複步驟1和2，然後在五個檔案中儲存標籤之後，才執行此動作。</span><span class="sxs-lookup"><span data-stu-id="06669-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![進階設定](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="06669-128">新增負數範例</span><span class="sxs-lookup"><span data-stu-id="06669-128">Add a negative example</span></span>

<span data-ttu-id="06669-129">類似于建立分類器時，新增否定性範例檔案的方式，您需要為提取程式新增否定性範例。</span><span class="sxs-lookup"><span data-stu-id="06669-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="06669-130">在我們的範例中，它應該是不含服務開始日期值的檔案。</span><span class="sxs-lookup"><span data-stu-id="06669-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="06669-131">從 [**標示的範例**] 清單中，選取負數範例。</span><span class="sxs-lookup"><span data-stu-id="06669-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="06669-132">在檢視器的文章頂端，選取 [**沒有標籤**]。</span><span class="sxs-lookup"><span data-stu-id="06669-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="06669-133">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06669-133">Click **Save**.</span></span>
 
<span data-ttu-id="06669-134">當您已標示五個檔案之後，就會顯示通知橫幅，告訴您移至訓練。</span><span class="sxs-lookup"><span data-stu-id="06669-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="06669-135">您可以選擇更多檔或換片訓練。</span><span class="sxs-lookup"><span data-stu-id="06669-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="06669-136">新增說明</span><span class="sxs-lookup"><span data-stu-id="06669-136">Add an explanation</span></span>

<span data-ttu-id="06669-137">在我們的範例中，我們將建立說明，提供實體格式本身的提示，以及範例檔中可能具有的變化。</span><span class="sxs-lookup"><span data-stu-id="06669-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="06669-138">例如，date 值可以是多種不同的格式，例如：</span><span class="sxs-lookup"><span data-stu-id="06669-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="06669-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="06669-139">10/14/2019</span></span>
- <span data-ttu-id="06669-140">2019 年 10 月 14 日</span><span class="sxs-lookup"><span data-stu-id="06669-140">October 14, 2019</span></span>
- <span data-ttu-id="06669-141">2019年10月14日星期一</span><span class="sxs-lookup"><span data-stu-id="06669-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="06669-142">為了協助識別*服務的開始日期*，您可以建立一個模式說明。</span><span class="sxs-lookup"><span data-stu-id="06669-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="06669-143">在 [說明] 區段中，選取 [**新增**]，然後輸入名稱 (例如， *Date*) 。</span><span class="sxs-lookup"><span data-stu-id="06669-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="06669-144">選取 [類型] 清單中的 [**模式] 清單**。</span><span class="sxs-lookup"><span data-stu-id="06669-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="06669-145">針對此值，您需要提供日期變化顯示在範例檔案中。</span><span class="sxs-lookup"><span data-stu-id="06669-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="06669-146">例如，如果您的日期格式顯示為0/00/0000，您可以輸入可能出現在檔中的任何變化，例如：</span><span class="sxs-lookup"><span data-stu-id="06669-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="06669-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="06669-147">0/0/0000</span></span>
    - <span data-ttu-id="06669-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="06669-148">0/00/0000</span></span>
    - <span data-ttu-id="06669-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="06669-149">00/0/0000</span></span>
    - <span data-ttu-id="06669-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="06669-150">00/00/0000</span></span>
4. <span data-ttu-id="06669-151">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="06669-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="06669-152">使用說明程式庫</span><span class="sxs-lookup"><span data-stu-id="06669-152">Use the Explanation library</span></span>

<span data-ttu-id="06669-153">若要建立諸如日期等專案的說明，使用 [說明] 程式庫比手動輸入所有變化更為容易。</span><span class="sxs-lookup"><span data-stu-id="06669-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="06669-154">說明庫是一組預先建立的片語和模式說明。</span><span class="sxs-lookup"><span data-stu-id="06669-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="06669-155">文件庫會嘗試提供一般片語或模式清單的所有格式，例如日期、電話號碼、郵遞區號和許多其他格式。</span><span class="sxs-lookup"><span data-stu-id="06669-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="06669-156">在我們的*服務開始日期*範例中，使用 [說明] 程式庫中的*日期*預先建立的說明會更有效率：</span><span class="sxs-lookup"><span data-stu-id="06669-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="06669-157">在 [**說明] 區段**中，選取 [**新增**]，然後選取 [**從解釋程式庫**]。</span><span class="sxs-lookup"><span data-stu-id="06669-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="06669-158">從 [說明] 程式庫中，選取 [**日期**]。</span><span class="sxs-lookup"><span data-stu-id="06669-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="06669-159">您可以查看會辨識的所有日期變化。</span><span class="sxs-lookup"><span data-stu-id="06669-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="06669-160">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06669-160">Select **Add**.</span></span></br>

    ![說明程式庫](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="06669-162">在 [**建立說明**] 頁面上，[說明] 程式庫中的*日期*資訊會自動填滿欄位。</span><span class="sxs-lookup"><span data-stu-id="06669-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="06669-163">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="06669-163">Select **Save**.</span></span></br>

    ![說明程式庫](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="06669-165">訓練模型</span><span class="sxs-lookup"><span data-stu-id="06669-165">Train the model</span></span> 

<span data-ttu-id="06669-166">儲存您的說明會開始訓練。</span><span class="sxs-lookup"><span data-stu-id="06669-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="06669-167">如果您的模型有足夠的資訊可從標示的範例檔案中解壓縮資料，您將會看到每個標示為 [**相符**] 的檔案。</span><span class="sxs-lookup"><span data-stu-id="06669-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![說明程式庫](../media/content-understanding/match2.png) 

<span data-ttu-id="06669-169">如果說明沒有足夠的資訊可找出您想要解壓縮的資料，則每個檔案都會以**不相符**的方式標示。</span><span class="sxs-lookup"><span data-stu-id="06669-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="06669-170">您可以按一下不匹配的檔案，以查看有關為何不符的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="06669-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="06669-171">新增其他說明</span><span class="sxs-lookup"><span data-stu-id="06669-171">Add another explanation</span></span>

<span data-ttu-id="06669-172">通常不相符是指我們所提供的說明並未提供足夠的資訊來解壓縮服務的開始日期值，以符合我們標示的檔案。</span><span class="sxs-lookup"><span data-stu-id="06669-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="06669-173">您可能需要編輯它，或新增另一個說明。</span><span class="sxs-lookup"><span data-stu-id="06669-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="06669-174">在我們的範例中，我們會注意到文字字串的*開始服務日期*永遠在實際值之前。</span><span class="sxs-lookup"><span data-stu-id="06669-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="06669-175">為了協助識別服務的開始日期，我們可以建立片語說明。</span><span class="sxs-lookup"><span data-stu-id="06669-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="06669-176">在 [說明] 區段中，選取 [**新增**]，然後輸入名稱 (例如，*首碼字串*) 。</span><span class="sxs-lookup"><span data-stu-id="06669-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="06669-177">在 [類型] 中，選取 [**片語] 清單**。</span><span class="sxs-lookup"><span data-stu-id="06669-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="06669-178">使用*服務的開始日期*做為值。</span><span class="sxs-lookup"><span data-stu-id="06669-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="06669-179">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="06669-179">Select **Save**.</span></span>

    ![說明程式庫](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="06669-181">訓練模型</span><span class="sxs-lookup"><span data-stu-id="06669-181">Train the model</span></span>

<span data-ttu-id="06669-182">儲存您的說明將會再次開始訓練。這一次，我們在範例中使用這兩個說明。</span><span class="sxs-lookup"><span data-stu-id="06669-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="06669-183">如果您的模型有足夠的資訊可從標示的範例檔案中解壓縮資料，您將會看到每個標示為 [**相符**] 的檔案。</span><span class="sxs-lookup"><span data-stu-id="06669-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="06669-184">如果您再次收到標籤上的**不相符**專案，您可能需要建立另一個說明，以提供模型以進一步識別檔案類型的資訊，或查看是否有現有的變更。</span><span class="sxs-lookup"><span data-stu-id="06669-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="06669-185">測試您的模型</span><span class="sxs-lookup"><span data-stu-id="06669-185">Test your model</span></span>

<span data-ttu-id="06669-186">如果您在已標示的範例檔案上收到相符的檔，您現在可以在其餘未標記的範例檔案上測試您的模型。</span><span class="sxs-lookup"><span data-stu-id="06669-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="06669-187">在模型首頁上，按一下 [**測試**] 索引標籤。 這會在未標記的範例檔案上執行該模型。</span><span class="sxs-lookup"><span data-stu-id="06669-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="06669-188">在 [**測試**檔案] 清單中，會顯示您的範例檔案，並顯示模型是否可以從這些檔案中解壓縮您所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="06669-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="06669-189">您可以使用這項資訊來協助您判斷您的分類器在識別檔時的效能。</span><span class="sxs-lookup"><span data-stu-id="06669-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![測試您的檔案](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="06669-191">另請參閱</span><span class="sxs-lookup"><span data-stu-id="06669-191">See Also</span></span>
  




