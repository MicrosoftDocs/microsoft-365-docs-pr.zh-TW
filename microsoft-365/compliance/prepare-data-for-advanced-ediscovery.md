---
title: 準備資料以供 Office 365 進階電子文件探索
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
description: '了解如何使用 Microsoft 365 安全性&amp;合規性中心，以準備與 Office 365 進階電子文件探索分析的 Office 365 的資料。 '
ms.openlocfilehash: 6407b6f2a2bbe9bc69842057232ec01569ef64c8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597760"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a><span data-ttu-id="5b1bc-103">準備資料以供 Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="5b1bc-103">Prepare data for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="5b1bc-104">本主題說明如何載入至進階電子文件中的案例中的內容搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-104">This topic describes how to load the results of a Content Search in to a case in Advanced eDiscovery.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5b1bc-105">當我們繼續投入在較新版本的進階電子文件中，我們已宣佈淘汰網站的 Office 365 進階電子文件探索 (也稱為*進階電子文件 v1.0*)。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Office 365 Advanced eDiscovery (also known as *Advanced eDiscovery v1.0*).</span></span> <span data-ttu-id="5b1bc-106">如果您仍在使用進階電子文件 v1.0，請轉換至[進階電子文件 v2.0](overview-ediscovery-20.md) （也就是*在 Microsoft 365 進階電子文件方案*） 儘速。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="5b1bc-107">進階電子文件探索 2.0 包含進階電子文件 v1.0 中找到的類似功能，但管理、 通訊管理及檢閱設定，也提供了許多新功能，例如 custodian。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="5b1bc-108">若要深入了解的進階電子文件 v1.0 淘汰網站，請參閱[退休的舊版電子文件探索工具](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span>  
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a><span data-ttu-id="5b1bc-109">步驟 1： 準備 Office 365 資料以供進階電子文件</span><span class="sxs-lookup"><span data-stu-id="5b1bc-109">Step 1: Prepare Office 365 data for Advanced eDiscovery</span></span>

<span data-ttu-id="5b1bc-110">若要分析資料的進階電子文件，您可以使用您執行 Microsoft 365 安全性中的內容搜尋的結果&amp;合規性中心 (Microsoft 365 安全性中的 [**內容搜尋**] 頁面上列出&amp;合規性中心) 或 eDiscovery 案例相關聯的搜尋 (安全性 [ **eDiscovery** ] 頁面上列出&amp;合規性中心)。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-110">To analyze data with Advanced eDiscovery, you can use the results of a Content Search that you run in the Microsoft 365 Security &amp; Compliance Center (listed on the **Content search** page in the Microsoft 365 Security &amp; Compliance Center) or a search associated with an eDiscovery case (listed on the **eDiscovery** page in the Security &amp; Compliance Center).</span></span> 
  
<span data-ttu-id="5b1bc-111">如需準備進階 eDiscovery 中分析的搜尋結果詳細步驟，請參閱[準備 Office 365 進階電子文件探索的搜尋結果](prepare-search-results-for-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-111">For the detailed steps on preparing search results for analysis in Advanced eDiscovery, see [Prepare search results for Office 365 Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b1bc-112">如果您有 Office 365 外部資料，並且想要匯入 Office 365，以便您可以準備和分析的進階電子文件，請參閱[ Overview of 匯入 PST 檔案複製到 Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) and [Office 365 中的封存協力廠商資料](https://go.microsoft.com/fwlink/p/?linkid=716918)。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-112">If you have data outside of Office 365 and want to import it to Office 365 so that you can prepare and analyze it in Advanced eDiscovery, a see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) and [Archiving third-party data in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).</span></span> 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a><span data-ttu-id="5b1bc-113">步驟 2： 負載搜尋結果中資料至進階電子文件中的案例</span><span class="sxs-lookup"><span data-stu-id="5b1bc-113">Step 2: Load search result data in to a case in Advanced eDiscovery</span></span>

<span data-ttu-id="5b1bc-114">您準備好的搜尋結果中的安全性之後&amp;進行分析的合規性中心下, 一步是載入至進階電子文件中的案例的搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-114">After you prepare the search results in the Security &amp; Compliance Center for analysis, the next step is to load the search results in to a case in Advanced eDiscovery.</span></span> <span data-ttu-id="5b1bc-115">如需詳細資訊，請參閱[執行處理序模組](run-the-process-module-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-115">For more detailed information, see [Run the Process module](run-the-process-module-in-advanced-ediscovery.md).</span></span>
  
1. <span data-ttu-id="5b1bc-116">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-116">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="5b1bc-117">使用公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-117">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="5b1bc-118">在安全性與合規性中心，按一下 [搜尋和調查]\*\*\*\* \> [電子文件探索]\*\*\*\*，來顯示貴組織中的案例清單。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-118">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
4. <span data-ttu-id="5b1bc-119">您想要將資料載入在進階電子文件中的案例旁邊，按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-119">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
5. <span data-ttu-id="5b1bc-120">在案例的 [首頁]\*\*\*\* 頁面上，按一下 [進階電子文件探索]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-120">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![按一下切換以開啟 [進階電子文件中的 [大小寫的進階 ediscovery](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="5b1bc-122">**連線至進階電子文件**會顯示進度列。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-122">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="5b1bc-123">當您已連線至進階電子文件時，在這種情況的 [設定] 頁面上會顯示容器的清單。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-123">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![這種情況會顯示在進階電子文件](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="5b1bc-125">這些容器代表您準備好在步驟 1 中的進階 eDiscovery 中分析的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-125">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="5b1bc-126">附註容器的名稱中安全性的案例有同名的內容搜尋&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-126">Note that the name of the container has the same name as the Content Search in the case in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="5b1bc-127">在清單容器是您備妥。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-127">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="5b1bc-128">如果不同的使用者準備進階電子文件中的搜尋結果，將不會在清單中包含對應的容器。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-128">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
6. <span data-ttu-id="5b1bc-129">若要從容器中的搜尋結果資料載入至進階電子文件中的案例中，選取的容器，然後按一下 [**程序**。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-129">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
<span data-ttu-id="5b1bc-130">從安全性搜尋結果之後&amp;合規性中心會新增至進階電子文件探索中的情況下一步是在進階電子文件中使用的工具來分析並 cull 與案件相關的資料。</span><span class="sxs-lookup"><span data-stu-id="5b1bc-130">After the search results from the Security &amp; Compliance Center are added to the case in Advanced eDiscovery, the next step is to use the tools in Advanced eDiscovery to analyze and cull the data that's relevant to the case.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5b1bc-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5b1bc-131">See also</span></span>

[<span data-ttu-id="5b1bc-132">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="5b1bc-132">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="5b1bc-133">設定使用者和案例</span><span class="sxs-lookup"><span data-stu-id="5b1bc-133">Set up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5b1bc-134">分析案例資料</span><span class="sxs-lookup"><span data-stu-id="5b1bc-134">Analyzing case data</span></span>](analyze-case-data-with-advanced-ediscovery.md)
  
[<span data-ttu-id="5b1bc-135">管理相關性設定</span><span class="sxs-lookup"><span data-stu-id="5b1bc-135">Managing Relevance setup</span></span>](manage-relevance-setup-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5b1bc-136">使用相關性模組</span><span class="sxs-lookup"><span data-stu-id="5b1bc-136">Using the Relevance module</span></span>](use-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5b1bc-137">匯出案例資料</span><span class="sxs-lookup"><span data-stu-id="5b1bc-137">Exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)

