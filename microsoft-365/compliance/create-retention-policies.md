---
title: 建立及設定保留原則以自動保留或刪除內容
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 使用保留原則可以非常有效地控制使用者透過電子郵件、文件和交談生成的內容。 保留想要的內容，清除不想要的內容。
ms.openlocfilehash: b992452cffbe7fa2df5e7ad02726ca337fbe0f45
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816841"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="55f06-104">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="55f06-104">Create and configure retention policies</span></span>

><span data-ttu-id="55f06-105">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="55f06-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="55f06-106">使用保留原則主動決定是否要保留內容、刪除內容，還是兩者，即保留然後刪除內容。</span><span class="sxs-lookup"><span data-stu-id="55f06-106">Use a retention policy to decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span> 

<span data-ttu-id="55f06-107">透過將相同的保留設定依照位置如網站或信箱層級的內容進行指派，保留原則可讓您工作的更有效率，。</span><span class="sxs-lookup"><span data-stu-id="55f06-107">A retention policy lets you do this very efficiently by assigning the same retention settings for content by location, at a site or mailbox level.</span></span> <span data-ttu-id="55f06-108">如果您不確定是否要使用保留原則或保留標籤，可參閱[保留原則及保留標籤](retention.md#retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="55f06-108">If you're not sure whether to use a retention policy or a retention label, see [Retention policies and retention labels](retention.md#retention-policies-and-retention-labels).</span></span>

<span data-ttu-id="55f06-109">如需有關保留原則及其運作方式的詳細資訊，可參閱 [瞭解保留原則和保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="55f06-109">For more information about retention policies and how retention works, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="55f06-110">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="55f06-110">Before you begin</span></span>

<span data-ttu-id="55f06-111">您組織中的全域系統管理員擁有建立及管理保留標籤及其原則的完整權限。</span><span class="sxs-lookup"><span data-stu-id="55f06-111">The global admin for your organization has full permissions to create and edit retention policies.</span></span> <span data-ttu-id="55f06-112">若您未以全域系統管理員的身分登入，請參閱 [建立和管理保留標籤所需權限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="55f06-112">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="55f06-113">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="55f06-113">Create and configure a retention policy</span></span>

<span data-ttu-id="55f06-114">雖然保留原則可以支援多個位置，但您無法建立含括所有支援位置的單一個保留原則：</span><span class="sxs-lookup"><span data-stu-id="55f06-114">Although a retention policy can support multiple locations, you can't create a single retention policy that includes all the supported locations:</span></span>
- <span data-ttu-id="55f06-115">Exchange 電子郵件</span><span class="sxs-lookup"><span data-stu-id="55f06-115">Exchange email</span></span>
- <span data-ttu-id="55f06-116">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="55f06-116">SharePoint site</span></span>
- <span data-ttu-id="55f06-117">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="55f06-117">OneDrive accounts</span></span>
- <span data-ttu-id="55f06-118">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="55f06-118">Microsoft 365 groups</span></span>
- <span data-ttu-id="55f06-119">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="55f06-119">Skype for Business</span></span>
- <span data-ttu-id="55f06-120">Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="55f06-120">Exchange public folders</span></span>
- <span data-ttu-id="55f06-121">Teams 通道訊息</span><span class="sxs-lookup"><span data-stu-id="55f06-121">Teams channel messages</span></span>
- <span data-ttu-id="55f06-122">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="55f06-122">Teams chats</span></span>

<span data-ttu-id="55f06-123">當您在建立保留原則時選取任一個 Teams 位置時，系統會自動排除其他的位置。</span><span class="sxs-lookup"><span data-stu-id="55f06-123">When you select either of the Teams locations when you create a retention policy, the other locations are automatically excluded.</span></span> <span data-ttu-id="55f06-124">因此，請依照您是否要涵蓋 Teams 位置來決定要遵循的指示：</span><span class="sxs-lookup"><span data-stu-id="55f06-124">Therefore, the instructions to follow depend on whether you need to include the Teams locations:</span></span>

- [<span data-ttu-id="55f06-125">Teams 位置的保留原則相關指示</span><span class="sxs-lookup"><span data-stu-id="55f06-125">Instructions for a retention policy for Teams locations</span></span>](#retention-policy-for-teams-locations)
- [<span data-ttu-id="55f06-126">除了 Teams 以外的位置保留原則相關指示</span><span class="sxs-lookup"><span data-stu-id="55f06-126">Instructions for a retention policy for locations other than Teams</span></span>](#retention-policy-for-locations-other-than-teams)

<span data-ttu-id="55f06-127">當您有多個保留原則，以及當您同時使用保留標籤時，請參閱 [保留原則優先或以什麼為優先？](retention.md#the-principles-of-retention-or-what-takes-precedence) 以瞭解在相同的內容上同時有多個保留設定套用時，會有什麼樣的結果。</span><span class="sxs-lookup"><span data-stu-id="55f06-127">When you have more than one retention policy, and when you also use retention labels, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) to understand the outcome when multiple retention settings apply to the same content.</span></span>

### <a name="retention-policy-for-teams-locations"></a><span data-ttu-id="55f06-128">Teams 位置的保留原則</span><span class="sxs-lookup"><span data-stu-id="55f06-128">Retention policy for Teams locations</span></span>

1. <span data-ttu-id="55f06-129">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。</span><span class="sxs-lookup"><span data-stu-id="55f06-129">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="55f06-130">選取 **[新保留原則]** 以啟動 [建立保留原則] 精靈，並命名新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="55f06-130">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="55f06-131">對於 **[選擇要套用原則的位置]** 頁面，請為 Teams 選取一個或兩個位置：**Teams 頻道訊息**和 **Teams 聊天**。</span><span class="sxs-lookup"><span data-stu-id="55f06-131">For the **Choose locations to apply the policy** page, select one or both of the locations for Teams: **Teams channel message** and **Teams chats**.</span></span>
     
    <span data-ttu-id="55f06-132">針對 **Teams 頻道訊息**，會包含來自標準頻道的訊息，但不會包含 [私人頻道](https://docs.microsoft.com/microsoftteams/private-channels)。</span><span class="sxs-lookup"><span data-stu-id="55f06-132">For **Teams channel messages**, message from standard channels but not [private channels](https://docs.microsoft.com/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="55f06-133">目前，保留原則尚未支援 [私人頻道]。</span><span class="sxs-lookup"><span data-stu-id="55f06-133">Currently, private channels aren't supported by retention policies.</span></span>
    
    <span data-ttu-id="55f06-134">根據預設，[所有小組和所有使用者都處於選中狀態](#a-policy-that-applies-to-entire-locations)，但您可以透過選取 [**[選擇]** 和 **[排除]** 選項](#a-policy-with-specific-inclusions-or-exclusions)對其進行優化。</span><span class="sxs-lookup"><span data-stu-id="55f06-134">By default, [all teams and all users are selected](#a-policy-that-applies-to-entire-locations), but you can refine this by selecting the [**Choose** and **Exclude** options](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

4. <span data-ttu-id="55f06-135">在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。</span><span class="sxs-lookup"><span data-stu-id="55f06-135">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>
    
    <span data-ttu-id="55f06-136">您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。</span><span class="sxs-lookup"><span data-stu-id="55f06-136">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="55f06-137">如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="55f06-137">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>
    
5. <span data-ttu-id="55f06-138">完成精靈以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="55f06-138">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="55f06-139">如需 Teams 保留原則的詳細資訊，請參閱在 Teams 文件中的 [Microsoft Teams 的保留原則](https://docs.microsoft.com/microsoftteams/retention-policies)。</span><span class="sxs-lookup"><span data-stu-id="55f06-139">For more information about retention policies for Teams, see [Retention policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies) from the Teams documentation.</span></span>

#### <a name="additional-retention-policy-needed-to-support-teams"></a><span data-ttu-id="55f06-140">支援 Teams 所需的其他保留原則</span><span class="sxs-lookup"><span data-stu-id="55f06-140">Additional retention policy needed to support Teams</span></span>

<span data-ttu-id="55f06-141">Teams 不僅是提供聊天和頻道訊息功能，還有更多功能。</span><span class="sxs-lookup"><span data-stu-id="55f06-141">Teams is more than just chats and channel messages.</span></span> <span data-ttu-id="55f06-142">如果您有透過 Microsoft 365 群組 (之前稱為 Office 365 群組) 建立的團隊，您應該額外使用 **Office 365 群組**位置來設定包含該 Microsoft 365 群組的保留原則。</span><span class="sxs-lookup"><span data-stu-id="55f06-142">If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Office 365 groups** location.</span></span> <span data-ttu-id="55f06-143">此保留原則適用於群組的信箱、網站和檔案中的內容。</span><span class="sxs-lookup"><span data-stu-id="55f06-143">This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="55f06-144">如果您有未與 Microsoft 365 群組連線的 Teams 位置，您需要有可以包含 **SharePoint 網站**或 **OneDrive 帳戶**位置的保留原則，用以保留及刪除 Teams 中的檔案：</span><span class="sxs-lookup"><span data-stu-id="55f06-144">If you have team sites that aren't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="55f06-145">在聊天中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="55f06-145">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span> 

- <span data-ttu-id="55f06-146">上傳至頻道的檔案則會儲存在團隊的 SharePoint 網站中。</span><span class="sxs-lookup"><span data-stu-id="55f06-146">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="55f06-147">當團隊未連線至 Microsoft 365 時，您可以將保留原則套用到僅特定團隊的檔案，方法是選取團隊的 SharePoint 網站，以及團隊中使用者的 OneDrive 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="55f06-147">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="55f06-148">套用至 Microsoft 365、SharePoint 網站或 OneDrive 帳戶的保留原則有可能會刪除 Teams 聊天中參考的檔案，或在頻道訊息刪除前就將其刪除。</span><span class="sxs-lookup"><span data-stu-id="55f06-148">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="55f06-149">在這種情況下，檔案仍會顯示在 Teams 訊息中，但是當使用者選取檔案時，會收到「找不到檔案」錯誤。</span><span class="sxs-lookup"><span data-stu-id="55f06-149">In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="55f06-150">此行為並非保留原則特定，因此也可能在使用者從 SharePoint 或 OneDrive 中手動刪除檔案時發生。</span><span class="sxs-lookup"><span data-stu-id="55f06-150">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>


### <a name="retention-policy-for-locations-other-than-teams"></a><span data-ttu-id="55f06-151">除了 Teams 以外的位置保留原則</span><span class="sxs-lookup"><span data-stu-id="55f06-151">Retention policy for locations other than Teams</span></span>

1. <span data-ttu-id="55f06-152">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。</span><span class="sxs-lookup"><span data-stu-id="55f06-152">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="55f06-153">選取 **[新保留原則]** 以啟動 [建立保留原則] 精靈，並命名新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="55f06-153">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="55f06-154">對於 **[選擇位置]** 頁面，開啟或關閉除 Teams 位置以外的任何位置。</span><span class="sxs-lookup"><span data-stu-id="55f06-154">For the **Choose locations** page, toggle on or off any of the locations except the locations for Teams.</span></span> <span data-ttu-id="55f06-155">您可以將每個位置保留為預設值，以便[將原則套用於整個位置](#a-policy-that-applies-to-entire-locations)，或[指定包含和排除](#a-policy-with-specific-inclusions-or-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="55f06-155">For each location, you can leave it at the default to [apply the policy to the entire location](#a-policy-that-applies-to-entire-locations), or [specify includes and excludes](#a-policy-with-specific-inclusions-or-exclusions).</span></span> 
    
    <span data-ttu-id="55f06-156">位置專用資訊：</span><span class="sxs-lookup"><span data-stu-id="55f06-156">Information specific to locations:</span></span>
    - [<span data-ttu-id="55f06-157">Exchange 電子郵件和 Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="55f06-157">Exchange email and Exchange public folders</span></span>](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [<span data-ttu-id="55f06-158">SharePoint 網站和 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="55f06-158">SharePoint sites and OneDrive accounts</span></span>](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [<span data-ttu-id="55f06-159">Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="55f06-159">Office 365 groups</span></span>](#configuration-information-for-microsoft-365-groups)
    - [<span data-ttu-id="55f06-160">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="55f06-160">Skype for Business</span></span>](#configuration-information-for-skype-for-business)

4. <span data-ttu-id="55f06-161">在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。</span><span class="sxs-lookup"><span data-stu-id="55f06-161">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>
    
    <span data-ttu-id="55f06-162">您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。</span><span class="sxs-lookup"><span data-stu-id="55f06-162">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="55f06-163">如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="55f06-163">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="55f06-164">完成精靈以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="55f06-164">Complete the wizard to save your settings.</span></span>


#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a><span data-ttu-id="55f06-165">Exchange 電子郵件和 Exchange 公用資料夾的設定資訊</span><span class="sxs-lookup"><span data-stu-id="55f06-165">Configuration information for Exchange email and Exchange public folders</span></span>

<span data-ttu-id="55f06-166">**Exchange 電子郵件** 位置支援使用者的電子郵件、行事曆和其他信箱專案的保留，方法是套用信箱層級的保留設定。</span><span class="sxs-lookup"><span data-stu-id="55f06-166">The **Exchange email** location supports retention for users' email, calendar, and other mailbox items, by applying retention settings at the level of a mailbox.</span></span>

<span data-ttu-id="55f06-167">包含了以下的電子郵件項目：郵件訊息（包括草稿）具有任何的附件檔案、工作和行事曆項目（具有結束日期），以及備註。</span><span class="sxs-lookup"><span data-stu-id="55f06-167">The following mail items are included: Mail messages (includes drafts) with any attachments, tasks and calendar items when they have an end date, and notes.</span></span> <span data-ttu-id="55f06-168">不包含沒有結束日期標示的連絡人、任何工作和行事曆項目。</span><span class="sxs-lookup"><span data-stu-id="55f06-168">Contacts, and any tasks and calendar items that don't have an end date are not included.</span></span> <span data-ttu-id="55f06-169">儲存在信箱中（例如 Skype 和 Teams 儲存的訊息）的其他項目不會包含在此位置。</span><span class="sxs-lookup"><span data-stu-id="55f06-169">Other items stored in a mailbox, such as Skype and Teams saved messages, aren't included with this location.</span></span> <span data-ttu-id="55f06-170">這些項目有各自具備的保留原則。</span><span class="sxs-lookup"><span data-stu-id="55f06-170">These items have their own retention locations.</span></span>

<span data-ttu-id="55f06-171">即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件**位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="55f06-171">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="55f06-172">若要保留這些信箱中的內容，請選取 **[Office 365 群組]** 位置。</span><span class="sxs-lookup"><span data-stu-id="55f06-172">To retain content in these mailboxes, select the **Office 365 groups** location.</span></span>

<span data-ttu-id="55f06-173">**Exchange 公用資料夾** 位置會將保留設定套用至所有的公用資料夾，且無法在資料夾或信箱層級套用。</span><span class="sxs-lookup"><span data-stu-id="55f06-173">The **Exchange public folders** location applies retention settings to all public folders and can't be applied at the folder or mailbox level.</span></span>

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a><span data-ttu-id="55f06-174">SharePoint 網站和 OneDrive 帳戶的配置資訊</span><span class="sxs-lookup"><span data-stu-id="55f06-174">Configuration information for SharePoint sites and OneDrive accounts</span></span>

<span data-ttu-id="55f06-175">當您選擇 **SharePoint 網站** 位置時，保留原則即可保留和刪除在 SharePoint 通訊網站中的文件、未與 Office 365 群組連結的小組網站，以及傳統網站。</span><span class="sxs-lookup"><span data-stu-id="55f06-175">When you choose the **SharePoint sites** location, the retention policy can retain and delete documents in SharePoint communication sites, team sites that aren't connected by Office 365 groups, and classic sites.</span></span> <span data-ttu-id="55f06-176">此選項不支援由 Office 365 群組所連結的小組網站，而是使用套用倒群組信箱、網站和檔案中的內容的 **Office 365 群組**位置。</span><span class="sxs-lookup"><span data-stu-id="55f06-176">Team sites connected by Office 365 groups aren't supported with this option and instead, use the **Office 365 groups** location that applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="55f06-177">雖然保留原則可套用到網站層級，但只有文件會套用保留設定。</span><span class="sxs-lookup"><span data-stu-id="55f06-177">Although the retention policy is applied at the site level, only documents have retention settings applied to them.</span></span> <span data-ttu-id="55f06-178">保留設定不適用於組織結構，包含像是文件庫、清單及網站內的資料夾。</span><span class="sxs-lookup"><span data-stu-id="55f06-178">Retention settings do not apply to the organizing structures that include libraries, lists, and folders within the site.</span></span> 

<span data-ttu-id="55f06-179">當您為 SharePoint 網站或 OneDrive 帳戶指定您的位置時，您不需要存取網站的權限，而當你在 **[編輯位置]** 頁面上指定 URL 時也不會需要進行任何的驗證。</span><span class="sxs-lookup"><span data-stu-id="55f06-179">When you specify your locations for SharePoint sites or OneDrive accounts, you don't need permissions to access the sites and no validation is done at the time you specify the URL on the **Edit locations** page.</span></span> <span data-ttu-id="55f06-180">不過，SharePoint 網站必須編制索引，而您指定的網站會在精靈結束時進行檢查，以確認這些網站是否存在。</span><span class="sxs-lookup"><span data-stu-id="55f06-180">However, the SharePoint sites must be indexed and the sites that you specify are checked that they exist at the end of the wizard.</span></span>

<span data-ttu-id="55f06-181">如果此檢查失敗，您會看到一則訊息，指出您輸入的 URL 驗證失敗，且精靈不會建立保留原則，直到驗證檢查通過為止。</span><span class="sxs-lookup"><span data-stu-id="55f06-181">If this check fails, you see a message that validation failed for the URL you entered, and the wizard won't create the retention policy until the validation check passes.</span></span> <span data-ttu-id="55f06-182">如果您看到這則訊息，請返回精靈並變更 URL 或從保留原則將網站移除。</span><span class="sxs-lookup"><span data-stu-id="55f06-182">If you see this message, go back in the wizard to change the URL or remove the site from the retention policy.</span></span>

<span data-ttu-id="55f06-183">若要特別指定包含或排除某個 OneDrive 帳戶，URL 的格式要求如下：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="55f06-183">To specify individual OneDrive accounts to include or exclude, the URL has the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>

<span data-ttu-id="55f06-184">例如，針對 contoso 租用戶中使用者名稱為 "rsimone" 的使用者：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="55f06-184">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>

<span data-ttu-id="55f06-185">若要驗證租用戶的語法並識別使用者的 URL，請參閱[取得組織中所有使用者的 OneDrive URL 清單](https://docs.microsoft.com/onedrive/list-onedrive-urls) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="55f06-185">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="55f06-186">Microsoft 365 群組的設定資訊</span><span class="sxs-lookup"><span data-stu-id="55f06-186">Configuration information for Microsoft 365 groups</span></span>

<span data-ttu-id="55f06-187">若要保留或刪除一個 Microsoft 365 群組（之前稱為 Office 365 群組）的內容，請使用 **Office 365 群組** 的位置。</span><span class="sxs-lookup"><span data-stu-id="55f06-187">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), use the **Office 365 groups** location.</span></span> <span data-ttu-id="55f06-188">即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件**位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="55f06-188">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="55f06-189">此外，雖然 **Exchange 電子郵件**位置一開始會允許您指定要包含或排除的群組信箱，但是當您嘗試儲存保留原則時，您會收到 "RemoteGroupMailbox" 不是Exchange 位置的有效選項錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="55f06-189">In addition, although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="55f06-190">如果建立群組時或稍後將小組網站新增至群組時已選取小組網站，則套用到 Microsoft 365 群組的保留策略包含群組信箱與小組網站。</span><span class="sxs-lookup"><span data-stu-id="55f06-190">A retention policy applied to a Microsoft 365 group includes the group mailbox and teams site, if a teams site was selected at the time the group was created or later added to the group.</span></span> <span data-ttu-id="55f06-191">此位置涵蓋儲存在小組網站中的檔案，但不涵蓋有自己的保留原則位置的小組聊天或小組頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="55f06-191">Files stored in the teams site are covered with this location, but not Teams chats or Teams channel messages that have their own retention policy locations.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="55f06-192">商務用 Skype 的設定資訊</span><span class="sxs-lookup"><span data-stu-id="55f06-192">Configuration information for Skype for Business</span></span>

<span data-ttu-id="55f06-193">不同於 Exchange 電子郵件，您無法將 Skype 位置的狀態切換為開啟以自動包含所有使用者，但當您開啟該位置時，必須手動選擇您想要保留其交談的使用者：</span><span class="sxs-lookup"><span data-stu-id="55f06-193">Unlike Exchange email, you can't toggle the status of the Skype location on to automatically include all users, but when you turn on that location, you must then manually choose the users whose conversations you want to retain:</span></span>

![為保留原則選擇 Skype 位置](../media/skype-location-retention-policies.png)
  
<span data-ttu-id="55f06-195">當您選取 **[選擇使用者]** 時，您可以選取 **[選取所有]** 方塊，快速包含所有使用者。</span><span class="sxs-lookup"><span data-stu-id="55f06-195">When you select **Choose user**, you can quickly include all users by selecting the **Select all** box.</span></span> <span data-ttu-id="55f06-196">不過，請務必了解，會將每個使用者算成原則中的一個特定包含。</span><span class="sxs-lookup"><span data-stu-id="55f06-196">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="55f06-197">因此，如果透過選擇 **[全選]** 方塊拉包含 1000 位使用者，則與手動選取要包含的 1000 位使用者相同，這是 商務用 Skype 支持的最大值。</span><span class="sxs-lookup"><span data-stu-id="55f06-197">So if you include 1,000 users by selecting the **Select all** box, it's the same as if you manually selected 1,000 users to include, which is the maximum supported for Skype for Business.</span></span>

<span data-ttu-id="55f06-198">請注意 Outlook 中的 **[交談記錄]** 資料夾的功能與 Skype 封存毫無關聯。</span><span class="sxs-lookup"><span data-stu-id="55f06-198">Be aware that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving.</span></span> <span data-ttu-id="55f06-199">使用者可以關閉 **[交談記錄]**，但 Skype 封存的運作方式是，將 Skype 交談的複本儲存在使用者無法存取但 eDiscovery 可以使用的隱藏資料夾。</span><span class="sxs-lookup"><span data-stu-id="55f06-199">**Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>

## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="55f06-200">保留和刪除內容的設定</span><span class="sxs-lookup"><span data-stu-id="55f06-200">Settings for retaining and deleting content</span></span>

<span data-ttu-id="55f06-201">透過在保留原則中選擇用於保留和刪除內容的設定，您的保留原則會具有下列其中一個設定達一段指定的期間：</span><span class="sxs-lookup"><span data-stu-id="55f06-201">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="55f06-202">僅保留</span><span class="sxs-lookup"><span data-stu-id="55f06-202">Retain-only</span></span>
    
    <span data-ttu-id="55f06-203">在此設定中，請選擇 **[在特定期內保留項目]** 和**在保留期結束時：不做任何處理**。</span><span class="sxs-lookup"><span data-stu-id="55f06-203">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Do nothing**.</span></span> <span data-ttu-id="55f06-204">或者，選取 **[永遠保留項目]**。</span><span class="sxs-lookup"><span data-stu-id="55f06-204">Or, select **Retain items forever**.</span></span>

- <span data-ttu-id="55f06-205">保留然後刪除</span><span class="sxs-lookup"><span data-stu-id="55f06-205">Retain and then delete</span></span>
    
    <span data-ttu-id="55f06-206">在此設定中，請選擇 **[在特定期內保留項目]** 和**在保留期結束時：自動刪除項目**。</span><span class="sxs-lookup"><span data-stu-id="55f06-206">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Delete items automatically**.</span></span>

- <span data-ttu-id="55f06-207">僅刪除</span><span class="sxs-lookup"><span data-stu-id="55f06-207">Delete-only</span></span>
    
    <span data-ttu-id="55f06-208">在此設定中，選擇 **「只有項目達到特定存留期時才刪除它」**。</span><span class="sxs-lookup"><span data-stu-id="55f06-208">For this configuration, choose **Only delete items when they reach a certain age**.</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="55f06-209">將內容保留特定的一段時間</span><span class="sxs-lookup"><span data-stu-id="55f06-209">Retaining content for a specific period of time</span></span>

<span data-ttu-id="55f06-210">設定保留原則時，您會選擇保留項目，或將其保留特定數天、數月或數年。</span><span class="sxs-lookup"><span data-stu-id="55f06-210">When you configure a retention policy, you choose to retain items for a specific number of days, months, or years.</span></span> <span data-ttu-id="55f06-211">或者永遠保留項目。</span><span class="sxs-lookup"><span data-stu-id="55f06-211">Or alternatively, retain the items forever.</span></span>

<span data-ttu-id="55f06-212">設定保留原則時，您可以選擇無限期保留內容，或將內容保留特定數天、數月或數年。</span><span class="sxs-lookup"><span data-stu-id="55f06-212">When you configure a retention policy, you can choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="55f06-213">保留時長是從內容的存留期起算，而不是從套用保留原則的時間起算。</span><span class="sxs-lookup"><span data-stu-id="55f06-213">The retention period is calculated from the age of the content, not from when the retention policy is applied.</span></span> 

<span data-ttu-id="55f06-214">保留期開始時，您還可以選擇建立內容的時間，或者只支援檔案和 SharePoint、OneDrive 和 Office 365 位置的內容上次修改的時間。</span><span class="sxs-lookup"><span data-stu-id="55f06-214">For the start of the retention period, you can also choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Office 365 locations, when the content was last modified.</span></span>

<span data-ttu-id="55f06-215">範例：</span><span class="sxs-lookup"><span data-stu-id="55f06-215">Examples:</span></span>
  
- <span data-ttu-id="55f06-216">SharePoint：如果您在將網站集合中的項目在上次修改后保留七年，而該網站集合中的某文件已有六年未曾修改，如果後續仍未修改該文件，則只會再保留該文件一年。</span><span class="sxs-lookup"><span data-stu-id="55f06-216">SharePoint: If you want to retain items in a site collection for seven years after this content is last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified.</span></span> <span data-ttu-id="55f06-217">如果該文件重新編輯，則其存留期將會從新的前次修改日期起算，因而會再保留七年。</span><span class="sxs-lookup"><span data-stu-id="55f06-217">If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>
  
- <span data-ttu-id="55f06-218">Exchange：同樣地，如果您要讓信箱中的項目保留七年，而六年前已傳送過某封郵件，該郵件則只會再保留一年。</span><span class="sxs-lookup"><span data-stu-id="55f06-218">Exchange: If you want to retain items in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year.</span></span> <span data-ttu-id="55f06-219">若為 Exchange 項目，時限是以收到內送電子郵件的日期，或傳送外寄電子郵件的日期為基礎。</span><span class="sxs-lookup"><span data-stu-id="55f06-219">For Exchange items, the age is based on the date received for incoming email, or the date sent for outgoing email.</span></span> <span data-ttu-id="55f06-220">根據前次修改時間保留項目只會套用到 OneDrive 和 SharePoint 中的網站內容。</span><span class="sxs-lookup"><span data-stu-id="55f06-220">Retaining items based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>
  
<span data-ttu-id="55f06-221">在保留期間結束時，您會選擇是否要永久刪除內容：</span><span class="sxs-lookup"><span data-stu-id="55f06-221">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>
  
![保留設定頁面](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="55f06-223">刪除早於特定存留期的內容</span><span class="sxs-lookup"><span data-stu-id="55f06-223">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="55f06-224">保留原則可以保留然後刪除項目，或刪除舊項目而不保留它們。</span><span class="sxs-lookup"><span data-stu-id="55f06-224">A retention policy can both retain and then delete items, or delete old items without retaining them.</span></span>
  
<span data-ttu-id="55f06-225">在這兩種情況下，如果您的保留原則刪除項目，請務必了解，文件刪除原則所指定的期限並不是從指派原則的時間算起，而是從建立或修改項目的時間算起。</span><span class="sxs-lookup"><span data-stu-id="55f06-225">In both cases, if your retention policy deletes items, it's important to understand that the time period specified for a retention policy is calculated from the time when the item was created or modified, and not the time since the policy was assigned.</span></span>

<span data-ttu-id="55f06-226">因此，在第一次指派保留原則之前，尤其是在該原則删除項目時，請首先考慮現有內容的期限以及該原則可能對該內容產生的影響。</span><span class="sxs-lookup"><span data-stu-id="55f06-226">So before you assign a retention policy for the first time, and especially when that policy deletes items, first consider the age of the existing content and how the policy may impact that content.</span></span> <span data-ttu-id="55f06-227">您也可以在指派新原則前先與使用者溝通，讓他們有足夠的時間可評估可能的影響。</span><span class="sxs-lookup"><span data-stu-id="55f06-227">You might also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact.</span></span>

### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="55f06-228">套用到整個組織的原則</span><span class="sxs-lookup"><span data-stu-id="55f06-228">A policy that applies to entire locations</span></span>

<span data-ttu-id="55f06-229">當您選擇位置時，除了商務用 Skype，預設設定是當位置的狀態為**開啟**時的**全部**。</span><span class="sxs-lookup"><span data-stu-id="55f06-229">When you choose locations, with the exception of Skype for Business, the default setting is **All** when the status of the location is **On**.</span></span>
  
<span data-ttu-id="55f06-230">當保留原則套用於整個位置的任何組合時，原則可以包含的收件者、網站、帳戶、組等的數量沒有限制。</span><span class="sxs-lookup"><span data-stu-id="55f06-230">When a retention policy applies to any combination of entire locations, there is no limit to the number of recipients, sites, accounts, groups etc that the policy can include.</span></span> 

<span data-ttu-id="55f06-231">例如，如果原則包含所有 Exchange 電子郵件和所有 SharePoint 網站，無論有多少個網站和收件者都會全部包含。</span><span class="sxs-lookup"><span data-stu-id="55f06-231">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and recipients will be included, no matter how many.</span></span> <span data-ttu-id="55f06-232">而對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承原則。</span><span class="sxs-lookup"><span data-stu-id="55f06-232">And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="55f06-233">具有特定包含或排除的原則</span><span class="sxs-lookup"><span data-stu-id="55f06-233">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="55f06-234">您也可以將保留原則套用至特定使用者、特定 Microsoft 365 群組或特定網站。</span><span class="sxs-lookup"><span data-stu-id="55f06-234">You can also apply a retention policy to specific users, specific Microsoft 365 groups, or specific sites.</span></span> <span data-ttu-id="55f06-235">若要這麼做，請確保該位置的 **[狀態]** 為\*\* [開啟]\*\*，然後使用連結來包含或排除特定使用者、Microsoft 365 群組或網站。</span><span class="sxs-lookup"><span data-stu-id="55f06-235">To do so, make sure the **Status** of that location is **On**, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span> 
  
<span data-ttu-id="55f06-236">不過，使用此設定時，如果您的保留原則包含或排除超過 1,000 個特定物件，則會有一些限制：</span><span class="sxs-lookup"><span data-stu-id="55f06-236">However, using this configuration, there are some limits when your retention policy includes or excludes over 1,000 specific objects:</span></span>
  
- <span data-ttu-id="55f06-237">保留原則的數目上限：</span><span class="sxs-lookup"><span data-stu-id="55f06-237">Maximum numbers for the retention policy:</span></span>
    - <span data-ttu-id="55f06-238">1000 個信箱</span><span class="sxs-lookup"><span data-stu-id="55f06-238">1,000 mailboxes</span></span>
    - <span data-ttu-id="55f06-239">1,000 個 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="55f06-239">1,000 Microsoft 365 groups</span></span>
    - <span data-ttu-id="55f06-240">1000 個 Teams 私人聊天使用者</span><span class="sxs-lookup"><span data-stu-id="55f06-240">1,000 users for Teams private chats</span></span>
    - <span data-ttu-id="55f06-241">100 個網站 (OneDrive 或 SharePoint)</span><span class="sxs-lookup"><span data-stu-id="55f06-241">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="55f06-242">針對一個租用戶支援的原則數目上限：10,000 個。</span><span class="sxs-lookup"><span data-stu-id="55f06-242">There is a maximum number of policies that are supported for a tenant: 10,000.</span></span> <span data-ttu-id="55f06-243">這些項目包括保留原則、保留標籤原則，以及自動套用保留原則。</span><span class="sxs-lookup"><span data-stu-id="55f06-243">These items include retention policies, retention label policies, and auto-apply retention policies.</span></span>

<span data-ttu-id="55f06-244">如果您的保留原則可能受限於這些限制，請選擇適用於整個位置的設定選項。</span><span class="sxs-lookup"><span data-stu-id="55f06-244">If your retention policies are likely to be subject to these limitations, choose the configuration options that apply to entire locations.</span></span>

> [!WARNING]
> <span data-ttu-id="55f06-245">如果您設定 [包含] 然後移除最後一個，則設定會還原為該位置的 **[全部]**。</span><span class="sxs-lookup"><span data-stu-id="55f06-245">If you configure includes and then remove the last one, the configuration reverts to **All** for the location.</span></span>  <span data-ttu-id="55f06-246">儲存原則前，請確定這是您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="55f06-246">Make sure this is the configuration that you intend before you save the policy.</span></span>
> 
> <span data-ttu-id="55f06-247">例如，如果您指定一個 SharePoint 網站要包含在設定為刪除資料的保留原則中，然後移除單一網站，則預設所有 SharePoint 網站都會遵守永久刪除資料的保留原則。</span><span class="sxs-lookup"><span data-stu-id="55f06-247">For example, if you specify one SharePoint site to include in your retention policy that's configured to delete data, and then remove the single site, by default all SharePoint sites will then be subject to the retention policy that permanently deletes data.</span></span> <span data-ttu-id="55f06-248">Exchange 收件者、OneDrive 帳戶、Teams 聊天使用者等都適用。</span><span class="sxs-lookup"><span data-stu-id="55f06-248">The same applies to includes for Exchange recipients, OneDrive accounts, Teams chat users etc.</span></span>
> 
> <span data-ttu-id="55f06-249">在這種情況下，如果您不想讓該位置的 **[所有]** 設定遵守保留原則，可以將位置切換為 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="55f06-249">In this scenario, toggle the location off if you don't want the **All** setting for the location to be subject to the retention policy.</span></span> <span data-ttu-id="55f06-250">或者，指定 [排除] 以免於使用原則。</span><span class="sxs-lookup"><span data-stu-id="55f06-250">Alternatively, specify excludes to be exempt from the policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="55f06-251">更新保留原則</span><span class="sxs-lookup"><span data-stu-id="55f06-251">Updating retention policies</span></span>

<span data-ttu-id="55f06-252">如果您編輯保留原則，且項目已受限於保留原則中的原始設定，則除了新識別的項目以外，還會將您的更新設定自動套用至這些項目。</span><span class="sxs-lookup"><span data-stu-id="55f06-252">If you edit a retention policy and items are already subject to the original settings in your retention policy, your updated settings will be automatically applied to these items in addition to items that are newly identified.</span></span>

<span data-ttu-id="55f06-253">此更新通常相當快，但可能需要數天的時間。</span><span class="sxs-lookup"><span data-stu-id="55f06-253">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="55f06-254">當您的 Microsoft 365 位置間的原則複寫完成時，您會在 Microsoft 365 合規性中心看到保留原則的狀態從**開啟 (處理中)** 變成**開啟 (成功)**。</span><span class="sxs-lookup"><span data-stu-id="55f06-254">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="lock-a-retention-policy-by-using-powershell"></a><span data-ttu-id="55f06-255">使用 PowerShell 鎖定保留原則</span><span class="sxs-lookup"><span data-stu-id="55f06-255">Lock a retention policy by using PowerShell</span></span>

<span data-ttu-id="55f06-256">如果您需要使用[保留鎖定](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)才能符合法規要求，您必須使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="55f06-256">You must use PowerShell if you need to use [Preservation Lock](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements) to comply with regulatory requirements.</span></span> <span data-ttu-id="55f06-257">因為系統管理員無法在套用保留鎖定之後停用或刪除保留原則，因此在 UI 中無法使用此功能來防範意外的設定。</span><span class="sxs-lookup"><span data-stu-id="55f06-257">Because administrators can't disable or delete a retention policy after a preservation lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="55f06-258">具有任何設定的所有保留原則都支持保留鎖定。</span><span class="sxs-lookup"><span data-stu-id="55f06-258">All retention policies with any configuration support Preservation Lock.</span></span> <span data-ttu-id="55f06-259">不過，當您使用下列的 PowerShell 命令時，您會發現 **工作量** 參數永遠顯示 **Exchange、SharePoint、OneDriveForBusines、Skype、ModernGroup**，而不是反映原則中設定的實際工作量。</span><span class="sxs-lookup"><span data-stu-id="55f06-259">However, when you use the PowerShell commands that follow, you'll notice that the **Workload** parameter always displays **Exchange, SharePoint, OneDriveForBusines, Skype, ModernGroup** rather than reflect the actual workloads configured in the policy.</span></span> <span data-ttu-id="55f06-260">這只是顯示問題。</span><span class="sxs-lookup"><span data-stu-id="55f06-260">This is a display issue only.</span></span>

1. <span data-ttu-id="55f06-261">[連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="55f06-261">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="55f06-262">執行 [Get-RetentionCompliancePolicy](https://powershell/module/exchange/get-retentioncompliancepolicy) 列出您的保留原則清單，並尋找您想要鎖定的原則名稱。</span><span class="sxs-lookup"><span data-stu-id="55f06-262">List your retention policies and find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](https://powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="55f06-263">例如：</span><span class="sxs-lookup"><span data-stu-id="55f06-263">For example:</span></span>
    
   ![PowerShell 中保留原則的清單](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. <span data-ttu-id="55f06-265">若要將保留鎖定置於保留原則上，請以保留原則名稱執行 [Set-RetentionCompliancePolicy]( ) cmdlet，並將 *RestrictiveRetention* 參數設為 true：</span><span class="sxs-lookup"><span data-stu-id="55f06-265">To place a Preservation Lock on a retention policy, run the [Set-RetentionCompliancePolicy]( ) cmdlet with the name of the retention policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="55f06-266">例如：</span><span class="sxs-lookup"><span data-stu-id="55f06-266">For example:</span></span>
    
    ![PowerShell 中的 RestrictiveRetention 參數](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="55f06-268">當系統提示時，請閱讀並輸入 **Y** 來認可此設定隨附的限制：</span><span class="sxs-lookup"><span data-stu-id="55f06-268">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y**:</span></span>
    
   ![確認您在 PowerShell 想要鎖定保留原則的提示。](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="55f06-270">保留鎖定現在放置於保留原則上。</span><span class="sxs-lookup"><span data-stu-id="55f06-270">A Preservation Lock is now placed on the retention policy.</span></span> <span data-ttu-id="55f06-271">若要確認，請再次執行 `Get-RetentionCompliancePolicy`，但指定保留原則名稱並顯示原則參數：</span><span class="sxs-lookup"><span data-stu-id="55f06-271">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the retention policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="55f06-272">您應該會看到 **RestrictiveRetention** 設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="55f06-272">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="55f06-273">例如：</span><span class="sxs-lookup"><span data-stu-id="55f06-273">For example:</span></span>

![PowerShell 中顯示所有參數的鎖定原則](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

