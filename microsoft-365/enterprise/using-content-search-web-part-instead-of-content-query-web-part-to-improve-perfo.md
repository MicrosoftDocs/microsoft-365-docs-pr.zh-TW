---
title: 請使用內容搜尋網頁組件 (而非內容查詢網頁組件) 來改善 SharePoint Online 中的效能
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: 瞭解如何將內容查詢網頁元件取代 SharePoint Server 2013 和 SharePoint Online 中的內容搜尋網頁元件，以提升效能。
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688855"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a>請使用內容搜尋網頁組件 (而非內容查詢網頁組件) 來改善 SharePoint Online 中的效能

本文將說明如何在 SharePoint Server 2013 和 SharePoint Online 中，透過將內容查詢網頁組件取代為內容搜尋網頁組件的方式來提升效能。
  
SharePoint Server 2013 和 SharePoint Online 最強大的新功能之一就是內容搜尋網頁組件 (CSWP)。 此網頁組件能使用搜尋索引，來快速擷取顯示給使用者的結果。 請從內容查詢網頁組件 (CQWP) 改為使用內容搜尋網頁組件，以改善您使用者的效能。
  
改用內容搜尋網頁組件 (而非內容查詢網頁組件) 將大幅改善 SharePoint Online 上的網頁載入效能。 您需要進行一些額外的設定以取得正確的查詢結果，但這將有助於提升效能並滿足使用者。
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a>比較改用內容搜尋網頁組件 (而非內容查詢網頁組件) 後的效能提升成果

以下範例說明當改用內容搜尋網頁組件 (而非內容查詢網頁組件) 後，您可能會體驗到的相對效能提升成果。 當網站結構複雜和查詢的內容廣泛時，這些效果的影響會更為顯著。
  
此範例網站具有下列特質：
  
- 8 個子網站層級。
    
- 列出使用自訂的「水果」內容類型。
    
- 網頁組件​​中的內容查詢非常廣泛，會傳回「水果」內容類型的所有項目。
    
- 此範例的 8 個網站中只使用 50 個項目。 對擁有更多內容的網站來說，這些效果會更加明顯。
    
以下為內容查詢網頁組件結果的螢幕擷取畫面。
  
![顯示網頁組件內容查詢的圖形](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
請使用 Internet Explorer 中 F12 開發人員工具的 **[網路]** 索引標籤，查看回應標頭的詳細資料。 在下方的螢幕擷取畫面中，載入此頁面時的 **SPRequestDuration** 值為 924 毫秒。 
  
![顯示 924 要求期間的螢幕擷取畫面](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 **SPRequestDuration** 代表伺服器為了準備該網頁所完成的工作量。 將「依查詢顯示內容」網頁組件切換至「依搜尋顯示內容」網頁組件能大幅減少呈現頁面所需的時間。 相比之下，擁有等量內容搜尋網頁組件的頁面，傳回相同結果數量時的 **SPRequestDuration** 值為 106 毫秒，如下方的螢幕擷取畫面所示： 
  
![顯示 106 要求期間的螢幕擷取畫面](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a>在 SharePoint Online 中新增內容搜尋網頁組件

新增內容搜尋網頁組件的程序與一般內容查詢網頁組件非常類似。 請參閱 [「在 SharePoint 中設定內容搜尋網頁組件」](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)中的 *「新增內容搜尋網頁組件」* ​​一節。
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a>為您的內容搜尋網頁組件建立正確的搜尋查詢

一旦新增內容搜尋網頁組件，您就可以縮小搜尋並傳回想要的項目。 如需如何執行此操作的詳細指示，請參閱在 [ SharePoint 中設定內容搜尋網頁組件](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)中的 *「透過設定內容搜尋網頁組件中的進階查詢來顯示內容​」* 一節。
  
## <a name="query-building-and-testing-tool"></a>建置查詢與測試工具

如需能建置並測試複雜查詢的工具，請參閱 Codeplex 上的[搜尋查詢工具](https://sp2013searchtool.codeplex.com/)。 
  

