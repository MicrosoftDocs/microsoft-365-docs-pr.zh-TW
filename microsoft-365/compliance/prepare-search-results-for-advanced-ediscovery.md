---
title: 準備進階電子文件探索的搜尋結果
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: 瞭解如何在安全性 & 規範中心準備內容搜尋的結果，以利用高級 eDiscovery 工具進行進一步的分析。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b403987c39d1ddcc1f22fd0abbeba85e60591414
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358565"
---
# <a name="prepare-search-results-for-advanced-ediscovery-classic"></a><span data-ttu-id="79893-103">準備進階電子文件探索 (傳統版) 的搜尋結果</span><span class="sxs-lookup"><span data-stu-id="79893-103">Prepare search results for Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79893-104">隨著我們繼續投資於更新版本的進階電子文件探索，我們即將宣布停用進階文件探索 (也稱為*進階電子文件探索 (傳統版)* 或*進階文件探索 1.0 版*)。</span><span class="sxs-lookup"><span data-stu-id="79893-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="79893-105">如果您仍在使用進階電子文件探索 1.0 版，請盡快轉換為[進階電子文件探索 2.0 版](overview-ediscovery-20.md) (*在Microsoft 365 中也稱為進階電子文件探索解決方案*)。</span><span class="sxs-lookup"><span data-stu-id="79893-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="79893-106">進階電子文件探索 2.0 中包含可在進階電子文件探索 1.0 版中找到的類似功能，但同時也提供許多新的功能，例如監管人管理、通訊管理和檢閱集。</span><span class="sxs-lookup"><span data-stu-id="79893-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="79893-107">若要深入了解進階電子文件探索 1.0 版的停用，請參閱[舊版電子文件探索工具的停用](legacy-ediscovery-retirement.md#advanced-ediscovery-v10) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="79893-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="79893-108">在安全性 & 合規性中心與 eDiscovery 案例相關聯的搜尋順利執行後，您可以使用高級 eDiscovery 準備進一步分析的搜尋結果，這樣可讓您分析大型的非結構化資料集，並減少與法律案例相關的資料量。</span><span class="sxs-lookup"><span data-stu-id="79893-108">After a search that's associated with an eDiscovery case in the Security & Compliance Center is successfully run, you can prepare the search results for further analysis with Advanced eDiscovery, which lets you analyze large, unstructured data sets and reduce the amount of data that's relevant to a legal case.</span></span> <span data-ttu-id="79893-109">Advanced eDiscovery 的功能包括：</span><span class="sxs-lookup"><span data-stu-id="79893-109">Advanced eDiscovery features include:</span></span>
  
- <span data-ttu-id="79893-110">**光學字元辨識** -當您準備高級 ediscovery 的搜尋結果時，光學字元辨識 (OCR) 功能會自動從影像析取文字，並將其包含在載入至高級 eDiscovery 以進行分析的搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="79893-110">**Optical character recognition** - When you prepare search results for Advanced eDiscovery, optical character recognition (OCR) functionality automatically extracts text from images, and includes this with the search results that are loaded in to Advanced eDiscovery for analysis.</span></span> <span data-ttu-id="79893-111">疏鬆檔案、電子郵件附件和內嵌的圖像支援 OCR。</span><span class="sxs-lookup"><span data-stu-id="79893-111">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="79893-112">這可讓您將高級 eDiscovery (的文字分析功能，套用至近乎重複的電子郵件執行緒、主題及預測編碼) ，以影像檔案中的文字內容。</span><span class="sxs-lookup"><span data-stu-id="79893-112">This allows you to apply the text analytic capabilities of Advanced eDiscovery (near-duplicates, email threading, themes, and predictive coding) to the text content in image files.</span></span> <span data-ttu-id="79893-113">「高級 eDiscovery OCR」支援下列圖像檔案格式：</span><span class="sxs-lookup"><span data-stu-id="79893-113">Advanced eDiscovery OCR supports the following formats for image files:</span></span>

    - <span data-ttu-id="79893-114">GIF</span><span class="sxs-lookup"><span data-stu-id="79893-114">GIF</span></span>
    - <span data-ttu-id="79893-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="79893-115">JPEG</span></span>
    - <span data-ttu-id="79893-116">Jpg</span><span class="sxs-lookup"><span data-stu-id="79893-116">JPG</span></span>
    - <span data-ttu-id="79893-117">PNG</span><span class="sxs-lookup"><span data-stu-id="79893-117">PNG</span></span>
    - <span data-ttu-id="79893-118">TIFF</span><span class="sxs-lookup"><span data-stu-id="79893-118">TIFF</span></span>
    
