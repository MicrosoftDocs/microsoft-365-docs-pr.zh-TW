---
title: '建立內容中心 (預覽) '
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
description: 瞭解如何建立內容中心。
ms.openlocfilehash: ae10cdae2fe84abf72cf09141798b628d88a504a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950093"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="08241-103">建立內容中心 (預覽) </span><span class="sxs-lookup"><span data-stu-id="08241-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="08241-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="08241-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="08241-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="08241-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="08241-106">若要建立及管理檔理解模型，您必須先使用內容中心。</span><span class="sxs-lookup"><span data-stu-id="08241-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="08241-107">內容中心是模型建立介面，也包含已發佈模型已套用之文件庫的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="08241-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![選取 doc 文件庫](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="08241-109">初始內容中心是在 [安裝](set-up-content-understanding.md)期間建立，但 SharePoint 管理員可以視需要選擇建立其他專案。</span><span class="sxs-lookup"><span data-stu-id="08241-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="08241-110">雖然單一內容中心可能是您想要查看所有模型活動匯總的環境，但若您的組織中有多個部門可能對其模型有不同的需求和需求，您可能想要有其他的內容中心。</span><span class="sxs-lookup"><span data-stu-id="08241-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="08241-111">SharePoint 系統管理員可以建立內容中心網站，例如他們會透過網站範本 [建立其他任何 SharePoint 網站](https://docs.microsoft.com/sharepoint/create-site-collection) 。</span><span class="sxs-lookup"><span data-stu-id="08241-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="08241-112">若要建立新的內容中心：</span><span class="sxs-lookup"><span data-stu-id="08241-112">To create a new content center:</span></span>

1. <span data-ttu-id="08241-113">在 Microsoft 365 系統管理中心，移至 SharePoint 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="08241-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="08241-114">在 SharePoint 系統管理中心的 [ **網站**] 底下，選取 [作用中 **網站**]。</span><span class="sxs-lookup"><span data-stu-id="08241-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="08241-115">在 [使用中的 **網站** ] 頁面上，按一下 [ **建立**]，然後選取 [ **其他選項**]。</span><span class="sxs-lookup"><span data-stu-id="08241-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="08241-116">在 [ **選擇範本** ] 功能表上，選取 [ **內容中心**]。</span><span class="sxs-lookup"><span data-stu-id="08241-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="08241-117">針對新網站，提供 **網站名稱**、 **主要系統管理員**和 **語言**。</span><span class="sxs-lookup"><span data-stu-id="08241-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="08241-118">您可以選擇以任何可用語言呈現的內容中心網站，但請注意，目前的模型只可為英文檔案建立。</span><span class="sxs-lookup"><span data-stu-id="08241-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="08241-119">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="08241-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="08241-120">授與其他使用者的存取權</span><span class="sxs-lookup"><span data-stu-id="08241-120">Give access to additional users</span></span>
 
<span data-ttu-id="08241-121">在建立網站後，您可以透過標準的 [SharePoint 網站許可權模型](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)，授與其他使用者對網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="08241-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="08241-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="08241-122">See Also</span></span>
[<span data-ttu-id="08241-123">建立分類器</span><span class="sxs-lookup"><span data-stu-id="08241-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="08241-124">建立提取程式</span><span class="sxs-lookup"><span data-stu-id="08241-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="08241-125">[建立內容中心](create-a-content-center.md) 
[檔理解概述](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="08241-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="08241-126">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="08241-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="08241-127">套用模型</span><span class="sxs-lookup"><span data-stu-id="08241-127">Apply a model</span></span>](apply-a-model.md)    




