---
title: 準備 Office 365 進階 eDiscovery 的搜尋結果
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: 了解如何在 Office 365 的安全&合规性中心中准备内容搜索的结果，以便使用高级电子数据展示工具进行进一步分析。
ms.openlocfilehash: 244fae317964261ad1eeadbdca2d4dffeda0a23a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077835"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a><span data-ttu-id="db3a4-103">準備 Office 365 進階 eDiscovery 的搜尋結果</span><span class="sxs-lookup"><span data-stu-id="db3a4-103">Prepare search results for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="db3a4-104">在安全&合规中心中与电子数据展示案例关联的搜索成功运行后，您可以使用 Office 365 高级电子数据展示准备搜索结果以进行进一步分析，从而可以分析大型非结构化数据集和减少与法律案例相关的数据量。</span><span class="sxs-lookup"><span data-stu-id="db3a4-104">After a search that's associated with an eDiscovery case in the Security & Compliance Center is successfully run, you can prepare the search results for further analysis with Office 365 Advanced eDiscovery, which lets you analyze large, unstructured data sets and reduce the amount of data that's relevant to a legal case.</span></span> <span data-ttu-id="db3a4-105">高级电子数据展示功能包括：</span><span class="sxs-lookup"><span data-stu-id="db3a4-105">Advanced eDiscovery features include:</span></span>
  
- <span data-ttu-id="db3a4-106">**光学字符识别**- 当您为高级电子数据展示准备搜索结果时，光学字符识别 （OCR） 功能会自动从图像中提取文本，并将其与加载到用于分析的高级电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="db3a4-106">**Optical character recognition** - When you prepare search results for Advanced eDiscovery, optical character recognition (OCR) functionality automatically extracts text from images, and includes this with the search results that are loaded in to Advanced eDiscovery for analysis.</span></span> <span data-ttu-id="db3a4-107">OCR 支持松散文件、电子邮件附件和嵌入图像。</span><span class="sxs-lookup"><span data-stu-id="db3a4-107">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="db3a4-108">这允许您将高级电子数据展示（近重复、电子邮件线程、主题和预测编码）的文本分析功能应用于图像文件中的文本内容。</span><span class="sxs-lookup"><span data-stu-id="db3a4-108">This allows you to apply the text analytic capabilities of Advanced eDiscovery (near-duplicates, email threading, themes, and predictive coding) to the text content in image files.</span></span> <span data-ttu-id="db3a4-109">高级电子数据展示 OCR 支持图像文件的以下格式：</span><span class="sxs-lookup"><span data-stu-id="db3a4-109">Advanced eDiscovery OCR supports the following formats for image files:</span></span>

    - <span data-ttu-id="db3a4-110">GIF</span><span class="sxs-lookup"><span data-stu-id="db3a4-110">GIF</span></span>
    - <span data-ttu-id="db3a4-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="db3a4-111">JPEG</span></span>
    - <span data-ttu-id="db3a4-112">Jpg</span><span class="sxs-lookup"><span data-stu-id="db3a4-112">JPG</span></span>
    - <span data-ttu-id="db3a4-113">PNG</span><span class="sxs-lookup"><span data-stu-id="db3a4-113">PNG</span></span>
    - <span data-ttu-id="db3a4-114">TIFF</span><span class="sxs-lookup"><span data-stu-id="db3a4-114">TIFF</span></span>
    
- <span data-ttu-id="db3a4-115">**近乎重复的检测**- 使您能够更高效地构建数据审阅，因此一个人可以审阅一组类似的文档。</span><span class="sxs-lookup"><span data-stu-id="db3a4-115">**Near-duplicate detection** - Lets you structure your data review more efficiently, so one person reviews a group of similar documents.</span></span> <span data-ttu-id="db3a4-116">这有助于防止多个审阅者必须查看同一文档的不同版本。</span><span class="sxs-lookup"><span data-stu-id="db3a4-116">This helps prevent multiple reviewers from having to view different versions of the same document.</span></span> 
    
