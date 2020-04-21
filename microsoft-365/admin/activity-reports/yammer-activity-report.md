---
title: Admin center 中的 Microsoft 365 報告-Yammer 活動報告
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
- MET150
- MOE150
ms.assetid: c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a
description: 取得 Yammer 活動報告，並深入瞭解使用 Yammer 發佈、贊或讀取郵件的使用者人數。
ms.openlocfilehash: bd128e17b8d435b8d5c6b06f16ff37fea11a6ce3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43618953"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Admin center 中的 Microsoft 365 報告-Yammer 活動報告

如 Microsoft 365 admin，「**報告**」儀表板會顯示您組織內產品使用狀況的資料。 請參閱系統[管理中心的活動報告](activity-reports.md)。 透過**Yammer 活動報告**，您可以查看使用 yammer 發佈的獨特使用者人數，例如或讀取郵件，以及整個組織產生的活動數量，以瞭解您的組織對 yammer 的參與程度。 
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。 
 
## <a name="how-to-get-to-the-yammer-activity-report"></a>如何取得 Yammer 活動報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取報告**] 下拉式清單中，選取 [ **Yammer** \> **活動**]。
  
## <a name="interpret-the-yammer-activity-report"></a>解讀 Yammer 活動報告

您可以查看 [活動] 和 [使用者] 圖表以了解使用者的 Yammer 活動。
  
![Yammer 活動報告](../../media/92e8b2c6-166a-4154-9824-3fb6bbedf0db.JPG)
  
活動報告中包含下列資訊。
  
- 使用 [日] 索引標籤，查看過去7天、30天、90天或180天的**Yammer 活動**報告趨勢。 不過，如果您選取報告中的特定一天，表格會顯示從目前日期的28天內的資料（並非報告產生的日期）。 
    
- 每份報告都具有報告產生時的日期。 報告反映出的資料通常會有 24 至 48 小時的延遲 (自活動時間起算)。
    
- 您可以查看 [**活動**] 圖表，以瞭解組織中的 Yammer 活動的數量趨勢。 您可以了解張貼訊息、閱讀訊息及對訊息按讚的個別數據。 
    
    ![Yammer 活動報告中的即時檢視](../../media/76983516-2c5f-43a1-a5e3-c414e9f17638.JPG)
  
  - 在 [**活動**] 圖表上，Y 軸是已張貼、讀取或贊的郵件活動計數。 
    
- 您可以查看 [**使用者**] 圖表，以瞭解正在產生 Yammer 活動之唯一使用者的數量趨勢。 您可以查看使用者張貼、閱讀或對 Yammer 訊息按讚的趨勢。 
    
    ![Yammer 活動報告中的使用者視圖](../../media/b1098162-7b79-430f-bfe4-9d3957d56885.JPG)
  
  - 在 [**使用者**] 活動圖表中，Y 軸是使用者張貼、讀取或贊 Yammer 訊息。 
    
  - 這兩份圖表的 X 軸都代表該特定報告的已選取日期範圍。
    
- 您可以選取圖例中的專案，以篩選您在圖表上看到的數列。 例如，在 [**活動**] 圖表上，選取 [**已張貼**]、[已**閱讀**] 或 [**贊**]，只查看與各項相關的資訊。 
    
    ![已張貼、讀取和贊的選項](../../media/8b832afc-415c-409b-816f-cb02b7a71e69.png)
  
    變更此選取項目並不會變更格線表格中的資訊。
    
- 圖表底下的表格顯示每個使用者層級的 Yammer 活動明細。
    
    您可以使用功能表來篩選和排序資料。
    
    ![Yammer 報告的功能表選項](../../media/9d32240c-f1ff-400b-9c4e-a21b48651530.JPG)
  
    您也可以新增和移除欄位。 可用的欄位如下︰
    
  - [使用者**名稱**] 是使用者的電子郵件地址。 您可以顯示實際的名稱，也可以讓此欄位匿名。 
    
    這個格線會顯示使用 Microsoft 365 帳戶登入 Yammer 的使用者，或使用單一登入登入網路的使用者。
    
  - [**顯示名稱**] 是使用者的完整名稱。 您可以顯示實際的名稱，也可以讓此欄位匿名。 
    
  - **使用者狀態**為三個值之一：已啟動、已刪除或已暫停。 
    
    這些報告顯示作用中、已停權及已刪除的使用者。報告不會反映出擱置中使用者，因為擱置中的使用者不能張貼訊息、閱讀訊息或對訊息按讚。
    
  - **[狀態變更日期（UTC）** ] 是在 Yammer 中變更使用者狀態的日期。 
    
  - [**上次活動日期（UTC）** ] 是指使用者投遞、讀取或贊郵件的最後日期。 
    
  - **已發佈**是使用者在您指定的期間內投遞的郵件數目。 
    
  - **Read**是使用者在您指定的時段內讀取的交談數目。 
    
  - **贊**是使用者在您指定的期間內按贊的郵件數目。 
    
  - 「已**指派產品**」是指派給此使用者的產品。 
    
    如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。 請參閱[Microsoft 365 系統管理中心的活動報告中](activity-reports.md)的 [**我要如何隱藏使用者層級詳細資料？** ] 區段。
    
- 您也可以選取 [**匯出**] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。 
    
## <a name="what-data-is-in-these-reports"></a>這些報告中有哪些資料？

- **所有用戶端**這些報告會匯總所有用戶端上的資料，包括在瀏覽器中或在 iOS 或 Android 應用程式上使用 Yammer。 
    
- **無外部網路資料**這些報告中不包含外部網路資料。 
    
- **啟用的網路**這些報告會顯示屬於 Microsoft 365 訂閱之 Yammer 網路的資料。 圖表會匯總登入 Yammer 網路之所有使用者的使用狀況，不論他們使用的是 Microsoft 365 或 Yammer 登入。 
    

