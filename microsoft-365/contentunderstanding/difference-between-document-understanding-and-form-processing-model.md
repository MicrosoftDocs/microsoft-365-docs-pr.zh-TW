---
title: 文件瞭解和表單處理模型之間的差異
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
description: 描述文件瞭解和表單處理模型之間的差異
ms.openlocfilehash: f57d220eb77a783de5ac352f3cf684364252a163
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975874"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a><span data-ttu-id="87551-103">文件瞭解和表單處理模型之間的差異</span><span class="sxs-lookup"><span data-stu-id="87551-103">Difference between document understanding and form processing models</span></span> 


<span data-ttu-id="87551-104">Microsoft SharePoint Syntex 中的內容瞭解可讓您識別並分類上傳至 SharePoint 文件庫的文件，以及擷取每個檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="87551-104">Content understanding in Microsoft SharePoint Syntex allows you to identify and classify documents that are uploaded to SharePoint document libraries, and extract relevant information from each file.</span></span>  <span data-ttu-id="87551-105">例如，當文件上傳到 SharePoint 文件庫時，所有識別為 *[採購單]* 的檔案都將被分類，然後顯示在自訂文件庫檢視中。</span><span class="sxs-lookup"><span data-stu-id="87551-105">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such, and then displayed in a custom document library view.</span></span> <span data-ttu-id="87551-106">此外，還可以從每個檔案中提取特定資訊（例如，*PO 號* 和 *總額*），並將其作為欄顯示在文件庫檢視中。</span><span class="sxs-lookup"><span data-stu-id="87551-106">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it as a column in your document library view.</span></span> 

<span data-ttu-id="87551-107">內容瞭解讓您建立 *模型* 來識別和擷取所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="87551-107">Content understanding lets you create *models* to identify and extract the information you need.</span></span> <span data-ttu-id="87551-108">模型在協助解決搜尋、業務流程、合規性和許多其他方面的業務問題方面具有價值。</span><span class="sxs-lookup"><span data-stu-id="87551-108">Models have value in helping to resolve business issues for search, business processes, compliance, and many others.</span></span>

<span data-ttu-id="87551-109">您可以使用兩種模型類型：</span><span class="sxs-lookup"><span data-stu-id="87551-109">There are two model types that you can use:</span></span>

