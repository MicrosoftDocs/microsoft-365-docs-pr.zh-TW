---
title: 新增您訂閱的儲存空間
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: 瞭解如何在 Microsoft 365 訂閱中新增及減少檔存放區。 使用額外的檔案存放區，您可以在 SharePoint 線上及 OneDrive 中儲存更多內容。
ms.date: ''
ms.openlocfilehash: 7f9973054bfe97beae36e28b73a3eb2025a13e73
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324465"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="c7ad2-104">新增您訂閱的儲存空間</span><span class="sxs-lookup"><span data-stu-id="c7ad2-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c7ad2-105">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-105">The admin center is changing.</span></span> <span data-ttu-id="c7ad2-106">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c7ad2-107">如果您快要用完 SharePoint Online 網站集合的儲存空間，而您有合格方案的話，可以將儲存空間新增至您的訂閱。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="c7ad2-108">如果您在可用的附加元件清單中看不到 **Office 365 額外檔案儲存空間** ，表示您的計畫不合格。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="c7ad2-109">如需詳細資訊，請參閱 [我的方案是否可享有？](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="c7ad2-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="c7ad2-110">如果您透過大量授權或 CSP 購買訂閱，您就無法直接從 Microsoft 為您的組織購買 **Office 365 額外檔案存放區** 。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="c7ad2-111">請與您的代表或合作夥伴聯繫以取得協助。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c7ad2-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="c7ad2-112">Before you begin</span></span>

