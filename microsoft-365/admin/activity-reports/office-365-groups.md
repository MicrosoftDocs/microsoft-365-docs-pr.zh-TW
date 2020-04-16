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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: 取得「Microsoft 365 群組」報告，以瞭解群組及其活動。
ms.openlocfilehash: f1d1c333946f20ecfb76223d79a38e1a18783550
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/15/2020
ms.locfileid: "43516850"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Admin center 中的 microsoft 365 報告-Microsoft 365 群組

Microsoft 365**報告**儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。 在 [Microsoft 365 群組報告] 中，您可以深入瞭解組織中群組的活動，並查看已建立及使用的群組數目。
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。  
  
## <a name="how-to-get-to-the-groups-report"></a>如何取得群組報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取報告**] 下拉式清單中，選取 [ **Office 365** \> **群組活動**]。
  
## <a name="interpret-the-groups-report"></a>轉譯群組報告

您可以透過查看 [**群組** **]、[活動]、[** 檔案**Activity**] 和 [**儲存**] 圖表來查看群組的活動。 
  
![Microsoft 365 報告-群組活動](../../media/852027a4-8eab-47d1-b770-2bb874bdc403.png)
  
|||
|:-----|:-----|
|1.  <br/> |您可以針對過去7天、30天、90天或180天的趨勢，查看**Microsoft 365 群組**報告。 不過，如果您在報告中選取某一天，表格（7）將會從目前的日期顯示最多28天的資料（不是報告產生的日期）。  <br/> |
|2.  <br/> |每個報告中的資料通常會涵蓋過去24到48小時。  <br/> |
|3.  <br/> |[**群組**] 視圖會顯示在任何指定的日期存在的群組總數，以及該天的使用中的電子郵件交談、Yammer 文章和 SharePoint 檔案活動及 SharePoint 頁面] 中的使用中群組數目。  <br/> |
|4.  <br/> |**活動**視圖會顯示跨越群組工作負載的群組活動數目。 您可以依跨所有群組的群組信箱來檢視已接收的 Exchange 電子郵件，或是檢視報表期間任何日期的已接收 Exchange 電子郵件。 您也可以在與群組相關聯的 Yammer 群組中查看已張貼、讀取和贊的郵件。 <br/> |
|5.  <br/> |[**檔案**] 視圖會顯示與群組相關聯之所有群組網站的總數和作用中檔案數目。  <br/> |
|6.  <br/> |[**儲存**] 視圖會顯示所有群組信箱和群組網站上使用的總儲存空間。  <br/> |
|7.  <br/> | 在 [**群組**] 圖表上，Y 軸是群組數目（可以視為總與使用中的）。  <br/>  在 [**活動**] 圖表上，Y 軸是活動的群組執行次數。  <br/>  **在 [檔案**] 圖表上，Y 軸是指總數或使用中檔的數目。  <br/>  在 [**儲存空間**] 圖表上，Y 軸是群組信箱或網站所使用的儲存空間總數。  <br/>  這三個圖表上的 X 軸都代表該特定報告的已選取日期範圍。  <br/> |
|8.  <br/> |您可以選取圖例中的專案，以篩選您在圖表上看到的數列。 例如，在 [**群組**] 圖表中，選取 [**總** **] 或 [** ![使用中總數](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) ] 和 [使用中的群組數目]，以查看只與每一個相關聯的資訊。 變更此選取項目並不會變更格線資料表中的資訊。  <br/> |
|9.  <br/> | 所顯示的群組清單是在最長報告時間範圍 (180 天) 內的所有現有 (未被刪除的) 群組。活動計數 (電子郵件交談、Yammer 文章與 SharePoint 檔案活動) 會因日期選取範圍而有所不同。  <br/> 附注：您可能不會在欄中看到下列清單中的所有專案，直到您新增這些專案為止。<br/>**組名**是群組的名稱。  <br/> [**已刪除**] 是已刪除的群組數目。 如果群組已刪除，但報告期間此群組有活動，那麼它會出現在格線中並被標幟為 True。  <br/> **群組擁有**者是群組擁有者的名稱。  <br/> [**上次活動日期**] 是群組接收郵件的最後日期。 這是電子郵件交談、Yammer 或網站上發生之活動的上次日期。  <br/> **Type**為群組的類型。 這可以是私人群組或公開群組。  <br/> **Members**是群組中的成員數目。  <br/> **External members**是群組中的外部使用者數目。  <br/> **Exchange** <br/> [**接收的電子郵件**] 是群組接收的郵件數目。  <br/> [**信箱總數**] 是群組信箱中的總專案數。  <br/> **使用的信箱儲存**空間是群組信箱所使用的儲存空間。  <br/> **SharePoint 檔案** <br/> **Total files**是儲存在 SharePoint 群組網站中的檔案數目。  <br/> 「作用中檔案 **」是在報告期間進行處理**（查看或修改、同步處理、從內部或外部共用）的 SharePoint 群組網站中的檔案數目。  <br/> [已**使用的網站儲存量（mb）** ] 是報告期間所用的儲存量（以 MB 為單位）。  <br/> **Yammer 訊息** <br/> 「**張貼**」是在報表期間的 Yammer 群組中張貼的郵件數目。  <br/> **Read**是在報告期間，Yammer 群組中讀取之交談的數目。  <br/> 「**贊**」是透過報告期間的 Yammer 群組中所贊的郵件數目。  <br/>  如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。 請參閱[Microsoft 365 系統管理中心的活動報告中](activity-reports.md)的 [**我要如何隱藏使用者層級詳細資料？** ] 區段。  <br/> |
|十進位  <br/> |選取或點擊 [**其他動作**] [欄標題] 旁邊的 [ ![移動 OWA 其他動作](../../media/80044eef-2368-4c7e-8d31-7155b029e0cf.png) ]，以新增或移除報告中的欄。  <br/> ![群組報告-選擇欄](../../media/d7fb95d6-2a2e-4144-b80d-581223e48043.png)|
|第  <br/> |您也可以選取 [**匯出**] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。  <br/> |
|||
   

