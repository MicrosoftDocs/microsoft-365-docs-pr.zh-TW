---
title: 步驟 1： 使用 SharePoint Syntex 來識別合約檔案及提取資料
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何使用 SharePoint Syntex 來識別協定檔案，並使用 Microsoft 365 解決方案提取資料。
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281130"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="ae0b1-104">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="ae0b1-104">Step 1.</span></span> <span data-ttu-id="ae0b1-105">使用 SharePoint Syntex 來識別合約檔案及提取資料</span><span class="sxs-lookup"><span data-stu-id="ae0b1-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="ae0b1-106">您的組織需要從您接收的許多檔案中識別和分類所有合約檔的方法。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="ae0b1-107">您也想能夠在每個識別 (的合約檔案中快速查看數個重要元素，例如， *客戶*、 *合同工* 和 *費用金額*) 。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="ae0b1-108">若要這麼做，您可以使用[SharePoint Syntex](index.md)建立檔理解模型，並將其套用至文件庫。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

<span data-ttu-id="ae0b1-109">檔[瞭解](document-understanding-overview.md)使用智慧 (AI) 模型，以自動化檔案的分類和資訊提取。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-109">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="ae0b1-110">檔理解模型在從非結構化檔或半結構化檔中解壓縮資訊時也是最佳的方式，而您所需的資訊不會包含在表格或表單中（如合約）。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-110">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span>

1. <span data-ttu-id="ae0b1-111">首先，您必須尋找至少五個範例檔案，您可以用來 "訓練" 模型，以搜尋您嘗試識別 (合約) 之內容類型的特定特性。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-111">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="ae0b1-112">使用 SharePoint Syntex，建立新的檔理解模型。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-112">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="ae0b1-113">您必須先 [建立分類符](create-a-classifier.md)，才能使用您的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-113">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="ae0b1-114">訓練分類器與範例檔案，您可以教它搜尋您在公司合同中所看到的特定特性。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-114">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="ae0b1-115">例如， [建立一個 "釋義"](create-a-classifier.md#create-an-explanation) ，搜尋您的合約中的特定字串，例如 *服務合約*、 *合約條款* 和 *補償*。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-115">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="ae0b1-116">您甚至可以訓練說明，以在檔的特定區段中尋找這些字串，或位於其他字串旁邊。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-116">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="ae0b1-117">當您認為您已使用所需的資訊訓練您的分類程式時，您可以在範例檔案的範例集合上測試模型，以查看其效率。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-117">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="ae0b1-118">測試完成之後，您可以視需要選擇變更您的說明，使其更有效率。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-118">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="ae0b1-119">在您的模型中，您可以 [建立解壓縮程式](create-an-extractor.md) ，以從每個合約提取特定的資料片段。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-119">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="ae0b1-120">例如，對於每個合約，您最關心的資訊是用戶端是誰、合同工的名稱，以及總成本。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-120">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="ae0b1-121">成功建立模型之後，請[將其套用至 SharePoint 文件庫](apply-a-model.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-121">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="ae0b1-122">當您將檔上傳至文件庫時，您的檔理解模型會執行，並會識別和分類所有符合您在模型中定義的合約內容類型的檔案。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-122">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="ae0b1-123">分類為合約的所有檔案都會顯示在自訂文件庫視圖中。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-123">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="ae0b1-124">檔案也會顯示您在解壓縮程式中所定義之每個合約的值。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-124">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![文件庫中的合約](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="ae0b1-126">此外，如果您有合約的保留需求，也可以使用您的模型套用 [保留標籤](apply-a-retention-label-to-a-model.md) ，以防止在指定的時間內刪除您的合約。</span><span class="sxs-lookup"><span data-stu-id="ae0b1-126">Additionally, if you have retention requirements for your contracts, you can also use your model to [apply a retention label](apply-a-retention-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time.</span></span>

## <a name="next-step"></a><span data-ttu-id="ae0b1-127">下一步</span><span class="sxs-lookup"><span data-stu-id="ae0b1-127">Next step</span></span>

[<span data-ttu-id="ae0b1-128">步驟2。使用 Microsoft Teams 建立您的合約管理通道</span><span class="sxs-lookup"><span data-stu-id="ae0b1-128">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)