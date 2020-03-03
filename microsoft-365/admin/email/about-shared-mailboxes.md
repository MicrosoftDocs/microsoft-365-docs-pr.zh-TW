---
title: 關於共用信箱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: 有多人需要存取同一個信箱時，會使用共用的信箱。 了解您需要知道之前建立共用的信箱。
ms.openlocfilehash: 3bb78cc272a1920d9eab92aff50a14e345dce2e1
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362378"
---
# <a name="about-shared-mailboxes"></a><span data-ttu-id="995a0-104">關於共用信箱</span><span class="sxs-lookup"><span data-stu-id="995a0-104">About shared mailboxes</span></span>

<span data-ttu-id="995a0-105">如果有多個人員需要存取相同信箱 (例如公司資訊或支援電子郵件地址、接待處或其他可能由多人共用的功能)，就會使用共用信箱。</span><span class="sxs-lookup"><span data-stu-id="995a0-105">Shared mailboxes are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="995a0-106">擁有群組信箱權限的使用者可以以信箱電子郵件地址的身分傳送或代表其傳送 (如果系統管理員已授與使用者執行該動作的權限)。</span><span class="sxs-lookup"><span data-stu-id="995a0-106">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="995a0-107">這會特別有用的說明和支援的信箱，因為使用者可以傳送電子郵件從 「 Contoso 支援 」 或 「 建置接收 Desk。</span><span class="sxs-lookup"><span data-stu-id="995a0-107">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk.</span></span>

<span data-ttu-id="995a0-108">之前[建立共用的信箱](create-a-shared-mailbox.md)時，以下是您應該要知道的事項。</span><span class="sxs-lookup"><span data-stu-id="995a0-108">Before you [create a shared mailbox](create-a-shared-mailbox.md), here are some things you should know.</span></span>

- <span data-ttu-id="995a0-109">**授權：** 您的共用的信箱可以儲存最多 50GB 的資料，而不會您指派授權給它。</span><span class="sxs-lookup"><span data-stu-id="995a0-109">**Licenses:** Your shared mailbox can store up to 50GB of data without you assigning a license to it.</span></span> <span data-ttu-id="995a0-110">超過此上限後，您必須指派授權給信箱才能儲存更多資料。</span><span class="sxs-lookup"><span data-stu-id="995a0-110">After that, you need to assign a license to the mailbox to store more data.</span></span> <span data-ttu-id="995a0-111">如需共用的信箱授權的詳細資訊，請參閱[Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)。</span><span class="sxs-lookup"><span data-stu-id="995a0-111">For more details on shared mailbox licensing, please see [Exchange Online Limits](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits).</span></span> <span data-ttu-id="995a0-112">當共用信箱到達儲存上限時，您可以接收電子郵件一段時間，但您將無法傳送新電子郵件。</span><span class="sxs-lookup"><span data-stu-id="995a0-112">When a shared mailbox reaches the storage limit, you'll be able to receive email for a while, but you won't be able to send new email.</span></span> <span data-ttu-id="995a0-113">之後，信箱將停止接收電子郵件。</span><span class="sxs-lookup"><span data-stu-id="995a0-113">Then, after that, it will stop receiving email.</span></span> <span data-ttu-id="995a0-114">傳送郵件到此信箱的寄件者會收到未傳遞回條。</span><span class="sxs-lookup"><span data-stu-id="995a0-114">Senders to the mailbox will get a non-delivery receipt.</span></span>

- <span data-ttu-id="995a0-115">**使用者權限：** 您要授與使用共用的信箱的使用者權限 （成員資格）。</span><span class="sxs-lookup"><span data-stu-id="995a0-115">**User permissions:** You need to give users permissions (membership) to use the shared mailbox.</span></span> <span data-ttu-id="995a0-116">僅限貴組織內部的人員可以使用共用信箱。</span><span class="sxs-lookup"><span data-stu-id="995a0-116">Only people inside your organization can use a shared mailbox.</span></span>

- <span data-ttu-id="995a0-117">**外部使用者：** 您不能授與人員外部商務 （例如使用 Gmail 帳戶的人） 存取您的共用信箱。</span><span class="sxs-lookup"><span data-stu-id="995a0-117">**External users:** You can't give people outside your business (such as people with a Gmail account) access to your shared mailbox.</span></span> <span data-ttu-id="995a0-118">如果您想這麼做，請考慮改為建立 Outlook 群組。</span><span class="sxs-lookup"><span data-stu-id="995a0-118">If you want to do this, consider creating a group for Outlook instead.</span></span> <span data-ttu-id="995a0-119">若要深入了解，請參閱[在系統管理中心建立 Office 365 群組](../create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="995a0-119">To learn more, see [Create an Office 365 group in the admin center](../create-groups/create-groups.md).</span></span>

-  <span data-ttu-id="995a0-120">**與 Outlook 搭配使用：** 除了使用從您的瀏覽器網頁型 Outlook 來存取共用的信箱，您也可以使用 Outlook for iOS app 或 Outlook for Android 應用程式。</span><span class="sxs-lookup"><span data-stu-id="995a0-120">**Use with Outlook:** In addition to using Outlook on the web from your browser to access shared mailboxes, you can also use the Outlook for iOS app or the Outlook for Android app.</span></span> <span data-ttu-id="995a0-121">若要了解更多，請參閱<a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">新增至 Outlook 行動裝置共用信箱</a>。</span><span class="sxs-lookup"><span data-stu-id="995a0-121">To learn more, see <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span> <span data-ttu-id="995a0-122">另一個選項是建立您的共用信箱的群組。</span><span class="sxs-lookup"><span data-stu-id="995a0-122">Another option is to create a group for your shared mailbox.</span></span> <span data-ttu-id="995a0-123">若要深入了解，請參閱[比較群組](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="995a0-123">To learn more, see [Compare Groups](../create-groups/compare-groups.md).</span></span>  

