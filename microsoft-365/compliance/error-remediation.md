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
description: 瞭解如何使用錯誤修正功能，修正資料調查 (預覽) 中可能會妨礙內容正確處理的資料問題。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: c6c62bb1a3191e369d553df5eb451d4656e704d7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286029"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="ca4ff-103">處理調查的資料時的錯誤修正</span><span class="sxs-lookup"><span data-stu-id="ca4ff-103">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="ca4ff-104">錯誤修正功能可讓調查人員修正資料問題，以防止資料調查 (預覽) 正確地處理內容。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-104">Error remediation allows investigators the ability to rectify data issues that prevent Data Investigations (preview) from properly processing the content.</span></span> <span data-ttu-id="ca4ff-105">例如，因為檔案遭到鎖定或加密，所以無法處理受密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-105">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="ca4ff-106">使用錯誤修正，調查人員可以下載具有這類錯誤的檔案、移除密碼保護，並上傳補救的檔案。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-106">Using error remediation, investigators can download files with such errors, remove the password protection, and upload the remediated files.</span></span>

<span data-ttu-id="ca4ff-107">使用下列工作流程修復資料調查 (預覽) 案例中發生錯誤的檔案。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-107">Use the following workflow to remediate files with errors in Data Investigations (preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="ca4ff-108">建立錯誤修正會話，以修正具有處理錯誤的檔案</span><span class="sxs-lookup"><span data-stu-id="ca4ff-108">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="ca4ff-109">如果在下列程式中隨時關閉錯誤修正嚮導，您可以在 [ **View** ] 下拉式功能表中選取 [**錯誤 remediations** ]，從 [**處理**] 索引標籤回到錯誤修正會話。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="ca4ff-110">在 [資料調查] 中的 [**處理**] 索引標籤上，于 [ **View** ] 下拉式功能表中選取 [**錯誤**]。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-110">On the **Processing** tab in a data investigation, select **Errors** in the **View** dropdown menu.</span></span>

2. <span data-ttu-id="ca4ff-111">按一下 [錯誤類型] 或 [檔案類型] 旁邊的選項按鈕，以選取您要修正的錯誤。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-111">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="ca4ff-112">在下列範例中，我們正在修正受密碼保護的檔案。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-112">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="ca4ff-113">按一下 [ **+ 新增錯誤修正**]。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-113">Click **+ New error remediation**.</span></span>

    ![按一下 [新增錯誤修正] 按鈕](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="ca4ff-115">「錯誤修正」會話開始，從準備階段開始，其中含有錯誤的檔案會複製到安全的 Azure 位置，以供下載。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-115">The error remediation session begins, starting with a preparation stage where the files with errors are copied to a secure Azure location so that they can be downloaded.</span></span>

    ![準備進行錯誤修正](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="ca4ff-117">準備完成後，請按 **[下一步：下載檔案]** 以繼續下載。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-117">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![下載需要修正的檔案](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="ca4ff-119">若要下載檔案，請指定要 **下載的目的地路徑**。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-119">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="ca4ff-120">這是您的本機電腦上應下載檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-120">This is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="ca4ff-121">預設路徑%USERPROFILE%\Downloads\errors，指向登入使用者的 [下載] 資料夾;這可以視需要變更。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-121">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="ca4ff-122">建議您使用本機檔路徑取代遠端網路路徑，以取得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-122">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca4ff-123">若尚未安裝 AzCopy，請移至 [開始使用 AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-123">If you haven't installed AzCopy, go to [Get started with AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) to install it.</span></span>

6. <span data-ttu-id="ca4ff-124">按一下 [ **複製到剪貼**簿]，複製預先定義的命令。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-124">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="ca4ff-125">啟動 windows 命令提示字元，貼上命令，然後按 **enter**鍵。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-125">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="ca4ff-126">將會下載檔案。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-126">The files will be downloaded.</span></span>

    ![在命令提示字元中下載之檔案的相關資訊](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="ca4ff-128">如果您在執行此命令時有問題，請參閱 [Advanced eDiscovery 中的疑難排解 AzCopy](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-128">If you have issues running this command, see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="ca4ff-129">下載檔案之後，您可以使用適當的工具加以修復。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-129">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="ca4ff-130">針對受密碼保護的檔案，您可以使用數種密碼破譯工具。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-130">For password protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="ca4ff-131">如果您知道檔案的密碼，您可以開啟檔案並移除密碼保護。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-131">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    
   > [!NOTE]
    > <span data-ttu-id="ca4ff-132">您必須保留已修正檔案的目錄結構及檔案名，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-132">It's important that you retain the directory structure and file names of the remediated files.</span></span> <span data-ttu-id="ca4ff-133">已下載的檔案和資料夾的路徑名稱，可讓修正的檔案與原始檔案產生關聯。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-133">The path names of the downloaded files and folders make it possible to associate the remediated files with the original files.</span></span>  <span data-ttu-id="ca4ff-134">如果目錄結構或檔案名已變更，您會收到下列錯誤： `Cannot apply Error Remediation to the current Evidenceset` 。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-134">If the directory structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Evidenceset`.</span></span>

8. <span data-ttu-id="ca4ff-135">現在，回到資料調查 (預覽) 並按 **[下一步：上傳檔案]**。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-135">Now, return to Data Investigations (preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="ca4ff-136">這會移至下一個您現在可以上傳檔案的步驟。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-136">This will move to the next step where you can now upload the files.</span></span>

    ![上傳檔案] 索引標籤](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="ca4ff-138">在 [檔案 **位置** ] 文字方塊中指定已修正檔案的位置，然後按一下 [ **複製到剪貼**簿]。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-138">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="ca4ff-139">將命令貼到 Windows 命令提示字元，然後按 **enter** 上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-139">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![在命令提示字元中上傳檔案的相關資訊](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="ca4ff-141">最後，請回到資料調查 (預覽) 並按 **[下一步：處理檔案]**。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-141">Finally, return to Data Investigations (preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="ca4ff-142">處理完成時。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-142">When processing is complete.</span></span>  <span data-ttu-id="ca4ff-143">您可以回到工作集，並查看修正的檔案。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-143">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="ca4ff-144">修正檔案時會發生什麼情況</span><span class="sxs-lookup"><span data-stu-id="ca4ff-144">What happens when files are remediated</span></span>

<span data-ttu-id="ca4ff-145">在上傳補救的檔案時，除了下欄欄位之外，仍會保留原始的中繼資料：</span><span class="sxs-lookup"><span data-stu-id="ca4ff-145">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="ca4ff-146">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="ca4ff-146">ExtractedTextSize</span></span>
- <span data-ttu-id="ca4ff-147">HasText</span><span class="sxs-lookup"><span data-stu-id="ca4ff-147">HasText</span></span>
- <span data-ttu-id="ca4ff-148">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="ca4ff-148">IsErrorRemediate</span></span>
- <span data-ttu-id="ca4ff-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="ca4ff-149">LoadId</span></span>
- <span data-ttu-id="ca4ff-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="ca4ff-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="ca4ff-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="ca4ff-151">ProcessingStatus</span></span>
- <span data-ttu-id="ca4ff-152">文字</span><span class="sxs-lookup"><span data-stu-id="ca4ff-152">Text</span></span>
- <span data-ttu-id="ca4ff-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="ca4ff-153">WordCount</span></span>
- <span data-ttu-id="ca4ff-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="ca4ff-154">WorkingsetId</span></span>

<span data-ttu-id="ca4ff-155">如需資料調查中所有檔元資料欄位的定義 (預覽) ，請參閱 [檔元資料欄位](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="ca4ff-155">For a definition of all document metadata fields in Data Investigations (preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
