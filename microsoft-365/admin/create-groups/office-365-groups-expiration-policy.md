---
title: 群組到期原則
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: 深入瞭解 Microsoft 365 群組到期原則。
ms.openlocfilehash: 8def757241dec28f5a54c76dc81614fd52fe85e5
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780418"
---
# <a name="microsoft-365-group-expiration-policy"></a><span data-ttu-id="0b398-103">Microsoft 365 群組到期原則</span><span class="sxs-lookup"><span data-stu-id="0b398-103">Microsoft 365 group expiration policy</span></span>

<span data-ttu-id="0b398-104">隨著 Microsoft 365 群組的使用量增加，管理員和使用者需要一種方式來清除未使用的群組。</span><span class="sxs-lookup"><span data-stu-id="0b398-104">With the increase in usage of Microsoft 365 groups, administrators and users need a way to clean up unused groups.</span></span> <span data-ttu-id="0b398-105">到期原則可協助從系統中移除非使用中的群組，並使事情更整潔。</span><span class="sxs-lookup"><span data-stu-id="0b398-105">Expiration policies can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="0b398-106">當群組到期時，其相關聯的所有服務（信箱、Planner、SharePoint 網站、小組等等）都會同時刪除。</span><span class="sxs-lookup"><span data-stu-id="0b398-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, team, etc.) are also deleted.</span></span>

<span data-ttu-id="0b398-107">當群組到期時，它會「虛刪除」，表示它仍可復原30天。</span><span class="sxs-lookup"><span data-stu-id="0b398-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="0b398-108">管理員可以指定到期期限及任何非作用中的群組，只要到達該期間結束，也不會被更新，將會被刪除。</span><span class="sxs-lookup"><span data-stu-id="0b398-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="0b398-109">到期期限是在建立群組時或在最後一次更新的日期時開始。</span><span class="sxs-lookup"><span data-stu-id="0b398-109">The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="0b398-110">在到期之前，系統會自動將電子郵件傳送給群組擁有者，以允許使用者在其他到期間隔內更新群組。</span><span class="sxs-lookup"><span data-stu-id="0b398-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="0b398-111">小組使用者會在小組中看到持續的通知。</span><span class="sxs-lookup"><span data-stu-id="0b398-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="0b398-112">主動使用中的群組會自動更新。</span><span class="sxs-lookup"><span data-stu-id="0b398-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="0b398-113">下列任何動作都會自動更新群組：</span><span class="sxs-lookup"><span data-stu-id="0b398-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="0b398-114">SharePoint-查看、編輯、下載、移動、共用或上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="0b398-114">SharePoint - view, edit, download, move, share, or upload files.</span></span>
- <span data-ttu-id="0b398-115">Outlook-加入群組、讀取或寫入群組的郵件，以及類似郵件（Outlook 網頁版）。</span><span class="sxs-lookup"><span data-stu-id="0b398-115">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="0b398-116">團隊-來訪小組頻道。</span><span class="sxs-lookup"><span data-stu-id="0b398-116">Teams - visiting a teams channel.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b398-117">當您變更到期原則時，服務會重新計算每個群組的到期日。</span><span class="sxs-lookup"><span data-stu-id="0b398-117">When you change the expiration policy, the service recalculates the expiration date for each group.</span></span> <span data-ttu-id="0b398-118">它永遠從建立群組的日期開始計數，然後套用新的到期原則。</span><span class="sxs-lookup"><span data-stu-id="0b398-118">It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="0b398-119">請務必知道到期會預設為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="0b398-119">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="0b398-120">系統管理員若要使用它，必須為組織啟用它。</span><span class="sxs-lookup"><span data-stu-id="0b398-120">Administrators will have to enable it for their organization if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="0b398-121">設定及使用 Microsoft 365 群組的到期原則，需要您擁有但不一定要為已套用到期原則之所有群組的成員指派 Azure AD Premium 授權。</span><span class="sxs-lookup"><span data-stu-id="0b398-121">Configuring and using the expiration policy for Microsoft 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="0b398-122">如需詳細資訊，請參閱[Azure Active Directory Premium 快速](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)入門。</span><span class="sxs-lookup"><span data-stu-id="0b398-122">For more information see [Getting started with Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a><span data-ttu-id="0b398-123">誰可以設定及使用 Microsoft 365 群組到期原則？</span><span class="sxs-lookup"><span data-stu-id="0b398-123">Who can configure and use the Microsoft 365 groups expiration policy?</span></span>

|<span data-ttu-id="0b398-124">角色</span><span class="sxs-lookup"><span data-stu-id="0b398-124">Role</span></span>|<span data-ttu-id="0b398-125">可以執行的動作</span><span class="sxs-lookup"><span data-stu-id="0b398-125">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="0b398-126">全域管理員（在 Azure、公司管理員）、使用者管理員</span><span class="sxs-lookup"><span data-stu-id="0b398-126">Global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="0b398-127">建立、讀取、更新或刪除 Microsoft 365 群組到期原則設定。</span><span class="sxs-lookup"><span data-stu-id="0b398-127">Create, read, update, or delete the Microsoft 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="0b398-128">User</span><span class="sxs-lookup"><span data-stu-id="0b398-128">User</span></span>|<span data-ttu-id="0b398-129">更新或[還原](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)擁有的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="0b398-129">Renew or [restore](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) a Microsoft 365 group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="0b398-130">如何設定到期原則</span><span class="sxs-lookup"><span data-stu-id="0b398-130">How to set the expiration policy</span></span>

