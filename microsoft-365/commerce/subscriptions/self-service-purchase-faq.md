---
title: 自助服務購買常見問題集
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: 尋找有關自助購買的常問問題的答案。
ms.openlocfilehash: cbf30a29ed3948cb3b20da919835ed2524163617
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721645"
---
# <a name="self-service-purchase-faq"></a>自助服務購買常見問題集

> [!NOTE]
> 本文中的資訊僅適用於 Microsoft Power 平台 （Power BI、 電源應用程式及自動化 Power） 訂閱。

## <a name="general"></a>一般

### <a name="what-changes-did-microsoft-announce-around-self-service-purchases-for-the-power-platform-products"></a>Microsoft 沒有宣佈何種變更繞自助購買 Power 平台產品？

2019 年 10 月 31 日起更新： 透過過去一週，我們已被聆聽客戶的意見反應，我們自助購買功能推出有關 Power 平台產品。 根據意見反應，我們要對我們計劃進行下列變更：

- 在 11 月 19 日，我們會提供 IT 系統管理員来關閉自助購買透過 PowerShell 以每個產品為基礎的方式。 若要了解如何使用它，請參閱[使用 AllowSelfServicePurchase MSCommerce PowerShell 模組](allowselfservicepurchase-powershell.md)。
- 若要提供更多時間來準備進行這項變更，我們要更新自助購買功能，以開始使用 Power BI 年 1 月 14 的商業雲端的所有客戶的電源平台產品的啟動。  

開始 2020 年 1 月 14，自助購買、 訂閱及電源平台產品 （Power BI、 電源應用程式] 及自動化 Power） 授權管理功能可用於在美國境內的商業雲端客戶。 自助服務購買讓使用者有機會嘗試新技術，並讓他們能夠開發解決方案的最終將優點其較大型的組織。 此功能將無法使用至美國的政府、 非營利組織版或教育版，在這個階段中的租用戶。 中央採購與 IT 團隊必須購買及部署自助購買透過<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>的解決方案，並將能夠關閉自助購買透過 PowerShell 以每個產品為基礎的所有使用者的可見性。

### <a name="why-is-microsoft-adding-a-self-service-purchase-option-for-the-power-platform-products"></a>Microsoft 新增 Power 平台產品的自助購買選項的為何？

在現今的世界，使用者與部門越來越多尋求且購買自行技術解決方案。 我們已接收到來自這些客戶若要啟用自助購買 Power 平台產品許多要求。 我們正在回應客戶需要同時也平衡 IT 管理員，常會可見度與控制時遺失其組織內的個人採用其不知情的情況下的協力廠商解決方案的需求。 電源平台產品即將來臨自助服務的能力，IT 系統管理員必須完成發生在其組織中所有自助購買看得到與組織層級設定的資料控管原則將累至透過自助購買的訂閱。 系統管理員也可以指派現有的授權，或購買額外的訂閱，透過現有的協議和使用者指派給自助購買價格 Power 平台產品。 指派這些集中購買授權之後，系統管理員就可以要求此項採購取消其現有的訂閱。 Microsoft 會探索簡化並在未來簡化系統管理員適用此程序的方式。

### <a name="when-will-self-service-purchase-for-the-power-platform-products-be-available"></a>何時自助購買 Power 平台產品可？

Microsoft 就啟動自助購買 Power bi 2020 年 1 月 14，在美國，客戶與其他市場擴展在接下來的月份。 電源應用程式和電源自動化會加入下列週。 此功能將無法使用至美國的政府、 非營利組織版或教育版，在這個階段中的租用戶。

### <a name="will-self-service-purchase-be-enabled-for-services-beyond-the-power-platform-products"></a>將 Power 平台產品以外的服務啟用自助購買？

現階段，Power 平台系列產品是透過自助服務購買所提供的唯一服務。

## <a name="making-a-self-service-purchase"></a>購買自助服務

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>客戶如何讓自助購買？

客戶能夠進行自助 online 從購買 Microsoft Power BI、 電源應用程式] 及自動化 Power 網站。 客戶，則第一次會要求輸入的電子郵件地址，以確保它們在現有的 Azure Active Directory (AD) 租用戶中的使用者，然後他們就會進入使用 Azure AD 認證登入。 登入之後, 會要求客戶選取多少他們想要購買了解並提供信用卡付款的訂閱。 完成購買程序時，他們可以開始使用其訂閱。 購買者也能夠存取他們可以在此啟用其組織中使用產品的其他人員在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>的有限的檢視。

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>自助服務購買的付款選項為何？

目前，信用卡是唯一可用的付款方式。 不支援透過開立發票付款。

### <a name="who-can-buy-through-self-service-purchase"></a>誰可以購買透過自助服務購買？

任何使用者與非來賓使用者帳戶中受管理的 Azure AD 租用戶可以購買。 此功能將無法使用的是政府、 非營利組織版，租用戶或教育版，這一次。 這適用於您的組織，如果沒有其他巨集指令則需要控制自助購買，這一次。

組織或不合格的自助購買的市場中的使用者會看到訊息來要求他們連絡其 IT 系統管理員，今天一樣。

### <a name="can-guest-users-buy-through-self-service-purchase"></a>來賓使用者可以透過自助服務購買購買？

否，來賓使用者無法完成自助購買它們來賓租用戶中。

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>從內部部署 Active Directory 同步處理的使用者可以透過自助服務購買購買？

如果使用者有作用中使用者帳戶中適用的 Azure AD 租用戶，他們可以完成自助購買。

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>誰可以自助項採購指派授權給？

