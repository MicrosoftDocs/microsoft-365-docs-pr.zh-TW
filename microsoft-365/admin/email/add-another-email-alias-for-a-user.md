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
ms.openlocfilehash: 4003dcfca29a722ccdf9b86cca5aa1141fbdb367
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892802"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="5baf4-103">為使用者新增其他電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="5baf4-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="5baf4-104">本文適用于具有商務用訂閱的 Microsoft 365 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="5baf4-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="5baf4-105">這不適用於家庭使用者。</span><span class="sxs-lookup"><span data-stu-id="5baf4-105">It's not for home users.</span></span>
  
<span data-ttu-id="5baf4-106">Microsoft 365 中的主要電子郵件地址通常是使用者在建立帳戶時所指派的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5baf4-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="5baf4-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span><span class="sxs-lookup"><span data-stu-id="5baf4-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="5baf4-108">他們也可以有一個以上的電子郵件地址與其 Microsoft 365 for business 帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="5baf4-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="5baf4-109">These additional addresses are called aliases.</span><span class="sxs-lookup"><span data-stu-id="5baf4-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="5baf4-110">例如，假設 Jenna 具有電子郵件地址 jenna@contosoco.com，但她也想要在 jen@contosoco.com 接收電子郵件，因為有些人會以該名稱來參照她。</span><span class="sxs-lookup"><span data-stu-id="5baf4-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="5baf4-111">您可以為她建立別名，這樣兩個電子郵件地址就會移至 Jenna 的 [收件匣]。</span><span class="sxs-lookup"><span data-stu-id="5baf4-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="5baf4-112">一個使用者最多可建立 400 個別名。</span><span class="sxs-lookup"><span data-stu-id="5baf4-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="5baf4-113">不需要額外費用或授權。</span><span class="sxs-lookup"><span data-stu-id="5baf4-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="5baf4-114">若要讓多位人員管理傳送到單一電子郵件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的電子郵件，請建立共用信箱。</span><span class="sxs-lookup"><span data-stu-id="5baf4-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="5baf4-115">若要深入瞭解，請參閱 [建立共用信箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="5baf4-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="5baf4-116">為使用者新增電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="5baf4-116">Add email aliases to a user</span></span>
<span data-ttu-id="5baf4-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="5baf4-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="5baf4-118">您必須具有系統 [管理員許可權](../add-users/about-admin-roles.md) ，才可執行此動作。</span><span class="sxs-lookup"><span data-stu-id="5baf4-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="5baf4-119">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="5baf4-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="5baf4-120">在 [作用中 **使用者** ] 頁面上，選取 [使用者 > **管理電子郵件別名**。</span><span class="sxs-lookup"><span data-stu-id="5baf4-120">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="5baf4-121">如果使用者未獲指派授權，您就不會看到此選項。</span><span class="sxs-lookup"><span data-stu-id="5baf4-121">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="5baf4-122">選取 [ **+ 新增別名** ]，然後輸入使用者的新別名。</span><span class="sxs-lookup"><span data-stu-id="5baf4-122">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="5baf4-123">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="5baf4-123">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="5baf4-124">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="5baf4-124">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="5baf4-125">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="5baf4-125">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="5baf4-126">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="5baf4-126">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="5baf4-127">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5baf4-127">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="5baf4-128">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="5baf4-128">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="5baf4-129">若要將另一個功能變數名稱新增至清單，請參閱 [add a domain To Microsoft 365](../setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="5baf4-129">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="5baf4-130">完成後，請選擇 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="5baf4-130">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="5baf4-131">請等候24小時，讓新的別名填入整個 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5baf4-131">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="5baf4-132">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="5baf4-132">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="5baf4-133">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="5baf4-133">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="5baf4-134">**當使用者回復時，[ *發件* 人] 位址將取決於其 Outlook 用戶端。網頁型 Outlook 會使用接收電子郵件的別名， (我們會將其稱為「乒乓球」原則) 。Outlook 桌面會使用其主要的電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="5baf4-134">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="5baf4-135">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="5baf4-135">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="5baf4-136">當送達 eliza 使用 Outlook 桌面回復郵件時，她的主要電子郵件地址會顯示為 Eliza@NodPublishers.com，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="5baf4-136">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="5baf4-137">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="5baf4-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="5baf4-138">在 [作用中 **使用者** ] 頁面上，選取您要編輯之人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="5baf4-138">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="5baf4-139">在 [使用者 **名稱/電子郵件別名**] 旁，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="5baf4-139">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="5baf4-140">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="5baf4-140">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="5baf4-141">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="5baf4-141">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="5baf4-142">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="5baf4-142">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="5baf4-143">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="5baf4-143">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="5baf4-144">在 [ **別名**] 底下的文字方塊中，輸入新電子郵件別名的第一個部分。</span><span class="sxs-lookup"><span data-stu-id="5baf4-144">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="5baf4-145">如果您已將自己的網域新增至 Microsoft 365，您可以使用下拉式清單選擇新電子郵件別名的網域。</span><span class="sxs-lookup"><span data-stu-id="5baf4-145">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="5baf4-146">然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="5baf4-146">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5baf4-147">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5baf4-147">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="5baf4-148">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="5baf4-148">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="5baf4-149">若要將另一個功能變數名稱新增至清單，請參閱 [add a domain To Microsoft 365](../setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="5baf4-149">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="5baf4-150">完成後，選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="5baf4-150">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="5baf4-151">請等候24小時，讓新的別名填入整個 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5baf4-151">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="5baf4-152">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="5baf4-152">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="5baf4-153">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="5baf4-153">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="5baf4-154">**當使用者回復時，[ *發件* 人] 位址將取決於其 Outlook 用戶端。網頁型 Outlook 會使用接收電子郵件的別名， (我們會將其稱為「乒乓球」原則) 。Outlook 桌面會使用其主要的電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="5baf4-154">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="5baf4-155">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="5baf4-155">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="5baf4-156">當送達 eliza 使用 Outlook 桌面回復郵件時，她的主要電子郵件地址會顯示為 Eliza@NodPublishers.com，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="5baf4-156">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5baf4-157">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="5baf4-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="5baf4-158">在 [作用中 **使用者** ] 頁面上，選取您要編輯之人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="5baf4-158">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="5baf4-159">在 [使用者 **名稱/電子郵件別名**] 旁，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="5baf4-159">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="5baf4-160">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="5baf4-160">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="5baf4-161">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="5baf4-161">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="5baf4-162">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="5baf4-162">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="5baf4-163">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="5baf4-163">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="5baf4-164">在 [ **別名**] 底下的文字方塊中，輸入新電子郵件別名的第一個部分。</span><span class="sxs-lookup"><span data-stu-id="5baf4-164">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="5baf4-165">如果您已將自己的網域新增至 Microsoft 365，您可以使用下拉式清單選擇新電子郵件別名的網域。</span><span class="sxs-lookup"><span data-stu-id="5baf4-165">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="5baf4-166">然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="5baf4-166">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5baf4-167">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5baf4-167">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="5baf4-168">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="5baf4-168">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="5baf4-169">若要將另一個功能變數名稱新增至清單，請參閱 [add a domain To Microsoft 365](../setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="5baf4-169">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="5baf4-170">完成後，選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="5baf4-170">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="5baf4-171">請等候24小時，讓新的別名填入整個 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5baf4-171">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="5baf4-172">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="5baf4-172">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="5baf4-173">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="5baf4-173">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="5baf4-174">**當使用者回復時，[ *發件* 人] 位址將取決於其 Outlook 用戶端。網頁型 Outlook 會使用接收電子郵件的別名， (我們會將其稱為「乒乓球」原則) 。Outlook 桌面會使用其主要的電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="5baf4-174">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="5baf4-175">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="5baf4-175">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="5baf4-176">當送達 eliza 使用 Outlook 桌面回復郵件時，她的主要電子郵件地址會顯示為 Eliza@NodPublishers.com，而不是 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="5baf4-176">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="5baf4-177">您取得的是「找不到符合參數名稱 EmailAddresses 的參數嗎」？</span><span class="sxs-lookup"><span data-stu-id="5baf4-177">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="5baf4-178">如果您收到錯誤訊息「**找不到符合參數名稱的參數 EmailAddresses**' 這表示要花很長的時間來完成設定您的租使用者，或自訂網域（如果您最近新增的話）。</span><span class="sxs-lookup"><span data-stu-id="5baf4-178">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="5baf4-179">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="5baf4-179">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="5baf4-180">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="5baf4-180">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="5baf4-181">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="5baf4-181">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="5baf4-182">您是從 GoDaddy 或其他協力廠商購買訂閱嗎？</span><span class="sxs-lookup"><span data-stu-id="5baf4-182">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="5baf4-183">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5baf4-183">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>

## <a name="sending-email-from-the-proxy-address-easily"></a><span data-ttu-id="5baf4-184">輕鬆從 proxy 位址傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="5baf4-184">Sending email from the proxy address easily</span></span>

<span data-ttu-id="5baf4-185">新功能在2021年4月推出，可讓使用者在使用 Outlook 網頁版時，輕鬆地從別名傳送。</span><span class="sxs-lookup"><span data-stu-id="5baf4-185">A new feature is rolling out in April 2021 that allows users to send from their aliases easily when using Outlook on the web.</span></span> <span data-ttu-id="5baf4-186">當該功能推出租使用者系統管理員使用 Cmdlet 的租用時 `Set-OrganizationConfig -SendFromAliasEnabled $true` ，租用中的使用者就可以存取核取方塊清單，其中每個專案都會對應至其 Outlook 設定中的別名。</span><span class="sxs-lookup"><span data-stu-id="5baf4-186">When the feature rolls out to a tenancy where the tenant admin uses the `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, users within the tenancy will get access to a list of checkboxes where each entry corresponds to an alias in their Outlook settings.</span></span> <span data-ttu-id="5baf4-187">選取別名會將其顯示在撰寫表單的 [寄件者] 下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="5baf4-187">Selecting an alias will make it appear in the From dropdown in the Compose form.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="5baf4-188">相關文章</span><span class="sxs-lookup"><span data-stu-id="5baf4-188">Related articles</span></span>

[<span data-ttu-id="5baf4-189">從不同的地址傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="5baf4-189">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="5baf4-190">變更使用名稱和電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="5baf4-190">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
