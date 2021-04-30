---
title: '在 Teams 系統管理中心中設定 Microsoft Viva 教學 (預覽) '
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: c1427ae9fceab38046b53b31540e08d726815bda
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100896"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="ab568-103">在 Teams 系統管理中心中設定 Microsoft Viva 教學 (預覽) </span><span class="sxs-lookup"><span data-stu-id="ab568-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="ab568-104">本文中的資訊與在正式發行之前可能會充分修改的預覽產品有關。</span><span class="sxs-lookup"><span data-stu-id="ab568-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="ab568-105">Teams 系統管理員會) Teams 系統管理中心安裝 Viva 教學 (Preview 並套用許可權原則。</span><span class="sxs-lookup"><span data-stu-id="ab568-105">The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.</span></span>

## <a name="manage-settings-for-viva-learning-preview"></a><span data-ttu-id="ab568-106">管理 Viva 學習 (預覽的設定) </span><span class="sxs-lookup"><span data-stu-id="ab568-106">Manage settings for Viva Learning (Preview)</span></span>

<span data-ttu-id="ab568-107">您必須是 Teams 系統管理中心的管理員，才可執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="ab568-107">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="ab568-108">若要讓 Viva 學習 (預覽) 供組織中的使用者使用，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ab568-108">To make Viva Learning (Preview) available for users in your organization, follow these steps:</span></span>

1. <span data-ttu-id="ab568-109">在 Teams 系統管理中心的左側導覽中，移至 **Teams 應用** 程式  >  **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="ab568-109">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Teams 系統管理中心中的左側導覽，顯示 [Teams 應用程式和管理應用程式] 區段。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="ab568-111">在 [ **管理應用程式** ] 頁面上的搜尋方塊中，輸入 *Viva 教學*，然後選取 [ **Viva 教學 (預覽])**。</span><span class="sxs-lookup"><span data-stu-id="ab568-111">On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![[管理應用程式] 頁面中顯示搜尋方塊的 Teams 系統管理中心。](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="ab568-113">在「 **Viva 教學 (預覽)** 」頁面上：</span><span class="sxs-lookup"><span data-stu-id="ab568-113">On the **Viva Learning (Preview)** page:</span></span>

   1. <span data-ttu-id="ab568-114">在 [ **狀態**] 下，選取 [ **允許** ]，以開啟 Viva 教學 (預覽) 。</span><span class="sxs-lookup"><span data-stu-id="ab568-114">Under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   2. <span data-ttu-id="ab568-115">在 [**設定**] 索引標籤的 [**應用程式設定**] 底下，移至 Microsoft 365 系統管理中心，[設定教學內容來源](content-sources-365-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ab568-115">On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).</span></span>

   ![Teams 系統管理中心中的學習頁面，顯示 [狀態與應用程式設定] 區段。](../media/learning/learning-app-teams-learning-page.png)

4. <span data-ttu-id="ab568-117">在 [ **管理應用程式** 設定] 之後，移至 [ **許可權原則** 及 **設定原則** ]，將許可權授與可存取 Viva 教學 (預覽) 做為組織參與預覽的一部分的員工。</span><span class="sxs-lookup"><span data-stu-id="ab568-117">After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="ab568-118">如果您的組織4.0 是 Teams TAP100 程式的一部分，您可能需要在環3.0 中啟用核准的使用者，才能存取 Viva 教學 (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="ab568-118">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview).</span></span> <br><br><span data-ttu-id="ab568-119">做為預覽的一部分，Viva 教學 (預覽) 會在環3.0 中發行。</span><span class="sxs-lookup"><span data-stu-id="ab568-119">As part of the preview, Viva Learning (Preview) is released in Ring 3.0.</span></span> <span data-ttu-id="ab568-120">如果您的組織是在環4.0，您將不會在 [ **管理應用程式** ] 頁面上看到 Viva 學習 (預覽) 。</span><span class="sxs-lookup"><span data-stu-id="ab568-120">If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page.</span></span> <span data-ttu-id="ab568-121">若要測試應用程式，您需要建立自訂應用程式許可權原則，將其設定為 **允許所有的應用程式**，並將其指派給環3.0 核准的使用者。</span><span class="sxs-lookup"><span data-stu-id="ab568-121">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span> <br><br>   <span data-ttu-id="ab568-122">![AppsPermission-Plcy] 頁面顯示 [允許所有已選取的應用程式]。](../media/learning/learning-app-tap-appspermission-plcy.png)</span><span class="sxs-lookup"><span data-stu-id="ab568-122">![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)</span></span>

## <a name="next-step"></a><span data-ttu-id="ab568-123">下一步</span><span class="sxs-lookup"><span data-stu-id="ab568-123">Next step</span></span>

[<span data-ttu-id="ab568-124">設定教學內容來源以取得 Viva 教學 (預覽) Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="ab568-124">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)