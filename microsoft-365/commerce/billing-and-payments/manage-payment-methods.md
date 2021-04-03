---
title: 管理付款方式
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: 了解如何在 Microsoft 365 系統管理中心管理您的付款方式。
ms.date: ''
ms.openlocfilehash: 1d28d082c0a7c123aadaa2230930326139fdcb8e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579779"
---
# <a name="manage-payment-methods"></a>管理付款方式

向 Microsoft 購買商務產品或服務時，您可以使用現有的付款方式，或新增付款方式。 您可以使用信用卡或轉帳卡，或是銀行帳戶來支付購買的項目。

如果您的商務帳戶有帳單設定檔，且您是帳單設定檔擁有者或帳單設定檔參與者，則可以使用支援信用卡或發票付款的帳單設定檔來購買或支付帳單。 如果您是帳單發票管理員，則只能使用帳單設定檔來支付帳單。 若要深入了解帳單設定檔和角色，請參閱[管理帳單設定檔](manage-billing-profiles.md)。

如果您的商務帳戶沒有帳單設定檔，任何全域或計費系統管理員都可以管理和使用新增到商務帳戶的任何銀行帳戶。 不過，您僅能管理或使用您新增的信用卡。

> [!NOTE]
> 使用銀行帳戶付款的選項不適用於部分國家或地區。
>
> 您必須使用與您租用戶相同的國家/地區發出的付款方式。

## <a name="before-you-begin"></a>開始之前

您必須是全域或計費管理員，才能執行本文所述的工作。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

## <a name="add-a-payment-method"></a>新增付款方式

