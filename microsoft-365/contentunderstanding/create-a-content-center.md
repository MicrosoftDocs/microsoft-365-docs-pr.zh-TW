---
title: 在 Microsoft SharePoint Syntex 中建立內容中心
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何建立內容中心。
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295429"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="407f1-103">在 Microsoft SharePoint Syntex 中建立內容中心</span><span class="sxs-lookup"><span data-stu-id="407f1-103">Create a content center in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="407f1-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="407f1-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="407f1-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="407f1-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="407f1-106">若要建立及管理檔理解模型，您必須先使用內容中心。</span><span class="sxs-lookup"><span data-stu-id="407f1-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="407f1-107">內容中心是模型建立介面，也包含已發佈模型已套用至哪些文件庫的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="407f1-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![選取 doc 文件庫](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="407f1-109">您在 [安裝](set-up-content-understanding.md)期間建立初始內容中心。</span><span class="sxs-lookup"><span data-stu-id="407f1-109">You create an initial content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="407f1-110">不過，SharePoint 管理員也可以視需要選擇建立其他的中心。</span><span class="sxs-lookup"><span data-stu-id="407f1-110">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="407f1-111">雖然單一內容中心對於您要匯總所有模型活動的環境可能很好，但您可能想要讓組織中的多個部門有其他的中心，其模型可能會有不同的需求和需求。</span><span class="sxs-lookup"><span data-stu-id="407f1-111">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="407f1-112">SharePoint 系統管理員可以建立內容中心網站，例如他們會使用網站範本 [建立其他任何 SharePoint 網站](https://docs.microsoft.com/sharepoint/create-site-collection) 。</span><span class="sxs-lookup"><span data-stu-id="407f1-112">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) by using a site template.</span></span>

<span data-ttu-id="407f1-113">若要建立新的內容中心：</span><span class="sxs-lookup"><span data-stu-id="407f1-113">To create a new content center:</span></span>

1. <span data-ttu-id="407f1-114">在 Microsoft 365 系統管理中心中，移至 SharePoint 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="407f1-114">From the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="407f1-115">在 SharePoint 系統管理中心的 [ **網站**] 底下，選取 [作用中 **網站**]。</span><span class="sxs-lookup"><span data-stu-id="407f1-115">In the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="407f1-116">在 [使用中的 **網站** ] 頁面上，按一下 [ **建立**]，然後選取 [ **其他選項**]。</span><span class="sxs-lookup"><span data-stu-id="407f1-116">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="407f1-117">在 [ **選擇範本** ] 功能表上，選取 [ **內容中心**]。</span><span class="sxs-lookup"><span data-stu-id="407f1-117">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="407f1-118">針對新網站，提供 **網站名稱**、 **主要系統管理員**和 **語言**。</span><span class="sxs-lookup"><span data-stu-id="407f1-118">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="407f1-119">您可以選擇性地選取內容中心網站，以在任何可用的語言中呈現。</span><span class="sxs-lookup"><span data-stu-id="407f1-119">You can optionally select a content center site to render in any of the available languages.</span></span> <span data-ttu-id="407f1-120">只有目前的型號可以建立英文檔案。</span><span class="sxs-lookup"><span data-stu-id="407f1-120">Only current models can be created for English files.</span></span></br>

6. <span data-ttu-id="407f1-121">選取 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="407f1-121">Select **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="407f1-122">授與其他使用者的存取權</span><span class="sxs-lookup"><span data-stu-id="407f1-122">Give access to additional users</span></span>
 
<span data-ttu-id="407f1-123">在您建立網站之後，您可以透過標準的 [SharePoint 網站許可權模型](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)，授與其他使用者對網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="407f1-123">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="407f1-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="407f1-124">See Also</span></span>
[<span data-ttu-id="407f1-125">建立分類器</span><span class="sxs-lookup"><span data-stu-id="407f1-125">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="407f1-126">建立提取程式</span><span class="sxs-lookup"><span data-stu-id="407f1-126">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="407f1-127">[建立內容中心](create-a-content-center.md) 
[檔理解概述](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="407f1-127">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="407f1-128">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="407f1-128">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="407f1-129">套用模型</span><span class="sxs-lookup"><span data-stu-id="407f1-129">Apply a model</span></span>](apply-a-model.md)    
