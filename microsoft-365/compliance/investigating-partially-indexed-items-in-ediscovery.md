---
title: 調查 Office 365 電子文件探索中已局部編製索引的項目
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: 已局部編製索引的項目 （也呼叫未建立索引的項目） 是 Exchange 信箱項目和文件在 SharePoint 和 OneDrive 網站，如某個原因而未完全編製索引的內容搜尋。 在本文中了解為何無法編製索引的搜尋項目，並已局部編製索引的項目所傳回、 識別搜尋錯誤的已局部編製索引的項目，並使用 PowerShell 指令碼來判斷您的組織暴露於已局部編製索引的電子郵件項目。
ms.openlocfilehash: b67b7d5cfedd37315a9f8bc9027e03b820598846
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072339"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a>調查 Office 365 電子文件探索中已局部編製索引的項目

當您執行搜尋時，自動從安全性 & 合規性中心執行內容搜尋會包含已局部編製索引的項目預估的搜尋結果中。 已局部編製索引的項目是 Exchange 信箱項目和文件 SharePoint 和 OneDrive for Business 網站完全沒有編入搜尋索引，因任何原因。 大部分的電子郵件和網站的文件會成功索引，因為它們會落在[電子郵件訊息的編製索引限制](limits-for-content-search.md#indexing-limits-for-email-messages)內。 不過，某些項目可能會超過這些索引限制，而且會已局部編製索引。 以下是其他原因無法編製索引的搜尋項目，並已局部編製索引的項目時執行內容搜尋所傳回的原因：
  
- 電子郵件具有無法建立索引; 檔案類型的附加的檔案在大多數情況下，該檔案類型是[無法辨識或不支援索引編製功能](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)
    
- 電子郵件有附加的檔案沒有有效的處理常式，圖像檔案; 例如這是最常見原因的已局部編製索引的電子郵件項目
    
- 太多檔案附加到電子郵件
    
- 附加到電子郵件的檔案是太大
    
- 檔案類型支援索引編製，但是特定檔案發生索引錯誤
    
雖然可能會有所不同，大部分的 Office 365 組織客戶的內容低於 1%磁碟區，擁有的內容低於 12%的已局部編製索引的大小。 與大小的磁碟區之間的差異的原因是較大的檔案有較高的機率的含有不能完全索引的內容。
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>已局部編製索引的項目計數為何變更搜尋？

安全 & 與規範中心執行內容搜尋之後，總數和大小所搜尋的位置中的已局部編製索引項目列出中會顯示在搜尋的詳細統計資料中的搜尋結果統計資料。 請注意這些稱為搜尋統計資料中*未編製索引的項目*。 以下是會影響搜尋結果中傳回的已局部編製索引項目數目的一些事項： 
  
- 如果項目已局部編製索引，且符合搜尋查詢，它會包含在計數 （和大小） 的搜尋結果項目和已局部編製索引的項目。 不過，當匯出該相同結果，項目是搜尋的只包含在搜尋結果; 集它具有不包括為已局部編製索引的項目。
    
- 如果您指定日期範圍的搜尋查詢 （包括它的關鍵字查詢中） 或使用條件，不會比對的日期範圍的任何已局部編製索引項目不包含已局部編製索引的項目計數。 只有已局部編製索引項目的日期範圍內的隨附中已局部編製索引的項目計數。
    
 **附註：** 已局部編製索引項目位於 SharePoint 和 OneDrive 網站*不*包含在搜尋的詳細統計資料中顯示的已局部編製索引的項目估計值。 不過，當您匯出內容搜尋結果時，可以匯出已局部編製索引的項目。 例如，如果您只搜尋網站在內容搜尋的估計數量中已局部編製索引的項目將會是零。 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>計算已局部編製索引的項目在您的組織中的比率

若要了解您的組織暴露於已局部編製索引的項目，您可以執行所有內容搜尋所有信箱中 （藉由使用空白的關鍵字查詢）。 在下面的下列範例中，有 56,208 (4,830 MB) 完全編製索引項目和 470 (316 MB) 已局部編製索引的項目。
  
![範例搜尋統計資料顯示的已局部編製索引的項目](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
您可以使用下列計算判斷百分比的已局部編製索引的項目。
  
 **若要計算的比例的組織中的已局部編製索引項目：**

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
藉由使用上述範例中，從搜尋結果。 84%的所有信箱項目已局部編製索引。
  
 **若要計算您組織中已局部編製索引項目的大小的百分比：**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

因此在前一個範例中，6.54] %的信箱項目的總大小會從已局部編製索引的項目。 如先前所述，大多數的 Office 365 組織的客戶的內容低於 1%磁碟區，擁有的內容低於 12%的已局部編製索引的大小。

## <a name="working-with-partially-indexed-items"></a>使用已局部編製索引的項目

在情況下當您要檢查部分項目來驗證它們不包含的相關資訊，您可以[匯出內容搜尋報告](export-a-content-search-report.md)包含已局部編製索引項目的相關資訊。 當您匯出內容搜尋報告時，請務必選擇其中一個包含已局部編製索引的項目匯出選項。 
  
![選擇 [匯出已局部編製索引的項目第二個或第三個選項](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
當您匯出內容搜尋結果] 或 [內容搜尋報告使用其中一個選項時，匯出包含名為未編製索引的 Items.csv 報表。 此報告中包含大部分的 ResultsLog.csv 檔案; 相同的資訊不過，未編製索引的 Items.csv 檔案也包含兩個欄位相關的已局部編製索引的項目：**錯誤標記**與**Error 屬性**。 這些欄位包含每個已局部編製索引項目的索引錯誤的相關資訊。 使用這兩個欄位中的資訊可協助您判斷針對特定的索引時發生錯誤會影響您調查。 如果是的話，您可以執行已設定目標內容搜尋和擷取及匯出特定的電子郵件與 SharePoint 或 OneDrive 文件，以便您可以檢查它們，以判斷如果它們相關您調查。 如需逐步指示，請參閱[準備 Office 365 中已設定目標內容搜尋的 CSV 檔案](csv-file-for-an-id-list-content-search.md)。
  
 **附註：** 未編製索引的 Items.csv 檔案也會包含名為**錯誤類型**和**錯誤訊息**的欄位。 這些是舊版欄位中內含的**錯誤標記**和**Error 屬性**欄位中，但具有較少的詳細資訊的資訊類似的資訊。 您可以放心地忽略這些舊版的欄位。 
  
## <a name="errors-related-to-partially-indexed-items"></a>與已局部編製索引的項目相關的錯誤

錯誤標記所組成的資訊、 錯誤和檔案類型的兩個部分。 例如，在此錯誤/filetype 配對：

```text
 parseroutputsize_xls
```

   
 `parseroutputsize`錯誤和`xls`是在發生錯誤的檔案的檔案類型。 在情況下所無法辨識該檔案類型或檔案類型不帶不會套用到錯誤，您會看到值`noformat`取代之檔案類型。 
  
以下是錯誤和錯誤的可能原因的描述編製索引的清單。
  
|**錯誤標記**|**描述**|
|:-----|:-----|
| `attachmentcount` <br/> |電子郵件有太多的附件，以及這些附件的一些未處理。  <br/> |
| `attachmentdepth` <br/> |內容的擷取器和文件剖析器找不到太多層級的巢狀方式置於其他附件的附件。 這些附件的一些不處理。  <br/> |
| `attachmentrms` <br/> |附件失敗解碼所以 RMS 保護。  <br/> |
| `attachmentsize` <br/> |附加到電子郵件的檔案太大，且無法處理。  <br/> |
| `indexingtruncated` <br/> |當索引寫入已處理的電子郵件訊息，其中一個索引的屬性太大，而且已被截斷。 截斷的屬性會列在 Error 屬性] 欄位。  <br/> |
| `invalidunicode` <br/> |電子郵件訊息包含無法處理為有效的 Unicode 的文字。 此項目編製索引可能不完整。  <br/> |
| `parserencrypted` <br/> |加密附件或電子郵件訊息的內容，以及 Office 365 無法解碼內容。  <br/> |
| `parsererror` <br/> |分析處理時發生未知的錯誤。 這通常會造成從軟體錯誤或服務當機。  <br/> |
| `parserinputsize` <br/> |附件是太大，剖析器處理，且該附件的剖析未發生的事件或未完成。  <br/> |
| `parsermalformed` <br/> |附件格式不正確，且無法剖析器處理。 這項結果從可以舊檔案格式，藉由不相容的軟體或有病毒假冒某個項目比其他宣告所建立的檔案。  <br/> |
| `parseroutputsize` <br/> |附件的剖析的輸出是太大，且必須截斷。  <br/> |
| `parserunknowntype` <br/> |附件具有 Office 365 無法偵測到的檔案類型。  <br/> |
| `parserunsupportedtype` <br/> |附件具有 Office 365could 偵測，但剖析該檔案類型不支援的檔案類型。  <br/> |
| `propertytoobig` <br/> |電子郵件屬性的值在 Exchange 儲存區已太大而無法擷取，並將無法處理的訊息。 這通常只是電子郵件訊息的本文屬性。  <br/> |
| `retrieverrms` <br/> |內容的擷取器無法解碼受 RMS 保護的郵件。  <br/> |
| `wordbreakertruncated` <br/> |太多文字已編製索引期間識別文件中。 當達到此限制時，停止處理屬性的屬性就會被截斷。  <br/> |
   
錯誤欄位描述哪些欄位受到錯誤標記] 欄位中列出的處理錯誤。 如果您搜尋屬性，例如：`subject`或`participants`，錯誤訊息的內文中不會影響您的搜尋結果。 決定完全哪些您可能需要進一步調查的已局部編製索引項目時，這可以是很有用。
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>使用 PowerShell 指令碼來判斷您的組織暴露於已局部編製索引的電子郵件項目

下列步驟顯示如何執行 PowerShell 指令碼，搜尋所有項目中所有 Exchange 信箱，然後產生報告相關的已局部編製索引的電子郵件項目貴組織的比率，（依計數，以及由大小） 並顯示的項目數 （和其檔案類型） 的每個索引所發生的錯誤。 使用在前一節中的錯誤標記描述，來識別索引時發生錯誤。
  
1. 使用.ps1 檔名尾碼，將下列文字儲存至 Windows PowerShell 指令碼檔案例如， `PartiallyIndexedItems.ps1`。

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
    
3. 在安全性 & 合規性中心 PowerShell，移至您在步驟 1，儲存指令碼的所在資料夾，然後執行指令碼。例如：

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

以下是範例的指令碼所傳回的輸出。
  
![輸出會產生報告，以在您的組織暴露於已局部編製索引的電子郵件項目上的指令碼範例](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
注意下列事項：
  
1. 總數和大小的電子郵件項目，貴組織的比率的已局部編製索引的電子郵件項目 （依計數，以及由大小）
    
2. 清單錯誤標記與之對應的檔案類型，發生錯誤。
  
## <a name="see-also"></a>請參閱

[位於 Office 365 中內容搜尋的已局部編製索引項目](partially-indexed-items-in-content-search.md)
