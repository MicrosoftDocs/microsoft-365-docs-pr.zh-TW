---
title: 檔理解概述
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 深入瞭解 Microsoft SharePoint Syntex 中的檔瞭解。
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294757"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="a75b6-103">檔理解概述</span><span class="sxs-lookup"><span data-stu-id="a75b6-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="a75b6-104">檔瞭解使用智慧 (AI) 模型，以自動化檔案的分類和資訊提取。</span><span class="sxs-lookup"><span data-stu-id="a75b6-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="a75b6-105">它最適合使用非結構化檔，例如信件或合約。</span><span class="sxs-lookup"><span data-stu-id="a75b6-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="a75b6-106">這些檔必須具有可根據片語或模式識別的文字。</span><span class="sxs-lookup"><span data-stu-id="a75b6-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="a75b6-107">識別的文字會同時指定它所 (分類的檔案類型) 以及您想要 (其擷取器) 提取的內容。</span><span class="sxs-lookup"><span data-stu-id="a75b6-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="a75b6-108">檔理解模型是在一種稱為 *內容中心*的 SharePoint 網站中建立及管理。</span><span class="sxs-lookup"><span data-stu-id="a75b6-108">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="a75b6-109">套用至 SharePoint 文件庫時，模型與內容類型相關聯時，會有欄，用來儲存所提取的資訊。</span><span class="sxs-lookup"><span data-stu-id="a75b6-109">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="a75b6-110">您建立的內容類型會儲存在 SharePoint 內容類型庫中。</span><span class="sxs-lookup"><span data-stu-id="a75b6-110">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="a75b6-111">您也可以選擇使用現有的內容類型以使用其架構。</span><span class="sxs-lookup"><span data-stu-id="a75b6-111">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="a75b6-112">將 *分類* 程式和 *擷取器* 新增至檔理解模型，以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="a75b6-112">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="a75b6-113">分類器是用來識別和分類上傳至文件庫的檔。</span><span class="sxs-lookup"><span data-stu-id="a75b6-113">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="a75b6-114">例如，分類器可以「訓練」，識別所有上傳至文件庫的 *合約更新* 檔。</span><span class="sxs-lookup"><span data-stu-id="a75b6-114">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="a75b6-115">當您建立分類器時，即會定義「合約更新」內容類型。</span><span class="sxs-lookup"><span data-stu-id="a75b6-115">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="a75b6-116">從這些檔中擷取器提取資訊。</span><span class="sxs-lookup"><span data-stu-id="a75b6-116">Extractors pull information from these documents.</span></span> <span data-ttu-id="a75b6-117">例如，針對文件庫中識別的所有合約更新檔，欄會顯示在您的視圖中，也會顯示每個合約更新檔的 *服務開始日期* 和  *用戶端* 。</span><span class="sxs-lookup"><span data-stu-id="a75b6-117">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="a75b6-118">您可以使用範例檔案訓練及測試您的模型中的分類器和擷取器。</span><span class="sxs-lookup"><span data-stu-id="a75b6-118">You can use sample files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="a75b6-119">範例檔案會提供您的模型範例，說明當您嘗試識別及解壓縮檔中的資料時，應尋找哪些專案。</span><span class="sxs-lookup"><span data-stu-id="a75b6-119">Sample files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="a75b6-120">例如，您可以使用貴公司所用的合約更新檔範例，訓練您的合約更新分類程式和擷取器。</span><span class="sxs-lookup"><span data-stu-id="a75b6-120">For example, you would train your contract renewal classifiers and extractors with samples of contract renewal documents your company works with.</span></span> <span data-ttu-id="a75b6-121">您也可以使用範例檔來測試模型的效能。</span><span class="sxs-lookup"><span data-stu-id="a75b6-121">You can also use sample files to test the effectiveness of your model.</span></span>

<span data-ttu-id="a75b6-122">在發佈模型之後，請使用內容中心將其套用至您具有存取權的任何 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="a75b6-122">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="a75b6-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a75b6-123">See Also</span></span>
[<span data-ttu-id="a75b6-124">建立分類器</span><span class="sxs-lookup"><span data-stu-id="a75b6-124">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="a75b6-125">建立提取程式</span><span class="sxs-lookup"><span data-stu-id="a75b6-125">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="a75b6-126">[建立內容中心](create-a-content-center.md) 
[建立表單處理模型](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="a75b6-126">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="a75b6-127">[套用模型](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="a75b6-127">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="a75b6-128">檔瞭解和表單處理模型之間的差異</span><span class="sxs-lookup"><span data-stu-id="a75b6-128">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="a75b6-129">表單處理概覽</span><span class="sxs-lookup"><span data-stu-id="a75b6-129">Form processing overview</span></span>](form-processing-overview.md)
