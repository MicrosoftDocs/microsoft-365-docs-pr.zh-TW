---
title: 在高級 eDiscovery 中測試相關性分析
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何使用 [測試] 索引標籤，在 [高級 eDiscovery] 中成批計算後，測試、比較和驗證整體的處理品質。
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769168"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="0760e-103">在高級 eDiscovery 中測試相關性分析</span><span class="sxs-lookup"><span data-stu-id="0760e-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="0760e-104">Advanced eDiscovery 中的 [測試] 索引標籤可讓您測試、比較及驗證整體的處理品質。</span><span class="sxs-lookup"><span data-stu-id="0760e-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="0760e-105">這些測試會在批次計算之後執行。</span><span class="sxs-lookup"><span data-stu-id="0760e-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="0760e-106">將檔案標記在集合中，一位專家就知道每個標籤檔案是否與案例相關作出最後的判斷。</span><span class="sxs-lookup"><span data-stu-id="0760e-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="0760e-107">在單一和多個問題案例中，測試一般會在每個問題中執行。</span><span class="sxs-lookup"><span data-stu-id="0760e-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="0760e-108">您可以在每次測試後查看結果，並使用指定的範例測試檔來改編測試結果。</span><span class="sxs-lookup"><span data-stu-id="0760e-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="0760e-109">測試其他</span><span class="sxs-lookup"><span data-stu-id="0760e-109">Testing the rest</span></span>

<span data-ttu-id="0760e-110">「測試 Rest」測試是用來驗證剔除決策，例如，根據最終的高級 eDiscovery 結果，只複查高於特定相關性截止分數的檔案。</span><span class="sxs-lookup"><span data-stu-id="0760e-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="0760e-111">專家會檢查所選截止分數底下的檔案範例，以評估該集合內相關檔案的數量。</span><span class="sxs-lookup"><span data-stu-id="0760e-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="0760e-112">這種測試會提供統計資料，以及複查集與測試 Rest 人口之間的比較。</span><span class="sxs-lookup"><span data-stu-id="0760e-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="0760e-113">考核集的結果是在訓練期間依相關性計算的結果。</span><span class="sxs-lookup"><span data-stu-id="0760e-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="0760e-114">結果包含以設定和輸入參數為基礎的計算，例如：</span><span class="sxs-lookup"><span data-stu-id="0760e-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="0760e-115">測試範例中檔案數目及識別相關檔案的範例統計資料。</span><span class="sxs-lookup"><span data-stu-id="0760e-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="0760e-116">檢查集合的人口參數和其餘部分的表格比較，例如檔案數目、相關檔案的預估數目、預估豐富程度，以及尋找其他相關檔案的平均成本。</span><span class="sxs-lookup"><span data-stu-id="0760e-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="0760e-117">成本參數設定可由系統管理員設定。</span><span class="sxs-lookup"><span data-stu-id="0760e-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="0760e-118">若要執行「測試 Rest」測試：</span><span class="sxs-lookup"><span data-stu-id="0760e-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="0760e-119">開啟 [ **相關性 \> 測試** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0760e-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="0760e-120">在 [ **測試** ] 索引標籤中，按一下 [ **新增測試**]。</span><span class="sxs-lookup"><span data-stu-id="0760e-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="0760e-121">隨即會顯示 [ **建立測試** ] 對話方塊，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="0760e-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![相關性測試的其他結果](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="0760e-123">在 [ **測試名稱**] 和 [ **描述**] 中，輸入名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="0760e-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="0760e-124">在 [**測試類型**] 清單中，選取 **[測試其餘** 專案]</span><span class="sxs-lookup"><span data-stu-id="0760e-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="0760e-125">在 [ **問題/類別** ] 清單中，選取問題名稱。</span><span class="sxs-lookup"><span data-stu-id="0760e-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="0760e-126">在 [ **載入** ] 清單中，選取負載。</span><span class="sxs-lookup"><span data-stu-id="0760e-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="0760e-127">在 [ **讀取%**] 中，接受預設值，或選取截止的相關性分數值。</span><span class="sxs-lookup"><span data-stu-id="0760e-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="0760e-128">在 [ **設定大小**] 或 [接受預設值]。</span><span class="sxs-lookup"><span data-stu-id="0760e-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="0760e-129">還原圖示會還原預設值。</span><span class="sxs-lookup"><span data-stu-id="0760e-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="0760e-130">按一下 [ **開始標記**]。</span><span class="sxs-lookup"><span data-stu-id="0760e-130">Click **Start tagging**.</span></span> <span data-ttu-id="0760e-131">會產生測試範例。</span><span class="sxs-lookup"><span data-stu-id="0760e-131">A test sample is generated.</span></span>

