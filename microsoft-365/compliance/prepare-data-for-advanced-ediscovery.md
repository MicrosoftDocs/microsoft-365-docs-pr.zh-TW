---
title: 準備進階電子文件探索的資料
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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: 瞭解如何使用安全性 &amp; 與合規性中心，準備要使用高級 eDiscovery 進行分析的資料。
ms.openlocfilehash: 3c9d237a3a9c04a443730143998324a7831f2998
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936328"
---
# <a name="prepare-data-for-advanced-ediscovery-classic"></a><span data-ttu-id="f339e-103">準備資料以供高級 eDiscovery （經典）</span><span class="sxs-lookup"><span data-stu-id="f339e-103">Prepare data for Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="f339e-104">本主題說明如何在高級 eDiscovery （經典）中，將內容搜尋的結果載入至案例。</span><span class="sxs-lookup"><span data-stu-id="f339e-104">This topic describes how to load the results of a Content Search in to a case in Advanced eDiscovery (classic).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f339e-105">隨著我們繼續投資於更新版本的進階電子文件探索，我們即將宣布停用進階文件探索 (也稱為*進階電子文件探索 (傳統版)* 或*進階文件探索 1.0 版*)。</span><span class="sxs-lookup"><span data-stu-id="f339e-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="f339e-106">如果您仍在使用進階電子文件探索 1.0 版，請盡快轉換為[進階電子文件探索 2.0 版](overview-ediscovery-20.md) (*在Microsoft 365 中也稱為進階電子文件探索解決方案*)。</span><span class="sxs-lookup"><span data-stu-id="f339e-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="f339e-107">進階電子文件探索 2.0 中包含可在進階電子文件探索 1.0 版中找到的類似功能，但同時也提供許多新的功能，例如監管人管理、通訊管理和檢閱集。</span><span class="sxs-lookup"><span data-stu-id="f339e-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="f339e-108">若要深入了解進階電子文件探索 1.0 版的停用，請參閱[舊版電子文件探索工具的停用](legacy-ediscovery-retirement.md#advanced-ediscovery-v10) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="f339e-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span>  
  
## <a name="step-1-prepare-data-for-advanced-ediscovery"></a><span data-ttu-id="f339e-109">步驟1：準備用於高級電子檔探索的資料</span><span class="sxs-lookup"><span data-stu-id="f339e-109">Step 1: Prepare data for Advanced eDiscovery</span></span>

<span data-ttu-id="f339e-110">若要使用 Advanced eDiscovery 來分析資料，您可以使用 Microsoft 365 安全性與合規性中心中所執行的內容搜尋結果 &amp; （列于 microsoft 365 安全性與合規性中心的 [**內容搜尋**] 頁面上 &amp; ），或與 eDiscovery 案例相關聯的搜尋（列在 [安全性與規範中心] 中的 [ **ediscovery** ] 頁面上 &amp; ）。</span><span class="sxs-lookup"><span data-stu-id="f339e-110">To analyze data with Advanced eDiscovery, you can use the results of a Content Search that you run in the Microsoft 365 Security &amp; Compliance Center (listed on the **Content search** page in the Microsoft 365 Security &amp; Compliance Center) or a search associated with an eDiscovery case (listed on the **eDiscovery** page in the Security &amp; Compliance Center).</span></span> 
  
