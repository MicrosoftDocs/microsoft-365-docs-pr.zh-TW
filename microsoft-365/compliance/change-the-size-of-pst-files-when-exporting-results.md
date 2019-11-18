---
title: 匯出 eDiscovery 搜尋結果時變更 PST 檔案的大小
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 您可以變更預設的 PST 檔案大小，當您匯出 eDiscovery 搜尋結果下載到您的電腦。
ms.openlocfilehash: b3bba45ce336b143ed948db384673f0a1a5a456f
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38685572"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="f3859-103">匯出 eDiscovery 搜尋結果時變更 PST 檔案的大小</span><span class="sxs-lookup"><span data-stu-id="f3859-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="f3859-104">當您匯出 eDiscovery 搜尋的電子郵件結果從不同的 Microsoft eDiscovery 工具使用 Office 365 電子文件探索匯出工具時，可匯出的 PST 檔案的預設大小為 10 GB。</span><span class="sxs-lookup"><span data-stu-id="f3859-104">When you use the Office 365 eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="f3859-105">如果您想要變更此預設的大小，您可以編輯您用來匯出搜尋結果的電腦上的 Windows 登錄。</span><span class="sxs-lookup"><span data-stu-id="f3859-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="f3859-106">若要這麼做的原因之一是讓 PST 檔案可容納抽取式媒體、 這類 DVD、 光碟片或 USB 磁碟機上。</span><span class="sxs-lookup"><span data-stu-id="f3859-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="f3859-107">Office 365 電子文件探索匯出工具用來匯出搜尋結果時使用內容搜尋工具中的安全性與合規性中心，就地 eDiscovery 在 Exchange Online 和 SharePoint Online 中的 eDiscovery 中心。</span><span class="sxs-lookup"><span data-stu-id="f3859-107">The Office 365 eDiscovery Export tool is used to export the search results when using the Content Search tool in the security and compliance center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="f3859-108">建立要變更的 PST 檔案大小，當您匯出 eDiscovery 搜尋結果的登錄設定</span><span class="sxs-lookup"><span data-stu-id="f3859-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="f3859-109">您要使用可匯出的 eDiscovery 搜尋結果的電腦上執行下列程序。</span><span class="sxs-lookup"><span data-stu-id="f3859-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="f3859-110">如果它已經開啟，請關閉 Office 365 電子文件探索匯出工具。</span><span class="sxs-lookup"><span data-stu-id="f3859-110">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="f3859-111">將下列文字儲存到視窗登錄檔案中，使用.reg; 檔名尾碼例如，PstExportSize.reg。</span><span class="sxs-lookup"><span data-stu-id="f3859-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="f3859-112">在範例中，與上述`PstSizeLimitInBytes`值設為 1,073,741,824 位元組或大約 1 GB。</span><span class="sxs-lookup"><span data-stu-id="f3859-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="f3859-113">以下是一些其他範例值`PstSizeLimitInBytes`設定。</span><span class="sxs-lookup"><span data-stu-id="f3859-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="f3859-114">**調整大小以 GB （大約）**</span><span class="sxs-lookup"><span data-stu-id="f3859-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="f3859-115">**大小 （位元組）**</span><span class="sxs-lookup"><span data-stu-id="f3859-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="f3859-116">.7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="f3859-116">.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="f3859-117">751619277</span><span class="sxs-lookup"><span data-stu-id="f3859-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="f3859-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="f3859-118">2 GB</span></span>  <br/> |<span data-ttu-id="f3859-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="f3859-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="f3859-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="f3859-120">4 GB</span></span>  <br/> |<span data-ttu-id="f3859-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="f3859-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="f3859-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="f3859-122">8 GB</span></span>  <br/> |<span data-ttu-id="f3859-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="f3859-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="f3859-124">變更`PstSizeLimitInBytes`值，當您匯出搜尋結果，並再將檔案儲存為 PST 檔案所需最大大小。</span><span class="sxs-lookup"><span data-stu-id="f3859-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="f3859-125">在 Windows 檔案總管] 中，按一下或按兩下您在先前步驟中建立的.reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="f3859-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="f3859-126">在 [使用者存取控制] 視窗中，按一下 [ **]** 讓登錄編輯程式中進行的變更。</span><span class="sxs-lookup"><span data-stu-id="f3859-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="f3859-127">出現提示時若要繼續，按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="f3859-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="f3859-128">登錄編輯程式中會顯示訊息，說明設定已成功新增至登錄。</span><span class="sxs-lookup"><span data-stu-id="f3859-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="f3859-129">您可以重複執行步驟 3 至 6，若要變更的值為`PstSizeLimitInBytes`登錄設定。</span><span class="sxs-lookup"><span data-stu-id="f3859-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="f3859-130">當您匯出 eDiscovery 搜尋結果時變更 PST 檔案的預設大小的相關的常見問題集</span><span class="sxs-lookup"><span data-stu-id="f3859-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="f3859-131">**原因是 [預設大小為 10 GB 嗎？**</span><span class="sxs-lookup"><span data-stu-id="f3859-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="f3859-132">10 GB 的預設大小已根據客戶意見反應。10 GB 是內容的最佳中單一 PST 與檔案損毀的最小機會量間的良好平衡。</span><span class="sxs-lookup"><span data-stu-id="f3859-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="f3859-133">**我應該增加或減少 PST 檔案的預設大小？**</span><span class="sxs-lookup"><span data-stu-id="f3859-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="f3859-134">客戶通常會減少的大小限制，使搜尋結果將會放在他們可以實際運送其組織中的其他位置的抽取式媒體上。</span><span class="sxs-lookup"><span data-stu-id="f3859-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship other locations in their organization.</span></span> <span data-ttu-id="f3859-135">我們不建議您增加預設的大小，因為 PST 檔案大於 10GB 可能已損毀問題。</span><span class="sxs-lookup"><span data-stu-id="f3859-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="f3859-136">**我有執行這項作業電腦為何？**</span><span class="sxs-lookup"><span data-stu-id="f3859-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="f3859-137">您要變更您在執行 Office 365 電子文件探索匯出工具的任何本機電腦上的登錄設定。</span><span class="sxs-lookup"><span data-stu-id="f3859-137">You need to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="f3859-138">**變更此設定後，必須將電腦重新開機嗎？**</span><span class="sxs-lookup"><span data-stu-id="f3859-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="f3859-139">否，您不需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="f3859-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="f3859-140">但是，如果執行 Office 365 電子文件探索匯出工具，您必須關閉它，並重新啟動後您變更此設定。</span><span class="sxs-lookup"><span data-stu-id="f3859-140">But, if the Office 365 eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="f3859-141">**沒有現有的登錄機碼取得編輯或沒有取得建立新的金鑰嗎？**</span><span class="sxs-lookup"><span data-stu-id="f3859-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="f3859-142">新的登錄機碼會建立第一次執行您在此程序中建立的.reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="f3859-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="f3859-143">然後設定編輯的每當您變更，然後重新執行.reg 編輯檔案。</span><span class="sxs-lookup"><span data-stu-id="f3859-143">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
