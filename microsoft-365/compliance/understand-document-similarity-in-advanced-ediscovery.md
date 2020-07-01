---
title: 在高級 eDiscovery 中瞭解檔相似性
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 請複習檔相似性值，將兩個檔案視為接近重複的最小 resemblance 層級，可在「高級 eDiscovery」中運作。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 939e9ad6cb193e2019fe84f1e0d3482eebac721c
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936638"
---
# <a name="understand-document-similarity-in-advanced-ediscovery-classic"></a><span data-ttu-id="a38ad-103">瞭解 Advanced eDiscovery （古典）中的檔相似性</span><span class="sxs-lookup"><span data-stu-id="a38ad-103">Understand document similarity in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="a38ad-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="a38ad-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="a38ad-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="a38ad-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="a38ad-106">在 [Advanced eDiscovery] 中，「檔相似性」是兩個檔視為接近重複專案所需的最小 resemblance 層級。</span><span class="sxs-lookup"><span data-stu-id="a38ad-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="a38ad-107">對於大部分商務應用程式，建議使用類似 60%-75% 的相似性值。</span><span class="sxs-lookup"><span data-stu-id="a38ad-107">For most business applications, it is recommended to use a Similarity value of 60%-75%.</span></span> <span data-ttu-id="a38ad-108">對於品質非常差的光學字元辨識（OCR）材料，可以套用較低的相似性值。</span><span class="sxs-lookup"><span data-stu-id="a38ad-108">For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a38ad-109">在指定的情況下設定及執行時，不能變更類似值。</span><span class="sxs-lookup"><span data-stu-id="a38ad-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="a38ad-110">在近乎重複（ND）集內，您的檔的 resemblance 層級可能會低於相似性閾值。</span><span class="sxs-lookup"><span data-stu-id="a38ad-110">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold.</span></span> <span data-ttu-id="a38ad-111">若要加入 ND 集的檔，ND 集中至少必須有一個檔，且該 resemblance 的層級超過相似性。</span><span class="sxs-lookup"><span data-stu-id="a38ad-111">For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="a38ad-112">例如，假設相似性設定為80%，檔 F1 類似于85% 層級的檔 F2，而檔 F2 類似檔 F3，其層級為90%。</span><span class="sxs-lookup"><span data-stu-id="a38ad-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="a38ad-113">不過，檔 F1 可能會類似于檔 F3 的一級，只是低於臨界值的70%。</span><span class="sxs-lookup"><span data-stu-id="a38ad-113">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold.</span></span> <span data-ttu-id="a38ad-114">不過，在此範例中，檔 F1、F2 及 F3 全都出現在一組中。</span><span class="sxs-lookup"><span data-stu-id="a38ad-114">Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set.</span></span> <span data-ttu-id="a38ad-115">同樣地，使用相似性值80%，我們可能已建立兩個集合，EquiSet-1 和 EquiSet-2。</span><span class="sxs-lookup"><span data-stu-id="a38ad-115">Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2.</span></span> <span data-ttu-id="a38ad-116">EquiSet-1 包含檔 E1 和 E2。</span><span class="sxs-lookup"><span data-stu-id="a38ad-116">EquiSet-1 contains documents E1 and E2.</span></span> <span data-ttu-id="a38ad-117">Equiset-2 包含檔 F1、F2 及 F3。</span><span class="sxs-lookup"><span data-stu-id="a38ad-117">Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="a38ad-118">Resemblance 的層級如下所示：</span><span class="sxs-lookup"><span data-stu-id="a38ad-118">The levels of resemblance are illustrated as follows:</span></span>
  
![文件相似性](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="a38ad-120">假設現在已插入另一個檔（X1）。</span><span class="sxs-lookup"><span data-stu-id="a38ad-120">Assume that another document, X1, is now inserted.</span></span> <span data-ttu-id="a38ad-121">X1 和 E3 之間的 resemblance 是87%。</span><span class="sxs-lookup"><span data-stu-id="a38ad-121">The resemblance between X1 and E3 is 87%.</span></span> <span data-ttu-id="a38ad-122">同樣地，X1 和 F1 之間的 resemblance 是92%。</span><span class="sxs-lookup"><span data-stu-id="a38ad-122">Similarly, the resemblance between X1 and F1 is 92%.</span></span> <span data-ttu-id="a38ad-123">因此，EquiSet-1、EquiSet-2 和 X1 現在會結合成一個 ND 集。</span><span class="sxs-lookup"><span data-stu-id="a38ad-123">As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![文件相似性](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="a38ad-125">如果有兩個檔指派給一個 ND 集，則即使將其他檔新增至集，或合併集時，這些檔仍會保持在相同的 ND 集中。</span><span class="sxs-lookup"><span data-stu-id="a38ad-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="a38ad-126">合併設定之後，當新檔新增至集時，樞紐分析表可能會變更。</span><span class="sxs-lookup"><span data-stu-id="a38ad-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="a38ad-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="a38ad-127">Related topics</span></span>

[<span data-ttu-id="a38ad-128">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="a38ad-128">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a38ad-129">設定分析選項</span><span class="sxs-lookup"><span data-stu-id="a38ad-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a38ad-130">設定忽略文字</span><span class="sxs-lookup"><span data-stu-id="a38ad-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a38ad-131">設定分析高級設定</span><span class="sxs-lookup"><span data-stu-id="a38ad-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a38ad-132">查看分析結果</span><span class="sxs-lookup"><span data-stu-id="a38ad-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

