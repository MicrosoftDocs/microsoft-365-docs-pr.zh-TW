---
title: 群組服務互動
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 群組服務互動
ms.openlocfilehash: 9632debf1bc6fdd2fce061a4c535906410700175
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662551"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="16e16-103">群組服務互動</span><span class="sxs-lookup"><span data-stu-id="16e16-103">Groups services interactions</span></span>

<span data-ttu-id="16e16-104">Microsoft 365 群組為 Microsoft 365 平臺內的一些服務和工作負載提供了共同的結構，可為使用者提供連線的體驗。</span><span class="sxs-lookup"><span data-stu-id="16e16-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="16e16-105">在其核心中，Microsoft 365 群組存在，可提供：</span><span class="sxs-lookup"><span data-stu-id="16e16-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="16e16-106"> (Azure AD) 管理成員資格的方式</span><span class="sxs-lookup"><span data-stu-id="16e16-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="16e16-107">在 Exchange 信箱、Microsoft 小組、Yammer) 中，會發生郵件和交談的位置 (</span><span class="sxs-lookup"><span data-stu-id="16e16-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="16e16-108">儲存 (SharePoint 的檔案位置) </span><span class="sxs-lookup"><span data-stu-id="16e16-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="16e16-109">排程 (Exchange) 的行事曆</span><span class="sxs-lookup"><span data-stu-id="16e16-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="16e16-110">用於 (OneNote 的記錄的捕獲筆記) </span><span class="sxs-lookup"><span data-stu-id="16e16-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="16e16-111">在建立群組時，也會布建許多其他資源，但是直到第一次從服務存取後，才會顯示這些資源：</span><span class="sxs-lookup"><span data-stu-id="16e16-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="16e16-112">用於管理群組工作 (Planner) 的主機板</span><span class="sxs-lookup"><span data-stu-id="16e16-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="16e16-113"> (Power BI) 的報表工作區</span><span class="sxs-lookup"><span data-stu-id="16e16-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="16e16-114">共用影片 (Microsoft Stream) 的區域</span><span class="sxs-lookup"><span data-stu-id="16e16-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="16e16-115">共用表單 (表單的區域) </span><span class="sxs-lookup"><span data-stu-id="16e16-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="16e16-116">在 Microsoft 365 中，其他服務可以與 Microsoft 365 群組互動，以將其他功能和功能提供給群組成員。</span><span class="sxs-lookup"><span data-stu-id="16e16-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="16e16-117">這包括下列範例：</span><span class="sxs-lookup"><span data-stu-id="16e16-117">Examples of this include:</span></span>

- <span data-ttu-id="16e16-118">應用程式的電源應用程式</span><span class="sxs-lookup"><span data-stu-id="16e16-118">Power Apps for apps</span></span>
- <span data-ttu-id="16e16-119">工作流程的自動力量</span><span class="sxs-lookup"><span data-stu-id="16e16-119">Power Automate for workflows</span></span>
- <span data-ttu-id="16e16-120">以瀑布式專案管理為基礎的 web 和藍圖上的專案</span><span class="sxs-lookup"><span data-stu-id="16e16-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="16e16-121">以通道為基礎之交談的小組</span><span class="sxs-lookup"><span data-stu-id="16e16-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="16e16-122">相關社區的 Yammer</span><span class="sxs-lookup"><span data-stu-id="16e16-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="16e16-123">與群組的使用者互動</span><span class="sxs-lookup"><span data-stu-id="16e16-123">User interactions with groups</span></span>

<span data-ttu-id="16e16-124">Microsoft 365 群組可以從各種介面建立及管理，既包括系統管理員和使用者。</span><span class="sxs-lookup"><span data-stu-id="16e16-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="16e16-125">管理體驗</span><span class="sxs-lookup"><span data-stu-id="16e16-125">Administrative experiences</span></span>

<span data-ttu-id="16e16-126">管理員可以從一些工作負載系統管理中心、支援腳本的命令列介面，以及與圖形 API 互動的自訂應用程式，建立及管理 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="16e16-127">這只是 Yammer 群組的唯一例外，必須從 Yammer web 介面中建立。</span><span class="sxs-lookup"><span data-stu-id="16e16-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="16e16-128">**相關設定**</span><span class="sxs-lookup"><span data-stu-id="16e16-128">**Related settings**</span></span>

<span data-ttu-id="16e16-129">跨越可管理群組設定的各種管理介面，有數個重疊，您應該注意。</span><span class="sxs-lookup"><span data-stu-id="16e16-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="16e16-130">**Microsoft 365 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="16e16-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="16e16-131">在 Microsoft 365 系統管理中心中，預設會啟用對群組的來賓存取，因為允許擁有者新增來賓的能力。</span><span class="sxs-lookup"><span data-stu-id="16e16-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="16e16-132">此系統管理中心中的群組沒有進一步的組織層級控制項可用。</span><span class="sxs-lookup"><span data-stu-id="16e16-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="16e16-133">**Azure AD 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="16e16-133">**Azure AD admin center**</span></span>

<span data-ttu-id="16e16-134">Azure AD 系統管理中心提供的控制措施是使用者是否可以建立群組或指派 Azure 入口網站的擁有者，以及到期及命名原則設定。</span><span class="sxs-lookup"><span data-stu-id="16e16-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="16e16-135">系統管理中心還提供許多來賓邀請控制項量值，不僅限於 Microsoft 365 系統管理中心，例如限制非擁有者是否也可以邀請來賓的功能。</span><span class="sxs-lookup"><span data-stu-id="16e16-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="16e16-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="16e16-136">**SharePoint**</span></span>

<span data-ttu-id="16e16-137">SharePoint 網站是以擁有者、成員及訪客安全性群組的方式建立，其前兩個對應至其 Microsoft 365 群組的對應。</span><span class="sxs-lookup"><span data-stu-id="16e16-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="16e16-138">雖然 SharePoint Online 網站的成員資格通常是由關聯的 Microsoft 365 群組管理，但不是雙向關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="16e16-139">Microsoft 365 群組層級成員資格的任何變更都會反映在 SharePoint 中，但如果 SharePoint 群組中的成員資格變更，則不會反映在 Microsoft 365 群組中。</span><span class="sxs-lookup"><span data-stu-id="16e16-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="16e16-140">使用者經驗</span><span class="sxs-lookup"><span data-stu-id="16e16-140">User experiences</span></span>

<span data-ttu-id="16e16-141">使用者可以從 Microsoft 365 中的數個服務建立群組，而在其他使用者只能與群組共用。</span><span class="sxs-lookup"><span data-stu-id="16e16-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="16e16-142">下列服務允許使用者建立群組：</span><span class="sxs-lookup"><span data-stu-id="16e16-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="16e16-143">Web SharePoint Stream 的 Outlook Planner 專案 Microsoft 小組 Yammer</span><span class="sxs-lookup"><span data-stu-id="16e16-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="16e16-144">**群組的建立限制**</span><span class="sxs-lookup"><span data-stu-id="16e16-144">**Restriction of group creation**</span></span>

