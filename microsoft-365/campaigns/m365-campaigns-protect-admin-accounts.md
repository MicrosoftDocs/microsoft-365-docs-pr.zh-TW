---
title: 保護您的系統管理員帳戶
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
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 瞭解如何設定和保護您的系統管理員帳戶。
ms.openlocfilehash: 0d687407fad1cec5da49dbc33ffeb84366f1c309
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398238"
---
# <a name="protect-your-administrator-accounts"></a>保護您的系統管理員帳戶

因為系統管理員帳戶具有較高的許可權，所以它們是駭客和網路罪犯的重要目標。 本文說明：

- 如何為緊急情況設定額外的系統管理員帳戶。
- 如何保護這些帳戶。

當您註冊 Microsoft 365 並輸入您的資訊時，您會自動成為全域系統管理員。全域管理員在 Microsoft 系統管理中心內具有使用者帳戶和所有其他設定的最終控制權，但不同類型的系統管理員帳戶具有不同的存取程度。 如需每種系統管理員角色之不同存取層級的詳細資訊，請參閱 [關於系統管理員角色](/office365/admin/add-users/about-admin-roles) 。

## <a name="create-additional-admin-accounts"></a>建立其他系統管理員帳戶

僅使用系統管理帳戶進行管理。 管理員應該要有個別的使用者帳戶，以便定期使用 Office 的應用程式，並且在必要時使用其管理帳戶來管理帳戶和裝置，以及在其他系統管理員職能上運作。 您也可以從系統管理員帳戶中移除 Microsoft 365 授權，這樣您就不需要付費。

您必須設定至少一個額外的全域系統管理員帳戶，以授與其他受信任員工的系統管理員存取權。 您也可以為使用者管理建立個別的系統管理員帳戶， (此角色稱為「 **使用者管理管理員** 」) 。 如需詳細資訊，請參閱 [關於系統管理員角色](/office365/admin/add-users/about-admin-roles)。

若要建立其他系統管理員帳戶：

 1. 移至 [系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理中心</a> ]，然後選擇左側導覽中的 [ **使用者**] [作用 \> 中 **使用者** ]。

    ![選擇左側流覽中的 [使用者] 和 [作用中使用者]](../media/Activeusers.png)

 2. 在 [作用中 **使用者** ] 頁面上，選取頁面頂端的 [ **新增使用者** ]，然後在 [ **新增使用者** ] 面板上，輸入名稱及其他資訊。
 3. 展開 [ **角色** ] 區段，然後選擇 [ **全域管理員** ]，以授予此使用者全域管理員存取權。 您也可以選擇 **自訂的系統管理員** ，並選擇任何顯示的角色。

    在 [ **其他電子郵件地址** ] 文字方塊中輸入備選電子郵件。 您可以使用此位址，當您鎖定時，復原您的密碼資訊。若為全域系統管理員，則也會傳送帳單報表至此位址。

    ![選擇系統管理員角色](../media/adminroles.png)

 4. 在 [**產品授權**] 區段中，將 **Microsoft 365 商務版** 的選取器移至 [**關閉**]，然後將 [**建立沒有產品許可證的使用者**]**開啟**。

    ![選擇產品授權](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>建立緊急管理員帳戶

您也應該建立未使用多重要素驗證 (MFA) 進行設定的備份帳戶，因此，如果您以第二種形式的) 驗證來遺失您的電話，則不會不慎封鎖 (（例如）。 請確定此帳戶的密碼為片語或至少16個字元的長度。 這通常稱為「斷玻璃帳戶」。

## <a name="create-a-user-account-for-yourself"></a>為自己建立使用者帳戶

使用您的使用者帳戶參與組織的共同作業，包括檢查郵件。 這表示您的系統管理員認證可能類似于  *小紅 Chavez <span></span> @Contoso. org* 和一般使用者帳戶可能類似 *alice <span></span> @Contoso .com*。

若要建立新的使用者帳戶：

1. 移至 [系統 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理中心</a> ]，然後選擇左側導覽中的 [ **使用者**] [作用 \> 中 **使用者** ]。
2. 在 [作用中 **使用者** ] 頁面上，選取頁面頂端的 [ **新增使用者** ]，然後在 [ **新增使用者** ] 面板上，輸入名稱及其他資訊。
3. 展開 [ **角色** ] 區段，然後選擇 [ **使用者 (無管理存取)**]。
4. 在 [**產品授權**] 區段中，將 **Microsoft 365 商務版** 的選取器移至 [**開啟**]。

## <a name="turn-on-security-defaults"></a>開啟安全性預設值

安全性預設值可提供 Microsoft 代表組織所管理的預先設定安全性設定，協助保護您的組織免受身分識別相關的攻擊。 這些設定包括針對所有系統管理員和使用者帳戶啟用多重要素驗證 (MFA) 。 如需安全性預設值的詳細資訊，以及若要瞭解如何啟用它們，請參閱 [開啟安全性預設值](m365-campaigns-conditional-access.md)。

## <a name="additional-recommendations"></a>其他建議

- 使用系統管理員帳戶之前，請先關閉所有不相關的瀏覽器會話和應用程式（包括個人電子郵件帳戶）。 您也可以在私人或 incognito 瀏覽器視窗中使用。
- 完成系統管理工作之後，請務必登出瀏覽器會話。
