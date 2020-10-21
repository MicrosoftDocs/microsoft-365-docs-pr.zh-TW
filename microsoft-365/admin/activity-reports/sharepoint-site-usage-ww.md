---
title: 系統管理中心的 Microsoft 365 報告-SharePoint 網站使用狀況
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
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 取得「SharePoint 網站使用量」報告，瞭解使用者在 SharePoint 網站中儲存的檔案數目、使用的數目，以及使用的總儲存空間。
ms.openlocfilehash: bc9345a5e281f1e7343bf62a2dc6832587d0786e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649774"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>系統管理中心的 Microsoft 365 報告-SharePoint 網站使用狀況

做為 Microsoft 365 系統管理員，[ **報告** ] 儀表板會顯示您組織中各種產品的活動概況。 此功能可讓您更深入解析各項產品的特定活動。 例如，您可以從 SharePoint 中取得您所取得之價值的高層級視圖、使用者儲存在 SharePoint 網站中的檔案總數、使用的檔案數目，以及所有這些網站所使用的儲存空間。 然後，您可以深入查看「SharePoint 網站流量」報告，以瞭解所有網站的趨勢及每個網站層級的詳細資料。 
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。
在系統管理中心的 Microsoft 365 報告不支援 GCC 高和 DoD 承租人。
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>如何取得 SharePoint 網站使用狀況報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。 
2. 在 [儀表板] 主頁上，按一下 [SharePoint 卡片上的 [ **View more** ] 按鈕。
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>解讀 SharePoint 網站使用量報告

您可以選擇 [ **網站使用狀況** ] 索引標籤，在 SharePoint 報告中查看網站使用狀況。<br/>![Microsoft 365 報告-Microsoft SharePoint 網站使用狀況報告。](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

選取 **[選擇欄位** ]，以新增或移除報告中的欄。  <br/> ![SharePoint 網站使用量報告-選擇欄](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)

您也可以選取 [ **匯出** ] 連結，將報告資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。 
  
|項目|描述|
|:-----|:-----|
|**計量**|**定義**|
|網站 URL  <br/> |網站的完整 URL。 <br/> |
|刪除  <br/> |網站的刪除狀態。 網站標示為已刪除至少需要7天。  <br/> |
|網站擁有人  <br/> |網站主要擁有人的使用者名稱。   <br/> |
|網站擁有者主要名稱  <br/> |網站擁有者的電子郵件地址。 <br/> |
|上次活動日期 (UTC)   <br/> | 上次偵測到檔案活動的日期，或在網站上查看頁面。  <br/> |
|檔案  <br/> |網站上的檔數目。 <br/>|
|使用中檔  <br/> | 網站上的使用中檔案數目。<br/> 附注：如果在報告的指定期間內已移除檔案，則報告中顯示的使用中檔數目可能會大於目前網站上的檔數目。  <br/> |
|使用的儲存空間 (MB)   <br/> |目前在網站上使用的儲存空間量。  <br/>|
|儲存量 (MB)   <br/> |為網站所分配的儲存空間上限。  <br/>|
|網頁檢視  <br/> |在網站上查看頁面的次數。  <br/>|
|訪問的頁面  <br/> |網站上已訪問的唯一頁面數目。  <br/>|
|根網站範本  <br/> |用來建立網站的範本。  <br/> 附注：如果您想要依不同的網站類型來篩選資料，請匯出資料，並使用根 Web 範本欄。 |
|||