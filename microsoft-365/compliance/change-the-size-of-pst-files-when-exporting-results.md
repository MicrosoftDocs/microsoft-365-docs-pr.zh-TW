---
title: 在匯出 eDiscovery 搜尋結果時變更 PST 檔案的大小
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 當您匯出 eDiscovery 搜尋結果時，您可以變更下載到電腦的 PST 檔案的預設大小。
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942916"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="6a35a-103">在匯出 eDiscovery 搜尋結果時變更 PST 檔案的大小</span><span class="sxs-lookup"><span data-stu-id="6a35a-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="6a35a-104">當您使用 eDiscovery 匯出工具從不同的 Microsoft eDiscovery 工具匯出 eDiscovery 搜尋的電子郵件結果時，可以匯出的 PST 檔案的預設大小為 10 GB。</span><span class="sxs-lookup"><span data-stu-id="6a35a-104">When you use the eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="6a35a-105">如果您想要變更此預設大小，您可以在用來匯出搜尋結果的電腦上，編輯 Windows 的註冊表。</span><span class="sxs-lookup"><span data-stu-id="6a35a-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="6a35a-106">執行這項作業的一個原因是，您可以在卸除式媒體（例如 DVD、光碟或 USB 磁片磁碟機）上容納 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="6a35a-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6a35a-107">在 [安全性 & 規範中心] 中使用「內容搜尋」工具、In-Place ediscovery Exchange Online，以及 SharePoint Online 中的 ediscovery 中心，可使用 ediscovery 匯出工具匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="6a35a-107">The eDiscovery Export tool is used to export the search results when using the Content Search tool in the Security & Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="6a35a-108">當您匯出 eDiscovery 搜尋結果時，建立登錄設定以變更 PST 檔案的大小</span><span class="sxs-lookup"><span data-stu-id="6a35a-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="6a35a-109">在您要用來匯出 eDiscovery 搜尋結果的電腦上執行下列程式。</span><span class="sxs-lookup"><span data-stu-id="6a35a-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="6a35a-110">關閉 eDiscovery 匯出工具（若已開啟）。</span><span class="sxs-lookup"><span data-stu-id="6a35a-110">Close the eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="6a35a-111">使用檔案名尾碼註冊，將下列文字儲存至視窗登錄檔;例如，PstExportSize。</span><span class="sxs-lookup"><span data-stu-id="6a35a-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="6a35a-112">在上面的範例中，此  `PstSizeLimitInBytes` 值設為1073741824位元組或大約 1 GB。</span><span class="sxs-lookup"><span data-stu-id="6a35a-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="6a35a-113">以下是設定的一些其他範例值  `PstSizeLimitInBytes` 。</span><span class="sxs-lookup"><span data-stu-id="6a35a-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="6a35a-114">**大小，以 GB 為單位 ()**</span><span class="sxs-lookup"><span data-stu-id="6a35a-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="6a35a-115">**大小（位元組）**</span><span class="sxs-lookup"><span data-stu-id="6a35a-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6a35a-116">0.7 GB (700 MB) </span><span class="sxs-lookup"><span data-stu-id="6a35a-116">0.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="6a35a-117">751619277</span><span class="sxs-lookup"><span data-stu-id="6a35a-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="6a35a-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="6a35a-118">2 GB</span></span>  <br/> |<span data-ttu-id="6a35a-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="6a35a-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="6a35a-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="6a35a-120">4 GB</span></span>  <br/> |<span data-ttu-id="6a35a-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="6a35a-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="6a35a-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="6a35a-122">8 GB</span></span>  <br/> |<span data-ttu-id="6a35a-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="6a35a-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="6a35a-124">`PstSizeLimitInBytes`當您匯出搜尋結果時，將值變更為所需的 PST 檔案大小上限，然後儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="6a35a-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="6a35a-125">在 Windows Explorer 中，按一下或按兩下您在先前步驟中建立的 .reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="6a35a-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="6a35a-126">在 [使用者存取控制] 視窗中，按一下 **[是]** 讓登錄編輯程式進行變更。</span><span class="sxs-lookup"><span data-stu-id="6a35a-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="6a35a-127">當系統提示您繼續時，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="6a35a-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="6a35a-128">登錄編輯器會顯示一則訊息，指出已成功將設定新增至註冊表。</span><span class="sxs-lookup"><span data-stu-id="6a35a-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="6a35a-129">您可以重複步驟 3-6，以變更 [登錄]  `PstSizeLimitInBytes` 設定的值。</span><span class="sxs-lookup"><span data-stu-id="6a35a-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="6a35a-130">當您匯出 eDiscovery 搜尋結果時，變更 PST 檔案預設大小的常見問題</span><span class="sxs-lookup"><span data-stu-id="6a35a-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="6a35a-131">**為何預設大小為 10 GB？**</span><span class="sxs-lookup"><span data-stu-id="6a35a-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="6a35a-132">10 GB 的預設大小是根據客戶的意見反應而定。10 GB 是在單一 PST 中的最佳內容量與最小可能的檔案損毀之間的完美平衡。</span><span class="sxs-lookup"><span data-stu-id="6a35a-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="6a35a-133">**是否應該增加或減少 PST 檔案的預設大小？**</span><span class="sxs-lookup"><span data-stu-id="6a35a-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="6a35a-134">客戶傾向于減少大小限制，讓搜尋結果能容納在其實際運送至其組織中其他位置的可移除媒體。</span><span class="sxs-lookup"><span data-stu-id="6a35a-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship to other locations in their organization.</span></span> <span data-ttu-id="6a35a-135">建議您不要增加預設大小，因為 PST 檔案大於 10 GB 時可能有損毀問題。</span><span class="sxs-lookup"><span data-stu-id="6a35a-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="6a35a-136">**我需要執行此動作的電腦為何？**</span><span class="sxs-lookup"><span data-stu-id="6a35a-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="6a35a-137">您必須在您執行 eDiscovery 匯出工具的任何本機電腦上變更登錄設定。</span><span class="sxs-lookup"><span data-stu-id="6a35a-137">You need to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="6a35a-138">**變更此設定後，是否需要重新開機電腦？**</span><span class="sxs-lookup"><span data-stu-id="6a35a-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="6a35a-139">否，您不需要重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="6a35a-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="6a35a-140">不過，如果 eDiscovery 匯出工具正在執行，您必須關閉它，然後在變更此設定之後重新開機它。</span><span class="sxs-lookup"><span data-stu-id="6a35a-140">But, if the eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="6a35a-141">**是否已編輯現有登錄機碼，或是建立新的金鑰？**</span><span class="sxs-lookup"><span data-stu-id="6a35a-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="6a35a-142">當您第一次執行您在此程式中建立的 .reg 檔案時，就會建立新的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="6a35a-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="6a35a-143">然後，每當您變更並重新執行 .reg 編輯檔案時，就會編輯設定。</span><span class="sxs-lookup"><span data-stu-id="6a35a-143">Then the setting is edited each time you change and rerun the .reg edit file.</span></span>
