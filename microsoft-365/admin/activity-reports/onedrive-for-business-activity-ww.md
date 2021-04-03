---
title: Admin center 中的 Microsoft 365 報告-Business activity OneDrive
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 取得組織的 OneDrive 使用方式報告，並瞭解每個 OneDrive 使用者的活動、共用的檔案數目及儲存使用量。
ms.openlocfilehash: 7b6173b3a86187e4612aaaa51bafbfbe965a6cfa
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579527"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Admin center 中的 Microsoft 365 報告-Business activity OneDrive

Microsoft 365 **報告** 儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報告，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。
  
例如，您可以查看每位授權使用 OneDrive 的使用者與 OneDrive 上檔案的互動，以了解活動。也可以查看共用的檔案數量，協助您了解共同作業的程度。
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>如何進入 OneDrive 活動報告？

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。 
2. 在 [儀表板] 主頁上，按一下 [OneDrive 卡片上的 [ **View more** ] 按鈕。
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>解讀商務用 OneDrive 活動報告

您可以選擇 [ **活動** ] 索引標籤，以查看 OneDrive 報告中的活動。<br/>![Microsoft 365 報告-Microsoft OneDrive 活動報告。](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

選取 **[選擇欄位** ]，以新增或移除報告中的欄。  <br/> ![OneDrive 活動報告-選擇欄](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

您也可以選取 [ **匯出** ] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。 
  
|項目|描述|
|:-----|:-----|
|**計量**|**定義**|
|使用者名稱  <br/> |OneDrive 帳戶擁有者的使用者名稱。  <br/> |
|上次活動日期 (UTC)   <br/> |在所選日期範圍的 OneDrive 帳戶上執行檔案活動的最晚日期。 . 若要查看特定日期發生的活動，請直接選取圖表中的日期。  <br/> |
|查看或編輯的檔案  <br/> |使用者上傳、下載、修改或查看的檔數目。   <br/> |
|同步處理的檔案  <br/> |已從使用者的本機裝置同步處理至 OneDrive 帳戶的檔案數目。 <br/> |
|內部共用的檔案  <br/> | 與組織內的使用者共用的檔案數目，或與可能包含外部使用者)  (的群組中的使用者共用的檔案數目。  <br/> |
|外部共用檔案  <br/> |與組織外的使用者共用的檔案數目。 <br/>|
|已刪除  <br/> | 這表示已移除使用者的授權。  <br/> 附注：只要使用者在選取的時段內授權，則已刪除之使用者的活動仍會顯示在報告中。 [ **已刪除** ] 資料行可協助您注意使用者可能不再使用中，但會對報表中的資料提供貢獻。  <br/> |
|刪除日期  <br/> |移除使用者授權的日期。 <br/>|
|指派的產品  <br/> |授權給使用者的 Microsoft 365 產品。|
|||