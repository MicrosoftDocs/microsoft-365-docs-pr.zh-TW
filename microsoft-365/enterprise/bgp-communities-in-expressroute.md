---
title: 在 ExpressRoute for Office 365 案例中使用 BGP 社區
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
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
- MOE150
- BCS160
ms.assetid: 9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099
description: 瞭解如何在 Azure ExpressRoute 中使用 BGP 社區，以管理 Office 365 案例的 IP 首碼數目及所需的頻寬。
ms.openlocfilehash: 9cb6980c1d8cc120f99cac087602856aeacf1adf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905209"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>在 ExpressRoute for Office 365 案例中使用 BGP 社區

使用 Azure ExpressRoute 連線到 Office 365 是根據特定 IP 子網的 BGP 廣告，其代表部署 Office 365 端點的網路。 由於 Office 365 的全域性質和構成 Office 365 的服務數目，客戶常常需要在其網路上管理其所接受的廣告。 減少 IP 子網的數目;在本文的其餘部分中，稱為 IP 首碼，以與 BGP 網路管理術語相符，可為客戶提供下列最終目標：
  
- **管理已播發的 IP 首碼已接受的號碼** ：具有內部網路基礎結構或網路載體的客戶，其內部網路基礎結構或網路載體只支援有限數目的 IP 首碼，而且具有網路承運人的網路承運人可接受超過有限號碼之首碼的客戶，將需要評估已宣告至其網路的首碼總數，並選取最適合 ExpressRoute 的 Office 365 應用程式

- **管理 Azure ExpressRoute 電路所需的頻寬量** -客戶可能想要在 ExpressRoute 路徑與網際網路路徑上控制 Office 365 服務的頻寬信封。 這可讓客戶為特定的應用程式（例如商務用 Skype）或透過網際網路路徑傳送其餘的 Office 365 應用程式，保留 ExpressRoute 頻寬。

為了協助客戶遵循這些目標，使用下列範例所示的服務特定 BGP 群組值，標記透過 ExpressRoute 所宣告的 Office 365 IP 首碼。
  
> [!NOTE]
> 您應該會期望某些與其他應用程式相關聯的網路流量會包含在社區值中。 這是全球軟體的預期行為，以服務提供共用服務和資料中心。 這兩個目標可能會在最小化的情況下，管理前置詞計數和/或頻寬的考慮。

|**服務**|**BGP 社區值**|**附註**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |包含 Exchange 和 EOP 服務\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|商務用 Skype\*  <br/> |12076:5030  <br/> |Microsoft 團隊服務 & 的商務用 Skype Online  <br/> |
|其他 Office 365 服務\*  <br/> |12076:5100  <br/> |包含 Azure Active Directory (驗證及目錄同步處理案例) 以及 Office 365 入口網站服務  <br/> |
|\* ExpressRoute 所包含的服務案例範圍已記錄在 [Office 365 端點](./urls-and-ip-address-ranges.md) 文章中。  <br/> \*\*未來可能會新增其他服務和 BGP 群組值。 [請參閱目前的 BGP 社區清單](/azure/expressroute/expressroute-routing)。  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>使用 BGP 社區最常見的案例是什麼？

客戶可以使用 BGP 社區來控制透過 Azure ExpressRoute 其網路接受的 IP 首碼群組，進而影響某些 Office 365 服務的 IP 前置詞計數和預期的頻寬信封。 請務必瞭解，不論使用 Azure ExpressRoute 或 BGP 社區，所有的 Office 365 都需要網際網路系結流量。 下列三個案例是此功能最常見的用法。
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>案例1：將 Office 365 IP 首碼的數目降至最低

Contoso Corporation 是目前使用 Office 365 進行 Exchange Online 和 SharePoint 線上的50000人員公司。 在審校 ExpressRoute 需求中，Contoso 決定其網路裝置在許多區域位置無法處理高於100其他路由專案的路由表大小。 Contoso 檢查 ExpressRoute 會刊登廣告以取得完整的 Office 365 服務集合的 IP 首碼總數，並結束超過100。 為了維持在100其他路由專案底下，Contoso 將使用 ExpressRoute Office 365 的方式，只使用 SharePoint 線上 BGP 社區 value，12076:5020，透過 ExpressRoute Microsoft 對等的方式接收。