<span data-ttu-id="f339e-111">如需在高級 eDiscovery 中準備搜尋結果以進行分析的詳細步驟，請參閱[準備高級 ediscovery 的搜尋結果](prepare-search-results-for-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="f339e-111">For the detailed steps on preparing search results for analysis in Advanced eDiscovery, see [Prepare search results for Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f339e-112">如果您有超出 Microsoft 365 的資料，且想要將資料匯入至 Microsoft 365，以便在高級 eDiscovery 中準備及分析它，請參閱將 PST 檔案匯[入至 Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365)並封存[協力廠商資料](https://www.microsoft.com/?ref=go)的總覽。</span><span class="sxs-lookup"><span data-stu-id="f339e-112">If you have data outside of Microsoft 365 and want to import it to Microsoft 365 so that you can prepare and analyze it in Advanced eDiscovery, a see [Overview of importing PST files to Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365) and [Archiving third-party data](https://www.microsoft.com/?ref=go).</span></span> 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a><span data-ttu-id="f339e-113">步驟2：在高級 eDiscovery 中將搜尋結果資料載入到案例中</span><span class="sxs-lookup"><span data-stu-id="f339e-113">Step 2: Load search result data in to a case in Advanced eDiscovery</span></span>

<span data-ttu-id="f339e-114">在安全性與規範中心中準備好搜尋結果 &amp; 以進行分析之後，下一步是在高級 eDiscovery 中的案例中載入搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="f339e-114">After you prepare the search results in the Security &amp; Compliance Center for analysis, the next step is to load the search results in to a case in Advanced eDiscovery.</span></span> <span data-ttu-id="f339e-115">如需詳細資訊，請參閱[執行 Process module](run-the-process-module-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="f339e-115">For more detailed information, see [Run the Process module](run-the-process-module-in-advanced-ediscovery.md).</span></span>
  
1. <span data-ttu-id="f339e-116">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="f339e-116">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="f339e-117">使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="f339e-117">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="f339e-118">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="f339e-118">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
4. <span data-ttu-id="f339e-119">在 [高級 eDiscovery] 中，按一下您想要在其中載入資料之案例旁邊的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="f339e-119">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
5. <span data-ttu-id="f339e-120">在案例的 [首頁]\*\*\*\* 頁面上，按一下 [切換至進階電子文件探索]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f339e-120">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span> 
    
    ![按一下 [切換至高級 eDiscovery]，以在 [高級 eDiscovery] 中開啟案例。](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="f339e-122">隨即會顯示 [連線**至高級 eDiscovery** ] 進度列。</span><span class="sxs-lookup"><span data-stu-id="f339e-122">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="f339e-123">當您連線至「高級 eDiscovery」時，容器清單會顯示在案例的 [設定] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="f339e-123">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![案例會顯示在高級 eDiscovery](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="f339e-125">這些容器代表您在步驟1的高級 eDiscovery 中準備分析的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="f339e-125">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="f339e-126">請注意，在安全性與合規性中心的案例中，容器的名稱與內容搜尋的名稱相同 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="f339e-126">Note that the name of the container has the same name as the Content Search in the case in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="f339e-127">清單中的容器是您準備的容器。</span><span class="sxs-lookup"><span data-stu-id="f339e-127">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="f339e-128">如果不同的使用者已為高級 eDiscovery 準備好搜尋結果，對應的容器將不會包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="f339e-128">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
6. <span data-ttu-id="f339e-129">若要在高級 eDiscovery 的案例中從容器中載入搜尋結果資料，請選取容器，然後按一下 [**處理**]。</span><span class="sxs-lookup"><span data-stu-id="f339e-129">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
<span data-ttu-id="f339e-130">在將安全性與 &amp; 合規性中心的搜尋結果新增至高級 ediscovery 的案例之後，下一步是使用高級 ediscovery 中的工具來分析和挑選與案例相關的資料。</span><span class="sxs-lookup"><span data-stu-id="f339e-130">After the search results from the Security &amp; Compliance Center are added to the case in Advanced eDiscovery, the next step is to use the tools in Advanced eDiscovery to analyze and cull the data that's relevant to the case.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f339e-131">請參閱</span><span class="sxs-lookup"><span data-stu-id="f339e-131">See also</span></span>

[<span data-ttu-id="f339e-132">進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="f339e-132">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f339e-133">設定使用者和案例</span><span class="sxs-lookup"><span data-stu-id="f339e-133">Set up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f339e-134">分析案例資料</span><span class="sxs-lookup"><span data-stu-id="f339e-134">Analyzing case data</span></span>](analyze-case-data-with-advanced-ediscovery.md)
  
[<span data-ttu-id="f339e-135">管理相關性設定</span><span class="sxs-lookup"><span data-stu-id="f339e-135">Managing Relevance setup</span></span>](manage-relevance-setup-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f339e-136">使用相關性模組</span><span class="sxs-lookup"><span data-stu-id="f339e-136">Using the Relevance module</span></span>](use-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f339e-137">匯出案例資料</span><span class="sxs-lookup"><span data-stu-id="f339e-137">Exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)

