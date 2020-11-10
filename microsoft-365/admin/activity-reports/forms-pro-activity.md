---
title: 系統管理中心的 Microsoft 365 報告-Dynamics 365 客戶語音活動
ms.author: sirkkuw
author: sirkkuw
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
description: 瞭解如何使用 Microsoft 365 系統管理中心的 [Microsoft 365 報告] 儀表板，取得 Microsoft Dynamics 365 客戶語音活動報告。
ms.openlocfilehash: de03067197c80634f02318b35a79eb84e33c4b86
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988549"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>系統管理中心的 Microsoft 365 報告-Dynamics 365 客戶語音活動

Microsoft 365 **報告** 儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。
  
例如，您可以查看每位授權使用 Microsoft Dynamics 365 客戶心聲的使用者活動，方法是查看其與 Dynamics 365 客戶心聲的互動。 它也可協助您瞭解所建立的專業人員調查的數目，以及使用者回應的 Pro 調查，以瞭解共同作業的程度。 
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>如何取得 Forms Pro 活動報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [ **選取報告** ] 下拉式清單中，選取 [ **Dynamics 365 Customer Voice** \> **activity** ]。

## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>解讀 Dynamics 365 客戶語音活動報告

您可以查看 [ **活動** ] 和 [ **使用者** ] 圖表，以取得使用者的 Dynamics 365 客戶語音活動。 

![表單活動報告](../../media/formsproactivity.png)

|項目|描述|
|:-----|:-----|
|1.  <br/> |您可以針對過去7天、30天、90天或180天的趨勢，查看 **Dynamics 365 客戶語音** 活動報告。 不過，如果您在報告中選取某一天，則 table (7) 會從目前的日期顯示最多28天的資料， (不是) 產生報表的日期。   <br/> |
|2.  <br/> |每個報告中的資料通常是最近的48小時。  <br/> |
|3.  <br/> |[ **使用者** ] 視圖可協助您瞭解活躍 Dynamics 365 客戶語音使用者數目的趨勢。 如果使用者已在特定期間內，在專業調查 (建立、編輯、查看等 ) 中執行活動，就會視為作用中的使用者。  <br/> |
|4.  <br/> |[ **活動** ] 視圖可協助您瞭解作用中使用者數目的趨勢。 使用者在指定的期間內若曾經執行過檔案活動 (儲存、同步處理、修改或共用) 或瀏覽過頁面，就會被視為作用中使用者。<br/> 附注：一項調查的活動可能會發生多次，但是只會算作一個作用中的調查。 例如，您可以建立一個專業人員調查，並在指定的期間內繼續編輯同一項調查，它只會算作一個單一調查。 <br>|
|5.<br/>|在 [ **使用者** ] 圖表上，Y 軸是唯一使用者的數目。 X 座標軸是唯一使用中使用者的日期。 圖例如下：<br/><br/>**設計者** 表示使用者已建立或編輯 Dynamics 365 客戶語音調查。<br><br>在 [ **活動** ] 圖表上，Y 軸是每個調查的 Dynamics 365 客戶語音回應計數。 X 座標軸是指調查或回應活動發生的日期。 圖例如下：<br/><br/>所 **建立的調查** 是使用者已建立的唯一 Dynamics 365 客戶語音調查計數。<br>**回應** 是接收調查之使用者已提交之匿名或非匿名回應的計數。 |
|6.<br/>|您可以選取圖例中的專案，以篩選您在圖表上看到的數列。 例如，在 [使用者] 圖表上，選取 [設計者]、[回應者] 或 [總計使用者]，以查看只與各項相關的資訊。 變更此選取專案並不會變更下方格線表格中的資訊。|
|7.<br/>|下表顯示每個使用者層級的活動明細。 圖例如下：<br/><br/>**Username** 是在 Microsoft Forms 上執行活動之使用者的電子郵件地址。<br/>[ **上次活動日期 (UTC)** 是使用者為選取的日期範圍執行表單活動的最晚日期。 若要查看特定日期發生的活動，請直接選取圖表中的日期。<br/>這會篩選表格，僅針對在該特定日執行活動的使用者，顯示檔活動資料。<br/><br/>[已 **建立的問卷調查數目** ] 是使用者建立的調查數目。<br/> [ **調查回應數目** ] 是調查已配送至的回應者回應數目。|
|8.<br/>|選取 [ **管理欄** ] 圖示，以新增或移除報告中的欄。|
|9.<br/>|您也可以選取 [ **匯出** ] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的匯總、排序及篩選，以進行進一步的分析。 如果您的使用者少於100，您可以在報表本身的資料表中進行排序和篩選。 如果您有超過100的使用者，為了進行篩選和排序，您將需要匯出資料。|