|**使用的 BGP 社區標記**|**透過 Azure ExpressRoute 可路由傳送的功能**|**需要網際網路路由**|
|:-----|:-----|:-----|
|SharePoint  <br/>  (12076:5020)   <br/> |SharePoint &amp; 商務 OneDrive 商務  <br/> | DNS、CRL、 &amp; CDN 要求  <br/>  所有其他 Office 365 服務並不是透過 Azure 明確支援 ExpressRoute  <br/>  所有其他 Microsoft 雲端服務  <br/>  Office 365 入口網站、Office 365 驗證、 &amp; office in 瀏覽器  <br/>  Exchange Online、Exchange Online Protection 和商務用 Skype Online  <br/> |

> [!NOTE]
> 若要為每個服務取得較低的前置詞計數，服務之間的重迭量會保持不變。 這是預期會發生的情況。
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>案例2：範圍 ExpressRoute 和內部頻寬用於某些 Office 365 服務

Fabrikam Inc. 是具有分散式異類網路的大型多國企業，是許多 Office 365 服務的訂戶，包含;Exchange Online、SharePoint 線上和商務用 Skype Online。 Fabrikam 的內部路由基礎結構可以在其路由表中處理數以千計的 IP 首碼;不過，Fabrikam 只想要為 Office 365 應用程式布建 ExpressRoute 和內部頻寬，這些應用程式最敏感的是網路效能，而且可對所有其他 Office 365 應用程式使用其現有的網際網路頻寬。
  
基於此原因，Fabrikam 將其 Azure ExpressRoute 頻寬只用于商務用 Skype Online BGP 社區值12076:5030，透過 ExpressRoute Microsoft 對等接收。 其他與 Office 365 相關聯的網路流量，會繼續使用網際網路出局點數。

|**使用的 BGP 社區標記**|**透過 Azure ExpressRoute 可路由傳送的功能**|**需要網際網路路由**|
|:-----|:-----|:-----|
|商務用 Skype  <br/>  (12076:5030)   <br/> |Skype SIP 信號、下載、語音、影片和桌面共用  <br/> | DNS、CRL、 &amp; CDN 要求  <br/>  所有其他 Office 365 服務並不是透過 Azure 明確支援 ExpressRoute  <br/>  所有其他 Microsoft 雲端服務  <br/>  Office 365 入口網站、Office 365 驗證、 &amp; office in 瀏覽器  <br/>  商務用 skype 遙測、Skype 用戶端快速秘訣、公用 IM 連線能力  <br/>  Exchange Online、Exchange Online Protection 及 SharePoint 線上  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>案例3：僅限 Office 365 服務的 Azure ExpressRoute 範圍

Woodgrove Bank 是許多 Microsoft 雲端服務（包括 Office 365）的客戶。 評估其網路容量與消耗 Woodgrove Bank 之後，請決定將 Azure ExpressRoute 當做支援的 Office 365 服務的慣用路徑進行部署。 路由表格可支援完整的 Office 365 IP 首碼集，以及已布建的 Azure ExpressRoute 電路，支援所有預計的頻寬和延遲需求。
  
為了確保與 Microsoft 雲端服務相關聯的網路流量（Office 365 除外），Woodgrove Bank 會將使用 ExpressRoute for Office 365 至所有使用 Office 365 特定 BGP 群組值、12076:5010、12076:5020、12076:5030、12076:5100 標記的 IP 首碼。

|**使用的 BGP 社區標記**|**透過 Azure ExpressRoute 可路由傳送的功能**|**需要網際網路路由**|
|:-----|:-----|:-----|
|Exchange，商務用 Skype & Microsoft 小組，SharePoint， &amp; 其他服務  <br/>  (12076:5010、12076:5020、12076:5030、12076:5100)   <br/> |Exchange Online &amp; Exchange Online Protection  <br/> SharePoint &amp; 商務 OneDrive 商務  <br/> Skype SIP 信號、下載、語音、影片和桌面共用  <br/> Office 365 入口網站、Office 365 驗證、 &amp; office in 瀏覽器  <br/> | DNS、CRL、 &amp; CDN 要求  <br/>  所有其他 Office 365 服務並不是透過 Azure 明確支援 ExpressRoute  <br/>  所有其他 Microsoft 雲端服務  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>使用 BGP 社區的主要規劃考慮

