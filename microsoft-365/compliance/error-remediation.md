---
title: 處理調查的資料時的錯誤修正
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
description: ''
ms.openlocfilehash: 524378ecb7ec7cd8285e7d1ccda5667aa6081f30
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634891"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="e54c7-102">處理調查的資料時的錯誤修正</span><span class="sxs-lookup"><span data-stu-id="e54c7-102">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="e54c7-103">錯誤修正功能可讓調查人員修正資料問題，以防止資料調查（預覽）正確地處理內容。</span><span class="sxs-lookup"><span data-stu-id="e54c7-103">Error remediation allows investigators the ability to rectify data issues that prevent Data Investigations (Preview) from properly processing the content.</span></span> <span data-ttu-id="e54c7-104">例如，因為檔案遭到鎖定或加密，所以無法處理受密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="e54c7-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="e54c7-105">使用錯誤修正，調查人員可以下載具有這類錯誤的檔案、移除密碼保護，並上傳補救的檔案。</span><span class="sxs-lookup"><span data-stu-id="e54c7-105">Using error remediation, investigators can download files with such errors, remove the password protection, and upload the remediated files.</span></span>

<span data-ttu-id="e54c7-106">使用下列工作流程修正資料調查（預覽）案例中發生錯誤的檔案。</span><span class="sxs-lookup"><span data-stu-id="e54c7-106">Use the following workflow to remediate files with errors in Data Investigations (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="e54c7-107">建立錯誤修正會話，以修正具有處理錯誤的檔案</span><span class="sxs-lookup"><span data-stu-id="e54c7-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="e54c7-108">如果在下列程式中隨時關閉錯誤修正嚮導，您可以在 [ **View** ] 下拉式功能表中選取 [**錯誤 remediations** ]，從 [**處理**] 索引標籤回到錯誤修正會話。</span><span class="sxs-lookup"><span data-stu-id="e54c7-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="e54c7-109">在 [資料調查] 中的 [**處理**] 索引標籤上，于 [ **View** ] 下拉式功能表中選取 [**錯誤**]。</span><span class="sxs-lookup"><span data-stu-id="e54c7-109">On the **Processing** tab in a data investigation, select **Errors** in the **View** dropdown menu.</span></span>

2. <span data-ttu-id="e54c7-110">按一下 [錯誤類型] 或 [檔案類型] 旁邊的選項按鈕，以選取您要修正的錯誤。</span><span class="sxs-lookup"><span data-stu-id="e54c7-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="e54c7-111">在下列範例中，我們正在修正受密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="e54c7-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="e54c7-112">按一下 [ **+ 新增錯誤修正**]。</span><span class="sxs-lookup"><span data-stu-id="e54c7-112">Click **+ New error remediation**.</span></span>

    ![錯誤修正](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="e54c7-114">「錯誤修正」會話開始，從準備階段開始，其中含有錯誤的檔案會複製到安全的 Azure 位置，以供下載。</span><span class="sxs-lookup"><span data-stu-id="e54c7-114">The error remediation session begins, starting with a preparation stage where the files with errors are copied to a secure Azure location so that they can be downloaded.</span></span>

    ![準備錯誤修正](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="e54c7-116">準備完成後，請按 **[下一步：下載檔案]** 以繼續下載。</span><span class="sxs-lookup"><span data-stu-id="e54c7-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![下載檔案](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="e54c7-118">若要下載檔案，請指定要**下載的目的地路徑**。</span><span class="sxs-lookup"><span data-stu-id="e54c7-118">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="e54c7-119">這是您的本機電腦上應下載檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="e54c7-119">This is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="e54c7-120">預設路徑%USERPROFILE%\Downloads\errors，指向登入使用者的 [下載] 資料夾;這可以視需要變更。</span><span class="sxs-lookup"><span data-stu-id="e54c7-120">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="e54c7-121">建議您使用本機檔路徑取代遠端網路路徑，以取得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="e54c7-121">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e54c7-122">若尚未安裝 AzCopy，您可以從下列位置進行安裝：https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="e54c7-122">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="e54c7-123">按一下 [**複製到剪貼**簿]，複製預先定義的命令。</span><span class="sxs-lookup"><span data-stu-id="e54c7-123">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="e54c7-124">啟動 windows 命令提示字元，貼上命令，然後按**enter**鍵。</span><span class="sxs-lookup"><span data-stu-id="e54c7-124">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="e54c7-125">將會下載檔案。</span><span class="sxs-lookup"><span data-stu-id="e54c7-125">The files will be downloaded.</span></span>

    ![準備錯誤修正](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="e54c7-127">如果您在執行此命令時有問題，請參閱[Advanced eDiscovery 中的疑難排解 AzCopy](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="e54c7-127">If you have issues running this command, see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="e54c7-128">下載檔案之後，您可以使用適當的工具加以修復。</span><span class="sxs-lookup"><span data-stu-id="e54c7-128">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="e54c7-129">針對受密碼保護的檔案，您可以使用數種密碼破譯工具。</span><span class="sxs-lookup"><span data-stu-id="e54c7-129">For password protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="e54c7-130">如果您知道檔案的密碼，您可以開啟檔案並移除密碼保護。</span><span class="sxs-lookup"><span data-stu-id="e54c7-130">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    
   > [!NOTE]
    > <span data-ttu-id="e54c7-131">您必須保留已修正檔案的目錄結構及檔案名，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="e54c7-131">It's important that you retain the directory structure and file names of the remediated files.</span></span> <span data-ttu-id="e54c7-132">已下載的檔案和資料夾的路徑名稱，可讓修正的檔案與原始檔案產生關聯。</span><span class="sxs-lookup"><span data-stu-id="e54c7-132">The path names of the downloaded files and folders make it possible to associate the remediated files with the original files.</span></span>  <span data-ttu-id="e54c7-133">如果目錄結構或檔案名已變更，您會收到下列錯誤： `Cannot apply Error Remediation to the current Evidenceset`。</span><span class="sxs-lookup"><span data-stu-id="e54c7-133">If the directory structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Evidenceset`.</span></span>

8. <span data-ttu-id="e54c7-134">現在，回到 [資料調查（預覽）]，然後按 **[下一步：上傳檔案]**。</span><span class="sxs-lookup"><span data-stu-id="e54c7-134">Now, return to Data Investigations (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="e54c7-135">這會移至下一個您現在可以上傳檔案的步驟。</span><span class="sxs-lookup"><span data-stu-id="e54c7-135">This will move to the next step where you can now upload the files.</span></span>

    ![上傳檔案](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="e54c7-137">在 [檔案**位置**] 文字方塊中指定已修正檔案的位置，然後按一下 [**複製到剪貼**簿]。</span><span class="sxs-lookup"><span data-stu-id="e54c7-137">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="e54c7-138">將命令貼到 Windows 命令提示字元，然後按**enter**上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="e54c7-138">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6 .png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="e54c7-140">最後，回到 [資料調查（預覽）]，然後按 **[下一步：處理檔案]**。</span><span class="sxs-lookup"><span data-stu-id="e54c7-140">Finally, return to Data Investigations (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="e54c7-141">處理完成時。</span><span class="sxs-lookup"><span data-stu-id="e54c7-141">When processing is complete.</span></span>  <span data-ttu-id="e54c7-142">您可以回到工作集，並查看修正的檔案。</span><span class="sxs-lookup"><span data-stu-id="e54c7-142">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="e54c7-143">修正檔案時會發生什麼情況</span><span class="sxs-lookup"><span data-stu-id="e54c7-143">What happens when files are remediated</span></span>

<span data-ttu-id="e54c7-144">在上傳補救的檔案時，除了下欄欄位之外，仍會保留原始的中繼資料：</span><span class="sxs-lookup"><span data-stu-id="e54c7-144">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="e54c7-145">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="e54c7-145">ExtractedTextSize</span></span>
- <span data-ttu-id="e54c7-146">HasText</span><span class="sxs-lookup"><span data-stu-id="e54c7-146">HasText</span></span>
- <span data-ttu-id="e54c7-147">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="e54c7-147">IsErrorRemediate</span></span>
- <span data-ttu-id="e54c7-148">LoadId</span><span class="sxs-lookup"><span data-stu-id="e54c7-148">LoadId</span></span>
- <span data-ttu-id="e54c7-149">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="e54c7-149">ProcessingErrorMessage</span></span>
- <span data-ttu-id="e54c7-150">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="e54c7-150">ProcessingStatus</span></span>
- <span data-ttu-id="e54c7-151">文字</span><span class="sxs-lookup"><span data-stu-id="e54c7-151">Text</span></span>
- <span data-ttu-id="e54c7-152">WordCount</span><span class="sxs-lookup"><span data-stu-id="e54c7-152">WordCount</span></span>
- <span data-ttu-id="e54c7-153">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="e54c7-153">WorkingsetId</span></span>

<span data-ttu-id="e54c7-154">如需資料調查（預覽）中所有檔元資料欄位的定義，請參閱[檔元資料欄位](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="e54c7-154">For a definition of all document metadata fields in Data Investigations (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
