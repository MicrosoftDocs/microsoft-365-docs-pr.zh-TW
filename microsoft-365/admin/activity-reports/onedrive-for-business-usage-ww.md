---
title: Microsoft 365系統管理中心報告-商務用 OneDrive 使用狀況
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: '取得「商務用 OneDrive 使用方式報告」，以瞭解整個組織所使用的檔案和儲存總數。 '
ms.openlocfilehash: 92dd18c8e8f6ded655ac6f41d1179e96ef81090b
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393340"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365系統管理中心報告-商務用 OneDrive 使用狀況

[Microsoft 365 **報告**] 儀表板會顯示您組織中產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。
  
例如，根據檔案的總數與貴組織已使用的儲存空間，儀表板上的 [OneDrive] 卡片可以提供您來自商務用 OneDrive 的高層級檢視。您可以進行深入分析，以了解作用中 OneDrive 帳戶的趨勢、使用者正在與多少個檔案進行互動，以及已使用的儲存空間。也會提供您每個使用者的 OneDrive 詳細資料。
  
> [!NOTE]
> 您必須是全域系統管理員、全域讀取者或報告讀取者 Microsoft 365 或 Exchange、SharePoint、Teams 服務、Teams 通訊或商務用 Skype 管理員查看報告。  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>如何進入 OneDrive 活動報告？

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。 
2. 在 [儀表板] 主頁上，按一下 [OneDrive 卡片上的 [ **View more** ] 按鈕。
  
## <a name="interpret-the-onedrive-usage-report"></a>解讀 OneDrive 使用狀況報告

您可以選擇 [**使用狀況**] 索引標籤，在 OneDrive 報告中查看使用狀況。<br/>![Microsoft 365 報告-Microsoft OneDrive 使用狀況報告。](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

選取 **[選擇欄位** ]，以新增或移除報告中的欄。  <br/> ![OneDrive 使用狀況報告-選擇欄](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

您也可以選取 [**匯出**] 連結，將報表資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。 
  
|項目|描述|
|:-----|:-----|
|**計量**|**定義**|
|URL  <br/> |使用者的 OneDrive 網址。 <br/> |
|已刪除  <br/> |OneDrive 的刪除狀態。 帳戶至少要 7 天才會標示為已刪除。  <br/> |
|擁有者  <br/> |OneDrive 主要系統管理員的使用者名稱。   <br/> |
|擁有者主要名稱  <br/> |OneDrive 擁有者的電子郵件地址。 <br/> |
|上次活動日期 (UTC)   <br/> | 在 OneDrive 中執行檔案活動的最晚日期。 如果 OneDrive 最近沒有檔案活動，值將會是空白。  <br/> |
|檔案  <br/> |OneDrive 中的檔數。 <br/>|
|使用中檔  <br/> | 時段內使用中檔案的數目。<br/> 附注：如果在報告的指定期間內已移除檔案，則報告中顯示的使用中檔案數目可能會大於目前 OneDrive 中的檔案數目。 > 刪除的使用者會在180天內繼續顯示在報告中。  <br/> |
|儲存體使用 (MB)   <br/> |OneDrive 使用的儲存量（以 MB 為單位）。 |
|||