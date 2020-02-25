---
title: 從您的商務用 Office 365 訂閱中移除授權
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 9c64d127-e2dd-4ecc-81f5-2f87e5a74803
description: 了解如何從 Office 365 商務版訂閱移除授權，授權已指派給某人時。
ms.openlocfilehash: d1af1b5696d359daf6578e090180b79587952106
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239736"
---
# <a name="remove-licenses-from-your-office-365-for-business-subscription"></a>從您的商務用 Office 365 訂閱中移除授權

您無法從已指派給使用者的授權從訂閱中移除。 如果您想要移除目前指派給其他人的授權，您需要[移除-授權-從位](../../admin/manage/remove-licenses-from-users.md)使用者） 您可以從訂閱中移除授權之前。

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 **[試用新的系統管理中心] **開關將它開啟。

## <a name="remove-licenses"></a>Remove licenses

1. 在系統管理中心，移至 [帳單]**** \> [產品與服務]<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank"></a> 頁面。

2. 在 [**產品 & 服務**] 頁面上，尋找您要從中移除授權，該的訂閱，然後選取 [**新增/移除授權**。

    [如果沒有看到 [新增/移除授權] 連結該怎麼辦？](#what-if-i-dont-see-the-addremove-licenses-link)

3. 在 [**授權總數**] 方塊中，輸入此訂閱所需的授權總數，然後選取 [**送出變更**。 例如，若您有 110 個授權，而您需要移除 5 個授權，則輸入 105。

::: moniker-end

::: moniker range="o365-germany"

1. 在 [系統管理中心中，移至**帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">訂閱</a>] 頁面。

2. 在 [**訂閱**] 頁面上，選取您要移除授權的訂閱，然後選取 [**新增/移除授權**。

    [如果沒有看到 [新增/移除授權] 連結該怎麼辦？](#what-if-i-dont-see-the-addremove-licenses-link)

3. 在 [**授權總數**] 方塊中，輸入您需要為此訂閱，然後選取 [**送出**的授權總數。 例如，若您有 110 個授權，而您需要移除 5 個授權，則輸入 105。


::: moniker-end

::: moniker range="o365-21vianet"

1. 在 [系統管理中心中，移至**帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">訂閱</a>] 頁面。

2. 在 [**訂閱**] 頁面上，選取您要移除授權的訂閱，然後選取 [**新增/移除授權**。

    [如果沒有看到 [新增/移除授權] 連結該怎麼辦？](#what-if-i-dont-see-the-addremove-licenses-link)

3. 在 [**授權總數**] 方塊中，輸入您需要為此訂閱，然後選取 [**送出**的授權總數。 例如，若您有 110 個授權，而您需要移除 5 個授權，則輸入 105。

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a>如果沒有看到 [新增/移除授權] 連結該怎麼辦？

This section describes the reasons why the **Add/Remove licenses** link might not be available, and what you can do about it.
  
### <a name="a-credit-check-is-pending"></a>正在等待信用查核

如果正在等待信用查核，您會看到「等待信用查核」的訊息，等到信用查核完成後才能移除授權。如果正在等待信用查核，請稍後再回來查看是否已完成信用查核。信用查核通常需要長達兩個工作天的時間才能完成。
  
After the credit check is complete, you should see the **Add/Remove licenses** link in the **Users** section. 如果是的話，請移至[移除從 Office 365 商務版訂閱的授權](#remove-licenses-from-your-office-365-for-business-subscription)。
  
### <a name="you-activated-the-subscription-using-a-product-key"></a>使用產品金鑰啟用您的訂閱

如果訂閱是使用 25 個字元的產品金鑰購買且啟用，您會看到「預付」字樣。如果您的訂閱已使用產品金鑰預付，您將無法移除授權，因為授權已預付。不過，當您續約訂閱時，可以移除額外的授權。
  
### <a name="you-bought-your-subscription-through-a-partner"></a>您是透過合作夥伴購買訂閱

如果透過雲端解決方案提供者或協力廠商購買訂閱，您無法移除授權。 請連絡您的雲端解決方案提供者，或使用大量授權服務中心 (VLSC) 連結來連絡您的合作夥伴取得協助。
  
## <a name="what-you-need-to-know-about-removing-licenses-from-users-in-office-365-for-business"></a>在商務用 Office 365 中將授權從使用者移除的注意事項

- 您必須是全域系統管理員或使用者管理系統管理員。如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

- 請依照這些步驟以新增授權給現有的使用者帳戶。[了解如何在新增使用者帳戶的同時指派授權](../../admin/add-users/add-users.md)。

## <a name="articles-about-managing-licenses-for-your-subscription"></a>管理您的訂閱授權的相關文章

- [了解訂閱與授權](subscriptions-and-licenses.md)

- [從使用者移除授權](../../admin/manage/remove-licenses-from-users.md)

- [將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md)

- [購買訂閱的授權](buy-licenses.md)

- [購買其他訂閱](../buy-another-subscription.md)

- [購買或編輯附加元件](../buy-or-edit-an-add-on.md)

- [管理 Yammer 使用者授權](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)

## <a name="related-links"></a>相關連結

[取消訂閱](../subscriptions/cancel-your-subscription.md)
