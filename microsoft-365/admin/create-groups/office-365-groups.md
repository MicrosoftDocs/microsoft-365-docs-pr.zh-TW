---
title: 系統管理員的 Microsoft 365 群組概觀 (部分機器翻譯)
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解 Microsoft 365 群組。
ms.openlocfilehash: b3bc0c30f4ac292da7af46678fc742854984db12
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925347"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a><span data-ttu-id="3fb04-103">系統管理員的 Microsoft 365 群組概觀 (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="3fb04-103">Overview of Microsoft 365 Groups for administrators</span></span>

<span data-ttu-id="3fb04-104">Microsoft 365 群組是推動 Microsoft 365 所有團隊合作的基礎成員資格服務。</span><span class="sxs-lookup"><span data-stu-id="3fb04-104">Microsoft 365 Groups is the foundational membership service that drives all teamwork across Microsoft 365.</span></span> <span data-ttu-id="3fb04-105">使用 Microsoft 365 群組，您可以讓一組人員存取共用資源集合。</span><span class="sxs-lookup"><span data-stu-id="3fb04-105">With Microsoft 365 Groups, you can give a group of people access to a collection of shared resources.</span></span> <span data-ttu-id="3fb04-106">這些資源包括：</span><span class="sxs-lookup"><span data-stu-id="3fb04-106">These resources include:</span></span>

- <span data-ttu-id="3fb04-107">共用的 Outlook 信箱</span><span class="sxs-lookup"><span data-stu-id="3fb04-107">A shared Outlook inbox</span></span>
- <span data-ttu-id="3fb04-108">共用日曆</span><span class="sxs-lookup"><span data-stu-id="3fb04-108">A shared calendar</span></span>
- <span data-ttu-id="3fb04-109">SharePoint 文件庫</span><span class="sxs-lookup"><span data-stu-id="3fb04-109">A SharePoint document library</span></span>
- <span data-ttu-id="3fb04-110">A Planner</span><span class="sxs-lookup"><span data-stu-id="3fb04-110">A Planner</span></span>
- <span data-ttu-id="3fb04-111">OneNote 筆記本</span><span class="sxs-lookup"><span data-stu-id="3fb04-111">A OneNote notebook</span></span>
- <span data-ttu-id="3fb04-112">Power BI</span><span class="sxs-lookup"><span data-stu-id="3fb04-112">Power BI</span></span>
- <span data-ttu-id="3fb04-113">如果 yammer (從 Yammer 建立群組，Yammer) </span><span class="sxs-lookup"><span data-stu-id="3fb04-113">Yammer (if the group was created from Yammer)</span></span>
- <span data-ttu-id="3fb04-114">如果群組 (從 Teams 建立，團隊會) </span><span class="sxs-lookup"><span data-stu-id="3fb04-114">A Team (if the group was created from Teams)</span></span>
- <span data-ttu-id="3fb04-115">如果您 (Project 網頁) </span><span class="sxs-lookup"><span data-stu-id="3fb04-115">Roadmap (if you have Project for the web)</span></span>

<span data-ttu-id="3fb04-116">有了 Microsoft 365 群組，您就不必手動指派許可權給這些資源。</span><span class="sxs-lookup"><span data-stu-id="3fb04-116">With a Microsoft 365 group, you don't have to manually assign permissions to each of these resources.</span></span> <span data-ttu-id="3fb04-117">將人員新增到群組時，會自動提供他們所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="3fb04-117">Adding people to the group automatically gives them the permissions they need.</span></span>

