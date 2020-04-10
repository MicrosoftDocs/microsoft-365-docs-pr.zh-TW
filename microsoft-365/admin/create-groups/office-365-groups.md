---
title: 管理員的 Office 365 群組概述
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
search.appverid:
- BCS160
- MET150
- MOE150
description: 深入瞭解 Office 365 群組。
ms.openlocfilehash: f5a0b72737a360a4bfe4cdd8fee4a08b7a7ff236
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212530"
---
# <a name="overview-of-office-365-groups-for-administrators"></a><span data-ttu-id="d0ca5-103">管理員的 Office 365 群組概述</span><span class="sxs-lookup"><span data-stu-id="d0ca5-103">Overview of Office 365 groups for administrators</span></span>

<span data-ttu-id="d0ca5-104">Office 365 群組是一種基礎成員資格服務，可促進整個 Microsoft 365 的所有團隊合作。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-104">Office 365 groups is the foundational membership service that drives all teamwork across Microsoft 365.</span></span> <span data-ttu-id="d0ca5-105">您可以使用 Office 365 群組，讓一群人員能夠存取共同作業資源的集合，供他們共用。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-105">With Office 365 groups, you can give a group of people access to a collection of collaboration resources for those people to share.</span></span> <span data-ttu-id="d0ca5-106">這些資源包括：</span><span class="sxs-lookup"><span data-stu-id="d0ca5-106">These resources include:</span></span>

- <span data-ttu-id="d0ca5-107">共用的 Outlook 收件匣</span><span class="sxs-lookup"><span data-stu-id="d0ca5-107">A shared Outlook inbox</span></span>
- <span data-ttu-id="d0ca5-108">共用行事曆</span><span class="sxs-lookup"><span data-stu-id="d0ca5-108">A shared calendar</span></span>
- <span data-ttu-id="d0ca5-109">SharePoint 文件庫</span><span class="sxs-lookup"><span data-stu-id="d0ca5-109">A SharePoint document library</span></span>
- <span data-ttu-id="d0ca5-110">Planner</span><span class="sxs-lookup"><span data-stu-id="d0ca5-110">A Planner</span></span>
- <span data-ttu-id="d0ca5-111">Power BI</span><span class="sxs-lookup"><span data-stu-id="d0ca5-111">Power BI</span></span>
- <span data-ttu-id="d0ca5-112">Yammer （如果群組是由 Yammer 建立）</span><span class="sxs-lookup"><span data-stu-id="d0ca5-112">Yammer (if the group was created from Yammer)</span></span>
- <span data-ttu-id="d0ca5-113">小組（如果群組是從小組建立）</span><span class="sxs-lookup"><span data-stu-id="d0ca5-113">A Team (if the group was created from Teams)</span></span>
- <span data-ttu-id="d0ca5-114">藍圖（如果您有 web 的專案）</span><span class="sxs-lookup"><span data-stu-id="d0ca5-114">Roadmap (if you have Project for the web)</span></span>

<span data-ttu-id="d0ca5-115">使用 Office 365 群組時，您不需要手動指派每個資源的許可權，因為新增人員至群組會自動為他們提供群組所提供之工具所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-115">With an Office 365 group, you don’t have to manually assign permissions to each of these resources, because adding people to the group automatically gives them the permissions they need to the tools that the group provides.</span></span>

<span data-ttu-id="d0ca5-116">除非您將[群組建立限制于一組特定的人員](manage-creation-of-groups.md)，否則任何 Office 365 使用者都可以建立群組。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-116">Any Office 365 user can create a group unless you [limit group creation to a specific set of people](manage-creation-of-groups.md).</span></span> <span data-ttu-id="d0ca5-117">請注意，如果您限制群組的建立，無法建立群組的使用者將無法建立 SharePoint 網站、規劃人員或小組。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-117">Note that if you limit group creation, users who cannot create groups will not be able to create SharePoint sites, Planners, or teams.</span></span> <span data-ttu-id="d0ca5-118">這些服務要求建立群組的人員可以建立群組。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-118">These services require the people creating them to be able to create a group.</span></span> <span data-ttu-id="d0ca5-119">使用者仍可參與群組活動，例如在 Planner 中建立工作或使用小組聊天，但前提是群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-119">Users can still participate in group activities, such as creating tasks in Planner or using Teams chat, provided they are a member of the group.</span></span>

<span data-ttu-id="d0ca5-120">群組具有下列角色：</span><span class="sxs-lookup"><span data-stu-id="d0ca5-120">Groups have the following roles:</span></span>