選擇利用 BGP 社區來影響如何透過客戶網路播發和傳播 ExpressRoute 的客戶，應考慮考慮下列考慮事項：
  
- 在您的網路設計中使用 BGP 社區時，務必確定路由對稱性仍然保留。 在某些情況下，BGP 社區的新增或移除可能會造成對稱路由中斷的情況，而且您的路由設定必須更新，以重新建立對稱路由。

- 使用 BGP 群組值來限定 Azure ExpressRoute 是指客戶動作。 不管客戶設定的任何範圍為何，Microsoft 都會通告與對等關係相關聯的所有 IP 首碼。

- Azure ExpressRoute 不會根據客戶指派的 BGP 團體，支援 Microsoft 網路上的任何動作。

- Office 365 使用的 IP 首碼只會以服務特定 BGP 群組值標示，不支援位置特定的 BGP 團體。 Office 365 服務是全域性的，根據租使用者位置或 Office 365 cloud 中的資料篩選首碼是不受支援的。 建議的方法是將您的網路設定為將使用者網路位置的最短或最喜歡的網路路徑與 Microsoft global 網路協調，不論他們所要求的 Office 365 服務的 IP 位址的實際位置為何。

- 每個 BGP 群組值中包含的 IP 首碼代表包含與值相關聯之 Office 365 應用程式的 IP 位址的子網。 在某些情況下，多個 Office 365 應用程式在子網內有多個 IP 位址會產生一個以上的群組值的 IP 前置詞。 這是預期的行為，但很少會因分配分散而造成的行為，而且不會影響前置詞計數或頻寬管理目標。 客戶可以使用「允許什麼」的方法，而不是「拒絕必要的功能」，以利用 Office 365 的 BGP 社區以將影響降至最低。

- 使用 BGP 社區時，不會變更基礎網路連線需求或使用 Office 365 所需的設定。 想要存取 Office 365 的客戶仍然必須能夠存取網際網路。

- 使用 BGP 社區限定 Azure ExpressRoute，只會影響您的內部網路透過 Microsoft 對等關係所能看到的路由。 您可能需要將額外的應用層級設定（例如使用 PAC 或 WPAD 設定）與已設定範圍的路由搭配使用。

- 除了使用 Microsoft 指派的 BGP 社區之外，客戶也可以選擇將自己的 BGP 團體指派給透過 Azure ExpressRoute 所學的 Office 365 IP 首碼，以影響內部路由。 常見的使用案例是針對透過每一種指派的 ExpressRoute 對等位置所獲知的所有路由指派位置，然後使用客戶網路中下游的資訊，將最短或最喜歡的網路路徑與 Microsoft 的網路進行協調。 使用客戶指派的 BGP 社區與 ExpressRoute for Office 365 案例是不在 Microsoft control 或 visibility 範圍範圍內。

您可以使用以下簡短連結回來： [https://aka.ms/bgpexpressroute365]() 。
  
## <a name="related-topics"></a>相關主題

[評估 Office 365 網路連線能力](assessing-network-connectivity.md)
  
[Azure ExpressRoute for Office 365](azure-expressroute.md)
  
[管理 ExpressRoute for Office 365 連線](managing-expressroute-for-connectivity.md)
  
[使用 ExpressRoute for Office 365 進行路由傳送](routing-with-expressroute.md)
  
[使用 ExpressRoute for Office 365 進行網路規劃](network-planning-with-expressroute.md)
  
[商務用 Skype Online 中的媒體品質和網路連線效能](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[商務用 Skype Online 中的 ExpressRoute 與 QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[使用 ExpressRoute 的通話流程](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[實作 ExpressRoute for Office 365](implementing-expressroute.md)
  
[支援 BGP 社區](/azure/expressroute/expressroute-routing)
  
[使用基準與效能歷程記錄進行 Office 365 效能調整](performance-tuning-using-baselines-and-history.md)
  
[Office 365 的效能疑難排解規劃](performance-troubleshooting-plan.md)
  
[Office 365 的 Azure ExpressRoute 訓練](https://channel9.msdn.com/series/aer)