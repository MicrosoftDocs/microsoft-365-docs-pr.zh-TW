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
description: 使用 Office365 設定電子郵件轉轉至一或多個電子郵件帳戶。
ms.openlocfilehash: 1168b549443de218339b1b8dcb32e57da175a2aa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926639"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="deeab-103">在 Microsoft 365 中設定電子郵件轉轉</span><span class="sxs-lookup"><span data-stu-id="deeab-103">Configure email forwarding in Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="deeab-104">系統管理中心正在變更。</span><span class="sxs-lookup"><span data-stu-id="deeab-104">The admin center is changing.</span></span> <span data-ttu-id="deeab-105">如果您的體驗不符合此處所示的詳細資料，請參閱 [關於新版 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true) (英文)。</span><span class="sxs-lookup"><span data-stu-id="deeab-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="deeab-106">做為組織的系統管理員，您可能會有公司要求為使用者信箱設定電子郵件轉轉。</span><span class="sxs-lookup"><span data-stu-id="deeab-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="deeab-107">電子郵件轉寄功能可讓您將寄至使用者信箱的電子郵件訊息轉寄到組織內外的其他使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="deeab-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="deeab-108">您可以使用外發垃圾郵件篩選策略來控制自動轉轉給外部收件者。</span><span class="sxs-lookup"><span data-stu-id="deeab-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="deeab-109">詳細資訊請參閱 Microsoft [365 中的控制自動外部電子郵件轉轉](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)。</span><span class="sxs-lookup"><span data-stu-id="deeab-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="deeab-110">設定電子郵件轉寄</span><span class="sxs-lookup"><span data-stu-id="deeab-110">Configure email forwarding</span></span>

