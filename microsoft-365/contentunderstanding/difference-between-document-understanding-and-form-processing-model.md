---
title: '檔瞭解和表單處理模型之間的差異 (預覽) '
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
description: 說明文件瞭解和表單處理模型之間的主要差異。
ms.openlocfilehash: 7c480b91c1ddd75016b4bd35faa3d5692cacd103
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612735"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a><span data-ttu-id="28aa3-103">檔瞭解和表單處理模型之間的差異 (預覽) </span><span class="sxs-lookup"><span data-stu-id="28aa3-103">Difference between document understanding and form processing models (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="28aa3-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="28aa3-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="28aa3-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="28aa3-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="28aa3-106">專案 Cortex 中的內容瞭解可讓您識別和分類上載至 SharePoint 文件庫的檔，以及提取每個檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="28aa3-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="28aa3-107">例如，當檔案上傳至 SharePoint 文件庫時，識別為*購買訂單*的所有檔案都會以這種方式分類，並顯示在顯示它們的自訂文件庫視圖中。</span><span class="sxs-lookup"><span data-stu-id="28aa3-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such and displayed in a custom document library view in which they are displayed.</span></span> <span data-ttu-id="28aa3-108">此外，您可以從每個檔案中拉入特定資訊 (例如， *PO 號碼*和*合計*) ，並將其顯示在文件庫視圖中的欄中。</span><span class="sxs-lookup"><span data-stu-id="28aa3-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it in a column in your document library view.</span></span> 


<span data-ttu-id="28aa3-109">內容瞭解可讓您建立*模型*，以識別及解壓縮您所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="28aa3-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span>  <span data-ttu-id="28aa3-110">可使用的模型類型有兩種：</span><span class="sxs-lookup"><span data-stu-id="28aa3-110">There are two types of models that can be used:</span></span>

