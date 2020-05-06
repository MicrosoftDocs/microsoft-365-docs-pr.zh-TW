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
description: 瞭解如何選取及匯出或下載簡報或外部評論的審閱集合中的內容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 29c2224a1ce0a92bca3b2057352f6f82fdc7afde
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034091"
---
# <a name="export-documents-from-a-review-set"></a>從檢閱集匯出文件

您可以透過下列其中一種方法，從審閱集中匯出簡報或外部審閱內容：

- [下載檔案](#download-documents-from-a-review-set)
 
- [匯出檔](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a>從審閱集下載檔案

下載提供一種簡單的方式，可從原生格式的審閱集下載內容。 它會利用瀏覽器的資料傳輸功能，讓下載做好準備時出現瀏覽器提示。 使用此方法下載的檔案會壓縮成容器檔案，並將成為專案層級檔案。 這表示如果您選取附件，將會自動收到包含附件的電子郵件。 同樣地，如果您選取嵌入在 word 檔中的 excel 試算表，您會收到 word 檔，並嵌入 excel 試算表。 已下載的專案會保留最後一個修改的日期，該日期可以看作是檔案屬性。

若要從審閱集下載內容，請先選取您想要下載的檔案，然後選取 [動作] 功能表中的 [下載]。

![自動產生電腦描述的螢幕擷取畫面](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a>從檢閱集匯出文件

匯出功能可讓使用者自訂下載套件所包含的內容。 它會提供具有下列設定的設定頁面：

### <a name="metadata-file"></a>元資料檔案

這可以視為您的「載入檔案」，該檔案包含與匯出之檔案相關聯的中繼資料。 如需元資料檔案中可用的匯出欄位清單，請參閱[Advanced eDiscovery 中的檔元資料欄位](document-metadata-fields-in-Advanced-eDiscovery.md)。 這個檔案通常可由協力廠商工具來 ingested。

### <a name="tag-data"></a>標記資料

此內容會新增為元資料檔案中的欄位。 包含所有套用至審查集的標記資訊。

### <a name="text-files"></a>文字檔

可為從審閱集匯出的每個檔案產生文字檔。 這些檔案通常是服務合作夥伴在 ingesting 資料到協力廠商工具的一部分時所需的時間。

### <a name="redacted-files"></a>Redacted 檔案

如果審閱時產生 redacted PDF 檔案，則在匯出期間可使用這些檔案。 您可以決定是否只匯出原生檔案，或將需要密文的原生檔案取代成包含實際密文的 PDF 檔案。

### <a name="export-location"></a>匯出位置

匯出的內容會傳送至 Microsoft 提供的 Azure blob 或客戶的 blob，如果在匯出時提供詳細資料，即可使用。

### <a name="export-structure"></a>匯出結構

從審閱集匯出內容時，會以下列結構組織內容。

  - 根資料夾–下載識別碼
    
      - Export\_load\_file .csv = metadata file
    
      - 摘要 .txt = 具有匯出統計資料的摘要檔案
    
      - 輸入\_或原\_生檔案 = 包含所有的原生檔案
    
      - 錯誤\_檔案 = 包含匯出中包含的任何錯誤檔案
        
          - ExtractionError –包含未從父系檔案正確提取之任何可用檔案中繼資料的 csv
        
          - ProcessingError –具有處理錯誤的內容。 此內容是專案層級的意義。如果附件發生處理錯誤，包含附件的電子郵件將會包含在此資料夾中。
    
      - 解壓縮\_的\_文字檔 = 包含處理時所產生的所有解壓縮文字檔。