- <span data-ttu-id="db3a4-117">**电子邮件线程**- 帮助您识别电子邮件线程中的唯一邮件，以便您只能关注每封邮件中的新信息。</span><span class="sxs-lookup"><span data-stu-id="db3a4-117">**Email threading** - Helps you identify the unique messages in an email thread so you can focus on only the new information in each message.</span></span> <span data-ttu-id="db3a4-118">在电子邮件线程中，第二个邮件包含第一条消息。</span><span class="sxs-lookup"><span data-stu-id="db3a4-118">In an email thread, the second message contains the first message.</span></span> <span data-ttu-id="db3a4-119">同样，以后的邮件包含所有以前的消息。</span><span class="sxs-lookup"><span data-stu-id="db3a4-119">Likewise, later messages contain all the previous messages.</span></span> <span data-ttu-id="db3a4-120">电子邮件线程无需在电子邮件线程中完整查看每封邮件。</span><span class="sxs-lookup"><span data-stu-id="db3a4-120">Email threading removes the need to review every message in its entirety in an email thread.</span></span> 
    
- <span data-ttu-id="db3a4-121">**主题**- 帮助您获得关于数据的宝贵见解，而不仅仅是关键字搜索统计信息。</span><span class="sxs-lookup"><span data-stu-id="db3a4-121">**Themes** - Help you get valuable insight about your data beyond just keyword search statistics.</span></span> <span data-ttu-id="db3a4-122">主题通过分组相关文档来帮助调查，以便您可以在上下文中查看文档。</span><span class="sxs-lookup"><span data-stu-id="db3a4-122">Themes help investigations by grouping related documents so you can look at the documents in context.</span></span> <span data-ttu-id="db3a4-123">使用主题时，您可以查看一组文档的相关主题，确定任何重叠，然后标识相关数据的横截面。</span><span class="sxs-lookup"><span data-stu-id="db3a4-123">When using themes, you can view the related themes for a set of documents, determine any overlap, and then identify cross-sections of related data.</span></span> 
    
- <span data-ttu-id="db3a4-124">**预测编码**- 允许您对一组文档做出决策（关于某些内容是否相关），从而根据要查找的内容对系统进行训练。</span><span class="sxs-lookup"><span data-stu-id="db3a4-124">**Predictive coding** - Lets you train the system on what you're looking for, by allowing you to make decisions (about whether something is relevant or not) on a small set of documents.</span></span> <span data-ttu-id="db3a4-125">然后，高级电子数据展示系统在分析数据集中的所有文档时应用该学习（基于您的指导）。</span><span class="sxs-lookup"><span data-stu-id="db3a4-125">Advanced eDiscovery then applies that learning (based on your guidance) when analyzing all of the documents in the data set.</span></span> <span data-ttu-id="db3a4-126">基于该学习，高级电子数据展示提供了相关性排名，因此您可以根据最有可能与案例相关的文档来决定要审阅哪些文档。</span><span class="sxs-lookup"><span data-stu-id="db3a4-126">Based on that learning, Advanced eDiscovery provides a relevance ranking so you can decide which documents to review based on what document are the most likely to be relevant to the case.</span></span> 
    
- <span data-ttu-id="db3a4-127">**导出用于审阅应用程序的数据**- 您可以在完成分析并减少数据集后从高级电子数据展示和 Office 365 导出数据。</span><span class="sxs-lookup"><span data-stu-id="db3a4-127">**Exporting data for review applications**  - You can export data from Advanced eDiscovery and Office 365 after you've completed your analysis and reduced the data set.</span></span> <span data-ttu-id="db3a4-128">导出包包括一个 CSV 文件，该文件包含导出的内容和分析元数据的属性。</span><span class="sxs-lookup"><span data-stu-id="db3a4-128">The export package includes a CSV file that contains the properties from the exported content and analytics metadata.</span></span> <span data-ttu-id="db3a4-129">然后，可以将此导出包导入到电子数据展示审核应用程序。</span><span class="sxs-lookup"><span data-stu-id="db3a4-129">This export package can then be imported to an eDiscovery review application.</span></span> 
    
## <a name="before-you-begin"></a><span data-ttu-id="db3a4-130">開始之前</span><span class="sxs-lookup"><span data-stu-id="db3a4-130">Before you begin</span></span>

