---
title: 在 Microsoft SharePoint Syntex 中建立內容中心
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 了解如何建立內容中心。
ms.openlocfilehash: 3544bbef7cf2f898733c7aaad620487098a2dd24
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515133"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="00d65-103">在 Microsoft SharePoint Syntex 中建立內容中心</span><span class="sxs-lookup"><span data-stu-id="00d65-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="00d65-104">若要建立及管理文件瞭解模型，首先您需要內容中心。</span><span class="sxs-lookup"><span data-stu-id="00d65-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="00d65-105">內容中心是模型建立介面，也包含已套用發佈模型之文件庫的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="00d65-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![選取文件庫](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="00d65-107">您可以在[安裝](set-up-content-understanding.md)時建立預設內容中心。</span><span class="sxs-lookup"><span data-stu-id="00d65-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="00d65-108">但 SharePoint 系統管理員也可以視需要選擇建立其他中心。</span><span class="sxs-lookup"><span data-stu-id="00d65-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="00d65-109">雖然就您想要彙總所有模型活動的環境來說，單一內容中心可能即已足夠，您可能想要有額外的中心，用於組織內的多個部門，而這對其模型可能有不同的要求和權限需求。</span><span class="sxs-lookup"><span data-stu-id="00d65-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="00d65-110">在 [Microsoft 365 多地理位置環境](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo)中，如果您在中央位置有單一預設內容中心，則只能提供該位置內模型活動的彙總。</span><span class="sxs-lookup"><span data-stu-id="00d65-110">In a [Microsoft 365 Multi-Geo environment](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo), if you have a single default content center in your central location, you can only provide a roll-up of model activity from within that location.</span></span> <span data-ttu-id="00d65-111">您目前無法取得多地理位置環境中跨伺服器域界限的模型活動彙總。</span><span class="sxs-lookup"><span data-stu-id="00d65-111">You currently cannot get a roll-up of model activity across farm-boundaries in Multi-Geo environment.</span></span> 


## <a name="create-a-content-center"></a><span data-ttu-id="00d65-112">建立內容中心</span><span class="sxs-lookup"><span data-stu-id="00d65-112">Create a content center</span></span>

<span data-ttu-id="00d65-113">SharePoint 系統管理員可以如同透過系統管理中心的網站佈建面板[建立任何其他 SharePoint 網站](https://docs.microsoft.com/sharepoint/create-site-collection)一般建立內容中心網站。</span><span class="sxs-lookup"><span data-stu-id="00d65-113">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="00d65-114">若要建立新內容中心：</span><span class="sxs-lookup"><span data-stu-id="00d65-114">To create a new content center:</span></span>

1. <span data-ttu-id="00d65-115">在 Microsoft 365 系統管理中心上，移至 SharePoint 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="00d65-115">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>

2. <span data-ttu-id="00d65-116">在 SharePoint 系統管理中心上，選取 [網站 **]** 底下的 [使用中網站 **]**。</span><span class="sxs-lookup"><span data-stu-id="00d65-116">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>

3. <span data-ttu-id="00d65-117">在 [使用中網站 **]** 頁面上，按一下 [建立 **]**，然後選取 [其他選項 **]**。</span><span class="sxs-lookup"><span data-stu-id="00d65-117">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>

4. <span data-ttu-id="00d65-118">在 [選擇範本 **]** 功能表上，選取 [內容中心 **]**。</span><span class="sxs-lookup"><span data-stu-id="00d65-118">On the **Choose a template** menu, select **Content Center**.</span></span>

5. <span data-ttu-id="00d65-119">針對新網站，提供 [網站名稱 **]**、[主要系統管理員 **]**，以及 [語言 **]**。</span><span class="sxs-lookup"><span data-stu-id="00d65-119">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

   > [!NOTE] 
   > <span data-ttu-id="00d65-120">您可以選取內容中心網站，以利用任何可用語言呈現，但請注意，目前的模型只能為英文檔案建立。</span><span class="sxs-lookup"><span data-stu-id="00d65-120">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="00d65-121">另請注意，如同其他網站範本，網站建立之後，即無法編輯預設網站語言。</span><span class="sxs-lookup"><span data-stu-id="00d65-121">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="00d65-122">選取 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="00d65-122">Select **Finished**.</span></span>
 
<span data-ttu-id="00d65-123">建立內容中心網站之後，您會在 SharePoint 系統管理中心的 [使用中網站 **]** 頁面上看到該網站。</span><span class="sxs-lookup"><span data-stu-id="00d65-123">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="00d65-124">授與其他使用者存取權</span><span class="sxs-lookup"><span data-stu-id="00d65-124">Give access to additional users</span></span>
 
<span data-ttu-id="00d65-125">建立網站後，您可以透過標準的 [SharePoint 網站權限模型](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)，為其他使用者提供網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="00d65-125">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="00d65-126">請參閱</span><span class="sxs-lookup"><span data-stu-id="00d65-126">See Also</span></span>
[<span data-ttu-id="00d65-127">建立分類器</span><span class="sxs-lookup"><span data-stu-id="00d65-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="00d65-128">建立擷取器</span><span class="sxs-lookup"><span data-stu-id="00d65-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="00d65-129">建立內容中心</span><span class="sxs-lookup"><span data-stu-id="00d65-129">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="00d65-130">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="00d65-130">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="00d65-131">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="00d65-131">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="00d65-132">套用模型</span><span class="sxs-lookup"><span data-stu-id="00d65-132">Apply a model</span></span>](apply-a-model.md)    
