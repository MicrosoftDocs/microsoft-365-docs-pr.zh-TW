---
title: 處理資料時的錯誤補救
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 瞭解如何使用錯誤修正功能，修正可避免正確處理內容的高級 eDiscovery 中的資料問題。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8ada53dd6339541fc39b37903a0f58fd4ad84c8c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035907"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="a3d83-103">處理資料時的錯誤補救</span><span class="sxs-lookup"><span data-stu-id="a3d83-103">Error remediation when processing data</span></span>

<span data-ttu-id="a3d83-104">錯誤修正功能可讓 eDiscovery 系統管理員修正資料問題，使「高級 eDiscovery」無法正確地處理內容。</span><span class="sxs-lookup"><span data-stu-id="a3d83-104">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="a3d83-105">例如，因為檔案遭到鎖定或加密，所以無法處理受密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d83-105">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="a3d83-106">使用錯誤修正，eDiscovery 管理員可以下載具有這類錯誤的檔案、移除密碼保護，然後上傳補救的檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d83-106">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="a3d83-107">使用下列工作流程修正高級 eDiscovery 案例中發生錯誤的檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d83-107">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="a3d83-108">建立錯誤修正會話，以修正具有處理錯誤的檔案</span><span class="sxs-lookup"><span data-stu-id="a3d83-108">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="a3d83-109">如果在下列程式中隨時關閉錯誤修正嚮導，您可以從 [處理] 索引標籤中選取 [ **Remediations** **]，以**回到 [**處理**] 索引標籤中的 [錯誤修正] 會話。</span><span class="sxs-lookup"><span data-stu-id="a3d83-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="a3d83-110">在 [高級 eDiscovery] 案例中的 [**處理**] 索引標籤上，選取 [**視圖**] 下拉式功能表中的 [**錯誤**]，然後選取 [**範圍**] 下拉式功能表中的審閱集或整個案例。</span><span class="sxs-lookup"><span data-stu-id="a3d83-110">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="a3d83-111">本節顯示所有來自特定審查集之案例或錯誤的錯誤。</span><span class="sxs-lookup"><span data-stu-id="a3d83-111">This section displays all errors from the case or error from a specific review set.</span></span>

   ![錯誤修正](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="a3d83-113">按一下 [錯誤類型] 或 [檔案類型] 旁邊的選項按鈕，以選取您要修正的錯誤。</span><span class="sxs-lookup"><span data-stu-id="a3d83-113">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="a3d83-114">在下列範例中，我們正在修正受密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d83-114">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="a3d83-115">按一下 [**新增錯誤修正**]。</span><span class="sxs-lookup"><span data-stu-id="a3d83-115">Click **New error remediation**.</span></span>

    <span data-ttu-id="a3d83-116">錯誤修正工作流程會從準備階段開始，其中有錯誤的檔案會複製到 Microsoft 提供的 Azure 儲存位置，這樣您就可以將這些檔案下載到您的本機電腦以進行修正。</span><span class="sxs-lookup"><span data-stu-id="a3d83-116">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![準備錯誤修正](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="a3d83-118">準備完成後，請按 **[下一步：下載檔案]** 以繼續下載。</span><span class="sxs-lookup"><span data-stu-id="a3d83-118">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![下載檔案](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="a3d83-120">若要下載檔案，請指定要**下載的目的地路徑**。</span><span class="sxs-lookup"><span data-stu-id="a3d83-120">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="a3d83-121">這是您的本機電腦上將下載檔案的上層資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="a3d83-121">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="a3d83-122">預設路徑%USERPROFILE%\Downloads\errors，指向登入使用者的 [下載] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a3d83-122">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="a3d83-123">您可以視需要變更此路徑。</span><span class="sxs-lookup"><span data-stu-id="a3d83-123">You can change this path if desired.</span></span> <span data-ttu-id="a3d83-124">如果您進行變更，建議您使用本機檔路徑，以取得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="a3d83-124">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="a3d83-125">請勿使用遠端網路路徑。</span><span class="sxs-lookup"><span data-stu-id="a3d83-125">Don't use a remote network path.</span></span> <span data-ttu-id="a3d83-126">例如，您可以使用路徑**C:\Remediation**。</span><span class="sxs-lookup"><span data-stu-id="a3d83-126">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="a3d83-127">父資料夾的路徑會自動新增至 AzCopy 命令（如 **/Dest**參數的值）。</span><span class="sxs-lookup"><span data-stu-id="a3d83-127">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="a3d83-128">按一下 [**複製到剪貼**簿]，複製預先定義的命令。</span><span class="sxs-lookup"><span data-stu-id="a3d83-128">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="a3d83-129">開啟 Windows 命令提示字元，貼上 AzCopy 命令，然後按**enter**鍵。</span><span class="sxs-lookup"><span data-stu-id="a3d83-129">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![準備進行錯誤修正](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="a3d83-131">您必須使用 AzCopy app-v 8.1 才能成功使用**下載**檔案頁面上提供的命令。</span><span class="sxs-lookup"><span data-stu-id="a3d83-131">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="a3d83-132">您也必須使用 AzCopy app-v 8.1 上傳步驟10中的檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d83-132">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="a3d83-133">若要安裝這 AzCopy 版本，請參閱[在 Windows 上使用 AzCopy 中的「傳送資料](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)」。</span><span class="sxs-lookup"><span data-stu-id="a3d83-133">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="a3d83-134">如果提供的 AzCopy 命令失敗，請參閱[Advanced eDiscovery 中的疑難排解 AzCopy](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d83-134">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="a3d83-135">您選取的檔案會下載到您在步驟5中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="a3d83-135">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="a3d83-136">在上層資料夾中（例如， **C:\Remediation**），會自動建立下列子資料夾結構：</span><span class="sxs-lookup"><span data-stu-id="a3d83-136">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="a3d83-137">*子資料夾 1*是以 case 或複查集的識別碼命名，取決於您在步驟1中所選取的範圍。</span><span class="sxs-lookup"><span data-stu-id="a3d83-137">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="a3d83-138">*子資料夾 2*以下載檔案的檔案識別碼命名</span><span class="sxs-lookup"><span data-stu-id="a3d83-138">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="a3d83-139">下載的檔案位於*子資料夾 2*中，也是以檔識別碼命名。</span><span class="sxs-lookup"><span data-stu-id="a3d83-139">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="a3d83-140">以下是將專案下載至**C:\Remediation**父系資料夾時所建立的資料夾路徑和錯誤檔案名範例：</span><span class="sxs-lookup"><span data-stu-id="a3d83-140">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="a3d83-141">如果下載多個檔案，則每個檔案都會下載到以檔識別碼命名的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="a3d83-141">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a3d83-142">當您在步驟9和步驟10中上傳檔案時，修正的檔案必須具有相同的檔案名，而且必須位於相同的子資料夾結構中。</span><span class="sxs-lookup"><span data-stu-id="a3d83-142">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="a3d83-143">子資料夾和檔案名用於關聯修正的檔案與原始錯誤檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d83-143">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="a3d83-144">如果資料夾結構或檔案名已變更，您會收到下列錯誤： `Cannot apply Error Remediation to the current Workingset`。</span><span class="sxs-lookup"><span data-stu-id="a3d83-144">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="a3d83-145">為了避免發生任何問題，我們建議您將修正的檔案保持在相同的父資料夾及子資料夾結構。</span><span class="sxs-lookup"><span data-stu-id="a3d83-145">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="a3d83-146">下載檔案之後，您可以使用適當的工具加以修復。</span><span class="sxs-lookup"><span data-stu-id="a3d83-146">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="a3d83-147">對於密碼保護的檔案，您可以使用數種密碼破譯工具。</span><span class="sxs-lookup"><span data-stu-id="a3d83-147">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="a3d83-148">如果您知道檔案的密碼，您可以開啟檔案並移除密碼保護。</span><span class="sxs-lookup"><span data-stu-id="a3d83-148">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="a3d83-149">回到 [Advanced eDiscovery] 和 [錯誤修正嚮導]，然後按一下 **[下一步：上傳**檔案]。</span><span class="sxs-lookup"><span data-stu-id="a3d83-149">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="a3d83-150">這會移至下一個頁面，您現在可以上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d83-150">This moves to the next page where you can now upload the files.</span></span>

    ![上傳檔案](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="a3d83-152">在 [檔案位置] 文字方塊中指定**可**修正檔案所在的父資料夾。</span><span class="sxs-lookup"><span data-stu-id="a3d83-152">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="a3d83-153">同樣地，上層資料夾必須具有下載檔案時所建立的相同子資料夾結構。</span><span class="sxs-lookup"><span data-stu-id="a3d83-153">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="a3d83-154">父資料夾的路徑會自動新增至 AzCopy 命令（如 **/source**參數的值）。</span><span class="sxs-lookup"><span data-stu-id="a3d83-154">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="a3d83-155">按一下 [**複製到剪貼**簿]，複製預先定義的命令。</span><span class="sxs-lookup"><span data-stu-id="a3d83-155">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="a3d83-156">開啟 Windows 命令提示字元，貼上 AzCopy 命令，然後按**enter**鍵。</span><span class="sxs-lookup"><span data-stu-id="a3d83-156">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="a3d83-157">上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d83-157">upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6 .png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="a3d83-159">在您執行 AzCopy 命令之後，請按 **[下一步：處理檔案]**。</span><span class="sxs-lookup"><span data-stu-id="a3d83-159">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="a3d83-160">處理完成時，您可以移至 [複查] 設定並查看修正的檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d83-160">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="remediating-errors-in-container-files"></a><span data-ttu-id="a3d83-161">在容器檔案中修正錯誤</span><span class="sxs-lookup"><span data-stu-id="a3d83-161">Remediating errors in container files</span></span>

<span data-ttu-id="a3d83-162">在使用「高級 eDiscovery」提取容器檔案（例如 .zip 檔案）內容的情況下，可以下載容器，並將內容擴充至原始容器所在的相同資料夾中。</span><span class="sxs-lookup"><span data-stu-id="a3d83-162">In situations when the contents of a container file (such as a .zip file) can't be extracted by Advanced eDiscovery, the containers can be downloaded and the contents expanded into the same folder in which the original container resides.</span></span> <span data-ttu-id="a3d83-163">展開的檔案會被視為父容器，就像它最初是由高級 eDiscovery 展開。</span><span class="sxs-lookup"><span data-stu-id="a3d83-163">The expanded files will be attributed to the parent container as if it was originally expanded by Advanced eDiscovery.</span></span> <span data-ttu-id="a3d83-164">程式的運作方式如上述所述，除了將單一檔案上傳為取代檔案之外。</span><span class="sxs-lookup"><span data-stu-id="a3d83-164">The process works as described as above except for uploading a single file as the replacement file.</span></span>  <span data-ttu-id="a3d83-165">當您上傳修正的檔案時，請勿包含原始的容器檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d83-165">When you upload remediated files, don't include the original container file.</span></span>

## <a name="remediating-errors-by-uploading-the-extracted-text"></a><span data-ttu-id="a3d83-166">上傳解壓縮的文字修正錯誤</span><span class="sxs-lookup"><span data-stu-id="a3d83-166">Remediating errors by uploading the extracted text</span></span>

<span data-ttu-id="a3d83-167">有時候，您無法將檔案修正為可供「高級 eDiscovery」轉譯的原生格式。</span><span class="sxs-lookup"><span data-stu-id="a3d83-167">Sometimes it's not possible to remediate a file to native format that Advanced eDiscovery can interpret.</span></span> <span data-ttu-id="a3d83-168">不過，您可以使用文字檔取代原始檔案，該文字檔包含原生檔案的原始文字（位於稱為「*文字覆蓋*」的程式中）。</span><span class="sxs-lookup"><span data-stu-id="a3d83-168">But you can replace the original file with a text file that contains the original text of the native file (in a process called *text overlay*).</span></span> <span data-ttu-id="a3d83-169">若要這麼做，請遵循本文所述的步驟，但不是以原生格式修正原始檔案，您可以建立文字檔，其中包含原始檔案中的解壓縮文字，然後使用以 .txt 尾碼附加的原始檔案名上傳文字檔。</span><span class="sxs-lookup"><span data-stu-id="a3d83-169">To do this, follow the steps described in this article but instead of remediating the original file in the native format, you would create a text file that contains the extracted text from the original file, and then upload the text file using the original filename appended with a .txt suffix.</span></span> <span data-ttu-id="a3d83-170">例如，您可以使用檔案名335850cc-6602-4af0-acfa-1d14d9128ca2，在修正糾錯期間下載檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d83-170">For example, you download a file during error remediation with the filename 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span></span> <span data-ttu-id="a3d83-171">您可以在原生應用程式中開啟檔案、複製文字，然後將它貼到新的名為335850cc-6602-4af0-acfa-1d14d9128ca2 的檔案中。</span><span class="sxs-lookup"><span data-stu-id="a3d83-171">You open the file in the native application, copy the text, and then paste it into a new file named 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span></span> <span data-ttu-id="a3d83-172">當您執行此動作時，請務必先在本機電腦上從修正的檔案位置移除原始檔案，然後再將修正的文字檔上傳至「Advanced eDiscovery」。</span><span class="sxs-lookup"><span data-stu-id="a3d83-172">When you do this, be sure to remove the original file in the native format from the remediated file location on your local computer before uploading the remediated text file to Advanced eDiscovery.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="a3d83-173">修正檔案時會發生什麼情況</span><span class="sxs-lookup"><span data-stu-id="a3d83-173">What happens when files are remediated</span></span>

<span data-ttu-id="a3d83-174">在上傳補救的檔案時，除了下欄欄位之外，仍會保留原始的中繼資料：</span><span class="sxs-lookup"><span data-stu-id="a3d83-174">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="a3d83-175">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="a3d83-175">ExtractedTextSize</span></span>
- <span data-ttu-id="a3d83-176">HasText</span><span class="sxs-lookup"><span data-stu-id="a3d83-176">HasText</span></span>
- <span data-ttu-id="a3d83-177">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="a3d83-177">IsErrorRemediate</span></span>
- <span data-ttu-id="a3d83-178">LoadId</span><span class="sxs-lookup"><span data-stu-id="a3d83-178">LoadId</span></span>
- <span data-ttu-id="a3d83-179">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="a3d83-179">ProcessingErrorMessage</span></span>
- <span data-ttu-id="a3d83-180">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="a3d83-180">ProcessingStatus</span></span>
- <span data-ttu-id="a3d83-181">文字</span><span class="sxs-lookup"><span data-stu-id="a3d83-181">Text</span></span>
- <span data-ttu-id="a3d83-182">WordCount</span><span class="sxs-lookup"><span data-stu-id="a3d83-182">WordCount</span></span>
- <span data-ttu-id="a3d83-183">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="a3d83-183">WorkingsetId</span></span>

<span data-ttu-id="a3d83-184">如需高級 eDiscovery 中所有元資料欄位的定義，請參閱[檔元資料欄位](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d83-184">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
