---
title: 系統管理中心的 microsoft 365 報告-Microsoft 團隊使用者活動
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: 瞭解如何取得 Microsoft 團隊使用者活動報告，並深入瞭解組織中的小組活動。
ms.openlocfilehash: 5b6c67903e7af600cac6ad1fda10962aecc2cc83
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949025"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>系統管理中心的 microsoft 365 報告-Microsoft 團隊使用者活動

Microsoft 365 **報告** 儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。 在 Microsoft Teams 使用者活動報告，您能夠深入了解組織中的 Microsoft Teams 活動情形。
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>如何取得 Microsoft Teams 使用者活動報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。
2. 在 [儀表板] 主頁上，按一下 [Microsoft 小組] 活動卡片上的 [ **View more** ] 按鈕。
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>解讀 Microsoft Teams 使用者活動報告

您可以選擇 [ **使用者活動** ] 索引標籤，以查看小組報表中的使用者活動。 <br/>![Microsoft 365 報告-Microsoft 團隊使用者活動。](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

選取 **[選擇欄位** ]，以新增或移除報告中的欄。  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

您也可以選取 [ **匯出** ] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。 

|項目|描述|
|:-----|:-----|
|**計量**|**定義**|
|使用者名稱  <br/> |使用者的電子郵件地址。 您可以顯示實際的名稱，也可以讓此欄位匿名。   <br/> |
|通道郵件   <br/> |使用者在指定期間內于小組聊天中張貼的唯一郵件數目。  <br/> |
|聊天訊息   <br/> |使用者在指定期間內，于私人聊天中張貼的唯一郵件數目。  <br/> |
|會議總數   <br/> |使用者在指定期間內參與的線上會議數目。  <br/> |
|1:1 通話   <br/> | 使用者在指定期間內參與的1:1 通話數目。  <br/> |
|上次活動日期 (UTC)   <br/> |使用者參與 Microsoft 小組活動的最後日期。<br/> |
|會議已即席參加   <br/> | 使用者在指定期間內參與的行事曆上未排定的會議數目。  <br/> |
|以特殊方式組織的會議 <br/> |在指定期間內，使用者組織的行事曆中未排定的會議數目。 <br/>|
|排程組織的會議  <br/> |使用者在指定期間內組織的排程會議數目。  <br/> |
|已授權 |如果使用者授權使用小組，則選取此選項。|
|其他活動|使用者被視為作用中，但聊天訊息、1:1 通話、通道訊息、會議總數和會議組織的值都是空的。 範例動作是指將 Microsoft 團隊用戶端啟動至前景時，會在 [撰寫郵件] 區域中採取動作，快顯通知顯示在 Microsoft 團隊用戶端，顯示在 Microsoft 團隊用戶端中的橫幅，等等。 |
|||