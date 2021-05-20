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
description: '瞭解您可以如何具有一個以上的電子郵件地址，稱為與您的商務用 Microsoft 365 相關的電子郵件別名。 '
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572102"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="16c2e-103">為使用者新增其他電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="16c2e-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="16c2e-104">本文適用于具有商務訂閱的 Microsoft 365 管理員。</span><span class="sxs-lookup"><span data-stu-id="16c2e-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="16c2e-105">這不適用於家庭使用者。</span><span class="sxs-lookup"><span data-stu-id="16c2e-105">It's not for home users.</span></span>
  
<span data-ttu-id="16c2e-106">在 Microsoft 365 中，主要的電子郵件地址通常是使用者在建立帳戶時所指派的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="16c2e-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="16c2e-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span><span class="sxs-lookup"><span data-stu-id="16c2e-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="16c2e-108">他們也可以有一個以上的電子郵件地址與其 Microsoft 365 的商務帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="16c2e-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="16c2e-109">These additional addresses are called aliases.</span><span class="sxs-lookup"><span data-stu-id="16c2e-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="16c2e-110">例如，假設 Jenna 具有電子郵件地址 jenna@contosoco.com，但她也想要在 jen@contosoco.com 接收電子郵件，因為有些人會以該名稱來參照她。</span><span class="sxs-lookup"><span data-stu-id="16c2e-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="16c2e-111">您可以為她建立別名，這樣兩個電子郵件地址就會移至 Jenna 的 [收件匣]。</span><span class="sxs-lookup"><span data-stu-id="16c2e-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
  
<span data-ttu-id="16c2e-p104">一個使用者最多可建立 400 個別名。不需要額外費用或授權。</span><span class="sxs-lookup"><span data-stu-id="16c2e-p104">You can create up to 400 aliases for a user. No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="16c2e-114">若要讓多位人員管理傳送到單一電子郵件地址（如 info@NodPublishers.com 或 sales@NodPublishers.com）的電子郵件，請建立共用信箱。</span><span class="sxs-lookup"><span data-stu-id="16c2e-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="16c2e-115">若要深入瞭解，請參閱 [建立共用信箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="16c2e-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="16c2e-116">為使用者新增電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="16c2e-116">Add email aliases to a user</span></span>

<span data-ttu-id="16c2e-117">您必須具有系統 [管理員許可權](../add-users/about-admin-roles.md) ，才可執行此動作。</span><span class="sxs-lookup"><span data-stu-id="16c2e-117">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

1. <span data-ttu-id="16c2e-118">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="16c2e-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="16c2e-119">在 [作用中 **使用者** ] 頁面上，選取 [使用者 > **管理使用者名稱和電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="16c2e-119">On the **Active Users** page, select the user > **Manage username and email**.</span></span> <span data-ttu-id="16c2e-120">如果使用者未獲指派授權，您就不會看到此選項。</span><span class="sxs-lookup"><span data-stu-id="16c2e-120">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="16c2e-121">選取 [ **+ 新增別名** ]，然後輸入使用者的新別名。</span><span class="sxs-lookup"><span data-stu-id="16c2e-121">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="16c2e-122">如果您收到錯誤訊息「**找不到符合參數名稱的參數 ' EmailAddresses**，這表示要花很長的時間來完成設定您的租使用者或您的自訂網域（如果您最近新增一個）。</span><span class="sxs-lookup"><span data-stu-id="16c2e-122">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="16c2e-123">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="16c2e-123">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="16c2e-124">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="16c2e-124">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="16c2e-125">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="16c2e-125">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="16c2e-126">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="16c2e-126">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="16c2e-127">電子郵件別名必須以來自下拉式清單的網域做為結尾。</span><span class="sxs-lookup"><span data-stu-id="16c2e-127">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="16c2e-128">若要將另一個功能變數名稱新增至清單，請參閱[add a domain to Microsoft 365](../setup/add-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="16c2e-128">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="16c2e-129">完成後，請選擇 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="16c2e-129">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="16c2e-130">請等候24小時，讓新的別名填滿整個 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="16c2e-130">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="16c2e-131">使用者現在會有主要位址和別名。</span><span class="sxs-lookup"><span data-stu-id="16c2e-131">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="16c2e-132">例如，所有傳送至送達 eliza Hoffman 主要位址的郵件，Eliza@NodPublishers.com，而她的別名 Sales@NodPublishers.com 會移至送達 eliza 的收件匣。</span><span class="sxs-lookup"><span data-stu-id="16c2e-132">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="16c2e-133">**當使用者回復時，[*發件\* 人] 位址將取決於她的 Outlook 用戶端。網頁上的 Outlook 會使用接收電子郵件的別名 (我們會將其稱為「乒乓球) 」。Outlook 桌面會使用她的主要電子郵件別名。*\*</span><span class="sxs-lookup"><span data-stu-id="16c2e-133">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="16c2e-134">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span><span class="sxs-lookup"><span data-stu-id="16c2e-134">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="16c2e-135">當送達 eliza 使用 Outlook 桌面回復郵件時，她的主要電子郵件地址會顯示為 Eliza@NodPublishers.com，而非 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="16c2e-135">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="16c2e-136">您取得的是「找不到符合參數名稱 EmailAddresses 的參數嗎」？</span><span class="sxs-lookup"><span data-stu-id="16c2e-136">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>