<span data-ttu-id="16e16-145">控制小組的蔓延的常見方法是限制哪些使用者可以建立。</span><span class="sxs-lookup"><span data-stu-id="16e16-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="16e16-146">這只能透過限制建立群組來完成。</span><span class="sxs-lookup"><span data-stu-id="16e16-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="16e16-147">這樣做會影響從其他服務（可能為使用者必要）建立群組的能力。</span><span class="sxs-lookup"><span data-stu-id="16e16-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="16e16-148">Microsoft 365 群組不支援限制從某些應用程式或服務建立群組，同時允許其他使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="16e16-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="16e16-149">群組建立限制的體驗會因應用程式和服務而異：</span><span class="sxs-lookup"><span data-stu-id="16e16-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="16e16-150">應用程式或服務</span><span class="sxs-lookup"><span data-stu-id="16e16-150">App or service</span></span>|<span data-ttu-id="16e16-151">功能</span><span class="sxs-lookup"><span data-stu-id="16e16-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="16e16-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="16e16-152">Outlook</span></span>|<span data-ttu-id="16e16-153">從 [人員] 頁面的新功能表移除 [**新增群組**] 選項</span><span class="sxs-lookup"><span data-stu-id="16e16-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="16e16-154">Planner</span><span class="sxs-lookup"><span data-stu-id="16e16-154">Planner</span></span>|<span data-ttu-id="16e16-155">**新計畫** 說明已關閉群組建立功能，並提供將計畫新增至現有的群組</span><span class="sxs-lookup"><span data-stu-id="16e16-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="16e16-156">Web 和藍圖的專案</span><span class="sxs-lookup"><span data-stu-id="16e16-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="16e16-157">**建立群組** 功能表說明群組建立限制，並建議使用現有的群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="16e16-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="16e16-158">SharePoint</span></span>|<span data-ttu-id="16e16-159">仍然可以建立未連接至群組的小組網站。</span><span class="sxs-lookup"><span data-stu-id="16e16-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="16e16-160">Stream</span><span class="sxs-lookup"><span data-stu-id="16e16-160">Stream</span></span>|<span data-ttu-id="16e16-161">**群組** 選項不會出現在 [ **建立] 功能表**底下。</span><span class="sxs-lookup"><span data-stu-id="16e16-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="16e16-162">Teams</span><span class="sxs-lookup"><span data-stu-id="16e16-162">Teams</span></span>|<span data-ttu-id="16e16-163">使用者無法使用新的群組建立小組，但仍然可以建立利用現有群組的小組。</span><span class="sxs-lookup"><span data-stu-id="16e16-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="16e16-164">[**建立小組**] 按鈕會取代為**群組中的 [建立小組**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="16e16-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="16e16-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="16e16-165">Yammer</span></span>|<span data-ttu-id="16e16-166">[**建立群組**] 選項會從 [主要群組/社區] 導覽中移除。</span><span class="sxs-lookup"><span data-stu-id="16e16-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="16e16-167">與群組的服務互動</span><span class="sxs-lookup"><span data-stu-id="16e16-167">Services interactions with groups</span></span>

<span data-ttu-id="16e16-168">請參閱 Microsoft 365 海報中的群組，以取得不同群組類型的相關資訊、建立與管理的方式，以及一些管理建議。</span><span class="sxs-lookup"><span data-stu-id="16e16-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="16e16-169">[![群組資訊圖的縮圖影像](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="16e16-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="16e16-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="16e16-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="16e16-171">下表提供與各種服務的 Microsoft 365 群組互動的概述：</span><span class="sxs-lookup"><span data-stu-id="16e16-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="16e16-172">產品</span><span class="sxs-lookup"><span data-stu-id="16e16-172">Product</span></span>|<span data-ttu-id="16e16-173">功能</span><span class="sxs-lookup"><span data-stu-id="16e16-173">Features</span></span>|<span data-ttu-id="16e16-174">服務</span><span class="sxs-lookup"><span data-stu-id="16e16-174">Does the service</span></span><br><span data-ttu-id="16e16-175">是否存在沒有群組的情況？</span><span class="sxs-lookup"><span data-stu-id="16e16-175">exist without a group?</span></span>|<span data-ttu-id="16e16-176">服務是否可以</span><span class="sxs-lookup"><span data-stu-id="16e16-176">Can the service</span></span><br><span data-ttu-id="16e16-177">建立群組？</span><span class="sxs-lookup"><span data-stu-id="16e16-177">create a group?</span></span>|<span data-ttu-id="16e16-178">刪除</span><span class="sxs-lookup"><span data-stu-id="16e16-178">Does deleting the</span></span><br><span data-ttu-id="16e16-179">實例刪除群組？</span><span class="sxs-lookup"><span data-stu-id="16e16-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="16e16-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="16e16-180">Azure AD</span></span>|<span data-ttu-id="16e16-181">成員資格、群組控制項、來賓</span><span class="sxs-lookup"><span data-stu-id="16e16-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="16e16-182">是</span><span class="sxs-lookup"><span data-stu-id="16e16-182">Yes</span></span>|<span data-ttu-id="16e16-183">是</span><span class="sxs-lookup"><span data-stu-id="16e16-183">Yes</span></span>|<span data-ttu-id="16e16-184">是</span><span class="sxs-lookup"><span data-stu-id="16e16-184">Yes</span></span>|
|<span data-ttu-id="16e16-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="16e16-185">Exchange</span></span>|<span data-ttu-id="16e16-186">行事曆、信箱</span><span class="sxs-lookup"><span data-stu-id="16e16-186">Calendar, mailbox</span></span>|<span data-ttu-id="16e16-187">是</span><span class="sxs-lookup"><span data-stu-id="16e16-187">Yes</span></span>|<span data-ttu-id="16e16-188">是</span><span class="sxs-lookup"><span data-stu-id="16e16-188">Yes</span></span>|<span data-ttu-id="16e16-189">是</span><span class="sxs-lookup"><span data-stu-id="16e16-189">Yes</span></span>|
|<span data-ttu-id="16e16-190">Forms</span><span class="sxs-lookup"><span data-stu-id="16e16-190">Forms</span></span>|<span data-ttu-id="16e16-191">Form</span><span class="sxs-lookup"><span data-stu-id="16e16-191">Form</span></span>|<span data-ttu-id="16e16-192">是</span><span class="sxs-lookup"><span data-stu-id="16e16-192">Yes</span></span>|<span data-ttu-id="16e16-193">否</span><span class="sxs-lookup"><span data-stu-id="16e16-193">No</span></span>|<span data-ttu-id="16e16-194">否</span><span class="sxs-lookup"><span data-stu-id="16e16-194">No</span></span>|
|<span data-ttu-id="16e16-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="16e16-195">OneNote</span></span>|<span data-ttu-id="16e16-196">筆記本</span><span class="sxs-lookup"><span data-stu-id="16e16-196">Notebook</span></span>|<span data-ttu-id="16e16-197">是</span><span class="sxs-lookup"><span data-stu-id="16e16-197">Yes</span></span>|<span data-ttu-id="16e16-198">否</span><span class="sxs-lookup"><span data-stu-id="16e16-198">No</span></span>|<span data-ttu-id="16e16-199">否</span><span class="sxs-lookup"><span data-stu-id="16e16-199">No</span></span>|
|<span data-ttu-id="16e16-200">Planner</span><span class="sxs-lookup"><span data-stu-id="16e16-200">Planner</span></span>|<span data-ttu-id="16e16-201">工作面板</span><span class="sxs-lookup"><span data-stu-id="16e16-201">Task board</span></span>|<span data-ttu-id="16e16-202">否</span><span class="sxs-lookup"><span data-stu-id="16e16-202">No</span></span>|<span data-ttu-id="16e16-203">是</span><span class="sxs-lookup"><span data-stu-id="16e16-203">Yes</span></span>|<span data-ttu-id="16e16-204">是</span><span class="sxs-lookup"><span data-stu-id="16e16-204">Yes</span></span>|
|<span data-ttu-id="16e16-205">Power Apps 應用程式</span><span class="sxs-lookup"><span data-stu-id="16e16-205">Power Apps app</span></span>|<span data-ttu-id="16e16-206">應用程式</span><span class="sxs-lookup"><span data-stu-id="16e16-206">App</span></span>|<span data-ttu-id="16e16-207">是</span><span class="sxs-lookup"><span data-stu-id="16e16-207">Yes</span></span>|<span data-ttu-id="16e16-208">否</span><span class="sxs-lookup"><span data-stu-id="16e16-208">No</span></span>|<span data-ttu-id="16e16-209">否</span><span class="sxs-lookup"><span data-stu-id="16e16-209">No</span></span>|
|<span data-ttu-id="16e16-210">自動功耗</span><span class="sxs-lookup"><span data-stu-id="16e16-210">Power Automate</span></span>|<span data-ttu-id="16e16-211">工作流程</span><span class="sxs-lookup"><span data-stu-id="16e16-211">Workflow</span></span>|<span data-ttu-id="16e16-212">是</span><span class="sxs-lookup"><span data-stu-id="16e16-212">Yes</span></span>|<span data-ttu-id="16e16-213">否</span><span class="sxs-lookup"><span data-stu-id="16e16-213">No</span></span>|<span data-ttu-id="16e16-214">否</span><span class="sxs-lookup"><span data-stu-id="16e16-214">No</span></span>|
|<span data-ttu-id="16e16-215">Power BI (傳統) </span><span class="sxs-lookup"><span data-stu-id="16e16-215">Power BI (classic)</span></span>|<span data-ttu-id="16e16-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="16e16-216">Workspace</span></span>|<span data-ttu-id="16e16-217">否</span><span class="sxs-lookup"><span data-stu-id="16e16-217">No</span></span>|<span data-ttu-id="16e16-218">是</span><span class="sxs-lookup"><span data-stu-id="16e16-218">Yes</span></span>|<span data-ttu-id="16e16-219">是</span><span class="sxs-lookup"><span data-stu-id="16e16-219">Yes</span></span>|
|<span data-ttu-id="16e16-220">Power BI (new) </span><span class="sxs-lookup"><span data-stu-id="16e16-220">Power BI (new)</span></span>|<span data-ttu-id="16e16-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="16e16-221">Workspace</span></span>|<span data-ttu-id="16e16-222">是</span><span class="sxs-lookup"><span data-stu-id="16e16-222">Yes</span></span>|<span data-ttu-id="16e16-223">否</span><span class="sxs-lookup"><span data-stu-id="16e16-223">No</span></span>|<span data-ttu-id="16e16-224">是</span><span class="sxs-lookup"><span data-stu-id="16e16-224">Yes</span></span>|
|<span data-ttu-id="16e16-225">Project 網頁版</span><span class="sxs-lookup"><span data-stu-id="16e16-225">Project for the web</span></span>|<span data-ttu-id="16e16-226">專案計劃</span><span class="sxs-lookup"><span data-stu-id="16e16-226">Project plan</span></span>|<span data-ttu-id="16e16-227">是</span><span class="sxs-lookup"><span data-stu-id="16e16-227">Yes</span></span>|<span data-ttu-id="16e16-228">是</span><span class="sxs-lookup"><span data-stu-id="16e16-228">Yes</span></span>|<span data-ttu-id="16e16-229">否</span><span class="sxs-lookup"><span data-stu-id="16e16-229">No</span></span>|
|<span data-ttu-id="16e16-230">藍圖</span><span class="sxs-lookup"><span data-stu-id="16e16-230">Roadmap</span></span>|<span data-ttu-id="16e16-231">藍圖</span><span class="sxs-lookup"><span data-stu-id="16e16-231">Roadmap</span></span>|<span data-ttu-id="16e16-232">是</span><span class="sxs-lookup"><span data-stu-id="16e16-232">Yes</span></span>|<span data-ttu-id="16e16-233">是</span><span class="sxs-lookup"><span data-stu-id="16e16-233">Yes</span></span>|<span data-ttu-id="16e16-234">否</span><span class="sxs-lookup"><span data-stu-id="16e16-234">No</span></span>|
|<span data-ttu-id="16e16-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="16e16-235">SharePoint</span></span>|<span data-ttu-id="16e16-236">網站</span><span class="sxs-lookup"><span data-stu-id="16e16-236">Site</span></span>|<span data-ttu-id="16e16-237">是</span><span class="sxs-lookup"><span data-stu-id="16e16-237">Yes</span></span>|<span data-ttu-id="16e16-238">是</span><span class="sxs-lookup"><span data-stu-id="16e16-238">Yes</span></span>|<span data-ttu-id="16e16-239">是</span><span class="sxs-lookup"><span data-stu-id="16e16-239">Yes</span></span>|
|<span data-ttu-id="16e16-240">Stream</span><span class="sxs-lookup"><span data-stu-id="16e16-240">Stream</span></span>|<span data-ttu-id="16e16-241">通道、影片</span><span class="sxs-lookup"><span data-stu-id="16e16-241">Channel, video</span></span>|<span data-ttu-id="16e16-242">是</span><span class="sxs-lookup"><span data-stu-id="16e16-242">Yes</span></span>|<span data-ttu-id="16e16-243">是</span><span class="sxs-lookup"><span data-stu-id="16e16-243">Yes</span></span>|<span data-ttu-id="16e16-244">是</span><span class="sxs-lookup"><span data-stu-id="16e16-244">Yes</span></span>|
|<span data-ttu-id="16e16-245">Teams</span><span class="sxs-lookup"><span data-stu-id="16e16-245">Teams</span></span>|<span data-ttu-id="16e16-246">團隊</span><span class="sxs-lookup"><span data-stu-id="16e16-246">Team</span></span>|<span data-ttu-id="16e16-247">否</span><span class="sxs-lookup"><span data-stu-id="16e16-247">No</span></span>|<span data-ttu-id="16e16-248">是</span><span class="sxs-lookup"><span data-stu-id="16e16-248">Yes</span></span>|<span data-ttu-id="16e16-249">是</span><span class="sxs-lookup"><span data-stu-id="16e16-249">Yes</span></span>|
|<span data-ttu-id="16e16-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="16e16-250">Yammer</span></span>|<span data-ttu-id="16e16-251">群組</span><span class="sxs-lookup"><span data-stu-id="16e16-251">Group</span></span>|<span data-ttu-id="16e16-252">是</span><span class="sxs-lookup"><span data-stu-id="16e16-252">Yes</span></span>|<span data-ttu-id="16e16-253">是</span><span class="sxs-lookup"><span data-stu-id="16e16-253">Yes</span></span>|<span data-ttu-id="16e16-254">是</span><span class="sxs-lookup"><span data-stu-id="16e16-254">Yes</span></span>|

<span data-ttu-id="16e16-255">當上表提供與 Microsoft 365 服務的群組互動的高層次概述時，您應該瞭解許多細微差別和複雜的情況。</span><span class="sxs-lookup"><span data-stu-id="16e16-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="16e16-256">下列各節將深入瞭解特定工作負載及其與群組的互動。</span><span class="sxs-lookup"><span data-stu-id="16e16-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="16e16-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="16e16-257">Azure AD</span></span>

<span data-ttu-id="16e16-258">Azure AD 在 Microsoft 365 中提供基礎的身分識別管理功能。</span><span class="sxs-lookup"><span data-stu-id="16e16-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="16e16-259">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="16e16-260">群組的成員資格</span><span class="sxs-lookup"><span data-stu-id="16e16-260">Group membership</span></span>
- <span data-ttu-id="16e16-261">命名原則</span><span class="sxs-lookup"><span data-stu-id="16e16-261">Naming policy</span></span>
- <span data-ttu-id="16e16-262">到期原則</span><span class="sxs-lookup"><span data-stu-id="16e16-262">Expiration policy</span></span>
- <span data-ttu-id="16e16-263">客人</span><span class="sxs-lookup"><span data-stu-id="16e16-263">Guests</span></span>
- <span data-ttu-id="16e16-264">群組的建立限制</span><span class="sxs-lookup"><span data-stu-id="16e16-264">Restriction of Group creation</span></span>

<span data-ttu-id="16e16-265">**Azure AD 是否可以建立群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="16e16-266">是的，您可以從 Azure AD 建立 Microsoft 365 群組，不論是透過「管理」網頁入口網站，還是透過 PowerShell 或圖形 API。</span><span class="sxs-lookup"><span data-stu-id="16e16-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="16e16-267">**Azure AD 是否存在沒有群組的情況？**</span><span class="sxs-lookup"><span data-stu-id="16e16-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="16e16-268">是的，Azure AD 執行大量服務，與 Microsoft 365 群組無關。</span><span class="sxs-lookup"><span data-stu-id="16e16-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="16e16-269">每個 Microsoft 365 群組都是以 Azure AD 中的物件來表示。</span><span class="sxs-lookup"><span data-stu-id="16e16-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="16e16-270">**每個群組是否可以有多個 Azure AD 實例？**</span><span class="sxs-lookup"><span data-stu-id="16e16-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="16e16-271">否，Azure AD 只有一個實例。</span><span class="sxs-lookup"><span data-stu-id="16e16-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="16e16-272">**Azure AD 是否可以與多個群組相關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="16e16-273">是的，因為 Azure AD 是提供群組成員資格服務的基礎平臺。</span><span class="sxs-lookup"><span data-stu-id="16e16-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="16e16-274">**Azure AD 與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="16e16-275">否，Azure AD 是群組存在所在的基礎平臺。</span><span class="sxs-lookup"><span data-stu-id="16e16-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="16e16-276">**刪除此實例後，會刪除群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="16e16-277">刪除 Azure AD 中的群組將會刪除相關的群組相關服務和內容。</span><span class="sxs-lookup"><span data-stu-id="16e16-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="16e16-278">Teams</span><span class="sxs-lookup"><span data-stu-id="16e16-278">Teams</span></span>

<span data-ttu-id="16e16-279">團隊是一個以聊天為中心的工作區，其目的在於提供單一介面，以與各種 Microsoft 和協力廠商服務互動，以提升共同作業。</span><span class="sxs-lookup"><span data-stu-id="16e16-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="16e16-280">根據預設，當建立小組時，與 Microsoft 365 群組相關聯的信箱和行事曆，會從 Exchange 的全域通訊清單和 Outlook 中隱藏。</span><span class="sxs-lookup"><span data-stu-id="16e16-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="16e16-281">如果使用者想要在相同的 Microsoft 365 群組上使用 Outlook 和小組，則系統管理員可以手動覆寫此。</span><span class="sxs-lookup"><span data-stu-id="16e16-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="16e16-282">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="16e16-283">交談</span><span class="sxs-lookup"><span data-stu-id="16e16-283">Conversations</span></span>
- <span data-ttu-id="16e16-284">通道 &] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="16e16-284">Channels & tabs</span></span>
- <span data-ttu-id="16e16-285">Meetings</span><span class="sxs-lookup"><span data-stu-id="16e16-285">Meetings</span></span>

