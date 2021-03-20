---
title: 管理 ExpressRoute for Office 365 連線
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/13/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: e4468915-15e1-4530-9361-cd18ce82e231
description: 瞭解如何管理 Office 365 的 ExpressRoute，包括設定類似首碼篩選、安全性和符合性等的常見區域。
ms.openlocfilehash: e8de0763df7d592bc41802b1ead48df06891e6dc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916665"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>管理 ExpressRoute for Office 365 連線

ExpressRoute for Office 365 提供備用的路由路徑，以到達許多 Office 365 服務，而不需要將所有流量送出至網際網路。 雖然仍然需要網際網路連線到 Office 365，但 Microsoft 透過 BGP 向您的網路公佈的特定路由會使直接 ExpressRoute 電路成為首選的，除非您的網路中有其他設定。 您可能想要設定以管理此路由的三個常見方面包括前置詞篩選、安全性和符合性。
  
> [!NOTE]
> Microsoft 變更了如何檢查 Azure ExpressRoute 的 Microsoft 對等路由網域。 從2017年7月31日起，所有 Azure ExpressRoute 客戶都可以直接從 Azure 系統管理主控台或透過 PowerShell 啟用 Microsoft 對等功能。 啟用 Microsoft 對等專案後，任何客戶都可以建立路由篩選器，以接收 Dynamics 365 客戶參與應用程式 (以前稱為 CRM Online) 的 BGP 路由播發。 需要 Office 365 Azure ExpressRoute 的客戶必須先從 Microsoft 取得檢查，然後才能建立 Office 365 的路由篩選。 請與您的 Microsoft 帳戶小組聯繫，以瞭解如何要求複查以啟用 Office 365 ExpressRoute。 嘗試建立 Office 365 之路由篩選的未授權訂閱將會收到 [錯誤訊息](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>首碼篩選

Microsoft 建議客戶接受來自 Microsoft 宣告的所有 BGP 路由，並提供嚴格的複查和驗證程式，以消除新增審查的任何好處。 ExpressRoute 本身提供建議的控制項，例如 IP 前置詞擁有權、完整性及擴充-用戶端沒有輸入路由篩選。
  
如果您需要在 ExpressRoute 公開對等之間額外驗證路由擁有權，您可以針對所有 IPv4 的清單 IPv6 及代表 [Microsoft 公用 IP 範圍](https://www.microsoft.com/download/details.aspx?id=53602)的 ip 首碼，檢查宣告的路由。 這些範圍涵蓋完整的 Microsoft 位址空間，並不經常變更，提供一組可篩選的可靠範圍，也為關心非 Microsoft 所擁有之不是 Microsoft 所擁有之路由的客戶，也對其環境提供額外的保護。 在事件發生變更時，會在每個月的第一年進行變更，且每次更新檔時，頁面的 [ **詳細資料** ] 區段中的版本編號都會隨之變更。
  
為了避免使用 [Office 365 URLs 及 IP 位址範圍](./urls-and-ip-address-ranges.md) 以產生首碼篩選清單，有許多原因。 包括下列專案：
  
- Office 365 IP 首碼經常會進行許多變更。

- Office 365 URLs 和 IP 位址範圍的設計是用來管理防火牆允許清單和 Proxy 基礎結構，而非路由傳送。

- [！注意] Office 365 URLs 和 IP 位址範圍並未涵蓋您 ExpressRoute 連線範圍內的其他 Microsoft 服務。

|**選項**|**複雜性**|**變更控制**|
|:-----|:-----|:-----|
|接受所有的 Microsoft 路由  <br/> |**低：** 客戶依賴 Microsoft 控制項，以確保所有路由都已正確擁有。  <br/> |無  <br/> |
|篩選 Microsoft 擁有的 supernets  <br/> |**中：** 客戶實施摘要的首碼篩選清單，只允許 Microsoft 擁有的路由。  <br/> |客戶必須確定路由篩選器中不經常的更新會反映出來。  <br/> |
|篩選 Office 365 IP 範圍  <br/> [!CAUTION] Not-Recommended |**高：** 客戶會根據定義的 Office 365 IP 首碼來篩選路由。  <br/> |客戶必須執行每月更新的可靠的變更管理程式。  <br/> [!CAUTION] 此解決方案需要大量的更新。 未在時間執行的變更可能會導致服務中斷。   |

使用 Azure ExpressRoute 連線到 Office 365 是根據特定 IP 子網的 BGP 廣告，其代表部署 Office 365 端點的網路。 由於 Office 365 的全域性質及組成 Office 365 的服務數目，客戶常常需要在其網路上管理其所接受的廣告。 如果您關心的是在您的環境中宣告的首碼數目，則 [BGP 社區](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) 功能可讓您將廣告篩選成一組特定的 Office 365 服務。 這項功能現在已在預覽中。
  
不論您管理來自 Microsoft 的 BGP 路由廣告的方式為何，當您與透過網際網路線路上的 Office 365 進行比較時，您就不會對 Office 365 服務帶來任何特殊的公開。 不管客戶用來連線至 Office 365 的電路類型為何，Microsoft 都會維持相同的安全性、相容性和效能等級。
  
### <a name="security"></a>安全性

Microsoft 建議您維護您自己的網路和安全性周邊控制，以供出入 ExpressRoute 公開和 Microsoft 對等的連線，其中包括 Office 365 服務的連線。 安全性控制措施應該是針對從您的網路送出至 Microsoft 網路的網路要求，以及從 Microsoft 網路到您網路的輸入。
  
#### <a name="outbound-from-customer-to-microsoft"></a>從客戶輸出至 Microsoft
  
當電腦連線到 Office 365 時，無論連線是透過網際網路或 ExpressRoute 電路進行，都可以連接到同一組端點。 不論使用哪一種電路，Microsoft 建議您將 Office 365 服務視為比一般網際網路目的地更為信任。 您的外寄安全性控制措施應重點放在埠和通訊協定上，以降低曝光並最小化不斷維護。 必要的埠資訊可在 [Office 365 端點](./urls-and-ip-address-ranges.md) 參考文章中取得。
  
針對新增的控制項，您可以使用 proxy 基礎結構內的 FQDN 層級篩選，來限制或檢查部分或所有網路要求，以用於網際網路或 Office 365。 維護 Fqdn 清單時，隨著功能的發行和 Office 365 產品的演化，需要更強大的變更管理，並追蹤發佈的 [Office 365 端點](./urls-and-ip-address-ranges.md)所做的變更。
  
> [!CAUTION]
> Microsoft 建議您不要只依賴 IP 首碼來管理 Office 365 的輸出安全性。

|**選項**|**複雜性**|**變更控制**|
|:-----|:-----|:-----|
|無限制  <br/> |**低：** 客戶可對 Microsoft 進行無限制的輸出存取。  <br/> |無  <br/> |
|埠限制  <br/> |**低：** 客戶利用預期的埠限制對 Microsoft 的輸出存取。  <br/> |罕見。  <br/> |
|FQDN 限制  <br/> |**高：** 客戶根據發佈的 Fqdn 來限制對 Office 365 的輸出存取。  <br/> |每月變更。  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>從 Microsoft 到客戶的輸入
  
有幾種選用的案例需要 Microsoft 啟動網路連線。
  
- 在登入密碼驗證期間的 ADFS。

- [Exchange Server 混合部署](/exchange/exchange-hybrid)。

- 將 Exchange Online 租使用者的郵件傳送至內部部署主機。

- 線上郵件 SharePoint 從 SharePoint 線上傳送至內部部署主機。

- [SharePoint 同盟混合式搜尋](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online)。

- [SharePoint 混合式 BCS](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution)。

- [商務用 skype 混合](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 式和/或 [商務用 skype 同盟](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。

- [商務用 Skype 雲端連接器](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)。

Microsoft 建議您透過網際網路電路接受這些連線，而不是 ExpressRoute 電路，以降低複雜性。 若您的相容性或效能需求規定必須透過 ExpressRoute 電路接受這些輸入連線，則建議使用防火牆或反向 proxy 來限定已接受的連線的範圍。 您可以使用 [Office 365 端點](./urls-and-ip-address-ranges.md) 來判斷正確的 FQDN 和 IP 首碼。
  
### <a name="compliance"></a>合規性

我們不依賴您用於任何符合性控制的路由路徑。 不論您是透過 ExpressRoute 或網際網路電路連接至 Office 365 服務，我們的規範控制措施都不會變更。 您應該檢查 Office 365 的不同法規遵從性和安全性認證等級，以找出符合組織需求的最佳選擇。
  
您可以使用下列短連結返回這裡：[https://aka.ms/manageexpressroute365]()
  
## <a name="related-topics"></a>相關主題

[內容傳遞網路](content-delivery-networks.md)
  
[Office 365 URL 與 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[管理 Office 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Office 365 的 Azure ExpressRoute 訓練](https://channel9.msdn.com/series/aer)