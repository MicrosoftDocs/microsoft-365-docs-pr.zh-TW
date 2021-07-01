---
title: 設定電子郵件轉寄
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: 電子郵件轉寄功能可讓您將傳送至 Microsoft 365 使用者信箱的電子郵件轉寄至組織內部或外部的其他信箱。
ms.openlocfilehash: e0043fe75eefe224c63fd23f352d4bd3ddf2c326
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228048"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="08d84-103">設定 Microsoft 365 中的電子郵件轉寄功能</span><span class="sxs-lookup"><span data-stu-id="08d84-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="08d84-104">做為組織的系統管理員，您可能需要設定使用者信箱的電子郵件轉寄功能的公司需求。</span><span class="sxs-lookup"><span data-stu-id="08d84-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="08d84-105">電子郵件轉寄功能可讓您將傳送至使用者信箱的電子郵件轉寄至組織內部或外部的其他使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="08d84-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08d84-106">您可以使用輸出垃圾郵件篩選原則來控制自動轉寄給外部收件者。</span><span class="sxs-lookup"><span data-stu-id="08d84-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="08d84-107">如需詳細資訊，請參閱[在 Microsoft 365 中控制自動外部電子郵件轉接](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)。</span><span class="sxs-lookup"><span data-stu-id="08d84-107">For more information, see [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="08d84-108">設定電子郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="08d84-108">Configure email forwarding</span></span>

<span data-ttu-id="08d84-109">在您設定電子郵件轉發之前，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="08d84-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="08d84-110">允許自動轉寄的郵件傳送給遠端網域上的人員。</span><span class="sxs-lookup"><span data-stu-id="08d84-110">Allow automatically forwarded messages to be sent to people on the remote domain.</span></span> <span data-ttu-id="08d84-111">如需詳細資訊，請參閱 [管理遠端網域](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) 。</span><span class="sxs-lookup"><span data-stu-id="08d84-111">See [Manage remote domains](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) for details.</span></span>

- <span data-ttu-id="08d84-112">一旦您設定了電子郵件轉寄功能，就只會轉寄傳送給 *寄件者* 信箱的 **新** 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="08d84-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="08d84-113">電子郵件轉寄要求 [  *寄件者*  ] 帳戶具有授權。</span><span class="sxs-lookup"><span data-stu-id="08d84-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="08d84-114">如果您正在設定電子郵件轉寄功能，因為使用者已離開您的組織，另一個選項是 [將其信箱轉換成共用信箱](convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="08d84-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="08d84-115">這樣可以讓數個人員存取它。</span><span class="sxs-lookup"><span data-stu-id="08d84-115">This way several people can access it.</span></span> <span data-ttu-id="08d84-116">不過，共用信箱不能超過50GB。</span><span class="sxs-lookup"><span data-stu-id="08d84-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="08d84-117">您必須是 Microsoft 365 的 Exchange 管理員或全域系統管理員，才可執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="08d84-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="08d84-118">如需詳細資訊，請參閱 [關於系統管理員角色](../add-users/about-admin-roles.md)的主題。</span><span class="sxs-lookup"><span data-stu-id="08d84-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="08d84-119">在系統管理中心中，移至 [ **使用者** 作用中 \> **[使用者](https://go.microsoft.com/fwlink/p/?linkid=834822)** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="08d84-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="08d84-120">選取您要轉寄其電子郵件的使用者名稱，然後開啟 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="08d84-120">Select the name of the user whose email you want to forward, then open the properties page.</span></span>

3. <span data-ttu-id="08d84-121">在 [ **郵件** ] 索引標籤上，選取 [ **管理電子郵件轉發**]。</span><span class="sxs-lookup"><span data-stu-id="08d84-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="08d84-122">在 [電子郵件轉寄] 頁面上，選取 [ **轉寄所有傳送至此信箱的電子郵件**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="08d84-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="08d84-123">如果您未看到此選項，請確定已將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="08d84-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="08d84-124">選取 [儲存變更 **]**。</span><span class="sxs-lookup"><span data-stu-id="08d84-124">Select **Save changes**.</span></span>

    <span data-ttu-id="08d84-125">**若要轉寄至多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。</span><span class="sxs-lookup"><span data-stu-id="08d84-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> 
    
    1.  <span data-ttu-id="08d84-126">開啟 **outlook**  >  **Home**  >   **規則**> 選取 [**管理規則 & 警示**]</span><span class="sxs-lookup"><span data-stu-id="08d84-126">Open **outlook** > **Home** >  **Rules** > Select **Manage Rules & Alerts**</span></span>
    1. <span data-ttu-id="08d84-127">選取 [**新增規則**]  >  **選取 [在我收到的郵件上** 的套用規則] 清單中，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="08d84-127">Select **New Rule** > **Select Apply rule on message I receive** located near bottom of list, then click **Next**.</span></span>
    1. <span data-ttu-id="08d84-128">當要求此規則會套用至您收到的每封郵件時，請按一下 **[是]** 。</span><span class="sxs-lookup"><span data-stu-id="08d84-128">Click **Yes** when asked This rule will be applied to every message you receive.</span></span> 
    1. <span data-ttu-id="08d84-129">在下一個清單中，選取 [動作重新 **導向至人員或公用群組** ]， **停止處理其他規則**</span><span class="sxs-lookup"><span data-stu-id="08d84-129">On the next list select the actions **redirect it to people or public group** and **stop processing more rules**</span></span>
    1. <span data-ttu-id="08d84-130">在視窗的下方，按一下帶底線片語的 [ **人員] 或 [公用群組** ]。</span><span class="sxs-lookup"><span data-stu-id="08d84-130">Click the underlined phrase **people or public group** in the bottom part of window.</span></span>
    1. <span data-ttu-id="08d84-131">在 [至] 欄位中，輸入要轉寄郵件的 **電子郵件地址** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="08d84-131">Type the **email address** to forward mail to in the To field, then click **OK**.</span></span>
    1. <span data-ttu-id="08d84-132">選取 **完成**</span><span class="sxs-lookup"><span data-stu-id="08d84-132">Select **Finish**</span></span>
    

     <span data-ttu-id="08d84-133">或者，在系統管理中心 [建立通訊群組](../setup/create-distribution-lists.md)， [新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。</span><span class="sxs-lookup"><span data-stu-id="08d84-133">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="08d84-134">請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！</span><span class="sxs-lookup"><span data-stu-id="08d84-134">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="08d84-135">否則，電子郵件轉寄功能會停止。</span><span class="sxs-lookup"><span data-stu-id="08d84-135">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="08d84-136">在系統管理中心中，移至 [ **使用者** 作用中 \> **[使用者](https://go.microsoft.com/fwlink/p/?linkid=847686)** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="08d84-136">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="08d84-137">選取您要轉寄其電子郵件的使用者名稱，以開啟 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="08d84-137">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="08d84-138">展開 [ **郵件設定**]，然後在 [ **電子郵件轉發** ] 區段中，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="08d84-138">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="08d84-139">在 [電子郵件轉寄] 頁面上，將 [切換至] 設定為 [ **開啟**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="08d84-139">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="08d84-140">如果您未看到此選項，請確定已將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="08d84-140">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="08d84-141">選取 \*\*\*\*[儲存]。</span><span class="sxs-lookup"><span data-stu-id="08d84-141">Select **Save**.</span></span>

   <span data-ttu-id="08d84-142">**若要轉寄至多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。</span><span class="sxs-lookup"><span data-stu-id="08d84-142">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="08d84-143">若要深入瞭解，請參閱 [使用規則來自動轉寄郵件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="08d84-143">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="08d84-144">或者，在系統管理中心 [建立通訊群組](../setup/create-distribution-lists.md)， [新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。</span><span class="sxs-lookup"><span data-stu-id="08d84-144">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="08d84-145">請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！</span><span class="sxs-lookup"><span data-stu-id="08d84-145">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="08d84-146">否則，電子郵件轉寄功能會停止。</span><span class="sxs-lookup"><span data-stu-id="08d84-146">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="08d84-147">在系統管理中心中，移至 [ **使用者** 作用中 \> **[使用者](https://go.microsoft.com/fwlink/p/?linkid=850628)** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="08d84-147">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="08d84-148">選取您要轉寄其電子郵件的使用者名稱，以開啟 [屬性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="08d84-148">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="08d84-149">展開 [ **郵件設定**]，然後在 [ **電子郵件轉發** ] 區段中，選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="08d84-149">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="08d84-150">在 [電子郵件轉寄] 頁面上，將 [切換至] 設定為 [ **開啟**]，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="08d84-150">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="08d84-151">如果您未看到此選項，請確定已將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="08d84-151">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="08d84-152">選取 \*\*\*\*[儲存]。</span><span class="sxs-lookup"><span data-stu-id="08d84-152">Select **Save**.</span></span>

   <span data-ttu-id="08d84-153">**若要轉寄至多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉寄位址。</span><span class="sxs-lookup"><span data-stu-id="08d84-153">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="08d84-154">若要深入瞭解，請參閱 [使用規則來自動轉寄郵件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="08d84-154">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="08d84-155">或者，在系統管理中心 [建立通訊群組](../setup/create-distribution-lists.md)， [新增位址](add-user-or-contact-to-distribution-list.md)，然後使用本文中的指示，將轉寄設定為指向 DL。</span><span class="sxs-lookup"><span data-stu-id="08d84-155">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="08d84-156">請勿刪除要轉寄電子郵件的使用者帳戶，或是移除其授權！</span><span class="sxs-lookup"><span data-stu-id="08d84-156">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span> <span data-ttu-id="08d84-157">否則，電子郵件轉寄功能會停止。</span><span class="sxs-lookup"><span data-stu-id="08d84-157">If you do, email forwarding will stop.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="08d84-158">相關內容</span><span class="sxs-lookup"><span data-stu-id="08d84-158">Related content</span></span> 

<span data-ttu-id="08d84-159">[建立共用信箱](../email/create-a-shared-mailbox.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="08d84-159">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="08d84-160">[從不同的位址傳送電子郵件](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (文章) </span><span class="sxs-lookup"><span data-stu-id="08d84-160">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>\
<span data-ttu-id="08d84-161">[變更使用者名稱和電子郵件地址](../add-users/change-a-user-name-and-email-address.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="08d84-161">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>
