---
title: 文件瞭解概觀
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 取得 Microsoft SharePoint Syntex 中文件瞭解的概覽。
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683820"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="44419-103">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="44419-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="44419-104">文件瞭解使用人工智慧 (AI) 模型來自動分類檔案及擷取資訊。</span><span class="sxs-lookup"><span data-stu-id="44419-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="44419-105">它最適用於非結構化文件，如信件或合约。</span><span class="sxs-lookup"><span data-stu-id="44419-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="44419-106">這些文件必須具有可根據片語或模式識別的文字。</span><span class="sxs-lookup"><span data-stu-id="44419-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="44419-107">所識別的文字指定了檔案的類型（它的分類）和您想要擷取的內容（它的擷取器）。</span><span class="sxs-lookup"><span data-stu-id="44419-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="44419-108">如需有關文件瞭解案例範例的詳細資訊，請參閱 [SharePoint Syntex 採用：入門指南](./adoption-getstarted.md)。</span><span class="sxs-lookup"><span data-stu-id="44419-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="44419-109">文件瞭解模型是在一種稱為 *内容中心* 的 SharePoint 網站中建立和管理的。</span><span class="sxs-lookup"><span data-stu-id="44419-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="44419-110">當套用至 SharePoint 文件庫時，模型與一個具有存儲所擷取資訊的欄的內容類型相關聯。</span><span class="sxs-lookup"><span data-stu-id="44419-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="44419-111">您建立的內容類型儲存在 SharePoint 內容類型庫中。</span><span class="sxs-lookup"><span data-stu-id="44419-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="44419-112">您也可以選擇使用現有內容類型來使用其架構。</span><span class="sxs-lookup"><span data-stu-id="44419-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="44419-113">無法更新唯讀或封存內容類型，因此無法在模型中使用。</span><span class="sxs-lookup"><span data-stu-id="44419-113">Read-only or sealed content types cannot be updated, so they can't be used in a model.</span></span>

<span data-ttu-id="44419-114">將 *分類器* 和 *擷取器* 新增至文件瞭解模型中，以執行以下動作：</span><span class="sxs-lookup"><span data-stu-id="44419-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="44419-115">分類器用來識別和分類上傳至文件庫的文件。</span><span class="sxs-lookup"><span data-stu-id="44419-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="44419-116">例如，可以「訓練」分類器來識別上傳到文件庫的所有 *合同續約* 文件。</span><span class="sxs-lookup"><span data-stu-id="44419-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="44419-117">合同續約內容類型由您在建立分類器時定義。</span><span class="sxs-lookup"><span data-stu-id="44419-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="44419-118">擷取器從這些文件中選取資訊。</span><span class="sxs-lookup"><span data-stu-id="44419-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="44419-119">例如，對於文件庫中識別的所有合同續約文件，檢視中顯示的欄也顯示每個合同續約文件的 *服務開始日期* 和 *客戶*。</span><span class="sxs-lookup"><span data-stu-id="44419-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="44419-120">您可以在模型中使用範例檔案來訓練和測試分類器和擷取器。</span><span class="sxs-lookup"><span data-stu-id="44419-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="44419-121">範例檔案向您的模型範例提供在嘗試從檔案中識別和擷取資料時要查找的內容。</span><span class="sxs-lookup"><span data-stu-id="44419-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="44419-122">例如，您會以貴公司使用的合同續約文件範例來訓練您的合同續約分類器和擷取器。</span><span class="sxs-lookup"><span data-stu-id="44419-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="44419-123">您也可以使用範例檔案來測試模型的有效性。</span><span class="sxs-lookup"><span data-stu-id="44419-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="44419-124">發佈模型之後，請使用內容中心將它套用到您有權存取的任何 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="44419-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="file-limitations"></a><span data-ttu-id="44419-125">檔案限制</span><span class="sxs-lookup"><span data-stu-id="44419-125">File limitations</span></span>

<span data-ttu-id="44419-126">文件瞭解模型：使用光學字元辨識 (OCR) 技術，在您使用範例檔案訓練模型時以及當您針對文件庫中的檔案執行模型時，掃描 PDF、影像和 TIFF 檔案。</span><span class="sxs-lookup"><span data-stu-id="44419-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="44419-127">請注意有關於 Microsoft Office 文字型檔案與 OCR 掃描檔案 (PDF、影像或 TIFF) 的下列差異：</span><span class="sxs-lookup"><span data-stu-id="44419-127">Note the following differences with regard to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="44419-128">Office 檔案：在 64,000 個字元處截斷 (在訓練中以及針對文件庫中的檔案執行時)。</span><span class="sxs-lookup"><span data-stu-id="44419-128">Office files: Truncated at 64,000 characters (in training and when run against files in a document library).</span></span>