<span data-ttu-id="0b398-131">如以上所述，到期會預設為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="0b398-131">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="0b398-132">管理員必須啟用到期原則，並將其設定為生效。</span><span class="sxs-lookup"><span data-stu-id="0b398-132">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="0b398-133">若要啟用它，請移至**Azure Active Directory （AAD）**  >  **群組**  >  **到期**。</span><span class="sxs-lookup"><span data-stu-id="0b398-133">To enable it go to **Azure Active Directory (AAD)** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="0b398-134">您可以在這裡設定預設的組生命週期，並指定您要提前多久的時間，將第一和第二個到期通知移至群組擁有者。</span><span class="sxs-lookup"><span data-stu-id="0b398-134">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="0b398-135">群組存留時間是以天數指定，可設定為180、365或您指定的自訂值。</span><span class="sxs-lookup"><span data-stu-id="0b398-135">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="0b398-136">自訂值至少必須是30天。</span><span class="sxs-lookup"><span data-stu-id="0b398-136">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="0b398-137">如果群組沒有擁有者，到期電子郵件將會移至指定的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="0b398-137">If the group does not have an owner, the expiration emails will go to a specified administrator.</span></span>

<span data-ttu-id="0b398-138">您可以設定所有群組的原則，只為選取的群組，或透過選取 [**無**] 完全關閉。</span><span class="sxs-lookup"><span data-stu-id="0b398-138">You can set the policy for all of your groups, only selected groups, or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="0b398-139">請注意，目前您不能針對不同的群組使用不同的原則。</span><span class="sxs-lookup"><span data-stu-id="0b398-139">Note that currently you can't have different policies for different groups.</span></span>

![Azure Active Directory 中群組到期設定的螢幕擷取畫面](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a><span data-ttu-id="0b398-141">到期原則與保留原則的運作方式</span><span class="sxs-lookup"><span data-stu-id="0b398-141">How expiry works with the retention policy</span></span>

<span data-ttu-id="0b398-142">如果您在群組的安全性與合規性中心中有設定保留原則，到期原則會順利地使用保留原則運作。</span><span class="sxs-lookup"><span data-stu-id="0b398-142">If you have setup retention policy in Security and Compliance center for groups, expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="0b398-143">當群組到期時，群組中的 [在信箱中交談] 核取方塊和群組網站中的檔案會保留在保留原則中所定義的特定天數內保留容器內。</span><span class="sxs-lookup"><span data-stu-id="0b398-143">When a group expires, the group's conversations in mail box and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="0b398-144">但到期後，使用者將不會看到此群組或其內容。</span><span class="sxs-lookup"><span data-stu-id="0b398-144">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a><span data-ttu-id="0b398-145">群組擁有者如何以及何時會到期的使用者群組</span><span class="sxs-lookup"><span data-stu-id="0b398-145">How and when a group owner learns if their groups are going to expire</span></span>

<span data-ttu-id="0b398-146">群組擁有者只會透過電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="0b398-146">Group owners will only be notified via email.</span></span> <span data-ttu-id="0b398-147">如果群組是透過 Planner、SharePoint 或任何其他應用程式建立，到期通知永遠都透過電子郵件傳送。</span><span class="sxs-lookup"><span data-stu-id="0b398-147">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="0b398-148">如果群組是透過小組建立，群組擁有者會收到透過「活動」區段進行更新的通知。</span><span class="sxs-lookup"><span data-stu-id="0b398-148">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="0b398-149">如果您的群組擁有者沒有有效的電子郵件地址，建議您在群組上啟用到期。</span><span class="sxs-lookup"><span data-stu-id="0b398-149">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="0b398-150">超過此群組的30天之後，群組擁有者（或您為沒有擁有者之群組所指定的電子郵件地址）將會收到電子郵件，讓使用者可以輕鬆地更新群組。</span><span class="sxs-lookup"><span data-stu-id="0b398-150">30 days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="0b398-151">如果不加以更新，他們會在到期前的15天內收到另一個更新電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0b398-151">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="0b398-152">如果他們仍未更新，他們會在到期前的一天內收到一封以上的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="0b398-152">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span>

<span data-ttu-id="0b398-153">若由於某些原因，任何擁有者或系統管理員都不會在過期前更新群組，管理員仍可在到期後30天內還原群組。</span><span class="sxs-lookup"><span data-stu-id="0b398-153">If for some reason none of the owners or admins renew the group before it expires, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="0b398-154">如需詳細資訊，請參閱：[還原已刪除的 Microsoft 365 群組](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)。</span><span class="sxs-lookup"><span data-stu-id="0b398-154">For details see: [Restore a deleted Microsoft 365 group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

## <a name="related-articles"></a><span data-ttu-id="0b398-155">相關文章</span><span class="sxs-lookup"><span data-stu-id="0b398-155">Related articles</span></span>

[<span data-ttu-id="0b398-156">保留原則概觀</span><span class="sxs-lookup"><span data-stu-id="0b398-156">Overview of retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

[<span data-ttu-id="0b398-157">指派新擁有者給孤立的群組</span><span class="sxs-lookup"><span data-stu-id="0b398-157">Assign a new owner to an orphaned group</span></span>](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

<span data-ttu-id="0b398-158">[設定 Microsoft 365 群組到期](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)'</span><span class="sxs-lookup"><span data-stu-id="0b398-158">[Configure Microsoft 365 groups expiration](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal) '</span></span>
