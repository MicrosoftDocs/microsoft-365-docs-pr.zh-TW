---
title: 在高級電子檔探索中執行進程模組及載入資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 瞭解如何使用安全性與 &amp; 合規性中心存取高級 eDiscovery，並執行案例的處理模組。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64172c0198418dbb0ba4d01a5adbd5aaef4c3a3b
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662831"
---
# <a name="run-the-process-module-and-load-data-in-advanced-ediscovery-classic"></a><span data-ttu-id="9b300-103">在高級 eDiscovery (傳統) 中執行進程模組和載入資料</span><span class="sxs-lookup"><span data-stu-id="9b300-103">Run the Process module and load data in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="9b300-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="9b300-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="9b300-106">本節說明高級 eDiscovery 處理模組的功能。</span><span class="sxs-lookup"><span data-stu-id="9b300-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="9b300-107">除了檔案資料之外，也可以將中繼資料（例如檔案類型、副檔名、位置或路徑），載入至「高級 eDiscovery」，並針對每個案例加以儲存。</span><span class="sxs-lookup"><span data-stu-id="9b300-107">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case.</span></span> <span data-ttu-id="9b300-108">某些中繼資料是由高級 eDiscovery 計算，例如，載入原生檔案時。</span><span class="sxs-lookup"><span data-stu-id="9b300-108">Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="9b300-109">Advanced eDiscovery 提供系統中繼資料值，例如接近重複的群組或相關性分數。</span><span class="sxs-lookup"><span data-stu-id="9b300-109">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores.</span></span> <span data-ttu-id="9b300-110">其他中繼資料（例如檔案批註）可以由系統管理員新增。</span><span class="sxs-lookup"><span data-stu-id="9b300-110">Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="9b300-111">正在執行進程</span><span class="sxs-lookup"><span data-stu-id="9b300-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="9b300-112">在處理期間，會將批次編號指派給檔案，以允許追蹤檔。</span><span class="sxs-lookup"><span data-stu-id="9b300-112">Batch numbers are assigned to a file during Process to allow the tracking of files.</span></span> <span data-ttu-id="9b300-113">批號也可識別處理選項的處理批次。</span><span class="sxs-lookup"><span data-stu-id="9b300-113">The batch number also enables identification of Process batches for reprocessing options.</span></span> <span data-ttu-id="9b300-114">其他篩選可依批次號碼和會話進行篩選。</span><span class="sxs-lookup"><span data-stu-id="9b300-114">Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="9b300-115">執行下列步驟以執行程式。</span><span class="sxs-lookup"><span data-stu-id="9b300-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="9b300-116">[開啟安全性 &amp; 規範中心](go-to-the-securitycompliance-center.md) 。</span><span class="sxs-lookup"><span data-stu-id="9b300-116">[Open the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="9b300-117">移至 [ **搜尋 &amp; 調查** \> **eDiscovery** ]，然後按一下 [ **移至高級 eDiscovery**]。</span><span class="sxs-lookup"><span data-stu-id="9b300-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="9b300-118">在 [Advanced eDiscovery] 的 [顯示 **案例** ] 頁面中，選取適當的大小寫，然後按一下 [ **移至任何情況**]。</span><span class="sxs-lookup"><span data-stu-id="9b300-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="9b300-119">在 [ **準備** \> **處理** \> **程式設定**] 中，從可用的容器清單中選取容器。</span><span class="sxs-lookup"><span data-stu-id="9b300-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![按一下 [處理常式]，將搜尋結果新增至案例](../media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="9b300-121">如果您想要將容器新增為 seed 檔案或預先標記的檔案，請按一下 [ **高級設定** ]。</span><span class="sxs-lookup"><span data-stu-id="9b300-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="9b300-122">使用 seed 檔案，加速低豐富 (的問題，通常是2% 或更少) 。</span><span class="sxs-lookup"><span data-stu-id="9b300-122">Use seed files to accelerate training for issues with low richness (usually 2%, or less).</span></span> <span data-ttu-id="9b300-123">針對 seed 檔案，建議您針對每個問題，選取各種明顯相關的檔案，並處理每個問題大約20-50 的播種 (很多種子檔都可以歪曲相關性結果) 。</span><span class="sxs-lookup"><span data-stu-id="9b300-123">For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results).</span></span> <span data-ttu-id="9b300-124">Seed 檔案應該由會訓練問題的相同人員進行審閱。</span><span class="sxs-lookup"><span data-stu-id="9b300-124">Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="9b300-125">使用預先標記的檔案來自動化相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="9b300-125">Use pre-tagged files to automate Relevance training.</span></span> <span data-ttu-id="9b300-126">您應標記至少1500個檔案，並將相關的與非相關檔案的比例保持在集合中，與新增至相關性的集合相同。</span><span class="sxs-lookup"><span data-stu-id="9b300-126">You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance.</span></span> <span data-ttu-id="9b300-127">這些檔案應以手動方式標記，您應該自信標記品質。</span><span class="sxs-lookup"><span data-stu-id="9b300-127">These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![處理批次檔案之 [高級設定] 頁面的螢幕擷取畫面](../media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="9b300-129">在 [ **Seed** ] 區段中：</span><span class="sxs-lookup"><span data-stu-id="9b300-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="9b300-130">選擇 [ **標示為種子檔** ]，將容器標示為 seed 檔案。</span><span class="sxs-lookup"><span data-stu-id="9b300-130">Choose **Mark as seed files** to mark the container as seed files.</span></span> <span data-ttu-id="9b300-131">您也需要根據問題的下拉式清單，選擇從 **每個問題** 進行指派。</span><span class="sxs-lookup"><span data-stu-id="9b300-131">You also need choose to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="9b300-132">從 [**標記**] 下拉式清單中選擇 [**相關**] 或 [**不相關**]。</span><span class="sxs-lookup"><span data-stu-id="9b300-132">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9b300-133">將檔案設定為 **Seed** 後，就無法將其標記為 **預先標記** 的檔。</span><span class="sxs-lookup"><span data-stu-id="9b300-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="9b300-134">在 [ **預先標記** 的檔案] 區段中：</span><span class="sxs-lookup"><span data-stu-id="9b300-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="9b300-135">選擇 [ **標記為預先標記的** 檔案]，將容器標示為預先標記的檔案。</span><span class="sxs-lookup"><span data-stu-id="9b300-135">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files.</span></span> <span data-ttu-id="9b300-136">您也必須根據問題的下拉式清單， **針對** 每個問題進行指派。</span><span class="sxs-lookup"><span data-stu-id="9b300-136">You also need to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="9b300-137">從 [**標記**] 下拉式清單中選擇 [**相關**] 或 [**不相關**]。</span><span class="sxs-lookup"><span data-stu-id="9b300-137">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9b300-138">將檔案設定為 **預先標記** 之後，就無法將其標記為 **Seed**。</span><span class="sxs-lookup"><span data-stu-id="9b300-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="9b300-139">在 [ **電子郵件標記** ] 區段中。</span><span class="sxs-lookup"><span data-stu-id="9b300-139">In the **Email tagging** section.</span></span> <span data-ttu-id="9b300-140">設定處理的電子郵件的哪一部分會標示為植入或預先標記。</span><span class="sxs-lookup"><span data-stu-id="9b300-140">set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="9b300-141">若要開始，請按一下 [ **處理**]。</span><span class="sxs-lookup"><span data-stu-id="9b300-141">To begin, click **Process**.</span></span> <span data-ttu-id="9b300-142">完成時，會顯示流程結果。</span><span class="sxs-lookup"><span data-stu-id="9b300-142">When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="9b300-143"> (選用) 如果您需要將資料來源指派給特定的保管人，您可以在 **保管人** 中新增及編輯保管人名稱， \> 並在 **保管人** \> **指派** 中指派保管人。</span><span class="sxs-lookup"><span data-stu-id="9b300-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="9b300-144">如果您新增至案例，您可以再次處理。</span><span class="sxs-lookup"><span data-stu-id="9b300-144">If you add to the case, then you can process again.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9b300-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="9b300-145">Related topics</span></span>

[<span data-ttu-id="9b300-146">Office 365 進階電子文件探索 (傳統版)</span><span class="sxs-lookup"><span data-stu-id="9b300-146">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="9b300-147">查看進程模組結果</span><span class="sxs-lookup"><span data-stu-id="9b300-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

