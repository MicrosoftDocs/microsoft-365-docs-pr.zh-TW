---
title: Office 365 群組到期原則
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解 Office 365 群組到期原則。
ms.openlocfilehash: c4c2f7b98247cc81b3fadc561f92084f9bd39c96
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352584"
---
# <a name="office-365-group-expiration-policy"></a><span data-ttu-id="fb133-103">Office 365 群組到期原則</span><span class="sxs-lookup"><span data-stu-id="fb133-103">Office 365 Group Expiration Policy</span></span>

<span data-ttu-id="fb133-104">使用 Office 365 群組的使用量增加，系統管理員和使用者需要方法來清除未使用的群組。</span><span class="sxs-lookup"><span data-stu-id="fb133-104">With the increase in usage of Office 365 Groups, administrators and users need a way to clean up unused groups.</span></span> <span data-ttu-id="fb133-105">從系統移除不在作用中的群組，並讓事情更簡潔，可協助到期原則。</span><span class="sxs-lookup"><span data-stu-id="fb133-105">Expiration policies can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="fb133-106">群組到期時，所有其相關聯的服務 (信箱，規劃中，SharePoint 網站] 等) 也會遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="fb133-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, etc.) are also deleted.</span></span>

<span data-ttu-id="fb133-107">群組到期時，「 虛刪除 」 這表示它仍可復原的最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="fb133-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="fb133-108">系統管理員可以指定到期時間和任何非使用中的群組，抵達陣列結尾的這段時間內，則不會更新，將被刪除。</span><span class="sxs-lookup"><span data-stu-id="fb133-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="fb133-109">建立群組，或依日期它上次更新時，會開始進行到期時間。</span><span class="sxs-lookup"><span data-stu-id="fb133-109">The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="fb133-110">群組擁有者將會自動傳送一封電子郵件，讓他們能更新群組的另一個到期間隔到期之前。</span><span class="sxs-lookup"><span data-stu-id="fb133-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="fb133-111">Microsoft teams 使用者會看到小組的持續性通知。</span><span class="sxs-lookup"><span data-stu-id="fb133-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="fb133-112">目前正在使用中的群組會自動更新。</span><span class="sxs-lookup"><span data-stu-id="fb133-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="fb133-113">任何下列的動作將會自動續約群組：</span><span class="sxs-lookup"><span data-stu-id="fb133-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="fb133-114">SharePoint-檢視、 編輯、 下載、 移動、 共用，或將檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="fb133-114">SharePoint - view, edit, download, move, share, or upload files.</span></span>
- <span data-ttu-id="fb133-115">Outlook-加入群組、 讀取或寫入群組訊息，從群組中，和 like 郵件 （outlook 網頁版）。</span><span class="sxs-lookup"><span data-stu-id="fb133-115">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="fb133-116">Teams-造訪小組通道。</span><span class="sxs-lookup"><span data-stu-id="fb133-116">Teams - visiting a teams channel.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb133-117">當您變更的到期原則時，此服務會重新計算每個群組的到期日。</span><span class="sxs-lookup"><span data-stu-id="fb133-117">When you change the expiration policy, the service recalculates the expiration date for each group.</span></span> <span data-ttu-id="fb133-118">它一律會開始算起群組時已建立，且然後將套用的新的到期原則。</span><span class="sxs-lookup"><span data-stu-id="fb133-118">It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="fb133-119">請務必了解到期預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="fb133-119">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="fb133-120">系統管理員必須啟用其租用戶如果他們想要使用它。</span><span class="sxs-lookup"><span data-stu-id="fb133-120">Administrators will have to enable it for their tenant if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="fb133-121">設定及使用 Office 365 群組的到期原則需要您擁有，但不是一定是將 Azure AD Premium 授權指派的到期原則會套用至其中的所有群組的成員。</span><span class="sxs-lookup"><span data-stu-id="fb133-121">Configuring and using the expiration policy for Office 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="fb133-122">如需詳細資訊，請參閱[開始使用 Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)。</span><span class="sxs-lookup"><span data-stu-id="fb133-122">For more information see [Getting started with Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-office-365-groups-expiration-policy"></a><span data-ttu-id="fb133-123">誰可以設定及使用 Office 365 群組到期原則？</span><span class="sxs-lookup"><span data-stu-id="fb133-123">Who can configure and use the Office 365 Groups expiration policy?</span></span>

|<span data-ttu-id="fb133-124">角色</span><span class="sxs-lookup"><span data-stu-id="fb133-124">Role</span></span>|<span data-ttu-id="fb133-125">他們可以執行的動作</span><span class="sxs-lookup"><span data-stu-id="fb133-125">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="fb133-126">Office 365 全域系統管理員 （Azure，公司系統管理員)，使用者系統管理員</span><span class="sxs-lookup"><span data-stu-id="fb133-126">Office 365 global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="fb133-127">建立、 讀取、 更新或刪除 Office 365 群組到期原則設定。</span><span class="sxs-lookup"><span data-stu-id="fb133-127">Create, read, update, or delete the Office 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="fb133-128">使用者</span><span class="sxs-lookup"><span data-stu-id="fb133-128">User</span></span>|<span data-ttu-id="fb133-129">續約或[還原](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)自己的 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="fb133-129">Renew or [restore](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) an Office 365 Group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="fb133-130">如何設定到期原則</span><span class="sxs-lookup"><span data-stu-id="fb133-130">How to set the expiration policy</span></span>

