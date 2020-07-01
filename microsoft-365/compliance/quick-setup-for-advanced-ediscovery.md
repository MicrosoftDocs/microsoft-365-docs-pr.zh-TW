---
title: 進階電子文件探索的快速設定
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: 了解如何從安全性與合規性中心存取進階電子文件探索，以及檢閱使用進階電子文件探索的一般工作流程。
ms.openlocfilehash: 5bd183f0f5f1c2f091fb374aab1e54f191665ce6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936256"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a><span data-ttu-id="6985a-103">快速設定進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="6985a-103">Quick setup Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6985a-104">隨著我們繼續投資於更新版本的進階電子文件探索，我們即將宣布停用進階文件探索 (也稱為*進階電子文件探索 (傳統版)* 或*進階文件探索 1.0 版*)。</span><span class="sxs-lookup"><span data-stu-id="6985a-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="6985a-105">如果您仍在使用進階電子文件探索 1.0 版，請盡快轉換為[進階電子文件探索 2.0 版](overview-ediscovery-20.md) (*在Microsoft 365 中也稱為進階電子文件探索解決方案*)。</span><span class="sxs-lookup"><span data-stu-id="6985a-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="6985a-106">進階電子文件探索 2.0 中包含可在進階電子文件探索 1.0 版中找到的類似功能，但同時也提供許多新的功能，例如監管人管理、通訊管理和檢閱集。</span><span class="sxs-lookup"><span data-stu-id="6985a-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="6985a-107">若要深入了解進階電子文件探索 1.0 版的停用，請參閱[舊版電子文件探索工具的停用](legacy-ediscovery-retirement.md#advanced-ediscovery-v10) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="6985a-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="6985a-108">此設定小節將為 Microsoft 365 安全性與合規性中心的電子文件探索管理員說明如何開始使用「進階電子文件探索」。</span><span class="sxs-lookup"><span data-stu-id="6985a-108">This setup section shows an Microsoft 365 Security &amp; Compliance Center eDiscovery manager how to get started with Advanced eDiscovery.</span></span> <span data-ttu-id="6985a-109">本文假設使用者具備這兩者的工作知識。</span><span class="sxs-lookup"><span data-stu-id="6985a-109">A working knowledge of both is assumed.</span></span>
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a><span data-ttu-id="6985a-110">存取進階電子文件探索中的案例</span><span class="sxs-lookup"><span data-stu-id="6985a-110">Accessing a case in Advanced eDiscovery</span></span>

<span data-ttu-id="6985a-111">You access Advanced eDiscovery from the Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="6985a-111">You access Advanced eDiscovery from the Security &amp; Compliance Center.</span></span> <span data-ttu-id="6985a-112">You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6985a-112">You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery.</span></span> <span data-ttu-id="6985a-113">For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="6985a-113">For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span></span> 
  
<span data-ttu-id="6985a-114">若要移至進階電子文件探索中的案例：</span><span class="sxs-lookup"><span data-stu-id="6985a-114">To go to a case in Advanced eDiscovery:</span></span> 
  
