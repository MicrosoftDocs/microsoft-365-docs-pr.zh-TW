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
ms.openlocfilehash: 36d762e50627763b7856ed1fe6c109e8da2b4789
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332027"
---
# <a name="understand-billing-profiles"></a>了解帳單設定檔

針對從 Microsoft 購買產品和服務的商業客戶，計費設定檔可讓您自訂發票上包含的專案，以及您支付發票的方式。

計費設定檔包含下列資訊：

- **計費帳戶** &ndash; 設定檔相關的帳單帳戶名稱
- **付款條件** &ndash; 信用卡或借貸卡、銀行帳戶、支票或電匯
- **連絡人資訊** &ndash; 帳單位址和連絡人名稱
- **發票設定** &ndash; 以計費帳戶的國家/地區為基礎的貨幣、選擇性的 PO 編號，以及以電子郵件附件形式接收發票的選項
- **許可權** &ndash; 可讓您變更帳單設定檔、支付帳單或使用計費設定檔中的付款條件進行購買的許可權

使用計費設定檔來控制購買及自訂發票。 每月發票會產生為以帳單設定檔購買的產品。 您可以自訂發票，例如更新採購訂單編號和電子郵件發票偏好設定。

您第一次購買時，會自動為您的帳單帳戶建立帳單設定檔。 您可以在 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">帳單設定檔</a> ] 頁面上建立計費設定檔，以設定更多發票。 例如，您可以在您為組織中的每個部門進行購買時使用不同的帳單設定檔。 在您下一個帳單日期，您會收到每個帳單設定檔的發票。

## <a name="billing-profile-roles"></a>計費設定檔角色

計費設定檔上的角色具有控制購買的許可權，以及查看和管理發票。 將這些角色指派給追蹤、組織和支付發票的使用者，例如組織中的採購團隊成員。

| 角色                         | 描述                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| 計費設定檔擁有者        | 管理帳單設定檔的所有專案                                          |
| 帳單設定檔參與者  | 管理帳單設定檔中的許可權以外的所有專案                        |
| 計費設定檔讀取器       | 計費設定檔中所有專案的唯讀視圖                                |
| 發票管理員              | 查看和支付帳單，且具有記帳設定檔中所有專案的唯讀視圖  |

## <a name="view-billing-profiles"></a>查看帳單設定檔

1. 在系統管理中心中，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">[帳單與付款]</a> 頁面。
2. 選擇 [ **帳單設定檔**]，然後從清單中選擇帳單設定檔。

    - 在 [ **概覽** ] 索引標籤上，您可以編輯帳單設定檔詳細資料，並開啟或關閉透過電子郵件傳送發票的功能。
    - 在 [ **許可權** ] 索引標籤上，您可以將角色指派給使用者以支付發票。
    - 在 [ **azure 信用平衡** ] 索引標籤上，Azure 客戶可以查看該帳單設定檔使用之 Azure 點數的交易餘額歷史記錄。
    - 在 [ **azure 信用** ] 索引標籤上，Azure 客戶可以查看與該帳單設定檔相關聯的 Azure 信用名單及其到期日期。

    > [!NOTE]
    > 如果您沒有任何 Azure 信用，您就不會看到 [ **azure 貸方餘額** ] 或 [ **azure 信用** ] 索引標籤。

## <a name="need-help-contact-support"></a>需要協助？ 連絡客戶支援

如果您有任何問題或需要協助您的 Azure 費用，請 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">建立支援 azure 支援的支援要求</a>。

如果您有任何疑問或需要協助您使用 Microsoft 365 系統管理中心的帳單設定檔，請 [聯繫商務產品支援](../../business-video/get-help-support.md)人員。
