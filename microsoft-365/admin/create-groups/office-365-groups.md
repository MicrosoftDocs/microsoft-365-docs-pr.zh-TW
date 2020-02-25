---
title: 系統管理員的 Office 365 群組概觀
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: v-teflor
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
description: 了解 Office 365 群組。
ms.openlocfilehash: e7a65c41d4ecdbc91e163d9a84241ae549a2f9ec
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239174"
---
# <a name="overview-of-office-365-groups-for-administrators"></a><span data-ttu-id="18c3c-103">系統管理員的 Office 365 群組概觀</span><span class="sxs-lookup"><span data-stu-id="18c3c-103">Overview of Office 365 Groups for administrators</span></span>

<span data-ttu-id="18c3c-104">Office 365 群組是在整個 Microsoft 365 的磁碟機所有團隊合作置於成員資格服務。</span><span class="sxs-lookup"><span data-stu-id="18c3c-104">Office 365 Groups is the foundational membership service that drives all teamwork across Microsoft 365.</span></span> <span data-ttu-id="18c3c-105">與 Office 365 群組，您可以授與一群人存取這些人共用的共同作業資源的集合。</span><span class="sxs-lookup"><span data-stu-id="18c3c-105">With Office 365 Groups, you can give a group of people access to a collection of collaboration resources for those people to share.</span></span> <span data-ttu-id="18c3c-106">這些資源，包括：</span><span class="sxs-lookup"><span data-stu-id="18c3c-106">These resources include:</span></span>

- <span data-ttu-id="18c3c-107">共用的 Outlook 收件匣</span><span class="sxs-lookup"><span data-stu-id="18c3c-107">A shared Outlook inbox</span></span>
- <span data-ttu-id="18c3c-108">共用行事曆</span><span class="sxs-lookup"><span data-stu-id="18c3c-108">A shared calendar</span></span>
- <span data-ttu-id="18c3c-109">SharePoint 文件庫</span><span class="sxs-lookup"><span data-stu-id="18c3c-109">A SharePoint document library</span></span>
- <span data-ttu-id="18c3c-110">會議規劃</span><span class="sxs-lookup"><span data-stu-id="18c3c-110">A Planner</span></span>
- <span data-ttu-id="18c3c-111">Power BI</span><span class="sxs-lookup"><span data-stu-id="18c3c-111">Power BI</span></span>
- <span data-ttu-id="18c3c-112">Yammer （如果群組當初用來建立 Yammer）</span><span class="sxs-lookup"><span data-stu-id="18c3c-112">Yammer (if the group was created from Yammer)</span></span>
- <span data-ttu-id="18c3c-113">小組 （如果群組已建立從 microsoft Teams）</span><span class="sxs-lookup"><span data-stu-id="18c3c-113">A Team (if the group was created from Teams)</span></span>
- <span data-ttu-id="18c3c-114">藍圖 （如果您有 web 專案）</span><span class="sxs-lookup"><span data-stu-id="18c3c-114">Roadmap (if you have Project for the web )</span></span>

<span data-ttu-id="18c3c-115">與 Office 365 群組，您不需要以手動方式將權限指派給每個這些資源，因為新增至群組的成員會自動提供給他們所需的權限群組提供的工具。</span><span class="sxs-lookup"><span data-stu-id="18c3c-115">With an Office 365 group, you don’t have to manually assign permissions to each of these resources, because adding members to the group automatically gives them the permissions they need to the tools that the group provides.</span></span>

