---
title: 將檔匯出至組織的 Azure 儲存體帳戶
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
ms.custom: seo-marvel-mar2020
description: 將審閱集中的檔匯出為 Azure 儲存體帳戶，然後使用 Azure 儲存體總管將其下載到本機電腦。
ms.openlocfilehash: b7638e33a40a2ac46f4bb69b869e4c2cf6d48f65
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256504"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a><span data-ttu-id="6572f-103">將審閱集中的檔匯出為 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="6572f-103">Export documents in a review set to an Azure Storage account</span></span>

<span data-ttu-id="6572f-104">當您在 Advanced eDiscovery 案例中從審閱集匯出檔時，您可以選擇將其匯出至組織所管理的 Azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="6572f-104">When you export documents from a review set in an Advanced eDiscovery case, you have the option to export them to an Azure Storage account managed by your organization.</span></span> <span data-ttu-id="6572f-105">如果您使用此選項，則會將檔上傳至您的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="6572f-105">If you use this option, the documents are uploaded to your Azure Storage location.</span></span> <span data-ttu-id="6572f-106">匯出後，您就可以 (存取檔，並使用 Azure 儲存體總管將檔下載到本機電腦或其他位置) 。</span><span class="sxs-lookup"><span data-stu-id="6572f-106">After they are exported, you can access the documents (and download them to a local computer or other location) by using the Azure Storage Explorer.</span></span> <span data-ttu-id="6572f-107">本文將說明如何將檔匯出至 Azure 儲存體帳戶，以及使用 Azure 儲存體總管連線至 Azure 儲存體位置，以下載匯出的檔。</span><span class="sxs-lookup"><span data-stu-id="6572f-107">This article provides instructions for how to export documents to your Azure Storage account and the use the Azure Storage Explorer to connect to an Azure Storage location to download the exported documents.</span></span> <span data-ttu-id="6572f-108">如需 Azure 儲存體總管的詳細資訊，請參閱[使用 Azure 儲存體總管](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。</span><span class="sxs-lookup"><span data-stu-id="6572f-108">For more information about Azure Storage Explorer, see [Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="before-you-export-documents-from-a-review-set"></a><span data-ttu-id="6572f-109">從審閱集匯出檔之前</span><span class="sxs-lookup"><span data-stu-id="6572f-109">Before you export documents from a review set</span></span>

- <span data-ttu-id="6572f-110">您必須提供 Azure 儲存體帳戶的共用存取簽名 (SAS) token，以及儲存帳戶中特定容器的 URL，才能從審閱集匯出檔。</span><span class="sxs-lookup"><span data-stu-id="6572f-110">You need to provide a shared access signature (SAS) token for your Azure Storage account and the URL for a specific container in the storage account to export documents from a review set.</span></span> <span data-ttu-id="6572f-111">請務必手動取得這些 (例如，複製至文字檔) 當您執行步驟2時</span><span class="sxs-lookup"><span data-stu-id="6572f-111">Be sure to have these at hand (for example, copied to a text file) when you perform Step 2</span></span>

  - <span data-ttu-id="6572f-112">**sas 權杖**：請務必為您的 Azure 儲存體帳戶 (（而非容器) ）取得 SAS 權杖。</span><span class="sxs-lookup"><span data-stu-id="6572f-112">**SAS token**: Be sure to get the SAS token is for your Azure Storage account (and not for the container).</span></span> <span data-ttu-id="6572f-113">您可以在 Azure 儲存體中為您的帳戶產生 SAS 權杖。</span><span class="sxs-lookup"><span data-stu-id="6572f-113">You can generate an SAS token for your account in Azure Storage.</span></span> <span data-ttu-id="6572f-114">若要執行此動作，請移至 Azure 儲存體帳戶，然後選取儲存體帳戶 blade 中 **設定** 設定底下的 [**共用存取簽名**]。</span><span class="sxs-lookup"><span data-stu-id="6572f-114">To do this, go to the Azure Storage account, and select **Share access signature** under the **Settings** settings in the storage account blade.</span></span> <span data-ttu-id="6572f-115">當您產生 SAS 權杖時，請使用預設設定並允許所有資源類型。</span><span class="sxs-lookup"><span data-stu-id="6572f-115">Use the default settings and allow all resource types when you generate the SAS token.</span></span>

  - <span data-ttu-id="6572f-116">**容器 URL**：您必須建立容器，將審閱集檔上傳至，然後取得容器的 URL 複本;例如， `https://ediscoverydata.blob.core.windows.net/exportdata` 。</span><span class="sxs-lookup"><span data-stu-id="6572f-116">**Container URL**: You need to create a container to upload the review set documents to, and then get a copy of the URL for the container; for example, `https://ediscoverydata.blob.core.windows.net/exportdata`.</span></span> <span data-ttu-id="6572f-117">若要取得 URL，請移至 Azure 儲存體中的容器，然後選取容器 blade 中的 [**設定**] 區段下的 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6572f-117">To get the URL, go to the container in Azure Storage, and select **Properties** under the **Settings** section in the container blade.</span></span>

- <span data-ttu-id="6572f-118">下載並安裝 Azure 儲存體總管。</span><span class="sxs-lookup"><span data-stu-id="6572f-118">Download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="6572f-119">如需相關指示，請參閱[Azure 儲存體總管 tool](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="6572f-119">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="6572f-120">您可以使用此工具來連線至 Azure 儲存體帳戶中的容器，並下載您在步驟1中匯出的檔。</span><span class="sxs-lookup"><span data-stu-id="6572f-120">You use this tool to connect to the container in your Azure Storage account and download the documents that you exported in Step 1.</span></span>

## <a name="step-1-export-the-documents-from-a-review-set"></a><span data-ttu-id="6572f-121">步驟1：從審閱集匯出檔</span><span class="sxs-lookup"><span data-stu-id="6572f-121">Step 1: Export the documents from a review set</span></span>

<span data-ttu-id="6572f-122">第一步是建立匯出工作，將檔匯出為審閱集。</span><span class="sxs-lookup"><span data-stu-id="6572f-122">The first step is to create an export job to export documents out of a review set.</span></span> <span data-ttu-id="6572f-123">如需所有匯出選項的詳細指示，請參閱 [從審閱集匯出檔](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="6572f-123">For more detailed instructions about all the export options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="6572f-124">下列程式會強調將檔匯出至組織 Azure 儲存體帳戶的設定。</span><span class="sxs-lookup"><span data-stu-id="6572f-124">The following procedure highlights the settings to export documents to your organization's Azure Storage account.</span></span>

1. <span data-ttu-id="6572f-125">在 Microsoft 365 合規性中心中，開啟 Advanced eDiscovery 案例，選取 [**複查集**] 索引標籤，然後選取您要匯出的複查集。</span><span class="sxs-lookup"><span data-stu-id="6572f-125">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="6572f-126">在 [檢查] 集中，按一下 [**動作**  >  **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="6572f-126">In the review set, click **Action** > **Export**.</span></span>

3. <span data-ttu-id="6572f-127">在 [ **匯出選項** ] 飛入頁面上，輸入 (必要) 和描述的名稱，以供匯出 (選用) 。</span><span class="sxs-lookup"><span data-stu-id="6572f-127">On the **Export options** flyout page, type a name (required) and description (optional) for the export.</span></span>

4. <span data-ttu-id="6572f-128">設定 [檔]、[中繼資料]、[內容] 及 [選項] 區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="6572f-128">Configure the settings in the documents, metadata, content, and options sections.</span></span> <span data-ttu-id="6572f-129">如需這些設定的詳細資訊，請參閱 [從審閱集匯出檔](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="6572f-129">For more information about these settings, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

5. <span data-ttu-id="6572f-130">在 [**輸出選項**] 區段中，選取 **匯出至 Azure 儲存體帳戶] 選項的緊縮目錄結構**。</span><span class="sxs-lookup"><span data-stu-id="6572f-130">In the **Output options** section, select the **Condensed directory structure exported to your Azure Storage account** option.</span></span>

6. <span data-ttu-id="6572f-131">在對應的欄位中貼上儲存體帳戶的容器 URL 和 SAS 權杖。</span><span class="sxs-lookup"><span data-stu-id="6572f-131">Paste the container URL and the SAS token for your storage account in the corresponding fields.</span></span>

   ![在對應的欄位中貼上連接 URL 和 SAS 權杖](../media/AzureStorageOutputOptions.png)

7. <span data-ttu-id="6572f-133">按一下 [ **匯出** ] 以建立匯出工作。</span><span class="sxs-lookup"><span data-stu-id="6572f-133">Click **Export** to create the export job.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="6572f-134">步驟2：從匯出工作取得 SAS URL</span><span class="sxs-lookup"><span data-stu-id="6572f-134">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="6572f-135">下一步是取得您在步驟1中建立匯出工作之後所產生的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="6572f-135">The next step is to obtain the SAS URL that's generated after you create the export job in Step 1.</span></span> <span data-ttu-id="6572f-136">您可以使用 SAS URL 連線至您在 Azure 儲存體帳戶中匯出審閱集檔的容器。</span><span class="sxs-lookup"><span data-stu-id="6572f-136">You use the SAS URL to connect to the container in your Azure Storage account that you exported the review set documents to.</span></span>

1. <span data-ttu-id="6572f-137">在 [ **Advanced eDiscovery** ] 頁面上，移至案例，然後按一下 [**匯出**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6572f-137">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="6572f-138">在 [**匯出**] 索引標籤，按一下您要下載的匯出工作。</span><span class="sxs-lookup"><span data-stu-id="6572f-138">On the **Exports** tab, click the export job that you want to download.</span></span> <span data-ttu-id="6572f-139">這是您在步驟1中建立的匯出工作。</span><span class="sxs-lookup"><span data-stu-id="6572f-139">This is the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="6572f-140">在飛入頁面的 [ **位置**] 下，複製所顯示的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="6572f-140">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="6572f-141">如有必要，您可以將它儲存至文字檔，以便在步驟3中存取。</span><span class="sxs-lookup"><span data-stu-id="6572f-141">If necessary, you can save it to a text file so you can access it in Step 3.</span></span>

   ![複製顯示在 [位置] 底下的 SAS URL](../media/eDiscoExportJob.png)

   > [!TIP]
   > <span data-ttu-id="6572f-143">在匯出工作中顯示的 SAS URL 會串聯容器 url 和 Azure 儲存體帳戶的 SAS 權杖。</span><span class="sxs-lookup"><span data-stu-id="6572f-143">The SAS URL that's displayed in the export job is a concatenation of the container URL and the SAS token for your Azure Storage account.</span></span> <span data-ttu-id="6572f-144">您可以從匯出工作複製它，或結合 URL 和 SAS 權杖，自行建立。</span><span class="sxs-lookup"><span data-stu-id="6572f-144">You can copy it from the export job or create it yourself by combining the URL and the SAS token.</span></span>

## <a name="step-3-connect-to-the-azure-storage-container"></a><span data-ttu-id="6572f-145">步驟3：連線 Azure 儲存體容器</span><span class="sxs-lookup"><span data-stu-id="6572f-145">Step 3: Connect to the Azure Storage container</span></span>

<span data-ttu-id="6572f-146">最後一個步驟是使用 Azure 儲存體總管和 SAS URL 連線至您 Azure 儲存體帳戶中的容器，並將匯出的檔下載到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="6572f-146">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the container in your Azure Storage account and download the exported documents to a local computer.</span></span>

1. <span data-ttu-id="6572f-147">啟動您已下載及安裝的 Azure 儲存體總管。</span><span class="sxs-lookup"><span data-stu-id="6572f-147">Start the Azure Storage Explorer that you downloaded and installed.</span></span>

2. <span data-ttu-id="6572f-148">按一下 [**開啟連線] 對話方塊** 圖示。</span><span class="sxs-lookup"><span data-stu-id="6572f-148">Click the **Open Connect Dialog** icon.</span></span>

   ![按一下 [新增帳戶] 圖示](../media/AzureStorageConnect.png)

3. <span data-ttu-id="6572f-150">在 [**連線 Azure 儲存體**] 頁面上，按一下 [ **Blob 容器**]。</span><span class="sxs-lookup"><span data-stu-id="6572f-150">On the **Connect to Azure Storage** page, click **Blob container**.</span></span>

4. <span data-ttu-id="6572f-151">在 [ **選取驗證方法** ] 頁面上，選取 [ **共用存取簽名 (SAS)** ] 選項，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6572f-151">On the **Select Authentication Method** page, select the **Shared access signature (SAS)** option and then click **Next**.</span></span>

5. <span data-ttu-id="6572f-152">在 [ **輸入連線資訊** ] 頁面上，貼上您在 [ **BLOB 容器 SAS url** ] 方塊中，于 [步驟 2]) 的 [匯出工作] 中取得的 SAS URL (。</span><span class="sxs-lookup"><span data-stu-id="6572f-152">On the **Enter Connection Info** page, paste the SAS URL (that you obtained in the export job in Step 2) in the **Blob Container SAS URL** box.</span></span>

    ![在 [URI] 方塊中貼上 SAS URL](../media/AzureStorageConnect3.png)

    <span data-ttu-id="6572f-154">請注意，容器名稱會顯示在 [ **顯示名稱** ] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="6572f-154">Notice that the container name is displayed in the **Display name** box.</span></span> <span data-ttu-id="6572f-155">您可以編輯此名稱。</span><span class="sxs-lookup"><span data-stu-id="6572f-155">You can edit this name.</span></span>

6. <span data-ttu-id="6572f-156">按 **[下一步]** 顯示 [**摘要**] 頁面，然後按一下 [**連線**]。</span><span class="sxs-lookup"><span data-stu-id="6572f-156">Click **Next** to display the **summary** page and then click **Connect**.</span></span>

    <span data-ttu-id="6572f-157">會開啟 [ **Blob 容器**] 節點 ([**儲存體帳戶**  >  **(附加的容器])** \> 。</span><span class="sxs-lookup"><span data-stu-id="6572f-157">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![在 Blob 容器節點中匯出工作](../media/AzureStorageConnect5.png)

    <span data-ttu-id="6572f-159">包含以步驟5顯示名稱命名的容器。</span><span class="sxs-lookup"><span data-stu-id="6572f-159">It contains a container named with the display name from step 5.</span></span> <span data-ttu-id="6572f-160">此容器包含您已下載至 Azure 儲存體帳戶中的容器之每個匯出工作的資料夾。</span><span class="sxs-lookup"><span data-stu-id="6572f-160">This container contains a folder for each export job that you've downloaded to the container in your Azure Storage account.</span></span> <span data-ttu-id="6572f-161">這些資料夾是以對應至匯出工作識別碼的識別碼命名。</span><span class="sxs-lookup"><span data-stu-id="6572f-161">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="6572f-162">您可以在 [支援] 頁面上 **的 [資料] 索引** 標籤上，針對每個 **針對匯出** 工作所列的匯出工作，在 [支援] 頁面上的 [**支援資訊** Advanced eDiscovery] 下，找到這些匯出 IDs (和匯出) 名稱。</span><span class="sxs-lookup"><span data-stu-id="6572f-162">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab in the Advanced eDiscovery case.</span></span>

7. <span data-ttu-id="6572f-163">按兩下 [匯出] 工作資料夾以將其開啟。</span><span class="sxs-lookup"><span data-stu-id="6572f-163">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="6572f-164">隨即會顯示資料夾清單及匯出報告。</span><span class="sxs-lookup"><span data-stu-id="6572f-164">A list of folders and export reports is displayed.</span></span>

    ![匯出資料夾包含匯出的檔案和匯出報告](../media/AzureStorageConnect6.png)

8. <span data-ttu-id="6572f-166">若要匯出匯出工作中的所有內容，請按一下 **向上** 箭號以回到匯出工作資料夾，然後按一下 [ **下載**]。</span><span class="sxs-lookup"><span data-stu-id="6572f-166">To export all contents from the export job, click the **Up** arrow to go back to the export job folder, and then click **Download**.</span></span>

9. <span data-ttu-id="6572f-167">指定要下載匯出檔案的位置，然後按一下 [選取資料夾]。</span><span class="sxs-lookup"><span data-stu-id="6572f-167">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="6572f-168">Azure 儲存體總管會啟動下載程式。</span><span class="sxs-lookup"><span data-stu-id="6572f-168">The Azure Storage Explorer starts the download process.</span></span> <span data-ttu-id="6572f-169">[ **活動** ] 窗格中會顯示所匯出專案的下載狀態。</span><span class="sxs-lookup"><span data-stu-id="6572f-169">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="6572f-170">下載完成時，會顯示一則訊息。</span><span class="sxs-lookup"><span data-stu-id="6572f-170">A message is displayed when the download is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="6572f-171">您可以選取要下載及查看的特定專案，而不是在 Azure 儲存體總管中下載整個匯出工作。</span><span class="sxs-lookup"><span data-stu-id="6572f-171">Instead of downloading the entire export job in Azure Storage Explorer, you can select specific items to download and view.</span></span>

## <a name="more-information"></a><span data-ttu-id="6572f-172">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="6572f-172">More information</span></span>

- <span data-ttu-id="6572f-173">「匯出工作」資料夾包含下列專案。</span><span class="sxs-lookup"><span data-stu-id="6572f-173">The export job folder contains the following items.</span></span> <span data-ttu-id="6572f-174">匯出資料夾中的實際專案是由建立匯出工作時設定的匯出選項所決定。</span><span class="sxs-lookup"><span data-stu-id="6572f-174">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="6572f-175">如需這些選項的詳細資訊，請參閱 [從審閱集匯出檔](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="6572f-175">For more information about these options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

  - <span data-ttu-id="6572f-176">Export_load_file.csv：此 CSV 檔是包含每個匯出檔相關資訊的詳細資料匯出報告。</span><span class="sxs-lookup"><span data-stu-id="6572f-176">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="6572f-177">檔案由每個檔的中繼資料屬性的欄所組成。</span><span class="sxs-lookup"><span data-stu-id="6572f-177">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="6572f-178">如需此報告中包含之中繼資料的清單和描述，請參閱 [Advanced eDiscovery 中檔元資料欄位](document-metadata-fields-in-advanced-ediscovery.md)之表格中的 **匯出** 的功能變數名稱欄。</span><span class="sxs-lookup"><span data-stu-id="6572f-178">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>

  - <span data-ttu-id="6572f-179">Summary.txt：一個文字檔，包含匯出摘要，包括匯出統計資料。</span><span class="sxs-lookup"><span data-stu-id="6572f-179">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>

  - <span data-ttu-id="6572f-180">Extracted_text_files：此資料夾包含每個匯出的檔的文字檔版本。</span><span class="sxs-lookup"><span data-stu-id="6572f-180">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>

  - <span data-ttu-id="6572f-181">NativeFiles：此資料夾包含每個匯出檔的原生檔案版本。</span><span class="sxs-lookup"><span data-stu-id="6572f-181">NativeFiles: This folder contains a native file version of each exported document.</span></span>

  - <span data-ttu-id="6572f-182">Error_files：當匯出工作包含任何錯誤檔時，此資料夾包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="6572f-182">Error_files: This folder includes the following items when the export job contains any error files:</span></span>

    - <span data-ttu-id="6572f-183">ExtractionError.csv：此 CSV 檔案包含未從其上層專案正確提取之檔案可用的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="6572f-183">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>

    - <span data-ttu-id="6572f-184">ProcessingError：此資料夾包含處理錯誤的檔。</span><span class="sxs-lookup"><span data-stu-id="6572f-184">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="6572f-185">此內容屬於專案層級，這表示如果附件發生處理錯誤，包含附件的檔也會包含在此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="6572f-185">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
