---
title: 快速設定 Office 365 進階電子文件探索
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
description: '了解如何從 Office 365 安全性與合規性中心存取 Office 365 進階電子文件探索，以及檢閱使用進階電子文件探索的一般工作流程。  '
ms.openlocfilehash: 6df2d68639f2be9f6ba38ea7211654058bc73035
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597670"
---
# <a name="quick-setup-for-office-365-advanced-ediscovery"></a><span data-ttu-id="4d95f-103">快速設定 Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="4d95f-103">Quick setup for Office 365 Advanced eDiscovery</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d95f-104">隨著我們繼續投資於更新版本的進階電子文件探索，我們現在宣布停用 Office 365 進階文件探索 (也稱為*進階文件探索 1.0 版*)。</span><span class="sxs-lookup"><span data-stu-id="4d95f-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Office 365 Advanced eDiscovery (also known as *Advanced eDiscovery v1.0*).</span></span> <span data-ttu-id="4d95f-105">如果您仍在使用進階電子文件探索 1.0 版，請盡快轉換為[進階電子文件探索 2.0 版](overview-ediscovery-20.md) (*在Microsoft 365 中也稱為進階電子文件探索解決方案*)。</span><span class="sxs-lookup"><span data-stu-id="4d95f-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="4d95f-106">進階電子文件探索 2.0 中包含可在進階電子文件探索 1.0 版中找到的類似功能，但同時也提供許多新的功能，例如監管人管理、通訊管理和檢閱集。</span><span class="sxs-lookup"><span data-stu-id="4d95f-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="4d95f-107">若要深入了解進階電子文件探索 1.0 版的停用，請參閱[舊版電子文件探索工具的停用](legacy-ediscovery-retirement.md#advanced-ediscovery-v10) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="4d95f-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="4d95f-108">此設定小節將為 Microsoft 365 安全性與合規性中心的電子文件探索管理員說明如何開始使用「進階電子文件探索」。</span><span class="sxs-lookup"><span data-stu-id="4d95f-108">This setup section shows an Microsoft 365 Security &amp; Compliance Center eDiscovery manager how to get started with Advanced eDiscovery.</span></span> <span data-ttu-id="4d95f-109">本文假設使用者具備這兩者的工作知識。</span><span class="sxs-lookup"><span data-stu-id="4d95f-109">A working knowledge of both is assumed.</span></span>
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a><span data-ttu-id="4d95f-110">存取進階電子文件探索中的案例</span><span class="sxs-lookup"><span data-stu-id="4d95f-110">Accessing a case in Advanced eDiscovery</span></span>