<span data-ttu-id="c7ad2-113">您必須是全域或 SharePoint 的系統管理員，才可執行本文中的工作。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="c7ad2-114">如需詳細資訊，請參閱[關於系統管理員角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="c7ad2-115">查看可用的儲存區</span><span class="sxs-lookup"><span data-stu-id="c7ad2-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c7ad2-116">在 SharePoint 系統管理中心中，移至 [使用中的 <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">網站</a> ] 頁面，並以具備組織之系統 [管理員許可權](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) 的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="c7ad2-117">在頁面右上方，查看所有網站所使用的儲存量，以及您訂閱的儲存空間總計。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="c7ad2-118">如果您的組織已在 Office 365 中設定多地理位置，此列也會顯示所有地理位置所使用的儲存量。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![「作用中的網站」頁面上的儲存區](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="c7ad2-120">使用的儲存空間不包括過去24-48 小時內所做的變更。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c7ad2-121">以 https://portal.office.de 全域或 SharePoint 管理員身分登入，然後選取 [管理] 磚以開啟系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="c7ad2-122">如果您看到一則訊息，表示您沒有存取此頁面的許可權，這表示您的組織沒有 Microsoft 365 系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="c7ad2-123">在左窗格中，選取 [系統 **管理中心**] 底下的 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="c7ad2-124">如果顯示的是傳統 SharePoint 系統管理中心，請選取頁面上方的 [立即開啟]\*\*\*\*，以開啟新的 SharePoint 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="c7ad2-125">在新 SharePoint 系統管理中心的左窗格中，選取 [使用中的網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="c7ad2-126">在頁面右上方，查看所有網站所使用的儲存量，以及您訂閱的儲存空間總計。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![「作用中的網站」頁面上的儲存區](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="c7ad2-128">使用的儲存空間不包括過去24-48 小時內所做的變更。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c7ad2-129">以 https://login.partner.microsoftonline.cn/ 全域或 SharePoint 管理員身分登入，然後選取 [管理] 磚以開啟系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="c7ad2-130"> (如果您看到的訊息您沒有存取此頁面的許可權，則表示您的組織中沒有 Microsoft 365 系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="c7ad2-131">在左窗格中，選取 [系統 **管理中心**] 底下的 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="c7ad2-132">如果顯示的是傳統 SharePoint 系統管理中心，請選取頁面上方的 [立即開啟]\*\*\*\*，以開啟新的 SharePoint 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="c7ad2-133">在新 SharePoint 系統管理中心的左窗格中，選取 [使用中的網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="c7ad2-134">在頁面右上方，查看所有網站所使用的儲存量，以及您訂閱的儲存空間總計。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![「作用中的網站」頁面上的儲存區](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="c7ad2-136">使用的儲存空間不包括過去24-48 小時內所做的變更。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="c7ad2-137">決定所使用的儲存空間量後，您可以為訂閱新增或移除儲存空間。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="c7ad2-138">若要瞭解增加儲存空間的成本，請遵循本文中的步驟，並在購買之前查看定價資訊。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="c7ad2-139">如需設定網站集合儲存限制的相關資訊，請參閱 [管理網站集合儲存限制](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="c7ad2-140">將儲存新增至您的訂閱</span><span class="sxs-lookup"><span data-stu-id="c7ad2-140">Add storage to your subscription</span></span>

<span data-ttu-id="c7ad2-141">如果您還沒有為訂閱購買額外的儲存空間，您可以這麼做。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c7ad2-142">在系統管理中心中，移至 [ **帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">購買服務</a> ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="c7ad2-143">在 [ **購買服務** ] 頁面的底部，選取 [ **附加**元件]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="c7ad2-144">選取 [ **Office 365 額外檔案儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="c7ad2-145">在 [ **Office 365 額外檔案儲存** ] 頁面上，如果已顯示，請選擇基礎訂閱，然後輸入您要新增的儲存空間數目。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="c7ad2-146">選取 [ **立即查看**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="c7ad2-147">在 [ **此外觀如何？** ] 頁面上，確認您選取的儲存體 gb 數目，然後查看定價資訊，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="c7ad2-148">在 [ **完成順序** ] 頁面上，確認 [合計]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="c7ad2-149">如果您需要進行任何變更，請選取 [ **編輯訂單**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="c7ad2-150">如果訂單需要信用檢查，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="c7ad2-151">當您完成時，請選取 [下一張 **訂單**] \> **移至**[系統管理中心]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c7ad2-152">在系統管理中心中，移至 [**帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">訂閱</a>] 頁面。  </span><span class="sxs-lookup"><span data-stu-id="c7ad2-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c7ad2-153">在 [ **訂閱** ] 頁面上，選擇您要新增儲存空間的訂閱，然後選取 [ **附加**元件]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c7ad2-155">如果您看不到 [ **附加**元件]，而且您已透過合作夥伴購買訂閱，請選取 [ \*\*大量授權服務中心 (VLSC]) \*\*。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c7ad2-156">選取 [ **購買附加**元件]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-156">Select **Buy add-ons**.</span></span>

    ![在系統管理中心的 [訂閱] 頁面上，購買附加元件連結。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="c7ad2-158">在 [ **購買服務** ] 頁面上，用滑鼠移過或點擊 [ **Office 365 額外檔案儲存**]，然後選取 [ **立即購買**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="c7ad2-159">輸入您需要的使用者授權數目，如果有顯示，請選擇基礎訂閱。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="c7ad2-160">選取 [ **立即查看**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="c7ad2-161">在 [ **此外觀如何？** ] 頁面上，確認您選取的儲存體 gb 數目，然後查看定價資訊，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="c7ad2-162">在 [ **完成順序** ] 頁面上，選取 [ **下單**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c7ad2-163">在系統管理中心中，前往 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[訂閱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c7ad2-164">在 [ **訂閱** ] 頁面上，選擇您要新增儲存空間的訂閱，然後選取 [ **附加**元件]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c7ad2-166">如果您看不到 [ **附加**元件]，而且您已透過合作夥伴購買訂閱，請選取 [ \*\*大量授權服務中心 (VLSC]) \*\*。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c7ad2-167">選取 [ **購買附加**元件]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-167">Select **Buy add-ons**.</span></span>

    ![在系統管理中心的 [訂閱] 頁面上，購買附加元件連結。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="c7ad2-169">在 [ **購買服務** ] 頁面上，用滑鼠移過或點擊 [ **Office 365 額外檔案儲存**]，然後選取 [ **立即購買**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="c7ad2-170">輸入您需要的使用者授權數目，如果有顯示，請選擇基礎訂閱。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="c7ad2-171">選取 [ **立即查看**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="c7ad2-172">在 [ **此外觀如何？** ] 頁面上，確認您選取的儲存體 gb 數目，然後查看定價資訊，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="c7ad2-173">在 [ **完成順序** ] 頁面上，選取 [ **下單**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="c7ad2-174">增加或減少儲存空間</span><span class="sxs-lookup"><span data-stu-id="c7ad2-174">Increase or decrease storage</span></span>

<span data-ttu-id="c7ad2-175">如果您已透過 **Office 365 額外檔案儲存** 空間附加元件購買額外的檔案存放區，您可以使用這些步驟來增加或減少訂閱的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="c7ad2-176">您可以將儲存體縮小為低達 1 gb。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="c7ad2-177">若要移除所有額外的儲存空間， [請與支援人員聯繫](../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c7ad2-178">在系統管理中心，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[您的產品]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="c7ad2-179">在 [ **產品** ] 索引標籤上，選取包含 **Office 365 額外檔案儲存空間** 附加元件的訂閱。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="c7ad2-180">在 [產品詳細資料] 頁面的 [ **附加** 元件] 區段中，選取 [ **管理載入**宏]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="c7ad2-181">在 [ **管理** 增益集] 窗格中，選擇 [ **附加** 元件] 清單中的 [ **Office 365 額外檔案儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="c7ad2-182">在 [ **數量** ] 文字方塊中，輸入您要用於訂閱的 gb 儲存空間數目。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="c7ad2-183">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c7ad2-184">在系統管理中心中，前往 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">[訂閱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c7ad2-185">在 [ **訂閱** ] 頁面上，選取 [ **附加**元件]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c7ad2-187">如果您看不到 [ **附加**元件]，而且您已透過合作夥伴購買訂閱，請選取 [ \*\*大量授權服務中心 (VLSC]) \*\*。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c7ad2-188">在 [ **Office 365 額外檔案儲存**] 底下，選取 [ **變更數量**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![變更數量連結。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="c7ad2-190">在右窗格中，輸入您需要的 gb 總數，然後選取 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="c7ad2-191">例如，如果您目前有 200 gb 的額外檔案存放區，但您只需要 100 gb，則可以在方塊中輸入 **100** 。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="c7ad2-192">選取 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c7ad2-193">在系統管理中心中，前往 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[訂閱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c7ad2-194">在 [ **訂閱** ] 頁面上，選取 [ **附加**元件]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c7ad2-196">如果您看不到 [ **附加**元件]，而且您已透過合作夥伴購買訂閱，請選取 [ \*\*大量授權服務中心 (VLSC]) \*\*。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c7ad2-197">在 [ **Office 365 額外檔案儲存**] 底下，選取 [ **變更數量**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![變更數量連結。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="c7ad2-199">在右窗格中，輸入您需要的 gb 總數，然後選取 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="c7ad2-200">例如，如果您目前有 200 gb 的額外檔案存放區，但您只需要 100 gb，則可以在方塊中輸入 **100** 。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="c7ad2-201">選取 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="c7ad2-202">我的方案是否符合 Office 365 額外檔案儲存空間的資格？</span><span class="sxs-lookup"><span data-stu-id="c7ad2-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="c7ad2-203">Office 365 額外檔案儲存空間適用於下列訂閱︰</span><span class="sxs-lookup"><span data-stu-id="c7ad2-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="c7ad2-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="c7ad2-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="c7ad2-205">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="c7ad2-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="c7ad2-206">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="c7ad2-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="c7ad2-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="c7ad2-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="c7ad2-208">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="c7ad2-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="c7ad2-209">使用 SharePoint 方案1的 web Office</span><span class="sxs-lookup"><span data-stu-id="c7ad2-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="c7ad2-210">使用 SharePoint 方案2的 web Office</span><span class="sxs-lookup"><span data-stu-id="c7ad2-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="c7ad2-211">SharePoint Online 方案 1</span><span class="sxs-lookup"><span data-stu-id="c7ad2-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="c7ad2-212">SharePoint Online 方案 2</span><span class="sxs-lookup"><span data-stu-id="c7ad2-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="c7ad2-213">Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="c7ad2-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="c7ad2-214">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="c7ad2-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="c7ad2-215">Microsoft 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="c7ad2-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="c7ad2-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="c7ad2-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="c7ad2-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c7ad2-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="c7ad2-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="c7ad2-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="c7ad2-219">Office 365 額外檔案儲存也適用于 GCC、GCC 高和 DOD 方案。</span><span class="sxs-lookup"><span data-stu-id="c7ad2-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="c7ad2-220">相關內容</span><span class="sxs-lookup"><span data-stu-id="c7ad2-220">Related content</span></span>

<span data-ttu-id="c7ad2-221">[管理網站儲存量限制](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (篇文章) </span><span class="sxs-lookup"><span data-stu-id="c7ad2-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="c7ad2-222">[設定 OneDrive 使用者 (文章的預設儲存空間](https://docs.microsoft.com/onedrive/set-default-storage-space)) </span><span class="sxs-lookup"><span data-stu-id="c7ad2-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