<span data-ttu-id="16e16-286">**小組是否可以建立群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="16e16-287">是的，建立新的小組將會建立新的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="16e16-288">您也可以為目前沒有的群組建立小組。</span><span class="sxs-lookup"><span data-stu-id="16e16-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="16e16-289">**是否有小組沒有群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="16e16-290">否，不可能有小組沒有群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="16e16-291">**每個群組可以有多個團隊嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="16e16-292">否，小組和群組之間的關聯性是1:1。</span><span class="sxs-lookup"><span data-stu-id="16e16-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="16e16-293">**小組是否可以與多個群組相關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-294">否，小組自身只能與單一群組相關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="16e16-295">**小組與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="16e16-296">否，小組只會與其最初關聯的群組相關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="16e16-297">**刪除小組是否刪除群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="16e16-298">是的，刪除 Microsoft 團隊中的團隊將會刪除群組、群組相關聯的服務和內容。</span><span class="sxs-lookup"><span data-stu-id="16e16-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="16e16-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="16e16-299">Exchange</span></span>

<span data-ttu-id="16e16-300">Exchange Online 提供郵件、行事曆、連絡人及相關聯的功能。</span><span class="sxs-lookup"><span data-stu-id="16e16-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="16e16-301">在群組的內容中，只有單一資源與整個服務實例相關聯–而非相關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="16e16-302">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="16e16-303">信箱和行事曆</span><span class="sxs-lookup"><span data-stu-id="16e16-303">Mailbox and calendar</span></span>
- <span data-ttu-id="16e16-304">能夠以電子郵件傳送所有群組成員</span><span class="sxs-lookup"><span data-stu-id="16e16-304">Ability to email all Group members</span></span>
- <span data-ttu-id="16e16-305">用於 eDiscovery 目的、Planner 批註的小組的儲存通道交談</span><span class="sxs-lookup"><span data-stu-id="16e16-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="16e16-306">**Exchange 是否可以建立群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="16e16-307">是的，您可以從 Exchange Online 系統管理中心和 Outlook 建立群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="16e16-308">您也可以將 Exchange 通訊群組清單轉換成 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="16e16-309">**是否有不含群組的 Exchange？**</span><span class="sxs-lookup"><span data-stu-id="16e16-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="16e16-310">是的，Exchange Online 提供許多服務，包括共用信箱和行事曆，沒有任何群組關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="16e16-311">**每個群組是否可以有多個 Exchange 信箱或行事曆實例？**</span><span class="sxs-lookup"><span data-stu-id="16e16-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="16e16-312">否，群組只能有一個 Exchange Online 信箱和行事曆。</span><span class="sxs-lookup"><span data-stu-id="16e16-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="16e16-313">**Exchange 信箱和行事曆是否可以與多個群組產生關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-314">否，信箱和行事曆與群組之間有1:1 的關係。</span><span class="sxs-lookup"><span data-stu-id="16e16-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="16e16-315">您可以與其他使用者或群組共用信箱，但這不會建立任何形式的服務關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="16e16-316">**Exchange 信箱或行事曆與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="16e16-317">否，信箱和行事曆無法變更為不同的群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="16e16-318">不過，您可以在 Outlook 中或使用協力廠商工具，將內容從一個信箱移至另一個信箱。</span><span class="sxs-lookup"><span data-stu-id="16e16-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="16e16-319">**刪除信箱會刪除群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="16e16-320">是的，刪除 Exchange 中的信箱會刪除群組相關聯的服務和內容。</span><span class="sxs-lookup"><span data-stu-id="16e16-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="16e16-321">Forms</span><span class="sxs-lookup"><span data-stu-id="16e16-321">Forms</span></span>