<span data-ttu-id="fb133-131">如上所述，到期是預設關閉。</span><span class="sxs-lookup"><span data-stu-id="fb133-131">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="fb133-132">系統管理員必須啟用到期原則，並設定它才會生效的屬性。</span><span class="sxs-lookup"><span data-stu-id="fb133-132">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="fb133-133">若要啟用移至**Azure Active Directory (AAD)** > **群組** > **到期**。</span><span class="sxs-lookup"><span data-stu-id="fb133-133">To enable it go to **Azure Active Directory (AAD)** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="fb133-134">您可以在這裡設定預設群組存留時間，並指定多久要移至群組擁有者的第一個及第二個過期通知。</span><span class="sxs-lookup"><span data-stu-id="fb133-134">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="fb133-135">群組存留期指定天內，且可以設為 180，365 或您指定自訂值。</span><span class="sxs-lookup"><span data-stu-id="fb133-135">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="fb133-136">自訂的值必須設為至少 30 天。</span><span class="sxs-lookup"><span data-stu-id="fb133-136">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="fb133-137">如果群組沒有擁有者的電子郵件會移至指定的系統管理員的到期時間。</span><span class="sxs-lookup"><span data-stu-id="fb133-137">If the group does not have an owner the expiration emails will go to a specified administrator.</span></span>

<span data-ttu-id="fb133-138">您可以將原則設定的所有群組，僅選取群組，或將它關閉完全藉由選取 [**無**。</span><span class="sxs-lookup"><span data-stu-id="fb133-138">You can set the policy for all of your groups, only selected groups, or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="fb133-139">請注意，目前您不能有不同的群組不同的原則。</span><span class="sxs-lookup"><span data-stu-id="fb133-139">Note that currently you can't have different policies for different groups.</span></span>

![在 Azure Active Directory 中的螢幕擷取畫面的群組到期日設定](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a><span data-ttu-id="fb133-141">到期與保留原則的運作方式</span><span class="sxs-lookup"><span data-stu-id="fb133-141">How expiry works with the retention policy</span></span>

<span data-ttu-id="fb133-142">如果您有設定保留原則中群組的安全性與合規性中心，到期原則的運作順暢地與保留原則。</span><span class="sxs-lookup"><span data-stu-id="fb133-142">If you have setup retention policy in Security and Compliance center for groups, expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="fb133-143">群組過期時，在 [郵件] 方塊中的群組交談和群組網站中的檔案會保留在 [保留] 容器中保留原則中定義特定天數。</span><span class="sxs-lookup"><span data-stu-id="fb133-143">When a group expires, the group's conversations in mail box and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="fb133-144">使用者不會看到群組中或其內容之後到期, 不過。</span><span class="sxs-lookup"><span data-stu-id="fb133-144">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a><span data-ttu-id="fb133-145">如何及何時群組擁有者可學習是否其群組即將到期</span><span class="sxs-lookup"><span data-stu-id="fb133-145">How and when a Group owner learns if their Groups are going to expire</span></span>

<span data-ttu-id="fb133-146">群組擁有者只會透過電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="fb133-146">Group owners will only be notified via email.</span></span> <span data-ttu-id="fb133-147">如果透過 Planner、 SharePoint 或任何其他應用程式已建立的群組，過期通知永遠都將透過電子郵件。</span><span class="sxs-lookup"><span data-stu-id="fb133-147">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="fb133-148">如果透過小組已建立的群組，群組擁有者會收到通知，以續約透過 [活動] 區段中。</span><span class="sxs-lookup"><span data-stu-id="fb133-148">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="fb133-149">不建議您啟用群組上的到期日，如果群組擁有者都不會有有效的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="fb133-149">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="fb133-150">30 天前群組到期時，群組擁有者 （或您所指定的群組，不需要擁有者的電子郵件地址） 將會收到一封電子郵件，讓使用者能輕鬆地更新群組。</span><span class="sxs-lookup"><span data-stu-id="fb133-150">30 days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="fb133-151">如果他們不更新它，就會收到其他更新電子郵件過期前的 15 天。</span><span class="sxs-lookup"><span data-stu-id="fb133-151">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="fb133-152">如果他們仍尚未更新它，他們會收到一個多個電子郵件通知密碼到期前一天。</span><span class="sxs-lookup"><span data-stu-id="fb133-152">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span>

<span data-ttu-id="fb133-153">如果基於某個原因而沒有任何一個擁有者或系統管理員會更新群組到期之前，系統管理員仍可還原該群組最多 30 天之後到期。</span><span class="sxs-lookup"><span data-stu-id="fb133-153">If for some reason none of the owners or admins renew the group before it expires, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="fb133-154">如需詳細資訊，請參閱：[還原已刪除的 Office 365 群組](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)。</span><span class="sxs-lookup"><span data-stu-id="fb133-154">For details see: [Restore a deleted Office 365 Group](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).</span></span>

## <a name="related-articles"></a><span data-ttu-id="fb133-155">相關文章</span><span class="sxs-lookup"><span data-stu-id="fb133-155">Related articles</span></span>

[<span data-ttu-id="fb133-156">保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="fb133-156">Overview of retention policies</span></span>](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[<span data-ttu-id="fb133-157">指派新擁有者給孤立的群組</span><span class="sxs-lookup"><span data-stu-id="fb133-157">Assign a new owner to an orphaned group</span></span>](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[<span data-ttu-id="fb133-158">設定 Office 365 群組到期日</span><span class="sxs-lookup"><span data-stu-id="fb133-158">Configure Office 365 groups expiration</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