- <span data-ttu-id="d0ca5-121">**擁有**者-群組擁有者可以新增或移除成員，並具有獨特的許可權，例如從共用收件匣刪除交談的功能，或變更群組的不同設定。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-121">**Owners** - Group owners can add or remove members and have unique permissions like the ability to delete conversations from the shared inbox or change different settings about the group.</span></span> <span data-ttu-id="d0ca5-122">群組擁有者可以重新命名群組、更新描述或圖片等等。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-122">Group owners can rename the group, update the description or picture and more.</span></span>
- <span data-ttu-id="d0ca5-123">**Members** -成員可以存取群組中的所有專案，但無法變更群組設定。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-123">**Members** - Members can access everything in the group, but can't change group settings.</span></span> <span data-ttu-id="d0ca5-124">依預設，群組成員可以邀請客人加入您的群組，但您可以[控制該設定](manage-guest-access-in-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-124">By default group members can invite guests to join your group, though you can [control that setting](manage-guest-access-in-groups.md).</span></span>
- <span data-ttu-id="d0ca5-125">**來賓**群組來賓是指來自組織外部的成員。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-125">**Guests** - Group guests are members who are from outside your organization.</span></span>

<span data-ttu-id="d0ca5-126">只有全域系統管理員、使用者管理員和群組管理員可以在 Microsoft 365 系統管理中心建立及管理群組。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-126">Only global admins, user admins, and groups admins can create and manage groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d0ca5-127">您不能是委派的系統管理員 (例如，擔任系統管理員的顧問)。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-127">You can't be a delegated admin (for example, a consultant who is an admin on behalf of).</span></span>

<span data-ttu-id="d0ca5-128">身為管理員，您可以：</span><span class="sxs-lookup"><span data-stu-id="d0ca5-128">As an administrator, you can:</span></span>

- [<span data-ttu-id="d0ca5-129">指定誰可以建立群組</span><span class="sxs-lookup"><span data-stu-id="d0ca5-129">Specify who can create groups</span></span>](manage-creation-of-groups.md)
- [<span data-ttu-id="d0ca5-130">為組織中的群組建立命名原則</span><span class="sxs-lookup"><span data-stu-id="d0ca5-130">Create a naming policy for groups in your organization</span></span>](groups-naming-policy.md)
- [<span data-ttu-id="d0ca5-131">選擇建立群組時所要使用的網域</span><span class="sxs-lookup"><span data-stu-id="d0ca5-131">Choose which domain to use when creating a group</span></span>](choose-domain-to-create-groups.md)
- [<span data-ttu-id="d0ca5-132">管理群組的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="d0ca5-132">Manage guest access to groups</span></span>](manage-guest-access-in-groups.md)
- <span data-ttu-id="d0ca5-133">[復原已刪除的群組](restore-deleted-group.md)（在刪除30天內）</span><span class="sxs-lookup"><span data-stu-id="d0ca5-133">[Recover a deleted group](restore-deleted-group.md) (within 30 days of deletion)</span></span>

