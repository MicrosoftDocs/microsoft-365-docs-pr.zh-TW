---
title: 表單處理概觀
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
description: 了解 Microsoft SharePoint Syntex 中的表單處理
ms.openlocfilehash: e3cf8298a2db9383e5b88dde737efc84e75c7f19
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222254"
---
# <a name="form-processing-overview"></a><span data-ttu-id="79b16-103">表單處理概觀</span><span class="sxs-lookup"><span data-stu-id="79b16-103">Form processing overview</span></span>

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="79b16-105">Microsoft SharePoint Syntex 使用 Microsoft PowerApps [AI Builder](/ai-builder/overview) 表單處理在 SharePoint 文件庫中建立模型。</span><span class="sxs-lookup"><span data-stu-id="79b16-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="79b16-106">您可以使用 AI Builder 表單處理來建立 AI 模型，這些模型使用機器學習技術從結構化或半結構化文件（如表單和發票）中識別和擷取機碼值對和表格資料。</span><span class="sxs-lookup"><span data-stu-id="79b16-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="79b16-107">組織通常從各種來源收到大量發票，如郵件、傳真、電子郵件等。處理這些文件並將其手動輸入資料庫可能需要相當長的時間。</span><span class="sxs-lookup"><span data-stu-id="79b16-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="79b16-108">透過使用 AI 來擷取文件中的文字、鑰匙/值對和表格，表單處理就能自動化這個流程。</span><span class="sxs-lookup"><span data-stu-id="79b16-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="79b16-109">如需有關表單處理案例範例的詳細資訊，請參閱 [SharePoint Syntex 採用：入門指南](./adoption-getstarted.md)。</span><span class="sxs-lookup"><span data-stu-id="79b16-109">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="79b16-110">例如，可以建立一個識別上傳到文件庫的所有採購訂單文件的表單處理模型。</span><span class="sxs-lookup"><span data-stu-id="79b16-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="79b16-111">然後，您可以從每個採購訂單中擷取並顯示對您很重要的特定資料，例如 *採購單號*、*日期* 或 *總成本*。</span><span class="sxs-lookup"><span data-stu-id="79b16-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![文件庫檢視](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="79b16-113">您使用範例檔案訓練模型，並定義要從表單中擷取的資訊。</span><span class="sxs-lookup"><span data-stu-id="79b16-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="79b16-114">文件的版面配置是透過訓練模型來學習的。</span><span class="sxs-lookup"><span data-stu-id="79b16-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="79b16-115">您只需五份表單文件即可開始使用。</span><span class="sxs-lookup"><span data-stu-id="79b16-115">You only need five form documents to get started.</span></span> <span data-ttu-id="79b16-116">AI Builder 將分析您範例檔案中的機碼值對，您也可以手動識別那些可能沒有偵測到的項。</span><span class="sxs-lookup"><span data-stu-id="79b16-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="79b16-117">AI Builder 讓您在範例檔案上測試模型的正確性。</span><span class="sxs-lookup"><span data-stu-id="79b16-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="79b16-118">訓練併發布模型之後，您的模型會建立 [Power Automate 流程](/power-automate/getting-started)。</span><span class="sxs-lookup"><span data-stu-id="79b16-118">After you train and publish your model, your model creates a [Power Automate Flow](/power-automate/getting-started).</span></span> <span data-ttu-id="79b16-119">文件上傳至 SharePoint 文件庫時，將執行流程，並擷取在模型中識別的資料。</span><span class="sxs-lookup"><span data-stu-id="79b16-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="79b16-120">擷取的資料會顯示在模型文件庫檢視中的欄中。</span><span class="sxs-lookup"><span data-stu-id="79b16-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="79b16-121">Office 365 系統管理員需要為 SharePoint 文件庫[啟用表單處理](./set-up-content-understanding.md)，以便用戶能够在其中[建立表單處理模型](create-a-form-processing-model.md)。</span><span class="sxs-lookup"><span data-stu-id="79b16-121">An Office 365 admin needs to [enable Form processing](./set-up-content-understanding.md) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="79b16-122">您可以在設定期間選取網站，或之後在管理設定中進行設定。</span><span class="sxs-lookup"><span data-stu-id="79b16-122">You can select the sites during setup, or after setup in your management settings.</span></span>

### <a name="file-limitations"></a><span data-ttu-id="79b16-123">檔案限制</span><span class="sxs-lookup"><span data-stu-id="79b16-123">File limitations</span></span>

<span data-ttu-id="79b16-124">使用表單處理模型時，請務必記得[檔案使用量的需求和限制](/ai-builder/form-processing-model-requirements)。</span><span class="sxs-lookup"><span data-stu-id="79b16-124">When using form processing models, make sure to note the [requirements and limitations for file usage](/ai-builder/form-processing-model-requirements).</span></span>

### <a name="multi-geo-environments"></a><span data-ttu-id="79b16-125">多地理位置環境</span><span class="sxs-lookup"><span data-stu-id="79b16-125">Multi-Geo environments</span></span>

<span data-ttu-id="79b16-126">在 [Microsoft 365 多地理位置環境](../enterprise/microsoft-365-multi-geo.md)中設定 SharePoint Syntex 時，您只能將它設定為在中央位置使用表單處理。</span><span class="sxs-lookup"><span data-stu-id="79b16-126">When setting up SharePoint Syntex in a [Microsoft 365 Multi-Geo environment](../enterprise/microsoft-365-multi-geo.md), you can only configure it to use form processing in the central location.</span></span> <span data-ttu-id="79b16-127">如果您要在衛星位置使用表單處理，請連絡 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="79b16-127">If you want to use form processing in a satellite location, contact Microsoft support.</span></span>






## <a name="see-also"></a><span data-ttu-id="79b16-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="79b16-128">See Also</span></span>
  
[<span data-ttu-id="79b16-129">Power Automate 文件</span><span class="sxs-lookup"><span data-stu-id="79b16-129">Power Automate documentation</span></span>](/power-automate/)

[<span data-ttu-id="79b16-130">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="79b16-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="79b16-131">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="79b16-131">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="79b16-132">訓練：使用 AI Builder 改善商務效能</span><span class="sxs-lookup"><span data-stu-id="79b16-132">Training: Improve business performance with AI Builder</span></span>](/learn/paths/improve-business-performance-ai-builder/?source=learn)