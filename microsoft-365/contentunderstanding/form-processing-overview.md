---
title: '窗 (預覽中的表單處理一覽) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解 Project Cortex 中的表單處理。
ms.openlocfilehash: de8e0ed546380059cc1b7b209eeec71f1eb779f9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950021"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="5ac6b-103">窗 (預覽中的表單處理一覽) </span><span class="sxs-lookup"><span data-stu-id="5ac6b-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="5ac6b-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="5ac6b-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="5ac6b-106">Project Cortex 使用 Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) 表單處理，以在 SharePoint 文件庫中建立模型。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="5ac6b-107">您可以使用 AI 建造器表單處理建立 AI 模型，使用電腦學習技術來識別及提取結構化或半結構化檔（如表單和發票）中的索引鍵-值對和資料表資料。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="5ac6b-108">公司通常會從各種來源（例如郵件、傳真、電子郵件或人員）收到大量發票。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="5ac6b-109">處理這些檔並手動將其輸入資料庫中，可能需要相當長的時間。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="5ac6b-110">使用 AI 提取文字、索引鍵/值組及檔中的表格，表單處理將會自動化此程式。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="5ac6b-111">例如，您可以建立表單處理模型，識別所有上傳至文件庫的採購訂單檔。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="5ac6b-112">而且，您可以從每個購買訂單提取及顯示對您很重要的特定資料，例如 *PO 號碼*、 *日期*或 *總成本*。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="5ac6b-113">您可以使用範例檔案訓練模型及定義要從表單提取的資訊。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="5ac6b-114">您可以透過訓練模型來瞭解檔的版面配置。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="5ac6b-115">您只需要五個表單檔即可開始。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-115">You only need five form documents to get started.</span></span> <span data-ttu-id="5ac6b-116">AI 產生器會分析您的金鑰-值對的範例檔案，也可以手動識別可能未偵測到的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="5ac6b-117">AI 產生器可讓您在範例檔案上測試模型的準確性。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="5ac6b-118">訓練及發行模型之後，您可以使用它來建立 [電源自動化流程](https://docs.microsoft.com/power-automate/getting-started)。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="5ac6b-119">當檔案上傳至 SharePoint 文件庫，並提取已在模型中識別的資料時，就會執行此流程。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="5ac6b-120">解壓縮的資料會顯示在模型文件庫視圖中的欄中。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="5ac6b-121">Office 365 系統管理員需要為 SharePoint 文件庫 [啟用表單處理](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) ，讓使用者能夠在其中 [建立表單處理模型](create-a-form-processing-model.md) 。</span><span class="sxs-lookup"><span data-stu-id="5ac6b-121">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="5ac6b-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5ac6b-122">See Also</span></span>
  
[<span data-ttu-id="5ac6b-123">電源自動化檔</span><span class="sxs-lookup"><span data-stu-id="5ac6b-123">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="5ac6b-124">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="5ac6b-124">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="5ac6b-125">檔理解概述</span><span class="sxs-lookup"><span data-stu-id="5ac6b-125">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="5ac6b-126">訓練：使用 AI 產生器改進商務效能</span><span class="sxs-lookup"><span data-stu-id="5ac6b-126">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