<span data-ttu-id="d0ca5-134">如果您傾向于管理 Office 365 群組的生命週期，使用一種更為自動化的方式，您可以使用到期原則，在特定的時間間隔內到期群組。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-134">If you prefer a more automated way to manage the lifecycle of your Office 365 groups, you can use expiration policies to expire groups at a specific time interval.</span></span> <span data-ttu-id="d0ca5-135">群組的擁有者會在群組到期前取得一封電子郵件30、15及1天，以允許使用者在仍需要時輕易更新群組。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-135">The group's owners will get an email 30, 15 and 1 day before the group expiration that allows them to easily renew the group if it's still needed.</span></span> <span data-ttu-id="d0ca5-136">請參閱： [Office 365 群組到期原則](office-365-groups-expiration-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-136">See: [Office 365 Group Expiration Policy](office-365-groups-expiration-policy.md).</span></span>

<span data-ttu-id="d0ca5-137">您可以從 Microsoft 365 系統管理中心或[使用 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)管理您的群組。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-137">You can administer your groups from the Microsoft 365 admin center or [by using PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).</span></span>

<span data-ttu-id="d0ca5-138">如果您有許多使用者，例如在大型公司或企業中，您可能會有許多使用者出於各種目的而建立群組。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-138">If you have a lot of users, such as in a large corporation or enterprise, you may have many users who create groups for various purposes.</span></span> <span data-ttu-id="d0ca5-139">強烈建議您複查[Office 365 群組中](plan-for-groups-governance.md)的控管計畫，以取得最佳作法。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-139">We highly recommend that you review [Plan for governance in Office 365 Groups](plan-for-groups-governance.md) for best practices.</span></span>

## <a name="group-limits"></a><span data-ttu-id="d0ca5-140">群組限制</span><span class="sxs-lookup"><span data-stu-id="d0ca5-140">Group limits</span></span>

<span data-ttu-id="d0ca5-141">下列限制適用于 Office 365 群組：</span><span class="sxs-lookup"><span data-stu-id="d0ca5-141">The following limits apply to Office 365 groups:</span></span>

|<span data-ttu-id="d0ca5-142">最大。。。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-142">Maximum...</span></span>|<span data-ttu-id="d0ca5-143">值</span><span class="sxs-lookup"><span data-stu-id="d0ca5-143">Value</span></span>|
|:---------|:----|
|<span data-ttu-id="d0ca5-144">Owners per group</span><span class="sxs-lookup"><span data-stu-id="d0ca5-144">Owners per group</span></span>|<span data-ttu-id="d0ca5-145">100</span><span class="sxs-lookup"><span data-stu-id="d0ca5-145">100</span></span>|
|<span data-ttu-id="d0ca5-146">Groups a user can create</span><span class="sxs-lookup"><span data-stu-id="d0ca5-146">Groups a user can create</span></span>|<span data-ttu-id="d0ca5-147">250</span><span class="sxs-lookup"><span data-stu-id="d0ca5-147">250</span></span>|
|<span data-ttu-id="d0ca5-148">管理員可以建立的群組</span><span class="sxs-lookup"><span data-stu-id="d0ca5-148">Groups an admin can create</span></span>|<span data-ttu-id="d0ca5-149">最高預設租使用者有500000位</span><span class="sxs-lookup"><span data-stu-id="d0ca5-149">Up to default tenant limit of 500K</span></span>|
|<span data-ttu-id="d0ca5-150">Number of members </span><span class="sxs-lookup"><span data-stu-id="d0ca5-150">Number of members</span></span>|<span data-ttu-id="d0ca5-151">超過1000，但只有1000可以同時存取群組交談。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-151">More than 1,000, though only 1,000 can access the Group conversations concurrently.</span></span> <br><span data-ttu-id="d0ca5-152">使用者可能會注意到當存取 Outlook 中大量群組的行事曆和交談時，會發生延遲。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-152">Users might notice delays when accessing the calendar and conversations in very large groups in Outlook.</span></span>|
|<span data-ttu-id="d0ca5-153">使用者可以是其成員的群組數目</span><span class="sxs-lookup"><span data-stu-id="d0ca5-153">Number of Groups a user can be a member of</span></span>|<span data-ttu-id="d0ca5-154">1,000</span><span class="sxs-lookup"><span data-stu-id="d0ca5-154">1,000</span></span>|
|<span data-ttu-id="d0ca5-155">檔存放區</span><span class="sxs-lookup"><span data-stu-id="d0ca5-155">File storage</span></span>|<span data-ttu-id="d0ca5-156">每個訂閱的使用者需要 1 tb + 10 GB + 購買的任何額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-156">1 Terabyte + 10 GB per subscribed user + any additional storage purchased.</span></span> <span data-ttu-id="d0ca5-157">您可以購買無限量的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-157">You can purchase an unlimited amount of additional storage.</span></span>|
|<span data-ttu-id="d0ca5-158">群組信箱大小</span><span class="sxs-lookup"><span data-stu-id="d0ca5-158">Group Mailbox size</span></span>|<span data-ttu-id="d0ca5-159">50 GB</span><span class="sxs-lookup"><span data-stu-id="d0ca5-159">50 GB</span></span>|

<span data-ttu-id="d0ca5-160">Office 365 組織可以擁有的預設 Office 365 群組數目上限為500000，但可按要求增加。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-160">The default maximum number of Office 365 groups that an Office 365 organization can have is 500,000, but can be increased by request.</span></span> <span data-ttu-id="d0ca5-161">如需 Office 365 群組限制的詳細資訊，請參閱[office 365 群組-系統管理](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)說明。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-161">For more information on Office 365 groups limits, see [Office 365 Groups - Admin help](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx).</span></span>

<span data-ttu-id="d0ca5-162">當您具有群組使用量的可操作資訊時，管理 Office 365 群組會更有效。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-162">Managing your Office 365 groups is more effective when you have actionable information about groups usage.</span></span> <span data-ttu-id="d0ca5-163">Microsoft 365 系統管理中心有一個報告工具，可讓您查看儲存空間使用方式、您擁有的使用中群組數目，甚至是使用者使用群組的方式。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-163">The Microsoft 365 admin center has a reporting tool that can let you see things such as storage use, how many active groups you have and even how your users are using the groups.</span></span> <span data-ttu-id="d0ca5-164">如需詳細資訊，請參閱： [admin center 中的 Office 365 報告](../activity-reports/office-365-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-164">See: [Office 365 Reports in the admin center](../activity-reports/office-365-groups.md) for more information.</span></span>

## <a name="which-office-365-plans-include-groups"></a><span data-ttu-id="d0ca5-165">哪些 Office 365 方案包含群組？</span><span class="sxs-lookup"><span data-stu-id="d0ca5-165">Which Office 365 plans include groups?</span></span>

<span data-ttu-id="d0ca5-166">任何有 Exchange Online 和 SharePoint 線上的 Office 365 訂閱都會支援群組。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-166">Any Office 365 subscription that has Exchange Online and SharePoint Online will support groups.</span></span> <span data-ttu-id="d0ca5-167">包括商務基本版和商務用的方案，以及 Enterprise E1、E3 和 E5 計畫。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-167">That includes the Business Essentials and Business Premium plans, and the Enterprise E1, E3 and E5 plans.</span></span> <span data-ttu-id="d0ca5-168">群組會接受建立群組的人員授權（也稱為群組的「召集人」）。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-168">The group takes on the licensing of the person who creates the group (also known as the "organizer" of the group).</span></span> <span data-ttu-id="d0ca5-169">只要召集人具有您想要群組擁有的任何功能的適當授權，該授權就會傳遞給群組。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-169">As long as the organizer has the proper license for whatever features you want the group to have, that license will convey to the group.</span></span>

> [!NOTE]
> <span data-ttu-id="d0ca5-170">如需有關 Office 365 服務系列與方案的詳細資訊，請參閱[office 365 方案選項](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</span><span class="sxs-lookup"><span data-stu-id="d0ca5-170">For more details about Office 365 service families and plans, see [Office 365 plan options](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</span></span>

<span data-ttu-id="d0ca5-171">如果您有僅限 Exchange 的計畫，您仍然可以在 Outlook 中取得群組的共用收件匣和共用行事曆功能，但不會取得文件庫、Planner 或任何其他功能。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-171">If you have an Exchange-only plan you can still get the shared inbox and shared calendar features of groups in Outlook but you won’t get the document library, Planner or any of the other capabilities.</span></span>

<span data-ttu-id="d0ca5-172">Office 365 群組可搭配 Azure Active Directory （AAD）使用。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-172">Office 365 groups work with Azure Active Directory (AAD).</span></span> <span data-ttu-id="d0ca5-173">您取得的群組功能取決於您所擁有的 Azure Active Directory 訂閱，以及指派給群組召集人的授權。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-173">The groups features you get depends on which Azure Active Directory subscription you have, and what license(s) is assigned to the organizer of the group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0ca5-174">針對所有群組功能，如果您有 Azure AD Premium 訂閱，使用者可以加入群組，不論他們是否已指派 AAD P1 授權。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-174">For all the groups features, if you have an Azure AD Premium subscription, users can join the group whether or not they have an AAD P1 license assigned to them.</span></span> <span data-ttu-id="d0ca5-175">不會強制執行授權。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-175">Licensing isn't enforced.</span></span>
> <span data-ttu-id="d0ca5-176">我們會定期產生使用方式報告，告訴您哪些使用者已遺失授權，而且需要指派給他們，以符合授權要求。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-176">Periodically we will generate usage reports that tell you which users are missing a license, and need one assigned to them to be compliant with the licensing requirements.</span></span> <span data-ttu-id="d0ca5-177">例如，假設使用者沒有授權，而且會將其新增至強制執行命名原則的群組中。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-177">For example, let's say a user doesn't have a license and they are added to a group where the naming policy is enforced.</span></span> <span data-ttu-id="d0ca5-178">報告會標示您需要授權。</span><span class="sxs-lookup"><span data-stu-id="d0ca5-178">The report will flag for you that they need a license.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d0ca5-179">相關文章</span><span class="sxs-lookup"><span data-stu-id="d0ca5-179">Related articles</span></span>

[<span data-ttu-id="d0ca5-180">了解 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d0ca5-180">Learn about Office 365 Groups</span></span>](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="d0ca5-181">將通訊群組清單升級至 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d0ca5-181">Upgrade distribution lists to Office 365 Groups</span></span>](../manage/upgrade-distribution-lists.md)

[<span data-ttu-id="d0ca5-182">使用 PowerShell 管理 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d0ca5-182">Manage Office 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[<span data-ttu-id="d0ca5-183">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="d0ca5-183">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
