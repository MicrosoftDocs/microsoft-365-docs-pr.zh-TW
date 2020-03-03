---
title: Office 365 系統管理中心-Microsoft Teams 裝置使用量報告
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
description: 深入了解您組織中由從 Office 365 報告取得 Microsoft Teams app 使用情況報告的 Microsoft Teams 應用程式的情形。
ms.openlocfilehash: 872cde92ccd66f4de5199a5035eaaa83b79f0cc0
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353654"
---
# <a name="office-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Office 365 系統管理中心-Microsoft Teams 裝置使用量報告

在 Office 365**報告**儀表板顯示您的活動概觀跨組織中的產品。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。 在 Microsoft Teams App 使用情況報告，您能夠深入了解組織中的 Microsoft Teams App 使用情形。
  
> [!NOTE]
> 您必須是全域系統管理員、 全域讀者或報告讀取者，在 Microsoft 365 或 Exchange、 SharePoint 或 Skype 商務系統管理員，才能查看報告。 
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>如何取得 Microsoft Teams App 使用情況報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取 [報告]** 下拉式清單，選取 [ **Microsoft Teams** \> **裝置使用量**。
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>解讀 Microsoft Teams App 使用情況報告

您可以透過檢視 Microsoft Teams app 使用情況查看 [**使用者**] 和 [**通訊**圖表。 
  
![Office 365 reports - Microsoft Teams app usage](../../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|||
|:-----|:-----|
|1.  <br/> |[ **Microsoft Teams 裝置使用量**] 報告可檢視的趨勢，過去 7 天、 30 天、 前 90 天或 180 天。 不過，如果您在報表中選取的特定一天，表格 (7) 將會顯示資料 28 天，從目前的日期 （不是該報告產生的日期）。  <br/> |
|2.  <br/> |每個報告中的資料通常涵蓋的最後一個 24 到 48 小時。  <br/> |
|3.  <br/> |[**使用者**] 檢視您的每日單獨使用者數目會依據 app 顯示。  <br/> |
|4.  <br/> |**通訊群組**] 檢視您的唯一使用者數目會依據 app 顯示在選取的時間期間。  <br/> |
|5.  <br/> | 在 [**使用者**] 圖表中，Y 軸是每部應用程式的使用者數目。  <br/>  在 [**通訊群組**] 圖表中，Y 軸是使用特定的 app 的使用者數目。  <br/>  圖表上的 X 軸代表該特定報告的已選取日期範圍。  <br/> |
|6.  <br/> |您可以篩選看圖表所選取項目在圖例中的數列。 例如，在 [**使用者**] 圖表中，選取 [ **Windows**、 **Mac**、**電話**、 **Web**、 **Android 手機**或**Windows phone** ，以查看只與其個別相關的資訊。 變更此選取項目並不會變更格線資料表中的資訊。  <br/> ![您可以選取應用程式類型來篩選 Microsoft Teams app 使用圖表。](../../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|7.  <br/> | 所顯示的群組清單是在最長報告時間範圍 (180 天) 內的所有現有 (未被刪除的) 群組。活動的數量會因日期選取範圍而有所不同。  <br/> 附註： 您可能不會看到下方清單中的資料行中的所有項目直到您新增那些。<br/> **Username**是使用者的電子郵件地址。 您可以顯示實際的名稱，也可以讓此欄位匿名。  <br/> **上次活動日期 (UTC)** 是指使用者參與 Microsoft Teams 活動的應用程式中的最後一個日期。  <br/> **刪除的郵件**會指出小組會在刪除。 如果小組已被刪除，但報告期間內此小組仍有活動，就會出現在格線中且 [已刪除] 會設為 True。  <br/> **已刪除日期**是小組被刪除的日期。  <br/> 如果使用者在指定的時間期間內使用 Windows app，系統會檢查**Windows** 。  <br/> 如果使用者在指定的時間期間內使用 Mac app，系統會檢查**Mac** 。  <br/> 如果使用者最近使用的 web 應用程式中指定的時間期間，系統會檢查**網頁**。  <br/> 如果使用者在指定的時間期間內使用 iOS app，系統會檢查**iOS** 。  <br/> 如果使用者在指定的時間期間內使用 Android 手機 app，系統會檢查**android 手機**。  <br/> 如果使用者最近使用的 Windows Phone 應用程式中指定的時間期間，系統會檢查**Windows phone** 。  <br/>  如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。 請參閱**如何隱藏使用者層級的詳細資訊？** ] 區段中[的 Microsoft 365 系統管理中心的活動報告](activity-reports.md)中。  <br/> |
|8.  <br/> |選取要新增或移除報告中的資料行的**資料行**。  <br/> ![Teams uapp usage report - choose columns](../../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |您可以也報告資料匯出到 Excel.csv 檔案，藉由選取 [**匯出**] 連結。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。  <br/> |
|||
   
  

