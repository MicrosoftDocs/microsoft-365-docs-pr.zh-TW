---
title: 進階電子文件探索
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: fd53438a-a760-45f6-9df4-861b50161ae4
description: 深入瞭解高級 eDiscovery 如何協助您分析資料、簡化檔檢查，並做出有效 eDiscovery 的決策。
ms.openlocfilehash: f8ada5d377e72516ea42d8c5dc5680573daec717
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662818"
---
# <a name="advanced-ediscovery-classic"></a><span data-ttu-id="83f26-103">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="83f26-103">Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83f26-104">**Advanced eDiscovery (傳統) 會在2020年12月31日永久撤銷。**</span><span class="sxs-lookup"><span data-stu-id="83f26-104">**Advanced eDiscovery (classic) will be permanently retired on December 31, 2020.**</span></span><br/>
> <span data-ttu-id="83f26-105">當我們繼續投資更新的高級 eDiscovery 時，我們會宣佈從 Advanced eDiscovery (傳統) 中永久淘汰和移除案例及案例資料。</span><span class="sxs-lookup"><span data-stu-id="83f26-105">As we continue to invest in newer versions of Advanced eDiscovery, we're announcing the permanent retirement and removal of cases and case data from Advanced eDiscovery (classic).</span></span>
> <span data-ttu-id="83f26-106">如果您仍在使用 Advanced eDiscovery (傳統) （也稱為「 *高級 ediscovery 1.0* 版」），請將您的使用轉變為 [高級 ediscovery 2.0 版](overview-ediscovery-20.md) ， (也稱為 *Microsoft 365) 中的高級 eDiscovery 解決方案* 。</span><span class="sxs-lookup"><span data-stu-id="83f26-106">If you're still using Advanced eDiscovery (classic), also known as *Advanced eDiscovery v1.0*, please transition your usage to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span>  <span data-ttu-id="83f26-107">在準備移除所有案例及案例資料時，您可以 [從案例中匯出資料](https://docs.microsoft.com/microsoft-365/compliance/export-results-in-advanced-ediscovery?view=o365-worldwide)，以封存案例資料。</span><span class="sxs-lookup"><span data-stu-id="83f26-107">In preparation for the removal of all cases and case data, you can archive case data by [exporting data from a case](https://docs.microsoft.com/microsoft-365/compliance/export-results-in-advanced-ediscovery?view=o365-worldwide).</span></span>
> <span data-ttu-id="83f26-108">「高級 eDiscovery ' 2.0」包含在高級 eDiscovery 1.0 中找到的類似功能，但也提供許多新功能，例如保管人管理、通訊管理及審查集。</span><span class="sxs-lookup"><span data-stu-id="83f26-108">Advanced eDiscovery v2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="83f26-109">若要深入瞭解 Advanced eDiscovery 1.0 的先前 retirment 階段，請參閱 [舊版 eDiscovery tools 的退休](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。</span><span class="sxs-lookup"><span data-stu-id="83f26-109">To learn more about the previous retirment phases of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span>

<span data-ttu-id="83f26-110">透過高級電子檔探索，您可以更好地瞭解資料，並減少 eDiscovery 成本。</span><span class="sxs-lookup"><span data-stu-id="83f26-110">With Advanced eDiscovery, you can better understand your data and reduce your eDiscovery costs.</span></span> <span data-ttu-id="83f26-111">「高級 eDiscovery」可協助您分析非結構化資料、執行更有效率的檔檢查，並作出決策以減少 eDiscovery 的資料。</span><span class="sxs-lookup"><span data-stu-id="83f26-111">Advanced eDiscovery helps you analyze unstructured data, perform more efficient document review, and make decisions to reduce data for eDiscovery.</span></span> <span data-ttu-id="83f26-112">您可以使用儲存在 Exchange Online 中的資料、SharePoint 線上 OneDrive、商務用 Skype、商務用 Skype、Microsoft 365 群組和 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="83f26-112">You can work with data stored in Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft 365 Groups, and Microsoft Teams.</span></span> <span data-ttu-id="83f26-113">您可以在 [安全性與合規性中心] 中執行 eDiscovery 搜尋，以搜尋群組、個別信箱和網站中的內容，然後使用「高級 eDiscovery」分析搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="83f26-113">You can perform an eDiscovery search in the security and compliance center to search for content in groups, individual mailboxes and sites, and then analyze the search results with Advanced eDiscovery.</span></span> <span data-ttu-id="83f26-114">當您在高級 eDiscovery 中準備用於分析的搜尋結果時，光學字元辨識功能可讓您從影像提取文字。</span><span class="sxs-lookup"><span data-stu-id="83f26-114">When you prepare search results for analysis in Advanced eDiscovery, Optical Character Recognition enables the extraction of text from images.</span></span> <span data-ttu-id="83f26-115">這項功能可讓高級 eDiscovery 的強大文字分析功能能夠套用到圖像檔案。</span><span class="sxs-lookup"><span data-stu-id="83f26-115">This feature allows the powerful text analytic capabilities of Advanced eDiscovery to be applied to image files.</span></span>
  
