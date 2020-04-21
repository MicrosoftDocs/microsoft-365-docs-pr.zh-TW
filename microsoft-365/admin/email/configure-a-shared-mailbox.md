---
title: 設定共用信箱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
description: 建立共用信箱之後，您會想要設定其使用者的某些設定，例如電子郵件轉寄及自動回復。 稍後，您可能想要變更其他設定，例如信箱名稱或成員。
ms.openlocfilehash: 63d3d0a5867875344ff4635071bbbad69e02eadc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629044"
---
# <a name="configure-a-shared-mailbox"></a>設定共用信箱

[建立共用信箱](create-a-shared-mailbox.md)之後，您會想要為信箱使用者設定某些設定，例如電子郵件轉寄及自動回復。 稍後，您可能需要變更其他設定，例如信箱名稱、成員或成員許可權。 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>變更共用信箱的名稱或電子郵件別名，或變更主要電子郵件地址

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取您要編輯的共用信箱，然後選取 [名稱]、[**電子郵件] 和 [電子郵件別名**] 旁邊的 [**編輯**]。

3. 輸入新的名稱，或新增其他別名。 如果您想要變更主要電子郵件地址，您的信箱必須有一個以上的電子郵件別名。

4. 選取 **[儲存]**。

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>轉寄傳送到共用信箱的電子郵件

您不需要將授權指派給共用信箱，即可轉寄傳送給它的電子郵件。 您可以將郵件轉寄至任何有效的電子郵件地址或通訊群組清單。

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取您要編輯的共用信箱，然後選取 [**電子郵件** \>轉寄] [**編輯**]。
    
3. 將切換設定為 [**開啟**]，然後輸入一個電子郵件地址，以轉寄郵件。 它可以是任何有效的電子郵件地址。 若要轉寄至多個位址，您必須為位址[建立通訊群組](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide)，然後在此方塊中輸入群組的名稱。
    
4. 選取 **[儲存]**。

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>從共用信箱傳送自動回覆

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取您要編輯的共用信箱，然後選取 [**自動回復** \> ] [**編輯**]。
    
3. 將切換設定為 [**開啟**]，然後選擇是否要將回復傳送給組織內或組織外的人員。

4. 輸入您想要傳送給組織內人員的回覆。 您只能加入文字而不能加入影像。

5. 如果您*也*想要將回復傳送給組織外部的人員，請選取您要取得回復的核取方塊，然後輸入文字。 There's no way to only send to people outside your organization but not to people inside your organization.

6. 選取 **[儲存]**。

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>允許所有人都看到已傳送的電子郵件 (回覆)

根據預設，從共用信箱寄出的郵件不會儲存至共用信箱的 [寄件備份] 資料夾。不過，這些郵件會儲存到寄件者的 [寄件備份] 資料夾。

如果您想要允許所有人查看已傳送的電子郵件，請在系統管理中心中編輯共用信箱設定，然後選取 [**已傳送的專案** \> ] [**編輯**]。


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>選擇共用信箱可用於存取 Microsoft 電子郵件的應用程式

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取您要編輯的共用信箱，然後選取 [**電子郵件應用程式** \> **編輯**]。

3. 針對您想要讓成員存取共用信箱的所有應用程式，將 [開啟] 設定為 [**開啟**]。 針對您不想要使用的任何應用程式，將其開關設定為 [**關閉**]。 

4. 選取 **[儲存]**。


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>讓共用信箱處於訴訟暫止狀態

若要深入瞭解訴訟暫止，請參閱[建立訴訟暫](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)止。

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取您要編輯的共用信箱，然後選取 [**訴訟暫** \>止] [**編輯**]。

3. 將開啟開關設定為 [**開啟**]。 

4. （選用）輸入持續時間、有關保留的備註，以及包含詳細資訊的 URL。  

5. 選取 **[儲存]**。


## <a name="add-or-remove-members"></a>新增或移除成員

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取您要編輯的共用信箱，然後選取 [**成員** \> **編輯**]。

3. 執行下列其中一項動作：
   - 若要新增成員，請選取 [**新增成員**]、[搜尋] 或 [選取要新增的成員]，然後選取 [**儲存**]。
   - 若要移除成員，請在必要時使用搜尋方塊來搜尋成員，選取成員名稱旁邊的**X** ，然後選取 [**儲存**]。 

4. 再次選取 [**儲存**]。

## <a name="add-or-remove-permissions-of-members"></a>新增或移除成員的許可權

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取您要編輯的共用信箱，然後選取 [**成員** \> **自訂許可權**]。

3. 選取您要變更成員之許可權旁邊的 [**編輯**]。 

4. 執行下列其中一項動作：
   - 若要將該許可權授與其他成員，請選取 [**新增許可權**]、[搜尋] 或 [選取要新增的成員]，然後選取 [**儲存**]。
   - 若要移除成員的許可權，請使用搜尋方塊來搜尋成員（如有必要），選取成員名稱旁邊的**X** ，然後選取 [**儲存**]。 

4. 再次選取 [**儲存**]。

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>在全域通訊清單中顯示或隱藏共用信箱

如果您選擇不在全域通訊清單中顯示共用信箱，該信箱不會出現在您組織的通訊清單中，但仍然會收到傳送給它的電子郵件。 

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組] ** > **[共用信箱]** 頁面。 

::: moniker-end

2. 選取您要編輯的共用信箱，然後選取 [**在全域通訊清單** \> **編輯**] 中的 [顯示]。

3. 將開啟或關閉切換為 **[開啟]** 或 [**關閉**]。 

4. 選取 **[儲存]**。

> [!NOTE]
> 從通訊清單中隱藏共用信箱，將無法將隱藏的信箱新增至他們的 Outlook 設定檔，直到共用信箱再次顯示在通訊清單中為止。 

## <a name="related-articles"></a>相關文章

[關於共用信箱](about-shared-mailboxes.md)

[建立共用信箱](create-a-shared-mailbox.md)

[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)

[從共用信箱中移除授權](remove-license-from-shared-mailbox.md)

[解決共用信箱的問題](resolve-issues-with-shared-mailboxes.md)
