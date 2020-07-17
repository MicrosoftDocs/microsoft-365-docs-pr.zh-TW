---
title: 新增使用者並指派授權
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 瞭解如何同時新增使用者並指派授權給 Microsoft 365。
ms.date: 07/01/2020
ms.openlocfilehash: 016c98fc93bfa1a92274a5b991cf8adbd1131bc9
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015884"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>同時新增使用者並指派授權

::: moniker range="o365-21vianet"

> [!NOTE]
> 系統管理中心正在變更。 如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。

::: moniker-end

在您的小組中，每個人都需要一個使用者帳戶，才能登入並存取[Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395)。 新增使用者帳戶的最簡單方法是在 Microsoft 365 系統管理中心一次加入一個使用者帳戶。 完成此步驟後，您的使用者就會有 Microsoft 365 授權、登入認證，以及 Microsoft 365 信箱。

## <a name="before-you-begin"></a>開始之前

您必須是全域、授權或使用者系統管理員，才能新增使用者並指派授權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

## <a name="watch-add-users-in-the-admin-center"></a>觀賞：在系統管理中心新增使用者

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> 影片中所用的步驟會顯示新增使用者的不同起點，但其餘步驟與下列程式相同。

## <a name="add-users-one-at-a-time"></a>一次新增一個使用者

::: moniker range="o365-worldwide"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的系統管理中心。
2. 移至 [**使用者**] [作用 > 中**使用者**]，然後選取 [**新增使用者**]。
3. 在 [**設定基礎**] 窗格中，填入基本的使用者資訊，然後選取 **[下一步]**。
    - **名稱**填入名字和姓氏、顯示名稱和使用者名稱。
    - **網域**為使用者的帳戶選擇網域。 例如，如果使用者的使用者名稱是 Jakob，而且網域是 contoso.com，他們會使用 jakob@contoso.com 登入。
    - **密碼設定**選擇使用自動產生的密碼或為使用者建立您自己的強式密碼。
    - 使用者必須在90天后變更其密碼。 或者，您可以選擇**要求此使用者在第一次登入時變更其密碼**。
    - 選擇是否要在使用者新增時以電子郵件傳送密碼。
4. 在 [**指派產品授權**] 窗格中，選取該使用者的位置和適當授權。 如果您沒有可用的授權，您仍然可以新增使用者，並購買額外的授權。 展開 [**應用**程式]，選取或取消選取 [應用程式]，以限制使用者擁有授權的應用程式。 選取 [下一步]****。
5. 在 [**選用設定**] 窗格中，展開 [**角色**]，讓此使用者成為系統管理員。展開 [**設定檔資訊**]，以新增其他有關使用者的資訊。
6. 選取 **[下一步]**，查看新使用者的設定，進行任何您想要的變更，然後選取 **[完成新增]**，然後按一下 [**關閉**]。

::: moniker-end

::: moniker range="o365-germany"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的系統管理中心。
2. 移至 [**使用者**] [作用 > 中**使用者**]，然後選取 [**新增使用者**]。
3. 在 [**新增使用者**] 窗格中填入下列資訊。 當您完成時，請選取 [**新增**]。
    - **名稱**：請填入名字、姓氏、顯示名稱和使用者名稱。
    - **網域**例如，如果使用者的使用者名稱是 Jakob，而且網域是 contoso.com，他們會輸入 jakob@contoso.com 來登入。
    - **連絡資訊**：展開並填入行動電話號碼、地址等資訊。
    - **密碼**使用自動產生的密碼或展開以指定使用者的強式密碼。 他們必須在90天后變更其密碼。 Or you can choose to **Make this user change their password when they first sign in**.
    - **角色**：如果您需要將這個使用者設為系統管理員的話，請展開此區段。
    - **產品授權**：展開此區段並選取合適的授權。如果您沒有可用的授權，您仍然可以新增使用者，並購買額外的授權。

::: moniker-end

::: moniker range="o365-21vianet"

1. 移至位於 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的系統管理中心。
2. 移至 [**使用者**] [作用 > 中**使用者**]，然後選取 [**新增使用者**]。
3. 在 [**新增使用者**] 窗格中填入下列資訊。 當您完成時，請選取 [**新增**]。
    - **名稱**：請填入名字、姓氏、顯示名稱和使用者名稱。
    - **網域**例如，如果使用者的使用者名稱是 Jakob，而且網域是 contoso.com，他們會輸入 jakob@contoso.com 來登入。
    - **連絡資訊**：展開並填入行動電話號碼、地址等資訊。
    - **密碼**使用自動產生的密碼或展開以指定使用者的強式密碼。 他們必須在90天后變更其密碼。 Or you can choose to **Make this user change their password when they first sign in**.
    - **角色**：如果您需要將這個使用者設為系統管理員的話，請展開此區段。
    - **產品授權**：展開此區段並選取合適的授權。如果您沒有可用的授權，您仍然可以新增使用者，並購買額外的授權。

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a>同時新增多個使用者

您可以使用下列任何一種方法，同時新增多個使用者：
  
- **使用試算表大量新增人員。** 請參閱[同時新增多個使用者](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)。
- **自動新增帳戶並指派授權** 。 請參閱[使用 Office 365 PowerShell 建立使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell)。 如果您已熟悉 Windows PowerShell Cmdlet 的用法，請選擇這個方法。
- **使用 ActiveDirectory？** [設定 Office 365 的目錄同步](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)處理。 使用 Azure AD Connect 工具複寫 Microsoft 365 中的 Active Directory 使用者帳戶（及其他 Active Directory 物件）。 [同步處理] 只會新增使用者帳戶。 您必須先將授權指派給同步處理的使用者，才能使用電子郵件和其他 Office 應用程式。
- **從 Exchange 遷移？** 查看[將多個電子郵件帳戶遷移至 Office 365 的方式](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。 當您使用「轉換」、「暫存」或「混合 Exchange」方法將多個信箱遷移至 Microsoft 365 時，會自動將使用者新增為遷移的一部分。 移轉只會新增使用者帳戶。 您必須先將授權指派給使用者，使用者才能使用電子郵件和其他 Office 應用程式。 如果您未指派授權給使用者，則在30天的寬限期過後，其信箱會停用。 瞭解如何在 Microsoft 365 系統管理中心中[指派授權給使用者](../manage/assign-licenses-to-users.md)。

## <a name="next-steps"></a>後續步驟

新增使用者後，您會收到來自 Microsoft 的電子郵件通知。 電子郵件會包含人員的使用者識別碼和密碼，讓他們能夠登入 Microsoft 365。 請以正常程序傳達新密碼。 與新的使用者分享[員工快速入門手冊](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)，以設定相關專案，例如如何[在 PC 或 Mac 上下載並安裝 office 應用程式](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)，以及如何[在行動裝置上設定 office 應用程式和電子郵件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。

## <a name="related-content"></a>相關內容

[將新員工新增至 Microsoft 365](add-new-employee.md) （文章） \
[同時將多個使用者新增至 Microsoft 365](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time) （文章） \
[在 Microsoft 365 （文章）中還原使用者](restore-user.md)\
[將授權指派給使用者](../manage/assign-licenses-to-users.md)（文章） \
[從您的組織刪除使用者](delete-a-user.md)（文章）