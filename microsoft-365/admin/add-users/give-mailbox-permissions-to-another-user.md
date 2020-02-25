---
title: 授予信箱的權限給 Office 365 中的另一個使用者 - 系統管理說明
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: '瞭解如何授予使用者存取另一個使用者信箱的權限。 這可讓使用者從其他使用者的信箱讀取郵件及傳送郵件。 '
ms.openlocfilehash: 8c3572cf543545de4a2825012f6c2e8e906cd8dd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239374"
---
# <a name="give-mailbox-permissions-to-another-user-in-office-365---admin-help"></a><span data-ttu-id="d8472-104">授予信箱的權限給 Office 365 中的另一個使用者 - 系統管理說明</span><span class="sxs-lookup"><span data-stu-id="d8472-104">Give mailbox permissions to another user in Office 365 - Admin Help</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="d8472-105">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="d8472-105">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="d8472-106">身為系統管理員，公司可能會要求您授權部分使用者存取另一個使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="d8472-106">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="d8472-107">例如，您可能會想要授權助理來傳送或讀取直屬主管信箱的電子郵件，或是授權其中一個使用者代理另一個使用者傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d8472-107">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="d8472-108">本主題將向您說明如何完成這項作業。</span><span class="sxs-lookup"><span data-stu-id="d8472-108">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="d8472-109">如需有關建立及管理共用信箱的資訊，請參閱[建立共用信箱](../email/create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="d8472-109">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="d8472-110">想知道如何設定信箱權限嗎？</span><span class="sxs-lookup"><span data-stu-id="d8472-110">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="d8472-p103">信箱權限能讓您將某個信箱的讀取/寫入權限授予給另一個使用者。以下文章將協助您設定及使用此功能：</span><span class="sxs-lookup"><span data-stu-id="d8472-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="d8472-113">**設定權限：**</span><span class="sxs-lookup"><span data-stu-id="d8472-113">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="d8472-p104">設定權限的第一個步驟便是決定您要授權其他使用者可對特定信箱採取的行動。您可以允許使用者讀取信箱中的電子郵件、代理另一個使用者傳送電子郵件，以及以該信箱當作寄件地址傳送電子郵件。請參閱下列文章，了解如何設定各種權限：</span><span class="sxs-lookup"><span data-stu-id="d8472-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="d8472-117">讀取另一個使用者信箱中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="d8472-117">Read email from another user's mailbox</span></span>](https://support.office.com/article/Read-email-from-another-user-s-mailbox-in-Office-365-cb3b6a8a-c6e8-4342-803c-3e54b6428cc2?#bkmk_reademailanotheruser)
    