1. <span data-ttu-id="6985a-115">[前往安全性與合規性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="6985a-115">[Go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="6985a-116">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="6985a-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
3. <span data-ttu-id="6985a-117">在 [電子文件探索]\*\*\*\* 頁面上，按一下進階電子文件探索中您要移至的案例旁邊的 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6985a-117">On the **eDiscovery** page, click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span>
    
4. <span data-ttu-id="6985a-118">在案例的 [首頁]\*\*\*\* 頁面上，按一下 [切換至進階電子文件探索]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6985a-118">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span>
    
    <span data-ttu-id="6985a-119">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span><span class="sxs-lookup"><span data-stu-id="6985a-119">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="6985a-120">When you're connected, the case is opened in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6985a-120">When you're connected, the case is opened in Advanced eDiscovery.</span></span> 
    
## <a name="workflow"></a><span data-ttu-id="6985a-121">工作流程</span><span class="sxs-lookup"><span data-stu-id="6985a-121">Workflow</span></span>

<span data-ttu-id="6985a-122">下圖說明常見的工作流程，用於管理和使用安全性與合規性中心以及進階電子文件探索中的電子文件探索案例。</span><span class="sxs-lookup"><span data-stu-id="6985a-122">The following diagram illustrates the common workflow for managing and using eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span>
  
![圖表會顯示設定中四個階段的進階電子文件探索工作流程，包括設定使用者和案例、識別案例資料、匯出及處理，接著是分析並匯出至本機電腦的階段。](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
<span data-ttu-id="6985a-124">This setup section describes the first four steps in the workflow.</span><span class="sxs-lookup"><span data-stu-id="6985a-124">This setup section describes the first four steps in the workflow.</span></span> <span data-ttu-id="6985a-125">For a description of the other steps in the workflow, see the following.</span><span class="sxs-lookup"><span data-stu-id="6985a-125">For a description of the other steps in the workflow, see the following.</span></span>
  
## <a name="analyze"></a><span data-ttu-id="6985a-126">分析</span><span class="sxs-lookup"><span data-stu-id="6985a-126">Analyze</span></span>

<span data-ttu-id="6985a-127">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results.</span><span class="sxs-lookup"><span data-stu-id="6985a-127">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results.</span></span> <span data-ttu-id="6985a-128">Analyze functionality can be customized by the user in order to achieve enhanced results.</span><span class="sxs-lookup"><span data-stu-id="6985a-128">Analyze functionality can be customized by the user in order to achieve enhanced results.</span></span> 
  
## <a name="relevance-setup-and-relevance"></a><span data-ttu-id="6985a-129">相關性設定和相關性</span><span class="sxs-lookup"><span data-stu-id="6985a-129">Relevance Setup and Relevance</span></span>

<span data-ttu-id="6985a-130">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process.</span><span class="sxs-lookup"><span data-stu-id="6985a-130">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process.</span></span> <span data-ttu-id="6985a-131">Calculates and displays interim results while monitoring statistical validity of the process.</span><span class="sxs-lookup"><span data-stu-id="6985a-131">Calculates and displays interim results while monitoring statistical validity of the process.</span></span> <span data-ttu-id="6985a-132">Displays the results to facilitate in making review decisions.</span><span class="sxs-lookup"><span data-stu-id="6985a-132">Displays the results to facilitate in making review decisions.</span></span> 
  
## <a name="export"></a><span data-ttu-id="6985a-133">匯出</span><span class="sxs-lookup"><span data-stu-id="6985a-133">Export</span></span>

<span data-ttu-id="6985a-134">[匯出案例資料](export-case-data-in-advanced-ediscovery.md) 可讓您匯出進階電子文件探索內容和結果，進行外部檢閱。</span><span class="sxs-lookup"><span data-stu-id="6985a-134">[Exporting case data](export-case-data-in-advanced-ediscovery.md) Enables the exporting of Advanced eDiscovery content and results for external review.</span></span> 
  
## <a name="report"></a><span data-ttu-id="6985a-135">報告</span><span class="sxs-lookup"><span data-stu-id="6985a-135">Report</span></span>

<span data-ttu-id="6985a-136">[執行報告](run-reports-in-advanced-ediscovery.md) 可讓您產生選取的報告，其與進階電子文件探索處理相關。</span><span class="sxs-lookup"><span data-stu-id="6985a-136">[Running reports](run-reports-in-advanced-ediscovery.md) Enables the generation of selected reports related to Advanced eDiscovery processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6985a-137">請參閱</span><span class="sxs-lookup"><span data-stu-id="6985a-137">See also</span></span>

[<span data-ttu-id="6985a-138">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="6985a-138">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="6985a-139">設定使用者和案例</span><span class="sxs-lookup"><span data-stu-id="6985a-139">Setting up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6985a-140">準備安裝</span><span class="sxs-lookup"><span data-stu-id="6985a-140">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)

