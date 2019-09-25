---
title: 在 Office 365 高级电子数据展示中测试相关性分析
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: '了解如何在 Office 365 高级电子数据展示中的批处理计算后使用"测试"选项卡来测试、比较和验证处理的总体质量。  '
ms.openlocfilehash: 7d150b9f68cdcd3246fbd4d8f79e0972a81a4703
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077478"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="6ba3d-103">在 Office 365 高级电子数据展示中测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="6ba3d-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="6ba3d-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="6ba3d-106">通过高级电子数据展示中的"测试"选项卡，您可以测试、比较和验证处理的总体质量。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-106">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="6ba3d-107">这些测试在批处理计算后执行。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-107">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="6ba3d-108">通过标记集合中的文件，专家可以最终确定每个标记的文件是否与案例实际相关。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-108">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="6ba3d-109">在单问题和多问题方案中，测试通常按问题执行。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-109">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="6ba3d-110">每个测试后都可以查看结果，并且测试结果可以使用指定的测试文件返工。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-110">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="6ba3d-111">测试其余的</span><span class="sxs-lookup"><span data-stu-id="6ba3d-111">Testing the rest</span></span>

<span data-ttu-id="6ba3d-112">"测试其余"测试用于验证剔除决策，例如，仅根据最终高级电子数据展示结果查看特定相关性截止分数以上的文件。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-112">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="6ba3d-113">专家在选定的截止分数下查看文件样本，以评估该集中的相关文件数。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-113">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="6ba3d-114">此测试提供"审阅"集和"测试休息"总体之间的统计信息和比较。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-114">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="6ba3d-115">审核集的结果按培训期间的相关性计算。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-115">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="6ba3d-116">结果包括基于设置和输入参数的计算，例如：</span><span class="sxs-lookup"><span data-stu-id="6ba3d-116">The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="6ba3d-117">测试样本中文件数的样本统计信息，并确定相关文件。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="6ba3d-118">"审阅"集和其余项的"填充"参数的表格比较，例如，文件数、相关文件的估计数量、估计的丰富度以及查找其他相关文件的平均成本。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-118">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file.</span></span> <span data-ttu-id="6ba3d-119">费用参数设置可以由管理员设置。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-119">Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="6ba3d-120">打开**相关性\>测试**选项卡。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="6ba3d-121">在"**测试"** 选项卡中，**单击"新建测试"。**</span><span class="sxs-lookup"><span data-stu-id="6ba3d-121">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="6ba3d-122">**将显示"创建测试"** 对话框，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-122">The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![相關性測試的其他結果](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="6ba3d-124">**在"测试名称"** 和"**描述"** 中键入名称和说明。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="6ba3d-125">在"**测试类型"** 列表中，**选择"测试其余"**</span><span class="sxs-lookup"><span data-stu-id="6ba3d-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="6ba3d-126">在"**问题/类别"** 列表中，选择问题名称。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="6ba3d-127">在"**加载"** 列表中，选择负载。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="6ba3d-128">**在"读取 %"** 中，接受默认值或为截止相关性分数选择一个值。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="6ba3d-129">**以"设置大小"** 或接受默认值。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-129">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="6ba3d-130">请注意，还原图标将还原默认值。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-130">Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="6ba3d-131">**单击"开始标记"。**</span><span class="sxs-lookup"><span data-stu-id="6ba3d-131">Click **Start tagging**.</span></span> <span data-ttu-id="6ba3d-132">生成测试样本。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-132">A test sample is generated.</span></span>
    
