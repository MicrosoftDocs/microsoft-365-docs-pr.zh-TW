---
title: 新增使用者並指派授權
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解如何同時新增使用者並指派授權給 Microsoft 365。
ms.date: 07/01/2020
ms.openlocfilehash: 71695c47bbc34a94f0040c37dd0c0bb0ab72fbba
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741410"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>同時新增使用者並指派授權

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。

::: moniker-end

小組裡的每個人都需要一個使用者帳戶，才能登入並存取[商務用 Microsoft 365](https://www.microsoft.com/microsoft-365/business)。 新增使用者帳戶最簡單的方法是在 Microsoft 365 系統管理中心一次新增一個帳戶。 執行此步驟之後，您的使用者會擁有 Microsoft 365 授權、登入認證和 Microsoft 365 信箱。

## <a name="before-you-begin"></a>開始之前

您必須是全域、授權或使用者系統管理員，才能新增使用者並指派授權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

## <a name="watch-add-users-in-the-admin-center"></a>觀賞：在系統管理中心新增使用者

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> 影片中使用的步驟顯示新增使用者的不同起點，但其餘步驟與下列程序相同。

## <a name="add-users-one-at-a-time"></a>一次新增一個使用者

::: moniker range="o365-worldwide"

1. 移至位於 <https://admin.microsoft.com> 的系統管理中心。
2. 移至 [使用者 **]** > [作用中使用者 **]**，然後選取 [新增使用者 **]**。
3. 在 [設定基本資料 **]** 窗格中，填入基本使用者資訊，然後選取 [下一步 **]**。
    - **名稱**：填入名字和姓氏、顯示名稱和使用者名稱。
    - **網域**：選擇使用者帳戶的網域。 例如，如果使用者的使用者名稱是 Jakob，而網域為 contoso.com，他們可以使用 jakob@contoso.com 來登入。
    - **密碼設定**：選擇使用自動產生的密碼，或是為使用者建立您自己的強式密碼。
    - 使用者必須在 90 天後變更他們的密碼。 或者，您可以選擇 [要求此使用者在第一次登入時變更密碼 **]**。
    - 選擇是否要在新增使用者時透過電子郵件傳送密碼。
4. 在 [指派產品授權 **]** 窗格中，選取使用者的位置和適當的授權。 如果您沒有任何可用的授權，您仍然可以新增使用者，並購買額外的授權。 展開 [應用程式 **]** 並選取或取消選取應用程式，以限制使用者擁有授權的應用程式。 選取 [下一步 **]**。
5. 在 [選用設定 **]** 窗格中，展開 [角色 **]** 以讓此使用者成為系統管理員。展開 [設定檔資訊 **]** 以新增有關使用者的其他資訊。
6. 選取 [下一步 **]**，檢閱新使用者的設定，進行您喜歡的任何變更，然後選取 [完成新增 **]**，然後選取 [關閉 **]**。

::: moniker-end

::: moniker range="o365-germany"

1. 移至位於 <https://portal.office.de/adminportal> 的系統管理中心。
2. 移至 [使用者 **]** > [作用中使用者 **]**，然後選取 [新增使用者 **]**。
3. 在 [新增使用者 **]** 窗格中，填入下列資訊。 完成時，選取 [新增 **]**。
    - **名稱**：填入名字、姓氏、顯示名稱和使用者名稱。
    - **網域**：例如，如果使用者的使用者名稱是 Jakob，而網域為 contoso.com，他們可以輸入 jakob@contoso.com 來登入。
    - **連絡資訊**：展開以填入行動電話號碼、地址等資訊。
    - **密碼**：使用自動產生的密碼，或展開以為該使用者指定強式密碼。 他們必須在 90 天後變更他們的密碼。 Or you can choose to **Make this user change their password when they first sign in**.
    - **角色**：如果您需要將這個使用者設為系統管理員的話，請展開此區段。
    - **產品授權**：展開此區段並選取合適的授權。如果您沒有可用的授權，您仍然可以新增使用者，並購買額外的授權。

::: moniker-end

::: moniker range="o365-21vianet"

1. 移至位於 <https://portal.partner.microsoftonline.cn> 的系統管理中心。
2. 移至 [使用者 **]** > [作用中使用者 **]**，然後選取 [新增使用者 **]**。
3. 在 [新增使用者 **]** 窗格中，填入下列資訊。 完成時，選取 [新增 **]**。
    - **名稱**：填入名字、姓氏、顯示名稱和使用者名稱。
    - **網域**：例如，如果使用者的使用者名稱是 Jakob，而網域為 contoso.com，他們可以輸入 jakob@contoso.com 來登入。
    - **連絡資訊**：展開以填入行動電話號碼、地址等資訊。
    - **密碼**：使用自動產生的密碼，或展開以為該使用者指定強式密碼。 他們必須在 90 天後變更他們的密碼。 Or you can choose to **Make this user change their password when they first sign in**.
    - **角色**：如果您需要將這個使用者設為系統管理員的話，請展開此區段。
    - **產品授權**：展開此區段並選取合適的授權。如果您沒有可用的授權，您仍然可以新增使用者，並購買額外的授權。

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a>同時新增多個使用者

您可以使用下列任一方法，同時新增多個使用者：

- **使用試算表大量新增人員。** 請參閱[同時新增多個使用者](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time)。
- **將新增帳戶和指派授權自動化。** 請參閱[使用 Microsoft 365 PowerShell 建立使用者帳戶](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell)。 如果您已熟悉使用 Windows PowerShell Cmdlet，請選擇此方法。
- **使用 ActiveDirectory？** [設定 Microsoft 365 的目錄同步處理](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)。 使用 Azure AD Connect 工具來複製 Microsoft 365 中的 Active Directory 使用者帳戶 (與其他 Active Directory 物件)。 同步只會新增使用者帳戶。 您必須先將授權指派給同步的使用者，之後他們才能使用電子郵件及其他 Office 應用程式。
- **從 Exchange Server 移轉？** 請參閱[將多個電子郵件帳戶移轉到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。 當您使用完全移轉、分段移轉或混合式 Exchange 方法，將多個信箱移轉到 Microsoft 365 時，您會在移轉過程中自動新增使用者。 移轉只會新增使用者帳戶。 您必須先將授權指派給使用者，之後他們才能使用電子郵件及其他 Office 應用程式。 如果您未指派授權給使用者，則其信箱會在 30 天的寬限期後停用。 了解如何[在 Microsoft 365 系統管理中心指派授權指派給使用者](../manage/assign-licenses-to-users.md)。

## <a name="next-steps"></a>後續步驟

新增使用者之後，您會收到來自 Microsoft 的電子郵件通知。 電子郵件會包含該人員的使用者識別碼與密碼，讓他們可以登入 Microsoft 365。 以正常程序傳達新密碼。 請與您的新使用者分享[員工快速入門指南](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)，以設定相關項目，例如如何[在 PC 或 Mac 上下載並安裝 Office 應用程式](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)，以及如何[在行動裝置上設定 Office 應用程式和電子郵件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。

## <a name="related-content"></a>相關內容

[將新員工新增至 Microsoft 365](add-new-employee.md) (文章)\
[同時將多位使用者新增至 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (文章)\
[在 Microsoft 365 中還原使用者](restore-user.md) (文章)\
[將授權指派給使用者](../manage/assign-licenses-to-users.md) (文章)\
[刪除組織中的使用者](delete-a-user.md) (文章)\