- <span data-ttu-id="79893-119">**近乎重複的偵測** -可讓您更有效率地組織資料評審，所以一個人會檢查類似檔的群組。</span><span class="sxs-lookup"><span data-stu-id="79893-119">**Near-duplicate detection** - Lets you structure your data review more efficiently, so one person reviews a group of similar documents.</span></span> <span data-ttu-id="79893-120">這有助於防止多個檢閱者查看相同檔的不同版本。</span><span class="sxs-lookup"><span data-stu-id="79893-120">This helps prevent multiple reviewers from having to view different versions of the same document.</span></span> 
    
- <span data-ttu-id="79893-121">**電子郵件執行緒** -協助您識別電子郵件線索中的唯一郵件，這樣您就只會專注于每封郵件中的新資訊。</span><span class="sxs-lookup"><span data-stu-id="79893-121">**Email threading** - Helps you identify the unique messages in an email thread so you can focus on only the new information in each message.</span></span> <span data-ttu-id="79893-122">在電子郵件線索中，第二封郵件會包含第一封郵件。</span><span class="sxs-lookup"><span data-stu-id="79893-122">In an email thread, the second message contains the first message.</span></span> <span data-ttu-id="79893-123">同樣地，後續郵件也會包含所有先前的郵件。</span><span class="sxs-lookup"><span data-stu-id="79893-123">Likewise, later messages contain all the previous messages.</span></span> <span data-ttu-id="79893-124">電子郵件執行緒功能可移除整個電子郵件執行緒中的每封郵件。</span><span class="sxs-lookup"><span data-stu-id="79893-124">Email threading removes the need to review every message in its entirety in an email thread.</span></span> 
    
- <span data-ttu-id="79893-125">**主題** -除了關鍵字搜尋統計資料之外，可協助您取得資料的重要洞察力。</span><span class="sxs-lookup"><span data-stu-id="79893-125">**Themes** - Help you get valuable insight about your data beyond just keyword search statistics.</span></span> <span data-ttu-id="79893-126">主題協助調查：將相關的檔分組，讓您在內容中查看檔。</span><span class="sxs-lookup"><span data-stu-id="79893-126">Themes help investigations by grouping related documents so you can look at the documents in context.</span></span> <span data-ttu-id="79893-127">使用主題時，您可以查看一組檔的相關主題、判斷任何重迭的各項，然後識別相關資料的橫截面。</span><span class="sxs-lookup"><span data-stu-id="79893-127">When using themes, you can view the related themes for a set of documents, determine any overlap, and then identify cross-sections of related data.</span></span> 
    
- <span data-ttu-id="79893-128">**預測編碼** -可讓您針對您所要的專案，對系統進行訓練，其方式是讓您 (決定是否在一小部分檔上) 相關事項。</span><span class="sxs-lookup"><span data-stu-id="79893-128">**Predictive coding** - Lets you train the system on what you're looking for, by allowing you to make decisions (about whether something is relevant or not) on a small set of documents.</span></span> <span data-ttu-id="79893-129">[！注意] 高級 eDiscovery 會根據您在分析資料集中的所有檔時的指導方針) 套用該教學 (。</span><span class="sxs-lookup"><span data-stu-id="79893-129">Advanced eDiscovery then applies that learning (based on your guidance) when analyzing all of the documents in the data set.</span></span> <span data-ttu-id="79893-130">根據這種教學，「高級 eDiscovery」會提供相關性排名，讓您根據哪一種檔最可能與案例相關的檔決定要檢查的檔。</span><span class="sxs-lookup"><span data-stu-id="79893-130">Based on that learning, Advanced eDiscovery provides a relevance ranking so you can decide which documents to review based on what document are the most likely to be relevant to the case.</span></span> 
    
