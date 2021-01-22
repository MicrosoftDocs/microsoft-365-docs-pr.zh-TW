---
title: 設置共用信箱的設定
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
description: 建立共用信箱之後，您需要為使用者設定一些設定，例如電子郵件轉場和自動回復。 稍後，您可能會想要變更其他設定，例如信箱名稱或成員。
ms.openlocfilehash: fe5d35be556b8edf5456bc2c0b820dc0ce77e323
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926603"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="c9b6d-104">設置共用信箱的設定</span><span class="sxs-lookup"><span data-stu-id="c9b6d-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="c9b6d-105">建立共用 [信箱之後](create-a-shared-mailbox.md)，您需要為信箱使用者設定一些設定，例如電子郵件轉場和自動回復。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="c9b6d-106">稍後，您可能會想要變更其他設定，例如信箱名稱、成員或成員許可權。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="c9b6d-107">變更共用信箱的名稱或電子郵件別名，或變更主要電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="c9b6d-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c9b6d-108">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="c9b6d-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c9b6d-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="c9b6d-111">選取要編輯的共用信箱，然後選取名稱、電子郵件、電子郵件別名旁邊的 **編輯。**</span><span class="sxs-lookup"><span data-stu-id="c9b6d-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="c9b6d-112">輸入新名稱，或新增其他別名。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="c9b6d-113">如果您要變更主要電子郵件地址，信箱必須擁有一個或多個電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="c9b6d-114">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="c9b6d-115">轉寄傳送到共用信箱的電子郵件</span><span class="sxs-lookup"><span data-stu-id="c9b6d-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="c9b6d-116">您不需要指派授權給共用信箱，以轉寄寄到共用信箱的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="c9b6d-117">您可以將郵件轉會到任何有效的電子郵件地址或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c9b6d-118">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="c9b6d-119"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c9b6d-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="c9b6d-121">選取要編輯的共用信箱，然後選取電子郵件 **轉轉編輯** \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="c9b6d-122">將開關切換為 **開啟**，然後輸入一個電子郵件地址來轉入郵件。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="c9b6d-123">可以是任何有效的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-123">It can be any valid email address.</span></span> <span data-ttu-id="c9b6d-124">若要轉入多個位址，您必須建立位址的[](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists)通訊群組，然後在此方塊中輸入組名。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="c9b6d-125">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="c9b6d-126">從共用信箱傳送自動回覆</span><span class="sxs-lookup"><span data-stu-id="c9b6d-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c9b6d-127">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="c9b6d-128"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c9b6d-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="c9b6d-130">選取要編輯的共用信箱，然後選取自動 **回復編輯** \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="c9b6d-131">將開關切換為 **開啟**，並選擇是否要傳送回復給組織內部或組織外部人員。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="c9b6d-132">輸入您想要傳送給組織內人員的回覆。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="c9b6d-133">您只能加入文字而不能加入影像。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="c9b6d-134">如果您也 *想要傳送* 回復給組織外部人員，請選取要收到回復的核取方塊，然後輸入文字。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="c9b6d-135">There's no way to only send to people outside your organization but not to people inside your organization.</span><span class="sxs-lookup"><span data-stu-id="c9b6d-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="c9b6d-136">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="c9b6d-137">允許所有人都看到已傳送的電子郵件 (回覆)</span><span class="sxs-lookup"><span data-stu-id="c9b6d-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="c9b6d-p108">根據預設，從共用信箱寄出的郵件不會儲存至共用信箱的 [寄件備份] 資料夾。不過，這些郵件會儲存到寄件者的 [寄件備份] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="c9b6d-140">如果您想要允許所有人都看到已寄件電子郵件，請在系統管理中心編輯共用信箱設定，然後選取已 **送出項目的編輯** \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="c9b6d-141">選擇共用信箱可用於存取 Microsoft 電子郵件的應用程式</span><span class="sxs-lookup"><span data-stu-id="c9b6d-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c9b6d-142">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="c9b6d-143"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c9b6d-144"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="c9b6d-145">選取要編輯的共用信箱，然後選取電子郵件 **App 編輯** \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="c9b6d-146">針對 **您希望成員能夠** 存取共用信箱的所有 App，將開關設為開啟。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="c9b6d-147">針對 **您不希望他們** 使用的任何 App，將開關設為關閉。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="c9b6d-148">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="c9b6d-149">將共用信箱置於訴訟資料保留狀態</span><span class="sxs-lookup"><span data-stu-id="c9b6d-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="c9b6d-150">若要深入瞭解訴訟資料保留，請參閱建立 [訴訟資料保留](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c9b6d-151">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="c9b6d-152"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c9b6d-153"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="c9b6d-154">選取要編輯的共用信箱，然後選取訴訟 **資料保留** \> **編輯**。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="c9b6d-155">將開關切換至 **開啟**。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="c9b6d-156">或者，輸入持續時間、保留的備註，以及包含詳細資訊的 URL。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="c9b6d-157">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="c9b6d-158">新增或移除成員</span><span class="sxs-lookup"><span data-stu-id="c9b6d-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c9b6d-159">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="c9b6d-160"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c9b6d-161"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="c9b6d-162">選取要編輯的共用信箱，然後選取成員 **編輯** \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="c9b6d-163">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c9b6d-163">Do one of the following:</span></span>
   - <span data-ttu-id="c9b6d-164">若要新增成員， **請選取新增成員**、搜尋或選取要新增的成員， **然後選取儲存**。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="c9b6d-165">若要移除成員，請在必要時使用搜尋方塊搜尋成員，選取成員名稱旁邊的 **X，\*\*\*\*然後選取儲存**。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="c9b6d-166">再次 **選取儲存** 。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="c9b6d-167">新增或移除成員的許可權</span><span class="sxs-lookup"><span data-stu-id="c9b6d-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c9b6d-168">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="c9b6d-169"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c9b6d-170"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="c9b6d-171">選取要編輯的共用信箱，然後選取成員 \> **自訂許可權**。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="c9b6d-172">選取 **您想要** 針對成員變更的許可權旁邊的編輯。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="c9b6d-173">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c9b6d-173">Do one of the following:</span></span>
   - <span data-ttu-id="c9b6d-174">若要將該許可權授予其他成員，請選取新增許可權、搜尋或選取要新增的成員，**然後選取儲存**。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="c9b6d-175">若要移除成員的許可權，請在必要時使用搜尋方塊搜尋成員，選取成員名稱旁邊的 **X，\*\*\*\*然後選取儲存**。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="c9b6d-176">再次 **選取儲存** 。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="c9b6d-177">顯示或隱藏全域通訊清單中的共用信箱</span><span class="sxs-lookup"><span data-stu-id="c9b6d-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="c9b6d-178">如果您選擇不顯示全域通訊清單中的共用信箱，信箱不會顯示在貴組織的地址清單中，但仍會收到電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c9b6d-179">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="c9b6d-180"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c9b6d-181"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 **[群組]** > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="c9b6d-182">選取要編輯的共用信箱，然後選取在全域 **地址清單中顯示編輯** \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="c9b6d-183">將開關切換至 **開啟**  或 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="c9b6d-184">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="c9b6d-185">從地址清單中隱藏共用信箱後，新共用信箱成員將無法新增隱藏的信箱至其 Outlook 設定檔，直到共用信箱再次顯示在地址清單中。</span><span class="sxs-lookup"><span data-stu-id="c9b6d-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="c9b6d-186">相關文章</span><span class="sxs-lookup"><span data-stu-id="c9b6d-186">Related articles</span></span>

[<span data-ttu-id="c9b6d-187">關於共用信箱</span><span class="sxs-lookup"><span data-stu-id="c9b6d-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="c9b6d-188">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="c9b6d-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="c9b6d-189">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="c9b6d-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="c9b6d-190">從共用信箱中移除授權</span><span class="sxs-lookup"><span data-stu-id="c9b6d-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="c9b6d-191">解決共用信箱的問題</span><span class="sxs-lookup"><span data-stu-id="c9b6d-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
