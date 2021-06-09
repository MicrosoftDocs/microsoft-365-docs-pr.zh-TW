---
title: Microsoft 365 群組到期原則
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
recommendations: false
description: 深入瞭解 Microsoft 365 群組到期原則。
ms.openlocfilehash: 90807d6c178061804e64db4440af42050a1d8e77
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530847"
---
# <a name="microsoft-365-group-expiration-policy"></a><span data-ttu-id="72cc5-103">Microsoft 365 群組到期原則</span><span class="sxs-lookup"><span data-stu-id="72cc5-103">Microsoft 365 group expiration policy</span></span>

<span data-ttu-id="72cc5-104">隨著 Microsoft 365 群組和 Microsoft Teams 的使用量增加，管理員和使用者需要一種方式來清除未使用的群組和團隊。</span><span class="sxs-lookup"><span data-stu-id="72cc5-104">With the increase in usage of Microsoft 365 groups and Microsoft Teams, administrators and users need a way to clean up unused groups and teams.</span></span> <span data-ttu-id="72cc5-105">Microsoft 365 群組到期原則可協助從系統中移除非使用中的群組，並使事情更整潔。</span><span class="sxs-lookup"><span data-stu-id="72cc5-105">A Microsoft 365 groups expiration policy can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="72cc5-106">當群組到期時，其相關聯的所有服務 (信箱、Planner、SharePoint 網站、小組等 ) 也會被刪除。</span><span class="sxs-lookup"><span data-stu-id="72cc5-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, team, etc.) are also deleted.</span></span>

<span data-ttu-id="72cc5-107">當群組到期時，它會「虛刪除」，表示它仍可復原30天。</span><span class="sxs-lookup"><span data-stu-id="72cc5-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="72cc5-108">管理員可以指定到期期限及任何非作用中的群組，只要到達該期間結束，也不會被更新，將會被刪除。</span><span class="sxs-lookup"><span data-stu-id="72cc5-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="72cc5-109"> (這包括已封存的團隊。 ) 到期期間會在建立群組時或在最後一次更新的日期時開始。</span><span class="sxs-lookup"><span data-stu-id="72cc5-109">(This includes archived teams.) The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="72cc5-110">在到期之前，系統會自動將電子郵件傳送給群組擁有者，以允許使用者在其他到期間隔內更新群組。</span><span class="sxs-lookup"><span data-stu-id="72cc5-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="72cc5-111">Teams 使用者會在 Teams 中看到持續通知。</span><span class="sxs-lookup"><span data-stu-id="72cc5-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="72cc5-112">主動使用中的群組會自動更新。</span><span class="sxs-lookup"><span data-stu-id="72cc5-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="72cc5-113">下列任何動作都會自動更新群組：</span><span class="sxs-lookup"><span data-stu-id="72cc5-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="72cc5-114">SharePoint-查看、編輯、下載、移動、共用或上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="72cc5-114">SharePoint - view, edit, download, move, share, or upload files.</span></span> <span data-ttu-id="72cc5-115"> (查看 SharePoint 頁面不會算作自動更新的動作。 ) </span><span class="sxs-lookup"><span data-stu-id="72cc5-115">(Viewing a SharePoint page does not count as an action for automatic renewal.)</span></span>
- <span data-ttu-id="72cc5-116">從群組中 Outlook 加入群組、讀取或寫入群組郵件，與 (Outlook 網頁) 上的郵件。</span><span class="sxs-lookup"><span data-stu-id="72cc5-116">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="72cc5-117">Teams-來訪小組頻道。</span><span class="sxs-lookup"><span data-stu-id="72cc5-117">Teams - visiting a teams channel.</span></span>

