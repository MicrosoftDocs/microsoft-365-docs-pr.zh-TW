---
title: 將檔匯出至您組織的 Azure 儲存體帳戶
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
description: 將檔中的審閱集匯出至 Azure 儲存體帳戶，然後使用 Azure Storage Explorer 將其下載到本機電腦。
ms.openlocfilehash: dfb3892f31e857d4744f6da337c924efaa87ab11
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574707"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a>將審閱集中的檔匯出至 Azure 儲存體帳戶

當您在高級 eDiscovery 案例中從審閱集匯出檔時，您可以選擇將其匯出至組織所管理的 Azure 儲存體帳戶。 如果您使用此選項，則會將檔上傳至您的 Azure 存放區位置。 匯出之後，您可以使用 Azure Storage Explorer (，存取檔，並將其下載至本機電腦或其他位置) 。 本文將說明如何將檔匯出至您的 Azure 儲存體帳戶，以及使用 Azure Storage Explorer 連線到 Azure 存放位置，以下載匯出的檔。 如需 Azure Storage Explorer 的詳細資訊，請參閱 [Use Azure Storage explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。

## <a name="before-you-export-documents-from-a-review-set"></a>從審閱集匯出檔之前

- 您必須為您的 Azure 儲存體帳戶提供共用存取簽名 (SAS) token，以及儲存帳戶中特定容器的 URL，以便從審閱集匯出檔。 請務必手動取得這些 (例如，複製至文字檔) 當您執行步驟2時

  - **Sas 權杖**：請務必取得您的 Azure 儲存體帳戶的 SAS token (，而不是) 容器。 您可以在 Azure Storage 中為您的帳戶產生 SAS 權杖。 若要執行此動作，請移至 Azure 儲存體帳戶，然後選取儲存帳戶 blade 之 [**設定**] 下的 [**共用存取簽名**]。 當您產生 SAS 權杖時，請使用預設設定並允許所有資源類型。

  - **容器 URL**：您必須建立容器，將審閱集檔上傳至，然後取得容器的 URL 複本;例如， `https://ediscoverydata.blob.core.windows.net/exportdata` 。 若要取得 URL，請移至 Azure Storage 中的容器，然後選取容器 blade 中 [**設定**] 區段下的 [**屬性**]。

- 下載及安裝 Azure Storage Explorer。 如需相關指示，請參閱 [Azure Storage Explorer 工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。 您可以使用此工具來連線至您的 Azure 儲存體帳戶中的容器，並下載您在步驟1中匯出的檔。

## <a name="step-1-export-the-documents-from-a-review-set"></a>步驟1：從審閱集匯出檔

第一步是建立匯出工作，將檔匯出為審閱集。 如需所有匯出選項的詳細指示，請參閱 [從審閱集匯出檔](export-documents-from-review-set.md)。 下列程式會強調將檔匯出到您組織的 Azure 儲存體帳戶的設定。

1. 在 Microsoft 365 規範中心，開啟 [高級 eDiscovery] 案例，選取 [ **複查集** ] 索引標籤，然後選取您要匯出的複查集。

2. 在 [檢查] 集中，按一下 [**動作**  >  **匯出**]。

3. 在 [ **匯出選項** ] 飛入頁面上，輸入 (必要) 和描述的名稱，以供匯出 (選用) 。

4. 設定 [檔]、[中繼資料]、[內容] 及 [選項] 區段中的設定。 如需這些設定的詳細資訊，請參閱 [從審閱集匯出檔](export-documents-from-review-set.md)。

5. 在 [ **輸出選項** ] 區段中，選取 [ **匯出至您的 Azure 儲存體帳戶] 選項的緊縮目錄結構** 。

6. 在對應的欄位中貼上儲存體帳戶的容器 URL 和 SAS 權杖。

   ![在對應的欄位中貼上連接 URL 和 SAS 權杖](../media/AzureStorageOutputOptions.png)

7. 按一下 [ **匯出** ] 以建立匯出工作。

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>步驟2：從匯出工作取得 SAS URL

下一步是取得您在步驟1中建立匯出工作之後所產生的 SAS URL。 您可以使用 SAS URL 連線至您的 Azure 儲存體帳戶中您匯出的審閱集檔的容器。

1. 在 [ **高級電子** 檔探索] 頁面上，移至案例，然後按一下 [ **匯出** ] 索引標籤。

2. 在 [ **匯出** ] 索引標籤上，按一下您要下載的匯出工作。 這是您在步驟1中建立的匯出工作。

3. 在飛入頁面的 [ **位置**] 下，複製所顯示的 SAS URL。 如有必要，您可以將它儲存至文字檔，以便在步驟3中存取。

   ![複製顯示在 [位置] 底下的 SAS URL](../media/eDiscoExportJob.png)

   > [!TIP]
   > 在匯出工作中顯示的 SAS URL 是串聯的容器 URL 和 SAS 權杖的 Azure 儲存體帳戶。 您可以從匯出工作複製它，或結合 URL 和 SAS 權杖，自行建立。

## <a name="step-3-connect-to-the-azure-storage-container"></a>步驟3：連線至 Azure 儲存體容器

最後一個步驟是使用 Azure Storage Explorer 和 SAS URL 來連線至您的 Azure 儲存體帳戶中的容器，並將匯出的檔下載到本機電腦。

1. 啟動您下載並安裝的 Azure 存放區 Explorer。

2. 按一下 [ **開啟連線] 對話方塊** 圖示。

   ![按一下 [新增帳戶] 圖示](../media/AzureStorageConnect.png)

3. 在 [ **Connect To Azure Storage]** 頁面上，按一下 [ **Blob 容器**]。

4. 在 [ **選取驗證方法** ] 頁面上，選取 [ **共用存取簽名 (SAS)** ] 選項，然後按 **[下一步]**。

5. 在 [ **輸入連線資訊** ] 頁面上，貼上您在 [ **BLOB 容器 SAS url** ] 方塊中，于 [步驟 2]) 的 [匯出工作] 中取得的 SAS URL (。

    ![在 [URI] 方塊中貼上 SAS URL](../media/AzureStorageConnect3.png)

    請注意，容器名稱會顯示在 [ **顯示名稱** ] 方塊中。 您可以編輯此名稱。

6. 按 **[下一步** ] 顯示 [ **摘要** ] 頁面，然後按一下 **[連接]**。

    會開啟 [**儲存帳戶**] (所連接的) 容器] 下 (的 [ **Blob 容器**] 節點  >   \> 。

    ![在 Blob 容器節點中匯出工作](../media/AzureStorageConnect5.png)

    包含以步驟5顯示名稱命名的容器。 此容器包含您已下載至您的 Azure 儲存體帳戶中的容器之每個匯出工作的資料夾。 這些資料夾是以對應至匯出工作識別碼的識別碼命名。 您可以在 [支援] 頁面上的 [支援資訊] 頁面上，找到這些匯出 IDs (，) 並在 [支援] 頁面的 [ **支援資訊** ] 頁面上，針對每個 **準備匯出** 工作所 **列于 [** 高級 eDiscovery 案例

7. 按兩下 [匯出] 工作資料夾以將其開啟。

   隨即會顯示資料夾清單及匯出報告。

    ![匯出資料夾包含匯出的檔案和匯出報告](../media/AzureStorageConnect6.png)

8. 若要匯出匯出工作中的所有內容，請按一下 **向上** 箭號以回到匯出工作資料夾，然後按一下 [ **下載**]。

9. 指定您要下載匯出檔案的位置，然後按一下 [選取資料夾]。

    Azure Storage Explorer 會啟動下載程式。 [ **活動** ] 窗格中會顯示所匯出專案的下載狀態。 下載完成時，會顯示一則訊息。

> [!NOTE]
> 您可以選取要下載及查看的特定專案，而不是在 Azure Storage Explorer 中下載整個匯出工作。

## <a name="more-information"></a>詳細資訊

- 「匯出工作」資料夾包含下列專案。 匯出資料夾中的實際專案是由建立匯出工作時設定的匯出選項所決定。 如需這些選項的詳細資訊，請參閱 [從審閱集匯出檔](export-documents-from-review-set.md)。

  - Export_load_file.csv：此 CSV 檔是包含每個匯出檔相關資訊的詳細資料匯出報告。 檔案由每個檔的中繼資料屬性的欄所組成。 如需此報告中包含之中繼資料的清單和描述，請參閱 [Advanced eDiscovery 中檔元資料欄位](document-metadata-fields-in-advanced-ediscovery.md)之表格中的 **匯出** 的功能變數名稱欄。

  - Summary.txt：一個文字檔，包含匯出摘要，包括匯出統計資料。

  - Extracted_text_files：此資料夾包含每個匯出的檔的文字檔版本。

  - NativeFiles：此資料夾包含每個匯出檔的原生檔案版本。

  - Error_files：當匯出工作包含任何錯誤檔時，此資料夾包含下列專案：

    - ExtractionError.csv：此 CSV 檔案包含未從其上層專案正確提取之檔案可用的中繼資料。

    - ProcessingError：此資料夾包含處理錯誤的檔。 此內容屬於專案層級，這表示如果附件發生處理錯誤，包含附件的檔也會包含在此資料夾中。
