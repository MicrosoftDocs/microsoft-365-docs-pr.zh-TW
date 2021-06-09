---
title: 在 Advanced eDiscovery 中設定智慧標籤
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 智慧標籤可讓您在 Advanced eDiscovery 案例中審閱內容時，套用機器學習功能。 使用智慧標籤群組來顯示機器學習偵測模型的結果，例如律師-用戶端許可權模型。
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081080"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="07206-104">在 Advanced eDiscovery 中設定智慧標籤</span><span class="sxs-lookup"><span data-stu-id="07206-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="07206-105">Machine learning (ML) 功能 Advanced eDiscovery 可協助您在審閱集中查看案例檔時，讓決策過程更有效率。</span><span class="sxs-lookup"><span data-stu-id="07206-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="07206-106">智慧標籤是可讓決策記錄的 ML 功能：在複查期間為檔加上標籤的方式。</span><span class="sxs-lookup"><span data-stu-id="07206-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="07206-107">當您建立智慧標籤群組時，您與智慧標籤群組相關聯 ML 模型的結果會以單行顯示標籤群組中的標記。</span><span class="sxs-lookup"><span data-stu-id="07206-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="07206-108">這有助於您在查看特定檔時，以線上顯示 ML 結果資訊。</span><span class="sxs-lookup"><span data-stu-id="07206-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="07206-109">設定智慧標籤群組的方式</span><span class="sxs-lookup"><span data-stu-id="07206-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="07206-110">在 [審閱集] 中，按一下 [ **管理複查集** ]，然後按一下 [ **管理標記**]。</span><span class="sxs-lookup"><span data-stu-id="07206-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="07206-111">按一下 [ **新增標記群組** ]，然後選取 [ **新增智慧標籤群組**]。</span><span class="sxs-lookup"><span data-stu-id="07206-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="07206-112">選取您要與標記群組產生關聯的 ML 模型。</span><span class="sxs-lookup"><span data-stu-id="07206-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="07206-113">這會建立一個標記群組和 *N* 個子標記，其中 *N* 是模型的可能輸出數目。</span><span class="sxs-lookup"><span data-stu-id="07206-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="07206-114">例如， [律師-用戶端許可權偵測模型](attorney-privilege-detection.md) 有兩個可能的輸出：</span><span class="sxs-lookup"><span data-stu-id="07206-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="07206-115">**正值** –用於標記包含律師費-用戶端許可權內容的檔。</span><span class="sxs-lookup"><span data-stu-id="07206-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="07206-116">**負數** –用於標記不含律師-用戶端許可權內容的檔。</span><span class="sxs-lookup"><span data-stu-id="07206-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="07206-117">如果選取此模型，便會建立含有兩個子標記的標籤群組， (一個名為 **正值** 的子標記，另一個名為的 **負數**) 用於複查集。</span><span class="sxs-lookup"><span data-stu-id="07206-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="07206-118">在此範例中，每個子標記會對應至「律師-用戶端許可權偵測模型」的其中一個可能輸出。</span><span class="sxs-lookup"><span data-stu-id="07206-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="07206-119">您也可以選擇性地重新命名 tag 群組和子標記。</span><span class="sxs-lookup"><span data-stu-id="07206-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="07206-120">例如，您可以將 **正值** 標籤重新命名為 **特權** 標籤，而 **否定** 標籤將不會有任何 **許可權**。</span><span class="sxs-lookup"><span data-stu-id="07206-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="07206-121">如何使用智慧標籤</span><span class="sxs-lookup"><span data-stu-id="07206-121">How to use smart tags</span></span>

<span data-ttu-id="07206-122">當您審閱檔時，模型的結果會顯示在適當的子標記旁邊。</span><span class="sxs-lookup"><span data-stu-id="07206-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="07206-123">例如，如果您有用於律師-用戶端許可權偵測的智慧標籤群組，且您檢查了可能具有特權的檔，則該結論的原因會顯示在適當的標記旁邊。</span><span class="sxs-lookup"><span data-stu-id="07206-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="07206-124">請務必注意，標記不會自動套用至檔。</span><span class="sxs-lookup"><span data-stu-id="07206-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="07206-125">檢閱者會決定如何標記檔。</span><span class="sxs-lookup"><span data-stu-id="07206-125">The reviewer makes the decision about how to tag the document.</span></span>
