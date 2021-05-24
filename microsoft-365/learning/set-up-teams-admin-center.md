---
title: '在 Teams 系統管理中心中設定 Microsoft Viva 教學 (預覽) '
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/24/2021
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
ms.openlocfilehash: a96a2f3ecf7d4e1ee0c136ae155868218f08aaf4
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636131"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="41633-103">在 Teams 系統管理中心中設定 Microsoft Viva 教學 (預覽) </span><span class="sxs-lookup"><span data-stu-id="41633-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="41633-104">本文中的資訊與在正式發行之前可能會充分修改的預覽產品有關。</span><span class="sxs-lookup"><span data-stu-id="41633-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="41633-105">Teams 系統管理員會) Teams 系統管理中心安裝 Viva 教學 (Preview 並套用許可權原則。</span><span class="sxs-lookup"><span data-stu-id="41633-105">The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.</span></span>

1. <span data-ttu-id="41633-106">針對 Viva 學習 (預覽) ，您必須先在 Teams 中設定更新原則。</span><span class="sxs-lookup"><span data-stu-id="41633-106">For Viva Learning (Preview), you must first set the Update policy in Teams.</span></span> <span data-ttu-id="41633-107">如需詳細資訊，請參閱[Microsoft Teams 公開預覽](/MicrosoftTeams/public-preview-doc-updates)。</span><span class="sxs-lookup"><span data-stu-id="41633-107">For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).</span></span>

    1. <span data-ttu-id="41633-108">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="41633-108">Sign in to the Teams admin center.</span></span>

    2. <span data-ttu-id="41633-109">選取 [ **Teams**  >  **更新原則**]。</span><span class="sxs-lookup"><span data-stu-id="41633-109">Select **Teams** > **Update policies**.</span></span>

    3. <span data-ttu-id="41633-110">選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="41633-110">Select **Add**.</span></span> 

    4. <span data-ttu-id="41633-111">具名更新原則、新增原則，然後開啟 [ **顯示預覽] 功能**。</span><span class="sxs-lookup"><span data-stu-id="41633-111">Name the update policy, add a policy, and turn on **Show preview features**.</span></span>

2. <span data-ttu-id="41633-112">管理員必須通知使用者原則更新，讓使用者將其組建移至 Teams 的公開預覽。</span><span class="sxs-lookup"><span data-stu-id="41633-112">The admin must notify users of the policy update so that they move their build into the Public Preview for Teams.</span></span> 

    1. <span data-ttu-id="41633-113">使用者必須選取其設定檔影像 >**關於**  >  **公開預覽**。</span><span class="sxs-lookup"><span data-stu-id="41633-113">Users must select their profile image > **About** > **Public Preview**.</span></span>
   
        ![Teams 應用程式中顯示使用者設定檔的上方導覽](../media/learning/learning-app-select-profile-teams.png)
    
    2. <span data-ttu-id="41633-115">使用者必須接受 **公開預覽** 條款及條件。</span><span class="sxs-lookup"><span data-stu-id="41633-115">Users must accept the **Public preview** terms and conditions.</span></span>

        ![切換至公開預覽組建](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="41633-117">針對具有限制原則且需要啟用 Viva 教學 (預覽) 的組織，請依照下一節中的程式進行。</span><span class="sxs-lookup"><span data-stu-id="41633-117">For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.</span></span>

## <a name="manage-settings-for-viva-learning-preview"></a><span data-ttu-id="41633-118">管理 Viva 學習 (預覽的設定) </span><span class="sxs-lookup"><span data-stu-id="41633-118">Manage settings for Viva Learning (Preview)</span></span>

<span data-ttu-id="41633-119">您必須是 Teams 系統管理中心的管理員，才可執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="41633-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="41633-120">若要讓 Viva 學習 (預覽) 供組織中的使用者使用，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="41633-120">To make Viva Learning (Preview) available for users in your organization, follow these steps:</span></span>

1. <span data-ttu-id="41633-121">在 Teams 系統管理中心的左側導覽中，移至 **Teams 應用** 程式  >  **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="41633-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Teams 系統管理中心中的左側導覽，顯示 [Teams 應用程式和管理應用程式] 區段。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="41633-123">在 [ **管理應用程式** ] 頁面上的搜尋方塊中，輸入 *Viva 教學*，然後選取 [ **Viva 教學 (預覽])**。</span><span class="sxs-lookup"><span data-stu-id="41633-123">On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![[管理應用程式] 頁面中顯示搜尋方塊的 Teams 系統管理中心。](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="41633-125">在「 **Viva 教學 (預覽)** 」頁面上：</span><span class="sxs-lookup"><span data-stu-id="41633-125">On the **Viva Learning (Preview)** page:</span></span>

   1. <span data-ttu-id="41633-126">在 [ **狀態**] 下，選取 [ **允許** ]，以開啟 Viva 教學 (預覽) 。</span><span class="sxs-lookup"><span data-stu-id="41633-126">Under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   2. <span data-ttu-id="41633-127">在 [**設定**] 索引標籤的 [**應用程式設定**] 底下，移至 Microsoft 365 系統管理中心，[設定教學內容來源](content-sources-365-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="41633-127">On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).</span></span>

   ![Teams 系統管理中心中的學習頁面，顯示 [狀態與應用程式設定] 區段。](../media/learning/learning-app-teams-learning-page.png)

4. <span data-ttu-id="41633-129">在 [ **管理應用程式** 設定] 之後，移至 [ **許可權原則** 及 **設定原則** ]，將許可權授與可存取 Viva 教學 (預覽) 做為組織參與預覽的一部分的員工。</span><span class="sxs-lookup"><span data-stu-id="41633-129">After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="41633-130">如果您的組織4.0 是 Teams TAP100 程式的一部分，您可能需要在環3.0 中啟用核准的使用者，才能存取 Viva 教學 (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="41633-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview).</span></span> <br><br><span data-ttu-id="41633-131">做為預覽的一部分，Viva 教學 (預覽) 會在環3.0 中發行。</span><span class="sxs-lookup"><span data-stu-id="41633-131">As part of the preview, Viva Learning (Preview) is released in Ring 3.0.</span></span> <span data-ttu-id="41633-132">如果您的組織是在環4.0，您將不會在 [ **管理應用程式** ] 頁面上看到 Viva 學習 (預覽) 。</span><span class="sxs-lookup"><span data-stu-id="41633-132">If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page.</span></span> <span data-ttu-id="41633-133">若要測試應用程式，您需要建立自訂應用程式許可權原則，將其設定為 **允許所有的應用程式**，並將其指派給環3.0 核准的使用者。</span><span class="sxs-lookup"><span data-stu-id="41633-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span> <br><br>   <span data-ttu-id="41633-134">![AppsPermission-Plcy] 頁面顯示 [允許所有已選取的應用程式]。](../media/learning/learning-app-tap-appspermission-plcy.png)</span><span class="sxs-lookup"><span data-stu-id="41633-134">![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)</span></span>

## <a name="next-step"></a><span data-ttu-id="41633-135">後續步驟</span><span class="sxs-lookup"><span data-stu-id="41633-135">Next step</span></span>

[<span data-ttu-id="41633-136">設定教學內容來源以取得 Viva 教學 (預覽) Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="41633-136">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
