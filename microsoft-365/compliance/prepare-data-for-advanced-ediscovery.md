---
title: 为 Office 365 高级电子数据展示准备数据
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: '了解如何使用 Microsoft 365 安全&amp;合规性中心准备 Office 365 数据，以便使用 Office 365 高级电子数据展示进行分析。 '
ms.openlocfilehash: be778acb3356071e9575ed708623a0b94e2b3c7a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077552"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a><span data-ttu-id="da682-103">为 Office 365 高级电子数据展示准备数据</span><span class="sxs-lookup"><span data-stu-id="da682-103">Prepare data for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="da682-104">本主题介绍如何将内容搜索的结果加载到高级电子数据展示中的案例中。</span><span class="sxs-lookup"><span data-stu-id="da682-104">This topic describes how to load the results of a Content Search in to a case in Advanced eDiscovery.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="da682-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="da682-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a><span data-ttu-id="da682-107">第 1 步：为高级电子数据展示准备 Office 365 数据</span><span class="sxs-lookup"><span data-stu-id="da682-107">Step 1: Prepare Office 365 data for Advanced eDiscovery</span></span>

<span data-ttu-id="da682-108">要使用高级电子数据展示分析数据，可以使用在 Microsoft 365 安全&amp;合规性中心（在 Microsoft 365 安全&amp;合规性中心**的内容搜索**页面上列出）中运行的内容搜索的结果，或与电子数据展示案例关联的搜索（在安全&amp;合规中心**的第一个电子数据展示**页面上列出）。</span><span class="sxs-lookup"><span data-stu-id="da682-108">To analyze data with Advanced eDiscovery, you can use the results of a Content Search that you run in the Microsoft 365 Security &amp; Compliance Center (listed on the **Content search** page in the Microsoft 365 Security &amp; Compliance Center) or a search associated with an eDiscovery case (listed on the **eDiscovery** page in the Security &amp; Compliance Center).</span></span> 
  
<span data-ttu-id="da682-109">有关在高级电子数据展示中准备用于分析的搜索结果的详细步骤，请参阅[为 Office 365 高级电子数据展示准备搜索结果。](prepare-search-results-for-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="da682-109">For the detailed steps on preparing search results for analysis in Advanced eDiscovery, see [Prepare search results for Office 365 Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="da682-110">如果您有 Office 365 以外的数据，并且希望将其导入 Office 365，以便在高级电子数据展示中准备和分析数据，请参阅将[PST 文件导入 Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)和[在 Office 365 中存档第三方数据的](https://go.microsoft.com/fwlink/p/?linkid=716918)概述。</span><span class="sxs-lookup"><span data-stu-id="da682-110">If you have data outside of Office 365 and want to import it to Office 365 so that you can prepare and analyze it in Advanced eDiscovery, a see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) and [Archiving third-party data in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).</span></span> 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a><span data-ttu-id="da682-111">步骤 2：将搜索结果数据加载到高级电子数据展示中的案例</span><span class="sxs-lookup"><span data-stu-id="da682-111">Step 2: Load search result data in to a case in Advanced eDiscovery</span></span>

<span data-ttu-id="da682-112">在安全&amp;合规性中心准备搜索结果进行分析后，下一步是将搜索结果加载到高级电子数据展示中的案例中。</span><span class="sxs-lookup"><span data-stu-id="da682-112">After you prepare the search results in the Security &amp; Compliance Center for analysis, the next step is to load the search results in to a case in Advanced eDiscovery.</span></span> <span data-ttu-id="da682-113">有关详细信息，请参阅[运行流程模块](run-the-process-module-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="da682-113">For more detailed information, see [Run the Process module](run-the-process-module-in-advanced-ediscovery.md).</span></span>
  
1. <span data-ttu-id="da682-114">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="da682-114">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="da682-115">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="da682-115">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="da682-116">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="da682-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
4. <span data-ttu-id="da682-117">单击要在高级电子数据展示中加载数据的情况**旁边的"打开"。**</span><span class="sxs-lookup"><span data-stu-id="da682-117">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
5. <span data-ttu-id="da682-118">在案例的 [首頁]\*\*\*\* 頁面上，按一下 [進階電子文件探索]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="da682-118">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![单击"切换到高级电子数据展示"以在高级电子数据展示中打开案例](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="da682-120">将显示"**连接到高级电子数据展示**进度栏"。</span><span class="sxs-lookup"><span data-stu-id="da682-120">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="da682-121">当您连接到高级电子数据展示时，案例的设置页上将显示一个容器列表。</span><span class="sxs-lookup"><span data-stu-id="da682-121">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![案例显示在高级电子数据展示中](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="da682-123">这些容器表示您在步骤 1 中的高级电子数据展示中为分析准备的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="da682-123">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="da682-124">请注意，容器的名称与安全&amp;合规性中心中的内容搜索具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="da682-124">Note that the name of the container has the same name as the Content Search in the case in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="da682-125">列表中的容器是您准备的容器。</span><span class="sxs-lookup"><span data-stu-id="da682-125">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="da682-126">如果其他用户为高级电子数据展示准备了搜索结果，则相应的容器将不会包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="da682-126">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
6. <span data-ttu-id="da682-127">要将搜索结果数据从 容器加载到高级电子数据展示中的案例中，请选择一个容器，然后单击"**处理"。**</span><span class="sxs-lookup"><span data-stu-id="da682-127">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
<span data-ttu-id="da682-128">将安全&amp;合规性中心的搜索结果添加到高级电子数据展示中的案例后，下一步是使用高级电子数据展示中的工具分析和剔除与案例相关的数据。</span><span class="sxs-lookup"><span data-stu-id="da682-128">After the search results from the Security &amp; Compliance Center are added to the case in Advanced eDiscovery, the next step is to use the tools in Advanced eDiscovery to analyze and cull the data that's relevant to the case.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="da682-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="da682-129">See also</span></span>

[<span data-ttu-id="da682-130">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="da682-130">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="da682-131">设置用户和案例</span><span class="sxs-lookup"><span data-stu-id="da682-131">Set up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="da682-132">分析案例資料</span><span class="sxs-lookup"><span data-stu-id="da682-132">Analyzing case data</span></span>](analyze-case-data-with-advanced-ediscovery.md)
  
[<span data-ttu-id="da682-133">管理相关性设置</span><span class="sxs-lookup"><span data-stu-id="da682-133">Managing Relevance setup</span></span>](manage-relevance-setup-in-advanced-ediscovery.md)
  
[<span data-ttu-id="da682-134">使用相關性模組</span><span class="sxs-lookup"><span data-stu-id="da682-134">Using the Relevance module</span></span>](use-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="da682-135">匯出案例資料</span><span class="sxs-lookup"><span data-stu-id="da682-135">Exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)