- <span data-ttu-id="db3a4-131">要使用高级电子数据展示分析用户的数据，必须为该用户（数据的保管人）分配 Office 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="db3a4-131">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="db3a4-132">或者，可以为具有 Office 365 E1 或 E3 许可证的用户分配高级电子数据展示独立许可证。</span><span class="sxs-lookup"><span data-stu-id="db3a4-132">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="db3a4-133">分配给案例并使用高级电子数据展示分析数据的管理员和合规官不需要 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="db3a4-133">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="db3a4-134">您必须是安全&合规中心中的电子数据展示经理或电子数据展示管理员，才能为高级电子数据展示准备搜索结果。</span><span class="sxs-lookup"><span data-stu-id="db3a4-134">You have to be an eDiscovery Manager or an eDiscovery Administrator in the Security & Compliance Center to prepare search results for Advanced eDiscovery.</span></span> <span data-ttu-id="db3a4-135">eDiscovery 管理員為 eDiscovery 管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="db3a4-135">An eDiscovery Manager is a member of the eDiscovery Manager role group.</span></span> <span data-ttu-id="db3a4-136">eDiscovery 系統管理員也是 eDiscovery 管理員角色群組的成員，但已獲指派其他 eDiscovery 權限。</span><span class="sxs-lookup"><span data-stu-id="db3a4-136">An eDiscovery Administrator is also member of the eDiscovery Manager role group, but has been assigned additional eDiscovery privileges.</span></span> <span data-ttu-id="db3a4-137">有关分配电子数据展示管理员权限的说明，请参阅[电子数据展示案例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的步骤 1。</span><span class="sxs-lookup"><span data-stu-id="db3a4-137">For instructions about assigning eDiscovery Administrator permissions, see Step 1 in [eDiscovery cases](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a><span data-ttu-id="db3a4-138">第 1 步：为高级电子数据展示准备搜索结果</span><span class="sxs-lookup"><span data-stu-id="db3a4-138">Step 1: Prepare search results for Advanced eDiscovery</span></span>

<span data-ttu-id="db3a4-139">您可以准备与电子数据展示案例关联的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="db3a4-139">You can prepare the results of a search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="db3a4-140">为高级电子数据展示准备搜索结果时，数据将上载并临时存储在 Microsoft 云中的唯一 Windows Azure 存储区域中。</span><span class="sxs-lookup"><span data-stu-id="db3a4-140">When you prepare search results for Advanced eDiscovery, the data is uploaded and temporarily stored in a unique Windows Azure storage area in the Microsoft cloud.</span></span> <span data-ttu-id="db3a4-141">此时，OCR 功能从搜索结果中的图像中提取文本。</span><span class="sxs-lookup"><span data-stu-id="db3a4-141">It's at this point that the OCR functionality extracts text from images in the search results.</span></span> <span data-ttu-id="db3a4-142">在[步骤 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery)中，此文本和其他搜索结果数据将加载到高级电子数据展示中的情况中。</span><span class="sxs-lookup"><span data-stu-id="db3a4-142">In [Step 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), this text and the other search results data is loaded in to the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="db3a4-143">在"安全&合规中心"中，**单击"电子数据**\>**展示"** 以显示组织中的案件列表。</span><span class="sxs-lookup"><span data-stu-id="db3a4-143">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="db3a4-144">单击**要**准备搜索结果以在高级电子数据展示中进行分析的案例旁边打开。</span><span class="sxs-lookup"><span data-stu-id="db3a4-144">Click **Open** next to the case that you want to prepare search results for analysis in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="db3a4-145">在案例的**主页**上，单击"**搜索"，** 然后选择搜索。</span><span class="sxs-lookup"><span data-stu-id="db3a4-145">On the **Home** page for the case, click **Search**, and then select the search.</span></span>
    
4. <span data-ttu-id="db3a4-146">在详细信息窗格中，**在"使用高级电子数据展示分析结果"** 下，**单击"准备结果进行分析"。**</span><span class="sxs-lookup"><span data-stu-id="db3a4-146">In the details pane, under **Analyze results with Advanced eDiscovery**, click **Prepare results for analysis**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="db3a4-147">如果搜尋的結果是早於 7 天前，則會提示您更新搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="db3a4-147">If the search results are older than 7 days, you will be prompted to update the search results.</span></span> 
  
5. <span data-ttu-id="db3a4-148">在**準備供分析的結果**的頁面上，執行下列動作︰ </span><span class="sxs-lookup"><span data-stu-id="db3a4-148">On the **Prepare results for analysis** page, do the following:</span></span> 
    
    - <span data-ttu-id="db3a4-149">选择在高级电子数据展示中准备索引项、索引和未编制索引的项目，或仅准备未编制索引的项目进行分析。</span><span class="sxs-lookup"><span data-stu-id="db3a4-149">Choose to prepare indexed items, indexed and unindexed items, or only unindexed items for analysis in Advanced eDiscovery.</span></span>
    
    - <span data-ttu-id="db3a4-150">选择是否包括在 SharePoint 上找到的满足搜索条件的所有文档版本。</span><span class="sxs-lookup"><span data-stu-id="db3a4-150">Choose whether to include all versions of documents found on SharePoint that met the search criteria.</span></span> <span data-ttu-id="db3a4-151">這個選項只在搜尋內容來源包含網站時才會出現。</span><span class="sxs-lookup"><span data-stu-id="db3a4-151">This option appears only if the content sources for the search includes sites.</span></span>
    
    - <span data-ttu-id="db3a4-152">指定是否要在准备过程完成且数据准备好在高级电子数据展示中处理时向人员发送（或复制）通知消息。</span><span class="sxs-lookup"><span data-stu-id="db3a4-152">Specify whether you want a notification message sent (or copied) to a person when the preparation process is completed and the data is ready to be processed in Advanced eDiscovery.</span></span>
    
6. <span data-ttu-id="db3a4-153">按一下 [準備]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="db3a4-153">Click **Prepare**.</span></span>
    
    <span data-ttu-id="db3a4-154">搜索结果准备使用高级电子数据展示进行分析。</span><span class="sxs-lookup"><span data-stu-id="db3a4-154">The search results are prepared for analysis with Advanced eDiscovery.</span></span>
    
7. <span data-ttu-id="db3a4-155">在详细信息窗格中，**单击"检查准备状态"** 以显示有关准备过程的信息。</span><span class="sxs-lookup"><span data-stu-id="db3a4-155">In the details pane, click **Check preparation status** to display information about the preparation process.</span></span> <span data-ttu-id="db3a4-156">准备过程完成后，您可以转到高级电子数据展示中的案例来处理数据进行分析。</span><span class="sxs-lookup"><span data-stu-id="db3a4-156">When the preparation process is finished, you can go to the case in Advanced eDiscovery to process the data for analysis.</span></span> 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a><span data-ttu-id="db3a4-157">第 2 步：将搜索结果数据添加到高级电子数据展示中的案例</span><span class="sxs-lookup"><span data-stu-id="db3a4-157">Step 2: Add the search results data to the case in Advanced eDiscovery</span></span>
<span data-ttu-id="db3a4-158"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="db3a4-158"></span></span>

<span data-ttu-id="db3a4-159">准备完成后，下一步是转到高级电子数据展示，并将搜索结果数据（已上载到 Microsoft 云中的 Azure 存储区域）加载到高级电子数据展示中的情况。</span><span class="sxs-lookup"><span data-stu-id="db3a4-159">When the preparation is finished, the next step is to go to Advanced eDiscovery and load the search results data (which have been uploaded to an Azure storage area in the Microsoft cloud ) to the case in Advanced eDiscovery.</span></span> <span data-ttu-id="db3a4-160">如前所述，要访问高级电子数据展示，您必须是安全&合规中心中的电子数据展示管理员或高级电子数据展示中的管理员。</span><span class="sxs-lookup"><span data-stu-id="db3a4-160">As previously explained, to access Advanced eDiscovery you have to be an eDiscovery Administrator in the Security & Compliance Center or an administrator in Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="db3a4-161">安全&合规中心的数据可用于添加到高级电子数据展示中的案例所需的时间因电子数据展示搜索的结果大小而异。</span><span class="sxs-lookup"><span data-stu-id="db3a4-161">The time it takes for the data from the Security & Compliance Center to be available to add to a case in Advanced eDiscovery varies, depending on the size of the results from the eDiscovery search.</span></span> 
  
1. <span data-ttu-id="db3a4-162">在"安全&合规中心"中，**单击"电子数据**\>**展示"** 以显示组织中的案件列表。</span><span class="sxs-lookup"><span data-stu-id="db3a4-162">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="db3a4-163">单击要在高级电子数据展示中加载数据的情况**旁边的"打开"。**</span><span class="sxs-lookup"><span data-stu-id="db3a4-163">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="db3a4-164">在案例的 [首頁]\*\*\*\* 頁面上，按一下 [進階電子文件探索]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="db3a4-164">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![单击"切换到高级电子数据展示"以在高级电子数据展示中打开案例](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="db3a4-166">将显示"**连接到高级电子数据展示**进度栏"。</span><span class="sxs-lookup"><span data-stu-id="db3a4-166">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="db3a4-167">当您连接到高级电子数据展示时，案例的设置页上将显示一个容器列表。</span><span class="sxs-lookup"><span data-stu-id="db3a4-167">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![案例显示在高级电子数据展示中](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="db3a4-169">这些容器表示您在步骤 1 中的高级电子数据展示中为分析准备的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="db3a4-169">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="db3a4-170">请注意，容器的名称与"安全&合规性中心"中的搜索具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="db3a4-170">Note that the name of the container has the same name as the search in the case in the Security & Compliance Center.</span></span> <span data-ttu-id="db3a4-171">列表中的容器是您准备的容器。</span><span class="sxs-lookup"><span data-stu-id="db3a4-171">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="db3a4-172">如果其他用户为高级电子数据展示准备了搜索结果，则相应的容器将不会包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="db3a4-172">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
4. <span data-ttu-id="db3a4-173">要将搜索结果数据从 容器加载到高级电子数据展示中的案例中，请选择一个容器，然后单击"**处理"。**</span><span class="sxs-lookup"><span data-stu-id="db3a4-173">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="db3a4-174">後續步驟</span><span class="sxs-lookup"><span data-stu-id="db3a4-174">Next steps</span></span>

<span data-ttu-id="db3a4-175">将电子数据展示搜索结果添加到案例后，下一步是使用高级电子数据展示工具分析数据并标识响应特定法律案例的内容。</span><span class="sxs-lookup"><span data-stu-id="db3a4-175">After the results of an eDiscovery search are added to a case, the next step is to use the Advanced eDiscovery tools to analyze the data and identify the content that's responsive to a specific legal case.</span></span> <span data-ttu-id="db3a4-176">有关使用高级电子数据展示的信息，请参阅[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="db3a4-176">For information about using Advanced eDiscovery, see [Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="db3a4-177">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="db3a4-177">More information</span></span>

<span data-ttu-id="db3a4-178">当您准备在高级电子数据展示中进行分析时，搜索结果中包含的任何 RMS 加密电子邮件都将解密。</span><span class="sxs-lookup"><span data-stu-id="db3a4-178">Any RMS-encrypted email messages that are included in the search results will be decrypted when you prepare them for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="db3a4-179">默认情况下，电子数据展示管理器角色组的成员启用此解密功能。</span><span class="sxs-lookup"><span data-stu-id="db3a4-179">This decryption capability is enabled by default for members of the eDiscovery Manager role group.</span></span> <span data-ttu-id="db3a4-180">这是因为 RMS 解密管理角色分配给此角色组。</span><span class="sxs-lookup"><span data-stu-id="db3a4-180">This is because the RMS Decrypt management role is assigned to this role group.</span></span> <span data-ttu-id="db3a4-181">在解密电子邮件时，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="db3a4-181">Keep the following things in mind about decrypting email messages:</span></span>
  
- <span data-ttu-id="db3a4-182">目前，此解密功能不包括来自 SharePoint 和 OneDrive 的加密内容。</span><span class="sxs-lookup"><span data-stu-id="db3a4-182">Currently, this decryption capability doesn't include encrypted content from SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="db3a4-183">导出邮件时，只会解密 RMS 加密的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="db3a4-183">Only RMS-encrypted email messages will be decrypted when you export them.</span></span>
    
- <span data-ttu-id="db3a4-184">如果 RMS 加密的电子邮件具有附件（如文档或其他电子邮件）也已加密，则仅解密顶级电子邮件。</span><span class="sxs-lookup"><span data-stu-id="db3a4-184">If an RMS-encrypted email message has an attachment (such as a document or another email message) that's also encrypted, only the top-level email message will be decrypted.</span></span>
    
- <span data-ttu-id="db3a4-185">如果您需要防止某人在准备用于高级电子数据展示的分析的搜索结果时解密 RMS 加密的邮件，则必须创建自定义角色组（通过复制内置电子数据展示管理器角色组），然后删除 RMS从自定义角色组解密管理角色。</span><span class="sxs-lookup"><span data-stu-id="db3a4-185">If you need to prevent someone from decrypting RMS-encrypted messages when preparing search results for analysis in Advanced eDiscovery, you'll have to create a custom role group (by copying the built-in eDiscovery Manager role group) and then remove the RMS Decrypt management role from the custom role group.</span></span> <span data-ttu-id="db3a4-186">然后，将不想解密邮件的人员添加为自定义角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="db3a4-186">Then add the person who you don't want to decrypt messages as a member of the custom role group.</span></span>
