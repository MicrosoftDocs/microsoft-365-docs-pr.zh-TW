---
title: 為使用者新增另一個電子郵件別名
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '瞭解您可以如何有一個以上的電子郵件地址，稱為「電子郵件別名」，與您的 Microsoft 365 for business 帳戶相關聯。 '
ms.openlocfilehash: 590782f7b22b1d26abef83f884d45da567f0425c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915947"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="3cf5d-103">為使用者新增其他電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="3cf5d-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3cf5d-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-104">The admin center is changing.</span></span> <span data-ttu-id="3cf5d-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="3cf5d-106">本文適用于具有商務用訂閱的 Microsoft 365 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="3cf5d-107">這不適用於家庭使用者。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-107">It's not for home users.</span></span>
  
<span data-ttu-id="3cf5d-108">Microsoft 365 中的主要電子郵件地址通常是使用者在建立帳戶時所指派的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="3cf5d-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span><span class="sxs-lookup"><span data-stu-id="3cf5d-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="3cf5d-110">他們也可以有一個以上的電子郵件地址與其 Microsoft 365 for business 帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="3cf5d-111">These additional addresses are called aliases.</span><span class="sxs-lookup"><span data-stu-id="3cf5d-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="3cf5d-112">例如，假設 Jenna 具有電子郵件地址 jenna@contosoco.com，但她也想要在 jen@contosoco.com 接收電子郵件，因為有些人會以該名稱來參照她。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="3cf5d-113">您可以為她建立別名，這樣兩個電子郵件地址就會移至 Jenna 的 [收件匣]。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="3cf5d-114">一個使用者最多可建立 400 個別名。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="3cf5d-115">不需要額外費用或授權。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="3cf5d-116">若要讓多位人員管理傳送到單一電子郵件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的電子郵件，請建立共用信箱。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="3cf5d-117">若要深入瞭解，請參閱 [建立共用信箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="3cf5d-118">為使用者新增電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="3cf5d-118">Add email aliases to a user</span></span>
<span data-ttu-id="3cf5d-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf5d-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="3cf5d-120">您必須具有系統 [管理員許可權](../add-users/about-admin-roles.md) ，才可執行此動作。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="3cf5d-121">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="3cf5d-122">在 [作用中 **使用者** ] 頁面上，選取 [使用者 > **管理電子郵件別名**。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="3cf5d-123">如果使用者未獲指派授權，您就不會看到此選項。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="3cf5d-124">選取 [ **+ 新增別名** ]，然後輸入使用者的新別名。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="3cf5d-125">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="3cf5d-126">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="3cf5d-127">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="3cf5d-128">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="3cf5d-129">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="3cf5d-130">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="3cf5d-131">若要將另一個功能變數名稱新增至清單，請參閱 [add a domain To Microsoft 365](../setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-131">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="3cf5d-132">完成後，請選擇 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="3cf5d-133">請等候24小時，讓新的別名填入整個 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-133">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="3cf5d-134">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="3cf5d-135">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="3cf5d-136">**當使用者回復時，[ *發件*  人] 位址會是她的主要電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="3cf5d-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="3cf5d-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="3cf5d-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="3cf5d-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="3cf5d-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="3cf5d-139">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="3cf5d-140">在 [作用中 **使用者** ] 頁面上，選取您要編輯之人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="3cf5d-141">在 [使用者 **名稱/電子郵件別名**] 旁，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="3cf5d-142">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="3cf5d-143">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="3cf5d-144">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="3cf5d-145">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="3cf5d-146">在 [ **別名**] 底下的文字方塊中，輸入新電子郵件別名的第一個部分。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="3cf5d-147">如果您已將自己的網域新增至 Microsoft 365，您可以使用下拉式清單選擇新電子郵件別名的網域。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-147">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="3cf5d-148">然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3cf5d-149">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="3cf5d-150">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="3cf5d-151">若要將另一個功能變數名稱新增至清單，請參閱 [add a domain To Microsoft 365](../setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-151">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="3cf5d-152">完成後，選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="3cf5d-153">請等候24小時，讓新的別名填入整個 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-153">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="3cf5d-154">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="3cf5d-155">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="3cf5d-156">**當使用者回復時，[ *發件*  人] 位址會是她的主要電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="3cf5d-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="3cf5d-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="3cf5d-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="3cf5d-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="3cf5d-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3cf5d-159">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="3cf5d-160">在 [作用中 **使用者** ] 頁面上，選取您要編輯之人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="3cf5d-161">在 [使用者 **名稱/電子郵件別名**] 旁，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="3cf5d-162">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="3cf5d-163">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="3cf5d-164">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="3cf5d-165">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="3cf5d-166">在 [ **別名**] 底下的文字方塊中，輸入新電子郵件別名的第一個部分。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="3cf5d-167">如果您已將自己的網域新增至 Microsoft 365，您可以使用下拉式清單選擇新電子郵件別名的網域。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-167">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="3cf5d-168">然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3cf5d-169">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="3cf5d-170">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="3cf5d-171">若要將另一個功能變數名稱新增至清單，請參閱 [add a domain To Microsoft 365](../setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-171">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="3cf5d-172">完成後，選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="3cf5d-173">請等候24小時，讓新的別名填入整個 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-173">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="3cf5d-174">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="3cf5d-175">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="3cf5d-176">**當使用者回復時，[ *發件*  人] 位址會是她的主要電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="3cf5d-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="3cf5d-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="3cf5d-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="3cf5d-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="3cf5d-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="3cf5d-179">您取得的是「找不到符合參數名稱 EmailAddresses 的參數嗎」？</span><span class="sxs-lookup"><span data-stu-id="3cf5d-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="3cf5d-180">如果您收到錯誤訊息「**找不到符合參數名稱的參數 EmailAddresses**' 這表示要花很長的時間來完成設定您的租使用者，或自訂網域（如果您最近新增的話）。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="3cf5d-181">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="3cf5d-182">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="3cf5d-183">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="3cf5d-184">您是從 GoDaddy 或其他協力廠商購買訂閱嗎？</span><span class="sxs-lookup"><span data-stu-id="3cf5d-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="3cf5d-185">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3cf5d-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="3cf5d-186">相關文章</span><span class="sxs-lookup"><span data-stu-id="3cf5d-186">Related articles</span></span>

[<span data-ttu-id="3cf5d-187">從不同的地址傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="3cf5d-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="3cf5d-188">變更使用名稱和電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="3cf5d-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
