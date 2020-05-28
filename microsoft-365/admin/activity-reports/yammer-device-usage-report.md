---
title: Admin center 中的 Microsoft 365 報告-Yammer 裝置使用方式報告
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
ms.assetid: b793ffdd-effa-43d0-849a-b1ca2e899f38
description: '取得 Yammer 裝置使用方式報告，以瞭解您的使用者在使用 Yammer 的裝置。 '
ms.openlocfilehash: 17fcf6c7d46988f0783b5097d3381b9bc08cbbe7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387450"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Admin center 中的 Microsoft 365 報告-Yammer 裝置使用方式報告

Microsoft 365**報告**儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。
  
Yammer 裝置使用量報告提供您的使用者在哪些裝置上使用 Yammer 的資訊。您可以依裝置類型檢視每日使用者數量和使用者數量。您可以在所選時間範圍內檢視這兩者。您也可以檢視每個使用者的詳細資料。
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。 
  
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>如何取得 Yammer 裝置使用量報告？

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取報告**] 下拉式清單中，選取 [ **Yammer** \> **裝置使用狀況**]。
  
## <a name="interpret-the-yammer-activity-report"></a>解讀 Yammer 活動報告

您可以查看 [**使用者**] 和 [**通訊**群組] 圖表，以瞭解使用者的 Yammer 裝置使用狀況。 
  
裝置使用量報告中包含下列資訊。
  
- 使用 [日] 索引標籤，查看過去7天、30天、90天或180天的**Yammer 裝置使用狀況**活動報告趨勢。 不過，如果您選取報告中的特定一天，表格會顯示從目前日期的28天內的資料（並非報告產生的日期）。 
    
- 每份報告都具有報告產生時的日期。 報告反映出的資料通常會有 24 至 48 小時的延遲 (自活動時間起算)。
    
- 您可以查看 [**使用者**] 圖表，依裝置類型查看每日使用者數目。<br/>![Yammer 裝置使用狀況圖表中的使用者視圖](../../media/ecfba1ec-fbea-4491-88da-1fb19b4d5629.png)<br/>![顯示使用者 view 的 Yammer 裝置使用方式報告](../../media/f396865a-ad6e-4f8b-a145-cc3865b352f4.png)
  
- 您可以透過裝置類型查看**分配**圖表以查看使用者數目。<br/>![Yammer 裝置使用方式報告中的通訊視圖](../../media/7a0b152e-2d2b-4d23-8dc2-046be53b724f.png)<br/>![Yammer 裝置使用報告](../../media/780c351d-7a1d-451d-8c16-4c454ef58aa8.png)
  
- 圖表底下的 [**詳細資料**] 表格顯示每個使用者層級的 Yammer 裝置使用量明細。 
    
    您也可以新增和移除欄位。 可用的欄位如下︰
    
  - [使用者**名稱**] 是使用者的電子郵件地址。 您可以顯示實際的名稱，也可以讓此欄位匿名。 
    
    這個格線會顯示使用 Microsoft 365 帳戶登入 Yammer 的使用者，或使用單一登入登入網路的使用者。
    
  - [**顯示名稱**] 是使用者的完整名稱。 您可以顯示實際的名稱，也可以讓此欄位匿名。 
    
  - **使用者狀態**是三個值之一： [作用中]、[已刪除] 或 [已擱置]。 
    
    這些報告顯示作用中、已停權及已刪除的使用者。報告不會反映出擱置中使用者，因為擱置中的使用者不能張貼訊息、閱讀訊息或對訊息按讚。
    
  - **Web**會指出使用者是否已在網頁上使用 Yammer。 
    
  - **Windows phone**會指出使用者是否已在 Windows phone 上使用 Yammer 
    
  - **Android 手機**會指出使用者是否已在 Android 手機上使用 Yammer。 
    
  - **iphone**會指出使用者是否已在 iPhone 上使用 Yammer。 
    
  - **ipad**會指出使用者是否已在 iPad 上使用 Yammer。 
    
  - **其他**表示使用者是否已在另一個裝置上使用 Yammer，但先前並未列出。 
    
    如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。 請參閱[Microsoft 365 系統管理中心的活動報告中](activity-reports.md)的 [**我要如何隱藏使用者層級詳細資料？** ] 區段。
    
- 您也可以選取 [**匯出**] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。 
    