- [<span data-ttu-id="d8472-118">從另一個使用者的信箱傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="d8472-118">Send email from another user's mailbox</span></span>](https://support.office.com/article/Send-email-from-another-user-s-mailbox-in-Office-365-2B828C5F-41AB-4904-97B9-3B63D8129C4E?#bkmk_sendemailanotheruser)
    
- [<span data-ttu-id="d8472-119">代理另一個使用者傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="d8472-119">Send email on behalf of a user</span></span>](https://support.office.com/article/Send-email-on-behalf-of-another-user-in-Office-365-C5E7749D-244E-477F-998E-55D3876C22EC?#bkmk_sendbehalflanotheruser)
    
 <span data-ttu-id="d8472-120">**變更傳播：**</span><span class="sxs-lookup"><span data-stu-id="d8472-120">**Changing propagation:**</span></span>
  
<span data-ttu-id="d8472-121">在您設定好權限後，系統需要 60 分鐘的時間，才能在整個系統中傳播並生效變更。</span><span class="sxs-lookup"><span data-stu-id="d8472-121">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="d8472-122">**如何運用設定完成的權限：**</span><span class="sxs-lookup"><span data-stu-id="d8472-122">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="d8472-p105">當您獲得權限後，您可以透過幾種不同的方式存取信箱。如需相關說明，請參閱下列文章：[存取另一個人的信箱](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span><span class="sxs-lookup"><span data-stu-id="d8472-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="d8472-125">從另一個使用者的信箱傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="d8472-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d8472-126">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="d8472-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="d8472-127">選取使用者名稱 (您計畫要賦予傳送權限的使用者)，以開啟其 [屬性] 窗格。</span><span class="sxs-lookup"><span data-stu-id="d8472-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="d8472-128">在 **[郵件]** 索引標籤上，選取 **[管理信箱權限]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="d8472-129">選取 **[傳送為]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="d8472-130">選取 **[新增權限]**，然後選擇您希望這位使用者能夠以其身分傳送的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="d8472-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="d8472-131">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d8472-132">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="d8472-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="d8472-133">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="d8472-134">選取 **[傳送為]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="d8472-135">選取 **[新增權限]**，然後選擇您希望這位使用者能夠以其身分傳送的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="d8472-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="d8472-136">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d8472-137">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="d8472-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="d8472-138">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="d8472-139">選取 **[傳送為]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="d8472-140">選取 **[新增權限]**，然後選擇您希望這位使用者能夠以其身分傳送的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="d8472-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="d8472-141">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="d8472-142">讀取另一個使用者信箱中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="d8472-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d8472-143">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="d8472-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="d8472-144">選取使用者名稱 (要允許讀取的信箱)，以開啟其 [屬性] 窗格。</span><span class="sxs-lookup"><span data-stu-id="d8472-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="d8472-145">在 **[郵件]** 索引標籤上，選取 **[管理信箱權限]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="d8472-146">選取 **[讀取和管理]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="d8472-147">選取 **[新增權限]**，然後選擇您想要允許讀取此信箱之電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="d8472-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="d8472-148">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-148">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d8472-149">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="d8472-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="d8472-150">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-150">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="d8472-151">選取 **[讀取和管理]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-151">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="d8472-152">選取 **[新增權限]**，然後選擇您想要允許讀取此信箱之電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="d8472-152">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="d8472-153">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-153">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d8472-154">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="d8472-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="d8472-155">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-155">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="d8472-156">選取 **[讀取和管理]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-156">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="d8472-157">選取 **[新增權限]**，然後選擇您想要允許讀取此信箱之電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="d8472-157">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="d8472-158">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-158">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="d8472-159">代理另一個使用者傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="d8472-159">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d8472-160">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="d8472-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="d8472-161">選取使用者名稱 (您計畫要賦予**代理傳送**權限的使用者)，以開啟其 [屬性] 窗格。</span><span class="sxs-lookup"><span data-stu-id="d8472-161">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="d8472-162">在 **[郵件]** 索引標籤上，選取 **[管理信箱權限]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-162">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="d8472-163">選取 **[代理傳送者]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-163">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="d8472-164">選取 **[新增權限]**，然後選擇您想要允許代理此信箱傳送電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="d8472-164">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="d8472-165">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-165">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d8472-166">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="d8472-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="d8472-167">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-167">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="d8472-168">選取 **[代理傳送者]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-168">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="d8472-169">選取 **[新增權限]**，然後選擇您想要允許代理此信箱傳送電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="d8472-169">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="d8472-170">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-170">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d8472-171">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">作用中使用者</a>頁面。</span><span class="sxs-lookup"><span data-stu-id="d8472-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="d8472-172">選取您要的使用者，展開 **[郵件設定]**，然後選取 **[信箱權限]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-172">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="d8472-173">選取 **[代理傳送者]** 旁邊的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-173">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="d8472-174">選取 **[新增權限]**，然後選擇您想要允許代理此信箱傳送電子郵件的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="d8472-174">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="d8472-175">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d8472-175">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="d8472-176">從 Outlook 和商務用 Outlook 網頁版傳送及讀取郵件</span><span class="sxs-lookup"><span data-stu-id="d8472-176">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="d8472-p106">想知道如何從另一個使用者的信箱傳送電子郵件嗎？請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="d8472-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="d8472-179">管理其他人的郵件和行事曆項目</span><span class="sxs-lookup"><span data-stu-id="d8472-179">Manage another person's mail and calendar items</span></span>](https://support.office.com/article/afb79d6b-2967-43b9-a944-a6b953190af5.aspx)
    
- [<span data-ttu-id="d8472-180">從另一個使用者或群組傳送電子郵件</span><span class="sxs-lookup"><span data-stu-id="d8472-180">Send email from another person or group</span></span>](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)
