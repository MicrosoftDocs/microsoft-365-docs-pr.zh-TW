---
title: 文件瞭解概觀
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 取得 Microsoft SharePoint Syntex 中文件瞭解的概覽。
ms.openlocfilehash: 1265dfa06db323e23d63a044a1a95a6b67c525cf
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333555"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="8a410-103">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="8a410-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="8a410-104">文件瞭解使用人工智慧 (AI) 模型來自動分類檔案及擷取資訊。</span><span class="sxs-lookup"><span data-stu-id="8a410-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="8a410-105">它最適用於非結構化文件，如信件或合约。</span><span class="sxs-lookup"><span data-stu-id="8a410-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="8a410-106">這些文件必須具有可根據片語或模式識別的文字。</span><span class="sxs-lookup"><span data-stu-id="8a410-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="8a410-107">所識別的文字指定了檔案的類型（它的分類）和您想要擷取的內容（它的擷取器）。</span><span class="sxs-lookup"><span data-stu-id="8a410-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="8a410-108">如需有關文件瞭解案例範例的詳細資訊，請參閱 [SharePoint Syntex 採用：入門指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example)。</span><span class="sxs-lookup"><span data-stu-id="8a410-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="8a410-109">文件瞭解模型是在一種稱為*内容中心*的 SharePoint 網站中建立和管理的。</span><span class="sxs-lookup"><span data-stu-id="8a410-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="8a410-110">當套用至 SharePoint 文件庫時，模型與一個具有存儲所擷取資訊的欄的內容類型相關聯。</span><span class="sxs-lookup"><span data-stu-id="8a410-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="8a410-111">您建立的內容類型儲存在 SharePoint 內容類型庫中。</span><span class="sxs-lookup"><span data-stu-id="8a410-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="8a410-112">您也可以選擇使用現有內容類型來使用其架構。</span><span class="sxs-lookup"><span data-stu-id="8a410-112">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="8a410-113">將*分類器*和*擷取器*新增至文件瞭解模型中，以執行以下動作：</span><span class="sxs-lookup"><span data-stu-id="8a410-113">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="8a410-114">分類器用來識別和分類上傳至文件庫的文件。</span><span class="sxs-lookup"><span data-stu-id="8a410-114">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="8a410-115">例如，可以「訓練」分類器來識別上傳到文件庫的所有*合同續約*文件。</span><span class="sxs-lookup"><span data-stu-id="8a410-115">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="8a410-116">合同續約內容類型由您在建立分類器時定義。</span><span class="sxs-lookup"><span data-stu-id="8a410-116">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="8a410-117">擷取器從這些文件中選取資訊。</span><span class="sxs-lookup"><span data-stu-id="8a410-117">Extractors pull information from these documents.</span></span> <span data-ttu-id="8a410-118">例如，對於文件庫中識別的所有合同續約文件，檢視中顯示的欄也顯示每個合同續約文件的*服務開始日期*和*客戶*。</span><span class="sxs-lookup"><span data-stu-id="8a410-118">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="8a410-119">您可以在模型中使用範例檔案來訓練和測試分類器和擷取器。</span><span class="sxs-lookup"><span data-stu-id="8a410-119">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="8a410-120">範例檔案向您的模型範例提供在嘗試從檔案中識別和擷取資料時要查找的內容。</span><span class="sxs-lookup"><span data-stu-id="8a410-120">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="8a410-121">例如，您會以貴公司使用的合同續約文件範例來訓練您的合同續約分類器和擷取器。</span><span class="sxs-lookup"><span data-stu-id="8a410-121">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="8a410-122">您也可以使用範例檔案來測試模型的有效性。</span><span class="sxs-lookup"><span data-stu-id="8a410-122">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="8a410-123">發佈模型之後，請使用內容中心將它套用到您有權存取的任何 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="8a410-123">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  



## <a name="see-also"></a><span data-ttu-id="8a410-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8a410-124">See Also</span></span>
[<span data-ttu-id="8a410-125">建立分類器</span><span class="sxs-lookup"><span data-stu-id="8a410-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="8a410-126">建立擷取器</span><span class="sxs-lookup"><span data-stu-id="8a410-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="8a410-127">建立內容中心</span><span class="sxs-lookup"><span data-stu-id="8a410-127">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="8a410-128">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="8a410-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="8a410-129">套用模型</span><span class="sxs-lookup"><span data-stu-id="8a410-129">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="8a410-130">文件瞭解和表單處理模型之間的差異</span><span class="sxs-lookup"><span data-stu-id="8a410-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="8a410-131">表單處理概觀</span><span class="sxs-lookup"><span data-stu-id="8a410-131">Form processing overview</span></span>](form-processing-overview.md)
