---
title: 將非 Office 365 的資料載入檢閱集
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
description: 將非 Office 365 資料匯入至高級 eDiscovery 案例中的複查集。
ms.openlocfilehash: 816519fcaa8dc5172dbb5c369a3ec191585d3647
ms.sourcegitcommit: 825037f166eea3ba70f8980cedc5492f90c1cc56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2020
ms.locfileid: "43097226"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="81e6b-103">將非 Office 365 的資料載入檢閱集</span><span class="sxs-lookup"><span data-stu-id="81e6b-103">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="81e6b-104">並非所有需要在高級 eDiscovery 中進行分析的檔都位於 Office 365。</span><span class="sxs-lookup"><span data-stu-id="81e6b-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Office 365.</span></span> <span data-ttu-id="81e6b-105">使用 Advanced eDiscovery 的非 Office 365 資料匯入功能，您可以將不位於 Office 365 的檔上傳至審閱集。</span><span class="sxs-lookup"><span data-stu-id="81e6b-105">With the non-Office 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Office 365 to a review set.</span></span> <span data-ttu-id="81e6b-106">本文說明如何將您的非 Office 365 檔移至高級 eDiscovery 以進行分析。</span><span class="sxs-lookup"><span data-stu-id="81e6b-106">This article shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="81e6b-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="81e6b-107">Before you begin</span></span>

<span data-ttu-id="81e6b-108">使用本文所述的上傳非 Office 365 功能，您需要具備下列各項：</span><span class="sxs-lookup"><span data-stu-id="81e6b-108">Using the upload non-Office 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="81e6b-109">您要將非 Office 365 內容關聯的所有保管人都必須獲指派適當的授權。</span><span class="sxs-lookup"><span data-stu-id="81e6b-109">All custodians that you want to associate non-Office 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="81e6b-110">如需詳細資訊，請參閱[Advanced EDiscovery 快速入門](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)。</span><span class="sxs-lookup"><span data-stu-id="81e6b-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="81e6b-111">現有的高級電子檔探索案例。</span><span class="sxs-lookup"><span data-stu-id="81e6b-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="81e6b-112">您必須先將保管人新增至案例，才能將非 Office 365 資料上傳及關聯。</span><span class="sxs-lookup"><span data-stu-id="81e6b-112">Custodians must be added to the case before you can upload and associate the non-Office 365 data to them.</span></span>