<span data-ttu-id="16e16-322">表單提供 web 型問卷調查和測驗。</span><span class="sxs-lookup"><span data-stu-id="16e16-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="16e16-323">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="16e16-324">表單的擁有權</span><span class="sxs-lookup"><span data-stu-id="16e16-324">Ownership of forms</span></span>

<span data-ttu-id="16e16-325">**表單是否可以建立群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="16e16-326">否，表單無法建立群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="16e16-327">**表單是否有沒有群組的功能？**</span><span class="sxs-lookup"><span data-stu-id="16e16-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="16e16-328">是的，您可以直接在使用者的帳戶中建立調查和測驗。</span><span class="sxs-lookup"><span data-stu-id="16e16-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="16e16-329">**每個群組可以有多個表單嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="16e16-330">是的，可以有多個表單與一個群組相關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="16e16-331">**表單是否可與多個群組相關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-332">否，表單只可與單一群組相關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="16e16-333">**表單與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="16e16-334">否，表單與群組建立關聯 (，或從個別) 取得擁有權時，無法將它移到另一個群組中。</span><span class="sxs-lookup"><span data-stu-id="16e16-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="16e16-335">**刪除表單會刪除群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="16e16-336">否，不可能從表單介面中刪除群組，只能從個別表單刪除。</span><span class="sxs-lookup"><span data-stu-id="16e16-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="16e16-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="16e16-337">OneNote</span></span>