- <span data-ttu-id="44419-129">OCR 掃描檔案：頁面上限為 20 頁。</span><span class="sxs-lookup"><span data-stu-id="44419-129">OCR-scanned files: There's a 20-page limit.</span></span>  

### <a name="requirements"></a><span data-ttu-id="44419-130">需求</span><span class="sxs-lookup"><span data-stu-id="44419-130">Requirements</span></span>

<span data-ttu-id="44419-131">OCR 處理最適合處理符合下列需求的文件：</span><span class="sxs-lookup"><span data-stu-id="44419-131">OCR processing works best on documents that meet the following requirements:</span></span>

- <span data-ttu-id="44419-132">JPG、PNG 或 PDF 格式 (文字或掃描文件)。</span><span class="sxs-lookup"><span data-stu-id="44419-132">JPG, PNG, or PDF format (text or scanned).</span></span> <span data-ttu-id="44419-133">文字內嵌 PDF 效果更好，因為字元解壓縮和位置不會有任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="44419-133">Text-embedded PDFs are better, because there won't be any errors in character extraction and location.</span></span>

- <span data-ttu-id="44419-134">如果您的 PDF 使用密碼鎖定，您必須先移除鎖定再提交。</span><span class="sxs-lookup"><span data-stu-id="44419-134">If your PDFs are password-locked, you must remove the lock before submitting them.</span></span>

- <span data-ttu-id="44419-135">每個集合中，用於訓練的文件總檔案大小不得超過 50 MB，PDF 文件不應超過 500 頁。</span><span class="sxs-lookup"><span data-stu-id="44419-135">The combined file size of the documents used for training per collection must not exceed 50 MB, and PDF documents shouldn't have more than 500 pages.</span></span>

- <span data-ttu-id="44419-136">若是影像，尺寸必須介於 50 × 50 到 10,000 × 10,000 像素之間。</span><span class="sxs-lookup"><span data-stu-id="44419-136">For images, dimensions must be between 50 × 50 and 10,000 × 10,000 pixels.</span></span>
   > [!NOTE]
   > <span data-ttu-id="44419-137">在 OCR 處理中，非常寬或具有奇數尺寸 (例如樓層規劃) 的影像可能會被截斷，並失去正確性。</span><span class="sxs-lookup"><span data-stu-id="44419-137">Images that are very wide or have odd dimensions (for example, floor plans) might get truncated in the OCR process and lose accuracy.</span></span>
 
- <span data-ttu-id="44419-138">若是 PDF 檔案，尺寸最多必須為 17 x 17 吋，與 Legal 或 A3 紙張大小對應且較小。</span><span class="sxs-lookup"><span data-stu-id="44419-138">For PDF files, dimensions must be at most 17 x 17 inches, corresponding to Legal or A3 paper sizes and smaller.</span></span>

- <span data-ttu-id="44419-139">如果從紙本文件掃描，應為高品質影像的掃描。</span><span class="sxs-lookup"><span data-stu-id="44419-139">If scanned from paper documents, scans should be high-quality images.</span></span>

- <span data-ttu-id="44419-140">必須使用拉丁字母 (英文字元)。</span><span class="sxs-lookup"><span data-stu-id="44419-140">Must use the Latin alphabet (English characters).</span></span>

> [!NOTE]
> <span data-ttu-id="44419-141">AI Builder 目前不支援下列表單處理輸入資料類型：</span><span class="sxs-lookup"><span data-stu-id="44419-141">AI Builder doesn't currently support the following types of form processing input data:</span></span><br><span data-ttu-id="44419-142">- 核取方塊或選項按鈕</span><span class="sxs-lookup"><span data-stu-id="44419-142">- Check boxes or radio buttons</span></span><br><span data-ttu-id="44419-143">- 簽章</span><span class="sxs-lookup"><span data-stu-id="44419-143">- Signatures</span></span><br><span data-ttu-id="44419-144">- 可填寫的 PDF</span><span class="sxs-lookup"><span data-stu-id="44419-144">- Fillable PDFs</span></span>

