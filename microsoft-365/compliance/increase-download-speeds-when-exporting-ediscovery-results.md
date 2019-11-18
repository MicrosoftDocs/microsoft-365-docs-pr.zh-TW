---
title: 匯出 eDiscovery 搜尋結果從 Office 365 時，增加的下載速度
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: 了解如何設定 Windows 登錄，以增加資料輸送量，從安全性 & 合規性中心] 及 [進階電子文件探索中 Office 365 下載搜尋結果，並搜尋資料時。
ms.openlocfilehash: f74d164250f9d5b9b8315fe2651d3374457451ed
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38685595"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a><span data-ttu-id="b64b6-103">匯出 eDiscovery 搜尋結果從 Office 365 時，增加的下載速度</span><span class="sxs-lookup"><span data-stu-id="b64b6-103">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>

<span data-ttu-id="b64b6-104">當您使用 Office 365 電子文件探索匯出工具來下載安全性 & 合規性中心的內容搜尋的結果，或從 Office 365 進階電子文件探索下載資料時，此工具會啟動下載資料至您的本機電腦的並行匯出作業數目。</span><span class="sxs-lookup"><span data-stu-id="b64b6-104">When you use the Office 365 eDiscovery Export tool to download the results of a Content Search in the Security & Compliance Center or download data from Office 365 Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer.</span></span> <span data-ttu-id="b64b6-105">根據預設，同時進行的作業數目設為 8 的次數中您要用來下載資料之電腦的核心。</span><span class="sxs-lookup"><span data-stu-id="b64b6-105">By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data.</span></span> <span data-ttu-id="b64b6-106">例如，如果您有雙核心電腦 （亦即一晶片上的兩個管理中心處理單位），同時進行匯出作業的預設數為 16。</span><span class="sxs-lookup"><span data-stu-id="b64b6-106">For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16.</span></span> <span data-ttu-id="b64b6-107">若要增加資料傳輸輸送量並提升並下載程序，您可以藉由使用若要下載搜尋結果的電腦上設定 Windows 登錄設定增加同時進行的作業數目。</span><span class="sxs-lookup"><span data-stu-id="b64b6-107">To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results.</span></span> <span data-ttu-id="b64b6-108">為了提升並下載程序，我們建議您以設定為 24 同時進行的作業開始。</span><span class="sxs-lookup"><span data-stu-id="b64b6-108">To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="b64b6-109">如果您透過低頻寬網路下載搜尋結果，請增加此設定可能會造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="b64b6-109">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact.</span></span> <span data-ttu-id="b64b6-110">或者，您可以增加到超過 24 同時進行的作業 （同時進行的作業的最大數目為 48） 的高頻寬網路中的設定。</span><span class="sxs-lookup"><span data-stu-id="b64b6-110">Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 48).</span></span> <span data-ttu-id="b64b6-111">設定此登錄設定之後，您可能必須變更，以找出最佳的同時進行的作業，為您的環境。</span><span class="sxs-lookup"><span data-stu-id="b64b6-111">After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="b64b6-112">建立登錄設定來匯出資料時變更的同時進行的作業數目</span><span class="sxs-lookup"><span data-stu-id="b64b6-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="b64b6-113">您將搜尋結果下載來自安全 & 與規範中心或進階電子文件中的資料使用的電腦上執行下列程序。</span><span class="sxs-lookup"><span data-stu-id="b64b6-113">Perform the following procedure on the computer that you'll use to download search results from the Security & Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="b64b6-114">如果它已經開啟，請關閉 Office 365 電子文件探索匯出工具。</span><span class="sxs-lookup"><span data-stu-id="b64b6-114">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="b64b6-115">將下列文字儲存到視窗登錄檔案中，使用.reg; 檔名尾碼例如，ConcurrentOperations.reg。</span><span class="sxs-lookup"><span data-stu-id="b64b6-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="b64b6-116">如同先前的說明，我們建議您開始使用 24 同時進行的作業，，，然後變更 [視需要此設定。</span><span class="sxs-lookup"><span data-stu-id="b64b6-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="b64b6-117">在 Windows 檔案總管] 中，按一下或按兩下您在上一個步驟中建立的.reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="b64b6-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="b64b6-118">在 [使用者存取控制] 視窗中，按一下 [ **]** 讓登錄編輯程式中進行的變更。</span><span class="sxs-lookup"><span data-stu-id="b64b6-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="b64b6-119">出現提示時若要繼續，按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="b64b6-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="b64b6-120">登錄編輯程式中會顯示訊息，說明設定已成功新增至登錄。</span><span class="sxs-lookup"><span data-stu-id="b64b6-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="b64b6-121">您可以重複執行步驟 2-5 若要變更的值為`DownloadConcurrency`登錄設定。</span><span class="sxs-lookup"><span data-stu-id="b64b6-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="b64b6-122">在您建立或變更之後`DownloadConcurrency`登錄設定，請務必建立新的匯出工作或重新啟動現有匯出作業的搜尋結果或您想要下載的資料。</span><span class="sxs-lookup"><span data-stu-id="b64b6-122">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download.</span></span> <span data-ttu-id="b64b6-123">請參閱如需詳細資訊的[詳細資訊](#more-information)一節。</span><span class="sxs-lookup"><span data-stu-id="b64b6-123">See the [More information](#more-information) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="b64b6-124">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b64b6-124">More information</span></span>

- <span data-ttu-id="b64b6-125">新的登錄機碼會建立第一次執行您在此程序中建立的.reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="b64b6-125">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="b64b6-126">然後在`DownloadConcurrency`登錄設定編輯的每當您變更，然後重新執行.reg 編輯檔案。</span><span class="sxs-lookup"><span data-stu-id="b64b6-126">Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="b64b6-127">Office 365 電子文件探索匯出工具會使用[Azure AzCopy 公用程式](https://go.microsoft.com/fwlink/?linkid=849949)來下載搜尋資料，從安全性 & 合規性中心或進階電子文件。</span><span class="sxs-lookup"><span data-stu-id="b64b6-127">The Office 365 eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security & Compliance Center or from Advanced eDiscovery.</span></span> <span data-ttu-id="b64b6-128">設定`DownloadConcurrency`登錄設定是類似於執行 AzCopy 公用程式時使用 **/NC**參數。</span><span class="sxs-lookup"><span data-stu-id="b64b6-128">Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility.</span></span> <span data-ttu-id="b64b6-129">這樣的登錄設定`"DownloadConcurrency=24"`會有相同效果： 使用的參數值`/NC:24`AzCopy 公用程式。</span><span class="sxs-lookup"><span data-stu-id="b64b6-129">So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="b64b6-130">如果您要停止匯出下載仍在建構中，然後將其重新 （嘗試再次下載搜尋結果），Office 365 電子文件探索匯出工具會嘗試繼續的相同下載。</span><span class="sxs-lookup"><span data-stu-id="b64b6-130">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the Office 365 eDiscovery Export tool will attempt to resume the same download.</span></span> <span data-ttu-id="b64b6-131">因此，如果您啟動下載，停止，，然後變更`DownloadConcurrency`登錄設定，下載可能會失敗如果重新啟動 （藉由按一下 [**下載匯出的結果**)。</span><span class="sxs-lookup"><span data-stu-id="b64b6-131">So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**).</span></span> <span data-ttu-id="b64b6-132">這是因為匯出工具將會嘗試繼續使用無效，因為您已變更的登錄設定的設定先前下載。</span><span class="sxs-lookup"><span data-stu-id="b64b6-132">This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="b64b6-133">因此，當您變更`DownloadConcurrency`登錄設定，請務必重新啟動匯出工作 （按一下 [**重新啟動匯出**) 安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="b64b6-133">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security & Compliance Center.</span></span> <span data-ttu-id="b64b6-134">然後您可以下載匯出的結果。</span><span class="sxs-lookup"><span data-stu-id="b64b6-134">Then you can download the exported results.</span></span> <span data-ttu-id="b64b6-135">如需有關匯出搜尋結果和資料的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b64b6-135">For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="b64b6-136">匯出內容搜尋結果</span><span class="sxs-lookup"><span data-stu-id="b64b6-136">Export Content Search results</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="b64b6-137">在 Office 365 進階電子文件探索中匯出結果</span><span class="sxs-lookup"><span data-stu-id="b64b6-137">Export results in Office 365 Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    
