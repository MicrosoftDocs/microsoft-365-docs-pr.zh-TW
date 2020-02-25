---
title: Microsoft 365 使用情況報告中的作用中使用者
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: 了解 Microsoft 365 使用情況分析、 活動報告和採用公制作用中使用者。
ms.openlocfilehash: 0e2f5f5112593c142b4a7829977221c5542adf49
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240036"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Microsoft 365 使用情況報告中的作用中使用者

## <a name="active-user-in-usage-reports"></a>使用量報告中的作用中使用者

Microsoft 365 產品的[Microsoft 365 使用情況分析](usage-analytics.md)和[在系統管理中心的活動報告](../activity-reports/activity-reports.md)的作用中使用者定義，如下所示。 
  
|**產品**|**作用中使用者定義**|**附註**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |已讀取或傳送電子郵件的任何使用者。  <br/> |未顯示任何行事曆資訊，這會新增接下來的更新中。  <br/> |
|SharePoint Online  <br/> |透過在任何網站上建立、修改、檢視、刪除、內外部共用或同步處理至用戶端以與檔案互動，或是檢視任何網站頁面的任何使用者。  <br/> |在 Microsoft 365 使用情況分析範本應用程式中的作用中使用者] 計量的 SharePoint Online，只會反映曾完成檔案活動的 SharePoint 小組網站或群組網站的使用者。 會更新範本應用程式，以同步處理至相同的定義，在系統管理中心使用情況報告。  <br/> |
|商務用 OneDrive  <br/> |透過建立、修改、檢視、刪除、內外部共用或同步處理至用戶端以與檔案互動的任何使用者。  <br/> ||
|Yammer  <br/> |已在 Yammer 上讀取、張貼或喜歡訊息的任何使用者。  <br/> ||
|商務用 Skype  <br/> |已參與端對端工作階段 (包括即時傳訊、音訊和視訊通話、應用程式共用和檔案轉移) 或已主辦或參與會議的任何使用者。  <br/> ||
|Office  <br/> |已啟動其 Microsoft 365 專業增強版、 Visio Pro 或 Project Pro 訂閱至少一部裝置上的任何使用者。  <br/> ||
|Microsoft 365 群組  <br/> |任何有信箱活動的群組成員 (若有郵件已傳送至群組)。  <br/> |這個定義將會增強與群組網站的檔案活動] 和 [Yammer 群組活動 （群組網站及訊息張貼至 Yammer 群組與群組相關聯的檔案活動）。此資料並目前不提供 Microsoft 365 使用情況分析範本應用程式  <br/> |
|Microsoft Teams  <br/> |已經參與聊天訊息、 私人聊天訊息、 通話、 會議或其他活動任何使用者。 其他活動是定義為其他小組活動數目之使用者所某些其中包含，而不限於： 依郵件、 應用程式]，使用檔案、 搜尋、 下列小組通道和 favoriting 它們。  <br/> ||
   
## <a name="adoption-metrics"></a>採用計量

[Microsoft 365 使用情況分析](usage-analytics.md)含有作用中的使用者顯示一段時間採用產品與相關的其他採用計量。 這些計量有效用於月、 年和選取的產品，而且的定義如下。 
  
|**評量**|**描述**|
|:-----|:-----|
|EnabledUsers  <br/> |若要在月份中使用產品啟用的使用者數目。  <br/> |
|Activeusers 工作負載  <br/> |使用在月份中的使用者數目。  <br/> |
|MoMReturningUsers  <br/> |使用的使用者數目當月也已作用中的上述的月份。  <br/> |
|FirstTimeUsers  <br/> |使用有從未使用過的服務之前在月份中的使用者數目。  <br/> |
|CumulativeActiveUsers  <br/> |使用月加上任何先前的月份中的使用者數目。  <br/> |
|ActiveUsers(%)  <br/> |%的使用者，相較於該月份中啟用的使用者人數當月四捨五入至最接近的第十個，作用中。  <br/> |
|MoMReturningUsers(%)  <br/> |%的使用者，四捨五入至最接近的第十個，主動中也已內使用相較於作用中使用者數上述月份的月份。  <br/> |
   
MoMReturningUsers、 FirstTimeUsers， &amp; CumulativeActiveUsers 已重設 1st 2018 年 1 月開頭的 Microsoft Teams 包含相對路徑。
  