10. <span data-ttu-id="6ba3d-133">查看并标记"**相关性\>标记"** 选项卡中的每个文件，完成后，单击"**计算"。**</span><span class="sxs-lookup"><span data-stu-id="6ba3d-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="6ba3d-134">在"测试"选项卡中，可以**单击"查看结果"** 以查看测试结果。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-134">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="6ba3d-135">下图显示了一个示例。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-135">An example is shown in the following figure.</span></span> 
    
    ![測試其他結果](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="6ba3d-137">在上图中，表**的"示例参数"** 部分包含有关专家标记的示例中的文件数以及该示例中的相关文件数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="6ba3d-138">表**的"填充参数"** 部分包含测试结果，包括分数低于所选截止分数的"审阅"文件组和分数高于所选截止分数的"其余"文件填充。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-138">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="6ba3d-139">对于每个总体，将显示以下结果：</span><span class="sxs-lookup"><span data-stu-id="6ba3d-139">For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="6ba3d-140">包括具有读取百分比的文件 - 声明截止</span><span class="sxs-lookup"><span data-stu-id="6ba3d-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="6ba3d-141">文件总数</span><span class="sxs-lookup"><span data-stu-id="6ba3d-141">The total number of files</span></span> 
    
- <span data-ttu-id="6ba3d-142">相关文件的估计数量</span><span class="sxs-lookup"><span data-stu-id="6ba3d-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="6ba3d-143">估计的丰富性</span><span class="sxs-lookup"><span data-stu-id="6ba3d-143">The estimated richness</span></span> 
    
- <span data-ttu-id="6ba3d-144">查找另一个相关文件的平均审阅成本</span><span class="sxs-lookup"><span data-stu-id="6ba3d-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="6ba3d-145">测试切片</span><span class="sxs-lookup"><span data-stu-id="6ba3d-145">Testing the slice</span></span>

<span data-ttu-id="6ba3d-146">"测试切片"测试执行类似于"测试休息"测试的测试，但执行相关性读取百分之指定的文件集的段。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="6ba3d-147">打开**相关性\>测试**选项卡。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="6ba3d-148">在"**测试"** 选项卡中，**单击"新建测试"。**</span><span class="sxs-lookup"><span data-stu-id="6ba3d-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="6ba3d-149">**将显示"创建测试"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-149">The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="6ba3d-150">**在"测试名称"\*\*\*\*和"说明"** 中键入信息。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="6ba3d-151">在"**测试类型"** 列表中，**选择"测试切片"。**</span><span class="sxs-lookup"><span data-stu-id="6ba3d-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="6ba3d-152">在"**问题"** 列表中，选择问题名称。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="6ba3d-153">在"**加载"** 列表中，选择负载。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="6ba3d-154">**在"读取 % "中，** 接受默认的低范围值和高范围值，或选择截止相关性分数的值。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="6ba3d-155">**在"设置大小"** 中，选择一个值或接受默认值。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="6ba3d-156">还原图标将还原默认值。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="6ba3d-157">**单击"开始标记"。**</span><span class="sxs-lookup"><span data-stu-id="6ba3d-157">Click **Start tagging**.</span></span> <span data-ttu-id="6ba3d-158">生成测试样本。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-158">A test sample is generated.</span></span>
    
10. <span data-ttu-id="6ba3d-159">查看并标记"**相关性\>标记"** 选项卡中的每个文件，完成后，单击"**计算"。**</span><span class="sxs-lookup"><span data-stu-id="6ba3d-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="6ba3d-160">在"测试"选项卡中，可以**单击"查看结果"** 以查看测试结果。</span><span class="sxs-lookup"><span data-stu-id="6ba3d-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="6ba3d-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6ba3d-161">See also</span></span>

[<span data-ttu-id="6ba3d-162">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="6ba3d-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="6ba3d-163">理解相关性评估</span><span class="sxs-lookup"><span data-stu-id="6ba3d-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6ba3d-164">标记和评估</span><span class="sxs-lookup"><span data-stu-id="6ba3d-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6ba3d-165">标记和相关性培训</span><span class="sxs-lookup"><span data-stu-id="6ba3d-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6ba3d-166">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="6ba3d-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6ba3d-167">根据结果决定</span><span class="sxs-lookup"><span data-stu-id="6ba3d-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

