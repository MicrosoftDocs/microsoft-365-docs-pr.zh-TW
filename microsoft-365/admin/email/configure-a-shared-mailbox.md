---
title: 設置共用信箱的設定
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 建立共用信箱之後，您需要為使用者設定一些設定，例如電子郵件轉場和自動回復。 稍後，您可能會想要變更其他設定，例如信箱名稱或成員。
ms.openlocfilehash: fe5d35be556b8edf5456bc2c0b820dc0ce77e323
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926603"
---
# <a name="configure-shared-mailbox-settings"></a>設置共用信箱的設定

建立共用 [信箱之後](create-a-shared-mailbox.md)，您需要為信箱使用者設定一些設定，例如電子郵件轉場和自動回復。 稍後，您可能會想要變更其他設定，例如信箱名稱、成員或成員許可權。 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>變更共用信箱的名稱或電子郵件別名，或變更主要電子郵件地址

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取要編輯的共用信箱，然後選取名稱、電子郵件、電子郵件別名旁邊的 **編輯。**

3. 輸入新名稱，或新增其他別名。 如果您要變更主要電子郵件地址，信箱必須擁有一個或多個電子郵件別名。

4. 選取 [儲存]。

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>轉寄傳送到共用信箱的電子郵件

您不需要指派授權給共用信箱，以轉寄寄到共用信箱的電子郵件。 您可以將郵件轉會到任何有效的電子郵件地址或通訊群組清單。

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取要編輯的共用信箱，然後選取電子郵件 **轉轉編輯** \> ****。
    
3. 將開關切換為 **開啟**，然後輸入一個電子郵件地址來轉入郵件。 可以是任何有效的電子郵件地址。 若要轉入多個位址，您必須建立位址的[](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists)通訊群組，然後在此方塊中輸入組名。
    
4. 選取 [儲存]。

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>從共用信箱傳送自動回覆

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取要編輯的共用信箱，然後選取自動 **回復編輯** \> ****。
    
3. 將開關切換為 **開啟**，並選擇是否要傳送回復給組織內部或組織外部人員。

4. 輸入您想要傳送給組織內人員的回覆。 您只能加入文字而不能加入影像。

5. 如果您也 *想要傳送* 回復給組織外部人員，請選取要收到回復的核取方塊，然後輸入文字。 There's no way to only send to people outside your organization but not to people inside your organization.

6. 選取 [儲存]。

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>允許所有人都看到已傳送的電子郵件 (回覆)

根據預設，從共用信箱寄出的郵件不會儲存至共用信箱的 [寄件備份] 資料夾。不過，這些郵件會儲存到寄件者的 [寄件備份] 資料夾。

如果您想要允許所有人都看到已寄件電子郵件，請在系統管理中心編輯共用信箱設定，然後選取已 **送出項目的編輯** \> ****。


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>選擇共用信箱可用於存取 Microsoft 電子郵件的應用程式

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取要編輯的共用信箱，然後選取電子郵件 **App 編輯** \> ****。

3. 針對 **您希望成員能夠** 存取共用信箱的所有 App，將開關設為開啟。 針對 **您不希望他們** 使用的任何 App，將開關設為關閉。 

4. 選取 [儲存]。


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>將共用信箱置於訴訟資料保留狀態

若要深入瞭解訴訟資料保留，請參閱建立 [訴訟資料保留](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)。

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取要編輯的共用信箱，然後選取訴訟 **資料保留** \> **編輯**。

3. 將開關切換至 **開啟**。 

4. 或者，輸入持續時間、保留的備註，以及包含詳細資訊的 URL。  

5. 選取 [儲存]。


## <a name="add-or-remove-members"></a>新增或移除成員

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取要編輯的共用信箱，然後選取成員 **編輯** \> ****。

3. 執行下列其中一項：
   - 若要新增成員， **請選取新增成員**、搜尋或選取要新增的成員， **然後選取儲存**。
   - 若要移除成員，請在必要時使用搜尋方塊搜尋成員，選取成員名稱旁邊的 **X，****然後選取儲存**。 

4. 再次 **選取儲存** 。

## <a name="add-or-remove-permissions-of-members"></a>新增或移除成員的許可權

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取要編輯的共用信箱，然後選取成員 \> **自訂許可權**。

3. 選取 **您想要** 針對成員變更的許可權旁邊的編輯。 

4. 執行下列其中一項：
   - 若要將該許可權授予其他成員，請選取新增許可權、搜尋或選取要新增的成員，**然後選取儲存**。
   - 若要移除成員的許可權，請在必要時使用搜尋方塊搜尋成員，選取成員名稱旁邊的 **X，****然後選取儲存**。 

4. 再次 **選取儲存** 。

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>顯示或隱藏全域通訊清單中的共用信箱

如果您選擇不顯示全域通訊清單中的共用信箱，信箱不會顯示在貴組織的地址清單中，但仍會收到電子郵件。 

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取要編輯的共用信箱，然後選取在全域 **地址清單中顯示編輯** \> ****。

3. 將開關切換至 **開啟**  或 **關閉**。 

4. 選取 [儲存]。

> [!NOTE]
> 從地址清單中隱藏共用信箱後，新共用信箱成員將無法新增隱藏的信箱至其 Outlook 設定檔，直到共用信箱再次顯示在地址清單中。 

## <a name="related-articles"></a>相關文章

[關於共用信箱](about-shared-mailboxes.md)

[建立共用信箱](create-a-shared-mailbox.md)

[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)

[從共用信箱中移除授權](remove-license-from-shared-mailbox.md)

[解決共用信箱的問題](resolve-issues-with-shared-mailboxes.md)
