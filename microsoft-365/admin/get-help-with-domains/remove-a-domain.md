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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: 瞭解如何從 Microsoft 365 移除舊的網域，以及將使用者和群組移至另一個網域。
ms.openlocfilehash: 21b2b17e5cab022f67c71c0d3858f8a03b45899b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628431"
---
# <a name="remove-a-domain"></a><span data-ttu-id="5428e-103">移除網域</span><span class="sxs-lookup"><span data-stu-id="5428e-103">Remove a domain</span></span>

<span data-ttu-id="5428e-104">投稿人：[![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span><span class="sxs-lookup"><span data-stu-id="5428e-104">Contributors: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span></span>
  
 <span data-ttu-id="5428e-105">**[檢查網域的常見問題集](../setup/domains-faq.md)** ：供您在找不到所需功能時參考。</span><span class="sxs-lookup"><span data-stu-id="5428e-105">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5428e-106">您移除的是您的網域，因為您想要將它新增至不同的 Microsoft 365 訂閱計畫嗎？</span><span class="sxs-lookup"><span data-stu-id="5428e-106">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="5428e-107">還是您只想取消訂閱？</span><span class="sxs-lookup"><span data-stu-id="5428e-107">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="5428e-108">您可以[變更您的方案或訂閱](../../commerce/subscriptions/switch-to-a-different-plan.md)或[取消您的訂閱](../../commerce/subscriptions/cancel-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="5428e-108">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="5428e-109">步驟1：將使用者移至另一個網域</span><span class="sxs-lookup"><span data-stu-id="5428e-109">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="5428e-110">移動使用者</span><span class="sxs-lookup"><span data-stu-id="5428e-110">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="5428e-111">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="5428e-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="5428e-112">移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="5428e-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="5428e-113">選取 [**使用者** >作用中**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="5428e-114">選取您要移動之所有使用者之名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="5428e-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="5428e-115">在頁面頂端選取 [**更多選項**] （**...**），然後選擇 [**變更網域**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="5428e-116">在 [**變更網域**] 窗格中，選取另一個網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="5428e-p102">如果您所處的網域也是您要移除的網域，您也必須為自己執行這個程序。為您的帳戶編輯網域時，您必須先登出，然後使用您選擇的新網域重新登入，才能繼續執行。</span><span class="sxs-lookup"><span data-stu-id="5428e-p102">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5428e-119">移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="5428e-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="5428e-120">選取 [**使用者** >作用中**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="5428e-121">選取您要移動之所有使用者之名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="5428e-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="5428e-122">在頁面頂端 **，選擇 [** > **編輯網域**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="5428e-123">在 [**編輯網域**] 窗格中，選取另一個網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="5428e-p103">如果您所處的網域也是您要移除的網域，您也必須為自己執行這個程序。為您的帳戶編輯網域時，您必須先登出，然後使用您選擇的新網域重新登入，才能繼續執行。</span><span class="sxs-lookup"><span data-stu-id="5428e-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5428e-126">移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="5428e-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="5428e-127">選取 [**使用者** >作用中**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="5428e-128">選取您要移動之所有使用者之名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="5428e-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="5428e-129">在頁面頂端 **，選擇 [** > **編輯網域**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="5428e-130">在 [**編輯網域**] 窗格中，選取另一個網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="5428e-p104">如果您所處的網域也是您要移除的網域，您也必須為自己執行這個程序。為您的帳戶編輯網域時，您必須先登出，然後使用您選擇的新網域重新登入，才能繼續執行。</span><span class="sxs-lookup"><span data-stu-id="5428e-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="5428e-133">自行移動</span><span class="sxs-lookup"><span data-stu-id="5428e-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="5428e-134">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="5428e-134">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="5428e-135">移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="5428e-135">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="5428e-136">移至 [**使用者** \>作用中**使用者**]，然後從清單中選取您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="5428e-136">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="5428e-137">在 [**帳戶**] 索引標籤上，選取 [**管理使用者名稱**]，然後選擇不同的網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-137">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="5428e-138">在頂端，選取您的帳戶名稱，然後選取 **[登出]。**</span><span class="sxs-lookup"><span data-stu-id="5428e-138">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="5428e-139">使用新的網域登入，並使用相同的密碼登入。</span><span class="sxs-lookup"><span data-stu-id="5428e-139">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="5428e-140">您也可以使用 PowerShell 將使用者移至另一個網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-140">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="5428e-141">如需詳細資訊，請參閱 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="5428e-141">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="5428e-142">若要設定預設網域，請使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="5428e-142">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5428e-143">移至 [**使用者** \>作用中**使用者**]，然後在清單中選取您的名稱。</span><span class="sxs-lookup"><span data-stu-id="5428e-143">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="5428e-144">在 [使用者**名稱/電子郵件**] 區段中，選取 [**編輯**]，然後選擇不同的網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-144">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="5428e-145">選取 [**設為主** > **儲存** > **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-145">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="5428e-146">在頂端，選取您的帳戶名稱，然後選取 **[登出]。**</span><span class="sxs-lookup"><span data-stu-id="5428e-146">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="5428e-147">使用新的網域登入，並使用相同的密碼登入。</span><span class="sxs-lookup"><span data-stu-id="5428e-147">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="5428e-148">您也可以使用 PowerShell 將使用者移至另一個網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-148">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="5428e-149">如需詳細資訊，請參閱 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="5428e-149">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="5428e-150">若要設定預設網域，請使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="5428e-150">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5428e-151">移至 [**使用者** \>作用中**使用者**]，然後在清單中選取您的名稱。</span><span class="sxs-lookup"><span data-stu-id="5428e-151">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="5428e-152">在 [使用者**名稱/電子郵件**] 區段中，選取 [**編輯**]，然後選擇不同的網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-152">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="5428e-153">選取 [**設為主** > **儲存** > **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-153">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="5428e-154">在頂端，選取您的帳戶名稱，然後選取 **[登出]。**</span><span class="sxs-lookup"><span data-stu-id="5428e-154">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="5428e-155">使用新的網域登入，並使用相同的密碼登入。</span><span class="sxs-lookup"><span data-stu-id="5428e-155">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="5428e-156">您也可以使用 PowerShell 將使用者移至另一個網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-156">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="5428e-157">如需詳細資訊，請參閱 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="5428e-157">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="5428e-158">若要設定預設網域，請使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="5428e-158">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="5428e-159">步驟2：將群組移至另一個網域</span><span class="sxs-lookup"><span data-stu-id="5428e-159">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5428e-160">在系統管理中心中，移至 [**群組** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5428e-160">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="5428e-161">選取組名，然後在 [**電子郵件地址，主要** **] 索引**標籤底下，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-161">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="5428e-162">使用下拉式清單選擇另一個網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-162">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="5428e-163">選取 [儲存]\*\*\*\*，再選取 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5428e-163">Select **Save**, then **Close**.</span></span> <span data-ttu-id="5428e-164">針對與您要移除之網域關聯的任何群組或通訊群組清單，重複這個程序。</span><span class="sxs-lookup"><span data-stu-id="5428e-164">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5428e-165">在系統<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，移至 [**群組** > **群組**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5428e-165">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="5428e-166">選取組名，然後選取 [**名稱**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-166">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="5428e-167">使用下拉式清單選擇另一個網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-167">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="5428e-168">選取 [儲存]\*\*\*\*，再選取 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5428e-168">Select **Save**, then **Close**.</span></span> <span data-ttu-id="5428e-169">針對與您要移除之網域關聯的任何群組或通訊群組清單，重複這個程序。</span><span class="sxs-lookup"><span data-stu-id="5428e-169">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5428e-170">在系統<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，移至 [**群組** > **群組**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5428e-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="5428e-171">選取組名，然後選取 [**名稱**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-171">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="5428e-172">使用下拉式清單選擇另一個網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-172">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="5428e-173">選取 [儲存]\*\*\*\*，再選取 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5428e-173">Select **Save**, then **Close**.</span></span> <span data-ttu-id="5428e-174">針對與您要移除之網域關聯的任何群組或通訊群組清單，重複這個程序。</span><span class="sxs-lookup"><span data-stu-id="5428e-174">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="5428e-175">步驟3：移除舊的網域</span><span class="sxs-lookup"><span data-stu-id="5428e-175">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5428e-176">在系統管理中心中，移至 **[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[網域]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="5428e-176">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5428e-177">在系統管理中心中，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5428e-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5428e-178">在系統管理中心中，移至 [**安裝** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">網域</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5428e-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="5428e-179">在 [**網域**] 頁面上，選取您要移除的網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-179">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="5428e-180">在右窗格中，選取 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-180">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="5428e-181">遵循任何其他提示，然後選取 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="5428e-181">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="5428e-182">移除網域需要多久的時間？</span><span class="sxs-lookup"><span data-stu-id="5428e-182">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="5428e-183">如果不是在許多地方（如安全性群組、通訊群組清單、使用者和 Microsoft 365 群組）上加以參考，則 Microsoft 365 可能只需要5分鐘的時間來移除網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-183">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="5428e-184">如果有許多參照都使用此網域，就會花費數小時 (一天) 的時間才能將網域移除。</span><span class="sxs-lookup"><span data-stu-id="5428e-184">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="5428e-p112">如果您有數百名或數千名使用者，請使用 PowerShell 來查詢所有使用者，然後將他們移到另一個網域。否則，UI 中很可能會遺失一些使用者，當您隨後想移除此網域時，將無法執行且不知道原因為何。如需詳細資訊，請參閱 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) (英文)。若要設定預設網域，請使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) (英文)。</span><span class="sxs-lookup"><span data-stu-id="5428e-p112">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="5428e-189">仍需要協助嗎？</span><span class="sxs-lookup"><span data-stu-id="5428e-189">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="5428e-190">您無法移除帳戶中的 [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) 網域。</span><span class="sxs-lookup"><span data-stu-id="5428e-190">You can't remove the [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) domain from your account.</span></span>
  
<span data-ttu-id="5428e-p113">仍無法運作嗎？您的網域可能需要手動移除。[打電話給我們](../contact-support-for-business-products.md)，我們會協助您處理。</span><span class="sxs-lookup"><span data-stu-id="5428e-p113">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="5428e-194">相關文章</span><span class="sxs-lookup"><span data-stu-id="5428e-194">Related articles</span></span>

[<span data-ttu-id="5428e-195">網域常見問題集</span><span class="sxs-lookup"><span data-stu-id="5428e-195">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="5428e-196">取得 Office 365 網域的說明</span><span class="sxs-lookup"><span data-stu-id="5428e-196">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="5428e-197">切換至不同的 Microsoft 365 for business 方案</span><span class="sxs-lookup"><span data-stu-id="5428e-197">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="5428e-198">取消訂閱</span><span class="sxs-lookup"><span data-stu-id="5428e-198">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
