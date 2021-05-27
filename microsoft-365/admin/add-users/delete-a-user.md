---
title: 刪除貴組織中的使用者
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: 瞭解如何刪除使用者帳戶，以及如何處理使用者的電子郵件和 OneDrive 內容，以及是否要保留產品授權。
ms.openlocfilehash: 43a57a69ce0d810af2b029f49c15d32d75a4dc33
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683136"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="8b19f-103">刪除貴組織中的使用者</span><span class="sxs-lookup"><span data-stu-id="8b19f-103">Delete a user from your organization</span></span>
  
<span data-ttu-id="8b19f-104">**想知道如何刪除您 *自己* 在工作或學校使用的 Microsoft 365 使用者帳戶？請聯繫您工作或學校的技術支援人員，為您執行這些步驟。**</span><span class="sxs-lookup"><span data-stu-id="8b19f-104">**Looking for how to delete your *own* Microsoft 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8b19f-105">開始之前</span><span class="sxs-lookup"><span data-stu-id="8b19f-105">Before you begin</span></span>

- <span data-ttu-id="8b19f-106">只有 Microsoft 365 具有公司或學校之[全域管理員](about-admin-roles.md)或使用者管理許可權的人員才能刪除使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8b19f-106">Only people who have [Microsoft 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span>
- <span data-ttu-id="8b19f-107">在永久刪除使用者資料之前，您有 30 天的期限可以[還原](restore-user.md)帳戶。</span><span class="sxs-lookup"><span data-stu-id="8b19f-107">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span>
- <span data-ttu-id="8b19f-108">如果您想要保留使用者的 OneDrive 資料，請將其移到不同的位置。</span><span class="sxs-lookup"><span data-stu-id="8b19f-108">If you want to keep the user's OneDrive data, move it to a different location.</span></span> <span data-ttu-id="8b19f-109">您甚至可以在刪除帳戶後的30天內移動資料。</span><span class="sxs-lookup"><span data-stu-id="8b19f-109">You can even move the data up to 30 days after deleting the account.</span></span> <span data-ttu-id="8b19f-110">請參閱[存取及備份離職使用者的資料](get-access-to-and-back-up-a-former-user-s-data.md)。</span><span class="sxs-lookup"><span data-stu-id="8b19f-110">See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span> <span data-ttu-id="8b19f-111">您不需要移動他們的 SharePoint 檔案；您仍然可以存取這些檔案。</span><span class="sxs-lookup"><span data-stu-id="8b19f-111">You don't need to move their SharePoint files; you'll still have access to them.</span></span>
- <span data-ttu-id="8b19f-p102">如果您想要保留使用者的電子郵件，請在刪除帳戶 **之前** ，將電子郵件移到不同的位置。如果您已刪除帳戶：如果尚未經過 30 天，則您可以還原帳戶、移動電子郵件資料，然後再刪除帳戶。請參閱 [存取及備份離職使用者的資料](get-access-to-and-back-up-a-former-user-s-data.md) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="8b19f-p102">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
- <span data-ttu-id="8b19f-115">如果您的 Enterprise 訂閱如 Office 365 企業版 E3，您可以將已刪除之使用者帳戶的信箱資料，將其變成非使用中的 *信箱*。</span><span class="sxs-lookup"><span data-stu-id="8b19f-115">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="8b19f-116">To learn more, see [Manage inactive mailboxes in Exchange Online](../../compliance/inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="8b19f-116">To learn more, see [Manage inactive mailboxes in Exchange Online](../../compliance/inactive-mailboxes-in-office-365.md).</span></span>

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="8b19f-117">全域管理員：刪除使用者、停止支付其授權，並選擇要如何處理他們的電子郵件和 OneDrive 內容。</span><span class="sxs-lookup"><span data-stu-id="8b19f-117">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="8b19f-118">如果您是全域系統管理員，當您刪除使用者時，您也可以讓其他使用者存取他們的電子郵件，並選擇要如何處理其 OneDrive 內容。</span><span class="sxs-lookup"><span data-stu-id="8b19f-118">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span>

### <a name="things-to-consider"></a><span data-ttu-id="8b19f-119">考慮事項</span><span class="sxs-lookup"><span data-stu-id="8b19f-119">Things to consider</span></span>

<span data-ttu-id="8b19f-120">開始之前，請先考慮您想要如何處理使用者的電子郵件和 OneDrive 內容，以及您是否要保留授權或停止付款。</span><span class="sxs-lookup"><span data-stu-id="8b19f-120">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|<span data-ttu-id="8b19f-121">項目</span><span class="sxs-lookup"><span data-stu-id="8b19f-121">Item</span></span> | <span data-ttu-id="8b19f-122">描述</span><span class="sxs-lookup"><span data-stu-id="8b19f-122">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="8b19f-123">產品授權</span><span class="sxs-lookup"><span data-stu-id="8b19f-123">Product licenses</span></span>  <br/> |<span data-ttu-id="8b19f-124">您可以從使用者移除授權，並將其從您的訂閱中移除，以停止支付該授權。</span><span class="sxs-lookup"><span data-stu-id="8b19f-124">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="8b19f-125">如果您選取此選項，則會自動從您的訂閱中移除授權。</span><span class="sxs-lookup"><span data-stu-id="8b19f-125">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="8b19f-126">如果您是透過合作夥伴或大量授權購買，**您就無法移除授權**。</span><span class="sxs-lookup"><span data-stu-id="8b19f-126">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="8b19f-127">如果您是支付年度計畫，或是您正在計費週期的中央，您將無法在您的承諾完成之前，從訂閱中移除授權。</span><span class="sxs-lookup"><span data-stu-id="8b19f-127">If you're paying for an annual plan or if you're in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="8b19f-128">OneDrive 內容</span><span class="sxs-lookup"><span data-stu-id="8b19f-128">OneDrive content</span></span>  <br/> |<span data-ttu-id="8b19f-129">如果使用者將其檔案儲存為 OneDrive，您可以授予另一個使用者存取這些檔案的許可權。</span><span class="sxs-lookup"><span data-stu-id="8b19f-129">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="8b19f-130">您必須將想要保留的檔案移至 OneDrive 檔設定的保留期間內。</span><span class="sxs-lookup"><span data-stu-id="8b19f-130">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="8b19f-131">**根據預設，保留期間是30天。**</span><span class="sxs-lookup"><span data-stu-id="8b19f-131">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="8b19f-132">如果您在刪除使用者之後未移動保留期間內的檔案，則會永久刪除 OneDrive 內容。</span><span class="sxs-lookup"><span data-stu-id="8b19f-132">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="8b19f-133">若要增加您為已刪除的帳戶 OneDrive 的檔案保留天數，請參閱[設定已刪除使用者的 OneDrive 保留](/onedrive/set-retention)。</span><span class="sxs-lookup"><span data-stu-id="8b19f-133">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span>  <br/><br/> <span data-ttu-id="8b19f-134">**重要！**</span><span class="sxs-lookup"><span data-stu-id="8b19f-134">**Important!**</span></span> <span data-ttu-id="8b19f-135">如果刪除的使用者使用個人電腦從 SharePoint 和 OneDrive 下載檔案，您就無法在其電腦上擦除儲存的檔案。</span><span class="sxs-lookup"><span data-stu-id="8b19f-135">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="8b19f-136">他們將繼續存取所有從 OneDrive 同步處理的檔案。</span><span class="sxs-lookup"><span data-stu-id="8b19f-136">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="8b19f-137">電子郵件</span><span class="sxs-lookup"><span data-stu-id="8b19f-137">Email</span></span>  <br/> | <span data-ttu-id="8b19f-138">授與另一個使用者對已刪除使用者之電子郵件的存取權，會將刪除的使用者信箱轉換成共用信箱。</span><span class="sxs-lookup"><span data-stu-id="8b19f-138">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="8b19f-139">然後新的信箱擁有者可以存取信箱，並監視新的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8b19f-139">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="8b19f-140">您也會有下列選項：</span><span class="sxs-lookup"><span data-stu-id="8b19f-140">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="8b19f-141">變更顯示名稱-建議您變更顯示名稱，以便在作用中 **使用者** 清單中識別共用信箱。</span><span class="sxs-lookup"><span data-stu-id="8b19f-141">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the **Active users** list.</span></span>  <br/>  <span data-ttu-id="8b19f-142">開啟自動回復-我們已經為您撰寫了禮貌的自動回復。</span><span class="sxs-lookup"><span data-stu-id="8b19f-142">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="8b19f-143">您可以將不同的自動回復傳送給組織內的人員，以及組織外的人員。</span><span class="sxs-lookup"><span data-stu-id="8b19f-143">You can send different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="8b19f-144">清除別名-別名是使用者的其他電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8b19f-144">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="8b19f-145">有些組織並未使用它們，否則您不需要在這裡做任何其他事情。</span><span class="sxs-lookup"><span data-stu-id="8b19f-145">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="8b19f-146">如果使用者確實有別名，我們建議您將其移除，這樣您就可以重複使用這些電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8b19f-146">If the user does have aliases, we recommend removing them so that you can reuse those email addresses.</span></span> <span data-ttu-id="8b19f-147">否則，您無法重複使用這些電子郵件地址，直到已刪除信箱的保留期間已經過去為止。</span><span class="sxs-lookup"><span data-stu-id="8b19f-147">Otherwise, you can't reuse those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="8b19f-148">根據預設，已刪除的信箱可復原30天。</span><span class="sxs-lookup"><span data-stu-id="8b19f-148">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="8b19f-149">如需詳細資訊，請參閱[刪除或還原 Exchange Online 中的使用者信箱](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="8b19f-149">For more information, see  [Delete or restore user mailboxes in Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="8b19f-150">Active Directory</span><span class="sxs-lookup"><span data-stu-id="8b19f-150">Active Directory</span></span>  <br/> |<span data-ttu-id="8b19f-151">如果您的公司使用與 Azure AD 同步處理的 **Active Directory** ，您必須從 Active Directory 中刪除使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8b19f-151">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="8b19f-152">您無法透過 Office 365 執行這個動作。</span><span class="sxs-lookup"><span data-stu-id="8b19f-152">You can't do it through Office 365.</span></span> <span data-ttu-id="8b19f-153">如需相關指示，請參閱 [刪除使用者帳戶](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="8b19f-153">For instructions, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>  <br/> |

### <a name="get-started"></a><span data-ttu-id="8b19f-154">快速入門</span><span class="sxs-lookup"><span data-stu-id="8b19f-154">Get started</span></span>

<span data-ttu-id="8b19f-155">由於引導體驗逐步逐步完成刪除使用者的步驟，以下是如何開始的方式。</span><span class="sxs-lookup"><span data-stu-id="8b19f-155">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8b19f-156">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="8b19f-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="8b19f-157">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="8b19f-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="8b19f-158">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="8b19f-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="8b19f-159">選取您要刪除的使用者，然後選取 [ **刪除使用者**]。</span><span class="sxs-lookup"><span data-stu-id="8b19f-159">Select the user that you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="8b19f-160">使用者管理：從 Office 365 中刪除一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="8b19f-160">User management admin: Delete one or more users from Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b19f-161">如果您已將使用者的帳戶 [轉換成共用信箱](../email/convert-user-mailbox-to-shared-mailbox.md) ，或已設定該帳戶的電子郵件轉寄功能，請勿刪除使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8b19f-161">Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account.</span></span> <span data-ttu-id="8b19f-162">這些函數仍然需要該帳戶。</span><span class="sxs-lookup"><span data-stu-id="8b19f-162">Those functions still need the account.</span></span> <span data-ttu-id="8b19f-163">共用信箱不需要授權。</span><span class="sxs-lookup"><span data-stu-id="8b19f-163">A shared mailbox doesn't require a license.</span></span> <span data-ttu-id="8b19f-164">如果您已將帳戶轉換成共用信箱，您可以 [停止支付授權](#stop-paying-for-the-license)。</span><span class="sxs-lookup"><span data-stu-id="8b19f-164">If you've converted the account to a shared mailbox you can [Stop paying for the license](#stop-paying-for-the-license).</span></span> <span data-ttu-id="8b19f-165">如果您已設定帳戶的電子郵件轉寄功能，您就無法移除授權。</span><span class="sxs-lookup"><span data-stu-id="8b19f-165">If you've set up email forwarding on the account, you can't remove the license.</span></span> <span data-ttu-id="8b19f-166">這樣做會停止電子郵件轉發並停用信箱。</span><span class="sxs-lookup"><span data-stu-id="8b19f-166">Doing so will stop email forwarding and deactivate the mailbox.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="8b19f-167">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="8b19f-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8b19f-168">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="8b19f-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8b19f-169">在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="8b19f-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="8b19f-170">選取您要刪除的使用者名稱，然後選取三個點 () 其他動作]，然後選擇 [  **刪除使用者**]。</span><span class="sxs-lookup"><span data-stu-id="8b19f-170">Select the names of the users that you want to delete, select the three dots (more actions), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="8b19f-171">雖然您已刪除使用者的帳戶，但 **仍在支付授權**。</span><span class="sxs-lookup"><span data-stu-id="8b19f-171">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="8b19f-172">請參閱下一個步驟，以停止支付授權。</span><span class="sxs-lookup"><span data-stu-id="8b19f-172">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="8b19f-173">或者，您可以將授權指派給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="8b19f-173">Or, you can assign the license to another user.</span></span> <span data-ttu-id="8b19f-174">它不會自動指派給某人。</span><span class="sxs-lookup"><span data-stu-id="8b19f-174">It won't be assigned to someone automatically.</span></span>

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="8b19f-175">停止支付授權費用</span><span class="sxs-lookup"><span data-stu-id="8b19f-175">Stop paying for the license</span></span>

<span data-ttu-id="8b19f-176">減少授權數量是一項獨立的步驟，只能由全域系統管理員或計費系統管理員來執行。</span><span class="sxs-lookup"><span data-stu-id="8b19f-176">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="8b19f-177">在系統管理中心，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[您的產品]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="8b19f-177">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8b19f-178">在系統管理中心，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">[您的產品]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="8b19f-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8b19f-179">在系統管理中心，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[您的產品]</a> 頁面。</span><span class="sxs-lookup"><span data-stu-id="8b19f-179">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end

2. <span data-ttu-id="8b19f-180">在 [ **產品** ] 索引標籤上，選取您要移除授權的訂閱。</span><span class="sxs-lookup"><span data-stu-id="8b19f-180">On the **Products** tab, select the subscription that you want to remove licenses for.</span></span>

3. <span data-ttu-id="8b19f-181">在訂閱詳細資料頁面上，選取 **[移除授權]**。</span><span class="sxs-lookup"><span data-stu-id="8b19f-181">On the subscription details page, select **Remove licenses**.</span></span>

4. <span data-ttu-id="8b19f-182">在 [ **移除授權** ] 窗格中的 [ **新數量**] 底下的 [ **授權總數** ] 方塊中，輸入此訂閱所需的授權總數。</span><span class="sxs-lookup"><span data-stu-id="8b19f-182">In the **Remove licenses** pane, under **New quantity**, in the **Total licenses** box, enter the total number of licenses that you want for this subscription.</span></span> <span data-ttu-id="8b19f-183">例如，如果您有100授權，而且想要移除五個，請輸入95。</span><span class="sxs-lookup"><span data-stu-id="8b19f-183">For example, if you have 100 licenses and you want to remove five of them, enter 95.</span></span>

5. <span data-ttu-id="8b19f-184">選取 \*\*\*\*[儲存]。</span><span class="sxs-lookup"><span data-stu-id="8b19f-184">Select **Save**.</span></span>

<span data-ttu-id="8b19f-185">稍後當您執行步驟以將其他人員新增至您的公司時，系統會提示您同時購買授權，只需一個步驟即可！</span><span class="sxs-lookup"><span data-stu-id="8b19f-185">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="8b19f-186">同時刪除多個使用者</span><span class="sxs-lookup"><span data-stu-id="8b19f-186">Delete many users at the same time</span></span>

<span data-ttu-id="8b19f-187">請參閱 [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8b19f-187">See the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="8b19f-188">修正刪除使用者的問題</span><span class="sxs-lookup"><span data-stu-id="8b19f-188">Fix issues with deleting a user</span></span>

<span data-ttu-id="8b19f-189">以下是使用者刪除使用者時遇到的最常見問題：</span><span class="sxs-lookup"><span data-stu-id="8b19f-189">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="8b19f-190">**您會收到錯誤訊息，指出無法刪除使用者行。請稍後再試一次。」**</span><span class="sxs-lookup"><span data-stu-id="8b19f-190">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="8b19f-191">請仔細檢查帳戶是否已設定電子郵件轉寄功能，或是否已轉換成共用信箱。</span><span class="sxs-lookup"><span data-stu-id="8b19f-191">Double-check whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="8b19f-192">這兩種情況都會導致該錯誤。</span><span class="sxs-lookup"><span data-stu-id="8b19f-192">Both of these will cause that error.</span></span> <span data-ttu-id="8b19f-193">若帳戶有電子郵件轉寄或已轉換成共用信箱，請勿刪除帳戶。</span><span class="sxs-lookup"><span data-stu-id="8b19f-193">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="8b19f-194">**您沒有適當的權限可刪除使用者** 。</span><span class="sxs-lookup"><span data-stu-id="8b19f-194">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="8b19f-195">只有[Microsoft 365 全域系統管理員或使用者管理管理員](about-admin-roles.md)可以刪除使用者的人員。</span><span class="sxs-lookup"><span data-stu-id="8b19f-195">Only people who are [Microsoft 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="8b19f-196">這通常需要您的學校或公司提供技術支援。</span><span class="sxs-lookup"><span data-stu-id="8b19f-196">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="8b19f-197">**您刪除了某個使用者，但對方的名稱仍在您的全域通訊錄中出現** 。</span><span class="sxs-lookup"><span data-stu-id="8b19f-197">**You delete the user but their name continues appear in your global address book**.</span></span> <span data-ttu-id="8b19f-198">如果公司使用 Active Directory，就會發生這個問題。</span><span class="sxs-lookup"><span data-stu-id="8b19f-198">This happens when a business is using Active Directory.</span></span> <span data-ttu-id="8b19f-199">您必須刪除 Active Directory 中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8b19f-199">You must delete the users account from Active Directory.</span></span> <span data-ttu-id="8b19f-200">如需相關指示，請參閱 [刪除使用者帳戶。](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="8b19f-200">For instructions, see [Delete a User Account.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span></span>

<span data-ttu-id="8b19f-201">**您想要從您的電腦刪除 Microsoft 365 嗎？移至 [[取消您的訂閱](../../commerce/subscriptions/cancel-your-subscription.md)]。**</span><span class="sxs-lookup"><span data-stu-id="8b19f-201">**Do you want to delete Microsoft 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>

## <a name="related-content"></a><span data-ttu-id="8b19f-202">相關內容</span><span class="sxs-lookup"><span data-stu-id="8b19f-202">Related content</span></span>

<span data-ttu-id="8b19f-203">[還原使用者](restore-user.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="8b19f-203">[Restore a user](restore-user.md) (article)</span></span>\
<span data-ttu-id="8b19f-204">[永久刪除信箱](/exchange/permanently-delete-a-mailbox-exchange-2013-help) (篇) </span><span class="sxs-lookup"><span data-stu-id="8b19f-204">[Permanently delete a mailbox](/exchange/permanently-delete-a-mailbox-exchange-2013-help) (article)</span></span>\
<span data-ttu-id="8b19f-205">[從 Office 365 (文章移除離職員工](remove-former-employee.md)) </span><span class="sxs-lookup"><span data-stu-id="8b19f-205">[Remove a former employee from Office 365](remove-former-employee.md) (article)</span></span>\
<span data-ttu-id="8b19f-206">[將新員工新增至 Office 365](add-new-employee.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="8b19f-206">[Add a new employee to Office 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="8b19f-207">[刪除使用者帳戶](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))：如果您的公司使用與 Azure AD 同步處理的 **Active Directory** ，請使用這些指示。</span><span class="sxs-lookup"><span data-stu-id="8b19f-207">[Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="8b19f-208">您無法透過 Office 365 執行這個動作。</span><span class="sxs-lookup"><span data-stu-id="8b19f-208">You can't do it through Office 365.</span></span> <span data-ttu-id="8b19f-209"> (篇文章) </span><span class="sxs-lookup"><span data-stu-id="8b19f-209">(article)</span></span>