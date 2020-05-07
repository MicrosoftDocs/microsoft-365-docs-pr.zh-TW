---
title: 管理訂閱授權
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
ms.custom:
- SaRA
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 36081d8d-b3fa-4948-8c34-e217bba825e1
description: 瞭解如何新增及移除 Microsoft 365 for business 訂閱的授權。
ms.openlocfilehash: f8ae177052be325673af96d9535f25dfcdc93180
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141230"
---
# <a name="manage-subscription-licenses"></a>管理訂閱授權

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心變更。 [！附注] 如果您的經驗不符合這裡所述的詳細資料，請參閱[關於新的 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

您可以使用這些步驟，從您的訂閱中新增或移除授權。

您無法從已指派給使用者的授權從訂閱中移除。 如果您想要移除目前指派給某人的授權，您必須先[移除使用者](../../admin/manage/remove-licenses-from-users.md)的授權，然後才能從訂閱中移除授權。

## <a name="add-or-remove-licenses-for-your-business-subscription"></a>新增或移除商務用訂閱的授權

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 [**帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">產品</a>] 頁面。

2. 在 [**產品**] 頁面上，尋找您要新增或移除授權的訂閱，然後選取 [**新增/移除授權**]。

    [如果沒有看到 [新增/移除授權] 連結該怎麼辦？](#what-if-i-dont-see-the-addremove-licenses-link)

3. 在 [**授權總數**] 方塊中，輸入此訂閱所需的授權總數，然後選取 [**提交變更**]。 For example, if you have 100 licenses and you need to add 5 more, enter 105. 如果您想要移除5項，請輸入95。

購買新的授權之後，請務必[將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md)。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，前往 [帳單]**** \> [訂閱]<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank"></a> 頁面。

2. 在 [**訂閱**] 頁面上，選取您要新增或移除授權的訂閱，然後選取 [**新增/移除授權**]。

    [如果沒有看到 [新增/移除授權] 連結該怎麼辦？](#what-if-i-dont-see-the-addremove-licenses-link)

3. 在 [**授權總數**] 方塊中，輸入此訂閱所需的授權總數，然後選取 [**提交** \> **關閉**]。 For example, if you have 100 licenses and you need to add 5 more, enter 105. 如果您想要移除5項，請輸入95。

購買新的授權之後，請務必[將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md)。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，前往 [帳單]**** \> [訂閱]<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank"></a> 頁面。

2. 在 [**訂閱**] 頁面上，選取您要新增或移除授權的訂閱，然後選取 [**新增/移除授權**]。

    [如果沒有看到 [新增/移除授權] 連結該怎麼辦？](#what-if-i-dont-see-the-addremove-licenses-link)

3. 在 [**授權總數**] 方塊中，輸入此訂閱所需的授權總數，然後選取 [**提交** \> **關閉**]。 For example, if you have 100 licenses and you need to add 5 more, enter 105. 如果您想要移除5項，請輸入95。

購買新的授權之後，請務必[將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md)。

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a>如果沒有看到 [新增/移除授權] 連結該怎麼辦？

下表說明 [**新增/移除授權**] 連結可能無法使用的原因，以及您可以採取的措施。 

|原因  |描述  |解決方案  |
|---------|---------|---------|
|已擱置信用檢查。 |如果正在等待信用查核，您會看到「等待信用查核」的訊息，等到信用查核完成後才能購買授權。  | 稍後再次查看，查看是否已完成信用檢查。 信用查核通常需要長達兩個工作天的時間才能完成。<br>After the credit check is complete, you should see the **Add/Remove licenses** link in the **Users** section. 如果是的話，請移至[管理訂閱授權](#manage-subscription-licenses)。 |
|您已使用產品金鑰啟用訂閱。| 如果訂閱是使用 25 個字元的產品金鑰購買且啟用，您會看到「預付」字樣。  |請參閱[將授權新增至使用產品金鑰支付的訂閱](add-licenses-using-product-key.md)。 |
|您是透過合作夥伴購買訂閱。 | 如果透過合作夥伴購買訂閱，您將會看到大量授權服務中心 (VLSC) 連結。 | 請參閱[透過大量授權服務中心新增授權至購買的訂閱](add-licenses-bought-through-vlsc.md)。 |
|您已透過轉銷商購買訂閱。|| 如果透過雲端解決方案提供者 (CSP) 合作夥伴購買訂閱，必須與 CSP 連絡才能購買其授權。        |
|您有試用版訂閱。 |Microsoft 365 的試用版會顯示「試用」文字。 | 您必須先購買您的試用訂閱，然後才可以新增更多授權。 請參閱[從免費試用版購買為商務用 Microsoft 365 的訂閱](../buy-a-subscription-from-your-free-trial.md)。|

## <a name="what-you-need-to-know-about-buying-licenses-for-your-business-subscription"></a>購買商務用訂閱的授權所需注意的事項

### <a name="buying-licenses"></a>購買授權

- 您必須是全域系統管理員或計費系統管理員，才可購買授權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
- 若要購買授權並同時將新使用者新增至您的訂閱，請參閱[個別加入使用者或大量 Microsoft 365-系統管理](../../admin/add-users/add-users.md)說明。

### <a name="license-availability"></a>授權可用性

- 如果您是以信用卡或銀行帳戶支付訂閱費用，在收到訂單確認後，就可立刻使用所購買的所有新授權。 如果您的訂閱付款方式是使用發票，您可能需要等待信用查核，然後才能使用新授權。

  > [!NOTE]
  > 銀行帳戶付款不適用於部分國家或地區。

- 如果您使用產品金鑰預付訂閱，您可以新增信用卡或銀行帳戶來新增更多授權，以涵蓋額外的新授權成本。 當您購買新授權後，系統會列出第二個訂閱和您剛剛新增的新授權數。 舉例來說，如果您的預付訂閱有 5 個授權，且您另外購買了 10 個授權，您就會看到畫面上列出兩個訂閱：一個訂閱有 5 個預付授權，另外一個則有 10 個新授權。

### <a name="billing-statements"></a>帳單報表

- 如果您是以信用卡或銀行帳戶支付費用，新授權的購買費用會在兩天內計入您的付款方式。
- 如果您是以發票支付費用，新授權的購買費用會計入您的下一筆帳單記錄。
- 如果您在計費期間購買新授權，您的第一筆帳單記錄可能會出現部分費用。餘款則會計入您的下一筆帳單記錄。

## <a name="related-articles"></a>相關文章

[了解訂閱與授權](subscriptions-and-licenses.md)

[購買訂閱的授權](buy-licenses.md)

[購買其他訂閱](../buy-another-subscription.md)

[將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md)

[管理 Yammer 使用者授權](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
