---
title: 了解您的帳單或發票
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 了解如何閱讀及了解您的 Microsoft 商務產品帳單或發票。
keywords: 帳單帳戶、組織資訊、發票
ms.openlocfilehash: 80b7e4f14390e2f695dc753358f9e5bebe055bd0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638408"
---
# <a name="understand-your-bill-or-invoice"></a>了解您的帳單或發票

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end

發票提供您的費用及付款指示摘要。 您可以在 Microsoft 365 系統管理中心[檢視您的線上發票](#view-your-online-invoice)。 您也可以以可攜式文件格式 (.pdf)下載它，以透過電子郵件傳送。

如果您只有 Microsoft 365 訂閱，請參閱[了解您的商務用 Microsoft 365 帳單或發票](understand-your-invoice2.md)。

## <a name="understand-the-invoice-header"></a>了解發票標頭

第一頁的頂端可識別負責付款的人員、傳送帳單的位置，以及費用摘要。

| 術語 | 描述 |
| --- | --- |
| 購買人 |帳單帳戶，可識別負責付款之法人實體的名稱和地址。 您可以在 [帳單帳戶<a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">]</a> 頁面上管理此資訊，在其中您可以找到帳戶合約及管理角色和權限。 |
| 帳單地址 |識別誰會接收發票。 您可以在 [帳單設定檔<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">]</a> 頁面上管理此資訊。 帳單設定檔也會顯示在 [線上發票] 頁面上的 [發票摘要 **]** 區段中。 若要深入了解帳單設定檔，以及如何使用其來為您的組織建立更靈活的帳單選項，請參閱[管理帳單設定檔](manage-billing-profiles.md)。 |
| 帳單設定檔 |帳單設定檔的名稱，用來定義發票屬性，例如 **帳單地址**、**PO 編號**，以及付款條件等。 您可以在 [帳單設定檔<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">]</a> 頁面上管理此資訊。 如需帳單設定檔的詳細資訊，以及如何使用其來為您的組織建立更靈活的帳單選項，請參閱[管理帳單設定檔](manage-billing-profiles.md)。 |
| 發票號碼 |用於追蹤用途的唯一、Microsoft 產生的發票號碼。 |
| 發票日期 |產生發票的日期，通常是在帳單週期結束的 5 到 12 天。 您可以在帳單設定檔明細頁面上查看您的發票日期。 發生在計費週期結束和發票日期之間的費用，會包含在下個月的發票中，因為它們處於下一個計費週期。 每個發票的計費週期開始和結束日期會列在 [帳單摘要 **]** 的發票 PDF 上方。|
| 付款條件 |您支付 Microsoft 帳單的方式。 *淨 30 天* 表示您需在發票日期的 30 天內遵循發票上的指示付款。 |

## <a name="understand-the-billing-summary"></a>了解帳單摘要

[帳單摘要 **]** 會顯示自上次計費週期的費用摘要、套用的任何點數、稅金和總應付金額。

| 術語 | 描述 |
| --- | --- |
| 費用|此計費週期購買的產品總數及其相關的費用與稅金。 彙總購買以提供您的帳單的精簡檢視。 |
| 點數 |從退貨獲得的點數 |
| 套用的 Azure 點數 |自動套用到每個計費週期 Azure 費用的您的 Azure 點數。 如果您沒有任何 Azure 點數，則會隱藏此欄位。 如需有關 Azure 點數的詳細資訊，請參閱[追蹤 Microsoft 客戶合約 Azure 點數餘額](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance)。 |
| 小計 |稅前應付金額 |
| 稅金 |根據您的帳單設定檔國家/地區所支付的稅務類型和金額。 如果您不需要支付稅金，您的發票上就不會顯示稅金。 |

### <a name="understand-your-charges"></a>了解您的費用

費用頁面會依產品顯示成本劃分。 若為 Azure 客戶，費用可能會依發票區段組織。 如需有關發票區段如何搭配 Azure 產品使用的詳細資訊，請參閱[開始使用您的 Microsoft 客戶合約帳單帳戶](https://docs.microsoft.com/azure/billing/billing-mca-overview)中的[發票區段](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections)。 在每個產品訂單內，成本會依服務系列劃分。

| 術語 |描述 |
| --- | --- |
| 單價 | 用來計算費用的服務有效單價 (以價格貨幣表示)。 此價格是產品、服務系列、計量和方案所特有。 |
| 數量 | 在計費週期期間購買或消耗的數量 |
| 費用/點數 | 套用點數/退款之後的費用淨額 |
| Azure 點數 | 套用至費用/點數的 Azure 點數金額 |
| 稅率 | 稅率，視國家/地區而定 |
| 稅額 | 根據稅率套用到購買的稅額 |
| 總計 | 購買的總應付金額 |

根據向您收費的產品類型而定，行項目的明細會有所不同。 例如，針對 Azure 產品，將會顯示所套用的 Azure 點數金額。 以基座為基礎的產品，顯示單價和數量。 發票明細會顯示所購買的產品、套用的折扣或點數、稅率和金額，以及行項目總計。

> 總計 = 費用 - Azure 點數 + 稅金

每個服務系列的總應付金額計算方式為從點數/費用中減去 Azure 點數，並加上稅金：

> 總計 = 費用/點數 - Azure 點數 + 稅金

如果您要在發票上顯示更多明細，請參閱[檢閱您的 Microsoft 客戶合約發票](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill)。

## <a name="understand-the-last-invoice-page"></a>了解最後一個發票頁面

### <a name="payment-instructions"></a>付款指示

在發票底部提供如何支付帳單的指示。 您可以使用轉帳、支票或線上付款。

### <a name="publisher-information"></a>發行者資訊

如果在您的帳單中有第三方服務，則每個發行者的名稱和地址會列在發票底部。

## <a name="view-your-online-invoice"></a>檢視您的線上發票

線上提供發票。 您可以從您的 PDF 發票和電子郵件通知取得線上發票的連結。 線上發票可展開，因此您可以檢視發票上的費用，並查看每個項目的明細。 線上發票包括：

- **定價明細**&mdash;包含有關折扣和產品價格明細的額外資訊。

- **線上付款**&mdash;您可以選擇從發票進行線上付款。

- **Azure 成本管理**&mdash;針對 Azure 客戶，線上發票會包含 Azure 成本管理的連結。

### <a name="to-view-your-online-invoice"></a>檢視您的線上發票

1. 在系統管理中心中，移至 [帳單 **]** \> [帳單與付款 <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">]</a> 頁面。

2. 若要下載 .pdf 版本發票，請在您想要查看的發票列中選擇 [下載發票 PDF **]**。

3. 若要檢視您的線上發票，請從清單中選擇發票。 您也可以從發票明細頁面下載 .pdf。

## <a name="invoice-faq"></a>發票常見問題集

### <a name="when-is-my-invoice-available"></a>何時可以取得我的發票？

部分發票會在購買後 24 小時內產生。 其他發票會在計費週期結束時產生，並包含該期間的所有項目。

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>我如何支付發票上的應付金額？

付款指示取決於您的付款方式，且會在發票 PDF 底部提供。 如果您的付款方式是信用卡，則會在發票日期的 10 天內自動請款。 如果您的付款方式是透過支票或轉帳，請參閱 PDF 中 **付款指示** 底下的資訊。

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>「購買人」與「帳單地址」地址之間有何不同？

- **購買人：** 負責付款並可在發票上識別的法人實體。 除非您在購買過程中選擇提供備用的交貨地址，否則會使用此處提供的地址來判斷您的稅率。 如需詳細資訊，請參閱[稅務資訊](tax-information.md)。
- **付款人：** 寄送實體發票的地址 (如果適用)。 每個法人實體可能會有多個 **帳單地址**，但每個帳單設定檔只能有一個 **帳單地址**。

### <a name="what-are-billed-amount-and-amount-due"></a>「計費金額」和「應付金額」是什麼？

- **計費金額：** 購買的總金額。
- **應付金額：** 積欠款項的餘額。

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>「服務期間」與「計費週期」之間的差異為何？

- **服務期間：** 向您收費以使用服務的期間。
- **計費週期：** 上次發票日期之後的期間。

### <a name="how-do-i-view-and-print-my-bill"></a>如何檢視及列印我的帳單？

1. 在 [帳單 **]**  >  [帳單與付款<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">]</a> 頁面上，選取發票日期範圍。
2. 若要列印或儲存帳單的 PDF 複本，請選取 [下載發票 PDF **]**，然後列印 PDF。

若要深入了解，請參閱[檢視您的帳單或發票](view-your-bill-or-invoice.md)。

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>為什麼我看不到 Azure 預付款做為付款方式？

只有合格的 Azure 產品和服務才可使用 Azure 預付款做為付款方式。

## <a name="need-help-contact-support"></a>需要協助？ 連絡客戶支援。

如果您有 Azure 點數的問題或需要相關協助，請<a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">向用 Azure 支援建立支援要求</a>。

如果您有 Microsoft 365 系統管理中心中發票的問題或需要協助，請[連絡商務產品的客戶支援](../../admin/contact-support-for-business-products.md)。