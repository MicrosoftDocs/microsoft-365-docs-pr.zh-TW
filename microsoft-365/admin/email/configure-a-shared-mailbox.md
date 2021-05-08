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
search.appverid:
- BCS160
- MET150
- MOE150
description: 建立共用信箱之後，您會想要設定其使用者的某些設定，例如電子郵件轉寄及自動回復。 稍後，您可能想要變更其他設定，例如信箱名稱或成員。
ms.openlocfilehash: 01d5aaa686e1d64c9ea7d89913d8208f779dcfd1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52243969"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="ddecb-104">設置共用信箱的設定</span><span class="sxs-lookup"><span data-stu-id="ddecb-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="ddecb-105">[建立共用信箱](create-a-shared-mailbox.md)之後，您會想要為信箱使用者設定某些設定，例如電子郵件轉寄及自動回復。</span><span class="sxs-lookup"><span data-stu-id="ddecb-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="ddecb-106">稍後，您可能需要變更其他設定，例如信箱名稱、成員或成員許可權。</span><span class="sxs-lookup"><span data-stu-id="ddecb-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="ddecb-107">變更共用信箱的名稱或電子郵件別名，或變更主要電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="ddecb-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="ddecb-108">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ddecb-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="ddecb-109">選取您要編輯的共用信箱，然後選取 [名稱]、[**電子郵件] 和 [電子郵件別名**] 旁邊的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-109">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="ddecb-110">輸入新的名稱，或新增其他別名。</span><span class="sxs-lookup"><span data-stu-id="ddecb-110">Enter a new name, or add another alias.</span></span> <span data-ttu-id="ddecb-111">如果您想要變更主要電子郵件地址，您的信箱必須有一個以上的電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="ddecb-111">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="ddecb-112">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-112">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="ddecb-113">轉寄傳送到共用信箱的電子郵件</span><span class="sxs-lookup"><span data-stu-id="ddecb-113">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="ddecb-114">您不需要將授權指派給共用信箱，即可轉寄傳送給它的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ddecb-114">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="ddecb-115">您可以將郵件轉寄至任何有效的電子郵件地址或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="ddecb-115">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="ddecb-116">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ddecb-116">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="ddecb-117">選取您要編輯的共用信箱，然後選取 [ **電子郵件** 轉寄] [ \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-117">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="ddecb-118">將切換設定為 [ **開啟**]，然後輸入一個電子郵件地址，以轉寄郵件。</span><span class="sxs-lookup"><span data-stu-id="ddecb-118">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="ddecb-119">它可以是任何有效的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ddecb-119">It can be any valid email address.</span></span> <span data-ttu-id="ddecb-120">若要轉寄至多個位址，您必須為位址 [建立通訊群組](/office365/admin/setup/create-distribution-lists) ，然後在此方塊中輸入群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="ddecb-120">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="ddecb-121">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-121">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="ddecb-122">從共用信箱傳送自動回覆</span><span class="sxs-lookup"><span data-stu-id="ddecb-122">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="ddecb-123">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ddecb-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="ddecb-124">選取您要編輯的共用信箱，然後選取 [ **自動回復**] [ \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-124">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="ddecb-125">將切換設定為 [ **開啟**]，然後選擇是否要將回復傳送給組織內或組織外的人員。</span><span class="sxs-lookup"><span data-stu-id="ddecb-125">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="ddecb-p106">輸入您想要傳送給組織內人員的回覆。您只能加入文字而不能加入影像。</span><span class="sxs-lookup"><span data-stu-id="ddecb-p106">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="ddecb-128">如果您 *也* 想要將回復傳送給組織外部的人員，請選取您要取得回復的核取方塊，然後輸入文字。</span><span class="sxs-lookup"><span data-stu-id="ddecb-128">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="ddecb-129">There's no way to only send to people outside your organization but not to people inside your organization.</span><span class="sxs-lookup"><span data-stu-id="ddecb-129">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="ddecb-130">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-130">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="ddecb-131">允許所有人都看到已傳送的電子郵件 (回覆)</span><span class="sxs-lookup"><span data-stu-id="ddecb-131">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="ddecb-p108">根據預設，從共用信箱寄出的郵件不會儲存至共用信箱的 [寄件備份] 資料夾。不過，這些郵件會儲存到寄件者的 [寄件備份] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="ddecb-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="ddecb-134">如果您想要允許所有人查看已傳送的電子郵件，請在系統管理中心中編輯共用信箱設定，然後選取 [ **已傳送的專案**] [ \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-134">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="ddecb-135">選擇共用信箱可用於存取 Microsoft 電子郵件的應用程式</span><span class="sxs-lookup"><span data-stu-id="ddecb-135">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="ddecb-136">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ddecb-136">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="ddecb-137">選取您要編輯的共用信箱，然後選取 [ **電子郵件應用程式** \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-137">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="ddecb-138">針對您想要讓成員存取共用信箱的所有應用程式，將 [開啟] 設定為 [ **開啟** ]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-138">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="ddecb-139">針對您不想要使用的任何應用程式，將其開關設定為 [ **關閉** ]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-139">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="ddecb-140">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-140">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="ddecb-141">讓共用信箱處於訴訟暫止狀態</span><span class="sxs-lookup"><span data-stu-id="ddecb-141">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="ddecb-142">若要深入瞭解訴訟暫止，請參閱 [建立訴訟暫](../../compliance/create-a-litigation-hold.md)止。</span><span class="sxs-lookup"><span data-stu-id="ddecb-142">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="ddecb-143">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ddecb-143">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="ddecb-144">選取您要編輯的共用信箱，然後選取 [ **訴訟暫** 止] [ \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-144">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="ddecb-145">將開啟開關設定為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-145">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="ddecb-146">（選用）輸入持續時間、有關保留的備註，以及包含詳細資訊的 URL。</span><span class="sxs-lookup"><span data-stu-id="ddecb-146">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="ddecb-147">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-147">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="ddecb-148">新增或移除成員</span><span class="sxs-lookup"><span data-stu-id="ddecb-148">Add or remove members</span></span>

1. <span data-ttu-id="ddecb-149">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ddecb-149">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="ddecb-150">選取您要編輯的共用信箱，然後選取 [ **成員** \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-150">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="ddecb-151">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ddecb-151">Do one of the following:</span></span>
   - <span data-ttu-id="ddecb-152">若要新增成員，請選取 [ **新增成員**]、[搜尋] 或 [選取要新增的成員]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-152">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="ddecb-153">若要移除成員，請在必要時使用搜尋方塊來搜尋成員，選取成員名稱旁邊的 **X** ，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-153">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="ddecb-154">再次選取 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-154">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="ddecb-155">新增或移除成員的許可權</span><span class="sxs-lookup"><span data-stu-id="ddecb-155">Add or remove permissions of members</span></span>

1. <span data-ttu-id="ddecb-156">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ddecb-156">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="ddecb-157">選取您要編輯的共用信箱，然後選取 [ **成員** \> **自訂許可權**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-157">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="ddecb-158">選取您要變更成員之許可權旁邊的 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-158">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="ddecb-159">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ddecb-159">Do one of the following:</span></span>
   - <span data-ttu-id="ddecb-160">若要將該許可權授與其他成員，請選取 [ **新增許可權**]、[搜尋] 或 [選取要新增的成員]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-160">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="ddecb-161">若要移除成員的許可權，請使用搜尋方塊來搜尋成員（如有必要），選取成員名稱旁邊的 **X** ，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-161">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="ddecb-162">再次選取 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-162">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="ddecb-163">在全域通訊清單中顯示或隱藏共用信箱</span><span class="sxs-lookup"><span data-stu-id="ddecb-163">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="ddecb-164">如果您選擇不在全域通訊清單中顯示共用信箱，該信箱不會出現在您組織的通訊清單中，但仍然會收到傳送給它的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ddecb-164">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="ddecb-165">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="ddecb-165">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="ddecb-166">選取您要編輯的共用信箱，然後選取 [ **在全域通訊清單** 編輯] 中的 [顯示] \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ddecb-166">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="ddecb-167">將開啟或關閉切換為 **[開啟]**  或 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-167">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="ddecb-168">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ddecb-168">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ddecb-169">從通訊清單中隱藏共用信箱，將無法將隱藏的信箱新增至其 Outlook 設定檔，直到共用信箱再次顯示在通訊清單中為止。</span><span class="sxs-lookup"><span data-stu-id="ddecb-169">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="ddecb-170">相關內容</span><span class="sxs-lookup"><span data-stu-id="ddecb-170">Related content</span></span>

<span data-ttu-id="ddecb-171">[關於共用信箱](about-shared-mailboxes.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="ddecb-171">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>

<span data-ttu-id="ddecb-172">[建立共用信箱](create-a-shared-mailbox.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="ddecb-172">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="ddecb-173">[將使用者信箱轉換成共用信箱](convert-user-mailbox-to-shared-mailbox.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="ddecb-173">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="ddecb-174">[從共用信箱中移除授權](remove-license-from-shared-mailbox.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="ddecb-174">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="ddecb-175">[解決共用信箱](resolve-issues-with-shared-mailboxes.md) (文章) 的問題</span><span class="sxs-lookup"><span data-stu-id="ddecb-175">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>