<span data-ttu-id="72cc5-118">請注意，唯一會觸發自動群組更新的 Yammer 活動，就是將檔上傳至群組內 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="72cc5-118">Note that the only Yammer activity which will trigger an automatic group renewal is the upload of a document to SharePoint within the community.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72cc5-119">當您變更到期原則時，服務會重新計算每個群組的到期日。</span><span class="sxs-lookup"><span data-stu-id="72cc5-119">When you change the expiration policy, the service recalculates the expiration date for each group.</span></span> <span data-ttu-id="72cc5-120">它永遠從建立群組的日期開始計數，然後套用新的到期原則。</span><span class="sxs-lookup"><span data-stu-id="72cc5-120">It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="72cc5-121">請務必知道到期會預設為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="72cc5-121">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="72cc5-122">管理員若要使用它，必須為組織啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="72cc5-122">Administrators have to enable it for their organization if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="72cc5-123">設定和使用 Microsoft 365 群組的到期原則時，需要您擁有但不一定要為已套用到期原則之所有群組的成員指派 Azure AD 進階版授權。</span><span class="sxs-lookup"><span data-stu-id="72cc5-123">Configuring and using the expiration policy for Microsoft 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="72cc5-124">如需詳細資訊，請參閱[Azure Active Directory 進階版快速](/azure/active-directory/active-directory-get-started-premium)入門。</span><span class="sxs-lookup"><span data-stu-id="72cc5-124">For more information see [Getting started with Azure Active Directory Premium](/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a><span data-ttu-id="72cc5-125">神秘可以設定及使用 Microsoft 365 群組到期原則？</span><span class="sxs-lookup"><span data-stu-id="72cc5-125">Who can configure and use the Microsoft 365 groups expiration policy?</span></span>

|<span data-ttu-id="72cc5-126">角色</span><span class="sxs-lookup"><span data-stu-id="72cc5-126">Role</span></span>|<span data-ttu-id="72cc5-127">可以執行的動作</span><span class="sxs-lookup"><span data-stu-id="72cc5-127">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="72cc5-128">在 Azure 中 Office 365 全域系統管理員 (公司管理員) ，使用者管理員</span><span class="sxs-lookup"><span data-stu-id="72cc5-128">Office 365 global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="72cc5-129">建立、讀取、更新或刪除 Microsoft 365 群組到期原則設定。</span><span class="sxs-lookup"><span data-stu-id="72cc5-129">Create, read, update, or delete the Microsoft 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="72cc5-130">使用者</span><span class="sxs-lookup"><span data-stu-id="72cc5-130">User</span></span>|<span data-ttu-id="72cc5-131">更新或[還原](/azure/active-directory/users-groups-roles/groups-restore-deleted)擁有的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="72cc5-131">Renew or [restore](/azure/active-directory/users-groups-roles/groups-restore-deleted) a Microsoft 365 group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="72cc5-132">如何設定到期原則</span><span class="sxs-lookup"><span data-stu-id="72cc5-132">How to set the expiration policy</span></span>

<span data-ttu-id="72cc5-133">如以上所述，到期會預設為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="72cc5-133">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="72cc5-134">管理員必須啟用到期原則，並將其設定為生效。</span><span class="sxs-lookup"><span data-stu-id="72cc5-134">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="72cc5-135">若要啟用此功能，請移至 **Azure Active Directory**  >  **群組**  >  **到期** 日。</span><span class="sxs-lookup"><span data-stu-id="72cc5-135">To enable it, go to **Azure Active Directory** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="72cc5-136">您可以在這裡設定預設的組生命週期，並指定您要提前多久的時間，將第一和第二個到期通知移至群組擁有者。</span><span class="sxs-lookup"><span data-stu-id="72cc5-136">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="72cc5-137">群組存留時間是以天數指定，可設定為180、365或您指定的自訂值。</span><span class="sxs-lookup"><span data-stu-id="72cc5-137">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="72cc5-138">自訂值至少必須是30天。</span><span class="sxs-lookup"><span data-stu-id="72cc5-138">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="72cc5-139">如果群組沒有擁有者，到期電子郵件將會移至指定的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="72cc5-139">If the group does not have an owner, the expiration emails will go to the specified administrator.</span></span>

<span data-ttu-id="72cc5-140">您可以設定所有群組的原則、只 () 的群組，或選取 [ **無**] 500 以完全關閉。</span><span class="sxs-lookup"><span data-stu-id="72cc5-140">You can set the policy for all of your groups, only selected groups (up to 500), or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="72cc5-141">請注意，目前您不能針對不同的群組使用不同的原則。</span><span class="sxs-lookup"><span data-stu-id="72cc5-141">Note that currently you can't have different policies for different groups.</span></span>

