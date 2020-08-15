---
title: 使用 SharePoint Online 的物件快取
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: 本文說明在 SharePoint Server 2013 內部部署和 SharePoint Online 中使用物件快取的差異。
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695629"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a>使用 SharePoint Online 的物件快取

本文說明在 SharePoint Server 2013 內部部署和 SharePoint Online 中使用物件快取的差異。
  
在 SharePoint 線上部署中，依賴物件快取會有很大的負面影響。 任何對 SharePoint Online 中物件快取的依賴性都會降低頁面的可靠性。 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a>SharePoint 線上及 SharePoint Server 2013 物件快取的運作方式

當以內部部署形式主控 SharePoint Server 2013 時，客戶就擁有主控物件快取的私人前端網頁伺服器。 這表示快取專用於一個客戶，而且只受限於可使用的記憶體量並指派給物件快取。 因為內部部署案例只會提供一位客戶，所以前端網頁伺服器通常會讓使用者在相同的網站之間進行要求。 這表示快取已滿，而且仍然保留所有的清單查詢結果，以及您的使用者定期要求的 SharePoint 物件。
  
![顯示到內部部署前端網頁伺服器的流量和負載](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
因此，當使用者第二次造訪頁面時，頁面載入時間會有所改善。 在至少四次載入相同頁面後，頁面會在所有前端網頁伺服器上快取。
  
相反地，在 SharePoint Online 中還有許多伺服器，還有許多網站。 每一位使用者可能會連接到未填入快取的不同前端網頁伺服器。 或者，也可能是針對伺服器填入快取，但該前端網頁伺服器的下一位使用者要求來自不同網站的頁面。 或者，即使下一個使用者要求相同頁面（如先前就診所要求），但其快取會在其快取中沒有該頁面的不同前端網頁伺服器上進行負載平衡。 在此情況下，快取根本不會協助使用者。
  
在下圖中，每個點都代表使用者要求的頁面及快取的位置。 不同的色彩代表不同的客戶，以共同使用 SaaS 基礎結構。
  
![顯示 SharePoint Online 中的物件快取結果](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
如您在圖表中所看到的，任何指定的使用者只要伺服器使用其快取版本的頁面，都是超薄的機會。 此外，由於較大的輸送量，而且伺服器在許多網站間共用，所以快取不會持續很長的時間，因為可供快取使用的空間。
  
針對上述所有原因，使用取得快取物件的使用者，並不是確保線上 SharePoint 中的品質使用者經驗和頁面載入時間的有效方式。
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a>如果無法依賴物件快取以提升 SharePoint 線上的效能，我們會改用什麼？

由於您不應該在 SharePoint Online 中依賴快取，因此應該評估使用物件快取的 SharePoint 自訂的替代設計方法。 這表示使用效能問題的方法，而不依靠物件快取來為使用者產生良好的結果。 這會在此系列的部分其他文章中說明，包含：
  
- [SharePoint Online 的瀏覽選項](navigation-options-for-sharepoint-online.md)
    
- [SharePoint Online 中的縮製和統合](minification-and-bundling-in-sharepoint-online.md)
    
- [使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [在 SharePoint Online 中延遲載入圖片與 JavaScript](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