自助服務項採購只可以將授權指派給相同的 Azure AD 租用戶中的使用者。 購買者能夠存取<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>以指派授權的有限的檢視。 他們將只有可見度，可以將授權指派給他們已購買的透過自助服務購買，這些產品，而且將僅能能夠將這些授權指派給相同的 Azure AD 租用戶中的使用者。

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>自助服務購買者其中檢視及管理其購買？

自助服務項採購可以管理其購買<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>的有限檢視中。 在系統管理中心一律可以取得項採購從所有 Office 365 和 Dynamics 線上應用程式內建 Office 365 app 啟動器中的 [**管理**] 磚。 他們可以檢視他們已進行，購買其他訂閱至相同的服務，並將這些訂閱的授權指派給其組織中其他使用者購買。 此外，項採購可以檢視和支付其 bill，更新其付款方式，並取消其訂閱。

**自助服務項採購有限的 Microsoft 365 系統管理中心檢視：**

![Microsoft 365 系統管理中心的螢幕擷取畫面。](../media/MACBillingProductsServicesSelfServicePurchaseIW.png)

## <a name="pricing"></a>定價

### <a name="what-is-the-pricing-for-self-service-purchases"></a>自助服務購買價格是什麼？

自助購買的產品價格 Power 平台的每個將提供 Microsoft 的網站上的和也會顯示為時進行自助購買結帳體驗的一部分。 這些價格，組織支付時讓中央購買或透過合作夥伴提供的價格價格可能會有所不同。

### <a name="who-is-responsible-for-payment"></a>誰負責付款？

購買透過自助服務購買的訂閱的人員將付款，並負責根據字詞和價格購買的付款。

## <a name="admin-capabilities"></a>系統管理功能

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>自助購買的將是系統管理員必須在哪些功能？

系統管理員可以檢視組織中<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>中進行所有自助購買。 他們可以看到產品、 購買者姓名、 購買的訂閱、 到期日，訂購記錄、 購買價格及每個自助購買指定的使用者。 如有需要為其組織，系統管理員將能夠關閉自助購買透過 PowerShell 以每個產品為基礎。 系統管理員有相同的資料管理，並透過產品購買透過自助服務購買或集中式存取原則。

系統管理員也可以控制組織中的使用者是否可以讓自助購買。 如需詳細資訊，請參閱[使用 AllowSelfServicePurchase MSCommerce PowerShell 模組](allowselfservicepurchase-powershell.md)。

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>如何為 Microsoft 尊重資料控管和合規性藉由啟用自助購買？

系統管理員維護根據其資料控管和合規性需求，而其租用戶中啟用的服務和產品的控制權。 此外，所有的資料管理和存取原則，您的組織已啟用，將會套用至自助購買啟用的服務。

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>建立從自助購買的產品資料擁有者是誰？

建立從透過自助服務購買購買的產品資料所擁有及控制由組織提供。

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>如何將集中購買透過自助服務購買的項目？

系統管理員可以將現有授權指派，或透過現有的協議和價格已指派給自助購買使用者購買其他訂閱的電源平台產品 （Power BI、 電源應用程式] 及自動化 Power）。 指派這些集中購買授權之後，系統管理員就可以要求此項採購取消其現有的訂閱。 Microsoft 會探索簡化並在未來簡化系統管理員適用此程序的方式。

### <a name="where-does-the-admin-see-self-service-purchases"></a>讓系統管理員會看到自助購買？

全域和計費系統管理員可以看到透過自助服務購買**帳單**購買的訂閱 > **產品 & services**在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>中與所有透過管理中心採購購買其他訂閱。 他們可以篩選清單，以透過管理中心採購購買訂閱，或包含透過自助服務購買購買的訂閱。

系統管理員可以看到的產品、 購買者姓名、 訂閱到期日，xxxxx xxxxxxx，購買價格，購買和指派的使用者。

## <a name="support-and-training"></a>支援和訓練

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>是客戶的 IT 部門或協力廠商預期支援透過自助服務購買購買的產品？

IT 部門和協力廠商未預期透過自助服務購買購買的產品提供支援。 Microsoft 會提供自助項採購標準的支援。

### <a name="if-a-self-service-purchaser-calls-support-will-they-use-the-customers-premier-support-incidents"></a>如果自助購買者撥打支援，他們會使用客戶的頂級支援事件的嗎？

自助服務項採購不會使用客戶的頂級支援事件的接收支援，如其自助購買。

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>如何使用者預期會接收透過自助服務購買購買的產品的訓練？

Microsoft Power BI、 電源應用程式] 及自動化 Power 網站上提供廣泛的使用者訓練。 產品有引導您學習、 文件、 範例和直接從其他使用者取得解答和提示的強式社群。

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>會發生什麼情況自助購買如果會在使用者離開組織？

有效的使用者仍然擁有自助購買訂閱期間充分利用。 直到購買者直接取消或系統管理員要求訂閱透過客戶支援取消訂閱仍處於作用中。 系統管理員也可以選擇將集中購買的授權指派給已取消訂閱的使用者。

## <a name="partners"></a>協力程式

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>什麼是自助購買 Microsoft 合作夥伴的角色？

已委派管理的權限的合作夥伴可以看到自助進行購買動作，在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>，就像系統管理員。合作夥伴可協助支援組織想要將集中透過自助服務購買購買的產品。 此外，協力廠商可能會提供解決方案來延伸自助購買的功能。