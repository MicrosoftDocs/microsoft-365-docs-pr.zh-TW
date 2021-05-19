---
title: 關閉您的帳戶
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
search.appverid: MET150
description: 瞭解如何使用 Microsoft 關閉您的帳戶。
ms.date: 04/02/2021
ms.openlocfilehash: ed73c191063a328490945c54dc2f5101c88f17e8
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537292"
---
# <a name="close-your-account"></a>關閉您的帳戶

當您使用 Microsoft 關閉您的帳戶時，與您的帳戶相關的所有資訊都會被刪除。 這些資訊包括訂閱、授權、付款方式、使用者及使用者資料。

## <a name="before-you-begin"></a>在您開始之前

開始此程序之前，請務必備份任何您想保留的資料。

您必須是全域或計費管理員，才能執行本文所述的工作。 如需詳細資訊，請參閱[關於系統管理員角色](../admin/add-users/about-admin-roles.md)。

## <a name="step-1-delete-users"></a>步驟1：刪除使用者

除了一個全域管理員之外，刪除所有使用者。 全域管理員完成步驟以關閉帳戶。 您必須先刪除所有其他使用者，才能在此程式結束之前刪除目錄。

若使用者從內部部署進行同步處理，請先關閉同步處理，然後使用 Azure 入口網站或 Azure PowerShell Cmdlet 刪除雲端目錄中的使用者。

若要刪除使用者，請參閱 [User management admin：刪除一或多個使用者](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365)。

您也可以使用 [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell Cmdlet，成批刪除使用者。

如果您的組織使用與 Microsoft Azure Active Directory (Azure AD) 同步處理的 Active Directory，請改為從 Active directory 中刪除使用者帳戶。 如需相關指示，請參閱[大量刪除使用者的 Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete)。

## <a name="step-2-cancel-all-active-subscriptions"></a>步驟2：取消所有作用中的訂閱

1. 在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。
2. 在 [ **產品** ] 索引標籤上，尋找使用中的訂閱。 選取 [ (更多動作) ] 的三個點，然後選取 [ **取消訂閱**]。
3. 在 **取消訂閱** 窗格中，選擇取消的原因。 您也可以選擇提供任何意見反應。
4. 選取 **[儲存]**。
5. 重複步驟1到4，以取消所有作用中的訂閱。

## <a name="step-3-delete-all-disabled-subscriptions"></a>步驟3：刪除所有已停用的訂閱

1. 在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。
2. 在 [ **產品** ] 索引標籤上，選取停用的訂閱。
3. 在 [訂閱詳細資料] 頁面上，選取 [ **訂閱和付款設定** ] 區段中的 [ **刪除訂閱**]。
4. 在 [ **刪除訂閱** ] 窗格中，選取 [ **刪除訂閱**]。
5. 在 [ **刪除訂閱** ] 對話方塊中，選取 **[是]**。
6. 針對每個停用的訂閱，重複步驟3到5，直到刪除所有訂閱為止。

> [!NOTE]
> 如果您無法立即刪除停用的訂閱， [請與支援人員聯繫](../business-video/get-help-support.md)。

## <a name="step-4-disable-multi-factor-authentication"></a>步驟4：停用多重要素驗證

1. 使用全域系統管理員帳戶登入系統管理中心。 若要確認您擁有的角色，請參閱 [檢查組織中的系統管理員角色](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)。
2. 移至 [**使用者** 作用中  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">使用者</a>] 頁面。
3. 選擇 **多重要素驗證**。
4. 在 [多重要素驗證] 頁面上，停用您目前所用全域系統管理員帳戶以外的所有帳戶。

您也可以 [使用 PowerShell 來停用多個使用者的多重要素驗證](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)。


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>步驟5：在 Azure Active Directory 中刪除目錄

1. 使用全域系統管理員帳戶登入 <a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 系統管理中心</a> 。
2. 選取 **[Azure Active Directory]**。
3. 切換至您要刪除的組織。
4. 選取 [ **刪除租** 使用者]。
5. 如果您的組織未通過一或多項檢查，您會看到有關如何傳遞檢查的詳細資訊連結。 傳遞所有檢查後，請選取 [ **刪除** ] 以完成程式。

完成此最後一個步驟之後，您的 Microsoft 帳戶會關閉並刪除。
