---
title: 系統管理員的 Microsoft 365 群組概觀 (部分機器翻譯)
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
description: 深入瞭解 Microsoft 365 群組。
ms.openlocfilehash: 14bc1211aaa65fb2daeebdb22729fce10154f204
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780406"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a><span data-ttu-id="372be-103">系統管理員的 Microsoft 365 群組概觀 (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="372be-103">Overview of Microsoft 365 Groups for administrators</span></span>

<span data-ttu-id="372be-104">Microsoft 365 群組是一種基礎成員資格服務，可促進整個 Microsoft 365 的所有團隊合作。</span><span class="sxs-lookup"><span data-stu-id="372be-104">Microsoft 365 Groups is the foundational membership service that drives all teamwork across Microsoft 365.</span></span> <span data-ttu-id="372be-105">使用 Microsoft 365 群組，您可以讓一組人員能夠存取共同作業資源的集合，供他們共用。</span><span class="sxs-lookup"><span data-stu-id="372be-105">With Microsoft 365 Groups, you can give a group of people access to a collection of collaboration resources for those people to share.</span></span> <span data-ttu-id="372be-106">這些資源包括：</span><span class="sxs-lookup"><span data-stu-id="372be-106">These resources include:</span></span>

- <span data-ttu-id="372be-107">共用的 Outlook 收件匣</span><span class="sxs-lookup"><span data-stu-id="372be-107">A shared Outlook inbox</span></span>
- <span data-ttu-id="372be-108">共用行事曆</span><span class="sxs-lookup"><span data-stu-id="372be-108">A shared calendar</span></span>
- <span data-ttu-id="372be-109">SharePoint 文件庫</span><span class="sxs-lookup"><span data-stu-id="372be-109">A SharePoint document library</span></span>
- <span data-ttu-id="372be-110">Planner</span><span class="sxs-lookup"><span data-stu-id="372be-110">A Planner</span></span>
- <span data-ttu-id="372be-111">OneNote 筆記本</span><span class="sxs-lookup"><span data-stu-id="372be-111">A OneNote notebook</span></span>
- <span data-ttu-id="372be-112">Power BI</span><span class="sxs-lookup"><span data-stu-id="372be-112">Power BI</span></span>
- <span data-ttu-id="372be-113">Yammer （如果群組是由 Yammer 建立）</span><span class="sxs-lookup"><span data-stu-id="372be-113">Yammer (if the group was created from Yammer)</span></span>
- <span data-ttu-id="372be-114">小組（如果群組是從小組建立）</span><span class="sxs-lookup"><span data-stu-id="372be-114">A Team (if the group was created from Teams)</span></span>
- <span data-ttu-id="372be-115">藍圖（如果您有 web 的專案）</span><span class="sxs-lookup"><span data-stu-id="372be-115">Roadmap (if you have Project for the web)</span></span>

<span data-ttu-id="372be-116">使用 Microsoft 365 群組時，您不需要手動指派每個資源的許可權，因為新增人員至群組會自動為他們提供群組所提供之工具所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="372be-116">With a Microsoft 365 group, you don't have to manually assign permissions to each of these resources, because adding people to the group automatically gives them the permissions they need to the tools that the group provides.</span></span>

<span data-ttu-id="372be-117">除非您將[群組建立限制于一組特定的人員](manage-creation-of-groups.md)，否則任何使用者都可以建立群組。</span><span class="sxs-lookup"><span data-stu-id="372be-117">Any user can create a group unless you [limit group creation to a specific set of people](manage-creation-of-groups.md).</span></span> <span data-ttu-id="372be-118">請注意，如果您限制群組的建立，無法建立群組的使用者將無法建立 SharePoint 網站、規劃人員或小組。</span><span class="sxs-lookup"><span data-stu-id="372be-118">Note that if you limit group creation, users who cannot create groups will not be able to create SharePoint sites, Planners, or teams.</span></span> <span data-ttu-id="372be-119">這些服務要求建立群組的人員可以建立群組。</span><span class="sxs-lookup"><span data-stu-id="372be-119">These services require the people creating them to be able to create a group.</span></span> <span data-ttu-id="372be-120">使用者仍可參與群組活動，例如在 Planner 中建立工作或使用小組聊天，但前提是群組的成員。</span><span class="sxs-lookup"><span data-stu-id="372be-120">Users can still participate in group activities, such as creating tasks in Planner or using Teams chat, provided they are a member of the group.</span></span>

