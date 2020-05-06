---
title: 下載調查的匯出工作
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
description: 安裝和使用 Azure Storage Explorer，以下載資料調查中從證據匯出的檔。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b9f3ee173fd9068f459e10b95fd497b7cf5015fc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035685"
---
# <a name="download-export-jobs"></a>下載匯出工作

當您從資料調查中的證據匯出檔時，會將檔上傳至 Microsoft 提供的 Azure 存放區位置，或組織所管理的 Azure 儲存體位置。 使用的 Azure 儲存位置類型取決於匯出檔時選取的選項。 

本文提供如何使用 Microsoft Azure Storage Explorer 連線到 Azure 存放位置，以流覽及下載匯出的檔的指示。 如需 Azure Storage Explorer 的詳細資訊，請參閱[快速入門：使用 Azure Storage explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。

## <a name="step-1-install-the-azure-storage-explorer"></a>步驟1：安裝 Azure Storage Explorer

第一個步驟是下載及安裝 Azure Storage Explorer。 如需相關指示，請參閱[Azure Storage Explorer 工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。 您可以使用此工具，在步驟3中連線並下載匯出的檔。

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>步驟2：從匯出工作取得 SAS URL

下一步是取得當您建立匯出工作以[從審閱集匯出檔](export-documents-from-review-set.md)時所產生的共用存取簽名（SAS） URL。 您可以複製上傳至 Microsoft 提供之 Azure 存放區位置或您組織所管理之 Azure 存放位置之檔的 SAS URL。 在這兩種情況下，您可以使用 SAS URL 連線至步驟3中的 Azure 儲存體位置。

1. 在 [**資料調查**] 頁面上，移至 [調查]，然後按一下 [**匯出**] 索引標籤。

2. 在 [**匯出**] 索引標籤上，按一下您要下載的匯出工作。

3. 在飛入頁面的 [**位置**] 下，複製所顯示的 SAS URL。 如有必要，您可以將它儲存至檔案，讓您可以在步驟3中存取。
 
   ![複製顯示在 [位置] 底下的 SAS URL](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a>步驟3：連線至 Azure 存放區位置

最後一個步驟是使用 Azure Storage Explorer 和 SAS URL 連線至 Azure 存放位置，並下載匯出至本機電腦的檔。

1.  開啟您在步驟1中安裝的 Azure 存放區 Explorer。

2. 按一下 [**新增帳戶**] 圖示。 或者，您也可以用滑鼠右鍵按一下 [**儲存帳戶**]。

   ![按一下 [新增帳戶] 圖示](../media/AzureStorageConnect.png)

3.  在 [ **Connect To Azure Storage]** 頁面上，按一下 [**使用共用存取簽名（SAS）] URI** ，然後按 **[下一步]**。

    ![按一下 [使用共用存取簽名（SAS）] URI，然後按 [下一步]](../media/AzureStorageConnect2.png)

4.  在 [**附加于 SAS URI** ] 頁面上，按一下 [URI] 方塊，然後貼上您在步驟2中取得的 SAS URL。 

    ![在 [URI] 方塊中貼上 SAS URL](../media/AzureStorageConnect3.png)

    請注意，SAS URL 的一部分會顯示在 [**顯示名稱**] 方塊中。 在您連接至儲存位置後，會將此名稱當做**儲存帳戶**下所建立之容器的顯示名稱使用。 這個名稱是由資料調查的識別碼和唯一的識別碼所組成。 您可以保留預設顯示名稱或加以變更。 如果您進行變更，顯示名稱必須是唯一的。

5.  按 [下一步]****。

    隨即會顯示 [連線**摘要**] 頁面。
   
    ![按一下 [連線摘要] 頁面上的 [連線]，以連線至 Azure 存放位置。](../media/AzureStorageConnect4.png)

6. 在 [連線**摘要**] 頁面上，複查連線資訊，然後按一下 **[連接]**。 

    開啟 [ **Blob 容器**] 節點（[**儲存帳戶** > **（附加的容器）** \> ] 下）。 

    ![在 Blob 容器節點中匯出工作](../media/AzureStorageConnect5.png)

    包含以步驟4顯示名稱命名的容器。 此容器包含您已建立之每個匯出工作的資料夾。 這些資料夾是以對應至匯出工作識別碼的識別碼命名。 您可以在 [支援] 頁面上的 [**支援資訊**] 下，于 [**工作**] 索引標籤上所列的每個**針對匯出工作準備資料的資料**匯出 IDs （和匯出的名稱）。

7. 按兩下 [匯出] 工作資料夾以將其開啟。

   隨即會顯示資料夾清單及匯出報告。
   
    ![匯出資料夾包含匯出的檔案和匯出報告](../media/AzureStorageConnect6.png)

   「匯出工作」資料夾包含下列專案。 匯出資料夾中的實際專案是由建立匯出工作時設定的匯出選項所決定。 如需詳細資訊，請參閱[從審閱集匯出檔](export-documents-from-review-set.md)。

    - Export_load_file .csv：此 CSV 檔是包含每個匯出檔相關資訊的詳細資料匯出報告。 檔案由每個檔的中繼資料屬性的欄所組成。 如需此報告中包含之中繼資料的清單和描述，請參閱[Advanced eDiscovery 中檔元資料欄位](document-metadata-fields.md)之表格中的**匯出**的功能變數名稱欄。
    
    - 摘要：一個文字檔，包含匯出摘要，包括匯出統計資料。
    
    - Extracted_text_files：此資料夾包含每個匯出的檔的文字檔版本。
     
    - NativeFiles：此資料夾包含每個匯出檔的原生檔案版本。
    
    - Error_files：當匯出工作包含任何錯誤檔時，此資料夾包含下列專案： 
        
      - ExtractionError：此 CSV 檔案包含未從其上層專案正確提取之檔案可用的中繼資料。
        
      - ProcessingError：此資料夾包含處理錯誤的檔。 此內容屬於專案層級，這表示如果附件發生處理錯誤，包含附件的檔也會包含在此資料夾中。
 
8. 若要匯出匯出中的所有內容，請選取 [匯出] 資料夾，然後按一下 [**下載**]。

9. 指定您要下載匯出檔案的位置，然後按一下 [**選取資料夾**]。

    Azure Storage Explorer 會啟動匯出程式。 [**活動**] 窗格中會顯示所匯出專案的下載狀態。 下載完成時，會顯示一則訊息。

    ![當下載完成時，會顯示一則訊息](../media/AzureStorageConnect8.png)

> [!NOTE]
> 您可以選取要下載的特定專案，而不是下載整個匯出工作。 您可以按兩下專案來查看專案，而不是下載專案。

