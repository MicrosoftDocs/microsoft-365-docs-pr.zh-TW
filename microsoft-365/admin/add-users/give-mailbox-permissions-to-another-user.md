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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 提供使用者存取其他使用者信箱的權限，讓使用者讀取及傳送來自其他使用者信箱的電子郵件。
ms.openlocfilehash: 0e5f7b154fa37ae9775e7208574b2a5395e7c239
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634277"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="61e5d-103">將信箱權限授予另一位其他使用者 - 系統管理員說明</span><span class="sxs-lookup"><span data-stu-id="61e5d-103">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="61e5d-p101">身為系統管理員，公司可能會要求您授權部分使用者存取另一個使用者的信箱。例如，您可能會想要授權助理來傳送或讀取直屬主管信箱的電子郵件，或是授權其中一個使用者代理另一個使用者傳送電子郵件。本主題將向您說明如何完成這項作業。</span><span class="sxs-lookup"><span data-stu-id="61e5d-p101">As the admin, you may have company requirements to allow some users access to another user's mailbox. For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user. This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="61e5d-107">如需有關建立及管理共用信箱的資訊，請參閱[建立共用信箱](../email/create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="61e5d-107">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="61e5d-108">想知道如何設定信箱權限嗎？</span><span class="sxs-lookup"><span data-stu-id="61e5d-108">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="61e5d-p102">信箱權限能讓您將某個信箱的讀取/寫入權限授予給另一個使用者。以下文章將協助您設定及使用此功能：</span><span class="sxs-lookup"><span data-stu-id="61e5d-p102">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="61e5d-111">**設定權限：**</span><span class="sxs-lookup"><span data-stu-id="61e5d-111">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="61e5d-p103">設定權限的第一個步驟便是決定您要授權其他使用者可對特定信箱採取的行動。您可以允許使用者讀取信箱中的電子郵件、代理另一個使用者傳送電子郵件，以及以該信箱當作寄件地址傳送電子郵件。請參閱下列文章，了解如何設定各種權限：</span><span class="sxs-lookup"><span data-stu-id="61e5d-p103">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="61e5d-115">讀取另一個使用者信箱中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="61e5d-115">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="61e5d-116">從另一個使用者的信箱傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="61e5d-116">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="61e5d-117">代理另一位使用者傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="61e5d-117">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="61e5d-118">**變更傳播：**</span><span class="sxs-lookup"><span data-stu-id="61e5d-118">**Changing propagation:**</span></span>
  
