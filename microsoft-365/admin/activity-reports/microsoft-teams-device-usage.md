---
title: 系統管理中心的 microsoft 365 報告-Microsoft 團隊裝置使用量
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 917b3e1d-203e-4439-8539-634e80196687
description: 從 Microsoft 365 報告取得 Microsoft 團隊應用程式使用方式報告，深入瞭解組織中所使用的 Microsoft 團隊應用程式。
ms.openlocfilehash: 9c79f83d90905470c56fd62489f1439b3383841f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621207"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>系統管理中心的 microsoft 365 報告-Microsoft 團隊裝置使用量

Microsoft 365**報告**儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。 在 Microsoft Teams App 使用情況報告，您能夠深入了解組織中的 Microsoft Teams App 使用情形。
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>如何取得 Microsoft Teams App 使用情況報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取報告**] 下拉式清單中，選取 [ **Microsoft 團隊** \> **裝置使用量**]。
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>解讀 Microsoft Teams App 使用情況報告

您可以查看 [**使用者**] 和 [**通訊**群組] 圖表，以查看 Microsoft 團隊應用程式使用方式。 
  
![Microsoft 365 報告-Microsoft 小組應用程式使用方式](../../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|||
|:-----|:-----|
|1.  <br/> |**Microsoft 團隊裝置使用方式**報告可查看過去7天、30天、90天或180天的趨勢。 不過，如果您在報告中選取某一天，表格（7）將會從目前的日期顯示最多28天的資料（不是報告產生的日期）。  <br/> |
|2.  <br/> |每個報告中的資料通常會涵蓋過去24到48小時。  <br/> |
|3.  <br/> |[**使用者**] 視圖會顯示應用程式每日的唯一使用者數目。  <br/> |
|4.  <br/> |「**散佈**」視圖會以應用程式為您顯示選取的時段內，依應用程式的唯一使用者數目。  <br/> |
|5.  <br/> | 在 [**使用者**] 圖表上，Y 軸是每個應用程式的使用者數目。  <br/>  在 [**分配**] 圖表上，Y 軸是使用指定應用程式的使用者數目。  <br/>  圖表上的 X 軸代表該特定報告的已選取日期範圍。  <br/> |
|6.  <br/> |您可以選取圖例中的專案，以篩選您在圖表上看到的數列。 例如，在 [**使用者**] 圖表上，選取 [ **Windows**]、[ **Mac**]、[**通話** **]、[** **Android 手機**版] 或 [ **Windows phone** ]，只查看與各項相關的資訊。 變更此選取項目並不會變更格線資料表中的資訊。  <br/> ![您可以透過選取應用程式類型來篩選 Microsoft 團隊應用程式使用狀況圖表。](../../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|7.  <br/> | 所顯示的群組清單是在最長報告時間範圍 (180 天) 內的所有現有 (未被刪除的) 群組。活動的數量會因日期選取範圍而有所不同。  <br/> 附注：您可能不會在欄中看到下列清單中的所有專案，直到您新增這些專案為止。<br/> [使用者**名稱**] 是使用者的電子郵件地址。 您可以顯示實際的名稱，也可以讓此欄位匿名。  <br/> [**上次活動日期（UTC）** ] 是指使用者在應用程式中參加 Microsoft 小組活動的最後日期。  <br/> [**已刪除**] 表示小組是否已刪除。 如果小組已被刪除，但報告期間內此小組仍有活動，就會出現在格線中且 [已刪除] 會設為 True。  <br/> 「**刪除日期**」是指小組已遭刪除的日期。  <br/> 如果使用者在指定期間內使用 Windows 應用程式，則會檢查**windows** 。  <br/> 如果使用者在指定期間內使用 Mac 應用程式，則會檢查**mac** 。  <br/> 如果使用者在指定的時段內使用 Web 應用程式，則會檢查**網頁**。  <br/> 如果使用者在指定期間內使用 iOS 應用程式，則會檢查**iOS** 。  <br/> 如果使用者在指定期間內使用 Android 電話應用程式，則會檢查**android 手機**。  <br/> 如果使用者在指定期間內使用 Windows Phone 應用程式，則會檢查**windows phone** 。  <br/>  如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。 請參閱[Microsoft 365 系統管理中心的活動報告中](activity-reports.md)的 [**我要如何隱藏使用者層級詳細資料？** ] 區段。  <br/> |
|8.  <br/> |選取 [**欄**]，以新增或移除報告中的欄。  <br/> ![Teams uapp usage report - choose columns](../../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |您也可以選取 [**匯出**] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。  <br/> |
|||
   
  