- <span data-ttu-id="81e6b-113">非 Office 365 資料必須是由「高級 eDiscovery」所支援的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="81e6b-113">Non-Office 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="81e6b-114">如需詳細資訊，請參閱[Advanced eDiscovery 中的支援檔案類型](supported-filetypes-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="81e6b-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="81e6b-115">所有上傳至審閱集的檔案，都必須位於資料夾中，其中每個資料夾都會與特定保管人產生關聯。</span><span class="sxs-lookup"><span data-stu-id="81e6b-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="81e6b-116">這些資料夾的名稱必須使用下列命名格式： *alias@domainname*。</span><span class="sxs-lookup"><span data-stu-id="81e6b-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="81e6b-117">Alias@domainname 必須是使用者的 Office 365 別名和網域。</span><span class="sxs-lookup"><span data-stu-id="81e6b-117">The alias@domainname must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="81e6b-118">您可以收集根資料夾中的所有 alias@domainname 資料夾。</span><span class="sxs-lookup"><span data-stu-id="81e6b-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="81e6b-119">根資料夾只能包含 alias@domainname 資料夾。</span><span class="sxs-lookup"><span data-stu-id="81e6b-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="81e6b-120">不支援根資料夾中的鬆散檔案。</span><span class="sxs-lookup"><span data-stu-id="81e6b-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="81e6b-121">您想要上傳的非 Office 365 資料的資料夾結構，會類似下列範例：</span><span class="sxs-lookup"><span data-stu-id="81e6b-121">The folder structure for the non-Office 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="81e6b-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="81e6b-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="81e6b-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="81e6b-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="81e6b-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="81e6b-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="81e6b-125">在此案例中，abraham.mcmahon@contoso.com、jewell.gordon@contoso.com 和 staci.gonzalez@contoso.com 是保管人的 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="81e6b-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![非 Office 365 資料上傳資料夾結構](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="81e6b-127">指派給 eDiscovery 管理員角色群組的帳戶（並新增為 eDiscovery 管理員）。</span><span class="sxs-lookup"><span data-stu-id="81e6b-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="81e6b-128">電腦上所安裝的 AzCopy v 8.1 工具，具有非 Office 365 內容資料夾結構的存取權。</span><span class="sxs-lookup"><span data-stu-id="81e6b-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Office 365 content folder structure.</span></span> <span data-ttu-id="81e6b-129">若要安裝 AzCopy，請參閱[在 Windows 上使用 AzCopy app-v 8.1 傳輸資料](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="81e6b-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="81e6b-130">請務必將 AzCopy 安裝在預設位置，也就是 **% ProgramFiles （x86）% \ Microsoft SDKs\Azure\AzCopy**。</span><span class="sxs-lookup"><span data-stu-id="81e6b-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="81e6b-131">您必須使用 AzCopy app-v 8.1。</span><span class="sxs-lookup"><span data-stu-id="81e6b-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="81e6b-132">其他版本的 AzCopy 在 [Advanced eDiscovery] 中載入非 Office 365 資料時可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="81e6b-132">Other versions of AzCopy may not work when loading non-Office 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="81e6b-133">將非 Office 365 內容上傳至高級電子檔探索</span><span class="sxs-lookup"><span data-stu-id="81e6b-133">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="81e6b-134">以 eDiscovery 管理員或 eDiscovery 管理員的身分開啟「高級 eDiscovery」，然後移至即將上傳非辦公室365資料的情況。</span><span class="sxs-lookup"><span data-stu-id="81e6b-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Office 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="81e6b-135">按一下 [**複查集**]，然後選取要上傳非 Office 365 資料的複查集。</span><span class="sxs-lookup"><span data-stu-id="81e6b-135">Click **Review sets**, and then select the review set to upload the non-Office 365 data to.</span></span>  <span data-ttu-id="81e6b-136">如果您沒有審校集，您可以建立一個。</span><span class="sxs-lookup"><span data-stu-id="81e6b-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="81e6b-137">在 [檢查] 集中，按一下 [**管理審閱集**]，然後按一下 [在**非 Office 365 資料**格上**查看上傳**]。</span><span class="sxs-lookup"><span data-stu-id="81e6b-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Office 365 data** tile.</span></span>

4. <span data-ttu-id="81e6b-138">按一下 **[上傳**檔案] 以啟動 [非 Office 365 資料匯入] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="81e6b-138">Click **Upload files** to start the Non-Office 365 data import wizard.</span></span>

   ![上傳檔案](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="81e6b-140">嚮導的第一個步驟是準備將檔案上傳至的安全 Microsoft 提供 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="81e6b-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="81e6b-141">準備完成後，[**下一步：上傳檔案]** 按鈕會變成作用中狀態。</span><span class="sxs-lookup"><span data-stu-id="81e6b-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![非 Office 365 匯入：準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="81e6b-143">按 **[下一步：上傳**檔案]。</span><span class="sxs-lookup"><span data-stu-id="81e6b-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="81e6b-144">在 [**上傳**檔案] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="81e6b-144">On the **Upload files** page, do the following:</span></span>

   ![非 Office 365 匯入：上傳檔案](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="81e6b-146">a.</span><span class="sxs-lookup"><span data-stu-id="81e6b-146">a.</span></span> <span data-ttu-id="81e6b-147">在 [檔案**位置**] 方塊中，確認或輸入您要上傳的非 Office 365 資料所在之根資料夾的位置。</span><span class="sxs-lookup"><span data-stu-id="81e6b-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Office 365 data you want to upload.</span></span> <span data-ttu-id="81e6b-148">例如，在 [**開始之前] 區段**中所顯示範例檔案的位置之後，您可以輸入 **%USERPROFILE\Downloads\nonO365**。</span><span class="sxs-lookup"><span data-stu-id="81e6b-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="81e6b-149">提供正確的位置，可確保路徑上顯示的 AzCopy 命令已正確更新。</span><span class="sxs-lookup"><span data-stu-id="81e6b-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="81e6b-150">b.</span><span class="sxs-lookup"><span data-stu-id="81e6b-150">b.</span></span> <span data-ttu-id="81e6b-151">按一下 [**複製到剪貼簿**]，複製方塊中所顯示的命令。</span><span class="sxs-lookup"><span data-stu-id="81e6b-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="81e6b-152">啟動 Windows 命令提示字元，貼上一個步驟中所複製的命令，然後按**enter**開始 AzCopy 命令。</span><span class="sxs-lookup"><span data-stu-id="81e6b-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="81e6b-153">啟動命令之後，非 Office 365 檔案會上傳至在步驟4中準備的 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="81e6b-153">After you start the command, the non-Office 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![非 Office 365 匯入： AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="81e6b-155">如先前所述，您必須使用 AzCopy app-v 8.1，以順利使用「**上載**檔案」頁面上提供的命令。</span><span class="sxs-lookup"><span data-stu-id="81e6b-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="81e6b-156">如果提供的 AzCopy 命令失敗，請參閱[Advanced eDiscovery 中的疑難排解 AzCopy](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="81e6b-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="81e6b-157">回到安全性 & 合規性中心，然後按一下 **[下一步：處理**檔案]。</span><span class="sxs-lookup"><span data-stu-id="81e6b-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="81e6b-158">這會啟動上傳至 Azure 存放位置的非 Office 365 檔案的處理、文字提取及編制索引。</span><span class="sxs-lookup"><span data-stu-id="81e6b-158">This initiates processing, text extraction, and indexing of the non-Office 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="81e6b-159">在 [**處理**檔案] 頁面或 [**工作**] 索引標籤上，透過查看名為 [**新增非 office 365 資料至審閱集**的工作]，追蹤處理非 office 365 檔案的進度。</span><span class="sxs-lookup"><span data-stu-id="81e6b-159">Track the progress of processing the non-Office 365 files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Office 365 data to a review set**.</span></span>  <span data-ttu-id="81e6b-160">工作完成後，會在 [檢查] 集中使用新的檔案。</span><span class="sxs-lookup"><span data-stu-id="81e6b-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![非 Office 365 匯入：處理檔](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="81e6b-162">完成處理之後，您可以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="81e6b-162">After the processing is finished, you can close the wizard.</span></span>
