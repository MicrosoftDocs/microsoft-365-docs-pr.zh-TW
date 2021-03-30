---
title: Azure ExpressRoute for Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: 瞭解如何搭配使用 Azure ExpressRoute 搭配 Office 365，並規劃網路實施專案（如果您要使用它進行部署）。
ms.openlocfilehash: 9af9a2981c9220784725284aa602cf2de66721e5
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408368"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute for Office 365

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

瞭解 Azure ExpressRoute 與 Office 365 搭配使用的方式，以及如何規劃在部署 Azure ExpressRoute 以與 Office 365 搭配使用時所需的網路實施專案。 在 Azure 中執行的基礎結構和平臺服務常常會以網路架構和效能考慮的方式來受益。 在這兩種情況下，我們建議 ExpressRoute Azure。 軟體即服務產品（如 Office 365 和 Dynamics 365）是透過網際網路安全且可靠地存取而建立的。 您可以閱讀 Internet 效能及安全性，以及在 [評估 office 365 網路](assessing-network-connectivity.md)連線的文章中，您可能會考慮 office 365 的 Azure ExpressRoute。

> [!NOTE]
> Azure Express 路由中不支援 Microsoft Defender for Endpoint。

> [!NOTE]
> 若要使用 Office 365 ExpressRoute，必須使用 Microsoft 授權。 當客戶的法規需求規定直接連線時，Microsoft 會檢查每家客戶要求的 ExpressRoute，並授權 Office 365 的使用。 如果您有這樣的需求，請提供文位元組選及網路連結，以 [瞭解 Office 365 要求表單 ExpressRoute](https://aka.ms/O365ERReview) 中是否需要直接連線才能開始 Microsoft 複查。 嘗試建立 Office 365 之路由篩選的未授權訂閱將會收到 [錯誤訊息](https://support.microsoft.com/kb/3181709)。

您現在可以為選取的 Office 365 網路流量，新增到 Office 365 的直接網路連線。 Azure ExpressRoute 提供直接連線、可預知的效能，並提供 Microsoft 網路元件的99.95% 的正常執行時間 SLA。 您仍需要網際網路連線，以取得未透過 Azure ExpressRoute 支援的服務。

## <a name="planning-azure-expressroute-for-office-365"></a>規劃 Office 365 的 Azure ExpressRoute

除了網際網路連線之外，您還可以選擇透過直接連線路由傳送其 Office 365 網路流量的子集，以提供 Microsoft 網路元件的可預見性和99.95% 的運作時間 SLA。 Azure ExpressRoute 為您提供 Office 365 和其他 Microsoft 雲端服務的這種專用網路連接。

不論您是否有現有 MPLS WAN，都可以使用三種方式之一將 ExpressRoute 新增至網路架構;透過支援的雲端 exchange 共同位置提供者、乙太網點對點連線提供者，或透過 MPLS 連線提供者。 查看 [您地區中提供的提供者](/azure/expressroute/expressroute-locations)。 直接 ExpressRoute 連線將會啟用與 [包含 Office 365 服務](azure-expressroute.md#BKMK_WhatDoIGet) 之應用程式的連線，如下所示。 所有其他應用程式和服務的網路流量將繼續穿越網際網路。

請考慮下列高層級網狀圖表，它會顯示一般的 Office 365 客戶連線到網際網路上的 Microsoft 資料中心，以存取所有的 Microsoft 應用程式，例如 Office 365、Windows Update 及 TechNet。 客戶不論是從內部部署網路或獨立的網際網路連線，都使用類似的網路路徑。

![Office 365 網路連線能力](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

現在請查看已更新的圖表，它會描述同時使用網際網路和 ExpressRoute 連接至 Office 365 的 Office 365 客戶。 請注意，有些連線（例如公用 DNS 和內容傳遞網路節點）仍然需要公用網際網路連線。 此外，還請注意，未位於其 ExpressRoute 連線大樓中的客戶使用者是透過網際網路連線。

![使用 ExpressRoute 的 Office 365 連線能力](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

仍想要更多資訊？ 瞭解如何 [使用適用于 office 365 的 azure ExpressRoute 管理網路流量](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) ，並瞭解如何 [設定 Office 365 的 azure ExpressRoute](/azure/expressroute/expressroute-faqs)。 我們也在頻道9上記錄了 [Office 365 訓練](https://channel9.msdn.com/series/aer) 系列的10個 part Azure ExpressRoute，以協助說明更徹底的概念。

## <a name="what-office-365-services-are-included"></a>包含哪些 Office 365 服務？
<a name="BKMK_WhatDoIGet"> </a>

下表列出 ExpressRoute 支援的 Office 365 服務。 請參閱 [Office 365 端點文章](./urls-and-ip-address-ranges.md) ，以瞭解這些應用程式的哪些網路要求需要網際網路連線。

|**包含的應用程式**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|商務用 Skype Online<sup>1</sup> <br/> Microsoft 團隊 <sup>1</sup> <br/> |
|SharePoint 線上<sup>1</sup> <br/> Business<sup>1</sup>的 OneDrive <br/> Project Online<sup>1</sup> <br/> |
|入口網站和共用<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> 這兩個應用程式都不受 ExpressRoute 支援網際網路連線性需求，請參閱 [Office 365 端點文章](./urls-and-ip-address-ranges.md) 以取得詳細資訊。

未隨附于 Office 365 ExpressRoute 的服務是適用于企業用戶端下載、內部部署身分識別提供者 Sign-In 和 Office 365 (（中國中的 21 Vianet) 服務）的 Microsoft 365 應用程式。

## <a name="implementing-expressroute-for-office-365"></a>實作 ExpressRoute for Office 365

實施 ExpressRoute 需要網路和應用程式擁有人的參與，並需要仔細規劃，以判斷新的 [網路路由架構](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)、頻寬需求、安全性的實施方式、高可用性等等。 若要執行 ExpressRoute，您必須：

1. 完全瞭解 Office 365 連線規劃中的需求 ExpressRoute。 瞭解哪些應用程式會使用網際網路或 ExpressRoute，並利用 internet 和 ExpressRoute 的 Office 365 流量，充分規劃網路容量、安全性和高可用性需求。

2. 決定網際網路和 ExpressRoute 流量<sup>1</sup>的出口和對等位置。

3. 決定網際網路和 ExpressRoute 連線所需的容量。

4. 制定實施安全性及其他標準周邊控制措施<sup>1</sup>的計畫。

5. 具有有效的 Microsoft Azure 帳戶來訂閱 ExpressRoute。

6. 選取連線模型和核准的 [提供者](/azure/expressroute/expressroute-locations)。 請記住，客戶可以選擇多個連線模型或夥伴，而夥伴不需要與您現有的網路提供者相同。

7. 先驗證部署，再將流量導向 ExpressRoute。

8. 選擇性地 [實施 QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) ，並評估區域擴充。

<sup>1</sup> 重要的效能考慮。 這裡的決策可能會大幅影響延遲，這對於商務用 Skype 之類的應用程式很重要。

如需其他參考，除了[ExpressRoute 檔](/azure/expressroute/expressroute-introduction)之外，還請使用我們的[路由輔助線](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408)。

若要購買 Office 365 ExpressRoute，您必須與一或多個核准的 [提供者](/azure/expressroute/expressroute-locations) 合作，以使用 ExpressRoute 優質訂閱來布建所需號碼和大小的電路。 沒有其他可從 Office 365 購買的授權。

您可以使用下列短連結返回這裡：[https://aka.ms/expressrouteoffice365]()

準備好註冊 [Office 365 的 ExpressRoute](https://aka.ms/ert)嗎？

## <a name="related-topics"></a>相關主題

[評估 Office 365 網路連線能力](assessing-network-connectivity.md)

[管理 ExpressRoute for Office 365 連線](managing-expressroute-for-connectivity.md)

[使用 ExpressRoute for Office 365 進行路由傳送](routing-with-expressroute.md)

[使用 ExpressRoute for Office 365 進行網路規劃](network-planning-with-expressroute.md)

[實作 ExpressRoute for Office 365](implementing-expressroute.md)

[在 ExpressRoute for Office 365 案例中使用 BGP 社區](bgp-communities-in-expressroute.md)

[商務用 Skype Online 中的媒體品質和網路連線效能](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[使用基準與效能歷程記錄進行 Office 365 效能調整](performance-tuning-using-baselines-and-history.md)

[Office 365 的效能疑難排解規劃](performance-troubleshooting-plan.md)

[Office 365 URL 與 IP 位址範圍](urls-and-ip-address-ranges.md)

[Office 365 網路與效能調整](network-planning-and-performance.md)

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版概觀](microsoft-365-overview.md)
