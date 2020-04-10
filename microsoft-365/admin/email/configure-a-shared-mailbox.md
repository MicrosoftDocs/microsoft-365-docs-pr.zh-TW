---
title: 設定共用信箱
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
description: 建立共用信箱之後，您會想要設定其使用者的某些設定，例如電子郵件轉寄及自動回復。 稍後，您可能想要變更其他設定，例如信箱名稱或成員。
ms.openlocfilehash: fc2995dc448c7cb28c13c10d78b57e7141963539
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212018"
---
# <a name="configure-a-shared-mailbox"></a><span data-ttu-id="d28b0-104">設定共用信箱</span><span class="sxs-lookup"><span data-stu-id="d28b0-104">Configure a shared mailbox</span></span>

<span data-ttu-id="d28b0-105">[建立共用信箱](create-a-shared-mailbox.md)之後，您會想要為信箱使用者設定某些設定，例如電子郵件轉寄及自動回復。</span><span class="sxs-lookup"><span data-stu-id="d28b0-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="d28b0-106">稍後，您可能需要變更其他設定，例如信箱名稱、成員或成員許可權。</span><span class="sxs-lookup"><span data-stu-id="d28b0-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="d28b0-107">變更共用信箱的名稱或電子郵件別名，或變更主要電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="d28b0-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d28b0-108">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="d28b0-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d28b0-110"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="d28b0-111">選取您要編輯的共用信箱，然後選取 [名稱]、[**電子郵件] 和 [電子郵件別名**] 旁邊的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="d28b0-112">輸入新的名稱，或新增其他別名。</span><span class="sxs-lookup"><span data-stu-id="d28b0-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="d28b0-113">如果您想要變更主要電子郵件地址，您的信箱必須有一個以上的電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="d28b0-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="d28b0-114">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d28b0-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="d28b0-115">轉寄傳送到共用信箱的電子郵件</span><span class="sxs-lookup"><span data-stu-id="d28b0-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="d28b0-116">您不需要將授權指派給共用信箱，即可轉寄傳送給它的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d28b0-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="d28b0-117">您可以將郵件轉寄至任何有效的電子郵件地址或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="d28b0-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d28b0-118">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="d28b0-119"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d28b0-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="d28b0-121">選取您要編輯的共用信箱，然後選取 [**電子郵件** \>轉寄] [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="d28b0-122">將切換設定為 [**開啟**]，然後輸入一個電子郵件地址，以轉寄郵件。</span><span class="sxs-lookup"><span data-stu-id="d28b0-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="d28b0-123">它可以是任何有效的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d28b0-123">It can be any valid email address.</span></span> <span data-ttu-id="d28b0-124">若要轉寄至多個位址，您必須為位址[建立通訊群組](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide)，然後在此方塊中輸入群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="d28b0-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="d28b0-125">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d28b0-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="d28b0-126">從共用信箱傳送自動回覆</span><span class="sxs-lookup"><span data-stu-id="d28b0-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d28b0-127">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="d28b0-128"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d28b0-129"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="d28b0-130">選取您要編輯的共用信箱，然後選取 [**自動回復** \> ] [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="d28b0-131">將切換設定為 [**開啟**]，然後選擇是否要將回復傳送給組織內或組織外的人員。</span><span class="sxs-lookup"><span data-stu-id="d28b0-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="d28b0-132">輸入您想要傳送給組織內人員的回覆。</span><span class="sxs-lookup"><span data-stu-id="d28b0-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="d28b0-133">您只能加入文字而不能加入影像。</span><span class="sxs-lookup"><span data-stu-id="d28b0-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="d28b0-134">如果您*也*想要將回復傳送給組織外部的人員，請選取您要取得回復的核取方塊，然後輸入文字。</span><span class="sxs-lookup"><span data-stu-id="d28b0-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="d28b0-135">There's no way to only send to people outside your organization but not to people inside your organization.</span><span class="sxs-lookup"><span data-stu-id="d28b0-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="d28b0-136">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d28b0-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="d28b0-137">允許所有人都看到已傳送的電子郵件 (回覆)</span><span class="sxs-lookup"><span data-stu-id="d28b0-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="d28b0-p108">根據預設，從共用信箱寄出的郵件不會儲存至共用信箱的 [寄件備份] 資料夾。不過，這些郵件會儲存到寄件者的 [寄件備份] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d28b0-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="d28b0-140">如果您想要允許所有人查看已傳送的電子郵件，請在系統管理中心中編輯共用信箱設定，然後選取 [**已傳送的專案** \> ] [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-office-365-email"></a><span data-ttu-id="d28b0-141">選擇共用信箱可用於存取 Office 365 電子郵件的應用程式</span><span class="sxs-lookup"><span data-stu-id="d28b0-141">Choose the apps that a shared mailbox can use to access Office 365 email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d28b0-142">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="d28b0-143"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d28b0-144"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="d28b0-145">選取您要編輯的共用信箱，然後選取 [**電子郵件應用程式** \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="d28b0-146">針對您想要讓成員存取共用信箱的所有應用程式，將 [開啟] 設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="d28b0-147">針對您不想要使用的任何應用程式，將其開關設定為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="d28b0-148">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d28b0-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="d28b0-149">讓共用信箱處於訴訟暫止狀態</span><span class="sxs-lookup"><span data-stu-id="d28b0-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="d28b0-150">若要深入瞭解訴訟暫止，請參閱[建立訴訟暫](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)止。</span><span class="sxs-lookup"><span data-stu-id="d28b0-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d28b0-151">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="d28b0-152"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d28b0-153"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="d28b0-154">選取您要編輯的共用信箱，然後選取 [**訴訟暫** \>止] [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="d28b0-155">將開啟開關設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="d28b0-156">（選用）輸入持續時間、有關保留的備註，以及包含詳細資訊的 URL。</span><span class="sxs-lookup"><span data-stu-id="d28b0-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="d28b0-157">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d28b0-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="d28b0-158">新增或移除成員</span><span class="sxs-lookup"><span data-stu-id="d28b0-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d28b0-159">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="d28b0-160"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d28b0-161"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="d28b0-162">選取您要編輯的共用信箱，然後選取 [**成員** \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="d28b0-163">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="d28b0-163">Do one of the following:</span></span>
   - <span data-ttu-id="d28b0-164">若要新增成員，請選取 [**新增成員**]、[搜尋] 或 [選取要新增的成員]，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="d28b0-165">若要移除成員，請在必要時使用搜尋方塊來搜尋成員，選取成員名稱旁邊的**X** ，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="d28b0-166">再次選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="d28b0-167">新增或移除成員的許可權</span><span class="sxs-lookup"><span data-stu-id="d28b0-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d28b0-168">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="d28b0-169"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d28b0-170"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="d28b0-171">選取您要編輯的共用信箱，然後選取 [**成員** \> **自訂許可權**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="d28b0-172">選取您要變更成員之許可權旁邊的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="d28b0-173">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="d28b0-173">Do one of the following:</span></span>
   - <span data-ttu-id="d28b0-174">若要將該許可權授與其他成員，請選取 [**新增許可權**]、[搜尋] 或 [選取要新增的成員]，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="d28b0-175">若要移除成員的許可權，請使用搜尋方塊來搜尋成員（如有必要），選取成員名稱旁邊的**X** ，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="d28b0-176">再次選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="d28b0-177">在全域通訊清單中顯示或隱藏共用信箱</span><span class="sxs-lookup"><span data-stu-id="d28b0-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="d28b0-178">如果您選擇不在全域通訊清單中顯示共用信箱，該信箱不會出現在您組織的通訊清單中，但仍然會收到傳送給它的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d28b0-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d28b0-179">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="d28b0-180"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d28b0-181"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">在系統管理中心</a>中，移至 \*\*[群組] \*\* > **[共用信箱]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="d28b0-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="d28b0-182">選取您要編輯的共用信箱，然後選取 [**在全域通訊清單** \> **編輯**] 中的 [顯示]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="d28b0-183">將開啟或關閉切換為 **[開啟]** 或 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="d28b0-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="d28b0-184">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d28b0-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d28b0-185">從通訊清單中隱藏共用信箱，將無法將隱藏的信箱新增至他們的 Outlook 設定檔，直到共用信箱再次顯示在通訊清單中為止。</span><span class="sxs-lookup"><span data-stu-id="d28b0-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="d28b0-186">相關文章</span><span class="sxs-lookup"><span data-stu-id="d28b0-186">Related articles</span></span>

[<span data-ttu-id="d28b0-187">關於共用信箱</span><span class="sxs-lookup"><span data-stu-id="d28b0-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="d28b0-188">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="d28b0-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="d28b0-189">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="d28b0-189">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="d28b0-190">從共用信箱中移除授權</span><span class="sxs-lookup"><span data-stu-id="d28b0-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="d28b0-191">解決共用信箱的問題</span><span class="sxs-lookup"><span data-stu-id="d28b0-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