### <a name="supported-file-types"></a><span data-ttu-id="44419-145">支援的檔案類型</span><span class="sxs-lookup"><span data-stu-id="44419-145">Supported file types</span></span>

<span data-ttu-id="44419-146">文件瞭解模型支援下列檔案類型：</span><span class="sxs-lookup"><span data-stu-id="44419-146">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="44419-147">doc</span><span class="sxs-lookup"><span data-stu-id="44419-147">doc</span></span>
- <span data-ttu-id="44419-148">docx</span><span class="sxs-lookup"><span data-stu-id="44419-148">docx</span></span>
- <span data-ttu-id="44419-149">eml</span><span class="sxs-lookup"><span data-stu-id="44419-149">eml</span></span>
- <span data-ttu-id="44419-150">heic</span><span class="sxs-lookup"><span data-stu-id="44419-150">heic</span></span>
- <span data-ttu-id="44419-151">heif</span><span class="sxs-lookup"><span data-stu-id="44419-151">heif</span></span>
- <span data-ttu-id="44419-152">htm</span><span class="sxs-lookup"><span data-stu-id="44419-152">htm</span></span>
- <span data-ttu-id="44419-153">html</span><span class="sxs-lookup"><span data-stu-id="44419-153">html</span></span>
- <span data-ttu-id="44419-154">jpeg</span><span class="sxs-lookup"><span data-stu-id="44419-154">jpeg</span></span>
- <span data-ttu-id="44419-155">jpg</span><span class="sxs-lookup"><span data-stu-id="44419-155">jpg</span></span>
- <span data-ttu-id="44419-156">markdown</span><span class="sxs-lookup"><span data-stu-id="44419-156">markdown</span></span>
- <span data-ttu-id="44419-157">md</span><span class="sxs-lookup"><span data-stu-id="44419-157">md</span></span>
- <span data-ttu-id="44419-158">msg</span><span class="sxs-lookup"><span data-stu-id="44419-158">msg</span></span>
- <span data-ttu-id="44419-159">pdf</span><span class="sxs-lookup"><span data-stu-id="44419-159">pdf</span></span>
- <span data-ttu-id="44419-160">png</span><span class="sxs-lookup"><span data-stu-id="44419-160">png</span></span>
- <span data-ttu-id="44419-161">ppt</span><span class="sxs-lookup"><span data-stu-id="44419-161">ppt</span></span>
- <span data-ttu-id="44419-162">pptx</span><span class="sxs-lookup"><span data-stu-id="44419-162">pptx</span></span>
- <span data-ttu-id="44419-163">rtf</span><span class="sxs-lookup"><span data-stu-id="44419-163">rtf</span></span>
- <span data-ttu-id="44419-164">tif</span><span class="sxs-lookup"><span data-stu-id="44419-164">tif</span></span>
- <span data-ttu-id="44419-165">tiff</span><span class="sxs-lookup"><span data-stu-id="44419-165">tiff</span></span>
- <span data-ttu-id="44419-166">txt</span><span class="sxs-lookup"><span data-stu-id="44419-166">txt</span></span>
- <span data-ttu-id="44419-167">xls</span><span class="sxs-lookup"><span data-stu-id="44419-167">xls</span></span>
- <span data-ttu-id="44419-168">xlsx</span><span class="sxs-lookup"><span data-stu-id="44419-168">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="44419-169">另請參閱</span><span class="sxs-lookup"><span data-stu-id="44419-169">See Also</span></span>
[<span data-ttu-id="44419-170">建立分類器</span><span class="sxs-lookup"><span data-stu-id="44419-170">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="44419-171">建立擷取器</span><span class="sxs-lookup"><span data-stu-id="44419-171">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="44419-172">建立內容中心</span><span class="sxs-lookup"><span data-stu-id="44419-172">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="44419-173">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="44419-173">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="44419-174">套用模型</span><span class="sxs-lookup"><span data-stu-id="44419-174">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="44419-175">文件瞭解和表單處理模型之間的差異</span><span class="sxs-lookup"><span data-stu-id="44419-175">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="44419-176">表單處理概觀</span><span class="sxs-lookup"><span data-stu-id="44419-176">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="44419-177">SharePoint Syntex 協助工具模式</span><span class="sxs-lookup"><span data-stu-id="44419-177">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)