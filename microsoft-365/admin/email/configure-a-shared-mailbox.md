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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: 建立共用信箱，並為其使用者設定某些設定，例如電子郵件轉寄及自動回復。
ms.openlocfilehash: e69d1bbde5784339f3973bf456eca1ded72840af
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393988"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="4d0b7-103">設置共用信箱的設定</span><span class="sxs-lookup"><span data-stu-id="4d0b7-103">Configure shared mailbox settings</span></span>

<span data-ttu-id="4d0b7-104">[建立共用信箱](create-a-shared-mailbox.md)之後，您會想要為信箱使用者設定某些設定，例如電子郵件轉寄及自動回復。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-104">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="4d0b7-105">稍後，您可能需要變更其他設定，例如信箱名稱、成員或成員許可權。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-105">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="4d0b7-106">變更共用信箱的名稱或電子郵件別名，或變更主要電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="4d0b7-106">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="4d0b7-107">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-107">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="4d0b7-108">選取您要編輯的共用信箱，然後選取 [名稱]、[**電子郵件] 和 [電子郵件別名**] 旁邊的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-108">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="4d0b7-109">輸入新的名稱，或新增其他別名。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-109">Enter a new name, or add another alias.</span></span> <span data-ttu-id="4d0b7-110">如果您想要變更主要電子郵件地址，您的信箱必須有一個以上的電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-110">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="4d0b7-111">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-111">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="4d0b7-112">轉寄傳送到共用信箱的電子郵件</span><span class="sxs-lookup"><span data-stu-id="4d0b7-112">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="4d0b7-113">您不需要將授權指派給共用信箱，即可轉寄傳送給它的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-113">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="4d0b7-114">您可以將郵件轉寄至任何有效的電子郵件地址或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-114">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="4d0b7-115">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-115">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="4d0b7-116">選取您要編輯的共用信箱，然後選取 [ **電子郵件** 轉寄] [ \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-116">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="4d0b7-117">將切換設定為 [ **開啟**]，然後輸入一個電子郵件地址，以轉寄郵件。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-117">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="4d0b7-118">它可以是任何有效的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-118">It can be any valid email address.</span></span> <span data-ttu-id="4d0b7-119">若要轉寄至多個位址，您必須為位址 [建立通訊群組](/office365/admin/setup/create-distribution-lists) ，然後在此方塊中輸入群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-119">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="4d0b7-120">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-120">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="4d0b7-121">從共用信箱傳送自動回覆</span><span class="sxs-lookup"><span data-stu-id="4d0b7-121">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="4d0b7-122">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-122">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="4d0b7-123">選取您要編輯的共用信箱，然後選取 [ **自動回復**] [ \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-123">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="4d0b7-124">將切換設定為 [ **開啟**]，然後選擇是否要將回復傳送給組織內或組織外的人員。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-124">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="4d0b7-p105">輸入您想要傳送給組織內人員的回覆。您只能加入文字而不能加入影像。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-p105">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="4d0b7-127">如果您 *也* 想要將回復傳送給組織外部的人員，請選取您要取得回復的核取方塊，然後輸入文字。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-127">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="4d0b7-128">There's no way to only send to people outside your organization but not to people inside your organization.</span><span class="sxs-lookup"><span data-stu-id="4d0b7-128">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="4d0b7-129">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-129">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="4d0b7-130">允許所有人都看到已傳送的電子郵件 (回覆)</span><span class="sxs-lookup"><span data-stu-id="4d0b7-130">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="4d0b7-p107">根據預設，從共用信箱寄出的郵件不會儲存至共用信箱的 [寄件備份] 資料夾。不過，這些郵件會儲存到寄件者的 [寄件備份] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-p107">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="4d0b7-133">如果您想要允許所有人查看已傳送的電子郵件，請在系統管理中心中編輯共用信箱設定，然後選取 [ **已傳送的專案**] [ \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-133">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="4d0b7-134">選擇共用信箱可用於存取 Microsoft 電子郵件的應用程式</span><span class="sxs-lookup"><span data-stu-id="4d0b7-134">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="4d0b7-135">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-135">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="4d0b7-136">選取您要編輯的共用信箱，然後選取 [ **電子郵件應用程式** \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-136">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="4d0b7-137">針對您想要讓成員存取共用信箱的所有應用程式，將 [開啟] 設定為 [ **開啟** ]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-137">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="4d0b7-138">針對您不想要使用的任何應用程式，將其開關設定為 [ **關閉** ]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-138">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="4d0b7-139">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-139">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="4d0b7-140">讓共用信箱處於訴訟暫止狀態</span><span class="sxs-lookup"><span data-stu-id="4d0b7-140">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="4d0b7-141">若要深入瞭解訴訟暫止，請參閱 [建立訴訟暫](../../compliance/create-a-litigation-hold.md)止。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-141">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="4d0b7-142">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="4d0b7-143">選取您要編輯的共用信箱，然後選取 [ **訴訟暫** 止] [ \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-143">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="4d0b7-144">將開啟開關設定為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-144">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="4d0b7-145">（選用）輸入持續時間、有關保留的備註，以及包含詳細資訊的 URL。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-145">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="4d0b7-146">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-146">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="4d0b7-147">新增或移除成員</span><span class="sxs-lookup"><span data-stu-id="4d0b7-147">Add or remove members</span></span>

1. <span data-ttu-id="4d0b7-148">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-148">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="4d0b7-149">選取您要編輯的共用信箱，然後選取 [ **成員** \> **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-149">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="4d0b7-150">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4d0b7-150">Do one of the following:</span></span>
   - <span data-ttu-id="4d0b7-151">若要新增成員，請選取 [ **新增成員**]、[搜尋] 或 [選取要新增的成員]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-151">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="4d0b7-152">若要移除成員，請在必要時使用搜尋方塊來搜尋成員，選取成員名稱旁邊的 **X** ，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-152">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="4d0b7-153">再次選取 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-153">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="4d0b7-154">新增或移除成員的許可權</span><span class="sxs-lookup"><span data-stu-id="4d0b7-154">Add or remove permissions of members</span></span>

1. <span data-ttu-id="4d0b7-155">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-155">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="4d0b7-156">選取您要編輯的共用信箱，然後選取 [ **成員** \> **自訂許可權**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-156">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="4d0b7-157">選取您要變更成員之許可權旁邊的 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-157">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="4d0b7-158">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4d0b7-158">Do one of the following:</span></span>
   - <span data-ttu-id="4d0b7-159">若要將該許可權授與其他成員，請選取 [ **新增許可權**]、[搜尋] 或 [選取要新增的成員]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-159">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="4d0b7-160">若要移除成員的許可權，請使用搜尋方塊來搜尋成員（如有必要），選取成員名稱旁邊的 **X** ，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-160">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="4d0b7-161">再次選取 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-161">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="4d0b7-162">在全域通訊清單中顯示或隱藏共用信箱</span><span class="sxs-lookup"><span data-stu-id="4d0b7-162">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="4d0b7-163">如果您選擇不在全域通訊清單中顯示共用信箱，該信箱不會出現在您組織的通訊清單中，但仍然會收到傳送給它的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-163">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="4d0b7-164">在系統管理中心中，移至 **[群組]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共用信箱]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-164">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="4d0b7-165">選取您要編輯的共用信箱，然後選取 [ **在全域通訊清單** 編輯] 中的 [顯示] \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-165">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="4d0b7-166">將開啟或關閉切換為 **[開啟]**  或 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-166">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="4d0b7-167">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-167">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="4d0b7-168">從通訊清單中隱藏共用信箱，將無法將隱藏的信箱新增至其 Outlook 設定檔，直到共用信箱再次顯示在通訊清單中為止。</span><span class="sxs-lookup"><span data-stu-id="4d0b7-168">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="4d0b7-169">相關內容</span><span class="sxs-lookup"><span data-stu-id="4d0b7-169">Related content</span></span>

<span data-ttu-id="4d0b7-170">[關於共用信箱](about-shared-mailboxes.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="4d0b7-170">[About shared mailboxes](about-shared-mailboxes.md) (article)\</span></span>
<span data-ttu-id="4d0b7-171">[建立共用信箱](create-a-shared-mailbox.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="4d0b7-171">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4d0b7-172">[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="4d0b7-172">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)\</span></span>
<span data-ttu-id="4d0b7-173">[從共用信箱移除授權](remove-license-from-shared-mailbox.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="4d0b7-173">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)\</span></span>
<span data-ttu-id="4d0b7-174">[解決共用信箱的問題](resolve-issues-with-shared-mailboxes.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="4d0b7-174">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>