<span data-ttu-id="4d95f-p103">您可以從安全性與合規性中心存取進階電子文件探索。您必須是安全性與合規性中心的電子文件探索案例的成員，才能存取進階電子文件探索中的案例。如需指派電子文件探索案例權限，並將使用者新增至電子文件探索案例的相關指示，請參閱[管理 Office 365 中的電子文件探索案例](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="4d95f-p103">You access Advanced eDiscovery from the Security &amp; Compliance Center. You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery. For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span></span> 
  
<span data-ttu-id="4d95f-114">若要移至進階電子文件探索中的案例：</span><span class="sxs-lookup"><span data-stu-id="4d95f-114">To go to a case in Advanced eDiscovery:</span></span> 
  
1. <span data-ttu-id="4d95f-115">[移至 Office 365 安全性與合規性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="4d95f-115">[Go to the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="4d95f-116">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="4d95f-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
3. <span data-ttu-id="4d95f-117">在 [電子文件探索]\*\*\*\* 頁面上，按一下進階電子文件探索中您要移至的案例旁邊的 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4d95f-117">On the **eDiscovery** page, click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span> 
    
4. <span data-ttu-id="4d95f-118">在案例的 [首頁]\*\*\*\* 頁面上，按一下 [進階電子文件探索]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4d95f-118">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span>
    
    <span data-ttu-id="4d95f-p104">即會顯示 [連線至進階電子文件探索]\*\*\*\*。連線時，會在進階電子文件探索中開啟案例。</span><span class="sxs-lookup"><span data-stu-id="4d95f-p104">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery.</span></span> 
    
## <a name="workflow"></a><span data-ttu-id="4d95f-121">工作流程</span><span class="sxs-lookup"><span data-stu-id="4d95f-121">Workflow</span></span>

<span data-ttu-id="4d95f-122">下圖說明常見的工作流程，用於管理和使用安全性與合規性中心以及進階電子文件探索中的電子文件探索案例。</span><span class="sxs-lookup"><span data-stu-id="4d95f-122">The following diagram illustrates the common workflow for managing and using eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span> 
  
![圖表會顯示設定中四個階段的 Office 365 進階電子文件探索工作流程，包括設定使用者和案例、識別案例資料、匯出及處理，接著是分析並匯出至本機電腦的階段。](media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
<span data-ttu-id="4d95f-p105">此設定一節說明工作流程中的前四個步驟。如需工作流程中其他步驟的說明，請參閱下列資訊。</span><span class="sxs-lookup"><span data-stu-id="4d95f-p105">This setup section describes the first four steps in the workflow. For a description of the other steps in the workflow, see the following.</span></span>
  
## <a name="analyze"></a><span data-ttu-id="4d95f-126">分析</span><span class="sxs-lookup"><span data-stu-id="4d95f-126">Analyze</span></span>

<span data-ttu-id="4d95f-p106">[分析案例資料](analyze-case-data-with-advanced-ediscovery.md) 透過各種參數識別並組織檔案、啟用佈景主題的使用，以及顯示結果。使用者可以自訂分析功能，以便實現增加的結果。</span><span class="sxs-lookup"><span data-stu-id="4d95f-p106">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results. Analyze functionality can be customized by the user in order to achieve enhanced results.</span></span> 
  
## <a name="relevance-setup-and-relevance"></a><span data-ttu-id="4d95f-129">相關性設定和相關性</span><span class="sxs-lookup"><span data-stu-id="4d95f-129">Relevance Setup and Relevance</span></span>

<span data-ttu-id="4d95f-p107">[相關性設定](manage-relevance-setup-in-advanced-ediscovery.md)和[使用相關性模組](use-relevance-in-advanced-ediscovery.md) 根據隨機檔案範例啟用評估和相關性訓練，並使用它們將決策套用至預測性編碼程序。監視程序的統計有效性時，計算並顯示過渡結果。顯示結果以便於做出檢閱決策。</span><span class="sxs-lookup"><span data-stu-id="4d95f-p107">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process. Calculates and displays interim results while monitoring statistical validity of the process. Displays the results to facilitate in making review decisions.</span></span> 
  
## <a name="export"></a><span data-ttu-id="4d95f-133">匯出</span><span class="sxs-lookup"><span data-stu-id="4d95f-133">Export</span></span>

<span data-ttu-id="4d95f-134">[匯出案例資料](export-case-data-in-advanced-ediscovery.md) 可讓您匯出進階電子文件探索內容和結果，進行外部檢閱。</span><span class="sxs-lookup"><span data-stu-id="4d95f-134">[Exporting case data](export-case-data-in-advanced-ediscovery.md) Enables the exporting of Advanced eDiscovery content and results for external review.</span></span> 
  
## <a name="report"></a><span data-ttu-id="4d95f-135">報告</span><span class="sxs-lookup"><span data-stu-id="4d95f-135">Report</span></span>

<span data-ttu-id="4d95f-136">[執行報告](run-reports-in-advanced-ediscovery.md) 可讓您產生選取的報告，其與進階電子文件探索處理相關。</span><span class="sxs-lookup"><span data-stu-id="4d95f-136">[Running reports](run-reports-in-advanced-ediscovery.md) Enables the generation of selected reports related to Advanced eDiscovery processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4d95f-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4d95f-137">See also</span></span>

[<span data-ttu-id="4d95f-138">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="4d95f-138">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="4d95f-139">設定使用者和案例</span><span class="sxs-lookup"><span data-stu-id="4d95f-139">Setting up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4d95f-140">準備安裝</span><span class="sxs-lookup"><span data-stu-id="4d95f-140">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)