新增付款方式不會將任何訂閱與它相關聯。 若要將單一訂閱指派給付款方式，請參閱[變更單一訂閱的付款方式](#change-a-payment-method-for-a-single-subscription)。 若要以新的付款方式取代使用另一種付款方式的所有訂閱，請參閱[取代付款方式](#replace-a-payment-method)。

1. 在系統管理中心中，移至 [帳單 **]**  >  [帳單與付款 **]**  >  [付款方式 <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">]</a> 頁面。
2. 選取 [新增付款方式]。
3. 在 [付款方式] 頁面上，從下拉式功能表選取付款方法。
4. 輸入新卡片或銀行帳戶的相關資訊，然後選取 [新增 **]**。

## <a name="update-payment-method-details"></a>更新付款方式詳細資料

您可以變更現有付款方式的信用卡或轉帳卡的名稱、帳單地址或到期日。 不過，您無法變更信用卡或帳戶號碼。 如果帳戶號碼已變更，請[將其以不同付款方式取代](#replace-a-payment-method)，然後[刪除舊的付款方式](#delete-a-payment-method)。

1. 在系統管理中心中，移至 [帳單] > [帳單與付款] > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>頁面。
2. 選取付款方式資料列以進行更新。 在右窗格中，選取 **[編輯]**。
3. 更新您的付款方式資訊，包括信用卡或轉帳卡上的名稱、帳單地址或到期日，然後選取 **[儲存]**。

## <a name="replace-a-payment-method"></a>取代付款方式

取代付款方式時，會針對使用相同付款方式的所有訂閱和帳單設定檔取代它。 取代付款方式不會刪除現有的付款方式。 該方式仍可供選取並用於其他訂閱和帳單設定檔。

若要變更單一訂閱的付款方式，請參閱[變更單一訂閱的付款方式](#change-a-payment-method-for-a-single-subscription)。

1. 在系統管理中心中，移至 [帳單] > [帳單與付款] > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>頁面。
2. 選取付款方式資料列以進行取代。 右側窗格會列出所有帳單設定檔，以及使用所選付款方式的個別訂閱。
3. 在右側窗格中，選取 [取代所有項目的付款方式]。
4. 若要使用現有的付款方式，請從下拉式清單中選擇一個付款方式，然後選取 [取代]。
    > [!NOTE]
    > 如果您有與帳單設定檔相關的訂閱，只能使用信用卡或轉帳卡付款。 如果您的銀行帳戶列在 [付款方式] 頁面上，則無法在下拉式清單中選取。
5. 若要新增新的付款方式，請選取 [新增付款方式]。
6. 在 [新增付款方式] 窗格中，輸入帳戶資訊，然後選取 [儲存]。 您使用的付款方式必須與您租用戶的國家/地區相同。
7. 已在下拉式清單中選取新的付款方式。 選取 [取代]。

## <a name="change-a-payment-method-for-a-single-subscription"></a>變更單一訂閱的付款方式

您可以變更用來支付單一訂閱的付款方式。

1. 在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。
2. 在 [產品 **]** 索引標籤上，尋找您想要以其他付款方式支付的訂閱。
3. 選取 [其他動作 **]** (三個點)，然後選取 [取代付款方式 **]**。
4. 在 [取代付款方式 **]** 窗格中，從下拉式清單選擇其他付款方式，或選擇新增付款方式。
5. 如果您新增付款方式，請輸入信用卡或帳戶詳細資料，然後選取 [儲存 **]**。
6. 確認選取的付款方式正確無誤，然後選取 [取代 **]**。

## <a name="delete-a-payment-method"></a>刪除付款方式

您只可以刪除未與訂閱或帳單設定檔連結的付款方式。 這適用於所有訂閱，而無論其狀態如何。

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>刪除未連結訂閱或帳單設定檔的付款方式

如果某個付款方式沒有與任何訂閱或帳單設定檔相關聯，您可以立即將其刪除。

1. 在系統管理中心中，移至 [帳單 **]**  >  [帳單與付款 **]**  >  [付款方式 <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">]</a> 頁面。
2. 尋找要刪除的付款方式，選取三個點，然後選取 [刪除 **]**。
3. 在右窗格底部，選取 [刪除 **]**。

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>刪除已連結訂閱或帳單設定檔的付款方式

如果某個付款方式已與任何訂閱或帳單設定檔連結，請先以現有的付款方式取代它，或新增付款方式，然後刪除舊的付款方式。

1. 在系統管理中心中，移至 [帳單 **]**  >  [帳單與付款 **]**  >  [付款方式 <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">]</a> 頁面。
2. 選取要刪除的付款方式列。 右窗格會列出使用該付款方式的現有訂閱。
3. 在右窗格中，選取 [編輯 **]**。
4. 若要使用現有的付款方式，請從下拉式清單中選擇一個付款方式，選取 [下一步 **]**，然後選取 [刪除 **]**。
    > [!NOTE]
    > 如果您有與帳單設定檔相關的訂閱，只能使用卡片或轉帳卡付款。 如果您的銀行帳戶列在 [付款方式 **]** 頁面上，則無法在下拉式清單中選擇。
5. 若要新增新的付款方式，請選取 [新增付款方式 **]**。
6. 選擇您要新增的付款方式類型，輸入帳戶資訊，然後選取 [儲存 **]**。
7. 已在下拉式清單中選取新的付款方式。 選取 [下一步 **]**。
8. 選取 [刪除 **]**。

## <a name="troubleshoot-payment-methods"></a>疑難排解付款方式

| 問題 | 疑難排解步驟 |
|:----------|:-----|
|**我收到錯誤訊息指出「瀏覽器目前的設定為封鎖 Cookie」。** |將您的瀏覽器設為允許第三方 Cookie，然後再試一次。 |
|**我的信用卡或轉帳卡遭到拒絕。** |如果您使用信用卡或轉帳卡付款，但信用卡遭到拒絕，您會收到一封電子郵件，指出 Microsoft 無法處理付款。 仔細檢查顯示的信用卡詳細資料&mdash;信用卡卡號、到期日、信用卡上的名稱，以及包括省/市、縣/市和郵遞區號在內的地址&mdash;與信用卡和帳單上顯示的資料完全相同。 您可以使用訂閱詳細資料頁面的 [帳單 **]** 區段的 [結算餘額 **]** 連結，更新您的卡片資訊並立即提交付款。 如需詳細資訊，請參閱[如果我有未付餘額，該怎麼辦？](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  如果還是繼續看到「已拒絕」訊息，請連絡您的銀行。 您的卡片可能非作用中。 如果您最近透過郵件收到的卡片有更新的到期日，請確定已啟用該卡片。 您的銀行也可以告訴您，您的卡片是否未核准進行線上、國際或週期性交易。 |
|**我想要更新信用卡或銀行帳戶號碼。** |您無法變更現有付款方式的信用卡或帳戶號碼。 如果您的信用卡或帳戶號碼已變更，請[以不同的付款方式取代它](#replace-a-payment-method)，這會將所有作用中的訂閱從該付款方式移至新的付款方式，然後[刪除舊的付款方式](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)。 |
|**我的帳戶只有一張信用卡或一個銀行帳戶，而我想移除它。** |如果您只有一個付款方式，您必須[將它以新的付款方式取代](#replace-a-payment-method)，之後才能刪除它。 |
|**我無法新增我的卡片或銀行帳戶。**  |您必須使用與您租用戶相同的國家/地區發出的付款方式。 如果您無法輸入您的卡片或銀行帳戶資訊，您可以[連絡客戶支援](../../admin/contact-support-for-business-products.md)。 |

## <a name="related-content"></a>相關內容

[支付您的商務訂閱費用](pay-for-your-subscription.md) (文章)\
[管理帳單設定檔](manage-billing-profiles.md) (文章)\
[變更計費頻率](change-payment-frequency.md) (文章)