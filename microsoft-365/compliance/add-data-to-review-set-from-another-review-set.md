---
title: 將資料從一個複查集新增至另一個複查集
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
description: 瞭解如何從一項審閱集選取檔，並在高級 eDiscovery 案例中個別使用另一組檔。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285177"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="a76d1-103">從另一個複查集將資料新增至審閱集</span><span class="sxs-lookup"><span data-stu-id="a76d1-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="a76d1-104">在某些情況下，您可能需要從一部審閱集選取檔，並在另一個審校集內個別使用這些檔。</span><span class="sxs-lookup"><span data-stu-id="a76d1-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="a76d1-105">如果您已在評審集中 culled 內容，而且想要對資料子集執行分析，這一點特別有用。</span><span class="sxs-lookup"><span data-stu-id="a76d1-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="a76d1-106">請遵循本文中的工作流程，將其中一個複查集的內容新增至另一個。</span><span class="sxs-lookup"><span data-stu-id="a76d1-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="a76d1-107">建立審閱集</span><span class="sxs-lookup"><span data-stu-id="a76d1-107">Create a review set</span></span>

<span data-ttu-id="a76d1-108">開始之前，您必須建立要將資料新增至其中的審閱集。</span><span class="sxs-lookup"><span data-stu-id="a76d1-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="a76d1-109">您可以在案例的 [ **複查集** ] 索引標籤上新增新的審閱集。</span><span class="sxs-lookup"><span data-stu-id="a76d1-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="a76d1-110">如需詳細資訊，請參閱 [建立審閱集](managing-review-sets.md#create-a-review-set)。</span><span class="sxs-lookup"><span data-stu-id="a76d1-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="a76d1-111">步驟1：識別要新增至其他審閱集的內容</span><span class="sxs-lookup"><span data-stu-id="a76d1-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="a76d1-112">您可以選取來源複查集內的特定檔，或選取 [複查] 集合查詢所傳回的所有專案，以將內容從一項審閱集新增至另一個。</span><span class="sxs-lookup"><span data-stu-id="a76d1-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="a76d1-113">若要新增選取的專案，請選取專案，然後選取 [ **動作**]，然後選取 [ **新增至其他審閱集**]。</span><span class="sxs-lookup"><span data-stu-id="a76d1-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![在 [動作] 功能表中新增至其他審閱集](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="a76d1-115">步驟2：指定新增至其他審閱集的選項</span><span class="sxs-lookup"><span data-stu-id="a76d1-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="a76d1-116">在 [ **新增至其他審閱集選項** ] 飛入頁面中，選擇您想要新增專案的審閱集。</span><span class="sxs-lookup"><span data-stu-id="a76d1-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="a76d1-117">選擇是否要新增 **所有搜尋結果** 或 **選取的專案**。</span><span class="sxs-lookup"><span data-stu-id="a76d1-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="a76d1-118">**其他資訊** 提供的選項可包含專案中的所有中繼資料，以及是否要在將檔新增至新的審閱集時，透過選取 [ **標籤** ] 核取方塊) 從來源複查集中包含標記 (。</span><span class="sxs-lookup"><span data-stu-id="a76d1-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![將資料新增至另一個評審集的選項](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="a76d1-120">按一下 **[確定]** 之後，會建立新的工作 (，並將 **資料新增至另一個評審集**) ，以將內容新增至另一個評審集。</span><span class="sxs-lookup"><span data-stu-id="a76d1-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="a76d1-121">您可以移至 [ **工作** ] 索引標籤，監視此工作的進度。</span><span class="sxs-lookup"><span data-stu-id="a76d1-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="a76d1-122">如需詳細資訊，請參閱 [管理工作](managing-jobs-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="a76d1-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
