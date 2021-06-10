---
title: 系統管理中心的 Microsoft 365 報告 - Microsoft Teams 使用者活動
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: 瞭解如何取得 Microsoft Teams 使用者活動報告，以及深入瞭解組織中的 Teams 活動。
ms.openlocfilehash: 1f45cd380813a843ad54e6552578941a9741138e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579599"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>系統管理中心的 Microsoft 365 報告 - Microsoft Teams 使用者活動

[Microsoft 365 **報告**] 儀表板會顯示您組織中產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。 在 Microsoft Teams 使用者活動報告，您能夠深入了解組織中的 Microsoft Teams 活動情形。
  
> [!NOTE]
> 您必須是全域系統管理員、全域讀取者或報告讀取者 Microsoft 365 或 Exchange、SharePoint、Teams 服務、Teams 通訊或商務用 Skype 管理員查看報告。  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>如何取得 Microsoft Teams 使用者活動報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取報告**] 下拉式清單中，選取 [ **Microsoft Teams** \> **使用者活動**]。
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>解讀 Microsoft Teams 使用者活動報告

您可以查看 [**活動**] 和 [**使用者**] 圖表，以取得 Microsoft Teams 使用者活動的方式。<br/>![Microsoft 365 報告-Microsoft Teams 使用者活動。](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|項目|描述|
|:-----|:-----|
|1.  <br/> |您可以針對過去7天、30天、90天或180天的趨勢，查看 **Microsoft Teams 使用者活動** 報告。 不過，如果您在報告中選取某一天，則 table (7) 會從目前的日期顯示最多28天的資料， (不是) 產生報表的日期。  <br/> |
|2.  <br/> |每個報告中的資料通常會涵蓋過去24到48小時。  <br/> |
|3.  <br/> |為了確保資料品質，我們會在過去五天執行每日資料驗證檢查，並填入偵測到的任何空隙。 在處理過程中，您可能會發現歷史資料的差異。  <br/> |
|4.  <br/> |**活動** 視圖會顯示活動類型的 Microsoft Teams 活動數目。 活動類型包括各種小組聊天訊息、私人聊天訊息、通話或會議。  <br/> |
|5.  <br/> |[ **使用者** ] 視圖會以活動類型顯示使用者數目。 活動類型包括各種小組聊天訊息、私人聊天訊息、通話或會議。  <br/> |
|6.  <br/> | 在 [ **活動** ] 圖表上，Y 軸是指定活動的計數。  <br/>  **在 [檔案**] 圖表上，Y 軸是參與小組聊天、私人聊天、通話或會議的使用者人數。  <br/>  圖表上的 X 軸是特定報表的選取日期範圍。  <br/> |
|7.  <br/> |您可以選取圖例中的專案，以篩選您在圖表上看到的數列。 例如，在 [ **活動** ] 圖表上，選取 [ **通道郵件**]、[ **交談訊息**]、[ **通話**] 或 [ **會議** ]，以查看只與各項相關的資訊。 變更此選取項目並不會變更格線資料表中的資訊。  <br/> ![篩選 Microsoft Teams 活動圖表](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|8.  <br/> | 所顯示的群組清單是在最長報告時間範圍 (180 天) 內的所有現有 (未被刪除的) 群組。活動的數量會因日期選取範圍而有所不同。  <br/> 附注：您可能不會在欄中看到下列清單中的所有專案，直到您新增這些專案為止。<br/>[使用者 **名稱**] 是使用者的電子郵件地址。 您可以顯示實際的名稱，也可以讓此欄位匿名。  <br/> **上次活動日期 (UTC)** 是指使用者上次參與 Microsoft Teams 活動的日期。  <br/> **通道郵件** 是使用者在指定期間內于小組聊天中張貼的唯一郵件數目。  <br/> **Chat messages** 是使用者在指定期間內于私人聊天中張貼的唯一郵件數目。  <br/> **通話** 是使用者在指定期間內參與的呼叫數目。  <br/> [**會議**] 是使用者在指定期間內參與的線上會議數目。  <br/> **其他活動** 是指使用者的其他小組活動數目。  <br/> [**已刪除**] 表示小組是否已刪除。 如果小組已被刪除，但報告期間內此小組仍有活動，就會出現在格線中且 [已刪除] 會設為 True。  <br/> 「**刪除日期**」是指小組已遭刪除的日期。  <br/> [**已指派產品**] 是指派給使用者的產品清單。  <br/>  如果您組織的原則使您無法查看使用者資訊可辨識的報告，您可以變更所有這些報告的隱私權設定。 請參閱 [Microsoft 365 系統管理中心的活動報告中](activity-reports.md)的 [**我要如何隱藏使用者層級詳細資料？** ] 區段。  <br/> |
|9.  <br/> |選取 [ **欄** ]，以新增或移除報告中的欄。  <br/> ![Teams user activity report - choose columns](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|10.  <br/> |您也可以選取 [**匯出**] 連結，將報表資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。  <br/> |
|||
   

