---
title: Admin center 中的 Microsoft 365 報告-SharePoint 活動
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- SPO160
- BSA160
ms.assetid: a91c958f-1279-499d-9959-12f0de08dc8f
description: 取得「SharePoint 活動使用方式」報告，以瞭解每個 SharePoint 使用者的活動、共用的檔案數目及儲存使用量。
ms.openlocfilehash: de4d4951f98e722a3608e9bccf2c4a1dbfc388d0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387486"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Admin center 中的 Microsoft 365 報告-SharePoint 活動

做為 Microsoft 365 系統管理員，[**報告**] 儀表板會顯示您組織中各種產品的活動概況。 此功能可讓您更深入解析各項產品的特定活動。 請參閱[Microsoft 365 系統管理中心的活動報告](activity-reports.md)。
  
例如，您可以查看每位授權使用 SharePoint 的使用者與檔案的互動，以了解他們的活動。也可以查看共用的檔案數量，幫助您了解共同作業的程度。
  
> [!NOTE]
> 一些功能會逐步地增加。這表示您可能還未見到此功能，或者功能可能與說明文章中描述的不一樣。如果您還未見到，不用擔心，功能即將推出！ 
  
如果要了解每個 SharePoint 網站的活動量和儲存空間使用情形，請檢視 [SharePoint 網站流量報告](sharepoint-site-usage.md)。
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。  
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>如何存取 SharePoint 活動報告？

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取報告**] 下拉式清單中，選取 [ **SharePoint** \> **活動**]。
  
## <a name="interpreting-the-sharepoint-activity-report"></a>解讀 SharePoint 活動報告

您可以透過查看 [檔案] 和 [**使用者**] 視圖 **，取得**SharePoint 活動的方式。<br/> ![SharePoint Activity Report](../../media/96ee85af-f213-499b-9e2b-22912bd0b8c2.png)
  
|||
|:-----|:-----|
|1.  <br/> |您可以針對過去7天、30天、90天或180天的趨勢，查看**SharePoint 活動報告**。 不過，如果您在報告中選取某一天，表格（7）將會從目前的日期顯示最多28天的資料（不是報告產生的日期）。  <br/> |
|2.  <br/> |每個報告中的資料通常會涵蓋過去24到48小時。  <br/> |
|3.  <br/> |[**檔案**] 視圖可協助您瞭解可對 SharePoint 網站上儲存之檔案執行檔案互動的唯一授權使用者數目。  <br/> |
|4.  <br/> |[**頁面**] 視圖會顯示使用者所訪問的唯一頁面數目。  <br/> |
|5.  <br/> |[**使用者**] 視圖可協助您瞭解作用中使用者數目的趨勢。 使用者在指定的期間內若曾經執行過檔案活動 (儲存、同步處理、修改或共用) 或瀏覽過頁面，就會被視為作用中使用者。  <br/> 附注：一個檔案的檔案活動可能會發生多次，但是只會算作一個作用中的檔案。 例如，您可能會在指定時間週期中多次儲存並同步處理同一個檔案，但在資料中它都只會計算為一個使用中的檔案和一個同步處理的檔案           |
|6.  <br/> | **在 [檔案**] 圖表上，Y 軸是使用者儲存、同步處理、修改或共用的唯一檔計數。  <br/>  在 [**使用者**] 圖表上，Y 軸是在網站上執行檔互動（儲存、同步處理、修改或共用）的唯一使用者數目。  <br/>  在 [**頁面**] 圖表上，X 軸是使用者所訪問之唯一頁面的計數。  <br/>  所有圖表中的 X 軸都代表此特定報告的所選日期範圍。  <br/> |
|7.  <br/> |您可以選取圖例中的專案，以篩選您在圖表上看到的數列。 例如，**在 [檔案**] 圖表上，選取 [已查看]**或 [編輯**]、[**內部共用**] 或 [在**外部**共用 **]，以**查看與各項相關的資訊。 變更此選取項目並不會變更格線資料表中的資訊。  <br/> |
|8.  <br/> | 表格顯示每個網站層級的活動明細。  <br/>  <br/> **Username**是在 SharePoint 網站上執行活動之使用者的電子郵件地址。  <br/> [**上次活動日期（UTC）** ] 是最近一次執行檔案活動的日期，或為選取的日期範圍所訪問的頁面。 若要查看特定日期發生的活動，請直接選取圖表中的日期。  <br/> ![選取圖表中的特定日期](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png) <br/> 這會篩選表格，僅針對在該特定日執行活動的使用者，顯示檔活動資料。  <br/>  [已**查看] 或 [編輯**的檔案] 是使用者上傳、下載、修改或查看的檔數目。  <br/>  [**同步**處理的檔案] 是已從使用者的本機裝置同步處理至 SharePoint 網站的檔案數目。  <br/>  [**內部共用**的檔案] 是指與組織內的使用者共用的檔案數目，或與群組中的使用者（可能包含外部使用者）共用的檔案數目。  <br/>  [**外部共用**的檔案] 是指與組織外的使用者共用的檔案數目。  <br/>  「所**訪問的頁面**」是使用者對獨特頁面的訪問。  <br/>  [**已刪除**] 表示使用者的授權已移除。  <br/>  **附注：** 已刪除使用者的活動只要在選取的時段內某一時刻授權，系統仍會顯示在報告中。 [已刪除] 欄可提醒您該名使用者可能已停止使用，但仍對報告中的資料有影響。  <br/> 「**刪除日期**」是使用者授權移除的日期。  <br/>  「已**指派的產品**」是授權給使用者的 Microsoft 365 產品。  <br/> |
|9.  <br/> |選取 [**管理欄**] 圖示 ![ 管理欄 ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) ，以新增或移除報告中的欄。  <br/> |
|10.  <br/> |您也可以選取 [**匯出**] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 位，您可以直接在報告中的表格上進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。  <br/> |
|||
   

