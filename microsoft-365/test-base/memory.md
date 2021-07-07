---
title: 記憶體迴歸分析
description: 如何推斷記憶體回歸
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: cd95c4e0eb04b05860ded256066913cf87d67e86
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322596"
---
# <a name="memory-regression-analysis"></a><span data-ttu-id="06f03-103">記憶體迴歸分析</span><span class="sxs-lookup"><span data-stu-id="06f03-103">Memory Regression Analysis</span></span>

<span data-ttu-id="06f03-104">測試基礎可協助您更清楚地發現執行應用程式之測試 Vm 中的嚴重記憶體使用量增加。</span><span class="sxs-lookup"><span data-stu-id="06f03-104">Test Base helps you more clearly notice significant memory usage increases in the test VMs running your apps.</span></span> <span data-ttu-id="06f03-105">效能度量（如記憶體使用量）可以表示整體應用程式健康情況，我們相信這項新增會極大地協助讓您的應用程式以最佳效能執行。</span><span class="sxs-lookup"><span data-stu-id="06f03-105">Performance metrics, such as memory usage, can be indicative of overall application health and we believe this addition will greatly help keep your apps performing optimally.</span></span>

<span data-ttu-id="06f03-106">請繼續閱讀以取得更多詳細資料或觀看這段影片，快速流覽最新的增強功能。</span><span class="sxs-lookup"><span data-stu-id="06f03-106">Read on for more details or watch this video for a quick walk through of the latest improvements.</span></span> 

<span data-ttu-id="06f03-107">如需 M365's 的測試基礎，以協助迴歸分析的詳細資訊，請參閱根據進程可靠性的回歸結果。</span><span class="sxs-lookup"><span data-stu-id="06f03-107">For more information on Test Base for M365's ability to help with regression analysis, see Regression results based on process reliability.</span></span>

<span data-ttu-id="06f03-108"><b>深入查看記憶體回歸</b></span><span class="sxs-lookup"><span data-stu-id="06f03-108"><b>Looking closer at memory regressions</b></span></span>

<span data-ttu-id="06f03-109">M365 儀表板的測試基底會顯示應用程式在新的預先發行的 Windows 更新上使用的記憶體，並與上次發行 Windows 更新所使用的記憶體進行比較。</span><span class="sxs-lookup"><span data-stu-id="06f03-109">The Test Base for M365 dashboard shows the memory consumed by your application on a new pre-released Windows update and compares it with the memory used by the last released Windows update.</span></span> 

<span data-ttu-id="06f03-110">使用此月份的增強功能時，記憶體迴歸分析現在會集中在您的 favorited 處理常式中。</span><span class="sxs-lookup"><span data-stu-id="06f03-110">With this month’s enhancements, memory regression analysis is now featured in your favorited processes.</span></span> <span data-ttu-id="06f03-111">應用程式可以包含多個進程，您可以透過 [可靠性] 索引標籤手動選取您最喜歡的處理常式。我們的服務會在這些 favorited 處理常式中識別記憶體回歸，同時將測試執行與不同的 Windows 更新版本進行比較。</span><span class="sxs-lookup"><span data-stu-id="06f03-111">Applications can contain multiple processes and you can manually select your favorite processes through the Reliability tab. Our service will then identify memory regressions in these favorited processes while comparing test runs across different Windows update releases.</span></span> <span data-ttu-id="06f03-112">如果偵測到回歸，便可輕鬆使用回歸的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="06f03-112">If a regression is detected, details about the regression are easily available.</span></span>

<span data-ttu-id="06f03-113">現在，讓我們詳細瞭解這項功能，並討論如何使用 Windows 效能分析器來疑難排解記憶體回歸。</span><span class="sxs-lookup"><span data-stu-id="06f03-113">Now let's look at this feature in detail and discuss how you can troubleshoot memory regressions using Windows Performance Analyzer.</span></span>

<span data-ttu-id="06f03-114">記憶體回歸所引發的失敗信號會顯示在 [記憶體使用量] 底下的 [測試結果] 頁面的 [M365] 儀表板的 [測試基底] 中。</span><span class="sxs-lookup"><span data-stu-id="06f03-114">The failure signal caused by a memory regression is shown in the Test Base for M365 dashboard on the Test results page under Memory Utilization:</span></span>

![記憶體使用量結果](Media/01_memory-utilization-results.png)


<span data-ttu-id="06f03-116">因記憶體使用量較高導致應用程式失敗，也會顯示 ```Fail``` 在 [測試摘要] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="06f03-116">Failure for the application due to higher memory consumption, will also be displayed as ```Fail``` on the Test Summary page:</span></span>

![測試摘要結果](Media/02_test-summary.png)

<span data-ttu-id="06f03-118">透過提供這些失敗信號，我們的目標是明確標示可能會中斷和影響應用程式使用者體驗的潛在問題。</span><span class="sxs-lookup"><span data-stu-id="06f03-118">By providing these failure signals upfront, our goal is to clearly flag potential issues that can disrupt and impact the end user experience for your application.</span></span> 

<span data-ttu-id="06f03-119">然後，您可以下載記錄檔，並使用 Windows 效能分析器（或您慣用的工具箱）進行進一步調查。</span><span class="sxs-lookup"><span data-stu-id="06f03-119">You can then download the log files and use the Windows Performance Analyzer, or your preferred toolkit, to investigate further.</span></span> <span data-ttu-id="06f03-120">您也可以與 M365 小組的測試基底合作，以修正問題，並協助避免影響使用者的問題。</span><span class="sxs-lookup"><span data-stu-id="06f03-120">You can also work jointly with the Test Base for M365 team on remediating the issue and help prevent issues impacting end users.</span></span>

