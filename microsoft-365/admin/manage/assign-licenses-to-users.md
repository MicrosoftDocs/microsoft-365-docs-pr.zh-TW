---
title: 將授權指派給使用者
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解如何指派授權給使用者。
ms.date: 08/14/2020
ms.openlocfilehash: 9f044f29cabf4976d5fbf17b22777da62e4414c5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915491"
---
# <a name="assign-licenses-to-users"></a>將授權指派給使用者

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet) (英文)。

::: moniker-end

::: moniker range="o365-worldwide"

您可以在 **[作用中使用者]** 頁面或 **[授權]** 頁面上指派授權給使用者。 所使用的方法取決於您要指派產品授權給特定使用者，還是要將使用者授權指派給特定產品。

::: moniker-end

[了解如何同時新增使用者和指派授權](../add-users/add-users.md)。

## <a name="before-you-begin"></a>開始之前

- 您必須是全域、授權或使用者系統管理員，才能指派授權。 如需詳細資訊，請參閱[關於 Microsoft 365 系統管理員角色](../add-users/about-admin-roles.md)。
- 您可以[使用 Office 365 PowerShell 指派授權給使用者帳戶](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)。
- 若要使用以群組為基礎的授權，請參閱[依據 Azure Active Directory 中的群組成員資格將授權指派給使用者](/azure/active-directory/users-groups-roles/licensing-groups-assign)。
- 某些服務 (例如 Sway) 會自動指派給使用者，而不需要您個別指派。

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>使用授權頁面來指派授權給使用者

使用 **[授權]** 頁面來指派授權時，您可以指派特定產品的授權給最多 20 位使用者。 在 **[授權]** 頁面上，您會看到您已訂閱的所有產品清單。 您也會看到每個產品的授權總數、已指派的授權數，以及有多少個可供使用。

1. 在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">[授權]</a> 頁面。
2. 選取產品。
3. 在產品詳細資料頁面上，選取 **[指派授權]**。
4. 在 **[指派授權給使用者]** 窗格中，開始輸入名稱，然後從結果中選擇，將它新增到清單中。 一次最多可以新增 20 個使用者。
5. 選取 **[開啟或關閉應用程式與服務]** 以指派或移除特定項目的存取權。
6. 完成時，請選取 [指派]，然後選取 [關閉]。

如果發生衝突，則會顯示訊息，告知您發生什麼問題，以及如何修正。 例如，如果您選取的授權包含發生衝突的服務，則錯誤訊息會指出，請檢查每個授權所包含的服務，然後再試一次。

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>變更使用者可以存取的應用程式與服務

1. 在系統管理中心中，前往 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">[授權]</a> 頁面。
2. 在 **[授權]** 頁面上，選取特定使用者的列。
3. 在右窗格中，選取或取消選取您要授與存取權或移除存取權的應用程式與服務。
4. 完成時，請選取 **[儲存]**，然後選取 **[關閉]**。

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a>使用作用中使用者頁面來指派授權

使用 **[作用中使用者]** 頁面來指派授權時，您會將使用者授權指派給產品。

### <a name="assign-licenses-to-multiple-users"></a>將授權指派給多個使用者

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。
2. 選取您要指派授權的使用者名稱旁的圓圈。
3. 在頂端，選取 **[更多選項(...)]**，然後選取 **[管理產品授權]**。
4. 在 **[管理產品授權]** 窗格中，選取 **[新增到現有產品授權指派]** \> **[下一步]**。
5. 在 **[新增到現有產品]** 窗格中，針對您已選取要指派授權的使用者，將開關切換到 **[開啟]** 位置。\
    根據預設，與這些授權相關的所有服務都會自動指派給使用者。 您可以限制使用者能使用的服務。 針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。
6. 在窗格底部，選取 **[新增]** \> **[關閉]**。  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a>將授權指派給多個使用者

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。
2. 選取您要指派授權的使用者名稱旁的方塊。
3. 在 **[大量動作]** 窗格中，選取 **[編輯產品授權]**。
4. 在 **[指派產品]** 窗格中，選取 **[新增到現有產品授權指派]** \> **[下一步]**。
5. 針對您已選取要指派授權的使用者，將開關切換到 **[開啟]** 位置。\
    根據預設，與這些授權相關的所有服務都會自動指派給使用者。 您可以限制使用者能使用的服務。 針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。
