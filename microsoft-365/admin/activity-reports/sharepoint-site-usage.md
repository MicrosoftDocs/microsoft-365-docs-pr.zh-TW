---
title: 系統管理中心的 Microsoft 365 報告-SharePoint 網站使用狀況
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
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
- SPO160
- BSA160
ms.assetid: 4ecfb843-e5d5-464d-8bf6-7ed512a9b213
description: '取得「SharePoint 網站使用量」報告，瞭解使用者在 SharePoint 網站中儲存的檔案數目、使用的數目，以及使用的總儲存空間。 '
ms.openlocfilehash: 7da72dccb4a90ed204ffa785040b1968ac70feb3
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688202"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>系統管理中心的 Microsoft 365 報告-SharePoint 網站使用狀況

做為 Microsoft 365 系統管理員，[ **報告** ] 儀表板會顯示您組織中各種產品的活動概況。 此功能可讓您更深入解析各項產品的特定活動。 例如，您可以從 SharePoint 中取得您所取得之價值的高層級視圖、使用者儲存在 SharePoint 網站中的檔案總數、使用的檔案數目，以及所有這些網站所使用的儲存空間。 然後，您可以深入查看「SharePoint 網站流量」報告，以瞭解所有網站的趨勢及每個網站層級的詳細資料。 
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。
在系統管理中心的 Microsoft 365 報告不支援 GCC 高和 DoD 承租人。
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>如何取得 SharePoint 網站使用狀況報告

1. 在系統管理中心中，移至 [ **報表** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用量</a>]。
    
2. 在 [ **SharePoint** 檔案] 底下，按一下 [ **查看更多**]。 

3. 在 [ **SharePoint 活動**] 旁邊，按一下向下箭號以開啟功能表。

4. 選取 [ **SharePoint** \> **網站使用量**]。
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>解讀 SharePoint 網站使用狀況報告

![SharePoint 網站使用量報告](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|項目|描述|
|:-----|:-----|
|1.  <br/> |您可以針對過去7天、30天、90天或180天的趨勢，查看 **SharePoint 網站使用狀況** 報告。 不過，如果您在報告中選取某一天，則 table (7) 會從目前的日期顯示最多28天的資料， (不是) 產生報表的日期。  <br/> |
|2.  <br/> |每個報告中的資料通常會涵蓋過去24到48小時。 <br/> |
|3.  <br/> |[ **網站** ] 圖表會顯示總數和作用中的網站數目，包括任何使用者已查看、修改、上傳、下載、共用或同步處理檔案，或在報告期間中查看頁面的網站。  <br/> |
|4.  <br/> |[ **檔案** ] 圖表會顯示所有網站上的檔案總數和使用中檔案數目。 檔總數包含使用者檔案和系統檔案。 使用中的檔案指的是在指定時間週期中曾經儲存、同步處理、修改或共用過的檔案。|
|5.  <br/> |[ **儲存空間** ] 圖表會顯示報告期間所分攤及消耗的儲存趨勢。  <br/> |
|6.  <br/> |[ **頁面** ] 圖表會顯示在所有網站上查看的頁面數目。  <br/> |
|7.  <br/> |您可以透過選取圖例中的專案來篩選所看到的圖表。 例如， **在 [檔案** ] 圖表上， **選取 [** 檔案] 或 [作用中 **檔**]。 在 [ **網站** ] 圖表中，您可以選取 [ **網站總數** ] 或 [使用中 **網站**]。 在 [ **儲存** 空間] 圖表上，您可以選取 [已 **分配儲存** ] 或 [ **儲存空間]。** 變更此選取項目並不會變更格線表格中的資訊。  <br/> |
|8.  <br/> | 表格顯示每個網站層級的活動明細。  <br/> ![使用狀況報告的欄選項](../../media/sharepointsite-usage.png)           <br/> **網站 url** 是網站的完整 URL。  <br/> 「**已刪除**」是網站的刪除狀態。 網站標示為已刪除至少需要7天。  <br/> **網站擁有** 者是網站主要擁有人的使用者名稱。  <br/>**網站擁有者主要名稱** 是網站擁有者的電子郵件地址。  <br/> **上次活動日期 (UTC)** 是指偵測到的最後一次檔案活動的日期，或在網站上查看頁面的日期。  <br/> **Files** 是網站上的檔數目。  <br/> [使用中檔案 **] 是網站** 上的使用中檔案數目。<br/> 附注：如果在報告的指定期間內已移除檔案，則報告中顯示的使用中檔數目可能會大於目前網站上的檔數目。<br/>**使用的儲存空間 (MB)** 是指目前在網站上使用的儲存空間量。  <br/> **儲存量 (MB)** 是針對此網站所指派的儲存量上限。  <br/> **網頁檢視** 是指在網站上查看頁面的次數。  <br/> 「所 **訪問的頁面**」是網站上已訪問的唯一頁面數目。  <br/> **根網站範本** 是用來建立網站的範本。  <br/> 附注：如果您想要依不同的網站類型來篩選資料，請匯出資料，並使用根 Web 範本欄。 <br/>如果您組織的原則使您無法查看使用者資訊可辨識的報告，您可以變更所有這些報告的隱私權設定。 請參閱 [Microsoft 365 系統管理中心的活動報告中](activity-reports.md)的 [**我要如何隱藏使用者層級詳細資料？** ] 區段。  <br/> |
|9.  <br/> |Select **manage columns** ![ manage columns ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) 以新增或移除報告中的欄。    <br/> |
|10.  <br/> |您也可以選取 [ **匯出** 匯出] 連結，將報告資料匯出至 Excel .csv 檔案 ![ ](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) 。 這會匯出所有網站的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的網站少於2000個，您可以在報表本身的資料表中進行排序和篩選。 如果您有超過2000的網站，為了進行篩選和排序，您將需要匯出資料。  <br/> 附注：將資料匯出至 Excel 檔案時，請注意，產生內容報告的日期會反映在 [ **資料** 開始于] 欄中的檔案中。      <br/>   |
|||
