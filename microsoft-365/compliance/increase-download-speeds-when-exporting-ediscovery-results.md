---
title: 提高匯出 eDiscovery 搜尋結果時的下載速度
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何設定 Windows 登錄，以在下載搜尋結果和資料時增加資料輸送量。
ms.openlocfilehash: a68a616d2dced4a3dd70580e1b258c95a0b5e39e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817672"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results"></a><span data-ttu-id="70283-103">提高匯出 eDiscovery 搜尋結果時的下載速度</span><span class="sxs-lookup"><span data-stu-id="70283-103">Increase the download speed when exporting eDiscovery search results</span></span>

<span data-ttu-id="70283-104">當您使用 eDiscovery 匯出工具在安全性 & 合規性中心下載內容搜尋的結果或從高級 eDiscovery 下載資料時，此工具會啟動特定數目的併發匯出作業，以將資料下載到您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="70283-104">When you use the eDiscovery Export tool to download the results of a Content Search in the Security & Compliance Center or download data from Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer.</span></span> <span data-ttu-id="70283-105">根據預設，並行作業數目會設定為您要用來下載資料之電腦中的核心數目的8倍。</span><span class="sxs-lookup"><span data-stu-id="70283-105">By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data.</span></span> <span data-ttu-id="70283-106">例如，如果您有一個雙核計算機（即一個晶片上的兩個中央處理單位），則同時匯出作業的預設數目為16。</span><span class="sxs-lookup"><span data-stu-id="70283-106">For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16.</span></span> <span data-ttu-id="70283-107">若要增加資料傳輸輸送量並加速下載程式，您可以在您用來下載搜尋結果的電腦上設定 Windows 登錄設定，以增加並行作業的數目。</span><span class="sxs-lookup"><span data-stu-id="70283-107">To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results.</span></span> <span data-ttu-id="70283-108">若要加速下載程式，建議您從24個同時作業的設定開始。</span><span class="sxs-lookup"><span data-stu-id="70283-108">To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="70283-109">如果您透過低頻寬網路下載搜尋結果，增加此設定可能會造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="70283-109">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact.</span></span> <span data-ttu-id="70283-110">或者，您也可以將此設定增加至高頻寬網路中超過24個同時作業（同時作業的最大數目為48）。</span><span class="sxs-lookup"><span data-stu-id="70283-110">Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 48).</span></span> <span data-ttu-id="70283-111">在您設定此登錄設定之後，您可能需要變更它，以找出您環境的最佳並行作業數目。</span><span class="sxs-lookup"><span data-stu-id="70283-111">After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="70283-112">建立登錄設定，以在匯出資料時變更同時作業的數目</span><span class="sxs-lookup"><span data-stu-id="70283-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="70283-113">在電腦上執行下列程式，以從 Security & 合規性中心或從高級 eDiscovery 的資料下載搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="70283-113">Perform the following procedure on the computer that you'll use to download search results from the Security & Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="70283-114">關閉 eDiscovery 匯出工具（若已開啟）。</span><span class="sxs-lookup"><span data-stu-id="70283-114">Close the eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="70283-115">使用檔案名尾碼註冊，將下列文字儲存至視窗登錄檔;例如，ConcurrentOperations。</span><span class="sxs-lookup"><span data-stu-id="70283-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="70283-116">如先前所述，我們建議您從24個同時進行的作業開始，然後視需要變更此設定。</span><span class="sxs-lookup"><span data-stu-id="70283-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="70283-117">在 [Windows Explorer] 中，按一下或按兩下您在上一個步驟中建立的 .reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="70283-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="70283-118">在 [使用者存取控制] 視窗中，按一下 **[是]** 讓登錄編輯程式進行變更。</span><span class="sxs-lookup"><span data-stu-id="70283-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="70283-119">當系統提示您繼續時，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="70283-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="70283-120">登錄編輯器會顯示一則訊息，指出已成功將設定新增至註冊表。</span><span class="sxs-lookup"><span data-stu-id="70283-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="70283-121">您可以重複步驟 2-5，以變更 [登錄] `DownloadConcurrency` 設定的值。</span><span class="sxs-lookup"><span data-stu-id="70283-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="70283-122">在您建立或變更登錄 `DownloadConcurrency` 設定之後，請務必建立新的匯出工作或重新開機您要下載之搜尋結果或資料的現有匯出工作。</span><span class="sxs-lookup"><span data-stu-id="70283-122">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download.</span></span> <span data-ttu-id="70283-123">如需詳細資訊，請參閱[詳細資訊](#more-information)一節。</span><span class="sxs-lookup"><span data-stu-id="70283-123">See the [More information](#more-information) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="70283-124">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="70283-124">More information</span></span>

- <span data-ttu-id="70283-125">當您第一次執行您在此程式中建立的 .reg 檔案時，就會建立新的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="70283-125">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="70283-126">然後， `DownloadConcurrency` 每當您變更並重新執行 .reg 編輯檔案時，就會編輯登錄設定。</span><span class="sxs-lookup"><span data-stu-id="70283-126">Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="70283-127">EDiscovery 匯出工具使用[Azure AzCopy 公用程式](https://go.microsoft.com/fwlink/?linkid=849949)，從安全性 & 規範中心或從高級 eDiscovery 下載搜尋資料。</span><span class="sxs-lookup"><span data-stu-id="70283-127">The eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security & Compliance Center or from Advanced eDiscovery.</span></span> <span data-ttu-id="70283-128">設定登錄 `DownloadConcurrency` 設定與執行 AzCopy 公用程式時使用 **/NC**參數類似。</span><span class="sxs-lookup"><span data-stu-id="70283-128">Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility.</span></span> <span data-ttu-id="70283-129">所以登錄設定的 `"DownloadConcurrency=24"` 效果與使用 AzCopy 公用程式的參數值相同 `/NC:24` 。</span><span class="sxs-lookup"><span data-stu-id="70283-129">So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="70283-130">如果您停止目前正在進行的匯出下載，然後重新開機它（嘗試再次下載搜尋結果），eDiscovery 匯出工具會嘗試繼續相同的下載。</span><span class="sxs-lookup"><span data-stu-id="70283-130">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the eDiscovery Export tool will attempt to resume the same download.</span></span> <span data-ttu-id="70283-131">因此，如果您開始下載，請停止它，然後變更登錄 `DownloadConcurrency` 設定，當您重新開機時（按一下 [**下載匯出的結果**]），下載可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="70283-131">So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**).</span></span> <span data-ttu-id="70283-132">這是因為匯出工具會嘗試使用不正確設定來繼續先前的下載，因為您已變更登錄設定。</span><span class="sxs-lookup"><span data-stu-id="70283-132">This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="70283-133">因此，變更登錄設定之後 `DownloadConcurrency` ，請務必在安全性 & 規範中心內重新開機匯出工作（按一下 [**重新開機匯出**]）。</span><span class="sxs-lookup"><span data-stu-id="70283-133">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security & Compliance Center.</span></span> <span data-ttu-id="70283-134">然後您可以下載匯出的結果。</span><span class="sxs-lookup"><span data-stu-id="70283-134">Then you can download the exported results.</span></span> <span data-ttu-id="70283-135">如需匯出搜尋結果和資料的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="70283-135">For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="70283-136">匯出內容搜尋結果</span><span class="sxs-lookup"><span data-stu-id="70283-136">Export Content Search results</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="70283-137">在高級電子檔探索中匯出結果</span><span class="sxs-lookup"><span data-stu-id="70283-137">Export results in Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    
