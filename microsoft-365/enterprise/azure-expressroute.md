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
description: 瞭解如何使用 Azure ExpressRoute 搭配 Office 365 並規劃網路實施專案（如果您要使用它進行部署）。
ms.openlocfilehash: c43957435272e1a3b6f738d33a2dd12e81dfc013
ms.sourcegitcommit: aff2331f9a3f22591f8ace1a646809969d28c120
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52464414"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute for Office 365

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

瞭解如何搭配 Office 365 使用 azure ExpressRoute，以及如何規劃要搭配 Office 365 使用 azure ExpressRoute 時所需的網路實施專案。 在 Azure 中執行的基礎結構和平臺服務常常會以網路架構和效能考慮的方式來受益。 在這兩種情況下，我們建議 ExpressRoute Azure。 軟體即服務產品（如 Office 365 和 Dynamics 365）已透過網際網路安全且可靠地存取。 您可以閱讀 Internet 效能及安全性，以及在[評估 Office 365 網路](assessing-network-connectivity.md)連線的文章中，您可能會針對 Office 365 考慮 Azure ExpressRoute。

> [!NOTE]
> Microsoft Defender for Endpoint 不會提供與 Azure ExpressRoute 的整合。 雖然這不會讓客戶定義 ExpressRoute 規則，可讓客戶從私人網路連接至 Microsoft Defender for Endpoint cloud services，但會在服務或雲端基礎結構演變時，維持規則。

