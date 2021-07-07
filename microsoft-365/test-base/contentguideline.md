---
title: 測試套件指導方針
description: 回顧有關測試套件的指導方針
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322586"
---
# <a name="test-package-guidelines"></a><span data-ttu-id="3bf84-103">測試套件指導方針</span><span class="sxs-lookup"><span data-stu-id="3bf84-103">Test package guidelines</span></span>

## <a name="1---script-referencing"></a><span data-ttu-id="3bf84-104">1. 腳本參考</span><span class="sxs-lookup"><span data-stu-id="3bf84-104">1.   Script referencing</span></span>

<span data-ttu-id="3bf84-105">當您將 .zip 檔案上傳至入口網站時，會將該檔案的所有內容解壓縮至根資料夾。</span><span class="sxs-lookup"><span data-stu-id="3bf84-105">When you upload a .zip file to the portal, we unzip all the content of that file into a root folder.</span></span> <span data-ttu-id="3bf84-106">您不需要撰寫任何程式碼即可執行此初始解壓縮作業。</span><span class="sxs-lookup"><span data-stu-id="3bf84-106">You do not need to write any code to do this initial unzip operation.</span></span> <span data-ttu-id="3bf84-107">您也可以使用相對於所上傳的 zip 檔案的路徑，參考 .zip 內的任何檔案。</span><span class="sxs-lookup"><span data-stu-id="3bf84-107">You also can reference any file within the .zip by using the path relative to the zip file uploaded.</span></span>

<span data-ttu-id="3bf84-108">在下列範例中，我們會示範如何從 [任務] 索引標籤的 [輸入] 欄位中參照二進位檔案/腳本。藍色的文字應該輸入 [**腳本路徑**] 欄位中，**而不需要用引號** 括住。</span><span class="sxs-lookup"><span data-stu-id="3bf84-108">In the example below, we show how you can reference your binaries/scripts from the input field in the Tasks tab. The text in blue should be entered into the **Script path** field **without the quotation marks.**</span></span>

<span data-ttu-id="3bf84-109">請務必注意，在上傳之前，您的 zip 檔案中的內容。</span><span class="sxs-lookup"><span data-stu-id="3bf84-109">It is important you are aware of the content within your zip file before uploading it.</span></span> <span data-ttu-id="3bf84-110">當您將資料夾壓縮時，您的本機機器會在 zip 檔案下建立一個主資料夾。</span><span class="sxs-lookup"><span data-stu-id="3bf84-110">Often when zipping a folder, your local machine will create a main folder underneath the zip file.</span></span> <span data-ttu-id="3bf84-111">在此情況下，參考將會如下列 **粗體** 所示：</span><span class="sxs-lookup"><span data-stu-id="3bf84-111">In this case, the referencing will be as shown in **bold** below:</span></span>

 <span data-ttu-id="3bf84-112">**Contoso_App_Folder.zip**</span><span class="sxs-lookup"><span data-stu-id="3bf84-112">**Contoso_App_Folder.zip**</span></span>
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - <span data-ttu-id="3bf84-113">ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="3bf84-113">ScriptX.ps1 – **“Contoso_App_Folder/ScriptX.ps1”**</span></span>
  - <span data-ttu-id="3bf84-114">Script.ps1 – **"Contoso_App_Folder/folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="3bf84-114">Script.ps1 – **“Contoso_App_Folder/folder1/script.ps1”**</span></span>

<span data-ttu-id="3bf84-115">其他情況下，您的 zip 檔案可能會有您的檔案或內容，但沒有第二層資料夾：</span><span class="sxs-lookup"><span data-stu-id="3bf84-115">Other times, your zip file may have your files or content right underneath it i.e. no 2nd-level folder:</span></span>

 <span data-ttu-id="3bf84-116">**Zip_file_uploaded.zip**</span><span class="sxs-lookup"><span data-stu-id="3bf84-116">**Zip_file_uploaded.zip**</span></span>
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="3bf84-117">ScriptX.ps1 – **"ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="3bf84-117">ScriptX.ps1 – **“ScriptX.ps1”**</span></span>
  - <span data-ttu-id="3bf84-118">Script.ps1 – **"folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="3bf84-118">Script.ps1 – **“folder1/script.ps1”**</span></span>
  
