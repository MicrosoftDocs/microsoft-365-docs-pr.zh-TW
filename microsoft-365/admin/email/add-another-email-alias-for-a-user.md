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
ms.openlocfilehash: efd0dbf5ae072c803b52d94dd41f16db9bb0413a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048804"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="6458f-103">為使用者新增其他電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="6458f-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="6458f-104">本文適用于具有商務用訂閱的 Microsoft 365 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="6458f-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="6458f-105">這不適用於家庭使用者。</span><span class="sxs-lookup"><span data-stu-id="6458f-105">It's not for home users.</span></span>
  
<span data-ttu-id="6458f-106">Microsoft 365 中的主要電子郵件地址通常是使用者在建立帳戶時所指派的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6458f-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="6458f-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span><span class="sxs-lookup"><span data-stu-id="6458f-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="6458f-108">他們也可以有一個以上的電子郵件地址與其 Microsoft 365 for business 帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="6458f-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="6458f-109">These additional addresses are called aliases.</span><span class="sxs-lookup"><span data-stu-id="6458f-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="6458f-110">例如，假設 Jenna 具有電子郵件地址 jenna@contosoco.com，但她也想要在 jen@contosoco.com 接收電子郵件，因為有些人會以該名稱來參照她。</span><span class="sxs-lookup"><span data-stu-id="6458f-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="6458f-111">您可以為她建立別名，這樣兩個電子郵件地址就會移至 Jenna 的 [收件匣]。</span><span class="sxs-lookup"><span data-stu-id="6458f-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="6458f-112">一個使用者最多可建立 400 個別名。</span><span class="sxs-lookup"><span data-stu-id="6458f-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="6458f-113">不需要額外費用或授權。</span><span class="sxs-lookup"><span data-stu-id="6458f-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="6458f-114">若要讓多位人員管理傳送到單一電子郵件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的電子郵件，請建立共用信箱。</span><span class="sxs-lookup"><span data-stu-id="6458f-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="6458f-115">若要深入瞭解，請參閱[建立共用信箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="6458f-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="6458f-116">為使用者新增電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="6458f-116">Add email aliases to a user</span></span>
<span data-ttu-id="6458f-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="6458f-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="6458f-118">您必須具有系統[管理員許可權](../add-users/about-admin-roles.md)，才可執行此動作。</span><span class="sxs-lookup"><span data-stu-id="6458f-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="6458f-119">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="6458f-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="6458f-120">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="6458f-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6458f-121">在 [作用中**使用者**] 頁面上，選取 [使用者 >**管理電子郵件別名**。</span><span class="sxs-lookup"><span data-stu-id="6458f-121">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="6458f-122">如果使用者未獲指派授權，您就不會看到此選項。</span><span class="sxs-lookup"><span data-stu-id="6458f-122">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="6458f-123">選取 [ **+ 新增別名**]，然後輸入使用者的新別名。</span><span class="sxs-lookup"><span data-stu-id="6458f-123">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="6458f-124">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="6458f-124">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6458f-125">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="6458f-125">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6458f-126">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="6458f-126">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6458f-127">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="6458f-127">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="6458f-128">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6458f-128">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="6458f-129">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="6458f-129">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="6458f-130">若要將另一個功能變數名稱新增至清單，請參閱[add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。</span><span class="sxs-lookup"><span data-stu-id="6458f-130">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="6458f-131">完成後，請選擇 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="6458f-131">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="6458f-132">請等候 24 小時，讓新別名填入整個 Office 365。</span><span class="sxs-lookup"><span data-stu-id="6458f-132">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="6458f-133">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="6458f-133">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="6458f-134">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="6458f-134">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="6458f-135">**當使用者回復時，[*發件*人] 位址會是她的主要電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="6458f-135">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="6458f-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="6458f-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="6458f-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="6458f-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="6458f-138">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="6458f-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="6458f-139">在 [作用中**使用者**] 頁面上，選取您要編輯之人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="6458f-139">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="6458f-140">在 [使用者**名稱/電子郵件別名**] 旁，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="6458f-140">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="6458f-141">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="6458f-141">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6458f-142">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="6458f-142">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6458f-143">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="6458f-143">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6458f-144">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="6458f-144">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="6458f-145">在 [**別名**] 底下的文字方塊中，輸入新電子郵件別名的第一個部分。</span><span class="sxs-lookup"><span data-stu-id="6458f-145">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="6458f-146">如果您已將自己的網域新增至 Office 365，您可以使用下拉式清單選擇新電子郵件別名的網域。</span><span class="sxs-lookup"><span data-stu-id="6458f-146">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="6458f-147">然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="6458f-147">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6458f-148">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6458f-148">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="6458f-149">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="6458f-149">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="6458f-150">若要將另一個功能變數名稱新增至清單，請參閱[add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。</span><span class="sxs-lookup"><span data-stu-id="6458f-150">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="6458f-151">當您完成時，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6458f-151">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="6458f-152">請等候 24 小時，讓新別名填入整個 Office 365。</span><span class="sxs-lookup"><span data-stu-id="6458f-152">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="6458f-153">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="6458f-153">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="6458f-154">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="6458f-154">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="6458f-155">**當使用者回復時，[*發件*人] 位址會是她的主要電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="6458f-155">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="6458f-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="6458f-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="6458f-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="6458f-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6458f-158">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="6458f-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="6458f-159">在 [作用中**使用者**] 頁面上，選取您要編輯之人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="6458f-159">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="6458f-160">在 [使用者**名稱/電子郵件別名**] 旁，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="6458f-160">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="6458f-161">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="6458f-161">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6458f-162">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="6458f-162">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6458f-163">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="6458f-163">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6458f-164">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="6458f-164">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="6458f-165">在 [**別名**] 底下的文字方塊中，輸入新電子郵件別名的第一個部分。</span><span class="sxs-lookup"><span data-stu-id="6458f-165">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="6458f-166">如果您已將自己的網域新增至 Office 365，您可以使用下拉式清單選擇新電子郵件別名的網域。</span><span class="sxs-lookup"><span data-stu-id="6458f-166">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="6458f-167">然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="6458f-167">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6458f-168">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6458f-168">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="6458f-169">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="6458f-169">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="6458f-170">若要將另一個功能變數名稱新增至清單，請參閱[add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。</span><span class="sxs-lookup"><span data-stu-id="6458f-170">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="6458f-171">當您完成時，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6458f-171">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="6458f-172">請等候 24 小時，讓新別名填入整個 Office 365。</span><span class="sxs-lookup"><span data-stu-id="6458f-172">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="6458f-173">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="6458f-173">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="6458f-174">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="6458f-174">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="6458f-175">**當使用者回復時，[*發件*人] 位址會是她的主要電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="6458f-175">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="6458f-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="6458f-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="6458f-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="6458f-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="6458f-178">您取得的是「找不到符合參數名稱 EmailAddresses 的參數嗎」？</span><span class="sxs-lookup"><span data-stu-id="6458f-178">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="6458f-179">如果您收到錯誤訊息「**找不到符合參數名稱的參數 EmailAddresses**' 這表示要花很長的時間來完成設定您的租使用者，或自訂網域（如果您最近新增的話）。</span><span class="sxs-lookup"><span data-stu-id="6458f-179">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="6458f-180">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="6458f-180">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="6458f-181">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="6458f-181">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="6458f-182">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="6458f-182">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="6458f-183">您是從 GoDaddy 或其他協力廠商購買訂閱嗎？</span><span class="sxs-lookup"><span data-stu-id="6458f-183">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="6458f-184">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6458f-184">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="6458f-185">相關文章</span><span class="sxs-lookup"><span data-stu-id="6458f-185">Related articles</span></span>

[<span data-ttu-id="6458f-186">從不同的地址傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="6458f-186">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="6458f-187">變更使用名稱和電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="6458f-187">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

