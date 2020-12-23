---
title: 將信箱權限授予另一位其他使用者 - 系統管理員說明
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: '瞭解如何授予使用者存取另一個使用者信箱的權限。 這可讓使用者從其他使用者的信箱讀取郵件及傳送郵件。 '
ms.openlocfilehash: af12cfe3acad9e12ca3983c9fa13f52b72f0a467
ms.sourcegitcommit: 16e018f8b6eef5dad48eabf179691ead3cebe533
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2020
ms.locfileid: "49725150"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="0b3fc-104">將信箱權限授予另一位其他使用者 - 系統管理員說明</span><span class="sxs-lookup"><span data-stu-id="0b3fc-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="0b3fc-105">身為系統管理員，公司可能會要求您授權部分使用者存取另一個使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="0b3fc-106">例如，您可能會想要授權助理來傳送或讀取直屬主管信箱的電子郵件，或是授權其中一個使用者代理另一個使用者傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="0b3fc-107">本主題將向您說明如何完成這項作業。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="0b3fc-108">如需有關建立及管理共用信箱的資訊，請參閱[建立共用信箱](../email/create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="0b3fc-109">想知道如何設定信箱權限嗎？</span><span class="sxs-lookup"><span data-stu-id="0b3fc-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="0b3fc-p103">信箱權限能讓您將某個信箱的讀取/寫入權限授予給另一個使用者。以下文章將協助您設定及使用此功能：</span><span class="sxs-lookup"><span data-stu-id="0b3fc-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="0b3fc-112">**設定權限：**</span><span class="sxs-lookup"><span data-stu-id="0b3fc-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="0b3fc-p104">設定權限的第一個步驟便是決定您要授權其他使用者可對特定信箱採取的行動。您可以允許使用者讀取信箱中的電子郵件、代理另一個使用者傳送電子郵件，以及以該信箱當作寄件地址傳送電子郵件。請參閱下列文章，了解如何設定各種權限：</span><span class="sxs-lookup"><span data-stu-id="0b3fc-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="0b3fc-116">讀取另一個使用者信箱中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="0b3fc-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="0b3fc-117">從另一個使用者的信箱傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="0b3fc-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="0b3fc-118">代理另一位使用者傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="0b3fc-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="0b3fc-119">**變更傳播：**</span><span class="sxs-lookup"><span data-stu-id="0b3fc-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="0b3fc-120">在您設定好權限後，系統需要 60 分鐘的時間，才能在整個系統中傳播並生效變更。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="0b3fc-121">**如何運用設定完成的權限：**</span><span class="sxs-lookup"><span data-stu-id="0b3fc-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="0b3fc-p105">當您獲得權限後，您可以透過幾種不同的方式存取信箱。如需相關說明，請參閱下列文章：[存取另一個人的信箱](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="0b3fc-124">權限只能在目前組織租使用者中設定。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-124">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="0b3fc-125">無法設定租使用者以外的信箱權限。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-125">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="0b3fc-126">從另一個使用者的信箱傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="0b3fc-126">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0b3fc-127">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="0b3fc-128">選取使用者名稱 (您計畫要賦予傳送權限的使用者)，以開啟其 [屬性] 窗格。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-128">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="0b3fc-129">在 **[郵件]** 索引標籤上，選取 **[管理信箱權限]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-129">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="0b3fc-130">選取 **[傳送為]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-130">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="0b3fc-131">選取 **[新增權限]**，然後選擇您希望這位使用者能夠以其身分傳送的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-131">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="0b3fc-132">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-132">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0b3fc-133">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="0b3fc-134">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-134">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="0b3fc-135">選取 **[傳送為]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-135">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="0b3fc-136">選取 **[新增權限]**，然後選擇您希望這位使用者能夠以其身分傳送的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-136">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="0b3fc-137">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-137">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0b3fc-138">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="0b3fc-139">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-139">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="0b3fc-140">選取 **[傳送為]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-140">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="0b3fc-141">選取 **[新增權限]**，然後選擇您希望這位使用者能夠以其身分傳送的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-141">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="0b3fc-142">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-142">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="0b3fc-143">讀取另一個使用者信箱中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="0b3fc-143">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0b3fc-144">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-144">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="0b3fc-145">選取使用者名稱 (要允許讀取的信箱)，以開啟其 [屬性] 窗格。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-145">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="0b3fc-146">在 **[郵件]** 索引標籤上，選取 **[管理信箱權限]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-146">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="0b3fc-147">選取 **[讀取和管理]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-147">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="0b3fc-148">選取 **[新增權限]**，然後選擇您想要允許讀取此信箱之電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-148">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="0b3fc-149">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-149">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="0b3fc-150">當 Exchange 系統管理中心授予時，**讀取** 和 **管理** 權限即為 **完整存取權** 權限。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-150">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="0b3fc-151">完整存取權權限不會授與 **傳送為** 或 **代理傳送者** 權限。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-151">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0b3fc-152">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="0b3fc-153">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-153">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="0b3fc-154">選取 **[讀取和管理]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-154">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="0b3fc-155">選取 **[新增權限]**，然後選擇您想要允許讀取此信箱之電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-155">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="0b3fc-156">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-156">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0b3fc-157">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="0b3fc-158">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-158">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="0b3fc-159">選取 **[讀取和管理]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-159">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="0b3fc-160">選取 **[新增權限]**，然後選擇您想要允許讀取此信箱之電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-160">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="0b3fc-161">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-161">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="0b3fc-162">代理另一個使用者傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="0b3fc-162">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0b3fc-163">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-163">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="0b3fc-164">選取使用者名稱 (您計畫要賦予 **代理傳送** 權限的使用者)，以開啟其 [屬性] 窗格。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-164">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="0b3fc-165">在 **[郵件]** 索引標籤上，選取 **[管理信箱權限]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-165">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="0b3fc-166">選取 **[代理傳送者]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-166">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="0b3fc-167">選取 **[新增權限]**，然後選擇您想要允許代理此信箱傳送電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-167">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="0b3fc-168">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-168">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0b3fc-169">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="0b3fc-170">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-170">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="0b3fc-171">選取 **[代理傳送者]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-171">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="0b3fc-172">選取 **[新增權限]**，然後選擇您想要允許代理此信箱傳送電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-172">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="0b3fc-173">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-173">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0b3fc-174">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-174">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="0b3fc-175">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-175">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="0b3fc-176">選取 **[代理傳送者]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-176">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="0b3fc-177">選取 **[新增權限]**，然後選擇您想要允許代理此信箱傳送電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-177">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="0b3fc-178">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="0b3fc-178">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="0b3fc-179">從 Outlook 和商務用 Outlook 網頁版傳送及讀取郵件</span><span class="sxs-lookup"><span data-stu-id="0b3fc-179">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="0b3fc-p108">想知道如何從另一個使用者的信箱傳送電子郵件嗎？請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="0b3fc-p108">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="0b3fc-182">管理其他人的郵件和行事曆項目</span><span class="sxs-lookup"><span data-stu-id="0b3fc-182">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="0b3fc-183">從另一個使用者或群組傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="0b3fc-183">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