<span data-ttu-id="83f26-116">Advanced eDiscovery 可透過接近重複偵測和電子郵件線索分析等功能識別冗余資訊，以簡化並加速檔審閱過程。</span><span class="sxs-lookup"><span data-stu-id="83f26-116">Advanced eDiscovery streamlines and speeds up the document review process by identifying redundant information with features like Near-duplicates detection and Email Thread analysis.</span></span> <span data-ttu-id="83f26-117">相關性功能會套用預測編碼技術來識別相關的檔。</span><span class="sxs-lookup"><span data-stu-id="83f26-117">The Relevance feature applies predictive coding technology to identify relevant documents.</span></span> <span data-ttu-id="83f26-118">「高級 eDiscovery」會從您的範例檔的標記決策中瞭解，並套用統計及自我教學技術，計算資料集中每個檔的相關性。</span><span class="sxs-lookup"><span data-stu-id="83f26-118">Advanced eDiscovery learns from your tagging decisions on sample documents and applies statistical and self-learning techniques to calculate the relevance of each document in the data set.</span></span> <span data-ttu-id="83f26-119">這可讓您將重點放在重要檔上，並在案例策略、挑選資料和優先順序檢查等方面作出及時的決策決策。</span><span class="sxs-lookup"><span data-stu-id="83f26-119">This enables you to focus on key documents, make quick yet informed decisions on case strategy, cull data, and prioritize review.</span></span>
  
 <span data-ttu-id="83f26-120">**為何要成為高級電子檔探索？**</span><span class="sxs-lookup"><span data-stu-id="83f26-120">**Why advanced eDiscovery?**</span></span> <span data-ttu-id="83f26-121">在 Office 365 的現有 eDiscovery 功能集中建立高級 eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="83f26-121">Advanced eDiscovery builds on the existing set of eDiscovery capabilities in Office 365.</span></span> <span data-ttu-id="83f26-122">例如，您可以使用安全規範中心中的「搜尋」功能，對 &amp; 組織中的所有內容來源執行初始搜尋，以找出並收集可能與特定法律案例相關的資料。</span><span class="sxs-lookup"><span data-stu-id="83f26-122">For example, you can use the Search feature in the Security &amp; Compliance Center to perform an initial search of all the content sources in your organization to identify and collect the data that may be relevant to a specific legal case.</span></span> <span data-ttu-id="83f26-123">接著，您可以套用 text analytics、機器學習及高級 eDiscovery 的相關性/預測性編碼功能，對該資料執行分析。</span><span class="sxs-lookup"><span data-stu-id="83f26-123">Then you can perform analysis on that data by applying the text analytics, machine learning, and the Relevance/predictive coding capabilities of Advanced eDiscovery.</span></span> <span data-ttu-id="83f26-124">這可協助您的組織快速處理成千上萬的電子郵件訊息、檔，以及其他種類的資料，以找出最可能與特定相關的專案。</span><span class="sxs-lookup"><span data-stu-id="83f26-124">This can help your organization quickly process thousands of email messages, documents, and other kinds of data to find those items that are most likely relevant to a specific</span></span> 
 
