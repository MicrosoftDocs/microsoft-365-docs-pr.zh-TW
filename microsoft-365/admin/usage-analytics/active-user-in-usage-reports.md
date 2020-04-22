---
title: Microsoft 365 使用方式報告中的作用中使用者
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
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: 深入瞭解 Microsoft 365 流量分析、活動報告和採用度量的使用者。
ms.openlocfilehash: 2117bae32913ad713318c1df25be66d6ef6859e5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631788"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Microsoft 365 使用方式報告中的作用中使用者

## <a name="active-user-in-usage-reports"></a>使用情況報告中的作用中使用者

Microsoft [365 使用方式分析](usage-analytics.md)的 microsoft 365 產品使用中使用者和系統[管理中心的活動報告](../activity-reports/activity-reports.md)定義如下。 
  
|**產品**|**作用中使用者定義**|**附註**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |已讀取或傳送電子郵件的任何使用者。  <br/> |未顯示任何行事曆資訊，這會新增接下來的更新中。  <br/> |
|SharePoint Online  <br/> |透過在任何網站上建立、修改、檢視、刪除、內外部共用或同步處理至用戶端以與檔案互動，或是檢視任何網站頁面的任何使用者。  <br/> |Microsoft 365 使用方式分析範本應用程式中的 SharePoint 線上作用中使用者度量，只會反映對 SharePoint 小組網站或群組網站進行檔案活動的使用者。 範本應用程式會更新，將定義同步處理為與系統管理中心的使用方式報告上的定義相同。  <br/> |
|商務用 OneDrive  <br/> |透過建立、修改、檢視、刪除、內外部共用或同步處理至用戶端以與檔案互動的任何使用者。  <br/> ||
|Yammer  <br/> |已在 Yammer 上讀取、張貼或喜歡訊息的任何使用者。  <br/> ||
|商務用 Skype  <br/> |已參與端對端工作階段 (包括即時傳訊、音訊和視訊通話、應用程式共用和檔案轉移) 或已主辦或參與會議的任何使用者。  <br/> ||
|Office  <br/> |在至少一個裝置上啟用其 Microsoft 365 Pro Plus、Visio Pro 或 Project Pro 訂閱的任何使用者。  <br/> ||
|Microsoft 365 群組  <br/> |任何有信箱活動的群組成員 (若有郵件已傳送至群組)。  <br/> |這種定義將會隨著群組網站檔案活動和 Yammer 群組活動（群組網站上的檔案活動，以及與群組相關聯之 Yammer 群組的郵件）的增強功能而增強。Microsoft 365 使用方式分析範本應用程式中目前無法使用此資料  <br/> |
|Microsoft Teams  <br/> |已參加聊天訊息、私人聊天訊息、通話、會議或其他活動的任何使用者。 其他活動是由使用者定義為其他小組活動的數目，其中包括（但不限於）：對郵件、應用程式、檔、搜尋、關注小組和頻道進行處理，並加以 favoriting。  <br/> ||
   
## <a name="adoption-metrics"></a>採用度量

[Microsoft 365 流量分析](usage-analytics.md)包含與使用中的使用者相關的其他採用量值，以顯示隨時間的產品採用方式。 在選取的月、年及產品中，這些計量值都是有效的，並且定義如下。 
  
|**度量**|**描述**|
|:-----|:-----|
|EnabledUsers  <br/> |在月份中啟用要使用產品的使用者人數。  <br/> |
|ActiveUsers  <br/> |在當月使用中的使用者人數。  <br/> |
|MoMReturningUsers  <br/> |在上月中也可以使用中的使用者人數。  <br/> |
|FirstTimeUsers  <br/> |先前從未使用此服務的月份中的使用者人數。  <br/> |
|CumulativeActiveUsers  <br/> |在當月內使用的使用者數目，以及上個月的數目。  <br/> |
|ActiveUsers （%）  <br/> |相對於該月份中啟用的使用者數目，以舍入為最接近第十個的使用者百分比。  <br/> |
|MoMReturningUsers （%）  <br/> |相對於作用中使用者數目，在上個月中也可以使用的使用者，四捨五入為最接近第十個的使用者百分比。  <br/> |
   
MoMReturningUsers、FirstTimeUsers、 &amp; CumulativeActiveUsers 已在包含 Microsoft 團隊的情況下，從2018年1月1日開始重設。
  
