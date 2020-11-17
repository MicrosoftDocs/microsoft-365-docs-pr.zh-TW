---
title: Microsoft 生產力分數
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Microsoft 生產力分數的概覽。
ms.openlocfilehash: 49ae35d68b0d0ebf627e44e5912d4a1bb7b712c0
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123486"
---
# <a name="microsoft-productivity-score"></a>Microsoft 生產力分數 

生產力分數可協助組織轉換工作如何使用 Microsoft 365 的相關資訊，以及支援這些功能的技術體驗。 分數會反映貴組織對於人員和技術經驗的效能，並與您的組織（如您的組織）比較您的分數。

分數包括：

- **度量** ，可協助您瞭解使用者如何使用 Microsoft 365 產品來共同作業、溝通及跨平臺工作。
- 資料的 **深入** 瞭解，可協助您找出機會，以提升員工生產力及滿意度。
- 您可以採取 **建議的動作**，協助貴組織中的人員有效使用 Microsoft 365 產品，讓每個人都能進行最佳的工作。

我們提供兩個區域的資料、洞察力和建議： 

- **人員體驗：** 衡量人員如何共同處理內容，如何使用 Microsoft 365 產品進行通訊，以及是否在多個平臺上使用 Microsoft 365。 

    我們提供這些洞察力，是因為當人們線上合作時，他們可節省時間，而且可在任何裝置上自由運作，這樣就能更有效率和滿意。 以靈活的方式進行通訊的功能可讓人員更有效率，能更好地建立更好的關聯性，進而使您的組織更具整合。 如需證據，請參閱 [Forrester report](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf)。

- **技術經驗：** 您的小組生產力取決於可靠且完善的技術，以及 Microsoft 365 的有效使用方式。 [端點分析](https://aka.ms/endpointanalytics) 可協助您瞭解使用者的生產力對您的硬體和軟體的效能與狀況問題有何影響。建議的動作可協助您修正這些問題。 Microsoft 365 network connectivity insights 可協助您疑難排解組織的 connectivty 問題。

如需概述和必要條件詳細資料，請參閱 [何謂「端點分析](https://docs.microsoft.com/mem/analytics/overview) 」。 若要深入瞭解 Microsoft 365 network connectivity insights，請參閱 [network connectivity 一覽](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-networking-overview)。
  

## <a name="how-the-score-is-calculated"></a>計算分數的方式

您的生產力分數是以人員和技術經驗類別的綜合分數為基礎。 每個類別平均加權，總100點數。 最高的可能生產力分數為800。

### <a name="score-categories"></a>分數類別 

-  (100 點的通訊) 
- 會議 (100 點) 
- 內容共同作業 (100 點) 
- 團隊合作 (100 點) 
- 行動性 (100 點) 
- 端點分析 (100 點) 
- 網路連通性 (100 點) 
- Microsoft 365 App Health (100 點) 
- **總可能 = 800 點**
 
 在每個分數類別中，我們會識別重要活動的模式，以瞭解人員如何使用 Microsoft 365 產品來共同作業、溝通，以及跨平臺工作。 我們提供28天和180天的主要即時檢視。 我們也提供不屬於分數計算的支援度量，但對於協助您識別您可以解決的基本行為和設定很重要。

### <a name="products-included-in-productivity-score"></a>產品包含在生產力分數中的產品 

生產力分數包括來自 Exchange、SharePoint、OneDrive、小組、Word、Excel、PowerPoint、OneNote、Outlook、Yammer 及 Skype 的資料。

您的分數會每日更新，而且會反映在最後 28 (中完成的使用者動作，包括當天) 。


## <a name="pre-requisites"></a>先決條件 

若要讓人員體驗資料，您需要使用 Microsoft 365 for business 或 Office 365 for enterprise 訂閱。 針對您租使用者的端點分析資料，您必須將 Microsoft Intune 新增至您的訂閱。 Intune 可協助您保護組織的資料，方法是管理裝置和應用程式。 當您有 Intune 之後，您可以在 Intune 體驗中開啟端點分析。 深入瞭解 Microsoft Intune。 
> [!NOTE]
> 若要取得生產力評分功能，不需要使用工作場所分析的授權。

若要查看組織的生產力評分，您必須具有下列其中一個角色： 

- 全域系統管理員 
- Exchange 系統管理員
- SharePoint 系統管理員 
- 商務用 Skype 系統管理員 
- Teams 系統管理員 
- 全域讀取者 
- 報告讀取者 

您可以從 [**報表**  >  **生產力分數**] 底下的 Microsoft 365 系統管理員那裡存取體驗。

## <a name="interpreting-productivity-score"></a>解讀生產力分數 

[生產力分數] 首頁會顯示每個類別的總分和總分記錄以及主要洞察力。

:::image type="content" source="../../media/prodscore-landing.png" alt-text="報表中的 [生產力分數] 頁面。":::

**您的分數** 會顯示為百分比值，以點為單位。 您可以在分子中看到您的點，而分母中的可能點數上限。

**對等基準** 可讓您將您的分數與像您的組織比較。 人員經驗類別的對等基準計算是一組類似組織內的平均量值。 組織的集合是由您地區中的組織所組成，這些組織的授權使用者數目、授權類型、行業，以及使用 Microsoft 365 的 tenure。 

端點分析對等基準包括裝置啟動效能的目標，以及根據整個承租人中匯總的中線值進行建議的軟體設定。

若為網路連線，建議的基準是80點。

**分數細分** 區段利用人員和技術經驗方面的基準，提供您的生產力分數明細。

分數記錄會顯示過去6個月內，每個類別中的分數變更的方式。

「 **人員經驗** 」和「 **技術經驗** 」區域包含這些區域的類別的主要洞察力。 您可以按一下每個類別以查看更深入的見解。

## <a name="category-details-pages"></a>類別詳細資料頁面

每個類別詳細資料頁面會顯示主要的洞察力和支援度量，以及您可以採取哪些相關的研究和動作，以促進組織中的變更。 調研可支援每個類別之主要真知灼見的重要性和基本概念。 如需詳細資訊，請 [閱讀 Forrester 報告](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf)。

詳細資料頁面包括：
- [內容共同作業–人員經驗](content-collaboration.md)
- [通訊–人員經驗](communication.md)
- [會議–人員經驗](meetings.md)
- [行動性–人員經驗](mobility.md)
- [團隊合作–人員經驗](teamwork.md)
- [Microsoft 365 應用程式健康情況–技術經驗](apps-health.md)

## <a name="business-continuity-special-report"></a>商務持續性特殊報告

「業務持續性報告」是可供所有 Microsoft 365 客戶使用的有限的工作場所智慧報告，可協助他們在這項富有挑戰性的時間內指導其組織。  

此報告可協助業務負責人瞭解： 

- 移動作業與通訊對遠端工作的影響。 

- 因人員調整為在家運作時，對工作生命期的影響。 

- 如果遠端會議支援有效的決策過程。

[深入瞭解商務持續性報告](https://aka.ms/bcrps)

[深入瞭解 Microsoft Graph](https://docs.microsoft.com/graph/)

## <a name="we-want-to-hear-from-you"></a>我們想要聽到您的來信

分享您對於生產力評分的想法，以及如何改善的想法。 請使用產品中的 **意見** 反應區段和/或與 ProductivityScorePreview@service.microsoft.com 的生產力分數小組聯繫。
