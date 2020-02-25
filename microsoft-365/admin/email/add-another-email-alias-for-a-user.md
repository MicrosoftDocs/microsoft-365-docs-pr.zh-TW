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
description: '了解如何可以有一個以上的電子郵件地址，呼叫與 Office 365 商務版帳戶相關聯的電子郵件別名。 '
ms.openlocfilehash: 10f219f380d30a5ee8e9822e7a35ee533d165c33
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251713"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="ad5c6-103">為使用者新增另一個電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="ad5c6-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="ad5c6-104">本文適用於 Office 365 系統管理員擁有商務版訂閱。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-104">This article is for Office 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="ad5c6-105">它不是隸屬使用者。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-105">It's not for home users.</span></span>
  
<span data-ttu-id="ad5c6-106">Office 365 的主要電子郵件地址通常是建立其帳戶時，已指派給使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-106">A primary email address in Office 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="ad5c6-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span><span class="sxs-lookup"><span data-stu-id="ad5c6-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="ad5c6-108">They can also have more than one email address associated with their Office 365 for business account.</span><span class="sxs-lookup"><span data-stu-id="ad5c6-108">They can also have more than one email address associated with their Office 365 for business account.</span></span> <span data-ttu-id="ad5c6-109">These additional addresses are called aliases.</span><span class="sxs-lookup"><span data-stu-id="ad5c6-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="ad5c6-110">例如，假設 Jenna 具有電子郵件地址 jenna@contosoco.com，但她也想要接收電子郵件在 jen@contosoco.com，因為有些人參照她該名稱。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="ad5c6-111">您可以為她建立別名，如此這兩個電子郵件地址前往 Jenna 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="ad5c6-112">一個使用者最多可建立 400 個別名。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="ad5c6-113">不需要額外費用或授權。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="ad5c6-114">如果您想多位人員管理傳送到單一電子郵件地址，例如 info@NodPublishers.com 或 sales@NodPublishers.com，建立共用的信箱。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="ad5c6-115">若要深入了解，請參閱[建立共用信箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="ad5c6-116">為使用者新增電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="ad5c6-116">Add email aliases to a user</span></span>
<span data-ttu-id="ad5c6-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="ad5c6-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="ad5c6-118">您必須具有[系統管理員權限](../add-users/about-admin-roles.md)若要這麼做。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="ad5c6-119">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="ad5c6-120">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ad5c6-121">在 [**作用中使用者**] 頁面上，選取使用者 >**管理電子郵件別名**。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-121">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="ad5c6-122">如果該人員沒有指派授權，您無法看到此選項。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-122">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="ad5c6-123">選取 [ **+ 新增別名**，並為使用者輸入新的別名。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-123">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="ad5c6-124">如果您收到錯誤訊息 「**參數找不到符合參數名稱 ' EmailAddresses**，「 這表示，花費的時間較長的時間完成設定您的租用戶或您的自訂網域，如果您最近新增一個。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-124">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="ad5c6-125">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-125">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="ad5c6-126">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-126">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="ad5c6-127">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-127">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="ad5c6-128">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-128">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="ad5c6-129">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-129">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="ad5c6-130">若要將另一個網域名稱新增至清單，請參閱[新增網域至 Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-130">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 
  
     
5. <span data-ttu-id="ad5c6-131">當您完成時，選擇 [**儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-131">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="ad5c6-132">請等候 24 小時，讓新別名填入整個 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-132">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="ad5c6-133">使用者現在有主要地址和一個別名。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-133">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="ad5c6-134">例如，所有傳送到送達 Eliza Hoffman 主要地址、 Eliza@NodPublishers.com，以及其別名，Sales@NodPublishers.com，郵件會移至送達 Eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-134">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="ad5c6-135">**當使用者回覆時，*從*地址將會是其主要電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="ad5c6-135">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="ad5c6-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="ad5c6-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="ad5c6-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="ad5c6-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="ad5c6-138">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="ad5c6-139">在 [**作用中使用者**] 頁面上，選取您想要編輯的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-139">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="ad5c6-140">接下來為**的使用者名稱 / 電子郵件別名**，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-140">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="ad5c6-141">如果您收到錯誤訊息 「**參數找不到符合參數名稱 ' EmailAddresses**，「 這表示，花費的時間較長的時間完成設定您的租用戶或您的自訂網域，如果您最近新增一個。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-141">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="ad5c6-142">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-142">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="ad5c6-143">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-143">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="ad5c6-144">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-144">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="ad5c6-145">在 [**別名**] 下的 [文字] 方塊中，輸入新的電子郵件別名的第一個部分。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-145">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="ad5c6-146">如果您已將自己的網域新增至 Office 365，您可以使用下拉式清單選擇新電子郵件別名的網域。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-146">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="ad5c6-147">然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-147">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ad5c6-148">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-148">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="ad5c6-149">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-149">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="ad5c6-150">若要將另一個網域名稱新增至清單，請參閱[新增網域至 Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-150">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 

5. <span data-ttu-id="ad5c6-151">當您完成時，選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-151">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="ad5c6-152">請等候 24 小時，讓新別名填入整個 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-152">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="ad5c6-153">使用者現在有主要地址和一個別名。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-153">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="ad5c6-154">例如，所有傳送到送達 Eliza Hoffman 主要地址、 Eliza@NodPublishers.com，以及其別名，Sales@NodPublishers.com，郵件會移至送達 Eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-154">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="ad5c6-155">**當使用者回覆時，*從*地址將會是其主要電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="ad5c6-155">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="ad5c6-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="ad5c6-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="ad5c6-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="ad5c6-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ad5c6-158">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="ad5c6-159">在 [**作用中使用者**] 頁面上，選取您想要編輯的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-159">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="ad5c6-160">接下來為**的使用者名稱 / 電子郵件別名**，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-160">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="ad5c6-161">如果您收到錯誤訊息 「**參數找不到符合參數名稱 ' EmailAddresses**，「 這表示，花費的時間較長的時間完成設定您的租用戶或您的自訂網域，如果您最近新增一個。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-161">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="ad5c6-162">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-162">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="ad5c6-163">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-163">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="ad5c6-164">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-164">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="ad5c6-165">在 [**別名**] 下的 [文字] 方塊中，輸入新的電子郵件別名的第一個部分。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-165">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="ad5c6-166">如果您已將自己的網域新增至 Office 365，您可以使用下拉式清單選擇新電子郵件別名的網域。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-166">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="ad5c6-167">然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-167">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ad5c6-168">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-168">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="ad5c6-169">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-169">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="ad5c6-170">若要將另一個網域名稱新增至清單，請參閱[新增網域至 Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-170">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 

5. <span data-ttu-id="ad5c6-171">當您完成時，選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-171">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="ad5c6-172">請等候 24 小時，讓新別名填入整個 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-172">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="ad5c6-173">使用者現在有主要地址和一個別名。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-173">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="ad5c6-174">例如，所有傳送到送達 Eliza Hoffman 主要地址、 Eliza@NodPublishers.com，以及其別名，Sales@NodPublishers.com，郵件會移至送達 Eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-174">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="ad5c6-175">**當使用者回覆時，*從*地址將會是其主要電子郵件別名。**</span><span class="sxs-lookup"><span data-stu-id="ad5c6-175">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="ad5c6-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="ad5c6-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="ad5c6-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="ad5c6-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="ad5c6-178">您收到 「 找不到符合參數名稱 EmailAddresses 」？</span><span class="sxs-lookup"><span data-stu-id="ad5c6-178">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="ad5c6-179">如果您收到 「**找不到符合參數名稱 EmailAddresses**」 錯誤訊息表示，花費的時間較長的時間完成設定您的租用戶或您的自訂網域，如果您最近新增一個。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-179">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="ad5c6-180">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-180">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="ad5c6-181">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-181">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="ad5c6-182">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-182">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="ad5c6-183">您是從 GoDaddy 或其他協力廠商購買訂閱嗎？</span><span class="sxs-lookup"><span data-stu-id="ad5c6-183">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="ad5c6-184">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ad5c6-184">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="ad5c6-185">相關文章</span><span class="sxs-lookup"><span data-stu-id="ad5c6-185">Related articles</span></span>

[<span data-ttu-id="ad5c6-186">從不同的地址傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="ad5c6-186">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="ad5c6-187">變更使用名稱和電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="ad5c6-187">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

