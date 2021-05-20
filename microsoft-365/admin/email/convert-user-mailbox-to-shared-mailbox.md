---
title: 將使用者信箱轉換為共用信箱
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '瞭解如何將私人信箱轉換為可由數個人員存取的共用信箱，而不只是一個人。 '
ms.openlocfilehash: 73e2bad40037e1343f4e08c07ca6b26df16b1a30
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537616"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="16e1f-103">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="16e1f-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="16e1f-104">當您將使用者的信箱轉換成共用信箱時，所有的現有電子郵件和行事曆都會保留。</span><span class="sxs-lookup"><span data-stu-id="16e1f-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="16e1f-105">只是在共用信箱中，有好幾個人可以存取，而不是一個人。</span><span class="sxs-lookup"><span data-stu-id="16e1f-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="16e1f-106">在以後的日期，您可以將共用信箱轉換回使用者 (私人) 信箱。</span><span class="sxs-lookup"><span data-stu-id="16e1f-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="16e1f-107">**以下是您必須知道的一些重要事項：**</span><span class="sxs-lookup"><span data-stu-id="16e1f-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="16e1f-108">您要轉換的使用者信箱必須已獲指派授權，才可將其轉換成共用信箱。</span><span class="sxs-lookup"><span data-stu-id="16e1f-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="16e1f-109">否則，您將看不到轉換信箱的選項。</span><span class="sxs-lookup"><span data-stu-id="16e1f-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="16e1f-110">如果您已移除授權，請將其新增回來，以便轉換信箱。</span><span class="sxs-lookup"><span data-stu-id="16e1f-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="16e1f-111">將信箱轉換成共用信箱之後，您可以從使用者的帳戶中移除授權。</span><span class="sxs-lookup"><span data-stu-id="16e1f-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="16e1f-112">共用信箱最多可以有 50 GB 的資料，而不會獲指派授權。</span><span class="sxs-lookup"><span data-stu-id="16e1f-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="16e1f-113">若要保留超過該數目的資料，您必須指派授權給它。</span><span class="sxs-lookup"><span data-stu-id="16e1f-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="16e1f-114">您可能需要刪除大量的電子郵件 (說，其中包含附件的附件) 從共用信箱壓縮，這樣您就可以移除授權。</span><span class="sxs-lookup"><span data-stu-id="16e1f-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="16e1f-115">不要刪除舊的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="16e1f-115">Don't delete the old user's account.</span></span> <span data-ttu-id="16e1f-116">鎖定共用信箱所需。</span><span class="sxs-lookup"><span data-stu-id="16e1f-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="16e1f-117">如果您已刪除使用者帳戶，請參閱 [轉換已刪除之使用者的信箱](#convert-the-mailbox-of-a-deleted-user)。</span><span class="sxs-lookup"><span data-stu-id="16e1f-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="16e1f-118">在信箱轉換成共用信箱之後，這些規則會完好無損。</span><span class="sxs-lookup"><span data-stu-id="16e1f-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="16e1f-119">使用 Exchange 系統管理中心轉換信箱</span><span class="sxs-lookup"><span data-stu-id="16e1f-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="16e1f-120">移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="16e1f-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="16e1f-121">選取 **[** 收件者] \> **信箱**。</span><span class="sxs-lookup"><span data-stu-id="16e1f-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="16e1f-122">選取使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="16e1f-122">Select the user mailbox.</span></span> <span data-ttu-id="16e1f-123">在 [ **轉換為共用信箱**] 底下，選取 [ **轉換**]。</span><span class="sxs-lookup"><span data-stu-id="16e1f-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="16e1f-124">如果信箱小於 50 GB，您可以移除 [使用者的授權](../manage/remove-licenses-from-users.md)，然後停止支付。</span><span class="sxs-lookup"><span data-stu-id="16e1f-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="16e1f-125">請勿刪除使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="16e1f-125">Don't delete the user's account.</span></span> <span data-ttu-id="16e1f-126">共用信箱需要以錨定。</span><span class="sxs-lookup"><span data-stu-id="16e1f-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="16e1f-127">如果您要轉換的是離開組織之員工的信箱，您應該採取額外的步驟，確定他們無法再登入。</span><span class="sxs-lookup"><span data-stu-id="16e1f-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="16e1f-128">請參閱[從 Microsoft 365 中移除前任員工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="16e1f-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="16e1f-129">在信箱轉換期間，不需要重設使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="16e1f-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="16e1f-130">不過，如果沒有重設密碼， **則原始的使用者名稱和密碼** 會在信箱轉換完成之後繼續運作。</span><span class="sxs-lookup"><span data-stu-id="16e1f-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="16e1f-131">如需有關共用信箱的其他資訊，請參閱 [關於共用](about-shared-mailboxes.md) 信箱及 [建立共用信箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="16e1f-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="16e1f-132">共用信箱不需要個別授權。</span><span class="sxs-lookup"><span data-stu-id="16e1f-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="16e1f-133">但是，如果您想啟用「就地封存」，或在共用信箱中使用「就地保留」或「訴訟資料暫留」，必須指派具有 Exchange Online 封存功能的 Exchange Online Plan 1 或 Exchange Online Plan 2 授權至信箱。</span><span class="sxs-lookup"><span data-stu-id="16e1f-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="16e1f-134">轉換已刪除使用者的信箱</span><span class="sxs-lookup"><span data-stu-id="16e1f-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="16e1f-135">假設您已刪除使用者帳戶，而現在您想要將其舊的信箱轉換成共用信箱。</span><span class="sxs-lookup"><span data-stu-id="16e1f-135">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="16e1f-136">以下是您需要執行的動作：</span><span class="sxs-lookup"><span data-stu-id="16e1f-136">Here's what you need to do:</span></span>

1. <span data-ttu-id="16e1f-137">[還原使用者的帳戶](../add-users/restore-user.md)。</span><span class="sxs-lookup"><span data-stu-id="16e1f-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="16e1f-138">請確定已指派 Microsoft 365 授權給它。</span><span class="sxs-lookup"><span data-stu-id="16e1f-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="16e1f-139">重設使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="16e1f-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="16e1f-140">請等候20-30 分鐘，以重新建立其信箱。</span><span class="sxs-lookup"><span data-stu-id="16e1f-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="16e1f-141">現在遵循此頁面上的指示，將其信箱轉換成共用信箱。</span><span class="sxs-lookup"><span data-stu-id="16e1f-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="16e1f-142">完成後，您可以從使用者的信箱中移除授權。</span><span class="sxs-lookup"><span data-stu-id="16e1f-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="16e1f-143">不要刪除使用者的舊信箱。</span><span class="sxs-lookup"><span data-stu-id="16e1f-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="16e1f-144">共用信箱需要以錨定。</span><span class="sxs-lookup"><span data-stu-id="16e1f-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="16e1f-145">新增成員至共用信箱。</span><span class="sxs-lookup"><span data-stu-id="16e1f-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="16e1f-146">將共用信箱轉換回使用者的 (私人) 信箱</span><span class="sxs-lookup"><span data-stu-id="16e1f-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="16e1f-147">移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="16e1f-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="16e1f-148">選取 **[** 共用收件者] \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16e1f-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="16e1f-149">選取共用信箱。</span><span class="sxs-lookup"><span data-stu-id="16e1f-149">Select the shared mailbox.</span></span> <span data-ttu-id="16e1f-150">在 [ **轉換為一般信箱**] 底下，選取 [ **轉換**]。</span><span class="sxs-lookup"><span data-stu-id="16e1f-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="16e1f-151">請回到系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="16e1f-151">Go back to the admin center.</span></span> <span data-ttu-id="16e1f-152">在 [ **使用者**] 底下，選擇與舊共用信箱相關聯的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="16e1f-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="16e1f-153">指派授權給帳戶，然後重設密碼。</span><span class="sxs-lookup"><span data-stu-id="16e1f-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="16e1f-154">信箱需要幾分鐘的時間才能設定，但是在該之後，將使用該帳戶的人員可以前往。</span><span class="sxs-lookup"><span data-stu-id="16e1f-154">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="16e1f-155">登入時，他們會看到使用於共用信箱中的電子郵件和行事曆專案。</span><span class="sxs-lookup"><span data-stu-id="16e1f-155">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="16e1f-156">轉換使用者在混合式環境中的信箱</span><span class="sxs-lookup"><span data-stu-id="16e1f-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="16e1f-157">如需將使用者信箱轉換成 Exchange 混合式環境中共用信箱的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="16e1f-157">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="16e1f-158">在內部部署 Exchange 環境中建立或修改遠端共用信箱的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="16e1f-158">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="16e1f-159">在 Exchange 混合式部署中執行目錄同步作業後，共用信箱意外轉換為使用者信箱</span><span class="sxs-lookup"><span data-stu-id="16e1f-159">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="16e1f-160">如果您是「組織管理」或「收件者管理」角色群組的成員，您可以使用 Exchange 管理命令介面，將使用者信箱變更為內部部署的共用信箱。</span><span class="sxs-lookup"><span data-stu-id="16e1f-160">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="16e1f-161">例如，`Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`。</span><span class="sxs-lookup"><span data-stu-id="16e1f-161">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-content"></a><span data-ttu-id="16e1f-162">相關內容</span><span class="sxs-lookup"><span data-stu-id="16e1f-162">Related content</span></span>

<span data-ttu-id="16e1f-163">[關於共用信箱](about-shared-mailboxes.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="16e1f-163">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>

<span data-ttu-id="16e1f-164">[建立共用信箱](create-a-shared-mailbox.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="16e1f-164">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="16e1f-165"> (文章) [設定共用信箱](configure-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="16e1f-165">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="16e1f-166">[從共用信箱中移除授權](remove-license-from-shared-mailbox.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="16e1f-166">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="16e1f-167">[解決共用信箱](resolve-issues-with-shared-mailboxes.md) (文章) 的問題</span><span class="sxs-lookup"><span data-stu-id="16e1f-167">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>