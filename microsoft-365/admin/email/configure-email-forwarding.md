---
title: 在 Office 365 中設定電子郵件轉發
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: 使用 Office365 設定電子郵件轉寄至一或多個電子郵件帳戶。
ms.openlocfilehash: 963256aedb52ae0adf31790a74fbdb77ad2bb27e
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142524"
---
# <a name="configure-email-forwarding-in-office-365"></a><span data-ttu-id="86938-103">在 Office 365 中設定電子郵件轉發</span><span class="sxs-lookup"><span data-stu-id="86938-103">Configure email forwarding in Office 365</span></span>
  
<span data-ttu-id="86938-104">做為 Office 365 組織的系統管理員，您可能需要設定使用者信箱的電子郵件轉寄功能的公司需求。</span><span class="sxs-lookup"><span data-stu-id="86938-104">As the admin of an Office 365 organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="86938-105">電子郵件轉寄功能可讓您將傳送至使用者信箱的電子郵件轉寄至組織內部或外部的其他使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="86938-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="86938-106">設定電子郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="86938-106">Configure email forwarding</span></span>

 <span data-ttu-id="86938-107">在您設定電子郵件轉發之前，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="86938-107">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="86938-108">一旦您設定了電子郵件轉寄功能，就只會轉寄傳送給*寄件者*信箱的**新**電子郵件。</span><span class="sxs-lookup"><span data-stu-id="86938-108">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span> 
    
- <span data-ttu-id="86938-109">電子郵件轉寄要求 [*寄件者*] 帳戶具有授權。</span><span class="sxs-lookup"><span data-stu-id="86938-109">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="86938-110">如果您正在設定電子郵件轉寄功能，因為使用者已離開您的組織，另一個選項是[將其信箱轉換成共用信箱](convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="86938-110">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="86938-111">這樣可以讓數個人員存取它。</span><span class="sxs-lookup"><span data-stu-id="86938-111">This way several people can access it.</span></span> <span data-ttu-id="86938-112">不過，共用信箱不能超過50GB。</span><span class="sxs-lookup"><span data-stu-id="86938-112">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="86938-113">您必須是 Office 365 中的 Exchange 系統管理員或全域系統管理員，才能執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="86938-113">You must be an Exchange administrator or Global administrator in Office 365 to do these steps.</span></span> <span data-ttu-id="86938-114">如需詳細資訊，請參閱[關於系統管理員角色](../add-users/about-admin-roles.md)的主題。</span><span class="sxs-lookup"><span data-stu-id="86938-114">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="86938-115">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="86938-115">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="86938-116">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="86938-116">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="86938-117">選取您要轉寄其電子郵件的使用者名稱，以開啟 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="86938-117">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="86938-118">在 [**郵件**] 索引標籤上，選取 [**管理電子郵件轉發**]。</span><span class="sxs-lookup"><span data-stu-id="86938-118">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="86938-119">在 [電子郵件轉寄] 頁面上，選取 [**轉寄所有傳送至此信箱的電子郵件**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="86938-119">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="86938-120">如果您未看到此選項，請確定已將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="86938-120">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="86938-121">選取 [儲存變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="86938-121">Select **Save changes**.</span></span>
    
    <span data-ttu-id="86938-122">*若要轉寄至多個電子郵件地址*，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。</span><span class="sxs-lookup"><span data-stu-id="86938-122">*To forward to multiple email addresses*, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="86938-123">若要深入瞭解，請參閱[使用規則來自動轉寄郵件](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="86938-123">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="86938-124">或者，在系統管理中心[建立通訊群組](../setup/create-distribution-lists.md)，[新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。</span><span class="sxs-lookup"><span data-stu-id="86938-124">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="86938-125">請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！</span><span class="sxs-lookup"><span data-stu-id="86938-125">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="86938-126">否則，電子郵件轉寄功能會停止。</span><span class="sxs-lookup"><span data-stu-id="86938-126">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="86938-127">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="86938-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="86938-128">選取您要轉寄其電子郵件的使用者名稱，以開啟 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="86938-128">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="86938-129">展開 [**郵件設定**]，然後在 [**電子郵件轉發**] 區段中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="86938-129">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="86938-130">在 [電子郵件轉寄] 頁面上，將 [切換至] 設定為 [**開啟**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="86938-130">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="86938-131">如果您未看到此選項，請確定已將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="86938-131">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="86938-132">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="86938-132">Select **Save**.</span></span>
    
    <span data-ttu-id="86938-133">**若要轉寄至多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。</span><span class="sxs-lookup"><span data-stu-id="86938-133">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="86938-134">若要深入瞭解，請參閱[使用規則來自動轉寄郵件](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="86938-134">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="86938-135">或者，在系統管理中心[建立通訊群組](../setup/create-distribution-lists.md)，[新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。</span><span class="sxs-lookup"><span data-stu-id="86938-135">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="86938-136">請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！</span><span class="sxs-lookup"><span data-stu-id="86938-136">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="86938-137">否則，電子郵件轉寄功能會停止。</span><span class="sxs-lookup"><span data-stu-id="86938-137">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="86938-138">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="86938-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="86938-139">選取您要轉寄其電子郵件的使用者名稱，以開啟 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="86938-139">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="86938-140">展開 [**郵件設定**]，然後在 [**電子郵件轉發**] 區段中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="86938-140">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="86938-141">在 [電子郵件轉寄] 頁面上，將 [切換至] 設定為 [**開啟**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="86938-141">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="86938-142">如果您未看到此選項，請確定已將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="86938-142">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="86938-143">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="86938-143">Select **Save**.</span></span>
    
    <span data-ttu-id="86938-144">**若要轉寄至多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。</span><span class="sxs-lookup"><span data-stu-id="86938-144">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="86938-145">若要深入瞭解，請參閱[使用規則來自動轉寄郵件](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="86938-145">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="86938-146">或者，在系統管理中心[建立通訊群組](../setup/create-distribution-lists.md)，[新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。</span><span class="sxs-lookup"><span data-stu-id="86938-146">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="86938-147">請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！</span><span class="sxs-lookup"><span data-stu-id="86938-147">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="86938-148">否則，電子郵件轉寄功能會停止。</span><span class="sxs-lookup"><span data-stu-id="86938-148">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
