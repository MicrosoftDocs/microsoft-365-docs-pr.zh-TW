---
title: Microsoft 365系統管理中心報告-Yammer 裝置使用方式報告
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- MST160
- MET150
- MOE150
description: 取得 Yammer 裝置使用方式報告，以瞭解您的使用者在哪個裝置上使用 Yammer。
ms.openlocfilehash: 817627cac791d35f49cd240ceb48de15ef328ef8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241841"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Microsoft 365系統管理中心報告-Yammer 裝置使用方式報告

[Microsoft 365 **報告**] 儀表板會顯示您組織中產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。
  
Yammer 裝置使用量報告提供您的使用者在哪些裝置上使用 Yammer 的資訊。您可以依裝置類型檢視每日使用者數量和使用者數量。您可以在所選時間範圍內檢視這兩者。您也可以檢視每個使用者的詳細資料。
  
> [!NOTE]
> 您必須是全域系統管理員、全域讀取者或報告讀取者 Microsoft 365 或 Exchange、SharePoint、Teams 服務、Teams 通訊或商務用 Skype 管理員查看報告。  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>如何取得 Yammer 裝置使用量報告？

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。 
2. 在 [儀表板] 主頁上，按一下 [Yammer 卡片上的 [ **View more** ] 按鈕。
  
## <a name="interpret-the-yammer-device-usage-report"></a>解讀 Yammer 裝置使用方式報告

您可以選擇 [**裝置使用狀況**] 索引標籤，在 OneDrive 報告中查看使用狀況。<br/>![Microsoft 365 報告-Microsoft Yammer 裝置使用狀況報告。](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

選取 **[選擇欄位** ]，以新增或移除報告中的欄。  <br/> ![Yammer 裝置使用方式報告-選擇欄](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

您也可以選取 [**匯出**] 連結，將報表資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。 
  
|項目|描述|
|:-----|:-----|
|**計量**|**定義**|
|使用者名稱  <br/> |使用者的電子郵件地址。 您可以顯示實際的名稱，也可以讓此欄位匿名。 這個格線會顯示使用 Microsoft 365 帳戶登入 Yammer 的使用者，或使用單一登入登入網路的使用者。 <br/> |
|顯示名稱  <br/> |使用者的完整名稱。 您可以顯示實際的名稱，也可以讓此欄位匿名。  <br/> |
|使用者狀態  <br/> |三個值之一： [作用中]、[已刪除] 或 [已擱置]。 這些報告顯示作用中、已停權及已刪除的使用者。 報告不會反映出擱置中使用者，因為擱置中的使用者不能張貼訊息、閱讀訊息或對訊息按讚。   <br/> |
|狀態變更日期 (UTC)   <br/> |在 Yammer 中變更使用者狀態的日期。  <br/> |
|上次活動日期 (UTC)   <br/> |使用者參與 Yammer 活動的最後一個日期 (UTC) 。  <br/> |
|網頁版  <br/> |會指出使用者是否已在網頁上使用 Yammer。  <br/> |
|Windows 電話  <br/> | 會指出使用者是否已在 Windows 電話上使用 Yammer。  <br/> |
|Android 手機  <br/> |會指出使用者是否已在 Android 手機上使用 Yammer。 <br/>|
|Iphone <br/> | 會指出使用者是否已在 iPhone 上使用 Yammer。  <br/> |
|Ipad  <br/> |會指出使用者是否已在 iPad 上使用 Yammer。 <br/>|
|其他  <br/> |會指出使用者是否已在另一個裝置上使用 Yammer，但先前並未列出。 <br/>|
|||