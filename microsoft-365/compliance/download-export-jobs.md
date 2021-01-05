---
title: 下載高級 eDiscovery 案例的匯出工作
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: 安裝和使用 Azure Storage Explorer，以從 Advanced eDiscovery 的審閱集中下載已匯出的檔。
ms.openlocfilehash: 094dcb4ecc8b1ca73a7ec0238ed20b27d4c16e72
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751290"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a><span data-ttu-id="7bab1-103">在高級 eDiscovery 案例中下載匯出工作</span><span class="sxs-lookup"><span data-stu-id="7bab1-103">Download export jobs in an Advanced eDiscovery case</span></span>

<span data-ttu-id="7bab1-104">當您在高級 eDiscovery 案例中從審閱集匯出檔時，會將檔上傳至 Microsoft 提供的 Azure 存放區位置，或組織所管理的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="7bab1-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="7bab1-105">使用的 Azure 儲存位置類型取決於匯出檔時選取的選項。</span><span class="sxs-lookup"><span data-stu-id="7bab1-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span>

<span data-ttu-id="7bab1-106">本文提供如何使用 Microsoft Azure Storage Explorer 連線到 Azure 存放位置，以流覽及下載匯出的檔的指示。</span><span class="sxs-lookup"><span data-stu-id="7bab1-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="7bab1-107">如需 Azure Storage Explorer 的詳細資訊，請參閱 [快速入門：使用 Azure Storage explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。</span><span class="sxs-lookup"><span data-stu-id="7bab1-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="7bab1-108">步驟1：安裝 Azure Storage Explorer</span><span class="sxs-lookup"><span data-stu-id="7bab1-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="7bab1-109">第一個步驟是下載及安裝 Azure Storage Explorer。</span><span class="sxs-lookup"><span data-stu-id="7bab1-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="7bab1-110">如需相關指示，請參閱 [Azure Storage Explorer 工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="7bab1-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="7bab1-111">您可以使用此工具，在步驟3中連線並下載匯出的檔。</span><span class="sxs-lookup"><span data-stu-id="7bab1-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="7bab1-112">步驟2：從匯出工作取得 SAS URL</span><span class="sxs-lookup"><span data-stu-id="7bab1-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="7bab1-113">下一步是取得當您建立匯出工作以 [從審閱集匯出檔](export-documents-from-review-set.md)時所產生的共用存取簽名 (SAS) URL。</span><span class="sxs-lookup"><span data-stu-id="7bab1-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="7bab1-114">您可以複製上傳至 Microsoft 提供之 Azure 存放區位置或您組織所管理之 Azure 存放位置之檔的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="7bab1-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="7bab1-115">在這兩種情況下，您可以使用 SAS URL 連線至步驟3中的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="7bab1-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="7bab1-116">在 [ **高級電子** 檔探索] 頁面上，移至案例，然後按一下 [ **匯出** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7bab1-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="7bab1-117">在 [ **匯出** ] 索引標籤上，按一下您要下載的匯出工作。</span><span class="sxs-lookup"><span data-stu-id="7bab1-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="7bab1-118">在飛入頁面的 [ **位置**] 下，複製所顯示的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="7bab1-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="7bab1-119">如有必要，您可以將它儲存至檔案，讓您可以在步驟3中存取。</span><span class="sxs-lookup"><span data-stu-id="7bab1-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![複製顯示在 [位置] 底下的 SAS URL](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="7bab1-121">步驟3：連線至 Azure 存放區位置</span><span class="sxs-lookup"><span data-stu-id="7bab1-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="7bab1-122">最後一個步驟是使用 Azure Storage Explorer 和 SAS URL 連線至 Azure 存放位置，並下載匯出至本機電腦的檔。</span><span class="sxs-lookup"><span data-stu-id="7bab1-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1. <span data-ttu-id="7bab1-123">開啟您在步驟1中安裝的 Azure 存放區 Explorer。</span><span class="sxs-lookup"><span data-stu-id="7bab1-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="7bab1-124">按一下 [ **新增帳戶** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="7bab1-124">Click the **Add account** icon.</span></span> <span data-ttu-id="7bab1-125">或者，您也可以用滑鼠右鍵按一下 [ **儲存帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="7bab1-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![按一下 [新增帳戶] 圖示](../media/AzureStorageConnect.png)

3. <span data-ttu-id="7bab1-127">在 [ **Connect To Azure Storage]** 頁面上，按一下 [ **使用共用存取簽名 (SAS) URI** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7bab1-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![按一下 [使用共用存取簽名 (SAS) URI]，然後按 [下一步]。](../media/AzureStorageConnect2.png)

4. <span data-ttu-id="7bab1-129">在 [ **附加于 SAS URI** ] 頁面上，按一下 [URI] 方塊，然後貼上您在步驟2中取得的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="7bab1-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![在 [URI] 方塊中貼上 SAS URL](../media/AzureStorageConnect3.png)

    <span data-ttu-id="7bab1-131">請注意，SAS URL 的一部分會顯示在 [ **顯示名稱** ] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="7bab1-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="7bab1-132">在您連接至儲存位置後，會將此名稱當做 **儲存帳戶** 下所建立之容器的顯示名稱使用。</span><span class="sxs-lookup"><span data-stu-id="7bab1-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="7bab1-133">這個名稱是由高級 eDiscovery 案例的識別碼所組成，也就是唯一的識別碼。</span><span class="sxs-lookup"><span data-stu-id="7bab1-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="7bab1-134">您可以保留預設顯示名稱或加以變更。</span><span class="sxs-lookup"><span data-stu-id="7bab1-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="7bab1-135">如果您進行變更，顯示名稱必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7bab1-135">If you change it, the display name must be unique.</span></span>

5. <span data-ttu-id="7bab1-136">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7bab1-136">Click **Next**.</span></span>

    <span data-ttu-id="7bab1-137">隨即會顯示 [連線 **摘要** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7bab1-137">The **Connection summary** page is displayed.</span></span>

    ![按一下 [連線摘要] 頁面上的 [連線]，以連線至 Azure 存放位置。](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="7bab1-139">在 [連線 **摘要** ] 頁面上，複查連線資訊，然後按一下 **[連接]**。</span><span class="sxs-lookup"><span data-stu-id="7bab1-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span>

    <span data-ttu-id="7bab1-140">會開啟 [**儲存帳戶**] (所連接的) 容器] 下 (的 [ **Blob 容器**] 節點  >   \> 。</span><span class="sxs-lookup"><span data-stu-id="7bab1-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![在 Blob 容器節點中匯出工作](../media/AzureStorageConnect5.png)

    <span data-ttu-id="7bab1-142">包含以步驟4顯示名稱命名的容器。</span><span class="sxs-lookup"><span data-stu-id="7bab1-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="7bab1-143">此容器包含您已建立之每個匯出工作的資料夾。</span><span class="sxs-lookup"><span data-stu-id="7bab1-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="7bab1-144">這些資料夾是以對應至匯出工作識別碼的識別碼命名。</span><span class="sxs-lookup"><span data-stu-id="7bab1-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="7bab1-145">在 [**工作**] 索引標籤上，您可以在 [支援] 清單中的 [**支援資訊**] 頁面上，找到這些匯出 IDs (和 [支援]**的匯出)** 名稱。</span><span class="sxs-lookup"><span data-stu-id="7bab1-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="7bab1-146">按兩下 [匯出] 工作資料夾以將其開啟。</span><span class="sxs-lookup"><span data-stu-id="7bab1-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="7bab1-147">隨即會顯示資料夾清單及匯出報告。</span><span class="sxs-lookup"><span data-stu-id="7bab1-147">A list of folders and export reports is displayed.</span></span>
   
    ![匯出資料夾包含匯出的檔案和匯出報告](../media/AzureStorageConnect6.png)

   <span data-ttu-id="7bab1-149">「匯出工作」資料夾包含下列專案。</span><span class="sxs-lookup"><span data-stu-id="7bab1-149">The export job folder contains the following items.</span></span> <span data-ttu-id="7bab1-150">匯出資料夾中的實際專案是由建立匯出工作時設定的匯出選項所決定。</span><span class="sxs-lookup"><span data-stu-id="7bab1-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="7bab1-151">如需詳細資訊，請參閱 [從審閱集匯出檔](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="7bab1-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="7bab1-152">Export_load_file.csv：此 CSV 檔是包含每個匯出檔相關資訊的詳細資料匯出報告。</span><span class="sxs-lookup"><span data-stu-id="7bab1-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="7bab1-153">檔案由每個檔的中繼資料屬性的欄所組成。</span><span class="sxs-lookup"><span data-stu-id="7bab1-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="7bab1-154">如需此報告中包含之中繼資料的清單和描述，請參閱 [Advanced eDiscovery 中檔元資料欄位](document-metadata-fields-in-advanced-ediscovery.md)之表格中的 **匯出** 的功能變數名稱欄。</span><span class="sxs-lookup"><span data-stu-id="7bab1-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
    
    - <span data-ttu-id="7bab1-155">Summary.txt：一個文字檔，包含匯出摘要，包括匯出統計資料。</span><span class="sxs-lookup"><span data-stu-id="7bab1-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="7bab1-156">Extracted_text_files：此資料夾包含每個匯出的檔的文字檔版本。</span><span class="sxs-lookup"><span data-stu-id="7bab1-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="7bab1-157">NativeFiles：此資料夾包含每個匯出檔的原生檔案版本。</span><span class="sxs-lookup"><span data-stu-id="7bab1-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="7bab1-158">Error_files：當匯出工作包含任何錯誤檔時，此資料夾包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="7bab1-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="7bab1-159">ExtractionError.csv：此 CSV 檔案包含未從其上層專案正確提取之檔案可用的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="7bab1-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="7bab1-160">ProcessingError：此資料夾包含處理錯誤的檔。</span><span class="sxs-lookup"><span data-stu-id="7bab1-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="7bab1-161">此內容屬於專案層級，這表示如果附件發生處理錯誤，包含附件的檔也會包含在此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="7bab1-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="7bab1-162">若要匯出匯出中的所有內容，請選取 [匯出] 資料夾，然後按一下 [ **下載**]。</span><span class="sxs-lookup"><span data-stu-id="7bab1-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="7bab1-163">指定您要下載匯出檔案的位置，然後按一下 [選取資料夾]。</span><span class="sxs-lookup"><span data-stu-id="7bab1-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="7bab1-164">Azure Storage Explorer 會啟動匯出程式。</span><span class="sxs-lookup"><span data-stu-id="7bab1-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="7bab1-165">[ **活動** ] 窗格中會顯示所匯出專案的下載狀態。</span><span class="sxs-lookup"><span data-stu-id="7bab1-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="7bab1-166">下載完成時，會顯示一則訊息。</span><span class="sxs-lookup"><span data-stu-id="7bab1-166">A message is displayed when the download is finished.</span></span>

    ![當下載完成時，會顯示一則訊息](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="7bab1-168">您可以選取要下載的特定專案，而不是下載整個匯出工作。</span><span class="sxs-lookup"><span data-stu-id="7bab1-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="7bab1-169">您可以按兩下專案來查看專案，而不是下載專案。</span><span class="sxs-lookup"><span data-stu-id="7bab1-169">And instead of downloading items, you can double-click an item to view it.</span></span>