<span data-ttu-id="16e16-338">OneNote 是數位筆記本應用程式。</span><span class="sxs-lookup"><span data-stu-id="16e16-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="16e16-339">以群組建立的 OneNote 筆記本是關聯 SharePoint 網站中的檔案，而不是群組聯機服務。</span><span class="sxs-lookup"><span data-stu-id="16e16-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="16e16-340">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="16e16-341">儲存在群組相關 SharePoint 庫中的共用筆記本 () </span><span class="sxs-lookup"><span data-stu-id="16e16-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="16e16-342">**可以 OneNote 建立群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="16e16-343">否，OneNote 應用程式無法建立群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="16e16-344">**是否有沒有群組的 OneNote 筆記本？**</span><span class="sxs-lookup"><span data-stu-id="16e16-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="16e16-345">是，筆記本可以直接在 OneDrive 或其他共用位置建立。</span><span class="sxs-lookup"><span data-stu-id="16e16-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="16e16-346">**每個群組是否可以有多個 OneNote 筆記本？**</span><span class="sxs-lookup"><span data-stu-id="16e16-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="16e16-347">是的，預設會建立筆記本，而且可以新增其他人，但是來自群組相關服務的任何 OneNote 連結，都不會進入預設的筆記本。</span><span class="sxs-lookup"><span data-stu-id="16e16-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="16e16-348">**OneNote 的筆記本是否可以與多個群組產生關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-349">否，筆記本會儲存在群組相關聯的 SharePoint 網站文件庫中，並從各種介面連結。</span><span class="sxs-lookup"><span data-stu-id="16e16-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="16e16-350">不過，您可以與其他群組共用，其方式與個人共用的方式相同。</span><span class="sxs-lookup"><span data-stu-id="16e16-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="16e16-351">**筆記本與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="16e16-352">否，筆記本本身會與群組產生關聯，而且可以從其他群組聯機服務直接存取，但是可以在 OneNote 應用程式內，將內容從一個筆記本移至另一個。</span><span class="sxs-lookup"><span data-stu-id="16e16-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="16e16-353">**刪除筆記本刪除群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="16e16-354">否，但如果刪除 OneNote 筆記本，某些群組相關服務中的連結可能會中斷。</span><span class="sxs-lookup"><span data-stu-id="16e16-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="16e16-355">Planner</span><span class="sxs-lookup"><span data-stu-id="16e16-355">Planner</span></span>