- [<span data-ttu-id="28aa3-111">檔理解模型</span><span class="sxs-lookup"><span data-stu-id="28aa3-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="28aa3-112">表單處理模型</span><span class="sxs-lookup"><span data-stu-id="28aa3-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="28aa3-113">雖然這兩種模型一般都使用相同的目的，但有一些重要差異會影響您可以選擇使用的專案。</span><span class="sxs-lookup"><span data-stu-id="28aa3-113">While both models are used for generally the same purpose, there are key differences that will affect which ones you may choose to use.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="28aa3-114">結構化與非結構化及半結構化內容</span><span class="sxs-lookup"><span data-stu-id="28aa3-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="28aa3-115">使用檔理解模型來識別及提取非結構化檔中的資料，例如信件或合約，而您想要提取的文字實體會位於檔的句子或特定區域中。</span><span class="sxs-lookup"><span data-stu-id="28aa3-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="28aa3-116">例如，非結構化檔可以是以不同方式撰寫的合約更新信件。</span><span class="sxs-lookup"><span data-stu-id="28aa3-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="28aa3-117">不過，各項合約更新檔的本文中的資訊都是一致的，例如文字字串「服務的開始日期」，然後是實際的日期。</span><span class="sxs-lookup"><span data-stu-id="28aa3-117">However, there is information that is consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="28aa3-118">使用表單處理模型來識別檔案，並從結構化或半結構化的檔（例如表單或發票）中提取資料，您可以在其中包含明確的索引鍵-值對 (例如， *Date： 10/1/2020*) \* 或 table 資料。</span><span class="sxs-lookup"><span data-stu-id="28aa3-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices, where you have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="28aa3-119">舉例來說，表單處理的一個不錯的候選人是公司的訂單要求表單，用戶端需要在該表單中提供其資訊，以供位於檔版面配置相同區域中的特定欄位（例如*名稱*、*電話號碼*、*總成本*等）。 納稅表單是結構化檔的好例子。</span><span class="sxs-lookup"><span data-stu-id="28aa3-119">As an example, a good candidate for form processing would be a company's order request form in which clients need to provide their information for specific fields which are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="28aa3-120">建立位置</span><span class="sxs-lookup"><span data-stu-id="28aa3-120">Where they are created</span></span>

<span data-ttu-id="28aa3-121">檔理解模型是在 SharePoint 內容中心網站中建立及管理的。</span><span class="sxs-lookup"><span data-stu-id="28aa3-121">Document understanding models are created and managed in a SharePoint content center site.</span></span> <span data-ttu-id="28aa3-122">您必須具有內容中心網站的存取權，才可建立檔理解模型，或將其中一項套用至 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="28aa3-122">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="28aa3-123">當您建立檔理解模型時，會建立新的[SharePoint 內容類型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)儲存至 SharePoint 內容類型庫。</span><span class="sxs-lookup"><span data-stu-id="28aa3-123">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="28aa3-124">您也可以視需要使用現有的內容類型來定義模型。</span><span class="sxs-lookup"><span data-stu-id="28aa3-124">You can optionally use existing content types to define your model if needed.</span></span>

<span data-ttu-id="28aa3-125">表單處理模型是在 PowerApps [AI](https://docs.microsoft.com/ai-builder/overview)產生器中建立，但是會直接從 SharePoint 文件庫開始建立。</span><span class="sxs-lookup"><span data-stu-id="28aa3-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint Document library.</span></span> <span data-ttu-id="28aa3-126">您必須在文件庫上啟用表單處理模型建立，使用者才可以為其建立表單處理模型，而管理員可以在內容瞭解管理設定中執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="28aa3-126">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="28aa3-127">表單處理模型會使用 PowerAutomate 流程，在將檔案上傳至文件庫時處理檔案。</span><span class="sxs-lookup"><span data-stu-id="28aa3-127">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="28aa3-128">表單處理模型也會建立新的[SharePoint 內容類型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)，也就是儲存在 SharePoint 內容類型庫中。</span><span class="sxs-lookup"><span data-stu-id="28aa3-128">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), which are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="28aa3-129">可以套用的位置</span><span class="sxs-lookup"><span data-stu-id="28aa3-129">Where they can be applied</span></span>

<span data-ttu-id="28aa3-130">檔理解模型可以套用到您具有存取權的不同 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="28aa3-130">Document understanding models can be applied to different SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="28aa3-131">您可以使用內容中心，不只是建立檔理解模型，也可以將它套用至不同文件庫。</span><span class="sxs-lookup"><span data-stu-id="28aa3-131">You can use the content center to not only create a document understanding model, but also to apply it to different document libraries.</span></span> <span data-ttu-id="28aa3-132">內容中心針對檔瞭解模型的使用方式及套用位置，提供了更集中的控制，因為這項資訊必須匯總至內容中心。</span><span class="sxs-lookup"><span data-stu-id="28aa3-132">The content center gives a more central control of how document understanding models are used and where they are applied, since this information must roll up to a content center.</span></span>

<span data-ttu-id="28aa3-133">表單處理模型目前只能套用到其建立所在的 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="28aa3-133">Form processing models can currently only be applied to the SharePoint document library from which they were created.</span></span> <span data-ttu-id="28aa3-134">這可讓具有網站存取權的任何授權使用者建立表單處理模型。</span><span class="sxs-lookup"><span data-stu-id="28aa3-134">This allows any licensed user who has access to the site to create a form processing model.</span></span>




 ## <a name="see-also"></a><span data-ttu-id="28aa3-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="28aa3-135">See Also</span></span>
[<span data-ttu-id="28aa3-136">訓練：使用 AI 產生器改進商務效能</span><span class="sxs-lookup"><span data-stu-id="28aa3-136">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="28aa3-137">建立分類器</span><span class="sxs-lookup"><span data-stu-id="28aa3-137">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="28aa3-138">建立提取程式</span><span class="sxs-lookup"><span data-stu-id="28aa3-138">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="28aa3-139">套用檔理解模型</span><span class="sxs-lookup"><span data-stu-id="28aa3-139">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="28aa3-140">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="28aa3-140">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>



  
  