<span data-ttu-id="18c3c-116">Office 365 中的任何使用者可以建立群組，除非您[限制群組建立一組特定的人員](manage-creation-of-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="18c3c-116">Any Office 365 user can create a group unless you [limit group creation to a specific set of people](manage-creation-of-groups.md).</span></span> <span data-ttu-id="18c3c-117">請注意，是否您限制建立群組，無法建立群組的使用者將無法建立 SharePoint 網站、 規劃人員或團隊。</span><span class="sxs-lookup"><span data-stu-id="18c3c-117">Note that if you limit group creation, users who cannot create groups will not be able to create SharePoint sites, Planners, or teams.</span></span> <span data-ttu-id="18c3c-118">這些服務必須能夠使用建立群組的使用者內容。</span><span class="sxs-lookup"><span data-stu-id="18c3c-118">These services need to be able to create a group using the user context.</span></span> <span data-ttu-id="18c3c-119">使用者仍可以參與群組活動，例如在 Planner 中建立工作，或回應交談在 Outlook 中，提供他們是群組的成員。</span><span class="sxs-lookup"><span data-stu-id="18c3c-119">Users can still participate in group activities, such as creating tasks in Planner or responding to conversations in Outlook, provided they are a member of the group.</span></span>

<span data-ttu-id="18c3c-120">群組擁有下列角色：</span><span class="sxs-lookup"><span data-stu-id="18c3c-120">Groups have the following roles:</span></span>

- <span data-ttu-id="18c3c-121">**擁有者**群組擁有者可以新增或移除成員及擁有獨特的權限，像是從共用收件匣中刪除交談，或變更群組的相關的不同設定的能力。</span><span class="sxs-lookup"><span data-stu-id="18c3c-121">**Owners** - Group owners can add or remove members and have unique permissions like the ability to delete conversations from the shared inbox or change different settings about the group.</span></span> <span data-ttu-id="18c3c-122">群組擁有者可以重新命名群組，請更新描述或圖片等等。</span><span class="sxs-lookup"><span data-stu-id="18c3c-122">Group owners can rename the group, update the description or picture and more.</span></span>
- <span data-ttu-id="18c3c-123">**成員**的成員可以存取在] 群組中的所有項目，但不能變更群組設定。</span><span class="sxs-lookup"><span data-stu-id="18c3c-123">**Members** - Members can access everything in the group, but can't change group settings.</span></span>
- <span data-ttu-id="18c3c-124">**來賓**-群組來賓都是來自組織外部的成員。</span><span class="sxs-lookup"><span data-stu-id="18c3c-124">**Guests** - Group guests are members who are from outside your organization.</span></span> <span data-ttu-id="18c3c-125">預設群組成員可以邀請來賓加入您的群組，但是您可以[控制設定](manage-guest-access-in-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="18c3c-125">By default group members can invite guests to join your group, though you can [control that setting](manage-guest-access-in-groups.md).</span></span>

<span data-ttu-id="18c3c-126">只有全域系統管理員和使用者管理系統管理員可以建立及管理在系統管理中心中的群組。</span><span class="sxs-lookup"><span data-stu-id="18c3c-126">Only global admins and user management admins can create and manage groups in the admin center.</span></span> <span data-ttu-id="18c3c-127">您不能是委派的系統管理員 (例如，擔任系統管理員的顧問)。</span><span class="sxs-lookup"><span data-stu-id="18c3c-127">You can't be a delegated admin (for example, a consultant who is an admin on behalf of).</span></span>

<span data-ttu-id="18c3c-128">身為管理員，您可以：</span><span class="sxs-lookup"><span data-stu-id="18c3c-128">As an administrator, you can:</span></span>

- [<span data-ttu-id="18c3c-129">指定誰可以建立群組</span><span class="sxs-lookup"><span data-stu-id="18c3c-129">Specify who can create groups</span></span>](manage-creation-of-groups.md)
- [<span data-ttu-id="18c3c-130">在您的組織中建立群組命名原則</span><span class="sxs-lookup"><span data-stu-id="18c3c-130">Create a naming policy for groups in your organization</span></span>](groups-naming-policy.md)
- <span data-ttu-id="18c3c-131">[選擇 [建立群組時要使用哪一個網域](choose-domain-to-create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="18c3c-131">[Choose which domain to use when creating a group](choose-domain-to-create-groups.md)</span></span>
- [<span data-ttu-id="18c3c-132">管理群組的來賓存取</span><span class="sxs-lookup"><span data-stu-id="18c3c-132">Manage guest access to groups</span></span>](manage-guest-access-in-groups.md)
- <span data-ttu-id="18c3c-133">[復原已刪除的群組](restore-deleted-group.md)（位於內的 [刪除的 30 天）</span><span class="sxs-lookup"><span data-stu-id="18c3c-133">[Recover a deleted group](restore-deleted-group.md) (within 30 days of deletion)</span></span>

<span data-ttu-id="18c3c-134">如果您偏好使用更自動化的方式來管理您的 Office 365 群組的生命週期您可以在特定時間間隔到期群組使用到期原則。</span><span class="sxs-lookup"><span data-stu-id="18c3c-134">If you prefer a more automated way to manage the lifecycle of your Office 365 Groups you can use expiration policies to expire groups at a specific time interval.</span></span> <span data-ttu-id="18c3c-135">群組的擁有者會收到密碼，讓他們能輕鬆地更新 「 群組，如果仍然需要群組到期前，電子郵件 30 度、 15 和 1 天。</span><span class="sxs-lookup"><span data-stu-id="18c3c-135">The group's owners will get an email 30, 15 and 1 day before the group expiration that allows them to easily renew the group if it's still needed.</span></span> <span data-ttu-id="18c3c-136">請參閱： [Office 365 群組到期原則](office-365-groups-expiration-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="18c3c-136">See: [Office 365 Group Expiration Policy](office-365-groups-expiration-policy.md).</span></span>

<span data-ttu-id="18c3c-137">您可以從 Microsoft 365 系統管理中心或[使用 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)來管理您的群組。</span><span class="sxs-lookup"><span data-stu-id="18c3c-137">You can administer your groups from the Microsoft 365 admin center or [by using PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).</span></span>

<span data-ttu-id="18c3c-138">如果您有許多使用者，例如中大型公司或企業版，您可能有多位使用者能夠建立各種用途的群組。</span><span class="sxs-lookup"><span data-stu-id="18c3c-138">If you have a lot of users, such as in a large corporation or enterprise, you may have many users who create groups for various purposes.</span></span> <span data-ttu-id="18c3c-139">我們強烈建議您檢閱[ Plan for Office 365 群組中的控管](plan-for-groups-governance.md)的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="18c3c-139">We highly recommend that you review [Plan for governance in Office 365 Groups](plan-for-groups-governance.md) for best practices.</span></span>

## <a name="group-limits"></a><span data-ttu-id="18c3c-140">群組限制</span><span class="sxs-lookup"><span data-stu-id="18c3c-140">Group limits</span></span>

<span data-ttu-id="18c3c-141">下列限制適用於 Office 365 群組：</span><span class="sxs-lookup"><span data-stu-id="18c3c-141">The following limits apply to Office 365 Groups:</span></span>

|<span data-ttu-id="18c3c-142">最大值...]</span><span class="sxs-lookup"><span data-stu-id="18c3c-142">Maximum...</span></span>|<span data-ttu-id="18c3c-143">值</span><span class="sxs-lookup"><span data-stu-id="18c3c-143">Value</span></span>|
|:---------|:----|
|<span data-ttu-id="18c3c-144">Owners per group</span><span class="sxs-lookup"><span data-stu-id="18c3c-144">Owners per group</span></span>|<span data-ttu-id="18c3c-145">100</span><span class="sxs-lookup"><span data-stu-id="18c3c-145">100</span></span>|
|<span data-ttu-id="18c3c-146">Groups a user can create</span><span class="sxs-lookup"><span data-stu-id="18c3c-146">Groups a user can create</span></span>|<span data-ttu-id="18c3c-147">250</span><span class="sxs-lookup"><span data-stu-id="18c3c-147">250</span></span>|
|<span data-ttu-id="18c3c-148">群組的系統管理員可以建立</span><span class="sxs-lookup"><span data-stu-id="18c3c-148">Groups an admin can create</span></span>|<span data-ttu-id="18c3c-149">最多 500 K 個預設租用戶限制</span><span class="sxs-lookup"><span data-stu-id="18c3c-149">Up to default tenant limit of 500K</span></span>|
|<span data-ttu-id="18c3c-150">Number of members </span><span class="sxs-lookup"><span data-stu-id="18c3c-150">Number of members</span></span>|<span data-ttu-id="18c3c-151">超過 1000 個，但僅 1000 可以存取群組交談同時。</span><span class="sxs-lookup"><span data-stu-id="18c3c-151">More than 1,000, though only 1,000 can access the Group conversations concurrently.</span></span> <br><span data-ttu-id="18c3c-152">存取行事曆及極大型的群組，在 Outlook 中的交談時，使用者可能會注意到的延遲。</span><span class="sxs-lookup"><span data-stu-id="18c3c-152">Users might notice delays when accessing the calendar and conversations in very large groups in Outlook.</span></span>|
|<span data-ttu-id="18c3c-153">使用者可以是成員的群組數目</span><span class="sxs-lookup"><span data-stu-id="18c3c-153">Number of Groups a user can be a member of</span></span>|<span data-ttu-id="18c3c-154">1,000</span><span class="sxs-lookup"><span data-stu-id="18c3c-154">1,000</span></span>|
|<span data-ttu-id="18c3c-155">檔案存放區</span><span class="sxs-lookup"><span data-stu-id="18c3c-155">File storage</span></span>|<span data-ttu-id="18c3c-156">1 Tb + 每個訂閱的使用者 + 購買任何額外儲存空間的 10 GB。</span><span class="sxs-lookup"><span data-stu-id="18c3c-156">1 Terabyte + 10 GB per subscribed user + any additional storage purchased.</span></span> <span data-ttu-id="18c3c-157">您可以購買 unlimited 額外儲存空間量。</span><span class="sxs-lookup"><span data-stu-id="18c3c-157">You can purchase an unlimited amount of additional storage.</span></span>|
|<span data-ttu-id="18c3c-158">群組信箱大小</span><span class="sxs-lookup"><span data-stu-id="18c3c-158">Group Mailbox size</span></span>|<span data-ttu-id="18c3c-159">50 GB</span><span class="sxs-lookup"><span data-stu-id="18c3c-159">50 GB</span></span>|

<span data-ttu-id="18c3c-160">目前每個 Office 365 組織預設的 Office 365 群組數量上限為 500,000 個，但可依要求再增加。</span><span class="sxs-lookup"><span data-stu-id="18c3c-160">The default maximum number of Office 365 Groups that an Office 365 organization can have is currently 500,000, but can be increased by request.</span></span> <span data-ttu-id="18c3c-161">如需有關 Office 365 群組限制的詳細資訊，請參閱[Office 365 群組-系統管理說明](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)</span><span class="sxs-lookup"><span data-stu-id="18c3c-161">For more information on Office 365 Groups limits, see [Office 365 Groups - Admin help](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)</span></span>

<span data-ttu-id="18c3c-162">當您有可採取行動的群組使用方式資訊時，管理您的 Office 365 群組會更有效率。</span><span class="sxs-lookup"><span data-stu-id="18c3c-162">Managing your Office 365 Groups is more effective when you have actionable information about Groups usage.</span></span> <span data-ttu-id="18c3c-163">在 Microsoft 365 系統管理中心有報告工具，可讓您查看等儲存使用中，多少作用中群組，您必須與您的使用者甚至是如何使用群組。</span><span class="sxs-lookup"><span data-stu-id="18c3c-163">The Microsoft 365 Admin Center has a reporting tool that can let you see things such as storage use, how many active Groups you have and even how your users are using the Groups.</span></span> <span data-ttu-id="18c3c-164">如需詳細資訊，請參閱：[在系統管理中心的 Office 365 報告](../activity-reports/office-365-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="18c3c-164">See: [Office 365 Reports in the admin center](../activity-reports/office-365-groups.md) for more information.</span></span>

## <a name="which-office-365-plans-include-groups"></a><span data-ttu-id="18c3c-165">哪些 Office 365 方案包含群組？</span><span class="sxs-lookup"><span data-stu-id="18c3c-165">Which Office 365 plans include Groups?</span></span>

<span data-ttu-id="18c3c-166">任何具有 Exchange Online 和 SharePoint Online 的 Office 365 訂閱會支援群組。</span><span class="sxs-lookup"><span data-stu-id="18c3c-166">Any Office 365 subscription that has Exchange Online and SharePoint Online will support groups.</span></span> <span data-ttu-id="18c3c-167">包含商務基本版和商務進階版方案和企業版 E1、 E3 和 E5 方案。</span><span class="sxs-lookup"><span data-stu-id="18c3c-167">That includes the Business Essentials and Business Premium plans, and the Enterprise E1, E3 and E5 plans.</span></span> <span data-ttu-id="18c3c-168">上建立的群組 （也稱為 「 組合管理 」 的群組） 之人員的授權，通訊群組。</span><span class="sxs-lookup"><span data-stu-id="18c3c-168">The Group takes on the licensing of the person who creates the Group (also known as the "organizer" of the Group).</span></span> <span data-ttu-id="18c3c-169">只要召集人有適當的權限的任何功能您想要有的群組，該授權會傳達給群組。</span><span class="sxs-lookup"><span data-stu-id="18c3c-169">As long as the organizer has the proper license for whatever features you want the Group to have, that license will convey to the Group.</span></span>

> [!NOTE]
> <span data-ttu-id="18c3c-170">如需有關 Office 365 服務系列與方案的詳細資訊，請檢查[Office 365 方案選項](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</span><span class="sxs-lookup"><span data-stu-id="18c3c-170">For more details about Office 365 service families and plans, please check [Office 365 plan options](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</span></span>

<span data-ttu-id="18c3c-171">如果您具有您仍然可以取得的共用收件匣與共用行事曆功能僅限 Exchange 的計劃中 Outlook，但您的群組不會收到文件庫、 Planner 或任何其他功能。</span><span class="sxs-lookup"><span data-stu-id="18c3c-171">If you have an Exchange-only plan you can still get the shared Inbox and shared Calendar features of groups in Outlook but you won’t get the document library, Planner or any of the other capabilities.</span></span>

<span data-ttu-id="18c3c-172">Office 365 群組的運作方式與 Azure Active Directory (AAD)。</span><span class="sxs-lookup"><span data-stu-id="18c3c-172">Office 365 Groups works with Azure Active Directory (AAD).</span></span> <span data-ttu-id="18c3c-173">您要取得的群組功能取決於哪些 Azure Active Directory 訂閱上您有，並查看授權指派給組合管理] 群組。</span><span class="sxs-lookup"><span data-stu-id="18c3c-173">The Groups features you get depends on which Azure Active Directory subscription you have, and what license(s) is assigned to the organizer of the Group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18c3c-174">所有的群組功能，如果您有 Azure AD Premium 訂閱，使用者可以加入群組有指派給他們的 AAD P1 授權。</span><span class="sxs-lookup"><span data-stu-id="18c3c-174">For all the Groups features, if you have an Azure AD Premium subscription, users can join the group whether or not they have an AAD P1 license assigned to them.</span></span> <span data-ttu-id="18c3c-175">授權不強制執行。</span><span class="sxs-lookup"><span data-stu-id="18c3c-175">Licensing isn't enforced.</span></span>
> <span data-ttu-id="18c3c-176">定期我們會產生流量報告，告訴您哪些使用者遺失授權，並且需要指派給它們是相容的授權需求。</span><span class="sxs-lookup"><span data-stu-id="18c3c-176">Periodically we will generate usage reports that tell you which users are missing a license, and need one assigned to them to be compliant with the licensing requirements.</span></span> <span data-ttu-id="18c3c-177">例如，假設使用者沒有授權和他們已新增至群組命名原則強制執行的位置。</span><span class="sxs-lookup"><span data-stu-id="18c3c-177">For example, let's say a user doesn't have a license and they are added to a group where the naming policy is enforced.</span></span> <span data-ttu-id="18c3c-178">報表會標示為您所需的授權。</span><span class="sxs-lookup"><span data-stu-id="18c3c-178">The report will flag for you that they need a license.</span></span>

## <a name="related-articles"></a><span data-ttu-id="18c3c-179">相關文章</span><span class="sxs-lookup"><span data-stu-id="18c3c-179">Related articles</span></span>

[<span data-ttu-id="18c3c-180">了解 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="18c3c-180">Learn about Office 365 Groups</span></span>](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="18c3c-181">通訊群組清單升級至 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="18c3c-181">Upgrade distribution lists to Office 365 Groups</span></span>](../manage/upgrade-distribution-lists.md)

[<span data-ttu-id="18c3c-182">使用 PowerShell 管理 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="18c3c-182">Manage Office 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[<span data-ttu-id="18c3c-183">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="18c3c-183">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