<span data-ttu-id="3fb04-118">除非您將建立群組限制為一組特定人員，否則 [任何使用者都可以建立群組](manage-creation-of-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="3fb04-118">Any user can create a group unless you [limit group creation to a specific set of people](manage-creation-of-groups.md).</span></span> <span data-ttu-id="3fb04-119">如果您限制建立群組，無法建立群組的使用者將無法建立 SharePoint 網站、規劃工具或小組。</span><span class="sxs-lookup"><span data-stu-id="3fb04-119">If you limit group creation, users who cannot create groups will not be able to create SharePoint sites, Planners, or teams.</span></span> <span data-ttu-id="3fb04-120">這些服務會要求建立服務的人能夠建立群組。</span><span class="sxs-lookup"><span data-stu-id="3fb04-120">These services require the people creating them to be able to create a group.</span></span> <span data-ttu-id="3fb04-121">只要使用者是群組的成員，他們仍可參與群組活動，例如，在 Planner 中建立工作，或是使用 Teams 聊天。</span><span class="sxs-lookup"><span data-stu-id="3fb04-121">Users can still participate in group activities, such as creating tasks in Planner or using Teams chat, provided they are a member of the group.</span></span>

<span data-ttu-id="3fb04-122">群組具有下列角色：</span><span class="sxs-lookup"><span data-stu-id="3fb04-122">Groups have the following roles:</span></span>

- <span data-ttu-id="3fb04-123">**擁有者** - 群組擁有者可以新增或移除成員，而且擁有唯一的許可權，例如刪除共用之信箱中的交談，或變更群組的不同設定。</span><span class="sxs-lookup"><span data-stu-id="3fb04-123">**Owners** - Group owners can add or remove members and have unique permissions like the ability to delete conversations from the shared inbox or change different settings about the group.</span></span> <span data-ttu-id="3fb04-124">群組擁有者可以重新命名群組、更新描述或圖片等等。</span><span class="sxs-lookup"><span data-stu-id="3fb04-124">Group owners can rename the group, update the description or picture and more.</span></span>
- <span data-ttu-id="3fb04-125">**成員** - 成員可以存取群組中所有專案，但無法變更群組設定。</span><span class="sxs-lookup"><span data-stu-id="3fb04-125">**Members** - Members can access everything in the group, but can't change group settings.</span></span> <span data-ttu-id="3fb04-126">根據預設，群組成員可以邀請來賓加入您的群組，不過您可以 [控制該設定](manage-guest-access-in-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="3fb04-126">By default group members can invite guests to join your group, though you can [control that setting](manage-guest-access-in-groups.md).</span></span>
- <span data-ttu-id="3fb04-127">**來賓** - 群組來賓是組織外部的成員。</span><span class="sxs-lookup"><span data-stu-id="3fb04-127">**Guests** - Group guests are members who are from outside your organization.</span></span>

<span data-ttu-id="3fb04-128">只有全域系統管理員、使用者系統管理員和群組管理員可以在 Microsoft 365 系統管理中心建立及管理群組。</span><span class="sxs-lookup"><span data-stu-id="3fb04-128">Only global admins, user admins, and groups admins can create and manage groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3fb04-129">您不能是委派的系統管理員 (例如，擔任系統管理員的顧問)。</span><span class="sxs-lookup"><span data-stu-id="3fb04-129">You can't be a delegated admin (for example, a consultant who is an admin on behalf of).</span></span>

<span data-ttu-id="3fb04-130">做為系統管理員，您可以：</span><span class="sxs-lookup"><span data-stu-id="3fb04-130">As an administrator, you can:</span></span>

- [<span data-ttu-id="3fb04-131">指定誰可以建立群組</span><span class="sxs-lookup"><span data-stu-id="3fb04-131">Specify who can create groups</span></span>](manage-creation-of-groups.md)
- [<span data-ttu-id="3fb04-132">為貴組織的群組建立命名政策</span><span class="sxs-lookup"><span data-stu-id="3fb04-132">Create a naming policy for groups in your organization</span></span>](groups-naming-policy.md)
- [<span data-ttu-id="3fb04-133">選擇在建立群組時要使用哪一個網域</span><span class="sxs-lookup"><span data-stu-id="3fb04-133">Choose which domain to use when creating a group</span></span>](choose-domain-to-create-groups.md)
- [<span data-ttu-id="3fb04-134">管理群組的來賓存取</span><span class="sxs-lookup"><span data-stu-id="3fb04-134">Manage guest access to groups</span></span>](manage-guest-access-in-groups.md)
- <span data-ttu-id="3fb04-135">[刪除後 30](restore-deleted-group.md) (復原刪除的群組) </span><span class="sxs-lookup"><span data-stu-id="3fb04-135">[Recover a deleted group](restore-deleted-group.md) (within 30 days of deletion)</span></span>

<span data-ttu-id="3fb04-136">如果您想要更自動化的方式來管理 Microsoft 365 群組的生命週期，可以使用到期政策以特定的時間間隔到期群組。</span><span class="sxs-lookup"><span data-stu-id="3fb04-136">If you prefer a more automated way to manage the lifecycle of your Microsoft 365 groups, you can use expiration policies to expire groups at a specific time interval.</span></span> <span data-ttu-id="3fb04-137">群組的擁有者將在群組到期日的 30、15 和 1 天前收到電子郵件，允許他們在仍然需要時為群組續約。</span><span class="sxs-lookup"><span data-stu-id="3fb04-137">The group's owners will get an email 30, 15, and 1 day before the group expiration that allows them to renew the group if it's still needed.</span></span> <span data-ttu-id="3fb04-138">請參閱 [：Microsoft 365 群組到期政策](office-365-groups-expiration-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="3fb04-138">See: [Microsoft 365 group Expiration Policy](office-365-groups-expiration-policy.md).</span></span>

<span data-ttu-id="3fb04-139">您可以使用 Microsoft 365 系統管理中心或 [PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel)來管理群組。</span><span class="sxs-lookup"><span data-stu-id="3fb04-139">You can administer your groups from the Microsoft 365 admin center or [by using PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel).</span></span>

<span data-ttu-id="3fb04-140">如果您有許多使用者 ，例如大型公司或企業，您可能有許多使用者會建立各種用途的群組。</span><span class="sxs-lookup"><span data-stu-id="3fb04-140">If you have many users, such as in a large corporation or enterprise, you may have many users who create groups for various purposes.</span></span> <span data-ttu-id="3fb04-141">我們強烈建議您查閱 [Microsoft 365](plan-for-groups-governance.md) 群組中的監管計畫以獲得最佳作法。</span><span class="sxs-lookup"><span data-stu-id="3fb04-141">We highly recommend that you review [Plan for governance in Microsoft 365 groups](plan-for-groups-governance.md) for best practices.</span></span>

## <a name="group-limits"></a><span data-ttu-id="3fb04-142">群組限制</span><span class="sxs-lookup"><span data-stu-id="3fb04-142">Group limits</span></span>

<span data-ttu-id="3fb04-143">下列限制適用于 Microsoft 365 群組：</span><span class="sxs-lookup"><span data-stu-id="3fb04-143">The following limits apply to Microsoft 365 Groups:</span></span>

|<span data-ttu-id="3fb04-144">最大。。。</span><span class="sxs-lookup"><span data-stu-id="3fb04-144">Maximum...</span></span>|<span data-ttu-id="3fb04-145">值</span><span class="sxs-lookup"><span data-stu-id="3fb04-145">Value</span></span>|
|:---------|:----|
|<span data-ttu-id="3fb04-146">Owners per group</span><span class="sxs-lookup"><span data-stu-id="3fb04-146">Owners per group</span></span>|<span data-ttu-id="3fb04-147">100</span><span class="sxs-lookup"><span data-stu-id="3fb04-147">100</span></span>|
|<span data-ttu-id="3fb04-148">Groups a user can create</span><span class="sxs-lookup"><span data-stu-id="3fb04-148">Groups a user can create</span></span>|<span data-ttu-id="3fb04-149">250</span><span class="sxs-lookup"><span data-stu-id="3fb04-149">250</span></span>|
|<span data-ttu-id="3fb04-150">系統管理員可以建立群組</span><span class="sxs-lookup"><span data-stu-id="3fb04-150">Groups an admin can create</span></span>|<span data-ttu-id="3fb04-151">租使用者的預設上限為 500 K</span><span class="sxs-lookup"><span data-stu-id="3fb04-151">Up to default tenant limit of 500 K</span></span>|
|<span data-ttu-id="3fb04-152">Number of members </span><span class="sxs-lookup"><span data-stu-id="3fb04-152">Number of members</span></span>|<span data-ttu-id="3fb04-153">超過 1，000 個，但只有 1，000 個可以同時存取群組交談。</span><span class="sxs-lookup"><span data-stu-id="3fb04-153">More than 1,000, though only 1,000 can access the Group conversations concurrently.</span></span> <br><span data-ttu-id="3fb04-154">使用者可能會發現，在 Outlook 中存取大型群組中的日曆和交談時，有延遲的情況。</span><span class="sxs-lookup"><span data-stu-id="3fb04-154">Users might notice delays when accessing the calendar and conversations in large groups in Outlook.</span></span>|
|<span data-ttu-id="3fb04-155">使用者可參與的群組數目</span><span class="sxs-lookup"><span data-stu-id="3fb04-155">Number of Groups a user can be a member of</span></span>|<span data-ttu-id="3fb04-156">7,000</span><span class="sxs-lookup"><span data-stu-id="3fb04-156">7,000</span></span>|
|<span data-ttu-id="3fb04-157">檔案儲存空間</span><span class="sxs-lookup"><span data-stu-id="3fb04-157">File storage</span></span>|<span data-ttu-id="3fb04-158">每個訂閱的使用者 1 TB + 10 GB + 任何其他購買的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="3fb04-158">1 Terabyte + 10 GB per subscribed user + any other storage purchased.</span></span> <span data-ttu-id="3fb04-159">您可以購買無限制的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="3fb04-159">You can purchase an unlimited amount of extra storage.</span></span>|
|<span data-ttu-id="3fb04-160">群組信箱大小</span><span class="sxs-lookup"><span data-stu-id="3fb04-160">Group Mailbox size</span></span>|<span data-ttu-id="3fb04-161">50 GB</span><span class="sxs-lookup"><span data-stu-id="3fb04-161">50 GB</span></span>|

<span data-ttu-id="3fb04-162">組織預設的 Microsoft 365 群組數量上限為 500，000 個。</span><span class="sxs-lookup"><span data-stu-id="3fb04-162">The default maximum number of Microsoft 365 groups that an organization can have is 500,000.</span></span> <span data-ttu-id="3fb04-163">若要超出預設限制，您必須與 Microsoft 支援服務聯繫。</span><span class="sxs-lookup"><span data-stu-id="3fb04-163">To go beyond the default limit, you must contact Microsoft Support.</span></span> <span data-ttu-id="3fb04-164">有關 Microsoft 365 群組限制詳細資訊，請參閱 [Microsoft 365 群組 - 系統管理協助](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。</span><span class="sxs-lookup"><span data-stu-id="3fb04-164">For more information on Microsoft 365 Groups limits, see [Microsoft 365 Groups - Admin help](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>

<span data-ttu-id="3fb04-165">當您有關于群組使用方式的可行資訊時，管理 Microsoft 365 群組會比較有效率。</span><span class="sxs-lookup"><span data-stu-id="3fb04-165">Managing your Microsoft 365 groups is more effective when you have actionable information about groups usage.</span></span> <span data-ttu-id="3fb04-166">Microsoft 365 系統管理中心有報告工具，可讓您查看儲存空間使用、使用中的群組數量，以及使用者如何使用群組。</span><span class="sxs-lookup"><span data-stu-id="3fb04-166">The Microsoft 365 admin center has a reporting tool that lets you see storage use, how many active groups you have, and how users are using the groups.</span></span> <span data-ttu-id="3fb04-167">請參閱：詳細資訊請參閱系統管理中心的 [Microsoft 365](../activity-reports/office-365-groups.md) 報告。</span><span class="sxs-lookup"><span data-stu-id="3fb04-167">See: [Microsoft 365 Reports in the admin center](../activity-reports/office-365-groups.md) for more information.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="3fb04-168">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="3fb04-168">Sensitivity labels</span></span>

<span data-ttu-id="3fb04-169">您可以建立敏感度標籤，貴組織的使用者在建立 Microsoft 365 群組時可以設定。</span><span class="sxs-lookup"><span data-stu-id="3fb04-169">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 group.</span></span> <span data-ttu-id="3fb04-170">使用敏感度標籤，您可以設定：</span><span class="sxs-lookup"><span data-stu-id="3fb04-170">With sensitivity labels, you can configure:</span></span> 

- <span data-ttu-id="3fb04-171">公用 (或私人網站的隱私權) </span><span class="sxs-lookup"><span data-stu-id="3fb04-171">Privacy (public or private)</span></span>
- <span data-ttu-id="3fb04-172">外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="3fb04-172">External users access</span></span>
- <span data-ttu-id="3fb04-173">未管理裝置存取</span><span class="sxs-lookup"><span data-stu-id="3fb04-173">Unmanaged device access</span></span>

<span data-ttu-id="3fb04-174">例如，您可以建立稱為高度機密的卷標，並指定任何使用這個標籤所建立的群組為私人群組，且不允許外部使用者。</span><span class="sxs-lookup"><span data-stu-id="3fb04-174">For example, you can create a label called *Highly Confidential* and specify that any group created with this label will be private and not allow external users.</span></span> <span data-ttu-id="3fb04-175">當貴組織的使用者在建立群組時選取此標籤時，群組會設定為私人，且不允許群組成員將外部使用者新增到群組。</span><span class="sxs-lookup"><span data-stu-id="3fb04-175">When users in your organization select this label during group creation, the group will be set to private and group members will not be allowed to add external users to the group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fb04-176">如果您目前使用分類標籤，一旦啟用敏感度標籤後，建立群組的使用者就無法再使用這些分類標籤。</span><span class="sxs-lookup"><span data-stu-id="3fb04-176">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span> 

<span data-ttu-id="3fb04-177">有關建立、管理及使用敏感度標籤的資訊，請參閱使用敏感度標籤來保護 [Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="3fb04-177">For information about creating, managing, and using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="which-microsoft-365-plans-include-groups"></a><span data-ttu-id="3fb04-178">哪些 Microsoft 365 方案包含群組？</span><span class="sxs-lookup"><span data-stu-id="3fb04-178">Which Microsoft 365 plans include groups?</span></span>

<span data-ttu-id="3fb04-179">任何擁有 Exchange Online 和 SharePoint Online 的 Microsoft 365 訂閱都支援群組。</span><span class="sxs-lookup"><span data-stu-id="3fb04-179">Any Microsoft 365 subscription that has Exchange Online and SharePoint Online will support groups.</span></span> <span data-ttu-id="3fb04-180">其中包括商務基本版和商務進版方案，以及企業版 E1、E3 和 E5 方案。</span><span class="sxs-lookup"><span data-stu-id="3fb04-180">That includes the Business Essentials and Business Premium plans, and the Enterprise E1, E3, and E5 plans.</span></span> <span data-ttu-id="3fb04-181">群組會接受建立群組群組 (也稱為群組成員「召集人」) 。</span><span class="sxs-lookup"><span data-stu-id="3fb04-181">The group takes on the licensing of the person who creates the group (also known as the "organizer" of the group).</span></span> <span data-ttu-id="3fb04-182">只要該名召集人擁有您希望群組擁有的功能之適當授權，該授權就會傳達給該群組。</span><span class="sxs-lookup"><span data-stu-id="3fb04-182">As long as the organizer has the proper license for whatever features you want the group to have, that license will convey to the group.</span></span>

> [!NOTE]
> <span data-ttu-id="3fb04-183">有關 Microsoft 365 服務系列與方案的詳細資訊，請參閱 [Microsoft 365 方案選項](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。</span><span class="sxs-lookup"><span data-stu-id="3fb04-183">For more details about Microsoft 365 service families and plans, see [Microsoft 365 plan options](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span></span>

<span data-ttu-id="3fb04-184">如果您有僅適用于 Exchange 的計畫，您仍然可以取得 Outlook 中群組的共用信箱和共用日曆功能，但您不會取得文件庫、Planner 或其他任何功能。</span><span class="sxs-lookup"><span data-stu-id="3fb04-184">If you have an Exchange-only plan you can still get the shared inbox and shared calendar features of groups in Outlook but you won't get the document library, Planner or any of the other capabilities.</span></span>

<span data-ttu-id="3fb04-185">Microsoft 365 群組可與 Azure Active Directory 一起使用。</span><span class="sxs-lookup"><span data-stu-id="3fb04-185">Microsoft 365 groups work with Azure Active Directory.</span></span> <span data-ttu-id="3fb04-186">您取得哪些群組功能取決於您擁有哪些 Azure Active Directory 訂閱，以及指派給群組的召集人哪些授權。</span><span class="sxs-lookup"><span data-stu-id="3fb04-186">The groups features you get depends on which Azure Active Directory subscription you have, and what licenses are assigned to the organizer of the group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fb04-187">對於所有群組功能，如果您有 Azure AD Premium 訂閱，無論使用者是否已指派 AAD P1 授權，都可以加入群組。</span><span class="sxs-lookup"><span data-stu-id="3fb04-187">For all the groups features, if you have an Azure AD Premium subscription, users can join the group whether or not they have an AAD P1 license assigned to them.</span></span> <span data-ttu-id="3fb04-188">不會強制執行授權。</span><span class="sxs-lookup"><span data-stu-id="3fb04-188">Licensing isn't enforced.</span></span>
> <span data-ttu-id="3fb04-189">我們會定期產生使用方式報告，告訴您哪些使用者遺失授權，並需要指派一個授權，才能符合授權要求。</span><span class="sxs-lookup"><span data-stu-id="3fb04-189">Periodically we will generate usage reports that tell you which users are missing a license, and need one assigned to them to be compliant with the licensing requirements.</span></span> <span data-ttu-id="3fb04-190">例如，假設使用者沒有授權，而他們會新增到強制執行命名策略的群組中。</span><span class="sxs-lookup"><span data-stu-id="3fb04-190">For example, let's say a user doesn't have a license and they are added to a group where the naming policy is enforced.</span></span> <span data-ttu-id="3fb04-191">報告會標出您需要授權。</span><span class="sxs-lookup"><span data-stu-id="3fb04-191">The report will flag for you that they need a license.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3fb04-192">相關文章</span><span class="sxs-lookup"><span data-stu-id="3fb04-192">Related articles</span></span>

[<span data-ttu-id="3fb04-193">瞭解 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="3fb04-193">Learn about Microsoft 365 Groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="3fb04-194">將通訊群組清單升級至 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="3fb04-194">Upgrade distribution lists to Microsoft 365 Groups</span></span>](../manage/upgrade-distribution-lists.md)

[<span data-ttu-id="3fb04-195">使用 PowerShell 管理 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="3fb04-195">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[<span data-ttu-id="3fb04-196">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="3fb04-196">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