- <span data-ttu-id="79893-131">**匯出資料以供審閱應用程式**  -您可以在完成分析並減少資料集後，從 Advanced EDiscovery 和 Microsoft 365 匯出資料。</span><span class="sxs-lookup"><span data-stu-id="79893-131">**Exporting data for review applications**  - You can export data from Advanced eDiscovery and Microsoft 365 after you've completed your analysis and reduced the data set.</span></span> <span data-ttu-id="79893-132">匯出套件包含 CSV 檔案，其中包含匯出內容和分析中繼資料中的屬性。</span><span class="sxs-lookup"><span data-stu-id="79893-132">The export package includes a CSV file that contains the properties from the exported content and analytics metadata.</span></span> <span data-ttu-id="79893-133">然後，您可以將此匯出套件匯入 eDiscovery 考核應用程式。</span><span class="sxs-lookup"><span data-stu-id="79893-133">This export package can then be imported to an eDiscovery review application.</span></span> 
    
## <a name="get-licenses-and-permissions"></a><span data-ttu-id="79893-134">取得授權和許可權</span><span class="sxs-lookup"><span data-stu-id="79893-134">Get licenses and permissions</span></span>

- <span data-ttu-id="79893-135">若要使用「高級 eDiscovery」分析使用者的資料，使用者 (必須指派 Office 365 E5 授權的資料) 的管理員。</span><span class="sxs-lookup"><span data-stu-id="79893-135">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="79893-136">或者，您可以將高級 eDiscovery 獨立授權指派給使用 Office 365 E1 或 E3 授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="79893-136">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="79893-137">獲指派案例的系統管理員和合規性監察官，以及使用高級 eDiscovery 來分析資料，不需要 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="79893-137">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="79893-138">您必須是 eDiscovery 管理員或安全性 & 合規性中心的 eDiscovery 管理員，才能準備高級 eDiscovery 的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="79893-138">You have to be an eDiscovery Manager or an eDiscovery Administrator in the Security & Compliance Center to prepare search results for Advanced eDiscovery.</span></span> <span data-ttu-id="79893-139">eDiscovery 管理員為 eDiscovery 管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="79893-139">An eDiscovery Manager is a member of the eDiscovery Manager role group.</span></span> <span data-ttu-id="79893-140">eDiscovery 系統管理員也是 eDiscovery 管理員角色群組的成員，但已獲指派其他 eDiscovery 權限。</span><span class="sxs-lookup"><span data-stu-id="79893-140">An eDiscovery Administrator is also member of the eDiscovery Manager role group, but has been assigned additional eDiscovery privileges.</span></span> <span data-ttu-id="79893-141">如需指派 eDiscovery 系統管理員許可權的相關指示，請參閱 [eDiscovery 案例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的步驟1。</span><span class="sxs-lookup"><span data-stu-id="79893-141">For instructions about assigning eDiscovery Administrator permissions, see Step 1 in [eDiscovery cases](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a><span data-ttu-id="79893-142">步驟1：準備高級 eDiscovery 的搜尋結果</span><span class="sxs-lookup"><span data-stu-id="79893-142">Step 1: Prepare search results for Advanced eDiscovery</span></span>

<span data-ttu-id="79893-143">您可以準備與 eDiscovery 案例相關聯之搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="79893-143">You can prepare the results of a search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="79893-144">當您準備高級 eDiscovery 的搜尋結果時，會將資料上傳並暫時儲存在 Microsoft 雲端的唯一 Windows Azure 儲存體區域中。</span><span class="sxs-lookup"><span data-stu-id="79893-144">When you prepare search results for Advanced eDiscovery, the data is uploaded and temporarily stored in a unique Windows Azure storage area in the Microsoft cloud.</span></span> <span data-ttu-id="79893-145">此時，OCR 功能會從搜尋結果中的影像提取文字。</span><span class="sxs-lookup"><span data-stu-id="79893-145">It's at this point that the OCR functionality extracts text from images in the search results.</span></span> <span data-ttu-id="79893-146">在 [步驟 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery)中，會在高級 eDiscovery 中載入此文字和其他搜尋結果資料至案例。</span><span class="sxs-lookup"><span data-stu-id="79893-146">In [Step 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), this text and the other search results data is loaded in to the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="79893-147">在 [安全性 & 規範中心] 中，按一下 [ **ediscovery** \> **ediscovery** ] 以顯示組織中案例的清單。</span><span class="sxs-lookup"><span data-stu-id="79893-147">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="79893-148">在 [高級 eDiscovery] 中，按一下您要準備搜尋結果以進行分析的案例旁邊的 [ **開啟** ]。</span><span class="sxs-lookup"><span data-stu-id="79893-148">Click **Open** next to the case that you want to prepare search results for analysis in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="79893-149">在案例的 **首頁** 上，按一下 [ **搜尋**]，然後選取搜尋。</span><span class="sxs-lookup"><span data-stu-id="79893-149">On the **Home** page for the case, click **Search**, and then select the search.</span></span>
    
4. <span data-ttu-id="79893-150">在詳細資料窗格的 [ **分析具有高級 eDiscovery 的結果**] 底下，按一下 [ **準備用於分析的結果**]。</span><span class="sxs-lookup"><span data-stu-id="79893-150">In the details pane, under **Analyze results with Advanced eDiscovery**, click **Prepare results for analysis**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="79893-151">如果搜尋的結果是早於 7 天前，則會提示您更新搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="79893-151">If the search results are older than 7 days, you will be prompted to update the search results.</span></span> 
  
5. <span data-ttu-id="79893-152">在**準備供分析的結果**的頁面上，執行下列動作︰ </span><span class="sxs-lookup"><span data-stu-id="79893-152">On the **Prepare results for analysis** page, do the following:</span></span> 
    
    - <span data-ttu-id="79893-153">選擇準備好編制索引的專案、索引及未編制索引的專案，或只在高級 eDiscovery 中分析未編制索引的專案。</span><span class="sxs-lookup"><span data-stu-id="79893-153">Choose to prepare indexed items, indexed and unindexed items, or only unindexed items for analysis in Advanced eDiscovery.</span></span>
    
    - <span data-ttu-id="79893-154">選擇是否要在符合搜尋準則的 SharePoint 上，包含找到的所有檔版本。</span><span class="sxs-lookup"><span data-stu-id="79893-154">Choose whether to include all versions of documents found on SharePoint that met the search criteria.</span></span> <span data-ttu-id="79893-155">這個選項只在搜尋內容來源包含網站時才會出現。</span><span class="sxs-lookup"><span data-stu-id="79893-155">This option appears only if the content sources for the search includes sites.</span></span>
    
    - <span data-ttu-id="79893-156">指定在準備工作完成時，是否要將通知訊息傳送 (或) 複製到人員，以及在高級 eDiscovery 中處理資料時已準備好。</span><span class="sxs-lookup"><span data-stu-id="79893-156">Specify whether you want a notification message sent (or copied) to a person when the preparation process is completed and the data is ready to be processed in Advanced eDiscovery.</span></span>
    
6. <span data-ttu-id="79893-157">按一下 [準備]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="79893-157">Click **Prepare**.</span></span>
    
    <span data-ttu-id="79893-158">搜尋結果是準備好使用高級 eDiscovery 進行分析。</span><span class="sxs-lookup"><span data-stu-id="79893-158">The search results are prepared for analysis with Advanced eDiscovery.</span></span>
    
7. <span data-ttu-id="79893-159">在詳細資料窗格中，按一下 [ **檢查準備狀態** ] 以顯示準備程式的資訊。</span><span class="sxs-lookup"><span data-stu-id="79893-159">In the details pane, click **Check preparation status** to display information about the preparation process.</span></span> <span data-ttu-id="79893-160">完成準備程式後，您可以移至高級 eDiscovery 中的案例處理資料，以進行分析。</span><span class="sxs-lookup"><span data-stu-id="79893-160">When the preparation process is finished, you can go to the case in Advanced eDiscovery to process the data for analysis.</span></span> 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a><span data-ttu-id="79893-161">步驟2：將搜尋結果資料新增至高級 eDiscovery 中的案例</span><span class="sxs-lookup"><span data-stu-id="79893-161">Step 2: Add the search results data to the case in Advanced eDiscovery</span></span>
<span data-ttu-id="79893-162"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="79893-162"><a name="step2"> </a></span></span>

<span data-ttu-id="79893-163">準備完成後，下一步是移至 [Advanced eDiscovery] 並載入搜尋結果資料 (已上傳至 Microsoft 雲端中的 Azure 儲存體區域 ) 高級 eDiscovery 中的案例。</span><span class="sxs-lookup"><span data-stu-id="79893-163">When the preparation is finished, the next step is to go to Advanced eDiscovery and load the search results data (which have been uploaded to an Azure storage area in the Microsoft cloud ) to the case in Advanced eDiscovery.</span></span> <span data-ttu-id="79893-164">如先前所述，若要存取高級 eDiscovery，您必須是 Security & 合規性中心的 eDiscovery 系統管理員或高級 eDiscovery 中的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="79893-164">As previously explained, to access Advanced eDiscovery you have to be an eDiscovery Administrator in the Security & Compliance Center or an administrator in Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79893-165">從安全性 & 合規性中心，將資料新增至高級 eDiscovery 的情況所需的時間，視 eDiscovery 搜尋的結果大小而定。</span><span class="sxs-lookup"><span data-stu-id="79893-165">The time it takes for the data from the Security & Compliance Center to be available to add to a case in Advanced eDiscovery varies, depending on the size of the results from the eDiscovery search.</span></span> 
  
1. <span data-ttu-id="79893-166">在 [安全性 & 規範中心] 中，按一下 [ **ediscovery** \> **ediscovery** ] 以顯示組織中案例的清單。</span><span class="sxs-lookup"><span data-stu-id="79893-166">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="79893-167">在 [高級 eDiscovery] 中，按一下您想要在其中載入資料之案例旁邊的 [ **開啟** ]。</span><span class="sxs-lookup"><span data-stu-id="79893-167">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="79893-168">在案例的 [首頁]\*\*\*\* 頁面上，按一下 [切換至進階電子文件探索]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="79893-168">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span> 
    
    ![按一下 [切換至高級 eDiscovery]，以在 [高級 eDiscovery] 中開啟案例。](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="79893-170">隨即會顯示 [連線 **至高級 eDiscovery** ] 進度列。</span><span class="sxs-lookup"><span data-stu-id="79893-170">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="79893-171">當您連線至「高級 eDiscovery」時，容器清單會顯示在案例的 [設定] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="79893-171">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![案例會顯示在高級 eDiscovery](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="79893-173">這些容器代表您在步驟1的高級 eDiscovery 中準備分析的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="79893-173">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="79893-174">請注意，在安全性 & 合規性中心的情況下，容器的名稱與搜尋的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="79893-174">Note that the name of the container has the same name as the search in the case in the Security & Compliance Center.</span></span> <span data-ttu-id="79893-175">清單中的容器是您準備的容器。</span><span class="sxs-lookup"><span data-stu-id="79893-175">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="79893-176">如果不同的使用者已為高級 eDiscovery 準備好搜尋結果，對應的容器將不會包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="79893-176">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
4. <span data-ttu-id="79893-177">若要在高級 eDiscovery 的案例中從容器中載入搜尋結果資料，請選取容器，然後按一下 [ **處理**]。</span><span class="sxs-lookup"><span data-stu-id="79893-177">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="79893-178">後續步驟</span><span class="sxs-lookup"><span data-stu-id="79893-178">Next steps</span></span>

<span data-ttu-id="79893-179">在將 eDiscovery 搜尋的結果新增至案例之後，下一步是使用「高級 eDiscovery」工具來分析資料，並識別回應特定法律案例的內容。</span><span class="sxs-lookup"><span data-stu-id="79893-179">After the results of an eDiscovery search are added to a case, the next step is to use the Advanced eDiscovery tools to analyze the data and identify the content that's responsive to a specific legal case.</span></span> <span data-ttu-id="79893-180">如需使用高級 eDiscovery 的詳細資訊，請參閱 [Advanced ediscovery (傳統) ](office-365-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="79893-180">For information about using Advanced eDiscovery, see [Advanced eDiscovery (classic)](office-365-advanced-ediscovery.md).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="79893-181">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="79893-181">More information</span></span>

<span data-ttu-id="79893-182">當您準備用於高級 eDiscovery 的分析時，搜尋結果中所包含的任何 RMS 加密電子郵件都會解密。</span><span class="sxs-lookup"><span data-stu-id="79893-182">Any RMS-encrypted email messages that are included in the search results will be decrypted when you prepare them for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="79893-183">預設會為 eDiscovery 管理員角色群組的成員啟用此解密功能。</span><span class="sxs-lookup"><span data-stu-id="79893-183">This decryption capability is enabled by default for members of the eDiscovery Manager role group.</span></span> <span data-ttu-id="79893-184">這是因為 RMS 解密管理角色會指派給此角色群組。</span><span class="sxs-lookup"><span data-stu-id="79893-184">This is because the RMS Decrypt management role is assigned to this role group.</span></span> <span data-ttu-id="79893-185">請記住下列有關解密電子郵件訊息的事項：</span><span class="sxs-lookup"><span data-stu-id="79893-185">Keep the following things in mind about decrypting email messages:</span></span>
  
- <span data-ttu-id="79893-186">目前，此解密功能不包括 SharePoint 和商務網站 OneDrive 的加密內容。</span><span class="sxs-lookup"><span data-stu-id="79893-186">Currently, this decryption capability doesn't include encrypted content from SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="79893-187">匯出時，只會解密 RMS 加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="79893-187">Only RMS-encrypted email messages will be decrypted when you export them.</span></span>
    
- <span data-ttu-id="79893-188">如果 RMS 加密的電子郵件中有附件 (例如檔或其他電子郵件訊息) 也加密，則只會解密最上層的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="79893-188">If an RMS-encrypted email message has an attachment (such as a document or another email message) that's also encrypted, only the top-level email message will be decrypted.</span></span>
    
- <span data-ttu-id="79893-189">如果您需要在準備高級 eDiscovery 的搜尋結果時，防止某人解密 RMS 加密的郵件，您必須建立自訂角色群組 (，方法是複製內建的 eDiscovery 管理員角色群組) 然後從自訂角色群組中移除 RMS 解密管理角色。</span><span class="sxs-lookup"><span data-stu-id="79893-189">If you need to prevent someone from decrypting RMS-encrypted messages when preparing search results for analysis in Advanced eDiscovery, you'll have to create a custom role group (by copying the built-in eDiscovery Manager role group) and then remove the RMS Decrypt management role from the custom role group.</span></span> <span data-ttu-id="79893-190">然後將您不想要將郵件解密的人員新增為自訂角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="79893-190">Then add the person who you don't want to decrypt messages as a member of the custom role group.</span></span>
