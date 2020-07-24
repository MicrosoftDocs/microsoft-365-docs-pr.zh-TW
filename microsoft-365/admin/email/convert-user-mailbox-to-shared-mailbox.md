---
title: 將使用者信箱轉換為共用信箱
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '瞭解如何將私人信箱轉換為可供多位使用者存取的共用信箱。 '
ms.openlocfilehash: 7ae00c1d9c901378798f063554a44a3e5b741442
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391527"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="7f091-103">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="7f091-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="7f091-104">當您將使用者的信箱轉換成共用信箱時，所有的現有電子郵件和行事曆都會保留。</span><span class="sxs-lookup"><span data-stu-id="7f091-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="7f091-105">只是在共用信箱中，有好幾個人可以存取，而不是一個人。</span><span class="sxs-lookup"><span data-stu-id="7f091-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="7f091-106">在以後的日期，您可以將共用信箱轉換回使用者（私人）信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="7f091-107">**以下是您必須知道的一些重要事項：**</span><span class="sxs-lookup"><span data-stu-id="7f091-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="7f091-108">您要轉換的使用者信箱必須已獲指派授權，才可將其轉換成共用信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="7f091-109">否則，您將看不到轉換信箱的選項。</span><span class="sxs-lookup"><span data-stu-id="7f091-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="7f091-110">如果您已移除授權，請將其新增回來，以便轉換信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="7f091-111">將信箱轉換成共用信箱之後，您可以從使用者的帳戶中移除授權。</span><span class="sxs-lookup"><span data-stu-id="7f091-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="7f091-112">共用信箱最多可以有50GB 的資料，而不需要指派授權。</span><span class="sxs-lookup"><span data-stu-id="7f091-112">Shared mailboxes can have up to 50GB of data without a license assigned to them.</span></span> <span data-ttu-id="7f091-113">若要保留超過該數目的資料，您必須指派授權給它。</span><span class="sxs-lookup"><span data-stu-id="7f091-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="7f091-114">您可能需要從共用信箱中刪除大量的電子郵件（稱為附件），以將其壓縮，這樣您就可以移除授權。</span><span class="sxs-lookup"><span data-stu-id="7f091-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="7f091-115">不要刪除舊的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7f091-115">Don't delete the old user's account.</span></span> <span data-ttu-id="7f091-116">鎖定共用信箱所需。</span><span class="sxs-lookup"><span data-stu-id="7f091-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="7f091-117">如果您已刪除使用者帳戶，請參閱[轉換已刪除之使用者的信箱](#convert-the-mailbox-of-a-deleted-user)。</span><span class="sxs-lookup"><span data-stu-id="7f091-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="7f091-118">在信箱轉換成共用信箱之後，這些規則會完好無損。</span><span class="sxs-lookup"><span data-stu-id="7f091-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="7f091-119">使用 Exchange 系統管理中心來轉換信箱</span><span class="sxs-lookup"><span data-stu-id="7f091-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="7f091-120">移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="7f091-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="7f091-121">選取 **[** 收件者] \> **信箱**。</span><span class="sxs-lookup"><span data-stu-id="7f091-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="7f091-122">選取使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-122">Select the user mailbox.</span></span> <span data-ttu-id="7f091-123">在 [**轉換為共用信箱**] 底下，選取 [**轉換**]。</span><span class="sxs-lookup"><span data-stu-id="7f091-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="7f091-124">如果信箱小於50GB，您可以移除[使用者的授權](../manage/remove-licenses-from-users.md)，然後停止付款。</span><span class="sxs-lookup"><span data-stu-id="7f091-124">If the mailbox is smaller than 50GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="7f091-125">請勿刪除使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7f091-125">Don't delete the user's account.</span></span> <span data-ttu-id="7f091-126">共用信箱需要以錨定。</span><span class="sxs-lookup"><span data-stu-id="7f091-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="7f091-127">如果您要轉換的是離開組織之員工的信箱，您應該採取額外的步驟，確定他們無法再登入。</span><span class="sxs-lookup"><span data-stu-id="7f091-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="7f091-128">請參閱[從 Microsoft 365 移除前任員工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="7f091-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="7f091-129">如需有關共用信箱的其他資訊，請參閱[關於共用](about-shared-mailboxes.md)信箱及[建立共用信箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="7f091-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="7f091-130">使用 Microsoft 365 admin center 轉換信箱</span><span class="sxs-lookup"><span data-stu-id="7f091-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7f091-131">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="7f091-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="7f091-132">選取您要轉換其信箱的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="7f091-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="7f091-133">重設使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="7f091-133">Reset the user's password.</span></span>

> [!NOTE]
> <span data-ttu-id="7f091-134">在信箱轉換期間，不需要重設使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="7f091-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="7f091-135">不過，如果沒有重設密碼，**則原始的使用者名稱和密碼**會在信箱轉換完成之後繼續運作。</span><span class="sxs-lookup"><span data-stu-id="7f091-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="7f091-136">在 [**郵件**] 索引標籤的 [**其他動作**] 下，選取 [**轉換成共用信箱**]。</span><span class="sxs-lookup"><span data-stu-id="7f091-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7f091-137">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="7f091-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="7f091-138">選取您要轉換其信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="7f091-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="7f091-139">在右窗格中，展開 [**郵件設定**]。</span><span class="sxs-lookup"><span data-stu-id="7f091-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="7f091-140">選取 [**其他設定**] 旁的 [**轉換成共用信箱**]。</span><span class="sxs-lookup"><span data-stu-id="7f091-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7f091-141">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="7f091-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="7f091-142">選取您要轉換其信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="7f091-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="7f091-143">在右窗格中，展開 [**郵件設定**]。</span><span class="sxs-lookup"><span data-stu-id="7f091-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="7f091-144">選取 [**其他設定**] 旁的 [**轉換成共用信箱**]。</span><span class="sxs-lookup"><span data-stu-id="7f091-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="7f091-145">如果信箱小於50GB，您可以[移除使用者的授權](../manage/remove-licenses-from-users.md)，然後停止付款。</span><span class="sxs-lookup"><span data-stu-id="7f091-145">If the mailbox is smaller than 50GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="7f091-146">不要刪除使用者的舊信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="7f091-147">共用信箱需要以錨定。</span><span class="sxs-lookup"><span data-stu-id="7f091-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="7f091-148">如果您要轉換的是離開組織之員工的信箱，您應該採取額外的步驟，確定他們無法再登入。</span><span class="sxs-lookup"><span data-stu-id="7f091-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="7f091-149">請參閱[移除 Microsoft 365 的離職員工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="7f091-149">See [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="7f091-150">如需有關共用信箱的其他資訊，請參閱[關於共用](about-shared-mailboxes.md)信箱及[建立共用信箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="7f091-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7f091-151">共用信箱不需要個別授權。</span><span class="sxs-lookup"><span data-stu-id="7f091-151">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="7f091-152">但是，如果您想啟用「就地封存」，或在共用信箱中使用「就地保留」或「訴訟資料暫留」，必須指派具有 Exchange Online 封存功能的 Exchange Online Plan 1 或 Exchange Online Plan 2 授權至信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-152">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="7f091-153">轉換已刪除使用者的信箱</span><span class="sxs-lookup"><span data-stu-id="7f091-153">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="7f091-154">假設您已刪除使用者帳戶，而現在您想要將其舊的信箱轉換成共用信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-154">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="7f091-155">以下是您需要執行的動作：</span><span class="sxs-lookup"><span data-stu-id="7f091-155">Here's what you need to do:</span></span>

1. <span data-ttu-id="7f091-156">[還原使用者的帳戶](../add-users/restore-user.md)。</span><span class="sxs-lookup"><span data-stu-id="7f091-156">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="7f091-157">請確定已將 Microsoft 365 授權指派給它。</span><span class="sxs-lookup"><span data-stu-id="7f091-157">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="7f091-158">重設使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="7f091-158">Reset the user's password.</span></span>
    
4. <span data-ttu-id="7f091-159">請等候20-30 分鐘，以重新建立其信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-159">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="7f091-160">現在遵循此頁面上的指示，將其信箱轉換成共用信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-160">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="7f091-161">完成後，您可以從使用者的信箱中移除授權。</span><span class="sxs-lookup"><span data-stu-id="7f091-161">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="7f091-162">不要刪除使用者的舊信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-162">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="7f091-163">共用信箱需要以錨定。</span><span class="sxs-lookup"><span data-stu-id="7f091-163">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="7f091-164">新增成員至共用信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-164">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="7f091-165">將共用信箱轉換回使用者的（私人）信箱</span><span class="sxs-lookup"><span data-stu-id="7f091-165">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="7f091-166">移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="7f091-166">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="7f091-167">選取 **[** 共用收件者] \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="7f091-167">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="7f091-168">選取共用信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-168">Select the shared mailbox.</span></span> <span data-ttu-id="7f091-169">在 [**轉換為一般信箱**] 底下，選取 [**轉換**]。</span><span class="sxs-lookup"><span data-stu-id="7f091-169">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="7f091-170">請回到系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="7f091-170">Go back to the admin center.</span></span> <span data-ttu-id="7f091-171">在 [**使用者**] 底下，選擇與舊共用信箱相關聯的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7f091-171">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="7f091-172">指派授權給帳戶，然後重設密碼。</span><span class="sxs-lookup"><span data-stu-id="7f091-172">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="7f091-173">信箱需要幾分鐘的時間才能設定，但是在該之後，將使用該帳戶的人員可以前往。</span><span class="sxs-lookup"><span data-stu-id="7f091-173">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="7f091-174">登入時，他們會看到使用於共用信箱中的電子郵件和行事曆專案。</span><span class="sxs-lookup"><span data-stu-id="7f091-174">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="7f091-175">轉換使用者在混合式環境中的信箱</span><span class="sxs-lookup"><span data-stu-id="7f091-175">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="7f091-176">如果此共用信箱位於混合式環境中，**強烈建議**（幾乎需要！）將使用者信箱移回內部部署，將使用者信箱轉換成共用信箱，然後將共用信箱移回雲端。</span><span class="sxs-lookup"><span data-stu-id="7f091-176">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span>

<span data-ttu-id="7f091-177">原因如下：如果您轉換雲端中的信箱，它可以進行轉換，但是內部部署仍會認為信箱是使用者信箱，因為新的現實不會同步處理回內部部署。</span><span class="sxs-lookup"><span data-stu-id="7f091-177">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="7f091-178">這通常不是問題，但是在某些情況下，內部部署屬性（會認為信箱是使用者信箱）可能會覆寫這些屬性的新雲端版本，因此，信箱可能會轉換回來。</span><span class="sxs-lookup"><span data-stu-id="7f091-178">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="7f091-179">這是一個問題，原因是使用者信箱需要授權 **，或在30天后才會將其虛刪除**！</span><span class="sxs-lookup"><span data-stu-id="7f091-179">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="7f091-180">我們已解決這種情況下的大部分原因，但仍然可以發生，但不常這麼做。</span><span class="sxs-lookup"><span data-stu-id="7f091-180">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="7f091-181">最好是安全的，將信箱移回內部部署。</span><span class="sxs-lookup"><span data-stu-id="7f091-181">It's best to be safe and move the mailbox back to on-premises.</span></span>

> [!NOTE]
> <span data-ttu-id="7f091-182">如果您是組織管理或收件者管理的一部分，您可以使用 Exchange 管理命令介面，將使用者信箱變更為內部部署的共用信箱。</span><span class="sxs-lookup"><span data-stu-id="7f091-182">If you are a part of Organization Management or Recipient Management, you can use the  Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="7f091-183">例如，`Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`。</span><span class="sxs-lookup"><span data-stu-id="7f091-183">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="7f091-184">當[共用信箱意外轉換為使用者信箱](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)時，請參閱此支援解決方案中的解決方法。</span><span class="sxs-lookup"><span data-stu-id="7f091-184">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="7f091-185">相關文章</span><span class="sxs-lookup"><span data-stu-id="7f091-185">Related articles</span></span>

[<span data-ttu-id="7f091-186">關於共用信箱</span><span class="sxs-lookup"><span data-stu-id="7f091-186">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="7f091-187">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="7f091-187">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="7f091-188">設定共用信箱</span><span class="sxs-lookup"><span data-stu-id="7f091-188">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="7f091-189">從共用信箱中移除授權</span><span class="sxs-lookup"><span data-stu-id="7f091-189">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="7f091-190">解決共用信箱的問題</span><span class="sxs-lookup"><span data-stu-id="7f091-190">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
