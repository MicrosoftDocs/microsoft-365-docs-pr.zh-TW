---
title: 在高級電子檔探索中執行進程模組
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: 瞭解使用高級電子檔探索來準備資料大小的案例檔案的指導方針。
ms.openlocfilehash: 5130bea7da8922fd7e98d07696ffde3930d2ce41
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936196"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a>在 [Advanced eDiscovery （古典）] 中執行進程模組

在**準備**過程中，案例檔案會載入至高級 eDiscovery \> ** **。 
  
> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a>指導方針：準備用於高級電子檔探索的資料

- **Quality**：明確識別案例的相關案例檔。
    
- **載入**：將檔案載入至可供高級 eDiscovery 存取的位置。
    
- 檔案**識別碼：「** 高級 eDiscovery」中的唯一檔識別碼。 如果沒有匯入的檔案識別碼，高級 eDiscovery 便會自動產生識別碼。 如果您在後續的處理常式載入中對應識別碼，並且對應的路徑與初始程式負載中的不同，則 Advanced eDiscovery 將取代路徑（而不是新增新的檔案專案）。 在匯出程式中，可以使用識別碼做為參考。 識別碼值不應該是 "-1"。
    
- **MD5**：此簽章是用來區分檔案（兩個檔案不會被視為完全重複，除非有相同的 MD5）。 根據預設，「高級 eDiscovery」會計算檔的 MD5。 當載入的檔案為文字檔時，建議您在 [高級 eDiscovery] 中載入和對應原始的 MD5 值，而不是計算它。
    
- **檔案類型和名稱**：
    
  - 「高級 eDiscovery」可以處理各種格式的檔，並將載入的原生檔案解壓縮成標準格式，例如 \* 。TXT、HTML 或。Xml。 文字檔的處理速度比原生檔案更快。 解壓縮的文字檔會儲存在 case 資料夾中。
    
  - 請勿載入無法解壓縮的檔案，例如系統檔案或圖形影像。 這些檔案可能會延遲處理。
    
  - 請確認檔案名具有極大的名稱和路徑是否正確。
    
- 檔案**路徑**：「高級 eDiscovery」可以載入路徑長度最長為400個字元的檔案。
    
- **文字提取**：從原生檔案提取文字時，除了一般文字之外，還會提取下列專案：隱藏的文字（excel 及 .doc）、隱藏的欄（excel）、追蹤變更（.doc）、喇叭附注（.ppt）、內嵌的物件（例如，.ppt 中的 Excel 物件）。 這些可以在文字編輯器中查看。
    
- **Ignore Text**：此選用功能是在程式執行之後及分析之前定義。 忽略文字應謹慎使用，因為其使用可能會降低檔分析的效能。
    
- **多語系文字**：「高級 eDiscovery」目前並未處理標記、保管人及問題的多語系名稱。
    
- **中繼資料**：判斷是否要在案例資料庫中儲存以供日後參考的中繼資料，例如日期範圍、檔案大小、檔案類型、擁有者和主旨。 在不重新執行清查或重新處理重新處理的開銷的情況下，載入檔之後，即可載入中繼資料。 
    
  - 如果檔案最初是以 path 載入，請在以後匯入中繼資料時對應 [路徑] 欄位。 您可以依識別碼參照檔案，並對應不同的路徑。 當檔案路徑變更時，這是一個有用的案例。
    
  - 如果檔案最初是以檔識別碼載入，請在載入中繼資料時對應 [識別碼] 欄。 依路徑參照檔案（而不是識別碼）將會以不同的識別碼重新載入檔案。 「高級 eDiscovery」會建立檔案的複本，而不是載入現有檔案的中繼資料。
    
- **系列**：無法載入沒有其上級（族的頭部）的系列。 
    
- 檔案**大小**：載入至 [Advanced eDiscovery] 的檔案大小不會有任何限制。 為了進行分析（分析、相關性等等），限制為解壓縮文字的5242880個字元。 會略過較大的檔案（例如，在相關性中，檔案不會參與相關性訓練程式，也不會在批次計算後接收相關性分數）。
    
- 檔案**數量**：在單一案例中，可以處理的檔案數目不建議使用限制。 效能取決於您系統的資源。 
    
## <a name="filtering-files"></a>篩選檔案

使用者定義的標籤可以與一組檔案相關聯，使其不會從處理常式或其他任務中排除。 每個處理常式會話都與批次識別碼相關聯。 雖然相關聯的專家看不到 [批次識別碼]，但您可以使用搜尋公用程式，為目前的批次新增篩選，並使用使用者定義的標籤來標示所有適當的檔案，以完成此動作。 
  
## <a name="see-also"></a>請參閱

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[執行處理模組及載入資料](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[查看進程模組結果](view-process-module-results-in-advanced-ediscovery.md)

