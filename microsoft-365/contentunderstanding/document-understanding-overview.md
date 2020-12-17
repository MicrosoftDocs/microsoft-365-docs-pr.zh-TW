---
title: 文件瞭解概觀
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: 取得 Microsoft SharePoint Syntex 中文件瞭解的概覽。
ms.openlocfilehash: 5dd44a119dff6f5d194861c381fa28f76a6f0da7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701104"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="ef11a-103">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="ef11a-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="ef11a-104">文件瞭解使用人工智慧 (AI) 模型來自動分類檔案及擷取資訊。</span><span class="sxs-lookup"><span data-stu-id="ef11a-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="ef11a-105">它最適用於非結構化文件，如信件或合约。</span><span class="sxs-lookup"><span data-stu-id="ef11a-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="ef11a-106">這些文件必須具有可根據片語或模式識別的文字。</span><span class="sxs-lookup"><span data-stu-id="ef11a-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="ef11a-107">所識別的文字指定了檔案的類型（它的分類）和您想要擷取的內容（它的擷取器）。</span><span class="sxs-lookup"><span data-stu-id="ef11a-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="ef11a-108">如需有關文件瞭解案例範例的詳細資訊，請參閱 [SharePoint Syntex 採用：入門指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example)。</span><span class="sxs-lookup"><span data-stu-id="ef11a-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="ef11a-109">文件瞭解模型是在一種稱為 *内容中心* 的 SharePoint 網站中建立和管理的。</span><span class="sxs-lookup"><span data-stu-id="ef11a-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="ef11a-110">當套用至 SharePoint 文件庫時，模型與一個具有存儲所擷取資訊的欄的內容類型相關聯。</span><span class="sxs-lookup"><span data-stu-id="ef11a-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="ef11a-111">您建立的內容類型儲存在 SharePoint 內容類型庫中。</span><span class="sxs-lookup"><span data-stu-id="ef11a-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="ef11a-112">您也可以選擇使用現有內容類型來使用其架構。</span><span class="sxs-lookup"><span data-stu-id="ef11a-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="ef11a-113">無法更新唯讀或封存內容類型，因此無法在模型中使用。</span><span class="sxs-lookup"><span data-stu-id="ef11a-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="ef11a-114">將 *分類器* 和 *擷取器* 新增至文件瞭解模型中，以執行以下動作：</span><span class="sxs-lookup"><span data-stu-id="ef11a-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="ef11a-115">分類器用來識別和分類上傳至文件庫的文件。</span><span class="sxs-lookup"><span data-stu-id="ef11a-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="ef11a-116">例如，可以「訓練」分類器來識別上傳到文件庫的所有 *合同續約* 文件。</span><span class="sxs-lookup"><span data-stu-id="ef11a-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="ef11a-117">合同續約內容類型由您在建立分類器時定義。</span><span class="sxs-lookup"><span data-stu-id="ef11a-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="ef11a-118">擷取器從這些文件中選取資訊。</span><span class="sxs-lookup"><span data-stu-id="ef11a-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="ef11a-119">例如，對於文件庫中識別的所有合同續約文件，檢視中顯示的欄也顯示每個合同續約文件的 *服務開始日期* 和 *客戶*。</span><span class="sxs-lookup"><span data-stu-id="ef11a-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="ef11a-120">您可以在模型中使用範例檔案來訓練和測試分類器和擷取器。</span><span class="sxs-lookup"><span data-stu-id="ef11a-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="ef11a-121">範例檔案向您的模型範例提供在嘗試從檔案中識別和擷取資料時要查找的內容。</span><span class="sxs-lookup"><span data-stu-id="ef11a-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="ef11a-122">例如，您會以貴公司使用的合同續約文件範例來訓練您的合同續約分類器和擷取器。</span><span class="sxs-lookup"><span data-stu-id="ef11a-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="ef11a-123">您也可以使用範例檔案來測試模型的有效性。</span><span class="sxs-lookup"><span data-stu-id="ef11a-123">You can also use example files to test the effectiveness of your model.</span></span>

> [!NOTE]
> <span data-ttu-id="ef11a-124">如果您使用光學字元辨識 (OCR) 技術來掃描文件，則Syntex 的模型訓練會有15頁之限制。</span><span class="sxs-lookup"><span data-stu-id="ef11a-124">If you use optical character recognition (OCR) technology to scan documents, Syntex has a 15-page limit for model training.</span></span>

<span data-ttu-id="ef11a-125">發佈模型之後，請使用內容中心將它套用到您有權存取的任何 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="ef11a-125">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ef11a-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ef11a-126">See Also</span></span>
[<span data-ttu-id="ef11a-127">建立分類器</span><span class="sxs-lookup"><span data-stu-id="ef11a-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="ef11a-128">建立擷取器</span><span class="sxs-lookup"><span data-stu-id="ef11a-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="ef11a-129">建立內容中心</span><span class="sxs-lookup"><span data-stu-id="ef11a-129">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="ef11a-130">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="ef11a-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="ef11a-131">套用模型</span><span class="sxs-lookup"><span data-stu-id="ef11a-131">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="ef11a-132">文件瞭解和表單處理模型之間的差異</span><span class="sxs-lookup"><span data-stu-id="ef11a-132">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="ef11a-133">表單處理概觀</span><span class="sxs-lookup"><span data-stu-id="ef11a-133">Form processing overview</span></span>](form-processing-overview.md)
