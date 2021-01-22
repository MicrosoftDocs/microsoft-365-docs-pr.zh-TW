---
title: 關於共用信箱
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 當多人需要存取同一個信箱時，會使用共用信箱。 瞭解建立共用信箱之前必須知道哪些資訊。
ms.openlocfilehash: 744c4fece24cf1fa5ee7259a0d722ff123ff2664
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926507"
---
# <a name="about-shared-mailboxes"></a><span data-ttu-id="b7f6b-104">關於共用信箱</span><span class="sxs-lookup"><span data-stu-id="b7f6b-104">About shared mailboxes</span></span>

<span data-ttu-id="b7f6b-105">如果有多個人員需要存取相同信箱 (例如公司資訊或支援電子郵件地址、接待處或其他可能由多人共用的功能)，就會使用共用信箱。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-105">Shared mailboxes are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="b7f6b-106">擁有群組信箱權限的使用者可以以信箱電子郵件地址的身分傳送或代表其傳送 (如果系統管理員已授與使用者執行該動作的權限)。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-106">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="b7f6b-107">這對於說明和支援信箱特別有用，因為使用者可以透過「Contoso 支援」或「大樓 A 接待處」傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-107">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="b7f6b-108">建立 [共用信箱之前](create-a-shared-mailbox.md)，以下是一些您應該瞭解的事：</span><span class="sxs-lookup"><span data-stu-id="b7f6b-108">Before you [create a shared mailbox](create-a-shared-mailbox.md), here are some things you should know:</span></span>

