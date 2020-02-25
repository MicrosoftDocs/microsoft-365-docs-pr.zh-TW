---
title: Microsoft 365 系統管理中心報告中的商務用 OneDrive 使用量
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 0de3b312-c4e8-4e4b-a02d-32b2f726a680
description: '取得商務用 OneDrive 使用狀況報告來了解的檔案和整個組織使用的儲存空間總數。 '
ms.openlocfilehash: b735a1e38eb2029ba1f8f0857f8aa621239e9bba
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239503"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365 系統管理中心報告中的商務用 OneDrive 使用量

Microsoft 365**報告**儀表板顯示您的活動概觀跨組織中的產品。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。
  
例如，根據檔案的總數與貴組織已使用的儲存空間，儀表板上的 [OneDrive] 卡片可以提供您來自商務用 OneDrive 的高層級檢視。您可以進行深入分析，以了解作用中 OneDrive 帳戶的趨勢、使用者正在與多少個檔案進行互動，以及已使用的儲存空間。也會提供您每個使用者的 OneDrive 詳細資料。
  
> [!NOTE]
> 您必須是全域系統管理員、 全域讀者或報告讀取者，在 Microsoft 365 或 Exchange、 SharePoint 或 Skype 商務系統管理員，才能查看報告。 
 
## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>如何進入 OneDrive 使用狀況報告？

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取 [報告]** 下拉式清單，選取 [ **OneDrive** \> **流量**。 
  
## <a name="interpret-the-onedrive-usage-report"></a>解讀 OneDrive 使用狀況報告

您可以透過檢視到 OneDrive 商務的使用狀況查看**帳戶**、**檔案**及**儲存**檢視。 
  
![OneDrive Usage Report](../media/49c5b93b-d081-436e-8992-236343a6d46b.png)
  
|||
|:-----|:-----|
|1.  <br/> |**OneDrive 使用情況**報告顯示過去 7 天、 30 天、 前 90 天或 180 天的趨勢。 不過，如果您在報表中選取的特定一天，表格 (7) 將會顯示資料 28 天，從目前的日期 （不是該報告產生的日期）。  <br/> |
|2.  <br/> |每個報告中的資料通常涵蓋的最後一個 24 到 48 小時。 <br/>|
|3.  <br/> |[**帳戶**] 檢視會顯示趨勢的總數與作用中 OneDrive 帳戶數目。 「使用中的帳戶」指的是使用者用來檢視、修改、上傳、下載、共用或同步處理檔案的帳戶。  <br/> |
|4.  <br/> |[**檔案**] 檢視會顯示總數與作用中檔案的數目。 使用中的檔案指的是在指定時間週期中曾經儲存、同步處理、修改或共用過的檔案。  <br/> 附註： 單一檔案，可以發生多次檔案活動，但只會算做一個使用中檔案。 例如，您可能會在指定時間週期中多次儲存並同步處理同一個檔案，但在資料中它都只會計算為一個使用中的檔案和一個同步處理的檔案。           |
|5.  <br/> |**儲存空間**] 檢視會顯示您正在使用的 OneDrive 儲存空間量的趨勢。  <br/> > 附註： 此大小包括任何版本和與檔案關聯的中繼資料。           |
|6.  <br/> | 在 [**帳戶**] 圖表中，Y 軸是 OneDrive 帳戶數目。  <br/>  在 [**檔案**] 圖表中，Y 軸是儲存在 OneDrive 中的檔案數目。  <br/>  在 [**儲存空間**] 圖表中，Y 軸是 OneDrive 儲存空間量。  <br/>  所有圖表中的 X 軸都代表此特定報告的所選日期範圍。  <br/> |
|7.  <br/> |您可以篩選看圖表所選取項目在圖例中的數列。 例如，在 [**檔案**] 圖表中，選取 [**檔案總數**] 或 [**使用中的檔案**。 在 [**帳戶**] 圖表中，選取 [**帳戶總計**] 或 [**作用中的帳戶**。 或在**儲存空間**] 圖表中，選取 [**使用的儲存空間**。 變更選取項目並不會變更表格中的資訊。  <br/> |
|8.  <br/> | 表格顯示每位使用者的 OneDrive資料明細。若要在表格中顯示，使用者必須獲得包含 OneDrive 的產品授權，而且必須開啟 SharePoint Online。使用者還必須登入 OneDrive 同步處理用戶端，或使用網頁瀏覽器瀏覽至其 OneDrive。  <br/>  如果 OneDrive 中有檔案活動，表格會顯示最近一次執行檔案活動的日期。 表格中的列是依 **[上次活動日期**排序，讓最新的檔案活動的 OneDrive 會出現在清單最頂端。  <br/>  您可以新增或移除表格中的欄位。  <br/> ![資料行選項](../media/onedriveusage-columns.png)  <br/> **URL**是使用者的 OneDrive 網址。  <br/> **刪除的郵件**是商務用 onedrive 的刪除狀態。 帳戶至少要 7 天才會標示為已刪除。  <br/> **擁有者**] 是 OneDrive 主要系統管理員使用者名稱。  <br/> **擁有者的主體名稱**是商務用 onedrive 擁有者的電子郵件地址。  <br/> **[上次活動日期 (UTC)** 是在 onedrive 執行檔案活動的最晚日期。 如果 OneDrive 最近沒有檔案活動，值將會是空白。  <br/> **檔案**] 是 OneDrive 中的檔案數目。  <br/> **作用中的檔案**] 是作用中的檔案數目的期間內。 使用中的檔案指的是在選定期間中曾經儲存、同步處理、修改或共用過的檔案。  <br/> 附註： 單一檔案，可以發生多次檔案活動，但只會算做一個使用中檔案。 例如，您可能會在指定時間週期中多次儲存並同步處理同一個檔案，但在資料中它都只會計算為一個使用中的檔案和一個同步處理的檔案。 > 若檔案已移除報告中，顯示在報告中的作用中檔案數目的指定的時間週期期間可能會大於目前的 OneDrive 中的檔案數目。 > 已刪除使用者仍可在報表中會出現 180 天。<br/>**使用的儲存空間 (MB)** 是 OneDrive 使用以 mb 為單位的儲存空間量。 這包括任何版本以及與檔案關聯的中繼資料。  <br/>  如果貴組織的原則防止您檢視報告所在識別使用者資訊，您可以變更所有這類報告的隱私權設定。 請參閱**如何隱藏使用者層級的詳細資訊？** [Microsoft 365 系統管理中心預覽中的活動報告](activity-reports.md)中的區段。  <br/> |
|9.  <br/> |選取 [**管理欄**] 圖示![管理欄](../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png)來新增或移除報告中的欄。  <br/> |
|10.  <br/> |您可以也報告資料匯出到 Excel.csv 檔案，藉由選取 [**匯出**] 連結。 這會匯出每個 OneDrive 的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的 OneDrive 帳戶少於 2000 個，可以直接在報告中的表格上進行排序和篩選。 如果您的 OneDrive多於 2000 個，則需要匯出資料才能進行篩選和排序。  <br/> 附註： 當資料匯出至 Excel 檔案時，請注意該內容的報告產生的日期會反映在**資料做為**資料行中的檔案。  <br/> |
|||
   

