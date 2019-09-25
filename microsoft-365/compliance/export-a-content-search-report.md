---
title: 匯出內容搜尋報告
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: 您可以只导出搜索结果报告，而不是在 Office 365 的安全&合规性中心中导出内容搜索的实际结果。 该报告包含搜索结果的摘要和包含有关要导出的每个项的详细信息的文档。
ms.openlocfilehash: 8e33a7ba236e0890fc5985aa9a00cba904a40793
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077046"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="95af4-104">匯出內容搜尋報告</span><span class="sxs-lookup"><span data-stu-id="95af4-104">Export a Content Search report</span></span>

<span data-ttu-id="95af4-105">您可以只导出导出搜索结果时生成的相同报告，而不是从安全&合规性中心（以及与电子数据展示案例关联的内容搜索）中导出来自内容搜索的完整搜索结果集.</span><span class="sxs-lookup"><span data-stu-id="95af4-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="95af4-106">导出报表时，该报表将下载到与内容搜索同名的文件夹中，但该文件夹已附加*在 _Reports Only*中。</span><span class="sxs-lookup"><span data-stu-id="95af4-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  .</span></span> <span data-ttu-id="95af4-107">例如，如果内容搜索名为*ContosoCase0815，* 则报告将下载到名为*ContosoCase0815_报告仅*的文件夹。</span><span class="sxs-lookup"><span data-stu-id="95af4-107">For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  .</span></span> <span data-ttu-id="95af4-108">有关报表中包含的文档列表，请参阅[报表中包含的内容。](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="95af4-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="95af4-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="95af4-109">Before you begin</span></span>

- <span data-ttu-id="95af4-110">要导出内容搜索报告，您必须在安全&合规性中心中分配合规性搜索管理角色。</span><span class="sxs-lookup"><span data-stu-id="95af4-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="95af4-111">此角色分配给内置电子数据展示管理器和组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="95af4-111">This role is assigned to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="95af4-112">默认情况下，它不分配给组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="95af4-112">It isn't assigned by default to the Organization Management role group.</span></span> <span data-ttu-id="95af4-113">有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="95af4-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="95af4-114">导出报表时，数据在下载到本地计算机之前，会暂时存储在 Microsoft 云中的唯一 Windows Azure 存储区域中。</span><span class="sxs-lookup"><span data-stu-id="95af4-114">When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="95af4-115">确保您的组织可以连接到 Azure 中的终结点，该终结点是**\*.blob.core.windows.net（** 通配符表示导出的唯一标识符）。</span><span class="sxs-lookup"><span data-stu-id="95af4-115">Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="95af4-116">搜索结果数据在创建两周后从 Azure 存储区域中删除。</span><span class="sxs-lookup"><span data-stu-id="95af4-116">The search results data is deleted from the Azure storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="95af4-117">用于导出搜索结果的计算机必须满足以下系统要求：</span><span class="sxs-lookup"><span data-stu-id="95af4-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="95af4-118">32 位或 64 位版本的 Windows 7 和更高版本</span><span class="sxs-lookup"><span data-stu-id="95af4-118">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="95af4-119">微软 .NET 框架 4.7</span><span class="sxs-lookup"><span data-stu-id="95af4-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="95af4-120">支援的瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="95af4-120">A supported browser:</span></span>
    
    - <span data-ttu-id="95af4-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="95af4-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="95af4-122">或</span><span class="sxs-lookup"><span data-stu-id="95af4-122">or</span></span>
    
    - <span data-ttu-id="95af4-123">微软互联网浏览器10及更高版本</span><span class="sxs-lookup"><span data-stu-id="95af4-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="95af4-124">**注意：** Microsoft 不会为 ClickOnce 应用程序制造第三方扩展程序或加载项。</span><span class="sxs-lookup"><span data-stu-id="95af4-124">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="95af4-125">不支持使用不支持的浏览器导出搜索结果以及第三方扩展或加载项。</span><span class="sxs-lookup"><span data-stu-id="95af4-125">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 

- <span data-ttu-id="95af4-126">如果内容搜索返回的结果的估计总大小超过 20&nbsp;TB，则导出报表将失败。</span><span class="sxs-lookup"><span data-stu-id="95af4-126">If the estimated total size of the results returned by a Content Search exceeds 20&nbsp;TB, exporting the report will fail.</span></span> <span data-ttu-id="95af4-127">要成功导出报表，请尝试缩小范围并重新运行搜索，以便结果的估计大小小于 20&nbsp;TB。</span><span class="sxs-lookup"><span data-stu-id="95af4-127">To successfully export the report, try to narrow the scope and re-run the search so the estimated size of the results is less than 20&nbsp;TB.</span></span>

- <span data-ttu-id="95af4-128">导出内容搜索报告将计算同时运行的最大导出数和单个用户可以运行的最大导出数。</span><span class="sxs-lookup"><span data-stu-id="95af4-128">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="95af4-129">有关导出限制的详细信息，请参阅[导出内容搜索结果](export-search-results.md#export-limits)。</span><span class="sxs-lookup"><span data-stu-id="95af4-129">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="95af4-130">生成和下载内容搜索报告</span><span class="sxs-lookup"><span data-stu-id="95af4-130">Generate and download a Content Search report</span></span>

<span data-ttu-id="95af4-131">生成和下载内容搜索报告的步骤与实际导出搜索结果非常相似。</span><span class="sxs-lookup"><span data-stu-id="95af4-131">The steps to generate and download a Content Search report are very similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="95af4-132">步骤 1：生成导出报告</span><span class="sxs-lookup"><span data-stu-id="95af4-132">Step 1: Generate the report for export</span></span>

<span data-ttu-id="95af4-133">第一步是准备报告以下载到您的计算机导出。</span><span class="sxs-lookup"><span data-stu-id="95af4-133">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="95af4-134">报表时，报表文档将上载到 Microsoft 云中的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="95af4-134">When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="95af4-135">移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="95af4-135">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="95af4-136">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="95af4-136">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="95af4-137">在"安全&合规性中心"的左侧窗格中，\*\*\*\*\>单击"**搜索内容搜索"。**</span><span class="sxs-lookup"><span data-stu-id="95af4-137">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="95af4-138">在"**内容"搜索**页上，选择搜索。</span><span class="sxs-lookup"><span data-stu-id="95af4-138">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="95af4-139">在详细信息窗格中，**在"将报表导出到计算机"** 下，单击"**生成报表"。**</span><span class="sxs-lookup"><span data-stu-id="95af4-139">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="95af4-140">如果搜索结果超过 7 天，系统将提示您更新搜索结果。</span><span class="sxs-lookup"><span data-stu-id="95af4-140">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="95af4-141">如果发生这种情况，请取消导出，单击所选搜索的详细信息窗格**中的"更新搜索结果"，** 然后在更新结果后再次启动报表导出。</span><span class="sxs-lookup"><span data-stu-id="95af4-141">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="95af4-142">在"**导出报表"** 页上，在"**从搜索中包括这些项目"** 下，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="95af4-142">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="95af4-143">仅导出索引项</span><span class="sxs-lookup"><span data-stu-id="95af4-143">Export only indexed items</span></span>
    
    - <span data-ttu-id="95af4-144">导出索引和未编制索引的项目</span><span class="sxs-lookup"><span data-stu-id="95af4-144">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="95af4-145">仅导出未编制索引的项目</span><span class="sxs-lookup"><span data-stu-id="95af4-145">Export only unindexed items</span></span>
    
    <span data-ttu-id="95af4-146">有关未编制索引的项目的详细信息，请参阅[内容搜索 中部分索引的项目。](partially-indexed-items-in-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="95af4-146">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="95af4-147">选择包括所有版本的 SharePoint 文档的搜索统计信息。</span><span class="sxs-lookup"><span data-stu-id="95af4-147">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="95af4-148">仅当搜索的内容源包括"共享点"或"企业网站的 OneDrive"时，才会显示此选项。</span><span class="sxs-lookup"><span data-stu-id="95af4-148">This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="95af4-149">**单击"生成报告"。**</span><span class="sxs-lookup"><span data-stu-id="95af4-149">Click **Generate report**.</span></span>
    
    <span data-ttu-id="95af4-150">搜索结果报告已准备下载，这意味着报告文档将上载到 Microsoft 云中的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="95af4-150">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud.</span></span> <span data-ttu-id="95af4-151">当报表准备好可供下载时，在详细信息窗格中的"**将报表导出到计算机"** 下**将显示"下载报表"** 链接。</span><span class="sxs-lookup"><span data-stu-id="95af4-151">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="95af4-152">您还可以导出与电子数据展示案例关联的内容搜索的报告。</span><span class="sxs-lookup"><span data-stu-id="95af4-152">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="95af4-153">为此，请转到![](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)**电子数据展示，**\>\*\*\*\* 选择一个案例，**然后单击"编辑**编辑"图标 。</span><span class="sxs-lookup"><span data-stu-id="95af4-153">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="95af4-154">在"**搜索"** 页上，选择搜索，**然后单击"导出**![导出"搜索结果](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)\>**图标"导出报告"。**</span><span class="sxs-lookup"><span data-stu-id="95af4-154">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="95af4-155">第 2 步：下载报告</span><span class="sxs-lookup"><span data-stu-id="95af4-155">Step 2: Download the report</span></span>

<span data-ttu-id="95af4-156">下一步是将报告从 Azure 存储区域下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="95af4-156">The next step is to download the report from the Azure storage area to your local computer.</span></span>
  
1. <span data-ttu-id="95af4-157">在生成报表的搜索详细信息窗格中，**在"将报表导出到计算机"** 下，**单击"下载报表"。**</span><span class="sxs-lookup"><span data-stu-id="95af4-157">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="95af4-158">**将显示"下载报告"** 页，其中包含有关报表的以下信息，直到下载到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="95af4-158">The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="95af4-159">要下载的项目数。</span><span class="sxs-lookup"><span data-stu-id="95af4-159">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="95af4-160">将下载的项目的估计总大小。</span><span class="sxs-lookup"><span data-stu-id="95af4-160">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="95af4-161">将导出索引还是未索引。</span><span class="sxs-lookup"><span data-stu-id="95af4-161">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="95af4-162">未编制索引的项目是具有可识别格式、已加密或由于其他原因未编制索引的项目。</span><span class="sxs-lookup"><span data-stu-id="95af4-162">Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="95af4-163">是否下载 SharePoint 文档的版本。</span><span class="sxs-lookup"><span data-stu-id="95af4-163">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="95af4-164">报表导出过程的状态。</span><span class="sxs-lookup"><span data-stu-id="95af4-164">The status of the report export process.</span></span> <span data-ttu-id="95af4-165">即使报表的编写未完成，您也可以开始下载报表。</span><span class="sxs-lookup"><span data-stu-id="95af4-165">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="95af4-166">**在"导出键"** 下，**单击"复制到剪贴板"。**</span><span class="sxs-lookup"><span data-stu-id="95af4-166">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="95af4-167">您将在步骤 5 中使用此密钥下载报告。</span><span class="sxs-lookup"><span data-stu-id="95af4-167">You will use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95af4-168">由于任何人都可以安装和启动电子数据展示导出工具，然后使用此密钥下载搜索报告，因此请务必采取预防措施来保护此密钥，就像保护密码或其他安全相关信息一样。</span><span class="sxs-lookup"><span data-stu-id="95af4-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="95af4-169">**单击"下载报告"。**</span><span class="sxs-lookup"><span data-stu-id="95af4-169">Click **Download report**.</span></span>
    
4. <span data-ttu-id="95af4-170">如果系统提示您安装**MicrosoftOffice 365 电子数据展示导出工具，** 请单击"**安装"。**</span><span class="sxs-lookup"><span data-stu-id="95af4-170">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="95af4-171">在**电子数据展示导出工具**中，将步骤 2 中复制的导出密钥粘贴到相应的框中。</span><span class="sxs-lookup"><span data-stu-id="95af4-171">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="95af4-172">**单击"浏览"** 以指定要下载报表的位置。</span><span class="sxs-lookup"><span data-stu-id="95af4-172">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="95af4-173">按一下 [開始]\*\*\*\* 將搜尋結果下載至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="95af4-173">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="95af4-174">**电子数据展示导出工具**显示有关导出过程的状态信息，包括要下载的剩余项目的数量（和大小）的估计值。</span><span class="sxs-lookup"><span data-stu-id="95af4-174">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="95af4-175">导出过程完成后，可以访问这些文件下载位置中的文件。</span><span class="sxs-lookup"><span data-stu-id="95af4-175">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="95af4-176">您可以下载与电子数据展示案例关联的内容搜索的报告。</span><span class="sxs-lookup"><span data-stu-id="95af4-176">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="95af4-177">为此，请转到![](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)**电子数据展示，**\>\*\*\*\* 选择一个案例，**然后单击"编辑**编辑"图标 。</span><span class="sxs-lookup"><span data-stu-id="95af4-177">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="95af4-178">在"**导出"** 页上，选择报表导出，然后在详细信息窗格中单击"**下载报表"。**</span><span class="sxs-lookup"><span data-stu-id="95af4-178">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="95af4-179">报告中包含的内容</span><span class="sxs-lookup"><span data-stu-id="95af4-179">What's included in the report</span></span>

<span data-ttu-id="95af4-180">生成和导出有关内容搜索结果的报告时，将下载以下文档：</span><span class="sxs-lookup"><span data-stu-id="95af4-180">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="95af4-181">**导出摘要**- 包含导出摘要的 Excel 文档。</span><span class="sxs-lookup"><span data-stu-id="95af4-181">**Export Summary** - An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="95af4-182">这包括搜索的内容源数、每个内容位置的搜索结果数、估计的项目数、要导出的项目的实际数量以及项目的估计和实际大小等信息将导出。</span><span class="sxs-lookup"><span data-stu-id="95af4-182">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="95af4-183">如果在导出报表时包含未编制索引的项目，则未编制索引的项目数将包含在估计搜索结果的总数中，以及"如果要导出搜索结果"中列出的已下载搜索结果的总数中。导出摘要报告。</span><span class="sxs-lookup"><span data-stu-id="95af4-183">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="95af4-184">换句话说，要下载的项目总数等于估计结果的总数和未编制索引的项目的总数。</span><span class="sxs-lookup"><span data-stu-id="95af4-184">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="95af4-185">**清单**- 一个清单文件（以 XML 格式），其中包含有关搜索结果中包含的每个项的信息。</span><span class="sxs-lookup"><span data-stu-id="95af4-185">**Manifest** - A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="95af4-186">**结果**- Excel 文档，其中包含包含有关将随搜索结果一起导出的每个索引项的信息的行。</span><span class="sxs-lookup"><span data-stu-id="95af4-186">**Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="95af4-187">对于电子邮件，结果日志包含有关每条消息的信息，包括：</span><span class="sxs-lookup"><span data-stu-id="95af4-187">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="95af4-188">邮件在源邮箱中的位置（包括邮件是在主邮箱还是存档邮箱中）。</span><span class="sxs-lookup"><span data-stu-id="95af4-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="95af4-189">邮件的发送或接收日期。</span><span class="sxs-lookup"><span data-stu-id="95af4-189">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="95af4-190">邮件中的"主题"行。</span><span class="sxs-lookup"><span data-stu-id="95af4-190">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="95af4-191">邮件的发件人和收件人。</span><span class="sxs-lookup"><span data-stu-id="95af4-191">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="95af4-192">对于来自 SharePoint 和 OneDrive 业务网站的文档，结果日志包含有关每个文档的信息，包括：</span><span class="sxs-lookup"><span data-stu-id="95af4-192">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="95af4-193">文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="95af4-193">The URL for the document.</span></span>
    
  - <span data-ttu-id="95af4-194">文档所在的网站集的 URL。</span><span class="sxs-lookup"><span data-stu-id="95af4-194">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="95af4-195">文档上次修改的日期。</span><span class="sxs-lookup"><span data-stu-id="95af4-195">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="95af4-196">文档的名称（位于结果日志的"主题"列中）。</span><span class="sxs-lookup"><span data-stu-id="95af4-196">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="95af4-197">**"结果"** 报表中的行数应等于将下载的搜索结果总数减去**未编制索引的项目**报表中列出的项目总数。</span><span class="sxs-lookup"><span data-stu-id="95af4-197">The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="95af4-198">**未编制索引的项目**- 包含搜索结果中将包括的任何未编制索引项的信息的 Excel 文档。</span><span class="sxs-lookup"><span data-stu-id="95af4-198">**Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results.</span></span> <span data-ttu-id="95af4-199">如果在生成搜索结果报告时未包含未编制索引的项目，则此报告仍将下载，但将为空。</span><span class="sxs-lookup"><span data-stu-id="95af4-199">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
