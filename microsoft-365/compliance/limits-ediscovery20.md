---
title: 進階電子文件探索限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解 Microsoft 365 中的高級 eDiscovery 解決方案的大小寫限制、索引限制和搜尋限制。
ms.openlocfilehash: c139480f18e0e6d94aae5a38d5fd636fbc62b2dc
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358471"
---
# <a name="limits-in-advanced-ediscovery"></a>進階電子文件探索的限制

本文說明 Microsoft 365 中的高級 eDiscovery 解決方案的限制。

## <a name="case-and-review-set-limits"></a>案例與複查集限制

下表列出高級 eDiscovery 中案例和審閱集的限制。

|**限制的描述**|**限制**|
|:-----|:-----|
|在案例) 中，所有審閱集可以新增到案例中的檔總數目 (。  <br/> |3 百萬 <br/> |
|每個負載集的檔案大小總計。 這包括將非 Office 365 載入至審閱集。  <br/> |300 GB <br/> |
|每天組織中的所有審閱集合中載入的資料總量。<br/> |2 TB <br/> |
|每個案例的載入集數目上限。  <br/> |200 <br/> |
|每個案例的審閱集數目上限。  <br/> |共 <br/> |
|||

## <a name="indexing-limits"></a>索引限制

下表列出高級 eDiscovery 中的索引限制。

|**限制的描述**|**限制**|
  |:-----|:-----|
  |從單一檔案解壓縮的字元數上限。  <br/> |10000000<sup>1</sup> <br/> |
  |單一檔案的大小上限。   <br/> |100 MB<sup>1</sup> <br/> |
  |檔中內嵌專案的最大深度。  <br/> |25<sup>1</sup> <br/> |
  |光學字元辨識 (OCR) 所處理的檔案大小上限。  <br/> |24 MB<sup>1</sup> <br/> |  
|||

## <a name="search-limits"></a>搜尋限制

本節所述的限制與使用 [ **搜尋** ] 索引標籤上的 [搜尋] 工具收集案例的資料有關。 如需詳細資訊，請參閱 [在高級 eDiscovery 中收集案例的資料](collecting-data-for-ediscovery.md)。

|**限制的描述**|**限制**|
|:-----|:-----|
|可在單一搜尋中搜尋的信箱或網站數目上限。  <br/> |無限制  <br/> |
|可以同時執行的搜尋數目上限。  <br/> |無限制  <br/> | 
|單一使用者可以同時開始的搜尋數目上限。  <br/> |10   <br/> | 
|搜尋查詢 (包含運算子和條件) 的最大字元數。  <br/> |**信箱**：10000<br/>**網站**：4000搜尋所有網站或2000時搜尋最多20個網站時 <sup>2</sup> <br/> |
|首碼萬用字元的最小字母字元數目;例如**一個 \* **或**設定 \* **。 <br/> |3   <br/> |  
|使用首碼萬用字元來搜尋確切的字詞，或是使用前置詞萬用字元及 **接近** 的布林運算子時，所傳回的最大變種。  <br/> |10000 <sup>3</sup> <br/> |
|搜尋的預覽頁面上顯示的每個使用者信箱的專案數上限。 隨即顯示最新的專案。   <br/> |100  <br/> |
|搜尋時，預覽頁面上顯示的所有信箱中的專案數上限。  <br/> |1,000  <br/> |
|可針對搜尋結果預覽的信箱數目上限。  如果有超過1000個信箱包含符合搜尋查詢的專案，則預覽中只會提供最多結果的前1000個信箱。<br/> |1,000  <br/> |
|在 [預覽] 頁面上，針對搜尋顯示之商務網站 SharePoint 和 OneDrive 的專案數上限。 隨即顯示最新的專案。  <br/> |200  <br/> |
|可用於預覽搜尋結果的商務網站 SharePoint 和 OneDrive 數目上限。 如果有超過200個網站包含符合搜尋查詢的專案，則預覽中只會提供最多結果的前200網站。  <br/> |200  <br/> |
|搜尋時預覽頁面上顯示的每個公用資料夾信箱的專案數上限。  <br/> |100  <br/> |
|在 [預覽] 頁面上顯示的所有公用資料夾信箱專案中找到的專案數上限。  <br/> |200  <br/> |
|可預覽搜尋結果的公用資料夾信箱數目上限。 如果有超過500的公用資料夾信箱包含符合搜尋查詢的專案，則預覽中只可使用具有最多結果的前500個信箱。  <br/> |500  <br/> |
|||

## <a name="viewer-limits"></a>檢視器限制

|**限制的描述**|**限制**|
  |:-----|:-----|
  |可在原生檢視器中查看的 Excel 檔案大小上限。  <br/> |4 MB  <br/> |
|||

## <a name="review-set-download-limits"></a>複查設定的下載限制

|**限制的描述**|**限制**|
|:-----|:-----|
|從審閱集下載的檔總大小或檔數目上限。  <br/> |3 MB 或50檔 <sup>4</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> 任何超出單一檔限制的專案會顯示為處理錯誤。<br/>
> <sup>2</sup> 搜尋商務位置的 SharePoint 和 OneDrive 時，所搜尋之網站 URLs 中的字元會因此限制而計數。<br/>
> <sup>3</sup> ：非片語查詢 (關鍵字值，但不使用雙引號) 我們使用特殊的前置詞索引。 這會告訴我們檔中的字詞，但不會出現在檔中。 若要執行片語查詢 (關鍵字值使用雙引號) ，我們需要比較檔內的字詞中的文字的位置。 這表示我們無法使用關鍵字查詢的首碼索引。 在此情況下，我們會以內部首碼擴充的任何可能的字來內部展開查詢;例如， **time \* **可以展開為 **"time 或 timer OR time 或 timex or timeboxed or ..."**。 10000的限制是 word 可以擴充的變種數目上限，而不是符合查詢的檔數目上限。 非片語字詞沒有上限。<br/>
> <sup>4</sup> 此限制適用于從審閱集下載選取的檔。 它不會套用到從審閱集匯出檔。 如需下載及匯出檔的詳細資訊，請參閱 [在高級 eDiscovery 中匯出案例資料](exporting-data-ediscover20.md)。 <br/>

