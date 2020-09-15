---
title: 自助購買常見問題
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: 尋找有關自助購買的常見問題的答案。
ms.date: 09/15/2020
ms.openlocfilehash: 81143dfe3794bc4f42bea879905bf08750f498b4
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816922"
---
# <a name="self-service-purchase-faq"></a>自助購買常見問題

自助購買讓使用者有機會嘗試新的技術，並開發最終受益于組織規模較高的解決方案。 中央採購和 IT 小組可透過 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>購買及部署自助購買解決方案的所有使用者都能看到。 系統管理員可以透過 PowerShell 關閉以每個產品為基礎的自助購買服務。 若要深入瞭解，請參閱 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。

自助購買可用於 Power Platform (Power BI、Power App 及 Power) 、Project 和 Visio 的自動功能。

> [!NOTE]
> 在印度或政府或教育版客戶中，無法使用自助購買服務。 Project 和 Visio 不適用於巴西的自助購買和剛果民主共和國。

## <a name="making-a-self-service-purchase"></a>進行自助購買

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>客戶如何進行自助購買？

客戶可以從產品網站或從應用程式購買提示中，讓自助購買線上。 客戶會先要求輸入電子郵件地址，以確保他們是現有 Azure Active Directory (AD) 租使用者中的使用者。 接下來，他們會使用 Azure AD 認證，導向使用者登入。 登入後，系統會要求客戶選取他們想要購買的訂閱數目，並提供信用卡付款。 購買完成後，即可開始使用其訂閱。 買方可以存取 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a> 的有限查看權，讓他們可以將授權指派給組織中的其他人。

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>自助購買的付款選項為何？

目前，信用卡是唯一可用的支付方式。 不支援透過開具發票付款。

### <a name="who-can-buy-through-self-service-purchase"></a>誰可以透過自助購買購買？

在受管理 Azure AD 租使用者中具有非來賓使用者帳戶的任何使用者，都可以進行自助購買。 「自助購買」不適用於政府或教育組織的承租人。 如果這適用于您的組織，則不需要其他動作即可控制自助購買。

不適合自助購買之組織或市場中的使用者，請參閱訊息要求他們聯繫其 IT 管理員。

### <a name="can-guest-users-buy-through-self-service-purchase"></a>來賓使用者是否可以透過自助購買購買？

否，來賓使用者無法在其為來賓的承租人中完成自助購買。

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>使用者是否可以透過自助購買從內部部署的 Active Directory 購買？

如果使用者在合格的 Azure AD 租使用者中有使用中的使用者帳戶，他們就可以完成自助購買。

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>誰可以自行服務購買指派授權？

自助購買只能將授權指派給相同 Azure AD 租使用者中的使用者。 買方可以存取 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a> 的有限視圖，以指派授權。 「購買者」可以將授權指派給他們透過自助購買購買的產品，而且只能將這些授權指派給相同 Azure AD 租使用者中的使用者。

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>自助買方如何查看和管理其購買情況？

自助購買可在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>的有限顯示中管理其購買。 「購買者」可以從內置於所有 Microsoft 365 和 Dynamics online 應用程式的應用程式啟動器中的系統 **管理** 磚，取得系統管理員中心的連線。 「購買者」可以查看他們所進行的購買、購買相同服務的其他訂閱，並將這些訂閱的授權指派給其組織中的其他使用者。 此外，「購買者」可以查看和支付帳單、更新其支付方式，以及取消訂閱。

## <a name="pricing"></a>定價

### <a name="what-is-the-pricing-for-self-service-purchases"></a>自助購買的定價為何？

Microsoft 網站提供每項自助購買產品的定價。 當使用者進行自助購買時，價格也會顯示為結帳體驗的一部分。 這些價格可能會與組織購買合作夥伴所提供的中央購買或價格時所支付的價格不同。

### <a name="who-is-responsible-for-payment"></a>誰負責付款？

透過「自助購買」購買訂閱的人員是已記帳的人員，並根據購買的條款及定價負責付款。

## <a name="admin-capabilities"></a>系統管理功能

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>管理員對自助購買有哪些功能？

系統管理員可以在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>的組織中，查看其組織中所進行的所有自助購買。 他們可以查看產品、購買購買的訂閱、到期日、訂單記錄、購買價格，以及每個自助購買的指派使用者。 在 [電源平臺系統管理中心] 中，系統管理員也可以查看自助購買容量。 根據組織的需要，系統管理員可以透過 PowerShell 關閉以每個產品為基礎的自助購買服務。 管理員透過自助購買或集中購買的產品，都具有相同的資料管理和存取原則。

系統管理員也可以控制組織中的使用者是否可以進行自助購買。 如需詳細資訊，請參閱 [Use AllowSelfServicePurchase For MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Microsoft 如何透過啟用自助購買來尊重資料控管和合規性？

系統管理員可以根據其資料控管和合規性需求，控制其承租人中提供哪些服務和產品。 您的組織開啟的所有資料管理和存取原則，都適用于可用的自助購買服務。

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>誰擁有從自助購買建立的產品資料？

從透過自助購買購買的產品所建立的資料，由組織擁有及控制。

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>如何集中購買透過「自助購買」所進行的購買？

管理員可以指派現有的授權，或透過現有的合約和定價為指派給自助購買的使用者，購買自助購買產品的其他訂閱。 在指派這些已集中購買的授權之後，系統管理員就可以要求購買者取消其現有的訂閱。

### <a name="where-does-the-admin-see-self-service-purchases"></a>系統管理員會在何處購買自助服務？

通用和計費系統管理員可以查看透過「自助購買」購買的**Billing**訂閱，以在  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>計費您的**產品**。 他們可以篩選 [產品] 清單，只顯示透過中央購買購買的訂閱，或包含透過「自助購買」購買的訂閱。

系統管理員可以查看產品、買方名稱、購買的訂閱、到期日、訂單記錄、購買價格，以及指派的使用者。

## <a name="support-and-training"></a>支援和訓練

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>客戶的 IT 部門或合作夥伴是否預計能夠支援透過自助購買購買的產品？

IT 部門和合作夥伴不會期望對透過自助購買購買的產品提供支援。 Microsoft 提供自助購買服務的標準支援。

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>如果自助買方致電支援，是否會使用客戶的「Premier 支援」事件？

自助購買者不會使用客戶的「Premier 支援」事件來接收自助購買的支援。

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>使用者期望透過自助購買購買的產品，如何接收訓練？

產品網站上提供豐富的使用者訓練。 產品已引導教學、檔、範例及強大的社區，以直接從其他使用者取得答案和秘訣。

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>使用者離開組織時，自助購買會發生什麼事？

如果最初購買自助購買產品的人員離開組織，有效的使用者會在訂閱期間繼續完整使用產品。 在買方直接取消服務，或系統管理員要求取消透過客戶支援的訂閱時，訂閱仍會保持使用中狀態。 系統管理員也可以選擇將已集中購買的授權指派給已取消之訂閱的使用者。

## <a name="partners"></a>協力程式

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Microsoft 合作夥伴在自助購買方面的角色為何？

委派管理許可權的合作夥伴可以在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>中查看自助購買，就像是管理員一樣。合作夥伴可協助您支援要集中使用自助購買購買的產品的組織。 此外，協力廠商可提供可擴充自助購買功能的解決方案。