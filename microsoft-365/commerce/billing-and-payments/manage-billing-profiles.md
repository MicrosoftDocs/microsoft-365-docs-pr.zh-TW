---
title: 了解帳單設定檔
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: 瞭解帳單設定檔如何支援發票。
ms.date: 04/02/2021
ms.openlocfilehash: e66efe12e05d2aaf286b689c955f17c8401144f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537328"
---
# <a name="understand-billing-profiles"></a>了解帳單設定檔

計費設定檔包含付款條件、帳單資訊和其他發票設定，例如購買訂單編號和電子郵件發票偏好設定。 您可以使用計費設定檔來支付您從 Microsoft 購買的產品。 當使用者進行自助購買時，會自動建立帳單設定檔。 每個帳單設定檔都是分開開票的。

> [!NOTE]
>
> 從 Microsoft.com 購買產品和服務的客戶或是在 Microsoft 365 系統管理中心的 [**購買服務**] 頁面上，都無法使用計費設定檔。

## <a name="what-are-billing-profile-roles"></a>什麼是計費設定檔角色？

計費設定檔上的角色具有控制購買的許可權，以及查看和管理發票。 將這些角色指派給追蹤、組織及支付發票的使用者。 例如，您組織中的採購團隊成員。

| 角色                         | 描述                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| 計費設定檔擁有者        | 管理帳單設定檔的所有專案                                          |
| 帳單設定檔參與者  | 管理帳單設定檔中的許可權以外的所有專案                        |
| 計費設定檔讀取器       | 計費設定檔中所有專案的唯讀視圖                                |
| 發票管理員              | 查看和支付帳單，且具有記帳設定檔中所有專案的唯讀視圖  |

## <a name="view-my-billing-profiles"></a>查看我的計費設定檔

> [!NOTE]
>
> 如果您遵循這些步驟，且計費配置檔案清單是空的，則表示您沒有帳單設定檔，且無法使用此功能。

1. 在系統管理中心中，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">[帳單與付款]</a> 頁面。
2. 選取 [ **帳單設定檔** ] 索引標籤，然後從清單中選取帳單設定檔。

每個帳單設定檔都包含下列資訊：

- **計費設定檔名稱和狀態** &ndash; 計費設定檔的唯一名稱，以及計費設定檔是否為使用中或已停用購買的狀態。
- **發票設定** &ndash; 以計費帳戶所在國家/地區為基礎的貨幣、發票頻率和日期的相關資訊、以電子郵件附件形式接收發票的選項，以及選用的 [PO 號碼] 欄位。
- **付款條件** &ndash; 顯示設定檔的主要和備份付款條件（如果有的話）
- **計費帳戶** &ndash; 與設定檔相關的帳單帳戶名稱。 如需計費帳戶的詳細資訊，請參閱 [瞭解帳單帳戶](../manage-billing-accounts.md)。
- **連絡人資訊** &ndash; 帳單位址和連絡人名稱和電子郵件地址
- **計費設定檔角色** &ndash; 指派其中一個計費設定檔角色以執行該設定檔的人員清單。 例如，支付帳單、新增 PO 號碼或取代用來進行購買的支付方式。

> [!NOTE]
>
> 您只可以將計費設定檔角色指派給組織中的使用者。

## <a name="need-help-contact-support"></a>需要協助？ 連絡客戶支援

如果您有任何問題或需要協助您的 Azure 費用，請 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">建立支援 azure 支援的支援要求</a>。

如果您有任何問題或需要協助您 Microsoft 365 系統管理中心的帳單設定檔，請[與支援人員聯繫](../../business-video/get-help-support.md)。

## <a name="related-content"></a>相關內容

[如何使用計費設定檔支付訂閱](pay-for-subscription-billing-profile.md) (文章) \
[瞭解帳單帳戶](../manage-billing-accounts.md) (文章) \
[管理支付方式](manage-payment-methods.md) (文章) 
