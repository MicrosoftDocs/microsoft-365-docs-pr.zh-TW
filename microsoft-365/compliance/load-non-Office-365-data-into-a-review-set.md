---
title: 將非 Office 365 的資料載入檢閱集
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
description: 将非 Office 365 数据导入高级电子数据展示案例中的审核集。
ms.openlocfilehash: 508346c3fe3a8f67addfed4ced08693daa2d49e7
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077232"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="6c576-103">將非 Office 365 的資料載入檢閱集</span><span class="sxs-lookup"><span data-stu-id="6c576-103">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="6c576-104">并非所有需要在高级电子数据展示中分析的文档都位于 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="6c576-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Office 365.</span></span> <span data-ttu-id="6c576-105">使用高级电子数据展示中的非 Office 365 数据导入功能，您可以将不在 Office 365 中的文档上载到审阅集。</span><span class="sxs-lookup"><span data-stu-id="6c576-105">With the non-Office 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Office 365 to a review set.</span></span> <span data-ttu-id="6c576-106">本文介绍如何将非 Office 365 文档引入高级电子数据展示以进行分析。</span><span class="sxs-lookup"><span data-stu-id="6c576-106">This article shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="6c576-107">高级电子数据展示需要适用于您的组织的 Microsoft 365 或 Office 365 E5 订阅，或具有高级合规性加载项订阅的 E3 订阅。</span><span class="sxs-lookup"><span data-stu-id="6c576-107">Advanced eDiscovery requires an Microsoft 365 or Office 365 E5 subscription for your organization or an E3 subscription with the Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="6c576-108">如果您没有该计划，并且想要尝试高级电子数据展示，则可以注册 Office 365 企业版 E5 试用版。</span><span class="sxs-lookup"><span data-stu-id="6c576-108">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6c576-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="6c576-109">Before you begin</span></span>

<span data-ttu-id="6c576-110">使用本文中描述的上载非 Office 365 功能需要具备以下功能：</span><span class="sxs-lookup"><span data-stu-id="6c576-110">Using the upload non-Office 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="6c576-111">要将非 Office 365 内容关联到的所有保管人都必须分配 E5 许可证或具有高级合规性附加许可证的 E3 许可证。</span><span class="sxs-lookup"><span data-stu-id="6c576-111">All custodians that you want to associate non-Office 365 content to must be assigned an E5 license, or an E3 license with an Advanced Compliance add-on license.</span></span>

- <span data-ttu-id="6c576-112">现有的高级电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="6c576-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="6c576-113">必须先将保管人添加到案例中，然后才能将非 Office 365 数据上载并关联到他们。</span><span class="sxs-lookup"><span data-stu-id="6c576-113">Custodians must be added to the case before you can upload and associate the non-Office 365 data to them.</span></span>

- <span data-ttu-id="6c576-114">非 Office 365 数据必须是高级电子数据展示支持的文件类型。</span><span class="sxs-lookup"><span data-stu-id="6c576-114">Non-Office 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="6c576-115">有关详细信息，请参阅[高级电子数据展示 中支持的文件类型。](supported-filetypes-ediscovery20.md)</span><span class="sxs-lookup"><span data-stu-id="6c576-115">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="6c576-116">上载到审阅集的所有文件都必须位于文件夹中，其中每个文件夹都与特定的保管人相关联。</span><span class="sxs-lookup"><span data-stu-id="6c576-116">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="6c576-117">这些文件夹的名称必须使用以下命名格式：*别名\域名。*</span><span class="sxs-lookup"><span data-stu-id="6c576-117">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="6c576-118">别名\域名必须是用户的 Office 365 别名和域。</span><span class="sxs-lookup"><span data-stu-id="6c576-118">The alias@domainname must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="6c576-119">您可以收集根文件夹中的所有别名\域名文件夹。</span><span class="sxs-lookup"><span data-stu-id="6c576-119">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="6c576-120">根文件夹只能包含别名\域名文件夹。</span><span class="sxs-lookup"><span data-stu-id="6c576-120">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="6c576-121">不支持根文件夹中的松散文件。</span><span class="sxs-lookup"><span data-stu-id="6c576-121">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="6c576-122">要上载的非 Office 365 数据的文件夹结构类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="6c576-122">The folder structure for the non-Office 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="6c576-123">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c576-123">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="6c576-124">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c576-124">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="6c576-125">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c576-125">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="6c576-126">abraham.mcmahon@contoso.com、jewell.gordon@contoso.com和staci.gonzalez@contoso.com是案例中保管人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="6c576-126">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![非 Office 365 数据上传文件夹结构](media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="6c576-128">分配给电子数据展示管理器角色组（并添加为电子数据展示管理员）的帐户。</span><span class="sxs-lookup"><span data-stu-id="6c576-128">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="6c576-129">AzCopy v8.1 工具安装在有权访问非 Office 365 内容文件夹结构的计算机上。</span><span class="sxs-lookup"><span data-stu-id="6c576-129">The AzCopy v8.1 tool installed on a computer that has access to the non-Office 365 content folder structure.</span></span> <span data-ttu-id="6c576-130">要安装 AzCopy，请参阅[在 Windows 上使用 AzCopy v8.1 传输数据。](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="6c576-130">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="6c576-131">请确保在默认位置安装 AzCopy，即 **%程序文件 （x86）%_微软 SDK_Azure_AzCopy**。</span><span class="sxs-lookup"><span data-stu-id="6c576-131">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="6c576-132">您必须使用 AzCopy v8.1。</span><span class="sxs-lookup"><span data-stu-id="6c576-132">You must use AzCopy v8.1.</span></span> <span data-ttu-id="6c576-133">在高级电子数据展示中加载非 Office 365 数据时，其他版本的 AzCopy 可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="6c576-133">Other versions of AzCopy may not work when loading non-Office 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="6c576-134">将非 Office 365 内容上载到高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="6c576-134">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="6c576-135">作为电子数据展示管理器或电子数据展示管理员，打开高级电子数据展示，然后将非 Office 365 数据上载到的情况下。</span><span class="sxs-lookup"><span data-stu-id="6c576-135">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="6c576-136">**单击"审阅集"，** 然后选择审阅集以将非 Office 365 数据上载到 。</span><span class="sxs-lookup"><span data-stu-id="6c576-136">Click **Review sets**, and then select the review set to upload the non-Office 365 data to.</span></span>  <span data-ttu-id="6c576-137">如果您没有审阅集，则可以创建一个审核集。</span><span class="sxs-lookup"><span data-stu-id="6c576-137">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="6c576-138">在审阅集中，**单击"管理审阅集"，** 然后单击"查看非 Office **365 数据**磁贴上的**上载"。**</span><span class="sxs-lookup"><span data-stu-id="6c576-138">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Office 365 data** tile.</span></span>