<span data-ttu-id="16e16-356">Planner 是輕量群組任務管理服務。</span><span class="sxs-lookup"><span data-stu-id="16e16-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="16e16-357">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="16e16-358">管理群組任務的外掛程式</span><span class="sxs-lookup"><span data-stu-id="16e16-358">Board for managing group tasks</span></span>

<span data-ttu-id="16e16-359">**Planner 是否可以建立群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="16e16-360">是的，建立計畫將會建立新的群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="16e16-361">**Planner 面板是否不存在群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="16e16-362">否，計畫必須與群組產生關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="16e16-363">**每個群組可以有多個方案嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="16e16-364">是，每個群組可以有多個方案。</span><span class="sxs-lookup"><span data-stu-id="16e16-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="16e16-365">**方案是否可以與多個群組相關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-366">否，計畫只依靠群組成員資格來決定存取權。</span><span class="sxs-lookup"><span data-stu-id="16e16-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="16e16-367">**方案與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="16e16-368">否，但是複製計畫會建立新的群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="16e16-369">任何其他應用程式所建立的群組不會自動顯示給使用者的 Planner。</span><span class="sxs-lookup"><span data-stu-id="16e16-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="16e16-370">若要先存取董事會，他們必須從另一個以群組為基礎的介面（如 Outlook）中開啟。</span><span class="sxs-lookup"><span data-stu-id="16e16-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="16e16-371">**刪除方案刪除群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="16e16-372">是的，刪除方案將會刪除群組和群組相關聯的服務和內容。</span><span class="sxs-lookup"><span data-stu-id="16e16-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="16e16-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="16e16-373">Power Apps</span></span>

<span data-ttu-id="16e16-374">在沒有程式碼的情況下，電源應用程式提供用於應用程式開發的畫布。</span><span class="sxs-lookup"><span data-stu-id="16e16-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="16e16-375">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="16e16-376">可以將應用程式與群組共用，以執行及修改</span><span class="sxs-lookup"><span data-stu-id="16e16-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="16e16-377">**能源應用程式可以建立群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="16e16-378">否，電源應用程式無法建立 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="16e16-379">**是否有沒有群組的超級應用程式？**</span><span class="sxs-lookup"><span data-stu-id="16e16-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="16e16-380">是的，您可以在 Power App 內建立應用程式，並將其存放在建立者帳戶中，直到共用或發佈。</span><span class="sxs-lookup"><span data-stu-id="16e16-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="16e16-381">**每個群組可以有多個應用程式嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="16e16-382">是的，可以有多個應用程式與群組共用。</span><span class="sxs-lookup"><span data-stu-id="16e16-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="16e16-383">**是否可以將應用程式與多個群組相關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-384">是的，您可以使用多個群組共用應用程式。</span><span class="sxs-lookup"><span data-stu-id="16e16-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="16e16-385">**應用程式與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="16e16-386">是的，因為電源應用程式與 Microsoft 365 群組之間的關聯只會共用–該應用程式仍會與建立者一起存放。</span><span class="sxs-lookup"><span data-stu-id="16e16-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16e16-387">[群組必須先啟用安全性，應用程式才能與其共用](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="16e16-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="16e16-388">**刪除應用程式時，是否要刪除群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="16e16-389">否，應用程式不會連線至群組，而不是與其共用。</span><span class="sxs-lookup"><span data-stu-id="16e16-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="16e16-390">自動功耗</span><span class="sxs-lookup"><span data-stu-id="16e16-390">Power Automate</span></span>

<span data-ttu-id="16e16-391">Power automation (以前稱為 Microsoft Flow) 提供工作流程和自動化服務。</span><span class="sxs-lookup"><span data-stu-id="16e16-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="16e16-392">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="16e16-393">工作流程可以與群組共用，以執行及修改。</span><span class="sxs-lookup"><span data-stu-id="16e16-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="16e16-394">**您可以自動執行建立群組的功能嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="16e16-395">否，電源自動化無法在與一個關聯的上下文中建立 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="16e16-396">不過，您可以建立流程來執行各種作業，例如建立 Azure AD 安全性群組或更新 Microsoft 365 群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="16e16-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="16e16-397">**是否有不含群組的流程？**</span><span class="sxs-lookup"><span data-stu-id="16e16-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="16e16-398">是的，您可以在 Power 自動化內建立流量，並駐留在建立者帳戶中，直到共用或發佈。</span><span class="sxs-lookup"><span data-stu-id="16e16-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="16e16-399">**每個群組是否可以有多個資料流程？**</span><span class="sxs-lookup"><span data-stu-id="16e16-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="16e16-400">是的，可以有多個資料流程與群組共用。</span><span class="sxs-lookup"><span data-stu-id="16e16-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="16e16-401">**流程是否可以與多個群組相關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-402">是，可以與多個群組共用流程。</span><span class="sxs-lookup"><span data-stu-id="16e16-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="16e16-403">**流程與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="16e16-404">是的，由於電源自動化與 Microsoft 365 群組之間的關聯只會共用–該流程仍會與建立者一起使用。</span><span class="sxs-lookup"><span data-stu-id="16e16-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="16e16-405">**刪除流程會刪除群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="16e16-406">否，像電源應用程式一樣，資料流程未連接至群組，而非與其共用。</span><span class="sxs-lookup"><span data-stu-id="16e16-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="16e16-407">Power BI (傳統) </span><span class="sxs-lookup"><span data-stu-id="16e16-407">Power BI (classic)</span></span>

<span data-ttu-id="16e16-408">Power BI 提供互動式資料導向儀表板和報告。</span><span class="sxs-lookup"><span data-stu-id="16e16-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="16e16-409">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="16e16-410">資料包告</span><span class="sxs-lookup"><span data-stu-id="16e16-410">Data reporting</span></span>

<span data-ttu-id="16e16-411">**Power BI 是否可以建立群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="16e16-412">是的，建立傳統的工作區將會建立 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="16e16-413">**是否有不含群組的 Power BI 傳統工作區？**</span><span class="sxs-lookup"><span data-stu-id="16e16-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="16e16-414">否， [POWER BI 中的傳統工作區必須與群組產生關聯](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace)。</span><span class="sxs-lookup"><span data-stu-id="16e16-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="16e16-415">**每個群組是否可以有多個 Power BI 工作區？**</span><span class="sxs-lookup"><span data-stu-id="16e16-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="16e16-416">否，傳統的工作區和群組之間的關係為1:1。</span><span class="sxs-lookup"><span data-stu-id="16e16-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="16e16-417">**工作區是否可以與多個群組相關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-418">從技術上而言，在使用群組建立傳統的工作區時，內容可以與使用者和安全性群組在群組外共用。</span><span class="sxs-lookup"><span data-stu-id="16e16-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="16e16-419">**工作區與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="16e16-420">否，傳統的工作區本身會與群組產生關聯，但是可以在 Power BI 介面內從一個工作區移至另一個工作區，或是在本機匯出內容。</span><span class="sxs-lookup"><span data-stu-id="16e16-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="16e16-421">**刪除工作區後，是否要刪除群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="16e16-422">是，刪除 Power BI 中的工作區會刪除群組和群組相關聯的服務和內容。</span><span class="sxs-lookup"><span data-stu-id="16e16-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="16e16-423">Power BI (new) </span><span class="sxs-lookup"><span data-stu-id="16e16-423">Power BI (new)</span></span>

