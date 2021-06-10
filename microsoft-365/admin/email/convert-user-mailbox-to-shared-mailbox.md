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
ms.openlocfilehash: 0beb85e5a69b72bcd244cd654c399e91ded06ba7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635471"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="64bc6-103">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="64bc6-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="64bc6-104">當您將使用者的信箱轉換成共用信箱時，所有的現有電子郵件和行事曆都會保留。</span><span class="sxs-lookup"><span data-stu-id="64bc6-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="64bc6-105">只是在共用信箱中，有好幾個人可以存取，而不是一個人。</span><span class="sxs-lookup"><span data-stu-id="64bc6-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="64bc6-106">在以後的日期，您可以將共用信箱轉換回使用者 (私人) 信箱。</span><span class="sxs-lookup"><span data-stu-id="64bc6-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="64bc6-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="64bc6-107">Before you begin</span></span>

<span data-ttu-id="64bc6-108">**以下是您必須知道的一些重要事項：**</span><span class="sxs-lookup"><span data-stu-id="64bc6-108">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="64bc6-109">您要轉換的使用者信箱必須已獲指派授權，才可將其轉換成共用信箱。</span><span class="sxs-lookup"><span data-stu-id="64bc6-109">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="64bc6-110">否則，您將看不到轉換信箱的選項。</span><span class="sxs-lookup"><span data-stu-id="64bc6-110">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="64bc6-111">如果您已移除授權，請將其新增回來，以便轉換信箱。</span><span class="sxs-lookup"><span data-stu-id="64bc6-111">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="64bc6-112">將信箱轉換成共用信箱之後，您可以從使用者的帳戶中移除授權。</span><span class="sxs-lookup"><span data-stu-id="64bc6-112">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="64bc6-113">共用信箱最多可以有 50 GB 的資料，而不會獲指派授權。</span><span class="sxs-lookup"><span data-stu-id="64bc6-113">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="64bc6-114">若要保留超過該數目的資料，您必須指派授權給它。</span><span class="sxs-lookup"><span data-stu-id="64bc6-114">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="64bc6-115">您可能需要刪除大量的電子郵件 (說，其中包含附件的附件) 從共用信箱壓縮，這樣您就可以移除授權。</span><span class="sxs-lookup"><span data-stu-id="64bc6-115">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="64bc6-116">不要刪除舊的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="64bc6-116">Don't delete the old user's account.</span></span> <span data-ttu-id="64bc6-117">鎖定共用信箱所需。</span><span class="sxs-lookup"><span data-stu-id="64bc6-117">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="64bc6-118">如果您已刪除使用者帳戶，請參閱 [轉換已刪除之使用者的信箱](#convert-the-mailbox-of-a-deleted-user)。</span><span class="sxs-lookup"><span data-stu-id="64bc6-118">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="64bc6-119">在信箱轉換成共用信箱之後，這些規則會完好無損。</span><span class="sxs-lookup"><span data-stu-id="64bc6-119">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="64bc6-120">使用 Exchange 系統管理中心轉換信箱</span><span class="sxs-lookup"><span data-stu-id="64bc6-120">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="64bc6-121">移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="64bc6-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="64bc6-122">選取 **[** 收件者] \> **信箱**。</span><span class="sxs-lookup"><span data-stu-id="64bc6-122">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="64bc6-123">選取使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="64bc6-123">Select the user mailbox.</span></span> <span data-ttu-id="64bc6-124">在 [ **轉換為共用信箱**] 底下，選取 [ **轉換**]。</span><span class="sxs-lookup"><span data-stu-id="64bc6-124">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="64bc6-125">如果信箱小於 50 GB，您可以移除 [使用者的授權](../manage/remove-licenses-from-users.md)，然後停止支付。</span><span class="sxs-lookup"><span data-stu-id="64bc6-125">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="64bc6-126">請勿刪除使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="64bc6-126">Don't delete the user's account.</span></span> <span data-ttu-id="64bc6-127">共用信箱需要以錨定。</span><span class="sxs-lookup"><span data-stu-id="64bc6-127">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="64bc6-128">如果您要轉換的是離開組織之員工的信箱，您應該採取額外的步驟，確定他們無法再登入。</span><span class="sxs-lookup"><span data-stu-id="64bc6-128">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="64bc6-129">請參閱[從 Microsoft 365 中移除前任員工](../add-users/remove-former-employee.md)。</span><span class="sxs-lookup"><span data-stu-id="64bc6-129">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="64bc6-130">在信箱轉換期間，不需要重設使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="64bc6-130">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="64bc6-131">不過，如果沒有重設密碼， **則原始的使用者名稱和密碼** 會在信箱轉換完成之後繼續運作。</span><span class="sxs-lookup"><span data-stu-id="64bc6-131">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="64bc6-132">如需有關共用信箱的其他資訊，請參閱 [關於共用](about-shared-mailboxes.md) 信箱及 [建立共用信箱](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="64bc6-132">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="64bc6-133">共用信箱不需要個別授權。</span><span class="sxs-lookup"><span data-stu-id="64bc6-133">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="64bc6-134">但是，如果您想啟用「就地封存」，或在共用信箱中使用「就地保留」或「訴訟資料暫留」，必須指派具有 Exchange Online 封存功能的 Exchange Online Plan 1 或 Exchange Online Plan 2 授權至信箱。</span><span class="sxs-lookup"><span data-stu-id="64bc6-134">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>

## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="64bc6-135">轉換已刪除使用者的信箱</span><span class="sxs-lookup"><span data-stu-id="64bc6-135">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="64bc6-136">假設您已刪除使用者帳戶，而現在您想要將其舊的信箱轉換成共用信箱。</span><span class="sxs-lookup"><span data-stu-id="64bc6-136">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="64bc6-137">以下是您需要執行的動作：</span><span class="sxs-lookup"><span data-stu-id="64bc6-137">Here's what you need to do:</span></span>

1. <span data-ttu-id="64bc6-138">[還原使用者的帳戶](../add-users/restore-user.md)。</span><span class="sxs-lookup"><span data-stu-id="64bc6-138">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="64bc6-139">請確定已指派 Microsoft 365 授權給它。</span><span class="sxs-lookup"><span data-stu-id="64bc6-139">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="64bc6-140">重設使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="64bc6-140">Reset the user's password.</span></span>
    
4. <span data-ttu-id="64bc6-141">請等候20-30 分鐘，以重新建立其信箱。</span><span class="sxs-lookup"><span data-stu-id="64bc6-141">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="64bc6-142">現在遵循此頁面上的指示，將其信箱轉換成共用信箱。</span><span class="sxs-lookup"><span data-stu-id="64bc6-142">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="64bc6-143">完成後，您可以從使用者的信箱中移除授權。</span><span class="sxs-lookup"><span data-stu-id="64bc6-143">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="64bc6-144">不要刪除使用者的舊信箱。</span><span class="sxs-lookup"><span data-stu-id="64bc6-144">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="64bc6-145">共用信箱需要以錨定。</span><span class="sxs-lookup"><span data-stu-id="64bc6-145">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="64bc6-146">新增成員至共用信箱。</span><span class="sxs-lookup"><span data-stu-id="64bc6-146">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="64bc6-147">將共用信箱轉換回使用者的 (私人) 信箱</span><span class="sxs-lookup"><span data-stu-id="64bc6-147">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="64bc6-148">移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="64bc6-148">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="64bc6-149">選取 **[** 共用收件者] \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="64bc6-149">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="64bc6-150">選取共用信箱。</span><span class="sxs-lookup"><span data-stu-id="64bc6-150">Select the shared mailbox.</span></span> <span data-ttu-id="64bc6-151">在 [ **轉換為一般信箱**] 底下，選取 [ **轉換**]。</span><span class="sxs-lookup"><span data-stu-id="64bc6-151">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="64bc6-152">請回到系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="64bc6-152">Go back to the admin center.</span></span> <span data-ttu-id="64bc6-153">在 [ **使用者**] 底下，選擇與舊共用信箱相關聯的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="64bc6-153">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="64bc6-154">指派授權給帳戶，然後重設密碼。</span><span class="sxs-lookup"><span data-stu-id="64bc6-154">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="64bc6-155">信箱需要幾分鐘的時間才能設定，但是在該之後，將使用該帳戶的人員可以前往。</span><span class="sxs-lookup"><span data-stu-id="64bc6-155">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="64bc6-156">登入時，他們會看到使用於共用信箱中的電子郵件和行事曆專案。</span><span class="sxs-lookup"><span data-stu-id="64bc6-156">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="64bc6-157">轉換使用者在混合式環境中的信箱</span><span class="sxs-lookup"><span data-stu-id="64bc6-157">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="64bc6-158">如需將使用者信箱轉換成 Exchange 混合式環境中共用信箱的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="64bc6-158">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="64bc6-159">在內部部署 Exchange 環境中建立或修改遠端共用信箱的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="64bc6-159">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="64bc6-160">在 Exchange 混合式部署中執行目錄同步作業後，共用信箱意外轉換為使用者信箱</span><span class="sxs-lookup"><span data-stu-id="64bc6-160">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="64bc6-161">如果您是「組織管理」或「收件者管理」角色群組的成員，您可以使用 Exchange 管理命令介面，將使用者信箱變更為內部部署的共用信箱。</span><span class="sxs-lookup"><span data-stu-id="64bc6-161">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="64bc6-162">例如，`Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`。</span><span class="sxs-lookup"><span data-stu-id="64bc6-162">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-content"></a><span data-ttu-id="64bc6-163">相關內容</span><span class="sxs-lookup"><span data-stu-id="64bc6-163">Related content</span></span>

<span data-ttu-id="64bc6-164">[關於共用信箱](about-shared-mailboxes.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="64bc6-164">[About shared mailboxes](about-shared-mailboxes.md) (article)\</span></span>
<span data-ttu-id="64bc6-165">[建立共用信箱](create-a-shared-mailbox.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="64bc6-165">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="64bc6-166">[設定共用信箱](configure-a-shared-mailbox.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="64bc6-166">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)\</span></span>
<span data-ttu-id="64bc6-167">[從共用信箱移除授權](remove-license-from-shared-mailbox.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="64bc6-167">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)\</span></span>
<span data-ttu-id="64bc6-168">[解決共用信箱的問題](resolve-issues-with-shared-mailboxes.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="64bc6-168">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>