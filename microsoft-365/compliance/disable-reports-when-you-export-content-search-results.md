---
title: 當您匯出內容搜尋結果時停用報告
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
description: 編輯 Windows 登錄在本機電腦上，停用的報表，當您從 Office 365 中的安全性 & 合規性中心匯出內容搜尋的結果。 停用這些報告可加速下載時間，並將儲存的磁碟空間。
ms.openlocfilehash: f9b999eaf3f1924012c9d4899b0e234f0893fc2c
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38685615"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="ca788-104">當您匯出內容搜尋結果時停用報告</span><span class="sxs-lookup"><span data-stu-id="ca788-104">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="ca788-105">當您要匯出其結果的安全性 & 合規性中心的內容搜尋使用 Office 365 電子文件探索匯出工具時，工具會自動建立，並匯出包含匯出內容相關的其他資訊的兩個報表。</span><span class="sxs-lookup"><span data-stu-id="ca788-105">When you use the Office 365 eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="ca788-106">這些報告是 Results.csv 和 Manifest.xml 檔案 （請參閱本主題的詳細說明這些報告的[常見問題集關於停用匯出報告](#frequently-asked-questions-about-disabling-export-reports)一節）。</span><span class="sxs-lookup"><span data-stu-id="ca788-106">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="ca788-107">因為這些檔案可能會很大，您可以加速下載時間，並藉由防止這些檔案所匯出儲存的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="ca788-107">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="ca788-108">您可以藉由變更您用來匯出搜尋結果的電腦上的 Windows 登錄來這麼做。</span><span class="sxs-lookup"><span data-stu-id="ca788-108">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="ca788-109">如果您想要包含在稍後的報告，您可以編輯的登錄設定。</span><span class="sxs-lookup"><span data-stu-id="ca788-109">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="ca788-110">建立登錄設定來停用匯出報告</span><span class="sxs-lookup"><span data-stu-id="ca788-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="ca788-111">您將使用來將結果匯出內容搜尋的電腦上執行下列程序。</span><span class="sxs-lookup"><span data-stu-id="ca788-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="ca788-112">如果它已經開啟，請關閉 Office 365 電子文件探索匯出工具。</span><span class="sxs-lookup"><span data-stu-id="ca788-112">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="ca788-113">執行下列一或兩個以下的步驟中，視哪些匯出報告您要停用。</span><span class="sxs-lookup"><span data-stu-id="ca788-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="ca788-114">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="ca788-114">**Results.csv**</span></span>
    
      <span data-ttu-id="ca788-115">將下列文字儲存到 Windows 登錄檔中，使用.reg; 檔名尾碼例如，DisableResultsCsv.reg。</span><span class="sxs-lookup"><span data-stu-id="ca788-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="ca788-116">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="ca788-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="ca788-117">將下列文字儲存到 Windows 登錄檔中，使用.reg; 檔名尾碼例如，DisableManifestXml.reg。</span><span class="sxs-lookup"><span data-stu-id="ca788-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="ca788-118">在 Windows 檔案總管] 中，按一下或按兩下您在先前步驟中建立的.reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="ca788-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="ca788-119">在 [使用者存取控制] 視窗中，按一下 [ **]** 讓登錄編輯程式中進行的變更。</span><span class="sxs-lookup"><span data-stu-id="ca788-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="ca788-120">出現提示時若要繼續，按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="ca788-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="ca788-121">登錄編輯程式中會顯示訊息，說明設定已成功新增至登錄。</span><span class="sxs-lookup"><span data-stu-id="ca788-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="ca788-122">編輯若要重新啟用匯出報告的登錄設定</span><span class="sxs-lookup"><span data-stu-id="ca788-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="ca788-123">如果您停用 [Results.csv] 及 [Manifest.xml 報表在先前的程序中建立.reg 檔案，您可以編輯若要重新啟用報表，以便在搜尋結果匯出這些檔案。</span><span class="sxs-lookup"><span data-stu-id="ca788-123">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="ca788-124">同樣地，您將用來將結果匯出內容搜尋的電腦上執行下列程序。</span><span class="sxs-lookup"><span data-stu-id="ca788-124">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="ca788-125">如果它已經開啟，請關閉 Office 365 電子文件探索匯出工具。</span><span class="sxs-lookup"><span data-stu-id="ca788-125">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="ca788-126">編輯一或兩個您在先前的程序中建立的.reg 編輯檔案。</span><span class="sxs-lookup"><span data-stu-id="ca788-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="ca788-127">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="ca788-127">**Results.csv**</span></span>
    
        <span data-ttu-id="ca788-128">開啟 [記事本] 中的 DisableResultsCsv.reg 檔案變更值`False`以`True`，然後儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="ca788-128">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="ca788-129">例如，您可以編輯檔案之後，它看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="ca788-129">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="ca788-130">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="ca788-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="ca788-131">開啟 [記事本] 中的 DisableManifestXml.reg 檔案變更值`False`以`True`，然後儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="ca788-131">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="ca788-132">例如，您可以編輯檔案之後，它看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="ca788-132">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="ca788-133">在 Windows 檔案總管] 中，按一下或按兩下您在上一個步驟中編輯.reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="ca788-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="ca788-134">在 [使用者存取控制] 視窗中，按一下 [ **]** 讓登錄編輯程式中進行的變更。</span><span class="sxs-lookup"><span data-stu-id="ca788-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="ca788-135">出現提示時若要繼續，按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="ca788-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="ca788-136">登錄編輯程式中會顯示訊息，說明設定已成功新增至登錄。</span><span class="sxs-lookup"><span data-stu-id="ca788-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="ca788-137">停用匯出報告相關的常見問題集</span><span class="sxs-lookup"><span data-stu-id="ca788-137">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="ca788-138">**什麼是 Results.csv 和 Manifest.xml 報告？**</span><span class="sxs-lookup"><span data-stu-id="ca788-138">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="ca788-139">將 Results.csv 和 Manifest.xml 檔案包含匯出內容相關的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="ca788-139">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="ca788-140">**Results.csv** Excel 文件包含在搜尋結果會下載每個項目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ca788-140">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="ca788-141">電子郵件，結果記錄檔會包含每個郵件的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="ca788-141">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="ca788-142">來源信箱中的郵件的位置 (包括郵件是否處於主要或封存信箱)。</span><span class="sxs-lookup"><span data-stu-id="ca788-142">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="ca788-143">郵件已傳送或接收的日期。</span><span class="sxs-lookup"><span data-stu-id="ca788-143">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="ca788-144">從郵件主旨行。</span><span class="sxs-lookup"><span data-stu-id="ca788-144">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="ca788-145">寄件者和收件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="ca788-145">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="ca788-146">郵件是否重複的郵件如果匯出搜尋結果時，啟用重複資料刪除。</span><span class="sxs-lookup"><span data-stu-id="ca788-146">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="ca788-147">重複的郵件將會在**父項目識別碼**] 欄中識別為重複郵件具有值。</span><span class="sxs-lookup"><span data-stu-id="ca788-147">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="ca788-148">**父項目識別碼**] 欄中的值是匯出之郵件的 [**項目 DocumentId** ] 欄中的值相同。</span><span class="sxs-lookup"><span data-stu-id="ca788-148">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="ca788-149">文件的 SharePoint 和 OneDrive for Business 網站，結果記錄檔包含每個文件的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="ca788-149">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="ca788-150">文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="ca788-150">The URL for the document.</span></span>
    
  - <span data-ttu-id="ca788-151">文件所在之網站集合的 URL。</span><span class="sxs-lookup"><span data-stu-id="ca788-151">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="ca788-152">上次修改文件的日期。</span><span class="sxs-lookup"><span data-stu-id="ca788-152">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="ca788-153">（這位於結果記錄檔中的 [主旨] 欄） 的文件的名稱。</span><span class="sxs-lookup"><span data-stu-id="ca788-153">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="ca788-154">**Manifest.xml**中資訊清單檔案 （XML 格式），其中包含搜尋結果中包含每個項目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ca788-154">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="ca788-155">此報告中的資訊會與 [Results.csv] 報告中，相同，但它的格式指定所電子搜索參照模型 (EDRM)。</span><span class="sxs-lookup"><span data-stu-id="ca788-155">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="ca788-156">如需有關 EDRM 的詳細資訊，請移至[https://www.edrm.net](https://www.edrm.net)。</span><span class="sxs-lookup"><span data-stu-id="ca788-156">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="ca788-157">**何時應該停用匯出這些報告？**</span><span class="sxs-lookup"><span data-stu-id="ca788-157">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="ca788-158">這取決於您的特定需求。</span><span class="sxs-lookup"><span data-stu-id="ca788-158">It depends on your specific needs.</span></span> <span data-ttu-id="ca788-159">許多組織不需要搜尋結果的其他資訊，而不需要這些報告。</span><span class="sxs-lookup"><span data-stu-id="ca788-159">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="ca788-160">**我有執行這項作業電腦為何？**</span><span class="sxs-lookup"><span data-stu-id="ca788-160">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="ca788-161">您必須變更您在執行 Office 365 電子文件探索匯出工具的任何本機電腦上的登錄設定。</span><span class="sxs-lookup"><span data-stu-id="ca788-161">You have to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="ca788-162">**變更此設定之後，我有重新啟動電腦？**</span><span class="sxs-lookup"><span data-stu-id="ca788-162">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="ca788-163">否，您不需要重新啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="ca788-163">No, you don't have to restart the computer.</span></span> <span data-ttu-id="ca788-164">但如果執行 Office 365 電子文件探索匯出工具，您必須關閉它，然後重新啟動它之後變更的登錄設定。</span><span class="sxs-lookup"><span data-stu-id="ca788-164">But if the Office 365 eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="ca788-165">**沒有現有的登錄機碼取得編輯或沒有取得建立新的金鑰嗎？**</span><span class="sxs-lookup"><span data-stu-id="ca788-165">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="ca788-166">新的登錄機碼會建立第一次執行您在本主題中的程序中建立的.reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="ca788-166">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="ca788-167">然後設定編輯的每當您變更，然後重新執行.reg 編輯檔案。</span><span class="sxs-lookup"><span data-stu-id="ca788-167">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