<span data-ttu-id="372be-121">群組具有下列角色：</span><span class="sxs-lookup"><span data-stu-id="372be-121">Groups have the following roles:</span></span>

- <span data-ttu-id="372be-122">**擁有**者-群組擁有者可以新增或移除成員，並具有獨特的許可權，例如從共用收件匣刪除交談的功能，或變更群組的不同設定。</span><span class="sxs-lookup"><span data-stu-id="372be-122">**Owners** - Group owners can add or remove members and have unique permissions like the ability to delete conversations from the shared inbox or change different settings about the group.</span></span> <span data-ttu-id="372be-123">群組擁有者可以重新命名群組、更新描述或圖片等等。</span><span class="sxs-lookup"><span data-stu-id="372be-123">Group owners can rename the group, update the description or picture and more.</span></span>
- <span data-ttu-id="372be-124">**Members** -成員可以存取群組中的所有專案，但無法變更群組設定。</span><span class="sxs-lookup"><span data-stu-id="372be-124">**Members** - Members can access everything in the group, but can't change group settings.</span></span> <span data-ttu-id="372be-125">依預設，群組成員可以邀請客人加入您的群組，但您可以[控制該設定](manage-guest-access-in-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="372be-125">By default group members can invite guests to join your group, though you can [control that setting](manage-guest-access-in-groups.md).</span></span>
- <span data-ttu-id="372be-126">**來賓**群組來賓是指來自組織外部的成員。</span><span class="sxs-lookup"><span data-stu-id="372be-126">**Guests** - Group guests are members who are from outside your organization.</span></span>

<span data-ttu-id="372be-127">只有全域系統管理員、使用者管理員和群組管理員可以在 Microsoft 365 系統管理中心建立及管理群組。</span><span class="sxs-lookup"><span data-stu-id="372be-127">Only global admins, user admins, and groups admins can create and manage groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="372be-128">您不能是委派的系統管理員 (例如，擔任系統管理員的顧問)。</span><span class="sxs-lookup"><span data-stu-id="372be-128">You can't be a delegated admin (for example, a consultant who is an admin on behalf of).</span></span>

<span data-ttu-id="372be-129">身為管理員，您可以：</span><span class="sxs-lookup"><span data-stu-id="372be-129">As an administrator, you can:</span></span>

- [<span data-ttu-id="372be-130">指定誰可以建立群組</span><span class="sxs-lookup"><span data-stu-id="372be-130">Specify who can create groups</span></span>](manage-creation-of-groups.md)
- [<span data-ttu-id="372be-131">為組織中的群組建立命名原則</span><span class="sxs-lookup"><span data-stu-id="372be-131">Create a naming policy for groups in your organization</span></span>](groups-naming-policy.md)
- [<span data-ttu-id="372be-132">選擇建立群組時所要使用的網域</span><span class="sxs-lookup"><span data-stu-id="372be-132">Choose which domain to use when creating a group</span></span>](choose-domain-to-create-groups.md)
- [<span data-ttu-id="372be-133">管理來賓存取群組</span><span class="sxs-lookup"><span data-stu-id="372be-133">Manage guest access to groups</span></span>](manage-guest-access-in-groups.md)
- <span data-ttu-id="372be-134">[復原已刪除的群組](restore-deleted-group.md)（在刪除30天內）</span><span class="sxs-lookup"><span data-stu-id="372be-134">[Recover a deleted group](restore-deleted-group.md) (within 30 days of deletion)</span></span>