- [<span data-ttu-id="87551-110">文件瞭解模型</span><span class="sxs-lookup"><span data-stu-id="87551-110">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="87551-111">表單處理模型</span><span class="sxs-lookup"><span data-stu-id="87551-111">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="87551-112">雖然這兩種模型通常用於相同用途，但以下列出的關鍵差異會影響您可以使用哪種模型。</span><span class="sxs-lookup"><span data-stu-id="87551-112">While both models are generally used for the same purpose, the key differences listed below affect which ones you can use.</span></span>

> [!NOTE]
> <span data-ttu-id="87551-113">如需有關表單處理和文件瞭解案例範例的詳細資訊，請參閱 [SharePoint Syntex 採用：入門指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)。</span><span class="sxs-lookup"><span data-stu-id="87551-113">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing and document understanding scenario examples.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="87551-114">結構化、非結構化和半結構化內容</span><span class="sxs-lookup"><span data-stu-id="87551-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="87551-115">使用文件瞭解模型從非結構化文件（如信件或合約）中識別和擷取資料，這些文件中要擷取的文字實體位於句子或文件的特定區域中。</span><span class="sxs-lookup"><span data-stu-id="87551-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract is in sentences or specific regions of the document.</span></span> <span data-ttu-id="87551-116">例如，非結構化文件可以是可以用不同方式撰寫的合同續約函。</span><span class="sxs-lookup"><span data-stu-id="87551-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="87551-117">不過，資訊會持續存在於每個合同續約文件的本文中，例如文字字串 *服務開始日期* 後接著實際日期。</span><span class="sxs-lookup"><span data-stu-id="87551-117">However, information exists consistently in the body of each contract renewal document, such as the text string *Service start date of* followed by an actual date.</span></span>

<span data-ttu-id="87551-118">使用表單處理模型來識別檔案並從結構化或半結構化文件（如表單或發票）中擷取資料。</span><span class="sxs-lookup"><span data-stu-id="87551-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices.</span></span> <span data-ttu-id="87551-119">表單處理模型經過訓練，能够從範例文件中瞭解表單的版面配置，並學會查找需要從類似位置擷取的資料。</span><span class="sxs-lookup"><span data-stu-id="87551-119">Form processing models are trained to understand the layout of your form from example documents, and learn to look for the data you need to extract from similar locations.</span></span> <span data-ttu-id="87551-120">表單通常具有更具結構化的版面配置，其中實體皆位於同一個位置 (例如，在稅務表單中的社會保險號碼)。</span><span class="sxs-lookup"><span data-stu-id="87551-120">Forms usually have a more structured layout where entities are in the same location (for example, a social security number in a tax form).</span></span>

> [!NOTE]
> <span data-ttu-id="87551-121">您必須具有内容中心網站的存取權限才能建立文件瞭解模型或將其套用至 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="87551-121">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 


## <a name="where-models-are-created"></a><span data-ttu-id="87551-122">建立模型的位置</span><span class="sxs-lookup"><span data-stu-id="87551-122">Where models are created</span></span>

<span data-ttu-id="87551-123">文件瞭解模型在 SharePoint 內容中心網站中建立和管理。</span><span class="sxs-lookup"><span data-stu-id="87551-123">Document understanding models are created and managed in a SharePoint content center site.</span></span> 

> [!NOTE]
> <span data-ttu-id="87551-124">如需有關輸入檔的詳細資訊，請參閱[表單處理模型需求和限制](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)。</span><span class="sxs-lookup"><span data-stu-id="87551-124">For more information about input documents, see [Form processing model requirements and limitations](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

<span data-ttu-id="87551-125">表單處理模型是在 PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)中建立，但建立是直接從 SharePoint 文件庫啟動。</span><span class="sxs-lookup"><span data-stu-id="87551-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation starts directly from a SharePoint document library.</span></span> <span data-ttu-id="87551-126">文件庫必須先啟用表單處理模型建立，使用者才能建立表單處理模型。</span><span class="sxs-lookup"><span data-stu-id="87551-126">A document library must have form processing model creation enabled before a user can create a form processing model for it.</span></span> <span data-ttu-id="87551-127">系統管理員可以在內容瞭解系統管理員設定中啟用表單處理模型建立。</span><span class="sxs-lookup"><span data-stu-id="87551-127">Admins can enable form processing model creation in the content understanding admin settings.</span></span> <span data-ttu-id="87551-128">表單處理模型使用 PowerAutomate 流程以在文件上傳到文件庫時處理這些檔案。</span><span class="sxs-lookup"><span data-stu-id="87551-128">Form processing models use PowerAutomate flows to process files when they're uploaded to the document library.</span></span>

<span data-ttu-id="87551-129">當您建立文件瞭解模型時，將建立儲存在 SharePoint 內容類型庫中的 [新 SharePoint 內容類型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)。</span><span class="sxs-lookup"><span data-stu-id="87551-129">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="87551-130">或者，您可以視需要使用現有內容類型來定義模型。</span><span class="sxs-lookup"><span data-stu-id="87551-130">Or you can use existing content types to define your model if needed.</span></span>

<span data-ttu-id="87551-131">表單處理模型也會建立 [新 SharePoint 內容類型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)，而且也會儲存在 SharePoint 內容類型庫中。</span><span class="sxs-lookup"><span data-stu-id="87551-131">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), and are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="87551-132">可以套用的位置</span><span class="sxs-lookup"><span data-stu-id="87551-132">Where they can be applied</span></span>

<span data-ttu-id="87551-133">您可以將文件瞭解模型套用至您有權存取的 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="87551-133">You can apply document understanding models to SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="87551-134">使用內容中心建立文件瞭解模型，並將它套用至不同的文件庫。</span><span class="sxs-lookup"><span data-stu-id="87551-134">Use the content center to create a document understanding model, and apply it to different document libraries.</span></span> <span data-ttu-id="87551-135">内容中心使您能够更集中地控制文件瞭解模型的使用方式和套用位置。</span><span class="sxs-lookup"><span data-stu-id="87551-135">The content center gives you a more central control for how document understanding models are used and where they're applied.</span></span> <span data-ttu-id="87551-136">注意：此資訊還必須匯總到内容中心。</span><span class="sxs-lookup"><span data-stu-id="87551-136">Note this information must also roll up to a content center.</span></span>

<span data-ttu-id="87551-137">表單處理模型目前只能套用到您建立它們時使用的 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="87551-137">Form processing models can currently only be applied to the SharePoint document library from which you created them.</span></span> <span data-ttu-id="87551-138">這可讓擁有網站存取權的授權使用者建立表單處理模型。</span><span class="sxs-lookup"><span data-stu-id="87551-138">This allows licensed users with access to the site to create a form processing model.</span></span> <span data-ttu-id="87551-139">請注意，您的系統管理員必須在 SharePoint 文件庫啟用表單處理，以供授權使用者使用之。</span><span class="sxs-lookup"><span data-stu-id="87551-139">Note that an admin needs to enable form processing on a SharePoint document library for it to be available to licensed users.</span></span>

 ## <a name="see-also"></a><span data-ttu-id="87551-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="87551-140">See Also</span></span>
[<span data-ttu-id="87551-141">訓練：使用 AI Builder 改善商務效能</span><span class="sxs-lookup"><span data-stu-id="87551-141">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[<span data-ttu-id="87551-142">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="87551-142">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="87551-143">表單處理概觀</span><span class="sxs-lookup"><span data-stu-id="87551-143">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="87551-144">SharePoint Syntex 簡介</span><span class="sxs-lookup"><span data-stu-id="87551-144">Introduction to SharePoint Syntex</span></span>](index.md)
