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
description: 了解如何設定和保護您的系統管理員帳戶。
ms.openlocfilehash: 76c90b48e0f0859ed856b6e3dc772aedfc2ccdaf
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753740"
---
# <a name="protect-your-administrator-accounts"></a>保護您的系統管理員帳戶

系統管理員帳戶會隨附提升的權限，因為它們的駭客和網路罪犯寶貴的目標。 本文說明：

- 如何設定緊急情況納入考量的其他系統管理員帳戶。
- 如何保護這些帳戶。
 
當您註冊 Microsoft 365 商務版，並輸入您的資訊時，會自動成為全域系統管理員。全域系統管理員具有使用者帳戶的最終控制項和其他所有設定在 Microsoft 系統管理中心中，但有許多不同種類的系統管理員帳戶具有不同程度的存取。 請參閱[關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)的系統管理員角色的每一種不同的存取層級的相關資訊。


## <a name="create-additional-admin-accounts"></a>建立其他系統管理員帳戶

使用系統管理員帳戶僅適用於管理。 系統管理員應該有個別的使用者帳戶的 Office 應用程式的一般用於與僅使用其時管理帳戶和裝置，以及其他系統函數工作時所需的系統管理帳戶。 它也是系統管理員帳戶的 Microsoft 365 商務版授權移除，因此您不需要支付它們是個好主意。

想要設定至少一個其他的全域系統管理員帳戶，將系統管理存取權授與另一個受信任的員工。 您也可以建立不同的系統管理員帳戶的使用者管理 （此角色會呼叫**使用者管理系統管理員**）。 如需詳細資訊，請參閱[關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。

若要建立其他系統管理員帳戶：

 1. 移至<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">系統管理中心</a>，然後選擇 [**使用者**\>左側的 **[作用中使用者**

    ![在左側導覽中選擇使用者，然後作用中使用者](media/Activeusers.png)

2. 在 [**作用中使用者**] 頁面上，選取頂端] 頁面上，並且在 [**新增使用者**] 面板上的 [**新增使用者**，輸入名稱，以及其他資訊。
3. 依序展開 [**角色**] 區段中，並選擇**全域系統管理員**授與此使用者的全域系統管理員存取權。 您也可以選擇**自訂的系統管理員**，然後選擇 [任何會顯示角色。

    在 [**備用電子郵件地址**] 文字方塊中輸入備用電子郵件。 您可以使用這個地址來復原您的密碼資訊，如果您要取得鎖定。全域系統管理員，帳單會傳送到這個地址。

    ![選擇系統管理員角色](media/adminroles.png)
    
4. 在 [**產品授權**] 區段中，移動選取器**Microsoft 365 商務**版來**關閉**使用中] 及 [**產品授權沒有建立使用者****上**。

    ![選擇 [產品授權](media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>建立緊急系統管理員帳戶

您也應該建立未設定，以多重要素驗證 (MFA) 讓您不小心鎖定自行備份帳戶 （例如如果您遺失您正在使用作為第二個表單式驗證的電話）。 請確定此帳戶的密碼是片語或，至少有 16 個字元長時間。 這通常稱為 「 中斷玻璃帳戶 」。

## <a name="create-a-user-account-for-yourself"></a>建立您自己的使用者帳戶

使用您的使用者帳戶來參與共同作業與您的組織，包括檢查郵件。 這表示您的系統管理員認證可能會類似於*Alice.Chavez<span></span>@Contoso.org*及一般使用者帳戶，您可能會類似於*Alice<span></span>@Contoso.com*。

若要建立新的使用者帳戶：
1. 移至<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">系統管理中心</a>，然後選擇 [**使用者**\>左側的 **[作用中使用者**
2. 在 [**作用中使用者**] 頁面上，選取頂端] 頁面上，並且在 [**新增使用者**] 面板上的 [**新增使用者**，輸入名稱，以及其他資訊。
3. 依序展開 [**角色**] 區段中，然後選擇 [**使用者 （沒有管理存取）**。
1. 在 [**產品授權**] 區段中，將選擇器**Microsoft 365 商務**版往**上**。 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>註冊每個這些帳戶的多重要素驗證


## <a name="additional-recommendations"></a>其他建議

- 請務必針對多重要素驗證也設定系統管理員帳戶。 我們將顯示您如何執行這項操作中[設定條件式存取原則](m365-campaigns-conditional-access.md)。
- 使用系統管理員帳戶之前, 關閉所有不相關的瀏覽器工作階段和應用程式，包括個人電子郵件帳戶。 您也可以使用私人，或 incognito 瀏覽器視窗中。
- 完成之後系統管理工作，請務必先登出瀏覽器工作階段。