## <a name="2---script-execution"></a><span data-ttu-id="3bf84-119">2. 腳本執行</span><span class="sxs-lookup"><span data-stu-id="3bf84-119">2.   Script execution</span></span>

<span data-ttu-id="3bf84-120">**Out-of-Box 測試：** 應用程式套件至少要包含三個 PowerShell 腳本，可執行應用程式及其相依專案的自動安裝、啟動和關閉。</span><span class="sxs-lookup"><span data-stu-id="3bf84-120">**Out-of-Box tests:** The application package needs to contain at least three PowerShell scripts that will execute unattended installing, launching, and closing of the application and its dependencies.</span></span> <span data-ttu-id="3bf84-121">每個腳本都應該處理其自己的必要條件、驗證成功，以及在必要的情況下 (執行) 。</span><span class="sxs-lookup"><span data-stu-id="3bf84-121">Each script should handle checking its own prerequisites, validating it succeeded, as well as cleaning up after itself (if necessary).</span></span>

<span data-ttu-id="3bf84-122">**功能測試：** 應用程式套件必須包含至少一個 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="3bf84-122">**Functional tests:** The application package needs to contain at least one PowerShell script.</span></span> <span data-ttu-id="3bf84-123">在提供多個腳本的情況下，腳本會在上傳順序中執行，而在特定腳本中的失敗將停止執行後續的腳本。</span><span class="sxs-lookup"><span data-stu-id="3bf84-123">Where more than one script is provided, the scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>

### <a name="script-requirements"></a><span data-ttu-id="3bf84-124">腳本需求</span><span class="sxs-lookup"><span data-stu-id="3bf84-124">Script requirements</span></span>

<span data-ttu-id="3bf84-125">• PowerShell 5.1 版以上的版本 +</span><span class="sxs-lookup"><span data-stu-id="3bf84-125">•   PowerShell Version 5.1+</span></span>     

<span data-ttu-id="3bf84-126">•自動執行</span><span class="sxs-lookup"><span data-stu-id="3bf84-126">•   Unattended execution</span></span>    

<span data-ttu-id="3bf84-127">•錯誤回復碼</span><span class="sxs-lookup"><span data-stu-id="3bf84-127">•   Error return code</span></span>               

<span data-ttu-id="3bf84-128">•驗證成功</span><span class="sxs-lookup"><span data-stu-id="3bf84-128">•   Validate success</span></span>            

<span data-ttu-id="3bf84-129">•記錄至腳本特定記錄資料夾</span><span class="sxs-lookup"><span data-stu-id="3bf84-129">•   Logging to script specific log folder</span></span>

<span data-ttu-id="3bf84-130">在測試管線中，每個腳本都必須完全以無人值守的方式執行。</span><span class="sxs-lookup"><span data-stu-id="3bf84-130">Each script needs to run completely unattended to successfully execute in the test pipeline.</span></span>

> [!Note]
> <span data-ttu-id="3bf84-131">在成功完成時，腳本應會傳回 "0"，如果執行期間發生任何錯誤，則為非零錯誤代碼。</span><span class="sxs-lookup"><span data-stu-id="3bf84-131">Scripts should return “0” on successful completion and a non-zero error code if any error occurs during execution.</span></span>

<span data-ttu-id="3bf84-132">每個腳本應該會驗證它是否順利運行。</span><span class="sxs-lookup"><span data-stu-id="3bf84-132">Each script should validate that it ran successfully.</span></span> <span data-ttu-id="3bf84-133">舉例來說.</span><span class="sxs-lookup"><span data-stu-id="3bf84-133">E.g.</span></span> <span data-ttu-id="3bf84-134">安裝腳本應該檢查是否存在系統上的某些二進位代碼和/或登錄機碼，在安裝程式二進位檔執行完畢後，請確定安裝成功的適當程度。</span><span class="sxs-lookup"><span data-stu-id="3bf84-134">the install script should check for the existence of certain binaries and/or registry keys on the system, after the installer binary finishes executing to ensure with a reasonable degree of confidence that the installation was successful.</span></span> 

