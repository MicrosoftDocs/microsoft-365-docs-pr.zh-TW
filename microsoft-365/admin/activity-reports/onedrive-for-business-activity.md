---
title: Microsoft 365 系統管理中心報告中的商務用 OneDrive 活動
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 8bbe4bf8-221b-46d6-99a5-2fb3c8ef9353
description: 為您的組織取得 [OneDrive 使用量] 報告，並知道活動的每個 OneDrive 使用者、 檔案共用，數目及儲存空間使用情形。
ms.openlocfilehash: b51071fe8c91b0064d6680b628b58df1f370c73d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353584"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365 系統管理中心報告中的商務用 OneDrive 活動

Microsoft 365**報告**儀表板顯示您的活動概觀跨組織中的產品。 此功能可讓您深入了解個別產品層級報告，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。
  
例如，您可以查看每位授權使用 OneDrive 的使用者與 OneDrive 上檔案的互動，以了解活動。也可以查看共用的檔案數量，協助您了解共同作業的程度。
  
> [!NOTE]
> 部分功能會逐步提供。這表示您可能還不會看到此功能，或看起來可能與說明文章中描述的不一樣。不過別擔心，新功能很快就會開放！ 
  
如果要了解每個 OneDrive 帳戶的活動量及儲存空間使用情形，可以檢視 [OneDrive 使用情況報告](onedrive-for-business-usage.md)。
  
> [!NOTE]
> 您必須是全域系統管理員、 全域讀者或報告讀取者，在 Microsoft 365 或 Exchange、 SharePoint 或 Skype 商務系統管理員，才能查看報告。 
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>如何進入 OneDrive 活動報告？

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取 [報告]** 下拉式清單，選取 [ **OneDrive** \> **活動**。
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>解讀商務用 OneDrive 活動報告

您可以透過檢視 OneDrive for Business activity 查看 [**檔案**] 和 [**使用者**檢視。 
  
![OneDrive Activity Report](../../media/316b2a03-8e42-447c-aae8-080813eebe84.png)
  
|||
|:-----|:-----|
|1.  <br/> |**商務用 OneDrive 活動**報告可檢視的趨勢，過去 7 天、 30 天、 前 90 天或 180 天。 不過，如果您在報表中選取的特定一天，表格 (7) 將會顯示資料 28 天，從目前的日期 （不是該報告產生的日期）。  <br/> |
|2.  <br/> |每個報告中的資料通常涵蓋的最後一個 24 到 48 小時。 <br/>|
|3.  <br/> |[**檔案**] 檢視可協助您了解執行過檔案互動，對任何 OneDrive 帳戶的授權使用者的唯一號碼。  <br/> |
|4.  <br/> |[**使用者**] 檢視可協助您了解在作用中 OneDrive 使用者人數的趨勢。 使用者只要在指定的期間內曾經執行過檔案活動 (儲存、同步、修改或共用)，就會視為使用中。  <br/> 附註： 單一檔案，可以發生多次檔案活動，但只會視為一個使用中檔案。 例如，您可能會在指定期間內多次儲存並同步處理同一個檔案，但在資料中它只會採計為一個使用中的檔案和一個同步處理的檔案。           |
|5.  <br/> | 在 [**檔案**] 圖表中，Y 軸是任何使用者儲存、 同步處理、 修改或共用的唯一檔案數目。  <br/>  在 [**使用者**] 圖表中，Y 軸是執行過檔案互動的唯一使用者人數 （儲存、 同步處理、 修改或共用） 對任何 OneDrive 帳戶。  <br/>  所有圖表中的 X 軸都代表此特定報告的所選日期範圍。  <br/> |
|6.  <br/> |您可以篩選看圖表所選取項目在圖例中的數列。 例如，在 [**檔案**] 圖表中，選取 [**檢視或編輯**或**已同步處理**以查看只與其個別相關的資訊。 變更此選取項目並不會變更格線表格中的資訊。  <br/> |
|7.  <br/> | 表格顯示每個使用者層級的資料明細。 您可以新增或移除表格中的欄位。   <br/>  **Username**是 OneDrive 帳戶的擁有者的使用者名稱。  <br/> **[上次活動日期 (UTC)** 是在所選的日期範圍的 OneDrive 帳戶執行檔案活動的最晚日期。 若要查看特定日期發生的活動，請直接選取圖表中的日期。  <br/> ![選取圖表中的特定日期](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png)  <br/>  這會篩選表格，顯示檔案活動資料僅針對該特定日期執行該活動的使用者。  <br/> **檔案檢視或編輯**是使用者上傳、 下載、 修改或檢視的檔案數目。  <br/> **檔案同步處理**為已同步處理使用者的本機裝置從 OneDrive 帳戶的檔案數目。  <br/> **在內部共用的檔案**是與組織內的使用者或群組 （也可能會包括外部使用者） 內的使用者共用的檔案數目。  <br/> **外部共用的檔案**是指與組織外部使用者共用的檔案數目。  <br/> **刪除的郵件**會指出使用者的授權被移除。  <br/> 附註： 已刪除的使用者活動仍會顯示在報表中，只要曾有過授權，在選取的時間期間一些時間。 **已刪除**] 欄可協助您請注意，使用者可能不再是作用中，但，藉此報告中的資料。<br/>**已刪除日期**是在其使用者的授權被移除的日期。  <br/> **產品指派**是授權給該使用者的 Microsoft 365 產品。  <br/>  如果貴組織的原則防止您檢視報告所在識別使用者資訊，您可以變更所有這類報告的隱私權設定。 請參閱**如何隱藏使用者層級的詳細資訊？** ] 區段中[的 Microsoft 365 系統管理中心的活動報告](activity-reports.md)中。  <br/> |
|8.  <br/> |選取 [**管理欄**] 圖示![管理欄](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png)來新增或移除報告中的欄。  <br/> |
|9.  <br/> |您可以也報告資料匯出到 Excel.csv 檔案，藉由選取 [**匯出**] 連結。 這會匯出所有使用者的資料，並可讓您進行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2000 個，您可以直接在報告中的表格內進行排序和篩選。 如果您的使用者多於 2000 個，則需要匯出資料才能進行排序和篩選。  <br/> |
|||
   

