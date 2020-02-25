---
title: 在系統管理中心-Yammer 裝置使用量報告的 Microsoft 365 報告
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
ms.assetid: b793ffdd-effa-43d0-849a-b1ca2e899f38
description: '取得要知道哪些裝置關於您的使用者使用 Yammer 上的 [Yammer 裝置使用量] 報告。 '
ms.openlocfilehash: 5202fd2ebe3e99182ecf7cd2d9bee77be0573cde
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239450"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>在系統管理中心-Yammer 裝置使用量報告的 Microsoft 365 報告

Microsoft 365**報告**儀表板顯示您的活動概觀跨組織中的產品。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。
  
Yammer 裝置使用量報告提供您的使用者在哪些裝置上使用 Yammer 的資訊。您可以依裝置類型檢視每日使用者數量和使用者數量。您可以在所選時間範圍內檢視這兩者。您也可以檢視每個使用者的詳細資料。
  
> [!NOTE]
> 您必須是全域系統管理員、 全域讀者或報告讀取者，在 Microsoft 365 或 Exchange、 SharePoint 或 Skype 商務系統管理員，才能查看報告。 
  
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>如何取得 Yammer 裝置使用量報告？

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取 [報告]** 下拉式清單，選取 [ **Yammer** \> **裝置使用量**。
  
## <a name="interpret-the-yammer-activity-report"></a>解讀 Yammer 活動報告

您可以透過檢視使用者的 Yammer 裝置使用量查看 [**使用者**] 和 [**通訊**圖表。 
  
裝置使用量報告中包含下列資訊。
  
- 若要檢視過去 7 天、 30 天、 前 90 天或 180 天的**Yammer 裝置使用量**活動] 趨勢報告使用天數索引標籤。 不過，如果您在報表中選取的特定一天，表格會顯示資料 28 天，從目前的日期 （不是該報告產生的日期）。 
    
- 每份報告都具有報告產生時的日期。 報告反映出的資料通常會有 24 至 48 小時的延遲 (自活動時間起算)。
    
- 您可以檢視 [**使用者**] 圖表以查看依裝置類型的每日使用者數量。<br/>![Yammer 裝置使用量圖表中的 [使用者] 檢視](../media/ecfba1ec-fbea-4491-88da-1fb19b4d5629.png)<br/>![Yammer 裝置使用量報告顯示 [使用者] 檢視](../media/f396865a-ad6e-4f8b-a145-cc3865b352f4.png)
  
- 您可以檢視**通訊群組**] 圖表以查看依裝置類型的使用者數目。<br/>![Yammer 裝置使用量報告中的 [通訊群組] 檢視](../media/7a0b152e-2d2b-4d23-8dc2-046be53b724f.png)<br/>![Yammer 裝置使用報告](../media/780c351d-7a1d-451d-8c16-4c454ef58aa8.png)
  
- 圖表底下的 [**詳細資料**] 表格顯示每個使用者層級的 Yammer 裝置使用量明細。 
    
    您也可以新增和移除欄位。 可用的欄位如下︰
    
  - **Username**是使用者的電子郵件地址。 您可以顯示實際的名稱，也可以讓此欄位匿名。 
    
    此格線會顯示的使用者登入 Yammer 使用 Microsoft 365 帳戶，或使用者登入網路使用單一登入。
    
  - **顯示名稱**是使用者的完整名稱。 您可以顯示實際的名稱，也可以讓此欄位匿名。 
    
  - **使用者狀態**是三個值之一： 作用中]、 [已刪除] 或 [已擱置。 
    
    這些報告顯示作用中、已停權及已刪除的使用者。報告不會反映出擱置中使用者，因為擱置中的使用者不能張貼訊息、閱讀訊息或對訊息按讚。
    
  - **Web**指出使用者是否曾在 web 上使用 Yammer。 
    
  - **Windows phone**指出使用者是否曾在 Windows phone 上使用 Yammer 
    
  - **Android 手機**指出使用者是否曾在 Android 手機上使用 Yammer。 
    
  - **iPhone**指出使用者是否曾在 iPhone 上使用 Yammer。 
    
  - **iPad**指出使用者是否曾在 iPad 上使用 Yammer。 
    
  - **其他**會指出使用者是否有不先前所列的其他裝置上使用 Yammer。 
    
    如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。 請參閱**如何隱藏使用者層級的詳細資訊？** ] 區段中[的 Microsoft 365 系統管理中心的活動報告](activity-reports.md)中。
    
- 您可以也報告資料匯出到 Excel.csv 檔案，藉由選取 [**匯出**] 連結。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。 
    