4. <span data-ttu-id="6c576-139">**单击"上载文件"** 以启动非 Office 365 数据导入向导。</span><span class="sxs-lookup"><span data-stu-id="6c576-139">Click **Upload files** to start the Non-Office 365 data import wizard.</span></span>

   ![上传文件](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="6c576-141">向导中的第一步准备 Microsoft 提供的安全 Azure 存储位置，以便将文件上载到 。</span><span class="sxs-lookup"><span data-stu-id="6c576-141">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="6c576-142">准备完成后，"**下一步：上传文件"** 按钮将变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="6c576-142">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![非 Office 365 导入：准备](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="6c576-144">**单击"下一步：上传文件"。**</span><span class="sxs-lookup"><span data-stu-id="6c576-144">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="6c576-145">在"**上传文件"** 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6c576-145">On the **Upload files** page, do the following:</span></span>

   ![非 Office 365 导入：上载文件](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="6c576-147">a.</span><span class="sxs-lookup"><span data-stu-id="6c576-147">a.</span></span> <span data-ttu-id="6c576-148">在"**文件位置的路径"** 框中，验证或键入要上载的非 Office 365 数据的根文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="6c576-148">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Office 365 data you want to upload.</span></span> <span data-ttu-id="6c576-149">例如，对于"**开始之前"部分**中显示的示例文件的位置，将键入 **%USERPROFILE_下载_nonO365**。</span><span class="sxs-lookup"><span data-stu-id="6c576-149">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="6c576-150">提供正确的位置可确保正确更新路径下方框中显示的 AzCopy 命令。</span><span class="sxs-lookup"><span data-stu-id="6c576-150">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="6c576-151">b.</span><span class="sxs-lookup"><span data-stu-id="6c576-151">b.</span></span> <span data-ttu-id="6c576-152">**单击"复制到剪贴板"** 以复制框中显示的命令。</span><span class="sxs-lookup"><span data-stu-id="6c576-152">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="6c576-153">启动 Windows 命令提示，粘贴您在上一步中复制的命令，然后按**Enter**以启动 AzCopy 命令。</span><span class="sxs-lookup"><span data-stu-id="6c576-153">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="6c576-154">启动该命令后，非 Office 365 文件将上载到步骤 4 中准备的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="6c576-154">After you start the command, the non-Office 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![非 Office 365 导入：AzCopy](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="6c576-156">如前所述，您必须使用 AzCopy v8.1 才能成功**使用"上载文件"** 页上提供的命令。</span><span class="sxs-lookup"><span data-stu-id="6c576-156">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="6c576-157">如果提供的 AzCopy 命令失败，请参阅[高级电子数据展示中的疑难解答 AzCopy](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="6c576-157">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="6c576-158">返回安全&合规性中心，然后单击向导**中的"下一步：处理文件"。**</span><span class="sxs-lookup"><span data-stu-id="6c576-158">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="6c576-159">这将启动上载到 Azure 存储位置的非 Office 365 文件的处理、文本提取和索引。</span><span class="sxs-lookup"><span data-stu-id="6c576-159">This initiates processing, text extraction, and indexing of the non-Office 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="6c576-160">通过查看**名为"将非 Office 365 数据添加到审阅集"** 的作业，跟踪**处理"进程文件"** 页**或"作业"** 选项卡上的非 Office 365 文件的进度。</span><span class="sxs-lookup"><span data-stu-id="6c576-160">Track the progress of processing the non-Office 365 files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Office 365 data to a review set**.</span></span>  <span data-ttu-id="6c576-161">作业完成后，新文件将在审阅集中可用。</span><span class="sxs-lookup"><span data-stu-id="6c576-161">After the job is finished, the new files will be available in the review set.</span></span>

   ![非 Office 365 导入：处理文件](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="6c576-163">处理完成后，可以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="6c576-163">After the processing is finished, you can close the wizard.</span></span>