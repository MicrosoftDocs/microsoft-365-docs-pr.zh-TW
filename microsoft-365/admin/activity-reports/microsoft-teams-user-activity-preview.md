---
title: 系統管理中心的 microsoft 365 報告-Microsoft 團隊使用者活動-預覽
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
ms.openlocfilehash: 734a4dfd62160c2f4d29b8faffb3268a1962fe4f
ms.sourcegitcommit: a50260b7c5be7374e8e2bea19cc08406ef51ac47
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/17/2020
ms.locfileid: "45167338"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity--preview"></a>系統管理中心的 microsoft 365 報告-Microsoft 團隊使用者活動-預覽

Microsoft 365**報告**儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。 在 Microsoft Teams 使用者活動報告，您能夠深入了解組織中的 Microsoft Teams 活動情形。
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。  
 
## <a name="how-to-get-to-the-preview-microsoft-teams-user-activity-report"></a>如何取得預覽 Microsoft 團隊使用者活動報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。
2. 從 [**選取報告**] 下拉式清單中，選取 [ **Microsoft 小組**]。
  
## <a name="interpret-the-preview-microsoft-teams-user-activity-report"></a>轉譯預覽 Microsoft 團隊使用者活動報告

您可以選擇 [**使用者活動**] 索引標籤，在 [預覽小組] 報告中查看使用者的活動。
  
|||
|:-----|:-----|
|**計量**|**定義**|
|使用者名稱  <br/> |使用者的電子郵件地址。 您可以顯示實際的名稱，也可以讓此欄位匿名。   <br/> |
|通道郵件   <br/> |使用者在指定期間內于小組聊天中張貼的唯一郵件數目。  <br/> |
|聊天訊息   <br/> |使用者在指定期間內，于私人聊天中張貼的唯一郵件數目。  <br/> |
|會議總數   <br/> |使用者在指定期間內參與的線上會議數目。  <br/> |
|1:1 通話   <br/> | 使用者在指定期間內參與的1:1 通話數目。  <br/> |
|上次活動日期（UTC）  <br/> |使用者參與 Microsoft 小組活動的最後日期。<br/> |
|會議已即席參加   <br/> | 使用者在指定期間內參與的行事曆上未排定的會議數目。  <br/> |
|以特殊方式組織的會議 <br/> |在指定期間內，使用者組織的行事曆中未排定的會議數目。 <br/>|
|排程組織的會議  <br/> |使用者在指定期間內組織的排程會議數目。  <br/> |
|已授權 |如果使用者授權使用小組，則選取此選項。|
|其他活動|使用者被視為作用中，但聊天訊息、1:1 通話、通道訊息、會議總數和會議組織的值都是空的。 範例動作是指將 Microsoft 團隊用戶端啟動至前景時，會在 [撰寫郵件] 區域中採取動作，快顯通知顯示在 Microsoft 團隊用戶端，顯示在 Microsoft 團隊用戶端中的橫幅，等等。 |
|||