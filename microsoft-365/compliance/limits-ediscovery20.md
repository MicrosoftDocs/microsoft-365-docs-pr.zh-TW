---
title: 進階電子文件探索限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解 Microsoft 365 中 Advanced eDiscovery 解決方案的實際案例限制、索引限制和搜尋限制。
ms.openlocfilehash: 335e40c6918fc33acc12082546b98f28c319c814
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244573"
---
# <a name="limits-in-advanced-ediscovery"></a>進階電子文件探索的限制

本文說明 Microsoft 365 中 Advanced eDiscovery 解決方案的限制。

## <a name="case-and-review-set-limits"></a>案例與複查集限制

下表列出 Advanced eDiscovery 中案例和審閱集的限制。

| 限制的描述 | 限制 |
|:-----|:-----|
|在案例) 中，所有審閱集可以新增到案例中的檔總數目 (。  <br/> |3 百萬 <br/> |
|每個負載集的檔案大小總計。 這包括將非 Office 365 載入至審閱集。  <br/> |300 GB <br/> |
|每天組織中的所有審閱集合中載入的資料總量。<br/> |2 TB <br/> |
|每個案例的負載集數目上限。  <br/> |200 <br/> |
|每個案例的審閱集數目上限。  <br/> |共 <br/> |
|每個案例的標記群組數目上限。  <br/> |1000 <br/> |
|每個案例的標記數目上限。  <br/> |1000 <br/> |
|您的組織中可將內容新增至審閱集的最大並行工作。 這些工作稱為 **將資料新增至審閱集** ，並顯示在 [ **工作** ] 索引標籤的案例中。| 10 <sup>4</sup> |
|將內容新增至每位使用者之審閱集的最大並行工作。 這些工作稱為 **將資料新增至審閱集** ，並顯示在 [ **工作** ] 索引標籤的案例中。 | 個 |
|||

## <a name="hold-limits"></a>保留限制

下表列出與 Advanced eDiscovery 案例相關聯的保留限制。

| 限制的描述 | 限制 |
|:-----|:-----|
|單一案例保留中的信箱數目上限。 此限制包括使用者信箱的組合總數，以及與 Microsoft 365 群組、Microsoft Teams 及 Yammer 群組相關聯的信箱。 <br/> |1,000  <br/> |
|單一案例保留中的網站數目上限。 此限制包括與 Microsoft 365 群組、Microsoft Teams 及 Yammer 群組相關聯的商務用 OneDrive 網站、SharePoint 網站和網站的綜合總數。  <br/> |100  <br/> |

## <a name="indexing-limits"></a>索引限制

下表列出 Advanced eDiscovery 中的索引限制。

| 限制的描述 | 限制 |
|:-----|:-----|
|從單一檔案解壓縮的字元數上限。  <br/> |10000000<sup>1</sup> <br/> |
|單一檔案的大小上限。   <br/> |100 MB<sup>1</sup> <br/> |
|檔中內嵌專案的最大深度。  <br/> |25<sup>1</sup> <br/> |
|光學字元辨識 (OCR) 所處理的檔案大小上限。  <br/> |24 MB<sup>1</sup> <br/> 
|每天每個組織的索引工作數目上限。 <br/> |10<sup>6</sup> <br/>|  
|||

## <a name="search-limits"></a>搜尋限制

本節所述的限制與使用 [ **搜尋** ] 索引標籤上的 [搜尋] 工具收集案例的資料有關。 如需詳細資訊，請參閱[在 Advanced eDiscovery 中收集案例的資料](collecting-data-for-ediscovery.md)。

| 限制的描述 | 限制 |
|:-----|:-----|
|可在單一搜尋中搜尋的信箱或網站數目上限。 |無限制|
|可以同時執行的搜尋數目上限。 |無限制 |
|單一使用者可以同時開始的搜尋數目上限。 |10  | 
|搜尋查詢 (包含運算子和條件) 的最大字元數。 |10000 &nbsp; <sup>2</sup>|
|SharePoint 和商務用 OneDrive 網站的搜尋查詢的最大字元數 (包括運算子和條件) 。 |10,000<br>4000，使用萬用字元 &nbsp; <sup>2</sup>|
|首碼萬用字元的最小字母字元數目;例如，**一個 \* *_ 或 _* 集 \***。|個 |  
|使用首碼萬用字元來搜尋確切的字詞，或是使用前置詞萬用字元及 **接近** 的布林運算子時，所傳回的最大變種。 |10000 &nbsp; <sup>3</sup>|
|搜尋的預覽頁面上顯示的每個使用者信箱的專案數上限。 隨即顯示最新的專案。 |100|
|搜尋時，預覽頁面上顯示的所有信箱中的專案數上限。|1,000|
|可針對搜尋結果預覽的信箱數目上限。  如果有超過1000個信箱包含符合搜尋查詢的專案，則預覽中只會提供最多結果的前1000個信箱。|1,000|
|在 [預覽] 頁面上搜尋的 SharePoint 和商務用 OneDrive 網站中顯示的專案數上限。 隨即顯示最新的專案。 |200|
|可預覽搜尋結果的 SharePoint 和商務用 OneDrive 網站數目上限。 如果有超過200個網站包含符合搜尋查詢的專案，則預覽中只會提供最多結果的前200網站。|200|
|搜尋時預覽頁面上顯示的每個公用資料夾信箱的專案數上限。 |100|
|在 [預覽] 頁面上顯示的所有公用資料夾信箱專案中找到的專案數上限。 |200|
|可預覽搜尋結果的公用資料夾信箱數目上限。 如果有超過500的公用資料夾信箱包含符合搜尋查詢的專案，則預覽中只可使用具有最多結果的前500個信箱。|500|
|||

## <a name="search-times"></a>搜尋時間

Microsoft 會收集所有組織執行之搜尋的效能資訊。 雖然搜尋查詢的複雜性可能會影響搜尋時間，會影響搜尋所需時間的最大因素是搜尋的信箱數量。 雖然 Microsoft 不會提供搜尋時間的服務等級協定，但下表會根據搜尋中包含的信箱數目，列出收集搜尋的平均搜尋時間。
  
  | 信箱數目 | 平均搜尋時間 |
  |:-----|:-----|
  |100  <br/> |30 秒  <br/> |
  |1,000  <br/> |45 秒  <br/> |
  |10,000  <br/> |4 分鐘  <br/> |
  |25,000  <br/> |10 分鐘  <br/> |
  |50,000  <br/> |20 分鐘  <br/> |
  |100,000  <br/> |25 分鐘  <br/> |
  |||

## <a name="viewer-limits"></a>檢視器限制

| 限制的描述 | 限制 |
|:-----|:-----|
|可在原生檢視器中查看的 Excel 檔案大小上限。  <br/> |4 MB  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a>匯出限制-最終匯出缺考核集

本節所述的限制與從審閱集匯出檔相關。

| 限制的描述 | 限制 |
|:-----|:-----|
|單一匯出的大小上限。|5000000檔或 500 GB （以較少者為准）|
|每個審閱集的併發匯出上限。 | 1 |
|||

## <a name="review-set-download-limits"></a>複查設定的下載限制

| 限制的描述 | 限制 |
|:-----|:-----|
|從審閱集下載的檔總大小或檔數目上限。  <br/> |3 MB 或50檔 <sup>5</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> 任何超出單一檔限制的專案會顯示為處理錯誤。
>
> <sup>2</sup>搜尋 SharePoint 和商務用 OneDrive 位置時，搜尋的網站 URLs 中的字元會根據此限制計算。 字元總數包括：<br>
> - [使用者] 和 [篩選] 欄位中的所有字元。
> - 適用于使用者的所有搜尋許可權篩選。
> - 搜尋中任何位置屬性的字元;這包括 ExchangeLocation、PublicFolderLocation、SharPointLocation、ExchangeLocationExclusion、PublicFolderLocationExclusion、SharePointLocationExclusion、OneDriveLocationExclusion。
>   例如，包含搜尋中的所有 SharePoint 網站和 OneDrive 帳戶會算作六個字元，因為會同時顯示 SharePointLocation 和 OneDriveLocation 欄位的 "all" 一詞。
>
> <sup>3</sup> ：非片語查詢 (關鍵字值，但不使用雙引號) 我們使用特殊的前置詞索引。 這會告訴我們檔中的字詞，但不會出現在檔中。 若要執行片語查詢 (關鍵字值使用雙引號) ，我們需要比較檔內的字詞中的文字的位置。 這表示我們無法使用關鍵字查詢的首碼索引。 在此情況下，我們會以內部首碼擴充的任何可能的字來內部展開查詢;例如， **time \* *_ 可以展開為 _*"time 或 timer OR time 或 timex or timeboxed or ..."**。 10000的限制是 word 可以擴充的變種數目上限，而不是符合查詢的檔數目上限。 非片語字詞沒有上限。
>
> <sup>4</sup> 在其他 eDiscovery 工具中匯出內容時，會共用此限制。 這表示內容搜尋與核心 eDiscovery (中的併發匯出及新增內容至 Advanced eDiscovery) 中的審閱集，都是針對此限制套用。
>
> <sup>5</sup> 此限制適用于從審閱集下載選取的檔。 它不會套用到從審閱集匯出檔。 如需下載及匯出檔的詳細資訊，請參閱[Export case data in Advanced eDiscovery](exporting-data-ediscover20.md)。
>
> 每個組織每天有<sup>6</sup>個索引限制。 例如，您可以在案例中的 [ **資料來源** ] 索引標籤上選取多個保管人，然後按一下 [ **更新索引** ]，避免為每個保管人建立個別的索引工作。 
