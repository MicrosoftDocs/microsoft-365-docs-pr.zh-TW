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
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a>將審閱集中的檔匯出為 Azure 儲存體帳戶

當您在 Advanced eDiscovery 案例中從審閱集匯出檔時，您可以選擇將其匯出至組織所管理的 Azure 儲存體帳戶。 如果您使用此選項，則會將檔上傳至您的 Azure 儲存體位置。 匯出後，您就可以 (存取檔，並使用 Azure 儲存體總管將檔下載到本機電腦或其他位置) 。 本文將說明如何將檔匯出至 Azure 儲存體帳戶，以及使用 Azure 儲存體總管連線至 Azure 儲存體位置，以下載匯出的檔。 如需 Azure 儲存體總管的詳細資訊，請參閱[使用 Azure 儲存體總管](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。

## <a name="before-you-export-documents-from-a-review-set"></a>從審閱集匯出檔之前

- 您必須提供 Azure 儲存體帳戶的共用存取簽名 (SAS) token，以及儲存帳戶中特定容器的 URL，才能從審閱集匯出檔。 請務必手動取得這些 (例如，複製至文字檔) 當您執行步驟2時

  - **sas 權杖**：請務必為您的 Azure 儲存體帳戶 (（而非容器) ）取得 SAS 權杖。 您可以在 Azure 儲存體中為您的帳戶產生 SAS 權杖。 若要執行此動作，請移至 Azure 儲存體帳戶，然後選取儲存體帳戶 blade 中 **設定** 設定底下的 [**共用存取簽名**]。 當您產生 SAS 權杖時，請使用預設設定並允許所有資源類型。

  - **容器 URL**：您必須建立容器，將審閱集檔上傳至，然後取得容器的 URL 複本;例如， `https://ediscoverydata.blob.core.windows.net/exportdata` 。 若要取得 URL，請移至 Azure 儲存體中的容器，然後選取容器 blade 中的 [**設定**] 區段下的 [**屬性**]。

- 下載並安裝 Azure 儲存體總管。 如需相關指示，請參閱[Azure 儲存體總管 tool](https://go.microsoft.com/fwlink/p/?LinkId=544842)。 您可以使用此工具來連線至 Azure 儲存體帳戶中的容器，並下載您在步驟1中匯出的檔。

## <a name="step-1-export-the-documents-from-a-review-set"></a>步驟1：從審閱集匯出檔

第一步是建立匯出工作，將檔匯出為審閱集。 如需所有匯出選項的詳細指示，請參閱 [從審閱集匯出檔](export-documents-from-review-set.md)。 下列程式會強調將檔匯出至組織 Azure 儲存體帳戶的設定。

1. 在 Microsoft 365 合規性中心中，開啟 Advanced eDiscovery 案例，選取 [**複查集**] 索引標籤，然後選取您要匯出的複查集。

2. 在 [檢查] 集中，按一下 [**動作**  >  **匯出**]。

3. 在 [ **匯出選項** ] 飛入頁面上，輸入 (必要) 和描述的名稱，以供匯出 (選用) 。

4. 設定 [檔]、[中繼資料]、[內容] 及 [選項] 區段中的設定。 如需這些設定的詳細資訊，請參閱 [從審閱集匯出檔](export-documents-from-review-set.md)。

5. 在 [**輸出選項**] 區段中，選取 **匯出至 Azure 儲存體帳戶] 選項的緊縮目錄結構**。

6. 在對應的欄位中貼上儲存體帳戶的容器 URL 和 SAS 權杖。

   ![在對應的欄位中貼上連接 URL 和 SAS 權杖](../media/AzureStorageOutputOptions.png)

7. 按一下 [ **匯出** ] 以建立匯出工作。

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>步驟2：從匯出工作取得 SAS URL

下一步是取得您在步驟1中建立匯出工作之後所產生的 SAS URL。 您可以使用 SAS URL 連線至您在 Azure 儲存體帳戶中匯出審閱集檔的容器。

1. 在 [ **Advanced eDiscovery** ] 頁面上，移至案例，然後按一下 [**匯出**] 索引標籤。

2. 在 [**匯出**] 索引標籤，按一下您要下載的匯出工作。 這是您在步驟1中建立的匯出工作。

3. 在飛入頁面的 [ **位置**] 下，複製所顯示的 SAS URL。 如有必要，您可以將它儲存至文字檔，以便在步驟3中存取。

   ![複製顯示在 [位置] 底下的 SAS URL](../media/eDiscoExportJob.png)

   > [!TIP]
   > 在匯出工作中顯示的 SAS URL 會串聯容器 url 和 Azure 儲存體帳戶的 SAS 權杖。 您可以從匯出工作複製它，或結合 URL 和 SAS 權杖，自行建立。

## <a name="step-3-connect-to-the-azure-storage-container"></a>步驟3：連線 Azure 儲存體容器

最後一個步驟是使用 Azure 儲存體總管和 SAS URL 連線至您 Azure 儲存體帳戶中的容器，並將匯出的檔下載到本機電腦。

1. 啟動您已下載及安裝的 Azure 儲存體總管。

2. 按一下 [**開啟連線] 對話方塊** 圖示。

   ![按一下 [新增帳戶] 圖示](../media/AzureStorageConnect.png)

3. 在 [**連線 Azure 儲存體**] 頁面上，按一下 [ **Blob 容器**]。

4. 在 [ **選取驗證方法** ] 頁面上，選取 [ **共用存取簽名 (SAS)** ] 選項，然後按 **[下一步]**。

5. 在 [ **輸入連線資訊** ] 頁面上，貼上您在 [ **BLOB 容器 SAS url** ] 方塊中，于 [步驟 2]) 的 [匯出工作] 中取得的 SAS URL (。

    ![在 [URI] 方塊中貼上 SAS URL](../media/AzureStorageConnect3.png)

    請注意，容器名稱會顯示在 [ **顯示名稱** ] 方塊中。 您可以編輯此名稱。

6. 按 **[下一步]** 顯示 [**摘要**] 頁面，然後按一下 [**連線**]。

    會開啟 [ **Blob 容器**] 節點 ([**儲存體帳戶**  >  **(附加的容器])** \> 。

    ![在 Blob 容器節點中匯出工作](../media/AzureStorageConnect5.png)

    包含以步驟5顯示名稱命名的容器。 此容器包含您已下載至 Azure 儲存體帳戶中的容器之每個匯出工作的資料夾。 這些資料夾是以對應至匯出工作識別碼的識別碼命名。 您可以在 [支援] 頁面上 **的 [資料] 索引** 標籤上，針對每個 **針對匯出** 工作所列的匯出工作，在 [支援] 頁面上的 [**支援資訊** Advanced eDiscovery] 下，找到這些匯出 IDs (和匯出) 名稱。

7. 按兩下 [匯出] 工作資料夾以將其開啟。

   隨即會顯示資料夾清單及匯出報告。

    ![匯出資料夾包含匯出的檔案和匯出報告](../media/AzureStorageConnect6.png)

8. 若要匯出匯出工作中的所有內容，請按一下 **向上** 箭號以回到匯出工作資料夾，然後按一下 [ **下載**]。

9. 指定要下載匯出檔案的位置，然後按一下 [選取資料夾]。

    Azure 儲存體總管會啟動下載程式。 [ **活動** ] 窗格中會顯示所匯出專案的下載狀態。 下載完成時，會顯示一則訊息。

> [!NOTE]
> 您可以選取要下載及查看的特定專案，而不是在 Azure 儲存體總管中下載整個匯出工作。

## <a name="more-information"></a>其他相關資訊

- 「匯出工作」資料夾包含下列專案。 匯出資料夾中的實際專案是由建立匯出工作時設定的匯出選項所決定。 如需這些選項的詳細資訊，請參閱 [從審閱集匯出檔](export-documents-from-review-set.md)。

  - Export_load_file.csv：此 CSV 檔是包含每個匯出檔相關資訊的詳細資料匯出報告。 檔案由每個檔的中繼資料屬性的欄所組成。 如需此報告中包含之中繼資料的清單和描述，請參閱 [Advanced eDiscovery 中檔元資料欄位](document-metadata-fields-in-advanced-ediscovery.md)之表格中的 **匯出** 的功能變數名稱欄。

  - Summary.txt：一個文字檔，包含匯出摘要，包括匯出統計資料。

  - Extracted_text_files：此資料夾包含每個匯出的檔的文字檔版本。

  - NativeFiles：此資料夾包含每個匯出檔的原生檔案版本。

  - Error_files：當匯出工作包含任何錯誤檔時，此資料夾包含下列專案：

    - ExtractionError.csv：此 CSV 檔案包含未從其上層專案正確提取之檔案可用的中繼資料。

    - ProcessingError：此資料夾包含處理錯誤的檔。 此內容屬於專案層級，這表示如果附件發生處理錯誤，包含附件的檔也會包含在此資料夾中。
