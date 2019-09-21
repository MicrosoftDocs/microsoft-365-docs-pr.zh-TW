---
title: 設定進階電子文件中的智慧標籤
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
description: 智慧標籤可讓您套用機器學習功能檢閱進階電子文件探索案例中的內容時。 使用智慧標籤群組來顯示機器學習偵測模型，例如律師-委託人權限模型的結果。
ms.openlocfilehash: 68b558cc2282cc388387f8d61825b9ee569ff32a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077511"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="c8955-104">設定進階電子文件中的智慧標籤</span><span class="sxs-lookup"><span data-stu-id="c8955-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="c8955-105">進階電子文件中的機器學習 (ML) 功能可協助您做出決策程序更有效率，檢閱區分大小的文件組中的檢閱時。</span><span class="sxs-lookup"><span data-stu-id="c8955-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="c8955-106">智慧標籤是帶的 ML 功能，以決定記錄的其中一種方法： 當期間檢閱標記的文件。</span><span class="sxs-lookup"><span data-stu-id="c8955-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="c8955-107">當您建立的智慧標籤群組時，然後您已與智慧標籤群組相關聯的 ML 模型的結果的決策會顯示在線具有 [標記] 群組中的標記。</span><span class="sxs-lookup"><span data-stu-id="c8955-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="c8955-108">這有助於看到 ML 結果在檢閱特定文件資訊中的行。</span><span class="sxs-lookup"><span data-stu-id="c8955-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="c8955-109">如何設定的智慧標籤群組</span><span class="sxs-lookup"><span data-stu-id="c8955-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="c8955-110">在 [檢閱設定，按一下 [**管理檢閱設定**，然後按一下**管理標記**。</span><span class="sxs-lookup"><span data-stu-id="c8955-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="c8955-111">按一下 [**新增標籤群組**，然後選取 [**新增智慧標籤群組**。</span><span class="sxs-lookup"><span data-stu-id="c8955-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="c8955-112">選取您想要關聯至標籤群組 ML 模型。</span><span class="sxs-lookup"><span data-stu-id="c8955-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="c8955-113">這會建立一個標記群組和*N*子標籤，其中*N*是可能輸出模型的數目。</span><span class="sxs-lookup"><span data-stu-id="c8955-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="c8955-114">例如，[律師-委託人權限偵測模型](attorney-privilege-detection.md)有兩個可能的輸出：</span><span class="sxs-lookup"><span data-stu-id="c8955-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="c8955-115">**正數**– 包含律師-委託人特殊權限內容的標籤文件的使用。</span><span class="sxs-lookup"><span data-stu-id="c8955-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="c8955-116">**負值**– 使用不含律師-委託人特殊權限內容的標籤文件。</span><span class="sxs-lookup"><span data-stu-id="c8955-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="c8955-117">如果您選取此模型，標記具有兩個的子系標記為建立群組 （一個子系標記名為**正值**與其他具名**負值**） 檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="c8955-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="c8955-118">在這個範例中，每一個子系標記會對應至下列其中一個可能輸出律師-委託人權限偵測模型。</span><span class="sxs-lookup"><span data-stu-id="c8955-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="c8955-119">或者，您可以重新命名 [標記] 群組及子系標記。</span><span class="sxs-lookup"><span data-stu-id="c8955-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="c8955-120">例如，您無法重新命名**誤判**標記**特殊權限**和**負數**的標記，以**不特殊權限**。</span><span class="sxs-lookup"><span data-stu-id="c8955-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="c8955-121">如何使用智慧標籤</span><span class="sxs-lookup"><span data-stu-id="c8955-121">How to use smart tags</span></span>

<span data-ttu-id="c8955-122">檢閱文件時, 模型的結果會顯示適當的子系標記旁。</span><span class="sxs-lookup"><span data-stu-id="c8955-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="c8955-123">例如，如果您有律師-委託人權限偵測的智慧標籤群組，且您檢閱可能特殊權限的文件，該結論的原因會顯示適當的標籤旁。</span><span class="sxs-lookup"><span data-stu-id="c8955-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="c8955-124">請務必注意，標籤不會自動套用至文件。</span><span class="sxs-lookup"><span data-stu-id="c8955-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="c8955-125">檢閱者進行決策來標記文件。</span><span class="sxs-lookup"><span data-stu-id="c8955-125">The reviewer makes the decision about how to tag the document.</span></span>