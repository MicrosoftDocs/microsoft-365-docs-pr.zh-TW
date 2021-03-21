---
title: 將核心資料移至新的 Microsoft 365 datacenter geos
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0a35176a-e585-4dec-a90b-36be8314667f
f1.keywords:
- NOCSH
description: 瞭解新的 Office 365 資料中心 geos，以及如何使用資料派駐選項，將核心資料要求移至新的地理位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f752956506df98ea71d0d02886d14dc719ed9413
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921603"
---
# <a name="moving-core-data-to-new-microsoft-365-datacenter-geos"></a>將核心資料移至新的 Microsoft 365 datacenter geos

我們仍然開啟新的資料中心 geos for Microsoft 365 服務。 這些新的資料中心 geos 可增加容量及計算資源，以支援我們持續的客戶需求和使用量成長。 此外，新的資料中心 geos 提供核心客戶資料的地理位置資料派駐服務。 

核心客戶資料是一項字詞，參考客戶資料的子集，包括： 
- Exchange Online 信箱內容 (電子郵件內文、行事曆專案和電子郵件附件的內容) 
- SharePoint 線上網站內容和儲存在該網站中的檔案
- 上傳至商務 OneDrive 的檔案
- 小組聊天訊息，包括私人郵件、通道訊息和交談中使用的影像
  
在現有的資料中心地理位置發起時，已有其核心客戶資料的現有客戶，不會受到影響。 我們不會對新的資料中心地理位置引進任何獨特的功能、功能或規範認證。 身為這兩個 geos 中任何一部的客戶，您會體驗到您之前所做的相同服務品質、效能及安全性控制措施。 我們為下表中所列的現有客戶提供選項，以要求將其組織的核心客戶資料及早遷移至新的資料中心地理位置。
  
|**具有租使用者註冊國家/地區的客戶**|**舊的資料中心地理位置**|**新的資料中心地理位置**|**地理位置可供使用**|
|:-----|:-----|:-----|:-----|
|**日本**| 亞洲/太平洋 | 日本 | 2014 年 12 月 |
|**澳大利亞，紐西蘭，斐濟**| 亞洲/太平洋 | 澳洲 | 2015 年 3 月 |
|**印度**| 亞洲/太平洋 | 印度 | 2015 年 10 月 |
|**加拿大**| 美國 | 加拿大 | 2016 年 5 月 |
|**英國**| 歐盟 | 英國 | 2016 年 9 月 |
|**南韓**| 亞洲/太平洋 | 韓國 | 2017 年 4 月 |
|**法國**| 歐盟 | 法國 | 2018 年 3 月 |
|**阿拉伯聯合大公國**| 歐盟 | 阿拉伯聯合大公國 | 2019 年 6 月 |
|**南非**| 歐盟 | 南非 | 2019 年 7 月 |
|**瑞士，列支敦斯登**| 歐盟 | 瑞士 | 2019 年 12 月 |
|**德國**| 歐盟 | 德國 | 2019 年 12 月 |
|**挪威**| 歐盟 | 挪威 | 2020 年 4 月 |
|**巴西**| 美洲地區 | 巴西 | 2020 年 11 月 |

從10月 1 2020 日到1月1日，含租使用者之 Office 365 教育版訂閱的客戶不適合進行遷移。

[互動式資料中心地圖](https://office.com/datamaps)的一部分，所有資料中心 geos、資料中心及客戶資料的位置完整清單皆可供使用。 
  
## <a name="data-residency-option"></a>資料派駐選項

我們為已在上表所列的「資料中心 geos」所涵蓋的合格 Microsoft 365 客戶提供資料派駐選項。 使用此選項時，具有資料派駐要求的合格客戶，可要求將其組織的核心客戶資料移轉至新的資料中心地理位置。  Microsoft 將在註冊時段內，為要求遷移的所有合格客戶提供認可的截止期限。  請查看 [如何要求資料移動](request-your-data-move.md) 頁面，以取得資料中心地理位置之開啟註冊視窗的詳細資訊，以及登錄程式的步驟。  在要求期間結束之前，資料移動最多可能需要24個月才能完成。

我們不會對新的資料中心地理位置引進任何獨特的功能、功能或規範認證。
    
複雜性、精確度及規模，我們需要在全域運作及自動環境中執行資料移動，禁止當您的租使用者或任何其他單一租使用者完成資料移動時，無法進行共用。 當客戶的資料移動完成時，客戶會在訊息中心接收一次確認。 
    
資料移動是後端服務作業，對使用者影響最小。 在 [資料移動頁面的期間和之後](during-and-after-your-data-move.md) ，會列出受影響的功能。 我們遵循 [Microsoft Online Services 服務等級協定 (SLA) ](https://go.microsoft.com/fwlink/p/?LinkId=523897) 以取得可用性，讓客戶無需準備或在移動期間進行監視。 如有需要，應執行任何服務維護的通知。 

將資料移至新的資料中心地理位置，對客戶沒有額外的成本。
    
## <a name="related-topics"></a>相關主題 
 
[如何要求資料移動](request-your-data-move.md)
    
[資料移動一般常見問題集](data-move-faq.md)
  
[Microsoft Dynamics CRM Online 的新 datacenter geos](/power-platform/admin/new-datacenter-regions)
  
[依地區的 Azure 服務](https://azure.microsoft.com/regions/)