> [!NOTE]
> 建議您不要針對 Microsoft 365 ExpressRoute，因為在大多數情況下，它不會提供服務的最佳連線模型。 因此，使用此 Microsoft 365 的連線模型時，需要 Microsoft 授權。 我們只會在必要的少數案例中查看每個客戶要求並授權 ExpressRoute Microsoft 365。 如需詳細資訊，請閱讀[Microsoft 365 指南的 ExpressRoute](https://aka.ms/erguide) ，並遵循您的生產力、網路及安全性小組的完整檔評論。請與您的 Microsoft 帳戶小組合作，視需要提交例外狀況。 嘗試為 Office 365 建立路由篩選的未授權訂閱將會收到[錯誤訊息](https://support.microsoft.com/kb/3181709)。

## <a name="planning-azure-expressroute-for-office-365"></a>規劃 Office 365 的 Azure ExpressRoute

除了網際網路連線之外，您還可以選擇透過直接連線路由傳送其 Office 365 網路流量的子集，以提供可預見性和 Microsoft 網路元件的99.95% 正常運作時間 SLA。 Azure ExpressRoute 會為您提供與 Office 365 和其他 Microsoft 雲端服務的專用網路連接。

不論您是否有現有 MPLS WAN，都可以使用三種方式之一將 ExpressRoute 新增至網路架構;透過支援的雲端 exchange 共同位置提供者、乙太網點對點連線提供者，或透過 MPLS 連線提供者。 查看 [您地區中提供的提供者](/azure/expressroute/expressroute-locations)。 直接 ExpressRoute 連線功能可讓您連線至所述的應用程式[Office 365 服務](azure-expressroute.md#BKMK_WhatDoIGet)中所述的應用程式。 所有其他應用程式和服務的網路流量將繼續穿越網際網路。

請考慮下列高層級網狀圖表，它會顯示一般 Office 365 客戶透過網際網路連線至 microsoft 資料中心，以存取所有 microsoft 應用程式，例如 Office 365、Windows 更新及 TechNet。 客戶不論是從內部部署網路或獨立的網際網路連線，都使用類似的網路路徑。

![Office 365 網路連線能力](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

現在，請查看已更新的圖表，它會描述同時使用網際網路與 ExpressRoute 的 Office 365 客戶，以連接至 Office 365。 請注意，有些連線（例如公用 DNS 和內容傳遞網路節點）仍然需要公用網際網路連線。 此外，還請注意，未位於其 ExpressRoute 連線大樓中的客戶使用者是透過網際網路連線。

![Office 365 與 ExpressRoute 的連接](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

仍想要更多資訊？ 瞭解如何[使用 azure ExpressRoute Office 365 管理網路流量](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)，並瞭解如何為[Office 365 設定 azure ExpressRoute](/azure/expressroute/expressroute-faqs)。 我們也針對通道9上的[Office 365 訓練](https://channel9.msdn.com/series/aer)系列記錄了10部分 Azure ExpressRoute，以協助說明更徹底的概念。

## <a name="what-office-365-services-are-included"></a>包含哪些 Office 365 服務？
<a name="BKMK_WhatDoIGet"> </a>

下表列出 ExpressRoute 支援的 Office 365 服務。 請複查[Office 365 端點文章](./urls-and-ip-address-ranges.md)，以瞭解這些應用程式的哪些網路要求需要網際網路連線。

| 包含的應用程式 |
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|商務用 Skype線上<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint線上<sup>1</sup> <br/> 商務用 OneDrive<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|入口網站和共用<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD 連線<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup>每個應用程式都有 ExpressRoute 不支援的網際網路連線需求，請參閱[Office 365 端點文章](./urls-and-ip-address-ranges.md)以取得詳細資訊。

Office 365 中未包含的 ExpressRoute 服務，會 Microsoft 365 Apps 企業版用戶端下載、內部部署身分識別提供者 Sign-In，以及 Office 365 在中國使用 21 Vianet (服務運作) 。

## <a name="implementing-expressroute-for-office-365"></a>實作 ExpressRoute for Office 365

實施 ExpressRoute 需要網路和應用程式擁有人的參與，並需要仔細規劃，以判斷新的 [網路路由架構](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)、頻寬需求、安全性的實施方式、高可用性等等。 若要執行 ExpressRoute，您必須：

1. 完全瞭解 Office 365 連線規劃中是否需要 ExpressRoute。 瞭解哪些應用程式會使用網際網路或 ExpressRoute，並利用 internet 和 ExpressRoute Office 365 流量，充分規劃網路容量、安全性和高可用性需求。

2. 決定網際網路和 ExpressRoute 流量<sup>1</sup>的出口和對等位置。

3. 決定網際網路和 ExpressRoute 連線所需的容量。

4. 制定實施安全性及其他標準周邊控制措施<sup>1</sup>的計畫。

5. 具有有效的 Microsoft Azure 帳戶，可訂閱 ExpressRoute。

6. 選取連線模型和核准的 [提供者](/azure/expressroute/expressroute-locations)。 請記住，客戶可以選擇多個連線模型或夥伴，而夥伴不需要與您現有的網路提供者相同。

7. 先驗證部署，再將流量導向 ExpressRoute。

8. 選擇性地 [實施 QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) ，並評估區域擴充。

<sup>1</sup> 重要的效能考慮。 這裡的決策可能會大幅影響延遲，這對商務用 Skype 的應用程式很重要。

如需其他參考，除了[ExpressRoute 檔](/azure/expressroute/expressroute-introduction)之外，還請使用我們的[路由輔助線](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408)。

若要購買 Office 365 的 ExpressRoute，您需要與一個或多個[核准的提供者](/azure/expressroute/expressroute-locations)合作，以使用 ExpressRoute 進階版訂閱來布建所需的號碼和大小的電路。 Office 365 購買其他授權。

您可以使用下列短連結返回這裡：[https://aka.ms/expressrouteoffice365]()

準備好註冊[Office 365 的 ExpressRoute 了](https://aka.ms/ert)嗎？

## <a name="related-topics"></a>相關主題

[評估 Office 365 網路連線能力](assessing-network-connectivity.md)

[管理 ExpressRoute for Office 365 連線](managing-expressroute-for-connectivity.md)

[使用 ExpressRoute for Office 365 進行路由傳送](routing-with-expressroute.md)

[使用 ExpressRoute for Office 365 進行網路規劃](network-planning-with-expressroute.md)

[實作 ExpressRoute for Office 365](implementing-expressroute.md)

[在 Office 365 案例的 ExpressRoute 中使用 BGP 社區](bgp-communities-in-expressroute.md)

[商務用 Skype Online 中的媒體品質和網路連線效能](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[使用基準與效能歷程記錄進行 Office 365 效能調整](performance-tuning-using-baselines-and-history.md)

[Office 365 的效能疑難排解規劃](performance-troubleshooting-plan.md)

[Office 365 URL 與 IP 位址範圍](urls-and-ip-address-ranges.md)

[Office 365 網路與效能調整](network-planning-and-performance.md)

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版概觀](microsoft-365-overview.md)
