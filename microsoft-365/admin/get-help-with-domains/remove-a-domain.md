---
title: 移除網域
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: 瞭解如何從 Microsoft 365 移除舊的網域，以及將使用者和群組移至另一個網域。
ms.openlocfilehash: c5e629f0d683c6dc3e18b1278027ac3a88cc834b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399893"
---
# <a name="remove-a-domain"></a><span data-ttu-id="59b08-103">移除網域</span><span class="sxs-lookup"><span data-stu-id="59b08-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="59b08-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="59b08-104">The admin center is changing.</span></span> <span data-ttu-id="59b08-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="59b08-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="59b08-106">若您找不到所需內容，請**[查看網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="59b08-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="59b08-107">您移除的是您的網域，因為您想要將它新增至不同的 Microsoft 365 訂閱計畫嗎？</span><span class="sxs-lookup"><span data-stu-id="59b08-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="59b08-108">還是您只想取消訂閱？</span><span class="sxs-lookup"><span data-stu-id="59b08-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="59b08-109">您可以[變更您的方案或訂閱](../../commerce/subscriptions/switch-to-a-different-plan.md)或[取消您的訂閱](../../commerce/subscriptions/cancel-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="59b08-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="59b08-110">步驟1：將使用者移至另一個網域</span><span class="sxs-lookup"><span data-stu-id="59b08-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="59b08-111">移動使用者</span><span class="sxs-lookup"><span data-stu-id="59b08-111">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="59b08-112">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="59b08-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="59b08-113">移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="59b08-113">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="59b08-114">選取 [**使用者**作用 > 中**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-114">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="59b08-115">選取您要移動之所有使用者之名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="59b08-115">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="59b08-116">在頁面頂端選取 [**更多選項**] （**...**），然後選擇 [**變更網域**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-116">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="59b08-117">在 [**變更網域**] 窗格中，選取另一個網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-117">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="59b08-p103">如果您所處的網域也是您要移除的網域，您也必須為自己執行這個程序。為您的帳戶編輯網域時，您必須先登出，然後使用您選擇的新網域重新登入，才能繼續執行。</span><span class="sxs-lookup"><span data-stu-id="59b08-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="59b08-120">移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="59b08-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="59b08-121">選取 [**使用者**作用 > 中**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-121">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="59b08-122">選取您要移動之所有使用者之名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="59b08-122">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="59b08-123">在頁面頂端 **，選擇 [** > **編輯網域**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-123">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="59b08-124">在 [**編輯網域**] 窗格中，選取另一個網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-124">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="59b08-p104">如果您所處的網域也是您要移除的網域，您也必須為自己執行這個程序。為您的帳戶編輯網域時，您必須先登出，然後使用您選擇的新網域重新登入，才能繼續執行。</span><span class="sxs-lookup"><span data-stu-id="59b08-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="59b08-127">移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="59b08-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="59b08-128">選取 [**使用者**作用 > 中**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-128">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="59b08-129">選取您要移動之所有使用者之名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="59b08-129">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="59b08-130">在頁面頂端 **，選擇 [** > **編輯網域**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-130">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="59b08-131">在 [**編輯網域**] 窗格中，選取另一個網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-131">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="59b08-p105">如果您所處的網域也是您要移除的網域，您也必須為自己執行這個程序。為您的帳戶編輯網域時，您必須先登出，然後使用您選擇的新網域重新登入，才能繼續執行。</span><span class="sxs-lookup"><span data-stu-id="59b08-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="59b08-134">自行移動</span><span class="sxs-lookup"><span data-stu-id="59b08-134">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="59b08-135">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="59b08-135">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="59b08-136">移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="59b08-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="59b08-137">移至 [**使用者**作用 \> 中**使用者**]，然後從清單中選取您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="59b08-137">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="59b08-138">在 [**帳戶**] 索引標籤上，選取 [**管理使用者名稱**]，然後選擇不同的網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-138">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="59b08-139">在頂端，選取您的帳戶名稱，然後選取 **[登出]。**</span><span class="sxs-lookup"><span data-stu-id="59b08-139">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="59b08-140">使用新的網域登入，並使用相同的密碼登入。</span><span class="sxs-lookup"><span data-stu-id="59b08-140">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="59b08-141">您也可以使用 PowerShell 將使用者移至另一個網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-141">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="59b08-142">如需詳細資訊，請參閱 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="59b08-142">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="59b08-143">若要設定預設網域，請使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="59b08-143">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="59b08-144">移至 [**使用者**作用 \> 中**使用者**]，然後在清單中選取您的名稱。</span><span class="sxs-lookup"><span data-stu-id="59b08-144">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="59b08-145">在 [使用者**名稱/電子郵件**] 區段中，選取 [**編輯**]，然後選擇不同的網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-145">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="59b08-146">選取 [**設為主** > **儲存** > **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-146">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="59b08-147">在頂端，選取您的帳戶名稱，然後選取 **[登出]。**</span><span class="sxs-lookup"><span data-stu-id="59b08-147">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="59b08-148">使用新的網域登入，並使用相同的密碼登入。</span><span class="sxs-lookup"><span data-stu-id="59b08-148">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="59b08-149">您也可以使用 PowerShell 將使用者移至另一個網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-149">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="59b08-150">如需詳細資訊，請參閱 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="59b08-150">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="59b08-151">若要設定預設網域，請使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="59b08-151">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="59b08-152">移至 [**使用者**作用 \> 中**使用者**]，然後在清單中選取您的名稱。</span><span class="sxs-lookup"><span data-stu-id="59b08-152">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="59b08-153">在 [使用者**名稱/電子郵件**] 區段中，選取 [**編輯**]，然後選擇不同的網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-153">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="59b08-154">選取 [**設為主** > **儲存** > **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-154">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="59b08-155">在頂端，選取您的帳戶名稱，然後選取 **[登出]。**</span><span class="sxs-lookup"><span data-stu-id="59b08-155">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="59b08-156">使用新的網域登入，並使用相同的密碼登入。</span><span class="sxs-lookup"><span data-stu-id="59b08-156">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="59b08-157">您也可以使用 PowerShell 將使用者移至另一個網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-157">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="59b08-158">如需詳細資訊，請參閱 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="59b08-158">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="59b08-159">若要設定預設網域，請使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="59b08-159">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="59b08-160">步驟2：將群組移至另一個網域</span><span class="sxs-lookup"><span data-stu-id="59b08-160">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="59b08-161">在系統管理中心中，移至 [**群組** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="59b08-161">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="59b08-162">選取組名，然後在 [**電子郵件地址，主要** **] 索引**標籤底下，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-162">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="59b08-163">使用下拉式清單選擇另一個網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-163">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="59b08-164">選取 [儲存]\*\*\*\*，再選取 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59b08-164">Select **Save**, then **Close**.</span></span> <span data-ttu-id="59b08-165">針對與您要移除之網域關聯的任何群組或通訊群組清單，重複這個程序。</span><span class="sxs-lookup"><span data-stu-id="59b08-165">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="59b08-166">在系統<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [**群組** > **群組**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="59b08-166">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="59b08-167">選取組名，然後選取 [**名稱**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-167">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="59b08-168">使用下拉式清單選擇另一個網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-168">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="59b08-169">選取 [儲存]\*\*\*\*，再選取 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59b08-169">Select **Save**, then **Close**.</span></span> <span data-ttu-id="59b08-170">針對與您要移除之網域關聯的任何群組或通訊群組清單，重複這個程序。</span><span class="sxs-lookup"><span data-stu-id="59b08-170">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="59b08-171">在系統<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [**群組** > **群組**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="59b08-171">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="59b08-172">選取組名，然後選取 [**名稱**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-172">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="59b08-173">使用下拉式清單選擇另一個網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-173">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="59b08-174">選取 [儲存]\*\*\*\*，再選取 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59b08-174">Select **Save**, then **Close**.</span></span> <span data-ttu-id="59b08-175">針對與您要移除之網域關聯的任何群組或通訊群組清單，重複這個程序。</span><span class="sxs-lookup"><span data-stu-id="59b08-175">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="59b08-176">步驟3：移除舊的網域</span><span class="sxs-lookup"><span data-stu-id="59b08-176">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="59b08-177">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="59b08-177">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="59b08-178">在系統管理中心中，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="59b08-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="59b08-179">在系統管理中心中，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="59b08-179">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="59b08-180">在 [**網域**] 頁面上，選取您要移除的網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-180">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="59b08-181">在右窗格中，選取 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-181">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="59b08-182">遵循任何其他提示，然後選取 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="59b08-182">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="59b08-183">移除網域需要多久的時間？</span><span class="sxs-lookup"><span data-stu-id="59b08-183">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="59b08-184">如果不是在許多地方（如安全性群組、通訊群組清單、使用者和 Microsoft 365 群組）上加以參考，則 Microsoft 365 可能只需要5分鐘的時間來移除網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-184">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="59b08-185">如果有許多參照都使用此網域，就會花費數小時 (一天) 的時間才能將網域移除。</span><span class="sxs-lookup"><span data-stu-id="59b08-185">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="59b08-p113">如果您有數百名或數千名使用者，請使用 PowerShell 來查詢所有使用者，然後將他們移到另一個網域。否則，UI 中很可能會遺失一些使用者，當您隨後想移除此網域時，將無法執行且不知道原因為何。如需詳細資訊，請參閱 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) (英文)。若要設定預設網域，請使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="59b08-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="59b08-190">仍需要協助嗎？</span><span class="sxs-lookup"><span data-stu-id="59b08-190">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="59b08-191">您無法移除帳戶中的 [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) 網域。</span><span class="sxs-lookup"><span data-stu-id="59b08-191">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="59b08-p114">仍無法運作嗎？您的網域可能需要手動移除。[打電話給我們](../contact-support-for-business-products.md)，我們會協助您處理。</span><span class="sxs-lookup"><span data-stu-id="59b08-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="59b08-195">相關文章</span><span class="sxs-lookup"><span data-stu-id="59b08-195">Related articles</span></span>

[<span data-ttu-id="59b08-196">網域常見問題集</span><span class="sxs-lookup"><span data-stu-id="59b08-196">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="59b08-197">取得 Office 365 網域的說明</span><span class="sxs-lookup"><span data-stu-id="59b08-197">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="59b08-198">切換到其他的商務用 Microsoft 365 方案</span><span class="sxs-lookup"><span data-stu-id="59b08-198">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="59b08-199">取消訂閱</span><span class="sxs-lookup"><span data-stu-id="59b08-199">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
