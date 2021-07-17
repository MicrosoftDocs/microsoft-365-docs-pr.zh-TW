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
description: 瞭解如何從簡報或外部評論的 Advanced eDiscovery 審閱集選取及匯出內容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a174c147da6e424891508bad484f45f4a5d308b6
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461396"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>從 Advanced eDiscovery 中的審閱集匯出檔

匯出功能可讓使用者在您從 Advanced eDiscovery 中的審閱集匯出檔時，自訂下載套件所包含的內容。

若要從審閱集匯出檔：

1. 在 Microsoft 365 合規性中心中，開啟 Advanced eDiscovery 案例，選取 [**複查集**] 索引標籤，然後選取您要匯出的複查集。

2. 在 [檢查] 集中，按一下 [**動作**  >  **匯出**]。

   匯出工具會顯示飛出的頁面，包含設定匯出的設定。 有些選項預設為選取狀態，但您可以變更這些選項。 請參閱下一節，以取得您可以設定的匯出選項的描述。

   ![從審閱集匯出專案的設定選項](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. 設定匯出後，按一下 [ **匯出** ] 以啟動匯出程式。 視您在 [**輸出選項**] 區段中選取的選項而定，您可以透過直接下載或組織的 Azure 儲存體帳戶來存取匯出檔案。

> [!NOTE]
> 匯出工作會在案例週期內保留。 不過，您必須在匯出工作完成後的30天內，從匯出工作下載內容。

## <a name="export-options"></a>匯出選項

使用下列選項來設定匯出。 並非所有選項都允許某些輸出選項，尤其是匯出至 PST 格式時不允許匯出文字檔和 redacted Pdf。

- **匯出名稱**：匯出工作的名稱。 這將用來命名將下載的 ZIP 檔案。

- **描述**：可讓您新增描述的自由文字欄位。

- **匯出這些檔**

  - 僅限選取的檔：此選項只會匯出目前選取的檔。 只有在審閱集中選取專案時，才可使用此選項。
  
  - 所有已篩選的檔：此選項會匯出使用中篩選器中的檔。 只有在對複查集套用篩選時，才可使用此選項。
  
  - 審閱集中的所有檔：此選項會匯出審閱集中的所有檔。

- **輸出選項**：匯出的內容可透過網頁瀏覽器直接下載，或是可以傳送至 Azure 儲存體帳戶。 前兩個選項可讓您直接下載。
  
  - 僅限報告：只會建立摘要和載入檔案。
  
  - 鬆散檔案與 Pst (電子郵件會在可能) 時新增至 Pst：以類似使用者在原生應用程式中所看到之原始目錄結構的格式匯出檔案。  如需詳細資訊，請參閱 [鬆散檔案及 PST 匯出結構](#loose-files-and-pst-export-structure) 一節。
  
  - 緊縮的目錄結構：檔案會匯出並包含在下載檔案中。
  
  - 匯出至 Azure 儲存體帳戶的緊縮目錄結構：檔案會匯出到您組織的 Azure 儲存體帳戶。 針對此選項，您必須提供 Azure 儲存體帳戶中容器的 URL，才能將檔案匯出至。 您也必須為您的 Azure 儲存體帳戶提供共用存取簽名 (SAS) token。 如需詳細資訊，請參閱[將檔匯出為審閱集中的 Azure 儲存體帳戶](download-export-jobs.md)。

- **Include**
  
  - 標記：選取此選項時，會將標記資訊包含在載入檔案中。
  
  - 文字檔：此選項包含匯出中原生檔案的解壓縮文字版本。
  
  - 以轉換的 Pdf 取代 redacted natives：如果在審核期間產生 redacted PDF 檔案，這些檔案可供匯出。 您可以選擇只匯出 redacted (的原生檔案，但不要選取此選項) 或選取此選項，即可匯出包含實際密文的 PDF 檔案。

下列各節說明鬆散檔案和緊縮目錄結構選項的資料夾結構。 匯出會分割成 ZIP 檔案，其大小上限為 75 GB 的解壓縮內容。 如果匯出大小小於 75 GB，則匯出會包含摘要檔和單一 ZIP 檔案。 若匯出的壓縮資料大於 75 GB，將會建立多個 ZIP 檔案。 下載後，可將 ZIP 檔案解壓縮到單一位置，以重新建立完整匯出。

### <a name="loose-files-and-pst-export-structure"></a>鬆散檔與 PST 匯出結構

如果您選取此匯出選項，匯出的內容會以下列結構組織：

- Summary.csv：包括從審閱集匯出的內容摘要

- 根資料夾：此資料夾命名為 [匯出名稱] x 的 z.zip，將會針對每個 ZIP 檔分割區重複此資料夾。
  
  - z.csv 的 Export_load_file_x：元資料檔案。
  
  - 警告與錯誤 z.csv：此檔案包含嘗試從審閱集匯出時，發生錯誤的相關資訊。
  
  - Exchange：此資料夾包含 Exchange 儲存于 PST 檔案中的所有內容。 Redacted PDF 檔案不能包含在此選項中。 如果在審閱集中選取了附件，將會使用附加的附件匯出上層電子郵件。
  
  - SharePoint：此資料夾包含以原生檔案格式 SharePoint 的所有本機內容。 Redacted PDF 檔案不能包含在此選項中。

### <a name="condensed-directory-structure"></a>緊縮目錄結構

- Summary.csv：包括從審閱集匯出的內容摘要

- 根資料夾：此資料夾命名為 [匯出名稱] x 的 z.zip，將會針對每個 ZIP 檔分割區重複此資料夾。
  
  - z.csv 的 Export_load_file_x：元資料檔案，也包含儲存在 ZIP 檔案中的每個檔案的位置。
  
  - 警告與錯誤 z.csv：此檔案包含嘗試從審閱集匯出時，發生錯誤的相關資訊。

  - NativeFiles：此資料夾包含所有已匯出的原生檔案。 如果您選取 [ *以轉換的 Pdf 取代 redacted Natives* ] 選項，則 Natives 檔案會取代為 redacted pdf。
  
  - Error_files：此資料夾包含提取或其他處理錯誤的檔案。 檔案會放在不同的資料夾中，ExtractionError 或 ProcessingError。 這些檔案會列于載入檔案中。

  - Extracted_text_files：此資料夾包含在處理時所產生的所有解壓縮文字檔。

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a>匯出至 Azure 儲存體帳戶的緊縮目錄結構

此選項使用與 *緊縮目錄結構* 相同的一般結構，但是不會壓縮內容，而且會將資料儲存至您的 Azure 儲存體帳戶。 使用協力廠商 eDiscovery 提供者時，通常會使用此選項。 如需如何使用此選項的詳細資訊，請參閱[將檔匯出為審閱集中的 Azure 儲存體帳戶](download-export-jobs.md)。
