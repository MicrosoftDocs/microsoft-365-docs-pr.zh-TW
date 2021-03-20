---
title: 管理自動宣告原則
f1.keywords:
- CSH
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
description: 瞭解如何建立及管理自動宣告原則，以自動將授權指派給某些應用程式的使用者。
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
ms.openlocfilehash: bf3f79e425b3f7cd86f1a5ab95a337ef5127e345
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911467"
---
# <a name="manage-auto-claim-policies"></a><span data-ttu-id="99b04-103">管理自動宣告原則</span><span class="sxs-lookup"><span data-stu-id="99b04-103">Manage auto-claim policies</span></span>

<span data-ttu-id="99b04-104">自動宣告原則可讓使用者在第一次登入至應用程式時，自動宣告產品的授權。</span><span class="sxs-lookup"><span data-stu-id="99b04-104">An auto-claim policy lets users automatically claim a license for a product the first time that they sign into an app.</span></span> <span data-ttu-id="99b04-105">身為系統管理員，您一般會以手動方式或使用以群組為基礎的授權，將授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="99b04-105">As an admin, you typically assign licenses to users either manually, or by using group-based licensing.</span></span> <span data-ttu-id="99b04-106">使用自動宣告原則，可管理使用者可自動宣告授權的產品。</span><span class="sxs-lookup"><span data-stu-id="99b04-106">By using auto-claim policies, you manage the products for which users can automatically claim licenses.</span></span> <span data-ttu-id="99b04-107">您也可以控制哪些授權來源的產品。</span><span class="sxs-lookup"><span data-stu-id="99b04-107">You can also control which products those licenses come from.</span></span>

<span data-ttu-id="99b04-108">在您建立自動宣告原則之後，您可以執行下列工作來管理原則：</span><span class="sxs-lookup"><span data-stu-id="99b04-108">After you create an auto-claim policy, you can do the following tasks to manage the policy:</span></span>