6. 在 **[新增到現有產品]** 窗格底部，選取 **[新增]** \> **[關閉]** \> **[關閉]**。

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a>將授權指派給多個使用者

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。
2. 選取您要指派授權的使用者名稱旁的方塊。
3. 在 **[大量動作]** 窗格中，選取 **[編輯產品授權]**。
4. 在 **[指派產品]** 窗格中，選取 **[新增到現有產品授權指派]** \> **[下一步]**。
5. 針對您已選取要指派授權的使用者，將開關切換到 **[開啟]** 位置。\
    根據預設，與這些授權相關的所有服務都會自動指派給使用者。 您可以限制使用者能使用的服務。 針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。
6. 在 **[新增到現有產品]** 窗格底部，選取 **[新增]** \> **[關閉]** \> **[關閉]**。

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a>將授權指派給一位使用者

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。
2. 選取您要指派授權的使用者列。
3. 在右窗格中，選取 **[授權與應用程式]**。
4. 展開 **[授權]** 區段，選取您要指派之授權的方塊，然後選取 **[儲存變更]**。

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a>將授權指派給一位使用者

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。
2. 選取您要指派授權的使用者名稱旁的方塊。
3. 在右側窗格的 **[產品授權]** 列中，選取 **[編輯]**。
4. 針對您要指派授權的使用者，在 **[產品授權]** 窗格中，將開關切換到 **[開啟]** 位置。\
    根據預設，與該授權相關的所有服務都會自動指派給使用者。 您可以限制使用者能使用的服務。 針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。
5. 在 **[產品授權]** 窗格底部，選擇 **[儲存]** \> **[關閉]** \> **[關閉]**。

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a>將授權指派給一位使用者

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。
2. 選取您要指派授權的使用者名稱旁的方塊。
3. 在右側窗格的 **[產品授權]** 列中，選取 **[編輯]**。
4. 針對您要指派授權的使用者，在 **[產品授權]** 窗格中，將開關切換到 **[開啟]** 位置。\
    根據預設，與該授權相關的所有服務都會自動指派給使用者。 您可以限制使用者能使用的服務。 針對您不想讓使用者使用的服務，將開關切換至 **[關閉]** 位置。
5. 在 **[產品授權]** 窗格底部，選擇 **[儲存]** \> **[關閉]** \> **[關閉]**。

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a>指派授權給來賓使用者

您可以在 Azure Active Directory 系統管理中心中邀請來賓使用者來與您的組織共同作業。 若要進一步了解來賓使用者，請參閱[什麼是 Azure Active Directory B2B 中的來賓使用者存取權？](/azure/active-directory/external-identities/what-is-b2b)。 如果您沒有任何來賓使用者，請參閱[快速入門：在 Azure 入口網站中將來賓使用者新增至您的目錄](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)。

> [!IMPORTANT]
> 您必須是全域系統管理員才能執行這些步驟。

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory 系統管理中心</a>
2. 在功能窗格中，選取 [使用者 **]**。
3. 在 [使用者 | 所有使用者 (預覽)**]** 頁面上，選取 [新增篩選 **]**。
4. 在 [挑選欄位 **]** 功能表中，選擇 [使用者類型 **]**，然後選取 [套用 **]**。
5. 在下一個功能表中，選取 [來賓 **]**。
6. 在結果清單中，選取需要授權的使用者。
7. 在 [管理 **]** 下，選取 [授權 **]**。
8. 選取 [作業 **]**。
9. 在 [更新授權指派 **]** 頁面上，選取您要為其指派授權的產品。
10. 在右側，除您不要來賓使用者可存取的任何服務的核取方塊。
11. 選取 [儲存 **]**。

## <a name="next-steps"></a>後續步驟

如果您的使用者尚未安裝 Office 應用程式，則可以與您的使用者分享[員工快速入門手冊](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)，以設定相關項目，例如[如何在 PC 或 Mac 上下載並安裝 Microsoft 365 或 Office 2019](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)，以及[如何在行動裝置上設定 Office 應用程式和電子郵件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。

## <a name="related-content"></a>相關內容

[了解訂閱與授權](../../commerce/licenses/subscriptions-and-licenses.md) (文章)\
[取消指派給使用者的授權](remove-licenses-from-users.md) (文章)\
[購買或移除訂閱授權](../../commerce/licenses/buy-licenses.md) (文章)