<span data-ttu-id="372be-135">如果您想要更自動化的方法來管理 Microsoft 365 群組的生命週期，您可以使用到期原則，在特定的時間間隔內到期群組。</span><span class="sxs-lookup"><span data-stu-id="372be-135">If you prefer a more automated way to manage the lifecycle of your Microsoft 365 groups, you can use expiration policies to expire groups at a specific time interval.</span></span> <span data-ttu-id="372be-136">群組的擁有者會在群組到期前取得一封電子郵件30、15及1天，以允許使用者在仍需要時輕易更新群組。</span><span class="sxs-lookup"><span data-stu-id="372be-136">The group's owners will get an email 30, 15 and 1 day before the group expiration that allows them to easily renew the group if it's still needed.</span></span> <span data-ttu-id="372be-137">請參閱： [Microsoft 365 群組到期原則](office-365-groups-expiration-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="372be-137">See: [Microsoft 365 group Expiration Policy](office-365-groups-expiration-policy.md).</span></span>

<span data-ttu-id="372be-138">您可以從 Microsoft 365 系統管理中心或[使用 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)管理您的群組。</span><span class="sxs-lookup"><span data-stu-id="372be-138">You can administer your groups from the Microsoft 365 admin center or [by using PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).</span></span>

<span data-ttu-id="372be-139">如果您有許多使用者，例如在大型公司或企業中，您可能會有許多使用者出於各種目的而建立群組。</span><span class="sxs-lookup"><span data-stu-id="372be-139">If you have a lot of users, such as in a large corporation or enterprise, you may have many users who create groups for various purposes.</span></span> <span data-ttu-id="372be-140">強烈建議您複查[Microsoft 365 群組中](plan-for-groups-governance.md)的控管計畫，以取得最佳作法。</span><span class="sxs-lookup"><span data-stu-id="372be-140">We highly recommend that you review [Plan for governance in Microsoft 365 groups](plan-for-groups-governance.md) for best practices.</span></span>

## <a name="group-limits"></a><span data-ttu-id="372be-141">群組限制</span><span class="sxs-lookup"><span data-stu-id="372be-141">Group limits</span></span>

<span data-ttu-id="372be-142">下列限制適用于 Microsoft 365 群組：</span><span class="sxs-lookup"><span data-stu-id="372be-142">The following limits apply to Microsoft 365 Groups:</span></span>

|<span data-ttu-id="372be-143">最大。。。</span><span class="sxs-lookup"><span data-stu-id="372be-143">Maximum...</span></span>|<span data-ttu-id="372be-144">值</span><span class="sxs-lookup"><span data-stu-id="372be-144">Value</span></span>|
|:---------|:----|
|<span data-ttu-id="372be-145">Owners per group</span><span class="sxs-lookup"><span data-stu-id="372be-145">Owners per group</span></span>|<span data-ttu-id="372be-146">100</span><span class="sxs-lookup"><span data-stu-id="372be-146">100</span></span>|
|<span data-ttu-id="372be-147">Groups a user can create</span><span class="sxs-lookup"><span data-stu-id="372be-147">Groups a user can create</span></span>|<span data-ttu-id="372be-148">250</span><span class="sxs-lookup"><span data-stu-id="372be-148">250</span></span>|
|<span data-ttu-id="372be-149">管理員可以建立的群組</span><span class="sxs-lookup"><span data-stu-id="372be-149">Groups an admin can create</span></span>|<span data-ttu-id="372be-150">最高預設租使用者有500000位</span><span class="sxs-lookup"><span data-stu-id="372be-150">Up to default tenant limit of 500K</span></span>|
|<span data-ttu-id="372be-151">Number of members </span><span class="sxs-lookup"><span data-stu-id="372be-151">Number of members</span></span>|<span data-ttu-id="372be-152">超過1000，但只有1000可以同時存取群組交談。</span><span class="sxs-lookup"><span data-stu-id="372be-152">More than 1,000, though only 1,000 can access the Group conversations concurrently.</span></span> <br><span data-ttu-id="372be-153">使用者可能會注意到當存取 Outlook 中大量群組的行事曆和交談時，會發生延遲。</span><span class="sxs-lookup"><span data-stu-id="372be-153">Users might notice delays when accessing the calendar and conversations in very large groups in Outlook.</span></span>|
|<span data-ttu-id="372be-154">使用者可以是其成員的群組數目</span><span class="sxs-lookup"><span data-stu-id="372be-154">Number of Groups a user can be a member of</span></span>|<span data-ttu-id="372be-155">1,000</span><span class="sxs-lookup"><span data-stu-id="372be-155">1,000</span></span>|
|<span data-ttu-id="372be-156">檔存放區</span><span class="sxs-lookup"><span data-stu-id="372be-156">File storage</span></span>|<span data-ttu-id="372be-157">每個訂閱的使用者需要 1 tb + 10 GB + 購買的任何額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="372be-157">1 Terabyte + 10 GB per subscribed user + any additional storage purchased.</span></span> <span data-ttu-id="372be-158">您可以購買無限量的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="372be-158">You can purchase an unlimited amount of additional storage.</span></span>|
|<span data-ttu-id="372be-159">群組信箱大小</span><span class="sxs-lookup"><span data-stu-id="372be-159">Group Mailbox size</span></span>|<span data-ttu-id="372be-160">50 GB</span><span class="sxs-lookup"><span data-stu-id="372be-160">50 GB</span></span>|

<span data-ttu-id="372be-161">組織可以擁有的預設 Microsoft 365 群組數目為500000，但可按要求增加。</span><span class="sxs-lookup"><span data-stu-id="372be-161">The default maximum number of Microsoft 365 groups that an organization can have is 500,000, but can be increased by request.</span></span> <span data-ttu-id="372be-162">如需 Microsoft 365 群組限制的詳細資訊，請參閱[Microsoft 365 群組-系統管理](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)說明。</span><span class="sxs-lookup"><span data-stu-id="372be-162">For more information on Microsoft 365 Groups limits, see [Microsoft 365 Groups - Admin help](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>

<span data-ttu-id="372be-163">當您具有群組使用量的可操作資訊時，管理 Microsoft 365 群組會更有效。</span><span class="sxs-lookup"><span data-stu-id="372be-163">Managing your Microsoft 365 groups is more effective when you have actionable information about groups usage.</span></span> <span data-ttu-id="372be-164">Microsoft 365 系統管理中心有一個報告工具，可讓您查看儲存空間使用方式、您擁有的使用中群組數目，甚至是使用者使用群組的方式。</span><span class="sxs-lookup"><span data-stu-id="372be-164">The Microsoft 365 admin center has a reporting tool that can let you see things such as storage use, how many active groups you have and even how your users are using the groups.</span></span> <span data-ttu-id="372be-165">如需詳細資訊，請參閱： [admin center 中的 Microsoft 365 報告](../activity-reports/office-365-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="372be-165">See: [Microsoft 365 Reports in the admin center](../activity-reports/office-365-groups.md) for more information.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="372be-166">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="372be-166">Sensitivity labels</span></span>

<span data-ttu-id="372be-167">您可以建立您組織中的使用者在建立 Microsoft 365 群組時所能設定的靈敏度標籤。</span><span class="sxs-lookup"><span data-stu-id="372be-167">You can create sensitivity labels that the users in your organization can set when they create an Microsoft 365 group.</span></span> <span data-ttu-id="372be-168">您可以使用敏感度標籤設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="372be-168">With sensitivity labels, you can configure:</span></span> 

- <span data-ttu-id="372be-169">隱私權（公開或私人）</span><span class="sxs-lookup"><span data-stu-id="372be-169">Privacy (public or private)</span></span>
- <span data-ttu-id="372be-170">外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="372be-170">External users access</span></span>
- <span data-ttu-id="372be-171">未受管理的裝置存取</span><span class="sxs-lookup"><span data-stu-id="372be-171">Unmanaged device access</span></span>

<span data-ttu-id="372be-172">例如，您可以建立一個名為「*高度機密*」的標籤，並指定使用此標籤建立的任何群組都是私人的，而不允許外部使用者。</span><span class="sxs-lookup"><span data-stu-id="372be-172">For example, you can create a label called *Highly Confidential* and specify that any group created with this label will be private and not allow external users.</span></span> <span data-ttu-id="372be-173">當您組織中的使用者在建立群組時選取此標籤時，會將群組設定為 [私人]，而且不允許群組成員將外部使用者新增至群組。</span><span class="sxs-lookup"><span data-stu-id="372be-173">When users in your organization select this label during group creation, the group will be set to private and group members will be not be allowed to add external users to the group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="372be-174">如果您目前使用的是分類標籤，當啟用敏感度標籤之後，建立群組的使用者將無法再使用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="372be-174">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span> 

<span data-ttu-id="372be-175">如需建立、管理及使用敏感度標籤的詳細資訊，請參閱[使用敏感度標籤來保護 Microsoft 團隊、microsoft 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="372be-175">For information about creating, managing, and using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="which-microsoft-365-plans-include-groups"></a><span data-ttu-id="372be-176">哪些 Microsoft 365 方案包含群組？</span><span class="sxs-lookup"><span data-stu-id="372be-176">Which Microsoft 365 plans include groups?</span></span>

<span data-ttu-id="372be-177">任何有 Exchange Online 和 SharePoint 線上的 Microsoft 365 訂閱都會支援群組。</span><span class="sxs-lookup"><span data-stu-id="372be-177">Any Microsoft 365 subscription that has Exchange Online and SharePoint Online will support groups.</span></span> <span data-ttu-id="372be-178">包括商務基本版和商務用的方案，以及 Enterprise E1、E3 和 E5 計畫。</span><span class="sxs-lookup"><span data-stu-id="372be-178">That includes the Business Essentials and Business Premium plans, and the Enterprise E1, E3 and E5 plans.</span></span> <span data-ttu-id="372be-179">群組會接受建立群組的人員授權（也稱為群組的「召集人」）。</span><span class="sxs-lookup"><span data-stu-id="372be-179">The group takes on the licensing of the person who creates the group (also known as the "organizer" of the group).</span></span> <span data-ttu-id="372be-180">只要召集人具有您想要群組擁有的任何功能的適當授權，該授權就會傳遞給群組。</span><span class="sxs-lookup"><span data-stu-id="372be-180">As long as the organizer has the proper license for whatever features you want the group to have, that license will convey to the group.</span></span>

> [!NOTE]
> <span data-ttu-id="372be-181">如需 Microsoft 365 服務系列與方案的詳細資訊，請參閱[microsoft 365 方案選項](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。</span><span class="sxs-lookup"><span data-stu-id="372be-181">For more details about Microsoft 365 service families and plans, see [Microsoft 365 plan options](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span></span>

<span data-ttu-id="372be-182">如果您有僅限 Exchange 的計畫，您仍然可以在 Outlook 中取得群組的共用收件匣和共用行事曆功能，但不會取得文件庫、Planner 或任何其他功能。</span><span class="sxs-lookup"><span data-stu-id="372be-182">If you have an Exchange-only plan you can still get the shared inbox and shared calendar features of groups in Outlook but you won't get the document library, Planner or any of the other capabilities.</span></span>

<span data-ttu-id="372be-183">Microsoft 365 群組使用 Azure Active Directory （AAD）。</span><span class="sxs-lookup"><span data-stu-id="372be-183">Microsoft 365 groups work with Azure Active Directory (AAD).</span></span> <span data-ttu-id="372be-184">您取得的群組功能取決於您所擁有的 Azure Active Directory 訂閱，以及指派給群組召集人的授權。</span><span class="sxs-lookup"><span data-stu-id="372be-184">The groups features you get depends on which Azure Active Directory subscription you have, and what license(s) is assigned to the organizer of the group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="372be-185">針對所有群組功能，如果您有 Azure AD Premium 訂閱，使用者可以加入群組，不論他們是否已指派 AAD P1 授權。</span><span class="sxs-lookup"><span data-stu-id="372be-185">For all the groups features, if you have an Azure AD Premium subscription, users can join the group whether or not they have an AAD P1 license assigned to them.</span></span> <span data-ttu-id="372be-186">不會強制執行授權。</span><span class="sxs-lookup"><span data-stu-id="372be-186">Licensing isn't enforced.</span></span>
> <span data-ttu-id="372be-187">我們會定期產生使用方式報告，告訴您哪些使用者已遺失授權，而且需要指派給他們，以符合授權要求。</span><span class="sxs-lookup"><span data-stu-id="372be-187">Periodically we will generate usage reports that tell you which users are missing a license, and need one assigned to them to be compliant with the licensing requirements.</span></span> <span data-ttu-id="372be-188">例如，假設使用者沒有授權，而且會將其新增至強制執行命名原則的群組中。</span><span class="sxs-lookup"><span data-stu-id="372be-188">For example, let's say a user doesn't have a license and they are added to a group where the naming policy is enforced.</span></span> <span data-ttu-id="372be-189">報告會標示您需要授權。</span><span class="sxs-lookup"><span data-stu-id="372be-189">The report will flag for you that they need a license.</span></span>

## <a name="related-articles"></a><span data-ttu-id="372be-190">相關文章</span><span class="sxs-lookup"><span data-stu-id="372be-190">Related articles</span></span>

[<span data-ttu-id="372be-191">深入瞭解 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="372be-191">Learn about Microsoft 365 Groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="372be-192">將通訊群組清單升級至 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="372be-192">Upgrade distribution lists to Microsoft 365 Groups</span></span>](../manage/upgrade-distribution-lists.md)

[<span data-ttu-id="372be-193">使用 PowerShell 管理 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="372be-193">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[<span data-ttu-id="372be-194">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="372be-194">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
