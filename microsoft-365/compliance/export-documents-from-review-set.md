---
title: 從檢閱集匯出文件
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
description: 瞭解如何在簡報或外部評論的高級 eDiscovery 檢查集中，選取及匯出內容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581014"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>從高級 eDiscovery 的審閱集中匯出檔

匯出功能可讓使用者在您從 Advanced eDiscovery 的審閱集中匯出檔時，自訂下載套件所包含的內容。

若要從審閱集匯出檔：

1. 在 Microsoft 365 規範中心，開啟 [高級 eDiscovery] 案例，選取 [ **複查集** ] 索引標籤，然後選取您要匯出的複查集。

2. 在 [檢查] 集中，按一下 [**動作**  >  **匯出**]。

   匯出工具會顯示飛出的頁面，包含設定匯出的設定。 有些選項預設為選取狀態，但您可以變更這些選項。 請參閱下一節，以取得您可以設定的匯出選項的描述。

   ![從審閱集匯出專案的設定選項](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. 設定匯出後，按一下 [ **匯出** ] 以啟動匯出程式。 根據您在 [ **輸出選項** ] 區段中選取的選項，您可以透過直接下載或組織的 Azure 儲存體帳戶來存取匯出檔案。

> [!NOTE]
> 匯出工作會在案例週期內保留。 不過，您必須在匯出工作完成後的30天內，從匯出工作下載內容。

## <a name="export-options"></a>匯出選項

使用下列選項來設定匯出。

- **匯出名稱**：匯出工作的名稱。

- **描述**：可讓您新增描述的自由文字欄位。

- **匯出這些檔**

  - **僅限選取的檔**：此選項只會匯出目前選取的檔。
  
  - **審閱集中的所有檔**：此選項會匯出審閱集中的所有檔。

- **中繼資料**
  
  - **Load file**：此檔案包含每個檔案的中繼資料。 這個檔案通常可由協力廠商的 eDiscovery 工具來 ingested。 如需包含哪些欄位的詳細資訊，請參閱 [Advanced eDiscovery 中的檔元資料欄位](document-metadata-fields-in-Advanced-eDiscovery.md)。
  
  - **標記**：選取此選項時，會將標記資訊包含在載入檔案中。

- **內容**
  
  - **原生** 檔案：選取此核取方塊，以在審閱集中包含檔的原生檔案。 如果您選擇匯出原生檔案，您可以使用下列選項來瞭解如何匯出聊天交談。
  
  - **交談選項**

    - **交談** 檔案：此選項會匯出重新構建的交談交談。 這種格式會顯示與使用者在原生應用程式中看到的外觀類似的對話。

    - **個別聊天訊息**：此選項會在原始交談檔案儲存在 Microsoft 365 中時，將其匯出。

- **選項**

  - **文字檔**：-此選項包含匯出中的原生檔案的解壓縮文字版本。
  
  - **以轉換的 Pdf 取代 redacted natives**：如果在審核期間產生 redacted PDF 檔案，這些檔案可供匯出。 您可以選擇只匯出 redacted (的原生檔案，但不要選取此選項) 或選取此選項，即可匯出包含實際密文的 PDF 檔案。

- **輸出選項**：匯出的內容可透過網頁瀏覽器直接下載，或是可以傳送至 Azure 儲存體帳戶。 前兩個選項可讓您直接下載。
  
  - **鬆散檔案與 pst (電子郵件會在可能) 時新增至 pst**：以類似使用者在原生應用程式中所看到之原始目錄結構的格式匯出檔案。  如需詳細資訊，請參閱 [鬆散檔案及 PST 匯出結構](#loose-files-and-pst-export-structure) 一節。
  
  - **緊縮的目錄結構**：檔案會匯出並包含在下載檔案中。
  
  - 已 **匯出至您的 Azure 儲存體帳戶的緊縮目錄結構**：檔案會匯出至您組織的 azure 儲存體帳戶。 針對此選項，您必須提供 Azure 儲存體帳戶中容器的 URL，才能將檔案匯出至。 您也必須為您的 Azure 儲存體帳戶提供共用存取簽名 (SAS) token。 如需詳細資訊，請參閱 [將檔匯出為審閱集合中的 Azure 儲存體帳戶](download-export-jobs.md)。

下列各節說明鬆散檔案和緊縮目錄結構選項的資料夾結構。

### <a name="loose-files-and-pst-export-structure"></a>鬆散檔與 PST 匯出結構

如果您選取此匯出選項，匯出的內容會以下列結構組織：

- 根資料夾：此資料夾命名為 ExportName.zip
  
  - Export_load_file.csv：元資料檔案。
  
  - Summary.csv：也包含匯出統計資料的摘要檔案。
  
  - Exchange：此資料夾包含所有來自 Exchange 的內容，以原生檔案格式。 如果您選取 [ **以轉換的 Pdf 取代 redacted Natives** ] 選項，則 Natives 檔案會取代為 redacted pdf。
  
  - SharePoint：此資料夾包含以原生檔案格式 SharePoint 的所有本機內容。 如果您選取 [ **以轉換的 Pdf 取代 redacted Natives** ] 選項，則 Natives 檔案會取代為 redacted pdf。

### <a name="condensed-directory-structure"></a>緊縮目錄結構

- 根資料夾：此資料夾命名為 ExportName.zip
  
  - Export_load_file.csv：元資料檔案。
  
  - Summary.txt：也包含匯出統計資料的摘要檔案。
  
  - NativeFiles：此資料夾包含所有已匯出的原生檔案。 如果您匯出的是 redacted PDF 檔案，則不會放入 PST 檔案。 相反地，它們會新增至分開的資料夾。
  
  - Error_files：此資料夾包含下列錯誤檔案（如果它們包含在匯出中）：

    - ExtractionError：包含未從父系檔案正確提取之任何可用檔案中繼資料的 CSV 檔案。

    - ProcessingError：此檔案包含含處理錯誤的檔案清單。 此內容屬於專案層級，也就是說，如果附件導致處理錯誤，則包含附件的電子郵件會包含在此資料夾中。
  
  - Extracted_text_files：此資料夾包含在處理時所產生的所有解壓縮文字檔。
