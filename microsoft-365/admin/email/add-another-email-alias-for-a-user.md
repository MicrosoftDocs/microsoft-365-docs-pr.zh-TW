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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '瞭解您可以如何有一個以上的電子郵件地址，稱為「電子郵件別名」，與您的 Microsoft 365 for business 帳戶相關聯。 '
ms.openlocfilehash: 603b2f42d603ae5172c66b6f78bc55f8d44c81f5
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140509"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="b2f8a-103">為使用者新增其他電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="b2f8a-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b2f8a-104">系統管理中心變更。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-104">The admin center is changing.</span></span> <span data-ttu-id="b2f8a-105">[！附注] 如果您的經驗不符合這裡所述的詳細資料，請參閱[關於新的 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="b2f8a-106">本文適用于具有商務用訂閱的 Microsoft 365 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="b2f8a-107">這不適用於家庭使用者。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-107">It's not for home users.</span></span>
  
<span data-ttu-id="b2f8a-108">Microsoft 365 中的主要電子郵件地址通常是使用者在建立帳戶時所指派的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="b2f8a-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span><span class="sxs-lookup"><span data-stu-id="b2f8a-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="b2f8a-110">他們也可以有一個以上的電子郵件地址與其 Microsoft 365 for business 帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="b2f8a-111">These additional addresses are called aliases.</span><span class="sxs-lookup"><span data-stu-id="b2f8a-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="b2f8a-112">例如，假設 Jenna 具有電子郵件地址 jenna@contosoco.com，但她也想要在 jen@contosoco.com 接收電子郵件，因為有些人會以該名稱來參照她。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="b2f8a-113">您可以為她建立別名，這樣兩個電子郵件地址就會移至 Jenna 的 [收件匣]。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="b2f8a-114">一個使用者最多可建立 400 個別名。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="b2f8a-115">不需要額外費用或授權。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="b2f8a-116">若要讓多位人員管理傳送到單一電子郵件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的電子郵件，請建立共用信箱。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="b2f8a-117">若要深入瞭解，請參閱[建立共用信箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="b2f8a-118">為使用者新增電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="b2f8a-118">Add email aliases to a user</span></span>
<span data-ttu-id="b2f8a-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="b2f8a-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="b2f8a-120">您必須具有系統[管理員許可權](../add-users/about-admin-roles.md)，才可執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="b2f8a-121">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="b2f8a-122">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="b2f8a-123">在 [作用中**使用者**] 頁面上，選取 [使用者 >**管理電子郵件別名**。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-123">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="b2f8a-124">如果使用者未獲指派授權，您就不會看到此選項。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-124">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="b2f8a-125">選取 [ **+ 新增別名**]，然後輸入使用者的新別名。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-125">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="b2f8a-126">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-126">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="b2f8a-127">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-127">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="b2f8a-128">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-128">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="b2f8a-129">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-129">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="b2f8a-130">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-130">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="b2f8a-131">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-131">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="b2f8a-132">若要將另一個功能變數名稱新增至清單，請參閱[add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-132">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="b2f8a-133">完成後，請選擇 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-133">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="b2f8a-134">請等候 24 小時，讓新別名填入整個 Office 365。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-134">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="b2f8a-135">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-135">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="b2f8a-136">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-136">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="b2f8a-137">**當使用者回復時，[*發件*人] 位址會是她的主要電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="b2f8a-137">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="b2f8a-138">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="b2f8a-138">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="b2f8a-139">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="b2f8a-139">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="b2f8a-140">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="b2f8a-141">在 [作用中**使用者**] 頁面上，選取您要編輯之人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-141">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="b2f8a-142">在 [使用者**名稱/電子郵件別名**] 旁，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-142">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="b2f8a-143">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-143">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="b2f8a-144">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-144">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="b2f8a-145">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-145">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="b2f8a-146">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-146">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="b2f8a-147">在 [**別名**] 底下的文字方塊中，輸入新電子郵件別名的第一個部分。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-147">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="b2f8a-148">如果您已將自己的網域新增至 Office 365，您可以使用下拉式清單選擇新電子郵件別名的網域。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-148">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="b2f8a-149">然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-149">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b2f8a-150">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-150">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="b2f8a-151">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-151">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="b2f8a-152">若要將另一個功能變數名稱新增至清單，請參閱[add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-152">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="b2f8a-153">當您完成時，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-153">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="b2f8a-154">請等候 24 小時，讓新別名填入整個 Office 365。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-154">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="b2f8a-155">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-155">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="b2f8a-156">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-156">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="b2f8a-157">**當使用者回復時，[*發件*人] 位址會是她的主要電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="b2f8a-157">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="b2f8a-158">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="b2f8a-158">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="b2f8a-159">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="b2f8a-159">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b2f8a-160">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="b2f8a-161">在 [作用中**使用者**] 頁面上，選取您要編輯之人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-161">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="b2f8a-162">在 [使用者**名稱/電子郵件別名**] 旁，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-162">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="b2f8a-163">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-163">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="b2f8a-164">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-164">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="b2f8a-165">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-165">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="b2f8a-166">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-166">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="b2f8a-167">在 [**別名**] 底下的文字方塊中，輸入新電子郵件別名的第一個部分。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-167">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="b2f8a-168">如果您已將自己的網域新增至 Office 365，您可以使用下拉式清單選擇新電子郵件別名的網域。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-168">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="b2f8a-169">然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-169">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b2f8a-170">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-170">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="b2f8a-171">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-171">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="b2f8a-172">若要將另一個功能變數名稱新增至清單，請參閱[add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-172">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="b2f8a-173">當您完成時，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-173">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="b2f8a-174">請等候 24 小時，讓新別名填入整個 Office 365。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-174">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="b2f8a-175">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-175">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="b2f8a-176">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-176">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="b2f8a-177">**當使用者回復時，[*發件*人] 位址會是她的主要電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="b2f8a-177">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="b2f8a-178">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="b2f8a-178">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="b2f8a-179">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="b2f8a-179">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="b2f8a-180">您取得的是「找不到符合參數名稱 EmailAddresses 的參數嗎」？</span><span class="sxs-lookup"><span data-stu-id="b2f8a-180">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="b2f8a-181">如果您收到錯誤訊息「**找不到符合參數名稱的參數 EmailAddresses**' 這表示要花很長的時間來完成設定您的租使用者，或自訂網域（如果您最近新增的話）。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-181">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="b2f8a-182">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-182">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="b2f8a-183">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-183">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="b2f8a-184">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-184">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="b2f8a-185">您是從 GoDaddy 或其他協力廠商購買訂閱嗎？</span><span class="sxs-lookup"><span data-stu-id="b2f8a-185">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="b2f8a-186">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b2f8a-186">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="b2f8a-187">相關文章</span><span class="sxs-lookup"><span data-stu-id="b2f8a-187">Related articles</span></span>

[<span data-ttu-id="b2f8a-188">從不同的地址傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="b2f8a-188">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="b2f8a-189">變更使用名稱和電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="b2f8a-189">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

