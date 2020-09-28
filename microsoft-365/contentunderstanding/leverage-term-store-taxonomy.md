---
title: 建立提取程式時利用字詞存放區分類
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 在 Microsoft SharePoint Syntex 中的檔理解模型中建立提取程式時，利用字詞存放區分類。
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295774"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="cf271-103">建立提取程式時利用字詞存放區分類</span><span class="sxs-lookup"><span data-stu-id="cf271-103">Leverage term store taxonomy when creating an extractor</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="cf271-104">當您在 SharePoint Syntex 中的檔理解模型中建立解壓縮程式時，您可以利用 [受管理的中繼資料服務](https://docs.microsoft.com/sharepoint/managed-metadata#terms) 字詞庫分類法，以顯示您提取之資料的慣用字詞。</span><span class="sxs-lookup"><span data-stu-id="cf271-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="cf271-105">例如，您的模型會識別和分類所有上傳至文件庫的 **合約** 檔。</span><span class="sxs-lookup"><span data-stu-id="cf271-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="cf271-106">此外，此模型也會從每個合約中解壓縮 **合約服務** 值，並將其顯示在文件庫視圖中的一欄。</span><span class="sxs-lookup"><span data-stu-id="cf271-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="cf271-107">在合同中的各種合約服務值中，您公司不再使用的數個舊值，且已重新命名。</span><span class="sxs-lookup"><span data-stu-id="cf271-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="cf271-108">例如，所有對字詞 *設計*、 *圖形*或 *拓撲* 的合約服務的參考，都應該稱為 *創造性*。</span><span class="sxs-lookup"><span data-stu-id="cf271-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="cf271-109">當您的模型從合約檔中解壓縮一個過期的字詞時，您想要讓它在您的文件庫視圖中顯示目前的字詞創意。</span><span class="sxs-lookup"><span data-stu-id="cf271-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="cf271-110">在下列範例中，訓練模型時，我們看到一個範例檔會包含已過時的 *設計*術語。</span><span class="sxs-lookup"><span data-stu-id="cf271-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![字詞庫](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a><span data-ttu-id="cf271-112">字詞集合同義字</span><span class="sxs-lookup"><span data-stu-id="cf271-112">Term set synonyms</span></span> 

<span data-ttu-id="cf271-113">字片語是在受管理的中繼資料服務術語存放區的 SharePoint 系統管理中心設定。</span><span class="sxs-lookup"><span data-stu-id="cf271-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="cf271-114">在下列範例中， *合約服務*字片語 [設定](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) 為包含許多字詞，包括 *創造性*。</span><span class="sxs-lookup"><span data-stu-id="cf271-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="cf271-115">它的詳細資料會顯示這項字詞具有三個同義字 (*設計*、 *圖形*和 *拓撲*) ，且同義字應轉譯成 *創造性*。</span><span class="sxs-lookup"><span data-stu-id="cf271-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span>

   ![字詞組](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="cf271-117"><Mike，這裡是我無法確定如何描述這種情況的地方。</span><span class="sxs-lookup"><span data-stu-id="cf271-117"><Mike, here is where I am unsure about how to describe this.</span></span>  <span data-ttu-id="cf271-118">什麼動作會告訴模型當我建立提取器以提取及顯示合約服務欄時，該資料行如何「標示」如何使用受管理的中繼資料字片語進行創造性服務？ ></span><span class="sxs-lookup"><span data-stu-id="cf271-118">What action tells the model that when I create an extractor to extract and display a Contract Services column, how is that column "marked" to use the managed metadata term set for Creative Services?></span></span>

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a><span data-ttu-id="cf271-119">設定受管理的元資料欄位的文件庫網站欄</span><span class="sxs-lookup"><span data-stu-id="cf271-119">Configure your document library site column for a managed metadata field</span></span>


   ![建立受管理的中繼資料](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a><span data-ttu-id="cf271-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cf271-121">See Also</span></span>
[<span data-ttu-id="cf271-122">受管理的中繼資料簡介</span><span class="sxs-lookup"><span data-stu-id="cf271-122">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[<span data-ttu-id="cf271-123">建立提取程式</span><span class="sxs-lookup"><span data-stu-id="cf271-123">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="cf271-124">建立受管理的中繼資料欄</span><span class="sxs-lookup"><span data-stu-id="cf271-124">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





