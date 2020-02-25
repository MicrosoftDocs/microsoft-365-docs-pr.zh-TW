---
title: 管理中心-Yammer 群組活動報告中的 office 365 報告
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
ms.assetid: 94dd92ec-ea73-43c6-b51f-2a11fd78aa31
description: 取得 Yammer 群組活動報告，以了解 Yammer 群組成為建立及用於您的組織，以及他們的活動數目。
ms.openlocfilehash: 436387a7476a62293107e1a22d6fc15287d4faf0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239439"
---
# <a name="office-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>管理中心-Yammer 群組活動報告中的 office 365 報告

在 Office 365**報告**儀表板顯示您的活動概觀跨組織中的產品。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。 在 Yammer 群組活動報告中，您能夠深入了解組織中的 Yammer 群組活動情形，並查看已建立和使用中的 Yammer 群組數量。
  
> [!NOTE]
> 您必須是全域系統管理員、 全域讀者或報告讀取者，在 Microsoft 365 或 Exchange、 SharePoint 或 Skype 商務系統管理員，才能查看報告。 

## <a name="how-to-get-to-the-yammer-groups-activity-report"></a>如何查看 Yammer 群組活動報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取 [報告]** 下拉式清單，選取 [ **Yammer** \> **群組活動**。
  
## <a name="interpret-the-yammer-groups-activity-report"></a>解讀 Yammer 群組活動報告

您可以透過檢視 Yammer 群組活動查看 [**群組**] 和 [**活動**圖表。<br/>![Yammer groups activity chart](../media/4ba4ea03-2f74-4d86-8c63-2b18477c9769.png)
  
|||
|:-----|:-----|
|1.  <br/> |[ **Yammer 群組活動**] 報告可檢視的趨勢，過去 7 天、 30 天、 前 90 天或 180 天。 不過，如果您在報表中選取的特定一天，表格 (7) 將會顯示資料 28 天，從目前的日期 （不是該報告產生的日期）。  <br/> |
|2.  <br/> |每個報告中的資料通常涵蓋的最後一個 24 到 48 小時。 <br/> |
|3.  <br/> |[**群組**] 檢視會顯示總數之群組的存在，而且多少執行群組交談活動。  <br/> |
|4.  <br/> |[**活動**] 檢視會顯示您的數字的 Yammer 訊息張貼、 讀取、 和按讚群組中。  <br/> |
|5.  <br/> | 在 [**群組**] 圖表中，Y 軸是總數或作用中的群組數目。  <br/>  在 [**活動**] 圖表中，Y 軸是指定 Yammer 群組活動的計數。  <br/>  這三個圖表上的 X 軸都代表該特定報告的已選取日期範圍。  <br/> |
|6.  <br/> |您可以篩選看圖表所選取項目在圖例中的數列。 例如，在 [**群組**] 圖表中，選取 [**總數**或**作用中**  ![總數和作用中的圖示](../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png)以查看只與其個別相關的資訊。 變更此選取項目並不會變更格線資料表中的資訊。  <br/> |
|7.  <br/> | 所顯示的群組清單是在最長報告時間範圍 (180 天) 內的所有現有 (未被刪除的) 群組。活動的數量 (收到的訊息數) 會因日期選取範圍而有所不同。  <br/> 附註： 您可能不會看到下方清單中的資料行中的所有項目直到您新增那些。<br/>**群組名稱**是群組的名稱。  <br/> **群組系統管理員**是群組系統管理員或擁有者的名稱。  <br/> **刪除的郵件**] 是已刪除的 Yammer 群組數目。 如果群組已刪除，但報告期間此群組有活動，那麼它會出現在格線中並被標幟為 True。  <br/> **類型**是群組、 公用或私人的類型。  <br/> **已連線至 Office 365**指出 Yammer 群組是否也是 Office 365 群組。  <br/> **[上次活動日期**是一則訊息已讀取、 張貼或按讚的群組的最晚日期。  <br/> **成員**] 是群組的成員數目。  <br/> **「 已張貼**是在報告期間 Yammer 群組中張貼的訊息數目。  <br/> **讀取**是在報告期間 Yammer 群組中讀取的交談數目。  <br/> **Liked**是在報告期間 Yammer 群組中按讚的訊息數目。  <br/>  如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。 請參閱**如何隱藏使用者層級的詳細資訊？** [在 Microsoft 365 系統管理中心的活動報告](activity-reports.md)中的一節。  <br/> |
|8.  <br/> |選取要新增或移除報告中的資料行的**資料行**。  <br/> ![Yammer groups activity - choose columns](../media/31bd549b-363d-4888-a45d-7af6fedb3588.png)|
|9.  <br/> |您可以也報告資料匯出到 Excel.csv 檔案，藉由選取 [**匯出**] 連結。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。  <br/> |
|||
   

