---
title: 關閉您的帳戶
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
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: 瞭解如何使用 Microsoft 關閉您的帳戶。
ms.openlocfilehash: 0fed7df54a21b3696e81915af78e377e855bfd12
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2020
ms.locfileid: "48794894"
---
# <a name="close-your-account"></a>關閉您的帳戶

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end

當您使用 Microsoft 關閉您的帳戶時，與您的帳戶相關的所有資訊都會被刪除。 這些資訊包括訂閱、授權、付款方式、使用者及使用者資料。 開始此程式之前，請務必備份您要保留的任何資料。

## <a name="step-1-delete-users"></a>步驟1：刪除使用者

刪除除了一個全域管理員之外的所有使用者，該全域管理員完成步驟以關閉帳戶。 您必須先刪除所有其他使用者，才能在此程式結束之前刪除目錄。

若使用者從內部部署進行同步處理，請先關閉同步處理，然後使用 Azure 入口網站或 Azure PowerShell Cmdlet 刪除雲端目錄中的使用者。

若要刪除使用者，請參閱 <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin：刪除一或多個使用者</a>。

您也可以使用 <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell Cmdlet，成批刪除使用者。

如果您的組織使用與 Azure AD 同步處理的 Active Directory，請改為刪除 Active Directory 中的使用者帳戶。 如需相關指示，請參閱 <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">大量刪除 Azure Active Directory 中的使用者</a>。

## <a name="step-2-cancel-all-active-subscriptions"></a>步驟2：取消所有作用中的訂閱

1. 在系統管理中心，移至 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">您的產品</a> 頁面。

2. 如果 [訂閱] 清單位於 **表格** 視圖中，請在右側選取 [ **卡片** ]。

3. 尋找作用中的訂閱，並在 [ **設定 & 動作** ] 區段中，選取 [ **取消訂閱** ]。

4. 遵循提示完成此程式。

5. 重複步驟1到4，以取消所有作用中的訂閱。

## <a name="step-3-delete-all-disabled-subscriptions"></a>步驟3：刪除所有已停用的訂閱

1. 在系統管理中心，移至 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">您的產品</a> 頁面。

2. 如果 [訂閱] 清單位於 **表格** 視圖中，請在右側選取 [ **卡片** ]。

3. 選取 [ **訂閱狀態** ] 旁的 [ **停用** ]。

4. 尋找停用的訂閱，然後在 [ **設定 & 動作** ] 區段中，選取 [ **刪除** ]。

5. 在 [ **刪除訂閱** ] 對話方塊中，選取 [ **我瞭解影響** ] 核取方塊，然後選取 [ **刪除訂閱** ]。

6. 針對每個停用的訂閱重複步驟4和5，直到刪除所有訂閱為止。

## <a name="step-4-disable-multi-factor-authentication"></a>步驟4：停用多重要素驗證

1. 在系統管理中心中，移至 [ **使用者** 作用中  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">使用者</a>] 頁面。

2. 選擇 **多重要素驗證** 。

3. 在 [多重要素驗證] 頁面上，停用您目前所用全域系統管理員帳戶以外的所有帳戶。

您也可以 <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">使用 PowerShell 來停用多個使用者的多重要素驗證</a>。

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>步驟5：刪除 Azure Active Directory 中的目錄

1. 使用全域系統管理員帳戶登入 <a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 系統管理中心</a> 。

2. 選取 [Azure Active Directory]  。

3. 切換至您要刪除的組織。

4. 選取 [ **刪除租** 使用者]。

5. 如果您的組織未通過一或多項檢查，您會看到有關如何傳遞檢查的詳細資訊連結。 傳遞所有檢查後，請選取 [ **刪除** ] 以完成程式。

完成此最後一個步驟之後，您的 Microsoft 帳戶會關閉並刪除。
