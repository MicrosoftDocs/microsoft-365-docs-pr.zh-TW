---
title: 當您匯出內容搜尋結果時停用報告
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: 在您的本機電腦上編輯 Windows 登錄，當您從 Office 365 的安全性 & 合規性中心匯出內容搜尋結果時，停用報告。 停用這些報告可加快下載時間，並節約磁碟空間。
ms.openlocfilehash: 3bd5fadda750c709c463fbc4d84668b43e0d3a10
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633448"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="d418b-104">當您匯出內容搜尋結果時停用報告</span><span class="sxs-lookup"><span data-stu-id="d418b-104">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="d418b-105">當您使用 eDiscovery 匯出工具在安全性 & 合規性中心匯出內容搜尋的結果時，此工具會自動建立及匯出包含匯出內容之其他資訊的兩個報告。</span><span class="sxs-lookup"><span data-stu-id="d418b-105">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="d418b-106">這些報告是結果 .csv 檔案和資訊清單 .xml 檔案（請參閱本主題中[關於如何停用「匯出報告](#frequently-asked-questions-about-disabling-export-reports)」一節的常見問題，以取得這些報告的詳細描述）。</span><span class="sxs-lookup"><span data-stu-id="d418b-106">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="d418b-107">因為這些檔案可能非常大，所以您可以透過防止匯出這些檔案，加快下載時間，並節省磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="d418b-107">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="d418b-108">若要這麼做，您可以在用來匯出搜尋結果的電腦上變更 Windows 登錄。</span><span class="sxs-lookup"><span data-stu-id="d418b-108">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="d418b-109">如果您想要稍後加入報告，您可以編輯登錄設定。</span><span class="sxs-lookup"><span data-stu-id="d418b-109">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="d418b-110">建立登錄設定以停用匯出報告</span><span class="sxs-lookup"><span data-stu-id="d418b-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="d418b-111">在您要用來匯出結果的電腦上執行下列程式，以進行內容搜尋。</span><span class="sxs-lookup"><span data-stu-id="d418b-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="d418b-112">關閉 eDiscovery 匯出工具（若已開啟）。</span><span class="sxs-lookup"><span data-stu-id="d418b-112">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="d418b-113">根據您要停用的匯出報表，執行下列其中一項或兩項步驟。</span><span class="sxs-lookup"><span data-stu-id="d418b-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="d418b-114">**結果 .csv**</span><span class="sxs-lookup"><span data-stu-id="d418b-114">**Results.csv**</span></span>
    
      <span data-ttu-id="d418b-115">使用檔案名尾碼註冊，將下列文字儲存至 Windows 登錄檔案。例如，DisableResultsCsv。</span><span class="sxs-lookup"><span data-stu-id="d418b-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="d418b-116">**Manifest .xml**</span><span class="sxs-lookup"><span data-stu-id="d418b-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="d418b-117">使用檔案名尾碼註冊，將下列文字儲存至 Windows 登錄檔案。例如，DisableManifestXml。</span><span class="sxs-lookup"><span data-stu-id="d418b-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="d418b-118">在 [Windows Explorer] 中，按一下或按兩下您在先前步驟中建立的 .reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="d418b-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="d418b-119">在 [使用者存取控制] 視窗中，按一下 **[是]** 讓登錄編輯程式進行變更。</span><span class="sxs-lookup"><span data-stu-id="d418b-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="d418b-120">當系統提示您繼續時，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="d418b-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="d418b-121">登錄編輯器會顯示一則訊息，指出已成功將設定新增至註冊表。</span><span class="sxs-lookup"><span data-stu-id="d418b-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="d418b-122">編輯登錄設定以重新啟用匯出報告</span><span class="sxs-lookup"><span data-stu-id="d418b-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="d418b-123">如果您已停用結果. csv 和資訊清單 .xml 報告在上述程式中建立 .reg 檔案，您可以編輯這些檔案，以重新啟用報表，使其與搜尋結果一起匯出。</span><span class="sxs-lookup"><span data-stu-id="d418b-123">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="d418b-124">此外，在您要用來匯出結果內容搜尋的電腦上執行下列程式。</span><span class="sxs-lookup"><span data-stu-id="d418b-124">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="d418b-125">關閉 eDiscovery 匯出工具（若已開啟）。</span><span class="sxs-lookup"><span data-stu-id="d418b-125">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="d418b-126">編輯您在先前程式中建立的其中一個或兩個 .reg 編輯檔案。</span><span class="sxs-lookup"><span data-stu-id="d418b-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="d418b-127">**結果 .csv**</span><span class="sxs-lookup"><span data-stu-id="d418b-127">**Results.csv**</span></span>
    
        <span data-ttu-id="d418b-128">在 [記事本] 中開啟 DisableResultsCsv 檔案，將值`False`變更為`True`，然後儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="d418b-128">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="d418b-129">例如，編輯檔案之後，它看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="d418b-129">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="d418b-130">**Manifest .xml**</span><span class="sxs-lookup"><span data-stu-id="d418b-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="d418b-131">在 [記事本] 中開啟 DisableManifestXml 檔案，將值`False`變更為`True`，然後儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="d418b-131">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="d418b-132">例如，編輯檔案之後，它看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="d418b-132">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="d418b-133">在 [Windows Explorer] 中，按一下或按兩下您在上一個步驟中編輯的 .reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="d418b-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="d418b-134">在 [使用者存取控制] 視窗中，按一下 **[是]** 讓登錄編輯程式進行變更。</span><span class="sxs-lookup"><span data-stu-id="d418b-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="d418b-135">當系統提示您繼續時，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="d418b-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="d418b-136">登錄編輯器會顯示一則訊息，指出已成功將設定新增至註冊表。</span><span class="sxs-lookup"><span data-stu-id="d418b-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="d418b-137">停用匯出報告的常見問題</span><span class="sxs-lookup"><span data-stu-id="d418b-137">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="d418b-138">**其結果是 csv 及資訊清單 .xml 報告？**</span><span class="sxs-lookup"><span data-stu-id="d418b-138">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="d418b-139">結果 .csv 和資訊清單 .xml 檔案包含匯出內容的其他相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d418b-139">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="d418b-140">**結果 .csv**包含每個下載為搜尋結果之專案相關資訊的 Excel 檔。</span><span class="sxs-lookup"><span data-stu-id="d418b-140">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="d418b-141">針對電子郵件，結果記錄檔包含每封郵件的相關資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="d418b-141">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="d418b-142">來源信箱中郵件的位置（包括郵件是在主要或封存信箱中）。</span><span class="sxs-lookup"><span data-stu-id="d418b-142">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="d418b-143">傳送或接收郵件的日期。</span><span class="sxs-lookup"><span data-stu-id="d418b-143">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="d418b-144">郵件的主旨行。</span><span class="sxs-lookup"><span data-stu-id="d418b-144">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="d418b-145">郵件的寄件者和收件者。</span><span class="sxs-lookup"><span data-stu-id="d418b-145">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="d418b-146">當您匯出搜尋結果時啟用重復資料刪除時，郵件是否是重複的郵件。</span><span class="sxs-lookup"><span data-stu-id="d418b-146">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="d418b-147">重複郵件會在**Parent ItemId** ] 欄中，將值識別為重複郵件。</span><span class="sxs-lookup"><span data-stu-id="d418b-147">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="d418b-148">**Parent ItemId** ] 欄中的值與所匯出郵件之 [**專案 DocumentId** ] 欄中的值相同。</span><span class="sxs-lookup"><span data-stu-id="d418b-148">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="d418b-149">針對來自 SharePoint 和 OneDrive 商務網站的檔，結果記錄檔包含每個檔的相關資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="d418b-149">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="d418b-150">檔的 URL。</span><span class="sxs-lookup"><span data-stu-id="d418b-150">The URL for the document.</span></span>
    
  - <span data-ttu-id="d418b-151">檔所在之網站集合的 URL。</span><span class="sxs-lookup"><span data-stu-id="d418b-151">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="d418b-152">上次修改檔的日期。</span><span class="sxs-lookup"><span data-stu-id="d418b-152">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="d418b-153">檔的名稱（位於結果記錄檔的 [主旨] 欄中）。</span><span class="sxs-lookup"><span data-stu-id="d418b-153">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="d418b-154">**Manifest .xml**包含搜尋結果中所包含之每個專案之相關資訊的資訊清單檔案（xml 格式）。</span><span class="sxs-lookup"><span data-stu-id="d418b-154">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="d418b-155">此報告中的資訊與結果 csv 報告相同，但其格式為「電子 Discovery 參考模型」（EDRM）所指定的格式。</span><span class="sxs-lookup"><span data-stu-id="d418b-155">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="d418b-156">如需 EDRM 的詳細資訊，請[https://www.edrm.net](https://www.edrm.net)前往。</span><span class="sxs-lookup"><span data-stu-id="d418b-156">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="d418b-157">**何時應該停用匯出這些報告？**</span><span class="sxs-lookup"><span data-stu-id="d418b-157">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="d418b-158">這取決於您的特定需求。</span><span class="sxs-lookup"><span data-stu-id="d418b-158">It depends on your specific needs.</span></span> <span data-ttu-id="d418b-159">許多組織不需要搜尋結果的額外資訊，而且不需要這些報告。</span><span class="sxs-lookup"><span data-stu-id="d418b-159">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="d418b-160">**我需要執行此動作的電腦為何？**</span><span class="sxs-lookup"><span data-stu-id="d418b-160">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="d418b-161">您必須在執行 eDiscovery 匯出工具的任何本機電腦上變更登錄設定。</span><span class="sxs-lookup"><span data-stu-id="d418b-161">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="d418b-162">**變更此設定後，是否需要重新開機電腦？**</span><span class="sxs-lookup"><span data-stu-id="d418b-162">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="d418b-163">否，您不需要重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="d418b-163">No, you don't have to restart the computer.</span></span> <span data-ttu-id="d418b-164">不過，如果正在執行 eDiscovery 匯出工具，您必須關閉它，然後在變更登錄設定之後重新開機它。</span><span class="sxs-lookup"><span data-stu-id="d418b-164">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="d418b-165">**是否已編輯現有登錄機碼，或是建立新的金鑰？**</span><span class="sxs-lookup"><span data-stu-id="d418b-165">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="d418b-166">當您第一次執行您在本主題的程式中所建立的 .reg 檔案時，就會建立新的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="d418b-166">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="d418b-167">然後，每當您變更並重新執行 .reg 編輯檔案時，就會編輯設定。</span><span class="sxs-lookup"><span data-stu-id="d418b-167">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
