---
title: 保護您的系統管理員帳戶
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 瞭解如何設定和保護您的系統管理員帳戶。
ms.openlocfilehash: 857c24ac0ec134e119b3de083afe8dc3269bdbe2
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183258"
---
# <a name="protect-your-administrator-accounts"></a>保護您的系統管理員帳戶

因為系統管理員帳戶具有較高的許可權, 所以對於駭客和網路罪犯來說, 它們是非常有價值的目標。 本文說明：

- 如何為緊急情況設定額外的系統管理員帳戶。
- 如何保護這些帳戶。
 
當您註冊 Microsoft 365 商務版並輸入您的資訊時, 您會自動成為全域系統管理員。全域管理員擁有使用者帳戶的最終控制權, 以及 Microsoft 系統管理中心的其他所有設定, 但有許多不同類型的系統管理員帳戶具有不同的存取程度。 如需各種系統管理員角色之不同存取層級的詳細資訊, 請參閱[關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。


## <a name="create-additional-admin-accounts"></a>建立其他系統管理員帳戶

僅使用系統管理帳戶進行管理。 系統管理員應該要有個別的使用者帳戶, 以便定期使用 Office 應用程式, 並在必要時使用其系統管理帳戶來管理帳戶、裝置以及使用其他系統管理功能。  將 Microsoft 365 商務版授權從系統管理帳戶中移除是個好方法, 因此您不需要付費。

您至少要設定一個額外的全域系統管理員帳戶, 以授與其他受信任員工的系統管理員存取權。 您也可以為使用者管理建立不同的系統管理員帳戶 (這個角色稱為「**使用者管理管理員**」)。 如需詳細資訊, 請參閱[關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。

若要建立其他系統管理員帳戶:

 1. 移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理中心</a>, 然後選擇左側導覽中的 [**使用者** \> ] [作用中**使用者**]。

    ![選擇 [使用者], 然後在左側導覽中選擇 [作用中的使用者]](media/Activeusers.png)

2. 在 [作用中**使用者**] 頁面上, 選取頁面頂端的 [新增**使用者**], 然後在 [**新增使用者**] 面板上, 輸入名稱及其他資訊。
3. 展開 [**角色**] 區段, 然後選擇 [**全域管理員**], 授與此使用者的全域系統管理員存取權。 您也可以選擇 [**自訂系統管理員**], 然後選擇任何顯示的角色。

    在 [替代電子郵件地址] 文字方塊中, 輸入備用電子郵件。 您可以使用此位址, 在您鎖定時, 復原您的密碼資訊。針對全域系統管理員, 帳單報表也會傳送至此位址。

    ![選擇系統管理員角色](media/adminroles.png)
    
4. 在 [**產品授權**] 區段中, 將 [ **Microsoft 365 商務**版] 的選取器移至 [**關閉**] ** **, 並將 [**建立不含產品授權的使用者**]

    ![選擇產品授權](media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>建立緊急系統管理員帳戶

您也應該建立未使用多重要素驗證 (MFA) 進行設定的備份帳戶, 如此一來, 您就不會不慎鎖定自己, 例如, 如果您因遺失從驗證的第二個所用的電話而遺失您的電話。 請確定此帳戶的密碼是片語或至少16個字元。 這通常稱為「中斷玻璃帳戶」。

## <a name="create-a-user-account-for-yourself"></a>為自己建立使用者帳戶

使用您的使用者帳戶參與與您的組織的共同作業, 包括檢查郵件。 這表示您的系統管理員認證可能類似于*小紅 Chavez<span></span>@Contoso。 org*和您的一般使用者帳戶可能與*alice<span></span>@Contoso*相同。

若要建立新的使用者帳戶:
1. 移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理中心</a>, 然後選擇左側導覽中的 [**使用者** \> ] [作用中**使用者**]。
2. 在 [作用中**使用者**] 頁面上, 選取頁面頂端的 [新增**使用者**], 然後在 [**新增使用者**] 面板上, 輸入名稱及其他資訊。
3. 展開 [**角色**] 區段, 然後選擇 [**使用者] (無系統管理存取)**。
1. 在 [**產品授權**] 區段中, 將**Microsoft 365 商務**版的選擇器移至 [**開啟**]。 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>針對多重要素驗證註冊這些帳戶


## <a name="additional-recommendations"></a>其他建議

- 請確定系統管理員帳戶也設定為多重要素驗證。 我們將在[設定條件式存取原則](m365-campaigns-conditional-access.md)中示範如何執行這項操作。
- 使用系統管理帳戶之前, 請關閉所有不相關的瀏覽器會話和應用程式, 包括個人電子郵件帳戶。 您也可以在私人或 incognito 瀏覽器視窗中使用。
- 完成系統管理工作之後, 請務必登出瀏覽器會話。