<span data-ttu-id="06f03-121">在 M365 service 之測試基底的 [記憶體使用量] 索引標籤中，會捕獲所有測試執行的記憶體信號。</span><span class="sxs-lookup"><span data-stu-id="06f03-121">Memory signals are captured in the Memory Utilization tab in the Test Base for M365 service for all test runs.</span></span> <span data-ttu-id="06f03-122">下列範例顯示的是最近的測試執行，針對《發行前8月2020安全性更新」的架應用程式「冒煙測試記憶體壓力」。</span><span class="sxs-lookup"><span data-stu-id="06f03-122">The example below shows a recent test run with the onboarded application “Smoke Test Memory Stress” against the pre-release August 2020 security update.</span></span> <span data-ttu-id="06f03-123"> (這個應用程式是由小組編寫，用以說明記憶體回歸。 ) </span><span class="sxs-lookup"><span data-stu-id="06f03-123">(This application was written by our team to illustrate memory regressions.)</span></span>

![記憶體迴歸分析結果](Media/03_memory-regression%20comparison.png)

<span data-ttu-id="06f03-125">在此範例中，最愛使用的處理常式 "USLTestMemoryStress.exe" 處理常式會在發行的7月更新中平均使用大約 100 MB，因此 M365 的測試基底會識別回歸。</span><span class="sxs-lookup"><span data-stu-id="06f03-125">In this example, the favorite process “USLTestMemoryStress.exe” process consumed an average of approximately 100 MB on the pre-release August update compared to the released July update, hence the Test Base for M365 identified a regression.</span></span> 

<span data-ttu-id="06f03-126">其他進程（如這裡所示）是「USLTestMemoryStress_Aux1.exe」和「USLTestMemoryStress_Aux2.exe」，也屬於同一個應用程式，但在兩個版本中佔用的記憶體量大致相同，所以它們已被視為「已傳遞」，且被視為狀況良好。</span><span class="sxs-lookup"><span data-stu-id="06f03-126">The other processes—shown here as “USLTestMemoryStress_Aux1.exe” and “USLTestMemoryStress_Aux2.exe”—also belong to the same application, but consumed approximately the same amount of memory for the two releases so they "passed" and were considered healthy.</span></span>

<span data-ttu-id="06f03-127">主要程式的退化決定是「統計重要」，所以服務會進行通訊並反白顯示此與使用者的差異。</span><span class="sxs-lookup"><span data-stu-id="06f03-127">The regression on the main process was determined to be “statistically significant” so the service communicated and highlighted this difference to the user.</span></span> <span data-ttu-id="06f03-128">如果比較的統計不重要，將不會反白顯示。</span><span class="sxs-lookup"><span data-stu-id="06f03-128">If the comparison was not statistically significant, it would not be highlighted.</span></span> <span data-ttu-id="06f03-129">記憶體使用量可能會有噪音，所以我們使用統計模型來區分各組建和發行，與 inconsequential 差異有意義的差異。</span><span class="sxs-lookup"><span data-stu-id="06f03-129">Memory utilization can be noisy, so we use statistical models to distinguish, across builds and releases, meaningful differences from inconsequential differences.</span></span> 

<span data-ttu-id="06f03-130">當 (誤報) 沒有真正差異時，比較可能很少會被標記，但這是必要的折衷，以提升正確識別回歸 (或 true 正值的可能性。 ) </span><span class="sxs-lookup"><span data-stu-id="06f03-130">A comparison may rarely be flagged when there is no true difference (a false positive), but this is a necessary tradeoff to improve the likelihood of correctly identifying regressions (or true positives.)</span></span>

<span data-ttu-id="06f03-131">下一步是瞭解導致記憶體回歸的原因。</span><span class="sxs-lookup"><span data-stu-id="06f03-131">The next step is to understand what caused the memory regression.</span></span> <span data-ttu-id="06f03-132">您可以從 [下載記錄檔] 選項下載這兩個執行的 zip 檔案，如下所示。</span><span class="sxs-lookup"><span data-stu-id="06f03-132">You can download the zip files for both executions from the Download log files option, as shown below.</span></span> 

<span data-ttu-id="06f03-133">這些 zip 檔案包含測試執行的結果，其中包括 ETL 檔案中所包含的腳本結果和記憶體及 CPU 效能資料。</span><span class="sxs-lookup"><span data-stu-id="06f03-133">These zip files contain the results of your test run, including script results and memory and CPU performance data which is included in the ETL file.</span></span>

![記憶體迴歸測試檔案](Media/04_memory-regression-test-files.png)

<span data-ttu-id="06f03-135">您可以下載和解壓縮兩個測試執行的記錄檔，然後找出每個資料夾中的 ETL 檔案，並將其重新命名為 target (。測試執行的測試執行) 和基線)  (上的測試執行，以簡化勘探及導覽。</span><span class="sxs-lookup"><span data-stu-id="06f03-135">You can download and unzip the logs for the two test runs, then locate the ETL file within each folder and rename them as target.etl (for the test run on the pre-release update) and baseline.etl (for the test run on last released update) to simplify exploration and navigation.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="06f03-136">後續步驟</span><span class="sxs-lookup"><span data-stu-id="06f03-136">Next steps</span></span>

<span data-ttu-id="06f03-137">若要開始深入瞭解智慧 CPU 迴歸分析，請繼續進行下一篇文章。</span><span class="sxs-lookup"><span data-stu-id="06f03-137">Advance to the next article to get started with understanding intelligent CPU regression analysis.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="06f03-138">下一步</span><span class="sxs-lookup"><span data-stu-id="06f03-138">Next step</span></span>](cpu.md)

<!---
Add button for next page
-->