- <span data-ttu-id="b7f6b-109">**授權：** 在不指派授權給共用信箱的情況下，您的共用信箱可以儲存最多 50 GB 的資料。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-109">**Licenses:** Your shared mailbox can store up to 50GB of data without you assigning a license to it.</span></span> <span data-ttu-id="b7f6b-110">超過此上限後，您必須指派授權給信箱才能儲存更多資料。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-110">After that, you need to assign a license to the mailbox to store more data.</span></span> <span data-ttu-id="b7f6b-111">如需共用信箱授權的詳細資訊，請參閱 [Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-111">For more details on shared mailbox licensing, please see [Exchange Online Limits](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits).</span></span> <span data-ttu-id="b7f6b-112">當共用信箱到達儲存上限時，您可以接收電子郵件一段時間，但您將無法傳送新電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-112">When a shared mailbox reaches the storage limit, you'll be able to receive email for a while, but you won't be able to send new email.</span></span> <span data-ttu-id="b7f6b-113">之後，信箱將停止接收電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-113">Then, after that, it will stop receiving email.</span></span> <span data-ttu-id="b7f6b-114">傳送郵件到此信箱的寄件者會收到未傳遞回條。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-114">Senders to the mailbox will get a non-delivery receipt.</span></span>

- <span data-ttu-id="b7f6b-115">**使用者許可權：** 您需要提供使用者共用 (許可權) 共用信箱。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-115">**User permissions:** You need to give users permissions (membership) to use the shared mailbox.</span></span> <span data-ttu-id="b7f6b-116">僅限貴組織內部的人員可以使用共用信箱。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-116">Only people inside your organization can use a shared mailbox.</span></span>

- <span data-ttu-id="b7f6b-117">**外部使用者：** 您無法讓公司外部人員存取您的 (，例如擁有 Gmail 帳戶) 存取您的共用信箱。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-117">**External users:** You can't give people outside your business (such as people with a Gmail account) access to your shared mailbox.</span></span> <span data-ttu-id="b7f6b-118">如果您想這麼做，請考慮改為建立 Outlook 群組。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-118">If you want to do this, consider creating a group for Outlook instead.</span></span> <span data-ttu-id="b7f6b-119">若要深入瞭解，請參閱在系統管理中心建立 [Microsoft 365 群組](../create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-119">To learn more, see [Create a Microsoft 365 group in the admin center](../create-groups/create-groups.md).</span></span>

- <span data-ttu-id="b7f6b-120">**與 Outlook 一同使用：** 除了從瀏覽器使用 Outlook 網頁版存取共用信箱，您也可以使用 iOS 版 Outlook App 或 Android 版 Outlook App。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-120">**Use with Outlook:** In addition to using Outlook on the web from your browser to access shared mailboxes, you can also use the Outlook for iOS app or the Outlook for Android app.</span></span> <span data-ttu-id="b7f6b-121">若要深入瞭解，請參閱[新增共用信箱至 Outlook Mobile。](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f)</span><span class="sxs-lookup"><span data-stu-id="b7f6b-121">To learn more, see [Add a shared mailbox to Outlook mobile](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f).</span></span> <span data-ttu-id="b7f6b-122">另一個選項是建立共用信箱的群組。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-122">Another option is to create a group for your shared mailbox.</span></span> <span data-ttu-id="b7f6b-123">若要深入瞭解，請參閱比較 [群組](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-123">To learn more, see [Compare Groups](../create-groups/compare-groups.md).</span></span>

- <span data-ttu-id="b7f6b-124">**加密：** 無法加密從共用信箱送出的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-124">**Encryption:** You can't encrypt email sent from a shared mailbox.</span></span> <span data-ttu-id="b7f6b-125">這是因為共用信箱沒有自己的安全性內容 (使用者名稱/密碼) 因此無法指派金鑰。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-125">This is because a shared mailbox does not have its own security context (username/password) so it cannot be assigned a key.</span></span> <span data-ttu-id="b7f6b-126">如果有不只一個人是成員，而他們傳送/接收他們以自己的金鑰加密的電子郵件，其他成員也許可以讀取電子郵件，而其他人可能無法讀取，視電子郵件加密的公用金鑰為哪一個。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-126">If more than one person is a member, and they send/receive emails they encrypted with their own keys, other members might be able to read the email and others might not, depending which public key the email was encrypted with.</span></span>

- <span data-ttu-id="b7f6b-127">**信箱轉換：** 您可以將使用者信箱轉換為共用信箱。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-127">**Mailbox conversion:** You can convert user mailboxes to shared mailboxes.</span></span> <span data-ttu-id="b7f6b-128">請參閱[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-128">See [Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span>

- <span data-ttu-id="b7f6b-129">**系統管理員角色：** 擁有全域系統管理員或 Exchange 系統管理員角色的使用者可以建立共用信箱。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-129">**Admin roles:** Users with global admin or Exchange admin roles can create shared mailboxes.</span></span>

- <span data-ttu-id="b7f6b-130">**訂閱需求：** 若要建立共用信箱，您必須訂閱商務用 Microsoft 365 方案，其中包含 Exchange Online (電子郵件) 。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-130">**Subscription requirements:** To create a shared mailbox, you need to subscribe to a Microsoft 365 for business plan that includes email (the Exchange Online service).</span></span> <span data-ttu-id="b7f6b-131">商務用 Microsoft 365 應用程式訂閱不包含電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-131">The Microsoft 365 Apps for business subscription doesn't include email.</span></span> <span data-ttu-id="b7f6b-132">Microsoft 365 商務標準版包含電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-132">Microsoft 365 Business Standard does include email.</span></span>

- <span data-ttu-id="b7f6b-133">**已簽署：** 共用信箱的用意並非由其相關聯的使用者帳戶直接進行登錄。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-133">**Signing in:** A shared mailbox is not intended for direct sign-in by its associated user account.</span></span> <span data-ttu-id="b7f6b-134">您應該一直封鎖共用信箱帳戶的登錄，並且保持封鎖。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-134">You should always block sign-in for the shared mailbox account and keep it blocked.</span></span>

- <span data-ttu-id="b7f6b-135">**太多使用者：** 當同時存取共用信箱的指定使用者過多時，可能會間歇性地無法連接到此信箱。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-135">**Too many users:** When there are too many designated users concurrently accessing a shared mailbox, they may intermittently fail to connect to this mailbox.</span></span> <span data-ttu-id="b7f6b-136">在這種情況下，您可以考慮減少使用者人數，或是使用不同的工作量，例如 Microsoft 365 群組或公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-136">In this case, you can consider reducing the number of the users or using a different workload, such a Microsoft 365 group or Public folder.</span></span>

- <span data-ttu-id="b7f6b-137">**刪除郵件：** 很抱歉，您無法防止人員刪除共用信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-137">**Message deletion:** Unfortunately, you can't prevent people from deleting messages in a shared mailbox.</span></span> <span data-ttu-id="b7f6b-138">解決此問題的唯一方法，就是建立 Microsoft 365 群組，而非共用信箱。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-138">The only way around this is to create a Microsoft 365 group instead of a shared mailbox.</span></span> <span data-ttu-id="b7f6b-139">Outlook 中的群組就像是共用信箱。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-139">A group in Outlook is like a shared mailbox.</span></span> <span data-ttu-id="b7f6b-140">如要比較這兩個群組，請參閱 [比較群組](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-140">For a comparison of the two, see [Compare groups](../create-groups/compare-groups.md).</span></span> <span data-ttu-id="b7f6b-141">若要深入瞭解群組，請參閱深入瞭解 [群組](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。</span><span class="sxs-lookup"><span data-stu-id="b7f6b-141">To learn more about groups, see [Learn more about groups](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="b7f6b-142">相關文章</span><span class="sxs-lookup"><span data-stu-id="b7f6b-142">Related articles</span></span>

[<span data-ttu-id="b7f6b-143">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="b7f6b-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="b7f6b-144">設定共用信箱</span><span class="sxs-lookup"><span data-stu-id="b7f6b-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="b7f6b-145">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="b7f6b-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="b7f6b-146">從共用信箱中移除授權</span><span class="sxs-lookup"><span data-stu-id="b7f6b-146">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="b7f6b-147">解決共用信箱的問題</span><span class="sxs-lookup"><span data-stu-id="b7f6b-147">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
