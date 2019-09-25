---
title: 處理資料時的錯誤補救
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
ms.openlocfilehash: 02fa8870d6edb4e1a6616604ee0e98638b217237
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077164"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="ca246-102">處理資料時的錯誤補救</span><span class="sxs-lookup"><span data-stu-id="ca246-102">Error remediation when processing data</span></span>

<span data-ttu-id="ca246-103">错误修正使电子数据展示管理员能够纠正阻止高级电子数据展示正确处理内容的数据问题。</span><span class="sxs-lookup"><span data-stu-id="ca246-103">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="ca246-104">例如，由于文件已被锁定或加密，因此无法处理受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="ca246-104">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="ca246-105">使用错误修正，电子数据展示管理员可以下载有此类错误的文件，删除密码保护，然后上载修复的文件。</span><span class="sxs-lookup"><span data-stu-id="ca246-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="ca246-106">使用以下工作流修复在高级电子数据展示案例中出现错误的文件。</span><span class="sxs-lookup"><span data-stu-id="ca246-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="ca246-107">创建错误修正会话以修复具有处理错误的文件</span><span class="sxs-lookup"><span data-stu-id="ca246-107">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="ca246-108">如果错误修正向导在以下过程中随时关闭，则可以通过**选择"查看"** 下拉菜单中"**修复"** 从"**处理"** 选项卡返回到错误修正会话。</span><span class="sxs-lookup"><span data-stu-id="ca246-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="ca246-109">在"高级电子数据展示"案例**中的"处理"** 选项卡上，**在"查看"** 下拉菜单**中选择"错误"，\*\*\*\*然后在"范围"** 下拉菜单中选择审阅集或整个案例。</span><span class="sxs-lookup"><span data-stu-id="ca246-109">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="ca246-110">本部分显示来自案例的所有错误或特定审核集的错误。</span><span class="sxs-lookup"><span data-stu-id="ca246-110">This section displays all errors from the case or error from a specific review set.</span></span>

   ![错误修正](media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="ca246-112">通过单击错误类型或文件类型旁边的单选按钮，选择要修复的错误。</span><span class="sxs-lookup"><span data-stu-id="ca246-112">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="ca246-113">在下面的示例中，我们正在修复受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="ca246-113">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="ca246-114">**单击"新建错误修正"。**</span><span class="sxs-lookup"><span data-stu-id="ca246-114">Click **New error remediation**.</span></span>

    <span data-ttu-id="ca246-115">错误修正工作流从准备阶段开始，其中错误的文件将复制到 Microsoft 提供的 Azure 存储位置，以便您可以将它们下载到本地计算机进行修复。</span><span class="sxs-lookup"><span data-stu-id="ca246-115">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![准备错误补救](media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="ca246-117">准备完成后，**单击"下一步：下载文件"** 以继续下载。</span><span class="sxs-lookup"><span data-stu-id="ca246-117">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![下载文件](media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="ca246-119">要下载文件，请指定**要下载的目标路径。**</span><span class="sxs-lookup"><span data-stu-id="ca246-119">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="ca246-120">这是本地计算机上的父文件夹的路径，将在那里下载该文件。</span><span class="sxs-lookup"><span data-stu-id="ca246-120">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="ca246-121">默认路径%USERPROFILE%_下载_错误指向登录用户的下载文件夹。</span><span class="sxs-lookup"><span data-stu-id="ca246-121">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="ca246-122">如果需要，可以更改此路径。</span><span class="sxs-lookup"><span data-stu-id="ca246-122">You can change this path if desired.</span></span> <span data-ttu-id="ca246-123">如果确实更改了它，我们建议您使用本地文件路径来获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="ca246-123">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="ca246-124">不要使用远程网络路径。</span><span class="sxs-lookup"><span data-stu-id="ca246-124">Don't use a remote network path.</span></span> <span data-ttu-id="ca246-125">例如，可以使用路径**C：\修复**。</span><span class="sxs-lookup"><span data-stu-id="ca246-125">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="ca246-126">父文件夹的路径将自动添加到 AzCopy 命令（作为 **/Dest**参数的值）。</span><span class="sxs-lookup"><span data-stu-id="ca246-126">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="ca246-127">通过单击"**复制到剪贴板"** 复制预定义的命令。</span><span class="sxs-lookup"><span data-stu-id="ca246-127">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="ca246-128">打开 Windows 命令提示符，粘贴 AzCopy 命令，然后**按"输入"。**</span><span class="sxs-lookup"><span data-stu-id="ca246-128">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![准备错误补救](media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="ca246-130">您必须使用 AzCopy v8.1 才能成功**使用"下载文件"** 页上提供的命令。</span><span class="sxs-lookup"><span data-stu-id="ca246-130">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="ca246-131">您还必须使用 AzCopy v8.1 来上载步骤 10 中的文件。</span><span class="sxs-lookup"><span data-stu-id="ca246-131">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="ca246-132">要安装此版本的 AzCopy，请参阅[在 Windows 上使用 AzCopy v8.1 传输数据。](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="ca246-132">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="ca246-133">如果提供的 AzCopy 命令失败，请参阅[高级电子数据展示中的疑难解答 AzCopy](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="ca246-133">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="ca246-134">您选择的文件将下载到您在步骤 5 中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="ca246-134">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="ca246-135">在父文件夹中（**例如，C：\修复），** 将自动创建以下子文件夹结构：</span><span class="sxs-lookup"><span data-stu-id="ca246-135">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="ca246-136">*子文件夹 1*使用案例 ID 或审阅集命名，具体取决于您在步骤 1 中选择的范围。</span><span class="sxs-lookup"><span data-stu-id="ca246-136">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="ca246-137">*子文件夹 2*使用下载文件的文件 ID 命名</span><span class="sxs-lookup"><span data-stu-id="ca246-137">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="ca246-138">下载的文件位于*子文件夹 2*中，并且也使用文件 ID 命名。</span><span class="sxs-lookup"><span data-stu-id="ca246-138">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="ca246-139">下面是在将项目下载到**C：\修复**父文件夹时创建的文件夹路径和错误文件名的示例：</span><span class="sxs-lookup"><span data-stu-id="ca246-139">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="ca246-140">如果下载了多个文件，则每个文件都将下载到使用文件 ID 命名的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="ca246-140">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ca246-141">在步骤 9 和步骤 10 中上载文件时，修复的文件必须具有相同的文件名，并且位于相同的子文件夹结构中。</span><span class="sxs-lookup"><span data-stu-id="ca246-141">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="ca246-142">子文件夹和文件名用于将修复的文件与原始错误文件相关联。</span><span class="sxs-lookup"><span data-stu-id="ca246-142">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="ca246-143">如果文件夹结构或文件名发生更改，您将收到以下错误： `Cannot apply Error Remediation to the current Workingset`。</span><span class="sxs-lookup"><span data-stu-id="ca246-143">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="ca246-144">为了防止任何问题，我们建议将修复的文件保留在同一父文件夹和子文件夹结构中。</span><span class="sxs-lookup"><span data-stu-id="ca246-144">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="ca246-145">下载文件后，您可以使用适当的工具进行修复。</span><span class="sxs-lookup"><span data-stu-id="ca246-145">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="ca246-146">对于受密码保护的文件，可以使用多种密码破解工具。</span><span class="sxs-lookup"><span data-stu-id="ca246-146">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="ca246-147">如果您知道这些文件的密码，则可以打开这些文件并删除密码保护。</span><span class="sxs-lookup"><span data-stu-id="ca246-147">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="ca246-148">返回到高级电子数据展示和错误修正向导，**然后单击"下一步：上传文件"。**</span><span class="sxs-lookup"><span data-stu-id="ca246-148">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="ca246-149">这将移动到下一页，您现在可以在其中上载文件。</span><span class="sxs-lookup"><span data-stu-id="ca246-149">This moves to the next page where you can now upload the files.</span></span>

    ![上传文件](media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="ca246-151">指定修复的文件所在的父文件夹，该文件夹**位于"文件位置路径"** 文本框中。</span><span class="sxs-lookup"><span data-stu-id="ca246-151">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="ca246-152">同样，父文件夹必须具有下载文件时创建的子文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="ca246-152">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="ca246-153">父文件夹的路径将自动添加到 AzCopy 命令（作为 **/Source**参数的值）。</span><span class="sxs-lookup"><span data-stu-id="ca246-153">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="ca246-154">通过单击"**复制到剪贴板"** 复制预定义的命令。</span><span class="sxs-lookup"><span data-stu-id="ca246-154">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="ca246-155">打开 Windows 命令提示符，粘贴 AzCopy 命令，然后**按"输入"。**</span><span class="sxs-lookup"><span data-stu-id="ca246-155">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="ca246-156">上传文件。</span><span class="sxs-lookup"><span data-stu-id="ca246-156">upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="ca246-158">运行 AzCopy 命令后，**单击"下一步：处理文件"。**</span><span class="sxs-lookup"><span data-stu-id="ca246-158">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="ca246-159">处理完成后，可以转到查看集并查看修复的文件。</span><span class="sxs-lookup"><span data-stu-id="ca246-159">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="ca246-160">修复文件时会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="ca246-160">What happens when files are remediated</span></span>

<span data-ttu-id="ca246-161">上载修复的文件时，原始元数据将保留，但以下字段除外：</span><span class="sxs-lookup"><span data-stu-id="ca246-161">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="ca246-162">提取的文本大小</span><span class="sxs-lookup"><span data-stu-id="ca246-162">ExtractedTextSize</span></span>
- <span data-ttu-id="ca246-163">HasText</span><span class="sxs-lookup"><span data-stu-id="ca246-163">HasText</span></span>
- <span data-ttu-id="ca246-164">误位修正</span><span class="sxs-lookup"><span data-stu-id="ca246-164">IsErrorRemediate</span></span>
- <span data-ttu-id="ca246-165">加载 Id</span><span class="sxs-lookup"><span data-stu-id="ca246-165">LoadId</span></span>
- <span data-ttu-id="ca246-166">处理错误消息</span><span class="sxs-lookup"><span data-stu-id="ca246-166">ProcessingErrorMessage</span></span>
- <span data-ttu-id="ca246-167">处理状态</span><span class="sxs-lookup"><span data-stu-id="ca246-167">ProcessingStatus</span></span>
- <span data-ttu-id="ca246-168">Text</span><span class="sxs-lookup"><span data-stu-id="ca246-168">Text</span></span>
- <span data-ttu-id="ca246-169">字数</span><span class="sxs-lookup"><span data-stu-id="ca246-169">WordCount</span></span>
- <span data-ttu-id="ca246-170">工作集Id</span><span class="sxs-lookup"><span data-stu-id="ca246-170">WorkingsetId</span></span>

<span data-ttu-id="ca246-171">有关高级电子数据展示中所有元数据字段的定义，请参阅[文档元数据字段](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="ca246-171">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
