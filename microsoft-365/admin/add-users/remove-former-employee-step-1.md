---
title: 步驟 1-停止員工登入 Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 封鎖離職員工的登入，並封鎖 Microsoft 365 服務的存取權。
ms.openlocfilehash: f2258b165c3d61f809288003f4a536ffe160ea59
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53061828"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>步驟 1-防止離職員工登入並封鎖 Microsoft 365 服務的存取權

如果您需要立即避免使用者登入存取，您應該重設其密碼。 在此步驟中，請從 Microsoft 365 中強制登出使用者。

> [!NOTE]
> 您必須是全域系統管理員，才能啟動其他系統管理員的登出。 若為非系統管理員的使用者，您可以使用使用者系統管理員或服務台管理員使用者來執行此動作。 [深入瞭解系統管理角色](about-admin-roles.md)

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。
2. 選取使用者名稱旁的方塊，然後選取 [ **重設密碼**]。
3. 輸入新密碼，然後選取 [ **重設**]。  (不要將其傳送給他們。 ) 
4. 選取使用者的名稱以移至其屬性窗格，然後在 [ **帳戶** ] 索引標籤上，選取 [登出 **所有會話**]。

在一小時內，或在他們保留目前的 Microsoft 365 頁面時，系統會提示他們重新登入。 存取權杖適用于一個小時，所以時程表取決於該權杖所留下的時間，以及是否要流覽至目前的網頁。
  
> [!IMPORTANT]
> 如果使用者在 Outlook 網頁版，只要在其信箱中按一下滑鼠，就不會立即將其彈出。 當他們選取不同的麻將牌（例如 OneDrive，或重新整理其瀏覽器）時，就會啟動登出。
  
若要使用 PowerShell 立即登出使用者，請參閱 [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) Cmdlet。
  
如需花費多久時間以將某人退出電子郵件的詳細資訊，請參閱[終止員工的電子郵件工作階段所需注意的事項](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session)。

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>封鎖離職員工的 Microsoft 365 服務存取權

> [!IMPORTANT]
 > 封鎖帳戶最多可能需要24小時才會生效。 如果您需要立即避免使用者登入存取，請依照上述步驟進行，然後重設其密碼。

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。
2. 選取您要封鎖的員工名稱，在使用者的名稱下，選取 [ **封鎖此使用者** 的符號]。
3. 選取 [ **封鎖使用者登入**]，然後選取 [ **儲存**]。

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>封鎖離職員工的電子郵件存取權 (Exchange Online)

如果您的 Microsoft 365 訂閱中包含電子郵件，請登入 Exchange 系統管理中心，然後遵循下列步驟，封鎖您的離職員工存取其電子郵件。
  
1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。
2. 在 Exchange 系統管理中心中，**流覽至 [** 收件者] [ \> **信箱**]。
3. 按兩下使用者並移至 [ **信箱功能** ] 頁面。 在 [行動 **裝置**] 下，選取 [**停用 Exchange ActiveSync** ] 和 [**停用裝置的 OWA]，** 然後在出現提示時回答 **[是]**
4. 在 [ **電子郵件** 連線] 下，選取 [ **停** 用並在提示時回答 **Yes]** 。
