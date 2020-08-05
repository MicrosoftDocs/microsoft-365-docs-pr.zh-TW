---
title: 系統管理中心的 Microsoft 365 報告-Business 使用 OneDrive
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 0de3b312-c4e8-4e4b-a02d-32b2f726a680
description: '取得商務使用狀況報告的 OneDrive，以瞭解整個組織所使用的檔案和儲存總數。 '
ms.openlocfilehash: 33c319961adc02ba5b8c937bd14626461bbb7200
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560396"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>系統管理中心的 Microsoft 365 報告-Business 使用 OneDrive

Microsoft 365**報告**儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。
  
例如，根據檔案的總數與貴組織已使用的儲存空間，儀表板上的 [OneDrive] 卡片可以提供您來自商務用 OneDrive 的高層級檢視。您可以進行深入分析，以了解作用中 OneDrive 帳戶的趨勢、使用者正在與多少個檔案進行互動，以及已使用的儲存空間。也會提供您每個使用者的 OneDrive 詳細資料。
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。  
 
## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>如何進入 OneDrive 使用狀況報告？

1. 在系統管理中心中，移至 [**報表** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用量</a>]。

    
2. 從 [**選取報告**] 下拉式清單中，選取 [ **OneDrive** \> **使用狀況**]。 
  
## <a name="interpret-the-onedrive-usage-report"></a>解讀 OneDrive 使用狀況報告

您可以查看「**帳戶**」、「檔案」及「**儲存**」**視圖，以**查看商務使用 OneDrive。 
  
![OneDrive Usage Report](../../media/49c5b93b-d081-436e-8992-236343a6d46b.png)
  
|||
|:-----|:-----|
|1.  <br/> |**OneDrive 使用狀況**報告會顯示過去7天、30天、90天或180天的趨勢。 不過，如果您在報告中選取某一天，則 table (7) 會從目前的日期顯示最多28天的資料， (不是) 產生報表的日期。  <br/> |
|2.  <br/> |每個報告中的資料通常會涵蓋過去24到48小時。 <br/>|
|3.  <br/> |[**帳戶**] 視圖會以總數和作用中 OneDrive 帳戶的數目來顯示趨勢。 「使用中的帳戶」指的是使用者用來檢視、修改、上傳、下載、共用或同步處理檔案的帳戶。  <br/> |
|4.  <br/> |[檔案] 視圖會**顯示檔總數**和使用中的檔案數目。 若檔已儲存、同步處理、修改或共用于特定時段內，則會視為作用中的檔案。  <br/> 附注：一個檔案的檔案活動可能會發生多次，但是只會算作一個作用中的檔案。 例如，您可能會在指定時間週期中多次儲存並同步處理同一個檔案，但在資料中它都只會計算為一個使用中的檔案和一個同步處理的檔案。           |
|5.  <br/> |[**儲存區**] 視圖會以您所使用的 OneDrive 儲存量來顯示趨勢。 如果您想要檢查儲存量限制，請參閱[檢查使用者是否有預設儲存量限制或特定限制](https://docs.microsoft.com/onedrive/set-default-storage-space#check-if-a-user-has-the-default-storage-limit-or-a-specific-limit)。  <br/> 附注：此大小包含任何與檔案相關聯的版本和中繼資料。           |
|6.  <br/> | 在 [**帳戶**] 圖表上，Y 軸是 OneDrive 帳戶的數目。  <br/>  **在 [檔案**] 圖表上，Y 軸是儲存在 OneDrive 中的檔數。  <br/>  在 [**儲存空間**] 圖表上，Y 軸是所用 OneDrive 儲存量的數量。  <br/>  所有圖表中的 X 軸都代表此特定報告的所選日期範圍。  <br/> |
|7.  <br/> |您可以選取圖例中的專案，以篩選您在圖表上看到的數列。 例如，**在 [檔案**] 圖表上，選取 [**檔總數** **] 或 [使用中檔案**]。 在 [**帳戶**] 圖表上，選取 [**總帳戶**] 或 [使用中**帳戶**]。 或是在 [**儲存空間**] 圖表上，選取 [**使用的儲存空間**]。 變更選取項目並不會變更表格中的資訊。  <br/> |
|8.  <br/> | 表格顯示每位使用者的 OneDrive資料明細。若要在表格中顯示，使用者必須獲得包含 OneDrive 的產品授權，而且必須開啟 SharePoint Online。使用者還必須登入 OneDrive 同步處理用戶端，或使用網頁瀏覽器瀏覽至其 OneDrive。  <br/>  如果 OneDrive 中有檔案活動，表格會顯示最近一次執行檔案活動的日期。 表格中的列是依**上一個活動日期**排序的，因此，最新檔案活動的 OneDrive 會出現在清單的頂端。  <br/>  您可以新增或移除表格中的欄位。  <br/> ![欄選項](../../media/onedriveusage-columns.png)  <br/> **URL**是使用者 OneDrive 的網頁位址。  <br/> 「**已刪除**」是 OneDrive 的刪除狀態。 帳戶至少要 7 天才會標示為已刪除。  <br/> **擁有**者是 OneDrive 主要系統管理員的使用者名稱。  <br/> **擁有者主要名稱**是 OneDrive 擁有者的電子郵件地址。  <br/> **上次活動日期 (UTC) **是在 OneDrive 中執行檔案活動的最晚日期。 如果 OneDrive 最近沒有檔案活動，值將會是空白。  <br/> **Files**是 OneDrive 中的檔數。  <br/> [使用中檔案 **] 是指**一段時間內的作用中檔案數目。<br/> 附注：如果在報告的指定期間內已移除檔案，則報告中顯示的使用中檔案數目可能會大於目前 OneDrive 中的檔案數目。 刪除的使用者會在報告中持續顯示180天。<br/>**使用的儲存體 (mb) **是指 OneDrive 使用的儲存量（以 MB 為單位）。 <br/>  如果您組織的原則使您無法查看使用者資訊可辨識的報告，您可以變更所有這些報告的隱私權設定。 請參閱[Microsoft 365 系統管理中心的活動報告中](activity-reports.md)的 [**我要如何隱藏使用者層級詳細資料？** ] 區段。  <br/> |
|9.  <br/> |選取 [**管理欄**] 圖示 ![ 管理欄 ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) ，以新增或移除報告中的欄。  <br/> |
|10.  <br/> |您也可以選取 [**匯出**] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出每個 OneDrive 的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的 OneDrive 帳戶少於 2000 個，可以直接在報告中的表格上進行排序和篩選。 如果您的 OneDrive多於 2000 個，則需要匯出資料才能進行篩選和排序。  <br/> 附注：將資料匯出至 Excel 檔案時，產生內容報告的日期會反映在 [**資料**] 欄位中的檔案。  <br/> |
|||
   
