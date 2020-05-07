---
title: 還原使用者
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
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: 瞭解如何還原已刪除的使用者帳戶和所有相關聯的資料。
ms.openlocfilehash: 7ac0805024ebf78075a66f77c99496675f20e497
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140564"
---
# <a name="restore-a-user"></a><span data-ttu-id="39590-103">還原使用者</span><span class="sxs-lookup"><span data-stu-id="39590-103">Restore a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="39590-104">系統管理中心變更。</span><span class="sxs-lookup"><span data-stu-id="39590-104">The admin center is changing.</span></span> <span data-ttu-id="39590-105">[！附注] 如果您的經驗不符合這裡所述的詳細資料，請參閱[關於新的 Microsoft 365 系統管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="39590-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
   
<span data-ttu-id="39590-p102">只要在刪除使用者帳戶後的 30 天內還原，該帳戶及其所有相關資料都會全部還原。使用者可以透過相同的公司或學校帳戶登入。信箱的內容會完全還原。若您要查詢某個使用者帳戶還剩多少時間可以還原，[請連絡我們](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="39590-p102">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../contact-support-for-business-products.md).</span></span>
  
<span data-ttu-id="39590-110">以下是幾個祕訣︰</span><span class="sxs-lookup"><span data-stu-id="39590-110">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="39590-111">請確定授權可指派給該帳戶。</span><span class="sxs-lookup"><span data-stu-id="39590-111">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="39590-112">如果貴公司使用 Active Directory，請參閱[如何對 Office 365 中已刪除之使用者帳戶的問題進行疑難排解](https://support.microsoft.com/kb/2619308)，以取得更多關於還原使用者帳戶的說明。</span><span class="sxs-lookup"><span data-stu-id="39590-112">If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](https://support.microsoft.com/kb/2619308) for instructions on restoring a user account.</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="39590-113">若要還原一或多個使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="39590-113">Restore one or more user accounts</span></span>

<span data-ttu-id="39590-114">您必須是 Microsoft 365 全域管理員或使用者管理系統管理員，才可執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="39590-114">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 
  
 
::: moniker range="o365-worldwide"

1. <span data-ttu-id="39590-115">在系統管理中心中，移至 [**使用者** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">刪除的使用者</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="39590-115">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="39590-116">移至 [系統[管理中心](https://go.microsoft.com/fwlink/p/?linkid=848041)]，然後選取 [**使用者** \> **刪除的使用者**]。</span><span class="sxs-lookup"><span data-stu-id="39590-116">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="39590-117">移至 [系統[管理中心](https://go.microsoft.com/fwlink/p/?linkid=850627)]，然後選取 [**使用者** \> **刪除的使用者**]。</span><span class="sxs-lookup"><span data-stu-id="39590-117">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="39590-118">在 [**刪除的使用者**] 頁面上，選取您要還原的使用者名稱，然後選取 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="39590-118">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
 
3. <span data-ttu-id="39590-119">依照提示設定密碼，然後選取 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="39590-119">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="39590-120">若使用者成功還原，請選取 [**傳送電子郵件並關閉**]。</span><span class="sxs-lookup"><span data-stu-id="39590-120">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="39590-121">如果您遇到名稱衝突或 Proxy 位址衝突，請參閱下方說明，了解如何還原這類帳戶。</span><span class="sxs-lookup"><span data-stu-id="39590-121">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="39590-122">還原使用者後，請確定通知他們密碼已變更，並追蹤這些密碼。</span><span class="sxs-lookup"><span data-stu-id="39590-122">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="39590-123">還原有使用者名稱衝突的使用者</span><span class="sxs-lookup"><span data-stu-id="39590-123">Restore a user that has a user name conflict</span></span>
<span data-ttu-id="39590-124"><a name="RestoreUserNameConflict"> </a></span><span class="sxs-lookup"><span data-stu-id="39590-124"><a name="RestoreUserNameConflict"> </a></span></span>

<span data-ttu-id="39590-125">當您刪除使用者帳戶，以相同的使用者名稱建立新的使用者帳戶 (不論是同一名使用者，還是另一名具有類似名稱的使用者)，稍後又試圖還原已刪除的帳戶時，即會發生名稱衝突的情形。</span><span class="sxs-lookup"><span data-stu-id="39590-125">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="39590-p104">若要修正此問題，您可以將您要還原的使用者帳戶取代作用中的使用者帳戶，或是為您要還原的帳戶指派不同的使用者名稱，以避免產生兩個具相同使用者名稱的帳戶。步驟如下：</span><span class="sxs-lookup"><span data-stu-id="39590-p104">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="39590-129">在系統管理中心中，移至 [**使用者** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">刪除的使用者</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="39590-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="39590-130">移至 [系統[管理中心](https://go.microsoft.com/fwlink/p/?linkid=848041)]，然後選取 [**使用者** \> **刪除的使用者**]。</span><span class="sxs-lookup"><span data-stu-id="39590-130">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="39590-131">移至 [系統[管理中心](https://go.microsoft.com/fwlink/p/?linkid=850627)]，然後選取 [**使用者** \> **刪除的使用者**]。</span><span class="sxs-lookup"><span data-stu-id="39590-131">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

  
2. <span data-ttu-id="39590-132">在 [**刪除的使用者**] 頁面上，選取您要還原的使用者名稱，然後選取 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="39590-132">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="39590-p105">若無法還原兩名或多名使用者，一則錯誤訊息會通知您某些使用者的還原作業失敗。請檢視記錄，了解哪些使用者無法順利還原，接著逐一對這些帳戶進行還原作業。</span><span class="sxs-lookup"><span data-stu-id="39590-p105">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="39590-135">依照提示設定密碼，然後選取 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="39590-135">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="39590-p106">隨即會跳出一則訊息，提示您還原帳戶時發生問題。請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="39590-p106">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="39590-p107">取消還原並重新命名目前作用中的使用者，然後再次嘗試還原。</span><span class="sxs-lookup"><span data-stu-id="39590-p107">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="39590-140">或者，輸入使用者的新主要電子郵件地址，然後選取 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="39590-140">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="39590-141">檢查結果，然後選取 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="39590-141">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="39590-142">還原 Proxy 位址衝突的使用者</span><span class="sxs-lookup"><span data-stu-id="39590-142">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="39590-p108">當您刪除包含 Proxy 位址的使用者帳戶、將相同的 Proxy 位址指派給另一個帳戶，然後試圖還原已刪除的帳戶時，會發生 Proxy 位址衝突的情形。請依照下列步驟操作以修正此問題。</span><span class="sxs-lookup"><span data-stu-id="39590-p108">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="39590-145">您必須具有 Microsoft 365 的系統[管理員許可權](about-admin-roles.md)，才可執行此動作。</span><span class="sxs-lookup"><span data-stu-id="39590-145">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="39590-146">在系統管理中心中，移至 [**使用者** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">刪除的使用者</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="39590-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="39590-147">移至 [系統[管理中心](https://go.microsoft.com/fwlink/p/?linkid=848041)]，然後選取 [**使用者** \> **刪除的使用者**]。</span><span class="sxs-lookup"><span data-stu-id="39590-147">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="39590-148">移至 [系統[管理中心](https://go.microsoft.com/fwlink/p/?linkid=850627)]，然後選取 [**使用者** \> **刪除的使用者**]。</span><span class="sxs-lookup"><span data-stu-id="39590-148">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="39590-149">在 [**刪除的使用者**] 頁面上，選取您要還原的使用者，然後選取 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="39590-149">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="39590-150">在 [**還原**] 頁面上，依照指示設定密碼，然後選取 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="39590-150">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="39590-151">所有衝突的 Proxy 位址都會自動從您要還原的使用者移除。</span><span class="sxs-lookup"><span data-stu-id="39590-151">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="39590-152">檢查結果，然後選取 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="39590-152">Review the results, and then select **Close**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="39590-153">相關文章</span><span class="sxs-lookup"><span data-stu-id="39590-153">Related articles</span></span>

[<span data-ttu-id="39590-154">刪除使用者</span><span class="sxs-lookup"><span data-stu-id="39590-154">Delete a user</span></span>](delete-a-user.md)
  