<span data-ttu-id="16c2e-137">如果您收到錯誤訊息「**找不到符合參數名稱的參數 EmailAddresses**' 這表示要花很長的時間來完成設定您的租使用者，或自訂網域（如果您最近新增的話）。</span><span class="sxs-lookup"><span data-stu-id="16c2e-137">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="16c2e-138">設定程序最多可能需要 4 個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="16c2e-138">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="16c2e-139">請稍候，讓設定程序完成，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="16c2e-139">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="16c2e-140">如果問題仍然存在，請連絡支援人員，他們會為您執行完整的同步處理。</span><span class="sxs-lookup"><span data-stu-id="16c2e-140">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="16c2e-141">您是從 GoDaddy 或其他協力廠商購買訂閱嗎？</span><span class="sxs-lookup"><span data-stu-id="16c2e-141">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="16c2e-142">如果您是從 GoDaddy 或其他協力廠商購買訂閱，您必須移至 GoDaddy/協力廠商管理主控台，才能將新別名設為主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="16c2e-142">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>

## <a name="sending-email-from-the-proxy-address-easily"></a><span data-ttu-id="16c2e-143">輕鬆從 proxy 位址傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="16c2e-143">Sending email from the proxy address easily</span></span>

<span data-ttu-id="16c2e-144">新功能在2021年4月推出，可讓使用者在網頁上使用 Outlook 時，輕鬆地從別名傳送。</span><span class="sxs-lookup"><span data-stu-id="16c2e-144">A new feature is rolling out in April 2021 that allows users to send from their aliases easily when using Outlook on the web.</span></span> <span data-ttu-id="16c2e-145">當該功能推出租使用者系統管理員使用 Cmdlet 的租用時 `Set-OrganizationConfig -SendFromAliasEnabled $true` ，租用中的使用者就可以存取核取方塊清單，其中每個專案都會對應至其 Outlook 設定中的別名。</span><span class="sxs-lookup"><span data-stu-id="16c2e-145">When the feature rolls out to a tenancy where the tenant admin uses the `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, users within the tenancy will get access to a list of checkboxes where each entry corresponds to an alias in their Outlook settings.</span></span> <span data-ttu-id="16c2e-146">選取別名會將其顯示在撰寫表單的 [寄件者] 下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="16c2e-146">Selecting an alias will make it appear in the From dropdown in the Compose form.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="16c2e-147">相關內容</span><span class="sxs-lookup"><span data-stu-id="16c2e-147">Related content</span></span>

<span data-ttu-id="16c2e-148">[從不同的位址傳送電子郵件](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (文章) </span><span class="sxs-lookup"><span data-stu-id="16c2e-148">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>

<span data-ttu-id="16c2e-149">[變更使用者名稱和電子郵件地址](../add-users/change-a-user-name-and-email-address.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="16c2e-149">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>

<span data-ttu-id="16c2e-150">[在 Microsoft 365 中設定電子郵件轉寄](configure-email-forwarding.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="16c2e-150">[Configure email forwarding in Microsoft 365](configure-email-forwarding.md) (article)</span></span>
