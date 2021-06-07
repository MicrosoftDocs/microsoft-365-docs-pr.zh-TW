---
title: '在 Teams 系統管理中心中設定 Microsoft Viva 教學 (預覽) '
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 瞭解如何設定 Microsoft Viva 教學 (預覽) Teams 系統管理中心。
ms.openlocfilehash: 860f16bee7d93f2212072c5d738263402704272f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789228"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>在 Teams 系統管理中心中設定 Microsoft Viva 教學 (預覽) 

> [!NOTE]
> 本文中的資訊與在正式發行之前可能會充分修改的預覽產品有關。 

Teams 管理員必須執行某些步驟，為租使用者中的使用者啟用 Viva 教學 (預覽) 。 根據啟用承租人的方式，這些步驟會有所不同：  [*公開預覽*](set-up-teams-admin-center.md#public-preview-tenants) 或 [*私人預覽* (或 Beta)](set-up-teams-admin-center.md#private-preview-tenants)。

## <a name="public-preview-tenants"></a>公開預覽承租人

### <a name="administrator-steps-for-public-preview-tenants"></a>公開預覽承租人的管理員步驟

因為 Viva 學習 (預覽) 尚未一般提供，所以必須執行某些步驟，才能啟用特定使用者或群組的功能和設定許可權。 

1. 為 Viva 教學 (預覽) 使用者啟用公開預覽功能。

    a. 修改 Teams 更新原則，以啟用公用預覽功能。 請參閱[Microsoft Teams 公開預覽](/microsoftteams/public-preview-doc-updates)。

    b. 針對將執行 Viva 教學 (預覽) 測試的使用者或群組，啟用更新原則。 請參閱 [將原則指派給使用者和群組](/microsoftteams/assign-policies-users-and-groups)。

2. 修改 Viva 教學 (預覽) 使用者的應用程式許可權原則。

    a. 除非目前是全域原則的一部分，否則請允許應用程式許可權原則中的所有 Microsoft 應用程式。 請參閱[在 Microsoft Teams 中管理應用程式許可權原則](/microsoftteams/teams-app-permission-policies)。 

    b. 針對將執行 Viva 教學 (預覽) 測試的使用者或群組，啟用 app 許可權原則。 請參閱 [將原則指派給使用者和群組](/microsoftteams/assign-policies-users-and-groups)。

3.  通知使用者將測試 Viva 教學 (預覽) 將[其組建用戶端切換成 Teams 的公開預覽](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants)。

> [!IMPORTANT]
> 針對公開預覽承租人，Viva 教學 (預覽) 會顯示在 Teams 系統管理中心的 **受管理應用程式** 中，直到最後的產品發行為止。 不過，啟用 Public Preview 使用者可在設定正確的原則和許可權之後，找到 Teams 應用程式存放區中的 Viva 學習 (預覽) 並加以使用。

### <a name="user-steps-for-public-preview-tenants"></a>公開預覽承租人的使用者步驟

已啟用公開預覽測試的使用者，若要啟用[先前所述的原則](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants)，則需要在其 Teams 用戶端[切換至公開預覽](/microsoftteams/public-preview-doc-updates#enable-public-preview)。

1. 使用者必須選取其設定檔影像 >**關於**  >  **公開預覽**。
   
    ![Teams 應用程式中顯示使用者設定檔的上方導覽](../media/learning/learning-app-select-profile-teams.png)
    
2. 使用者必須接受公開預覽條款及條件。

    ![切換至公開預覽組建](../media/learning/learning-app-switch-to-public-preview.png)
 
3. 使用者現在可以在 Teams 應用程式存放區找到 Viva 教學 (預覽) ，並開始使用它。

## <a name="private-preview-tenants"></a>私人預覽承租人

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a>私人預覽 (或 Beta) 承租人的管理員步驟

針對私人預覽承租人，不需要啟用其他原則。 不過，Viva 教學 (預覽) 必須供組織中的使用者使用。

1. 在 Teams 系統管理中心的左側導覽中，移至 **Teams 應用** 程式  >  **管理應用程式**。

   ![Teams 系統管理中心中的左側導覽，顯示 [Teams 應用程式和管理應用程式] 區段。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. 在 [ **管理應用程式** ] 頁面上的搜尋方塊中，輸入 *Viva 教學*，然後選取 [ **Viva 教學 (預覽])**。

   ![[管理應用程式] 頁面中顯示搜尋方塊的 Teams 系統管理中心。](../media/learning/learning-app-teams-manage-apps-page.png)

3. 在 [ **Viva 教學 (預覽)** ] 頁面的 [ **狀態**] 下，選取 [ **允許** ]，以開啟 Viva 教學 (預覽) 。

   ![Teams 系統管理中心中的學習頁面，顯示 [狀態與應用程式設定] 區段。](../media/learning/learning-app-teams-learning-page.png)


<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center.

    2. Select **Teams** > **Update policies**.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page:

   1. Under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   2. On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

4. After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.

> [!NOTE]
>  If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview). <br><br>As part of the preview, Viva Learning (Preview) is released in Ring 3.0. If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page. To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users. <br><br>   ![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

--->

## <a name="next-step"></a>後續步驟

[設定教學內容來源以取得 Viva 教學 (預覽) Microsoft 365 系統管理中心](content-sources-365-admin-center.md)