- [<span data-ttu-id="99b04-109">開啟或關閉原則</span><span class="sxs-lookup"><span data-stu-id="99b04-109">Turn the policy on or off</span></span>](#turn-a-policy-on-or-off)
- [<span data-ttu-id="99b04-110">編輯原則易記名稱</span><span class="sxs-lookup"><span data-stu-id="99b04-110">Edit the policy friendly name</span></span>](#edit-the-policy-friendly-name)
- [<span data-ttu-id="99b04-111">新增或移除備份產品</span><span class="sxs-lookup"><span data-stu-id="99b04-111">Add or remove backup products</span></span>](#add-or-remove-backup-products)
- [<span data-ttu-id="99b04-112">管理指派應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="99b04-112">Manage the assigning apps and services</span></span>](#change-the-assigning-apps-and-services)
- [<span data-ttu-id="99b04-113">變更指派順序</span><span class="sxs-lookup"><span data-stu-id="99b04-113">Change the assigning order</span></span>](#change-the-assigning-order-for-backup-products)
- [<span data-ttu-id="99b04-114">查看原則報表</span><span class="sxs-lookup"><span data-stu-id="99b04-114">View a policy report</span></span>](#view-an-auto-claim-policy-report)

> [!IMPORTANT]
> <span data-ttu-id="99b04-115">「自動宣告」原則目前僅適用于 Microsoft 小組。</span><span class="sxs-lookup"><span data-stu-id="99b04-115">Auto-claim policies are currently only available for Microsoft Teams.</span></span> <span data-ttu-id="99b04-116">未來可使用的產品越多。</span><span class="sxs-lookup"><span data-stu-id="99b04-116">More products will be available to use in the future.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="99b04-117">開始之前</span><span class="sxs-lookup"><span data-stu-id="99b04-117">Before you begin</span></span>

<span data-ttu-id="99b04-118">您必須是全域系統管理員，才能建立及管理自動宣告原則。</span><span class="sxs-lookup"><span data-stu-id="99b04-118">You must be a Global admin to create and manage auto-claim policies.</span></span> <span data-ttu-id="99b04-119">如需詳細資訊，請參閱[關於 Microsoft 365 系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="99b04-119">For more information, see [About Microsoft 365 admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a><span data-ttu-id="99b04-120">開啟或關閉自動理賠原則功能</span><span class="sxs-lookup"><span data-stu-id="99b04-120">Turn the auto-claim policy feature on or off</span></span>

<span data-ttu-id="99b04-121">預設會關閉自動理賠原則功能。</span><span class="sxs-lookup"><span data-stu-id="99b04-121">By default, the auto-claim policy feature is turned off.</span></span> <span data-ttu-id="99b04-122">在您可以使用此功能之前，您必須先將其開啟。</span><span class="sxs-lookup"><span data-stu-id="99b04-122">Before you can use the feature, you must first turn it on.</span></span> <span data-ttu-id="99b04-123">在您開啟功能之後，您可以建立自動宣告原則。</span><span class="sxs-lookup"><span data-stu-id="99b04-123">After you turn on the feature, you can create an auto-claim policy.</span></span>

### <a name="turn-on-auto-claim-policies"></a><span data-ttu-id="99b04-124">開啟自動宣告原則</span><span class="sxs-lookup"><span data-stu-id="99b04-124">Turn on auto-claim policies</span></span>

1. <span data-ttu-id="99b04-125">在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="99b04-125">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="99b04-126">在頁面的中央，選取 [ **開啟設定** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="99b04-126">In the center of the page, select the **Turn on setting** button.</span></span>

### <a name="turn-off-auto-claim-policies"></a><span data-ttu-id="99b04-127">關閉自動宣告原則</span><span class="sxs-lookup"><span data-stu-id="99b04-127">Turn off auto-claim policies</span></span>

1. <span data-ttu-id="99b04-128">在系統管理中心中，移至 [ **設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">組織設定</a> ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="99b04-128">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Org settings</a> page.</span></span>
2. <span data-ttu-id="99b04-129">在表格底部附近，選取 [ **使用者擁有的應用程式和服務**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-129">Near the bottom of the table, select **User owned apps and services**.</span></span>
3. <span data-ttu-id="99b04-130">在右窗格中，清除 [ **讓使用者在第一次登入時自動宣告授權**] 方塊。</span><span class="sxs-lookup"><span data-stu-id="99b04-130">In the right pane, clear the box for **Let users auto-claim licenses the first time they sign in**.</span></span>

<span data-ttu-id="99b04-131">如果您已有作用中的原則，但不想讓任何使用者宣告授權，請 [關閉原則](#turn-a-policy-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="99b04-131">If you already have an active policy, but you don't want any more users to claim licenses, [turn off the policy](#turn-a-policy-on-or-off).</span></span> <span data-ttu-id="99b04-132">當您關閉自動宣告原則時，就不會有其他使用者可以從該點宣告授權。</span><span class="sxs-lookup"><span data-stu-id="99b04-132">When you turn off an auto-claim policy, no more users can claim a license from that point on.</span></span> <span data-ttu-id="99b04-133">已宣告授權的使用者不會遺失其授權。</span><span class="sxs-lookup"><span data-stu-id="99b04-133">Users who already claimed a license don't lose their license.</span></span>

## <a name="create-an-auto-claim-policy"></a><span data-ttu-id="99b04-134">建立自動宣告原則</span><span class="sxs-lookup"><span data-stu-id="99b04-134">Create an auto-claim policy</span></span>

<span data-ttu-id="99b04-135">[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動報銷宣告原則</a> ] 索引標籤會列出您建立的原則。</span><span class="sxs-lookup"><span data-stu-id="99b04-135">The <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab lists the policies that you create.</span></span> <span data-ttu-id="99b04-136">在此索引標籤上，您可以看到：原則的名稱、與原則相關聯的應用程式、指派給原則的產品、可用授權的數目，以及原則的狀態。</span><span class="sxs-lookup"><span data-stu-id="99b04-136">On this tab, you can see: the name of the policy, the app that is associated with the policy, the product that's assigned to the policy, the number of available licenses, and the status of the policy.</span></span>

<span data-ttu-id="99b04-137">當您建立自動宣告原則時，您可以在其中新增備份產品。</span><span class="sxs-lookup"><span data-stu-id="99b04-137">When you create an auto-claim policy, you can add a backup product to it.</span></span> <span data-ttu-id="99b04-138">如果主要產品的授權不足，將會使用備份產品將授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="99b04-138">If the primary product is out of licenses, the backup product is used to assign licenses to users.</span></span> <span data-ttu-id="99b04-139">您最多可以新增四個備份產品，並 [變更其使用順序](#change-the-assigning-order-for-backup-products)。</span><span class="sxs-lookup"><span data-stu-id="99b04-139">You can add up to four backup products and [change the order in which they're used](#change-the-assigning-order-for-backup-products).</span></span> <span data-ttu-id="99b04-140">若要深入瞭解，請參閱 [新增或移除備份產品](#add-or-remove-backup-products)。</span><span class="sxs-lookup"><span data-stu-id="99b04-140">To learn more, see [Add or remove backup products](#add-or-remove-backup-products).</span></span>

> [!NOTE]
> <span data-ttu-id="99b04-141">目前，您只可以建立一個自動宣告原則。</span><span class="sxs-lookup"><span data-stu-id="99b04-141">Currently, you can only create one auto-claim policy.</span></span> <span data-ttu-id="99b04-142">您可以建立的原則數目會隨著更多的產品能夠使用此功能而增加。</span><span class="sxs-lookup"><span data-stu-id="99b04-142">The number of policies you can create will increase as more products are able to use this feature.</span></span>

1. <span data-ttu-id="99b04-143">在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="99b04-143">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="99b04-144">選取 [ **新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-144">Select **Add a policy**.</span></span>
3. <span data-ttu-id="99b04-145">在 [ **名稱此自動宣告原則** ] 頁面上，輸入原則的名稱，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="99b04-145">On the **Name this auto-claim policy** page, enter a name for the policy, then select **Next**.</span></span>
4. <span data-ttu-id="99b04-146">在 [ **設定自動宣告應用程式和產品** ] 頁面上，選取要指派授權的應用程式和訂閱。</span><span class="sxs-lookup"><span data-stu-id="99b04-146">On the **Set an auto-claim app and product** page, select an app and the subscription to assign licenses from.</span></span>
5. <span data-ttu-id="99b04-147">如果您想要新增備份產品，請選取 [ **新增備份產品至這個原則**]，然後從清單中選取產品。</span><span class="sxs-lookup"><span data-stu-id="99b04-147">If you want to add a backup product, select **Add a backup product to this policy**, then select the product from the list.</span></span>
6. <span data-ttu-id="99b04-148">選取 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="99b04-148">Select **Next**.</span></span>
7. <span data-ttu-id="99b04-149">在 [ **選取應用程式** ] 頁面上，清除或選取要排除或包含在授權中的應用程式方塊，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="99b04-149">On the **Select apps** page, clear or select the boxes for the apps to exclude or include with the license, then select **Next**.</span></span>
8. <span data-ttu-id="99b04-150">如果您已新增一或多個備份產品，請對每個產品重複步驟7。</span><span class="sxs-lookup"><span data-stu-id="99b04-150">If you added one or more backup products, repeat step 7 for each product.</span></span> <span data-ttu-id="99b04-151">否則，請移至步驟9。</span><span class="sxs-lookup"><span data-stu-id="99b04-151">Otherwise, go to step 9.</span></span>
9. <span data-ttu-id="99b04-152">在 [ **檢查和完成]** 頁面上，確認新的原則資訊，進行必要的變更，然後選取 [ **建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-152">On the **Review and finish** page, verify the new policy information, make any necessary changes, then select **Create policy**.</span></span>
10. <span data-ttu-id="99b04-153">選取 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="99b04-153">Select **Close**.</span></span>

## <a name="turn-a-policy-on-or-off"></a><span data-ttu-id="99b04-154">開啟或關閉原則</span><span class="sxs-lookup"><span data-stu-id="99b04-154">Turn a policy on or off</span></span>

<span data-ttu-id="99b04-155">當您關閉原則時，就不會有其他使用者可以宣告該原則下的授權。</span><span class="sxs-lookup"><span data-stu-id="99b04-155">When you turn off a policy, no more users can claim licenses under that policy.</span></span> <span data-ttu-id="99b04-156">此變更不會影響在該原則下已宣告授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="99b04-156">The change doesn't affect users who already claimed licenses under that policy.</span></span>

1. <span data-ttu-id="99b04-157">在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="99b04-157">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="99b04-158">選取您要編輯的原則。</span><span class="sxs-lookup"><span data-stu-id="99b04-158">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="99b04-159">在詳細資料窗格的 [ **開啟或關閉此原則**] 下，選取或清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="99b04-159">In the details pane, under **Turn this policy on or off**, select or clear the check box.</span></span>
4. <span data-ttu-id="99b04-160">選取 [ **儲存** ] 以關閉 [詳細資料] 窗格。</span><span class="sxs-lookup"><span data-stu-id="99b04-160">Select **Save** to close the details pane.</span></span>

## <a name="edit-the-policy-friendly-name"></a><span data-ttu-id="99b04-161">編輯原則易記名稱</span><span class="sxs-lookup"><span data-stu-id="99b04-161">Edit the policy friendly name</span></span>

1. <span data-ttu-id="99b04-162">在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="99b04-162">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="99b04-163">選取您要編輯的原則。</span><span class="sxs-lookup"><span data-stu-id="99b04-163">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="99b04-164">在 [詳細資料] 窗格的 [ **原則名稱** ] 區段中，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-164">In the details pane, in the **Policy name** section, select **Edit**.</span></span>
4. <span data-ttu-id="99b04-165">輸入新的原則名稱，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-165">Enter a new policy name, then select **Save**.</span></span>
5. <span data-ttu-id="99b04-166">選取 [ **儲存** ] 以關閉 [詳細資料] 窗格。</span><span class="sxs-lookup"><span data-stu-id="99b04-166">Select **Save** to close the details pane.</span></span>

## <a name="add-or-remove-backup-products"></a><span data-ttu-id="99b04-167">新增或移除備份產品</span><span class="sxs-lookup"><span data-stu-id="99b04-167">Add or remove backup products</span></span>

<span data-ttu-id="99b04-168">當您建立原則時，您可以在其中新增產品。</span><span class="sxs-lookup"><span data-stu-id="99b04-168">When you create a policy, you add a product to it.</span></span> <span data-ttu-id="99b04-169">然後，系統會自動將授權指派給該授權集區中的使用者。</span><span class="sxs-lookup"><span data-stu-id="99b04-169">Licenses are then automatically assigned to users from that pool of licenses.</span></span> <span data-ttu-id="99b04-170">您可以隨時新增或移除自動理賠原則的產品。</span><span class="sxs-lookup"><span data-stu-id="99b04-170">You can add or remove products for an auto-claim policy at any time.</span></span> <span data-ttu-id="99b04-171">如果您已有一個產品與原則相關聯，則您新增的任何產品都會視為備份產品。</span><span class="sxs-lookup"><span data-stu-id="99b04-171">If you already have one product associated with the policy, any products that you add are considered backup products.</span></span> <span data-ttu-id="99b04-172">使用第一項產品的可用授權數量時，該原則會使用清單中的下一個備份產品來指派授權。</span><span class="sxs-lookup"><span data-stu-id="99b04-172">When the available number of licenses from the first product are used up, the policy uses the next backup product on the list to assign licenses from.</span></span> <span data-ttu-id="99b04-173">您 [可以視需要重新排序產品清單](#change-the-assigning-apps-and-services) 。</span><span class="sxs-lookup"><span data-stu-id="99b04-173">You [can reorder the list of products](#change-the-assigning-apps-and-services) as you like.</span></span>

<span data-ttu-id="99b04-174">當您移除備份產品時，將不再用來指派授權。</span><span class="sxs-lookup"><span data-stu-id="99b04-174">When you remove a backup product, it's no longer used to assign licenses.</span></span> <span data-ttu-id="99b04-175">現有授權的使用者仍具有該授權，但沒有新的使用者可以接收該產品的授權。</span><span class="sxs-lookup"><span data-stu-id="99b04-175">Users with an existing license still have that license, but no new users can receive licenses for that product.</span></span>

> [!NOTE]
> <span data-ttu-id="99b04-176">自動宣告原則至少必須包含一個產品。</span><span class="sxs-lookup"><span data-stu-id="99b04-176">An auto-claim policy must contain at least one product.</span></span> <span data-ttu-id="99b04-177">您無法移除原則中的所有產品。</span><span class="sxs-lookup"><span data-stu-id="99b04-177">You can't remove all products from a policy.</span></span> <span data-ttu-id="99b04-178">如果您不想要再指派特定自動宣告原則的授權，請 [關閉原則](#view-an-auto-claim-policy-report)。</span><span class="sxs-lookup"><span data-stu-id="99b04-178">If you don't want to assign licenses from a specific auto-claim policy anymore, [turn off the policy](#view-an-auto-claim-policy-report).</span></span>

### <a name="add-a-backup-product"></a><span data-ttu-id="99b04-179">新增備份產品</span><span class="sxs-lookup"><span data-stu-id="99b04-179">Add a backup product</span></span>

1. <span data-ttu-id="99b04-180">在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="99b04-180">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="99b04-181">選取您要編輯的原則。</span><span class="sxs-lookup"><span data-stu-id="99b04-181">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="99b04-182">在 [詳細資料] 窗格的底部，選取 [ **新增備份產品至此原則**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-182">In the details pane, at the bottom, select **Add a backup product to this policy**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="99b04-183">如果您未看到此連結，這是因為您只有一個與您的帳戶相關聯的產品。</span><span class="sxs-lookup"><span data-stu-id="99b04-183">If you don't see this link, it's because you only have one product associated with your account.</span></span>
4. <span data-ttu-id="99b04-184">在 [ **新增產品** ] 窗格中，使用下拉式清單選擇要新增至原則的產品，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-184">In the **Add a product** pane, use the drop-down to choose a product to add to the policy, then select **Add**.</span></span>
5. <span data-ttu-id="99b04-185">選取 [ **儲存** ] 以關閉 [詳細資料] 窗格。</span><span class="sxs-lookup"><span data-stu-id="99b04-185">Select **Save** to close the details pane.</span></span>

### <a name="remove-a-backup-product"></a><span data-ttu-id="99b04-186">移除備份產品</span><span class="sxs-lookup"><span data-stu-id="99b04-186">Remove a backup product</span></span>

1. <span data-ttu-id="99b04-187">在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="99b04-187">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="99b04-188">選取您要編輯的原則。</span><span class="sxs-lookup"><span data-stu-id="99b04-188">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="99b04-189">在 [詳細資料] 窗格的底部，選取 [ **移除產品**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-189">In the details pane, at the bottom, select **Remove a product**.</span></span>
4. <span data-ttu-id="99b04-190">在 [ **從原則移除產品** ] 窗格中，選取您要移除之原則的方塊，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-190">In the **Remove a product from the policy** pane, select the box for the policy that you want to remove, then select **Save**.</span></span>
5. <span data-ttu-id="99b04-191">關閉 [詳細資料] 窗格。</span><span class="sxs-lookup"><span data-stu-id="99b04-191">Close the details pane.</span></span>

## <a name="change-the-assigning-apps-and-services"></a><span data-ttu-id="99b04-192">變更指派應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="99b04-192">Change the assigning apps and services</span></span>

<span data-ttu-id="99b04-193">每個產品都有相關聯的應用程式和服務集合。</span><span class="sxs-lookup"><span data-stu-id="99b04-193">Each product has a collection of apps and services associated with it.</span></span>
<span data-ttu-id="99b04-194">針對您的自動宣告原則中的每一種產品，您可以指定當使用者自動指派該產品的授權時所要包含的應用程式和服務。</span><span class="sxs-lookup"><span data-stu-id="99b04-194">For each product in your auto-claim policy, you can specify which apps and services to include when a user is automatically assigned a license to that product.</span></span>

1. <span data-ttu-id="99b04-195">在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="99b04-195">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="99b04-196">選取您要編輯的原則。</span><span class="sxs-lookup"><span data-stu-id="99b04-196">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="99b04-197">在詳細資料窗格的 [ **應用程式和服務**] 底下，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-197">In the details pane, under **Apps and services**, select **Edit**.</span></span>
4. <span data-ttu-id="99b04-198">在 [ **應用程式和服務** ] 窗格的 [ **產品** ] 下拉式清單中，選取單一產品，或選取 [ **所有產品**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-198">In the **Apps and services** pane, from the **Product** drop-down, select a single product, or select **All products**.</span></span>
5. <span data-ttu-id="99b04-199">針對您想要讓使用者擁有或沒有存取權的應用程式和服務，選取或取消選取方塊。</span><span class="sxs-lookup"><span data-stu-id="99b04-199">Check or clear the boxes for apps and services that you want users to have or not have access to.</span></span>
6. <span data-ttu-id="99b04-200">完成後，請選取 [ **儲存**]，然後關閉 [詳細資料] 窗格。</span><span class="sxs-lookup"><span data-stu-id="99b04-200">When you're finished, select **Save**, then close the details pane.</span></span>

## <a name="change-the-assigning-order-for-backup-products"></a><span data-ttu-id="99b04-201">變更備份產品的指派順序</span><span class="sxs-lookup"><span data-stu-id="99b04-201">Change the assigning order for backup products</span></span>

<span data-ttu-id="99b04-202">如果您有指派給原則的備份產品，您可以變更使用者登入 app 時，用來指派授權的順序。</span><span class="sxs-lookup"><span data-stu-id="99b04-202">If you have backup products assigned to the policy, you can change the order in which they're used to assign licenses when users sign in to the app.</span></span>

1. <span data-ttu-id="99b04-203">在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="99b04-203">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="99b04-204">選取您要編輯的原則。</span><span class="sxs-lookup"><span data-stu-id="99b04-204">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="99b04-205">在 [詳細資料] 窗格的 [ **產品授權** ] 區段中，選取您要移動之產品旁的方塊，然後選取 [ **上移** ] 或 [ **下移**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-205">In the details pane, in the **Product licenses** section, select the box next to the product that you want to move, then select **Move up** or **Move down**.</span></span>
4. <span data-ttu-id="99b04-206">針對每個要重新排序的產品重複步驟3。</span><span class="sxs-lookup"><span data-stu-id="99b04-206">Repeat step 3 for each product that you want to reorder.</span></span>
5. <span data-ttu-id="99b04-207">當您完成重新排序產品時，請選取 [ **儲存** ] 以關閉 [詳細資料] 窗格。</span><span class="sxs-lookup"><span data-stu-id="99b04-207">When you're finished reordering the products, select **Save** to close the details pane.</span></span>

## <a name="view-an-auto-claim-policy-report"></a><span data-ttu-id="99b04-208">查看自動宣告原則報告</span><span class="sxs-lookup"><span data-stu-id="99b04-208">View an auto-claim policy report</span></span>

1. <span data-ttu-id="99b04-209">在系統管理中心中，移至 [ **帳單** \> **授權** ] 頁面，然後選取 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自動宣告原則</a> ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="99b04-209">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="99b04-210">選取 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="99b04-210">Select **View report**.</span></span> <span data-ttu-id="99b04-211">[ **自動宣告原則報告** ] 頁面會列出過去90天內從每個原則指派的所有授權。</span><span class="sxs-lookup"><span data-stu-id="99b04-211">The **Auto-claim policy report** page lists all licenses assigned from each policy in the last 90 days.</span></span> <span data-ttu-id="99b04-212">根據預設，此頁面會顯示過去的90天。</span><span class="sxs-lookup"><span data-stu-id="99b04-212">By default, the page shows the past 90 days.</span></span>
3. <span data-ttu-id="99b04-213">若要變更所顯示的時段，請選取 [ **過去30天** ] 下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="99b04-213">To change the time period shown, select the **Past 30 days** drop-down list.</span></span> <span data-ttu-id="99b04-214">您可以查看過去1、7、30和90天的報告。</span><span class="sxs-lookup"><span data-stu-id="99b04-214">You can view reports for the past 1, 7, 30, and 90 days.</span></span>

## <a name="next-steps"></a><span data-ttu-id="99b04-215">後續步驟</span><span class="sxs-lookup"><span data-stu-id="99b04-215">Next steps</span></span>

<span data-ttu-id="99b04-216">您可以定期回到 [ **自動宣告原則** ] 索引標籤，以查看您建立之原則下已宣告授權的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="99b04-216">You can periodically return to the **Auto-claim policy** tab to see a list of users who have claimed licenses under the policies you created.</span></span>

## <a name="related-content"></a><span data-ttu-id="99b04-217">相關內容</span><span class="sxs-lookup"><span data-stu-id="99b04-217">Related content</span></span>

<span data-ttu-id="99b04-218">[將授權指派給使用者](../../admin/manage/assign-licenses-to-users.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="99b04-218">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="99b04-219">[購買或移除訂閱授權](buy-licenses.md) (篇) </span><span class="sxs-lookup"><span data-stu-id="99b04-219">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>\
<span data-ttu-id="99b04-220">瞭解 (文章) [的訂閱與授權](subscriptions-and-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="99b04-220">[Understand subscriptions and licenses](subscriptions-and-licenses.md) (article)</span></span>