<span data-ttu-id="61e5d-119">在您設定好權限後，系統需要 60 分鐘的時間，才能在整個系統中傳播並生效變更。</span><span class="sxs-lookup"><span data-stu-id="61e5d-119">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="61e5d-120">**如何運用設定完成的權限：**</span><span class="sxs-lookup"><span data-stu-id="61e5d-120">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="61e5d-p104">當您獲得權限後，您可以透過幾種不同的方式存取信箱。如需相關說明，請參閱下列文章：[存取另一個人的信箱](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)。</span><span class="sxs-lookup"><span data-stu-id="61e5d-p104">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="61e5d-123">權限只能在目前組織租使用者中設定。</span><span class="sxs-lookup"><span data-stu-id="61e5d-123">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="61e5d-124">無法設定租使用者以外的信箱權限。</span><span class="sxs-lookup"><span data-stu-id="61e5d-124">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="61e5d-125">從另一個使用者的信箱傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="61e5d-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="61e5d-126">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="61e5d-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="61e5d-127">選取使用者名稱 (您計畫要賦予傳送權限的使用者)，以開啟其 [屬性] 窗格。</span><span class="sxs-lookup"><span data-stu-id="61e5d-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="61e5d-128">在 **[郵件]** 索引標籤上，選取 **[管理信箱權限]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="61e5d-129">選取 **[傳送為]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="61e5d-130">選取 **[新增權限]**，然後選擇您希望這位使用者能夠以其身分傳送的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="61e5d-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="61e5d-131">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="61e5d-132">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="61e5d-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="61e5d-133">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="61e5d-134">選取 **[傳送為]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="61e5d-135">選取 **[新增權限]**，然後選擇您希望這位使用者能夠以其身分傳送的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="61e5d-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="61e5d-136">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="61e5d-137">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="61e5d-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="61e5d-138">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="61e5d-139">選取 **[傳送為]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="61e5d-140">選取 **[新增權限]**，然後選擇您希望這位使用者能夠以其身分傳送的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="61e5d-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="61e5d-141">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="61e5d-142">讀取另一個使用者信箱中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="61e5d-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="61e5d-143">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="61e5d-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="61e5d-144">選取使用者名稱 (要允許讀取的信箱)，以開啟其 [屬性] 窗格。</span><span class="sxs-lookup"><span data-stu-id="61e5d-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="61e5d-145">在 **[郵件]** 索引標籤上，選取 **[管理信箱權限]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="61e5d-146">選取 **[讀取和管理]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="61e5d-147">選取 **[新增權限]**，然後選擇您想要允許讀取此信箱之電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="61e5d-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="61e5d-148">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-148">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="61e5d-149">當 Exchange 系統管理中心授予時，**讀取** 和 **管理** 權限即為 **完整存取權** 權限。</span><span class="sxs-lookup"><span data-stu-id="61e5d-149">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="61e5d-150">完整存取權權限不會授與 **傳送為** 或 **代理傳送者** 權限。</span><span class="sxs-lookup"><span data-stu-id="61e5d-150">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="61e5d-151">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="61e5d-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="61e5d-152">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-152">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="61e5d-153">選取 **[讀取和管理]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-153">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="61e5d-154">選取 **[新增權限]**，然後選擇您想要允許讀取此信箱之電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="61e5d-154">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="61e5d-155">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-155">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="61e5d-156">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="61e5d-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="61e5d-157">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-157">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="61e5d-158">選取 **[讀取和管理]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-158">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="61e5d-159">選取 **[新增權限]**，然後選擇您想要允許讀取此信箱之電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="61e5d-159">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="61e5d-160">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-160">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="61e5d-161">代理另一個使用者傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="61e5d-161">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="61e5d-162">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="61e5d-162">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="61e5d-163">選取使用者名稱 (您計畫要賦予 **代理傳送** 權限的使用者)，以開啟其 [屬性] 窗格。</span><span class="sxs-lookup"><span data-stu-id="61e5d-163">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="61e5d-164">在 **[郵件]** 索引標籤上，選取 **[管理信箱權限]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-164">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="61e5d-165">選取 **[代理傳送者]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-165">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="61e5d-166">選取 **[新增權限]**，然後選擇您想要允許代理此信箱傳送電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="61e5d-166">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="61e5d-167">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-167">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="61e5d-168">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="61e5d-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="61e5d-169">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-169">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="61e5d-170">選取 **[代理傳送者]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-170">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="61e5d-171">選取 **[新增權限]**，然後選擇您想要允許代理此信箱傳送電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="61e5d-171">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="61e5d-172">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-172">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="61e5d-173">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="61e5d-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="61e5d-174">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-174">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="61e5d-175">選取 **[代理傳送者]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-175">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="61e5d-176">選取 **[新增權限]**，然後選擇您想要允許代理此信箱傳送電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="61e5d-176">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="61e5d-177">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="61e5d-177">Select **Save**.</span></span>

::: moniker-end


## <a name="related-content"></a><span data-ttu-id="61e5d-178">相關內容</span><span class="sxs-lookup"><span data-stu-id="61e5d-178">Related content</span></span>
  
<span data-ttu-id="61e5d-179">[管理其他人的郵件和行事曆項目](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (文章)</span><span class="sxs-lookup"><span data-stu-id="61e5d-179">[Manage another person's mail and calendar items](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (article)\</span></span>   
<span data-ttu-id="61e5d-180">[從另一個使用者或群組傳送電子郵件](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (文章)</span><span class="sxs-lookup"><span data-stu-id="61e5d-180">[Send email from another person or group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (article)\</span></span>
<span data-ttu-id="61e5d-181">[變更使用名稱和電子郵件地址](../add-users/change-a-user-name-and-email-address.md) (影片)</span><span class="sxs-lookup"><span data-stu-id="61e5d-181">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (video)</span></span>