<span data-ttu-id="3bf84-135">若要正確診斷測試執行期間發生錯誤的情況，這是必要的，例如，無法成功安裝應用程式，而不能啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="3bf84-135">This is necessary to properly diagnose where errors occur during a test run, e.g. unable to install the application successfully versus being unable to launch it.</span></span>

> [!Important]
> <span data-ttu-id="3bf84-136">請 **避免下列情況：** 腳本不應該重新開機電腦，如果有必要重新開機，請在腳本上載期間指定此項。</span><span class="sxs-lookup"><span data-stu-id="3bf84-136">**Avoid the following:** Scripts should not reboot the machine, if a reboot is necessary please specify this during the upload of your scripts.</span></span>

## <a name="3---log-collection"></a><span data-ttu-id="3bf84-137">3. 記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="3bf84-137">3.   Log collection</span></span>

<span data-ttu-id="3bf84-138">每個腳本都應該輸出其所產生的任何記錄到名為的資料夾中 ```logs``` 。</span><span class="sxs-lookup"><span data-stu-id="3bf84-138">Each script should output any logs it generates into a folder named ```logs```.</span></span> <span data-ttu-id="3bf84-139">名為的目錄中的所有資料夾 ```logs``` ，將會複製並提交至頁面上供下載 ```Test Results``` 。</span><span class="sxs-lookup"><span data-stu-id="3bf84-139">All folders in the directory named ```logs``` will be copied and presented for download on the ```Test Results``` page.</span></span>

<span data-ttu-id="3bf84-140">例如，安裝腳本 (可能位於 **應用程式/腳本/安裝** 目錄) 中，可將其記錄輸出至：記錄檔 **/安裝記錄** 檔，最後的記錄將位於： **Apps/script/install/logs/install .log。**</span><span class="sxs-lookup"><span data-stu-id="3bf84-140">For example, the installation script (which may be located in the **App/scripts/install** directory) can output its logs to: **logs/install.log**, such that the final log will be at: **Apps/scripts/install/logs/install.log**</span></span>

<span data-ttu-id="3bf84-141">系統會同時選取檔案及其他 ```install.log``` 資料夾中的其他檔案 ```logs``` ，並將其重新整理以供下載。</span><span class="sxs-lookup"><span data-stu-id="3bf84-141">The system will pick up the ```install.log``` file along with other files within other ```logs``` folders and collate it for download.</span></span>


## <a name="4---application-binaries"></a><span data-ttu-id="3bf84-142">4. 應用程式二進位檔案</span><span class="sxs-lookup"><span data-stu-id="3bf84-142">4.   Application binaries</span></span>

<span data-ttu-id="3bf84-143">任何二進位檔案和相依性應包含在單一 zip 檔案中。</span><span class="sxs-lookup"><span data-stu-id="3bf84-143">Any binaries and dependencies should be included in the single zip file.</span></span> 

<span data-ttu-id="3bf84-144">這些都應該包括安裝應用程式所需的一切 (例如，應用程式安裝程式) ;若應用程式對任何 framework （如 .net Core/Standard or .NET Framework）都有相依性，這些元件應該會包含在檔案中，並可在所提供的腳本中正確地加以參照。</span><span class="sxs-lookup"><span data-stu-id="3bf84-144">These should include everything necessary for installation of the application (e.g. the application installer); if the application has a dependency on any frameworks, such as .NET Core/Standard or .NET Framework, these should be included in the file and referenced correctly in the provided scripts.</span></span>


> [!Note]
> <span data-ttu-id="3bf84-145">上傳的 zip 檔案名稱中不能有任何空格或特殊字元</span><span class="sxs-lookup"><span data-stu-id="3bf84-145">The uploaded zip file cannot have any spaces or special characters in its name</span></span>

## <a name="next-steps"></a><span data-ttu-id="3bf84-146">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3bf84-146">Next steps</span></span>

<span data-ttu-id="3bf84-147">請移至下一篇，以查看一些常見問題 **(常見問題)**</span><span class="sxs-lookup"><span data-stu-id="3bf84-147">Advance to the next article to view some **Frequently Asked Questions (FAQ)**</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="3bf84-148">下一步</span><span class="sxs-lookup"><span data-stu-id="3bf84-148">Next step</span></span>](faq.md)
