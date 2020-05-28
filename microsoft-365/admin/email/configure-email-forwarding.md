---
title: 設定電子郵件轉寄
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: 使用 Office365 設定電子郵件轉寄至一或多個電子郵件帳戶。
ms.openlocfilehash: 72eca099f0c7e60efe8f616dfe23201cd46975cf
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400121"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="1e601-103">設定電子郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="1e601-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1e601-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="1e601-104">The admin center is changing.</span></span> <span data-ttu-id="1e601-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet) (英文)。</span><span class="sxs-lookup"><span data-stu-id="1e601-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="1e601-106">做為組織的系統管理員，您可能需要設定使用者信箱的電子郵件轉寄功能的公司需求。</span><span class="sxs-lookup"><span data-stu-id="1e601-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="1e601-107">電子郵件轉寄功能可讓您將傳送至使用者信箱的電子郵件轉寄至組織內部或外部的其他使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="1e601-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="1e601-108">設定電子郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="1e601-108">Configure email forwarding</span></span>

 <span data-ttu-id="1e601-109">在您設定電子郵件轉發之前，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="1e601-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="1e601-110">一旦您設定了電子郵件轉寄功能，只會 fowarded 傳送給*寄件者*信箱的**新**電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1e601-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="1e601-111">電子郵件轉寄要求 [*寄件者*] 帳戶具有授權。</span><span class="sxs-lookup"><span data-stu-id="1e601-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="1e601-112">如果您正在設定電子郵件轉寄功能，因為使用者已離開您的組織，另一個選項是[將其信箱轉換成共用信箱](convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="1e601-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="1e601-113">這樣可以讓數個人員存取它。</span><span class="sxs-lookup"><span data-stu-id="1e601-113">This way several people can access it.</span></span> <span data-ttu-id="1e601-114">不過，共用信箱不能超過50GB。</span><span class="sxs-lookup"><span data-stu-id="1e601-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="1e601-115">您必須是 Microsoft 365 中的 Exchange 系統管理員或全域系統管理員，才能執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="1e601-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="1e601-116">如需詳細資訊，請參閱[關於系統管理員角色](../add-users/about-admin-roles.md)的主題。</span><span class="sxs-lookup"><span data-stu-id="1e601-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="1e601-117">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="1e601-117">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="1e601-118">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="1e601-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="1e601-119">選取您要轉寄其電子郵件的使用者名稱，以開啟 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="1e601-119">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="1e601-120">在 [**郵件**] 索引標籤上，選取 [**管理電子郵件轉發**]。</span><span class="sxs-lookup"><span data-stu-id="1e601-120">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="1e601-121">在 [電子郵件轉寄] 頁面上，選取 [**轉寄所有傳送至此信箱的電子郵件**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="1e601-121">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="1e601-122">如果您未看到此選項，請確定已將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1e601-122">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="1e601-123">選取 [儲存變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e601-123">Select **Save changes**.</span></span>
    
    <span data-ttu-id="1e601-124">**若要轉寄至多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。</span><span class="sxs-lookup"><span data-stu-id="1e601-124">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="1e601-125">若要深入瞭解，請參閱[使用規則來自動轉寄郵件](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="1e601-125">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="1e601-126">或者，在系統管理中心[建立通訊群組](../setup/create-distribution-lists.md)，[新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。</span><span class="sxs-lookup"><span data-stu-id="1e601-126">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="1e601-127">請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！</span><span class="sxs-lookup"><span data-stu-id="1e601-127">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="1e601-128">否則，電子郵件轉寄功能會停止。</span><span class="sxs-lookup"><span data-stu-id="1e601-128">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="1e601-129">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="1e601-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="1e601-130">選取您要轉寄其電子郵件的使用者名稱，以開啟 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="1e601-130">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="1e601-131">展開 [**郵件設定**]，然後在 [**電子郵件轉發**] 區段中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="1e601-131">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="1e601-132">在 [電子郵件轉寄] 頁面上，將 [切換至] 設定為 [**開啟**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="1e601-132">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="1e601-133">如果您未看到此選項，請確定已將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1e601-133">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="1e601-134">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e601-134">Select **Save**.</span></span>
    
    <span data-ttu-id="1e601-135">**若要轉寄至多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。</span><span class="sxs-lookup"><span data-stu-id="1e601-135">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="1e601-136">若要深入瞭解，請參閱[使用規則來自動轉寄郵件](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="1e601-136">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="1e601-137">或者，在系統管理中心[建立通訊群組](../setup/create-distribution-lists.md)，[新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。</span><span class="sxs-lookup"><span data-stu-id="1e601-137">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="1e601-138">請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！</span><span class="sxs-lookup"><span data-stu-id="1e601-138">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="1e601-139">否則，電子郵件轉寄功能會停止。</span><span class="sxs-lookup"><span data-stu-id="1e601-139">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="1e601-140">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="1e601-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="1e601-141">選取您要轉寄其電子郵件的使用者名稱，以開啟 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="1e601-141">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="1e601-142">展開 [**郵件設定**]，然後在 [**電子郵件轉發**] 區段中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="1e601-142">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="1e601-143">在 [電子郵件轉寄] 頁面上，將 [切換至] 設定為 [**開啟**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="1e601-143">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="1e601-144">如果您未看到此選項，請確定已將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1e601-144">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="1e601-145">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e601-145">Select **Save**.</span></span>
    
    <span data-ttu-id="1e601-146">**若要轉寄至多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。</span><span class="sxs-lookup"><span data-stu-id="1e601-146">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="1e601-147">若要深入瞭解，請參閱[使用規則來自動轉寄郵件](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="1e601-147">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="1e601-148">或者，在系統管理中心[建立通訊群組](../setup/create-distribution-lists.md)，[新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。</span><span class="sxs-lookup"><span data-stu-id="1e601-148">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="1e601-149">請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！</span><span class="sxs-lookup"><span data-stu-id="1e601-149">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="1e601-150">否則，電子郵件轉寄功能會停止。</span><span class="sxs-lookup"><span data-stu-id="1e601-150">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
