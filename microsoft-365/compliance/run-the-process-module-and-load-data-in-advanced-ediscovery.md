---
title: 執行處理序模組及載入 Office 365 進階電子文件探索中的資料
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: '了解如何使用 Office 365 安全性&amp;合規性中心存取 Office 365 進階電子文件探索及執行處理序模組的案例。  '
ms.openlocfilehash: 89a4be9bf56f35d9d9cbd88494bcae5a5a10fe7a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077571"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a><span data-ttu-id="b75d7-103">執行處理序模組及載入 Office 365 進階電子文件探索中的資料</span><span class="sxs-lookup"><span data-stu-id="b75d7-103">Run the Process module and load data in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="b75d7-p101">進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="b75d7-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="b75d7-106">本節說明進階電子文件處理序模組的功能。</span><span class="sxs-lookup"><span data-stu-id="b75d7-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="b75d7-107">除了檔案資料，例如檔案類型、 副檔名、 位置或路徑、 建立日期和時間、 作者、 custodian 和主旨的中繼資料可以載入至進階電子文件探索，並儲存為每個案例。</span><span class="sxs-lookup"><span data-stu-id="b75d7-107">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case.</span></span> <span data-ttu-id="b75d7-108">有些中繼資料的計算方式進階電子文件，例如載入原生檔案時。</span><span class="sxs-lookup"><span data-stu-id="b75d7-108">Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="b75d7-109">進階電子文件提供系統中繼資料值，例如近似重複群組或相關性分數。</span><span class="sxs-lookup"><span data-stu-id="b75d7-109">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores.</span></span> <span data-ttu-id="b75d7-110">由系統管理員可以新增其他中繼資料，例如檔案註釋。</span><span class="sxs-lookup"><span data-stu-id="b75d7-110">Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="b75d7-111">執行程序</span><span class="sxs-lookup"><span data-stu-id="b75d7-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="b75d7-112">批次號碼指派給檔案程序期間允許的追蹤檔案。</span><span class="sxs-lookup"><span data-stu-id="b75d7-112">Batch numbers are assigned to a file during Process to allow the tracking of files.</span></span> <span data-ttu-id="b75d7-113">批次數目也可讓重新處理選項的程序批次的識別。</span><span class="sxs-lookup"><span data-stu-id="b75d7-113">The batch number also enables identification of Process batches for reprocessing options.</span></span> <span data-ttu-id="b75d7-114">其他篩選器可用來篩選由批次數目和工作階段。</span><span class="sxs-lookup"><span data-stu-id="b75d7-114">Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="b75d7-115">執行下列步驟來執行處理程序。</span><span class="sxs-lookup"><span data-stu-id="b75d7-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="b75d7-116">[開啟 Office 365 安全性&amp;合規性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b75d7-116">[Open the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="b75d7-117">移至**搜尋&amp;調查** \> **eDiscovery** ，然後按一下 [**移至進階電子文件**。</span><span class="sxs-lookup"><span data-stu-id="b75d7-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="b75d7-118">在進階電子文件，在顯示的**案例**] 頁面中選取適當的情況下，按一下 [**前往案例**。</span><span class="sxs-lookup"><span data-stu-id="b75d7-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="b75d7-119">在 [**準備** \> **程序** \> **安裝程式**，從可用的容器清單容器選取。</span><span class="sxs-lookup"><span data-stu-id="b75d7-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![按一下 [新增至案例的搜尋結果的程序](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="b75d7-121">如果您想要作為植入的檔案或預先標記檔案新增容器，請按一下 [**進階設定...** ]。</span><span class="sxs-lookup"><span data-stu-id="b75d7-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="b75d7-122">使用植入的檔案來加速問題的訓練與低豐富性 (通常是 2%或更少)。</span><span class="sxs-lookup"><span data-stu-id="b75d7-122">Use seed files to accelerate training for issues with low richness (usually 2%, or less).</span></span> <span data-ttu-id="b75d7-123">對於植入的檔案，建議您選取各種是否相關檔案和處理程序的相關 20-50 種子每 （植入的檔案太多可以扭曲相關性結果） 的問題。</span><span class="sxs-lookup"><span data-stu-id="b75d7-123">For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results).</span></span> <span data-ttu-id="b75d7-124">植入的檔案應該檢閱同一位人員給將訓練問題。</span><span class="sxs-lookup"><span data-stu-id="b75d7-124">Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="b75d7-125">使用預先標記的檔案來自動化相關性訓練。</span><span class="sxs-lookup"><span data-stu-id="b75d7-125">Use pre-tagged files to automate Relevance training.</span></span> <span data-ttu-id="b75d7-126">您應該標記至少 1500 檔案，並新增至相關性集合相同保留之非相關檔案相關的比例。</span><span class="sxs-lookup"><span data-stu-id="b75d7-126">You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance.</span></span> <span data-ttu-id="b75d7-127">這些檔案應該手動標記，而且您應該以內的標記品質。</span><span class="sxs-lookup"><span data-stu-id="b75d7-127">These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![螢幕擷取畫面的進階設定] 頁面上的處理批次檔案](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="b75d7-129">在 [**種子**] 區段中：</span><span class="sxs-lookup"><span data-stu-id="b75d7-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="b75d7-130">選擇 [**標示成已植入的檔案**，即可將容器標示為植入的檔案。</span><span class="sxs-lookup"><span data-stu-id="b75d7-130">Choose **Mark as seed files** to mark the container as seed files.</span></span> <span data-ttu-id="b75d7-131">您也需要選擇要指派給每此問題： 從**問題**下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="b75d7-131">You also need choose to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="b75d7-132">從**標籤**下拉式清單中選擇**相關**或**不相關**。</span><span class="sxs-lookup"><span data-stu-id="b75d7-132">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b75d7-133">一旦您設定檔案作為**植入**，您無法將它們標示為**預先標記**。</span><span class="sxs-lookup"><span data-stu-id="b75d7-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="b75d7-134">在 [**預先標記的檔案**] 區段中：</span><span class="sxs-lookup"><span data-stu-id="b75d7-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="b75d7-135">選擇 [**標示成已預先標記檔案**可將標示預先標記檔案中的容器]。</span><span class="sxs-lookup"><span data-stu-id="b75d7-135">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files.</span></span> <span data-ttu-id="b75d7-136">您也需要將它們指派每此問題： 從**問題**下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="b75d7-136">You also need to assign them per issue from the **For issue** drop-down.</span></span> <span data-ttu-id="b75d7-137">從**標籤**下拉式清單中選擇**相關**或**不相關**。</span><span class="sxs-lookup"><span data-stu-id="b75d7-137">Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b75d7-138">一旦您設定檔做為**預先標記**時，您無法將它們標示為**植入**。</span><span class="sxs-lookup"><span data-stu-id="b75d7-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="b75d7-139">在 [**電子郵件標記**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="b75d7-139">In the **Email tagging** section.</span></span> <span data-ttu-id="b75d7-140">已處理的電子郵件的哪個部分會被標示為植入或預先標記的設定。</span><span class="sxs-lookup"><span data-stu-id="b75d7-140">set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="b75d7-141">若要開始，請按一下 [**程序**。</span><span class="sxs-lookup"><span data-stu-id="b75d7-141">To begin, click **Process**.</span></span> <span data-ttu-id="b75d7-142">完成時，會顯示處理程序的結果。</span><span class="sxs-lookup"><span data-stu-id="b75d7-142">When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="b75d7-143">（選用）如果您需要指派給特定 custodian 的資料來源，您可以新增和編輯中**Custodians** custodian 名稱\> **Custodians**中的**管理**] 和 [指派 custodians \> **指派**。</span><span class="sxs-lookup"><span data-stu-id="b75d7-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="b75d7-144">如果您新增至案例，然後您可以再次處理。</span><span class="sxs-lookup"><span data-stu-id="b75d7-144">If you add to the case, then you can process again.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b75d7-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b75d7-145">See also</span></span>

[<span data-ttu-id="b75d7-146">Office 365 進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="b75d7-146">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b75d7-147">檢視處理序模組結果</span><span class="sxs-lookup"><span data-stu-id="b75d7-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