<span data-ttu-id="16e16-424">Power BI 提供互動式資料導向儀表板和報告。</span><span class="sxs-lookup"><span data-stu-id="16e16-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="16e16-425">在 Power BI 中建立新的工作區並不會建立 Microsoft 365 群組，以任何其他方式建立群組，會在 Power BI 中建立新的 (非經典) workspace。</span><span class="sxs-lookup"><span data-stu-id="16e16-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="16e16-426">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="16e16-427">資料包告</span><span class="sxs-lookup"><span data-stu-id="16e16-427">Data reporting</span></span>

<span data-ttu-id="16e16-428">**Power BI 是否可以建立群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="16e16-429">否，不可能從新的 Power BI 介面建立 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="16e16-430">**新的 Power BI workspace 是否有沒有群組的功能？**</span><span class="sxs-lookup"><span data-stu-id="16e16-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="16e16-431">是的，在 Power BI 中建立的報表和工作區可能與 Microsoft 365 群組沒有關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="16e16-432">**每個群組是否可以有多個工作區？**</span><span class="sxs-lookup"><span data-stu-id="16e16-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="16e16-433">是的， [可與單一群組共用 POWER BI 所建立的多個工作區](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)。</span><span class="sxs-lookup"><span data-stu-id="16e16-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="16e16-434">**工作區是否可以與多個群組相關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-435">否，由 Power BI 建立的工作區只能與單一群組相關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="16e16-436">**工作區與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="16e16-437">[是] 和 [否]。</span><span class="sxs-lookup"><span data-stu-id="16e16-437">Yes and no.</span></span> <span data-ttu-id="16e16-438">由 Power BI 建立的工作區一次只能與一個群組相關聯，但隨時可以變更關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="16e16-439">群組中的 Power BI 建立的工作區會永久關聯到該群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="16e16-440">**刪除工作區後，是否要刪除群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="16e16-441">是，刪除 Power BI 中的工作區會刪除群組和群組相關聯的服務和內容。</span><span class="sxs-lookup"><span data-stu-id="16e16-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="16e16-442">Project 網頁版</span><span class="sxs-lookup"><span data-stu-id="16e16-442">Project for the web</span></span>

<span data-ttu-id="16e16-443">Web 的專案提供建立專案計劃、甘特圖及路標的功能。</span><span class="sxs-lookup"><span data-stu-id="16e16-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="16e16-444">提供給群組的主要功能。</span><span class="sxs-lookup"><span data-stu-id="16e16-444">Key features provided to groups.</span></span>

- <span data-ttu-id="16e16-445">專案計劃</span><span class="sxs-lookup"><span data-stu-id="16e16-445">Project plans</span></span>

<span data-ttu-id="16e16-446">**您可以在網站上專案建立群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="16e16-447">是的，您可以直接從 Web 專案建立新的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="16e16-448">**是否有沒有群組的專案？**</span><span class="sxs-lookup"><span data-stu-id="16e16-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="16e16-449">是的專案可以存在，但不會與 Microsoft 365 群組產生關聯，但是工作指派需要群組關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="16e16-450">**每個群組是否可以有多個專案？**</span><span class="sxs-lookup"><span data-stu-id="16e16-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="16e16-451">是的，您可以在單一群組中連接多個專案。</span><span class="sxs-lookup"><span data-stu-id="16e16-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="16e16-452">**專案是否可以與多個群組相關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-453">否，專案只能與單一群組相關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="16e16-454">**專案與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="16e16-455">否，建立與群組的關聯之後，就無法變更。</span><span class="sxs-lookup"><span data-stu-id="16e16-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="16e16-456">**刪除專案時是否刪除群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="16e16-457">否，刪除網路專案中的專案不會刪除群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="16e16-458">藍圖</span><span class="sxs-lookup"><span data-stu-id="16e16-458">Roadmap</span></span>

<span data-ttu-id="16e16-459">藍圖提供與 web 和 Project Online 的專案建立專案藍圖的能力。</span><span class="sxs-lookup"><span data-stu-id="16e16-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="16e16-460">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="16e16-461">專案藍圖</span><span class="sxs-lookup"><span data-stu-id="16e16-461">Project roadmaps</span></span>

<span data-ttu-id="16e16-462">**藍圖是否可以建立群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="16e16-463">是的，您可以直接從藍圖建立新的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="16e16-464">**是否有沒有群組的藍圖？**</span><span class="sxs-lookup"><span data-stu-id="16e16-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="16e16-465">是的，路線圖可以存在，但不會與 Microsoft 365 群組產生關聯，但共用藍圖需要群組關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="16e16-466">**每個群組是否可以有多個路線圖？**</span><span class="sxs-lookup"><span data-stu-id="16e16-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="16e16-467">是的，您可以將多個藍圖連線到單一群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="16e16-468">**藍圖是否可以與多個群組相關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-469">否，藍圖只會與單一群組相關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="16e16-470">**藍圖與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="16e16-471">否，建立與群組的關聯之後，就無法變更。</span><span class="sxs-lookup"><span data-stu-id="16e16-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="16e16-472">**刪除藍圖之後刪除群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="16e16-473">否，刪除藍圖不會刪除群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="16e16-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="16e16-474">SharePoint</span></span>

