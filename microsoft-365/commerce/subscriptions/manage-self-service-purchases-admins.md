---
title: '管理自助購買 (系統管理員) '
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 系統管理員可以瞭解如何管理組織中使用者所進行的自我服務購買。
ms.openlocfilehash: 2ce12b7dba4e765745a94fa10f4ba15e7013e3c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920177"
---
# <a name="manage-self-service-purchases-admin"></a>管理自助購買 (管理員)

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。

::: moniker-end

身為系統管理員，您可以看到組織中人員所進行的自我服務購買。 您會看到產品名稱、購買購買的訂閱、到期日、購買價格，以及每個自助購買的指派使用者。 如果您的組織需要，您可以透過 PowerShell 關閉以每個產品為基礎的自助購買服務。 透過自助購買或集中購買的產品，您可以使用相同的資料管理和存取原則。

您也可以控制組織中的使用者是否可以進行自助購買。 如需詳細資訊，請參閱 [Use AllowSelfServicePurchase For MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。

## <a name="view-self-service-subscriptions"></a>查看自助訂閱

1. 在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。
2. 在 [ **產品** ] 索引標籤上，選取篩選圖示，然後選取 [ **自助**]。
3. 若要查看訂閱的詳細資料，請從清單中選擇其中一個。

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>查看誰有自助購買訂閱的授權

1. 在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面。
2. 選取 [篩選] 圖示，然後選擇 [ **自我服務**]。
3. 選取產品以查看指派給人員的授權。
    > [!NOTE]
    > 如果有多個產品購買的產品，該產品只會列出一次，而且 [ **可用數量** ] 欄會顯示針對該產品購買的所有訂閱總數。
4. [ **使用者** ] 清單是依進行自助購買的人員名稱群組。
5. 若要匯出具有這些訂閱之授權的使用者清單，請選擇您想要匯出的訂閱，然後選擇 [ **匯出使用者**]。

## <a name="disable-or-enable-self-service-purchases"></a>停用或啟用自助購買

您可以針對組織中的使用者停用或啟用自助購買功能。 **MSCommerce** PowerShell 模組包含 **AllowSelfServicePurchase** 的 **PolicyID** 參數值，可讓您控制組織中的使用者是否可以進行自助購買，以及哪些產品。

您可以使用 **MSCommerce** PowerShell 模組來：

- 查看 **AllowSelfServicePurchase** 參數值的預設狀態（不論是由產品啟用或停用）
- 查看適用產品的清單，以及是否啟用或停用自助購買功能
- 查看或修改特定產品的目前設定，以啟用或停用

如需詳細資訊，請參閱 [Use AllowSelfServicePurchase For MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。

## <a name="centralize-licenses-under-a-single-subscription"></a>在單一訂閱下集中授權

您可以指派現有的授權，或透過現有的合約針對指派給自助購買之使用者的現有協定來購買其他訂閱。 在您指派這些已集中購買的授權之後，您可以要求購買者取消其現有的訂閱。

1. 在系統管理中心中，移至 [ **帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">購買服務</a> ] 頁面。
2. 尋找並選擇您想要購買的產品，然後選擇 [ **購買**]。
3. 完成其餘步驟以完成購買。
4. 請遵循 View the [自助購買訂閱授權的](#view-who-has-licenses-for-a-self-service-purchase-subscription) 使用者，在下一個步驟中將使用者清單匯出為參考的使用者。
5. 將授權指派給在其他訂閱中具有授權的每個人。 如需完整步驟，請參閱 [將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md)。
6. 聯繫購買自助購買訂閱的人員，並要求他們 [取消](manage-self-service-purchases-users.md#cancel-a-subscription)。

## <a name="take-over-a-self-service-purchase-subscription"></a>接管自助購買訂閱

您可以接管組織中使用者所做的自助購買訂閱。 當您接管自助購買訂閱時，您有兩個選項：

1. 將使用者移至不同的訂閱，並取消原始的訂閱。
2. 取消自助購買訂閱，並從指派的使用者中移除授權。

### <a name="move-users-to-a-different-subscription"></a>將使用者移至其他訂閱

當您將使用者移至不同的訂閱時，會自動取消舊的訂閱。 最初購買自助購買訂閱的使用者會收到一封電子郵件，指出訂閱已取消。

> [!NOTE]
> 您必須具備您要移動使用者的訂閱中每個使用者的可用授權。

1. 在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。
2. 在 [ **產品** ] 索引標籤上，選取篩選圖示，然後選取 [ **自助**]。
3. 選取您要接管的訂閱。
4. 在 [訂閱詳細資料] 頁面的 [ **訂閱與設定** ] 區段中，選取 [ **取得此訂閱的控制權**]。
5. 在右窗格中，選取 [ **移動使用者**]。
6. 選取您要將使用者移至其中的產品，然後選取 [ **移動使用者**]。
7. 在 [ **將使用者移至** ] 方塊中，選取 [ **移動使用者**]。 移動程式可能需要數分鐘的時間。 當程式執行時，請勿關閉瀏覽器。
8. 移動程式完成後，請關閉 [ **移動完成] 窗格**。
9. 在 [訂閱詳細資料] 頁面上，自助購買之訂閱的 **訂閱狀態** 會顯示為 [ **已刪除**]。

### <a name="cancel-a-self-service-purchase-subscription"></a>取消自助購買訂閱

當您選擇取消自助購買訂閱時，具有授權的使用者將無法存取產品。 最初購買自助購買訂閱的使用者會收到一封電子郵件，指出訂閱已取消。

1. 在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。
2. 在 [ **產品** ] 索引標籤上，選取篩選圖示，然後選取 [ **自助**]。
3. 選取您要取消的訂閱。
4. 在 [訂閱詳細資料] 頁面的 [ **訂閱與設定** ] 區段中，選取 [ **取得此訂閱的控制權**]。
5. 在右窗格中，選取 [ **取消訂閱**]。
6. 從下拉式清單中選取您取消的原因，然後選取 [ **取消訂閱**]。
7. 在 [ **您確定要取消嗎？** ] 方塊中，選取 [ **取消訂閱**]。
8. 關閉右窗格。
9. 在 [訂閱詳細資料] 頁面上， **訂閱狀態** 會顯示為 [ **已刪除**]。

## <a name="need-help-contact-us"></a>需要協助？ 聯繫我們。

如需有關自助購買的常見問題，請參閱 [自助購買常見問題](self-service-purchase-faq.md)。

如果您有任何問題或需要協助您購買自助服務，請 [與支援人員聯繫](../../admin/contact-support-for-business-products.md)。