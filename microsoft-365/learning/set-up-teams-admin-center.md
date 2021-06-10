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
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="c813d-103">在 Teams 系統管理中心中設定 Microsoft Viva 教學 (預覽) </span><span class="sxs-lookup"><span data-stu-id="c813d-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="c813d-104">本文中的資訊與在正式發行之前可能會充分修改的預覽產品有關。</span><span class="sxs-lookup"><span data-stu-id="c813d-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="c813d-105">Teams 管理員必須執行某些步驟，為租使用者中的使用者啟用 Viva 教學 (預覽) 。</span><span class="sxs-lookup"><span data-stu-id="c813d-105">The Teams administrator needs to perform certain steps to enable Viva Learning (Preview) for their users in the tenant.</span></span> <span data-ttu-id="c813d-106">根據啟用承租人的方式，這些步驟會有所不同：  [*公開預覽*](set-up-teams-admin-center.md#public-preview-tenants) 或 [*私人預覽* (或 Beta)](set-up-teams-admin-center.md#private-preview-tenants)。</span><span class="sxs-lookup"><span data-stu-id="c813d-106">These steps vary based on how the tenant is enabled:  [*Public Preview*](set-up-teams-admin-center.md#public-preview-tenants) or [*Private Preview* (or Beta)](set-up-teams-admin-center.md#private-preview-tenants).</span></span>

## <a name="public-preview-tenants"></a><span data-ttu-id="c813d-107">公開預覽承租人</span><span class="sxs-lookup"><span data-stu-id="c813d-107">Public Preview tenants</span></span>

### <a name="administrator-steps-for-public-preview-tenants"></a><span data-ttu-id="c813d-108">公開預覽承租人的管理員步驟</span><span class="sxs-lookup"><span data-stu-id="c813d-108">Administrator steps for Public Preview tenants</span></span>

<span data-ttu-id="c813d-109">因為 Viva 學習 (預覽) 尚未一般提供，所以必須執行某些步驟，才能啟用特定使用者或群組的功能和設定許可權。</span><span class="sxs-lookup"><span data-stu-id="c813d-109">Because the Viva Learning (Preview) is not yet generally available, certain steps are required to enable the features and set permissions for specific users or groups.</span></span> 

1. <span data-ttu-id="c813d-110">為 Viva 教學 (預覽) 使用者啟用公開預覽功能。</span><span class="sxs-lookup"><span data-stu-id="c813d-110">Enable Public Preview features for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="c813d-111">a.</span><span class="sxs-lookup"><span data-stu-id="c813d-111">a.</span></span> <span data-ttu-id="c813d-112">修改 Teams 更新原則，以啟用公用預覽功能。</span><span class="sxs-lookup"><span data-stu-id="c813d-112">Modify Teams update policy to enable Public Preview features.</span></span> <span data-ttu-id="c813d-113">請參閱[Microsoft Teams 公開預覽](/microsoftteams/public-preview-doc-updates)。</span><span class="sxs-lookup"><span data-stu-id="c813d-113">See [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span></span>

    <span data-ttu-id="c813d-114">b.</span><span class="sxs-lookup"><span data-stu-id="c813d-114">b.</span></span> <span data-ttu-id="c813d-115">針對將執行 Viva 教學 (預覽) 測試的使用者或群組，啟用更新原則。</span><span class="sxs-lookup"><span data-stu-id="c813d-115">Enable the update policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="c813d-116">請參閱 [將原則指派給使用者和群組](/microsoftteams/assign-policies-users-and-groups)。</span><span class="sxs-lookup"><span data-stu-id="c813d-116">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

2. <span data-ttu-id="c813d-117">修改 Viva 教學 (預覽) 使用者的應用程式許可權原則。</span><span class="sxs-lookup"><span data-stu-id="c813d-117">Modify the app permission policy for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="c813d-118">a.</span><span class="sxs-lookup"><span data-stu-id="c813d-118">a.</span></span> <span data-ttu-id="c813d-119">除非目前是全域原則的一部分，否則請允許應用程式許可權原則中的所有 Microsoft 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c813d-119">Unless it's currently part of the global policy, allow all Microsoft apps in the app permission policy.</span></span> <span data-ttu-id="c813d-120">請參閱[在 Microsoft Teams 中管理應用程式許可權原則](/microsoftteams/teams-app-permission-policies)。</span><span class="sxs-lookup"><span data-stu-id="c813d-120">See [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span> 

    <span data-ttu-id="c813d-121">b.</span><span class="sxs-lookup"><span data-stu-id="c813d-121">b.</span></span> <span data-ttu-id="c813d-122">針對將執行 Viva 教學 (預覽) 測試的使用者或群組，啟用 app 許可權原則。</span><span class="sxs-lookup"><span data-stu-id="c813d-122">Enable the app permission policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="c813d-123">請參閱 [將原則指派給使用者和群組](/microsoftteams/assign-policies-users-and-groups)。</span><span class="sxs-lookup"><span data-stu-id="c813d-123">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

3.  <span data-ttu-id="c813d-124">通知使用者將測試 Viva 教學 (預覽) 將[其組建用戶端切換成 Teams 的公開預覽](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants)。</span><span class="sxs-lookup"><span data-stu-id="c813d-124">Notify users who will test Viva Learning (Preview) to [switch their build client to Public Preview for Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c813d-125">針對公開預覽承租人，Viva 教學 (預覽) 會顯示在 Teams 系統管理中心的 **受管理應用程式** 中，直到最後的產品發行為止。</span><span class="sxs-lookup"><span data-stu-id="c813d-125">For Public Preview tenants, Viva Learning (Preview) will not be displayed in **Managed apps** in the Teams admin center until final product release.</span></span> <span data-ttu-id="c813d-126">不過，啟用 Public Preview 使用者可在設定正確的原則和許可權之後，找到 Teams 應用程式存放區中的 Viva 學習 (預覽) 並加以使用。</span><span class="sxs-lookup"><span data-stu-id="c813d-126">However, enabled Public Preview users can find Viva Learning (Preview) in the Teams app store and use it, once the correct policies and permissions have been set up.</span></span>

### <a name="user-steps-for-public-preview-tenants"></a><span data-ttu-id="c813d-127">公開預覽承租人的使用者步驟</span><span class="sxs-lookup"><span data-stu-id="c813d-127">User steps for Public Preview tenants</span></span>

<span data-ttu-id="c813d-128">已啟用公開預覽測試的使用者，若要啟用[先前所述的原則](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants)，則需要在其 Teams 用戶端[切換至公開預覽](/microsoftteams/public-preview-doc-updates#enable-public-preview)。</span><span class="sxs-lookup"><span data-stu-id="c813d-128">Users who have been enabled for Public Preview testing — by enabling the [policies previously described](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) — need to [switch to Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) in their Teams client.</span></span>

1. <span data-ttu-id="c813d-129">使用者必須選取其設定檔影像 >**關於**  >  **公開預覽**。</span><span class="sxs-lookup"><span data-stu-id="c813d-129">Users must select their profile image > **About** > **Public Preview**.</span></span>
   
    ![Teams 應用程式中顯示使用者設定檔的上方導覽](../media/learning/learning-app-select-profile-teams.png)
    
2. <span data-ttu-id="c813d-131">使用者必須接受公開預覽條款及條件。</span><span class="sxs-lookup"><span data-stu-id="c813d-131">Users must accept the Public Preview terms and conditions.</span></span>

    ![切換至公開預覽組建](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="c813d-133">使用者現在可以在 Teams 應用程式存放區找到 Viva 教學 (預覽) ，並開始使用它。</span><span class="sxs-lookup"><span data-stu-id="c813d-133">Users can now find Viva Learning (Preview) in the Teams app store and start using it.</span></span>

## <a name="private-preview-tenants"></a><span data-ttu-id="c813d-134">私人預覽承租人</span><span class="sxs-lookup"><span data-stu-id="c813d-134">Private Preview tenants</span></span>

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a><span data-ttu-id="c813d-135">私人預覽 (或 Beta) 承租人的管理員步驟</span><span class="sxs-lookup"><span data-stu-id="c813d-135">Administrator steps for Private Preview (or Beta) tenants</span></span>

<span data-ttu-id="c813d-136">針對私人預覽承租人，不需要啟用其他原則。</span><span class="sxs-lookup"><span data-stu-id="c813d-136">For Private Preview tenants, there are no additional policies that need to be enabled.</span></span> <span data-ttu-id="c813d-137">不過，Viva 教學 (預覽) 必須供組織中的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="c813d-137">However, Viva Learning (Preview) must be made available for users in your organization.</span></span>

1. <span data-ttu-id="c813d-138">在 Teams 系統管理中心的左側導覽中，移至 **Teams 應用** 程式  >  **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="c813d-138">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Teams 系統管理中心中的左側導覽，顯示 [Teams 應用程式和管理應用程式] 區段。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="c813d-140">在 [ **管理應用程式** ] 頁面上的搜尋方塊中，輸入 *Viva 教學*，然後選取 [ **Viva 教學 (預覽])**。</span><span class="sxs-lookup"><span data-stu-id="c813d-140">On the **Manage apps** page, in the search box, type *Viva Learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![[管理應用程式] 頁面中顯示搜尋方塊的 Teams 系統管理中心。](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="c813d-142">在 [ **Viva 教學 (預覽)** ] 頁面的 [ **狀態**] 下，選取 [ **允許** ]，以開啟 Viva 教學 (預覽) 。</span><span class="sxs-lookup"><span data-stu-id="c813d-142">On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

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

## <a name="next-step"></a><span data-ttu-id="c813d-144">下一步</span><span class="sxs-lookup"><span data-stu-id="c813d-144">Next step</span></span>

[<span data-ttu-id="c813d-145">設定教學內容來源以取得 Viva 教學 (預覽) Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="c813d-145">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
