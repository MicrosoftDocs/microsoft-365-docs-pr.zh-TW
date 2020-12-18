---
title: Admin center 中的 microsoft 365 報告-Microsoft 365 群組
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: 取得「Microsoft 365 群組」報告，以瞭解群組及其活動。
ms.openlocfilehash: 4a89f09f89e399905d0cb6927eca76c1242dfc62
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611903"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Admin center 中的 microsoft 365 報告-Microsoft 365 群組

Microsoft 365 **報告** 儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。 在 [Microsoft 365 群組報告] 中，您可以深入瞭解組織中群組的活動，並查看已建立及使用的群組數目。
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。  
  
## <a name="how-to-get-to-the-groups-report"></a>如何取得群組報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。 
2. 在 [儀表板] 主頁上，按一下 [作用中的使用者-Microsoft 365 應用程式] 或 [作用中使用者]-Microsoft 365 服務卡片上的 [ **View more** ] 按鈕，以取得 Office 365 報告頁面。
  
## <a name="interpret-the-groups-report"></a>轉譯群組報告

您可以選擇 [群組] [ **活動** ] 索引標籤，在 Office 365 報告中查看啟用。<br/>![Microsoft 365 報告-Microsoft Office 365 群組活動。](../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png)

選取 **[選擇欄位** ]，以新增或移除報告中的欄。  <br/> ![Office 365 群組活動報告-選擇欄](../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png)

您也可以選取 [ **匯出** ] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。 

|項目|描述|
|:-----|:-----|
|**計量**|**定義**|
|群組名稱  <br/> |群組的名稱。  <br/> |
|刪除  <br/> |已刪除的群組數目。 如果群組已刪除，但報告期間此群組有活動，那麼它會出現在格線中並被標幟為 True。  <br/> |
|群組擁有者  <br/> |群組擁有者的名稱。  <br/> |
|上次活動日期 (UTC)   <br/> |最近一天群組收到郵件的日期。 這是電子郵件交談、Yammer 或網站上發生之活動的上次日期。  <br/> |
|類型  <br/> |群組的類型。 這可以是私人群組或公開群組。  <br/> |
|Exchange 中收到的電子郵件  <br/> |群組接收的郵件數目。|
|Exchange 中的電子郵件 (總計)   <br/> |群組信箱中的總專案數。  <br/> |
|Exchange (MB) 所用的信箱儲存空間  <br/> |群組信箱所使用的儲存空間。 <br/>|
|SharePoint 檔案 (總計)   <br/> |儲存在 SharePoint 群組網站中的檔案數目。  <br/> |
| (使用中) 的 SharePoint 檔案  <br/> |在報告期間內 (查看或修改、同步處理、內部或外部共用) 的 SharePoint 群組網站中的檔案數目。  <br/> |
|用於 SharePoint (MB 的網站總儲存量)   <br/> |報告期間使用的儲存空間（MB）。  <br/> |
|Yammer 中的郵件 (發表)   <br/> |在報告期間內，在 Yammer 群組中張貼的郵件數目。  <br/> |
|Yammer 中的郵件 (讀取)   <br/> |在報告期間，Yammer 群組中讀取的交談數目。  <br/> |
|Yammer 中的郵件 (贊)   <br/> |在報告期間，Yammer 群組中所贊的郵件數目。  <br/> |
|成員  <br/> |群組中的成員數目。  <br/> |
|外部成員 |群組中的外部使用者數目。|
|||