10. <span data-ttu-id="0760e-132">檢查及標記 [相關性標籤] 索引 **卷 \>** 標中的每個檔案，完成後，按一下 [ **計算**]。</span><span class="sxs-lookup"><span data-stu-id="0760e-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="0760e-133">在 [測試] 索引標籤中，您可以按一下 [ **查看結果** ] 以查看測試結果。</span><span class="sxs-lookup"><span data-stu-id="0760e-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="0760e-134">下列螢幕擷取畫面所示的範例。</span><span class="sxs-lookup"><span data-stu-id="0760e-134">An example is shown in the following screenshot.</span></span>

    ![測試其他結果](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="0760e-136">在先前的螢幕擷取畫面中，表格的 **範例參數** 區段包含專家標示之範例中檔案數目的詳細資料，以及該範例中找到的相關檔案數目。</span><span class="sxs-lookup"><span data-stu-id="0760e-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="0760e-137">表格的「 **人口參數** 」區段包含測試結果，包括檔的審閱集人口，其分數低於選取的截止點，以及 "Rest" 檔的檔與選取的截止點之上的分數。</span><span class="sxs-lookup"><span data-stu-id="0760e-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="0760e-138">針對每個人口，會顯示下列結果：</span><span class="sxs-lookup"><span data-stu-id="0760e-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="0760e-139">包含已讀取的%-規定截止點</span><span class="sxs-lookup"><span data-stu-id="0760e-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="0760e-140">檔總數</span><span class="sxs-lookup"><span data-stu-id="0760e-140">The total number of files</span></span>

- <span data-ttu-id="0760e-141">相關檔案的預估數目</span><span class="sxs-lookup"><span data-stu-id="0760e-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="0760e-142">預估豐富</span><span class="sxs-lookup"><span data-stu-id="0760e-142">The estimated richness</span></span>

- <span data-ttu-id="0760e-143">尋找另一個相關檔案的平均檢查成本</span><span class="sxs-lookup"><span data-stu-id="0760e-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="0760e-144">測試切片</span><span class="sxs-lookup"><span data-stu-id="0760e-144">Testing the slice</span></span>

<span data-ttu-id="0760e-145">「測試分割區」測試會執行類似于「測試 Rest」測試的測試，但是對檔集（依相關性讀取% 所指定）進行測試。</span><span class="sxs-lookup"><span data-stu-id="0760e-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="0760e-146">若要執行「測試磁區」測試：</span><span class="sxs-lookup"><span data-stu-id="0760e-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="0760e-147">開啟 [ **相關性 \> 測試** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0760e-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="0760e-148">在 [ **測試** ] 索引標籤中，按一下 [ **新增測試**]。</span><span class="sxs-lookup"><span data-stu-id="0760e-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="0760e-149">隨即會顯示 [ **建立測試** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="0760e-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="0760e-150">在 [ **測試名稱** 和 **描述**] 中，輸入資訊。</span><span class="sxs-lookup"><span data-stu-id="0760e-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="0760e-151">在 [ **測試類型** ] 清單中，選取 **[測試切片**]。</span><span class="sxs-lookup"><span data-stu-id="0760e-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="0760e-152">在 [ **問題** ] 清單中，選取問題名稱。</span><span class="sxs-lookup"><span data-stu-id="0760e-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="0760e-153">在 [ **載入** ] 清單中，選取負載。</span><span class="sxs-lookup"><span data-stu-id="0760e-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="0760e-154">在 [ **介於**] 中，接受預設的 [低] 和 [高] 範圍值，或選取 [截止相關性分數] 的值。</span><span class="sxs-lookup"><span data-stu-id="0760e-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="0760e-155">在 [ **設定大小**] 中，選取值或接受預設值。</span><span class="sxs-lookup"><span data-stu-id="0760e-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="0760e-156">還原圖示會還原預設值。</span><span class="sxs-lookup"><span data-stu-id="0760e-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="0760e-157">按一下 [ **開始標記**]。</span><span class="sxs-lookup"><span data-stu-id="0760e-157">Click **Start tagging**.</span></span> <span data-ttu-id="0760e-158">會產生測試範例。</span><span class="sxs-lookup"><span data-stu-id="0760e-158">A test sample is generated.</span></span>

10. <span data-ttu-id="0760e-159">檢查及標記 [相關性標籤] 索引 **卷 \>** 標中的每個檔案，完成後，按一下 [ **計算**]。</span><span class="sxs-lookup"><span data-stu-id="0760e-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="0760e-160">在 [測試] 索引標籤中，您可以按一下 [ **查看結果** ] 以查看測試結果。</span><span class="sxs-lookup"><span data-stu-id="0760e-160">In the Test tab, you can click **View results** to see the test results.</span></span>
