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
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: 瞭解如何在 Microsoft 365 訂閱中新增及減少檔存放區。 使用額外的檔案存放區，您可以在 SharePoint 線上及 OneDrive 中儲存更多內容。
ms.date: ''
ms.openlocfilehash: b170924f40d517cb6bbdf8635ad3e163eadc8643
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911923"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="f978b-104">新增您訂閱的儲存空間</span><span class="sxs-lookup"><span data-stu-id="f978b-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f978b-105">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="f978b-105">The admin center is changing.</span></span> <span data-ttu-id="f978b-106">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="f978b-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="f978b-107">如果您快要用完 SharePoint Online 網站集合的儲存空間，而您有合格方案的話，可以將儲存空間新增至您的訂閱。</span><span class="sxs-lookup"><span data-stu-id="f978b-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="f978b-108">如果您在可用的附加元件清單中看不到 **Office 365 額外檔案儲存空間** ，表示您的計畫不合格。</span><span class="sxs-lookup"><span data-stu-id="f978b-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="f978b-109">如需詳細資訊，請參閱 [我的方案是否可享有？](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="f978b-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="f978b-110">如果您透過大量授權或 CSP 購買訂閱，您就無法直接從 Microsoft 為您的組織購買 **Office 365 額外檔案存放區** 。</span><span class="sxs-lookup"><span data-stu-id="f978b-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="f978b-111">請與您的代表或合作夥伴聯繫以取得協助。</span><span class="sxs-lookup"><span data-stu-id="f978b-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f978b-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="f978b-112">Before you begin</span></span>

<span data-ttu-id="f978b-113">您必須是全域或 SharePoint 的系統管理員，才可執行本文中的工作。</span><span class="sxs-lookup"><span data-stu-id="f978b-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="f978b-114">如需詳細資訊，請參閱[關於系統管理員角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f978b-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="f978b-115">查看可用的儲存區</span><span class="sxs-lookup"><span data-stu-id="f978b-115">View available storage</span></span>

1. <span data-ttu-id="f978b-116">在 SharePoint 系統管理中心中，移至 [使用中的 <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">網站</a> ] 頁面，並以具備組織之系統 [管理員許可權](/sharepoint/sharepoint-admin-role) 的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="f978b-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="f978b-117">在頁面右上方，查看所有網站所使用的儲存空間量，以及您訂閱的總計儲存空間。</span><span class="sxs-lookup"><span data-stu-id="f978b-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="f978b-118">如果您的組織已在 Office 365 中設定多地理位置，此列也會顯示所有地理位置所使用的儲存量。</span><span class="sxs-lookup"><span data-stu-id="f978b-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![[使用中網站] 頁面上的儲存空間橫條](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="f978b-120">使用的儲存空間不包含在過去 24 到 48 小時內所做的變更。</span><span class="sxs-lookup"><span data-stu-id="f978b-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="f978b-121">決定所使用的儲存空間量後，您可以為訂閱新增或移除儲存空間。</span><span class="sxs-lookup"><span data-stu-id="f978b-121">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="f978b-122">若要瞭解增加儲存空間的成本，請遵循本文中的步驟，並查看定價資訊，再購買其他。</span><span class="sxs-lookup"><span data-stu-id="f978b-122">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="f978b-123">如需設定網站集合儲存限制的相關資訊，請參閱 [管理網站集合儲存限制](/sharepoint/manage-site-collection-storage-limits)。</span><span class="sxs-lookup"><span data-stu-id="f978b-123">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="f978b-124">將儲存新增至您的訂閱</span><span class="sxs-lookup"><span data-stu-id="f978b-124">Add storage to your subscription</span></span>

<span data-ttu-id="f978b-125">如果您還沒有為訂閱購買額外的儲存空間，您可以這麼做。</span><span class="sxs-lookup"><span data-stu-id="f978b-125">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="f978b-126">在系統管理中心中，移至 [ **帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">購買服務</a> ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f978b-126">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="f978b-127">在 [ **購買服務** ] 頁面底部的 [ **附加** 元件] 區段中，尋找 [ **Office 365 額外檔案儲存區**]，然後選取 [ **詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="f978b-127">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="f978b-128">在 [產品詳細資料] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f978b-128">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="f978b-129">如有需要，請選擇基礎訂閱，然後輸入您想要新增的儲存空間數目。</span><span class="sxs-lookup"><span data-stu-id="f978b-129">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="f978b-130">選取 [ **立即查看**]。</span><span class="sxs-lookup"><span data-stu-id="f978b-130">Select **Check out now**.</span></span>
6. <span data-ttu-id="f978b-131">在 [ **此外觀如何？** ] 頁面上，確認您選取的儲存體 gb 數目，然後查看定價資訊，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f978b-131">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="f978b-132">在 [ **完成順序** ] 頁面上，確認 [合計]。</span><span class="sxs-lookup"><span data-stu-id="f978b-132">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="f978b-133">如果您需要進行任何變更，請選取 [ **編輯訂單**]。</span><span class="sxs-lookup"><span data-stu-id="f978b-133">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="f978b-134">如果訂單需要信用檢查，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f978b-134">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="f978b-135">當您完成時，請選取 [下一張 **訂單**] \> **移至**[系統管理中心]。</span><span class="sxs-lookup"><span data-stu-id="f978b-135">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="f978b-136">增加或減少儲存空間</span><span class="sxs-lookup"><span data-stu-id="f978b-136">Increase or decrease storage</span></span>

<span data-ttu-id="f978b-137">如果您已透過 **Office 365 額外檔案儲存區** 購買額外的檔案存放區，您可以使用這些步驟來增加或減少訂閱的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="f978b-137">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="f978b-138">您可以將儲存體縮小為低達 1 gb。</span><span class="sxs-lookup"><span data-stu-id="f978b-138">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="f978b-139">若要移除所有額外的儲存空間， [請與支援人員聯繫](../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="f978b-139">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

1. <span data-ttu-id="f978b-140">在系統管理中心，移至 [帳單 **]** \> [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="f978b-140">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="f978b-141">在 [ **產品** ] 索引標籤上，選取包含 **Office 365 額外檔案儲存空間** 附加元件的訂閱。</span><span class="sxs-lookup"><span data-stu-id="f978b-141">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="f978b-142">在 [產品詳細資料] 頁面的 [ **附加** 元件] 區段中，選取 [ **管理載入** 宏]。</span><span class="sxs-lookup"><span data-stu-id="f978b-142">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="f978b-143">在 [ **管理** 增益集] 窗格中，選擇 [ **附加** 元件] 清單中的 [ **Office 365 額外檔案儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f978b-143">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="f978b-144">在 [ **數量** ] 文字方塊中，輸入您要用於訂閱的 gb 儲存空間數目。</span><span class="sxs-lookup"><span data-stu-id="f978b-144">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="f978b-145">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="f978b-145">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="f978b-146">我的方案是否符合 Office 365 額外檔案儲存空間的資格？</span><span class="sxs-lookup"><span data-stu-id="f978b-146">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="f978b-147">Office 365 額外檔案儲存空間適用於下列訂閱︰</span><span class="sxs-lookup"><span data-stu-id="f978b-147">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="f978b-148">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="f978b-148">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="f978b-149">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="f978b-149">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="f978b-150">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="f978b-150">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="f978b-151">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="f978b-151">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="f978b-152">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="f978b-152">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="f978b-153">使用 SharePoint 方案1的 web Office</span><span class="sxs-lookup"><span data-stu-id="f978b-153">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="f978b-154">使用 SharePoint 方案2的 web Office</span><span class="sxs-lookup"><span data-stu-id="f978b-154">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="f978b-155">SharePoint Online 方案 1</span><span class="sxs-lookup"><span data-stu-id="f978b-155">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="f978b-156">SharePoint Online 方案 2</span><span class="sxs-lookup"><span data-stu-id="f978b-156">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="f978b-157">Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="f978b-157">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="f978b-158">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="f978b-158">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="f978b-159">Microsoft 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="f978b-159">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="f978b-160">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="f978b-160">Microsoft 365 E3</span></span>
- <span data-ttu-id="f978b-161">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f978b-161">Microsoft 365 E5</span></span>
- <span data-ttu-id="f978b-162">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="f978b-162">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="f978b-163">Office 365 額外檔案儲存也適用于 GCC、GCC 高和 DOD 方案。</span><span class="sxs-lookup"><span data-stu-id="f978b-163">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="f978b-164">相關內容</span><span class="sxs-lookup"><span data-stu-id="f978b-164">Related content</span></span>

<span data-ttu-id="f978b-165">[管理網站儲存量限制](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (篇文章) </span><span class="sxs-lookup"><span data-stu-id="f978b-165">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="f978b-166">[設定 OneDrive 使用者 (文章的預設儲存空間](/onedrive/set-default-storage-space)) </span><span class="sxs-lookup"><span data-stu-id="f978b-166">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>