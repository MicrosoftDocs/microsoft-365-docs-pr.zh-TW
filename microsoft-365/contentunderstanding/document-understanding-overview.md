---
title: '檔理解一覽 (預覽) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 深入瞭解 Project Cortex 中的檔知識。
ms.openlocfilehash: c1e4092164ee96d4f244f10be9ebab62a2c8da5b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950045"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="4c9f7-103">檔理解一覽 (預覽) </span><span class="sxs-lookup"><span data-stu-id="4c9f7-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="4c9f7-104">專案 Cortex 目前在預覽中。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="4c9f7-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="4c9f7-106">檔瞭解使用 AI 模型自動進行檔案分類和資訊提取。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="4c9f7-107">它最適合使用非結構化檔，如信件或合約。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="4c9f7-108">檔應有文字可根據片語或模式識別。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="4c9f7-109">識別的文字可以指定其 (分類的檔案類型) 以及您想提取 (其擷取器) 的內容。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="4c9f7-110">檔理解模型是在一種稱為內容中心的 SharePoint 網站中建立及管理。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="4c9f7-111">套用至 SharePoint 文件庫時，模型會與內容類型相關聯，該內容類型具有用來儲存提取資訊的欄。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="4c9f7-112">您建立的內容類型會儲存在 SharePoint 內容類型庫中。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="4c9f7-113">您也可以選擇使用現有的內容類型，以便使用其架構。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="4c9f7-114">您可以將 *分類* 器和 *擷取器* 新增至檔理解模型，以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="4c9f7-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="4c9f7-115">分類器是用來識別和分類上傳至文件庫的檔。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="4c9f7-116">例如，分類器可以「訓練」，識別所有上傳至文件庫的 *合約更新* 檔。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="4c9f7-117">當您建立分類器時，即會定義「合約更新」內容類型。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="4c9f7-118">從這些檔中擷取器提取資訊。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="4c9f7-119">例如，針對文件庫中識別的所有合約更新檔，欄會顯示在您的視圖中，也會顯示每個合約更新檔的 *服務開始日期* 和  *用戶端* 。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="4c9f7-120">您可以使用範例檔案訓練及測試模型中的分類器和擷取器。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="4c9f7-121">範例檔案會提供您的模型範例，說明在嘗試識別及解壓縮資料時所要尋找的專案。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="4c9f7-122">例如，您可以使用貴公司所用的合約更新檔範例，訓練您的合約更新類元和擷取器。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="4c9f7-123">您也可以使用範例檔來測試模型的效能。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="4c9f7-124">在發佈模型之後，請使用內容中心將其套用至您具有存取權的任何 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="4c9f7-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="4c9f7-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4c9f7-125">See Also</span></span>
[<span data-ttu-id="4c9f7-126">建立分類器</span><span class="sxs-lookup"><span data-stu-id="4c9f7-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="4c9f7-127">建立提取程式</span><span class="sxs-lookup"><span data-stu-id="4c9f7-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="4c9f7-128">[建立內容中心](create-a-content-center.md) 
[建立表單處理模型](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="4c9f7-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="4c9f7-129">[套用模型](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="4c9f7-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="4c9f7-130">檔瞭解和表單處理模型之間的差異</span><span class="sxs-lookup"><span data-stu-id="4c9f7-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="4c9f7-131">表單處理概覽</span><span class="sxs-lookup"><span data-stu-id="4c9f7-131">Form processing overview</span></span>](form-processing-overview.md)




