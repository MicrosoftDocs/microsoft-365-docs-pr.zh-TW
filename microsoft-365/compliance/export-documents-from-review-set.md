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
description: ''
ms.openlocfilehash: 0448082ce6dcbcd9d1cee52557a78b2d7913a034
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41588353"
---
# <a name="export-documents-from-a-review-set"></a>從檢閱集匯出文件

您可以從下列方法之一來設定檢閱匯出簡報或外部的檢閱內容：

- [下載文件](#download-documents-from-a-review-set)
 
- [匯出的文件](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a>檢閱設定從下載文件

下載提供簡單的方法，從原生格式設定的設定檢閱下載內容。 它利用瀏覽器的資料傳輸功能，因此下載已準備好之後，就會顯示瀏覽器提示。 檔案下載使用此方法會壓縮成容器檔案，將項目層級的檔案。 這表示，如果您選取附件，您就會自動接收電子郵件包含附件。 同樣地，如果您選取 [已 excel 試算表內嵌於 word 文件，您會收到 word 文件與內嵌的 excel 試算表。 已下載的項目會保留檔案屬性為可檢視的上次修改的日期。

若要下載的內容從檢閱設定，啟動選取您要下載，然後選取 [動作] 功能表底下的 [「 下載 」 的檔案。

![說明自動產生之電腦的螢幕擷取畫面](media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a>從檢閱集匯出文件

匯出可讓使用者自訂隨附的下載套件中的內容。 它提供設定] 頁面上使用下列設定：

### <a name="metadata-file"></a>中繼資料檔案

這可視為您 「 載入檔案"，其中包含您匯出的檔案相關聯的中繼資料。 如需中繼資料檔案中可用的欄位的清單，請參閱\[連結\]。 此檔案通常可以 ingested 3<sup>rd</sup>廠商工具所傳輸。

### <a name="tag-data"></a>標記資料

此內容會新增為中繼資料檔案中的欄位。 它包含所有檢閱組中套用的標籤資訊。

### <a name="text-files"></a>文字檔

文字檔案可以產生的每個檢閱設定從匯出的檔案。 通常時間這些檔案所需的服務合作夥伴一部分 ingesting 資料到 3<sup>rd</sup>廠商工具傳輸。

### <a name="redacted-files"></a>Redacted 的檔案

如果檢閱期間所產生 redacted 的 Pdf，這些檔案匯出期間都使用。 使用者可以決定是否要匯出僅適用於原生檔案，或取代人民 Pdf 中具有與燒錄 redactions。

### <a name="export-location"></a>匯出的位置

匯出的內容會傳遞至下列一項 Microsoft 提供您可以使用 Azure blob 或客戶的 blob，如果在匯出並提供詳細資料。

### <a name="export-structure"></a>匯出結構

當內容來自檢閱設定匯出時，內容被組織中的下列結構。

  - 根資料夾 – 下載識別碼
    
      - 匯出\_載入\_file.csv = 中繼資料檔案
    
      - Summary.txt = 匯出統計資料摘要檔案
    
      - 輸入\_或原生\_檔案 = 包含所有的原生檔案
    
      - 錯誤\_檔案 = 包含任何包含在匯出的錯誤檔案
        
          - ExtractionError – csv 包含不正確地從父檔案解壓縮的任何的檔案可用的中繼資料
        
          - ProcessingError – 與處理錯誤的內容。 此內容是表示如果附件時發生錯誤處理，包含附件的電子郵件將會包含在此資料夾的項目層級。
    
      - 擷取\_文字\_檔案 = 包含所有在處理所產生的擷取的文字檔案。