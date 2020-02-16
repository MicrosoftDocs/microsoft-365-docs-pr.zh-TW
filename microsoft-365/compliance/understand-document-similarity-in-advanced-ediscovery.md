---
title: 了解在 Office 365 進階電子文件探索中的文件相似性
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
description: '檢閱文件相似性值，最低的層級的兩個檔案被視為接近重複，跟在 Office 365 進階電子文件探索中的運作方式。 '
ms.openlocfilehash: b5c777579e876e54032ce5872291a2791e2c3b09
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080764"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a><span data-ttu-id="59c1a-103">了解在 Office 365 進階電子文件探索中的文件相似性</span><span class="sxs-lookup"><span data-stu-id="59c1a-103">Understand document similarity in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="59c1a-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="59c1a-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="59c1a-106">在進階電子文件，文件相似性是跟所需的兩個文件被視為接近重複的最低層級。</span><span class="sxs-lookup"><span data-stu-id="59c1a-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="59c1a-107">對於大多數的商務應用程式，建議使用相似性值的 60%的 75%。</span><span class="sxs-lookup"><span data-stu-id="59c1a-107">For most business applications, it is recommended to use a Similarity value of 60%-75%.</span></span> <span data-ttu-id="59c1a-108">非常不佳的品質光學字元辨識 (OCR) 材料，可以套用較低的相似性值。</span><span class="sxs-lookup"><span data-stu-id="59c1a-108">For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="59c1a-109">已設定，並針對特定情況下執行之後，就無法變更相似性值。</span><span class="sxs-lookup"><span data-stu-id="59c1a-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="59c1a-110">Near-複本 (ND) 在集內，可能會有的跟低於相似性閾值等級的文件。</span><span class="sxs-lookup"><span data-stu-id="59c1a-110">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold.</span></span> <span data-ttu-id="59c1a-111">加入 ND 組，文件中必須有至少一個文件使用跟超過相似性的層級設定 ND。</span><span class="sxs-lookup"><span data-stu-id="59c1a-111">For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="59c1a-112">例如，假設相似性設為 80%、 文件 F1 類似的 85%的層級的文件 f2 鍵和文件 f2 鍵的格式類似於文件 F3 90%的層級。</span><span class="sxs-lookup"><span data-stu-id="59c1a-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="59c1a-113">不過，文件 F1 可能類似文件 F3 僅 70%以下，以低於閾值的層級。</span><span class="sxs-lookup"><span data-stu-id="59c1a-113">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold.</span></span> <span data-ttu-id="59c1a-114">不過，在此範例中，文件中，F1、 F2、 F3 所有都會出現在一個 ND 設定。</span><span class="sxs-lookup"><span data-stu-id="59c1a-114">Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set.</span></span> <span data-ttu-id="59c1a-115">同樣地，使用相似性值的 80%，我們可能會建立兩組，EquiSet-1 和 EquiSet-2。</span><span class="sxs-lookup"><span data-stu-id="59c1a-115">Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2.</span></span> <span data-ttu-id="59c1a-116">EquiSet 1] 會包含文件 E1 和 E2。</span><span class="sxs-lookup"><span data-stu-id="59c1a-116">EquiSet-1 contains documents E1 and E2.</span></span> <span data-ttu-id="59c1a-117">Equiset 2 包含 F1，F2、 F3 的文件。</span><span class="sxs-lookup"><span data-stu-id="59c1a-117">Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="59c1a-118">類似的層級圖例所示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="59c1a-118">The levels of resemblance are illustrated as follows:</span></span>
  
![文件相似性](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="59c1a-120">假設另一個文件，X1，會立即插入。</span><span class="sxs-lookup"><span data-stu-id="59c1a-120">Assume that another document, X1, is now inserted.</span></span> <span data-ttu-id="59c1a-121">X1 和 E3 之間跟是 87%。</span><span class="sxs-lookup"><span data-stu-id="59c1a-121">The resemblance between X1 and E3 is 87%.</span></span> <span data-ttu-id="59c1a-122">同樣地，跟 X1 和 F1 之間是 92%。</span><span class="sxs-lookup"><span data-stu-id="59c1a-122">Similarly, the resemblance between X1 and F1 is 92%.</span></span> <span data-ttu-id="59c1a-123">因此，EquiSet-1、-2、 EquiSet 和 X1 現在結合為一個 ND 設定。</span><span class="sxs-lookup"><span data-stu-id="59c1a-123">As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![文件相似性](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="59c1a-125">如果任何兩份文件或指派給一個 ND 組，它們會保持在一起 ND 組相同，即使其他文件新增至集合如果合併設定。</span><span class="sxs-lookup"><span data-stu-id="59c1a-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="59c1a-126">合併設定之後，新文件加入至集合時，可以變更樞紐分析表文件。</span><span class="sxs-lookup"><span data-stu-id="59c1a-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="59c1a-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="59c1a-127">See also</span></span>

[<span data-ttu-id="59c1a-128">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="59c1a-128">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="59c1a-129">設定分析選項</span><span class="sxs-lookup"><span data-stu-id="59c1a-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="59c1a-130">設定忽略文字</span><span class="sxs-lookup"><span data-stu-id="59c1a-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="59c1a-131">設定分析進階設定</span><span class="sxs-lookup"><span data-stu-id="59c1a-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="59c1a-132">檢視分析結果</span><span class="sxs-lookup"><span data-stu-id="59c1a-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

