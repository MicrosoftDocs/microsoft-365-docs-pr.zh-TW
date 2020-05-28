---
title: Admin center 中的 Microsoft 365 報告-Business activity OneDrive
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
ms.assetid: 8bbe4bf8-221b-46d6-99a5-2fb3c8ef9353
description: 取得組織的 OneDrive 使用方式報告，並瞭解每個 OneDrive 使用者的活動、共用的檔案數目及儲存使用量。
ms.openlocfilehash: 9de2260049d901b401bd62a9e4d05191222b97a3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387534"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Admin center 中的 Microsoft 365 報告-Business activity OneDrive

Microsoft 365**報告**儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報告，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。
  
例如，您可以查看每位授權使用 OneDrive 的使用者與 OneDrive 上檔案的互動，以了解活動。也可以查看共用的檔案數量，協助您了解共同作業的程度。
  
> [!NOTE]
> 部分功能會逐步提供。這表示您可能還不會看到此功能，或看起來可能與說明文章中描述的不一樣。不過別擔心，新功能很快就會開放！ 
  
如果要了解每個 OneDrive 帳戶的活動量及儲存空間使用情形，可以檢視 [OneDrive 使用情況報告](onedrive-for-business-usage.md)。
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>如何進入 OneDrive 活動報告？

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取報告**] 下拉式清單中，選取 [ **OneDrive** \> **活動**]。
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>解讀商務用 OneDrive 活動報告

您可以透過查看 [檔案] 和 [**使用者**]**視圖，取得**商務活動 OneDrive。 
  
![OneDrive Activity Report](../../media/316b2a03-8e42-447c-aae8-080813eebe84.png)
  
|||
|:-----|:-----|
|1.  <br/> |您可以針對過去7天、30天、90天或180天的趨勢，查看**商務活動的 OneDrive**報告。 不過，如果您在報告中選取某一天，表格（7）將會從目前的日期顯示最多28天的資料（不是報告產生的日期）。  <br/> |
|2.  <br/> |每個報告中的資料通常會涵蓋過去24到48小時。 <br/>|
|3.  <br/> |[檔案 **] 視圖可**協助您瞭解可對任何 OneDrive 帳戶執行檔案互動的授權使用者的唯一數目。  <br/> |
|4.  <br/> |[**使用者**] 視圖可協助您瞭解作用中 OneDrive 使用者數目的趨勢。 使用者只要在指定的期間內曾經執行過檔案活動 (儲存、同步、修改或共用)，就會視為使用中。  <br/> 附注：一個檔案的檔案活動可能會發生多次，但只會計入一個作用中的檔。 例如，您可能會在指定期間內多次儲存並同步處理同一個檔案，但在資料中它只會採計為一個使用中的檔案和一個同步處理的檔案。           |
|5.  <br/> | **在 [檔案**] 圖表上，Y 軸是任何使用者儲存、同步處理、修改或共用的唯一檔案數目。  <br/>  在 [**使用者**] 圖表上，Y 軸是對任何 OneDrive 帳戶執行檔互動（儲存、同步處理、修改或共用）的唯一使用者數目。  <br/>  所有圖表中的 X 軸都代表此特定報告的所選日期範圍。  <br/> |
|6.  <br/> |您可以選取圖例中的專案，以篩選您在圖表上看到的數列。 例如，**在 [檔案**] 圖表上，選取 [查看]**或 [編輯**或**同步**處理]，以查看只與各項相關的資訊。 變更此選取項目並不會變更格線表格中的資訊。  <br/> |
|7.  <br/> | 表格顯示每個使用者層級的資料明細。 您可以新增或移除表格中的欄位。   <br/>  **Username**是 OneDrive 帳戶擁有者的使用者名稱。  <br/> [**上次活動日期（UTC）** ] 是在所選日期範圍的 OneDrive 帳戶上執行檔案活動的最後日期。 若要查看特定日期發生的活動，請直接選取圖表中的日期。  <br/> ![選取圖表中的特定日期](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png)  <br/>  這會篩選表格，僅針對在該特定日執行活動的使用者，顯示檔活動資料。  <br/> [已**查看] 或 [編輯**的檔案] 是使用者上傳、下載、修改或查看的檔數目。  <br/> [**同步**處理的檔案] 是已從使用者的本機裝置同步處理至 OneDrive 帳戶的檔案數目。  <br/> [**內部共用**的檔案] 是指與組織內的使用者共用的檔案數目，或與群組內的使用者共用的檔案數目（可能包括外部使用者）。  <br/> [**外部共用**的檔案] 是指與組織外的使用者共用的檔案數目。  <br/> [**已刪除**] 表示使用者的授權已移除。  <br/> 附注：只要使用者在選取的時段內授權，則已刪除之使用者的活動仍會顯示在報告中。 [**已刪除**] 資料行可協助您注意使用者可能不再使用中，但會對報表中的資料提供貢獻。<br/>「**刪除日期**」是使用者授權移除的日期。  <br/> 「**已指派的產品**」是授權給使用者的 Microsoft 365 產品。  <br/>  如果您組織的原則使您無法查看使用者資訊可辨識的報告，您可以變更所有這些報告的隱私權設定。 請參閱[Microsoft 365 系統管理中心的活動報告中](activity-reports.md)的 [**我要如何隱藏使用者層級詳細資料？** ] 區段。  <br/> |
|8.  <br/> |選取 [**管理欄**] 圖示 ![ 管理欄 ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) ，以新增或移除報告中的欄。  <br/> |
|9.  <br/> |您也可以選取 [**匯出**] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。  <br/> |
|||
   