![Azure Active Directory 中群組到期設定的螢幕擷取畫面](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a><span data-ttu-id="72cc5-143">到期原則與保留原則的運作方式</span><span class="sxs-lookup"><span data-stu-id="72cc5-143">How expiry works with the retention policy</span></span>

<span data-ttu-id="72cc5-144">如果您已為安全性與合規性中心的群組設定保留原則，到期原則會順利地使用保留原則運作。</span><span class="sxs-lookup"><span data-stu-id="72cc5-144">If you have set up a retention policy for groups in the Security and Compliance center, the expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="72cc5-145">當群組到期時，群組中的信箱交談和群組網站中的檔案，保留原則中所定義的特定天數保留在保留容器中。</span><span class="sxs-lookup"><span data-stu-id="72cc5-145">When a group expires, the group's mailbox conversations and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="72cc5-146">但到期後，使用者將不會看到此群組或其內容。</span><span class="sxs-lookup"><span data-stu-id="72cc5-146">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a><span data-ttu-id="72cc5-147">群組擁有者如何以及何時會到期的使用者群組</span><span class="sxs-lookup"><span data-stu-id="72cc5-147">How and when a group owner learns if their groups are going to expire</span></span>

<span data-ttu-id="72cc5-148">群組擁有者只會透過電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="72cc5-148">Group owners will only be notified via email.</span></span> <span data-ttu-id="72cc5-149">如果群組是透過 Planner、SharePoint 或任何其他應用程式建立，到期通知永遠都透過電子郵件傳送。</span><span class="sxs-lookup"><span data-stu-id="72cc5-149">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="72cc5-150">如果群組是透過 Teams 建立，群組擁有者會收到透過「活動」區段進行更新的通知。</span><span class="sxs-lookup"><span data-stu-id="72cc5-150">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="72cc5-151">如果您的群組擁有者沒有有效的電子郵件地址，建議您在群組上啟用到期。</span><span class="sxs-lookup"><span data-stu-id="72cc5-151">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="72cc5-152">在群組到期之前的30天內，群組擁有者 (或您為沒有擁有者) 的群組所指定的電子郵件地址，將會收到電子郵件，讓使用者可以輕鬆地更新群組。</span><span class="sxs-lookup"><span data-stu-id="72cc5-152">Thirty days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="72cc5-153">如果不加以更新，他們會在到期前的15天內收到另一個更新電子郵件。</span><span class="sxs-lookup"><span data-stu-id="72cc5-153">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="72cc5-154">如果他們仍未更新，他們會在到期前的一天內收到一封以上的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="72cc5-154">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span>

<span data-ttu-id="72cc5-155">若由於某些原因，任何擁有者或系統管理員都不會在過期前更新群組，管理員仍可在到期後30天內還原群組。</span><span class="sxs-lookup"><span data-stu-id="72cc5-155">If for some reason none of the owners or admins renew the group before it expires, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="72cc5-156">如需詳細資訊，請參閱：[還原已刪除的 Microsoft 365 群組](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)。</span><span class="sxs-lookup"><span data-stu-id="72cc5-156">For details see: [Restore a deleted Microsoft 365 group](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).</span></span>

## <a name="archiving-group-contents"></a><span data-ttu-id="72cc5-157">封存群組內容</span><span class="sxs-lookup"><span data-stu-id="72cc5-157">Archiving group contents</span></span>

<span data-ttu-id="72cc5-158">如果您有一個不再打算使用的群組，但您想要保留其內容，請參閱封存[群組、小組和 Yammer](end-life-cycle-groups-teams-sites-yammer.md) ，以取得如何從不同群組服務匯出資訊的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="72cc5-158">If you have a group that you no longer plan to use, but you want to retain its content, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information about how to export information from the different groups services.</span></span>

## <a name="related-topics"></a><span data-ttu-id="72cc5-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="72cc5-159">Related topics</span></span>

[<span data-ttu-id="72cc5-160">共同作業管理規劃逐步</span><span class="sxs-lookup"><span data-stu-id="72cc5-160">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="72cc5-161">建立共同作業管理計畫</span><span class="sxs-lookup"><span data-stu-id="72cc5-161">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="72cc5-162">保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="72cc5-162">Overview of retention policies</span></span>](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[<span data-ttu-id="72cc5-163">指派新擁有者給孤立的群組</span><span class="sxs-lookup"><span data-stu-id="72cc5-163">Assign a new owner to an orphaned group</span></span>](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[<span data-ttu-id="72cc5-164">設定 Microsoft 365 群組到期</span><span class="sxs-lookup"><span data-stu-id="72cc5-164">Configure Microsoft 365 groups expiration</span></span>](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