- <span data-ttu-id="995a0-124">**加密：** 從共用信箱傳送的電子郵件無法加密。</span><span class="sxs-lookup"><span data-stu-id="995a0-124">**Encryption:** You can't encrypt email sent from a shared mailbox.</span></span> <span data-ttu-id="995a0-125">這是因為共用的信箱不具有自己的安全性內容 （使用者名稱與密碼），讓它不能指定索引鍵。</span><span class="sxs-lookup"><span data-stu-id="995a0-125">This is because a shared mailbox does not have its own security context (username/password) so it cannot be assigned a key.</span></span> <span data-ttu-id="995a0-126">如果一個以上的人員為成員，以及他們傳送/接收電子郵件他們自己的機碼會使用加密、 其他成員可能無法讀取電子郵件和其他人可能不、 哪一個公開金鑰，這取決於電子郵件加密所使用。</span><span class="sxs-lookup"><span data-stu-id="995a0-126">If more than one person is a member, and they send/receive emails they encrypted with their own keys, other members might be able to read the email and others might not, depending which public key the email was encrypted with.</span></span>

- <span data-ttu-id="995a0-127">**信箱轉換：** 您可以將使用者信箱轉換成共用信箱。</span><span class="sxs-lookup"><span data-stu-id="995a0-127">**Mailbox conversion:** You can convert user mailboxes to shared mailboxes.</span></span> <span data-ttu-id="995a0-128">請參閱[將使用者信箱轉換為共用信箱](convert-user-mailbox-to-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="995a0-128">See [Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span>

- <span data-ttu-id="995a0-129">**系統管理員角色：** 使用全域系統管理員或 Exchange 系統管理員角色可以建立的使用者共用信箱。</span><span class="sxs-lookup"><span data-stu-id="995a0-129">**Admin roles:** Users with global admin or Exchange admin roles can create shared mailboxes.</span></span>

- <span data-ttu-id="995a0-130">**訂閱需求：** 若要建立共用的信箱，您需要 Office 365 訂閱包含電子郵件 （Exchange Online 服務） 的商務方案。</span><span class="sxs-lookup"><span data-stu-id="995a0-130">**Subscription requirements:** To create a shared mailbox, you need to subscribe to an Office 365 for business plan that includes email (the Exchange Online service).</span></span> <span data-ttu-id="995a0-131">Office 365 商務版訂閱不包含電子郵件;Office 365 商務進階版會執行。</span><span class="sxs-lookup"><span data-stu-id="995a0-131">The Office 365 Business subscription doesn't include email; Office 365 Business Premium does.</span></span>

- <span data-ttu-id="995a0-132">**登入：** 共用的信箱不適合直接登入其相關聯的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="995a0-132">**Signing in:** A shared mailbox is not intended for direct sign-in by its associated user account.</span></span> <span data-ttu-id="995a0-133">您應該一律封鎖登入共用的信箱帳戶，並保持封鎖。</span><span class="sxs-lookup"><span data-stu-id="995a0-133">You should always block sign-in for the shared mailbox account and keep it blocked.</span></span>

- <span data-ttu-id="995a0-134">**太多的使用者：** 太多指定的使用者，同時存取共用的信箱時，他們可能會間歇性地無法連線到此信箱。</span><span class="sxs-lookup"><span data-stu-id="995a0-134">**Too many users:** When there are too many designated users concurrently accessing a shared mailbox, they may intermittently fail to connect to this mailbox.</span></span> <span data-ttu-id="995a0-135">在此情況下，您可以考慮降低的使用者數目，或使用不同的工作負載，例如 Office 365 群組或公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="995a0-135">In this case, you can consider reducing the number of the users or using a different workload, such as Office 365 group or Public folder.</span></span>

- <span data-ttu-id="995a0-136">**刪除的郵件：** 不幸的是，您無法防止人員刪除共用信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="995a0-136">**Message deletion:** Unfortunately, you can't prevent people from deleting messages in a shared mailbox.</span></span> <span data-ttu-id="995a0-137">此問題的唯一因應措施，便是建立 Office 365 群組來取代共用信箱。</span><span class="sxs-lookup"><span data-stu-id="995a0-137">The only way around this is to create an Office 365 Group instead of a shared mailbox.</span></span> <span data-ttu-id="995a0-138">Outlook 中的群組就像是共用信箱。</span><span class="sxs-lookup"><span data-stu-id="995a0-138">A Group in Outlook is like a shared mailbox.</span></span> <span data-ttu-id="995a0-139">如需兩者的比較，請參閱[比較群組](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="995a0-139">For a comparison of the two, see [Compare Groups](../create-groups/compare-groups.md).</span></span> <span data-ttu-id="995a0-140">若要深入了解群組，請參閱[了解更多關於群組](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)</span><span class="sxs-lookup"><span data-stu-id="995a0-140">To learn more about Groups, see [Learn more about Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)</span></span>

## <a name="related-articles"></a><span data-ttu-id="995a0-141">相關文章</span><span class="sxs-lookup"><span data-stu-id="995a0-141">Related articles</span></span>

[<span data-ttu-id="995a0-142">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="995a0-142">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="995a0-143">設定共用信箱</span><span class="sxs-lookup"><span data-stu-id="995a0-143">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="995a0-144">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="995a0-144">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="995a0-145">從共用信箱中移除授權</span><span class="sxs-lookup"><span data-stu-id="995a0-145">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="995a0-146">解決共用信箱的問題</span><span class="sxs-lookup"><span data-stu-id="995a0-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