<span data-ttu-id="deeab-111">設定電子郵件轉轉之前，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="deeab-111">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="deeab-112">設定電子郵件轉寄功能後，系統只會轉寄從信箱 *寄* 到該郵件的新電子郵件。</span><span class="sxs-lookup"><span data-stu-id="deeab-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="deeab-113">電子郵件轉轉會要求  *從帳戶*  擁有授權。</span><span class="sxs-lookup"><span data-stu-id="deeab-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="deeab-114">如果您因為使用者離開您的組織而設定電子郵件轉轉，另一個選項是 [將其信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="deeab-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="deeab-115">如此一來，多人就可以存取。</span><span class="sxs-lookup"><span data-stu-id="deeab-115">This way several people can access it.</span></span> <span data-ttu-id="deeab-116">不過，共用信箱不可超過 50 GB。</span><span class="sxs-lookup"><span data-stu-id="deeab-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="deeab-117">您必須是 Microsoft 365 中的 Exchange 系統管理員或全域系統管理員，才能執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="deeab-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="deeab-118">詳細資訊請參閱關於系統管理員 [角色的主題](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="deeab-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="deeab-119">在系統管理中心中，前往使用者使用 \> **[中使用者](https://go.microsoft.com/fwlink/p/?linkid=834822)** 頁面。</span><span class="sxs-lookup"><span data-stu-id="deeab-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="deeab-120">選取您想要轉看其電子郵件的使用者名稱，以開啟屬性頁面。</span><span class="sxs-lookup"><span data-stu-id="deeab-120">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="deeab-121">在郵件 **上，** 選取管理 **電子郵件轉寄**。</span><span class="sxs-lookup"><span data-stu-id="deeab-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="deeab-122">在電子郵件轉寄頁面上，選取轉寄所有寄到此信箱的電子郵件，輸入轉寄位址，然後選擇是否要保留轉寄電子郵件的一份副本。</span><span class="sxs-lookup"><span data-stu-id="deeab-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="deeab-123">如果您未看到此選項，請確定已指派授權給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="deeab-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="deeab-124">選取 **[儲存變更]**。</span><span class="sxs-lookup"><span data-stu-id="deeab-124">Select **Save changes**.</span></span>

    <span data-ttu-id="deeab-125">**若要轉轉多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉往位址。</span><span class="sxs-lookup"><span data-stu-id="deeab-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="deeab-126">若要深入瞭解，請參閱 [使用規則自動轉轉郵件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="deeab-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="deeab-127">或者，在系統管理中心建立[](../setup/create-distribution-lists.md)通訊群組，新增位址[](add-user-or-contact-to-distribution-list.md)至群組，然後設定轉場，使用本文中的指示指向 DL。</span><span class="sxs-lookup"><span data-stu-id="deeab-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="deeab-128">不要刪除您轉轉電子郵件之使用者的帳戶，或移除他們的授權！</span><span class="sxs-lookup"><span data-stu-id="deeab-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="deeab-129">如果您這麼做，電子郵件轉轉功能將會停止。</span><span class="sxs-lookup"><span data-stu-id="deeab-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="deeab-130">在系統管理中心中，前往使用者使用 \> **[中使用者](https://go.microsoft.com/fwlink/p/?linkid=847686)** 頁面。</span><span class="sxs-lookup"><span data-stu-id="deeab-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="deeab-131">選取您想要轉看其電子郵件的使用者名稱，以開啟屬性頁面。</span><span class="sxs-lookup"><span data-stu-id="deeab-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="deeab-132">展開 **郵件設定**，然後在電子郵件轉寄 **區** 段 **，選取編輯**。</span><span class="sxs-lookup"><span data-stu-id="deeab-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="deeab-133">在電子郵件轉轉頁面上，將開關設為開啟、輸入轉場地址，並選擇是否要保留已轉轉電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="deeab-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="deeab-134">如果您未看到此選項，請確定已指派授權給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="deeab-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="deeab-135">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="deeab-135">Select **Save**.</span></span>

   <span data-ttu-id="deeab-136">**若要轉轉多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉往位址。</span><span class="sxs-lookup"><span data-stu-id="deeab-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="deeab-137">若要深入瞭解，請參閱 [使用規則自動轉轉郵件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="deeab-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="deeab-138">或者，在系統管理中心建立[](../setup/create-distribution-lists.md)通訊群組，新增位址[](add-user-or-contact-to-distribution-list.md)至群組，然後設定轉場，使用本文中的指示指向 DL。</span><span class="sxs-lookup"><span data-stu-id="deeab-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="deeab-139">不要刪除您轉轉電子郵件之使用者的帳戶，或移除他們的授權！</span><span class="sxs-lookup"><span data-stu-id="deeab-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="deeab-140">如果您這麼做，電子郵件轉轉功能將會停止。</span><span class="sxs-lookup"><span data-stu-id="deeab-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="deeab-141">在系統管理中心中，前往使用者使用 \> **[中使用者](https://go.microsoft.com/fwlink/p/?linkid=850628)** 頁面。</span><span class="sxs-lookup"><span data-stu-id="deeab-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="deeab-142">選取您想要轉看其電子郵件的使用者名稱，以開啟屬性頁面。</span><span class="sxs-lookup"><span data-stu-id="deeab-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="deeab-143">展開 **郵件設定**，然後在電子郵件轉寄 **區** 段 **，選取編輯**。</span><span class="sxs-lookup"><span data-stu-id="deeab-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="deeab-144">在電子郵件轉轉頁面上，將開關設為開啟、輸入轉場地址，並選擇是否要保留已轉轉電子郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="deeab-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="deeab-145">如果您未看到此選項，請確定已指派授權給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="deeab-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="deeab-146">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="deeab-146">Select **Save**.</span></span>

   <span data-ttu-id="deeab-147">**若要轉轉多個電子郵件地址**，您可以要求使用者在 Outlook 中設定規則，以轉往位址。</span><span class="sxs-lookup"><span data-stu-id="deeab-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="deeab-148">若要深入瞭解，請參閱 [使用規則自動轉轉郵件](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)。</span><span class="sxs-lookup"><span data-stu-id="deeab-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="deeab-149">或者，在系統管理中心建立[](../setup/create-distribution-lists.md)通訊群組，新增位址[](add-user-or-contact-to-distribution-list.md)至群組，然後設定轉場，使用本文中的指示指向 DL。</span><span class="sxs-lookup"><span data-stu-id="deeab-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="deeab-150">不要刪除您轉轉電子郵件之使用者的帳戶，或移除他們的授權！</span><span class="sxs-lookup"><span data-stu-id="deeab-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="deeab-151">如果您這麼做，電子郵件轉轉功能將會停止。</span><span class="sxs-lookup"><span data-stu-id="deeab-151">If you do, email forwarding will stop.</span></span>

::: moniker-end
