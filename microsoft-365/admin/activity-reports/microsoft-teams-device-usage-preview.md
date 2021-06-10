---
title: Microsoft 365admin center 中的報告-Microsoft Teams 裝置使用量
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 透過從 Microsoft 365 報告取得 Microsoft Teams 應用程式使用方式報告，深入瞭解組織中所使用的 Microsoft Teams 應用程式。
ms.openlocfilehash: 096954ad246f3b10369dfbf683d04b6c81950b5e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579635"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Microsoft 365admin center 中的報告-Microsoft Teams 裝置使用量

[Microsoft 365 **報告**] 儀表板會顯示您組織中產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。 在 Microsoft Teams App 使用情況報告，您能夠深入了解組織中的 Microsoft Teams App 使用情形。
  
> [!NOTE]
> 您必須是全域系統管理員、全域讀取者或報告讀取者 Microsoft 365 或 Exchange、SharePoint、Teams 服務、Teams 通訊或商務用 Skype 管理員查看報告。  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>如何取得 Microsoft Teams App 使用情況報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。 
2. 在 [儀表板] 主頁上，按一下 [Microsoft Teams 活動卡片上的 [ **View more** ] 按鈕。
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>解讀 Microsoft Teams App 使用情況報告

您可以選擇 [**裝置使用狀況**] 索引標籤，在 Teams 報告中查看裝置使用方式。<br/>![Microsoft 365 報告-Microsoft Teams 裝置使用量。](../../media/e46c7f7c-8371-4a20-ae82-b20df64b0205.png)

選取 **[選擇欄位** ]，以新增或移除報告中的欄。  <br/> ![Teams 使用者裝置報告-選擇欄](../../media/3358d5d9-931b-4d30-931f-450b2f5717da.png)

您也可以選取 [**匯出**] 連結，將報表資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。 

您可以針對過去7天、30天、90天或180天的趨勢，查看 **Microsoft Teams 裝置使用狀況** 報告。 不過，如果您在報告中選取某一天，則 table (7) 會從目前的日期顯示最多28天的資料， (不是) 產生報表的日期。
  
|項目|描述|
|:-----|:-----|
|**計量**|**定義**|
|使用者名稱  <br/> |使用者的顯示名稱。  <br/> |
|Windows  <br/> |如果使用者是在 Windows 型電腦上的 Teams 桌面用戶端中使用中，則為選取狀態。  <br/> |
|Mac  <br/> |如果使用者是在 macOS 電腦上的 Teams 桌面用戶端中使用中，則為選取狀態。  <br/> |
|iOS  <br/> |如果使用者在 iOS 的 Teams 行動用戶端上為使用中狀態，則會選取此選項。  <br/> |
|Android 手機  <br/> | 如果使用者在適用于 Android 的 Teams 行動用戶端上使用，則會選取此選項。  <br/> |
|Chrome 作業系統  <br/> |如果使用者是在 ChromeOS 電腦上的 Teams 桌面用戶端中使用中，則為選取狀態。|
|Linux  <br/> | 如果使用者是在 Linux 電腦上的 Teams 桌面用戶端中使用中，則為選取狀態。  <br/> |
|網頁版  <br/> |如果使用者是在裝置上的 Teams 網頁用戶端中使用中，則為選取狀態。|
|上次活動日期 (UTC)   <br/> |使用者參與 Teams 活動的最後一個日期 (UTC) 。  <br/> |
|已授權|如果使用者授權使用 Teams，則選取此選項。|
|||