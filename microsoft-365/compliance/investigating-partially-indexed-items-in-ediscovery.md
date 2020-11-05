---
title: 調查 eDiscovery 中已部分索引的專案
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何在組織內管理 Exchange、SharePoint 和 OneDrive 中部分索引的 (或未編制索引的) 專案。
ms.openlocfilehash: bbf234e2051cd103d1b99ab75b8e5c15365762a9
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919995"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a>調查 eDiscovery 中已部分索引的專案

當您執行搜尋時，您從 Microsoft 365 規範中心執行的 eDiscovery 搜尋會自動包含在預估搜尋結果中已部分索引的專案。 已部分編制索引的專案是 Exchange 信箱專案和檔，其上的 SharePoint 和 OneDrive 出於某些原因尚未完全編制搜尋索引的商務網站。 大部分電子郵件訊息和網站檔都已成功編制索引，因為它們在電子郵件的 [索引限制](limits-for-content-search.md#indexing-limits-for-email-messages)內。 不過，有些專案可能會超出這些索引限制，而且會進行部分編制索引。 以下是在執行 eDiscovery 搜尋時，無法將專案編制索引以進行搜尋的其他原因，而且會傳回成部分索引項目目：
  
- 電子郵件的附加檔案沒有有效的處理常式，例如映射檔;這是部分索引電子郵件專案最常見的原因

- 附加到電子郵件的檔案太多

- 附加到電子郵件的檔案太大

- 檔案類型支援索引編制，但特定檔案發生索引錯誤

雖然這種方式不同，但大多陣列織客戶的內容少於磁片容量的1%，而不是以部分索引的大小小於12% 的內容。 磁片區與大小之間差異的原因是，較大的檔案包含無法完全編制索引之內容的可能性較高。
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>為何搜尋的部分索引項目目計數變更？

在您執行 eDiscovery 搜尋之後，搜尋位置中已部分索引項目目的總數和大小會列在搜尋結果統計資料中，顯示在搜尋的詳細統計資料中。 請注意，這些是在搜尋統計資料中稱為未  *編制索引的專案*  。 以下是會影響搜尋結果中傳回的部分索引項目目數目的一些事項：
  
- 如果專案已部分編制索引，且符合搜尋查詢，則會同時包含搜尋結果專案的計數 (和) 大小，以及部分編制索引的專案。 不過，當匯出相同搜尋的結果時，此專案會包含在一組搜尋結果中;它不會包含在部分索引項目目中。

- 如果您指定搜尋查詢 (的日期範圍，方法是將它納入關鍵字查詢或使用條件) 中，任何不符合日期範圍的部分索引項目目都不會包含在部分編制索引的專案計數中。 只有位於日期範圍內的部分索引項目目會包含在部分索引項目目的計數中。

> [!NOTE]
> 位於 SharePoint 和 OneDrive 網站中的部分索引項目目 *不會* 包含在搜尋的詳細統計資料中顯示的部分索引項目目估計內。 不過，當您匯出 eDiscovery 搜尋的結果時，可以匯出部分索引的專案。 例如，如果您只有搜尋網站，估計數目的部分索引項目目會是零。
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>計算組織中已部分索引的專案比率

若要瞭解組織在部分索引項目目中的危險性，您可以使用空白的關鍵字查詢) ，在所有信箱中執行所有內容的搜尋 (。 在下列範例中，有 56208 (4830 MB) 完整編制索引的專案，以及 470 (316 MB) 部分索引的專案。
  
![顯示部分索引項目目之搜尋統計資料的範例](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
您可以使用下列計算來判斷部分索引項目目的百分比。
  
 **若要計算組織中已部分索引的專案比率：**

`(Total number of partially indexed items/Total number of items) x 100`

`(470/56,208) x 100 = 0.84%`

使用上述範例中的搜尋結果，就會以部分索引的方式列出所有信箱專案的84%。
  
 **若要計算組織中部分索引項目目大小的百分比：**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

在上一個範例中，信箱專案總大小的6.54% 是從部分索引的專案。 如先前所述，大多陣列織客戶的內容少於1% 的內容，而不是以部分索引的大小小於12% 的內容。

## <a name="working-with-partially-indexed-items"></a>使用部分編制索引的專案

在需要檢查部分專案以驗證它們不包含相關資訊的情況下，您可以匯出包含部分索引項目目相關資訊的 [內容搜尋報告](export-a-content-search-report.md) 。 當您匯出內容搜尋報告時，請務必選擇其中一個包含部分索引項目目的匯出選項。
  
![選擇第二個或第三個選項，匯出已部分索引的專案](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
當您使用其中一個選項匯出 eDiscovery 搜尋結果或搜尋報告時，匯出會包含一個名為「未編制索引」 Items.csv 的報表。 這個報告包含的資訊大部分與 ResultsLog.csv 檔案相同;不過，未編制索引的 Items.csv 檔案中也包含與部分索引項目目相關的兩個欄位： **錯誤標記** 和 **錯誤屬性** 。 這些欄位包含每個部分索引項目目之索引錯誤的相關資訊。 使用這兩個欄位中的資訊可協助您判斷是否有特定影響調查的索引錯誤。 如果是的話，您可以執行目標搜尋，並取得及匯出特定的電子郵件訊息，並 SharePoint 或 OneDrive 檔，以便進行檢查，以判斷是否與您的調查相關。 如需逐步指示，請參閱 [Prepare a CSV file for a 目標 search In Office 365](csv-file-for-an-id-list-content-search.md)。

> [!NOTE]
> 未編制索引的 Items.csv 檔案也包含名為「 **錯誤類型** 」和「 **錯誤訊息** 」的欄位。 這些是舊版欄位，包含類似于 [ **錯誤標記** ] 和 [ **錯誤屬性** ] 欄位中的資訊，但詳細資訊更少的資訊。 您可以放心忽略這些舊版欄位。
  
## <a name="errors-related-to-partially-indexed-items"></a>與部分索引項目目相關的錯誤

錯誤標記是由兩部分資訊組成，錯誤和檔案類型。 例如，在此錯誤/類型的對中：

```text
 parseroutputsize_xls
```

 `parseroutputsize` 為錯誤， `xls` 是發生錯誤之檔案的檔案類型。 在此情況下，無法辨識檔案類型或檔案類型未套用至錯誤，您會看到 [！注意事項] 此值會顯示 `noformat` 在 [檔案類型] 的位置。
  
下列是索引錯誤的清單，以及錯誤可能原因的描述。
  
|**錯誤標記**|**描述**|
|:-----|:-----|
| `attachmentcount` <br/> |電子郵件中有太多附件，但未處理某些附件。  <br/> |
| `attachmentdepth` <br/> |內容檢索程式和檔剖析器發現嵌套在其他附件中的附件太多層級。 部分附件未處理。  <br/> |
| `attachmentrms` <br/> |因為郵件是受 RMS 保護，所以附件的解碼失敗。  <br/> |
| `attachmentsize` <br/> |附加到電子郵件的檔案太大，無法處理。  <br/> |
| `indexingtruncated` <br/> |當寫入已處理的電子郵件給索引時，其中一個可編制索引的屬性太大，已被截斷。 截斷的屬性會列在 [錯誤屬性] 欄位中。  <br/> |
| `invalidunicode` <br/> |電子郵件包含無法當作有效的 Unicode 處理的文字。 此專案的索引可能不完整。  <br/> |
| `parserencrypted` <br/> |附件或電子郵件訊息的內容已加密，但 Microsoft 365 無法解碼內容。  <br/> |
| `parsererror` <br/> |剖析時發生未知的錯誤。 這通常是軟體錯誤或服務損毀的結果。  <br/> |
| `parserinputsize` <br/> |附件太大，分析器無法處理，且該附件的分析並未發生或未完成。  <br/> |
| `parsermalformed` <br/> |附件格式不正確，無法由分析程式處理。 這是因為舊的檔案格式、由不相容的軟體所建立的檔案，或假裝為非所聲稱之專案的結果。  <br/> |
| `parseroutputsize` <br/> |對附件剖析的輸出過大，必須加以截斷。  <br/> |
| `parserunknowntype` <br/> |附件的檔案類型無法偵測到 Microsoft 365。  <br/> |
| `parserunsupportedtype` <br/> |附件的檔案類型，Office 365 可以偵測，但不支援分析該檔案類型。  <br/> |
| `propertytoobig` <br/> |Exchange 存放區中的電子郵件屬性值過大，無法進行找回，無法處理郵件。 這通常只會在電子郵件的 body 屬性時發生。  <br/> |
| `retrieverrms` <br/> |內容檢索程式無法解碼受 RMS 保護的郵件。  <br/> |
| `wordbreakertruncated` <br/> |在編制索引期間檔中識別過多的字。 當達到此限制時，處理屬性已停止，而且會截斷屬性。  <br/> |

[錯誤] 欄位描述 [錯誤標記] 欄位中所列的處理錯誤所影響的欄位。 如果您正在搜尋諸如或的屬性  `subject`  `participants` ，則郵件本文中的錯誤不會影響搜尋的結果。 這對判斷可能需要進一步調查的部分索引項目目是很有用的。
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>使用 PowerShell 腳本，判斷組織的部分索引電子郵件專案的危險性

下列步驟將示範如何執行 PowerShell 腳本，以搜尋所有 Exchange 信箱中的所有專案，然後產生有關組織的部分索引電子郵件專案 (依計數和) 大小之比例的報告，並顯示每個索引錯誤的專案 (及其檔案類型) 的數目。 使用上一節中的錯誤標記描述來識別索引錯誤。
  
1. 使用檔案名尾碼（ps1）將下列文字儲存至 Windows PowerShell 腳本檔案中;例如， `PartiallyIndexedItems.ps1` 。

```powershell
  write-host "**************************************************"
  write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
```

2. [連線到安全性與合規性中心 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084)。

3. 在 [安全性 & 規範中心] PowerShell 中，移至您在步驟1中用來儲存腳本的資料夾，然後執行腳本;例如：

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

以下是腳本傳回的輸出範例。
  
![從腳本輸出的範例，產生您組織對部分索引電子郵件專案的公開報告](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
注意下列事項：
  
1. 電子郵件專案的總數和大小，以及您組織的部分索引電子郵件專案 (依計數和大小的比例) 

2. 清單錯誤標記，以及發生錯誤的對應檔案類型。
  
## <a name="see-also"></a>另請參閱

[EDiscovery 中已部分索引的專案](partially-indexed-items-in-content-search.md)
