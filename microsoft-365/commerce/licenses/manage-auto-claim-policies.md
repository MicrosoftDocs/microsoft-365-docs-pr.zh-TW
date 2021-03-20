---
title: 管理自動宣告原則
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: 瞭解如何建立及管理自動宣告原則，以自動將授權指派給某些應用程式的使用者。
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
ms.openlocfilehash: bf3f79e425b3f7cd86f1a5ab95a337ef5127e345
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911467"
---
# <a name="manage-auto-claim-policies"></a>管理自動宣告原則

自動宣告原則可讓使用者在第一次登入至應用程式時，自動宣告產品的授權。 身為系統管理員，您一般會以手動方式或使用以群組為基礎的授權，將授權指派給使用者。 使用自動宣告原則，可管理使用者可自動宣告授權的產品。 您也可以控制哪些授權來源的產品。

在您建立自動宣告原則之後，您可以執行下列工作來管理原則：

- [開啟或關閉原則](#turn-a-policy-on-or-off)
- [編輯原則易記名稱](#edit-the-policy-friendly-name)
- [新增或移除備份產品](#add-or-remove-backup-products)
- [管理指派應用程式和服務](#change-the-assigning-apps-and-services)
- [變更指派順序](#change-the-assigning-order-for-backup-products)
- [查看原則報表](#view-an-auto-claim-policy-report)

> [!IMPORTANT]
> 「自動宣告」原則目前僅適用于 Microsoft 小組。 未來可使用的產品越多。

## <a name="before-you-begin"></a>開始之前

您必須是全域系統管理員，才能建立及管理自動宣告原則。 如需詳細資訊，請參閱[關於 Microsoft 365 系統管理員角色](../../admin/add-users/about-admin-roles.md)。

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a>開啟或關閉自動理賠原則功能

預設會關閉自動理賠原則功能。 在您可以使用此功能之前，您必須先將其開啟。 在您開啟功能之後，您可以建立自動宣告原則。

### <a name="turn-on-auto-claim-policies"></a>開啟自動宣告原則

1. 在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。
2. 在頁面的中央，選取 [ **開啟設定** ] 按鈕。

### <a name="turn-off-auto-claim-policies"></a>關閉自動宣告原則

1. 在系統管理中心中，移至 [ **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">組織設定</a> ] 頁面。
2. 在表格底部附近，選取 [ **使用者擁有的應用程式和服務**]。
3. 在右窗格中，清除 [ **讓使用者在第一次登入時自動宣告授權**] 方塊。

如果您已有作用中的原則，但不想讓任何使用者宣告授權，請 [關閉原則](#turn-a-policy-on-or-off)。 當您關閉自動宣告原則時，就不會有其他使用者可以從該點宣告授權。 已宣告授權的使用者不會遺失其授權。

## <a name="create-an-auto-claim-policy"></a>建立自動宣告原則

[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動報銷宣告原則</a> ] 索引標籤會列出您建立的原則。 在此索引標籤上，您可以看到：原則的名稱、與原則相關聯的應用程式、指派給原則的產品、可用授權的數目，以及原則的狀態。

當您建立自動宣告原則時，您可以在其中新增備份產品。 如果主要產品的授權不足，將會使用備份產品將授權指派給使用者。 您最多可以新增四個備份產品，並 [變更其使用順序](#change-the-assigning-order-for-backup-products)。 若要深入瞭解，請參閱 [新增或移除備份產品](#add-or-remove-backup-products)。

> [!NOTE]
> 目前，您只可以建立一個自動宣告原則。 您可以建立的原則數目會隨著更多的產品能夠使用此功能而增加。

1. 在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。
2. 選取 [ **新增原則**]。
3. 在 [ **名稱此自動宣告原則** ] 頁面上，輸入原則的名稱，然後選取 **[下一步]**。
4. 在 [ **設定自動宣告應用程式和產品** ] 頁面上，選取要指派授權的應用程式和訂閱。
5. 如果您想要新增備份產品，請選取 [ **新增備份產品至這個原則**]，然後從清單中選取產品。
6. 選取 [下一步]。
7. 在 [ **選取應用程式** ] 頁面上，清除或選取要排除或包含在授權中的應用程式方塊，然後選取 **[下一步]**。
8. 如果您已新增一或多個備份產品，請對每個產品重複步驟7。 否則，請移至步驟9。
9. 在 [ **檢查和完成]** 頁面上，確認新的原則資訊，進行必要的變更，然後選取 [ **建立原則**]。
10. 選取 [關閉]。

## <a name="turn-a-policy-on-or-off"></a>開啟或關閉原則

當您關閉原則時，就不會有其他使用者可以宣告該原則下的授權。 此變更不會影響在該原則下已宣告授權的使用者。

1. 在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。
2. 選取您要編輯的原則。
3. 在詳細資料窗格的 [ **開啟或關閉此原則**] 下，選取或清除核取方塊。
4. 選取 [ **儲存** ] 以關閉 [詳細資料] 窗格。

## <a name="edit-the-policy-friendly-name"></a>編輯原則易記名稱

1. 在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。
2. 選取您要編輯的原則。
3. 在 [詳細資料] 窗格的 [ **原則名稱** ] 區段中，選取 [ **編輯**]。
4. 輸入新的原則名稱，然後選取 [ **儲存**]。
5. 選取 [ **儲存** ] 以關閉 [詳細資料] 窗格。

## <a name="add-or-remove-backup-products"></a>新增或移除備份產品

當您建立原則時，您可以在其中新增產品。 然後，系統會自動將授權指派給該授權集區中的使用者。 您可以隨時新增或移除自動理賠原則的產品。 如果您已有一個產品與原則相關聯，則您新增的任何產品都會視為備份產品。 使用第一項產品的可用授權數量時，該原則會使用清單中的下一個備份產品來指派授權。 您 [可以視需要重新排序產品清單](#change-the-assigning-apps-and-services) 。

當您移除備份產品時，將不再用來指派授權。 現有授權的使用者仍具有該授權，但沒有新的使用者可以接收該產品的授權。

> [!NOTE]
> 自動宣告原則至少必須包含一個產品。 您無法移除原則中的所有產品。 如果您不想要再指派特定自動宣告原則的授權，請 [關閉原則](#view-an-auto-claim-policy-report)。

### <a name="add-a-backup-product"></a>新增備份產品

1. 在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。
2. 選取您要編輯的原則。
3. 在 [詳細資料] 窗格的底部，選取 [ **新增備份產品至此原則**]。
    > [!NOTE]
    > 如果您未看到此連結，這是因為您只有一個與您的帳戶相關聯的產品。
4. 在 [ **新增產品** ] 窗格中，使用下拉式清單選擇要新增至原則的產品，然後選取 [ **新增**]。
5. 選取 [ **儲存** ] 以關閉 [詳細資料] 窗格。

### <a name="remove-a-backup-product"></a>移除備份產品

1. 在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。
2. 選取您要編輯的原則。
3. 在 [詳細資料] 窗格的底部，選取 [ **移除產品**]。
4. 在 [ **從原則移除產品** ] 窗格中，選取您要移除之原則的方塊，然後選取 [ **儲存**]。
5. 關閉 [詳細資料] 窗格。

## <a name="change-the-assigning-apps-and-services"></a>變更指派應用程式和服務

每個產品都有相關聯的應用程式和服務集合。
針對您的自動宣告原則中的每一種產品，您可以指定當使用者自動指派該產品的授權時所要包含的應用程式和服務。

1. 在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。
2. 選取您要編輯的原則。
3. 在詳細資料窗格的 [ **應用程式和服務**] 底下，選取 [ **編輯**]。
4. 在 [ **應用程式和服務** ] 窗格的 [ **產品** ] 下拉式清單中，選取單一產品，或選取 [ **所有產品**]。
5. 針對您想要讓使用者擁有或沒有存取權的應用程式和服務，選取或取消選取方塊。
6. 完成後，請選取 [ **儲存**]，然後關閉 [詳細資料] 窗格。

## <a name="change-the-assigning-order-for-backup-products"></a>變更備份產品的指派順序

如果您有指派給原則的備份產品，您可以變更使用者登入 app 時，用來指派授權的順序。

1. 在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。
2. 選取您要編輯的原則。
3. 在 [詳細資料] 窗格的 [ **產品授權** ] 區段中，選取您要移動之產品旁的方塊，然後選取 [ **上移** ] 或 [ **下移**]。
4. 針對每個要重新排序的產品重複步驟3。
5. 當您完成重新排序產品時，請選取 [ **儲存** ] 以關閉 [詳細資料] 窗格。

## <a name="view-an-auto-claim-policy-report"></a>查看自動宣告原則報告

1. 在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。
2. 選取 [ **查看報告**]。 [ **自動宣告原則報告** ] 頁面會列出過去90天內從每個原則指派的所有授權。 根據預設，此頁面會顯示過去的90天。
3. 若要變更所顯示的時段，請選取 [ **過去30天** ] 下拉式清單。 您可以查看過去1、7、30和90天的報告。

## <a name="next-steps"></a>後續步驟

您可以定期回到 [ **自動宣告原則** ] 索引標籤，以查看您建立之原則下已宣告授權的使用者清單。

## <a name="related-content"></a>相關內容

[將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md) (文章)\
[購買或移除訂閱授權](buy-licenses.md) (篇) \
瞭解 (文章) [的訂閱與授權](subscriptions-and-licenses.md)