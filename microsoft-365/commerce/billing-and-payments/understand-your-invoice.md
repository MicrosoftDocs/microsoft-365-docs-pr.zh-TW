---
title: 認識您的帳單或發票
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
description: 瞭解如何閱讀和瞭解 Microsoft 商務產品的帳單或發票。
keywords: 計費帳戶、組織資訊、發票
ms.openlocfilehash: 80b7e4f14390e2f695dc753358f9e5bebe055bd0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638408"
---
# <a name="understand-your-bill-or-invoice"></a>認識您的帳單或發票

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end

該發票提供您的費用和付款指示的摘要。 您可以在 Microsoft 365 系統管理中心中 [查看您的線上發票](#view-your-online-invoice) 。 您也可以透過電子郵件傳送，以便攜檔案格式 ( .pdf) 下載。

如果您只有 Microsoft 365 訂閱，請參閱 [瞭解您的帳單或發票（適用于商務用 microsoft 365](understand-your-invoice2.md)）。

## <a name="understand-the-invoice-header"></a>瞭解發票標頭

第一頁的頂端會識別負責付款的人員、計費傳送至的人員，以及費用的摘要。

| 字詞 | 描述 |
| --- | --- |
| 銷售至 |用來識別負責付款之法人的名稱和位址的帳單帳戶。 您可以在 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">帳單帳戶</a> ] 頁面上管理此資訊，您可以在其中找到帳戶合約和管理角色和許可權。 |
| 付款人 |識別接收發票的人員。 此資訊可在 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">帳單設定檔</a> ] 頁面上管理。 計費設定檔也會顯示在 [線上發票] 頁面上的 [ **發票摘要** ] 區段中。 若要深入瞭解計費設定檔，以及如何使用它們為您的組織建立更靈活的計費選項，請參閱 [Manage 計費設定檔](manage-billing-profiles.md)。 |
| 計費設定檔 |用來定義發票內容（如 **付款人**、 **PO 編號**及付款條款）的計費設定檔名稱。 此資訊可在 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">帳單設定檔</a> ] 頁面上管理。 如需計費設定檔的詳細資訊，以及如何使用它們為組織建立更靈活的帳單選項，請參閱 [管理帳單設定檔](manage-billing-profiles.md)。 |
| 發票編號 |用於追蹤用途的唯一 Microsoft 所產生的發票編號。 |
| 發票日期 |產生發票的日期，通常為記帳週期結束後的5到12天。 您可以在 [帳單設定檔詳細資料] 頁面上檢查您的開票日期。 在下個月的發票中包含計費期間結束之間所發生的費用，因為它們在下一個計費期間內。 每張發票的帳單的開始和結束日期都會列于上述發票上的 **計費摘要**中。|
| 付款條款 |您為 Microsoft 帳單付費的方式。 *30* 天表示您在發票上的30天內，依照發票上的指示支付。 |

## <a name="understand-the-billing-summary"></a>瞭解帳單摘要

**計費摘要**會顯示自上次計費期間、所套用的任何貸方、稅金和到期總額的費用摘要。

| 字詞 | 描述 |
| --- | --- |
| 收費|為此帳單期限購買的產品總數，以及其相關的費用和稅款。 匯總購買以提供您的帳單的簡潔觀點。 |
| 參與名單 |您從傳回獲得的學分 |
| 應用 Azure 信用 |您的 Azure 信用，會自動套用至 Azure 每個計費期間的費用。 如果您沒有任何 Azure 信用，此欄位是隱藏的。 如需 Azure 信用的詳細資訊，請參閱 [追蹤 Microsoft 客戶協定 Azure 信用平衡](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance)。 |
| 小計 |納稅到期金額 |
| 稅 |根據帳單設定檔的國家/地區所支付的稅金類型和金額。 如果您不需要支付稅款，您的發票上不會顯示任何稅款。 |

### <a name="understand-your-charges"></a>瞭解您的費用

[費用] 頁面會顯示依產品細分的成本。 針對 Azure 客戶，費用可能會依發票區段進行組織。 如需有關發票區段如何搭配 Azure 產品使用的詳細資訊，請參閱[您的 Microsoft 客戶合約計費帳戶快速入門](https://docs.microsoft.com/azure/billing/billing-mca-overview)中的 [[發票] 區段](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections)。 在每個產品訂單內，成本會依服務系列細分。

| 字詞 |描述 |
| --- | --- |
| 單價 | 服務 (的有效單位價格，以用於計算費用的定價幣種) 。 這項價格對於產品、服務系列、計量和服務都是唯一的。 |
| 數量 | 計費期間所購買或消耗的數量 |
| 費用/片尾 | 套用片尾/退款後的費用淨金額 |
| Azure 信用 | 套用至費用/片尾的 Azure 信用金額 |
| 稅率 | 稅率（取決於國家/地區） |
| 納稅金額 | 根據稅率套用到採購的稅金金額 |
| 總計 | 購買的應付總金額 |

[行專案] 詳細資料會根據您所收取的產品類型而有所不同。 例如，針對 Azure 產品，會顯示所套用的 Azure 信用數量。 以座位為基礎的產品會顯示單位價格和數量。 [發票詳細資料] 顯示已購買的產品、所套用的折扣或片尾、稅率和金額，以及行專案合計。

> 總計 = 費用-Azure 信用 + 稅收

每個服務系列的到期總金額是透過從信用/費用中減去 Azure 的點數來計算，並加上稅款：

> 總計 = 費用/片尾-Azure 信用 + 稅收

如果您的發票上有您想要詳細資料的 Azure 費用，請參閱 [複查您的 Microsoft 客戶合約發票](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill)。

## <a name="understand-the-last-invoice-page"></a>瞭解 [最後發票] 頁面

### <a name="payment-instructions"></a>付款指示

在發票底部是如何支付帳單的指示。 您可以依電線、支票或線上付費。

### <a name="publisher-information"></a>發行者資訊

如果您在帳單中有協力廠商服務，每個出版社的名稱和位址都會列在發票的底部。

## <a name="view-your-online-invoice"></a>查看您的線上發票

線上提供發票。 您可以從您的 PDF 發票，及從電子郵件通知取得線上發票的連結。 線上發票是可展開的，可讓您查看發票上的費用，並查看每個專案的詳細資料。 線上發票包括：

- **定價詳細資料** &mdash;其他資訊，包括有關折扣及產品定價的詳細資訊。

- **線上付款** &mdash;您可以選擇讓付款從發票進行線上。

- **Azure 成本管理** &mdash;針對 Azure 客戶，線上發票包含 Azure 成本管理的連結。

### <a name="to-view-your-online-invoice"></a>若要查看您的線上發票

1. 在系統管理中心中，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">[帳單與付款]</a> 頁面。

2. 若要下載您的發票的 .pdf 版本，請選擇您想要查看之發票列中的 [ **下載發票 pdf** ]。

3. 若要查看您的線上發票，請從清單中選擇發票。 您也可以從 [發票詳細資料] 頁面下載 .pdf。

## <a name="invoice-faq"></a>發票常見問題解答

### <a name="when-is-my-invoice-available"></a>何時提供可用的發票？

某些發票會在購買24小時內產生。 其他發票會在帳單期間結束時產生，並包含該期間內的所有專案。

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>如何在發票上支付金額到期日？

付款指示取決於您的支付方式，以及發票 PDF 的底部提供。 如果您的支付方式是信用卡，它會在開票日的10天內自動計費。 如果您的付款條件是以支票或電匯方式傳輸，請參閱 PDF 中 **付款指示** 下的資訊。

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>「銷售到」和「付款人」位址有什麼不同？

- **銷售：** 負責支付及識別發票上的法律法人。 除非您選擇在購買過程中提供替代的寄送位址，否則這裡提供的位址是用來判斷您的稅率。 如需詳細資訊，請參閱 [稅務資訊](tax-information.md)。
- **付款人：** 實體發票的傳送位址（如果適用）。 每個合法的法人可以有多個 **帳單** 位址，但每個帳單設定檔只能有一個 **帳單** 。

### <a name="what-are-billed-amount-and-amount-due"></a>「記帳金額」和「應付金額到期」是什麼？

- **計費金額：** 您所進行之購買的總金額。
- **應付金額：** 您欠付的剩餘餘額。

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>「' 服務期間」和「帳單時段」之間的差異為何？

- **服務週期：** 您要使用服務的時段。
- **帳單期限：** 最後一個發票日期之後的時段。

### <a name="how-do-i-view-and-print-my-bill"></a>如何查看和列印帳單？

1. 在 [**帳單**帳單  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& 付款</a>] 頁面上，選取發票日期範圍。
2. 若要列印或儲存帳單的 PDF 副本，請選取 [ **下載發票 PDF**]，然後列印 pdf。

若要深入瞭解，請參閱 [查看您的帳單或發票](view-your-bill-or-invoice.md)。

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>為什麼我看不到 Azure 預付款做為支付方式？

Azure 預付款只適用于合格 Azure 產品和服務的支付方式。

## <a name="need-help-contact-support"></a>需要協助？ 連絡客戶支援。

如果您有任何疑問或需要協助您的 Azure 信用，請 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">建立 azure 支援的支援要求</a>。

如果您在 Microsoft 365 系統管理中心中有任何疑問或需要協助您的發票，請 [與商務產品支援人員聯繫](../../admin/contact-support-for-business-products.md)。