> [!NOTE]
> <span data-ttu-id="83f26-125">「高級 eDiscovery」需要 Office 365 E3，具有您組織的「高級規範附加元件」或「E5」訂閱。</span><span class="sxs-lookup"><span data-stu-id="83f26-125">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="83f26-126">如果您沒有這項計畫，且想要嘗試使用 Advanced eDiscovery，您可以 [註冊 Office 365 企業版 E5 的試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="83f26-126">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> <span data-ttu-id="83f26-127">情況 下。</span><span class="sxs-lookup"><span data-stu-id="83f26-127">case.</span></span> <span data-ttu-id="83f26-128">簡化後的資料集可以從 Office 365 匯出，以供進一步複查。</span><span class="sxs-lookup"><span data-stu-id="83f26-128">The reduced data set can then be exported out of Office 365 for further review.</span></span> 
  
## <a name="get-started"></a><span data-ttu-id="83f26-129">入門</span><span class="sxs-lookup"><span data-stu-id="83f26-129">Get started</span></span>

<span data-ttu-id="83f26-130">開始使用高級 eDiscovery 的最快捷方式是建立案例並準備安全性 & 規範中心的搜尋結果，並在 [Advanced eDiscovery] 中載入這些結果，然後執行 [快速分析] 以分析案例資料，然後將結果匯出以進行外部審閱。</span><span class="sxs-lookup"><span data-stu-id="83f26-130">The quickest way to get started with Advanced eDiscovery is to create a case and prepare search results in Security & Compliance Center, load those results in Advanced eDiscovery, and then run Express analysis to analyze that case data and then export the results for external review.</span></span>
  
- <span data-ttu-id="83f26-131">[快速瞭解](quick-setup-for-advanced-ediscovery.md) 高級 eDiscovery 工作流程</span><span class="sxs-lookup"><span data-stu-id="83f26-131">[Get a quick overview](quick-setup-for-advanced-ediscovery.md) of the Advanced eDiscovery workflow</span></span> 
    
- <span data-ttu-id="83f26-132">使用安全性 & 合規性中心建立案例、指派 eDiscovery 許可權及新增案例成員，以設定高級 eDiscovery 的[使用者和案例](set-up-users-and-cases-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="83f26-132">[Set up users and cases](set-up-users-and-cases-in-advanced-ediscovery.md) for Advanced eDiscovery by creating a case, assigning eDiscovery permissions, and adding case members, all by using the Security & Compliance Center</span></span> 
    
- <span data-ttu-id="83f26-133">在高級電子檔探索的案例中[準備及載入搜尋資料](prepare-data-for-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="83f26-133">[Prepare and load search data](prepare-data-for-advanced-ediscovery.md) in to the case in Advanced eDiscovery</span></span> 
    
- <span data-ttu-id="83f26-134">將[非 Office 365 資料載入](import-non-office-365-data-into-advanced-ediscovery.md)到案例中，以在高級 eDiscovery 中進行分析</span><span class="sxs-lookup"><span data-stu-id="83f26-134">[Load non-Office 365 data](import-non-office-365-data-into-advanced-ediscovery.md) in to a case to analyze it in Advanced eDiscovery</span></span> 
    
- <span data-ttu-id="83f26-135">[使用快速分析](use-express-analysis-in-advanced-ediscovery.md) 以快速分析案例中的資料，然後輕鬆匯出結果</span><span class="sxs-lookup"><span data-stu-id="83f26-135">[Use Express analysis](use-express-analysis-in-advanced-ediscovery.md) to quickly analyze the data in a case and then easily export the results</span></span> 
    
## <a name="analyze-data"></a><span data-ttu-id="83f26-136">分析資料</span><span class="sxs-lookup"><span data-stu-id="83f26-136">Analyze data</span></span>

<span data-ttu-id="83f26-137">在 [Advanced eDiscovery] 中載入搜尋資料後，您將使用 [分析] 模組開始進行分析。</span><span class="sxs-lookup"><span data-stu-id="83f26-137">After search data is loaded into the case in Advanced eDiscovery, you'll use the Analyze module to start analyzing it.</span></span> <span data-ttu-id="83f26-138">分析程式的第一個部分包括將檔案組織成一組獨特的檔案、重複專案和臨近記錄的 (同時也知道檔相似性) 。</span><span class="sxs-lookup"><span data-stu-id="83f26-138">The first part of the analysis process consists of organizing files into groups of unique files, duplicates, and near-duplicates (also know as document similarity).</span></span> <span data-ttu-id="83f26-139">然後，您可以將資料再次組織成分層結構化的電子郵件執行緒及主題，並選擇性地設定 [忽略文字篩選]，以排除特定文字的分析。</span><span class="sxs-lookup"><span data-stu-id="83f26-139">Then you organize the data again into hierarchically structured groups of email threads and themes and, optionally, set ignore text filters to exclude certain text from analysis.</span></span> <span data-ttu-id="83f26-140">然後，您會執行分析並查看結果。</span><span class="sxs-lookup"><span data-stu-id="83f26-140">Then you run the analysis and view the results.</span></span>
  
- <span data-ttu-id="83f26-141">[深入瞭解檔相似性](understand-document-similarity-in-advanced-ediscovery.md) ，以準備在高級 eDiscovery 中分析資料</span><span class="sxs-lookup"><span data-stu-id="83f26-141">[Learn about document similarity](understand-document-similarity-in-advanced-ediscovery.md) to prepare you for analyzing data in Advanced eDiscovery</span></span> 
    
- <span data-ttu-id="83f26-142">設定臨近重複、主題及電子郵件執行緒[的選項](set-analyze-options-in-advanced-ediscovery.md)，然後執行分析模組</span><span class="sxs-lookup"><span data-stu-id="83f26-142">[Set up the options](set-analyze-options-in-advanced-ediscovery.md) for near-duplicates, themes, and email threading and then run the Analyze module</span></span> 
    
- <span data-ttu-id="83f26-143">設定 [忽略文字和文字字串加以分析] 的 [[忽略文字] 篩選器](set-ignore-text-in-advanced-ediscovery.md);當您執行相關性分析時，這些篩選也會略過文字</span><span class="sxs-lookup"><span data-stu-id="83f26-143">[Set up Ignore Text filters](set-ignore-text-in-advanced-ediscovery.md) to exclude text and text strings from being analyzed; these filters will also ignore text when you run Relevance analysis</span></span> 
    
- <span data-ttu-id="83f26-144">[查看](view-analyze-results-in-advanced-ediscovery.md) 分析處理常式的結果</span><span class="sxs-lookup"><span data-stu-id="83f26-144">[View the results](view-analyze-results-in-advanced-ediscovery.md) of the analysis process</span></span> 
    
- <span data-ttu-id="83f26-145">設定分析處理常式的[高級設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="83f26-145">[Configure advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for the analysis process</span></span> 
    
## <a name="set-up-relevance-training"></a><span data-ttu-id="83f26-146">設定相關性訓練</span><span class="sxs-lookup"><span data-stu-id="83f26-146">Set up Relevance training</span></span>

<span data-ttu-id="83f26-147">在「高級 eDiscovery」中稱為相關性) 的預測編碼 (可讓您進行決策 (有關某一小型檔上是否有相關資訊，或不) 。</span><span class="sxs-lookup"><span data-stu-id="83f26-147">Predictive coding (called Relevance) in Advanced eDiscovery lets you train the system on what you're looking for by letting you to make decisions (about whether something is relevant or not) on a small set of documents.</span></span>
  
- <span data-ttu-id="83f26-148">[瞭解如何設定相關性訓練](manage-relevance-setup-in-advanced-ediscovery.md) 、標記與案例相關的檔案，以及定義案例問題</span><span class="sxs-lookup"><span data-stu-id="83f26-148">[Learn about setting up Relevance training](manage-relevance-setup-in-advanced-ediscovery.md) , tagging files that are relevant to a case, and defining case issues</span></span> 
    
- <span data-ttu-id="83f26-149">[定義案例問題](define-issues-and-assign-users.md) ，並將每個問題指派給將訓練檔的使用者</span><span class="sxs-lookup"><span data-stu-id="83f26-149">[Define case issues](define-issues-and-assign-users.md) and assign each issue to a user who will train the files</span></span> 
    
- <span data-ttu-id="83f26-150">將匯入的檔案新增至將新增至相關性訓練的[目前或新的負載](set-up-loads-to-add-imported-files.md)。</span><span class="sxs-lookup"><span data-stu-id="83f26-150">[Add imported files to current or new load](set-up-loads-to-add-imported-files.md) that will be added to the Relevance training.</span></span> <span data-ttu-id="83f26-151">「負載」是新增至案例，然後用於相關性訓練的新批次檔</span><span class="sxs-lookup"><span data-stu-id="83f26-151">A load is a new batch of files that are added to a case and then used for Relevance training</span></span> 
    
- <span data-ttu-id="83f26-152">定義可以新增至相關性訓練的[突出顯示關鍵字](define-highlighted-keywords-and-advanced-options.md)。</span><span class="sxs-lookup"><span data-stu-id="83f26-152">[Define highlighted keywords](define-highlighted-keywords-and-advanced-options.md) that can be added to the Relevance training.</span></span> <span data-ttu-id="83f26-153">這可協助您更好地識別與案例相關的檔案</span><span class="sxs-lookup"><span data-stu-id="83f26-153">This helps you better identify files that are relevant to a case</span></span> 
    
## <a name="run-the-relevance-module"></a><span data-ttu-id="83f26-154">執行相關性模組</span><span class="sxs-lookup"><span data-stu-id="83f26-154">Run the Relevance module</span></span>

<span data-ttu-id="83f26-155">設定訓練後，您就可以執行相關性模組，並評估訓練設定的有效性。</span><span class="sxs-lookup"><span data-stu-id="83f26-155">After set up training, you're ready to run the Relevance module and assess the effectiveness of the training settings.</span></span> <span data-ttu-id="83f26-156">這會產生相關性排名，可協助您決定是否需要執行其他訓練，或是否準備好開始標籤與案例相關的標記。</span><span class="sxs-lookup"><span data-stu-id="83f26-156">This results in a relevance ranking that helps you decide if you need to perform additional training or if you're ready to start tagging files as relevant to your case.</span></span>
  
- <span data-ttu-id="83f26-157">[深入瞭解](use-relevance-in-advanced-ediscovery.md) 根據檔案的範例集合，相關性處理常式和進行評估、標記、追蹤和重新培訓的處理過程</span><span class="sxs-lookup"><span data-stu-id="83f26-157">[Learn about the Relevance process](use-relevance-in-advanced-ediscovery.md) and the iterative process of assessment, tagging, tracking, and retraining based on sample set of files</span></span> 
    
- <span data-ttu-id="83f26-158">[瞭解評估](assessment-in-relevance-in-advanced-ediscovery.md) ，熟悉案例的專家會回顧一組案例檔案，並判斷相關性訓練的效能</span><span class="sxs-lookup"><span data-stu-id="83f26-158">[Learn about assessment](assessment-in-relevance-in-advanced-ediscovery.md) , where an expert familiar with the case reviews a set of case files and determines the effectiveness of the Relevance training</span></span> 
    
- <span data-ttu-id="83f26-159">[評估案例](tagging-and-assessment-in-advanced-ediscovery.md) 檔案，以計算稱為「豐富的訓練」) 訓練設定的效能 (，然後標記檔案為相關或不相關的案例。</span><span class="sxs-lookup"><span data-stu-id="83f26-159">[Assess case files](tagging-and-assessment-in-advanced-ediscovery.md) to calculate the effectiveness (called  \*richness) of training settings, and then tag files as relevant or not relevant to your case.</span></span> <span data-ttu-id="83f26-160">這可協助您判斷目前的訓練是否足夠，或者是否應該調整訓練設定。</span><span class="sxs-lookup"><span data-stu-id="83f26-160">This helps you determine if the current training is sufficient or if you should adjust the training settings.</span></span> 
    
- <span data-ttu-id="83f26-161">完成評估之後請[執行相關性訓練](tagging-and-relevance-training-in-advanced-ediscovery.md)，然後再將檔案標記為相關的問題或與您為案例定義的問題無關。</span><span class="sxs-lookup"><span data-stu-id="83f26-161">[Perform the relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md) after assessment is complete, and then once again tag files as relevant or not relevant to the issues you've defined for the case</span></span> 
    
- <span data-ttu-id="83f26-162">[追蹤相關性分析](track-relevance-analysis-in-advanced-ediscovery.md) 程式，判斷相關性訓練是否已實現評估目標 (稱為 \* 穩定的訓練狀態) 或是否需要更多訓練;您也可以針對每個案例問題，查看相關性結果</span><span class="sxs-lookup"><span data-stu-id="83f26-162">[Track the Relevance analysis](track-relevance-analysis-in-advanced-ediscovery.md) process to determine if Relevance training has achieved your assessment target (known as a  \*stable training status) or whether more training is needed; you can also view the Relevance results for each case issue</span></span> 
    
- <span data-ttu-id="83f26-163">根據[相關性分析作出決策](decision-based-on-the-results-in-advanced-ediscovery.md)，以判斷可匯出以供審閱之一組所產生之案例檔案的大小</span><span class="sxs-lookup"><span data-stu-id="83f26-163">[Make decisions based on Relevance analysis](decision-based-on-the-results-in-advanced-ediscovery.md) to determine the size of the resulting set of case files that can be exported for review</span></span> 
    
- <span data-ttu-id="83f26-164">[測試相關性分析的品質](test-relevance-analysis-in-advanced-ediscovery.md) ，以驗證相關性過程中所進行的挑選決定</span><span class="sxs-lookup"><span data-stu-id="83f26-164">[Test the quality of the Relevance analysis](test-relevance-analysis-in-advanced-ediscovery.md) to validate the culling decisions made during the Relevance process</span></span> 
    
## <a name="export-results"></a><span data-ttu-id="83f26-165">匯出結果</span><span class="sxs-lookup"><span data-stu-id="83f26-165">Export results</span></span>

<span data-ttu-id="83f26-166">在「高級 eDiscovery」中分析案例資料的最後一個步驟，就是匯出分析的結果以進行外部考核。</span><span class="sxs-lookup"><span data-stu-id="83f26-166">The final step in analyzing case data in Advanced eDiscovery is to export results of the analysis for external review.</span></span>
  
- [<span data-ttu-id="83f26-167">瞭解匯出案例資料</span><span class="sxs-lookup"><span data-stu-id="83f26-167">Learn about exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="83f26-168">匯出案例資料</span><span class="sxs-lookup"><span data-stu-id="83f26-168">Export case data</span></span>](export-results-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="83f26-169">檢視批次歷程記錄及匯出過去的結果</span><span class="sxs-lookup"><span data-stu-id="83f26-169">View batch history and export past results</span></span>](view-batch-history-and-export-past-results.md)
    
- [<span data-ttu-id="83f26-170">匯出報告欄位</span><span class="sxs-lookup"><span data-stu-id="83f26-170">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
    
## <a name="other-advanced-ediscovery-tools"></a><span data-ttu-id="83f26-171">其他的高級電子檔探索工具</span><span class="sxs-lookup"><span data-stu-id="83f26-171">Other Advanced eDiscovery tools</span></span>

<span data-ttu-id="83f26-172">「高級 eDiscovery」提供其他工具和功能，除了分析案例資料、相關性分析和匯出資料之外。</span><span class="sxs-lookup"><span data-stu-id="83f26-172">Advanced eDiscovery provides additional tools and capabilities beyond analyzing case data, relevance analysis, and exporting data.</span></span>
  
- [<span data-ttu-id="83f26-173">執行高級 eDiscovery 報告</span><span class="sxs-lookup"><span data-stu-id="83f26-173">Run Advanced eDiscovery reports</span></span>](run-reports-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="83f26-174">定義案例與租使用者設定</span><span class="sxs-lookup"><span data-stu-id="83f26-174">Define case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="83f26-175">高級 eDiscovery 公用程式</span><span class="sxs-lookup"><span data-stu-id="83f26-175">Advanced eDiscovery utilities</span></span>](use-advanced-ediscovery-utilities.md)