<span data-ttu-id="16e16-475">SharePoint 是以網路為基礎的內容管理平臺，可提供許多 Microsoft 365 服務的儲存服務。</span><span class="sxs-lookup"><span data-stu-id="16e16-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="16e16-476">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="16e16-477">文件庫</span><span class="sxs-lookup"><span data-stu-id="16e16-477">Document library</span></span>
- <span data-ttu-id="16e16-478">存放 OneNote 筆記本的存放庫</span><span class="sxs-lookup"><span data-stu-id="16e16-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="16e16-479">團隊 wiki 檔案的儲存</span><span class="sxs-lookup"><span data-stu-id="16e16-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="16e16-480">**可以 SharePoint 建立群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="16e16-481">是的，在 SharePoint 中建立小組網站時，預設會建立 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="16e16-482">您也可以建立群組，並選擇性地建立現有網站的團隊。</span><span class="sxs-lookup"><span data-stu-id="16e16-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="16e16-483">**是否有沒有群組的 SharePoint 網站？**</span><span class="sxs-lookup"><span data-stu-id="16e16-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="16e16-484">是的，SharePoint 提供許多非群組相關的服務和網站，例如通訊和 hub 網站。</span><span class="sxs-lookup"><span data-stu-id="16e16-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="16e16-485">**每個群組可以有多個網站嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="16e16-486">否，每個群組只能有一個網站。</span><span class="sxs-lookup"><span data-stu-id="16e16-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="16e16-487">小組中的私人管道使用的其他網站未連接至群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="16e16-488">**是否可以將網站與多個群組相關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-489">技術否，但在使用群組建立網站時，內容可以與其他群組共用。</span><span class="sxs-lookup"><span data-stu-id="16e16-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="16e16-490">**網站與群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="16e16-491">否，網站本身會與群組產生關聯，但是可以在 SharePoint 介面內，透過在本機匯出內容，或使用協力廠商工具，將內容移至介面中的另一個網站。</span><span class="sxs-lookup"><span data-stu-id="16e16-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="16e16-492">**刪除網站刪除群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="16e16-493">是，在 SharePoint 中刪除網站會刪除群組和群組相關聯的服務和內容。</span><span class="sxs-lookup"><span data-stu-id="16e16-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="16e16-494">Stream</span><span class="sxs-lookup"><span data-stu-id="16e16-494">Stream</span></span>

<span data-ttu-id="16e16-495">Microsoft Stream 是一種影片主控和共用平臺。</span><span class="sxs-lookup"><span data-stu-id="16e16-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="16e16-496">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="16e16-497">影片儲存體</span><span class="sxs-lookup"><span data-stu-id="16e16-497">Video storage</span></span>
- <span data-ttu-id="16e16-498">小組會議錄製</span><span class="sxs-lookup"><span data-stu-id="16e16-498">Teams meeting recording</span></span>
- <span data-ttu-id="16e16-499">影片通道</span><span class="sxs-lookup"><span data-stu-id="16e16-499">Video channels</span></span>

<span data-ttu-id="16e16-500">**Stream 是否可以建立群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="16e16-501">是的，您可以直接從 Stream 建立新的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="16e16-502">**是否有不含群組的資料流程？**</span><span class="sxs-lookup"><span data-stu-id="16e16-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="16e16-503">是的，視頻通道和影片可以存在於 Stream 中，但不會與群組產生關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="16e16-504">**每個群組是否可以有多個影片和通道？**</span><span class="sxs-lookup"><span data-stu-id="16e16-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="16e16-505">是的，每個群組中可以有多個影片和頻道。</span><span class="sxs-lookup"><span data-stu-id="16e16-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="16e16-506">**影片或通道是否可以與多個群組產生關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="16e16-507">是的，雖然使用群組建立影片或通道，但可與其他群組共用。</span><span class="sxs-lookup"><span data-stu-id="16e16-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="16e16-508">**與其群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="16e16-509">是和否;Stream 中的影片是由原始的上載程式或會議錄製器所擁有，因此可以與任何群組相關聯，但是影片通道只會與其最初建立所在的群組相關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="16e16-510">**刪除影片或頻道會刪除群組嗎？**</span><span class="sxs-lookup"><span data-stu-id="16e16-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="16e16-511">否，刪除影片或頻道不會刪除群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="16e16-512">不過，在 Stream 中刪除群組本身會刪除與群組相關聯的服務和內容，但實際的影片除外。</span><span class="sxs-lookup"><span data-stu-id="16e16-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="16e16-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="16e16-513">Yammer</span></span>

<span data-ttu-id="16e16-514">Yammer 是一種企業社交平臺，可促進組織內部及組織之間的社區參與。</span><span class="sxs-lookup"><span data-stu-id="16e16-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="16e16-515">在 Yammer 中建立的社區 (以前稱為「群組」 ) 會建立信箱，但目前卻不會使用。</span><span class="sxs-lookup"><span data-stu-id="16e16-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="16e16-516">與 Yammer 關聯的 Microsoft 365 群組無法與 Microsoft 小組中的小組一起使用。</span><span class="sxs-lookup"><span data-stu-id="16e16-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="16e16-517">**提供給群組的主要功能**</span><span class="sxs-lookup"><span data-stu-id="16e16-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="16e16-518">交談區域</span><span class="sxs-lookup"><span data-stu-id="16e16-518">Conversation area</span></span>

<span data-ttu-id="16e16-519">**Yammer 是否可以建立 Microsoft 365 群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="16e16-520">是，在 Yammer 中建立新的群組會建立新的 Microsoft 365 群組，如果已連線平臺，而且使用者具備建立群組的能力。</span><span class="sxs-lookup"><span data-stu-id="16e16-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="16e16-521">在 Yammer 本身以外的任何介面或服務中，都無法建立與 Microsoft 365 群組相關聯的 Yammer 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="16e16-522">**Yammer 群組是否存在於沒有 Microsoft 365 群組的情況？**</span><span class="sxs-lookup"><span data-stu-id="16e16-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="16e16-523">是的，您可以建立沒有 Microsoft 365 群組的 Yammer 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="16e16-524">如果 Yammer 平臺未連接至 Microsoft 365 群組，或使用者沒有建立 Microsoft 365 群組的能力，就會建立 Yammer 群組，而不需要 Microsoft 365 群組關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="16e16-525">**每個 Microsoft 365 群組是否可以有多個 Yammer 群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="16e16-526">否，Yammer 群組和 Microsoft 365 群組之間的關聯性為1:1。</span><span class="sxs-lookup"><span data-stu-id="16e16-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="16e16-527">**Yammer 群組是否可以與多個 Microsoft 365 群組相關聯？**</span><span class="sxs-lookup"><span data-stu-id="16e16-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="16e16-528">否，Yammer 群組僅可與單一 Microsoft 365 群組相關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="16e16-529">您可以與其他 Yammer 群組共用帖子或將其移至其他 Yammer 群組。</span><span class="sxs-lookup"><span data-stu-id="16e16-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="16e16-530">**Yammer 群組與 Microsoft 365 群組的關聯是否可以變更？**</span><span class="sxs-lookup"><span data-stu-id="16e16-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="16e16-531">否，Yammer 群組只會與其原來關聯的 Microsoft 365 群組相關聯。</span><span class="sxs-lookup"><span data-stu-id="16e16-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="16e16-532">**刪除 Yammer 群組是否刪除 Microsoft 365 群組？**</span><span class="sxs-lookup"><span data-stu-id="16e16-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="16e16-533">是，刪除 Yammer 中的群組會刪除相關的 Microsoft 群組和群組相關聯的服務和內容。</span><span class="sxs-lookup"><span data-stu-id="16e16-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

