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
description: 使用保留原則可以有效地控制使用者透過電子郵件、文件和交談生成的內容。 保留想要的內容，清除不想要的內容。
ms.openlocfilehash: 9e7ab359297ef1402fa64bc754591a4be3140af0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269501"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="4092e-104">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="4092e-104">Create and configure retention policies</span></span>

><span data-ttu-id="4092e-105">*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="4092e-105">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="4092e-106">使用保留原則，主動決定是否要保留內容、刪除內容，或保留然後刪除內容，以管理貴組織的資料。</span><span class="sxs-lookup"><span data-stu-id="4092e-106">Use a retention policy to manage the data for your organization by deciding proactively whether to retain content, delete content, or retain and then delete the content.</span></span>

<span data-ttu-id="4092e-107">保留原則可讓您在容器層級指派相同的保留設定，以自動由該容器中的內容繼承，進而有效率地執行此工作。</span><span class="sxs-lookup"><span data-stu-id="4092e-107">A retention policy lets you do this very efficiently by assigning the same retention settings at the container level to be automatically inherited by content in that container.</span></span> <span data-ttu-id="4092e-108">例如，SharePoint 網站的所有專案、使用者 Exchange 信箱中的所有電子郵件訊息、搭配 Microsoft Teams 所使用的團隊所有頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="4092e-108">For example, all items in SharePoint sites, all email messages in users' Exchange mailboxes, all channel messages for teams that are used with Microsoft Teams.</span></span> <span data-ttu-id="4092e-109">如果您不確定要使用容器層級的保留原則或專案層級的保留標籤，請參閱 [保留原則及保留標籤](retention.md#retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="4092e-109">If you're not sure whether to use a retention policy at the container level or a retention label at the item level, see [Retention policies and retention labels](retention.md#retention-policies-and-retention-labels).</span></span>

<span data-ttu-id="4092e-110">如需有關保留原則及其在 Microsoft 365 中運作方式的詳細資訊，可參閱 [了解保留原則及保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="4092e-110">For more information about retention policies and how retention works in Microsoft 365, see [Learn about retention policies and retention labels](retention.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4092e-111">此頁面上的資訊適用於合規性系統管理員。</span><span class="sxs-lookup"><span data-stu-id="4092e-111">The information on this page is for compliance administrators.</span></span> <span data-ttu-id="4092e-112">如果您不是系統管理員，且想要了解你所使用之應用程式的保留原則設定方式，請與您的技術支援中心、IT 部門或系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="4092e-112">If you are not an administrator and want to understand how retention policies have been configured for the apps that you use, contact your help desk, IT department, or administrator.</span></span> <span data-ttu-id="4092e-113">若您在 Teams 聊天和頻道訊息中看見有關保留原則的訊息，建議您檢閱 [關於保留原則的 Teams 訊息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="4092e-113">If you're seeing messages about retention policies in Teams chats and channel messages, you might find it helpful to review [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4092e-114">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="4092e-114">Before you begin</span></span>

<span data-ttu-id="4092e-115">您組織中的全域系統管理員擁有建立及管理保留標籤及其原則的完整權限。</span><span class="sxs-lookup"><span data-stu-id="4092e-115">The global admin for your organization has full permissions to create and edit retention policies.</span></span> <span data-ttu-id="4092e-116">若您未以全域系統管理員的身分登入，請參閱 [建立和管理保留標籤所需權限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="4092e-116">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="4092e-117">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="4092e-117">Create and configure a retention policy</span></span>

<span data-ttu-id="4092e-118">雖然保留原則可以支援在保留原則中識別為「位置」的多個服務，但您無法建立包含所有受支援位置的單一保留原則：</span><span class="sxs-lookup"><span data-stu-id="4092e-118">Although a retention policy can support multiple services that are identified as "locations" in the retention policy, you can't create a single retention policy that includes all the supported locations:</span></span>

- <span data-ttu-id="4092e-119">Exchange 電子郵件</span><span class="sxs-lookup"><span data-stu-id="4092e-119">Exchange email</span></span>
- <span data-ttu-id="4092e-120">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="4092e-120">SharePoint site</span></span>
- <span data-ttu-id="4092e-121">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="4092e-121">OneDrive accounts</span></span>
- <span data-ttu-id="4092e-122">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="4092e-122">Microsoft 365 groups</span></span>
- <span data-ttu-id="4092e-123">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="4092e-123">Skype for Business</span></span>
- <span data-ttu-id="4092e-124">Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="4092e-124">Exchange public folders</span></span>
- <span data-ttu-id="4092e-125">Teams 通道訊息</span><span class="sxs-lookup"><span data-stu-id="4092e-125">Teams channel messages</span></span>
- <span data-ttu-id="4092e-126">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="4092e-126">Teams chats</span></span>
- <span data-ttu-id="4092e-127">Yammer 社群訊息</span><span class="sxs-lookup"><span data-stu-id="4092e-127">Yammer community messages</span></span>
- <span data-ttu-id="4092e-128">Yammer 私人訊息</span><span class="sxs-lookup"><span data-stu-id="4092e-128">Yammer private messages</span></span>

<span data-ttu-id="4092e-129">建立保留原則時若選取 Teams 或 Yammer 位置，系統會自動排除另一個位置。</span><span class="sxs-lookup"><span data-stu-id="4092e-129">If you select the Teams or Yammer locations when you create a retention policy, the other locations are automatically excluded.</span></span> <span data-ttu-id="4092e-130">這表示，應遵循的指示將取決於您是否要包含 Teams 或 Yammer 位置而定：</span><span class="sxs-lookup"><span data-stu-id="4092e-130">This means that the instructions to follow depend on whether you need to include the Teams or Yammer locations:</span></span>

- [<span data-ttu-id="4092e-131">Teams 位置保留原則的指示</span><span class="sxs-lookup"><span data-stu-id="4092e-131">Instructions for a retention policy for Teams locations</span></span>](#retention-policy-for-teams-locations)
- [<span data-ttu-id="4092e-132">Yammer 位置保留原則的指示</span><span class="sxs-lookup"><span data-stu-id="4092e-132">Instructions for a retention policy for Yammer locations</span></span>](#retention-policy-for-yammer-locations)
- [<span data-ttu-id="4092e-133">Teams 和 Yammer 以外位置保留原則的指示</span><span class="sxs-lookup"><span data-stu-id="4092e-133">Instructions for a retention policy for locations other than Teams and Yammer</span></span>](#retention-policy-for-locations-other-than-teams-and-yammer)

<span data-ttu-id="4092e-134">當您有多個保留原則，以及當您同時使用保留標籤時，請參閱 [保留原則優先或以什麼為優先？](retention.md#the-principles-of-retention-or-what-takes-precedence) 以瞭解在相同的內容上同時有多個保留設定套用時，會有什麼樣的結果。</span><span class="sxs-lookup"><span data-stu-id="4092e-134">When you have more than one retention policy, and when you also use retention labels, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) to understand the outcome when multiple retention settings apply to the same content.</span></span>

### <a name="retention-policy-for-teams-locations"></a><span data-ttu-id="4092e-135">Teams 位置的保留原則</span><span class="sxs-lookup"><span data-stu-id="4092e-135">Retention policy for Teams locations</span></span>

1. <span data-ttu-id="4092e-136">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。</span><span class="sxs-lookup"><span data-stu-id="4092e-136">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="4092e-137">選取 **[新保留原則]** 以啟動 [建立保留原則] 精靈，並命名新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="4092e-137">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="4092e-138">對於 **[選擇要套用原則的位置]** 頁面，請為 Teams 選取一個或兩個位置：**Teams 頻道訊息** 和 **Teams 聊天**。</span><span class="sxs-lookup"><span data-stu-id="4092e-138">For the **Choose locations to apply the policy** page, select one or both of the locations for Teams: **Teams channel message** and **Teams chats**.</span></span>

   <span data-ttu-id="4092e-139">針對 **Teams 頻道訊息**，會包含來自標準頻道的訊息，但不會包含 [私人頻道](/microsoftteams/private-channels)。</span><span class="sxs-lookup"><span data-stu-id="4092e-139">For **Teams channel messages**, message from standard channels but not [private channels](/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="4092e-140">目前，保留原則尚未支援 [私人頻道]。</span><span class="sxs-lookup"><span data-stu-id="4092e-140">Currently, private channels aren't supported by retention policies.</span></span>

   <span data-ttu-id="4092e-141">根據預設，[所有小組和所有使用者都處於選中狀態](#a-policy-that-applies-to-entire-locations)，但您可以透過選取 [**[選擇]** 和 **[排除]** 選項](#a-policy-with-specific-inclusions-or-exclusions)對其進行優化。</span><span class="sxs-lookup"><span data-stu-id="4092e-141">By default, [all teams and all users are selected](#a-policy-that-applies-to-entire-locations), but you can refine this by selecting the [**Choose** and **Exclude** options](#a-policy-with-specific-inclusions-or-exclusions).</span></span> <span data-ttu-id="4092e-142">不過，在變更預設值之前，請注意保留原則的下列結果，該保留原則在已針對包含或排除項進行設定時，會刪除郵件：</span><span class="sxs-lookup"><span data-stu-id="4092e-142">However, before you change the default, be aware of the following consequences for a retention policy that deletes messages when it's configured for includes or excludes:</span></span>
    
    - <span data-ttu-id="4092e-143">對於群組聊天，因為訊息複本會儲存於聊天中包含的每位使用者的信箱中，所以系統會繼續從未指派此原則的使用者於「電子文件探索」結果中退回郵件複本。</span><span class="sxs-lookup"><span data-stu-id="4092e-143">For group chats, because a copy of messages are saved in each user's mailbox who are included in the chat, copies of messages will continue to be returned in eDiscovery results from users who weren't assigned the policy.</span></span>
    - <span data-ttu-id="4092e-144">對於未指派此原則的使用者，已刪除的郵件將會回到其 Teams 搜尋結果中，但因為從指派給使用者之原則中已永久刪除，所以不會顯示郵件內容。</span><span class="sxs-lookup"><span data-stu-id="4092e-144">For users who weren't assigned the policy, deleted messages will be returned in their Teams search results but won't display the contents of the message as a result of the permanent deletion from the policy assigned to users.</span></span>

4. <span data-ttu-id="4092e-145">在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。</span><span class="sxs-lookup"><span data-stu-id="4092e-145">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

   <span data-ttu-id="4092e-146">您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。</span><span class="sxs-lookup"><span data-stu-id="4092e-146">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="4092e-147">如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="4092e-147">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="4092e-148">完成精靈以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="4092e-148">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="4092e-149">如需何時使用 Teams 保留原則的高層級資訊，請參閱在 Teams 文件中的 [Microsoft Teams 的保留原則](/microsoftteams/retention-policies)。</span><span class="sxs-lookup"><span data-stu-id="4092e-149">For high-level information when to use retention policies for Teams, see [Retention policies in Microsoft Teams](/microsoftteams/retention-policies) from the Teams documentation.</span></span>

<span data-ttu-id="4092e-150">如需 Teams 保留運作方式的技術詳細資料，包括哪些郵件元素支援保留和時間資訊及逐步範例，請參閱[了解 Microsoft Teams 的保留](retention-policies-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4092e-150">For technical details about how retention works for Teams, including what elements of messages are supported for retention and timing information with example walkthroughs, see [Learn about retention for Microsoft Teams](retention-policies-teams.md).</span></span>

#### <a name="known-configuration-issues"></a><span data-ttu-id="4092e-151">已知的設定問題</span><span class="sxs-lookup"><span data-stu-id="4092e-151">Known configuration issues</span></span>

- <span data-ttu-id="4092e-152">雖然您可以選取選項，在上次修改項目時開始保留期間，但是一律會使用 **項目建立時間** 的值。</span><span class="sxs-lookup"><span data-stu-id="4092e-152">Although you can select the option to start the retention period when items were last modified, the value of **When items were created** is always used.</span></span> <span data-ttu-id="4092e-153">對於已編輯的訊息，原始訊息的一份副本會與原始時間戳記一起儲存，以識別建立此預先編輯訊息的時間，且預先編輯後的訊息具有較新的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="4092e-153">For messages that are edited, a copy of the original message is saved with its original timestamp to identify when this pre-edited message was created, and the post-edited message has a newer timestamp.</span></span>

- <span data-ttu-id="4092e-154">當您針對 [Teams 頻道訊息] 位置選取 [選擇小組] 時，您可能會看到也不是小組的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="4092e-154">When you select **Choose teams** for the **Teams channel messages** location, you might see Microsoft 365 groups that aren't also teams.</span></span> <span data-ttu-id="4092e-155">請勿選取這些群組。</span><span class="sxs-lookup"><span data-stu-id="4092e-155">Don't select these groups.</span></span>

- <span data-ttu-id="4092e-156">當您選取 **[選擇 Teams 聊天的使用者]** 位置時，您可能會看到來賓和非信箱使用者。</span><span class="sxs-lookup"><span data-stu-id="4092e-156">When you select **Choose users for the Teams chats** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="4092e-157">保留原則並非為這些使用者設計，因此請不要選取他們。</span><span class="sxs-lookup"><span data-stu-id="4092e-157">Retention policies aren't designed for these users, so don't select them.</span></span>


#### <a name="additional-retention-policy-needed-to-support-teams"></a><span data-ttu-id="4092e-158">支援 Teams 所需的其他保留原則</span><span class="sxs-lookup"><span data-stu-id="4092e-158">Additional retention policy needed to support Teams</span></span>

<span data-ttu-id="4092e-159">Teams 不僅是提供聊天和頻道訊息功能，還有更多功能。</span><span class="sxs-lookup"><span data-stu-id="4092e-159">Teams is more than just chats and channel messages.</span></span> <span data-ttu-id="4092e-160">如果您有透過 Microsoft 365 群組 (之前稱為 Office 365 群組) 建立的小組，您應該額外使用 [Microsoft 365 群組 **]** 位置來設定包含該 Microsoft 365 群組的保留原則。</span><span class="sxs-lookup"><span data-stu-id="4092e-160">If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Microsoft 365 Groups** location.</span></span> <span data-ttu-id="4092e-161">此保留原則適用於群組的信箱、網站和檔案中的內容。</span><span class="sxs-lookup"><span data-stu-id="4092e-161">This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="4092e-162">如果您有未與 Microsoft 365 群組連線的 Teams 位置，您需要有可以包含 **SharePoint 網站** 或 **OneDrive 帳戶** 位置的保留原則，用以保留及刪除 Teams 中的檔案：</span><span class="sxs-lookup"><span data-stu-id="4092e-162">If you have team sites that aren't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="4092e-163">在聊天中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="4092e-163">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span>

- <span data-ttu-id="4092e-164">上傳至頻道的檔案則會儲存在團隊的 SharePoint 網站中。</span><span class="sxs-lookup"><span data-stu-id="4092e-164">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="4092e-165">當團隊未連線至 Microsoft 365 時，您可以將保留原則套用到僅特定團隊的檔案，方法是選取團隊的 SharePoint 網站，以及團隊中使用者的 OneDrive 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4092e-165">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="4092e-166">套用至 Microsoft 365、SharePoint 網站或 OneDrive 帳戶的保留原則有可能會刪除 Teams 聊天中參考的檔案，或在頻道訊息刪除前就將其刪除。</span><span class="sxs-lookup"><span data-stu-id="4092e-166">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="4092e-167">在這種情況下，檔案仍會顯示在 Teams 訊息中，但是當使用者選取檔案時，會收到「找不到檔案」錯誤。</span><span class="sxs-lookup"><span data-stu-id="4092e-167">In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="4092e-168">此行為並非保留原則特定，因此也可能在使用者從 SharePoint 或 OneDrive 中手動刪除檔案時發生。</span><span class="sxs-lookup"><span data-stu-id="4092e-168">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-yammer-locations"></a><span data-ttu-id="4092e-169">Yammer 位置的保留原則</span><span class="sxs-lookup"><span data-stu-id="4092e-169">Retention policy for Yammer locations</span></span>

> [!NOTE]
> <span data-ttu-id="4092e-170">Yammer 的保留原則已推出預覽版。</span><span class="sxs-lookup"><span data-stu-id="4092e-170">Retention policies for Yammer are rolling out in preview.</span></span> <span data-ttu-id="4092e-171">如果您還沒有看到 Yammer 的新位置，請於幾周後再試一次。</span><span class="sxs-lookup"><span data-stu-id="4092e-171">If you don't yet see the new locations for Yammer, try again in a few weeks.</span></span>
>
> <span data-ttu-id="4092e-172">若要使用此功能，您的 Yammer 網路必須處於[原生模式](/yammer/configure-your-yammer-network/overview-native-mode)，而非混合模式。</span><span class="sxs-lookup"><span data-stu-id="4092e-172">To use this feature, your Yammer network must be [Native Mode](/yammer/configure-your-yammer-network/overview-native-mode), not Hybrid Mode.</span></span>

1. <span data-ttu-id="4092e-173">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。</span><span class="sxs-lookup"><span data-stu-id="4092e-173">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="4092e-174">選取 **[新增保留原則]** 以建立新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="4092e-174">Select **New retention policy** to create a new retention policy.</span></span>

3. <span data-ttu-id="4092e-175">在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。</span><span class="sxs-lookup"><span data-stu-id="4092e-175">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span> 
    
    <span data-ttu-id="4092e-176">您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。</span><span class="sxs-lookup"><span data-stu-id="4092e-176">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="4092e-177">如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="4092e-177">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>
    
    <span data-ttu-id="4092e-178">請勿選取 [使用進階保留設定 **]**，因為 Yammer 位置不支援此選項。</span><span class="sxs-lookup"><span data-stu-id="4092e-178">Do not select **Use advanced retention settings** because this option isn't supported for Yammer locations.</span></span> 

4. <span data-ttu-id="4092e-179">在 [選擇位置 **]** 頁面上，選取 [讓我選擇特定位置 **]**。</span><span class="sxs-lookup"><span data-stu-id="4092e-179">For the **Choose locations** page, select **Let me choose specific locations**.</span></span> <span data-ttu-id="4092e-180">然後將 Yammer 的一個或兩個位置切換為開啟：**Yammer 社群訊息** 和 **Yammer 私人訊息**。</span><span class="sxs-lookup"><span data-stu-id="4092e-180">Then toggle on one or both of the locations for Yammer: **Yammer community message** and **Yammer private messages**.</span></span>
    
    <span data-ttu-id="4092e-181">預設會選取所有社群和使用者，但是您可以指定要包含或排除的社群和使用者，以縮小範圍。</span><span class="sxs-lookup"><span data-stu-id="4092e-181">By default, all communities and users are selected, but you can refine this by specifying communities and users to be included or excluded.</span></span>
    
    <span data-ttu-id="4092e-182">針對 Yammer 私人訊息：</span><span class="sxs-lookup"><span data-stu-id="4092e-182">For Yammer private messages:</span></span> 
    - <span data-ttu-id="4092e-183">如果您保留預設值 **全部**，將不會包含 Azure B2B 來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="4092e-183">If you leave the default at **All**, Azure B2B guest users are not included.</span></span> 
    - <span data-ttu-id="4092e-184">如果您選取 [選擇使用者 **]**，就可以將保留原則套用至外部使用者 (如果您知道其帳戶)。</span><span class="sxs-lookup"><span data-stu-id="4092e-184">If you select **Choose user**, you can apply a retention policy to external users if you know their account.</span></span>

5. <span data-ttu-id="4092e-185">完成精靈以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="4092e-185">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="4092e-186">如需保留原則對 Yammer 運作方式的詳細資訊，請參閱[了解 Yammer 的保留](retention-policies-yammer.md)。</span><span class="sxs-lookup"><span data-stu-id="4092e-186">For more information about how retention policies work for Yammer, see [Learn about retention for Yammer](retention-policies-yammer.md).</span></span>

#### <a name="additional-retention-policies-needed-to-support-yammer"></a><span data-ttu-id="4092e-187">支援 Yammer 所需的額外保留原則</span><span class="sxs-lookup"><span data-stu-id="4092e-187">Additional retention policies needed to support Yammer</span></span>

<span data-ttu-id="4092e-188">Yammer 不僅可提供社群訊息和私人訊息功能，還有更多功能。</span><span class="sxs-lookup"><span data-stu-id="4092e-188">Yammer is more than just community messages and private messages.</span></span> <span data-ttu-id="4092e-189">若要保留及刪除您 Yammer 網路的電子郵件訊息，請使用 [Microsoft 365 群組 **]** 位置來設定包含用於 Yammer 的任何 Microsoft 365 群組的額外保留原則。</span><span class="sxs-lookup"><span data-stu-id="4092e-189">To retain and delete email messages for your Yammer network, configure an additional retention policy that includes any Microsoft 365 groups that are used for Yammer, by using the **Microsoft 365 Groups** location.</span></span> 

<span data-ttu-id="4092e-190">若要保留及刪除 Yammer 中儲存的檔案，您需要包含 **SharePoint 網站** 或 **OneDrive 帳戶** 位置的保留原則：</span><span class="sxs-lookup"><span data-stu-id="4092e-190">To retain and delete files that are stored in Yammer, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations:</span></span>

- <span data-ttu-id="4092e-191">在私人訊息中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="4092e-191">Files that are shared in private messages are stored in the OneDrive account of the user who shared the file.</span></span> 

- <span data-ttu-id="4092e-192">上傳到社群的檔案會儲存在 Yammer 社群的 SharePoint 網站中。</span><span class="sxs-lookup"><span data-stu-id="4092e-192">Files that are uploaded to communities are stored in the SharePoint site for the Yammer community.</span></span>

<span data-ttu-id="4092e-193">套用至 SharePoint 網站或 OneDrive 帳戶的保留原則可能會在刪除 Yammer 訊息之前便刪除這些訊息中參考的檔案。</span><span class="sxs-lookup"><span data-stu-id="4092e-193">It's possible that a retention policy that's applied to SharePoint sites or OneDrive accounts could delete a file that's referenced in a Yammer message before those messages get deleted.</span></span> <span data-ttu-id="4092e-194">在這種情況下，檔案仍會顯示在 Yammer 訊息中，但是當使用者選取檔案時，會遇到「找不到檔案」錯誤。</span><span class="sxs-lookup"><span data-stu-id="4092e-194">In this scenario, the file still displays in the Yammer message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="4092e-195">此行為並非保留原則特定，因此也可能在使用者從 SharePoint 或 OneDrive 中手動刪除檔案時發生。</span><span class="sxs-lookup"><span data-stu-id="4092e-195">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a><span data-ttu-id="4092e-196">Teams 和 Yammer 以外位置的保留原則</span><span class="sxs-lookup"><span data-stu-id="4092e-196">Retention policy for locations other than Teams and Yammer</span></span>

<span data-ttu-id="4092e-197">針對適用於下列任何服務的保留原則，使用下列指示：</span><span class="sxs-lookup"><span data-stu-id="4092e-197">Use the following instructions for retention policies that apply to any of these services:</span></span>

- <span data-ttu-id="4092e-198">Exchange：電子郵件和公用資料夾</span><span class="sxs-lookup"><span data-stu-id="4092e-198">Exchange: Email and public folders</span></span>
- <span data-ttu-id="4092e-199">SharePoint：網站</span><span class="sxs-lookup"><span data-stu-id="4092e-199">SharePoint: Sites</span></span>
- <span data-ttu-id="4092e-200">OneDrive：帳戶</span><span class="sxs-lookup"><span data-stu-id="4092e-200">OneDrive: Accounts</span></span>
- <span data-ttu-id="4092e-201">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="4092e-201">Microsoft 365 groups</span></span>
- <span data-ttu-id="4092e-202">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="4092e-202">Skype for Business</span></span>

1. <span data-ttu-id="4092e-203">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。</span><span class="sxs-lookup"><span data-stu-id="4092e-203">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="4092e-204">選取 **[新保留原則]** 以啟動 [建立保留原則] 精靈，並命名新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="4092e-204">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="4092e-205">對於 **[選擇位置]** 頁面，開啟或關閉除 Teams 位置以外的任何位置。</span><span class="sxs-lookup"><span data-stu-id="4092e-205">For the **Choose locations** page, toggle on or off any of the locations except the locations for Teams.</span></span> <span data-ttu-id="4092e-206">您可以將每個位置保留為預設值，以便[將原則套用於整個位置](#a-policy-that-applies-to-entire-locations)，或[指定包含和排除](#a-policy-with-specific-inclusions-or-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="4092e-206">For each location, you can leave it at the default to [apply the policy to the entire location](#a-policy-that-applies-to-entire-locations), or [specify includes and excludes](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

    <span data-ttu-id="4092e-207">位置專用資訊：</span><span class="sxs-lookup"><span data-stu-id="4092e-207">Information specific to locations:</span></span>
    - [<span data-ttu-id="4092e-208">Exchange 電子郵件和 Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="4092e-208">Exchange email and Exchange public folders</span></span>](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [<span data-ttu-id="4092e-209">SharePoint 網站和 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="4092e-209">SharePoint sites and OneDrive accounts</span></span>](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [<span data-ttu-id="4092e-210">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="4092e-210">Microsoft 365 Groups</span></span>](#configuration-information-for-microsoft-365-groups)
    - [<span data-ttu-id="4092e-211">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="4092e-211">Skype for Business</span></span>](#configuration-information-for-skype-for-business)

4. <span data-ttu-id="4092e-212">在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。</span><span class="sxs-lookup"><span data-stu-id="4092e-212">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

    <span data-ttu-id="4092e-213">您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。</span><span class="sxs-lookup"><span data-stu-id="4092e-213">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="4092e-214">如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="4092e-214">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="4092e-215">完成精靈以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="4092e-215">Complete the wizard to save your settings.</span></span>

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a><span data-ttu-id="4092e-216">Exchange 電子郵件和 Exchange 公用資料夾的設定資訊</span><span class="sxs-lookup"><span data-stu-id="4092e-216">Configuration information for Exchange email and Exchange public folders</span></span>

<span data-ttu-id="4092e-217">**Exchange 電子郵件** 位置支援使用者的電子郵件、行事曆和其他信箱專案的保留，方法是套用信箱層級的保留設定。</span><span class="sxs-lookup"><span data-stu-id="4092e-217">The **Exchange email** location supports retention for users' email, calendar, and other mailbox items, by applying retention settings at the level of a mailbox.</span></span>

<span data-ttu-id="4092e-218">如需有關在設定 Exchange 保留設定時包含和排除哪些項目的詳細資訊，請參閱 [保留與刪除所包含的內容](retention-policies-exchange.md#whats-included-for-retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="4092e-218">For detailed information about which items are included and excluded when you configure retention settings for Exchange, see [What's included for retention and deletion](retention-policies-exchange.md#whats-included-for-retention-and-deletion)</span></span>

<span data-ttu-id="4092e-219">請注意，即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件** 位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="4092e-219">Note that even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="4092e-220">若要保留這些信箱中的內容，請選取 [Microsoft 365 群組 **]** 位置。</span><span class="sxs-lookup"><span data-stu-id="4092e-220">To retain content in these mailboxes, select the **Microsoft 365 Groups** location.</span></span>

<span data-ttu-id="4092e-221">**Exchange 公用資料夾** 位置會將保留設定套用至所有的公用資料夾，且無法在資料夾或信箱層級套用。</span><span class="sxs-lookup"><span data-stu-id="4092e-221">The **Exchange public folders** location applies retention settings to all public folders and can't be applied at the folder or mailbox level.</span></span>

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a><span data-ttu-id="4092e-222">SharePoint 網站和 OneDrive 帳戶的配置資訊</span><span class="sxs-lookup"><span data-stu-id="4092e-222">Configuration information for SharePoint sites and OneDrive accounts</span></span>

<span data-ttu-id="4092e-223">當您選擇 [SharePoint 網站 **]** 位置時，保留原則即可保留及刪除在 SharePoint 通訊網站中的文件、未由 Microsoft 365 群組連結的小組網站，以及傳統網站。</span><span class="sxs-lookup"><span data-stu-id="4092e-223">When you choose the **SharePoint sites** location, the retention policy can retain and delete documents in SharePoint communication sites, team sites that aren't connected by Microsoft 365 groups, and classic sites.</span></span> <span data-ttu-id="4092e-224">此選項不支援由 Microsoft 365 群組所連線的小組網站，而是會使用套用至群組信箱、網站和檔案中內容的 [Microsoft 365 群組 **]** 位置。</span><span class="sxs-lookup"><span data-stu-id="4092e-224">Team sites connected by Microsoft 365 groups aren't supported with this option and instead, use the **Microsoft 365 Groups** location that applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="4092e-225">雖然保留原則可套用到網站層級，但只有文件會套用保留設定。</span><span class="sxs-lookup"><span data-stu-id="4092e-225">Although the retention policy is applied at the site level, only documents have retention settings applied to them.</span></span> <span data-ttu-id="4092e-226">如需有關在設定 SharePoint 和 OneDrive 保留設定時所包含和排除之內容的詳細資訊，請參閱 [保留與刪除所包含的內容](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion)。</span><span class="sxs-lookup"><span data-stu-id="4092e-226">For detailed information about what's included and excluded when you configure retention settings for SharePoint and OneDrive, see [What's included for retention and deletion](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion).</span></span> 

<span data-ttu-id="4092e-227">當您為 SharePoint 網站或 OneDrive 帳戶指定您的位置時，您不需要存取網站的權限，而當你在 **[編輯位置]** 頁面上指定 URL 時也不會需要進行任何的驗證。</span><span class="sxs-lookup"><span data-stu-id="4092e-227">When you specify your locations for SharePoint sites or OneDrive accounts, you don't need permissions to access the sites and no validation is done at the time you specify the URL on the **Edit locations** page.</span></span> <span data-ttu-id="4092e-228">不過，您指定的 SharePoint 網站會在精靈結束時進行檢查，以確認其存在。</span><span class="sxs-lookup"><span data-stu-id="4092e-228">However, the SharePoint sites that you specify are checked that they exist at the end of the wizard.</span></span> <span data-ttu-id="4092e-229">如果此檢查失敗，您會看到一則訊息，指出您輸入的 URL 驗證失敗，且精靈不會建立保留原則，直到驗證檢查通過為止。</span><span class="sxs-lookup"><span data-stu-id="4092e-229">If this check fails, you see a message that validation failed for the URL you entered, and the wizard won't create the retention policy until the validation check passes.</span></span> <span data-ttu-id="4092e-230">如果您看到這則訊息，請返回精靈並變更 URL 或從保留原則將網站移除。</span><span class="sxs-lookup"><span data-stu-id="4092e-230">If you see this message, go back in the wizard to change the URL or remove the site from the retention policy.</span></span>

<span data-ttu-id="4092e-231">若要特別指定包含或排除某個 OneDrive 帳戶，URL 的格式要求如下：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="4092e-231">To specify individual OneDrive accounts to include or exclude, the URL has the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>

<span data-ttu-id="4092e-232">例如，針對 contoso 租用戶中使用者名稱為 "rsimone" 的使用者：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="4092e-232">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>

<span data-ttu-id="4092e-233">若要驗證租用戶的語法並識別使用者的 URL，請參閱[取得組織中所有使用者的 OneDrive URL 清單](/onedrive/list-onedrive-urls) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="4092e-233">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](/onedrive/list-onedrive-urls).</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="4092e-234">Microsoft 365 群組的設定資訊</span><span class="sxs-lookup"><span data-stu-id="4092e-234">Configuration information for Microsoft 365 Groups</span></span>

<span data-ttu-id="4092e-235">若要保留或刪除一個 Microsoft 365 群組 (之前稱為 Office 365 群組) 的內容，請使用 [Microsoft 365 群組 **]** 位置。</span><span class="sxs-lookup"><span data-stu-id="4092e-235">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), use the **Microsoft 365 Groups** location.</span></span> <span data-ttu-id="4092e-236">即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件** 位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="4092e-236">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="4092e-237">雖然 **Exchange 電子郵件** 位置一開始會允許您指定要包括或排除的群組信箱，但是當您嘗試儲存保留原則時，您會收到 "RemoteGroupMailbox" 不是 Exchange 位置之有效選項的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="4092e-237">Although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you'll see an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="4092e-238">根據預設，套用到 Microsoft 365 群組的保留原則包括群組信箱和 SharePoint 小組網站。</span><span class="sxs-lookup"><span data-stu-id="4092e-238">By default, a retention policy applied to a Microsoft 365 group includes the group mailbox and SharePoint teams site.</span></span> <span data-ttu-id="4092e-239">此位置涵蓋儲存在 SharePoint 小組網站中的檔案，但不涵蓋有自己的保留原則位置的小組聊天或小組頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="4092e-239">Files stored in the SharePoint teams site are covered with this location, but not Teams chats or Teams channel messages that have their own retention policy locations.</span></span>

<span data-ttu-id="4092e-240">若因為您希望保留原則只套用至 Microsoft 365 信箱，或只套用至已連結的 SharePoint 小組網站而要變更預設值，請使用 [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell Cmdlet 與具有下列其中一個值的 *應用程式* 參數：</span><span class="sxs-lookup"><span data-stu-id="4092e-240">To change the default because you want the retention policy to apply to either just the Microsoft 365 mailboxes, or just the connected SharePoint teams sites, use the [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell cmdlet with the *Applications* parameter with one of the following values:</span></span>

- <span data-ttu-id="4092e-241">`Group:Exchange` 只針對已連結到群組的 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="4092e-241">`Group:Exchange` for just Microsoft 365 mailboxes that are connected to the group.</span></span>
- <span data-ttu-id="4092e-242">`Group:SharePoint` 只針對已連結至群組的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="4092e-242">`Group:SharePoint` for just SharePoint sites that are connected to the group.</span></span>

<span data-ttu-id="4092e-243">若要回到所選 Microsoft 365 群組的信箱和 SharePoint 網站的預設值，請指定 `Group:Exchange,SharePoint`。</span><span class="sxs-lookup"><span data-stu-id="4092e-243">To return to the default value of both the mailbox and SharePoint site for the selected Microsoft 365 groups, specify `Group:Exchange,SharePoint`.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="4092e-244">商務用 Skype 的設定資訊</span><span class="sxs-lookup"><span data-stu-id="4092e-244">Configuration information for Skype for Business</span></span>

<span data-ttu-id="4092e-245">不同於 Exchange 電子郵件，您無法將 Skype 位置的狀態切換為開啟以自動包含所有使用者，但當您開啟該位置時，必須手動選擇您想要保留其交談的使用者：</span><span class="sxs-lookup"><span data-stu-id="4092e-245">Unlike Exchange email, you can't toggle the status of the Skype location on to automatically include all users, but when you turn on that location, you must then manually choose the users whose conversations you want to retain:</span></span>

![為保留原則選擇 Skype 位置](../media/skype-location-retention-policies.png)

<span data-ttu-id="4092e-247">當您選取 **[選擇使用者]** 時，您可以選取 **[選取所有]** 方塊，快速包含所有使用者。</span><span class="sxs-lookup"><span data-stu-id="4092e-247">When you select **Choose user**, you can quickly include all users by selecting the **Select all** box.</span></span> <span data-ttu-id="4092e-248">不過，請務必了解，會將每個使用者算成原則中的一個特定包含。</span><span class="sxs-lookup"><span data-stu-id="4092e-248">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="4092e-249">因此，如果透過選擇 **[全選]** 方塊拉包含 1000 位使用者，則與手動選取要包含的 1000 位使用者相同，這是 商務用 Skype 支持的最大值。</span><span class="sxs-lookup"><span data-stu-id="4092e-249">So if you include 1,000 users by selecting the **Select all** box, it's the same as if you manually selected 1,000 users to include, which is the maximum supported for Skype for Business.</span></span>

<span data-ttu-id="4092e-250">請注意 Outlook 中的 **[交談記錄]** 資料夾的功能與 Skype 封存毫無關聯。</span><span class="sxs-lookup"><span data-stu-id="4092e-250">Be aware that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving.</span></span> <span data-ttu-id="4092e-251">使用者可以關閉 **[交談記錄]**，但 Skype 封存的運作方式是，將 Skype 交談的複本儲存在使用者無法存取但 eDiscovery 可以使用的隱藏資料夾。</span><span class="sxs-lookup"><span data-stu-id="4092e-251">**Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>

## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="4092e-252">保留和刪除內容的設定</span><span class="sxs-lookup"><span data-stu-id="4092e-252">Settings for retaining and deleting content</span></span>

<span data-ttu-id="4092e-253">透過在保留原則中選擇用於保留和刪除內容的設定，您的保留原則會具有下列其中一個設定達一段指定的期間：</span><span class="sxs-lookup"><span data-stu-id="4092e-253">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="4092e-254">僅保留</span><span class="sxs-lookup"><span data-stu-id="4092e-254">Retain-only</span></span>

    <span data-ttu-id="4092e-255">在此設定中，請選擇 **[在特定期內保留項目]** 和 **在保留期結束時：不做任何處理**。</span><span class="sxs-lookup"><span data-stu-id="4092e-255">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Do nothing**.</span></span> <span data-ttu-id="4092e-256">或者，選取 **[永遠保留項目]**。</span><span class="sxs-lookup"><span data-stu-id="4092e-256">Or, select **Retain items forever**.</span></span>

- <span data-ttu-id="4092e-257">保留然後刪除</span><span class="sxs-lookup"><span data-stu-id="4092e-257">Retain and then delete</span></span>

    <span data-ttu-id="4092e-258">在此設定中，請選擇 **[在特定期內保留項目]** 和 **在保留期結束時：自動刪除項目**。</span><span class="sxs-lookup"><span data-stu-id="4092e-258">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Delete items automatically**.</span></span>

- <span data-ttu-id="4092e-259">僅刪除</span><span class="sxs-lookup"><span data-stu-id="4092e-259">Delete-only</span></span>

    <span data-ttu-id="4092e-260">在此設定中，選擇 **「只有項目達到特定存留期時才刪除它」**。</span><span class="sxs-lookup"><span data-stu-id="4092e-260">For this configuration, choose **Only delete items when they reach a certain age**.</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="4092e-261">將內容保留特定的一段時間</span><span class="sxs-lookup"><span data-stu-id="4092e-261">Retaining content for a specific period of time</span></span>

<span data-ttu-id="4092e-262">設定保留原則時，您會選擇保留項目，或將其保留特定數天、數月或數年。</span><span class="sxs-lookup"><span data-stu-id="4092e-262">When you configure a retention policy, you choose to retain items for a specific number of days, months, or years.</span></span> <span data-ttu-id="4092e-263">或者永遠保留項目。</span><span class="sxs-lookup"><span data-stu-id="4092e-263">Or alternatively, retain the items forever.</span></span>

<span data-ttu-id="4092e-264">設定保留原則時，您可以選擇無限期保留內容，或將內容保留特定數天、數月或數年。</span><span class="sxs-lookup"><span data-stu-id="4092e-264">When you configure a retention policy, you can choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="4092e-265">保留時長是從內容的存留期起算，而不是從套用保留原則的時間起算。</span><span class="sxs-lookup"><span data-stu-id="4092e-265">The retention period is calculated from the age of the content, not from when the retention policy is applied.</span></span>

<span data-ttu-id="4092e-266">保留期間開始時，您還可以選擇建立內容的時間，或者對於檔案和 SharePoint、OneDrive 和 Microsoft 365 群組，還支援選擇上次修改內容的時間。</span><span class="sxs-lookup"><span data-stu-id="4092e-266">For the start of the retention period, you can also choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Microsoft 365 Groups, when the content was last modified.</span></span>

<span data-ttu-id="4092e-267">範例：</span><span class="sxs-lookup"><span data-stu-id="4092e-267">Examples:</span></span>

- <span data-ttu-id="4092e-p132">SharePoint：如果您想要將網站集合中的項目在此內容前次修改後保留七年，而且該網站集合中的某文件已有六年未曾修改，則若該文件後續仍未修改，則只會再保留一年。如果該文件重新編輯，則其存留期將會從新的前次修改日期算起，因而會再保留七年。</span><span class="sxs-lookup"><span data-stu-id="4092e-p132">SharePoint: If you want to retain items in a site collection for seven years after this content is last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified. If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>

- <span data-ttu-id="4092e-p133">Exchange：如果您想要將信箱中的項目保留七年，而且六年前已傳送某郵件，則該郵件只會保留一年。對於 Exchange 項目，時間會根據接收電子郵件或寄出電子郵件的日期。根據前次修改時間保留項目只會套用到 OneDrive 和 SharePoint 中的網站內容。</span><span class="sxs-lookup"><span data-stu-id="4092e-p133">Exchange: If you want to retain items in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year. For Exchange items, the age is based on the date received for incoming email, or the date sent for outgoing email. Retaining items based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>

<span data-ttu-id="4092e-273">在保留期間結束時，您會選擇是否要永久刪除內容：</span><span class="sxs-lookup"><span data-stu-id="4092e-273">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>

![保留設定頁面](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="4092e-275">刪除早於特定存留期的內容</span><span class="sxs-lookup"><span data-stu-id="4092e-275">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="4092e-276">保留原則可以保留然後刪除項目，或刪除舊項目而不保留它們。</span><span class="sxs-lookup"><span data-stu-id="4092e-276">A retention policy can both retain and then delete items, or delete old items without retaining them.</span></span>

<span data-ttu-id="4092e-277">在這兩種情況下，如果您的保留原則刪除項目，請務必了解，文件刪除原則所指定的期限並不是從指派原則的時間算起，而是從建立或修改項目的時間算起。</span><span class="sxs-lookup"><span data-stu-id="4092e-277">In both cases, if your retention policy deletes items, it's important to understand that the time period specified for a retention policy is calculated from the time when the item was created or modified, and not the time since the policy was assigned.</span></span>

<span data-ttu-id="4092e-p134">因此，在第一次指派保留原則之前，尤其是在該原則删除項目時，請首先考慮現有內容的期限以及該原則可能對該內容產生的影響。您也可以在指派新原則前先與使用者溝通，讓他們有足夠的時間來評估可能的影響。</span><span class="sxs-lookup"><span data-stu-id="4092e-p134">So before you assign a retention policy for the first time, and especially when that policy deletes items, first consider the age of the existing content and how the policy may impact that content. You might also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact.</span></span>

### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="4092e-280">套用到整個組織的原則</span><span class="sxs-lookup"><span data-stu-id="4092e-280">A policy that applies to entire locations</span></span>

<span data-ttu-id="4092e-281">當您選擇位置時，除了商務用 Skype，預設設定是當位置的狀態為 **開啟** 時的 **全部**。</span><span class="sxs-lookup"><span data-stu-id="4092e-281">When you choose locations, with the exception of Skype for Business, the default setting is **All** when the status of the location is **On**.</span></span>

<span data-ttu-id="4092e-282">將保留原則套用至整個位置的任何組合時，原則可以包含的收件者、網站、帳戶、群組等的數量沒有限制。</span><span class="sxs-lookup"><span data-stu-id="4092e-282">When a retention policy applies to any combination of entire locations, there is no limit to the number of recipients, sites, accounts, groups, etc., that the policy can include.</span></span>

<span data-ttu-id="4092e-p135">例如，如果原則包含所有 Exchange 電子郵件和所有 SharePoint 網站，無論有多少個網站和收件者都會全部包含。而對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承原則。</span><span class="sxs-lookup"><span data-stu-id="4092e-p135">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and recipients will be included, no matter how many. And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="4092e-285">具有特定包含或排除的原則</span><span class="sxs-lookup"><span data-stu-id="4092e-285">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="4092e-286">注意，當您使用選用設定將保留設定限定為特定使用者、特定 Microsoft 365 群組或特定網站時，需要注意根據原則而異的限制。</span><span class="sxs-lookup"><span data-stu-id="4092e-286">Be aware that if you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of.</span></span> <span data-ttu-id="4092e-287">如需詳細資訊，請參閱[保留原則和保留標籤原則的限制](retention-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="4092e-287">For more information, see [Limits for retention policies and retention label policies](retention-limits.md).</span></span> 

<span data-ttu-id="4092e-288">若要使用選用設定限定保留設定範圍，請確保該位置的 **[狀態]** 為 **[開啟]**，然後使用連結來包含或排除特定使用者、Microsoft 365 群組或網站。</span><span class="sxs-lookup"><span data-stu-id="4092e-288">To use the optional configuration to scope your retention settings, make sure the **Status** of that location is **On**, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span>

> [!WARNING]
> <span data-ttu-id="4092e-289">如果您設定 [包含] 然後移除最後一個，則設定會還原為該位置的 **[全部]**。</span><span class="sxs-lookup"><span data-stu-id="4092e-289">If you configure includes and then remove the last one, the configuration reverts to **All** for the location.</span></span>  <span data-ttu-id="4092e-290">儲存原則前，請確定這是您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="4092e-290">Make sure this is the configuration that you intend before you save the policy.</span></span>
>
> <span data-ttu-id="4092e-291">例如，如果您指定一個 SharePoint 網站要包含在設定為刪除資料的保留原則中，然後移除單一網站，則預設所有 SharePoint 網站都會遵守永久刪除資料的保留原則。</span><span class="sxs-lookup"><span data-stu-id="4092e-291">For example, if you specify one SharePoint site to include in your retention policy that's configured to delete data, and then remove the single site, by default all SharePoint sites will then be subject to the retention policy that permanently deletes data.</span></span> <span data-ttu-id="4092e-292">Exchange 收件者、OneDrive 帳戶、Teams 聊天使用者等都適用。</span><span class="sxs-lookup"><span data-stu-id="4092e-292">The same applies to includes for Exchange recipients, OneDrive accounts, Teams chat users etc.</span></span>
>
> <span data-ttu-id="4092e-293">在這種情況下，如果您不想讓該位置的 **[所有]** 設定遵守保留原則，可以將位置切換為 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="4092e-293">In this scenario, toggle the location off if you don't want the **All** setting for the location to be subject to the retention policy.</span></span> <span data-ttu-id="4092e-294">或者，指定 [排除] 以免於使用原則。</span><span class="sxs-lookup"><span data-stu-id="4092e-294">Alternatively, specify excludes to be exempt from the policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="4092e-295">更新保留原則</span><span class="sxs-lookup"><span data-stu-id="4092e-295">Updating retention policies</span></span>

<span data-ttu-id="4092e-296">在建立及儲存標籤或原則之後，部分設定無法變更，其中包括：</span><span class="sxs-lookup"><span data-stu-id="4092e-296">Some settings can't be changed after a retention policy is created and saved, which include:</span></span>
- <span data-ttu-id="4092e-297">保留原則名稱和保留期間以外的保留設定，以及開始保留期間的時間。</span><span class="sxs-lookup"><span data-stu-id="4092e-297">The retention policy name and the retention settings except the retention period and when to start the retention period.</span></span>

<span data-ttu-id="4092e-298">如果您編輯保留原則，且項目已受限於保留原則中的原始設定，則除了新識別的項目以外，還會將您的更新設定自動套用至這些項目。</span><span class="sxs-lookup"><span data-stu-id="4092e-298">If you edit a retention policy and items are already subject to the original settings in your retention policy, your updated settings will be automatically applied to these items in addition to items that are newly identified.</span></span>

<span data-ttu-id="4092e-299">此更新通常相當快，但可能需要數天的時間。</span><span class="sxs-lookup"><span data-stu-id="4092e-299">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="4092e-300">當您的 Microsoft 365 位置間的原則複寫完成時，您會在 Microsoft 365 合規性中心看到保留原則的狀態從 **開啟 (處理中)** 變成 **開啟 (成功)**。</span><span class="sxs-lookup"><span data-stu-id="4092e-300">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="4092e-301">鎖定原則以防止變更</span><span class="sxs-lookup"><span data-stu-id="4092e-301">Locking the policy to prevent changes</span></span>

<span data-ttu-id="4092e-302">如果您需要確保沒有人可以關閉原則、刪除原則或放寬限制，請參閱 [使用「保留鎖定」來限制變更保留原則和保留標籤原則](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="4092e-302">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>
